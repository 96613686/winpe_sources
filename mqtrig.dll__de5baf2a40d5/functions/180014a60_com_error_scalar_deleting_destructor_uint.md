# _com_error::`scalar deleting destructor'(uint)

- ea: `0x180014a60`
- end: `0x180014a8f`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `47`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180014a1c`
- `0x180014a60`
- `0x180014b34`

## pseudocode

```c
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  _com_error::~_com_error(this);
  if ( (a2 & 1) != 0 )
    MmDeallocate(this);
  return this;
}

```

## disassembly

```asm
0x180014a60  mov     [rsp+arg_0], rbx
0x180014a65  push    rdi
0x180014a66  sub     rsp, 20h
0x180014a6a  mov     ebx, edx
0x180014a6c  mov     rdi, rcx
0x180014a6f  call    ??1_com_error@@UEAA@XZ; _com_error::~_com_error(void)
0x180014a74  test    bl, 1
0x180014a77  jz      short loc_180014A81
0x180014a79  mov     rcx, rdi; void *
0x180014a7c  call    ?MmDeallocate@@YAXPEAX@Z; MmDeallocate(void *)
0x180014a81  mov     rbx, [rsp+28h+arg_0]
0x180014a86  mov     rax, rdi
0x180014a89  add     rsp, 20h
0x180014a8d  pop     rdi
0x180014a8e  retn
```
