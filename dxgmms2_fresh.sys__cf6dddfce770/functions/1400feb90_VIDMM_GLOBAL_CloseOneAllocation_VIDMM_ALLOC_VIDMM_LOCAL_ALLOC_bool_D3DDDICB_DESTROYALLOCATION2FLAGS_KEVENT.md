# VIDMM_GLOBAL::CloseOneAllocation(VIDMM_ALLOC *,VIDMM_LOCAL_ALLOC * *,bool,_D3DDDICB_DESTROYALLOCATION2FLAGS,_KEVENT * *)

- ea: `0x1400feb90`
- end: `0x1400ff10a`
- name: `?CloseOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_ALLOC@@PEAPEAUVIDMM_LOCAL_ALLOC@@_NU_D3DDDICB_DESTROYALLOCATION2FLAGS@@PEAPEAU_KEVENT@@@Z`
- size: `1402`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_ALLOC *@<rdx>, struct VIDMM_LOCAL_ALLOC **@<r8>, bool@<r9b>, struct _D3DDDICB_DESTROYALLOCATION2FLAGS, struct _KEVENT **)`
- caller_count: `11`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14009d31c`
- `0x14009fcf4`
- `0x1400bfce0`
- `0x1400c12cc`
- `0x1400c1cdc`
- `0x1400f18cc`
- `0x1400f2fbc`
- `0x1400fd7a8`
- `0x1400fdb44`
- `0x1400fdc1c`
- `0x1400fea34`

## callees

