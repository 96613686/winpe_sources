# Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1::CheckForEmailApproval

- ea: `0xd5810`
- end: `0xd5bcf`
- name: `Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1::CheckForEmailApproval`
- size: `959`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xd5810`
- `0x128e30`
- `0x129270`

## string_xrefs

- `0xd5821`: `emailrouteraccessapproval`
- `0xd5837`: `emailrouteraccessapproval`
- `0xd584d`: `emailrouteraccessapproval`
- `0xd58d8`: `emailrouteraccessapproval`
- `0xd591f`: `emailrouteraccessapproval`
- `0xd592c`: `emailrouteraccessapproval`
- `0xd593e`: `emailrouteraccessapproval`
- `0xd595d`: `emailrouteraccessapproval`
- `0xd59c1`: `emailrouteraccessapproval`
- `0xd5a4c`: `emailrouteraccessapproval`
- `0xd5a90`: `emailrouteraccessapproval`
- `0xd5b0b`: `emailrouteraccessapproval`
- `0xd5b55`: `emailrouteraccessapproval`
- `0xd5b62`: `emailrouteraccessapproval`
- `0xd5975`: `Mailbox emailrouteraccessapproval is set to PendingApproval for the user: {0} email address {1} is not null. Provisioning: {2}.`
- `0xd59d9`: `Mailbox emailrouteraccessapproval is set to empty for the user: {0} email address is null. Provisioning: {1}.`
- `0xd5aa8`: `Mailbox emailrouteraccessapproval is set to PendingApproval for the user: {0} email address {1} is changed to {2}. Provisioning: {3}.`
- `0xd5b23`: `Mailbox emailrouteraccessapproval is set to empty for the user: {0} email address was removed. Provisioning: {1}.`
- `0xd5b9d`: `Mailbox isemailaddressapprovedbyo365admin is set to false for the user: {0} because emailrouteraccessapproval is not set to approved. Provisioning: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0xd5810  ldarg.2
0xd5811  brfalse.s loc_D584C
0xd5813  ldarg.1
0xd5814  ldstr    aInternalemaila// "internalemailaddress"
0xd5819  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xd581e  brfalse.s loc_D5836
0xd5820  ldarg.1
0xd5821  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xd5826  ldc.i4.0
0xd5827  box      [mscorlib]System.Int32
0xd582c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0xd5831  br       loc_D5B54
0xd5836  ldarg.1
0xd5837  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xd583c  ldc.i4.2
0xd583d  box      [mscorlib]System.Int32
0xd5842  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0xd5847  br       loc_D5B54
0xd584c  ldarg.1
0xd584d  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xd5852  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xd5857  brtrue   loc_D5A0F
0xd585c  ldarg.0
0xd585d  call     instance bool class Microsoft.Crm.ObjectModel.ProvisionedEntity`1<var<u1>>::get_Provisioning()
0xd5862  brtrue.s loc_D58AD
0xd5864  ldarg.3
0xd5865  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd586a  ldstr    aPrvapprovereje// "prvApproveRejectEmailAddress"
0xd586f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0xd5874  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0xd5879  stloc.s  4
0xd587b  ldarg.3
0xd587c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xd5881  ldloc.s  4
0xd5883  ldarg.3
0xd5884  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd5889  ldc.i4.8
0xd588a  ldarg.1
0xd588b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0xd5890  unbox.any [mscorlib]System.Guid
0xd5895  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::.ctor(int32, valuetype [mscorlib]System.Guid)
0xd589a  stloc.s  5
0xd589c  ldarg.0
0xd589d  ldarg.3
0xd589e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xd58a3  ldloc.s  5
0xd58a5  ldloc.s  4
0xd58a7  ldarg.3
0xd58a8  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::CheckPrivilegeForApproveReject(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd58ad  ldarg.1
0xd58ae  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0xd58b3  unbox.any [mscorlib]System.Guid
0xd58b8  ldstr    aSystemuser_0// "SystemUser"
0xd58bd  ldarg.3
0xd58be  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd58c3  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0xd58c8  stloc.0
0xd58c9  ldarg.0
0xd58ca  ldloc.0
0xd58cb  ldstr    aSystemuser_0// "SystemUser"
0xd58d0  ldc.i4.2
0xd58d1  newarr   [mscorlib]System.String
0xd58d6  dup
0xd58d7  ldc.i4.0
0xd58d8  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xd58dd  stelem.ref
0xd58de  dup
0xd58df  ldc.i4.1
0xd58e0  ldstr    aInternalemaila// "internalemailaddress"
0xd58e5  stelem.ref
0xd58e6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xd58eb  ldarg.3
0xd58ec  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xd58f1  ldarg.3
0xd58f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd58f7  stloc.1
0xd58f8  ldarg.1
0xd58f9  ldstr    aInternalemaila// "internalemailaddress"
0xd58fe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd5903  brtrue.s loc_D5912
0xd5905  ldloc.1
0xd5906  ldstr    aInternalemaila// "internalemailaddress"
0xd590b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd5910  br.s     loc_D591D
0xd5912  ldarg.1
0xd5913  ldstr    aInternalemaila// "internalemailaddress"
0xd5918  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd591d  stloc.2
0xd591e  ldarg.1
0xd591f  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xd5924  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xd5929  brfalse.s loc_D593D
0xd592b  ldloc.1
0xd592c  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xd5931  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd5936  unbox.any [mscorlib]System.Int32
0xd593b  br.s     loc_D594D
0xd593d  ldarg.1
0xd593e  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xd5943  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd5948  unbox.any [mscorlib]System.Int32
0xd594d  stloc.3
0xd594e  ldloc.3
0xd594f  brtrue.s loc_D59AF
0xd5951  ldloc.2
0xd5952  brfalse.s loc_D59AF
0xd5954  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd5959  ldloc.2
0xd595a  beq.s    loc_D59AF
0xd595c  ldarg.1
0xd595d  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xd5962  ldc.i4.2
0xd5963  box      [mscorlib]System.Int32
0xd5968  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0xd596d  ldarg.3
0xd596e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd5973  ldc.i4.s 0x11
0xd5975  ldstr    aMailboxEmailro// "Mailbox emailrouteraccessapproval is se"...
0xd597a  ldc.i4.3
0xd597b  newarr   [mscorlib]System.Object
0xd5980  dup
0xd5981  ldc.i4.0
0xd5982  ldarg.1
0xd5983  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0xd5988  unbox.any [mscorlib]System.Guid
0xd598d  box      [mscorlib]System.Guid
0xd5992  stelem.ref
0xd5993  dup
0xd5994  ldc.i4.1
0xd5995  ldloc.2
0xd5996  stelem.ref
0xd5997  dup
0xd5998  ldc.i4.2
0xd5999  ldarg.0
0xd599a  call     instance bool class Microsoft.Crm.ObjectModel.ProvisionedEntity`1<var<u1>>::get_Provisioning()
0xd599f  box      [mscorlib]System.Boolean
0xd59a4  stelem.ref
0xd59a5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd59aa  br       loc_D5B54
0xd59af  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd59b4  ldloc.2
0xd59b5  bne.un   loc_D5B54
0xd59ba  ldloc.3
0xd59bb  brfalse  loc_D5B54
0xd59c0  ldarg.1
0xd59c1  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xd59c6  ldc.i4.0
0xd59c7  box      [mscorlib]System.Int32
0xd59cc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0xd59d1  ldarg.3
0xd59d2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd59d7  ldc.i4.s 0x11
0xd59d9  ldstr    aMailboxEmailro_0// "Mailbox emailrouteraccessapproval is se"...
0xd59de  ldc.i4.2
0xd59df  newarr   [mscorlib]System.Object
0xd59e4  dup
0xd59e5  ldc.i4.0
0xd59e6  ldarg.1
0xd59e7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0xd59ec  unbox.any [mscorlib]System.Guid
0xd59f1  box      [mscorlib]System.Guid
0xd59f6  stelem.ref
0xd59f7  dup
0xd59f8  ldc.i4.1
0xd59f9  ldarg.0
0xd59fa  call     instance bool class Microsoft.Crm.ObjectModel.ProvisionedEntity`1<var<u1>>::get_Provisioning()
0xd59ff  box      [mscorlib]System.Boolean
0xd5a04  stelem.ref
0xd5a05  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd5a0a  br       loc_D5B54
0xd5a0f  ldarg.1
0xd5a10  ldstr    aInternalemaila// "internalemailaddress"
0xd5a15  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xd5a1a  brtrue   loc_D5AF8
0xd5a1f  ldarg.1
0xd5a20  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0xd5a25  unbox.any [mscorlib]System.Guid
0xd5a2a  ldstr    aSystemuser_0// "SystemUser"
0xd5a2f  ldarg.3
0xd5a30  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd5a35  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0xd5a3a  stloc.s  6
0xd5a3c  ldarg.0
0xd5a3d  ldloc.s  6
0xd5a3f  ldstr    aSystemuser_0// "SystemUser"
0xd5a44  ldc.i4.2
0xd5a45  newarr   [mscorlib]System.String
0xd5a4a  dup
0xd5a4b  ldc.i4.0
0xd5a4c  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xd5a51  stelem.ref
0xd5a52  dup
0xd5a53  ldc.i4.1
0xd5a54  ldstr    aInternalemaila// "internalemailaddress"
0xd5a59  stelem.ref
0xd5a5a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xd5a5f  ldarg.3
0xd5a60  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xd5a65  ldarg.3
0xd5a66  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd5a6b  stloc.s  7
0xd5a6d  ldarg.1
0xd5a6e  ldstr    aInternalemaila// "internalemailaddress"
0xd5a73  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd5a78  ldloc.s  7
0xd5a7a  ldstr    aInternalemaila// "internalemailaddress"
0xd5a7f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd5a84  ldc.i4.1
0xd5a85  call     bool Microsoft.Crm.ObjectModel.MailboxUtil::HasValueChanged(object newValue, object oldValue, [opt] bool isCaseInsensitive)
0xd5a8a  brfalse  loc_D5B54
0xd5a8f  ldarg.1
0xd5a90  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xd5a95  ldc.i4.2
0xd5a96  box      [mscorlib]System.Int32
0xd5a9b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0xd5aa0  ldarg.3
0xd5aa1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd5aa6  ldc.i4.s 0x11
0xd5aa8  ldstr    aMailboxEmailro_1// "Mailbox emailrouteraccessapproval is se"...
0xd5aad  ldc.i4.4
0xd5aae  newarr   [mscorlib]System.Object
0xd5ab3  dup
0xd5ab4  ldc.i4.0
0xd5ab5  ldarg.1
0xd5ab6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0xd5abb  unbox.any [mscorlib]System.Guid
0xd5ac0  box      [mscorlib]System.Guid
0xd5ac5  stelem.ref
0xd5ac6  dup
0xd5ac7  ldc.i4.1
0xd5ac8  ldloc.s  7
0xd5aca  ldstr    aInternalemaila// "internalemailaddress"
0xd5acf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd5ad4  stelem.ref
0xd5ad5  dup
0xd5ad6  ldc.i4.2
0xd5ad7  ldarg.1
0xd5ad8  ldstr    aInternalemaila// "internalemailaddress"
0xd5add  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd5ae2  stelem.ref
0xd5ae3  dup
0xd5ae4  ldc.i4.3
0xd5ae5  ldarg.0
0xd5ae6  call     instance bool class Microsoft.Crm.ObjectModel.ProvisionedEntity`1<var<u1>>::get_Provisioning()
0xd5aeb  box      [mscorlib]System.Boolean
0xd5af0  stelem.ref
0xd5af1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd5af6  br.s     loc_D5B54
0xd5af8  ldarg.1
0xd5af9  ldstr    aInternalemaila// "internalemailaddress"
0xd5afe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd5b03  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd5b08  bne.un.s loc_D5B54
0xd5b0a  ldarg.1
0xd5b0b  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xd5b10  ldc.i4.0
0xd5b11  box      [mscorlib]System.Int32
0xd5b16  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0xd5b1b  ldarg.3
0xd5b1c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd5b21  ldc.i4.s 0x11
0xd5b23  ldstr    aMailboxEmailro_2// "Mailbox emailrouteraccessapproval is se"...
0xd5b28  ldc.i4.2
0xd5b29  newarr   [mscorlib]System.Object
0xd5b2e  dup
0xd5b2f  ldc.i4.0
0xd5b30  ldarg.1
0xd5b31  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0xd5b36  unbox.any [mscorlib]System.Guid
0xd5b3b  box      [mscorlib]System.Guid
0xd5b40  stelem.ref
0xd5b41  dup
0xd5b42  ldc.i4.1
0xd5b43  ldarg.0
0xd5b44  call     instance bool class Microsoft.Crm.ObjectModel.ProvisionedEntity`1<var<u1>>::get_Provisioning()
0xd5b49  box      [mscorlib]System.Boolean
0xd5b4e  stelem.ref
0xd5b4f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd5b54  ldarg.1
0xd5b55  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xd5b5a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xd5b5f  brtrue.s loc_D5BCE
0xd5b61  ldarg.1
0xd5b62  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0xd5b67  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd5b6c  unbox.any [mscorlib]System.Int32
0xd5b71  ldc.i4.1
0xd5b72  bne.un.s loc_D5B84
0xd5b74  ldarg.0
0xd5b75  call     instance bool class Microsoft.Crm.ObjectModel.ProvisionedEntity`1<var<u1>>::get_Provisioning()
0xd5b7a  brtrue.s loc_D5BCE
0xd5b7c  ldarg.1
0xd5b7d  ldarg.3
0xd5b7e  call     void Microsoft.Crm.ObjectModel.MailboxUtil::SetO365AdminApprovalStatus(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd5b83  ret
0xd5b84  ldarg.1
0xd5b85  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0xd5b8a  ldc.i4.0
0xd5b8b  box      [mscorlib]System.Boolean
0xd5b90  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
  ... truncated ...
```
