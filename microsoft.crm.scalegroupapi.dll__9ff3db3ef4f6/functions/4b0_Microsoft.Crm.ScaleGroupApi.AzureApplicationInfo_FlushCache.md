# Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::FlushCache

- ea: `0x4b0`
- end: `0x4c8`
- name: `Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::FlushCache`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x4b0  ldnull
0x4b1  ldftn    class Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::BuildInfo()
0x4b7  newobj   instance void class [mscorlib]System.Func`1<class Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo>::.ctor(object, native int)
0x4bc  ldc.i4.1
0x4bd  newobj   instance void class [mscorlib]System.Lazy`1<class Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo>::.ctor(class [mscorlib]System.Func`1<var<u1>>, !!T0)
0x4c2  stsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo> Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::_cachedInfo
0x4c7  ret
```
