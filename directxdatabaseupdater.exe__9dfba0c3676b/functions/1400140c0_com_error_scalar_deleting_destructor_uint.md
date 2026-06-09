# _com_error::`scalar deleting destructor'(uint)

- ea: `0x1400140c0`
- end: `0x1400140f4`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `52`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140003218`
- `0x140014074`
- `0x1400140c0`

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
0x1400140c0  mov     [rsp+arg_0], rbx
0x1400140c5  push    rdi
0x1400140c6  sub     rsp, 20h
0x1400140ca  mov     ebx, edx
0x1400140cc  mov     rdi, rcx
0x1400140cf  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x1400140d4  test    bl, 1
0x1400140d7  jz      short loc_1400140E6
0x1400140d9  mov     edx, 20h ; ' '; unsigned __int64
0x1400140de  mov     rcx, rdi; void *
0x1400140e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400140e6  mov     rbx, [rsp+28h+arg_0]
0x1400140eb  mov     rax, rdi
0x1400140ee  add     rsp, 20h
0x1400140f2  pop     rdi
0x1400140f3  retn
```
