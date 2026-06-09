# GetOpaqueBlobAndPinAndDelete(HKEY__ *,ushort const *,uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x18001bc90`
- end: `0x18001bee2`
- name: `?GetOpaqueBlobAndPinAndDelete@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAK23@Z`
- size: `594`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a170`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18001069c`
- `0x18001070c`
- `0x180011e48`
- `0x180013e3c`
- `0x180019818`
- `0x180019838`
- `0x180019868`
- `0x18001bc90`
- `0x180023124`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x18001bd2d`
- `ncrypt!NCryptSetProperty` at `0x18001bd2d`
- `ncrypt!NCryptOpenKey` at `0x18001bd66`
- `ncrypt!NCryptOpenKey` at `0x18001bd66`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001bcfd`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001bcfd`

## string_xrefs

- `0x18001bd3e`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001bd77`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001bddd`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001be54`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetOpaqueBlobAndPinAndDelete(
        HKEY a1,
        const unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  unsigned __int8 **v8; // r14
  __int64 v9; // rax
  SECURITY_STATUS v10; // eax
  int RegistryValue; // ebx
  __int64 v12; // rdx
  SECURITY_STATUS v13; // eax
  unsigned __int8 *v14; // rax
  unsigned __int8 *v15; // rax
  int dwFlags; // [rsp+28h] [rbp-49h]
  int dwFlagsa; // [rsp+28h] [rbp-49h]
  int dwFlagsb; // [rsp+28h] [rbp-49h]
  int dwFlagsc; // [rsp+28h] [rbp-49h]
  unsigned int *v21; // [rsp+30h] [rbp-41h]
  unsigned __int8 *v22; // [rsp+38h] [rbp-39h] BYREF
  unsigned __int8 *v23; // [rsp+40h] [rbp-31h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+48h] [rbp-29h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-21h] BYREF
  unsigned __int8 **v26; // [rsp+58h] [rbp-19h] BYREF
  unsigned int v27[2]; // [rsp+60h] [rbp-11h] BYREF
  char v28; // [rsp+68h] [rbp-9h]
  _BYTE v29[72]; // [rsp+70h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+4Fh]
  HKEY hkey; // [rsp+C8h] [rbp+57h] BYREF
  LPCWSTR pszKeyName; // [rsp+D0h] [rbp+5Fh] BYREF
  unsigned __int8 *v33; // [rsp+D8h] [rbp+67h] BYREF

  pszKeyName = a2;
  hkey = a1;
  *a3 = 0;
  v8 = a5;
  *a5 = 0;
  phKey = 0;
  v9 = lambda_84b30d09626fe4dbba818ee3995ceb42_::_lambda_84b30d09626fe4dbba818ee3995ceb42_(
         &v26,
         &hkey,
         &pszKeyName,
         &phKey);
  wil::ScopeExitIgnore__lambda_84b30d09626fe4dbba818ee3995ceb42___(v29, v9);
  phProvider = 0;
  v10 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  RegistryValue = v10;
  if ( v10 < 0 )
  {
    v12 = 853;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v10,
      dwFlags);
    goto LABEL_14;
  }
  v13 = NCryptSetProperty(phProvider, L"PCP_SESSIONID", (PBYTE)&byte_18002B490, 0x10u, 0);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35C,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)v13,
      dwFlagsa);
  v10 = NCryptOpenKey(phProvider, &phKey, pszKeyName, 0, 0x10000000u);
  RegistryValue = v10;
  if ( v10 < 0 )
  {
    v12 = 867;
    goto LABEL_7;
  }
  LODWORD(a5) = 0;
  v22 = 0;
  v26 = &v22;
  *(_QWORD *)v27 = 0;
  v28 = 1;
  RegistryValue = NgcUtils::ExportNCryptKey(phKey, L"OpaqueKeyBlob", 0, (unsigned int)v27, (unsigned __int8 **)&a5, v21);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v26);
  if ( RegistryValue >= 0 )
  {
    LODWORD(v33) = 0;
    v23 = 0;
    v26 = &v23;
    *(_QWORD *)v27 = 0;
    v28 = 1;
    RegistryValue = NgcUtils::GetRegistryValue(hkey, 0, pszKeyName, 8u, v27, &v33);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v26);
    if ( RegistryValue >= 0 )
    {
      v14 = v22;
      v22 = 0;
      *a3 = v14;
      *a4 = (unsigned int)a5;
      v15 = v23;
      v23 = 0;
      *v8 = v15;
      *a6 = (unsigned int)v33;
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v23,
        0);
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v22,
        0);
      RegistryValue = 0;
      goto LABEL_14;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x376,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)RegistryValue,
      dwFlagsc);
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v23, 0);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36C,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)RegistryValue,
      dwFlagsb);
  }
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v22, 0);
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  wil::details::ScopeExitFnGuard__lambda_84b30d09626fe4dbba818ee3995ceb42___::_ScopeExitFnGuard__lambda_84b30d09626fe4dbba818ee3995ceb42___(v29);
  return (unsigned int)RegistryValue;
}

