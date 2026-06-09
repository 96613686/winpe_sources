# PerfDiagSecondaryLogons::CSecondaryLogonScenario::OnEvent(_EVENT_RECORD *,void *)

- ea: `0x18003f1b8`
- end: `0x18003f3a3`
- name: `?OnEvent@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@QEAAJPEAU_EVENT_RECORD@@PEAX@Z`
- size: `491`
- prototype: `__int64 __fastcall(PerfDiagSecondaryLogons::CSecondaryLogonScenario *__hidden this, struct _EVENT_RECORD *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800ba4d0`

## callees

- `0x18003df28`
- `0x18003f1b8`
- `0x18003f3ac`
- `0x1800ba54c`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x18003f2b3`
- `KERNEL32!CreateTimerQueueTimer` at `0x18003f2b3`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18003f32d`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18003f32d`

## pseudocode

```c
__int64 __fastcall PerfDiagSecondaryLogons::CSecondaryLogonScenario::OnEvent(
        HANDLE *this,
        struct _EVENT_RECORD *a2,
        void *a3)
{
  const struct _EVENT_DESCRIPTOR *v5; // rdx
  __int64 v6; // rax
  unsigned int v7; // esi
  HANDLE v9; // rdx
  __int64 v10; // rax
  HANDLE v11; // rdx
  __int64 v12; // rax

  PerfDiagSecondaryLogons::CSecondaryLogonScenario::LogEventArrival(
    (PerfDiagSecondaryLogons::CSecondaryLogonScenario *)this,
    a2,
    &PDEvt_SecondaryLogon_ReceivedEvent);
  v6 = *(_QWORD *)&a2->EventHeader.ProviderId.Data1 - MS_Winlogon_Provider;
  if ( !v6 )
    v6 = *(_QWORD *)a2->EventHeader.ProviderId.Data4 - 0x38B5A316CBA3CC91LL;
  v7 = 1;
  if ( v6 )
  {
    v10 = *(_QWORD *)&a2->EventHeader.ProviderId.Data1 - PerfDiagScenariosProvider;
    if ( !v10 )
      v10 = *(_QWORD *)a2->EventHeader.ProviderId.Data4 - 0xA5BE0AE2C621B96LL;
    if ( v10 )
    {
      v12 = *(_QWORD *)&a2->EventHeader.ProviderId.Data1 - SYSMAIN_SERVICE_EVENT_PROVIDER;
      if ( !v12 )
        v12 = *(_QWORD *)a2->EventHeader.ProviderId.Data4 - 0x19B6E2688F49D6AALL;
      if ( !v12 && a2->EventHeader.EventDescriptor.Id == 1015 && a2->EventHeader.EventDescriptor.Version == 2 )
        return 0;
      goto LABEL_34;
    }
    if ( a2->EventHeader.EventDescriptor.Id != 10001 || a2->EventHeader.EventDescriptor.Version )
      goto LABEL_34;
    if ( *((_DWORD *)this + 6) == 2 )
    {
      v11 = this[5];
      if ( v11 )
      {
        DeleteTimerQueueTimer(this[4], v11, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        this[5] = 0;
      }
      PerfDiagSecondaryLogons::CSecondaryLogonScenario::SetState(this, 3);
      return 0;
    }
    goto LABEL_24;
  }
  if ( a2->EventHeader.EventDescriptor.Id != 5003 )
  {
    if ( a2->EventHeader.EventDescriptor.Id != 10 || a2->EventHeader.EventDescriptor.Version )
      goto LABEL_34;
    if ( !*((_DWORD *)this + 6) )
      return v7;
    if ( *((_DWORD *)this + 6) == 1 )
    {
      PerfDiagSecondaryLogons::CSecondaryLogonScenario::SetState(this, 2);
      v9 = this[4];
      if ( v9
        && CreateTimerQueueTimer(
             this + 5,
             v9,
             PerfDiagSecondaryLogons::CSecondaryLogonScenario::s_postBootTimerCallback,
             this,
             1000 * *((_DWORD *)this + 16),
             0,
             8u) )
      {
        return 0;
      }
      v7 = -2147467259;
      goto LABEL_9;
    }
LABEL_24:
    PerfDiagSecondaryLogons::CSecondaryLogonScenario::LogEventArrival(
      (PerfDiagSecondaryLogons::CSecondaryLogonScenario *)this,
      a2,
      &PDEvt_SecondaryLogon_UnexpectedEvent);
LABEL_9:
    PerfDiagSecondaryLogons::CSecondaryLogonScenario::SetState(this, 0);
    return v7;
  }
  if ( !a2->EventHeader.EventDescriptor.Version )
  {
    if ( !*((_DWORD *)this + 6) )
    {
      PerfDiagSecondaryLogons::CSecondaryLogonScenario::SetState(this, 1);
      *((_DWORD *)this + 12) = a2->EventHeader.ProcessId;
      return 0;
    }
    PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_SecondaryLogon_DetectedMultipleLogons, v5);
    goto LABEL_9;
  }
LABEL_34:
  PerfDiagSecondaryLogons::CSecondaryLogonScenario::LogEventArrival(
    (PerfDiagSecondaryLogons::CSecondaryLogonScenario *)this,
    a2,
    &PDEvt_SecondaryLogon_UnexpectedEvent);
  return 2147549183LL;
}

