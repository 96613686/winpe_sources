# CTSRpcClientTrackerMgr::TrackCaller(long,unsigned __int64 *)

- ea: `0x180031400`
- end: `0x18003201f`
- name: `?TrackCaller@CTSRpcClientTrackerMgr@@UEAAJJPEA_K@Z`
- size: `3103`
- prototype: `__int64 __fastcall(CTSRpcClientTrackerMgr *this, DWORD, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001b80`
- `0x1800051b0`
- `0x1800074c0`
- `0x180008b20`
- `0x180008cb0`
- `0x18000fdf0`
- `0x180010910`
- `0x180010eb0`
- `0x18001b090`
- `0x18001eab0`
- `0x1800225a4`
- `0x180031400`
- `0x18004b460`
- `0x18004b86c`
- `0x18009404c`
- `0x180097010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180031ba4`
- `ntdll!RtlReleaseResource` at `0x180031c57`
- `ntdll!RtlReleaseResource` at `0x180031c72`
- `ntdll!RtlReleaseResource` at `0x180031ba4`
- `ntdll!RtlReleaseResource` at `0x180031c57`
- `ntdll!RtlReleaseResource` at `0x180031c72`
- `ntdll!RtlAcquireResourceExclusive` at `0x180031ada`
- `ntdll!RtlAcquireResourceExclusive` at `0x180031ada`
- `ntdll!RtlCaptureStackBackTrace` at `0x1800314da`
- `ntdll!RtlCaptureStackBackTrace` at `0x1800314da`
- `ntdll!RtlInsertElementGenericTable` at `0x180031b19`
- `ntdll!RtlInsertElementGenericTable` at `0x180031b19`
- `ntdll!RtlLengthSid` at `0x18003187f`
- `ntdll!RtlLengthSid` at `0x18003187f`
- `ntdll!EtwEventWriteTransfer` at `0x18003168a`
- `ntdll!EtwEventWriteTransfer` at `0x180031dfd`
- `ntdll!EtwEventWriteTransfer` at `0x18003168a`
- `ntdll!EtwEventWriteTransfer` at `0x180031dfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800316d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800316d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800316c1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800316c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800316a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800316a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031710`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031fbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031710`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031fbf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800319d0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800319d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031f7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031f7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031889`
- `RPCRT4!RpcImpersonateClient` at `0x180031542`
- `RPCRT4!RpcImpersonateClient` at `0x180031542`
- `RPCRT4!RpcRevertToSelf` at `0x180031fda`
- `RPCRT4!RpcRevertToSelf` at `0x180031fda`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180031e99`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180031e99`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180031a06`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180031a06`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800319bd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800319bd`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003199c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18003199c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180031fe2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180031fe2`

## string_xrefs

