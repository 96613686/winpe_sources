# BootScenario::~BootScenario(void)

- ea: `0x18003b898`
- end: `0x18003b8f3`
- name: `??1BootScenario@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(BootScenario *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003b858`

## callees

- `0x18001769c`
- `0x18003b898`
- `0x18003b93c`

## import_xrefs

- `KERNEL32!DeleteTimerQueueEx` at `0x18003b8ae`
- `KERNEL32!DeleteTimerQueueEx` at `0x18003b8ae`

## pseudocode

```c
void __fastcall BootScenario::~BootScenario(BootScenario *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
  {
    DeleteTimerQueueEx(v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
  }
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 8) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 7) - 24LL));
  PerfDiagDm::CDiagnosticModuleRootBase::~CDiagnosticModuleRootBase(this);
}

```

## disassembly

```asm
0x18003b898  push    rbx
0x18003b89a  sub     rsp, 20h
0x18003b89e  mov     rbx, rcx
0x18003b8a1  mov     rcx, [rcx+20h]; TimerQueue
0x18003b8a5  test    rcx, rcx
0x18003b8a8  jz      short loc_18003B8CC
0x18003b8aa  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18003b8ae  call    cs:__imp_DeleteTimerQueueEx
0x18003b8b4  mov     qword ptr [rbx+20h], 0
0x18003b8bc  mov     qword ptr [rbx+28h], 0
0x18003b8c4  mov     qword ptr [rbx+30h], 0
0x18003b8cc  mov     rcx, [rbx+40h]
0x18003b8d0  sub     rcx, 18h; this
0x18003b8d4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003b8d9  mov     rcx, [rbx+38h]
0x18003b8dd  sub     rcx, 18h; this
0x18003b8e1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003b8e6  mov     rcx, rbx; this
0x18003b8e9  add     rsp, 20h
0x18003b8ed  pop     rbx
0x18003b8ee  jmp     ??1CDiagnosticModuleRootBase@PerfDiagDm@@IEAA@XZ; PerfDiagDm::CDiagnosticModuleRootBase::~CDiagnosticModuleRootBase(void)
```
