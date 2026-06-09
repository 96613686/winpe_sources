# TpmKeyTransKey::CreateNewKey(_SECURITY_DESCRIPTOR *,ulong,ushort * *)

- ea: `0x180017f60`
- end: `0x180018198`
- name: `?CreateNewKey@TpmKeyTransKey@@MEAAJPEAU_SECURITY_DESCRIPTOR@@KPEAPEAG@Z`
- size: `568`
- prototype: `__int64 __fastcall(TpmKeyTransKey *this, struct _SECURITY_DESCRIPTOR *, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800012e8`
- `0x180004de0`
- `0x18000b0fc`
- `0x18000da94`
- `0x18000db5c`
- `0x18001069c`
- `0x180010730`
- `0x180010784`
- `0x18001496c`
- `0x180017ebc`
- `0x180017f30`
- `0x180017f60`
- `0x18001d070`
- `0x180028010`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x180018093`
- `ncrypt!NCryptSetProperty` at `0x180018093`
- `ncrypt!NCryptFreeObject` at `0x1800180c1`
- `ncrypt!NCryptFreeObject` at `0x1800180c1`
- `ncrypt!NCryptOpenKey` at `0x1800180dc`
- `ncrypt!NCryptOpenKey` at `0x1800180dc`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001804c`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001804c`

## string_xrefs

- `0x18001805f`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\tpmkeytranskey.cpp`
- `0x1800180a4`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\tpmkeytranskey.cpp`
- `0x1800180ed`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\tpmkeytranskey.cpp`
- `0x180018124`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\tpmkeytranskey.cpp`

## pseudocode

```c
__int64 __fastcall TpmKeyTransKey::CreateNewKey(
        TpmKeyTransKey *this,
        struct _SECURITY_DESCRIPTOR *a2,
        int a3,
        unsigned __int16 **a4)
{
  _DWORD *v8; // r9
  int PregenKey; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  NCRYPT_HANDLE *v12; // rbx
  const WCHAR *v13; // rax
  SECURITY_STATUS v14; // eax
  SECURITY_STATUS v15; // edi
  SECURITY_STATUS v16; // eax
  NCRYPT_HANDLE v17; // rcx
  struct _SECURITY_DESCRIPTOR *v18; // r8
  int v19; // eax
  unsigned __int16 *v20; // rax
  DWORD dwFlags; // [rsp+20h] [rbp-49h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-49h]
  LPCWSTR pszKeyName; // [rsp+30h] [rbp-39h] BYREF
  TpmKeyTransKey *v25; // [rsp+38h] [rbp-31h] BYREF
  __int16 v26; // [rsp+40h] [rbp-29h]
  int *v27; // [rsp+48h] [rbp-21h] BYREF
  __int16 v28; // [rsp+50h] [rbp-19h]
  int v29; // [rsp+58h] [rbp-11h] BYREF
  char v30; // [rsp+5Ch] [rbp-Dh]
  _BYTE v31[16]; // [rsp+60h] [rbp-9h] BYREF
  _DWORD v32[4]; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v29 = 0;
  v30 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v29);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    if ( v30 && (v32[0] || v32[1] || v32[2] || v32[3]) )
      v8 = v32;
    else
      v8 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180037000,
      byte_18002EC4D,
      v31,
      v8);
  }
  v27 = &v29;
  v28 = 256;
  pszKeyName = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszKeyName,
    0);
  PregenKey = NgcGetPregenKey(0, a3, 0, &pszKeyName);
  v10 = PregenKey;
  if ( PregenKey < 0 )
  {
    v11 = 56;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\tpmkeytranskey.cpp",
      (const char *)(unsigned int)PregenKey,
      dwFlags);
    goto LABEL_25;
  }
  v12 = (NCRYPT_HANDLE *)((char *)this + 16);
  if ( *((_QWORD *)this + 2)
    || (v13 = (const WCHAR *)(*(__int64 (__fastcall **)(TpmKeyTransKey *))(*(_QWORD *)this + 8LL))(this),
        v14 = NCryptOpenStorageProvider((NCRYPT_PROV_HANDLE *)this + 2, v13, 0),
        v15 = v14,
        v14 >= 0) )
  {
    v16 = NCryptSetProperty(*v12, L"PCP_SESSIONID", (PBYTE)&pbInput, 0x10u, 0);
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\tpmkeytranskey.cpp",
        (const char *)(unsigned int)v16,
        dwFlagsa);
    v17 = *((_QWORD *)this + 1);
    if ( v17 )
      NCryptFreeObject(v17);
    PregenKey = NCryptOpenKey(*v12, (NCRYPT_KEY_HANDLE *)this + 1, pszKeyName, 0, 0x10000000u);
    v10 = PregenKey;
    if ( PregenKey < 0 )
    {
      v11 = 83;
      goto LABEL_21;
    }
    v25 = this;
    v26 = 256;
    v19 = NgcUtils::SetNCryptSecurityDescriptor(*((_QWORD *)this + 1), a2, v18);
    v10 = v19;
    if ( v19 >= 0 )
    {
      HIBYTE(v26) = 0;
      v20 = (unsigned __int16 *)pszKeyName;
      pszKeyName = 0;
      *a4 = v20;
      wil::details::ScopeExitFnGuard__lambda_0bac2ce823ad4db9ffe1585967a02367___::operator()(&v25);
      v10 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\tpmkeytranskey.cpp",
        (const char *)(unsigned int)v19,
        dwFlags);
      wil::details::ScopeExitFnGuard__lambda_0bac2ce823ad4db9ffe1585967a02367___::operator()(&v25);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\tpmkeytranskey.cpp",
      (const char *)(unsigned int)v14,
      dwFlags);
    v10 = v15;
  }
