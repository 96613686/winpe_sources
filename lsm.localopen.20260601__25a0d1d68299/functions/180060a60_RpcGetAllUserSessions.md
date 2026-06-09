# RpcGetAllUserSessions

- ea: `0x180060a60`
- end: `0x180061440`
- name: `RpcGetAllUserSessions`
- size: `2528`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001b90`
- `0x18000bd30`
- `0x18000c684`
- `0x18000e8b0`
- `0x18000f260`
- `0x18000f320`
- `0x18000f6e8`
- `0x180013658`
- `0x18001e9d0`
- `0x180021bc0`
- `0x180022200`
- `0x180023984`
- `0x180024b00`
- `0x180027610`
- `0x18002772c`
- `0x180028328`
- `0x18002847c`
- `0x1800288ac`
- `0x18004e850`
- `0x18004f354`
- `0x18005ef98`
- `0x180060a60`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1800610bb`
- `ntdll!RtlEqualSid` at `0x1800610bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060b6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060b6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060d99`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060d99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060cdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060cf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060d09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060cdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060cf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060d09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060eab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060eab`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180060b57`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180060b57`

## string_xrefs

- `0x180060ba2`: `ConvertStringSidToSid`
- `0x180060e6f`: `Impersonate.ImpersonateRpcClient`
- `0x180060f83`: `AccessCheck(WINSTATION_QUERY) failed on session`
- `0x180061078`: `GetUserSid() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcGetAllUserSessions(__int64 a1, const WCHAR *a2, _QWORD *a3, unsigned int *a4)
{
  const WCHAR *v6; // rdi
  char *v7; // r14
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  signed int LastError; // eax
  signed int v15; // ebx
  const char *v16; // rax
  __int16 *v17; // rdx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  unsigned int v22; // edi
  char *v23; // rax
  unsigned int v24; // esi
  int v25; // eax
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // eax
  int v30; // r8d
  int v31; // r9d
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  int v35; // ebx
  int v36; // r8d
  int v37; // r9d
  int v38; // eax
  int v39; // r8d
  int v40; // r9d
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  __int64 v44; // r15
  char *v45; // rbx
  int v46; // eax
  int v47; // r8d
  int v48; // r9d
  int v49; // ecx
  int v50; // r8d
  int v51; // r9d
  int v52; // ecx
  int v53; // r8d
  int v54; // r9d
  int v55; // ecx
  int v56; // r8d
  int v57; // r9d
  struct ISessionManagerInternal *ClientProcessId; // [rsp+40h] [rbp-C0h] BYREF
  const char *v59; // [rsp+48h] [rbp-B8h] BYREF
  const char *v60; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v61; // [rsp+58h] [rbp-A8h] BYREF
  const char *v62; // [rsp+60h] [rbp-A0h] BYREF
  const char *v63; // [rsp+68h] [rbp-98h] BYREF
  const char *v64; // [rsp+70h] [rbp-90h] BYREF
  const char *v65; // [rsp+78h] [rbp-88h] BYREF
  const char *v66; // [rsp+80h] [rbp-80h] BYREF
  const char *v67; // [rsp+88h] [rbp-78h] BYREF
  struct ITSSession *v68; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp-68h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v71; // [rsp+A8h] [rbp-58h] BYREF
  PSID Sid; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v73; // [rsp+B8h] [rbp-48h] BYREF
  struct ISessionManagerInternal *v74; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v75[592]; // [rsp+D0h] [rbp-30h] BYREF

  v6 = a2;
  v60 = (const char *)a2;
  v61 = 0;
  v68 = 0;
  v74 = 0;
  v73 = 0;
  v71 = 0;
  v70 = 0;
  Sid = 0;
  hMem = 0;
  v7 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v75, 0, "RpcGetAllUserSessions");
  if ( !a3 || !a4 || !v6 )
  {
    v15 = -2147024809;
    goto LABEL_19;
  }
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    ClientProcessId = (struct ISessionManagerInternal *)CRpcUtils::GetClientProcessId();
    v59 = (const char *)v6;
    v64 = "RpcGetAllUserSessions called";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v8,
      (unsigned int)&dword_1800C7094,
      v9,
      v10,
      (__int64)&v64,
      (__int64)&v59,
      (__int64)&ClientProcessId);
  }
  *a3 = 0;
  *a4 = 0;
  if ( !ConvertStringSidToSidW(v6, &Sid) )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    if ( v15 < 0 )
    {
      if ( (unsigned int)dword_1800DF020 > 3 )
      {
        v60 = "RpcGetAllUserSessions";
        LODWORD(v64) = v15;
        ClientProcessId = (struct ISessionManagerInternal *)"ConvertStringSidToSid";
        v59 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v11,
          (unsigned int)&word_1800C7056,
          v12,
          v13,
          (__int64)&v59,
          (__int64)&ClientProcessId,
          (__int64)&v64,
          (__int64)&v60);
      }
      goto LABEL_19;
    }
  }
  if ( !CTSPerfProvider::TotalSessions )
  {
LABEL_13:
    v15 = 0;
    goto LABEL_23;
  }
  if ( (unsigned int)CTSPerfProvider::TotalSessions < 0x10000 )
  {
    v22 = CTSPerfProvider::TotalSessions + 10;
    v23 = (char *)LocalAlloc(0x40u, 16LL * (unsigned int)(CTSPerfProvider::TotalSessions + 10));
    v7 = v23;
    if ( !v23 )
    {
      v15 = -2147024882;
      goto LABEL_18;
    }
    memset_0(v23, 0, 16LL * v22);
    ClientProcessId = 0;
    ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&ClientProcessId);
    v74 = ClientProcessId;
    v15 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)ClientProcessId + 24LL))(
            ClientProcessId,
            &v73);
    if ( v15 < 0 )
    {
      if ( (unsigned int)dword_1800DF020 <= 3 )
        goto LABEL_18;
      v16 = "GetSessionList";
      v17 = word_1800C6FDA;
      goto LABEL_17;
    }
    v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v73 + 32LL))(v73, &v71);
    if ( v15 < 0 )
    {
      if ( (unsigned int)dword_1800DF020 <= 3 )
        goto LABEL_18;
      v16 = "GetInstanceOfEnum";
      v17 = (__int16 *)&dword_1800C6F9C;
      goto LABEL_17;
    }
    v15 = CImpersonate::ImpersonateRpcClient((CImpersonate *)&v61);
    if ( v15 >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 88LL))(v71);
      v24 = 0;
      if ( v22 )
      {
        do
        {
          LODWORD(v62) = 0;
          if ( hMem )
          {
            CoTaskMemFree(hMem);
            hMem = 0;
          }
          SmartPtr<ITSSession>::operator=(&v68, 0);
          v25 = (*(__int64 (__fastcall **)(__int64, struct ITSSession **))(*(_QWORD *)v71 + 80LL))(v71, &v68);
          v15 = v25;
          if ( v25 == -2147024637 )
            break;
          if ( v25 < 0 )
          {
            if ( (unsigned int)dword_1800DF020 > 3 )
            {
              v63 = "RpcGetAllUserSessions";
              LODWORD(ClientProcessId) = v25;
              v67 = "Enum";
              v66 = "Warning HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v26,
                (unsigned int)qword_1800C6F20,
                v27,
                v28,
                (__int64)&v66,
                (__int64)&v67,
                (__int64)&ClientProcessId,
                (__int64)&v63);
            }
            goto LABEL_18;
          }
          v29 = (*(__int64 (__fastcall **)(struct ITSSession *, const char **))(*(_QWORD *)v68 + 80LL))(v68, &v62);
          if ( v29 >= 0 )
          {
            if ( (*(int (__fastcall **)(struct ITSSession *, __int64))(*(_QWORD *)v68 + 136LL))(v68, 1) >= 0 )
            {
              SmartPtr<IUserName>::operator=(&v70, 0);
              v35 = (*(__int64 (__fastcall **)(struct ITSSession *, __int64 *))(*(_QWORD *)v68 + 96LL))(v68, &v70);
              if ( v35 >= 0 )
              {
                v38 = (*(__int64 (__fastcall **)(__int64, HLOCAL *))(*(_QWORD *)v70 + 72LL))(v70, &hMem);
                if ( v38 >= 0 )
                {
                  if ( RtlEqualSid(hMem, Sid) )
                  {
                    v44 = 16LL * v24;
                    *(_DWORD *)&v7[v44] = (_DWORD)v62;
                    LODWORD(v64) = 0;
                    (*(void (__fastcall **)(struct ITSSession *, const char **))(*(_QWORD *)v68 + 88LL))(v68, &v64);
                    *(_DWORD *)&v7[v44 + 4] = PrivateToPublicState((unsigned int)v64);
                    v45 = &v7[v44];
                    v46 = PrivateSessionTypeToPublicSessionType(v68, (unsigned int *)&v7[v44 + 8]);
                    if ( v46 >= 0 )
                    {
                      if ( *((_DWORD *)v45 + 2) == 7
                        || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl)
                        && *((_DWORD *)v45 + 2) == 9 )
                      {
                        v59 = 0;
                        v15 = (**(__int64 (__fastcall ***)(struct ITSSession *, __int64 *, const char **))v68)(
                                v68,
                                qword_1800AE500,
                                &v59);
                        if ( v15 < 0 )
                        {
                          if ( (unsigned int)dword_1800DF020 > 3 )
                          {
                            v63 = "RpcGetAllUserSessions";
                            LODWORD(ClientProcessId) = v15;
                            v67 = "Target session is not correct object";
                            v66 = "Warning HResult failed";
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                              v52,
                              (unsigned int)byte_1800C6DB9,
                              v53,
                              v54,
                              (__int64)&v66,
                              (__int64)&v67,
                              (__int64)&ClientProcessId,
                              (__int64)&v63);
                          }
                          goto LABEL_77;
                        }
                        v15 = (*(__int64 (__fastcall **)(const char *, char *))(*(_QWORD *)v59 + 592LL))(
                                v59,
                                &v7[v44 + 12]);
                        if ( v15 < 0 )
                        {
                          if ( (unsigned int)dword_1800DF020 > 3 )
                          {
                            v63 = "RpcGetAllUserSessions";
                            LODWORD(ClientProcessId) = v15;
                            v67 = "GetParentSessionId";
                            v66 = "Warning HResult failed";
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                              v55,
                              (unsigned int)byte_1800C6D7B,
                              v56,
                              v57,
                              (__int64)&v66,
                              (__int64)&v67,
                              (__int64)&ClientProcessId,
                              (__int64)&v63);
                          }
LABEL_77:
                          SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v59);
                          goto LABEL_18;
                        }
                        SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v59);
                      }
                      else
                      {
                        v15 = (*(__int64 (__fastcall **)(struct ITSSession *, char *))(*(_QWORD *)v68 + 304LL))(
                                v68,
                                &v7[v44 + 12]);
                        if ( v15 < 0 )
                        {
                          if ( (unsigned int)dword_1800DF020 > 3 )
                          {
                            v63 = "RpcGetAllUserSessions";
                            LODWORD(ClientProcessId) = v15;
                            v67 = "getChildSessionId";
                            v66 = "Warning HResult failed";
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                              v49,
                              (unsigned int)byte_1800C6D3D,
                              v50,
                              v51,
                              (__int64)&v66,
                              (__int64)&v67,
                              (__int64)&ClientProcessId,
                              (__int64)&v63);
                          }
                          goto LABEL_18;
                        }
                      }
                      ++v24;
                    }
                    else if ( (unsigned int)dword_1800DF020 > 2 )
                    {
                      v63 = (const char *)(int)v62;
                      LODWORD(v59) = v46;
                      v65 = "PrivateSessionTypeToPublicSessionType() failed";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                        (_DWORD)v62,
                        (unsigned int)&byte_1800C6DF7,
                        v47,
                        v48,
                        (__int64)&v65,
                        (__int64)&v59,
                        (__int64)&v63);
                    }
                  }
                  else if ( (unsigned int)dword_1800DF020 > 3 )
                  {
                    v63 = (const char *)(int)v62;
                    v65 = "Session does not belong to the user";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                      v41,
                      (unsigned int)qword_1800C6E28,
                      v42,
                      v43,
                      (__int64)&v65,
                      (__int64)&v63);
                  }
                }
                else if ( (unsigned int)dword_1800DF020 > 3 )
                {
                  v65 = (const char *)(int)v62;
                  LODWORD(v59) = v38;
                  v63 = "GetUserSid() failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                    (_DWORD)v62,
                    (unsigned int)&dword_1800C6E54,
                    v39,
                    v40,
                    (__int64)&v63,
                    (__int64)&v59,
                    (__int64)&v65);
                }
              }
              else if ( (unsigned int)dword_1800DF020 > 3 )
              {
                v66 = (const char *)CRpcUtils::GetClientProcessId();
                v67 = (const char *)(int)v62;
                LODWORD(ClientProcessId) = v35;
                v65 = "Session has no userName associated";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                  (_DWORD)v62,
                  (unsigned int)byte_1800C6E85,
                  v36,
                  v37,
                  (__int64)&v65,
                  (__int64)&ClientProcessId,
                  (__int64)&v67,
                  (__int64)&v66);
              }
            }
            else if ( (unsigned int)dword_1800DF020 > 3 )
            {
              v65 = (const char *)(int)v62;
              v59 = "AccessCheck(WINSTATION_QUERY) failed on session";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                v32,
                (unsigned int)byte_1800C6ECB,
                v33,
                v34,
                (__int64)&v59,
                (__int64)&v65);
            }
          }
          else if ( (unsigned int)dword_1800DF020 > 2 )
          {
            LODWORD(v59) = v29;
            v65 = "Failed to get session ID";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              dword_1800DF020,
              (unsigned int)&byte_1800C6EF7,
              v30,
              v31,
              (__int64)&v65,
              (__int64)&v59);
          }
        }
        while ( v24 < v22 );
        if ( !v24 )
          goto LABEL_83;
        *a3 = v7;
        *a4 = v24;
        goto LABEL_13;
      }
