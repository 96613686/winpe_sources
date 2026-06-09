# CPullPin::~CPullPin(void)

- ea: `0x18001f2dc`
- end: `0x18001f471`
- name: `??1CPullPin@@UEAA@XZ`
- size: `405`
- prototype: `void __fastcall(CPullPin *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800f00e4`
- `0x1800f0260`
- `0x18014c850`

## callees

- `0x18001f2dc`
- `0x18002e984`
- `0x180037bb0`
- `0x18015e010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18001f3fc`
- `KERNEL32!WaitForSingleObject` at `0x18001f3fc`
- `KERNEL32!DeleteCriticalSection` at `0x18001f41b`
- `KERNEL32!DeleteCriticalSection` at `0x18001f42a`
- `KERNEL32!DeleteCriticalSection` at `0x18001f41b`
- `KERNEL32!DeleteCriticalSection` at `0x18001f42a`
- `KERNEL32!LeaveCriticalSection` at `0x18001f324`
- `KERNEL32!LeaveCriticalSection` at `0x18001f392`
- `KERNEL32!LeaveCriticalSection` at `0x18001f3df`
- `KERNEL32!LeaveCriticalSection` at `0x18001f324`
- `KERNEL32!LeaveCriticalSection` at `0x18001f392`
- `KERNEL32!LeaveCriticalSection` at `0x18001f3df`
- `KERNEL32!EnterCriticalSection` at `0x18001f2ff`
- `KERNEL32!EnterCriticalSection` at `0x18001f30e`
- `KERNEL32!EnterCriticalSection` at `0x18001f2ff`
- `KERNEL32!EnterCriticalSection` at `0x18001f30e`
- `KERNEL32!CloseHandle` at `0x18001f40b`
- `KERNEL32!CloseHandle` at `0x18001f43f`
- `KERNEL32!CloseHandle` at `0x18001f454`
- `KERNEL32!CloseHandle` at `0x18001f40b`
- `KERNEL32!CloseHandle` at `0x18001f43f`
- `KERNEL32!CloseHandle` at `0x18001f454`

## pseudocode

```c
void __fastcall CPullPin::~CPullPin(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  PRTL_CRITICAL_SECTION_DEBUG v5; // rcx
  void *v6; // rsi
  HANDLE OwningThread; // rcx
  void *v8; // rcx

  v2 = this + 1;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CPullPin::`vftable';
  EnterCriticalSection(this + 1);
  EnterCriticalSection(v2);
  if ( this->SpinCount )
  {
    v3 = this + 3;
    if ( (*(int (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)this[3].DebugInfo + 72LL))(this[3].DebugInfo) >= 0 )
    {
      HIDWORD(this[3].SpinCount) = 2;
      CAMThread::CallWorker((CAMThread *)this, 2u);
      (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)v3->DebugInfo + 80LL))(v3->DebugInfo);
      CAMThread::Close((CAMThread *)this);
      DebugInfo = this[4].DebugInfo;
      if ( DebugInfo )
        (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)&DebugInfo->Type + 48LL))(DebugInfo);
    }
    LeaveCriticalSection(v2);
  }
  else
  {
    LeaveCriticalSection(v2);
    v3 = this + 3;
  }
  if ( v3->DebugInfo )
  {
    (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)v3->DebugInfo + 16LL))(v3->DebugInfo);
    v3->DebugInfo = 0;
  }
  v5 = this[4].DebugInfo;
  if ( v5 )
  {
    (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)&v5->Type + 16LL))(v5);
    this[4].DebugInfo = 0;
  }
  LeaveCriticalSection(v2);
  v6 = (void *)_InterlockedExchange64((volatile __int64 *)&this->SpinCount, 0);
  if ( v6 )
  {
    WaitForSingleObject(v6, 0xFFFFFFFF);
    CloseHandle(v6);
  }
  DeleteCriticalSection(this + 2);
  DeleteCriticalSection(v2);
  OwningThread = this->OwningThread;
  if ( OwningThread )
    CloseHandle(OwningThread);
  v8 = *(void **)&this->LockCount;
  if ( v8 )
    CloseHandle(v8);
}

