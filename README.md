# Censored - A .NET Profanity Censoring Library

A .NET library to easily easily detect and censor words. Inspired by a blog from [James Newton-King](http://james.newtonking.com/archive/2009/07/03/simple-net-profanity-filter) and code used with [permission](https://twitter.com/JamesNK/status/688905862723682304).

Grab the NuGet: [![NuGet](https://img.shields.io/nuget/v/Censored.svg?label=NuGet)](https://www.nuget.org/packages/Censored/)

Build Status: [![Build status](https://ci.appveyor.com/api/projects/status/nsj9rae1g93hy62o/branch/master?svg=true)](https://ci.appveyor.com/project/JamesMontemagno/Censored/branch/master)

### Usage

```csharp
var censoredWords = new List<string>
{
  "gosh",
  "drat",
  "darn*",
};
 
var censor = new Censor(censoredWords);
string result;

 
result = censor.CensorText("I stubbed my toe. Gosh it hurts!");
// I stubbed my toe. **** it hurts!
 
result = censor.CensorText("The midrate on the USD -> EUR forex trade has soured my day. Drat!");
// The midrate on the USD -> EUR forex trade has soured my day. ****!
 
result = censor.CensorText("Gosh darnit, my shoe laces are undone.");
// **** ******, my shoe laces are undone.


bool hasCensoredWord;

hasCensoredWord = censor.CensorText("I stubbed my toe. Gosh it hurts!");
// true

hasCensoredWord = censor.CensorText("I stubbed my toe. It hurts!");
// false
```


### License
Under MIT (please see LICENSE file)