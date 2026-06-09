# Microsoft.Crm.Tools.Admin.OrganizationOperationChecksFactory::GetCommonSqlServerChecks

- ea: `0xb6d0`
- end: `0xb7db`
- name: `Microsoft.Crm.Tools.Admin.OrganizationOperationChecksFactory::GetCommonSqlServerChecks`
- size: `267`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xb7e0`
- `0xb810`
- `0xb880`
- `0xb8b0`
- `0xb920`

## callees

- `0xb0c0`
- `0xc7a0`
- `0xc850`
- `0xc8c0`

## pseudocode

```c

```

## disassembly

```asm
0xb6d0  newobj   instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionDescriptorCollection::.ctor()
0xb6d5  ldloca.s 0
0xb6d7  ldstr    aA636628802304e// "A6366288-0230-4e7b-B007-7E599E35E880"
0xb6dc  call     instance void [mscorlib]System.Guid::.ctor(string)
0xb6e1  ldloca.s 1
0xb6e3  ldstr    a0323a462Feb942// "0323A462-FEB9-4253-A1F3-8B57DDF7A994"
0xb6e8  call     instance void [mscorlib]System.Guid::.ctor(string)
0xb6ed  ldloca.s 2
0xb6ef  ldstr    a780ab0133fc642// "780AB013-3FC6-427d-B829-576C7339F5F1"
0xb6f4  call     instance void [mscorlib]System.Guid::.ctor(string)
0xb6f9  dup
0xb6fa  ldarg.1
0xb6fb  ldarg.0
0xb6fc  ldc.i4.s 0x15
0xb6fe  callvirt instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ICondition Microsoft.Crm.Tools.Admin.IGetSqlServerValidators::GetValidators(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, valuetype Microsoft.Crm.Tools.Admin.SqlValidators typeCode)
0xb703  ldloc.2
0xb704  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionDescriptorCollection::Add(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ICondition, valuetype [mscorlib]System.Guid)
0xb709  dup
0xb70a  ldarg.1
0xb70b  ldarg.0
0xb70c  ldc.i4.s 0x16
0xb70e  callvirt instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ICondition Microsoft.Crm.Tools.Admin.IGetSqlServerValidators::GetValidators(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, valuetype Microsoft.Crm.Tools.Admin.SqlValidators typeCode)
0xb713  ldloc.0
0xb714  ldloc.2
0xb715  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionDescriptorCollection::Add(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ICondition, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb71a  dup
0xb71b  ldarg.1
0xb71c  ldarg.0
0xb71d  ldc.i4.s 0x17
0xb71f  callvirt instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ICondition Microsoft.Crm.Tools.Admin.IGetSqlServerValidators::GetValidators(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, valuetype Microsoft.Crm.Tools.Admin.SqlValidators typeCode)
0xb724  ldloc.1
0xb725  ldloc.0
0xb726  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionDescriptorCollection::Add(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ICondition, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb72b  dup
0xb72c  ldarg.1
0xb72d  ldarg.0
0xb72e  ldc.i4.s 0x18
0xb730  callvirt instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ICondition Microsoft.Crm.Tools.Admin.IGetSqlServerValidators::GetValidators(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, valuetype Microsoft.Crm.Tools.Admin.SqlValidators typeCode)
0xb735  ldstr    aE195606f7be749// "E195606F-7BE7-49dc-9BFB-ADC4F144C79D"
0xb73a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb73f  ldloc.1
0xb740  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionDescriptorCollection::Add(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ICondition, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb745  dup
0xb746  ldarg.1
0xb747  ldarg.0
0xb748  ldc.i4.s 0x19
0xb74a  callvirt instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ICondition Microsoft.Crm.Tools.Admin.IGetSqlServerValidators::GetValidators(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, valuetype Microsoft.Crm.Tools.Admin.SqlValidators typeCode)
0xb74f  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationOperationChecksFactory::SqlSysAdminValidatorId
0xb754  ldstr    aE195606f7be749// "E195606F-7BE7-49dc-9BFB-ADC4F144C79D"
0xb759  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb75e  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionDescriptorCollection::Add(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ICondition, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb763  dup
0xb764  ldarg.1
0xb765  ldarg.0
0xb766  ldc.i4.1
0xb767  callvirt instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ICondition Microsoft.Crm.Tools.Admin.IGetSqlServerValidators::GetValidators(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, valuetype Microsoft.Crm.Tools.Admin.SqlValidators typeCode)
0xb76c  ldstr    a025723411c8947// "02572341-1C89-47A8-88FE-5F0432D5C16A"
0xb771  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb776  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationOperationChecksFactory::SqlSysAdminValidatorId
0xb77b  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionDescriptorCollection::Add(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ICondition, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb780  dup
0xb781  ldarg.0
0xb782  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0xb787  newobj   instance void Microsoft.Crm.Tools.Admin.WordBreakerValidator::.ctor(class [mscorlib]System.Collections.IDictionary instanceData)
0xb78c  ldstr    a16d746e901e24a// "16d746e9-01e2-4a35-b3aa-3651f34387b4"
0xb791  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb796  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationOperationChecksFactory::SqlSysAdminValidatorId
0xb79b  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionDescriptorCollection::Add(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ICondition, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb7a0  dup
0xb7a1  newobj   instance void Microsoft.Crm.Tools.Admin.FullTextInstalledValidator::.ctor()
0xb7a6  ldstr    a34860d505d134b// "34860D50-5D13-4b55-932C-5B51B9E2A6F5"
0xb7ab  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb7b0  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationOperationChecksFactory::SqlSysAdminValidatorId
0xb7b5  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionDescriptorCollection::Add(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ICondition, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb7ba  dup
0xb7bb  ldarg.2
0xb7bc  newobj   instance void Microsoft.Crm.Tools.Admin.FullTextRunningValidator::.ctor(class Microsoft.Crm.Tools.Admin.IServiceRunningValidator serviceRunningValidator)
0xb7c1  ldstr    a50eb5e059b334b// "50EB5E05-9B33-4bc3-A2B6-3863025C118B"
0xb7c6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb7cb  ldstr    a34860d505d134b// "34860D50-5D13-4b55-932C-5B51B9E2A6F5"
0xb7d0  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb7d5  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionDescriptorCollection::Add(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ICondition, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb7da  ret
```
