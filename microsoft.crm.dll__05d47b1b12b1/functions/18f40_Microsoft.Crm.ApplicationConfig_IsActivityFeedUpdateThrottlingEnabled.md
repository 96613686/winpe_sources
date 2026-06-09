# Microsoft.Crm.ApplicationConfig::IsActivityFeedUpdateThrottlingEnabled

- ea: `0x18f40`
- end: `0x18f57`
- name: `Microsoft.Crm.ApplicationConfig::IsActivityFeedUpdateThrottlingEnabled`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18f40`
- `0x18f60`

## string_xrefs

- `0x18f40`: `UpdatePostTimestampThrottlingEnabled`

## pseudocode

```c

```

## disassembly

```asm
0x18f40  ldstr    aUpdateposttime// "UpdatePostTimestampThrottlingEnabled"
0x18f45  call     object Microsoft.Crm.ApplicationConfig::RetrieveDeploymentProperty(string propertyName)
0x18f4a  stloc.0
0x18f4b  ldloc.0
0x18f4c  brfalse.s loc_18F55
0x18f4e  ldloc.0
0x18f4f  unbox.any [mscorlib]System.Boolean
0x18f54  ret
0x18f55  ldc.i4.1
0x18f56  ret
```
