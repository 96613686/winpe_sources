# SequencingAPICoreW(IMsiString const &,ushort const *,ushort const *,tagMSIINSTALLCONTEXT,ushort const *,bool,IMsiServices *,ulong,tagMSIPATCHSEQUENCEINFOW *)

- ea: `0x18005acec`
- end: `0x18005de49`
- name: `?SequencingAPICoreW@@YAIAEBVIMsiString@@PEBG1W4tagMSIINSTALLCONTEXT@@1_NPEAVIMsiServices@@KPEAUtagMSIPATCHSEQUENCEINFOW@@@Z`
- size: `12637`
- prototype: `unsigned int(const struct IMsiString *, const unsigned __int16 *, const unsigned __int16 *, enum tagMSIINSTALLCONTEXT, const unsigned __int16 *, bool, struct IMsiServices *, unsigned int, struct tagMSIPATCHSEQUENCEINFOW *)`
- caller_count: `2`
- callee_count: `41`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18005a450`
- `0x1801a2d90`

## callees

- `0x18000bb80`
- `0x18000c4bc`
- `0x18000d270`
- `0x180014288`
- `0x180018ee0`
- `0x180021358`
- `0x18002e870`
- `0x1800399d0`
- `0x18003c030`
- `0x18003e40c`
- `0x180047380`
- `0x18004a014`
- `0x18005a9a8`
- `0x18005ac8c`
- `0x18005acbc`
- `0x18005acec`
- `0x18005de50`
- `0x180072e00`
- `0x18008593c`
- `0x180086f64`
- `0x18008b3c4`
- `0x18008bea8`
- `0x18008bf54`
- `0x18008c93c`
- `0x1800ae46c`
- `0x1800e0490`
- `0x1801197c8`
- `0x18011eec0`
- `0x180131928`
- `0x18013fcf8`
- `0x18014d5f0`
- `0x180157624`
- `0x18015b000`
- `0x18015cffc`
- `0x1801a20a8`
- `0x1801afa90`
- `0x18021c94c`
- `0x180257c08`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x18005ca73`
- `msvcrt!_ui64tow_s` at `0x18005ca73`
- `msvcrt!_wcstoui64` at `0x18005c354`
- `msvcrt!_wcstoui64` at `0x18005c354`
- `msvcrt!qsort` at `0x18005da1d`
- `msvcrt!qsort` at `0x18005da1d`
- `KERNEL32!InitializeCriticalSection` at `0x18005ae70`
- `KERNEL32!InitializeCriticalSection` at `0x18005ae70`
- `KERNEL32!GlobalFree` at `0x18005b0ea`
- `KERNEL32!GlobalFree` at `0x18005b98a`
- `KERNEL32!GlobalFree` at `0x18005be0e`
- `KERNEL32!GlobalFree` at `0x18005c6e6`
- `KERNEL32!GlobalFree` at `0x18005c844`
- `KERNEL32!GlobalFree` at `0x18005ce50`
- `KERNEL32!GlobalFree` at `0x18005ce68`
- `KERNEL32!GlobalFree` at `0x18005d106`
- `KERNEL32!GlobalFree` at `0x18005d11e`
- `KERNEL32!GlobalFree` at `0x18005d827`
- `KERNEL32!GlobalFree` at `0x18005d933`
- `KERNEL32!GlobalFree` at `0x18005d9b5`
- `KERNEL32!GlobalFree` at `0x18005de38`
- `KERNEL32!GlobalFree` at `0x18005b0ea`
- `KERNEL32!GlobalFree` at `0x18005b98a`
- `KERNEL32!GlobalFree` at `0x18005be0e`
- `KERNEL32!GlobalFree` at `0x18005c6e6`
- `KERNEL32!GlobalFree` at `0x18005c844`
- `KERNEL32!GlobalFree` at `0x18005ce50`
- `KERNEL32!GlobalFree` at `0x18005ce68`
- `KERNEL32!GlobalFree` at `0x18005d106`
- `KERNEL32!GlobalFree` at `0x18005d11e`
- `KERNEL32!GlobalFree` at `0x18005d827`
- `KERNEL32!GlobalFree` at `0x18005d933`
- `KERNEL32!GlobalFree` at `0x18005d9b5`
- `KERNEL32!GlobalFree` at `0x18005de38`

## string_xrefs

- `0x18005b2ed`: `EngineCopy`
- `0x18005b3d0`: `InstalledWith3x`
- `0x18005b4a4`: `#_PatchCache`
- `0x18005b352`: `SourcePath`
- `0x18005cd96`: `%s ERROR: %s product had not been installed/configured with version >= 3.0 of Windows Installer for %s in non-managed context.`
- `0x18005d258`: `%s ERROR: %d returned from attempt to get the summary info of %s patch file!`

## pseudocode

```c

```
