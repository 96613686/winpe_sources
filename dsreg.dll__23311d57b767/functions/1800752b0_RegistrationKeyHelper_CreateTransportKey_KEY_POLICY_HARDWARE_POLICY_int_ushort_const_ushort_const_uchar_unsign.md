# RegistrationKeyHelper::CreateTransportKey(_KEY_POLICY,_HARDWARE_POLICY,int,ushort const *,ushort const *,uchar * *,unsigned __int64 *,uchar * *,unsigned __int64 *,uchar * *,unsigned __int64 *,ulong *)

- ea: `0x1800752b0`
- end: `0x180075862`
- name: `?CreateTransportKey@RegistrationKeyHelper@@SAJW4_KEY_POLICY@@W4_HARDWARE_POLICY@@HPEBG2PEAPEAEPEA_K3434PEAK@Z`
- size: `1458`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800565d8`

## callees

- `0x1800011ec`
- `0x1800012a4`
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
- `0x1800752b0`
- `0x1800765b8`
- `0x180076a7c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800757bb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800757bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800756ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800756fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075706`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075710`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800756ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800756fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075706`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075710`
- `popkeycli!NgcGetSymmetricPopKeyTransportKey` at `0x18007555b`
- `popkeycli!NgcGetSymmetricPopKeyTransportKey` at `0x18007555b`

## string_xrefs

- `0x1800753f7`: `RegistrationKeyHelper::CreateTransportKey`
- `0x180075422`: `RegistrationKeyHelper::CreateTransportKey`
- `0x1800754ca`: `RegistrationKeyHelper::CreateTransportKey`
- `0x1800755bc`: `RegistrationKeyHelper::CreateTransportKey`
- `0x18007561f`: `RegistrationKeyHelper::CreateTransportKey`
- `0x180075669`: `RegistrationKeyHelper::CreateTransportKey`
- `0x18007581d`: `RegistrationKeyHelper::CreateTransportKey`
- `0x1800755a1`: `%s: Cannot create transport key. NgcGetSymmetricPopKeyTransportKey failed with error code 0x%08x. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, NGC key type: %d (%s), Flags: %lu.`
- `0x180075613`: `%s: Transport key created. NgcGetSymmetricPopKeyTransportKey succeeded. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, NGC key type: %d (%s), Flags: %lu, NGC key status: %d (%s).`

## pseudocode

