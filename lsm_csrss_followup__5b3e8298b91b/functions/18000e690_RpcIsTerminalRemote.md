# RpcIsTerminalRemote

- ea: `0x18000e690`
- end: `0x18000ee9e`
- name: `RpcIsTerminalRemote`
- size: `2062`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e010`

## callees

- `0x1800074c0`
- `0x18000e690`
- `0x180014c00`
- `0x1800186a0`
- `0x18001d320`
- `0x18001f87c`
- `0x1800298d4`
- `0x18004b460`
- `0x18004b86c`
- `0x18005b4a0`
- `0x18005fcc4`
- `0x180094040`
- `0x180097010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000ed8a`
- `ntdll!EtwEventWriteTransfer` at `0x18000ed8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee0f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000edeb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ee05`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000edeb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ee05`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000e726`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000e726`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e815`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e8e5`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e9a3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000ea65`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000eb4f`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000ec5f`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e815`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e8e5`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000e9a3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000ea65`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000eb4f`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000ec5f`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000e73e`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000e73e`

## string_xrefs

- `0x18000edb3`: `%s with Trace ID 0x%x Completed`
- `0x18000e9d0`: `CheckAccessToSession(WINSTATION_QUERY)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcIsTerminalRemote(__int64 a1, int a2, bool *a3)
{
  const char *v4; // r14
  struct ISessionManagerInternal *v5; // rbx
  int v6; // edi
  CSessionManager *v7; // rax
  struct ISessionManagerInternal *v8; // rax
  RPC_STATUS v9; // eax
  int v10; // r8d
  int v11; // r9d
  signed int v12; // ecx
  const char *v13; // rax
  RPC_STATUS v14; // eax
  int v15; // r8d
  int v16; // r9d
  signed int v17; // ecx
  const char *v18; // rax
  RPC_STATUS v19; // eax
  int v20; // r8d
  int v21; // r9d
  signed int v22; // ecx
  const char *v23; // rax
  RPC_STATUS v24; // eax
  int v25; // r8d
  int v26; // r9d
  signed int v27; // ecx
  const char *v28; // rax
  RPC_STATUS v29; // eax
  int v30; // r8d
  int v31; // r9d
  signed int v32; // ecx
  const char *v33; // rax
  RPC_STATUS v34; // eax
  signed int v35; // ecx
  const char *v36; // rax
  unsigned int Pid[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v39; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int ClientLocalFlag; // [rsp+5Ch] [rbp-A4h] BYREF
  const char *v41; // [rsp+60h] [rbp-A0h] BYREF
  const char *v42; // [rsp+68h] [rbp-98h] BYREF
  struct ITerminal *v43; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v44[2]; // [rsp+78h] [rbp-88h] BYREF
  struct ITSSession *v45; // [rsp+88h] [rbp-78h] BYREF
  __int64 v46; // [rsp+90h] [rbp-70h] BYREF
  const char *v47; // [rsp+98h] [rbp-68h] BYREF
  __int128 Buf1; // [rsp+A0h] [rbp-60h] BYREF
  void **v49; // [rsp+B0h] [rbp-50h] BYREF
  int v50; // [rsp+C8h] [rbp-38h]
  __int64 v51; // [rsp+D0h] [rbp-30h]
  int v52; // [rsp+D8h] [rbp-28h]
  const char *v53; // [rsp+E0h] [rbp-20h]
  int v54; // [rsp+F0h] [rbp-10h]
  int *v55; // [rsp+300h] [rbp+200h] BYREF
  int v56; // [rsp+308h] [rbp+208h]
  int v57; // [rsp+30Ch] [rbp+20Ch]
  __int16 *v58; // [rsp+310h] [rbp+210h]
  int v59; // [rsp+318h] [rbp+218h]
  int v60; // [rsp+31Ch] [rbp+21Ch]
  const char *v61; // [rsp+320h] [rbp+220h]
  __int64 v62; // [rsp+328h] [rbp+228h]
  const char **v63; // [rsp+330h] [rbp+230h]
  __int64 v64; // [rsp+338h] [rbp+238h]
  const char **v65; // [rsp+340h] [rbp+240h]
  __int64 v66; // [rsp+348h] [rbp+248h]
  const char *v67; // [rsp+350h] [rbp+250h]
  __int64 v68; // [rsp+358h] [rbp+258h]
  const char **v69; // [rsp+360h] [rbp+260h]
  __int64 v70; // [rsp+368h] [rbp+268h]

  v4 = (const char *)a2;
  v5 = 0;
  v46 = 0;
  v45 = 0;
  v43 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)&v49, 0, "RpcIsTerminalRemote");
  if ( !a3 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "pbRemote", "RpcIsTerminalRemote");
    v6 = -2147024809;
    goto LABEL_59;
  }
  ClientLocalFlag = 0;
  if ( I_RpcBindingIsClientLocal(0, &ClientLocalFlag) || !ClientLocalFlag )
  {
    v6 = -2147024846;
    goto LABEL_59;
  }
  if ( (_DWORD)v4 == (unsigned int)WTSGetServiceSessionId() )
  {
    v6 = 0;
    *a3 = 0;
    goto LABEL_65;
  }
  if ( (int)v4 >= 0x10000 )
  {
    v6 = -2147024809;
    goto LABEL_59;
  }
  ClientLocalFlag = -2147467263;
  v5 = ISessionManagerInternal::pSMGlobalInstance;
  if ( ISessionManagerInternal::pSMGlobalInstance )
  {
LABEL_13:
    ClientLocalFlag = 0;
    (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v5 + 8LL))(v5);
    goto LABEL_14;
  }
  v5 = 0;
  v7 = (CSessionManager *)operator new(0x758u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 )
  {
    v8 = CSessionManager::CSessionManager(v7, (int *)&ClientLocalFlag);
    ISessionManagerInternal::pSMGlobalInstance = v8;
    if ( !v8 )
      goto LABEL_14;
    (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v8 + 8LL))(v8);
    v5 = ISessionManagerInternal::pSMGlobalInstance;
    goto LABEL_13;
  }
  ISessionManagerInternal::pSMGlobalInstance = 0;
LABEL_14:
  v6 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v5 + 24LL))(v5, &v46);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct ITSSession **))(*(_QWORD *)v46 + 24LL))(
           v46,
           (unsigned int)v4,
           &v45);
    if ( v6 >= 0 )
    {
      v6 = CheckAccessToSession(v45, 1u, 1);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(struct ITSSession *, struct ITerminal **))(*(_QWORD *)v45 + 104LL))(v45, &v43);
        if ( v6 >= 0 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AgentSessionInteractiveLogon>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AgentSessionInteractiveLogon>::GetImpl'::`2'::impl) )
          {
            Buf1 = 0;
            v39 = 0;
            v6 = (*(__int64 (__fastcall **)(struct ITerminal *, __int128 *, unsigned int *))(*(_QWORD *)v43 + 128LL))(
                   v43,
                   &Buf1,
                   &v39);
            if ( v6 < 0 )
            {
              if ( (unsigned int)dword_1800DA020 > 3 )
              {
                Pid[0] = 0;
                v29 = I_RpcBindingInqLocalClientPID(0, Pid);
                v32 = v29;
                if ( v29 > 0 )
                  v32 = (unsigned __int16)v29 | 0x80070000;
                v33 = 0;
                if ( v32 >= 0 )
                  v33 = (const char *)Pid[0];
                v42 = v33;
                v44[0] = "RpcIsTerminalRemote";
                LODWORD(v41) = v6;
                *(_QWORD *)Pid = "ptrTerminal->GetTerminalType";
                v47 = "Warning HResult failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                  v32,
                  (unsigned int)word_1800C19CA,
                  v30,
                  v31,
                  (__int64)&v47,
                  (__int64)Pid,
                  (__int64)&v41,
                  (__int64)v44,
                  (__int64)&v42);
              }
              goto LABEL_59;
            }
            if ( !(unsigned int)CGlassTerminal::IsLocalGlassTerminal(v43) && !(unsigned int)IsCacheTerminal(v43) )
            {
              *a3 = memcmp_0(&Buf1, TERMINAL_TYPE_AGENT, 0x10u) != 0;
              goto LABEL_65;
            }
          }
          else if ( !(unsigned int)CGlassTerminal::IsLocalGlassTerminal(v43) && !(unsigned int)IsCacheTerminal(v43) )
          {
            *a3 = 1;
            goto LABEL_65;
          }
          *a3 = 0;
          goto LABEL_65;
        }
        if ( (unsigned int)dword_1800DA020 > 3 )
        {
          Pid[0] = 0;
          v24 = I_RpcBindingInqLocalClientPID(0, Pid);
          v27 = v24;
          if ( v24 > 0 )
            v27 = (unsigned __int16)v24 | 0x80070000;
          v28 = 0;
          if ( v27 >= 0 )
            v28 = (const char *)Pid[0];
          v42 = v28;
          v44[0] = "RpcIsTerminalRemote";
          v39 = v6;
          v41 = "ptrSession->getTerminal";
          *(_QWORD *)Pid = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v27,
            (unsigned int)byte_1800C1A1D,
            v25,
            v26,
            (__int64)Pid,
            (__int64)&v41,
            (__int64)&v39,
            (__int64)v44,
            (__int64)&v42);
        }
      }
      else if ( (unsigned int)dword_1800DA020 > 3 )
      {
        Pid[0] = 0;
        v19 = I_RpcBindingInqLocalClientPID(0, Pid);
        v22 = v19;
        if ( v19 > 0 )
          v22 = (unsigned __int16)v19 | 0x80070000;
        v23 = 0;
        if ( v22 >= 0 )
          v23 = (const char *)Pid[0];
        v42 = v23;
        v44[0] = "RpcIsTerminalRemote";
        v39 = v6;
        v41 = "CheckAccessToSession(WINSTATION_QUERY)";
        *(_QWORD *)Pid = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v22,
          (unsigned int)qword_1800C1A70,
          v20,
          v21,
          (__int64)Pid,
          (__int64)&v41,
          (__int64)&v39,
          (__int64)v44,
          (__int64)&v42);
      }
    }
    else if ( (unsigned int)dword_1800DA020 > 3 )
    {
      Pid[0] = 0;
      v14 = I_RpcBindingInqLocalClientPID(0, Pid);
      v17 = v14;
      if ( v14 > 0 )
        v17 = (unsigned __int16)v14 | 0x80070000;
      v18 = 0;
      if ( v17 >= 0 )
        v18 = (const char *)Pid[0];
      v42 = v18;
      v44[0] = "RpcIsTerminalRemote";
      v39 = v6;
      v41 = "FindSessionById";
      *(_QWORD *)Pid = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v17,
        (unsigned int)byte_1800C1AC3,
        v15,
        v16,
        (__int64)Pid,
        (__int64)&v41,
        (__int64)&v39,
        (__int64)v44,
        (__int64)&v42);
    }
  }
  else if ( (unsigned int)dword_1800DA020 > 3 )
  {
    Pid[0] = 0;
    v9 = I_RpcBindingInqLocalClientPID(0, Pid);
    v12 = v9;
    if ( v9 > 0 )
      v12 = (unsigned __int16)v9 | 0x80070000;
    v13 = 0;
    if ( v12 >= 0 )
      v13 = (const char *)Pid[0];
    v41 = v13;
    *(_QWORD *)Pid = "RpcIsTerminalRemote";
    v39 = v6;
    v44[0] = "GetSessionList";
    v42 = "Warning HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      v12,
      (unsigned int)&word_1800C1B16,
      v10,
      v11,
      (__int64)&v42,
      (__int64)v44,
      (__int64)&v39,
      (__int64)Pid,
      (__int64)&v41);
  }
