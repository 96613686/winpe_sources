# ConfigDataSourceW

- ea: `0x180007c0c`
- end: `0x1800080be`
- name: `ConfigDataSourceW`
- size: `1202`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned __int16, const wchar_t *, __int64)`
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000295c`
- `0x180006db8`
- `0x1800084c0`
- `0x1800099a0`

## callees

- `0x180001010`
- `0x180002940`
- `0x180002e14`
- `0x180002e4c`
- `0x180004bac`
- `0x180004bdc`
- `0x180004db0`
- `0x180007c0c`
- `0x1800080c4`
- `0x18000823c`
- `0x18000a378`
- `0x180013a64`
- `0x180014364`
- `0x180014aae`
- `0x180014ae0`
- `0x180015010`

## import_xrefs

- `USER32!LoadCursorA` at `0x180007cad`
- `USER32!LoadCursorA` at `0x180007cad`
- `USER32!SetCursor` at `0x180007cb6`
- `USER32!SetCursor` at `0x180007d65`
- `USER32!SetCursor` at `0x180007ecd`
- `USER32!SetCursor` at `0x18000807e`
- `USER32!SetCursor` at `0x180007cb6`
- `USER32!SetCursor` at `0x180007d65`
- `USER32!SetCursor` at `0x180007ecd`
- `USER32!SetCursor` at `0x18000807e`
- `KERNEL32!SetThreadErrorMode` at `0x180007d8c`
- `KERNEL32!SetThreadErrorMode` at `0x180007db4`
- `KERNEL32!SetThreadErrorMode` at `0x180007d8c`
- `KERNEL32!SetThreadErrorMode` at `0x180007db4`
- `KERNEL32!FormatMessageW` at `0x180007df4`
- `KERNEL32!FormatMessageW` at `0x180007df4`
- `KERNEL32!LoadLibraryExW` at `0x180007da1`
- `KERNEL32!LoadLibraryExW` at `0x180007da1`
- `KERNEL32!GetLastError` at `0x180007dc3`
- `KERNEL32!GetLastError` at `0x180007dc3`
- `KERNEL32!FreeLibrary` at `0x180008075`
- `KERNEL32!FreeLibrary` at `0x180008075`
- `KERNEL32!GetProcAddress` at `0x180007ef0`
- `KERNEL32!GetProcAddress` at `0x180007f09`
- `KERNEL32!GetProcAddress` at `0x180007ef0`
- `KERNEL32!GetProcAddress` at `0x180007f09`

## string_xrefs

- `0x180007eff`: `ConfigDSN`
- `0x180007ee6`: `ConfigDSNW`

## pseudocode

