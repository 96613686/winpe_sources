# Microsoft.Crm.Application.Utility.WrpcCheckSuppressor::SaveTokenState

- ea: `0x4c7a0`
- end: `0x4c7f2`
- name: `Microsoft.Crm.Application.Utility.WrpcCheckSuppressor::SaveTokenState`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4c770`

## callees

- `0x4c760`
- `0x4c7a0`

## string_xrefs

- `0x4c7a5`: `WRPCTokenState`
- `0x4c7b6`: `WRPCTokenState`
- `0x4c7c8`: `WRPCTokenState`

## pseudocode

```c

```

## disassembly

```asm
0x4c7a0  call     class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Items()
0x4c7a5  ldstr    aWrpctokenstate// "WRPCTokenState"
0x4c7aa  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x4c7af  brfalse.s loc_4C7E2
0x4c7b1  call     class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Items()
0x4c7b6  ldstr    aWrpctokenstate// "WRPCTokenState"
0x4c7bb  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x4c7c0  brfalse.s loc_4C7E2
0x4c7c2  ldarg.0
0x4c7c3  call     class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Items()
0x4c7c8  ldstr    aWrpctokenstate// "WRPCTokenState"
0x4c7cd  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x4c7d2  unbox.any TokenState
0x4c7d7  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype TokenState>::.ctor(var<u1>)
0x4c7dc  call     instance void Microsoft.Crm.Application.Utility.WrpcCheckSuppressor::set_InitialTokenState(valuetype [mscorlib]System.Nullable`1<valuetype TokenState> value)
0x4c7e1  ret
0x4c7e2  ldarg.0
0x4c7e3  ldloca.s 0
0x4c7e5  initobj  valuetype [mscorlib]System.Nullable`1<valuetype TokenState>
0x4c7eb  ldloc.0
0x4c7ec  call     instance void Microsoft.Crm.Application.Utility.WrpcCheckSuppressor::set_InitialTokenState(valuetype [mscorlib]System.Nullable`1<valuetype TokenState> value)
0x4c7f1  ret
```
