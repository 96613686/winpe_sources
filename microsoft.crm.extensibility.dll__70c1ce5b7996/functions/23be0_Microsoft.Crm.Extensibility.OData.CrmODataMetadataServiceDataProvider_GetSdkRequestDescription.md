# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetSdkRequestDescription

- ea: `0x23be0`
- end: `0x23c4a`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetSdkRequestDescription`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x23b70`
- `0x23bb0`

## callees

- `0x7040`
- `0x21860`
- `0x23be0`
- `0x23d10`
- `0x23d50`

## string_xrefs

- `0x23c0a`: `Metadata Entity {0} does not support delete operation`

## pseudocode

```c

```

## disassembly

```asm
0x23be0  ldarg.2
0x23be1  ldarg.1
0x23be2  ldarg.0
0x23be3  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x23be8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x23bed  stind.ref
0x23bee  ldsfld   string [mscorlib]System.String::Empty
0x23bf3  stloc.0
0x23bf4  ldarg.2
0x23bf5  ldind.ref
0x23bf6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrimitiveOperationDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_PrimitiveOperations()
0x23bfb  ldc.i4.4
0x23bfc  ldloca.s 0
0x23bfe  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrimitiveOperationType, string>::TryGetValue(var<u1>, !!T0)
0x23c03  brtrue.s loc_23C2F
0x23c05  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23c0a  ldstr    aMetadataEntity_0// "Metadata Entity {0} does not support de"...
0x23c0f  ldc.i4.1
0x23c10  newarr   [mscorlib]System.Object
0x23c15  dup
0x23c16  ldc.i4.0
0x23c17  ldarg.2
0x23c18  ldind.ref
0x23c19  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_Name()
0x23c1e  stelem.ref
0x23c1f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x23c24  ldstr    aGet_0// "GET"
0x23c29  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x23c2e  throw
0x23c2f  ldloc.0
0x23c30  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OrganizationDataService::GetOrganizationContext()
0x23c35  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription Microsoft.Crm.Extensibility.OData.CrmSdkRequestResponseProvider::GetRequestDescription(string requestName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x23c3a  stloc.1
0x23c3b  ldarg.3
0x23c3c  ldloc.1
0x23c3d  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkRequestDescription::get_RequestName()
0x23c42  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor(string)
0x23c47  stind.ref
0x23c48  ldloc.1
0x23c49  ret
```
