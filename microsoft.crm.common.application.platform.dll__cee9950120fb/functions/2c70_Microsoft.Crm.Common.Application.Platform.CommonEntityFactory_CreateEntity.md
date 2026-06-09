# Microsoft.Crm.Common.Application.Platform.CommonEntityFactory::CreateEntity

- ea: `0x2c70`
- end: `0x2f2b`
- name: `Microsoft.Crm.Common.Application.Platform.CommonEntityFactory::CreateEntity`
- size: `699`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x2c50`
- `0x2c70`
- `0x2f40`
- `0x31a0`
- `0x3fd0`
- `0x4160`
- `0x4270`
- `0x46a0`
- `0x46c0`
- `0x4750`
- `0x4780`
- `0x4a60`
- `0x4a90`
- `0x4ad0`
- `0x4b40`
- `0x4b60`
- `0x72c0`

## string_xrefs

- `0x2e91`: `template`

## pseudocode

```c

```

## disassembly

```asm
0x2c70  ldarg.0
0x2c71  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x2c76  stloc.0
0x2c77  ldloc.0
0x2c78  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x2c7d  stloc.1
0x2c7e  ldloc.1
0x2c7f  ldc.i4   0xA112A88F
0x2c84  bgt.un.s loc_2CF2
0x2c86  ldloc.1
0x2c87  ldc.i4   0x694AAA0B
0x2c8c  bgt.un.s loc_2CB4
0x2c8e  ldloc.1
0x2c8f  ldc.i4   0x964BC5D
0x2c94  beq      loc_2DC7
0x2c99  ldloc.1
0x2c9a  ldc.i4   0xCFB5881
0x2c9f  beq      loc_2DDC
0x2ca4  ldloc.1
0x2ca5  ldc.i4   0x694AAA0B
0x2caa  beq      loc_2E90
0x2caf  br       loc_2F08
0x2cb4  ldloc.1
0x2cb5  ldc.i4   0x82EBAD3A
0x2cba  bgt.un.s loc_2CD7
0x2cbc  ldloc.1
0x2cbd  ldc.i4   0x79C5E711
0x2cc2  beq      loc_2E1B
0x2cc7  ldloc.1
0x2cc8  ldc.i4   0x82EBAD3A
0x2ccd  beq      loc_2D73
0x2cd2  br       loc_2F08
0x2cd7  ldloc.1
0x2cd8  ldc.i4   0x8A8753C7
0x2cdd  beq      loc_2D9D
0x2ce2  ldloc.1
0x2ce3  ldc.i4   0xA112A88F
0x2ce8  beq      loc_2E6F
0x2ced  br       loc_2F08
0x2cf2  ldloc.1
0x2cf3  ldc.i4   0xE548412C
0x2cf8  bgt.un.s loc_2D38
0x2cfa  ldloc.1
0x2cfb  ldc.i4   0xD470ED47
0x2d00  bgt.un.s loc_2D1D
0x2d02  ldloc.1
0x2d03  ldc.i4   0xB2F80A30
0x2d08  beq      loc_2DB2
0x2d0d  ldloc.1
0x2d0e  ldc.i4   0xD470ED47
0x2d13  beq      loc_2E45
0x2d18  br       loc_2F08
0x2d1d  ldloc.1
0x2d1e  ldc.i4   0xD6FABDD3
0x2d23  beq      loc_2E5A
0x2d28  ldloc.1
0x2d29  ldc.i4   0xE548412C
0x2d2e  beq      loc_2E06
0x2d33  br       loc_2F08
0x2d38  ldloc.1
0x2d39  ldc.i4   0xF4DFB8B8
0x2d3e  bgt.un.s loc_2D5B
0x2d40  ldloc.1
0x2d41  ldc.i4   0xF448886C
0x2d46  beq      loc_2E81
0x2d4b  ldloc.1
0x2d4c  ldc.i4   0xF4DFB8B8
0x2d51  beq      loc_2E30
0x2d56  br       loc_2F08
0x2d5b  ldloc.1
0x2d5c  ldc.i4   0xF8963A7F
0x2d61  beq      loc_2DF1
0x2d66  ldloc.1
0x2d67  ldc.i4   0xFD571550
0x2d6c  beq.s    loc_2D88
0x2d6e  br       loc_2F08
0x2d73  ldloc.0
0x2d74  ldstr    aAppointment// "appointment"
0x2d79  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d7e  brtrue   loc_2E9F
0x2d83  br       loc_2F08
0x2d88  ldloc.0
0x2d89  ldstr    aDuplicaterule// "duplicaterule"
0x2d8e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d93  brtrue   loc_2EA6
0x2d98  br       loc_2F08
0x2d9d  ldloc.0
0x2d9e  ldstr    aEmail// "email"
0x2da3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2da8  brtrue   loc_2EAD
0x2dad  br       loc_2F08
0x2db2  ldloc.0
0x2db3  ldstr    aFax// "fax"
0x2db8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dbd  brtrue   loc_2EB4
0x2dc2  br       loc_2F08
0x2dc7  ldloc.0
0x2dc8  ldstr    aLetter// "letter"
0x2dcd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dd2  brtrue   loc_2EBB
0x2dd7  br       loc_2F08
0x2ddc  ldloc.0
0x2ddd  ldstr    aList// "list"
0x2de2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2de7  brtrue   loc_2EC2
0x2dec  br       loc_2F08
0x2df1  ldloc.0
0x2df2  ldstr    aPhonecall// "phonecall"
0x2df7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dfc  brtrue   loc_2EC9
0x2e01  br       loc_2F08
0x2e06  ldloc.0
0x2e07  ldstr    aProduct// "product"
0x2e0c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e11  brtrue   loc_2ED0
0x2e16  br       loc_2F08
0x2e1b  ldloc.0
0x2e1c  ldstr    aProductpricele// "productpricelevel"
0x2e21  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e26  brtrue   loc_2ED7
0x2e2b  br       loc_2F08
0x2e30  ldloc.0
0x2e31  ldstr    aQueue// "queue"
0x2e36  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e3b  brtrue   loc_2EDE
0x2e40  br       loc_2F08
0x2e45  ldloc.0
0x2e46  ldstr    aQueueitem// "queueitem"
0x2e4b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e50  brtrue   loc_2EE5
0x2e55  br       loc_2F08
0x2e5a  ldloc.0
0x2e5b  ldstr    aRecurringappoi// "recurringappointmentmaster"
0x2e60  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e65  brtrue   loc_2EEC
0x2e6a  br       loc_2F08
0x2e6f  ldloc.0
0x2e70  ldstr    aSocialactivity// "socialactivity"
0x2e75  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e7a  brtrue.s loc_2EF3
0x2e7c  br       loc_2F08
0x2e81  ldloc.0
0x2e82  ldstr    aTask// "task"
0x2e87  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e8c  brtrue.s loc_2EFA
0x2e8e  br.s     loc_2F08
0x2e90  ldloc.0
0x2e91  ldstr    aTemplate// "template"
0x2e96  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2e9b  brtrue.s loc_2F01
0x2e9d  br.s     loc_2F08
0x2e9f  ldarg.0
0x2ea0  newobj   instance void Microsoft.Crm.Common.Application.Platform.Appointment::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x2ea5  ret
0x2ea6  ldarg.0
0x2ea7  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DuplicateRule::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x2eac  ret
0x2ead  ldarg.0
0x2eae  newobj   instance void Microsoft.Crm.Common.Application.Platform.Email::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x2eb3  ret
0x2eb4  ldarg.0
0x2eb5  newobj   instance void Microsoft.Crm.Common.Application.Platform.Fax::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x2eba  ret
0x2ebb  ldarg.0
0x2ebc  newobj   instance void Microsoft.Crm.Common.Application.Platform.Letter::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x2ec1  ret
0x2ec2  ldarg.0
0x2ec3  newobj   instance void Microsoft.Crm.Common.Application.Platform.List::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x2ec8  ret
0x2ec9  ldarg.0
0x2eca  newobj   instance void Microsoft.Crm.Common.Application.Platform.PhoneCall::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x2ecf  ret
0x2ed0  ldarg.0
0x2ed1  newobj   instance void Microsoft.Crm.Common.Application.Platform.Product::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x2ed6  ret
0x2ed7  ldarg.0
0x2ed8  newobj   instance void Microsoft.Crm.Common.Application.Platform.ProductPriceLevel::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x2edd  ret
0x2ede  ldarg.0
0x2edf  newobj   instance void Microsoft.Crm.Common.Application.Platform.Queue::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x2ee4  ret
0x2ee5  ldarg.0
0x2ee6  newobj   instance void Microsoft.Crm.Common.Application.Platform.QueueItem::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x2eeb  ret
0x2eec  ldarg.0
0x2eed  newobj   instance void Microsoft.Crm.Common.Application.Platform.RecurringAppointmentMaster::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x2ef2  ret
0x2ef3  ldarg.0
0x2ef4  newobj   instance void Microsoft.Crm.Common.Application.Platform.SocialActivity::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x2ef9  ret
0x2efa  ldarg.0
0x2efb  newobj   instance void Microsoft.Crm.Common.Application.Platform.Task::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x2f00  ret
0x2f01  ldarg.0
0x2f02  newobj   instance void Microsoft.Crm.Common.Application.Platform.Template::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType type)
0x2f07  ret
0x2f08  ldarg.0
0x2f09  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x2f0e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x2f13  brfalse.s loc_2F29
0x2f15  ldarg.0
0x2f16  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x2f1b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x2f20  brfalse.s loc_2F29
0x2f22  ldarg.0
0x2f23  newobj   instance void Microsoft.Crm.Common.Application.Platform.CustomActivity::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType entityType)
0x2f28  ret
0x2f29  ldnull
0x2f2a  ret
```