- `0x14002bb3c`
- `0x14002bddc`
- `0x14002d8cc`
- `0x14002dab4`
- `0x14002e6c0`
- `0x1400331b4`
- `0x140059030`
- `0x140059380`
- `0x140097b0c`
- `0x1400e8048`
- `0x1400eaf08`
- `0x1400feb90`
- `0x1400ff110`
- `0x1400ff20c`
- `0x1400ff470`
- `0x140119fc4`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400ff050`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400ff050`
- `ntoskrnl!KeReadStateEvent` at `0x1400feeee`
- `ntoskrnl!KeReadStateEvent` at `0x1400feeee`
- `ntoskrnl!KeSetEvent` at `0x1400fee22`
- `ntoskrnl!KeSetEvent` at `0x1400fee22`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400fec3a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400fec3a`
- `watchdog!WdLogSingleEntry2` at `0x1400fef12`
- `watchdog!WdLogSingleEntry2` at `0x1400fef12`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400fee77`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400fef3a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400fee77`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400fef3a`
- `watchdog!WdLogSingleEntry5` at `0x1400ff0f4`
- `watchdog!WdLogSingleEntry5` at `0x1400ff0f4`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400ff0cf`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400febe0`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400fec65`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall VIDMM_GLOBAL::CloseOneAllocation(
        VIDMM_GLOBAL *this,
        __int64 **a2,
        struct VIDMM_LOCAL_ALLOC **a3,
        char a4,
        struct _D3DDDICB_DESTROYALLOCATION2FLAGS a5,
        struct _KEVENT **a6)
{
  __int64 v9; // rdi
  VIDMM_DEVICE *v11; // rcx
  __int64 v12; // rdx
  struct _KTHREAD *CurrentThread; // rcx
  struct CVirtualAddressAllocator *VirtualAddressAllocator; // rax
  char v15; // bp
  struct VIDMM_ALLOC **v16; // r8
  struct VIDMM_ALLOC **v17; // rdx
  __int64 v18; // r13
  unsigned __int64 v19; // rcx
  __int64 result; // rax
  __int64 *v21; // rax
  __int64 v22; // rcx
  bool v23; // r8
  __int64 *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 *v27; // rcx
  __int64 v28; // rbp
  __int64 v29; // rbp
  __int64 v30; // r15
  __int64 v31; // r12
  __int64 v32; // r14
  unsigned int CurrentProcessId; // eax
  __int64 v34; // rcx
  __int64 v35; // [rsp+80h] [rbp-C8h]
  __int64 *v36; // [rsp+88h] [rbp-C0h]
  _BYTE v37[32]; // [rsp+90h] [rbp-B8h] BYREF
  _QWORD v38[19]; // [rsp+B0h] [rbp-98h] BYREF
  int v39; // [rsp+158h] [rbp+10h]
  char v40; // [rsp+160h] [rbp+18h]
  int v41; // [rsp+168h] [rbp+20h]

  LOBYTE(v39) = 0;
  v41 = 0;
  LODWORD(v35) = 0;
  v9 = **a2;
  v36 = a2[1];
  v40 = 0;
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(this, a2) + 24) = a2;
    WdLogGlobalForLineNumber = 5979;
  }
  if ( a3 )
    *a3 = (struct VIDMM_LOCAL_ALLOC *)*a2;
  if ( (byte_140087201 & 0x10) != 0 )
  {
    v24 = a2[2];
    if ( v24 )
    {
      v39 = *((_DWORD *)v24 + 4);
      v25 = v24[5];
      if ( v25 )
      {
        v41 = *(_DWORD *)(v25 + 16);
        v35 = *(_QWORD *)(v25 + 48);
      }
    }
    if ( (**(_DWORD **)(v9 + 392) & 8) != 0 )
      v26 = *(_QWORD *)(v9 + 224);
    else
      v26 = (*a2)[2];
    v40 = v26;
  }
  v11 = (VIDMM_DEVICE *)*((unsigned int *)a2 + 8);
  if ( ((unsigned __int8)v11 & 1) == 0 )
  {
    v21 = a2[1];
    if ( v21 && v21[3] || (*(_DWORD *)(v9 + 32) & 4) != 0 )
    {
      if ( (*(_DWORD *)(v9 + 32) & 4) == 0 )
      {
        VIDMM_GLOBAL::TerminateOneAllocation(this, (struct VIDMM_ALLOC *)a2, (unsigned int)a3, a5, 0);
        goto LABEL_7;
      }
      *((_DWORD *)a2 + 7) |= 4u;
      *((_DWORD *)a2 + 8) = (unsigned int)v11 | 1;
    }
    else
    {
      *((_DWORD *)a2 + 7) |= 4u;
      if ( (*((_DWORD *)a2 + 7) & 3) == 1 )
        VIDMM_DEVICE::UnfaultCommitment(v11, (struct VIDMM_ALLOC *)a2);
      if ( (*(_DWORD *)(v9 + 24) & 4) != 0 )
      {
        v22 = *(_QWORD *)(*(_QWORD *)this + 16LL);
        if ( v22 )
        {
          if ( *(__int64 ***)(v22 + 248) == a2 )
            *(_QWORD *)(v22 + 248) = 0;
        }
      }
    }
    KeSetEvent((PRKEVENT)a2 + 3, 0, 0);
  }
LABEL_7:
  if ( a4 && ((_DWORD)a2[4] & 1) != 0 && !KeReadStateEvent((PRKEVENT)a2 + 3) )
  {
    WdLogSingleEntry2(4, a2, -1071775486);
    result = 3223191810LL;
    WdLogGlobalForLineNumber = 6124;
    *a6 = (struct _KEVENT *)(a2 + 9);
  }
  else
  {
    KeWaitForSingleObject(a2 + 9, Executive, 0, 0, 0);
    CurrentThread = KeGetCurrentThread();
    if ( CurrentThread != *(struct _KTHREAD **)(*(_QWORD *)this + 8LL) )
      VIDMM_GLOBAL::WaitForAllPagingEngines(this, 0, (struct VIDMM_GLOBAL_ALLOC *)v9);
    if ( g_IsInternalReleaseOrDbg )
    {
      *(_QWORD *)(WdLogNewEntry5_WdTrace(CurrentThread, v12) + 24) = a2;
      WdLogGlobalForLineNumber = 6180;
    }
    if ( a2[85] )
    {
      if ( (**(_DWORD **)(v9 + 392) & 0x10000008) != 0 && (*(_DWORD *)(*((_QWORD *)this + 3) + 444LL) & 0x10) == 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v9 + 232) + 64LL))(
          *(_QWORD *)(v9 + 232),
          *(_QWORD *)(v9 + 240));
      a2[85] = 0;
    }
    VirtualAddressAllocator = VIDMM_PROCESS::GetVirtualAddressAllocator(
                                (VIDMM_PROCESS *)(*a2)[1],
                                *(_DWORD *)(*((_QWORD *)this + 3) + 240LL),
                                (*(_DWORD *)(*(_QWORD *)v9 + 60LL) >> 2) & 0x3F);
    if ( VirtualAddressAllocator )
    {
      DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
        (DXGAUTOPUSHLOCKEXCLUSIVE *)v37,
        (struct CVirtualAddressAllocator *)((char *)VirtualAddressAllocator + 64),
        *((_QWORD *)VirtualAddressAllocator + 9) != (_QWORD)KeGetCurrentThread());
      if ( a2[81] != (__int64 *)(a2 + 81) || (v15 = 0, a2[83] != (__int64 *)(a2 + 83)) )
        v15 = 1;
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v37);
      if ( v15 )
      {
        memset(v38, 0, 0x58u);
        v38[0] = -4294967175LL;
        v38[2] = a2;
        VIDMM_GLOBAL::QueueSystemCleanupCommandAndWait(this, (struct VIDMM_SYSTEM_COMMAND *)v38, v23);
      }
    }
    DXGFASTMUTEX::Acquire((DXGFASTMUTEX *)(v9 + 136));
    v16 = (struct VIDMM_ALLOC **)a2[5];
    if ( v16[1] != (struct VIDMM_ALLOC *)(a2 + 5)
      || (v17 = (struct VIDMM_ALLOC **)a2[6], *v17 != (struct VIDMM_ALLOC *)(a2 + 5)) )
    {
      __fastfail(3u);
    }
    *v17 = (struct VIDMM_ALLOC *)v16;
    v16[1] = (struct VIDMM_ALLOC *)v17;
    v18 = *(_QWORD *)(v9 + 240);
    VIDMM_GLOBAL::CloseLocalAllocation(this, (struct VIDMM_LOCAL_ALLOC *)*a2, a3 == 0);
    DXGFASTMUTEX::Release((DXGFASTMUTEX *)(v9 + 136));
    if ( (byte_140087201 & 0x10) != 0 )
    {
      v27 = a2[2];
      if ( v27 )
      {
        v28 = v27[5];
        if ( v28 )
          v29 = *(_QWORD *)(v28 + 56);
        else
          LOBYTE(v29) = 0;
        v30 = v27[5];
      }
      else
      {
        LOBYTE(v30) = 0;
        LOBYTE(v29) = 0;
      }
      v31 = *((_QWORD *)this + 3);
      if ( v36 )
        v32 = v36[3];
      else
        LOBYTE(v32) = 0;
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      McTemplateK0ppppppppppppq_EtwWriteTransfer(
        v41,
        (unsigned int)&EventDestroyDeviceAllocation,
        v35,
        CurrentProcessId,
        v32,
        v31,
        (char)a2,
        v9,
        v30,
        v29,
        v39,
        v41,
        v35,
        v40,
        v18);
    }
    v19 = *(_QWORD *)(*(_QWORD *)v9 + 16LL);
    _InterlockedIncrement((volatile signed __int32 *)this + 952);
    _InterlockedAdd64((volatile signed __int64 *)this + 477, v19);
    VIDMM_DEVICE::NotifyAllocationClosed((VIDMM_DEVICE *)a2[1], (struct VIDMM_ALLOC *)a2);
    if ( *((_DWORD *)a2 + 174) )
    {
      v34 = *((int *)a2 + 174);
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 270, 56, a2, v34, 0);
      WdLogGlobalForLineNumber = 227;
      JUMPOUT(0x1400FF10ALL);
    }
    operator delete(a2);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400feb90  mov     [rsp+arg_0], rbx
0x1400feb95  push    rbp
0x1400feb96  push    rsi
0x1400feb97  push    rdi
0x1400feb98  push    r12
0x1400feb9a  push    r13
0x1400feb9c  push    r14
0x1400feb9e  push    r15
0x1400feba0  sub     rsp, 110h
0x1400feba7  mov     rax, [rdx]
0x1400febaa  xor     r12d, r12d
0x1400febad  mov     bpl, r9b
0x1400febb0  mov     [rsp+148h+arg_8], r12d
0x1400febb8  mov     r14, r8
0x1400febbb  mov     [rsp+148h+arg_18], r12d
0x1400febc3  mov     rbx, rdx
0x1400febc6  mov     [rsp+148h+var_C8], r12
0x1400febce  mov     rdi, [rax]
0x1400febd1  mov     rsi, rcx
0x1400febd4  mov     rax, [rdx+8]
0x1400febd8  mov     [rsp+148h+var_C0], rax
0x1400febe0  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400febe7  mov     [rsp+148h+arg_10], r12
0x1400febef  cmp     [rax], r12b
0x1400febf2  jnz     loc_1400FEE77
0x1400febf8  test    r14, r14
0x1400febfb  jnz     loc_1400FEF78
0x1400fec01  test    cs:byte_140087201, 10h
0x1400fec08  jnz     loc_1400FEF83
0x1400fec0e  mov     ecx, [rbx+20h]; this
0x1400fec11  mov     r15d, 4
0x1400fec17  test    cl, 1
0x1400fec1a  jz      loc_1400FEDB5
0x1400fec20  test    bpl, bpl
0x1400fec23  jnz     loc_1400FEEDC
0x1400fec29  lea     rcx, [rbx+48h]; Object
0x1400fec2d  mov     [rsp+148h+Timeout], r12; Timeout
0x1400fec32  xor     r9d, r9d; Alertable
0x1400fec35  xor     r8d, r8d; WaitMode
0x1400fec38  xor     edx, edx; WaitReason
0x1400fec3a  call    cs:__imp_KeWaitForSingleObject
0x1400fec41  nop     dword ptr [rax+rax+00h]
0x1400fec46  mov     rcx, gs:188h
0x1400fec4f  mov     rax, [rsi]
0x1400fec52  cmp     rcx, [rax+8]
0x1400fec56  jz      short loc_1400FEC65
0x1400fec58  mov     r8, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400fec5b  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400fec5d  mov     rcx, rsi; this
0x1400fec60  call    ?WaitForAllPagingEngines@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::WaitForAllPagingEngines(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x1400fec65  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400fec6c  cmp     [rax], r12b
0x1400fec6f  jnz     loc_1400FEF3A
0x1400fec75  mov     r8, [rbx+2A8h]
0x1400fec7c  test    r8, r8
0x1400fec7f  jnz     loc_1400FEE33
0x1400fec85  mov     rax, [rdi]
0x1400fec88  mov     rdx, [rsi+18h]
0x1400fec8c  mov     rcx, [rbx]
0x1400fec8f  mov     r8d, [rax+3Ch]
0x1400fec93  mov     edx, [rdx+0F0h]; unsigned int
0x1400fec99  mov     rcx, [rcx+8]; this
0x1400fec9d  shr     r8d, 2
0x1400feca1  and     r8d, 3Fh; unsigned int
0x1400feca5  call    ?GetVirtualAddressAllocator@VIDMM_PROCESS@@QEAAPEAVCVirtualAddressAllocator@@KI@Z; VIDMM_PROCESS::GetVirtualAddressAllocator(ulong,uint)
0x1400fecaa  test    rax, rax
0x1400fecad  jz      short loc_1400FECFD
0x1400fecaf  lea     rdx, [rax+40h]; struct DXGPUSHLOCK *
0x1400fecb3  mov     rcx, [rdx+8]
0x1400fecb7  mov     rax, gs:188h
0x1400fecc0  cmp     rcx, rax
0x1400fecc3  lea     rcx, [rsp+148h+var_B8]; this
0x1400feccb  setnz   r8b; unsigned __int8
0x1400feccf  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@E@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const,uchar)
0x1400fecd4  lea     rax, [rbx+288h]
0x1400fecdb  cmp     [rax], rax
0x1400fecde  jz      loc_1400FEF60
0x1400fece4  mov     bpl, 1
0x1400fece7  lea     rcx, [rsp+148h+var_B8]; this
0x1400fecef  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1400fecf4  test    bpl, bpl
0x1400fecf7  jnz     loc_1400FEE96
0x1400fecfd  lea     rbp, [rdi+88h]
0x1400fed04  mov     rcx, rbp; this
0x1400fed07  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x1400fed0c  lea     rax, [rbx+28h]
0x1400fed10  mov     r8, [rax]
0x1400fed13  cmp     [r8+8], rax
0x1400fed17  jnz     loc_1400FEF59
0x1400fed1d  mov     rdx, [rax+8]
0x1400fed21  cmp     [rdx], rax
0x1400fed24  jnz     loc_1400FEF59
0x1400fed2a  mov     [rdx], r8
0x1400fed2d  test    r14, r14
0x1400fed30  mov     [r8+8], rdx
0x1400fed34  mov     rcx, rsi; this
0x1400fed37  mov     rdx, [rbx]; struct VIDMM_LOCAL_ALLOC *
0x1400fed3a  setz    r8b; bool
0x1400fed3e  mov     r13, [rdi+0F0h]
0x1400fed45  call    ?CloseLocalAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_LOCAL_ALLOC@@_N@Z; VIDMM_GLOBAL::CloseLocalAllocation(VIDMM_LOCAL_ALLOC *,bool)
0x1400fed4a  mov     rcx, rbp; this
0x1400fed4d  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400fed52  test    cs:byte_140087201, 10h
0x1400fed59  jnz     loc_1400FF00A
0x1400fed5f  mov     rax, [rdi]
0x1400fed62  mov     rcx, [rax+10h]
0x1400fed66  lock inc dword ptr [rsi+0EE0h]
0x1400fed6d  lock add [rsi+0EE8h], rcx
0x1400fed75  mov     rcx, [rbx+8]; this
0x1400fed79  mov     rdx, rbx; struct VIDMM_ALLOC *
0x1400fed7c  call    ?NotifyAllocationClosed@VIDMM_DEVICE@@QEAAXPEAUVIDMM_ALLOC@@@Z; VIDMM_DEVICE::NotifyAllocationClosed(VIDMM_ALLOC *)
0x1400fed81  mov     eax, [rbx+2B8h]
0x1400fed87  test    eax, eax
0x1400fed89  jnz     loc_1400FF0C8
0x1400fed8f  mov     rcx, rbx; void *
0x1400fed92  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400fed97  xor     eax, eax
0x1400fed99  mov     rbx, [rsp+148h+arg_0]
0x1400feda1  add     rsp, 110h
0x1400feda8  pop     r15
0x1400fedaa  pop     r14
0x1400fedac  pop     r13
0x1400fedae  pop     r12
0x1400fedb0  pop     rdi
0x1400fedb1  pop     rsi
0x1400fedb2  pop     rbp
0x1400fedb3  retn
0x1400fedb5  mov     rax, [rbx+8]
0x1400fedb9  test    rax, rax
0x1400fedbc  jnz     short loc_1400FEDFD
0x1400fedbe  mov     eax, [rdi+20h]
0x1400fedc1  test    r15b, al
0x1400fedc4  jnz     short loc_1400FEE03
0x1400fedc6  or      [rbx+1Ch], r15d
0x1400fedca  mov     eax, [rbx+1Ch]
0x1400fedcd  and     al, 3
0x1400fedcf  cmp     al, 1
0x1400fedd1  jz      loc_1400FEFE0
0x1400fedd7  mov     eax, [rdi+18h]
0x1400fedda  test    r15b, al
0x1400feddd  jz      short loc_1400FEE19
0x1400feddf  mov     rax, [rsi]
0x1400fede2  mov     rcx, [rax+10h]
0x1400fede6  test    rcx, rcx
0x1400fede9  jz      short loc_1400FEE19
0x1400fedeb  cmp     [rcx+0F8h], rbx
0x1400fedf2  jnz     short loc_1400FEE19
0x1400fedf4  mov     [rcx+0F8h], r12
0x1400fedfb  jmp     short loc_1400FEE19
0x1400fedfd  cmp     [rax+18h], r12
0x1400fee01  jz      short loc_1400FEDBE
0x1400fee03  mov     eax, [rdi+20h]
0x1400fee06  test    r15b, al
0x1400fee09  jz      loc_1400FEFED
0x1400fee0f  or      ecx, 1
0x1400fee12  or      [rbx+1Ch], r15d
0x1400fee16  mov     [rbx+20h], ecx
0x1400fee19  lea     rcx, [rbx+48h]; Event
0x1400fee1d  xor     r8d, r8d; Wait
0x1400fee20  xor     edx, edx; Increment
0x1400fee22  call    cs:__imp_KeSetEvent
0x1400fee29  nop     dword ptr [rax+rax+00h]
0x1400fee2e  jmp     loc_1400FEC20
0x1400fee33  mov     rax, [rdi+188h]
0x1400fee3a  test    dword ptr [rax], 10000008h
0x1400fee40  jz      short loc_1400FEE6B
0x1400fee42  mov     rax, [rsi+18h]
0x1400fee46  mov     ecx, [rax+1BCh]
0x1400fee4c  test    cl, 10h
0x1400fee4f  jnz     short loc_1400FEE6B
0x1400fee51  mov     rcx, [rdi+0E8h]
0x1400fee58  mov     rdx, [rdi+0F0h]
0x1400fee5f  mov     rax, [rcx]
0x1400fee62  mov     rax, [rax+40h]
0x1400fee66  call    _guard_dispatch_icall
0x1400fee6b  mov     [rbx+2A8h], r12
0x1400fee72  jmp     loc_1400FEC85
0x1400fee77  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400fee7e  nop     dword ptr [rax+rax+00h]
0x1400fee83  mov     [rax+18h], rbx
0x1400fee87  mov     cs:WdLogGlobalForLineNumber, 175Bh
0x1400fee91  jmp     loc_1400FEBF8
0x1400fee96  xor     edx, edx; Val
0x1400fee98  lea     rcx, [rsp+148h+var_98]; void *
0x1400feea0  lea     r8d, [rdx+58h]; Size
0x1400feea4  call    memset
0x1400feea9  lea     rdx, [rsp+148h+var_98]; struct VIDMM_SYSTEM_COMMAND *
0x1400feeb1  mov     [rsp+148h+var_98], 79h ; 'y'
0x1400feebc  mov     rcx, rsi; this
0x1400feebf  mov     [rsp+148h+var_88], rbx
0x1400feec7  mov     [rsp+148h+var_94], 0FFFFFFFFh
0x1400feed2  call    ?QueueSystemCleanupCommandAndWait@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_SYSTEM_COMMAND@@_N@Z; VIDMM_GLOBAL::QueueSystemCleanupCommandAndWait(VIDMM_SYSTEM_COMMAND *,bool)
0x1400feed7  jmp     loc_1400FECFD
0x1400feedc  mov     eax, [rbx+20h]
0x1400feedf  test    al, 1
0x1400feee1  jz      loc_1400FEC29
0x1400feee7  lea     rbp, [rbx+48h]
0x1400feeeb  mov     rcx, rbp; Event
0x1400feeee  call    cs:__imp_KeReadStateEvent
0x1400feef5  nop     dword ptr [rax+rax+00h]
0x1400feefa  test    eax, eax
0x1400feefc  jnz     loc_1400FEC29
0x1400fef02  mov     rdi, 0FFFFFFFFC01E0102h
0x1400fef09  mov     rdx, rbx
0x1400fef0c  mov     r8, rdi
0x1400fef0f  mov     ecx, r15d
0x1400fef12  call    cs:__imp_WdLogSingleEntry2
0x1400fef19  nop     dword ptr [rax+rax+00h]
0x1400fef1e  mov     rcx, [rsp+148h+arg_28]
0x1400fef26  mov     eax, edi
0x1400fef28  mov     cs:WdLogGlobalForLineNumber, 17ECh
0x1400fef32  mov     [rcx], rbp
0x1400fef35  jmp     loc_1400FED99
0x1400fef3a  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400fef41  nop     dword ptr [rax+rax+00h]
0x1400fef46  mov     [rax+18h], rbx
0x1400fef4a  mov     cs:WdLogGlobalForLineNumber, 1824h
0x1400fef54  jmp     loc_1400FEC75
0x1400fef59  mov     ecx, 3
0x1400fef5e  int     29h; Win8: RtlFailFast(ecx)
0x1400fef60  lea     rax, [rbx+298h]
0x1400fef67  mov     bpl, r12b
0x1400fef6a  cmp     [rax], rax
0x1400fef6d  jnz     loc_1400FECE4
0x1400fef73  jmp     loc_1400FECE7
0x1400fef78  mov     rax, [rbx]
0x1400fef7b  mov     [r14], rax
0x1400fef7e  jmp     loc_1400FEC01
0x1400fef83  mov     rax, [rbx+10h]
0x1400fef87  test    rax, rax
0x1400fef8a  jz      short loc_1400FEFB5
0x1400fef8c  mov     ecx, [rax+10h]
0x1400fef8f  mov     [rsp+148h+arg_8], ecx
0x1400fef96  mov     rcx, [rax+28h]
0x1400fef9a  test    rcx, rcx
0x1400fef9d  jz      short loc_1400FEFB5
0x1400fef9f  mov     eax, [rcx+10h]
0x1400fefa2  mov     [rsp+148h+arg_18], eax
0x1400fefa9  mov     rax, [rcx+30h]
0x1400fefad  mov     [rsp+148h+var_C8], rax
0x1400fefb5  mov     rax, [rdi+188h]
0x1400fefbc  mov     ecx, [rax]
0x1400fefbe  test    cl, 8
0x1400fefc1  jz      short loc_1400FEFCC
0x1400fefc3  mov     rax, [rdi+0E0h]
0x1400fefca  jmp     short loc_1400FEFD3
0x1400fefcc  mov     rax, [rbx]
0x1400fefcf  mov     rax, [rax+10h]
0x1400fefd3  mov     [rsp+148h+arg_10], rax
0x1400fefdb  jmp     loc_1400FEC0E
0x1400fefe0  mov     rdx, rbx; struct VIDMM_ALLOC *
0x1400fefe3  call    ?UnfaultCommitment@VIDMM_DEVICE@@QEAAXPEAUVIDMM_ALLOC@@@Z; VIDMM_DEVICE::UnfaultCommitment(VIDMM_ALLOC *)
0x1400fefe8  jmp     loc_1400FEDD7
0x1400fefed  mov     r9d, dword ptr [rsp+148h+arg_20]; struct _D3DDDICB_DESTROYALLOCATION2FLAGS
0x1400feff5  mov     rdx, rbx; struct VIDMM_ALLOC *
0x1400feff8  mov     rcx, rsi; this
0x1400feffb  mov     [rsp+148h+Timeout], r12; struct DXGTERMINATIONTRACKER *
0x1400ff000  call    ?TerminateOneAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_ALLOC@@IU_D3DDDICB_DESTROYALLOCATION2FLAGS@@PEAVDXGTERMINATIONTRACKER@@@Z; VIDMM_GLOBAL::TerminateOneAllocation(VIDMM_ALLOC *,uint,_D3DDDICB_DESTROYALLOCATION2FLAGS,DXGTERMINATIONTRACKER *)
0x1400ff005  jmp     loc_1400FEC20
0x1400ff00a  mov     rcx, [rbx+10h]
0x1400ff00e  test    rcx, rcx
0x1400ff011  jz      short loc_1400FF044
0x1400ff013  mov     rbp, [rcx+28h]
0x1400ff017  test    rbp, rbp
0x1400ff01a  jz      short loc_1400FF03A
0x1400ff01c  mov     rbp, [rbp+38h]
0x1400ff020  mov     r15, [rcx+28h]
0x1400ff024  mov     rax, [rsp+148h+var_C0]
0x1400ff02c  mov     r12, [rsi+18h]
0x1400ff030  test    rax, rax
0x1400ff033  jnz     short loc_1400FF04C
0x1400ff035  xor     r14d, r14d
0x1400ff038  jmp     short loc_1400FF050
0x1400ff03a  test    rcx, rcx
0x1400ff03d  jz      short loc_1400FF044
0x1400ff03f  mov     rbp, r12
0x1400ff042  jmp     short loc_1400FF020
0x1400ff044  mov     r15, r12
0x1400ff047  mov     rbp, r12
0x1400ff04a  jmp     short loc_1400FF024
0x1400ff04c  mov     r14, [rax+18h]
0x1400ff050  call    cs:__imp_PsGetCurrentProcessId
0x1400ff057  nop     dword ptr [rax+rax+00h]
0x1400ff05c  mov     r8, [rsp+148h+arg_10]
0x1400ff064  mov     r9, rax
0x1400ff067  mov     ecx, [rsp+148h+arg_18]
0x1400ff06e  mov     edx, [rsp+148h+arg_8]
0x1400ff075  mov     [rsp+148h+var_D8], r13
0x1400ff07a  mov     [rsp+148h+var_E0], r8
0x1400ff07f  mov     r8, [rsp+148h+var_C8]
0x1400ff087  mov     [rsp+148h+var_E8], r8
0x1400ff08c  mov     [rsp+148h+var_F0], rcx
0x1400ff091  mov     [rsp+148h+var_F8], rdx
0x1400ff096  lea     rdx, EventDestroyDeviceAllocation
0x1400ff09d  mov     [rsp+148h+var_100], rbp
0x1400ff0a2  mov     [rsp+148h+var_108], r15
0x1400ff0a7  mov     [rsp+148h+var_110], rdi
0x1400ff0ac  mov     [rsp+148h+var_118], rbx
0x1400ff0b1  mov     [rsp+148h+var_120], r12
0x1400ff0b6  mov     [rsp+148h+Timeout], r14
  ... truncated ...
```
