# SERVER_RequestVersionVector

- ea: `0x1401a1e20`
- end: `0x1401a226d`
- name: `SERVER_RequestVersionVector`
- size: `1101`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, void *@<rdx>, __int64, int, int, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000e34c`
- `0x14002c2f4`
- `0x14007b760`
- `0x1401989a4`
- `0x14019b78c`
- `0x14019b870`
- `0x1401a1e20`
- `0x1401b0928`
- `0x1401b184c`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401a1ec1`
- `KERNEL32!GetCurrentThreadId` at `0x1401a1f80`
- `KERNEL32!GetCurrentThreadId` at `0x1401a1fec`
- `KERNEL32!GetCurrentThreadId` at `0x1401a2054`
- `KERNEL32!GetCurrentThreadId` at `0x1401a20c1`
- `KERNEL32!GetCurrentThreadId` at `0x1401a1ec1`
- `KERNEL32!GetCurrentThreadId` at `0x1401a1f80`
- `KERNEL32!GetCurrentThreadId` at `0x1401a1fec`
- `KERNEL32!GetCurrentThreadId` at `0x1401a2054`
- `KERNEL32!GetCurrentThreadId` at `0x1401a20c1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1401a2243`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1401a2243`

## string_xrefs

- `0x1401a1f60`: `vvGeneration is not 0 when requestType is REQUEST_SLOW_SYNC or REQUEST_SUBORDINATE_SYNC. connId:%? csId:%?`
- `0x1401a1fcc`: `changeType is not CHANGE_ALL when requestType is REQUEST_SLOW_SYNC or REQUEST_SUBORDINATE_SYNC. connId:%? csId:%?`
- `0x1401a1ea1`: `Invalid value (1) passed for changeType parameter. connId:%? csId:%?`

## pseudocode

```c
__int64 __fastcall SERVER_RequestVersionVector(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        unsigned int a3,
        const struct _GUID *a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7,
        __int64 a8)
{
  __int64 v8; // r15
  NetworkGlobals *v10; // rcx
  struct FrsStatus *v11; // rbx
  const wchar_t *v14; // rdx
  DWORD CurrentThreadId; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  struct FrsStatus *v18; // rax
  __int64 v19; // rcx
  DWORD v20; // eax
  __int64 v21; // rcx
  unsigned __int64 v22; // r8
  UpstreamTransport *v23; // rdi
  DWORD v24; // eax
  __int64 v25; // rcx
  DWORD v27; // [rsp+38h] [rbp-59h]
  DWORD v28; // [rsp+38h] [rbp-59h]
  const wchar_t *v29; // [rsp+50h] [rbp-41h] BYREF
  int v30; // [rsp+58h] [rbp-39h]
  int v31; // [rsp+5Ch] [rbp-35h]
  const wchar_t *v32; // [rsp+60h] [rbp-31h]
  unsigned int v33; // [rsp+68h] [rbp-29h] BYREF
  struct FrsStatus *v34; // [rsp+70h] [rbp-21h] BYREF
  int Reply; // [rsp+78h] [rbp-19h] BYREF
  struct UpstreamTransport *UpstreamTransport; // [rsp+80h] [rbp-11h] BYREF

  v8 = a8;
  v10 = (NetworkGlobals *)a7;
  v11 = 0;
  v33 = a3;
  v34 = 0;
  UpstreamTransport = 0;
  v14 = L"SERVER_RequestVersionVector";
  Reply = 0;
  if ( a7 == 1 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v29 = L"SERVER_RequestVersionVector";
      v32 = L"SRTR";
      v30 = 2233;
      v31 = 4;
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
        &v29,
        L"Invalid value (1) passed for changeType parameter. connId:%? csId:%?",
        a4,
        a5);
    }
    CurrentThreadId = GetCurrentThreadId();
    v34 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v16,
                                87,
                                0,
                                1,
                                "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                "SERVER_RequestVersionVector",
                                2237,
                                CurrentThreadId,
                                0);
    v11 = v34;
    if ( v34 )
      goto LABEL_22;
    v10 = (NetworkGlobals *)a7;
    v14 = L"SERVER_RequestVersionVector";
  }
  if ( a6 - 1 > 1 )
    goto LABEL_22;
  if ( v8 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v29 = L"SERVER_RequestVersionVector";
      v32 = L"SRTR";
      v30 = 2248;
      v31 = 4;
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
        &v29,
        L"vvGeneration is not 0 when requestType is REQUEST_SLOW_SYNC or REQUEST_SUBORDINATE_SYNC. connId:%? csId:%?",
        a4,
        a5);
    }
    v27 = GetCurrentThreadId();
    v18 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v17,
                                87,
                                0,
                                1,
                                "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                "SERVER_RequestVersionVector",
                                2253,
                                v27,
                                0);
  }
  else
  {
    if ( (_DWORD)v10 == 2 )
      goto LABEL_22;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v29 = L"SERVER_RequestVersionVector";
      v32 = L"SRTR";
      v30 = 2257;
      v31 = 4;
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
        &v29,
        L"changeType is not CHANGE_ALL when requestType is REQUEST_SLOW_SYNC or REQUEST_SUBORDINATE_SYNC. connId:%? csId:%?",
        a4,
        a5);
    }
    v28 = GetCurrentThreadId();
    v18 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v19,
                                87,
                                0,
                                1,
                                "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                "SERVER_RequestVersionVector",
                                2262,
                                v28,
                                0);
  }
  v34 = v18;
  v11 = v18;
