# Microsoft.Crm.Metadata.CacheConstants::GetLockTimeout

- ea: `0x4f2b0`
- end: `0x4f312`
- name: `Microsoft.Crm.Metadata.CacheConstants::GetLockTimeout`
- size: `98`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4e860`
- `0xab160`
- `0xad810`

## callees

- `0x4f2b0`

## string_xrefs

- `0x4f2c4`: `MetadataCacheLockTimeoutInMilliseconds`
- `0x4f2f2`: `MetadataCacheLockTimeoutInMilliseconds`
- `0x4f2d3`: `D:\a\1\s\src\ManagedPlatform\SDK\Metadata\MetadataCache\StaticMetadataCache.cs`

## pseudocode

```c

```

## disassembly

```asm
0x4f2b0  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x4f2b5  brtrue.s loc_4F2DF
0x4f2b7  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInCrmInternalToolContext()
0x4f2bc  brtrue.s loc_4F2DF
0x4f2be  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x4f2c3  ldarg.0
0x4f2c4  ldstr    aMetadatacachel// "MetadataCacheLockTimeoutInMilliseconds"
0x4f2c9  ldc.i4   0x4C2
0x4f2ce  ldstr    aGetlocktimeout// "GetLockTimeout"
0x4f2d3  ldstr    aDA1SSrcManaged_9// "D:\\a\\1\\s\\src\\ManagedPlatform\\SDK"...
0x4f2d8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x4f2dd  br.s     loc_4F2E9
0x4f2df  ldc.i4   0xEA60
0x4f2e4  box      [mscorlib]System.Int32
0x4f2e9  stloc.0
0x4f2ea  ldloc.0
0x4f2eb  brtrue.s loc_4F302
0x4f2ed  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x4f2f2  ldstr    aMetadatacachel// "MetadataCacheLockTimeoutInMilliseconds"
0x4f2f7  callvirt T0x2B000008
0x4f2fc  box      valuetype [mscorlib]System.Nullable`1<int32>
0x4f301  stloc.0
0x4f302  ldloc.0
0x4f303  brfalse.s loc_4F30C
0x4f305  ldloc.0
0x4f306  unbox.any [mscorlib]System.Int32
0x4f30b  ret
0x4f30c  ldc.i4   0xEA60
0x4f311  ret
```
