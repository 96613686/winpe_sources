# NgcRegController::NgcRegBegin(_DISCOVERY_METADATA *,ushort const *,void (*)(NgcHttpRequest *,STRUCT_NGC_REG_RESPONSE_CALLBACK_CONTEXT *,long),STRUCT_NGC_REG_RESPONSE_CALLBACK_CONTEXT *,NgcHttpRequest *)

- ea: `0x18007f394`
- end: `0x18007fb19`
- name: `?NgcRegBegin@NgcRegController@@AEAAJPEAU_DISCOVERY_METADATA@@PEBGP6AXPEAVNgcHttpRequest@@PEAUSTRUCT_NGC_REG_RESPONSE_CALLBACK_CONTEXT@@J@Z32@Z`
- size: `1925`
- prototype: `int(NgcRegController *__hidden this, struct _DISCOVERY_METADATA *, const unsigned __int16 *, void (*)(struct NgcHttpRequest *, struct STRUCT_NGC_REG_RESPONSE_CALLBACK_CONTEXT *, int), struct STRUCT_NGC_REG_RESPONSE_CALLBACK_CONTEXT *, struct NgcHttpRequest *)`
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18007ec2c`
- `0x18007fb20`

## callees

- `0x1800011ec`
- `0x1800012a4`
- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000bac0`
- `0x180010640`
- `0x180012948`
- `0x1800204f0`
- `0x180025fe0`
- `0x1800307c4`
- `0x180033730`
- `0x180043ef8`
- `0x180044300`
- `0x180051650`
- `0x180055174`
- `0x180055210`
- `0x18006dbb8`
- `0x18006e66c`
- `0x1800794a0`
- `0x18007f394`
- `0x18008305c`
- `0x180083078`
- `0x180083094`
- `0x180083dc8`
- `0x1800840ac`
- `0x18008504c`
- `0x1800851ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f78c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f78c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18007fa6a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18007fa6a`
- `CRYPT32!CertOpenStore` at `0x18007f76a`
- `CRYPT32!CertOpenStore` at `0x18007f76a`
- `CRYPT32!CertCloseStore` at `0x18007fa55`
- `CRYPT32!CertCloseStore` at `0x18007fa55`
- `CRYPT32!CertFreeCertificateContext` at `0x18007f7b4`
- `CRYPT32!CertFreeCertificateContext` at `0x18007fa45`
- `CRYPT32!CertFreeCertificateContext` at `0x18007f7b4`
- `CRYPT32!CertFreeCertificateContext` at `0x18007fa45`
- `RPCRT4!UuidFromStringW` at `0x18007f839`
- `RPCRT4!UuidFromStringW` at `0x18007f839`

## string_xrefs

- `0x18007f526`: `pcszAuthToken`
- `0x18007f540`: `pcszAuthToken`
- `0x18007f957`: `DELETE`
- `0x18007f5ed`: `%s: No existing registration status has been loaded from registry. PATCH operation requires a key ID from a previous successful registration.`
- `0x18007f612`: `%s: No NGC key has been loaded or created. PATCH or DELETE operation requires an NGC key from a previous successful registration.`
- `0x18007f79c`: `%s: Cannot open local machine cert store in read write mode. CertOpenStore failed with error code: 0x%08x.`
- `0x18007f780`: `%s: Opened machine cert store in read write mode. Attach the device cert to the request.`
- `0x18007f8d3`: `NgcRequestSerializer::CreatePostRequestBody`
- `0x18007f882`: `NgcRequestSerializer::CreateHeader`
- `0x18007f902`: `NgcRequestSerializer::CreatePatchRequestBody`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcRegController::NgcRegBegin(
        NgcRegController *this,
        struct _DISCOVERY_METADATA *a2,
        const unsigned __int16 *a3,
        void (*a4)(struct NgcHttpRequest *, struct STRUCT_NGC_REG_RESPONSE_CALLBACK_CONTEXT *, int),
        struct STRUCT_NGC_REG_RESPONSE_CALLBACK_CONTEXT *a5,
        struct NgcHttpRequest *a6)
{
  void *v9; // r12
  PCCERT_CONTEXT v10; // r15
  unsigned int v11; // ebx
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // rcx
  __int64 v14; // rcx
  int EncodedHash; // eax
  int v16; // eax
  const unsigned __int16 *VersionString; // rsi
  const unsigned __int16 *v18; // r10
  int appended; // eax
  __int64 v20; // r8
  unsigned __int16 *v21; // r14
  unsigned __int16 *v22; // r12
  const wchar_t *v23; // r8
  int JoinCertificate; // eax
  DWORD LastError; // eax
  __int64 v26; // r8
  int v27; // eax
  unsigned __int16 *v28; // rcx
  unsigned int v29; // eax
  KeyManager *v30; // rcx
  BOOL v31; // eax
  struct STRUCT_NGC_REG_RESPONSE_CALLBACK_CONTEXT *v32; // rdx
  const unsigned __int16 *v33; // r9
  DWORD_PTR v34; // rdi
  void (*pvPara)(struct NgcHttpRequest *, struct STRUCT_NGC_REG_RESPONSE_CALLBACK_CONTEXT *, int); // [rsp+20h] [rbp-89h]
  PCCERT_CONTEXT pCertContext; // [rsp+30h] [rbp-79h] BYREF
  __int64 v38; // [rsp+38h] [rbp-71h]
  int v39; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int16 *v40; // [rsp+48h] [rbp-61h] BYREF
  void *lpMem; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int16 *v42; // [rsp+58h] [rbp-51h] BYREF
  DWORD_PTR dwContext; // [rsp+60h] [rbp-49h]
  void *Block; // [rsp+68h] [rbp-41h] BYREF
  unsigned __int16 *v45; // [rsp+70h] [rbp-39h] BYREF
  struct STRUCT_NGC_REG_RESPONSE_CALLBACK_CONTEXT *v46; // [rsp+78h] [rbp-31h]
  UUID Uuid; // [rsp+80h] [rbp-29h] BYREF
  int v48; // [rsp+90h] [rbp-19h] BYREF
  char v49; // [rsp+94h] [rbp-15h]
  GUID ActivityId; // [rsp+A8h] [rbp-1h] BYREF

