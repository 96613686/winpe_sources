# ThreadContext::~ThreadContext(void)

- ea: `0x1802b2d98`
- end: `0x1802b3161`
- name: `??1ThreadContext@@QEAA@XZ`
- size: `969`
- prototype: `void __fastcall(ThreadContext *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18020666c`

## callees

- `0x180022ab4`
- `0x18009092c`
- `0x1800b5248`
- `0x1800c4538`
- `0x18013674c`
- `0x180171570`
- `0x18018f81c`
- `0x1801a48e8`
- `0x1801a9140`
- `0x1801ace6c`
- `0x1802b278c`
- `0x1802b27c0`
- `0x1802b27f4`
- `0x1802b2828`
- `0x1802b2d98`
- `0x1802b3168`
- `0x1802b31c8`

## import_xrefs

- `msvcrt!free` at `0x1802b2e5d`
- `msvcrt!free` at `0x1802b2f20`
- `msvcrt!free` at `0x1802b2f45`
- `msvcrt!free` at `0x1802b2f6b`
- `msvcrt!free` at `0x1802b2e5d`
- `msvcrt!free` at `0x1802b2f20`
- `msvcrt!free` at `0x1802b2f45`
- `msvcrt!free` at `0x1802b2f6b`
- `KERNEL32!DeleteCriticalSection` at `0x1802b3034`
- `KERNEL32!DeleteCriticalSection` at `0x1802b30de`
- `KERNEL32!DeleteCriticalSection` at `0x1802b313c`
- `KERNEL32!DeleteCriticalSection` at `0x1802b3034`
- `KERNEL32!DeleteCriticalSection` at `0x1802b30de`
- `KERNEL32!DeleteCriticalSection` at `0x1802b313c`
- `KERNEL32!EnterCriticalSection` at `0x1802b2dcf`
- `KERNEL32!EnterCriticalSection` at `0x1802b2dcf`
- `KERNEL32!LeaveCriticalSection` at `0x1802b2e44`
- `KERNEL32!LeaveCriticalSection` at `0x1802b2e44`
- `ADVAPI32!CryptReleaseContext` at `0x1802b3001`
- `ADVAPI32!CryptReleaseContext` at `0x1802b3001`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ThreadContext::~ThreadContext(ThreadContext *this)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  _QWORD *v4; // rcx
  __int64 v5; // rax
  void *v6; // rcx
  void *v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  void *v10; // rcx
  _QWORD *v11; // rsi
  _QWORD *i; // rcx
  _QWORD *v13; // rbx
  _QWORD *v14; // rsi
  _QWORD *j; // rcx
  _QWORD *v16; // rbx
  HCRYPTPROV v17; // rcx

  *(_QWORD *)this = &ThreadContext::`vftable';
  EnterCriticalSection(&ThreadContext::s_csThreadContext);
  v2 = *((_QWORD *)this + 1);
  v3 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    *(_QWORD *)(v2 + 8) = v3;
  }
  else if ( v3 )
  {
    ThreadContext::globalListFirst = (struct ThreadContext *)(v3 - 8);
  }
  else
  {
    ThreadContext::globalListFirst = 0;
  }
  v4 = (_QWORD *)*((_QWORD *)this + 2);
  v5 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    *v4 = v5;
  }
  else if ( v5 )
  {
    ThreadContext::globalListLast = (struct ThreadContext *)(v5 - 8);
  }
  else
  {
    ThreadContext::globalListLast = 0;
  }
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  LeaveCriticalSection(&ThreadContext::s_csThreadContext);
  v6 = (void *)*((_QWORD *)this + 1745);
  if ( v6 )
  {
    free(v6);
    *((_QWORD *)this + 1745) = 0;
  }
  *((_BYTE *)this + 524) = 1;
  *((_BYTE *)this + 276) = 1;
  if ( *((_QWORD *)this + 72) )
  {
    *(_QWORD *)(*((_QWORD *)this + 228) + 448LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 228) + 472LL) = 0;
    v7 = (void *)*((_QWORD *)this + 74);
    if ( v7 )
    {
      DeleteObject<HeapAllocator,JsUtil::BaseHashSet<Js::PropertyRecord const *,HeapAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,Js::PropertyRecord const *,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry>>(
        (__int64)v6,
        v7);
      *((_QWORD *)this + 74) = 0;
    }
    Recycler::RootRelease(*((Recycler **)this + 72), *((_QWORD *)this + 228), 0);
    *((_QWORD *)this + 228) = 0;
    DeleteObject<HeapAllocator,CodeGenNumberThreadAllocator>(v8, *((CodeGenNumberThreadAllocator **)this + 227));
    *((_QWORD *)this + 227) = 0;
    DeleteObject<HeapAllocator,Recycler>(v9, *((Recycler **)this + 72));
  }
  v10 = (void *)*((_QWORD *)this + 225);
  if ( v10 )
  {
    if ( *((_BYTE *)this + 8378) )
      DeleteObject<HeapAllocator,JsUtil::BackgroundJobProcessor>(
        (__int64)v10,
        *((JsUtil::BackgroundJobProcessor **)this + 225));
    else
      free(v10);
    *((_QWORD *)this + 225) = 0;
  }
  v11 = (_QWORD *)((char *)this + 1792);
  for ( i = (_QWORD *)*((_QWORD *)this + 224); i != v11; i = v13 )
  {
    v13 = (_QWORD *)*i;
    free(i);
  }
  *v11 = v11;
  v14 = (_QWORD *)((char *)this + 8320);
  for ( j = (_QWORD *)*((_QWORD *)this + 1040); j != v14; j = v16 )
  {
    v16 = (_QWORD *)*j;
    free(j);
  }
  *v14 = v14;
  *((_QWORD *)this + 1041) = (char *)this + 8320;
  HashTable<Js::InlineCache *,ArenaAllocator>::Init((__int64)this + 2064);
  HashTable<Js::InlineCache *,ArenaAllocator>::Init((__int64)this + 6088);
  *((_QWORD *)this + 1020) = 0;
  *((_QWORD *)this + 1021) = 0;
  *((_QWORD *)this + 1022) = 0;
  *((_QWORD *)this + 1023) = 0;
  *((_DWORD *)this + 2048) = 0;
  *((_QWORD *)this + 256) = (char *)this + 2048;
  *((_QWORD *)this + 257) = (char *)this + 2048;
  *((_QWORD *)this + 1038) = (char *)this + 8304;
  *((_QWORD *)this + 1039) = (char *)this + 8304;
  if ( *((_QWORD *)this + 3) )
    *((_QWORD *)this + 3) = 0;
  _InterlockedAdd64((volatile signed __int64 *)&ThreadContext::processNativeCodeSize, -*((_QWORD *)this + 231));
  v17 = *((_QWORD *)this + 73);
  if ( v17 )
  {
    CryptReleaseContext(v17, 0);
    *((_QWORD *)this + 73) = 0;
  }
  JsUtil::BaseDictionary<Js::FunctionProxy *,Js::FunctionProxy *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleHashedEntry>::~BaseDictionary<Js::FunctionProxy *,Js::FunctionProxy *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleHashedEntry>((int *)this + 3492);
  JsUtil::BaseDictionary<Js::PropertyRecord const *,Js::PropertyRecord const *,HeapAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry>::~BaseDictionary<Js::PropertyRecord const *,Js::PropertyRecord const *,HeapAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry>((__int64)this + 13840);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8856));
  Js::WindowsFoundationAdapter::~WindowsFoundationAdapter((ThreadContext *)((char *)this + 8784));
  *((_QWORD *)this + 1094) = &Js::DelayLoadWinRtFoundation::`vftable';
  DelayLoadLibrary::~DelayLoadLibrary((ThreadContext *)((char *)this + 8752));
  Js::WindowsGlobalizationAdapter::~WindowsGlobalizationAdapter((ThreadContext *)((char *)this + 8680));
  *((_QWORD *)this + 1073) = &Js::DelayLoadWinRtString::`vftable';
  DelayLoadLibrary::~DelayLoadLibrary((ThreadContext *)((char *)this + 8584));
  *((_QWORD *)this + 1069) = &Js::DelayLoadWinRtRoParameterizedIID::`vftable';
  DelayLoadLibrary::~DelayLoadLibrary((ThreadContext *)((char *)this + 8552));
  *((_QWORD *)this + 1065) = &Js::DelayLoadWinRtTypeResolution::`vftable';
  DelayLoadLibrary::~DelayLoadLibrary((ThreadContext *)((char *)this + 8520));
  *((_QWORD *)this + 1060) = &Js::DelayLoadWinRtError::`vftable';
  DelayLoadLibrary::~DelayLoadLibrary((ThreadContext *)((char *)this + 8480));
  *((_QWORD *)this + 1051) = &Js::DelayLoadWinRtString::`vftable';
  DelayLoadLibrary::~DelayLoadLibrary((ThreadContext *)((char *)this + 8408));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8336));
  ArenaAllocatorBase<InPlaceFreeListPolicy>::~ArenaAllocatorBase<InPlaceFreeListPolicy>((__int64)this + 8208);
  JsUtil::BaseDictionary<int,StackSym *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::~BaseDictionary<int,StackSym *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>((int *)this + 2040);
  HashTable<ObjTypeGuardBucket,ArenaAllocator>::~HashTable<ObjTypeGuardBucket,ArenaAllocator>((__int64)this + 6088);
  HashTable<ObjTypeGuardBucket,ArenaAllocator>::~HashTable<ObjTypeGuardBucket,ArenaAllocator>((__int64)this + 2064);
  ArenaAllocatorBase<InPlaceFreeListPolicy>::~ArenaAllocatorBase<InPlaceFreeListPolicy>((__int64)this + 1952);
  ArenaAllocatorBase<InPlaceFreeListPolicy>::~ArenaAllocatorBase<InPlaceFreeListPolicy>((__int64)this + 1664);
  PageAllocator::~PageAllocator((ThreadContext *)((char *)this + 408));
  IdleDecommitPageAllocator::~IdleDecommitPageAllocator((struct _RTL_CRITICAL_SECTION *)this + 4);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
}

```

