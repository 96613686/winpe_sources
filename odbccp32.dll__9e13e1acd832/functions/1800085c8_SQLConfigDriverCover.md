# SQLConfigDriverCover

- ea: `0x1800085c8`
- end: `0x180008bdc`
- name: `SQLConfigDriverCover`
- size: `1556`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned __int16, const WCHAR *, const WCHAR *, LPWSTR lpWideCharStr, unsigned __int16, __int16 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180006afc`
- `0x180008bf0`

## callees

- `0x180001010`
- `0x180002940`
- `0x180002e4c`
- `0x180004bac`
- `0x180004bdc`
- `0x180004db0`
- `0x1800080c4`
- `0x18000823c`
- `0x1800085c8`
- `0x18000a378`
- `0x180012a78`
- `0x180013a64`
- `0x180013fa8`
- `0x180014aae`
- `0x180014ae0`
- `0x180015010`

## import_xrefs

- `msvcrt!calloc` at `0x180008a86`
- `msvcrt!calloc` at `0x180008a86`
- `USER32!LoadCursorA` at `0x180008681`
- `USER32!LoadCursorA` at `0x180008681`
- `USER32!SetCursor` at `0x18000868a`
- `USER32!SetCursor` at `0x18000878c`
- `USER32!SetCursor` at `0x180008996`
- `USER32!SetCursor` at `0x180008ba3`
- `USER32!SetCursor` at `0x18000868a`
- `USER32!SetCursor` at `0x18000878c`
- `USER32!SetCursor` at `0x180008996`
- `USER32!SetCursor` at `0x180008ba3`
- `KERNEL32!SetThreadErrorMode` at `0x18000885b`
- `KERNEL32!SetThreadErrorMode` at `0x180008882`
- `KERNEL32!SetThreadErrorMode` at `0x18000885b`
- `KERNEL32!SetThreadErrorMode` at `0x180008882`
- `KERNEL32!MultiByteToWideChar` at `0x180008b25`
- `KERNEL32!MultiByteToWideChar` at `0x180008b25`
- `KERNEL32!FormatMessageW` at `0x1800088c7`
- `KERNEL32!FormatMessageW` at `0x1800088c7`
- `KERNEL32!LoadLibraryExW` at `0x18000886d`
- `KERNEL32!LoadLibraryExW` at `0x18000886d`
- `KERNEL32!GetLastError` at `0x180008898`
- `KERNEL32!GetLastError` at `0x180008898`
- `KERNEL32!FreeLibrary` at `0x180008b99`
- `KERNEL32!FreeLibrary` at `0x180008b99`
- `KERNEL32!GetProcAddress` at `0x1800089b9`
- `KERNEL32!GetProcAddress` at `0x1800089d4`
- `KERNEL32!GetProcAddress` at `0x1800089b9`
- `KERNEL32!GetProcAddress` at `0x1800089d4`

## string_xrefs

- `0x1800089cd`: `ConfigDriver`
- `0x1800089af`: `ConfigDriverW`

## pseudocode

```c
__int64 __fastcall SQLConfigDriverCover(
        HWND hWnd,
        unsigned __int16 a2,
        const WCHAR *a3,
        const WCHAR *a4,
        LPWSTR lpWideCharStr,
        unsigned __int16 a6,
        __int16 *a7)
{
  unsigned int v10; // edi
  int v11; // ecx
  HCURSOR CursorA; // rax
  WCHAR *v13; // rbx
  __int64 v14; // rcx
  __int16 v15; // ax
  HMODULE v16; // rdx
  unsigned int v17; // r9d
  BOOL v18; // ebx
  HMODULE Library; // rax
  CHAR *v20; // rbx
  DWORD LastError; // esi
  DWORD v22; // eax
  __int64 v23; // rcx
  FARPROC ProcAddress; // rax
  __int64 v25; // rcx
  __int16 *v26; // rax
  CHAR *v27; // r14
  unsigned int v28; // eax
  WCHAR v29; // r10
  unsigned int v30; // r10d
  int nSize; // [rsp+28h] [rbp-D8h]
  int nSizea; // [rsp+28h] [rbp-D8h]
  __int16 v34; // [rsp+50h] [rbp-B0h] BYREF
  HMODULE hModule; // [rsp+58h] [rbp-A8h] BYREF
  DWORD OldMode; // [rsp+60h] [rbp-A0h] BYREF
  const WCHAR *v37; // [rsp+68h] [rbp-98h]
  __int16 *v38; // [rsp+70h] [rbp-90h]
  CHAR *v39; // [rsp+78h] [rbp-88h] BYREF
  HCURSOR hCursor; // [rsp+80h] [rbp-80h]
  CHAR *v41; // [rsp+88h] [rbp-78h] BYREF
  FARPROC v42; // [rsp+90h] [rbp-70h]
  wchar_t pszFormat[264]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t pszDest[304]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR szErrorMsg[608]; // [rsp+510h] [rbp+410h] BYREF

  v38 = a7;
  OldMode = 0;
  v37 = a4;
  memset_0(pszFormat, 0, 0x208u);
  if ( lpWideCharStr && a6 )
    *lpWideCharStr = 0;
  v10 = 1;
  if ( (unsigned __int16)(a2 - 1) <= 2u || a2 >= 0x65u )
  {
    if ( !a3 || !*a3 )
    {
      v11 = 7;
      goto LABEL_73;
    }
    CursorA = LoadCursorA(0, (LPCSTR)0x7F02);
    hCursor = SetCursor(CursorA);
    if ( a7 )
      *a7 = 0;
    LODWORD(v13) = 0;
    if ( !(unsigned int)cpGetPrivateProfileString(
                          HKEY_LOCAL_MACHINE,
                          a3,
                          L"Setup",
                          (void *)&SubKey,
                          2u,
                          0,
                          pszFormat,
                          520,
                          (__int64)L"ODBCINST.INI",
                          0)
      && !(unsigned int)cpGetPrivateProfileString(
                          HKEY_LOCAL_MACHINE,
                          a3,
                          L"Driver",
                          (void *)&SubKey,
                          2u,
                          0,
                          pszFormat,
                          520,
                          (__int64)L"ODBCINST.INI",
                          0) )
    {
      if ( hWnd )
      {
        SetString(pszFormat, 260, 0x52Bu);
        StringCchPrintfW(pszDest, 0x12Du, pszFormat, a3);
        DoMessage(hWnd, pszDest, 0x10u);
      }
      SetCursor(hCursor);
      v11 = 6;
      goto LABEL_73;
    }
    if ( a2 == 3 )
    {
      hModule = 0;
      if ( (DupeStringAlloc(v14, &hModule, v37) & 0xFFFE) != 0 || (v13 = (WCHAR *)hModule) == 0 )
      {
        v10 = (unsigned int)v13;
      }
      else
      {
        v15 = *(_WORD *)hModule;
        v16 = hModule;
        while ( v15 && v15 != 61 )
        {
          v16 = (HMODULE)((char *)v16 + 2);
          v15 = *(_WORD *)v16;
        }
        if ( *(_WORD *)v16 == 61 )
        {
          *(_WORD *)v16 = 0;
          v10 = cpWritePrivateProfileString(
                  HKEY_LOCAL_MACHINE,
                  (__int64)a3,
                  v13,
                  1u,
                  (BYTE *)(((unsigned __int64)v16 + 2) & -(__int64)(*((_WORD *)v16 + 1) != 0)),
                  (__int64)L"ODBCINST.INI");
        }
        else
        {
          PostInstError(8);
          v10 = v17;
        }
        OFree(v13);
      }
      goto LABEL_71;
    }
    v18 = SetThreadErrorMode(0x8001u, &OldMode);
    Library = LoadLibraryExW(pszFormat, 0, 8u);
    hModule = Library;
    if ( v18 )
    {
      SetThreadErrorMode(OldMode, 0);
      Library = hModule;
    }
    v20 = 0;
    if ( !Library )
    {
      LastError = GetLastError();
      v22 = FormatMessageW(0x1000u, 0, LastError, 0, pszDest, 0x104u, 0);
      v23 = v22;
      if ( v22 )
      {
        if ( v22 < 0x104uLL )
        {
          if ( v22 >= 2uLL && pszDest[v22 - 2] == 13 && pszFormat[v22 + 263] == 10 )
            v23 = v22 - 2LL;
          StringCchPrintfW(&pszDest[v23], 260 - v23, L" (%s)", pszFormat);
        }
      }
      else
      {
        pszDest[0] = 0;
      }
      SetString(pszFormat, 260, 0x52Cu);
      if ( !pszFormat[0] || !(unsigned int)FormatMessageVWrapper(szErrorMsg, 0x25Au, pszFormat) )
        szErrorMsg[0] = 0;
      if ( hWnd )
        DoMessage(hWnd, szErrorMsg, 0x10u);
      SetCursor(hCursor);
      SQLPostInstallerErrorW(0xDu, szErrorMsg);
      return 0;
    }
    ProcAddress = GetProcAddress(Library, "ConfigDriverW");
    if ( ProcAddress )
    {
      LOWORD(nSize) = a6;
      v10 = ((__int64 (__fastcall *)(HWND, _QWORD, const WCHAR *, const WCHAR *, LPWSTR, int, __int16 *))ProcAddress)(
              hWnd,
              a2,
              a3,
              v37,
              lpWideCharStr,
              nSize,
              v38);
      if ( !v10 )
        PostInstErrorMsgId(11, 1415);
      goto LABEL_70;
    }
    v42 = GetProcAddress(hModule, "ConfigDriver");
    if ( !v42 )
    {
      if ( a2 > 0x64u )
      {
        PostInstErrorMsgId(13, 1325);
        v10 = 0;
      }
      goto LABEL_70;
    }
    v25 = (__int64)v38;
    v26 = &v34;
    v34 = 0;
    v41 = 0;
    if ( v38 )
      v26 = v38;
    v39 = 0;
    v38 = v26;
    LConvertToAnsi(v25, a3, -3, &v39, -3, 0, 14);
    LConvertToAnsi(0, v37, -3, &v41, -3, 0, 14);
    if ( lpWideCharStr && a6 )
      v20 = (CHAR *)calloc(a6, 1u);
    v27 = v41;
    if ( v39 && (v41 || !v37) && (v20 || !lpWideCharStr) )
    {
      LOWORD(nSizea) = a6;
      v28 = ((__int64 (__fastcall *)(HWND, _QWORD, CHAR *, CHAR *, CHAR *, int, __int16 *))v42)(
              hWnd,
              a2,
              v39,
              v41,
              v20,
              nSizea,
              v38);
      v29 = 0;
      v10 = v28;
      if ( !v28 )
      {
        PostInstErrorMsgId(11, 1415);
        goto LABEL_61;
      }
      if ( !v20 || !*v20 )
      {
LABEL_61:
        if ( lpWideCharStr )
          *lpWideCharStr = v29;
        goto LABEL_67;
      }
      MultiByteToWideChar(0, 0, v20, -1, lpWideCharStr, a6);
    }
    else
    {
      PostInstErrorMsgId(1, 1414);
      v10 = v30;
    }
LABEL_67:
    OFree(v39);
    OFree(v27);
    OFree(v20);
LABEL_70:
    FreeLibrary(hModule);
LABEL_71:
    SetCursor(hCursor);
    return v10;
  }
  v11 = 5;
LABEL_73:
  PostInstError(v11);
  return 0;
}

