# RpcGetRequestForWinlogon

- ea: `0x180031a40`
- end: `0x1800322e5`
- name: `RpcGetRequestForWinlogon`
- size: `2213`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180001330`
- `0x180001b90`
- `0x1800077a0`
- `0x18000c684`
- `0x18000da1c`
- `0x18000f320`
- `0x1800212cc`
- `0x180021b00`
- `0x1800248e8`
- `0x180024b00`
- `0x18002701c`
- `0x18002f3c0`
- `0x180031650`
- `0x180031680`
- `0x180031a40`
- `0x18003ffb0`
- `0x18004b7b4`
- `0x18004e850`
- `0x180058770`
- `0x18008f8c4`
- `0x18009959c`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031e9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031e9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800322a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800322a6`

## string_xrefs

- `0x180031b3c`: `ulUserToken`

## pseudocode

```c
__int64 __fastcall RpcGetRequestForWinlogon(
        __int64 a1,
        struct ISessionArbitration **a2,
        struct ISessionArbitration *a3,
        __int64 a4)
{
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  struct ISessionArbitration *v10; // r13
  struct ISessionArbitration *v11; // rdi
  const char *v12; // r8
  int SessionFromRpcClientId; // ebx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int InstanceOfSessionArbitrator; // eax
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  char *v21; // rdx
  const char *v22; // rax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // eax
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  int *v33; // rdx
  const char *v34; // rax
  HLOCAL v35; // rax
  int InstanceOfSessionManagerInternal; // eax
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  int IsVAILGuest; // eax
  int v47; // r15d
  int AllowListenersInsideArgonContainer; // eax
  int v49; // ecx
  int v50; // r8d
  int v51; // r9d
  int v52; // ecx
  int v53; // r8d
  int v54; // r9d
  int v55; // ecx
  int v56; // r8d
  int v57; // r9d
  int v58; // ecx
  int v59; // r8d
  int v60; // r9d
  const char *v62; // [rsp+50h] [rbp-79h] BYREF
  const char *v63; // [rsp+58h] [rbp-71h] BYREF
  struct ISessionArbitration *v64; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int64 ClientProcessId; // [rsp+68h] [rbp-61h] BYREF
  __int64 v66; // [rsp+70h] [rbp-59h] BYREF
  int v67; // [rsp+78h] [rbp-51h] BYREF
  int v68; // [rsp+7Ch] [rbp-4Dh] BYREF
  __int64 v69; // [rsp+80h] [rbp-49h] BYREF
  void *Src; // [rsp+88h] [rbp-41h]
  __int64 v71; // [rsp+90h] [rbp-39h]
  int v72; // [rsp+98h] [rbp-31h] BYREF
  struct ISessionManagerInternal *v73; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v74; // [rsp+A8h] [rbp-21h] BYREF
  struct ITSSession *v75; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v76; // [rsp+B8h] [rbp-11h] BYREF
  __int128 v77; // [rsp+C0h] [rbp-9h] BYREF
  __int128 v78; // [rsp+D0h] [rbp+7h] BYREF

  v73 = 0;
  v76 = 0;
  v75 = 0;
  v72 = 0;
  v68 = 0;
  v78 = 0;
  v77 = 0;
  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    v66 = (__int64)a2;
    v64 = a3;
    ClientProcessId = CRpcUtils::GetClientProcessId();
    v63 = "RpcGetRequestForWinlogon was called";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v7,
      (unsigned int)word_1800C628A,
      v8,
      v9,
      (__int64)&v63,
      (__int64)&ClientProcessId,
      (__int64)&v64,
      (__int64)&v66);
  }
  v67 = 0;
  v10 = 0;
  v71 = 0;
  v11 = 0;
  v69 = 0;
  Src = 0;
  if ( !a2 )
  {
    v12 = "pLogonHandle";
LABEL_5:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v12, "RpcGetRequestForWinlogon");
    SessionFromRpcClientId = -2147024809;
    goto LABEL_74;
  }
  if ( !a3 )
  {
    v12 = "ulUserToken";
    goto LABEL_5;
  }
  if ( !a4 )
  {
    v12 = "pRequest";
    goto LABEL_5;
  }
  v10 = a3;
  v64 = *a2;
  v11 = v64;
  *(_QWORD *)a4 = 0;
  *(_QWORD *)(a4 + 8) = 0;
  *(_DWORD *)(a4 + 16) = 0;
  if ( v11 )
  {
    if ( (unsigned int)dword_1800DF020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DF020, 0x400000000000LL) )
    {
      v62 = (const char *)a3;
      ClientProcessId = (unsigned __int64)"ArbitrationContinue";
      v63 = (const char *)a2;
      v66 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v26,
        (unsigned int)word_1800C619A,
        v27,
        v28,
        (__int64)&v66,
        (__int64)&ClientProcessId,
        (__int64)&v63,
        (__int64)&v62);
    }
  }
  else
  {
    LogArbitrationForSession(1, a3);
    if ( (unsigned int)dword_1800DF020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DF020, 0x400000000000LL) )
    {
      v63 = (const char *)a3;
      v66 = (__int64)"ArbitrationStart";
      ClientProcessId = (unsigned __int64)a2;
      v62 = (const char *)0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v14,
        (unsigned int)byte_1800C6231,
        v15,
        v16,
        (__int64)&v62,
        (__int64)&v66,
        (__int64)&ClientProcessId,
        (__int64)&v63);
    }
    InstanceOfSessionArbitrator = GetInstanceOfSessionArbitrator(0, a3, &v64);
    SessionFromRpcClientId = InstanceOfSessionArbitrator;
    if ( InstanceOfSessionArbitrator == -2147023174 )
    {
      v11 = v64;
      goto LABEL_22;
    }
    if ( InstanceOfSessionArbitrator < 0 )
    {
      v20 = dword_1800DF020;
      if ( (unsigned int)dword_1800DF020 <= 3 )
      {
LABEL_19:
        v11 = v64;
        goto LABEL_74;
      }
      v62 = "RpcGetRequestForWinlogon";
      v21 = byte_1800C61F3;
      v22 = "GetInstanceOfSessionArbitrator";
LABEL_18:
      v63 = v22;
      ClientProcessId = (unsigned __int64)"Warning HResult failed";
      LODWORD(v66) = SessionFromRpcClientId;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v20,
        (_DWORD)v21,
        v18,
        v19,
        (__int64)&ClientProcessId,
        (__int64)&v63,
        (__int64)&v66,
        (__int64)&v62);
      goto LABEL_19;
    }
    v11 = v64;
  }
  *a2 = v11;
  v29 = (*(__int64 (__fastcall **)(struct ISessionArbitration *, __int64 *, int *))(*(_QWORD *)v11 + 32LL))(
          v11,
          &v69,
          &v67);
  SessionFromRpcClientId = v29;
  if ( v29 != -2147023174 )
  {
    if ( v29 < 0 )
    {
      if ( (unsigned int)dword_1800DF020 <= 3 )
        goto LABEL_74;
      v62 = "RpcGetRequestForWinlogon";
      v33 = &dword_1800C615C;
      v34 = "pSessionArbitration->GetRequestForWinlogon";
LABEL_37:
      v63 = v34;
      ClientProcessId = (unsigned __int64)"Warning HResult failed";
      LODWORD(v66) = SessionFromRpcClientId;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v30,
        (_DWORD)v33,
        v31,
        v32,
        (__int64)&ClientProcessId,
        (__int64)&v63,
        (__int64)&v66,
        (__int64)&v62);
      goto LABEL_74;
    }
    goto LABEL_41;
  }
LABEL_22:
  if ( (unsigned int)dword_1800DF020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DF020, 0x400000000000LL) )
  {
    v63 = (const char *)0x2000000;
    v62 = "ArbitrationFailureRetry";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v23,
      (unsigned int)byte_1800C6123,
      v24,
      v25,
      (__int64)&v63,
      (__int64)&v62);
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(struct ISessionArbitration *))(*(_QWORD *)v11 + 16LL))(v11);
    v64 = 0;
    *a2 = 0;
  }
  SessionFromRpcClientId = GetInstanceOfSessionArbitrator(1, a3, &v64);
  if ( SessionFromRpcClientId < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_19;
    v62 = "RpcGetRequestForWinlogon";
    v21 = byte_1800C60E5;
    v22 = "GetInstanceOfArbitrationObject";
    goto LABEL_18;
  }
  v11 = v64;
  *a2 = v64;
  SessionFromRpcClientId = (*(__int64 (__fastcall **)(struct ISessionArbitration *, __int64 *, int *))(*(_QWORD *)v11 + 32LL))(
                             v11,
                             &v69,
                             &v67);
  if ( SessionFromRpcClientId < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_74;
    v62 = "RpcGetRequestForWinlogon";
    v33 = (int *)&byte_1800C60A7;
    v34 = "GetRequestForWinlogon";
    goto LABEL_37;
  }
LABEL_41:
  if ( HIDWORD(v69) )
  {
    v35 = LocalAlloc(0x40u, 4LL * HIDWORD(v69));
    *(_QWORD *)(a4 + 8) = v35;
    if ( !v35 )
    {
      SessionFromRpcClientId = -2147024882;
      goto LABEL_74;
    }
    memcpy_0(v35, Src, 4LL * HIDWORD(v69));
  }
  else
  {
    *(_QWORD *)(a4 + 8) = 0;
  }
  if ( (((_DWORD)v69 - 1) & 0xFFFFFFFC) == 0 && (_DWORD)v69 != 2 )
  {
    InstanceOfSessionManagerInternal = ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v73);
    SessionFromRpcClientId = InstanceOfSessionManagerInternal;
    if ( InstanceOfSessionManagerInternal < 0 )
    {
      _DbgPrintMessage(
        8,
        "GetInstanceOfSessionManager failed: 0x%x in %s",
        InstanceOfSessionManagerInternal,
        "RpcGetRequestForWinlogon");
      goto LABEL_74;
    }
    LODWORD(v66) = 0;
    (*(void (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v73 + 88LL))(v73, &v66);
    SessionFromRpcClientId = CRpcUtils::GetSessionFromRpcClientId(&v75);
    if ( SessionFromRpcClientId < 0 )
    {
      if ( (unsigned int)dword_1800DF020 > 3 )
      {
        LODWORD(v64) = SessionFromRpcClientId;
        v62 = "RpcGetRequestForWinlogon";
        v63 = "Failed to get session for session arbitrating";
        ClientProcessId = (unsigned __int64)"Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v37,
          (unsigned int)byte_1800C6065,
          v38,
          v39,
          (__int64)&ClientProcessId,
          (__int64)&v63,
          (__int64)&v64,
          (__int64)&v62);
      }
      goto LABEL_74;
    }
    SessionFromRpcClientId = (*(__int64 (__fastcall **)(struct ITSSession *, __int64 *))(*(_QWORD *)v75 + 104LL))(
                               v75,
                               &v76);
    if ( SessionFromRpcClientId < 0 )
    {
      if ( (unsigned int)dword_1800DF020 > 3 )
      {
        LODWORD(v64) = SessionFromRpcClientId;
        v62 = "RpcGetRequestForWinlogon";
        v63 = "Failed to get terminal for session arbitrating";
        ClientProcessId = (unsigned __int64)"Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v40,
          (unsigned int)byte_1800C6023,
          v41,
          v42,
          (__int64)&ClientProcessId,
          (__int64)&v63,
          (__int64)&v64,
          (__int64)&v62);
      }
      goto LABEL_74;
    }
    SessionFromRpcClientId = (*(__int64 (__fastcall **)(__int64, __int128 *, int *, int *, __int128 *))(*(_QWORD *)v76 + 136LL))(
                               v76,
                               &v78,
                               &v72,
                               &v68,
                               &v77);
    if ( SessionFromRpcClientId < 0 )
    {
      if ( (unsigned int)dword_1800DF020 > 3 )
      {
        LODWORD(v64) = SessionFromRpcClientId;
        v62 = "RpcGetRequestForWinlogon";
        v63 = "Failed to get terminal type for session arbitrating";
        ClientProcessId = (unsigned __int64)"Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v43,
          (unsigned int)byte_1800C5FE1,
          v44,
          v45,
          (__int64)&ClientProcessId,
          (__int64)&v63,
          (__int64)&v64,
          (__int64)&v62);
      }
      goto LABEL_74;
    }
    LODWORD(v64) = 0;
    IsVAILGuest = CSLQuery::IsVAILGuest((int *)&v64);
    v47 = (int)v64;
    SessionFromRpcClientId = IsVAILGuest;
    if ( IsVAILGuest < 0 )
      v47 = 0;
    AllowListenersInsideArgonContainer = CContainerHelper::GetAllowListenersInsideArgonContainer();
    if ( (_DWORD)v66 && !v47 && !AllowListenersInsideArgonContainer )
    {
      if ( v68 == 5 )
      {
        if ( (unsigned int)dword_1800DF020 > 5 )
        {
          v62 = "Terminal is RAIL in container, allowing without asking host";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v49,
            (unsigned int)byte_1800C5F99,
            v50,
            v51,
            (__int64)&v62);
        }
      }
      else
      {
        SessionFromRpcClientId = DoAskForSession();
        if ( SessionFromRpcClientId )
        {
          if ( (unsigned int)dword_1800DF020 > 2 )
          {
            v62 = "Session was denied";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              v52,
              (unsigned int)byte_1800C5FBD,
              v53,
              v54,
              (__int64)&v62);
          }
          SessionFromRpcClientId = -2147023676;
          LODWORD(v69) = 6;
        }
      }
    }
  }
  *(_DWORD *)a4 = v69;
  *(_DWORD *)(a4 + 16) = v71;
  *(_DWORD *)(a4 + 4) = HIDWORD(v69);
  if ( v67 )
  {
    LogArbitrationForSession(0, a3);
    NotifySessionArbitrationCompleted(a3, (struct _TS_WINLOGON_REQUEST *)a4);
  }
  if ( SessionFromRpcClientId >= 0 )
  {
    if ( (unsigned int)dword_1800DF020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DF020, 0x400000000000LL) )
    {
      LODWORD(v66) = v67;
      v63 = "ArbitrationEnd";
      v74 = (__int64)a3;
      v62 = (const char *)a2;
      LODWORD(v64) = SessionFromRpcClientId;
      ClientProcessId = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v58,
        (unsigned int)&byte_1800C5EC7,
        v59,
        v60,
        (__int64)&ClientProcessId,
        (__int64)&v63,
        (__int64)&v64,
        (__int64)&v66,
        (__int64)&v62,
        (__int64)&v74);
    }
LABEL_82:
    if ( !v67 )
      goto LABEL_85;
    goto LABEL_83;
  }
LABEL_74:
  if ( (unsigned int)dword_1800DF020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DF020, 0x400000000000LL) )
  {
    LODWORD(v66) = v67;
    ClientProcessId = (unsigned __int64)"ArbitrationFailure";
    v62 = (const char *)v10;
    v63 = (const char *)a2;
    LODWORD(v64) = SessionFromRpcClientId;
    v74 = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v55,
      (unsigned int)&unk_1800C5F30,
      v56,
      v57,
      (__int64)&v74,
      (__int64)&ClientProcessId,
      (__int64)&v64,
      (__int64)&v66,
      (__int64)&v63,
      (__int64)&v62);
  }
  if ( SessionFromRpcClientId >= 0 )
    goto LABEL_82;
LABEL_83:
  if ( v11 )
  {
    (*(void (__fastcall **)(struct ISessionArbitration *))(*(_QWORD *)v11 + 16LL))(v11);
    *a2 = 0;
  }
LABEL_85:
  if ( Src )
    CoTaskMemFree(Src);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v73);
  return (unsigned int)SessionFromRpcClientId;
}

```

