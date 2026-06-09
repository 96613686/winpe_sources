# <>c__DisplayClass2_1::<SelectEvents>b__2

- ea: `0x16b90`
- end: `0x16fce`
- name: `<>c__DisplayClass2_1::<SelectEvents>b__2`
- size: `1086`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x220`
- `0x2730`
- `0x2af0`
- `0x2c00`
- `0x33a0`
- `0x4430`
- `0x4460`
- `0x44c0`
- `0xd5a0`
- `0xe180`
- `0x10900`
- `0x10b50`
- `0x11590`
- `0x16b90`

## string_xrefs

- `0x16f8d`: `AsyncOperationDataAccess.SelectEvent`

## pseudocode

```c

```

## disassembly

```asm
0x16b90  ldarg.0
0x16b91  ldfld    object[] <>c__DisplayClass2_1::values
0x16b96  ldc.i4.s 0x10
0x16b98  ldelem.ref
0x16b99  unbox.any [mscorlib]System.Guid
0x16b9e  ldarg.0
0x16b9f  ldfld    object[] <>c__DisplayClass2_1::values
0x16ba4  ldc.i4.s 0x12
0x16ba6  ldelem.ref
0x16ba7  unbox.any [mscorlib]System.Int32
0x16bac  ldarg.0
0x16bad  ldfld    object[] <>c__DisplayClass2_1::values
0x16bb2  ldc.i4.s 0x11
0x16bb4  ldelem.ref
0x16bb5  unbox.any [mscorlib]System.DateTime
0x16bba  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime)
0x16bbf  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken::.ctor(valuetype [mscorlib]System.Guid, int32, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0x16bc4  stloc.0
0x16bc5  ldloc.0
0x16bc6  ldarg.0
0x16bc7  ldfld    object[] <>c__DisplayClass2_1::values
0x16bcc  ldc.i4.0
0x16bcd  ldelem.ref
0x16bce  unbox.any [mscorlib]System.Guid
0x16bd3  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken::set_TransactionContextId(valuetype [mscorlib]System.Guid)
0x16bd8  ldarg.0
0x16bd9  ldfld    object[] <>c__DisplayClass2_1::values
0x16bde  ldlen
0x16bdf  conv.i4
0x16be0  ldc.i4.s 0x1A
0x16be2  ble.s    loc_16C08
0x16be4  ldarg.0
0x16be5  ldfld    object[] <>c__DisplayClass2_1::values
0x16bea  ldc.i4.s 0x1A
0x16bec  ldelem.ref
0x16bed  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x16bf2  beq.s    loc_16C08
0x16bf4  ldloc.0
0x16bf5  ldarg.0
0x16bf6  ldfld    object[] <>c__DisplayClass2_1::values
0x16bfb  ldc.i4.s 0x1A
0x16bfd  ldelem.ref
0x16bfe  unbox.any [mscorlib]System.Guid
0x16c03  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken::set_ParentPluginExecutionId(valuetype [mscorlib]System.Guid)
0x16c08  ldnull
0x16c09  stloc.1
0x16c0a  ldarg.0
0x16c0b  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16c10  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16c15  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x16c1a  ldarg.0
0x16c1b  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16c20  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16c25  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x16c2a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x16c2f  ldarg.0
0x16c30  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16c35  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16c3a  ldarg.0
0x16c3b  ldfld    object[] <>c__DisplayClass2_1::values
0x16c40  ldc.i4.7
0x16c41  ldelem.ref
0x16c42  call     T0x2B000037
0x16c47  ldarg.0
0x16c48  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16c4d  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16c52  ldarg.0
0x16c53  ldfld    object[] <>c__DisplayClass2_1::values
0x16c58  ldc.i4.4
0x16c59  ldelem.ref
0x16c5a  call     T0x2B000037
0x16c5f  ldarg.0
0x16c60  ldfld    object[] <>c__DisplayClass2_1::values
0x16c65  ldc.i4.0
0x16c66  ldelem.ref
0x16c67  unbox.any [mscorlib]System.Guid
0x16c6c  ldarg.0
0x16c6d  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16c72  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16c77  ldarg.0
0x16c78  ldfld    object[] <>c__DisplayClass2_1::values
0x16c7d  ldc.i4.1
0x16c7e  ldelem.ref
0x16c7f  call     T0x2B000038
0x16c84  ldarg.0
0x16c85  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16c8a  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16c8f  ldarg.0
0x16c90  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16c95  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16c9a  ldarg.0
0x16c9b  ldfld    object[] <>c__DisplayClass2_1::values
0x16ca0  ldc.i4.2
0x16ca1  ldelem.ref
0x16ca2  call     T0x2B000036
0x16ca7  call     instance string Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::DecompressData(string data)
0x16cac  ldarg.0
0x16cad  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16cb2  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16cb7  ldarg.0
0x16cb8  ldfld    object[] <>c__DisplayClass2_1::values
0x16cbd  ldc.i4.3
0x16cbe  ldelem.ref
0x16cbf  call     T0x2B000036
0x16cc4  ldarg.0
0x16cc5  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16cca  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16ccf  ldarg.0
0x16cd0  ldfld    object[] <>c__DisplayClass2_1::values
0x16cd5  ldc.i4.4
0x16cd6  ldelem.ref
0x16cd7  ldarg.0
0x16cd8  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16cdd  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16ce2  ldarg.0
0x16ce3  ldfld    object[] <>c__DisplayClass2_1::values
0x16ce8  ldc.i4.5
0x16ce9  ldelem.ref
0x16cea  call     T0x2B000036
0x16cef  ldarg.0
0x16cf0  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16cf5  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16cfa  ldarg.0
0x16cfb  ldfld    object[] <>c__DisplayClass2_1::values
0x16d00  ldc.i4.6
0x16d01  ldelem.ref
0x16d02  call     T0x2B000038
0x16d07  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetLookup(object objectId, string objectIdName, int32 objectTypeCode)
0x16d0c  ldarg.0
0x16d0d  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16d12  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16d17  ldarg.0
0x16d18  ldfld    object[] <>c__DisplayClass2_1::values
0x16d1d  ldc.i4.8
0x16d1e  ldelem.ref
0x16d1f  ldarg.0
0x16d20  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16d25  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16d2a  ldarg.0
0x16d2b  ldfld    object[] <>c__DisplayClass2_1::values
0x16d30  ldc.i4.s 9
0x16d32  ldelem.ref
0x16d33  call     T0x2B000036
0x16d38  ldarg.0
0x16d39  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16d3e  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16d43  ldarg.0
0x16d44  ldfld    object[] <>c__DisplayClass2_1::values
0x16d49  ldc.i4.s 0xA
0x16d4b  ldelem.ref
0x16d4c  call     T0x2B000038
0x16d51  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetLookup(object objectId, string objectIdName, int32 objectTypeCode)
0x16d56  ldarg.0
0x16d57  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16d5c  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16d61  ldarg.0
0x16d62  ldfld    object[] <>c__DisplayClass2_1::values
0x16d67  ldc.i4.s 0x13
0x16d69  ldelem.ref
0x16d6a  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetEntityNameReference(object primaryEntityType)
0x16d6f  ldarg.0
0x16d70  ldfld    object[] <>c__DisplayClass2_1::values
0x16d75  ldc.i4.s 0xB
0x16d77  ldelem.ref
0x16d78  unbox.any [mscorlib]System.Guid
0x16d7d  ldarg.0
0x16d7e  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16d83  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16d88  ldarg.0
0x16d89  ldfld    object[] <>c__DisplayClass2_1::values
0x16d8e  ldc.i4.s 0xC
0x16d90  ldelem.ref
0x16d91  call     T0x2B000038
0x16d96  ldarg.0
0x16d97  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16d9c  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16da1  ldarg.0
0x16da2  ldfld    object[] <>c__DisplayClass2_1::values
0x16da7  ldc.i4.s 0xD
0x16da9  ldelem.ref
0x16daa  call     T0x2B000036
0x16daf  ldarg.0
0x16db0  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16db5  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16dba  ldarg.0
0x16dbb  ldfld    object[] <>c__DisplayClass2_1::values
0x16dc0  ldc.i4.s 0xE
0x16dc2  ldelem.ref
0x16dc3  call     T0x2B000036
0x16dc8  ldarg.0
0x16dc9  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16dce  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16dd3  ldarg.0
0x16dd4  ldfld    object[] <>c__DisplayClass2_1::values
0x16dd9  ldc.i4.s 0xF
0x16ddb  ldelem.ref
0x16ddc  call     T0x2B000039
0x16de1  ldarg.0
0x16de2  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16de7  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16dec  ldarg.0
0x16ded  ldfld    object[] <>c__DisplayClass2_1::values
0x16df2  ldc.i4.s 0x15
0x16df4  ldelem.ref
0x16df5  call     T0x2B000039
0x16dfa  ldarg.0
0x16dfb  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16e00  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16e05  ldarg.0
0x16e06  ldfld    object[] <>c__DisplayClass2_1::values
0x16e0b  ldc.i4.s 0x16
0x16e0d  ldelem.ref
0x16e0e  call     T0x2B000039
0x16e13  ldarg.0
0x16e14  ldfld    object[] <>c__DisplayClass2_1::values
0x16e19  ldc.i4.s 0x18
0x16e1b  ldelem.ref
0x16e1c  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x16e21  beq.s    loc_16E33
0x16e23  ldarg.0
0x16e24  ldfld    object[] <>c__DisplayClass2_1::values
0x16e29  ldc.i4.s 0x18
0x16e2b  ldelem.ref
0x16e2c  unbox.any [mscorlib]System.DateTime
0x16e31  br.s     loc_16E38
0x16e33  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x16e38  ldloc.0
0x16e39  ldarg.0
0x16e3a  ldfld    object[] <>c__DisplayClass2_1::values
0x16e3f  ldc.i4.s 0x14
0x16e41  ldelem.ref
0x16e42  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x16e47  beq.s    loc_16E5E
0x16e49  ldarg.0
0x16e4a  ldfld    object[] <>c__DisplayClass2_1::values
0x16e4f  ldc.i4.s 0x14
0x16e51  ldelem.ref
0x16e52  unbox.any [mscorlib]System.Guid
0x16e57  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x16e5c  br.s     loc_16E67
0x16e5e  ldloca.s 3
0x16e60  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x16e66  ldloc.3
0x16e67  ldarg.0
0x16e68  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16e6d  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16e72  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x16e77  ldarg.0
0x16e78  ldfld    object[] <>c__DisplayClass2_1::values
0x16e7d  ldlen
0x16e7e  conv.i4
0x16e7f  ldc.i4.s 0x19
0x16e81  bgt.s    loc_16E86
0x16e83  ldc.i4.1
0x16e84  br.s     loc_16EA7
0x16e86  ldarg.0
0x16e87  ldfld    object[] <>c__DisplayClass2_1::values
0x16e8c  ldc.i4.s 0x19
0x16e8e  ldelem.ref
0x16e8f  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x16e94  beq.s    loc_16EA6
0x16e96  ldarg.0
0x16e97  ldfld    object[] <>c__DisplayClass2_1::values
0x16e9c  ldc.i4.s 0x19
0x16e9e  ldelem.ref
0x16e9f  unbox.any [mscorlib]System.Int32
0x16ea4  br.s     loc_16EA7
0x16ea6  ldc.i4.1
0x16ea7  ldnull
0x16ea8  ldarg.0
0x16ea9  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16eae  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16eb3  ldarg.0
0x16eb4  ldfld    object[] <>c__DisplayClass2_1::values
0x16eb9  ldc.i4.s 0x12
0x16ebb  ldelem.ref
0x16ebc  call     T0x2B000038
0x16ec1  ldarg.0
0x16ec2  ldfld    class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext <>c__DisplayClass2_1::rootExecutionContext
0x16ec7  newobj   instance void Microsoft.Crm.Asynchronous.AsyncEvent::.ctor(class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase queueManager, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid primaryEntityId, valuetype [mscorlib]System.Guid id, int32 operationType, string data, string dependencyToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup regardingObject, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup owningExtension, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference primaryEntity, valuetype [mscorlib]System.Guid ownerId, int32 retryCount, string messageName, string recurrencePattern, valuetype [mscorlib]System.DateTime recurrenceStartTime, valuetype [mscorlib]System.DateTime createdOn, valuetype [mscorlib]System.DateTime modifiedOn, valuetype [mscorlib]System.DateTime postponeUntil, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> requestId, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration, int32 subtype, string jobParameters, [opt] int32 depth, [opt] class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext rootExecutionContext)
0x16ecc  stloc.1
0x16ecd  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncXrmLogger [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncXrmLogger::get_Instance()
0x16ed2  ldloc.1
0x16ed3  call     class Microsoft.Crm.Asynchronous.AsyncEventAdapter Microsoft.Crm.Asynchronous.AsyncEventAdapter::Create(class Microsoft.Crm.Asynchronous.AsyncEvent instance)
0x16ed8  ldarg.0
0x16ed9  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x16ede  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x16ee3  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x16ee8  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x16eed  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncXrmLogger::GetCustomProperties(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IAsyncExecutionUnit, string)
0x16ef2  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x16ef7  leave    loc_16F99
0x16efc  stloc.s  4
0x16efe  ldarg.0
0x16eff  ldfld    object[] <>c__DisplayClass2_1::values
0x16f04  ldc.i4.0
0x16f05  ldelem.ref
0x16f06  unbox.any [mscorlib]System.Guid
0x16f0b  stloc.s  5
0x16f0d  ldarg.0
  ... truncated ...
```
