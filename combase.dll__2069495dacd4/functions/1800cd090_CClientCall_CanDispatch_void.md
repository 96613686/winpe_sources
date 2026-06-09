# CClientCall::CanDispatch(void)

- ea: `0x1800cd090`
- end: `0x1800cd2b5`
- name: `?CanDispatch@CClientCall@@UEAAJXZ`
- size: `549`
- prototype: `__int64 __fastcall(CClientCall *this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006250`
- `0x18000712c`
- `0x1800188a0`
- `0x180019100`
- `0x1800865f4`
- `0x1800cd090`

## import_xrefs

- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x1800cd19e`
- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x1800cd19e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd1c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd1c5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800cd18e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800cd18e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd0a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd0a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cd15a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cd16c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cd15a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cd16c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cd163`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cd163`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cd2a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cd2a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800cd0f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800cd0f2`

## string_xrefs

- `0x1800cd0b1`: `onecore\com\combase\dcomrem\call.cxx`
- `0x1800cd1ed`: `onecore\com\combase\dcomrem\call.cxx`

## pseudocode

```c
__int64 __fastcall CClientCall::CanDispatch(CClientCall *this)
{
  const char *v2; // r9
  _BYTE *v3; // r15
  int v4; // ebp
  void *v5; // rsi
  tagSOleTlsData *ReservedForOle; // rax
  void **p_hThread; // r12
  void *hThread; // rax
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v11; // rax
  _DWORD *v12; // rdi
  int v13; // ebx
  __int64 dwOptions; // [rsp+30h] [rbp-38h]
  COleTls Tls; // [rsp+70h] [rbp+8h] BYREF

  GetCurrentThreadId();
  COleStaticMutexSem::Request(&gCallLock, "onecore\\com\\combase\\dcomrem\\call.cxx", 0xA20u, v2);
  v3 = this->gap2A0;
  if ( (this->gap2A0[0] & 2) != 0 && !this->m_ulCancelTimeout )
  {
    v4 = -2147418110;
    goto LABEL_20;
  }
  v5 = 0;
  this->m_dwStartCount = GetTickCount64();
  if ( (this->gap8[12] & 0x20) != 0 )
  {
    v4 = 0;
LABEL_19:
    LODWORD(Tls._pData) = *(_DWORD *)v3;
    *(_DWORD *)v3 = LODWORD(Tls._pData) | 0x10000;
    CPackagedComCatalog::EntryLookup::RankingType<CPackagedComCatalog::EffectiveClsctxRanking>::DestroyOptionalRanking((Windows::Foundation::Collections::Internal::NaiveSplitView<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0> >::Chunk *)&v3[**(int **)this->gap8 - 664]);
    *((_QWORD *)&this->ObjectLibrary::Details::AddTypeIdentityLayersBuilder<CClientCall,ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<65>,CClientCall,ObjectLibrary::ForwardedBases<CMessageCall> >,ObjectLibrary::ForwardedBases<CMessageCall> >::AddTypeIdLayerHelper<ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<65>,CClientCall,ObjectLibrary::ForwardedBases<CMessageCall> >,ObjectLibrary::PolymorphicType<ObjectLibrary::OneOf<CAsyncCall,CClientCall>,CMessageCall,ObjectLibrary::AddAllocation<ObjectLibrary::AllocationOptions<PrivMemAllocator,368,ObjectLibrary::Details::Nil>,CMessageCall,ObjectLibrary::AddComReferenceCounting<ObjectLibrary::ComReferenceCountingOptions<4>,CMessageCall,ObjectLibrary::Details::Nil> > > >
    + 85) = v5;
    goto LABEL_20;
  }
  ReservedForOle = (tagSOleTlsData *)NtCurrentTeb()->ReservedForOle;
  Tls._pData = ReservedForOle;
  if ( ReservedForOle )
  {
    v4 = 0;
  }
  else
  {
    v4 = COleTls::TLSAllocData(&Tls);
    if ( v4 < 0 )
      goto LABEL_20;
    ReservedForOle = Tls._pData;
  }
  p_hThread = &ReservedForOle->hThread;
  hThread = ReservedForOle->hThread;
  if ( hThread )
  {
    v5 = hThread;
    goto LABEL_19;
  }
  CurrentProcess = GetCurrentProcess();
  CurrentThread = GetCurrentThread();
  v11 = GetCurrentProcess();
  if ( DuplicateHandle(v11, CurrentThread, CurrentProcess, p_hThread, 0, 0, 2u) )
  {
    v5 = *p_hThread;
    RpcMgmtSetCancelTimeout(0);
    goto LABEL_19;
  }
  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
    || gfEnableTracing && (WPP_GLOBAL_Control->ReserveSpace[28] & 1) != 0 )
  {
    LODWORD(dwOptions) = GetLastError();
    ComTraceMessage(
      -1,
      "onecore\\com\\combase\\dcomrem\\call.cxx",
      "CClientCall::CanDispatch",
      2637,
      ERRORS,
      L"DuplicateHandle failed: %!WINERROR!",
      dwOptions);
  }
  v4 = -2147417856;
LABEL_20:
  if ( !--gCallLock._cLocks && gCallLock._lockOrder != Highest )
  {
    v12 = NtCurrentTeb()->ReservedForOle;
    if ( v12 )
    {
      v13 = 1 << gCallLock._lockOrder;
      if ( ((1 << gCallLock._lockOrder) & v12[144]) == 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs((unsigned __int8)gCallLock._lockOrder);
      v12[144] &= ~v13;
    }
  }
  LeaveCriticalSection(&gCallLock._cs);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800cd090  push    rbx
0x1800cd092  push    rbp
0x1800cd093  push    rdi
0x1800cd094  sub     rsp, 50h
0x1800cd098  mov     [rsp+68h+var_20], r14
0x1800cd09d  mov     r14, this
0x1800cd0a0  mov     [rsp+68h+var_28], r15
0x1800cd0a5  call    cs:__imp_GetCurrentThreadId
0x1800cd0ab  mov     r8d, 0A20h; dwLine
0x1800cd0b1  lea     rdx, pszFile; "onecore\\com\\combase\\dcomrem\\call.cx"...
0x1800cd0b8  lea     this, ?gCallLock@@3VCOleStaticMutexSem@@A; this
0x1800cd0bf  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x1800cd0c4  lea     r15, [r14+2A0h]
0x1800cd0cb  test    byte ptr [r15], 2
0x1800cd0cf  jz      short loc_1800CD0E5
0x1800cd0d1  cmp     dword ptr [r14+0E0h], 0
0x1800cd0d9  jnz     short loc_1800CD0E5
0x1800cd0db  mov     ebp, 80010002h
0x1800cd0e0  jmp     loc_1800CD24A
0x1800cd0e5  mov     [rsp+68h+arg_8], rsi
0x1800cd0ea  mov     [rsp+68h+arg_10], r12
0x1800cd0f2  call    cs:__imp_GetTickCount64
0x1800cd0f8  xor     esi, esi
0x1800cd0fa  mov     [r14+170h], rax
0x1800cd101  test    byte ptr [r14+14h], 20h
0x1800cd106  jz      short loc_1800CD10F
0x1800cd108  mov     ebp, esi
0x1800cd10a  jmp     loc_1800CD207
0x1800cd10f  mov     rax, gs:30h
0x1800cd118  mov     rax, [rax+1758h]
0x1800cd11f  mov     [rsp+68h+Tls._pData], rax
0x1800cd124  test    rax, rax
0x1800cd127  jz      short loc_1800CD12D
0x1800cd129  mov     ebp, esi
0x1800cd12b  jmp     short loc_1800CD146
0x1800cd12d  lea     this, [rsp+68h+Tls]; this
0x1800cd132  call    ?TLSAllocData@COleTls@@QEAAJXZ; COleTls::TLSAllocData(void)
0x1800cd137  mov     ebp, eax
0x1800cd139  test    eax, eax
0x1800cd13b  js      loc_1800CD23D
0x1800cd141  mov     rax, [rsp+68h+Tls._pData]
0x1800cd146  lea     r12, [rax+0E0h]
0x1800cd14d  mov     rax, [r12]
0x1800cd151  test    rax, rax
0x1800cd154  jnz     loc_1800CD204
0x1800cd15a  call    cs:__imp_GetCurrentProcess
0x1800cd160  mov     rdi, rax
0x1800cd163  call    cs:__imp_GetCurrentThread
0x1800cd169  mov     rbx, rax
0x1800cd16c  call    cs:__imp_GetCurrentProcess
0x1800cd172  mov     [rsp+68h+dwOptions], 2; dwOptions
0x1800cd17a  mov     r9, r12; lpTargetHandle
0x1800cd17d  mov     this, rax; hSourceProcessHandle
0x1800cd180  mov     [rsp+68h+bInheritHandle], esi; bInheritHandle
0x1800cd184  mov     r8, rdi; hTargetProcessHandle
0x1800cd187  mov     [rsp+68h+dwDesiredAccess], esi; dwDesiredAccess
0x1800cd18b  mov     rdx, rbx; hSourceHandle
0x1800cd18e  call    cs:__imp_DuplicateHandle
0x1800cd194  test    eax, eax
0x1800cd196  jz      short loc_1800CD1A6
0x1800cd198  mov     rsi, [r12]
0x1800cd19c  xor     ecx, ecx; Timeout
0x1800cd19e  call    cs:__imp_RpcMgmtSetCancelTimeout
0x1800cd1a4  jmp     short loc_1800CD207
0x1800cd1a6  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1800cd1ac  test    eax, eax
0x1800cd1ae  jnz     short loc_1800CD1C5
0x1800cd1b0  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x1800cd1b6  jz      short loc_1800CD1FD
0x1800cd1b8  mov     rax, cs:WPP_GLOBAL_Control
0x1800cd1bf  test    byte ptr [rax+1Ch], 1
0x1800cd1c3  jz      short loc_1800CD1FD
0x1800cd1c5  call    cs:__imp_GetLastError
0x1800cd1cb  mov     [rsp+68h+dwOptions], eax
0x1800cd1cf  mov     r9d, 0A4Dh; line
0x1800cd1d5  lea     r8, aCclientcallCan; "CClientCall::CanDispatch"
0x1800cd1dc  mov     ecx, 0FFFFFFFFh; hr
0x1800cd1e1  lea     rax, aDuplicatehandl; "DuplicateHandle failed: %!WINERROR!"
0x1800cd1e8  mov     qword ptr [rsp+68h+bInheritHandle], rax; format
0x1800cd1ed  lea     rdx, pszFile; "onecore\\com\\combase\\dcomrem\\call.cx"...
0x1800cd1f4  mov     [rsp+68h+dwDesiredAccess], esi; level
0x1800cd1f8  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800cd1fd  mov     ebp, 80010100h
0x1800cd202  jmp     short loc_1800CD23D
0x1800cd204  mov     rsi, rax
0x1800cd207  mov     eax, [r15]
0x1800cd20a  lea     rdx, [rsp+68h+Tls]
0x1800cd20f  mov     dword ptr [rsp+68h+Tls._pData], eax
0x1800cd213  mov     r8, r15
0x1800cd216  bts     eax, 10h
0x1800cd21a  mov     [r15], eax
0x1800cd21d  mov     rax, [r15-298h]
0x1800cd224  movsxd  this, dword ptr [rax]
0x1800cd227  add     this, 0FFFFFFFFFFFFFD68h
0x1800cd22e  add     this, r15; this
0x1800cd231  call    ?DestroyOptionalRanking@?$RankingType@VEffectiveClsctxRanking@CPackagedComCatalog@@@EntryLookup@CPackagedComCatalog@@UEBAXAEAUOptionalRankingGeneric@23@@Z; CPackagedComCatalog::EntryLookup::RankingType<CPackagedComCatalog::EffectiveClsctxRanking>::DestroyOptionalRanking(CPackagedComCatalog::EntryLookup::OptionalRankingGeneric &)
0x1800cd236  mov     [r14+2A8h], rsi
0x1800cd23d  mov     rsi, [rsp+68h+arg_8]
0x1800cd242  mov     r12, [rsp+68h+arg_10]
0x1800cd24a  add     cs:?gCallLock@@3VCOleStaticMutexSem@@A._cLocks, 0FFFFFFFFh; COleStaticMutexSem gCallLock ...
0x1800cd251  mov     r15, [rsp+68h+var_28]
0x1800cd256  mov     r14, [rsp+68h+var_20]
0x1800cd25b  jnz     short loc_1800CD29E
0x1800cd25d  cmp     cs:?gCallLock@@3VCOleStaticMutexSem@@A._lockOrder, 13h; COleStaticMutexSem gCallLock ...
0x1800cd264  jz      short loc_1800CD29E
0x1800cd266  mov     rax, gs:30h
0x1800cd26f  mov     rdi, [rax+1758h]
0x1800cd276  test    rdi, rdi
0x1800cd279  jz      short loc_1800CD29E
0x1800cd27b  movzx   ecx, cs:?gCallLock@@3VCOleStaticMutexSem@@A._lockOrder; COleStaticMutexSem gCallLock ...
0x1800cd282  mov     ebx, 1
0x1800cd287  shl     ebx, cl
0x1800cd289  test    [rdi+240h], ebx
0x1800cd28f  jnz     short loc_1800CD296
0x1800cd291  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "lockFlag & _locksHeldByThread")
0x1800cd296  not     ebx
0x1800cd298  and     [rdi+240h], ebx
0x1800cd29e  lea     this, ?gCallLock@@3VCOleStaticMutexSem@@A._cs; lpCriticalSection
0x1800cd2a5  call    cs:__imp_LeaveCriticalSection
0x1800cd2ab  mov     eax, ebp
0x1800cd2ad  add     rsp, 50h
0x1800cd2b1  pop     rdi
0x1800cd2b2  pop     rbp
0x1800cd2b3  pop     rbx
0x1800cd2b4  retn
```
