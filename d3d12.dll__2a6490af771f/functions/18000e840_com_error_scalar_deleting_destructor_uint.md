# _com_error::`scalar deleting destructor'(uint)

- ea: `0x18000e840`
- end: `0x18000e874`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(_com_error *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180008a28`
- `0x18000b7e0`
- `0x18000e840`

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
0x18000e840  mov     [rsp+arg_0], rbx
0x18000e845  push    rdi
0x18000e846  sub     rsp, 20h
0x18000e84a  mov     ebx, edx
0x18000e84c  mov     rdi, rcx
0x18000e84f  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x18000e854  test    bl, 1
0x18000e857  jz      short loc_18000E866
0x18000e859  mov     edx, 20h ; ' '
0x18000e85e  mov     rcx, rdi; Block
0x18000e861  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e866  mov     rbx, [rsp+28h+arg_0]
0x18000e86b  mov     rax, rdi
0x18000e86e  add     rsp, 20h
0x18000e872  pop     rdi
0x18000e873  retn
```
