# NgcKeyTransportKey::OpenKeyBasedOnKeyDatabase(_NGC_IDP_ACCOUNT_INFO *,ushort const *)

- ea: `0x180019424`
- end: `0x1800196ac`
- name: `?OpenKeyBasedOnKeyDatabase@NgcKeyTransportKey@@AEAAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBG@Z`
- size: `648`
- prototype: `__int64 __fastcall(NgcKeyTransportKey *this, struct _NGC_IDP_ACCOUNT_INFO *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012858`
- `0x1800193d4`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18000db5c`
- `0x18001069c`
- `0x18001070c`
- `0x180010730`
- `0x180011e48`
- `0x180015000`
- `0x1800152f4`
- `0x1800177f4`
- `0x180019424`
- `0x180022ef4`
- `0x180023124`
- `0x180028010`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x1800195f3`
- `ncrypt!NCryptSetProperty` at `0x1800195f3`
- `ncrypt!NCryptOpenKey` at `0x180019631`
- `ncrypt!NCryptOpenKey` at `0x180019631`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800195a8`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800195a8`

## string_xrefs

- `0x1800194a7`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`
- `0x180019553`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`
- `0x180019604`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`
- `0x180019644`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`

## pseudocode

```c
__int64 __fastcall NgcKeyTransportKey::OpenKeyBasedOnKeyDatabase(
        NgcKeyTransportKey *this,
        struct _NGC_IDP_ACCOUNT_INFO *a2,
        const unsigned __int16 *a3)
{
  unsigned __int16 **v6; // rsi
  const unsigned __int16 *v7; // rdx
  NgcUtils *v8; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int RegistryValue; // ebx
  __int64 v11; // rdx
  const WCHAR *v12; // rax
  unsigned __int64 v13; // r8
  __int64 v14; // rdx
  unsigned __int64 v15; // r9
  const WCHAR *v16; // r15
  const WCHAR *v17; // rax
  const unsigned __int16 *v18; // r8
  NgcUtils *v19; // r14
  NCRYPT_HANDLE *v20; // rsi
  SECURITY_STATUS v21; // eax
  DWORD v22; // ebx
  SECURITY_STATUS v23; // eax
  SECURITY_STATUS v24; // eax
  LPCWSTR v25; // rax
  NCRYPT_KEY_HANDLE v26; // rax
  unsigned __int16 **dwFlags; // [rsp+20h] [rbp-30h]
  int dwFlagsa; // [rsp+20h] [rbp-30h]
  int dwFlagsb; // [rsp+20h] [rbp-30h]
  int dwFlagsc; // [rsp+20h] [rbp-30h]
  int dwFlagsd; // [rsp+20h] [rbp-30h]
  LPCWSTR pszKeyName; // [rsp+30h] [rbp-20h] BYREF
  LPCWSTR *p_pszKeyName; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v35[2]; // [rsp+40h] [rbp-10h] BYREF
  char v36; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  unsigned __int8 *v38; // [rsp+80h] [rbp+30h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+98h] [rbp+48h] BYREF

  v6 = (unsigned __int16 **)((char *)this + 24);
  if ( *((_QWORD *)this + 3) )
    goto LABEL_8;
  v38 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v38,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v8,
                                        v7,
                                        L"KeyTransportKey",
                                        (const unsigned __int16 *)&v38,
                                        dwFlags);
  RegistryValue = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    NgcStateSeparatedRegistryLocation = GetPopRegLocationForKeyMapping(
                                          a2,
                                          a3,
                                          (const unsigned __int16 *)v38,
                                          L"PerDeviceKeyTransportKey",
                                          v6);
    RegistryValue = NgcStateSeparatedRegistryLocation;
    if ( NgcStateSeparatedRegistryLocation < 0 )
    {
      v11 = 101;
      goto LABEL_6;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
LABEL_8:
    LODWORD(v38) = 0;
    pszKeyName = 0;
    p_pszKeyName = &pszKeyName;
    *(_QWORD *)v35 = 0;
    v36 = 1;
    v12 = (const WCHAR *)(*(__int64 (__fastcall **)(NgcKeyTransportKey *))(*(_QWORD *)this + 24LL))(this);
    RegistryValue = NgcUtils::GetRegistryValue(
                      HKEY_LOCAL_MACHINE,
                      (HKEY)*v6,
                      v12,
                      2u,
                      (unsigned int)v35,
                      &v38,
                      (unsigned int *)pszKeyName);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_pszKeyName);
    if ( (RegistryValue & 0x80000000) == 0 )
    {
      if ( (_DWORD)v38 )
      {
        v16 = pszKeyName;
        if ( NgcUtils::IsStringNullTerminated(
               (NgcUtils *)pszKeyName,
               (const unsigned __int16 *)((unsigned int)v38 + 2LL),
               v13) )
        {
          v17 = (const WCHAR *)(*(__int64 (__fastcall **)(NgcKeyTransportKey *))(*(_QWORD *)this + 8LL))(this);
          v19 = (NgcUtils *)v17;
          v20 = (NCRYPT_HANDLE *)((char *)this + 16);
          if ( *((_QWORD *)this + 2)
            || (v21 = NCryptOpenStorageProvider((NCRYPT_PROV_HANDLE *)this + 2, v17, 0), RegistryValue = v21, v21 >= 0) )
          {
            v22 = 64;
            if ( NgcUtils::AreStringsEqual(v19, L"Microsoft Platform Crypto Provider", v18) )
            {
              v23 = NCryptSetProperty(*v20, L"PCP_SESSIONID", (PBYTE)&byte_18002B068, 0x10u, 0);
              if ( v23 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x87,
                  (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
                  (const char *)(unsigned int)v23,
                  dwFlagsc);
              v22 = 268435520;
            }
            phKey = 0;
            v24 = NCryptOpenKey(*v20, &phKey, v16, 0, v22);
            RegistryValue = v24;
            if ( v24 >= 0 )
            {
              v25 = pszKeyName;
              pszKeyName = 0;
              *((_QWORD *)this + 4) = v25;
              v26 = phKey;
              phKey = 0;
              *((_QWORD *)this + 1) = v26;
              wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
              RegistryValue = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x92,
                (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
                (const char *)(unsigned int)v24,
                dwFlagsd);
              wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
            }
            goto LABEL_27;
          }
          v15 = (unsigned int)v21;
          v14 = 124;
LABEL_14:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v14,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
            (const char *)v15,
            dwFlagsb);
LABEL_27:
          wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
            &pszKeyName,
            0);
          return RegistryValue;
        }
        v14 = 116;
      }
      else
      {
        v14 = 115;
      }
      RegistryValue = -2147024883;
    }
    else
    {
      v14 = 112;
    }
    v15 = RegistryValue;
    goto LABEL_14;
  }
  v11 = 94;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
    (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
    dwFlagsa);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
  return RegistryValue;
}

```

