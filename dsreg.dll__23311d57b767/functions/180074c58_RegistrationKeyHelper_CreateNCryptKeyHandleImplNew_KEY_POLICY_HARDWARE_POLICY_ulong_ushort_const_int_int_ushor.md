# RegistrationKeyHelper::CreateNCryptKeyHandleImplNew(_KEY_POLICY,_HARDWARE_POLICY,ulong,ushort const *,int,int,ushort const *,ushort const *,unsigned __int64 *,ushort * *,int *)

- ea: `0x180074c58`
- end: `0x1800750b9`
- name: `?CreateNCryptKeyHandleImplNew@RegistrationKeyHelper@@CAJW4_KEY_POLICY@@W4_HARDWARE_POLICY@@KPEBGHH22PEA_KPEAPEAGPEAH@Z`
- size: `1121`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800747bc`

## callees

- `0x1800012a4`
- `0x180001e6c`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x18000ddf0`
- `0x180012948`
- `0x18001b560`
- `0x1800204f0`
- `0x1800307c4`
- `0x180043ef8`
- `0x180044300`
- `0x180051604`
- `0x180055174`
- `0x180055194`
- `0x180074c58`
- `0x1800750c0`
- `0x180076ad8`
- `0x180076bd8`
- `0x1800b8c44`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180074ef8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180074ef8`
- `ncrypt!NCryptDeleteKey` at `0x180075075`
- `ncrypt!NCryptDeleteKey` at `0x180075075`
- `ncrypt!NCryptFreeObject` at `0x180074de0`
- `ncrypt!NCryptFreeObject` at `0x180075051`
- `ncrypt!NCryptFreeObject` at `0x180074de0`
- `ncrypt!NCryptFreeObject` at `0x180075051`

## string_xrefs

- `0x180074fcd`: `CopyStringW`
- `0x18007501c`: `StringCompare`
- `0x180074cdd`: `RegistrationKeyHelper::CreateNCryptKeyHandleImplNew`
- `0x180074d1b`: `RegistrationKeyHelper::CreateNCryptKeyHandleImplNew`
- `0x180074d7e`: `RegistrationKeyHelper::CreateNCryptKeyHandleImplNew`
- `0x180074dae`: `RegistrationKeyHelper::CreateNCryptKeyHandleImplNew`
- `0x180074e2b`: `%s: NCryptOpenStorageProvider('%s') failed with 0x%08x`
- `0x180075038`: `%s: New key could not be created successfully. Number of providers tried: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistrationKeyHelper::CreateNCryptKeyHandleImplNew(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        unsigned __int16 *a4,
        int a5,
        int a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int64 *a9,
        unsigned __int16 **a10,
        int *a11)
{
  int NewKey; // ebx
  const unsigned __int16 *v14; // rdx
  unsigned int TpmVersion; // eax
  int AadKeyStorageProviders; // eax
  int v17; // r13d
  signed int v18; // r15d
  const unsigned __int16 *v19; // r15
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r9
  unsigned __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // r9
  const wchar_t *v26; // r8
  int v27; // eax
  int v29[2]; // [rsp+20h] [rbp-A9h]
  unsigned int v30; // [rsp+40h] [rbp-89h] BYREF
  int v31; // [rsp+44h] [rbp-85h]
  NCRYPT_HANDLE hObject; // [rsp+48h] [rbp-81h] BYREF
  __int64 v33; // [rsp+50h] [rbp-79h] BYREF
  unsigned __int16 *v34; // [rsp+58h] [rbp-71h]
  unsigned __int16 *v35; // [rsp+60h] [rbp-69h]
  unsigned __int16 *v36; // [rsp+68h] [rbp-61h]
  const unsigned __int16 *v37; // [rsp+70h] [rbp-59h] BYREF
  __int64 v38; // [rsp+78h] [rbp-51h] BYREF
  int v39; // [rsp+80h] [rbp-49h] BYREF
  char v40; // [rsp+84h] [rbp-45h]
  _BYTE v41[16]; // [rsp+88h] [rbp-41h] BYREF
  GUID ActivityId; // [rsp+98h] [rbp-31h] BYREF
  unsigned __int16 *Source[2]; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-11h]

  v36 = a4;
  v35 = a7;
  v34 = a8;
  hObject = 0;
  *(_OWORD *)Source = 0;
  v44 = 0;
  v30 = 3;
  if ( !a10 )
  {
    NewKey = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationKeyHelper::CreateNCryptKeyHandleImplNew",
      L"providerName");
    v14 = L"providerName";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationKeyHelper::CreateNCryptKeyHandleImplNew", v14);
    goto LABEL_41;
  }
  *a10 = 0;
  if ( !a9 )
  {
    NewKey = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationKeyHelper::CreateNCryptKeyHandleImplNew",
      L"keyHandle");
    v14 = L"keyHandle";
    goto LABEL_3;
  }
  *a9 = 0;
  if ( a11 )
    *a11 = 0;
  TpmVersion = RegistrationKeyHelper::GetTpmVersion();
  AadKeyStorageProviders = GetAadKeyStorageProviders(a1, a2, TpmVersion, 0, Source, &v30);
  NewKey = AadKeyStorageProviders;
  if ( AadKeyStorageProviders < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationKeyHelper::CreateNCryptKeyHandleImplNew",
      L"GetAadKeyStorageProviders",
      (unsigned int)AadKeyStorageProviders);
    goto LABEL_41;
  }
  v31 = 0;
  v29[0] = a2;
  v17 = v30;
  Logger::TraceInformation(
    L"%s: %d KSPs to try based on key policy %lu and hardware policy %lu",
    L"RegistrationKeyHelper::CreateNCryptKeyHandleImplNew",
    v30,
    a1,
    *(_QWORD *)v29);
  v18 = 0;
  v30 = 0;
  if ( v17 > 0 )
  {
    while ( 1 )
    {
      if ( hObject )
      {
        NCryptFreeObject(hObject);
        hObject = 0;
      }
      v19 = Source[v18];
      Logger::TraceInformation(
        L"%s: Trying provider '%s'.",
        L"RegistrationKeyHelper::CreateNCryptKeyHandleImplNew",
        v19);
      v20 = RegistrationKeyHelper::OpenNCryptStorageProvider(v19, &hObject, 1);
      NewKey = v20;
      if ( v20 >= 0 )
      {
        ++v31;
        v39 = 0;
        v40 = 0;
        _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v39);
        if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
        {
          v33 = 0x1000000;
          if ( v40 )
            _tlgGuidIsZero(&ActivityId);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
            (__int64)&dword_18013D150,
            (__int64)byte_18012A291);
        }
        NewKey = RegistrationKeyHelper::CreateNewKey(hObject, v21, v36, a5, a6, v35, v34, a9);
        if ( v40 )
          EventActivityIdControl(4u, &ActivityId);
        v39 = 2;
        if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
        {
          v37 = v19;
          LODWORD(v33) = NewKey;
          v38 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            (__int64)&dword_18013D150,
            (__int64)byte_18012A491,
            (__int64)v41,
            v22,
            (__int64)&v38,
            (__int64)&v33,
            &v37);
        }
        if ( NewKey >= 0 )
        {
          v23 = -1;
          do
            ++v23;
          while ( v19[v23] );
          v24 = CopyStringW(v19, v23, a10);
          NewKey = v24;
          if ( v24 < 0 )
          {
            v25 = (unsigned int)v24;
            v26 = L"CopyStringW";
LABEL_33:
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"RegistrationKeyHelper::CreateNCryptKeyHandleImplNew",
              v26,
              v25);
            _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v39);
            break;
          }
          if ( a11 )
          {
            if ( v31 > 1 )
            {
              v27 = StringCompare(v19, L"Microsoft Software Key Storage Provider", 0x30001u, a11);
              NewKey = v27;
              if ( v27 < 0 )
              {
                v25 = (unsigned int)v27;
                v26 = L"StringCompare";
                goto LABEL_33;
              }
            }
          }
          _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v39);
