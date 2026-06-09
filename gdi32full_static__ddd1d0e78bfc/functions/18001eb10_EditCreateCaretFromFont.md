# EditCreateCaretFromFont

- ea: `0x18001eb10`
- end: `0x18001edd5`
- name: `EditCreateCaretFromFont`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006b6b0`

## callees

- `0x18001e920`
- `0x18001eb10`
- `0x1800200a0`
- `0x180028260`
- `0x180028dd0`
- `0x18002f120`
- `0x18007f800`

## import_xrefs

- `GDI32!DeleteDC` at `0x18001ed9a`
- `GDI32!DeleteDC` at `0x18001ed9a`
- `GDI32!ExtTextOutW` at `0x18001ed01`
- `GDI32!ExtTextOutW` at `0x18001ed01`
- `GDI32!SelectObject` at `0x18001ec22`
- `GDI32!SelectObject` at `0x18001ecca`
- `GDI32!SelectObject` at `0x18001ed19`
- `GDI32!SelectObject` at `0x18001ec22`
- `GDI32!SelectObject` at `0x18001ecca`
- `GDI32!SelectObject` at `0x18001ed19`
- `GDI32!SetTextColor` at `0x18001eb9f`
- `GDI32!SetTextColor` at `0x18001eb9f`
- `GDI32!DeleteObject` at `0x18001ed28`
- `GDI32!DeleteObject` at `0x18001ed42`
- `GDI32!DeleteObject` at `0x18001ed8b`
- `GDI32!DeleteObject` at `0x18001ed28`
- `GDI32!DeleteObject` at `0x18001ed42`
- `GDI32!DeleteObject` at `0x18001ed8b`
- `USER32!CreateCaret` at `0x18001ed78`
- `USER32!CreateCaret` at `0x18001ed78`
- `win32u!NtGdiGetCharABCWidthsW` at `0x18001ec5c`
- `win32u!NtGdiGetCharABCWidthsW` at `0x18001ec5c`
- `win32u!NtGdiGetGlyphIndicesW` at `0x18001ec84`
- `win32u!NtGdiGetGlyphIndicesW` at `0x18001ec84`

## pseudocode

```c
__int64 __fastcall EditCreateCaretFromFont(__int64 a1, HDC a2, int a3, int a4, unsigned int a5, unsigned __int16 a6)
{
  unsigned int Caret; // r15d
  HDC CompatibleDC; // rdi
  COLORREF BkColor; // eax
  int cWeight; // ecx
  HFONT FontW; // rax
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v15; // rsi
  HGDIOBJ v16; // r13
  HGDIOBJ v17; // rax
  void *v18; // rcx
  int v19; // ebx
  WCHAR String[2]; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int16 v22; // [rsp+74h] [rbp-15h] BYREF
  HGDIOBJ ho; // [rsp+78h] [rbp-11h]
  __int64 v24; // [rsp+80h] [rbp-9h]
  __int64 v25; // [rsp+88h] [rbp-1h] BYREF
  int v26; // [rsp+90h] [rbp+7h]

  LODWORD(ho) = a3;
  v25 = 0;
  v26 = 0;
  String[0] = 0;
  v22 = 0;
  if ( a6 >= 3u )
    return 0;
  Caret = 0;
  CompatibleDC = CreateCompatibleDC(a2);
  if ( !CompatibleDC )
    return 0;
  BkColor = GetBkColor(a2);
  SetBkColor(CompatibleDC, ~BkColor);
  SetTextColor(CompatibleDC, 0xFFFFFFu);
  v24 = a5;
  cWeight = 700;
  if ( (int)ho <= 1 )
    cWeight = 400;
  FontW = CreateFontW(a4, 0, 0, 0, cWeight, 0, 0, 0, 1u, 0, 0, 0, 0, (&g_CaretShapes)[2 * a5]);
  ho = FontW;
  if ( FontW )
  {
    SelectObject(CompatibleDC, FontW);
    v22 = *((_WORD *)&g_CaretShapes + 8 * v24 + a6 + 4);
    if ( (unsigned int)NtGdiGetCharABCWidthsW(CompatibleDC, v22, 1, 0, 1, &v25) )
    {
      if ( (unsigned int)NtGdiGetGlyphIndicesW(CompatibleDC, &v22, 1, String, 0) )
      {
        if ( String[0] )
        {
          CompatibleBitmap = CreateCompatibleBitmap(a2, (HIDWORD(v25) + 15) & 0xFFFFFFF0, a4);
          v15 = CompatibleBitmap;
          if ( CompatibleBitmap )
          {
            v16 = SelectObject(CompatibleDC, CompatibleBitmap);
            if ( ExtTextOutW(CompatibleDC, -(int)v25, 0, 0x12u, 0, String, 1u, 0) )
            {
              v18 = *(void **)(a1 + 296);
              if ( v18 )
                DeleteObject(v18);
              *(_QWORD *)(a1 + 296) = v15;
              if ( a6 == 1 )
                v19 = 1 - HIDWORD(v25);
              else
                v19 = 0;
              *(_DWORD *)(a1 + 304) = v19;
              Caret = CreateCaret(*(HWND *)(a1 + 64), v15, 0, 0);
            }
            else
            {
              v17 = SelectObject(CompatibleDC, v16);
              DeleteObject(v17);
            }
          }
        }
      }
    }
    DeleteObject(ho);
  }
  DeleteDC(CompatibleDC);
  return Caret;
}

