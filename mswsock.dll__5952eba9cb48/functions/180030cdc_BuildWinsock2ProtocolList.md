# BuildWinsock2ProtocolList

- ea: `0x180030cdc`
- end: `0x18003151f`
- name: `BuildWinsock2ProtocolList`
- size: `2115`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180032294`

## callees

- `0x18001757c`
- `0x18001c53c`
- `0x180021408`
- `0x1800222f0`
- `0x180022bd2`
- `0x180030cdc`
- `0x180031b4c`
- `0x1800327cc`
- `0x18003439c`
- `0x180037195`
- `0x18003847c`
- `0x18003a78c`
- `0x180053010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800310fb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800313e7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800310fb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800313e7`
- `ntdll!RtlFreeHeap` at `0x1800314d4`
- `ntdll!RtlFreeHeap` at `0x1800314d4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030ee0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030ee0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030f07`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030f07`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800314ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800314ec`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180030e72`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180030e72`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180030ddb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180030ddb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800314b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800314b2`

## string_xrefs

- `0x180030d88`: `Failed to open provider parameters key`
- `0x180030dee`: `Failed to read number of subkeys`
- `0x180030ead`: `Failed to fill protocol info 2 from key name`
- `0x180030efd`: `WSHGetWSAProtocolInfo`
- `0x180030f88`: `Caught exception while getting WSA protocol info`
- `0x18003100b`: `Failed to allocate space for protocolInfo2`
- `0x180031144`: `Failed to allocate space for protocolInfo2`
- `0x180031055`: `Caught exception when copying over protocol info 2`

## pseudocode

