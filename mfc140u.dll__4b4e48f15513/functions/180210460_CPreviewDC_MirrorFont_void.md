# CPreviewDC::MirrorFont(void)

- ea: `0x180210460`
- end: `0x180210660`
- name: `?MirrorFont@CPreviewDC@@IEAAXXZ`
- size: `512`
- prototype: `void __fastcall(CPreviewDC *this)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180210040`
- `0x1802100e0`
- `0x180210160`
- `0x180210200`
- `0x1802103b0`
- `0x180210660`

## callees

- `0x180210460`
- `0x180231d70`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1802105c3`
- `KERNEL32!MulDiv` at `0x1802105d4`
- `KERNEL32!MulDiv` at `0x1802105c3`
- `KERNEL32!MulDiv` at `0x1802105d4`
- `GDI32!CreateFontIndirectW` at `0x180210542`
- `GDI32!CreateFontIndirectW` at `0x1802105f8`
- `GDI32!CreateFontIndirectW` at `0x180210542`
- `GDI32!CreateFontIndirectW` at `0x1802105f8`
- `GDI32!DeleteObject` at `0x180210611`
- `GDI32!DeleteObject` at `0x180210628`
- `GDI32!DeleteObject` at `0x180210611`
- `GDI32!DeleteObject` at `0x180210628`
- `GDI32!SelectObject` at `0x180210552`
- `GDI32!SelectObject` at `0x180210608`
- `GDI32!SelectObject` at `0x180210552`
- `GDI32!SelectObject` at `0x180210608`
- `GDI32!GetObjectW` at `0x1802104d1`
- `GDI32!GetObjectW` at `0x1802104d1`
- `GDI32!GetTextMetricsW` at `0x1802104fa`
- `GDI32!GetTextMetricsW` at `0x180210560`
- `GDI32!GetTextMetricsW` at `0x1802104fa`
- `GDI32!GetTextMetricsW` at `0x180210560`
- `GDI32!GetTextFaceW` at `0x1802104ec`
- `GDI32!GetTextFaceW` at `0x1802104ec`
- `GDI32!GetWindowExtEx` at `0x18021058d`
- `GDI32!GetWindowExtEx` at `0x18021058d`
- `GDI32!GetViewportExtEx` at `0x18021059f`
- `GDI32!GetViewportExtEx` at `0x18021059f`

## pseudocode

```c
void __fastcall CPreviewDC::MirrorFont(CPreviewDC *this)
{
  HFONT__ *m_hPrinterFont; // rcx
  HFONT FontIndirectW; // r14
  int v4; // ebx
  int v5; // esi
  HDC__ *m_hDC; // rcx
  HDC__ *v7; // rcx
  int cy; // r8d
  int tmAscent; // edx
  int v10; // ebx
  HFONT v11; // rbx
  HFONT__ **p_m_hFont; // rdi
  CSize sizeVpExt; // [rsp+28h] [rbp-79h] BYREF
  tagTEXTMETRICW tm; // [rsp+30h] [rbp-71h] BYREF
  wchar_t v15; // [rsp+6Ch] [rbp-35h]
  char v16; // [rsp+6Eh] [rbp-33h]
  char v17; // [rsp+6Fh] [rbp-32h]
  tagLOGFONTW logFont; // [rsp+70h] [rbp-31h] BYREF

  if ( this->m_hAttribDC )
  {
    m_hPrinterFont = this->m_hPrinterFont;
    if ( m_hPrinterFont )
    {
      if ( this->m_hDC && GetObjectW(m_hPrinterFont, 92, &logFont.lfEscapement) )
      {
        GetTextFaceW(this->m_hAttribDC, 32, &logFont.lfFaceName[4]);
        GetTextMetricsW(this->m_hAttribDC, (LPTEXTMETRICW)&tm.tmDescent);
        logFont.lfEscapement = tm.tmDescent >= 0 ? tm.tmAveCharWidth - tm.tmDescent : tm.tmDescent;
        logFont.lfOrientation = tm.tmWeight;
        *(_DWORD *)&logFont.lfOutPrecision = tm.tmDigitizedAspectX;
        logFont.lfFaceName[0] = v15;
        LOBYTE(logFont.lfFaceName[1]) = v16;
        HIBYTE(logFont.lfFaceName[1]) = logFont.lfHeight;
        HIBYTE(logFont.lfFaceName[3]) = v17;
        FontIndirectW = CreateFontIndirectW((const LOGFONTW *)&logFont.lfEscapement);
        SelectObject(this->m_hDC, FontIndirectW);
        if ( GetTextMetricsW(this->m_hDC, (LPTEXTMETRICW)&tm.tmDescent) )
        {
          v4 = -logFont.lfEscapement;
          if ( tm.tmDescent >= 0 )
            v5 = tm.tmDescent - tm.tmAveCharWidth;
          else
            v5 = -tm.tmDescent;
          m_hDC = this->m_hDC;
          sizeVpExt = 0;
          GetWindowExtEx(m_hDC, &sizeVpExt);
          v7 = this->m_hDC;
          *(_QWORD *)&tm.tmHeight = 0;
          GetViewportExtEx(v7, (LPSIZE)&tm);
          cy = sizeVpExt.cy;
          if ( sizeVpExt.cy < 0 )
          {
            cy = -sizeVpExt.cy;
            sizeVpExt.cy = -sizeVpExt.cy;
          }
          tmAscent = tm.tmAscent;
          if ( tm.tmAscent < 0 )
          {
            tmAscent = -tm.tmAscent;
            tm.tmAscent = -tm.tmAscent;
          }
          v10 = MulDiv(v4, tmAscent, cy);
          if ( v10 < MulDiv(v5, tm.tmAscent, sizeVpExt.cy) )
          {
            HIBYTE(logFont.lfFaceName[4]) = 0;
            *(wchar_t *)((char *)&logFont.lfFaceName[3] + 1) = (HIBYTE(logFont.lfFaceName[3]) & 0xF0) != 80 ? 0 : 0x50;
            v11 = CreateFontIndirectW((const LOGFONTW *)&logFont.lfEscapement);
            SelectObject(this->m_hDC, v11);
            DeleteObject(FontIndirectW);
            FontIndirectW = v11;
          }
          p_m_hFont = &this->m_hFont;
          if ( !p_m_hFont )
            AfxThrowInvalidArgException();
          if ( *p_m_hFont )
            DeleteObject(*p_m_hFont);
          *p_m_hFont = FontIndirectW;
        }
      }
    }
    else
    {
      this->SelectStockObject(this, 14);
    }
  }
}

