# TraceFileW(long,ushort *,ushort const *,uint)

- ea: `0x1800206c4`
- end: `0x180020785`
- name: `?TraceFileW@@YAXJPEAGPEBGI@Z`
- size: `193`
- prototype: `void __fastcall(int, unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `7`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18001ebdc`
- `0x18002003c`
- `0x180020120`
- `0x1800202f8`
- `0x18008571c`
- `0x1800857c0`
- `0x1800858a4`

## callees

- `0x1800152f8`
- `0x1800206c4`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800206f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800206f9`
- `msvcrt!fclose` at `0x180020764`
- `msvcrt!fclose` at `0x180020764`
- `msvcrt!fflush` at `0x18002075b`
- `msvcrt!fflush` at `0x18002075b`
- `msvcrt!fwprintf` at `0x180020752`
- `msvcrt!fwprintf` at `0x180020752`

## string_xrefs

- `0x180020746`: `%02ld-%02ld-%04ld %02ld:%02ld : DTC Install error = %d, %s, %s (%d) \n`

## pseudocode

```c

```
