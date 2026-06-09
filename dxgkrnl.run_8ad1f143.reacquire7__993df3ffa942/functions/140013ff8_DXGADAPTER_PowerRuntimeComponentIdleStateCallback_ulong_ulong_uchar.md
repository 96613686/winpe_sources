# DXGADAPTER::PowerRuntimeComponentIdleStateCallback(ulong,ulong,uchar)

- ea: `0x140013ff8`
- end: `0x140014547`
- name: `?PowerRuntimeComponentIdleStateCallback@DXGADAPTER@@QEAAXKKE@Z`
- size: `1359`
- prototype: `void __fastcall(DXGADAPTER *__hidden this, unsigned int, unsigned int, unsigned __int8)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x140018ef4`
- `0x14001d430`

## callees

- `0x140012540`
- `0x140012afc`
- `0x140012cd4`
- `0x140013a20`
- `0x140013e40`
- `0x140013ff8`
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

- `ntoskrnl!KeUnstackDetachProcess` at `0x140014181`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140014181`
- `ntoskrnl!PoFxCompleteIdleState` at `0x14001421c`
- `ntoskrnl!PoFxCompleteIdleState` at `0x1400142a5`
- `ntoskrnl!PoFxCompleteIdleState` at `0x14001421c`
- `ntoskrnl!PoFxCompleteIdleState` at `0x1400142a5`
- `ntoskrnl!KeSetEvent` at `0x140014435`
- `ntoskrnl!KeSetEvent` at `0x140014435`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001441d`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001441d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400143f3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400143f3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001412b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001418d`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400143b8`
- `ntoskrnl!KeGetCurrentIrql` at `0x140014480`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001412b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001418d`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400143b8`
- `ntoskrnl!KeGetCurrentIrql` at `0x140014480`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400143a7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400143a7`
- `HAL!KeStallExecutionProcessor` at `0x1400143cd`
- `HAL!KeStallExecutionProcessor` at `0x1400143cd`
- `watchdog!WdLogSingleEntry5` at `0x140014313`
- `watchdog!WdLogSingleEntry5` at `0x1400144ab`
- `watchdog!WdLogSingleEntry5` at `0x140014313`
- `watchdog!WdLogSingleEntry5` at `0x1400144ab`
- `watchdog!WdLogSingleEntry1` at `0x1400144d1`
- `watchdog!WdLogSingleEntry1` at `0x1400144d1`

## pseudocode

```c
void __fastcall DXGADAPTER::PowerRuntimeComponentIdleStateCallback(
        DXGADAPTER *this,
        unsigned int a2,
        __int64 a3,
        char a4)
{
  unsigned int v4; // ebx
  DXGADAPTER *v6; // rdi
  __int64 v7; // r13
  char v8; // si
  __int64 v9; // r15
  __int64 v10; // r14
  _BYTE *v11; // r12
  int v12; // ecx
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int v15; // ebx
  DXGGLOBAL *Global; // rax
  PSLIST_ENTRY v17; // rax
  struct DXGTHREAD *Current; // rax
  char v19; // [rsp+50h] [rbp-49h]
  KIRQL CurrentIrql; // [rsp+50h] [rbp-49h]
  unsigned int v22; // [rsp+54h] [rbp-45h]
  int v23; // [rsp+54h] [rbp-45h]
  int v24; // [rsp+58h] [rbp-41h]
  unsigned int v25; // [rsp+5Ch] [rbp-3Dh]
  struct DXGTHREAD *v26; // [rsp+60h] [rbp-39h]
  unsigned int v27; // [rsp+68h] [rbp-31h] BYREF
  __int64 v28; // [rsp+70h] [rbp-29h]
  char v29; // [rsp+78h] [rbp-21h]
  _BYTE v30[8]; // [rsp+80h] [rbp-19h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+88h] [rbp-11h] BYREF

  v4 = a3;
  v25 = a3;
  v6 = this;
  v7 = a2;
  v8 = 1;
  if ( *((_QWORD *)this + 520)
    && (a2 == 1 || a2 == 4)
    && _InterlockedIncrement((volatile signed __int32 *)this + 1030) > 1 )
  {
    while ( 1 )
    {
      v17 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v6 + 259);
      if ( v17 )
        break;
      if ( KeGetCurrentIrql() < 2u )
        KeWaitForSingleObject((char *)v6 + 4088, Executive, 0, 0, 0);
      else
        KeStallExecutionProcessor(0x64u);
    }
    LODWORD(v17[1].Next) = v7;
    HIDWORD(v17[1].Next) = v4;
    *((_BYTE *)&v17[1].Next + 8) = a4;
    ExInterlockedInsertTailList((PLIST_ENTRY)v6 + 258, (PLIST_ENTRY)v17, (PKSPIN_LOCK)v6 + 514);
    KeSetEvent((PRKEVENT)((char *)v6 + 4040), 0, 0);
  }
  else if ( *((_DWORD *)this + 50) == 1 )
  {
    if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
      McTemplateK0pqq_EtwWriteTransfer(
        (_DWORD)this,
        (unsigned int)Dxgk_SetPowerComponentFState,
        a3,
        (_DWORD)this,
        a2,
        a3);
    v9 = *((_QWORD *)v6 + 419);
    v10 = 520 * v7;
    if ( !a4 && *(_BYTE *)(v10 + v9 + 360) )
    {
      v8 = 0;
      v11 = (_BYTE *)(v10 + v9 + 359);
    }
    else
    {
      if ( (*((int *)v6 + 716) >= 0x2000 || *((_BYTE *)v6 + 3164)) && *(_DWORD *)(v10 + v9 + 208) == 3 )
      {
        v19 = 0;
      }
      else
      {
        v19 = 1;
        *(_DWORD *)(v10 + v9 + 344) = v4;
      }
      v11 = (_BYTE *)(v10 + v9 + 359);
      *v11 = 1;
      if ( v4 )
      {
        this = *(DXGADAPTER **)(v10 + v9 + 512);
        if ( this )
          DXGPOWERSTATISTICSTRANSITIONENGINE::RecordEnteringIdleFState((DXGADAPTER *)((char *)this + 136));
      }
      if ( v19 )
      {
        v22 = *(_DWORD *)(v10 + v9 + 4);
        v27 = -1;
        v28 = 0;
        if ( (qword_1401604F0 & 2) != 0 )
        {
          v29 = 1;
          v27 = 5124;
          if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
            McTemplateK0q_EtwWriteTransfer(this, EventProfilerEnter, a3, 5124);
        }
        else
        {
          v29 = 0;
        }
        DXGETWPROFILER_BASE::PushProfilerEntry(&v27, 5124);
        _InterlockedAdd((volatile signed __int32 *)v6 + 1233, 1u);
        CurrentIrql = KeGetCurrentIrql();
        v26 = 0;
        if ( CurrentIrql < 2u && (Current = DXGTHREAD::GetCurrent(), (v26 = Current) != 0) )
          v12 = *((_DWORD *)Current + 10);
        else
          v12 = 0;
        v24 = v12;
        DXGVALIDATIONPROCESSATTACH::DXGVALIDATIONPROCESSATTACH((DXGVALIDATIONPROCESSATTACH *)v30, v6);
        v23 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v6 + 105))(*((_QWORD *)v6 + 36), v22, v4);
        if ( v30[0] )
          KeUnstackDetachProcess(&ApcState);
        if ( CurrentIrql != KeGetCurrentIrql() )
        {
          KeGetCurrentIrql();
          WdLogSingleEntry5(0, 275, 16);
          WdLogGlobalForLineNumber = 2579;
        }
        if ( v26 && *((_DWORD *)v26 + 10) != v24 )
        {
          WdLogSingleEntry5(0, 275, 38);
          WdLogGlobalForLineNumber = 73;
        }
        _InterlockedDecrement((volatile signed __int32 *)v6 + 1233);
        if ( v23 != -1071775466 && v23 )
        {
          WdLogSingleEntry1(2, v23);
          WdLogGlobalForLineNumber = 2581;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Driver returned an invalid NTSTATUS code: 0x%I64x",
            v23,
            0,
            0,
            0,
            0);
          v4 = v25;
        }
        DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v27);
        if ( v29 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
          McTemplateK0q_EtwWriteTransfer(v13, EventProfilerExit, a3, v27);
      }
    }
    if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
      McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, Dxgk_SetPowerComponentFStateEnd, a3, v6, v7);
    if ( (*(_DWORD *)(v10 + v9 + 216) & 2) == 0 )
    {
      *v11 = 0;
      if ( !a4 )
        PoFxCompleteIdleState(*((_QWORD *)v6 + 420), (unsigned int)v7);
      if ( v8 )
      {
        if ( !v4 )
        {
          v14 = *(_QWORD *)(v10 + v9 + 512);
          if ( v14 )
            DXGPOWERSTATISTICSTRANSITIONENGINE::RecordLeavingIdleFState((DXGPOWERSTATISTICSTRANSITIONENGINE *)(v14 + 136));
        }
        if ( *(_DWORD *)(v10 + v9 + 208) == 7 )
        {
          v15 = *(_DWORD *)(v10 + v9 + 4);
          Global = DXGGLOBAL::GetGlobal();
          DXGGLOBAL::NotifySharedPowerGraphicsFStateTransition(Global, v6, v15, v25, 0);
        }
      }
    }
  }
  else if ( !a4 )
  {
    PoFxCompleteIdleState(*((_QWORD *)this + 420), a2);
  }
}