## disassembly

```asm
0x180031a40  mov     [rsp-8+arg_0], rbx
0x180031a45  push    rbp
0x180031a46  push    rsi
0x180031a47  push    rdi
0x180031a48  push    r12
0x180031a4a  push    r13
0x180031a4c  push    r14
0x180031a4e  push    r15
0x180031a50  lea     rbp, [rsp-27h]
0x180031a55  sub     rsp, 0F0h
0x180031a5c  mov     rax, cs:__security_cookie
0x180031a63  xor     rax, rsp
0x180031a66  mov     [rbp+57h+var_40], rax
0x180031a6a  mov     eax, cs:dword_1800DF020
0x180031a70  xor     r15d, r15d
0x180031a73  mov     [rbp+57h+var_80], r15
0x180031a77  xorps   xmm0, xmm0
0x180031a7a  mov     [rbp+57h+var_68], r15
0x180031a7e  mov     rsi, r9
0x180031a81  mov     [rbp+57h+var_70], r15
0x180031a85  mov     r14, r8
0x180031a88  mov     [rbp+57h+var_88], r15d
0x180031a8c  mov     r12, rdx
0x180031a8f  mov     [rbp+57h+var_A4], r15d
0x180031a93  movups  [rbp+57h+var_50], xmm0
0x180031a97  movups  [rbp+57h+var_60], xmm0
0x180031a9b  cmp     eax, 5
0x180031a9e  jbe     short loc_180031AEE
0x180031aa0  mov     [rbp+57h+var_B0], rdx
0x180031aa4  mov     [rbp+57h+var_C0], r8
0x180031aa8  call    ?GetClientProcessId@CRpcUtils@@SAKXZ; CRpcUtils::GetClientProcessId(void)
0x180031aad  mov     eax, eax
0x180031aaf  lea     rdx, word_1800C628A
0x180031ab6  mov     [rbp+57h+var_B8], rax
0x180031aba  lea     rax, aRpcgetrequestf_0; "RpcGetRequestForWinlogon was called"
0x180031ac1  mov     [rbp+57h+var_C8], rax
0x180031ac5  lea     rax, [rbp+57h+var_B0]
0x180031ac9  mov     [rsp+120h+var_E8], rax
0x180031ace  lea     rax, [rbp+57h+var_C0]
0x180031ad2  mov     [rsp+120h+var_F0], rax
0x180031ad7  lea     rax, [rbp+57h+var_B8]
0x180031adb  mov     [rsp+120h+var_F8], rax
0x180031ae0  lea     rax, [rbp+57h+var_C8]
0x180031ae4  mov     [rsp+120h+var_100], rax
0x180031ae9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180031aee  mov     [rbp+57h+var_A8], r15d
0x180031af2  mov     r13, r15
0x180031af5  mov     [rbp+57h+var_90], r15
0x180031af9  mov     rdi, r15
0x180031afc  mov     [rbp+57h+var_A0], r15
0x180031b00  mov     ebx, 2000000h
0x180031b05  mov     [rbp+57h+Src], r15
0x180031b09  test    r12, r12
0x180031b0c  jnz     short loc_180031B37
0x180031b0e  lea     r8, aPlogonhandle; "pLogonHandle"
0x180031b15  lea     r9, aRpcgetrequestf; "RpcGetRequestForWinlogon"
0x180031b1c  mov     ecx, 8; int
0x180031b21  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180031b28  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031b2d  mov     ebx, 80070057h
0x180031b32  jmp     loc_180032154
0x180031b37  test    r14, r14
0x180031b3a  jnz     short loc_180031B45
0x180031b3c  lea     r8, aUlusertoken; "ulUserToken"
0x180031b43  jmp     short loc_180031B15
0x180031b45  test    rsi, rsi
0x180031b48  jnz     short loc_180031B53
0x180031b4a  lea     r8, aPrequest; "pRequest"
0x180031b51  jmp     short loc_180031B15
0x180031b53  mov     rdi, [r12]
0x180031b57  mov     r13, r14
0x180031b5a  mov     [rbp+57h+var_C0], rdi
0x180031b5e  mov     [rsi], r15
0x180031b61  mov     [rsi+8], r15
0x180031b65  mov     [rsi+10h], r15d
0x180031b69  test    rdi, rdi
0x180031b6c  jnz     loc_180031D33
0x180031b72  mov     rdx, r14; void *
0x180031b75  lea     ecx, [rdi+1]; int
0x180031b78  call    ?LogArbitrationForSession@@YAJHPEAX@Z; LogArbitrationForSession(int,void *)
0x180031b7d  mov     eax, cs:dword_1800DF020
0x180031b83  cmp     eax, 5
0x180031b86  jbe     short loc_180031BE9
0x180031b88  mov     rdx, 400000000000h
0x180031b92  lea     rcx, dword_1800DF020
0x180031b99  call    _tlgKeywordOn
0x180031b9e  test    al, al
0x180031ba0  jz      short loc_180031BE9
0x180031ba2  lea     rax, aArbitrationsta; "ArbitrationStart"
0x180031ba9  mov     [rbp+57h+var_C8], r14
0x180031bad  mov     [rbp+57h+var_B0], rax
0x180031bb1  lea     rdx, byte_1800C6231
0x180031bb8  lea     rax, [rbp+57h+var_C8]
0x180031bbc  mov     [rbp+57h+var_B8], r12
0x180031bc0  mov     [rsp+120h+var_E8], rax
0x180031bc5  lea     rax, [rbp+57h+var_B8]
0x180031bc9  mov     [rsp+120h+var_F0], rax
0x180031bce  lea     rax, [rbp+57h+var_B0]
0x180031bd2  mov     [rsp+120h+var_F8], rax
0x180031bd7  lea     rax, [rbp+57h+var_D0]
0x180031bdb  mov     [rsp+120h+var_100], rax
0x180031be0  mov     [rbp+57h+var_D0], rbx
0x180031be4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180031be9  lea     r8, [rbp+57h+var_C0]; struct ISessionArbitration **
0x180031bed  mov     rdx, r14; void *
0x180031bf0  xor     ecx, ecx; int
0x180031bf2  call    ?GetInstanceOfSessionArbitrator@@YAJHPEAXPEAPEAUISessionArbitration@@@Z; GetInstanceOfSessionArbitrator(int,void *,ISessionArbitration * *)
0x180031bf7  mov     ebx, eax
0x180031bf9  cmp     eax, 800706BAh
0x180031bfe  jz      short loc_180031C75
0x180031c00  test    eax, eax
0x180031c02  jns     short loc_180031C6C
0x180031c04  mov     ecx, cs:dword_1800DF020
0x180031c0a  cmp     ecx, 3
0x180031c0d  jbe     short loc_180031C63
0x180031c0f  lea     rax, aRpcgetrequestf; "RpcGetRequestForWinlogon"
0x180031c16  mov     [rbp+57h+var_D0], rax
0x180031c1a  lea     rdx, byte_1800C61F3
0x180031c21  lea     rax, aGetinstanceofs_9; "GetInstanceOfSessionArbitrator"
0x180031c28  mov     [rbp+57h+var_C8], rax
0x180031c2c  lea     rax, aWarningHresult; "Warning HResult failed"
0x180031c33  mov     [rbp+57h+var_B8], rax
0x180031c37  lea     rax, [rbp+57h+var_D0]
0x180031c3b  mov     [rsp+120h+var_E8], rax
0x180031c40  lea     rax, [rbp+57h+var_B0]
0x180031c44  mov     [rsp+120h+var_F0], rax
0x180031c49  lea     rax, [rbp+57h+var_C8]
0x180031c4d  mov     [rsp+120h+var_F8], rax
0x180031c52  lea     rax, [rbp+57h+var_B8]
0x180031c56  mov     [rsp+120h+var_100], rax
0x180031c5b  mov     dword ptr [rbp+57h+var_B0], ebx
0x180031c5e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180031c63  mov     rdi, [rbp+57h+var_C0]
0x180031c67  jmp     loc_180032154
0x180031c6c  mov     rdi, [rbp+57h+var_C0]
0x180031c70  jmp     loc_180031D9F
0x180031c75  mov     rdi, [rbp+57h+var_C0]
0x180031c79  mov     eax, cs:dword_1800DF020
0x180031c7f  cmp     eax, 5
0x180031c82  jbe     short loc_180031CCF
0x180031c84  mov     rdx, 400000000000h
0x180031c8e  lea     rcx, dword_1800DF020
0x180031c95  call    _tlgKeywordOn
0x180031c9a  test    al, al
0x180031c9c  jz      short loc_180031CCF
0x180031c9e  lea     rax, aArbitrationfai_0; "ArbitrationFailureRetry"
0x180031ca5  mov     [rbp+57h+var_C8], 2000000h
0x180031cad  mov     [rbp+57h+var_D0], rax
0x180031cb1  lea     rdx, byte_1800C6123
0x180031cb8  lea     rax, [rbp+57h+var_D0]
0x180031cbc  mov     [rsp+120h+var_F8], rax
0x180031cc1  lea     rax, [rbp+57h+var_C8]
0x180031cc5  mov     [rsp+120h+var_100], rax
0x180031cca  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x180031ccf  test    rdi, rdi
0x180031cd2  jz      short loc_180031CEB
0x180031cd4  mov     rax, [rdi]
0x180031cd7  mov     rcx, rdi
0x180031cda  mov     rax, [rax+10h]
0x180031cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ce3  mov     [rbp+57h+var_C0], r15
0x180031ce7  mov     [r12], r15
0x180031ceb  lea     r8, [rbp+57h+var_C0]; struct ISessionArbitration **
0x180031cef  mov     rdx, r14; void *
0x180031cf2  mov     ecx, 1; int
0x180031cf7  call    ?GetInstanceOfSessionArbitrator@@YAJHPEAXPEAPEAUISessionArbitration@@@Z; GetInstanceOfSessionArbitrator(int,void *,ISessionArbitration * *)
0x180031cfc  mov     ebx, eax
0x180031cfe  test    eax, eax
0x180031d00  jns     loc_180031E37
0x180031d06  mov     eax, cs:dword_1800DF020
0x180031d0c  cmp     eax, 3
0x180031d0f  jbe     loc_180031C63
0x180031d15  lea     rax, aRpcgetrequestf; "RpcGetRequestForWinlogon"
0x180031d1c  mov     [rbp+57h+var_D0], rax
0x180031d20  lea     rdx, byte_1800C60E5
0x180031d27  lea     rax, aGetinstanceofa; "GetInstanceOfArbitrationObject"
0x180031d2e  jmp     loc_180031C28
0x180031d33  mov     eax, cs:dword_1800DF020
0x180031d39  cmp     eax, 5
0x180031d3c  jbe     short loc_180031D9F
0x180031d3e  mov     rdx, 400000000000h
0x180031d48  lea     rcx, dword_1800DF020
0x180031d4f  call    _tlgKeywordOn
0x180031d54  test    al, al
0x180031d56  jz      short loc_180031D9F
0x180031d58  lea     rax, aArbitrationcon; "ArbitrationContinue"
0x180031d5f  mov     [rbp+57h+var_D0], r14
0x180031d63  mov     [rbp+57h+var_B8], rax
0x180031d67  lea     rdx, word_1800C619A
0x180031d6e  lea     rax, [rbp+57h+var_D0]
0x180031d72  mov     [rbp+57h+var_C8], r12
0x180031d76  mov     [rsp+120h+var_E8], rax
0x180031d7b  lea     rax, [rbp+57h+var_C8]
0x180031d7f  mov     [rsp+120h+var_F0], rax
0x180031d84  lea     rax, [rbp+57h+var_B8]
0x180031d88  mov     [rsp+120h+var_F8], rax
0x180031d8d  lea     rax, [rbp+57h+var_B0]
0x180031d91  mov     [rsp+120h+var_100], rax
0x180031d96  mov     [rbp+57h+var_B0], rbx
0x180031d9a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180031d9f  mov     [r12], rdi
0x180031da3  lea     r8, [rbp+57h+var_A8]
0x180031da7  mov     rax, [rdi]
0x180031daa  lea     rdx, [rbp+57h+var_A0]
0x180031dae  mov     rcx, rdi
0x180031db1  mov     rax, [rax+20h]
0x180031db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031dba  mov     ebx, eax
0x180031dbc  cmp     eax, 800706BAh
0x180031dc1  jz      loc_180031C79
0x180031dc7  test    eax, eax
0x180031dc9  jns     loc_180031E89
0x180031dcf  mov     eax, cs:dword_1800DF020
0x180031dd5  cmp     eax, 3
0x180031dd8  jbe     loc_180032154
0x180031dde  lea     rax, aRpcgetrequestf; "RpcGetRequestForWinlogon"
0x180031de5  mov     [rbp+57h+var_D0], rax
0x180031de9  lea     rdx, dword_1800C615C
0x180031df0  lea     rax, aPsessionarbitr; "pSessionArbitration->GetRequestForWinlo"...
0x180031df7  mov     [rbp+57h+var_C8], rax
0x180031dfb  lea     rax, aWarningHresult; "Warning HResult failed"
0x180031e02  mov     [rbp+57h+var_B8], rax
0x180031e06  lea     rax, [rbp+57h+var_D0]
0x180031e0a  mov     [rsp+120h+var_E8], rax
0x180031e0f  lea     rax, [rbp+57h+var_B0]
0x180031e13  mov     dword ptr [rbp+57h+var_B0], ebx
0x180031e16  mov     [rsp+120h+var_F0], rax
0x180031e1b  lea     rax, [rbp+57h+var_C8]
0x180031e1f  mov     [rsp+120h+var_F8], rax
0x180031e24  lea     rax, [rbp+57h+var_B8]
0x180031e28  mov     [rsp+120h+var_100], rax
0x180031e2d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180031e32  jmp     loc_180032154
0x180031e37  mov     rdi, [rbp+57h+var_C0]
0x180031e3b  lea     r8, [rbp+57h+var_A8]
0x180031e3f  mov     [r12], rdi
0x180031e43  lea     rdx, [rbp+57h+var_A0]
0x180031e47  mov     rcx, rdi
0x180031e4a  mov     rax, [rdi]
0x180031e4d  mov     rax, [rax+20h]
0x180031e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e56  mov     ebx, eax
0x180031e58  test    eax, eax
0x180031e5a  jns     short loc_180031E89
0x180031e5c  mov     eax, cs:dword_1800DF020
0x180031e62  cmp     eax, 3
0x180031e65  jbe     loc_180032154
0x180031e6b  lea     rax, aRpcgetrequestf; "RpcGetRequestForWinlogon"
0x180031e72  mov     [rbp+57h+var_D0], rax
0x180031e76  lea     rdx, byte_1800C60A7
0x180031e7d  lea     rax, aGetrequestforw; "GetRequestForWinlogon"
0x180031e84  jmp     loc_180031DF7
0x180031e89  mov     eax, dword ptr [rbp+57h+var_A0+4]
0x180031e8c  test    eax, eax
0x180031e8e  jz      short loc_180031ED0
0x180031e90  mov     edx, eax
0x180031e92  mov     ecx, 40h ; '@'; uFlags
0x180031e97  shl     rdx, 2; uBytes
0x180031e9b  call    cs:__imp_LocalAlloc
0x180031ea2  nop     dword ptr [rax+rax+00h]
0x180031ea7  mov     [rsi+8], rax
0x180031eab  test    rax, rax
0x180031eae  jnz     short loc_180031EBA
0x180031eb0  mov     ebx, 8007000Eh
0x180031eb5  jmp     loc_180032154
0x180031eba  mov     r8d, dword ptr [rbp+57h+var_A0+4]
0x180031ebe  mov     rcx, rax; void *
0x180031ec1  mov     rdx, [rbp+57h+Src]; Src
0x180031ec5  shl     r8, 2; Size
0x180031ec9  call    memcpy_0
0x180031ece  jmp     short loc_180031ED4
0x180031ed0  mov     [rsi+8], r15
0x180031ed4  mov     ecx, dword ptr [rbp+57h+var_A0]
0x180031ed7  lea     eax, [rcx-1]
0x180031eda  test    eax, 0FFFFFFFCh
0x180031edf  jnz     loc_180032120
0x180031ee5  cmp     ecx, 2
0x180031ee8  jz      loc_180032120
0x180031eee  lea     rcx, [rbp+57h+var_80]; struct ISessionManagerInternal **
0x180031ef2  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x180031ef7  mov     ebx, eax
0x180031ef9  test    eax, eax
0x180031efb  jns     short loc_180031F1D
0x180031efd  lea     r9, aRpcgetrequestf; "RpcGetRequestForWinlogon"
0x180031f04  mov     r8d, eax
0x180031f07  lea     rdx, aGetinstanceofs; "GetInstanceOfSessionManager failed: 0x%"...
0x180031f0e  mov     ecx, 8; int
0x180031f13  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031f18  jmp     loc_180032154
0x180031f1d  mov     rcx, [rbp+57h+var_80]
0x180031f21  lea     rdx, [rbp+57h+var_B0]
0x180031f25  mov     dword ptr [rbp+57h+var_B0], r15d
0x180031f29  mov     rax, [rcx]
0x180031f2c  mov     rax, [rax+58h]
0x180031f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f35  lea     rcx, [rbp+57h+var_70]; struct ITSSession **
0x180031f39  call    ?GetSessionFromRpcClientId@CRpcUtils@@SAJPEAPEAUITSSession@@@Z; CRpcUtils::GetSessionFromRpcClientId(ITSSession * *)
0x180031f3e  mov     ebx, eax
0x180031f40  test    eax, eax
0x180031f42  jns     short loc_180031F90
  ... truncated ...
```
