# getInnerConnectionProperties(IXMLDOMNodeList *,ulong,ulong *,_PEAP_CONN_PROPERTIES *,uchar * *,ulong *)

- ea: `0x18000e380`
- end: `0x18000eb08`
- name: `?getInnerConnectionProperties@@YAKPEAUIXMLDOMNodeList@@KPEAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEAE1@Z`
- size: `1928`
- prototype: `unsigned int __fastcall(struct IXMLDOMNodeList *, unsigned int, unsigned int *, struct _PEAP_CONN_PROPERTIES *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000d660`

## callees

- `0x180005010`
- `0x180007d00`
- `0x18000cb70`
- `0x18000e380`
- `0x180010140`
- `0x1800201a0`
- `0x180020d80`
- `0x180061f9c`
- `0x180082010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000e4a8`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000e4a8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e820`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e820`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e879`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e8d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e879`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e8d2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ea2e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ea2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e88d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e88d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e4ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e6ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e778`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e9b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e4ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e6ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e778`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e9b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e804`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ea42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e804`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ea42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e7f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e7f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e66c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e66c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e6e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e736`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e6e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e736`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000e75f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000e79b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000e75f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000e79b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e425`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e425`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e472`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea83`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eab8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e472`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea83`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eab8`

## string_xrefs

- `0x18000e86f`: `RasEapCreateConnectionProperties`
- `0x18000e6d7`: `ConfigUIPath`
- `0x18000e72c`: `ConfigUIPath`
- `0x18000e55a`: `System\CurrentControlSet\Services\Rasman\PPP\EAP`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall getInnerConnectionProperties(
        struct IXMLDOMNodeList *a1,
        unsigned int a2,
        unsigned int *a3,
        struct _PEAP_CONN_PROPERTIES *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  WCHAR *v6; // rsi
  wchar_t *v7; // r12
  __int64 v8; // rdi
  DWORD LastError; // ebx
  const wchar_t *v10; // rax
  int v11; // ecx
  OLECHAR *v12; // rbx
  WCHAR *v13; // r15
  __int64 v14; // rax
  SIZE_T v15; // rbx
  WCHAR *v16; // rax
  WCHAR *v17; // r13
  unsigned __int64 v18; // rbx
  __int64 v19; // r10
  __int64 v20; // rcx
  const WCHAR *v21; // r8
  unsigned __int64 v22; // rdx
  WCHAR v23; // r9
  WCHAR *v24; // rcx
  unsigned __int64 v25; // rcx
  WCHAR *v26; // rax
  unsigned __int64 v27; // rdx
  const unsigned __int16 *v28; // rcx
  unsigned __int64 v29; // r8
  WCHAR *v30; // rax
  unsigned __int16 v31; // dx
  WCHAR *v32; // rcx
  size_t v33; // rcx
  WCHAR *v34; // rax
  HKEY v35; // r15
  BYTE *v36; // rdi
  HMODULE Library; // rax
  HMODULE v38; // rdi
  DWORD v39; // eax
  FARPROC ProcAddress; // rbx
  struct _EAPTLS_CONTROL_BLOCK *v41; // rcx
  __int64 v42; // rdx
  void (*v43)(void); // rsi
  unsigned int FirstEntryConnProp; // eax
  char *v45; // r9
  unsigned int v46; // r13d
  unsigned __int8 *v47; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-69h]
  int phkResulta; // [rsp+20h] [rbp-69h]
  unsigned int uBytes; // [rsp+40h] [rbp-49h] BYREF
  DWORD uBytes_4; // [rsp+44h] [rbp-45h] BYREF
  unsigned int v53; // [rsp+48h] [rbp-41h]
  WCHAR *v54; // [rsp+50h] [rbp-39h]
  __int64 v55; // [rsp+58h] [rbp-31h] BYREF
  void *Source; // [rsp+60h] [rbp-29h] BYREF
  __int64 v57; // [rsp+68h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-19h] BYREF
  struct _PEAP_ENTRY_CONN_PROPERTIES *v59; // [rsp+78h] [rbp-11h] BYREF
  STRSAFE_PCNZWCH v60; // [rsp+80h] [rbp-9h]
  STRSAFE_PCNZWCH pszSrc; // [rsp+E0h] [rbp+57h] BYREF
  unsigned int v62; // [rsp+E8h] [rbp+5Fh]
  unsigned int *v63; // [rsp+F0h] [rbp+67h]
  struct _PEAP_CONN_PROPERTIES *v64; // [rsp+F8h] [rbp+6Fh]

  v64 = a4;
  v63 = a3;
  v62 = a2;
  v6 = 0;
  v59 = 0;
  Source = 0;
  uBytes = 0;
  v55 = 0;
  v57 = 0;
  v7 = 0;
  v60 = 0;
  *a6 = 0;
  *a5 = 0;
  *a3 = 0;
  ((void (__fastcall *)(struct IXMLDOMNodeList *, __int64 *))a1->lpVtbl->nextNode)(a1, &v55);
  v8 = v55;
  if ( !v55 )
  {
    LastError = 0;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    goto LABEL_88;
  }
  v10 = SysAllocString(L"baseeapconnectionpropertiesv1:Type[1]");
  v12 = (OLECHAR *)v10;
  pszSrc = v10;
  if ( !v10 )
    ATL::AtlThrowImpl(v11);
  if ( (*(unsigned int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v8 + 296LL))(v8, v10, &v57)
    || !v57 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        L"baseeapconnectionpropertiesv1:Type[1]");
    SysFreeString(v12);
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    goto LABEL_87;
  }
  SysFreeString(v12);
  pszSrc = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, STRSAFE_PCNZWCH *))(*(_QWORD *)v57 + 208LL))(v57, &pszSrc) )
  {
LABEL_87:
    LastError = 87;
    goto LABEL_88;
  }
  v13 = 0;
  v53 = _o__wtol(pszSrc);
  v7 = (wchar_t *)pszSrc;
  v60 = pszSrc;
  hKey = 0;
  v14 = -1;
  do
    ++v14;
  while ( pszSrc[v14] );
  v15 = 2 * (int)v14 + 102;
  v16 = (WCHAR *)LocalAlloc(0x40u, v15);
  v17 = v16;
  if ( !v16 )
  {
    LastError = 14;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 248, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    goto LABEL_81;
  }
  v18 = v15 >> 1;
  if ( !v18 )
    goto LABEL_34;
  v19 = 2147483646;
  if ( v18 > 0x7FFFFFFF )
  {
    *v16 = 0;
    goto LABEL_40;
  }
  v20 = 2147483646;
  v21 = L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP";
  v22 = v18;
  do
  {
    if ( !v20 )
      break;
    v23 = *v21;
    if ( !*v21 )
      break;
    ++v21;
    *v16++ = v23;
    --v20;
    --v22;
  }
  while ( v22 );
  v24 = v16 - 1;
  if ( v22 )
    v24 = v16;
  *v24 = 0;
  v25 = v18;
  v26 = v17;
  do
  {
    if ( !*v26 )
      break;
    ++v26;
    --v25;
  }
  while ( v25 );
  v27 = v18 - v25;
  if ( v25 )
  {
    v28 = L"\\";
    v29 = v18 - v27;
    v30 = &v17[v27];
    if ( v18 != v27 )
    {
      do
      {
        if ( !v19 )
          break;
        v31 = *v28;
        if ( !*v28 )
          break;
        ++v28;
        *v30++ = v31;
        --v19;
        --v29;
      }
      while ( v29 );
    }
    v32 = v30 - 1;
    if ( v29 )
      v32 = v30;
    *v32 = 0;
    v33 = v18;
  }
  else
  {
LABEL_34:
    v33 = v18;
    if ( !v18 )
      goto LABEL_40;
  }
  v34 = v17;
  do
  {
    if ( !*v34 )
      break;
    ++v34;
    --v33;
  }
  while ( v33 );
  if ( v33 )
    StringCopyWorkerW(&v17[v18 - v33], v33, (size_t *)(v18 - v33), v7, (size_t)phkResult);
LABEL_40:
  LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v17, 0, 0x20019u, &hKey);
  if ( !LastError )
  {
    v35 = hKey;
    uBytes_4 = 0;
    LODWORD(pszSrc) = 0;
    v36 = 0;
    v54 = 0;
    LastError = RegQueryValueExW(hKey, L"ConfigUIPath", 0, &uBytes_4, 0, (LPDWORD)&pszSrc);
    if ( LastError )
    {
      v13 = 0;
    }
    else
    {
      v36 = (BYTE *)LocalAlloc(0x40u, (unsigned int)pszSrc);
      if ( !v36 )
        goto LABEL_51;
      LastError = RegQueryValueExW(v35, L"ConfigUIPath", 0, &uBytes_4, v36, (LPDWORD)&pszSrc);
      if ( LastError )
      {
LABEL_52:
        v13 = v54;
        goto LABEL_53;
      }
      *(_WORD *)&v36[2 * ((unsigned __int64)(unsigned int)pszSrc >> 1) - 2] = 0;
      LODWORD(pszSrc) = ExpandEnvironmentStringsW((LPCWSTR)v36, 0, 0);
      v6 = (WCHAR *)LocalAlloc(0x40u, 2LL * (unsigned int)pszSrc);
      if ( !v6 )
      {
LABEL_51:
        LastError = 14;
        goto LABEL_52;
      }
      *v6 = 0;
      LODWORD(pszSrc) = ExpandEnvironmentStringsW((LPCWSTR)v36, v6, (DWORD)pszSrc);
      if ( !(_DWORD)pszSrc )
      {
        LastError = GetLastError();
        goto LABEL_52;
      }
      v13 = v6;
      v6 = 0;
    }
LABEL_53:
    LocalFree(v36);
    LocalFree(v6);
    RegCloseKey(hKey);
    goto LABEL_54;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 249, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v17);
LABEL_54:
  LocalFree(v17);
  if ( LastError )
    goto LABEL_81;
  Library = LoadLibraryExW(v13, 0, 0);
  v38 = Library;
  if ( !Library )
  {
    v39 = GetLastError();
    LastError = v39;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 235, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v39);
    goto LABEL_81;
  }
  ProcAddress = GetProcAddress(Library, "RasEapCreateConnectionProperties");
  if ( ProcAddress )
  {
    v43 = (void (*)(void))GetProcAddress(v38, "RasEapFreeMemory");
    if ( !v43 )
    {
      LastError = GetLastError();
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_80;
      v42 = 237;
      goto LABEL_61;
    }
    if ( v64 )
    {
      FirstEntryConnProp = PeapGetFirstEntryConnProp(v64, &v59);
      if ( !FirstEntryConnProp && v59 )
      {
        v45 = (char *)v59 + 12;
        phkResulta = *((_DWORD *)v59 + 1) - 15;
        goto LABEL_72;
      }
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          238,
          WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
          FirstEntryConnProp);
    }
    phkResulta = 0;
    v45 = 0;
LABEL_72:
    v46 = v53;
    LastError = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, char *, int, void **, unsigned int *))ProcAddress)(
                  v53,
                  v62,
                  v55,
                  v45,
                  phkResulta,
                  &Source,
                  &uBytes);
    if ( !LastError && uBytes )
    {
      v47 = (unsigned __int8 *)LocalAlloc(0x40u, uBytes);
      *a5 = v47;
      if ( v47 )
      {
        memcpy_s_0(v47, uBytes, Source, uBytes);
        *a6 = uBytes;
        *v63 = v46;
      }
      else
      {
        LastError = 14;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
      }
    }
    if ( Source )
      v43();
    goto LABEL_80;
  }
  LastError = GetLastError();
  v41 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v42 = 236;
LABEL_61:
    WPP_SF_S(*((_QWORD *)v41 + 2), v42, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v13);
  }
LABEL_80:
  FreeLibrary(v38);
LABEL_81:
  if ( v13 )
    LocalFree(v13);
LABEL_88:
  SysFreeString(v7);
  if ( v57 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  return LastError;
}

```

