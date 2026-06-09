# UtilExecutionEngine::CreateManualEvent(int)

- ea: `0x140011430`
- end: `0x140011443`
- name: `?CreateManualEvent@UtilExecutionEngine@@EEAAPEAXH@Z`
- size: `19`
- prototype: `HANDLE __fastcall(UtilExecutionEngine *this, BOOL)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14001143c`

## pseudocode

```c
HANDLE __fastcall UtilExecutionEngine::CreateManualEvent(UtilExecutionEngine *this, BOOL a2)
{
  return CreateEventW(0, 1, a2, 0);
}

```

## disassembly

```asm
0x140011430  xor     r9d, r9d
0x140011433  mov     r8d, edx
0x140011436  xor     ecx, ecx
0x140011438  lea     edx, [r9+1]
0x14001143c  jmp     cs:__imp_CreateEventW
```