```c
__int64 __fastcall BuildWinsock2ProtocolList(
        __int64 a1,
        int a2,
        __int64 a3,
        const WCHAR *a4,
        _DWORD *a5,
        unsigned int a6,
        char **a7,
        DWORD *a8)
{
  char **v10; // r13
  char *v11; // rsi
  HMODULE v12; // rbx
  unsigned int v13; // eax
  unsigned int v14; // r14d
  const wchar_t *v15; // rdx
  unsigned int v16; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rsi
  size_t v19; // r14
  char *v20; // rax
  int v21; // edx
  int v22; // ecx
  int v23; // r8d
  DWORD v24; // edx
  unsigned int v25; // r8d
  size_t v26; // r12
  char *v27; // rax
  unsigned int v28; // r12d
  char *v29; // rcx
  _DWORD *v30; // r13
  unsigned int v31; // r14d
  _DWORD *v32; // r10
  int v33; // edx
  int v34; // r9d
  int v35; // r11d
  __int64 v36; // rcx
  int v37; // r8d
  char *v38; // rbx
  int v39; // eax
  char *v40; // r8
  char *v41; // rdx
  char *v42; // rcx
  __int64 v43; // rax
  wchar_t *v44; // rbx
  __int64 v45; // rcx
  DWORD v47; // [rsp+60h] [rbp-2B8h] BYREF
  unsigned int v48; // [rsp+64h] [rbp-2B4h]
  DWORD cSubKeys; // [rsp+68h] [rbp-2B0h] BYREF
  unsigned int v50; // [rsp+6Ch] [rbp-2ACh]
  const WCHAR *v51; // [rsp+70h] [rbp-2A8h]
  HMODULE v52; // [rsp+80h] [rbp-298h]
  _DWORD *v53; // [rsp+88h] [rbp-290h]
  DWORD cchName; // [rsp+90h] [rbp-288h] BYREF
  __int64 v55; // [rsp+98h] [rbp-280h]
  HKEY hKey; // [rsp+A0h] [rbp-278h] BYREF
  void *Src; // [rsp+A8h] [rbp-270h] BYREF
  char **v58; // [rsp+B0h] [rbp-268h]
  DWORD *v59; // [rsp+B8h] [rbp-260h]
  char *v60; // [rsp+C0h] [rbp-258h]
  WCHAR Name[256]; // [rsp+D0h] [rbp-248h] BYREF

  v55 = a3;
  v51 = a4;
  v53 = a5;
  v10 = a7;
  v58 = a7;
  v59 = a8;
  Src = 0;
  v47 = 0;
  cSubKeys = 0;
  cchName = 0;
  hKey = 0;
  if ( a2 )
  {
    v11 = 0;
    v12 = 0;
    v13 = OpenProviderParametersKey(a1, a3, &hKey);
    v14 = v13;
    if ( v13 )
    {
      v15 = L"Failed to open provider parameters key";
    }
    else
    {
      v13 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      v14 = v13;
      if ( !v13 )
      {
        if ( cSubKeys )
        {
          v47 = cSubKeys;
          v11 = (char *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
                          SockPrivateHeap,
                          0,
                          628 * cSubKeys);
          while ( (unsigned int)v12 < cSubKeys )
          {
            cchName = 256;
            RegEnumKeyExW(hKey, (DWORD)v12, Name, &cchName, 0, 0, 0, 0);
            v16 = FillProtocolInfo2FromKeyName(Name, hKey, &v11[628 * (unsigned int)v12]);
            v14 = v16;
            if ( v16 )
            {
              LogErrorWithProvider(v16, L"Failed to fill protocol info 2 from key name", a3);
              goto LABEL_14;
            }
            LODWORD(v12) = (_DWORD)v12 + 1;
          }
          *a8 = v47;
          *a7 = v11;
LABEL_14:
          v12 = 0;
        }
        else
        {
          *a8 = 0;
          *a7 = 0;
        }
        goto LABEL_64;
      }
      v15 = L"Failed to read number of subkeys";
    }
    LogErrorWithProvider(v13, v15, a3);
    goto LABEL_64;
  }
  v14 = 0;
  v48 = 0;
  Library = LoadLibraryExW(a4, 0, 0);
  v52 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WSHGetWSAProtocolInfo");
    if ( ProcAddress )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_S(1025, 38, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, a4);
      Src = 0;
      v47 = 0;
      v14 = ((__int64 (__fastcall *)(__int64, void **, DWORD *))ProcAddress)(a3, &Src, &v47);
      v48 = v14;
      v50 = v14;
      if ( !v14 && Src && v47 )
      {
        v19 = 628 * v47;
        v20 = (char *)((__int64 (__fastcall *)(HANDLE, _QWORD, size_t))SockAllocateHeapRoutine)(SockPrivateHeap, 0, v19);
        v11 = v20;
        v60 = v20;
        if ( v20 )
        {
          memcpy_0(v20, Src, v19);
          v14 = 0;
          v48 = 0;
          v50 = 0;
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_LS(v22, v21, v23, v47, (__int64)a4);
          *a7 = v11;
          *a8 = v47;
        }
        else
        {
          v14 = 8;
          LogErrorWithProvider(8, L"Failed to allocate space for protocolInfo2", a3);
        }
        goto LABEL_63;
      }
    }
  }
  v24 = a6;
  v47 = a6;
  v25 = 0;
  if ( a6 )
  {
    do
    {
      if ( (v53[10 * v25] & 0x10) != 0 )
        ++v24;
      ++v25;
    }
    while ( v25 < a6 );
    v47 = v24;
    v10 = v58;
  }
  if ( !(unsigned int)_o__wcsicmp(a3, L"TcpIp") )
    ++v47;
  v26 = 628 * v47;
  v27 = (char *)((__int64 (__fastcall *)(HANDLE, _QWORD, size_t))SockAllocateHeapRoutine)(SockPrivateHeap, 0, v26);
  v11 = v27;
  if ( !v27 )
  {
    v14 = 8;
    LogErrorWithProvider(8, L"Failed to allocate space for protocolInfo2", a3);
    *v10 = 0;
    *v59 = 0;
    goto LABEL_63;
  }
  memset_0(v27, 0, v26);
  v28 = 0;
  LODWORD(v55) = 0;
  if ( !a6 )
    goto LABEL_60;
  v29 = 0;
  v60 = 0;
  v30 = v53;
  v31 = 0;
  do
  {
    v32 = &v30[10 * (_QWORD)v29];
    v53 = v32;
    v33 = v32[1];
    v34 = v32[4];
    v35 = v32[5];
    v36 = 628LL * v31;
    *(_DWORD *)&v11[v36 + 72] = 2;
    *(_DWORD *)&v11[v36 + 76] = v33;
    *(_DWORD *)&v11[v36 + 80] = v32[2];
    *(_DWORD *)&v11[v36 + 84] = v32[3];
    *(_DWORD *)&v11[v36 + 88] = v34;
    *(_DWORD *)&v11[v36 + 92] = v35;
    *(_QWORD *)&v11[v36 + 96] = 0;
    *(_DWORD *)&v11[v36 + 104] = 0;
    *(_DWORD *)&v11[v36 + 108] = v32[6];
    *(_DWORD *)&v11[v36 + 16] = 0;
    v37 = *v32 & 0xFFF | 0x20000;
    v38 = &v11[v36];
    *(_DWORD *)&v11[v36] = v37;
    *(_QWORD *)&v11[v36 + 4] = 0;
    *(_DWORD *)&v11[v36 + 12] = 0;
    *(_DWORD *)&v11[v36 + 40] = 1;
    if ( v33 != 2 )
    {
      if ( v33 == 6 && v34 == 2 || v33 == 16 && v34 == 2 )
      {
        *((_DWORD *)v38 + 24) = 255;
        v39 = 0;
        goto LABEL_53;
      }
      if ( v33 == 17 && (!v35 || v35 == 0x80000000) )
      {
        *((_DWORD *)v38 + 23) = 0x80000000;
      }
      else
      {
        v39 = 0;
        if ( v33 != 7 )
          goto LABEL_53;
        *(_DWORD *)v38 = v37 | 0x180;
      }
    }
    *((_DWORD *)v38 + 4) = 8;
    v39 = 8;
LABEL_53:
    v40 = v38 + 116;
    if ( (*(_BYTE *)v32 & 0x10) != 0 )
    {
      *((_DWORD *)v38 + 4) = v39 | 3;
      BuildNewProtocolName(a3, v32, v40);
      v41 = &v11[628 * ++v31];
      v42 = v41;
      v43 = 4;
      do
      {
        *(_OWORD *)v42 = *(_OWORD *)v38;
        *((_OWORD *)v42 + 1) = *((_OWORD *)v38 + 1);
        *((_OWORD *)v42 + 2) = *((_OWORD *)v38 + 2);
        *((_OWORD *)v42 + 3) = *((_OWORD *)v38 + 3);
        *((_OWORD *)v42 + 4) = *((_OWORD *)v38 + 4);
        *((_OWORD *)v42 + 5) = *((_OWORD *)v38 + 5);
        *((_OWORD *)v42 + 6) = *((_OWORD *)v38 + 6);
        *((_OWORD *)v42 + 7) = *((_OWORD *)v38 + 7);
        v42 += 128;
        v38 += 128;
        --v43;
      }
      while ( v43 );
      *(_OWORD *)v42 = *(_OWORD *)v38;
      *((_OWORD *)v42 + 1) = *((_OWORD *)v38 + 1);
      *((_OWORD *)v42 + 2) = *((_OWORD *)v38 + 2);
      *((_OWORD *)v42 + 3) = *((_OWORD *)v38 + 3);
      *((_OWORD *)v42 + 4) = *((_OWORD *)v38 + 4);
      *((_OWORD *)v42 + 5) = *((_OWORD *)v38 + 5);
      *((_OWORD *)v42 + 6) = *((_OWORD *)v38 + 6);
      *((_DWORD *)v42 + 28) = *((_DWORD *)v38 + 28);
      *((_DWORD *)v41 + 4) &= ~2u;
      *((_DWORD *)v41 + 22) = 1;
      *((_DWORD *)v41 + 27) = 0;
      v44 = (wchar_t *)(v41 + 116);
      BuildNewProtocolName(a3, v53, v41 + 116);
      StringCbCatW(v44, 0x200u, L" [Pseudo Stream]");
    }
    else
    {
      BuildNewProtocolName(a3, v32, v40);
    }
    LODWORD(v55) = v55 + 1;
    ++v31;
    v29 = ++v60;
  }
  while ( (unsigned int)v55 < a6 );
  LODWORD(v51) = v31;
  v14 = v48;
  v10 = v58;
  v28 = (unsigned int)v51;
LABEL_60:
  if ( !(unsigned int)_o__wcsicmp(a3, L"TcpIp") )
  {
    v45 = 628LL * v28;
    *(_DWORD *)&v11[v45 + 72] = 2;
    *(_DWORD *)&v11[v45 + 76] = 2;
    *(_DWORD *)&v11[v45 + 80] = 16;
    *(_DWORD *)&v11[v45 + 84] = 16;
    *(_QWORD *)&v11[v45 + 88] = 3;
    *(_QWORD *)&v11[v45 + 96] = 255;
    *(_DWORD *)&v11[v45 + 104] = 0;
    *(_DWORD *)&v11[v45 + 108] = 65467;
    *(_DWORD *)&v11[v45 + 16] = 12;
    *(_QWORD *)&v11[v45] = 132617;
    *(_QWORD *)&v11[v45 + 8] = 0;
    *(_DWORD *)&v11[v45 + 40] = 1;
    StringCbPrintfW((STRSAFE_LPWSTR)&v11[v45 + 116], 0x200u, L"MSAFD %s [%s]", a3, L"RAW/IP");
  }
  *v10 = v11;
  *v59 = v47;
LABEL_63:
  v12 = v52;
LABEL_64:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v14 && v11 )
  {
    RtlFreeHeap(SockPrivateHeap, 0, v11);
    *v10 = 0;
  }
  if ( v12 )
    FreeLibrary(v12);
  return v14;
}

```

