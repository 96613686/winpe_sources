# Microsoft.Crm.BootstrapService::.ctor_0

- ea: `0x1ad0`
- end: `0x1c4c`
- name: `Microsoft.Crm.BootstrapService::.ctor_0`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1ac0`

## callees

- `0x1ad0`
- `0x1d00`
- `0x17d70`
- `0x17d90`
- `0x1be80`
- `0x44400`
- `0x44510`

## string_xrefs

- `0x1af2`: `TraceDirectory`
- `0x1b5d`: `TraceDirectory`
- `0x1b12`: `GeoReadOnlyModeEnabled`
- `0x1b1a`: `GeoReadOnlyModeReplica`
- `0x1b2c`: `CloudConfigUrl`
- `0x1b94`: `service`
- `0x1bfd`: `Bootstrap service failed to load so falling back to legacy provider. Error details:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x1ad0  ldarg.0
0x1ad1  ldc.i4.s 0xB
0x1ad3  newarr   [mscorlib]System.String
0x1ad8  dup
0x1ad9  ldc.i4.0
0x1ada  ldstr    aTracerefresh// "TraceRefresh"
0x1adf  stelem.ref
0x1ae0  dup
0x1ae1  ldc.i4.1
0x1ae2  ldstr    aTracecallstack// "TraceCallStack"
0x1ae7  stelem.ref
0x1ae8  dup
0x1ae9  ldc.i4.2
0x1aea  ldstr    aTracecategorie// "TraceCategories"
0x1aef  stelem.ref
0x1af0  dup
0x1af1  ldc.i4.3
0x1af2  ldstr    aTracedirectory// "TraceDirectory"
0x1af7  stelem.ref
0x1af8  dup
0x1af9  ldc.i4.4
0x1afa  ldstr    aTraceenabled// "TraceEnabled"
0x1aff  stelem.ref
0x1b00  dup
0x1b01  ldc.i4.5
0x1b02  ldstr    aTracefilesize// "TraceFileSize"
0x1b07  stelem.ref
0x1b08  dup
0x1b09  ldc.i4.6
0x1b0a  ldstr    aTracebypassorg// "TraceBypassOrganizations"
0x1b0f  stelem.ref
0x1b10  dup
0x1b11  ldc.i4.7
0x1b12  ldstr    aGeoreadonlymod// "GeoReadOnlyModeEnabled"
0x1b17  stelem.ref
0x1b18  dup
0x1b19  ldc.i4.8
0x1b1a  ldstr    aGeoreadonlymod_0// "GeoReadOnlyModeReplica"
0x1b1f  stelem.ref
0x1b20  dup
0x1b21  ldc.i4.s 9
0x1b23  ldstr    aLongquerythres// "LongQueryThresholdInSeconds"
0x1b28  stelem.ref
0x1b29  dup
0x1b2a  ldc.i4.s 0xA
0x1b2c  ldstr    aCloudconfigurl// "CloudConfigUrl"
0x1b31  stelem.ref
0x1b32  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1b37  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.BootstrapService::BootstrapServerSettings
0x1b3c  ldarg.0
0x1b3d  ldc.i4.8
0x1b3e  newarr   [mscorlib]System.String
0x1b43  dup
0x1b44  ldc.i4.0
0x1b45  ldstr    aTracerefresh// "TraceRefresh"
0x1b4a  stelem.ref
0x1b4b  dup
0x1b4c  ldc.i4.1
0x1b4d  ldstr    aTracecallstack// "TraceCallStack"
0x1b52  stelem.ref
0x1b53  dup
0x1b54  ldc.i4.2
0x1b55  ldstr    aTracecategorie// "TraceCategories"
0x1b5a  stelem.ref
0x1b5b  dup
0x1b5c  ldc.i4.3
0x1b5d  ldstr    aTracedirectory// "TraceDirectory"
0x1b62  stelem.ref
0x1b63  dup
0x1b64  ldc.i4.4
0x1b65  ldstr    aTraceenabled// "TraceEnabled"
0x1b6a  stelem.ref
0x1b6b  dup
0x1b6c  ldc.i4.5
0x1b6d  ldstr    aTracefilesize// "TraceFileSize"
0x1b72  stelem.ref
0x1b73  dup
0x1b74  ldc.i4.6
0x1b75  ldstr    aLongquerythres// "LongQueryThresholdInSeconds"
0x1b7a  stelem.ref
0x1b7b  dup
0x1b7c  ldc.i4.7
0x1b7d  ldstr    aTraceuseetwonl// "TraceUseEtwOnly"
0x1b82  stelem.ref
0x1b83  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1b88  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.BootstrapService::BootstrapDeploymentSettings
0x1b8d  ldarg.0
0x1b8e  call     instance void [mscorlib]System.Object::.ctor()
0x1b93  ldarg.1
0x1b94  ldstr    aService// "service"
0x1b99  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x1b9e  ldarg.0
0x1b9f  ldarg.1
0x1ba0  stfld    class Microsoft.Crm.ILocatorService Microsoft.Crm.BootstrapService::_serverLocatorService
0x1ba5  ldsfld   class [mscorlib]System.Func`1<class Microsoft.Crm.Core.IConfigFileManager> <>c::<>9__8_0
0x1baa  dup
0x1bab  brtrue.s loc_1BC4
0x1bad  pop
0x1bae  ldsfld   class <>c <>c::<>9
0x1bb3  ldftn    instance class Microsoft.Crm.Core.IConfigFileManager <>c::<.ctor>b__8_0()
0x1bb9  newobj   instance void class [mscorlib]System.Func`1<class Microsoft.Crm.Core.IConfigFileManager>::.ctor(object, native int)
0x1bbe  dup
0x1bbf  stsfld   class [mscorlib]System.Func`1<class Microsoft.Crm.Core.IConfigFileManager> <>c::<>9__8_0
0x1bc4  call     T0x2B000007
0x1bc9  ldarg.0
0x1bca  call     T0x2B000008
0x1bcf  stfld    class Microsoft.Crm.Core.IConfigFileManager Microsoft.Crm.BootstrapService::_configFileManager
0x1bd4  ldarg.0
0x1bd5  call     instance void Microsoft.Crm.BootstrapService::InitializeBootstrapSettings()
0x1bda  leave.s  loc_1C4B
0x1bdc  stloc.0
0x1bdd  newobj   instance void Microsoft.Crm.CrmEventLog::.ctor()
0x1be2  stloc.1
0x1be3  ldloc.1
0x1be4  ldstr    aMscrmplatform// "MSCRMPlatform"
0x1be9  ldc.i4.1
0x1bea  ldc.i4   0xC000460B
0x1bef  conv.u8
0x1bf0  ldc.i4.1
0x1bf1  newarr   [mscorlib]System.Object
0x1bf6  dup
0x1bf7  ldc.i4.0
0x1bf8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1bfd  ldstr    aBootstrapServi// "Bootstrap service failed to load so fal"...
0x1c02  ldc.i4.1
0x1c03  newarr   [mscorlib]System.Object
0x1c08  dup
0x1c09  ldc.i4.0
0x1c0a  ldloc.0
0x1c0b  callvirt instance string [mscorlib]System.Object::ToString()
0x1c10  stelem.ref
0x1c11  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1c16  stelem.ref
0x1c17  callvirt instance void Microsoft.Crm.CrmEventLog::WriteEntry(string eventSourceName, valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventId, object[] values)
0x1c1c  leave.s  loc_1C28
0x1c1e  ldloc.1
0x1c1f  brfalse.s loc_1C27
0x1c21  ldloc.1
0x1c22  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c27  endfinally
0x1c28  ldarg.0
0x1c29  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x1c2e  stfld    class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.BootstrapService::_bootstrapServerSettingsValues
0x1c33  ldarg.0
0x1c34  ldfld    class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.BootstrapService::_bootstrapServerSettingsValues
0x1c39  ldsfld   string Microsoft.Crm.BootstrapServerSettingsConstants::IsCloudConfigEnabled
0x1c3e  ldc.i4.0
0x1c3f  box      [mscorlib]System.Boolean
0x1c44  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x1c49  leave.s  loc_1C4B
0x1c4b  ret
```
