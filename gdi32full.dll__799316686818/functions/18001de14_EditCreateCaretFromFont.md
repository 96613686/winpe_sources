# EditCreateCaretFromFont

- ea: `0x18001de14`
- end: `0x18001e090`
- name: `EditCreateCaretFromFont`
- size: `636`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180066f30`

## callees

- `0x18001da40`
- `0x18001dc40`
- `0x18001de14`
- `0x18001fe20`
- `0x1800200f0`
- `0x180026130`
- `0x18007ac50`

## import_xrefs

- `GDI32!DeleteDC` at `0x18001e05c`
- `GDI32!DeleteDC` at `0x18001e05c`
- `GDI32!ExtTextOutW` at `0x18001dfe7`
- `GDI32!ExtTextOutW` at `0x18001dfe7`
- `GDI32!SelectObject` at `0x18001df20`
- `GDI32!SelectObject` at `0x18001dfb6`
- `GDI32!SelectObject` at `0x18001dff9`
- `GDI32!SelectObject` at `0x18001df20`
- `GDI32!SelectObject` at `0x18001dfb6`
- `GDI32!SelectObject` at `0x18001dff9`
- `GDI32!SetTextColor` at `0x18001dea3`
- `GDI32!SetTextColor` at `0x18001dea3`
- `GDI32!DeleteObject` at `0x18001e002`
- `GDI32!DeleteObject` at `0x18001e016`
- `GDI32!DeleteObject` at `0x18001e053`
- `GDI32!DeleteObject` at `0x18001e002`
- `GDI32!DeleteObject` at `0x18001e016`
- `GDI32!DeleteObject` at `0x18001e053`
- `USER32!CreateCaret` at `0x18001e046`
- `USER32!CreateCaret` at `0x18001e046`
- `win32u!NtGdiGetCharABCWidthsW` at `0x18001df54`
- `win32u!NtGdiGetCharABCWidthsW` at `0x18001df54`
- `win32u!NtGdiGetGlyphIndicesW` at `0x18001df76`
- `win32u!NtGdiGetGlyphIndicesW` at `0x18001df76`

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
0x18001de14  mov     [rsp-8+arg_10], rbx
0x18001de19  push    rbp
0x18001de1a  push    rsi
0x18001de1b  push    rdi
0x18001de1c  push    r12
0x18001de1e  push    r13
0x18001de20  push    r14
0x18001de22  push    r15
0x18001de24  lea     rbp, [rsp-17h]
0x18001de29  sub     rsp, 0A0h
0x18001de30  mov     rax, cs:__security_cookie
0x18001de37  xor     rax, rsp
0x18001de3a  mov     [rbp+47h+var_38], rax
0x18001de3e  movzx   r12d, [rbp+47h+arg_28]
0x18001de43  xor     eax, eax
0x18001de45  mov     ebx, [rbp+47h+arg_20]
0x18001de48  mov     r14, rcx
0x18001de4b  xor     ecx, ecx
0x18001de4d  mov     dword ptr [rbp+47h+ho], r8d
0x18001de51  mov     [rbp+47h+var_48], rax
0x18001de55  mov     r13d, r9d
0x18001de58  mov     [rbp+47h+var_40], eax
0x18001de5b  mov     rsi, rdx
0x18001de5e  mov     [rbp+47h+String], cx
0x18001de62  mov     [rbp+47h+var_5C], cx
0x18001de66  cmp     r12d, 3
0x18001de6a  jnb     loc_18001E067
0x18001de70  mov     r15d, ecx
0x18001de73  mov     rcx, rdx; hdc
0x18001de76  call    CreateCompatibleDC
0x18001de7b  mov     rdi, rax
0x18001de7e  test    rax, rax
0x18001de81  jz      loc_18001E067
0x18001de87  mov     rcx, rsi; hdc
0x18001de8a  call    GetBkColor
0x18001de8f  not     eax
0x18001de91  mov     rcx, rdi; hdc
0x18001de94  mov     edx, eax; color
0x18001de96  call    SetBkColor
0x18001de9b  mov     edx, 0FFFFFFh; color
0x18001dea0  mov     rcx, rdi; hdc
0x18001dea3  call    cs:__imp_SetTextColor
0x18001dea9  lea     r8, g_CaretShapes
0x18001deb0  mov     [rbp+47h+var_50], rbx
0x18001deb4  mov     edx, 190h
0x18001deb9  mov     eax, ebx
0x18001debb  add     rax, rax
0x18001debe  mov     ebx, 1
0x18001dec3  cmp     dword ptr [rbp+47h+ho], ebx
0x18001dec6  mov     ecx, 2BCh
0x18001decb  cmovle  ecx, edx
0x18001dece  xor     r9d, r9d; cOrientation
0x18001ded1  mov     rax, [r8+rax*8]
0x18001ded5  xor     edx, edx; cWidth
0x18001ded7  mov     [rsp+0D0h+pszFaceName], rax; pszFaceName
0x18001dedc  xor     r8d, r8d; cEscapement
0x18001dedf  xor     eax, eax
0x18001dee1  mov     [rsp+0D0h+iPitchAndFamily], eax; iPitchAndFamily
0x18001dee5  mov     [rsp+0D0h+iQuality], eax; iQuality
0x18001dee9  mov     [rsp+0D0h+iClipPrecision], eax; iClipPrecision
0x18001deed  mov     [rsp+0D0h+iOutPrecision], eax; iOutPrecision
0x18001def1  mov     [rsp+0D0h+iCharSet], ebx; iCharSet
0x18001def5  mov     [rsp+0D0h+bStrikeOut], eax; bStrikeOut
0x18001def9  mov     [rsp+0D0h+bUnderline], eax; bUnderline
0x18001defd  mov     [rsp+0D0h+bItalic], eax; bItalic
0x18001df01  mov     [rsp+0D0h+cWeight], ecx; cWeight
0x18001df05  mov     ecx, r13d; cHeight
0x18001df08  call    CreateFontW
0x18001df0d  mov     [rbp+47h+ho], rax
0x18001df11  test    rax, rax
0x18001df14  jz      loc_18001E059
0x18001df1a  mov     rdx, rax; h
0x18001df1d  mov     rcx, rdi; hdc
0x18001df20  call    cs:__imp_SelectObject
0x18001df26  mov     rcx, [rbp+47h+var_50]
0x18001df2a  lea     rax, g_CaretShapes
0x18001df31  xor     r9d, r9d
0x18001df34  mov     r8d, ebx
0x18001df37  lea     rcx, [r12+rcx*8]
0x18001df3b  movzx   edx, word ptr [rax+rcx*2+8]
0x18001df40  lea     rax, [rbp+47h+var_48]
0x18001df44  mov     qword ptr [rsp+0D0h+bItalic], rax
0x18001df49  mov     rcx, rdi
0x18001df4c  mov     [rsp+0D0h+cWeight], ebx
0x18001df50  mov     [rbp+47h+var_5C], dx
0x18001df54  call    cs:__imp_NtGdiGetCharABCWidthsW
0x18001df5a  xor     ecx, ecx
0x18001df5c  test    eax, eax
0x18001df5e  jz      loc_18001E04F
0x18001df64  mov     [rsp+0D0h+cWeight], ecx
0x18001df68  lea     r9, [rbp+47h+String]
0x18001df6c  mov     rcx, rdi
0x18001df6f  lea     rdx, [rbp+47h+var_5C]
0x18001df73  mov     r8d, ebx
0x18001df76  call    cs:__imp_NtGdiGetGlyphIndicesW
0x18001df7c  xor     ecx, ecx
0x18001df7e  test    eax, eax
0x18001df80  jz      loc_18001E04F
0x18001df86  cmp     [rbp+47h+String], cx
0x18001df8a  jz      loc_18001E04F
0x18001df90  mov     edx, dword ptr [rbp+47h+var_48+4]
0x18001df93  mov     r8d, r13d; cy
0x18001df96  add     edx, 0Fh
0x18001df99  mov     rcx, rsi; hdc
0x18001df9c  and     edx, 0FFFFFFF0h; cx
0x18001df9f  call    CreateCompatibleBitmap
0x18001dfa4  mov     rsi, rax
0x18001dfa7  test    rax, rax
0x18001dfaa  jz      loc_18001E04F
0x18001dfb0  mov     rdx, rax; h
0x18001dfb3  mov     rcx, rdi; hdc
0x18001dfb6  call    cs:__imp_SelectObject
0x18001dfbc  mov     edx, dword ptr [rbp+47h+var_48]
0x18001dfbf  lea     r9d, [rbx+11h]; options
0x18001dfc3  xor     ecx, ecx
0x18001dfc5  mov     r13, rax
0x18001dfc8  mov     qword ptr [rsp+0D0h+bStrikeOut], rcx; lpDx
0x18001dfcd  lea     rax, [rbp+47h+String]
0x18001dfd1  mov     [rsp+0D0h+bUnderline], ebx; c
0x18001dfd5  neg     edx; x
0x18001dfd7  mov     qword ptr [rsp+0D0h+bItalic], rax; lpString
0x18001dfdc  xor     r8d, r8d; y
0x18001dfdf  mov     qword ptr [rsp+0D0h+cWeight], rcx; lprect
0x18001dfe4  mov     rcx, rdi; hdc
0x18001dfe7  call    cs:__imp_ExtTextOutW
0x18001dfed  xor     edx, edx
0x18001dfef  test    eax, eax
0x18001dff1  jnz     short loc_18001E00A
0x18001dff3  mov     rdx, r13; h
0x18001dff6  mov     rcx, rdi; hdc
0x18001dff9  call    cs:__imp_SelectObject
0x18001dfff  mov     rcx, rax; ho
0x18001e002  call    cs:__imp_DeleteObject
0x18001e008  jmp     short loc_18001E04F
0x18001e00a  mov     rcx, [r14+128h]; ho
0x18001e011  test    rcx, rcx
0x18001e014  jz      short loc_18001E01E
0x18001e016  call    cs:__imp_DeleteObject
0x18001e01c  xor     edx, edx
0x18001e01e  mov     [r14+128h], rsi
0x18001e025  cmp     r12w, bx
0x18001e029  jnz     short loc_18001E030
0x18001e02b  sub     ebx, dword ptr [rbp+47h+var_48+4]
0x18001e02e  jmp     short loc_18001E032
0x18001e030  mov     ebx, edx
0x18001e032  mov     [r14+130h], ebx
0x18001e039  xor     r9d, r9d; nHeight
0x18001e03c  mov     rcx, [r14+40h]; hWnd
0x18001e040  xor     r8d, r8d; nWidth
0x18001e043  mov     rdx, rsi; hBitmap
0x18001e046  call    cs:__imp_CreateCaret
0x18001e04c  mov     r15d, eax
0x18001e04f  mov     rcx, [rbp+47h+ho]; ho
0x18001e053  call    cs:__imp_DeleteObject
0x18001e059  mov     rcx, rdi; hdc
0x18001e05c  call    cs:__imp_DeleteDC
0x18001e062  mov     eax, r15d
0x18001e065  jmp     short loc_18001E069
0x18001e067  xor     eax, eax
0x18001e069  mov     rcx, [rbp+47h+var_38]
0x18001e06d  xor     rcx, rsp; StackCookie
0x18001e070  call    __security_check_cookie
0x18001e075  mov     rbx, [rsp+0D0h+arg_10]
0x18001e07d  add     rsp, 0A0h
0x18001e084  pop     r15
0x18001e086  pop     r14
0x18001e088  pop     r13
0x18001e08a  pop     r12
0x18001e08c  pop     rdi
0x18001e08d  pop     rsi
0x18001e08e  pop     rbp
0x18001e08f  retn
```
