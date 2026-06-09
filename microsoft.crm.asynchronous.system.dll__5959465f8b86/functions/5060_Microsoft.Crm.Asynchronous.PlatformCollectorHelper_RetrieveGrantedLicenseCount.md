# Microsoft.Crm.Asynchronous.PlatformCollectorHelper::RetrieveGrantedLicenseCount

- ea: `0x5060`
- end: `0x50b2`
- name: `Microsoft.Crm.Asynchronous.PlatformCollectorHelper::RetrieveGrantedLicenseCount`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4f30`

## string_xrefs

- `0x5087`: `AccessMode`

## pseudocode

```c

```

## disassembly

```asm
0x5060  ldarg.1
0x5061  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x5066  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x506b  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5070  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x5075  stloc.0
0x5076  ldloc.0
0x5077  ldstr    aRetrievelicens// "RetrieveLicenseInfo"
0x507c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x5081  ldloc.0
0x5082  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x5087  ldstr    aAccessmode// "AccessMode"
0x508c  ldc.i4.0
0x508d  box      [mscorlib]System.Int32
0x5092  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x5097  ldloc.0
0x5098  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x509d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x50a2  ldstr    aGrantedlicense// "GrantedLicenseCount"
0x50a7  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x50ac  unbox.any [mscorlib]System.Int32
0x50b1  ret
```
