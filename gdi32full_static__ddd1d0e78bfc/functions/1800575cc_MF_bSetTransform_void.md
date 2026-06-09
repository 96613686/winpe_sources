# MF::bSetTransform(void *)

- ea: `0x1800575cc`
- end: `0x180057669`
- name: `?bSetTransform@MF@@QEAAHPEAX@Z`
- size: `157`
- prototype: `int(MF *__hidden this, void *)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800566e0`
- `0x180056770`
- `0x1800567f0`
- `0x180057140`
- `0x1800571d0`
- `0x180057240`
- `0x1800572b0`
- `0x180057380`
- `0x180096b10`
- `0x180096bb0`
- `0x180096de0`

## callees

- `0x1800575cc`
- `0x18007f800`

## import_xrefs

- `GDI32!SetWorldTransform` at `0x180057640`
- `GDI32!SetWorldTransform` at `0x180057640`
- `win32u!NtGdiGetTransform` at `0x18005760b`
- `win32u!NtGdiGetTransform` at `0x18005760b`
- `win32u!NtGdiCombineTransform` at `0x180057628`
- `win32u!NtGdiCombineTransform` at `0x180057628`

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
0x1800575cc  mov     [rsp+arg_10], rbx
0x1800575d1  push    rdi
0x1800575d2  sub     rsp, 40h
0x1800575d6  mov     rax, cs:__security_cookie
0x1800575dd  xor     rax, rsp
0x1800575e0  mov     [rsp+48h+var_10], rax
0x1800575e5  mov     rdi, rdx
0x1800575e8  lea     r8, [rsp+48h+xf]
0x1800575ed  mov     rbx, rcx
0x1800575f0  xorps   xmm0, xmm0
0x1800575f3  mov     rcx, [rcx+2D8h]
0x1800575fa  xor     eax, eax
0x1800575fc  mov     edx, 204h
0x180057601  mov     qword ptr [rsp+48h+xf.eDx], rax
0x180057606  movups  xmmword ptr [rsp+48h+xf.eM11], xmm0
0x18005760b  call    cs:__imp_NtGdiGetTransform
0x180057612  nop     dword ptr [rax+rax+00h]
0x180057617  lea     r8, [rbx+2C0h]
0x18005761e  lea     rdx, [rsp+48h+xf]
0x180057623  lea     rcx, [rsp+48h+xf]
0x180057628  call    cs:__imp_NtGdiCombineTransform
0x18005762f  nop     dword ptr [rax+rax+00h]
0x180057634  test    eax, eax
0x180057636  jz      short loc_180057665
0x180057638  lea     rdx, [rsp+48h+xf]; lpxf
0x18005763d  mov     rcx, rdi; hdc
0x180057640  call    cs:__imp_SetWorldTransform
0x180057647  nop     dword ptr [rax+rax+00h]
0x18005764c  mov     rcx, [rsp+48h+var_10]
0x180057651  xor     rcx, rsp; StackCookie
0x180057654  call    __security_check_cookie
0x180057659  mov     rbx, [rsp+48h+arg_10]
0x18005765e  add     rsp, 40h
0x180057662  pop     rdi
0x180057663  retn
0x180057665  xor     eax, eax
0x180057667  jmp     short loc_18005764C
```