```

## disassembly

```asm
0x18001f2dc  mov     [rsp+arg_0], rbx
0x18001f2e1  mov     [rsp+arg_8], rsi
0x18001f2e6  push    rdi
0x18001f2e7  sub     rsp, 20h
0x18001f2eb  lea     rax, ??_7CPullPin@@6B@; const CPullPin::`vftable'
0x18001f2f2  mov     rbx, rcx
0x18001f2f5  lea     rdi, [rcx+28h]
0x18001f2f9  mov     [rcx], rax
0x18001f2fc  mov     rcx, rdi; lpCriticalSection
0x18001f2ff  call    cs:__imp_EnterCriticalSection
0x18001f306  nop     dword ptr [rax+rax+00h]
0x18001f30b  mov     rcx, rdi; lpCriticalSection
0x18001f30e  call    cs:__imp_EnterCriticalSection
0x18001f315  nop     dword ptr [rax+rax+00h]
0x18001f31a  cmp     qword ptr [rbx+20h], 0
0x18001f31f  jnz     short loc_18001F336
0x18001f321  mov     rcx, rdi; lpCriticalSection
0x18001f324  call    cs:__imp_LeaveCriticalSection
0x18001f32b  nop     dword ptr [rax+rax+00h]
0x18001f330  lea     rsi, [rbx+78h]
0x18001f334  jmp     short loc_18001F39E
0x18001f336  lea     rsi, [rbx+78h]
0x18001f33a  mov     rcx, [rsi]
0x18001f33d  mov     rax, [rcx]
0x18001f340  mov     rax, [rax+48h]
0x18001f344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f349  test    eax, eax
0x18001f34b  js      short loc_18001F38F
0x18001f34d  mov     edx, 2; unsigned int
0x18001f352  mov     rcx, rbx; this
0x18001f355  mov     [rbx+9Ch], edx
0x18001f35b  call    ?CallWorker@CAMThread@@QEAAKK@Z; CAMThread::CallWorker(ulong)
0x18001f360  mov     rcx, [rsi]
0x18001f363  mov     rax, [rcx]
0x18001f366  mov     rax, [rax+50h]
0x18001f36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f36f  mov     rcx, rbx; this
0x18001f372  call    ?Close@CAMThread@@QEAAXXZ; CAMThread::Close(void)
0x18001f377  mov     rcx, [rbx+0A0h]
0x18001f37e  test    rcx, rcx
0x18001f381  jz      short loc_18001F38F
0x18001f383  mov     rax, [rcx]
0x18001f386  mov     rax, [rax+30h]
0x18001f38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f38f  mov     rcx, rdi; lpCriticalSection
0x18001f392  call    cs:__imp_LeaveCriticalSection
0x18001f399  nop     dword ptr [rax+rax+00h]
0x18001f39e  mov     rcx, [rsi]
0x18001f3a1  test    rcx, rcx
0x18001f3a4  jz      short loc_18001F3B9
0x18001f3a6  mov     rax, [rcx]
0x18001f3a9  mov     rax, [rax+10h]
0x18001f3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3b2  mov     qword ptr [rsi], 0
0x18001f3b9  mov     rcx, [rbx+0A0h]
0x18001f3c0  test    rcx, rcx
0x18001f3c3  jz      short loc_18001F3DC
0x18001f3c5  mov     rax, [rcx]
0x18001f3c8  mov     rax, [rax+10h]
0x18001f3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3d1  mov     qword ptr [rbx+0A0h], 0
0x18001f3dc  mov     rcx, rdi; lpCriticalSection
0x18001f3df  call    cs:__imp_LeaveCriticalSection
0x18001f3e6  nop     dword ptr [rax+rax+00h]
0x18001f3eb  xor     esi, esi
0x18001f3ed  xchg    rsi, [rbx+20h]
0x18001f3f1  test    rsi, rsi
0x18001f3f4  jz      short loc_18001F417
0x18001f3f6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001f3f9  mov     rcx, rsi; hHandle
0x18001f3fc  call    cs:__imp_WaitForSingleObject
0x18001f403  nop     dword ptr [rax+rax+00h]
0x18001f408  mov     rcx, rsi; hObject
0x18001f40b  call    cs:__imp_CloseHandle
0x18001f412  nop     dword ptr [rax+rax+00h]
0x18001f417  lea     rcx, [rbx+50h]; lpCriticalSection
0x18001f41b  call    cs:__imp_DeleteCriticalSection
0x18001f422  nop     dword ptr [rax+rax+00h]
0x18001f427  mov     rcx, rdi; lpCriticalSection
0x18001f42a  call    cs:__imp_DeleteCriticalSection
0x18001f431  nop     dword ptr [rax+rax+00h]
0x18001f436  mov     rcx, [rbx+10h]; hObject
0x18001f43a  test    rcx, rcx
0x18001f43d  jz      short loc_18001F44B
0x18001f43f  call    cs:__imp_CloseHandle
0x18001f446  nop     dword ptr [rax+rax+00h]
0x18001f44b  mov     rcx, [rbx+8]; hObject
0x18001f44f  test    rcx, rcx
0x18001f452  jz      short loc_18001F460
0x18001f454  call    cs:__imp_CloseHandle
0x18001f45b  nop     dword ptr [rax+rax+00h]
0x18001f460  mov     rbx, [rsp+28h+arg_0]
0x18001f465  mov     rsi, [rsp+28h+arg_8]
0x18001f46a  add     rsp, 20h
0x18001f46e  pop     rdi
0x18001f46f  retn
```