```c
__int64 __fastcall RegistrationKeyHelper::CreateTransportKey(
        unsigned int a1,
        __int64 a2,
        int a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        _QWORD *a6,
        _QWORD *a7,
        HLOCAL *a8,
        _QWORD *a9,
        HLOCAL *a10,
        _QWORD *a11,
        int *a12)
{
  unsigned int v16; // edi
  int CurrentUserSid; // ebx
  const unsigned __int16 *v18; // rdx
  int SymmetricPopKeyTransportKey; // eax
  __int64 v20; // rax
  int v21; // edx
  __int64 KeyStatusName; // rax
  __int64 NgcKeyType; // rax
  int v24; // r9d
  int v25; // r8d
  __int64 v26; // rdx
  int v27; // eax
  int v28; // eax
  HLOCAL v29; // rax
  _QWORD *v30; // rcx
  _QWORD *v31; // rcx
  __int16 *v32; // rdx
  int v34[2]; // [rsp+30h] [rbp-D0h]
  __int64 v35; // [rsp+38h] [rbp-C8h]
  __int64 v36; // [rsp+40h] [rbp-C0h]
  __int64 v37; // [rsp+48h] [rbp-B8h]
  int v38; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v40; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+70h] [rbp-90h]
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL v43; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v44; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL v45; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v46; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v47; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v48; // [rsp+A8h] [rbp-58h]
  _QWORD *v49; // [rsp+B0h] [rbp-50h]
  __int64 v50; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD *v51; // [rsp+C0h] [rbp-40h]
  __int64 v52; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD *v53; // [rsp+D0h] [rbp-30h]
  __int64 v54; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD *v55; // [rsp+E0h] [rbp-20h]
  int v56; // [rsp+E8h] [rbp-18h] BYREF
  char v57; // [rsp+ECh] [rbp-14h]
  GUID ActivityId; // [rsp+100h] [rbp+0h] BYREF

  v49 = a6;
  v51 = a7;
  v53 = a9;
  v55 = a11;
  v40 = 0;
  v38 = 1;
  hMem = 0;
  v16 = a3 != 0 ? 2 : 0;
  v43 = 0;
  v50 = 0;
  v44 = 0;
  if ( a3 )
    a5 = 0;
  v52 = 0;
  v48 = a5;
  v45 = 0;
  v54 = 0;
  v39 = 0;
  v56 = 0;
  v57 = 0;
  v46 = L"login.windows.net";
  v47 = a4;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v56);
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
  {
    v41 = 0x1000000;
    if ( v57 )
      _tlgGuidIsZero(&ActivityId);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_18013D150,
      (__int64)&dword_18012A3E4);
  }
  if ( !a4 )
  {
    CurrentUserSid = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationKeyHelper::CreateTransportKey", L"tenantId");
    v18 = L"tenantId";
LABEL_10:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationKeyHelper::CreateTransportKey", v18);
    goto LABEL_40;
  }
  if ( !v49 )
  {
    CurrentUserSid = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationKeyHelper::CreateTransportKey",
      L"transportKeyPub");
    v18 = L"transportKeyPub";
    goto LABEL_10;
  }
  if ( !v51 )
  {
    CurrentUserSid = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"RegistrationKeyHelper::CreateTransportKey",
      L"transportKeyPubSize");
    v18 = L"transportKeyPubSize";
    goto LABEL_10;
  }
  if ( a8 && !v53 || a10 && !v55 )
  {
    CurrentUserSid = -2147024809;
    Logger::TraceError(
      L"%s: attestationStatement/attestationStatementSize (or aikCertificate/aikCertificateSize) parameters should be non-NULL together.",
      L"RegistrationKeyHelper::CreateTransportKey");
    goto LABEL_40;
  }
  if ( a3 || (CurrentUserSid = GetCurrentUserSid((LPWSTR *)&hMem), CurrentUserSid >= 0) )
  {
    if ( a1 != 1 )
    {
      if ( a1 == 2 )
      {
        v38 = 2;
LABEL_28:
        SymmetricPopKeyTransportKey = NgcGetSymmetricPopKeyTransportKey(
                                        &v46,
                                        hMem,
                                        &v38,
                                        v16,
                                        &v43,
                                        &v50,
                                        &v44,
                                        &v52,
                                        &v45,
                                        &v54,
                                        &v40);
        CurrentUserSid = SymmetricPopKeyTransportKey;
        if ( SymmetricPopKeyTransportKey >= 0 )
        {
          KeyStatusName = GetKeyStatusName(v40);
          NgcKeyType = GetNgcKeyType((unsigned int)v38, KeyStatusName);
          LODWORD(v37) = v24;
          LODWORD(v36) = v16;
          v34[0] = v25;
          Logger::TraceInformation(
            L"%s: Transport key created. NgcGetSymmetricPopKeyTransportKey succeeded. SID: %s, IDP domain: %s, Tenant doma"
             "in: %s, User ID: %s, NGC key type: %d (%s), Flags: %lu, NGC key status: %d (%s).",
            L"RegistrationKeyHelper::CreateTransportKey",
            hMem,
            v46,
            v47,
            v48,
            *(_QWORD *)v34,
            NgcKeyType,
            v36,
            v37,
            v26);
          v27 = ConvertKeyStatusToDwordKeyType(v40, &v39);
          if ( v27 >= 0 )
          {
            v28 = v39;
          }
          else
          {
            Logger::TraceWarning(
              (wchar_t *)L"%s: ConvertKeyStatusToDwordKeyType failed with error code: 0x%08x.",
              L"RegistrationKeyHelper::CreateTransportKey",
              (unsigned int)v27);
            v28 = 0;
          }
          if ( a12 )
            *a12 = v28;
          v29 = v43;
          v43 = 0;
          *v49 = v29;
          *v51 = v50;
          if ( a8 )
          {
            v30 = v53;
            *a8 = v44;
            v44 = 0;
            *v30 = v52;
          }
          if ( a10 )
          {
            v31 = v55;
            *a10 = v45;
            v45 = 0;
            *v31 = v54;
          }
        }
        else
        {
          Logger::WriteNgcCreateTransportKeyFailureEvent(
            (const unsigned __int16 *)hMem,
            v46,
            v47,
            v48,
            v38,
            v16,
            SymmetricPopKeyTransportKey);
          v20 = GetNgcKeyType((unsigned int)v38, (unsigned int)v38);
          LODWORD(v37) = v16;
          LODWORD(v35) = v21;
          Logger::TraceError(
            L"%s: Cannot create transport key. NgcGetSymmetricPopKeyTransportKey failed with error code 0x%08x. SID: %s, I"
             "DP domain: %s, Tenant domain: %s, User ID: %s, NGC key type: %d (%s), Flags: %lu.",
            L"RegistrationKeyHelper::CreateTransportKey",
            (unsigned int)CurrentUserSid,
            hMem,
            v46,
            v47,
            v48,
            v35,
            v20,
            v37);
        }
        goto LABEL_40;
      }
      if ( a1 != 3 )
      {
        CurrentUserSid = -2147024809;
        Logger::TraceError(L"%s: The key policy %d is invalid.", L"RegistrationKeyHelper::CreateTransportKey", a1);
        goto LABEL_40;
      }
      v16 |= 1u;
    }
    v38 = 1;
    goto LABEL_28;
  }
LABEL_40:
  LocalFree(hMem);
  if ( CurrentUserSid >= 0 )
  {
    if ( (unsigned int)dword_18013D150 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
    {
      v32 = (__int16 *)byte_18012A4DB;
      v39 = v40;
      goto LABEL_47;
    }
  }
  else
  {
    LocalFree(v43);
    LocalFree(v44);
    LocalFree(v45);
    if ( (unsigned int)dword_18013D150 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
    {
      v39 = CurrentUserSid;
      v32 = word_18012A52A;
LABEL_47:
      v41 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (__int64)&dword_18013D150,
        (__int64)v32);
    }
  }
  if ( v57 )
    EventActivityIdControl(4u, &ActivityId);
  v56 = 2;
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x200000000000LL) )
  {
    v41 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_18013D150,
      (__int64)&unk_18012A458);
  }
  Logger::TraceVerbose(
    (wchar_t *)L"%s - hr: 0x%08x",
    L"RegistrationKeyHelper::CreateTransportKey",
    (unsigned int)CurrentUserSid);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>((__int64)&v56);
  return (unsigned int)CurrentUserSid;
}

```

