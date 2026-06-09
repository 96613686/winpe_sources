# CRmsInterface::CreateAndSerializeLicense(void *,ushort const *,_EFS_KEY *,uchar * *,ulong *,void * *)

- ea: `0x18006cc84`
- end: `0x18006cf5b`
- name: `?CreateAndSerializeLicense@CRmsInterface@@QEAAJPEAXPEBGPEAU_EFS_KEY@@PEAPEAEPEAKPEAPEAX@Z`
- size: `727`
- prototype: `__int64 __fastcall(CRmsInterface *__hidden this, void *, const unsigned __int16 *, struct _EFS_KEY *, unsigned __int8 **, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180072ae8`

## callees

- `0x180004f86`
- `0x18006bcf8`
- `0x18006c764`
- `0x18006cc84`
- `0x18006d1a0`
- `0x18006db58`
- `0x18006dddc`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ceb0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ceb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ce9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ce9f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006ce19`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006ce19`
- `winmsipc!__imp_IpcCloseHandle` at `0x18006cf13`
- `winmsipc!__imp_IpcCloseHandle` at `0x18006cf23`
- `winmsipc!__imp_IpcCloseHandle` at `0x18006cf13`
- `winmsipc!__imp_IpcCloseHandle` at `0x18006cf23`
- `winmsipc!__imp_IpcFreeMemory` at `0x18006cf00`
- `winmsipc!__imp_IpcFreeMemory` at `0x18006cf00`
- `winmsipc!__imp_IpcSetLicenseProperty` at `0x18006cd63`
- `winmsipc!__imp_IpcSetLicenseProperty` at `0x18006cda7`
- `winmsipc!__imp_IpcSetLicenseProperty` at `0x18006cd63`
- `winmsipc!__imp_IpcSetLicenseProperty` at `0x18006cda7`
- `winmsipc!__imp_IpcSerializeLicense` at `0x18006ce56`
- `winmsipc!__imp_IpcSerializeLicense` at `0x18006ce8b`
- `winmsipc!__imp_IpcSerializeLicense` at `0x18006ce56`
- `winmsipc!__imp_IpcSerializeLicense` at `0x18006ce8b`
- `winmsipc!__imp_IpcpSetKeyBits` at `0x18006cdc1`
- `winmsipc!__imp_IpcpSetKeyBits` at `0x18006cdc1`

## pseudocode

```c

```
