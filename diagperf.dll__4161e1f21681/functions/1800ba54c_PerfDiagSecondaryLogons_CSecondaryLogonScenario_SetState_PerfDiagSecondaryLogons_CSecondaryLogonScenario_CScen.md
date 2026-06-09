# PerfDiagSecondaryLogons::CSecondaryLogonScenario::SetState(PerfDiagSecondaryLogons::CSecondaryLogonScenario::CScenarioState)

- ea: `0x1800ba54c`
- end: `0x1800ba5e3`
- name: `?SetState@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@AEAAXW4CScenarioState@12@@Z`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18003f1b8`
- `0x1800ba5f0`

## callees

- `0x1800282a4`
- `0x18003ff34`
- `0x1800ba54c`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x1800ba58c`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800ba58c`

## pseudocode

```c
void __fastcall PerfDiagSecondaryLogons::CSecondaryLogonScenario::SetState(
        __int64 a1,
        int a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  int v6; // esi
  void *v7; // rdx

  if ( *(_DWORD *)(a1 + 24) != a2 )
  {
    v6 = *(_DWORD *)(a1 + 24);
    if ( !a2 )
    {
      if ( *(int *)(a1 + 24) < 3 )
        PerfDiagSecondaryLogons::CSecondaryLogonScenario::EndScenario((PerfDiagSecondaryLogons::CSecondaryLogonScenario *)a1);
      v7 = *(void **)(a1 + 40);
      if ( v7 )
      {
        DeleteTimerQueueTimer(*(HANDLE *)(a1 + 32), v7, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        *(_QWORD *)(a1 + 40) = 0;
      }
    }
    *(_DWORD *)(a1 + 24) = a2;
    PerfDiagOutput::StatusLog::Write(
      (PerfDiagOutput::StatusLog *)PDEvt_SecondaryLogon_ChangedState,
      (const struct _EVENT_DESCRIPTOR *)*(unsigned int *)(a1 + 24),
      0,
      a4);
    if ( a2 )
    {
      if ( !v6 )
        _InterlockedIncrement((volatile signed __int32 *)&PerfDiagDm::CDmManager::g_spInstance[4]);
    }
    else if ( v6 )
    {
      _InterlockedDecrement((volatile signed __int32 *)&PerfDiagDm::CDmManager::g_spInstance[4]);
    }
  }
}

```

## disassembly

```asm
0x1800ba54c  mov     [rsp+arg_0], rbx
0x1800ba551  mov     [rsp+arg_8], rsi
0x1800ba556  push    rdi
0x1800ba557  sub     rsp, 20h
0x1800ba55b  mov     eax, [rcx+18h]
0x1800ba55e  mov     edi, edx
0x1800ba560  mov     rbx, rcx
0x1800ba563  cmp     eax, edx
0x1800ba565  jz      short loc_1800BA5D3
0x1800ba567  mov     esi, [rcx+18h]
0x1800ba56a  test    edx, edx
0x1800ba56c  jnz     short loc_1800BA59A
0x1800ba56e  mov     eax, [rcx+18h]
0x1800ba571  cmp     eax, 3
0x1800ba574  jge     short loc_1800BA57B
0x1800ba576  call    ?EndScenario@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@AEAAXXZ; PerfDiagSecondaryLogons::CSecondaryLogonScenario::EndScenario(void)
0x1800ba57b  mov     rdx, [rbx+28h]; Timer
0x1800ba57f  test    rdx, rdx
0x1800ba582  jz      short loc_1800BA59A
0x1800ba584  mov     rcx, [rbx+20h]; TimerQueue
0x1800ba588  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800ba58c  call    cs:__imp_DeleteTimerQueueTimer
0x1800ba592  mov     qword ptr [rbx+28h], 0
0x1800ba59a  mov     [rbx+18h], edi
0x1800ba59d  lea     rcx, PDEvt_SecondaryLogon_ChangedState; this
0x1800ba5a4  mov     edx, [rbx+18h]; struct _EVENT_DESCRIPTOR *
0x1800ba5a7  xor     r8d, r8d; unsigned int
0x1800ba5aa  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x1800ba5af  test    edi, edi
0x1800ba5b1  jnz     short loc_1800BA5C4
0x1800ba5b3  test    esi, esi
0x1800ba5b5  jz      short loc_1800BA5D3
0x1800ba5b7  mov     rax, cs:?g_spInstance@CDmManager@PerfDiagDm@@2V?$CAtlGlobalPtr@VCDmManager@PerfDiagDm@@@XPerfCore@@A; XPerfCore::CAtlGlobalPtr<PerfDiagDm::CDmManager> PerfDiagDm::CDmManager::g_spInstance
0x1800ba5be  lock dec dword ptr [rax+40h]
0x1800ba5c2  jmp     short loc_1800BA5D3
0x1800ba5c4  test    esi, esi
0x1800ba5c6  jnz     short loc_1800BA5D3
0x1800ba5c8  mov     rax, cs:?g_spInstance@CDmManager@PerfDiagDm@@2V?$CAtlGlobalPtr@VCDmManager@PerfDiagDm@@@XPerfCore@@A; XPerfCore::CAtlGlobalPtr<PerfDiagDm::CDmManager> PerfDiagDm::CDmManager::g_spInstance
0x1800ba5cf  lock inc dword ptr [rax+40h]
0x1800ba5d3  mov     rbx, [rsp+28h+arg_0]
0x1800ba5d8  mov     rsi, [rsp+28h+arg_8]
0x1800ba5dd  add     rsp, 20h
0x1800ba5e1  pop     rdi
0x1800ba5e2  retn
```
