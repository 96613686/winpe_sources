# _com_error::`scalar deleting destructor'(uint)

- ea: `0x18001b300`
- end: `0x18001b330`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(_com_error *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001b2b4`
- `0x18001b300`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18001b31c`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18001b31c`

## pseudocode

```c
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  _com_error::~_com_error(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001b300  mov     [rsp+arg_0], rbx
0x18001b305  push    rdi
0x18001b306  sub     rsp, 20h
0x18001b30a  mov     ebx, edx
0x18001b30c  mov     rdi, rcx
0x18001b30f  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x18001b314  test    bl, 1
0x18001b317  jz      short loc_18001B322
0x18001b319  mov     rcx, rdi
0x18001b31c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b322  mov     rbx, [rsp+28h+arg_0]
0x18001b327  mov     rax, rdi
0x18001b32a  add     rsp, 20h
0x18001b32e  pop     rdi
0x18001b32f  retn
```
