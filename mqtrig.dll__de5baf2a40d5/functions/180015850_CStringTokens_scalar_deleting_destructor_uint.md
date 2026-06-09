# CStringTokens::`scalar deleting destructor'(uint)

- ea: `0x180015850`
- end: `0x180015881`
- name: `??_GCStringTokens@@UEAAPEAXI@Z`
- size: `49`
- prototype: `CStringTokens *__fastcall(CStringTokens *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800157fc`
- `0x180015850`

## import_xrefs

- `msvcrt!free` at `0x18001586c`
- `msvcrt!free` at `0x18001586c`

## pseudocode

```c
CStringTokens *__fastcall CStringTokens::`scalar deleting destructor'(CStringTokens *this, char a2)
{
  CStringTokens::~CStringTokens(this);
  if ( (a2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x180015850  mov     [rsp+arg_0], rbx
0x180015855  push    rdi
0x180015856  sub     rsp, 20h
0x18001585a  mov     ebx, edx
0x18001585c  mov     rdi, rcx
0x18001585f  call    ??1CStringTokens@@UEAA@XZ; CStringTokens::~CStringTokens(void)
0x180015864  test    bl, 1
0x180015867  jz      short loc_180015873
0x180015869  mov     rcx, rdi; Block
0x18001586c  call    cs:__imp_free
0x180015872  nop
0x180015873  mov     rax, rdi
0x180015876  mov     rbx, [rsp+28h+arg_0]
0x18001587b  add     rsp, 20h
0x18001587f  pop     rdi
0x180015880  retn
```
