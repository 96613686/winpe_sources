# RequestBuilderCacheLoader::LoadCacheData

- ea: `0xfee0`
- end: `0xff09`
- name: `RequestBuilderCacheLoader::LoadCacheData`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x4c50`
- `0x55c0`
- `0x55d0`
- `0xfee0`

## pseudocode

```c

```

## disassembly

```asm
0xfee0  ldarg.2
0xfee1  ldc.i4.0
0xfee2  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0xfee7  stloc.0
0xfee8  ldarg.1
0xfee9  callvirt instance string Microsoft.Crm.Sdk.RequestBuilderKey::get_RequestName()
0xfeee  ldarg.1
0xfeef  callvirt instance string Microsoft.Crm.Sdk.RequestBuilderKey::get_Namespace()
0xfef4  ldarg.2
0xfef5  newobj   instance void Microsoft.Crm.Sdk.RequestBuilder::.ctor(string requestName, string namespaceName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xfefa  stloc.1
0xfefb  leave.s  loc_FF07
0xfefd  ldloc.0
0xfefe  brfalse.s loc_FF06
0xff00  ldloc.0
0xff01  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xff06  endfinally
0xff07  ldloc.1
0xff08  ret
```
