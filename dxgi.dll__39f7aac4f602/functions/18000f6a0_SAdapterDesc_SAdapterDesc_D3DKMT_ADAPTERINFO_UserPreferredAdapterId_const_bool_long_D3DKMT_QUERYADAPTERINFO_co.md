# SAdapterDesc::SAdapterDesc(_D3DKMT_ADAPTERINFO *,UserPreferredAdapterId const &,bool,long (*)(_D3DKMT_QUERYADAPTERINFO const *),long (*)(_D3DKMT_QUERYVIDEOMEMORYINFO *),ulong,ulong)

- ea: `0x18000f6a0`
- end: `0x18000fd38`
- name: `??0SAdapterDesc@@QEAA@PEAU_D3DKMT_ADAPTERINFO@@AEBUUserPreferredAdapterId@@_NP6AJPEBU_D3DKMT_QUERYADAPTERINFO@@@ZP6AJPEAU_D3DKMT_QUERYVIDEOMEMORYINFO@@@ZKK@Z`
- size: `1688`
- prototype: `SAdapterDesc *__usercall@<rax>(SAdapterDesc *__hidden this@<rcx>, struct _D3DKMT_ADAPTERINFO *@<rdx>, const struct UserPreferredAdapterId *@<r8>, bool@<r9b>, int (*)(const struct _D3DKMT_QUERYADAPTERINFO *), int (*)(struct _D3DKMT_QUERYVIDEOMEMORYINFO *), unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18003f04c`

## callees

- `0x18000c6b0`
- `0x18000dfe0`
- `0x18000f6a0`
- `0x18000fd40`
- `0x18000fd60`
- `0x1800100d4`
- `0x180010598`
- `0x180010d40`
- `0x180015df4`
- `0x180016504`
- `0x180019268`
- `0x180075fa0`
- `0x180076f14`
- `0x180076f20`
- `0x18007bf63`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7d9`
- `api-ms-win-dx-d3dkmt-l1-1-0!GdiEntry13` at `0x18000f9a5`
- `api-ms-win-dx-d3dkmt-l1-1-0!GdiEntry13` at `0x18000f9a5`

## string_xrefs

- `0x18000f7e6`: `DisplayConfigGetDeviceInfo failed.`
- `0x18000f809`: `DisplayConfigGetDeviceInfo GLE.`
- `0x18000fb31`: `DisplayConfigGetDeviceInfo FailurePoint.`
- `0x18000fba7`: `DisplayConfigGetDeviceInfo FailurePoint.`

## pseudocode

```c

```
