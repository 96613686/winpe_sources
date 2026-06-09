# Microsoft.Crm.Extensibility.RequestValidator::.ctor

- ea: `0xbe00`
- end: `0xbe3f`
- name: `Microsoft.Crm.Extensibility.RequestValidator::.ctor`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xbe40`

## callees

- `0x41a0`
- `0xbe00`

## string_xrefs

- `0xbe24`: `Update`
- `0xbe0e`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0xbe00  ldarg.0
0xbe01  call     instance void [mscorlib]System.Object::.ctor()
0xbe06  ldc.i4.0
0xbe07  stloc.0
0xbe08  ldarg.1
0xbe09  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0xbe0e  ldstr    aCreate// "Create"
0xbe13  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbe18  brfalse.s loc_BE1E
0xbe1a  ldc.i4.1
0xbe1b  stloc.0
0xbe1c  br.s     loc_BE32
0xbe1e  ldarg.1
0xbe1f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0xbe24  ldstr    aUpdate// "Update"
0xbe29  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbe2e  brfalse.s loc_BE32
0xbe30  ldc.i4.2
0xbe31  stloc.0
0xbe32  ldarg.0
0xbe33  ldloc.0
0xbe34  newobj   instance void Microsoft.Crm.Extensibility.EntityActionResolver::.ctor(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState defaultState)
0xbe39  stfld    class Microsoft.Crm.Extensibility.EntityActionResolver Microsoft.Crm.Extensibility.RequestValidator::_entityActionResolver
0xbe3e  ret
```
