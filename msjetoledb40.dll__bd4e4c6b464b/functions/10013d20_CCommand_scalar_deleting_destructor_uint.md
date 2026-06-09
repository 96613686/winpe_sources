# CCommand::`scalar deleting destructor'(uint)

- ea: `0x10013d20`
- end: `0x10013d43`
- name: `??_GCCommand@@UAEPAXI@Z`
- size: `35`
- prototype: `void *__thiscall(CCommand *__hidden this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x10013d20`
- `0x10013d50`
- `0x1004cea1`

## pseudocode

```c
CCommand *__thiscall CCommand::`scalar deleting destructor'(CCommand *this, char a2)
{
  CCommand::~CCommand(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x10013d20  mov     edi, edi
0x10013d22  push    ebp
0x10013d23  mov     ebp, esp
0x10013d25  push    esi
0x10013d26  mov     esi, ecx
0x10013d28  call    ??1CCommand@@UAE@XZ; CCommand::~CCommand(void)
0x10013d2d  test    [ebp+arg_0], 1
0x10013d31  jz      short loc_10013D3C
0x10013d33  push    esi; Block
0x10013d34  call    ??3@YAXPAX@Z; operator delete(void *)
0x10013d39  add     esp, 4
0x10013d3c  mov     eax, esi
0x10013d3e  pop     esi
0x10013d3f  pop     ebp
0x10013d40  retn    4
```
