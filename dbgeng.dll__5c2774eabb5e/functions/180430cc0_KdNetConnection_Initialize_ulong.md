# KdNetConnection::Initialize(ulong *)

- ea: `0x180430cc0`
- end: `0x180431020`
- name: `?Initialize@KdNetConnection@@UEAAJPEAK@Z`
- size: `864`
- prototype: `__int64 __fastcall(KdNetConnection *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x18007cf9c`
- `0x18008d550`
- `0x1800db578`
- `0x1800f0f40`
- `0x1800f2998`
- `0x180430c80`
- `0x180430cc0`
- `0x180435b28`
- `0x180437240`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x180430db1`
- `ntdll!RtlGetVersion` at `0x180430db1`
- `ntdll!RtlGetNtProductType` at `0x180430d85`
- `ntdll!RtlGetNtProductType` at `0x180430d85`
- `ntdll!NtSetTimerResolution` at `0x180430f72`
- `ntdll!NtSetTimerResolution` at `0x180430f72`
- `WS2_32!__imp_WSAStartup` at `0x180430e33`
- `WS2_32!__imp_WSAStartup` at `0x180430e33`

## string_xrefs

- `0x180430e45`: `Failed to open WinSock.  Error 0n%d\n`
- `0x180430e0f`: `Failed to initialize link encryption.  Error 0n%d\n`
- `0x180430e6a`: `Opened %hs\n`
- `0x180430f28`: `Will attempt to connect on IPv4 only.\n`

## pseudocode

```c

```
