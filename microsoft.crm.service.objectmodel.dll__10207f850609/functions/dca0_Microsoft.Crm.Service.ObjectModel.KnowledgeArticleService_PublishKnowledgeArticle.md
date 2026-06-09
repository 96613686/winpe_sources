# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::PublishKnowledgeArticle

- ea: `0xdca0`
- end: `0xdfd9`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::PublishKnowledgeArticle`
- size: `825`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0xdca0`
- `0xeba0`
- `0xedc0`
- `0xef10`
- `0xf7b0`

## string_xrefs

- `0xddc4`: `publishstatusid`
- `0xddca`: `publishstatusid`
- `0xde16`: `expirationstatusid`
- `0xde1c`: `expirationstatusid`
- `0xde4b`: `PublishKnowledgeArticleSDK Successfully Moved Approved Translation KnowledgeArticleId={0} to State={1} Status={1}`
- `0xdf20`: `PublishKnowledgeArticleSDK Unable to copy Related Product Information for KnowledgeArticleId={0} as  ParentKnowledgeArticleId is not available `
- `0xdf6c`: `Copying Related Category Information for KnowledgeArticleId={0} ParentKnowledgeArticleId={1} `
- `0xdfae`: `Copying Related Product Information for KnowledgeArticleId={0} ParentKnowledgeArticleId={1} `

## pseudocode

```c

```

## disassembly

