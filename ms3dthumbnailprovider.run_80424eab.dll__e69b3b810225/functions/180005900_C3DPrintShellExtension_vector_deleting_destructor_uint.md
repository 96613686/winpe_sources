# C3DPrintShellExtension::`vector deleting destructor'(uint)

- ea: `0x180005900`
- end: `0x180005934`
- name: `??_EC3DPrintShellExtension@@EEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(C3DPrintShellExtension *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180001f44`
- `0x180005470`
- `0x180005900`

## pseudocode

```c
C3DPrintShellExtension *__fastcall C3DPrintShellExtension::`vector deleting destructor'(
        C3DPrintShellExtension *this,
        char a2)
{
  C3DPrintShellExtension::~C3DPrintShellExtension(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005900  mov     [rsp+arg_0], rbx
0x180005905  push    rdi
0x180005906  sub     rsp, 20h
0x18000590a  mov     ebx, edx
0x18000590c  mov     rdi, rcx
0x18000590f  call    ??1C3DPrintShellExtension@@EEAA@XZ; C3DPrintShellExtension::~C3DPrintShellExtension(void)
0x180005914  test    bl, 1
0x180005917  jz      short loc_180005926
0x180005919  mov     edx, 28h ; '('
0x18000591e  mov     rcx, rdi; Block
0x180005921  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005926  mov     rbx, [rsp+28h+arg_0]
0x18000592b  mov     rax, rdi
0x18000592e  add     rsp, 20h
0x180005932  pop     rdi
0x180005933  retn
```
