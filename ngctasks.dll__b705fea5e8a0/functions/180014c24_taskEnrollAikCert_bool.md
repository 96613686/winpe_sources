# taskEnrollAikCert(bool *)

- ea: `0x180014c24`
- end: `0x180014e9c`
- name: `?taskEnrollAikCert@@YAJPEA_N@Z`
- size: `632`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800110c4`

## callees

- `0x180008c74`
- `0x18000cc34`
- `0x18000ebc0`
- `0x18000ef9c`
- `0x180010310`
- `0x18001159c`
- `0x180012438`
- `0x180014bcc`
- `0x180014c24`
- `0x180016850`
- `0x18001c9ac`
- `0x18001cb68`
- `0x18001ce10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014ccb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014ccb`

## string_xrefs

- `0x180014c84`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180014ceb`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180014d77`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180014da1`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180014dee`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180014e34`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180014e63`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall taskEnrollAikCert(bool *a1)
{
  char v2; // al
  const unsigned __int16 *v4; // rdx
  NgcUtils *v5; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  HKEY v9; // rdx
  int RegistryDwordValue; // eax
  HKEY v11; // rdx
  unsigned int v12; // esi
  int v13; // eax
  int v14; // eax
  unsigned int v15; // r9d
  int v16; // eax
  int v17; // eax
  unsigned int v18; // r9d
  int v19; // eax
  unsigned __int16 **phkResult; // [rsp+20h] [rbp-20h]
  int phkResulta; // [rsp+20h] [rbp-20h]
  unsigned int *phkResultb; // [rsp+20h] [rbp-20h]
  unsigned int *phkResultc; // [rsp+20h] [rbp-20h]
  int phkResultd; // [rsp+20h] [rbp-20h]
  HKEY v25; // [rsp+30h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  unsigned int v28; // [rsp+50h] [rbp+10h] BYREF

  v2 = AcquireExclusiveRunning(0, L"Volatile-AIKCertEnroll-EXCLUSIVE");
  *a1 = v2;
  if ( !v2 )
    return 0;
  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v5,
                                        v4,
                                        L"AIKCertEnroll",
                                        (const unsigned __int16 *)&lpSubKey,
                                        phkResult);
  v7 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    v25 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v25,
      0);
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &v25);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    if ( (v7 & 0x80000000) == 0 )
    {
      v28 = 0;
      RegistryDwordValue = NgcUtils::GetRegistryDwordValue(
                             (NgcUtils *)v25,
                             v9,
                             (const unsigned __int16 *)&stru_180025478,
                             (const unsigned __int16 *)&v28,
                             phkResultb);
      v12 = v28;
      if ( RegistryDwordValue == -2147024894 )
        v12 = 1;
      if ( (int)NgcUtils::GetRegistryDwordValue(
                  (NgcUtils *)v25,
                  v11,
                  (const unsigned __int16 *)&stru_180025458,
                  &g_reenrollAik,
                  phkResultc) < 0 )
        *(_DWORD *)&g_reenrollAik = 0;
      v28 = 0;
      v13 = RemoveRevokedAikCertificates(&v28);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5C7,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v13,
          phkResultd);
      v14 = EnrollForKeyPool(L"PregenKeys\\AIK");
      v7 = v14;
      if ( v14 >= 0 )
      {
        if ( (v28 || *(_DWORD *)&g_reenrollAik || v12)
          && (v16 = EnrollForKeyPool(L"PregenKeys\\ClaimedAIK"), v7 = v16, v16 < 0) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5D6,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
            (const char *)(unsigned int)v16,
            phkResultd);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
        }
        else
        {
          *(_DWORD *)&g_reenrollAik = 0;
          v17 = NgcUtils::SetRegistryDwordValue((NgcUtils *)v25, (HKEY)&stru_180025458, 0, v15);
          if ( v17 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x5DD,
              (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
              (const char *)(unsigned int)v17,
              phkResultd);
          v19 = NgcUtils::SetRegistryDwordValue((NgcUtils *)v25, (HKEY)&stru_180025478, 0, v18);
          if ( v19 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x5E3,
              (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
              (const char *)(unsigned int)v19,
              phkResultd);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
          v7 = 0;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5CC,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v14,
          phkResultd);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A9,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)v7,
        (int)phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A1,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      phkResulta);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
  return v7;
}

```

