# CreateUserFont(char const *,ulong *,HDC__ *,int)

- ea: `0x1800661d0`
- end: `0x1800665c6`
- name: `?CreateUserFont@@YAPEAUHFONT__@@PEBDPEAKPEAUHDC__@@H@Z`
- size: `1014`
- prototype: `HFONT(const char *, unsigned int *, HDC, int)`
- caller_count: `6`
- callee_count: `10`
- tags: ``

## callers

- `0x1800197c8`
- `0x1800310a0`
- `0x1800325e0`
- `0x18003b090`
- `0x180047ffc`
- `0x18005d400`

## callees

- `0x180020100`
- `0x180042da8`
- `0x18004f65c`
- `0x180065438`
- `0x1800661d0`
- `0x180068194`
- `0x180069430`
- `0x18006a7ac`
- `0x18006c384`
- `0x180075c90`

## import_xrefs

- `msvcrt!free` at `0x1800663ab`
- `msvcrt!free` at `0x180066592`
- `msvcrt!free` at `0x1800663ab`
- `msvcrt!free` at `0x180066592`
- `KERNEL32!GetSystemDefaultLCID` at `0x1800664df`
- `KERNEL32!GetSystemDefaultLCID` at `0x1800664df`
- `KERNEL32!MulDiv` at `0x18006653d`
- `KERNEL32!MulDiv` at `0x180066568`
- `KERNEL32!MulDiv` at `0x18006653d`
- `KERNEL32!MulDiv` at `0x180066568`
- `USER32!ReleaseDC` at `0x1800664d3`
- `USER32!ReleaseDC` at `0x1800664d3`
- `USER32!GetDC` at `0x180066496`
- `USER32!GetDC` at `0x180066496`
- `USER32!GetDesktopWindow` at `0x18006648a`
- `USER32!GetDesktopWindow` at `0x18006648a`
- `GDI32!DeleteDC` at `0x180066548`
- `GDI32!DeleteDC` at `0x180066548`
- `GDI32!CreateICA` at `0x18006651c`
- `GDI32!CreateICA` at `0x18006651c`
- `GDI32!GetDeviceCaps` at `0x18006652d`
- `GDI32!GetDeviceCaps` at `0x180066558`
- `GDI32!GetDeviceCaps` at `0x18006652d`
- `GDI32!GetDeviceCaps` at `0x180066558`
- `GDI32!GetTextMetricsA` at `0x1800664c0`
- `GDI32!GetTextMetricsA` at `0x1800664c0`
- `GDI32!CreateFontIndirectA` at `0x180066579`
- `GDI32!CreateFontIndirectA` at `0x180066579`
- `SHLWAPI!StrChrA` at `0x180066263`
- `SHLWAPI!StrChrA` at `0x1800662a3`
- `SHLWAPI!StrChrA` at `0x1800662dc`
- `SHLWAPI!StrChrA` at `0x180066263`
- `SHLWAPI!StrChrA` at `0x1800662a3`
- `SHLWAPI!StrChrA` at `0x1800662dc`

## pseudocode

