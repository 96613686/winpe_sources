# RpcGetAllUserSessions

- ea: `0x18005d000`
- end: `0x18005d9af`
- name: `RpcGetAllUserSessions`
- size: `2479`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001b80`
- `0x180008f64`
- `0x18000fa38`
- `0x180014c00`
- `0x180014f40`
- `0x180014ff0`
- `0x180015d24`
- `0x180017e00`
- `0x18001ee40`
- `0x18001f7bc`
- `0x18001fd70`
- `0x180021bc4`
- `0x180022c4c`
- `0x180025600`
- `0x180025890`
- `0x1800262a0`
- `0x1800263f0`
- `0x1800267c4`
- `0x18004b460`
- `0x18004bf44`
- `0x18005b590`
- `0x18005d000`
- `0x180097010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18005d630`
- `ntdll!RtlEqualSid` at `0x18005d630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d105`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005d31a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005d31a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d273`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d282`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d291`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d273`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d282`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d291`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d426`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d426`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005d0f7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005d0f7`

## string_xrefs

- `0x18005d136`: `ConvertStringSidToSid`
- `0x18005d3ea`: `Impersonate.ImpersonateRpcClient`
- `0x18005d4f8`: `AccessCheck(WINSTATION_QUERY) failed on session`
- `0x18005d5ed`: `GetUserSid() failed`

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
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    ClientProcessId = (struct ISessionManagerInternal *)CRpcUtils::GetClientProcessId();
    v59 = (const char *)v6;
    v64 = "RpcGetAllUserSessions called";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v8,
      (unsigned int)&dword_1800C1F0C,
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
      if ( (unsigned int)dword_1800DA020 > 3 )
      {
        v60 = "RpcGetAllUserSessions";
        LODWORD(v64) = v15;
        ClientProcessId = (struct ISessionManagerInternal *)"ConvertStringSidToSid";
        v59 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v11,
          (unsigned int)&word_1800C1ECE,
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
      if ( (unsigned int)dword_1800DA020 <= 3 )
        goto LABEL_18;
      v16 = "GetSessionList";
      v17 = word_1800C1E52;
      goto LABEL_17;
    }
    v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v73 + 32LL))(v73, &v71);
    if ( v15 < 0 )
    {
      if ( (unsigned int)dword_1800DA020 <= 3 )
        goto LABEL_18;
      v16 = "GetInstanceOfEnum";
      v17 = (__int16 *)&dword_1800C1E14;
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
            if ( (unsigned int)dword_1800DA020 > 3 )
            {
              v63 = "RpcGetAllUserSessions";
              LODWORD(ClientProcessId) = v25;
              v67 = "Enum";
              v66 = "Warning HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v26,
                (unsigned int)qword_1800C1D98,
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
                                qword_1800A9370,
                                &v59);
                        if ( v15 < 0 )
                        {
                          if ( (unsigned int)dword_1800DA020 > 3 )
                          {
                            v63 = "RpcGetAllUserSessions";
                            LODWORD(ClientProcessId) = v15;
                            v67 = "Target session is not correct object";
                            v66 = "Warning HResult failed";
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                              v52,
                              (unsigned int)byte_1800C1C31,
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
                          if ( (unsigned int)dword_1800DA020 > 3 )
                          {
                            v63 = "RpcGetAllUserSessions";
                            LODWORD(ClientProcessId) = v15;
                            v67 = "GetParentSessionId";
                            v66 = "Warning HResult failed";
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                              v55,
                              (unsigned int)byte_1800C1BF3,
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
                          if ( (unsigned int)dword_1800DA020 > 3 )
                          {
                            v63 = "RpcGetAllUserSessions";
                            LODWORD(ClientProcessId) = v15;
                            v67 = "getChildSessionId";
                            v66 = "Warning HResult failed";
                            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                              v49,
                              (unsigned int)byte_1800C1BB5,
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
                    else if ( (unsigned int)dword_1800DA020 > 2 )
                    {
                      v63 = (const char *)(int)v62;
                      LODWORD(v59) = v46;
                      v65 = "PrivateSessionTypeToPublicSessionType() failed";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                        (_DWORD)v62,
                        (unsigned int)&byte_1800C1C6F,
                        v47,
                        v48,
                        (__int64)&v65,
                        (__int64)&v59,
                        (__int64)&v63);
                    }
                  }
                  else if ( (unsigned int)dword_1800DA020 > 3 )
                  {
                    v63 = (const char *)(int)v62;
                    v65 = "Session does not belong to the user";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                      v41,
                      (unsigned int)qword_1800C1CA0,
                      v42,
                      v43,
                      (__int64)&v65,
                      (__int64)&v63);
                  }
                }
                else if ( (unsigned int)dword_1800DA020 > 3 )
                {
                  v65 = (const char *)(int)v62;
                  LODWORD(v59) = v38;
                  v63 = "GetUserSid() failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                    (_DWORD)v62,
                    (unsigned int)&dword_1800C1CCC,
                    v39,
                    v40,
                    (__int64)&v63,
                    (__int64)&v59,
                    (__int64)&v65);
                }
              }
              else if ( (unsigned int)dword_1800DA020 > 3 )
              {
                v66 = (const char *)CRpcUtils::GetClientProcessId();
                v67 = (const char *)(int)v62;
                LODWORD(ClientProcessId) = v35;
                v65 = "Session has no userName associated";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                  (_DWORD)v62,
                  (unsigned int)byte_1800C1CFD,
                  v36,
                  v37,
                  (__int64)&v65,
                  (__int64)&ClientProcessId,
                  (__int64)&v67,
                  (__int64)&v66);
              }
            }
            else if ( (unsigned int)dword_1800DA020 > 3 )
            {
              v65 = (const char *)(int)v62;
              v59 = "AccessCheck(WINSTATION_QUERY) failed on session";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                v32,
                (unsigned int)byte_1800C1D43,
                v33,
                v34,
                (__int64)&v59,
                (__int64)&v65);
            }
          }
          else if ( (unsigned int)dword_1800DA020 > 2 )
          {
            LODWORD(v59) = v29;
            v65 = "Failed to get session ID";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              dword_1800DA020,
              (unsigned int)&byte_1800C1D6F,
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
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      v16 = "Impersonate.ImpersonateRpcClient";
      v17 = &word_1800C1DD6;
      goto LABEL_17;
    }
  }
  else
  {
    v15 = -2147023537;
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      v16 = "NumUserSessions >= LISTENER_SESSION_ID";
      v17 = (__int16 *)qword_1800C1E90;
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
  if ( (unsigned int)dword_1800DA020 > 2 )
  {
    LODWORD(ClientProcessId) = v15;
    v63 = (const char *)CRpcUtils::GetClientProcessId();
    v67 = (const char *)v6;
    v66 = "RpcGetAllUserSessions() failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v18,
      (unsigned int)byte_1800C1B69,
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
0x18005d000  mov     [rsp-8+arg_0], rbx
0x18005d005  push    rbp
0x18005d006  push    rsi
0x18005d007  push    rdi
0x18005d008  push    r12
0x18005d00a  push    r13
0x18005d00c  push    r14
0x18005d00e  push    r15
0x18005d010  lea     rbp, [rsp-230h]
0x18005d018  sub     rsp, 330h
0x18005d01f  mov     rax, cs:__security_cookie
0x18005d026  xor     rax, rsp
0x18005d029  mov     [rbp+260h+var_40], rax
0x18005d030  mov     r12, r9
0x18005d033  mov     r13, r8
0x18005d036  mov     rdi, rdx
0x18005d039  mov     [rsp+360h+var_310], rdx
0x18005d03e  xor     r15d, r15d
0x18005d041  mov     [rsp+360h+var_308], r15w
0x18005d047  mov     [rbp+260h+var_2D0], r15
0x18005d04b  mov     [rbp+260h+var_2A0], r15
0x18005d04f  mov     [rbp+260h+var_2A8], r15
0x18005d053  mov     [rbp+260h+var_2B8], r15
0x18005d057  mov     [rbp+260h+var_2C0], r15
0x18005d05b  mov     [rbp+260h+Sid], r15
0x18005d05f  mov     [rbp+260h+hMem], r15
0x18005d063  mov     r14d, r15d
0x18005d066  lea     rsi, aRpcgetallusers; "RpcGetAllUserSessions"
0x18005d06d  mov     r8, rsi; char *
0x18005d070  xor     edx, edx; int
0x18005d072  lea     rcx, [rbp+260h+var_290]; this
0x18005d076  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18005d07b  test    r13, r13
0x18005d07e  jz      loc_18005D9A5
0x18005d084  test    r12, r12
0x18005d087  jz      loc_18005D9A5
0x18005d08d  test    rdi, rdi
0x18005d090  jz      loc_18005D9A5
0x18005d096  mov     eax, cs:dword_1800DA020
0x18005d09c  cmp     eax, 4
0x18005d09f  jbe     short loc_18005D0E8
0x18005d0a1  call    ?GetClientProcessId@CRpcUtils@@SAKXZ; CRpcUtils::GetClientProcessId(void)
0x18005d0a6  mov     eax, eax
0x18005d0a8  mov     [rsp+360h+var_320], rax
0x18005d0ad  mov     [rsp+360h+var_318], rdi
0x18005d0b2  lea     rax, aRpcgetallusers_0; "RpcGetAllUserSessions called"
0x18005d0b9  mov     [rsp+360h+var_2F0], rax
0x18005d0be  lea     rax, [rsp+360h+var_320]
0x18005d0c3  mov     [rsp+360h+var_330], rax
0x18005d0c8  lea     rax, [rsp+360h+var_318]
0x18005d0cd  mov     [rsp+360h+var_338], rax
0x18005d0d2  lea     rax, [rsp+360h+var_2F0]
0x18005d0d7  mov     [rsp+360h+var_340], rax
0x18005d0dc  lea     rdx, dword_1800C1F0C
0x18005d0e3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18005d0e8  mov     [r13+0], r15
0x18005d0ec  mov     [r12], r15d
0x18005d0f0  lea     rdx, [rbp+260h+Sid]; Sid
0x18005d0f4  mov     rcx, rdi; StringSid
0x18005d0f7  call    cs:__imp_ConvertStringSidToSidW
0x18005d0fd  test    eax, eax
0x18005d0ff  jnz     loc_18005D187
0x18005d105  call    cs:__imp_GetLastError
0x18005d10b  mov     ebx, eax
0x18005d10d  test    eax, eax
0x18005d10f  jle     short loc_18005D11A
0x18005d111  movzx   ebx, ax
0x18005d114  or      ebx, 80070000h
0x18005d11a  test    ebx, ebx
0x18005d11c  jns     short loc_18005D187
0x18005d11e  mov     eax, cs:dword_1800DA020
0x18005d124  cmp     eax, 3
0x18005d127  jbe     loc_18005D20F
0x18005d12d  mov     [rsp+360h+var_310], rsi
0x18005d132  mov     dword ptr [rsp+360h+var_2F0], ebx
0x18005d136  lea     rax, aConvertstrings_2; "ConvertStringSidToSid"
0x18005d13d  mov     [rsp+360h+var_320], rax
0x18005d142  lea     rax, aWarningHresult; "Warning HResult failed"
0x18005d149  mov     [rsp+360h+var_318], rax
0x18005d14e  lea     rax, [rsp+360h+var_310]
0x18005d153  mov     [rsp+360h+var_328], rax
0x18005d158  lea     rax, [rsp+360h+var_2F0]
0x18005d15d  mov     [rsp+360h+var_330], rax
0x18005d162  lea     rax, [rsp+360h+var_320]
0x18005d167  mov     [rsp+360h+var_338], rax
0x18005d16c  lea     rax, [rsp+360h+var_318]
0x18005d171  mov     [rsp+360h+var_340], rax
0x18005d176  lea     rdx, word_1800C1ECE
0x18005d17d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18005d182  jmp     loc_18005D20F
0x18005d187  mov     edi, cs:?TotalSessions@CTSPerfProvider@@0JC; long volatile CTSPerfProvider::TotalSessions
0x18005d18d  test    edi, edi
0x18005d18f  jnz     short loc_18005D199
0x18005d191  mov     ebx, r15d
0x18005d194  jmp     loc_18005D279
0x18005d199  cmp     edi, 10000h
0x18005d19f  jb      loc_18005D309
0x18005d1a5  mov     ebx, 8007054Fh
0x18005d1aa  mov     eax, cs:dword_1800DA020
0x18005d1b0  cmp     eax, 3
0x18005d1b3  jbe     short loc_18005D20A
0x18005d1b5  lea     rax, aNumusersession; "NumUserSessions >= LISTENER_SESSION_ID"
0x18005d1bc  lea     rdx, qword_1800C1E90
0x18005d1c3  mov     [rsp+360h+var_318], rax
0x18005d1c8  lea     rax, aWarningHresult; "Warning HResult failed"
0x18005d1cf  mov     [rsp+360h+var_300], rax
0x18005d1d4  lea     rax, [rsp+360h+var_320]
0x18005d1d9  mov     [rsp+360h+var_328], rax
0x18005d1de  lea     rax, [rsp+360h+var_2F0]
0x18005d1e3  mov     [rsp+360h+var_330], rax
0x18005d1e8  lea     rax, [rsp+360h+var_318]
0x18005d1ed  mov     [rsp+360h+var_338], rax
0x18005d1f2  lea     rax, [rsp+360h+var_300]
0x18005d1f7  mov     [rsp+360h+var_340], rax
0x18005d1fc  mov     dword ptr [rsp+360h+var_2F0], ebx
0x18005d200  mov     [rsp+360h+var_320], rsi
0x18005d205  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18005d20a  mov     rdi, [rsp+360h+var_310]
0x18005d20f  mov     eax, cs:dword_1800DA020
0x18005d215  cmp     eax, 2
0x18005d218  jbe     short loc_18005D26B
0x18005d21a  mov     dword ptr [rsp+360h+var_320], ebx
0x18005d21e  call    ?GetClientProcessId@CRpcUtils@@SAKXZ; CRpcUtils::GetClientProcessId(void)
0x18005d223  mov     eax, eax
0x18005d225  mov     [rsp+360h+var_2F8], rax
0x18005d22a  mov     [rbp+260h+var_2D8], rdi
0x18005d22e  lea     rax, aRpcgetallusers_1; "RpcGetAllUserSessions() failed"
0x18005d235  mov     [rbp+260h+var_2E0], rax
0x18005d239  lea     rax, [rsp+360h+var_320]
0x18005d23e  mov     [rsp+360h+var_328], rax
0x18005d243  lea     rax, [rsp+360h+var_2F8]
0x18005d248  mov     [rsp+360h+var_330], rax
0x18005d24d  lea     rax, [rbp+260h+var_2D8]
0x18005d251  mov     [rsp+360h+var_338], rax
0x18005d256  lea     rax, [rbp+260h+var_2E0]
0x18005d25a  mov     [rsp+360h+var_340], rax
0x18005d25f  lea     rdx, byte_1800C1B69
0x18005d266  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18005d26b  test    r14, r14
0x18005d26e  jz      short loc_18005D279
0x18005d270  mov     rcx, r14; hMem
0x18005d273  call    cs:__imp_LocalFree
0x18005d279  mov     rcx, [rbp+260h+Sid]; hMem
0x18005d27d  test    rcx, rcx
0x18005d280  jz      short loc_18005D288
0x18005d282  call    cs:__imp_LocalFree
0x18005d288  mov     rcx, [rbp+260h+hMem]; hMem
0x18005d28c  test    rcx, rcx
0x18005d28f  jz      short loc_18005D29B
0x18005d291  call    cs:__imp_LocalFree
0x18005d297  mov     [rbp+260h+hMem], r15
0x18005d29b  lea     rcx, [rbp+260h+var_290]; this
0x18005d29f  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18005d2a4  lea     rcx, [rbp+260h+var_2C0]
0x18005d2a8  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005d2ad  lea     rcx, [rbp+260h+var_2B8]
0x18005d2b1  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005d2b6  lea     rcx, [rbp+260h+var_2A8]
0x18005d2ba  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005d2bf  lea     rcx, [rbp+260h+var_2A0]
0x18005d2c3  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005d2c8  lea     rcx, [rbp+260h+var_2D0]
0x18005d2cc  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005d2d1  nop
0x18005d2d2  lea     rcx, [rsp+360h+var_308]; this
0x18005d2d7  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x18005d2dc  nop
0x18005d2dd  mov     eax, ebx
0x18005d2df  mov     rcx, [rbp+260h+var_40]
0x18005d2e6  xor     rcx, rsp; StackCookie
0x18005d2e9  call    __security_check_cookie
0x18005d2ee  mov     rbx, [rsp+360h+arg_0]
0x18005d2f6  add     rsp, 330h
0x18005d2fd  pop     r15
0x18005d2ff  pop     r14
0x18005d301  pop     r13
0x18005d303  pop     r12
0x18005d305  pop     rdi
0x18005d306  pop     rsi
0x18005d307  pop     rbp
0x18005d308  retn
0x18005d309  add     edi, 0Ah
0x18005d30c  mov     ebx, edi
0x18005d30e  shl     rbx, 4
0x18005d312  mov     rdx, rbx; uBytes
0x18005d315  mov     ecx, 40h ; '@'; uFlags
0x18005d31a  call    cs:__imp_LocalAlloc
0x18005d320  mov     r14, rax
0x18005d323  test    rax, rax
0x18005d326  jnz     short loc_18005D332
0x18005d328  mov     ebx, 8007000Eh
0x18005d32d  jmp     loc_18005D20A
0x18005d332  mov     r8, rbx; Size
0x18005d335  xor     edx, edx; Val
0x18005d337  mov     rcx, r14; void *
0x18005d33a  call    memset_0
0x18005d33f  mov     [rsp+360h+var_320], r15
0x18005d344  lea     rcx, [rsp+360h+var_320]; struct ISessionManagerInternal **
0x18005d349  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18005d34e  mov     rcx, [rsp+360h+var_320]
0x18005d353  mov     [rbp+260h+var_2A0], rcx
0x18005d357  mov     rax, [rcx]
0x18005d35a  lea     rdx, [rbp+260h+var_2A8]
0x18005d35e  mov     rax, [rax+18h]
0x18005d362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d367  mov     ebx, eax
0x18005d369  test    eax, eax
0x18005d36b  jns     short loc_18005D38F
0x18005d36d  mov     eax, cs:dword_1800DA020
0x18005d373  cmp     eax, 3
0x18005d376  jbe     loc_18005D20A
0x18005d37c  lea     rax, aGetsessionlist_2; "GetSessionList"
0x18005d383  lea     rdx, word_1800C1E52
0x18005d38a  jmp     loc_18005D1C3
0x18005d38f  mov     rcx, [rbp+260h+var_2A8]
0x18005d393  mov     rax, [rcx]
0x18005d396  lea     rdx, [rbp+260h+var_2B8]
0x18005d39a  mov     rax, [rax+20h]
0x18005d39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3a3  mov     ebx, eax
0x18005d3a5  test    eax, eax
0x18005d3a7  jns     short loc_18005D3CB
0x18005d3a9  mov     eax, cs:dword_1800DA020
0x18005d3af  cmp     eax, 3
0x18005d3b2  jbe     loc_18005D20A
0x18005d3b8  lea     rax, aGetinstanceofe_0; "GetInstanceOfEnum"
0x18005d3bf  lea     rdx, dword_1800C1E14
0x18005d3c6  jmp     loc_18005D1C3
0x18005d3cb  lea     rcx, [rsp+360h+var_308]; this
0x18005d3d0  call    ?ImpersonateRpcClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateRpcClient(void)
0x18005d3d5  mov     ebx, eax
0x18005d3d7  test    eax, eax
0x18005d3d9  jns     short loc_18005D3FD
0x18005d3db  mov     eax, cs:dword_1800DA020
0x18005d3e1  cmp     eax, 3
0x18005d3e4  jbe     loc_18005D20A
0x18005d3ea  lea     rax, aImpersonateImp; "Impersonate.ImpersonateRpcClient"
0x18005d3f1  lea     rdx, word_1800C1DD6
0x18005d3f8  jmp     loc_18005D1C3
0x18005d3fd  mov     rcx, [rbp+260h+var_2B8]
0x18005d401  mov     rax, [rcx]
0x18005d404  mov     rax, [rax+58h]
0x18005d408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d40d  mov     esi, r15d
0x18005d410  test    edi, edi
0x18005d412  jz      loc_18005D99B
0x18005d418  mov     dword ptr [rsp+360h+var_300], r15d
0x18005d41d  mov     rcx, [rbp+260h+hMem]; pv
0x18005d421  test    rcx, rcx
0x18005d424  jz      short loc_18005D430
0x18005d426  call    cs:__imp_CoTaskMemFree
0x18005d42c  mov     [rbp+260h+hMem], r15
0x18005d430  xor     edx, edx
0x18005d432  lea     rcx, [rbp+260h+var_2D0]
0x18005d436  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x18005d43b  mov     rcx, [rbp+260h+var_2B8]
0x18005d43f  mov     rax, [rcx]
0x18005d442  lea     rdx, [rbp+260h+var_2D0]
0x18005d446  mov     rax, [rax+50h]
0x18005d44a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d44f  mov     ebx, eax
0x18005d451  cmp     eax, 80070103h
0x18005d456  jz      loc_18005D723
0x18005d45c  test    eax, eax
0x18005d45e  js      loc_18005D934
0x18005d464  mov     rcx, [rbp+260h+var_2D0]
0x18005d468  mov     rax, [rcx]
0x18005d46b  lea     rdx, [rsp+360h+var_300]
0x18005d470  mov     rax, [rax+50h]
0x18005d474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d479  test    eax, eax
0x18005d47b  jns     short loc_18005D4C1
0x18005d47d  mov     ecx, cs:dword_1800DA020
0x18005d483  cmp     ecx, 2
0x18005d486  jbe     loc_18005D71B
0x18005d48c  mov     dword ptr [rsp+360h+var_318], eax
0x18005d490  lea     rax, aFailedToGetSes_1; "Failed to get session ID"
0x18005d497  mov     [rsp+360h+var_2E8], rax
0x18005d49c  lea     rax, [rsp+360h+var_318]
0x18005d4a1  mov     [rsp+360h+var_338], rax
0x18005d4a6  lea     rax, [rsp+360h+var_2E8]
0x18005d4ab  mov     [rsp+360h+var_340], rax
0x18005d4b0  lea     rdx, byte_1800C1D6F
0x18005d4b7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005d4bc  jmp     loc_18005D71B
0x18005d4c1  mov     rcx, [rbp+260h+var_2D0]
0x18005d4c5  mov     rax, [rcx]
0x18005d4c8  xor     r8d, r8d
0x18005d4cb  lea     edx, [r8+1]
0x18005d4cf  mov     rax, [rax+88h]
0x18005d4d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d4db  test    eax, eax
0x18005d4dd  jns     short loc_18005D529
0x18005d4df  mov     eax, cs:dword_1800DA020
0x18005d4e5  cmp     eax, 3
0x18005d4e8  jbe     loc_18005D71B
0x18005d4ee  movsxd  rax, dword ptr [rsp+360h+var_300]
0x18005d4f3  mov     [rsp+360h+var_2E8], rax
0x18005d4f8  lea     rax, aAccesscheckWin; "AccessCheck(WINSTATION_QUERY) failed on"...
0x18005d4ff  mov     [rsp+360h+var_318], rax
  ... truncated ...
```
