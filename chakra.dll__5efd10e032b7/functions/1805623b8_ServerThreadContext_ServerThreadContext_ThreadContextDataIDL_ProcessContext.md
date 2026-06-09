# ServerThreadContext::ServerThreadContext(ThreadContextDataIDL *,ProcessContext *)

- ea: `0x1805623b8`
- end: `0x180562627`
- name: `??0ServerThreadContext@@QEAA@PEAUThreadContextDataIDL@@PEAVProcessContext@@@Z`
- size: `623`
- prototype: `ServerThreadContext *__fastcall(ServerThreadContext *__hidden this, struct ThreadContextDataIDL *, struct ProcessContext *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18055fe10`

## callees

- `0x1800319f8`
- `0x180278840`
- `0x1802efb90`
- `0x1802f0664`
- `0x18033aa8c`
- `0x180560a78`
- `0x1805622c4`
- `0x1805623b8`
- `0x1805a9c5a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180562435`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1805625a1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180562435`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1805625a1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1805625c7`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1805625c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1805624cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1805624cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
ServerThreadContext *__fastcall ServerThreadContext::ServerThreadContext(
        ServerThreadContext *this,
        struct ThreadContextDataIDL *a2,
        struct ProcessContext *a3)
{
  __int64 v4; // rbx
  int v5; // edx
  int v6; // r8d
  int v7; // edx
  AutoSystemInfo *v8; // rcx
  __int64 v9; // r8
  _QWORD *v10; // rax
  unsigned __int64 v12[7]; // [rsp+70h] [rbp-38h] BYREF

  v12[1] = -2;
  ThreadContextInfo::ThreadContextInfo(this);
  *(_QWORD *)this = &ServerThreadContext::`vftable';
  *((_QWORD *)this + 13) = a3;
  *((_QWORD *)this + 14) = 0;
  v4 = *((_QWORD *)a3 + 1);
  `vector constructor iterator'((char *)this + 120, 8u, 0x40u, (void *(*)(void *))Js::TickDelta::TickDelta);
  *((_QWORD *)this + 79) = 0;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 16, 0xFA0u);
  *((_QWORD *)this + 85) = v4;
  *((_QWORD *)this + 86) = 0;
  memset_0((char *)this + 120, -1, 0x200u);
  *((_QWORD *)this + 87) = *((_QWORD *)a3 + 1);
  *((_QWORD *)this + 88) = 0;
  Memory::CustomHeap::CodePageAllocators<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper>::CodePageAllocators<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper>(
    (_DWORD)this + 712,
    v5,
    0,
    (_DWORD)this + 696,
    0,
    *((_QWORD *)a3 + 1));
  LOBYTE(v6) = 1;
  Memory::CustomHeap::CodePageAllocators<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper>::CodePageAllocators<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper>(
    (_DWORD)this + 1296,
    v7,
    v6,
    (_DWORD)this + 696,
    (__int64)this + 120,
    *((_QWORD *)a3 + 1));
  JITThunkEmitter<Memory::SectionAllocWrapper>::JITThunkEmitter<Memory::SectionAllocWrapper>(
    (char *)this + 1880,
    this,
    (char *)this + 696,
    *((_QWORD *)a3 + 1));
  GetCurrentProcess();
  v12[0] = -1;
  AutoSystemInfo::GetAvailableCommit(v8, v12);
  Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>(
    (_DWORD)this + 5160,
    0,
    (unsigned int)&Js::Configuration::Global,
    3,
    v12[0] <= 0xB900000 ? 256 : 1024,
    0,
    0,
    32,
    0,
    0,
    0,
    v9,
    0);
  *(_OWORD *)((char *)this + 5416) = *(_OWORD *)a2;
  *(_OWORD *)((char *)this + 5432) = *((_OWORD *)a2 + 1);
  *(_OWORD *)((char *)this + 5448) = *((_OWORD *)a2 + 2);
  *(_OWORD *)((char *)this + 5464) = *((_OWORD *)a2 + 3);
  *((_QWORD *)this + 685) = *((_QWORD *)a2 + 8);
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 5496), 0);
  *((_DWORD *)this + 1384) = 0;
  *((_BYTE *)this + 5540) = *((_BYTE *)a2 + 1) != 0;
  *((_DWORD *)this + 1372) = GetProcessId(*((HANDLE *)a3 + 1));
  v10 = (_QWORD *)operator new<Memory::HeapAllocator>(
                    32,
                    &Memory::HeapAllocator::Instance,
                    Memory::HeapAllocator::Alloc);
  v12[0] = (unsigned __int64)v10;
  if ( v10 )
  {
    *v10 = 0;
    v10[1] = 0;
    v10[2] = &Memory::HeapAllocator::Instance;
    v10[3] = v10;
  }
  else
  {
    v10 = 0;
  }
  *((_QWORD *)this + 14) = v10;
  return this;
}

