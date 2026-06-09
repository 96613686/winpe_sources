# RealtimeProtection::CRtpDlpEngine::OnCloseFile(PPID const &,wchar_t const *,_MPDLP_ONCLOSE_TYPE,uchar,ulong)

- ea: `0x18004fa30`
- end: `0x1800502f7`
- name: `?OnCloseFile@CRtpDlpEngine@RealtimeProtection@@QEAAJAEBUPPID@@PEB_WW4_MPDLP_ONCLOSE_TYPE@@EK@Z`
- size: `2247`
- prototype: `int __high(const struct PPID *, const wchar_t *, enum _MPDLP_ONCLOSE_TYPE, unsigned __int8, unsigned int)`
- caller_count: `2`
- callee_count: `28`
- tags: ``

## callers

- `0x180050370`
- `0x18015f5bc`

## callees

- `0x18001b760`
- `0x180028a10`
- `0x180028d80`
- `0x18002a3a0`
- `0x18002b050`
- `0x18002b100`
- `0x18002dcc0`
- `0x180034420`
- `0x1800376e0`
- `0x180037754`
- `0x180038450`
- `0x18004f430`
- `0x18004fa30`
- `0x180050300`
- `0x18005cd40`
- `0x18005da68`
- `0x18006aa2c`
- `0x1800809d0`
- `0x180089fa0`
- `0x18009d750`
- `0x180100bb0`
- `0x180109324`
- `0x18010b558`
- `0x18010b568`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18023a290`
- `0x18023a6d0`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x18005015e`
- `MpClient!MpFreeMemory` at `0x18005015e`
- `KERNEL32!AcquireSRWLockShared` at `0x18004faa9`
- `KERNEL32!AcquireSRWLockShared` at `0x18004faa9`
- `KERNEL32!ReleaseSRWLockShared` at `0x18004fb1f`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800501a6`
- `KERNEL32!ReleaseSRWLockShared` at `0x18004fb1f`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800501a6`
- `KERNEL32!DebugBreak` at `0x1800500f8`
- `KERNEL32!DebugBreak` at `0x1800500f8`

## string_xrefs

- `0x18004fa84`: `MpDlp_DebugCheckAccessForFile`
- `0x180050097`: `MpDlp_DebugCheckAccessForFilePath`

## pseudocode

```c

```
