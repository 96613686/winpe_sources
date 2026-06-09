# EnrollForKeyPool(ushort const *)

- ea: `0x180012438`
- end: `0x1800126db`
- name: `?EnrollForKeyPool@@YAJPEBG@Z`
- size: `675`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014c24`

## callees

- `0x180008c74`
- `0x18000cc34`
- `0x18000ebc0`
- `0x18000ef9c`
- `0x18000ff9c`
- `0x180010310`
- `0x180012438`
- `0x1800126e4`
- `0x180014bcc`
- `0x18001c9ac`
- `0x18001cd5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800125dc`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800125dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800124bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800124bd`

## string_xrefs

- `0x180012476`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x1800124dd`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180012500`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x18001255e`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180012613`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180012645`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x18001269a`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall EnrollForKeyPool(const unsigned __int16 *a1)
{
  const unsigned __int16 *v2; // rdx
  NgcUtils *v3; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  unsigned int *v7; // r9
  int v8; // eax
  DWORD v9; // esi
  WCHAR *v10; // r8
  DWORD i; // edi
  LSTATUS v12; // eax
  int v13; // eax
  unsigned __int16 **phkResult; // [rsp+20h] [rbp-40h]
  int phkResulta; // [rsp+20h] [rbp-40h]
  int phkResultb; // [rsp+20h] [rbp-40h]
  int phkResultc; // [rsp+20h] [rbp-40h]
  int phkResultd; // [rsp+20h] [rbp-40h]
  HKEY hKey; // [rsp+40h] [rbp-20h] BYREF
  LPWSTR lpName; // [rsp+48h] [rbp-18h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  DWORD cchName; // [rsp+88h] [rbp+28h] BYREF
  struct HKEY__ v25; // [rsp+90h] [rbp+30h] BYREF

  lpSubKey[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    lpSubKey,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v3,
                                        v2,
                                        a1,
                                        (const unsigned __int16 *)lpSubKey,
                                        phkResult);
  v5 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x554,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      phkResulta);
LABEL_23:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpSubKey);
    return v5;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0xF003Fu, &hKey);
  v5 = v6;
  if ( v6 > 0 )
    v5 = (unsigned __int16)v6 | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x560,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)v5,
      phkResultb);
    if ( v5 + 2147024894 <= 1 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      v5 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x569,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)v5,
        phkResultc);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
    goto LABEL_23;
  }
  v25.unused = 0;
  cchName = 0;
  v8 = NgcUtils::QueryRegistrySubKeys((NgcUtils *)hKey, &v25, &cchName, v7);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x571,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)v8,
      phkResultb);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_23;
  }
  v9 = cchName + 1;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpName,
    0,
    cchName + 1);
  v10 = lpName;
  if ( !lpName )
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x577,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)0x8007000ELL,
      phkResultb);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_23;
  }
  for ( i = 0; i < v25.unused; ++i )
  {
    cchName = v9;
    v12 = RegEnumKeyExW(hKey, i, v10, &cchName, 0, 0, 0, 0);
    v5 = v12;
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x584,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)v5,
        phkResultd);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_23;
    }
    v13 = EnrollForOneAIK(lpName);
    v5 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x587,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)(unsigned int)v13,
        phkResultd);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_23;
    }
    v10 = lpName;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(lpSubKey);
  return 0;
}