## disassembly

```asm
0x18000e380  mov     [rsp-8+arg_18], r9
0x18000e385  mov     [rsp-8+arg_10], r8
0x18000e38a  mov     [rsp-8+arg_8], edx
0x18000e38e  push    rbp
0x18000e38f  push    rbx
0x18000e390  push    rsi
0x18000e391  push    rdi
0x18000e392  push    r12
0x18000e394  push    r13
0x18000e396  push    r14
0x18000e398  push    r15
0x18000e39a  lea     rbp, [rsp-0Fh]
0x18000e39f  sub     rsp, 98h
0x18000e3a6  xor     esi, esi
0x18000e3a8  mov     [rbp+47h+var_58], rsi
0x18000e3ac  mov     [rbp+47h+Source], rsi
0x18000e3b0  mov     dword ptr [rbp+47h+uBytes], esi
0x18000e3b3  mov     [rbp+47h+var_78], rsi
0x18000e3b7  mov     [rbp+47h+var_68], rsi
0x18000e3bb  mov     r12d, esi
0x18000e3be  mov     [rbp+47h+var_50], rsi
0x18000e3c2  mov     rdx, [rbp+47h+arg_28]
0x18000e3c6  mov     [rdx], esi
0x18000e3c8  mov     rdx, [rbp+47h+arg_20]
0x18000e3cc  mov     [rdx], rsi
0x18000e3cf  mov     [r8], esi
0x18000e3d2  mov     rax, [rcx]
0x18000e3d5  lea     rdx, [rbp+47h+var_78]
0x18000e3d9  mov     rax, [rax+48h]
0x18000e3dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3e2  mov     rdi, [rbp+47h+var_78]
0x18000e3e6  test    rdi, rdi
0x18000e3e9  jnz     short loc_18000E41E
0x18000e3eb  mov     ebx, esi
0x18000e3ed  lea     r14, WPP_GLOBAL_Control
0x18000e3f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3fb  cmp     rcx, r14
0x18000e3fe  jz      loc_18000EAB5
0x18000e404  mov     edx, 0E9h
0x18000e409  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000e410  mov     rcx, [rcx+10h]
0x18000e414  call    WPP_SF_
0x18000e419  jmp     loc_18000EAB5
0x18000e41e  lea     rcx, aBaseeapconnect_0; "baseeapconnectionpropertiesv1:Type[1]"
0x18000e425  call    cs:__imp_SysAllocString
0x18000e42c  nop     dword ptr [rax+rax+00h]
0x18000e431  mov     rbx, rax
0x18000e434  mov     [rbp+47h+pszSrc], rax
0x18000e438  test    rax, rax
0x18000e43b  jnz     short loc_18000E443
0x18000e43d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000e443  mov     rax, [rdi]
0x18000e446  lea     r8, [rbp+47h+var_68]
0x18000e44a  mov     rdx, rbx
0x18000e44d  mov     rcx, rdi
0x18000e450  mov     rax, [rax+128h]
0x18000e457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e45c  test    eax, eax
0x18000e45e  jnz     loc_18000EA50
0x18000e464  cmp     [rbp+47h+var_68], 0
0x18000e469  jz      loc_18000EA50
0x18000e46f  mov     rcx, rbx; bstrString
0x18000e472  call    cs:__imp_SysFreeString
0x18000e479  nop     dword ptr [rax+rax+00h]
0x18000e47e  mov     rcx, [rbp+47h+var_68]
0x18000e482  mov     [rbp+47h+pszSrc], rsi
0x18000e486  mov     rax, [rcx]
0x18000e489  lea     rdx, [rbp+47h+pszSrc]
0x18000e48d  mov     rax, [rax+0D0h]
0x18000e494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e499  test    eax, eax
0x18000e49b  jnz     loc_18000EAB0
0x18000e4a1  mov     r15, rsi
0x18000e4a4  mov     rcx, [rbp+47h+pszSrc]
0x18000e4a8  call    cs:__imp__o__wtol
0x18000e4af  nop     dword ptr [rax+rax+00h]
0x18000e4b4  mov     [rbp+47h+var_88], eax
0x18000e4b7  mov     r12, [rbp+47h+pszSrc]
0x18000e4bb  mov     [rbp+47h+var_50], r12
0x18000e4bf  mov     [rbp+47h+hKey], rsi
0x18000e4c3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000e4ca  nop     word ptr [rax+rax+00h]
0x18000e4d0  lea     rax, [rax+1]
0x18000e4d4  cmp     [r12+rax*2], r15w
0x18000e4d9  jnz     short loc_18000E4D0
0x18000e4db  lea     eax, ds:66h[rax*2]
0x18000e4e2  movsxd  rbx, eax
0x18000e4e5  mov     rdx, rbx; uBytes
0x18000e4e8  mov     ecx, 40h ; '@'; uFlags
0x18000e4ed  call    cs:__imp_LocalAlloc
0x18000e4f4  nop     dword ptr [rax+rax+00h]
0x18000e4f9  mov     r13, rax
0x18000e4fc  test    rax, rax
0x18000e4ff  jnz     short loc_18000E537
0x18000e501  mov     ebx, 0Eh
0x18000e506  lea     r14, WPP_GLOBAL_Control
0x18000e50d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e514  cmp     rcx, r14
0x18000e517  jz      loc_18000EA3A
0x18000e51d  mov     edx, 0F8h
0x18000e522  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000e529  mov     rcx, [rcx+10h]
0x18000e52d  call    WPP_SF_
0x18000e532  jmp     loc_18000EA3A
0x18000e537  shr     rbx, 1
0x18000e53a  jz      loc_18000E604
0x18000e540  mov     r10d, 7FFFFFFEh
0x18000e546  cmp     rbx, 7FFFFFFFh
0x18000e54d  jbe     short loc_18000E557
0x18000e54f  mov     [rax], si
0x18000e552  jmp     loc_18000E650
0x18000e557  mov     rcx, r10
0x18000e55a  lea     r8, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\Ra"...
0x18000e561  mov     rdx, rbx
0x18000e564  test    rcx, rcx
0x18000e567  jz      short loc_18000E588
0x18000e569  movzx   r9d, word ptr [r8]
0x18000e56d  test    r9w, r9w
0x18000e571  jz      short loc_18000E588
0x18000e573  add     r8, 2
0x18000e577  mov     [rax], r9w
0x18000e57b  add     rax, 2
0x18000e57f  dec     rcx
0x18000e582  sub     rdx, 1
0x18000e586  jnz     short loc_18000E564
0x18000e588  lea     rcx, [rax-2]
0x18000e58c  test    rdx, rdx
0x18000e58f  cmovnz  rcx, rax
0x18000e593  mov     [rcx], si
0x18000e596  mov     r8, rbx
0x18000e599  mov     rcx, rbx
0x18000e59c  mov     rax, r13
0x18000e59f  nop
0x18000e5a0  cmp     [rax], r15w
0x18000e5a4  jz      short loc_18000E5B0
0x18000e5a6  add     rax, 2
0x18000e5aa  sub     rcx, 1
0x18000e5ae  jnz     short loc_18000E5A0
0x18000e5b0  mov     rdx, r8
0x18000e5b3  sub     rdx, rcx
0x18000e5b6  test    rcx, rcx
0x18000e5b9  cmovz   rdx, rsi
0x18000e5bd  jz      short loc_18000E604
0x18000e5bf  lea     rcx, asc_180087834; "\\"
0x18000e5c6  sub     r8, rdx
0x18000e5c9  lea     rax, [r13+rdx*2+0]
0x18000e5ce  jz      short loc_18000E5F1
0x18000e5d0  test    r10, r10
0x18000e5d3  jz      short loc_18000E5F1
0x18000e5d5  movzx   edx, word ptr [rcx]
0x18000e5d8  test    dx, dx
0x18000e5db  jz      short loc_18000E5F1
0x18000e5dd  add     rcx, 2
0x18000e5e1  mov     [rax], dx
0x18000e5e4  add     rax, 2
0x18000e5e8  dec     r10
0x18000e5eb  sub     r8, 1
0x18000e5ef  jnz     short loc_18000E5D0
0x18000e5f1  lea     rcx, [rax-2]
0x18000e5f5  test    r8, r8
0x18000e5f8  cmovnz  rcx, rax
0x18000e5fc  mov     [rcx], si
0x18000e5ff  mov     rcx, rbx
0x18000e602  jmp     short loc_18000E615
0x18000e604  mov     rcx, rbx
0x18000e607  test    rbx, rbx
0x18000e60a  jz      short loc_18000E650
0x18000e60c  cmp     rbx, 7FFFFFFFh
0x18000e613  ja      short loc_18000E650
0x18000e615  mov     rax, r13
0x18000e618  cmp     [rax], r15w
0x18000e61c  jz      short loc_18000E628
0x18000e61e  add     rax, 2
0x18000e622  sub     rcx, 1
0x18000e626  jnz     short loc_18000E618
0x18000e628  mov     r8, rbx
0x18000e62b  sub     r8, rcx
0x18000e62e  test    rcx, rcx
0x18000e631  cmovz   r8, rsi; pcchNewDestLength
0x18000e635  jz      short loc_18000E650
0x18000e637  sub     rbx, r8
0x18000e63a  lea     rcx, ds:0[r8*2]
0x18000e642  add     rcx, r13; pszDest
0x18000e645  mov     r9, r12; pszSrc
0x18000e648  mov     rdx, rbx; cchDest
0x18000e64b  call    StringCopyWorkerW
0x18000e650  lea     rax, [rbp+47h+hKey]
0x18000e654  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18000e659  mov     r9d, 20019h; samDesired
0x18000e65f  xor     r8d, r8d; ulOptions
0x18000e662  mov     rdx, r13; lpSubKey
0x18000e665  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e66c  call    cs:__imp_RegOpenKeyExW
0x18000e673  nop     dword ptr [rax+rax+00h]
0x18000e678  mov     ebx, eax
0x18000e67a  lea     r14, WPP_GLOBAL_Control
0x18000e681  test    eax, eax
0x18000e683  jz      short loc_18000E6B2
0x18000e685  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e68c  cmp     rcx, r14
0x18000e68f  jz      loc_18000E801
0x18000e695  mov     edx, 0F9h
0x18000e69a  mov     r9, r13
0x18000e69d  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000e6a4  mov     rcx, [rcx+10h]
0x18000e6a8  call    WPP_SF_S
0x18000e6ad  jmp     loc_18000E801
0x18000e6b2  mov     r15, [rbp+47h+hKey]
0x18000e6b6  mov     dword ptr [rbp+47h+uBytes+4], esi
0x18000e6b9  mov     dword ptr [rbp+47h+pszSrc], esi
0x18000e6bc  xor     edi, edi
0x18000e6be  mov     [rbp+47h+var_80], rdi
0x18000e6c2  lea     rax, [rbp+47h+pszSrc]
0x18000e6c6  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18000e6cb  mov     [rsp+0D0h+phkResult], rdi; lpData
0x18000e6d0  lea     r9, [rbp+47h+uBytes+4]; lpType
0x18000e6d4  xor     r8d, r8d; lpReserved
0x18000e6d7  lea     rdx, aConfiguipath; "ConfigUIPath"
0x18000e6de  mov     rcx, r15; hKey
0x18000e6e1  call    cs:__imp_RegQueryValueExW
0x18000e6e8  nop     dword ptr [rax+rax+00h]
0x18000e6ed  mov     ebx, eax
0x18000e6ef  test    eax, eax
0x18000e6f1  jnz     loc_18000E7C5
0x18000e6f7  mov     edx, dword ptr [rbp+47h+pszSrc]; uBytes
0x18000e6fa  mov     ecx, 40h ; '@'; uFlags
0x18000e6ff  call    cs:__imp_LocalAlloc
0x18000e706  nop     dword ptr [rax+rax+00h]
0x18000e70b  mov     rdi, rax
0x18000e70e  test    rax, rax
0x18000e711  jz      loc_18000E7CA
0x18000e717  lea     rax, [rbp+47h+pszSrc]
0x18000e71b  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18000e720  mov     [rsp+0D0h+phkResult], rdi; lpData
0x18000e725  lea     r9, [rbp+47h+uBytes+4]; lpType
0x18000e729  xor     r8d, r8d; lpReserved
0x18000e72c  lea     rdx, aConfiguipath; "ConfigUIPath"
0x18000e733  mov     rcx, r15; hKey
0x18000e736  call    cs:__imp_RegQueryValueExW
0x18000e73d  nop     dword ptr [rax+rax+00h]
0x18000e742  mov     ebx, eax
0x18000e744  test    eax, eax
0x18000e746  jnz     loc_18000E7CF
0x18000e74c  mov     ecx, dword ptr [rbp+47h+pszSrc]
0x18000e74f  shr     rcx, 1
0x18000e752  mov     [rdi+rcx*2-2], ax
0x18000e757  xor     r8d, r8d; nSize
0x18000e75a  xor     edx, edx; lpDst
0x18000e75c  mov     rcx, rdi; lpSrc
0x18000e75f  call    cs:__imp_ExpandEnvironmentStringsW
0x18000e766  nop     dword ptr [rax+rax+00h]
0x18000e76b  mov     edx, eax
0x18000e76d  mov     dword ptr [rbp+47h+pszSrc], edx
0x18000e770  add     rdx, rdx; uBytes
0x18000e773  mov     ecx, 40h ; '@'; uFlags
0x18000e778  call    cs:__imp_LocalAlloc
0x18000e77f  nop     dword ptr [rax+rax+00h]
0x18000e784  mov     rsi, rax
0x18000e787  test    rax, rax
0x18000e78a  jz      short loc_18000E7CA
0x18000e78c  xor     eax, eax
0x18000e78e  mov     [rsi], ax
0x18000e791  mov     r8d, dword ptr [rbp+47h+pszSrc]; nSize
0x18000e795  mov     rdx, rsi; lpDst
0x18000e798  mov     rcx, rdi; lpSrc
0x18000e79b  call    cs:__imp_ExpandEnvironmentStringsW
0x18000e7a2  nop     dword ptr [rax+rax+00h]
0x18000e7a7  mov     dword ptr [rbp+47h+pszSrc], eax
0x18000e7aa  test    eax, eax
0x18000e7ac  jnz     short loc_18000E7BE
0x18000e7ae  call    cs:__imp_GetLastError
0x18000e7b5  nop     dword ptr [rax+rax+00h]
0x18000e7ba  mov     ebx, eax
0x18000e7bc  jmp     short loc_18000E7CF
0x18000e7be  mov     r15, rsi
0x18000e7c1  xor     esi, esi
0x18000e7c3  jmp     short loc_18000E7D3
0x18000e7c5  mov     r15, rdi
0x18000e7c8  jmp     short loc_18000E7D3
0x18000e7ca  mov     ebx, 0Eh
0x18000e7cf  mov     r15, [rbp+47h+var_80]
0x18000e7d3  mov     rcx, rdi; hMem
0x18000e7d6  call    cs:__imp_LocalFree
0x18000e7dd  nop     dword ptr [rax+rax+00h]
0x18000e7e2  mov     rcx, rsi; hMem
0x18000e7e5  call    cs:__imp_LocalFree
0x18000e7ec  nop     dword ptr [rax+rax+00h]
0x18000e7f1  mov     rcx, [rbp+47h+hKey]; hKey
0x18000e7f5  call    cs:__imp_RegCloseKey
0x18000e7fc  nop     dword ptr [rax+rax+00h]
0x18000e801  mov     rcx, r13; hMem
0x18000e804  call    cs:__imp_LocalFree
0x18000e80b  nop     dword ptr [rax+rax+00h]
0x18000e810  test    ebx, ebx
0x18000e812  jnz     loc_18000EA3A
0x18000e818  xor     r8d, r8d; dwFlags
0x18000e81b  xor     edx, edx; hFile
0x18000e81d  mov     rcx, r15; lpLibFileName
0x18000e820  call    cs:__imp_LoadLibraryExW
0x18000e827  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
