# sqlencrypt::SqlSecurityUtility::DecryptCEK(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,sqlencrypt::EncryptionKeyInfo &,uchar * *,ushort *,sqlencrypt::SymmetricKeyCache * &,ulong,sqlencrypt::OnEncryptionError *)

- ea: `0x10047cc4c`
- end: `0x10047d0bf`
- name: `?DecryptCEK@SqlSecurityUtility@sqlencrypt@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUEncryptionKeyInfo@2@PEAPEAEPEAGAEAPEAVSymmetricKeyCache@2@KPEAUOnEncryptionError@2@@Z`
- size: `1139`
- prototype: `__int64 __fastcall(int, int, int, int, struct sqlencrypt::SymmetricKeyCache **, int, struct sqlencrypt::OnEncryptionError *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1004c7328`

## callees

- `0x10046d6fc`
- `0x1004725b4`
- `0x10047c5c8`
- `0x10047cc4c`
- `0x10047d83c`
- `0x10047f838`
- `0x10047f8e8`
- `0x100481568`
- `0x1004815fc`
- `0x100481650`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x10047cfcb`
- `KERNEL32!LocalAlloc` at `0x10047cfcb`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10047cfe5`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10047cfe5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10047d029`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x10047d029`

## pseudocode

```c

```
