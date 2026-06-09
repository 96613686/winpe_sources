# ThreadContext::~ThreadContext(void)

- ea: `0x18030f78c`
- end: `0x18030fc31`
- name: `??1ThreadContext@@QEAA@XZ`
- size: `1189`
- prototype: `void __fastcall(ThreadContext *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18030f750`

## callees

- `0x1800cb478`
- `0x1801508d4`
- `0x1801c8690`
- `0x1801c87b0`
- `0x18030f78c`
- `0x18030fc38`
- `0x18030fcc0`
- `0x18030fd24`
- `0x18033b434`
- `0x1803bcf80`
- `0x1803c0838`
- `0x1803c0888`
- `0x1803c445c`
- `0x1803d42dc`
- `0x1803d4308`
- `0x1803de67c`
- `0x1803ef048`
- `0x1803f1254`
- `0x1803f1468`
- `0x1803f3728`
- `0x1803f3b60`
- `0x1803f3bb0`
- `0x1803f495c`
- `0x18053c510`
- `0x18053c54c`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18030f827`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18030f827`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18030f7ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18030f7ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18030fac7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18030fb56`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18030fbff`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18030fac7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18030fb56`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18030fbff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ThreadContext::~ThreadContext(ThreadContext *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  void *v5; // rbx
  __int64 i; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  void *v11; // rdx
  _QWORD *v12; // rsi
  _QWORD *j; // rdx
  _QWORD *v14; // rbx
  _QWORD *v15; // rsi
  _QWORD *k; // rdx
  _QWORD *v17; // rbx

  *(_QWORD *)this = &ThreadContext::`vftable'{for `Memory::DefaultRecyclerCollectionWrapper'};
  *((_QWORD *)this + 2) = &ThreadContext::`vftable'{for `ThreadContextInfo'};
  EnterCriticalSection(&ThreadContext::s_csThreadContext);
  v2 = *((_QWORD *)this + 15);
  if ( v2 )
    *(_QWORD *)(v2 + 128) = *((_QWORD *)this + 16);
  else
    ThreadContext::globalListFirst = (ThreadContext *)*((_QWORD *)this + 16);
  v3 = *((_QWORD *)this + 16);
  if ( v3 )
    *(_QWORD *)(v3 + 120) = *((_QWORD *)this + 15);
  else
    ThreadContext::globalListLast = (struct ThreadContext *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  LeaveCriticalSection(&ThreadContext::s_csThreadContext);
  v5 = (void *)*((_QWORD *)this + 1694);
  if ( v5 )
  {
    (**(void (__fastcall ***)(_QWORD, _QWORD))v5)(*((_QWORD *)this + 1694), 0);
    Memory::HeapAllocator::Free((Memory::HeapAllocator *)&Memory::HeapAllocator::Instance, v5, 0x20u);
    *((_QWORD *)this + 1694) = 0;
  }
  *((_BYTE *)this + 1108) = 1;
  if ( *((_QWORD *)this + 162) )
  {
    for ( i = *((_QWORD *)this + 877); i; i = *(_QWORD *)(i + 48) )
    {
      if ( !*(_BYTE *)(i + 1521) )
        Js::ScriptContext::MarkForClose((Js::ScriptContext *)i);
    }
    *(_QWORD *)(*((_QWORD *)this + 875) + 480LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 875) + 504LL) = 0;
    v7 = *(_QWORD *)(*((_QWORD *)this + 875) + 512LL);
    if ( v7 )
    {
      JsUtil::BaseDictionary<void *,Js::MapOrSetDataNode<JsUtil::KeyValuePair<void *,void *>> *,Memory::Recycler,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::Clear(v7);
      *(_QWORD *)(*((_QWORD *)this + 875) + 512LL) = 0;
    }
    v8 = *(_QWORD *)(*((_QWORD *)this + 875) + 520LL);
    if ( v8 )
    {
      *(_DWORD *)(v8 + 16) = 0;
      *(_QWORD *)(*((_QWORD *)this + 875) + 520LL) = 0;
    }
    if ( *((_QWORD *)this + 28) )
    {
      Memory::DeleteObject<Memory::HeapAllocator,0,JsUtil::BaseHashSet<Js::PropertyRecord const *,Memory::HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,Js::PropertyRecord const *,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry,JsUtil::AsymetricResizeLock>>(v8);
      *((_QWORD *)this + 28) = 0;
    }
    if ( *((_QWORD *)this + 32) )
    {
      Memory::DeleteObject<Memory::HeapAllocator,0,BVSparse<Memory::HeapAllocator>>(v8);
      *((_QWORD *)this + 32) = 0;
    }
    Memory::Recycler::RootRelease(*((Memory::Recycler **)this + 162), *((void **)this + 875), 0);
    *((_QWORD *)this + 875) = 0;
    v10 = (_QWORD *)*((_QWORD *)this + 162);
    if ( v10[273] || v10[280] || v10[288] )
    {
      Js::Throw::FatalInternalError(-2147467259);
      __debugbreak();
    }
    Memory::DeleteObject<Memory::HeapAllocator,0,Memory::Recycler>(v9);
  }
  v11 = (void *)*((_QWORD *)this + 317);
  if ( v11 )
  {
    if ( *((_BYTE *)this + 7898) )
      Memory::DeleteObject<Memory::HeapAllocator,0,JsUtil::BackgroundJobProcessor>(v4);
    else
      Memory::HeapAllocator::Free((Memory::HeapAllocator *)&Memory::HeapAllocator::Instance, v11, 0x38u);
    *((_QWORD *)this + 317) = 0;
  }
  v12 = (_QWORD *)((char *)this + 2528);
  for ( j = (_QWORD *)*((_QWORD *)this + 316); j != v12; j = v14 )
  {
    v14 = (_QWORD *)*j;
    Memory::HeapAllocator::Free((Memory::HeapAllocator *)&Memory::HeapAllocator::Instance, j, 0x10u);
  }
  *v12 = v12;
  v15 = (_QWORD *)((char *)this + 7840);
  for ( k = (_QWORD *)*((_QWORD *)this + 980); k != v15; k = v17 )
  {
    v17 = (_QWORD *)*k;
    Memory::DeleteObject<Memory::HeapAllocator,0,Js::SharedContents>(v4);
  }
  *v15 = v15;
  *((_QWORD *)this + 981) = (char *)this + 7840;
  JsUtil::BaseDictionary<int,SList<Js::InlineCache *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::Reset((char *)this + 7432);
  JsUtil::BaseDictionary<int,SList<Js::InlineCache *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::Reset((char *)this + 7480);
  JsUtil::BaseDictionary<int,SList<Js::InlineCache *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::Reset((char *)this + 7536);
  *((_QWORD *)this + 927) = (char *)this + 7416;
  *((_QWORD *)this + 928) = (char *)this + 7416;
  *((_QWORD *)this + 964) = (char *)this + 7712;
  *((_QWORD *)this + 965) = (char *)this + 7712;
  *((_QWORD *)this + 978) = (char *)this + 7824;
  *((_QWORD *)this + 979) = (char *)this + 7824;
  *((_QWORD *)this + 941) = 0;
  if ( *((_QWORD *)this + 27) )
    *((_QWORD *)this + 27) = 0;
  _InterlockedAdd64((volatile signed __int64 *)&ThreadContext::processNativeCodeSize, -*((_QWORD *)this + 879));
  JsUtil::BaseDictionary<Ident *,unsigned int,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::~BaseDictionary<Ident *,unsigned int,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>((char *)this + 13560);
  *((_QWORD *)this + 1660) = &UCrtC99MathApis::`vftable';
  DelayLoadLibrary::~DelayLoadLibrary((ThreadContext *)((char *)this + 13280));
  JsUtil::BaseDictionary<Js::DynamicType const *,void *,Memory::HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::~BaseDictionary<Js::DynamicType const *,void *,Memory::HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>((char *)this + 13200);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8208));
  Js::WindowsFoundationAdapter::~WindowsFoundationAdapter((ThreadContext *)((char *)this + 8136));
  *((_QWORD *)this + 1013) = &Js::DelayLoadWinRtFoundation::`vftable';
  DelayLoadLibrary::~DelayLoadLibrary((ThreadContext *)((char *)this + 8104));
  *((_QWORD *)this + 1009) = &Js::DelayLoadWinRtRoParameterizedIID::`vftable';
  DelayLoadLibrary::~DelayLoadLibrary((ThreadContext *)((char *)this + 8072));
  *((_QWORD *)this + 1004) = &Js::DelayLoadWinRtTypeResolution::`vftable';
  DelayLoadLibrary::~DelayLoadLibrary((ThreadContext *)((char *)this + 8032));
  *((_QWORD *)this + 999) = &Js::DelayLoadWinRtError::`vftable';
  DelayLoadLibrary::~DelayLoadLibrary((ThreadContext *)((char *)this + 7992));
  *((_QWORD *)this + 990) = &Js::DelayLoadWinRtString::`vftable';
  DelayLoadLibrary::~DelayLoadLibrary((ThreadContext *)((char *)this + 7920));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 7856));
  Memory::ArenaAllocator::~ArenaAllocator((ThreadContext *)((char *)this + 7728));
  Memory::ArenaAllocator::~ArenaAllocator((ThreadContext *)((char *)this + 7616));
  JsUtil::BaseDictionary<unsigned int,SList<unsigned short const *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::~BaseDictionary<unsigned int,SList<unsigned short const *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>((char *)this + 7536);
  JsUtil::BaseDictionary<unsigned int,SList<unsigned short const *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::~BaseDictionary<unsigned int,SList<unsigned short const *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>((char *)this + 7480);
  JsUtil::BaseDictionary<unsigned int,SList<unsigned short const *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::~BaseDictionary<unsigned int,SList<unsigned short const *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>((char *)this + 7432);
  Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>((char *)this + 7320);
  Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>((char *)this + 7224);
  Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>((char *)this + 7128);
  JITThunkEmitter<Memory::VirtualAllocWrapper>::~JITThunkEmitter<Memory::VirtualAllocWrapper>((char *)this + 3720);
  Memory::CustomHeap::CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>::~CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>((char *)this + 3136);
  Memory::CustomHeap::CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>::~CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>((char *)this + 2552);
  Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>((char *)this + 2384);
  SList<Js::ArrayBufferContentForDelayedFreeBase *,Memory::HeapAllocator,FakeCount>::~SList<Js::ArrayBufferContentForDelayedFreeBase *,Memory::HeapAllocator,FakeCount>((char *)this + 1304);
  Memory::IdleDecommitPageAllocator::~IdleDecommitPageAllocator((ThreadContext *)((char *)this + 976));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 928));
  Memory::PreReservedVirtualAllocWrapper::~PreReservedVirtualAllocWrapper((ThreadContext *)((char *)this + 344));
  ThreadContextInfo::~ThreadContextInfo((ThreadContext *)((char *)this + 16));
}

