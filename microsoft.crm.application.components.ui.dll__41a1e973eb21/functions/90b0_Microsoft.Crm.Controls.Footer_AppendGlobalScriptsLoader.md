# Microsoft.Crm.Controls.Footer::AppendGlobalScriptsLoader

- ea: `0x90b0`
- end: `0x913b`
- name: `Microsoft.Crm.Controls.Footer::AppendGlobalScriptsLoader`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x8f00`

## callees

- `0x8d80`
- `0x90b0`
- `0x142c0`
- `0x2a830`

## string_xrefs

- `0x911f`: `/_static/_common/scripts/MicrosoftAjax.js`
- `0x9127`: `/_static/_common/scripts/EncodeDecode.js`
- `0x912f`: `/_static/_common/scripts/Microsoft.Crm.Client.Core.js`

## pseudocode

```c

```

## disassembly

```asm
0x90b0  newobj   instance void <>c__DisplayClass19_0::.ctor()
0x90b5  stloc.0
0x90b6  ldloc.0
0x90b7  ldarg.0
0x90b8  stfld    class Microsoft.Crm.Controls.Footer <>c__DisplayClass19_0::<>4__this
0x90bd  ldloc.0
0x90be  ldarg.2
0x90bf  stfld    bool <>c__DisplayClass19_0::needOutlookCookiesPreloader
0x90c4  ldloc.0
0x90c5  ldloc.0
0x90c6  ldftn    instance void <>c__DisplayClass19_0::<AppendGlobalScriptsLoader>b__0(class [mscorlib]System.Text.StringBuilder snippet)
0x90cc  newobj   instance void class [mscorlib]System.Action`1<class [mscorlib]System.Text.StringBuilder>::.ctor(object, native int)
0x90d1  stfld    class [mscorlib]System.Action`1<class [mscorlib]System.Text.StringBuilder> <>c__DisplayClass19_0::globalAshxLoader
0x90d6  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x90db  ldc.i4.1
0x90dc  newarr   [mscorlib]System.Char
0x90e1  dup
0x90e2  ldc.i4.0
0x90e3  ldc.i4.s 0x2F
0x90e5  stelem.i2
0x90e6  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x90eb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x90f0  brtrue.s loc_9101
0x90f2  ldloc.0
0x90f3  ldftn    instance void <>c__DisplayClass19_0::<AppendGlobalScriptsLoader>b__1(class [mscorlib]System.Text.StringBuilder snippet)
0x90f9  newobj   instance void class [mscorlib]System.Action`1<class [mscorlib]System.Text.StringBuilder>::.ctor(object, native int)
0x90fe  stloc.1
0x90ff  br.s     loc_910E
0x9101  ldloc.0
0x9102  ldftn    instance void <>c__DisplayClass19_0::<AppendGlobalScriptsLoader>b__2(class [mscorlib]System.Text.StringBuilder snippet)
0x9108  newobj   instance void class [mscorlib]System.Action`1<class [mscorlib]System.Text.StringBuilder>::.ctor(object, native int)
0x910d  stloc.1
0x910e  ldarg.0
0x910f  ldarg.1
0x9110  ldloc.0
0x9111  ldfld    bool <>c__DisplayClass19_0::needOutlookCookiesPreloader
0x9116  ldloc.1
0x9117  ldc.i4.3
0x9118  newarr   [mscorlib]System.String
0x911d  dup
0x911e  ldc.i4.0
0x911f  ldstr    aStaticCommonSc_6// "/_static/_common/scripts/MicrosoftAjax."...
0x9124  stelem.ref
0x9125  dup
0x9126  ldc.i4.1
0x9127  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/EncodeDecode.j"...
0x912c  stelem.ref
0x912d  dup
0x912e  ldc.i4.2
0x912f  ldstr    aStaticCommonSc_8// "/_static/_common/scripts/Microsoft.Crm."...
0x9134  stelem.ref
0x9135  call     instance void Microsoft.Crm.Controls.Footer::AppendOrderedScriptLoader(class [mscorlib]System.Text.StringBuilder jsSnippet, bool enableCookiePreloading, class [mscorlib]System.Action`1<class [mscorlib]System.Text.StringBuilder> appendOnSuccess, string[] scriptPaths)
0x913a  ret
```
