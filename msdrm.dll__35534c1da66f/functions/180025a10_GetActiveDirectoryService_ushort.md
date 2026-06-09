# GetActiveDirectoryService(ushort * *)

- ea: `0x180025a10`
- end: `0x1800262ae`
- name: `?GetActiveDirectoryService@@YAJPEAPEAG@Z`
- size: `2206`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800262b4`

## callees

- `0x180001284`
- `0x180001290`
- `0x180004654`
- `0x1800046c8`
- `0x180015438`
- `0x1800172d4`
- `0x180025a10`
- `0x180026300`
- `0x18005bd72`
- `0x18005f010`

## import_xrefs

- `msvcrt!wcschr` at `0x180025b8f`
- `msvcrt!wcschr` at `0x180025b8f`
- `msvcrt!wcsstr` at `0x180025d91`
- `msvcrt!wcsstr` at `0x180025db1`
- `msvcrt!wcsstr` at `0x180025d91`
- `msvcrt!wcsstr` at `0x180025db1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b63`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180025a71`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180025a91`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180025a71`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180025a91`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180025bb3`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180025bb3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180025a4d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180025a4d`
- `WLDAP32!__imp_ldap_unbind` at `0x180025c59`
- `WLDAP32!__imp_ldap_unbind` at `0x180025e8a`
- `WLDAP32!__imp_ldap_unbind` at `0x180026269`
- `WLDAP32!__imp_ldap_unbind` at `0x180025c59`
- `WLDAP32!__imp_ldap_unbind` at `0x180025e8a`
- `WLDAP32!__imp_ldap_unbind` at `0x180026269`
- `WLDAP32!__imp_LdapGetLastError` at `0x18002620e`
- `WLDAP32!__imp_LdapGetLastError` at `0x18002620e`
- `WLDAP32!__imp_ldap_first_entry` at `0x180025cdb`
- `WLDAP32!__imp_ldap_first_entry` at `0x180025f03`
- `WLDAP32!__imp_ldap_first_entry` at `0x1800260a7`
- `WLDAP32!__imp_ldap_first_entry` at `0x180025cdb`
- `WLDAP32!__imp_ldap_first_entry` at `0x180025f03`
- `WLDAP32!__imp_ldap_first_entry` at `0x1800260a7`
- `WLDAP32!__imp_ldap_msgfree` at `0x180025e73`
- `WLDAP32!__imp_ldap_msgfree` at `0x180026052`
- `WLDAP32!__imp_ldap_msgfree` at `0x18002624a`
- `WLDAP32!__imp_ldap_msgfree` at `0x180025e73`
- `WLDAP32!__imp_ldap_msgfree` at `0x180026052`
- `WLDAP32!__imp_ldap_msgfree` at `0x18002624a`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180025c38`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180025c87`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180025c38`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180025c87`
- `WLDAP32!__imp_ldap_control_freeW` at `0x18002625b`
- `WLDAP32!__imp_ldap_control_freeW` at `0x18002625b`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180025cf7`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180025f2c`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800260c3`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180025cf7`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180025f2c`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800260c3`
- `WLDAP32!__imp_ldap_initW` at `0x180025c0e`
- `WLDAP32!__imp_ldap_initW` at `0x180025c67`
- `WLDAP32!__imp_ldap_initW` at `0x180025c0e`
- `WLDAP32!__imp_ldap_initW` at `0x180025c67`
- `WLDAP32!__imp_ldap_search_sW` at `0x180025cbe`
- `WLDAP32!__imp_ldap_search_sW` at `0x180025edf`
- `WLDAP32!__imp_ldap_search_sW` at `0x180026083`
- `WLDAP32!__imp_ldap_search_sW` at `0x180025cbe`
- `WLDAP32!__imp_ldap_search_sW` at `0x180025edf`
- `WLDAP32!__imp_ldap_search_sW` at `0x180026083`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180025e81`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180026044`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180026253`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180025e81`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180026044`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180026253`

## string_xrefs

- `0x180025f1f`: `configurationNamingContext`
- `0x1800260b6`: `serviceBindingInformation`
- `0x180025a46`: `secur32.dll`
- `0x180025a8a`: `GetComputerObjectNameW`
- `0x180025ae8`: `[msdrm]: GetUserNameExW/GetComputerObjectNameW FAILED with error code: %d `
- `0x180026070`: `(&(objectCategory=serviceConnectionPoint)(keywords=MSRMRootCluster)(keywords=1.0))`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=2
__int64 __fastcall GetActiveDirectoryService(unsigned __int16 **a1)
{
  char *v1; // r15
  wchar_t *v2; // r14
  signed int ForestName; // edi
  unsigned __int16 *v4; // r13
  HMODULE LibraryW; // rax
  HMODULE v6; // r12
  FARPROC ProcAddress; // rsi
  unsigned int v8; // eax
  DWORD v9; // eax
  int v10; // esi
  wchar_t *v11; // rax
  signed int LastError; // eax
  wchar_t *v13; // rax
  LDAP *v14; // rsi
  PWCHAR *v15; // r12
  unsigned __int16 *v16; // rsi
  LDAP *v17; // rax
  ULONG v18; // eax
  LDAP *v19; // rax
  LDAPMessage *entry; // rax
  PWCHAR *valuesW; // rax
  PWCHAR v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r8
  const wchar_t *v25; // r14
  wchar_t *v26; // rax
  wchar_t *v27; // r8
  PWCHAR v28; // rcx
  __int64 v29; // rax
  unsigned __int16 *v30; // rcx
  unsigned __int16 *v31; // rax
  int v32; // ecx
  int v33; // edx
  LDAPMessage *v34; // rax
  PWCHAR *v35; // rax
  PWCHAR v36; // rax
  __int64 v37; // rdx
  unsigned __int64 v38; // r8
  signed __int64 v39; // r14
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // rcx
  unsigned __int16 *v42; // rax
  LDAPMessage *v43; // rax
  PWCHAR *v44; // rax
  PWCHAR v45; // rax
  __int64 v46; // rcx
  unsigned __int64 v47; // rdx
  signed __int64 v48; // r14
  unsigned __int64 v49; // rax
  unsigned __int64 v50; // rcx
  unsigned __int16 *v51; // rax
  LDAPMessage *res; // [rsp+40h] [rbp-68h] BYREF
  void *Block; // [rsp+48h] [rbp-60h] BYREF
  unsigned __int16 *v55; // [rsp+50h] [rbp-58h]
  LDAP *v56; // [rsp+58h] [rbp-50h]
  unsigned __int64 v57; // [rsp+60h] [rbp-48h]
  __int64 v58; // [rsp+68h] [rbp-40h]
  ULONG v60; // [rsp+B8h] [rbp+10h] BYREF
  unsigned __int16 *v61; // [rsp+C0h] [rbp+18h]
  unsigned __int64 v62; // [rsp+C8h] [rbp+20h]

  v58 = -2;
  res = 0;
  Block = 0;
  v1 = 0;
  v60 = 0;
  v2 = 0;
  ForestName = 0;
  v4 = 0;
  LibraryW = LoadLibraryW(L"secur32.dll");
  v6 = LibraryW;
  if ( !LibraryW )
    goto LABEL_22;
  if ( g_fGlobalOptionUseServerProc )
  {
    ProcAddress = GetProcAddress(LibraryW, "GetComputerObjectNameW");
    v8 = 7;
    LOWORD(v62) = 47;
  }
  else
  {
    ProcAddress = GetProcAddress(LibraryW, "GetUserNameExW");
    v8 = 12;
    LODWORD(v62) = 92;
  }
  LODWORD(v61) = v8;
  v55 = (unsigned __int16 *)ProcAddress;
  if ( !ProcAddress )
    goto LABEL_22;
  if ( ((unsigned __int8 (__fastcall *)(_QWORD, _QWORD, ULONG *))ProcAddress)(v8, 0, &v60) )
  {
LABEL_12:
    v11 = (wchar_t *)operator new[](saturated_mul(v60 + 1, 2u));
    v2 = v11;
    if ( v11 )
    {
      if ( ((unsigned __int8 (__fastcall *)(_QWORD, wchar_t *, ULONG *))ProcAddress)((unsigned int)v61, v11, &v60) )
      {
        v13 = wcschr(v2, v62);
        if ( v13 )
          *v13 = 0;
        v4 = v2;
        v2 = 0;
      }
      else
      {
        LastError = GetLastError();
        ForestName = LastError;
        if ( LastError > 0 )
          ForestName = (unsigned __int16)LastError | 0x80070000;
        if ( ForestName >= 0 )
          ForestName = -2147467259;
      }
    }
    else
    {
      ForestName = -2147024882;
    }
    goto LABEL_22;
  }
  v9 = GetLastError();
  v10 = v9;
  if ( v9 == 234 )
  {
    ProcAddress = (FARPROC)v55;
    goto LABEL_12;
  }
  _RTLTRACE("[msdrm]: GetUserNameExW/GetComputerObjectNameW FAILED with error code: %d ", v9);
  if ( v10 > 0 )
    ForestName = (unsigned __int16)v10 | 0x80070000;
  else
    ForestName = v10;
LABEL_22:
  operator delete(v2);
  if ( v6 )
    FreeLibrary(v6);
  if ( ForestName < 0 )
  {
    v14 = 0;
    v15 = 0;
    v60 = 0;
    _RTLTRACE("[msdrm]: GetUserDomain FAILED : %x ", ForestName);
    goto LABEL_97;
  }
  ForestName = GetForestName(v4, (unsigned __int16 **)&Block);
  v16 = (unsigned __int16 *)Block;
  if ( Block )
  {
    operator delete(v4);
    v4 = v16;
    Block = 0;
  }
  while ( 1 )
  {
    v17 = ldap_initW(v4, 0xCC4u);
    v14 = v17;
    if ( !v17 )
    {
LABEL_95:
      v60 = LdapGetLastError();
LABEL_96:
      v15 = 0;
      goto LABEL_97;
    }
    v57 = (unsigned __int64)v1;
    v56 = v17;
    v18 = ldap_bind_sW(v17, 0, 0, 0x486u);
    v60 = v18;
    if ( !v18 )
      break;
    if ( v18 != 81 )
      goto LABEL_96;
    ldap_unbind(v14);
    v19 = ldap_initW(v4, 0x185u);
    v14 = v19;
    if ( !v19 )
      goto LABEL_95;
    v60 = ldap_bind_sW(v19, 0, 0, 0x486u);
    if ( v60 )
      goto LABEL_96;
    v60 = ldap_search_sW(v14, 0, 0, (const PWSTR)L"(objectClass=*)", 0, 0, &res);
    if ( v60 )
      goto LABEL_96;
    entry = ldap_first_entry(v14, res);
    if ( !entry )
      goto LABEL_64;
    valuesW = ldap_get_valuesW(v14, entry, (const PWSTR)L"rootDomainNamingContext");
    v15 = valuesW;
    if ( !valuesW )
      goto LABEL_61;
    v22 = *valuesW;
    if ( !*valuesW )
      goto LABEL_61;
    v1 = (char *)v4;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v62 = (unsigned int)(v23 + 1);
    v4 = (unsigned __int16 *)operator new[](saturated_mul(v62, 2u));
    if ( !v4 )
    {
      ForestName = -2147024882;
      goto LABEL_97;
    }
    v24 = -1;
    do
      ++v24;
    while ( (*v15)[v24] );
    memset_0(v4, 0, 2 * v24 + 2);
    v61 = v4;
    v25 = *v15;
    while ( v25 )
    {
      v26 = wcsstr(v25, L"DC=");
      if ( !v26 )
        break;
      v25 = v26 + 3;
      v27 = wcsstr(v26 + 3, L",");
      if ( !v27 )
      {
        v28 = *v15;
        v29 = -1;
        do
          ++v29;
        while ( v28[v29] );
        v27 = &v28[v29];
      }
      v30 = v61;
      if ( v61 != v4 )
      {
        *v61 = 46;
        v61 = ++v30;
      }
      v57 = v27 - v25;
      ForestName = StringCchCopyNW(v30, v62 - (v30 - v4), v25, v57);
      if ( ForestName < 0 )
        goto LABEL_97;
      v61 += v57;
    }
    if ( v1 )
    {
      v31 = (unsigned __int16 *)v1;
      do
      {
        v32 = *(unsigned __int16 *)((char *)v31 + (char *)v4 - v1);
        v33 = *v31 - v32;
        if ( v33 )
          break;
        ++v31;
      }
      while ( v32 );
      if ( !v33 )
      {
        v60 = 81;
        goto LABEL_97;
      }
    }
    ldap_msgfree(res);
    res = 0;
    ldap_value_freeW(v15);
    ldap_unbind(v14);
  }
  v60 = ldap_search_sW(v14, 0, 0, (const PWSTR)L"(objectClass=*)", 0, 0, &res);
  LODWORD(v61) = v60;
  if ( v60 )
    goto LABEL_65;
  v34 = ldap_first_entry(v14, res);
  if ( !v34 )
  {
LABEL_64:
    ForestName = -2147168440;
LABEL_65:
    v15 = 0;
    goto LABEL_97;
  }
  v35 = ldap_get_valuesW(v14, v34, (const PWSTR)L"configurationNamingContext");
  v15 = v35;
  v62 = (unsigned __int64)v35;
  if ( !v35 || !*v35 )
  {
LABEL_61:
    ForestName = -2147168440;
    goto LABEL_97;
  }
  operator delete(v4);
  v4 = 0;
  v55 = 0;
  v36 = *v15;
  if ( !*v15 )
  {
    ForestName = -2147024809;
    goto LABEL_97;
  }
  v37 = 0x7FFFFFFF;
  do
  {
    if ( !*v36 )
      break;
    ++v36;
    --v37;
  }
  while ( v37 );
  ForestName = v37 == 0 ? 0x80070057 : 0;
  v38 = (0x7FFFFFFF - v37) & -(__int64)(v37 != 0);
  if ( v37 )
  {
    v39 = v38 + 1;
    if ( v38 + 1 < v38 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    if ( v39 < 0 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    v40 = 2LL * (unsigned int)v39;
    v41 = HIDWORD(v39) << 33;
    if ( v41 + v40 < v40 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    if ( !(v41 + v40) )
      goto LABEL_80;
    v42 = (unsigned __int16 *)operator new[](saturated_mul(v39, 2u));
    v4 = v42;
    v55 = v42;
    if ( !v42 )
    {
      ForestName = -2147024882;
      goto LABEL_97;
    }
    ForestName = StringCchCopyW(v42, v39, *v15);
    if ( ForestName >= 0 )
    {
LABEL_80:
      ldap_value_freeW(v15);
      v15 = 0;
      ldap_msgfree(res);
      res = 0;
      v60 = ldap_search_sW(
              v14,
              v4,
              2u,
              (const PWSTR)L"(&(objectCategory=serviceConnectionPoint)(keywords=MSRMRootCluster)(keywords=1.0))",
              0,
              0,
              &res);
      LODWORD(v61) = v60;
      if ( !v60 )
      {
        v43 = ldap_first_entry(v14, res);
        if ( v43 )
        {
          v44 = ldap_get_valuesW(v14, v43, (const PWSTR)L"serviceBindingInformation");
          v15 = v44;
          v62 = (unsigned __int64)v44;
          if ( v44 )
          {
            v45 = *v44;
            if ( v45 )
            {
              v46 = 0x7FFFFFFF;
              do
              {
                if ( !*v45 )
                  break;
                ++v45;
                --v46;
              }
              while ( v46 );
              ForestName = v46 == 0 ? 0x80070057 : 0;
              v47 = (0x7FFFFFFF - v46) & ((unsigned __int128)-(__int128)(unsigned __int64)v46 >> 64);
              if ( v46 )
              {
                v48 = v47 + 1;
                if ( v47 + 1 < v47 )
                  SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
                if ( v48 < 0 )
                  SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
                v49 = 2LL * (unsigned int)v48;
                v50 = HIDWORD(v48) << 33;
                if ( v50 + v49 < v49 )
                  SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
                if ( v50 + v49 )
                {
                  v51 = (unsigned __int16 *)operator new[](saturated_mul(v48, 2u));
                  *a1 = v51;
                  if ( v51 )
                    ForestName = StringCchCopyW(v51, v48, *v15);
                  else
                    ForestName = -2147024882;
                }
              }
              goto LABEL_97;
            }
          }
        }
        goto LABEL_61;
      }
    }
  }
LABEL_97:
  operator delete(v4);
  operator delete(v1);
  operator delete(Block);
  operator delete(0);
  ldap_msgfree(res);
  ldap_value_freeW(v15);
  ldap_control_freeW(0);
  if ( v14 )
    ldap_unbind(v14);
  if ( v60 )
    return (unsigned int)-2147168440;
  return (unsigned int)ForestName;
}

```

