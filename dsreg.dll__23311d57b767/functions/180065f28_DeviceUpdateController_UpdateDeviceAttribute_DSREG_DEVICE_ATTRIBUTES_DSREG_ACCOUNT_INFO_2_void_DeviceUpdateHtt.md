# DeviceUpdateController::UpdateDeviceAttribute(_DSREG_DEVICE_ATTRIBUTES,_DSREG_ACCOUNT_INFO_2 *,void (*)(DeviceUpdateHttpRequest *,STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *,long),STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *)

- ea: `0x180065f28`
- end: `0x180066671`
- name: `?UpdateDeviceAttribute@DeviceUpdateController@@AEAAJW4_DSREG_DEVICE_ATTRIBUTES@@PEAU_DSREG_ACCOUNT_INFO_2@@P6AXPEAVDeviceUpdateHttpRequest@@PEAUSTRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT@@J@Z3@Z`
- size: `1865`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, struct STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180066678`

## callees

- `0x1800016f8`
- `0x1800017ec`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000bac0`
- `0x18000f368`
- `0x18001b560`
- `0x18001f1b4`
- `0x1800204f0`
- `0x1800307c4`
- `0x18003334c`
- `0x18003c9d0`
- `0x18003f034`
- `0x180043ef8`
- `0x180044300`
- `0x18004651c`
- `0x180051604`
- `0x180055174`
- `0x180055194`
- `0x18006552c`
- `0x18006565c`
- `0x1800658d8`
- `0x180065f28`
- `0x180066f68`
- `0x18006724c`
- `0x1800677cc`
- `0x180067b44`
- `0x18006e66c`
- `0x180077118`
- `0x180078f80`
- `0x180079210`
- `0x1800793ec`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180066569`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180066569`
- `RPCRT4!RpcStringFreeW` at `0x180066622`
- `RPCRT4!RpcStringFreeW` at `0x180066622`
- `RPCRT4!UuidToStringW` at `0x180066494`
- `RPCRT4!UuidToStringW` at `0x180066494`

## string_xrefs

