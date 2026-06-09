# Microsoft.Crm.Application.Security.WrpcValidationBypass::.ctor

- ea: `0x30130`
- end: `0x30172`
- name: `Microsoft.Crm.Application.Security.WrpcValidationBypass::.ctor`
- size: `66`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x32bb0`
- `0x35ed0`
- `0x43a90`
- `0x6c150`

## callees

- `0x30130`

## string_xrefs

- `0x30148`: `WRPCTokenState`
- `0x30161`: `WRPCTokenState`

## pseudocode

```c

```

## disassembly

```asm
0x30130  ldarg.0
0x30131  call     instance void [mscorlib]System.Object::.ctor()
0x30136  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x3013b  brfalse.s loc_30171
0x3013d  ldarg.0
0x3013e  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x30143  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x30148  ldstr    aWrpctokenstate// "WRPCTokenState"
0x3014d  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x30152  stfld    object Microsoft.Crm.Application.Security.WrpcValidationBypass::_oldTokenState
0x30157  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x3015c  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x30161  ldstr    aWrpctokenstate// "WRPCTokenState"
0x30166  ldc.i4.3
0x30167  box      Microsoft.Crm.Application.Security.WrpcTokenState
0x3016c  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x30171  ret
```
