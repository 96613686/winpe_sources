# NtTraceControl_0

- ea: `0x180001eca`
- end: `0x180001ed0`
- name: `NtTraceControl_0`
- size: `6`
- prototype: ``
- caller_count: `14`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180008de0`
- `0x18000a300`
- `0x18000b5f0`
- `0x18000d780`
- `0x18000de40`
- `0x18000ef18`
- `0x18000ff24`
- `0x18000ff6c`
- `0x180013284`
- `0x18001349c`
- `0x180013504`
- `0x1800137e4`
- `0x1800138d0`
- `0x180013bc8`

## import_xrefs

- `ntdll!NtTraceControl` at `0x180001eca`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall NtTraceControl_0(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  return NtTraceControl(a1, a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x180001eca  jmp     cs:__imp_NtTraceControl
```
