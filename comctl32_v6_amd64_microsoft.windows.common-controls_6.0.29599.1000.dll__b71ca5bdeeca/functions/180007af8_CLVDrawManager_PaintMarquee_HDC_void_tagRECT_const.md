# CLVDrawManager::_PaintMarquee(HDC__ *,void *,tagRECT const *)

- ea: `0x180007af8`
- end: `0x180007dcc`
- name: `?_PaintMarquee@CLVDrawManager@@AEAAXPEAUHDC__@@PEAXPEBUtagRECT@@@Z`
- size: `724`
- prototype: `void __fastcall(CLVDrawManager *__hidden this, HDC, void *, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002d9a0`

## callees

- `0x180007af8`
- `0x180007fc4`
- `0x1800c9e74`
- `0x1800cfc28`
- `0x180114520`

## import_xrefs

- `GDI32!DeleteObject` at `0x180007cfd`
- `GDI32!DeleteObject` at `0x180007cfd`
- `GDI32!SelectObject` at `0x180007bd8`
- `GDI32!SelectObject` at `0x180007cf4`
- `GDI32!SelectObject` at `0x180007bd8`
- `GDI32!SelectObject` at `0x180007cf4`
- `GDI32!DeleteDC` at `0x180007d06`
- `GDI32!DeleteDC` at `0x180007d06`
- `GDI32!CreateCompatibleDC` at `0x180007b56`
- `GDI32!CreateCompatibleDC` at `0x180007b56`
- `GDI32!CreateDIBSection` at `0x180007bc0`
- `GDI32!CreateDIBSection` at `0x180007bc0`
- `GDI32!GdiAlphaBlend` at `0x180007cdb`
- `GDI32!GdiAlphaBlend` at `0x180007cdb`
- `USER32!IntersectRect` at `0x180007b45`
- `USER32!IntersectRect` at `0x180007b45`
- `USER32!GetSysColor` at `0x180007be5`
- `USER32!GetSysColor` at `0x180007d42`
- `USER32!GetSysColor` at `0x180007d7b`
- `USER32!GetSysColor` at `0x180007d88`
- `USER32!GetSysColor` at `0x180007be5`
- `USER32!GetSysColor` at `0x180007d42`
- `USER32!GetSysColor` at `0x180007d7b`
- `USER32!GetSysColor` at `0x180007d88`

## pseudocode

