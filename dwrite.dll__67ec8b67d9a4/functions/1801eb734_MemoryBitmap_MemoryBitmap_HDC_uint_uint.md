# MemoryBitmap::MemoryBitmap(HDC__ *,uint,uint)

- ea: `0x1801eb734`
- end: `0x1801eb879`
- name: `??0MemoryBitmap@@QEAA@PEAUHDC__@@II@Z`
- size: `325`
- prototype: `MemoryBitmap *(MemoryBitmap *__hidden this, HDC, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1801eb5bc`
- `0x1802328d0`

## callees

- `0x1801eb734`
- `0x1801f37b0`
- `0x18020bc10`
- `0x18020c3b0`
- `0x180212490`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801eb7dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801eb7dd`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1801eb80a`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1801eb80a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801eb83f`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801eb83f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
MemoryBitmap *__fastcall MemoryBitmap::MemoryBitmap(MemoryBitmap *this, HDC a2, unsigned int a3, unsigned int a4)
{
  HBITMAP v6; // rdi
  GdiException *v7; // rax
  void *ppvBits; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v10[8]; // [rsp+38h] [rbp-48h] BYREF
  MemoryBitmap *v11; // [rsp+40h] [rbp-40h]
  BITMAPINFO pbmi; // [rsp+48h] [rbp-38h] BYREF

  v11 = this;
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = a3;
  *((_DWORD *)this + 3) = a4;
  *((_QWORD *)this + 2) = 0;
  if ( a3 && a4 )
  {
    memset(&pbmi.bmiHeader.biWidth, 0, 40);
    pbmi.bmiHeader.biSize = 40;
    if ( a3 > 0x7FFFFFFF || (pbmi.bmiHeader.biWidth = a3, a4 > 0x7FFFFFFF) || a4 == 0x80000000 )
      SafeIntExceptionHandler<Exception>::SafeIntOnOverflow();
    pbmi.bmiHeader.biHeight = -a4;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    SetLastError(0);
    ppvBits = 0;
    v6 = CreateDIBSection(a2, &pbmi, 0, &ppvBits, 0, 0);
    if ( !v6 )
    {
      v7 = GdiException::GdiException((GdiException *)v10);
      LogAndThrow<GdiException>(v7, 0x706D626D656DLL, 32);
    }
    if ( *(_QWORD *)this )
      DeleteObject(*(HGDIOBJ *)this);
    *(_QWORD *)this = v6;
    *((_QWORD *)this + 2) = ppvBits;
  }
  return this;
}

```

## disassembly

```asm
0x1801eb734  mov     [rsp-18h+arg_10], rbx
0x1801eb739  push    rbp
0x1801eb73a  push    rdi
0x1801eb73b  push    r14
0x1801eb73d  mov     rbp, rsp
0x1801eb740  sub     rsp, 80h
0x1801eb747  mov     rax, cs:__security_cookie
0x1801eb74e  xor     rax, rsp
0x1801eb751  mov     [rbp+var_8], rax
0x1801eb755  mov     rdi, rdx
0x1801eb758  mov     rbx, rcx
0x1801eb75b  mov     [rbp+var_40], rcx
0x1801eb75f  mov     qword ptr [rcx], 0
0x1801eb766  mov     [rcx+8], r8d
0x1801eb76a  mov     [rcx+0Ch], r9d
0x1801eb76e  mov     qword ptr [rcx+10h], 0
0x1801eb776  test    r8d, r8d
0x1801eb779  jz      loc_1801EB850
0x1801eb77f  test    r9d, r9d
0x1801eb782  jz      loc_1801EB850
0x1801eb788  xorps   xmm0, xmm0
0x1801eb78b  xor     eax, eax
0x1801eb78d  movups  xmmword ptr [rbp+pbmi.bmiHeader.biWidth], xmm0
0x1801eb791  movups  xmmword ptr [rbp+pbmi.bmiHeader.biSizeImage], xmm0
0x1801eb795  mov     qword ptr [rbp+pbmi.bmiHeader.biClrImportant], rax
0x1801eb799  mov     [rbp+pbmi.bmiHeader.biSize], 28h ; '('
0x1801eb7a0  mov     eax, 7FFFFFFFh
0x1801eb7a5  cmp     r8d, eax
0x1801eb7a8  ja      loc_1801EB873
0x1801eb7ae  mov     [rbp+pbmi.bmiHeader.biWidth], r8d
0x1801eb7b2  cmp     r9d, eax
0x1801eb7b5  ja      loc_1801EB873
0x1801eb7bb  cmp     r9d, 80000000h
0x1801eb7c2  jz      loc_1801EB873
0x1801eb7c8  neg     r9d
0x1801eb7cb  mov     [rbp+pbmi.bmiHeader.biHeight], r9d
0x1801eb7cf  mov     qword ptr [rbp+pbmi.bmiHeader.biPlanes], 200001h
0x1801eb7d7  xor     ecx, ecx; dwErrCode
0x1801eb7d9  lea     r14d, [rcx+20h]
0x1801eb7dd  call    cs:__imp_SetLastError
0x1801eb7e3  mov     [rbp+ppvBits], 0
0x1801eb7eb  mov     [rsp+80h+offset], 0; offset
0x1801eb7f3  mov     [rsp+80h+hSection], 0; hSection
0x1801eb7fc  lea     r9, [rbp+ppvBits]; ppvBits
0x1801eb800  xor     r8d, r8d; usage
0x1801eb803  lea     rdx, [rbp+pbmi]; pbmi
0x1801eb807  mov     rcx, rdi; hdc
0x1801eb80a  call    cs:__imp_CreateDIBSection
0x1801eb810  mov     rdi, rax
0x1801eb813  test    rax, rax
0x1801eb816  jnz     short loc_1801EB837
0x1801eb818  lea     rcx, [rbp+var_48]; this
0x1801eb81c  call    ??0GdiException@@QEAA@XZ; GdiException::GdiException(void)
0x1801eb821  mov     rdx, 706D626D656Dh
0x1801eb82b  mov     r8d, r14d
0x1801eb82e  mov     rcx, rax
0x1801eb831  call    ??$LogAndThrow@VGdiException@@@@YAXAEBVGdiException@@VEventTag@@I@Z; LogAndThrow<GdiException>(GdiException const &,EventTag,uint)
0x1801eb837  mov     rcx, [rbx]; ho
0x1801eb83a  test    rcx, rcx
0x1801eb83d  jz      short loc_1801EB845
0x1801eb83f  call    cs:__imp_DeleteObject
0x1801eb845  mov     [rbx], rdi
0x1801eb848  mov     rax, [rbp+ppvBits]
0x1801eb84c  mov     [rbx+10h], rax
0x1801eb850  mov     rax, rbx
0x1801eb853  mov     rcx, [rbp+var_8]
0x1801eb857  xor     rcx, rsp; StackCookie
0x1801eb85a  call    __security_check_cookie
0x1801eb85f  mov     rbx, [rsp+80h+arg_10]
0x1801eb867  add     rsp, 80h
0x1801eb86e  pop     r14
0x1801eb870  pop     rdi
0x1801eb871  pop     rbp
0x1801eb872  retn
0x1801eb873  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
```
