# Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::GetPrimaryFieldName

- ea: `0xb96d0`
- end: `0xba124`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::GetPrimaryFieldName`
- size: `2644`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0xb8dd0`
- `0xbb2e0`

## callees

- `0xb8440`
- `0xb8450`
- `0xb8460`
- `0xb8470`
- `0xb8480`
- `0xb8eb0`
- `0xb9210`
- `0xb96d0`

## string_xrefs

- `0xb9d29`: `CustomControlDefaultConfig`
- `0xb9d3e`: `customcontroldefaultconfigid`
- `0xb9d5f`: `customcontroldefaultconfigid`

## pseudocode

```c

```

## disassembly

```asm
0xb96d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb96d5  stloc.0
0xb96d6  newobj   instance void Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::.ctor()
0xb96db  stloc.2
0xb96dc  ldarg.2
0xb96dd  ldc.i4   0x1207
0xb96e2  bgt      loc_B985F
0xb96e7  ldarg.2
0xb96e8  ldc.i4   0x460
0xb96ed  bgt      loc_B97A0
0xb96f2  ldarg.2
0xb96f3  ldc.i4   0x406
0xb96f8  bgt.s    loc_B973A
0xb96fa  ldarg.2
0xb96fb  ldc.i4.s 0x55
0xb96fd  bgt.s    loc_B9714
0xb96ff  ldarg.2
0xb9700  ldc.i4.s 0x4E
0xb9702  beq      loc_B9A96
0xb9707  ldarg.2
0xb9708  ldc.i4.s 0x55
0xb970a  beq      loc_B9A96
0xb970f  br       loc_BA117
0xb9714  ldarg.2
0xb9715  ldc.i4   0x3F8
0xb971a  beq      loc_B9A96
0xb971f  ldarg.2
0xb9720  ldc.i4   0x3FB
0xb9725  beq      loc_B9BAA
0xb972a  ldarg.2
0xb972b  ldc.i4   0x406
0xb9730  beq      loc_B9B1D
0xb9735  br       loc_BA117
0xb973a  ldarg.2
0xb973b  ldc.i4   0x40C
0xb9740  bgt.s    loc_B975D
0xb9742  ldarg.2
0xb9743  ldc.i4   0x408
0xb9748  beq      loc_B9B1D
0xb974d  ldarg.2
0xb974e  ldc.i4   0x40C
0xb9753  beq      loc_B9A96
0xb9758  br       loc_BA117
0xb975d  ldarg.2
0xb975e  ldc.i4   0x40F
0xb9763  beq      loc_B9AD3
0xb9768  ldarg.2
0xb9769  ldc.i4   0x457
0xb976e  sub
0xb976f  switch   loc_B9AD3, loc_BA117, loc_BA117, loc_BA117, loc_B9BAA, loc_B9BAA, loc_B9BAA
0xb9790  ldarg.2
0xb9791  ldc.i4   0x460
0xb9796  beq      loc_B9BAA
0xb979b  br       loc_BA117
0xb97a0  ldarg.2
0xb97a1  ldc.i4   0xBBD
0xb97a6  bgt.s    loc_B97F1
0xb97a8  ldarg.2
0xb97a9  ldc.i4   0x4B0
0xb97ae  bgt.s    loc_B97CB
0xb97b0  ldarg.2
0xb97b1  ldc.i4   0x46A
0xb97b6  beq      loc_B9BAA
0xb97bb  ldarg.2
0xb97bc  ldc.i4   0x4B0
0xb97c1  beq      loc_B9A96
0xb97c6  br       loc_BA117
0xb97cb  ldarg.2
0xb97cc  ldc.i4   0x7DA
0xb97d1  beq      loc_B9A96
0xb97d6  ldarg.2
0xb97d7  ldc.i4   0x7DB
0xb97dc  beq      loc_B9A96
0xb97e1  ldarg.2
0xb97e2  ldc.i4   0xBBD
0xb97e7  beq      loc_B9A96
0xb97ec  br       loc_BA117
0xb97f1  ldarg.2
0xb97f2  ldc.i4   0x1005
0xb97f7  bgt.s    loc_B9814
0xb97f9  ldarg.2
0xb97fa  ldc.i4   0xC9F
0xb97ff  beq      loc_B9A96
0xb9804  ldarg.2
0xb9805  ldc.i4   0x1005
0xb980a  beq      loc_B9BAA
0xb980f  br       loc_BA117
0xb9814  ldarg.2
0xb9815  ldc.i4   0x1006
0xb981a  beq      loc_B9BAA
0xb981f  ldarg.2
0xb9820  ldc.i4   0x11F8
0xb9825  sub
0xb9826  switch   loc_B9BAA, loc_B9BAA, loc_B9A96, loc_BA117, loc_BA117, loc_B9A96, loc_BA117, loc_BA117, loc_B9A96
0xb984f  ldarg.2
0xb9850  ldc.i4   0x1207
0xb9855  beq      loc_B9A96
0xb985a  br       loc_BA117
0xb985f  ldarg.2
0xb9860  ldc.i4   0x2392
0xb9865  bgt      loc_B9904
0xb986a  ldarg.2
0xb986b  ldc.i4   0x1BBC
0xb9870  bgt.s    loc_B98BB
0xb9872  ldarg.2
0xb9873  ldc.i4   0x125F
0xb9878  bgt.s    loc_B9895
0xb987a  ldarg.2
0xb987b  ldc.i4   0x120A
0xb9880  beq      loc_B9A96
0xb9885  ldarg.2
0xb9886  ldc.i4   0x125F
0xb988b  beq      loc_B9A96
0xb9890  br       loc_BA117
0xb9895  ldarg.2
0xb9896  ldc.i4   0x1260
0xb989b  beq      loc_B9BAA
0xb98a0  ldarg.2
0xb98a1  ldc.i4   0x1265
0xb98a6  beq      loc_B9BDA
0xb98ab  ldarg.2
0xb98ac  ldc.i4   0x1BBC
0xb98b1  beq      loc_B9B10
0xb98b6  br       loc_BA117
0xb98bb  ldarg.2
0xb98bc  ldc.i4   0x2288
0xb98c1  bgt.s    loc_B98DE
0xb98c3  ldarg.2
0xb98c4  ldc.i4   0x1FF5
0xb98c9  beq      loc_B9A96
0xb98ce  ldarg.2
0xb98cf  ldc.i4   0x2288
0xb98d4  beq      loc_B9AD3
0xb98d9  br       loc_BA117
0xb98de  ldarg.2
0xb98df  ldc.i4   0x232E
0xb98e4  beq      loc_BA031
0xb98e9  ldarg.2
0xb98ea  ldc.i4   0x238C
0xb98ef  beq      loc_B9A96
0xb98f4  ldarg.2
0xb98f5  ldc.i4   0x2392
0xb98fa  beq      loc_B9A96
0xb98ff  br       loc_BA117
0xb9904  ldarg.2
0xb9905  ldc.i4   0x2619
0xb990a  bgt.s    loc_B9955
0xb990c  ldarg.2
0xb990d  ldc.i4   0x2475
0xb9912  bgt.s    loc_B992F
0xb9914  ldarg.2
0xb9915  ldc.i4   0x2454
0xb991a  beq      loc_B9A96
0xb991f  ldarg.2
0xb9920  ldc.i4   0x2475
0xb9925  beq      loc_B9AD3
0xb992a  br       loc_BA117
0xb992f  ldarg.2
0xb9930  ldc.i4   0x24B8
0xb9935  beq      loc_B9A96
0xb993a  ldarg.2
0xb993b  ldc.i4   0x2616
0xb9940  beq      loc_B9A96
0xb9945  ldarg.2
0xb9946  ldc.i4   0x2619
0xb994b  beq      loc_B9E2C
0xb9950  br       loc_BA117
0xb9955  ldarg.2
0xb9956  ldc.i4   0x268C
0xb995b  bgt.s    loc_B99C1
0xb995d  ldarg.2
0xb995e  ldc.i4   0x261B
0xb9963  beq      loc_B9CEE
0xb9968  ldarg.2
0xb9969  ldc.i4   0x2649
0xb996e  sub
0xb996f  switch   loc_B9ED9, loc_B99FE, loc_B9FA4, loc_B9F58, loc_B9F25, loc_B99FE, loc_B9FEA, loc_B9BAA, loc_BA117, loc_B99FC, loc_BA117, loc_B9A4A
0xb99a4  ldarg.2
0xb99a5  ldc.i4   0x268A
0xb99aa  sub
0xb99ab  switch   loc_B9AD3, loc_B9AD3, loc_B9AD3
0xb99bc  br       loc_BA117
0xb99c1  ldarg.2
0xb99c2  ldc.i4   0x26CD
0xb99c7  beq      loc_B9A96
0xb99cc  ldarg.2
0xb99cd  ldc.i4   0x26D6
0xb99d2  beq      loc_B9A96
0xb99d7  ldarg.2
0xb99d8  ldc.i4   0x26DB
0xb99dd  sub
0xb99de  switch   loc_B9A96, loc_BA117, loc_B9A96, loc_BA117, loc_B9AD3
0xb99f7  br       loc_BA117
0xb99fc  ldloc.2
0xb99fd  ret
0xb99fe  ldarg.0
0xb99ff  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::mdcache
0xb9a04  brtrue.s loc_B9A11
0xb9a06  ldarg.0
0xb9a07  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0xb9a0c  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::mdcache
0xb9a11  ldloc.2
0xb9a12  ldarg.0
0xb9a13  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::mdcache
0xb9a18  ldarg.1
0xb9a19  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetAttribute(valuetype [mscorlib]System.Guid)
0xb9a1e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0xb9a23  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::set_Name(string value)
0xb9a28  ldloc.2
0xb9a29  ldarg.0
0xb9a2a  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::mdcache
0xb9a2f  ldarg.1
0xb9a30  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetAttribute(valuetype [mscorlib]System.Guid)
0xb9a35  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0xb9a3a  ldloc.0
0xb9a3b  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetLabelString(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb9a40  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::set_DisplayName(string value)
0xb9a45  br       loc_BA122
0xb9a4a  ldarg.0
0xb9a4b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::mdcache
0xb9a50  brtrue.s loc_B9A5D
0xb9a52  ldarg.0
0xb9a53  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0xb9a58  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::mdcache
0xb9a5d  ldloc.2
0xb9a5e  ldarg.0
0xb9a5f  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::mdcache
0xb9a64  ldarg.1
0xb9a65  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntityKey(valuetype [mscorlib]System.Guid)
0xb9a6a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata::get_Name()
0xb9a6f  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::set_Name(string value)
0xb9a74  ldloc.2
0xb9a75  ldarg.0
0xb9a76  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::mdcache
0xb9a7b  ldarg.1
0xb9a7c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntityKey(valuetype [mscorlib]System.Guid)
0xb9a81  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata::get_DisplayNames()
0xb9a86  ldloc.0
0xb9a87  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetLabelString(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb9a8c  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::set_DisplayName(string value)
0xb9a91  br       loc_BA122
0xb9a96  ldloc.0
0xb9a97  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb9a9c  ldarg.2
0xb9a9d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xb9aa2  stloc.1
0xb9aa3  ldloc.2
0xb9aa4  ldarg.0
0xb9aa5  ldarg.1
0xb9aa6  ldloc.1
0xb9aa7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xb9aac  ldloc.1
0xb9aad  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0xb9ab2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0xb9ab7  ldc.i4.0
0xb9ab8  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::RetrievePrimaryField(valuetype [mscorlib]System.Guid id, string entityName, string fieldName, bool bUnPublished)
0xb9abd  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::set_Name(string value)
0xb9ac2  ldloc.2
0xb9ac3  ldloc.2
0xb9ac4  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::get_Name()
0xb9ac9  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::set_DisplayName(string value)
0xb9ace  br       loc_BA122
0xb9ad3  ldloc.0
0xb9ad4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb9ad9  ldarg.2
0xb9ada  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xb9adf  stloc.1
0xb9ae0  ldloc.2
0xb9ae1  ldarg.0
0xb9ae2  ldarg.1
0xb9ae3  ldloc.1
0xb9ae4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xb9ae9  ldloc.1
0xb9aea  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0xb9aef  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0xb9af4  ldc.i4.1
0xb9af5  call     instance string Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::RetrievePrimaryField(valuetype [mscorlib]System.Guid id, string entityName, string fieldName, bool bUnPublished)
0xb9afa  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::set_Name(string value)
0xb9aff  ldloc.2
0xb9b00  ldloc.2
0xb9b01  callvirt instance string Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::get_Name()
0xb9b06  callvirt instance void Microsoft.Crm.Application.Controls.SystemCustomization.NamePair::set_DisplayName(string value)
0xb9b0b  br       loc_BA122
0xb9b10  ldarg.0
0xb9b11  ldarg.1
0xb9b12  call     instance class Microsoft.Crm.Application.Controls.SystemCustomization.NamePair Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::RetrieveSolutionNamePair(valuetype [mscorlib]System.Guid id)
0xb9b17  stloc.2
0xb9b18  br       loc_BA122
0xb9b1d  ldc.i4   0x406
0xb9b22  starg.s  2
0xb9b24  ldloc.0
0xb9b25  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb9b2a  ldarg.2
0xb9b2b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xb9b30  stloc.1
0xb9b31  ldloc.1
0xb9b32  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xb9b37  ldarg.1
0xb9b38  ldc.i4.2
0xb9b39  newarr   [mscorlib]System.String
  ... truncated ...
```
