# Microsoft.Crm.WebServices.ImportXmlService::ImportSolutionSkipCapable

- ea: `0xde20`
- end: `0xdfb1`
- name: `Microsoft.Crm.WebServices.ImportXmlService::ImportSolutionSkipCapable`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xde00`

## callees

- `0xde20`
- `0xe130`
- `0xe5e0`
- `0xe6d0`

## pseudocode

```c

```

## disassembly

```asm
0xde20  ldarg.3
0xde21  ldstr    aCustomizationf// "customizationFile"
0xde26  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xde2b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0xde30  stloc.0
0xde31  ldsfld   string [mscorlib]System.String::Empty
0xde36  pop
0xde37  ldsfld   string [mscorlib]System.String::Empty
0xde3c  pop
0xde3d  ldsfld   string [mscorlib]System.String::Empty
0xde42  pop
0xde43  ldarg.0
0xde44  call     instance void Microsoft.Crm.WebServices.ImportXmlService::UpdateImportCounter()
0xde49  ldarg.0
0xde4a  ldarg.s  8
0xde4c  call     instance void Microsoft.Crm.WebServices.ImportXmlService::CheckPrivileges(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xde51  ldarg.s  8
0xde53  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.PlatformMessageDispatcher::.ctor()
0xde58  callvirt instance class [mscorlib]System.IDisposable [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::SwitchMessageDispatcher(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IPlatformMessageDispatcher)
0xde5d  stloc.1
0xde5e  ldarg.1
0xde5f  ldarg.2
0xde60  ldarg.s  7
0xde62  ldarg.3
0xde63  ldarg.s  4
0xde65  ldarg.s  5
0xde67  ldarg.s  8
0xde69  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::.ctor(bool, bool, bool, unsigned int8[], valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xde6e  stloc.2
0xde6f  ldloc.2
0xde70  ldarg.s  6
0xde72  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::set_SkipProductUpdateDependencies(bool)
0xde77  ldloc.2
0xde78  ldc.i4.1
0xde79  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::RunImport(bool)
0xde7e  leave    loc_DFB0
0xde83  stloc.3
0xde84  ldsfld   string [mscorlib]System.String::Empty
0xde89  stloc.s  4
0xde8b  ldloc.3
0xde8c  callvirt instance string [mscorlib]System.Object::ToString()
0xde91  pop
0xde92  ldloc.3
0xde93  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0xde98  stloc.s  5
0xde9a  ldloc.s  5
0xde9c  brfalse.s loc_DEA6
0xde9e  ldloc.s  5
0xdea0  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0xdea5  pop
0xdea6  ldloc.3
0xdea7  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xdeac  brfalse.s loc_DEBB
0xdeae  ldloc.3
0xdeaf  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xdeb4  callvirt instance string [mscorlib]System.Object::ToString()
0xdeb9  stloc.s  4
0xdebb  ldloc.s  5
0xdebd  brfalse.s loc_DEE7
0xdebf  ldloc.s  5
0xdec1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_CrmExceptionData()
0xdec6  ldc.i4.0
0xdec7  box      [mscorlib]System.Int32
0xdecc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<object, object>::ContainsKey(var<u1>)
0xded1  brtrue.s loc_DEE7
0xded3  ldloc.s  5
0xded5  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<object, object> [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_CrmExceptionData()
0xdeda  ldc.i4.0
0xdedb  box      [mscorlib]System.Int32
0xdee0  ldloc.s  4
0xdee2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<object, object>::Add(var<u1>, !!T0)
0xdee7  rethrow
0xdee9  ldloc.2
0xdeea  callvirt instance string [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0xdeef  brtrue.s loc_DEF7
0xdef1  ldsfld   string [mscorlib]System.String::Empty
0xdef6  pop
0xdef7  ldloc.2
0xdef8  callvirt instance bool [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_HasImportFailed()
0xdefd  pop
0xdefe  ldloc.2
0xdeff  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_ImportContext()
0xdf04  pop
0xdf05  ldloc.2
0xdf06  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_OperationContext()
0xdf0b  pop
0xdf0c  ldloc.2
0xdf0d  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_CurrentVersion()
0xdf12  ldnull
0xdf13  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xdf18  brtrue.s loc_DF22
0xdf1a  ldsfld   string [mscorlib]System.String::Empty
0xdf1f  pop
0xdf20  br.s     loc_DF2E
0xdf22  ldloc.2
0xdf23  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_CurrentVersion()
0xdf28  callvirt instance string [mscorlib]System.Object::ToString()
0xdf2d  pop
0xdf2e  ldarg.s  8
0xdf30  brfalse.s loc_DF86
0xdf32  ldarg.s  8
0xdf34  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0xdf39  ldstr    aIssolutioninte// "issolutioninternal"
0xdf3e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0xdf43  brfalse.s loc_DF5C
0xdf45  ldarg.s  8
0xdf47  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0xdf4c  ldstr    aIssolutioninte// "issolutioninternal"
0xdf51  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0xdf56  unbox.any [mscorlib]System.Boolean
0xdf5b  pop
0xdf5c  ldarg.s  8
0xdf5e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0xdf63  ldstr    aIsmanaged// "ismanaged"
0xdf68  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0xdf6d  brfalse.s loc_DF86
0xdf6f  ldarg.s  8
0xdf71  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0xdf76  ldstr    aIsmanaged// "ismanaged"
0xdf7b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0xdf80  call     bool [mscorlib]System.Convert::ToBoolean(object)
0xdf85  pop
0xdf86  endfinally
0xdf87  ldloc.2
0xdf88  brfalse.s loc_DF90
0xdf8a  ldloc.2
0xdf8b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdf90  endfinally
0xdf91  ldloc.1
0xdf92  brfalse.s loc_DF9A
0xdf94  ldloc.1
0xdf95  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdf9a  endfinally
0xdf9b  ldarg.0
0xdf9c  ldloc.0
0xdf9d  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0xdfa2  ldc.i4   0x3E8
0xdfa7  conv.i8
0xdfa8  div
0xdfa9  conv.r8
0xdfaa  call     instance void Microsoft.Crm.WebServices.ImportXmlService::UpdateDurationCounter(float64 duration)
0xdfaf  endfinally
0xdfb0  ret
```
