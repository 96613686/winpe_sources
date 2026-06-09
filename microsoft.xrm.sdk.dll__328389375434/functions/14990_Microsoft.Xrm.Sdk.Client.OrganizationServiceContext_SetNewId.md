# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SetNewId

- ea: `0x14990`
- end: `0x149cd`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::SetNewId`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x23d90`
- `0x24360`

## callees

- `0x3bc0`
- `0x3bd0`
- `0x3c30`
- `0x14990`
- `0x149d0`

## pseudocode

```c

```

## disassembly

```asm
0x14990  ldarg.0
0x14991  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState> Microsoft.Xrm.Sdk.Entity::get_EntityState()
0x14996  stloc.0
0x14997  ldc.i4.1
0x14998  stloc.1
0x14999  ldloca.s 0
0x1499b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::GetValueOrDefault()
0x149a0  ldloc.1
0x149a1  ceq
0x149a3  ldloca.s 0
0x149a5  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.Xrm.Sdk.EntityState>::get_HasValue()
0x149aa  and
0x149ab  brfalse.s loc_149CC
0x149ad  ldarg.0
0x149ae  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Entity::get_Id()
0x149b3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x149b8  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x149bd  brfalse.s loc_149CC
0x149bf  call     valuetype [mscorlib]System.Guid Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::CreateSequentialGuid()
0x149c4  stloc.2
0x149c5  ldarg.0
0x149c6  ldloc.2
0x149c7  callvirt instance void Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid value)
0x149cc  ret
```
