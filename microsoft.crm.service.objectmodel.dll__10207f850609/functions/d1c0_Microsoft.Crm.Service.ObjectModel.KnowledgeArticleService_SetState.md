# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SetState

- ea: `0xd1c0`
- end: `0xd3d8`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SetState`
- size: `536`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0xd1c0`
- `0xf3f0`
- `0xf5a0`
- `0xf630`
- `0xf730`
- `0xf8c0`
- `0xff10`

## string_xrefs

- `0xd1eb`: `readyforreview`
- `0xd2b2`: `readyforreview`
- `0xd330`: `readyforreview`
- `0xd1fb`: `updatecontent`
- `0xd2ba`: `updatecontent`
- `0xd338`: `updatecontent`
- `0xd214`: `publishstatusid`
- `0xd2da`: `publishstatusid`
- `0xd358`: `publishstatusid`
- `0xd226`: `expirationstatusid`
- `0xd2eb`: `expirationstatusid`
- `0xd368`: `expirationstatusid`

## pseudocode

```c

```

## disassembly

```asm
0xd1c0  ldc.i4.0
0xd1c1  stloc.0
0xd1c2  ldc.i4.s 0xC
0xd1c4  newarr   [mscorlib]System.String
0xd1c9  dup
0xd1ca  ldc.i4.0
0xd1cb  ldstr    aStatecode// "statecode"
0xd1d0  stelem.ref
0xd1d1  dup
0xd1d2  ldc.i4.1
0xd1d3  ldstr    aIsprimary// "isprimary"
0xd1d8  stelem.ref
0xd1d9  dup
0xd1da  ldc.i4.2
0xd1db  ldstr    aStatuscode// "statuscode"
0xd1e0  stelem.ref
0xd1e1  dup
0xd1e2  ldc.i4.3
0xd1e3  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xd1e8  stelem.ref
0xd1e9  dup
0xd1ea  ldc.i4.4
0xd1eb  ldstr    aReadyforreview// "readyforreview"
0xd1f0  stelem.ref
0xd1f1  dup
0xd1f2  ldc.i4.5
0xd1f3  ldstr    aReview// "review"
0xd1f8  stelem.ref
0xd1f9  dup
0xd1fa  ldc.i4.6
0xd1fb  ldstr    aUpdatecontent// "updatecontent"
0xd200  stelem.ref
0xd201  dup
0xd202  ldc.i4.7
0xd203  ldstr    aPublishon// "publishon"
0xd208  stelem.ref
0xd209  dup
0xd20a  ldc.i4.8
0xd20b  ldstr    aExpirationdate// "expirationdate"
0xd210  stelem.ref
0xd211  dup
0xd212  ldc.i4.s 9
0xd214  ldstr    aPublishstatusi// "publishstatusid"
0xd219  stelem.ref
0xd21a  dup
0xd21b  ldc.i4.s 0xA
0xd21d  ldstr    aExpirationstat// "expirationstateid"
0xd222  stelem.ref
0xd223  dup
0xd224  ldc.i4.s 0xB
0xd226  ldstr    aExpirationstat_0// "expirationstatusid"
0xd22b  stelem.ref
0xd22c  stloc.1
0xd22d  ldarg.0
0xd22e  ldarg.1
0xd22f  ldloc.1
0xd230  ldarg.s  4
0xd232  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::RetrieveKnowledgeArticle(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, string[] columnSet, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd237  stloc.2
0xd238  ldarg.0
0xd239  ldloc.2
0xd23a  ldarg.2
0xd23b  ldarg.s  4
0xd23d  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SetStatePrivilegeCheck(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, int32 newState, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd242  ldarg.0
0xd243  ldarg.1
0xd244  ldarg.2
0xd245  ldarg.3
0xd246  ldarg.s  4
0xd248  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetState(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, int32, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd24d  stloc.0
0xd24e  ldloc.0
0xd24f  brfalse  loc_D3D6
0xd254  ldarg.2
0xd255  ldc.i4.3
0xd256  bne.un.s loc_D270
0xd258  ldarg.0
0xd259  ldloc.2
0xd25a  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xd25f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd264  unbox.any [mscorlib]System.Guid
0xd269  ldarg.s  4
0xd26b  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SetRemainingPublishedVersionsToArchived(valuetype [mscorlib]System.Guid knowledgeArticleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd270  ldc.i4.0
0xd271  stloc.3
0xd272  ldloc.2
0xd273  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xd278  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd27d  unbox.any [mscorlib]System.Guid
0xd282  ldstr    aKnowledgeartic// "KnowledgeArticle"
0xd287  ldarg.s  4
0xd289  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd28e  stloc.s  4
0xd290  ldarg.0
0xd291  ldloc.s  4
0xd293  ldarg.0
0xd294  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0xd299  ldc.i4.s 0xA
0xd29b  newarr   [mscorlib]System.String
0xd2a0  dup
0xd2a1  ldc.i4.0
0xd2a2  ldstr    aIsrootarticle// "isrootarticle"
0xd2a7  stelem.ref
0xd2a8  dup
0xd2a9  ldc.i4.1
0xd2aa  ldstr    aIsprimary// "isprimary"
0xd2af  stelem.ref
0xd2b0  dup
0xd2b1  ldc.i4.2
0xd2b2  ldstr    aReadyforreview// "readyforreview"
0xd2b7  stelem.ref
0xd2b8  dup
0xd2b9  ldc.i4.3
0xd2ba  ldstr    aUpdatecontent// "updatecontent"
0xd2bf  stelem.ref
0xd2c0  dup
0xd2c1  ldc.i4.4
0xd2c2  ldstr    aReview// "review"
0xd2c7  stelem.ref
0xd2c8  dup
0xd2c9  ldc.i4.5
0xd2ca  ldstr    aPublishon// "publishon"
0xd2cf  stelem.ref
0xd2d0  dup
0xd2d1  ldc.i4.6
0xd2d2  ldstr    aExpirationdate// "expirationdate"
0xd2d7  stelem.ref
0xd2d8  dup
0xd2d9  ldc.i4.7
0xd2da  ldstr    aPublishstatusi// "publishstatusid"
0xd2df  stelem.ref
0xd2e0  dup
0xd2e1  ldc.i4.8
0xd2e2  ldstr    aExpirationstat// "expirationstateid"
0xd2e7  stelem.ref
0xd2e8  dup
0xd2e9  ldc.i4.s 9
0xd2eb  ldstr    aExpirationstat_0// "expirationstatusid"
0xd2f0  stelem.ref
0xd2f1  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xd2f6  ldarg.s  4
0xd2f8  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xd2fd  ldarg.s  4
0xd2ff  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd304  stloc.s  5
0xd306  ldarg.2
0xd307  switch   loc_D325, loc_D3C9, loc_D38C, loc_D38C, loc_D3B5
0xd320  br       loc_D3C9
0xd325  ldarg.0
0xd326  ldloc.s  5
0xd328  ldc.i4.8
0xd329  newarr   [mscorlib]System.String
0xd32e  dup
0xd32f  ldc.i4.0
0xd330  ldstr    aReadyforreview// "readyforreview"
0xd335  stelem.ref
0xd336  dup
0xd337  ldc.i4.1
0xd338  ldstr    aUpdatecontent// "updatecontent"
0xd33d  stelem.ref
0xd33e  dup
0xd33f  ldc.i4.2
0xd340  ldstr    aReview// "review"
0xd345  stelem.ref
0xd346  dup
0xd347  ldc.i4.3
0xd348  ldstr    aPublishon// "publishon"
0xd34d  stelem.ref
0xd34e  dup
0xd34f  ldc.i4.4
0xd350  ldstr    aExpirationdate// "expirationdate"
0xd355  stelem.ref
0xd356  dup
0xd357  ldc.i4.5
0xd358  ldstr    aPublishstatusi// "publishstatusid"
0xd35d  stelem.ref
0xd35e  dup
0xd35f  ldc.i4.6
0xd360  ldstr    aExpirationstat// "expirationstateid"
0xd365  stelem.ref
0xd366  dup
0xd367  ldc.i4.7
0xd368  ldstr    aExpirationstat_0// "expirationstatusid"
0xd36d  stelem.ref
0xd36e  ldarg.s  4
0xd370  call     instance bool Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::ResetAttributesToDefault(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity businessEntity, string[] columnSet, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd375  stloc.3
0xd376  ldarg.0
0xd377  ldloc.s  5
0xd379  ldstr    aAb81c1af1a4548// "AB81C1AF-1A45-48D9-8133-3EDC033DBEEF"
0xd37e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xd383  ldarg.s  4
0xd385  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::ValidatePrimaryArticleAndSwitchProcess(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, valuetype [mscorlib]System.Guid processGuid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd38a  br.s     loc_D3C9
0xd38c  ldarg.s  4
0xd38e  ldloc.2
0xd38f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0xd394  ldstr    aPublishon// "publishon"
0xd399  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xd39e  ldloc.2
0xd39f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0xd3a4  ldstr    aExpirationdate// "expirationdate"
0xd3a9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xd3ae  call     void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleHelper::RescheduleKnowledgeArticleAsyncJob(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo publishOn, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo expirationDate)
0xd3b3  br.s     loc_D3C9
0xd3b5  ldarg.0
0xd3b6  ldloc.s  5
0xd3b8  ldstr    aBcd4379356864f// "BCD43793-5686-4FD4-B3B4-C0C26D6F7E40"
0xd3bd  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xd3c2  ldarg.s  4
0xd3c4  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::ValidatePrimaryArticleAndSwitchProcess(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, valuetype [mscorlib]System.Guid processGuid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd3c9  ldloc.3
0xd3ca  brfalse.s loc_D3D6
0xd3cc  ldarg.0
0xd3cd  ldloc.s  5
0xd3cf  ldarg.s  4
0xd3d1  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd3d6  ldloc.0
0xd3d7  ret
```
