# JsUtil::BackgroundJobProcessor::BackgroundJobProcessor(AllocationPolicyManager *,JsUtil::ThreadService *)

- ea: `0x180184eb0`
- end: `0x18018500a`
- name: `??0BackgroundJobProcessor@JsUtil@@QEAA@PEAVAllocationPolicyManager@@PEAVThreadService@1@@Z`
- size: `346`
- prototype: `__int64 __fastcall(JsUtil::BackgroundJobProcessor *__hidden this, struct AllocationPolicyManager *, struct JsUtil::ThreadService *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180110690`
- `0x1802c8d4c`

## callees

- `0x180110cfc`
- `0x180184eb0`
- `0x1801a158c`
- `0x1801aa070`
- `0x1801ad274`
- `0x1801b25fc`
- `0x18035e010`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x180184fa5`
- `msvcrt!_beginthreadex` at `0x180184fa5`
- `KERNEL32!ResumeThread` at `0x180184fc0`
- `KERNEL32!ResumeThread` at `0x180184fc0`
- `KERNEL32!ResetEvent` at `0x180184ff0`
- `KERNEL32!ResetEvent` at `0x180184ff0`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180184f27`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180184f27`
- `KERNEL32!CloseHandle` at `0x180184fd6`
- `KERNEL32!CloseHandle` at `0x180184fd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
JsUtil::BackgroundJobProcessor *__fastcall JsUtil::BackgroundJobProcessor::BackgroundJobProcessor(
        JsUtil::BackgroundJobProcessor *this,
        struct AllocationPolicyManager *a2,
        struct JsUtil::ThreadService *a3)
{
  bool v4; // dl
  bool v5; // r8
  bool v6; // dl
  bool v7; // r8
  void *v8; // rax
  char InitFlag; // [rsp+20h] [rbp-48h]
  char v11; // [rsp+38h] [rbp-30h]

  *((_BYTE *)this + 8) = 1;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_BYTE *)this + 48) = 0;
  *(_QWORD *)this = &JsUtil::BackgroundJobProcessor::`vftable';
  v11 = 0;
  InitFlag = 0;
  PageAllocator::PageAllocator((char *)this + 56, a2, a3, 1024, InitFlag, 0, 0, v11, -2);
  *((_QWORD *)this + 28) = 0;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 232), 0);
  *((_BYTE *)this + 272) = 0;
  Event::Event((JsUtil::BackgroundJobProcessor *)((char *)this + 280), v4, v5);
  *((_DWORD *)this + 72) = 0;
  *((_QWORD *)this + 37) = 0;
  Event::Event((JsUtil::BackgroundJobProcessor *)((char *)this + 304), v6, v7);
  *((_QWORD *)this + 39) = GetCurrentThreadContextId();
  *((_QWORD *)this + 40) = a3;
  if ( JsUtil::ThreadService::HasCallback(a3) )
  {
    *((_BYTE *)this + 272) = 1;
  }
  else
  {
    v8 = (void *)_beginthreadex(0, 0, JsUtil::BackgroundJobProcessor::StaticThreadProc, this, 4u, 0);
    *((_QWORD *)this + 28) = v8;
    if ( !v8 )
      Js::Throw::OutOfMemory();
    if ( ResumeThread(v8) == -1 )
    {
      CloseHandle(*((HANDLE *)this + 28));
      Js::Throw::OutOfMemory();
    }
    JsUtil::BackgroundJobProcessor::WaitWithThread(
      this,
      (JsUtil::BackgroundJobProcessor *)((char *)this + 304),
      0xFFFFFFFF);
    ResetEvent(*((HANDLE *)this + 38));
  }
  return this;
}

```

## disassembly

