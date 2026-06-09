# Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute_0

- ea: `0x820`
- end: `0x891`
- name: `Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute_0`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x730`
- `0x820`

## string_xrefs

- `0x821`: `manifest/control`
- `0x82f`: `manifest/control/property`
- `0x83d`: `manifest/control/data-set`
- `0x84b`: `manifest/control/data-set/property-set`
- `0x859`: `manifest/control/group`
- `0x867`: `manifest/control/group/property`
- `0x875`: `manifest/control/group/data-set`
- `0x883`: `manifest/control/group/data-set/property-set`

## pseudocode

```c

```

## disassembly

```asm
0x820  ldarg.0
0x821  ldstr    aManifestContro// "manifest/control"
0x826  ldc.i4.1
0x827  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x82c  brfalse.s loc_88F
0x82e  ldarg.0
0x82f  ldstr    aManifestContro_0// "manifest/control/property"
0x834  ldc.i4.0
0x835  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x83a  brfalse.s loc_88F
0x83c  ldarg.0
0x83d  ldstr    aManifestContro_1// "manifest/control/data-set"
0x842  ldc.i4.0
0x843  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x848  brfalse.s loc_88F
0x84a  ldarg.0
0x84b  ldstr    aManifestContro_2// "manifest/control/data-set/property-set"
0x850  ldc.i4.0
0x851  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x856  brfalse.s loc_88F
0x858  ldarg.0
0x859  ldstr    aManifestContro_3// "manifest/control/group"
0x85e  ldc.i4.0
0x85f  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x864  brfalse.s loc_88F
0x866  ldarg.0
0x867  ldstr    aManifestContro_4// "manifest/control/group/property"
0x86c  ldc.i4.0
0x86d  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x872  brfalse.s loc_88F
0x874  ldarg.0
0x875  ldstr    aManifestContro_5// "manifest/control/group/data-set"
0x87a  ldc.i4.0
0x87b  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x880  brfalse.s loc_88F
0x882  ldarg.0
0x883  ldstr    aManifestContro_6// "manifest/control/group/data-set/propert"...
0x888  ldc.i4.0
0x889  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x88e  ret
0x88f  ldc.i4.0
0x890  ret
```
