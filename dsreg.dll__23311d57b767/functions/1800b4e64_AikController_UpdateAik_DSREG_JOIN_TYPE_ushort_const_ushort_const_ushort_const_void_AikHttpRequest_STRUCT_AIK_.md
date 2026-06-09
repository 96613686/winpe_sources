# AikController::UpdateAik(_DSREG_JOIN_TYPE,ushort const *,ushort const *,ushort const *,void (*)(AikHttpRequest *,STRUCT_AIK_RESPONSE_CALLBACK_CONTEXT *,long),STRUCT_AIK_RESPONSE_CALLBACK_CONTEXT *)

- ea: `0x1800b4e64`
- end: `0x1800b55ca`
- name: `?UpdateAik@AikController@@AEAAJW4_DSREG_JOIN_TYPE@@PEBG11P6AXPEAVAikHttpRequest@@PEAUSTRUCT_AIK_RESPONSE_CALLBACK_CONTEXT@@J@Z3@Z`
- size: `1894`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800b55d0`

## callees

- `0x1800012a4`
- `0x180003ba0`
- `0x180005ba0`
- `0x1800084f4`
- `0x180009780`
- `0x18000bac0`
- `0x18000f368`
- `0x180017bb0`
- `0x1800204f0`
- `0x1800307c4`
- `0x18003334c`
- `0x180039940`
- `0x180040394`
- `0x180040f50`
- `0x180043ef8`
- `0x180044300`
- `0x18004651c`
- `0x180051604`
- `0x180055174`
- `0x180055194`
- `0x18006e66c`
- `0x180074300`
- `0x180075dcc`
- `0x180077118`
- `0x18008ccb4`
- `0x1800b4bd0`
- `0x1800b4d24`
- `0x1800b4e64`
- `0x1800b5818`
- `0x1800b59ec`
- `0x1800b60a4`
- `0x1800b636c`
- `0x1800b66dc`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800b5483`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800b5483`
- `RPCRT4!RpcStringFreeW` at `0x1800b557b`
- `RPCRT4!RpcStringFreeW` at `0x1800b557b`
- `RPCRT4!UuidToStringW` at `0x1800b5082`
- `RPCRT4!UuidToStringW` at `0x1800b5082`

## string_xrefs

- `0x1800b506e`: `CreateGuid`
- `0x1800b4eb7`: `AikController::UpdateAik`
- `0x1800b4f1c`: `AikController::UpdateAik`
- `0x1800b4f36`: `AikController::UpdateAik`
- `0x1800b4fd9`: `AikController::UpdateAik`
- `0x1800b5092`: `AikController::UpdateAik`
- `0x1800b50d4`: `AikController::UpdateAik`
- `0x1800b52bc`: `AikController::UpdateAik`
- `0x1800b52d8`: `AikController::UpdateAik`
- `0x1800b53f9`: `AikController::UpdateAik`
- `0x1800b5461`: `AikController::UpdateAik`
- `0x1800b5584`: `AikController::UpdateAik`
- `0x1800b51d5`: `AikRequestSerializer::CreateRequestBody`
- `0x1800b51ae`: `AikRequestSerializer::CreateHeader`
- `0x1800b5170`: `AikManager::CreateTokenBindingAik`
- `0x1800b50cd`: `AikController::GetUpdateEndpoint`
- `0x1800b5468`: `%s: Token binding AIK update begin succeeded. Join type: %d, Tenant ID: "%s", Device ID: "%s", User SID: "%s", Token: "%s", Request ID: "%s".`
- `0x1800b5400`: `%s: Token binding AIK update begin failed with error code 0x%08x. Join type: %d, Tenant ID: "%s", Device ID: "%s", User SID: "%s", Token: "%s", Request ID: "%s".`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AikController::UpdateAik(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        __int64 a6,
        struct STRUCT_AIK_RESPONSE_CALLBACK_CONTEXT *a7)
{
  int v9; // r15d
  unsigned __int16 *v10; // r12
  unsigned __int16 *v11; // rdi
  unsigned int v12; // ebx
  int appended; // eax
  const wchar_t *v14; // r8
  __int64 v15; // r9
  unsigned int v16; // eax
  int UpdateEndpoint; // eax
  int v18; // r8d
  unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // r13
  const struct _CERT_CONTEXT *v22; // r9
  int v23; // eax
  unsigned int i; // edi
  unsigned __int16 *v25; // r14
  unsigned __int16 *v26; // rdi
  unsigned __int16 *v27; // rsi
  unsigned __int16 *v28; // r15
  unsigned int v29; // r12d
  const unsigned __int16 *v30; // rax
  unsigned __int16 *v31; // rdi
  unsigned __int16 *v32; // rsi
  const unsigned __int16 *v33; // rax
  __int64 v34; // r9
  int *v36; // [rsp+20h] [rbp-E0h]
  unsigned int v38; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v39; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v40; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v41; // [rsp+80h] [rbp-80h] BYREF
  void *Block; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v43; // [rsp+90h] [rbp-70h] BYREF
  void *lpMem; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v45; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v46; // [rsp+A8h] [rbp-58h] BYREF
  int v47[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v48; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v49; // [rsp+C0h] [rbp-40h]
  RPC_WSTR StringUuid; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v51; // [rsp+D0h] [rbp-30h] BYREF
  int v52; // [rsp+D8h] [rbp-28h] BYREF
  char v53; // [rsp+DCh] [rbp-24h]
  _BYTE v54[16]; // [rsp+E0h] [rbp-20h] BYREF
  GUID ActivityId; // [rsp+F0h] [rbp-10h] BYREF
  UUID Uuid; // [rsp+100h] [rbp+0h] BYREF

  v49 = a3;
  v48 = a5;
  v38 = 2;
  Logger::TraceVerbose((wchar_t *)L"%s started", L"AikController::UpdateAik");
  v9 = 0;
  StringUuid = 0;
  Uuid = 0;
  v46 = 0;
  v10 = 0;
  v39 = 0;
  Block = 0;
  v43 = 0;
  lpMem = 0;
  v45 = 0;
  v51 = 0;
  v40 = 0;
  v41 = 0;
  v11 = 0;
  v52 = 0;
  v53 = 0;
  if ( !a7 )
  {
    v12 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"AikController::UpdateAik", L"pContext");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"AikController::UpdateAik", L"pContext");
LABEL_44:
    v21 = a4;
    goto LABEL_45;
  }
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v52);
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
  {
    *(_QWORD *)v47 = 0x1000000;
    if ( v53 )
      _tlgGuidIsZero(&ActivityId);
    v36 = v47;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_18013D150,
      (__int64)byte_18012BB83);
  }
  appended = AikController::Initialize(a1, 2, a3);
  v12 = appended;
  if ( appended < 0 )
  {
    v14 = L"AikController::Initialize";
LABEL_10:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"AikController::UpdateAik",
      v14,
      (unsigned int)appended,
      v36);
    goto LABEL_44;
  }
  v38 = **(_DWORD **)(*(_QWORD *)(a1 + 8) + 8LL);
  if ( (unsigned int)IsEmptyString(v49) )
  {
    appended = StringDup(*(const unsigned __int16 **)(v15 + 32), &v51, 0);
    v12 = appended;
    if ( appended < 0 )
    {
LABEL_13:
      v14 = L"StringDup";
      goto LABEL_10;
    }
    v49 = v51;
  }
  appended = StringDup(*(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 16LL), &v40, 0);
  v12 = appended;
  if ( appended < 0 )
    goto LABEL_13;
  if ( (unsigned int)IsEmptyString(a5) )
  {
    appended = CreateGuid(&Uuid);
    v12 = appended;
    if ( appended < 0 )
    {
      v14 = L"CreateGuid";
      goto LABEL_10;
    }
    v16 = UuidToStringW(&Uuid, &StringUuid);
    v9 = v16;
    if ( v16 )
    {
      Logger::TraceError(
        L"%s: Cannot convert the request ID to a string. UuidToStringW failed with error code: 0x%08x.",
        L"AikController::UpdateAik",
        v16);
      goto LABEL_44;
    }
    v48 = StringUuid;
  }
  UpdateEndpoint = AikController::GetUpdateEndpoint(*(struct _DSREG_ACCOUNT_INFO_2 **)(*(_QWORD *)(a1 + 8) + 8LL), &v39);
  v12 = UpdateEndpoint;
  if ( UpdateEndpoint < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"AikController::UpdateAik",
      L"AikController::GetUpdateEndpoint",
      (unsigned int)UpdateEndpoint);
    v10 = v39;
    goto LABEL_44;
  }
  v10 = v39;
  appended = ParseUrlAndAppendVersion(v39, L"3.0", v47, (unsigned __int16 **)&Block, &v43);
  v12 = appended;
  if ( appended < 0 )
  {
    v14 = L"ParseUrlAndAppendVersion";
    goto LABEL_10;
  }
  appended = GetCertificatePublicKeyHash(
               *(const struct _CERT_CONTEXT **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 8LL),
               &v46,
               v18);
  v12 = appended;
  if ( appended < 0 )
  {
    v14 = L"GetCertificatePublicKeyHash";
    goto LABEL_10;
  }
  appended = AikManager::CreateTokenBindingAiks(
               a1 + 16,
               **(unsigned int **)(*(_QWORD *)(a1 + 8) + 8LL),
               v46,
               *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 32LL));
  v12 = appended;
  if ( appended < 0 )
  {
    v14 = L"AikManager::CreateTokenBindingAik";
    goto LABEL_10;
  }
  appended = StringDup(*(const unsigned __int16 **)(a1 + 72), &v41, 0);
  v12 = appended;
  if ( appended < 0 )
    goto LABEL_13;
  appended = AikRequestSerializer::CreateHeader(v48, a4, (unsigned __int16 **)&lpMem);
  v12 = appended;
  if ( appended < 0 )
  {
    v14 = L"AikRequestSerializer::CreateHeader";
    goto LABEL_10;
  }
  appended = AikRequestSerializer::CreateRequestBody(
               (const struct ByteArray *)(a1 + 24),
               (const struct ByteArray *)(a1 + 40),
               (const struct ByteArray *)(a1 + 56),
               &v45);
  v12 = appended;
  if ( appended < 0 )
  {
    v14 = L"AikRequestSerializer::CreateRequestBody";
    goto LABEL_10;
  }
  *((_QWORD *)a7 + 2) = a1;
  v19 = (unsigned __int16 *)operator new(0xD0u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v19;
  v39 = v19;
  if ( !v19 )
  {
    v11 = 0;
    v12 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"AikController::UpdateAik");
    goto LABEL_44;
  }
  WinHttpRequest::WinHttpRequest((WinHttpRequest *)v19, 120000);
  *(_QWORD *)v11 = &AikHttpRequest::`vftable';
  *((_QWORD *)v11 + 22) = 0;
  *((_QWORD *)v11 + 25) = 0;
  *((_QWORD *)v11 + 24) = 0;
  *((_QWORD *)v11 + 23) = 0;
  appended = AikHttpRequest::Initialize(
               (AikHttpRequest *)v11,
               (const unsigned __int16 *)Block,
               v43,
               v20,
               (void (*)(struct AikHttpRequest *, struct STRUCT_AIK_RESPONSE_CALLBACK_CONTEXT *, int))v36,
               a7);
  v12 = appended;
  if ( appended < 0 )
  {
    v14 = L"AikHttpRequest::Initialize";
    goto LABEL_10;
  }
  v21 = a4;
  if ( (unsigned int)IsEmptyString(a4) )
    v22 = *(const struct _CERT_CONTEXT **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 8LL);
  else
    v22 = 0;
  v23 = AikHttpRequest::Send((DWORD_PTR)v11, (const unsigned __int16 *)lpMem, v45, v22);
  v12 = v23;
  if ( v23 < 0 )
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"AikController::UpdateAik",
      L"AikHttpRequest::Send",
      (unsigned int)v23);
