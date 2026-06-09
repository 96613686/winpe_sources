# AsyncRpcHandler::RequestUpdates(_GUID const &,VersionChainVector const &,ulong,int,__MIDL___MIDL_itf_frstransport_0000_0000_0004)

- ea: `0x1401ab43c`
- end: `0x1401ab891`
- name: `?RequestUpdates@AsyncRpcHandler@@QEAAPEAVFrsStatus@@AEBU_GUID@@AEBVVersionChainVector@@KHW4__MIDL___MIDL_itf_frstransport_0000_0000_0004@@@Z`
- size: `1109`
- prototype: `struct FrsStatus *__high(const struct _GUID *, const struct VersionChainVector *, unsigned int, int, enum __MIDL___MIDL_itf_frstransport_0000_0000_0004)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1401ab8a0`

## callees

- `0x1400036d0`
- `0x1400046cc`
- `0x14000e34c`
- `0x140024964`
- `0x140024c84`
- `0x1401a3074`
- `0x1401a3568`
- `0x1401a4d80`
- `0x1401a82ac`
- `0x1401ab43c`
- `0x1401ad48c`
- `0x1401ae578`
- `0x1401b30b0`
- `0x1401b3a04`
- `0x1401b6804`
- `0x1401b9494`
- `0x1401c4300`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401ab49a`
- `KERNEL32!GetCurrentThreadId` at `0x1401ab508`
- `KERNEL32!GetCurrentThreadId` at `0x1401ab6ca`
- `KERNEL32!GetCurrentThreadId` at `0x1401ab81e`
- `KERNEL32!GetCurrentThreadId` at `0x1401ab49a`
- `KERNEL32!GetCurrentThreadId` at `0x1401ab508`
- `KERNEL32!GetCurrentThreadId` at `0x1401ab6ca`
- `KERNEL32!GetCurrentThreadId` at `0x1401ab81e`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1401ab4f5`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1401ab4f5`

## string_xrefs

- `0x1401ab740`: `AsyncRpcHandler::RequestUpdates`
- `0x1401ab7c2`: `AsyncRpcHandler::RequestUpdates`
- `0x1401ab48d`: `AsyncRpcHandler::RequestUpdates`
- `0x1401ab4e5`: `AsyncRpcHandler::RequestUpdates`
- `0x1401ab6f5`: `AsyncRpcHandler::RequestUpdates`
- `0x1401ab722`: `AsyncRpcHandler::RequestUpdates`
- `0x1401ab7a4`: `AsyncRpcHandler::RequestUpdates`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AsyncRpcHandler::RequestUpdates(
        __int64 a1,
        _OWORD *a2,
        VersionChainVector *a3,
        unsigned int a4,
        int a5,
        int a6)
{
  unsigned __int64 v6; // rdi
  __int64 v10; // rsi
  _DWORD *v11; // r12
  DWORD CurrentThreadId; // eax
  __int64 v13; // rcx
  int v14; // edx
  struct FrsStatus *v15; // r14
  DWORD v16; // eax
  __int64 v17; // rcx
  bool v18; // of
  size_t v19; // rdi
  void *v20; // rbx
  DWORD v21; // eax
  int v22; // r8d
  DWORD v23; // eax
  __int64 v24; // rcx
  int v26; // [rsp+30h] [rbp-69h]
  unsigned int v27; // [rsp+70h] [rbp-29h] BYREF
  struct _FRS_VERSION_VECTOR *v28; // [rsp+78h] [rbp-21h] BYREF
  struct FrsStatus *v29; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v30[8]; // [rsp+88h] [rbp-11h] BYREF
  const wchar_t *v31; // [rsp+90h] [rbp-9h] BYREF
  int v32; // [rsp+98h] [rbp-1h]
  int v33; // [rsp+9Ch] [rbp+3h]
  const wchar_t *v34; // [rsp+A0h] [rbp+7h]
  unsigned int v35; // [rsp+F0h] [rbp+57h] BYREF
  unsigned int v36; // [rsp+108h] [rbp+6Fh]

  v36 = a4;
  v6 = a4;
  v10 = 0;
  v35 = 0;
  v28 = 0;
  v27 = 0;
  ScopedCrewLock::ScopedCrewLock(v30, a1 + 176);
  v11 = (_DWORD *)(a1 + 280);
  if ( *(_DWORD *)(a1 + 280) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v15 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v13,
                                5023,
                                0,
                                1,
                                "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                                "AsyncRpcHandler::RequestUpdates",
                                2281,
                                CurrentThreadId,
                                0);
    if ( v15 )
      goto LABEL_17;
  }
  v35 = RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(a1 + 48), 0x70u);
  if ( v35 )
  {
    v16 = GetCurrentThreadId();
    v15 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v17,
                                v35,
                                0,
                                1,
                                "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                                "AsyncRpcHandler::RequestUpdates",
                                2289,
                                v16,
                                0);
    if ( v15 )
      goto LABEL_17;
  }
  v29 = VersionChainVector::Get(a3, (void *(*)(unsigned __int64))operator_new, &v27, &v28);
  CLEAR_ERROR(&v29);
  v15 = BandwidthThrottler::ThrottleBytes(*(BandwidthThrottler **)(a1 + 40), 32LL * v27 + 164, 0, 0);
  if ( v15 )
    goto LABEL_17;
  *(_QWORD *)(a1 + 72) = a1;
  *(_DWORD *)(a1 + 92) = 3;
  *(_QWORD *)(a1 + 96) = *(_QWORD *)(a1 + 168);
  *(_QWORD *)(a1 + 112) = 5;
  *(_QWORD *)(a1 + 120) = a1;
  *(_DWORD *)(a1 + 104) = 384;
  *(_DWORD *)(a1 + 296) = 1;
  *v11 = 1;
  *(_OWORD *)(a1 + 304) = *a2;
  v18 = (v6 * (unsigned __int128)0x2B0uLL) >> 64 != 0;
  v19 = 688 * v6;
  if ( v18 )
    v19 = -1;
  v20 = operator new(v19);
  memset_0(v20, 0, v19);
  *(_QWORD *)(a1 + 320) = v20;
  *(_DWORD *)(a1 + 336) = a5;
  *(_DWORD *)(a1 + 328) = v36;
  *(_DWORD *)(a1 + 332) = 0;
  *(_DWORD *)(a1 + 340) = 3;
  RefCountObject::AddRef((RefCountObject *)a1);
  v35 = RpcRequestUpdates(
          (int)a1 + 48,
          *(_QWORD *)(a1 + 160),
          (unsigned int)*(_QWORD *)(a1 + 32) + 32,
          (_DWORD)a2,
          *(_DWORD *)(a1 + 328),
          *(_DWORD *)(a1 + 336),
          a6,
          v27,
          (__int64)v28,
          *(_QWORD *)(a1 + 320),
          a1 + 332,
          a1 + 340,
          a1 + 344,
          a1 + 360);
  if ( !v35 )
    goto LABEL_12;
  v21 = GetCurrentThreadId();
  v15 = (struct FrsStatus *)LogTranslatedRemoteError(
                              v35,
                              v35 == 1237,
                              v22,
                              (unsigned int)"AsyncRpcHandler::RequestUpdates",
                              2368,
                              v21,
                              v26,
                              0);
  *v11 = 2;
  RefCountObject::Release((RefCountObject *)a1);
  if ( v15 )
  {
LABEL_17:
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v31 = L"AsyncRpcHandler::RequestUpdates";
      v32 = 2375;
      v33 = 2;
      v34 = L"DOWN";
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID,enum AsyncRpcHandler::RequestType,enum ICancelContext::RequestState,long,FrsStatus>(
        (unsigned int)&v31,
        v14,
        *(_QWORD *)(a1 + 32) + 32,
        (_DWORD)a2,
        a1 + 296,
        a1 + 280,
        (__int64)&v35,
        (__int64)v15);
    }
  }
  else
  {
LABEL_12:
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v31 = L"AsyncRpcHandler::RequestUpdates";
      v32 = 2386;
      v33 = 5;
      v34 = L"DOWN";
      v29 = (struct FrsStatus *)a1;
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID,enum AsyncRpcHandler::RequestType,enum ICancelContext::RequestState,unsigned __int64>(
        (unsigned int)&v31,
        v14,
        *(_QWORD *)(a1 + 32) + 32,
        (_DWORD)a2,
        a1 + 296,
        a1 + 280,
        (__int64)&v29);
    }
    *(_QWORD *)(a1 + 376) = TaskPool::ThreadCounterAdd();
  }
  if ( v15 )
  {
    v23 = GetCurrentThreadId();
    v10 = FrsStatusList::PushNewError(
            v24,
            *((unsigned int *)v15 + 1),
            *((unsigned int *)v15 + 2),
            *(unsigned int *)v15,
            "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
            "AsyncRpcHandler::RequestUpdates",
            2399,
            v23,
            v15);
  }
  ScopedCrewLock::~ScopedCrewLock((ScopedCrewLock *)v30);
  scoped_any<_FRS_VERSION_VECTOR *,close_delete,null_t,0>::~scoped_any<_FRS_VERSION_VECTOR *,close_delete,null_t,0>(&v28);
  return v10;
}

```