LABEL_83:
      v15 = -2147024894;
      goto LABEL_18;
    }
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      v16 = "Impersonate.ImpersonateRpcClient";
      v17 = &word_1800C6F5E;
      goto LABEL_17;
    }
  }
  else
  {
    v15 = -2147023537;
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      v16 = "NumUserSessions >= LISTENER_SESSION_ID";
      v17 = (__int16 *)qword_1800C7018;
LABEL_17:
      v59 = v16;
      v62 = "Warning HResult failed";
      LODWORD(v64) = v15;
      ClientProcessId = (struct ISessionManagerInternal *)"RpcGetAllUserSessions";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v11,
        (_DWORD)v17,
        v12,
        v13,
        (__int64)&v62,
        (__int64)&v59,
        (__int64)&v64,
        (__int64)&ClientProcessId);
    }
  }
LABEL_18:
  v6 = (const WCHAR *)v60;
LABEL_19:
  if ( (unsigned int)dword_1800DF020 > 2 )
  {
    LODWORD(ClientProcessId) = v15;
    v63 = (const char *)CRpcUtils::GetClientProcessId();
    v67 = (const char *)v6;
    v66 = "RpcGetAllUserSessions() failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v18,
      (unsigned int)byte_1800C6CF1,
      v19,
      v20,
      (__int64)&v66,
      (__int64)&v67,
      (__int64)&v63,
      (__int64)&ClientProcessId);
  }
  if ( v7 )
    LocalFree(v7);
