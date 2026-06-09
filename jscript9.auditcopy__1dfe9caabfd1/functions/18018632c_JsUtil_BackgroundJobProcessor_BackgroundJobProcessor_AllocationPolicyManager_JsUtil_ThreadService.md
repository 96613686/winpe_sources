# JsUtil::BackgroundJobProcessor::BackgroundJobProcessor(AllocationPolicyManager *,JsUtil::ThreadService *)

- ea: `0x18018632c`
- end: `0x1801864a9`
- name: `??0BackgroundJobProcessor@JsUtil@@QEAA@PEAVAllocationPolicyManager@@PEAVThreadService@1@@Z`
- size: `381`
- prototype: `JsUtil::BackgroundJobProcessor *__fastcall(JsUtil::BackgroundJobProcessor *this, struct AllocationPolicyManager *, struct JsUtil::ThreadService *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18001fac0`
- `0x1802ce4dc`

## callees

- `0x18001f668`
- `0x18018632c`
- `0x1801a38dc`
- `0x1801acd90`
- `0x1801af678`
- `0x1801b4ac0`
- `0x180364010`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x18018642b`
- `msvcrt!_beginthreadex` at `0x18018642b`
- `KERNEL32!ResumeThread` at `0x18018644c`
- `KERNEL32!ResumeThread` at `0x18018644c`
- `KERNEL32!ResetEvent` at `0x180186488`
- `KERNEL32!ResetEvent` at `0x180186488`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1801863a3`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1801863a3`
- `KERNEL32!CloseHandle` at `0x180186468`
- `KERNEL32!CloseHandle` at `0x180186468`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
JsUtil::BackgroundJobProcessor *__fastcall JsUtil::BackgroundJobProcessor::BackgroundJobProcessor(
        JsUtil::BackgroundJobProcessor *this,
        struct AllocationPolicyManager *a2,
        struct JsUtil::ThreadService *a3)
{
  void *v4; // rax

  *((_BYTE *)this + 8) = 1;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_BYTE *)this + 48) = 0;
  *(_QWORD *)this = &JsUtil::BackgroundJobProcessor::`vftable';
  PageAllocator::PageAllocator((__int64)this + 56, (__int64)a2, (__int64)a3, 1024, 0, 0, 0, 0);
  *((_QWORD *)this + 28) = 0;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 232), 0);
  *((_BYTE *)this + 272) = 0;
  Event::Event((JsUtil::BackgroundJobProcessor *)((char *)this + 280));
  *((_DWORD *)this + 72) = 0;
  *((_QWORD *)this + 37) = 0;
  Event::Event((JsUtil::BackgroundJobProcessor *)((char *)this + 304));
  *((_QWORD *)this + 39) = GetCurrentThreadContextId();
  *((_QWORD *)this + 40) = a3;
  if ( JsUtil::ThreadService::HasCallback(a3) )
  {
    *((_BYTE *)this + 272) = 1;
  }
  else
  {
    v4 = (void *)_beginthreadex(
                   0,
                   0,
                   (_beginthreadex_proc_type)JsUtil::BackgroundJobProcessor::StaticThreadProc,
                   this,
                   4u,
                   0);
    *((_QWORD *)this + 28) = v4;
    if ( !v4 )
      Js::Throw::OutOfMemory();
    if ( ResumeThread(v4) == -1 )
    {
      CloseHandle(*((HANDLE *)this + 28));
      Js::Throw::OutOfMemory();
    }
    JsUtil::BackgroundJobProcessor::WaitWithThread(this, (HANDLE *)this + 38, 0xFFFFFFFF);
    ResetEvent(*((HANDLE *)this + 38));
  }
  return this;
}