LABEL_25:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszKeyName);
  wil::details::ScopeExitFnGuard__lambda_2a086c7cf88b665cca229335fa30f51d___::operator()(&v27);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v29);
  return v10;
}

```

## disassembly

```asm
0x180017f60  push    rbp
0x180017f62  push    rbx
0x180017f63  push    rsi
0x180017f64  push    rdi
0x180017f65  push    r12
0x180017f67  push    r14
0x180017f69  push    r15
0x180017f6b  lea     rbp, [rsp-27h]
0x180017f70  sub     rsp, 90h
0x180017f77  mov     rax, cs:__security_cookie
0x180017f7e  xor     rax, rsp
0x180017f81  mov     [rbp+57h+var_40], rax
0x180017f85  mov     r14, r9
0x180017f88  mov     ebx, r8d
0x180017f8b  mov     r15, rdx
0x180017f8e  mov     rsi, rcx
0x180017f91  xor     r12d, r12d
0x180017f94  mov     [rbp+57h+var_68], r12d
0x180017f98  mov     [rbp+57h+var_64], r12b
0x180017f9c  lea     rcx, [rbp+57h+var_68]
0x180017fa0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180017fa5  mov     eax, cs:dword_180037000
0x180017fab  cmp     eax, 5
0x180017fae  jbe     short loc_180017FEE
0x180017fb0  cmp     [rbp+57h+var_64], r12b
0x180017fb4  jz      short loc_180017FD4
0x180017fb6  cmp     [rbp+57h+var_50], r12d
0x180017fba  jnz     short loc_180017FCE
0x180017fbc  cmp     [rbp+57h+var_4C], r12d
0x180017fc0  jnz     short loc_180017FCE
0x180017fc2  cmp     [rbp+57h+var_48], r12d
0x180017fc6  jnz     short loc_180017FCE
0x180017fc8  cmp     [rbp+57h+var_44], r12d
0x180017fcc  jz      short loc_180017FD4
0x180017fce  lea     r9, [rbp+57h+var_50]
0x180017fd2  jmp     short loc_180017FD7
0x180017fd4  mov     r9, r12
0x180017fd7  lea     r8, [rbp+57h+var_60]
0x180017fdb  lea     rdx, byte_18002EC4D
0x180017fe2  lea     rcx, dword_180037000
0x180017fe9  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180017fee  lea     rax, [rbp+57h+var_68]
0x180017ff2  mov     [rbp+57h+var_78], rax
0x180017ff6  mov     [rbp+57h+var_70], 100h
0x180017ffc  mov     [rbp+57h+pszKeyName], r12
0x180018000  xor     edx, edx
0x180018002  lea     rcx, [rbp+57h+pszKeyName]
0x180018006  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001800b  lea     r9, [rbp+57h+pszKeyName]
0x18001800f  xor     r8d, r8d
0x180018012  mov     edx, ebx
0x180018014  xor     ecx, ecx
0x180018016  call    NgcGetPregenKey
0x18001801b  mov     ebx, eax
0x18001801d  test    eax, eax
0x18001801f  jns     short loc_18001802B
0x180018021  mov     edx, 38h ; '8'
0x180018026  jmp     loc_1800180ED
0x18001802b  lea     rbx, [rsi+10h]
0x18001802f  cmp     [rbx], r12
0x180018032  jnz     short loc_180018077
0x180018034  mov     rax, [rsi]
0x180018037  mov     rcx, rsi
0x18001803a  mov     rax, [rax+8]
0x18001803e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018043  mov     rdx, rax; pszProviderName
0x180018046  xor     r8d, r8d; dwFlags
0x180018049  mov     rcx, rbx; phProvider
0x18001804c  call    cs:__imp_NCryptOpenStorageProvider
0x180018052  mov     edi, eax
0x180018054  test    eax, eax
0x180018056  jns     short loc_180018077
0x180018058  mov     rcx, [rbp+5Fh]; this
0x18001805c  mov     r9d, eax; char *
0x18001805f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180018066  mov     edx, 3Fh ; '?'; void *
0x18001806b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018070  mov     ebx, edi
0x180018072  jmp     loc_18001815B
0x180018077  mov     [rsp+0C0h+dwFlags], r12d; int
0x18001807c  mov     r9d, 10h; cbInput
0x180018082  lea     r8, pbInput; pbInput
0x180018089  lea     rdx, aPcpSessionid; "PCP_SESSIONID"
0x180018090  mov     rcx, [rbx]; hObject
0x180018093  call    cs:__imp_NCryptSetProperty
0x180018099  mov     rcx, [rbp+5Fh]; this
0x18001809d  test    eax, eax
0x18001809f  jns     short loc_1800180B5
0x1800180a1  mov     r9d, eax; char *
0x1800180a4  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800180ab  mov     edx, 47h ; 'G'; void *
0x1800180b0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800180b5  lea     rdi, [rsi+8]
0x1800180b9  mov     rcx, [rdi]; hObject
0x1800180bc  test    rcx, rcx
0x1800180bf  jz      short loc_1800180C7
0x1800180c1  call    cs:__imp_NCryptFreeObject
0x1800180c7  mov     [rsp+0C0h+dwFlags], 10000000h; int
0x1800180cf  xor     r9d, r9d; dwLegacyKeySpec
0x1800180d2  mov     r8, [rbp+57h+pszKeyName]; pszKeyName
0x1800180d6  mov     rdx, rdi; phKey
0x1800180d9  mov     rcx, [rbx]; hProvider
0x1800180dc  call    cs:__imp_NCryptOpenKey
0x1800180e2  mov     ebx, eax
0x1800180e4  test    eax, eax
0x1800180e6  jns     short loc_180018102
0x1800180e8  mov     edx, 53h ; 'S'; void *
0x1800180ed  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800180f4  mov     r9d, eax; char *
0x1800180f7  mov     rcx, [rbp+5Fh]; this
0x1800180fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018100  jmp     short loc_18001815B
0x180018102  mov     [rbp+57h+var_88], rsi
0x180018106  mov     [rbp+57h+var_80], 100h
0x18001810c  mov     rdx, r15; AbsoluteSD
0x18001810f  mov     rcx, [rdi]; hObject
0x180018112  call    ?SetNCryptSecurityDescriptor@NgcUtils@@YAJ_KPEAU_SECURITY_DESCRIPTOR@@@Z; NgcUtils::SetNCryptSecurityDescriptor(unsigned __int64,_SECURITY_DESCRIPTOR *)
0x180018117  mov     ebx, eax
0x180018119  test    eax, eax
0x18001811b  jns     short loc_180018140
0x18001811d  mov     rcx, [rbp+5Fh]; this
0x180018121  mov     r9d, eax; char *
0x180018124  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001812b  mov     edx, 61h ; 'a'; void *
0x180018130  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018135  lea     rcx, [rbp+57h+var_88]
0x180018139  call    wil__details__ScopeExitFnGuard__lambda_0bac2ce823ad4db9ffe1585967a02367_____operator__
0x18001813e  jmp     short loc_18001815B
0x180018140  mov     byte ptr [rbp+57h+var_80+1], r12b
0x180018144  mov     rax, [rbp+57h+pszKeyName]
0x180018148  mov     [rbp+57h+pszKeyName], r12
0x18001814c  mov     [r14], rax
0x18001814f  lea     rcx, [rbp+57h+var_88]
0x180018153  call    wil__details__ScopeExitFnGuard__lambda_0bac2ce823ad4db9ffe1585967a02367_____operator__
0x180018158  mov     ebx, r12d
0x18001815b  lea     rcx, [rbp+57h+pszKeyName]
0x18001815f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180018164  nop
0x180018165  lea     rcx, [rbp+57h+var_78]
0x180018169  call    wil__details__ScopeExitFnGuard__lambda_2a086c7cf88b665cca229335fa30f51d_____operator__
0x18001816e  nop
0x18001816f  lea     rcx, [rbp+57h+var_68]
0x180018173  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180018178  mov     eax, ebx
0x18001817a  mov     rcx, [rbp+57h+var_40]
0x18001817e  xor     rcx, rsp; StackCookie
0x180018181  call    __security_check_cookie
0x180018186  add     rsp, 90h
0x18001818d  pop     r15
0x18001818f  pop     r14
0x180018191  pop     r12
0x180018193  pop     rdi
0x180018194  pop     rsi
0x180018195  pop     rbx
0x180018196  pop     rbp
0x180018197  retn
```
