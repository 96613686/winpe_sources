# Microsoft.Crm.Setup.Common.CA.DismWrapper::GetFeatureInfo

- ea: `0x172c0`
- end: `0x172db`
- name: `Microsoft.Crm.Setup.Common.CA.DismWrapper::GetFeatureInfo`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17e00`

## callees

- `0x172c0`
- `0x17300`

## string_xrefs

- `0x172c8`: `featureName`

## pseudocode

```c

```

## disassembly

```asm
0x172c0  ldarg.1
0x172c1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x172c6  brfalse.s loc_172D3
0x172c8  ldstr    aFeaturename// "featureName"
0x172cd  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x172d2  throw
0x172d3  ldarg.0
0x172d4  ldarg.1
0x172d5  call     instance class Microsoft.Crm.Setup.Common.CA.IFeatureInfo Microsoft.Crm.Setup.Common.CA.DismWrapper::GetFeatureInfoInternal(string featureName)
0x172da  ret
```
