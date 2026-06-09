# DXGADAPTER::PowerRuntimeComponentIdleStateCallback(ulong,ulong,uchar)

- ea: `0x140013e38`
- end: `0x140014387`
- name: `?PowerRuntimeComponentIdleStateCallback@DXGADAPTER@@QEAAXKKE@Z`
- size: `1359`
- prototype: `void __fastcall(DXGADAPTER *__hidden this, unsigned int, unsigned int, unsigned __int8)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x140018e54`
- `0x14001d300`

## callees

- `0x140012380`
- `0x14001293c`
- `0x140012b14`
- `0x140013860`
- `0x140013c80`
- `0x140013e38`
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

- `ntoskrnl!KeUnstackDetachProcess` at `0x140013fc1`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140013fc1`
- `ntoskrnl!PoFxCompleteIdleState` at `0x14001405c`
- `ntoskrnl!PoFxCompleteIdleState` at `0x1400140e5`
- `ntoskrnl!PoFxCompleteIdleState` at `0x14001405c`
- `ntoskrnl!PoFxCompleteIdleState` at `0x1400140e5`
- `ntoskrnl!KeSetEvent` at `0x140014275`
- `ntoskrnl!KeSetEvent` at `0x140014275`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001425d`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001425d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014233`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014233`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013f6b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013fcd`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400141f8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400142c0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013f6b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013fcd`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400141f8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400142c0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400141e7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400141e7`
- `HAL!KeStallExecutionProcessor` at `0x14001420d`
- `HAL!KeStallExecutionProcessor` at `0x14001420d`
- `watchdog!WdLogSingleEntry5` at `0x140014153`
- `watchdog!WdLogSingleEntry5` at `0x1400142eb`
- `watchdog!WdLogSingleEntry5` at `0x140014153`
- `watchdog!WdLogSingleEntry5` at `0x1400142eb`
- `watchdog!WdLogSingleEntry1` at `0x140014311`
- `watchdog!WdLogSingleEntry1` at `0x140014311`

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
  __int64 v17; // rcx
  PSLIST_ENTRY v18; // rax
  struct DXGTHREAD *Current; // rax
  KIRQL v20; // al
  char v21; // [rsp+50h] [rbp-49h]
  KIRQL CurrentIrql; // [rsp+50h] [rbp-49h]
  unsigned int v24; // [rsp+54h] [rbp-45h]
  int v25; // [rsp+54h] [rbp-45h]
  int v26; // [rsp+58h] [rbp-41h]
  unsigned int v27; // [rsp+5Ch] [rbp-3Dh]
  struct DXGTHREAD *v28; // [rsp+60h] [rbp-39h]
  unsigned int v29; // [rsp+68h] [rbp-31h] BYREF
  __int64 v30; // [rsp+70h] [rbp-29h]
  char v31; // [rsp+78h] [rbp-21h]
  _BYTE v32[8]; // [rsp+80h] [rbp-19h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+88h] [rbp-11h] BYREF

  v4 = a3;
  v27 = a3;
  v6 = this;
  v7 = a2;
  v8 = 1;
  if ( *((_QWORD *)this + 518)
    && (a2 == 1 || a2 == 4)
    && _InterlockedIncrement((volatile signed __int32 *)this + 1026) > 1 )
  {
    while ( 1 )
    {
      v18 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v6 + 258);
      if ( v18 )
        break;
      if ( KeGetCurrentIrql() < 2u )
        KeWaitForSingleObject((char *)v6 + 4072, Executive, 0, 0, 0);
      else
        KeStallExecutionProcessor(0x64u);
    }
    LODWORD(v18[1].Next) = v7;
    HIDWORD(v18[1].Next) = v4;
    *((_BYTE *)&v18[1].Next + 8) = a4;
    ExInterlockedInsertTailList((PLIST_ENTRY)v6 + 257, (PLIST_ENTRY)v18, (PKSPIN_LOCK)v6 + 512);
    KeSetEvent((PRKEVENT)((char *)v6 + 4024), 0, 0);
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
    v9 = *((_QWORD *)v6 + 417);
    v10 = 520 * v7;
    if ( !a4 && *(_BYTE *)(v10 + v9 + 360) )
    {
      v8 = 0;
      v11 = (_BYTE *)(v10 + v9 + 359);
    }
    else
    {
      if ( (*((int *)v6 + 712) >= 0x2000 || *((_BYTE *)v6 + 3148)) && *(_DWORD *)(v10 + v9 + 208) == 3 )
      {
        v21 = 0;
      }
      else
      {
        v21 = 1;
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
      if ( v21 )
      {
        v24 = *(_DWORD *)(v10 + v9 + 4);
        v29 = -1;
        v30 = 0;
        if ( (qword_14015C500 & 2) != 0 )
        {
          v31 = 1;
          v29 = 5124;
          if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
            McTemplateK0q_EtwWriteTransfer(this, EventProfilerEnter, a3, 5124);
        }
        else
        {
          v31 = 0;
        }
        DXGETWPROFILER_BASE::PushProfilerEntry(&v29, 5124);
        _InterlockedAdd((volatile signed __int32 *)v6 + 1229, 1u);
        CurrentIrql = KeGetCurrentIrql();
        v28 = 0;
        if ( CurrentIrql < 2u && (Current = DXGTHREAD::GetCurrent(), (v28 = Current) != 0) )
          v12 = *((_DWORD *)Current + 10);
        else
          v12 = 0;
        v26 = v12;
        DXGVALIDATIONPROCESSATTACH::DXGVALIDATIONPROCESSATTACH((DXGVALIDATIONPROCESSATTACH *)v32, v6);
        v25 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v6 + 105))(*((_QWORD *)v6 + 36), v24, v4);
        if ( v32[0] )
          KeUnstackDetachProcess(&ApcState);
        if ( CurrentIrql != KeGetCurrentIrql() )
        {
          v20 = KeGetCurrentIrql();
          WdLogSingleEntry5(0, 275, 16, v6, CurrentIrql, v20);
          WdLogGlobalForLineNumber = 2579;
        }
        if ( v28 )
        {
          v17 = *((int *)v28 + 10);
          if ( (_DWORD)v17 != v26 )
          {
            WdLogSingleEntry5(0, 275, 38, v17, v26, 0);
            WdLogGlobalForLineNumber = 73;
          }
        }
        _InterlockedDecrement((volatile signed __int32 *)v6 + 1229);
        if ( v25 != -1071775466 && v25 )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 2581;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Driver returned an invalid NTSTATUS code: 0x%I64x",
            v25,
            0,
            0,
            0,
            0);
          v4 = v27;
        }
        DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v29);
        if ( v31 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
          McTemplateK0q_EtwWriteTransfer(v13, EventProfilerExit, a3, v29);
      }
    }
    if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
      McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, Dxgk_SetPowerComponentFStateEnd, a3, v6, v7);
    if ( (*(_DWORD *)(v10 + v9 + 216) & 2) == 0 )
    {
      *v11 = 0;
      if ( !a4 )
        PoFxCompleteIdleState(*((_QWORD *)v6 + 418), (unsigned int)v7);
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
          DXGGLOBAL::NotifySharedPowerGraphicsFStateTransition(Global, v6, v15, v27, 0);
        }
      }
    }
  }
  else if ( !a4 )
  {
    PoFxCompleteIdleState(*((_QWORD *)this + 418), a2);
  }
}

```

