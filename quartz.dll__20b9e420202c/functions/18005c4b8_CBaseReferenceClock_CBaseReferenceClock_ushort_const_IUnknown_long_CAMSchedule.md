# CBaseReferenceClock::CBaseReferenceClock(ushort const *,IUnknown *,long *,CAMSchedule *)

- ea: `0x18005c4b8`
- end: `0x18005c69c`
- name: `??0CBaseReferenceClock@@QEAA@PEBGPEAUIUnknown@@PEAJPEAVCAMSchedule@@@Z`
- size: `484`
- prototype: `CBaseReferenceClock *__usercall@<rax>(CBaseReferenceClock *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, struct IUnknown *@<r8>, int *@<r9>, struct CAMSchedule *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180059b70`
- `0x1800fc0bc`

## callees

- `0x180038458`
- `0x18005c4b8`
- `0x180060014`
- `0x18015e010`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x18005c633`
- `KERNEL32!SetThreadPriority` at `0x18005c633`
- `KERNEL32!CreateThread` at `0x18005c616`
- `KERNEL32!CreateThread` at `0x18005c616`
- `KERNEL32!CreateEventW` at `0x18005c55e`
- `KERNEL32!CreateEventW` at `0x18005c55e`
- `KERNEL32!InitializeCriticalSection` at `0x18005c4ef`
- `KERNEL32!InitializeCriticalSection` at `0x18005c4ef`
- `KERNEL32!CloseHandle` at `0x18005c655`
- `KERNEL32!CloseHandle` at `0x18005c655`
- `WINMM!timeGetDevCaps` at `0x18005c59f`
- `WINMM!timeGetDevCaps` at `0x18005c59f`
- `WINMM!timeBeginPeriod` at `0x18005c5ba`
- `WINMM!timeBeginPeriod` at `0x18005c5ba`
- `WINMM!timeGetTime` at `0x18005c5c6`
- `WINMM!timeGetTime` at `0x18005c5c6`

## pseudocode

```c
CBaseReferenceClock *__fastcall CBaseReferenceClock::CBaseReferenceClock(
        CBaseReferenceClock *this,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        int *a4,
        struct CAMSchedule *ThreadId)
{
  bool v7; // zf
  CAMSchedule *v8; // rax
  CAMSchedule *v9; // rdi
  HANDLE EventW; // rax
  MMRESULT DevCaps; // eax
  UINT wPeriodMin; // ecx
  DWORD Time; // eax
  HANDLE Thread; // rax
  void (__fastcall ***v15)(_QWORD, __int64); // rcx
  timecaps_tag ptc; // [rsp+48h] [rbp+10h] BYREF

  ptc = (timecaps_tag)a2;
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  if ( !a3 )
    a3 = (struct IUnknown *)this;
  *((_QWORD *)this + 1) = a3;
  *((_DWORD *)this + 4) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 1);
  v7 = ThreadId == 0;
  *(_QWORD *)this = &CBaseReferenceClock::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CWaveOutClock::`vftable'{for `IReferenceClock'};
  *((_QWORD *)this + 4) = &CBaseReferenceClock::`vftable'{for `IReferenceClockTimerControl'};
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  if ( v7 )
  {
    v8 = (CAMSchedule *)operator new(0xB8u);
    v9 = v8;
    if ( v8 )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      v8 = CAMSchedule::CAMSchedule(v9, EventW);
    }
  }
  else
  {
    v8 = ThreadId;
  }
  *((_QWORD *)this + 16) = v8;
  if ( v8 )
  {
    ptc = 0;
    DevCaps = timeGetDevCaps(&ptc, 8u);
    wPeriodMin = 1;
    if ( !DevCaps )
      wPeriodMin = ptc.wPeriodMin;
    *((_DWORD *)this + 28) = wPeriodMin;
    timeBeginPeriod(wPeriodMin);
    Time = timeGetTime();
    *((_DWORD *)this + 22) = Time;
    v7 = ThreadId == 0;
    *((_QWORD *)this + 10) = 10000LL * Time;
    if ( v7 )
    {
      LODWORD(ThreadId) = 0;
      Thread = CreateThread(0, 0, CBaseReferenceClock::AdviseThreadFunction, this, 0, (LPDWORD)&ThreadId);
      *((_QWORD *)this + 15) = Thread;
      if ( Thread )
      {
        SetThreadPriority(Thread, 15);
      }
      else
      {
        *a4 = -2147467259;
        CloseHandle(*(HANDLE *)(*((_QWORD *)this + 16) + 160LL));
        v15 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 16);
        if ( v15 )
          (**v15)(v15, 1);
        *((_QWORD *)this + 16) = 0;
      }
    }
  }
  else
  {
    *a4 = -2147024882;
  }
  return this;
}