```c
__int64 __fastcall ConfigDataSourceW(HWND hWnd, unsigned __int16 a2, const wchar_t *a3, __int64 a4)
{
  unsigned int v4; // esi
  unsigned __int64 v8; // rax
  HCURSOR CursorA; // rax
  HCURSOR v10; // r12
  BOOL v11; // ebx
  HMODULE Library; // r15
  DWORD LastError; // esi
  DWORD v14; // eax
  DWORD v15; // edx
  FARPROC ProcAddress; // rax
  __int64 v17; // rcx
  FARPROC v18; // rbx
  __int16 v19; // ax
  __int64 v20; // rcx
  __int64 v21; // r14
  __int64 v22; // rsi
  unsigned int v23; // ebx
  __int64 v25; // rcx
  DWORD OldMode; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszFormat[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t v32[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR LibFileName[264]; // [rsp+6A0h] [rbp+5A0h] BYREF
  wchar_t pszDest[520]; // [rsp+8B0h] [rbp+7B0h] BYREF

  v4 = a2;
  OldMode = 0;
  memset_0(LibFileName, 0, 0x208u);
  if ( (unsigned __int16)(v4 - 1) > 2u )
  {
    v25 = 5;
    goto LABEL_48;
  }
  if ( !a3 )
    goto LABEL_46;
  if ( !*a3 )
    goto LABEL_46;
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  if ( v8 >= 0x104 )
  {
LABEL_46:
    v25 = 7;
LABEL_48:
    PostInstError(v25);
    return 0;
  }
  CursorA = LoadCursorA(0, (LPCSTR)0x7F02);
  v10 = SetCursor(CursorA);
  if ( !(unsigned int)cpGetPrivateProfileString(
                        -2147483646,
                        a3,
                        L"Setup",
                        &SubKey,
                        2,
                        0,
                        LibFileName,
                        520,
                        L"ODBCINST.INI",
                        0) )
  {
    if ( hWnd )
    {
      SetString(pszFormat, 260);
      StringCchPrintfW(pszDest, 0x208u, pszFormat, a3);
      DoMessage(hWnd, pszDest, 0x10u);
    }
    PostInstError(6);
    SetCursor(v10);
    return 0;
  }
  StringCchCopyW(v32, 0x104u, a3);
  v11 = SetThreadErrorMode(0x8001u, &OldMode);
  Library = LoadLibraryExW(LibFileName, 0, 8u);
  if ( v11 )
    SetThreadErrorMode(OldMode, 0);
  if ( !Library )
  {
    LastError = GetLastError();
    v14 = FormatMessageW(0x1000u, 0, LastError, 0, Buffer, 0x104u, 0);
    v15 = v14;
    if ( v14 )
    {
      if ( v14 < 0x104 )
      {
        if ( v14 >= 2 && Buffer[v14 - 2] == 13 && Buffer[v14 - 1] == 10 )
          v15 = v14 - 2;
        StringCchPrintfW(&Buffer[v15], 260LL - v15, L" (%s)", LibFileName);
      }
    }
    else
    {
      Buffer[0] = 0;
    }
    SetString(pszFormat, 260);
    if ( !pszFormat[0] || !(unsigned int)FormatMessageVWrapper(pszDest, 0x208u, pszFormat) )
      pszDest[0] = 0;
    if ( hWnd )
      DoMessage(hWnd, pszDest, 0x10u);
    SetCursor(v10);
    SQLPostInstallerErrorW(0xDu, pszDest);
    return 0;
  }
  ProcAddress = GetProcAddress(Library, "ConfigDSNW");
  if ( ProcAddress )
  {
    v23 = ((__int64 (__fastcall *)(HWND, _QWORD, wchar_t *, __int64))ProcAddress)(hWnd, v4, v32, a4);
    if ( !v23 )
      PostInstErrorMsgId(11, 1415);
  }
  else
  {
    v18 = GetProcAddress(Library, "ConfigDSN");
    if ( v18 )
    {
      v29 = 0;
      v28 = 0;
      LConvertToAnsi(v17, v32, 4294967293LL, &v29, -3, 0, 14);
      v19 = wdnlen(a4);
      LConvertToAnsi(v20, a4, (unsigned int)v19, &v28, 0, 0, 14);
      v21 = v29;
      v22 = v28;
      if ( v29 && (v28 || !a4) )
      {
        v23 = ((__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))v18)(hWnd, a2, v29, v28);
        if ( !v23 )
          PostInstErrorMsgId(11, 1415);
      }
      else
      {
        PostInstErrorMsgId(1, 1414);
        v23 = 0;
      }
      if ( v21 )
        OFree(v21);
      if ( v22 )
        OFree(v22);
    }
    else
    {
      if ( hWnd )
      {
        SetString(pszFormat, 260);
        StringCchPrintfW(pszDest, 0x208u, pszFormat, v32);
        DoMessage(hWnd, pszDest, 0x10u);
      }
      PostInstErrorMsgId(13, 1325);
      v23 = 0;
    }
  }
  FreeLibrary(Library);
  SetCursor(v10);
  return v23;
}

```

## disassembly