```

## disassembly

```asm
0x140013ff8  mov     [rsp-8+arg_18], rbx
0x140013ffd  push    rbp
0x140013ffe  push    rsi
0x140013fff  push    rdi
0x140014000  push    r12
0x140014002  push    r13
0x140014004  push    r14
0x140014006  push    r15
0x140014008  lea     rbp, [rsp-27h]
0x14001400d  sub     rsp, 0C0h
0x140014014  mov     rax, cs:__security_cookie
0x14001401b  xor     rax, rsp
0x14001401e  mov     [rbp+57h+var_38], rax
0x140014022  cmp     qword ptr [rcx+1040h], 0
0x14001402a  mov     ebx, r8d
0x14001402d  mov     [rbp+57h+var_94], ebx
0x140014030  mov     r12b, r9b
0x140014033  mov     [rbp+57h+var_9F], r9b
0x140014037  mov     rdi, rcx
0x14001403a  mov     r13d, edx
0x14001403d  mov     esi, 1
0x140014042  jnz     loc_14001437D
0x140014048  mov     eax, [rcx+0C8h]
0x14001404e  cmp     eax, esi
0x140014050  jnz     loc_140014296
0x140014056  cmp     cs:bTracingEnabled, 0
0x14001405d  jz      short loc_14001406C
0x14001405f  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x140014066  jnz     loc_140014340
0x14001406c  mov     r15, [rdi+0D18h]
0x140014073  imul    r14, r13, 208h
0x14001407a  test    r12b, r12b
0x14001407d  jnz     short loc_14001408D
0x14001407f  cmp     [r14+r15+168h], r12b
0x140014087  jnz     loc_1400142D5
0x14001408d  cmp     dword ptr [rdi+0B30h], 2000h
0x140014097  jl      loc_14001432E
0x14001409d  cmp     dword ptr [r14+r15+0D0h], 3
0x1400140a6  jz      loc_140014446
0x1400140ac  mov     [rbp+57h+var_A0], sil
0x1400140b0  mov     [r14+r15+158h], ebx
0x1400140b8  lea     r12, [r15+167h]
0x1400140bf  add     r12, r14
0x1400140c2  mov     [r12], sil
0x1400140c6  test    ebx, ebx
0x1400140c8  jnz     loc_1400142B3
0x1400140ce  cmp     [rbp+57h+var_A0], 0
0x1400140d2  jz      loc_1400141E5
0x1400140d8  test    byte ptr cs:qword_1401604F0, 2
0x1400140df  mov     eax, [r14+r15+4]
0x1400140e4  mov     [rbp+57h+var_9C], eax
0x1400140e7  mov     [rbp+57h+var_88], 0FFFFFFFFh
0x1400140ee  mov     [rbp+57h+var_80], 0
0x1400140f6  jnz     short loc_1400140FE
0x1400140f8  mov     [rbp+57h+var_78], 0
0x1400140fc  jmp     short loc_140014116
0x1400140fe  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, sil
0x140014105  mov     [rbp+57h+var_78], sil
0x140014109  mov     [rbp+57h+var_88], 1404h
0x140014110  jnz     loc_14001444F
0x140014116  mov     edx, 1404h
0x14001411b  lea     rcx, [rbp+57h+var_88]
0x14001411f  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x140014124  lock add [rdi+1344h], esi
0x14001412b  call    cs:__imp_KeGetCurrentIrql
0x140014132  nop     dword ptr [rax+rax+00h]
0x140014137  mov     [rbp+57h+var_A0], al
0x14001413a  mov     [rbp+57h+var_90], 0
0x140014142  cmp     al, 2
0x140014144  jb      loc_140014466
0x14001414a  xor     ecx, ecx
0x14001414c  mov     [rbp+57h+var_98], ecx
0x14001414f  mov     rdx, rdi; struct DXGADAPTER *
0x140014152  lea     rcx, [rbp+57h+var_70]; this
0x140014156  call    ??0DXGVALIDATIONPROCESSATTACH@@QEAA@PEAVDXGADAPTER@@@Z; DXGVALIDATIONPROCESSATTACH::DXGVALIDATIONPROCESSATTACH(DXGADAPTER *)
0x14001415b  mov     rax, [rdi+348h]
0x140014162  mov     r8d, ebx
0x140014165  mov     edx, [rbp+57h+var_9C]
0x140014168  mov     rcx, [rdi+120h]
0x14001416f  call    _guard_dispatch_icall
0x140014174  cmp     [rbp+57h+var_70], 0
0x140014178  mov     [rbp+57h+var_9C], eax
0x14001417b  jz      short loc_14001418D
0x14001417d  lea     rcx, [rbp+57h+ApcState]; ApcState
0x140014181  call    cs:__imp_KeUnstackDetachProcess
0x140014188  nop     dword ptr [rax+rax+00h]
0x14001418d  call    cs:__imp_KeGetCurrentIrql
0x140014194  nop     dword ptr [rax+rax+00h]
0x140014199  cmp     [rbp+57h+var_A0], al
0x14001419c  jnz     loc_140014480
0x1400141a2  mov     rax, [rbp+57h+var_90]
0x1400141a6  test    rax, rax
0x1400141a9  jnz     loc_1400142E7
0x1400141af  lock dec dword ptr [rdi+1344h]
0x1400141b6  movsxd  rax, [rbp+57h+var_9C]
0x1400141ba  cmp     eax, 0C01E0116h
0x1400141bf  jz      short loc_1400141C9
0x1400141c1  test    eax, eax
0x1400141c3  jnz     loc_1400144C6
0x1400141c9  lea     rcx, [rbp+57h+var_88]; this
0x1400141cd  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400141d2  cmp     [rbp+57h+var_78], 0
0x1400141d6  jz      short loc_1400141E5
0x1400141d8  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, sil
0x1400141df  jnz     loc_140014521
0x1400141e5  cmp     cs:bTracingEnabled, 0
0x1400141ec  jz      short loc_1400141FB
0x1400141ee  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x1400141f5  jnz     loc_14001435D
0x1400141fb  mov     eax, [r14+r15+0D8h]
0x140014203  test    al, 2
0x140014205  jnz     short loc_14001426E
0x140014207  cmp     [rbp+57h+var_9F], 0
0x14001420b  mov     byte ptr [r12], 0
0x140014210  jnz     short loc_140014228
0x140014212  mov     rcx, [rdi+0D20h]
0x140014219  mov     edx, r13d
0x14001421c  call    cs:__imp_PoFxCompleteIdleState
0x140014223  nop     dword ptr [rax+rax+00h]
0x140014228  test    sil, sil
0x14001422b  jz      short loc_14001426E
0x14001422d  test    ebx, ebx
0x14001422f  jnz     short loc_140014242
0x140014231  mov     rcx, [r14+r15+200h]
0x140014239  test    rcx, rcx
0x14001423c  jnz     loc_140014536
0x140014242  cmp     dword ptr [r14+r15+0D0h], 7
0x14001424b  jnz     short loc_14001426E
0x14001424d  mov     ebx, [r14+r15+4]
0x140014252  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140014257  mov     r9d, [rbp+57h+var_94]; unsigned int
0x14001425b  mov     r8d, ebx; unsigned int
0x14001425e  mov     rdx, rdi; void *
0x140014261  mov     byte ptr [rsp+0F0h+Timeout], 0; char
0x140014266  mov     rcx, rax; this
0x140014269  call    ?NotifySharedPowerGraphicsFStateTransition@DXGGLOBAL@@QEAAXQEAXKIE@Z; DXGGLOBAL::NotifySharedPowerGraphicsFStateTransition(void * const,ulong,uint,uchar)
0x14001426e  mov     rcx, [rbp+57h+var_38]
0x140014272  xor     rcx, rsp; StackCookie
0x140014275  call    __security_check_cookie
0x14001427a  mov     rbx, [rsp+0F0h+arg_18]
0x140014282  add     rsp, 0C0h
0x140014289  pop     r15
0x14001428b  pop     r14
0x14001428d  pop     r13
0x14001428f  pop     r12
0x140014291  pop     rdi
0x140014292  pop     rsi
0x140014293  pop     rbp
0x140014294  retn
0x140014296  test    r12b, r12b
0x140014299  jnz     short loc_14001426E
0x14001429b  mov     rcx, [rcx+0D20h]
0x1400142a2  mov     edx, r13d
0x1400142a5  call    cs:__imp_PoFxCompleteIdleState
0x1400142ac  nop     dword ptr [rax+rax+00h]
0x1400142b1  jmp     short loc_14001426E
0x1400142b3  mov     rcx, [r14+r15+200h]
0x1400142bb  test    rcx, rcx
0x1400142be  jz      loc_1400140CE
0x1400142c4  add     rcx, 88h; this
0x1400142cb  call    ?RecordEnteringIdleFState@DXGPOWERSTATISTICSTRANSITIONENGINE@@QEAAXXZ; DXGPOWERSTATISTICSTRANSITIONENGINE::RecordEnteringIdleFState(void)
0x1400142d0  jmp     loc_1400140CE
0x1400142d5  xor     sil, sil
0x1400142d8  lea     r12, [r15+167h]
0x1400142df  add     r12, r14
0x1400142e2  jmp     loc_1400141E5
0x1400142e7  movsxd  rcx, dword ptr [rax+28h]
0x1400142eb  movsxd  rax, [rbp+57h+var_98]
0x1400142ef  cmp     ecx, eax
0x1400142f1  jz      loc_1400141AF
0x1400142f7  mov     r9, rcx
0x1400142fa  mov     [rsp+0F0h+var_C8], 0
0x140014303  xor     ecx, ecx
0x140014305  mov     [rsp+0F0h+Timeout], rax
0x14001430a  mov     edx, 113h
0x14001430f  lea     r8d, [rcx+26h]
0x140014313  call    cs:__imp_WdLogSingleEntry5
0x14001431a  nop     dword ptr [rax+rax+00h]
0x14001431f  mov     cs:WdLogGlobalForLineNumber, 49h ; 'I'
0x140014329  jmp     loc_1400141AF
0x14001432e  cmp     byte ptr [rdi+0C5Ch], 0
0x140014335  jnz     loc_14001409D
0x14001433b  jmp     loc_1400140AC
0x140014340  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x140014344  lea     rdx, Dxgk_SetPowerComponentFState
0x14001434b  mov     r9, rdi
0x14001434e  mov     dword ptr [rsp+0F0h+Timeout], r13d
0x140014353  call    McTemplateK0pqq_EtwWriteTransfer
0x140014358  jmp     loc_14001406C
0x14001435d  mov     r9, rdi
0x140014360  mov     dword ptr [rsp+0F0h+Timeout], r13d
0x140014365  lea     rdx, Dxgk_SetPowerComponentFStateEnd
0x14001436c  lea     rcx, DxgkControlGuid_Context
0x140014373  call    McTemplateK0pt_EtwWriteTransfer
0x140014378  jmp     loc_1400141FB
0x14001437d  cmp     r13d, esi
0x140014380  jz      short loc_14001438C
0x140014382  cmp     r13d, 4
0x140014386  jnz     loc_140014048
0x14001438c  mov     eax, esi
0x14001438e  lock xadd [rcx+1018h], eax
0x140014396  add     eax, esi
0x140014398  cmp     eax, esi
0x14001439a  jle     loc_140014048
0x1400143a0  lea     rcx, [rdi+1030h]; ListHead
0x1400143a7  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400143ae  nop     dword ptr [rax+rax+00h]
0x1400143b3  test    rax, rax
0x1400143b6  jnz     short loc_140014401
0x1400143b8  call    cs:__imp_KeGetCurrentIrql
0x1400143bf  nop     dword ptr [rax+rax+00h]
0x1400143c4  cmp     al, 2
0x1400143c6  jb      short loc_1400143DB
0x1400143c8  mov     ecx, 64h ; 'd'; MicroSeconds
0x1400143cd  call    cs:__imp_KeStallExecutionProcessor
0x1400143d4  nop     dword ptr [rax+rax+00h]
0x1400143d9  jmp     short loc_1400143A0
0x1400143db  lea     rcx, [rdi+0FF8h]; Object
0x1400143e2  mov     [rsp+0F0h+Timeout], 0; Timeout
0x1400143eb  xor     r9d, r9d; Alertable
0x1400143ee  xor     r8d, r8d; WaitMode
0x1400143f1  xor     edx, edx; WaitReason
0x1400143f3  call    cs:__imp_KeWaitForSingleObject
0x1400143fa  nop     dword ptr [rax+rax+00h]
0x1400143ff  jmp     short loc_1400143A0
0x140014401  lea     r8, [rdi+1010h]; Lock
0x140014408  mov     [rax+10h], r13d
0x14001440c  lea     rcx, [rdi+1020h]; ListHead
0x140014413  mov     [rax+14h], ebx
0x140014416  mov     rdx, rax; ListEntry
0x140014419  mov     [rax+18h], r12b
0x14001441d  call    cs:__imp_ExInterlockedInsertTailList
0x140014424  nop     dword ptr [rax+rax+00h]
0x140014429  lea     rcx, [rdi+0FC8h]; Event
0x140014430  xor     r8d, r8d; Wait
0x140014433  xor     edx, edx; Increment
0x140014435  call    cs:__imp_KeSetEvent
0x14001443c  nop     dword ptr [rax+rax+00h]
0x140014441  jmp     loc_14001426E
0x140014446  mov     [rbp+57h+var_A0], 0
0x14001444a  jmp     loc_1400140B8
0x14001444f  mov     r9d, 1404h
0x140014455  lea     rdx, EventProfilerEnter
0x14001445c  call    McTemplateK0q_EtwWriteTransfer
0x140014461  jmp     loc_140014116
0x140014466  call    ?GetCurrent@DXGTHREAD@@SAPEAV1@XZ; DXGTHREAD::GetCurrent(void)
0x14001446b  mov     [rbp+57h+var_90], rax
0x14001446f  test    rax, rax
0x140014472  jz      loc_14001414A
0x140014478  mov     ecx, [rax+28h]
0x14001447b  jmp     loc_14001414C
0x140014480  call    cs:__imp_KeGetCurrentIrql
0x140014487  nop     dword ptr [rax+rax+00h]
0x14001448c  movzx   ecx, [rbp+57h+var_A0]
0x140014490  mov     r9, rdi
0x140014493  movzx   eax, al
0x140014496  mov     edx, 113h
0x14001449b  mov     [rsp+0F0h+var_C8], rax
0x1400144a0  mov     [rsp+0F0h+Timeout], rcx
0x1400144a5  xor     ecx, ecx
0x1400144a7  lea     r8d, [rcx+10h]
0x1400144ab  call    cs:__imp_WdLogSingleEntry5
0x1400144b2  nop     dword ptr [rax+rax+00h]
0x1400144b7  mov     cs:WdLogGlobalForLineNumber, 0A13h
0x1400144c1  jmp     loc_1400141A2
0x1400144c6  mov     rdx, rax
0x1400144c9  mov     ecx, 2
0x1400144ce  mov     rbx, rax
0x1400144d1  call    cs:__imp_WdLogSingleEntry1
0x1400144d8  nop     dword ptr [rax+rax+00h]
0x1400144dd  xor     eax, eax
0x1400144df  mov     cs:WdLogGlobalForLineNumber, 0A15h
0x1400144e9  mov     [rsp+0F0h+var_B0], rax
0x1400144ee  lea     r9, aDriverReturned; "Driver returned an invalid NTSTATUS cod"...
0x1400144f5  mov     [rsp+0F0h+var_B8], rax
0x1400144fa  or      r8d, 0FFFFFFFFh
0x1400144fe  mov     [rsp+0F0h+var_C0], rax
0x140014503  mov     edx, 40000h
0x140014508  mov     [rsp+0F0h+var_C8], rax
0x14001450d  xor     ecx, ecx
0x14001450f  mov     [rsp+0F0h+Timeout], rbx
0x140014514  call    DxgkLogInternalTriageEvent
0x140014519  mov     ebx, [rbp+57h+var_94]
0x14001451c  jmp     loc_1400141C9
0x140014521  mov     r9d, [rbp+57h+var_88]
0x140014525  lea     rdx, EventProfilerExit
0x14001452c  call    McTemplateK0q_EtwWriteTransfer
0x140014531  jmp     loc_1400141E5
0x140014536  add     rcx, 88h; this
0x14001453d  call    ?RecordLeavingIdleFState@DXGPOWERSTATISTICSTRANSITIONENGINE@@QEAAXXZ; DXGPOWERSTATISTICSTRANSITIONENGINE::RecordLeavingIdleFState(void)
0x140014542  jmp     loc_140014242
```
