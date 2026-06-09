# PerfDiagSecondaryLogons::CSecondaryLogonScenario::~CSecondaryLogonScenario(void)

- ea: `0x1800ba3bc`
- end: `0x1800ba3f5`
- name: `??1CSecondaryLogonScenario@PerfDiagSecondaryLogons@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(PerfDiagSecondaryLogons::CSecondaryLogonScenario *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800ba37c`

## callees

- `0x18003b93c`
- `0x1800ba3bc`

## import_xrefs

- `KERNEL32!DeleteTimerQueueEx` at `0x1800ba3d2`
- `KERNEL32!DeleteTimerQueueEx` at `0x1800ba3d2`

## pseudocode

```c
void __fastcall PerfDiagSecondaryLogons::CSecondaryLogonScenario::~CSecondaryLogonScenario(
        PerfDiagSecondaryLogons::CSecondaryLogonScenario *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
    DeleteTimerQueueEx(v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  PerfDiagDm::CDiagnosticModuleRootBase::~CDiagnosticModuleRootBase(this);
}

```

## disassembly

```asm
0x1800ba3bc  push    rbx
0x1800ba3be  sub     rsp, 20h
0x1800ba3c2  mov     rbx, rcx
0x1800ba3c5  mov     rcx, [rcx+20h]; TimerQueue
0x1800ba3c9  test    rcx, rcx
0x1800ba3cc  jz      short loc_1800BA3D8
0x1800ba3ce  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800ba3d2  call    cs:__imp_DeleteTimerQueueEx
0x1800ba3d8  mov     rcx, rbx; this
0x1800ba3db  mov     qword ptr [rbx+20h], 0
0x1800ba3e3  mov     qword ptr [rbx+28h], 0
0x1800ba3eb  add     rsp, 20h
0x1800ba3ef  pop     rbx
0x1800ba3f0  jmp     ??1CDiagnosticModuleRootBase@PerfDiagDm@@IEAA@XZ; PerfDiagDm::CDiagnosticModuleRootBase::~CDiagnosticModuleRootBase(void)
```