```

## disassembly

```asm
0x18018632c  mov     r11, rsp
0x18018632f  mov     [r11+18h], r8
0x180186333  mov     [r11+10h], rdx
0x180186337  mov     [r11+8], rcx
0x18018633b  push    rbx
0x18018633c  push    rsi
0x18018633d  push    rdi
0x18018633e  sub     rsp, 50h
0x180186342  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x18018634a  mov     rbx, rcx
0x18018634d  mov     byte ptr [rcx+8], 1
0x180186351  xor     esi, esi
0x180186353  mov     [rcx+10h], rsi
0x180186357  mov     [rcx+18h], rsi
0x18018635b  mov     [rcx+20h], rsi
0x18018635f  mov     [rcx+28h], rsi
0x180186363  mov     [rcx+30h], sil
0x180186367  lea     rax, ??_7BackgroundJobProcessor@JsUtil@@6B@; const JsUtil::BackgroundJobProcessor::`vftable'
0x18018636e  mov     [rcx], rax
0x180186371  lea     rcx, [rcx+38h]
0x180186375  mov     [rsp+68h+var_30], sil
0x18018637a  mov     [r11-38h], rsi
0x18018637e  mov     [r11-40h], rsi
0x180186382  mov     [rsp+68h+InitFlag], sil
0x180186387  mov     r9d, 400h
0x18018638d  call    ??0PageAllocator@@QEAA@PEAVAllocationPolicyManager@@W4PageAllocatorType@@_K_NPEAUBackgroundPageQueue@0@23@Z; PageAllocator::PageAllocator(AllocationPolicyManager *,PageAllocatorType,unsigned __int64,bool,PageAllocator::BackgroundPageQueue *,unsigned __int64,bool)
0x180186392  nop
0x180186393  mov     [rbx+0E0h], rsi
0x18018639a  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x1801863a1  xor     edx, edx; dwSpinCount
0x1801863a3  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1801863aa  nop     dword ptr [rax+rax+00h]
0x1801863af  nop
0x1801863b0  mov     [rbx+110h], sil
0x1801863b7  lea     rcx, [rbx+118h]; this
0x1801863be  call    ??0Event@@QEAA@_N0@Z; Event::Event(bool,bool)
0x1801863c3  nop
0x1801863c4  mov     [rbx+120h], esi
0x1801863ca  mov     [rbx+128h], rsi
0x1801863d1  lea     rdi, [rbx+130h]
0x1801863d8  mov     rcx, rdi; this
0x1801863db  call    ??0Event@@QEAA@_N0@Z; Event::Event(bool,bool)
0x1801863e0  nop
0x1801863e1  mov     rax, cs:?GetCurrentThreadContextId@@3P6APEAXXZEA; void * (*GetCurrentThreadContextId)(void)
0x1801863e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801863ed  mov     [rbx+138h], rax
0x1801863f4  mov     rcx, [rsp+68h+arg_10]; this
0x1801863fc  mov     [rbx+140h], rcx
0x180186403  call    ?HasCallback@ThreadService@JsUtil@@QEBA_NXZ; JsUtil::ThreadService::HasCallback(void)
0x180186408  test    al, al
0x18018640a  jnz     loc_180186496
0x180186410  mov     [rsp+68h+ThrdAddr], rsi; ThrdAddr
0x180186415  mov     dword ptr [rsp+68h+InitFlag], 4; InitFlag
0x18018641d  mov     r9, rbx; ArgList
0x180186420  lea     r8, ?StaticThreadProc@BackgroundJobProcessor@JsUtil@@CAIPEAX@Z; StartAddress
0x180186427  xor     edx, edx; StackSize
0x180186429  xor     ecx, ecx; Security
0x18018642b  call    cs:__imp__beginthreadex
0x180186432  nop     dword ptr [rax+rax+00h]
0x180186437  mov     [rbx+0E0h], rax
0x18018643e  test    rax, rax
0x180186441  jnz     short loc_180186449
0x180186443  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x180186449  mov     rcx, rax; hThread
0x18018644c  call    cs:__imp_ResumeThread
0x180186453  nop     dword ptr [rax+rax+00h]
0x180186458  or      r8d, 0FFFFFFFFh; unsigned int
0x18018645c  cmp     eax, r8d
0x18018645f  jnz     short loc_18018647A
0x180186461  mov     rcx, [rbx+0E0h]; hObject
0x180186468  call    cs:__imp_CloseHandle
0x18018646f  nop     dword ptr [rax+rax+00h]
0x180186474  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x18018647a  mov     rdx, rdi; struct Event *
0x18018647d  mov     rcx, rbx; this
0x180186480  call    ?WaitWithThread@BackgroundJobProcessor@JsUtil@@AEAA_NAEBVEvent@@I@Z; JsUtil::BackgroundJobProcessor::WaitWithThread(Event const &,uint)
0x180186485  mov     rcx, [rdi]; hEvent
0x180186488  call    cs:__imp_ResetEvent
0x18018648f  nop     dword ptr [rax+rax+00h]
0x180186494  jmp     short loc_18018649D
0x180186496  mov     byte ptr [rbx+110h], 1
0x18018649d  mov     rax, rbx
0x1801864a0  add     rsp, 50h
0x1801864a4  pop     rdi
0x1801864a5  pop     rsi
0x1801864a6  pop     rbx
0x1801864a7  retn
```