```c
void __fastcall CLVDrawManager::_PaintMarquee(CLVDrawManager *this, HDC a2, void *a3, const struct tagRECT *a4)
{
  __int64 v4; // rax
  HDC CompatibleDC; // rbx
  HBITMAP v8; // rax
  HBITMAP v9; // r14
  HGDIOBJ v10; // r15
  COLORREF SysColor; // eax
  unsigned int v12; // edx
  unsigned int v13; // edx
  unsigned int v14; // ecx
  unsigned int v15; // edx
  unsigned int v16; // ecx
  unsigned int v17; // edx
  COLORREF v18; // eax
  COLORREF v19; // eax
  void *ppvBits; // [rsp+68h] [rbp-41h] BYREF
  RECT rect; // [rsp+70h] [rbp-39h] BYREF
  struct tagRECT rcDst; // [rsp+80h] [rbp-29h] BYREF
  BITMAPINFO pbmi; // [rsp+90h] [rbp-19h] BYREF

  v4 = *((_QWORD *)this + 3);
  rcDst = 0;
  if ( IntersectRect(&rcDst, a4, (const RECT *)(*(_QWORD *)(v4 + 456) + 32LL)) )
  {
    CompatibleDC = CreateCompatibleDC(a2);
    if ( CompatibleDC )
    {
      ppvBits = 0;
      pbmi.bmiHeader.biWidth = 1;
      pbmi.bmiHeader.biHeight = 1;
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
      rect = (RECT)_mm_load_si128((const __m128i *)&_xmm);
      memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
      pbmi.bmiHeader.biSize = 40;
      v8 = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, 0, 0);
      v9 = v8;
      if ( v8 )
      {
        v10 = SelectObject(CompatibleDC, v8);
        SysColor = GetSysColor(26);
        FillRectClr(CompatibleDC, &rect, SysColor);
        *((_BYTE *)ppvBits + 3) = 70;
        v12 = *((unsigned __int8 *)ppvBits + 2) * *((unsigned __int8 *)ppvBits + 3);
        if ( v12 >= 0xFF00 )
          LOBYTE(v13) = -1;
        else
          v13 = v12 / 0xFF;
        *((_BYTE *)ppvBits + 2) = v13;
        v14 = *((unsigned __int8 *)ppvBits + 1) * *((unsigned __int8 *)ppvBits + 3);
        if ( v14 >= 0xFF00 )
          LOBYTE(v15) = -1;
        else
          v15 = v14 / 0xFF;
        *((_BYTE *)ppvBits + 1) = v15;
        v16 = *(unsigned __int8 *)ppvBits * *((unsigned __int8 *)ppvBits + 3);
        if ( v16 >= 0xFF00 )
          LOBYTE(v17) = -1;
        else
          v17 = v16 / 0xFF;
        *(_BYTE *)ppvBits = v17;
        GdiAlphaBlend(
          a2,
          rcDst.left,
          rcDst.top,
          rcDst.right - rcDst.left,
          rcDst.bottom - rcDst.top,
          CompatibleDC,
          0,
          0,
          rect.right - rect.left,
          rect.bottom - rect.top,
          (BLENDFUNCTION)33488896);
        if ( (*(_BYTE *)(*((_QWORD *)this + 3) + 832LL) & 1) != 0 )
        {
          v18 = GetSysColor(13);
          FillRectClr(CompatibleDC, &rect, v18);
          *((_BYTE *)ppvBits + 3) = -1;
          CLVDrawManager::_DrawOutlineRectAlpha(this, a2, CompatibleDC, &rcDst);
        }
        SelectObject(CompatibleDC, v10);
        DeleteObject(v9);
      }
      DeleteDC(CompatibleDC);
    }
    if ( (*(_BYTE *)(*((_QWORD *)this + 3) + 832LL) & 1) == 0 )
    {
      GetSysColor(13);
      v19 = GetSysColor(13);
      SHOutlineRectThickness(a2, (RECT *)(*(_QWORD *)(*((_QWORD *)this + 3) + 456LL) + 32LL), v19, 1);
    }
  }
}

```

## disassembly

