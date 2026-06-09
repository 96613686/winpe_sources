# Microsoft.Crm.Controls.Header::AttachResourcesAndRelatedScripts

- ea: `0x8400`
- end: `0x847b`
- name: `Microsoft.Crm.Controls.Header::AttachResourcesAndRelatedScripts`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x20f0`

## callees

- `0x2ef0`
- `0x38d0`
- `0x40f0`
- `0x4f20`

## string_xrefs

- `0x8407`: `_sWebServicesNamespace`
- `0x840c`: `http://schemas.microsoft.com/crm/2009/WebServices`
- `0x8417`: `LOCID_REMOTECOMMAND_ERROR`

## pseudocode

```c

```

## disassembly

```asm
0x8400  ldarg.0
0x8401  call     instance void Microsoft.Crm.Controls.PageResourceManager::AttachResourcesAndRelatedScripts()
0x8406  ldarg.0
0x8407  ldstr    aSwebservicesna// "_sWebServicesNamespace"
0x840c  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2009/W"...
0x8411  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x8416  ldarg.0
0x8417  ldstr    aLocidRemotecom// "LOCID_REMOTECOMMAND_ERROR"
0x841c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8421  ldstr    aGeneric// "Generic"
0x8426  ldc.i4.0
0x8427  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x842c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetErrorMessage(string, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8431  ldc.i4.0
0x8432  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x8437  ldarg.0
0x8438  ldstr    aLocidErrmsgEtm// "LOCID_ERRMSG_ETM_RETRY"
0x843d  ldarg.0
0x843e  ldstr    aErrorMessageEt// "Error_Message_ETM_Retry"
0x8443  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x8448  ldc.i4.0
0x8449  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x844e  ldarg.0
0x844f  ldstr    aErrorcodeEtm// "ERRORCODE_ETM"
0x8454  ldstr    a0x// "0x"
0x8459  ldc.i4   0x8004A001
0x845e  stloc.0
0x845f  ldloca.s 0
0x8461  ldstr    aX// "X"
0x8466  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x846b  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x8470  call     string [mscorlib]System.String::Concat(string, string)
0x8475  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x847a  ret
```
