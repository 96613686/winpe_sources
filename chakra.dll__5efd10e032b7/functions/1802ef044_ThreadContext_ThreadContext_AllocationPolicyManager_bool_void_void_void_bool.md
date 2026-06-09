# ThreadContext::ThreadContext(AllocationPolicyManager *,bool (*)(void (*)(void *),void *),bool)

- ea: `0x1802ef044`
- end: `0x1802ef8f5`
- name: `??0ThreadContext@@QEAA@PEAVAllocationPolicyManager@@P6A_NP6AXPEAX@Z1@Z_N@Z`
- size: `2225`
- prototype: `ThreadContext *__fastcall(ThreadContext *__hidden this, struct AllocationPolicyManager *, bool (*)(void (*)(void *), void *), bool)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802eeaa0`
- `0x1802f0e5c`

## callees

- `0x180069aa0`
- `0x180141950`
- `0x1802ef8fc`
- `0x1802ef990`
- `0x1802ef9e4`
- `0x1802efa34`
- `0x1802efa88`
- `0x1802efaf0`
- `0x1802efb38`
- `0x1802efb90`
- `0x1802efbec`
- `0x1802f04b8`
- `0x1802f079c`
- `0x1802f07e8`
- `0x1802f0868`
- `0x1802f08a8`
- `0x1802f08f8`
- `0x1802f0974`
- `0x1802f09ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1802ef520`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1802ef6aa`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1802ef520`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1802ef6aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802ef8d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802ef8d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802ef8b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802ef8b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802ef299`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802ef2c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802ef2e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802ef299`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802ef2c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802ef2e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802ef0f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802ef0f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
ThreadContext *__fastcall ThreadContext::ThreadContext(
        ThreadContext *this,
        struct AllocationPolicyManager *a2,
        bool (*a3)(void (*)(void *), void *),
        bool a4)
{
  HANDLE CurrentProcess; // rax
  HANDLE v6; // rax
  int v7; // r8d
  HANDLE v8; // rax
  __int64 v9; // r8
  char *v10; // rax
  ThreadContext *v11; // rcx
  char *(*v13)(Memory::ArenaAllocator *__hidden, unsigned __int64); // [rsp+60h] [rbp-68h] BYREF
  int v14; // [rsp+68h] [rbp-60h]

  *((_DWORD *)this + 2) = 0;
  Js::AgentOfBuffer::AgentOfBuffer((ThreadContext *)((char *)this + 120));
  ThreadContextInfo::ThreadContextInfo((ThreadContext *)((char *)this + 16));
  *(_QWORD *)this = &ThreadContext::`vftable'{for `Memory::DefaultRecyclerCollectionWrapper'};
  *((_QWORD *)this + 2) = &ThreadContext::`vftable'{for `ThreadContextInfo'};
  *((_QWORD *)this + 24) = 0;
  *((_BYTE *)this + 200) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_BYTE *)this + 264) = 0;
  *((_DWORD *)this + 67) = 0;
  *((_DWORD *)this + 68) = GetCurrentThreadId();
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_WORD *)this + 148) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_WORD *)this + 156) = 0;
  *((_BYTE *)this + 314) = 0;
  *((_QWORD *)this + 40) = a2;
  *((_QWORD *)this + 41) = a3;
  *((_BYTE *)this + 336) = 0;
  Memory::PreReservedVirtualAllocWrapper::PreReservedVirtualAllocWrapper((ThreadContext *)((char *)this + 344));
  *((_DWORD *)this + 226) = 0;
  Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::BackgroundPageQueue::BackgroundPageQueue((char *)this + 912);
  Memory::IdleDecommitPageAllocator::IdleDecommitPageAllocator(
    (_DWORD)this + 976,
    (_DWORD)a2,
    0,
    (unsigned int)&Js::Configuration::Global);
  *((_QWORD *)this + 162) = 0;
  *((_QWORD *)this + 163) = (char *)this + 1304;
  *((_QWORD *)this + 164) = &Memory::HeapAllocator::Instance;
  *((_QWORD *)this + 165) = 0;
  *((_QWORD *)this + 166) = 0;
  *((_QWORD *)this + 168) = 0;
  *((_QWORD *)this + 169) = 0;
  *((_QWORD *)this + 298) = Js::Throw::OutOfMemory;
  *((_QWORD *)this + 299) = JsUtil::ExternalApi::RecoverUnusedMemory;
  *((_QWORD *)this + 300) = 0;
  *((_QWORD *)this + 301) = 0;
  *((_QWORD *)this + 302) = 0;
  *((_QWORD *)this + 303) = (char *)this + 976;
  *((_QWORD *)this + 304) = 0;
  *((_BYTE *)this + 2440) = 0;
  *((_QWORD *)this + 306) = 3;
  *((_QWORD *)this + 307) = 0;
  *((_DWORD *)this + 616) = 0;
  *((_QWORD *)this + 309) = 0;
  *((_QWORD *)this + 310) = 0;
  *((_QWORD *)this + 312) = 0;
  *((_QWORD *)this + 313) = 0;
  *((_DWORD *)this + 628) = 0;
  *(_QWORD *)((char *)this + 2516) = 2048;
  *((_QWORD *)this + 316) = (char *)this + 2528;
  *((_QWORD *)this + 317) = 0;
  CurrentProcess = GetCurrentProcess();
  Memory::CustomHeap::CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>::CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>(
    (_DWORD)this + 2552,
    (_DWORD)a2,
    0,
    0,
    (__int64)CurrentProcess);
  v6 = GetCurrentProcess();
  LOBYTE(v7) = 1;
  Memory::CustomHeap::CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>::CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>(
    (_DWORD)this + 3136,
    (_DWORD)a2,
    v7,
    (_DWORD)this + 344,
    (__int64)v6);
  v8 = GetCurrentProcess();
  JITThunkEmitter<Memory::VirtualAllocWrapper>::JITThunkEmitter<Memory::VirtualAllocWrapper>(
    (char *)this + 3720,
    (char *)this + 16,
    v9,
    v8);
  *((_QWORD *)this + 875) = 0;
  *((_QWORD *)this + 876) = 0;
  *((_QWORD *)this + 877) = 0;
  *((_BYTE *)this + 7024) = 0;
  *((_QWORD *)this + 879) = 0;
  *((_QWORD *)this + 880) = 0;
  *((_QWORD *)this + 881) = 0;
  *((_QWORD *)this + 882) = 0;
  *((_QWORD *)this + 883) = 0x3FF0000000000000LL;
  *((_QWORD *)this + 884) = 0;
  *((_QWORD *)this + 885) = 0;
  *((_WORD *)this + 3544) = 1;
  *((_BYTE *)this + 7090) = 1;
  *((_DWORD *)this + 1774) = 0;
  *((_DWORD *)this + 1780) = 0;
  *((_QWORD *)this + 891) = Js::Throw::OutOfMemory;
  *((_QWORD *)this + 892) = JsUtil::ExternalApi::RecoverUnusedMemory;
  *((_QWORD *)this + 893) = 0;
  *((_QWORD *)this + 894) = 0;
  *((_QWORD *)this + 895) = 0;
  *((_QWORD *)this + 896) = (char *)this + 976;
  *((_QWORD *)this + 897) = 0;
  *((_BYTE *)this + 7184) = 0;
  *((_QWORD *)this + 899) = 3;
  *((_QWORD *)this + 900) = 0;
  *((_DWORD *)this + 1802) = 0;
  *((_QWORD *)this + 902) = 0;
  *((_QWORD *)this + 903) = Js::Throw::OutOfMemory;
  *((_QWORD *)this + 904) = JsUtil::ExternalApi::RecoverUnusedMemory;
  *((_QWORD *)this + 905) = 0;
  *((_QWORD *)this + 906) = 0;
  *((_QWORD *)this + 907) = 0;
  *((_QWORD *)this + 908) = (char *)this + 976;
  *((_QWORD *)this + 909) = 0;
  *((_BYTE *)this + 7280) = 0;
  *((_QWORD *)this + 911) = 3;
  *((_QWORD *)this + 912) = 0;
  *((_DWORD *)this + 1826) = 0;
  *((_QWORD *)this + 914) = 0;
  *((_QWORD *)this + 915) = Js::Throw::OutOfMemory;
  *((_QWORD *)this + 916) = JsUtil::ExternalApi::RecoverUnusedMemory;
  *((_QWORD *)this + 917) = 0;
  *((_QWORD *)this + 918) = 0;
  *((_QWORD *)this + 919) = 0;
  *((_QWORD *)this + 920) = (char *)this + 976;
  *((_QWORD *)this + 921) = 0;
  *((_BYTE *)this + 7376) = 0;
  *((_QWORD *)this + 923) = 3;
  *((_QWORD *)this + 924) = 0;
  *((_DWORD *)this + 1850) = 0;
  *((_QWORD *)this + 926) = 0;
  *((_QWORD *)this + 927) = (char *)this + 7416;
  *((_QWORD *)this + 928) = (char *)this + 7416;
  JsUtil::BaseDictionary<int,SList<Js::InlineCache *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::BaseDictionary<int,SList<Js::InlineCache *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>(
    (char *)this + 7432,
    (char *)this + 7128,
    521);
  JsUtil::BaseDictionary<int,SList<Js::InlineCache *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::BaseDictionary<int,SList<Js::InlineCache *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>(
    (char *)this + 7480,
    (char *)this + 7128,
    293);
  *((_QWORD *)this + 941) = 0;
  JsUtil::BaseDictionary<void *,Js::IsInstInlineCache *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::BaseDictionary<void *,Js::IsInstInlineCache *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>(
    (char *)this + 7536,
    (char *)this + 7224);
  *((_QWORD *)this + 948) = 0;
  *((_QWORD *)this + 949) = 0;
  *((_QWORD *)this + 950) = 1;
  *((_DWORD *)this + 1902) = 0;
  Js::ThreadCacheRegistry<Js::PrototypeChainCache<Js::OnlyWritablePropertyCache>>::ThreadCacheRegistry<Js::PrototypeChainCache<Js::OnlyWritablePropertyCache>>(
    (char *)this + 7616,
    (char *)this + 976);
  Js::ThreadCacheRegistry<Js::PrototypeChainCache<Js::OnlyWritablePropertyCache>>::ThreadCacheRegistry<Js::PrototypeChainCache<Js::OnlyWritablePropertyCache>>(
    (char *)this + 7728,
    (char *)this + 976);
  *((_QWORD *)this + 980) = (char *)this + 7840;
  *((_QWORD *)this + 981) = (char *)this + 7840;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 7856), 0);
  *((_BYTE *)this + 7896) = 0;
  *((_BYTE *)this + 7897) = byte_18073F2DA;
  *((_BYTE *)this + 7898) = byte_18073F242;
  *((_BYTE *)this + 7899) = 1;
  *((_QWORD *)this + 988) = 0;
  *((_DWORD *)this + 1978) = 0;
  *((_QWORD *)this + 991) = 0;
  *((_BYTE *)this + 7936) = 0;
  *((_QWORD *)this + 990) = &Js::DelayLoadWinRtString::`vftable';
  *((_QWORD *)this + 993) = 0;
  *((_QWORD *)this + 994) = 0;
  *((_QWORD *)this + 995) = 0;
  *((_QWORD *)this + 996) = 0;
  *((_QWORD *)this + 997) = 0;
  *((_QWORD *)this + 998) = 0;
  *((_QWORD *)this + 1000) = 0;
  *((_BYTE *)this + 8008) = 0;
  *((_QWORD *)this + 999) = &Js::DelayLoadWinRtError::`vftable';
  *((_QWORD *)this + 1002) = 0;
  *((_QWORD *)this + 1003) = 0;
  *((_QWORD *)this + 1005) = 0;
  *((_BYTE *)this + 8048) = 0;
  *((_QWORD *)this + 1004) = &Js::DelayLoadWinRtTypeResolution::`vftable';
  *((_QWORD *)this + 1007) = 0;
  *((_QWORD *)this + 1010) = 0;
  *((_BYTE *)this + 8088) = 0;
  *((_QWORD *)this + 1009) = &Js::DelayLoadWinRtRoParameterizedIID::`vftable';
  *((_QWORD *)this + 1012) = 0;
  *((_QWORD *)this + 1014) = 0;
  *((_BYTE *)this + 8120) = 0;
  *((_QWORD *)this + 1013) = &Js::DelayLoadWinRtFoundation::`vftable';
  *((_QWORD *)this + 1016) = 0;
  *((_QWORD *)this + 1017) = 0;
  *((_QWORD *)this + 1018) = 0;
  *((_DWORD *)this + 2038) = 0;
  *((_QWORD *)this + 1020) = 0;
  *((_QWORD *)this + 1021) = 0;
  *((_QWORD *)this + 1023) = 0;
  *((_QWORD *)this + 1024) = 0;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 8208), 0);
  *((_DWORD *)this + 3296) = 0;
  JsUtil::BaseDictionary<Js::DynamicType const *,void *,Memory::HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::BaseDictionary<Js::DynamicType const *,void *,Memory::HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>((char *)this + 13200);
  *((_QWORD *)this + 1658) = (char *)this + 13248;
  *((_QWORD *)this + 1659) = 0;
  *((_QWORD *)this + 1661) = 0;
  *((_BYTE *)this + 13296) = 0;
  *((_QWORD *)this + 1660) = &UCrtC99MathApis::`vftable';
  *((_QWORD *)this + 1663) = 0;
  *((_QWORD *)this + 1664) = 0;
  *((_QWORD *)this + 1665) = 0;
  *((_QWORD *)this + 1666) = 0;
  *((_QWORD *)this + 1667) = 0;
  *((_QWORD *)this + 1668) = 0;
  *((_QWORD *)this + 1669) = 0;
  *((_QWORD *)this + 1670) = 0;
  *((_BYTE *)this + 13368) = 0;
  ThreadConfiguration::ThreadConfiguration((ThreadContext *)((char *)this + 13369), a4);
  *((_DWORD *)this + 3354) = 0;
  *((_BYTE *)this + 13420) = 0;
  *((_QWORD *)this + 1680) = 0;
  DirectCallTelemetry::DirectCallTelemetry((ThreadContext *)((char *)this + 13448), this);
  *((_QWORD *)this + 1690) = 0;
  *((_QWORD *)this + 1691) = 0;
  *((_DWORD *)this + 3384) = 0;
  *((_DWORD *)this + 3385) = -1;
  *((_WORD *)this + 6772) = 256;
  *((_QWORD *)this + 1694) = 0;
  *((_QWORD *)this + 1695) = 0;
  *((_QWORD *)this + 1696) = 0;
  *((_QWORD *)this + 1697) = (char *)this + 2384;
  *((_QWORD *)this + 1698) = 0;
  *((_DWORD *)this + 3398) = 0;
  *((_DWORD *)this + 3400) = 0;
  *((_DWORD *)this + 3401) = 75;
  *((_QWORD *)this + 1701) = &ThreadContext::ThreadContextRecyclerTelemetryHostInterface::`vftable';
  *((_QWORD *)this + 1702) = this;
  *((_QWORD *)this + 167) = JsUtil::List<IProjectionContext *,Memory::ArenaAllocator,0,Js::CopyRemovePolicy,DefaultComparer>::New((char *)this + 2384);
  v10 = Memory::ArenaAllocator::Alloc((ThreadContext *)((char *)this + 2384), 0x30u);
  *((_QWORD *)v10 + 3) = (char *)this + 2384;
  *(_QWORD *)v10 = &JsUtil::List<Js::ByteCodeWriter::JumpInfo,Memory::ArenaAllocator,0,Js::CopyRemovePolicy,DefaultComparer>::`vftable';
  *((_DWORD *)v10 + 9) = 4;
  *((_QWORD *)v10 + 1) = 0;
  *((_DWORD *)v10 + 4) = 0;
  *((_DWORD *)v10 + 8) = 0;
  *((_QWORD *)this + 1022) = v10;
  *((_QWORD *)this + 311) = 0;
  *((_BYTE *)this + 8201) = 0;
  Entropy::Initialize((ThreadContext *)((char *)this + 8160));
  v13 = Memory::ArenaAllocator::AllocZero;
  v14 = 0;
  *((_QWORD *)this + 318) = Memory::AllocateArray<Memory::ArenaAllocator,void *,0>((char *)this + 2384, &v13, 49);
  *((_OWORD *)this + 828) = 0;
  v13 = (char *(*)(Memory::ArenaAllocator *__hidden, unsigned __int64))&ThreadContext::s_csThreadContext;
  EnterCriticalSection(&ThreadContext::s_csThreadContext);
  JsUtil::DoublyLinkedListElement<ThreadContext,Memory::ArenaAllocator>::LinkToBeginning<ThreadContext>(this);
  ThreadContext::InitAvailableCommit(v11);
  LeaveCriticalSection(&ThreadContext::s_csThreadContext);
  return this;
}

