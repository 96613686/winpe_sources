# VIDMM_GLOBAL::CloseOneAllocation(VIDMM_ALLOC *,VIDMM_LOCAL_ALLOC * *,bool,_D3DDDICB_DESTROYALLOCATION2FLAGS,_KEVENT * *)

- ea: `0x1400e84b4`
- end: `0x1400e8a2e`
- name: `?CloseOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_ALLOC@@PEAPEAUVIDMM_LOCAL_ALLOC@@_NU_D3DDDICB_DESTROYALLOCATION2FLAGS@@PEAPEAU_KEVENT@@@Z`
- size: `1402`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_ALLOC *@<rdx>, struct VIDMM_LOCAL_ALLOC **@<r8>, bool@<r9b>, struct _D3DDDICB_DESTROYALLOCATION2FLAGS, struct _KEVENT **)`
- caller_count: `11`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400997d4`
- `0x14009c1ac`
- `0x1400bc240`
- `0x1400bd81c`
- `0x1400bdbf8`
- `0x1400e8358`
- `0x140101e68`
- `0x1401020cc`
- `0x140102390`
- `0x140103bfc`
- `0x140104c48`

## callees

- `0x14002ea7c`
- `0x14002ed1c`
- `0x14002fbac`
- `0x14002fd94`
- `0x140030ae0`
- `0x1400348c4`
- `0x140058760`
- `0x140058ac0`
- `0x14009d45c`
- `0x1400dfbe8`
- `0x1400e3458`
- `0x1400e84b4`
- `0x1400e8a34`
- `0x1400e8b30`
- `0x1400e9900`
- `0x140116580`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400e8974`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400e8974`
- `ntoskrnl!KeReadStateEvent` at `0x1400e8812`
- `ntoskrnl!KeReadStateEvent` at `0x1400e8812`
- `ntoskrnl!KeSetEvent` at `0x1400e8746`
- `ntoskrnl!KeSetEvent` at `0x1400e8746`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e855e`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e855e`
- `watchdog!WdLogSingleEntry2` at `0x1400e8836`
- `watchdog!WdLogSingleEntry2` at `0x1400e8836`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e879b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e885e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e879b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e885e`
- `watchdog!WdLogSingleEntry5` at `0x1400e8a18`
- `watchdog!WdLogSingleEntry5` at `0x1400e8a18`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400e89f3`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e8504`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e8589`

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
  __int64 v34; // [rsp+80h] [rbp-C8h]
  __int64 *v35; // [rsp+88h] [rbp-C0h]
  _BYTE v36[32]; // [rsp+90h] [rbp-B8h] BYREF
  _QWORD v37[19]; // [rsp+B0h] [rbp-98h] BYREF
  int v38; // [rsp+158h] [rbp+10h]
  char v39; // [rsp+160h] [rbp+18h]
  int v40; // [rsp+168h] [rbp+20h]

  LOBYTE(v38) = 0;
  v40 = 0;
  LODWORD(v34) = 0;
  v9 = **a2;
  v35 = a2[1];
  v39 = 0;
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(this, a2) + 24) = a2;
    WdLogGlobalForLineNumber = 5838;
  }
  if ( a3 )
    *a3 = (struct VIDMM_LOCAL_ALLOC *)*a2;
  if ( (byte_140086201 & 0x10) != 0 )
  {
    v24 = a2[2];
    if ( v24 )
    {
      v38 = *((_DWORD *)v24 + 4);
      v25 = v24[5];
      if ( v25 )
      {
        v40 = *(_DWORD *)(v25 + 16);
        v34 = *(_QWORD *)(v25 + 48);
      }
    }
    if ( (**(_DWORD **)(v9 + 384) & 8) != 0 )
      v26 = *(_QWORD *)(v9 + 224);
    else
      v26 = (*a2)[2];
    v39 = v26;
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
    WdLogGlobalForLineNumber = 5983;
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
      WdLogGlobalForLineNumber = 6039;
    }
    if ( a2[85] )
    {
      if ( (**(_DWORD **)(v9 + 384) & 0x10000008) != 0 && (*(_DWORD *)(*((_QWORD *)this + 3) + 444LL) & 0x10) == 0 )
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
        (DXGAUTOPUSHLOCKEXCLUSIVE *)v36,
        (struct CVirtualAddressAllocator *)((char *)VirtualAddressAllocator + 64),
        *((_QWORD *)VirtualAddressAllocator + 9) != (_QWORD)KeGetCurrentThread());
      if ( a2[81] != (__int64 *)(a2 + 81) || (v15 = 0, a2[83] != (__int64 *)(a2 + 83)) )
        v15 = 1;
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v36);
      if ( v15 )
      {
        memset(v37, 0, 0x58u);
        v37[0] = -4294967175LL;
        v37[2] = a2;
        VIDMM_GLOBAL::QueueSystemCleanupCommandAndWait(this, (struct VIDMM_SYSTEM_COMMAND *)v37, v23);
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
    if ( (byte_140086201 & 0x10) != 0 )
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
      if ( v35 )
        v32 = v35[3];
      else
        LOBYTE(v32) = 0;
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      McTemplateK0ppppppppppppq_EtwWriteTransfer(
        v40,
        (unsigned int)EventDestroyDeviceAllocation,
        v34,
        CurrentProcessId,
        v32,
        v31,
        (char)a2,
        v9,
        v30,
        v29,
        v38,
        v40,
        v34,
        v39,
        v18);
    }
    v19 = *(_QWORD *)(*(_QWORD *)v9 + 16LL);
    _InterlockedIncrement((volatile signed __int32 *)this + 952);
    _InterlockedAdd64((volatile signed __int64 *)this + 477, v19);
    VIDMM_DEVICE::NotifyAllocationClosed((VIDMM_DEVICE *)a2[1], (struct VIDMM_ALLOC *)a2);
    if ( *((_DWORD *)a2 + 174) )
    {
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 270, 56);
      WdLogGlobalForLineNumber = 222;
      JUMPOUT(0x1400E8A2ELL);
    }
    operator delete(a2);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400e84b4  mov     [rsp+arg_0], rbx