LABEL_59:
  if ( (unsigned int)dword_1800DA020 > 3 )
  {
    v47 = v4;
    LODWORD(v41) = v6;
    Pid[0] = 0;
    v34 = I_RpcBindingInqLocalClientPID(0, Pid);
    v35 = v34;
    if ( v34 > 0 )
      v35 = (unsigned __int16)v34 | 0x80070000;
    v36 = 0;
    if ( v35 >= 0 )
      v36 = (const char *)Pid[0];
    v42 = v36;
    v69 = &v47;
    v70 = 8;
    v67 = "RpcIsTerminalRemote";
    v68 = 20;
    v65 = &v41;
    v66 = 4;
    v63 = &v42;
    v64 = 8;
    v61 = "RPC call to us failed from another process. It was called with these parameters.";
    v62 = 81;
    v44[0] = 0x14030B000000LL;
    v44[1] = 0;
    v55 = off_1800DA028;
    v56 = *(unsigned __int16 *)off_1800DA028;
    v57 = 2;
    v58 = word_1800C1982;
    v59 = 71;
    v60 = 1;
    v39 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(RegHandle, v44, 0, 0, 7, &v55);
  }
LABEL_65:
  v49 = &CRpcCallTrace::`vftable';
  if ( v54 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v53, v50);
  v49 = &CTraceBase::`vftable';
  if ( !v52 && CTraceBase::g_bEnabled && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_75;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_75:
  v51 = 0;
  if ( v43 )
    (*(void (__fastcall **)(struct ITerminal *))(*(_QWORD *)v43 + 16LL))(v43);
  if ( v45 )
    (*(void (__fastcall **)(struct ITSSession *))(*(_QWORD *)v45 + 16LL))(v45);
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  if ( v5 )
    (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v5 + 16LL))(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e690  mov     [rsp-8+arg_0], rbx
0x18000e695  mov     [rsp-8+arg_18], rsi
0x18000e69a  push    rbp
0x18000e69b  push    rdi
0x18000e69c  push    r12
0x18000e69e  push    r14
0x18000e6a0  push    r15
0x18000e6a2  lea     rbp, [rsp-280h]
0x18000e6aa  sub     rsp, 380h
0x18000e6b1  mov     rax, cs:__security_cookie
0x18000e6b8  xor     rax, rsp
0x18000e6bb  mov     [rbp+2A0h+var_30], rax
0x18000e6c2  mov     rsi, r8
0x18000e6c5  movsxd  r14, edx
0x18000e6c8  xor     r15d, r15d
0x18000e6cb  mov     ebx, r15d
0x18000e6ce  mov     [rbp+2A0h+var_310], r15
0x18000e6d2  mov     [rbp+2A0h+var_318], r15
0x18000e6d6  mov     [rsp+3A0h+var_330], r15
0x18000e6db  lea     r12, aRpcisterminalr_0; "RpcIsTerminalRemote"
0x18000e6e2  mov     r8, r12; char *
0x18000e6e5  xor     edx, edx; int
0x18000e6e7  lea     rcx, [rbp+2A0h+var_2F0]; this
0x18000e6eb  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18000e6f0  test    rsi, rsi
0x18000e6f3  jnz     short loc_18000E71A
0x18000e6f5  mov     r9, r12
0x18000e6f8  lea     r8, aPbremote; "pbRemote"
0x18000e6ff  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18000e706  mov     ecx, 8; int
0x18000e70b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e710  mov     edi, 80070057h
0x18000e715  jmp     loc_18000EC3C
0x18000e71a  mov     [rsp+3A0h+ClientLocalFlag], r15d
0x18000e71f  lea     rdx, [rsp+3A0h+ClientLocalFlag]; ClientLocalFlag
0x18000e724  xor     ecx, ecx; BindingHandle
0x18000e726  call    cs:__imp_I_RpcBindingIsClientLocal
0x18000e72c  test    eax, eax
0x18000e72e  jnz     loc_18000EC37
0x18000e734  cmp     [rsp+3A0h+ClientLocalFlag], ebx
0x18000e738  jz      loc_18000EC37
0x18000e73e  call    cs:__imp_WTSGetServiceSessionId
0x18000e744  cmp     r14d, eax
0x18000e747  jnz     short loc_18000E753
0x18000e749  mov     edi, r15d
0x18000e74c  mov     [rsi], bl
0x18000e74e  jmp     loc_18000ED91
0x18000e753  cmp     r14d, 10000h
0x18000e75a  jl      short loc_18000E766
0x18000e75c  mov     edi, 80070057h
0x18000e761  jmp     loc_18000EC3C
0x18000e766  mov     [rsp+3A0h+ClientLocalFlag], 80004001h
0x18000e76e  mov     rbx, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x18000e775  test    rbx, rbx
0x18000e778  jnz     short loc_18000E7C9
0x18000e77a  mov     rbx, r15
0x18000e77d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e784  mov     ecx, 758h; unsigned __int64
0x18000e789  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e78e  test    rax, rax
0x18000e791  jz      loc_18000E89D
0x18000e797  lea     rdx, [rsp+3A0h+ClientLocalFlag]; int *
0x18000e79c  mov     rcx, rax; this
0x18000e79f  call    ??0CSessionManager@@QEAA@PEAJ@Z; CSessionManager::CSessionManager(long *)
0x18000e7a4  mov     rdx, rax
0x18000e7a7  mov     cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA, rax; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x18000e7ae  test    rax, rax
0x18000e7b1  jz      short loc_18000E7DD
0x18000e7b3  mov     rcx, [rax]
0x18000e7b6  mov     rax, [rcx+8]
0x18000e7ba  mov     rcx, rdx
0x18000e7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7c2  mov     rbx, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x18000e7c9  mov     [rsp+3A0h+ClientLocalFlag], r15d
0x18000e7ce  mov     rax, [rbx]
0x18000e7d1  mov     rcx, rbx
0x18000e7d4  mov     rax, [rax+8]
0x18000e7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7dd  mov     rax, [rbx]
0x18000e7e0  lea     rdx, [rbp+2A0h+var_310]
0x18000e7e4  mov     rcx, rbx
0x18000e7e7  mov     rax, [rax+18h]
0x18000e7eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7f0  mov     edi, eax
0x18000e7f2  test    eax, eax
0x18000e7f4  jns     loc_18000E8A9
0x18000e7fa  mov     ecx, cs:dword_1800DA020
0x18000e800  cmp     ecx, 3
0x18000e803  jbe     loc_18000EC3C
0x18000e809  mov     [rsp+3A0h+Pid], r15d
0x18000e80e  lea     rdx, [rsp+3A0h+Pid]; Pid
0x18000e813  xor     ecx, ecx; Binding
0x18000e815  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000e81b  mov     ecx, eax
0x18000e81d  test    eax, eax
0x18000e81f  jle     short loc_18000E82A
0x18000e821  movzx   ecx, ax
0x18000e824  or      ecx, 80070000h
0x18000e82a  mov     eax, r15d
0x18000e82d  test    ecx, ecx
0x18000e82f  cmovns  eax, [rsp+3A0h+Pid]
0x18000e834  mov     [rsp+3A0h+var_340], rax
0x18000e839  mov     qword ptr [rsp+3A0h+Pid], r12
0x18000e83e  mov     [rsp+3A0h+var_348], edi
0x18000e842  lea     rax, aGetsessionlist_2; "GetSessionList"
0x18000e849  mov     [rsp+3A0h+var_328], rax
0x18000e84e  lea     rax, aWarningHresult; "Warning HResult failed"
0x18000e855  mov     [rsp+3A0h+var_338], rax
0x18000e85a  lea     rax, [rsp+3A0h+var_340]
0x18000e85f  mov     [rsp+3A0h+var_360], rax
0x18000e864  lea     rax, [rsp+3A0h+Pid]
0x18000e869  mov     [rsp+3A0h+var_368], rax
0x18000e86e  lea     rax, [rsp+3A0h+var_348]
0x18000e873  mov     [rsp+3A0h+var_370], rax
0x18000e878  lea     rax, [rsp+3A0h+var_328]
0x18000e87d  mov     [rsp+3A0h+var_378], rax
0x18000e882  lea     rax, [rsp+3A0h+var_338]
0x18000e887  mov     [rsp+3A0h+var_380], rax
0x18000e88c  lea     rdx, word_1800C1B16
0x18000e893  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000e898  jmp     loc_18000EC3C
0x18000e89d  mov     cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA, r15; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x18000e8a4  jmp     loc_18000E7DD
0x18000e8a9  mov     rcx, [rbp+2A0h+var_310]
0x18000e8ad  mov     rax, [rcx]
0x18000e8b0  lea     r8, [rbp+2A0h+var_318]
0x18000e8b4  mov     edx, r14d
0x18000e8b7  mov     rax, [rax+18h]
0x18000e8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8c0  mov     edi, eax
0x18000e8c2  test    eax, eax
0x18000e8c4  jns     loc_18000E96D
0x18000e8ca  mov     eax, cs:dword_1800DA020
0x18000e8d0  cmp     eax, 3
0x18000e8d3  jbe     loc_18000EC3C
0x18000e8d9  mov     [rsp+3A0h+Pid], r15d
0x18000e8de  lea     rdx, [rsp+3A0h+Pid]; Pid
0x18000e8e3  xor     ecx, ecx; Binding
0x18000e8e5  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000e8eb  mov     ecx, eax
0x18000e8ed  test    eax, eax
0x18000e8ef  jle     short loc_18000E8FA
0x18000e8f1  movzx   ecx, ax
0x18000e8f4  or      ecx, 80070000h
0x18000e8fa  mov     eax, r15d
0x18000e8fd  test    ecx, ecx
0x18000e8ff  cmovns  eax, [rsp+3A0h+Pid]
0x18000e904  mov     [rsp+3A0h+var_338], rax
0x18000e909  mov     [rsp+3A0h+var_328], r12
0x18000e90e  mov     [rsp+3A0h+var_348], edi
0x18000e912  lea     rax, aFindsessionbyi_2; "FindSessionById"
0x18000e919  mov     [rsp+3A0h+var_340], rax
0x18000e91e  lea     rax, aWarningHresult; "Warning HResult failed"
0x18000e925  mov     qword ptr [rsp+3A0h+Pid], rax
0x18000e92a  lea     rax, [rsp+3A0h+var_338]
0x18000e92f  mov     [rsp+3A0h+var_360], rax
0x18000e934  lea     rax, [rsp+3A0h+var_328]
0x18000e939  mov     [rsp+3A0h+var_368], rax
0x18000e93e  lea     rax, [rsp+3A0h+var_348]
0x18000e943  mov     [rsp+3A0h+var_370], rax
0x18000e948  lea     rax, [rsp+3A0h+var_340]
0x18000e94d  mov     [rsp+3A0h+var_378], rax
0x18000e952  lea     rax, [rsp+3A0h+Pid]
0x18000e957  mov     [rsp+3A0h+var_380], rax
0x18000e95c  lea     rdx, byte_1800C1AC3
0x18000e963  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000e968  jmp     loc_18000EC3C
0x18000e96d  mov     edx, 1; unsigned int
0x18000e972  mov     r8d, edx; int
0x18000e975  mov     rcx, [rbp+2A0h+var_318]; struct ITSSession *
0x18000e979  call    ?CheckAccessToSession@@YAJPEAUITSSession@@KH@Z; CheckAccessToSession(ITSSession *,ulong,int)
0x18000e97e  mov     edi, eax
0x18000e980  test    eax, eax
0x18000e982  jns     loc_18000EA2B
0x18000e988  mov     eax, cs:dword_1800DA020
0x18000e98e  cmp     eax, 3
0x18000e991  jbe     loc_18000EC3C
0x18000e997  mov     [rsp+3A0h+Pid], r15d
0x18000e99c  lea     rdx, [rsp+3A0h+Pid]; Pid
0x18000e9a1  xor     ecx, ecx; Binding
0x18000e9a3  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000e9a9  mov     ecx, eax
0x18000e9ab  test    eax, eax
0x18000e9ad  jle     short loc_18000E9B8
0x18000e9af  movzx   ecx, ax
0x18000e9b2  or      ecx, 80070000h
0x18000e9b8  mov     eax, r15d
0x18000e9bb  test    ecx, ecx
0x18000e9bd  cmovns  eax, [rsp+3A0h+Pid]
0x18000e9c2  mov     [rsp+3A0h+var_338], rax
0x18000e9c7  mov     [rsp+3A0h+var_328], r12
0x18000e9cc  mov     [rsp+3A0h+var_348], edi
0x18000e9d0  lea     rax, aCheckaccesstos; "CheckAccessToSession(WINSTATION_QUERY)"
0x18000e9d7  mov     [rsp+3A0h+var_340], rax
0x18000e9dc  lea     rax, aWarningHresult; "Warning HResult failed"
0x18000e9e3  mov     qword ptr [rsp+3A0h+Pid], rax
0x18000e9e8  lea     rax, [rsp+3A0h+var_338]
0x18000e9ed  mov     [rsp+3A0h+var_360], rax
0x18000e9f2  lea     rax, [rsp+3A0h+var_328]
0x18000e9f7  mov     [rsp+3A0h+var_368], rax
0x18000e9fc  lea     rax, [rsp+3A0h+var_348]
0x18000ea01  mov     [rsp+3A0h+var_370], rax
0x18000ea06  lea     rax, [rsp+3A0h+var_340]
0x18000ea0b  mov     [rsp+3A0h+var_378], rax
0x18000ea10  lea     rax, [rsp+3A0h+Pid]
0x18000ea15  mov     [rsp+3A0h+var_380], rax
0x18000ea1a  lea     rdx, qword_1800C1A70
0x18000ea21  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000ea26  jmp     loc_18000EC3C
0x18000ea2b  mov     rcx, [rbp+2A0h+var_318]
0x18000ea2f  mov     rax, [rcx]
0x18000ea32  lea     rdx, [rsp+3A0h+var_330]
0x18000ea37  mov     rax, [rax+68h]
0x18000ea3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea40  mov     edi, eax
0x18000ea42  test    eax, eax
0x18000ea44  jns     loc_18000EAED
0x18000ea4a  mov     eax, cs:dword_1800DA020
0x18000ea50  cmp     eax, 3
0x18000ea53  jbe     loc_18000EC3C
0x18000ea59  mov     [rsp+3A0h+Pid], r15d
0x18000ea5e  lea     rdx, [rsp+3A0h+Pid]; Pid
0x18000ea63  xor     ecx, ecx; Binding
0x18000ea65  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000ea6b  mov     ecx, eax
0x18000ea6d  test    eax, eax
0x18000ea6f  jle     short loc_18000EA7A
0x18000ea71  movzx   ecx, ax
0x18000ea74  or      ecx, 80070000h
0x18000ea7a  mov     eax, r15d
0x18000ea7d  test    ecx, ecx
0x18000ea7f  cmovns  eax, [rsp+3A0h+Pid]
0x18000ea84  mov     [rsp+3A0h+var_338], rax
0x18000ea89  mov     [rsp+3A0h+var_328], r12
0x18000ea8e  mov     [rsp+3A0h+var_348], edi
0x18000ea92  lea     rax, aPtrsessionGett_1; "ptrSession->getTerminal"
0x18000ea99  mov     [rsp+3A0h+var_340], rax
0x18000ea9e  lea     rax, aWarningHresult; "Warning HResult failed"
0x18000eaa5  mov     qword ptr [rsp+3A0h+Pid], rax
0x18000eaaa  lea     rax, [rsp+3A0h+var_338]
0x18000eaaf  mov     [rsp+3A0h+var_360], rax
0x18000eab4  lea     rax, [rsp+3A0h+var_328]
0x18000eab9  mov     [rsp+3A0h+var_368], rax
0x18000eabe  lea     rax, [rsp+3A0h+var_348]
0x18000eac3  mov     [rsp+3A0h+var_370], rax
0x18000eac8  lea     rax, [rsp+3A0h+var_340]
0x18000eacd  mov     [rsp+3A0h+var_378], rax
0x18000ead2  lea     rax, [rsp+3A0h+Pid]
0x18000ead7  mov     [rsp+3A0h+var_380], rax
0x18000eadc  lea     rdx, byte_1800C1A1D
0x18000eae3  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000eae8  jmp     loc_18000EC3C
0x18000eaed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AgentSessionInteractiveLogon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AgentSessionInteractiveLogon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AgentSessionInteractiveLogon> `wil::Feature<__WilFeatureTraits_Feature_AgentSessionInteractiveLogon>::GetImpl(void)'::`2'::impl
0x18000eaf4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AgentSessionInteractiveLogon@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AgentSessionInteractiveLogon>::__private_IsEnabled(void)
0x18000eaf9  mov     rcx, [rsp+3A0h+var_330]; struct ITerminal *
0x18000eafe  test    al, al
0x18000eb00  jz      loc_18000EC18
0x18000eb06  xorps   xmm0, xmm0
0x18000eb09  movups  [rbp+2A0h+Buf1], xmm0
0x18000eb0d  mov     [rsp+3A0h+var_348], r15d
0x18000eb12  mov     rax, [rcx]
0x18000eb15  lea     r8, [rsp+3A0h+var_348]
0x18000eb1a  lea     rdx, [rbp+2A0h+Buf1]
0x18000eb1e  mov     rax, [rax+80h]
0x18000eb25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb2a  mov     edi, eax
0x18000eb2c  test    eax, eax
0x18000eb2e  jns     loc_18000EBD2
0x18000eb34  mov     eax, cs:dword_1800DA020
0x18000eb3a  cmp     eax, 3
0x18000eb3d  jbe     loc_18000EC3C
0x18000eb43  mov     [rsp+3A0h+Pid], r15d
0x18000eb48  lea     rdx, [rsp+3A0h+Pid]; Pid
0x18000eb4d  xor     ecx, ecx; Binding
0x18000eb4f  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000eb55  mov     ecx, eax
0x18000eb57  test    eax, eax
0x18000eb59  jle     short loc_18000EB64
0x18000eb5b  movzx   ecx, ax
0x18000eb5e  or      ecx, 80070000h
0x18000eb64  mov     eax, r15d
0x18000eb67  test    ecx, ecx
0x18000eb69  cmovns  eax, [rsp+3A0h+Pid]
0x18000eb6e  mov     [rsp+3A0h+var_338], rax
0x18000eb73  mov     [rsp+3A0h+var_328], r12
0x18000eb78  mov     dword ptr [rsp+3A0h+var_340], edi
0x18000eb7c  lea     rax, aPtrterminalGet_0; "ptrTerminal->GetTerminalType"
0x18000eb83  mov     qword ptr [rsp+3A0h+Pid], rax
0x18000eb88  lea     rax, aWarningHresult; "Warning HResult failed"
0x18000eb8f  mov     [rbp+2A0h+var_308], rax
0x18000eb93  lea     rax, [rsp+3A0h+var_338]
0x18000eb98  mov     [rsp+3A0h+var_360], rax
0x18000eb9d  lea     rax, [rsp+3A0h+var_328]
0x18000eba2  mov     [rsp+3A0h+var_368], rax
0x18000eba7  lea     rax, [rsp+3A0h+var_340]
0x18000ebac  mov     [rsp+3A0h+var_370], rax
0x18000ebb1  lea     rax, [rsp+3A0h+Pid]
0x18000ebb6  mov     [rsp+3A0h+var_378], rax
0x18000ebbb  lea     rax, [rbp+2A0h+var_308]
0x18000ebbf  mov     [rsp+3A0h+var_380], rax
  ... truncated ...
```