```

## disassembly

```asm
0x18003f1b8  mov     [rsp+arg_0], rbx
0x18003f1bd  mov     [rsp+arg_8], rsi
0x18003f1c2  push    rdi
0x18003f1c3  sub     rsp, 40h
0x18003f1c7  lea     r8, PDEvt_SecondaryLogon_ReceivedEvent; struct _EVENT_DESCRIPTOR *
0x18003f1ce  mov     rdi, rdx
0x18003f1d1  mov     rbx, rcx
0x18003f1d4  call    ?LogEventArrival@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@AEAAXQEAU_EVENT_RECORD@@PEBU_EVENT_DESCRIPTOR@@@Z; PerfDiagSecondaryLogons::CSecondaryLogonScenario::LogEventArrival(_EVENT_RECORD * const,_EVENT_DESCRIPTOR const *)
0x18003f1d9  mov     rax, [rdi+18h]
0x18003f1dd  sub     rax, cs:MS_Winlogon_Provider
0x18003f1e4  jnz     short loc_18003F1F1
0x18003f1e6  mov     rax, [rdi+20h]
0x18003f1ea  sub     rax, cs:qword_1800E0B68
0x18003f1f1  mov     esi, 1
0x18003f1f6  test    rax, rax
0x18003f1f9  jnz     loc_18003F2CB
0x18003f1ff  mov     eax, 138Bh
0x18003f204  cmp     [rdi+28h], ax
0x18003f208  jnz     short loc_18003F24D
0x18003f20a  cmp     byte ptr [rdi+2Ah], 0
0x18003f20e  jnz     loc_18003F37C
0x18003f214  mov     eax, [rbx+18h]
0x18003f217  test    eax, eax
0x18003f219  jnz     short loc_18003F230
0x18003f21b  mov     edx, esi
0x18003f21d  mov     rcx, rbx
0x18003f220  call    ?SetState@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@AEAAXW4CScenarioState@12@@Z; PerfDiagSecondaryLogons::CSecondaryLogonScenario::SetState(PerfDiagSecondaryLogons::CSecondaryLogonScenario::CScenarioState)
0x18003f225  mov     eax, [rdi+0Ch]
0x18003f228  mov     [rbx+30h], eax
0x18003f22b  jmp     loc_18003F378
0x18003f230  lea     rcx, PDEvt_SecondaryLogon_DetectedMultipleLogons; this
0x18003f237  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &)
0x18003f23c  xor     edx, edx
0x18003f23e  mov     rcx, rbx
0x18003f241  call    ?SetState@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@AEAAXW4CScenarioState@12@@Z; PerfDiagSecondaryLogons::CSecondaryLogonScenario::SetState(PerfDiagSecondaryLogons::CSecondaryLogonScenario::CScenarioState)
0x18003f246  mov     eax, esi
0x18003f248  jmp     loc_18003F393
0x18003f24d  cmp     word ptr [rdi+28h], 0Ah
0x18003f252  jnz     loc_18003F37C
0x18003f258  cmp     byte ptr [rdi+2Ah], 0
0x18003f25c  jnz     loc_18003F37C
0x18003f262  mov     eax, [rbx+18h]
0x18003f265  test    eax, eax
0x18003f267  jz      short loc_18003F246
0x18003f269  mov     eax, [rbx+18h]
0x18003f26c  cmp     eax, esi
0x18003f26e  jnz     loc_18003F305
0x18003f274  mov     edx, 2
0x18003f279  mov     rcx, rbx
0x18003f27c  call    ?SetState@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@AEAAXW4CScenarioState@12@@Z; PerfDiagSecondaryLogons::CSecondaryLogonScenario::SetState(PerfDiagSecondaryLogons::CSecondaryLogonScenario::CScenarioState)
0x18003f281  mov     rdx, [rbx+20h]; TimerQueue
0x18003f285  test    rdx, rdx
0x18003f288  jz      short loc_18003F2C1
0x18003f28a  imul    eax, [rbx+40h], 3E8h
0x18003f291  lea     rcx, [rbx+28h]; phNewTimer
0x18003f295  mov     [rsp+48h+Flags], 8; Flags
0x18003f29d  lea     r8, ?s_postBootTimerCallback@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@CAXPEAXE@Z; Callback
0x18003f2a4  mov     [rsp+48h+Period], 0; Period
0x18003f2ac  mov     r9, rbx; Parameter
0x18003f2af  mov     [rsp+48h+DueTime], eax; DueTime
0x18003f2b3  call    cs:__imp_CreateTimerQueueTimer
0x18003f2b9  test    eax, eax
0x18003f2bb  jnz     loc_18003F378
0x18003f2c1  mov     esi, 80004005h
0x18003f2c6  jmp     loc_18003F23C
0x18003f2cb  mov     rax, [rdi+18h]
0x18003f2cf  sub     rax, cs:PerfDiagScenariosProvider
0x18003f2d6  jnz     short loc_18003F2E3
0x18003f2d8  mov     rax, [rdi+20h]
0x18003f2dc  sub     rax, cs:qword_1800E1090
0x18003f2e3  test    rax, rax
0x18003f2e6  jnz     short loc_18003F34A
0x18003f2e8  mov     eax, 2711h
0x18003f2ed  cmp     [rdi+28h], ax
0x18003f2f1  jnz     loc_18003F37C
0x18003f2f7  cmp     byte ptr [rdi+2Ah], 0
0x18003f2fb  jnz     short loc_18003F37C
0x18003f2fd  mov     eax, [rbx+18h]
0x18003f300  cmp     eax, 2
0x18003f303  jz      short loc_18003F31C
0x18003f305  lea     r8, PDEvt_SecondaryLogon_UnexpectedEvent; struct _EVENT_DESCRIPTOR *
0x18003f30c  mov     rdx, rdi; struct _EVENT_RECORD *
0x18003f30f  mov     rcx, rbx; this
0x18003f312  call    ?LogEventArrival@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@AEAAXQEAU_EVENT_RECORD@@PEBU_EVENT_DESCRIPTOR@@@Z; PerfDiagSecondaryLogons::CSecondaryLogonScenario::LogEventArrival(_EVENT_RECORD * const,_EVENT_DESCRIPTOR const *)
0x18003f317  jmp     loc_18003F23C
0x18003f31c  mov     rdx, [rbx+28h]; Timer
0x18003f320  test    rdx, rdx
0x18003f323  jz      short loc_18003F33B
0x18003f325  mov     rcx, [rbx+20h]; TimerQueue
0x18003f329  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18003f32d  call    cs:__imp_DeleteTimerQueueTimer
0x18003f333  mov     qword ptr [rbx+28h], 0
0x18003f33b  mov     edx, 3
0x18003f340  mov     rcx, rbx
0x18003f343  call    ?SetState@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@AEAAXW4CScenarioState@12@@Z; PerfDiagSecondaryLogons::CSecondaryLogonScenario::SetState(PerfDiagSecondaryLogons::CSecondaryLogonScenario::CScenarioState)
0x18003f348  jmp     short loc_18003F378
0x18003f34a  mov     rax, [rdi+18h]
0x18003f34e  sub     rax, cs:SYSMAIN_SERVICE_EVENT_PROVIDER
0x18003f355  jnz     short loc_18003F362
0x18003f357  mov     rax, [rdi+20h]
0x18003f35b  sub     rax, cs:qword_1800E1558
0x18003f362  test    rax, rax
0x18003f365  jnz     short loc_18003F37C
0x18003f367  mov     eax, 3F7h
0x18003f36c  cmp     [rdi+28h], ax
0x18003f370  jnz     short loc_18003F37C
0x18003f372  cmp     byte ptr [rdi+2Ah], 2
0x18003f376  jnz     short loc_18003F37C
0x18003f378  xor     eax, eax
0x18003f37a  jmp     short loc_18003F393
0x18003f37c  lea     r8, PDEvt_SecondaryLogon_UnexpectedEvent; struct _EVENT_DESCRIPTOR *
0x18003f383  mov     rdx, rdi; struct _EVENT_RECORD *
0x18003f386  mov     rcx, rbx; this
0x18003f389  call    ?LogEventArrival@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@AEAAXQEAU_EVENT_RECORD@@PEBU_EVENT_DESCRIPTOR@@@Z; PerfDiagSecondaryLogons::CSecondaryLogonScenario::LogEventArrival(_EVENT_RECORD * const,_EVENT_DESCRIPTOR const *)
0x18003f38e  mov     eax, 8000FFFFh
0x18003f393  mov     rbx, [rsp+48h+arg_0]
0x18003f398  mov     rsi, [rsp+48h+arg_8]
0x18003f39d  add     rsp, 40h
0x18003f3a1  pop     rdi
0x18003f3a2  retn
```