```

## disassembly

```asm
0x1800085c8  push    rbp
0x1800085ca  push    rbx
0x1800085cb  push    rsi
0x1800085cc  push    rdi
0x1800085cd  push    r12
0x1800085cf  push    r13
0x1800085d1  push    r14
0x1800085d3  push    r15
0x1800085d5  lea     rbp, [rsp-8E8h]
0x1800085dd  sub     rsp, 9E8h
0x1800085e4  mov     rax, cs:__security_cookie
0x1800085eb  xor     rax, rsp
0x1800085ee  mov     [rbp+920h+var_50], rax
0x1800085f5  mov     rbx, [rbp+920h+arg_30]
0x1800085fc  mov     r14, r8
0x1800085ff  mov     rsi, [rbp+920h+lpWideCharStr]
0x180008606  movzx   r15d, dx
0x18000860a  movzx   r13d, [rbp+920h+arg_28]
0x180008612  mov     r12, rcx
0x180008615  xor     edi, edi
0x180008617  mov     [rsp+0A20h+var_9B0], rbx
0x18000861c  xor     edx, edx; Val
0x18000861e  mov     [rsp+0A20h+OldMode], edi
0x180008622  mov     r8d, 208h; Size
0x180008628  mov     [rsp+0A20h+var_9B8], r9
0x18000862d  lea     rcx, [rbp+920h+pszFormat]; void *
0x180008631  call    memset_0
0x180008636  test    rsi, rsi
0x180008639  jz      short loc_180008644
0x18000863b  test    r13w, r13w
0x18000863f  jz      short loc_180008644
0x180008641  mov     [rsi], di
0x180008644  mov     edi, 1
0x180008649  movzx   eax, r15w
0x18000864d  sub     ax, di
0x180008650  lea     ecx, [rdi+1]
0x180008653  cmp     ax, cx
0x180008656  jbe     short loc_180008667
0x180008658  cmp     r15w, 65h ; 'e'
0x18000865d  jnb     short loc_180008667
0x18000865f  lea     ecx, [rdi+4]
0x180008662  jmp     loc_180008BB2
0x180008667  xor     ecx, ecx; hInstance
0x180008669  test    r14, r14
0x18000866c  jz      loc_180008BAD
0x180008672  cmp     [r14], cx
0x180008676  jz      loc_180008BAD
0x18000867c  mov     edx, 7F02h; lpCursorName
0x180008681  call    cs:__imp_LoadCursorA
0x180008687  mov     rcx, rax; hCursor
0x18000868a  call    cs:__imp_SetCursor
0x180008690  mov     [rbp+920h+hCursor], rax
0x180008694  xor     eax, eax
0x180008696  test    rbx, rbx
0x180008699  jz      short loc_18000869E
0x18000869b  mov     [rbx], ax
0x18000869e  xor     ebx, ebx
0x1800086a0  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x1800086a7  mov     [rsp+0A20h+var_9D8], rbx
0x1800086ac  lea     r9, SubKey
0x1800086b3  mov     [rsp+0A20h+var_9E0], rax
0x1800086b8  lea     r8, aSetup; "Setup"
0x1800086bf  mov     [rsp+0A20h+var_9E8], 208h
0x1800086c7  lea     rax, [rbp+920h+pszFormat]
0x1800086cb  mov     [rsp+0A20h+Arguments], rax
0x1800086d0  mov     rdx, r14
0x1800086d3  mov     qword ptr [rsp+0A20h+nSize], rbx
0x1800086d8  mov     rcx, 0FFFFFFFF80000002h
0x1800086df  mov     dword ptr [rsp+0A20h+lpBuffer], 2
0x1800086e7  call    cpGetPrivateProfileString
0x1800086ec  test    eax, eax
0x1800086ee  jnz     loc_18000879C
0x1800086f4  mov     [rsp+0A20h+var_9D8], rbx
0x1800086f9  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x180008700  mov     [rsp+0A20h+var_9E0], rax
0x180008705  lea     r9, SubKey
0x18000870c  mov     [rsp+0A20h+var_9E8], 208h
0x180008714  lea     rax, [rbp+920h+pszFormat]
0x180008718  mov     [rsp+0A20h+Arguments], rax
0x18000871d  lea     r8, aDriver_0; "Driver"
0x180008724  mov     qword ptr [rsp+0A20h+nSize], rbx
0x180008729  mov     rdx, r14
0x18000872c  mov     rcx, 0FFFFFFFF80000002h
0x180008733  mov     dword ptr [rsp+0A20h+lpBuffer], 2
0x18000873b  call    cpGetPrivateProfileString
0x180008740  test    eax, eax
0x180008742  jnz     short loc_18000879C
0x180008744  test    r12, r12
0x180008747  jz      short loc_180008788
0x180008749  mov     edx, 104h; cchBufferMax
0x18000874e  lea     rcx, [rbp+920h+pszFormat]; lpBuffer
0x180008752  mov     r8d, 52Bh
0x180008758  call    SetString
0x18000875d  mov     r9, r14
0x180008760  lea     r8, [rbp+920h+pszFormat]; pszFormat
0x180008764  mov     edx, 12Dh; cchDest
0x180008769  lea     rcx, [rbp+920h+pszDest]; pszDest
0x180008770  call    StringCchPrintfW
0x180008775  lea     r8d, [rbx+10h]; uType
0x180008779  mov     rcx, r12; hWnd
0x18000877c  lea     rdx, [rbp+920h+pszDest]; lpText
0x180008783  call    DoMessage
0x180008788  mov     rcx, [rbp+920h+hCursor]; hCursor
0x18000878c  call    cs:__imp_SetCursor
0x180008792  mov     ecx, 6
0x180008797  jmp     loc_180008BB2
0x18000879c  cmp     r15w, 3
0x1800087a1  jnz     loc_180008851
0x1800087a7  mov     r8, [rsp+0A20h+var_9B8]
0x1800087ac  lea     rdx, [rsp+0A20h+hModule]
0x1800087b1  mov     [rsp+0A20h+hModule], rbx
0x1800087b6  call    DupeStringAlloc
0x1800087bb  test    ax, 0FFFEh
0x1800087bf  jnz     loc_18000884A
0x1800087c5  mov     rbx, [rsp+0A20h+hModule]
0x1800087ca  xor     r9d, r9d
0x1800087cd  test    rbx, rbx
0x1800087d0  jz      short loc_18000884A
0x1800087d2  movzx   eax, word ptr [rbx]
0x1800087d5  mov     rdx, rbx
0x1800087d8  jmp     short loc_1800087E7
0x1800087da  cmp     ax, 3Dh ; '='
0x1800087de  jz      short loc_1800087EC
0x1800087e0  add     rdx, 2
0x1800087e4  movzx   eax, word ptr [rdx]
0x1800087e7  test    ax, ax
0x1800087ea  jnz     short loc_1800087DA
0x1800087ec  cmp     word ptr [rdx], 3Dh ; '='
0x1800087f0  jnz     short loc_180008830
0x1800087f2  mov     [rdx], r9w
0x1800087f6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800087fd  add     rdx, 2
0x180008801  mov     r9d, edi
0x180008804  movzx   eax, word ptr [rdx]
0x180008807  neg     ax
0x18000880a  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x180008811  sbb     r8, r8
0x180008814  mov     qword ptr [rsp+0A20h+nSize], rax; __int64
0x180008819  and     r8, rdx
0x18000881c  mov     rdx, r14
0x18000881f  mov     [rsp+0A20h+lpBuffer], r8; lpData
0x180008824  mov     r8, rbx
0x180008827  call    cpWritePrivateProfileString
0x18000882c  mov     edi, eax
0x18000882e  jmp     short loc_18000883D
0x180008830  mov     ecx, 8
0x180008835  call    PostInstError
0x18000883a  mov     edi, r9d
0x18000883d  mov     rcx, rbx
0x180008840  call    OFree
0x180008845  jmp     loc_180008B9F
0x18000884a  mov     edi, ebx
0x18000884c  jmp     loc_180008B9F
0x180008851  lea     rdx, [rsp+0A20h+OldMode]; lpOldMode
0x180008856  mov     ecx, 8001h; dwNewMode
0x18000885b  call    cs:__imp_SetThreadErrorMode
0x180008861  xor     edx, edx; hFile
0x180008863  lea     rcx, [rbp+920h+pszFormat]; lpLibFileName
0x180008867  mov     ebx, eax
0x180008869  lea     r8d, [rdx+8]; dwFlags
0x18000886d  call    cs:__imp_LoadLibraryExW
0x180008873  mov     [rsp+0A20h+hModule], rax
0x180008878  test    ebx, ebx
0x18000887a  jz      short loc_18000888D
0x18000887c  mov     ecx, [rsp+0A20h+OldMode]; dwNewMode
0x180008880  xor     edx, edx; lpOldMode
0x180008882  call    cs:__imp_SetThreadErrorMode
0x180008888  mov     rax, [rsp+0A20h+hModule]
0x18000888d  xor     ebx, ebx
0x18000888f  test    rax, rax
0x180008892  jnz     loc_1800089AF
0x180008898  call    cs:__imp_GetLastError
0x18000889e  mov     [rsp+0A20h+Arguments], rbx; Arguments
0x1800088a3  xor     r9d, r9d; dwLanguageId
0x1800088a6  mov     esi, eax
0x1800088a8  mov     ebx, 104h
0x1800088ad  lea     rax, [rbp+920h+pszDest]
0x1800088b4  mov     [rsp+0A20h+nSize], ebx; nSize
0x1800088b8  mov     r8d, esi; dwMessageId
0x1800088bb  mov     [rsp+0A20h+lpBuffer], rax; lpBuffer
0x1800088c0  xor     edx, edx; lpSource
0x1800088c2  mov     ecx, 1000h; dwFlags
0x1800088c7  call    cs:__imp_FormatMessageW
0x1800088cd  xor     r15d, r15d
0x1800088d0  mov     ecx, eax
0x1800088d2  mov     edi, 0Dh
0x1800088d7  test    eax, eax
0x1800088d9  jz      short loc_180008924
0x1800088db  cmp     rcx, rbx
0x1800088de  jnb     short loc_18000892C
0x1800088e0  cmp     rcx, 2
0x1800088e4  jb      short loc_180008901
0x1800088e6  lea     rax, [rcx-2]
0x1800088ea  cmp     [rbp+rax*2+920h+pszDest], di
0x1800088f2  jnz     short loc_180008901
0x1800088f4  cmp     [rbp+rcx*2+920h+var_772], 0Ah
0x1800088fd  cmovz   rcx, rax
0x180008901  lea     rax, [rbp+920h+pszDest]
0x180008908  mov     rdx, rbx
0x18000890b  sub     rdx, rcx; cchDest
0x18000890e  lea     r9, [rbp+920h+pszFormat]
0x180008912  lea     rcx, [rax+rcx*2]; pszDest
0x180008916  lea     r8, aS; " (%s)"
0x18000891d  call    StringCchPrintfW
0x180008922  jmp     short loc_18000892C
0x180008924  mov     [rbp+920h+pszDest], r15w
0x18000892c  mov     r8d, 52Ch
0x180008932  lea     rcx, [rbp+920h+pszFormat]; lpBuffer
0x180008936  mov     edx, ebx; cchBufferMax
0x180008938  call    SetString
0x18000893d  cmp     [rbp+920h+pszFormat], r15w
0x180008942  jz      short loc_180008970
0x180008944  lea     rax, [rbp+920h+pszDest]
0x18000894b  mov     r9, r14
0x18000894e  mov     qword ptr [rsp+0A20h+nSize], rax
0x180008953  lea     r8, [rbp+920h+pszFormat]; lpSource
0x180008957  mov     edx, 25Ah; nSize
0x18000895c  mov     dword ptr [rsp+0A20h+lpBuffer], esi
0x180008960  lea     rcx, [rbp+920h+szErrorMsg]; lpBuffer
0x180008967  call    FormatMessageVWrapper
0x18000896c  test    eax, eax
0x18000896e  jnz     short loc_180008978
0x180008970  mov     [rbp+920h+szErrorMsg], r15w
0x180008978  test    r12, r12
0x18000897b  jz      short loc_180008992
0x18000897d  mov     r8d, 10h; uType
0x180008983  lea     rdx, [rbp+920h+szErrorMsg]; lpText
0x18000898a  mov     rcx, r12; hWnd
0x18000898d  call    DoMessage
0x180008992  mov     rcx, [rbp+920h+hCursor]; hCursor
0x180008996  call    cs:__imp_SetCursor
0x18000899c  lea     rdx, [rbp+920h+szErrorMsg]; lpszErrorMsg
0x1800089a3  mov     ecx, edi; dwErrorCode
0x1800089a5  call    SQLPostInstallerErrorW
0x1800089aa  jmp     loc_180008BB7
0x1800089af  lea     rdx, aConfigdriverw; "ConfigDriverW"
0x1800089b6  mov     rcx, rax; hModule
0x1800089b9  call    cs:__imp_GetProcAddress
0x1800089bf  test    rax, rax
0x1800089c2  jnz     loc_180008B58
0x1800089c8  mov     rcx, [rsp+0A20h+hModule]; hModule
0x1800089cd  lea     rdx, aConfigdriver; "ConfigDriver"
0x1800089d4  call    cs:__imp_GetProcAddress
0x1800089da  mov     [rbp+920h+var_990], rax
0x1800089de  test    rax, rax
0x1800089e1  jnz     short loc_180008A02
0x1800089e3  cmp     r15w, 64h ; 'd'
0x1800089e8  jbe     loc_180008B94
0x1800089ee  mov     edx, 52Dh
0x1800089f3  lea     ecx, [rax+0Dh]
0x1800089f6  call    PostInstErrorMsgId
0x1800089fb  mov     edi, ebx
0x1800089fd  jmp     loc_180008B94
0x180008a02  mov     rcx, [rsp+0A20h+var_9B0]
0x180008a07  lea     rax, [rsp+0A20h+var_9D0]
0x180008a0c  xor     edx, edx
0x180008a0e  mov     dword ptr [rsp+0A20h+Arguments], 0Eh
0x180008a16  mov     qword ptr [rsp+0A20h+nSize], rdx
0x180008a1b  lea     r9, [rsp+0A20h+var_9A8]
0x180008a20  test    rcx, rcx
0x180008a23  mov     [rsp+0A20h+var_9D0], dx
0x180008a28  mov     [rbp+920h+var_998], rbx
0x180008a2c  cmovnz  rax, rcx
0x180008a30  mov     [rsp+0A20h+var_9A8], rbx
0x180008a35  mov     [rsp+0A20h+var_9B0], rax
0x180008a3a  lea     eax, [rdx-3]
0x180008a3d  mov     r8d, eax
0x180008a40  mov     dword ptr [rsp+0A20h+lpBuffer], eax
0x180008a44  mov     rdx, r14
0x180008a47  call    LConvertToAnsi
0x180008a4c  mov     rdx, [rsp+0A20h+var_9B8]
0x180008a51  lea     r9, [rbp+920h+var_998]
0x180008a55  xor     ecx, ecx
0x180008a57  mov     dword ptr [rsp+0A20h+Arguments], 0Eh
0x180008a5f  mov     qword ptr [rsp+0A20h+nSize], rcx
0x180008a64  lea     r8d, [rcx-3]
0x180008a68  mov     dword ptr [rsp+0A20h+lpBuffer], r8d
0x180008a6d  call    LConvertToAnsi
0x180008a72  xor     r10d, r10d
0x180008a75  test    rsi, rsi
0x180008a78  jz      short loc_180008A92
0x180008a7a  test    r13w, r13w
0x180008a7e  jz      short loc_180008A92
0x180008a80  mov     rcx, r13; Count
0x180008a83  mov     rdx, rdi; Size
0x180008a86  call    cs:__imp_calloc
0x180008a8c  mov     rbx, rax
0x180008a8f  xor     r10d, r10d
0x180008a92  mov     rax, [rsp+0A20h+var_9A8]
0x180008a97  mov     r14, [rbp+920h+var_998]
0x180008a9b  test    rax, rax
0x180008a9e  jz      loc_180008B2D
0x180008aa4  test    r14, r14
0x180008aa7  jnz     short loc_180008AB0
0x180008aa9  cmp     [rsp+0A20h+var_9B8], r10
0x180008aae  jnz     short loc_180008B2D
0x180008ab0  test    rbx, rbx
0x180008ab3  jnz     short loc_180008ABA
0x180008ab5  test    rsi, rsi
0x180008ab8  jnz     short loc_180008B2D
  ... truncated ...
```
