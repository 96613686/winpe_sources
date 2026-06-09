# ProvideComponent(ushort const *,ushort const *,ushort const *,ulong,ushort *,ulong *,bool,CRFSCachedSourceInfo &)

- ea: `0x18004a530`
- end: `0x18004b48e`
- name: `?ProvideComponent@@YAIPEBG00KPEAGPEAK_NAEAVCRFSCachedSourceInfo@@@Z`
- size: `3934`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, DWORD dwReinstallMode, unsigned __int16 *, unsigned int *, bool, struct CRFSCachedSourceInfo *)`
- caller_count: `2`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180049774`
- `0x1801a0a90`

## callees

- `0x18000c4bc`
- `0x180013b7c`
- `0x1800398bc`
- `0x1800399d0`
- `0x180039bc4`
- `0x18003ae54`
- `0x18003bd60`
- `0x18003c030`
- `0x180044960`
- `0x1800459c0`
- `0x1800491f0`
- `0x18004a530`
- `0x18004b494`
- `0x18004c678`
- `0x180095d40`
- `0x180152b00`
- `0x180153670`
- `0x180159ff0`
- `0x18019bef0`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18004a6f5`
- `KERNEL32!InitializeCriticalSection` at `0x18004a6f5`
- `KERNEL32!lstrlenW` at `0x18004aa71`
- `KERNEL32!lstrlenW` at `0x18004aa71`
- `KERNEL32!GlobalFree` at `0x18004a61f`
- `KERNEL32!GlobalFree` at `0x18004a641`
- `KERNEL32!GlobalFree` at `0x18004a776`
- `KERNEL32!GlobalFree` at `0x18004a79a`
- `KERNEL32!GlobalFree` at `0x18004a8a3`
- `KERNEL32!GlobalFree` at `0x18004a8c3`
- `KERNEL32!GlobalFree` at `0x18004ab20`
- `KERNEL32!GlobalFree` at `0x18004ab54`
- `KERNEL32!GlobalFree` at `0x18004ac1d`
- `KERNEL32!GlobalFree` at `0x18004ac75`
- `KERNEL32!GlobalFree` at `0x18004ac95`
- `KERNEL32!GlobalFree` at `0x18004adc6`
- `KERNEL32!GlobalFree` at `0x18004ae6a`
- `KERNEL32!GlobalFree` at `0x18004ae9e`
- `KERNEL32!GlobalFree` at `0x18004af44`
- `KERNEL32!GlobalFree` at `0x18004af64`
- `KERNEL32!GlobalFree` at `0x18004af9c`
- `KERNEL32!GlobalFree` at `0x18004aff4`
- `KERNEL32!GlobalFree` at `0x18004b014`
- `KERNEL32!GlobalFree` at `0x18004b03a`
- `KERNEL32!GlobalFree` at `0x18004b09e`
- `KERNEL32!GlobalFree` at `0x18004b0be`
- `KERNEL32!GlobalFree` at `0x18004b0f5`
- `KERNEL32!GlobalFree` at `0x18004b14d`
- `KERNEL32!GlobalFree` at `0x18004b16d`
- `KERNEL32!GlobalFree` at `0x18004b193`
- `KERNEL32!GlobalFree` at `0x18004b1cc`
- `KERNEL32!GlobalFree` at `0x18004b224`
- `KERNEL32!GlobalFree` at `0x18004b244`
- `KERNEL32!GlobalFree` at `0x18004b28e`
- `KERNEL32!GlobalFree` at `0x18004b2ae`
- `KERNEL32!GlobalFree` at `0x18004b2fa`
- `KERNEL32!GlobalFree` at `0x18004b31a`
- `KERNEL32!GlobalFree` at `0x18004b388`
- `KERNEL32!GlobalFree` at `0x18004b3a8`
- `KERNEL32!GlobalFree` at `0x18004b3eb`
- `KERNEL32!GlobalFree` at `0x18004b40b`
- `KERNEL32!GlobalFree` at `0x18004b45a`
- `KERNEL32!GlobalFree` at `0x18004b47a`
- `KERNEL32!GlobalFree` at `0x18004a61f`
- `KERNEL32!GlobalFree` at `0x18004a641`
- `KERNEL32!GlobalFree` at `0x18004a776`
- `KERNEL32!GlobalFree` at `0x18004a79a`
- `KERNEL32!GlobalFree` at `0x18004a8a3`
- `KERNEL32!GlobalFree` at `0x18004a8c3`
- `KERNEL32!GlobalFree` at `0x18004ab20`
- `KERNEL32!GlobalFree` at `0x18004ab54`
- `KERNEL32!GlobalFree` at `0x18004ac1d`
- `KERNEL32!GlobalFree` at `0x18004ac75`
- `KERNEL32!GlobalFree` at `0x18004ac95`
- `KERNEL32!GlobalFree` at `0x18004adc6`
- `KERNEL32!GlobalFree` at `0x18004ae6a`
- `KERNEL32!GlobalFree` at `0x18004ae9e`
- `KERNEL32!GlobalFree` at `0x18004af44`
- `KERNEL32!GlobalFree` at `0x18004af64`
- `KERNEL32!GlobalFree` at `0x18004af9c`
- `KERNEL32!GlobalFree` at `0x18004aff4`
- `KERNEL32!GlobalFree` at `0x18004b014`
- `KERNEL32!GlobalFree` at `0x18004b03a`
- `KERNEL32!GlobalFree` at `0x18004b09e`
- `KERNEL32!GlobalFree` at `0x18004b0be`
- `KERNEL32!GlobalFree` at `0x18004b0f5`
- `KERNEL32!GlobalFree` at `0x18004b14d`
- `KERNEL32!GlobalFree` at `0x18004b16d`
- `KERNEL32!GlobalFree` at `0x18004b193`
- `KERNEL32!GlobalFree` at `0x18004b1cc`
- `KERNEL32!GlobalFree` at `0x18004b224`
- `KERNEL32!GlobalFree` at `0x18004b244`
- `KERNEL32!GlobalFree` at `0x18004b28e`
- `KERNEL32!GlobalFree` at `0x18004b2ae`
- `KERNEL32!GlobalFree` at `0x18004b2fa`
- `KERNEL32!GlobalFree` at `0x18004b31a`
- `KERNEL32!GlobalFree` at `0x18004b388`
- `KERNEL32!GlobalFree` at `0x18004b3a8`
- `KERNEL32!GlobalFree` at `0x18004b3eb`
- `KERNEL32!GlobalFree` at `0x18004b40b`
- `KERNEL32!GlobalFree` at `0x18004b45a`
- `KERNEL32!GlobalFree` at `0x18004b47a`

## pseudocode

```c

```