```asm
0x180007af8  push    rbp
0x180007afa  push    rbx
0x180007afb  push    rsi
0x180007afc  push    rdi
0x180007afd  push    r13
0x180007aff  push    r14
0x180007b01  push    r15
0x180007b03  lea     rbp, [rsp-27h]
0x180007b08  sub     rsp, 0D0h
0x180007b0f  mov     rax, cs:__security_cookie
0x180007b16  xor     rax, rsp
0x180007b19  mov     [rbp+57h+var_40], rax
0x180007b1d  mov     rax, [rcx+18h]
0x180007b21  xorps   xmm0, xmm0
0x180007b24  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x180007b28  mov     rsi, rdx
0x180007b2b  mov     rdi, rcx
0x180007b2e  mov     r14d, 20h ; ' '
0x180007b34  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x180007b38  mov     r8, [rax+1C8h]
0x180007b3f  mov     rdx, r9; lprcSrc1
0x180007b42  add     r8, r14; lprcSrc2
0x180007b45  call    cs:__imp_IntersectRect
0x180007b4b  test    eax, eax
0x180007b4d  jz      loc_180007D1F
0x180007b53  mov     rcx, rsi; hdc
0x180007b56  call    cs:__imp_CreateCompatibleDC
0x180007b5c  lea     r13d, [r14-1Fh]
0x180007b60  mov     rbx, rax
0x180007b63  test    rax, rax
0x180007b66  jz      loc_180007D12
0x180007b6c  movdqa  xmm0, cs:__xmm@00000001000000010000000000000000
0x180007b74  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x180007b78  xor     eax, eax
0x180007b7a  mov     [rbp+57h+ppvBits], 0
0x180007b82  xorps   xmm1, xmm1
0x180007b85  mov     [rsp+100h+offset], eax; offset
0x180007b89  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm1
0x180007b8d  xor     r8d, r8d; usage
0x180007b90  mov     [rbp+57h+pbmi.bmiHeader.biWidth], r13d
0x180007b94  lea     rdx, [rbp+57h+pbmi]; pbmi
0x180007b98  mov     [rbp+57h+pbmi.bmiHeader.biHeight], r13d
0x180007b9c  mov     rcx, rbx; hdc
0x180007b9f  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x180007ba7  mov     [rsp+100h+hSection], rax; hSection
0x180007bac  movdqu  xmmword ptr [rbp+57h+rect.left], xmm0
0x180007bb1  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x180007bb5  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm1
0x180007bb9  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x180007bc0  call    cs:__imp_CreateDIBSection
0x180007bc6  mov     r14, rax
0x180007bc9  test    rax, rax
0x180007bcc  jz      loc_180007D03
0x180007bd2  mov     rdx, rax; h
0x180007bd5  mov     rcx, rbx; hdc
0x180007bd8  call    cs:__imp_SelectObject
0x180007bde  lea     ecx, [r13+19h]; nIndex
0x180007be2  mov     r15, rax
0x180007be5  call    cs:__imp_GetSysColor
0x180007beb  lea     rdx, [rbp+57h+rect]; lprect
0x180007bef  mov     rcx, rbx; hdc
0x180007bf2  mov     r8d, eax; color
0x180007bf5  call    FillRectClr
0x180007bfa  mov     rcx, [rbp+57h+ppvBits]
0x180007bfe  mov     r11d, 0FF00h
0x180007c04  mov     r10d, 80808081h
0x180007c0a  mov     r9d, 0FFh
0x180007c10  mov     byte ptr [rcx+3], 46h ; 'F'
0x180007c14  mov     r8, [rbp+57h+ppvBits]
0x180007c18  movzx   edx, byte ptr [r8+3]
0x180007c1d  movzx   ecx, byte ptr [r8+2]
0x180007c22  imul    edx, ecx
0x180007c25  cmp     edx, r11d
0x180007c28  jnb     loc_180007DB4
0x180007c2e  mov     eax, r10d
0x180007c31  mul     edx
0x180007c33  shr     edx, 7
0x180007c36  mov     [r8+2], dl
0x180007c3a  mov     r8, [rbp+57h+ppvBits]
0x180007c3e  movzx   ecx, byte ptr [r8+3]
0x180007c43  movzx   eax, byte ptr [r8+1]
0x180007c48  imul    ecx, eax
0x180007c4b  cmp     ecx, r11d
0x180007c4e  jnb     loc_180007DBC
0x180007c54  mov     eax, r10d
0x180007c57  mul     ecx
0x180007c59  shr     edx, 7
0x180007c5c  mov     [r8+1], dl
0x180007c60  mov     r8, [rbp+57h+ppvBits]
0x180007c64  movzx   ecx, byte ptr [r8+3]
0x180007c69  movzx   eax, byte ptr [r8]
0x180007c6d  imul    ecx, eax
0x180007c70  cmp     ecx, r11d
0x180007c73  jnb     loc_180007DC4
0x180007c79  mov     eax, r10d
0x180007c7c  mul     ecx
0x180007c7e  shr     edx, 7
0x180007c81  mov     [r8], dl
0x180007c84  mov     ecx, [rbp+57h+rect.right]
0x180007c87  sub     ecx, [rbp+57h+rect.left]
0x180007c8a  mov     r10d, [rbp+57h+rect.bottom]
0x180007c8e  sub     r10d, [rbp+57h+rect.top]
0x180007c92  mov     r11d, [rbp+57h+rcDst.bottom]
0x180007c96  mov     r8d, [rbp+57h+rcDst.top]; yoriginDest
0x180007c9a  sub     r11d, r8d
0x180007c9d  mov     r9d, [rbp+57h+rcDst.right]
0x180007ca1  mov     edx, [rbp+57h+rcDst.left]; xoriginDest
0x180007ca4  sub     r9d, edx; wDest
0x180007ca7  mov     dword ptr [rbp+57h+var_A0.BlendOp], 1FF0000h
0x180007cae  mov     eax, dword ptr [rbp+57h+var_A0.BlendOp]
0x180007cb1  mov     dword ptr [rsp+100h+ftn.BlendOp], eax; ftn
0x180007cb5  mov     [rsp+100h+hSrc], r10d; hSrc
0x180007cba  mov     [rsp+100h+wSrc], ecx; wSrc
0x180007cbe  mov     rcx, rsi; hdcDest
0x180007cc1  mov     [rsp+100h+yoriginSrc], 0; yoriginSrc
0x180007cc9  mov     [rsp+100h+xoriginSrc], 0; xoriginSrc
0x180007cd1  mov     qword ptr [rsp+100h+offset], rbx; hdcSrc
0x180007cd6  mov     dword ptr [rsp+100h+hSection], r11d; hDest
0x180007cdb  call    cs:__imp_GdiAlphaBlend
0x180007ce1  mov     rax, [rdi+18h]
0x180007ce5  test    [rax+340h], r13b
0x180007cec  jnz     short loc_180007D3D
0x180007cee  mov     rdx, r15; h
0x180007cf1  mov     rcx, rbx; hdc
0x180007cf4  call    cs:__imp_SelectObject
0x180007cfa  mov     rcx, r14; ho
0x180007cfd  call    cs:__imp_DeleteObject
0x180007d03  mov     rcx, rbx; hdc
0x180007d06  call    cs:__imp_DeleteDC
0x180007d0c  mov     r14d, 20h ; ' '
0x180007d12  mov     rax, [rdi+18h]
0x180007d16  test    [rax+340h], r13b
0x180007d1d  jz      short loc_180007D76
0x180007d1f  mov     rcx, [rbp+57h+var_40]
0x180007d23  xor     rcx, rsp; StackCookie
0x180007d26  call    __security_check_cookie
0x180007d2b  add     rsp, 0D0h
0x180007d32  pop     r15
0x180007d34  pop     r14
0x180007d36  pop     r13
0x180007d38  pop     rdi
0x180007d39  pop     rsi
0x180007d3a  pop     rbx
0x180007d3b  pop     rbp
0x180007d3c  retn
0x180007d3d  mov     ecx, 0Dh; nIndex
0x180007d42  call    cs:__imp_GetSysColor
0x180007d48  lea     rdx, [rbp+57h+rect]; lprect
0x180007d4c  mov     rcx, rbx; hdc
0x180007d4f  mov     r8d, eax; color
0x180007d52  call    FillRectClr
0x180007d57  mov     rax, [rbp+57h+ppvBits]
0x180007d5b  lea     r9, [rbp+57h+rcDst]; struct tagRECT *
0x180007d5f  mov     r8, rbx; HDC
0x180007d62  mov     rdx, rsi; HDC
0x180007d65  mov     rcx, rdi; this
0x180007d68  mov     byte ptr [rax+3], 0FFh
0x180007d6c  call    ?_DrawOutlineRectAlpha@CLVDrawManager@@AEAAXPEAUHDC__@@0QEAUtagRECT@@@Z; CLVDrawManager::_DrawOutlineRectAlpha(HDC__ *,HDC__ *,tagRECT * const)
0x180007d71  jmp     loc_180007CEE
0x180007d76  mov     ecx, 0Dh; nIndex
0x180007d7b  call    cs:__imp_GetSysColor
0x180007d81  mov     ecx, 0Dh; nIndex
0x180007d86  mov     ebx, eax
0x180007d88  call    cs:__imp_GetSysColor
0x180007d8e  mov     rdx, [rdi+18h]
0x180007d92  mov     r9d, ebx
0x180007d95  mov     r8d, eax; color
0x180007d98  mov     dword ptr [rsp+100h+hSection], r13d; int
0x180007d9d  mov     rcx, rsi; hdc
0x180007da0  mov     rdx, [rdx+1C8h]
0x180007da7  add     rdx, r14; lprc
0x180007daa  call    SHOutlineRectThickness
0x180007daf  jmp     loc_180007D1F
0x180007db4  mov     edx, r9d
0x180007db7  jmp     loc_180007C36
0x180007dbc  mov     edx, r9d
0x180007dbf  jmp     loc_180007C5C
0x180007dc4  mov     edx, r9d
0x180007dc7  jmp     loc_180007C81
```