```asm
0x180007c0c  push    rbp
0x180007c0e  push    rbx
0x180007c0f  push    rsi
0x180007c10  push    rdi
0x180007c11  push    r12
0x180007c13  push    r13
0x180007c15  push    r14
0x180007c17  push    r15
0x180007c19  lea     rbp, [rsp-0BD8h]
0x180007c21  sub     rsp, 0CD8h
0x180007c28  mov     rax, cs:__security_cookie
0x180007c2f  xor     rax, rsp
0x180007c32  mov     [rbp+0C10h+var_50], rax
0x180007c39  movzx   esi, dx
0x180007c3c  mov     rbx, r8
0x180007c3f  mov     rdi, rcx
0x180007c42  mov     [rsp+0D10h+var_CC0], si
0x180007c47  xor     r14d, r14d
0x180007c4a  lea     rcx, [rbp+0C10h+LibFileName]; void *
0x180007c51  xor     edx, edx; Val
0x180007c53  mov     [rsp+0D10h+OldMode], r14d
0x180007c58  mov     r8d, 208h; Size
0x180007c5e  mov     r13, r9
0x180007c61  call    memset_0
0x180007c66  lea     eax, [rsi-1]
0x180007c69  lea     ecx, [r14+2]
0x180007c6d  cmp     ax, cx
0x180007c70  ja      loc_18000808F
0x180007c76  test    rbx, rbx
0x180007c79  jz      loc_180008088
0x180007c7f  cmp     [rbx], r14w
0x180007c83  jz      loc_180008088
0x180007c89  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007c8d  inc     rax
0x180007c90  cmp     [rbx+rax*2], r14w
0x180007c95  jnz     short loc_180007C8D
0x180007c97  mov     r15d, 104h
0x180007c9d  cmp     rax, r15
0x180007ca0  jnb     loc_180008088
0x180007ca6  mov     edx, 7F02h; lpCursorName
0x180007cab  xor     ecx, ecx; hInstance
0x180007cad  call    cs:__imp_LoadCursorA
0x180007cb3  mov     rcx, rax; hCursor
0x180007cb6  call    cs:__imp_SetCursor
0x180007cbc  mov     [rsp+0D10h+var_CC8], r14
0x180007cc1  lea     r9, SubKey
0x180007cc8  mov     r12, rax
0x180007ccb  lea     r8, aSetup; "Setup"
0x180007cd2  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x180007cd9  mov     rdx, rbx
0x180007cdc  mov     [rsp+0D10h+var_CD0], rax
0x180007ce1  mov     rcx, 0FFFFFFFF80000002h
0x180007ce8  mov     [rsp+0D10h+var_CD8], 208h
0x180007cf0  lea     rax, [rbp+0C10h+LibFileName]
0x180007cf7  mov     [rsp+0D10h+Arguments], rax
0x180007cfc  mov     qword ptr [rsp+0D10h+nSize], r14
0x180007d01  mov     dword ptr [rsp+0D10h+lpBuffer], 2
0x180007d09  call    cpGetPrivateProfileString
0x180007d0e  test    eax, eax
0x180007d10  jnz     short loc_180007D70
0x180007d12  test    rdi, rdi
0x180007d15  jz      short loc_180007D58
0x180007d17  mov     r8d, 52Bh
0x180007d1d  lea     rcx, [rsp+0D10h+pszFormat]; lpBuffer
0x180007d22  mov     edx, r15d; cchBufferMax
0x180007d25  call    SetString
0x180007d2a  mov     r9, rbx
0x180007d2d  lea     r8, [rsp+0D10h+pszFormat]; pszFormat
0x180007d32  mov     edx, 208h; cchDest
0x180007d37  lea     rcx, [rbp+0C10h+pszDest]; pszDest
0x180007d3e  call    StringCchPrintfW
0x180007d43  mov     r8d, 10h; uType
0x180007d49  lea     rdx, [rbp+0C10h+pszDest]; lpText
0x180007d50  mov     rcx, rdi; hWnd
0x180007d53  call    DoMessage
0x180007d58  mov     ecx, 6
0x180007d5d  call    PostInstError
0x180007d62  mov     rcx, r12; hCursor
0x180007d65  call    cs:__imp_SetCursor
0x180007d6b  jmp     loc_180008099
0x180007d70  mov     r8, rbx; pszSrc
0x180007d73  lea     rcx, [rbp+0C10h+var_880]; pszDest
0x180007d7a  mov     rdx, r15; cchDest
0x180007d7d  call    StringCchCopyW
0x180007d82  lea     rdx, [rsp+0D10h+OldMode]; lpOldMode
0x180007d87  mov     ecx, 8001h; dwNewMode
0x180007d8c  call    cs:__imp_SetThreadErrorMode
0x180007d92  xor     edx, edx; hFile
0x180007d94  lea     rcx, [rbp+0C10h+LibFileName]; lpLibFileName
0x180007d9b  mov     ebx, eax
0x180007d9d  lea     r8d, [rdx+8]; dwFlags
0x180007da1  call    cs:__imp_LoadLibraryExW
0x180007da7  mov     r15, rax
0x180007daa  test    ebx, ebx
0x180007dac  jz      short loc_180007DBA
0x180007dae  mov     ecx, [rsp+0D10h+OldMode]; dwNewMode
0x180007db2  xor     edx, edx; lpOldMode
0x180007db4  call    cs:__imp_SetThreadErrorMode
0x180007dba  test    r15, r15
0x180007dbd  jnz     loc_180007EE6
0x180007dc3  call    cs:__imp_GetLastError
0x180007dc9  mov     [rsp+0D10h+Arguments], r14; Arguments
0x180007dce  mov     r13d, 104h
0x180007dd4  mov     esi, eax
0x180007dd6  mov     [rsp+0D10h+nSize], r13d; nSize
0x180007ddb  lea     rax, [rbp+0C10h+Buffer]
0x180007de2  mov     r8d, esi; dwMessageId
0x180007de5  xor     r9d, r9d; dwLanguageId
0x180007de8  mov     [rsp+0D10h+lpBuffer], rax; lpBuffer
0x180007ded  xor     edx, edx; lpSource
0x180007def  mov     ecx, 1000h; dwFlags
0x180007df4  call    cs:__imp_FormatMessageW
0x180007dfa  lea     ebx, [r15+0Dh]
0x180007dfe  mov     edx, eax
0x180007e00  test    eax, eax
0x180007e02  jz      short loc_180007E54
0x180007e04  cmp     eax, r13d
0x180007e07  jnb     short loc_180007E5C
0x180007e09  cmp     eax, 2
0x180007e0c  jb      short loc_180007E2C
0x180007e0e  lea     r8d, [rax-2]
0x180007e12  cmp     [rbp+r8*2+0C10h+Buffer], bx
0x180007e1b  jnz     short loc_180007E2C
0x180007e1d  dec     eax
0x180007e1f  cmp     [rbp+rax*2+0C10h+Buffer], 0Ah
0x180007e28  cmovz   edx, r8d
0x180007e2c  mov     eax, edx
0x180007e2e  lea     rcx, [rbp+0C10h+Buffer]
0x180007e35  mov     rdx, r13
0x180007e38  lea     r9, [rbp+0C10h+LibFileName]
0x180007e3f  sub     rdx, rax; cchDest
0x180007e42  lea     r8, aS; " (%s)"
0x180007e49  lea     rcx, [rcx+rax*2]; pszDest
0x180007e4d  call    StringCchPrintfW
0x180007e52  jmp     short loc_180007E5C
0x180007e54  mov     [rbp+0C10h+Buffer], r14w
0x180007e5c  mov     r8d, 52Ch
0x180007e62  lea     rcx, [rsp+0D10h+pszFormat]; lpBuffer
0x180007e67  mov     edx, r13d; cchBufferMax
0x180007e6a  call    SetString
0x180007e6f  cmp     [rsp+0D10h+pszFormat], r14w
0x180007e75  jz      short loc_180007EA8
0x180007e77  lea     rax, [rbp+0C10h+Buffer]
0x180007e7e  mov     edx, 208h; nSize
0x180007e83  mov     qword ptr [rsp+0D10h+nSize], rax
0x180007e88  lea     r9, [rbp+0C10h+var_880]
0x180007e8f  lea     r8, [rsp+0D10h+pszFormat]; lpSource
0x180007e94  mov     dword ptr [rsp+0D10h+lpBuffer], esi
0x180007e98  lea     rcx, [rbp+0C10h+pszDest]; lpBuffer
0x180007e9f  call    FormatMessageVWrapper
0x180007ea4  test    eax, eax
0x180007ea6  jnz     short loc_180007EB0
0x180007ea8  mov     [rbp+0C10h+pszDest], r14w
0x180007eb0  test    rdi, rdi
0x180007eb3  jz      short loc_180007ECA
0x180007eb5  mov     r8d, 10h; uType
0x180007ebb  lea     rdx, [rbp+0C10h+pszDest]; lpText
0x180007ec2  mov     rcx, rdi; hWnd
0x180007ec5  call    DoMessage
0x180007eca  mov     rcx, r12; hCursor
0x180007ecd  call    cs:__imp_SetCursor
0x180007ed3  lea     rdx, [rbp+0C10h+pszDest]; lpszErrorMsg
0x180007eda  mov     ecx, ebx; dwErrorCode
0x180007edc  call    SQLPostInstallerErrorW
0x180007ee1  jmp     loc_180008099
0x180007ee6  lea     rdx, aConfigdsnw; "ConfigDSNW"
0x180007eed  mov     rcx, r15; hModule
0x180007ef0  call    cs:__imp_GetProcAddress
0x180007ef6  test    rax, rax
0x180007ef9  jnz     loc_18000804B
0x180007eff  lea     rdx, aConfigdsn; "ConfigDSN"
0x180007f06  mov     rcx, r15; hModule
0x180007f09  call    cs:__imp_GetProcAddress
0x180007f0f  mov     rbx, rax
0x180007f12  test    rax, rax
0x180007f15  jz      loc_180007FEC
0x180007f1b  mov     esi, 0Eh
0x180007f20  mov     [rsp+0D10h+var_CB0], r14
0x180007f25  mov     dword ptr [rsp+0D10h+Arguments], esi
0x180007f29  lea     r9, [rsp+0D10h+var_CB0]
0x180007f2e  mov     qword ptr [rsp+0D10h+nSize], r14
0x180007f33  lea     rdx, [rbp+0C10h+var_880]
0x180007f3a  mov     [rsp+0D10h+var_CB8], r14
0x180007f3f  lea     r8d, [rsi-11h]
0x180007f43  mov     dword ptr [rsp+0D10h+lpBuffer], r8d
0x180007f48  call    LConvertToAnsi
0x180007f4d  mov     rcx, r13
0x180007f50  call    wdnlen
0x180007f55  mov     dword ptr [rsp+0D10h+Arguments], esi
0x180007f59  lea     r9, [rsp+0D10h+var_CB8]
0x180007f5e  movsx   r8d, ax
0x180007f62  mov     rdx, r13
0x180007f65  mov     qword ptr [rsp+0D10h+nSize], r14
0x180007f6a  mov     dword ptr [rsp+0D10h+lpBuffer], r14d
0x180007f6f  call    LConvertToAnsi
0x180007f74  mov     r14, [rsp+0D10h+var_CB0]
0x180007f79  mov     rsi, [rsp+0D10h+var_CB8]
0x180007f7e  test    r14, r14
0x180007f81  jz      short loc_180007FB8
0x180007f83  test    rsi, rsi
0x180007f86  jnz     short loc_180007F8D
0x180007f88  test    r13, r13
0x180007f8b  jnz     short loc_180007FB8
0x180007f8d  movzx   edx, [rsp+0D10h+var_CC0]
0x180007f92  mov     r9, rsi
0x180007f95  mov     r8, r14
0x180007f98  mov     rcx, rdi
0x180007f9b  mov     rax, rbx
0x180007f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fa3  mov     ebx, eax
0x180007fa5  test    eax, eax
0x180007fa7  jnz     short loc_180007FC9
0x180007fa9  mov     edx, 587h
0x180007fae  lea     ecx, [rax+0Bh]
0x180007fb1  call    PostInstErrorMsgId
0x180007fb6  jmp     short loc_180007FC9
0x180007fb8  mov     edx, 586h
0x180007fbd  mov     ecx, 1
0x180007fc2  call    PostInstErrorMsgId
0x180007fc7  xor     ebx, ebx
0x180007fc9  test    r14, r14
0x180007fcc  jz      short loc_180007FD6
0x180007fce  mov     rcx, r14
0x180007fd1  call    OFree
0x180007fd6  test    rsi, rsi
0x180007fd9  jz      loc_180008072
0x180007fdf  mov     rcx, rsi
0x180007fe2  call    OFree
0x180007fe7  jmp     loc_180008072
0x180007fec  mov     ebx, 52Dh
0x180007ff1  test    rdi, rdi
0x180007ff4  jz      short loc_18000803A
0x180007ff6  mov     r8d, ebx
0x180007ff9  lea     rcx, [rsp+0D10h+pszFormat]; lpBuffer
0x180007ffe  mov     edx, 104h; cchBufferMax
0x180008003  call    SetString
0x180008008  lea     r9, [rbp+0C10h+var_880]
0x18000800f  mov     edx, 208h; cchDest
0x180008014  lea     r8, [rsp+0D10h+pszFormat]; pszFormat
0x180008019  lea     rcx, [rbp+0C10h+pszDest]; pszDest
0x180008020  call    StringCchPrintfW
0x180008025  mov     r8d, 10h; uType
0x18000802b  lea     rdx, [rbp+0C10h+pszDest]; lpText
0x180008032  mov     rcx, rdi; hWnd
0x180008035  call    DoMessage
0x18000803a  mov     edx, ebx
0x18000803c  mov     ecx, 0Dh
0x180008041  call    PostInstErrorMsgId
0x180008046  mov     ebx, r14d
0x180008049  jmp     short loc_180008072
0x18000804b  mov     edx, esi
0x18000804d  lea     r8, [rbp+0C10h+var_880]
0x180008054  mov     r9, r13
0x180008057  mov     rcx, rdi
0x18000805a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000805f  mov     ebx, eax
0x180008061  test    eax, eax
0x180008063  jnz     short loc_180008072
0x180008065  mov     edx, 587h
0x18000806a  lea     ecx, [rax+0Bh]
0x18000806d  call    PostInstErrorMsgId
0x180008072  mov     rcx, r15; hLibModule
0x180008075  call    cs:__imp_FreeLibrary
0x18000807b  mov     rcx, r12; hCursor
0x18000807e  call    cs:__imp_SetCursor
0x180008084  mov     eax, ebx
0x180008086  jmp     short loc_18000809B
0x180008088  mov     ecx, 7
0x18000808d  jmp     short loc_180008094
0x18000808f  mov     ecx, 5
0x180008094  call    PostInstError
0x180008099  xor     eax, eax
0x18000809b  mov     rcx, [rbp+0C10h+var_50]
0x1800080a2  xor     rcx, rsp; StackCookie
0x1800080a5  call    __security_check_cookie
0x1800080aa  add     rsp, 0CD8h
0x1800080b1  pop     r15
0x1800080b3  pop     r14
0x1800080b5  pop     r13
0x1800080b7  pop     r12
0x1800080b9  pop     rdi
0x1800080ba  pop     rsi
0x1800080bb  pop     rbx
0x1800080bc  pop     rbp
0x1800080bd  retn
```
