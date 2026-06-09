# RtlNtStatusToDosError_0

- ea: `0x180001ee2`
- end: `0x180001ee8`
- name: `RtlNtStatusToDosError_0`
- size: `6`
- prototype: `ULONG __stdcall(NTSTATUS Status)`
- caller_count: `23`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180004cb8`
- `0x1800052b4`
- `0x1800099c0`
- `0x18000a300`
- `0x18000b5f0`
- `0x18000bbe0`
- `0x18000c4a0`
- `0x18000d5f0`
- `0x18000d780`
- `0x18000de40`
- `0x18000ef18`
- `0x18000fc74`
- `0x18000ff6c`
- `0x180012f80`
- `0x180013084`
- `0x180013284`
- `0x18001349c`
- `0x180013504`
- `0x1800137e4`
- `0x1800138d0`
- `0x180013bc8`
- `0x18001502c`
- `0x18001526c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180001ee2`

## pseudocode

```c
// attributes: thunk
ULONG __stdcall RtlNtStatusToDosError_0(NTSTATUS Status)
{
  return RtlNtStatusToDosError(Status);
}

```

## disassembly

```asm
0x180001ee2  jmp     cs:__imp_RtlNtStatusToDosError
```
