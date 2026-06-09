# CDXGISurfaceDIBSection::Init(uint,uint)

- ea: `0x180098dc0`
- end: `0x180098eba`
- name: `?Init@CDXGISurfaceDIBSection@@QEAAJII@Z`
- size: `250`
- prototype: `__int64 __fastcall(CDXGISurfaceDIBSection *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180098160`

## callees

- `0x180075fa0`
- `0x180098dc0`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x180098dfc`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x180098dfc`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180098e90`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180098e90`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180098e71`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180098e71`
- `ext-ms-win-gdi-draw-l1-1-1!SetStretchBltMode` at `0x180098e84`
- `ext-ms-win-gdi-draw-l1-1-1!SetStretchBltMode` at `0x180098e84`

## pseudocode

```c
__int64 __fastcall CDXGISurfaceDIBSection::Init(CDXGISurfaceDIBSection *this, LONG a2, int a3)
{
  HDC CompatibleDC; // rax
  HBITMAP v7; // rdi
  BITMAPINFO pbmi; // [rsp+30h] [rbp-40h] BYREF
  int v10; // [rsp+5Ch] [rbp-14h]
  int v11; // [rsp+60h] [rbp-10h]

  *((_DWORD *)this + 8) = 88;
  *((_DWORD *)this + 7) = a3;
  *((_DWORD *)this + 6) = a2;
  *(_QWORD *)((char *)this + 36) = 1;
  CompatibleDC = CreateCompatibleDC(0);
  *(_QWORD *)this = CompatibleDC;
  if ( !CompatibleDC )
    return 2147500037LL;
  pbmi.bmiHeader.biWidth = a2;
  *(_QWORD *)&pbmi.bmiHeader.biCompression = 3;
  pbmi.bmiHeader.biSize = 40;
  pbmi.bmiHeader.biHeight = -a3;
  *(_DWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  *(_QWORD *)&pbmi.bmiHeader.biXPelsPerMeter = 0;
  *(_QWORD *)&pbmi.bmiHeader.biClrUsed = 0;
  v11 = 255;
  v10 = 65280;
  pbmi.bmiColors[0] = (RGBQUAD)16711680;
  v7 = CreateDIBSection(CompatibleDC, &pbmi, 0, (void **)this + 2, 0, 0);
  if ( !v7 )
    return 2147500037LL;
  SetStretchBltMode(*(HDC *)this, 3);
  *((_QWORD *)this + 1) = SelectObject(*(HDC *)this, v7);
  return 0;
}

```

## disassembly

```asm
0x180098dc0  push    rbp
0x180098dc2  push    rbx
0x180098dc3  push    rsi
0x180098dc4  push    rdi
0x180098dc5  push    r15
0x180098dc7  mov     rbp, rsp
0x180098dca  sub     rsp, 70h
0x180098dce  mov     rax, cs:__security_cookie
0x180098dd5  xor     rax, rsp
0x180098dd8  mov     [rbp+var_8], rax
0x180098ddc  mov     rbx, rcx
0x180098ddf  mov     dword ptr [rcx+20h], 58h ; 'X'
0x180098de6  mov     [rcx+1Ch], r8d
0x180098dea  mov     edi, r8d
0x180098ded  mov     [rcx+18h], edx
0x180098df0  mov     esi, edx
0x180098df2  mov     qword ptr [rcx+24h], 1
0x180098dfa  xor     ecx, ecx; hdc
0x180098dfc  call    cs:__imp_CreateCompatibleDC
0x180098e02  mov     [rbx], rax
0x180098e05  test    rax, rax
0x180098e08  jz      loc_180098E9E
0x180098e0e  mov     [rbp+pbmi.bmiHeader.biWidth], esi
0x180098e11  lea     r9, [rbx+10h]; ppvBits
0x180098e15  mov     esi, 3
0x180098e1a  mov     [rsp+70h+offset], 0; offset
0x180098e22  neg     edi
0x180098e24  mov     qword ptr [rbp+pbmi.bmiHeader.biCompression], rsi
0x180098e28  xor     r8d, r8d; usage
0x180098e2b  mov     [rbp+pbmi.bmiHeader.biSize], 28h ; '('
0x180098e32  lea     rdx, [rbp+pbmi]; pbmi
0x180098e36  mov     [rbp+pbmi.bmiHeader.biHeight], edi
0x180098e39  mov     rcx, rax; hdc
0x180098e3c  mov     dword ptr [rbp+pbmi.bmiHeader.biPlanes], 200001h
0x180098e43  mov     qword ptr [rbp+pbmi.bmiHeader.biXPelsPerMeter], 0
0x180098e4b  mov     qword ptr [rbp+pbmi.bmiHeader.biClrUsed], 0
0x180098e53  mov     [rbp+var_10], 0FFh
0x180098e5a  mov     [rbp+var_14], 0FF00h
0x180098e61  mov     dword ptr [rbp+pbmi.bmiColors.rgbBlue], 0FF0000h
0x180098e68  mov     [rsp+70h+hSection], 0; hSection
0x180098e71  call    cs:__imp_CreateDIBSection
0x180098e77  mov     rdi, rax
0x180098e7a  test    rax, rax
0x180098e7d  jz      short loc_180098E9E
0x180098e7f  mov     rcx, [rbx]; hdc
0x180098e82  mov     edx, esi; mode
0x180098e84  call    cs:__imp_SetStretchBltMode
0x180098e8a  mov     rcx, [rbx]; hdc
0x180098e8d  mov     rdx, rdi; h
0x180098e90  call    cs:__imp_SelectObject
0x180098e96  mov     [rbx+8], rax
0x180098e9a  xor     eax, eax
0x180098e9c  jmp     short loc_180098EA3
0x180098e9e  mov     eax, 80004005h
0x180098ea3  mov     rcx, [rbp+var_8]
0x180098ea7  xor     rcx, rsp; StackCookie
0x180098eaa  call    __security_check_cookie
0x180098eaf  add     rsp, 70h
0x180098eb3  pop     r15
0x180098eb5  pop     rdi
0x180098eb6  pop     rsi
0x180098eb7  pop     rbx
0x180098eb8  pop     rbp
0x180098eb9  retn
```
