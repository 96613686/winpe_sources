# CSourceBitsDIBSection::CSourceBitsDIBSection(DXGI_SURFACE_DESC const &,HDC__ * *)

- ea: `0x180084d4c`
- end: `0x180084e91`
- name: `??0CSourceBitsDIBSection@@QEAA@AEBUDXGI_SURFACE_DESC@@PEAPEAUHDC__@@@Z`
- size: `325`
- prototype: `CSourceBitsDIBSection *__fastcall(CSourceBitsDIBSection *__hidden this, const struct DXGI_SURFACE_DESC *, HDC *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180072434`

## callees

- `0x180010d40`
- `0x180075fa0`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x180084da9`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x180084da9`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180084e5e`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180084e5e`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180084e2d`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180084e2d`
- `ext-ms-win-gdi-draw-l1-1-1!SetStretchBltMode` at `0x180084e51`
- `ext-ms-win-gdi-draw-l1-1-1!SetStretchBltMode` at `0x180084e51`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CSourceBitsDIBSection *__fastcall CSourceBitsDIBSection::CSourceBitsDIBSection(
        CSourceBitsDIBSection *this,
        const struct DXGI_SURFACE_DESC *a2,
        HDC *a3)
{
  HDC CompatibleDC; // rax
  HBITMAP v7; // rbx
  BITMAPINFO pbmi; // [rsp+38h] [rbp-48h] BYREF
  int v10; // [rsp+64h] [rbp-1Ch]
  int v11; // [rsp+68h] [rbp-18h]

  *(_QWORD *)this = &CSourceBitsDIBSection::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(struct DXGI_SURFACE_DESC *)((char *)this + 32) = *a2;
  *((_DWORD *)this + 10) = 88;
  CompatibleDC = CreateCompatibleDC(0);
  *((_QWORD *)this + 2) = CompatibleDC;
  DXGIThrowFailure(CompatibleDC == 0 ? 0x80004005 : 0);
  pbmi.bmiHeader.biSize = 40;
  pbmi.bmiHeader.biWidth = a2->Width;
  pbmi.bmiHeader.biHeight = -a2->Height;
  *(_DWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  *(_QWORD *)&pbmi.bmiHeader.biCompression = 3;
  *(_QWORD *)&pbmi.bmiHeader.biXPelsPerMeter = 0;
  *(_QWORD *)&pbmi.bmiHeader.biClrUsed = 0;
  v11 = 255;
  v10 = 65280;
  pbmi.bmiColors[0] = (RGBQUAD)16711680;
  v7 = CreateDIBSection(*((HDC *)this + 2), &pbmi, 0, (void **)this + 3, 0, 0);
  DXGIThrowFailure(v7 == 0 ? 0x80004005 : 0);
  SetStretchBltMode(*((HDC *)this + 2), 3);
  *((_QWORD *)this + 1) = SelectObject(*((HDC *)this + 2), v7);
  *a3 = (HDC)*((_QWORD *)this + 2);
  return this;
}

```

## disassembly

```asm
0x180084d4c  mov     [rsp-18h+arg_18], rbx
0x180084d51  push    rbp
0x180084d52  push    rsi
0x180084d53  push    rdi
0x180084d54  mov     rbp, rsp
0x180084d57  sub     rsp, 80h
0x180084d5e  mov     rax, cs:__security_cookie
0x180084d65  xor     rax, rsp
0x180084d68  mov     [rbp+var_10], rax
0x180084d6c  mov     rsi, r8
0x180084d6f  mov     rbx, rdx
0x180084d72  mov     rdi, rcx
0x180084d75  mov     [rbp+var_50], rcx
0x180084d79  lea     rax, ??_7CSourceBitsDIBSection@@6B@; const CSourceBitsDIBSection::`vftable'
0x180084d80  mov     [rcx], rax
0x180084d83  mov     qword ptr [rcx+8], 0
0x180084d8b  mov     qword ptr [rcx+10h], 0
0x180084d93  movups  xmm0, xmmword ptr [rdx]
0x180084d96  movups  xmmword ptr [rcx+20h], xmm0
0x180084d9a  mov     eax, [rdx+10h]
0x180084d9d  mov     [rcx+30h], eax
0x180084da0  mov     dword ptr [rcx+28h], 58h ; 'X'
0x180084da7  xor     ecx, ecx; hdc
0x180084da9  call    cs:__imp_CreateCompatibleDC
0x180084daf  mov     [rdi+10h], rax
0x180084db3  neg     rax
0x180084db6  sbb     ecx, ecx
0x180084db8  not     ecx
0x180084dba  and     ecx, 80004005h; int
0x180084dc0  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x180084dc5  mov     [rbp+pbmi.bmiHeader.biSize], 28h ; '('
0x180084dcc  mov     eax, [rbx]
0x180084dce  mov     [rbp+pbmi.bmiHeader.biWidth], eax
0x180084dd1  mov     eax, [rbx+4]
0x180084dd4  neg     eax
0x180084dd6  mov     [rbp+pbmi.bmiHeader.biHeight], eax
0x180084dd9  mov     dword ptr [rbp+pbmi.bmiHeader.biPlanes], 200001h
0x180084de0  mov     qword ptr [rbp+pbmi.bmiHeader.biCompression], 3
0x180084de8  mov     qword ptr [rbp+pbmi.bmiHeader.biXPelsPerMeter], 0
0x180084df0  mov     qword ptr [rbp+pbmi.bmiHeader.biClrUsed], 0
0x180084df8  mov     [rbp+var_18], 0FFh
0x180084dff  mov     [rbp+var_1C], 0FF00h
0x180084e06  mov     dword ptr [rbp+pbmi.bmiColors.rgbBlue], 0FF0000h
0x180084e0d  lea     r9, [rdi+18h]; ppvBits
0x180084e11  mov     [rsp+80h+offset], 0; offset
0x180084e19  mov     [rsp+80h+hSection], 0; hSection
0x180084e22  xor     r8d, r8d; usage
0x180084e25  lea     rdx, [rbp+pbmi]; pbmi
0x180084e29  mov     rcx, [rdi+10h]; hdc
0x180084e2d  call    cs:__imp_CreateDIBSection
0x180084e33  mov     rbx, rax
0x180084e36  neg     rax
0x180084e39  sbb     ecx, ecx
0x180084e3b  not     ecx
0x180084e3d  and     ecx, 80004005h; int
0x180084e43  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x180084e48  mov     edx, 3; mode
0x180084e4d  mov     rcx, [rdi+10h]; hdc
0x180084e51  call    cs:__imp_SetStretchBltMode
0x180084e57  mov     rdx, rbx; h
0x180084e5a  mov     rcx, [rdi+10h]; hdc
0x180084e5e  call    cs:__imp_SelectObject
0x180084e64  mov     [rdi+8], rax
0x180084e68  mov     rcx, [rdi+10h]
0x180084e6c  mov     [rsi], rcx
0x180084e6f  mov     rax, rdi
0x180084e72  mov     rcx, [rbp+var_10]
0x180084e76  xor     rcx, rsp; StackCookie
0x180084e79  call    __security_check_cookie
0x180084e7e  mov     rbx, [rsp+80h+arg_18]
0x180084e86  add     rsp, 80h
0x180084e8d  pop     rdi
0x180084e8e  pop     rsi
0x180084e8f  pop     rbp
0x180084e90  retn
```
