# UtilExecutionEngine::ClrCreateSemaphore(ulong,ulong)

- ea: `0x1400114c0`
- end: `0x1400114cc`
- name: `?ClrCreateSemaphore@UtilExecutionEngine@@EEAAPEAXKK@Z`
- size: `12`
- prototype: `HANDLE __fastcall(UtilExecutionEngine *this, LONG, LONG)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!CreateSemaphoreW` at `0x1400114c5`

## pseudocode

```c
HANDLE __fastcall UtilExecutionEngine::ClrCreateSemaphore(UtilExecutionEngine *this, LONG a2, LONG a3)
{
  return CreateSemaphoreW(0, a2, a3, 0);
}

```

## disassembly

```asm
0x1400114c0  xor     r9d, r9d
0x1400114c3  xor     ecx, ecx
0x1400114c5  jmp     cs:__imp_CreateSemaphoreW
```
