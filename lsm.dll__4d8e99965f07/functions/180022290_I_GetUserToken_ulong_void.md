# I_GetUserToken(ulong,void * *)

- ea: `0x180022290`
- end: `0x180022893`
- name: `?I_GetUserToken@@YAJKPEAPEAX@Z`
- size: `1539`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180022260`

## callees

- `0x180001f14`
- `0x18000e8b0`
- `0x18000f260`
- `0x18001db60`
- `0x18001f250`
- `0x180021c80`
- `0x180022290`
- `0x180027610`
- `0x18004e850`
- `0x18004ec5c`
- `0x1800637cc`
- `0x18009c010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800224d7`
- `ntdll!EtwEventWriteTransfer` at `0x1800224d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002267e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002267e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800223a2`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180022520`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800225ea`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800226bf`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800223a2`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180022520`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800225ea`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800226bf`

## string_xrefs

- `0x1800222da`: `I_GetUserToken`
- `0x180022618`: `RpcGetUserToken was called on a session that we couldn't find.`
- `0x1800226f2`: `UserName->DuplicateTokenInPid`
- `0x18002276a`: `I_GetUserToken (TargetSession: %u, TokenHandle: 0x%p)`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
  _BYTE v43[592]; // [rsp+B0h] [rbp-50h] BYREF
  int *v44; // [rsp+300h] [rbp+200h] BYREF
  int v45; // [rsp+308h] [rbp+208h]
  int v46; // [rsp+30Ch] [rbp+20Ch]
  __int16 *v47; // [rsp+310h] [rbp+210h]
  int v48; // [rsp+318h] [rbp+218h]
  int v49; // [rsp+31Ch] [rbp+21Ch]
  const char *v50; // [rsp+320h] [rbp+220h]
  __int64 v51; // [rsp+328h] [rbp+228h]
  const char *v52; // [rsp+330h] [rbp+230h]
  __int64 v53; // [rsp+338h] [rbp+238h]
  int *v54; // [rsp+340h] [rbp+240h]
  __int64 v55; // [rsp+348h] [rbp+248h]
  const char *v56; // [rsp+350h] [rbp+250h]
  __int64 v57; // [rsp+358h] [rbp+258h]
  unsigned int *v58; // [rsp+360h] [rbp+260h]
  __int64 v59; // [rsp+368h] [rbp+268h]
  DWORD v60[68]; // [rsp+370h] [rbp+270h] BYREF

  v42 = 0;
  v40 = 0;
  v39 = 0;
  v38 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v43, 0, "I_GetUserToken");
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
    if ( (unsigned int)dword_1800DF020 > 3 )
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
      v58 = v35;
      v59 = 8;
      v56 = "I_GetUserToken";
      v57 = 15;
      v54 = &v34;
      v55 = 4;
      v52 = "GetInstanceOfSessionManager";
      v53 = 28;
      v50 = "Warning HResult failed";
      v51 = 23;
      v41[0] = 0x14030B000000LL;
      v41[1] = 0;
      v44 = off_1800DF028;
      v45 = *(unsigned __int16 *)off_1800DF028;
      v46 = 2;
      v47 = &word_1800C6996;
      v48 = 71;
      v49 = 1;
      Pid[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(RegHandle, v41, 0, 0, 7, &v44);
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
                    (char *)v60,
                    0x104u,
                    "I_GetUserToken (TargetSession: %u, TokenHandle: 0x%p)",
                    a1,
                    *a2);
            if ( v29 < 0 && (unsigned int)dword_1800DF020 > 3 )
            {
              v34 = v29;
              v37 = "I_GetUserToken";
              Pid[0] = v29;
              v36 = "StringCchPrintfA failed while writing into output buffer";
              v41[0] = "HResult failed but continue";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                dword_1800DF020,
                (unsigned int)byte_1800C6863,
                (_DWORD)v30,
                v31,
                (__int64)v41,
                (__int64)&v36,
                (__int64)Pid,
                (__int64)&v37,
                (__int64)&v34);
            }
            CRpcUtils::DumpRpcCaller(v60, v35, v30);
          }
        }
        else if ( (unsigned int)dword_1800DF020 > 3 )
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
            (unsigned int)&byte_1800C68A7,
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
    else if ( (unsigned int)dword_1800DF020 > 5 )
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
        (unsigned int)word_1800C68FA,
        v17,
        v18,
        (__int64)&v36,
        (__int64)&v34,
        (__int64)&v37);
    }
  }
  else if ( (unsigned int)dword_1800DF020 > 3 )
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
      (unsigned int)qword_1800C6938,
      v12,
      v13,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v34,
      (__int64)Pid,
      (__int64)v35);
  }
