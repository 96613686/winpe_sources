# DwFindEntryInPersonalPhonebooks

- ea: `0x1800cb0f8`
- end: `0x1800cb7d5`
- name: `DwFindEntryInPersonalPhonebooks`
- size: `1757`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800289e0`

## callees

- `0x18000c190`
- `0x18000dde0`
- `0x180028e34`
- `0x180029390`
- `0x18004e580`
- `0x18007e548`
- `0x18008d8d8`
- `0x1800cb0f8`
- `0x1800cfa9c`
- `0x1800d01a0`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb6e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb6e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800cb239`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800cb239`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800cb30b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800cb31f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800cb5b1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800cb5c2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800cb30b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800cb31f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800cb5b1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800cb5c2`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800cb773`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800cb773`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800cb595`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800cb595`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800cb545`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800cb545`
- `rtutils!TracePrintfExA` at `0x1800cb47f`
- `rtutils!TracePrintfExA` at `0x1800cb47f`

## string_xrefs

- `0x1800cb471`: `DwReadEntryFromSystem for rasphone.pbk failed with %d`

## pseudocode

```c
__int64 __fastcall DwFindEntryInPersonalPhonebooks(__int64 a1, unsigned int a2, int a3, int a4, _QWORD *a5, __int64 a6)
{
  int v8; // r12d
  __int64 FirstFileW; // r13
  STRSAFE_LPWSTR *v10; // r9
  HRESULT v11; // eax
  unsigned int v12; // ebx
  char *v13; // rcx
  __int64 v14; // r9
  __int64 v15; // rdx
  int v16; // ebx
  HRESULT v17; // eax
  unsigned int EntryFromSystem; // eax
  char *v19; // rcx
  HRESULT v20; // eax
  DWORD LastError; // eax
  int v22; // ebx
  HRESULT v23; // eax
  size_t *pcchRemaining; // [rsp+20h] [rbp-E0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR String[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  wchar_t pszDest[264]; // [rsp+6D0h] [rbp+5D0h] BYREF

  v8 = a1;
  if ( a1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_SDc(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a2, a3 != 0);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && *((char *)WPP_GLOBAL_Control + 28) < 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Dc(*((_QWORD *)WPP_GLOBAL_Control + 2), 827, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, a2, a3 != 0);
  }
  memset_0(pszDest, 0, 0x20Au);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = -1;
  memset_0(String, 0, 0x20Au);
  memset_0(Buffer, 0, 0x20Au);
  *a5 = 0;
  if ( a3 )
  {
    if ( GetSystemDirectoryW(Buffer, 0x105u) - 1 > 0xF2 )
    {
      v12 = 0;
      goto LABEL_90;
    }
    v11 = StringCchCatExW(Buffer, 0x105u, L"\\Ras\\", v10, pcchRemaining, 0x100u);
    LOWORD(v12) = v11;
    if ( v11 < 0 )
    {
      v13 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          828,
          &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
          (unsigned int)v11);
        v13 = (char *)WPP_GLOBAL_Control;
      }
      v12 = (unsigned __int16)v12;
      goto LABEL_91;
    }
  }
  else if ( !(unsigned int)GetPhonebookDirectory(1u, Buffer, 0x105u) )
  {
    v14 = 621;
    v12 = 621;
    v13 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_91;
    }
    v15 = 829;
    goto LABEL_89;
  }
  v16 = 260 - lstrlenW(L"*.pbk");
  if ( lstrlenW(String) > v16 )
  {
    v14 = 621;
    v12 = 621;
    v13 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((char *)WPP_GLOBAL_Control + 28) >= 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_91;
    }
    v15 = 830;
    goto LABEL_89;
  }
  if ( !a3 )
  {
    v17 = StringCchPrintfExW(pszDest, 0x105u, 0, 0, 0x100u, L"%s%s", Buffer, L"rasphone.pbk");
    if ( v17 < 0 )
    {
      v12 = (unsigned __int16)v17;
      if ( (_WORD)v17 )
      {
        v13 = (char *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || *((char *)WPP_GLOBAL_Control + 28) >= 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_91;
        }
        v15 = 831;
LABEL_36:
        v14 = v12;
LABEL_89:
        WPP_SF_d(*((_QWORD *)v13 + 2), v15, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v14);
        goto LABEL_90;
      }
      goto LABEL_90;
    }
    EntryFromSystem = DwReadEntryFromSystem((unsigned int)pszDest, v8, a2, a4, (__int64)a5, a6);
    v12 = EntryFromSystem;
    if ( EntryFromSystem )
    {
      v19 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_44;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        832,
        &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
        EntryFromSystem);
    }
    else if ( *a5 )
    {
      goto LABEL_90;
    }
    v19 = (char *)WPP_GLOBAL_Control;
LABEL_44:
    if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(g_dwTraceId, 0xCu, "DwReadEntryFromSystem for rasphone.pbk failed with %d", v12);
      v19 = (char *)WPP_GLOBAL_Control;
    }
    if ( v19 != (char *)&WPP_GLOBAL_Control && v19[28] < 0 && (unsigned __int8)v19[25] >= 2u )
      WPP_SF_d(*((_QWORD *)v19 + 2), 833, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v12);
  }
  v20 = StringCchPrintfExW(String, 0x105u, 0, 0, 0x100u, L"%s%s", Buffer, L"*.pbk");
  if ( v20 < 0 )
  {
    v12 = (unsigned __int16)v20;
    if ( (_WORD)v20 )
    {
      v13 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_91;
      }
      v15 = 834;
      goto LABEL_36;
    }
LABEL_90:
    v13 = (char *)WPP_GLOBAL_Control;
    goto LABEL_91;
  }
  while ( 1 )
  {
    if ( FirstFileW == -1 )
    {
      FirstFileW = (__int64)FindFirstFileW(String, &FindFileData);
      if ( FirstFileW == -1 )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( !LastError )
          goto LABEL_90;
        v13 = (char *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || *((char *)WPP_GLOBAL_Control + 28) >= 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_91;
        }
        v15 = 835;
LABEL_88:
        v14 = LastError;
        goto LABEL_89;
      }
      goto LABEL_64;
    }
    if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
      break;
LABEL_64:
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      v22 = 260 - lstrlenW(Buffer);
      if ( lstrlenW(FindFileData.cFileName) > v22 )
      {
        v14 = 621;
        v12 = 621;
        v13 = (char *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 837;
          goto LABEL_89;
        }
        goto LABEL_91;
      }
      v23 = StringCchPrintfExW(String, 0x105u, 0, 0, 0x100u, L"%s%s", Buffer, FindFileData.cFileName);
      if ( v23 < 0 )
      {
        v12 = (unsigned __int16)v23;
        if ( !(_WORD)v23 )
          goto LABEL_90;
        v13 = (char *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 838;
          goto LABEL_36;
        }
        goto LABEL_91;
      }
      if ( a3 )
      {
        if ( !(unsigned int)IsRouterPhonebook(String) )
          goto LABEL_71;
      }
      else if ( (unsigned int)CompareStringWrapW(FindFileData.cFileName, L"rasphone.pbk") )
      {
LABEL_71:
        v12 = DwReadEntryFromSystem((unsigned int)String, v8, a2, a4, (__int64)a5, a6);
        if ( !v12 && *a5 )
          goto LABEL_90;
      }
    }
  }
  LastError = GetLastError();
  v12 = LastError;
  if ( !LastError )
    goto LABEL_90;
  v13 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = 836;
    goto LABEL_88;
  }
LABEL_91:
  if ( !*a5 )
  {
    v12 = 623;
    if ( v13 != (char *)&WPP_GLOBAL_Control && v13[28] < 0 && (unsigned __int8)v13[25] >= 2u )
    {
      WPP_SF_d(*((_QWORD *)v13 + 2), 839, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 623);
      v13 = (char *)WPP_GLOBAL_Control;
    }
  }
  if ( FirstFileW != -1 )
  {
    FindClose((HANDLE)FirstFileW);
    v13 = (char *)WPP_GLOBAL_Control;
  }
  if ( v13 != (char *)&WPP_GLOBAL_Control && v13[28] < 0 && (unsigned __int8)v13[25] >= 6u )
    WPP_SF_d(*((_QWORD *)v13 + 2), 840, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x1800cb0f8  mov     [rsp-8+arg_10], rbx
0x1800cb0fd  push    rbp
0x1800cb0fe  push    rsi
0x1800cb0ff  push    rdi
0x1800cb100  push    r12
0x1800cb102  push    r13
0x1800cb104  push    r14
0x1800cb106  push    r15
0x1800cb108  lea     rbp, [rsp-7F0h]
0x1800cb110  sub     rsp, 8F0h
0x1800cb117  mov     rax, cs:__security_cookie
0x1800cb11e  xor     rax, rsp
0x1800cb121  mov     [rbp+820h+var_40], rax
0x1800cb128  mov     rbx, [rbp+820h+arg_20]
0x1800cb12f  mov     r14d, r8d
0x1800cb132  mov     rax, [rbp+820h+arg_28]
0x1800cb139  mov     r15d, edx
0x1800cb13c  mov     [rsp+920h+var_8E0], rbx
0x1800cb141  mov     r12, rcx
0x1800cb144  mov     [rsp+920h+var_8D8], rax
0x1800cb149  mov     [rsp+920h+var_8D0], r9
0x1800cb14e  test    rcx, rcx
0x1800cb151  jz      short loc_1800CB18E
0x1800cb153  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb15a  lea     rdi, WPP_GLOBAL_Control
0x1800cb161  cmp     rcx, rdi
0x1800cb164  jz      short loc_1800CB1CF
0x1800cb166  test    byte ptr [rcx+1Ch], 80h
0x1800cb16a  jz      short loc_1800CB1CF
0x1800cb16c  cmp     byte ptr [rcx+19h], 6
0x1800cb170  jb      short loc_1800CB1CF
0x1800cb172  mov     rcx, [rcx+10h]
0x1800cb176  test    r8d, r8d
0x1800cb179  mov     r9, r12
0x1800cb17c  setnz   al
0x1800cb17f  mov     byte ptr [rsp+920h+dwFlags], al
0x1800cb183  mov     dword ptr [rsp+920h+pcchRemaining], edx
0x1800cb187  call    WPP_SF_SDc
0x1800cb18c  jmp     short loc_1800CB1CF
0x1800cb18e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb195  lea     rdi, WPP_GLOBAL_Control
0x1800cb19c  cmp     rcx, rdi
0x1800cb19f  jz      short loc_1800CB1CF
0x1800cb1a1  test    byte ptr [rcx+1Ch], 80h
0x1800cb1a5  jz      short loc_1800CB1CF
0x1800cb1a7  cmp     byte ptr [rcx+19h], 6
0x1800cb1ab  jb      short loc_1800CB1CF
0x1800cb1ad  mov     rcx, [rcx+10h]
0x1800cb1b1  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800cb1b8  test    r14d, r14d
0x1800cb1bb  mov     edx, 33Bh
0x1800cb1c0  mov     r9d, r15d
0x1800cb1c3  setnz   al
0x1800cb1c6  mov     byte ptr [rsp+920h+pcchRemaining], al; pcchRemaining
0x1800cb1ca  call    WPP_SF_Dc
0x1800cb1cf  mov     esi, 20Ah
0x1800cb1d4  lea     rcx, [rbp+820h+pszDest]; void *
0x1800cb1db  mov     r8d, esi; Size
0x1800cb1de  xor     edx, edx; Val
0x1800cb1e0  call    memset_0
0x1800cb1e5  xor     edx, edx; Val
0x1800cb1e7  lea     r8d, [rsi+46h]; Size
0x1800cb1eb  lea     rcx, [rsp+920h+FindFileData]; void *
0x1800cb1f0  call    memset_0
0x1800cb1f5  mov     r8d, esi; Size
0x1800cb1f8  lea     rcx, [rbp+820h+String]; void *
0x1800cb1ff  xor     edx, edx; Val
0x1800cb201  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800cb205  call    memset_0
0x1800cb20a  mov     r8d, esi; Size
0x1800cb20d  lea     rcx, [rbp+820h+Buffer]; void *
0x1800cb214  xor     edx, edx; Val
0x1800cb216  call    memset_0
0x1800cb21b  mov     qword ptr [rbx], 0
0x1800cb222  mov     esi, 105h
0x1800cb227  test    r14d, r14d
0x1800cb22a  jz      loc_1800CB2B5
0x1800cb230  mov     edx, esi; uSize
0x1800cb232  lea     rcx, [rbp+820h+Buffer]; lpBuffer
0x1800cb239  call    cs:__imp_GetSystemDirectoryW
0x1800cb23f  dec     eax
0x1800cb241  cmp     eax, 0F2h
0x1800cb246  ja      short loc_1800CB2AE
0x1800cb248  lea     r8, aRas; "\\Ras\\"
0x1800cb24f  mov     [rsp+920h+dwFlags], 100h; dwFlags
0x1800cb257  mov     edx, esi; cchDest
0x1800cb259  lea     rcx, [rbp+820h+Buffer]; pszDest
0x1800cb260  call    StringCchCatExW
0x1800cb265  mov     ebx, eax
0x1800cb267  test    eax, eax
0x1800cb269  jns     loc_1800CB304
0x1800cb26f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb276  cmp     rcx, rdi
0x1800cb279  jz      short loc_1800CB2A6
0x1800cb27b  test    byte ptr [rcx+1Ch], 80h
0x1800cb27f  jz      short loc_1800CB2A6
0x1800cb281  cmp     byte ptr [rcx+19h], 2
0x1800cb285  jb      short loc_1800CB2A6
0x1800cb287  mov     rcx, [rcx+10h]
0x1800cb28b  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800cb292  mov     edx, 33Ch
0x1800cb297  mov     r9d, eax
0x1800cb29a  call    WPP_SF_d
0x1800cb29f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb2a6  movzx   ebx, bx
0x1800cb2a9  jmp     loc_1800CB72A
0x1800cb2ae  xor     ebx, ebx
0x1800cb2b0  jmp     loc_1800CB723
0x1800cb2b5  mov     r8d, esi
0x1800cb2b8  lea     rdx, [rbp+820h+Buffer]
0x1800cb2bf  mov     ecx, 1
0x1800cb2c4  call    GetPhonebookDirectory
0x1800cb2c9  test    eax, eax
0x1800cb2cb  jnz     short loc_1800CB304
0x1800cb2cd  mov     r9d, 26Dh
0x1800cb2d3  mov     ebx, r9d
0x1800cb2d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb2dd  cmp     rcx, rdi
0x1800cb2e0  jz      loc_1800CB72A
0x1800cb2e6  test    byte ptr [rcx+1Ch], 80h
0x1800cb2ea  jz      loc_1800CB72A
0x1800cb2f0  cmp     byte ptr [rcx+19h], 2
0x1800cb2f4  jb      loc_1800CB72A
0x1800cb2fa  mov     edx, 33Dh
0x1800cb2ff  jmp     loc_1800CB713
0x1800cb304  lea     rcx, aPbk; "*.pbk"
0x1800cb30b  call    cs:__imp_lstrlenW
0x1800cb311  mov     ebx, 104h
0x1800cb316  lea     rcx, [rbp+820h+String]; lpString
0x1800cb31d  sub     ebx, eax
0x1800cb31f  call    cs:__imp_lstrlenW
0x1800cb325  cmp     eax, ebx
0x1800cb327  jle     short loc_1800CB360
0x1800cb329  mov     r9d, 26Dh
0x1800cb32f  mov     ebx, r9d
0x1800cb332  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb339  cmp     rcx, rdi
0x1800cb33c  jz      loc_1800CB72A
0x1800cb342  test    byte ptr [rcx+1Ch], 80h
0x1800cb346  jz      loc_1800CB72A
0x1800cb34c  cmp     byte ptr [rcx+19h], 2
0x1800cb350  jb      loc_1800CB72A
0x1800cb356  mov     edx, 33Eh
0x1800cb35b  jmp     loc_1800CB713
0x1800cb360  lea     rax, aRasphonePbk; "rasphone.pbk"
0x1800cb367  test    r14d, r14d
0x1800cb36a  jnz     loc_1800CB4B5
0x1800cb370  mov     [rsp+920h+var_8E8], rax
0x1800cb375  lea     rcx, [rbp+820h+pszDest]; pszDest
0x1800cb37c  lea     rax, [rbp+820h+Buffer]
0x1800cb383  xor     r9d, r9d; pcchRemaining
0x1800cb386  mov     [rsp+920h+var_8F0], rax
0x1800cb38b  xor     r8d, r8d; ppszDestEnd
0x1800cb38e  lea     rax, aSS_3; "%s%s"
0x1800cb395  mov     rdx, rsi; cchDest
0x1800cb398  mov     qword ptr [rsp+920h+dwFlags], rax; pszFormat
0x1800cb39d  mov     dword ptr [rsp+920h+pcchRemaining], 100h; dwFlags
0x1800cb3a5  call    StringCchPrintfExW
0x1800cb3aa  test    eax, eax
0x1800cb3ac  jns     short loc_1800CB3EA
0x1800cb3ae  movzx   ebx, ax
0x1800cb3b1  test    ebx, ebx
0x1800cb3b3  jz      loc_1800CB723
0x1800cb3b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb3c0  cmp     rcx, rdi
0x1800cb3c3  jz      loc_1800CB72A
0x1800cb3c9  test    byte ptr [rcx+1Ch], 80h
0x1800cb3cd  jz      loc_1800CB72A
0x1800cb3d3  cmp     byte ptr [rcx+19h], 2
0x1800cb3d7  jb      loc_1800CB72A
0x1800cb3dd  mov     edx, 33Fh
0x1800cb3e2  mov     r9d, ebx
0x1800cb3e5  jmp     loc_1800CB713
0x1800cb3ea  mov     rax, [rsp+920h+var_8D8]
0x1800cb3ef  lea     rcx, [rbp+820h+pszDest]
0x1800cb3f6  mov     r9, [rsp+920h+var_8D0]
0x1800cb3fb  mov     r8d, r15d
0x1800cb3fe  mov     qword ptr [rsp+920h+dwFlags], rax
0x1800cb403  mov     rdx, r12
0x1800cb406  mov     rax, [rsp+920h+var_8E0]
0x1800cb40b  mov     [rsp+920h+pcchRemaining], rax
0x1800cb410  call    DwReadEntryFromSystem
0x1800cb415  mov     ebx, eax
0x1800cb417  test    eax, eax
0x1800cb419  jz      short loc_1800CB44D
0x1800cb41b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb422  cmp     rcx, rdi
0x1800cb425  jz      short loc_1800CB463
0x1800cb427  test    byte ptr [rcx+1Ch], 80h
0x1800cb42b  jz      short loc_1800CB463
0x1800cb42d  cmp     byte ptr [rcx+19h], 2
0x1800cb431  jb      short loc_1800CB463
0x1800cb433  mov     rcx, [rcx+10h]
0x1800cb437  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800cb43e  mov     edx, 340h
0x1800cb443  mov     r9d, eax
0x1800cb446  call    WPP_SF_d
0x1800cb44b  jmp     short loc_1800CB45C
0x1800cb44d  mov     rax, [rsp+920h+var_8E0]
0x1800cb452  cmp     qword ptr [rax], 0
0x1800cb456  jnz     loc_1800CB723
0x1800cb45c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb463  mov     eax, cs:g_dwTraceId
0x1800cb469  cmp     eax, 0FFFFFFFFh
0x1800cb46c  jz      short loc_1800CB48C
0x1800cb46e  mov     r9d, ebx
0x1800cb471  lea     r8, aDwreadentryfro; "DwReadEntryFromSystem for rasphone.pbk "...
0x1800cb478  mov     edx, 0Ch; dwFlags
0x1800cb47d  mov     ecx, eax; dwTraceID
0x1800cb47f  call    cs:__imp_TracePrintfExA
0x1800cb485  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb48c  cmp     rcx, rdi
0x1800cb48f  jz      short loc_1800CB4B5
0x1800cb491  test    byte ptr [rcx+1Ch], 80h
0x1800cb495  jz      short loc_1800CB4B5
0x1800cb497  cmp     byte ptr [rcx+19h], 2
0x1800cb49b  jb      short loc_1800CB4B5
0x1800cb49d  mov     rcx, [rcx+10h]
0x1800cb4a1  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800cb4a8  mov     edx, 341h
0x1800cb4ad  mov     r9d, ebx
0x1800cb4b0  call    WPP_SF_d
0x1800cb4b5  lea     rax, aPbk; "*.pbk"
0x1800cb4bc  xor     r9d, r9d; pcchRemaining
0x1800cb4bf  mov     [rsp+920h+var_8E8], rax
0x1800cb4c4  lea     rcx, [rbp+820h+String]; pszDest
0x1800cb4cb  lea     rax, [rbp+820h+Buffer]
0x1800cb4d2  xor     r8d, r8d; ppszDestEnd
0x1800cb4d5  mov     [rsp+920h+var_8F0], rax
0x1800cb4da  mov     rdx, rsi; cchDest
0x1800cb4dd  lea     rax, aSS_3; "%s%s"
0x1800cb4e4  mov     qword ptr [rsp+920h+dwFlags], rax; pszFormat
0x1800cb4e9  mov     dword ptr [rsp+920h+pcchRemaining], 100h; dwFlags
0x1800cb4f1  call    StringCchPrintfExW
0x1800cb4f6  test    eax, eax
0x1800cb4f8  jns     short loc_1800CB533
0x1800cb4fa  movzx   ebx, ax
0x1800cb4fd  test    ebx, ebx
0x1800cb4ff  jz      loc_1800CB723
0x1800cb505  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb50c  cmp     rcx, rdi
0x1800cb50f  jz      loc_1800CB72A
0x1800cb515  test    byte ptr [rcx+1Ch], 80h
0x1800cb519  jz      loc_1800CB72A
0x1800cb51f  cmp     byte ptr [rcx+19h], 2
0x1800cb523  jb      loc_1800CB72A
0x1800cb529  mov     edx, 342h
0x1800cb52e  jmp     loc_1800CB3E2
0x1800cb533  lea     rdx, [rsp+920h+FindFileData]; lpFindFileData
0x1800cb538  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800cb53c  jnz     short loc_1800CB592
0x1800cb53e  lea     rcx, [rbp+820h+String]; lpFileName
0x1800cb545  call    cs:__imp_FindFirstFileW
0x1800cb54b  mov     r13, rax
0x1800cb54e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800cb552  jnz     short loc_1800CB5A3
0x1800cb554  call    cs:__imp_GetLastError
0x1800cb55a  mov     ebx, eax
0x1800cb55c  test    eax, eax
0x1800cb55e  jz      loc_1800CB723
0x1800cb564  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb56b  cmp     rcx, rdi
0x1800cb56e  jz      loc_1800CB72A
0x1800cb574  test    byte ptr [rcx+1Ch], 80h
0x1800cb578  jz      loc_1800CB72A
0x1800cb57e  cmp     byte ptr [rcx+19h], 2
0x1800cb582  jb      loc_1800CB72A
0x1800cb588  mov     edx, 343h
0x1800cb58d  jmp     loc_1800CB710
0x1800cb592  mov     rcx, r13; hFindFile
0x1800cb595  call    cs:__imp_FindNextFileW
0x1800cb59b  test    eax, eax
0x1800cb59d  jz      loc_1800CB6E7
0x1800cb5a3  test    byte ptr [rsp+920h+FindFileData.dwFileAttributes], 10h
0x1800cb5a8  jnz     short loc_1800CB533
0x1800cb5aa  lea     rcx, [rbp+820h+Buffer]; lpString
0x1800cb5b1  call    cs:__imp_lstrlenW
0x1800cb5b7  mov     ebx, 104h
0x1800cb5bc  lea     rcx, [rbp+820h+FindFileData.cFileName]; lpString
0x1800cb5c0  sub     ebx, eax
0x1800cb5c2  call    cs:__imp_lstrlenW
0x1800cb5c8  cmp     eax, ebx
0x1800cb5ca  jg      loc_1800CB6BF
0x1800cb5d0  lea     rax, [rbp+820h+FindFileData.cFileName]
0x1800cb5d4  xor     r9d, r9d; pcchRemaining
0x1800cb5d7  mov     [rsp+920h+var_8E8], rax
0x1800cb5dc  lea     rcx, [rbp+820h+String]; pszDest
0x1800cb5e3  lea     rax, [rbp+820h+Buffer]
0x1800cb5ea  xor     r8d, r8d; ppszDestEnd
0x1800cb5ed  mov     [rsp+920h+var_8F0], rax
0x1800cb5f2  mov     rdx, rsi; cchDest
0x1800cb5f5  lea     rax, aSS_3; "%s%s"
0x1800cb5fc  mov     qword ptr [rsp+920h+dwFlags], rax; pszFormat
0x1800cb601  mov     dword ptr [rsp+920h+pcchRemaining], 100h; dwFlags
0x1800cb609  call    StringCchPrintfExW
0x1800cb60e  test    eax, eax
0x1800cb610  js      short loc_1800CB68E
0x1800cb612  test    r14d, r14d
0x1800cb615  jnz     short loc_1800CB631
0x1800cb617  lea     rdx, aRasphonePbk; "rasphone.pbk"
  ... truncated ...
```