- `0x1800660d9`: `CreateGuid`
- `0x18006645e`: `%s: DeviceUpdateController::SaveAttribute failed with error code: 0x%08x. Attribute: "%s", Device ID: "%s".`
- `0x180065f90`: `DeviceUpdateController::UpdateDeviceAttribute`
- `0x180066072`: `DeviceUpdateController::UpdateDeviceAttribute`
- `0x18006609f`: `DeviceUpdateController::UpdateDeviceAttribute`
- `0x1800660b9`: `DeviceUpdateController::UpdateDeviceAttribute`
- `0x1800660e3`: `DeviceUpdateController::UpdateDeviceAttribute`
- `0x180066386`: `DeviceUpdateController::UpdateDeviceAttribute`
- `0x180066457`: `DeviceUpdateController::UpdateDeviceAttribute`
- `0x1800664a1`: `DeviceUpdateController::UpdateDeviceAttribute`
- `0x1800664fe`: `DeviceUpdateController::UpdateDeviceAttribute`
- `0x180066547`: `DeviceUpdateController::UpdateDeviceAttribute`
- `0x18006662b`: `DeviceUpdateController::UpdateDeviceAttribute`
- `0x180066111`: `DeviceUpdateController::GetUpdateEndpoint`
- `0x180066163`: `DeviceUpdateRequestSerializer::CreateHeader`
- `0x180066223`: `StringCompareIgnoreCase`
- `0x1800662a6`: `DeviceUpdateRequestSerializer::CreatePostRequestBody`
- `0x18006633b`: `DeviceUpdateHttpRequest::Initialize`
- `0x180066373`: `DeviceUpdateHttpRequest::Send`
- `0x180066505`: `%s: Device update begin failed. Attribute: "%s", Tenant ID: "%s", Device ID: "%s", Join type: %d, Request ID: %s, Error code: 0x%08x.`
- `0x18006654e`: `%s: Device update begin succeeded. Attribute: "%s", Tenant ID: "%s", Device ID: "%s", Join type: %d, Request ID: %s.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeviceUpdateController::UpdateDeviceAttribute(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        struct STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *a5)
{
  __int64 v7; // r14
  WinHttpRequest *v8; // rdi
  const WCHAR *v9; // r15
  bool IsZero; // al
  GUID *p_ActivityId; // r9
  int v12; // ebx
  const unsigned __int16 *v13; // rdx
  int UpdateEndpoint; // eax
  const wchar_t *v15; // r8
  const unsigned __int16 *v16; // rdx
  __int64 v17; // r8
  int v18; // eax
  const unsigned __int16 *v19; // rdx
  const WCHAR *v20; // rcx
  WinHttpRequest *v21; // rax
  const unsigned __int16 *v22; // r9
  void *v23; // rcx
  __int64 v24; // rdx
  _BYTE *v25; // rax
  unsigned __int16 *v26; // rcx
  unsigned __int64 v27; // rdx
  unsigned __int16 *v28; // rax
  __int64 v29; // rax
  __int64 v30; // r8
  const WCHAR *v31; // r14
  unsigned int v32; // edi
  unsigned int v33; // eax
  __int64 v34; // rax
  __int64 v35; // rsi
  int v36; // r9d
  unsigned __int64 *v38; // [rsp+20h] [rbp-E0h]
  struct _CERT_CONTEXT *v39; // [rsp+28h] [rbp-D8h]
  struct _CERT_CONTEXT *v40; // [rsp+28h] [rbp-D8h]
  __int64 v41; // [rsp+38h] [rbp-C8h]
  int v42; // [rsp+50h] [rbp-B0h] BYREF
  RPC_WSTR StringUuid; // [rsp+58h] [rbp-A8h] BYREF
  int v44[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v45; // [rsp+68h] [rbp-98h] BYREF
  __int64 v46; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+78h] [rbp-88h] BYREF
  void *Block; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v49; // [rsp+88h] [rbp-78h] BYREF
  void *lpMem; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v51[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v52; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v53; // [rsp+A8h] [rbp-58h] BYREF
  __int64 AttributeName; // [rsp+B0h] [rbp-50h] BYREF
  LPCWCH lpString1[2]; // [rsp+B8h] [rbp-48h] BYREF
  int v56; // [rsp+C8h] [rbp-38h] BYREF
  char v57; // [rsp+CCh] [rbp-34h]
  _BYTE v58[16]; // [rsp+D0h] [rbp-30h] BYREF
  GUID ActivityId; // [rsp+E0h] [rbp-20h] BYREF
  UUID Uuid; // [rsp+F0h] [rbp-10h] BYREF

  v7 = a1;
  v46 = a1;
  v45 = 0;
  Uuid = 0;
  Block = 0;
  v49 = 0;
  lpMem = 0;
  v52 = 0;
  *(_OWORD *)lpString1 = 0;
  *(_QWORD *)v51 = 0;
  v53 = 0;
  v8 = 0;
  Logger::TraceVerbose((wchar_t *)L"%s started", L"DeviceUpdateController::UpdateDeviceAttribute");
  v56 = 0;
  v57 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v56);
  v9 = &cchOriginalDestLength;
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
  {
    v42 = *(_DWORD *)a3;
    *(_QWORD *)v44 = *(_QWORD *)(a3 + 32);
    AttributeName = GetAttributeName(a2);
    v47 = 16779264;
    if ( !v57 || (IsZero = _tlgGuidIsZero(&ActivityId), p_ActivityId = &ActivityId, IsZero) )
      LODWORD(p_ActivityId) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18013D150,
      (unsigned int)byte_180129D53,
      (unsigned int)v58,
      (_DWORD)p_ActivityId,
      (__int64)&v47,
      (__int64)&AttributeName,
      (__int64)v44,
      (__int64)&v42);
  }
  else if ( !a3 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DeviceUpdateController::UpdateDeviceAttribute",
      L"accountInfo");
    v13 = L"accountInfo";
    goto LABEL_11;
  }
  if ( a5 )
  {
    UpdateEndpoint = CreateGuid(&Uuid);
    v12 = UpdateEndpoint;
    if ( UpdateEndpoint < 0 )
    {
      v15 = L"CreateGuid";
LABEL_14:
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"DeviceUpdateController::UpdateDeviceAttribute",
        v15,
        (unsigned int)UpdateEndpoint);
      goto LABEL_53;
    }
    UpdateEndpoint = DeviceUpdateController::GetUpdateEndpoint(a2, a3, &v45);
    v12 = UpdateEndpoint;
    if ( UpdateEndpoint < 0 )
    {
      v15 = L"DeviceUpdateController::GetUpdateEndpoint";
      goto LABEL_14;
    }
    UpdateEndpoint = ParseUrlAndAppendVersion(v45, L"2.0", v44, (unsigned __int16 **)&Block, &v49);
    v12 = UpdateEndpoint;
    if ( UpdateEndpoint < 0 )
    {
      v15 = L"ParseUrlAndAppendVersion";
      goto LABEL_14;
    }
    UpdateEndpoint = DeviceUpdateRequestSerializer::CreateHeader(
                       &Uuid,
                       v16,
                       (unsigned __int16 **)&lpMem,
                       (unsigned __int64 *)v51);
    v12 = UpdateEndpoint;
    if ( UpdateEndpoint < 0 )
    {
      v15 = L"DeviceUpdateRequestSerializer::CreateHeader";
      goto LABEL_14;
    }
    v17 = 0;
    switch ( a2 )
    {
      case 1u:
        UpdateEndpoint = DeviceInfo::GetDnsHostName((DeviceInfo *)(v7 + 8), lpString1);
        v12 = UpdateEndpoint;
        if ( UpdateEndpoint < 0 )
        {
          v15 = L"MdmDeviceInfo::GetDeviceDisplayName";
          goto LABEL_14;
        }
        break;
      case 2u:
        UpdateEndpoint = DeviceInfo::GetOsVersion((DeviceInfo *)(v7 + 8), lpString1);
        v12 = UpdateEndpoint;
        if ( UpdateEndpoint < 0 )
        {
          v15 = L"MdmDeviceInfo::GetDeviceOsVersion";
          goto LABEL_14;
        }
        break;
      case 3u:
        UpdateEndpoint = DeviceInfo::GetFutureHostName((DeviceInfo *)(v7 + 8), lpString1);
        v12 = UpdateEndpoint;
        if ( UpdateEndpoint < 0 )
        {
          v15 = L"DeviceInfo::GetFutureHostName";
          goto LABEL_14;
        }
        UpdateEndpoint = DeviceInfo::GetFutureFullyQualifiedName((DeviceInfo *)(v7 + 8), &lpString1[1]);
        v12 = UpdateEndpoint;
        if ( UpdateEndpoint < 0 )
        {
          v15 = L"DeviceInfo::GetFutureFullyQualifiedName";
          goto LABEL_14;
        }
        if ( lpString1[0] == lpString1[1] )
        {
          v18 = 1;
        }
        else
        {
          v42 = 0;
          v19 = &cchOriginalDestLength;
          if ( lpString1[1] )
            v19 = lpString1[1];
          v20 = &cchOriginalDestLength;
          if ( lpString1[0] )
            v20 = lpString1[0];
          UpdateEndpoint = StringCompare(v20, v19, 0x30001u, &v42);
          v12 = UpdateEndpoint;
          if ( UpdateEndpoint < 0 )
          {
            v15 = L"StringCompareIgnoreCase";
            goto LABEL_14;
          }
          v18 = v42;
        }
        v17 = 2LL - (v18 != 0);
        v7 = v46;
        break;
      case 4u:
        v12 = -2147467263;
        goto LABEL_53;
      default:
LABEL_45:
        v38 = &v53;
        UpdateEndpoint = DeviceUpdateRequestSerializer::CreateUpdateRequestBody(a2, lpString1, v17, &v52);
        v12 = UpdateEndpoint;
        if ( UpdateEndpoint >= 0 )
        {
          *((_QWORD *)a5 + 2) = v7;
          v21 = (WinHttpRequest *)operator new(0xD0u, (const struct std::nothrow_t *)&std::nothrow);
          v8 = v21;
          v47 = (__int64)v21;
          if ( !v21 )
          {
            v8 = 0;
            v12 = -2147024882;
            Logger::TraceCritical(
              L"%s: Out of memory. Allocation failed.",
              L"DeviceUpdateController::UpdateDeviceAttribute");
            goto LABEL_53;
          }
          WinHttpRequest::WinHttpRequest(v21, 120000);
          *(_QWORD *)v8 = &DeviceUpdateHttpRequest::`vftable';
          *((_QWORD *)v8 + 22) = 0;
          *((_QWORD *)v8 + 23) = 0;
          *((_QWORD *)v8 + 24) = 0;
          *((_QWORD *)v8 + 25) = 0;
          UpdateEndpoint = DeviceUpdateHttpRequest::Initialize(
                             v8,
                             (const unsigned __int16 *)Block,
                             v49,
                             v22,
                             (void (*)(struct DeviceUpdateHttpRequest *, struct STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *, int))&v53,
                             a5);
          v12 = UpdateEndpoint;
          if ( UpdateEndpoint >= 0 )
          {
            UpdateEndpoint = DeviceUpdateHttpRequest::Send(
                               (DWORD_PTR)v8,
                               (const unsigned __int16 *)lpMem,
                               v51[0],
                               v52,
                               v53,
                               *(const struct _CERT_CONTEXT **)(a3 + 8));
            v12 = UpdateEndpoint;
            if ( UpdateEndpoint >= 0 )
              goto LABEL_53;
            v15 = L"DeviceUpdateHttpRequest::Send";
          }
          else
          {
            v15 = L"DeviceUpdateHttpRequest::Initialize";
          }
        }
        else
        {
          v15 = L"DeviceUpdateRequestSerializer::CreatePostRequestBody";
        }
        goto LABEL_14;
    }
    v17 = 1;
    goto LABEL_45;
  }
  v12 = -2147024809;
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"DeviceUpdateController::UpdateDeviceAttribute", L"pContext");
  v13 = L"pContext";
