# UtilExecutionEngine::CreateAutoEvent(int)

- ea: `0x180040740`
- end: `0x180040751`
- name: `?CreateAutoEvent@UtilExecutionEngine@@EEAAPEAXH@Z`
- size: `17`
- prototype: `void *__fastcall(UtilExecutionEngine *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18004074a`

## pseudocode

```c
HANDLE __fastcall UtilExecutionEngine::CreateAutoEvent(UtilExecutionEngine *this, BOOL a2)
{
  return CreateEventW(0, 0, a2, 0);
}

```

## disassembly

```asm
0x180040740  mov     r8d, edx
0x180040743  xor     r9d, r9d
0x180040746  xor     edx, edx
0x180040748  xor     ecx, ecx
0x18004074a  jmp     cs:__imp_CreateEventW
```
