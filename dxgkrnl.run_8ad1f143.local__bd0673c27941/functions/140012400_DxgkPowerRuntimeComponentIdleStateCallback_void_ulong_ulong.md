# DxgkPowerRuntimeComponentIdleStateCallback(void *,ulong,ulong)

- ea: `0x140012400`
- end: `0x140012936`
- name: `?DxgkPowerRuntimeComponentIdleStateCallback@@YAXPEAXKK@Z`
- size: `1334`
- prototype: `void __fastcall(struct DXGADAPTER *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x140012380`
- `0x140012400`
- `0x14001293c`
- `0x140012b14`
- `0x140013860`
- `0x140013c80`
- `0x14001b890`
- `0x14001becc`
- `0x14001d0e4`
- `0x14001d6b4`
- `0x140060570`
- `0x1400796f8`
- `0x1400a0100`
- `0x1400a01e0`
- `0x140310f10`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x14001257f`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001257f`
- `ntoskrnl!PoFxCompleteIdleState` at `0x140012614`
- `ntoskrnl!PoFxCompleteIdleState` at `0x140012698`
- `ntoskrnl!PoFxCompleteIdleState` at `0x140012614`
- `ntoskrnl!PoFxCompleteIdleState` at `0x140012698`
- `ntoskrnl!KeSetEvent` at `0x140012824`
- `ntoskrnl!KeSetEvent` at `0x140012824`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001280c`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001280c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400127e2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400127e2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012529`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001258b`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400127ab`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001286f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012529`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001258b`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400127ab`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001286f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001279a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001279a`
- `HAL!KeStallExecutionProcessor` at `0x1400127c0`
- `HAL!KeStallExecutionProcessor` at `0x1400127c0`
- `watchdog!WdLogSingleEntry5` at `0x140012706`
- `watchdog!WdLogSingleEntry5` at `0x14001289a`
- `watchdog!WdLogSingleEntry5` at `0x140012706`
- `watchdog!WdLogSingleEntry5` at `0x14001289a`
- `watchdog!WdLogSingleEntry1` at `0x1400128c0`
- `watchdog!WdLogSingleEntry1` at `0x1400128c0`

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
  if ( *((_QWORD *)a1 + 518) && (a2 == 1 || a2 == 4) && _InterlockedIncrement((volatile signed __int32 *)a1 + 1026) > 1 )
  {
    while ( 1 )
    {
      v16 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v5 + 258);
      if ( v16 )
        break;
      if ( KeGetCurrentIrql() < 2u )
        KeWaitForSingleObject((char *)v5 + 4072, Executive, 0, 0, 0);
      else
        KeStallExecutionProcessor(0x64u);
    }
    LODWORD(v16[1].Next) = v3;
    HIDWORD(v16[1].Next) = v4;
    *((_BYTE *)&v16[1].Next + 8) = 0;
    ExInterlockedInsertTailList((PLIST_ENTRY)v5 + 257, (PLIST_ENTRY)v16, (PKSPIN_LOCK)v5 + 512);
    KeSetEvent((PRKEVENT)((char *)v5 + 4024), 0, 0);
  }
  else if ( *((_DWORD *)a1 + 50) == 1 )
  {
    if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
      McTemplateK0pqq_EtwWriteTransfer((_DWORD)a1, (unsigned int)Dxgk_SetPowerComponentFState, a3, (_DWORD)a1, a2, a3);
    v7 = *((_QWORD *)v5 + 417);
    v8 = 520 * v3;
    if ( *(_BYTE *)(520 * v3 + v7 + 360) )
    {
      v6 = 0;
      v9 = (_BYTE *)(v8 + v7 + 359);
    }
    else
    {
      if ( (*((int *)v5 + 712) >= 0x2000 || *((_BYTE *)v5 + 3148)) && *(_DWORD *)(v8 + v7 + 208) == 3 )
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
        if ( (qword_14015C500 & 2) != 0 )
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
        _InterlockedAdd((volatile signed __int32 *)v5 + 1229, 1u);
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
        _InterlockedDecrement((volatile signed __int32 *)v5 + 1229);
        if ( v22 != -1071775466 && v22 )
        {
          WdLogSingleEntry1(2);
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
      PoFxCompleteIdleState(*((_QWORD *)v5 + 418), (unsigned int)v3);
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
    PoFxCompleteIdleState(*((_QWORD *)a1 + 418), a2);
  }
}

```

## disassembly

```asm
0x140012400  mov     [rsp-8+arg_18], rbx
0x140012405  push    rbp
0x140012406  push    rsi
0x140012407  push    rdi
0x140012408  push    r12
0x14001240a  push    r13
0x14001240c  push    r14
0x14001240e  push    r15
0x140012410  lea     rbp, [rsp-27h]
0x140012415  sub     rsp, 0C0h
0x14001241c  mov     rax, cs:__security_cookie
0x140012423  xor     rax, rsp
0x140012426  mov     [rbp+57h+var_38], rax
0x14001242a  xor     r12d, r12d
0x14001242d  mov     r13d, edx
0x140012430  mov     ebx, r8d
0x140012433  mov     rdi, rcx
0x140012436  mov     esi, 1
0x14001243b  mov     [rbp+57h+var_94], ebx
0x14001243e  cmp     [rcx+1030h], r12
0x140012445  jnz     loc_140012770
0x14001244b  mov     eax, [rcx+0C8h]
0x140012451  cmp     eax, esi
0x140012453  jnz     loc_14001268E
0x140012459  cmp     cs:bTracingEnabled, r12b
0x140012460  jz      short loc_14001246F
0x140012462  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x140012469  jnz     loc_140012733
0x14001246f  mov     r15, [rdi+0D08h]
0x140012476  imul    r14, r13, 208h
0x14001247d  cmp     [r14+r15+168h], r12b
0x140012485  jnz     loc_1400126C8
0x14001248b  cmp     dword ptr [rdi+0B20h], 2000h
0x140012495  jl      loc_140012721
0x14001249b  cmp     dword ptr [r14+r15+0D0h], 3
0x1400124a4  jz      loc_140012835
0x1400124aa  mov     [rbp+57h+var_A0], sil
0x1400124ae  mov     [r14+r15+158h], ebx
0x1400124b6  lea     r12, [r15+167h]
0x1400124bd  add     r12, r14
0x1400124c0  mov     [r12], sil
0x1400124c4  test    ebx, ebx
0x1400124c6  jnz     loc_1400126A6
0x1400124cc  cmp     [rbp+57h+var_A0], 0
0x1400124d0  jz      loc_1400125E3
0x1400124d6  test    byte ptr cs:qword_14015C500, 2
0x1400124dd  mov     eax, [r14+r15+4]
0x1400124e2  mov     [rbp+57h+var_9C], eax
0x1400124e5  mov     [rbp+57h+var_88], 0FFFFFFFFh
0x1400124ec  mov     [rbp+57h+var_80], 0
0x1400124f4  jnz     short loc_1400124FC
0x1400124f6  mov     [rbp+57h+var_78], 0
0x1400124fa  jmp     short loc_140012514
0x1400124fc  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, sil
0x140012503  mov     [rbp+57h+var_78], sil
0x140012507  mov     [rbp+57h+var_88], 1404h
0x14001250e  jnz     loc_14001283E
0x140012514  mov     edx, 1404h
0x140012519  lea     rcx, [rbp+57h+var_88]
0x14001251d  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x140012522  lock add [rdi+1334h], esi
0x140012529  call    cs:__imp_KeGetCurrentIrql
0x140012530  nop     dword ptr [rax+rax+00h]
0x140012535  mov     [rbp+57h+var_A0], al
0x140012538  mov     [rbp+57h+var_90], 0
0x140012540  cmp     al, 2
0x140012542  jb      loc_140012855
0x140012548  xor     ecx, ecx
0x14001254a  mov     [rbp+57h+var_98], ecx
0x14001254d  mov     rdx, rdi; struct DXGADAPTER *
0x140012550  lea     rcx, [rbp+57h+var_70]; this
0x140012554  call    ??0DXGVALIDATIONPROCESSATTACH@@QEAA@PEAVDXGADAPTER@@@Z; DXGVALIDATIONPROCESSATTACH::DXGVALIDATIONPROCESSATTACH(DXGADAPTER *)
0x140012559  mov     rax, [rdi+348h]
0x140012560  mov     r8d, ebx
0x140012563  mov     edx, [rbp+57h+var_9C]
0x140012566  mov     rcx, [rdi+120h]
0x14001256d  call    _guard_dispatch_icall
0x140012572  cmp     [rbp+57h+var_70], 0
0x140012576  mov     [rbp+57h+var_9C], eax
0x140012579  jz      short loc_14001258B
0x14001257b  lea     rcx, [rbp+57h+ApcState]; ApcState
0x14001257f  call    cs:__imp_KeUnstackDetachProcess
0x140012586  nop     dword ptr [rax+rax+00h]
0x14001258b  call    cs:__imp_KeGetCurrentIrql
0x140012592  nop     dword ptr [rax+rax+00h]
0x140012597  cmp     [rbp+57h+var_A0], al
0x14001259a  jnz     loc_14001286F
0x1400125a0  mov     rax, [rbp+57h+var_90]
0x1400125a4  test    rax, rax
0x1400125a7  jnz     loc_1400126DA
0x1400125ad  lock dec dword ptr [rdi+1334h]
0x1400125b4  movsxd  rax, [rbp+57h+var_9C]
0x1400125b8  cmp     eax, 0C01E0116h
0x1400125bd  jz      short loc_1400125C7
0x1400125bf  test    eax, eax
0x1400125c1  jnz     loc_1400128B5
0x1400125c7  lea     rcx, [rbp+57h+var_88]; this
0x1400125cb  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400125d0  cmp     [rbp+57h+var_78], 0
0x1400125d4  jz      short loc_1400125E3
0x1400125d6  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, sil
0x1400125dd  jnz     loc_140012910
0x1400125e3  cmp     cs:bTracingEnabled, 0
0x1400125ea  jz      short loc_1400125F9
0x1400125ec  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x1400125f3  jnz     loc_140012750
0x1400125f9  mov     eax, [r14+r15+0D8h]
0x140012601  test    al, 2
0x140012603  jnz     short loc_140012666
0x140012605  mov     byte ptr [r12], 0
0x14001260a  mov     edx, r13d
0x14001260d  mov     rcx, [rdi+0D10h]
0x140012614  call    cs:__imp_PoFxCompleteIdleState
0x14001261b  nop     dword ptr [rax+rax+00h]
0x140012620  test    sil, sil
0x140012623  jz      short loc_140012666
0x140012625  test    ebx, ebx
0x140012627  jnz     short loc_14001263A
0x140012629  mov     rcx, [r14+r15+200h]
0x140012631  test    rcx, rcx
0x140012634  jnz     loc_140012925
0x14001263a  cmp     dword ptr [r14+r15+0D0h], 7
0x140012643  jnz     short loc_140012666
0x140012645  mov     ebx, [r14+r15+4]
0x14001264a  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x14001264f  mov     r9d, [rbp+57h+var_94]; unsigned int
0x140012653  mov     r8d, ebx; unsigned int
0x140012656  mov     rdx, rdi; void *
0x140012659  mov     byte ptr [rsp+0F0h+Timeout], 0; char
0x14001265e  mov     rcx, rax; this
0x140012661  call    ?NotifySharedPowerGraphicsFStateTransition@DXGGLOBAL@@QEAAXQEAXKIE@Z; DXGGLOBAL::NotifySharedPowerGraphicsFStateTransition(void * const,ulong,uint,uchar)
0x140012666  mov     rcx, [rbp+57h+var_38]
0x14001266a  xor     rcx, rsp; StackCookie
0x14001266d  call    __security_check_cookie
0x140012672  mov     rbx, [rsp+0F0h+arg_18]
0x14001267a  add     rsp, 0C0h
0x140012681  pop     r15
0x140012683  pop     r14
0x140012685  pop     r13
0x140012687  pop     r12
0x140012689  pop     rdi
0x14001268a  pop     rsi
0x14001268b  pop     rbp
0x14001268c  retn
0x14001268e  mov     rcx, [rcx+0D10h]
0x140012695  mov     edx, r13d
0x140012698  call    cs:__imp_PoFxCompleteIdleState
0x14001269f  nop     dword ptr [rax+rax+00h]
0x1400126a4  jmp     short loc_140012666
0x1400126a6  mov     rcx, [r14+r15+200h]
0x1400126ae  test    rcx, rcx
0x1400126b1  jz      loc_1400124CC
0x1400126b7  add     rcx, 88h; this
0x1400126be  call    ?RecordEnteringIdleFState@DXGPOWERSTATISTICSTRANSITIONENGINE@@QEAAXXZ; DXGPOWERSTATISTICSTRANSITIONENGINE::RecordEnteringIdleFState(void)
0x1400126c3  jmp     loc_1400124CC
0x1400126c8  mov     sil, r12b
0x1400126cb  lea     r12, [r15+167h]
0x1400126d2  add     r12, r14
0x1400126d5  jmp     loc_1400125E3
0x1400126da  movsxd  rcx, dword ptr [rax+28h]
0x1400126de  movsxd  rax, [rbp+57h+var_98]
0x1400126e2  cmp     ecx, eax
0x1400126e4  jz      loc_1400125AD
0x1400126ea  mov     r9, rcx
0x1400126ed  mov     [rsp+0F0h+var_C8], 0
0x1400126f6  xor     ecx, ecx
0x1400126f8  mov     [rsp+0F0h+Timeout], rax
0x1400126fd  mov     edx, 113h
0x140012702  lea     r8d, [rcx+26h]
0x140012706  call    cs:__imp_WdLogSingleEntry5
0x14001270d  nop     dword ptr [rax+rax+00h]
0x140012712  mov     cs:WdLogGlobalForLineNumber, 49h ; 'I'
0x14001271c  jmp     loc_1400125AD
0x140012721  cmp     [rdi+0C4Ch], r12b
0x140012728  jnz     loc_14001249B
0x14001272e  jmp     loc_1400124AA
0x140012733  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x140012737  lea     rdx, Dxgk_SetPowerComponentFState
0x14001273e  mov     r9, rdi
0x140012741  mov     dword ptr [rsp+0F0h+Timeout], r13d
0x140012746  call    McTemplateK0pqq_EtwWriteTransfer
0x14001274b  jmp     loc_14001246F
0x140012750  mov     r9, rdi
0x140012753  mov     dword ptr [rsp+0F0h+Timeout], r13d
0x140012758  lea     rdx, Dxgk_SetPowerComponentFStateEnd
0x14001275f  lea     rcx, DxgkControlGuid_Context
0x140012766  call    McTemplateK0pt_EtwWriteTransfer
0x14001276b  jmp     loc_1400125F9
0x140012770  cmp     r13d, esi
0x140012773  jz      short loc_14001277F
0x140012775  cmp     r13d, 4
0x140012779  jnz     loc_14001244B
0x14001277f  mov     eax, esi
0x140012781  lock xadd [rcx+1008h], eax
0x140012789  add     eax, esi
0x14001278b  cmp     eax, esi
0x14001278d  jle     loc_14001244B
0x140012793  lea     rcx, [rdi+1020h]; ListHead
0x14001279a  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400127a1  nop     dword ptr [rax+rax+00h]
0x1400127a6  test    rax, rax
0x1400127a9  jnz     short loc_1400127F0
0x1400127ab  call    cs:__imp_KeGetCurrentIrql
0x1400127b2  nop     dword ptr [rax+rax+00h]
0x1400127b7  cmp     al, 2
0x1400127b9  jb      short loc_1400127CE
0x1400127bb  mov     ecx, 64h ; 'd'; MicroSeconds
0x1400127c0  call    cs:__imp_KeStallExecutionProcessor
0x1400127c7  nop     dword ptr [rax+rax+00h]
0x1400127cc  jmp     short loc_140012793
0x1400127ce  lea     rcx, [rdi+0FE8h]; Object
0x1400127d5  mov     [rsp+0F0h+Timeout], r12; Timeout
0x1400127da  xor     r9d, r9d; Alertable
0x1400127dd  xor     r8d, r8d; WaitMode
0x1400127e0  xor     edx, edx; WaitReason
0x1400127e2  call    cs:__imp_KeWaitForSingleObject
0x1400127e9  nop     dword ptr [rax+rax+00h]
0x1400127ee  jmp     short loc_140012793
0x1400127f0  lea     r8, [rdi+1000h]; Lock
0x1400127f7  mov     [rax+10h], r13d
0x1400127fb  lea     rcx, [rdi+1010h]; ListHead
0x140012802  mov     [rax+14h], ebx
0x140012805  mov     rdx, rax; ListEntry
0x140012808  mov     [rax+18h], r12b
0x14001280c  call    cs:__imp_ExInterlockedInsertTailList
0x140012813  nop     dword ptr [rax+rax+00h]
0x140012818  lea     rcx, [rdi+0FB8h]; Event
0x14001281f  xor     r8d, r8d; Wait
0x140012822  xor     edx, edx; Increment
0x140012824  call    cs:__imp_KeSetEvent
0x14001282b  nop     dword ptr [rax+rax+00h]
0x140012830  jmp     loc_140012666
0x140012835  mov     [rbp+57h+var_A0], r12b
0x140012839  jmp     loc_1400124B6
0x14001283e  mov     r9d, 1404h
0x140012844  lea     rdx, EventProfilerEnter
0x14001284b  call    McTemplateK0q_EtwWriteTransfer
0x140012850  jmp     loc_140012514
0x140012855  call    ?GetCurrent@DXGTHREAD@@SAPEAV1@XZ; DXGTHREAD::GetCurrent(void)
0x14001285a  mov     [rbp+57h+var_90], rax
0x14001285e  test    rax, rax
0x140012861  jz      loc_140012548
0x140012867  mov     ecx, [rax+28h]
0x14001286a  jmp     loc_14001254A
0x14001286f  call    cs:__imp_KeGetCurrentIrql
0x140012876  nop     dword ptr [rax+rax+00h]
0x14001287b  movzx   ecx, [rbp+57h+var_A0]
0x14001287f  mov     r9, rdi
0x140012882  movzx   eax, al
0x140012885  mov     edx, 113h
0x14001288a  mov     [rsp+0F0h+var_C8], rax
0x14001288f  mov     [rsp+0F0h+Timeout], rcx
0x140012894  xor     ecx, ecx
0x140012896  lea     r8d, [rcx+10h]
0x14001289a  call    cs:__imp_WdLogSingleEntry5
0x1400128a1  nop     dword ptr [rax+rax+00h]
0x1400128a6  mov     cs:WdLogGlobalForLineNumber, 0A13h
0x1400128b0  jmp     loc_1400125A0
0x1400128b5  mov     rdx, rax
0x1400128b8  mov     ecx, 2
0x1400128bd  mov     rbx, rax
0x1400128c0  call    cs:__imp_WdLogSingleEntry1
0x1400128c7  nop     dword ptr [rax+rax+00h]
0x1400128cc  xor     eax, eax
0x1400128ce  mov     cs:WdLogGlobalForLineNumber, 0A15h
0x1400128d8  mov     [rsp+0F0h+var_B0], rax
0x1400128dd  lea     r9, aDriverReturned; "Driver returned an invalid NTSTATUS cod"...
0x1400128e4  mov     [rsp+0F0h+var_B8], rax
0x1400128e9  or      r8d, 0FFFFFFFFh
0x1400128ed  mov     [rsp+0F0h+var_C0], rax
0x1400128f2  mov     edx, 40000h
0x1400128f7  mov     [rsp+0F0h+var_C8], rax
0x1400128fc  xor     ecx, ecx
0x1400128fe  mov     [rsp+0F0h+Timeout], rbx
0x140012903  call    DxgkLogInternalTriageEvent
0x140012908  mov     ebx, [rbp+57h+var_94]
0x14001290b  jmp     loc_1400125C7
0x140012910  mov     r9d, [rbp+57h+var_88]
0x140012914  lea     rdx, EventProfilerExit
0x14001291b  call    McTemplateK0q_EtwWriteTransfer
0x140012920  jmp     loc_1400125E3
0x140012925  add     rcx, 88h; this
0x14001292c  call    ?RecordLeavingIdleFState@DXGPOWERSTATISTICSTRANSITIONENGINE@@QEAAXXZ; DXGPOWERSTATISTICSTRANSITIONENGINE::RecordLeavingIdleFState(void)
0x140012931  jmp     loc_14001263A
```