LABEL_11:
  Logger::WriteNullOrEmptyParameterFailureEvent(L"DeviceUpdateController::UpdateDeviceAttribute", v13);
LABEL_53:
  operator delete(Block);
  operator delete(v49);
  v23 = lpMem;
  if ( lpMem )
  {
    v24 = 2LL * *(_QWORD *)v51;
    if ( 2LL * *(_QWORD *)v51 )
    {
      v25 = lpMem;
      do
      {
        *v25++ = 0;
        --v24;
      }
      while ( v24 );
    }
  }
  SafeFree(v23);
  v26 = v52;
  if ( v52 )
  {
    v27 = 2 * v53;
    if ( 2 * v53 )
    {
      v28 = v52;
      do
      {
        *(_BYTE *)v28 = 0;
        v28 = (unsigned __int16 *)((char *)v28 + 1);
        --v27;
      }
      while ( v27 );
    }
  }
  SafeFree(v26);
  if ( v12 >= 0 )
  {
    if ( a3 )
    {
LABEL_68:
      v9 = *(const WCHAR **)(a3 + 32);
      v31 = *(const WCHAR **)(a3 + 16);
      v32 = *(_DWORD *)a3;
      goto LABEL_70;
    }
  }
  else
  {
    if ( v8 )
      (**(void (__fastcall ***)(WinHttpRequest *, __int64))v8)(v8, 1);
    if ( a3 )
    {
      if ( (int)DeviceUpdateController::SaveAttribute(v46, a2, (unsigned int *)a3, v12, 0) < 0 )
      {
        v29 = GetAttributeName(a2);
        Logger::TraceError(
          L"%s: DeviceUpdateController::SaveAttribute failed with error code: 0x%08x. Attribute: \"%s\", Device ID: \"%s\".",
          L"DeviceUpdateController::UpdateDeviceAttribute",
          v30,
          v29,
          *(_QWORD *)(a3 + 16));
      }
      goto LABEL_68;
    }
  }
  v31 = &cchOriginalDestLength;
  v32 = 0;
