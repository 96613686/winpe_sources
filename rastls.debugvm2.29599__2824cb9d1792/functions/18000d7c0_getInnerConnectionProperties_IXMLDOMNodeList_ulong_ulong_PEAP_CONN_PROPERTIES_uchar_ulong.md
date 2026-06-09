# getInnerConnectionProperties(IXMLDOMNodeList *,ulong,ulong *,_PEAP_CONN_PROPERTIES *,uchar * *,ulong *)

- ea: `0x18000d7c0`
- end: `0x18000dea9`
- name: `?getInnerConnectionProperties@@YAKPEAUIXMLDOMNodeList@@KPEAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEAE1@Z`
- size: `1769`
- prototype: `unsigned int __fastcall(struct IXMLDOMNodeList *, unsigned int, unsigned int *, struct _PEAP_CONN_PROPERTIES *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000cbb0`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18000c190`
- `0x18000d7c0`
- `0x18000f350`
- `0x18001e530`
- `0x18001f020`
- `0x18005e7c8`
- `0x18007c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000d8dc`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000d8dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000dc04`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000dc04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dc51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dc9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dc51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dc9e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000dde8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000dde8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d91d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db86`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dd78`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d91d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db86`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dd78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dbd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dbdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dbee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ddf6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dbd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dbdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dbee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ddf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dbe5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dbe5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000da9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000da9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db0b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db0b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db54`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000db73`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000dba3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000db73`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000dba3`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d865`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d865`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d8ac`
- `OLEAUT32!__imp_SysFreeString` at `0x18000de31`
- `OLEAUT32!__imp_SysFreeString` at `0x18000de60`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d8ac`
- `OLEAUT32!__imp_SysFreeString` at `0x18000de31`
- `OLEAUT32!__imp_SysFreeString` at `0x18000de60`

## string_xrefs

- `0x18000dc47`: `RasEapCreateConnectionProperties`
- `0x18000db01`: `ConfigUIPath`
- `0x18000db4a`: `ConfigUIPath`
- `0x18000d984`: `System\CurrentControlSet\Services\Rasman\PPP\EAP`

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
0x18000d7c0  mov     [rsp-8+arg_18], r9
0x18000d7c5  mov     [rsp-8+arg_10], r8
0x18000d7ca  mov     [rsp-8+arg_8], edx
0x18000d7ce  push    rbp
0x18000d7cf  push    rbx
0x18000d7d0  push    rsi
0x18000d7d1  push    rdi
0x18000d7d2  push    r12
0x18000d7d4  push    r13
0x18000d7d6  push    r14
0x18000d7d8  push    r15
0x18000d7da  lea     rbp, [rsp-0Fh]
0x18000d7df  sub     rsp, 98h
0x18000d7e6  xor     esi, esi
0x18000d7e8  mov     [rbp+47h+var_58], rsi
0x18000d7ec  mov     [rbp+47h+Source], rsi
0x18000d7f0  mov     dword ptr [rbp+47h+uBytes], esi
0x18000d7f3  mov     [rbp+47h+var_78], rsi
0x18000d7f7  mov     [rbp+47h+var_68], rsi
0x18000d7fb  mov     r12d, esi
0x18000d7fe  mov     [rbp+47h+var_50], rsi
0x18000d802  mov     rdx, [rbp+47h+arg_28]
0x18000d806  mov     [rdx], esi
0x18000d808  mov     rdx, [rbp+47h+arg_20]
0x18000d80c  mov     [rdx], rsi
0x18000d80f  mov     [r8], esi
0x18000d812  mov     rax, [rcx]
0x18000d815  lea     rdx, [rbp+47h+var_78]
0x18000d819  mov     rax, [rax+48h]
0x18000d81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d822  mov     rdi, [rbp+47h+var_78]
0x18000d826  test    rdi, rdi
0x18000d829  jnz     short loc_18000D85E
0x18000d82b  mov     ebx, esi
0x18000d82d  lea     r14, WPP_GLOBAL_Control
0x18000d834  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d83b  cmp     rcx, r14
0x18000d83e  jz      loc_18000DE5D
0x18000d844  mov     edx, 0E9h
0x18000d849  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000d850  mov     rcx, [rcx+10h]
0x18000d854  call    WPP_SF_
0x18000d859  jmp     loc_18000DE5D
0x18000d85e  lea     rcx, aBaseeapconnect_0; "baseeapconnectionpropertiesv1:Type[1]"
0x18000d865  call    cs:__imp_SysAllocString
0x18000d86b  mov     rbx, rax
0x18000d86e  mov     [rbp+47h+pszSrc], rax
0x18000d872  test    rax, rax
0x18000d875  jnz     short loc_18000D87D
0x18000d877  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d87d  mov     rax, [rdi]
0x18000d880  lea     r8, [rbp+47h+var_68]
0x18000d884  mov     rdx, rbx
0x18000d887  mov     rcx, rdi
0x18000d88a  mov     rax, [rax+128h]
0x18000d891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d896  test    eax, eax
0x18000d898  jnz     loc_18000DDFE
0x18000d89e  cmp     [rbp+47h+var_68], 0
0x18000d8a3  jz      loc_18000DDFE
0x18000d8a9  mov     rcx, rbx; bstrString
0x18000d8ac  call    cs:__imp_SysFreeString
0x18000d8b2  mov     rcx, [rbp+47h+var_68]
0x18000d8b6  mov     [rbp+47h+pszSrc], rsi
0x18000d8ba  mov     rax, [rcx]
0x18000d8bd  lea     rdx, [rbp+47h+pszSrc]
0x18000d8c1  mov     rax, [rax+0D0h]
0x18000d8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8cd  test    eax, eax
0x18000d8cf  jnz     loc_18000DE58
0x18000d8d5  mov     r15, rsi
0x18000d8d8  mov     rcx, [rbp+47h+pszSrc]
0x18000d8dc  call    cs:__imp__o__wtol
0x18000d8e2  mov     [rbp+47h+var_88], eax
0x18000d8e5  mov     r12, [rbp+47h+pszSrc]
0x18000d8e9  mov     [rbp+47h+var_50], r12
0x18000d8ed  mov     [rbp+47h+hKey], rsi
0x18000d8f1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000d8f8  nop     dword ptr [rax+rax+00000000h]
0x18000d900  lea     rax, [rax+1]
0x18000d904  cmp     [r12+rax*2], r15w
0x18000d909  jnz     short loc_18000D900
0x18000d90b  lea     eax, ds:66h[rax*2]
0x18000d912  movsxd  rbx, eax
0x18000d915  mov     rdx, rbx; uBytes
0x18000d918  mov     ecx, 40h ; '@'; uFlags
0x18000d91d  call    cs:__imp_LocalAlloc
0x18000d923  mov     r13, rax
0x18000d926  test    rax, rax
0x18000d929  jnz     short loc_18000D961
0x18000d92b  mov     ebx, 0Eh
0x18000d930  lea     r14, WPP_GLOBAL_Control
0x18000d937  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d93e  cmp     rcx, r14
0x18000d941  jz      loc_18000DDEE
0x18000d947  mov     edx, 0F8h
0x18000d94c  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000d953  mov     rcx, [rcx+10h]
0x18000d957  call    WPP_SF_
0x18000d95c  jmp     loc_18000DDEE
0x18000d961  shr     rbx, 1
0x18000d964  jz      loc_18000DA34
0x18000d96a  mov     r10d, 7FFFFFFEh
0x18000d970  cmp     rbx, 7FFFFFFFh
0x18000d977  jbe     short loc_18000D981
0x18000d979  mov     [rax], si
0x18000d97c  jmp     loc_18000DA80
0x18000d981  mov     rcx, r10
0x18000d984  lea     r8, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\Ra"...
0x18000d98b  mov     rdx, rbx
0x18000d98e  test    rcx, rcx
0x18000d991  jz      short loc_18000D9B2
0x18000d993  movzx   r9d, word ptr [r8]
0x18000d997  test    r9w, r9w
0x18000d99b  jz      short loc_18000D9B2
0x18000d99d  add     r8, 2
0x18000d9a1  mov     [rax], r9w
0x18000d9a5  add     rax, 2
0x18000d9a9  dec     rcx
0x18000d9ac  sub     rdx, 1
0x18000d9b0  jnz     short loc_18000D98E
0x18000d9b2  lea     rcx, [rax-2]
0x18000d9b6  test    rdx, rdx
0x18000d9b9  cmovnz  rcx, rax
0x18000d9bd  mov     [rcx], si
0x18000d9c0  mov     r8, rbx
0x18000d9c3  mov     rcx, rbx
0x18000d9c6  mov     rax, r13
0x18000d9c9  nop     dword ptr [rax+00000000h]
0x18000d9d0  cmp     [rax], r15w
0x18000d9d4  jz      short loc_18000D9E0
0x18000d9d6  add     rax, 2
0x18000d9da  sub     rcx, 1
0x18000d9de  jnz     short loc_18000D9D0
0x18000d9e0  mov     rdx, r8
0x18000d9e3  sub     rdx, rcx
0x18000d9e6  test    rcx, rcx
0x18000d9e9  cmovz   rdx, rsi
0x18000d9ed  jz      short loc_18000DA34
0x18000d9ef  lea     rcx, asc_180081834; "\\"
0x18000d9f6  sub     r8, rdx
0x18000d9f9  lea     rax, [r13+rdx*2+0]
0x18000d9fe  jz      short loc_18000DA21
0x18000da00  test    r10, r10
0x18000da03  jz      short loc_18000DA21
0x18000da05  movzx   edx, word ptr [rcx]
0x18000da08  test    dx, dx
0x18000da0b  jz      short loc_18000DA21
0x18000da0d  add     rcx, 2
0x18000da11  mov     [rax], dx
0x18000da14  add     rax, 2
0x18000da18  dec     r10
0x18000da1b  sub     r8, 1
0x18000da1f  jnz     short loc_18000DA00
0x18000da21  lea     rcx, [rax-2]
0x18000da25  test    r8, r8
0x18000da28  cmovnz  rcx, rax
0x18000da2c  mov     [rcx], si
0x18000da2f  mov     rcx, rbx
0x18000da32  jmp     short loc_18000DA45
0x18000da34  mov     rcx, rbx
0x18000da37  test    rbx, rbx
0x18000da3a  jz      short loc_18000DA80
0x18000da3c  cmp     rbx, 7FFFFFFFh
0x18000da43  ja      short loc_18000DA80
0x18000da45  mov     rax, r13
0x18000da48  cmp     [rax], r15w
0x18000da4c  jz      short loc_18000DA58
0x18000da4e  add     rax, 2
0x18000da52  sub     rcx, 1
0x18000da56  jnz     short loc_18000DA48
0x18000da58  mov     r8, rbx
0x18000da5b  sub     r8, rcx
0x18000da5e  test    rcx, rcx
0x18000da61  cmovz   r8, rsi; pcchNewDestLength
0x18000da65  jz      short loc_18000DA80
0x18000da67  sub     rbx, r8
0x18000da6a  lea     rcx, ds:0[r8*2]
0x18000da72  add     rcx, r13; pszDest
0x18000da75  mov     r9, r12; pszSrc
0x18000da78  mov     rdx, rbx; cchDest
0x18000da7b  call    StringCopyWorkerW
0x18000da80  lea     rax, [rbp+47h+hKey]
0x18000da84  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18000da89  mov     r9d, 20019h; samDesired
0x18000da8f  xor     r8d, r8d; ulOptions
0x18000da92  mov     rdx, r13; lpSubKey
0x18000da95  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000da9c  call    cs:__imp_RegOpenKeyExW
0x18000daa2  mov     ebx, eax
0x18000daa4  lea     r14, WPP_GLOBAL_Control
0x18000daab  test    eax, eax
0x18000daad  jz      short loc_18000DADC
0x18000daaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dab6  cmp     rcx, r14
0x18000dab9  jz      loc_18000DBEB
0x18000dabf  mov     edx, 0F9h
0x18000dac4  mov     r9, r13
0x18000dac7  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000dace  mov     rcx, [rcx+10h]
0x18000dad2  call    WPP_SF_S
0x18000dad7  jmp     loc_18000DBEB
0x18000dadc  mov     r15, [rbp+47h+hKey]
0x18000dae0  mov     dword ptr [rbp+47h+uBytes+4], esi
0x18000dae3  mov     dword ptr [rbp+47h+pszSrc], esi
0x18000dae6  xor     edi, edi
0x18000dae8  mov     [rbp+47h+var_80], rdi
0x18000daec  lea     rax, [rbp+47h+pszSrc]
0x18000daf0  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18000daf5  mov     [rsp+0D0h+phkResult], rdi; lpData
0x18000dafa  lea     r9, [rbp+47h+uBytes+4]; lpType
0x18000dafe  xor     r8d, r8d; lpReserved
0x18000db01  lea     rdx, aConfiguipath; "ConfigUIPath"
0x18000db08  mov     rcx, r15; hKey
0x18000db0b  call    cs:__imp_RegQueryValueExW
0x18000db11  mov     ebx, eax
0x18000db13  test    eax, eax
0x18000db15  jnz     loc_18000DBC1
0x18000db1b  mov     edx, dword ptr [rbp+47h+pszSrc]; uBytes
0x18000db1e  mov     ecx, 40h ; '@'; uFlags
0x18000db23  call    cs:__imp_LocalAlloc
0x18000db29  mov     rdi, rax
0x18000db2c  test    rax, rax
0x18000db2f  jz      loc_18000DBC6
0x18000db35  lea     rax, [rbp+47h+pszSrc]
0x18000db39  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18000db3e  mov     [rsp+0D0h+phkResult], rdi; lpData
0x18000db43  lea     r9, [rbp+47h+uBytes+4]; lpType
0x18000db47  xor     r8d, r8d; lpReserved
0x18000db4a  lea     rdx, aConfiguipath; "ConfigUIPath"
0x18000db51  mov     rcx, r15; hKey
0x18000db54  call    cs:__imp_RegQueryValueExW
0x18000db5a  mov     ebx, eax
0x18000db5c  test    eax, eax
0x18000db5e  jnz     short loc_18000DBCB
0x18000db60  mov     ecx, dword ptr [rbp+47h+pszSrc]
0x18000db63  shr     rcx, 1
0x18000db66  mov     [rdi+rcx*2-2], ax
0x18000db6b  xor     r8d, r8d; nSize
0x18000db6e  xor     edx, edx; lpDst
0x18000db70  mov     rcx, rdi; lpSrc
0x18000db73  call    cs:__imp_ExpandEnvironmentStringsW
0x18000db79  mov     edx, eax
0x18000db7b  mov     dword ptr [rbp+47h+pszSrc], edx
0x18000db7e  add     rdx, rdx; uBytes
0x18000db81  mov     ecx, 40h ; '@'; uFlags
0x18000db86  call    cs:__imp_LocalAlloc
0x18000db8c  mov     rsi, rax
0x18000db8f  test    rax, rax
0x18000db92  jz      short loc_18000DBC6
0x18000db94  xor     eax, eax
0x18000db96  mov     [rsi], ax
0x18000db99  mov     r8d, dword ptr [rbp+47h+pszSrc]; nSize
0x18000db9d  mov     rdx, rsi; lpDst
0x18000dba0  mov     rcx, rdi; lpSrc
0x18000dba3  call    cs:__imp_ExpandEnvironmentStringsW
0x18000dba9  mov     dword ptr [rbp+47h+pszSrc], eax
0x18000dbac  test    eax, eax
0x18000dbae  jnz     short loc_18000DBBA
0x18000dbb0  call    cs:__imp_GetLastError
0x18000dbb6  mov     ebx, eax
0x18000dbb8  jmp     short loc_18000DBCB
0x18000dbba  mov     r15, rsi
0x18000dbbd  xor     esi, esi
0x18000dbbf  jmp     short loc_18000DBCF
0x18000dbc1  mov     r15, rdi
0x18000dbc4  jmp     short loc_18000DBCF
0x18000dbc6  mov     ebx, 0Eh
0x18000dbcb  mov     r15, [rbp+47h+var_80]
0x18000dbcf  mov     rcx, rdi; hMem
0x18000dbd2  call    cs:__imp_LocalFree
0x18000dbd8  mov     rcx, rsi; hMem
0x18000dbdb  call    cs:__imp_LocalFree
0x18000dbe1  mov     rcx, [rbp+47h+hKey]; hKey
0x18000dbe5  call    cs:__imp_RegCloseKey
0x18000dbeb  mov     rcx, r13; hMem
0x18000dbee  call    cs:__imp_LocalFree
0x18000dbf4  test    ebx, ebx
0x18000dbf6  jnz     loc_18000DDEE
0x18000dbfc  xor     r8d, r8d; dwFlags
0x18000dbff  xor     edx, edx; hFile
0x18000dc01  mov     rcx, r15; lpLibFileName
0x18000dc04  call    cs:__imp_LoadLibraryExW
0x18000dc0a  mov     rdi, rax
0x18000dc0d  test    rax, rax
0x18000dc10  jnz     short loc_18000DC47
0x18000dc12  call    cs:__imp_GetLastError
0x18000dc18  mov     ebx, eax
0x18000dc1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc21  cmp     rcx, r14
0x18000dc24  jz      loc_18000DDEE
0x18000dc2a  mov     edx, 0EBh
0x18000dc2f  mov     r9d, eax
0x18000dc32  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000dc39  mov     rcx, [rcx+10h]
0x18000dc3d  call    WPP_SF_d
0x18000dc42  jmp     loc_18000DDEE
0x18000dc47  lea     rdx, aRaseapcreateco_2; "RasEapCreateConnectionProperties"
0x18000dc4e  mov     rcx, rdi; hModule
0x18000dc51  call    cs:__imp_GetProcAddress
  ... truncated ...
```
