# PoolKeyList::p_Populate(_PregenParms const *)

- ea: `0x18001ca98`
- end: `0x18001cd15`
- name: `?p_Populate@PoolKeyList@@AEAAJPEBU_PregenParms@@@Z`
- size: `637`
- prototype: `__int64 __fastcall(PoolKeyList *__hidden this, const struct _PregenParms *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c1e4`

## callees

- `0x18000b0fc`
- `0x18000db5c`
- `0x18001069c`
- `0x180010730`
- `0x180014e40`
- `0x1800153f0`
- `0x18001737c`
- `0x18001c9a8`
- `0x18001ca98`
- `0x180022ef4`
- `0x180023264`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001cbfe`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001cbfe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cb1d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cb1d`

## string_xrefs

- `0x18001cadd`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001cb3a`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001cb88`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001cc42`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001cc7f`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001ccd5`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PoolKeyList::p_Populate(PoolKeyList *this, const unsigned __int16 **a2)
{
  const unsigned __int16 *v4; // rdx
  NgcUtils *v5; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v7; // ebx
  HKEY *v8; // rax
  int v9; // eax
  unsigned int *v10; // r9
  bool v11; // sf
  int v12; // eax
  DWORD v13; // r14d
  WCHAR *v14; // rbx
  DWORD i; // esi
  LSTATUS v16; // eax
  signed int v17; // edi
  int v18; // eax
  unsigned int v19; // edi
  int phkResult; // [rsp+20h] [rbp-30h]
  int phkResulta; // [rsp+20h] [rbp-30h]
  int phkResultb; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKey[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  DWORD cchName; // [rsp+98h] [rbp+48h] BYREF
  LPWSTR lpName; // [rsp+A0h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+58h] BYREF

  lpSubKey[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    lpSubKey,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v5,
                                        v4,
                                        a2[3],
                                        (unsigned __int16 *)lpSubKey);
  v7 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C4,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      phkResult);
LABEL_24:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpSubKey);
    return v7;
  }
  hKey = 0;
  v8 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0xF003Fu, v8);
  v11 = v9 < 0;
  if ( v9 > 0 )
  {
    v9 = (unsigned __int16)v9 | 0x80070000;
    v11 = v9 < 0;
  }
  if ( v11 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6D1,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v9,
      phkResulta);
LABEL_7:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v7 = 0;
    goto LABEL_24;
  }
  cchName = 0;
  LODWORD(lpName) = 0;
  v12 = NgcUtils::QueryRegistrySubKeys((NgcUtils *)hKey, &cchName, (unsigned int *)&lpName, v10);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6DB,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v12,
      phkResulta);
LABEL_23:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_24;
  }
  if ( !cchName )
    goto LABEL_7;
  v13 = (_DWORD)lpName + 1;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpName,
    0,
    (unsigned int)((_DWORD)lpName + 1));
  v14 = lpName;
  if ( !lpName )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E5,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)0x8007000ELL,
      phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
    goto LABEL_23;
  }
  for ( i = 0; ; ++i )
  {
    cchName = v13;
    v16 = RegEnumKeyExW(hKey, i, v14, &cchName, 0, 0, 0, 0);
    v17 = v16;
    if ( v16 > 0 )
      v17 = (unsigned __int16)v16 | 0x80070000;
    if ( v17 == -2147024637 )
      break;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6FA,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v17,
        phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      v7 = v17;
      goto LABEL_24;
    }
    v18 = PoolKeyList::p_Add(this, (NgcUtils *)v14, (const struct _PregenParms *)a2);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6FE,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v18,
        phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpSubKey);
      return v19;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpSubKey);
  return 0;
}

```

## disassembly