## disassembly

```asm
0x180025a10  mov     rax, rsp
0x180025a13  mov     [rax+8], rcx
0x180025a17  push    rbx
0x180025a18  push    rsi
0x180025a19  push    rdi
0x180025a1a  push    r12
0x180025a1c  push    r13
0x180025a1e  push    r14
0x180025a20  push    r15
0x180025a22  sub     rsp, 70h
0x180025a26  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x180025a2e  xor     ebx, ebx
0x180025a30  mov     [rax-68h], rbx
0x180025a34  mov     [rax-60h], rbx
0x180025a38  mov     r15d, ebx
0x180025a3b  mov     [rax+10h], ebx
0x180025a3e  mov     r14d, ebx
0x180025a41  mov     edi, ebx
0x180025a43  mov     r13d, ebx
0x180025a46  lea     rcx, LibFileName; "secur32.dll"
0x180025a4d  call    cs:__imp_LoadLibraryW
0x180025a53  mov     r12, rax
0x180025a56  test    rax, rax
0x180025a59  jz      loc_180025BA3
0x180025a5f  mov     rcx, rax; hModule
0x180025a62  cmp     cs:?g_fGlobalOptionUseServerProc@@3HA, ebx; int g_fGlobalOptionUseServerProc
0x180025a68  jnz     short loc_180025A8A
0x180025a6a  lea     rdx, ProcName; "GetUserNameExW"
0x180025a71  call    cs:__imp_GetProcAddress
0x180025a77  mov     rsi, rax
0x180025a7a  lea     eax, [rbx+0Ch]
0x180025a7d  mov     dword ptr [rsp+0A8h+arg_18], 5Ch ; '\'
0x180025a88  jmp     short loc_180025AAA
0x180025a8a  lea     rdx, aGetcomputerobj; "GetComputerObjectNameW"
0x180025a91  call    cs:__imp_GetProcAddress
0x180025a97  mov     rsi, rax
0x180025a9a  mov     eax, 7
0x180025a9f  lea     ecx, [rax+28h]
0x180025aa2  mov     word ptr [rsp+0A8h+arg_18], cx
0x180025aaa  mov     dword ptr [rsp+0A8h+arg_10], eax
0x180025ab1  mov     [rsp+0A8h+var_58], rsi
0x180025ab6  test    rsi, rsi
0x180025ab9  jz      loc_180025BA3
0x180025abf  lea     r8, [rsp+0A8h+arg_8]
0x180025ac7  xor     edx, edx
0x180025ac9  mov     ecx, eax
0x180025acb  mov     rax, rsi
0x180025ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ad3  test    al, al
0x180025ad5  jnz     short loc_180025B12
0x180025ad7  call    cs:__imp_GetLastError
0x180025add  mov     esi, eax
0x180025adf  cmp     eax, 0EAh
0x180025ae4  jz      short loc_180025B0D
0x180025ae6  mov     edx, eax
0x180025ae8  lea     rcx, aMsdrmGetuserna; "[msdrm]: GetUserNameExW/GetComputerObje"...
0x180025aef  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180025af4  test    esi, esi
0x180025af6  jg      short loc_180025AFF
0x180025af8  mov     edi, esi
0x180025afa  jmp     loc_180025BA3
0x180025aff  movzx   edi, si
0x180025b02  or      edi, 80070000h
0x180025b08  jmp     loc_180025BA3
0x180025b0d  mov     rsi, [rsp+0A8h+var_58]
0x180025b12  mov     ecx, [rsp+0A8h+arg_8]
0x180025b19  inc     ecx
0x180025b1b  mov     eax, 2
0x180025b20  mul     rcx
0x180025b23  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180025b2a  cmovb   rax, rcx
0x180025b2e  mov     rcx, rax; unsigned __int64
0x180025b31  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180025b36  mov     r14, rax
0x180025b39  test    rax, rax
0x180025b3c  jnz     short loc_180025B45
0x180025b3e  mov     edi, 8007000Eh
0x180025b43  jmp     short loc_180025BA3
0x180025b45  lea     r8, [rsp+0A8h+arg_8]
0x180025b4d  mov     rdx, r14
0x180025b50  mov     ecx, dword ptr [rsp+0A8h+arg_10]
0x180025b57  mov     rax, rsi
0x180025b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b5f  test    al, al
0x180025b61  jnz     short loc_180025B84
0x180025b63  call    cs:__imp_GetLastError
0x180025b69  mov     edi, eax
0x180025b6b  test    eax, eax
0x180025b6d  jle     short loc_180025B78
0x180025b6f  movzx   edi, ax
0x180025b72  or      edi, 80070000h
0x180025b78  mov     eax, 80004005h
0x180025b7d  test    edi, edi
0x180025b7f  cmovns  edi, eax
0x180025b82  jmp     short loc_180025BA3
0x180025b84  movzx   edx, word ptr [rsp+0A8h+arg_18]; Ch
0x180025b8c  mov     rcx, r14; Str
0x180025b8f  call    cs:__imp_wcschr
0x180025b95  test    rax, rax
0x180025b98  jz      short loc_180025B9D
0x180025b9a  mov     [rax], bx
0x180025b9d  mov     r13, r14
0x180025ba0  mov     r14, rbx
0x180025ba3  mov     rcx, r14; Block
0x180025ba6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025bab  test    r12, r12
0x180025bae  jz      short loc_180025BB9
0x180025bb0  mov     rcx, r12; hLibModule
0x180025bb3  call    cs:__imp_FreeLibrary
0x180025bb9  test    edi, edi
0x180025bbb  jns     short loc_180025BDD
0x180025bbd  mov     rsi, rbx
0x180025bc0  mov     r12, rbx
0x180025bc3  mov     [rsp+0A8h+arg_8], ebx
0x180025bca  mov     edx, edi
0x180025bcc  lea     rcx, aMsdrmGetuserdo; "[msdrm]: GetUserDomain FAILED : %x "
0x180025bd3  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180025bd8  jmp     loc_18002621E
0x180025bdd  lea     rdx, [rsp+0A8h+Block]; unsigned __int16 **
0x180025be2  mov     rcx, r13; unsigned __int16 *
0x180025be5  call    ?GetForestName@@YAJPEAGPEAPEAG@Z; GetForestName(ushort *,ushort * *)
0x180025bea  mov     edi, eax
0x180025bec  mov     rsi, [rsp+0A8h+Block]
0x180025bf1  test    rsi, rsi
0x180025bf4  jz      short loc_180025C06
0x180025bf6  mov     rcx, r13; Block
0x180025bf9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025bfe  mov     r13, rsi
0x180025c01  mov     [rsp+0A8h+Block], rbx
0x180025c06  mov     edx, 0CC4h; PortNumber
0x180025c0b  mov     rcx, r13; HostName
0x180025c0e  call    cs:__imp_ldap_initW
0x180025c14  mov     rsi, rax
0x180025c17  test    rax, rax
0x180025c1a  jz      loc_18002620E
0x180025c20  mov     [rsp+0A8h+var_48], r15
0x180025c25  mov     [rsp+0A8h+var_50], rax
0x180025c2a  mov     r9d, 486h; method
0x180025c30  xor     r8d, r8d; cred
0x180025c33  xor     edx, edx; dn
0x180025c35  mov     rcx, rax; ld
0x180025c38  call    cs:__imp_ldap_bind_sW
0x180025c3e  mov     [rsp+0A8h+arg_8], eax
0x180025c45  test    eax, eax
0x180025c47  jz      loc_180025EBD
0x180025c4d  cmp     eax, 51h ; 'Q'
0x180025c50  jnz     loc_18002621B
0x180025c56  mov     rcx, rsi; ld
0x180025c59  call    cs:__imp_ldap_unbind
0x180025c5f  mov     edx, 185h; PortNumber
0x180025c64  mov     rcx, r13; HostName
0x180025c67  call    cs:__imp_ldap_initW
0x180025c6d  mov     rsi, rax
0x180025c70  test    rax, rax
0x180025c73  jz      loc_18002620E
0x180025c79  mov     r9d, 486h; method
0x180025c7f  xor     r8d, r8d; cred
0x180025c82  xor     edx, edx; dn
0x180025c84  mov     rcx, rax; ld
0x180025c87  call    cs:__imp_ldap_bind_sW
0x180025c8d  mov     [rsp+0A8h+arg_8], eax
0x180025c94  test    eax, eax
0x180025c96  jnz     loc_18002621B
0x180025c9c  lea     rax, [rsp+0A8h+var_68]
0x180025ca1  mov     [rsp+0A8h+res], rax; res
0x180025ca6  mov     [rsp+0A8h+attrsonly], ebx; attrsonly
0x180025caa  mov     [rsp+0A8h+attrs], rbx; attrs
0x180025caf  lea     r9, filter; "(objectClass=*)"
0x180025cb6  xor     r8d, r8d; scope
0x180025cb9  xor     edx, edx; base
0x180025cbb  mov     rcx, rsi; ld
0x180025cbe  call    cs:__imp_ldap_search_sW
0x180025cc4  mov     [rsp+0A8h+arg_8], eax
0x180025ccb  test    eax, eax
0x180025ccd  jnz     loc_18002621B
0x180025cd3  mov     rdx, [rsp+0A8h+var_68]; res
0x180025cd8  mov     rcx, rsi; ld
0x180025cdb  call    cs:__imp_ldap_first_entry
0x180025ce1  test    rax, rax
0x180025ce4  jz      loc_180025F0E
0x180025cea  lea     r8, attr; "rootDomainNamingContext"
0x180025cf1  mov     rdx, rax; entry
0x180025cf4  mov     rcx, rsi; ld
0x180025cf7  call    cs:__imp_ldap_get_valuesW
0x180025cfd  mov     r12, rax
0x180025d00  test    rax, rax
0x180025d03  jz      loc_180025EAF
0x180025d09  mov     rcx, [rax]
0x180025d0c  test    rcx, rcx
0x180025d0f  jz      loc_180025EAF
0x180025d15  mov     r15, r13
0x180025d18  or      r14, 0FFFFFFFFFFFFFFFFh
0x180025d1c  mov     rax, r14
0x180025d1f  inc     rax
0x180025d22  cmp     [rcx+rax*2], bx
0x180025d26  jnz     short loc_180025D1F
0x180025d28  lea     ecx, [rax+1]
0x180025d2b  mov     [rsp+0A8h+arg_18], rcx
0x180025d33  mov     eax, 2
0x180025d38  mul     rcx
0x180025d3b  cmovb   rax, r14
0x180025d3f  mov     rcx, rax; unsigned __int64
0x180025d42  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180025d47  mov     r13, rax
0x180025d4a  test    rax, rax
0x180025d4d  jz      loc_180025EA5
0x180025d53  mov     rax, [r12]
0x180025d57  mov     r8, r14
0x180025d5a  inc     r8
0x180025d5d  cmp     [rax+r8*2], bx
0x180025d62  jnz     short loc_180025D5A
0x180025d64  lea     r8, ds:2[r8*2]; Size
0x180025d6c  xor     edx, edx; Val
0x180025d6e  mov     rcx, r13; void *
0x180025d71  call    memset_0
0x180025d76  mov     [rsp+0A8h+arg_10], r13
0x180025d7e  mov     r14, [r12]
0x180025d82  jmp     loc_180025E3F
0x180025d87  lea     rdx, aDc; "DC="
0x180025d8e  mov     rcx, r14; Str
0x180025d91  call    cs:__imp_wcsstr
0x180025d97  mov     r14, rax
0x180025d9a  test    rax, rax
0x180025d9d  jz      loc_180025E48
0x180025da3  add     r14, 6
0x180025da7  lea     rdx, asc_180067D08; ","
0x180025dae  mov     rcx, r14; Str
0x180025db1  call    cs:__imp_wcsstr
0x180025db7  mov     r8, rax
0x180025dba  test    rax, rax
0x180025dbd  jnz     short loc_180025DD4
0x180025dbf  mov     rcx, [r12]
0x180025dc3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025dc7  inc     rax
0x180025dca  cmp     [rcx+rax*2], bx
0x180025dce  jnz     short loc_180025DC7
0x180025dd0  lea     r8, [rcx+rax*2]
0x180025dd4  mov     rcx, [rsp+0A8h+arg_10]
0x180025ddc  cmp     rcx, r13
0x180025ddf  jz      short loc_180025DF2
0x180025de1  mov     word ptr [rcx], 2Eh ; '.'
0x180025de6  add     rcx, 2; unsigned __int16 *
0x180025dea  mov     [rsp+0A8h+arg_10], rcx
0x180025df2  sub     r8, r14
0x180025df5  sar     r8, 1
0x180025df8  mov     [rsp+0A8h+var_48], r8
0x180025dfd  mov     rax, rcx
0x180025e00  sub     rax, r13
0x180025e03  sar     rax, 1
0x180025e06  mov     rdx, [rsp+0A8h+arg_18]
0x180025e0e  sub     rdx, rax; unsigned __int64
0x180025e11  mov     r9, r8; unsigned __int64
0x180025e14  mov     r8, r14; unsigned __int16 *
0x180025e17  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180025e1c  mov     edi, eax
0x180025e1e  test    eax, eax
0x180025e20  js      loc_18002621E
0x180025e26  mov     rax, [rsp+0A8h+arg_10]
0x180025e2e  mov     rcx, [rsp+0A8h+var_48]
0x180025e33  lea     rax, [rax+rcx*2]
0x180025e37  mov     [rsp+0A8h+arg_10], rax
0x180025e3f  test    r14, r14
0x180025e42  jnz     loc_180025D87
0x180025e48  test    r15, r15
0x180025e4b  jz      short loc_180025E6E
0x180025e4d  mov     rax, r15
0x180025e50  mov     r8, r13
0x180025e53  sub     r8, r15
0x180025e56  movzx   edx, word ptr [rax]
0x180025e59  movzx   ecx, word ptr [rax+r8]
0x180025e5e  sub     edx, ecx
0x180025e60  jnz     short loc_180025E6A
0x180025e62  add     rax, 2
0x180025e66  test    ecx, ecx
0x180025e68  jnz     short loc_180025E56
0x180025e6a  test    edx, edx
0x180025e6c  jz      short loc_180025E95
0x180025e6e  mov     rcx, [rsp+0A8h+var_68]; res
0x180025e73  call    cs:__imp_ldap_msgfree
0x180025e79  mov     [rsp+0A8h+var_68], rbx
0x180025e7e  mov     rcx, r12; vals
0x180025e81  call    cs:__imp_ldap_value_freeW
0x180025e87  mov     rcx, rsi; ld
0x180025e8a  call    cs:__imp_ldap_unbind
0x180025e90  jmp     loc_180025C06
0x180025e95  mov     [rsp+0A8h+arg_8], 51h ; 'Q'
0x180025ea0  jmp     loc_18002621E
0x180025ea5  mov     edi, 8007000Eh
0x180025eaa  jmp     loc_18002621E
0x180025eaf  mov     r14d, 8004CF48h
0x180025eb5  mov     edi, r14d
0x180025eb8  jmp     loc_180026224
0x180025ebd  lea     rax, [rsp+0A8h+var_68]
0x180025ec2  mov     [rsp+0A8h+res], rax; res
0x180025ec7  mov     [rsp+0A8h+attrsonly], ebx; attrsonly
0x180025ecb  mov     [rsp+0A8h+attrs], rbx; attrs
0x180025ed0  lea     r9, filter; "(objectClass=*)"
0x180025ed7  xor     r8d, r8d; scope
0x180025eda  xor     edx, edx; base
0x180025edc  mov     rcx, rsi; ld
  ... truncated ...
```