## disassembly

```asm
0x180019424  mov     [rsp-28h+arg_8], rbx
0x180019429  push    rbp
0x18001942a  push    rsi
0x18001942b  push    rdi
0x18001942c  push    r14
0x18001942e  push    r15
0x180019430  mov     rbp, rsp
0x180019433  sub     rsp, 50h
0x180019437  mov     r14, r8
0x18001943a  mov     r15, rdx
0x18001943d  mov     rdi, rcx
0x180019440  lea     rsi, [rcx+18h]
0x180019444  cmp     qword ptr [rsi], 0
0x180019448  jnz     loc_1800194CF
0x18001944e  mov     [rbp+arg_0], 0
0x180019456  xor     edx, edx
0x180019458  lea     rcx, [rbp+arg_0]
0x18001945c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180019461  lea     r9, [rbp+arg_0]; unsigned __int16 *
0x180019465  lea     r8, aKeytransportke; "KeyTransportKey"
0x18001946c  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180019471  mov     ebx, eax
0x180019473  test    eax, eax
0x180019475  jns     short loc_18001947E
0x180019477  mov     edx, 5Eh ; '^'
0x18001947c  jmp     short loc_1800194A4
0x18001947e  mov     qword ptr [rsp+50h+dwFlags], rsi; int
0x180019483  lea     r9, aPerdevicekeytr; "PerDeviceKeyTransportKey"
0x18001948a  mov     r8, [rbp+arg_0]; unsigned __int16 *
0x18001948e  mov     rdx, r14; unsigned __int16 *
0x180019491  mov     rcx, r15; struct _NGC_IDP_ACCOUNT_INFO *
0x180019494  call    ?GetPopRegLocationForKeyMapping@@YAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBG11PEAPEAG@Z; GetPopRegLocationForKeyMapping(_NGC_IDP_ACCOUNT_INFO *,ushort const *,ushort const *,ushort const *,ushort * *)
0x180019499  mov     ebx, eax
0x18001949b  test    eax, eax
0x18001949d  jns     short loc_1800194C6
0x18001949f  mov     edx, 65h ; 'e'; void *
0x1800194a4  mov     r9d, eax; char *
0x1800194a7  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800194ae  mov     rcx, [rbp+28h]; this
0x1800194b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800194b7  nop
0x1800194b8  lea     rcx, [rbp+arg_0]
0x1800194bc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800194c1  jmp     loc_180019696
0x1800194c6  lea     rcx, [rbp+arg_0]
0x1800194ca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800194cf  mov     dword ptr [rbp+arg_0], 0
0x1800194d6  mov     [rbp+pszKeyName], 0
0x1800194de  lea     rax, [rbp+pszKeyName]
0x1800194e2  mov     [rbp+var_18], rax
0x1800194e6  mov     qword ptr [rbp+var_10], 0
0x1800194ee  mov     [rbp+var_8], 1
0x1800194f2  mov     rax, [rdi]
0x1800194f5  mov     rcx, rdi
0x1800194f8  mov     rax, [rax+18h]
0x1800194fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019501  lea     rcx, [rbp+arg_0]
0x180019505  mov     [rsp+50h+var_28], rcx; unsigned __int8 **
0x18001950a  lea     rcx, [rbp+var_10]
0x18001950e  mov     qword ptr [rsp+50h+dwFlags], rcx; int
0x180019513  mov     r9d, 2; dwFlags
0x180019519  mov     r8, rax; lpValue
0x18001951c  mov     rdx, [rsi]; lpSubKey
0x18001951f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180019526  call    ?GetRegistryValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1KPEAPEAEPEAK@Z; NgcUtils::GetRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x18001952b  mov     ebx, eax
0x18001952d  lea     rcx, [rbp+var_18]
0x180019531  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180019536  test    ebx, ebx
0x180019538  jns     short loc_180019541
0x18001953a  mov     edx, 70h ; 'p'
0x18001953f  jmp     short loc_180019550
0x180019541  mov     eax, dword ptr [rbp+arg_0]
0x180019544  test    eax, eax
0x180019546  jnz     short loc_180019568
0x180019548  lea     edx, [rax+73h]; void *
0x18001954b  mov     ebx, 8007000Dh
0x180019550  mov     r9d, ebx; char *
0x180019553  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001955a  mov     rcx, [rbp+28h]; this
0x18001955e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019563  jmp     loc_18001968B
0x180019568  mov     r15, [rbp+pszKeyName]
0x18001956c  lea     rdx, [rax+2]; unsigned __int16 *
0x180019570  mov     rcx, r15; this
0x180019573  call    ?IsStringNullTerminated@NgcUtils@@YA_NPEBG_K@Z; NgcUtils::IsStringNullTerminated(ushort const *,unsigned __int64)
0x180019578  test    al, al
0x18001957a  jnz     short loc_180019583
0x18001957c  mov     edx, 74h ; 't'
0x180019581  jmp     short loc_18001954B
0x180019583  mov     rax, [rdi]
0x180019586  mov     rcx, rdi
0x180019589  mov     rax, [rax+8]
0x18001958d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019592  mov     r14, rax
0x180019595  lea     rsi, [rdi+10h]
0x180019599  cmp     qword ptr [rsi], 0
0x18001959d  jnz     short loc_1800195BE
0x18001959f  xor     r8d, r8d; dwFlags
0x1800195a2  mov     rdx, rax; pszProviderName
0x1800195a5  mov     rcx, rsi; phProvider
0x1800195a8  call    cs:__imp_NCryptOpenStorageProvider
0x1800195ae  mov     ebx, eax
0x1800195b0  test    eax, eax
0x1800195b2  jns     short loc_1800195BE
0x1800195b4  mov     r9d, eax
0x1800195b7  mov     edx, 7Ch ; '|'
0x1800195bc  jmp     short loc_180019553
0x1800195be  mov     ebx, 40h ; '@'
0x1800195c3  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x1800195ca  mov     rcx, r14; this
0x1800195cd  call    ?AreStringsEqual@NgcUtils@@YA_NPEBG0@Z; NgcUtils::AreStringsEqual(ushort const *,ushort const *)
0x1800195d2  test    al, al
0x1800195d4  jz      short loc_180019618
0x1800195d6  mov     [rsp+50h+dwFlags], 0; int
0x1800195de  lea     r9d, [rbx-30h]; cbInput
0x1800195e2  lea     r8, byte_18002B068; pbInput
0x1800195e9  lea     rdx, aPcpSessionid; "PCP_SESSIONID"
0x1800195f0  mov     rcx, [rsi]; hObject
0x1800195f3  call    cs:__imp_NCryptSetProperty
0x1800195f9  mov     rcx, [rbp+28h]; this
0x1800195fd  test    eax, eax
0x1800195ff  jns     short loc_180019613
0x180019601  mov     r9d, eax; char *
0x180019604  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001960b  lea     edx, [rbx+47h]; void *
0x18001960e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180019613  mov     ebx, 10000040h
0x180019618  mov     [rbp+phKey], 0
0x180019620  mov     [rsp+50h+dwFlags], ebx; int
0x180019624  xor     r9d, r9d; dwLegacyKeySpec
0x180019627  mov     r8, r15; pszKeyName
0x18001962a  lea     rdx, [rbp+phKey]; phKey
0x18001962e  mov     rcx, [rsi]; hProvider
0x180019631  call    cs:__imp_NCryptOpenKey
0x180019637  mov     ebx, eax
0x180019639  test    eax, eax
0x18001963b  jns     short loc_180019660
0x18001963d  mov     rcx, [rbp+28h]; this
0x180019641  mov     r9d, eax; char *
0x180019644  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001964b  mov     edx, 92h; void *
0x180019650  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019655  lea     rcx, [rbp+phKey]
0x180019659  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001965e  jmp     short loc_18001968B
0x180019660  mov     rax, [rbp+pszKeyName]
0x180019664  mov     [rbp+pszKeyName], 0
0x18001966c  mov     [rdi+20h], rax
0x180019670  mov     rax, [rbp+phKey]
0x180019674  mov     [rbp+phKey], 0
0x18001967c  mov     [rdi+8], rax
0x180019680  lea     rcx, [rbp+phKey]
0x180019684  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180019689  xor     ebx, ebx
0x18001968b  xor     edx, edx
0x18001968d  lea     rcx, [rbp+pszKeyName]
0x180019691  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180019696  mov     eax, ebx
0x180019698  mov     rbx, [rsp+50h+arg_8]
0x1800196a0  add     rsp, 50h
0x1800196a4  pop     r15
0x1800196a6  pop     r14
0x1800196a8  pop     rdi
0x1800196a9  pop     rsi
0x1800196aa  pop     rbp
0x1800196ab  retn
```