LABEL_42:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v43);
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
0x180022290  mov     [rsp-8+arg_10], rbx
0x180022295  push    rbp
0x180022296  push    rsi
0x180022297  push    rdi
0x180022298  push    r12
0x18002229a  push    r13
0x18002229c  push    r14
0x18002229e  push    r15
0x1800222a0  lea     rbp, [rsp-390h]
0x1800222a8  sub     rsp, 490h
0x1800222af  mov     rax, cs:__security_cookie
0x1800222b6  xor     rax, rsp
0x1800222b9  mov     [rbp+3C0h+var_40], rax
0x1800222c0  mov     r14, rdx
0x1800222c3  mov     r15d, ecx
0x1800222c6  xor     r12d, r12d
0x1800222c9  mov     [rbp+3C0h+var_420], r12
0x1800222cd  mov     [rbp+3C0h+var_438], r12
0x1800222d1  mov     [rbp+3C0h+var_440], r12
0x1800222d5  mov     [rsp+4C0h+var_448], r12
0x1800222da  lea     r13, aIGetusertoken; "I_GetUserToken"
0x1800222e1  mov     r8, r13; char *
0x1800222e4  xor     edx, edx; int
0x1800222e6  lea     rcx, [rbp+3C0h+var_410]; this
0x1800222ea  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x1800222ef  nop
0x1800222f0  mov     [r14], r12
0x1800222f3  mov     [rsp+4C0h+Pid], 80004001h
0x1800222fb  mov     rsi, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x180022302  test    rsi, rsi
0x180022305  jnz     short loc_180022363
0x180022307  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002230e  mov     ecx, 758h; unsigned __int64
0x180022313  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022318  mov     [rbp+3C0h+var_430], rax
0x18002231c  test    rax, rax
0x18002231f  jz      short loc_180022333
0x180022321  lea     rdx, [rsp+4C0h+Pid]; int *
0x180022326  mov     rcx, rax; this
0x180022329  call    ??0CSessionManager@@QEAA@PEAJ@Z; CSessionManager::CSessionManager(long *)
0x18002232e  mov     rcx, rax
0x180022331  jmp     short loc_180022336
0x180022333  mov     rcx, r12
0x180022336  mov     cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA, rcx; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x18002233d  test    rcx, rcx
0x180022340  jnz     short loc_180022350
0x180022342  mov     rsi, r12
0x180022345  mov     ebx, 8007000Eh
0x18002234a  mov     [rbp+3C0h+var_420], r12
0x18002234e  jmp     short loc_180022387
0x180022350  mov     rax, [rcx]
0x180022353  mov     rax, [rax+8]
0x180022357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002235c  mov     rsi, cs:?pSMGlobalInstance@ISessionManagerInternal@@0PEAV1@EA; ISessionManagerInternal * ISessionManagerInternal::pSMGlobalInstance
0x180022363  mov     [rsp+4C0h+Pid], r12d
0x180022368  mov     rax, [rsi]
0x18002236b  mov     rcx, rsi
0x18002236e  mov     rax, [rax+8]
0x180022372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022377  mov     ebx, [rsp+4C0h+Pid]
0x18002237b  mov     [rbp+3C0h+var_420], rsi
0x18002237f  test    ebx, ebx
0x180022381  jns     loc_1800224E8
0x180022387  mov     eax, cs:dword_1800DF020
0x18002238d  cmp     eax, 3
0x180022390  jbe     loc_180022804
0x180022396  mov     [rsp+4C0h+Pid], r12d
0x18002239b  lea     rdx, [rsp+4C0h+Pid]; Pid
0x1800223a0  xor     ecx, ecx; Binding
0x1800223a2  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800223a9  nop     dword ptr [rax+rax+00h]
0x1800223ae  mov     ecx, eax
0x1800223b0  test    eax, eax
0x1800223b2  jle     short loc_1800223BD
0x1800223b4  movzx   ecx, ax
0x1800223b7  or      ecx, 80070000h
0x1800223bd  mov     eax, r12d
0x1800223c0  test    ecx, ecx
0x1800223c2  cmovns  eax, [rsp+4C0h+Pid]
0x1800223c7  mov     qword ptr [rsp+4C0h+var_460], rax
0x1800223cc  mov     [rsp+4C0h+var_468], ebx
0x1800223d0  lea     rax, [rsp+4C0h+var_460]
0x1800223d5  mov     [rbp+3C0h+var_160], rax
0x1800223dc  mov     [rbp+3C0h+var_158], 8
0x1800223e7  mov     [rbp+3C0h+var_170], r13
0x1800223ee  mov     [rbp+3C0h+var_168], 0Fh
0x1800223f9  lea     rax, [rsp+4C0h+var_468]
0x1800223fe  mov     [rbp+3C0h+var_180], rax
0x180022405  mov     [rbp+3C0h+var_178], 4
0x180022410  lea     rax, aGetinstanceofs_0; "GetInstanceOfSessionManager"
0x180022417  mov     [rbp+3C0h+var_190], rax
0x18002241e  mov     [rbp+3C0h+var_188], 1Ch
0x180022429  lea     rax, aWarningHresult; "Warning HResult failed"
0x180022430  mov     [rbp+3C0h+var_1A0], rax
0x180022437  mov     [rbp+3C0h+var_198], 17h
0x180022442  mov     dword ptr [rbp+3C0h+var_430], 0B000000h
0x180022449  movzx   eax, cs:word_1800C698C
0x180022450  mov     dword ptr [rbp+3C0h+var_430+4], eax
0x180022453  mov     [rbp+3C0h+var_428], r12
0x180022457  mov     rax, cs:off_1800DF028
0x18002245e  mov     [rbp+3C0h+var_1C0], rax
0x180022465  movzx   eax, word ptr [rax]
0x180022468  mov     [rbp+3C0h+var_1B8], eax
0x18002246e  mov     [rbp+3C0h+var_1B4], 2
0x180022478  lea     rax, word_1800C6996
0x18002247f  mov     [rbp+3C0h+var_1B0], rax
0x180022486  mov     [rbp+3C0h+var_1A8], 47h ; 'G'
0x180022490  mov     [rbp+3C0h+var_1A4], 1
0x18002249a  lea     rax, _TraceLoggingMetadataEnd
0x1800224a1  lea     rcx, _TraceLoggingMetadata
0x1800224a8  sub     eax, ecx
0x1800224aa  mov     [rsp+4C0h+Pid], eax
0x1800224ae  mov     eax, [rsp+4C0h+Pid]
0x1800224b2  lea     rax, [rbp+3C0h+var_1C0]
0x1800224b9  mov     [rsp+4C0h+var_498], rax
0x1800224be  mov     dword ptr [rsp+4C0h+var_4A0], 7
0x1800224c6  xor     r9d, r9d
0x1800224c9  xor     r8d, r8d
0x1800224cc  lea     rdx, [rbp+3C0h+var_430]
0x1800224d0  mov     rcx, cs:RegHandle
0x1800224d7  call    cs:__imp_EtwEventWriteTransfer
0x1800224de  nop     dword ptr [rax+rax+00h]
0x1800224e3  jmp     loc_180022804
0x1800224e8  mov     rax, [rsi]
0x1800224eb  lea     rdx, [rbp+3C0h+var_438]
0x1800224ef  mov     rcx, rsi
0x1800224f2  mov     rax, [rax+18h]
0x1800224f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224fb  mov     ebx, eax
0x1800224fd  test    eax, eax
0x1800224ff  jns     loc_1800225AE
0x180022505  mov     ecx, cs:dword_1800DF020
0x18002250b  cmp     ecx, 3
0x18002250e  jbe     loc_180022804
0x180022514  mov     [rsp+4C0h+Pid], r12d
0x180022519  lea     rdx, [rsp+4C0h+Pid]; Pid
0x18002251e  xor     ecx, ecx; Binding
0x180022520  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180022527  nop     dword ptr [rax+rax+00h]
0x18002252c  mov     ecx, eax
0x18002252e  test    eax, eax
0x180022530  jle     short loc_18002253B
0x180022532  movzx   ecx, ax
0x180022535  or      ecx, 80070000h
0x18002253b  mov     eax, r12d
0x18002253e  test    ecx, ecx
0x180022540  cmovns  eax, [rsp+4C0h+Pid]
0x180022545  mov     qword ptr [rsp+4C0h+var_460], rax
0x18002254a  mov     qword ptr [rsp+4C0h+Pid], r13
0x18002254f  mov     [rsp+4C0h+var_468], ebx
0x180022553  lea     rax, aGetsessionlist_2; "GetSessionList"
0x18002255a  mov     [rsp+4C0h+var_458], rax
0x18002255f  lea     rax, aWarningHresult; "Warning HResult failed"
0x180022566  mov     [rsp+4C0h+var_450], rax
0x18002256b  lea     rax, [rsp+4C0h+var_460]
0x180022570  mov     [rsp+4C0h+var_480], rax
0x180022575  lea     rax, [rsp+4C0h+Pid]
0x18002257a  mov     [rsp+4C0h+var_488], rax
0x18002257f  lea     rax, [rsp+4C0h+var_468]
0x180022584  mov     [rsp+4C0h+var_490], rax
0x180022589  lea     rax, [rsp+4C0h+var_458]
0x18002258e  mov     [rsp+4C0h+var_498], rax
0x180022593  lea     rax, [rsp+4C0h+var_450]
0x180022598  mov     [rsp+4C0h+var_4A0], rax
0x18002259d  lea     rdx, qword_1800C6938
0x1800225a4  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800225a9  jmp     loc_180022804
0x1800225ae  mov     rcx, [rbp+3C0h+var_438]
0x1800225b2  mov     rax, [rcx]
0x1800225b5  lea     r8, [rbp+3C0h+var_440]
0x1800225b9  mov     edx, r15d
0x1800225bc  mov     rax, [rax+18h]
0x1800225c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225c5  mov     ebx, eax
0x1800225c7  test    eax, eax
0x1800225c9  jns     loc_180022653
0x1800225cf  mov     eax, cs:dword_1800DF020
0x1800225d5  cmp     eax, 5
0x1800225d8  jbe     loc_180022804
0x1800225de  mov     [rsp+4C0h+Pid], r12d
0x1800225e3  lea     rdx, [rsp+4C0h+Pid]; Pid
0x1800225e8  xor     ecx, ecx; Binding
0x1800225ea  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800225f1  nop     dword ptr [rax+rax+00h]
0x1800225f6  mov     ecx, eax
0x1800225f8  test    eax, eax
0x1800225fa  jle     short loc_180022605
0x1800225fc  movzx   ecx, ax
0x1800225ff  or      ecx, 80070000h
0x180022605  mov     eax, r12d
0x180022608  test    ecx, ecx
0x18002260a  cmovns  eax, [rsp+4C0h+Pid]
0x18002260f  mov     [rsp+4C0h+var_450], rax
0x180022614  mov     [rsp+4C0h+var_468], ebx
0x180022618  lea     rax, aRpcgetusertoke; "RpcGetUserToken was called on a session"...
0x18002261f  mov     [rsp+4C0h+var_458], rax
0x180022624  lea     rax, [rsp+4C0h+var_450]
0x180022629  mov     [rsp+4C0h+var_490], rax
0x18002262e  lea     rax, [rsp+4C0h+var_468]
0x180022633  mov     [rsp+4C0h+var_498], rax
0x180022638  lea     rax, [rsp+4C0h+var_458]
0x18002263d  mov     [rsp+4C0h+var_4A0], rax
0x180022642  lea     rdx, word_1800C68FA
0x180022649  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18002264e  jmp     loc_180022804
0x180022653  mov     rcx, [rbp+3C0h+var_440]
0x180022657  mov     rax, [rcx]
0x18002265a  lea     rdx, [rsp+4C0h+var_448]
0x18002265f  mov     rax, [rax+60h]
0x180022663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022668  mov     ebx, eax
0x18002266a  test    eax, eax
0x18002266c  js      loc_180022804
0x180022672  mov     rdi, [rsp+4C0h+var_448]
0x180022677  mov     rax, [rdi]
0x18002267a  mov     rbx, [rax+50h]
0x18002267e  call    cs:__imp_GetCurrentProcessId
0x180022685  nop     dword ptr [rax+rax+00h]
0x18002268a  mov     r8, r14
0x18002268d  mov     edx, eax
0x18002268f  mov     rcx, rdi
0x180022692  mov     rax, rbx
0x180022695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002269a  mov     ebx, eax
0x18002269c  test    eax, eax
0x18002269e  jns     loc_18002274D
0x1800226a4  mov     eax, cs:dword_1800DF020
0x1800226aa  cmp     eax, 3
0x1800226ad  jbe     loc_180022804
0x1800226b3  mov     [rsp+4C0h+Pid], r12d
0x1800226b8  lea     rdx, [rsp+4C0h+Pid]; Pid
0x1800226bd  xor     ecx, ecx; Binding
0x1800226bf  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800226c6  nop     dword ptr [rax+rax+00h]
0x1800226cb  mov     ecx, eax
0x1800226cd  test    eax, eax
0x1800226cf  jle     short loc_1800226DA
0x1800226d1  movzx   ecx, ax
0x1800226d4  or      ecx, 80070000h
0x1800226da  mov     eax, r12d
0x1800226dd  test    ecx, ecx
0x1800226df  cmovns  eax, [rsp+4C0h+Pid]
0x1800226e4  mov     [rsp+4C0h+var_450], rax
0x1800226e9  mov     [rsp+4C0h+var_458], r13
0x1800226ee  mov     [rsp+4C0h+var_468], ebx
0x1800226f2  lea     rax, aUsernameDuplic; "UserName->DuplicateTokenInPid"
0x1800226f9  mov     qword ptr [rsp+4C0h+var_460], rax
0x1800226fe  lea     rax, aWarningHresult; "Warning HResult failed"
0x180022705  mov     qword ptr [rsp+4C0h+Pid], rax
0x18002270a  lea     rax, [rsp+4C0h+var_450]
0x18002270f  mov     [rsp+4C0h+var_480], rax
0x180022714  lea     rax, [rsp+4C0h+var_458]
0x180022719  mov     [rsp+4C0h+var_488], rax
0x18002271e  lea     rax, [rsp+4C0h+var_468]
0x180022723  mov     [rsp+4C0h+var_490], rax
0x180022728  lea     rax, [rsp+4C0h+var_460]
0x18002272d  mov     [rsp+4C0h+var_498], rax
0x180022732  lea     rax, [rsp+4C0h+Pid]
0x180022737  mov     [rsp+4C0h+var_4A0], rax
0x18002273c  lea     rdx, byte_1800C68A7
0x180022743  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180022748  jmp     loc_180022804
0x18002274d  test    byte ptr cs:?g_DebugFlagsEx@@3KA, 1; ulong g_DebugFlagsEx
0x180022754  jz      loc_180022804
0x18002275a  mov     [rsp+4C0h+var_460], r12d
0x18002275f  mov     rax, [r14]
0x180022762  mov     [rsp+4C0h+var_4A0], rax
0x180022767  mov     r9d, r15d
0x18002276a  lea     r8, aIGetusertokenT; "I_GetUserToken (TargetSession: %u, Toke"...
0x180022771  mov     edx, 104h; unsigned __int64
0x180022776  lea     rcx, [rbp+3C0h+var_150]; char *
0x18002277d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180022782  test    eax, eax
0x180022784  jns     short loc_1800227F2
0x180022786  mov     ecx, cs:dword_1800DF020
0x18002278c  cmp     ecx, 3
0x18002278f  jbe     short loc_1800227F2
0x180022791  mov     [rsp+4C0h+var_468], eax
0x180022795  mov     [rsp+4C0h+var_450], r13
0x18002279a  mov     [rsp+4C0h+Pid], eax
0x18002279e  lea     rax, aStringcchprint; "StringCchPrintfA failed while writing i"...
0x1800227a5  mov     [rsp+4C0h+var_458], rax
0x1800227aa  lea     rax, aHresultFailedB; "HResult failed but continue"
0x1800227b1  mov     [rbp+3C0h+var_430], rax
0x1800227b5  lea     rax, [rsp+4C0h+var_468]
0x1800227ba  mov     [rsp+4C0h+var_480], rax
0x1800227bf  lea     rax, [rsp+4C0h+var_450]
0x1800227c4  mov     [rsp+4C0h+var_488], rax
0x1800227c9  lea     rax, [rsp+4C0h+Pid]
0x1800227ce  mov     [rsp+4C0h+var_490], rax
0x1800227d3  lea     rax, [rsp+4C0h+var_458]
0x1800227d8  mov     [rsp+4C0h+var_498], rax
0x1800227dd  lea     rax, [rbp+3C0h+var_430]
0x1800227e1  mov     [rsp+4C0h+var_4A0], rax
0x1800227e6  lea     rdx, byte_1800C6863
0x1800227ed  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800227f2  lea     rdx, [rsp+4C0h+var_460]; volatile unsigned int *
0x1800227f7  lea     rcx, [rbp+3C0h+var_150]; char *
0x1800227fe  call    ?DumpRpcCaller@CRpcUtils@@SAXPEBDAECKAEBU_EVENT_DESCRIPTOR@@@Z; CRpcUtils::DumpRpcCaller(char const *,ulong volatile &,_EVENT_DESCRIPTOR const &)
0x180022803  nop
  ... truncated ...
```
