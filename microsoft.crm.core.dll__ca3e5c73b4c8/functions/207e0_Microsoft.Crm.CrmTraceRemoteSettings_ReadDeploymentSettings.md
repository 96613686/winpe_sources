# Microsoft.Crm.CrmTraceRemoteSettings::ReadDeploymentSettings

- ea: `0x207e0`
- end: `0x208da`
- name: `Microsoft.Crm.CrmTraceRemoteSettings::ReadDeploymentSettings`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0xb10`
- `0x1f80`
- `0x207e0`
- `0x208e0`
- `0x20a60`
- `0x20a80`
- `0x20aa0`
- `0x20ac0`
- `0x20ae0`
- `0x20af0`

## string_xrefs

- `0x20827`: `TraceDirectory`
- `0x20894`: `TraceDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x207e0  newobj   instance void Microsoft.Crm.CrmTraceRemoteSettings::.ctor()
0x207e5  stloc.0
0x207e6  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.BootstrapService::GetSku()
0x207eb  ldc.i4.2
0x207ec  bne.un.s loc_20864
0x207ee  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTraceRemoteSettings::GetFirstPodScaleGroupId()
0x207f3  stloc.1
0x207f4  ldloc.0
0x207f5  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x207fa  ldloc.1
0x207fb  ldstr    aTracecallstack// "TraceCallStack"
0x20800  callvirt T0x2B000059
0x20805  callvirt instance void Microsoft.Crm.CrmTraceRemoteSettings::set_TraceCallStack(bool value)
0x2080a  ldloc.0
0x2080b  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x20810  ldloc.1
0x20811  ldstr    aTracecategorie// "TraceCategories"
0x20816  callvirt T0x2B00005A
0x2081b  callvirt instance void Microsoft.Crm.CrmTraceRemoteSettings::set_TraceCategories(string value)
0x20820  ldloc.0
0x20821  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x20826  ldloc.1
0x20827  ldstr    aTracedirectory// "TraceDirectory"
0x2082c  callvirt T0x2B00005A
0x20831  callvirt instance void Microsoft.Crm.CrmTraceRemoteSettings::set_TraceDirectory(string value)
0x20836  ldloc.0
0x20837  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2083c  ldloc.1
0x2083d  ldstr    aTraceenabled// "TraceEnabled"
0x20842  callvirt T0x2B000059
0x20847  callvirt instance void Microsoft.Crm.CrmTraceRemoteSettings::set_TraceEnabled(bool value)
0x2084c  ldloc.0
0x2084d  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x20852  ldloc.1
0x20853  ldstr    aTracefilesize// "TraceFileSize"
0x20858  callvirt T0x2B000043
0x2085d  callvirt instance void Microsoft.Crm.CrmTraceRemoteSettings::set_TraceFileSize(int32 value)
0x20862  br.s     loc_208CD
0x20864  ldloc.0
0x20865  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2086a  ldstr    aTracecallstack// "TraceCallStack"
0x2086f  callvirt T0x2B00003D
0x20874  callvirt instance void Microsoft.Crm.CrmTraceRemoteSettings::set_TraceCallStack(bool value)
0x20879  ldloc.0
0x2087a  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2087f  ldstr    aTracecategorie// "TraceCategories"
0x20884  callvirt T0x2B00005B
0x20889  callvirt instance void Microsoft.Crm.CrmTraceRemoteSettings::set_TraceCategories(string value)
0x2088e  ldloc.0
0x2088f  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x20894  ldstr    aTracedirectory// "TraceDirectory"
0x20899  callvirt T0x2B00005B
0x2089e  callvirt instance void Microsoft.Crm.CrmTraceRemoteSettings::set_TraceDirectory(string value)
0x208a3  ldloc.0
0x208a4  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x208a9  ldstr    aTraceenabled// "TraceEnabled"
0x208ae  callvirt T0x2B00003D
0x208b3  callvirt instance void Microsoft.Crm.CrmTraceRemoteSettings::set_TraceEnabled(bool value)
0x208b8  ldloc.0
0x208b9  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x208be  ldstr    aTracefilesize// "TraceFileSize"
0x208c3  callvirt T0x2B00003E
0x208c8  callvirt instance void Microsoft.Crm.CrmTraceRemoteSettings::set_TraceFileSize(int32 value)
0x208cd  ldloc.0
0x208ce  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x208d3  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.CrmTraceRemoteSettings::_timestamp
0x208d8  ldloc.0
0x208d9  ret
```