- `0x18003182e`: `No token`
- `0x1800316f4`: `OpenThreadToken failed: 0x%x in %s`
- `0x180031569`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x1800316ea`: `CRpcUtils::GetClientToken`
- `0x1800315bf`: `ImpersonateRpcClient`
- `0x180031749`: `GetClientToken`
- `0x1800318cb`: `UserName.GetUserSid`
- `0x1800319ae`: `IsValidSid(pSid) failed: 0x%x in %s`
- `0x180031a34`: `CopySid failed: 0x%x in %s`
- `0x18003185a`: `CUserName::GetUserSid`
- `0x18003155f`: `CImpersonate::ImpersonateRpcClient`

## pseudocode

```c
__int64 __fastcall CTSRpcClientTrackerMgr::TrackCaller(CTSRpcClientTrackerMgr *this, DWORD a2, unsigned __int64 *a3)
{
  char v3; // r13
  char v4; // r14
  CImpersonate *v5; // rcx
  char v6; // al
  void *v7; // rdi
  void *v8; // rbx
  volatile signed __int32 *v9; // r15
  RPC_STATUS v10; // eax
  signed int v11; // esi
  HANDLE CurrentThread; // rax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  signed int LastError; // eax
  void *v17; // rax
  signed int v18; // eax
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  int v24; // eax
  SIZE_T v25; // rsi
  void *v26; // rax
  void *v27; // r13
  void *v28; // rax
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  ULONG v32; // r14d
  const char *v33; // rdx
  DWORD LengthSid; // eax
  HLOCAL v35; // rax
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  signed int v39; // eax
  const char *v40; // r14
  char *v41; // r15
  struct _RTL_GENERIC_TABLE *v42; // r14
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  int v46; // ecx
  int v47; // r8d
  int v48; // r9d
  int v49; // eax
  int v50; // ecx
  int v51; // r8d
  int v52; // r9d
  __int64 v53; // rax
  RPC_STATUS v54; // eax
  int v55; // r8d
  int v56; // r9d
  signed int v57; // ecx
  const char *v58; // rax
  ULONG BackTraceHash; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v61; // [rsp+44h] [rbp-BCh]
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pSessionId[2]; // [rsp+50h] [rbp-B0h] BYREF
  char *v64; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 NewElement[8]; // [rsp+60h] [rbp-A0h] BYREF
  const char *v66; // [rsp+68h] [rbp-98h] BYREF
  __int64 v67; // [rsp+70h] [rbp-90h] BYREF
  __int64 v68; // [rsp+78h] [rbp-88h]
  const char *v69; // [rsp+80h] [rbp-80h] BYREF
  int v70; // [rsp+88h] [rbp-78h]
  void *v71; // [rsp+90h] [rbp-70h]
  void *v72; // [rsp+98h] [rbp-68h]
  void **v73; // [rsp+A0h] [rbp-60h] BYREF
  int v74; // [rsp+A8h] [rbp-58h]
  int v75; // [rsp+ACh] [rbp-54h]
  const char *v76; // [rsp+B0h] [rbp-50h]
  __int64 v77; // [rsp+B8h] [rbp-48h]
  signed __int32 v78[386]; // [rsp+C0h] [rbp-40h] BYREF
  struct _LIST_ENTRY v79; // [rsp+6C8h] [rbp+5C8h] BYREF
  void *v80; // [rsp+6D8h] [rbp+5D8h]
  int v81; // [rsp+6E0h] [rbp+5E0h]
  PSID *v82; // [rsp+6E8h] [rbp+5E8h]
  __int64 v83; // [rsp+AF8h] [rbp+9F8h]
  __int64 v84; // [rsp+B00h] [rbp+A00h]
  __int64 v85; // [rsp+B08h] [rbp+A08h]
  __int64 v86; // [rsp+B10h] [rbp+A10h]
  int v87; // [rsp+B18h] [rbp+A18h]
  int *v88; // [rsp+B30h] [rbp+A30h] BYREF
  int v89; // [rsp+B38h] [rbp+A38h]
  int v90; // [rsp+B3Ch] [rbp+A3Ch]
  char *v91; // [rsp+B40h] [rbp+A40h]
  int v92; // [rsp+B48h] [rbp+A48h]
  int v93; // [rsp+B4Ch] [rbp+A4Ch]
  const char *v94; // [rsp+B50h] [rbp+A50h]
  __int64 v95; // [rsp+B58h] [rbp+A58h]
  unsigned __int16 *v96; // [rsp+B60h] [rbp+A60h]
  __int64 v97; // [rsp+B68h] [rbp+A68h]
  ULONG *p_BackTraceHash; // [rsp+B70h] [rbp+A70h]
  __int64 v99; // [rsp+B78h] [rbp+A78h]
  const char **v100; // [rsp+B80h] [rbp+A80h]
  __int64 v101; // [rsp+B88h] [rbp+A88h]
  unsigned __int16 v102[264]; // [rsp+B90h] [rbp+A90h] BYREF

  v67 = (__int64)a3;
  pSessionId[0] = a2;
  v66 = (const char *)this;
  v3 = 0;
  v61 = 0;
  v4 = 0;
  v73 = &CTSPrivateObject<IUserName>::`vftable';
  v76 = "UserName";
  v74 = 0;
  v75 = 1;
  v79.Blink = &v79;
  v79.Flink = &v79;
  AddTrackingObject(&v79);
  v77 = 0;
  v78[0] = 0;
  BackTraceHash = 0;
  v6 = _InterlockedIncrement(v78);
  if ( g_bCaptureObjectStackTrace == 1 )
    RtlCaptureStackBackTrace(1u, 6u, (PVOID *)&v78[12 * (v6 & 0x1F) + 2], &BackTraceHash);
  v73 = &CUserName::`vftable';
  v80 = 0;
  v81 &= 0xFFFFFFE0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v87 &= 0xFFFFFFFC;
  v7 = 0;
  v71 = 0;
  v8 = 0;
  v72 = 0;
  v9 = 0;
  v64 = 0;
  CImpersonate::CheckCurrentContext(v5, 0);
  v10 = RpcImpersonateClient(0);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 < 0 )
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", v11, "CImpersonate::ImpersonateRpcClient");
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      BackTraceHash = v11;
      v100 = (const char **)"TrackCaller";
      v101 = 12;
      p_BackTraceHash = &BackTraceHash;
      v99 = 4;
      v96 = (unsigned __int16 *)"ImpersonateRpcClient";
      v97 = 21;
      v94 = "Warning HResult failed";
      v95 = 23;
      v67 = 0x14030B000000LL;
      v68 = 0;
      v88 = off_1800DA028;
      v89 = *(unsigned __int16 *)off_1800DA028;
      v90 = 2;
      v91 = &byte_1800C2D57;
      v92 = 51;
      v93 = 1;
      pSessionId[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(RegHandle, &v67, 0, 0, 6, &v88);
    }
    goto LABEL_82;
  }
  v4 = 1;
  v61 = 257;
  v3 = 1;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    v11 = 0;
