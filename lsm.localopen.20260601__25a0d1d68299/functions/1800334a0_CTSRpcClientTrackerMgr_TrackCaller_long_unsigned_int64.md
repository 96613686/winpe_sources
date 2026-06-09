# CTSRpcClientTrackerMgr::TrackCaller(long,unsigned __int64 *)

- ea: `0x1800334a0`
- end: `0x1800340f2`
- name: `?TrackCaller@CTSRpcClientTrackerMgr@@UEAAJJPEA_K@Z`
- size: `3154`
- prototype: `__int64 __fastcall(CTSRpcClientTrackerMgr *__hidden this, int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001b90`
- `0x1800051f0`
- `0x1800077a0`
- `0x180008f40`
- `0x180013880`
- `0x180014430`
- `0x180014a10`
- `0x1800192f0`
- `0x18001eb00`
- `0x180023984`
- `0x1800243ec`
- `0x1800334a0`
- `0x18004e850`
- `0x18004ec5c`
- `0x18009959c`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180033c44`
- `ntdll!RtlReleaseResource` at `0x180033cfd`
- `ntdll!RtlReleaseResource` at `0x180033d1e`
- `ntdll!RtlReleaseResource` at `0x180033c44`
- `ntdll!RtlReleaseResource` at `0x180033cfd`
- `ntdll!RtlReleaseResource` at `0x180033d1e`
- `ntdll!RtlAcquireResourceExclusive` at `0x180033b6e`
- `ntdll!RtlAcquireResourceExclusive` at `0x180033b6e`
- `ntdll!RtlCaptureStackBackTrace` at `0x180033574`
- `ntdll!RtlCaptureStackBackTrace` at `0x180033574`
- `ntdll!RtlInsertElementGenericTable` at `0x180033bb3`
- `ntdll!RtlInsertElementGenericTable` at `0x180033bb3`
- `ntdll!RtlLengthSid` at `0x1800338ff`
- `ntdll!RtlLengthSid` at `0x1800338ff`
- `ntdll!EtwEventWriteTransfer` at `0x1800336fa`
- `ntdll!EtwEventWriteTransfer` at `0x180033eac`
- `ntdll!EtwEventWriteTransfer` at `0x1800336fa`
- `ntdll!EtwEventWriteTransfer` at `0x180033eac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033aa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800340b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033aa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800340b8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003372f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003372f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033710`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033710`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003378a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034075`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003378a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034075`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033a55`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033a55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034036`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034036`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003390f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003390f`
- `RPCRT4!RpcRevertToSelf` at `0x18003409a`
- `RPCRT4!RpcRevertToSelf` at `0x18003409a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180033f4e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180033f4e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180033a8e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180033a8e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180033a3c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180033a3c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180033a15`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180033a15`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800340a8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800340a8`

## string_xrefs

