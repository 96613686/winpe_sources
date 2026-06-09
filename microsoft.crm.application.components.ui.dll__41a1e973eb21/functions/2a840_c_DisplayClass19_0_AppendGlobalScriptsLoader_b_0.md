# <>c__DisplayClass19_0::<AppendGlobalScriptsLoader>b__0

- ea: `0x2a840`
- end: `0x2a862`
- name: `<>c__DisplayClass19_0::<AppendGlobalScriptsLoader>b__0`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x8d80`

## string_xrefs

- `0x2a856`: `/_common/global.ashx`

## pseudocode

```c

```

## disassembly

```asm
0x2a840  ldarg.0
0x2a841  ldfld    class Microsoft.Crm.Controls.Footer <>c__DisplayClass19_0::<>4__this
0x2a846  ldarg.1
0x2a847  ldarg.0
0x2a848  ldfld    bool <>c__DisplayClass19_0::needOutlookCookiesPreloader
0x2a84d  ldnull
0x2a84e  ldc.i4.1
0x2a84f  newarr   [mscorlib]System.String
0x2a854  dup
0x2a855  ldc.i4.0
0x2a856  ldstr    aCommonGlobalAs_0// "/_common/global.ashx"
0x2a85b  stelem.ref
0x2a85c  call     instance void Microsoft.Crm.Controls.Footer::AppendOrderedScriptLoader(class [mscorlib]System.Text.StringBuilder jsSnippet, bool enableCookiePreloading, class [mscorlib]System.Action`1<class [mscorlib]System.Text.StringBuilder> appendOnSuccess, string[] scriptPaths)
0x2a861  ret
```