LABEL_15:
    v17 = TokenHandle;
    goto LABEL_16;
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( v11 >= 0 )
    goto LABEL_15;
  _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", v11, "CRpcUtils::GetClientToken");
  v17 = TokenHandle;
  if ( !TokenHandle )
  {
LABEL_16:
    v7 = v17;
    v71 = v17;
    goto LABEL_17;
  }
  CloseHandle(TokenHandle);
LABEL_17:
  if ( v11 < 0 )
  {
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      v64 = "TrackCaller";
      BackTraceHash = v11;
      TokenHandle = "GetClientToken";
      *(_QWORD *)pSessionId = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v13,
        (unsigned int)byte_1800C2D8B,
        v14,
        v15,
        (__int64)pSessionId,
        (__int64)&TokenHandle,
        (__int64)&BackTraceHash,
        (__int64)&v64);
    }
    goto LABEL_82;
  }
  v18 = CUserName::Initialize((CUserName *)&v73, v7, 0);
  v11 = v18;
  if ( v18 < 0 )
  {
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      v64 = "TrackCaller";
      BackTraceHash = v18;
      TokenHandle = "UserName.Initialize";
      *(_QWORD *)pSessionId = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_1800DA020,
        (unsigned int)word_1800C2DCA,
        v19,
        v20,
        (__int64)pSessionId,
        (__int64)&TokenHandle,
        (__int64)&BackTraceHash,
        (__int64)&v64);
    }
    goto LABEL_82;
  }
  if ( (v81 & 2) == 0 )
  {
    if ( (v81 & 1) == 0 )
    {
      _DbgPrintMessage(8, "No token");
      v11 = -2147023888;
      goto LABEL_30;
    }
    v24 = CUserName::InitializeUserName((CUserName *)&v73, v80);
    v11 = v24;
    if ( v24 < 0 )
    {
      _DbgPrintMessage(8, "InitializeUserName failed: 0x%x in %s", v24, "CUserName::GetUserSid");
      goto LABEL_30;
    }
  }
  v25 = RtlLengthSid(*v82);
  v26 = CoTaskMemAlloc(v25);
  v27 = v26;
  if ( v26 )
  {
    memcpy_0(v26, *v82, v25);
    v28 = operator new(0x648u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v28;
    v69 = (const char *)v28;
    if ( v28 )
    {
      CTSObject<IUnknown>::CTSObject<IUnknown>(v28, "CTSRpcClient");
      *(_QWORD *)v8 = &CTSRpcClientTrackerMgr::CTSRpcClient::`vftable';
      *((_QWORD *)v8 + 199) = 0;
      *((_QWORD *)v8 + 200) = 0;
    }
    else
    {
      v8 = 0;
    }
    v72 = v8;
    if ( !v8 )
    {
      v11 = -2147024882;
      if ( (unsigned int)dword_1800DA020 > 3 )
      {
        v67 = (__int64)"TrackCaller";
        LODWORD(TokenHandle) = -2147024882;
        v69 = "New CTSRpcClient";
        v66 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v29,
          (unsigned int)qword_1800C2E48,
          v30,
          v31,
          (__int64)&v66,
          (__int64)&v69,
          (__int64)&TokenHandle,
          (__int64)&v67);
      }
      goto LABEL_81;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 8LL))(v8);
    if ( IsValidSid(v27) )
    {
      LengthSid = GetLengthSid(v27);
      *((_DWORD *)v8 + 400) = LengthSid;
      v35 = LocalAlloc(0x40u, LengthSid);
      *((_QWORD *)v8 + 199) = v35;
      if ( !v35 )
      {
        v32 = -2147024882;
        v11 = -2147024882;
        _DbgPrintMessage(
          8,
          "LocalAlloc failed: 0x%x in %s",
          2147942414LL,
          "CTSRpcClientTrackerMgr::CTSRpcClient::Initialize");
        goto LABEL_46;
      }
      v32 = 0;
      if ( CopySid(*((_DWORD *)v8 + 400), v35, v27) )
        goto LABEL_48;
      v39 = GetLastError();
      v11 = v39;
      if ( v39 > 0 )
        v11 = (unsigned __int16)v39 | 0x80070000;
      v32 = v11;
      if ( v11 >= 0 )
      {
LABEL_48:
        v11 = v32;
        v40 = v66;
        v41 = (char *)(v66 + 1592);
        v69 = v66 + 1592;
        v70 = 1;
        if ( *((_DWORD *)v66 + 422) )
          RtlAcquireResourceExclusive((PRTL_RESOURCE)(v66 + 1592), 1u);
        v42 = (struct _RTL_GENERIC_TABLE *)(v40 + 1696);
        if ( !(unsigned int)CListTree<CTSRpcClientTrackerMgr::CTSRpcClient>::Lookup(v42, v8, &v64) )
        {
          TokenHandle = v8;
          NewElement[0] = 0;
          if ( !RtlInsertElementGenericTable(v42, &TokenHandle, 8u, NewElement) )
          {
            v11 = -2147024882;
            if ( (unsigned int)dword_1800DA020 > 3 )
            {
              v66 = "TrackCaller";
              BackTraceHash = -2147024882;
              TokenHandle = "m_ptrRpcClientList.Add";
              *(_QWORD *)pSessionId = "Warning HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v43,
                (unsigned int)&word_1800C2EC6,
                v44,
                v45,
                (__int64)pSessionId,
                (__int64)&TokenHandle,
                (__int64)&BackTraceHash,
                (__int64)&v66);
            }
            if ( *((_DWORD *)v41 + 24) )
              RtlReleaseResource((PRTL_RESOURCE)v41);
            v9 = (volatile signed __int32 *)v64;
            goto LABEL_81;
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)TokenHandle + 8LL))(TokenHandle);
          v11 = 0;
          if ( !(unsigned int)CListTree<CTSRpcClientTrackerMgr::CTSRpcClient>::Lookup(v42, v8, &v64) )
          {
            v11 = -2147023537;
            if ( (unsigned int)dword_1800DA020 > 3 )
            {
              v66 = "TrackCaller";
              BackTraceHash = -2147023537;
              TokenHandle = "m_ptrRpcClientList.Lookup";
              *(_QWORD *)pSessionId = "Warning HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v46,
                (unsigned int)byte_1800C2F05,
                v47,
                v48,
                (__int64)pSessionId,
                (__int64)&TokenHandle,
                (__int64)&BackTraceHash,
                (__int64)&v66);
            }
            if ( *((_DWORD *)v41 + 24) )
              RtlReleaseResource((PRTL_RESOURCE)v41);
            v9 = (volatile signed __int32 *)v64;
            goto LABEL_81;
          }
        }
        if ( *((_DWORD *)v41 + 24) )
          RtlReleaseResource((PRTL_RESOURCE)v41);
        v9 = (volatile signed __int32 *)v64;
        v49 = _InterlockedIncrement((volatile signed __int32 *)v64 + 401);
        if ( v49 <= (int)pSessionId[0] )
        {
          if ( (unsigned int)dword_1800DA020 > 5 )
          {
            LODWORD(TokenHandle) = *((_DWORD *)v9 + 401);
            BackTraceHash = 0;
            v54 = I_RpcBindingInqLocalClientPID(0, &BackTraceHash);
            v57 = v54;
            if ( v54 > 0 )
              v57 = (unsigned __int16)v54 | 0x80070000;
            v58 = 0;
            if ( v57 >= 0 )
              v58 = (const char *)BackTraceHash;
            v69 = v58;
            v66 = "RpcClientTracker added successfully this RPC Caller";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              v57,
              (unsigned int)qword_1800C2FE0,
              v55,
              v56,
              (__int64)&v66,
              (__int64)&v69,
              (__int64)&TokenHandle);
          }
          *(_QWORD *)v67 = v9;
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        }
        else
        {
          BackTraceHash = 0;
          pSessionId[0] = 0;
          CRpcUtils::GetRpcCallerInfo(pSessionId, &BackTraceHash, 0x104u, v102);
          if ( (unsigned int)dword_1800DA020 > 1 )
          {
            v66 = (const char *)pSessionId[0];
            v64 = (char *)BackTraceHash;
            v100 = &v66;
            v101 = 8;
            p_BackTraceHash = (ULONG *)&v64;
            v99 = 8;
            v53 = -1;
            do
              ++v53;
            while ( v102[v53] );
            v96 = v102;
            v97 = (unsigned int)(2 * v53 + 2);
            v94 = "Caller failed to be added";
            v95 = 26;
            v67 = 0x14010B000000LL;
            v68 = 0;
            v88 = off_1800DA028;
            v89 = *(unsigned __int16 *)off_1800DA028;
            v90 = 2;
            v91 = &byte_1800C2F4F;
            v92 = 81;
            v93 = 1;
            LODWORD(TokenHandle) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwEventWriteTransfer(RegHandle, &v67, 0, 0, 6, &v88);
          }
          _InterlockedDecrement(v9 + 401);
          v11 = -2147024891;
          if ( (unsigned int)dword_1800DA020 > 3 )
          {
            v66 = "TrackCaller";
            LODWORD(TokenHandle) = -2147024891;
            v64 = "ptrFound->IncrementCount() >= MaxCount";
            v69 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v50,
              (unsigned int)byte_1800C2FA1,
              v51,
              v52,
              (__int64)&v69,
              (__int64)&v64,
              (__int64)&TokenHandle,
              (__int64)&v66);
          }
        }
        goto LABEL_81;
      }
      v33 = "CopySid failed: 0x%x in %s";
    }
    else
    {
      v11 = -2147024809;
      v32 = -2147024809;
      v33 = "IsValidSid(pSid) failed: 0x%x in %s";
    }
    _DbgPrintMessage(8, v33, (unsigned int)v11, "CTSRpcClientTrackerMgr::CTSRpcClient::Initialize");
LABEL_46:
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      v64 = "TrackCaller";
      BackTraceHash = v32;
      TokenHandle = "ptrRpcClient->Initialize";
      *(_QWORD *)pSessionId = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v36,
        (unsigned int)&byte_1800C2E87,
        v37,
        v38,
        (__int64)pSessionId,
        (__int64)&TokenHandle,
        (__int64)&BackTraceHash,
        (__int64)&v64);
    }
LABEL_81:
    CoTaskMemFree(v27);
    v4 = HIBYTE(v61);
    v3 = v61;
    goto LABEL_82;
  }
  v11 = -2147024882;
  v4 = HIBYTE(v61);
  v3 = v61;
LABEL_30:
  if ( (unsigned int)dword_1800DA020 > 3 )
  {
    v64 = "TrackCaller";
    BackTraceHash = v11;
    TokenHandle = "UserName.GetUserSid";
    *(_QWORD *)pSessionId = "Warning HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v21,
      (unsigned int)byte_1800C2E09,
      v22,
      v23,
      (__int64)pSessionId,
      (__int64)&TokenHandle,
      (__int64)&BackTraceHash,
      (__int64)&v64);
  }
LABEL_82:
  if ( v9 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v8 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v7 )
    CloseHandle(v7);
  CUserName::~CUserName((CUserName *)&v73);
  if ( v3 )
  {
    if ( v4 )
    {
      RpcRevertToSelf();
    }
    else if ( !RevertToSelf() )
    {
      GetLastError();
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180031400  mov     [rsp-8+arg_8], rbx
0x180031405  push    rbp
0x180031406  push    rsi
0x180031407  push    rdi
0x180031408  push    r12
0x18003140a  push    r13
0x18003140c  push    r14
0x18003140e  push    r15
0x180031410  lea     rbp, [rsp-0CB0h]
0x180031418  sub     rsp, 0DB0h
0x18003141f  mov     rax, cs:__security_cookie
0x180031426  xor     rax, rsp
0x180031429  mov     [rbp+0CE0h+var_40], rax
0x180031430  mov     [rsp+0DE0h+var_D70], r8
0x180031435  mov     [rsp+0DE0h+pSessionId], edx
0x180031439  mov     [rsp+0DE0h+var_D78], rcx
0x18003143e  xor     r13b, r13b
0x180031441  mov     [rsp+0DE0h+var_D9C], 0
0x180031448  xor     r14b, r14b
0x18003144b  lea     rax, ??_7?$CTSPrivateObject@UIUserName@@@@6B@; const CTSPrivateObject<IUserName>::`vftable'
0x180031452  mov     [rbp+0CE0h+var_D40], rax
0x180031456  lea     rax, aUsername; "UserName"
0x18003145d  mov     [rbp+0CE0h+var_D30], rax
0x180031461  xor     r12d, r12d
0x180031464  mov     [rbp+0CE0h+var_D38], r12d
0x180031468  mov     [rbp+0CE0h+var_D34], 1
0x18003146f  lea     rax, [rbp+0CE0h+var_718]
0x180031476  mov     [rbp+0CE0h+var_718.Blink], rax
0x18003147d  lea     rax, [rbp+0CE0h+var_718]
0x180031484  mov     [rbp+0CE0h+var_718.Flink], rax
0x18003148b  lea     rcx, [rbp+0CE0h+var_718]; struct _LIST_ENTRY *
0x180031492  call    ?AddTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; AddTrackingObject(_LIST_ENTRY *)
0x180031497  mov     [rbp+0CE0h+var_D28], r12
0x18003149b  mov     [rbp+0CE0h+var_D20], r12d
0x18003149f  mov     [rsp+0DE0h+BackTraceHash], r12d
0x1800314a4  mov     eax, 1
0x1800314a9  lock xadd [rbp+0CE0h+var_D20], eax
0x1800314ae  inc     eax
0x1800314b0  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x1800314b7  jnz     short loc_1800314E0
0x1800314b9  and     eax, 1Fh
0x1800314bc  lea     rcx, [rax+rax*2]
0x1800314c0  shl     rcx, 4
0x1800314c4  lea     r8, [rbp+0CE0h+var_D18]
0x1800314c8  add     r8, rcx; BackTrace
0x1800314cb  lea     r9, [rsp+0DE0h+BackTraceHash]; BackTraceHash
0x1800314d0  mov     edx, 6; FramesToCapture
0x1800314d5  mov     ecx, 1; FramesToSkip
0x1800314da  call    cs:__imp_RtlCaptureStackBackTrace
0x1800314e0  lea     rax, ??_7CUserName@@6B@; const CUserName::`vftable'
0x1800314e7  mov     [rbp+0CE0h+var_D40], rax
0x1800314eb  mov     [rbp+0CE0h+var_708], r12
0x1800314f2  and     [rbp+0CE0h+var_700], 0FFFFFFE0h
0x1800314f9  mov     [rbp+0CE0h+var_6F8], r12
0x180031500  mov     [rbp+0CE0h+var_2E8], r12
0x180031507  mov     [rbp+0CE0h+var_2E0], r12
0x18003150e  mov     [rbp+0CE0h+var_2D8], r12
0x180031515  mov     [rbp+0CE0h+var_2D0], r12
0x18003151c  and     [rbp+0CE0h+var_2C8], 0FFFFFFFCh
0x180031523  mov     rdi, r12
0x180031526  mov     [rbp+0CE0h+var_D50], r12
0x18003152a  mov     rbx, r12
0x18003152d  mov     [rbp+0CE0h+var_D48], rbx
0x180031531  mov     r15, r12
0x180031534  mov     [rsp+0DE0h+var_D88], r12
0x180031539  xor     edx, edx; void *
0x18003153b  call    ?CheckCurrentContext@CImpersonate@@AEAAJPEAX@Z; CImpersonate::CheckCurrentContext(void *)
0x180031540  xor     ecx, ecx; BindingHandle
0x180031542  call    cs:__imp_RpcImpersonateClient
0x180031548  mov     esi, eax
0x18003154a  test    eax, eax
0x18003154c  jle     short loc_180031557
0x18003154e  movzx   esi, ax
0x180031551  or      esi, 80070000h
0x180031557  test    esi, esi
0x180031559  jns     loc_180031695
0x18003155f  lea     r9, aCimpersonateIm_0; "CImpersonate::ImpersonateRpcClient"
0x180031566  mov     r8d, esi
0x180031569  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x180031570  mov     ecx, 8; int
0x180031575  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003157a  mov     eax, cs:dword_1800DA020
0x180031580  cmp     eax, 3
0x180031583  jbe     loc_180031F8D
0x180031589  mov     [rsp+0DE0h+BackTraceHash], esi
0x18003158d  lea     rax, aTrackcaller; "TrackCaller"
0x180031594  mov     [rbp+0CE0h+var_260], rax
0x18003159b  mov     [rbp+0CE0h+var_258], 0Ch
0x1800315a6  xor     ecx, ecx
0x1800315a8  lea     rax, [rsp+0DE0h+BackTraceHash]
0x1800315ad  mov     [rbp+0CE0h+var_270], rax
0x1800315b4  mov     [rbp+0CE0h+var_268], 4
0x1800315bf  lea     rax, aImpersonaterpc; "ImpersonateRpcClient"
0x1800315c6  mov     [rbp+0CE0h+var_280], rax
0x1800315cd  mov     [rbp+0CE0h+var_278], 15h
0x1800315d8  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800315df  mov     [rbp+0CE0h+var_290], rax
0x1800315e6  mov     [rbp+0CE0h+var_288], 17h
0x1800315f1  mov     dword ptr [rsp+0DE0h+var_D70], 0B000000h
0x1800315f9  movzx   eax, cs:word_1800C2D4D
0x180031600  mov     dword ptr [rsp+0DE0h+var_D70+4], eax
0x180031604  mov     [rsp+0DE0h+var_D68], rcx
0x180031609  mov     rax, cs:off_1800DA028
0x180031610  mov     [rbp+0CE0h+var_2B0], rax
0x180031617  movzx   eax, word ptr [rax]
0x18003161a  mov     [rbp+0CE0h+var_2A8], eax
0x180031620  mov     [rbp+0CE0h+var_2A4], 2
0x18003162a  lea     rax, byte_1800C2D57
0x180031631  mov     [rbp+0CE0h+var_2A0], rax
0x180031638  mov     [rbp+0CE0h+var_298], 33h ; '3'
0x180031642  mov     [rbp+0CE0h+var_294], 1
0x18003164c  lea     rax, _TraceLoggingMetadataEnd
0x180031653  lea     rcx, _TraceLoggingMetadata
0x18003165a  sub     eax, ecx
0x18003165c  mov     [rsp+0DE0h+pSessionId], eax
0x180031660  mov     eax, [rsp+0DE0h+pSessionId]
0x180031664  lea     rax, [rbp+0CE0h+var_2B0]
0x18003166b  mov     [rsp+0DE0h+var_DB8], rax
0x180031670  mov     dword ptr [rsp+0DE0h+var_DC0], 6
0x180031678  xor     r9d, r9d
0x18003167b  xor     r8d, r8d
0x18003167e  lea     rdx, [rsp+0DE0h+var_D70]
0x180031683  mov     rcx, cs:RegHandle
0x18003168a  call    cs:__imp_EtwEventWriteTransfer
0x180031690  jmp     loc_180031F8D
0x180031695  mov     r14b, 1
0x180031698  mov     [rsp+0DE0h+var_D9C], 101h
0x18003169f  movzx   r13d, r14b
0x1800316a3  mov     [rsp+0DE0h+TokenHandle], r12
0x1800316a8  call    cs:__imp_GetCurrentThread
0x1800316ae  mov     rcx, rax; ThreadHandle
0x1800316b1  lea     r9, [rsp+0DE0h+TokenHandle]; TokenHandle
0x1800316b6  mov     edx, 0Eh; DesiredAccess
0x1800316bb  mov     r8d, 1; OpenAsSelf
0x1800316c1  call    cs:__imp_OpenThreadToken
0x1800316c7  mov     r12d, 8
0x1800316cd  test    eax, eax
0x1800316cf  jnz     short loc_180031718
0x1800316d1  call    cs:__imp_GetLastError
0x1800316d7  mov     esi, eax
0x1800316d9  test    eax, eax
0x1800316db  jle     short loc_1800316E6
0x1800316dd  movzx   esi, ax
0x1800316e0  or      esi, 80070000h
0x1800316e6  test    esi, esi
0x1800316e8  jns     short loc_18003171A
0x1800316ea  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x1800316f1  mov     r8d, esi
0x1800316f4  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x1800316fb  mov     ecx, r12d; int
0x1800316fe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031703  mov     rax, [rsp+0DE0h+TokenHandle]
0x180031708  test    rax, rax
0x18003170b  jz      short loc_18003171F
0x18003170d  mov     rcx, rax; hObject
0x180031710  call    cs:__imp_CloseHandle
0x180031716  jmp     short loc_180031726
0x180031718  xor     esi, esi
0x18003171a  mov     rax, [rsp+0DE0h+TokenHandle]
0x18003171f  mov     rdi, rax
0x180031722  mov     [rbp+0CE0h+var_D50], rax
0x180031726  test    esi, esi
0x180031728  jns     short loc_18003179A
0x18003172a  mov     eax, cs:dword_1800DA020
0x180031730  cmp     eax, 3
0x180031733  jbe     loc_180031F8D
0x180031739  lea     rax, aTrackcaller; "TrackCaller"
0x180031740  mov     [rsp+0DE0h+var_D88], rax
0x180031745  mov     [rsp+0DE0h+BackTraceHash], esi
0x180031749  lea     rax, aGetclienttoken; "GetClientToken"
0x180031750  mov     [rsp+0DE0h+TokenHandle], rax
0x180031755  lea     rax, aWarningHresult; "Warning HResult failed"
0x18003175c  mov     qword ptr [rsp+0DE0h+pSessionId], rax
0x180031761  lea     rax, [rsp+0DE0h+var_D88]
0x180031766  mov     [rsp+0DE0h+var_DA8], rax
0x18003176b  lea     rax, [rsp+0DE0h+BackTraceHash]
0x180031770  mov     [rsp+0DE0h+var_DB0], rax
0x180031775  lea     rax, [rsp+0DE0h+TokenHandle]
0x18003177a  mov     [rsp+0DE0h+var_DB8], rax
0x18003177f  lea     rax, [rsp+0DE0h+pSessionId]
0x180031784  mov     [rsp+0DE0h+var_DC0], rax
0x180031789  lea     rdx, byte_1800C2D8B
0x180031790  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180031795  jmp     loc_180031F8D
0x18003179a  xor     r8d, r8d; int
0x18003179d  mov     rdx, rdi; void *
0x1800317a0  lea     rcx, [rbp+0CE0h+var_D40]; this
0x1800317a4  call    ?Initialize@CUserName@@UEAAJ_KH@Z; CUserName::Initialize(unsigned __int64,int)
0x1800317a9  mov     esi, eax
0x1800317ab  test    eax, eax
0x1800317ad  jns     short loc_18003181F
0x1800317af  mov     ecx, cs:dword_1800DA020
0x1800317b5  cmp     ecx, 3
0x1800317b8  jbe     loc_180031F8D
0x1800317be  lea     rax, aTrackcaller; "TrackCaller"
0x1800317c5  mov     [rsp+0DE0h+var_D88], rax
0x1800317ca  mov     [rsp+0DE0h+BackTraceHash], esi
0x1800317ce  lea     rax, aUsernameInitia; "UserName.Initialize"
0x1800317d5  mov     [rsp+0DE0h+TokenHandle], rax
0x1800317da  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800317e1  mov     qword ptr [rsp+0DE0h+pSessionId], rax
0x1800317e6  lea     rax, [rsp+0DE0h+var_D88]
0x1800317eb  mov     [rsp+0DE0h+var_DA8], rax
0x1800317f0  lea     rax, [rsp+0DE0h+BackTraceHash]
0x1800317f5  mov     [rsp+0DE0h+var_DB0], rax
0x1800317fa  lea     rax, [rsp+0DE0h+TokenHandle]
0x1800317ff  mov     [rsp+0DE0h+var_DB8], rax
0x180031804  lea     rax, [rsp+0DE0h+pSessionId]
0x180031809  mov     [rsp+0DE0h+var_DC0], rax
0x18003180e  lea     rdx, word_1800C2DCA
0x180031815  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003181a  jmp     loc_180031F8D
0x18003181f  mov     eax, [rbp+0CE0h+var_700]
0x180031825  test    al, 2
0x180031827  jnz     short loc_180031875
0x180031829  test    r14b, al
0x18003182c  jnz     short loc_180031844
0x18003182e  lea     rdx, aNoToken; "No token"
0x180031835  mov     ecx, r12d; int
0x180031838  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003183d  mov     esi, 800703F0h
0x180031842  jmp     short loc_1800318AC
0x180031844  mov     rdx, [rbp+0CE0h+var_708]; void *
0x18003184b  lea     rcx, [rbp+0CE0h+var_D40]; this
0x18003184f  call    ?InitializeUserName@CUserName@@AEAAJPEAX@Z; CUserName::InitializeUserName(void *)
0x180031854  mov     esi, eax
0x180031856  test    eax, eax
0x180031858  jns     short loc_180031875
0x18003185a  lea     r9, aCusernameGetus_0; "CUserName::GetUserSid"
0x180031861  mov     r8d, eax
0x180031864  lea     rdx, aInitializeuser; "InitializeUserName failed: 0x%x in %s"
0x18003186b  mov     ecx, r12d; int
0x18003186e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031873  jmp     short loc_1800318AC
0x180031875  mov     rcx, [rbp+0CE0h+var_6F8]
0x18003187c  mov     rcx, [rcx]; Sid
0x18003187f  call    cs:__imp_RtlLengthSid
0x180031885  mov     esi, eax
0x180031887  mov     ecx, eax; cb
0x180031889  call    cs:__imp_CoTaskMemAlloc
0x18003188f  mov     r13, rax
0x180031892  test    rax, rax
0x180031895  jnz     loc_18003191C
0x18003189b  mov     esi, 8007000Eh
0x1800318a0  movzx   r14d, byte ptr [rsp+0DE0h+var_D9C+1]
0x1800318a6  movzx   r13d, byte ptr [rsp+0DE0h+var_D9C]
0x1800318ac  mov     eax, cs:dword_1800DA020
0x1800318b2  cmp     eax, 3
0x1800318b5  jbe     loc_180031F8D
0x1800318bb  lea     rax, aTrackcaller; "TrackCaller"
0x1800318c2  mov     [rsp+0DE0h+var_D88], rax
0x1800318c7  mov     [rsp+0DE0h+BackTraceHash], esi
0x1800318cb  lea     rax, aUsernameGetuse; "UserName.GetUserSid"
0x1800318d2  mov     [rsp+0DE0h+TokenHandle], rax
0x1800318d7  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800318de  mov     qword ptr [rsp+0DE0h+pSessionId], rax
0x1800318e3  lea     rax, [rsp+0DE0h+var_D88]
0x1800318e8  mov     [rsp+0DE0h+var_DA8], rax
0x1800318ed  lea     rax, [rsp+0DE0h+BackTraceHash]
0x1800318f2  mov     [rsp+0DE0h+var_DB0], rax
0x1800318f7  lea     rax, [rsp+0DE0h+TokenHandle]
0x1800318fc  mov     [rsp+0DE0h+var_DB8], rax
0x180031901  lea     rax, [rsp+0DE0h+pSessionId]
0x180031906  mov     [rsp+0DE0h+var_DC0], rax
0x18003190b  lea     rdx, byte_1800C2E09
0x180031912  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180031917  jmp     loc_180031F8D
0x18003191c  mov     r8, rsi; Size
0x18003191f  mov     rdx, [rbp+0CE0h+var_6F8]
0x180031926  mov     rdx, [rdx]; Src
0x180031929  mov     rcx, r13; void *
0x18003192c  call    memcpy_0
0x180031931  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180031938  mov     ecx, 648h; unsigned __int64
0x18003193d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180031942  mov     rbx, rax
0x180031945  mov     [rbp+0CE0h+var_D60], rax
0x180031949  test    rax, rax
0x18003194c  jz      short loc_180031979
0x18003194e  lea     rdx, aCtsrpcclient; "CTSRpcClient"
0x180031955  mov     rcx, rax
0x180031958  call    ??0?$CTSObject@UIUnknown@@@@QEAA@PEBD@Z; CTSObject<IUnknown>::CTSObject<IUnknown>(char const *)
0x18003195d  lea     rax, ??_7CTSRpcClient@CTSRpcClientTrackerMgr@@6B@; const CTSRpcClientTrackerMgr::CTSRpcClient::`vftable'
0x180031964  mov     [rbx], rax
0x180031967  xor     esi, esi
0x180031969  mov     [rbx+638h], rsi
0x180031970  mov     [rbx+640h], rsi
0x180031977  jmp     short loc_18003197D
0x180031979  xor     esi, esi
0x18003197b  mov     ebx, esi
0x18003197d  mov     [rbp+0CE0h+var_D48], rbx
0x180031981  test    rbx, rbx
0x180031984  jz      loc_180031F09
0x18003198a  mov     rax, [rbx]
0x18003198d  mov     rcx, rbx
0x180031990  mov     rax, [rax+8]
0x180031994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031999  mov     rcx, r13; pSid
0x18003199c  call    cs:__imp_IsValidSid
0x1800319a2  test    eax, eax
  ... truncated ...
```