```

## disassembly

```asm
0x18005c4b8  mov     [rsp+arg_0], rbx
0x18005c4bd  mov     [rsp+arg_10], rsi
0x18005c4c2  mov     qword ptr [rsp+ptc.wPeriodMin], rdx
0x18005c4c7  push    rdi
0x18005c4c8  sub     rsp, 30h
0x18005c4cc  mov     rsi, r9
0x18005c4cf  mov     rbx, rcx
0x18005c4d2  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18005c4d9  test    r8, r8
0x18005c4dc  cmovz   r8, rcx
0x18005c4e0  mov     [rcx+8], r8
0x18005c4e4  mov     dword ptr [rcx+10h], 0
0x18005c4eb  add     rcx, 28h ; '('; lpCriticalSection
0x18005c4ef  call    cs:__imp_InitializeCriticalSection
0x18005c4f6  nop     dword ptr [rax+rax+00h]
0x18005c4fb  cmp     qword ptr [rsp+38h+ThreadId], 0
0x18005c501  lea     rax, ??_7CBaseReferenceClock@@6BCUnknown@@@; const CBaseReferenceClock::`vftable'{for `CUnknown'}
0x18005c508  mov     [rbx], rax
0x18005c50b  lea     rax, ??_7CWaveOutClock@@6BIReferenceClock@@@; const CWaveOutClock::`vftable'{for `IReferenceClock'}
0x18005c512  mov     [rbx+18h], rax
0x18005c516  lea     rax, ??_7CBaseReferenceClock@@6BIReferenceClockTimerControl@@@; const CBaseReferenceClock::`vftable'{for `IReferenceClockTimerControl'}
0x18005c51d  mov     [rbx+20h], rax
0x18005c521  mov     qword ptr [rbx+60h], 0
0x18005c529  mov     qword ptr [rbx+70h], 0
0x18005c531  mov     qword ptr [rbx+78h], 0
0x18005c539  jz      short loc_18005C542
0x18005c53b  mov     rax, qword ptr [rsp+38h+ThreadId]
0x18005c540  jmp     short loc_18005C575
0x18005c542  mov     ecx, 0B8h; Size
0x18005c547  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005c54c  mov     rdi, rax
0x18005c54f  test    rax, rax
0x18005c552  jz      short loc_18005C575
0x18005c554  xor     r9d, r9d; lpName
0x18005c557  xor     r8d, r8d; bInitialState
0x18005c55a  xor     edx, edx; bManualReset
0x18005c55c  xor     ecx, ecx; lpEventAttributes
0x18005c55e  call    cs:__imp_CreateEventW
0x18005c565  nop     dword ptr [rax+rax+00h]
0x18005c56a  mov     rdx, rax; void *
0x18005c56d  mov     rcx, rdi; this
0x18005c570  call    ??0CAMSchedule@@QEAA@PEAX@Z; CAMSchedule::CAMSchedule(void *)
0x18005c575  mov     [rbx+80h], rax
0x18005c57c  test    rax, rax
0x18005c57f  jnz     short loc_18005C58C
0x18005c581  mov     dword ptr [rsi], 8007000Eh
0x18005c587  jmp     loc_18005C688
0x18005c58c  mov     edx, 8; cbtc
0x18005c591  mov     qword ptr [rsp+38h+ptc.wPeriodMin], 0
0x18005c59a  lea     rcx, [rsp+38h+ptc]; ptc
0x18005c59f  call    cs:__imp_timeGetDevCaps
0x18005c5a6  nop     dword ptr [rax+rax+00h]
0x18005c5ab  test    eax, eax
0x18005c5ad  mov     ecx, 1
0x18005c5b2  cmovz   ecx, [rsp+38h+ptc.wPeriodMin]; uPeriod
0x18005c5b7  mov     [rbx+70h], ecx
0x18005c5ba  call    cs:__imp_timeBeginPeriod
0x18005c5c1  nop     dword ptr [rax+rax+00h]
0x18005c5c6  call    cs:__imp_timeGetTime
0x18005c5cd  nop     dword ptr [rax+rax+00h]
0x18005c5d2  mov     eax, eax
0x18005c5d4  mov     [rbx+58h], eax
0x18005c5d7  imul    rax, 2710h
0x18005c5de  cmp     qword ptr [rsp+38h+ThreadId], 0
0x18005c5e4  mov     [rbx+50h], rax
0x18005c5e8  jnz     loc_18005C688
0x18005c5ee  lea     rax, [rsp+38h+ThreadId]
0x18005c5f3  mov     [rsp+38h+ThreadId], 0
0x18005c5fb  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18005c600  lea     r8, ?AdviseThreadFunction@CBaseReferenceClock@@CAKPEAX@Z; lpStartAddress
0x18005c607  mov     r9, rbx; lpParameter
0x18005c60a  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18005c612  xor     edx, edx; dwStackSize
0x18005c614  xor     ecx, ecx; lpThreadAttributes
0x18005c616  call    cs:__imp_CreateThread
0x18005c61d  nop     dword ptr [rax+rax+00h]
0x18005c622  mov     [rbx+78h], rax
0x18005c626  test    rax, rax
0x18005c629  jz      short loc_18005C641
0x18005c62b  mov     edx, 0Fh; nPriority
0x18005c630  mov     rcx, rax; hThread
0x18005c633  call    cs:__imp_SetThreadPriority
0x18005c63a  nop     dword ptr [rax+rax+00h]
0x18005c63f  jmp     short loc_18005C688
0x18005c641  mov     dword ptr [rsi], 80004005h
0x18005c647  mov     rcx, [rbx+80h]
0x18005c64e  mov     rcx, [rcx+0A0h]; hObject
0x18005c655  call    cs:__imp_CloseHandle
0x18005c65c  nop     dword ptr [rax+rax+00h]
0x18005c661  mov     rcx, [rbx+80h]
0x18005c668  test    rcx, rcx
0x18005c66b  jz      short loc_18005C67D
0x18005c66d  mov     rax, [rcx]
0x18005c670  mov     edx, 1
0x18005c675  mov     rax, [rax]
0x18005c678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c67d  mov     qword ptr [rbx+80h], 0
0x18005c688  mov     rsi, [rsp+38h+arg_10]
0x18005c68d  mov     rax, rbx
0x18005c690  mov     rbx, [rsp+38h+arg_0]
0x18005c695  add     rsp, 30h
0x18005c699  pop     rdi
0x18005c69a  retn
```
