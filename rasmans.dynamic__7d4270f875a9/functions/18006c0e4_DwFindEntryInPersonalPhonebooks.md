# DwFindEntryInPersonalPhonebooks

- ea: `0x18006c0e4`
- end: `0x18006c849`
- name: `DwFindEntryInPersonalPhonebooks`
- size: `1893`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180076514`

## callees

- `0x180005bfc`
- `0x18005fe20`
- `0x180060014`
- `0x180060298`
- `0x18006c0e4`
- `0x18006c850`
- `0x18006d4c4`
- `0x18007f0b4`
- `0x18007f108`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c52f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c74e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c52f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c74e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18006c576`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18006c576`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006c7e0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006c7e0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006c51a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006c51a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006c225`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006c225`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006c693`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006c693`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006c2fd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006c317`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006c59c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006c5b3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006c62d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006c2fd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006c317`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006c59c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006c5b3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006c62d`

## pseudocode

```c
__int64 __fastcall DwFindEntryInPersonalPhonebooks(
        __int64 a1,
        unsigned int a2,
        int a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6)
{
  __int64 FirstFileW; // r13
  STRSAFE_LPWSTR *v8; // r9
  HRESULT v9; // eax
  unsigned int v10; // ebx
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // ebx
  HRESULT v15; // eax
  unsigned int EntryFromSystem; // eax
  struct _LIST_ENTRY *v17; // rcx
  HRESULT v18; // eax
  DWORD LastError; // eax
  int v20; // ebx
  HRESULT v21; // eax
  bool v22; // zf
  int v23; // eax
  WCHAR *v24; // rax
  size_t *pcchRemaining; // [rsp+20h] [rbp-E0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR Buffer[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  wchar_t pszDest[264]; // [rsp+6D0h] [rbp+5D0h] BYREF

  if ( a1 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_SDc(WPP_GLOBAL_Control[1].Flink, a2, a3, a1, a2, a3 != 0);
    }
  }
  else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
         && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
         && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_Dc(WPP_GLOBAL_Control[1].Flink, 827, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, a2, a3 != 0);
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
      v10 = 0;
      goto LABEL_93;
    }
    v9 = StringCchCatExW(Buffer, 0x105u, L"\\Ras\\", v8, pcchRemaining, 0x100u);
    LOWORD(v10) = v9;
    if ( v9 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 828, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, (unsigned int)v9);
        v11 = WPP_GLOBAL_Control;
      }
      v10 = (unsigned __int16)v10;
      goto LABEL_94;
    }
  }
  else if ( !(unsigned int)GetPhonebookDirectory(1u, Buffer) )
  {
    v12 = 621;
    v10 = 621;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_94;
    }
    v13 = 829;
    goto LABEL_92;
  }
  v14 = 260 - lstrlenW(L"*.pbk");
  if ( lstrlenW(String) > v14 )
  {
    v12 = 621;
    v10 = 621;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_94;
    }
    v13 = 830;
    goto LABEL_92;
  }
  if ( !a3 )
  {
    v15 = StringCchPrintfExW(pszDest, 0x105u, 0, 0, 0x100u, L"%s%s", Buffer, L"rasphone.pbk");
    if ( v15 < 0 )
    {
      v10 = (unsigned __int16)v15;
      if ( (_WORD)v15 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_94;
        }
        v13 = 831;
LABEL_36:
        v12 = v10;
LABEL_92:
        WPP_SF_d(v11[1].Flink, v13, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v12);
        goto LABEL_93;
      }
      goto LABEL_93;
    }
    EntryFromSystem = DwReadEntryFromSystem(pszDest, (__int64)a5, a6);
    v10 = EntryFromSystem;
    if ( EntryFromSystem )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_48;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_44;
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 832, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, EntryFromSystem);
    }
    else if ( *a5 )
    {
      goto LABEL_93;
    }
    v17 = WPP_GLOBAL_Control;
LABEL_44:
    if ( v17 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v17[1].Blink) < 0 && BYTE1(v17[1].Blink) >= 2u )
      WPP_SF_d(v17[1].Flink, 833, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v10);
  }
LABEL_48:
  v18 = StringCchPrintfExW(String, 0x105u, 0, 0, 0x100u, L"%s%s", Buffer, L"*.pbk");
  if ( v18 < 0 )
  {
    v10 = (unsigned __int16)v18;
    if ( (_WORD)v18 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_94;
      }
      v13 = 834;
      goto LABEL_36;
    }
LABEL_93:
    v11 = WPP_GLOBAL_Control;
    goto LABEL_94;
  }
  while ( FirstFileW == -1 )
  {
    FirstFileW = (__int64)FindFirstFileW(String, &FindFileData);
    if ( FirstFileW == -1 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( !LastError )
        goto LABEL_93;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_94;
      }
      v13 = 835;
LABEL_91:
      v12 = LastError;
      goto LABEL_92;
    }
LABEL_62:
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      v20 = 260 - lstrlenW(Buffer);
      if ( lstrlenW(FindFileData.cFileName) > v20 )
      {
        v12 = 621;
        v10 = 621;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v13 = 837;
          goto LABEL_92;
        }
        goto LABEL_94;
      }
      v21 = StringCchPrintfExW(String, 0x105u, 0, 0, 0x100u, L"%s%s", Buffer, FindFileData.cFileName);
      if ( v21 < 0 )
      {
        v10 = (unsigned __int16)v21;
        if ( !(_WORD)v21 )
          goto LABEL_93;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v13 = 838;
          goto LABEL_36;
        }
        goto LABEL_94;
      }
      if ( a3 )
      {
        v23 = lstrlenW(String);
        v22 = 2LL * v23 == 0;
        v24 = &String[v23];
        if ( !v22 )
        {
          do
          {
            if ( *v24 == 92 )
              break;
            --v24;
          }
          while ( v24 != String );
        }
        if ( *v24 == 92 )
          ++v24;
        v22 = CompareStringW(0x7Fu, 1u, L"router.pbk", -1, v24, -1) == 2;
      }
      else
      {
        v22 = (unsigned int)CompareStringWrapW(FindFileData.cFileName, L"rasphone.pbk") == 0;
      }
      if ( !v22 )
      {
        v10 = DwReadEntryFromSystem(String, (__int64)a5, a6);
        if ( !v10 )
        {
          if ( *a5 )
            goto LABEL_93;
        }
      }
    }
  }
  if ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
    goto LABEL_62;
  LastError = GetLastError();
  v10 = LastError;
  if ( !LastError )
    goto LABEL_93;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v13 = 836;
    goto LABEL_91;
  }
LABEL_94:
  if ( !*a5 )
  {
    v10 = 623;
    if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v11[1].Blink) < 0 && BYTE1(v11[1].Blink) >= 2u )
    {
      WPP_SF_d(v11[1].Flink, 839, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 623);
      v11 = WPP_GLOBAL_Control;
    }
  }
  if ( FirstFileW != -1 )
  {
    FindClose((HANDLE)FirstFileW);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v11[1].Blink) < 0 && BYTE1(v11[1].Blink) >= 6u )
    WPP_SF_d(v11[1].Flink, 840, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18006c0e4  mov     [rsp-8+arg_10], rbx
0x18006c0e9  push    rbp
0x18006c0ea  push    rsi
0x18006c0eb  push    rdi
0x18006c0ec  push    r12
0x18006c0ee  push    r13
0x18006c0f0  push    r14
0x18006c0f2  push    r15
0x18006c0f4  lea     rbp, [rsp-7F0h]
0x18006c0fc  sub     rsp, 8F0h
0x18006c103  mov     rax, cs:__security_cookie
0x18006c10a  xor     rax, rsp
0x18006c10d  mov     [rbp+820h+var_40], rax
0x18006c114  mov     rbx, [rbp+820h+arg_20]
0x18006c11b  mov     r14d, r8d
0x18006c11e  mov     rax, [rbp+820h+arg_28]
0x18006c125  mov     r15d, edx
0x18006c128  mov     [rsp+920h+var_8E0], rbx
0x18006c12d  mov     r12, rcx
0x18006c130  mov     [rsp+920h+var_8D8], rax
0x18006c135  mov     [rsp+920h+var_8D0], r9
0x18006c13a  test    rcx, rcx
0x18006c13d  jz      short loc_18006C17A
0x18006c13f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c146  lea     rdi, WPP_GLOBAL_Control
0x18006c14d  cmp     rcx, rdi
0x18006c150  jz      short loc_18006C1BB
0x18006c152  test    byte ptr [rcx+1Ch], 80h
0x18006c156  jz      short loc_18006C1BB
0x18006c158  cmp     byte ptr [rcx+19h], 6
0x18006c15c  jb      short loc_18006C1BB
0x18006c15e  mov     rcx, [rcx+10h]
0x18006c162  test    r8d, r8d
0x18006c165  mov     r9, r12
0x18006c168  setnz   al
0x18006c16b  mov     byte ptr [rsp+920h+dwFlags], al
0x18006c16f  mov     dword ptr [rsp+920h+pcchRemaining], edx
0x18006c173  call    WPP_SF_SDc
0x18006c178  jmp     short loc_18006C1BB
0x18006c17a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c181  lea     rdi, WPP_GLOBAL_Control
0x18006c188  cmp     rcx, rdi
0x18006c18b  jz      short loc_18006C1BB
0x18006c18d  test    byte ptr [rcx+1Ch], 80h
0x18006c191  jz      short loc_18006C1BB
0x18006c193  cmp     byte ptr [rcx+19h], 6
0x18006c197  jb      short loc_18006C1BB
0x18006c199  mov     rcx, [rcx+10h]
0x18006c19d  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006c1a4  test    r14d, r14d
0x18006c1a7  mov     edx, 33Bh
0x18006c1ac  mov     r9d, r15d
0x18006c1af  setnz   al
0x18006c1b2  mov     byte ptr [rsp+920h+pcchRemaining], al; pcchRemaining
0x18006c1b6  call    WPP_SF_Dc
0x18006c1bb  mov     esi, 20Ah
0x18006c1c0  lea     rcx, [rbp+820h+pszDest]; void *
0x18006c1c7  mov     r8d, esi; Size
0x18006c1ca  xor     edx, edx; Val
0x18006c1cc  call    memset_0
0x18006c1d1  xor     edx, edx; Val
0x18006c1d3  lea     r8d, [rsi+46h]; Size
0x18006c1d7  lea     rcx, [rsp+920h+FindFileData]; void *
0x18006c1dc  call    memset_0
0x18006c1e1  mov     r8d, esi; Size
0x18006c1e4  lea     rcx, [rbp+820h+String]; void *
0x18006c1eb  xor     edx, edx; Val
0x18006c1ed  or      r13, 0FFFFFFFFFFFFFFFFh
0x18006c1f1  call    memset_0
0x18006c1f6  mov     r8d, esi; Size
0x18006c1f9  lea     rcx, [rbp+820h+Buffer]; void *
0x18006c200  xor     edx, edx; Val
0x18006c202  call    memset_0
0x18006c207  mov     qword ptr [rbx], 0
0x18006c20e  mov     esi, 105h
0x18006c213  test    r14d, r14d
0x18006c216  jz      loc_18006C2A7
0x18006c21c  mov     edx, esi; uSize
0x18006c21e  lea     rcx, [rbp+820h+Buffer]; lpBuffer
0x18006c225  call    cs:__imp_GetSystemDirectoryW
0x18006c22c  nop     dword ptr [rax+rax+00h]
0x18006c231  dec     eax
0x18006c233  cmp     eax, 0F2h
0x18006c238  ja      short loc_18006C2A0
0x18006c23a  lea     r8, aRas; "\\Ras\\"
0x18006c241  mov     [rsp+920h+dwFlags], 100h; dwFlags
0x18006c249  mov     edx, esi; cchDest
0x18006c24b  lea     rcx, [rbp+820h+Buffer]; pszDest
0x18006c252  call    StringCchCatExW
0x18006c257  mov     ebx, eax
0x18006c259  test    eax, eax
0x18006c25b  jns     loc_18006C2F6
0x18006c261  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c268  cmp     rcx, rdi
0x18006c26b  jz      short loc_18006C298
0x18006c26d  test    byte ptr [rcx+1Ch], 80h
0x18006c271  jz      short loc_18006C298
0x18006c273  cmp     byte ptr [rcx+19h], 2
0x18006c277  jb      short loc_18006C298
0x18006c279  mov     rcx, [rcx+10h]
0x18006c27d  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006c284  mov     edx, 33Ch
0x18006c289  mov     r9d, eax
0x18006c28c  call    WPP_SF_d
0x18006c291  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c298  movzx   ebx, bx
0x18006c29b  jmp     loc_18006C797
0x18006c2a0  xor     ebx, ebx
0x18006c2a2  jmp     loc_18006C790
0x18006c2a7  mov     r8d, esi
0x18006c2aa  lea     rdx, [rbp+820h+Buffer]
0x18006c2b1  mov     ecx, 1
0x18006c2b6  call    GetPhonebookDirectory
0x18006c2bb  test    eax, eax
0x18006c2bd  jnz     short loc_18006C2F6
0x18006c2bf  mov     r9d, 26Dh
0x18006c2c5  mov     ebx, r9d
0x18006c2c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c2cf  cmp     rcx, rdi
0x18006c2d2  jz      loc_18006C797
0x18006c2d8  test    byte ptr [rcx+1Ch], 80h
0x18006c2dc  jz      loc_18006C797
0x18006c2e2  cmp     byte ptr [rcx+19h], 2
0x18006c2e6  jb      loc_18006C797
0x18006c2ec  mov     edx, 33Dh
0x18006c2f1  jmp     loc_18006C780
0x18006c2f6  lea     rcx, aPbk; "*.pbk"
0x18006c2fd  call    cs:__imp_lstrlenW
0x18006c304  nop     dword ptr [rax+rax+00h]
0x18006c309  mov     ebx, 104h
0x18006c30e  lea     rcx, [rbp+820h+String]; lpString
0x18006c315  sub     ebx, eax
0x18006c317  call    cs:__imp_lstrlenW
0x18006c31e  nop     dword ptr [rax+rax+00h]
0x18006c323  cmp     eax, ebx
0x18006c325  jle     short loc_18006C35E
0x18006c327  mov     r9d, 26Dh
0x18006c32d  mov     ebx, r9d
0x18006c330  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c337  cmp     rcx, rdi
0x18006c33a  jz      loc_18006C797
0x18006c340  test    byte ptr [rcx+1Ch], 80h
0x18006c344  jz      loc_18006C797
0x18006c34a  cmp     byte ptr [rcx+19h], 2
0x18006c34e  jb      loc_18006C797
0x18006c354  mov     edx, 33Eh
0x18006c359  jmp     loc_18006C780
0x18006c35e  lea     rax, aRasphonePbk; "rasphone.pbk"
0x18006c365  test    r14d, r14d
0x18006c368  jnz     loc_18006C48A
0x18006c36e  mov     [rsp+920h+var_8E8], rax
0x18006c373  lea     rcx, [rbp+820h+pszDest]; pszDest
0x18006c37a  lea     rax, [rbp+820h+Buffer]
0x18006c381  xor     r9d, r9d; pcchRemaining
0x18006c384  mov     [rsp+920h+var_8F0], rax
0x18006c389  xor     r8d, r8d; ppszDestEnd
0x18006c38c  lea     rax, aSS_3; "%s%s"
0x18006c393  mov     rdx, rsi; cchDest
0x18006c396  mov     qword ptr [rsp+920h+dwFlags], rax; pszFormat
0x18006c39b  mov     dword ptr [rsp+920h+pcchRemaining], 100h; dwFlags
0x18006c3a3  call    StringCchPrintfExW
0x18006c3a8  test    eax, eax
0x18006c3aa  jns     short loc_18006C3E8
0x18006c3ac  movzx   ebx, ax
0x18006c3af  test    ebx, ebx
0x18006c3b1  jz      loc_18006C790
0x18006c3b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c3be  cmp     rcx, rdi
0x18006c3c1  jz      loc_18006C797
0x18006c3c7  test    byte ptr [rcx+1Ch], 80h
0x18006c3cb  jz      loc_18006C797
0x18006c3d1  cmp     byte ptr [rcx+19h], 2
0x18006c3d5  jb      loc_18006C797
0x18006c3db  mov     edx, 33Fh
0x18006c3e0  mov     r9d, ebx
0x18006c3e3  jmp     loc_18006C780
0x18006c3e8  mov     rax, [rsp+920h+var_8D8]
0x18006c3ed  lea     rcx, [rbp+820h+pszDest]; pszSrc
0x18006c3f4  mov     r9, [rsp+920h+var_8D0]
0x18006c3f9  mov     r8d, r15d
0x18006c3fc  mov     qword ptr [rsp+920h+dwFlags], rax; __int64
0x18006c401  mov     rdx, r12
0x18006c404  mov     rax, [rsp+920h+var_8E0]
0x18006c409  mov     [rsp+920h+pcchRemaining], rax; __int64
0x18006c40e  call    DwReadEntryFromSystem
0x18006c413  mov     ebx, eax
0x18006c415  test    eax, eax
0x18006c417  jz      short loc_18006C44B
0x18006c419  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c420  cmp     rcx, rdi
0x18006c423  jz      short loc_18006C48A
0x18006c425  test    byte ptr [rcx+1Ch], 80h
0x18006c429  jz      short loc_18006C461
0x18006c42b  cmp     byte ptr [rcx+19h], 2
0x18006c42f  jb      short loc_18006C461
0x18006c431  mov     rcx, [rcx+10h]
0x18006c435  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006c43c  mov     edx, 340h
0x18006c441  mov     r9d, eax
0x18006c444  call    WPP_SF_d
0x18006c449  jmp     short loc_18006C45A
0x18006c44b  mov     rax, [rsp+920h+var_8E0]
0x18006c450  cmp     qword ptr [rax], 0
0x18006c454  jnz     loc_18006C790
0x18006c45a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c461  cmp     rcx, rdi
0x18006c464  jz      short loc_18006C48A
0x18006c466  test    byte ptr [rcx+1Ch], 80h
0x18006c46a  jz      short loc_18006C48A
0x18006c46c  cmp     byte ptr [rcx+19h], 2
0x18006c470  jb      short loc_18006C48A
0x18006c472  mov     rcx, [rcx+10h]
0x18006c476  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006c47d  mov     edx, 341h
0x18006c482  mov     r9d, ebx
0x18006c485  call    WPP_SF_d
0x18006c48a  lea     rax, aPbk; "*.pbk"
0x18006c491  xor     r9d, r9d; pcchRemaining
0x18006c494  mov     [rsp+920h+var_8E8], rax
0x18006c499  lea     rcx, [rbp+820h+String]; pszDest
0x18006c4a0  lea     rax, [rbp+820h+Buffer]
0x18006c4a7  xor     r8d, r8d; ppszDestEnd
0x18006c4aa  mov     [rsp+920h+var_8F0], rax
0x18006c4af  mov     rdx, rsi; cchDest
0x18006c4b2  lea     rax, aSS_3; "%s%s"
0x18006c4b9  mov     qword ptr [rsp+920h+dwFlags], rax; pszFormat
0x18006c4be  mov     dword ptr [rsp+920h+pcchRemaining], 100h; dwFlags
0x18006c4c6  call    StringCchPrintfExW
0x18006c4cb  test    eax, eax
0x18006c4cd  jns     short loc_18006C508
0x18006c4cf  movzx   ebx, ax
0x18006c4d2  test    ebx, ebx
0x18006c4d4  jz      loc_18006C790
0x18006c4da  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c4e1  cmp     rcx, rdi
0x18006c4e4  jz      loc_18006C797
0x18006c4ea  test    byte ptr [rcx+1Ch], 80h
0x18006c4ee  jz      loc_18006C797
0x18006c4f4  cmp     byte ptr [rcx+19h], 2
0x18006c4f8  jb      loc_18006C797
0x18006c4fe  mov     edx, 342h
0x18006c503  jmp     loc_18006C3E0
0x18006c508  lea     rdx, [rsp+920h+FindFileData]; lpFindFileData
0x18006c50d  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18006c511  jnz     short loc_18006C573
0x18006c513  lea     rcx, [rbp+820h+String]; lpFileName
0x18006c51a  call    cs:__imp_FindFirstFileW
0x18006c521  nop     dword ptr [rax+rax+00h]
0x18006c526  mov     r13, rax
0x18006c529  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006c52d  jnz     short loc_18006C58A
0x18006c52f  call    cs:__imp_GetLastError
0x18006c536  nop     dword ptr [rax+rax+00h]
0x18006c53b  mov     ebx, eax
0x18006c53d  test    eax, eax
0x18006c53f  jz      loc_18006C790
0x18006c545  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c54c  cmp     rcx, rdi
0x18006c54f  jz      loc_18006C797
0x18006c555  test    byte ptr [rcx+1Ch], 80h
0x18006c559  jz      loc_18006C797
0x18006c55f  cmp     byte ptr [rcx+19h], 2
0x18006c563  jb      loc_18006C797
0x18006c569  mov     edx, 343h
0x18006c56e  jmp     loc_18006C77D
0x18006c573  mov     rcx, r13; hFindFile
0x18006c576  call    cs:__imp_FindNextFileW
0x18006c57d  nop     dword ptr [rax+rax+00h]
0x18006c582  test    eax, eax
0x18006c584  jz      loc_18006C74E
0x18006c58a  test    byte ptr [rsp+920h+FindFileData.dwFileAttributes], 10h
0x18006c58f  jnz     loc_18006C508
0x18006c595  lea     rcx, [rbp+820h+Buffer]; lpString
0x18006c59c  call    cs:__imp_lstrlenW
0x18006c5a3  nop     dword ptr [rax+rax+00h]
0x18006c5a8  mov     ebx, 104h
0x18006c5ad  lea     rcx, [rbp+820h+FindFileData.cFileName]; lpString
0x18006c5b1  sub     ebx, eax
0x18006c5b3  call    cs:__imp_lstrlenW
0x18006c5ba  nop     dword ptr [rax+rax+00h]
0x18006c5bf  cmp     eax, ebx
0x18006c5c1  jg      loc_18006C726
0x18006c5c7  lea     rax, [rbp+820h+FindFileData.cFileName]
0x18006c5cb  xor     r9d, r9d; pcchRemaining
0x18006c5ce  mov     [rsp+920h+var_8E8], rax
0x18006c5d3  lea     rcx, [rbp+820h+String]; pszDest
0x18006c5da  lea     rax, [rbp+820h+Buffer]
0x18006c5e1  xor     r8d, r8d; ppszDestEnd
0x18006c5e4  mov     [rsp+920h+var_8F0], rax
0x18006c5e9  mov     rdx, rsi; cchDest
0x18006c5ec  lea     rax, aSS_3; "%s%s"
0x18006c5f3  mov     qword ptr [rsp+920h+dwFlags], rax; pszFormat
0x18006c5f8  mov     dword ptr [rsp+920h+pcchRemaining], 100h; dwFlags
0x18006c600  call    StringCchPrintfExW
0x18006c605  test    eax, eax
0x18006c607  js      loc_18006C6F1
0x18006c60d  test    r14d, r14d
0x18006c610  jnz     short loc_18006C626
0x18006c612  lea     rdx, aRasphonePbk; "rasphone.pbk"
0x18006c619  lea     rcx, [rbp+820h+FindFileData.cFileName]; lpString1
  ... truncated ...
```
