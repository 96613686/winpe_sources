# DRMSetUsagePolicy

- ea: `0x180007c30`
- end: `0x180007f08`
- name: `DRMSetUsagePolicy`
- size: `728`
- prototype: `HRESULT __stdcall(DRMPUBHANDLE hIssuanceLicense, DRM_USAGEPOLICY_TYPE eUsagePolicyType, BOOL fDelete, BOOL fExclusion, PWSTR wszName, PWSTR wszMinVersion, PWSTR wszMaxVersion, PWSTR wszPublicKey, PWSTR wszDigestAlgorithm, BYTE *pbDigest, UINT cbDigest)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180001284`
- `0x18000420c`
- `0x1800043ac`
- `0x1800046c8`
- `0x180007c30`
- `0x180016548`
- `0x18001ffd8`
- `0x18003b3b8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180007da7`
- `msvcrt!_wcsicmp` at `0x180007da7`

## pseudocode

```c

```