LABEL_39:
          if ( NewKey < 0 )
            Logger::TraceError(
              L"%s: New key could not be created successfully. Number of providers tried: %d",
              L"RegistrationKeyHelper::CreateNCryptKeyHandleImplNew",
              (unsigned int)v17);
          break;
        }
        Logger::TraceWarning(
          (wchar_t *)L"%s: Key creation using provider '%s' failed with error 0x%08X",
          L"RegistrationKeyHelper::CreateNCryptKeyHandleImplNew",
          v19,
          (unsigned int)NewKey);
        _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v39);
      }
      else
      {
        Logger::TraceWarning(
          (wchar_t *)L"%s: NCryptOpenStorageProvider('%s') failed with 0x%08x",
          L"RegistrationKeyHelper::CreateNCryptKeyHandleImplNew",
          v19,
          (unsigned int)v20);
      }
      v18 = v30 + 1;
      v30 = v18;
      if ( v18 >= v17 )
        goto LABEL_39;
    }
  }
LABEL_41:
  if ( hObject )
    NCryptFreeObject(hObject);
  if ( NewKey < 0 )
  {
    if ( a10 )
    {
      operator delete(*a10);
      *a10 = 0;
    }
    if ( a9 )
    {
      NCryptDeleteKey(*a9, 0);
      *a9 = 0;
    }
  }
  Logger::TraceVerbose(
    (wchar_t *)L"%s - hr: 0x%08x",
    L"RegistrationKeyHelper::CreateNCryptKeyHandleImplNew",
    (unsigned int)NewKey);
  return (unsigned int)NewKey;
}