LABEL_23:
  if ( Sid )
    LocalFree(Sid);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v75);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v70);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v71);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v73);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v74);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v68);
  CImpersonate::StopImpersonating((CImpersonate *)&v61);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180060a60  mov     [rsp-8+arg_0], rbx
0x180060a65  push    rbp
0x180060a66  push    rsi
0x180060a67  push    rdi
0x180060a68  push    r12
0x180060a6a  push    r13
0x180060a6c  push    r14
0x180060a6e  push    r15
0x180060a70  lea     rbp, [rsp-230h]
0x180060a78  sub     rsp, 330h
0x180060a7f  mov     rax, cs:__security_cookie
0x180060a86  xor     rax, rsp
0x180060a89  mov     [rbp+260h+var_40], rax
0x180060a90  mov     r12, r9
0x180060a93  mov     r13, r8
0x180060a96  mov     rdi, rdx
0x180060a99  mov     [rsp+360h+var_310], rdx
0x180060a9e  xor     r15d, r15d
0x180060aa1  mov     [rsp+360h+var_308], r15w
0x180060aa7  mov     [rbp+260h+var_2D0], r15
0x180060aab  mov     [rbp+260h+var_2A0], r15
0x180060aaf  mov     [rbp+260h+var_2A8], r15
0x180060ab3  mov     [rbp+260h+var_2B8], r15
0x180060ab7  mov     [rbp+260h+var_2C0], r15
0x180060abb  mov     [rbp+260h+Sid], r15
0x180060abf  mov     [rbp+260h+hMem], r15
0x180060ac3  mov     r14d, r15d
0x180060ac6  lea     rsi, aRpcgetallusers; "RpcGetAllUserSessions"
0x180060acd  mov     r8, rsi; char *
0x180060ad0  xor     edx, edx; int
0x180060ad2  lea     rcx, [rbp+260h+var_290]; this
0x180060ad6  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180060adb  test    r13, r13
0x180060ade  jz      loc_180061436
0x180060ae4  test    r12, r12
0x180060ae7  jz      loc_180061436
0x180060aed  test    rdi, rdi
0x180060af0  jz      loc_180061436
0x180060af6  mov     eax, cs:dword_1800DF020
0x180060afc  cmp     eax, 4
0x180060aff  jbe     short loc_180060B48
0x180060b01  call    ?GetClientProcessId@CRpcUtils@@SAKXZ; CRpcUtils::GetClientProcessId(void)
0x180060b06  mov     eax, eax
0x180060b08  mov     [rsp+360h+var_320], rax
0x180060b0d  mov     [rsp+360h+var_318], rdi
0x180060b12  lea     rax, aRpcgetallusers_0; "RpcGetAllUserSessions called"
0x180060b19  mov     [rsp+360h+var_2F0], rax
0x180060b1e  lea     rax, [rsp+360h+var_320]
0x180060b23  mov     [rsp+360h+var_330], rax
0x180060b28  lea     rax, [rsp+360h+var_318]
0x180060b2d  mov     [rsp+360h+var_338], rax
0x180060b32  lea     rax, [rsp+360h+var_2F0]
0x180060b37  mov     [rsp+360h+var_340], rax
0x180060b3c  lea     rdx, dword_1800C7094
0x180060b43  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180060b48  mov     [r13+0], r15
0x180060b4c  mov     [r12], r15d
0x180060b50  lea     rdx, [rbp+260h+Sid]; Sid
0x180060b54  mov     rcx, rdi; StringSid
0x180060b57  call    cs:__imp_ConvertStringSidToSidW
0x180060b5e  nop     dword ptr [rax+rax+00h]
0x180060b63  test    eax, eax
0x180060b65  jnz     loc_180060BF3
0x180060b6b  call    cs:__imp_GetLastError
0x180060b72  nop     dword ptr [rax+rax+00h]
0x180060b77  mov     ebx, eax
0x180060b79  test    eax, eax
0x180060b7b  jle     short loc_180060B86
0x180060b7d  movzx   ebx, ax
0x180060b80  or      ebx, 80070000h
0x180060b86  test    ebx, ebx
0x180060b88  jns     short loc_180060BF3
0x180060b8a  mov     eax, cs:dword_1800DF020
0x180060b90  cmp     eax, 3
0x180060b93  jbe     loc_180060C7B
0x180060b99  mov     [rsp+360h+var_310], rsi
0x180060b9e  mov     dword ptr [rsp+360h+var_2F0], ebx
0x180060ba2  lea     rax, aConvertstrings_2; "ConvertStringSidToSid"
0x180060ba9  mov     [rsp+360h+var_320], rax
0x180060bae  lea     rax, aWarningHresult; "Warning HResult failed"
0x180060bb5  mov     [rsp+360h+var_318], rax
0x180060bba  lea     rax, [rsp+360h+var_310]
0x180060bbf  mov     [rsp+360h+var_328], rax
0x180060bc4  lea     rax, [rsp+360h+var_2F0]
0x180060bc9  mov     [rsp+360h+var_330], rax
0x180060bce  lea     rax, [rsp+360h+var_320]
0x180060bd3  mov     [rsp+360h+var_338], rax
0x180060bd8  lea     rax, [rsp+360h+var_318]
0x180060bdd  mov     [rsp+360h+var_340], rax
0x180060be2  lea     rdx, word_1800C7056
0x180060be9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180060bee  jmp     loc_180060C7B
0x180060bf3  mov     edi, cs:?TotalSessions@CTSPerfProvider@@0JC; long volatile CTSPerfProvider::TotalSessions
0x180060bf9  test    edi, edi
0x180060bfb  jnz     short loc_180060C05
0x180060bfd  mov     ebx, r15d
0x180060c00  jmp     loc_180060CEB
0x180060c05  cmp     edi, 10000h
0x180060c0b  jb      loc_180060D88
0x180060c11  mov     ebx, 8007054Fh
0x180060c16  mov     eax, cs:dword_1800DF020
0x180060c1c  cmp     eax, 3
0x180060c1f  jbe     short loc_180060C76
0x180060c21  lea     rax, aNumusersession; "NumUserSessions >= LISTENER_SESSION_ID"
0x180060c28  lea     rdx, qword_1800C7018
0x180060c2f  mov     [rsp+360h+var_318], rax
0x180060c34  lea     rax, aWarningHresult; "Warning HResult failed"
0x180060c3b  mov     [rsp+360h+var_300], rax
0x180060c40  lea     rax, [rsp+360h+var_320]
0x180060c45  mov     [rsp+360h+var_328], rax
0x180060c4a  lea     rax, [rsp+360h+var_2F0]
0x180060c4f  mov     [rsp+360h+var_330], rax
0x180060c54  lea     rax, [rsp+360h+var_318]
0x180060c59  mov     [rsp+360h+var_338], rax
0x180060c5e  lea     rax, [rsp+360h+var_300]
0x180060c63  mov     [rsp+360h+var_340], rax
0x180060c68  mov     dword ptr [rsp+360h+var_2F0], ebx
0x180060c6c  mov     [rsp+360h+var_320], rsi
0x180060c71  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180060c76  mov     rdi, [rsp+360h+var_310]
0x180060c7b  mov     eax, cs:dword_1800DF020
0x180060c81  cmp     eax, 2
0x180060c84  jbe     short loc_180060CD7
0x180060c86  mov     dword ptr [rsp+360h+var_320], ebx
0x180060c8a  call    ?GetClientProcessId@CRpcUtils@@SAKXZ; CRpcUtils::GetClientProcessId(void)
0x180060c8f  mov     eax, eax
0x180060c91  mov     [rsp+360h+var_2F8], rax
0x180060c96  mov     [rbp+260h+var_2D8], rdi
0x180060c9a  lea     rax, aRpcgetallusers_1; "RpcGetAllUserSessions() failed"
0x180060ca1  mov     [rbp+260h+var_2E0], rax
0x180060ca5  lea     rax, [rsp+360h+var_320]
0x180060caa  mov     [rsp+360h+var_328], rax
0x180060caf  lea     rax, [rsp+360h+var_2F8]
0x180060cb4  mov     [rsp+360h+var_330], rax
0x180060cb9  lea     rax, [rbp+260h+var_2D8]
0x180060cbd  mov     [rsp+360h+var_338], rax
0x180060cc2  lea     rax, [rbp+260h+var_2E0]
0x180060cc6  mov     [rsp+360h+var_340], rax
0x180060ccb  lea     rdx, byte_1800C6CF1
0x180060cd2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180060cd7  test    r14, r14
0x180060cda  jz      short loc_180060CEB
0x180060cdc  mov     rcx, r14; hMem
0x180060cdf  call    cs:__imp_LocalFree
0x180060ce6  nop     dword ptr [rax+rax+00h]
0x180060ceb  mov     rcx, [rbp+260h+Sid]; hMem
0x180060cef  test    rcx, rcx
0x180060cf2  jz      short loc_180060D00
0x180060cf4  call    cs:__imp_LocalFree
0x180060cfb  nop     dword ptr [rax+rax+00h]
0x180060d00  mov     rcx, [rbp+260h+hMem]; hMem
0x180060d04  test    rcx, rcx
0x180060d07  jz      short loc_180060D19
0x180060d09  call    cs:__imp_LocalFree
0x180060d10  nop     dword ptr [rax+rax+00h]
0x180060d15  mov     [rbp+260h+hMem], r15
0x180060d19  lea     rcx, [rbp+260h+var_290]; this
0x180060d1d  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x180060d22  lea     rcx, [rbp+260h+var_2C0]
0x180060d26  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180060d2b  lea     rcx, [rbp+260h+var_2B8]
0x180060d2f  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180060d34  lea     rcx, [rbp+260h+var_2A8]
0x180060d38  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180060d3d  lea     rcx, [rbp+260h+var_2A0]
0x180060d41  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180060d46  lea     rcx, [rbp+260h+var_2D0]
0x180060d4a  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180060d4f  nop
0x180060d50  lea     rcx, [rsp+360h+var_308]; this
0x180060d55  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x180060d5a  nop
0x180060d5b  mov     eax, ebx
0x180060d5d  mov     rcx, [rbp+260h+var_40]
0x180060d64  xor     rcx, rsp; StackCookie
0x180060d67  call    __security_check_cookie
0x180060d6c  mov     rbx, [rsp+360h+arg_0]
0x180060d74  add     rsp, 330h
0x180060d7b  pop     r15
0x180060d7d  pop     r14
0x180060d7f  pop     r13
0x180060d81  pop     r12
0x180060d83  pop     rdi
0x180060d84  pop     rsi
0x180060d85  pop     rbp
0x180060d86  retn
0x180060d88  add     edi, 0Ah
0x180060d8b  mov     ebx, edi
0x180060d8d  shl     rbx, 4
0x180060d91  mov     rdx, rbx; uBytes
0x180060d94  mov     ecx, 40h ; '@'; uFlags
0x180060d99  call    cs:__imp_LocalAlloc
0x180060da0  nop     dword ptr [rax+rax+00h]
0x180060da5  mov     r14, rax
0x180060da8  test    rax, rax
0x180060dab  jnz     short loc_180060DB7
0x180060dad  mov     ebx, 8007000Eh
0x180060db2  jmp     loc_180060C76
0x180060db7  mov     r8, rbx; Size
0x180060dba  xor     edx, edx; Val
0x180060dbc  mov     rcx, r14; void *
0x180060dbf  call    memset_0
0x180060dc4  mov     [rsp+360h+var_320], r15
0x180060dc9  lea     rcx, [rsp+360h+var_320]; struct ISessionManagerInternal **
0x180060dce  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x180060dd3  mov     rcx, [rsp+360h+var_320]
0x180060dd8  mov     [rbp+260h+var_2A0], rcx
0x180060ddc  mov     rax, [rcx]
0x180060ddf  lea     rdx, [rbp+260h+var_2A8]
0x180060de3  mov     rax, [rax+18h]
0x180060de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060dec  mov     ebx, eax
0x180060dee  test    eax, eax
0x180060df0  jns     short loc_180060E14
0x180060df2  mov     eax, cs:dword_1800DF020
0x180060df8  cmp     eax, 3
0x180060dfb  jbe     loc_180060C76
0x180060e01  lea     rax, aGetsessionlist_2; "GetSessionList"
0x180060e08  lea     rdx, word_1800C6FDA
0x180060e0f  jmp     loc_180060C2F
0x180060e14  mov     rcx, [rbp+260h+var_2A8]
0x180060e18  mov     rax, [rcx]
0x180060e1b  lea     rdx, [rbp+260h+var_2B8]
0x180060e1f  mov     rax, [rax+20h]
0x180060e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060e28  mov     ebx, eax
0x180060e2a  test    eax, eax
0x180060e2c  jns     short loc_180060E50
0x180060e2e  mov     eax, cs:dword_1800DF020
0x180060e34  cmp     eax, 3
0x180060e37  jbe     loc_180060C76
0x180060e3d  lea     rax, aGetinstanceofe_0; "GetInstanceOfEnum"
0x180060e44  lea     rdx, dword_1800C6F9C
0x180060e4b  jmp     loc_180060C2F
0x180060e50  lea     rcx, [rsp+360h+var_308]; this
0x180060e55  call    ?ImpersonateRpcClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateRpcClient(void)
0x180060e5a  mov     ebx, eax
0x180060e5c  test    eax, eax
0x180060e5e  jns     short loc_180060E82
0x180060e60  mov     eax, cs:dword_1800DF020
0x180060e66  cmp     eax, 3
0x180060e69  jbe     loc_180060C76
0x180060e6f  lea     rax, aImpersonateImp; "Impersonate.ImpersonateRpcClient"
0x180060e76  lea     rdx, word_1800C6F5E
0x180060e7d  jmp     loc_180060C2F
0x180060e82  mov     rcx, [rbp+260h+var_2B8]
0x180060e86  mov     rax, [rcx]
0x180060e89  mov     rax, [rax+58h]
0x180060e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060e92  mov     esi, r15d
0x180060e95  test    edi, edi
0x180060e97  jz      loc_18006142C
0x180060e9d  mov     dword ptr [rsp+360h+var_300], r15d
0x180060ea2  mov     rcx, [rbp+260h+hMem]; pv
0x180060ea6  test    rcx, rcx
0x180060ea9  jz      short loc_180060EBB
0x180060eab  call    cs:__imp_CoTaskMemFree
0x180060eb2  nop     dword ptr [rax+rax+00h]
0x180060eb7  mov     [rbp+260h+hMem], r15
0x180060ebb  xor     edx, edx
0x180060ebd  lea     rcx, [rbp+260h+var_2D0]
0x180060ec1  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x180060ec6  mov     rcx, [rbp+260h+var_2B8]
0x180060eca  mov     rax, [rcx]
0x180060ecd  lea     rdx, [rbp+260h+var_2D0]
0x180060ed1  mov     rax, [rax+50h]
0x180060ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060eda  mov     ebx, eax
0x180060edc  cmp     eax, 80070103h
0x180060ee1  jz      loc_1800611B4
0x180060ee7  test    eax, eax
0x180060ee9  js      loc_1800613C5
0x180060eef  mov     rcx, [rbp+260h+var_2D0]
0x180060ef3  mov     rax, [rcx]
0x180060ef6  lea     rdx, [rsp+360h+var_300]
0x180060efb  mov     rax, [rax+50h]
0x180060eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060f04  test    eax, eax
0x180060f06  jns     short loc_180060F4C
0x180060f08  mov     ecx, cs:dword_1800DF020
0x180060f0e  cmp     ecx, 2
0x180060f11  jbe     loc_1800611AC
0x180060f17  mov     dword ptr [rsp+360h+var_318], eax
0x180060f1b  lea     rax, aFailedToGetSes_1; "Failed to get session ID"
0x180060f22  mov     [rsp+360h+var_2E8], rax
0x180060f27  lea     rax, [rsp+360h+var_318]
0x180060f2c  mov     [rsp+360h+var_338], rax
0x180060f31  lea     rax, [rsp+360h+var_2E8]
0x180060f36  mov     [rsp+360h+var_340], rax
0x180060f3b  lea     rdx, byte_1800C6EF7
0x180060f42  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180060f47  jmp     loc_1800611AC
0x180060f4c  mov     rcx, [rbp+260h+var_2D0]
0x180060f50  mov     rax, [rcx]
0x180060f53  xor     r8d, r8d
0x180060f56  lea     edx, [r8+1]
0x180060f5a  mov     rax, [rax+88h]
0x180060f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060f66  test    eax, eax
0x180060f68  jns     short loc_180060FB4
  ... truncated ...
```
