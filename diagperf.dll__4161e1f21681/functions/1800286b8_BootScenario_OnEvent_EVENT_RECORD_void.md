# BootScenario::OnEvent(_EVENT_RECORD *,void *)

- ea: `0x1800286b8`
- end: `0x180028aed`
- name: `?OnEvent@BootScenario@@QEAAJPEAU_EVENT_RECORD@@PEAX@Z`
- size: `1077`
- prototype: `__int64 __fastcall(BootScenario *__hidden this, struct _EVENT_RECORD *, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x1800b4e00`

## callees

- `0x1800282a4`
- `0x1800286b8`
- `0x180028af4`
- `0x18003df28`
- `0x180042044`
- `0x180043ea8`
- `0x1800b4e80`
- `0x1800b4ec0`
- `0x1800cf080`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180028750`
- `ntdll!EtwEventWrite` at `0x180028750`
- `ntdll!EtwEventEnabled` at `0x1800286fe`
- `ntdll!EtwEventEnabled` at `0x1800286fe`
- `KERNEL32!CreateTimerQueueTimer` at `0x18002885e`
- `KERNEL32!CreateTimerQueueTimer` at `0x180028915`
- `KERNEL32!CreateTimerQueueTimer` at `0x18002885e`
- `KERNEL32!CreateTimerQueueTimer` at `0x180028915`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800287b2`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800287cc`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800288ae`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800287b2`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800287cc`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800288ae`
- `KERNEL32!DeleteTimerQueueEx` at `0x1800289c7`
- `KERNEL32!DeleteTimerQueueEx` at `0x1800289c7`

## pseudocode

```c
__int64 __fastcall BootScenario::OnEvent(BootScenario *this, struct _EVENT_RECORD *a2, void *a3)
{
  unsigned __int64 v3; // rsi
  __int64 v8; // rax
  void *v9; // rdx
  void *v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rax
  USHORT Id; // cx
  UCHAR *p_Version; // rax
  void *v15; // rdx
  const unsigned __int16 *v16; // r9
  bool v17; // si
  void *v18; // rcx
  unsigned int v19; // edi
  __int64 v20; // rax
  __int64 v21; // rax
  int v22; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v23[6]; // [rsp+48h] [rbp-38h] BYREF

  v3 = PerfDiagOutput::StatusLog::g_RegHandle;
  if ( PerfDiagOutput::StatusLog::g_RegHandle
    && (unsigned __int8)EtwEventEnabled(PerfDiagOutput::StatusLog::g_RegHandle, PDEvt_Boot_ReceivedEvent) )
  {
    v22 = *((_DWORD *)this + 6);
    v23[1] = 16;
    v23[0] = &a2->EventHeader.ProviderId;
    v23[3] = 2;
    v23[2] = &a2->EventHeader.EventDescriptor;
    v23[5] = 4;
    v23[4] = &v22;
    EtwEventWrite(v3, PDEvt_Boot_ReceivedEvent, 3, v23);
  }
  if ( *((int *)this + 6) >= 6 )
    return 1;
  v8 = *(_QWORD *)&a2->EventHeader.ProviderId.Data1 - MS_Kernel_BootDiagnostics_Provider;
  if ( !v8 )
    v8 = *(_QWORD *)a2->EventHeader.ProviderId.Data4 + 0x3ECBA871811F0848LL;
  if ( !v8 )
  {
    if ( a2->EventHeader.EventDescriptor.Id == 501 && !a2->EventHeader.EventDescriptor.Version )
    {
      v9 = (void *)*((_QWORD *)this + 5);
      if ( v9 )
      {
        DeleteTimerQueueTimer(*((HANDLE *)this + 4), v9, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        *((_QWORD *)this + 5) = 0;
      }
      v10 = (void *)*((_QWORD *)this + 6);
      if ( v10 )
      {
        DeleteTimerQueueTimer(*((HANDLE *)this + 4), v10, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        *((_QWORD *)this + 6) = 0;
      }
      v11 = 1;
      goto LABEL_52;
    }
    goto LABEL_69;
  }
  v12 = *(_QWORD *)&a2->EventHeader.ProviderId.Data1 - MS_Winlogon_Provider;
  if ( !v12 )
    v12 = *(_QWORD *)a2->EventHeader.ProviderId.Data4 - 0x38B5A316CBA3CC91LL;
  if ( v12 )
  {
    v20 = *(_QWORD *)&a2->EventHeader.ProviderId.Data1 - PerfDiagScenariosProvider;
    if ( !v20 )
      v20 = *(_QWORD *)a2->EventHeader.ProviderId.Data4 - 0xA5BE0AE2C621B96LL;
    if ( v20 )
    {
      v21 = *(_QWORD *)&a2->EventHeader.ProviderId.Data1 - SYSMAIN_SERVICE_EVENT_PROVIDER;
      if ( !v21 )
        v21 = *(_QWORD *)a2->EventHeader.ProviderId.Data4 - 0x19B6E2688F49D6AALL;
      if ( !v21 && a2->EventHeader.EventDescriptor.Id == 1015 && a2->EventHeader.EventDescriptor.Version == 2 )
        return 0;
    }
    else if ( a2->EventHeader.EventDescriptor.Id == 7001 && !a2->EventHeader.EventDescriptor.Version )
    {
      if ( *((_DWORD *)this + 6) != 2 )
        return 0;
      if ( *(int *)(*((_QWORD *)this + 7) - 16LL) <= 0 )
      {
        BootScenario::SnapshotLogger(this, (char *)this + 56, a3);
        return 0;
      }
LABEL_61:
      v19 = -2147467259;
      goto LABEL_62;
    }
    goto LABEL_69;
  }
  Id = a2->EventHeader.EventDescriptor.Id;
  if ( Id == 5007 )
  {
    if ( a2->EventHeader.EventDescriptor.Version == 2 )
    {
      if ( *((_DWORD *)this + 6) == 1 )
      {
        BootScenario::setState(this, 2);
        CreateTimerQueueTimer(
          (PHANDLE)this + 5,
          *((HANDLE *)this + 4),
          BootScenario::_kernelSnapshotTimerCallback,
          this,
          1000 * *((_DWORD *)this + 22),
          0,
          8u);
        return 0;
      }
      goto LABEL_50;
    }
  }
  else if ( Id == 5001 )
  {
    p_Version = &a2->EventHeader.EventDescriptor.Version;
    if ( !a2->EventHeader.EventDescriptor.Version )
    {
      if ( *((_DWORD *)this + 6) == 2 )
      {
        BootScenario::setState(this, 3);
        v15 = (void *)*((_QWORD *)this + 5);
        *((_DWORD *)this + 18) = a2->EventHeader.ProcessId;
        if ( v15 )
        {
          DeleteTimerQueueTimer(*((HANDLE *)this + 4), v15, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          *((_QWORD *)this + 5) = 0;
        }
        return 0;
      }
      goto LABEL_50;
    }
    goto LABEL_29;
  }
  p_Version = &a2->EventHeader.EventDescriptor.Version;
LABEL_29:
  if ( Id == 5005 )
  {
    p_Version = &a2->EventHeader.EventDescriptor.Version;
    if ( !a2->EventHeader.EventDescriptor.Version )
    {
      if ( *((_DWORD *)this + 6) == 3 )
      {
        BootScenario::setState(this, 4);
        if ( CreateTimerQueueTimer(
               (PHANDLE)this + 6,
               *((HANDLE *)this + 4),
               BootScenario::_postBootTimerCallback,
               this,
               1000 * *((_DWORD *)this + 23),
               0,
               8u) )
        {
          return 0;
        }
        goto LABEL_61;
      }
LABEL_50:
      BootScenario::logUnexpectedEvent(this, a2);
      v19 = -2147418113;
LABEL_62:
      BootScenario::setState(this, 7);
      return v19;
    }
  }
  if ( Id == 5003 )
  {
    if ( !*p_Version )
    {
      if ( *((int *)this + 6) < 5 )
      {
        PerfDiagOutput::StatusLog::Write(
          (PerfDiagOutput::StatusLog *)PDEvt_Boot_DetectedMultipleLogons,
          (const struct _EVENT_DESCRIPTOR *)0x138B);
        BootScenario::RestoreCKCL(this);
        if ( *((_DWORD *)this + 6) != 6 )
        {
          v17 = *((int *)this + 6) > 0 && *((int *)this + 6) < 6;
          *((_DWORD *)this + 6) = 6;
          PerfDiagOutput::StatusLog::Write(
            (PerfDiagOutput::StatusLog *)PDEvt_Boot_ChangedState,
            (const struct _EVENT_DESCRIPTOR *)*((unsigned int *)this + 6),
            0,
            v16);
          if ( v17 )
          {
            _InterlockedAdd((volatile signed __int32 *)&PerfDiagDm::CDmManager::g_spInstance[4], 0xFFFFFFFF);
            PerfDiagDm::CEvent::SetEvent((PerfDiagDm::CEvent *)&g_BootDoneEvent);
          }
        }
        v18 = (void *)*((_QWORD *)this + 4);
        if ( v18 && DeleteTimerQueueEx(v18, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
        {
          *((_QWORD *)this + 4) = 0;
          *((_QWORD *)this + 5) = 0;
          *((_QWORD *)this + 6) = 0;
        }
      }
      return 0;
    }
  }
  else if ( Id == 5002 && !*p_Version )
  {
    if ( *((_DWORD *)this + 6) == 4 )
    {
      v11 = 5;
LABEL_52:
      BootScenario::setState(this, v11);
      return 0;
    }
    goto LABEL_50;
  }
LABEL_69:
  BootScenario::logUnexpectedEvent(this, a2);
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800286b8  mov     [rsp-28h+arg_18], rbx
0x1800286bd  push    rbp
0x1800286be  push    rsi
0x1800286bf  push    rdi
0x1800286c0  push    r14
0x1800286c2  push    r15
0x1800286c4  mov     rbp, rsp
0x1800286c7  sub     rsp, 80h
0x1800286ce  mov     rax, cs:__security_cookie
0x1800286d5  xor     rax, rsp
0x1800286d8  mov     [rbp+var_8], rax
0x1800286dc  mov     rsi, cs:?g_RegHandle@StatusLog@PerfDiagOutput@@3_KA; unsigned __int64 PerfDiagOutput::StatusLog::g_RegHandle
0x1800286e3  xor     r15d, r15d
0x1800286e6  mov     r14, r8
0x1800286e9  mov     rdi, rdx
0x1800286ec  mov     rbx, rcx
0x1800286ef  test    rsi, rsi
0x1800286f2  jz      short loc_180028756
0x1800286f4  lea     rdx, PDEvt_Boot_ReceivedEvent
0x1800286fb  mov     rcx, rsi
0x1800286fe  call    cs:__imp_EtwEventEnabled
0x180028704  test    al, al
0x180028706  jz      short loc_180028756
0x180028708  mov     eax, [rbx+18h]
0x18002870b  lea     r9, [rbp+var_38]
0x18002870f  mov     [rbp+var_40], eax
0x180028712  lea     r8d, [r15+3]
0x180028716  lea     rax, [rdi+18h]
0x18002871a  mov     [rbp+var_30], 10h
0x180028722  mov     [rbp+var_38], rax
0x180028726  lea     rdx, PDEvt_Boot_ReceivedEvent
0x18002872d  lea     rax, [rdi+28h]
0x180028731  mov     [rbp+var_20], 2
0x180028739  mov     [rbp+var_28], rax
0x18002873d  mov     rcx, rsi
0x180028740  lea     rax, [rbp+var_40]
0x180028744  mov     [rbp+var_10], 4
0x18002874c  mov     [rbp+var_18], rax
0x180028750  call    cs:__imp_EtwEventWrite
0x180028756  mov     eax, [rbx+18h]
0x180028759  cmp     eax, 6
0x18002875c  jl      short loc_180028768
0x18002875e  mov     eax, 1
0x180028763  jmp     loc_180028ACA
0x180028768  mov     rax, [rdi+18h]
0x18002876c  sub     rax, cs:MS_Kernel_BootDiagnostics_Provider
0x180028773  jnz     short loc_180028780
0x180028775  mov     rax, [rdi+20h]
0x180028779  sub     rax, cs:qword_1800E0FE8
0x180028780  test    rax, rax
0x180028783  jnz     short loc_1800287E0
0x180028785  mov     eax, 1F5h
0x18002878a  cmp     [rdi+28h], ax
0x18002878e  jnz     loc_180028ABA
0x180028794  cmp     [rdi+2Ah], r15b
0x180028798  jnz     loc_180028ABA
0x18002879e  mov     rdx, [rbx+28h]; Timer
0x1800287a2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800287a6  test    rdx, rdx
0x1800287a9  jz      short loc_1800287BC
0x1800287ab  mov     rcx, [rbx+20h]; TimerQueue
0x1800287af  mov     r8, rdi; CompletionEvent
0x1800287b2  call    cs:__imp_DeleteTimerQueueTimer
0x1800287b8  mov     [rbx+28h], r15
0x1800287bc  mov     rdx, [rbx+30h]; Timer
0x1800287c0  test    rdx, rdx
0x1800287c3  jz      short loc_1800287D6
0x1800287c5  mov     rcx, [rbx+20h]; TimerQueue
0x1800287c9  mov     r8, rdi; CompletionEvent
0x1800287cc  call    cs:__imp_DeleteTimerQueueTimer
0x1800287d2  mov     [rbx+30h], r15
0x1800287d6  mov     edx, 1
0x1800287db  jmp     loc_180028A1B
0x1800287e0  mov     rax, [rdi+18h]
0x1800287e4  sub     rax, cs:MS_Winlogon_Provider
0x1800287eb  jnz     short loc_1800287F8
0x1800287ed  mov     rax, [rdi+20h]
0x1800287f1  sub     rax, cs:qword_1800E0B68
0x1800287f8  test    rax, rax
0x1800287fb  jnz     loc_180028A25
0x180028801  movzx   ecx, word ptr [rdi+28h]
0x180028805  mov     eax, 138Fh
0x18002880a  cmp     cx, ax
0x18002880d  jnz     short loc_180028869
0x18002880f  cmp     byte ptr [rdi+2Ah], 2
0x180028813  jnz     loc_1800288BD
0x180028819  mov     eax, [rbx+18h]
0x18002881c  mov     esi, 1
0x180028821  cmp     eax, esi
0x180028823  jnz     loc_180028A04
0x180028829  lea     edx, [rsi+1]
0x18002882c  mov     rcx, rbx
0x18002882f  call    ?setState@BootScenario@@AEAAXW4BSState@1@@Z; BootScenario::setState(BootScenario::BSState)
0x180028834  imul    eax, [rbx+58h], 3E8h
0x18002883b  lea     rcx, [rbx+28h]; phNewTimer
0x18002883f  mov     rdx, [rbx+20h]; TimerQueue
0x180028843  lea     r8, ?_kernelSnapshotTimerCallback@BootScenario@@CAXPEAXE@Z; Callback
0x18002884a  mov     [rsp+80h+Flags], 8; Flags
0x180028852  mov     r9, rbx; Parameter
0x180028855  mov     [rsp+80h+Period], r15d; Period
0x18002885a  mov     [rsp+80h+DueTime], eax; DueTime
0x18002885e  call    cs:__imp_CreateTimerQueueTimer
0x180028864  jmp     loc_180028A5B
0x180028869  mov     eax, 1389h
0x18002886e  cmp     cx, ax
0x180028871  jnz     short loc_1800288BD
0x180028873  lea     rax, [rdi+2Ah]
0x180028877  cmp     [rax], r15b
0x18002887a  jnz     short loc_1800288C1
0x18002887c  mov     eax, [rbx+18h]
0x18002887f  cmp     eax, 2
0x180028882  jnz     loc_180028A04
0x180028888  lea     edx, [rax+1]
0x18002888b  mov     rcx, rbx
0x18002888e  call    ?setState@BootScenario@@AEAAXW4BSState@1@@Z; BootScenario::setState(BootScenario::BSState)
0x180028893  mov     rdx, [rbx+28h]; Timer
0x180028897  mov     eax, [rdi+0Ch]
0x18002889a  mov     [rbx+48h], eax
0x18002889d  test    rdx, rdx
0x1800288a0  jz      loc_180028A5B
0x1800288a6  mov     rcx, [rbx+20h]; TimerQueue
0x1800288aa  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800288ae  call    cs:__imp_DeleteTimerQueueTimer
0x1800288b4  mov     [rbx+28h], r15
0x1800288b8  jmp     loc_180028A5B
0x1800288bd  lea     rax, [rdi+2Ah]
0x1800288c1  mov     edx, 138Dh
0x1800288c6  cmp     cx, dx
0x1800288c9  jnz     short loc_180028928
0x1800288cb  lea     rax, [rdi+2Ah]
0x1800288cf  cmp     [rax], r15b
0x1800288d2  jnz     short loc_180028928
0x1800288d4  mov     eax, [rbx+18h]
0x1800288d7  cmp     eax, 3
0x1800288da  jnz     loc_180028A04
0x1800288e0  lea     edx, [rax+1]
0x1800288e3  mov     rcx, rbx
0x1800288e6  call    ?setState@BootScenario@@AEAAXW4BSState@1@@Z; BootScenario::setState(BootScenario::BSState)
0x1800288eb  imul    eax, [rbx+5Ch], 3E8h
0x1800288f2  lea     rcx, [rbx+30h]; phNewTimer
0x1800288f6  mov     rdx, [rbx+20h]; TimerQueue
0x1800288fa  lea     r8, ?_postBootTimerCallback@BootScenario@@CAXPEAXE@Z; Callback
0x180028901  mov     [rsp+80h+Flags], 8; Flags
0x180028909  mov     r9, rbx; Parameter
0x18002890c  mov     [rsp+80h+Period], r15d; Period
0x180028911  mov     [rsp+80h+DueTime], eax; DueTime
0x180028915  call    cs:__imp_CreateTimerQueueTimer
0x18002891b  test    eax, eax
0x18002891d  jnz     loc_180028A5B
0x180028923  jmp     loc_180028A6C
0x180028928  mov     edx, 138Bh; struct _EVENT_DESCRIPTOR *
0x18002892d  cmp     cx, dx
0x180028930  jnz     loc_1800289E3
0x180028936  cmp     [rax], r15b
0x180028939  jnz     loc_180028ABA
0x18002893f  mov     eax, [rbx+18h]
0x180028942  cmp     eax, 5
0x180028945  jge     loc_180028A5B
0x18002894b  lea     rcx, PDEvt_Boot_DetectedMultipleLogons; this
0x180028952  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &)
0x180028957  mov     rcx, rbx; this
0x18002895a  call    ?RestoreCKCL@BootScenario@@AEAAXXZ; BootScenario::RestoreCKCL(void)
0x18002895f  mov     eax, [rbx+18h]
0x180028962  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180028966  cmp     eax, 6
0x180028969  jz      short loc_1800289B7
0x18002896b  mov     eax, [rbx+18h]
0x18002896e  test    eax, eax
0x180028970  jle     short loc_18002897F
0x180028972  mov     eax, [rbx+18h]
0x180028975  cmp     eax, 6
0x180028978  jge     short loc_18002897F
0x18002897a  lea     esi, [rdi+2]
0x18002897d  jmp     short loc_180028982
0x18002897f  mov     sil, r15b
0x180028982  mov     dword ptr [rbx+18h], 6
0x180028989  lea     rcx, PDEvt_Boot_ChangedState; this
0x180028990  mov     edx, [rbx+18h]; struct _EVENT_DESCRIPTOR *
0x180028993  xor     r8d, r8d; unsigned int
0x180028996  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x18002899b  test    sil, sil
0x18002899e  jz      short loc_1800289B7
0x1800289a0  mov     rax, cs:?g_spInstance@CDmManager@PerfDiagDm@@2V?$CAtlGlobalPtr@VCDmManager@PerfDiagDm@@@XPerfCore@@A; XPerfCore::CAtlGlobalPtr<PerfDiagDm::CDmManager> PerfDiagDm::CDmManager::g_spInstance
0x1800289a7  lock add [rax+40h], edi
0x1800289ab  lea     rcx, ?g_BootDoneEvent@@3VCEvent@PerfDiagDm@@A; this
0x1800289b2  call    ?SetEvent@CEvent@PerfDiagDm@@QEAAJXZ; PerfDiagDm::CEvent::SetEvent(void)
0x1800289b7  mov     rcx, [rbx+20h]; TimerQueue
0x1800289bb  test    rcx, rcx
0x1800289be  jz      loc_180028A5B
0x1800289c4  mov     rdx, rdi; CompletionEvent
0x1800289c7  call    cs:__imp_DeleteTimerQueueEx
0x1800289cd  test    eax, eax
0x1800289cf  jz      loc_180028A5B
0x1800289d5  mov     [rbx+20h], r15
0x1800289d9  mov     [rbx+28h], r15
0x1800289dd  mov     [rbx+30h], r15
0x1800289e1  jmp     short loc_180028A5B
0x1800289e3  mov     r8d, 138Ah
0x1800289e9  cmp     cx, r8w
0x1800289ed  jnz     loc_180028ABA
0x1800289f3  cmp     [rax], r15b
0x1800289f6  jnz     loc_180028ABA
0x1800289fc  mov     eax, [rbx+18h]
0x1800289ff  cmp     eax, 4
0x180028a02  jz      short loc_180028A16
0x180028a04  mov     rdx, rdi; struct _EVENT_RECORD *
0x180028a07  mov     rcx, rbx; this
0x180028a0a  call    ?logUnexpectedEvent@BootScenario@@AEAAXQEAU_EVENT_RECORD@@@Z; BootScenario::logUnexpectedEvent(_EVENT_RECORD * const)
0x180028a0f  mov     edi, 8000FFFFh
0x180028a14  jmp     short loc_180028A71
0x180028a16  mov     edx, 5
0x180028a1b  mov     rcx, rbx
0x180028a1e  call    ?setState@BootScenario@@AEAAXW4BSState@1@@Z; BootScenario::setState(BootScenario::BSState)
0x180028a23  jmp     short loc_180028A5B
0x180028a25  mov     rax, [rdi+18h]
0x180028a29  sub     rax, cs:PerfDiagScenariosProvider
0x180028a30  jnz     short loc_180028A3D
0x180028a32  mov     rax, [rdi+20h]
0x180028a36  sub     rax, cs:qword_1800E1090
0x180028a3d  test    rax, rax
0x180028a40  jnz     short loc_180028A8C
0x180028a42  mov     eax, 1B59h
0x180028a47  cmp     [rdi+28h], ax
0x180028a4b  jnz     short loc_180028ABA
0x180028a4d  cmp     [rdi+2Ah], r15b
0x180028a51  jnz     short loc_180028ABA
0x180028a53  mov     eax, [rbx+18h]
0x180028a56  cmp     eax, 2
0x180028a59  jz      short loc_180028A5F
0x180028a5b  xor     eax, eax
0x180028a5d  jmp     short loc_180028ACA
0x180028a5f  lea     rdx, [rbx+38h]
0x180028a63  mov     rax, [rdx]
0x180028a66  cmp     [rax-10h], r15d
0x180028a6a  jle     short loc_180028A82
0x180028a6c  mov     edi, 80004005h
0x180028a71  mov     edx, 7
0x180028a76  mov     rcx, rbx
0x180028a79  call    ?setState@BootScenario@@AEAAXW4BSState@1@@Z; BootScenario::setState(BootScenario::BSState)
0x180028a7e  mov     eax, edi
0x180028a80  jmp     short loc_180028ACA
0x180028a82  mov     r8, r14
0x180028a85  call    ?SnapshotLogger@BootScenario@@AEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAX@Z; BootScenario::SnapshotLogger(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,void *)
0x180028a8a  jmp     short loc_180028A5B
0x180028a8c  mov     rax, [rdi+18h]
0x180028a90  sub     rax, cs:SYSMAIN_SERVICE_EVENT_PROVIDER
0x180028a97  jnz     short loc_180028AA4
0x180028a99  mov     rax, [rdi+20h]
0x180028a9d  sub     rax, cs:qword_1800E1558
0x180028aa4  test    rax, rax
0x180028aa7  jnz     short loc_180028ABA
0x180028aa9  mov     eax, 3F7h
0x180028aae  cmp     [rdi+28h], ax
0x180028ab2  jnz     short loc_180028ABA
0x180028ab4  cmp     byte ptr [rdi+2Ah], 2
0x180028ab8  jz      short loc_180028A5B
0x180028aba  mov     rdx, rdi; struct _EVENT_RECORD *
0x180028abd  mov     rcx, rbx; this
0x180028ac0  call    ?logUnexpectedEvent@BootScenario@@AEAAXQEAU_EVENT_RECORD@@@Z; BootScenario::logUnexpectedEvent(_EVENT_RECORD * const)
0x180028ac5  mov     eax, 8000FFFFh
0x180028aca  mov     rcx, [rbp+var_8]
0x180028ace  xor     rcx, rsp; StackCookie
0x180028ad1  call    __security_check_cookie
0x180028ad6  mov     rbx, [rsp+80h+arg_18]
0x180028ade  add     rsp, 80h
0x180028ae5  pop     r15
0x180028ae7  pop     r14
0x180028ae9  pop     rdi
0x180028aea  pop     rsi
0x180028aeb  pop     rbp
0x180028aec  retn
```
