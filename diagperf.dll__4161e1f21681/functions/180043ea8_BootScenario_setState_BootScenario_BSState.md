# BootScenario::setState(BootScenario::BSState)

- ea: `0x180043ea8`
- end: `0x180043f7e`
- name: `?setState@BootScenario@@AEAAXW4BSState@1@@Z`
- size: `214`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800286b8`
- `0x1800b4f00`
- `0x1800b58a0`

## callees

- `0x1800282a4`
- `0x180028af4`
- `0x180043ea8`
- `0x1800b4e80`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x180043ef9`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180043f18`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180043ef9`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180043f18`

## pseudocode

```c
void __fastcall BootScenario::setState(__int64 a1, int a2, __int64 a3, const unsigned __int16 *a4)
{
  bool v6; // di
  void *v7; // rdx
  void *v8; // rdx

  if ( *(_DWORD *)(a1 + 24) != a2 )
  {
    v6 = *(int *)(a1 + 24) > 0 && *(int *)(a1 + 24) < 6;
    if ( a2 == 7 )
    {
      BootScenario::RestoreCKCL((BootScenario *)a1);
      v7 = *(void **)(a1 + 40);
      if ( v7 )
      {
        DeleteTimerQueueTimer(*(HANDLE *)(a1 + 32), v7, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        *(_QWORD *)(a1 + 40) = 0;
      }
      v8 = *(void **)(a1 + 48);
      if ( v8 )
      {
        DeleteTimerQueueTimer(*(HANDLE *)(a1 + 32), v8, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        *(_QWORD *)(a1 + 48) = 0;
      }
    }
    *(_DWORD *)(a1 + 24) = a2;
    PerfDiagOutput::StatusLog::Write(
      (PerfDiagOutput::StatusLog *)PDEvt_Boot_ChangedState,
      (const struct _EVENT_DESCRIPTOR *)*(unsigned int *)(a1 + 24),
      0,
      a4);
    if ( a2 < 6 )
    {
      if ( !v6 )
        _InterlockedIncrement((volatile signed __int32 *)&PerfDiagDm::CDmManager::g_spInstance[4]);
    }
    else if ( v6 )
    {
      _InterlockedDecrement((volatile signed __int32 *)&PerfDiagDm::CDmManager::g_spInstance[4]);
      PerfDiagDm::CEvent::SetEvent((PerfDiagDm::CEvent *)&g_BootDoneEvent);
    }
  }
}

```

## disassembly

```asm
0x180043ea8  mov     [rsp+arg_0], rbx
0x180043ead  mov     [rsp+arg_8], rsi
0x180043eb2  push    rdi
0x180043eb3  sub     rsp, 20h
0x180043eb7  mov     eax, [rcx+18h]
0x180043eba  mov     esi, edx
0x180043ebc  mov     rbx, rcx
0x180043ebf  cmp     eax, edx
0x180043ec1  jz      loc_180043F6E
0x180043ec7  mov     eax, [rcx+18h]
0x180043eca  test    eax, eax
0x180043ecc  jle     short loc_180043EDB
0x180043ece  mov     eax, [rcx+18h]
0x180043ed1  cmp     eax, 6
0x180043ed4  jge     short loc_180043EDB
0x180043ed6  mov     dil, 1
0x180043ed9  jmp     short loc_180043EDE
0x180043edb  xor     dil, dil
0x180043ede  cmp     esi, 7
0x180043ee1  jnz     short loc_180043F26
0x180043ee3  call    ?RestoreCKCL@BootScenario@@AEAAXXZ; BootScenario::RestoreCKCL(void)
0x180043ee8  mov     rdx, [rbx+28h]; Timer
0x180043eec  test    rdx, rdx
0x180043eef  jz      short loc_180043F07
0x180043ef1  mov     rcx, [rbx+20h]; TimerQueue
0x180043ef5  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180043ef9  call    cs:__imp_DeleteTimerQueueTimer
0x180043eff  mov     qword ptr [rbx+28h], 0
0x180043f07  mov     rdx, [rbx+30h]; Timer
0x180043f0b  test    rdx, rdx
0x180043f0e  jz      short loc_180043F26
0x180043f10  mov     rcx, [rbx+20h]; TimerQueue
0x180043f14  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180043f18  call    cs:__imp_DeleteTimerQueueTimer
0x180043f1e  mov     qword ptr [rbx+30h], 0
0x180043f26  mov     [rbx+18h], esi
0x180043f29  lea     rcx, PDEvt_Boot_ChangedState; this
0x180043f30  mov     edx, [rbx+18h]; struct _EVENT_DESCRIPTOR *
0x180043f33  xor     r8d, r8d; unsigned int
0x180043f36  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x180043f3b  cmp     esi, 6
0x180043f3e  jl      short loc_180043F5E
0x180043f40  test    dil, dil
0x180043f43  jz      short loc_180043F6E
0x180043f45  mov     rax, cs:?g_spInstance@CDmManager@PerfDiagDm@@2V?$CAtlGlobalPtr@VCDmManager@PerfDiagDm@@@XPerfCore@@A; XPerfCore::CAtlGlobalPtr<PerfDiagDm::CDmManager> PerfDiagDm::CDmManager::g_spInstance
0x180043f4c  lea     rcx, ?g_BootDoneEvent@@3VCEvent@PerfDiagDm@@A; this
0x180043f53  lock dec dword ptr [rax+40h]
0x180043f57  call    ?SetEvent@CEvent@PerfDiagDm@@QEAAJXZ; PerfDiagDm::CEvent::SetEvent(void)
0x180043f5c  jmp     short loc_180043F6E
0x180043f5e  test    dil, dil
0x180043f61  jnz     short loc_180043F6E
0x180043f63  mov     rax, cs:?g_spInstance@CDmManager@PerfDiagDm@@2V?$CAtlGlobalPtr@VCDmManager@PerfDiagDm@@@XPerfCore@@A; XPerfCore::CAtlGlobalPtr<PerfDiagDm::CDmManager> PerfDiagDm::CDmManager::g_spInstance
0x180043f6a  lock inc dword ptr [rax+40h]
0x180043f6e  mov     rbx, [rsp+28h+arg_0]
0x180043f73  mov     rsi, [rsp+28h+arg_8]
0x180043f78  add     rsp, 20h
0x180043f7c  pop     rdi
0x180043f7d  retn
```
