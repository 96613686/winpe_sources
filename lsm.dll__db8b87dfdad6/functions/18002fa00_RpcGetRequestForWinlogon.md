# RpcGetRequestForWinlogon

- ea: `0x18002fa00`
- end: `0x180030298`
- name: `RpcGetRequestForWinlogon`
- size: `2200`
- prototype: `__int64 __fastcall(__int64, struct ISessionArbitration **, struct ISessionArbitration *, __int64)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180001330`
- `0x180001b80`
- `0x1800074c0`
- `0x180008f64`
- `0x180014ff0`
- `0x180015ef8`
- `0x18001eecc`
- `0x18001f6fc`
- `0x180022a04`
- `0x180022c4c`
- `0x180025070`
- `0x18002d3b4`
- `0x18002f624`
- `0x18002f650`
- `0x18002fa00`
- `0x18003d87c`
- `0x1800485b8`
- `0x18004b460`
- `0x180054fd0`
- `0x18008ab2c`
- `0x18009404c`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fe5b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fe5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030260`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030260`

## string_xrefs

- `0x18002fafc`: `ulUserToken`

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
  unsigned int AllowListenersInsideArgonContainer; // eax
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
  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    v66 = (__int64)a2;
    v64 = a3;
    ClientProcessId = CRpcUtils::GetClientProcessId();
    v63 = "RpcGetRequestForWinlogon was called";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v7,
      (unsigned int)word_1800C1102,
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
    if ( (unsigned int)dword_1800DA020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DA020, 0x400000000000LL) )
    {
      v62 = (const char *)a3;
      ClientProcessId = (unsigned __int64)"ArbitrationContinue";
      v63 = (const char *)a2;
      v66 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v26,
        (unsigned int)word_1800C1012,
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
    if ( (unsigned int)dword_1800DA020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DA020, 0x400000000000LL) )
    {
      v63 = (const char *)a3;
      v66 = (__int64)"ArbitrationStart";
      ClientProcessId = (unsigned __int64)a2;
      v62 = (const char *)0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v14,
        (unsigned int)byte_1800C10A9,
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
      v20 = dword_1800DA020;
      if ( (unsigned int)dword_1800DA020 <= 3 )
      {
LABEL_19:
        v11 = v64;
        goto LABEL_74;
      }
      v62 = "RpcGetRequestForWinlogon";
      v21 = byte_1800C106B;
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
      if ( (unsigned int)dword_1800DA020 <= 3 )
        goto LABEL_74;
      v62 = "RpcGetRequestForWinlogon";
      v33 = &dword_1800C0FD4;
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
  if ( (unsigned int)dword_1800DA020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DA020, 0x400000000000LL) )
  {
    v63 = (const char *)0x2000000;
    v62 = "ArbitrationFailureRetry";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v23,
      (unsigned int)byte_1800C0F9B,
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
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_19;
    v62 = "RpcGetRequestForWinlogon";
    v21 = byte_1800C0F5D;
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
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_74;
    v62 = "RpcGetRequestForWinlogon";
    v33 = (int *)&byte_1800C0F1F;
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
      if ( (unsigned int)dword_1800DA020 > 3 )
      {
        LODWORD(v64) = SessionFromRpcClientId;
        v62 = "RpcGetRequestForWinlogon";
        v63 = "Failed to get session for session arbitrating";
        ClientProcessId = (unsigned __int64)"Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v37,
          (unsigned int)byte_1800C0EDD,
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
      if ( (unsigned int)dword_1800DA020 > 3 )
      {
        LODWORD(v64) = SessionFromRpcClientId;
        v62 = "RpcGetRequestForWinlogon";
        v63 = "Failed to get terminal for session arbitrating";
        ClientProcessId = (unsigned __int64)"Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v40,
          (unsigned int)byte_1800C0E9B,
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
      if ( (unsigned int)dword_1800DA020 > 3 )
      {
        LODWORD(v64) = SessionFromRpcClientId;
        v62 = "RpcGetRequestForWinlogon";
        v63 = "Failed to get terminal type for session arbitrating";
        ClientProcessId = (unsigned __int64)"Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v43,
          (unsigned int)byte_1800C0E59,
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
        if ( (unsigned int)dword_1800DA020 > 5 )
        {
          v62 = "Terminal is RAIL in container, allowing without asking host";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v49,
            (unsigned int)byte_1800C0E11,
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
          if ( (unsigned int)dword_1800DA020 > 2 )
          {
            v62 = "Session was denied";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              v52,
              (unsigned int)byte_1800C0E35,
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
    if ( (unsigned int)dword_1800DA020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DA020, 0x400000000000LL) )
    {
      LODWORD(v66) = v67;
      v63 = "ArbitrationEnd";
      v74 = (__int64)a3;
      v62 = (const char *)a2;
      LODWORD(v64) = SessionFromRpcClientId;
      ClientProcessId = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v58,
        (unsigned int)&byte_1800C0D3F,
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
  if ( (unsigned int)dword_1800DA020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DA020, 0x400000000000LL) )
  {
    LODWORD(v66) = v67;
    ClientProcessId = (unsigned __int64)"ArbitrationFailure";
    v62 = (const char *)v10;
    v63 = (const char *)a2;
    LODWORD(v64) = SessionFromRpcClientId;
    v74 = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v55,
      (unsigned int)&unk_1800C0DA8,
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
0x18002fa00  mov     [rsp-8+arg_0], rbx
0x18002fa05  push    rbp
0x18002fa06  push    rsi
0x18002fa07  push    rdi
0x18002fa08  push    r12
0x18002fa0a  push    r13
0x18002fa0c  push    r14
0x18002fa0e  push    r15
0x18002fa10  lea     rbp, [rsp-27h]
0x18002fa15  sub     rsp, 0F0h
0x18002fa1c  mov     rax, cs:__security_cookie
0x18002fa23  xor     rax, rsp
0x18002fa26  mov     [rbp+57h+var_40], rax
0x18002fa2a  mov     eax, cs:dword_1800DA020
0x18002fa30  xor     r15d, r15d
0x18002fa33  mov     [rbp+57h+var_80], r15
0x18002fa37  xorps   xmm0, xmm0
0x18002fa3a  mov     [rbp+57h+var_68], r15
0x18002fa3e  mov     rsi, r9
0x18002fa41  mov     [rbp+57h+var_70], r15
0x18002fa45  mov     r14, r8
0x18002fa48  mov     [rbp+57h+var_88], r15d
0x18002fa4c  mov     r12, rdx
0x18002fa4f  mov     [rbp+57h+var_A4], r15d
0x18002fa53  movups  [rbp+57h+var_50], xmm0
0x18002fa57  movups  [rbp+57h+var_60], xmm0
0x18002fa5b  cmp     eax, 5
0x18002fa5e  jbe     short loc_18002FAAE
0x18002fa60  mov     [rbp+57h+var_B0], rdx
0x18002fa64  mov     [rbp+57h+var_C0], r8
0x18002fa68  call    ?GetClientProcessId@CRpcUtils@@SAKXZ; CRpcUtils::GetClientProcessId(void)
0x18002fa6d  mov     eax, eax
0x18002fa6f  lea     rdx, word_1800C1102
0x18002fa76  mov     [rbp+57h+var_B8], rax
0x18002fa7a  lea     rax, aRpcgetrequestf_0; "RpcGetRequestForWinlogon was called"
0x18002fa81  mov     [rbp+57h+var_C8], rax
0x18002fa85  lea     rax, [rbp+57h+var_B0]
0x18002fa89  mov     [rsp+120h+var_E8], rax
0x18002fa8e  lea     rax, [rbp+57h+var_C0]
0x18002fa92  mov     [rsp+120h+var_F0], rax
0x18002fa97  lea     rax, [rbp+57h+var_B8]
0x18002fa9b  mov     [rsp+120h+var_F8], rax
0x18002faa0  lea     rax, [rbp+57h+var_C8]
0x18002faa4  mov     [rsp+120h+var_100], rax
0x18002faa9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18002faae  mov     [rbp+57h+var_A8], r15d
0x18002fab2  mov     r13, r15
0x18002fab5  mov     [rbp+57h+var_90], r15
0x18002fab9  mov     rdi, r15
0x18002fabc  mov     [rbp+57h+var_A0], r15
0x18002fac0  mov     ebx, 2000000h
0x18002fac5  mov     [rbp+57h+Src], r15
0x18002fac9  test    r12, r12
0x18002facc  jnz     short loc_18002FAF7
0x18002face  lea     r8, aPlogonhandle; "pLogonHandle"
0x18002fad5  lea     r9, aRpcgetrequestf; "RpcGetRequestForWinlogon"
0x18002fadc  mov     ecx, 8; int
0x18002fae1  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18002fae8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002faed  mov     ebx, 80070057h
0x18002faf2  jmp     loc_18003010E
0x18002faf7  test    r14, r14
0x18002fafa  jnz     short loc_18002FB05
0x18002fafc  lea     r8, aUlusertoken; "ulUserToken"
0x18002fb03  jmp     short loc_18002FAD5
0x18002fb05  test    rsi, rsi
0x18002fb08  jnz     short loc_18002FB13
0x18002fb0a  lea     r8, aPrequest; "pRequest"
0x18002fb11  jmp     short loc_18002FAD5
0x18002fb13  mov     rdi, [r12]
0x18002fb17  mov     r13, r14
0x18002fb1a  mov     [rbp+57h+var_C0], rdi
0x18002fb1e  mov     [rsi], r15
0x18002fb21  mov     [rsi+8], r15
0x18002fb25  mov     [rsi+10h], r15d
0x18002fb29  test    rdi, rdi
0x18002fb2c  jnz     loc_18002FCF3
0x18002fb32  mov     rdx, r14; void *
0x18002fb35  lea     ecx, [rdi+1]; int
0x18002fb38  call    ?LogArbitrationForSession@@YAJHPEAX@Z; LogArbitrationForSession(int,void *)
0x18002fb3d  mov     eax, cs:dword_1800DA020
0x18002fb43  cmp     eax, 5
0x18002fb46  jbe     short loc_18002FBA9
0x18002fb48  mov     rdx, 400000000000h
0x18002fb52  lea     rcx, dword_1800DA020
0x18002fb59  call    _tlgKeywordOn
0x18002fb5e  test    al, al
0x18002fb60  jz      short loc_18002FBA9
0x18002fb62  lea     rax, aArbitrationsta; "ArbitrationStart"
0x18002fb69  mov     [rbp+57h+var_C8], r14
0x18002fb6d  mov     [rbp+57h+var_B0], rax
0x18002fb71  lea     rdx, byte_1800C10A9
0x18002fb78  lea     rax, [rbp+57h+var_C8]
0x18002fb7c  mov     [rbp+57h+var_B8], r12
0x18002fb80  mov     [rsp+120h+var_E8], rax
0x18002fb85  lea     rax, [rbp+57h+var_B8]
0x18002fb89  mov     [rsp+120h+var_F0], rax
0x18002fb8e  lea     rax, [rbp+57h+var_B0]
0x18002fb92  mov     [rsp+120h+var_F8], rax
0x18002fb97  lea     rax, [rbp+57h+var_D0]
0x18002fb9b  mov     [rsp+120h+var_100], rax
0x18002fba0  mov     [rbp+57h+var_D0], rbx
0x18002fba4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18002fba9  lea     r8, [rbp+57h+var_C0]; struct ISessionArbitration **
0x18002fbad  mov     rdx, r14; void *
0x18002fbb0  xor     ecx, ecx; int
0x18002fbb2  call    ?GetInstanceOfSessionArbitrator@@YAJHPEAXPEAPEAUISessionArbitration@@@Z; GetInstanceOfSessionArbitrator(int,void *,ISessionArbitration * *)
0x18002fbb7  mov     ebx, eax
0x18002fbb9  cmp     eax, 800706BAh
0x18002fbbe  jz      short loc_18002FC35
0x18002fbc0  test    eax, eax
0x18002fbc2  jns     short loc_18002FC2C
0x18002fbc4  mov     ecx, cs:dword_1800DA020
0x18002fbca  cmp     ecx, 3
0x18002fbcd  jbe     short loc_18002FC23
0x18002fbcf  lea     rax, aRpcgetrequestf; "RpcGetRequestForWinlogon"
0x18002fbd6  mov     [rbp+57h+var_D0], rax
0x18002fbda  lea     rdx, byte_1800C106B
0x18002fbe1  lea     rax, aGetinstanceofs_9; "GetInstanceOfSessionArbitrator"
0x18002fbe8  mov     [rbp+57h+var_C8], rax
0x18002fbec  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002fbf3  mov     [rbp+57h+var_B8], rax
0x18002fbf7  lea     rax, [rbp+57h+var_D0]
0x18002fbfb  mov     [rsp+120h+var_E8], rax
0x18002fc00  lea     rax, [rbp+57h+var_B0]
0x18002fc04  mov     [rsp+120h+var_F0], rax
0x18002fc09  lea     rax, [rbp+57h+var_C8]
0x18002fc0d  mov     [rsp+120h+var_F8], rax
0x18002fc12  lea     rax, [rbp+57h+var_B8]
0x18002fc16  mov     [rsp+120h+var_100], rax
0x18002fc1b  mov     dword ptr [rbp+57h+var_B0], ebx
0x18002fc1e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002fc23  mov     rdi, [rbp+57h+var_C0]
0x18002fc27  jmp     loc_18003010E
0x18002fc2c  mov     rdi, [rbp+57h+var_C0]
0x18002fc30  jmp     loc_18002FD5F
0x18002fc35  mov     rdi, [rbp+57h+var_C0]
0x18002fc39  mov     eax, cs:dword_1800DA020
0x18002fc3f  cmp     eax, 5
0x18002fc42  jbe     short loc_18002FC8F
0x18002fc44  mov     rdx, 400000000000h
0x18002fc4e  lea     rcx, dword_1800DA020
0x18002fc55  call    _tlgKeywordOn
0x18002fc5a  test    al, al
0x18002fc5c  jz      short loc_18002FC8F
0x18002fc5e  lea     rax, aArbitrationfai_0; "ArbitrationFailureRetry"
0x18002fc65  mov     [rbp+57h+var_C8], 2000000h
0x18002fc6d  mov     [rbp+57h+var_D0], rax
0x18002fc71  lea     rdx, byte_1800C0F9B
0x18002fc78  lea     rax, [rbp+57h+var_D0]
0x18002fc7c  mov     [rsp+120h+var_F8], rax
0x18002fc81  lea     rax, [rbp+57h+var_C8]
0x18002fc85  mov     [rsp+120h+var_100], rax
0x18002fc8a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x18002fc8f  test    rdi, rdi
0x18002fc92  jz      short loc_18002FCAB
0x18002fc94  mov     rax, [rdi]
0x18002fc97  mov     rcx, rdi
0x18002fc9a  mov     rax, [rax+10h]
0x18002fc9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fca3  mov     [rbp+57h+var_C0], r15
0x18002fca7  mov     [r12], r15
0x18002fcab  lea     r8, [rbp+57h+var_C0]; struct ISessionArbitration **
0x18002fcaf  mov     rdx, r14; void *
0x18002fcb2  mov     ecx, 1; int
0x18002fcb7  call    ?GetInstanceOfSessionArbitrator@@YAJHPEAXPEAPEAUISessionArbitration@@@Z; GetInstanceOfSessionArbitrator(int,void *,ISessionArbitration * *)
0x18002fcbc  mov     ebx, eax
0x18002fcbe  test    eax, eax
0x18002fcc0  jns     loc_18002FDF7
0x18002fcc6  mov     eax, cs:dword_1800DA020
0x18002fccc  cmp     eax, 3
0x18002fccf  jbe     loc_18002FC23
0x18002fcd5  lea     rax, aRpcgetrequestf; "RpcGetRequestForWinlogon"
0x18002fcdc  mov     [rbp+57h+var_D0], rax
0x18002fce0  lea     rdx, byte_1800C0F5D
0x18002fce7  lea     rax, aGetinstanceofa; "GetInstanceOfArbitrationObject"
0x18002fcee  jmp     loc_18002FBE8
0x18002fcf3  mov     eax, cs:dword_1800DA020
0x18002fcf9  cmp     eax, 5
0x18002fcfc  jbe     short loc_18002FD5F
0x18002fcfe  mov     rdx, 400000000000h
0x18002fd08  lea     rcx, dword_1800DA020
0x18002fd0f  call    _tlgKeywordOn
0x18002fd14  test    al, al
0x18002fd16  jz      short loc_18002FD5F
0x18002fd18  lea     rax, aArbitrationcon; "ArbitrationContinue"
0x18002fd1f  mov     [rbp+57h+var_D0], r14
0x18002fd23  mov     [rbp+57h+var_B8], rax
0x18002fd27  lea     rdx, word_1800C1012
0x18002fd2e  lea     rax, [rbp+57h+var_D0]
0x18002fd32  mov     [rbp+57h+var_C8], r12
0x18002fd36  mov     [rsp+120h+var_E8], rax
0x18002fd3b  lea     rax, [rbp+57h+var_C8]
0x18002fd3f  mov     [rsp+120h+var_F0], rax
0x18002fd44  lea     rax, [rbp+57h+var_B8]
0x18002fd48  mov     [rsp+120h+var_F8], rax
0x18002fd4d  lea     rax, [rbp+57h+var_B0]
0x18002fd51  mov     [rsp+120h+var_100], rax
0x18002fd56  mov     [rbp+57h+var_B0], rbx
0x18002fd5a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18002fd5f  mov     [r12], rdi
0x18002fd63  lea     r8, [rbp+57h+var_A8]
0x18002fd67  mov     rax, [rdi]
0x18002fd6a  lea     rdx, [rbp+57h+var_A0]
0x18002fd6e  mov     rcx, rdi
0x18002fd71  mov     rax, [rax+20h]
0x18002fd75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd7a  mov     ebx, eax
0x18002fd7c  cmp     eax, 800706BAh
0x18002fd81  jz      loc_18002FC39
0x18002fd87  test    eax, eax
0x18002fd89  jns     loc_18002FE49
0x18002fd8f  mov     eax, cs:dword_1800DA020
0x18002fd95  cmp     eax, 3
0x18002fd98  jbe     loc_18003010E
0x18002fd9e  lea     rax, aRpcgetrequestf; "RpcGetRequestForWinlogon"
0x18002fda5  mov     [rbp+57h+var_D0], rax
0x18002fda9  lea     rdx, dword_1800C0FD4
0x18002fdb0  lea     rax, aPsessionarbitr; "pSessionArbitration->GetRequestForWinlo"...
0x18002fdb7  mov     [rbp+57h+var_C8], rax
0x18002fdbb  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002fdc2  mov     [rbp+57h+var_B8], rax
0x18002fdc6  lea     rax, [rbp+57h+var_D0]
0x18002fdca  mov     [rsp+120h+var_E8], rax
0x18002fdcf  lea     rax, [rbp+57h+var_B0]
0x18002fdd3  mov     dword ptr [rbp+57h+var_B0], ebx
0x18002fdd6  mov     [rsp+120h+var_F0], rax
0x18002fddb  lea     rax, [rbp+57h+var_C8]
0x18002fddf  mov     [rsp+120h+var_F8], rax
0x18002fde4  lea     rax, [rbp+57h+var_B8]
0x18002fde8  mov     [rsp+120h+var_100], rax
0x18002fded  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002fdf2  jmp     loc_18003010E
0x18002fdf7  mov     rdi, [rbp+57h+var_C0]
0x18002fdfb  lea     r8, [rbp+57h+var_A8]
0x18002fdff  mov     [r12], rdi
0x18002fe03  lea     rdx, [rbp+57h+var_A0]
0x18002fe07  mov     rcx, rdi
0x18002fe0a  mov     rax, [rdi]
0x18002fe0d  mov     rax, [rax+20h]
0x18002fe11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe16  mov     ebx, eax
0x18002fe18  test    eax, eax
0x18002fe1a  jns     short loc_18002FE49
0x18002fe1c  mov     eax, cs:dword_1800DA020
0x18002fe22  cmp     eax, 3
0x18002fe25  jbe     loc_18003010E
0x18002fe2b  lea     rax, aRpcgetrequestf; "RpcGetRequestForWinlogon"
0x18002fe32  mov     [rbp+57h+var_D0], rax
0x18002fe36  lea     rdx, byte_1800C0F1F
0x18002fe3d  lea     rax, aGetrequestforw; "GetRequestForWinlogon"
0x18002fe44  jmp     loc_18002FDB7
0x18002fe49  mov     eax, dword ptr [rbp+57h+var_A0+4]
0x18002fe4c  test    eax, eax
0x18002fe4e  jz      short loc_18002FE8A
0x18002fe50  mov     edx, eax
0x18002fe52  mov     ecx, 40h ; '@'; uFlags
0x18002fe57  shl     rdx, 2; uBytes
0x18002fe5b  call    cs:__imp_LocalAlloc
0x18002fe61  mov     [rsi+8], rax
0x18002fe65  test    rax, rax
0x18002fe68  jnz     short loc_18002FE74
0x18002fe6a  mov     ebx, 8007000Eh
0x18002fe6f  jmp     loc_18003010E
0x18002fe74  mov     r8d, dword ptr [rbp+57h+var_A0+4]
0x18002fe78  mov     rcx, rax; void *
0x18002fe7b  mov     rdx, [rbp+57h+Src]; Src
0x18002fe7f  shl     r8, 2; Size
0x18002fe83  call    memcpy_0
0x18002fe88  jmp     short loc_18002FE8E
0x18002fe8a  mov     [rsi+8], r15
0x18002fe8e  mov     ecx, dword ptr [rbp+57h+var_A0]
0x18002fe91  lea     eax, [rcx-1]
0x18002fe94  test    eax, 0FFFFFFFCh
0x18002fe99  jnz     loc_1800300DA
0x18002fe9f  cmp     ecx, 2
0x18002fea2  jz      loc_1800300DA
0x18002fea8  lea     rcx, [rbp+57h+var_80]; struct ISessionManagerInternal **
0x18002feac  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18002feb1  mov     ebx, eax
0x18002feb3  test    eax, eax
0x18002feb5  jns     short loc_18002FED7
0x18002feb7  lea     r9, aRpcgetrequestf; "RpcGetRequestForWinlogon"
0x18002febe  mov     r8d, eax
0x18002fec1  lea     rdx, aGetinstanceofs; "GetInstanceOfSessionManager failed: 0x%"...
0x18002fec8  mov     ecx, 8; int
0x18002fecd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002fed2  jmp     loc_18003010E
0x18002fed7  mov     rcx, [rbp+57h+var_80]
0x18002fedb  lea     rdx, [rbp+57h+var_B0]
0x18002fedf  mov     dword ptr [rbp+57h+var_B0], r15d
0x18002fee3  mov     rax, [rcx]
0x18002fee6  mov     rax, [rax+58h]
0x18002feea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002feef  lea     rcx, [rbp+57h+var_70]; struct ITSSession **
0x18002fef3  call    ?GetSessionFromRpcClientId@CRpcUtils@@SAJPEAPEAUITSSession@@@Z; CRpcUtils::GetSessionFromRpcClientId(ITSSession * *)
0x18002fef8  mov     ebx, eax
0x18002fefa  test    eax, eax
0x18002fefc  jns     short loc_18002FF4A
0x18002fefe  mov     eax, cs:dword_1800DA020
  ... truncated ...
```
