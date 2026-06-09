# RpcIsTerminalRemote

- ea: `0x180020b00`
- end: `0x1800212c6`
- name: `RpcIsTerminalRemote`
- size: `1990`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task`

## callers

- `0x1800203e0`

## callees

- `0x1800077a0`
- `0x18000c6b0`
- `0x18000e8b0`
- `0x18000f260`
- `0x18001e6f0`
- `0x180020b00`
- `0x180021c80`
- `0x18002bc84`
- `0x18004e850`
- `0x18004ec5c`
- `0x18005eea8`
- `0x1800637cc`
- `0x180099590`
- `0x18009c010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18002122a`
- `ntdll!EtwEventWriteTransfer` at `0x18002122a`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180020b96`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180020b96`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020c91`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020d67`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020e2b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020ef3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020fe3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800210f9`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020c91`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020d67`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020e2b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020ef3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020fe3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800210f9`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180020bb4`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180020bb4`

## string_xrefs

- `0x180020e5e`: `CheckAccessToSession(WINSTATION_QUERY)`

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
  _BYTE v49[592]; // [rsp+B0h] [rbp-50h] BYREF
  int *v50; // [rsp+300h] [rbp+200h] BYREF
  int v51; // [rsp+308h] [rbp+208h]
  int v52; // [rsp+30Ch] [rbp+20Ch]
  __int16 *v53; // [rsp+310h] [rbp+210h]
  int v54; // [rsp+318h] [rbp+218h]
  int v55; // [rsp+31Ch] [rbp+21Ch]
  const char *v56; // [rsp+320h] [rbp+220h]
  __int64 v57; // [rsp+328h] [rbp+228h]
  const char **v58; // [rsp+330h] [rbp+230h]
  __int64 v59; // [rsp+338h] [rbp+238h]
  const char **v60; // [rsp+340h] [rbp+240h]
  __int64 v61; // [rsp+348h] [rbp+248h]
  const char *v62; // [rsp+350h] [rbp+250h]
  __int64 v63; // [rsp+358h] [rbp+258h]
  const char **v64; // [rsp+360h] [rbp+260h]
  __int64 v65; // [rsp+368h] [rbp+268h]

  v4 = (const char *)a2;
  v5 = 0;
  v46 = 0;
  v45 = 0;
  v43 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v49, 0, "RpcIsTerminalRemote");
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
              if ( (unsigned int)dword_1800DF020 > 3 )
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
                  (unsigned int)word_1800C6B52,
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
        if ( (unsigned int)dword_1800DF020 > 3 )
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
            (unsigned int)byte_1800C6BA5,
            v25,
            v26,
            (__int64)Pid,
            (__int64)&v41,
            (__int64)&v39,
            (__int64)v44,
            (__int64)&v42);
        }
      }
      else if ( (unsigned int)dword_1800DF020 > 3 )
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
          (unsigned int)qword_1800C6BF8,
          v20,
          v21,
          (__int64)Pid,
          (__int64)&v41,
          (__int64)&v39,
          (__int64)v44,
          (__int64)&v42);
      }
    }
    else if ( (unsigned int)dword_1800DF020 > 3 )
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
        (unsigned int)byte_1800C6C4B,
        v15,
        v16,
        (__int64)Pid,
        (__int64)&v41,
        (__int64)&v39,
        (__int64)v44,
        (__int64)&v42);
    }
  }
  else if ( (unsigned int)dword_1800DF020 > 3 )
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
      (unsigned int)&word_1800C6C9E,
      v10,
      v11,
      (__int64)&v42,
      (__int64)v44,
      (__int64)&v39,
      (__int64)Pid,
      (__int64)&v41);
  }
LABEL_59:
  if ( (unsigned int)dword_1800DF020 > 3 )
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
    v64 = &v47;
    v65 = 8;
    v62 = "RpcIsTerminalRemote";
    v63 = 20;
    v60 = &v41;
    v61 = 4;
    v58 = &v42;
    v59 = 8;
    v56 = "RPC call to us failed from another process. It was called with these parameters.";
    v57 = 81;
    v44[0] = 0x14030B000000LL;
    v44[1] = 0;
    v50 = off_1800DF028;
    v51 = *(unsigned __int16 *)off_1800DF028;
    v52 = 2;
    v53 = word_1800C6B0A;
    v54 = 71;
    v55 = 1;
    v39 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(RegHandle, v44, 0, 0, 7, &v50);
  }
LABEL_65:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v49);
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
0x180020b00  mov     [rsp-8+arg_0], rbx
0x180020b05  mov     [rsp-8+arg_18], rsi
0x180020b0a  push    rbp
0x180020b0b  push    rdi
0x180020b0c  push    r12
0x180020b0e  push    r14
0x180020b10  push    r15
0x180020b12  lea     rbp, [rsp-280h]
0x180020b1a  sub     rsp, 380h
0x180020b21  mov     rax, cs:__security_cookie
0x180020b28  xor     rax, rsp
0x180020b2b  mov     [rbp+2A0h+var_30], rax
0x180020b32  mov     rsi, r8
0x180020b35  movsxd  r14, edx
0x180020b38  xor     r15d, r15d
0x180020b3b  mov     ebx, r15d
0x180020b3e  mov     [rbp+2A0h+var_310], r15
0x180020b42  mov     [rbp+2A0h+var_318], r15
0x180020b46  mov     [rsp+3A0h+var_330], r15
0x180020b4b  lea     r12, aRpcisterminalr_0; "RpcIsTerminalRemote"
0x180020b52  mov     r8, r12; char *
0x180020b55  xor     edx, edx; int
0x180020b57  lea     rcx, [rbp+2A0h+var_2F0]; this
0x180020b5b  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180020b60  test    rsi, rsi
0x180020b63  jnz     short loc_180020B8A
0x180020b65  mov     r9, r12
0x180020b68  lea     r8, aPbremote; "pbRemote"
0x180020b6f  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180020b76  mov     ecx, 8; int
0x180020b7b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020b80  mov     edi, 80070057h
0x180020b85  jmp     loc_1800210D6
0x180020b8a  mov     [rsp+3A0h+ClientLocalFlag], r15d
0x180020b8f  lea     rdx, [rsp+3A0h+ClientLocalFlag]; ClientLocalFlag
0x180020b94  xor     ecx, ecx; BindingHandle
0x180020b96  call    cs:__imp_I_RpcBindingIsClientLocal
0x180020b9d  nop     dword ptr [rax+rax+00h]
0x180020ba2  test    eax, eax
0x180020ba4  jnz     loc_1800210D1
0x180020baa  cmp     [rsp+3A0h+ClientLocalFlag], ebx
0x180020bae  jz      loc_1800210D1
0x180020bb4  call    cs:__imp_WTSGetServiceSessionId
0x180020bbb  nop     dword ptr [rax+rax+00h]
0x180020bc0  cmp     r14d, eax
0x180020bc3  jnz     short loc_180020BCF
0x180020bc5  mov     edi, r15d
0x180020bc8  mov     [rsi], bl
0x180020bca  jmp     loc_180021236
0x180020bcf  cmp     r14d, 10000h
0x180020bd6  jl      short loc_180020BE2
0x180020bd8  mov     edi, 80070057h
0x180020bdd  jmp     loc_1800210D6
0x180020be2  mov     [rsp+3A0h+ClientLocalFlag], 80004001h
0x180020bea  mov     rbx, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x180020bf1  test    rbx, rbx
0x180020bf4  jnz     short loc_180020C45
0x180020bf6  mov     rbx, r15
0x180020bf9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020c00  mov     ecx, 758h; unsigned __int64
0x180020c05  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020c0a  test    rax, rax
0x180020c0d  jz      loc_180020D1F
0x180020c13  lea     rdx, [rsp+3A0h+ClientLocalFlag]; int *
0x180020c18  mov     rcx, rax; this
0x180020c1b  call    ??0CSessionManager@@QEAA@PEAJ@Z; CSessionManager::CSessionManager(long *)
0x180020c20  mov     rdx, rax
0x180020c23  mov     cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA, rax; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x180020c2a  test    rax, rax
0x180020c2d  jz      short loc_180020C59
0x180020c2f  mov     rcx, [rax]
0x180020c32  mov     rax, [rcx+8]
0x180020c36  mov     rcx, rdx
0x180020c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c3e  mov     rbx, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x180020c45  mov     [rsp+3A0h+ClientLocalFlag], r15d
0x180020c4a  mov     rax, [rbx]
0x180020c4d  mov     rcx, rbx
0x180020c50  mov     rax, [rax+8]
0x180020c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c59  mov     rax, [rbx]
0x180020c5c  lea     rdx, [rbp+2A0h+var_310]
0x180020c60  mov     rcx, rbx
0x180020c63  mov     rax, [rax+18h]
0x180020c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c6c  mov     edi, eax
0x180020c6e  test    eax, eax
0x180020c70  jns     loc_180020D2B
0x180020c76  mov     ecx, cs:dword_1800DF020
0x180020c7c  cmp     ecx, 3
0x180020c7f  jbe     loc_1800210D6
0x180020c85  mov     [rsp+3A0h+Pid], r15d
0x180020c8a  lea     rdx, [rsp+3A0h+Pid]; Pid
0x180020c8f  xor     ecx, ecx; Binding
0x180020c91  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180020c98  nop     dword ptr [rax+rax+00h]
0x180020c9d  mov     ecx, eax
0x180020c9f  test    eax, eax
0x180020ca1  jle     short loc_180020CAC
0x180020ca3  movzx   ecx, ax
0x180020ca6  or      ecx, 80070000h
0x180020cac  mov     eax, r15d
0x180020caf  test    ecx, ecx
0x180020cb1  cmovns  eax, [rsp+3A0h+Pid]
0x180020cb6  mov     [rsp+3A0h+var_340], rax
0x180020cbb  mov     qword ptr [rsp+3A0h+Pid], r12
0x180020cc0  mov     [rsp+3A0h+var_348], edi
0x180020cc4  lea     rax, aGetsessionlist_2; "GetSessionList"
0x180020ccb  mov     [rsp+3A0h+var_328], rax
0x180020cd0  lea     rax, aWarningHresult; "Warning HResult failed"
0x180020cd7  mov     [rsp+3A0h+var_338], rax
0x180020cdc  lea     rax, [rsp+3A0h+var_340]
0x180020ce1  mov     [rsp+3A0h+var_360], rax
0x180020ce6  lea     rax, [rsp+3A0h+Pid]
0x180020ceb  mov     [rsp+3A0h+var_368], rax
0x180020cf0  lea     rax, [rsp+3A0h+var_348]
0x180020cf5  mov     [rsp+3A0h+var_370], rax
0x180020cfa  lea     rax, [rsp+3A0h+var_328]
0x180020cff  mov     [rsp+3A0h+var_378], rax
0x180020d04  lea     rax, [rsp+3A0h+var_338]
0x180020d09  mov     [rsp+3A0h+var_380], rax
0x180020d0e  lea     rdx, word_1800C6C9E
0x180020d15  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180020d1a  jmp     loc_1800210D6
0x180020d1f  mov     cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA, r15; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x180020d26  jmp     loc_180020C59
0x180020d2b  mov     rcx, [rbp+2A0h+var_310]
0x180020d2f  mov     rax, [rcx]
0x180020d32  lea     r8, [rbp+2A0h+var_318]
0x180020d36  mov     edx, r14d
0x180020d39  mov     rax, [rax+18h]
0x180020d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d42  mov     edi, eax
0x180020d44  test    eax, eax
0x180020d46  jns     loc_180020DF5
0x180020d4c  mov     eax, cs:dword_1800DF020
0x180020d52  cmp     eax, 3
0x180020d55  jbe     loc_1800210D6
0x180020d5b  mov     [rsp+3A0h+Pid], r15d
0x180020d60  lea     rdx, [rsp+3A0h+Pid]; Pid
0x180020d65  xor     ecx, ecx; Binding
0x180020d67  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180020d6e  nop     dword ptr [rax+rax+00h]
0x180020d73  mov     ecx, eax
0x180020d75  test    eax, eax
0x180020d77  jle     short loc_180020D82
0x180020d79  movzx   ecx, ax
0x180020d7c  or      ecx, 80070000h
0x180020d82  mov     eax, r15d
0x180020d85  test    ecx, ecx
0x180020d87  cmovns  eax, [rsp+3A0h+Pid]
0x180020d8c  mov     [rsp+3A0h+var_338], rax
0x180020d91  mov     [rsp+3A0h+var_328], r12
0x180020d96  mov     [rsp+3A0h+var_348], edi
0x180020d9a  lea     rax, aFindsessionbyi_2; "FindSessionById"
0x180020da1  mov     [rsp+3A0h+var_340], rax
0x180020da6  lea     rax, aWarningHresult; "Warning HResult failed"
0x180020dad  mov     qword ptr [rsp+3A0h+Pid], rax
0x180020db2  lea     rax, [rsp+3A0h+var_338]
0x180020db7  mov     [rsp+3A0h+var_360], rax
0x180020dbc  lea     rax, [rsp+3A0h+var_328]
0x180020dc1  mov     [rsp+3A0h+var_368], rax
0x180020dc6  lea     rax, [rsp+3A0h+var_348]
0x180020dcb  mov     [rsp+3A0h+var_370], rax
0x180020dd0  lea     rax, [rsp+3A0h+var_340]
0x180020dd5  mov     [rsp+3A0h+var_378], rax
0x180020dda  lea     rax, [rsp+3A0h+Pid]
0x180020ddf  mov     [rsp+3A0h+var_380], rax
0x180020de4  lea     rdx, byte_1800C6C4B
0x180020deb  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180020df0  jmp     loc_1800210D6
0x180020df5  mov     edx, 1; unsigned int
0x180020dfa  mov     r8d, edx; int
0x180020dfd  mov     rcx, [rbp+2A0h+var_318]; struct ITSSession *
0x180020e01  call    ?CheckAccessToSession@@YAJPEAUITSSession@@KH@Z; CheckAccessToSession(ITSSession *,ulong,int)
0x180020e06  mov     edi, eax
0x180020e08  test    eax, eax
0x180020e0a  jns     loc_180020EB9
0x180020e10  mov     eax, cs:dword_1800DF020
0x180020e16  cmp     eax, 3
0x180020e19  jbe     loc_1800210D6
0x180020e1f  mov     [rsp+3A0h+Pid], r15d
0x180020e24  lea     rdx, [rsp+3A0h+Pid]; Pid
0x180020e29  xor     ecx, ecx; Binding
0x180020e2b  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180020e32  nop     dword ptr [rax+rax+00h]
0x180020e37  mov     ecx, eax
0x180020e39  test    eax, eax
0x180020e3b  jle     short loc_180020E46
0x180020e3d  movzx   ecx, ax
0x180020e40  or      ecx, 80070000h
0x180020e46  mov     eax, r15d
0x180020e49  test    ecx, ecx
0x180020e4b  cmovns  eax, [rsp+3A0h+Pid]
0x180020e50  mov     [rsp+3A0h+var_338], rax
0x180020e55  mov     [rsp+3A0h+var_328], r12
0x180020e5a  mov     [rsp+3A0h+var_348], edi
0x180020e5e  lea     rax, aCheckaccesstos; "CheckAccessToSession(WINSTATION_QUERY)"
0x180020e65  mov     [rsp+3A0h+var_340], rax
0x180020e6a  lea     rax, aWarningHresult; "Warning HResult failed"
0x180020e71  mov     qword ptr [rsp+3A0h+Pid], rax
0x180020e76  lea     rax, [rsp+3A0h+var_338]
0x180020e7b  mov     [rsp+3A0h+var_360], rax
0x180020e80  lea     rax, [rsp+3A0h+var_328]
0x180020e85  mov     [rsp+3A0h+var_368], rax
0x180020e8a  lea     rax, [rsp+3A0h+var_348]
0x180020e8f  mov     [rsp+3A0h+var_370], rax
0x180020e94  lea     rax, [rsp+3A0h+var_340]
0x180020e99  mov     [rsp+3A0h+var_378], rax
0x180020e9e  lea     rax, [rsp+3A0h+Pid]
0x180020ea3  mov     [rsp+3A0h+var_380], rax
0x180020ea8  lea     rdx, qword_1800C6BF8
0x180020eaf  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180020eb4  jmp     loc_1800210D6
0x180020eb9  mov     rcx, [rbp+2A0h+var_318]
0x180020ebd  mov     rax, [rcx]
0x180020ec0  lea     rdx, [rsp+3A0h+var_330]
0x180020ec5  mov     rax, [rax+68h]
0x180020ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ece  mov     edi, eax
0x180020ed0  test    eax, eax
0x180020ed2  jns     loc_180020F81
0x180020ed8  mov     eax, cs:dword_1800DF020
0x180020ede  cmp     eax, 3
0x180020ee1  jbe     loc_1800210D6
0x180020ee7  mov     [rsp+3A0h+Pid], r15d
0x180020eec  lea     rdx, [rsp+3A0h+Pid]; Pid
0x180020ef1  xor     ecx, ecx; Binding
0x180020ef3  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180020efa  nop     dword ptr [rax+rax+00h]
0x180020eff  mov     ecx, eax
0x180020f01  test    eax, eax
0x180020f03  jle     short loc_180020F0E
0x180020f05  movzx   ecx, ax
0x180020f08  or      ecx, 80070000h
0x180020f0e  mov     eax, r15d
0x180020f11  test    ecx, ecx
0x180020f13  cmovns  eax, [rsp+3A0h+Pid]
0x180020f18  mov     [rsp+3A0h+var_338], rax
0x180020f1d  mov     [rsp+3A0h+var_328], r12
0x180020f22  mov     [rsp+3A0h+var_348], edi
0x180020f26  lea     rax, aPtrsessionGett_1; "ptrSession->getTerminal"
0x180020f2d  mov     [rsp+3A0h+var_340], rax
0x180020f32  lea     rax, aWarningHresult; "Warning HResult failed"
0x180020f39  mov     qword ptr [rsp+3A0h+Pid], rax
0x180020f3e  lea     rax, [rsp+3A0h+var_338]
0x180020f43  mov     [rsp+3A0h+var_360], rax
0x180020f48  lea     rax, [rsp+3A0h+var_328]
0x180020f4d  mov     [rsp+3A0h+var_368], rax
0x180020f52  lea     rax, [rsp+3A0h+var_348]
0x180020f57  mov     [rsp+3A0h+var_370], rax
0x180020f5c  lea     rax, [rsp+3A0h+var_340]
0x180020f61  mov     [rsp+3A0h+var_378], rax
0x180020f66  lea     rax, [rsp+3A0h+Pid]
0x180020f6b  mov     [rsp+3A0h+var_380], rax
0x180020f70  lea     rdx, byte_1800C6BA5
0x180020f77  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180020f7c  jmp     loc_1800210D6
0x180020f81  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AgentSessionInteractiveLogon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AgentSessionInteractiveLogon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AgentSessionInteractiveLogon> `wil::Feature<__WilFeatureTraits_Feature_AgentSessionInteractiveLogon>::GetImpl(void)'::`2'::impl
0x180020f88  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AgentSessionInteractiveLogon@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AgentSessionInteractiveLogon>::__private_IsEnabled(void)
0x180020f8d  mov     rcx, [rsp+3A0h+var_330]; struct ITerminal *
0x180020f92  test    al, al
0x180020f94  jz      loc_1800210B2
0x180020f9a  xorps   xmm0, xmm0
0x180020f9d  movups  [rbp+2A0h+Buf1], xmm0
0x180020fa1  mov     [rsp+3A0h+var_348], r15d
0x180020fa6  mov     rax, [rcx]
0x180020fa9  lea     r8, [rsp+3A0h+var_348]
0x180020fae  lea     rdx, [rbp+2A0h+Buf1]
0x180020fb2  mov     rax, [rax+80h]
0x180020fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020fbe  mov     edi, eax
0x180020fc0  test    eax, eax
0x180020fc2  jns     loc_18002106C
0x180020fc8  mov     eax, cs:dword_1800DF020
0x180020fce  cmp     eax, 3
0x180020fd1  jbe     loc_1800210D6
0x180020fd7  mov     [rsp+3A0h+Pid], r15d
0x180020fdc  lea     rdx, [rsp+3A0h+Pid]; Pid
0x180020fe1  xor     ecx, ecx; Binding
0x180020fe3  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180020fea  nop     dword ptr [rax+rax+00h]
0x180020fef  mov     ecx, eax
0x180020ff1  test    eax, eax
0x180020ff3  jle     short loc_180020FFE
0x180020ff5  movzx   ecx, ax
0x180020ff8  or      ecx, 80070000h
0x180020ffe  mov     eax, r15d
0x180021001  test    ecx, ecx
0x180021003  cmovns  eax, [rsp+3A0h+Pid]
0x180021008  mov     [rsp+3A0h+var_338], rax
0x18002100d  mov     [rsp+3A0h+var_328], r12
0x180021012  mov     dword ptr [rsp+3A0h+var_340], edi
0x180021016  lea     rax, aPtrterminalGet_0; "ptrTerminal->GetTerminalType"
0x18002101d  mov     qword ptr [rsp+3A0h+Pid], rax
0x180021022  lea     rax, aWarningHresult; "Warning HResult failed"
0x180021029  mov     [rbp+2A0h+var_308], rax
0x18002102d  lea     rax, [rsp+3A0h+var_338]
0x180021032  mov     [rsp+3A0h+var_360], rax
0x180021037  lea     rax, [rsp+3A0h+var_328]
  ... truncated ...
```
