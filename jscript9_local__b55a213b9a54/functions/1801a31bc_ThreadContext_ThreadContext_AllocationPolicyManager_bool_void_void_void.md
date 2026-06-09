# ThreadContext::ThreadContext(AllocationPolicyManager *,bool (*)(void (*)(void *),void *))

- ea: `0x1801a31bc`
- end: `0x1801a386e`
- name: `??0ThreadContext@@QEAA@PEAVAllocationPolicyManager@@P6A_NP6AXPEAX@Z1@Z@Z`
- size: `1714`
- prototype: `ThreadContext *__fastcall(ThreadContext *__hidden this, struct AllocationPolicyManager *, bool (*)(void (*)(void *), void *))`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802077a4`
- `0x1802ce304`

## callees

- `0x18003ed20`
- `0x1801312b0`
- `0x180156208`
- `0x180171570`
- `0x1801951e8`
- `0x18019e99c`
- `0x1801a31bc`
- `0x1801a38dc`
- `0x1801a39c8`
- `0x1801a3a18`
- `0x1801a3ae8`
- `0x1802b2a74`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1801a34bc`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1801a36aa`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1801a34bc`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1801a36aa`
- `KERNEL32!EnterCriticalSection` at `0x1801a3825`
- `KERNEL32!EnterCriticalSection` at `0x1801a3825`
- `KERNEL32!LeaveCriticalSection` at `0x1801a3842`
- `KERNEL32!LeaveCriticalSection` at `0x1801a3842`
- `KERNEL32!GetCurrentThreadId` at `0x1801a320f`
- `KERNEL32!GetCurrentThreadId` at `0x1801a320f`

## pseudocode

```c
// Hidden C++ exception states: #wind=42
ThreadContext *__fastcall ThreadContext::ThreadContext(
        ThreadContext *this,
        struct AllocationPolicyManager *a2,
        bool (*a3)(void (*)(void *), void *))
{
  __int64 v4; // r8
  char *v5; // rbx
  __int64 v6; // r9
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // rax
  char v11; // [rsp+40h] [rbp-61h]
  char *(*v12)(ArenaAllocator *__hidden, unsigned __int64); // [rsp+58h] [rbp-49h] BYREF
  int v13; // [rsp+60h] [rbp-41h]

  JsUtil::DoublyLinkedListElement<JsUtil::MruDictionary<UnifiedRegex::RegexKey,UnifiedRegex::RegexPattern *,Recycler,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::MruListEntry>::DoublyLinkedListElement<JsUtil::MruDictionary<UnifiedRegex::RegexKey,UnifiedRegex::RegexPattern *,Recycler,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::MruListEntry>((char *)this + 8);
  *(_QWORD *)this = &ThreadContext::`vftable';
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_DWORD *)this + 9) = GetCurrentThreadId();
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_WORD *)this + 28) = 256;
  *((_QWORD *)this + 8) = a2;
  *((_QWORD *)this + 9) = a3;
  *((_BYTE *)this + 80) = 0;
  *((_DWORD *)this + 22) = 0;
  PageAllocator::BackgroundPageQueue::BackgroundPageQueue((ThreadContext *)((char *)this + 96));
  IdleDecommitPageAllocator::IdleDecommitPageAllocator((char *)this + 160, a2);
  v11 = 0;
  PageAllocator::PageAllocator((char *)this + 408, a2, v4, 0, 1024, 0, 0, v11, -2);
  *((_QWORD *)this + 72) = 0;
  *((_QWORD *)this + 73) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_QWORD *)this + 75) = 0;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 78) = 0;
  *((_QWORD *)this + 79) = 0;
  v5 = (char *)this + 1664;
  *((_QWORD *)this + 208) = Js::Throw::OutOfMemory;
  *((_QWORD *)this + 209) = Js::MemoryHelper::RecoverUnusedMemory;
  *((_QWORD *)this + 210) = 0;
  *((_QWORD *)this + 211) = 0;
  *((_QWORD *)this + 212) = 0;
  *((_QWORD *)this + 213) = (char *)this + 160;
  *((_QWORD *)this + 214) = 0;
  *((_BYTE *)this + 1720) = 0;
  *((_QWORD *)this + 216) = 0;
  *((_QWORD *)this + 217) = 0;
  *((_DWORD *)this + 436) = 0;
  *((_QWORD *)this + 219) = 0;
  *((_QWORD *)this + 220) = 0;
  *((_DWORD *)this + 444) = 2048;
  *(_QWORD *)((char *)this + 1780) = 1;
  *((_DWORD *)this + 447) = 0;
  *((_QWORD *)this + 224) = (char *)this + 1792;
  *((_QWORD *)this + 225) = 0;
  *((_QWORD *)this + 227) = 0;
  *((_QWORD *)this + 228) = 0;
  *((_QWORD *)this + 229) = 0;
  *((_QWORD *)this + 230) = 0;
  *((_QWORD *)this + 231) = 0;
  *((_QWORD *)this + 232) = 0;
  *((_QWORD *)this + 233) = 0;
  *((_QWORD *)this + 234) = 0;
  *((_QWORD *)this + 235) = 0x3FF0000000000000LL;
  *((_QWORD *)this + 236) = 0;
  *((_WORD *)this + 952) = 1;
  *((_BYTE *)this + 1906) = 1;
  *((_QWORD *)this + 239) = 0;
  *((_QWORD *)this + 240) = 0;
  *((_DWORD *)this + 486) = 0;
  *((_QWORD *)this + 244) = Js::Throw::OutOfMemory;
  *((_QWORD *)this + 245) = Js::MemoryHelper::RecoverUnusedMemory;
  *((_QWORD *)this + 246) = 0;
  *((_QWORD *)this + 247) = 0;
  *((_QWORD *)this + 248) = 0;
  *((_QWORD *)this + 249) = (char *)this + 160;
  *((_QWORD *)this + 250) = 0;
  *((_BYTE *)this + 2008) = 0;
  *((_QWORD *)this + 252) = 0;
  *((_QWORD *)this + 253) = 0;
  *((_DWORD *)this + 508) = 0;
  *((_QWORD *)this + 255) = 0;
  *((_QWORD *)this + 256) = (char *)this + 2048;
  *((_QWORD *)this + 257) = (char *)this + 2048;
  *((_QWORD *)this + 258) = (char *)this + 1952;
  *((_DWORD *)this + 518) = 500;
  HashTable<Js::InlineCache *,ArenaAllocator>::Init((char *)this + 2064);
  *((_QWORD *)this + 761) = v6;
  *((_DWORD *)this + 1524) = 256;
  HashTable<Js::InlineCache *,ArenaAllocator>::Init((char *)this + 6088);
  JsUtil::BaseDictionary<void *,Js::IsInstInlineCache *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::BaseDictionary<void *,Js::IsInstInlineCache *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>(
    (char *)this + 8160,
    v7);
  *((_QWORD *)this + 1026) = Js::Throw::OutOfMemory;
  *((_QWORD *)this + 1027) = Js::MemoryHelper::RecoverUnusedMemory;
  *((_QWORD *)this + 1028) = 0;
  *((_QWORD *)this + 1029) = 0;
  *((_QWORD *)this + 1030) = 0;
  *((_QWORD *)this + 1031) = (char *)this + 160;
  *((_QWORD *)this + 1032) = 0;
  *((_BYTE *)this + 8264) = 0;
  *((_QWORD *)this + 1034) = 0;
  *((_QWORD *)this + 1035) = 0;
  *((_DWORD *)this + 2072) = 0;
  *((_QWORD *)this + 1037) = 0;
  *((_QWORD *)this + 1038) = (char *)this + 8304;
  *((_QWORD *)this + 1039) = (char *)this + 8304;
  *((_QWORD *)this + 1040) = (char *)this + 8320;
  *((_QWORD *)this + 1041) = (char *)this + 8320;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 8336), 0);
  *((_BYTE *)this + 8376) = 0;
  *((_BYTE *)this + 8377) = BYTE5(qword_180442D70);
  *((_BYTE *)this + 8378) = Js::Configuration::Global;
  *((_DWORD *)this + 2095) = 4;
  *((_BYTE *)this + 8384) = 0;
  *((_QWORD *)this + 1049) = 0;
  *((_DWORD *)this + 2100) = 0;
  *((_QWORD *)this + 1052) = 0;
  *((_BYTE *)this + 8424) = 0;
  *((_QWORD *)this + 1051) = &Js::DelayLoadWinRtString::`vftable';
  *((_QWORD *)this + 1054) = 0;
  *((_QWORD *)this + 1055) = 0;
  *((_QWORD *)this + 1056) = 0;
  *((_QWORD *)this + 1057) = 0;
  *((_QWORD *)this + 1058) = 0;
  *((_QWORD *)this + 1059) = 0;
  *((_QWORD *)this + 1061) = 0;
  *((_BYTE *)this + 8496) = 0;
  *((_QWORD *)this + 1060) = &Js::DelayLoadWinRtError::`vftable';
  *((_QWORD *)this + 1063) = 0;
  *((_QWORD *)this + 1064) = 0;
  *((_QWORD *)this + 1066) = 0;
  *((_BYTE *)this + 8536) = 0;
  *((_QWORD *)this + 1065) = &Js::DelayLoadWinRtTypeResolution::`vftable';
  *((_QWORD *)this + 1068) = 0;
  *((_QWORD *)this + 1070) = 0;
  *((_BYTE *)this + 8568) = 0;
  *((_QWORD *)this + 1069) = &Js::DelayLoadWinRtRoParameterizedIID::`vftable';
  *((_QWORD *)this + 1072) = 0;
  *((_QWORD *)this + 1074) = 0;
  *((_BYTE *)this + 8600) = 0;
  *((_QWORD *)this + 1076) = 0;
  *((_QWORD *)this + 1077) = 0;
  *((_QWORD *)this + 1078) = 0;
  *((_QWORD *)this + 1079) = 0;
  *((_QWORD *)this + 1080) = 0;
  *((_QWORD *)this + 1081) = 0;
  *((_QWORD *)this + 1073) = &Js::DelayLoadWindowsGlobalization::`vftable';
  *((_QWORD *)this + 1082) = 0;
  *((_QWORD *)this + 1083) = 0;
  *((_DWORD *)this + 2168) = 0;
  *((_QWORD *)this + 1085) = 0;
  *((_QWORD *)this + 1086) = 0;
  *((_QWORD *)this + 1087) = 0;
  *((_QWORD *)this + 1088) = 0;
  *((_QWORD *)this + 1089) = 0;
  *((_QWORD *)this + 1090) = 0;
  *((_QWORD *)this + 1091) = 0;
  *((_QWORD *)this + 1092) = 0;
  *((_QWORD *)this + 1093) = 0;
  *((_QWORD *)this + 1095) = 0;
  *((_BYTE *)this + 8768) = 0;
  *((_QWORD *)this + 1094) = &Js::DelayLoadWinRtFoundation::`vftable';
  *((_QWORD *)this + 1097) = 0;
  *((_QWORD *)this + 1098) = 0;
  *((_QWORD *)this + 1099) = 0;
  *((_DWORD *)this + 2200) = 0;
  *((_QWORD *)this + 1101) = 0;
  *((_QWORD *)this + 1102) = 0;
  *((_QWORD *)this + 1104) = 0;
  *((_QWORD *)this + 1105) = 0;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 8856), 0);
  *((_DWORD *)this + 3456) = 0;
  JsUtil::BaseDictionary<Js::DynamicType const *,void *,HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::BaseDictionary<Js::DynamicType const *,void *,HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>((char *)this + 13840);
  *((_QWORD *)this + 1738) = (char *)this + 13888;
  *((_BYTE *)this + 13912) = 0;
  *((_DWORD *)this + 3479) = -1;
  *((_DWORD *)this + 3480) = 0;
  *((_BYTE *)this + 13924) = 0;
  *((_QWORD *)this + 1741) = 0;
  *((_DWORD *)this + 3484) = 0;
  *((_DWORD *)this + 3485) = -1;
  *((_QWORD *)this + 1743) = 0;
  *((_QWORD *)this + 1745) = 0;
  *((_QWORD *)this + 1746) = 0;
  *((_QWORD *)this + 1747) = 0;
  *((_QWORD *)this + 1748) = 0;
  *((_QWORD *)this + 1749) = 0;
  *((_DWORD *)this + 3500) = 0;
  *((_QWORD *)this + 1751) = (char *)this + 1664;
  v12 = (char *(*)(ArenaAllocator *__hidden, unsigned __int64))ArenaAllocator::Alloc;
  v13 = 0;
  v8 = operator new<ArenaAllocator>(40, (char *)this + 1664, &v12);
  if ( v8 )
  {
    *(_DWORD *)(v8 + 16) = 4;
    *(_QWORD *)(v8 + 24) = v5;
    *(_QWORD *)v8 = 0;
    *(_QWORD *)(v8 + 8) = 0;
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 77) = v8;
  v12 = (char *(*)(ArenaAllocator *__hidden, unsigned __int64))ArenaAllocator::Alloc;
  v13 = 0;
  v9 = operator new<ArenaAllocator>(48, (char *)this + 1664, &v12);
  if ( v9 )
  {
    *(_DWORD *)(v9 + 16) = 4;
    *(_QWORD *)(v9 + 24) = v5;
    *(_QWORD *)v9 = 0;
    *(_QWORD *)(v9 + 8) = 0;
    *(_DWORD *)(v9 + 40) = 0;
  }
  else
  {
    v9 = 0;
  }
  *((_QWORD *)this + 1103) = v9;
  *((_QWORD *)this + 221) = 0;
  *((_BYTE *)this + 8849) = 0;
  Entropy::Initialize((ThreadContext *)((char *)this + 8808));
  v12 = ArenaAllocator::AllocZero;
  v13 = 0;
  *((_QWORD *)this + 226) = AllocateArray<ArenaAllocator,void *,0>((char *)this + 1664, &v12, 33);
  *((_OWORD *)this + 868) = 0;
  EnterCriticalSection(&ThreadContext::s_csThreadContext);
  JsUtil::DoublyLinkedListElement<ThreadContext>::LinkToBeginning<ThreadContext>((char *)this + 8);
  LeaveCriticalSection(&ThreadContext::s_csThreadContext);
  return this;
}

```

## disassembly

```asm
0x1801a31bc  mov     rax, rsp
0x1801a31bf  mov     [rax+18h], r8
0x1801a31c3  mov     [rax+10h], rdx
0x1801a31c7  mov     [rax+8], rcx
0x1801a31cb  push    rbp
0x1801a31cc  push    rsi
0x1801a31cd  push    rdi
0x1801a31ce  push    r12
0x1801a31d0  push    r13
0x1801a31d2  push    r14
0x1801a31d4  push    r15
0x1801a31d6  lea     rbp, [rax-5Fh]
0x1801a31da  sub     rsp, 0C0h
0x1801a31e1  mov     [rbp+57h+var_B0], 0FFFFFFFFFFFFFFFEh
0x1801a31e9  mov     [rax+20h], rbx
0x1801a31ed  mov     r14, [rbp+57h+arg_0]
0x1801a31f1  lea     rcx, [r14+8]; void *
0x1801a31f5  call    ??0?$DoublyLinkedListElement@UMruListEntry@?$MruDictionary@VRegexKey@UnifiedRegex@@PEAURegexPattern@2@VRecycler@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@@JsUtil@@@JsUtil@@QEAA@XZ; JsUtil::DoublyLinkedListElement<JsUtil::MruDictionary<UnifiedRegex::RegexKey,UnifiedRegex::RegexPattern *,Recycler,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::MruListEntry>::DoublyLinkedListElement<JsUtil::MruDictionary<UnifiedRegex::RegexKey,UnifiedRegex::RegexPattern *,Recycler,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::MruListEntry>(void)
0x1801a31fa  lea     rcx, ??_7ThreadContext@@6B@; const ThreadContext::`vftable'
0x1801a3201  mov     [r14], rcx
0x1801a3204  xor     r13d, r13d
0x1801a3207  mov     [r14+18h], r13
0x1801a320b  mov     [r14+20h], r13d
0x1801a320f  call    cs:__imp_GetCurrentThreadId
0x1801a3216  nop     dword ptr [rax+rax+00h]
0x1801a321b  mov     [r14+24h], eax
0x1801a321f  mov     [r14+28h], r13
0x1801a3223  mov     [r14+30h], r13
0x1801a3227  mov     word ptr [r14+38h], 100h
0x1801a322e  mov     rdi, [rbp+57h+arg_8]
0x1801a3232  mov     [r14+40h], rdi
0x1801a3236  mov     rax, [rbp+57h+arg_10]
0x1801a323a  mov     [r14+48h], rax
0x1801a323e  mov     [r14+50h], r13b
0x1801a3242  mov     [r14+58h], r13d
0x1801a3246  lea     rbx, [r14+60h]
0x1801a324a  mov     rcx, rbx; this
0x1801a324d  call    ??0BackgroundPageQueue@PageAllocator@@QEAA@XZ; PageAllocator::BackgroundPageQueue::BackgroundPageQueue(void)
0x1801a3252  nop
0x1801a3253  lea     rsi, [r14+0A0h]
0x1801a325a  mov     qword ptr [rsp+0F0h+var_C0], rbx
0x1801a325f  mov     byte ptr [rsp+0F0h+var_C8], r13b
0x1801a3264  mov     [rsp+0F0h+var_D0], 400h
0x1801a326d  mov     rdx, rdi
0x1801a3270  mov     rcx, rsi
0x1801a3273  call    ??0IdleDecommitPageAllocator@@QEAA@PEAVAllocationPolicyManager@@W4PageAllocatorType@@_K2_NPEAUBackgroundPageQueue@PageAllocator@@@Z; IdleDecommitPageAllocator::IdleDecommitPageAllocator(AllocationPolicyManager *,PageAllocatorType,unsigned __int64,unsigned __int64,bool,PageAllocator::BackgroundPageQueue *)
0x1801a3278  nop
0x1801a3279  lea     rcx, [r14+198h]
0x1801a3280  mov     [rsp+38h], r13b
0x1801a3285  mov     qword ptr [rsp+0F0h+var_C0], r13
0x1801a328a  mov     [rsp+0F0h+var_C8], r13
0x1801a328f  mov     byte ptr [rsp+0F0h+var_D0], r13b
0x1801a3294  xor     r9d, r9d
0x1801a3297  mov     rdx, rdi
0x1801a329a  call    ??0PageAllocator@@QEAA@PEAVAllocationPolicyManager@@W4PageAllocatorType@@_K_NPEAUBackgroundPageQueue@0@23@Z; PageAllocator::PageAllocator(AllocationPolicyManager *,PageAllocatorType,unsigned __int64,bool,PageAllocator::BackgroundPageQueue *,unsigned __int64,bool)
0x1801a329f  nop
0x1801a32a0  mov     [r14+240h], r13
0x1801a32a7  mov     [r14+248h], r13
0x1801a32ae  mov     [r14+250h], r13
0x1801a32b5  mov     [r14+258h], r13
0x1801a32bc  mov     [r14+260h], r13
0x1801a32c3  mov     [r14+270h], r13
0x1801a32ca  mov     [r14+278h], r13
0x1801a32d1  lea     rbx, [r14+680h]
0x1801a32d8  lea     r12, ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1801a32df  mov     [rbx], r12
0x1801a32e2  lea     rdi, ?RecoverUnusedMemory@MemoryHelper@Js@@SAXXZ; Js::MemoryHelper::RecoverUnusedMemory(void)
0x1801a32e9  mov     [rbx+8], rdi
0x1801a32ed  mov     [rbx+10h], r13
0x1801a32f1  mov     [rbx+18h], r13
0x1801a32f5  mov     [rbx+20h], r13
0x1801a32f9  mov     [rbx+28h], rsi
0x1801a32fd  mov     [rbx+30h], r13
0x1801a3301  mov     [rbx+38h], r13b
0x1801a3305  mov     [rbx+40h], r13
0x1801a3309  mov     [rbx+48h], r13
0x1801a330d  mov     [rbx+50h], r13d
0x1801a3311  mov     [rbx+58h], r13
0x1801a3315  mov     [r14+6E0h], r13
0x1801a331c  mov     dword ptr [r14+6F0h], 800h
0x1801a3327  mov     qword ptr [r14+6F4h], 1
0x1801a3332  mov     [r14+6FCh], r13d
0x1801a3339  lea     rax, [r14+700h]
0x1801a3340  mov     [rax], rax
0x1801a3343  mov     [r14+708h], r13
0x1801a334a  mov     [r14+718h], r13
0x1801a3351  mov     [r14+720h], r13
0x1801a3358  mov     [r14+728h], r13
0x1801a335f  mov     [r14+730h], r13
0x1801a3366  mov     [r14+738h], r13
0x1801a336d  mov     [r14+740h], r13
0x1801a3374  mov     [r14+748h], r13
0x1801a337b  mov     [r14+750h], r13
0x1801a3382  mov     rax, 3FF0000000000000h
0x1801a338c  mov     [r14+758h], rax
0x1801a3393  mov     [r14+760h], r13
0x1801a339a  mov     word ptr [r14+770h], 1
0x1801a33a4  mov     byte ptr [r14+772h], 1
0x1801a33ac  mov     [r14+778h], r13
0x1801a33b3  mov     [r14+780h], r13
0x1801a33ba  mov     [r14+798h], r13d
0x1801a33c1  lea     r9, [r14+7A0h]
0x1801a33c8  mov     [r9], r12
0x1801a33cb  mov     [r9+8], rdi
0x1801a33cf  mov     [r9+10h], r13
0x1801a33d3  mov     [r9+18h], r13
0x1801a33d7  mov     [r9+20h], r13
0x1801a33db  mov     [r9+28h], rsi
0x1801a33df  mov     [r9+30h], r13
0x1801a33e3  mov     [r9+38h], r13b
0x1801a33e7  mov     [r9+40h], r13
0x1801a33eb  mov     [r9+48h], r13
0x1801a33ef  mov     [r9+50h], r13d
0x1801a33f3  mov     [r9+58h], r13
0x1801a33f7  lea     rax, [r14+800h]
0x1801a33fe  mov     [rax], rax
0x1801a3401  mov     [rax+8], rax
0x1801a3405  lea     rcx, [r14+810h]
0x1801a340c  mov     [rcx], r9
0x1801a340f  mov     dword ptr [rcx+8], 1F4h
0x1801a3416  call    ?Init@?$HashTable@PEAUInlineCache@Js@@VArenaAllocator@@@@IEAAXXZ; HashTable<Js::InlineCache *,ArenaAllocator>::Init(void)
0x1801a341b  nop
0x1801a341c  lea     rcx, [r14+17C8h]
0x1801a3423  mov     [rcx], r9
0x1801a3426  mov     dword ptr [rcx+8], 100h
0x1801a342d  call    ?Init@?$HashTable@PEAUInlineCache@Js@@VArenaAllocator@@@@IEAAXXZ; HashTable<Js::InlineCache *,ArenaAllocator>::Init(void)
0x1801a3432  nop
0x1801a3433  lea     rcx, [r14+1FE0h]
0x1801a343a  mov     rdx, r9
0x1801a343d  call    ??0?$BaseDictionary@PEAXPEAUIsInstInlineCache@Js@@VArenaAllocator@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@@JsUtil@@QEAA@PEAVArenaAllocator@@H@Z; JsUtil::BaseDictionary<void *,Js::IsInstInlineCache *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::BaseDictionary<void *,Js::IsInstInlineCache *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>(ArenaAllocator *,int)
0x1801a3442  nop
0x1801a3443  mov     [r14+2010h], r12
0x1801a344a  mov     [r14+2018h], rdi
0x1801a3451  mov     [r14+2020h], r13
0x1801a3458  mov     [r14+2028h], r13
0x1801a345f  mov     [r14+2030h], r13
0x1801a3466  mov     [r14+2038h], rsi
0x1801a346d  mov     [r14+2040h], r13
0x1801a3474  mov     [r14+2048h], r13b
0x1801a347b  mov     [r14+2050h], r13
0x1801a3482  mov     [r14+2058h], r13
0x1801a3489  mov     [r14+2060h], r13d
0x1801a3490  mov     [r14+2068h], r13
0x1801a3497  lea     rax, [r14+2070h]
0x1801a349e  mov     [rax], rax
0x1801a34a1  mov     [rax+8], rax
0x1801a34a5  lea     rax, [r14+2080h]
0x1801a34ac  mov     [rax], rax
0x1801a34af  mov     [rax+8], rax
0x1801a34b3  lea     rcx, [r14+2090h]; lpCriticalSection
0x1801a34ba  xor     edx, edx; dwSpinCount
0x1801a34bc  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1801a34c3  nop     dword ptr [rax+rax+00h]
0x1801a34c8  nop
0x1801a34c9  mov     [r14+20B8h], r13b
0x1801a34d0  mov     al, byte ptr cs:qword_180442D70+5
0x1801a34d6  mov     [r14+20B9h], al
0x1801a34dd  mov     al, cs:?Global@Configuration@Js@@2V12@A; Js::Configuration Js::Configuration::Global
0x1801a34e3  mov     [r14+20BAh], al
0x1801a34ea  lea     r12d, [r13+4]
0x1801a34ee  mov     [r14+20BCh], r12d
0x1801a34f5  mov     [r14+20C0h], r13b
0x1801a34fc  mov     [r14+20C8h], r13
0x1801a3503  mov     [r14+20D0h], r13d
0x1801a350a  mov     [r14+20E0h], r13
0x1801a3511  mov     [r14+20E8h], r13b
0x1801a3518  lea     rax, ??_7DelayLoadWinRtString@Js@@6B@; const Js::DelayLoadWinRtString::`vftable'
0x1801a351f  mov     [r14+20D8h], rax
0x1801a3526  mov     [r14+20F0h], r13
0x1801a352d  mov     [r14+20F8h], r13
0x1801a3534  mov     [r14+2100h], r13
0x1801a353b  mov     [r14+2108h], r13
0x1801a3542  mov     [r14+2110h], r13
0x1801a3549  mov     [r14+2118h], r13
0x1801a3550  mov     [r14+2128h], r13
0x1801a3557  mov     [r14+2130h], r13b
0x1801a355e  lea     rax, ??_7DelayLoadWinRtError@Js@@6B@; const Js::DelayLoadWinRtError::`vftable'
0x1801a3565  mov     [r14+2120h], rax
0x1801a356c  mov     [r14+2138h], r13
0x1801a3573  mov     [r14+2140h], r13
0x1801a357a  mov     [r14+2150h], r13
0x1801a3581  mov     [r14+2158h], r13b
0x1801a3588  lea     rax, ??_7DelayLoadWinRtTypeResolution@Js@@6B@; const Js::DelayLoadWinRtTypeResolution::`vftable'
0x1801a358f  mov     [r14+2148h], rax
0x1801a3596  mov     [r14+2160h], r13
0x1801a359d  mov     [r14+2170h], r13
0x1801a35a4  mov     [r14+2178h], r13b
0x1801a35ab  lea     rax, ??_7DelayLoadWinRtRoParameterizedIID@Js@@6B@; const Js::DelayLoadWinRtRoParameterizedIID::`vftable'
0x1801a35b2  mov     [r14+2168h], rax
0x1801a35b9  mov     [r14+2180h], r13
0x1801a35c0  mov     [r14+2190h], r13
0x1801a35c7  mov     [r14+2198h], r13b
0x1801a35ce  mov     [r14+21A0h], r13
0x1801a35d5  mov     [r14+21A8h], r13
0x1801a35dc  mov     [r14+21B0h], r13
0x1801a35e3  mov     [r14+21B8h], r13
0x1801a35ea  mov     [r14+21C0h], r13
0x1801a35f1  mov     [r14+21C8h], r13
0x1801a35f8  lea     rax, ??_7DelayLoadWindowsGlobalization@Js@@6B@; const Js::DelayLoadWindowsGlobalization::`vftable'
0x1801a35ff  mov     [r14+2188h], rax
0x1801a3606  mov     [r14+21D0h], r13
0x1801a360d  mov     [r14+21D8h], r13
0x1801a3614  mov     [r14+21E0h], r13d
0x1801a361b  lea     rax, [r14+21E8h]
0x1801a3622  mov     [rbp+57h+var_A0], rax
0x1801a3626  mov     [rax], r13
0x1801a3629  mov     [rax+8], r13
0x1801a362d  mov     [rax+10h], r13
0x1801a3631  mov     [rax+18h], r13
0x1801a3635  mov     [rax+20h], r13
0x1801a3639  mov     [rax+28h], r13
0x1801a363d  mov     [rax+30h], r13
0x1801a3641  mov     [rax+38h], r13
0x1801a3645  mov     [rax+40h], r13
0x1801a3649  mov     [r14+2238h], r13
0x1801a3650  mov     [r14+2240h], r13b
0x1801a3657  lea     rax, ??_7DelayLoadWinRtFoundation@Js@@6B@; const Js::DelayLoadWinRtFoundation::`vftable'
0x1801a365e  mov     [r14+2230h], rax
0x1801a3665  mov     [r14+2248h], r13
0x1801a366c  lea     rax, [r14+2250h]
0x1801a3673  mov     [rbp+57h+var_A0], rax
0x1801a3677  mov     [rax], r13
0x1801a367a  mov     [rax+8], r13
0x1801a367e  mov     [r14+2260h], r13d
0x1801a3685  lea     rdi, [r14+2268h]
0x1801a368c  mov     [rdi], r13
0x1801a368f  mov     [rdi+8], r13
0x1801a3693  mov     [r14+2280h], r13
0x1801a369a  mov     [r14+2288h], r13
0x1801a36a1  lea     rcx, [r14+2298h]; lpCriticalSection
0x1801a36a8  xor     edx, edx; dwSpinCount
0x1801a36aa  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1801a36b1  nop     dword ptr [rax+rax+00h]
0x1801a36b6  nop
0x1801a36b7  mov     [r14+3600h], r13d
0x1801a36be  lea     rcx, [r14+3610h]
0x1801a36c5  call    ??0?$BaseDictionary@PEBVDynamicType@Js@@PEAXUHeapAllocator@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@@JsUtil@@QEAA@PEAUHeapAllocator@@H@Z; JsUtil::BaseDictionary<Js::DynamicType const *,void *,HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::BaseDictionary<Js::DynamicType const *,void *,HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>(HeapAllocator *,int)
0x1801a36ca  nop
0x1801a36cb  lea     rsi, [r14+3640h]
0x1801a36d2  mov     [r14+3650h], rsi
0x1801a36d9  mov     [r14+3658h], r13b
0x1801a36e0  or      eax, 0FFFFFFFFh
0x1801a36e3  mov     [r14+365Ch], eax
0x1801a36ea  mov     [r14+3660h], r13d
0x1801a36f1  mov     [r14+3664h], r13b
0x1801a36f8  mov     [r14+3668h], r13
0x1801a36ff  mov     [r14+3670h], r13d
0x1801a3706  mov     [r14+3674h], eax
0x1801a370d  mov     [r14+3678h], r13
0x1801a3714  mov     [r14+3688h], r13
0x1801a371b  mov     [r14+3690h], r13
0x1801a3722  mov     [r14+3698h], r13
0x1801a3729  mov     [r14+36A0h], r13
0x1801a3730  mov     [r14+36A8h], r13
0x1801a3737  mov     [r14+36B0h], r13d
0x1801a373e  mov     [r14+36B8h], rbx
0x1801a3745  lea     rax, ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x1801a374c  mov     [rbp+57h+var_A0], rax
0x1801a3750  mov     [rbp+57h+var_98], r13d
0x1801a3754  mov     eax, [rbp+57h+var_94]
0x1801a3757  mov     [rbp+57h+var_94], eax
0x1801a375a  lea     r8, [rbp+57h+var_A0]
0x1801a375e  mov     rdx, rbx
0x1801a3761  lea     ecx, [r13+28h]
0x1801a3765  call    ??$?2VArenaAllocator@@@@YAPEAX_KPEAVArenaAllocator@@P80@EAAPEAD0@Z@Z; operator new<ArenaAllocator>(unsigned __int64,ArenaAllocator *,char * (ArenaAllocator::*)(unsigned __int64))
0x1801a376a  test    rax, rax
0x1801a376d  jz      short loc_1801A3780
0x1801a376f  mov     [rax+10h], r12d
0x1801a3773  mov     [rax+18h], rbx
0x1801a3777  mov     [rax], r13
0x1801a377a  mov     [rax+8], r13
0x1801a377e  jmp     short loc_1801A3783
0x1801a3780  mov     rax, r13
0x1801a3783  mov     [r14+268h], rax
0x1801a378a  lea     rax, ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x1801a3791  mov     [rbp+57h+var_A0], rax
0x1801a3795  mov     [rbp+57h+var_98], r13d
0x1801a3799  mov     eax, [rbp+57h+var_94]
0x1801a379c  mov     [rbp+57h+var_94], eax
0x1801a379f  lea     r8, [rbp+57h+var_A0]
0x1801a37a3  mov     rdx, rbx
0x1801a37a6  mov     ecx, 30h ; '0'
0x1801a37ab  call    ??$?2VArenaAllocator@@@@YAPEAX_KPEAVArenaAllocator@@P80@EAAPEAD0@Z@Z; operator new<ArenaAllocator>(unsigned __int64,ArenaAllocator *,char * (ArenaAllocator::*)(unsigned __int64))
0x1801a37b0  test    rax, rax
0x1801a37b3  jz      short loc_1801A37CA
0x1801a37b5  mov     [rax+10h], r12d
0x1801a37b9  mov     [rax+18h], rbx
0x1801a37bd  mov     [rax], r13
0x1801a37c0  mov     [rax+8], r13
0x1801a37c4  mov     [rax+28h], r13d
0x1801a37c8  jmp     short loc_1801A37CD
0x1801a37ca  mov     rax, r13
0x1801a37cd  mov     [r14+2278h], rax
0x1801a37d4  mov     [r14+6E8h], r13
0x1801a37db  mov     [r14+2291h], r13b
0x1801a37e2  mov     rcx, rdi; this
0x1801a37e5  call    ?Initialize@Entropy@@QEAAXXZ; Entropy::Initialize(void)
0x1801a37ea  lea     rax, ?AllocZero@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::AllocZero(unsigned __int64)
0x1801a37f1  mov     [rbp+57h+var_A0], rax
0x1801a37f5  mov     [rbp+57h+var_98], r13d
  ... truncated ...
```
