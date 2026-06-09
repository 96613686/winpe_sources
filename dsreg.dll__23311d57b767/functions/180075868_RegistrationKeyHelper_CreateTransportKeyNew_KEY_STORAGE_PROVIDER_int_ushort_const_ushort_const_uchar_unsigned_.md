# RegistrationKeyHelper::CreateTransportKeyNew(_KEY_STORAGE_PROVIDER,int,ushort const *,ushort const *,uchar * *,unsigned __int64 *,uchar * *,unsigned __int64 *,uchar * *,unsigned __int64 *,ulong *)

- ea: `0x180075868`
- end: `0x180075dc5`
- name: `?CreateTransportKeyNew@RegistrationKeyHelper@@SAJW4_KEY_STORAGE_PROVIDER@@HPEBG1PEAPEAEPEA_K2323PEAK@Z`
- size: `1373`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation`

## callers

- `0x18005693c`

## callees

- `0x180001260`
- `0x180001e08`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180012948`
- `0x180012eb8`
- `0x1800204f0`
- `0x1800307c4`
- `0x180031f44`
- `0x1800334e0`
- `0x180034eb4`
- `0x180044300`
- `0x180055174`
- `0x18006d074`
- `0x180075868`
- `0x1800765b8`
- `0x180076a7c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180075d31`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180075d31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075c84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075c93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075c9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075ca7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075c84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075c93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075c9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075ca7`
- `popkeycli!NgcGetSymmetricPopKeyTransportKey` at `0x180075b01`
- `popkeycli!NgcGetSymmetricPopKeyTransportKey` at `0x180075b01`

## string_xrefs

- `0x18007598e`: `RegistrationKeyHelper::CreateTransportKeyNew`
- `0x1800759b9`: `RegistrationKeyHelper::CreateTransportKeyNew`
- `0x180075a5f`: `RegistrationKeyHelper::CreateTransportKeyNew`
- `0x180075b5e`: `RegistrationKeyHelper::CreateTransportKeyNew`
- `0x180075bb4`: `RegistrationKeyHelper::CreateTransportKeyNew`
- `0x180075c07`: `RegistrationKeyHelper::CreateTransportKeyNew`
- `0x180075d80`: `RegistrationKeyHelper::CreateTransportKeyNew`
- `0x180075b43`: `%s: Cannot create transport key. NgcGetSymmetricPopKeyTransportKey failed with error code 0x%08x. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Key type: %d (%s), Flags: %lu.`
- `0x180075ba8`: `%s: Transport key created. NgcGetSymmetricPopKeyTransportKey succeeded. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Key type: %d (%s), Flags: %lu, NGC key status: %d (%s).`

## pseudocode

```c
__int64 __fastcall RegistrationKeyHelper::CreateTransportKeyNew(
        unsigned int a1,
        int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        _QWORD *a5,
        _QWORD *a6,
        HLOCAL *a7,
        _QWORD *a8,
        HLOCAL *a9,
        _QWORD *a10,
        int *a11)
{
  unsigned int v14; // edi
  int CurrentUserSid; // ebx
  const unsigned __int16 *v16; // rdx
  int SymmetricPopKeyTransportKey; // eax
  __int64 v18; // rax
  int v19; // edx
  __int64 KeyStatusName; // rax
  __int64 NgcKeyType; // rax
  int v22; // r9d
  int v23; // r8d
  __int64 v24; // rdx
  int *v25; // rdi
  int v26; // eax
  int v27; // eax
  HLOCAL v28; // rax
  _QWORD *v29; // rcx
  __int64 v30; // rcx
  __int16 *v31; // rdx
  int v33[2]; // [rsp+30h] [rbp-D0h]
  __int64 v34; // [rsp+38h] [rbp-C8h]
  __int64 v35; // [rsp+40h] [rbp-C0h]
  __int64 v36; // [rsp+48h] [rbp-B8h]
  int v37; // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v39; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL v41; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL v42; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v43; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v44; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v45; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v46; // [rsp+A0h] [rbp-60h]
  _QWORD *v47; // [rsp+A8h] [rbp-58h]
  __int64 v48; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v49; // [rsp+B8h] [rbp-48h]
  __int64 v50; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v51; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD *v52; // [rsp+D0h] [rbp-30h]
  int *v53; // [rsp+D8h] [rbp-28h]
  int v54; // [rsp+E0h] [rbp-20h] BYREF
  char v55; // [rsp+E4h] [rbp-1Ch]
  GUID ActivityId; // [rsp+F8h] [rbp-8h] BYREF

  v47 = a5;
  v49 = a6;
  v52 = a10;
  v53 = a11;
  v39 = 0;
  hMem = 0;
  v41 = 0;
  v48 = 0;
  v14 = a2 != 0 ? 2 : 0;
  v42 = 0;
  v50 = 0;
  if ( a2 )
    a4 = 0;
  v43 = 0;
  v51 = 0;
  v38 = 0;
  v54 = 0;
  v55 = 0;
  v46 = a4;
  v37 = 1;
  v44 = L"login.windows.net";
  v45 = a3;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v54);
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
  {
    if ( v55 )
      _tlgGuidIsZero(&ActivityId);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18013D150,
      (__int64)&byte_18012A267);
  }
  if ( !a3 )
  {
    CurrentUserSid = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationKeyHelper::CreateTransportKeyNew", L"tenantId");
    v16 = L"tenantId";
LABEL_10:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationKeyHelper::CreateTransportKeyNew", v16);
    goto LABEL_40;
  }
  if ( !v47 )
  {
    CurrentUserSid = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationKeyHelper::CreateTransportKeyNew",
      L"transportKeyPub");
    v16 = L"transportKeyPub";
    goto LABEL_10;
  }
  if ( !v49 )
  {
    CurrentUserSid = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationKeyHelper::CreateTransportKeyNew",
      L"transportKeyPubSize");
    v16 = L"transportKeyPubSize";
    goto LABEL_10;
  }
  if ( a7 && !a8 || a9 && !v52 )
  {
    CurrentUserSid = -2147024809;
    Logger::TraceError(
      L"%s: attestationStatement/attestationStatementSize (or aikCertificate/aikCertificateSize) parameters should be non-NULL together.",
      L"RegistrationKeyHelper::CreateTransportKeyNew");
    goto LABEL_40;
  }
  if ( a2 || (CurrentUserSid = GetCurrentUserSid((LPWSTR *)&hMem), CurrentUserSid >= 0) )
  {
    switch ( a1 )
    {
      case 1u:
        v37 = 1;
        v14 |= 1u;
        break;
      case 2u:
        v37 = 2;
        break;
      case 4u:
        v37 = 5;
        break;
      default:
        CurrentUserSid = -2147024809;
        Logger::TraceError(
          L"%s: deviceKeyStorageProvider parameter has invalid value (%d).",
          L"RegistrationKeyHelper::CreateTransportKeyNew",
          a1);
        goto LABEL_40;
    }
    SymmetricPopKeyTransportKey = NgcGetSymmetricPopKeyTransportKey(
                                    &v44,
                                    hMem,
                                    &v37,
                                    v14,
                                    &v41,
                                    &v48,
                                    &v42,
                                    &v50,
                                    &v43,
                                    &v51,
                                    &v39);
    CurrentUserSid = SymmetricPopKeyTransportKey;
    if ( SymmetricPopKeyTransportKey >= 0 )
    {
      KeyStatusName = GetKeyStatusName(v39);
      NgcKeyType = GetNgcKeyType((unsigned int)v37, KeyStatusName);
      LODWORD(v36) = v22;
      LODWORD(v35) = v14;
      v33[0] = v23;
      Logger::TraceInformation(
        L"%s: Transport key created. NgcGetSymmetricPopKeyTransportKey succeeded. SID: %s, IDP domain: %s, Tenant domain: "
         "%s, User ID: %s, Key type: %d (%s), Flags: %lu, NGC key status: %d (%s).",
        L"RegistrationKeyHelper::CreateTransportKeyNew",
        hMem,
        v44,
        v45,
        v46,
        *(_QWORD *)v33,
        NgcKeyType,
        v35,
        v36,
        v24);
      v25 = v53;
      if ( v53 )
      {
        v26 = ConvertKeyStatusToDwordKeyType(v39, &v38);
        if ( v26 >= 0 )
        {
          v27 = v38;
        }
        else
        {
          Logger::TraceWarning(
            (wchar_t *)L"%s: ConvertKeyStatusToDwordKeyType failed with error code: 0x%08x.",
            L"RegistrationKeyHelper::CreateTransportKeyNew",
            (unsigned int)v26);
          v27 = 0;
        }
        *v25 = v27;
      }
      v28 = v41;
      v41 = 0;
      *v47 = v28;
      *v49 = v48;
      if ( a7 )
      {
        *a7 = v42;
        *a8 = v50;
        v42 = 0;
      }
      if ( a9 )
      {
        v29 = v52;
        *a9 = v43;
        v43 = 0;
        *v29 = v51;
      }
    }
    else
    {
      Logger::WriteNgcCreateTransportKeyFailureEvent(
        (const unsigned __int16 *)hMem,
        v44,
        v45,
        v46,
        v37,
        v14,
        SymmetricPopKeyTransportKey);
      v18 = GetNgcKeyType((unsigned int)v37, (unsigned int)v37);
      LODWORD(v36) = v14;
      LODWORD(v34) = v19;
      Logger::TraceError(
        L"%s: Cannot create transport key. NgcGetSymmetricPopKeyTransportKey failed with error code 0x%08x. SID: %s, IDP d"
         "omain: %s, Tenant domain: %s, User ID: %s, Key type: %d (%s), Flags: %lu.",
        L"RegistrationKeyHelper::CreateTransportKeyNew",
        (unsigned int)CurrentUserSid,
        hMem,
        v44,
        v45,
        v46,
        v34,
        v18,
        v36);
    }
  }
