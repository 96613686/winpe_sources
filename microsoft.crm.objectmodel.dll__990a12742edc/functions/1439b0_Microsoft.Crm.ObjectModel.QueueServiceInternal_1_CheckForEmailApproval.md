# Microsoft.Crm.ObjectModel.QueueServiceInternal`1::CheckForEmailApproval

- ea: `0x1439b0`
- end: `0x143bac`
- name: `Microsoft.Crm.ObjectModel.QueueServiceInternal`1::CheckForEmailApproval`
- size: `508`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xd8c20`
- `0x128e30`
- `0x1439b0`

## string_xrefs

- `0x1439c1`: `emailrouteraccessapproval`
- `0x1439d7`: `emailrouteraccessapproval`
- `0x1439ed`: `emailrouteraccessapproval`
- `0x143a6b`: `emailrouteraccessapproval`
- `0x143ab3`: `emailrouteraccessapproval`
- `0x143ac0`: `emailrouteraccessapproval`
- `0x143ad2`: `emailrouteraccessapproval`
- `0x143af5`: `emailrouteraccessapproval`
- `0x143b15`: `emailrouteraccessapproval`
- `0x143b35`: `emailrouteraccessapproval`
- `0x143b5a`: `emailrouteraccessapproval`
- `0x143b6b`: `emailrouteraccessapproval`
- `0x143b78`: `emailrouteraccessapproval`

## pseudocode

```c

```

## disassembly