  v46 = a5;
  dwContext = (DWORD_PTR)a6;
  v9 = 0;
  Block = 0;
  v45 = 0;
  v42 = 0;
  v10 = 0;
  pCertContext = 0;
  Uuid = GUID_NULL;
  lpMem = 0;
  v40 = 0;
  Logger::TraceVerbose((wchar_t *)L"%s started", L"NgcRegController::NgcRegBegin", a3, a4);
  v48 = 0;
  v49 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::zInternalStart(&v48);
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x800000000000LL) )
  {
    v38 = 0x1000000;
    if ( v49 )
      _tlgGuidIsZero(&ActivityId);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_18013D150,
      (__int64)word_18012A74A);
  }
  if ( !*((_DWORD *)this + 4) )
  {
    Logger::TraceInformation(L"%s: No registration required.", L"NgcRegController::NgcRegBegin");
    v11 = 0;
    goto LABEL_94;
  }
  v38 = 0;
  if ( a2 )
  {
    if ( !*((_QWORD *)a2 + 9) )
    {
      v11 = -2147024809;
      Logger::TraceError(
        L"%s: \"%s\" should not be null.",
        L"NgcRegController::NgcRegBegin",
        L"pRegistrationInfo->pszKeyProvisioningEndpointReference");
      v12 = L"pRegistrationInfo->pszKeyProvisioningEndpointReference";
      goto LABEL_10;
    }
    if ( !a3 )
    {
      v11 = -2147024809;
      Logger::TraceError(L"%s: \"%s\" should not be null.", L"NgcRegController::NgcRegBegin", L"pcszAuthToken");
      v12 = L"pcszAuthToken";
      goto LABEL_10;
    }
    if ( !a5 )
    {
      v11 = -2147024809;
      Logger::TraceError(L"%s: \"%s\" should not be null.", L"NgcRegController::NgcRegBegin", L"pContext");
      v12 = L"pContext";
      goto LABEL_10;
    }
    if ( !a6 )
    {
      v11 = -2147024809;
      Logger::TraceError(L"%s: \"%s\" should not be null.", L"NgcRegController::NgcRegBegin", L"pRequest");
      v12 = L"pRequest";
      goto LABEL_10;
    }
    if ( !*((_QWORD *)this + 1) )
    {
      v13 = L"%s: Key manager is not initialized.";
LABEL_21:
      v11 = -2147024809;
      Logger::TraceError(v13, L"NgcRegController::NgcRegBegin");
      goto LABEL_84;
    }
    if ( !*(_QWORD *)this )
    {
      v13 = L"%s: Registration status storage is not initialized.";
      goto LABEL_21;
    }
    if ( (unsigned int)NgcStatusStorage::IsEmpty(*(NgcStatusStorage **)this) && *((_DWORD *)this + 4) == 2 )
    {
      v13 = L"%s: No existing registration status has been loaded from registry. PATCH operation requires a key ID from a "
             "previous successful registration.";
      goto LABEL_21;
    }
    if ( (unsigned int)(*((_DWORD *)this + 4) - 2) <= 2 )
    {
      if ( !(unsigned int)KeyManager::HasUserKey(*((KeyManager **)this + 1)) )
      {
        v13 = L"%s: No NGC key has been loaded or created. PATCH or DELETE operation requires an NGC key from a previous s"
               "uccessful registration.";
        goto LABEL_21;
      }
      EncodedHash = GetEncodedHash(
                      *(const unsigned __int8 **)(v14 + 72),
                      *(_DWORD *)(v14 + 80),
                      (unsigned __int16 **)this + 3,
                      1);
      v11 = EncodedHash;
      if ( EncodedHash < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"KeyManager::GetUserKeyPubHashBase64Url",
          L"GetEncodedHashUrlSafe",
          (unsigned int)EncodedHash);
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"NgcRegController::NgcRegBegin",
          L"KeyManager::GetUserKeyPubHashBase64Url",
          v11);
        goto LABEL_84;
      }
      v16 = StringCat(*((const unsigned __int16 **)a2 + 9), *((const unsigned __int16 **)this + 3), &v42);
      v11 = v16;
      if ( v16 < 0 )
      {
        Logger::TraceError(
          L"%s: StringCat failed with error code: 0x%08x",
          L"NgcRegController::NgcRegBegin",
          (unsigned int)v16);
        goto LABEL_84;
      }
    }
    VersionString = (const unsigned __int16 *)UrlHelper::GetVersionString(0);
    if ( !VersionString )
    {
      v11 = -2147024809;
      Logger::TraceError(
        L"%s: Unsupported app version %s. UrlHelper::GetVersionString returns NULL",
        L"NgcRegController::NgcRegBegin",
        0);
      goto LABEL_84;
    }
    appended = ParseUrlAndAppendVersion(v18, VersionString, &v39, (unsigned __int16 **)&Block, &v45);
    v11 = appended;
    v21 = (unsigned __int16 *)Block;
    v22 = v45;
    if ( appended < 0 )
    {
      v23 = L"ParseUrlAndAppendVersion";
      goto LABEL_38;
    }
    JoinCertificate = RegistrationCertStatus::GetJoinCertificate(
                        1,
                        *(_QWORD *)(*((_QWORD *)this + 1) + 24LL),
                        v20,
                        0,
                        &pCertContext);
    v11 = JoinCertificate;
    if ( JoinCertificate >= 0 )
    {
      v38 = (__int64)CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, L"My");
      if ( !v38 )
      {
        LastError = GetLastError();
        Logger::TraceVerbose(
          (wchar_t *)L"%s: Cannot open local machine cert store in read write mode. CertOpenStore failed with error code: 0x%08x.",
          L"NgcRegController::NgcRegBegin",
          LastError);
        v10 = pCertContext;
        if ( pCertContext )
        {
          CertFreeCertificateContext(pCertContext);
          v10 = 0;
        }
LABEL_50:
        if ( !(unsigned int)IsEmptyString(*((const unsigned __int16 **)this + 4)) )
        {
          v29 = UuidFromStringW(v28, &Uuid);
          if ( v29 )
          {
            Logger::TraceWarning(
              (wchar_t *)L"%s: The request ID \"%s\" is not a valid GUID. UuidFromString failed with error code: 0x%08x.",
              L"NgcRegController::NgcRegBegin",
              *((_QWORD *)this + 4),
              v29);
            Uuid = GUID_NULL;
          }
        }
        appended = NgcRequestSerializer::CreateHeader(&Uuid, a3, VersionString, (unsigned __int16 **)&lpMem);
        v11 = appended;
        if ( appended >= 0 )
        {
          v31 = (unsigned int)KeyManager::HasAikCert(*((KeyManager **)this + 1))
             && (unsigned int)KeyManager::HasUserKeyAtt(v30);
          if ( *((_DWORD *)this + 4) == 1 )
          {
            appended = NgcRequestSerializer::CreateRequestBody(v30, 1u, v31 ? -1 : 1, &v40);
            v11 = appended;
            if ( appended < 0 )
            {
              v23 = L"NgcRequestSerializer::CreatePostRequestBody";
              goto LABEL_38;
            }
          }
          else if ( *((_DWORD *)this + 4) == 2 )
          {
            appended = NgcRequestSerializer::CreateRequestBody(v30, 0, v31 ? -1 : 1, &v40);
            v11 = appended;
            if ( appended < 0 )
            {
              v23 = L"NgcRequestSerializer::CreatePatchRequestBody";
              goto LABEL_38;
            }
          }
          v32 = v46;
          *((_QWORD *)v46 + 2) = this;
          *(UUID *)((char *)v32 + 24) = Uuid;
          if ( *((_DWORD *)this + 4) == 1 )
          {
            v33 = L"POST";
          }
          else if ( *((_DWORD *)this + 4) == 2 )
          {
            v33 = L"PATCH";
          }
          else
          {
            if ( (unsigned int)(*((_DWORD *)this + 4) - 3) >= 2 )
            {
              v11 = -2147024809;
              Logger::TraceError(
                L"%s: Unsupported http method %d. NgcRegController::GetHttpMethod returns NULL",
                L"NgcRegController::NgcRegBegin");
              goto LABEL_79;
            }
            v33 = L"DELETE";
          }
          v34 = dwContext;
          appended = NgcHttpRequest::Initialize((NgcHttpRequest *)dwContext, v21, v22, v33, pvPara, v32);
          v11 = appended;
          if ( appended >= 0 )
          {
            appended = NgcHttpRequest::Send(v34, (const unsigned __int16 *)lpMem, v40, v10);
            v11 = appended;
            if ( appended >= 0 )
              goto LABEL_79;
            v23 = L"NgcHttpRequest::Send";
          }
          else
          {
            v23 = L"NgcHttpRequest::Initialize";
          }
        }
        else
        {
          v23 = L"NgcRequestSerializer::CreateHeader";
        }
LABEL_38:
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"NgcRegController::NgcRegBegin",
          v23,
          (unsigned int)appended);
