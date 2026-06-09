# CIISGlobalModule::OnGlobalRSCAQuery(IGlobalRSCAQueryProvider *)

- ea: `0x1800029c0`
- end: `0x1800029c8`
- name: `?OnGlobalRSCAQuery@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalRSCAQueryProvider@@@Z`
- size: `8`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001cb4`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalRSCAQuery(__int64 a1, __int64 a2)
{
  return IIS_REQMON_CONTEXT::DumpRequests(a2);
}

```

## disassembly

```asm
0x1800029c0  mov     rcx, rdx
0x1800029c3  jmp     ?DumpRequests@IIS_REQMON_CONTEXT@@SA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalRSCAQueryProvider@@@Z; IIS_REQMON_CONTEXT::DumpRequests(IGlobalRSCAQueryProvider *)
```
