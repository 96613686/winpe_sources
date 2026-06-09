# UtilExecutionEngine::ClrHeapCreate(ulong,unsigned __int64,unsigned __int64)

- ea: `0x1400115e0`
- end: `0x1400115f2`
- name: `?ClrHeapCreate@UtilExecutionEngine@@EEAAPEAXK_K0@Z`
- size: `18`
- prototype: `HANDLE __fastcall(UtilExecutionEngine *this, DWORD, SIZE_T, SIZE_T)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!HeapCreate` at `0x1400115eb`

## pseudocode

```c
HANDLE __fastcall UtilExecutionEngine::ClrHeapCreate(UtilExecutionEngine *this, DWORD a2, SIZE_T a3, SIZE_T a4)
{
  return HeapCreate(a2, a3, a4);
}

```

## disassembly

```asm
0x1400115e0  mov     rax, r8
0x1400115e3  mov     ecx, edx
0x1400115e5  mov     rdx, rax
0x1400115e8  mov     r8, r9
0x1400115eb  jmp     cs:__imp_HeapCreate
```
