# ThreadContext::~ThreadContext(void)

- ea: `0x1802adafc`
- end: `0x1802ade88`
- name: `??1ThreadContext@@QEAA@XZ`
- size: `908`
- prototype: `void __fastcall(ThreadContext *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802032c4`

## callees

- `0x18000b704`
- `0x18007f5e0`
- `0x1800a550c`
- `0x18010e564`
- `0x18016cf40`
- `0x180170044`
- `0x18018ed14`
- `0x1801a2648`
- `0x1801a6cdc`
- `0x1801aad04`
- `0x1802ad50c`
- `0x1802ad53c`
- `0x1802ad56c`
- `0x1802ad59c`
- `0x1802adafc`
- `0x1802ade90`
- `0x1802adeec`

## import_xrefs

- `msvcrt!free` at `0x1802adbb5`
- `msvcrt!free` at `0x1802adc72`
- `msvcrt!free` at `0x1802adc91`
- `msvcrt!free` at `0x1802adcb1`
- `msvcrt!free` at `0x1802adbb5`
- `msvcrt!free` at `0x1802adc72`
- `msvcrt!free` at `0x1802adc91`
- `msvcrt!free` at `0x1802adcb1`
- `KERNEL32!DeleteCriticalSection` at `0x1802add6e`
- `KERNEL32!DeleteCriticalSection` at `0x1802ade12`
- `KERNEL32!DeleteCriticalSection` at `0x1802ade6a`
- `KERNEL32!DeleteCriticalSection` at `0x1802add6e`
- `KERNEL32!DeleteCriticalSection` at `0x1802ade12`
- `KERNEL32!DeleteCriticalSection` at `0x1802ade6a`
- `KERNEL32!EnterCriticalSection` at `0x1802adb33`
- `KERNEL32!EnterCriticalSection` at `0x1802adb33`
- `KERNEL32!LeaveCriticalSection` at `0x1802adba2`
- `KERNEL32!LeaveCriticalSection` at `0x1802adba2`
- `ADVAPI32!CryptReleaseContext` at `0x1802add41`
- `ADVAPI32!CryptReleaseContext` at `0x1802add41`

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
  __int64 v7; // rcx
  __int64 v8; // rcx
  void *v9; // rcx
  _QWORD *v10; // rsi
  _QWORD *i; // rcx
  _QWORD *v12; // rbx
  _QWORD *v13; // rsi
  _QWORD *j; // rcx
  _QWORD *v15; // rbx
  HCRYPTPROV v16; // rcx

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
    if ( *((_QWORD *)this + 74) )
    {
      DeleteObject<HeapAllocator,JsUtil::BaseHashSet<Js::PropertyRecord const *,HeapAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,Js::PropertyRecord const *,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry>>(v6);
      *((_QWORD *)this + 74) = 0;
    }
    Recycler::RootRelease(*((Recycler **)this + 72), *((void **)this + 228), 0);
    *((_QWORD *)this + 228) = 0;
    DeleteObject<HeapAllocator,CodeGenNumberThreadAllocator>(v7, *((_QWORD *)this + 227));
    *((_QWORD *)this + 227) = 0;
    DeleteObject<HeapAllocator,Recycler>(v8, *((_QWORD *)this + 72));
  }
  v9 = (void *)*((_QWORD *)this + 225);
  if ( v9 )
  {
    if ( *((_BYTE *)this + 8378) )
      DeleteObject<HeapAllocator,JsUtil::BackgroundJobProcessor>(v9, *((_QWORD *)this + 225));
    else
      free(v9);
    *((_QWORD *)this + 225) = 0;
  }
  v10 = (_QWORD *)((char *)this + 1792);
  for ( i = (_QWORD *)*((_QWORD *)this + 224); i != v10; i = v12 )
  {
    v12 = (_QWORD *)*i;
    free(i);
  }
  *v10 = v10;
  v13 = (_QWORD *)((char *)this + 8320);
  for ( j = (_QWORD *)*((_QWORD *)this + 1040); j != v13; j = v15 )
  {
    v15 = (_QWORD *)*j;
    free(j);
  }
  *v13 = v13;
  *((_QWORD *)this + 1041) = (char *)this + 8320;
  HashTable<Js::InlineCache *,ArenaAllocator>::Init((char *)this + 2064);
  HashTable<Js::InlineCache *,ArenaAllocator>::Init((char *)this + 6088);
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
  v16 = *((_QWORD *)this + 73);
  if ( v16 )
  {
    CryptReleaseContext(v16, 0);
    *((_QWORD *)this + 73) = 0;
  }
  JsUtil::BaseDictionary<Js::FunctionProxy *,Js::FunctionProxy *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleHashedEntry>::~BaseDictionary<Js::FunctionProxy *,Js::FunctionProxy *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleHashedEntry>((char *)this + 13968);
  JsUtil::BaseDictionary<Js::PropertyRecord const *,Js::PropertyRecord const *,HeapAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry>::~BaseDictionary<Js::PropertyRecord const *,Js::PropertyRecord const *,HeapAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry>((char *)this + 13840);
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
  ArenaAllocatorBase<InPlaceFreeListPolicy>::~ArenaAllocatorBase<InPlaceFreeListPolicy>((char *)this + 8208);
  JsUtil::BaseDictionary<int,StackSym *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::~BaseDictionary<int,StackSym *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>((char *)this + 8160);
  HashTable<ObjTypeGuardBucket,ArenaAllocator>::~HashTable<ObjTypeGuardBucket,ArenaAllocator>((char *)this + 6088);
  HashTable<ObjTypeGuardBucket,ArenaAllocator>::~HashTable<ObjTypeGuardBucket,ArenaAllocator>((char *)this + 2064);
  ArenaAllocatorBase<InPlaceFreeListPolicy>::~ArenaAllocatorBase<InPlaceFreeListPolicy>((char *)this + 1952);
  ArenaAllocatorBase<InPlaceFreeListPolicy>::~ArenaAllocatorBase<InPlaceFreeListPolicy>((char *)this + 1664);
  PageAllocator::~PageAllocator((ThreadContext *)((char *)this + 408));
  IdleDecommitPageAllocator::~IdleDecommitPageAllocator((ThreadContext *)((char *)this + 160));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
}