```asm
0x18001ca98  push    rbp
0x18001ca9a  push    rbx
0x18001ca9b  push    rsi
0x18001ca9c  push    rdi
0x18001ca9d  push    r12
0x18001ca9f  push    r14
0x18001caa1  push    r15
0x18001caa3  mov     rbp, rsp
0x18001caa6  sub     rsp, 50h
0x18001caaa  mov     r15, rdx
0x18001caad  mov     r12, rcx
0x18001cab0  mov     [rbp+lpSubKey], 0
0x18001cab8  xor     edx, edx
0x18001caba  lea     rcx, [rbp+lpSubKey]
0x18001cabe  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001cac3  lea     r9, [rbp+lpSubKey]; unsigned __int16 *
0x18001cac7  mov     r8, [r15+18h]; unsigned __int16 *
0x18001cacb  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001cad0  mov     ebx, eax
0x18001cad2  test    eax, eax
0x18001cad4  jns     short loc_18001CAF3
0x18001cad6  mov     rcx, [rbp+38h]; this
0x18001cada  mov     r9d, eax; char *
0x18001cadd  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001cae4  mov     edx, 6C4h; void *
0x18001cae9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001caee  jmp     loc_18001CCFB
0x18001caf3  mov     [rbp+hKey], 0
0x18001cafb  lea     rcx, [rbp+hKey]
0x18001caff  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18001cb04  mov     [rsp+50h+phkResult], rax; int
0x18001cb09  mov     r9d, 0F003Fh; samDesired
0x18001cb0f  xor     r8d, r8d; ulOptions
0x18001cb12  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001cb16  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cb1d  call    cs:__imp_RegOpenKeyExW
0x18001cb23  test    eax, eax
0x18001cb25  jle     short loc_18001CB31
0x18001cb27  movzx   eax, ax
0x18001cb2a  or      eax, 80070000h
0x18001cb2f  test    eax, eax
0x18001cb31  jns     short loc_18001CB5C
0x18001cb33  mov     rcx, [rbp+38h]; this
0x18001cb37  mov     r9d, eax; char *
0x18001cb3a  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001cb41  mov     edx, 6D1h; void *
0x18001cb46  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cb4b  nop
0x18001cb4c  lea     rcx, [rbp+hKey]
0x18001cb50  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001cb55  xor     ebx, ebx
0x18001cb57  jmp     loc_18001CCFB
0x18001cb5c  mov     [rbp+cchName], 0
0x18001cb63  mov     dword ptr [rbp+lpName], 0
0x18001cb6a  lea     r8, [rbp+lpName]; unsigned int *
0x18001cb6e  lea     rdx, [rbp+cchName]; HKEY
0x18001cb72  mov     rcx, [rbp+hKey]; this
0x18001cb76  call    ?QueryRegistrySubKeys@NgcUtils@@YAJPEAUHKEY__@@PEAK1@Z; NgcUtils::QueryRegistrySubKeys(HKEY__ *,ulong *,ulong *)
0x18001cb7b  mov     ebx, eax
0x18001cb7d  test    eax, eax
0x18001cb7f  jns     short loc_18001CB9E
0x18001cb81  mov     rcx, [rbp+38h]; this
0x18001cb85  mov     r9d, eax; char *
0x18001cb88  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001cb8f  mov     edx, 6DBh; void *
0x18001cb94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cb99  jmp     loc_18001CCF1
0x18001cb9e  cmp     [rbp+cchName], 0
0x18001cba2  jz      short loc_18001CB4C
0x18001cba4  mov     r14d, dword ptr [rbp+lpName]
0x18001cba8  inc     r14d
0x18001cbab  mov     r8d, r14d
0x18001cbae  xor     edx, edx
0x18001cbb0  lea     rcx, [rbp+lpName]
0x18001cbb4  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001cbb9  nop
0x18001cbba  mov     rbx, [rbp+lpName]
0x18001cbbe  test    rbx, rbx
0x18001cbc1  jz      loc_18001CCC9
0x18001cbc7  xor     esi, esi
0x18001cbc9  mov     [rbp+cchName], r14d
0x18001cbcd  mov     [rsp+50h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18001cbd6  mov     [rsp+50h+lpcchClass], 0; lpcchClass
0x18001cbdf  mov     [rsp+50h+lpClass], 0; lpClass
0x18001cbe8  mov     [rsp+50h+phkResult], 0; int
0x18001cbf1  lea     r9, [rbp+cchName]; lpcchName
0x18001cbf5  mov     r8, rbx; lpName
0x18001cbf8  mov     edx, esi; dwIndex
0x18001cbfa  mov     rcx, [rbp+hKey]; hKey
0x18001cbfe  call    cs:__imp_RegEnumKeyExW
0x18001cc04  mov     edi, eax
0x18001cc06  test    eax, eax
0x18001cc08  jle     short loc_18001CC13
0x18001cc0a  movzx   edi, ax
0x18001cc0d  or      edi, 80070000h
0x18001cc13  cmp     edi, 80070103h
0x18001cc19  jz      loc_18001CCA8
0x18001cc1f  test    edi, edi
0x18001cc21  js      short loc_18001CC78
0x18001cc23  mov     r8, r15; struct _PregenParms *
0x18001cc26  mov     rdx, rbx; unsigned __int16 *
0x18001cc29  mov     rcx, r12; this
0x18001cc2c  call    ?p_Add@PoolKeyList@@AEAAJPEBGPEBU_PregenParms@@@Z; PoolKeyList::p_Add(ushort const *,_PregenParms const *)
0x18001cc31  mov     edi, eax
0x18001cc33  test    eax, eax
0x18001cc35  js      short loc_18001CC3B
0x18001cc37  inc     esi
0x18001cc39  jmp     short loc_18001CBC9
0x18001cc3b  mov     rcx, [rbp+38h]; this
0x18001cc3f  mov     r9d, edi; char *
0x18001cc42  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001cc49  mov     edx, 6FEh; void *
0x18001cc4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cc53  nop
0x18001cc54  lea     rcx, [rbp+lpName]
0x18001cc58  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001cc5d  nop
0x18001cc5e  lea     rcx, [rbp+hKey]
0x18001cc62  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001cc67  nop
0x18001cc68  lea     rcx, [rbp+lpSubKey]
0x18001cc6c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001cc71  mov     eax, edi
0x18001cc73  jmp     loc_18001CD06
0x18001cc78  mov     rcx, [rbp+38h]; this
0x18001cc7c  mov     r9d, edi; char *
0x18001cc7f  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001cc86  mov     edx, 6FAh; void *
0x18001cc8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cc90  nop
0x18001cc91  lea     rcx, [rbp+lpName]
0x18001cc95  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001cc9a  nop
0x18001cc9b  lea     rcx, [rbp+hKey]
0x18001cc9f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001cca4  mov     ebx, edi
0x18001cca6  jmp     short loc_18001CCFB
0x18001cca8  lea     rcx, [rbp+lpName]
0x18001ccac  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ccb1  nop
0x18001ccb2  lea     rcx, [rbp+hKey]
0x18001ccb6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001ccbb  nop
0x18001ccbc  lea     rcx, [rbp+lpSubKey]
0x18001ccc0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ccc5  xor     eax, eax
0x18001ccc7  jmp     short loc_18001CD06
0x18001ccc9  mov     rcx, [rbp+38h]; this
0x18001cccd  mov     ebx, 8007000Eh
0x18001ccd2  mov     r9d, ebx; char *
0x18001ccd5  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001ccdc  mov     edx, 6E5h; void *
0x18001cce1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cce6  nop
0x18001cce7  lea     rcx, [rbp+lpName]
0x18001cceb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ccf0  nop
0x18001ccf1  lea     rcx, [rbp+hKey]
0x18001ccf5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001ccfa  nop
0x18001ccfb  lea     rcx, [rbp+lpSubKey]
0x18001ccff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001cd04  mov     eax, ebx
0x18001cd06  add     rsp, 50h
0x18001cd0a  pop     r15
0x18001cd0c  pop     r14
0x18001cd0e  pop     r12
0x18001cd10  pop     rdi
0x18001cd11  pop     rsi
0x18001cd12  pop     rbx
0x18001cd13  pop     rbp
0x18001cd14  retn
```
