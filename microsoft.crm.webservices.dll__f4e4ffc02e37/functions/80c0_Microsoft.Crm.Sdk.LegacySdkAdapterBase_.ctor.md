# Microsoft.Crm.Sdk.LegacySdkAdapterBase::.ctor

- ea: `0x80c0`
- end: `0x8144`
- name: `Microsoft.Crm.Sdk.LegacySdkAdapterBase::.ctor`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3580`

## callees

- `0x2de0`
- `0x80c0`
- `0x8400`

## string_xrefs

- `0x80d2`: `correlationToken`

## pseudocode

```c

```

## disassembly

```asm
0x80c0  ldarg.0
0x80c1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x80c6  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.LegacySdkAdapterBase::_organizationId
0x80cb  ldarg.0
0x80cc  call     instance void [mscorlib]System.Object::.ctor()
0x80d1  ldarg.1
0x80d2  ldstr    aCorrelationtok// "correlationToken"
0x80d7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x80dc  ldarg.s  4
0x80de  ldstr    aOrganizationid_0// "organizationId"
0x80e3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x80e8  ldarg.0
0x80e9  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken::.ctor()
0x80ee  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken Microsoft.Crm.Sdk.LegacySdkAdapterBase::_authToken
0x80f3  ldarg.0
0x80f4  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken Microsoft.Crm.Sdk.LegacySdkAdapterBase::_authToken
0x80f9  ldc.i4.0
0x80fa  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken::set_AuthenticationType(int32)
0x80ff  ldarga.s 3
0x8101  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x8106  brfalse.s loc_811A
0x8108  ldarg.0
0x8109  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken Microsoft.Crm.Sdk.LegacySdkAdapterBase::_authToken
0x810e  ldarga.s 3
0x8110  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x8115  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken::set_CallerId(valuetype [mscorlib]System.Guid)
0x811a  ldarg.0
0x811b  ldarg.0
0x811c  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken Microsoft.Crm.Sdk.LegacySdkAdapterBase::_authToken
0x8121  ldarg.1
0x8122  ldarg.2
0x8123  ldarg.s  4
0x8125  ldarg.1
0x8126  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken::get_TransactionContextId()
0x812b  newobj   instance void Microsoft.Crm.Sdk.InProcessCrmService::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken authenticationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken callerOriginToken, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid transactionContextId)
0x8130  stfld    class Microsoft.Crm.Sdk.InProcessCrmService Microsoft.Crm.Sdk.LegacySdkAdapterBase::_innerProxy
0x8135  ldarg.0
0x8136  ldarg.s  4
0x8138  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.LegacySdkAdapterBase::_organizationId
0x813d  ldarg.0
0x813e  call     instance void Microsoft.Crm.Sdk.LegacySdkAdapterBase::InitializeExceptionHandler()
0x8143  ret
```
