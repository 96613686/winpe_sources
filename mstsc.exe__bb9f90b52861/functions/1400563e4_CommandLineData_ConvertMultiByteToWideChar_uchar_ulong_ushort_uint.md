# CommandLineData::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *,uint *)

- ea: `0x1400563e4`
- end: `0x1400565a0`
- name: `?ConvertMultiByteToWideChar@CommandLineData@@AEAAJPEAEKPEAPEAGPEAI@Z`
- size: `444`
- prototype: `int(CommandLineData *__hidden this, unsigned __int8 *, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400582a0`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000cffc`
- `0x1400563e4`
- `0x1400b3ef0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140056577`
- `KERNEL32!LocalFree` at `0x140056577`
- `KERNEL32!MultiByteToWideChar` at `0x140056417`
- `KERNEL32!MultiByteToWideChar` at `0x140056503`
- `KERNEL32!MultiByteToWideChar` at `0x140056417`
- `KERNEL32!MultiByteToWideChar` at `0x140056503`
- `KERNEL32!GetLastError` at `0x140056425`
- `KERNEL32!GetLastError` at `0x14005650f`
- `KERNEL32!GetLastError` at `0x140056425`
- `KERNEL32!GetLastError` at `0x14005650f`

## pseudocode

```c

```