```

## disassembly

```asm
0x18001eb10  mov     [rsp-8+arg_10], rbx
0x18001eb15  push    rbp
0x18001eb16  push    rsi
0x18001eb17  push    rdi
0x18001eb18  push    r12
0x18001eb1a  push    r13
0x18001eb1c  push    r14
0x18001eb1e  push    r15
0x18001eb20  lea     rbp, [rsp-17h]
0x18001eb25  sub     rsp, 0A0h
0x18001eb2c  mov     rax, cs:__security_cookie
0x18001eb33  xor     rax, rsp
0x18001eb36  mov     [rbp+47h+var_38], rax
0x18001eb3a  movzx   r12d, [rbp+47h+arg_28]
0x18001eb3f  xor     eax, eax
0x18001eb41  mov     ebx, [rbp+47h+arg_20]
0x18001eb44  mov     r14, rcx
0x18001eb47  xor     ecx, ecx
0x18001eb49  mov     dword ptr [rbp+47h+ho], r8d
0x18001eb4d  mov     [rbp+47h+var_48], rax
0x18001eb51  mov     r13d, r9d
0x18001eb54  mov     [rbp+47h+var_40], eax
0x18001eb57  mov     rsi, rdx
0x18001eb5a  mov     [rbp+47h+String], cx
0x18001eb5e  mov     [rbp+47h+var_5C], cx
0x18001eb62  cmp     r12d, 3
0x18001eb66  jnb     loc_18001EDAB
0x18001eb6c  mov     r15d, ecx
0x18001eb6f  mov     rcx, rdx; hdc
0x18001eb72  call    CreateCompatibleDC
0x18001eb77  mov     rdi, rax
0x18001eb7a  test    rax, rax
0x18001eb7d  jz      loc_18001EDAB
0x18001eb83  mov     rcx, rsi; hdc
0x18001eb86  call    GetBkColor
0x18001eb8b  not     eax
0x18001eb8d  mov     rcx, rdi; hdc
0x18001eb90  mov     edx, eax; color
0x18001eb92  call    SetBkColor
0x18001eb97  mov     edx, 0FFFFFFh; color
0x18001eb9c  mov     rcx, rdi; hdc
0x18001eb9f  call    cs:__imp_SetTextColor
0x18001eba6  nop     dword ptr [rax+rax+00h]
0x18001ebab  lea     r8, g_CaretShapes
0x18001ebb2  mov     [rbp+47h+var_50], rbx
0x18001ebb6  mov     edx, 190h
0x18001ebbb  mov     eax, ebx
0x18001ebbd  add     rax, rax
0x18001ebc0  mov     ebx, 1
0x18001ebc5  cmp     dword ptr [rbp+47h+ho], ebx
0x18001ebc8  mov     ecx, 2BCh
0x18001ebcd  cmovle  ecx, edx
0x18001ebd0  xor     r9d, r9d; cOrientation
0x18001ebd3  mov     rax, [r8+rax*8]
0x18001ebd7  xor     edx, edx; cWidth
0x18001ebd9  mov     [rsp+0D0h+pszFaceName], rax; pszFaceName
0x18001ebde  xor     r8d, r8d; cEscapement
0x18001ebe1  xor     eax, eax
0x18001ebe3  mov     [rsp+0D0h+iPitchAndFamily], eax; iPitchAndFamily
0x18001ebe7  mov     [rsp+0D0h+iQuality], eax; iQuality
0x18001ebeb  mov     [rsp+0D0h+iClipPrecision], eax; iClipPrecision
0x18001ebef  mov     [rsp+0D0h+iOutPrecision], eax; iOutPrecision
0x18001ebf3  mov     [rsp+0D0h+iCharSet], ebx; iCharSet
0x18001ebf7  mov     [rsp+0D0h+bStrikeOut], eax; bStrikeOut
0x18001ebfb  mov     [rsp+0D0h+bUnderline], eax; bUnderline
0x18001ebff  mov     [rsp+0D0h+bItalic], eax; bItalic
0x18001ec03  mov     [rsp+0D0h+cWeight], ecx; cWeight
0x18001ec07  mov     ecx, r13d; cHeight
0x18001ec0a  call    CreateFontW
0x18001ec0f  mov     [rbp+47h+ho], rax
0x18001ec13  test    rax, rax
0x18001ec16  jz      loc_18001ED97
0x18001ec1c  mov     rdx, rax; h
0x18001ec1f  mov     rcx, rdi; hdc
0x18001ec22  call    cs:__imp_SelectObject
0x18001ec29  nop     dword ptr [rax+rax+00h]
0x18001ec2e  mov     rcx, [rbp+47h+var_50]
0x18001ec32  lea     rax, g_CaretShapes
0x18001ec39  xor     r9d, r9d
0x18001ec3c  mov     r8d, ebx
0x18001ec3f  lea     rcx, [r12+rcx*8]
0x18001ec43  movzx   edx, word ptr [rax+rcx*2+8]
0x18001ec48  lea     rax, [rbp+47h+var_48]
0x18001ec4c  mov     qword ptr [rsp+0D0h+bItalic], rax
0x18001ec51  mov     rcx, rdi
0x18001ec54  mov     [rsp+0D0h+cWeight], ebx
0x18001ec58  mov     [rbp+47h+var_5C], dx
0x18001ec5c  call    cs:__imp_NtGdiGetCharABCWidthsW
0x18001ec63  nop     dword ptr [rax+rax+00h]
0x18001ec68  xor     ecx, ecx
0x18001ec6a  test    eax, eax
0x18001ec6c  jz      loc_18001ED87
0x18001ec72  mov     [rsp+0D0h+cWeight], ecx
0x18001ec76  lea     r9, [rbp+47h+String]
0x18001ec7a  mov     rcx, rdi
0x18001ec7d  lea     rdx, [rbp+47h+var_5C]
0x18001ec81  mov     r8d, ebx
0x18001ec84  call    cs:__imp_NtGdiGetGlyphIndicesW
0x18001ec8b  nop     dword ptr [rax+rax+00h]
0x18001ec90  xor     ecx, ecx
0x18001ec92  test    eax, eax
0x18001ec94  jz      loc_18001ED87
0x18001ec9a  cmp     [rbp+47h+String], cx
0x18001ec9e  jz      loc_18001ED87
0x18001eca4  mov     edx, dword ptr [rbp+47h+var_48+4]
0x18001eca7  mov     r8d, r13d; cy
0x18001ecaa  add     edx, 0Fh
0x18001ecad  mov     rcx, rsi; hdc
0x18001ecb0  and     edx, 0FFFFFFF0h; cx
0x18001ecb3  call    CreateCompatibleBitmap
0x18001ecb8  mov     rsi, rax
0x18001ecbb  test    rax, rax
0x18001ecbe  jz      loc_18001ED87
0x18001ecc4  mov     rdx, rax; h
0x18001ecc7  mov     rcx, rdi; hdc
0x18001ecca  call    cs:__imp_SelectObject
0x18001ecd1  nop     dword ptr [rax+rax+00h]
0x18001ecd6  mov     edx, dword ptr [rbp+47h+var_48]
0x18001ecd9  lea     r9d, [rbx+11h]; options
0x18001ecdd  xor     ecx, ecx
0x18001ecdf  mov     r13, rax
0x18001ece2  mov     qword ptr [rsp+0D0h+bStrikeOut], rcx; lpDx
0x18001ece7  lea     rax, [rbp+47h+String]
0x18001eceb  mov     [rsp+0D0h+bUnderline], ebx; c
0x18001ecef  neg     edx; x
0x18001ecf1  mov     qword ptr [rsp+0D0h+bItalic], rax; lpString
0x18001ecf6  xor     r8d, r8d; y
0x18001ecf9  mov     qword ptr [rsp+0D0h+cWeight], rcx; lprect
0x18001ecfe  mov     rcx, rdi; hdc
0x18001ed01  call    cs:__imp_ExtTextOutW
0x18001ed08  nop     dword ptr [rax+rax+00h]
0x18001ed0d  xor     edx, edx
0x18001ed0f  test    eax, eax
0x18001ed11  jnz     short loc_18001ED36
0x18001ed13  mov     rdx, r13; h
0x18001ed16  mov     rcx, rdi; hdc
0x18001ed19  call    cs:__imp_SelectObject
0x18001ed20  nop     dword ptr [rax+rax+00h]
0x18001ed25  mov     rcx, rax; ho
0x18001ed28  call    cs:__imp_DeleteObject
0x18001ed2f  nop     dword ptr [rax+rax+00h]
0x18001ed34  jmp     short loc_18001ED87
0x18001ed36  mov     rcx, [r14+128h]; ho
0x18001ed3d  test    rcx, rcx
0x18001ed40  jz      short loc_18001ED50
0x18001ed42  call    cs:__imp_DeleteObject
0x18001ed49  nop     dword ptr [rax+rax+00h]
0x18001ed4e  xor     edx, edx
0x18001ed50  mov     [r14+128h], rsi
0x18001ed57  cmp     r12w, bx
0x18001ed5b  jnz     short loc_18001ED62
0x18001ed5d  sub     ebx, dword ptr [rbp+47h+var_48+4]
0x18001ed60  jmp     short loc_18001ED64
0x18001ed62  mov     ebx, edx
0x18001ed64  mov     [r14+130h], ebx
0x18001ed6b  xor     r9d, r9d; nHeight
0x18001ed6e  mov     rcx, [r14+40h]; hWnd
0x18001ed72  xor     r8d, r8d; nWidth
0x18001ed75  mov     rdx, rsi; hBitmap
0x18001ed78  call    cs:__imp_CreateCaret
0x18001ed7f  nop     dword ptr [rax+rax+00h]
0x18001ed84  mov     r15d, eax
0x18001ed87  mov     rcx, [rbp+47h+ho]; ho
0x18001ed8b  call    cs:__imp_DeleteObject
0x18001ed92  nop     dword ptr [rax+rax+00h]
0x18001ed97  mov     rcx, rdi; hdc
0x18001ed9a  call    cs:__imp_DeleteDC
0x18001eda1  nop     dword ptr [rax+rax+00h]
0x18001eda6  mov     eax, r15d
0x18001eda9  jmp     short loc_18001EDAD
0x18001edab  xor     eax, eax
0x18001edad  mov     rcx, [rbp+47h+var_38]
0x18001edb1  xor     rcx, rsp; StackCookie
0x18001edb4  call    __security_check_cookie
0x18001edb9  mov     rbx, [rsp+0D0h+arg_10]
0x18001edc1  add     rsp, 0A0h
0x18001edc8  pop     r15
0x18001edca  pop     r14
0x18001edcc  pop     r13
0x18001edce  pop     r12
0x18001edd0  pop     rdi
0x18001edd1  pop     rsi
0x18001edd2  pop     rbp
0x18001edd3  retn
```
