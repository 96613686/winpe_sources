# Microsoft.Crm.ServiceBus.ServiceBusUtility::GetNameValues

- ea: `0x2660`
- end: `0x26aa`
- name: `Microsoft.Crm.ServiceBus.ServiceBusUtility::GetNameValues`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2600`

## callees

- `0x2660`

## string_xrefs

- `0x2661`: `token`

## pseudocode

```c

```

## disassembly

```asm
0x2660  ldarg.0
0x2661  ldstr    aToken_0// "token"
0x2666  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x266b  ldarg.0
0x266c  ldc.i4.1
0x266d  newarr   [mscorlib]System.String
0x2672  dup
0x2673  ldc.i4.0
0x2674  ldstr    asc_933C// "&"
0x2679  stelem.ref
0x267a  ldc.i4.1
0x267b  callvirt instance string[] [mscorlib]System.String::Split(string[], valuetype [mscorlib]System.StringSplitOptions)
0x2680  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x2685  ldsfld   class [mscorlib]System.Func`3<class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>, string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>> <>c::<>9__2_0
0x268a  dup
0x268b  brtrue.s loc_26A4
0x268d  pop
0x268e  ldsfld   class <>c <>c::<>9
0x2693  ldftn    instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> <>c::<GetNameValues>b__2_0(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> dict, string rawNameValue)
0x2699  newobj   instance void class [mscorlib]System.Func`3<class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>, string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>>::.ctor(object, native int)
0x269e  dup
0x269f  stsfld   class [mscorlib]System.Func`3<class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>, string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>> <>c::<>9__2_0
0x26a4  call     T0x2B000004
0x26a9  ret
```
