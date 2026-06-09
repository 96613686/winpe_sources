# Microsoft.Crm.BusinessEntities.NotificationsExtension::FireNotificationsForEntity

- ea: `0x6b900`
- end: `0x6c2ea`
- name: `Microsoft.Crm.BusinessEntities.NotificationsExtension::FireNotificationsForEntity`
- size: `2538`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x6b770`
- `0x6b790`
- `0x6b7b0`

## callees

- `0x66ae0`
- `0x66c80`
- `0x670c0`
- `0x6b900`
- `0x6c2f0`
- `0x6c340`
- `0x85d00`

## string_xrefs

- `0x6bc23`: `PluginAssembly`
- `0x6bc0e`: `PluginType`
- `0x6bccb`: `GlobalSearchConfiguration`
- `0x6bbf9`: `ComplexControl`
- `0x6beb4`: `azureactivedirectoryobjectid`
- `0x6bbba`: `SdkMessageProcessingStepSecureConfig`
- `0x6bc77`: `HierarchySecurityConfiguration`
- `0x6c225`: `globalsearchconfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x6b900  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x6b905  brtrue   loc_6C2E9
0x6b90a  ldc.i4.0
0x6b90b  stloc.0
0x6b90c  ldarg.1
0x6b90d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x6b912  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x6b917  stloc.1
0x6b918  ldloc.1
0x6b919  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x6b91e  stloc.2
0x6b91f  ldloc.2
0x6b920  ldc.i4   0x61F7D251
0x6b925  bgt.un   loc_6BA0A
0x6b92a  ldloc.2
0x6b92b  ldc.i4   0x1563FA76
0x6b930  bgt.un.s loc_6B99E
0x6b932  ldloc.2
0x6b933  ldc.i4   0x10EA0C9A
0x6b938  bgt.un.s loc_6B960
0x6b93a  ldloc.2
0x6b93b  ldc.i4   0xAE7B79E
0x6b940  beq      loc_6BB7A
0x6b945  ldloc.2
0x6b946  ldc.i4   0x10661D21
0x6b94b  beq      loc_6BAFC
0x6b950  ldloc.2
0x6b951  ldc.i4   0x10EA0C9A
0x6b956  beq      loc_6BBE3
0x6b95b  br       loc_6C2D8
0x6b960  ldloc.2
0x6b961  ldc.i4   0x12BE27D0
0x6b966  bgt.un.s loc_6B983
0x6b968  ldloc.2
0x6b969  ldc.i4   0x112AFCEC
0x6b96e  beq      loc_6BBB9
0x6b973  ldloc.2
0x6b974  ldc.i4   0x12BE27D0
0x6b979  beq      loc_6BB65
0x6b97e  br       loc_6C2D8
0x6b983  ldloc.2
0x6b984  ldc.i4   0x12D21220
0x6b989  beq      loc_6BB8F
0x6b98e  ldloc.2
0x6b98f  ldc.i4   0x1563FA76
0x6b994  beq      loc_6BC8B
0x6b999  br       loc_6C2D8
0x6b99e  ldloc.2
0x6b99f  ldc.i4   0x1E717A3A
0x6b9a4  bgt.un.s loc_6B9CC
0x6b9a6  ldloc.2
0x6b9a7  ldc.i4   0x1971E30A
0x6b9ac  beq      loc_6BB3B
0x6b9b1  ldloc.2
0x6b9b2  ldc.i4   0x1C5BF4D4
0x6b9b7  beq      loc_6BD09
0x6b9bc  ldloc.2
0x6b9bd  ldc.i4   0x1E717A3A
0x6b9c2  beq      loc_6BD1E
0x6b9c7  br       loc_6C2D8
0x6b9cc  ldloc.2
0x6b9cd  ldc.i4   0x3E732F14
0x6b9d2  bgt.un.s loc_6B9EF
0x6b9d4  ldloc.2
0x6b9d5  ldc.i4   0x3B47A31F
0x6b9da  beq      loc_6BB50
0x6b9df  ldloc.2
0x6b9e0  ldc.i4   0x3E732F14
0x6b9e5  beq      loc_6BCCA
0x6b9ea  br       loc_6C2D8
0x6b9ef  ldloc.2
0x6b9f0  ldc.i4   0x59CA5C18
0x6b9f5  beq      loc_6BCB5
0x6b9fa  ldloc.2
0x6b9fb  ldc.i4   0x61F7D251
0x6ba00  beq      loc_6BC37
0x6ba05  br       loc_6C2D8
0x6ba0a  ldloc.2
0x6ba0b  ldc.i4   0xA9EEDA04
0x6ba10  bgt.un.s loc_6BA7E
0x6ba12  ldloc.2
0x6ba13  ldc.i4   0x97E841F3
0x6ba18  bgt.un.s loc_6BA40
0x6ba1a  ldloc.2
0x6ba1b  ldc.i4   0x6DEFD58A
0x6ba20  beq      loc_6BC22
0x6ba25  ldloc.2
0x6ba26  ldc.i4   0x820A3ED9
0x6ba2b  beq      loc_6BAE7
0x6ba30  ldloc.2
0x6ba31  ldc.i4   0x97E841F3
0x6ba36  beq      loc_6BBA4
0x6ba3b  br       loc_6C2D8
0x6ba40  ldloc.2
0x6ba41  ldc.i4   0x98703B94
0x6ba46  bgt.un.s loc_6BA63
0x6ba48  ldloc.2
0x6ba49  ldc.i4   0x9828037A
0x6ba4e  beq      loc_6BC0D
0x6ba53  ldloc.2
0x6ba54  ldc.i4   0x98703B94
0x6ba59  beq      loc_6BCA0
0x6ba5e  br       loc_6C2D8
0x6ba63  ldloc.2
0x6ba64  ldc.i4   0xA3256D37
0x6ba69  beq      loc_6BCF4
0x6ba6e  ldloc.2
0x6ba6f  ldc.i4   0xA9EEDA04
0x6ba74  beq      loc_6BC4C
0x6ba79  br       loc_6C2D8
0x6ba7e  ldloc.2
0x6ba7f  ldc.i4   0xDD96D64D
0x6ba84  bgt.un.s loc_6BAAC
0x6ba86  ldloc.2
0x6ba87  ldc.i4   0xB211566B
0x6ba8c  beq      loc_6BB11
0x6ba91  ldloc.2
0x6ba92  ldc.i4   0xD8C7DDD4
0x6ba97  beq      loc_6BC76
0x6ba9c  ldloc.2
0x6ba9d  ldc.i4   0xDD96D64D
0x6baa2  beq      loc_6BC61
0x6baa7  br       loc_6C2D8
0x6baac  ldloc.2
0x6baad  ldc.i4   0xE2607C09
0x6bab2  bgt.un.s loc_6BACC
0x6bab4  ldloc.2
0x6bab5  ldc.i4   0xE0CC9868
0x6baba  beq      loc_6BBCE
0x6babf  ldloc.2
0x6bac0  ldc.i4   0xE2607C09
0x6bac5  beq.s    loc_6BB26
0x6bac7  br       loc_6C2D8
0x6bacc  ldloc.2
0x6bacd  ldc.i4   0xE4EE1E07
0x6bad2  beq      loc_6BCDF
0x6bad7  ldloc.2
0x6bad8  ldc.i4   0xE9F43F78
0x6badd  beq      loc_6BBF8
0x6bae2  br       loc_6C2D8
0x6bae7  ldloc.1
0x6bae8  ldstr    aAuthorizations// "AuthorizationServer"
0x6baed  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6baf2  brtrue   loc_6BD33
0x6baf7  br       loc_6C2D8
0x6bafc  ldloc.1
0x6bafd  ldstr    aPartnerapplica// "PartnerApplication"
0x6bb02  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bb07  brtrue   loc_6BD87
0x6bb0c  br       loc_6C2D8
0x6bb11  ldloc.1
0x6bb12  ldstr    aMailbox// "Mailbox"
0x6bb17  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bb1c  brtrue   loc_6BDB3
0x6bb21  br       loc_6C2D8
0x6bb26  ldloc.1
0x6bb27  ldstr    aEmailserverpro// "EmailServerProfile"
0x6bb2c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bb31  brtrue   loc_6BDF6
0x6bb36  br       loc_6C2D8
0x6bb3b  ldloc.1
0x6bb3c  ldstr    aOrganization// "Organization"
0x6bb41  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bb46  brtrue   loc_6BE22
0x6bb4b  br       loc_6C2D8
0x6bb50  ldloc.1
0x6bb51  ldstr    aSystemuser_0// "SystemUser"
0x6bb56  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bb5b  brtrue   loc_6BE67
0x6bb60  br       loc_6C2D8
0x6bb65  ldloc.1
0x6bb66  ldstr    aTransactioncur_0// "TransactionCurrency"
0x6bb6b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bb70  brtrue   loc_6BEEB
0x6bb75  br       loc_6C2D8
0x6bb7a  ldloc.1
0x6bb7b  ldstr    aSolution// "Solution"
0x6bb80  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bb85  brtrue   loc_6BF12
0x6bb8a  br       loc_6C2D8
0x6bb8f  ldloc.1
0x6bb90  ldstr    aSavedquery// "SavedQuery"
0x6bb95  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bb9a  brtrue   loc_6BF39
0x6bb9f  br       loc_6C2D8
0x6bba4  ldloc.1
0x6bba5  ldstr    aSdkmessageproc// "SdkMessageProcessingStep"
0x6bbaa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bbaf  brtrue   loc_6BF91
0x6bbb4  br       loc_6C2D8
0x6bbb9  ldloc.1
0x6bbba  ldstr    aSdkmessageproc_2// "SdkMessageProcessingStepSecureConfig"
0x6bbbf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bbc4  brtrue   loc_6BFDB
0x6bbc9  br       loc_6C2D8
0x6bbce  ldloc.1
0x6bbcf  ldstr    aSdkmessageproc_0// "SdkMessageProcessingStepImage"
0x6bbd4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bbd9  brtrue   loc_6C00D
0x6bbde  br       loc_6C2D8
0x6bbe3  ldloc.1
0x6bbe4  ldstr    aSystemform// "SystemForm"
0x6bbe9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bbee  brtrue   loc_6C046
0x6bbf3  br       loc_6C2D8
0x6bbf8  ldloc.1
0x6bbf9  ldstr    aComplexcontrol// "ComplexControl"
0x6bbfe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bc03  brtrue   loc_6C07A
0x6bc08  br       loc_6C2D8
0x6bc0d  ldloc.1
0x6bc0e  ldstr    aPlugintype// "PluginType"
0x6bc13  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bc18  brtrue   loc_6C0A6
0x6bc1d  br       loc_6C2D8
0x6bc22  ldloc.1
0x6bc23  ldstr    aPluginassembly// "PluginAssembly"
0x6bc28  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bc2d  brtrue   loc_6C0D8
0x6bc32  br       loc_6C2D8
0x6bc37  ldloc.1
0x6bc38  ldstr    aWebresource// "WebResource"
0x6bc3d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bc42  brtrue   loc_6C10A
0x6bc47  br       loc_6C2D8
0x6bc4c  ldloc.1
0x6bc4d  ldstr    aSharepointdocu// "SharePointDocumentLocation"
0x6bc52  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bc57  brtrue   loc_6C131
0x6bc5c  br       loc_6C2D8
0x6bc61  ldloc.1
0x6bc62  ldstr    aSharepointsite// "SharePointSite"
0x6bc67  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bc6c  brtrue   loc_6C131
0x6bc71  br       loc_6C2D8
0x6bc76  ldloc.1
0x6bc77  ldstr    aHierarchysecur// "HierarchySecurityConfiguration"
0x6bc7c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bc81  brtrue   loc_6C163
0x6bc86  br       loc_6C2D8
0x6bc8b  ldloc.1
0x6bc8c  ldstr    aHierarchyrule// "HierarchyRule"
0x6bc91  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bc96  brtrue   loc_6C195
0x6bc9b  br       loc_6C2D8
0x6bca0  ldloc.1
0x6bca1  ldstr    aUsermapping// "UserMapping"
0x6bca6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bcab  brtrue   loc_6C1BC
0x6bcb0  br       loc_6C2D8
0x6bcb5  ldloc.1
0x6bcb6  ldstr    aSyncattributem// "SyncAttributeMapping"
0x6bcbb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bcc0  brtrue   loc_6C1E8
0x6bcc5  br       loc_6C2D8
0x6bcca  ldloc.1
0x6bccb  ldstr    aGlobalsearchco// "GlobalSearchConfiguration"
0x6bcd0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bcd5  brtrue   loc_6C214
0x6bcda  br       loc_6C2D8
0x6bcdf  ldloc.1
0x6bce0  ldstr    aEntitydataprov// "EntityDataProvider"
0x6bce5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bcea  brtrue   loc_6C237
0x6bcef  br       loc_6C2D8
0x6bcf4  ldloc.1
0x6bcf5  ldstr    aEntitydatasour// "EntityDataSource"
0x6bcfa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bcff  brtrue   loc_6C266
0x6bd04  br       loc_6C2D8
0x6bd09  ldloc.1
0x6bd0a  ldstr    aSavedqueryvisu// "SavedQueryVisualization"
0x6bd0f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bd14  brtrue   loc_6C292
0x6bd19  br       loc_6C2D8
0x6bd1e  ldloc.1
0x6bd1f  ldstr    aUserqueryvisua// "UserQueryVisualization"
0x6bd24  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bd29  brtrue   loc_6C2B6
0x6bd2e  br       loc_6C2D8
0x6bd33  ldc.i4.s 0x49
0x6bd35  ldarg.1
0x6bd36  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x6bd3b  unbox.any [mscorlib]System.Guid
0x6bd40  stloc.3
0x6bd41  ldloca.s 3
0x6bd43  ldstr    aB_0// "B"
0x6bd48  call     instance string [mscorlib]System.Guid::ToString(string)
0x6bd4d  ldarg.2
0x6bd4e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6bd53  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string, valuetype [mscorlib]System.Guid)
0x6bd58  ldc.i4.1
0x6bd59  ldarg.3
0x6bd5a  beq.s    loc_6BD60
0x6bd5c  ldc.i4.4
0x6bd5d  ldarg.3
0x6bd5e  bne.un.s loc_6BD80
0x6bd60  ldc.i4.s 0x4A
0x6bd62  ldarg.2
0x6bd63  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
  ... truncated ...
```
