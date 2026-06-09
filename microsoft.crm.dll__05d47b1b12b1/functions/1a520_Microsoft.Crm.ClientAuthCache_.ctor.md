# Microsoft.Crm.ClientAuthCache::.ctor

- ea: `0x1a520`
- end: `0x1a550`
- name: `Microsoft.Crm.ClientAuthCache::.ctor`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x1a544`: `Creating a client authentication cache.`

## pseudocode

```c

```

## disassembly

```asm
0x1a520  ldarg.0
0x1a521  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x1a526  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ClientAuthCache::secretCache
0x1a52b  ldarg.0
0x1a52c  call     instance void [mscorlib]System.Object::.ctor()
0x1a531  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1a536  ldc.i4.1
0x1a537  ldstr    a0_0// "{0}"
0x1a53c  ldc.i4.1
0x1a53d  newarr   [mscorlib]System.Object
0x1a542  dup
0x1a543  ldc.i4.0
0x1a544  ldstr    aCreatingAClien// "Creating a client authentication cache."
0x1a549  stelem.ref
0x1a54a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a54f  ret
```
