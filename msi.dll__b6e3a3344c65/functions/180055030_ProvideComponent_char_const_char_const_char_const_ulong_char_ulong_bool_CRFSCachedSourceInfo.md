# ProvideComponent(char const *,char const *,char const *,ulong,char *,ulong *,bool,CRFSCachedSourceInfo &)

- ea: `0x180055030`
- end: `0x180055edb`
- name: `?ProvideComponent@@YAIPEBD00KPEADPEAK_NAEAVCRFSCachedSourceInfo@@@Z`
- size: `3755`
- prototype: `unsigned int __fastcall(const char *, const char *, const char *, DWORD dwReinstallMode, char *, unsigned int *, bool, struct CRFSCachedSourceInfo *)`
- caller_count: `2`
- callee_count: `26`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18015298c`
- `0x180199820`

## callees

- `0x18000a150`
- `0x180015950`
- `0x18001ba40`
- `0x18001cab0`
- `0x18001d960`
- `0x1800250d4`
- `0x180025560`
- `0x180025a18`
- `0x18004c5c0`
- `0x1800504bc`
- `0x180051d20`
- `0x180051f88`
- `0x1800520f4`
- `0x180054124`
- `0x180055030`
- `0x180056008`
- `0x180056280`
- `0x1800ae2ec`
- `0x1800ae31c`
- `0x1800aee10`
- `0x18014df38`
- `0x18014ef90`
- `0x180150470`
- `0x180154618`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800551cb`
- `KERNEL32!InitializeCriticalSection` at `0x1800551cb`
- `KERNEL32!lstrlenA` at `0x18005551d`
- `KERNEL32!lstrlenA` at `0x18005551d`
- `KERNEL32!GlobalFree` at `0x180055121`
- `KERNEL32!GlobalFree` at `0x18005513d`
- `KERNEL32!GlobalFree` at `0x180055242`
- `KERNEL32!GlobalFree` at `0x180055260`
- `KERNEL32!GlobalFree` at `0x180055366`
- `KERNEL32!GlobalFree` at `0x180055380`
- `KERNEL32!GlobalFree` at `0x1800555af`
- `KERNEL32!GlobalFree` at `0x1800555dd`
- `KERNEL32!GlobalFree` at `0x180055668`
- `KERNEL32!GlobalFree` at `0x1800556b7`
- `KERNEL32!GlobalFree` at `0x1800556d1`
- `KERNEL32!GlobalFree` at `0x1800557b7`
- `KERNEL32!GlobalFree` at `0x180055811`
- `KERNEL32!GlobalFree` at `0x18005591f`
- `KERNEL32!GlobalFree` at `0x180055935`
- `KERNEL32!GlobalFree` at `0x180055963`
- `KERNEL32!GlobalFree` at `0x180055a14`
- `KERNEL32!GlobalFree` at `0x180055a4b`
- `KERNEL32!GlobalFree` at `0x180055a65`
- `KERNEL32!GlobalFree` at `0x180055a93`
- `KERNEL32!GlobalFree` at `0x180055aee`
- `KERNEL32!GlobalFree` at `0x180055b08`
- `KERNEL32!GlobalFree` at `0x180055b39`
- `KERNEL32!GlobalFree` at `0x180055b88`
- `KERNEL32!GlobalFree` at `0x180055ba2`
- `KERNEL32!GlobalFree` at `0x180055bc2`
- `KERNEL32!GlobalFree` at `0x180055c11`
- `KERNEL32!GlobalFree` at `0x180055c2b`
- `KERNEL32!GlobalFree` at `0x180055c4b`
- `KERNEL32!GlobalFree` at `0x180055c7e`
- `KERNEL32!GlobalFree` at `0x180055ccd`
- `KERNEL32!GlobalFree` at `0x180055ce7`
- `KERNEL32!GlobalFree` at `0x180055d28`
- `KERNEL32!GlobalFree` at `0x180055d42`
- `KERNEL32!GlobalFree` at `0x180055d85`
- `KERNEL32!GlobalFree` at `0x180055d9f`
- `KERNEL32!GlobalFree` at `0x180055dfc`
- `KERNEL32!GlobalFree` at `0x180055e16`
- `KERNEL32!GlobalFree` at `0x180055e53`
- `KERNEL32!GlobalFree` at `0x180055e6d`
- `KERNEL32!GlobalFree` at `0x180055eb3`
- `KERNEL32!GlobalFree` at `0x180055ecd`
- `KERNEL32!GlobalFree` at `0x180055121`
- `KERNEL32!GlobalFree` at `0x18005513d`
- `KERNEL32!GlobalFree` at `0x180055242`
- `KERNEL32!GlobalFree` at `0x180055260`
- `KERNEL32!GlobalFree` at `0x180055366`
- `KERNEL32!GlobalFree` at `0x180055380`
- `KERNEL32!GlobalFree` at `0x1800555af`
- `KERNEL32!GlobalFree` at `0x1800555dd`
- `KERNEL32!GlobalFree` at `0x180055668`
- `KERNEL32!GlobalFree` at `0x1800556b7`
- `KERNEL32!GlobalFree` at `0x1800556d1`
- `KERNEL32!GlobalFree` at `0x1800557b7`
- `KERNEL32!GlobalFree` at `0x180055811`
- `KERNEL32!GlobalFree` at `0x18005591f`
- `KERNEL32!GlobalFree` at `0x180055935`
- `KERNEL32!GlobalFree` at `0x180055963`
- `KERNEL32!GlobalFree` at `0x180055a14`
- `KERNEL32!GlobalFree` at `0x180055a4b`
- `KERNEL32!GlobalFree` at `0x180055a65`
- `KERNEL32!GlobalFree` at `0x180055a93`
- `KERNEL32!GlobalFree` at `0x180055aee`
- `KERNEL32!GlobalFree` at `0x180055b08`
- `KERNEL32!GlobalFree` at `0x180055b39`
- `KERNEL32!GlobalFree` at `0x180055b88`
- `KERNEL32!GlobalFree` at `0x180055ba2`
- `KERNEL32!GlobalFree` at `0x180055bc2`
- `KERNEL32!GlobalFree` at `0x180055c11`
- `KERNEL32!GlobalFree` at `0x180055c2b`
- `KERNEL32!GlobalFree` at `0x180055c4b`
- `KERNEL32!GlobalFree` at `0x180055c7e`
- `KERNEL32!GlobalFree` at `0x180055ccd`
- `KERNEL32!GlobalFree` at `0x180055ce7`
- `KERNEL32!GlobalFree` at `0x180055d28`
- `KERNEL32!GlobalFree` at `0x180055d42`
- `KERNEL32!GlobalFree` at `0x180055d85`
- `KERNEL32!GlobalFree` at `0x180055d9f`
- `KERNEL32!GlobalFree` at `0x180055dfc`
- `KERNEL32!GlobalFree` at `0x180055e16`
- `KERNEL32!GlobalFree` at `0x180055e53`
- `KERNEL32!GlobalFree` at `0x180055e6d`
- `KERNEL32!GlobalFree` at `0x180055eb3`
- `KERNEL32!GlobalFree` at `0x180055ecd`

## pseudocode

```c

```
