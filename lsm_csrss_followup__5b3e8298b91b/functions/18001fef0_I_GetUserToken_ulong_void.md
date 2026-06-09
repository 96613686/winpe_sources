# I_GetUserToken(ulong,void * *)

- ea: `0x18001fef0`
- end: `0x180020548`
- name: `?I_GetUserToken@@YAJKPEAPEAX@Z`
- size: `1624`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001fec0`

## callees

- `0x180001f04`
- `0x1800074c0`
- `0x18000d0a0`
- `0x180014c00`
- `0x18001db30`
- `0x18001f87c`
- `0x18001fef0`
- `0x180025600`
- `0x18004b460`
- `0x18004b86c`
- `0x18005fcc4`
- `0x180097010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180020131`
- `ntdll!EtwEventWriteTransfer` at `0x180020131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204ba`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180020496`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800204b0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180020496`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800204b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800202c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800202c2`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020002`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020174`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020234`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800202fd`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020002`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020174`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180020234`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800202fd`

## string_xrefs

- `0x18001ff3a`: `I_GetUserToken`
- `0x18002025c`: `RpcGetUserToken was called on a session that we couldn't find.`
- `0x18002032a`: `UserName->DuplicateTokenInPid`
- `0x1800203a2`: `I_GetUserToken (TargetSession: %u, TokenHandle: 0x%p)`
- `0x18002045e`: `%s with Trace ID 0x%x Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall I_GetUserToken(unsigned int a1, void **a2)
{
  struct ISessionManagerInternal *v4; // rsi
  CSessionManager *v5; // rax
  struct ISessionManagerInternal *v6; // rcx
  int v7; // ebx
  RPC_STATUS v8; // eax
  signed int v9; // ecx
  __int64 v10; // rax
  RPC_STATUS v11; // eax
  int v12; // r8d
  int v13; // r9d
  signed int v14; // ecx
  __int64 v15; // rax
  RPC_STATUS v16; // eax
  int v17; // r8d
  int v18; // r9d
  signed int v19; // ecx
  const char *v20; // rax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, void **); // rbx
  DWORD CurrentProcessId; // eax
  RPC_STATUS v24; // eax
  int v25; // r8d
  int v26; // r9d
  signed int v27; // ecx
  const char *v28; // rax
  int v29; // eax
  const struct _EVENT_DESCRIPTOR *v30; // r8
  int v31; // r9d
  unsigned int Pid[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v35[2]; // [rsp+60h] [rbp-A0h] BYREF
  const char *v36; // [rsp+68h] [rbp-98h] BYREF
  const char *v37; // [rsp+70h] [rbp-90h] BYREF
  __int64 v38; // [rsp+78h] [rbp-88h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v41[2]; // [rsp+90h] [rbp-70h] BYREF
  struct ISessionManagerInternal *v42; // [rsp+A0h] [rbp-60h]
  void **v43; // [rsp+B0h] [rbp-50h] BYREF
  int v44; // [rsp+C8h] [rbp-38h]
  __int64 v45; // [rsp+D0h] [rbp-30h]
  int v46; // [rsp+D8h] [rbp-28h]
  const char *v47; // [rsp+E0h] [rbp-20h]
  int v48; // [rsp+F0h] [rbp-10h]
  int *v49; // [rsp+300h] [rbp+200h] BYREF
  int v50; // [rsp+308h] [rbp+208h]
  int v51; // [rsp+30Ch] [rbp+20Ch]
  __int16 *v52; // [rsp+310h] [rbp+210h]
  int v53; // [rsp+318h] [rbp+218h]
  int v54; // [rsp+31Ch] [rbp+21Ch]
  const char *v55; // [rsp+320h] [rbp+220h]
  __int64 v56; // [rsp+328h] [rbp+228h]
  const char *v57; // [rsp+330h] [rbp+230h]
  __int64 v58; // [rsp+338h] [rbp+238h]
  int *v59; // [rsp+340h] [rbp+240h]
  __int64 v60; // [rsp+348h] [rbp+248h]
  const char *v61; // [rsp+350h] [rbp+250h]
  __int64 v62; // [rsp+358h] [rbp+258h]
  unsigned int *v63; // [rsp+360h] [rbp+260h]
  __int64 v64; // [rsp+368h] [rbp+268h]
  DWORD v65[68]; // [rsp+370h] [rbp+270h] BYREF

  v42 = 0;
  v40 = 0;
  v39 = 0;
  v38 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)&v43, 0, "I_GetUserToken");
  *a2 = 0;
  Pid[0] = -2147467263;
  v4 = ISessionManagerInternal::pSMGlobalInstance;
  if ( !ISessionManagerInternal::pSMGlobalInstance )
  {
    v5 = (CSessionManager *)operator new(0x758u, (const struct std::nothrow_t *)&std::nothrow);
    v41[0] = v5;
    if ( v5 )
      v6 = CSessionManager::CSessionManager(v5, (int *)Pid);
    else
      v6 = 0;
    ISessionManagerInternal::pSMGlobalInstance = v6;
    if ( !v6 )
    {
      v4 = 0;
      v7 = -2147024882;
      v42 = 0;
      goto LABEL_9;
    }
    (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v6 + 8LL))(v6);
    v4 = ISessionManagerInternal::pSMGlobalInstance;
  }
  Pid[0] = 0;
  (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v4 + 8LL))(v4);
  v7 = Pid[0];
  v42 = v4;
  if ( (Pid[0] & 0x80000000) != 0 )
  {
LABEL_9:
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      Pid[0] = 0;
      v8 = I_RpcBindingInqLocalClientPID(0, Pid);
      v9 = v8;
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      v10 = 0;
      if ( v9 >= 0 )
        v10 = Pid[0];
      *(_QWORD *)v35 = v10;
      v34 = v7;
      v63 = v35;
      v64 = 8;
      v61 = "I_GetUserToken";
      v62 = 15;
      v59 = &v34;
      v60 = 4;
      v57 = "GetInstanceOfSessionManager";
      v58 = 28;
      v55 = "Warning HResult failed";
      v56 = 23;
      v41[0] = 0x14030B000000LL;
      v41[1] = 0;
      v49 = off_1800DA028;
      v50 = *(unsigned __int16 *)off_1800DA028;
      v51 = 2;
      v52 = &word_1800C180E;
      v53 = 71;
      v54 = 1;
      Pid[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(RegHandle, v41, 0, 0, 7, &v49);
    }
    goto LABEL_42;
  }
  v7 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v4 + 24LL))(v4, &v40);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v40 + 24LL))(v40, a1, &v39);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 96LL))(v39, &v38);
      if ( v7 >= 0 )
      {
        v21 = v38;
        v22 = *(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v38 + 80LL);
        CurrentProcessId = GetCurrentProcessId();
        v7 = v22(v21, CurrentProcessId, a2);
        if ( v7 >= 0 )
        {
          if ( (g_DebugFlagsEx & 1) != 0 )
          {
            v35[0] = 0;
            v29 = StringCchPrintfA(
                    (char *)v65,
                    0x104u,
                    "I_GetUserToken (TargetSession: %u, TokenHandle: 0x%p)",
                    a1,
                    *a2);
            if ( v29 < 0 && (unsigned int)dword_1800DA020 > 3 )
            {
              v34 = v29;
              v37 = "I_GetUserToken";
              Pid[0] = v29;
              v36 = "StringCchPrintfA failed while writing into output buffer";
              v41[0] = "HResult failed but continue";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                dword_1800DA020,
                (unsigned int)byte_1800C16DB,
                (_DWORD)v30,
                v31,
                (__int64)v41,
                (__int64)&v36,
                (__int64)Pid,
                (__int64)&v37,
                (__int64)&v34);
            }
            CRpcUtils::DumpRpcCaller(v65, v35, v30);
          }
        }
        else if ( (unsigned int)dword_1800DA020 > 3 )
        {
          Pid[0] = 0;
          v24 = I_RpcBindingInqLocalClientPID(0, Pid);
          v27 = v24;
          if ( v24 > 0 )
            v27 = (unsigned __int16)v24 | 0x80070000;
          v28 = 0;
          if ( v27 >= 0 )
            v28 = (const char *)Pid[0];
          v37 = v28;
          v36 = "I_GetUserToken";
          v34 = v7;
          *(_QWORD *)v35 = "UserName->DuplicateTokenInPid";
          *(_QWORD *)Pid = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v27,
            (unsigned int)&byte_1800C171F,
            v25,
            v26,
            (__int64)Pid,
            (__int64)v35,
            (__int64)&v34,
            (__int64)&v36,
            (__int64)&v37);
        }
      }
    }
    else if ( (unsigned int)dword_1800DA020 > 5 )
    {
      Pid[0] = 0;
      v16 = I_RpcBindingInqLocalClientPID(0, Pid);
      v19 = v16;
      if ( v16 > 0 )
        v19 = (unsigned __int16)v16 | 0x80070000;
      v20 = 0;
      if ( v19 >= 0 )
        v20 = (const char *)Pid[0];
      v37 = v20;
      v34 = v7;
      v36 = "RpcGetUserToken was called on a session that we couldn't find.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v19,
        (unsigned int)word_1800C1772,
        v17,
        v18,
        (__int64)&v36,
        (__int64)&v34,
        (__int64)&v37);
    }
  }
  else if ( (unsigned int)dword_1800DA020 > 3 )
  {
    Pid[0] = 0;
    v11 = I_RpcBindingInqLocalClientPID(0, Pid);
    v14 = v11;
    if ( v11 > 0 )
      v14 = (unsigned __int16)v11 | 0x80070000;
    v15 = 0;
    if ( v14 >= 0 )
      v15 = Pid[0];
    *(_QWORD *)v35 = v15;
    *(_QWORD *)Pid = "I_GetUserToken";
    v34 = v7;
    v36 = "GetSessionList";
    v37 = "Warning HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      v14,
      (unsigned int)qword_1800C17B0,
      v12,
      v13,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v34,
      (__int64)Pid,
      (__int64)v35);
  }
LABEL_42:
  v43 = &CRpcCallTrace::`vftable';
  if ( v48 && (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "%s with Trace ID 0x%x Completed", v47, v44);
  v43 = &CTraceBase::`vftable';
  if ( !v46 && CTraceBase::g_bEnabled && CTraceBase::g_TLSIndex != -1 )
  {
    if ( TlsSetValue(CTraceBase::g_TLSIndex, 0) )
    {
      if ( TlsSetValue(CTraceBase::g_CreatorFunctionTLSIndex, 0) )
        goto LABEL_52;
    }
    else
    {
      GetLastError();
    }
    GetLastError();
  }
LABEL_52:
  v45 = 0;
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v4 )
    (*(void (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001fef0  mov     [rsp-8+arg_10], rbx
0x18001fef5  push    rbp
0x18001fef6  push    rsi
0x18001fef7  push    rdi
0x18001fef8  push    r12
0x18001fefa  push    r13
0x18001fefc  push    r14
0x18001fefe  push    r15
0x18001ff00  lea     rbp, [rsp-390h]
0x18001ff08  sub     rsp, 490h
0x18001ff0f  mov     rax, cs:__security_cookie
0x18001ff16  xor     rax, rsp
0x18001ff19  mov     [rbp+3C0h+var_40], rax
0x18001ff20  mov     r14, rdx
0x18001ff23  mov     r15d, ecx
0x18001ff26  xor     r12d, r12d
0x18001ff29  mov     [rbp+3C0h+var_420], r12
0x18001ff2d  mov     [rbp+3C0h+var_438], r12
0x18001ff31  mov     [rbp+3C0h+var_440], r12
0x18001ff35  mov     [rsp+4C0h+var_448], r12
0x18001ff3a  lea     r13, aIGetusertoken; "I_GetUserToken"
0x18001ff41  mov     r8, r13; char *
0x18001ff44  xor     edx, edx; int
0x18001ff46  lea     rcx, [rbp+3C0h+var_410]; this
0x18001ff4a  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18001ff4f  nop
0x18001ff50  mov     [r14], r12
0x18001ff53  mov     [rsp+4C0h+Pid], 80004001h
0x18001ff5b  mov     rsi, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x18001ff62  test    rsi, rsi
0x18001ff65  jnz     short loc_18001FFC3
0x18001ff67  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ff6e  mov     ecx, 758h; unsigned __int64
0x18001ff73  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001ff78  mov     [rbp+3C0h+var_430], rax
0x18001ff7c  test    rax, rax
0x18001ff7f  jz      short loc_18001FF93
0x18001ff81  lea     rdx, [rsp+4C0h+Pid]; int *
0x18001ff86  mov     rcx, rax; this
0x18001ff89  call    ??0CSessionManager@@QEAA@PEAJ@Z; CSessionManager::CSessionManager(long *)
0x18001ff8e  mov     rcx, rax
0x18001ff91  jmp     short loc_18001FF96
0x18001ff93  mov     rcx, r12
0x18001ff96  mov     cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA, rcx; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x18001ff9d  test    rcx, rcx
0x18001ffa0  jnz     short loc_18001FFB0
0x18001ffa2  mov     rsi, r12
0x18001ffa5  mov     ebx, 8007000Eh
0x18001ffaa  mov     [rbp+3C0h+var_420], r12
0x18001ffae  jmp     short loc_18001FFE7
0x18001ffb0  mov     rax, [rcx]
0x18001ffb3  mov     rax, [rax+8]
0x18001ffb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffbc  mov     rsi, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x18001ffc3  mov     [rsp+4C0h+Pid], r12d
0x18001ffc8  mov     rax, [rsi]
0x18001ffcb  mov     rcx, rsi
0x18001ffce  mov     rax, [rax+8]
0x18001ffd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffd7  mov     ebx, [rsp+4C0h+Pid]
0x18001ffdb  mov     [rbp+3C0h+var_420], rsi
0x18001ffdf  test    ebx, ebx
0x18001ffe1  jns     loc_18002013C
0x18001ffe7  mov     eax, cs:dword_1800DA020
0x18001ffed  cmp     eax, 3
0x18001fff0  jbe     loc_18002043C
0x18001fff6  mov     [rsp+4C0h+Pid], r12d
0x18001fffb  lea     rdx, [rsp+4C0h+Pid]; Pid
0x180020000  xor     ecx, ecx; Binding
0x180020002  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180020008  mov     ecx, eax
0x18002000a  test    eax, eax
0x18002000c  jle     short loc_180020017
0x18002000e  movzx   ecx, ax
0x180020011  or      ecx, 80070000h
0x180020017  mov     eax, r12d
0x18002001a  test    ecx, ecx
0x18002001c  cmovns  eax, [rsp+4C0h+Pid]
0x180020021  mov     qword ptr [rsp+4C0h+var_460], rax
0x180020026  mov     [rsp+4C0h+var_468], ebx
0x18002002a  lea     rax, [rsp+4C0h+var_460]
0x18002002f  mov     [rbp+3C0h+var_160], rax
0x180020036  mov     [rbp+3C0h+var_158], 8
0x180020041  mov     [rbp+3C0h+var_170], r13
0x180020048  mov     [rbp+3C0h+var_168], 0Fh
0x180020053  lea     rax, [rsp+4C0h+var_468]
0x180020058  mov     [rbp+3C0h+var_180], rax
0x18002005f  mov     [rbp+3C0h+var_178], 4
0x18002006a  lea     rax, aGetinstanceofs_0; "GetInstanceOfSessionManager"
0x180020071  mov     [rbp+3C0h+var_190], rax
0x180020078  mov     [rbp+3C0h+var_188], 1Ch
0x180020083  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002008a  mov     [rbp+3C0h+var_1A0], rax
0x180020091  mov     [rbp+3C0h+var_198], 17h
0x18002009c  mov     dword ptr [rbp+3C0h+var_430], 0B000000h
0x1800200a3  movzx   eax, cs:word_1800C1804
0x1800200aa  mov     dword ptr [rbp+3C0h+var_430+4], eax
0x1800200ad  mov     [rbp+3C0h+var_428], r12
0x1800200b1  mov     rax, cs:off_1800DA028
0x1800200b8  mov     [rbp+3C0h+var_1C0], rax
0x1800200bf  movzx   eax, word ptr [rax]
0x1800200c2  mov     [rbp+3C0h+var_1B8], eax
0x1800200c8  mov     [rbp+3C0h+var_1B4], 2
0x1800200d2  lea     rax, word_1800C180E
0x1800200d9  mov     [rbp+3C0h+var_1B0], rax
0x1800200e0  mov     [rbp+3C0h+var_1A8], 47h ; 'G'
0x1800200ea  mov     [rbp+3C0h+var_1A4], 1
0x1800200f4  lea     rax, _TraceLoggingMetadataEnd
0x1800200fb  lea     rcx, _TraceLoggingMetadata
0x180020102  sub     eax, ecx
0x180020104  mov     [rsp+4C0h+Pid], eax
0x180020108  mov     eax, [rsp+4C0h+Pid]
0x18002010c  lea     rax, [rbp+3C0h+var_1C0]
0x180020113  mov     [rsp+4C0h+var_498], rax
0x180020118  mov     dword ptr [rsp+4C0h+var_4A0], 7
0x180020120  xor     r9d, r9d
0x180020123  xor     r8d, r8d
0x180020126  lea     rdx, [rbp+3C0h+var_430]
0x18002012a  mov     rcx, cs:RegHandle
0x180020131  call    cs:__imp_EtwEventWriteTransfer
0x180020137  jmp     loc_18002043C
0x18002013c  mov     rax, [rsi]
0x18002013f  lea     rdx, [rbp+3C0h+var_438]
0x180020143  mov     rcx, rsi
0x180020146  mov     rax, [rax+18h]
0x18002014a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002014f  mov     ebx, eax
0x180020151  test    eax, eax
0x180020153  jns     loc_1800201FC
0x180020159  mov     ecx, cs:dword_1800DA020
0x18002015f  cmp     ecx, 3
0x180020162  jbe     loc_18002043C
0x180020168  mov     [rsp+4C0h+Pid], r12d
0x18002016d  lea     rdx, [rsp+4C0h+Pid]; Pid
0x180020172  xor     ecx, ecx; Binding
0x180020174  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18002017a  mov     ecx, eax
0x18002017c  test    eax, eax
0x18002017e  jle     short loc_180020189
0x180020180  movzx   ecx, ax
0x180020183  or      ecx, 80070000h
0x180020189  mov     eax, r12d
0x18002018c  test    ecx, ecx
0x18002018e  cmovns  eax, [rsp+4C0h+Pid]
0x180020193  mov     qword ptr [rsp+4C0h+var_460], rax
0x180020198  mov     qword ptr [rsp+4C0h+Pid], r13
0x18002019d  mov     [rsp+4C0h+var_468], ebx
0x1800201a1  lea     rax, aGetsessionlist_2; "GetSessionList"
0x1800201a8  mov     [rsp+4C0h+var_458], rax
0x1800201ad  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800201b4  mov     [rsp+4C0h+var_450], rax
0x1800201b9  lea     rax, [rsp+4C0h+var_460]
0x1800201be  mov     [rsp+4C0h+var_480], rax
0x1800201c3  lea     rax, [rsp+4C0h+Pid]
0x1800201c8  mov     [rsp+4C0h+var_488], rax
0x1800201cd  lea     rax, [rsp+4C0h+var_468]
0x1800201d2  mov     [rsp+4C0h+var_490], rax
0x1800201d7  lea     rax, [rsp+4C0h+var_458]
0x1800201dc  mov     [rsp+4C0h+var_498], rax
0x1800201e1  lea     rax, [rsp+4C0h+var_450]
0x1800201e6  mov     [rsp+4C0h+var_4A0], rax
0x1800201eb  lea     rdx, qword_1800C17B0
0x1800201f2  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800201f7  jmp     loc_18002043C
0x1800201fc  mov     rcx, [rbp+3C0h+var_438]
0x180020200  mov     rax, [rcx]
0x180020203  lea     r8, [rbp+3C0h+var_440]
0x180020207  mov     edx, r15d
0x18002020a  mov     rax, [rax+18h]
0x18002020e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020213  mov     ebx, eax
0x180020215  test    eax, eax
0x180020217  jns     short loc_180020297
0x180020219  mov     eax, cs:dword_1800DA020
0x18002021f  cmp     eax, 5
0x180020222  jbe     loc_18002043C
0x180020228  mov     [rsp+4C0h+Pid], r12d
0x18002022d  lea     rdx, [rsp+4C0h+Pid]; Pid
0x180020232  xor     ecx, ecx; Binding
0x180020234  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18002023a  mov     ecx, eax
0x18002023c  test    eax, eax
0x18002023e  jle     short loc_180020249
0x180020240  movzx   ecx, ax
0x180020243  or      ecx, 80070000h
0x180020249  mov     eax, r12d
0x18002024c  test    ecx, ecx
0x18002024e  cmovns  eax, [rsp+4C0h+Pid]
0x180020253  mov     [rsp+4C0h+var_450], rax
0x180020258  mov     [rsp+4C0h+var_468], ebx
0x18002025c  lea     rax, aRpcgetusertoke; "RpcGetUserToken was called on a session"...
0x180020263  mov     [rsp+4C0h+var_458], rax
0x180020268  lea     rax, [rsp+4C0h+var_450]
0x18002026d  mov     [rsp+4C0h+var_490], rax
0x180020272  lea     rax, [rsp+4C0h+var_468]
0x180020277  mov     [rsp+4C0h+var_498], rax
0x18002027c  lea     rax, [rsp+4C0h+var_458]
0x180020281  mov     [rsp+4C0h+var_4A0], rax
0x180020286  lea     rdx, word_1800C1772
0x18002028d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180020292  jmp     loc_18002043C
0x180020297  mov     rcx, [rbp+3C0h+var_440]
0x18002029b  mov     rax, [rcx]
0x18002029e  lea     rdx, [rsp+4C0h+var_448]
0x1800202a3  mov     rax, [rax+60h]
0x1800202a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202ac  mov     ebx, eax
0x1800202ae  test    eax, eax
0x1800202b0  js      loc_18002043C
0x1800202b6  mov     rdi, [rsp+4C0h+var_448]
0x1800202bb  mov     rax, [rdi]
0x1800202be  mov     rbx, [rax+50h]
0x1800202c2  call    cs:__imp_GetCurrentProcessId
0x1800202c8  mov     r8, r14
0x1800202cb  mov     edx, eax
0x1800202cd  mov     rcx, rdi
0x1800202d0  mov     rax, rbx
0x1800202d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202d8  mov     ebx, eax
0x1800202da  test    eax, eax
0x1800202dc  jns     loc_180020385
0x1800202e2  mov     eax, cs:dword_1800DA020
0x1800202e8  cmp     eax, 3
0x1800202eb  jbe     loc_18002043C
0x1800202f1  mov     [rsp+4C0h+Pid], r12d
0x1800202f6  lea     rdx, [rsp+4C0h+Pid]; Pid
0x1800202fb  xor     ecx, ecx; Binding
0x1800202fd  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180020303  mov     ecx, eax
0x180020305  test    eax, eax
0x180020307  jle     short loc_180020312
0x180020309  movzx   ecx, ax
0x18002030c  or      ecx, 80070000h
0x180020312  mov     eax, r12d
0x180020315  test    ecx, ecx
0x180020317  cmovns  eax, [rsp+4C0h+Pid]
0x18002031c  mov     [rsp+4C0h+var_450], rax
0x180020321  mov     [rsp+4C0h+var_458], r13
0x180020326  mov     [rsp+4C0h+var_468], ebx
0x18002032a  lea     rax, aUsernameDuplic; "UserName->DuplicateTokenInPid"
0x180020331  mov     qword ptr [rsp+4C0h+var_460], rax
0x180020336  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002033d  mov     qword ptr [rsp+4C0h+Pid], rax
0x180020342  lea     rax, [rsp+4C0h+var_450]
0x180020347  mov     [rsp+4C0h+var_480], rax
0x18002034c  lea     rax, [rsp+4C0h+var_458]
0x180020351  mov     [rsp+4C0h+var_488], rax
0x180020356  lea     rax, [rsp+4C0h+var_468]
0x18002035b  mov     [rsp+4C0h+var_490], rax
0x180020360  lea     rax, [rsp+4C0h+var_460]
0x180020365  mov     [rsp+4C0h+var_498], rax
0x18002036a  lea     rax, [rsp+4C0h+Pid]
0x18002036f  mov     [rsp+4C0h+var_4A0], rax
0x180020374  lea     rdx, byte_1800C171F
0x18002037b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180020380  jmp     loc_18002043C
0x180020385  test    byte ptr cs:?g_DebugFlagsEx@@3KA, 1; ulong g_DebugFlagsEx
0x18002038c  jz      loc_18002043C
0x180020392  mov     [rsp+4C0h+var_460], r12d
0x180020397  mov     rax, [r14]
0x18002039a  mov     [rsp+4C0h+var_4A0], rax
0x18002039f  mov     r9d, r15d
0x1800203a2  lea     r8, aIGetusertokenT; "I_GetUserToken (TargetSession: %u, Toke"...
0x1800203a9  mov     edx, 104h; unsigned __int64
0x1800203ae  lea     rcx, [rbp+3C0h+var_150]; char *
0x1800203b5  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800203ba  test    eax, eax
0x1800203bc  jns     short loc_18002042A
0x1800203be  mov     ecx, cs:dword_1800DA020
0x1800203c4  cmp     ecx, 3
0x1800203c7  jbe     short loc_18002042A
0x1800203c9  mov     [rsp+4C0h+var_468], eax
0x1800203cd  mov     [rsp+4C0h+var_450], r13
0x1800203d2  mov     [rsp+4C0h+Pid], eax
0x1800203d6  lea     rax, aStringcchprint; "StringCchPrintfA failed while writing i"...
0x1800203dd  mov     [rsp+4C0h+var_458], rax
0x1800203e2  lea     rax, aHresultFailedB; "HResult failed but continue"
0x1800203e9  mov     [rbp+3C0h+var_430], rax
0x1800203ed  lea     rax, [rsp+4C0h+var_468]
0x1800203f2  mov     [rsp+4C0h+var_480], rax
0x1800203f7  lea     rax, [rsp+4C0h+var_450]
0x1800203fc  mov     [rsp+4C0h+var_488], rax
0x180020401  lea     rax, [rsp+4C0h+Pid]
0x180020406  mov     [rsp+4C0h+var_490], rax
0x18002040b  lea     rax, [rsp+4C0h+var_458]
0x180020410  mov     [rsp+4C0h+var_498], rax
0x180020415  lea     rax, [rbp+3C0h+var_430]
0x180020419  mov     [rsp+4C0h+var_4A0], rax
0x18002041e  lea     rdx, byte_1800C16DB
0x180020425  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002042a  lea     rdx, [rsp+4C0h+var_460]; volatile unsigned int *
0x18002042f  lea     rcx, [rbp+3C0h+var_150]; char *
0x180020436  call    ?DumpRpcCaller@CRpcUtils@@SAXPEBDAECKAEBU_EVENT_DESCRIPTOR@@@Z; CRpcUtils::DumpRpcCaller(char const *,ulong volatile &,_EVENT_DESCRIPTOR const &)
0x18002043b  nop
0x18002043c  lea     rax, ??_7CRpcCallTrace@@6B@; const CRpcCallTrace::`vftable'
0x180020443  mov     [rbp+3C0h+var_410], rax
0x180020447  cmp     [rbp+3C0h+var_3D0], 0
0x18002044b  jz      short loc_18002046F
0x18002044d  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x180020454  jz      short loc_18002046F
  ... truncated ...
```
