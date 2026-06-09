# CommandLineData::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *,uint *)

- ea: `0x140054274`
- end: `0x140054430`
- name: `?ConvertMultiByteToWideChar@CommandLineData@@AEAAJPEAEKPEAPEAGPEAI@Z`
- size: `444`
- prototype: `int(CommandLineData *__hidden this, unsigned __int8 *, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140056130`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000cffc`
- `0x140054274`
- `0x1400b1d80`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140054407`
- `KERNEL32!LocalFree` at `0x140054407`
- `KERNEL32!MultiByteToWideChar` at `0x1400542a7`
- `KERNEL32!MultiByteToWideChar` at `0x140054393`
- `KERNEL32!MultiByteToWideChar` at `0x1400542a7`
- `KERNEL32!MultiByteToWideChar` at `0x140054393`
- `KERNEL32!GetLastError` at `0x1400542b5`
- `KERNEL32!GetLastError` at `0x14005439f`
- `KERNEL32!GetLastError` at `0x1400542b5`
- `KERNEL32!GetLastError` at `0x14005439f`

## pseudocode

```c

```
