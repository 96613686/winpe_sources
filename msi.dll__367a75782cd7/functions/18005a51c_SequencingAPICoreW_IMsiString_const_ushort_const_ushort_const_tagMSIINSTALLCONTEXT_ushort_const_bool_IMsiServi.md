# SequencingAPICoreW(IMsiString const &,ushort const *,ushort const *,tagMSIINSTALLCONTEXT,ushort const *,bool,IMsiServices *,ulong,tagMSIPATCHSEQUENCEINFOW *)

- ea: `0x18005a51c`
- end: `0x18005d65f`
- name: `?SequencingAPICoreW@@YAIAEBVIMsiString@@PEBG1W4tagMSIINSTALLCONTEXT@@1_NPEAVIMsiServices@@KPEAUtagMSIPATCHSEQUENCEINFOW@@@Z`
- size: `12611`
- prototype: `unsigned int(const struct IMsiString *, const unsigned __int16 *, const unsigned __int16 *, enum tagMSIINSTALLCONTEXT, const unsigned __int16 *, bool, struct IMsiServices *, unsigned int, struct tagMSIPATCHSEQUENCEINFOW *)`
- caller_count: `2`
- callee_count: `40`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180129c60`
- `0x18019bde0`

## callees

- `0x180015950`
- `0x180017a84`
- `0x18001e5d0`
- `0x180025688`
- `0x180025a18`
- `0x180037278`
- `0x18003da40`
- `0x18004035c`
- `0x1800405f0`
- `0x1800410d4`
- `0x18004295c`
- `0x18004ceb0`
- `0x18004d5c4`
- `0x180050cf0`
- `0x1800598c0`
- `0x18005a210`
- `0x18005a4c4`
- `0x18005a4f0`
- `0x18005a51c`
- `0x18005d670`
- `0x180061334`
- `0x180076e28`
- `0x18008eac8`
- `0x18009008c`
- `0x1800a5fc4`
- `0x1800dee18`
- `0x180111040`
- `0x180117e10`
- `0x18012c5c4`
- `0x18013aaf4`
- `0x180151c78`
- `0x1801555fc`
- `0x180157604`
- `0x18019b158`
- `0x1801a8930`
- `0x180212fdc`
- `0x18024d908`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x18005c24f`
- `msvcrt!_ui64tow_s` at `0x18005c24f`
- `msvcrt!_wcstoui64` at `0x18005b3bc`
- `msvcrt!_wcstoui64` at `0x18005b3bc`
- `msvcrt!qsort` at `0x18005c516`
- `msvcrt!qsort` at `0x18005c516`
- `KERNEL32!InitializeCriticalSection` at `0x18005a69d`
- `KERNEL32!InitializeCriticalSection` at `0x18005a69d`
- `KERNEL32!GlobalFree` at `0x18005a915`
- `KERNEL32!GlobalFree` at `0x18005b199`
- `KERNEL32!GlobalFree` at `0x18005bb68`
- `KERNEL32!GlobalFree` at `0x18005bfdc`
- `KERNEL32!GlobalFree` at `0x18005c0d5`
- `KERNEL32!GlobalFree` at `0x18005c6d6`
- `KERNEL32!GlobalFree` at `0x18005c6e8`
- `KERNEL32!GlobalFree` at `0x18005c986`
- `KERNEL32!GlobalFree` at `0x18005c998`
- `KERNEL32!GlobalFree` at `0x18005d0a7`
- `KERNEL32!GlobalFree` at `0x18005d1ca`
- `KERNEL32!GlobalFree` at `0x18005d246`
- `KERNEL32!GlobalFree` at `0x18005d654`
- `KERNEL32!GlobalFree` at `0x18005a915`
- `KERNEL32!GlobalFree` at `0x18005b199`
- `KERNEL32!GlobalFree` at `0x18005bb68`
- `KERNEL32!GlobalFree` at `0x18005bfdc`
- `KERNEL32!GlobalFree` at `0x18005c0d5`
- `KERNEL32!GlobalFree` at `0x18005c6d6`
- `KERNEL32!GlobalFree` at `0x18005c6e8`
- `KERNEL32!GlobalFree` at `0x18005c986`
- `KERNEL32!GlobalFree` at `0x18005c998`
- `KERNEL32!GlobalFree` at `0x18005d0a7`
- `KERNEL32!GlobalFree` at `0x18005d1ca`
- `KERNEL32!GlobalFree` at `0x18005d246`
- `KERNEL32!GlobalFree` at `0x18005d654`

## string_xrefs

- `0x18005ab0e`: `EngineCopy`
- `0x18005abf4`: `InstalledWith3x`
- `0x18005acc8`: `#_PatchCache`
- `0x18005ab76`: `SourcePath`
- `0x18005c614`: `%s ERROR: %s product had not been installed/configured with version >= 3.0 of Windows Installer for %s in non-managed context.`
- `0x18005cade`: `%s ERROR: %d returned from attempt to get the summary info of %s patch file!`

## pseudocode

```c

```
