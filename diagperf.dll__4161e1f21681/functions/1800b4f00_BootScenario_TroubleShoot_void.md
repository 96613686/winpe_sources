# BootScenario::TroubleShoot(void *)

- ea: `0x1800b4f00`
- end: `0x1800b4fd3`
- name: `?TroubleShoot@BootScenario@@UEAAJPEAX@Z`
- size: `211`
- prototype: `__int64 __fastcall(BootScenario *__hidden this, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x18001a984`
- `0x1800279d8`
- `0x1800282a4`
- `0x18003df28`
- `0x180043ea8`
- `0x1800b4ec0`
- `0x1800b4f00`

## import_xrefs

- `KERNEL32!DeleteTimerQueueEx` at `0x1800b4f39`
- `KERNEL32!DeleteTimerQueueEx` at `0x1800b4f39`

## pseudocode

```c
__int64 __fastcall BootScenario::TroubleShoot(BootScenario *this, void *a2, __int64 a3, const unsigned __int16 *a4)
{
  __int64 result; // rax
  void *v7; // rcx
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  __int64 v9; // rcx
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  void *v11; // rdx
  unsigned int v12; // eax
  const unsigned __int16 *v13; // r9
  void **v14; // [rsp+20h] [rbp-18h] BYREF
  int v15; // [rsp+28h] [rbp-10h]

  if ( *((_DWORD *)this + 6) != 5 )
    return 2147549183LL;
  BootScenario::setState((__int64)this, 6, a3, a4);
  v7 = (void *)*((_QWORD *)this + 4);
  if ( v7 && DeleteTimerQueueEx(v7, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
  {
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
  }
  v14 = &PerfDiagShared::CTracingEnablementConfig::`vftable';
  if ( (int)Performance::RegistryTransferable<PerfDiagShared::CTracingEnablementConfig>::readWriteImpl(&v14, 0) >= 0
    && v15 == 1 )
  {
    PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Boot_CancelledAnalysisViaRegistry_Info, v8);
    return 1;
  }
  else
  {
    result = BootScenario::SnapshotLogger(v9, (char *)this + 64, a2);
    if ( (int)result >= 0 )
    {
      PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Boot_Troubleshooting_Start, v10);
      v12 = BootScenario::PerformTroubleshooting(this, v11);
      PerfDiagOutput::StatusLog::Write(
        (PerfDiagOutput::StatusLog *)PDEvt_Boot_Troubleshooting_Stop,
        (const struct _EVENT_DESCRIPTOR *)v12,
        0,
        v13);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800b4f00  mov     [rsp+arg_0], rbx
0x1800b4f05  push    rdi
0x1800b4f06  sub     rsp, 30h
0x1800b4f0a  mov     eax, [rcx+18h]
0x1800b4f0d  mov     rdi, rdx
0x1800b4f10  mov     rbx, rcx
0x1800b4f13  cmp     eax, 5
0x1800b4f16  jz      short loc_1800B4F22
0x1800b4f18  mov     eax, 8000FFFFh
0x1800b4f1d  jmp     loc_1800B4FC8
0x1800b4f22  mov     edx, 6
0x1800b4f27  call    ?setState@BootScenario@@AEAAXW4BSState@1@@Z; BootScenario::setState(BootScenario::BSState)
0x1800b4f2c  mov     rcx, [rbx+20h]; TimerQueue
0x1800b4f30  test    rcx, rcx
0x1800b4f33  jz      short loc_1800B4F5B
0x1800b4f35  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800b4f39  call    cs:__imp_DeleteTimerQueueEx
0x1800b4f3f  test    eax, eax
0x1800b4f41  jz      short loc_1800B4F5B
0x1800b4f43  mov     qword ptr [rbx+20h], 0
0x1800b4f4b  mov     qword ptr [rbx+28h], 0
0x1800b4f53  mov     qword ptr [rbx+30h], 0
0x1800b4f5b  lea     rax, ??_7CTracingEnablementConfig@PerfDiagShared@@6B@; const PerfDiagShared::CTracingEnablementConfig::`vftable'
0x1800b4f62  xor     edx, edx
0x1800b4f64  lea     rcx, [rsp+38h+var_18]
0x1800b4f69  mov     [rsp+38h+var_18], rax
0x1800b4f6e  call    ?readWriteImpl@?$RegistryTransferable@VCTracingEnablementConfig@PerfDiagShared@@@Performance@@AEAAJ_N@Z; Performance::RegistryTransferable<PerfDiagShared::CTracingEnablementConfig>::readWriteImpl(bool)
0x1800b4f73  test    eax, eax
0x1800b4f75  js      short loc_1800B4F91
0x1800b4f77  cmp     [rsp+38h+var_10], 1
0x1800b4f7c  jnz     short loc_1800B4F91
0x1800b4f7e  lea     rcx, PDEvt_Boot_CancelledAnalysisViaRegistry_Info; this
0x1800b4f85  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &)
0x1800b4f8a  mov     eax, 1
0x1800b4f8f  jmp     short loc_1800B4FC8
0x1800b4f91  lea     rdx, [rbx+40h]
0x1800b4f95  mov     r8, rdi
0x1800b4f98  call    ?SnapshotLogger@BootScenario@@AEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAX@Z; BootScenario::SnapshotLogger(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,void *)
0x1800b4f9d  test    eax, eax
0x1800b4f9f  js      short loc_1800B4FC8
0x1800b4fa1  lea     rcx, PDEvt_Boot_Troubleshooting_Start; this
0x1800b4fa8  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &)
0x1800b4fad  mov     rcx, rbx; this
0x1800b4fb0  call    ?PerformTroubleshooting@BootScenario@@AEAAJPEAX@Z; BootScenario::PerformTroubleshooting(void *)
0x1800b4fb5  xor     r8d, r8d; unsigned int
0x1800b4fb8  lea     rcx, PDEvt_Boot_Troubleshooting_Stop; this
0x1800b4fbf  mov     edx, eax; struct _EVENT_DESCRIPTOR *
0x1800b4fc1  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x1800b4fc6  xor     eax, eax
0x1800b4fc8  mov     rbx, [rsp+38h+arg_0]
0x1800b4fcd  add     rsp, 30h
0x1800b4fd1  pop     rdi
0x1800b4fd2  retn
```