```c
HFONT __fastcall CreateUserFont(const char *a1, unsigned int *a2, HDC a3, int a4)
{
  CHAR *v7; // rbx
  PSTR v8; // rax
  int v9; // esi
  const char *NonSpace; // rax
  const CHAR *v11; // r10
  PSTR v12; // rax
  const char *v13; // rax
  const CHAR *v14; // r10
  PSTR v15; // rax
  const CHAR *v16; // rdi
  __int64 v17; // rax
  LONG lfWeight; // ecx
  __int64 v19; // rax
  BYTE lfItalic; // cl
  __int64 v21; // rax
  BYTE lfUnderline; // cl
  void *v23; // rdi
  __int64 v24; // rax
  CHAR *lfFaceName; // rcx
  CHAR *v26; // r8
  __int64 v27; // rdx
  CHAR *v28; // rax
  HWND DesktopWindow; // r14
  HDC DC; // rdi
  int v31; // esi
  HDC ICA; // rdi
  int v33; // eax
  int v34; // esi
  int DeviceCaps; // eax
  HFONT v36; // rdi
  void *Block; // [rsp+20h] [rbp-79h] BYREF
  LOGFONTA lf; // [rsp+28h] [rbp-71h] BYREF
  struct tagTEXTMETRICA tm; // [rsp+68h] [rbp-31h] BYREF

  memset(&lf.lfWeight, 0, 44);
  lf.lfWeight = 400;
  lf.lfPitchAndFamily = 0;
  lf.lfCharSet = -1;
  *(_OWORD *)&lf.lfHeight = 0;
  if ( a2 )
    *a2 = -1;
  if ( a1 )
  {
    v7 = lcStrDup(a1);
    if ( !v7 )
      OOM();
  }
  else
  {
    v7 = 0;
  }
  v8 = StrChrA(v7, 0x2Cu);
  v9 = 12;
  if ( v8 )
  {
    *v8 = 0;
    NonSpace = (const char *)FirstNonSpace(v8 + 1);
    v11 = NonSpace;
    if ( (unsigned __int8)(*NonSpace - 48) <= 9u )
      v9 = Atoi(NonSpace);
    v12 = StrChrA(v11, 0x2Cu);
    if ( v12 )
    {
      v13 = (const char *)FirstNonSpace(v12 + 1);
      v14 = v13;
      if ( (unsigned __int8)(*v13 - 48) <= 9u )
        lf.lfCharSet = Atoi(v13);
      v15 = StrChrA(v14, 0x2Cu);
      if ( v15 )
      {
        v16 = (const CHAR *)FirstNonSpace(v15 + 1);
        v17 = HHStrStrIA(v16, "BOLD");
        lfWeight = lf.lfWeight;
        if ( v17 )
          lfWeight = 700;
        lf.lfWeight = lfWeight;
        v19 = HHStrStrIA(v16, "ITALIC");
        lfItalic = lf.lfItalic;
        if ( v19 )
          lfItalic = 1;
        lf.lfItalic = lfItalic;
        v21 = HHStrStrIA(v16, "UNDERLINE");
        lfUnderline = lf.lfUnderline;
        if ( v21 )
          lfUnderline = 1;
        lf.lfUnderline = lfUnderline;
        if ( HHStrStrIA(v16, "#") )
        {
          Block = 0;
          CWStr::operator=(&Block, v16);
          v23 = Block;
          if ( a2 )
            *a2 = IEColorToWin32Color((const unsigned __int16 *)Block);
          if ( v23 )
            free(v23);
        }
        else if ( (HHStrStrIA(v16, "0x") || HHStrStrIA(v16, "0X")) && a2 )
        {
          *a2 = Atoi(v16);
        }
      }
    }
  }
  v24 = 31;
  lfFaceName = lf.lfFaceName;
  v26 = v7;
  v27 = 32;
  do
  {
    if ( !v24 )
      break;
    if ( !*v26 )
      break;
    *lfFaceName++ = *v26++;
    --v24;
    --v27;
  }
  while ( v27 );
  v28 = lfFaceName - 1;
  if ( v27 )
    v28 = lfFaceName;
  *v28 = 0;
  *(_WORD *)&lf.lfOutPrecision = 0;
  lf.lfQuality = 0;
  if ( a4 == -1 )
  {
    if ( lf.lfCharSet == 0xFF )
    {
      if ( v7 && ((unsigned int)IsSamePrefix(v7, "Symbol", -1) || (unsigned int)IsSamePrefix(v7, "WingDings", -1)) )
      {
        lf.lfCharSet = 2;
      }
      else
      {
        DesktopWindow = GetDesktopWindow();
        DC = GetDC(DesktopWindow);
        if ( DC )
        {
          memset(&tm, 0, sizeof(tm));
          GetTextMetricsA(DC, &tm);
          lf.lfCharSet = tm.tmCharSet;
          ReleaseDC(DesktopWindow, DC);
        }
        else
        {
          lf.lfCharSet = 0;
        }
      }
    }
  }
  else
  {
    lf.lfCharSet = a4;
  }
  if ( (GetSystemDefaultLCID() & 0x3FF) == 0x1E && g_bWinNT5 && v9 < 11 )
    v9 = 11;
  v31 = 2 * v9;
  if ( a3 )
  {
    DeviceCaps = GetDeviceCaps(a3, 90);
    v34 = MulDiv(DeviceCaps, v31, 144);
  }
  else
  {
    ICA = CreateICA("DISPLAY", 0, 0, 0);
    v33 = GetDeviceCaps(ICA, 90);
    v34 = MulDiv(v33, v31, 144);
    DeleteDC(ICA);
  }
  lf.lfHeight = -v34;
  v36 = CreateFontIndirectA(&lf);
  if ( v7 )
    free(v7);
  return v36;
}

```

