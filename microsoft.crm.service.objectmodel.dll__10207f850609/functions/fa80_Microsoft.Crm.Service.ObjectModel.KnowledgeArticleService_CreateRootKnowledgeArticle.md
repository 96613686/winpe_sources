# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CreateRootKnowledgeArticle

- ea: `0xfa80`
- end: `0xfc3c`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CreateRootKnowledgeArticle`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xcf30`

## callees

- `0xfa80`
- `0xfdf0`

## pseudocode

```c

```

## disassembly

```asm
0xfa80  ldarg.1
0xfa81  ldstr    aEntity// "entity"
0xfa86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xfa8b  ldarg.2
0xfa8c  ldstr    aContext// "context"
0xfa91  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xfa96  ldnull
0xfa97  stloc.0
0xfa98  ldc.i4.0
0xfa99  stloc.1
0xfa9a  ldarg.1
0xfa9b  ldstr    aTitle// "title"
0xfaa0  ldarg.3
0xfaa1  ldstr    aTitle// "title"
0xfaa6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xfaab  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xfab0  ldarg.1
0xfab1  ldstr    aIsrootarticle// "isrootarticle"
0xfab6  ldc.i4.1
0xfab7  box      [mscorlib]System.Boolean
0xfabc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xfac1  ldarg.1
0xfac2  ldstr    aLanguagelocale// "languagelocaleid"
0xfac7  ldarg.3
0xfac8  ldstr    aLanguagelocale// "languagelocaleid"
0xfacd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xfad2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xfad7  ldarg.1
0xfad8  ldstr    aMajorversionnu// "majorversionnumber"
0xfadd  ldc.i4.0
0xfade  box      [mscorlib]System.Int32
0xfae3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xfae8  ldarg.3
0xfae9  ldstr    aArticlepublicn// "articlepublicnumber"
0xfaee  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xfaf3  brfalse.s loc_FB1B
0xfaf5  ldc.i4.1
0xfaf6  stloc.1
0xfaf7  ldarg.1
0xfaf8  ldstr    aArticlepublicn// "articlepublicnumber"
0xfafd  ldarg.3
0xfafe  ldstr    aArticlepublicn// "articlepublicnumber"
0xfb03  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xfb08  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xfb0d  ldarg.0
0xfb0e  ldarg.1
0xfb0f  ldarg.2
0xfb10  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xfb15  stloc.0
0xfb16  br       loc_FC20
0xfb1b  nop
0xfb1c  ldarg.0
0xfb1d  ldarg.1
0xfb1e  ldarg.2
0xfb1f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xfb24  stloc.0
0xfb25  leave    loc_FC0A
0xfb2a  stloc.2
0xfb2b  ldarg.2
0xfb2c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xfb31  ldc.i4.0
0xfb32  ldstr    a0// "{0}"
0xfb37  ldc.i4.1
0xfb38  newarr   [mscorlib]System.Object
0xfb3d  dup
0xfb3e  ldc.i4.0
0xfb3f  ldstr    aRootKnowledgeA// "Root Knowledge Article creation failed "...
0xfb44  ldarg.1
0xfb45  ldstr    aArticlepublicn// "articlepublicnumber"
0xfb4a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xfb4f  ldarg.1
0xfb50  ldstr    aLanguagelocale// "languagelocaleid"
0xfb55  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xfb5a  ldarg.1
0xfb5b  ldstr    aLanguagelocale_1// "languagelocaleidname"
0xfb60  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xfb65  call     string [mscorlib]System.String::Format(string, object, object, object)
0xfb6a  stelem.ref
0xfb6b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xfb70  ldarg.2
0xfb71  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xfb76  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticle::.ctor(valuetype [mscorlib]System.Guid)
0xfb7b  dup
0xfb7c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0xfb81  ldarg.2
0xfb82  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xfb87  stloc.3
0xfb88  ldloc.3
0xfb89  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0xfb8e  dup
0xfb8f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0xfb94  ldarg.2
0xfb95  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xfb9a  ldloc.3
0xfb9b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0xfba0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0xfba5  ldarg.2
0xfba6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xfbab  stloc.s  4
0xfbad  ldloc.s  4
0xfbaf  ldstr    aArticlepublicn// "articlepublicnumber"
0xfbb4  ldc.i4.0
0xfbb5  ldarg.1
0xfbb6  ldstr    aArticlepublicn// "articlepublicnumber"
0xfbbb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xfbc0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xfbc5  pop
0xfbc6  ldarg.0
0xfbc7  ldloc.s  4
0xfbc9  ldloc.3
0xfbca  ldarg.2
0xfbcb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xfbd0  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xfbd5  brtrue.s loc_FBFF
0xfbd7  ldloc.2
0xfbd8  ldarg.2
0xfbd9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xfbde  ldc.i4.0
0xfbdf  ldstr    aNoKnowledgeArt// "No Knowledge Articles existed with publ"...
0xfbe4  ldc.i4.1
0xfbe5  newarr   [mscorlib]System.Object
0xfbea  dup
0xfbeb  ldc.i4.0
0xfbec  ldarg.1
0xfbed  ldstr    aArticlepublicn// "articlepublicnumber"
0xfbf2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xfbf7  stelem.ref
0xfbf8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xfbfd  rethrow
0xfbff  ldarg.0
0xfc00  ldarg.1
0xfc01  ldarg.2
0xfc02  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xfc07  stloc.0
0xfc08  leave.s  loc_FC0A
0xfc0a  ldarg.3
0xfc0b  ldstr    aArticlepublicn// "articlepublicnumber"
0xfc10  ldarg.1
0xfc11  ldstr    aArticlepublicn// "articlepublicnumber"
0xfc16  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xfc1b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xfc20  ldloc.1
0xfc21  brfalse.s loc_FC3A
0xfc23  ldarg.0
0xfc24  ldarg.3
0xfc25  ldstr    aArticlepublicn// "articlepublicnumber"
0xfc2a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xfc2f  callvirt instance string [mscorlib]System.Object::ToString()
0xfc34  ldarg.2
0xfc35  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::UpdateCurrentKANumberInOrgSettings(string passedPublicNumber, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xfc3a  ldloc.0
0xfc3b  ret
```