LABEL_70:
  StringUuid = 0;
  v33 = UuidToStringW(&Uuid, &StringUuid);
  if ( v33 )
    Logger::TraceWarning(
      (wchar_t *)L"%s: Cannot convert the request ID to a GUID string. Error code: 0x%08x.",
      L"DeviceUpdateController::UpdateDeviceAttribute",
      v33);
  v34 = GetAttributeName(a2);
  v35 = v34;
  if ( v12 >= 0 )
  {
    Logger::WriteBeginDeviceUpdateAttributeSuccessEvent(v34, v9, v31, v32, StringUuid);
    LODWORD(v39) = v32;
    Logger::TraceVerbose(
      (wchar_t *)L"%s: Device update begin succeeded. Attribute: \"%s\", Tenant ID: \"%s\", Device ID: \"%s\", Join type: "
                  "%d, Request ID: %s.",
      L"DeviceUpdateController::UpdateDeviceAttribute",
      v35,
      v9,
      v31,
      v39,
      StringUuid);
  }
  else
  {
    LODWORD(v38) = v32;
    Logger::WriteBeginDeviceUpdateAttributeFailureEvent((unsigned int)v12, v34, v9, v31, v38, StringUuid);
    LODWORD(v41) = v12;
    LODWORD(v40) = v32;
    Logger::TraceError(
      L"%s: Device update begin failed. Attribute: \"%s\", Tenant ID: \"%s\", Device ID: \"%s\", Join type: %d, Request ID"
       ": %s, Error code: 0x%08x.",
      L"DeviceUpdateController::UpdateDeviceAttribute",
      v35,
      v9,
      v31,
      v40,
      StringUuid,
      v41);
  }
  if ( v57 )
    EventActivityIdControl(4u, &ActivityId);
  v56 = 2;
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
  {
    v47 = (__int64)StringUuid;
    v42 = v32;
    AttributeName = (__int64)v9;
    v46 = v35;
    v44[0] = v12;
    v45 = (unsigned __int16 *)16779264;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_18013D150,
      (unsigned int)&byte_180129CDF,
      (unsigned int)v58,
      v36,
      (__int64)&v45,
      (__int64)v44,
      (__int64)&v46,
      (__int64)&AttributeName,
      (__int64)&v42,
      (__int64)&v47);
  }
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  Logger::TraceVerbose(
    (wchar_t *)L"%s - hr: 0x%08x",
    L"DeviceUpdateController::UpdateDeviceAttribute",
    (unsigned int)v12);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v56);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180065f28  mov     [rsp-8+arg_18], rbx
