# CBrowserBandSite::_CreateToolbarButtonBitmaps(int,int)

- ea: `0x18033ea80`
- end: `0x18033ec86`
- name: `?_CreateToolbarButtonBitmaps@CBrowserBandSite@@MEAAPEAUHBITMAP__@@HH@Z`
- size: `518`
- prototype: `HBITMAP(CBrowserBandSite *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18033fbd0`
- `0x18033fdc0`

## callees

- `0x18033ea80`
- `0x18047c998`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18033eb2d`
- `KERNEL32!MulDiv` at `0x18033eb46`
- `KERNEL32!MulDiv` at `0x18033eb2d`
- `KERNEL32!MulDiv` at `0x18033eb46`
- `GDI32!StretchBlt` at `0x18033ebef`
- `GDI32!StretchBlt` at `0x18033ebef`
- `GDI32!DeleteObject` at `0x18033ec3e`
- `GDI32!DeleteObject` at `0x18033ec3e`
- `GDI32!SelectObject` at `0x18033eb0e`
- `GDI32!SelectObject` at `0x18033eb9d`
- `GDI32!SelectObject` at `0x18033ec04`
- `GDI32!SelectObject` at `0x18033ec2a`
- `GDI32!SelectObject` at `0x18033eb0e`
- `GDI32!SelectObject` at `0x18033eb9d`
- `GDI32!SelectObject` at `0x18033ec04`
- `GDI32!SelectObject` at `0x18033ec2a`
- `GDI32!DeleteDC` at `0x18033ec13`
- `GDI32!DeleteDC` at `0x18033ec4d`
- `GDI32!DeleteDC` at `0x18033ec13`
- `GDI32!DeleteDC` at `0x18033ec4d`
- `GDI32!CreateCompatibleDC` at `0x18033eaf0`
- `GDI32!CreateCompatibleDC` at `0x18033eb5e`
- `GDI32!CreateCompatibleDC` at `0x18033eaf0`
- `GDI32!CreateCompatibleDC` at `0x18033eb5e`
- `GDI32!CreateCompatibleBitmap` at `0x18033eb83`
- `GDI32!CreateCompatibleBitmap` at `0x18033eb83`
- `USER32!ReleaseDC` at `0x18033ec5e`
- `USER32!ReleaseDC` at `0x18033ec5e`
- `USER32!GetDC` at `0x18033ead5`
- `USER32!GetDC` at `0x18033ead5`

## pseudocode

```c
HBITMAP __fastcall CBrowserBandSite::_CreateToolbarButtonBitmaps(CBrowserBandSite *this, int a2, int a3)
{
  HBITMAP MappedBitmap; // rbp
  HBITMAP v6; // r14
  HDC DC; // rax
  HDC v8; // rdi
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rsi
  int v11; // r12d
  HDC v12; // r15
  int v13; // r13d
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v15; // r12
  HGDIOBJ v16; // rbx
  int hDest; // [rsp+A8h] [rbp+10h]
  HGDIOBJ h; // [rsp+B8h] [rbp+20h]

  MappedBitmap = CreateMappedBitmap(g_hinst, 545, 0, 0, 0);
  v6 = MappedBitmap;
  if ( a2 != 96 || a3 != 96 )
  {
    DC = GetDC(0);
    v8 = DC;
    if ( DC )
    {
      CompatibleDC = CreateCompatibleDC(DC);
      hdcSrc = CompatibleDC;
      if ( CompatibleDC )
      {
        h = SelectObject(CompatibleDC, MappedBitmap);
        v11 = MulDiv(13, a2, 96);
        hDest = MulDiv(11, a3, 96);
        v12 = CreateCompatibleDC(v8);
        if ( v12 )
        {
          v13 = 3 * v11;
          CompatibleBitmap = CreateCompatibleBitmap(v8, 3 * v11, hDest);
          v15 = CompatibleBitmap;
          if ( CompatibleBitmap )
          {
            v16 = SelectObject(v12, CompatibleBitmap);
            StretchBlt(v12, 0, 0, v13, hDest, hdcSrc, 0, 0, 39, 11, 0xCC0020u);
            v6 = v15;
            SelectObject(v12, v16);
          }
          DeleteDC(v12);
        }
        SelectObject(hdcSrc, h);
        if ( v6 != MappedBitmap )
          DeleteObject(MappedBitmap);
        DeleteDC(hdcSrc);
      }
      ReleaseDC(0, v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18033ea80  mov     [rsp+arg_0], rbx
0x18033ea85  push    rbp
0x18033ea86  push    rsi
0x18033ea87  push    rdi
0x18033ea88  push    r12
0x18033ea8a  push    r13
0x18033ea8c  push    r14
0x18033ea8e  push    r15
0x18033ea90  sub     rsp, 60h
0x18033ea94  mov     rcx, cs:g_hinst; hInstance
0x18033ea9b  mov     ebx, r8d
0x18033ea9e  mov     r15d, edx
0x18033eaa1  mov     [rsp+98h+iNumMaps], 0; iNumMaps
0x18033eaa9  xor     r8d, r8d; wFlags
0x18033eaac  mov     edx, 221h; idBitmap
0x18033eab1  xor     r9d, r9d; lpColorMap
0x18033eab4  call    CreateMappedBitmap
0x18033eab9  mov     r13d, 60h ; '`'
0x18033eabf  mov     rbp, rax
0x18033eac2  mov     r14, rax
0x18033eac5  cmp     r15d, r13d
0x18033eac8  jnz     short loc_18033EAD3
0x18033eaca  cmp     ebx, r13d
0x18033eacd  jz      loc_18033EC6A
0x18033ead3  xor     ecx, ecx; hWnd
0x18033ead5  call    cs:__imp_GetDC
0x18033eadc  nop     dword ptr [rax+rax+00h]
0x18033eae1  mov     rdi, rax
0x18033eae4  test    rax, rax
0x18033eae7  jz      loc_18033EC6A
0x18033eaed  mov     rcx, rax; hdc
0x18033eaf0  call    cs:__imp_CreateCompatibleDC
0x18033eaf7  nop     dword ptr [rax+rax+00h]
0x18033eafc  mov     rsi, rax
0x18033eaff  test    rax, rax
0x18033eb02  jz      loc_18033EC59
0x18033eb08  mov     rdx, rbp; h
0x18033eb0b  mov     rcx, rax; hdc
0x18033eb0e  call    cs:__imp_SelectObject
0x18033eb15  nop     dword ptr [rax+rax+00h]
0x18033eb1a  mov     r8d, r13d; nDenominator
0x18033eb1d  mov     edx, r15d; nNumerator
0x18033eb20  mov     ecx, 0Dh; nNumber
0x18033eb25  mov     [rsp+98h+h], rax
0x18033eb2d  call    cs:__imp_MulDiv
0x18033eb34  nop     dword ptr [rax+rax+00h]
0x18033eb39  mov     r8d, r13d; nDenominator
0x18033eb3c  mov     edx, ebx; nNumerator
0x18033eb3e  mov     ecx, 0Bh; nNumber
0x18033eb43  mov     r12d, eax
0x18033eb46  call    cs:__imp_MulDiv
0x18033eb4d  nop     dword ptr [rax+rax+00h]
0x18033eb52  mov     rcx, rdi; hdc
0x18033eb55  mov     [rsp+98h+hDest], eax
0x18033eb5c  mov     ebx, eax
0x18033eb5e  call    cs:__imp_CreateCompatibleDC
0x18033eb65  nop     dword ptr [rax+rax+00h]
0x18033eb6a  mov     r15, rax
0x18033eb6d  test    rax, rax
0x18033eb70  jz      loc_18033EC1F
0x18033eb76  lea     r13d, [r12+r12*2]
0x18033eb7a  mov     r8d, ebx; cy
0x18033eb7d  mov     edx, r13d; cx
0x18033eb80  mov     rcx, rdi; hdc
0x18033eb83  call    cs:__imp_CreateCompatibleBitmap
0x18033eb8a  nop     dword ptr [rax+rax+00h]
0x18033eb8f  mov     r12, rax
0x18033eb92  test    rax, rax
0x18033eb95  jz      short loc_18033EC10
0x18033eb97  mov     rdx, rax; h
0x18033eb9a  mov     rcx, r15; hdc
0x18033eb9d  call    cs:__imp_SelectObject
0x18033eba4  nop     dword ptr [rax+rax+00h]
0x18033eba9  mov     [rsp+98h+rop], 0CC0020h; rop
0x18033ebb1  mov     r9d, r13d; wDest
0x18033ebb4  mov     [rsp+98h+hSrc], 0Bh; hSrc
0x18033ebbc  mov     rbx, rax
0x18033ebbf  mov     eax, [rsp+98h+hDest]
0x18033ebc6  xor     r8d, r8d; yDest
0x18033ebc9  mov     [rsp+98h+wSrc], 27h ; '''; wSrc
0x18033ebd1  xor     edx, edx; xDest
0x18033ebd3  mov     [rsp+98h+ySrc], 0; ySrc
0x18033ebdb  mov     rcx, r15; hdcDest
0x18033ebde  mov     [rsp+98h+xSrc], 0; xSrc
0x18033ebe6  mov     [rsp+98h+hdcSrc], rsi; hdcSrc
0x18033ebeb  mov     [rsp+98h+iNumMaps], eax; hDest
0x18033ebef  call    cs:__imp_StretchBlt
0x18033ebf6  nop     dword ptr [rax+rax+00h]
0x18033ebfb  mov     rdx, rbx; h
0x18033ebfe  mov     rcx, r15; hdc
0x18033ec01  mov     r14, r12
0x18033ec04  call    cs:__imp_SelectObject
0x18033ec0b  nop     dword ptr [rax+rax+00h]
0x18033ec10  mov     rcx, r15; hdc
0x18033ec13  call    cs:__imp_DeleteDC
0x18033ec1a  nop     dword ptr [rax+rax+00h]
0x18033ec1f  mov     rdx, [rsp+98h+h]; h
0x18033ec27  mov     rcx, rsi; hdc
0x18033ec2a  call    cs:__imp_SelectObject
0x18033ec31  nop     dword ptr [rax+rax+00h]
0x18033ec36  cmp     r14, rbp
0x18033ec39  jz      short loc_18033EC4A
0x18033ec3b  mov     rcx, rbp; ho
0x18033ec3e  call    cs:__imp_DeleteObject
0x18033ec45  nop     dword ptr [rax+rax+00h]
0x18033ec4a  mov     rcx, rsi; hdc
0x18033ec4d  call    cs:__imp_DeleteDC
0x18033ec54  nop     dword ptr [rax+rax+00h]
0x18033ec59  mov     rdx, rdi; hDC
0x18033ec5c  xor     ecx, ecx; hWnd
0x18033ec5e  call    cs:__imp_ReleaseDC
0x18033ec65  nop     dword ptr [rax+rax+00h]
0x18033ec6a  mov     rbx, [rsp+98h+arg_0]
0x18033ec72  mov     rax, r14
0x18033ec75  add     rsp, 60h
0x18033ec79  pop     r15
0x18033ec7b  pop     r14
0x18033ec7d  pop     r13
0x18033ec7f  pop     r12
0x18033ec81  pop     rdi
0x18033ec82  pop     rsi
0x18033ec83  pop     rbp
0x18033ec84  retn
```