```asm
0x1439b0  ldarg.2
0x1439b1  brfalse.s loc_1439EC
0x1439b3  ldarg.1
0x1439b4  ldstr    aEmailaddress// "emailaddress"
0x1439b9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1439be  brfalse.s loc_1439D6
0x1439c0  ldarg.1
0x1439c1  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x1439c6  ldc.i4.0
0x1439c7  box      [mscorlib]System.Int32
0x1439cc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x1439d1  br       loc_143B6A
0x1439d6  ldarg.1
0x1439d7  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x1439dc  ldc.i4.2
0x1439dd  box      [mscorlib]System.Int32
0x1439e2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x1439e7  br       loc_143B6A
0x1439ec  ldarg.1
0x1439ed  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x1439f2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1439f7  brtrue   loc_143B27
0x1439fc  ldarg.3
0x1439fd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x143a02  ldstr    aPrvapprovereje// "prvApproveRejectEmailAddress"
0x143a07  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0x143a0c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x143a11  stloc.0
0x143a12  ldarg.3
0x143a13  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x143a18  ldloc.0
0x143a19  ldarg.3
0x143a1a  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x143a1f  newobj   instance void Microsoft.Crm.ObjectModel.SystemUserService::.ctor()
0x143a24  ldarg.0
0x143a25  ldarg.1
0x143a26  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x143a2b  unbox.any [mscorlib]System.Guid
0x143a30  ldarg.3
0x143a31  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal class Microsoft.Crm.ObjectModel.QueueServiceInternal`1<var<u1>>::GetQueueOwnerSecurityPrinicipal(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x143a36  stloc.1
0x143a37  ldarg.3
0x143a38  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x143a3d  ldloc.1
0x143a3e  ldloc.0
0x143a3f  ldarg.3
0x143a40  callvirt instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<class Microsoft.Crm.ObjectModel.ProvisioningOff>::CheckPrivilegeForApproveReject(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x143a45  ldarg.1
0x143a46  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x143a4b  unbox.any [mscorlib]System.Guid
0x143a50  ldstr    aQueue// "Queue"
0x143a55  ldarg.3
0x143a56  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x143a5b  stloc.2
0x143a5c  ldarg.0
0x143a5d  ldloc.2
0x143a5e  ldstr    aQueue// "Queue"
0x143a63  ldc.i4.2
0x143a64  newarr   [mscorlib]System.String
0x143a69  dup
0x143a6a  ldc.i4.0
0x143a6b  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x143a70  stelem.ref
0x143a71  dup
0x143a72  ldc.i4.1
0x143a73  ldstr    aEmailaddress// "emailaddress"
0x143a78  stelem.ref
0x143a79  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x143a7e  ldarg.3
0x143a7f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x143a84  ldarg.3
0x143a85  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x143a8a  stloc.3
0x143a8b  ldarg.1
0x143a8c  ldstr    aEmailaddress// "emailaddress"
0x143a91  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x143a96  brtrue.s loc_143AA5
0x143a98  ldloc.3
0x143a99  ldstr    aEmailaddress// "emailaddress"
0x143a9e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x143aa3  br.s     loc_143AB0
0x143aa5  ldarg.1
0x143aa6  ldstr    aEmailaddress// "emailaddress"
0x143aab  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x143ab0  stloc.s  4
0x143ab2  ldarg.1
0x143ab3  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x143ab8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x143abd  brfalse.s loc_143AD1
0x143abf  ldloc.3
0x143ac0  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x143ac5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x143aca  unbox.any [mscorlib]System.Int32
0x143acf  br.s     loc_143AE1
0x143ad1  ldarg.1
0x143ad2  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x143ad7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x143adc  unbox.any [mscorlib]System.Int32
0x143ae1  stloc.s  5
0x143ae3  ldloc.s  5
0x143ae5  brtrue.s loc_143B07
0x143ae7  ldloc.s  4
0x143ae9  brfalse.s loc_143B07
0x143aeb  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x143af0  ldloc.s  4
0x143af2  beq.s    loc_143B07
0x143af4  ldarg.1
0x143af5  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x143afa  ldc.i4.2
0x143afb  box      [mscorlib]System.Int32
0x143b00  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x143b05  br.s     loc_143B6A
0x143b07  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x143b0c  ldloc.s  4
0x143b0e  bne.un.s loc_143B6A
0x143b10  ldloc.s  5
0x143b12  brfalse.s loc_143B6A
0x143b14  ldarg.1
0x143b15  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x143b1a  ldc.i4.0
0x143b1b  box      [mscorlib]System.Int32
0x143b20  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x143b25  br.s     loc_143B6A
0x143b27  ldarg.1
0x143b28  ldstr    aEmailaddress// "emailaddress"
0x143b2d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x143b32  brtrue.s loc_143B47
0x143b34  ldarg.1
0x143b35  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x143b3a  ldc.i4.2
0x143b3b  box      [mscorlib]System.Int32
0x143b40  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x143b45  br.s     loc_143B6A
0x143b47  ldarg.1
0x143b48  ldstr    aEmailaddress// "emailaddress"
0x143b4d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x143b52  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x143b57  bne.un.s loc_143B6A
0x143b59  ldarg.1
0x143b5a  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x143b5f  ldc.i4.0
0x143b60  box      [mscorlib]System.Int32
0x143b65  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x143b6a  ldarg.1
0x143b6b  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x143b70  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x143b75  brtrue.s loc_143BAB
0x143b77  ldarg.1
0x143b78  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x143b7d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x143b82  unbox.any [mscorlib]System.Int32
0x143b87  ldc.i4.1
0x143b88  bne.un.s loc_143B9A
0x143b8a  ldarg.0
0x143b8b  call     instance bool class Microsoft.Crm.ObjectModel.ProvisionedEntity`1<var<u1>>::get_Provisioning()
0x143b90  brtrue.s loc_143BAB
0x143b92  ldarg.1
0x143b93  ldarg.3
0x143b94  call     void Microsoft.Crm.ObjectModel.MailboxUtil::SetO365AdminApprovalStatus(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x143b99  ret
0x143b9a  ldarg.1
0x143b9b  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x143ba0  ldc.i4.0
0x143ba1  box      [mscorlib]System.Boolean
0x143ba6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::SetAttributeValue(string, object)
0x143bab  ret
```
