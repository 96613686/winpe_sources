# MspSetThreadOption

- ea: `0x180007740`
- end: `0x1800078bd`
- name: `MspSetThreadOption`
- size: `381`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, int, int, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180011090`
- `0x180012d10`

## callees

- `0x180006c50`
- `0x180007700`
- `0x180007740`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800077a5`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800077a5`
- `ntdll!RtlReleaseResource` at `0x180007854`
- `ntdll!RtlReleaseResource` at `0x180007854`

## pseudocode

```c

```
