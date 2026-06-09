# Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::StateTransitionCreated

- ea: `0x32000`
- end: `0x320bb`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::StateTransitionCreated`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x39480`

## callees

- `0x317b0`
- `0x317c0`

## string_xrefs

- `0x3205f`: `componentType`
- `0x3206b`: `componentName`
- `0x32077`: `componentId`

## pseudocode

```c

```

## disassembly

```asm
0x32000  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x32005  ldarg.0
0x32006  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3200b  ldarg.0
0x3200c  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x32011  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x32016  callvirt instance string [mscorlib]System.Object::ToString()
0x3201b  stloc.0
0x3201c  ldc.i4.8
0x3201d  newarr   [mscorlib]System.String
0x32022  dup
0x32023  ldc.i4.0
0x32024  ldstr    aCreatingStateT// "Creating state transition: "
0x32029  stelem.ref
0x3202a  dup
0x3202b  ldc.i4.1
0x3202c  ldarg.1
0x3202d  stelem.ref
0x3202e  dup
0x3202f  ldc.i4.2
0x32030  ldstr    asc_CC16C// ", "
0x32035  stelem.ref
0x32036  dup
0x32037  ldc.i4.3
0x32038  ldarg.2
0x32039  stelem.ref
0x3203a  dup
0x3203b  ldc.i4.4
0x3203c  ldstr    asc_CC16C// ", "
0x32041  stelem.ref
0x32042  dup
0x32043  ldc.i4.5
0x32044  ldarg.3
0x32045  stelem.ref
0x32046  dup
0x32047  ldc.i4.6
0x32048  ldstr    asc_CC16C// ", "
0x3204d  stelem.ref
0x3204e  dup
0x3204f  ldc.i4.7
0x32050  ldarg.s  4
0x32052  stelem.ref
0x32053  call     string [mscorlib]System.String::Concat(string[])
0x32058  stloc.1
0x32059  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x3205e  dup
0x3205f  ldstr    aComponenttype_0// "componentType"
0x32064  ldarg.1
0x32065  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x3206a  dup
0x3206b  ldstr    aComponentname// "componentName"
0x32070  ldarg.2
0x32071  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x32076  dup
0x32077  ldstr    aComponentid// "componentId"
0x3207c  ldarg.3
0x3207d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x32082  dup
0x32083  ldstr    aStatetransitio// "stateTransitionType"
0x32088  ldarg.s  4
0x3208a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x3208f  dup
0x32090  ldstr    aCstinput// "cstInput"
0x32095  ldarg.s  5
0x32097  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x3209c  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x320a1  call     class Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetryEvents Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetryEvents::get_Instance()
0x320a6  ldarg.0
0x320a7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x320ac  ldsfld   string Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::applicationVersion
0x320b1  ldloc.0
0x320b2  ldloc.1
0x320b3  ldarg.s  5
0x320b5  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetryEvents::StateTransitionCreated(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string dbVersion, string message, string cstInput)
0x320ba  ret
```