LABEL_40:
  LocalFree(hMem);
  if ( CurrentUserSid >= 0 )
  {
    if ( (unsigned int)dword_18013D150 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
    {
      v31 = &word_18012A136;
      v38 = v39;
      goto LABEL_47;
    }
  }
  else
  {
    LocalFree(v41);
    LocalFree(v42);
    LocalFree(v43);
    if ( (unsigned int)dword_18013D150 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
    {
      v38 = CurrentUserSid;
      v31 = (__int16 *)byte_18012A175;
LABEL_47:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v30,
        (__int64)v31);
    }
  }
  if ( v55 )
    EventActivityIdControl(4u, &ActivityId);
  v54 = 2;
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18013D150,
      (__int64)&dword_18012A30C);
  Logger::TraceVerbose(
    (wchar_t *)L"%s - hr: 0x%08x",
    L"RegistrationKeyHelper::CreateTransportKeyNew",
    (unsigned int)CurrentUserSid);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>((__int64)&v54);
  return (unsigned int)CurrentUserSid;
}

```

## disassembly

```asm
0x180075868  mov     [rsp-8+arg_8], rbx
0x18007586d  push    rbp
0x18007586e  push    rsi
0x18007586f  push    rdi
0x180075870  push    r12
0x180075872  push    r13
0x180075874  push    r14
0x180075876  push    r15
0x180075878  lea     rbp, [rsp-10h]
0x18007587d  sub     rsp, 110h
0x180075884  mov     rax, cs:__security_cookie
0x18007588b  xor     rax, rsp
0x18007588e  mov     [rbp+40h+var_38], rax
0x180075892  mov     rax, [rbp+40h+arg_20]
0x180075896  mov     esi, ecx
0x180075898  mov     r15, [rbp+40h+arg_30]
0x18007589f  xor     ecx, ecx
0x1800758a1  mov     r13, [rbp+40h+arg_38]
0x1800758a8  mov     rbx, r8
0x1800758ab  mov     r14, [rbp+40h+arg_40]
0x1800758b2  mov     r12d, edx
0x1800758b5  mov     [rbp+40h+var_98], rax
0x1800758b9  mov     rax, [rbp+40h+arg_28]
0x1800758bd  mov     [rbp+40h+var_88], rax
0x1800758c1  mov     rax, [rbp+40h+arg_48]
0x1800758c8  mov     [rbp+40h+var_70], rax
0x1800758cc  mov     rax, [rbp+40h+arg_50]
0x1800758d3  mov     [rbp+40h+var_68], rax
0x1800758d7  mov     eax, edx
0x1800758d9  neg     eax
0x1800758db  mov     [rsp+140h+var_D8], ecx
0x1800758df  mov     [rsp+140h+hMem], rcx
0x1800758e4  lea     rax, aLoginWindowsNe; "login.windows.net"
0x1800758eb  sbb     edi, edi
0x1800758ed  mov     [rsp+140h+var_C8], rcx
0x1800758f2  mov     [rbp+40h+var_90], rcx
0x1800758f6  and     edi, 2
0x1800758f9  test    edx, edx
0x1800758fb  mov     [rbp+40h+var_C0], rcx
0x1800758ff  mov     [rbp+40h+var_80], rcx
0x180075903  cmovnz  r9, rcx
0x180075907  mov     [rbp+40h+var_B8], rcx
0x18007590b  mov     [rbp+40h+var_78], rcx
0x18007590f  mov     [rsp+140h+var_DC], ecx
0x180075913  mov     [rbp+40h+var_60], ecx
0x180075916  mov     [rbp+40h+var_5C], cl
0x180075919  lea     rcx, [rbp+40h+var_60]
0x18007591d  mov     [rbp+40h+var_A0], r9
0x180075921  mov     [rsp+140h+var_E0], 1
0x180075929  mov     [rbp+40h+var_B0], rax
0x18007592d  mov     [rbp+40h+var_A8], rbx
0x180075931  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180075936  mov     eax, cs:dword_18013D150
0x18007593c  cmp     eax, 5
0x18007593f  jbe     short loc_18007598E
0x180075941  mov     rdx, 200000000000h
0x18007594b  lea     rcx, dword_18013D150
0x180075952  call    _tlgKeywordOn
0x180075957  test    al, al
0x180075959  jz      short loc_18007598E
0x18007595b  cmp     [rbp+40h+var_5C], 0
0x18007595f  jz      short loc_180075974
0x180075961  lea     rcx, [rbp+40h+ActivityId]; struct _GUID *
0x180075965  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18007596a  test    al, al
0x18007596c  jnz     short loc_180075974
0x18007596e  lea     r9, [rbp+40h+ActivityId]
0x180075972  jmp     short loc_180075977
0x180075974  xor     r9d, r9d
0x180075977  lea     r8, [rbp+40h+var_58]
0x18007597b  lea     rdx, byte_18012A267
0x180075982  lea     rcx, dword_18013D150
0x180075989  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007598e  lea     rdx, aRegistrationke_10; "RegistrationKeyHelper::CreateTransportK"...
0x180075995  test    rbx, rbx
0x180075998  jnz     short loc_1800759CA
0x18007599a  lea     r8, aTenantid_1; "tenantId"
0x1800759a1  mov     ebx, 80070057h
0x1800759a6  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800759ad  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800759b2  lea     rdx, aTenantid_1; "tenantId"
0x1800759b9  lea     rcx, aRegistrationke_10; "RegistrationKeyHelper::CreateTransportK"...
0x1800759c0  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800759c5  jmp     loc_180075C7F
0x1800759ca  cmp     [rbp+40h+var_98], 0
0x1800759cf  jnz     short loc_1800759F2
0x1800759d1  lea     r8, aTransportkeypu; "transportKeyPub"
0x1800759d8  mov     ebx, 80070057h
0x1800759dd  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800759e4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800759e9  lea     rdx, aTransportkeypu; "transportKeyPub"
0x1800759f0  jmp     short loc_1800759B9
0x1800759f2  cmp     [rbp+40h+var_88], 0
0x1800759f7  jnz     short loc_180075A1A
0x1800759f9  lea     r8, aTransportkeypu_0; "transportKeyPubSize"
0x180075a00  mov     ebx, 80070057h
0x180075a05  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180075a0c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180075a11  lea     rdx, aTransportkeypu_0; "transportKeyPubSize"
0x180075a18  jmp     short loc_1800759B9
0x180075a1a  test    r15, r15
0x180075a1d  jz      short loc_180075A24
0x180075a1f  test    r13, r13
0x180075a22  jz      short loc_180075A30
0x180075a24  test    r14, r14
0x180075a27  jz      short loc_180075A46
0x180075a29  cmp     [rbp+40h+var_70], 0
0x180075a2e  jnz     short loc_180075A46
0x180075a30  lea     rcx, aSAttestationst; "%s: attestationStatement/attestationSta"...
0x180075a37  mov     ebx, 80070057h
0x180075a3c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180075a41  jmp     loc_180075C7F
0x180075a46  test    r12d, r12d
0x180075a49  jnz     short loc_180075A66
0x180075a4b  lea     rcx, [rsp+140h+hMem]; StringSid
0x180075a50  call    ?GetCurrentUserSid@@YAJPEAPEAG@Z; GetCurrentUserSid(ushort * *)
0x180075a55  mov     ebx, eax
0x180075a57  test    eax, eax
0x180075a59  js      loc_180075C7F
0x180075a5f  lea     rdx, aRegistrationke_10; "RegistrationKeyHelper::CreateTransportK"...
0x180075a66  mov     ecx, esi
0x180075a68  sub     ecx, 1
0x180075a6b  jz      short loc_180075AA4
0x180075a6d  sub     ecx, 1
0x180075a70  jz      short loc_180075A9A
0x180075a72  cmp     ecx, 2
0x180075a75  jz      short loc_180075A90
0x180075a77  mov     r8d, esi
0x180075a7a  lea     rcx, aSDevicekeystor; "%s: deviceKeyStorageProvider parameter "...
0x180075a81  mov     ebx, 80070057h
0x180075a86  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180075a8b  jmp     loc_180075C7F
0x180075a90  mov     [rsp+140h+var_E0], 5
0x180075a98  jmp     short loc_180075AAF
0x180075a9a  mov     [rsp+140h+var_E0], 2
0x180075aa2  jmp     short loc_180075AAF
0x180075aa4  mov     [rsp+140h+var_E0], 1
0x180075aac  or      edi, 1
0x180075aaf  mov     rdx, [rsp+140h+hMem]
0x180075ab4  lea     rax, [rsp+140h+var_D8]
0x180075ab9  mov     [rsp+140h+var_F0], rax
0x180075abe  lea     r8, [rsp+140h+var_E0]
0x180075ac3  lea     rax, [rbp+40h+var_78]
0x180075ac7  mov     r9d, edi
0x180075aca  mov     [rsp+140h+var_F8], rax
0x180075acf  lea     rcx, [rbp+40h+var_B0]
0x180075ad3  lea     rax, [rbp+40h+var_B8]
0x180075ad7  mov     [rsp+140h+var_100], rax
0x180075adc  lea     rax, [rbp+40h+var_80]
0x180075ae0  mov     [rsp+140h+var_108], rax
0x180075ae5  lea     rax, [rbp+40h+var_C0]
0x180075ae9  mov     qword ptr [rsp+140h+var_110], rax
0x180075aee  lea     rax, [rbp+40h+var_90]
0x180075af2  mov     qword ptr [rsp+140h+var_118], rax
0x180075af7  lea     rax, [rsp+140h+var_C8]
0x180075afc  mov     qword ptr [rsp+140h+var_120], rax
0x180075b01  call    cs:__imp_NgcGetSymmetricPopKeyTransportKey
0x180075b07  mov     ebx, eax
0x180075b09  test    eax, eax
0x180075b0b  jns     short loc_180075B86
0x180075b0d  mov     r9, [rbp+40h+var_A0]; unsigned __int16 *
0x180075b11  mov     r8, [rbp+40h+var_A8]; unsigned __int16 *
0x180075b15  mov     rdx, [rbp+40h+var_B0]; unsigned __int16 *
0x180075b19  mov     rcx, [rsp+140h+hMem]; unsigned __int16 *
0x180075b1e  mov     [rsp+140h+var_110], eax; int
0x180075b22  mov     eax, [rsp+140h+var_E0]
0x180075b26  mov     [rsp+140h+var_118], edi; unsigned int
0x180075b2a  mov     [rsp+140h+var_120], eax; int
0x180075b2e  call    ?WriteNgcCreateTransportKeyFailureEvent@Logger@@SAJPEBG000HKJ@Z; Logger::WriteNgcCreateTransportKeyFailureEvent(ushort const *,ushort const *,ushort const *,ushort const *,int,ulong,long)
0x180075b33  mov     edx, [rsp+140h+var_E0]
0x180075b37  mov     ecx, edx
0x180075b39  call    GetNgcKeyType
0x180075b3e  mov     r9, [rsp+140h+hMem]
0x180075b43  lea     rcx, aSCannotCreateT; "%s: Cannot create transport key. NgcGet"...
0x180075b4a  mov     dword ptr [rsp+140h+var_F8], edi
0x180075b4e  mov     r8d, ebx
0x180075b51  mov     [rsp+140h+var_100], rax
0x180075b56  mov     rax, [rbp+40h+var_A0]
0x180075b5a  mov     dword ptr [rsp+140h+var_108], edx
0x180075b5e  lea     rdx, aRegistrationke_10; "RegistrationKeyHelper::CreateTransportK"...
0x180075b65  mov     qword ptr [rsp+140h+var_110], rax
0x180075b6a  mov     rax, [rbp+40h+var_A8]
0x180075b6e  mov     qword ptr [rsp+140h+var_118], rax
0x180075b73  mov     rax, [rbp+40h+var_B0]
0x180075b77  mov     qword ptr [rsp+140h+var_120], rax
0x180075b7c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180075b81  jmp     loc_180075C7F
0x180075b86  mov     r9d, [rsp+140h+var_D8]
0x180075b8b  mov     ecx, r9d
0x180075b8e  call    GetKeyStatusName
0x180075b93  mov     r8d, [rsp+140h+var_E0]
0x180075b98  mov     rdx, rax
0x180075b9b  mov     ecx, r8d
0x180075b9e  call    GetNgcKeyType
0x180075ba3  mov     [rsp+140h+var_F0], rdx
0x180075ba8  lea     rcx, aSTransportKeyC_0; "%s: Transport key created. NgcGetSymmet"...
0x180075baf  mov     dword ptr [rsp+140h+var_F8], r9d
0x180075bb4  lea     rdx, aRegistrationke_10; "RegistrationKeyHelper::CreateTransportK"...
0x180075bbb  mov     r9, [rbp+40h+var_B0]
0x180075bbf  mov     dword ptr [rsp+140h+var_100], edi
0x180075bc3  mov     [rsp+140h+var_108], rax
0x180075bc8  mov     rax, [rbp+40h+var_A0]
0x180075bcc  mov     [rsp+140h+var_110], r8d
0x180075bd1  mov     r8, [rsp+140h+hMem]
0x180075bd6  mov     qword ptr [rsp+140h+var_118], rax
0x180075bdb  mov     rax, [rbp+40h+var_A8]
0x180075bdf  mov     qword ptr [rsp+140h+var_120], rax
0x180075be4  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180075be9  mov     rdi, [rbp+40h+var_68]
0x180075bed  test    rdi, rdi
0x180075bf0  jz      short loc_180075C24
0x180075bf2  mov     ecx, [rsp+140h+var_D8]
0x180075bf6  lea     rdx, [rsp+140h+var_DC]
0x180075bfb  call    ?ConvertKeyStatusToDwordKeyType@@YAJW4_NGC_KEY_STATUS@@PEAK@Z; ConvertKeyStatusToDwordKeyType(_NGC_KEY_STATUS,ulong *)
0x180075c00  test    eax, eax
0x180075c02  jns     short loc_180075C1E
0x180075c04  mov     r8d, eax
0x180075c07  lea     rdx, aRegistrationke_10; "RegistrationKeyHelper::CreateTransportK"...
0x180075c0e  lea     rcx, aSConvertkeysta_0; "%s: ConvertKeyStatusToDwordKeyType fail"...
0x180075c15  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180075c1a  xor     eax, eax
0x180075c1c  jmp     short loc_180075C22
0x180075c1e  mov     eax, [rsp+140h+var_DC]
0x180075c22  mov     [rdi], eax
0x180075c24  mov     rax, [rsp+140h+var_C8]
0x180075c29  mov     rcx, [rbp+40h+var_98]
0x180075c2d  mov     [rsp+140h+var_C8], 0
0x180075c36  mov     [rcx], rax
0x180075c39  mov     rcx, [rbp+40h+var_88]
0x180075c3d  mov     rax, [rbp+40h+var_90]
0x180075c41  mov     [rcx], rax
0x180075c44  test    r15, r15
0x180075c47  jz      short loc_180075C60
0x180075c49  mov     rax, [rbp+40h+var_C0]
0x180075c4d  mov     [r15], rax
0x180075c50  mov     rax, [rbp+40h+var_80]
0x180075c54  mov     [r13+0], rax
0x180075c58  mov     [rbp+40h+var_C0], 0
0x180075c60  test    r14, r14
0x180075c63  jz      short loc_180075C7F
0x180075c65  mov     rax, [rbp+40h+var_B8]
0x180075c69  mov     rcx, [rbp+40h+var_70]
0x180075c6d  mov     [r14], rax
0x180075c70  mov     rax, [rbp+40h+var_78]
0x180075c74  mov     [rbp+40h+var_B8], 0
0x180075c7c  mov     [rcx], rax
0x180075c7f  mov     rcx, [rsp+140h+hMem]; hMem
0x180075c84  call    cs:__imp_LocalFree
0x180075c8a  test    ebx, ebx
0x180075c8c  jns     short loc_180075CDF
0x180075c8e  mov     rcx, [rsp+140h+var_C8]; hMem
0x180075c93  call    cs:__imp_LocalFree
0x180075c99  mov     rcx, [rbp+40h+var_C0]; hMem
0x180075c9d  call    cs:__imp_LocalFree
0x180075ca3  mov     rcx, [rbp+40h+var_B8]; hMem
0x180075ca7  call    cs:__imp_LocalFree
0x180075cad  mov     eax, cs:dword_18013D150
0x180075cb3  cmp     eax, 2
0x180075cb6  jbe     short loc_180075D22
0x180075cb8  mov     rdx, 200000000000h
0x180075cc2  lea     rcx, dword_18013D150
0x180075cc9  call    _tlgKeywordOn
0x180075cce  test    al, al
0x180075cd0  jz      short loc_180075D22
0x180075cd2  mov     [rsp+140h+var_DC], ebx
0x180075cd6  lea     rdx, byte_18012A175
0x180075cdd  jmp     short loc_180075D13
0x180075cdf  mov     eax, cs:dword_18013D150
0x180075ce5  cmp     eax, 4
0x180075ce8  jbe     short loc_180075D22
0x180075cea  mov     rdx, 200000000000h
0x180075cf4  lea     rcx, dword_18013D150
0x180075cfb  call    _tlgKeywordOn
0x180075d00  test    al, al
0x180075d02  jz      short loc_180075D22
0x180075d04  mov     eax, [rsp+140h+var_D8]
0x180075d08  lea     rdx, word_18012A136
0x180075d0f  mov     [rsp+140h+var_DC], eax
0x180075d13  lea     rax, [rsp+140h+var_DC]
0x180075d18  mov     qword ptr [rsp+140h+var_120], rax
0x180075d1d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180075d22  cmp     [rbp+40h+var_5C], 0
0x180075d26  jz      short loc_180075D37
0x180075d28  lea     rdx, [rbp+40h+ActivityId]; ActivityId
0x180075d2c  mov     ecx, 4; ControlCode
0x180075d31  call    cs:__imp_EventActivityIdControl
0x180075d37  mov     eax, cs:dword_18013D150
0x180075d3d  mov     [rbp+40h+var_60], 2
0x180075d44  cmp     eax, 5
0x180075d47  jbe     short loc_180075D7D
0x180075d49  mov     rdx, 200000000000h
0x180075d53  lea     rcx, dword_18013D150
0x180075d5a  call    _tlgKeywordOn
0x180075d5f  test    al, al
0x180075d61  jz      short loc_180075D7D
0x180075d63  xor     r9d, r9d
0x180075d66  lea     r8, [rbp+40h+var_58]
0x180075d6a  lea     rdx, dword_18012A30C
0x180075d71  lea     rcx, dword_18013D150
0x180075d78  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
  ... truncated ...
```