```

## disassembly

```asm
0x180012438  mov     [rsp-18h+arg_0], rbx
0x18001243d  push    rbp
0x18001243e  push    rsi
0x18001243f  push    rdi
0x180012440  mov     rbp, rsp
0x180012443  sub     rsp, 60h
0x180012447  mov     rbx, rcx
0x18001244a  mov     [rbp+lpSubKey], 0
0x180012452  xor     edx, edx
0x180012454  lea     rcx, [rbp+lpSubKey]
0x180012458  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001245d  lea     r9, [rbp+lpSubKey]; unsigned __int16 *
0x180012461  mov     r8, rbx; unsigned __int16 *
0x180012464  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180012469  mov     ebx, eax
0x18001246b  test    eax, eax
0x18001246d  jns     short loc_18001248D
0x18001246f  mov     rcx, [rbp+18h]; this
0x180012473  mov     r9d, eax; char *
0x180012476  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001247d  mov     edx, 554h; void *
0x180012482  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012487  nop
0x180012488  jmp     loc_1800126C0
0x18001248d  mov     [rbp+hKey], 0
0x180012495  xor     edx, edx
0x180012497  lea     rcx, [rbp+hKey]
0x18001249b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800124a0  lea     rax, [rbp+hKey]
0x1800124a4  mov     [rsp+60h+phkResult], rax; int
0x1800124a9  mov     r9d, 0F003Fh; samDesired
0x1800124af  xor     r8d, r8d; ulOptions
0x1800124b2  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800124b6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800124bd  call    cs:__imp_RegOpenKeyExW
0x1800124c3  mov     ebx, eax
0x1800124c5  test    eax, eax
0x1800124c7  jle     short loc_1800124D2
0x1800124c9  movzx   ebx, ax
0x1800124cc  or      ebx, 80070000h
0x1800124d2  test    ebx, ebx
0x1800124d4  jns     short loc_180012532
0x1800124d6  mov     rcx, [rbp+18h]; this
0x1800124da  mov     r9d, ebx; char *
0x1800124dd  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800124e4  mov     edx, 560h; void *
0x1800124e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800124ee  lea     eax, [rbx+7FF8FFFEh]
0x1800124f4  cmp     eax, 1
0x1800124f7  jbe     short loc_180012521
0x1800124f9  mov     rcx, [rbp+18h]; this
0x1800124fd  mov     r9d, ebx; char *
0x180012500  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180012507  mov     edx, 569h; void *
0x18001250c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012511  nop
0x180012512  lea     rcx, [rbp+hKey]
0x180012516  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001251b  nop
0x18001251c  jmp     loc_1800126C0
0x180012521  lea     rcx, [rbp+hKey]
0x180012525  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001252a  nop
0x18001252b  xor     ebx, ebx
0x18001252d  jmp     loc_1800126C0
0x180012532  mov     [rbp+arg_10.unused], 0
0x180012539  mov     [rbp+cchName], 0
0x180012540  lea     r8, [rbp+cchName]; unsigned int *
0x180012544  lea     rdx, [rbp+arg_10]; HKEY
0x180012548  mov     rcx, [rbp+hKey]; this
0x18001254c  call    ?QueryRegistrySubKeys@NgcUtils@@YAJPEAUHKEY__@@PEAK1@Z; NgcUtils::QueryRegistrySubKeys(HKEY__ *,ulong *,ulong *)
0x180012551  mov     ebx, eax
0x180012553  test    eax, eax
0x180012555  jns     short loc_18001257F
0x180012557  mov     rcx, [rbp+18h]; this
0x18001255b  mov     r9d, eax; char *
0x18001255e  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180012565  mov     edx, 571h; void *
0x18001256a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001256f  nop
0x180012570  lea     rcx, [rbp+hKey]
0x180012574  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180012579  nop
0x18001257a  jmp     loc_1800126C0
0x18001257f  mov     esi, [rbp+cchName]
0x180012582  inc     esi
0x180012584  mov     r8d, esi
0x180012587  xor     edx, edx
0x180012589  lea     rcx, [rbp+lpName]
0x18001258d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180012592  nop
0x180012593  mov     r8, [rbp+lpName]; lpName
0x180012597  test    r8, r8
0x18001259a  jz      loc_18001268E
0x1800125a0  xor     edi, edi
0x1800125a2  cmp     edi, [rbp+arg_10.unused]
0x1800125a5  jnb     loc_18001266D
0x1800125ab  mov     [rbp+cchName], esi
0x1800125ae  mov     [rsp+60h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800125b7  mov     [rsp+60h+lpcchClass], 0; lpcchClass
0x1800125c0  mov     [rsp+60h+lpClass], 0; lpClass
0x1800125c9  mov     [rsp+60h+phkResult], 0; int
0x1800125d2  lea     r9, [rbp+cchName]; lpcchName
0x1800125d6  mov     edx, edi; dwIndex
0x1800125d8  mov     rcx, [rbp+hKey]; hKey
0x1800125dc  call    cs:__imp_RegEnumKeyExW
0x1800125e2  mov     ebx, eax
0x1800125e4  test    eax, eax
0x1800125e6  jle     short loc_1800125F1
0x1800125e8  movzx   ebx, ax
0x1800125eb  or      ebx, 80070000h
0x1800125f1  test    ebx, ebx
0x1800125f3  js      short loc_18001263E
0x1800125f5  mov     rcx, [rbp+lpName]; unsigned __int16 *
0x1800125f9  call    ?EnrollForOneAIK@@YAJPEBG@Z; EnrollForOneAIK(ushort const *)
0x1800125fe  mov     ebx, eax
0x180012600  test    eax, eax
0x180012602  js      short loc_18001260C
0x180012604  inc     edi
0x180012606  mov     r8, [rbp+lpName]
0x18001260a  jmp     short loc_1800125A2
0x18001260c  mov     rcx, [rbp+18h]; this
0x180012610  mov     r9d, eax; char *
0x180012613  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001261a  mov     edx, 587h; void *
0x18001261f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012624  nop
0x180012625  lea     rcx, [rbp+lpName]
0x180012629  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001262e  nop
0x18001262f  lea     rcx, [rbp+hKey]
0x180012633  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180012638  nop
0x180012639  jmp     loc_1800126C0
0x18001263e  mov     rcx, [rbp+18h]; this
0x180012642  mov     r9d, ebx; char *
0x180012645  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001264c  mov     edx, 584h; void *
0x180012651  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012656  nop
0x180012657  lea     rcx, [rbp+lpName]
0x18001265b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012660  nop
0x180012661  lea     rcx, [rbp+hKey]
0x180012665  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001266a  nop
0x18001266b  jmp     short loc_1800126C0
0x18001266d  lea     rcx, [rbp+lpName]
0x180012671  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012676  nop
0x180012677  lea     rcx, [rbp+hKey]
0x18001267b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180012680  nop
0x180012681  lea     rcx, [rbp+lpSubKey]
0x180012685  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001268a  xor     eax, eax
0x18001268c  jmp     short loc_1800126CB
0x18001268e  mov     rcx, [rbp+18h]; this
0x180012692  mov     ebx, 8007000Eh
0x180012697  mov     r9d, ebx; char *
0x18001269a  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800126a1  mov     edx, 577h; void *
0x1800126a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800126ab  nop
0x1800126ac  lea     rcx, [rbp+lpName]
0x1800126b0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800126b5  nop
0x1800126b6  lea     rcx, [rbp+hKey]
0x1800126ba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800126bf  nop
0x1800126c0  lea     rcx, [rbp+lpSubKey]
0x1800126c4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800126c9  mov     eax, ebx
0x1800126cb  mov     rbx, [rsp+60h+arg_0]
0x1800126d3  add     rsp, 60h
0x1800126d7  pop     rdi
0x1800126d8  pop     rsi
0x1800126d9  pop     rbp
0x1800126da  retn
```
