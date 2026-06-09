# SoftwareKeyTransKey::CreateNewKey(_SECURITY_DESCRIPTOR *,ulong,ushort * *)

- ea: `0x1800187a0`
- end: `0x180018a4c`
- name: `?CreateNewKey@SoftwareKeyTransKey@@MEAAJPEAU_SECURITY_DESCRIPTOR@@KPEAPEAG@Z`
- size: `684`
- prototype: `int(SoftwareKeyTransKey *__hidden this, struct _SECURITY_DESCRIPTOR *, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800012e8`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000da94`
- `0x18000db5c`
- `0x180010730`
- `0x180010784`
- `0x180013f9c`
- `0x180014918`
- `0x18001496c`
- `0x180018704`
- `0x18001874c`
- `0x1800187a0`
- `0x180028010`

## import_xrefs

- `ncrypt!NCryptFinalizeKey` at `0x1800189bb`
- `ncrypt!NCryptFinalizeKey` at `0x1800189bb`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800188f2`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800188f2`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001885f`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001885f`

## string_xrefs

- `0x180018872`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\softwarekeytranskey.cpp`
- `0x1800188ad`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\softwarekeytranskey.cpp`
- `0x180018905`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\softwarekeytranskey.cpp`
- `0x18001894e`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\softwarekeytranskey.cpp`
- `0x1800189ce`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\softwarekeytranskey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SoftwareKeyTransKey::CreateNewKey(
        SoftwareKeyTransKey *this,
        struct _SECURITY_DESCRIPTOR *a2,
        __int64 a3,
        unsigned __int16 **a4)
{
  _DWORD *v7; // r9
  const WCHAR *v8; // rax
  SECURITY_STATUS v9; // eax
  unsigned int v10; // ebx
  unsigned __int16 **v11; // rdx
  int v12; // eax
  NCRYPT_HANDLE *v13; // rbx
  unsigned __int16 *v14; // r14
  SECURITY_STATUS PersistedKey; // eax
  struct _SECURITY_DESCRIPTOR *v16; // r8
  SECURITY_STATUS v17; // esi
  int v18; // edi
  unsigned int v19; // r9d
  __int64 v20; // rdx
  unsigned int v21; // r9d
  SECURITY_STATUS v22; // eax
  DWORD dwLegacyKeySpec; // [rsp+20h] [rbp-49h]
  DWORD dwLegacyKeySpeca; // [rsp+20h] [rbp-49h]
  LPCWSTR pszKeyName; // [rsp+30h] [rbp-39h] BYREF
  SoftwareKeyTransKey *v27; // [rsp+38h] [rbp-31h] BYREF
  __int16 v28; // [rsp+40h] [rbp-29h]
  int *v29; // [rsp+48h] [rbp-21h] BYREF
  __int16 v30; // [rsp+50h] [rbp-19h]
  int v31; // [rsp+58h] [rbp-11h] BYREF
  char v32; // [rsp+5Ch] [rbp-Dh]
  _BYTE v33[16]; // [rsp+60h] [rbp-9h] BYREF
  _DWORD v34[4]; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v31 = 0;
  v32 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v31);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    if ( v32 && (v34[0] || v34[1] || v34[2] || v34[3]) )
      v7 = v34;
    else
      v7 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180037000,
      &dword_18002ECAC,
      v33,
      v7);
  }
  v29 = &v31;
  v30 = 256;
  if ( *((_QWORD *)this + 2)
    || (v8 = (const WCHAR *)(*(__int64 (__fastcall **)(SoftwareKeyTransKey *))(*(_QWORD *)this + 8LL))(this),
        v9 = NCryptOpenStorageProvider((NCRYPT_PROV_HANDLE *)this + 2, v8, 0),
        v10 = v9,
        v9 >= 0) )
  {
    pszKeyName = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszKeyName,
      0);
    v12 = NgcUtils::GenRandomGuid((NgcUtils *)&pszKeyName, v11);
    v10 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\softwarekeytranskey.cpp",
        (const char *)(unsigned int)v12,
        dwLegacyKeySpec);
LABEL_15:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
      goto LABEL_28;
    }
    v13 = (NCRYPT_HANDLE *)((char *)this + 8);
    v14 = (unsigned __int16 *)pszKeyName;
    PersistedKey = NCryptCreatePersistedKey(
                     *((_QWORD *)this + 2),
                     (NCRYPT_KEY_HANDLE *)this + 1,
                     L"RSA",
                     pszKeyName,
                     0,
                     0x40u);
    v17 = PersistedKey;
    if ( PersistedKey < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\softwarekeytranskey.cpp",
        (const char *)(unsigned int)PersistedKey,
        dwLegacyKeySpeca);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
      v10 = v17;
      goto LABEL_28;
    }
    v27 = this;
    v28 = 256;
    v18 = NgcUtils::SetNCryptSecurityDescriptor(*v13, a2, v16);
    if ( v18 >= 0 )
    {
      v18 = NgcUtils::SetNCryptDwordProperty((NgcUtils *)*v13, (unsigned __int64)L"Export Policy", 0, v19);
      if ( v18 >= 0 )
      {
        v18 = NgcUtils::SetNCryptDwordProperty(
                (NgcUtils *)*v13,
                (unsigned __int64)L"Length",
                (const unsigned __int16 *)0x800,
                v21);
        if ( v18 >= 0 )
        {
          v22 = NCryptFinalizeKey(*v13, 0);
          v10 = v22;
          if ( v22 >= 0 )
          {
            HIBYTE(v28) = 0;
            pszKeyName = 0;
            *a4 = v14;
            wil::details::ScopeExitFnGuard__lambda_b77dc92ef505b91b2d7e2ba3e88216b8___::operator()(&v27);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
            v10 = 0;
            goto LABEL_28;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5D,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\softwarekeytranskey.cpp",
            (const char *)(unsigned int)v22,
            dwLegacyKeySpeca);
          wil::details::ScopeExitFnGuard__lambda_b77dc92ef505b91b2d7e2ba3e88216b8___::operator()(&v27);
          goto LABEL_15;
        }
        v20 = 89;
      }
      else
      {
        v20 = 84;
      }
    }
    else
    {
      v20 = 79;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\softwarekeytranskey.cpp",
      (const char *)(unsigned int)v18,
      dwLegacyKeySpeca);
    wil::details::ScopeExitFnGuard__lambda_b77dc92ef505b91b2d7e2ba3e88216b8___::operator()(&v27);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
    v10 = v18;
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x34,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\softwarekeytranskey.cpp",
    (const char *)(unsigned int)v9,
    dwLegacyKeySpec);
LABEL_28:
  wil::details::ScopeExitFnGuard__lambda_49562c3b8faef8a0b45e6404d2abc10f___::operator()(&v29);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v31);
  return v10;
}

```