0x180065f2d  push    rbp
0x180065f2e  push    rsi
0x180065f2f  push    rdi
0x180065f30  push    r12
0x180065f32  push    r13
0x180065f34  push    r14
0x180065f36  push    r15
0x180065f38  lea     rbp, [rsp-10h]
0x180065f3d  sub     rsp, 110h
0x180065f44  mov     rax, cs:__security_cookie
0x180065f4b  xor     rax, rsp
0x180065f4e  mov     [rbp+40h+var_40], rax
0x180065f52  mov     rsi, r8
0x180065f55  mov     r12d, edx
0x180065f58  mov     r14, rcx
0x180065f5b  mov     [rsp+140h+var_D0], rcx
0x180065f60  mov     r13, [rbp+40h+arg_20]
0x180065f64  xor     ebx, ebx
0x180065f66  mov     [rsp+140h+var_D8], rbx
0x180065f6b  xorps   xmm0, xmm0
0x180065f6e  movups  xmmword ptr [rbp+40h+Uuid.Data1], xmm0
0x180065f72  mov     [rbp+40h+Block], rbx
0x180065f76  mov     [rbp+40h+var_B8], rbx
0x180065f7a  mov     [rbp+40h+lpMem], rbx
0x180065f7e  mov     [rbp+40h+var_A0], rbx
0x180065f82  movups  xmmword ptr [rbp+40h+lpString1], xmm0
0x180065f86  mov     qword ptr [rbp+40h+var_A8], rbx
0x180065f8a  mov     [rbp+40h+var_98], rbx
0x180065f8e  mov     edi, ebx
0x180065f90  lea     rdx, aDeviceupdateco_3; "DeviceUpdateController::UpdateDeviceAtt"...
0x180065f97  lea     rcx, aSStarted; "%s started"
0x180065f9e  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180065fa3  mov     [rbp+40h+var_78], ebx
0x180065fa6  mov     [rbp+40h+var_74], bl
0x180065fa9  lea     rcx, [rbp+40h+var_78]
0x180065fad  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x180065fb2  mov     eax, cs:dword_18013D150
0x180065fb8  lea     r15, cchOriginalDestLength
0x180065fbf  cmp     eax, 5
0x180065fc2  jbe     loc_18006608E
0x180065fc8  mov     rdx, 400000000000h
0x180065fd2  lea     rcx, dword_18013D150
0x180065fd9  call    _tlgKeywordOn
0x180065fde  test    al, al
0x180065fe0  jz      loc_18006608E
0x180065fe6  mov     eax, [rsi]
0x180065fe8  mov     [rsp+140h+var_F0], eax
0x180065fec  mov     rax, [rsi+20h]
0x180065ff0  mov     qword ptr [rsp+140h+var_E0], rax
0x180065ff5  mov     ecx, r12d
0x180065ff8  call    GetAttributeName
0x180065ffd  mov     [rbp+40h+var_90], rax
0x180066001  mov     [rsp+140h+var_C8], 1000800h
0x18006600a  cmp     [rbp+40h+var_74], bl
0x18006600d  jz      short loc_180066020
0x18006600f  lea     rcx, [rbp+40h+ActivityId]; struct _GUID *
0x180066013  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180066018  test    al, al
0x18006601a  lea     r9, [rbp+40h+ActivityId]
0x18006601e  jz      short loc_180066023
0x180066020  mov     r9, rbx
0x180066023  lea     rax, [rsp+140h+var_F0]
0x180066028  mov     [rsp+140h+var_108], rax
0x18006602d  lea     rax, [rsp+140h+var_E0]
0x180066032  mov     [rsp+140h+var_110], rax
0x180066037  lea     rax, [rbp+40h+var_90]
0x18006603b  mov     [rsp+140h+var_118], rax
0x180066040  lea     rax, [rsp+140h+var_C8]
0x180066045  mov     [rsp+140h+var_120], rax
0x18006604a  lea     r8, [rbp+40h+var_70]
0x18006604e  lea     rdx, byte_180129D53
0x180066055  lea     rcx, dword_18013D150
0x18006605c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180066061  test    r13, r13
0x180066064  jnz     short loc_1800660CA
0x180066066  mov     ebx, 80070057h
0x18006606b  lea     r8, aPcontext; "pContext"
0x180066072  lea     rdx, aDeviceupdateco_3; "DeviceUpdateController::UpdateDeviceAtt"...
0x180066079  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180066080  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180066085  lea     rdx, aPcontext; "pContext"
0x18006608c  jmp     short loc_1800660B9
0x18006608e  test    rsi, rsi
0x180066091  jnz     short loc_180066061
0x180066093  mov     ebx, 80070057h
0x180066098  lea     r8, aAccountinfo; "accountInfo"
0x18006609f  lea     rdx, aDeviceupdateco_3; "DeviceUpdateController::UpdateDeviceAtt"...
0x1800660a6  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800660ad  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800660b2  lea     rdx, aAccountinfo; "accountInfo"
0x1800660b9  lea     rcx, aDeviceupdateco_3; "DeviceUpdateController::UpdateDeviceAtt"...
0x1800660c0  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800660c5  jmp     loc_180066399
0x1800660ca  lea     rcx, [rbp+40h+Uuid]; struct _GUID *
0x1800660ce  call    ?CreateGuid@@YAJPEAU_GUID@@@Z; CreateGuid(_GUID *)
0x1800660d3  mov     ebx, eax
0x1800660d5  test    eax, eax
0x1800660d7  jns     short loc_1800660FB
0x1800660d9  lea     r8, aCreateguid; "CreateGuid"
0x1800660e0  mov     r9d, eax
0x1800660e3  lea     rdx, aDeviceupdateco_3; "DeviceUpdateController::UpdateDeviceAtt"...
0x1800660ea  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800660f1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800660f6  jmp     loc_180066399
0x1800660fb  lea     r8, [rsp+140h+var_D8]
0x180066100  mov     rdx, rsi
0x180066103  mov     ecx, r12d
0x180066106  call    ?GetUpdateEndpoint@DeviceUpdateController@@CAJW4_DSREG_DEVICE_ATTRIBUTES@@PEAU_DSREG_ACCOUNT_INFO_2@@PEAPEAG@Z; DeviceUpdateController::GetUpdateEndpoint(_DSREG_DEVICE_ATTRIBUTES,_DSREG_ACCOUNT_INFO_2 *,ushort * *)
0x18006610b  mov     ebx, eax
0x18006610d  test    eax, eax
0x18006610f  jns     short loc_18006611A
0x180066111  lea     r8, aDeviceupdateco; "DeviceUpdateController::GetUpdateEndpoi"...
0x180066118  jmp     short loc_1800660E0
0x18006611a  lea     rax, [rbp+40h+var_B8]
0x18006611e  mov     [rsp+140h+var_120], rax; unsigned __int16 **
0x180066123  lea     r9, [rbp+40h+Block]; unsigned __int16 **
0x180066127  lea     r8, [rsp+140h+var_E0]; int *
0x18006612c  lea     rdx, a20; "2.0"
0x180066133  mov     rcx, [rsp+140h+var_D8]; unsigned __int16 *
0x180066138  call    ?ParseUrlAndAppendVersion@@YAJPEBG0PEAHPEAPEAG2@Z; ParseUrlAndAppendVersion(ushort const *,ushort const *,int *,ushort * *,ushort * *)
0x18006613d  mov     ebx, eax
0x18006613f  test    eax, eax
0x180066141  jns     short loc_18006614C
0x180066143  lea     r8, aParseurlandapp; "ParseUrlAndAppendVersion"
0x18006614a  jmp     short loc_1800660E0
0x18006614c  lea     r9, [rbp+40h+var_A8]; unsigned __int64 *
0x180066150  lea     r8, [rbp+40h+lpMem]; unsigned __int16 **
0x180066154  lea     rcx, [rbp+40h+Uuid]; struct _GUID *
0x180066158  call    ?CreateHeader@DeviceUpdateRequestSerializer@@SAJPEBU_GUID@@PEBGPEAPEAGPEA_K@Z; DeviceUpdateRequestSerializer::CreateHeader(_GUID const *,ushort const *,ushort * *,unsigned __int64 *)
0x18006615d  mov     ebx, eax
0x18006615f  test    eax, eax
0x180066161  jns     short loc_18006616F
0x180066163  lea     r8, aDeviceupdatere_3; "DeviceUpdateRequestSerializer::CreateHe"...
0x18006616a  jmp     loc_1800660E0
0x18006616f  xor     r8d, r8d
0x180066172  mov     ecx, r12d
0x180066175  sub     ecx, 1
0x180066178  jz      loc_180066262
0x18006617e  sub     ecx, 1
0x180066181  jz      loc_180066243
0x180066187  sub     ecx, 1
0x18006618a  jz      short loc_18006619F
0x18006618c  cmp     ecx, 1
0x18006618f  jnz     loc_180066287
0x180066195  mov     ebx, 80004001h
0x18006619a  jmp     loc_180066399
0x18006619f  lea     rdx, [rbp+40h+lpString1]; unsigned __int16 **
0x1800661a3  lea     rcx, [r14+8]; this
0x1800661a7  call    ?GetFutureHostName@DeviceInfo@@QEAAJPEAPEBG@Z; DeviceInfo::GetFutureHostName(ushort const * *)
0x1800661ac  mov     ebx, eax
0x1800661ae  test    eax, eax
0x1800661b0  jns     short loc_1800661BE
0x1800661b2  lea     r8, aDeviceinfoGetf_1; "DeviceInfo::GetFutureHostName"
0x1800661b9  jmp     loc_1800660E0
0x1800661be  lea     rdx, [rbp+40h+lpString1+8]; unsigned __int16 **
0x1800661c2  lea     rcx, [r14+8]; this
0x1800661c6  call    ?GetFutureFullyQualifiedName@DeviceInfo@@QEAAJPEAPEBG@Z; DeviceInfo::GetFutureFullyQualifiedName(ushort const * *)
0x1800661cb  mov     ebx, eax
0x1800661cd  test    eax, eax
0x1800661cf  jns     short loc_1800661DD
0x1800661d1  lea     r8, aDeviceinfoGetf_0; "DeviceInfo::GetFutureFullyQualifiedName"
0x1800661d8  jmp     loc_1800660E0
0x1800661dd  mov     rax, [rbp+40h+lpString1]
0x1800661e1  mov     rcx, [rbp+40h+lpString1+8]
0x1800661e5  cmp     rax, rcx
0x1800661e8  jnz     short loc_1800661F1
0x1800661ea  mov     eax, 1
0x1800661ef  jmp     short loc_180066233
0x1800661f1  mov     [rsp+140h+var_F0], 0
0x1800661f9  mov     rdx, r15
0x1800661fc  test    rcx, rcx
0x1800661ff  cmovnz  rdx, rcx; unsigned __int16 *
0x180066203  mov     rcx, r15
0x180066206  test    rax, rax
0x180066209  cmovnz  rcx, rax; lpString1
0x18006620d  lea     r9, [rsp+140h+var_F0]; int *
0x180066212  mov     r8d, 30001h; unsigned int
0x180066218  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x18006621d  mov     ebx, eax
0x18006621f  test    eax, eax
0x180066221  jns     short loc_18006622F
0x180066223  lea     r8, aStringcomparei; "StringCompareIgnoreCase"
0x18006622a  jmp     loc_1800660E0
0x18006622f  mov     eax, [rsp+140h+var_F0]
0x180066233  neg     eax
0x180066235  sbb     r8, r8
0x180066238  add     r8, 2
0x18006623c  mov     r14, [rsp+140h+var_D0]
0x180066241  jmp     short loc_180066287
0x180066243  lea     rcx, [r14+8]; this
0x180066247  lea     rdx, [rbp+40h+lpString1]; unsigned __int16 **
0x18006624b  call    ?GetOsVersion@DeviceInfo@@QEAAJPEAPEBG@Z; DeviceInfo::GetOsVersion(ushort const * *)
0x180066250  mov     ebx, eax
0x180066252  test    eax, eax
0x180066254  jns     short loc_180066281
0x180066256  lea     r8, aMdmdeviceinfoG; "MdmDeviceInfo::GetDeviceOsVersion"
0x18006625d  jmp     loc_1800660E0
0x180066262  lea     rcx, [r14+8]; this
0x180066266  lea     rdx, [rbp+40h+lpString1]; unsigned __int16 **
0x18006626a  call    ?GetDnsHostName@DeviceInfo@@QEAAJPEAPEBG@Z; DeviceInfo::GetDnsHostName(ushort const * *)
0x18006626f  mov     ebx, eax
0x180066271  test    eax, eax
0x180066273  jns     short loc_180066281
0x180066275  lea     r8, aMdmdeviceinfoG_0; "MdmDeviceInfo::GetDeviceDisplayName"
0x18006627c  jmp     loc_1800660E0
0x180066281  mov     r8d, 1
0x180066287  lea     rax, [rbp+40h+var_98]
0x18006628b  mov     [rsp+140h+var_120], rax; void (*)(struct DeviceUpdateHttpRequest *, struct STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *, int)
0x180066290  lea     r9, [rbp+40h+var_A0]
0x180066294  lea     rdx, [rbp+40h+lpString1]
0x180066298  mov     ecx, r12d
0x18006629b  call    ?CreateUpdateRequestBody@DeviceUpdateRequestSerializer@@SAJW4_DSREG_DEVICE_ATTRIBUTES@@PEAPEBG_KPEAPEAGPEA_K@Z; DeviceUpdateRequestSerializer::CreateUpdateRequestBody(_DSREG_DEVICE_ATTRIBUTES,ushort const * *,unsigned __int64,ushort * *,unsigned __int64 *)
0x1800662a0  mov     ebx, eax
0x1800662a2  test    eax, eax
0x1800662a4  jns     short loc_1800662B2
0x1800662a6  lea     r8, aDeviceupdatere_2; "DeviceUpdateRequestSerializer::CreatePo"...
0x1800662ad  jmp     loc_1800660E0
0x1800662b2  mov     [r13+10h], r14
0x1800662b6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800662bd  mov     ecx, 0D0h; unsigned __int64
0x1800662c2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800662c7  mov     rdi, rax
0x1800662ca  mov     [rsp+140h+var_C8], rax
0x1800662cf  test    rax, rax
0x1800662d2  jz      loc_18006637F
0x1800662d8  mov     edx, 1D4C0h; int
0x1800662dd  mov     rcx, rax; this
0x1800662e0  call    ??0WinHttpRequest@@QEAA@H@Z; WinHttpRequest::WinHttpRequest(int)
0x1800662e5  lea     rcx, ??_7DeviceUpdateHttpRequest@@6B@; const DeviceUpdateHttpRequest::`vftable'
0x1800662ec  mov     [rdi], rcx
0x1800662ef  mov     qword ptr [rdi+0B0h], 0
0x1800662fa  mov     qword ptr [rdi+0B8h], 0
0x180066305  mov     qword ptr [rdi+0C0h], 0
0x180066310  mov     qword ptr [rdi+0C8h], 0
0x18006631b  test    rdi, rdi
0x18006631e  jz      short loc_180066381
0x180066320  mov     [rsp+140h+var_118], r13; struct STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *
0x180066325  mov     r8, [rbp+40h+var_B8]; unsigned __int16 *
0x180066329  mov     rdx, [rbp+40h+Block]; unsigned __int16 *
0x18006632d  mov     rcx, rdi; this
0x180066330  call    ?Initialize@DeviceUpdateHttpRequest@@QEAAJPEBG00P6AXPEAV1@PEAUSTRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT@@J@Z2@Z; DeviceUpdateHttpRequest::Initialize(ushort const *,ushort const *,ushort const *,void (*)(DeviceUpdateHttpRequest *,STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *,long),STRUCT_DEVICE_UPDATE_RESPONSE_CALLBACK_CONTEXT *)
0x180066335  mov     ebx, eax
0x180066337  test    eax, eax
0x180066339  jns     short loc_180066347
0x18006633b  lea     r8, aDeviceupdateht_2; "DeviceUpdateHttpRequest::Initialize"
0x180066342  jmp     loc_1800660E0
0x180066347  mov     rax, [rsi+8]
0x18006634b  mov     [rsp+140h+var_118], rax; struct _CERT_CONTEXT *
0x180066350  mov     rax, [rbp+40h+var_98]
0x180066354  mov     [rsp+140h+var_120], rax; unsigned __int64
0x180066359  mov     r9, [rbp+40h+var_A0]; unsigned __int16 *
0x18006635d  mov     r8, qword ptr [rbp+40h+var_A8]; unsigned int
0x180066361  mov     rdx, [rbp+40h+lpMem]; unsigned __int16 *
0x180066365  mov     rcx, rdi; dwContext
0x180066368  call    ?Send@DeviceUpdateHttpRequest@@QEAAJPEBG_K01PEBU_CERT_CONTEXT@@@Z; DeviceUpdateHttpRequest::Send(ushort const *,unsigned __int64,ushort const *,unsigned __int64,_CERT_CONTEXT const *)
0x18006636d  mov     ebx, eax
0x18006636f  test    eax, eax
0x180066371  jns     short loc_180066399
0x180066373  lea     r8, aDeviceupdateht_0; "DeviceUpdateHttpRequest::Send"
0x18006637a  jmp     loc_1800660E0
0x18006637f  xor     edi, edi
0x180066381  mov     ebx, 8007000Eh
0x180066386  lea     rdx, aDeviceupdateco_3; "DeviceUpdateController::UpdateDeviceAtt"...
0x18006638d  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180066394  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180066399  mov     rcx, [rbp+40h+Block]; Block
0x18006639d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800663a2  mov     rcx, [rbp+40h+var_B8]; Block
0x1800663a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800663ab  mov     rcx, [rbp+40h+lpMem]; lpMem
0x1800663af  test    rcx, rcx
0x1800663b2  jz      short loc_1800663D0
0x1800663b4  mov     rax, qword ptr [rbp+40h+var_A8]
0x1800663b8  lea     rdx, [rax+rax]
0x1800663bc  test    rdx, rdx
0x1800663bf  jz      short loc_1800663D0
0x1800663c1  mov     rax, rcx
0x1800663c4  mov     byte ptr [rax], 0
0x1800663c7  inc     rax
0x1800663ca  sub     rdx, 1
0x1800663ce  jnz     short loc_1800663C4
0x1800663d0  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800663d5  mov     rcx, [rbp+40h+var_A0]; lpMem
0x1800663d9  test    rcx, rcx
0x1800663dc  jz      short loc_1800663FA
0x1800663de  mov     rax, [rbp+40h+var_98]
0x1800663e2  lea     rdx, [rax+rax]
0x1800663e6  test    rdx, rdx
0x1800663e9  jz      short loc_1800663FA
0x1800663eb  mov     rax, rcx
0x1800663ee  mov     byte ptr [rax], 0
0x1800663f1  inc     rax
0x1800663f4  sub     rdx, 1
0x1800663f8  jnz     short loc_1800663EE
0x1800663fa  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800663ff  test    ebx, ebx
0x180066401  jns     short loc_18006646C
0x180066403  test    rdi, rdi
0x180066406  jz      short loc_18006641B
  ... truncated ...
```