## disassembly

```asm
0x140013e38  mov     [rsp-8+arg_18], rbx
0x140013e3d  push    rbp
0x140013e3e  push    rsi
0x140013e3f  push    rdi
0x140013e40  push    r12
0x140013e42  push    r13
0x140013e44  push    r14
0x140013e46  push    r15
0x140013e48  lea     rbp, [rsp-27h]
0x140013e4d  sub     rsp, 0C0h
0x140013e54  mov     rax, cs:__security_cookie
0x140013e5b  xor     rax, rsp
0x140013e5e  mov     [rbp+57h+var_38], rax
0x140013e62  cmp     qword ptr [rcx+1030h], 0
0x140013e6a  mov     ebx, r8d
0x140013e6d  mov     [rbp+57h+var_94], ebx
0x140013e70  mov     r12b, r9b
0x140013e73  mov     [rbp+57h+var_9F], r9b
0x140013e77  mov     rdi, rcx
0x140013e7a  mov     r13d, edx
0x140013e7d  mov     esi, 1
0x140013e82  jnz     loc_1400141BD
0x140013e88  mov     eax, [rcx+0C8h]
0x140013e8e  cmp     eax, esi
0x140013e90  jnz     loc_1400140D6
0x140013e96  cmp     cs:bTracingEnabled, 0
0x140013e9d  jz      short loc_140013EAC
0x140013e9f  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x140013ea6  jnz     loc_140014180
0x140013eac  mov     r15, [rdi+0D08h]
0x140013eb3  imul    r14, r13, 208h
0x140013eba  test    r12b, r12b
0x140013ebd  jnz     short loc_140013ECD
0x140013ebf  cmp     [r14+r15+168h], r12b
0x140013ec7  jnz     loc_140014115
0x140013ecd  cmp     dword ptr [rdi+0B20h], 2000h
0x140013ed7  jl      loc_14001416E
0x140013edd  cmp     dword ptr [r14+r15+0D0h], 3
0x140013ee6  jz      loc_140014286
0x140013eec  mov     [rbp+57h+var_A0], sil
0x140013ef0  mov     [r14+r15+158h], ebx
0x140013ef8  lea     r12, [r15+167h]
0x140013eff  add     r12, r14
0x140013f02  mov     [r12], sil
0x140013f06  test    ebx, ebx
0x140013f08  jnz     loc_1400140F3
0x140013f0e  cmp     [rbp+57h+var_A0], 0
0x140013f12  jz      loc_140014025
0x140013f18  test    byte ptr cs:qword_14015C500, 2
0x140013f1f  mov     eax, [r14+r15+4]
0x140013f24  mov     [rbp+57h+var_9C], eax
0x140013f27  mov     [rbp+57h+var_88], 0FFFFFFFFh
0x140013f2e  mov     [rbp+57h+var_80], 0
0x140013f36  jnz     short loc_140013F3E
0x140013f38  mov     [rbp+57h+var_78], 0
0x140013f3c  jmp     short loc_140013F56
0x140013f3e  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, sil
0x140013f45  mov     [rbp+57h+var_78], sil
0x140013f49  mov     [rbp+57h+var_88], 1404h
0x140013f50  jnz     loc_14001428F
0x140013f56  mov     edx, 1404h
0x140013f5b  lea     rcx, [rbp+57h+var_88]
0x140013f5f  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x140013f64  lock add [rdi+1334h], esi
0x140013f6b  call    cs:__imp_KeGetCurrentIrql
0x140013f72  nop     dword ptr [rax+rax+00h]
0x140013f77  mov     [rbp+57h+var_A0], al
0x140013f7a  mov     [rbp+57h+var_90], 0
0x140013f82  cmp     al, 2
0x140013f84  jb      loc_1400142A6
0x140013f8a  xor     ecx, ecx
0x140013f8c  mov     [rbp+57h+var_98], ecx
0x140013f8f  mov     rdx, rdi; struct DXGADAPTER *
0x140013f92  lea     rcx, [rbp+57h+var_70]; this
0x140013f96  call    ??0DXGVALIDATIONPROCESSATTACH@@QEAA@PEAVDXGADAPTER@@@Z; DXGVALIDATIONPROCESSATTACH::DXGVALIDATIONPROCESSATTACH(DXGADAPTER *)
0x140013f9b  mov     rax, [rdi+348h]
0x140013fa2  mov     r8d, ebx
0x140013fa5  mov     edx, [rbp+57h+var_9C]
0x140013fa8  mov     rcx, [rdi+120h]
0x140013faf  call    _guard_dispatch_icall
0x140013fb4  cmp     [rbp+57h+var_70], 0
0x140013fb8  mov     [rbp+57h+var_9C], eax
0x140013fbb  jz      short loc_140013FCD
0x140013fbd  lea     rcx, [rbp+57h+ApcState]; ApcState
0x140013fc1  call    cs:__imp_KeUnstackDetachProcess
0x140013fc8  nop     dword ptr [rax+rax+00h]
0x140013fcd  call    cs:__imp_KeGetCurrentIrql
0x140013fd4  nop     dword ptr [rax+rax+00h]
0x140013fd9  cmp     [rbp+57h+var_A0], al
0x140013fdc  jnz     loc_1400142C0
0x140013fe2  mov     rax, [rbp+57h+var_90]
0x140013fe6  test    rax, rax
0x140013fe9  jnz     loc_140014127
0x140013fef  lock dec dword ptr [rdi+1334h]
0x140013ff6  movsxd  rax, [rbp+57h+var_9C]
0x140013ffa  cmp     eax, 0C01E0116h
0x140013fff  jz      short loc_140014009
0x140014001  test    eax, eax
0x140014003  jnz     loc_140014306
0x140014009  lea     rcx, [rbp+57h+var_88]; this
0x14001400d  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x140014012  cmp     [rbp+57h+var_78], 0
0x140014016  jz      short loc_140014025
0x140014018  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, sil
0x14001401f  jnz     loc_140014361
0x140014025  cmp     cs:bTracingEnabled, 0
0x14001402c  jz      short loc_14001403B
0x14001402e  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x140014035  jnz     loc_14001419D
0x14001403b  mov     eax, [r14+r15+0D8h]
0x140014043  test    al, 2
0x140014045  jnz     short loc_1400140AE
0x140014047  cmp     [rbp+57h+var_9F], 0
0x14001404b  mov     byte ptr [r12], 0
0x140014050  jnz     short loc_140014068
0x140014052  mov     rcx, [rdi+0D10h]
0x140014059  mov     edx, r13d
0x14001405c  call    cs:__imp_PoFxCompleteIdleState
0x140014063  nop     dword ptr [rax+rax+00h]
0x140014068  test    sil, sil
0x14001406b  jz      short loc_1400140AE
0x14001406d  test    ebx, ebx
0x14001406f  jnz     short loc_140014082
0x140014071  mov     rcx, [r14+r15+200h]
0x140014079  test    rcx, rcx
0x14001407c  jnz     loc_140014376
0x140014082  cmp     dword ptr [r14+r15+0D0h], 7
0x14001408b  jnz     short loc_1400140AE
0x14001408d  mov     ebx, [r14+r15+4]
0x140014092  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140014097  mov     r9d, [rbp+57h+var_94]; unsigned int
0x14001409b  mov     r8d, ebx; unsigned int
0x14001409e  mov     rdx, rdi; void *
0x1400140a1  mov     byte ptr [rsp+0F0h+Timeout], 0; char
0x1400140a6  mov     rcx, rax; this
0x1400140a9  call    ?NotifySharedPowerGraphicsFStateTransition@DXGGLOBAL@@QEAAXQEAXKIE@Z; DXGGLOBAL::NotifySharedPowerGraphicsFStateTransition(void * const,ulong,uint,uchar)
0x1400140ae  mov     rcx, [rbp+57h+var_38]
0x1400140b2  xor     rcx, rsp; StackCookie
0x1400140b5  call    __security_check_cookie
0x1400140ba  mov     rbx, [rsp+0F0h+arg_18]
0x1400140c2  add     rsp, 0C0h
0x1400140c9  pop     r15
0x1400140cb  pop     r14
0x1400140cd  pop     r13
0x1400140cf  pop     r12
0x1400140d1  pop     rdi
0x1400140d2  pop     rsi
0x1400140d3  pop     rbp
0x1400140d4  retn
0x1400140d6  test    r12b, r12b
0x1400140d9  jnz     short loc_1400140AE
0x1400140db  mov     rcx, [rcx+0D10h]
0x1400140e2  mov     edx, r13d
0x1400140e5  call    cs:__imp_PoFxCompleteIdleState
0x1400140ec  nop     dword ptr [rax+rax+00h]
0x1400140f1  jmp     short loc_1400140AE
0x1400140f3  mov     rcx, [r14+r15+200h]
0x1400140fb  test    rcx, rcx
0x1400140fe  jz      loc_140013F0E
0x140014104  add     rcx, 88h; this
0x14001410b  call    ?RecordEnteringIdleFState@DXGPOWERSTATISTICSTRANSITIONENGINE@@QEAAXXZ; DXGPOWERSTATISTICSTRANSITIONENGINE::RecordEnteringIdleFState(void)
0x140014110  jmp     loc_140013F0E
0x140014115  xor     sil, sil
0x140014118  lea     r12, [r15+167h]
0x14001411f  add     r12, r14
0x140014122  jmp     loc_140014025
0x140014127  movsxd  rcx, dword ptr [rax+28h]
0x14001412b  movsxd  rax, [rbp+57h+var_98]
0x14001412f  cmp     ecx, eax
0x140014131  jz      loc_140013FEF
0x140014137  mov     r9, rcx
0x14001413a  mov     [rsp+0F0h+var_C8], 0
0x140014143  xor     ecx, ecx
0x140014145  mov     [rsp+0F0h+Timeout], rax
0x14001414a  mov     edx, 113h
0x14001414f  lea     r8d, [rcx+26h]
0x140014153  call    cs:__imp_WdLogSingleEntry5
0x14001415a  nop     dword ptr [rax+rax+00h]
0x14001415f  mov     cs:WdLogGlobalForLineNumber, 49h ; 'I'
0x140014169  jmp     loc_140013FEF
0x14001416e  cmp     byte ptr [rdi+0C4Ch], 0
0x140014175  jnz     loc_140013EDD
0x14001417b  jmp     loc_140013EEC
0x140014180  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x140014184  lea     rdx, Dxgk_SetPowerComponentFState
0x14001418b  mov     r9, rdi
0x14001418e  mov     dword ptr [rsp+0F0h+Timeout], r13d
0x140014193  call    McTemplateK0pqq_EtwWriteTransfer
0x140014198  jmp     loc_140013EAC
0x14001419d  mov     r9, rdi
0x1400141a0  mov     dword ptr [rsp+0F0h+Timeout], r13d
0x1400141a5  lea     rdx, Dxgk_SetPowerComponentFStateEnd
0x1400141ac  lea     rcx, DxgkControlGuid_Context
0x1400141b3  call    McTemplateK0pt_EtwWriteTransfer
0x1400141b8  jmp     loc_14001403B
0x1400141bd  cmp     r13d, esi
0x1400141c0  jz      short loc_1400141CC
0x1400141c2  cmp     r13d, 4
0x1400141c6  jnz     loc_140013E88
0x1400141cc  mov     eax, esi
0x1400141ce  lock xadd [rcx+1008h], eax
0x1400141d6  add     eax, esi
0x1400141d8  cmp     eax, esi
0x1400141da  jle     loc_140013E88
0x1400141e0  lea     rcx, [rdi+1020h]; ListHead
0x1400141e7  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400141ee  nop     dword ptr [rax+rax+00h]
0x1400141f3  test    rax, rax
0x1400141f6  jnz     short loc_140014241
0x1400141f8  call    cs:__imp_KeGetCurrentIrql
0x1400141ff  nop     dword ptr [rax+rax+00h]
0x140014204  cmp     al, 2
0x140014206  jb      short loc_14001421B
0x140014208  mov     ecx, 64h ; 'd'; MicroSeconds
0x14001420d  call    cs:__imp_KeStallExecutionProcessor
0x140014214  nop     dword ptr [rax+rax+00h]
0x140014219  jmp     short loc_1400141E0
0x14001421b  lea     rcx, [rdi+0FE8h]; Object
0x140014222  mov     [rsp+0F0h+Timeout], 0; Timeout
0x14001422b  xor     r9d, r9d; Alertable
0x14001422e  xor     r8d, r8d; WaitMode
0x140014231  xor     edx, edx; WaitReason
0x140014233  call    cs:__imp_KeWaitForSingleObject
0x14001423a  nop     dword ptr [rax+rax+00h]
0x14001423f  jmp     short loc_1400141E0
0x140014241  lea     r8, [rdi+1000h]; Lock
0x140014248  mov     [rax+10h], r13d
0x14001424c  lea     rcx, [rdi+1010h]; ListHead
0x140014253  mov     [rax+14h], ebx
0x140014256  mov     rdx, rax; ListEntry
0x140014259  mov     [rax+18h], r12b
0x14001425d  call    cs:__imp_ExInterlockedInsertTailList
0x140014264  nop     dword ptr [rax+rax+00h]
0x140014269  lea     rcx, [rdi+0FB8h]; Event
0x140014270  xor     r8d, r8d; Wait
0x140014273  xor     edx, edx; Increment
0x140014275  call    cs:__imp_KeSetEvent
0x14001427c  nop     dword ptr [rax+rax+00h]
0x140014281  jmp     loc_1400140AE
0x140014286  mov     [rbp+57h+var_A0], 0
0x14001428a  jmp     loc_140013EF8
0x14001428f  mov     r9d, 1404h
0x140014295  lea     rdx, EventProfilerEnter
0x14001429c  call    McTemplateK0q_EtwWriteTransfer
0x1400142a1  jmp     loc_140013F56
0x1400142a6  call    ?GetCurrent@DXGTHREAD@@SAPEAV1@XZ; DXGTHREAD::GetCurrent(void)
0x1400142ab  mov     [rbp+57h+var_90], rax
0x1400142af  test    rax, rax
0x1400142b2  jz      loc_140013F8A
0x1400142b8  mov     ecx, [rax+28h]
0x1400142bb  jmp     loc_140013F8C
0x1400142c0  call    cs:__imp_KeGetCurrentIrql
0x1400142c7  nop     dword ptr [rax+rax+00h]
0x1400142cc  movzx   ecx, [rbp+57h+var_A0]
0x1400142d0  mov     r9, rdi
0x1400142d3  movzx   eax, al
0x1400142d6  mov     edx, 113h
0x1400142db  mov     [rsp+0F0h+var_C8], rax
0x1400142e0  mov     [rsp+0F0h+Timeout], rcx
0x1400142e5  xor     ecx, ecx
0x1400142e7  lea     r8d, [rcx+10h]
0x1400142eb  call    cs:__imp_WdLogSingleEntry5
0x1400142f2  nop     dword ptr [rax+rax+00h]
0x1400142f7  mov     cs:WdLogGlobalForLineNumber, 0A13h
0x140014301  jmp     loc_140013FE2
0x140014306  mov     rdx, rax
0x140014309  mov     ecx, 2
0x14001430e  mov     rbx, rax
0x140014311  call    cs:__imp_WdLogSingleEntry1
0x140014318  nop     dword ptr [rax+rax+00h]
0x14001431d  xor     eax, eax
0x14001431f  mov     cs:WdLogGlobalForLineNumber, 0A15h
0x140014329  mov     [rsp+0F0h+var_B0], rax
0x14001432e  lea     r9, aDriverReturned; "Driver returned an invalid NTSTATUS cod"...
0x140014335  mov     [rsp+0F0h+var_B8], rax
0x14001433a  or      r8d, 0FFFFFFFFh
0x14001433e  mov     [rsp+0F0h+var_C0], rax
0x140014343  mov     edx, 40000h
0x140014348  mov     [rsp+0F0h+var_C8], rax
0x14001434d  xor     ecx, ecx
0x14001434f  mov     [rsp+0F0h+Timeout], rbx
0x140014354  call    DxgkLogInternalTriageEvent
0x140014359  mov     ebx, [rbp+57h+var_94]
0x14001435c  jmp     loc_140014009
0x140014361  mov     r9d, [rbp+57h+var_88]
0x140014365  lea     rdx, EventProfilerExit
0x14001436c  call    McTemplateK0q_EtwWriteTransfer
0x140014371  jmp     loc_140014025
0x140014376  add     rcx, 88h; this
0x14001437d  call    ?RecordLeavingIdleFState@DXGPOWERSTATISTICSTRANSITIONENGINE@@QEAAXXZ; DXGPOWERSTATISTICSTRANSITIONENGINE::RecordLeavingIdleFState(void)
0x140014382  jmp     loc_140014082
```