0x1400e84b9  push    rbp
0x1400e84ba  push    rsi
0x1400e84bb  push    rdi
0x1400e84bc  push    r12
0x1400e84be  push    r13
0x1400e84c0  push    r14
0x1400e84c2  push    r15
0x1400e84c4  sub     rsp, 110h
0x1400e84cb  mov     rax, [rdx]
0x1400e84ce  xor     r12d, r12d
0x1400e84d1  mov     bpl, r9b
0x1400e84d4  mov     [rsp+148h+arg_8], r12d
0x1400e84dc  mov     r14, r8
0x1400e84df  mov     [rsp+148h+arg_18], r12d
0x1400e84e7  mov     rbx, rdx
0x1400e84ea  mov     [rsp+148h+var_C8], r12
0x1400e84f2  mov     rdi, [rax]
0x1400e84f5  mov     rsi, rcx
0x1400e84f8  mov     rax, [rdx+8]
0x1400e84fc  mov     [rsp+148h+var_C0], rax
0x1400e8504  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400e850b  mov     [rsp+148h+arg_10], r12
0x1400e8513  cmp     [rax], r12b
0x1400e8516  jnz     loc_1400E879B
0x1400e851c  test    r14, r14
0x1400e851f  jnz     loc_1400E889C
0x1400e8525  test    cs:byte_140086201, 10h
0x1400e852c  jnz     loc_1400E88A7
0x1400e8532  mov     ecx, [rbx+20h]; this
0x1400e8535  mov     r15d, 4
0x1400e853b  test    cl, 1
0x1400e853e  jz      loc_1400E86D9
0x1400e8544  test    bpl, bpl
0x1400e8547  jnz     loc_1400E8800
0x1400e854d  lea     rcx, [rbx+48h]; Object
0x1400e8551  mov     [rsp+148h+Timeout], r12; Timeout
0x1400e8556  xor     r9d, r9d; Alertable
0x1400e8559  xor     r8d, r8d; WaitMode
0x1400e855c  xor     edx, edx; WaitReason
0x1400e855e  call    cs:__imp_KeWaitForSingleObject
0x1400e8565  nop     dword ptr [rax+rax+00h]
0x1400e856a  mov     rcx, gs:188h
0x1400e8573  mov     rax, [rsi]
0x1400e8576  cmp     rcx, [rax+8]
0x1400e857a  jz      short loc_1400E8589
0x1400e857c  mov     r8, rdi; struct VIDMM_GLOBAL_ALLOC *
0x1400e857f  xor     edx, edx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400e8581  mov     rcx, rsi; this
0x1400e8584  call    ?WaitForAllPagingEngines@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::WaitForAllPagingEngines(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x1400e8589  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400e8590  cmp     [rax], r12b
0x1400e8593  jnz     loc_1400E885E
0x1400e8599  mov     r8, [rbx+2A8h]
0x1400e85a0  test    r8, r8
0x1400e85a3  jnz     loc_1400E8757
0x1400e85a9  mov     rax, [rdi]
0x1400e85ac  mov     rdx, [rsi+18h]
0x1400e85b0  mov     rcx, [rbx]
0x1400e85b3  mov     r8d, [rax+3Ch]
0x1400e85b7  mov     edx, [rdx+0F0h]; unsigned int
0x1400e85bd  mov     rcx, [rcx+8]; this
0x1400e85c1  shr     r8d, 2
0x1400e85c5  and     r8d, 3Fh; unsigned int
0x1400e85c9  call    ?GetVirtualAddressAllocator@VIDMM_PROCESS@@QEAAPEAVCVirtualAddressAllocator@@KI@Z; VIDMM_PROCESS::GetVirtualAddressAllocator(ulong,uint)
0x1400e85ce  test    rax, rax
0x1400e85d1  jz      short loc_1400E8621
0x1400e85d3  lea     rdx, [rax+40h]; struct DXGPUSHLOCK *
0x1400e85d7  mov     rcx, [rdx+8]
0x1400e85db  mov     rax, gs:188h
0x1400e85e4  cmp     rcx, rax
0x1400e85e7  lea     rcx, [rsp+148h+var_B8]; this
0x1400e85ef  setnz   r8b; unsigned __int8
0x1400e85f3  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@E@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const,uchar)
0x1400e85f8  lea     rax, [rbx+288h]
0x1400e85ff  cmp     [rax], rax
0x1400e8602  jz      loc_1400E8884
0x1400e8608  mov     bpl, 1
0x1400e860b  lea     rcx, [rsp+148h+var_B8]; this
0x1400e8613  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1400e8618  test    bpl, bpl
0x1400e861b  jnz     loc_1400E87BA
0x1400e8621  lea     rbp, [rdi+88h]
0x1400e8628  mov     rcx, rbp; this
0x1400e862b  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x1400e8630  lea     rax, [rbx+28h]
0x1400e8634  mov     r8, [rax]
0x1400e8637  cmp     [r8+8], rax
0x1400e863b  jnz     loc_1400E887D
0x1400e8641  mov     rdx, [rax+8]
0x1400e8645  cmp     [rdx], rax
0x1400e8648  jnz     loc_1400E887D
0x1400e864e  mov     [rdx], r8
0x1400e8651  test    r14, r14
0x1400e8654  mov     [r8+8], rdx
0x1400e8658  mov     rcx, rsi; this
0x1400e865b  mov     rdx, [rbx]; struct VIDMM_LOCAL_ALLOC *
0x1400e865e  setz    r8b; bool
0x1400e8662  mov     r13, [rdi+0F0h]
0x1400e8669  call    ?CloseLocalAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_LOCAL_ALLOC@@_N@Z; VIDMM_GLOBAL::CloseLocalAllocation(VIDMM_LOCAL_ALLOC *,bool)
0x1400e866e  mov     rcx, rbp; this
0x1400e8671  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400e8676  test    cs:byte_140086201, 10h
0x1400e867d  jnz     loc_1400E892E
0x1400e8683  mov     rax, [rdi]
0x1400e8686  mov     rcx, [rax+10h]
0x1400e868a  lock inc dword ptr [rsi+0EE0h]
0x1400e8691  lock add [rsi+0EE8h], rcx
0x1400e8699  mov     rcx, [rbx+8]; this
0x1400e869d  mov     rdx, rbx; struct VIDMM_ALLOC *
0x1400e86a0  call    ?NotifyAllocationClosed@VIDMM_DEVICE@@QEAAXPEAUVIDMM_ALLOC@@@Z; VIDMM_DEVICE::NotifyAllocationClosed(VIDMM_ALLOC *)
0x1400e86a5  mov     eax, [rbx+2B8h]
0x1400e86ab  test    eax, eax
0x1400e86ad  jnz     loc_1400E89EC
0x1400e86b3  mov     rcx, rbx; void *
0x1400e86b6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400e86bb  xor     eax, eax
0x1400e86bd  mov     rbx, [rsp+148h+arg_0]
0x1400e86c5  add     rsp, 110h
0x1400e86cc  pop     r15
0x1400e86ce  pop     r14
0x1400e86d0  pop     r13
0x1400e86d2  pop     r12
0x1400e86d4  pop     rdi
0x1400e86d5  pop     rsi
0x1400e86d6  pop     rbp
0x1400e86d7  retn
0x1400e86d9  mov     rax, [rbx+8]
0x1400e86dd  test    rax, rax
0x1400e86e0  jnz     short loc_1400E8721
0x1400e86e2  mov     eax, [rdi+20h]
0x1400e86e5  test    r15b, al
0x1400e86e8  jnz     short loc_1400E8727
0x1400e86ea  or      [rbx+1Ch], r15d
0x1400e86ee  mov     eax, [rbx+1Ch]
0x1400e86f1  and     al, 3
0x1400e86f3  cmp     al, 1
0x1400e86f5  jz      loc_1400E8904
0x1400e86fb  mov     eax, [rdi+18h]
0x1400e86fe  test    r15b, al
0x1400e8701  jz      short loc_1400E873D
0x1400e8703  mov     rax, [rsi]
0x1400e8706  mov     rcx, [rax+10h]
0x1400e870a  test    rcx, rcx
0x1400e870d  jz      short loc_1400E873D
0x1400e870f  cmp     [rcx+0F8h], rbx
0x1400e8716  jnz     short loc_1400E873D
0x1400e8718  mov     [rcx+0F8h], r12
0x1400e871f  jmp     short loc_1400E873D
0x1400e8721  cmp     [rax+18h], r12
0x1400e8725  jz      short loc_1400E86E2
0x1400e8727  mov     eax, [rdi+20h]
0x1400e872a  test    r15b, al
0x1400e872d  jz      loc_1400E8911
0x1400e8733  or      ecx, 1
0x1400e8736  or      [rbx+1Ch], r15d
0x1400e873a  mov     [rbx+20h], ecx
0x1400e873d  lea     rcx, [rbx+48h]; Event
0x1400e8741  xor     r8d, r8d; Wait
0x1400e8744  xor     edx, edx; Increment
0x1400e8746  call    cs:__imp_KeSetEvent
0x1400e874d  nop     dword ptr [rax+rax+00h]
0x1400e8752  jmp     loc_1400E8544
0x1400e8757  mov     rax, [rdi+180h]
0x1400e875e  test    dword ptr [rax], 10000008h
0x1400e8764  jz      short loc_1400E878F
0x1400e8766  mov     rax, [rsi+18h]
0x1400e876a  mov     ecx, [rax+1BCh]
0x1400e8770  test    cl, 10h
0x1400e8773  jnz     short loc_1400E878F
0x1400e8775  mov     rcx, [rdi+0E8h]
0x1400e877c  mov     rdx, [rdi+0F0h]
0x1400e8783  mov     rax, [rcx]
0x1400e8786  mov     rax, [rax+40h]
0x1400e878a  call    _guard_dispatch_icall
0x1400e878f  mov     [rbx+2A8h], r12
0x1400e8796  jmp     loc_1400E85A9
0x1400e879b  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400e87a2  nop     dword ptr [rax+rax+00h]
0x1400e87a7  mov     [rax+18h], rbx
0x1400e87ab  mov     cs:WdLogGlobalForLineNumber, 16CEh
0x1400e87b5  jmp     loc_1400E851C
0x1400e87ba  xor     edx, edx; Val
0x1400e87bc  lea     rcx, [rsp+148h+var_98]; void *
0x1400e87c4  lea     r8d, [rdx+58h]; Size
0x1400e87c8  call    memset
0x1400e87cd  lea     rdx, [rsp+148h+var_98]; struct VIDMM_SYSTEM_COMMAND *
0x1400e87d5  mov     [rsp+148h+var_98], 79h ; 'y'
0x1400e87e0  mov     rcx, rsi; this
0x1400e87e3  mov     [rsp+148h+var_88], rbx
0x1400e87eb  mov     [rsp+148h+var_94], 0FFFFFFFFh
0x1400e87f6  call    ?QueueSystemCleanupCommandAndWait@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_SYSTEM_COMMAND@@_N@Z; VIDMM_GLOBAL::QueueSystemCleanupCommandAndWait(VIDMM_SYSTEM_COMMAND *,bool)
0x1400e87fb  jmp     loc_1400E8621
0x1400e8800  mov     eax, [rbx+20h]
0x1400e8803  test    al, 1
0x1400e8805  jz      loc_1400E854D
0x1400e880b  lea     rbp, [rbx+48h]
0x1400e880f  mov     rcx, rbp; Event
0x1400e8812  call    cs:__imp_KeReadStateEvent
0x1400e8819  nop     dword ptr [rax+rax+00h]
0x1400e881e  test    eax, eax
0x1400e8820  jnz     loc_1400E854D
0x1400e8826  mov     rdi, 0FFFFFFFFC01E0102h
0x1400e882d  mov     rdx, rbx
0x1400e8830  mov     r8, rdi
0x1400e8833  mov     ecx, r15d
0x1400e8836  call    cs:__imp_WdLogSingleEntry2
0x1400e883d  nop     dword ptr [rax+rax+00h]
0x1400e8842  mov     rcx, [rsp+148h+arg_28]
0x1400e884a  mov     eax, edi
0x1400e884c  mov     cs:WdLogGlobalForLineNumber, 175Fh
0x1400e8856  mov     [rcx], rbp
0x1400e8859  jmp     loc_1400E86BD
0x1400e885e  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400e8865  nop     dword ptr [rax+rax+00h]
0x1400e886a  mov     [rax+18h], rbx
0x1400e886e  mov     cs:WdLogGlobalForLineNumber, 1797h
0x1400e8878  jmp     loc_1400E8599
0x1400e887d  mov     ecx, 3
0x1400e8882  int     29h; Win8: RtlFailFast(ecx)
0x1400e8884  lea     rax, [rbx+298h]
0x1400e888b  mov     bpl, r12b
0x1400e888e  cmp     [rax], rax
0x1400e8891  jnz     loc_1400E8608
0x1400e8897  jmp     loc_1400E860B
0x1400e889c  mov     rax, [rbx]
0x1400e889f  mov     [r14], rax
0x1400e88a2  jmp     loc_1400E8525
0x1400e88a7  mov     rax, [rbx+10h]
0x1400e88ab  test    rax, rax
0x1400e88ae  jz      short loc_1400E88D9
0x1400e88b0  mov     ecx, [rax+10h]
0x1400e88b3  mov     [rsp+148h+arg_8], ecx
0x1400e88ba  mov     rcx, [rax+28h]
0x1400e88be  test    rcx, rcx
0x1400e88c1  jz      short loc_1400E88D9
0x1400e88c3  mov     eax, [rcx+10h]
0x1400e88c6  mov     [rsp+148h+arg_18], eax
0x1400e88cd  mov     rax, [rcx+30h]
0x1400e88d1  mov     [rsp+148h+var_C8], rax
0x1400e88d9  mov     rax, [rdi+180h]
0x1400e88e0  mov     ecx, [rax]
0x1400e88e2  test    cl, 8
0x1400e88e5  jz      short loc_1400E88F0
0x1400e88e7  mov     rax, [rdi+0E0h]
0x1400e88ee  jmp     short loc_1400E88F7
0x1400e88f0  mov     rax, [rbx]
0x1400e88f3  mov     rax, [rax+10h]
0x1400e88f7  mov     [rsp+148h+arg_10], rax
0x1400e88ff  jmp     loc_1400E8532
0x1400e8904  mov     rdx, rbx; struct VIDMM_ALLOC *
0x1400e8907  call    ?UnfaultCommitment@VIDMM_DEVICE@@QEAAXPEAUVIDMM_ALLOC@@@Z; VIDMM_DEVICE::UnfaultCommitment(VIDMM_ALLOC *)
0x1400e890c  jmp     loc_1400E86FB
0x1400e8911  mov     r9d, dword ptr [rsp+148h+arg_20]; struct _D3DDDICB_DESTROYALLOCATION2FLAGS
0x1400e8919  mov     rdx, rbx; struct VIDMM_ALLOC *
0x1400e891c  mov     rcx, rsi; this
0x1400e891f  mov     [rsp+148h+Timeout], r12; struct DXGTERMINATIONTRACKER *
0x1400e8924  call    ?TerminateOneAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_ALLOC@@IU_D3DDDICB_DESTROYALLOCATION2FLAGS@@PEAVDXGTERMINATIONTRACKER@@@Z; VIDMM_GLOBAL::TerminateOneAllocation(VIDMM_ALLOC *,uint,_D3DDDICB_DESTROYALLOCATION2FLAGS,DXGTERMINATIONTRACKER *)
0x1400e8929  jmp     loc_1400E8544
0x1400e892e  mov     rcx, [rbx+10h]
0x1400e8932  test    rcx, rcx
0x1400e8935  jz      short loc_1400E8968
0x1400e8937  mov     rbp, [rcx+28h]
0x1400e893b  test    rbp, rbp
0x1400e893e  jz      short loc_1400E895E
0x1400e8940  mov     rbp, [rbp+38h]
0x1400e8944  mov     r15, [rcx+28h]
0x1400e8948  mov     rax, [rsp+148h+var_C0]
0x1400e8950  mov     r12, [rsi+18h]
0x1400e8954  test    rax, rax
0x1400e8957  jnz     short loc_1400E8970
0x1400e8959  xor     r14d, r14d
0x1400e895c  jmp     short loc_1400E8974
0x1400e895e  test    rcx, rcx
0x1400e8961  jz      short loc_1400E8968
0x1400e8963  mov     rbp, r12
0x1400e8966  jmp     short loc_1400E8944
0x1400e8968  mov     r15, r12
0x1400e896b  mov     rbp, r12
0x1400e896e  jmp     short loc_1400E8948
0x1400e8970  mov     r14, [rax+18h]
0x1400e8974  call    cs:__imp_PsGetCurrentProcessId
0x1400e897b  nop     dword ptr [rax+rax+00h]
0x1400e8980  mov     r8, [rsp+148h+arg_10]
0x1400e8988  mov     r9, rax
0x1400e898b  mov     ecx, [rsp+148h+arg_18]
0x1400e8992  mov     edx, [rsp+148h+arg_8]
0x1400e8999  mov     [rsp+148h+var_D8], r13
0x1400e899e  mov     [rsp+148h+var_E0], r8
0x1400e89a3  mov     r8, [rsp+148h+var_C8]
0x1400e89ab  mov     [rsp+148h+var_E8], r8
0x1400e89b0  mov     [rsp+148h+var_F0], rcx
0x1400e89b5  mov     [rsp+148h+var_F8], rdx
0x1400e89ba  lea     rdx, EventDestroyDeviceAllocation
0x1400e89c1  mov     [rsp+148h+var_100], rbp
0x1400e89c6  mov     [rsp+148h+var_108], r15
0x1400e89cb  mov     [rsp+148h+var_110], rdi
0x1400e89d0  mov     [rsp+148h+var_118], rbx
0x1400e89d5  mov     [rsp+148h+var_120], r12
0x1400e89da  mov     [rsp+148h+Timeout], r14
  ... truncated ...
```
