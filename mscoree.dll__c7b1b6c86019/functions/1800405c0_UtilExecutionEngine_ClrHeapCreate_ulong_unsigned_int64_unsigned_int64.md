# UtilExecutionEngine::ClrHeapCreate(ulong,unsigned __int64,unsigned __int64)

- ea: `0x1800405c0`
- end: `0x1800405d2`
- name: `?ClrHeapCreate@UtilExecutionEngine@@EEAAPEAXK_K0@Z`
- size: `18`
- prototype: `void *__fastcall(UtilExecutionEngine *__hidden this, unsigned int, unsigned __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!HeapCreate` at `0x1800405cb`

## pseudocode

```c
HANDLE __fastcall UtilExecutionEngine::ClrHeapCreate(UtilExecutionEngine *this, DWORD a2, SIZE_T a3, SIZE_T a4)
{
  return HeapCreate(a2, a3, a4);
}

```

## disassembly

```asm
0x1800405c0  mov     rax, r8
0x1800405c3  mov     ecx, edx
0x1800405c5  mov     rdx, rax
0x1800405c8  mov     r8, r9
0x1800405cb  jmp     cs:__imp_HeapCreate
```