```

## disassembly

```asm
0x180210460  mov     rax, rsp
0x180210463  mov     [rax+10h], rbx
0x180210467  mov     [rax+18h], rsi
0x18021046b  mov     [rax+20h], rdi
0x18021046f  push    rbp
0x180210470  push    r14
0x180210472  push    r15
0x180210474  lea     rbp, [rax-5Fh]
0x180210478  sub     rsp, 0E0h
0x18021047f  mov     rax, cs:__security_cookie
0x180210486  xor     rax, rsp
0x180210489  mov     [rbp+57h+var_20], rax
0x18021048d  xor     r15d, r15d
0x180210490  mov     rdi, this
0x180210493  cmp     [this+10h], r15
0x180210497  jz      loc_180210631
0x18021049d  mov     this, [this+40h]; h
0x1802104a1  test    this, this
0x1802104a4  jnz     short loc_1802104BE
0x1802104a6  mov     rax, [rdi]
0x1802104a9  lea     edx, [this+0Eh]
0x1802104ac  mov     this, rdi
0x1802104af  mov     rax, [rax+58h]
0x1802104b3  call    cs:__guard_dispatch_icall_fptr
0x1802104b9  jmp     loc_180210631
0x1802104be  cmp     [rdi+8], r15
0x1802104c2  jz      loc_180210631
0x1802104c8  lea     r8, [rbp+57h+logFont.lfEscapement]; pv
0x1802104cc  mov     edx, 5Ch ; '\'; c
0x1802104d1  call    cs:__imp_GetObjectW
0x1802104d7  test    eax, eax
0x1802104d9  jz      loc_180210631
0x1802104df  mov     this, [rdi+10h]; hdc
0x1802104e3  lea     r8, [rbp+57h+logFont.lfFaceName+8]; lpName
0x1802104e7  mov     edx, 20h ; ' '; c
0x1802104ec  call    cs:__imp_GetTextFaceW
0x1802104f2  mov     this, [rdi+10h]; hdc
0x1802104f6  lea     rdx, [rbp+57h+tm.tmDescent]; lptm
0x1802104fa  call    cs:__imp_GetTextMetricsW
0x180210500  mov     ecx, [rbp+57h+tm.tmDescent]
0x180210503  test    ecx, ecx
0x180210505  jns     short loc_18021050C
0x180210507  mov     [rbp+57h+logFont.lfEscapement], ecx
0x18021050a  jmp     short loc_180210514
0x18021050c  mov     eax, [rbp+57h+tm.tmAveCharWidth]
0x18021050f  sub     eax, ecx
0x180210511  mov     [rbp+57h+logFont.lfEscapement], eax
0x180210514  mov     eax, [rbp+57h+tm.tmWeight]
0x180210517  lea     this, [rbp+57h+logFont.lfEscapement]; lplf
0x18021051b  mov     [rbp+57h+logFont.lfOrientation], eax
0x18021051e  mov     eax, [rbp+57h+tm.tmDigitizedAspectX]
0x180210521  mov     dword ptr [rbp+57h+logFont.lfOutPrecision], eax
0x180210524  mov     al, byte ptr [rbp+57h+var_8C]
0x180210527  mov     byte ptr [rbp+57h+logFont.lfFaceName], al
0x18021052a  mov     al, byte ptr [rbp+57h+var_8C+1]
0x18021052d  mov     byte ptr [rbp+57h+logFont.lfFaceName+1], al
0x180210530  mov     al, [rbp+57h+var_8A]
0x180210533  mov     byte ptr [rbp+57h+logFont.lfFaceName+2], al
0x180210536  mov     al, byte ptr [rbp+57h+logFont.lfHeight]
0x180210539  mov     byte ptr [rbp+57h+logFont.lfFaceName+3], al
0x18021053c  mov     al, [rbp+57h+var_89]
0x18021053f  mov     byte ptr [rbp+57h+logFont.lfFaceName+7], al
0x180210542  call    cs:__imp_CreateFontIndirectW
0x180210548  mov     this, [rdi+8]; hdc
0x18021054c  mov     rdx, rax; h
0x18021054f  mov     r14, rax
0x180210552  call    cs:__imp_SelectObject
0x180210558  mov     this, [rdi+8]; hdc
0x18021055c  lea     rdx, [rbp+57h+tm.tmDescent]; lptm
0x180210560  call    cs:__imp_GetTextMetricsW
0x180210566  test    eax, eax
0x180210568  jz      loc_180210631
0x18021056e  mov     ebx, [rbp+57h+logFont.lfEscapement]
0x180210571  mov     esi, [rbp+57h+tm.tmDescent]
0x180210574  neg     ebx
0x180210576  test    esi, esi
0x180210578  jns     short loc_18021057E
0x18021057a  neg     esi
0x18021057c  jmp     short loc_180210581
0x18021057e  sub     esi, [rbp+57h+tm.tmAveCharWidth]
0x180210581  mov     this, [rdi+8]; hdc
0x180210585  lea     rdx, [rbp+57h+sizeVpExt]; lpsize
0x180210589  mov     qword ptr [rbp+57h+sizeVpExt.cx], r15
0x18021058d  call    cs:__imp_GetWindowExtEx
0x180210593  mov     this, [rdi+8]; hdc
0x180210597  lea     rdx, [rbp+57h+tm]; lpsize
0x18021059b  mov     qword ptr [rbp+57h+tm.tmHeight], r15
0x18021059f  call    cs:__imp_GetViewportExtEx
0x1802105a5  mov     r8d, [rbp+57h+sizeVpExt.cy]
0x1802105a9  test    r8d, r8d
0x1802105ac  jns     short loc_1802105B5
0x1802105ae  neg     r8d; nDenominator
0x1802105b1  mov     [rbp+57h+sizeVpExt.cy], r8d
0x1802105b5  mov     edx, [rbp+57h+tm.tmAscent]
0x1802105b8  test    edx, edx
0x1802105ba  jns     short loc_1802105C1
0x1802105bc  neg     edx; nNumerator
0x1802105be  mov     [rbp+57h+tm.tmAscent], edx
0x1802105c1  mov     ecx, ebx; nNumber
0x1802105c3  call    cs:__imp_MulDiv
0x1802105c9  mov     r8d, [rbp+57h+sizeVpExt.cy]; nDenominator
0x1802105cd  mov     ecx, esi; nNumber
0x1802105cf  mov     edx, [rbp+57h+tm.tmAscent]; nNumerator
0x1802105d2  mov     ebx, eax
0x1802105d4  call    cs:__imp_MulDiv
0x1802105da  cmp     ebx, eax
0x1802105dc  jge     short loc_18021061A
0x1802105de  mov     al, byte ptr [rbp+57h+logFont.lfFaceName+7]
0x1802105e1  lea     this, [rbp+57h+logFont.lfEscapement]; lplf
0x1802105e5  and     al, 0F0h
0x1802105e7  mov     [rbp+57h+logFont.lfFaceName+8], r15w
0x1802105ec  cmp     al, 50h ; 'P'
0x1802105ee  setnz   al
0x1802105f1  dec     al
0x1802105f3  and     al, 50h
0x1802105f5  mov     byte ptr [rbp+57h+logFont.lfFaceName+7], al
0x1802105f8  call    cs:__imp_CreateFontIndirectW
0x1802105fe  mov     this, [rdi+8]; hdc
0x180210602  mov     rdx, rax; h
0x180210605  mov     rbx, rax
0x180210608  call    cs:__imp_SelectObject
0x18021060e  mov     this, r14; ho
0x180210611  call    cs:__imp_DeleteObject
0x180210617  mov     r14, rbx
0x18021061a  add     rdi, 38h ; '8'
0x18021061e  jz      short loc_18021065A
0x180210620  mov     this, [rdi]; ho
0x180210623  test    this, this
0x180210626  jz      short loc_18021062E
0x180210628  call    cs:__imp_DeleteObject
0x18021062e  mov     [rdi], r14
0x180210631  mov     this, [rbp+57h+var_20]
0x180210635  xor     this, rsp; StackCookie
0x180210638  call    __security_check_cookie
0x18021063d  lea     r11, [rsp+0F0h+var_10]
0x180210645  mov     rbx, [r11+28h]
0x180210649  mov     rsi, [r11+30h]
0x18021064d  mov     rdi, [r11+38h]
0x180210651  mov     rsp, r11
0x180210654  pop     r15
0x180210656  pop     r14
0x180210658  pop     rbp
0x180210659  retn
0x18021065a  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
