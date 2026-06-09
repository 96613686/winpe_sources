# UtilExecutionEngine::CreateManualEvent(int)

- ea: `0x180040760`
- end: `0x180040773`
- name: `?CreateManualEvent@UtilExecutionEngine@@EEAAPEAXH@Z`
- size: `19`
- prototype: `void *__fastcall(UtilExecutionEngine *__hidden this, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18004076c`

## pseudocode

```c
HANDLE __fastcall UtilExecutionEngine::CreateManualEvent(UtilExecutionEngine *this, BOOL a2)
{
  return CreateEventW(0, 1, a2, 0);
}

```

## disassembly

```asm
0x180040760  xor     r9d, r9d
0x180040763  mov     r8d, edx
0x180040766  xor     ecx, ecx
0x180040768  lea     edx, [r9+1]
0x18004076c  jmp     cs:__imp_CreateEventW
```