```

## disassembly

```asm
0x1802ef044  mov     rax, rsp
0x1802ef047  mov     [rax+20h], r9b
0x1802ef04b  mov     [rax+18h], r8
0x1802ef04f  mov     [rax+10h], rdx
0x1802ef053  mov     [rax+8], rcx
0x1802ef057  push    rbx
0x1802ef058  push    rbp
0x1802ef059  push    rsi
0x1802ef05a  push    rdi
0x1802ef05b  push    r12
0x1802ef05d  push    r13
0x1802ef05f  push    r14
0x1802ef061  push    r15
0x1802ef063  sub     rsp, 88h
0x1802ef06a  mov     qword ptr [rax-78h], 0FFFFFFFFFFFFFFFEh
0x1802ef072  xor     r13d, r13d
0x1802ef075  mov     r12, rcx
0x1802ef078  mov     [rcx+8], r13d
0x1802ef07c  lea     rcx, [rcx+78h]; this
0x1802ef080  call    ??0AgentOfBuffer@Js@@QEAA@XZ; Js::AgentOfBuffer::AgentOfBuffer(void)
0x1802ef085  lea     r14, [r12+10h]
0x1802ef08a  mov     rcx, r14; this
0x1802ef08d  call    ??0ThreadContextInfo@@QEAA@XZ; ThreadContextInfo::ThreadContextInfo(void)
0x1802ef092  nop
0x1802ef093  lea     rax, ??_7ThreadContext@@6BDefaultRecyclerCollectionWrapper@Memory@@@; const ThreadContext::`vftable'{for `Memory::DefaultRecyclerCollectionWrapper'}
0x1802ef09a  mov     [r12], rax
0x1802ef09e  lea     rax, ??_7ThreadContext@@6BThreadContextInfo@@@; const ThreadContext::`vftable'{for `ThreadContextInfo'}
0x1802ef0a5  mov     [r14], rax
0x1802ef0a8  mov     [r12+0C0h], r13
0x1802ef0b0  mov     [r12+0C8h], r13b
0x1802ef0b8  mov     [r12+0D0h], r13
0x1802ef0c0  mov     [r12+0D8h], r13
0x1802ef0c8  mov     [r12+0E0h], r13
0x1802ef0d0  mov     [r12+0E8h], r13
0x1802ef0d8  mov     [r12+0F0h], r13
0x1802ef0e0  mov     [r12+100h], r13
0x1802ef0e8  mov     [r12+108h], r13b
0x1802ef0f0  mov     [r12+10Ch], r13d
0x1802ef0f8  call    cs:__imp_GetCurrentThreadId
0x1802ef0ff  nop     dword ptr [rax+rax+00h]
0x1802ef104  mov     [r12+110h], eax
0x1802ef10c  mov     [r12+118h], r13
0x1802ef114  mov     [r12+120h], r13
0x1802ef11c  mov     [r12+128h], r13w
0x1802ef125  mov     [r12+130h], r13
0x1802ef12d  mov     [r12+138h], r13w
0x1802ef136  mov     [r12+13Ah], r13b
0x1802ef13e  mov     rsi, [rsp+0C8h+arg_8]
0x1802ef146  mov     [r12+140h], rsi
0x1802ef14e  mov     rax, [rsp+0C8h+arg_10]
0x1802ef156  mov     [r12+148h], rax
0x1802ef15e  mov     [r12+150h], r13b
0x1802ef166  lea     rdi, [r12+158h]
0x1802ef16e  mov     rcx, rdi; this
0x1802ef171  call    ??0PreReservedVirtualAllocWrapper@Memory@@QEAA@XZ; Memory::PreReservedVirtualAllocWrapper::PreReservedVirtualAllocWrapper(void)
0x1802ef176  nop
0x1802ef177  mov     [r12+388h], r13d
0x1802ef17f  lea     rbx, [r12+390h]
0x1802ef187  mov     rcx, rbx
0x1802ef18a  call    ??0BackgroundPageQueue@?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@QEAA@XZ; Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::BackgroundPageQueue::BackgroundPageQueue(void)
0x1802ef18f  nop
0x1802ef190  lea     rbp, [r12+3D0h]
0x1802ef198  mov     [rsp+0C8h+var_80], r13b
0x1802ef19d  mov     [rsp+0C8h+var_88], 20h ; ' '
0x1802ef1a5  mov     [rsp+0C8h+var_90], rbx
0x1802ef1aa  mov     [rsp+0C8h+var_98], r13b
0x1802ef1af  mov     eax, cs:dword_18073F790
0x1802ef1b5  mov     [rsp+0C8h+var_A0], eax
0x1802ef1b9  lea     r9, ?Global@Configuration@Js@@2V12@A; Js::Configuration Js::Configuration::Global
0x1802ef1c0  xor     r8d, r8d
0x1802ef1c3  mov     rdx, rsi
0x1802ef1c6  mov     rcx, rbp
0x1802ef1c9  call    ??0IdleDecommitPageAllocator@Memory@@QEAA@PEAVAllocationPolicyManager@@W4PageAllocatorType@@AEAVConfigFlagsTable@Js@@II_NPEAUBackgroundPageQueue@?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@1@I3@Z; Memory::IdleDecommitPageAllocator::IdleDecommitPageAllocator(AllocationPolicyManager *,PageAllocatorType,Js::ConfigFlagsTable &,uint,uint,bool,Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::BackgroundPageQueue *,uint,bool)
0x1802ef1ce  nop
0x1802ef1cf  mov     [r12+510h], r13
0x1802ef1d7  lea     rax, [r12+518h]
0x1802ef1df  mov     [rax], rax
0x1802ef1e2  lea     rcx, ?Instance@HeapAllocator@Memory@@2U12@A; Memory::HeapAllocator Memory::HeapAllocator::Instance
0x1802ef1e9  mov     [rax+8], rcx
0x1802ef1ed  mov     [r12+528h], r13
0x1802ef1f5  mov     [r12+530h], r13
0x1802ef1fd  mov     [r12+540h], r13
0x1802ef205  mov     [r12+548h], r13
0x1802ef20d  lea     r15, [r12+950h]
0x1802ef215  lea     rax, ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1802ef21c  mov     [r15], rax
0x1802ef21f  lea     rbx, ?RecoverUnusedMemory@ExternalApi@JsUtil@@SAXXZ; JsUtil::ExternalApi::RecoverUnusedMemory(void)
0x1802ef226  mov     [r15+8], rbx
0x1802ef22a  mov     [r15+10h], r13
0x1802ef22e  mov     [r15+18h], r13
0x1802ef232  mov     [r15+20h], r13
0x1802ef236  mov     [r15+28h], rbp
0x1802ef23a  mov     [r15+30h], r13
0x1802ef23e  mov     [r15+38h], r13b
0x1802ef242  mov     r13d, 3
0x1802ef248  mov     [r15+40h], r13
0x1802ef24c  xor     ecx, ecx
0x1802ef24e  mov     [r15+48h], rcx
0x1802ef252  mov     [r15+50h], ecx
0x1802ef256  mov     [r15+58h], rcx
0x1802ef25a  mov     [r12+9B0h], rcx
0x1802ef262  mov     [r12+9C0h], rcx
0x1802ef26a  mov     [r12+9C8h], rcx
0x1802ef272  mov     [r12+9D0h], ecx
0x1802ef27a  mov     qword ptr [r12+9D4h], 800h
0x1802ef286  lea     rax, [r12+9E0h]
0x1802ef28e  mov     [rax], rax
0x1802ef291  mov     [r12+9E8h], rcx
0x1802ef299  call    cs:__imp_GetCurrentProcess
0x1802ef2a0  nop     dword ptr [rax+rax+00h]
0x1802ef2a5  lea     rcx, [r12+9F8h]
0x1802ef2ad  mov     [rsp+0C8h+var_A8], rax
0x1802ef2b2  xor     r9d, r9d
0x1802ef2b5  xor     r8d, r8d
0x1802ef2b8  mov     rdx, rsi
0x1802ef2bb  call    ??0?$CodePageAllocators@VVirtualAllocWrapper@Memory@@VPreReservedVirtualAllocWrapper@2@@CustomHeap@Memory@@QEAA@PEAVAllocationPolicyManager@@_NPEAVPreReservedVirtualAllocWrapper@2@PEAX@Z; Memory::CustomHeap::CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>::CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>(AllocationPolicyManager *,bool,Memory::PreReservedVirtualAllocWrapper *,void *)
0x1802ef2c0  nop
0x1802ef2c1  call    cs:__imp_GetCurrentProcess
0x1802ef2c8  nop     dword ptr [rax+rax+00h]
0x1802ef2cd  lea     rcx, [r12+0C40h]
0x1802ef2d5  mov     [rsp+0C8h+var_A8], rax
0x1802ef2da  mov     r9, rdi
0x1802ef2dd  mov     r8b, 1
0x1802ef2e0  mov     rdx, rsi
0x1802ef2e3  call    ??0?$CodePageAllocators@VVirtualAllocWrapper@Memory@@VPreReservedVirtualAllocWrapper@2@@CustomHeap@Memory@@QEAA@PEAVAllocationPolicyManager@@_NPEAVPreReservedVirtualAllocWrapper@2@PEAX@Z; Memory::CustomHeap::CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>::CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>(AllocationPolicyManager *,bool,Memory::PreReservedVirtualAllocWrapper *,void *)
0x1802ef2e8  nop
0x1802ef2e9  call    cs:__imp_GetCurrentProcess
0x1802ef2f0  nop     dword ptr [rax+rax+00h]
0x1802ef2f5  lea     rcx, [r12+0E88h]
0x1802ef2fd  mov     r9, rax
0x1802ef300  mov     rdx, r14
0x1802ef303  call    ??0?$JITThunkEmitter@VVirtualAllocWrapper@Memory@@@@QEAA@PEAVThreadContextInfo@@PEAVVirtualAllocWrapper@Memory@@PEAX@Z; JITThunkEmitter<Memory::VirtualAllocWrapper>::JITThunkEmitter<Memory::VirtualAllocWrapper>(ThreadContextInfo *,Memory::VirtualAllocWrapper *,void *)
0x1802ef308  nop
0x1802ef309  xor     esi, esi
0x1802ef30b  mov     [r12+1B58h], rsi
0x1802ef313  mov     [r12+1B60h], rsi
0x1802ef31b  mov     [r12+1B68h], rsi
0x1802ef323  mov     [r12+1B70h], sil
0x1802ef32b  mov     [r12+1B78h], rsi
0x1802ef333  mov     [r12+1B80h], rsi
0x1802ef33b  mov     [r12+1B88h], rsi
0x1802ef343  mov     [r12+1B90h], rsi
0x1802ef34b  mov     rax, 3FF0000000000000h
0x1802ef355  mov     [r12+1B98h], rax
0x1802ef35d  mov     [r12+1BA0h], rsi
0x1802ef365  mov     [r12+1BA8h], rsi
0x1802ef36d  mov     word ptr [r12+1BB0h], 1
0x1802ef378  mov     byte ptr [r12+1BB2h], 1
0x1802ef381  mov     [r12+1BB8h], esi
0x1802ef389  mov     [r12+1BD0h], esi
0x1802ef391  lea     rdi, [r12+1BD8h]
0x1802ef399  lea     rcx, ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1802ef3a0  mov     [rdi], rcx
0x1802ef3a3  mov     [rdi+8], rbx
0x1802ef3a7  mov     [rdi+10h], rsi
0x1802ef3ab  mov     [rdi+18h], rsi
0x1802ef3af  mov     [rdi+20h], rsi
0x1802ef3b3  mov     [rdi+28h], rbp
0x1802ef3b7  mov     [rdi+30h], rsi
0x1802ef3bb  mov     [rdi+38h], sil
0x1802ef3bf  mov     [rdi+40h], r13
0x1802ef3c3  mov     [rdi+48h], rsi
0x1802ef3c7  mov     [rdi+50h], esi
0x1802ef3ca  mov     [rdi+58h], rsi
0x1802ef3ce  lea     rbx, [r12+1C38h]
0x1802ef3d6  mov     [rbx], rcx
0x1802ef3d9  lea     rax, ?RecoverUnusedMemory@ExternalApi@JsUtil@@SAXXZ; JsUtil::ExternalApi::RecoverUnusedMemory(void)
0x1802ef3e0  mov     [rbx+8], rax
0x1802ef3e4  mov     [rbx+10h], rsi
0x1802ef3e8  mov     [rbx+18h], rsi
0x1802ef3ec  mov     [rbx+20h], rsi
0x1802ef3f0  mov     [rbx+28h], rbp
0x1802ef3f4  mov     [rbx+30h], rsi
0x1802ef3f8  mov     [rbx+38h], sil
0x1802ef3fc  mov     [rbx+40h], r13
0x1802ef400  mov     [rbx+48h], rsi
0x1802ef404  mov     [rbx+50h], esi
0x1802ef407  mov     [rbx+58h], rsi
0x1802ef40b  mov     [r12+1C98h], rcx
0x1802ef413  mov     [r12+1CA0h], rax
0x1802ef41b  mov     [r12+1CA8h], rsi
0x1802ef423  mov     [r12+1CB0h], rsi
0x1802ef42b  mov     [r12+1CB8h], rsi
0x1802ef433  mov     [r12+1CC0h], rbp
0x1802ef43b  mov     [r12+1CC8h], rsi
0x1802ef443  mov     [r12+1CD0h], sil
0x1802ef44b  mov     [r12+1CD8h], r13
0x1802ef453  mov     [r12+1CE0h], rsi
0x1802ef45b  mov     [r12+1CE8h], esi
0x1802ef463  mov     [r12+1CF0h], rsi
0x1802ef46b  lea     rax, [r12+1CF8h]
0x1802ef473  mov     [rax], rax
0x1802ef476  mov     [rax+8], rax
0x1802ef47a  lea     rcx, [r12+1D08h]
0x1802ef482  mov     r8d, 209h
0x1802ef488  mov     rdx, rdi
0x1802ef48b  call    ??0?$BaseDictionary@HPEAV?$SList@PEAUInlineCache@Js@@VArenaAllocator@Memory@@VFakeCount@@@@VArenaAllocator@Memory@@U?$DictionarySizePolicy@UPrimePolicy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@VNoResizeLock@7@@JsUtil@@QEAA@PEAVArenaAllocator@Memory@@H@Z; JsUtil::BaseDictionary<int,SList<Js::InlineCache *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::BaseDictionary<int,SList<Js::InlineCache *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>(Memory::ArenaAllocator *,int)
0x1802ef490  nop
0x1802ef491  lea     rcx, [r12+1D38h]
0x1802ef499  mov     r8d, 125h
0x1802ef49f  mov     rdx, rdi
0x1802ef4a2  call    ??0?$BaseDictionary@HPEAV?$SList@PEAUInlineCache@Js@@VArenaAllocator@Memory@@VFakeCount@@@@VArenaAllocator@Memory@@U?$DictionarySizePolicy@UPrimePolicy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@VNoResizeLock@7@@JsUtil@@QEAA@PEAVArenaAllocator@Memory@@H@Z; JsUtil::BaseDictionary<int,SList<Js::InlineCache *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::BaseDictionary<int,SList<Js::InlineCache *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>(Memory::ArenaAllocator *,int)
0x1802ef4a7  nop
0x1802ef4a8  mov     [r12+1D68h], rsi
0x1802ef4b0  lea     rcx, [r12+1D70h]
0x1802ef4b8  mov     rdx, rbx
0x1802ef4bb  call    ??0?$BaseDictionary@PEAXPEAUIsInstInlineCache@Js@@VArenaAllocator@Memory@@U?$DictionarySizePolicy@UPrimePolicy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@VNoResizeLock@8@@JsUtil@@QEAA@PEAVArenaAllocator@Memory@@H@Z; JsUtil::BaseDictionary<void *,Js::IsInstInlineCache *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::BaseDictionary<void *,Js::IsInstInlineCache *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>(Memory::ArenaAllocator *,int)
0x1802ef4c0  nop
0x1802ef4c1  mov     [r12+1DA0h], rsi
0x1802ef4c9  mov     [r12+1DA8h], rsi
0x1802ef4d1  mov     qword ptr [r12+1DB0h], 1
0x1802ef4dd  mov     [r12+1DB8h], esi
0x1802ef4e5  lea     rcx, [r12+1DC0h]
0x1802ef4ed  mov     rdx, rbp
0x1802ef4f0  call    ??0?$ThreadCacheRegistry@V?$PrototypeChainCache@VOnlyWritablePropertyCache@Js@@@Js@@@Js@@QEAA@PEAV?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@@Z; Js::ThreadCacheRegistry<Js::PrototypeChainCache<Js::OnlyWritablePropertyCache>>::ThreadCacheRegistry<Js::PrototypeChainCache<Js::OnlyWritablePropertyCache>>(Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>> *)
0x1802ef4f5  nop
0x1802ef4f6  lea     rcx, [r12+1E30h]
0x1802ef4fe  mov     rdx, rbp
0x1802ef501  call    ??0?$ThreadCacheRegistry@V?$PrototypeChainCache@VOnlyWritablePropertyCache@Js@@@Js@@@Js@@QEAA@PEAV?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@@Z; Js::ThreadCacheRegistry<Js::PrototypeChainCache<Js::OnlyWritablePropertyCache>>::ThreadCacheRegistry<Js::PrototypeChainCache<Js::OnlyWritablePropertyCache>>(Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>> *)
0x1802ef506  nop
0x1802ef507  lea     rax, [r12+1EA0h]
0x1802ef50f  mov     [rax], rax
0x1802ef512  mov     [rax+8], rax
0x1802ef516  lea     rcx, [r12+1EB0h]; lpCriticalSection
0x1802ef51e  xor     edx, edx; dwSpinCount
0x1802ef520  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1802ef527  nop     dword ptr [rax+rax+00h]
0x1802ef52c  nop
0x1802ef52d  mov     [r12+1ED8h], sil
0x1802ef535  mov     al, cs:byte_18073F2DA
0x1802ef53b  mov     [r12+1ED9h], al
0x1802ef543  mov     al, cs:byte_18073F242
0x1802ef549  mov     [r12+1EDAh], al
0x1802ef551  mov     byte ptr [r12+1EDBh], 1
0x1802ef55a  mov     [r12+1EE0h], rsi
0x1802ef562  mov     [r12+1EE8h], esi
0x1802ef56a  mov     [r12+1EF8h], rsi
0x1802ef572  mov     [r12+1F00h], sil
0x1802ef57a  lea     rax, ??_7DelayLoadWinRtString@Js@@6B@; const Js::DelayLoadWinRtString::`vftable'
0x1802ef581  mov     [r12+1EF0h], rax
0x1802ef589  mov     [r12+1F08h], rsi
0x1802ef591  mov     [r12+1F10h], rsi
0x1802ef599  mov     [r12+1F18h], rsi
0x1802ef5a1  mov     [r12+1F20h], rsi
0x1802ef5a9  mov     [r12+1F28h], rsi
0x1802ef5b1  mov     [r12+1F30h], rsi
0x1802ef5b9  mov     [r12+1F40h], rsi
0x1802ef5c1  mov     [r12+1F48h], sil
0x1802ef5c9  lea     rax, ??_7DelayLoadWinRtError@Js@@6B@; const Js::DelayLoadWinRtError::`vftable'
0x1802ef5d0  mov     [r12+1F38h], rax
0x1802ef5d8  mov     [r12+1F50h], rsi
0x1802ef5e0  mov     [r12+1F58h], rsi
0x1802ef5e8  mov     [r12+1F68h], rsi
0x1802ef5f0  mov     [r12+1F70h], sil
0x1802ef5f8  lea     rax, ??_7DelayLoadWinRtTypeResolution@Js@@6B@; const Js::DelayLoadWinRtTypeResolution::`vftable'
0x1802ef5ff  mov     [r12+1F60h], rax
0x1802ef607  mov     [r12+1F78h], rsi
0x1802ef60f  mov     [r12+1F90h], rsi
0x1802ef617  mov     [r12+1F98h], sil
0x1802ef61f  lea     rax, ??_7DelayLoadWinRtRoParameterizedIID@Js@@6B@; const Js::DelayLoadWinRtRoParameterizedIID::`vftable'
0x1802ef626  mov     [r12+1F88h], rax
0x1802ef62e  mov     [r12+1FA0h], rsi
0x1802ef636  mov     [r12+1FB0h], rsi
0x1802ef63e  mov     [r12+1FB8h], sil
0x1802ef646  lea     rax, ??_7DelayLoadWinRtFoundation@Js@@6B@; const Js::DelayLoadWinRtFoundation::`vftable'
0x1802ef64d  mov     [r12+1FA8h], rax
0x1802ef655  mov     [r12+1FC0h], rsi
0x1802ef65d  lea     rax, [r12+1FC8h]
0x1802ef665  mov     [rsp+0C8h+var_68], rax
0x1802ef66a  mov     [rax], rsi
0x1802ef66d  add     rax, 8
0x1802ef671  mov     [rsp+0C8h+var_68], rax
0x1802ef676  mov     [rax], rsi
0x1802ef679  mov     [r12+1FD8h], esi
0x1802ef681  lea     rdi, [r12+1FE0h]
0x1802ef689  mov     [rdi], rsi
0x1802ef68c  mov     [rdi+8], rsi
0x1802ef690  mov     [r12+1FF8h], rsi
0x1802ef698  mov     [r12+2000h], rsi
0x1802ef6a0  lea     rcx, [r12+2010h]; lpCriticalSection
0x1802ef6a8  xor     edx, edx; dwSpinCount
0x1802ef6aa  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1802ef6b1  nop     dword ptr [rax+rax+00h]
0x1802ef6b6  nop
0x1802ef6b7  mov     [r12+3380h], esi
0x1802ef6bf  lea     rcx, [r12+3390h]
0x1802ef6c7  call    ??0?$BaseDictionary@PEBVDynamicType@Js@@PEAXUHeapAllocator@Memory@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@VNoResizeLock@8@@JsUtil@@QEAA@PEAUHeapAllocator@Memory@@H@Z; JsUtil::BaseDictionary<Js::DynamicType const *,void *,Memory::HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::BaseDictionary<Js::DynamicType const *,void *,Memory::HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>(Memory::HeapAllocator *,int)
0x1802ef6cc  nop
0x1802ef6cd  lea     rbx, [r12+33C0h]
0x1802ef6d5  mov     [r12+33D0h], rbx
0x1802ef6dd  mov     [r12+33D8h], rsi
0x1802ef6e5  mov     [r12+33E8h], rsi
0x1802ef6ed  mov     [r12+33F0h], sil
0x1802ef6f5  lea     rax, ??_7UCrtC99MathApis@@6B@; const UCrtC99MathApis::`vftable'
0x1802ef6fc  mov     [r12+33E0h], rax
0x1802ef704  mov     [r12+33F8h], rsi
0x1802ef70c  mov     [r12+3400h], rsi
0x1802ef714  mov     [r12+3408h], rsi
0x1802ef71c  mov     [r12+3410h], rsi
0x1802ef724  mov     [r12+3418h], rsi
  ... truncated ...
```