- `0x1800338ae`: `No token`
- `0x18003376e`: `OpenThreadToken failed: 0x%x in %s`
- `0x180033764`: `CRpcUtils::GetClientToken`
- `0x180033630`: `ImpersonateRpcClient`
- `0x1800337ca`: `GetClientToken`
- `0x180033947`: `UserName.GetUserSid`
- `0x180033a2d`: `IsValidSid(pSid) failed: 0x%x in %s`
- `0x180033ac8`: `CopySid failed: 0x%x in %s`
- `0x1800338da`: `CUserName::GetUserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CTSRpcClientTrackerMgr::TrackCaller(CTSRpcClientTrackerMgr *this, DWORD a2, unsigned __int64 *a3)
{
  ULONG v3; // r14d
  char v4; // al
  void *v5; // rdi
  void *v6; // rbx
  volatile signed __int32 *v7; // r15
  signed int v8; // eax
  signed int v9; // esi
  HANDLE CurrentThread; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  signed int LastError; // eax
  void *v15; // rax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // eax
  SIZE_T v23; // rsi
  void *v24; // rax
  void *v25; // r13
  void *v26; // rax
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  const char *v30; // rdx
  DWORD LengthSid; // eax
  HLOCAL v32; // rax
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  signed int v36; // eax
  const char *v37; // r14
  char *v38; // r15
  struct _RTL_GENERIC_TABLE *v39; // r14
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  int v46; // eax
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  __int64 v50; // rax
  RPC_STATUS v51; // eax
  int v52; // r8d
  int v53; // r9d
  signed int v54; // ecx
  const char *v55; // rax
  ULONG BackTraceHash; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v59; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pSessionId[2]; // [rsp+58h] [rbp-A8h] BYREF
  char *v61; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 NewElement[8]; // [rsp+68h] [rbp-98h] BYREF
  const char *v63; // [rsp+70h] [rbp-90h] BYREF
  __int64 v64; // [rsp+78h] [rbp-88h] BYREF
  __int64 v65; // [rsp+80h] [rbp-80h]
  const char *v66; // [rsp+88h] [rbp-78h] BYREF
  int v67; // [rsp+90h] [rbp-70h]
  void *v68; // [rsp+98h] [rbp-68h]
  void *v69; // [rsp+A0h] [rbp-60h]
  void **v70; // [rsp+B0h] [rbp-50h] BYREF
  int v71; // [rsp+B8h] [rbp-48h]
  int v72; // [rsp+BCh] [rbp-44h]
  const char *v73; // [rsp+C0h] [rbp-40h]
  __int64 v74; // [rsp+C8h] [rbp-38h]
  signed __int32 v75[386]; // [rsp+D0h] [rbp-30h] BYREF
  struct _LIST_ENTRY v76; // [rsp+6D8h] [rbp+5D8h] BYREF
  void *v77; // [rsp+6E8h] [rbp+5E8h]
  int v78; // [rsp+6F0h] [rbp+5F0h]
  PSID *v79; // [rsp+6F8h] [rbp+5F8h]
  __int64 v80; // [rsp+B08h] [rbp+A08h]
  __int64 v81; // [rsp+B10h] [rbp+A10h]
  __int64 v82; // [rsp+B18h] [rbp+A18h]
  __int64 v83; // [rsp+B20h] [rbp+A20h]
  int v84; // [rsp+B28h] [rbp+A28h]
  int *v85; // [rsp+B40h] [rbp+A40h] BYREF
  int v86; // [rsp+B48h] [rbp+A48h]
  int v87; // [rsp+B4Ch] [rbp+A4Ch]
  char *v88; // [rsp+B50h] [rbp+A50h]
  int v89; // [rsp+B58h] [rbp+A58h]
  int v90; // [rsp+B5Ch] [rbp+A5Ch]
  const char *v91; // [rsp+B60h] [rbp+A60h]
  __int64 v92; // [rsp+B68h] [rbp+A68h]
  unsigned __int16 *v93; // [rsp+B70h] [rbp+A70h]
  __int64 v94; // [rsp+B78h] [rbp+A78h]
  ULONG *p_BackTraceHash; // [rsp+B80h] [rbp+A80h]
  __int64 v96; // [rsp+B88h] [rbp+A88h]
  const char **v97; // [rsp+B90h] [rbp+A90h]
  __int64 v98; // [rsp+B98h] [rbp+A98h]
  unsigned __int16 v99[264]; // [rsp+BA0h] [rbp+AA0h] BYREF

  v64 = (__int64)a3;
  pSessionId[0] = a2;
  v63 = (const char *)this;
  v59 = 0;
  v70 = &CTSPrivateObject<IUserName>::`vftable';
  v73 = "UserName";
  v3 = 0;
  v71 = 0;
  v72 = 1;
  v76.Blink = &v76;
  v76.Flink = &v76;
  AddTrackingObject(&v76);
  v74 = 0;
  v75[0] = 0;
  BackTraceHash = 0;
  v4 = _InterlockedIncrement(v75);
  if ( g_bCaptureObjectStackTrace == 1 )
    RtlCaptureStackBackTrace(1u, 6u, (PVOID *)&v75[12 * (v4 & 0x1F) + 2], &BackTraceHash);
  v70 = &CUserName::`vftable';
  v77 = 0;
  v78 &= 0xFFFFFFE0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 &= 0xFFFFFFFC;
  v5 = 0;
  v68 = 0;
  v6 = 0;
  v69 = 0;
  v7 = 0;
  v61 = 0;
  v8 = CImpersonate::ImpersonateRpcClient((CImpersonate *)&v59);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      BackTraceHash = v8;
      v97 = (const char **)"TrackCaller";
      v98 = 12;
      p_BackTraceHash = &BackTraceHash;
      v96 = 4;
      v93 = (unsigned __int16 *)"ImpersonateRpcClient";
      v94 = 21;
      v91 = "Warning HResult failed";
      v92 = 23;
      v64 = 0x14030B000000LL;
      v65 = 0;
      v85 = off_1800DF028;
      v86 = *(unsigned __int16 *)off_1800DF028;
      v87 = 2;
      v88 = &byte_1800C7EDF;
      v89 = 51;
      v90 = 1;
      pSessionId[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(RegHandle, &v64, 0, 0, 6, &v85);
    }
    goto LABEL_80;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    v9 = 0;
LABEL_13:
    v15 = TokenHandle;
    goto LABEL_14;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( v9 >= 0 )
    goto LABEL_13;
  _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", v9, "CRpcUtils::GetClientToken");
  v15 = TokenHandle;
  if ( !TokenHandle )
  {
LABEL_14:
    v5 = v15;
    v68 = v15;
    goto LABEL_15;
  }
  CloseHandle(TokenHandle);
LABEL_15:
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      v61 = "TrackCaller";
      BackTraceHash = v9;
      TokenHandle = "GetClientToken";
      *(_QWORD *)pSessionId = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v11,
        (unsigned int)byte_1800C7F13,
        v12,
        v13,
        (__int64)pSessionId,
        (__int64)&TokenHandle,
        (__int64)&BackTraceHash,
        (__int64)&v61);
    }
    goto LABEL_80;
  }
  v9 = CUserName::Initialize((CUserName *)&v70, v5, 0);
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      v61 = "TrackCaller";
      BackTraceHash = v9;
      TokenHandle = "UserName.Initialize";
      *(_QWORD *)pSessionId = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v16,
        (unsigned int)word_1800C7F52,
        v17,
        v18,
        (__int64)pSessionId,
        (__int64)&TokenHandle,
        (__int64)&BackTraceHash,
        (__int64)&v61);
    }
    goto LABEL_80;
  }
  if ( (v78 & 2) == 0 )
  {
    if ( (v78 & 1) == 0 )
    {
      _DbgPrintMessage(8, "No token");
      v9 = -2147023888;
      goto LABEL_28;
    }
    v22 = CUserName::InitializeUserName((CUserName *)&v70, v77);
    v9 = v22;
    if ( v22 < 0 )
    {
      _DbgPrintMessage(8, "InitializeUserName failed: 0x%x in %s", v22, "CUserName::GetUserSid");
      goto LABEL_28;
    }
  }
  v23 = RtlLengthSid(*v79);
  v24 = CoTaskMemAlloc(v23);
  v25 = v24;
  if ( v24 )
  {
    memcpy_0(v24, *v79, v23);
    v26 = operator new(0x648u, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v26;
    v66 = (const char *)v26;
    if ( v26 )
    {
      CTSObject<IUnknown>::CTSObject<IUnknown>(v26, "CTSRpcClient");
      *(_QWORD *)v6 = &CTSRpcClientTrackerMgr::CTSRpcClient::`vftable';
      *((_QWORD *)v6 + 199) = 0;
      *((_QWORD *)v6 + 200) = 0;
    }
    else
    {
      v6 = 0;
    }
    v69 = v6;
    if ( !v6 )
    {
      v9 = -2147024882;
      if ( (unsigned int)dword_1800DF020 > 3 )
      {
        v64 = (__int64)"TrackCaller";
        LODWORD(TokenHandle) = -2147024882;
        v66 = "New CTSRpcClient";
        v63 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v27,
          (unsigned int)qword_1800C7FD0,
          v28,
          v29,
          (__int64)&v63,
          (__int64)&v66,
          (__int64)&TokenHandle,
          (__int64)&v64);
      }
      goto LABEL_79;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( IsValidSid(v25) )
    {
      LengthSid = GetLengthSid(v25);
      *((_DWORD *)v6 + 400) = LengthSid;
      v32 = LocalAlloc(0x40u, LengthSid);
      *((_QWORD *)v6 + 199) = v32;
      if ( !v32 )
      {
        v3 = -2147024882;
        v9 = -2147024882;
        _DbgPrintMessage(
          8,
          "LocalAlloc failed: 0x%x in %s",
          2147942414LL,
          "CTSRpcClientTrackerMgr::CTSRpcClient::Initialize");
        goto LABEL_44;
      }
      if ( CopySid(*((_DWORD *)v6 + 400), v32, v25) )
        goto LABEL_46;
      v36 = GetLastError();
      v9 = v36;
      if ( v36 > 0 )
        v9 = (unsigned __int16)v36 | 0x80070000;
      v3 = v9;
      if ( v9 >= 0 )
      {
LABEL_46:
        v9 = v3;
        v37 = v63;
        v38 = (char *)(v63 + 1592);
        v66 = v63 + 1592;
        v67 = 1;
        if ( *((_DWORD *)v63 + 422) )
          RtlAcquireResourceExclusive((PRTL_RESOURCE)(v63 + 1592), 1u);
        v39 = (struct _RTL_GENERIC_TABLE *)(v37 + 1696);
        if ( !(unsigned int)CListTree<CTSRpcClientTrackerMgr::CTSRpcClient>::Lookup(v39, v6, &v61) )
        {
          TokenHandle = v6;
          NewElement[0] = 0;
          if ( !RtlInsertElementGenericTable(v39, &TokenHandle, 8u, NewElement) )
          {
            v9 = -2147024882;
            if ( (unsigned int)dword_1800DF020 > 3 )
            {
              v63 = "TrackCaller";
              BackTraceHash = -2147024882;
              TokenHandle = "m_ptrRpcClientList.Add";
              *(_QWORD *)pSessionId = "Warning HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v40,
                (unsigned int)&word_1800C804E,
                v41,
                v42,
                (__int64)pSessionId,
                (__int64)&TokenHandle,
                (__int64)&BackTraceHash,
                (__int64)&v63);
            }
            if ( *((_DWORD *)v38 + 24) )
              RtlReleaseResource((PRTL_RESOURCE)v38);
            v7 = (volatile signed __int32 *)v61;
            goto LABEL_79;
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)TokenHandle + 8LL))(TokenHandle);
          v9 = 0;
          if ( !(unsigned int)CListTree<CTSRpcClientTrackerMgr::CTSRpcClient>::Lookup(v39, v6, &v61) )
          {
            v9 = -2147023537;
            if ( (unsigned int)dword_1800DF020 > 3 )
            {
              v63 = "TrackCaller";
              BackTraceHash = -2147023537;
              TokenHandle = "m_ptrRpcClientList.Lookup";
              *(_QWORD *)pSessionId = "Warning HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v43,
                (unsigned int)byte_1800C808D,
                v44,
                v45,
                (__int64)pSessionId,
                (__int64)&TokenHandle,
                (__int64)&BackTraceHash,
                (__int64)&v63);
            }
            if ( *((_DWORD *)v38 + 24) )
              RtlReleaseResource((PRTL_RESOURCE)v38);
            v7 = (volatile signed __int32 *)v61;
            goto LABEL_79;
          }
        }
        if ( *((_DWORD *)v38 + 24) )
          RtlReleaseResource((PRTL_RESOURCE)v38);
        v7 = (volatile signed __int32 *)v61;
        v46 = _InterlockedIncrement((volatile signed __int32 *)v61 + 401);
        if ( v46 <= (int)pSessionId[0] )
        {
          if ( (unsigned int)dword_1800DF020 > 5 )
          {
            LODWORD(TokenHandle) = *((_DWORD *)v7 + 401);
            BackTraceHash = 0;
            v51 = I_RpcBindingInqLocalClientPID(0, &BackTraceHash);
            v54 = v51;
            if ( v51 > 0 )
              v54 = (unsigned __int16)v51 | 0x80070000;
            v55 = 0;
            if ( v54 >= 0 )
              v55 = (const char *)BackTraceHash;
            v66 = v55;
            v63 = "RpcClientTracker added successfully this RPC Caller";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              v54,
              (unsigned int)qword_1800C8168,
              v52,
              v53,
              (__int64)&v63,
              (__int64)&v66,
              (__int64)&TokenHandle);
          }
          *(_QWORD *)v64 = v7;
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
        }
        else
        {
          BackTraceHash = 0;
          pSessionId[0] = 0;
          CRpcUtils::GetRpcCallerInfo(pSessionId, &BackTraceHash, 0x104u, v99);
          if ( (unsigned int)dword_1800DF020 > 1 )
          {
            v63 = (const char *)pSessionId[0];
            v61 = (char *)BackTraceHash;
            v97 = &v63;
            v98 = 8;
            p_BackTraceHash = (ULONG *)&v61;
            v96 = 8;
            v50 = -1;
            do
              ++v50;
            while ( v99[v50] );
            v93 = v99;
            v94 = (unsigned int)(2 * v50 + 2);
            v91 = "Caller failed to be added";
            v92 = 26;
            v64 = 0x14010B000000LL;
            v65 = 0;
            v85 = off_1800DF028;
            v86 = *(unsigned __int16 *)off_1800DF028;
            v87 = 2;
            v88 = &byte_1800C80D7;
            v89 = 81;
            v90 = 1;
            LODWORD(TokenHandle) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwEventWriteTransfer(RegHandle, &v64, 0, 0, 6, &v85);
          }
          _InterlockedDecrement(v7 + 401);
          v9 = -2147024891;
          if ( (unsigned int)dword_1800DF020 > 3 )
          {
            v63 = "TrackCaller";
            LODWORD(TokenHandle) = -2147024891;
            v61 = "ptrFound->IncrementCount() >= MaxCount";
            v66 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v47,
              (unsigned int)byte_1800C8129,
              v48,
              v49,
              (__int64)&v66,
              (__int64)&v61,
              (__int64)&TokenHandle,
              (__int64)&v63);
          }
        }
        goto LABEL_79;
      }
      v30 = "CopySid failed: 0x%x in %s";
    }
    else
    {
      v9 = -2147024809;
      v3 = -2147024809;
      v30 = "IsValidSid(pSid) failed: 0x%x in %s";
    }
    _DbgPrintMessage(8, v30, (unsigned int)v9, "CTSRpcClientTrackerMgr::CTSRpcClient::Initialize");