```asm
0xdca0  ldarg.s  5
0xdca2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0xdca7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0xdcac  ldarg.1
0xdcad  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xdcb2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xdcb7  unbox.any [mscorlib]System.Guid
0xdcbc  stloc.0
0xdcbd  ldarg.s  5
0xdcbf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xdcc4  ldc.i4.s 0x1A
0xdcc6  ldstr    a0// "{0}"
0xdccb  ldc.i4.1
0xdccc  newarr   [mscorlib]System.Object
0xdcd1  dup
0xdcd2  ldc.i4.0
0xdcd3  ldstr    aPublishingKnow// "Publishing KnowledgeArticle={0}"
0xdcd8  ldloc.0
0xdcd9  box      [mscorlib]System.Guid
0xdcde  call     string [mscorlib]System.String::Format(string, object)
0xdce3  stelem.ref
0xdce4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xdce9  ldarg.0
0xdcea  ldarg.1
0xdceb  ldarg.s  5
0xdced  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xdcf2  ldarg.0
0xdcf3  ldloc.0
0xdcf4  ldarg.s  5
0xdcf6  ldc.i4.2
0xdcf7  newarr   [mscorlib]System.String
0xdcfc  dup
0xdcfd  ldc.i4.0
0xdcfe  ldstr    aIsprimary// "isprimary"
0xdd03  stelem.ref
0xdd04  dup
0xdd05  ldc.i4.1
0xdd06  ldstr    aParentarticlec// "parentarticlecontentid"
0xdd0b  stelem.ref
0xdd0c  call     instance class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticle Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::RetrieveKnowledgeArticleById(valuetype [mscorlib]System.Guid knowledgeArticleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string[] columns)
0xdd11  stloc.1
0xdd12  ldloc.1
0xdd13  brfalse  loc_DFCB
0xdd18  ldloc.1
0xdd19  ldstr    aIsprimary// "isprimary"
0xdd1e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xdd23  unbox.any [mscorlib]System.Boolean
0xdd28  stloc.2
0xdd29  ldloc.2
0xdd2a  ldarg.s  4
0xdd2c  and
0xdd2d  brfalse  loc_DEAC
0xdd32  ldarg.0
0xdd33  ldloc.0
0xdd34  ldarg.s  5
0xdd36  call     instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::RetreiveTranslationsWithOneApprovedVersion(valuetype [mscorlib]System.Guid knowledgeArticleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xdd3b  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0xdd40  stloc.3
0xdd41  br       loc_DE8D
0xdd46  ldloca.s 3
0xdd48  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0xdd4d  stloc.s  4
0xdd4f  ldarg.s  5
0xdd51  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xdd56  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticle::.ctor(valuetype [mscorlib]System.Guid)
0xdd5b  stloc.s  5
0xdd5d  ldloc.s  5
0xdd5f  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xdd64  ldloc.s  4
0xdd66  box      [mscorlib]System.Guid
0xdd6b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0xdd70  ldloc.s  5
0xdd72  ldstr    aStatecode// "statecode"
0xdd77  ldarg.1
0xdd78  ldstr    aStatecode// "statecode"
0xdd7d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xdd82  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0xdd87  ldloc.s  5
0xdd89  ldstr    aStatuscode// "statuscode"
0xdd8e  ldarg.1
0xdd8f  ldstr    aStatuscode// "statuscode"
0xdd94  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xdd99  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0xdd9e  ldarg.1
0xdd9f  ldstr    aPublishon// "publishon"
0xdda4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xdda9  brtrue.s loc_DDD9
0xddab  ldloc.s  5
0xddad  ldstr    aPublishon// "publishon"
0xddb2  ldarg.1
0xddb3  ldstr    aPublishon// "publishon"
0xddb8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xddbd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0xddc2  ldloc.s  5
0xddc4  ldstr    aPublishstatusi// "publishstatusid"
0xddc9  ldarg.1
0xddca  ldstr    aPublishstatusi// "publishstatusid"
0xddcf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xddd4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0xddd9  ldarg.1
0xddda  ldstr    aExpirationdate// "expirationdate"
0xdddf  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xdde4  brtrue.s loc_DE2B
0xdde6  ldloc.s  5
0xdde8  ldstr    aExpirationdate// "expirationdate"
0xdded  ldarg.1
0xddee  ldstr    aExpirationdate// "expirationdate"
0xddf3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xddf8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0xddfd  ldloc.s  5
0xddff  ldstr    aExpirationstat// "expirationstateid"
0xde04  ldarg.1
0xde05  ldstr    aExpirationstat// "expirationstateid"
0xde0a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xde0f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0xde14  ldloc.s  5
0xde16  ldstr    aExpirationstat_0// "expirationstatusid"
0xde1b  ldarg.1
0xde1c  ldstr    aExpirationstat_0// "expirationstatusid"
0xde21  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xde26  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0xde2b  ldarg.0
0xde2c  ldloc.s  5
0xde2e  ldarg.s  5
0xde30  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xde35  ldarg.s  5
0xde37  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xde3c  ldc.i4.s 0x1A
0xde3e  ldstr    a0// "{0}"
0xde43  ldc.i4.1
0xde44  newarr   [mscorlib]System.Object
0xde49  dup
0xde4a  ldc.i4.0
0xde4b  ldstr    aPublishknowled// "PublishKnowledgeArticleSDK Successfully"...
0xde50  ldloc.0
0xde51  box      [mscorlib]System.Guid
0xde56  ldloc.s  5
0xde58  ldstr    aStatecode// "statecode"
0xde5d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xde62  unbox.any [mscorlib]System.Int32
0xde67  box      [mscorlib]System.Int32
0xde6c  ldloc.s  5
0xde6e  ldstr    aStatuscode// "statuscode"
0xde73  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xde78  unbox.any [mscorlib]System.Int32
0xde7d  box      [mscorlib]System.Int32
0xde82  call     string [mscorlib]System.String::Format(string, object, object, object)
0xde87  stelem.ref
0xde88  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xde8d  ldloca.s 3
0xde8f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0xde94  brtrue   loc_DD46
0xde99  leave    loc_DFCB
0xde9e  ldloca.s 3
0xdea0  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0xdea6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdeab  endfinally
0xdeac  ldloc.2
0xdead  brtrue   loc_DFCB
0xdeb2  ldarg.2
0xdeb3  ldarg.3
0xdeb4  or
0xdeb5  brfalse  loc_DFCB
0xdeba  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xdebf  stloc.s  6
0xdec1  ldarg.1
0xdec2  ldstr    aParentarticlec// "parentarticlecontentid"
0xdec7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xdecc  brtrue.s loc_DEE2
0xdece  ldarg.1
0xdecf  ldstr    aParentarticlec// "parentarticlecontentid"
0xded4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xded9  unbox.any [mscorlib]System.Guid
0xdede  stloc.s  6
0xdee0  br.s     loc_DF36
0xdee2  ldloc.1
0xdee3  ldstr    aParentarticlec// "parentarticlecontentid"
0xdee8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0xdeed  brtrue.s loc_DF03
0xdeef  ldloc.1
0xdef0  ldstr    aParentarticlec// "parentarticlecontentid"
0xdef5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xdefa  unbox.any [mscorlib]System.Guid
0xdeff  stloc.s  6
0xdf01  br.s     loc_DF36
0xdf03  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xdf08  stloc.s  6
0xdf0a  ldarg.s  5
0xdf0c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xdf11  ldc.i4.s 0x1A
0xdf13  ldstr    a0// "{0}"
0xdf18  ldc.i4.1
0xdf19  newarr   [mscorlib]System.Object
0xdf1e  dup
0xdf1f  ldc.i4.0
0xdf20  ldstr    aPublishknowled_0// "PublishKnowledgeArticleSDK Unable to co"...
0xdf25  ldloc.0
0xdf26  box      [mscorlib]System.Guid
0xdf2b  call     string [mscorlib]System.String::Format(string, object)
0xdf30  stelem.ref
0xdf31  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xdf36  ldloc.s  6
0xdf38  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xdf3d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xdf42  brfalse  loc_DFCB
0xdf47  ldarg.3
0xdf48  brfalse.s loc_DF89
0xdf4a  ldarg.0
0xdf4b  ldloc.s  6
0xdf4d  ldloc.0
0xdf4e  ldc.i4.1
0xdf4f  ldarg.s  5
0xdf51  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CopyRelatedCategoriesFromSourceToTargetKnowledgeArticle(valuetype [mscorlib]System.Guid sourceKnowledgeArticleId, valuetype [mscorlib]System.Guid targetKnowledgeArticleId, bool clearExistingCategoriesBeforeCopy, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xdf56  ldarg.s  5
0xdf58  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xdf5d  ldc.i4.s 0x1A
0xdf5f  ldstr    a0// "{0}"
0xdf64  ldc.i4.1
0xdf65  newarr   [mscorlib]System.Object
0xdf6a  dup
0xdf6b  ldc.i4.0
0xdf6c  ldstr    aCopyingRelated// "Copying Related Category Information fo"...
0xdf71  ldloc.0
0xdf72  box      [mscorlib]System.Guid
0xdf77  ldloc.s  6
0xdf79  box      [mscorlib]System.Guid
0xdf7e  call     string [mscorlib]System.String::Format(string, object, object)
0xdf83  stelem.ref
0xdf84  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xdf89  ldarg.2
0xdf8a  brfalse.s loc_DFCB
0xdf8c  ldarg.0
0xdf8d  ldloc.s  6
0xdf8f  ldloc.0
0xdf90  ldc.i4.1
0xdf91  ldarg.s  5
0xdf93  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CopyRelatedProductsFromSourceToTargetKnowledgeArticle(valuetype [mscorlib]System.Guid sourceKnowledgeArticleId, valuetype [mscorlib]System.Guid targetKnowledgeArticleId, bool clearExistingProductsBeforeCopy, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xdf98  ldarg.s  5
0xdf9a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xdf9f  ldc.i4.s 0x1A
0xdfa1  ldstr    a0// "{0}"
0xdfa6  ldc.i4.1
0xdfa7  newarr   [mscorlib]System.Object
0xdfac  dup
0xdfad  ldc.i4.0
0xdfae  ldstr    aCopyingRelated_0// "Copying Related Product Information for"...
0xdfb3  ldloc.0
0xdfb4  box      [mscorlib]System.Guid
0xdfb9  ldloc.s  6
0xdfbb  box      [mscorlib]System.Guid
0xdfc0  call     string [mscorlib]System.String::Format(string, object, object)
0xdfc5  stelem.ref
0xdfc6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xdfcb  ldarg.s  5
0xdfcd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0xdfd2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0xdfd7  ldc.i4.1
0xdfd8  ret
```