LABEL_22:
  if ( v11 )
    goto LABEL_35;
  if ( isInBackupRestore )
  {
    if ( *isInBackupRestore )
    {
      v20 = GetCurrentThreadId();
      v34 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  v21,
                                  9036,
                                  0,
                                  3,
                                  "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                  "SERVER_RequestVersionVector",
                                  2294,
                                  v20,
                                  0);
      v11 = v34;
      if ( v34 )
        goto LABEL_35;
    }
  }
  UpstreamTransport = NetworkGlobals::FindUpstreamTransport(v10, a2, a4);
  v23 = UpstreamTransport;
  if ( !UpstreamTransport )
  {
    v24 = GetCurrentThreadId();
    v34 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v25,
                                9026,
                                0,
                                3,
                                "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                "SERVER_RequestVersionVector",
                                2306,
                                v24,
                                0);
    v11 = v34;
    if ( v34 )
      goto LABEL_35;
  }
  UpstreamTransport::CountBytes(v23, 4u, v22);
  v34 = (struct FrsStatus *)UpstreamTransport::RequestVvUp(v23, v33, a5, a6, a7, v8);
  v11 = v34;
  if ( v34 )
  {
LABEL_35:
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v29 = L"SERVER_RequestVersionVector";
      v30 = 2340;
      v32 = L"SRTR";
      v31 = 3;
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned long,enum __MIDL___MIDL_itf_frstransport_0000_0000_0007,enum __MIDL___MIDL_itf_frstransport_0000_0000_0008,FrsStatus>(
        (unsigned int)&v29,
        (_DWORD)v14,
        (_DWORD)a4,
        a5,
        (__int64)&v33,
        (__int64)&a6,
        (__int64)&a7,
        (__int64)v11);
    }
    Reply = *((_DWORD *)v11 + 1);
    CLEAR_ERROR(&v34);
  }
  else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v30 = 2353;
    v29 = L"SERVER_RequestVersionVector";
    v31 = 4;
    v32 = L"SRTR";
    dbgobj::DbgPrint<unsigned short,_GUID,_GUID,unsigned long,enum __MIDL___MIDL_itf_frstransport_0000_0000_0007,enum __MIDL___MIDL_itf_frstransport_0000_0000_0008>(
      (unsigned int)&v29,
      (_DWORD)v14,
      (_DWORD)a4,
      a5,
      (__int64)&v33,
      (__int64)&a6,
      (__int64)&a7);
  }
  RpcAsyncCompleteCall(pAsync, &Reply);
  return ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&UpstreamTransport);
}