LABEL_44:
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      v61 = "TrackCaller";
      BackTraceHash = v3;
      TokenHandle = "ptrRpcClient->Initialize";
      *(_QWORD *)pSessionId = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v33,
        (unsigned int)&byte_1800C800F,
        v34,
        v35,
        (__int64)pSessionId,
        (__int64)&TokenHandle,
        (__int64)&BackTraceHash,
        (__int64)&v61);
    }
LABEL_79:
    CoTaskMemFree(v25);
    goto LABEL_80;
  }
  v9 = -2147024882;
LABEL_28:
  if ( (unsigned int)dword_1800DF020 > 3 )
  {
    v61 = "TrackCaller";
    BackTraceHash = v9;
    TokenHandle = "UserName.GetUserSid";
    *(_QWORD *)pSessionId = "Warning HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v19,
      (unsigned int)byte_1800C7F91,
      v20,
      v21,
      (__int64)pSessionId,
      (__int64)&TokenHandle,
      (__int64)&BackTraceHash,
      (__int64)&v61);
  }
LABEL_80:
  if ( v7 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v6 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v5 )
    CloseHandle(v5);
  CUserName::~CUserName((CUserName *)&v70);
  if ( (_BYTE)v59 )
  {
    if ( HIBYTE(v59) )
    {
      RpcRevertToSelf();
    }
    else if ( !RevertToSelf() )
    {
      GetLastError();
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800334a0  mov     [rsp-8+arg_8], rbx
0x1800334a5  push    rbp
0x1800334a6  push    rsi
0x1800334a7  push    rdi
0x1800334a8  push    r12
0x1800334aa  push    r13
0x1800334ac  push    r14
0x1800334ae  push    r15
0x1800334b0  lea     rbp, [rsp-0CC0h]
0x1800334b8  sub     rsp, 0DC0h
0x1800334bf  mov     rax, cs:__security_cookie
0x1800334c6  xor     rax, rsp
0x1800334c9  mov     [rbp+0CF0h+var_40], rax
0x1800334d0  mov     [rsp+0DF0h+var_D78], r8
0x1800334d5  mov     [rsp+0DF0h+pSessionId], edx
0x1800334d9  mov     [rsp+0DF0h+var_D80], rcx
0x1800334de  mov     [rsp+0DF0h+var_DA0], 0
0x1800334e5  lea     rax, ??_7?$CTSPrivateObject@UIUserName@@@@6B@; const CTSPrivateObject<IUserName>::`vftable'
0x1800334ec  mov     [rbp+0CF0h+var_D40], rax
0x1800334f0  lea     rax, aUsername; "UserName"
0x1800334f7  mov     [rbp+0CF0h+var_D30], rax
0x1800334fb  xor     r14d, r14d
0x1800334fe  mov     [rbp+0CF0h+var_D38], r14d
0x180033502  mov     [rbp+0CF0h+var_D34], 1
0x180033509  lea     rax, [rbp+0CF0h+var_718]
0x180033510  mov     [rbp+0CF0h+var_718.Blink], rax
0x180033517  lea     rax, [rbp+0CF0h+var_718]
0x18003351e  mov     [rbp+0CF0h+var_718.Flink], rax
0x180033525  lea     rcx, [rbp+0CF0h+var_718]; struct _LIST_ENTRY *
0x18003352c  call    ?AddTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; AddTrackingObject(_LIST_ENTRY *)
0x180033531  mov     [rbp+0CF0h+var_D28], r14
0x180033535  mov     [rbp+0CF0h+var_D20], r14d
0x180033539  mov     [rsp+0DF0h+BackTraceHash], r14d
0x18003353e  mov     eax, 1
0x180033543  lock xadd [rbp+0CF0h+var_D20], eax
0x180033548  inc     eax
0x18003354a  cmp     cs:?g_bCaptureObjectStackTrace@@3HA, 1; int g_bCaptureObjectStackTrace
0x180033551  jnz     short loc_180033580
0x180033553  and     eax, 1Fh
0x180033556  lea     rcx, [rax+rax*2]
0x18003355a  shl     rcx, 4
0x18003355e  lea     r8, [rbp+0CF0h+var_D18]
0x180033562  add     r8, rcx; BackTrace
0x180033565  lea     r9, [rsp+0DF0h+BackTraceHash]; BackTraceHash
0x18003356a  mov     edx, 6; FramesToCapture
0x18003356f  mov     ecx, 1; FramesToSkip
0x180033574  call    cs:__imp_RtlCaptureStackBackTrace
0x18003357b  nop     dword ptr [rax+rax+00h]
0x180033580  lea     rax, ??_7CUserName@@6B@; const CUserName::`vftable'
0x180033587  mov     [rbp+0CF0h+var_D40], rax
0x18003358b  mov     [rbp+0CF0h+var_708], r14
0x180033592  and     [rbp+0CF0h+var_700], 0FFFFFFE0h
0x180033599  mov     [rbp+0CF0h+var_6F8], r14
0x1800335a0  mov     [rbp+0CF0h+var_2E8], r14
0x1800335a7  mov     [rbp+0CF0h+var_2E0], r14
0x1800335ae  mov     [rbp+0CF0h+var_2D8], r14
0x1800335b5  mov     [rbp+0CF0h+var_2D0], r14
0x1800335bc  and     [rbp+0CF0h+var_2C8], 0FFFFFFFCh
0x1800335c3  mov     rdi, r14
0x1800335c6  mov     [rbp+0CF0h+var_D58], r14
0x1800335ca  mov     rbx, r14
0x1800335cd  mov     [rbp+0CF0h+var_D50], rbx
0x1800335d1  mov     r15, r14
0x1800335d4  mov     [rsp+0DF0h+var_D90], r14
0x1800335d9  lea     rcx, [rsp+0DF0h+var_DA0]; this
0x1800335de  call    ?ImpersonateRpcClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateRpcClient(void)
0x1800335e3  mov     esi, eax
0x1800335e5  test    eax, eax
0x1800335e7  jns     loc_18003370B
0x1800335ed  mov     ecx, cs:dword_1800DF020
0x1800335f3  cmp     ecx, 3
0x1800335f6  jbe     loc_180034043
0x1800335fc  mov     [rsp+0DF0h+BackTraceHash], eax
0x180033600  lea     rax, aTrackcaller; "TrackCaller"
0x180033607  mov     [rbp+0CF0h+var_260], rax
0x18003360e  mov     [rbp+0CF0h+var_258], 0Ch
0x180033619  lea     rax, [rsp+0DF0h+BackTraceHash]
0x18003361e  mov     [rbp+0CF0h+var_270], rax
0x180033625  mov     [rbp+0CF0h+var_268], 4
0x180033630  lea     rax, aImpersonaterpc; "ImpersonateRpcClient"
0x180033637  mov     [rbp+0CF0h+var_280], rax
0x18003363e  mov     [rbp+0CF0h+var_278], 15h
0x180033649  lea     rax, aWarningHresult; "Warning HResult failed"
0x180033650  mov     [rbp+0CF0h+var_290], rax
0x180033657  mov     [rbp+0CF0h+var_288], 17h
0x180033662  mov     dword ptr [rsp+0DF0h+var_D78], 0B000000h
0x18003366a  movzx   eax, cs:word_1800C7ED5
0x180033671  mov     dword ptr [rsp+0DF0h+var_D78+4], eax
0x180033675  mov     [rbp+0CF0h+var_D70], r14
0x180033679  mov     rax, cs:off_1800DF028
0x180033680  mov     [rbp+0CF0h+var_2B0], rax
0x180033687  movzx   eax, word ptr [rax]
0x18003368a  mov     [rbp+0CF0h+var_2A8], eax
0x180033690  mov     [rbp+0CF0h+var_2A4], 2
0x18003369a  lea     rax, byte_1800C7EDF
0x1800336a1  mov     [rbp+0CF0h+var_2A0], rax
0x1800336a8  mov     [rbp+0CF0h+var_298], 33h ; '3'
0x1800336b2  mov     [rbp+0CF0h+var_294], 1
0x1800336bc  lea     rax, _TraceLoggingMetadataEnd
0x1800336c3  lea     rcx, _TraceLoggingMetadata
0x1800336ca  sub     eax, ecx
0x1800336cc  mov     [rsp+0DF0h+pSessionId], eax
0x1800336d0  mov     eax, [rsp+0DF0h+pSessionId]
0x1800336d4  lea     rax, [rbp+0CF0h+var_2B0]
0x1800336db  mov     [rsp+0DF0h+var_DC8], rax
0x1800336e0  mov     dword ptr [rsp+0DF0h+var_DD0], 6
0x1800336e8  xor     r9d, r9d
0x1800336eb  xor     r8d, r8d
0x1800336ee  lea     rdx, [rsp+0DF0h+var_D78]
0x1800336f3  mov     rcx, cs:RegHandle
0x1800336fa  call    cs:__imp_EtwEventWriteTransfer
0x180033701  nop     dword ptr [rax+rax+00h]
0x180033706  jmp     loc_180034043
0x18003370b  mov     [rsp+0DF0h+TokenHandle], r14
0x180033710  call    cs:__imp_GetCurrentThread
0x180033717  nop     dword ptr [rax+rax+00h]
0x18003371c  mov     rcx, rax; ThreadHandle
0x18003371f  lea     r9, [rsp+0DF0h+TokenHandle]; TokenHandle
0x180033724  mov     edx, 0Eh; DesiredAccess
0x180033729  mov     r8d, 1; OpenAsSelf
0x18003372f  call    cs:__imp_OpenThreadToken
0x180033736  nop     dword ptr [rax+rax+00h]
0x18003373b  mov     r12d, 8
0x180033741  test    eax, eax
0x180033743  jnz     short loc_180033798
0x180033745  call    cs:__imp_GetLastError
0x18003374c  nop     dword ptr [rax+rax+00h]
0x180033751  mov     esi, eax
0x180033753  test    eax, eax
0x180033755  jle     short loc_180033760
0x180033757  movzx   esi, ax
0x18003375a  or      esi, 80070000h
0x180033760  test    esi, esi
0x180033762  jns     short loc_18003379B
0x180033764  lea     r9, aCrpcutilsGetcl; "CRpcUtils::GetClientToken"
0x18003376b  mov     r8d, esi
0x18003376e  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x180033775  mov     ecx, r12d; int
0x180033778  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003377d  mov     rax, [rsp+0DF0h+TokenHandle]
0x180033782  test    rax, rax
0x180033785  jz      short loc_1800337A0
0x180033787  mov     rcx, rax; hObject
0x18003378a  call    cs:__imp_CloseHandle
0x180033791  nop     dword ptr [rax+rax+00h]
0x180033796  jmp     short loc_1800337A7
0x180033798  mov     esi, r14d
0x18003379b  mov     rax, [rsp+0DF0h+TokenHandle]
0x1800337a0  mov     rdi, rax
0x1800337a3  mov     [rbp+0CF0h+var_D58], rax
0x1800337a7  test    esi, esi
0x1800337a9  jns     short loc_18003381B
0x1800337ab  mov     eax, cs:dword_1800DF020
0x1800337b1  cmp     eax, 3
0x1800337b4  jbe     loc_180034043
0x1800337ba  lea     rax, aTrackcaller; "TrackCaller"
0x1800337c1  mov     [rsp+0DF0h+var_D90], rax
0x1800337c6  mov     [rsp+0DF0h+BackTraceHash], esi
0x1800337ca  lea     rax, aGetclienttoken; "GetClientToken"
0x1800337d1  mov     [rsp+0DF0h+TokenHandle], rax
0x1800337d6  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800337dd  mov     qword ptr [rsp+0DF0h+pSessionId], rax
0x1800337e2  lea     rax, [rsp+0DF0h+var_D90]
0x1800337e7  mov     [rsp+0DF0h+var_DB8], rax
0x1800337ec  lea     rax, [rsp+0DF0h+BackTraceHash]
0x1800337f1  mov     [rsp+0DF0h+var_DC0], rax
0x1800337f6  lea     rax, [rsp+0DF0h+TokenHandle]
0x1800337fb  mov     [rsp+0DF0h+var_DC8], rax
0x180033800  lea     rax, [rsp+0DF0h+pSessionId]
0x180033805  mov     [rsp+0DF0h+var_DD0], rax
0x18003380a  lea     rdx, byte_1800C7F13
0x180033811  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180033816  jmp     loc_180034043
0x18003381b  xor     r8d, r8d; int
0x18003381e  mov     rdx, rdi; void *
0x180033821  lea     rcx, [rbp+0CF0h+var_D40]; this
0x180033825  call    ?Initialize@CUserName@@UEAAJ_KH@Z; CUserName::Initialize(unsigned __int64,int)
0x18003382a  mov     esi, eax
0x18003382c  test    eax, eax
0x18003382e  jns     short loc_1800338A0
0x180033830  mov     eax, cs:dword_1800DF020
0x180033836  cmp     eax, 3
0x180033839  jbe     loc_180034043
0x18003383f  lea     rax, aTrackcaller; "TrackCaller"
0x180033846  mov     [rsp+0DF0h+var_D90], rax
0x18003384b  mov     [rsp+0DF0h+BackTraceHash], esi
0x18003384f  lea     rax, aUsernameInitia; "UserName.Initialize"
0x180033856  mov     [rsp+0DF0h+TokenHandle], rax
0x18003385b  lea     rax, aWarningHresult; "Warning HResult failed"
0x180033862  mov     qword ptr [rsp+0DF0h+pSessionId], rax
0x180033867  lea     rax, [rsp+0DF0h+var_D90]
0x18003386c  mov     [rsp+0DF0h+var_DB8], rax
0x180033871  lea     rax, [rsp+0DF0h+BackTraceHash]
0x180033876  mov     [rsp+0DF0h+var_DC0], rax
0x18003387b  lea     rax, [rsp+0DF0h+TokenHandle]
0x180033880  mov     [rsp+0DF0h+var_DC8], rax
0x180033885  lea     rax, [rsp+0DF0h+pSessionId]
0x18003388a  mov     [rsp+0DF0h+var_DD0], rax
0x18003388f  lea     rdx, word_1800C7F52
0x180033896  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003389b  jmp     loc_180034043
0x1800338a0  mov     eax, [rbp+0CF0h+var_700]
0x1800338a6  test    al, 2
0x1800338a8  jnz     short loc_1800338F5
0x1800338aa  test    al, 1
0x1800338ac  jnz     short loc_1800338C4
0x1800338ae  lea     rdx, aNoToken; "No token"
0x1800338b5  mov     ecx, r12d; int
0x1800338b8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800338bd  mov     esi, 800703F0h
0x1800338c2  jmp     short loc_180033928
0x1800338c4  mov     rdx, [rbp+0CF0h+var_708]; void *
0x1800338cb  lea     rcx, [rbp+0CF0h+var_D40]; this
0x1800338cf  call    ?InitializeUserName@CUserName@@AEAAJPEAX@Z; CUserName::InitializeUserName(void *)
0x1800338d4  mov     esi, eax
0x1800338d6  test    eax, eax
0x1800338d8  jns     short loc_1800338F5
0x1800338da  lea     r9, aCusernameGetus_0; "CUserName::GetUserSid"
0x1800338e1  mov     r8d, eax
0x1800338e4  lea     rdx, aInitializeuser; "InitializeUserName failed: 0x%x in %s"
0x1800338eb  mov     ecx, r12d; int
0x1800338ee  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800338f3  jmp     short loc_180033928
0x1800338f5  mov     rcx, [rbp+0CF0h+var_6F8]
0x1800338fc  mov     rcx, [rcx]; Sid
0x1800338ff  call    cs:__imp_RtlLengthSid
0x180033906  nop     dword ptr [rax+rax+00h]
0x18003390b  mov     esi, eax
0x18003390d  mov     ecx, eax; cb
0x18003390f  call    cs:__imp_CoTaskMemAlloc
0x180033916  nop     dword ptr [rax+rax+00h]
0x18003391b  mov     r13, rax
0x18003391e  test    rax, rax
0x180033921  jnz     short loc_180033998
0x180033923  mov     esi, 8007000Eh
0x180033928  mov     eax, cs:dword_1800DF020
0x18003392e  cmp     eax, 3
0x180033931  jbe     loc_180034043
0x180033937  lea     rax, aTrackcaller; "TrackCaller"
0x18003393e  mov     [rsp+0DF0h+var_D90], rax
0x180033943  mov     [rsp+0DF0h+BackTraceHash], esi
0x180033947  lea     rax, aUsernameGetuse; "UserName.GetUserSid"
0x18003394e  mov     [rsp+0DF0h+TokenHandle], rax
0x180033953  lea     rax, aWarningHresult; "Warning HResult failed"
0x18003395a  mov     qword ptr [rsp+0DF0h+pSessionId], rax
0x18003395f  lea     rax, [rsp+0DF0h+var_D90]
0x180033964  mov     [rsp+0DF0h+var_DB8], rax
0x180033969  lea     rax, [rsp+0DF0h+BackTraceHash]
0x18003396e  mov     [rsp+0DF0h+var_DC0], rax
0x180033973  lea     rax, [rsp+0DF0h+TokenHandle]
0x180033978  mov     [rsp+0DF0h+var_DC8], rax
0x18003397d  lea     rax, [rsp+0DF0h+pSessionId]
0x180033982  mov     [rsp+0DF0h+var_DD0], rax
0x180033987  lea     rdx, byte_1800C7F91
0x18003398e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180033993  jmp     loc_180034043
0x180033998  mov     r8, rsi; Size
0x18003399b  mov     rdx, [rbp+0CF0h+var_6F8]
0x1800339a2  mov     rdx, [rdx]; Src
0x1800339a5  mov     rcx, r13; void *
0x1800339a8  call    memcpy_0
0x1800339ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800339b4  mov     ecx, 648h; unsigned __int64
0x1800339b9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800339be  mov     rbx, rax
0x1800339c1  mov     [rbp+0CF0h+var_D68], rax
0x1800339c5  test    rax, rax
0x1800339c8  jz      short loc_1800339F3
0x1800339ca  lea     rdx, aCtsrpcclient; "CTSRpcClient"
0x1800339d1  mov     rcx, rax
0x1800339d4  call    ??0?$CTSObject@UIUnknown@@@@QEAA@PEBD@Z; CTSObject<IUnknown>::CTSObject<IUnknown>(char const *)
0x1800339d9  lea     rax, ??_7CTSRpcClient@CTSRpcClientTrackerMgr@@6B@; const CTSRpcClientTrackerMgr::CTSRpcClient::`vftable'
0x1800339e0  mov     [rbx], rax
0x1800339e3  mov     [rbx+638h], r14
0x1800339ea  mov     [rbx+640h], r14
0x1800339f1  jmp     short loc_1800339F6
0x1800339f3  mov     rbx, r14
0x1800339f6  mov     [rbp+0CF0h+var_D50], rbx
0x1800339fa  test    rbx, rbx
0x1800339fd  jz      loc_180033FC4
0x180033a03  mov     rax, [rbx]
0x180033a06  mov     rcx, rbx
0x180033a09  mov     rax, [rax+8]
0x180033a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a12  mov     rcx, r13; pSid
0x180033a15  call    cs:__imp_IsValidSid
0x180033a1c  nop     dword ptr [rax+rax+00h]
0x180033a21  test    eax, eax
0x180033a23  jnz     short loc_180033A39
0x180033a25  mov     esi, 80070057h
0x180033a2a  mov     r14d, esi
0x180033a2d  lea     rdx, aIsvalidsidPsid; "IsValidSid(pSid) failed: 0x%x in %s"
0x180033a34  jmp     loc_180033ACF
0x180033a39  mov     rcx, r13; pSid
0x180033a3c  call    cs:__imp_GetLengthSid
0x180033a43  nop     dword ptr [rax+rax+00h]
0x180033a48  mov     edx, eax; uBytes
0x180033a4a  mov     [rbx+640h], edx
0x180033a50  mov     ecx, 40h ; '@'; uFlags
0x180033a55  call    cs:__imp_LocalAlloc
  ... truncated ...
```
