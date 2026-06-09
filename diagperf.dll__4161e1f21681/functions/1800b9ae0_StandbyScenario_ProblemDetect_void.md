# StandbyScenario::ProblemDetect(void *)

- ea: `0x1800b9ae0`
- end: `0x1800b9da3`
- name: `?ProblemDetect@StandbyScenario@@UEAAJPEAX@Z`
- size: `707`
- prototype: `__int64 __fastcall(StandbyScenario *__hidden this, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x18001a438`
- `0x1800282a4`
- `0x18002c470`
- `0x18003df28`
- `0x180041b74`
- `0x1800b91a4`
- `0x1800b94a4`
- `0x1800b9ae0`
- `0x1800cf080`

## import_xrefs

- `msvcrt!free` at `0x1800b9d09`
- `msvcrt!free` at `0x1800b9d77`
- `msvcrt!free` at `0x1800b9d09`
- `msvcrt!free` at `0x1800b9d77`
- `ntdll!EtwEventWrite` at `0x1800b9ba2`
- `ntdll!EtwEventWrite` at `0x1800b9ba2`
- `ntdll!EtwEventEnabled` at `0x1800b9b57`
- `ntdll!EtwEventEnabled` at `0x1800b9b57`
- `wdi!WdiSetProblemDetectionResult` at `0x1800b9cf7`
- `wdi!WdiSetProblemDetectionResult` at `0x1800b9cf7`

## pseudocode