```

## disassembly

```asm
0x1802adafc  mov     r11, rsp
0x1802adaff  mov     [r11+8], rcx
0x1802adb03  push    rsi
0x1802adb04  push    rdi
0x1802adb05  push    r12
0x1802adb07  push    r14
0x1802adb09  push    r15
0x1802adb0b  sub     rsp, 30h
0x1802adb0f  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x1802adb17  mov     [r11+10h], rbx
0x1802adb1b  mov     [r11+18h], rbp
0x1802adb1f  lea     rax, ??_7ThreadContext@@6B@; const ThreadContext::`vftable'
0x1802adb26  mov     rdi, rcx
0x1802adb29  mov     [rcx], rax
0x1802adb2c  lea     rcx, ?s_csThreadContext@ThreadContext@@0VCriticalSection@@A; lpCriticalSection
0x1802adb33  call    cs:__imp_EnterCriticalSection
0x1802adb39  mov     rcx, [rdi+8]
0x1802adb3d  mov     rax, [rdi+10h]
0x1802adb41  xor     r12d, r12d
0x1802adb44  test    rcx, rcx
0x1802adb47  jz      short loc_1802ADB4F
0x1802adb49  mov     [rcx+8], rax
0x1802adb4d  jmp     short loc_1802ADB68
0x1802adb4f  test    rax, rax
0x1802adb52  jz      short loc_1802ADB61
0x1802adb54  add     rax, 0FFFFFFFFFFFFFFF8h
0x1802adb58  mov     cs:?globalListFirst@ThreadContext@@2PEAV1@EA, rax; ThreadContext * ThreadContext::globalListFirst
0x1802adb5f  jmp     short loc_1802ADB68
0x1802adb61  mov     cs:?globalListFirst@ThreadContext@@2PEAV1@EA, r12; ThreadContext * ThreadContext::globalListFirst
0x1802adb68  mov     rcx, [rdi+10h]
0x1802adb6c  mov     rax, [rdi+8]
0x1802adb70  test    rcx, rcx
0x1802adb73  jz      short loc_1802ADB7A
0x1802adb75  mov     [rcx], rax
0x1802adb78  jmp     short loc_1802ADB93
0x1802adb7a  test    rax, rax
0x1802adb7d  jz      short loc_1802ADB8C
0x1802adb7f  add     rax, 0FFFFFFFFFFFFFFF8h
0x1802adb83  mov     cs:?globalListLast@ThreadContext@@0PEAV1@EA, rax; ThreadContext * ThreadContext::globalListLast
0x1802adb8a  jmp     short loc_1802ADB93
0x1802adb8c  mov     cs:?globalListLast@ThreadContext@@0PEAV1@EA, r12; ThreadContext * ThreadContext::globalListLast
0x1802adb93  mov     [rdi+8], r12
0x1802adb97  mov     [rdi+10h], r12
0x1802adb9b  lea     rcx, ?s_csThreadContext@ThreadContext@@0VCriticalSection@@A; lpCriticalSection
0x1802adba2  call    cs:__imp_LeaveCriticalSection
0x1802adba8  nop
0x1802adba9  mov     rcx, [rdi+3688h]; Block
0x1802adbb0  test    rcx, rcx
0x1802adbb3  jz      short loc_1802ADBC2
0x1802adbb5  call    cs:__imp_free
0x1802adbbb  mov     [rdi+3688h], r12
0x1802adbc2  lea     r14, [rdi+198h]
0x1802adbc9  mov     byte ptr [r14+74h], 1
0x1802adbce  lea     r15, [rdi+0A0h]
0x1802adbd5  mov     byte ptr [r15+74h], 1
0x1802adbda  cmp     [rdi+240h], r12
0x1802adbe1  jz      short loc_1802ADC53
0x1802adbe3  mov     rax, [rdi+720h]
0x1802adbea  mov     [rax+1C0h], r12
0x1802adbf1  mov     rax, [rdi+720h]
0x1802adbf8  mov     [rax+1D8h], r12
0x1802adbff  mov     rdx, [rdi+250h]
0x1802adc06  test    rdx, rdx
0x1802adc09  jz      short loc_1802ADC17
0x1802adc0b  call    ??$DeleteObject@UHeapAllocator@@V?$BaseHashSet@PEBVPropertyRecord@Js@@UHeapAllocator@@U?$DictionarySizePolicy@UPrimePolicy@@$01$01$00$03@@PEBV12@UPropertyRecordStringHashComparer@2@VSimpleHashedEntry@JsUtil@@@JsUtil@@@@YAXPEAUHeapAllocator@@PEAV?$BaseHashSet@PEBVPropertyRecord@Js@@UHeapAllocator@@U?$DictionarySizePolicy@UPrimePolicy@@$01$01$00$03@@PEBV12@UPropertyRecordStringHashComparer@2@VSimpleHashedEntry@JsUtil@@@JsUtil@@@Z; DeleteObject<HeapAllocator,JsUtil::BaseHashSet<Js::PropertyRecord const *,HeapAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,Js::PropertyRecord const *,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry>>(HeapAllocator *,JsUtil::BaseHashSet<Js::PropertyRecord const *,HeapAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,Js::PropertyRecord const *,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry> *)
0x1802adc10  mov     [rdi+250h], r12
0x1802adc17  xor     r8d, r8d; unsigned int *
0x1802adc1a  mov     rdx, [rdi+720h]; void *
0x1802adc21  mov     rcx, [rdi+240h]; this
0x1802adc28  call    ?RootRelease@Recycler@@QEAAXPEAXPEAI@Z; Recycler::RootRelease(void *,uint *)
0x1802adc2d  mov     [rdi+720h], r12
0x1802adc34  mov     rdx, [rdi+718h]
0x1802adc3b  call    ??$DeleteObject@UHeapAllocator@@VCodeGenNumberThreadAllocator@@@@YAXPEAUHeapAllocator@@PEAVCodeGenNumberThreadAllocator@@@Z; DeleteObject<HeapAllocator,CodeGenNumberThreadAllocator>(HeapAllocator *,CodeGenNumberThreadAllocator *)
0x1802adc40  mov     [rdi+718h], r12
0x1802adc47  mov     rdx, [rdi+240h]
0x1802adc4e  call    ??$DeleteObject@UHeapAllocator@@VRecycler@@@@YAXPEAUHeapAllocator@@PEAVRecycler@@@Z; DeleteObject<HeapAllocator,Recycler>(HeapAllocator *,Recycler *)
0x1802adc53  mov     rcx, [rdi+708h]; Block
0x1802adc5a  test    rcx, rcx
0x1802adc5d  jz      short loc_1802ADC7F
0x1802adc5f  cmp     [rdi+20BAh], r12b
0x1802adc66  jz      short loc_1802ADC72
0x1802adc68  mov     rdx, rcx
0x1802adc6b  call    ??$DeleteObject@UHeapAllocator@@VBackgroundJobProcessor@JsUtil@@@@YAXPEAUHeapAllocator@@PEAVBackgroundJobProcessor@JsUtil@@@Z; DeleteObject<HeapAllocator,JsUtil::BackgroundJobProcessor>(HeapAllocator *,JsUtil::BackgroundJobProcessor *)
0x1802adc70  jmp     short loc_1802ADC78
0x1802adc72  call    cs:__imp_free
0x1802adc78  mov     [rdi+708h], r12
0x1802adc7f  lea     rsi, [rdi+700h]
0x1802adc86  mov     rcx, [rsi]; Block
0x1802adc89  cmp     rcx, rsi
0x1802adc8c  jz      short loc_1802ADC9C
0x1802adc8e  mov     rbx, [rcx]
0x1802adc91  call    cs:__imp_free
0x1802adc97  mov     rcx, rbx
0x1802adc9a  jmp     short loc_1802ADC89
0x1802adc9c  mov     [rsi], rsi
0x1802adc9f  lea     rsi, [rdi+2080h]
0x1802adca6  mov     rcx, [rsi]; Block
0x1802adca9  cmp     rcx, rsi
0x1802adcac  jz      short loc_1802ADCBC
0x1802adcae  mov     rbx, [rcx]
0x1802adcb1  call    cs:__imp_free
0x1802adcb7  mov     rcx, rbx
0x1802adcba  jmp     short loc_1802ADCA9
0x1802adcbc  mov     [rsi], rsi
0x1802adcbf  mov     [rsi+8], rsi
0x1802adcc3  lea     rsi, [rdi+810h]
0x1802adcca  mov     rcx, rsi
0x1802adccd  call    ?Init@?$HashTable@PEAUInlineCache@Js@@VArenaAllocator@@@@IEAAXXZ; HashTable<Js::InlineCache *,ArenaAllocator>::Init(void)
0x1802adcd2  lea     rbp, [rdi+17C8h]
0x1802adcd9  mov     rcx, rbp
0x1802adcdc  call    ?Init@?$HashTable@PEAUInlineCache@Js@@VArenaAllocator@@@@IEAAXXZ; HashTable<Js::InlineCache *,ArenaAllocator>::Init(void)
0x1802adce1  lea     rbx, [rdi+1FE0h]
0x1802adce8  mov     [rbx], r12
0x1802adceb  mov     [rbx+8], r12
0x1802adcef  mov     [rbx+10h], r12
0x1802adcf3  mov     [rbx+18h], r12
0x1802adcf7  mov     [rbx+20h], r12d
0x1802adcfb  lea     rax, [rdi+800h]
0x1802add02  mov     [rax], rax
0x1802add05  mov     [rax+8], rax
0x1802add09  lea     rax, [rdi+2070h]
0x1802add10  mov     [rax], rax
0x1802add13  mov     [rax+8], rax
0x1802add17  cmp     [rdi+18h], r12
0x1802add1b  jz      short loc_1802ADD21
0x1802add1d  mov     [rdi+18h], r12
0x1802add21  mov     rax, [rdi+738h]
0x1802add28  neg     rax
0x1802add2b  lock add cs:?processNativeCodeSize@ThreadContext@@0_KA, rax; unsigned __int64 ThreadContext::processNativeCodeSize
0x1802add33  mov     rcx, [rdi+248h]; hProv
0x1802add3a  test    rcx, rcx
0x1802add3d  jz      short loc_1802ADD4E
0x1802add3f  xor     edx, edx; dwFlags
0x1802add41  call    cs:__imp_CryptReleaseContext
0x1802add47  mov     [rdi+248h], r12
0x1802add4e  lea     rcx, [rdi+3690h]
0x1802add55  call    ??1?$BaseDictionary@PEAVFunctionProxy@Js@@PEAV12@VArenaAllocator@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleHashedEntry@JsUtil@@@JsUtil@@QEAA@XZ; JsUtil::BaseDictionary<Js::FunctionProxy *,Js::FunctionProxy *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleHashedEntry>::~BaseDictionary<Js::FunctionProxy *,Js::FunctionProxy *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleHashedEntry>(void)
0x1802add5a  lea     rcx, [rdi+3610h]
0x1802add61  call    ??1?$BaseDictionary@PEBVPropertyRecord@Js@@PEBV12@UHeapAllocator@@U?$DictionarySizePolicy@UPrimePolicy@@$01$01$00$03@@UPropertyRecordStringHashComparer@2@VSimpleHashedEntry@JsUtil@@@JsUtil@@QEAA@XZ; JsUtil::BaseDictionary<Js::PropertyRecord const *,Js::PropertyRecord const *,HeapAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry>::~BaseDictionary<Js::PropertyRecord const *,Js::PropertyRecord const *,HeapAllocator,DictionarySizePolicy<PrimePolicy,2,2,1,4>,Js::PropertyRecordStringHashComparer,JsUtil::SimpleHashedEntry>(void)
0x1802add66  nop
0x1802add67  lea     rcx, [rdi+2298h]; lpCriticalSection
0x1802add6e  call    cs:__imp_DeleteCriticalSection
0x1802add74  nop
0x1802add75  lea     rcx, [rdi+2250h]; this
0x1802add7c  call    ??1WindowsFoundationAdapter@Js@@QEAA@XZ; Js::WindowsFoundationAdapter::~WindowsFoundationAdapter(void)
0x1802add81  lea     rcx, [rdi+2230h]; this
0x1802add88  lea     rax, ??_7DelayLoadWinRtFoundation@Js@@6B@; const Js::DelayLoadWinRtFoundation::`vftable'
0x1802add8f  mov     [rcx], rax
0x1802add92  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x1802add97  lea     rcx, [rdi+21E8h]; this
0x1802add9e  call    ??1WindowsGlobalizationAdapter@Js@@QEAA@XZ; Js::WindowsGlobalizationAdapter::~WindowsGlobalizationAdapter(void)
0x1802adda3  lea     rcx, [rdi+2188h]; this
0x1802addaa  lea     r12, ??_7DelayLoadWinRtString@Js@@6B@; const Js::DelayLoadWinRtString::`vftable'
0x1802addb1  mov     [rcx], r12
0x1802addb4  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x1802addb9  lea     rcx, [rdi+2168h]; this
0x1802addc0  lea     rax, ??_7DelayLoadWinRtRoParameterizedIID@Js@@6B@; const Js::DelayLoadWinRtRoParameterizedIID::`vftable'
0x1802addc7  mov     [rcx], rax
0x1802addca  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x1802addcf  lea     rcx, [rdi+2148h]; this
0x1802addd6  lea     rax, ??_7DelayLoadWinRtTypeResolution@Js@@6B@; const Js::DelayLoadWinRtTypeResolution::`vftable'
0x1802adddd  mov     [rcx], rax
0x1802adde0  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x1802adde5  lea     rcx, [rdi+2120h]; this
0x1802addec  lea     rax, ??_7DelayLoadWinRtError@Js@@6B@; const Js::DelayLoadWinRtError::`vftable'
0x1802addf3  mov     [rcx], rax
0x1802addf6  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x1802addfb  lea     rcx, [rdi+20D8h]; this
0x1802ade02  mov     [rcx], r12
0x1802ade05  call    ??1DelayLoadLibrary@@UEAA@XZ; DelayLoadLibrary::~DelayLoadLibrary(void)
0x1802ade0a  nop
0x1802ade0b  lea     rcx, [rdi+2090h]; lpCriticalSection
0x1802ade12  call    cs:__imp_DeleteCriticalSection
0x1802ade18  nop
0x1802ade19  lea     rcx, [rdi+2010h]
0x1802ade20  call    ??1?$ArenaAllocatorBase@VInPlaceFreeListPolicy@@@@QEAA@XZ; ArenaAllocatorBase<InPlaceFreeListPolicy>::~ArenaAllocatorBase<InPlaceFreeListPolicy>(void)
0x1802ade25  mov     rcx, rbx
0x1802ade28  call    ??1?$BaseDictionary@HPEAVStackSym@@VArenaAllocator@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@@JsUtil@@QEAA@XZ; JsUtil::BaseDictionary<int,StackSym *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::~BaseDictionary<int,StackSym *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>(void)
0x1802ade2d  mov     rcx, rbp
0x1802ade30  call    ??1?$HashTable@VObjTypeGuardBucket@@VArenaAllocator@@@@QEAA@XZ; HashTable<ObjTypeGuardBucket,ArenaAllocator>::~HashTable<ObjTypeGuardBucket,ArenaAllocator>(void)
0x1802ade35  mov     rcx, rsi
0x1802ade38  call    ??1?$HashTable@VObjTypeGuardBucket@@VArenaAllocator@@@@QEAA@XZ; HashTable<ObjTypeGuardBucket,ArenaAllocator>::~HashTable<ObjTypeGuardBucket,ArenaAllocator>(void)
0x1802ade3d  lea     rcx, [rdi+7A0h]
0x1802ade44  call    ??1?$ArenaAllocatorBase@VInPlaceFreeListPolicy@@@@QEAA@XZ; ArenaAllocatorBase<InPlaceFreeListPolicy>::~ArenaAllocatorBase<InPlaceFreeListPolicy>(void)
0x1802ade49  lea     rcx, [rdi+680h]
0x1802ade50  call    ??1?$ArenaAllocatorBase@VInPlaceFreeListPolicy@@@@QEAA@XZ; ArenaAllocatorBase<InPlaceFreeListPolicy>::~ArenaAllocatorBase<InPlaceFreeListPolicy>(void)
0x1802ade55  mov     rcx, r14; this
0x1802ade58  call    ??1PageAllocator@@UEAA@XZ; PageAllocator::~PageAllocator(void)
0x1802ade5d  mov     rcx, r15; this
0x1802ade60  call    ??1IdleDecommitPageAllocator@@UEAA@XZ; IdleDecommitPageAllocator::~IdleDecommitPageAllocator(void)
0x1802ade65  nop
0x1802ade66  lea     rcx, [rdi+70h]; lpCriticalSection
0x1802ade6a  call    cs:__imp_DeleteCriticalSection
0x1802ade70  nop
0x1802ade71  mov     rbx, [rsp+58h+arg_8]
0x1802ade76  mov     rbp, [rsp+58h+arg_10]
0x1802ade7b  add     rsp, 30h
0x1802ade7f  pop     r15
0x1802ade81  pop     r14
0x1802ade83  pop     r12
0x1802ade85  pop     rdi
0x1802ade86  pop     rsi
0x1802ade87  retn
```
