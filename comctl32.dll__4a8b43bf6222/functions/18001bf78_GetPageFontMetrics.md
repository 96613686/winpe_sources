# GetPageFontMetrics

- ea: `0x18001bf78`
- end: `0x18001c1d4`
- name: `GetPageFontMetrics`
- size: `604`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001f42c`

## callees

- `0x1800115f0`
- `0x18001bf78`
- `0x18008ea60`

## import_xrefs

- `GDI32!SelectObject` at `0x18001c0cc`
- `GDI32!SelectObject` at `0x18001c153`
- `GDI32!SelectObject` at `0x18001c0cc`
- `GDI32!SelectObject` at `0x18001c153`
- `GDI32!DeleteObject` at `0x18001c15c`
- `GDI32!DeleteObject` at `0x18001c15c`
- `GDI32!CreateFontIndirectW` at `0x18001c0b4`
- `GDI32!CreateFontIndirectW` at `0x18001c0b4`
- `GDI32!GetDeviceCaps` at `0x18001c082`
- `GDI32!GetDeviceCaps` at `0x18001c082`
- `GDI32!GetTextMetricsW` at `0x18001c0f8`
- `GDI32!GetTextMetricsW` at `0x18001c0f8`
- `GDI32!GetTextExtentPoint32W` at `0x18001c117`
- `GDI32!GetTextExtentPoint32W` at `0x18001c117`
- `KERNEL32!lstrcmpiW` at `0x18001c04f`
- `KERNEL32!lstrcmpiW` at `0x18001c04f`
- `KERNEL32!MulDiv` at `0x18001c092`
- `KERNEL32!MulDiv` at `0x18001c092`
- `USER32!GetDC` at `0x18001c065`
- `USER32!GetDC` at `0x18001c065`
- `USER32!ReleaseDC` at `0x18001c1a4`
- `USER32!ReleaseDC` at `0x18001c1a4`

## pseudocode

```c
__int64 __fastcall GetPageFontMetrics(__int64 a1, __int16 *a2)
{
  unsigned int v4; // r15d
  __int16 v5; // r10
  __int64 v6; // rdx
  __int64 v7; // rcx
  WCHAR *v8; // r9
  WCHAR *lfFaceName; // rax
  WCHAR *v10; // rdx
  int v11; // eax
  HDC DC; // rax
  HDC v13; // r14
  int v14; // ebx
  int DeviceCaps; // eax
  int v16; // eax
  HFONT v17; // rax
  HFONT v18; // r12
  int *v19; // rbx
  HGDIOBJ v20; // r15
  int tmAveCharWidth; // eax
  tagTEXTMETRICW tm; // [rsp+20h] [rbp-89h] BYREF
  LOGFONTW lf; // [rsp+60h] [rbp-49h] BYREF

  memset(&lf, 0, sizeof(lf));
  v4 = 0;
  if ( a2 )
  {
    v5 = *a2;
    if ( *a2 > 0 )
    {
      if ( a2[1] )
      {
        v6 = 2147483646;
        v7 = 32;
        v8 = (WCHAR *)(a2 + 1);
        lfFaceName = lf.lfFaceName;
        do
        {
          if ( !v6 )
            break;
          if ( !*v8 )
            break;
          *lfFaceName++ = *v8++;
          --v6;
          --v7;
        }
        while ( v7 );
        v10 = lfFaceName - 1;
        if ( v7 )
          v10 = lfFaceName;
        v11 = *(_DWORD *)(a1 + 304);
        *v10 = 0;
        if ( *((_DWORD *)a2 + 18) == v11
          && *((_DWORD *)a2 + 17) == *(_DWORD *)(a1 + 300)
          && v5 == *(_WORD *)(a1 + 232)
          && !lstrcmpiW((LPCWSTR)a2 + 1, (LPCWSTR)(a1 + 234)) )
        {
          return 1;
        }
        else
        {
          DC = GetDC(*(HWND *)a1);
          v13 = DC;
          if ( DC )
          {
            v14 = *a2;
            DeviceCaps = GetDeviceCaps(DC, 90);
            v16 = MulDiv(v14, DeviceCaps, 72);
            lf.lfWeight = 400;
            lf.lfHeight = -v16;
            lf.lfCharSet = *((_BYTE *)a2 + 72);
            lf.lfItalic = *((_BYTE *)a2 + 68);
            v17 = CreateFontIndirectW(&lf);
            v18 = v17;
            if ( v17 )
            {
              v19 = (int *)(a1 + 312);
              v20 = SelectObject(v13, v17);
              memset(&tm, 0, sizeof(tm));
              GetTextMetricsW(v13, &tm);
              if ( (tm.tmPitchAndFamily & 1) != 0
                && GetTextExtentPoint32W(v13, AveCharWidthData, 52, (LPSIZE)(a1 + 312)) )
              {
                tmAveCharWidth = (int)(((int)((unsigned __int64)(1321528399LL * *v19) >> 32) >> 3)
                                     + 1
                                     + ((unsigned int)((unsigned __int64)(1321528399LL * *v19) >> 32) >> 31))
                               / 2;
              }
              else
              {
                tmAveCharWidth = tm.tmAveCharWidth;
              }
              *v19 = tmAveCharWidth;
              *(_DWORD *)(a1 + 316) = tm.tmHeight;
              if ( v20 )
                SelectObject(v13, v20);
              DeleteObject(v18);
              v4 = 1;
              *(_OWORD *)(a1 + 232) = *(_OWORD *)a2;
              *(_OWORD *)(a1 + 248) = *((_OWORD *)a2 + 1);
              *(_OWORD *)(a1 + 264) = *((_OWORD *)a2 + 2);
              *(_OWORD *)(a1 + 280) = *((_OWORD *)a2 + 3);
              *(_OWORD *)(a1 + 296) = *((_OWORD *)a2 + 4);
            }
            ReleaseDC(*(HWND *)a1, v13);
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001bf78  mov     [rsp-8+arg_10], rbx
0x18001bf7d  push    rbp
0x18001bf7e  push    rsi
0x18001bf7f  push    rdi
0x18001bf80  push    r12
0x18001bf82  push    r13
0x18001bf84  push    r14
0x18001bf86  push    r15
0x18001bf88  lea     rbp, [rsp-27h]
0x18001bf8d  sub     rsp, 0D0h
0x18001bf94  mov     rax, cs:__security_cookie
0x18001bf9b  xor     rax, rsp
0x18001bf9e  mov     [rbp+57h+var_40], rax
0x18001bfa2  mov     rsi, rdx
0x18001bfa5  mov     rdi, rcx
0x18001bfa8  xor     edx, edx; Val
0x18001bfaa  lea     rcx, [rbp+57h+lf]; void *
0x18001bfae  lea     r8d, [rdx+5Ch]; Size
0x18001bfb2  call    memset
0x18001bfb7  xor     r13d, r13d
0x18001bfba  mov     r15d, r13d
0x18001bfbd  test    rsi, rsi
0x18001bfc0  jz      loc_18001C1AA
0x18001bfc6  movzx   r10d, word ptr [rsi]
0x18001bfca  test    r10w, r10w
0x18001bfce  jle     loc_18001C1AA
0x18001bfd4  lea     r8, [rsi+2]
0x18001bfd8  cmp     [r8], r13w
0x18001bfdc  jz      loc_18001C1AA
0x18001bfe2  mov     edx, 7FFFFFFEh
0x18001bfe7  lea     ecx, [r13+20h]
0x18001bfeb  mov     r9, r8
0x18001bfee  lea     rax, [rbp+57h+lf.lfFaceName]
0x18001bff2  test    rdx, rdx
0x18001bff5  jz      short loc_18001C016
0x18001bff7  movzx   r11d, word ptr [r9]
0x18001bffb  test    r11w, r11w
0x18001bfff  jz      short loc_18001C016
0x18001c001  mov     [rax], r11w
0x18001c005  add     r9, 2
0x18001c009  add     rax, 2
0x18001c00d  dec     rdx
0x18001c010  sub     rcx, 1
0x18001c014  jnz     short loc_18001BFF2
0x18001c016  test    rcx, rcx
0x18001c019  lea     rdx, [rax-2]
0x18001c01d  cmovnz  rdx, rax
0x18001c021  mov     eax, [rdi+130h]
0x18001c027  mov     [rdx], r13w
0x18001c02b  cmp     [rsi+48h], eax
0x18001c02e  jnz     short loc_18001C062
0x18001c030  mov     eax, [rdi+12Ch]
0x18001c036  cmp     [rsi+44h], eax
0x18001c039  jnz     short loc_18001C062
0x18001c03b  cmp     r10w, [rdi+0E8h]
0x18001c043  jnz     short loc_18001C062
0x18001c045  lea     rdx, [rdi+0EAh]; lpString2
0x18001c04c  mov     rcx, r8; lpString1
0x18001c04f  call    cs:__imp_lstrcmpiW
0x18001c055  test    eax, eax
0x18001c057  jnz     short loc_18001C062
0x18001c059  lea     r15d, [rax+1]
0x18001c05d  jmp     loc_18001C1AA
0x18001c062  mov     rcx, [rdi]; hWnd
0x18001c065  call    cs:__imp_GetDC
0x18001c06b  mov     r14, rax
0x18001c06e  test    rax, rax
0x18001c071  jz      loc_18001C1AA
0x18001c077  movsx   ebx, word ptr [rsi]
0x18001c07a  mov     edx, 5Ah ; 'Z'; index
0x18001c07f  mov     rcx, rax; hdc
0x18001c082  call    cs:__imp_GetDeviceCaps
0x18001c088  mov     r8d, 48h ; 'H'; nDenominator
0x18001c08e  mov     ecx, ebx; nNumber
0x18001c090  mov     edx, eax; nNumerator
0x18001c092  call    cs:__imp_MulDiv
0x18001c098  lea     rcx, [rbp+57h+lf]; lplf
0x18001c09c  mov     [rbp+57h+lf.lfWeight], 190h
0x18001c0a3  neg     eax
0x18001c0a5  mov     [rbp+57h+lf.lfHeight], eax
0x18001c0a8  mov     al, [rsi+48h]
0x18001c0ab  mov     [rbp+57h+lf.lfCharSet], al
0x18001c0ae  mov     al, [rsi+44h]
0x18001c0b1  mov     [rbp+57h+lf.lfItalic], al
0x18001c0b4  call    cs:__imp_CreateFontIndirectW
0x18001c0ba  mov     r12, rax
0x18001c0bd  test    rax, rax
0x18001c0c0  jz      loc_18001C19E
0x18001c0c6  mov     rdx, rax; h
0x18001c0c9  mov     rcx, r14; hdc
0x18001c0cc  call    cs:__imp_SelectObject
0x18001c0d2  xorps   xmm0, xmm0
0x18001c0d5  lea     rdx, [rsp+100h+tm]; lptm
0x18001c0da  movups  xmmword ptr [rbp+57h+tm.tmOverhang], xmm0
0x18001c0de  mov     rcx, r14; hdc
0x18001c0e1  lea     rbx, [rdi+138h]
0x18001c0e8  movups  xmmword ptr [rbp+57h+tm.tmFirstChar], xmm0
0x18001c0ec  mov     r15, rax
0x18001c0ef  movups  xmmword ptr [rsp+100h+tm.tmHeight], xmm0
0x18001c0f4  movups  xmmword ptr [rbp+57h+tm.tmExternalLeading], xmm0
0x18001c0f8  call    cs:__imp_GetTextMetricsW
0x18001c0fe  test    [rbp+57h+tm.tmPitchAndFamily], 1
0x18001c102  jz      short loc_18001C13C
0x18001c104  mov     r9, rbx; psizl
0x18001c107  lea     rdx, AveCharWidthData; "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLM"...
0x18001c10e  mov     r8d, 34h ; '4'; c
0x18001c114  mov     rcx, r14; hdc
0x18001c117  call    cs:__imp_GetTextExtentPoint32W
0x18001c11d  cmp     eax, 1
0x18001c120  jnz     short loc_18001C13C
0x18001c122  mov     eax, 4EC4EC4Fh
0x18001c127  imul    dword ptr [rbx]
0x18001c129  sar     edx, 3
0x18001c12c  mov     eax, edx
0x18001c12e  inc     edx
0x18001c130  shr     eax, 1Fh
0x18001c133  add     eax, edx
0x18001c135  cdq
0x18001c136  sub     eax, edx
0x18001c138  sar     eax, 1
0x18001c13a  jmp     short loc_18001C13F
0x18001c13c  mov     eax, [rbp+57h+tm.tmAveCharWidth]
0x18001c13f  mov     [rbx], eax
0x18001c141  mov     eax, [rsp+100h+tm.tmHeight]
0x18001c145  mov     [rbx+4], eax
0x18001c148  test    r15, r15
0x18001c14b  jz      short loc_18001C159
0x18001c14d  mov     rdx, r15; h
0x18001c150  mov     rcx, r14; hdc
0x18001c153  call    cs:__imp_SelectObject
0x18001c159  mov     rcx, r12; ho
0x18001c15c  call    cs:__imp_DeleteObject
0x18001c162  movaps  xmm0, xmmword ptr [rsi]
0x18001c165  mov     r15d, 1
0x18001c16b  movups  xmmword ptr [rdi+0E8h], xmm0
0x18001c172  movaps  xmm1, xmmword ptr [rsi+10h]
0x18001c176  movups  xmmword ptr [rdi+0F8h], xmm1
0x18001c17d  movaps  xmm0, xmmword ptr [rsi+20h]
0x18001c181  movups  xmmword ptr [rdi+108h], xmm0
0x18001c188  movaps  xmm1, xmmword ptr [rsi+30h]
0x18001c18c  movups  xmmword ptr [rdi+118h], xmm1
0x18001c193  movaps  xmm0, xmmword ptr [rsi+40h]
0x18001c197  movups  xmmword ptr [rdi+128h], xmm0
0x18001c19e  mov     rcx, [rdi]; hWnd
0x18001c1a1  mov     rdx, r14; hDC
0x18001c1a4  call    cs:__imp_ReleaseDC
0x18001c1aa  mov     eax, r15d
0x18001c1ad  mov     rcx, [rbp+57h+var_40]
0x18001c1b1  xor     rcx, rsp; StackCookie
0x18001c1b4  call    __security_check_cookie
0x18001c1b9  mov     rbx, [rsp+100h+arg_10]
0x18001c1c1  add     rsp, 0D0h
0x18001c1c8  pop     r15
0x18001c1ca  pop     r14
0x18001c1cc  pop     r13
0x18001c1ce  pop     r12
0x18001c1d0  pop     rdi
0x18001c1d1  pop     rsi
0x18001c1d2  pop     rbp
0x18001c1d3  retn
```
