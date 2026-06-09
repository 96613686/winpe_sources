# Microsoft.Crm.Asynchronous.BootstrapRollupOperation::Initialize

- ea: `0xbd10`
- end: `0xbe84`
- name: `Microsoft.Crm.Asynchronous.BootstrapRollupOperation::Initialize`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x16bb0`

## callees

- `0xba30`
- `0xba40`
- `0xba50`
- `0xba60`
- `0xba80`
- `0xba90`
- `0xbaa0`
- `0xbab0`
- `0xbac0`
- `0xbad0`
- `0xbae0`
- `0xbb00`
- `0xbb20`
- `0xbb40`
- `0xbc60`
- `0xbc70`
- `0xbc80`
- `0xbc90`
- `0xbd10`
- `0xe870`
- `0xf7b0`
- `0xfd90`

## string_xrefs

- `0xbe03`: `RollupPropertiesId`

## pseudocode

```c

```

## disassembly

```asm
0xbd10  ldarg.0
0xbd11  ldarg.1
0xbd12  call     instance void Microsoft.Crm.Asynchronous.BootstrapRollupOperation::set_AsyncEvent(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent value)
0xbd17  ldarg.0
0xbd18  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.BootstrapRollupOperation::get_AsyncEvent()
0xbd1d  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0xbd22  ldloca.s 0
0xbd24  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0xbd29  brfalse.s loc_BD34
0xbd2b  ldarg.0
0xbd2c  ldloc.0
0xbd2d  call     instance void Microsoft.Crm.Asynchronous.BootstrapRollupOperation::set_RollupPropertiesId(valuetype [mscorlib]System.Guid value)
0xbd32  br.s     loc_BD3F
0xbd34  ldstr    aThisAsyncevent// "this.AsyncEvent.Data does not have Guid"...
0xbd39  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xbd3e  throw
0xbd3f  ldarg.0
0xbd40  ldarg.0
0xbd41  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xbd46  ldarg.0
0xbd47  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BootstrapRollupOperation::get_RollupPropertiesId()
0xbd4c  newobj   instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration, valuetype [mscorlib]System.Guid rollupPropertiesId)
0xbd51  call     instance void Microsoft.Crm.Asynchronous.BootstrapRollupOperation::set_DataAccess(class Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess value)
0xbd56  ldarg.0
0xbd57  call     instance class Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess Microsoft.Crm.Asynchronous.BootstrapRollupOperation::get_DataAccess()
0xbd5c  ldarg.0
0xbd5d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BootstrapRollupOperation::get_RollupPropertiesId()
0xbd62  callvirt instance class [mscorlib]System.Tuple`6<valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<bool>, string, int32, valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess::GetBootstrapInformation(valuetype [mscorlib]System.Guid rollupPropertiesId)
0xbd67  stloc.1
0xbd68  ldarg.0
0xbd69  ldloc.1
0xbd6a  callvirt instance var<u1> class [mscorlib]System.Tuple`6<valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<bool>, string, int32, valuetype [mscorlib]System.Guid>::get_Item1()
0xbd6f  stloc.2
0xbd70  ldloca.s 2
0xbd72  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xbd77  brtrue.s loc_BD7C
0xbd79  ldc.i4.1
0xbd7a  br.s     loc_BD83
0xbd7c  ldloca.s 2
0xbd7e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0xbd83  call     instance void Microsoft.Crm.Asynchronous.BootstrapRollupOperation::set_StepNumber(int32 value)
0xbd88  ldarg.0
0xbd89  ldloc.1
0xbd8a  callvirt instance var<u1> class [mscorlib]System.Tuple`6<valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<bool>, string, int32, valuetype [mscorlib]System.Guid>::get_Item2()
0xbd8f  stloc.2
0xbd90  ldloca.s 2
0xbd92  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xbd97  brtrue.s loc_BD9C
0xbd99  ldc.i4.0
0xbd9a  br.s     loc_BDA3
0xbd9c  ldloca.s 2
0xbd9e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0xbda3  call     instance void Microsoft.Crm.Asynchronous.BootstrapRollupOperation::set_RetryCount(int32 value)
0xbda8  ldarg.0
0xbda9  ldloc.1
0xbdaa  callvirt instance var<u1> class [mscorlib]System.Tuple`6<valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<bool>, string, int32, valuetype [mscorlib]System.Guid>::get_Item3()
0xbdaf  stloc.3
0xbdb0  ldloca.s 3
0xbdb2  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xbdb7  brtrue.s loc_BDBC
0xbdb9  ldc.i4.0
0xbdba  br.s     loc_BDC3
0xbdbc  ldloca.s 3
0xbdbe  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0xbdc3  call     instance void Microsoft.Crm.Asynchronous.BootstrapRollupOperation::set_UseHierarchies(bool value)
0xbdc8  ldarg.0
0xbdc9  ldloc.1
0xbdca  callvirt instance var<u1> class [mscorlib]System.Tuple`6<valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<bool>, string, int32, valuetype [mscorlib]System.Guid>::get_Item4()
0xbdcf  call     instance void Microsoft.Crm.Asynchronous.BootstrapRollupOperation::set_SourceEntityLogicalName(string value)
0xbdd4  ldarg.0
0xbdd5  ldloc.1
0xbdd6  callvirt instance var<u1> class [mscorlib]System.Tuple`6<valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<bool>, string, int32, valuetype [mscorlib]System.Guid>::get_Item5()
0xbddb  call     instance void Microsoft.Crm.Asynchronous.BootstrapRollupOperation::set_InitialValueCalculationStatus(int32 value)
0xbde0  ldarg.0
0xbde1  ldloc.1
0xbde2  callvirt instance var<u1> class [mscorlib]System.Tuple`6<valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<bool>, string, int32, valuetype [mscorlib]System.Guid>::get_Item6()
0xbde7  call     instance void Microsoft.Crm.Asynchronous.BootstrapRollupOperation::set_BootstrapRollupAsyncJobId(valuetype [mscorlib]System.Guid value)
0xbdec  ldarg.0
0xbded  ldarg.0
0xbdee  newobj   instance void Microsoft.Crm.Asynchronous.Rollups.Bootstrap.StepFactory::.ctor(class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation bootstrapProcess)
0xbdf3  call     instance void Microsoft.Crm.Asynchronous.BootstrapRollupOperation::set_StepFactory(class Microsoft.Crm.Asynchronous.Rollups.Bootstrap.StepFactory value)
0xbdf8  ldarg.0
0xbdf9  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xbdfe  call     instance void Microsoft.Crm.Asynchronous.BootstrapRollupOperation::set_InitialStartTime(valuetype [mscorlib]System.DateTime value)
0xbe03  ldstr    aRollupproperti// "RollupPropertiesId"
0xbe08  ldarg.0
0xbe09  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BootstrapRollupOperation::get_RollupPropertiesId()
0xbe0e  stloc.s  4
0xbe10  ldloca.s 4
0xbe12  constrained. [mscorlib]System.Guid
0xbe18  callvirt instance string [mscorlib]System.Object::ToString()
0xbe1d  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperty(string, string)
0xbe22  ldstr    aUsehierarchies// "UseHierarchies"
0xbe27  ldarg.0
0xbe28  call     instance bool Microsoft.Crm.Asynchronous.BootstrapRollupOperation::get_UseHierarchies()
0xbe2d  stloc.s  5
0xbe2f  ldloca.s 5
0xbe31  call     instance string [mscorlib]System.Boolean::ToString()
0xbe36  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperty(string, string)
0xbe3b  ldstr    aSourceentitylo// "SourceEntityLogicalName"
0xbe40  ldarg.0
0xbe41  call     instance string Microsoft.Crm.Asynchronous.BootstrapRollupOperation::get_SourceEntityLogicalName()
0xbe46  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperty(string, string)
0xbe4b  ldstr    aInitialvalueca// "InitialValueCalculationStatus"
0xbe50  ldarg.0
0xbe51  call     instance int32 Microsoft.Crm.Asynchronous.BootstrapRollupOperation::get_InitialValueCalculationStatus()
0xbe56  stloc.s  6
0xbe58  ldloca.s 6
0xbe5a  call     instance string [mscorlib]System.Int32::ToString()
0xbe5f  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperty(string, string)
0xbe64  ldstr    aBootstraprollu// "BootstrapRollupAsyncJobId"
0xbe69  ldarg.0
0xbe6a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BootstrapRollupOperation::get_BootstrapRollupAsyncJobId()
0xbe6f  stloc.s  4
0xbe71  ldloca.s 4
0xbe73  constrained. [mscorlib]System.Guid
0xbe79  callvirt instance string [mscorlib]System.Object::ToString()
0xbe7e  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperty(string, string)
0xbe83  ret
```