## disassembly

```asm
0x1802b2d98  mov     r11, rsp
0x1802b2d9b  mov     [r11+8], rcx
0x1802b2d9f  push    rsi
0x1802b2da0  push    rdi
0x1802b2da1  push    r12
0x1802b2da3  push    r14
0x1802b2da5  push    r15
0x1802b2da7  sub     rsp, 30h
0x1802b2dab  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x1802b2db3  mov     [r11+10h], rbx
0x1802b2db7  mov     [r11+18h], rbp
0x1802b2dbb  lea     rax, ??_7ThreadContext@@6B@; const ThreadContext::`vftable'
0x1802b2dc2  mov     rdi, rcx
0x1802b2dc5  mov     [rcx], rax
0x1802b2dc8  lea     rcx, ?s_csThreadContext@ThreadContext@@0VCriticalSection@@A; lpCriticalSection
0x1802b2dcf  call    cs:__imp_EnterCriticalSection
0x1802b2dd6  nop     dword ptr [rax+rax+00h]
0x1802b2ddb  mov     rcx, [rdi+8]
0x1802b2ddf  mov     rax, [rdi+10h]
0x1802b2de3  xor     r12d, r12d
0x1802b2de6  test    rcx, rcx
0x1802b2de9  jz      short loc_1802B2DF1
0x1802b2deb  mov     [rcx+8], rax
0x1802b2def  jmp     short loc_1802B2E0A
0x1802b2df1  test    rax, rax
0x1802b2df4  jz      short loc_1802B2E03
0x1802b2df6  add     rax, 0FFFFFFFFFFFFFFF8h
0x1802b2dfa  mov     cs:?globalListFirst@ThreadContext@@2PEAV1@EA, rax; ThreadContext * ThreadContext::globalListFirst
0x1802b2e01  jmp     short loc_1802B2E0A
0x1802b2e03  mov     cs:?globalListFirst@ThreadContext@@2PEAV1@EA, r12; ThreadContext * ThreadContext::globalListFirst
0x1802b2e0a  mov     rcx, [rdi+10h]
0x1802b2e0e  mov     rax, [rdi+8]
0x1802b2e12  test    rcx, rcx
0x1802b2e15  jz      short loc_1802B2E1C
0x1802b2e17  mov     [rcx], rax
0x1802b2e1a  jmp     short loc_1802B2E35
0x1802b2e1c  test    rax, rax
0x1802b2e1f  jz      short loc_1802B2E2E
0x1802b2e21  add     rax, 0FFFFFFFFFFFFFFF8h
0x1802b2e25  mov     cs:?globalListLast@ThreadContext@@0PEAV1@EA, rax; ThreadContext * ThreadContext::globalListLast
0x1802b2e2c  jmp     short loc_1802B2E35
0x1802b2e2e  mov     cs:?globalListLast@ThreadContext@@0PEAV1@EA, r12; ThreadContext * ThreadContext::globalListLast
0x1802b2e35  mov     [rdi+8], r12
0x1802b2e39  mov     [rdi+10h], r12
0x1802b2e3d  lea     rcx, ?s_csThreadContext@ThreadContext@@0VCriticalSection@@A; lpCriticalSection
0x1802b2e44  call    cs:__imp_LeaveCriticalSection
0x1802b2e4b  nop     dword ptr [rax+rax+00h]
0x1802b2e50  nop
0x1802b2e51  mov     rcx, [rdi+3688h]; Block
0x1802b2e58  test    rcx, rcx
0x1802b2e5b  jz      short loc_1802B2E70
0x1802b2e5d  call    cs:__imp_free
0x1802b2e64  nop     dword ptr [rax+rax+00h]
0x1802b2e69  mov     [rdi+3688h], r12
0x1802b2e70  lea     r14, [rdi+198h]
0x1802b2e77  mov     byte ptr [r14+74h], 1
0x1802b2e7c  lea     r15, [rdi+0A0h]
0x1802b2e83  mov     byte ptr [r15+74h], 1
0x1802b2e88  cmp     [rdi+240h], r12
0x1802b2e8f  jz      short loc_1802B2F01
0x1802b2e91  mov     rax, [rdi+720h]
0x1802b2e98  mov     [rax+1C0h], r12
0x1802b2e9f  mov     rax, [rdi+720h]
0x1802b2ea6  mov     [rax+1D8h], r12
0x1802b2ead  mov     rdx, [rdi+250h]
0x1802b2eb4  test    rdx, rdx
0x1802b2eb7  jz      short loc_1802B2EC5
0x1802b2eb9  call    ??$DeleteObject@UHeapAllocator@@V?$BaseHashSet@PEBVPropertyRecord@Js@@UHeapAllocator@@U?$DictionarySizePolicy@UPrimePolicy@@$01$01$00$03@@PEBV12@UPropertyRecordStringHashComparer@2@VSimpleHashedEntry@JsUtil@@@JsUtil@@@@YAXPEAUHeapAllocator@@PEAV?$BaseHashSet@PEBVPropertyRecord@Js@@UHeapAllocator@@U?$DictionarySizePolicy@UPrimePolicy@@$01$01$00$03@@PEBV12@UPropertyRecordStringHashComparer@2@VSimpleHashedEntry@JsUtil@@@JsUtil@@@Z; DeleteObject<HeapAllocator,JsUtil::BaseHashSet<Js::PropertyRecord const *,HeapAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,Js::PropertyRecord const *,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry>>(HeapAllocator *,JsUtil::BaseHashSet<Js::PropertyRecord const *,HeapAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,Js::PropertyRecord const *,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry> *)
0x1802b2ebe  mov     [rdi+250h], r12
0x1802b2ec5  xor     r8d, r8d; unsigned int *
0x1802b2ec8  mov     rdx, [rdi+720h]; void *
0x1802b2ecf  mov     rcx, [rdi+240h]; this
0x1802b2ed6  call    ?RootRelease@Recycler@@QEAAXPEAXPEAI@Z; Recycler::RootRelease(void *,uint *)
0x1802b2edb  mov     [rdi+720h], r12
0x1802b2ee2  mov     rdx, [rdi+718h]
0x1802b2ee9  call    ??$DeleteObject@UHeapAllocator@@VCodeGenNumberThreadAllocator@@@@YAXPEAUHeapAllocator@@PEAVCodeGenNumberThreadAllocator@@@Z; DeleteObject<HeapAllocator,CodeGenNumberThreadAllocator>(HeapAllocator *,CodeGenNumberThreadAllocator *)
0x1802b2eee  mov     [rdi+718h], r12
0x1802b2ef5  mov     rdx, [rdi+240h]
0x1802b2efc  call    ??$DeleteObject@UHeapAllocator@@VRecycler@@@@YAXPEAUHeapAllocator@@PEAVRecycler@@@Z; DeleteObject<HeapAllocator,Recycler>(HeapAllocator *,Recycler *)
0x1802b2f01  mov     rcx, [rdi+708h]; Block
0x1802b2f08  test    rcx, rcx
0x1802b2f0b  jz      short loc_1802B2F33
0x1802b2f0d  cmp     [rdi+20BAh], r12b
0x1802b2f14  jz      short loc_1802B2F20
0x1802b2f16  mov     rdx, rcx
0x1802b2f19  call    ??$DeleteObject@UHeapAllocator@@VBackgroundJobProcessor@JsUtil@@@@YAXPEAUHeapAllocator@@PEAVBackgroundJobProcessor@JsUtil@@@Z; DeleteObject<HeapAllocator,JsUtil::BackgroundJobProcessor>(HeapAllocator *,JsUtil::BackgroundJobProcessor *)
0x1802b2f1e  jmp     short loc_1802B2F2C
0x1802b2f20  call    cs:__imp_free
0x1802b2f27  nop     dword ptr [rax+rax+00h]
0x1802b2f2c  mov     [rdi+708h], r12
0x1802b2f33  lea     rsi, [rdi+700h]
0x1802b2f3a  mov     rcx, [rsi]; Block
0x1802b2f3d  cmp     rcx, rsi
0x1802b2f40  jz      short loc_1802B2F56
0x1802b2f42  mov     rbx, [rcx]
0x1802b2f45  call    cs:__imp_free
0x1802b2f4c  nop     dword ptr [rax+rax+00h]
0x1802b2f51  mov     rcx, rbx
0x1802b2f54  jmp     short loc_1802B2F3D
0x1802b2f56  mov     [rsi], rsi
0x1802b2f59  lea     rsi, [rdi+2080h]
0x1802b2f60  mov     rcx, [rsi]; Block
0x1802b2f63  cmp     rcx, rsi
0x1802b2f66  jz      short loc_1802B2F7C
0x1802b2f68  mov     rbx, [rcx]
0x1802b2f6b  call    cs:__imp_free
0x1802b2f72  nop     dword ptr [rax+rax+00h]
0x1802b2f77  mov     rcx, rbx
0x1802b2f7a  jmp     short loc_1802B2F63
0x1802b2f7c  mov     [rsi], rsi
0x1802b2f7f  mov     [rsi+8], rsi
0x1802b2f83  lea     rsi, [rdi+810h]
0x1802b2f8a  mov     rcx, rsi
0x1802b2f8d  call    ?Init@?$HashTable@PEAUInlineCache@Js@@VArenaAllocator@@@@IEAAXXZ; HashTable<Js::InlineCache *,ArenaAllocator>::Init(void)
0x1802b2f92  lea     rbp, [rdi+17C8h]
0x1802b2f99  mov     rcx, rbp
0x1802b2f9c  call    ?Init@?$HashTable@PEAUInlineCache@Js@@VArenaAllocator@@@@IEAAXXZ; HashTable<Js::InlineCache *,ArenaAllocator>::Init(void)
0x1802b2fa1  lea     rbx, [rdi+1FE0h]
0x1802b2fa8  mov     [rbx], r12
0x1802b2fab  mov     [rbx+8], r12
0x1802b2faf  mov     [rbx+10h], r12
0x1802b2fb3  mov     [rbx+18h], r12
0x1802b2fb7  mov     [rbx+20h], r12d
0x1802b2fbb  lea     rax, [rdi+800h]
0x1802b2fc2  mov     [rax], rax
0x1802b2fc5  mov     [rax+8], rax
0x1802b2fc9  lea     rax, [rdi+2070h]
0x1802b2fd0  mov     [rax], rax
0x1802b2fd3  mov     [rax+8], rax
0x1802b2fd7  cmp     [rdi+18h], r12
0x1802b2fdb  jz      short loc_1802B2FE1
0x1802b2fdd  mov     [rdi+18h], r12
0x1802b2fe1  mov     rax, [rdi+738h]
0x1802b2fe8  neg     rax
0x1802b2feb  lock add cs:?processNativeCodeSize@ThreadContext@@0_KA, rax; unsigned __int64 ThreadContext::processNativeCodeSize
0x1802b2ff3  mov     rcx, [rdi+248h]; hProv
0x1802b2ffa  test    rcx, rcx
0x1802b2ffd  jz      short loc_1802B3014
0x1802b2fff  xor     edx, edx; dwFlags
0x1802b3001  call    cs:__imp_CryptReleaseContext
0x1802b3008  nop     dword ptr [rax+rax+00h]
0x1802b300d  mov     [rdi+248h], r12
0x1802b3014  lea     rcx, [rdi+3690h]
0x1802b301b  call    ??1?$BaseDictionary@PEAVFunctionProxy@Js@@PEAV12@VArenaAllocator@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleHashedEntry@JsUtil@@@JsUtil@@QEAA@XZ; JsUtil::BaseDictionary<Js::FunctionProxy *,Js::FunctionProxy *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleHashedEntry>::~BaseDictionary<Js::FunctionProxy *,Js::FunctionProxy *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleHashedEntry>(void)
0x1802b3020  lea     rcx, [rdi+3610h]
0x1802b3027  call    ??1?$BaseDictionary@PEBVPropertyRecord@Js@@PEBV12@UHeapAllocator@@U?$DictionarySizePolicy@UPrimePolicy@@$01$01$00$03@@UPropertyRecordStringHashComparer@2@VSimpleHashedEntry@JsUtil@@@JsUtil@@QEAA@XZ; JsUtil::BaseDictionary<Js::PropertyRecord const *,Js::PropertyRecord const *,HeapAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry>::~BaseDictionary<Js::PropertyRecord const *,Js::PropertyRecord const *,HeapAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry>(void)
0x1802b302c  nop
0x1802b302d  lea     rcx, [rdi+2298h]; lpCriticalSection
0x1802b3034  call    cs:__imp_DeleteCriticalSection
0x1802b303b  nop     dword ptr [rax+rax+00h]
0x1802b3040  nop
0x1802b3041  lea     rcx, [rdi+2250h]; this
0x1802b3048  call    ??1WindowsFoundationAdapter@Js@@QEAA@XZ; Js::WindowsFoundationAdapter::~WindowsFoundationAdapter(void)
0x1802b304d  lea     rcx, [rdi+2230h]; this
0x1802b3054  lea     rax, ??_7DelayLoadWinRtFoundation@Js@@6B@; const Js::DelayLoadWinRtFoundation::`vftable'
0x1802b305b  mov     [rcx], rax
0x1802b305e  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x1802b3063  lea     rcx, [rdi+21E8h]; this
0x1802b306a  call    ??1WindowsGlobalizationAdapter@Js@@QEAA@XZ; Js::WindowsGlobalizationAdapter::~WindowsGlobalizationAdapter(void)
0x1802b306f  lea     rcx, [rdi+2188h]; this
0x1802b3076  lea     r12, ??_7DelayLoadWinRtString@Js@@6B@; const Js::DelayLoadWinRtString::`vftable'
0x1802b307d  mov     [rcx], r12
0x1802b3080  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x1802b3085  lea     rcx, [rdi+2168h]; this
0x1802b308c  lea     rax, ??_7DelayLoadWinRtRoParameterizedIID@Js@@6B@; const Js::DelayLoadWinRtRoParameterizedIID::`vftable'
0x1802b3093  mov     [rcx], rax
0x1802b3096  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x1802b309b  lea     rcx, [rdi+2148h]; this
0x1802b30a2  lea     rax, ??_7DelayLoadWinRtTypeResolution@Js@@6B@; const Js::DelayLoadWinRtTypeResolution::`vftable'
0x1802b30a9  mov     [rcx], rax
0x1802b30ac  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x1802b30b1  lea     rcx, [rdi+2120h]; this
0x1802b30b8  lea     rax, ??_7DelayLoadWinRtError@Js@@6B@; const Js::DelayLoadWinRtError::`vftable'
0x1802b30bf  mov     [rcx], rax
0x1802b30c2  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x1802b30c7  lea     rcx, [rdi+20D8h]; this
0x1802b30ce  mov     [rcx], r12
0x1802b30d1  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x1802b30d6  nop
0x1802b30d7  lea     rcx, [rdi+2090h]; lpCriticalSection
0x1802b30de  call    cs:__imp_DeleteCriticalSection
0x1802b30e5  nop     dword ptr [rax+rax+00h]
0x1802b30ea  nop
0x1802b30eb  lea     rcx, [rdi+2010h]
0x1802b30f2  call    ??1?$ArenaAllocatorBase@VInPlaceFreeListPolicy@@@@QEAA@XZ; ArenaAllocatorBase<InPlaceFreeListPolicy>::~ArenaAllocatorBase<InPlaceFreeListPolicy>(void)
0x1802b30f7  mov     rcx, rbx
0x1802b30fa  call    ??1?$BaseDictionary@HPEAVStackSym@@VArenaAllocator@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@@JsUtil@@QEAA@XZ; JsUtil::BaseDictionary<int,StackSym *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::~BaseDictionary<int,StackSym *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>(void)
0x1802b30ff  mov     rcx, rbp
0x1802b3102  call    ??1?$HashTable@VObjTypeGuardBucket@@VArenaAllocator@@@@QEAA@XZ; HashTable<ObjTypeGuardBucket,ArenaAllocator>::~HashTable<ObjTypeGuardBucket,ArenaAllocator>(void)
0x1802b3107  mov     rcx, rsi
0x1802b310a  call    ??1?$HashTable@VObjTypeGuardBucket@@VArenaAllocator@@@@QEAA@XZ; HashTable<ObjTypeGuardBucket,ArenaAllocator>::~HashTable<ObjTypeGuardBucket,ArenaAllocator>(void)
0x1802b310f  lea     rcx, [rdi+7A0h]
0x1802b3116  call    ??1?$ArenaAllocatorBase@VInPlaceFreeListPolicy@@@@QEAA@XZ; ArenaAllocatorBase<InPlaceFreeListPolicy>::~ArenaAllocatorBase<InPlaceFreeListPolicy>(void)
0x1802b311b  lea     rcx, [rdi+680h]
0x1802b3122  call    ??1?$ArenaAllocatorBase@VInPlaceFreeListPolicy@@@@QEAA@XZ; ArenaAllocatorBase<InPlaceFreeListPolicy>::~ArenaAllocatorBase<InPlaceFreeListPolicy>(void)
0x1802b3127  mov     rcx, r14; this
0x1802b312a  call    ??1PageAllocator@@UEAA@XZ; PageAllocator::~PageAllocator(void)
0x1802b312f  mov     rcx, r15; this
0x1802b3132  call    ??1IdleDecommitPageAllocator@@UEAA@XZ; IdleDecommitPageAllocator::~IdleDecommitPageAllocator(void)
0x1802b3137  nop
0x1802b3138  lea     rcx, [rdi+70h]; lpCriticalSection
0x1802b313c  call    cs:__imp_DeleteCriticalSection
0x1802b3143  nop     dword ptr [rax+rax+00h]
0x1802b3148  nop
0x1802b3149  mov     rbx, [rsp+58h+arg_8]
0x1802b314e  mov     rbp, [rsp+58h+arg_10]
0x1802b3153  add     rsp, 30h
0x1802b3157  pop     r15
0x1802b3159  pop     r14
0x1802b315b  pop     r12
0x1802b315d  pop     rdi
0x1802b315e  pop     rsi
0x1802b315f  retn
```