```

## disassembly

```asm
0x18001bc90  mov     rax, rsp
0x18001bc93  mov     [rax+20h], rbx
0x18001bc97  mov     [rax+10h], rdx
0x18001bc9b  mov     [rax+8], rcx
0x18001bc9f  push    rbp
0x18001bca0  push    rsi
0x18001bca1  push    r12
0x18001bca3  push    r14
0x18001bca5  push    r15
0x18001bca7  lea     rbp, [rax-4Fh]
0x18001bcab  sub     rsp, 90h
0x18001bcb2  mov     r15, r9
0x18001bcb5  mov     rsi, r8
0x18001bcb8  xor     r12d, r12d
0x18001bcbb  mov     [r8], r12
0x18001bcbe  mov     r14, [rbp+47h+arg_20]
0x18001bcc2  mov     [r14], r12
0x18001bcc5  mov     [rbp+47h+phKey], r12
0x18001bcc9  lea     r9, [rbp+47h+phKey]
0x18001bccd  lea     r8, [rbp+47h+pszKeyName]
0x18001bcd1  lea     rdx, [rbp+47h+hkey]
0x18001bcd5  lea     rcx, [rbp+47h+var_60]
0x18001bcd9  call    _lambda_84b30d09626fe4dbba818ee3995ceb42____lambda_84b30d09626fe4dbba818ee3995ceb42_
0x18001bcde  mov     rdx, rax
0x18001bce1  lea     rcx, [rbp+47h+var_48]
0x18001bce5  call    wil__ScopeExitIgnore__lambda_84b30d09626fe4dbba818ee3995ceb42___
0x18001bcea  nop
0x18001bceb  mov     [rbp+47h+phProvider], r12
0x18001bcef  xor     r8d, r8d; dwFlags
0x18001bcf2  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x18001bcf9  lea     rcx, [rbp+47h+phProvider]; phProvider
0x18001bcfd  call    cs:__imp_NCryptOpenStorageProvider
0x18001bd03  mov     ebx, eax
0x18001bd05  test    eax, eax
0x18001bd07  jns     short loc_18001BD10
0x18001bd09  mov     edx, 355h
0x18001bd0e  jmp     short loc_18001BD77
0x18001bd10  mov     [rsp+0B0h+dwFlags], r12d; int
0x18001bd15  mov     r9d, 10h; cbInput
0x18001bd1b  lea     r8, byte_18002B490; pbInput
0x18001bd22  lea     rdx, aPcpSessionid; "PCP_SESSIONID"
0x18001bd29  mov     rcx, [rbp+47h+phProvider]; hObject
0x18001bd2d  call    cs:__imp_NCryptSetProperty
0x18001bd33  mov     rcx, [rbp+4Fh]; this
0x18001bd37  test    eax, eax
0x18001bd39  jns     short loc_18001BD4F
0x18001bd3b  mov     r9d, eax; char *
0x18001bd3e  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001bd45  mov     edx, 35Ch; void *
0x18001bd4a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001bd4f  mov     [rsp+0B0h+dwFlags], 10000000h; int
0x18001bd57  xor     r9d, r9d; dwLegacyKeySpec
0x18001bd5a  mov     r8, [rbp+47h+pszKeyName]; pszKeyName
0x18001bd5e  lea     rdx, [rbp+47h+phKey]; phKey
0x18001bd62  mov     rcx, [rbp+47h+phProvider]; hProvider
0x18001bd66  call    cs:__imp_NCryptOpenKey
0x18001bd6c  mov     ebx, eax
0x18001bd6e  test    eax, eax
0x18001bd70  jns     short loc_18001BD8F
0x18001bd72  mov     edx, 363h; void *
0x18001bd77  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001bd7e  mov     r9d, eax; char *
0x18001bd81  mov     rcx, [rbp+4Fh]; this
0x18001bd85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bd8a  jmp     loc_18001BEB5
0x18001bd8f  mov     dword ptr [rbp+47h+arg_20], r12d
0x18001bd93  mov     [rbp+47h+var_80], r12
0x18001bd97  lea     rax, [rbp+47h+var_80]
0x18001bd9b  mov     [rbp+47h+var_60], rax
0x18001bd9f  mov     qword ptr [rbp+47h+var_58], r12
0x18001bda3  mov     [rbp+47h+var_50], 1
0x18001bda7  lea     rax, [rbp+47h+arg_20]
0x18001bdab  mov     qword ptr [rsp+0B0h+dwFlags], rax; int
0x18001bdb0  lea     r9, [rbp+47h+var_58]; unsigned int
0x18001bdb4  xor     r8d, r8d; dwFlags
0x18001bdb7  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x18001bdbe  mov     rcx, [rbp+47h+phKey]; hKey
0x18001bdc2  call    ?ExportNCryptKey@NgcUtils@@YAJ_KPEBGKPEAPEAEPEAK@Z; NgcUtils::ExportNCryptKey(unsigned __int64,ushort const *,ulong,uchar * *,ulong *)
0x18001bdc7  mov     ebx, eax
0x18001bdc9  lea     rcx, [rbp+47h+var_60]
0x18001bdcd  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001bdd2  test    ebx, ebx
0x18001bdd4  jns     short loc_18001BDFF
0x18001bdd6  mov     rcx, [rbp+4Fh]; this
0x18001bdda  mov     r9d, ebx; char *
0x18001bddd  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001bde4  mov     edx, 36Ch; void *
0x18001bde9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bdee  nop
0x18001bdef  xor     edx, edx
0x18001bdf1  lea     rcx, [rbp+47h+var_80]
0x18001bdf5  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001bdfa  jmp     loc_18001BEB5
0x18001bdff  mov     dword ptr [rbp+47h+arg_10], r12d
0x18001be03  mov     [rbp+47h+var_78], r12
0x18001be07  lea     rax, [rbp+47h+var_78]
0x18001be0b  mov     [rbp+47h+var_60], rax
0x18001be0f  mov     qword ptr [rbp+47h+var_58], r12
0x18001be13  mov     [rbp+47h+var_50], 1
0x18001be17  lea     rax, [rbp+47h+arg_10]
0x18001be1b  mov     [rsp+28h], rax; unsigned __int8 **
0x18001be20  lea     rax, [rbp+47h+var_58]
0x18001be24  mov     qword ptr [rsp+0B0h+dwFlags], rax; int
0x18001be29  mov     r9d, 8; dwFlags
0x18001be2f  mov     r8, [rbp+47h+pszKeyName]; lpValue
0x18001be33  xor     edx, edx; lpSubKey
0x18001be35  mov     rcx, [rbp+47h+hkey]; hkey
0x18001be39  call    ?GetRegistryValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1KPEAPEAEPEAK@Z; NgcUtils::GetRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x18001be3e  mov     ebx, eax
0x18001be40  lea     rcx, [rbp+47h+var_60]
0x18001be44  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001be49  test    ebx, ebx
0x18001be4b  jns     short loc_18001BE76
0x18001be4d  mov     rcx, [rbp+4Fh]; this
0x18001be51  mov     r9d, ebx; char *
0x18001be54  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001be5b  mov     edx, 376h; void *
0x18001be60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001be65  nop
0x18001be66  xor     edx, edx
0x18001be68  lea     rcx, [rbp+47h+var_78]
0x18001be6c  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001be71  jmp     loc_18001BDEF
0x18001be76  mov     rax, [rbp+47h+var_80]
0x18001be7a  mov     [rbp+47h+var_80], r12
0x18001be7e  mov     [rsi], rax
0x18001be81  mov     eax, dword ptr [rbp+47h+arg_20]
0x18001be84  mov     [r15], eax
0x18001be87  mov     rax, [rbp+47h+var_78]
0x18001be8b  mov     [rbp+47h+var_78], r12
0x18001be8f  mov     [r14], rax
0x18001be92  mov     rcx, [rbp+47h+arg_28]
0x18001be96  mov     eax, dword ptr [rbp+47h+arg_10]
0x18001be99  mov     [rcx], eax
0x18001be9b  xor     edx, edx
0x18001be9d  lea     rcx, [rbp+47h+var_78]
0x18001bea1  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001bea6  nop
0x18001bea7  xor     edx, edx
0x18001bea9  lea     rcx, [rbp+47h+var_80]
0x18001bead  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001beb2  mov     ebx, r12d
0x18001beb5  lea     rcx, [rbp+47h+phProvider]
0x18001beb9  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001bebe  nop
0x18001bebf  lea     rcx, [rbp+47h+var_48]
0x18001bec3  call    wil__details__ScopeExitFnGuard__lambda_84b30d09626fe4dbba818ee3995ceb42______ScopeExitFnGuard__lambda_84b30d09626fe4dbba818ee3995ceb42___
0x18001bec8  mov     eax, ebx
0x18001beca  mov     rbx, [rsp+0B0h+arg_18]
0x18001bed2  add     rsp, 90h
0x18001bed9  pop     r15
0x18001bedb  pop     r14
0x18001bedd  pop     r12
0x18001bedf  pop     rsi
0x18001bee0  pop     rbp
0x18001bee1  retn
```