## disassembly

```asm
0x180030cdc  push    rbx
0x180030cde  push    rsi
0x180030cdf  push    rdi
0x180030ce0  push    r12
0x180030ce2  push    r13
0x180030ce4  push    r14
0x180030ce6  push    r15
0x180030ce8  sub     rsp, 2E0h
0x180030cef  mov     rax, cs:__security_cookie
0x180030cf6  xor     rax, rsp
0x180030cf9  mov     [rsp+318h+var_48], rax
0x180030d01  mov     rbx, r9
0x180030d04  mov     r15, r8
0x180030d07  mov     [rsp+318h+var_280], r8
0x180030d0f  mov     [rsp+318h+var_2A8], rbx
0x180030d14  mov     rax, [rsp+318h+arg_20]
0x180030d1c  mov     [rsp+318h+var_290], rax
0x180030d24  mov     r13, [rsp+318h+arg_30]
0x180030d2c  mov     [rsp+318h+var_268], r13
0x180030d34  mov     r12, [rsp+318h+arg_38]
0x180030d3c  mov     [rsp+318h+var_260], r12
0x180030d44  xor     edi, edi
0x180030d46  mov     [rsp+318h+Src], rdi
0x180030d4e  mov     [rsp+318h+var_2B8], edi
0x180030d52  mov     [rsp+318h+cSubKeys], edi
0x180030d56  mov     [rsp+318h+cchName], edi
0x180030d5d  mov     [rsp+318h+hKey], rdi
0x180030d65  test    edx, edx
0x180030d67  jz      loc_180030ED1
0x180030d6d  mov     esi, edi
0x180030d6f  mov     ebx, edi
0x180030d71  lea     r8, [rsp+318h+hKey]
0x180030d79  mov     rdx, r15
0x180030d7c  call    OpenProviderParametersKey
0x180030d81  mov     r14d, eax
0x180030d84  test    eax, eax
0x180030d86  jz      short loc_180030D9E
0x180030d88  lea     rdx, aFailedToOpenPr_1; "Failed to open provider parameters key"
0x180030d8f  mov     r8, r15
0x180030d92  mov     ecx, eax
0x180030d94  call    LogErrorWithProvider
0x180030d99  jmp     loc_1800314A5
0x180030d9e  mov     [rsp+318h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180030da3  mov     [rsp+318h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180030da8  mov     [rsp+318h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x180030dad  mov     [rsp+318h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x180030db2  mov     [rsp+318h+lpcValues], rdi; lpcValues
0x180030db7  mov     [rsp+318h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180030dbc  mov     [rsp+318h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x180030dc1  lea     rax, [rsp+318h+cSubKeys]
0x180030dc6  mov     [rsp+318h+lpcSubKeys], rax; lpcSubKeys
0x180030dcb  xor     r9d, r9d; lpReserved
0x180030dce  xor     r8d, r8d; lpcchClass
0x180030dd1  xor     edx, edx; lpClass
0x180030dd3  mov     rcx, [rsp+318h+hKey]; hKey
0x180030ddb  call    cs:__imp_RegQueryInfoKeyW
0x180030de2  nop     dword ptr [rax+rax+00h]
0x180030de7  mov     r14d, eax
0x180030dea  test    eax, eax
0x180030dec  jz      short loc_180030DF7
0x180030dee  lea     rdx, aFailedToReadNu; "Failed to read number of subkeys"
0x180030df5  jmp     short loc_180030D8F
0x180030df7  mov     eax, [rsp+318h+cSubKeys]
0x180030dfb  test    eax, eax
0x180030dfd  jnz     short loc_180030E0C
0x180030dff  mov     [r12], edi
0x180030e03  mov     [r13+0], rdi
0x180030e07  jmp     loc_1800314A5
0x180030e0c  mov     [rsp+318h+var_2B8], eax
0x180030e10  imul    r8d, eax, 274h
0x180030e17  xor     edx, edx
0x180030e19  mov     rcx, cs:SockPrivateHeap
0x180030e20  mov     rax, cs:SockAllocateHeapRoutine
0x180030e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e2c  mov     rsi, rax
0x180030e2f  cmp     ebx, [rsp+318h+cSubKeys]
0x180030e33  jnb     loc_180030EC3
0x180030e39  mov     [rsp+318h+cchName], 100h
0x180030e44  mov     [rsp+318h+lpcValues], rdi; lpftLastWriteTime
0x180030e49  mov     [rsp+318h+lpcbMaxClassLen], rdi; lpcchClass
0x180030e4e  mov     [rsp+318h+lpcbMaxSubKeyLen], rdi; lpClass
0x180030e53  mov     [rsp+318h+lpcSubKeys], rdi; lpReserved
0x180030e58  lea     r9, [rsp+318h+cchName]; lpcchName
0x180030e60  lea     r8, [rsp+318h+Name]; lpName
0x180030e68  mov     edx, ebx; dwIndex
0x180030e6a  mov     rcx, [rsp+318h+hKey]; hKey
0x180030e72  call    cs:__imp_RegEnumKeyExW
0x180030e79  nop     dword ptr [rax+rax+00h]
0x180030e7e  mov     eax, ebx
0x180030e80  imul    r8, rax, 274h
0x180030e87  add     r8, rsi; void *
0x180030e8a  mov     rdx, [rsp+318h+hKey]; hKey
0x180030e92  lea     rcx, [rsp+318h+Name]; lpSubKey
0x180030e9a  call    FillProtocolInfo2FromKeyName
0x180030e9f  mov     r14d, eax
0x180030ea2  test    eax, eax
0x180030ea4  jnz     short loc_180030EAA
0x180030ea6  inc     ebx
0x180030ea8  jmp     short loc_180030E2F
0x180030eaa  mov     r8, r15
0x180030ead  lea     rdx, aFailedToFillPr; "Failed to fill protocol info 2 from key"...
0x180030eb4  mov     ecx, eax
0x180030eb6  call    LogErrorWithProvider
0x180030ebb  mov     rbx, rdi
0x180030ebe  jmp     loc_1800314A5
0x180030ec3  mov     eax, [rsp+318h+var_2B8]
0x180030ec7  mov     [r12], eax
0x180030ecb  mov     [r13+0], rsi
0x180030ecf  jmp     short loc_180030EBB
0x180030ed1  mov     r14d, edi
0x180030ed4  mov     [rsp+318h+var_2B4], edi
0x180030ed8  xor     r8d, r8d; dwFlags
0x180030edb  xor     edx, edx; hFile
0x180030edd  mov     rcx, rbx; lpLibFileName
0x180030ee0  call    cs:__imp_LoadLibraryExW
0x180030ee7  nop     dword ptr [rax+rax+00h]
0x180030eec  mov     [rsp+318h+var_298], rax
0x180030ef4  test    rax, rax
0x180030ef7  jz      loc_1800310B0
0x180030efd  lea     rdx, aWshgetwsaproto; "WSHGetWSAProtocolInfo"
0x180030f04  mov     rcx, rax; hModule
0x180030f07  call    cs:__imp_GetProcAddress
0x180030f0e  nop     dword ptr [rax+rax+00h]
0x180030f13  mov     rsi, rax
0x180030f16  test    rax, rax
0x180030f19  jz      loc_1800310B0
0x180030f1f  test    byte ptr cs:xmmword_180063D60, 2
0x180030f26  jz      short loc_180030F41
0x180030f28  mov     edx, 26h ; '&'
0x180030f2d  mov     ecx, 401h
0x180030f32  mov     r9, rbx
0x180030f35  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180030f3c  call    WPP_SF_S
0x180030f41  mov     [rsp+318h+Src], rdi
0x180030f49  mov     [rsp+318h+var_2B8], edi
0x180030f4d  lea     r8, [rsp+318h+var_2B8]
0x180030f52  lea     rdx, [rsp+318h+Src]
0x180030f5a  mov     rcx, r15
0x180030f5d  mov     rax, rsi
0x180030f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f65  mov     r14d, eax
0x180030f68  mov     [rsp+318h+var_2B4], eax
0x180030f6c  mov     [rsp+318h+var_2AC], eax
0x180030f70  jmp     short loc_180030FAD
0x180030f72  mov     r14d, eax
0x180030f75  mov     [rsp+318h+var_2B4], eax
0x180030f79  mov     [rsp+318h+var_2AC], eax
0x180030f7d  mov     r15, [rsp+318h+var_280]
0x180030f85  mov     r8, r15
0x180030f88  lea     rdx, aCaughtExceptio_1; "Caught exception while getting WSA prot"...
0x180030f8f  mov     ecx, eax
0x180030f91  call    LogErrorWithProvider
0x180030f96  xor     edi, edi
0x180030f98  mov     rbx, [rsp+318h+var_2A8]
0x180030f9d  mov     r13, [rsp+318h+var_268]
0x180030fa5  mov     r12, [rsp+318h+var_260]
0x180030fad  test    r14d, r14d
0x180030fb0  jnz     loc_1800310B0
0x180030fb6  cmp     [rsp+318h+Src], rdi
0x180030fbe  jz      loc_1800310B0
0x180030fc4  cmp     [rsp+318h+var_2B8], edi
0x180030fc8  jbe     loc_1800310B0
0x180030fce  imul    eax, [rsp+318h+var_2B8], 274h
0x180030fd6  mov     r14d, eax
0x180030fd9  mov     r8d, eax
0x180030fdc  xor     edx, edx
0x180030fde  mov     rcx, cs:SockPrivateHeap
0x180030fe5  mov     rax, cs:SockAllocateHeapRoutine
0x180030fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ff1  mov     rsi, rax
0x180030ff4  mov     [rsp+318h+var_258], rax
0x180030ffc  test    rax, rax
0x180030fff  jnz     short loc_18003101F
0x180031001  lea     r12d, [rax+8]
0x180031005  mov     r14d, r12d
0x180031008  mov     r8, r15
0x18003100b  lea     rdx, aFailedToAlloca_8; "Failed to allocate space for protocolIn"...
0x180031012  mov     ecx, r12d
0x180031015  call    LogErrorWithProvider
0x18003101a  jmp     loc_18003149D
0x18003101f  mov     r8, r14; Size
0x180031022  mov     rdx, [rsp+318h+Src]; Src
0x18003102a  mov     rcx, rax; void *
0x18003102d  call    memcpy_0
0x180031032  mov     r14d, edi
0x180031035  mov     [rsp+318h+var_2B4], edi
0x180031039  mov     [rsp+318h+var_2AC], edi
0x18003103d  jmp     short loc_180031082
0x18003103f  mov     r14d, eax
0x180031042  mov     [rsp+318h+var_2B4], eax
0x180031046  mov     [rsp+318h+var_2AC], eax
0x18003104a  mov     r15, [rsp+318h+var_280]
0x180031052  mov     r8, r15
0x180031055  lea     rdx, aCaughtExceptio; "Caught exception when copying over prot"...
0x18003105c  mov     ecx, eax
0x18003105e  call    LogErrorWithProvider
0x180031063  xor     edi, edi
0x180031065  mov     rsi, [rsp+318h+var_258]
0x18003106d  mov     rbx, [rsp+318h+var_2A8]
0x180031072  mov     r13, [rsp+318h+var_268]
0x18003107a  mov     r12, [rsp+318h+var_260]
0x180031082  test    r14d, r14d
0x180031085  jnz     short loc_1800310B0
0x180031087  test    byte ptr cs:xmmword_180063D60, 2
0x18003108e  jz      short loc_18003109F
0x180031090  mov     [rsp+318h+lpcSubKeys], rbx
0x180031095  mov     r9d, [rsp+318h+var_2B8]
0x18003109a  call    WPP_SF_LS
0x18003109f  mov     [r13+0], rsi
0x1800310a3  mov     eax, [rsp+318h+var_2B8]
0x1800310a7  mov     [r12], eax
0x1800310ab  jmp     loc_18003149D
0x1800310b0  mov     ebx, [rsp+318h+arg_28]
0x1800310b7  mov     edx, ebx
0x1800310b9  mov     [rsp+318h+var_2B8], ebx
0x1800310bd  mov     r8d, edi
0x1800310c0  test    ebx, ebx
0x1800310c2  jz      short loc_1800310F1
0x1800310c4  mov     r13, [rsp+318h+var_290]
0x1800310cc  mov     eax, r8d
0x1800310cf  lea     rcx, [rax+rax*4]
0x1800310d3  test    byte ptr [r13+rcx*8+0], 10h
0x1800310d9  jz      short loc_1800310DD
0x1800310db  inc     edx
0x1800310dd  inc     r8d
0x1800310e0  cmp     r8d, ebx
0x1800310e3  jb      short loc_1800310CC
0x1800310e5  mov     [rsp+318h+var_2B8], edx
0x1800310e9  mov     r13, [rsp+318h+var_268]
0x1800310f1  lea     rdx, aTcpip_0; "TcpIp"
0x1800310f8  mov     rcx, r15
0x1800310fb  call    cs:__imp__o__wcsicmp
0x180031102  nop     dword ptr [rax+rax+00h]
0x180031107  test    eax, eax
0x180031109  jnz     short loc_18003110F
0x18003110b  inc     [rsp+318h+var_2B8]
0x18003110f  imul    eax, [rsp+318h+var_2B8], 274h
0x180031117  mov     r12d, eax
0x18003111a  mov     r8d, eax
0x18003111d  xor     edx, edx
0x18003111f  mov     rcx, cs:SockPrivateHeap
0x180031126  mov     rax, cs:SockAllocateHeapRoutine
0x18003112d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031132  mov     rsi, rax
0x180031135  test    rax, rax
0x180031138  jnz     short loc_180031166
0x18003113a  lea     r12d, [rax+8]
0x18003113e  mov     r14d, r12d
0x180031141  mov     r8, r15
0x180031144  lea     rdx, aFailedToAlloca_8; "Failed to allocate space for protocolIn"...
0x18003114b  mov     ecx, r12d
0x18003114e  call    LogErrorWithProvider
0x180031153  mov     [r13+0], rdi
0x180031157  mov     rcx, [rsp+318h+var_260]
0x18003115f  mov     [rcx], edi
0x180031161  jmp     loc_18003149D
0x180031166  mov     r8, r12; Size
0x180031169  xor     edx, edx; Val
0x18003116b  mov     rcx, rsi; void *
0x18003116e  call    memset_0
0x180031173  mov     r12d, edi
0x180031176  mov     dword ptr [rsp+318h+var_280], edi
0x18003117d  test    ebx, ebx
0x18003117f  jz      loc_1800313DD
0x180031185  mov     rcx, rdi
0x180031188  mov     [rsp+318h+var_258], rcx
0x180031190  mov     r12d, 8
0x180031196  mov     r13, [rsp+318h+var_290]
0x18003119e  mov     r14d, edi
0x1800311a1  lea     rax, [rcx+rcx*4]
0x1800311a5  lea     r10, ds:0[rax*8]
0x1800311ad  add     r10, r13
0x1800311b0  mov     [rsp+318h+var_290], r10
0x1800311b8  mov     edx, [r10+4]
0x1800311bc  mov     r9d, [r10+10h]
0x1800311c0  mov     r11d, [r10+14h]
0x1800311c4  mov     eax, r14d
0x1800311c7  imul    rcx, rax, 274h
0x1800311ce  mov     dword ptr [rsi+rcx+48h], 2
0x1800311d6  mov     [rsi+rcx+4Ch], edx
0x1800311da  mov     eax, [r10+8]
0x1800311de  mov     [rsi+rcx+50h], eax
0x1800311e2  mov     eax, [r10+0Ch]
0x1800311e6  mov     [rsi+rcx+54h], eax
0x1800311ea  mov     [rsi+rcx+58h], r9d
0x1800311ef  mov     [rsi+rcx+5Ch], r11d
0x1800311f4  mov     qword ptr [rsi+rcx+60h], 0
0x1800311fd  mov     [rsi+rcx+68h], edi
0x180031201  mov     eax, [r10+18h]
0x180031205  mov     [rsi+rcx+6Ch], eax
0x180031209  mov     [rsi+rcx+10h], edi
0x18003120d  mov     r8d, [r10]
0x180031210  and     r8d, 0FFFh
0x180031217  bts     r8d, 11h
0x18003121c  lea     rbx, [rcx+rsi]
0x180031220  mov     [rbx], r8d
0x180031223  mov     qword ptr [rsi+rcx+4], 0
0x18003122c  mov     [rsi+rcx+0Ch], edi
0x180031230  mov     dword ptr [rsi+rcx+28h], 1
0x180031238  cmp     edx, 2
  ... truncated ...
```
