# Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::GetConfigSettings

- ea: `0x16e80`
- end: `0x16edc`
- name: `Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::GetConfigSettings`
- size: `92`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x16bc0`
- `0x16c30`
- `0x16c60`

## callees

- `0x16e80`

## string_xrefs

- `0x16ea3`: `NOT AN ERROR: [OrgDbUpdate-GetConfigSettings] Found Site settings for {0}, value is {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x16e80  ldsfld   string [mscorlib]System.String::Empty
0x16e85  stloc.0
0x16e86  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x16e8b  ldarg.0
0x16e8c  ldc.i4.0
0x16e8d  callvirt T0x2B00001B
0x16e92  stloc.0
0x16e93  ldloc.0
0x16e94  brtrue.s loc_16E9C
0x16e96  ldsfld   string [mscorlib]System.String::Empty
0x16e9b  stloc.0
0x16e9c  ldnull
0x16e9d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x16ea2  ldc.i4.3
0x16ea3  ldstr    aNotAnErrorOrgd// "NOT AN ERROR: [OrgDbUpdate-GetConfigSet"...
0x16ea8  ldarg.0
0x16ea9  ldloc.0
0x16eaa  call     string [mscorlib]System.String::Format(string, object, object)
0x16eaf  ldc.i4.0
0x16eb0  newarr   [mscorlib]System.Object
0x16eb5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16eba  leave.s  loc_16EDA
0x16ebc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x16ec1  ldc.i4.3
0x16ec2  ldstr    aSiteSettingsFo// "Site settings for {0} has not been set."
0x16ec7  ldarg.0
0x16ec8  call     string [mscorlib]System.String::Format(string, object)
0x16ecd  ldc.i4.0
0x16ece  newarr   [mscorlib]System.Object
0x16ed3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16ed8  leave.s  loc_16EDA
0x16eda  ldloc.0
0x16edb  ret
```
