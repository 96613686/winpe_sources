# Microsoft.Crm.Application.WebServices.SystemCustomization.HierarchySecurityConfiguration::SaveHierarchySecurityModelingEntityConfiguration

- ea: `0x4420`
- end: `0x46b4`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.HierarchySecurityConfiguration::SaveHierarchySecurityModelingEntityConfiguration`
- size: `660`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4420`

## string_xrefs

- `0x444f`: `ishierarchicalsecuritymodelenabled`
- `0x447a`: `maxdepthforhierarchicalsecuritymodel`
- `0x44bb`: `hierarchysecurityconfiguration`
- `0x4575`: `hierarchysecurityconfiguration`
- `0x45f9`: `hierarchysecurityconfiguration`
- `0x4663`: `hierarchysecurityconfiguration`
- `0x44e5`: `hierarchysecuritymodelingsettingid`

## pseudocode

```c

```

## disassembly

```asm
0x4420  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteHierarchicalSecurityConfiguration()
0x4425  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x442a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x442f  brfalse  loc_4695
0x4434  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4439  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::GetSettings(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x443e  ldstr    aOrganization// "organization"
0x4443  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4448  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x444d  stloc.0
0x444e  ldloc.0
0x444f  ldstr    aIshierarchical// "ishierarchicalsecuritymodelenabled"
0x4454  ldarg.2
0x4455  box      [mscorlib]System.Boolean
0x445a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x445f  ldloc.0
0x4460  ldstr    aUsepositionhie// "usepositionhierarchy"
0x4465  ldarg.3
0x4466  box      [mscorlib]System.Boolean
0x446b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4470  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_MaxDepthForHierarchicalSecurity()
0x4475  ldarg.s  4
0x4477  beq.s    loc_448B
0x4479  ldloc.0
0x447a  ldstr    aMaxdepthforhie// "maxdepthforhierarchicalsecuritymodel"
0x447f  ldarg.s  4
0x4481  box      [mscorlib]System.Int32
0x4486  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x448b  ldloc.0
0x448c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4491  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x4496  stloc.3
0x4497  ldloca.s 3
0x4499  constrained. [mscorlib]System.Guid
0x449f  callvirt instance string [mscorlib]System.Object::ToString()
0x44a4  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x44a9  ldloc.0
0x44aa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x44af  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x44b4  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0x44b9  stloc.1
0x44ba  ldloc.1
0x44bb  ldstr    aHierarchysecur// "hierarchysecurityconfiguration"
0x44c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x44c5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x44ca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x44cf  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0x44d4  ldloc.1
0x44d5  ldc.i4.2
0x44d6  newarr   [mscorlib]System.String
0x44db  dup
0x44dc  ldc.i4.0
0x44dd  ldstr    aEntityname// "entityname"
0x44e2  stelem.ref
0x44e3  dup
0x44e4  ldc.i4.1
0x44e5  ldstr    aHierarchysecur_0// "hierarchysecuritymodelingsettingid"
0x44ea  stelem.ref
0x44eb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x44f0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x44f5  ldloc.1
0x44f6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x44fb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4500  stloc.2
0x4501  ldarg.1
0x4502  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4507  brtrue   loc_4650
0x450c  ldarg.1
0x450d  ldc.i4.1
0x450e  newarr   [mscorlib]System.Char
0x4513  dup
0x4514  ldc.i4.0
0x4515  ldc.i4.s 0x2C
0x4517  stelem.i2
0x4518  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x451d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x4522  stloc.s  4
0x4524  stloc.s  5
0x4526  ldc.i4.0
0x4527  stloc.s  6
0x4529  br.s     loc_4541
0x452b  ldloc.s  5
0x452d  ldloc.s  6
0x452f  ldelem.ref
0x4530  stloc.s  7
0x4532  ldloc.s  4
0x4534  ldloc.s  7
0x4536  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x453b  ldloc.s  6
0x453d  ldc.i4.1
0x453e  add
0x453f  stloc.s  6
0x4541  ldloc.s  6
0x4543  ldloc.s  5
0x4545  ldlen
0x4546  conv.i4
0x4547  blt.s    loc_452B
0x4549  ldloc.2
0x454a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x454f  stloc.s  8
0x4551  br.s     loc_45AB
0x4553  ldloc.s  8
0x4555  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x455a  stloc.s  9
0x455c  ldarg.1
0x455d  ldloc.s  9
0x455f  ldstr    aEntityname// "entityname"
0x4564  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4569  callvirt instance string [mscorlib]System.Object::ToString()
0x456e  callvirt instance bool [mscorlib]System.String::Contains(string)
0x4573  brtrue.s loc_4592
0x4575  ldstr    aHierarchysecur// "hierarchysecurityconfiguration"
0x457a  ldloc.s  9
0x457c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x4581  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4586  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x458b  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Delete(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4590  br.s     loc_45AB
0x4592  ldloc.s  4
0x4594  ldloc.s  9
0x4596  ldstr    aEntityname// "entityname"
0x459b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x45a0  callvirt instance string [mscorlib]System.Object::ToString()
0x45a5  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Remove(var<u1>)
0x45aa  pop
0x45ab  ldloc.s  8
0x45ad  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x45b2  brtrue.s loc_4553
0x45b4  leave.s  loc_45C2
0x45b6  ldloc.s  8
0x45b8  brfalse.s loc_45C1
0x45ba  ldloc.s  8
0x45bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45c1  endfinally
0x45c2  ldloc.s  4
0x45c4  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x45c9  stloc.s  0xA
0x45cb  br.s     loc_4637
0x45cd  ldloca.s 0xA
0x45cf  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x45d4  stloc.s  0xB
0x45d6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x45db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x45e0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x45e5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x45ea  ldloc.s  0xB
0x45ec  ldc.i4.1
0x45ed  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x45f2  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x45f7  stloc.s  0xC
0x45f9  ldstr    aHierarchysecur// "hierarchysecurityconfiguration"
0x45fe  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4603  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4608  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x460d  dup
0x460e  ldstr    aEntityname// "entityname"
0x4613  ldloc.s  0xB
0x4615  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x461a  dup
0x461b  ldstr    aObjecttypecode// "objecttypecode"
0x4620  ldloc.s  0xC
0x4622  box      [mscorlib]System.Int32
0x4627  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x462c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4631  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Create(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4636  pop
0x4637  ldloca.s 0xA
0x4639  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x463e  brtrue.s loc_45CD
0x4640  leave.s  loc_46A6
0x4642  ldloca.s 0xA
0x4644  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x464a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x464f  endfinally
0x4650  ldloc.2
0x4651  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x4656  stloc.s  8
0x4658  br.s     loc_467E
0x465a  ldloc.s  8
0x465c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x4661  stloc.s  0xD
0x4663  ldstr    aHierarchysecur// "hierarchysecurityconfiguration"
0x4668  ldloc.s  0xD
0x466a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x466f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4674  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4679  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Delete(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x467e  ldloc.s  8
0x4680  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4685  brtrue.s loc_465A
0x4687  leave.s  loc_46A6
0x4689  ldloc.s  8
0x468b  brfalse.s loc_4694
0x468d  ldloc.s  8
0x468f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4694  endfinally
0x4695  ldc.i4   0x80040277
0x469a  ldc.i4.0
0x469b  newarr   [mscorlib]System.Object
0x46a0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x46a5  throw
0x46a6  leave.s  loc_46B3
0x46a8  stloc.s  0xE
0x46aa  ldarg.0
0x46ab  ldloc.s  0xE
0x46ad  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x46b2  throw
0x46b3  ret
```
