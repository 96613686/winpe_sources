# Microsoft.Crm.ProductVersion::get_ProductVersionFromRegistry

- ea: `0x3d880`
- end: `0x3d8e3`
- name: `Microsoft.Crm.ProductVersion::get_ProductVersionFromRegistry`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x51630`
- `0x51670`
- `0x55c90`

## callees

- `0x34780`
- `0x3d860`
- `0x3d880`

## string_xrefs

- `0x3d880`: `CRM_Live_Serviceability_Version`
- `0x3d89f`: `CRM_Server_Serviceability_Version`

## pseudocode

```c

```

## disassembly

```asm
0x3d880  ldstr    aCrmLiveService// "CRM_Live_Serviceability_Version"
0x3d885  ldsfld   string [mscorlib]System.String::Empty
0x3d88a  call     object Microsoft.Crm.RegistryCache::GetValue(string key, object defaultValue)
0x3d88f  castclass [mscorlib]System.String
0x3d894  stloc.0
0x3d895  ldloc.0
0x3d896  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3d89b  brtrue.s loc_3D89F
0x3d89d  ldloc.0
0x3d89e  ret
0x3d89f  ldstr    aCrmServerServi// "CRM_Server_Serviceability_Version"
0x3d8a4  ldsfld   string [mscorlib]System.String::Empty
0x3d8a9  call     object Microsoft.Crm.RegistryCache::GetValue(string key, object defaultValue)
0x3d8ae  castclass [mscorlib]System.String
0x3d8b3  stloc.0
0x3d8b4  ldloc.0
0x3d8b5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3d8ba  brtrue.s loc_3D8BE
0x3d8bc  ldloc.0
0x3d8bd  ret
0x3d8be  ldstr    aCrmServerVersi// "CRM_Server_Version"
0x3d8c3  ldsfld   string [mscorlib]System.String::Empty
0x3d8c8  call     object Microsoft.Crm.RegistryCache::GetValue(string key, object defaultValue)
0x3d8cd  castclass [mscorlib]System.String
0x3d8d2  stloc.0
0x3d8d3  ldloc.0
0x3d8d4  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3d8d9  brtrue.s loc_3D8DD
0x3d8db  ldloc.0
0x3d8dc  ret
0x3d8dd  call     string Microsoft.Crm.ProductVersion::get_FullVersion()
0x3d8e2  ret
```
