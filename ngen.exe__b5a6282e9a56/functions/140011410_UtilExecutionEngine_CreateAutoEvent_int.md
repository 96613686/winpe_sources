# UtilExecutionEngine::CreateAutoEvent(int)

- ea: `0x140011410`
- end: `0x140011421`
- name: `?CreateAutoEvent@UtilExecutionEngine@@EEAAPEAXH@Z`
- size: `17`
- prototype: `HANDLE __fastcall(UtilExecutionEngine *this, BOOL)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14001141a`

## pseudocode

```c
HANDLE __fastcall UtilExecutionEngine::CreateAutoEvent(UtilExecutionEngine *this, BOOL a2)
{
  return CreateEventW(0, 0, a2, 0);
}

```

## disassembly

```asm
0x140011410  mov     r8d, edx
0x140011413  xor     r9d, r9d
0x140011416  xor     edx, edx
0x140011418  xor     ecx, ecx
0x14001141a  jmp     cs:__imp_CreateEventW
```