LABEL_45:
  operator delete(Block);
  operator delete(v43);
  SafeFree(lpMem);
  SafeFree(v45);
  SafeFree(v46);
  SafeFree(v10);
  if ( v9 )
  {
    if ( v9 > 0 )
      v12 = (unsigned __int16)v9 | 0x80070000;
    else
      v12 = v9;
  }
  if ( (v12 & 0x80000000) == 0 )
  {
    v25 = v48;
    v31 = v41;
    v32 = v40;
    v28 = v49;
    v29 = v38;
    Logger::WriteBeginUpdateAikSuccessEvent(v38, v49, v40, v41, v21, v48);
    v33 = Logger::LogSensitiveString(v21);
    Logger::TraceVerbose(
      (wchar_t *)L"%s: Token binding AIK update begin succeeded. Join type: %d, Tenant ID: \"%s\", Device ID: \"%s\", User"
                  " SID: \"%s\", Token: \"%s\", Request ID: \"%s\".",
      L"AikController::UpdateAik",
      v38,
      v28,
      v32,
      v31,
      v33,
      v25);
  }
  else
  {
    if ( v11 )
      (**(void (__fastcall ***)(unsigned __int16 *, __int64))v11)(v11, 1);
    for ( i = 0; (int)i < 3; ++i )
    {
      if ( *(_QWORD *)(a1 + 16LL * i + 24)
        && *(_QWORD *)(a1 + 16LL * i + 32)
        && (int)RegistrationKeyHelper::DeleteAik(
                  i,
                  *(const unsigned __int16 **)(a1 + 88),
                  *(const unsigned __int16 **)(a1 + 80),
                  *(const wchar_t **)(a1 + 72)) >= 0 )
      {
        ByteArray::Reset((ByteArray *)(a1 + 24 + 16LL * i));
      }
    }
    v25 = v48;
    v26 = v41;
    v27 = v40;
    v28 = v49;
    v29 = v38;
    Logger::WriteBeginUpdateAikFailureEvent(v12, v38, v49, v40, v41, v21, v48);
    v30 = Logger::LogSensitiveString(v21);
    Logger::TraceError(
      L"%s: Token binding AIK update begin failed with error code 0x%08x. Join type: %d, Tenant ID: \"%s\", Device ID: \"%"
       "s\", User SID: \"%s\", Token: \"%s\", Request ID: \"%s\".",
      L"AikController::UpdateAik",
      v12,
      v38,
      v28,
      v27,
      v26,
      v30,
      v25);
  }
  if ( v53 )
    EventActivityIdControl(4u, &ActivityId);
  v52 = 2;
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
  {
    v46 = v25;
    v45 = (unsigned __int16 *)Logger::LogSensitiveString(v21);
    lpMem = v41;
    v43 = v40;
    Block = v28;
    v38 = v29;
    v47[0] = v12;
    v39 = (unsigned __int16 *)0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)&dword_18013D150,
      (__int64)&word_18012BBB6,
      (__int64)v54,
      v34,
      (__int64)&v39,
      (__int64)v47,
      (__int64)&v38,
      &Block,
      &v43,
      &lpMem,
      &v45,
      &v46);
  }
  SafeFree(v51);
  SafeFree(v40);
  SafeFree(v41);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"AikController::UpdateAik", v12);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v52);
  return v12;
}

