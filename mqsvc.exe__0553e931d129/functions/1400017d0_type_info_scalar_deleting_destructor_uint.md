# type_info::`scalar deleting destructor'(uint)

- ea: `0x1400017d0`
- end: `0x140001800`
- name: `??_Gtype_info@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(type_info *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1400017d0`
- `0x14000181c`

## import_xrefs

- `msvcrt!??1type_info@@UEAA@XZ` at `0x1400017df`
- `msvcrt!??1type_info@@UEAA@XZ` at `0x1400017df`

## pseudocode

```c
type_info *__fastcall type_info::`scalar deleting destructor'(type_info *this, char a2)
{
  type_info::~type_info(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1400017d0  mov     [rsp+arg_0], rbx
0x1400017d5  push    rdi
0x1400017d6  sub     rsp, 20h
0x1400017da  mov     ebx, edx
0x1400017dc  mov     rdi, rcx
0x1400017df  call    cs:__imp_??1type_info@@UEAA@XZ; type_info::~type_info(void)
0x1400017e5  test    bl, 1
0x1400017e8  jz      short loc_1400017F2
0x1400017ea  mov     rcx, rdi; void *
0x1400017ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400017f2  mov     rbx, [rsp+28h+arg_0]
0x1400017f7  mov     rax, rdi
0x1400017fa  add     rsp, 20h
0x1400017fe  pop     rdi
0x1400017ff  retn
```
