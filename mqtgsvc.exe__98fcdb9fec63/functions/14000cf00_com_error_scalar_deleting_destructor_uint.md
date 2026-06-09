# _com_error::`scalar deleting destructor'(uint)

- ea: `0x14000cf00`
- end: `0x14000cf31`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `49`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000ceb4`
- `0x14000cf00`

## import_xrefs

- `msvcrt!free` at `0x14000cf1c`
- `msvcrt!free` at `0x14000cf1c`

## pseudocode

```c
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  _com_error::~_com_error(this);
  if ( (a2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x14000cf00  mov     [rsp+arg_0], rbx
0x14000cf05  push    rdi
0x14000cf06  sub     rsp, 20h
0x14000cf0a  mov     ebx, edx
0x14000cf0c  mov     rdi, rcx
0x14000cf0f  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x14000cf14  test    bl, 1
0x14000cf17  jz      short loc_14000CF23
0x14000cf19  mov     rcx, rdi; Block
0x14000cf1c  call    cs:__imp_free
0x14000cf22  nop
0x14000cf23  mov     rax, rdi
0x14000cf26  mov     rbx, [rsp+28h+arg_0]
0x14000cf2b  add     rsp, 20h
0x14000cf2f  pop     rdi
0x14000cf30  retn
```
