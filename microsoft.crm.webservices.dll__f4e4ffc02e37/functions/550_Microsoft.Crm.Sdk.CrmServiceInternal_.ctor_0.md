# Microsoft.Crm.Sdk.CrmServiceInternal::.ctor_0

- ea: `0x550`
- end: `0x599`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::.ctor_0`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x540`
- `0x2e20`

## callees

- `0x550`

## string_xrefs

- `0x57f`: `The Microsoft Dynamics CRM 4.0 (2007) Web service endpoint is not supported in this release.`

## pseudocode

```c

```

## disassembly

```asm
0x550  ldarg.0
0x551  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x556  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.CrmServiceInternal::_transactionContextId
0x55b  ldarg.0
0x55c  call     instance void [mscorlib]System.Object::.ctor()
0x561  ldarg.2
0x562  ldsfld   class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EndpointVersionProvider::CrmSdk2007Version
0x567  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x56c  brfalse.s loc_58A
0x56e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOrganizationGuid()
0x573  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LegacySupportValidatorUtility::Is2007EndpointValidForOrg(valuetype [mscorlib]System.Guid)
0x578  brtrue.s loc_58A
0x57a  ldc.i4   0x194
0x57f  ldstr    aTheMicrosoftDy// "The Microsoft Dynamics CRM 4.0 (2007) W"...
0x584  newobj   instance void [System.Web]System.Web.HttpException::.ctor(int32, string)
0x589  throw
0x58a  ldarg.0
0x58b  ldarg.1
0x58c  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.CrmServiceInternal::_transactionContextId
0x591  ldarg.0
0x592  ldarg.2
0x593  stfld    class [mscorlib]System.Version Microsoft.Crm.Sdk.CrmServiceInternal::_endpointVersion
0x598  ret
```
