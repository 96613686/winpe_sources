# Microsoft.Crm.Sdk.CrmServiceSoapExtensionReflector::ReflectMethod

- ea: `0xa140`
- end: `0xa1e8`
- name: `Microsoft.Crm.Sdk.CrmServiceSoapExtensionReflector::ReflectMethod`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xa140`
- `0xa340`
- `0xa410`
- `0xa480`

## string_xrefs

- `0xa150`: `CrmService`
- `0xa1ae`: `Loading ServiceDescription.`

## pseudocode

```c

```

## disassembly

```asm
0xa140  ldarg.0
0xa141  call     instance class [System.Web.Services]System.Web.Services.Description.ProtocolReflector [System.Web.Services]System.Web.Services.Description.SoapExtensionReflector::get_ReflectionContext()
0xa146  callvirt instance class [mscorlib]System.Type [System.Web.Services]System.Web.Services.Description.ProtocolReflector::get_ServiceType()
0xa14b  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xa150  ldstr    aCrmservice// "CrmService"
0xa155  ldc.i4.4
0xa156  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xa15b  brfalse.s loc_A15E
0xa15d  ret
0xa15e  ldarg.0
0xa15f  call     instance class [System.Web.Services]System.Web.Services.Description.ProtocolReflector [System.Web.Services]System.Web.Services.Description.SoapExtensionReflector::get_ReflectionContext()
0xa164  stloc.0
0xa165  ldarg.0
0xa166  ldarg.0
0xa167  ldfld    int32 Microsoft.Crm.Sdk.CrmServiceSoapExtensionReflector::_reflectMethodCallCount
0xa16c  ldc.i4.1
0xa16d  add
0xa16e  stfld    int32 Microsoft.Crm.Sdk.CrmServiceSoapExtensionReflector::_reflectMethodCallCount
0xa173  ldarg.0
0xa174  ldfld    int32 Microsoft.Crm.Sdk.CrmServiceSoapExtensionReflector::_reflectMethodCallCount
0xa179  ldarg.0
0xa17a  call     instance class [System.Web.Services]System.Web.Services.Description.ProtocolReflector [System.Web.Services]System.Web.Services.Description.SoapExtensionReflector::get_ReflectionContext()
0xa17f  callvirt instance class [System.Web.Services]System.Web.Services.Protocols.LogicalMethodInfo[] [System.Web.Services]System.Web.Services.Description.ProtocolReflector::get_Methods()
0xa184  ldlen
0xa185  conv.i4
0xa186  bne.un.s loc_A1E7
0xa188  ldsfld   int32 Microsoft.Crm.Sdk.CrmServiceSoapExtensionReflector::_callCount
0xa18d  ldc.i4.1
0xa18e  add
0xa18f  dup
0xa190  stsfld   int32 Microsoft.Crm.Sdk.CrmServiceSoapExtensionReflector::_callCount
0xa195  ldc.i4.1
0xa196  ble.s    loc_A1E7
0xa198  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOrganizationGuid()
0xa19d  stloc.1
0xa19e  ldloc.1
0xa19f  ldc.i4.s 0x1A
0xa1a1  ldstr    a0// "{0}"
0xa1a6  ldc.i4.1
0xa1a7  newarr   [mscorlib]System.Object
0xa1ac  dup
0xa1ad  ldc.i4.0
0xa1ae  ldstr    aLoadingService// "Loading ServiceDescription."
0xa1b3  stelem.ref
0xa1b4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa1b9  ldarg.0
0xa1ba  call     instance class [System.Web.Services]System.Web.Services.Description.ProtocolReflector [System.Web.Services]System.Web.Services.Description.SoapExtensionReflector::get_ReflectionContext()
0xa1bf  callvirt instance class [mscorlib]System.Type [System.Web.Services]System.Web.Services.Description.ProtocolReflector::get_ServiceType()
0xa1c4  call     string Microsoft.Crm.Sdk.CrmServiceSoapExtensionReflector::GetCurrentNamespace(class [mscorlib]System.Type webServiceType)
0xa1c9  stloc.2
0xa1ca  ldloc.1
0xa1cb  ldloc.2
0xa1cc  ldc.i4.0
0xa1cd  newobj   instance void Microsoft.Crm.Sdk.CrmSchemaFixer::.ctor(valuetype [mscorlib]System.Guid organizationId, string namespaceName, bool renderPrivateMethods)
0xa1d2  ldloc.0
0xa1d3  callvirt instance class [System.Web.Services]System.Web.Services.Description.ServiceDescription [System.Web.Services]System.Web.Services.Description.ProtocolReflector::get_ServiceDescription()
0xa1d8  callvirt instance class [System.Web.Services]System.Web.Services.Description.Types [System.Web.Services]System.Web.Services.Description.ServiceDescription::get_Types()
0xa1dd  callvirt instance class [System.Xml]System.Xml.Serialization.XmlSchemas [System.Web.Services]System.Web.Services.Description.Types::get_Schemas()
0xa1e2  callvirt instance void Microsoft.Crm.Sdk.CrmSchemaFixer::ReplaceSchemas(class [System.Xml]System.Xml.Serialization.XmlSchemas oldSchemas)
0xa1e7  ret
```