## disassembly

```asm
0x1800187a0  mov     [rsp-8+arg_10], rbx
0x1800187a5  push    rbp
0x1800187a6  push    rsi
0x1800187a7  push    rdi
0x1800187a8  push    r12
0x1800187aa  push    r13
0x1800187ac  push    r14
0x1800187ae  push    r15
0x1800187b0  lea     rbp, [rsp-27h]
0x1800187b5  sub     rsp, 90h
0x1800187bc  mov     rax, cs:__security_cookie
0x1800187c3  xor     rax, rsp
0x1800187c6  mov     [rbp+57h+var_40], rax
0x1800187ca  mov     r12, r9
0x1800187cd  mov     r15, rdx
0x1800187d0  mov     rdi, rcx
0x1800187d3  xor     r13d, r13d
0x1800187d6  mov     [rbp+57h+var_68], r13d
0x1800187da  mov     [rbp+57h+var_64], r13b
0x1800187de  lea     rcx, [rbp+57h+var_68]
0x1800187e2  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x1800187e7  mov     eax, cs:dword_180037000
0x1800187ed  cmp     eax, 5
0x1800187f0  jbe     short loc_180018830
0x1800187f2  cmp     [rbp+57h+var_64], r13b
0x1800187f6  jz      short loc_180018816
0x1800187f8  cmp     [rbp+57h+var_50], r13d
0x1800187fc  jnz     short loc_180018810
0x1800187fe  cmp     [rbp+57h+var_4C], r13d
0x180018802  jnz     short loc_180018810
0x180018804  cmp     [rbp+57h+var_48], r13d
0x180018808  jnz     short loc_180018810
0x18001880a  cmp     [rbp+57h+var_44], r13d
0x18001880e  jz      short loc_180018816
0x180018810  lea     r9, [rbp+57h+var_50]
0x180018814  jmp     short loc_180018819
0x180018816  mov     r9, r13
0x180018819  lea     r8, [rbp+57h+var_60]
0x18001881d  lea     rdx, dword_18002ECAC
0x180018824  lea     rcx, dword_180037000
0x18001882b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180018830  lea     rax, [rbp+57h+var_68]
0x180018834  mov     [rbp+57h+var_78], rax
0x180018838  mov     [rbp+57h+var_70], 100h
0x18001883e  lea     rsi, [rdi+10h]
0x180018842  cmp     [rsi], r13
0x180018845  jnz     short loc_180018888
0x180018847  mov     rax, [rdi]
0x18001884a  mov     rcx, rdi
0x18001884d  mov     rax, [rax+8]
0x180018851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018856  mov     rdx, rax; pszProviderName
0x180018859  xor     r8d, r8d; dwFlags
0x18001885c  mov     rcx, rsi; phProvider
0x18001885f  call    cs:__imp_NCryptOpenStorageProvider
0x180018865  mov     ebx, eax
0x180018867  test    eax, eax
0x180018869  jns     short loc_180018888
0x18001886b  mov     rcx, [rbp+5Fh]; this
0x18001886f  mov     r9d, eax; char *
0x180018872  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180018879  mov     edx, 34h ; '4'; void *
0x18001887e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018883  jmp     loc_180018A10
0x180018888  mov     [rbp+57h+pszKeyName], r13
0x18001888c  xor     edx, edx
0x18001888e  lea     rcx, [rbp+57h+pszKeyName]
0x180018892  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180018897  lea     rcx, [rbp+57h+pszKeyName]; this
0x18001889b  call    ?GenRandomGuid@NgcUtils@@YAJPEAPEAG@Z; NgcUtils::GenRandomGuid(ushort * *)
0x1800188a0  mov     ebx, eax
0x1800188a2  test    eax, eax
0x1800188a4  jns     short loc_1800188CD
0x1800188a6  mov     rcx, [rbp+5Fh]; this
0x1800188aa  mov     r9d, eax; char *
0x1800188ad  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800188b4  mov     edx, 39h ; '9'; void *
0x1800188b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800188be  nop
0x1800188bf  lea     rcx, [rbp+57h+pszKeyName]
0x1800188c3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800188c8  jmp     loc_180018A10
0x1800188cd  lea     rbx, [rdi+8]
0x1800188d1  mov     [rsp+0C0h+dwFlags], 40h ; '@'; dwFlags
0x1800188d9  mov     [rsp+0C0h+dwLegacyKeySpec], r13d; int
0x1800188de  mov     r14, [rbp+57h+pszKeyName]
0x1800188e2  mov     r9, r14; pszKeyName
0x1800188e5  lea     r8, pszAlgId; "RSA"
0x1800188ec  mov     rdx, rbx; phKey
0x1800188ef  mov     rcx, [rsi]; hProvider
0x1800188f2  call    cs:__imp_NCryptCreatePersistedKey
0x1800188f8  mov     esi, eax
0x1800188fa  test    eax, eax
0x1800188fc  jns     short loc_180018927
0x1800188fe  mov     rcx, [rbp+5Fh]; this
0x180018902  mov     r9d, eax; char *
0x180018905  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001890c  mov     edx, 41h ; 'A'; void *
0x180018911  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018916  nop
0x180018917  lea     rcx, [rbp+57h+pszKeyName]
0x18001891b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180018920  mov     ebx, esi
0x180018922  jmp     loc_180018A10
0x180018927  mov     [rbp+57h+var_88], rdi
0x18001892b  mov     [rbp+57h+var_80], 100h
0x180018931  mov     rdx, r15; AbsoluteSD
0x180018934  mov     rcx, [rbx]; hObject
0x180018937  call    ?SetNCryptSecurityDescriptor@NgcUtils@@YAJ_KPEAU_SECURITY_DESCRIPTOR@@@Z; NgcUtils::SetNCryptSecurityDescriptor(unsigned __int64,_SECURITY_DESCRIPTOR *)
0x18001893c  mov     edi, eax
0x18001893e  test    eax, eax
0x180018940  jns     short loc_180018975
0x180018942  mov     edx, 4Fh ; 'O'; void *
0x180018947  mov     rcx, [rbp+5Fh]; this
0x18001894b  mov     r9d, edi; char *
0x18001894e  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180018955  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001895a  nop
0x18001895b  lea     rcx, [rbp+57h+var_88]
0x18001895f  call    wil__details__ScopeExitFnGuard__lambda_b77dc92ef505b91b2d7e2ba3e88216b8_____operator__
0x180018964  nop
0x180018965  lea     rcx, [rbp+57h+pszKeyName]
0x180018969  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001896e  mov     ebx, edi
0x180018970  jmp     loc_180018A10
0x180018975  xor     r8d, r8d; unsigned __int16 *
0x180018978  lea     rdx, aExportPolicy; "Export Policy"
0x18001897f  mov     rcx, [rbx]; this
0x180018982  call    ?SetNCryptDwordProperty@NgcUtils@@YAJ_KPEBGK@Z; NgcUtils::SetNCryptDwordProperty(unsigned __int64,ushort const *,ulong)
0x180018987  mov     edi, eax
0x180018989  test    eax, eax
0x18001898b  jns     short loc_180018994
0x18001898d  mov     edx, 54h ; 'T'
0x180018992  jmp     short loc_180018947
0x180018994  mov     r8d, 800h; unsigned __int16 *
0x18001899a  lea     rdx, aLength; "Length"
0x1800189a1  mov     rcx, [rbx]; this
0x1800189a4  call    ?SetNCryptDwordProperty@NgcUtils@@YAJ_KPEBGK@Z; NgcUtils::SetNCryptDwordProperty(unsigned __int64,ushort const *,ulong)
0x1800189a9  mov     edi, eax
0x1800189ab  test    eax, eax
0x1800189ad  jns     short loc_1800189B6
0x1800189af  mov     edx, 59h ; 'Y'
0x1800189b4  jmp     short loc_180018947
0x1800189b6  xor     edx, edx; dwFlags
0x1800189b8  mov     rcx, [rbx]; hKey
0x1800189bb  call    cs:__imp_NCryptFinalizeKey
0x1800189c1  mov     ebx, eax
0x1800189c3  test    eax, eax
0x1800189c5  jns     short loc_1800189EE
0x1800189c7  mov     rcx, [rbp+5Fh]; this
0x1800189cb  mov     r9d, eax; char *
0x1800189ce  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800189d5  mov     edx, 5Dh ; ']'; void *
0x1800189da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800189df  nop
0x1800189e0  lea     rcx, [rbp+57h+var_88]
0x1800189e4  call    wil__details__ScopeExitFnGuard__lambda_b77dc92ef505b91b2d7e2ba3e88216b8_____operator__
0x1800189e9  jmp     loc_1800188BF
0x1800189ee  mov     byte ptr [rbp+57h+var_80+1], r13b
0x1800189f2  mov     [rbp+57h+pszKeyName], r13
0x1800189f6  mov     [r12], r14
0x1800189fa  lea     rcx, [rbp+57h+var_88]
0x1800189fe  call    wil__details__ScopeExitFnGuard__lambda_b77dc92ef505b91b2d7e2ba3e88216b8_____operator__
0x180018a03  nop
0x180018a04  lea     rcx, [rbp+57h+pszKeyName]
0x180018a08  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180018a0d  mov     ebx, r13d
0x180018a10  lea     rcx, [rbp+57h+var_78]
0x180018a14  call    wil__details__ScopeExitFnGuard__lambda_49562c3b8faef8a0b45e6404d2abc10f_____operator__
0x180018a19  nop
0x180018a1a  lea     rcx, [rbp+57h+var_68]
0x180018a1e  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180018a23  mov     eax, ebx
0x180018a25  mov     rcx, [rbp+57h+var_40]
0x180018a29  xor     rcx, rsp; StackCookie
0x180018a2c  call    __security_check_cookie
0x180018a31  mov     rbx, [rsp+0C0h+arg_10]
0x180018a39  add     rsp, 90h
0x180018a40  pop     r15
0x180018a42  pop     r14
0x180018a44  pop     r13
0x180018a46  pop     r12
0x180018a48  pop     rdi
0x180018a49  pop     rsi
0x180018a4a  pop     rbp
0x180018a4b  retn
```
