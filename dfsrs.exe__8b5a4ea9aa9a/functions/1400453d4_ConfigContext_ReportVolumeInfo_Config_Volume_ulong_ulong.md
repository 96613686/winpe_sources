# ConfigContext::ReportVolumeInfo(Config::Volume *,ulong,ulong)

- ea: `0x1400453d4`
- end: `0x140045676`
- name: `?ReportVolumeInfo@ConfigContext@@IEAAXPEAVVolume@Config@@KK@Z`
- size: `674`
- prototype: `void(ConfigContext *__hidden this, struct Config::Volume *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x1400461d4`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000daa0`
- `0x140022d1c`
- `0x1400453d4`
- `0x1400677e8`
- `0x140067e78`
- `0x140068058`
- `0x1400681bc`
- `0x140069130`
- `0x140069684`
- `0x14006a550`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x140045439`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140045576`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140045439`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140045576`
- `KERNEL32!LeaveCriticalSection` at `0x1400454e7`
- `KERNEL32!LeaveCriticalSection` at `0x14004561c`
- `KERNEL32!LeaveCriticalSection` at `0x1400454e7`
- `KERNEL32!LeaveCriticalSection` at `0x14004561c`
- `KERNEL32!EnterCriticalSection` at `0x140045453`
- `KERNEL32!EnterCriticalSection` at `0x140045590`
- `KERNEL32!EnterCriticalSection` at `0x140045453`
- `KERNEL32!EnterCriticalSection` at `0x140045590`

## string_xrefs

- `0x140045469`: `ConfigContext::ReportVolumeInfo`
- `0x1400454a9`: `Update volumeInfoHistory`
- `0x1400455df`: `Update contentInfoHistory`

## pseudocode

```c

```