```c
__int64 __fastcall StandbyScenario::ProblemDetect(StandbyScenario *this, unsigned __int16 *a2)
{
  __int64 result; // rax
  int Event; // eax
  const unsigned __int16 *v6; // r9
  _BYTE *v7; // rbx
  unsigned int v8; // esi
  unsigned __int64 v9; // rsi
  _WORD *v10; // rdi
  int v11; // ecx
  int v12; // ecx
  __int64 v13; // rax
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  const unsigned __int16 *v15; // r9
  const unsigned __int16 *v16; // r9
  const struct _EVENT_DESCRIPTOR *v17; // r15
  const unsigned __int16 *v18; // r9
  struct PerfDiagSuspend::CAnalysisContext *v19; // rdx
  void *v20; // r8
  const unsigned __int16 *v21; // r9
  signed __int32 v22[8]; // [rsp+0h] [rbp-60h] BYREF
  void *Block; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v24[6]; // [rsp+28h] [rbp-38h] BYREF

  result = PerfDiagDm::IsScenarioEnabled(this, a2);
  if ( (_DWORD)result )
    return result;
  Block = 0;
  Event = PerfDiagDm::GetEvent(&Block, a2);
  v7 = Block;
  v8 = Event;
  if ( Event < 0 )
    goto LABEL_31;
  v9 = PerfDiagOutput::StatusLog::g_RegHandle;
  v10 = (char *)Block + 40;
  if ( PerfDiagOutput::StatusLog::g_RegHandle
    && (unsigned __int8)EtwEventEnabled(PerfDiagOutput::StatusLog::g_RegHandle, PDEvt_Standby_ReceivedEvent) )
  {
    LODWORD(Block) = *((_DWORD *)this + 4);
    v24[1] = 16;
    v24[0] = v7 + 24;
    v24[2] = v7 + 40;
    v24[4] = &Block;
    v24[3] = 2;
    v24[5] = 4;
    EtwEventWrite(v9, PDEvt_Standby_ReceivedEvent, 3, v24);
  }
  v11 = *((_DWORD *)this + 4);
  if ( !v11 )
  {
    v8 = 1;
    if ( *v10 != 1 || v7[42] )
      goto LABEL_31;
    *(_QWORD *)((char *)this + 28) = *((_QWORD *)v7 + 2);
    *((_DWORD *)this + 4) = 1;
    PerfDiagOutput::StatusLog::Write(
      (PerfDiagOutput::StatusLog *)PDEvt_Standby_ChangedState,
      (const struct _EVENT_DESCRIPTOR *)1,
      0,
      v6);
    _InterlockedAdd((volatile signed __int32 *)&PerfDiagDm::CDmManager::g_spInstance[4], 1u);
    goto LABEL_30;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    if ( v12 == 1 )
      v8 = 1;
    else
      v8 = -2147418113;
    goto LABEL_31;
  }
  v8 = 1;
  if ( *v10 != 2 )
  {
    if ( *v10 != 1 || v7[42] )
      goto LABEL_31;
    *(_QWORD *)((char *)this + 28) = *((_QWORD *)v7 + 2);
    goto LABEL_30;
  }
  if ( v7[42] != 1 )
  {
LABEL_31:
    free(v7);
    return v8;
  }
  v13 = *((_QWORD *)v7 + 2);
  *((_DWORD *)this + 4) = 2;
  *(_QWORD *)((char *)this + 20) = v13;
  PerfDiagOutput::StatusLog::Write(
    (PerfDiagOutput::StatusLog *)PDEvt_Standby_ChangedState,
    (const struct _EVENT_DESCRIPTOR *)2,
    0,
    v6);
  if ( *((_WORD *)v7 + 43) < 4u )
  {
    _InterlockedDecrement((volatile signed __int32 *)&PerfDiagDm::CDmManager::g_spInstance[4]);
    *((_DWORD *)this + 4) = 0;
    PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Standby_ChangedState, 0, 0, v15);
    v8 = -2147024883;
    goto LABEL_31;
  }
  if ( **((int **)v7 + 12) < 0 )
  {
    PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Standby_FailedTransition, v14);
    _InterlockedDecrement((volatile signed __int32 *)&PerfDiagDm::CDmManager::g_spInstance[4]);
    *((_DWORD *)this + 4) = 0;
    PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Standby_ChangedState, 0, 0, v16);
LABEL_30:
    v8 = 0;
    goto LABEL_31;
  }
  PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Standby_DetectRegressions_Start, v14);
  v17 = (const struct _EVENT_DESCRIPTOR *)(unsigned int)StandbyScenario::DetectRegressions(this, a2);
  PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Standby_DetectRegressions_Stop, v17, 0, v18);
  if ( (_DWORD)v17 == 1 )
  {
    PerfDiagSuspend::OutputFindings(*((PerfDiagSuspend **)this + 5), v19, v20);
    ATL::CAutoPtr<PerfDiagSuspend::CAnalysisContext>::Free((char *)this + 40);
    _InterlockedOr(v22, 0);
LABEL_20:
    _InterlockedDecrement((volatile signed __int32 *)&PerfDiagDm::CDmManager::g_spInstance[4]);
    *((_DWORD *)this + 4) = 0;
    PerfDiagOutput::StatusLog::Write((PerfDiagOutput::StatusLog *)PDEvt_Standby_ChangedState, 0, 0, v21);
    goto LABEL_21;
  }
  _InterlockedOr(v22, 0);
  if ( (_DWORD)v17 )
    goto LABEL_20;
LABEL_21:
  WdiSetProblemDetectionResult(a2, (_DWORD)v17 == 0);
  if ( (_DWORD)v17 == 1 )
    LODWORD(v17) = 0;
  free(v7);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800b9ae0  mov     [rsp-38h+arg_10], rbx
0x1800b9ae5  push    rbp
0x1800b9ae6  push    rsi
0x1800b9ae7  push    rdi
0x1800b9ae8  push    r12
0x1800b9aea  push    r13
0x1800b9aec  push    r14
0x1800b9aee  push    r15
0x1800b9af0  mov     rbp, rsp
0x1800b9af3  sub     rsp, 60h
0x1800b9af7  mov     rax, cs:__security_cookie
0x1800b9afe  xor     rax, rsp
0x1800b9b01  mov     [rbp+var_8], rax
0x1800b9b05  mov     r13, rdx
0x1800b9b08  mov     r14, rcx
0x1800b9b0b  call    ?IsScenarioEnabled@PerfDiagDm@@YAJPEBG@Z; PerfDiagDm::IsScenarioEnabled(ushort const *)
0x1800b9b10  xor     r15d, r15d
0x1800b9b13  test    eax, eax
0x1800b9b15  jnz     loc_1800B9D7F
0x1800b9b1b  mov     rdx, r13
0x1800b9b1e  mov     [rbp+Block], r15
0x1800b9b22  lea     rcx, [rbp+Block]
0x1800b9b26  call    ?GetEvent@PerfDiagDm@@YAJAEAV?$CHeapPtr@U_EVENT_RECORD@@VCCRTAllocator@ATL@@@ATL@@PEAX@Z; PerfDiagDm::GetEvent(ATL::CHeapPtr<_EVENT_RECORD,ATL::CCRTAllocator> &,void *)
0x1800b9b2b  mov     rbx, [rbp+Block]
0x1800b9b2f  mov     esi, eax
0x1800b9b31  test    eax, eax
0x1800b9b33  js      loc_1800B9D74
0x1800b9b39  mov     rsi, cs:?g_RegHandle@StatusLog@PerfDiagOutput@@3_KA; unsigned __int64 PerfDiagOutput::StatusLog::g_RegHandle
0x1800b9b40  lea     rdi, [rbx+28h]
0x1800b9b44  lea     r12d, [r15+2]
0x1800b9b48  test    rsi, rsi
0x1800b9b4b  jz      short loc_1800B9BA8
0x1800b9b4d  lea     rdx, PDEvt_Standby_ReceivedEvent
0x1800b9b54  mov     rcx, rsi
0x1800b9b57  call    cs:__imp_EtwEventEnabled
0x1800b9b5d  test    al, al
0x1800b9b5f  jz      short loc_1800B9BA8
0x1800b9b61  mov     eax, [r14+10h]
0x1800b9b65  lea     r9, [rbp+var_38]
0x1800b9b69  mov     dword ptr [rbp+Block], eax
0x1800b9b6c  lea     r8d, [r15+3]
0x1800b9b70  lea     rax, [rbx+18h]
0x1800b9b74  mov     [rbp+var_30], 10h
0x1800b9b7c  mov     [rbp+var_38], rax
0x1800b9b80  lea     rdx, PDEvt_Standby_ReceivedEvent
0x1800b9b87  lea     rax, [rbp+Block]
0x1800b9b8b  mov     [rbp+var_28], rdi
0x1800b9b8f  mov     rcx, rsi
0x1800b9b92  mov     [rbp+var_18], rax
0x1800b9b96  mov     [rbp+var_20], r12
0x1800b9b9a  mov     [rbp+var_10], 4
0x1800b9ba2  call    cs:__imp_EtwEventWrite
0x1800b9ba8  mov     ecx, [r14+10h]
0x1800b9bac  test    ecx, ecx
0x1800b9bae  jz      loc_1800B9D31
0x1800b9bb4  sub     ecx, 1
0x1800b9bb7  jz      short loc_1800B9BD2
0x1800b9bb9  cmp     ecx, 1
0x1800b9bbc  jz      short loc_1800B9BC8
0x1800b9bbe  mov     esi, 8000FFFFh
0x1800b9bc3  jmp     loc_1800B9D74
0x1800b9bc8  mov     esi, 1
0x1800b9bcd  jmp     loc_1800B9D74
0x1800b9bd2  mov     esi, 1
0x1800b9bd7  cmp     [rdi], r12w
0x1800b9bdb  jnz     loc_1800B9D14
0x1800b9be1  cmp     [rdi+2], sil
0x1800b9be5  jnz     loc_1800B9D74
0x1800b9beb  mov     rax, [rbx+10h]
0x1800b9bef  mov     edx, r12d; struct _EVENT_DESCRIPTOR *
0x1800b9bf2  mov     [r14+10h], r12d
0x1800b9bf6  xor     r8d, r8d; unsigned int
0x1800b9bf9  mov     [r14+14h], eax
0x1800b9bfd  lea     r12, PDEvt_Standby_ChangedState
0x1800b9c04  shr     rax, 20h
0x1800b9c08  mov     rcx, r12; this
0x1800b9c0b  mov     [r14+18h], eax
0x1800b9c0f  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x1800b9c14  lea     eax, [rsi+3]
0x1800b9c17  cmp     [rbx+56h], ax
0x1800b9c1b  jnb     short loc_1800B9C43
0x1800b9c1d  mov     rax, cs:?g_spInstance@CDmManager@PerfDiagDm@@2V?$CAtlGlobalPtr@VCDmManager@PerfDiagDm@@@XPerfCore@@A; XPerfCore::CAtlGlobalPtr<PerfDiagDm::CDmManager> PerfDiagDm::CDmManager::g_spInstance
0x1800b9c24  xor     r8d, r8d; unsigned int
0x1800b9c27  xor     edx, edx; struct _EVENT_DESCRIPTOR *
0x1800b9c29  mov     rcx, r12; this
0x1800b9c2c  lock dec dword ptr [rax+40h]
0x1800b9c30  mov     [r14+10h], r15d
0x1800b9c34  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x1800b9c39  mov     esi, 8007000Dh
0x1800b9c3e  jmp     loc_1800B9D74
0x1800b9c43  mov     rax, [rbx+60h]
0x1800b9c47  cmp     [rax], r15d
0x1800b9c4a  jge     short loc_1800B9C79
0x1800b9c4c  lea     rcx, PDEvt_Standby_FailedTransition; this
0x1800b9c53  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &)
0x1800b9c58  mov     rax, cs:?g_spInstance@CDmManager@PerfDiagDm@@2V?$CAtlGlobalPtr@VCDmManager@PerfDiagDm@@@XPerfCore@@A; XPerfCore::CAtlGlobalPtr<PerfDiagDm::CDmManager> PerfDiagDm::CDmManager::g_spInstance
0x1800b9c5f  xor     r8d, r8d; unsigned int
0x1800b9c62  xor     edx, edx; struct _EVENT_DESCRIPTOR *
0x1800b9c64  mov     rcx, r12; this
0x1800b9c67  lock dec dword ptr [rax+40h]
0x1800b9c6b  mov     [r14+10h], r15d
0x1800b9c6f  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x1800b9c74  jmp     loc_1800B9D71
0x1800b9c79  lea     rcx, PDEvt_Standby_DetectRegressions_Start; this
0x1800b9c80  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &)
0x1800b9c85  mov     rdx, r13; void *
0x1800b9c88  mov     rcx, r14; this
0x1800b9c8b  call    ?DetectRegressions@StandbyScenario@@QEAAJPEAX@Z; StandbyScenario::DetectRegressions(void *)
0x1800b9c90  xor     r8d, r8d; unsigned int
0x1800b9c93  lea     rcx, PDEvt_Standby_DetectRegressions_Stop; this
0x1800b9c9a  mov     edx, eax; struct _EVENT_DESCRIPTOR *
0x1800b9c9c  mov     r15d, eax
0x1800b9c9f  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x1800b9ca4  cmp     r15d, esi
0x1800b9ca7  jnz     short loc_1800B9CC2
0x1800b9ca9  mov     rcx, [r14+28h]; this
0x1800b9cad  call    ?OutputFindings@PerfDiagSuspend@@YAJAEAUCAnalysisContext@1@PEAX@Z; PerfDiagSuspend::OutputFindings(PerfDiagSuspend::CAnalysisContext &,void *)
0x1800b9cb2  lea     rcx, [r14+28h]
0x1800b9cb6  call    ?Free@?$CAutoPtr@UCAnalysisContext@PerfDiagSuspend@@@ATL@@QEAAXXZ; ATL::CAutoPtr<PerfDiagSuspend::CAnalysisContext>::Free(void)
0x1800b9cbb  lock or [rsp+60h+var_60], 0
0x1800b9cc0  jmp     short loc_1800B9CCC
0x1800b9cc2  lock or [rsp+60h+var_60], 0
0x1800b9cc7  test    r15d, r15d
0x1800b9cca  jz      short loc_1800B9CEC
0x1800b9ccc  mov     rax, cs:?g_spInstance@CDmManager@PerfDiagDm@@2V?$CAtlGlobalPtr@VCDmManager@PerfDiagDm@@@XPerfCore@@A; XPerfCore::CAtlGlobalPtr<PerfDiagDm::CDmManager> PerfDiagDm::CDmManager::g_spInstance
0x1800b9cd3  xor     r8d, r8d; unsigned int
0x1800b9cd6  xor     edx, edx; struct _EVENT_DESCRIPTOR *
0x1800b9cd8  mov     rcx, r12; this
0x1800b9cdb  lock dec dword ptr [rax+40h]
0x1800b9cdf  mov     dword ptr [r14+10h], 0
0x1800b9ce7  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x1800b9cec  xor     edx, edx
0x1800b9cee  mov     rcx, r13
0x1800b9cf1  test    r15d, r15d
0x1800b9cf4  setz    dl
0x1800b9cf7  call    cs:__imp_WdiSetProblemDetectionResult
0x1800b9cfd  xor     ecx, ecx
0x1800b9cff  cmp     r15d, esi
0x1800b9d02  cmovz   r15d, ecx
0x1800b9d06  mov     rcx, rbx; Block
0x1800b9d09  call    cs:__imp_free
0x1800b9d0f  mov     eax, r15d
0x1800b9d12  jmp     short loc_1800B9D7F
0x1800b9d14  cmp     [rdi], si
0x1800b9d17  jnz     short loc_1800B9D74
0x1800b9d19  cmp     [rdi+2], r15b
0x1800b9d1d  jnz     short loc_1800B9D74
0x1800b9d1f  mov     rax, [rbx+10h]
0x1800b9d23  mov     [r14+1Ch], eax
0x1800b9d27  shr     rax, 20h
0x1800b9d2b  mov     [r14+20h], eax
0x1800b9d2f  jmp     short loc_1800B9D71
0x1800b9d31  mov     esi, 1
0x1800b9d36  cmp     [rdi], si
0x1800b9d39  jnz     short loc_1800B9D74
0x1800b9d3b  cmp     [rdi+2], r15b
0x1800b9d3f  jnz     short loc_1800B9D74
0x1800b9d41  mov     rax, [rbx+10h]
0x1800b9d45  lea     rcx, PDEvt_Standby_ChangedState; this
0x1800b9d4c  mov     [r14+1Ch], eax
0x1800b9d50  xor     r8d, r8d; unsigned int
0x1800b9d53  shr     rax, 20h
0x1800b9d57  mov     edx, esi; struct _EVENT_DESCRIPTOR *
0x1800b9d59  mov     [r14+20h], eax
0x1800b9d5d  mov     [r14+10h], esi
0x1800b9d61  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x1800b9d66  mov     rax, cs:?g_spInstance@CDmManager@PerfDiagDm@@2V?$CAtlGlobalPtr@VCDmManager@PerfDiagDm@@@XPerfCore@@A; XPerfCore::CAtlGlobalPtr<PerfDiagDm::CDmManager> PerfDiagDm::CDmManager::g_spInstance
0x1800b9d6d  lock add [rax+40h], esi
0x1800b9d71  mov     esi, r15d
0x1800b9d74  mov     rcx, rbx; Block
0x1800b9d77  call    cs:__imp_free
0x1800b9d7d  mov     eax, esi
0x1800b9d7f  mov     rcx, [rbp+var_8]
0x1800b9d83  xor     rcx, rsp; StackCookie
0x1800b9d86  call    __security_check_cookie
0x1800b9d8b  mov     rbx, [rsp+60h+arg_10]
0x1800b9d93  add     rsp, 60h
0x1800b9d97  pop     r15
0x1800b9d99  pop     r14
0x1800b9d9b  pop     r13
0x1800b9d9d  pop     r12
0x1800b9d9f  pop     rdi
0x1800b9da0  pop     rsi
0x1800b9da1  pop     rbp
0x1800b9da2  retn
```