```

## disassembly

```asm
0x180074c58  mov     [rsp-8+arg_10], rbx
0x180074c5d  push    rbp
0x180074c5e  push    rsi
0x180074c5f  push    rdi
0x180074c60  push    r12
0x180074c62  push    r13
0x180074c64  push    r14
0x180074c66  push    r15
0x180074c68  lea     rbp, [rsp-7]
0x180074c6d  sub     rsp, 0D0h
0x180074c74  mov     rax, cs:__security_cookie
0x180074c7b  xor     rax, rsp
0x180074c7e  mov     [rbp+37h+var_40], rax
0x180074c82  mov     [rbp+37h+var_98], r9
0x180074c86  mov     r15d, edx
0x180074c89  mov     edi, ecx
0x180074c8b  mov     rax, [rbp+37h+arg_30]
0x180074c8f  mov     [rbp+37h+var_A0], rax
0x180074c93  mov     rax, [rbp+37h+arg_38]
0x180074c97  mov     [rbp+37h+var_A8], rax
0x180074c9b  mov     rsi, [rbp+37h+arg_40]
0x180074ca2  mov     r14, [rbp+37h+arg_48]
0x180074ca9  mov     r12, [rbp+37h+arg_50]
0x180074cb0  xor     r13d, r13d
0x180074cb3  mov     [rsp+100h+hObject], r13
0x180074cb8  xorps   xmm0, xmm0
0x180074cbb  movdqu  xmmword ptr [rbp+37h+Source], xmm0
0x180074cc0  mov     [rbp+37h+var_48], r13
0x180074cc4  mov     [rsp+100h+var_C0], 3
0x180074ccc  test    r14, r14
0x180074ccf  jnz     short loc_180074D07
0x180074cd1  mov     ebx, 80070057h
0x180074cd6  lea     r8, aProvidername; "providerName"
0x180074cdd  lea     rdi, aRegistrationke_7; "RegistrationKeyHelper::CreateNCryptKeyH"...
0x180074ce4  mov     rdx, rdi
0x180074ce7  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180074cee  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180074cf3  lea     rdx, aProvidername; "providerName"
0x180074cfa  mov     rcx, rdi; unsigned __int16 *
0x180074cfd  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180074d02  jmp     loc_180075047
0x180074d07  mov     [r14], r13
0x180074d0a  test    rsi, rsi
0x180074d0d  jnz     short loc_180074D3A
0x180074d0f  mov     ebx, 80070057h
0x180074d14  lea     r8, aKeyhandle; "keyHandle"
0x180074d1b  lea     rdi, aRegistrationke_7; "RegistrationKeyHelper::CreateNCryptKeyH"...
0x180074d22  mov     rdx, rdi
0x180074d25  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180074d2c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180074d31  lea     rdx, aKeyhandle; "keyHandle"
0x180074d38  jmp     short loc_180074CFA
0x180074d3a  mov     [rsi], r13
0x180074d3d  test    r12, r12
0x180074d40  jz      short loc_180074D46
0x180074d42  mov     [r12], r13d
0x180074d46  call    ?GetTpmVersion@RegistrationKeyHelper@@SAIXZ; RegistrationKeyHelper::GetTpmVersion(void)
0x180074d4b  mov     r8d, eax
0x180074d4e  lea     rax, [rsp+100h+var_C0]
0x180074d53  mov     [rsp+100h+var_D8], rax
0x180074d58  lea     rax, [rbp+37h+Source]
0x180074d5c  mov     qword ptr [rsp+100h+var_E0], rax
0x180074d61  xor     r9d, r9d
0x180074d64  mov     edx, r15d
0x180074d67  mov     ecx, edi
0x180074d69  call    ?GetAadKeyStorageProviders@@YAJW4_KEY_POLICY@@W4_HARDWARE_POLICY@@IHQEAPEBGAEAH@Z; GetAadKeyStorageProviders(_KEY_POLICY,_HARDWARE_POLICY,uint,int,ushort const * * const,int &)
0x180074d6e  mov     ebx, eax
0x180074d70  test    eax, eax
0x180074d72  jns     short loc_180074D99
0x180074d74  mov     r9d, eax
0x180074d77  lea     r8, aGetaadkeystora; "GetAadKeyStorageProviders"
0x180074d7e  lea     rdi, aRegistrationke_7; "RegistrationKeyHelper::CreateNCryptKeyH"...
0x180074d85  mov     rdx, rdi
0x180074d88  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180074d8f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180074d94  jmp     loc_180075047
0x180074d99  mov     [rsp+100h+var_BC], r13d
0x180074d9e  mov     [rsp+100h+var_E0], r15d
0x180074da3  mov     r9d, edi
0x180074da6  mov     r13d, [rsp+100h+var_C0]
0x180074dab  mov     r8d, r13d
0x180074dae  lea     rdi, aRegistrationke_7; "RegistrationKeyHelper::CreateNCryptKeyH"...
0x180074db5  mov     rdx, rdi
0x180074db8  lea     rcx, aSDKspsToTryBas; "%s: %d KSPs to try based on key policy "...
0x180074dbf  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180074dc4  xor     eax, eax
0x180074dc6  mov     r15d, eax
0x180074dc9  mov     [rsp+100h+var_C0], eax
0x180074dcd  test    r13d, r13d
0x180074dd0  jle     loc_180075044
0x180074dd6  mov     rcx, [rsp+100h+hObject]; hObject
0x180074ddb  test    rcx, rcx
0x180074dde  jz      short loc_180074DEF
0x180074de0  call    cs:__imp_NCryptFreeObject
0x180074de6  mov     [rsp+100h+hObject], 0
0x180074def  movsxd  rax, r15d
0x180074df2  mov     r15, [rbp+rax*8+37h+Source]
0x180074df7  mov     r8, r15
0x180074dfa  mov     rdx, rdi
0x180074dfd  lea     rcx, aSTryingProvide; "%s: Trying provider '%s'."
0x180074e04  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180074e09  mov     r8d, 1; int
0x180074e0f  lea     rdx, [rsp+100h+hObject]; phProvider
0x180074e14  mov     rcx, r15; unsigned __int16 *
0x180074e17  call    ?OpenNCryptStorageProvider@RegistrationKeyHelper@@SAJPEBGPEA_KH@Z; RegistrationKeyHelper::OpenNCryptStorageProvider(ushort const *,unsigned __int64 *,int)
0x180074e1c  mov     ebx, eax
0x180074e1e  test    eax, eax
0x180074e20  jns     short loc_180074E3C
0x180074e22  mov     r9d, eax
0x180074e25  mov     r8, r15
0x180074e28  mov     rdx, rdi
0x180074e2b  lea     rcx, aSNcryptopensto; "%s: NCryptOpenStorageProvider('%s') fai"...
0x180074e32  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180074e37  jmp     loc_180074F90
0x180074e3c  inc     [rsp+100h+var_BC]
0x180074e40  xor     ebx, ebx
0x180074e42  mov     [rbp+37h+var_80], ebx
0x180074e45  mov     [rbp+37h+var_7C], bl
0x180074e48  lea     rcx, [rbp+37h+var_80]
0x180074e4c  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x180074e51  mov     eax, cs:dword_18013D150
0x180074e57  cmp     eax, 5
0x180074e5a  jbe     short loc_180074EB7
0x180074e5c  mov     rdx, 400000000000h
0x180074e66  lea     rcx, dword_18013D150
0x180074e6d  call    _tlgKeywordOn
0x180074e72  test    al, al
0x180074e74  jz      short loc_180074EB7
0x180074e76  mov     [rbp+37h+var_B0], 1000000h
0x180074e7e  cmp     [rbp+37h+var_7C], bl
0x180074e81  jz      short loc_180074E94
0x180074e83  lea     rcx, [rbp+37h+ActivityId]; struct _GUID *
0x180074e87  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180074e8c  test    al, al
0x180074e8e  lea     r9, [rbp+37h+ActivityId]
0x180074e92  jz      short loc_180074E97
0x180074e94  mov     r9, rbx
0x180074e97  lea     rax, [rbp+37h+var_B0]
0x180074e9b  mov     qword ptr [rsp+100h+var_E0], rax
0x180074ea0  lea     r8, [rbp+37h+var_78]
0x180074ea4  lea     rdx, byte_18012A291
0x180074eab  lea     rcx, dword_18013D150
0x180074eb2  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180074eb7  mov     [rsp+100h+var_C8], rsi; unsigned __int64 *
0x180074ebc  mov     rax, [rbp+37h+var_A8]
0x180074ec0  mov     [rsp+100h+var_D0], rax; unsigned __int16 *
0x180074ec5  mov     rax, [rbp+37h+var_A0]
0x180074ec9  mov     [rsp+100h+var_D8], rax; unsigned __int16 *
0x180074ece  mov     eax, [rbp+37h+arg_28]
0x180074ed1  mov     [rsp+100h+var_E0], eax; int
0x180074ed5  mov     r9d, [rbp+37h+arg_20]; int
0x180074ed9  mov     r8, [rbp+37h+var_98]; unsigned __int16 *
0x180074edd  mov     rcx, [rsp+100h+hObject]; unsigned __int64
0x180074ee2  call    ?CreateNewKey@RegistrationKeyHelper@@CAJ_KKPEBGHH11PEA_K@Z; RegistrationKeyHelper::CreateNewKey(unsigned __int64,ulong,ushort const *,int,int,ushort const *,ushort const *,unsigned __int64 *)
0x180074ee7  mov     ebx, eax
0x180074ee9  cmp     [rbp+37h+var_7C], 0
0x180074eed  jz      short loc_180074EFE
0x180074eef  lea     rdx, [rbp+37h+ActivityId]; ActivityId
0x180074ef3  mov     ecx, 4; ControlCode
0x180074ef8  call    cs:__imp_EventActivityIdControl
0x180074efe  mov     [rbp+37h+var_80], 2
0x180074f05  mov     eax, cs:dword_18013D150
0x180074f0b  cmp     eax, 5
0x180074f0e  jbe     short loc_180074F6B
0x180074f10  mov     rdx, 400000000000h
0x180074f1a  lea     rcx, dword_18013D150
0x180074f21  call    _tlgKeywordOn
0x180074f26  test    al, al
0x180074f28  jz      short loc_180074F6B
0x180074f2a  mov     [rbp+37h+var_90], r15
0x180074f2e  mov     dword ptr [rbp+37h+var_B0], ebx
0x180074f31  mov     [rbp+37h+var_88], 1000000h
0x180074f39  lea     rax, [rbp+37h+var_90]
0x180074f3d  mov     [rsp+100h+var_D0], rax
0x180074f42  lea     rax, [rbp+37h+var_B0]
0x180074f46  mov     [rsp+100h+var_D8], rax
0x180074f4b  lea     rax, [rbp+37h+var_88]
0x180074f4f  mov     qword ptr [rsp+100h+var_E0], rax
0x180074f54  lea     r8, [rbp+37h+var_78]
0x180074f58  lea     rdx, byte_18012A491
0x180074f5f  lea     rcx, dword_18013D150
0x180074f66  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180074f6b  xor     eax, eax
0x180074f6d  test    ebx, ebx
0x180074f6f  jns     short loc_180074FAB
0x180074f71  mov     r9d, ebx
0x180074f74  mov     r8, r15
0x180074f77  mov     rdx, rdi
0x180074f7a  lea     rcx, aSKeyCreationUs; "%s: Key creation using provider '%s' fa"...
0x180074f81  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180074f86  nop
0x180074f87  lea     rcx, [rbp+37h+var_80]
0x180074f8b  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x180074f90  mov     r15d, [rsp+100h+var_C0]
0x180074f95  inc     r15d
0x180074f98  mov     [rsp+100h+var_C0], r15d
0x180074f9d  cmp     r15d, r13d
0x180074fa0  jl      loc_180074DD6
0x180074fa6  jmp     loc_18007502E
0x180074fab  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180074faf  inc     rdx; unsigned __int64
0x180074fb2  cmp     [r15+rdx*2], ax
0x180074fb7  jnz     short loc_180074FAF
0x180074fb9  mov     r8, r14; unsigned __int16 **
0x180074fbc  mov     rcx, r15; Source
0x180074fbf  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x180074fc4  mov     ebx, eax
0x180074fc6  test    eax, eax
0x180074fc8  jns     short loc_180074FEF
0x180074fca  mov     r9d, eax
0x180074fcd  lea     r8, aCopystringw; "CopyStringW"
0x180074fd4  mov     rdx, rdi
0x180074fd7  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180074fde  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180074fe3  nop
0x180074fe4  lea     rcx, [rbp+37h+var_80]
0x180074fe8  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x180074fed  jmp     short loc_180075044
0x180074fef  test    r12, r12
0x180074ff2  jz      short loc_180075025
0x180074ff4  cmp     [rsp+100h+var_BC], 1
0x180074ff9  jle     short loc_180075025
0x180074ffb  mov     r9, r12; int *
0x180074ffe  mov     r8d, 30001h; unsigned int
0x180075004  lea     rdx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x18007500b  mov     rcx, r15; lpString1
0x18007500e  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x180075013  mov     ebx, eax
0x180075015  test    eax, eax
0x180075017  jns     short loc_180075025
0x180075019  mov     r9d, eax
0x18007501c  lea     r8, aStringcompare; "StringCompare"
0x180075023  jmp     short loc_180074FD4
0x180075025  lea     rcx, [rbp+37h+var_80]
0x180075029  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x18007502e  test    ebx, ebx
0x180075030  jns     short loc_180075044
0x180075032  mov     r8d, r13d
0x180075035  mov     rdx, rdi
0x180075038  lea     rcx, aSNewKeyCouldNo; "%s: New key could not be created succes"...
0x18007503f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180075044  xor     r13d, r13d
0x180075047  mov     rcx, [rsp+100h+hObject]; hObject
0x18007504c  test    rcx, rcx
0x18007504f  jz      short loc_180075057
0x180075051  call    cs:__imp_NCryptFreeObject
0x180075057  test    ebx, ebx
0x180075059  jns     short loc_18007507E
0x18007505b  test    r14, r14
0x18007505e  jz      short loc_18007506B
0x180075060  mov     rcx, [r14]; Block
0x180075063  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180075068  mov     [r14], r13
0x18007506b  test    rsi, rsi
0x18007506e  jz      short loc_18007507E
0x180075070  xor     edx, edx; dwFlags
0x180075072  mov     rcx, [rsi]; hKey
0x180075075  call    cs:__imp_NCryptDeleteKey
0x18007507b  mov     [rsi], r13
0x18007507e  mov     r8d, ebx
0x180075081  mov     rdx, rdi
0x180075084  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18007508b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180075090  mov     eax, ebx
0x180075092  mov     rcx, [rbp+37h+var_40]
0x180075096  xor     rcx, rsp; StackCookie
0x180075099  call    __security_check_cookie
0x18007509e  mov     rbx, [rsp+100h+arg_10]
0x1800750a6  add     rsp, 0D0h
0x1800750ad  pop     r15
0x1800750af  pop     r14
0x1800750b1  pop     r13
0x1800750b3  pop     r12
0x1800750b5  pop     rdi
0x1800750b6  pop     rsi
0x1800750b7  pop     rbp
0x1800750b8  retn
```
