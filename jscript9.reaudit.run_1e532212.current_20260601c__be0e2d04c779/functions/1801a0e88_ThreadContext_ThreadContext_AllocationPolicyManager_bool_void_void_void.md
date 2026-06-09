# ThreadContext::ThreadContext(AllocationPolicyManager *,bool (*)(void (*)(void *),void *))

- ea: `0x1801a0e88`
- end: `0x1801a151b`
- name: `??0ThreadContext@@QEAA@PEAVAllocationPolicyManager@@P6A_NP6AXPEAX@Z1@Z@Z`
- size: `1683`
- prototype: `ThreadContext *__fastcall(ThreadContext *__hidden this, struct AllocationPolicyManager *, bool (*)(void (*)(void *), void *))`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18020432c`
- `0x1802c8b9c`

## callees

- `0x180066330`
- `0x180109220`
- `0x180125e3c`
- `0x180170044`
- `0x180193314`
- `0x18019c734`
- `0x1801a0e88`
- `0x1801a158c`
- `0x1801a1674`
- `0x1801a16c0`
- `0x1801a1788`
- `0x1802ad7e0`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1801a1182`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1801a136a`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1801a1182`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1801a136a`
- `KERNEL32!EnterCriticalSection` at `0x1801a14df`
- `KERNEL32!EnterCriticalSection` at `0x1801a14df`
- `KERNEL32!LeaveCriticalSection` at `0x1801a14f6`
- `KERNEL32!LeaveCriticalSection` at `0x1801a14f6`
- `KERNEL32!GetCurrentThreadId` at `0x1801a0edb`
- `KERNEL32!GetCurrentThreadId` at `0x1801a0edb`

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
  *((_BYTE *)this + 8377) = BYTE5(qword_18043CD70);
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
0x1801a0e88  mov     rax, rsp
0x1801a0e8b  mov     [rax+18h], r8
0x1801a0e8f  mov     [rax+10h], rdx
0x1801a0e93  mov     [rax+8], rcx
0x1801a0e97  push    rbp
0x1801a0e98  push    rsi
0x1801a0e99  push    rdi
0x1801a0e9a  push    r12
0x1801a0e9c  push    r13
0x1801a0e9e  push    r14
0x1801a0ea0  push    r15
0x1801a0ea2  lea     rbp, [rax-5Fh]
0x1801a0ea6  sub     rsp, 0C0h
0x1801a0ead  mov     [rbp+57h+var_B0], 0FFFFFFFFFFFFFFFEh
0x1801a0eb5  mov     [rax+20h], rbx
0x1801a0eb9  mov     r14, [rbp+57h+arg_0]
0x1801a0ebd  lea     rcx, [r14+8]; void *
0x1801a0ec1  call    ??0?$DoublyLinkedListElement@UMruListEntry@?$MruDictionary@VRegexKey@UnifiedRegex@@PEAURegexPattern@2@VRecycler@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@@JsUtil@@@JsUtil@@QEAA@XZ; JsUtil::DoublyLinkedListElement<JsUtil::MruDictionary<UnifiedRegex::RegexKey,UnifiedRegex::RegexPattern *,Recycler,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::MruListEntry>::DoublyLinkedListElement<JsUtil::MruDictionary<UnifiedRegex::RegexKey,UnifiedRegex::RegexPattern *,Recycler,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::MruListEntry>(void)
0x1801a0ec6  lea     rcx, ??_7ThreadContext@@6B@; const ThreadContext::`vftable'
0x1801a0ecd  mov     [r14], rcx
0x1801a0ed0  xor     r13d, r13d
0x1801a0ed3  mov     [r14+18h], r13
0x1801a0ed7  mov     [r14+20h], r13d
0x1801a0edb  call    cs:__imp_GetCurrentThreadId
0x1801a0ee1  mov     [r14+24h], eax
0x1801a0ee5  mov     [r14+28h], r13
0x1801a0ee9  mov     [r14+30h], r13
0x1801a0eed  mov     word ptr [r14+38h], 100h
0x1801a0ef4  mov     rdi, [rbp+57h+arg_8]
0x1801a0ef8  mov     [r14+40h], rdi
0x1801a0efc  mov     rax, [rbp+57h+arg_10]
0x1801a0f00  mov     [r14+48h], rax
0x1801a0f04  mov     [r14+50h], r13b
0x1801a0f08  mov     [r14+58h], r13d
0x1801a0f0c  lea     rbx, [r14+60h]
0x1801a0f10  mov     rcx, rbx; this
0x1801a0f13  call    ??0BackgroundPageQueue@PageAllocator@@QEAA@XZ; PageAllocator::BackgroundPageQueue::BackgroundPageQueue(void)
0x1801a0f18  nop
0x1801a0f19  lea     rsi, [r14+0A0h]
0x1801a0f20  mov     qword ptr [rsp+0F0h+var_C0], rbx
0x1801a0f25  mov     byte ptr [rsp+0F0h+var_C8], r13b
0x1801a0f2a  mov     [rsp+0F0h+var_D0], 400h
0x1801a0f33  mov     rdx, rdi
0x1801a0f36  mov     rcx, rsi
0x1801a0f39  call    ??0IdleDecommitPageAllocator@@QEAA@PEAVAllocationPolicyManager@@W4PageAllocatorType@@_K2_NPEAUBackgroundPageQueue@PageAllocator@@@Z; IdleDecommitPageAllocator::IdleDecommitPageAllocator(AllocationPolicyManager *,PageAllocatorType,unsigned __int64,unsigned __int64,bool,PageAllocator::BackgroundPageQueue *)
0x1801a0f3e  nop
0x1801a0f3f  lea     rcx, [r14+198h]
0x1801a0f46  mov     [rsp+38h], r13b
0x1801a0f4b  mov     qword ptr [rsp+0F0h+var_C0], r13
0x1801a0f50  mov     [rsp+0F0h+var_C8], r13
0x1801a0f55  mov     byte ptr [rsp+0F0h+var_D0], r13b
0x1801a0f5a  xor     r9d, r9d
0x1801a0f5d  mov     rdx, rdi
0x1801a0f60  call    ??0PageAllocator@@QEAA@PEAVAllocationPolicyManager@@W4PageAllocatorType@@_K_NPEAUBackgroundPageQueue@0@23@Z; PageAllocator::PageAllocator(AllocationPolicyManager *,PageAllocatorType,unsigned __int64,bool,PageAllocator::BackgroundPageQueue *,unsigned __int64,bool)
0x1801a0f65  nop
0x1801a0f66  mov     [r14+240h], r13
0x1801a0f6d  mov     [r14+248h], r13
0x1801a0f74  mov     [r14+250h], r13
0x1801a0f7b  mov     [r14+258h], r13
0x1801a0f82  mov     [r14+260h], r13
0x1801a0f89  mov     [r14+270h], r13
0x1801a0f90  mov     [r14+278h], r13
0x1801a0f97  lea     rbx, [r14+680h]
0x1801a0f9e  lea     r12, ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1801a0fa5  mov     [rbx], r12
0x1801a0fa8  lea     rdi, ?RecoverUnusedMemory@MemoryHelper@Js@@SAXXZ; Js::MemoryHelper::RecoverUnusedMemory(void)
0x1801a0faf  mov     [rbx+8], rdi
0x1801a0fb3  mov     [rbx+10h], r13
0x1801a0fb7  mov     [rbx+18h], r13
0x1801a0fbb  mov     [rbx+20h], r13
0x1801a0fbf  mov     [rbx+28h], rsi
0x1801a0fc3  mov     [rbx+30h], r13
0x1801a0fc7  mov     [rbx+38h], r13b
0x1801a0fcb  mov     [rbx+40h], r13
0x1801a0fcf  mov     [rbx+48h], r13
0x1801a0fd3  mov     [rbx+50h], r13d
0x1801a0fd7  mov     [rbx+58h], r13
0x1801a0fdb  mov     [r14+6E0h], r13
0x1801a0fe2  mov     dword ptr [r14+6F0h], 800h
0x1801a0fed  mov     qword ptr [r14+6F4h], 1
0x1801a0ff8  mov     [r14+6FCh], r13d
0x1801a0fff  lea     rax, [r14+700h]
0x1801a1006  mov     [rax], rax
0x1801a1009  mov     [r14+708h], r13
0x1801a1010  mov     [r14+718h], r13
0x1801a1017  mov     [r14+720h], r13
0x1801a101e  mov     [r14+728h], r13
0x1801a1025  mov     [r14+730h], r13
0x1801a102c  mov     [r14+738h], r13
0x1801a1033  mov     [r14+740h], r13
0x1801a103a  mov     [r14+748h], r13
0x1801a1041  mov     [r14+750h], r13
0x1801a1048  mov     rax, 3FF0000000000000h
0x1801a1052  mov     [r14+758h], rax
0x1801a1059  mov     [r14+760h], r13
0x1801a1060  mov     word ptr [r14+770h], 1
0x1801a106a  mov     byte ptr [r14+772h], 1
0x1801a1072  mov     [r14+778h], r13
0x1801a1079  mov     [r14+780h], r13
0x1801a1080  mov     [r14+798h], r13d
0x1801a1087  lea     r9, [r14+7A0h]
0x1801a108e  mov     [r9], r12
0x1801a1091  mov     [r9+8], rdi
0x1801a1095  mov     [r9+10h], r13
0x1801a1099  mov     [r9+18h], r13
0x1801a109d  mov     [r9+20h], r13
0x1801a10a1  mov     [r9+28h], rsi
0x1801a10a5  mov     [r9+30h], r13
0x1801a10a9  mov     [r9+38h], r13b
0x1801a10ad  mov     [r9+40h], r13
0x1801a10b1  mov     [r9+48h], r13
0x1801a10b5  mov     [r9+50h], r13d
0x1801a10b9  mov     [r9+58h], r13
0x1801a10bd  lea     rax, [r14+800h]
0x1801a10c4  mov     [rax], rax
0x1801a10c7  mov     [rax+8], rax
0x1801a10cb  lea     rcx, [r14+810h]
0x1801a10d2  mov     [rcx], r9
0x1801a10d5  mov     dword ptr [rcx+8], 1F4h
0x1801a10dc  call    ?Init@?$HashTable@PEAUInlineCache@Js@@VArenaAllocator@@@@IEAAXXZ; HashTable<Js::InlineCache *,ArenaAllocator>::Init(void)
0x1801a10e1  nop
0x1801a10e2  lea     rcx, [r14+17C8h]
0x1801a10e9  mov     [rcx], r9
0x1801a10ec  mov     dword ptr [rcx+8], 100h
0x1801a10f3  call    ?Init@?$HashTable@PEAUInlineCache@Js@@VArenaAllocator@@@@IEAAXXZ; HashTable<Js::InlineCache *,ArenaAllocator>::Init(void)
0x1801a10f8  nop
0x1801a10f9  lea     rcx, [r14+1FE0h]
0x1801a1100  mov     rdx, r9
0x1801a1103  call    ??0?$BaseDictionary@PEAXPEAUIsInstInlineCache@Js@@VArenaAllocator@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@@JsUtil@@QEAA@PEAVArenaAllocator@@H@Z; JsUtil::BaseDictionary<void *,Js::IsInstInlineCache *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::BaseDictionary<void *,Js::IsInstInlineCache *,ArenaAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>(ArenaAllocator *,int)
0x1801a1108  nop
0x1801a1109  mov     [r14+2010h], r12
0x1801a1110  mov     [r14+2018h], rdi
0x1801a1117  mov     [r14+2020h], r13
0x1801a111e  mov     [r14+2028h], r13
0x1801a1125  mov     [r14+2030h], r13
0x1801a112c  mov     [r14+2038h], rsi
0x1801a1133  mov     [r14+2040h], r13
0x1801a113a  mov     [r14+2048h], r13b
0x1801a1141  mov     [r14+2050h], r13
0x1801a1148  mov     [r14+2058h], r13
0x1801a114f  mov     [r14+2060h], r13d
0x1801a1156  mov     [r14+2068h], r13
0x1801a115d  lea     rax, [r14+2070h]
0x1801a1164  mov     [rax], rax
0x1801a1167  mov     [rax+8], rax
0x1801a116b  lea     rax, [r14+2080h]
0x1801a1172  mov     [rax], rax
0x1801a1175  mov     [rax+8], rax
0x1801a1179  lea     rcx, [r14+2090h]; lpCriticalSection
0x1801a1180  xor     edx, edx; dwSpinCount
0x1801a1182  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1801a1188  nop
0x1801a1189  mov     [r14+20B8h], r13b
0x1801a1190  mov     al, byte ptr cs:qword_18043CD70+5
0x1801a1196  mov     [r14+20B9h], al
0x1801a119d  mov     al, cs:?Global@Configuration@Js@@2V12@A; Js::Configuration Js::Configuration::Global
0x1801a11a3  mov     [r14+20BAh], al
0x1801a11aa  lea     r12d, [r13+4]
0x1801a11ae  mov     [r14+20BCh], r12d
0x1801a11b5  mov     [r14+20C0h], r13b
0x1801a11bc  mov     [r14+20C8h], r13
0x1801a11c3  mov     [r14+20D0h], r13d
0x1801a11ca  mov     [r14+20E0h], r13
0x1801a11d1  mov     [r14+20E8h], r13b
0x1801a11d8  lea     rax, ??_7DelayLoadWinRtString@Js@@6B@; const Js::DelayLoadWinRtString::`vftable'
0x1801a11df  mov     [r14+20D8h], rax
0x1801a11e6  mov     [r14+20F0h], r13
0x1801a11ed  mov     [r14+20F8h], r13
0x1801a11f4  mov     [r14+2100h], r13
0x1801a11fb  mov     [r14+2108h], r13
0x1801a1202  mov     [r14+2110h], r13
0x1801a1209  mov     [r14+2118h], r13
0x1801a1210  mov     [r14+2128h], r13
0x1801a1217  mov     [r14+2130h], r13b
0x1801a121e  lea     rax, ??_7DelayLoadWinRtError@Js@@6B@; const Js::DelayLoadWinRtError::`vftable'
0x1801a1225  mov     [r14+2120h], rax
0x1801a122c  mov     [r14+2138h], r13
0x1801a1233  mov     [r14+2140h], r13
0x1801a123a  mov     [r14+2150h], r13
0x1801a1241  mov     [r14+2158h], r13b
0x1801a1248  lea     rax, ??_7DelayLoadWinRtTypeResolution@Js@@6B@; const Js::DelayLoadWinRtTypeResolution::`vftable'
0x1801a124f  mov     [r14+2148h], rax
0x1801a1256  mov     [r14+2160h], r13
0x1801a125d  mov     [r14+2170h], r13
0x1801a1264  mov     [r14+2178h], r13b
0x1801a126b  lea     rax, ??_7DelayLoadWinRtRoParameterizedIID@Js@@6B@; const Js::DelayLoadWinRtRoParameterizedIID::`vftable'
0x1801a1272  mov     [r14+2168h], rax
0x1801a1279  mov     [r14+2180h], r13
0x1801a1280  mov     [r14+2190h], r13
0x1801a1287  mov     [r14+2198h], r13b
0x1801a128e  mov     [r14+21A0h], r13
0x1801a1295  mov     [r14+21A8h], r13
0x1801a129c  mov     [r14+21B0h], r13
0x1801a12a3  mov     [r14+21B8h], r13
0x1801a12aa  mov     [r14+21C0h], r13
0x1801a12b1  mov     [r14+21C8h], r13
0x1801a12b8  lea     rax, ??_7DelayLoadWindowsGlobalization@Js@@6B@; const Js::DelayLoadWindowsGlobalization::`vftable'
0x1801a12bf  mov     [r14+2188h], rax
0x1801a12c6  mov     [r14+21D0h], r13
0x1801a12cd  mov     [r14+21D8h], r13
0x1801a12d4  mov     [r14+21E0h], r13d
0x1801a12db  lea     rax, [r14+21E8h]
0x1801a12e2  mov     [rbp+57h+var_A0], rax
0x1801a12e6  mov     [rax], r13
0x1801a12e9  mov     [rax+8], r13
0x1801a12ed  mov     [rax+10h], r13
0x1801a12f1  mov     [rax+18h], r13
0x1801a12f5  mov     [rax+20h], r13
0x1801a12f9  mov     [rax+28h], r13
0x1801a12fd  mov     [rax+30h], r13
0x1801a1301  mov     [rax+38h], r13
0x1801a1305  mov     [rax+40h], r13
0x1801a1309  mov     [r14+2238h], r13
0x1801a1310  mov     [r14+2240h], r13b
0x1801a1317  lea     rax, ??_7DelayLoadWinRtFoundation@Js@@6B@; const Js::DelayLoadWinRtFoundation::`vftable'
0x1801a131e  mov     [r14+2230h], rax
0x1801a1325  mov     [r14+2248h], r13
0x1801a132c  lea     rax, [r14+2250h]
0x1801a1333  mov     [rbp+57h+var_A0], rax
0x1801a1337  mov     [rax], r13
0x1801a133a  mov     [rax+8], r13
0x1801a133e  mov     [r14+2260h], r13d
0x1801a1345  lea     rdi, [r14+2268h]
0x1801a134c  mov     [rdi], r13
0x1801a134f  mov     [rdi+8], r13
0x1801a1353  mov     [r14+2280h], r13
0x1801a135a  mov     [r14+2288h], r13
0x1801a1361  lea     rcx, [r14+2298h]; lpCriticalSection
0x1801a1368  xor     edx, edx; dwSpinCount
0x1801a136a  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1801a1370  nop
0x1801a1371  mov     [r14+3600h], r13d
0x1801a1378  lea     rcx, [r14+3610h]
0x1801a137f  call    ??0?$BaseDictionary@PEBVDynamicType@Js@@PEAXUHeapAllocator@@U?$DictionarySizePolicy@UPowerOf2Policy@@$01$01$00$03@@UDefaultComparer@@VSimpleDictionaryEntry@JsUtil@@@JsUtil@@QEAA@PEAUHeapAllocator@@H@Z; JsUtil::BaseDictionary<Js::DynamicType const *,void *,HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>::BaseDictionary<Js::DynamicType const *,void *,HeapAllocator,DictionarySizePolicy<PowerOf2Policy,2,2,1,4>,DefaultComparer,JsUtil::SimpleDictionaryEntry>(HeapAllocator *,int)
0x1801a1384  nop
0x1801a1385  lea     rsi, [r14+3640h]
0x1801a138c  mov     [r14+3650h], rsi
0x1801a1393  mov     [r14+3658h], r13b
0x1801a139a  or      eax, 0FFFFFFFFh
0x1801a139d  mov     [r14+365Ch], eax
0x1801a13a4  mov     [r14+3660h], r13d
0x1801a13ab  mov     [r14+3664h], r13b
0x1801a13b2  mov     [r14+3668h], r13
0x1801a13b9  mov     [r14+3670h], r13d
0x1801a13c0  mov     [r14+3674h], eax
0x1801a13c7  mov     [r14+3678h], r13
0x1801a13ce  mov     [r14+3688h], r13
0x1801a13d5  mov     [r14+3690h], r13
0x1801a13dc  mov     [r14+3698h], r13
0x1801a13e3  mov     [r14+36A0h], r13
0x1801a13ea  mov     [r14+36A8h], r13
0x1801a13f1  mov     [r14+36B0h], r13d
0x1801a13f8  mov     [r14+36B8h], rbx
0x1801a13ff  lea     rax, ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x1801a1406  mov     [rbp+57h+var_A0], rax
0x1801a140a  mov     [rbp+57h+var_98], r13d
0x1801a140e  mov     eax, [rbp+57h+var_94]
0x1801a1411  mov     [rbp+57h+var_94], eax
0x1801a1414  lea     r8, [rbp+57h+var_A0]
0x1801a1418  mov     rdx, rbx
0x1801a141b  lea     ecx, [r13+28h]
0x1801a141f  call    ??$?2VArenaAllocator@@@@YAPEAX_KPEAVArenaAllocator@@P80@EAAPEAD0@Z@Z; operator new<ArenaAllocator>(unsigned __int64,ArenaAllocator *,char * (ArenaAllocator::*)(unsigned __int64))
0x1801a1424  test    rax, rax
0x1801a1427  jz      short loc_1801A143A
0x1801a1429  mov     [rax+10h], r12d
0x1801a142d  mov     [rax+18h], rbx
0x1801a1431  mov     [rax], r13
0x1801a1434  mov     [rax+8], r13
0x1801a1438  jmp     short loc_1801A143D
0x1801a143a  mov     rax, r13
0x1801a143d  mov     [r14+268h], rax
0x1801a1444  lea     rax, ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x1801a144b  mov     [rbp+57h+var_A0], rax
0x1801a144f  mov     [rbp+57h+var_98], r13d
0x1801a1453  mov     eax, [rbp+57h+var_94]
0x1801a1456  mov     [rbp+57h+var_94], eax
0x1801a1459  lea     r8, [rbp+57h+var_A0]
0x1801a145d  mov     rdx, rbx
0x1801a1460  mov     ecx, 30h ; '0'
0x1801a1465  call    ??$?2VArenaAllocator@@@@YAPEAX_KPEAVArenaAllocator@@P80@EAAPEAD0@Z@Z; operator new<ArenaAllocator>(unsigned __int64,ArenaAllocator *,char * (ArenaAllocator::*)(unsigned __int64))
0x1801a146a  test    rax, rax
0x1801a146d  jz      short loc_1801A1484
0x1801a146f  mov     [rax+10h], r12d
0x1801a1473  mov     [rax+18h], rbx
0x1801a1477  mov     [rax], r13
0x1801a147a  mov     [rax+8], r13
0x1801a147e  mov     [rax+28h], r13d
0x1801a1482  jmp     short loc_1801A1487
0x1801a1484  mov     rax, r13
0x1801a1487  mov     [r14+2278h], rax
0x1801a148e  mov     [r14+6E8h], r13
0x1801a1495  mov     [r14+2291h], r13b
0x1801a149c  mov     rcx, rdi; this
0x1801a149f  call    ?Initialize@Entropy@@QEAAXXZ; Entropy::Initialize(void)
0x1801a14a4  lea     rax, ?AllocZero@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::AllocZero(unsigned __int64)
0x1801a14ab  mov     [rbp+57h+var_A0], rax
0x1801a14af  mov     [rbp+57h+var_98], r13d
0x1801a14b3  mov     eax, [rbp+57h+var_94]
0x1801a14b6  mov     [rbp+57h+var_94], eax
0x1801a14b9  mov     r8d, 21h ; '!'
  ... truncated ...
```