```asm
0x180184eb0  mov     r11, rsp
0x180184eb3  mov     [r11+18h], r8
0x180184eb7  mov     [r11+10h], rdx
0x180184ebb  mov     [r11+8], rcx
0x180184ebf  push    rbx
0x180184ec0  push    rsi
0x180184ec1  push    rdi
0x180184ec2  sub     rsp, 50h
0x180184ec6  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x180184ece  mov     rbx, rcx
0x180184ed1  mov     byte ptr [rcx+8], 1
0x180184ed5  xor     esi, esi
0x180184ed7  mov     [rcx+10h], rsi
0x180184edb  mov     [rcx+18h], rsi
0x180184edf  mov     [rcx+20h], rsi
0x180184ee3  mov     [rcx+28h], rsi
0x180184ee7  mov     [rcx+30h], sil
0x180184eeb  lea     rax, ??_7BackgroundJobProcessor@JsUtil@@6B@; const JsUtil::BackgroundJobProcessor::`vftable'
0x180184ef2  mov     [rcx], rax
0x180184ef5  lea     rcx, [rcx+38h]
0x180184ef9  mov     [rsp+68h+var_30], sil
0x180184efe  mov     [r11-38h], rsi
0x180184f02  mov     [r11-40h], rsi
0x180184f06  mov     [rsp+68h+InitFlag], sil
0x180184f0b  mov     r9d, 400h
0x180184f11  call    ??0PageAllocator@@QEAA@PEAVAllocationPolicyManager@@W4PageAllocatorType@@_K_NPEAUBackgroundPageQueue@0@23@Z; PageAllocator::PageAllocator(AllocationPolicyManager *,PageAllocatorType,unsigned __int64,bool,PageAllocator::BackgroundPageQueue *,unsigned __int64,bool)
0x180184f16  nop
0x180184f17  mov     [rbx+0E0h], rsi
0x180184f1e  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x180184f25  xor     edx, edx; dwSpinCount
0x180184f27  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180184f2d  nop
0x180184f2e  mov     [rbx+110h], sil
0x180184f35  lea     rcx, [rbx+118h]; this
0x180184f3c  call    ??0Event@@QEAA@_N0@Z; Event::Event(bool,bool)
0x180184f41  nop
0x180184f42  mov     [rbx+120h], esi
0x180184f48  mov     [rbx+128h], rsi
0x180184f4f  lea     rdi, [rbx+130h]
0x180184f56  mov     rcx, rdi; this
0x180184f59  call    ??0Event@@QEAA@_N0@Z; Event::Event(bool,bool)
0x180184f5e  nop
0x180184f5f  mov     rax, cs:?GetCurrentThreadContextId@@3P6APEAXXZEA; void * (*GetCurrentThreadContextId)(void)
0x180184f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184f6b  mov     [rbx+138h], rax
0x180184f72  mov     rcx, [rsp+68h+arg_10]; this
0x180184f7a  mov     [rbx+140h], rcx
0x180184f81  call    ?HasCallback@ThreadService@JsUtil@@QEBA_NXZ; JsUtil::ThreadService::HasCallback(void)
0x180184f86  test    al, al
0x180184f88  jnz     short loc_180184FF8
0x180184f8a  mov     [rsp+68h+ThrdAddr], rsi; ThrdAddr
0x180184f8f  mov     dword ptr [rsp+68h+InitFlag], 4; InitFlag
0x180184f97  mov     r9, rbx; ArgList
0x180184f9a  lea     r8, ?StaticThreadProc@BackgroundJobProcessor@JsUtil@@CAIPEAX@Z; StartAddress
0x180184fa1  xor     edx, edx; StackSize
0x180184fa3  xor     ecx, ecx; Security
0x180184fa5  call    cs:__imp__beginthreadex
0x180184fab  mov     [rbx+0E0h], rax
0x180184fb2  test    rax, rax
0x180184fb5  jnz     short loc_180184FBD
0x180184fb7  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x180184fbd  mov     rcx, rax; hThread
0x180184fc0  call    cs:__imp_ResumeThread
0x180184fc6  or      r8d, 0FFFFFFFFh; unsigned int
0x180184fca  cmp     eax, r8d
0x180184fcd  jnz     short loc_180184FE2
0x180184fcf  mov     rcx, [rbx+0E0h]; hObject
0x180184fd6  call    cs:__imp_CloseHandle
0x180184fdc  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x180184fe2  mov     rdx, rdi; struct Event *
0x180184fe5  mov     rcx, rbx; this
0x180184fe8  call    ?WaitWithThread@BackgroundJobProcessor@JsUtil@@AEAA_NAEBVEvent@@I@Z; JsUtil::BackgroundJobProcessor::WaitWithThread(Event const &,uint)
0x180184fed  mov     rcx, [rdi]; hEvent
0x180184ff0  call    cs:__imp_ResetEvent
0x180184ff6  jmp     short loc_180184FFF
0x180184ff8  mov     byte ptr [rbx+110h], 1
0x180184fff  mov     rax, rbx
0x180185002  add     rsp, 50h
0x180185006  pop     rdi
0x180185007  pop     rsi
0x180185008  pop     rbx
0x180185009  retn
```
