# MF::bSetTransform(void *)

- ea: `0x180051a7c`
- end: `0x180051b06`
- name: `?bSetTransform@MF@@QEAAHPEAX@Z`
- size: `138`
- prototype: `int(MF *__hidden this, void *)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180050c80`
- `0x180050d10`
- `0x180050d90`
- `0x180051610`
- `0x1800516a0`
- `0x180051710`
- `0x180051780`
- `0x180051850`
- `0x180090fb0`
- `0x180091050`
- `0x180091280`

## callees

- `0x180051a7c`
- `0x18007ac50`

## import_xrefs

- `GDI32!SetWorldTransform` at `0x180051ae4`
- `GDI32!SetWorldTransform` at `0x180051ae4`
- `win32u!NtGdiGetTransform` at `0x180051abb`
- `win32u!NtGdiGetTransform` at `0x180051abb`
- `win32u!NtGdiCombineTransform` at `0x180051ad2`
- `win32u!NtGdiCombineTransform` at `0x180051ad2`

## pseudocode

```c
BOOL __fastcall MF::bSetTransform(MF *this, HDC a2)
{
  __int64 v4; // rcx
  XFORM xf; // [rsp+20h] [rbp-28h] BYREF

  v4 = *((_QWORD *)this + 91);
  memset(&xf, 0, sizeof(xf));
  NtGdiGetTransform(v4, 516, &xf);
  return (unsigned int)NtGdiCombineTransform(&xf, &xf, (char *)this + 704) && SetWorldTransform(a2, &xf);
}

```

## disassembly

```asm
0x180051a7c  mov     [rsp+arg_10], rbx
0x180051a81  push    rdi
0x180051a82  sub     rsp, 40h
0x180051a86  mov     rax, cs:__security_cookie
0x180051a8d  xor     rax, rsp
0x180051a90  mov     [rsp+48h+var_10], rax
0x180051a95  mov     rdi, rdx
0x180051a98  lea     r8, [rsp+48h+xf]
0x180051a9d  mov     rbx, rcx
0x180051aa0  xorps   xmm0, xmm0
0x180051aa3  mov     rcx, [rcx+2D8h]
0x180051aaa  xor     eax, eax
0x180051aac  mov     edx, 204h
0x180051ab1  mov     qword ptr [rsp+48h+xf.eDx], rax
0x180051ab6  movups  xmmword ptr [rsp+48h+xf.eM11], xmm0
0x180051abb  call    cs:__imp_NtGdiGetTransform
0x180051ac1  lea     r8, [rbx+2C0h]
0x180051ac8  lea     rdx, [rsp+48h+xf]
0x180051acd  lea     rcx, [rsp+48h+xf]
0x180051ad2  call    cs:__imp_NtGdiCombineTransform
0x180051ad8  test    eax, eax
0x180051ada  jz      short loc_180051B02
0x180051adc  lea     rdx, [rsp+48h+xf]; lpxf
0x180051ae1  mov     rcx, rdi; hdc
0x180051ae4  call    cs:__imp_SetWorldTransform
0x180051aea  mov     rcx, [rsp+48h+var_10]
0x180051aef  xor     rcx, rsp; StackCookie
0x180051af2  call    __security_check_cookie
0x180051af7  mov     rbx, [rsp+48h+arg_10]
0x180051afc  add     rsp, 40h
0x180051b00  pop     rdi
0x180051b01  retn
0x180051b02  xor     eax, eax
0x180051b04  jmp     short loc_180051AEA
```