```

## disassembly

```asm
0x1800b4e64  mov     [rsp-8+arg_8], rbx
0x1800b4e69  push    rbp
0x1800b4e6a  push    rsi
0x1800b4e6b  push    rdi
0x1800b4e6c  push    r12
0x1800b4e6e  push    r13
0x1800b4e70  push    r14
0x1800b4e72  push    r15
0x1800b4e74  lea     rbp, [rsp-20h]
0x1800b4e79  sub     rsp, 120h
0x1800b4e80  mov     rax, cs:__security_cookie
0x1800b4e87  xor     rax, rsp
0x1800b4e8a  mov     [rbp+50h+var_40], rax
0x1800b4e8e  mov     [rsp+150h+var_F0], r9
0x1800b4e93  mov     rbx, r8
0x1800b4e96  mov     [rbp+50h+var_90], rbx
0x1800b4e9a  mov     r14, rcx
0x1800b4e9d  mov     rsi, [rbp+50h+arg_20]
0x1800b4ea4  mov     [rbp+50h+var_98], rsi
0x1800b4ea8  mov     r13, [rbp+50h+arg_30]
0x1800b4eaf  mov     [rsp+150h+var_E8], 2
0x1800b4eb7  lea     rdx, aAikcontrollerU_0; "AikController::UpdateAik"
0x1800b4ebe  lea     rcx, aSStarted; "%s started"
0x1800b4ec5  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b4eca  xor     eax, eax
0x1800b4ecc  mov     r15d, eax
0x1800b4ecf  mov     [rbp+50h+StringUuid], rax
0x1800b4ed3  xorps   xmm0, xmm0
0x1800b4ed6  movups  xmmword ptr [rbp+50h+Uuid.Data1], xmm0
0x1800b4eda  mov     [rbp+50h+var_A8], rax
0x1800b4ede  mov     r12d, eax
0x1800b4ee1  mov     [rsp+150h+var_E0], rax
0x1800b4ee6  mov     [rbp+50h+Block], rax
0x1800b4eea  mov     [rbp+50h+var_C0], rax
0x1800b4eee  mov     [rbp+50h+lpMem], rax
0x1800b4ef2  mov     [rbp+50h+var_B0], rax
0x1800b4ef6  mov     [rbp+50h+var_80], rax
0x1800b4efa  mov     [rsp+150h+var_D8], rax
0x1800b4eff  mov     [rbp+50h+var_D0], rax
0x1800b4f03  mov     edi, eax
0x1800b4f05  mov     [rbp+50h+var_78], eax
0x1800b4f08  mov     [rbp+50h+var_74], al
0x1800b4f0b  test    r13, r13
0x1800b4f0e  jnz     short loc_1800B4F47
0x1800b4f10  mov     ebx, 80070057h
0x1800b4f15  lea     r8, aPcontext; "pContext"
0x1800b4f1c  lea     rdx, aAikcontrollerU_0; "AikController::UpdateAik"
0x1800b4f23  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800b4f2a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b4f2f  lea     rdx, aPcontext; "pContext"
0x1800b4f36  lea     rcx, aAikcontrollerU_0; "AikController::UpdateAik"
0x1800b4f3d  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800b4f42  jmp     loc_1800B52EB
0x1800b4f47  lea     rcx, [rbp+50h+var_78]
0x1800b4f4b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x1800b4f50  mov     eax, cs:dword_18013D150
0x1800b4f56  cmp     eax, 5
0x1800b4f59  jbe     short loc_1800B4FB9
0x1800b4f5b  mov     rdx, 400000000000h
0x1800b4f65  lea     rcx, dword_18013D150
0x1800b4f6c  call    _tlgKeywordOn
0x1800b4f71  test    al, al
0x1800b4f73  jz      short loc_1800B4FB9
0x1800b4f75  mov     qword ptr [rbp+50h+var_A0], 1000000h
0x1800b4f7d  cmp     [rbp+50h+var_74], 0
0x1800b4f81  jz      short loc_1800B4F96
0x1800b4f83  lea     rcx, [rbp+50h+ActivityId]; struct _GUID *
0x1800b4f87  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800b4f8c  test    al, al
0x1800b4f8e  jnz     short loc_1800B4F96
0x1800b4f90  lea     r9, [rbp+50h+ActivityId]
0x1800b4f94  jmp     short loc_1800B4F99
0x1800b4f96  xor     r9d, r9d
0x1800b4f99  lea     rax, [rbp+50h+var_A0]
0x1800b4f9d  mov     [rsp+150h+var_130], rax
0x1800b4fa2  lea     r8, [rbp+50h+var_70]
0x1800b4fa6  lea     rdx, byte_18012BB83
0x1800b4fad  lea     rcx, dword_18013D150
0x1800b4fb4  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800b4fb9  mov     r8, rbx
0x1800b4fbc  mov     edx, 2
0x1800b4fc1  mov     rcx, r14
0x1800b4fc4  call    ?Initialize@AikController@@AEAAJW4_DSREG_JOIN_TYPE@@PEBG@Z; AikController::Initialize(_DSREG_JOIN_TYPE,ushort const *)
0x1800b4fc9  mov     ebx, eax
0x1800b4fcb  test    eax, eax
0x1800b4fcd  jns     short loc_1800B4FF1
0x1800b4fcf  lea     r8, aAikcontrollerI; "AikController::Initialize"
0x1800b4fd6  mov     r9d, eax
0x1800b4fd9  lea     rdx, aAikcontrollerU_0; "AikController::UpdateAik"
0x1800b4fe0  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800b4fe7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b4fec  jmp     loc_1800B52EB
0x1800b4ff1  mov     rax, [r14+8]
0x1800b4ff5  mov     r9, [rax+8]
0x1800b4ff9  mov     eax, [r9]
0x1800b4ffc  mov     [rsp+150h+var_E8], eax
0x1800b5000  mov     rcx, [rbp+50h+var_90]; unsigned __int16 *
0x1800b5004  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800b5009  test    eax, eax
0x1800b500b  jz      short loc_1800B5034
0x1800b500d  xor     r8d, r8d; int
0x1800b5010  lea     rdx, [rbp+50h+var_80]; unsigned __int16 **
0x1800b5014  mov     rcx, [r9+20h]; unsigned __int16 *
0x1800b5018  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x1800b501d  mov     ebx, eax
0x1800b501f  test    eax, eax
0x1800b5021  jns     short loc_1800B502C
0x1800b5023  lea     r8, aStringdup; "StringDup"
0x1800b502a  jmp     short loc_1800B4FD6
0x1800b502c  mov     rcx, [rbp+50h+var_80]
0x1800b5030  mov     [rbp+50h+var_90], rcx
0x1800b5034  mov     rax, [r14+8]
0x1800b5038  mov     rcx, [rax+8]
0x1800b503c  xor     r8d, r8d; int
0x1800b503f  lea     rdx, [rsp+150h+var_D8]; unsigned __int16 **
0x1800b5044  mov     rcx, [rcx+10h]; unsigned __int16 *
0x1800b5048  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x1800b504d  mov     ebx, eax
0x1800b504f  test    eax, eax
0x1800b5051  js      short loc_1800B5023
0x1800b5053  mov     rcx, rsi; unsigned __int16 *
0x1800b5056  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800b505b  test    eax, eax
0x1800b505d  jz      short loc_1800B50B2
0x1800b505f  lea     rcx, [rbp+50h+Uuid]; struct _GUID *
0x1800b5063  call    ?CreateGuid@@YAJPEAU_GUID@@@Z; CreateGuid(_GUID *)
0x1800b5068  mov     ebx, eax
0x1800b506a  test    eax, eax
0x1800b506c  jns     short loc_1800B507A
0x1800b506e  lea     r8, aCreateguid; "CreateGuid"
0x1800b5075  jmp     loc_1800B4FD6
0x1800b507a  lea     rdx, [rbp+50h+StringUuid]; StringUuid
0x1800b507e  lea     rcx, [rbp+50h+Uuid]; Uuid
0x1800b5082  call    cs:__imp_UuidToStringW
0x1800b5088  mov     r15d, eax
0x1800b508b  test    eax, eax
0x1800b508d  jz      short loc_1800B50AA
0x1800b508f  mov     r8d, eax
0x1800b5092  lea     rdx, aAikcontrollerU_0; "AikController::UpdateAik"
0x1800b5099  lea     rcx, aSCannotConvert_0; "%s: Cannot convert the request ID to a "...
0x1800b50a0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b50a5  jmp     loc_1800B52EB
0x1800b50aa  mov     rax, [rbp+50h+StringUuid]
0x1800b50ae  mov     [rbp+50h+var_98], rax
0x1800b50b2  mov     rcx, [r14+8]
0x1800b50b6  lea     rdx, [rsp+150h+var_E0]; unsigned __int16 **
0x1800b50bb  mov     rcx, [rcx+8]; struct _DSREG_ACCOUNT_INFO_2 *
0x1800b50bf  call    ?GetUpdateEndpoint@AikController@@CAJPEAU_DSREG_ACCOUNT_INFO_2@@PEAPEAG@Z; AikController::GetUpdateEndpoint(_DSREG_ACCOUNT_INFO_2 *,ushort * *)
0x1800b50c4  mov     ebx, eax
0x1800b50c6  test    eax, eax
0x1800b50c8  jns     short loc_1800B50F1
0x1800b50ca  mov     r9d, eax
0x1800b50cd  lea     r8, aAikcontrollerG; "AikController::GetUpdateEndpoint"
0x1800b50d4  lea     rdx, aAikcontrollerU_0; "AikController::UpdateAik"
0x1800b50db  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800b50e2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b50e7  mov     r12, [rsp+150h+var_E0]
0x1800b50ec  jmp     loc_1800B52EB
0x1800b50f1  lea     rax, [rbp+50h+var_C0]
0x1800b50f5  mov     [rsp+150h+var_130], rax; void (*)(struct AikHttpRequest *, struct STRUCT_AIK_RESPONSE_CALLBACK_CONTEXT *, int)
0x1800b50fa  lea     r9, [rbp+50h+Block]; unsigned __int16 **
0x1800b50fe  lea     r8, [rbp+50h+var_A0]; int *
0x1800b5102  lea     rdx, Buffer; "3.0"
0x1800b5109  mov     r12, [rsp+150h+var_E0]
0x1800b510e  mov     rcx, r12; unsigned __int16 *
0x1800b5111  call    ?ParseUrlAndAppendVersion@@YAJPEBG0PEAHPEAPEAG2@Z; ParseUrlAndAppendVersion(ushort const *,ushort const *,int *,ushort * *,ushort * *)
0x1800b5116  mov     ebx, eax
0x1800b5118  test    eax, eax
0x1800b511a  jns     short loc_1800B5128
0x1800b511c  lea     r8, aParseurlandapp; "ParseUrlAndAppendVersion"
0x1800b5123  jmp     loc_1800B4FD6
0x1800b5128  mov     rax, [r14+8]
0x1800b512c  mov     rcx, [rax+8]
0x1800b5130  lea     rdx, [rbp+50h+var_A8]; unsigned __int16 **
0x1800b5134  mov     rcx, [rcx+8]; struct _CERT_CONTEXT *
0x1800b5138  call    ?GetCertificatePublicKeyHash@@YAJPEBU_CERT_CONTEXT@@PEAPEAGH@Z; GetCertificatePublicKeyHash(_CERT_CONTEXT const *,ushort * *,int)
0x1800b513d  mov     ebx, eax
0x1800b513f  test    eax, eax
0x1800b5141  jns     short loc_1800B514F
0x1800b5143  lea     r8, aGetcertificate_0; "GetCertificatePublicKeyHash"
0x1800b514a  jmp     loc_1800B4FD6
0x1800b514f  mov     rax, [r14+8]
0x1800b5153  mov     rdx, [rax+8]
0x1800b5157  mov     r9, [rdx+20h]
0x1800b515b  mov     r8, [rbp+50h+var_A8]
0x1800b515f  mov     edx, [rdx]
0x1800b5161  lea     rcx, [r14+10h]
0x1800b5165  call    ?CreateTokenBindingAiks@AikManager@@QEAAJW4_DSREG_JOIN_TYPE@@PEBG11@Z; AikManager::CreateTokenBindingAiks(_DSREG_JOIN_TYPE,ushort const *,ushort const *,ushort const *)
0x1800b516a  mov     ebx, eax
0x1800b516c  test    eax, eax
0x1800b516e  jns     short loc_1800B517C
0x1800b5170  lea     r8, aAikmanagerCrea_1; "AikManager::CreateTokenBindingAik"
0x1800b5177  jmp     loc_1800B4FD6
0x1800b517c  xor     r8d, r8d; int
0x1800b517f  lea     rdx, [rbp+50h+var_D0]; unsigned __int16 **
0x1800b5183  mov     rcx, [r14+48h]; unsigned __int16 *
0x1800b5187  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x1800b518c  mov     ebx, eax
0x1800b518e  test    eax, eax
0x1800b5190  js      loc_1800B5023
0x1800b5196  lea     r8, [rbp+50h+lpMem]; unsigned __int16 **
0x1800b519a  mov     rdx, [rsp+150h+var_F0]; unsigned __int16 *
0x1800b519f  mov     rcx, [rbp+50h+var_98]; unsigned __int16 *
0x1800b51a3  call    ?CreateHeader@AikRequestSerializer@@SAJPEBG0PEAPEAG@Z; AikRequestSerializer::CreateHeader(ushort const *,ushort const *,ushort * *)
0x1800b51a8  mov     ebx, eax
0x1800b51aa  test    eax, eax
0x1800b51ac  jns     short loc_1800B51BA
0x1800b51ae  lea     r8, aAikrequestseri_0; "AikRequestSerializer::CreateHeader"
0x1800b51b5  jmp     loc_1800B4FD6
0x1800b51ba  lea     r8, [r14+38h]; struct ByteArray *
0x1800b51be  lea     rdx, [r14+28h]; struct ByteArray *
0x1800b51c2  lea     rcx, [r14+18h]; struct ByteArray *
0x1800b51c6  lea     r9, [rbp+50h+var_B0]; unsigned __int16 **
0x1800b51ca  call    ?CreateRequestBody@AikRequestSerializer@@SAJAEBVByteArray@@00PEAPEAG@Z; AikRequestSerializer::CreateRequestBody(ByteArray const &,ByteArray const &,ByteArray const &,ushort * *)
0x1800b51cf  mov     ebx, eax
0x1800b51d1  test    eax, eax
0x1800b51d3  jns     short loc_1800B51E1
0x1800b51d5  lea     r8, aAikrequestseri; "AikRequestSerializer::CreateRequestBody"
0x1800b51dc  jmp     loc_1800B4FD6
0x1800b51e1  mov     [r13+10h], r14
0x1800b51e5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b51ec  mov     ecx, 0D0h; unsigned __int64
0x1800b51f1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b51f6  mov     rdi, rax
0x1800b51f9  mov     [rsp+150h+var_E0], rax
0x1800b51fe  test    rax, rax
0x1800b5201  jz      loc_1800B52D1
0x1800b5207  mov     edx, 1D4C0h; int
0x1800b520c  mov     rcx, rax; this
0x1800b520f  call    ??0WinHttpRequest@@QEAA@H@Z; WinHttpRequest::WinHttpRequest(int)
0x1800b5214  lea     rcx, ??_7AikHttpRequest@@6B@; const AikHttpRequest::`vftable'
0x1800b521b  mov     [rdi], rcx
0x1800b521e  mov     qword ptr [rdi+0B0h], 0
0x1800b5229  mov     qword ptr [rdi+0C8h], 0
0x1800b5234  mov     qword ptr [rdi+0C0h], 0
0x1800b523f  mov     qword ptr [rdi+0B8h], 0
0x1800b524a  test    rdi, rdi
0x1800b524d  jz      loc_1800B52D3
0x1800b5253  mov     [rsp+150h+var_128], r13; struct STRUCT_AIK_RESPONSE_CALLBACK_CONTEXT *
0x1800b5258  mov     r8, [rbp+50h+var_C0]; unsigned __int16 *
0x1800b525c  mov     rdx, [rbp+50h+Block]; unsigned __int16 *
0x1800b5260  mov     rcx, rdi; this
0x1800b5263  call    ?Initialize@AikHttpRequest@@QEAAJPEBG00P6AXPEAV1@PEAUSTRUCT_AIK_RESPONSE_CALLBACK_CONTEXT@@J@Z2@Z; AikHttpRequest::Initialize(ushort const *,ushort const *,ushort const *,void (*)(AikHttpRequest *,STRUCT_AIK_RESPONSE_CALLBACK_CONTEXT *,long),STRUCT_AIK_RESPONSE_CALLBACK_CONTEXT *)
0x1800b5268  mov     ebx, eax
0x1800b526a  test    eax, eax
0x1800b526c  jns     short loc_1800B527A
0x1800b526e  lea     r8, aAikhttprequest_6; "AikHttpRequest::Initialize"
0x1800b5275  jmp     loc_1800B4FD6
0x1800b527a  mov     r13, [rsp+150h+var_F0]
0x1800b527f  mov     rcx, r13; unsigned __int16 *
0x1800b5282  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800b5287  test    eax, eax
0x1800b5289  jz      short loc_1800B5299
0x1800b528b  mov     rax, [r14+8]
0x1800b528f  mov     rcx, [rax+8]
0x1800b5293  mov     r9, [rcx+8]
0x1800b5297  jmp     short loc_1800B529C
0x1800b5299  xor     r9d, r9d; struct _CERT_CONTEXT *
0x1800b529c  mov     r8, [rbp+50h+var_B0]; unsigned __int16 *
0x1800b52a0  mov     rdx, [rbp+50h+lpMem]; unsigned __int16 *
0x1800b52a4  mov     rcx, rdi; dwContext
0x1800b52a7  call    ?Send@AikHttpRequest@@QEAAJPEBG0PEBU_CERT_CONTEXT@@@Z; AikHttpRequest::Send(ushort const *,ushort const *,_CERT_CONTEXT const *)
0x1800b52ac  mov     ebx, eax
0x1800b52ae  test    eax, eax
0x1800b52b0  jns     short loc_1800B52F0
0x1800b52b2  mov     r9d, eax
0x1800b52b5  lea     r8, aAikhttprequest_4; "AikHttpRequest::Send"
0x1800b52bc  lea     rdx, aAikcontrollerU_0; "AikController::UpdateAik"
0x1800b52c3  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800b52ca  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b52cf  jmp     short loc_1800B52F0
0x1800b52d1  xor     edi, edi
0x1800b52d3  mov     ebx, 8007000Eh
0x1800b52d8  lea     rdx, aAikcontrollerU_0; "AikController::UpdateAik"
0x1800b52df  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x1800b52e6  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800b52eb  mov     r13, [rsp+150h+var_F0]
0x1800b52f0  mov     rcx, [rbp+50h+Block]; Block
0x1800b52f4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b52f9  mov     rcx, [rbp+50h+var_C0]; Block
0x1800b52fd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b5302  mov     rcx, [rbp+50h+lpMem]; lpMem
0x1800b5306  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800b530b  mov     rcx, [rbp+50h+var_B0]; lpMem
0x1800b530f  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800b5314  mov     rcx, [rbp+50h+var_A8]; lpMem
0x1800b5318  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800b531d  mov     rcx, r12; lpMem
0x1800b5320  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800b5325  test    r15d, r15d
0x1800b5328  jz      short loc_1800B533B
0x1800b532a  jg      short loc_1800B5331
0x1800b532c  mov     ebx, r15d
0x1800b532f  jmp     short loc_1800B533B
0x1800b5331  movzx   ebx, r15w
0x1800b5335  or      ebx, 80070000h
0x1800b533b  test    ebx, ebx
0x1800b533d  jns     loc_1800B540E
0x1800b5343  test    rdi, rdi
0x1800b5346  jz      short loc_1800B535B
  ... truncated ...
```