## disassembly

```asm
0x1800661d0  push    rbp
0x1800661d2  push    r12
0x1800661d4  push    r14
0x1800661d6  push    r15
0x1800661d8  lea     rbp, [rsp-3Fh]
0x1800661dd  sub     rsp, 0D8h
0x1800661e4  mov     rax, cs:__security_cookie
0x1800661eb  xor     rax, rsp
0x1800661ee  mov     [rbp+57h+var_50], rax
0x1800661f2  xorps   xmm0, xmm0
0x1800661f5  xor     eax, eax
0x1800661f7  mov     r15d, r9d
0x1800661fa  mov     r12, r8
0x1800661fd  mov     r14, rdx
0x180066200  movups  xmmword ptr [rbp+57h+lf.lfWeight], xmm0
0x180066204  mov     [rbp+57h+lf.lfWeight], 190h
0x18006620b  mov     [rbp+57h+lf.lfPitchAndFamily], al
0x18006620e  mov     [rbp+57h+lf.lfCharSet], 0FFh
0x180066212  movups  xmmword ptr [rbp+57h+lf.lfFaceName+4], xmm0
0x180066216  movups  xmmword ptr [rbp+57h+lf.lfFaceName+10h], xmm0
0x18006621a  movups  xmmword ptr [rbp+57h+lf.lfHeight], xmm0
0x18006621e  test    rdx, rdx
0x180066221  jz      short loc_180066229
0x180066223  mov     dword ptr [rdx], 0FFFFFFFFh
0x180066229  mov     [rsp+0F0h+var_20], rbx
0x180066231  test    rcx, rcx
0x180066234  jz      short loc_180066249
0x180066236  call    ?lcStrDup@@YAPEADPEBD@Z; lcStrDup(char const *)
0x18006623b  mov     rbx, rax
0x18006623e  test    rax, rax
0x180066241  jnz     short loc_18006624B
0x180066243  call    ?OOM@@YAXXZ; OOM(void)
0x180066249  xor     ebx, ebx
0x18006624b  mov     [rsp+0F0h+var_28], rsi
0x180066253  mov     edx, 2Ch ; ','; wMatch
0x180066258  mov     rcx, rbx; pszStart
0x18006625b  mov     [rsp+0F0h+var_30], rdi
0x180066263  call    cs:__imp_StrChrA
0x180066269  mov     esi, 0Ch
0x18006626e  test    rax, rax
0x180066271  jz      loc_1800663EB
0x180066277  lea     rcx, [rax+1]
0x18006627b  mov     byte ptr [rax], 0
0x18006627e  call    FirstNonSpace
0x180066283  mov     r10, rax
0x180066286  movzx   ecx, byte ptr [rax]
0x180066289  sub     cl, 30h ; '0'
0x18006628c  cmp     cl, 9
0x18006628f  ja      short loc_18006629B
0x180066291  mov     rcx, rax; char *
0x180066294  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x180066299  mov     esi, eax
0x18006629b  mov     edx, 2Ch ; ','; wMatch
0x1800662a0  mov     rcx, r10; pszStart
0x1800662a3  call    cs:__imp_StrChrA
0x1800662a9  test    rax, rax
0x1800662ac  jz      loc_1800663EB
0x1800662b2  lea     rcx, [rax+1]
0x1800662b6  call    FirstNonSpace
0x1800662bb  mov     r10, rax
0x1800662be  movzx   ecx, byte ptr [rax]
0x1800662c1  sub     cl, 30h ; '0'
0x1800662c4  cmp     cl, 9
0x1800662c7  ja      short loc_1800662D4
0x1800662c9  mov     rcx, rax; char *
0x1800662cc  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x1800662d1  mov     [rbp+57h+lf.lfCharSet], al
0x1800662d4  mov     edx, 2Ch ; ','; wMatch
0x1800662d9  mov     rcx, r10; pszStart
0x1800662dc  call    cs:__imp_StrChrA
0x1800662e2  test    rax, rax
0x1800662e5  jz      loc_1800663EB
0x1800662eb  lea     rcx, [rax+1]
0x1800662ef  mov     [rsp+0F0h+var_38], r13
0x1800662f7  call    FirstNonSpace
0x1800662fc  lea     rdx, aBold; "BOLD"
0x180066303  mov     rcx, rax; pszStart
0x180066306  mov     rdi, rax
0x180066309  call    HHStrStrIA
0x18006630e  mov     ecx, [rbp+57h+lf.lfWeight]
0x180066311  test    rax, rax
0x180066314  mov     edx, 2BCh
0x180066319  cmovnz  ecx, edx
0x18006631c  lea     rdx, aItalic_0; "ITALIC"
0x180066323  mov     [rbp+57h+lf.lfWeight], ecx
0x180066326  mov     rcx, rdi; pszStart
0x180066329  call    HHStrStrIA
0x18006632e  movzx   ecx, [rbp+57h+lf.lfItalic]
0x180066332  lea     rdx, aUnderline_0; "UNDERLINE"
0x180066339  test    rax, rax
0x18006633c  mov     r13d, 1
0x180066342  cmovnz  ecx, r13d
0x180066346  mov     [rbp+57h+lf.lfItalic], cl
0x180066349  mov     rcx, rdi; pszStart
0x18006634c  call    HHStrStrIA
0x180066351  movzx   ecx, [rbp+57h+lf.lfUnderline]
0x180066355  lea     rdx, asc_18007FFCC; "#"
0x18006635c  test    rax, rax
0x18006635f  cmovnz  ecx, r13d
0x180066363  mov     [rbp+57h+lf.lfUnderline], cl
0x180066366  mov     rcx, rdi; pszStart
0x180066369  call    HHStrStrIA
0x18006636e  mov     r13, [rsp+0F0h+var_38]
0x180066376  test    rax, rax
0x180066379  jz      short loc_1800663B3
0x18006637b  mov     rdx, rdi
0x18006637e  mov     [rbp+57h+Block], 0
0x180066386  lea     rcx, [rbp+57h+Block]
0x18006638a  call    ??4CWStr@@QEAAXPEBD@Z; CWStr::operator=(char const *)
0x18006638f  mov     rdi, [rbp+57h+Block]
0x180066393  test    r14, r14
0x180066396  jz      short loc_1800663A3
0x180066398  mov     rcx, rdi; unsigned __int16 *
0x18006639b  call    ?IEColorToWin32Color@@YAHPEBG@Z; IEColorToWin32Color(ushort const *)
0x1800663a0  mov     [r14], eax
0x1800663a3  test    rdi, rdi
0x1800663a6  jz      short loc_1800663EB
0x1800663a8  mov     rcx, rdi; Block
0x1800663ab  call    cs:__imp_free
0x1800663b1  jmp     short loc_1800663EB
0x1800663b3  lea     rdx, a0x_1; "0x"
0x1800663ba  mov     rcx, rdi; pszStart
0x1800663bd  call    HHStrStrIA
0x1800663c2  test    rax, rax
0x1800663c5  jnz     short loc_1800663DB
0x1800663c7  lea     rdx, a0x_2; "0X"
0x1800663ce  mov     rcx, rdi; pszStart
0x1800663d1  call    HHStrStrIA
0x1800663d6  test    rax, rax
0x1800663d9  jz      short loc_1800663EB
0x1800663db  test    r14, r14
0x1800663de  jz      short loc_1800663EB
0x1800663e0  mov     rcx, rdi; char *
0x1800663e3  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x1800663e8  mov     [r14], eax
0x1800663eb  mov     eax, 1Fh
0x1800663f0  lea     rcx, [rbp+57h+lf.lfFaceName]
0x1800663f4  mov     r8, rbx
0x1800663f7  mov     edx, 20h ; ' '
0x1800663fc  test    rax, rax
0x1800663ff  jz      short loc_18006641C
0x180066401  movzx   r9d, byte ptr [r8]
0x180066405  test    r9b, r9b
0x180066408  jz      short loc_18006641C
0x18006640a  mov     [rcx], r9b
0x18006640d  inc     r8
0x180066410  inc     rcx
0x180066413  dec     rax
0x180066416  sub     rdx, 1
0x18006641a  jnz     short loc_1800663FC
0x18006641c  test    rdx, rdx
0x18006641f  lea     rax, [rcx-1]
0x180066423  cmovnz  rax, rcx
0x180066427  mov     byte ptr [rax], 0
0x18006642a  mov     word ptr [rbp+57h+lf.lfOutPrecision], 0
0x180066430  mov     [rbp+57h+lf.lfQuality], 0
0x180066434  cmp     r15d, 0FFFFFFFFh
0x180066438  jz      short loc_180066443
0x18006643a  mov     [rbp+57h+lf.lfCharSet], r15b
0x18006643e  jmp     loc_1800664DF
0x180066443  cmp     [rbp+57h+lf.lfCharSet], 0FFh
0x180066447  jnz     loc_1800664DF
0x18006644d  test    rbx, rbx
0x180066450  jz      short loc_18006648A
0x180066452  mov     r8d, 0FFFFFFFFh; int
0x180066458  lea     rdx, aSymbol; "Symbol"
0x18006645f  mov     rcx, rbx; char *
0x180066462  call    ?IsSamePrefix@@YAHPEBD0H@Z; IsSamePrefix(char const *,char const *,int)
0x180066467  test    eax, eax
0x180066469  jnz     short loc_180066484
0x18006646b  mov     r8d, 0FFFFFFFFh; int
0x180066471  lea     rdx, aWingdings; "WingDings"
0x180066478  mov     rcx, rbx; char *
0x18006647b  call    ?IsSamePrefix@@YAHPEBD0H@Z; IsSamePrefix(char const *,char const *,int)
0x180066480  test    eax, eax
0x180066482  jz      short loc_18006648A
0x180066484  mov     [rbp+57h+lf.lfCharSet], 2
0x180066488  jmp     short loc_1800664DF
0x18006648a  call    cs:__imp_GetDesktopWindow
0x180066490  mov     rcx, rax; hWnd
0x180066493  mov     r14, rax
0x180066496  call    cs:__imp_GetDC
0x18006649c  mov     rdi, rax
0x18006649f  test    rax, rax
0x1800664a2  jz      short loc_1800664DB
0x1800664a4  xorps   xmm0, xmm0
0x1800664a7  lea     rdx, [rbp+57h+tm]; lptm
0x1800664ab  xor     eax, eax
0x1800664ad  mov     rcx, rdi; hdc
0x1800664b0  movups  xmmword ptr [rbp+57h+tm.tmHeight], xmm0
0x1800664b4  mov     qword ptr [rbp+57h+tm.tmItalic], rax
0x1800664b8  movups  xmmword ptr [rbp+57h+tm.tmExternalLeading], xmm0
0x1800664bc  movups  xmmword ptr [rbp+57h+tm.tmOverhang], xmm0
0x1800664c0  call    cs:__imp_GetTextMetricsA
0x1800664c6  movzx   ecx, [rbp+57h+tm.tmCharSet]
0x1800664ca  mov     rdx, rdi; hDC
0x1800664cd  mov     [rbp+57h+lf.lfCharSet], cl
0x1800664d0  mov     rcx, r14; hWnd
0x1800664d3  call    cs:__imp_ReleaseDC
0x1800664d9  jmp     short loc_1800664DF
0x1800664db  mov     [rbp+57h+lf.lfCharSet], 0
0x1800664df  call    cs:__imp_GetSystemDefaultLCID
0x1800664e5  mov     ecx, 3FFh
0x1800664ea  and     ax, cx
0x1800664ed  cmp     ax, 1Eh
0x1800664f1  jnz     short loc_180066506
0x1800664f3  cmp     cs:?g_bWinNT5@@3HA, 0; int g_bWinNT5
0x1800664fa  jz      short loc_180066506
0x1800664fc  mov     eax, 0Bh
0x180066501  cmp     esi, eax
0x180066503  cmovl   esi, eax
0x180066506  add     esi, esi
0x180066508  test    r12, r12
0x18006650b  jnz     short loc_180066550
0x18006650d  xor     r9d, r9d; pdm
0x180066510  lea     rcx, pszDriver; "DISPLAY"
0x180066517  xor     r8d, r8d; pszPort
0x18006651a  xor     edx, edx; pszDevice
0x18006651c  call    cs:__imp_CreateICA
0x180066522  mov     rcx, rax; hdc
0x180066525  mov     edx, 5Ah ; 'Z'; index
0x18006652a  mov     rdi, rax
0x18006652d  call    cs:__imp_GetDeviceCaps
0x180066533  mov     r8d, 90h; nDenominator
0x180066539  mov     edx, esi; nNumerator
0x18006653b  mov     ecx, eax; nNumber
0x18006653d  call    cs:__imp_MulDiv
0x180066543  mov     rcx, rdi; hdc
0x180066546  mov     esi, eax
0x180066548  call    cs:__imp_DeleteDC
0x18006654e  jmp     short loc_180066570
0x180066550  mov     edx, 5Ah ; 'Z'; index
0x180066555  mov     rcx, r12; hdc
0x180066558  call    cs:__imp_GetDeviceCaps
0x18006655e  mov     r8d, 90h; nDenominator
0x180066564  mov     edx, esi; nNumerator
0x180066566  mov     ecx, eax; nNumber
0x180066568  call    cs:__imp_MulDiv
0x18006656e  mov     esi, eax
0x180066570  neg     esi
0x180066572  lea     rcx, [rbp+57h+lf]; lplf
0x180066576  mov     [rbp+57h+lf.lfHeight], esi
0x180066579  call    cs:__imp_CreateFontIndirectA
0x18006657f  mov     rsi, [rsp+0F0h+var_28]
0x180066587  mov     rdi, rax
0x18006658a  test    rbx, rbx
0x18006658d  jz      short loc_180066598
0x18006658f  mov     rcx, rbx; Block
0x180066592  call    cs:__imp_free
0x180066598  mov     rbx, [rsp+0F0h+var_20]
0x1800665a0  mov     rax, rdi
0x1800665a3  mov     rdi, [rsp+0F0h+var_30]
0x1800665ab  mov     rcx, [rbp+57h+var_50]
0x1800665af  xor     rcx, rsp; StackCookie
0x1800665b2  call    __security_check_cookie
0x1800665b7  add     rsp, 0D8h
0x1800665be  pop     r15
0x1800665c0  pop     r14
0x1800665c2  pop     r12
0x1800665c4  pop     rbp
0x1800665c5  retn
```
