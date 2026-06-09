# Js::ScriptContext::~ScriptContext(void)

- ea: `0x18033abb4`
- end: `0x18033aecc`
- name: `??1ScriptContext@Js@@QEAA@XZ`
- size: `792`
- prototype: `void __fastcall(Js::ScriptContext *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18033ab78`

## callees

- `0x1801508d4`
- `0x1801b1208`
- `0x1801b1280`
- `0x1801b1e88`
- `0x1801c8690`
- `0x1801c87b0`
- `0x1803202a0`
- `0x180320350`
- `0x18033abb4`
- `0x18033aed4`
- `0x18033af28`
- `0x18033b54c`
- `0x18033b750`
- `0x18033b790`
- `0x18039eca0`
- `0x1803b9324`
- `0x1803cff7c`
- `0x1803eaf20`
- `0x1803f4320`
- `0x1803f56b4`
- `0x18053db48`
- `0x18053e820`
- `0x180540080`
- `0x18055d010`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18033ae48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18033ae48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18033abee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18033abee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18033ae5c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18033ae5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Js::ScriptContext::~ScriptContext(Js::ScriptContext *this)
{
  __int64 v2; // rbp
  __int64 v3; // rcx
  void (__fastcall ***v4)(_QWORD); // rcx
  bool v5; // si
  __int64 v6; // rax
  void *v7; // rdx
  __int64 v8; // rcx
  void *v9; // rdx
  void *v10; // rbx
  void *v11; // rbx
  void *v12; // rdx

  *(_QWORD *)this = &Js::ScriptContext::`vftable';
  v2 = *((_QWORD *)this + 110);
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 8208));
  if ( *((_QWORD *)this + 216) )
    Memory::DeleteObject<Memory::HeapAllocator,0,JsUtil::BaseDictionary<__int64,enum IR::JnHelperMethod,Memory::HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::AsymetricResizeLock>>(v3);
  v4 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 183);
  if ( v4 )
    (**v4)(v4);
  if ( *((_BYTE *)this + 1526) )
  {
    ThreadContext::ClearInlineCaches(*((ThreadContext **)this + 110));
    Js::ScriptContext::ClearInlineCaches(this);
  }
  if ( *((_BYTE *)this + 1527) )
  {
    ThreadContext::ClearIsInstInlineCaches(*((ThreadContext **)this + 110));
    Js::ScriptContext::ClearIsInstInlineCaches(this);
  }
  if ( *((_BYTE *)this + 24) && !*((_BYTE *)this + 1521) )
    ThreadContext::RemoveFromPendingClose(*((ThreadContext **)this + 110), this);
  Js::ScriptContext::SetIsClosed(this);
  v5 = Js::ScriptContext::Close(this, 1);
  Memory::HeapBucketT<Memory::SmallFinalizableHeapBlockT<SmallAllocationBlockAttributes>>::RemoveAllocator(
    *((_QWORD *)this + 132) + 17832LL,
    (char *)this + 1016);
  *((_QWORD *)this + 132) = 0;
  Js::ScriptContext::ShutdownClearSourceLists(this);
  if ( *((_QWORD *)this + 124) )
  {
    Memory::DeleteObject<Memory::ArenaAllocator,0,UnifiedRegex::RegexStacks>((char *)this + 256);
    *((_QWORD *)this + 124) = 0;
  }
  v6 = *((_QWORD *)this + 1);
  if ( v6 )
  {
    *(_QWORD *)(v6 + 1088) = 0;
    if ( v5 )
    {
      v7 = (void *)*((_QWORD *)this + 2);
      if ( v7 )
      {
        if ( *(_BYTE *)(*((_QWORD *)this + 110) + 296LL) && !*(_QWORD *)(*((_QWORD *)this + 1) + 1096LL) )
          Memory::Recycler::RootRelease(*((Memory::Recycler **)this + 126), v7, 0);
      }
    }
    *((_QWORD *)this + 1) = 0;
  }
  if ( Js::ScriptContext::IsRegistered(this) )
    ThreadContext::UnregisterScriptContext(*((ThreadContext **)this + 110), this);
  v9 = (void *)*((_QWORD *)this + 196);
  if ( v9 )
  {
    Memory::HeapAllocator::Free((Memory::HeapAllocator *)&Memory::HeapAllocator::Instance, v9, 0x20u);
    *((_QWORD *)this + 196) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 145);
  if ( v10 )
  {
    NativeCodeGenerator::~NativeCodeGenerator(*((NativeCodeGenerator **)this + 145));
    Memory::HeapAllocator::Free((Memory::HeapAllocator *)&Memory::HeapAllocator::Instance, v10, 0xF8u);
    *((_QWORD *)this + 145) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 5);
  if ( v11 )
  {
    Js::JITPageAddrToFuncRangeCache::ClearCache(*((Js::JITPageAddrToFuncRangeCache **)this + 5));
    Memory::HeapAllocator::Free((Memory::HeapAllocator *)&Memory::HeapAllocator::Instance, v11, 0x10u);
    *((_QWORD *)this + 5) = 0;
  }
  if ( *((_QWORD *)this + 139) )
  {
    Memory::DeleteObject<Memory::HeapAllocator,0,InterpreterThunkEmitter>(v8);
    *((_QWORD *)this + 139) = 0;
  }
  if ( *((_QWORD *)this + 141) )
  {
    Memory::DeleteObject<Memory::HeapAllocator,0,InterpreterThunkEmitter>(v8);
    *((_QWORD *)this + 141) = 0;
  }
  v12 = (void *)*((_QWORD *)this + 142);
  if ( v12 )
  {
    Memory::HeapAllocator::Free((Memory::HeapAllocator *)&Memory::HeapAllocator::Instance, v12, 0x88u);
    *((_QWORD *)this + 142) = 0;
  }
  *((_QWORD *)this + 208) = (char *)this + 1664;
  if ( *((_QWORD *)this + 108) )
  {
    JITManager::CleanupScriptContext((JITManager *)&JITManager::s_jitManager, (void **)this + 108);
    *((_QWORD *)this + 108) = 0;
  }
  --*(_DWORD *)(*((_QWORD *)this + 110) + 13416LL);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 8208));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1576));
  Memory::ArenaAllocatorBase<Memory::StandAloneFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::StandAloneFreeListPolicy,4,0,0>((char *)this + 752);
  Memory::ArenaAllocatorBase<Memory::StandAloneFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::StandAloneFreeListPolicy,4,0,0>((char *)this + 656);
  Memory::ArenaAllocatorBase<Memory::InlineCacheFreeListPolicy,5,1,1024>::~ArenaAllocatorBase<Memory::InlineCacheFreeListPolicy,5,1,1024>((char *)this + 544);
  Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>((char *)this + 448);
  Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>((char *)this + 352);
  Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>((char *)this + 256);
  Js::ScriptContextOptimizationOverrideInfo::~ScriptContextOptimizationOverrideInfo((Js::ScriptContext *)((char *)this + 64));
}

```

## disassembly

```asm
0x18033abb4  mov     r11, rsp
0x18033abb7  mov     [r11+8], rcx
0x18033abbb  push    rsi
0x18033abbc  push    rdi
0x18033abbd  push    r14
0x18033abbf  sub     rsp, 30h
0x18033abc3  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x18033abcb  mov     [r11+10h], rbx
0x18033abcf  mov     [r11+18h], rbp
0x18033abd3  lea     rax, ??_7ScriptContext@Js@@6B@; const Js::ScriptContext::`vftable'
0x18033abda  mov     rdi, rcx
0x18033abdd  mov     [rcx], rax
0x18033abe0  mov     rbp, [rcx+370h]
0x18033abe7  lea     rcx, [rbp+2010h]; lpCriticalSection
0x18033abee  call    cs:__imp_EnterCriticalSection
0x18033abf5  nop     dword ptr [rax+rax+00h]
0x18033abfa  mov     rdx, [rdi+6C0h]
0x18033ac01  xor     r14d, r14d
0x18033ac04  test    rdx, rdx
0x18033ac07  jz      short loc_18033AC0E
0x18033ac09  call    ??$DeleteObject@UHeapAllocator@Memory@@$0A@V?$BaseDictionary@_JW4JnHelperMethod@IR@@UHeapAllocator@Memory@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@VAsymetricResizeLock@8@@JsUtil@@@Memory@@YAXPEAUHeapAllocator@0@PEAV?$BaseDictionary@_JW4JnHelperMethod@IR@@UHeapAllocator@Memory@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@VAsymetricResizeLock@8@@JsUtil@@@Z; Memory::DeleteObject<Memory::HeapAllocator,0,JsUtil::BaseDictionary<__int64,IR::JnHelperMethod,Memory::HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::AsymetricResizeLock>>(Memory::HeapAllocator *,JsUtil::BaseDictionary<__int64,IR::JnHelperMethod,Memory::HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry,JsUtil::AsymetricResizeLock> *)
0x18033ac0e  mov     rcx, [rdi+5B8h]
0x18033ac15  test    rcx, rcx
0x18033ac18  jz      short loc_18033AC25
0x18033ac1a  mov     rax, [rcx]
0x18033ac1d  mov     rax, [rax]
0x18033ac20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033ac25  cmp     [rdi+5F6h], r14b
0x18033ac2c  jz      short loc_18033AC42
0x18033ac2e  mov     rcx, [rdi+370h]; this
0x18033ac35  call    ?ClearInlineCaches@ThreadContext@@QEAAXXZ; ThreadContext::ClearInlineCaches(void)
0x18033ac3a  mov     rcx, rdi; this
0x18033ac3d  call    ?ClearInlineCaches@ScriptContext@Js@@QEAAXXZ; Js::ScriptContext::ClearInlineCaches(void)
0x18033ac42  cmp     [rdi+5F7h], r14b
0x18033ac49  jz      short loc_18033AC5F
0x18033ac4b  mov     rcx, [rdi+370h]; this
0x18033ac52  call    ?ClearIsInstInlineCaches@ThreadContext@@QEAAXXZ; ThreadContext::ClearIsInstInlineCaches(void)
0x18033ac57  mov     rcx, rdi; this
0x18033ac5a  call    ?ClearIsInstInlineCaches@ScriptContext@Js@@QEAAXXZ; Js::ScriptContext::ClearIsInstInlineCaches(void)
0x18033ac5f  cmp     [rdi+18h], r14b
0x18033ac63  jz      short loc_18033AC7D
0x18033ac65  cmp     [rdi+5F1h], r14b
0x18033ac6c  jnz     short loc_18033AC7D
0x18033ac6e  mov     rdx, rdi; struct Js::ScriptContext *
0x18033ac71  mov     rcx, [rdi+370h]; this
0x18033ac78  call    ?RemoveFromPendingClose@ThreadContext@@QEAAXPEAVScriptContext@Js@@@Z; ThreadContext::RemoveFromPendingClose(Js::ScriptContext *)
0x18033ac7d  mov     rcx, rdi; this
0x18033ac80  call    ?SetIsClosed@ScriptContext@Js@@QEAAXXZ; Js::ScriptContext::SetIsClosed(void)
0x18033ac85  mov     dl, 1; bool
0x18033ac87  mov     rcx, rdi; this
0x18033ac8a  call    ?Close@ScriptContext@Js@@QEAA_N_N@Z; Js::ScriptContext::Close(bool)
0x18033ac8f  mov     sil, al
0x18033ac92  lea     rbx, [rdi+3F8h]
0x18033ac99  mov     rcx, [rbx+28h]
0x18033ac9d  add     rcx, 45A8h
0x18033aca4  mov     rdx, rbx
0x18033aca7  call    ?RemoveAllocator@?$HeapBucketT@V?$SmallFinalizableHeapBlockT@VSmallAllocationBlockAttributes@@@Memory@@@Memory@@IEAAXPEAV?$SmallHeapBlockAllocator@V?$SmallFinalizableHeapBlockT@VSmallAllocationBlockAttributes@@@Memory@@@2@@Z; Memory::HeapBucketT<Memory::SmallFinalizableHeapBlockT<SmallAllocationBlockAttributes>>::RemoveAllocator(Memory::SmallHeapBlockAllocator<Memory::SmallFinalizableHeapBlockT<SmallAllocationBlockAttributes>> *)
0x18033acac  mov     [rbx+28h], r14
0x18033acb0  mov     rcx, rdi; this
0x18033acb3  call    ?ShutdownClearSourceLists@ScriptContext@Js@@QEAAXXZ; Js::ScriptContext::ShutdownClearSourceLists(void)
0x18033acb8  mov     rdx, [rdi+3E0h]
0x18033acbf  test    rdx, rdx
0x18033acc2  jz      short loc_18033ACD7
0x18033acc4  lea     rcx, [rdi+100h]
0x18033accb  call    ??$DeleteObject@VArenaAllocator@Memory@@$0A@URegexStacks@UnifiedRegex@@@Memory@@YAXPEAVArenaAllocator@0@PEAURegexStacks@UnifiedRegex@@@Z; Memory::DeleteObject<Memory::ArenaAllocator,0,UnifiedRegex::RegexStacks>(Memory::ArenaAllocator *,UnifiedRegex::RegexStacks *)
0x18033acd0  mov     [rdi+3E0h], r14
0x18033acd7  mov     rax, [rdi+8]
0x18033acdb  test    rax, rax
0x18033acde  jz      short loc_18033AD25
0x18033ace0  mov     [rax+440h], r14
0x18033ace7  test    sil, sil
0x18033acea  jz      short loc_18033AD21
0x18033acec  mov     rdx, [rdi+10h]; void *
0x18033acf0  test    rdx, rdx
0x18033acf3  jz      short loc_18033AD21
0x18033acf5  mov     rax, [rdi+370h]
0x18033acfc  cmp     [rax+128h], r14b
0x18033ad03  jz      short loc_18033AD21
0x18033ad05  mov     rax, [rdi+8]
0x18033ad09  cmp     [rax+448h], r14
0x18033ad10  jnz     short loc_18033AD21
0x18033ad12  xor     r8d, r8d; unsigned int *
0x18033ad15  mov     rcx, [rdi+3F0h]; this
0x18033ad1c  call    ?RootRelease@Recycler@Memory@@QEAAXPEAXPEAI@Z; Memory::Recycler::RootRelease(void *,uint *)
0x18033ad21  mov     [rdi+8], r14
0x18033ad25  mov     rcx, rdi; this
0x18033ad28  call    ?IsRegistered@ScriptContext@Js@@QEAA_NXZ; Js::ScriptContext::IsRegistered(void)
0x18033ad2d  test    al, al
0x18033ad2f  jz      short loc_18033AD40
0x18033ad31  mov     rdx, rdi; struct Js::ScriptContext *
0x18033ad34  mov     rcx, [rdi+370h]; this
0x18033ad3b  call    ?UnregisterScriptContext@ThreadContext@@QEAAXPEAVScriptContext@Js@@@Z; ThreadContext::UnregisterScriptContext(Js::ScriptContext *)
0x18033ad40  mov     rdx, [rdi+620h]; void *
0x18033ad47  lea     rsi, ?Instance@HeapAllocator@Memory@@2U12@A; Memory::HeapAllocator Memory::HeapAllocator::Instance
0x18033ad4e  test    rdx, rdx
0x18033ad51  jz      short loc_18033AD68
0x18033ad53  mov     r8d, 20h ; ' '; unsigned __int64
0x18033ad59  mov     rcx, rsi; this
0x18033ad5c  call    ?Free@HeapAllocator@Memory@@QEAAXPEAX_K@Z; Memory::HeapAllocator::Free(void *,unsigned __int64)
0x18033ad61  mov     [rdi+620h], r14
0x18033ad68  mov     rbx, [rdi+488h]
0x18033ad6f  test    rbx, rbx
0x18033ad72  jz      short loc_18033AD94
0x18033ad74  mov     rcx, rbx; this
0x18033ad77  call    ??1NativeCodeGenerator@@QEAA@XZ; NativeCodeGenerator::~NativeCodeGenerator(void)
0x18033ad7c  mov     r8d, 0F8h; unsigned __int64
0x18033ad82  mov     rdx, rbx; void *
0x18033ad85  mov     rcx, rsi; this
0x18033ad88  call    ?Free@HeapAllocator@Memory@@QEAAXPEAX_K@Z; Memory::HeapAllocator::Free(void *,unsigned __int64)
0x18033ad8d  mov     [rdi+488h], r14
0x18033ad94  mov     rbx, [rdi+28h]
0x18033ad98  test    rbx, rbx
0x18033ad9b  jz      short loc_18033ADBB
0x18033ad9d  mov     rcx, rbx; this
0x18033ada0  call    ?ClearCache@JITPageAddrToFuncRangeCache@Js@@QEAAXXZ; Js::JITPageAddrToFuncRangeCache::ClearCache(void)
0x18033ada5  nop
0x18033ada6  mov     r8d, 10h; unsigned __int64
0x18033adac  mov     rdx, rbx; void *
0x18033adaf  mov     rcx, rsi; this
0x18033adb2  call    ?Free@HeapAllocator@Memory@@QEAAXPEAX_K@Z; Memory::HeapAllocator::Free(void *,unsigned __int64)
0x18033adb7  mov     [rdi+28h], r14
0x18033adbb  mov     rdx, [rdi+458h]
0x18033adc2  test    rdx, rdx
0x18033adc5  jz      short loc_18033ADD3
0x18033adc7  call    ??$DeleteObject@UHeapAllocator@Memory@@$0A@VInterpreterThunkEmitter@@@Memory@@YAXPEAUHeapAllocator@0@PEAVInterpreterThunkEmitter@@@Z; Memory::DeleteObject<Memory::HeapAllocator,0,InterpreterThunkEmitter>(Memory::HeapAllocator *,InterpreterThunkEmitter *)
0x18033adcc  mov     [rdi+458h], r14
0x18033add3  mov     rdx, [rdi+468h]
0x18033adda  test    rdx, rdx
0x18033addd  jz      short loc_18033ADEB
0x18033addf  call    ??$DeleteObject@UHeapAllocator@Memory@@$0A@VInterpreterThunkEmitter@@@Memory@@YAXPEAUHeapAllocator@0@PEAVInterpreterThunkEmitter@@@Z; Memory::DeleteObject<Memory::HeapAllocator,0,InterpreterThunkEmitter>(Memory::HeapAllocator *,InterpreterThunkEmitter *)
0x18033ade4  mov     [rdi+468h], r14
0x18033adeb  mov     rdx, [rdi+470h]; void *
0x18033adf2  test    rdx, rdx
0x18033adf5  jz      short loc_18033AE0C
0x18033adf7  mov     r8d, 88h; unsigned __int64
0x18033adfd  mov     rcx, rsi; this
0x18033ae00  call    ?Free@HeapAllocator@Memory@@QEAAXPEAX_K@Z; Memory::HeapAllocator::Free(void *,unsigned __int64)
0x18033ae05  mov     [rdi+470h], r14
0x18033ae0c  lea     rax, [rdi+680h]
0x18033ae13  mov     [rax], rax
0x18033ae16  lea     rbx, [rdi+360h]
0x18033ae1d  cmp     [rbx], r14
0x18033ae20  jz      short loc_18033AE34
0x18033ae22  mov     rdx, rbx; void **
0x18033ae25  lea     rcx, ?s_jitManager@JITManager@@0V1@A; this
0x18033ae2c  call    ?CleanupScriptContext@JITManager@@QEAAJPEAPEAX@Z; JITManager::CleanupScriptContext(void * *)
0x18033ae31  mov     [rbx], r14
0x18033ae34  mov     rax, [rdi+370h]
0x18033ae3b  dec     dword ptr [rax+3468h]
0x18033ae41  lea     rcx, [rbp+2010h]; lpCriticalSection
0x18033ae48  call    cs:__imp_LeaveCriticalSection
0x18033ae4f  nop     dword ptr [rax+rax+00h]
0x18033ae54  nop
0x18033ae55  lea     rcx, [rdi+628h]; lpCriticalSection
0x18033ae5c  call    cs:__imp_DeleteCriticalSection
0x18033ae63  nop     dword ptr [rax+rax+00h]
0x18033ae68  nop
0x18033ae69  lea     rcx, [rdi+2F0h]
0x18033ae70  call    ??1?$ArenaAllocatorBase@VStandAloneFreeListPolicy@Memory@@$03$0A@$0A@@Memory@@QEAA@XZ; Memory::ArenaAllocatorBase<Memory::StandAloneFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::StandAloneFreeListPolicy,4,0,0>(void)
0x18033ae75  lea     rcx, [rdi+290h]
0x18033ae7c  call    ??1?$ArenaAllocatorBase@VStandAloneFreeListPolicy@Memory@@$03$0A@$0A@@Memory@@QEAA@XZ; Memory::ArenaAllocatorBase<Memory::StandAloneFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::StandAloneFreeListPolicy,4,0,0>(void)
0x18033ae81  lea     rcx, [rdi+220h]
0x18033ae88  call    ??1?$ArenaAllocatorBase@VInlineCacheFreeListPolicy@Memory@@$04$00$0EAA@@Memory@@QEAA@XZ; Memory::ArenaAllocatorBase<Memory::InlineCacheFreeListPolicy,5,1,1024>::~ArenaAllocatorBase<Memory::InlineCacheFreeListPolicy,5,1,1024>(void)
0x18033ae8d  lea     rcx, [rdi+1C0h]
0x18033ae94  call    ??1?$ArenaAllocatorBase@VInPlaceFreeListPolicy@Memory@@$03$0A@$0A@@Memory@@QEAA@XZ; Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>(void)
0x18033ae99  lea     rcx, [rdi+160h]
0x18033aea0  call    ??1?$ArenaAllocatorBase@VInPlaceFreeListPolicy@Memory@@$03$0A@$0A@@Memory@@QEAA@XZ; Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>(void)
0x18033aea5  lea     rcx, [rdi+100h]
0x18033aeac  call    ??1?$ArenaAllocatorBase@VInPlaceFreeListPolicy@Memory@@$03$0A@$0A@@Memory@@QEAA@XZ; Memory::ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>::~ArenaAllocatorBase<Memory::InPlaceFreeListPolicy,4,0,0>(void)
0x18033aeb1  lea     rcx, [rdi+40h]; this
0x18033aeb5  mov     rbx, [rsp+48h+arg_8]
0x18033aeba  mov     rbp, [rsp+48h+arg_10]
0x18033aebf  add     rsp, 30h
0x18033aec3  pop     r14
0x18033aec5  pop     rdi
0x18033aec6  pop     rsi
0x18033aec7  jmp     ??1ScriptContextOptimizationOverrideInfo@Js@@QEAA@XZ; Js::ScriptContextOptimizationOverrideInfo::~ScriptContextOptimizationOverrideInfo(void)
```
