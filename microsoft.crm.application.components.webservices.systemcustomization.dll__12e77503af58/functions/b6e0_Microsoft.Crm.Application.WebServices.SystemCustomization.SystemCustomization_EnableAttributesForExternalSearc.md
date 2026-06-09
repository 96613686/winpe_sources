# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::EnableAttributesForExternalSearchFaceting

- ea: `0xb6e0`
- end: `0xb7bb`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::EnableAttributesForExternalSearchFaceting`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xb6e0`
- `0xbf10`
- `0xbf30`

## pseudocode

```c

```

## disassembly

```asm
0xb6e0  ldarg.1
0xb6e1  call     T0x2B000003
0xb6e6  stloc.0
0xb6e7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityAttributeCollection::.ctor()
0xb6ec  stloc.1
0xb6ed  ldloc.0
0xb6ee  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.WebServices.SystemCustomization.RelevanceSearchFacetList>::GetEnumerator()
0xb6f3  stloc.3
0xb6f4  br.s     loc_B741
0xb6f6  ldloca.s 3
0xb6f8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Application.WebServices.SystemCustomization.RelevanceSearchFacetList>::get_Current()
0xb6fd  stloc.s  4
0xb6ff  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0xb704  stloc.s  5
0xb706  ldloc.s  4
0xb708  callvirt instance string Microsoft.Crm.Application.WebServices.SystemCustomization.RelevanceSearchFacetList::get_attributeNames()
0xb70d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb712  brtrue.s loc_B741
0xb714  ldloc.s  5
0xb716  ldloc.s  4
0xb718  callvirt instance string Microsoft.Crm.Application.WebServices.SystemCustomization.RelevanceSearchFacetList::get_attributeNames()
0xb71d  ldc.i4.1
0xb71e  newarr   [mscorlib]System.Char
0xb723  dup
0xb724  ldc.i4.0
0xb725  ldc.i4.s 0x2C
0xb727  stelem.i2
0xb728  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xb72d  callvirt instance void [System]System.Collections.Specialized.StringCollection::AddRange(string[])
0xb732  ldloc.1
0xb733  ldloc.s  4
0xb735  callvirt instance string Microsoft.Crm.Application.WebServices.SystemCustomization.RelevanceSearchFacetList::get_entityName()
0xb73a  ldloc.s  5
0xb73c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [System]System.Collections.Specialized.StringCollection>::Add(var<u1>, !!T0)
0xb741  ldloca.s 3
0xb743  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Application.WebServices.SystemCustomization.RelevanceSearchFacetList>::MoveNext()
0xb748  brtrue.s loc_B6F6
0xb74a  leave.s  loc_B75A
0xb74c  ldloca.s 3
0xb74e  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Application.WebServices.SystemCustomization.RelevanceSearchFacetList>
0xb754  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb759  endfinally
0xb75a  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.UserSearchFacetService::.ctor()
0xb75f  stloc.2
0xb760  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb765  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xb76a  ldc.i4.0
0xb76b  ldc.i4.0
0xb76c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xb771  stloc.s  6
0xb773  ldloc.s  6
0xb775  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb77a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0xb77f  ldc.i4.0
0xb780  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0xb785  ldloc.2
0xb786  ldloc.s  6
0xb788  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb78d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0xb792  ldloc.1
0xb793  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.UserSearchFacetService::SetUserSearchFacets(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityAttributeCollection)
0xb798  ldloc.s  6
0xb79a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0xb79f  leave.s  loc_B7AD
0xb7a1  ldloc.s  6
0xb7a3  brfalse.s loc_B7AC
0xb7a5  ldloc.s  6
0xb7a7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb7ac  endfinally
0xb7ad  leave.s  loc_B7BA
0xb7af  stloc.s  7
0xb7b1  ldarg.0
0xb7b2  ldloc.s  7
0xb7b4  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xb7b9  throw
0xb7ba  ret
```