LABEL_79:
        if ( v21 )
          operator delete(v21);
        if ( v22 )
          operator delete(v22);
        v9 = (void *)v38;
        goto LABEL_84;
      }
      Logger::TraceVerbose(
        L"%s: Opened machine cert store in read write mode. Attach the device cert to the request.",
        L"NgcRegController::NgcRegBegin");
LABEL_49:
      v10 = pCertContext;
      goto LABEL_50;
    }
    if ( JoinCertificate == -2146885628 )
    {
      Logger::TraceVerbose(
        (wchar_t *)L"%s: Cannot find device cert. Try searching for workpalce cert.",
        L"NgcRegController::NgcRegBegin");
      v27 = RegistrationCertStatus::GetJoinCertificate(
              0,
              *(_QWORD *)(*((_QWORD *)this + 1) + 24LL),
              v26,
              0,
              &pCertContext);
      v11 = v27;
      if ( v27 >= 0 )
      {
        Logger::TraceVerbose(L"%s: Attach the workplace cert to the request.", L"NgcRegController::NgcRegBegin");
        goto LABEL_49;
      }
      if ( v27 == -2146885628 )
      {
        Logger::TraceVerbose(
          (wchar_t *)L"%s: Cannot find workplace cert. Will not attach any cert to the request.",
          L"NgcRegController::NgcRegBegin");
        goto LABEL_49;
      }
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"NgcRegController::NgcRegBegin",
        L"RegistrationCertStatus::GetWorkplaceCertificate",
        (unsigned int)v27);
    }
    else
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"NgcRegController::NgcRegBegin",
        L"RegistrationCertStatus::GetDeviceCertificate",
        (unsigned int)JoinCertificate);
      v38 = 0;
    }
    v10 = pCertContext;
    goto LABEL_79;
  }
  v11 = -2147024809;
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"NgcRegController::NgcRegBegin", L"pRegistrationInfo");
  v12 = L"pRegistrationInfo";
