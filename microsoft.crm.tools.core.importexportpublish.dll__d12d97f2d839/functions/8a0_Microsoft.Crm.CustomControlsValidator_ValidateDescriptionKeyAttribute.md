# Microsoft.Crm.CustomControlsValidator::ValidateDescriptionKeyAttribute

- ea: `0x8a0`
- end: `0x92d`
- name: `Microsoft.Crm.CustomControlsValidator::ValidateDescriptionKeyAttribute`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x730`
- `0x8a0`

## string_xrefs

- `0x8e7`: `manifest/control/property`
- `0x8af`: `manifest/control/data-set`
- `0x8cb`: `manifest/control/data-set/property-set`
- `0x8a1`: `manifest/control/data-set/doc`
- `0x8bd`: `manifest/control/data-set/property-set/doc`
- `0x8d9`: `manifest/control/property/doc`
- `0x8f5`: `manifest/control/group/doc`
- `0x903`: `manifest/control/group/property/doc`
- `0x911`: `manifest/control/group/data-set/doc`
- `0x91f`: `manifest/control/group/data-set/property-set/doc`

## pseudocode

```c

```

## disassembly

```asm
0x8a0  ldarg.0
0x8a1  ldstr    aManifestContro_7// "manifest/control/data-set/doc"
0x8a6  ldc.i4.0
0x8a7  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x8ac  brtrue.s loc_8BC
0x8ae  ldarg.0
0x8af  ldstr    aManifestContro_1// "manifest/control/data-set"
0x8b4  ldc.i4.0
0x8b5  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x8ba  brfalse.s loc_92B
0x8bc  ldarg.0
0x8bd  ldstr    aManifestContro_8// "manifest/control/data-set/property-set/"...
0x8c2  ldc.i4.0
0x8c3  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x8c8  brtrue.s loc_8D8
0x8ca  ldarg.0
0x8cb  ldstr    aManifestContro_2// "manifest/control/data-set/property-set"
0x8d0  ldc.i4.0
0x8d1  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x8d6  brfalse.s loc_92B
0x8d8  ldarg.0
0x8d9  ldstr    aManifestContro_9// "manifest/control/property/doc"
0x8de  ldc.i4.0
0x8df  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x8e4  brtrue.s loc_8F4
0x8e6  ldarg.0
0x8e7  ldstr    aManifestContro_0// "manifest/control/property"
0x8ec  ldc.i4.0
0x8ed  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x8f2  brfalse.s loc_92B
0x8f4  ldarg.0
0x8f5  ldstr    aManifestContro_10// "manifest/control/group/doc"
0x8fa  ldc.i4.0
0x8fb  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x900  brfalse.s loc_92B
0x902  ldarg.0
0x903  ldstr    aManifestContro_11// "manifest/control/group/property/doc"
0x908  ldc.i4.0
0x909  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x90e  brfalse.s loc_92B
0x910  ldarg.0
0x911  ldstr    aManifestContro_12// "manifest/control/group/data-set/doc"
0x916  ldc.i4.0
0x917  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x91c  brfalse.s loc_92B
0x91e  ldarg.0
0x91f  ldstr    aManifestContro_13// "manifest/control/group/data-set/propert"...
0x924  ldc.i4.0
0x925  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDisplayNameKeyAttribute(string xmlPath, bool controlNode)
0x92a  ret
0x92b  ldc.i4.0
0x92c  ret
```
