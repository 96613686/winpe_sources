# DxgkPowerRuntimeComponentIdleStateCallback(void *,ulong,ulong)

- ea: `0x1400125c0`
- end: `0x140012af6`
- name: `?DxgkPowerRuntimeComponentIdleStateCallback@@YAXPEAXKK@Z`
- size: `1334`
- prototype: `void __fastcall(struct DXGADAPTER *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x140012540`
- `0x1400125c0`
- `0x140012afc`
- `0x140012cd4`
- `0x140013a20`
- `0x140013e40`
- `0x14001b9c0`
- `0x14001bffc`
- `0x14001d214`
- `0x14001d884`
- `0x140060920`
- `0x140079e08`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x140317c80`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x14001273f`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001273f`
- `ntoskrnl!PoFxCompleteIdleState` at `0x1400127d4`
- `ntoskrnl!PoFxCompleteIdleState` at `0x140012858`
- `ntoskrnl!PoFxCompleteIdleState` at `0x1400127d4`
- `ntoskrnl!PoFxCompleteIdleState` at `0x140012858`
- `ntoskrnl!KeSetEvent` at `0x1400129e4`
- `ntoskrnl!KeSetEvent` at `0x1400129e4`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x1400129cc`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x1400129cc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400129a2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400129a2`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400126e9`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001274b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001296b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012a2f`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400126e9`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001274b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001296b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012a2f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001295a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001295a`
- `HAL!KeStallExecutionProcessor` at `0x140012980`
- `HAL!KeStallExecutionProcessor` at `0x140012980`
- `watchdog!WdLogSingleEntry5` at `0x1400128c6`
- `watchdog!WdLogSingleEntry5` at `0x140012a5a`
- `watchdog!WdLogSingleEntry5` at `0x1400128c6`
- `watchdog!WdLogSingleEntry5` at `0x140012a5a`
- `watchdog!WdLogSingleEntry1` at `0x140012a80`
- `watchdog!WdLogSingleEntry1` at `0x140012a80`

## pseudocode

```c
void __fastcall DxgkPowerRuntimeComponentIdleStateCallback(struct DXGADAPTER *a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // r13
  unsigned int v4; // ebx
  struct DXGADAPTER *v5; // rdi
  char v6; // si
  __int64 v7; // r15
  __int64 v8; // r14
  _BYTE *v9; // r12
  int v10; // ecx
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int v13; // ebx
  DXGGLOBAL *Global; // rax
  __int64 v15; // rcx
  PSLIST_ENTRY v16; // rax
  struct DXGTHREAD *Current; // rax
  KIRQL v18; // al
  char v19; // [rsp+50h] [rbp-49h]
  KIRQL CurrentIrql; // [rsp+50h] [rbp-49h]
  unsigned int v21; // [rsp+54h] [rbp-45h]
  int v22; // [rsp+54h] [rbp-45h]
  int v23; // [rsp+58h] [rbp-41h]
  unsigned int v24; // [rsp+5Ch] [rbp-3Dh]
  struct DXGTHREAD *v25; // [rsp+60h] [rbp-39h]
  unsigned int v26; // [rsp+68h] [rbp-31h] BYREF
  __int64 v27; // [rsp+70h] [rbp-29h]
  char v28; // [rsp+78h] [rbp-21h]
  _BYTE v29[8]; // [rsp+80h] [rbp-19h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+88h] [rbp-11h] BYREF

  v3 = a2;
  v4 = a3;
  v5 = a1;
  v6 = 1;
  v24 = a3;
  if ( *((_QWORD *)a1 + 520) && (a2 == 1 || a2 == 4) && _InterlockedIncrement((volatile signed __int32 *)a1 + 1030) > 1 )
  {
    while ( 1 )
    {
      v16 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v5 + 259);
      if ( v16 )
        break;
      if ( KeGetCurrentIrql() < 2u )
        KeWaitForSingleObject((char *)v5 + 4088, Executive, 0, 0, 0);
      else
        KeStallExecutionProcessor(0x64u);
    }
    LODWORD(v16[1].Next) = v3;
    HIDWORD(v16[1].Next) = v4;
    *((_BYTE *)&v16[1].Next + 8) = 0;
    ExInterlockedInsertTailList((PLIST_ENTRY)v5 + 258, (PLIST_ENTRY)v16, (PKSPIN_LOCK)v5 + 514);
    KeSetEvent((PRKEVENT)((char *)v5 + 4040), 0, 0);
  }
  else if ( *((_DWORD *)a1 + 50) == 1 )
  {
    if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
      McTemplateK0pqq_EtwWriteTransfer((_DWORD)a1, (unsigned int)Dxgk_SetPowerComponentFState, a3, (_DWORD)a1, a2, a3);
    v7 = *((_QWORD *)v5 + 419);
    v8 = 520 * v3;
    if ( *(_BYTE *)(520 * v3 + v7 + 360) )
    {
      v6 = 0;
      v9 = (_BYTE *)(v8 + v7 + 359);
    }
    else
    {
      if ( (*((int *)v5 + 716) >= 0x2000 || *((_BYTE *)v5 + 3164)) && *(_DWORD *)(v8 + v7 + 208) == 3 )
      {
        v19 = 0;
      }
      else
      {
        v19 = 1;
        *(_DWORD *)(v8 + v7 + 344) = v4;
      }
      v9 = (_BYTE *)(v8 + v7 + 359);
      *v9 = 1;
      if ( v4 )
      {
        a1 = *(struct DXGADAPTER **)(v8 + v7 + 512);
        if ( a1 )
          DXGPOWERSTATISTICSTRANSITIONENGINE::RecordEnteringIdleFState((struct DXGADAPTER *)((char *)a1 + 136));
      }
      if ( v19 )
      {
        v21 = *(_DWORD *)(v8 + v7 + 4);
        v26 = -1;
        v27 = 0;
        if ( (qword_1401604F0 & 2) != 0 )
        {
          v28 = 1;
          v26 = 5124;
          if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
            McTemplateK0q_EtwWriteTransfer(a1, EventProfilerEnter, a3, 5124);
        }
        else
        {
          v28 = 0;
        }
        DXGETWPROFILER_BASE::PushProfilerEntry(&v26, 5124);
        _InterlockedAdd((volatile signed __int32 *)v5 + 1233, 1u);
        CurrentIrql = KeGetCurrentIrql();
        v25 = 0;
        if ( CurrentIrql < 2u && (Current = DXGTHREAD::GetCurrent(), (v25 = Current) != 0) )
          v10 = *((_DWORD *)Current + 10);
        else
          v10 = 0;
        v23 = v10;
        DXGVALIDATIONPROCESSATTACH::DXGVALIDATIONPROCESSATTACH((DXGVALIDATIONPROCESSATTACH *)v29, v5);
        v22 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v5 + 105))(*((_QWORD *)v5 + 36), v21, v4);
        if ( v29[0] )
          KeUnstackDetachProcess(&ApcState);
        if ( CurrentIrql != KeGetCurrentIrql() )
        {
          v18 = KeGetCurrentIrql();
          WdLogSingleEntry5(0, 275, 16, v5, CurrentIrql, v18);
          WdLogGlobalForLineNumber = 2579;
        }
        if ( v25 )
        {
          v15 = *((int *)v25 + 10);
          if ( (_DWORD)v15 != v23 )
          {
            WdLogSingleEntry5(0, 275, 38, v15, v23, 0);
            WdLogGlobalForLineNumber = 73;
          }
        }
        _InterlockedDecrement((volatile signed __int32 *)v5 + 1233);
        if ( v22 != -1071775466 && v22 )
        {
          WdLogSingleEntry1(2, v22);
          WdLogGlobalForLineNumber = 2581;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Driver returned an invalid NTSTATUS code: 0x%I64x",
            v22,
            0,
            0,
            0,
            0);
          v4 = v24;
        }
        DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v26);
        if ( v28 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
          McTemplateK0q_EtwWriteTransfer(v11, EventProfilerExit, a3, v26);
      }
    }
    if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
      McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, Dxgk_SetPowerComponentFStateEnd, a3, v5, v3);
    if ( (*(_DWORD *)(v8 + v7 + 216) & 2) == 0 )
    {
      *v9 = 0;
      PoFxCompleteIdleState(*((_QWORD *)v5 + 420), (unsigned int)v3);
      if ( v6 )
      {
        if ( !v4 )
        {
          v12 = *(_QWORD *)(v8 + v7 + 512);
          if ( v12 )
            DXGPOWERSTATISTICSTRANSITIONENGINE::RecordLeavingIdleFState((DXGPOWERSTATISTICSTRANSITIONENGINE *)(v12 + 136));
        }
        if ( *(_DWORD *)(v8 + v7 + 208) == 7 )
        {
          v13 = *(_DWORD *)(v8 + v7 + 4);
          Global = DXGGLOBAL::GetGlobal();
          DXGGLOBAL::NotifySharedPowerGraphicsFStateTransition(Global, v5, v13, v24, 0);
        }
      }
    }
  }
  else
  {
    PoFxCompleteIdleState(*((_QWORD *)a1 + 420), a2);
  }
}