```

## disassembly

```asm
0x1401a1e20  push    rbp
0x1401a1e22  push    rbx
0x1401a1e23  push    rsi
0x1401a1e24  push    rdi
0x1401a1e25  push    r12
0x1401a1e27  push    r13
0x1401a1e29  push    r14
0x1401a1e2b  push    r15
0x1401a1e2d  lea     rbp, [rsp-7]
0x1401a1e32  sub     rsp, 98h
0x1401a1e39  mov     r14, [rbp+3Fh+arg_20]
0x1401a1e3d  xor     r13d, r13d
0x1401a1e40  mov     r15, [rbp+3Fh+arg_38]
0x1401a1e47  mov     r12, rcx
0x1401a1e4a  mov     ecx, [rbp+3Fh+arg_30]
0x1401a1e4d  mov     ebx, r13d
0x1401a1e50  mov     [rbp+3Fh+var_68], r8d
0x1401a1e54  mov     rdi, rdx
0x1401a1e57  mov     [rbp+3Fh+var_60], rbx
0x1401a1e5b  mov     rsi, r9
0x1401a1e5e  mov     [rbp+3Fh+var_50], r13
0x1401a1e62  lea     rdx, aServerRequestv_0; "SERVER_RequestVersionVector"
0x1401a1e69  mov     [rbp+3Fh+Reply], r13d
0x1401a1e6d  lea     r8, aSrtr; "SRTR"
0x1401a1e74  cmp     ecx, 1
0x1401a1e77  jnz     loc_1401A1F29
0x1401a1e7d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401a1e84  test    rax, rax
0x1401a1e87  jz      short loc_1401A1EC1
0x1401a1e89  cmp     [rax+40h], r13d
0x1401a1e8d  jz      short loc_1401A1EC1
0x1401a1e8f  cmp     dword ptr [rax+38h], 4
0x1401a1e93  jl      short loc_1401A1EC1
0x1401a1e95  mov     [rbp+3Fh+var_80], rdx
0x1401a1e99  lea     rcx, [rbp+3Fh+var_80]
0x1401a1e9d  mov     [rbp+3Fh+var_70], r8
0x1401a1ea1  lea     rdx, aInvalidValue1P; "Invalid value (1) passed for changeType"...
0x1401a1ea8  mov     r8, rsi
0x1401a1eab  mov     [rbp+3Fh+var_78], 8B9h
0x1401a1eb2  mov     r9, r14
0x1401a1eb5  mov     [rbp+3Fh+var_74], 4
0x1401a1ebc  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x1401a1ec1  call    cs:__imp_GetCurrentThreadId
0x1401a1ec8  nop     dword ptr [rax+rax+00h]
0x1401a1ecd  mov     [rsp+0D0h+var_90], r13
0x1401a1ed2  mov     r9d, 1
0x1401a1ed8  mov     dword ptr [rsp+0D0h+var_98], eax
0x1401a1edc  xor     r8d, r8d
0x1401a1edf  lea     rax, aServerRequestv; "SERVER_RequestVersionVector"
0x1401a1ee6  mov     dword ptr [rsp+0D0h+var_A0], 8BDh
0x1401a1eee  mov     [rsp+0D0h+var_A8], rax
0x1401a1ef3  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a1efa  lea     edx, [r9+56h]
0x1401a1efe  mov     [rsp+0D0h+var_B0], rax
0x1401a1f03  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a1f08  mov     [rbp+3Fh+var_60], rax
0x1401a1f0c  mov     rbx, rax
0x1401a1f0f  test    rax, rax
0x1401a1f12  jnz     loc_1401A203A
0x1401a1f18  mov     ecx, [rbp+3Fh+arg_30]
0x1401a1f1b  lea     rdx, aServerRequestv_0; "SERVER_RequestVersionVector"
0x1401a1f22  lea     r8, aSrtr; "SRTR"
0x1401a1f29  mov     eax, [rbp+3Fh+arg_28]
0x1401a1f2c  dec     eax
0x1401a1f2e  cmp     eax, 1
0x1401a1f31  ja      loc_1401A203A
0x1401a1f37  test    r15, r15
0x1401a1f3a  jz      short loc_1401A1F9F
0x1401a1f3c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401a1f43  test    rax, rax
0x1401a1f46  jz      short loc_1401A1F80
0x1401a1f48  cmp     [rax+40h], r13d
0x1401a1f4c  jz      short loc_1401A1F80
0x1401a1f4e  cmp     dword ptr [rax+38h], 4
0x1401a1f52  jl      short loc_1401A1F80
0x1401a1f54  mov     [rbp+3Fh+var_80], rdx
0x1401a1f58  lea     rcx, [rbp+3Fh+var_80]
0x1401a1f5c  mov     [rbp+3Fh+var_70], r8
0x1401a1f60  lea     rdx, aVvgenerationIs; "vvGeneration is not 0 when requestType "...
0x1401a1f67  mov     r8, rsi
0x1401a1f6a  mov     [rbp+3Fh+var_78], 8C8h
0x1401a1f71  mov     r9, r14
0x1401a1f74  mov     [rbp+3Fh+var_74], 4
0x1401a1f7b  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x1401a1f80  call    cs:__imp_GetCurrentThreadId
0x1401a1f87  nop     dword ptr [rax+rax+00h]
0x1401a1f8c  mov     [rsp+0D0h+var_90], r13
0x1401a1f91  mov     dword ptr [rsp+0D0h+var_98], eax
0x1401a1f95  mov     dword ptr [rsp+0D0h+var_A0], 8CDh
0x1401a1f9d  jmp     short loc_1401A2009
0x1401a1f9f  cmp     ecx, 2
0x1401a1fa2  jz      loc_1401A203A
0x1401a1fa8  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401a1faf  test    rax, rax
0x1401a1fb2  jz      short loc_1401A1FEC
0x1401a1fb4  cmp     [rax+40h], r13d
0x1401a1fb8  jz      short loc_1401A1FEC
0x1401a1fba  cmp     dword ptr [rax+38h], 4
0x1401a1fbe  jl      short loc_1401A1FEC
0x1401a1fc0  mov     [rbp+3Fh+var_80], rdx
0x1401a1fc4  lea     rcx, [rbp+3Fh+var_80]
0x1401a1fc8  mov     [rbp+3Fh+var_70], r8
0x1401a1fcc  lea     rdx, aChangetypeIsNo; "changeType is not CHANGE_ALL when reque"...
0x1401a1fd3  mov     r8, rsi
0x1401a1fd6  mov     [rbp+3Fh+var_78], 8D1h
0x1401a1fdd  mov     r9, r14
0x1401a1fe0  mov     [rbp+3Fh+var_74], 4
0x1401a1fe7  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x1401a1fec  call    cs:__imp_GetCurrentThreadId
0x1401a1ff3  nop     dword ptr [rax+rax+00h]
0x1401a1ff8  mov     [rsp+0D0h+var_90], r13
0x1401a1ffd  mov     dword ptr [rsp+0D0h+var_98], eax
0x1401a2001  mov     dword ptr [rsp+0D0h+var_A0], 8D6h
0x1401a2009  mov     r9d, 1
0x1401a200f  lea     rax, aServerRequestv; "SERVER_RequestVersionVector"
0x1401a2016  mov     [rsp+0D0h+var_A8], rax
0x1401a201b  xor     r8d, r8d
0x1401a201e  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a2025  mov     [rsp+0D0h+var_B0], rax
0x1401a202a  lea     edx, [r9+56h]
0x1401a202e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a2033  mov     [rbp+3Fh+var_60], rax
0x1401a2037  mov     rbx, rax
0x1401a203a  test    rbx, rbx
0x1401a203d  jnz     loc_1401A21C2
0x1401a2043  mov     rax, cs:?isInBackupRestore@@3PEAHEA; int * isInBackupRestore
0x1401a204a  test    rax, rax
0x1401a204d  jz      short loc_1401A20AA
0x1401a204f  cmp     [rax], r13d
0x1401a2052  jz      short loc_1401A20AA
0x1401a2054  call    cs:__imp_GetCurrentThreadId
0x1401a205b  nop     dword ptr [rax+rax+00h]
0x1401a2060  mov     [rsp+0D0h+var_90], r13
0x1401a2065  lea     r9d, [rbx+3]
0x1401a2069  mov     dword ptr [rsp+0D0h+var_98], eax
0x1401a206d  xor     r8d, r8d
0x1401a2070  lea     rax, aServerRequestv; "SERVER_RequestVersionVector"
0x1401a2077  mov     dword ptr [rsp+0D0h+var_A0], 8F6h
0x1401a207f  mov     [rsp+0D0h+var_A8], rax
0x1401a2084  mov     edx, 234Ch
0x1401a2089  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a2090  mov     [rsp+0D0h+var_B0], rax
0x1401a2095  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a209a  mov     [rbp+3Fh+var_60], rax
0x1401a209e  mov     rbx, rax
0x1401a20a1  test    rax, rax
0x1401a20a4  jnz     loc_1401A21C2
0x1401a20aa  mov     r8, rsi; struct _GUID *
0x1401a20ad  mov     rdx, rdi; void *
0x1401a20b0  call    ?FindUpstreamTransport@NetworkGlobals@@QEAAPEAVUpstreamTransport@@PEAXAEBU_GUID@@@Z; NetworkGlobals::FindUpstreamTransport(void *,_GUID const &)
0x1401a20b5  mov     [rbp+3Fh+var_50], rax
0x1401a20b9  mov     rdi, rax
0x1401a20bc  test    rax, rax
0x1401a20bf  jnz     short loc_1401A2117
0x1401a20c1  call    cs:__imp_GetCurrentThreadId
0x1401a20c8  nop     dword ptr [rax+rax+00h]
0x1401a20cd  mov     [rsp+0D0h+var_90], r13
0x1401a20d2  lea     r9d, [rdi+3]
0x1401a20d6  mov     dword ptr [rsp+0D0h+var_98], eax
0x1401a20da  xor     r8d, r8d
0x1401a20dd  lea     rax, aServerRequestv; "SERVER_RequestVersionVector"
0x1401a20e4  mov     dword ptr [rsp+0D0h+var_A0], 902h
0x1401a20ec  mov     [rsp+0D0h+var_A8], rax
0x1401a20f1  mov     edx, 2342h
0x1401a20f6  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a20fd  mov     [rsp+0D0h+var_B0], rax
0x1401a2102  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a2107  mov     [rbp+3Fh+var_60], rax
0x1401a210b  mov     rbx, rax
0x1401a210e  test    rax, rax
0x1401a2111  jnz     loc_1401A21C2
0x1401a2117  mov     edx, 4; unsigned __int64
0x1401a211c  mov     rcx, rdi; this
0x1401a211f  call    ?CountBytes@UpstreamTransport@@QEAAX_K0@Z; UpstreamTransport::CountBytes(unsigned __int64,unsigned __int64)
0x1401a2124  mov     eax, [rbp+3Fh+arg_30]
0x1401a2127  mov     r8, r14
0x1401a212a  mov     r9d, [rbp+3Fh+arg_28]
0x1401a212e  mov     rcx, rdi
0x1401a2131  mov     edx, [rbp+3Fh+var_68]
0x1401a2134  mov     [rsp+0D0h+var_A8], r15
0x1401a2139  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1401a213d  call    ?RequestVvUp@UpstreamTransport@@QEAAPEAVFrsStatus@@KAEBU_GUID@@W4__MIDL___MIDL_itf_frstransport_0000_0000_0007@@W4__MIDL___MIDL_itf_frstransport_0000_0000_0008@@_K@Z; UpstreamTransport::RequestVvUp(ulong,_GUID const &,__MIDL___MIDL_itf_frstransport_0000_0000_0007,__MIDL___MIDL_itf_frstransport_0000_0000_0008,unsigned __int64)
0x1401a2142  mov     [rbp+3Fh+var_60], rax
0x1401a2146  mov     rbx, rax
0x1401a2149  test    rax, rax
0x1401a214c  jnz     short loc_1401A21C2
0x1401a214e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401a2155  test    rax, rax
0x1401a2158  jz      loc_1401A223C
0x1401a215e  cmp     [rax+40h], r13d
0x1401a2162  jz      loc_1401A223C
0x1401a2168  cmp     dword ptr [rax+38h], 4
0x1401a216c  jl      loc_1401A223C
0x1401a2172  lea     rax, aServerRequestv_0; "SERVER_RequestVersionVector"
0x1401a2179  mov     [rbp+3Fh+var_78], 931h
0x1401a2180  mov     [rbp+3Fh+var_80], rax
0x1401a2184  lea     rcx, [rbp+3Fh+var_80]
0x1401a2188  lea     rax, aSrtr; "SRTR"
0x1401a218f  mov     [rbp+3Fh+var_74], 4
0x1401a2196  mov     [rbp+3Fh+var_70], rax
0x1401a219a  mov     r9, r14
0x1401a219d  lea     rax, [rbp+3Fh+arg_30]
0x1401a21a1  mov     r8, rsi
0x1401a21a4  mov     [rsp+0D0h+var_A0], rax
0x1401a21a9  lea     rax, [rbp+3Fh+arg_28]
0x1401a21ad  mov     [rsp+0D0h+var_A8], rax
0x1401a21b2  lea     rax, [rbp+3Fh+var_68]
0x1401a21b6  mov     [rsp+0D0h+var_B0], rax
0x1401a21bb  call    ??$DbgPrint@GU_GUID@@U1@KW4__MIDL___MIDL_itf_frstransport_0000_0000_0007@@W4__MIDL___MIDL_itf_frstransport_0000_0000_0008@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1AEBKAEBW4__MIDL___MIDL_itf_frstransport_0000_0000_0007@@AEBW4__MIDL___MIDL_itf_frstransport_0000_0000_0008@@@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID,ulong,__MIDL___MIDL_itf_frstransport_0000_0000_0007,__MIDL___MIDL_itf_frstransport_0000_0000_0008>(ushort const *,_GUID const &,_GUID const &,ulong const &,__MIDL___MIDL_itf_frstransport_0000_0000_0007 const &,__MIDL___MIDL_itf_frstransport_0000_0000_0008 const &)
0x1401a21c0  jmp     short loc_1401A223C
0x1401a21c2  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401a21c9  test    rax, rax
0x1401a21cc  jz      short loc_1401A222D
0x1401a21ce  cmp     [rax+40h], r13d
0x1401a21d2  jz      short loc_1401A222D
0x1401a21d4  cmp     dword ptr [rax+38h], 3
0x1401a21d8  jl      short loc_1401A222D
0x1401a21da  mov     [rsp+0D0h+var_98], rbx
0x1401a21df  lea     rax, aServerRequestv_0; "SERVER_RequestVersionVector"
0x1401a21e6  mov     [rbp+3Fh+var_80], rax
0x1401a21ea  lea     rcx, [rbp+3Fh+var_80]
0x1401a21ee  lea     rax, aSrtr; "SRTR"
0x1401a21f5  mov     [rbp+3Fh+var_78], 924h
0x1401a21fc  mov     [rbp+3Fh+var_70], rax
0x1401a2200  mov     r9, r14
0x1401a2203  lea     rax, [rbp+3Fh+arg_30]
0x1401a2207  mov     [rbp+3Fh+var_74], 3
0x1401a220e  mov     [rsp+0D0h+var_A0], rax
0x1401a2213  mov     r8, rsi
0x1401a2216  lea     rax, [rbp+3Fh+arg_28]
0x1401a221a  mov     [rsp+0D0h+var_A8], rax
0x1401a221f  lea     rax, [rbp+3Fh+var_68]
0x1401a2223  mov     [rsp+0D0h+var_B0], rax
0x1401a2228  call    ??$DbgPrint@GU_GUID@@U1@KW4__MIDL___MIDL_itf_frstransport_0000_0000_0007@@W4__MIDL___MIDL_itf_frstransport_0000_0000_0008@@VFrsStatus@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1AEBKAEBW4__MIDL___MIDL_itf_frstransport_0000_0000_0007@@AEBW4__MIDL___MIDL_itf_frstransport_0000_0000_0008@@AEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID,ulong,__MIDL___MIDL_itf_frstransport_0000_0000_0007,__MIDL___MIDL_itf_frstransport_0000_0000_0008,FrsStatus>(ushort const *,_GUID const &,_GUID const &,ulong const &,__MIDL___MIDL_itf_frstransport_0000_0000_0007 const &,__MIDL___MIDL_itf_frstransport_0000_0000_0008 const &,FrsStatus const &)
0x1401a222d  mov     eax, [rbx+4]
0x1401a2230  lea     rcx, [rbp+3Fh+var_60]; struct FrsStatus **
0x1401a2234  mov     [rbp+3Fh+Reply], eax
0x1401a2237  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401a223c  lea     rdx, [rbp+3Fh+Reply]; Reply
0x1401a2240  mov     rcx, r12; pAsync
0x1401a2243  call    cs:__imp_RpcAsyncCompleteCall
0x1401a224a  nop     dword ptr [rax+rax+00h]
0x1401a224f  lea     rcx, [rbp+3Fh+var_50]
0x1401a2253  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x1401a2258  add     rsp, 98h
0x1401a225f  pop     r15
0x1401a2261  pop     r14
0x1401a2263  pop     r13
0x1401a2265  pop     r12
0x1401a2267  pop     rdi
0x1401a2268  pop     rsi
0x1401a2269  pop     rbx
0x1401a226a  pop     rbp
0x1401a226b  retn
```
