# <>c__DisplayClass193_0::<DeleteMultipleWithoutSecurityChecks>b__0

- ea: `0x8c410`
- end: `0x8c521`
- name: `<>c__DisplayClass193_0::<DeleteMultipleWithoutSecurityChecks>b__0`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x4c940`
- `0x4cb20`
- `0x51950`
- `0x51aa0`
- `0x5e350`
- `0x5e360`
- `0x5f600`
- `0x8c410`

## string_xrefs

- `0x8c489`: `EntityObjectTypeCode: {0} is not supported by DeleteMultipleWithoutSecurityChecks()`
- `0x8c4ca`: `BPOMultipleDeleteCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x8c410  ldarg.0
0x8c411  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass193_0::entityIds
0x8c416  ldstr    aEnityids// "enityIds"
0x8c41b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8c420  ldarg.0
0x8c421  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass193_0::context
0x8c426  ldstr    aContext// "context"
0x8c42b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8c430  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x8c435  stloc.0
0x8c436  ldarg.0
0x8c437  ldfld    int32 <>c__DisplayClass193_0::entityObjectTypeCode
0x8c43c  ldc.i4   0x1069
0x8c441  beq.s    loc_8C4AD
0x8c443  ldarg.0
0x8c444  ldfld    int32 <>c__DisplayClass193_0::entityObjectTypeCode
0x8c449  ldc.i4   0x125F
0x8c44e  beq.s    loc_8C4AD
0x8c450  ldarg.0
0x8c451  ldfld    int32 <>c__DisplayClass193_0::entityObjectTypeCode
0x8c456  ldc.i4   0x1F43
0x8c45b  beq.s    loc_8C4AD
0x8c45d  ldarg.0
0x8c45e  ldfld    int32 <>c__DisplayClass193_0::entityObjectTypeCode
0x8c463  ldc.i4   0x26B7
0x8c468  beq.s    loc_8C4AD
0x8c46a  ldarg.0
0x8c46b  ldfld    int32 <>c__DisplayClass193_0::entityObjectTypeCode
0x8c470  ldc.i4   0x125C
0x8c475  beq.s    loc_8C4AD
0x8c477  ldarg.0
0x8c478  ldfld    int32 <>c__DisplayClass193_0::entityObjectTypeCode
0x8c47d  ldc.i4   0x232F
0x8c482  beq.s    loc_8C4AD
0x8c484  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8c489  ldstr    aEntityobjectty_0// "EntityObjectTypeCode: {0} is not suppor"...
0x8c48e  ldc.i4.1
0x8c48f  newarr   [mscorlib]System.Object
0x8c494  dup
0x8c495  ldc.i4.0
0x8c496  ldarg.0
0x8c497  ldfld    int32 <>c__DisplayClass193_0::entityObjectTypeCode
0x8c49c  box      [mscorlib]System.Int32
0x8c4a1  stelem.ref
0x8c4a2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8c4a7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x8c4ac  throw
0x8c4ad  ldarg.0
0x8c4ae  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass193_0::entityIds
0x8c4b3  ldarg.0
0x8c4b4  ldfld    int32 <>c__DisplayClass193_0::entityObjectTypeCode
0x8c4b9  ldarg.0
0x8c4ba  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass193_0::context
0x8c4bf  call     bool Microsoft.Crm.BusinessEntities.CascadeEngine::DeleteMultiple(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> entityIds, int32 entityObjectTypeCode, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8c4c4  pop
0x8c4c5  call     class Microsoft.Crm.Platform.Server.BusinessProcessObjectTelemetryEvents Microsoft.Crm.Platform.Server.BusinessProcessObjectTelemetryEvents::get_Instance()
0x8c4ca  ldstr    aBpomultipledel// "BPOMultipleDeleteCompleted"
0x8c4cf  ldarg.0
0x8c4d0  ldfld    int32 <>c__DisplayClass193_0::entityObjectTypeCode
0x8c4d5  ldarg.0
0x8c4d6  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass193_0::context
0x8c4db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8c4e0  ldloc.0
0x8c4e1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x8c4e6  callvirt instance void Microsoft.Crm.Platform.Server.BusinessProcessObjectTelemetryEvents::OperationCompleted(string eventName, int32 entityTypeCode, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x8c4eb  call     class Microsoft.Crm.Platform.Server.BPOCrmTelemetryEvents Microsoft.Crm.Platform.Server.BPOCrmTelemetryEvents::get_Instance()
0x8c4f0  ldarg.0
0x8c4f1  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass193_0::context
0x8c4f6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8c4fb  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x8c500  ldarg.0
0x8c501  ldfld    int32 <>c__DisplayClass193_0::entityObjectTypeCode
0x8c506  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x8c50b  ldloc.0
0x8c50c  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x8c511  call     string Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_CurrentClientId()
0x8c516  call     string Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_CurrentClientType()
0x8c51b  callvirt instance void Microsoft.Crm.Platform.Server.BPOCrmTelemetryEvents::BPOMultipleDeleteCompleted(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, int32 entityTypeCode, string userPuid, int64 executionTime, string clientSessionId, string clientType)
0x8c520  ret
```