## disassembly

```asm
0x180014c24  mov     [rsp-8+arg_8], rbx
0x180014c29  mov     [rsp-8+arg_10], rsi
0x180014c2e  push    rbp
0x180014c2f  mov     rbp, rsp
0x180014c32  sub     rsp, 40h
0x180014c36  mov     rbx, rcx
0x180014c39  lea     rdx, aVolatileAikcer; "Volatile-AIKCertEnroll-EXCLUSIVE"
0x180014c40  xor     ecx, ecx; hHandle
0x180014c42  call    AcquireExclusiveRunning
0x180014c47  mov     [rbx], al
0x180014c49  test    al, al
0x180014c4b  jnz     short loc_180014C54
0x180014c4d  xor     eax, eax
0x180014c4f  jmp     loc_180014E8C
0x180014c54  mov     [rbp+lpSubKey], 0
0x180014c5c  xor     edx, edx
0x180014c5e  lea     rcx, [rbp+lpSubKey]
0x180014c62  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180014c67  lea     r9, [rbp+lpSubKey]; unsigned __int16 *
0x180014c6b  lea     r8, aAikcertenroll; "AIKCertEnroll"
0x180014c72  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180014c77  mov     ebx, eax
0x180014c79  test    eax, eax
0x180014c7b  jns     short loc_180014C9B
0x180014c7d  mov     rcx, [rbp+8]; this
0x180014c81  mov     r9d, eax; char *
0x180014c84  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180014c8b  mov     edx, 5A1h; void *
0x180014c90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014c95  nop
0x180014c96  jmp     loc_180014E81
0x180014c9b  mov     [rbp+var_10], 0
0x180014ca3  xor     edx, edx
0x180014ca5  lea     rcx, [rbp+var_10]
0x180014ca9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180014cae  lea     rax, [rbp+var_10]
0x180014cb2  mov     [rsp+40h+phkResult], rax; int
0x180014cb7  mov     r9d, 20019h; samDesired
0x180014cbd  xor     r8d, r8d; ulOptions
0x180014cc0  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180014cc4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014ccb  call    cs:__imp_RegOpenKeyExW
0x180014cd1  mov     ebx, eax
0x180014cd3  test    eax, eax
0x180014cd5  jle     short loc_180014CE0
0x180014cd7  movzx   ebx, ax
0x180014cda  or      ebx, 80070000h
0x180014ce0  test    ebx, ebx
0x180014ce2  jns     short loc_180014D0C
0x180014ce4  mov     rcx, [rbp+8]; this
0x180014ce8  mov     r9d, ebx; char *
0x180014ceb  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180014cf2  mov     edx, 5A9h; void *
0x180014cf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014cfc  nop
0x180014cfd  lea     rcx, [rbp+var_10]
0x180014d01  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180014d06  nop
0x180014d07  jmp     loc_180014E81
0x180014d0c  mov     [rbp+arg_0], 0
0x180014d13  lea     r9, [rbp+arg_0]; unsigned __int16 *
0x180014d17  lea     r8, stru_180025478; unsigned __int16 *
0x180014d1e  mov     rcx, [rbp+var_10]; this
0x180014d22  call    ?GetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1PEAK@Z; NgcUtils::GetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180014d27  mov     esi, [rbp+arg_0]
0x180014d2a  mov     ecx, 1
0x180014d2f  cmp     eax, 80070002h
0x180014d34  cmovz   esi, ecx
0x180014d37  lea     r9, ?g_reenrollAik@@3KA; unsigned __int16 *
0x180014d3e  lea     r8, stru_180025458; unsigned __int16 *
0x180014d45  mov     rcx, [rbp+var_10]; this
0x180014d49  call    ?GetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1PEAK@Z; NgcUtils::GetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180014d4e  test    eax, eax
0x180014d50  jns     short loc_180014D5C
0x180014d52  mov     cs:?g_reenrollAik@@3KA, 0; ulong g_reenrollAik
0x180014d5c  mov     [rbp+arg_0], 0
0x180014d63  lea     rcx, [rbp+arg_0]; unsigned int *
0x180014d67  call    ?RemoveRevokedAikCertificates@@YAJPEAK@Z; RemoveRevokedAikCertificates(ulong *)
0x180014d6c  mov     rcx, [rbp+8]; this
0x180014d70  test    eax, eax
0x180014d72  jns     short loc_180014D88
0x180014d74  mov     r9d, eax; char *
0x180014d77  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180014d7e  mov     edx, 5C7h; void *
0x180014d83  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014d88  lea     rcx, aPregenkeysAik; "PregenKeys\\AIK"
0x180014d8f  call    ?EnrollForKeyPool@@YAJPEBG@Z; EnrollForKeyPool(ushort const *)
0x180014d94  mov     ebx, eax
0x180014d96  test    eax, eax
0x180014d98  jns     short loc_180014DC2
0x180014d9a  mov     rcx, [rbp+8]; this
0x180014d9e  mov     r9d, eax; char *
0x180014da1  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180014da8  mov     edx, 5CCh; void *
0x180014dad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014db2  nop
0x180014db3  lea     rcx, [rbp+var_10]
0x180014db7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180014dbc  nop
0x180014dbd  jmp     loc_180014E81
0x180014dc2  cmp     [rbp+arg_0], 0
0x180014dc6  jnz     short loc_180014DD5
0x180014dc8  cmp     cs:?g_reenrollAik@@3KA, 0; ulong g_reenrollAik
0x180014dcf  ja      short loc_180014DD5
0x180014dd1  test    esi, esi
0x180014dd3  jz      short loc_180014E0C
0x180014dd5  lea     rcx, aPregenkeysClai; "PregenKeys\\ClaimedAIK"
0x180014ddc  call    ?EnrollForKeyPool@@YAJPEBG@Z; EnrollForKeyPool(ushort const *)
0x180014de1  mov     ebx, eax
0x180014de3  test    eax, eax
0x180014de5  jns     short loc_180014E0C
0x180014de7  mov     rcx, [rbp+8]; this
0x180014deb  mov     r9d, eax; char *
0x180014dee  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180014df5  mov     edx, 5D6h; void *
0x180014dfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014dff  nop
0x180014e00  lea     rcx, [rbp+var_10]
0x180014e04  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180014e09  nop
0x180014e0a  jmp     short loc_180014E81
0x180014e0c  mov     cs:?g_reenrollAik@@3KA, 0; ulong g_reenrollAik
0x180014e16  xor     r8d, r8d; unsigned __int16 *
0x180014e19  lea     rdx, stru_180025458; HKEY
0x180014e20  mov     rcx, [rbp+var_10]; this
0x180014e24  call    ?SetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBGK@Z; NgcUtils::SetRegistryDwordValue(HKEY__ *,ushort const *,ulong)
0x180014e29  mov     rcx, [rbp+8]; this
0x180014e2d  test    eax, eax
0x180014e2f  jns     short loc_180014E45
0x180014e31  mov     r9d, eax; char *
0x180014e34  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180014e3b  mov     edx, 5DDh; void *
0x180014e40  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014e45  xor     r8d, r8d; unsigned __int16 *
0x180014e48  lea     rdx, stru_180025478; HKEY
0x180014e4f  mov     rcx, [rbp+var_10]; this
0x180014e53  call    ?SetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBGK@Z; NgcUtils::SetRegistryDwordValue(HKEY__ *,ushort const *,ulong)
0x180014e58  mov     rcx, [rbp+8]; this
0x180014e5c  test    eax, eax
0x180014e5e  jns     short loc_180014E75
0x180014e60  mov     r9d, eax; char *
0x180014e63  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180014e6a  mov     edx, 5E3h; void *
0x180014e6f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014e74  nop
0x180014e75  lea     rcx, [rbp+var_10]
0x180014e79  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180014e7e  nop
0x180014e7f  xor     ebx, ebx
0x180014e81  lea     rcx, [rbp+lpSubKey]
0x180014e85  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014e8a  mov     eax, ebx
0x180014e8c  mov     rbx, [rsp+40h+arg_8]
0x180014e91  mov     rsi, [rsp+40h+arg_10]
0x180014e96  add     rsp, 40h
0x180014e9a  pop     rbp
0x180014e9b  retn
```