```

## disassembly

```asm
0x1400125c0  mov     [rsp-8+arg_18], rbx
0x1400125c5  push    rbp
0x1400125c6  push    rsi
0x1400125c7  push    rdi
0x1400125c8  push    r12
0x1400125ca  push    r13
0x1400125cc  push    r14
0x1400125ce  push    r15
0x1400125d0  lea     rbp, [rsp-27h]
0x1400125d5  sub     rsp, 0C0h
0x1400125dc  mov     rax, cs:__security_cookie
0x1400125e3  xor     rax, rsp
0x1400125e6  mov     [rbp+57h+var_38], rax
0x1400125ea  xor     r12d, r12d
0x1400125ed  mov     r13d, edx
0x1400125f0  mov     ebx, r8d
0x1400125f3  mov     rdi, rcx
0x1400125f6  mov     esi, 1
0x1400125fb  mov     [rbp+57h+var_94], ebx
0x1400125fe  cmp     [rcx+1040h], r12
0x140012605  jnz     loc_140012930
0x14001260b  mov     eax, [rcx+0C8h]
0x140012611  cmp     eax, esi
0x140012613  jnz     loc_14001284E
0x140012619  cmp     cs:bTracingEnabled, r12b
0x140012620  jz      short loc_14001262F
0x140012622  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x140012629  jnz     loc_1400128F3
0x14001262f  mov     r15, [rdi+0D18h]
0x140012636  imul    r14, r13, 208h
0x14001263d  cmp     [r14+r15+168h], r12b
0x140012645  jnz     loc_140012888
0x14001264b  cmp     dword ptr [rdi+0B30h], 2000h
0x140012655  jl      loc_1400128E1
0x14001265b  cmp     dword ptr [r14+r15+0D0h], 3
0x140012664  jz      loc_1400129F5
0x14001266a  mov     [rbp+57h+var_A0], sil
0x14001266e  mov     [r14+r15+158h], ebx
0x140012676  lea     r12, [r15+167h]
0x14001267d  add     r12, r14
0x140012680  mov     [r12], sil
0x140012684  test    ebx, ebx
0x140012686  jnz     loc_140012866
0x14001268c  cmp     [rbp+57h+var_A0], 0
0x140012690  jz      loc_1400127A3
0x140012696  test    byte ptr cs:qword_1401604F0, 2
0x14001269d  mov     eax, [r14+r15+4]
0x1400126a2  mov     [rbp+57h+var_9C], eax
0x1400126a5  mov     [rbp+57h+var_88], 0FFFFFFFFh
0x1400126ac  mov     [rbp+57h+var_80], 0
0x1400126b4  jnz     short loc_1400126BC
0x1400126b6  mov     [rbp+57h+var_78], 0
0x1400126ba  jmp     short loc_1400126D4
0x1400126bc  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, sil
0x1400126c3  mov     [rbp+57h+var_78], sil
0x1400126c7  mov     [rbp+57h+var_88], 1404h
0x1400126ce  jnz     loc_1400129FE
0x1400126d4  mov     edx, 1404h
0x1400126d9  lea     rcx, [rbp+57h+var_88]
0x1400126dd  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1400126e2  lock add [rdi+1344h], esi
0x1400126e9  call    cs:__imp_KeGetCurrentIrql
0x1400126f0  nop     dword ptr [rax+rax+00h]
0x1400126f5  mov     [rbp+57h+var_A0], al
0x1400126f8  mov     [rbp+57h+var_90], 0
0x140012700  cmp     al, 2
0x140012702  jb      loc_140012A15
0x140012708  xor     ecx, ecx
0x14001270a  mov     [rbp+57h+var_98], ecx
0x14001270d  mov     rdx, rdi; struct DXGADAPTER *
0x140012710  lea     rcx, [rbp+57h+var_70]; this
0x140012714  call    ??0DXGVALIDATIONPROCESSATTACH@@QEAA@PEAVDXGADAPTER@@@Z; DXGVALIDATIONPROCESSATTACH::DXGVALIDATIONPROCESSATTACH(DXGADAPTER *)
0x140012719  mov     rax, [rdi+348h]
0x140012720  mov     r8d, ebx
0x140012723  mov     edx, [rbp+57h+var_9C]
0x140012726  mov     rcx, [rdi+120h]
0x14001272d  call    _guard_dispatch_icall
0x140012732  cmp     [rbp+57h+var_70], 0
0x140012736  mov     [rbp+57h+var_9C], eax
0x140012739  jz      short loc_14001274B
0x14001273b  lea     rcx, [rbp+57h+ApcState]; ApcState
0x14001273f  call    cs:__imp_KeUnstackDetachProcess
0x140012746  nop     dword ptr [rax+rax+00h]
0x14001274b  call    cs:__imp_KeGetCurrentIrql
0x140012752  nop     dword ptr [rax+rax+00h]
0x140012757  cmp     [rbp+57h+var_A0], al
0x14001275a  jnz     loc_140012A2F
0x140012760  mov     rax, [rbp+57h+var_90]
0x140012764  test    rax, rax
0x140012767  jnz     loc_14001289A
0x14001276d  lock dec dword ptr [rdi+1344h]
0x140012774  movsxd  rax, [rbp+57h+var_9C]
0x140012778  cmp     eax, 0C01E0116h
0x14001277d  jz      short loc_140012787
0x14001277f  test    eax, eax
0x140012781  jnz     loc_140012A75
0x140012787  lea     rcx, [rbp+57h+var_88]; this
0x14001278b  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x140012790  cmp     [rbp+57h+var_78], 0
0x140012794  jz      short loc_1400127A3
0x140012796  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, sil
0x14001279d  jnz     loc_140012AD0
0x1400127a3  cmp     cs:bTracingEnabled, 0
0x1400127aa  jz      short loc_1400127B9
0x1400127ac  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x1400127b3  jnz     loc_140012910
0x1400127b9  mov     eax, [r14+r15+0D8h]
0x1400127c1  test    al, 2
0x1400127c3  jnz     short loc_140012826
0x1400127c5  mov     byte ptr [r12], 0
0x1400127ca  mov     edx, r13d
0x1400127cd  mov     rcx, [rdi+0D20h]
0x1400127d4  call    cs:__imp_PoFxCompleteIdleState
0x1400127db  nop     dword ptr [rax+rax+00h]
0x1400127e0  test    sil, sil
0x1400127e3  jz      short loc_140012826
0x1400127e5  test    ebx, ebx
0x1400127e7  jnz     short loc_1400127FA
0x1400127e9  mov     rcx, [r14+r15+200h]
0x1400127f1  test    rcx, rcx
0x1400127f4  jnz     loc_140012AE5
0x1400127fa  cmp     dword ptr [r14+r15+0D0h], 7
0x140012803  jnz     short loc_140012826
0x140012805  mov     ebx, [r14+r15+4]
0x14001280a  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x14001280f  mov     r9d, [rbp+57h+var_94]; unsigned int
0x140012813  mov     r8d, ebx; unsigned int
0x140012816  mov     rdx, rdi; void *
0x140012819  mov     byte ptr [rsp+0F0h+Timeout], 0; char
0x14001281e  mov     rcx, rax; this
0x140012821  call    ?NotifySharedPowerGraphicsFStateTransition@DXGGLOBAL@@QEAAXQEAXKIE@Z; DXGGLOBAL::NotifySharedPowerGraphicsFStateTransition(void * const,ulong,uint,uchar)
0x140012826  mov     rcx, [rbp+57h+var_38]
0x14001282a  xor     rcx, rsp; StackCookie
0x14001282d  call    __security_check_cookie
0x140012832  mov     rbx, [rsp+0F0h+arg_18]
0x14001283a  add     rsp, 0C0h
0x140012841  pop     r15
0x140012843  pop     r14
0x140012845  pop     r13
0x140012847  pop     r12
0x140012849  pop     rdi
0x14001284a  pop     rsi
0x14001284b  pop     rbp
0x14001284c  retn
0x14001284e  mov     rcx, [rcx+0D20h]
0x140012855  mov     edx, r13d
0x140012858  call    cs:__imp_PoFxCompleteIdleState
0x14001285f  nop     dword ptr [rax+rax+00h]
0x140012864  jmp     short loc_140012826
0x140012866  mov     rcx, [r14+r15+200h]
0x14001286e  test    rcx, rcx
0x140012871  jz      loc_14001268C
0x140012877  add     rcx, 88h; this
0x14001287e  call    ?RecordEnteringIdleFState@DXGPOWERSTATISTICSTRANSITIONENGINE@@QEAAXXZ; DXGPOWERSTATISTICSTRANSITIONENGINE::RecordEnteringIdleFState(void)
0x140012883  jmp     loc_14001268C
0x140012888  mov     sil, r12b
0x14001288b  lea     r12, [r15+167h]
0x140012892  add     r12, r14
0x140012895  jmp     loc_1400127A3
0x14001289a  movsxd  rcx, dword ptr [rax+28h]
0x14001289e  movsxd  rax, [rbp+57h+var_98]
0x1400128a2  cmp     ecx, eax
0x1400128a4  jz      loc_14001276D
0x1400128aa  mov     r9, rcx
0x1400128ad  mov     [rsp+0F0h+var_C8], 0
0x1400128b6  xor     ecx, ecx
0x1400128b8  mov     [rsp+0F0h+Timeout], rax
0x1400128bd  mov     edx, 113h
0x1400128c2  lea     r8d, [rcx+26h]
0x1400128c6  call    cs:__imp_WdLogSingleEntry5
0x1400128cd  nop     dword ptr [rax+rax+00h]
0x1400128d2  mov     cs:WdLogGlobalForLineNumber, 49h ; 'I'
0x1400128dc  jmp     loc_14001276D
0x1400128e1  cmp     [rdi+0C5Ch], r12b
0x1400128e8  jnz     loc_14001265B
0x1400128ee  jmp     loc_14001266A
0x1400128f3  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x1400128f7  lea     rdx, Dxgk_SetPowerComponentFState
0x1400128fe  mov     r9, rdi
0x140012901  mov     dword ptr [rsp+0F0h+Timeout], r13d
0x140012906  call    McTemplateK0pqq_EtwWriteTransfer
0x14001290b  jmp     loc_14001262F
0x140012910  mov     r9, rdi
0x140012913  mov     dword ptr [rsp+0F0h+Timeout], r13d
0x140012918  lea     rdx, Dxgk_SetPowerComponentFStateEnd
0x14001291f  lea     rcx, DxgkControlGuid_Context
0x140012926  call    McTemplateK0pt_EtwWriteTransfer
0x14001292b  jmp     loc_1400127B9
0x140012930  cmp     r13d, esi
0x140012933  jz      short loc_14001293F
0x140012935  cmp     r13d, 4
0x140012939  jnz     loc_14001260B
0x14001293f  mov     eax, esi
0x140012941  lock xadd [rcx+1018h], eax
0x140012949  add     eax, esi
0x14001294b  cmp     eax, esi
0x14001294d  jle     loc_14001260B
0x140012953  lea     rcx, [rdi+1030h]; ListHead
0x14001295a  call    cs:__imp_ExpInterlockedPopEntrySList
0x140012961  nop     dword ptr [rax+rax+00h]
0x140012966  test    rax, rax
0x140012969  jnz     short loc_1400129B0
0x14001296b  call    cs:__imp_KeGetCurrentIrql
0x140012972  nop     dword ptr [rax+rax+00h]
0x140012977  cmp     al, 2
0x140012979  jb      short loc_14001298E
0x14001297b  mov     ecx, 64h ; 'd'; MicroSeconds
0x140012980  call    cs:__imp_KeStallExecutionProcessor
0x140012987  nop     dword ptr [rax+rax+00h]
0x14001298c  jmp     short loc_140012953
0x14001298e  lea     rcx, [rdi+0FF8h]; Object
0x140012995  mov     [rsp+0F0h+Timeout], r12; Timeout
0x14001299a  xor     r9d, r9d; Alertable
0x14001299d  xor     r8d, r8d; WaitMode
0x1400129a0  xor     edx, edx; WaitReason
0x1400129a2  call    cs:__imp_KeWaitForSingleObject
0x1400129a9  nop     dword ptr [rax+rax+00h]
0x1400129ae  jmp     short loc_140012953
0x1400129b0  lea     r8, [rdi+1010h]; Lock
0x1400129b7  mov     [rax+10h], r13d
0x1400129bb  lea     rcx, [rdi+1020h]; ListHead
0x1400129c2  mov     [rax+14h], ebx
0x1400129c5  mov     rdx, rax; ListEntry
0x1400129c8  mov     [rax+18h], r12b
0x1400129cc  call    cs:__imp_ExInterlockedInsertTailList
0x1400129d3  nop     dword ptr [rax+rax+00h]
0x1400129d8  lea     rcx, [rdi+0FC8h]; Event
0x1400129df  xor     r8d, r8d; Wait
0x1400129e2  xor     edx, edx; Increment
0x1400129e4  call    cs:__imp_KeSetEvent
0x1400129eb  nop     dword ptr [rax+rax+00h]
0x1400129f0  jmp     loc_140012826
0x1400129f5  mov     [rbp+57h+var_A0], r12b
0x1400129f9  jmp     loc_140012676
0x1400129fe  mov     r9d, 1404h
0x140012a04  lea     rdx, EventProfilerEnter
0x140012a0b  call    McTemplateK0q_EtwWriteTransfer
0x140012a10  jmp     loc_1400126D4
0x140012a15  call    ?GetCurrent@DXGTHREAD@@SAPEAV1@XZ; DXGTHREAD::GetCurrent(void)
0x140012a1a  mov     [rbp+57h+var_90], rax
0x140012a1e  test    rax, rax
0x140012a21  jz      loc_140012708
0x140012a27  mov     ecx, [rax+28h]
0x140012a2a  jmp     loc_14001270A
0x140012a2f  call    cs:__imp_KeGetCurrentIrql
0x140012a36  nop     dword ptr [rax+rax+00h]
0x140012a3b  movzx   ecx, [rbp+57h+var_A0]
0x140012a3f  mov     r9, rdi
0x140012a42  movzx   eax, al
0x140012a45  mov     edx, 113h
0x140012a4a  mov     [rsp+0F0h+var_C8], rax
0x140012a4f  mov     [rsp+0F0h+Timeout], rcx
0x140012a54  xor     ecx, ecx
0x140012a56  lea     r8d, [rcx+10h]
0x140012a5a  call    cs:__imp_WdLogSingleEntry5
0x140012a61  nop     dword ptr [rax+rax+00h]
0x140012a66  mov     cs:WdLogGlobalForLineNumber, 0A13h
0x140012a70  jmp     loc_140012760
0x140012a75  mov     rdx, rax
0x140012a78  mov     ecx, 2
0x140012a7d  mov     rbx, rax
0x140012a80  call    cs:__imp_WdLogSingleEntry1
0x140012a87  nop     dword ptr [rax+rax+00h]
0x140012a8c  xor     eax, eax
0x140012a8e  mov     cs:WdLogGlobalForLineNumber, 0A15h
0x140012a98  mov     [rsp+0F0h+var_B0], rax
0x140012a9d  lea     r9, aDriverReturned; "Driver returned an invalid NTSTATUS cod"...
0x140012aa4  mov     [rsp+0F0h+var_B8], rax
0x140012aa9  or      r8d, 0FFFFFFFFh
0x140012aad  mov     [rsp+0F0h+var_C0], rax
0x140012ab2  mov     edx, 40000h
0x140012ab7  mov     [rsp+0F0h+var_C8], rax
0x140012abc  xor     ecx, ecx
0x140012abe  mov     [rsp+0F0h+Timeout], rbx
0x140012ac3  call    DxgkLogInternalTriageEvent
0x140012ac8  mov     ebx, [rbp+57h+var_94]
0x140012acb  jmp     loc_140012787
0x140012ad0  mov     r9d, [rbp+57h+var_88]
0x140012ad4  lea     rdx, EventProfilerExit
0x140012adb  call    McTemplateK0q_EtwWriteTransfer
0x140012ae0  jmp     loc_1400127A3
0x140012ae5  add     rcx, 88h; this
0x140012aec  call    ?RecordLeavingIdleFState@DXGPOWERSTATISTICSTRANSITIONENGINE@@QEAAXXZ; DXGPOWERSTATISTICSTRANSITIONENGINE::RecordLeavingIdleFState(void)
0x140012af1  jmp     loc_1400127FA
```