## disassembly

```asm
0x1800752b0  mov     [rsp-8+arg_8], rbx
0x1800752b5  push    rbp
0x1800752b6  push    rsi
0x1800752b7  push    rdi
0x1800752b8  push    r12
0x1800752ba  push    r13
0x1800752bc  push    r14
0x1800752be  push    r15
0x1800752c0  lea     rbp, [rsp-20h]
0x1800752c5  sub     rsp, 120h
0x1800752cc  mov     rax, cs:__security_cookie
0x1800752d3  xor     rax, rsp
0x1800752d6  mov     [rbp+50h+var_40], rax
0x1800752da  mov     rax, [rbp+50h+arg_28]
0x1800752e1  xor     edx, edx
0x1800752e3  mov     r15, [rbp+50h+arg_38]
0x1800752ea  mov     esi, ecx
0x1800752ec  mov     rcx, [rbp+50h+arg_20]
0x1800752f3  mov     rbx, r9
0x1800752f6  mov     r14, [rbp+50h+arg_48]
0x1800752fd  mov     r12d, r8d
0x180075300  mov     r13, [rbp+50h+arg_58]
0x180075307  mov     [rbp+50h+var_A0], rax
0x18007530b  mov     rax, [rbp+50h+arg_30]
0x180075312  mov     [rbp+50h+var_90], rax
0x180075316  mov     rax, [rbp+50h+arg_40]
0x18007531d  mov     [rbp+50h+var_80], rax
0x180075321  mov     rax, [rbp+50h+arg_50]
0x180075328  mov     [rbp+50h+var_70], rax
0x18007532c  mov     eax, r8d
0x18007532f  neg     eax
0x180075331  mov     [rsp+150h+var_E8], edx
0x180075335  lea     rax, aLoginWindowsNe; "login.windows.net"
0x18007533c  mov     [rsp+150h+var_F0], 1
0x180075344  sbb     edi, edi
0x180075346  mov     [rsp+150h+hMem], rdx
0x18007534b  and     edi, 2
0x18007534e  mov     [rbp+50h+var_D0], rdx
0x180075352  test    r8d, r8d
0x180075355  mov     [rbp+50h+var_98], rdx
0x180075359  mov     [rbp+50h+var_C8], rdx
0x18007535d  cmovnz  rcx, rdx
0x180075361  mov     [rbp+50h+var_88], rdx
0x180075365  mov     [rbp+50h+var_A8], rcx
0x180075369  lea     rcx, [rbp+50h+var_68]
0x18007536d  mov     [rbp+50h+var_C0], rdx
0x180075371  mov     [rbp+50h+var_78], rdx
0x180075375  mov     [rsp+150h+var_EC], edx
0x180075379  mov     [rbp+50h+var_68], edx
0x18007537c  mov     [rbp+50h+var_64], dl
0x18007537f  mov     [rbp+50h+var_B8], rax
0x180075383  mov     [rbp+50h+var_B0], rbx
0x180075387  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18007538c  mov     eax, cs:dword_18013D150
0x180075392  cmp     eax, 5
0x180075395  jbe     short loc_1800753F7
0x180075397  mov     rdx, 200000000000h
0x1800753a1  lea     rcx, dword_18013D150
0x1800753a8  call    _tlgKeywordOn
0x1800753ad  test    al, al
0x1800753af  jz      short loc_1800753F7
0x1800753b1  cmp     [rbp+50h+var_64], 0
0x1800753b5  mov     [rsp+150h+var_E0], 1000000h
0x1800753be  jz      short loc_1800753D3
0x1800753c0  lea     rcx, [rbp+50h+ActivityId]; struct _GUID *
0x1800753c4  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800753c9  test    al, al
0x1800753cb  jnz     short loc_1800753D3
0x1800753cd  lea     r9, [rbp+50h+ActivityId]
0x1800753d1  jmp     short loc_1800753D6
0x1800753d3  xor     r9d, r9d
0x1800753d6  lea     rax, [rsp+150h+var_E0]
0x1800753db  lea     r8, [rbp+50h+var_60]
0x1800753df  mov     qword ptr [rsp+150h+var_130], rax
0x1800753e4  lea     rdx, dword_18012A3E4
0x1800753eb  lea     rcx, dword_18013D150
0x1800753f2  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800753f7  lea     rdx, aRegistrationke_12; "RegistrationKeyHelper::CreateTransportK"...
0x1800753fe  test    rbx, rbx
0x180075401  jnz     short loc_180075433
0x180075403  lea     r8, aTenantid_1; "tenantId"
0x18007540a  mov     ebx, 80070057h
0x18007540f  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180075416  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007541b  lea     rdx, aTenantid_1; "tenantId"
0x180075422  lea     rcx, aRegistrationke_12; "RegistrationKeyHelper::CreateTransportK"...
0x180075429  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007542e  jmp     loc_1800756E9
0x180075433  cmp     [rbp+50h+var_A0], 0
0x180075438  jnz     short loc_18007545B
0x18007543a  lea     r8, aTransportkeypu; "transportKeyPub"
0x180075441  mov     ebx, 80070057h
0x180075446  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18007544d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180075452  lea     rdx, aTransportkeypu; "transportKeyPub"
0x180075459  jmp     short loc_180075422
0x18007545b  cmp     [rbp+50h+var_90], 0
0x180075460  jnz     short loc_180075483
0x180075462  lea     r8, aTransportkeypu_0; "transportKeyPubSize"
0x180075469  mov     ebx, 80070057h
0x18007546e  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180075475  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007547a  lea     rdx, aTransportkeypu_0; "transportKeyPubSize"
0x180075481  jmp     short loc_180075422
0x180075483  test    r15, r15
0x180075486  jz      short loc_18007548F
0x180075488  cmp     [rbp+50h+var_80], 0
0x18007548d  jz      short loc_18007549B
0x18007548f  test    r14, r14
0x180075492  jz      short loc_1800754B1
0x180075494  cmp     [rbp+50h+var_70], 0
0x180075499  jnz     short loc_1800754B1
0x18007549b  lea     rcx, aSAttestationst; "%s: attestationStatement/attestationSta"...
0x1800754a2  mov     ebx, 80070057h
0x1800754a7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800754ac  jmp     loc_1800756E9
0x1800754b1  test    r12d, r12d
0x1800754b4  jnz     short loc_1800754D1
0x1800754b6  lea     rcx, [rsp+150h+hMem]; StringSid
0x1800754bb  call    ?GetCurrentUserSid@@YAJPEAPEAG@Z; GetCurrentUserSid(ushort * *)
0x1800754c0  mov     ebx, eax
0x1800754c2  test    eax, eax
0x1800754c4  js      loc_1800756E9
0x1800754ca  lea     rdx, aRegistrationke_12; "RegistrationKeyHelper::CreateTransportK"...
0x1800754d1  mov     ecx, esi
0x1800754d3  sub     ecx, 1
0x1800754d6  jz      short loc_180075502
0x1800754d8  sub     ecx, 1
0x1800754db  jz      loc_1800755E4
0x1800754e1  cmp     ecx, 1
0x1800754e4  jz      short loc_1800754FF
0x1800754e6  mov     r8d, esi
0x1800754e9  lea     rcx, aSTheKeyPolicyD; "%s: The key policy %d is invalid."
0x1800754f0  mov     ebx, 80070057h
0x1800754f5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800754fa  jmp     loc_1800756E9
0x1800754ff  or      edi, 1
0x180075502  mov     [rsp+150h+var_F0], 1
0x18007550a  mov     rdx, [rsp+150h+hMem]
0x18007550f  lea     rax, [rsp+150h+var_E8]
0x180075514  mov     [rsp+150h+var_100], rax
0x180075519  lea     r8, [rsp+150h+var_F0]
0x18007551e  lea     rax, [rbp+50h+var_78]
0x180075522  mov     r9d, edi
0x180075525  mov     [rsp+150h+var_108], rax
0x18007552a  lea     rcx, [rbp+50h+var_B8]
0x18007552e  lea     rax, [rbp+50h+var_C0]
0x180075532  mov     [rsp+150h+var_110], rax
0x180075537  lea     rax, [rbp+50h+var_88]
0x18007553b  mov     [rsp+150h+var_118], rax
0x180075540  lea     rax, [rbp+50h+var_C8]
0x180075544  mov     qword ptr [rsp+150h+var_120], rax
0x180075549  lea     rax, [rbp+50h+var_98]
0x18007554d  mov     qword ptr [rsp+150h+var_128], rax
0x180075552  lea     rax, [rbp+50h+var_D0]
0x180075556  mov     qword ptr [rsp+150h+var_130], rax
0x18007555b  call    cs:__imp_NgcGetSymmetricPopKeyTransportKey
0x180075561  mov     ebx, eax
0x180075563  test    eax, eax
0x180075565  jns     loc_1800755F1
0x18007556b  mov     r9, [rbp+50h+var_A8]; unsigned __int16 *
0x18007556f  mov     r8, [rbp+50h+var_B0]; unsigned __int16 *
0x180075573  mov     rdx, [rbp+50h+var_B8]; unsigned __int16 *
0x180075577  mov     rcx, [rsp+150h+hMem]; unsigned __int16 *
0x18007557c  mov     [rsp+150h+var_120], eax; int
0x180075580  mov     eax, [rsp+150h+var_F0]
0x180075584  mov     [rsp+150h+var_128], edi; unsigned int
0x180075588  mov     [rsp+150h+var_130], eax; int
0x18007558c  call    ?WriteNgcCreateTransportKeyFailureEvent@Logger@@SAJPEBG000HKJ@Z; Logger::WriteNgcCreateTransportKeyFailureEvent(ushort const *,ushort const *,ushort const *,ushort const *,int,ulong,long)
0x180075591  mov     edx, [rsp+150h+var_F0]
0x180075595  mov     ecx, edx
0x180075597  call    GetNgcKeyType
0x18007559c  mov     r9, [rsp+150h+hMem]
0x1800755a1  lea     rcx, aSCannotCreateT_0; "%s: Cannot create transport key. NgcGet"...
0x1800755a8  mov     dword ptr [rsp+150h+var_108], edi
0x1800755ac  mov     r8d, ebx
0x1800755af  mov     [rsp+150h+var_110], rax
0x1800755b4  mov     rax, [rbp+50h+var_A8]
0x1800755b8  mov     dword ptr [rsp+150h+var_118], edx
0x1800755bc  lea     rdx, aRegistrationke_12; "RegistrationKeyHelper::CreateTransportK"...
0x1800755c3  mov     qword ptr [rsp+150h+var_120], rax
0x1800755c8  mov     rax, [rbp+50h+var_B0]
0x1800755cc  mov     qword ptr [rsp+150h+var_128], rax
0x1800755d1  mov     rax, [rbp+50h+var_B8]
0x1800755d5  mov     qword ptr [rsp+150h+var_130], rax
0x1800755da  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800755df  jmp     loc_1800756E9
0x1800755e4  mov     [rsp+150h+var_F0], 2
0x1800755ec  jmp     loc_18007550A
0x1800755f1  mov     r9d, [rsp+150h+var_E8]
0x1800755f6  mov     ecx, r9d
0x1800755f9  call    GetKeyStatusName
0x1800755fe  mov     r8d, [rsp+150h+var_F0]
0x180075603  mov     rdx, rax
0x180075606  mov     ecx, r8d
0x180075609  call    GetNgcKeyType
0x18007560e  mov     [rsp+150h+var_100], rdx
0x180075613  lea     rcx, aSTransportKeyC; "%s: Transport key created. NgcGetSymmet"...
0x18007561a  mov     dword ptr [rsp+150h+var_108], r9d
0x18007561f  lea     rdx, aRegistrationke_12; "RegistrationKeyHelper::CreateTransportK"...
0x180075626  mov     r9, [rbp+50h+var_B8]
0x18007562a  mov     dword ptr [rsp+150h+var_110], edi
0x18007562e  mov     [rsp+150h+var_118], rax
0x180075633  mov     rax, [rbp+50h+var_A8]
0x180075637  mov     [rsp+150h+var_120], r8d
0x18007563c  mov     r8, [rsp+150h+hMem]
0x180075641  mov     qword ptr [rsp+150h+var_128], rax
0x180075646  mov     rax, [rbp+50h+var_B0]
0x18007564a  mov     qword ptr [rsp+150h+var_130], rax
0x18007564f  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180075654  mov     ecx, [rsp+150h+var_E8]
0x180075658  lea     rdx, [rsp+150h+var_EC]
0x18007565d  call    ?ConvertKeyStatusToDwordKeyType@@YAJW4_NGC_KEY_STATUS@@PEAK@Z; ConvertKeyStatusToDwordKeyType(_NGC_KEY_STATUS,ulong *)
0x180075662  test    eax, eax
0x180075664  jns     short loc_180075680
0x180075666  mov     r8d, eax
0x180075669  lea     rdx, aRegistrationke_12; "RegistrationKeyHelper::CreateTransportK"...
0x180075670  lea     rcx, aSConvertkeysta_0; "%s: ConvertKeyStatusToDwordKeyType fail"...
0x180075677  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18007567c  xor     eax, eax
0x18007567e  jmp     short loc_180075684
0x180075680  mov     eax, [rsp+150h+var_EC]
0x180075684  test    r13, r13
0x180075687  jz      short loc_18007568D
0x180075689  mov     [r13+0], eax
0x18007568d  mov     rax, [rbp+50h+var_D0]
0x180075691  mov     rcx, [rbp+50h+var_A0]
0x180075695  mov     [rbp+50h+var_D0], 0
0x18007569d  mov     [rcx], rax
0x1800756a0  mov     rcx, [rbp+50h+var_90]
0x1800756a4  mov     rax, [rbp+50h+var_98]
0x1800756a8  mov     [rcx], rax
0x1800756ab  test    r15, r15
0x1800756ae  jz      short loc_1800756CA
0x1800756b0  mov     rax, [rbp+50h+var_C8]
0x1800756b4  mov     rcx, [rbp+50h+var_80]
0x1800756b8  mov     [r15], rax
0x1800756bb  mov     rax, [rbp+50h+var_88]
0x1800756bf  mov     [rbp+50h+var_C8], 0
0x1800756c7  mov     [rcx], rax
0x1800756ca  test    r14, r14
0x1800756cd  jz      short loc_1800756E9
0x1800756cf  mov     rax, [rbp+50h+var_C0]
0x1800756d3  mov     rcx, [rbp+50h+var_70]
0x1800756d7  mov     [r14], rax
0x1800756da  mov     rax, [rbp+50h+var_78]
0x1800756de  mov     [rbp+50h+var_C0], 0
0x1800756e6  mov     [rcx], rax
0x1800756e9  mov     rcx, [rsp+150h+hMem]; hMem
0x1800756ee  call    cs:__imp_LocalFree
0x1800756f4  test    ebx, ebx
0x1800756f6  jns     short loc_18007574C
0x1800756f8  mov     rcx, [rbp+50h+var_D0]; hMem
0x1800756fc  call    cs:__imp_LocalFree
0x180075702  mov     rcx, [rbp+50h+var_C8]; hMem
0x180075706  call    cs:__imp_LocalFree
0x18007570c  mov     rcx, [rbp+50h+var_C0]; hMem
0x180075710  call    cs:__imp_LocalFree
0x180075716  mov     eax, cs:dword_18013D150
0x18007571c  cmp     eax, 2
0x18007571f  jbe     loc_1800757AC
0x180075725  mov     rdx, 200000000000h
0x18007572f  lea     rcx, dword_18013D150
0x180075736  call    _tlgKeywordOn
0x18007573b  test    al, al
0x18007573d  jz      short loc_1800757AC
0x18007573f  mov     [rsp+150h+var_EC], ebx
0x180075743  lea     rdx, word_18012A52A
0x18007574a  jmp     short loc_180075780
0x18007574c  mov     eax, cs:dword_18013D150
0x180075752  cmp     eax, 4
0x180075755  jbe     short loc_1800757AC
0x180075757  mov     rdx, 200000000000h
0x180075761  lea     rcx, dword_18013D150
0x180075768  call    _tlgKeywordOn
0x18007576d  test    al, al
0x18007576f  jz      short loc_1800757AC
0x180075771  mov     eax, [rsp+150h+var_E8]
0x180075775  lea     rdx, byte_18012A4DB
0x18007577c  mov     [rsp+150h+var_EC], eax
0x180075780  lea     rax, [rsp+150h+var_EC]
0x180075785  mov     [rsp+150h+var_E0], 1000000h
0x18007578e  mov     qword ptr [rsp+150h+var_128], rax
0x180075793  lea     rcx, dword_18013D150
0x18007579a  lea     rax, [rsp+150h+var_E0]
0x18007579f  xor     r8d, r8d
0x1800757a2  mov     qword ptr [rsp+150h+var_130], rax
0x1800757a7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800757ac  cmp     [rbp+50h+var_64], 0
0x1800757b0  jz      short loc_1800757C1
0x1800757b2  lea     rdx, [rbp+50h+ActivityId]; ActivityId
0x1800757b6  mov     ecx, 4; ControlCode
0x1800757bb  call    cs:__imp_EventActivityIdControl
0x1800757c1  mov     eax, cs:dword_18013D150
0x1800757c7  mov     [rbp+50h+var_68], 2
0x1800757ce  cmp     eax, 5
0x1800757d1  jbe     short loc_18007581A
0x1800757d3  mov     rdx, 200000000000h
0x1800757dd  lea     rcx, dword_18013D150
0x1800757e4  call    _tlgKeywordOn
  ... truncated ...
```
