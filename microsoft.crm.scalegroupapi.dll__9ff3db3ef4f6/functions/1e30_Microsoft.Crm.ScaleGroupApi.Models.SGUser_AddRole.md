# Microsoft.Crm.ScaleGroupApi.Models.SGUser::AddRole

- ea: `0x1e30`
- end: `0x1f6b`
- name: `Microsoft.Crm.ScaleGroupApi.Models.SGUser::AddRole`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x4b60`

## callees

- `0x1c60`
- `0x1c80`
- `0x1ca0`
- `0x1cc0`
- `0x1ce0`
- `0x1d00`
- `0x1d20`
- `0x1d40`
- `0x1d60`
- `0x1d80`
- `0x1da0`
- `0x1dc0`
- `0x1de0`
- `0x1e00`
- `0x1e20`
- `0x1e30`

## pseudocode

```c

```

## disassembly

```asm
0x1e30  ldarg.1
0x1e31  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUser::BizMgr
0x1e36  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1e3b  brfalse.s loc_1E45
0x1e3d  ldarg.0
0x1e3e  ldc.i4.1
0x1e3f  call     instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_HasCeoBusinessManagerRole(bool value)
0x1e44  ret
0x1e45  ldarg.1
0x1e46  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUser::CSRMgr
0x1e4b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1e50  brfalse.s loc_1E5A
0x1e52  ldarg.0
0x1e53  ldc.i4.1
0x1e54  call     instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_HasCsrManagerRole(bool value)
0x1e59  ret
0x1e5a  ldarg.1
0x1e5b  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUser::CSR
0x1e60  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1e65  brfalse.s loc_1E6F
0x1e67  ldarg.0
0x1e68  ldc.i4.1
0x1e69  call     instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_HasCustomerServiceRepresentativeRole(bool value)
0x1e6e  ret
0x1e6f  ldarg.1
0x1e70  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUser::Proxy
0x1e75  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1e7a  brfalse.s loc_1E84
0x1e7c  ldarg.0
0x1e7d  ldc.i4.1
0x1e7e  call     instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_HasDelegateRole(bool value)
0x1e83  ret
0x1e84  ldarg.1
0x1e85  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUser::MarketingMgr
0x1e8a  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1e8f  brfalse.s loc_1E99
0x1e91  ldarg.0
0x1e92  ldc.i4.1
0x1e93  call     instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_HasMarketingManagerRole(bool value)
0x1e98  ret
0x1e99  ldarg.1
0x1e9a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUser::MarketingProfessional
0x1e9f  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1ea4  brfalse.s loc_1EAE
0x1ea6  ldarg.0
0x1ea7  ldc.i4.1
0x1ea8  call     instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_HasMarketingProfessionalRole(bool value)
0x1ead  ret
0x1eae  ldarg.1
0x1eaf  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUser::SalesMgr
0x1eb4  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1eb9  brfalse.s loc_1EC3
0x1ebb  ldarg.0
0x1ebc  ldc.i4.1
0x1ebd  call     instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_HasSalesManagerRole(bool value)
0x1ec2  ret
0x1ec3  ldarg.1
0x1ec4  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUser::SalesRep
0x1ec9  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1ece  brfalse.s loc_1ED8
0x1ed0  ldarg.0
0x1ed1  ldc.i4.1
0x1ed2  call     instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_HasSalespersonRole(bool value)
0x1ed7  ret
0x1ed8  ldarg.1
0x1ed9  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUser::ScheduleMgr
0x1ede  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1ee3  brfalse.s loc_1EED
0x1ee5  ldarg.0
0x1ee6  ldc.i4.1
0x1ee7  call     instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_HasScheduleManagerRole(bool value)
0x1eec  ret
0x1eed  ldarg.1
0x1eee  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUser::Scheduler
0x1ef3  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1ef8  brfalse.s loc_1F02
0x1efa  ldarg.0
0x1efb  ldc.i4.1
0x1efc  call     instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_HasSchedulerRole(bool value)
0x1f01  ret
0x1f02  ldarg.1
0x1f03  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUser::Support
0x1f08  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1f0d  brfalse.s loc_1F17
0x1f0f  ldarg.0
0x1f10  ldc.i4.1
0x1f11  call     instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_HasSupportUserRole(bool value)
0x1f16  ret
0x1f17  ldarg.1
0x1f18  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUser::SystemAdmin
0x1f1d  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1f22  brfalse.s loc_1F2C
0x1f24  ldarg.0
0x1f25  ldc.i4.1
0x1f26  call     instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_HasSystemAdministratorRole(bool value)
0x1f2b  ret
0x1f2c  ldarg.1
0x1f2d  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUser::Customizer
0x1f32  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1f37  brfalse.s loc_1F41
0x1f39  ldarg.0
0x1f3a  ldc.i4.1
0x1f3b  call     instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_HasSystemCustomizerRole(bool value)
0x1f40  ret
0x1f41  ldarg.1
0x1f42  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUser::VPMarketing
0x1f47  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1f4c  brfalse.s loc_1F56
0x1f4e  ldarg.0
0x1f4f  ldc.i4.1
0x1f50  call     instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_HasVicePresidentOfMarketingRole(bool value)
0x1f55  ret
0x1f56  ldarg.1
0x1f57  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUser::VPSales
0x1f5c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1f61  brfalse.s loc_1F6A
0x1f63  ldarg.0
0x1f64  ldc.i4.1
0x1f65  call     instance void Microsoft.Crm.ScaleGroupApi.Models.SGUser::set_HasVicePresidentOfSalesRole(bool value)
0x1f6a  ret
```