```

## disassembly

```asm
0x1805623b8  mov     rax, rsp
0x1805623bb  mov     [rax+18h], r8
0x1805623bf  mov     [rax+10h], rdx
0x1805623c3  mov     [rax+8], rcx
0x1805623c7  push    rbx
0x1805623c8  push    rsi
0x1805623c9  push    rdi
0x1805623ca  push    r14
0x1805623cc  push    r15
0x1805623ce  sub     rsp, 80h
0x1805623d5  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFEh
0x1805623dd  mov     r14, rcx
0x1805623e0  call    ??0ThreadContextInfo@@QEAA@XZ; ThreadContextInfo::ThreadContextInfo(void)
0x1805623e5  nop
0x1805623e6  lea     rax, ??_7ServerThreadContext@@6B@; const ServerThreadContext::`vftable'
0x1805623ed  mov     [r14], rax
0x1805623f0  mov     rsi, [rsp+0A8h+arg_10]
0x1805623f8  mov     [r14+68h], rsi
0x1805623fc  xor     r15d, r15d
0x1805623ff  mov     [r14+70h], r15
0x180562403  lea     rdi, [r14+78h]
0x180562407  mov     rbx, [rsi+8]
0x18056240b  lea     r9, ??0TickDelta@Js@@QEAA@XZ; void *(*)(void *)
0x180562412  lea     edx, [r15+8]; unsigned __int64
0x180562416  lea     r8d, [r15+40h]; unsigned __int64
0x18056241a  mov     rcx, rdi; void *
0x18056241d  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180562422  mov     [rdi+200h], r15
0x180562429  lea     rcx, [rdi+208h]; lpCriticalSection
0x180562430  mov     edx, 0FA0h; dwSpinCount
0x180562435  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18056243c  nop     dword ptr [rax+rax+00h]
0x180562441  mov     [rdi+230h], rbx
0x180562448  mov     [rdi+238h], r15
0x18056244f  mov     r8d, 200h; Size
0x180562455  or      edx, 0FFFFFFFFh; Val
0x180562458  mov     rcx, rdi; void *
0x18056245b  call    memset_0
0x180562460  nop
0x180562461  lea     rbx, [r14+2B8h]
0x180562468  mov     rax, [rsi+8]
0x18056246c  mov     [rbx], rax
0x18056246f  mov     [rbx+8], r15
0x180562473  lea     rcx, [r14+2C8h]
0x18056247a  mov     rax, [rsi+8]
0x18056247e  mov     [rsp+0A8h+var_80], rax
0x180562483  mov     [rsp+0A8h+var_88], r15
0x180562488  mov     r9, rbx
0x18056248b  xor     r8d, r8d
0x18056248e  call    ??0?$CodePageAllocators@VSectionAllocWrapper@Memory@@VPreReservedSectionAllocWrapper@2@@CustomHeap@Memory@@QEAA@PEAVAllocationPolicyManager@@_NPEAVSectionAllocWrapper@2@PEAVPreReservedSectionAllocWrapper@2@PEAX@Z; Memory::CustomHeap::CodePageAllocators<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper>::CodePageAllocators<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper>(AllocationPolicyManager *,bool,Memory::SectionAllocWrapper *,Memory::PreReservedSectionAllocWrapper *,void *)
0x180562493  nop
0x180562494  lea     rcx, [r14+510h]
0x18056249b  mov     rax, [rsi+8]
0x18056249f  mov     [rsp+0A8h+var_80], rax
0x1805624a4  mov     [rsp+0A8h+var_88], rdi
0x1805624a9  mov     r9, rbx
0x1805624ac  mov     r8b, 1
0x1805624af  call    ??0?$CodePageAllocators@VSectionAllocWrapper@Memory@@VPreReservedSectionAllocWrapper@2@@CustomHeap@Memory@@QEAA@PEAVAllocationPolicyManager@@_NPEAVSectionAllocWrapper@2@PEAVPreReservedSectionAllocWrapper@2@PEAX@Z; Memory::CustomHeap::CodePageAllocators<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper>::CodePageAllocators<Memory::SectionAllocWrapper,Memory::PreReservedSectionAllocWrapper>(AllocationPolicyManager *,bool,Memory::SectionAllocWrapper *,Memory::PreReservedSectionAllocWrapper *,void *)
0x1805624b4  nop
0x1805624b5  lea     rcx, [r14+758h]
0x1805624bc  mov     r9, [rsi+8]
0x1805624c0  mov     r8, rbx
0x1805624c3  mov     rdx, r14
0x1805624c6  call    ??0?$JITThunkEmitter@VSectionAllocWrapper@Memory@@@@QEAA@PEAVThreadContextInfo@@PEAVSectionAllocWrapper@Memory@@PEAX@Z; JITThunkEmitter<Memory::SectionAllocWrapper>::JITThunkEmitter<Memory::SectionAllocWrapper>(ThreadContextInfo *,Memory::SectionAllocWrapper *,void *)
0x1805624cb  nop
0x1805624cc  call    cs:__imp_GetCurrentProcess
0x1805624d3  nop     dword ptr [rax+rax+00h]
0x1805624d8  mov     r8, rax
0x1805624db  mov     [rsp+0A8h+var_38], 0FFFFFFFFFFFFFFFFh
0x1805624e4  lea     rdx, [rsp+0A8h+var_38]; unsigned __int64 *
0x1805624e9  call    ?GetAvailableCommit@AutoSystemInfo@@QEAAHPEA_K@Z; AutoSystemInfo::GetAvailableCommit(unsigned __int64 *)
0x1805624ee  cmp     [rsp+0A8h+var_38], 0B900000h
0x1805624f7  setbe   al
0x1805624fa  neg     al
0x1805624fc  sbb     edx, edx
0x1805624fe  and     edx, 0FFFFFD00h
0x180562504  add     edx, 400h
0x18056250a  lea     rcx, [r14+1428h]
0x180562511  mov     [rsp+0A8h+var_48], r15b
0x180562516  mov     [rsp+0A8h+var_50], r8
0x18056251b  mov     [rsp+0A8h+var_58], r15b
0x180562520  mov     [rsp+0A8h+var_60], r15b
0x180562525  mov     [rsp+0A8h+var_68], r15d
0x18056252a  lea     edi, [r15+20h]
0x18056252e  mov     [rsp+0A8h+var_70], edi
0x180562532  mov     [rsp+0A8h+var_78], r15
0x180562537  mov     byte ptr [rsp+0A8h+var_80], r15b
0x18056253c  mov     dword ptr [rsp+0A8h+var_88], edx
0x180562540  lea     r9d, [r15+3]
0x180562544  lea     r8, ?Global@Configuration@Js@@2V12@A; Js::Configuration Js::Configuration::Global
0x18056254b  xor     edx, edx
0x18056254d  call    ??0?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@QEAA@PEAVAllocationPolicyManager@@AEAVConfigFlagsTable@Js@@W4PageAllocatorType@@I_NPEAUBackgroundPageQueue@01@II33PEAX3@Z; Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>(AllocationPolicyManager *,Js::ConfigFlagsTable &,PageAllocatorType,uint,bool,Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::BackgroundPageQueue *,uint,uint,bool,bool,void *,bool)
0x180562552  nop
0x180562553  mov     rbx, [rsp+0A8h+arg_8]
0x18056255b  movups  xmm0, xmmword ptr [rbx]
0x18056255e  movups  xmmword ptr [r14+1528h], xmm0
0x180562566  movups  xmm1, xmmword ptr [rbx+10h]
0x18056256a  movups  xmmword ptr [r14+1538h], xmm1
0x180562572  movups  xmm0, xmmword ptr [rbx+20h]
0x180562576  movups  xmmword ptr [r14+1548h], xmm0
0x18056257e  movups  xmm1, xmmword ptr [rbx+30h]
0x180562582  movups  xmmword ptr [r14+1558h], xmm1
0x18056258a  movsd   xmm0, qword ptr [rbx+40h]
0x18056258f  movsd   qword ptr [r14+1568h], xmm0
0x180562598  lea     rcx, [r14+1578h]; lpCriticalSection
0x18056259f  xor     edx, edx; dwSpinCount
0x1805625a1  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1805625a8  nop     dword ptr [rax+rax+00h]
0x1805625ad  nop
0x1805625ae  mov     [r14+15A0h], r15d
0x1805625b5  cmp     [rbx+1], r15b
0x1805625b9  setnz   al
0x1805625bc  mov     [r14+15A4h], al
0x1805625c3  mov     rcx, [rsi+8]; Process
0x1805625c7  call    cs:__imp_GetProcessId
0x1805625ce  nop     dword ptr [rax+rax+00h]
0x1805625d3  mov     [r14+1570h], eax
0x1805625da  lea     r8, ?Alloc@HeapAllocator@Memory@@QEAAPEAD_K@Z; Memory::HeapAllocator::Alloc(unsigned __int64)
0x1805625e1  lea     rbx, ?Instance@HeapAllocator@Memory@@2U12@A; Memory::HeapAllocator Memory::HeapAllocator::Instance
0x1805625e8  mov     rdx, rbx
0x1805625eb  mov     ecx, edi
0x1805625ed  call    ??$?2UHeapAllocator@Memory@@@@YAPEAX_KPEAUHeapAllocator@Memory@@P801@EAAPEAD0@Z@Z; operator new<Memory::HeapAllocator>(unsigned __int64,Memory::HeapAllocator *,char * (Memory::HeapAllocator::*)(unsigned __int64))
0x1805625f2  mov     [rsp+0A8h+var_38], rax
0x1805625f7  test    rax, rax
0x1805625fa  jz      short loc_18056260D
0x1805625fc  mov     [rax], r15
0x1805625ff  mov     [rax+8], r15
0x180562603  mov     [rax+10h], rbx
0x180562607  mov     [rax+18h], rax
0x18056260b  jmp     short loc_180562610
0x18056260d  mov     rax, r15
0x180562610  mov     [r14+70h], rax
0x180562614  mov     rax, r14
0x180562617  add     rsp, 80h
0x18056261e  pop     r15
0x180562620  pop     r14
0x180562622  pop     rdi
0x180562623  pop     rsi
0x180562624  pop     rbx
0x180562625  retn
```