## disassembly

```asm
0x1401ab43c  mov     [rsp-8+arg_8], rbx
0x1401ab441  mov     [rsp-8+arg_18], r9d
0x1401ab446  push    rbp
0x1401ab447  push    rsi
0x1401ab448  push    rdi
0x1401ab449  push    r12
0x1401ab44b  push    r13
0x1401ab44d  push    r14
0x1401ab44f  push    r15
0x1401ab451  lea     rbp, [rsp-17h]
0x1401ab456  sub     rsp, 0B0h
0x1401ab45d  mov     edi, r9d
0x1401ab460  mov     rbx, r8
0x1401ab463  mov     r13, rdx
0x1401ab466  mov     r15, rcx
0x1401ab469  xor     esi, esi
0x1401ab46b  mov     [rbp+47h+arg_0], esi
0x1401ab46e  mov     [rbp+47h+var_68], rsi
0x1401ab472  mov     [rbp+47h+var_70], esi
0x1401ab475  lea     rdx, [rcx+0B0h]
0x1401ab47c  lea     rcx, [rbp+47h+var_58]
0x1401ab480  call    ??0ScopedCrewLock@@QEAA@AEAVCREWLock@@UWrite@0@@Z; ScopedCrewLock::ScopedCrewLock(CREWLock &,ScopedCrewLock::Write)
0x1401ab485  nop
0x1401ab486  lea     r12, [r15+118h]
0x1401ab48d  lea     r14, aAsyncrpchandle_17; "AsyncRpcHandler::RequestUpdates"
0x1401ab494  cmp     [r12], esi
0x1401ab498  jz      short loc_1401AB4EC
0x1401ab49a  call    cs:__imp_GetCurrentThreadId
0x1401ab4a1  nop     dword ptr [rax+rax+00h]
0x1401ab4a6  mov     [rsp+0E0h+var_A0], rsi
0x1401ab4ab  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1401ab4af  mov     dword ptr [rsp+0E0h+var_B0], 8E9h
0x1401ab4b7  mov     [rsp+0E0h+var_B8], r14
0x1401ab4bc  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401ab4c3  mov     [rsp+0E0h+var_C0], rax
0x1401ab4c8  lea     r9d, [rsi+1]
0x1401ab4cc  xor     r8d, r8d
0x1401ab4cf  mov     edx, 139Fh
0x1401ab4d4  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401ab4d9  mov     r14, rax
0x1401ab4dc  test    rax, rax
0x1401ab4df  jnz     loc_1401AB7A4
0x1401ab4e5  lea     r14, aAsyncrpchandle_17; "AsyncRpcHandler::RequestUpdates"
0x1401ab4ec  lea     rcx, [r15+30h]; pAsync
0x1401ab4f0  mov     edx, 70h ; 'p'; Size
0x1401ab4f5  call    cs:__imp_RpcAsyncInitializeHandle
0x1401ab4fc  nop     dword ptr [rax+rax+00h]
0x1401ab501  mov     [rbp+47h+arg_0], eax
0x1401ab504  test    eax, eax
0x1401ab506  jz      short loc_1401AB553
0x1401ab508  call    cs:__imp_GetCurrentThreadId
0x1401ab50f  nop     dword ptr [rax+rax+00h]
0x1401ab514  mov     [rsp+0E0h+var_A0], rsi
0x1401ab519  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1401ab51d  mov     dword ptr [rsp+0E0h+var_B0], 8F1h
0x1401ab525  mov     [rsp+0E0h+var_B8], r14
0x1401ab52a  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401ab531  mov     [rsp+0E0h+var_C0], rax
0x1401ab536  mov     r9d, 1
0x1401ab53c  xor     r8d, r8d
0x1401ab53f  mov     edx, [rbp+47h+arg_0]
0x1401ab542  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401ab547  mov     r14, rax
0x1401ab54a  test    rax, rax
0x1401ab54d  jnz     loc_1401AB7A4
0x1401ab553  lea     r9, [rbp+47h+var_68]; struct _FRS_VERSION_VECTOR **
0x1401ab557  lea     r8, [rbp+47h+var_70]; unsigned int *
0x1401ab55b  lea     rdx, ?operator_new@@YAPEAX_K@Z; void *(*)(unsigned __int64)
0x1401ab562  mov     rcx, rbx; this
0x1401ab565  call    ?Get@VersionChainVector@@QEBAPEAVFrsStatus@@P6APEAX_K@ZPEAKPEAPEAU_FRS_VERSION_VECTOR@@@Z; VersionChainVector::Get(void * (*)(unsigned __int64),ulong *,_FRS_VERSION_VECTOR * *)
0x1401ab56a  mov     [rbp+47h+var_60], rax
0x1401ab56e  lea     rcx, [rbp+47h+var_60]; struct FrsStatus **
0x1401ab572  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401ab577  mov     edx, [rbp+47h+var_70]
0x1401ab57a  shl     rdx, 5
0x1401ab57e  add     rdx, 0A4h; unsigned __int64
0x1401ab585  xor     r9d, r9d; int
0x1401ab588  xor     r8d, r8d; unsigned __int64
0x1401ab58b  mov     rcx, [r15+28h]; this
0x1401ab58f  call    ?ThrottleBytes@BandwidthThrottler@@QEAAPEAVFrsStatus@@_K0H@Z; BandwidthThrottler::ThrottleBytes(unsigned __int64,unsigned __int64,int)
0x1401ab594  mov     r14, rax
0x1401ab597  test    rax, rax
0x1401ab59a  jnz     loc_1401AB7A4
0x1401ab5a0  mov     [r15+48h], r15
0x1401ab5a4  mov     dword ptr [r15+5Ch], 3
0x1401ab5ac  mov     rax, [r15+0A8h]
0x1401ab5b3  mov     [r15+60h], rax
0x1401ab5b7  mov     qword ptr [r15+70h], 5
0x1401ab5bf  mov     [r15+78h], r15
0x1401ab5c3  mov     dword ptr [r15+68h], 180h
0x1401ab5cb  lea     ecx, [r14+1]
0x1401ab5cf  mov     [r15+128h], ecx
0x1401ab5d6  mov     [r12], ecx
0x1401ab5da  movups  xmm0, xmmword ptr [r13+0]
0x1401ab5df  movdqu  xmmword ptr [r15+130h], xmm0
0x1401ab5e8  mov     eax, 2B0h
0x1401ab5ed  mul     rdi
0x1401ab5f0  mov     rdi, rax
0x1401ab5f3  lea     rax, [r14-1]
0x1401ab5f7  cmovo   rdi, rax
0x1401ab5fb  mov     rcx, rdi; Size
0x1401ab5fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401ab603  mov     rbx, rax
0x1401ab606  mov     r8, rdi; Size
0x1401ab609  xor     edx, edx; Val
0x1401ab60b  mov     rcx, rax; void *
0x1401ab60e  call    memset_0
0x1401ab613  mov     [r15+140h], rbx
0x1401ab61a  mov     eax, [rbp+47h+arg_20]
0x1401ab61d  mov     [r15+150h], eax
0x1401ab624  mov     eax, [rbp+47h+arg_18]
0x1401ab627  mov     [r15+148h], eax
0x1401ab62e  lea     rdi, [r15+14Ch]
0x1401ab635  mov     [rdi], esi
0x1401ab637  lea     rbx, [r15+154h]
0x1401ab63e  mov     dword ptr [rbx], 3
0x1401ab644  mov     rcx, r15; this
0x1401ab647  call    ?AddRef@RefCountObject@@QEAAJXZ; RefCountObject::AddRef(void)
0x1401ab64c  mov     r10, [r15+140h]
0x1401ab653  mov     edx, [r15+150h]
0x1401ab65a  mov     r11d, [r15+148h]
0x1401ab661  mov     r8, [r15+20h]
0x1401ab665  add     r8, 20h ; ' '
0x1401ab669  lea     rax, [r15+168h]
0x1401ab670  lea     r9, [r15+158h]
0x1401ab677  mov     [rsp+0E0h+var_78], rax
0x1401ab67c  mov     [rsp+0E0h+var_80], r9
0x1401ab681  mov     [rsp+0E0h+var_88], rbx
0x1401ab686  mov     [rsp+0E0h+var_90], rdi
0x1401ab68b  mov     [rsp+0E0h+var_98], r10
0x1401ab690  mov     rax, [rbp+47h+var_68]
0x1401ab694  mov     [rsp+0E0h+var_A0], rax
0x1401ab699  mov     eax, [rbp+47h+var_70]
0x1401ab69c  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1401ab6a0  mov     eax, [rbp+47h+arg_28]
0x1401ab6a3  mov     dword ptr [rsp+0E0h+var_B0], eax
0x1401ab6a7  mov     dword ptr [rsp+0E0h+var_B8], edx
0x1401ab6ab  mov     dword ptr [rsp+0E0h+var_C0], r11d
0x1401ab6b0  mov     r9, r13
0x1401ab6b3  mov     rdx, [r15+0A0h]
0x1401ab6ba  lea     rcx, [r15+30h]
0x1401ab6be  call    RpcRequestUpdates
0x1401ab6c3  mov     [rbp+47h+arg_0], eax
0x1401ab6c6  test    eax, eax
0x1401ab6c8  jz      short loc_1401AB722
0x1401ab6ca  call    cs:__imp_GetCurrentThreadId
0x1401ab6d1  nop     dword ptr [rax+rax+00h]
0x1401ab6d6  mov     edx, esi
0x1401ab6d8  mov     ecx, [rbp+47h+arg_0]
0x1401ab6db  cmp     ecx, 4D5h
0x1401ab6e1  setz    dl
0x1401ab6e4  mov     [rsp+0E0h+var_A8], rsi
0x1401ab6e9  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1401ab6ed  mov     dword ptr [rsp+0E0h+var_C0], 940h
0x1401ab6f5  lea     rbx, aAsyncrpchandle_17; "AsyncRpcHandler::RequestUpdates"
0x1401ab6fc  mov     r9, rbx
0x1401ab6ff  call    LogTranslatedRemoteError
0x1401ab704  mov     r14, rax
0x1401ab707  mov     dword ptr [r12], 2
0x1401ab70f  mov     rcx, r15; this
0x1401ab712  call    ?Release@RefCountObject@@QEAAJXZ; RefCountObject::Release(void)
0x1401ab717  test    r14, r14
0x1401ab71a  jnz     loc_1401AB7AB
0x1401ab720  jmp     short loc_1401AB729
0x1401ab722  lea     rbx, aAsyncrpchandle_17; "AsyncRpcHandler::RequestUpdates"
0x1401ab729  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ab730  test    rax, rax
0x1401ab733  jz      short loc_1401AB796
0x1401ab735  cmp     [rax+40h], esi
0x1401ab738  jz      short loc_1401AB796
0x1401ab73a  cmp     dword ptr [rax+38h], 5
0x1401ab73e  jl      short loc_1401AB796
0x1401ab740  lea     rax, aAsyncrpchandle_14; "AsyncRpcHandler::RequestUpdates"
0x1401ab747  mov     [rbp+47h+var_50], rax
0x1401ab74b  mov     [rbp+47h+var_48], 952h
0x1401ab752  mov     [rbp+47h+var_44], 5
0x1401ab759  lea     rax, aDown; "DOWN"
0x1401ab760  mov     [rbp+47h+var_40], rax
0x1401ab764  mov     [rbp+47h+var_60], r15
0x1401ab768  mov     r8, [r15+20h]
0x1401ab76c  add     r8, 20h ; ' '
0x1401ab770  lea     rax, [rbp+47h+var_60]
0x1401ab774  mov     [rsp+0E0h+var_B0], rax
0x1401ab779  mov     [rsp+0E0h+var_B8], r12
0x1401ab77e  lea     rax, [r15+128h]
0x1401ab785  mov     [rsp+0E0h+var_C0], rax
0x1401ab78a  mov     r9, r13
0x1401ab78d  lea     rcx, [rbp+47h+var_50]
0x1401ab791  call    ??$DbgPrint@GU_GUID@@U1@W4RequestType@AsyncRpcHandler@@W4RequestState@ICancelContext@@_K@dbgobj@@QEAA_KPEBGAEBU_GUID@@1AEBW4RequestType@AsyncRpcHandler@@AEBW4RequestState@ICancelContext@@AEB_K@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID,AsyncRpcHandler::RequestType,ICancelContext::RequestState,unsigned __int64>(ushort const *,_GUID const &,_GUID const &,AsyncRpcHandler::RequestType const &,ICancelContext::RequestState const &,unsigned __int64 const &)
0x1401ab796  call    ?ThreadCounterAdd@TaskPool@@SAPEAJXZ; TaskPool::ThreadCounterAdd(void)
0x1401ab79b  mov     [r15+178h], rax
0x1401ab7a2  jmp     short loc_1401AB819
0x1401ab7a4  lea     rbx, aAsyncrpchandle_17; "AsyncRpcHandler::RequestUpdates"
0x1401ab7ab  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401ab7b2  test    rax, rax
0x1401ab7b5  jz      short loc_1401AB819
0x1401ab7b7  cmp     [rax+40h], esi
0x1401ab7ba  jz      short loc_1401AB819
0x1401ab7bc  cmp     dword ptr [rax+38h], 2
0x1401ab7c0  jl      short loc_1401AB819
0x1401ab7c2  lea     rax, aAsyncrpchandle_14; "AsyncRpcHandler::RequestUpdates"
0x1401ab7c9  mov     [rbp+47h+var_50], rax
0x1401ab7cd  mov     [rbp+47h+var_48], 947h
0x1401ab7d4  mov     [rbp+47h+var_44], 2
0x1401ab7db  lea     rax, aDown; "DOWN"
0x1401ab7e2  mov     [rbp+47h+var_40], rax
0x1401ab7e6  mov     r8, [r15+20h]
0x1401ab7ea  add     r8, 20h ; ' '
0x1401ab7ee  lea     rax, [r15+128h]
0x1401ab7f5  mov     [rsp+0E0h+var_A8], r14
0x1401ab7fa  lea     rcx, [rbp+47h+arg_0]
0x1401ab7fe  mov     [rsp+0E0h+var_B0], rcx
0x1401ab803  mov     [rsp+0E0h+var_B8], r12
0x1401ab808  mov     [rsp+0E0h+var_C0], rax
0x1401ab80d  mov     r9, r13
0x1401ab810  lea     rcx, [rbp+47h+var_50]
0x1401ab814  call    ??$DbgPrint@GU_GUID@@U1@W4RequestType@AsyncRpcHandler@@W4RequestState@ICancelContext@@JVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1AEBW4RequestType@AsyncRpcHandler@@AEBW4RequestState@ICancelContext@@AEBJAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID,AsyncRpcHandler::RequestType,ICancelContext::RequestState,long,FrsStatus>(ushort const *,_GUID const &,_GUID const &,AsyncRpcHandler::RequestType const &,ICancelContext::RequestState const &,long const &,FrsStatus const &)
0x1401ab819  test    r14, r14
0x1401ab81c  jz      short loc_1401AB85F
0x1401ab81e  call    cs:__imp_GetCurrentThreadId
0x1401ab825  nop     dword ptr [rax+rax+00h]
0x1401ab82a  mov     [rsp+0E0h+var_A0], r14
0x1401ab82f  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1401ab833  mov     dword ptr [rsp+0E0h+var_B0], 95Fh
0x1401ab83b  mov     [rsp+0E0h+var_B8], rbx
0x1401ab840  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401ab847  mov     [rsp+0E0h+var_C0], rax
0x1401ab84c  mov     r9d, [r14]
0x1401ab84f  mov     r8d, [r14+8]
0x1401ab853  mov     edx, [r14+4]
0x1401ab857  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401ab85c  mov     rsi, rax
0x1401ab85f  lea     rcx, [rbp+47h+var_58]; this
0x1401ab863  call    ??1ScopedCrewLock@@QEAA@XZ; ScopedCrewLock::~ScopedCrewLock(void)
0x1401ab868  nop
0x1401ab869  lea     rcx, [rbp+47h+var_68]
0x1401ab86d  call    ??1?$scoped_any@PEAU_FRS_VERSION_VECTOR@@Uclose_delete@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_VERSION_VECTOR *,close_delete,null_t,0>::~scoped_any<_FRS_VERSION_VECTOR *,close_delete,null_t,0>(void)
0x1401ab872  mov     rax, rsi
0x1401ab875  mov     rbx, [rsp+0E0h+arg_8]
0x1401ab87d  add     rsp, 0B0h
0x1401ab884  pop     r15
0x1401ab886  pop     r14
0x1401ab888  pop     r13
0x1401ab88a  pop     r12
0x1401ab88c  pop     rdi
0x1401ab88d  pop     rsi
0x1401ab88e  pop     rbp
0x1401ab88f  retn
```
