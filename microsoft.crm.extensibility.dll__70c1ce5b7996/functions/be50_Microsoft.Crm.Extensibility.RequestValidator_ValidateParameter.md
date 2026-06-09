# Microsoft.Crm.Extensibility.RequestValidator::ValidateParameter

- ea: `0xbe50`
- end: `0xbebc`
- name: `Microsoft.Crm.Extensibility.RequestValidator::ValidateParameter`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0xb3a0`

## callees

- `0x41b0`
- `0xbe50`
- `0xbec0`

## string_xrefs

- `0xbe9f`: `EntityState must be set to null, Created (for Create message) or Changed (for Update message)`

## pseudocode

```c

```

## disassembly

```asm
0xbe50  ldarg.0
0xbe51  ldfld    class Microsoft.Crm.Extensibility.EntityActionResolver Microsoft.Crm.Extensibility.RequestValidator::_entityActionResolver
0xbe56  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState Microsoft.Crm.Extensibility.EntityActionResolver::get_DefaultState()
0xbe5b  brfalse.s loc_BEAA
0xbe5d  ldarg.2
0xbe5e  ldstr    aTarget// "Target"
0xbe63  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbe68  brfalse.s loc_BEAA
0xbe6a  ldarg.3
0xbe6b  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0xbe70  stloc.0
0xbe71  ldloc.0
0xbe72  brfalse.s loc_BEAA
0xbe74  ldloc.0
0xbe75  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_EntityState()
0xbe7a  stloc.1
0xbe7b  ldloca.s 1
0xbe7d  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState>::get_HasValue()
0xbe82  brfalse.s loc_BEAA
0xbe84  ldloc.0
0xbe85  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_EntityState()
0xbe8a  stloc.1
0xbe8b  ldloca.s 1
0xbe8d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState>::get_Value()
0xbe92  ldarg.0
0xbe93  ldfld    class Microsoft.Crm.Extensibility.EntityActionResolver Microsoft.Crm.Extensibility.RequestValidator::_entityActionResolver
0xbe98  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState Microsoft.Crm.Extensibility.EntityActionResolver::get_DefaultState()
0xbe9d  beq.s    loc_BEAA
0xbe9f  ldstr    aEntitystateMus// "EntityState must be set to null, Create"...
0xbea4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xbea9  throw
0xbeaa  ldarg.0
0xbeab  ldarg.1
0xbeac  ldarg.2
0xbead  ldarg.3
0xbeae  ldarg.0
0xbeaf  ldfld    class Microsoft.Crm.Extensibility.EntityActionResolver Microsoft.Crm.Extensibility.RequestValidator::_entityActionResolver
0xbeb4  ldarg.s  4
0xbeb6  call     instance void Microsoft.Crm.Extensibility.RequestValidator::ValidateRequiredMembers(string requestName, string fieldName, object fieldValue, class Microsoft.Crm.Extensibility.EntityActionResolver entityActionResolver, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xbebb  ret
```
