# UtilExecutionEngine::ClrCreateSemaphore(ulong,ulong)

- ea: `0x180040590`
- end: `0x18004059c`
- name: `?ClrCreateSemaphore@UtilExecutionEngine@@EEAAPEAXKK@Z`
- size: `12`
- prototype: `void *__fastcall(UtilExecutionEngine *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!CreateSemaphoreW` at `0x180040595`

## pseudocode

```c
HANDLE __fastcall UtilExecutionEngine::ClrCreateSemaphore(UtilExecutionEngine *this, LONG a2, LONG a3)
{
  return CreateSemaphoreW(0, a2, a3, 0);
}

```

## disassembly

```asm
0x180040590  xor     r9d, r9d
0x180040593  xor     ecx, ecx
0x180040595  jmp     cs:__imp_CreateSemaphoreW
```