LABEL_10:
  Logger::WriteNullOrEmptyParameterFailureEvent(L"NgcRegController::NgcRegBegin", v12);
LABEL_84:
  SafeFree(lpMem);
  SafeFree(v40);
  SafeFree(v42);
  if ( v10 )
    CertFreeCertificateContext(v10);
  if ( v9 )
    CertCloseStore(v9, 0);
  if ( v49 )
    EventActivityIdControl(4u, &ActivityId);
  v48 = 2;
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x800000000000LL) )
  {
    v39 = v11;
    dwContext = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)&dword_18013D150,
      (__int64)&byte_18012A56F);
  }
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"NgcRegController::NgcRegBegin", v11);
LABEL_94:
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>((__int64)&v48);
  return v11;
}

```

## disassembly

```asm
0x18007f394  mov     [rsp-8+arg_18], rbx
0x18007f399  push    rbp
0x18007f39a  push    rsi
0x18007f39b  push    rdi
0x18007f39c  push    r12
0x18007f39e  push    r13
0x18007f3a0  push    r14
0x18007f3a2  push    r15
0x18007f3a4  lea     rbp, [rsp-17h]
0x18007f3a9  sub     rsp, 0C0h
0x18007f3b0  mov     rax, cs:__security_cookie
0x18007f3b7  xor     rax, rsp
0x18007f3ba  mov     [rbp+47h+var_38], rax
0x18007f3be  mov     r13, r8
0x18007f3c1  mov     rsi, rdx
0x18007f3c4  mov     rdi, rcx
0x18007f3c7  mov     rbx, [rbp+47h+arg_20]
0x18007f3cb  mov     [rbp+47h+var_78], rbx
0x18007f3cf  mov     r14, [rbp+47h+arg_28]
0x18007f3d3  mov     [rbp+47h+dwContext], r14
0x18007f3d7  xor     r12d, r12d
0x18007f3da  mov     [rbp+47h+Block], r12
0x18007f3de  mov     [rbp+47h+var_80], r12
0x18007f3e2  mov     [rbp+47h+var_98], r12
0x18007f3e6  mov     r15d, r12d
0x18007f3e9  mov     [rbp+47h+pCertContext], r12
0x18007f3ed  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18007f3f4  movdqu  xmmword ptr [rbp+47h+Uuid.Data1], xmm0
0x18007f3f9  mov     [rbp+47h+lpMem], r12
0x18007f3fd  mov     [rbp+47h+var_A8], r12
0x18007f401  lea     rdx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f408  lea     rcx, aSStarted; "%s started"
0x18007f40f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007f414  mov     [rbp+47h+var_60], r12d
0x18007f418  mov     [rbp+47h+var_5C], r12b
0x18007f41c  lea     rcx, [rbp+47h+var_60]
0x18007f420  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0IAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0IAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::zInternalStart(void)
0x18007f425  mov     eax, cs:dword_18013D150
0x18007f42b  cmp     eax, 5
0x18007f42e  jbe     short loc_18007F48C
0x18007f430  mov     rdx, 800000000000h
0x18007f43a  lea     rcx, dword_18013D150
0x18007f441  call    _tlgKeywordOn
0x18007f446  test    al, al
0x18007f448  jz      short loc_18007F48C
0x18007f44a  mov     [rbp+47h+var_B8], 1000000h
0x18007f452  cmp     [rbp+47h+var_5C], r12b
0x18007f456  jz      short loc_18007F469
0x18007f458  lea     rcx, [rbp+47h+ActivityId]; struct _GUID *
0x18007f45c  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18007f461  test    al, al
0x18007f463  lea     r9, [rbp+47h+ActivityId]
0x18007f467  jz      short loc_18007F46C
0x18007f469  mov     r9, r12
0x18007f46c  lea     rax, [rbp+47h+var_B8]
0x18007f470  mov     [rsp+0F0h+pvPara], rax
0x18007f475  lea     r8, [rbp+47h+var_58]
0x18007f479  lea     rdx, word_18012A74A
0x18007f480  lea     rcx, dword_18013D150
0x18007f487  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18007f48c  cmp     [rdi+10h], r12d
0x18007f490  jnz     short loc_18007F4AD
0x18007f492  lea     rdx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f499  lea     rcx, aSNoRegistratio; "%s: No registration required."
0x18007f4a0  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18007f4a5  mov     ebx, r12d
0x18007f4a8  jmp     loc_18007FAE7
0x18007f4ad  mov     [rbp+47h+var_B8], r12
0x18007f4b1  test    rsi, rsi
0x18007f4b4  jnz     short loc_18007F4ED
0x18007f4b6  mov     ebx, 80070057h
0x18007f4bb  lea     r8, aPregistrationi_0; "pRegistrationInfo"
0x18007f4c2  lea     rdx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f4c9  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18007f4d0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007f4d5  lea     rdx, aPregistrationi_0; "pRegistrationInfo"
0x18007f4dc  lea     rcx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f4e3  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007f4e8  jmp     loc_18007FA22
0x18007f4ed  cmp     qword ptr [rsi+48h], 0
0x18007f4f2  jnz     short loc_18007F51C
0x18007f4f4  mov     ebx, 80070057h
0x18007f4f9  lea     r8, aPregistrationi; "pRegistrationInfo->pszKeyProvisioningEn"...
0x18007f500  lea     rdx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f507  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18007f50e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007f513  lea     rdx, aPregistrationi; "pRegistrationInfo->pszKeyProvisioningEn"...
0x18007f51a  jmp     short loc_18007F4DC
0x18007f51c  test    r13, r13
0x18007f51f  jnz     short loc_18007F549
0x18007f521  mov     ebx, 80070057h
0x18007f526  lea     r8, aPcszauthtoken; "pcszAuthToken"
0x18007f52d  lea     rdx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f534  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18007f53b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007f540  lea     rdx, aPcszauthtoken; "pcszAuthToken"
0x18007f547  jmp     short loc_18007F4DC
0x18007f549  test    rbx, rbx
0x18007f54c  jnz     short loc_18007F579
0x18007f54e  mov     ebx, 80070057h
0x18007f553  lea     r8, aPcontext; "pContext"
0x18007f55a  lea     rdx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f561  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18007f568  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007f56d  lea     rdx, aPcontext; "pContext"
0x18007f574  jmp     loc_18007F4DC
0x18007f579  test    r14, r14
0x18007f57c  jnz     short loc_18007F5A9
0x18007f57e  mov     ebx, 80070057h
0x18007f583  lea     r8, aPrequest; "pRequest"
0x18007f58a  lea     rdx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f591  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18007f598  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007f59d  lea     rdx, aPrequest; "pRequest"
0x18007f5a4  jmp     loc_18007F4DC
0x18007f5a9  cmp     qword ptr [rdi+8], 0
0x18007f5ae  jnz     short loc_18007F5CD
0x18007f5b0  lea     rcx, aSKeyManagerIsN; "%s: Key manager is not initialized."
0x18007f5b7  lea     rdx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f5be  mov     ebx, 80070057h
0x18007f5c3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007f5c8  jmp     loc_18007FA22
0x18007f5cd  mov     rcx, [rdi]; this
0x18007f5d0  test    rcx, rcx
0x18007f5d3  jnz     short loc_18007F5DE
0x18007f5d5  lea     rcx, aSRegistrationS; "%s: Registration status storage is not "...
0x18007f5dc  jmp     short loc_18007F5B7
0x18007f5de  call    ?IsEmpty@NgcStatusStorage@@QEAAHXZ; NgcStatusStorage::IsEmpty(void)
0x18007f5e3  test    eax, eax
0x18007f5e5  jz      short loc_18007F5F6
0x18007f5e7  cmp     dword ptr [rdi+10h], 2
0x18007f5eb  jnz     short loc_18007F5F6
0x18007f5ed  lea     rcx, aSNoExistingReg; "%s: No existing registration status has"...
0x18007f5f4  jmp     short loc_18007F5B7
0x18007f5f6  mov     eax, [rdi+10h]
0x18007f5f9  sub     eax, 2
0x18007f5fc  cmp     eax, 2
0x18007f5ff  ja      loc_18007F6AE
0x18007f605  mov     rcx, [rdi+8]; this
0x18007f609  call    ?HasUserKey@KeyManager@@QEAAHXZ; KeyManager::HasUserKey(void)
0x18007f60e  test    eax, eax
0x18007f610  jnz     short loc_18007F61B
0x18007f612  lea     rcx, aSNoNgcKeyHasBe; "%s: No NGC key has been loaded or creat"...
0x18007f619  jmp     short loc_18007F5B7
0x18007f61b  mov     r9d, 1; int
0x18007f621  lea     r8, [rdi+18h]; unsigned __int16 **
0x18007f625  mov     edx, [rcx+50h]; unsigned int
0x18007f628  mov     rcx, [rcx+48h]; unsigned __int8 *
0x18007f62c  call    ?GetEncodedHash@@YAJPEBEKPEAPEAGH@Z; GetEncodedHash(uchar const *,ulong,ushort * *,int)
0x18007f631  mov     ebx, eax
0x18007f633  test    eax, eax
0x18007f635  jns     short loc_18007F676
0x18007f637  mov     r9d, eax
0x18007f63a  lea     r8, aGetencodedhash; "GetEncodedHashUrlSafe"
0x18007f641  lea     rdx, aKeymanagerGetu_0; "KeyManager::GetUserKeyPubHashBase64Url"
0x18007f648  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18007f64f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007f654  mov     r9d, ebx
0x18007f657  lea     r8, aKeymanagerGetu_0; "KeyManager::GetUserKeyPubHashBase64Url"
0x18007f65e  lea     rdx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f665  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18007f66c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007f671  jmp     loc_18007FA22
0x18007f676  lea     r8, [rbp+47h+var_98]; unsigned __int16 **
0x18007f67a  mov     rdx, [rdi+18h]; unsigned __int16 *
0x18007f67e  mov     rcx, [rsi+48h]; unsigned __int16 *
0x18007f682  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x18007f687  mov     ebx, eax
0x18007f689  test    eax, eax
0x18007f68b  jns     short loc_18007F6A8
0x18007f68d  mov     r8d, eax
0x18007f690  lea     rdx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f697  lea     rcx, aSStringcatFail; "%s: StringCat failed with error code: 0"...
0x18007f69e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007f6a3  jmp     loc_18007FA22
0x18007f6a8  mov     r10, [rbp+47h+var_98]
0x18007f6ac  jmp     short loc_18007F6B2
0x18007f6ae  mov     r10, [rsi+48h]
0x18007f6b2  xor     ecx, ecx
0x18007f6b4  call    ?GetVersionString@UrlHelper@@SAPEAGW4_URL_VERSION@@@Z; UrlHelper::GetVersionString(_URL_VERSION)
0x18007f6b9  mov     rsi, rax
0x18007f6bc  test    rax, rax
0x18007f6bf  jnz     short loc_18007F6E1
0x18007f6c1  mov     ebx, 80070057h
0x18007f6c6  xor     r8d, r8d
0x18007f6c9  lea     rdx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f6d0  lea     rcx, aSUnsupportedAp_0; "%s: Unsupported app version %s. UrlHelp"...
0x18007f6d7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007f6dc  jmp     loc_18007FA22
0x18007f6e1  lea     rax, [rbp+47h+var_80]
0x18007f6e5  mov     [rsp+0F0h+pvPara], rax; unsigned __int16 **
0x18007f6ea  lea     r9, [rbp+47h+Block]; unsigned __int16 **
0x18007f6ee  lea     r8, [rbp+47h+var_B0]; int *
0x18007f6f2  mov     rdx, rsi; unsigned __int16 *
0x18007f6f5  mov     rcx, r10; unsigned __int16 *
0x18007f6f8  call    ?ParseUrlAndAppendVersion@@YAJPEBG0PEAHPEAPEAG2@Z; ParseUrlAndAppendVersion(ushort const *,ushort const *,int *,ushort * *,ushort * *)
0x18007f6fd  mov     ebx, eax
0x18007f6ff  mov     r14, [rbp+47h+Block]
0x18007f703  mov     r12, [rbp+47h+var_80]
0x18007f707  test    eax, eax
0x18007f709  jns     short loc_18007F72D
0x18007f70b  lea     r8, aParseurlandapp; "ParseUrlAndAppendVersion"
0x18007f712  mov     r9d, eax
0x18007f715  lea     rdx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f71c  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18007f723  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007f728  jmp     loc_18007FA04
0x18007f72d  mov     rdx, [rdi+8]
0x18007f731  lea     rax, [rbp+47h+pCertContext]
0x18007f735  mov     [rsp+0F0h+pvPara], rax
0x18007f73a  xor     r9d, r9d
0x18007f73d  mov     rdx, [rdx+18h]
0x18007f741  lea     ecx, [r9+1]
0x18007f745  call    ?GetJoinCertificate@RegistrationCertStatus@@SAJW4_CERTFICATE_LOCATION@@PEBG1W4INFO_KIND@@PEAPEBU_CERT_CONTEXT@@@Z; RegistrationCertStatus::GetJoinCertificate(_CERTFICATE_LOCATION,ushort const *,ushort const *,INFO_KIND,_CERT_CONTEXT const * *)
0x18007f74a  mov     ebx, eax
0x18007f74c  test    eax, eax
0x18007f74e  js      short loc_18007F7BF
0x18007f750  lea     rax, aMy; "My"
0x18007f757  mov     [rsp+0F0h+pvPara], rax; pvPara
0x18007f75c  mov     r9d, 20000h; dwFlags
0x18007f762  xor     r8d, r8d; hCryptProv
0x18007f765  xor     edx, edx; dwEncodingType
0x18007f767  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18007f76a  call    cs:__imp_CertOpenStore
0x18007f770  mov     [rbp+47h+var_B8], rax
0x18007f774  test    rax, rax
0x18007f777  jz      short loc_18007F78C
0x18007f779  lea     rdx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f780  lea     rcx, aSOpenedMachine; "%s: Opened machine cert store in read w"...
0x18007f787  jmp     loc_18007F81F
0x18007f78c  call    cs:__imp_GetLastError
0x18007f792  mov     r8d, eax
0x18007f795  lea     rdx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f79c  lea     rcx, aSCannotOpenLoc; "%s: Cannot open local machine cert stor"...
0x18007f7a3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007f7a8  mov     r15, [rbp+47h+pCertContext]
0x18007f7ac  test    r15, r15
0x18007f7af  jz      short loc_18007F828
0x18007f7b1  mov     rcx, r15; pCertContext
0x18007f7b4  call    cs:__imp_CertFreeCertificateContext
0x18007f7ba  xor     r15d, r15d
0x18007f7bd  jmp     short loc_18007F828
0x18007f7bf  cmp     eax, 80092004h
0x18007f7c4  jnz     loc_18007F9DD
0x18007f7ca  lea     r15, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f7d1  mov     rdx, r15
0x18007f7d4  lea     rcx, aSCannotFindDev; "%s: Cannot find device cert. Try search"...
0x18007f7db  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007f7e0  mov     rdx, [rdi+8]
0x18007f7e4  lea     rax, [rbp+47h+pCertContext]
0x18007f7e8  mov     [rsp+0F0h+pvPara], rax; void (*)(struct NgcHttpRequest *, struct STRUCT_NGC_REG_RESPONSE_CALLBACK_CONTEXT *, int)
0x18007f7ed  xor     r9d, r9d
0x18007f7f0  mov     rdx, [rdx+18h]
0x18007f7f4  xor     ecx, ecx
0x18007f7f6  call    ?GetJoinCertificate@RegistrationCertStatus@@SAJW4_CERTFICATE_LOCATION@@PEBG1W4INFO_KIND@@PEAPEBU_CERT_CONTEXT@@@Z; RegistrationCertStatus::GetJoinCertificate(_CERTFICATE_LOCATION,ushort const *,ushort const *,INFO_KIND,_CERT_CONTEXT const * *)
0x18007f7fb  mov     ebx, eax
0x18007f7fd  test    eax, eax
0x18007f7ff  js      short loc_18007F80A
0x18007f801  lea     rcx, aSAttachTheWork; "%s: Attach the workplace cert to the re"...
0x18007f808  jmp     short loc_18007F81C
0x18007f80a  cmp     eax, 80092004h
0x18007f80f  jnz     loc_18007F9BE
0x18007f815  lea     rcx, aSCannotFindWor; "%s: Cannot find workplace cert. Will no"...
0x18007f81c  mov     rdx, r15
0x18007f81f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007f824  mov     r15, [rbp+47h+pCertContext]
0x18007f828  mov     rcx, [rdi+20h]; unsigned __int16 *
0x18007f82c  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18007f831  test    eax, eax
0x18007f833  jnz     short loc_18007F869
0x18007f835  lea     rdx, [rbp+47h+Uuid]; Uuid
0x18007f839  call    cs:__imp_UuidFromStringW
0x18007f83f  test    eax, eax
0x18007f841  jz      short loc_18007F869
0x18007f843  mov     r9d, eax
0x18007f846  mov     r8, [rdi+20h]
0x18007f84a  lea     rdx, aNgcregcontroll_14; "NgcRegController::NgcRegBegin"
0x18007f851  lea     rcx, aSTheRequestIdS; "%s: The request ID \"%s\" is not a vali"...
0x18007f858  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18007f85d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18007f864  movdqu  xmmword ptr [rbp+47h+Uuid.Data1], xmm0
0x18007f869  lea     r9, [rbp+47h+lpMem]; unsigned __int16 **
0x18007f86d  mov     r8, rsi; unsigned __int16 *
0x18007f870  mov     rdx, r13; unsigned __int16 *
0x18007f873  lea     rcx, [rbp+47h+Uuid]; struct _GUID *
0x18007f877  call    ?CreateHeader@NgcRequestSerializer@@SAJPEBU_GUID@@PEBG1PEAPEAG@Z; NgcRequestSerializer::CreateHeader(_GUID const *,ushort const *,ushort const *,ushort * *)
0x18007f87c  mov     ebx, eax
0x18007f87e  test    eax, eax
0x18007f880  jns     short loc_18007F88E
0x18007f882  lea     r8, aNgcrequestseri_1; "NgcRequestSerializer::CreateHeader"
0x18007f889  jmp     loc_18007F712
0x18007f88e  mov     rcx, [rdi+8]; this
0x18007f892  call    ?HasAikCert@KeyManager@@QEAAHXZ; KeyManager::HasAikCert(void)
0x18007f897  test    eax, eax
0x18007f899  jz      short loc_18007F8AB
0x18007f89b  call    ?HasUserKeyAtt@KeyManager@@QEAAHXZ; KeyManager::HasUserKeyAtt(void)
0x18007f8a0  test    eax, eax
0x18007f8a2  jz      short loc_18007F8AB
0x18007f8a4  mov     eax, 1
0x18007f8a9  jmp     short loc_18007F8AD
  ... truncated ...
```
