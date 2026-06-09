# Microsoft.Crm.Common.Application.Utility.ActivityRegardingMap::ProcessParameters

- ea: `0xc70`
- end: `0xe4f`
- name: `Microsoft.Crm.Common.Application.Utility.ActivityRegardingMap::ProcessParameters`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xc70`
- `0xe50`
- `0x1c40`

## string_xrefs

- `0xcd5`: `_CreateFromId`
- `0xcef`: `_CreateFromId`
- `0xd07`: `_CreateFromId`
- `0xce2`: `_CreateFromType`
- `0xcfb`: `_CreateFromType`
- `0xd13`: `_CreateFromType`

## pseudocode

```c

```

## disassembly

```asm
0xc70  ldarg.0
0xc71  ldarg.1
0xc72  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::set_TargetEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0xc77  ldnull
0xc78  stloc.0
0xc79  ldnull
0xc7a  stloc.1
0xc7b  ldnull
0xc7c  stloc.2
0xc7d  ldarg.2
0xc7e  ldstr    aPid// "pId"
0xc83  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0xc88  brfalse.s loc_CD4
0xc8a  ldarg.3
0xc8b  ldstr    aPid// "pId"
0xc90  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc95  stloc.0
0xc96  ldarg.3
0xc97  ldstr    aPtype// "pType"
0xc9c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xca1  stloc.1
0xca2  ldarg.3
0xca3  ldstr    aPname// "pName"
0xca8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xcad  stloc.2
0xcae  ldarg.2
0xcaf  ldstr    aPid// "pId"
0xcb4  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Remove(var<u1>)
0xcb9  pop
0xcba  ldarg.2
0xcbb  ldstr    aPtype// "pType"
0xcc0  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Remove(var<u1>)
0xcc5  pop
0xcc6  ldarg.2
0xcc7  ldstr    aPname// "pName"
0xccc  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Remove(var<u1>)
0xcd1  pop
0xcd2  br.s     loc_D1E
0xcd4  ldarg.2
0xcd5  ldstr    aCreatefromid// "_CreateFromId"
0xcda  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0xcdf  brfalse.s loc_D1E
0xce1  ldarg.2
0xce2  ldstr    aCreatefromtype// "_CreateFromType"
0xce7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0xcec  brfalse.s loc_D1E
0xcee  ldarg.3
0xcef  ldstr    aCreatefromid// "_CreateFromId"
0xcf4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xcf9  stloc.0
0xcfa  ldarg.3
0xcfb  ldstr    aCreatefromtype// "_CreateFromType"
0xd00  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd05  stloc.1
0xd06  ldarg.2
0xd07  ldstr    aCreatefromid// "_CreateFromId"
0xd0c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Remove(var<u1>)
0xd11  pop
0xd12  ldarg.2
0xd13  ldstr    aCreatefromtype// "_CreateFromType"
0xd18  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Remove(var<u1>)
0xd1d  pop
0xd1e  ldloc.0
0xd1f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd24  brtrue   loc_E4E
0xd29  ldloc.0
0xd2a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd2f  stloc.3
0xd30  ldloca.s 3
0xd32  constrained. [mscorlib]System.Guid
0xd38  callvirt instance string [mscorlib]System.Object::ToString()
0xd3d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xd42  brfalse  loc_E4E
0xd47  ldloc.1
0xd48  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd4d  ldc.i4.0
0xd4e  ceq
0xd50  ldstr    aActivityEntity_1// "Activity entity mapping invoked with a "...
0xd55  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0xd5a  ldloc.1
0xd5b  ldarg.0
0xd5c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntityType()
0xd61  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0xd66  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd6b  stloc.s  4
0xd6d  ldloc.2
0xd6e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd73  brfalse.s loc_D90
0xd75  ldloc.s  4
0xd77  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xd7c  dup
0xd7d  ldloc.0
0xd7e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0xd83  dup
0xd84  ldc.i4.0
0xd85  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_IsNew(bool)
0xd8a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_DisplayName()
0xd8f  stloc.2
0xd90  ldloc.2
0xd91  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd96  ldc.i4.0
0xd97  ceq
0xd99  ldstr    aActivityEntity_2// "Activity entity mapping invoked with a "...
0xd9e  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0xda3  ldarg.0
0xda4  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::CreateTargetEntityIfNecessary()
0xda9  ldloc.s  4
0xdab  ldarg.0
0xdac  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntity()
0xdb1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0xdb6  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0xdbb  ldstr    aRegardingobjec// "regardingobjectid"
0xdc0  call     bool Microsoft.Crm.Common.Application.Utility.ActivityRegardingMap::RegardingParentalRelationshipExists(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType fromEntityType, int32 toTypeCode, string toAttributeName)
0xdc5  brfalse  loc_E4E
0xdca  ldarg.0
0xdcb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntity()
0xdd0  ldstr    aRegardingobjec// "regardingobjectid"
0xdd5  ldloc.0
0xdd6  ldloc.s  4
0xdd8  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0xddd  ldloc.2
0xdde  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::.ctor(string, int32, string)
0xde3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xde8  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0xded  brfalse.s loc_E4E
0xdef  ldloc.1
0xdf0  ldloca.s 5
0xdf2  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0xdf7  brfalse.s loc_E4E
0xdf9  ldarg.3
0xdfa  ldstr    aContentid// "contentId"
0xdff  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xe04  stloc.s  6
0xe06  ldloc.s  6
0xe08  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe0d  brtrue.s loc_E4E
0xe0f  ldloc.s  5
0xe11  ldc.i4.s 0x70
0xe13  bne.un.s loc_E4E
0xe15  ldarg.2
0xe16  ldstr    aContentid// "contentId"
0xe1b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Remove(var<u1>)
0xe20  pop
0xe21  ldloc.s  6
0xe23  ldloca.s 7
0xe25  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0xe2a  brfalse.s loc_E4E
0xe2c  ldarg.0
0xe2d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntity()
0xe32  ldstr    aDescription// "description"
0xe37  ldloc.s  7
0xe39  ldarg.0
0xe3a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntityType()
0xe3f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0xe44  call     string Microsoft.Crm.Common.Application.Commands.ApplicationCommand::RetrieveKBArticleContent(valuetype [mscorlib]System.Guid articleId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xe49  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xe4e  ret
```
