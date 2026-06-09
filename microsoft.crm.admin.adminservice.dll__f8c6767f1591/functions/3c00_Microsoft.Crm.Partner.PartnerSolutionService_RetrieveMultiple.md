# Microsoft.Crm.Partner.PartnerSolutionService::RetrieveMultiple

- ea: `0x3c00`
- end: `0x3d5c`
- name: `Microsoft.Crm.Partner.PartnerSolutionService::RetrieveMultiple`
- size: `348`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x31e0`
- `0x3200`
- `0x3220`
- `0x3240`
- `0x3260`
- `0x3280`
- `0x32a0`
- `0x32c0`
- `0x3660`
- `0x39f0`
- `0x3c00`

## string_xrefs

- `0x3cfb`: `DeploymentXml`
- `0x3c3c`: `D:\a\1\s\src\CrmLive\Admin\Partner\PartnerSolutionService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x3c00  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Partner.PartnerSolutionInfo>::.ctor()
0x3c05  stloc.0
0x3c06  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3c0b  stloc.1
0x3c0c  ldloc.1
0x3c0d  ldstr    aPartnerid// "PartnerId"
0x3c12  ldarg.1
0x3c13  box      [mscorlib]System.Guid
0x3c18  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3c1d  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x3c22  ldstr    aPartnersolutio_2// "PartnerSolution"
0x3c27  ldnull
0x3c28  ldc.i4.1
0x3c29  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x3c2e  dup
0x3c2f  ldc.i4.0
0x3c30  ldloc.1
0x3c31  stelem.ref
0x3c32  ldc.i4   0xA0
0x3c37  ldstr    aRetrievemultip// "RetrieveMultiple"
0x3c3c  ldstr    aDA1SSrcCrmlive_5// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Partn"...
0x3c41  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x3c46  stloc.2
0x3c47  newobj   instance void Microsoft.Crm.Partner.PartnerService::.ctor()
0x3c4c  stloc.3
0x3c4d  ldloc.2
0x3c4e  brfalse  loc_3D55
0x3c53  ldloc.2
0x3c54  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x3c59  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x3c5e  stloc.s  4
0x3c60  br       loc_3D39
0x3c65  ldloca.s 4
0x3c67  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x3c6c  stloc.s  5
0x3c6e  ldloc.3
0x3c6f  ldloc.s  5
0x3c71  ldstr    aPartnerid// "PartnerId"
0x3c76  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3c7b  unbox.any [mscorlib]System.Guid
0x3c80  callvirt instance string Microsoft.Crm.Partner.PartnerService::GetNameFromId(valuetype [mscorlib]System.Guid id)
0x3c85  stloc.s  6
0x3c87  newobj   instance void Microsoft.Crm.Partner.PartnerSolutionInfo::.ctor()
0x3c8c  stloc.s  7
0x3c8e  ldloc.s  7
0x3c90  ldloc.s  5
0x3c92  ldstr    aId// "Id"
0x3c97  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3c9c  unbox.any [mscorlib]System.Guid
0x3ca1  callvirt instance void Microsoft.Crm.Partner.PartnerSolutionInfo::set_Id(valuetype [mscorlib]System.Guid value)
0x3ca6  ldloc.s  7
0x3ca8  ldloc.s  5
0x3caa  ldstr    aName// "Name"
0x3caf  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3cb4  castclass [mscorlib]System.String
0x3cb9  callvirt instance void Microsoft.Crm.Partner.PartnerSolutionInfo::set_SolutionName(string value)
0x3cbe  ldloc.s  7
0x3cc0  ldloc.s  6
0x3cc2  callvirt instance void Microsoft.Crm.Partner.PartnerSolutionInfo::set_PartnerName(string value)
0x3cc7  ldloc.s  7
0x3cc9  ldloc.s  5
0x3ccb  ldstr    aDescription// "Description"
0x3cd0  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3cd5  castclass [mscorlib]System.String
0x3cda  callvirt instance void Microsoft.Crm.Partner.PartnerSolutionInfo::set_Description(string value)
0x3cdf  ldloc.s  7
0x3ce1  ldloc.s  5
0x3ce3  ldstr    aApplicationred// "ApplicationRedirectUrl"
0x3ce8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3ced  castclass [mscorlib]System.String
0x3cf2  callvirt instance void Microsoft.Crm.Partner.PartnerSolutionInfo::set_ApplicationRedirectUrl(string value)
0x3cf7  ldloc.s  7
0x3cf9  ldloc.s  5
0x3cfb  ldstr    aDeploymentxml// "DeploymentXml"
0x3d00  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3d05  castclass [mscorlib]System.String
0x3d0a  call     T0x2B00000C
0x3d0f  callvirt instance void Microsoft.Crm.Partner.PartnerSolutionInfo::set_DeploymentConfig(class Microsoft.Crm.Partner.PartnerSolutionDeploymentConfig value)
0x3d14  ldloc.s  7
0x3d16  ldloc.s  5
0x3d18  ldstr    aLocalizeddata// "LocalizedData"
0x3d1d  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3d22  castclass [mscorlib]System.String
0x3d27  call     T0x2B00000D
0x3d2c  callvirt instance void Microsoft.Crm.Partner.PartnerSolutionInfo::set_LocalizedData(class Microsoft.Crm.Partner.PartnerSolutionLocalizedData value)
0x3d31  ldloc.0
0x3d32  ldloc.s  7
0x3d34  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Partner.PartnerSolutionInfo>::Add(var<u1>)
0x3d39  ldloca.s 4
0x3d3b  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x3d40  brtrue   loc_3C65
0x3d45  leave.s  loc_3D55
0x3d47  ldloca.s 4
0x3d49  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x3d4f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3d54  endfinally
0x3d55  ldloc.0
0x3d56  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Partner.PartnerSolutionInfo>::ToArray()
0x3d5b  ret
```
