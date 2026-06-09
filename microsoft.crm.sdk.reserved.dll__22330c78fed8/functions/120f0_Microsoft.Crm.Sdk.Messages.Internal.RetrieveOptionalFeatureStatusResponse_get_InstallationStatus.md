# Microsoft.Crm.Sdk.Messages.Internal.RetrieveOptionalFeatureStatusResponse::get_InstallationStatus

- ea: `0x120f0`
- end: `0x1211a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveOptionalFeatureStatusResponse::get_InstallationStatus`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x120f0`

## string_xrefs

- `0x120f6`: `InstallationStatus`
- `0x12108`: `InstallationStatus`

## pseudocode

```c

```

## disassembly

```asm
0x120f0  ldarg.0
0x120f1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x120f6  ldstr    aInstallationst// "InstallationStatus"
0x120fb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x12100  brfalse.s loc_12118
0x12102  ldarg.0
0x12103  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x12108  ldstr    aInstallationst// "InstallationStatus"
0x1210d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x12112  unbox.any [mscorlib]System.Int32
0x12117  ret
0x12118  ldc.i4.0
0x12119  ret
```