```

## disassembly

```asm
0x18030f78c  mov     r11, rsp
0x18030f78f  mov     [r11+8], rcx
0x18030f793  push    rbx
0x18030f794  push    rbp
0x18030f795  push    rsi
0x18030f796  push    rdi
0x18030f797  push    r12
0x18030f799  push    r13
0x18030f79b  push    r14
0x18030f79d  push    r15
0x18030f79f  sub     rsp, 38h
0x18030f7a3  mov     qword ptr [r11-58h], 0FFFFFFFFFFFFFFFEh
0x18030f7ab  lea     rax, ??_7ThreadContext@@6BDefaultRecyclerCollectionWrapper@Memory@@@; const ThreadContext::`vftable'{for `Memory::DefaultRecyclerCollectionWrapper'}
0x18030f7b2  mov     rdi, rcx
0x18030f7b5  mov     [rcx], rax
0x18030f7b8  lea     rax, ??_7ThreadContext@@6BThreadContextInfo@@@; const ThreadContext::`vftable'{for `ThreadContextInfo'}
0x18030f7bf  mov     [rcx+10h], rax
0x18030f7c3  lea     rcx, ?s_csThreadContext@ThreadContext@@0VCriticalSection@@A; lpCriticalSection
0x18030f7ca  call    cs:__imp_EnterCriticalSection
0x18030f7d1  nop     dword ptr [rax+rax+00h]
0x18030f7d6  mov     rcx, [rdi+78h]
0x18030f7da  mov     rax, [rdi+80h]
0x18030f7e1  xor     esi, esi
0x18030f7e3  test    rcx, rcx
0x18030f7e6  jz      short loc_18030F7F1
0x18030f7e8  mov     [rcx+80h], rax
0x18030f7ef  jmp     short loc_18030F7F8
0x18030f7f1  mov     cs:?globalListFirst@ThreadContext@@2PEAV1@EA, rax; ThreadContext * ThreadContext::globalListFirst
0x18030f7f8  mov     rcx, [rdi+80h]
0x18030f7ff  mov     rax, [rdi+78h]
0x18030f803  test    rcx, rcx
0x18030f806  jz      short loc_18030F80E
0x18030f808  mov     [rcx+78h], rax
0x18030f80c  jmp     short loc_18030F815
0x18030f80e  mov     cs:?globalListLast@ThreadContext@@0PEAV1@EA, rax; ThreadContext * ThreadContext::globalListLast
0x18030f815  mov     [rdi+78h], rsi
0x18030f819  mov     [rdi+80h], rsi
0x18030f820  lea     rcx, ?s_csThreadContext@ThreadContext@@0VCriticalSection@@A; lpCriticalSection
0x18030f827  call    cs:__imp_LeaveCriticalSection
0x18030f82e  nop     dword ptr [rax+rax+00h]
0x18030f833  nop
0x18030f834  mov     rbx, [rdi+34F0h]
0x18030f83b  lea     rbp, ?Instance@HeapAllocator@Memory@@2U12@A; Memory::HeapAllocator Memory::HeapAllocator::Instance
0x18030f842  test    rbx, rbx
0x18030f845  jz      short loc_18030F86F
0x18030f847  mov     rax, [rbx]
0x18030f84a  xor     edx, edx
0x18030f84c  mov     rcx, rbx
0x18030f84f  mov     rax, [rax]
0x18030f852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030f857  mov     r8d, 20h ; ' '; unsigned __int64
0x18030f85d  mov     rdx, rbx; void *
0x18030f860  mov     rcx, rbp; this
0x18030f863  call    ?Free@HeapAllocator@Memory@@QEAAXPEAX_K@Z; Memory::HeapAllocator::Free(void *,unsigned __int64)
0x18030f868  mov     [rdi+34F0h], rsi
0x18030f86f  mov     byte ptr [rdi+454h], 1
0x18030f876  cmp     [rdi+510h], rsi
0x18030f87d  jz      loc_18030F980
0x18030f883  mov     rbx, [rdi+1B68h]
0x18030f88a  jmp     short loc_18030F8A1
0x18030f88c  cmp     [rbx+5F1h], sil
0x18030f893  jnz     short loc_18030F89D
0x18030f895  mov     rcx, rbx; this
0x18030f898  call    ?MarkForClose@ScriptContext@Js@@QEAAXXZ; Js::ScriptContext::MarkForClose(void)
0x18030f89d  mov     rbx, [rbx+30h]
0x18030f8a1  test    rbx, rbx
0x18030f8a4  jnz     short loc_18030F88C
0x18030f8a6  mov     rax, [rdi+1B58h]
0x18030f8ad  mov     [rax+1E0h], rsi
0x18030f8b4  mov     rax, [rdi+1B58h]
0x18030f8bb  mov     [rax+1F8h], rsi
0x18030f8c2  mov     rax, [rdi+1B58h]
0x18030f8c9  mov     rcx, [rax+200h]
0x18030f8d0  test    rcx, rcx
0x18030f8d3  jz      short loc_18030F8E8
0x18030f8d5  call    ?Clear@?$BaseDictionary@PEAXPEAV?$MapOrSetDataNode@U?$KeyValuePair@PEAXPEAX@JsUtil@@@Js@@VRecycler@Memory@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@VNoResizeLock@8@@JsUtil@@QEAAXXZ; JsUtil::BaseDictionary<void *,Js::MapOrSetDataNode<JsUtil::KeyValuePair<void *,void *>> *,Memory::Recycler,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::Clear(void)
0x18030f8da  mov     rax, [rdi+1B58h]
0x18030f8e1  mov     [rax+200h], rsi
0x18030f8e8  mov     rax, [rdi+1B58h]
0x18030f8ef  mov     rcx, [rax+208h]
0x18030f8f6  test    rcx, rcx
0x18030f8f9  jz      short loc_18030F90C
0x18030f8fb  mov     [rcx+10h], esi
0x18030f8fe  mov     rax, [rdi+1B58h]
0x18030f905  mov     [rax+208h], rsi
0x18030f90c  mov     rdx, [rdi+0E0h]
0x18030f913  test    rdx, rdx
0x18030f916  jz      short loc_18030F924
0x18030f918  call    ??$DeleteObject@UHeapAllocator@Memory@@$0A@V?$BaseHashSet@PEBVPropertyRecord@Js@@UHeapAllocator@Memory@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@PEBV12@UPropertyRecordStringHashComparer@2@VSimpleHashedEntry@JsUtil@@VAsymetricResizeLock@8@@JsUtil@@@Memory@@YAXPEAUHeapAllocator@0@PEAV?$BaseHashSet@PEBVPropertyRecord@Js@@UHeapAllocator@Memory@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@PEBV12@UPropertyRecordStringHashComparer@2@VSimpleHashedEntry@JsUtil@@VAsymetricResizeLock@8@@JsUtil@@@Z; Memory::DeleteObject<Memory::HeapAllocator,0,JsUtil::BaseHashSet<Js::PropertyRecord const *,Memory::HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,Js::PropertyRecord const *,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry,JsUtil::AsymetricResizeLock>>(Memory::HeapAllocator *,JsUtil::BaseHashSet<Js::PropertyRecord const *,Memory::HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,Js::PropertyRecord const *,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry,JsUtil::AsymetricResizeLock> *)
0x18030f91d  mov     [rdi+0E0h], rsi
0x18030f924  mov     rdx, [rdi+100h]
0x18030f92b  test    rdx, rdx
0x18030f92e  jz      short loc_18030F93C
0x18030f930  call    ??$DeleteObject@UHeapAllocator@Memory@@$0A@V?$BVSparse@UHeapAllocator@Memory@@@@@Memory@@YAXPEAUHeapAllocator@0@PEAV?$BVSparse@UHeapAllocator@Memory@@@@@Z; Memory::DeleteObject<Memory::HeapAllocator,0,BVSparse<Memory::HeapAllocator>>(Memory::HeapAllocator *,BVSparse<Memory::HeapAllocator> *)
0x18030f935  mov     [rdi+100h], rsi
0x18030f93c  xor     r8d, r8d; unsigned int *
0x18030f93f  mov     rdx, [rdi+1B58h]; void *
0x18030f946  mov     rcx, [rdi+510h]; this
0x18030f94d  call    ?RootRelease@Recycler@Memory@@QEAAXPEAXPEAI@Z; Memory::Recycler::RootRelease(void *,uint *)
0x18030f952  mov     [rdi+1B58h], rsi
0x18030f959  mov     rdx, [rdi+510h]
0x18030f960  cmp     [rdx+888h], rsi
0x18030f967  jnz     short loc_18030F99C
0x18030f969  cmp     [rdx+8C0h], rsi
0x18030f970  jnz     short loc_18030F99C
0x18030f972  cmp     [rdx+900h], rsi
0x18030f979  jnz     short loc_18030F99C
0x18030f97b  call    ??$DeleteObject@UHeapAllocator@Memory@@$0A@VRecycler@2@@Memory@@YAXPEAUHeapAllocator@0@PEAVRecycler@0@@Z; Memory::DeleteObject<Memory::HeapAllocator,0,Memory::Recycler>(Memory::HeapAllocator *,Memory::Recycler *)
0x18030f980  mov     rdx, [rdi+9E8h]; void *
0x18030f987  test    rdx, rdx
0x18030f98a  jz      short loc_18030F9BC
0x18030f98c  cmp     [rdi+1EDAh], sil
0x18030f993  jz      short loc_18030F9A7
0x18030f995  call    ??$DeleteObject@UHeapAllocator@Memory@@$0A@VBackgroundJobProcessor@JsUtil@@@Memory@@YAXPEAUHeapAllocator@0@PEAVBackgroundJobProcessor@JsUtil@@@Z; Memory::DeleteObject<Memory::HeapAllocator,0,JsUtil::BackgroundJobProcessor>(Memory::HeapAllocator *,JsUtil::BackgroundJobProcessor *)
0x18030f99a  jmp     short loc_18030F9B5
0x18030f99c  mov     ecx, 80004005h; int
0x18030f9a1  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
0x18030f9a6  int     3; Trap to Debugger
0x18030f9a7  mov     r8d, 38h ; '8'; unsigned __int64
0x18030f9ad  mov     rcx, rbp; this
0x18030f9b0  call    ?Free@HeapAllocator@Memory@@QEAAXPEAX_K@Z; Memory::HeapAllocator::Free(void *,unsigned __int64)
0x18030f9b5  mov     [rdi+9E8h], rsi
0x18030f9bc  lea     rsi, [rdi+9E0h]
0x18030f9c3  mov     rdx, [rsi]; void *
0x18030f9c6  cmp     rdx, rsi
0x18030f9c9  jz      short loc_18030F9E1
0x18030f9cb  mov     rbx, [rdx]
0x18030f9ce  mov     r8d, 10h; unsigned __int64
0x18030f9d4  mov     rcx, rbp; this
0x18030f9d7  call    ?Free@HeapAllocator@Memory@@QEAAXPEAX_K@Z; Memory::HeapAllocator::Free(void *,unsigned __int64)
0x18030f9dc  mov     rdx, rbx
0x18030f9df  jmp     short loc_18030F9C6
0x18030f9e1  mov     [rsi], rsi
0x18030f9e4  lea     rsi, [rdi+1EA0h]
0x18030f9eb  mov     rdx, [rsi]
0x18030f9ee  cmp     rdx, rsi
0x18030f9f1  jz      short loc_18030FA00
0x18030f9f3  mov     rbx, [rdx]
0x18030f9f6  call    ??$DeleteObject@UHeapAllocator@Memory@@$0A@VSharedContents@Js@@@Memory@@YAXPEAUHeapAllocator@0@PEAVSharedContents@Js@@@Z; Memory::DeleteObject<Memory::HeapAllocator,0,Js::SharedContents>(Memory::HeapAllocator *,Js::SharedContents *)
0x18030f9fb  mov     rdx, rbx
0x18030f9fe  jmp     short loc_18030F9EE
0x18030fa00  mov     [rsi], rsi
0x18030fa03  mov     [rsi+8], rsi
0x18030fa07  lea     rbx, [rdi+1D08h]
0x18030fa0e  mov     rcx, rbx
0x18030fa11  call    ?Reset@?$BaseDictionary@HPEAV?$SList@PEAUInlineCache@Js@@VArenaAllocator@Memory@@VFakeCount@@@@VArenaAllocator@Memory@@U?$DictionarySizePolicy@UPrimePolicy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@VNoResizeLock@7@@JsUtil@@QEAAXXZ; JsUtil::BaseDictionary<int,SList<Js::InlineCache *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::Reset(void)
0x18030fa16  lea     rsi, [rdi+1D38h]
0x18030fa1d  mov     rcx, rsi
0x18030fa20  call    ?Reset@?$BaseDictionary@HPEAV?$SList@PEAUInlineCache@Js@@VArenaAllocator@Memory@@VFakeCount@@@@VArenaAllocator@Memory@@U?$DictionarySizePolicy@UPrimePolicy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@VNoResizeLock@7@@JsUtil@@QEAAXXZ; JsUtil::BaseDictionary<int,SList<Js::InlineCache *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::Reset(void)
0x18030fa25  lea     rbp, [rdi+1D70h]
0x18030fa2c  mov     rcx, rbp
0x18030fa2f  call    ?Reset@?$BaseDictionary@HPEAV?$SList@PEAUInlineCache@Js@@VArenaAllocator@Memory@@VFakeCount@@@@VArenaAllocator@Memory@@U?$DictionarySizePolicy@UPrimePolicy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@VNoResizeLock@7@@JsUtil@@QEAAXXZ; JsUtil::BaseDictionary<int,SList<Js::InlineCache *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::Reset(void)
0x18030fa34  lea     rax, [rdi+1CF8h]
0x18030fa3b  mov     [rax], rax
0x18030fa3e  mov     [rax+8], rax
0x18030fa42  lea     r14, [rdi+1DC0h]
0x18030fa49  lea     rax, [r14+60h]
0x18030fa4d  mov     [rax], rax
0x18030fa50  mov     [rax+8], rax
0x18030fa54  lea     r15, [rdi+1E30h]
0x18030fa5b  lea     rax, [r15+60h]
0x18030fa5f  mov     [rax], rax
0x18030fa62  mov     [rax+8], rax
0x18030fa66  xor     eax, eax
0x18030fa68  mov     [rdi+1D68h], rax
0x18030fa6f  cmp     [rdi+0D8h], rax
0x18030fa76  jz      short loc_18030FA7F
0x18030fa78  mov     [rdi+0D8h], rax
0x18030fa7f  mov     rax, [rdi+1B78h]
0x18030fa86  neg     rax
0x18030fa89  lock add cs:?processNativeCodeSize@ThreadContext@@0_KA, rax; unsigned __int64 ThreadContext::processNativeCodeSize
0x18030fa91  lea     rcx, [rdi+34F8h]
0x18030fa98  call    ??1?$BaseDictionary@PEAUIdent@@IVArenaAllocator@Memory@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@VNoResizeLock@7@@JsUtil@@QEAA@XZ; JsUtil::BaseDictionary<Ident *,uint,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::~BaseDictionary<Ident *,uint,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>(void)
0x18030fa9d  lea     rcx, [rdi+33E0h]; this
0x18030faa4  lea     rax, ??_7UCrtC99MathApis@@6B@; const UCrtC99MathApis::`vftable'
0x18030faab  mov     [rcx], rax
0x18030faae  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x18030fab3  lea     rcx, [rdi+3390h]
0x18030faba  call    ??1?$BaseDictionary@PEBVDynamicType@Js@@PEAXUHeapAllocator@Memory@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@VNoResizeLock@8@@JsUtil@@QEAA@XZ; JsUtil::BaseDictionary<Js::DynamicType const *,void *,Memory::HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::~BaseDictionary<Js::DynamicType const *,void *,Memory::HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>(void)
0x18030fabf  nop
0x18030fac0  lea     rcx, [rdi+2010h]; lpCriticalSection
0x18030fac7  call    cs:__imp_DeleteCriticalSection
0x18030face  nop     dword ptr [rax+rax+00h]
0x18030fad3  nop
0x18030fad4  lea     rcx, [rdi+1FC8h]; this
0x18030fadb  call    ??1WindowsFoundationAdapter@Js@@QEAA@XZ; Js::WindowsFoundationAdapter::~WindowsFoundationAdapter(void)
0x18030fae0  lea     rcx, [rdi+1FA8h]; this
0x18030fae7  lea     rax, ??_7DelayLoadWinRtFoundation@Js@@6B@; const Js::DelayLoadWinRtFoundation::`vftable'
0x18030faee  mov     [rcx], rax
0x18030faf1  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x18030faf6  lea     rcx, [rdi+1F88h]; this
0x18030fafd  lea     rax, ??_7DelayLoadWinRtRoParameterizedIID@Js@@6B@; const Js::DelayLoadWinRtRoParameterizedIID::`vftable'
0x18030fb04  mov     [rcx], rax
0x18030fb07  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x18030fb0c  lea     rcx, [rdi+1F60h]; this
0x18030fb13  lea     rax, ??_7DelayLoadWinRtTypeResolution@Js@@6B@; const Js::DelayLoadWinRtTypeResolution::`vftable'
0x18030fb1a  mov     [rcx], rax
0x18030fb1d  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x18030fb22  lea     rcx, [rdi+1F38h]; this
0x18030fb29  lea     rax, ??_7DelayLoadWinRtError@Js@@6B@; const Js::DelayLoadWinRtError::`vftable'
0x18030fb30  mov     [rcx], rax
0x18030fb33  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x18030fb38  lea     rcx, [rdi+1EF0h]; this
0x18030fb3f  lea     rax, ??_7DelayLoadWinRtString@Js@@6B@; const Js::DelayLoadWinRtString::`vftable'
0x18030fb46  mov     [rcx], rax
0x18030fb49  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x18030fb4e  nop
0x18030fb4f  lea     rcx, [rdi+1EB0h]; lpCriticalSection
0x18030fb56  call    cs:__imp_DeleteCriticalSection
0x18030fb5d  nop     dword ptr [rax+rax+00h]
0x18030fb62  nop
0x18030fb63  mov     rcx, r15; this
0x18030fb66  call    ??1ArenaAllocator@Memory@@QEAA@XZ; Memory::ArenaAllocator::~ArenaAllocator(void)
0x18030fb6b  mov     rcx, r14; this
0x18030fb6e  call    ??1ArenaAllocator@Memory@@QEAA@XZ; Memory::ArenaAllocator::~ArenaAllocator(void)
0x18030fb73  mov     rcx, rbp
0x18030fb76  call    ??1?$BaseDictionary@IPEAV?$SList@PEBGVArenaAllocator@Memory@@VFakeCount@@@@VArenaAllocator@Memory@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@VNoResizeLock@7@@JsUtil@@QEAA@XZ; JsUtil::BaseDictionary<uint,SList<ushort const *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::~BaseDictionary<uint,SList<ushort const *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>(void)
0x18030fb7b  mov     rcx, rsi
0x18030fb7e  call    ??1?$BaseDictionary@IPEAV?$SList@PEBGVArenaAllocator@Memory@@VFakeCount@@@@VArenaAllocator@Memory@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@VNoResizeLock@7@@JsUtil@@QEAA@XZ; JsUtil::BaseDictionary<uint,SList<ushort const *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::~BaseDictionary<uint,SList<ushort const *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>(void)
0x18030fb83  mov     rcx, rbx
0x18030fb86  call    ??1?$BaseDictionary@IPEAV?$SList@PEBGVArenaAllocator@Memory@@VFakeCount@@@@VArenaAllocator@Memory@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@VNoResizeLock@7@@JsUtil@@QEAA@XZ; JsUtil::BaseDictionary<uint,SList<ushort const *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>::~BaseDictionary<uint,SList<ushort const *,Memory::ArenaAllocator,FakeCount> *,Memory::ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::NoResizeLock>(void)
0x18030fb8b  lea     rcx, [rdi+1C98h]
0x18030fb92  call    ??1?$ArenaAllocatorBase@VInPlaceFreeListPolicy@Memory@@$03$0A@$0A@@Memory@@QEAA@XZ; Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>(void)
0x18030fb97  lea     rcx, [rdi+1C38h]
0x18030fb9e  call    ??1?$ArenaAllocatorBase@VInPlaceFreeListPolicy@Memory@@$03$0A@$0A@@Memory@@QEAA@XZ; Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>(void)
0x18030fba3  lea     rcx, [rdi+1BD8h]
0x18030fbaa  call    ??1?$ArenaAllocatorBase@VInPlaceFreeListPolicy@Memory@@$03$0A@$0A@@Memory@@QEAA@XZ; Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>(void)
0x18030fbaf  lea     rcx, [rdi+0E88h]
0x18030fbb6  call    ??1?$JITThunkEmitter@VVirtualAllocWrapper@Memory@@@@QEAA@XZ; JITThunkEmitter<Memory::VirtualAllocWrapper>::~JITThunkEmitter<Memory::VirtualAllocWrapper>(void)
0x18030fbbb  lea     rcx, [rdi+0C40h]
0x18030fbc2  call    ??1?$CodePageAllocators@VVirtualAllocWrapper@Memory@@VPreReservedVirtualAllocWrapper@2@@CustomHeap@Memory@@QEAA@XZ; Memory::CustomHeap::CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>::~CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>(void)
0x18030fbc7  lea     rcx, [rdi+9F8h]
0x18030fbce  call    ??1?$CodePageAllocators@VVirtualAllocWrapper@Memory@@VPreReservedVirtualAllocWrapper@2@@CustomHeap@Memory@@QEAA@XZ; Memory::CustomHeap::CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>::~CodePageAllocators<Memory::VirtualAllocWrapper,Memory::PreReservedVirtualAllocWrapper>(void)
0x18030fbd3  lea     rcx, [rdi+950h]
0x18030fbda  call    ??1?$ArenaAllocatorBase@VInPlaceFreeListPolicy@Memory@@$03$0A@$0A@@Memory@@QEAA@XZ; Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>(void)
0x18030fbdf  lea     rcx, [rdi+518h]
0x18030fbe6  call    ??1?$SList@PEAVArrayBufferContentForDelayedFreeBase@Js@@UHeapAllocator@Memory@@VFakeCount@@@@QEAA@XZ; SList<Js::ArrayBufferContentForDelayedFreeBase *,Memory::HeapAllocator,FakeCount>::~SList<Js::ArrayBufferContentForDelayedFreeBase *,Memory::HeapAllocator,FakeCount>(void)
0x18030fbeb  lea     rcx, [rdi+3D0h]; this
0x18030fbf2  call    ??1IdleDecommitPageAllocator@Memory@@QEAA@XZ; Memory::IdleDecommitPageAllocator::~IdleDecommitPageAllocator(void)
0x18030fbf7  nop
0x18030fbf8  lea     rcx, [rdi+3A0h]; lpCriticalSection
0x18030fbff  call    cs:__imp_DeleteCriticalSection
0x18030fc06  nop     dword ptr [rax+rax+00h]
0x18030fc0b  nop
0x18030fc0c  lea     rcx, [rdi+158h]; this
0x18030fc13  call    ??1PreReservedVirtualAllocWrapper@Memory@@QEAA@XZ; Memory::PreReservedVirtualAllocWrapper::~PreReservedVirtualAllocWrapper(void)
0x18030fc18  lea     rcx, [rdi+10h]; this
0x18030fc1c  add     rsp, 38h
0x18030fc20  pop     r15
0x18030fc22  pop     r14
0x18030fc24  pop     r13
0x18030fc26  pop     r12
0x18030fc28  pop     rdi
0x18030fc29  pop     rsi
0x18030fc2a  pop     rbp
0x18030fc2b  pop     rbx
0x18030fc2c  jmp     ??1ThreadContextInfo@@QEAA@XZ; ThreadContextInfo::~ThreadContextInfo(void)
```
