# NtfsAddNtfsMcbEntry

- ea: `0x140031410`
- end: `0x140031a47`
- name: `NtfsAddNtfsMcbEntry`
- size: `1591`
- prototype: `BOOLEAN __fastcall(__int64, __int64, LONGLONG, unsigned __int64, char, unsigned __int8)`
- caller_count: `12`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003380c`
- `0x1400c2798`
- `0x1400cc78c`
- `0x1400cf580`
- `0x1400da814`
- `0x14015d274`
- `0x1401611e0`
- `0x1401700a0`
- `0x1401dd5b0`
- `0x1401f2d00`
- `0x1401f63f8`
- `0x14027e3c8`

## callees

- `0x1400054e8`
- `0x140007ea0`
- `0x140023bd4`
- `0x140031410`
- `0x14003c34c`
- `0x14003fb90`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x1400317ee`
- `ntoskrnl!ExQueueWorkItem` at `0x1400317ee`
- `ntoskrnl!FsRtlNumberOfRunsInBaseMcb` at `0x14003190b`
- `ntoskrnl!FsRtlNumberOfRunsInBaseMcb` at `0x14003190b`
- `ntoskrnl!KeTryToAcquireGuardedMutex` at `0x140031590`
- `ntoskrnl!KeTryToAcquireGuardedMutex` at `0x140031590`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003187c`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003187c`
- `ntoskrnl!IoGetActivityIdThread` at `0x14003178d`
- `ntoskrnl!IoGetActivityIdThread` at `0x14003178d`
- `ntoskrnl!FsRtlAddBaseMcbEntryEx` at `0x1400316ad`
- `ntoskrnl!FsRtlAddBaseMcbEntryEx` at `0x1400316ad`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005b666`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140060336`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005b666`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140060336`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x14003155b`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x14003155b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14003181c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14003181c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14003162e`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14003162e`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400319a4`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14005b634`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400319a4`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14005b634`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x140031478`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x140031478`
- `ntoskrnl!ExRaiseStatus` at `0x1400319d3`
- `ntoskrnl!ExRaiseStatus` at `0x1400319d3`

## pseudocode

```c
BOOLEAN __fastcall NtfsAddNtfsMcbEntry(
        __int64 a1,
        __int64 a2,
        LONGLONG a3,
        unsigned __int64 a4,
        char a5,
        unsigned __int8 a6)
{
  unsigned __int64 v6; // rsi
  __int64 v7; // r12
  __int64 v8; // rbx
  unsigned __int8 v9; // di
  PVOID v10; // r15
  BOOLEAN v11; // r14
  __int64 v12; // r13
  unsigned __int64 v13; // r11
  unsigned int v14; // edx
  unsigned int v15; // eax
  unsigned int v16; // r9d
  __int64 v17; // r12
  __int64 v18; // r8
  __int64 v19; // r10
  __int64 v20; // rdi
  __int64 v21; // rax
  signed __int64 v22; // rcx
  __int64 v23; // r8
  unsigned __int64 v24; // rsi
  NTSTATUS v25; // eax
  __int64 *ActivityIdThread; // rax
  __int64 v27; // rcx
  __int64 v28; // r9
  struct _LOOKASIDE_LIST_EX *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rdx
  struct _LOOKASIDE_LIST_EX *v36; // rcx
  __int64 v37; // [rsp+20h] [rbp-B8h]
  unsigned int v38; // [rsp+48h] [rbp-90h]
  unsigned __int64 v39; // [rsp+58h] [rbp-80h]
  __int64 v40; // [rsp+68h] [rbp-70h]
  LONGLONG Lbn; // [rsp+70h] [rbp-68h]
  __int64 v42; // [rsp+80h] [rbp-58h]

  v6 = a4;
  v7 = a2;
  v8 = a1;
  v9 = a6;
  v10 = 0;
  v42 = 0;
  v11 = 0;
  if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 4) != 0 )
    McTemplateU0ppiii_EtwWriteTransfer(a1, a2, *(_QWORD *)a1, a1, a2, a3, a4);
  if ( !a5 )
    ExAcquireAutoExpandPushLockExclusive(v8 + 32, 0);
  v12 = v7;
  Lbn = a3;
  v13 = v6;
  v39 = v6;
  while ( 1 )
  {
    if ( v12 >= (__int64)(v7 + v6) )
      goto LABEL_33;
    v14 = 0;
    a1 = (unsigned int)(*(_DWORD *)(v8 + 12) - 1);
    while ( 1 )
    {
      while ( 1 )
      {
        v15 = ((unsigned int)a1 + v14) >> 1;
        v16 = v15;
        v38 = v15;
        v17 = 32LL * v15;
        v18 = *(_QWORD *)(v8 + 24);
        v19 = *(_QWORD *)(v17 + v18);
        v40 = v19;
        if ( v19 <= v12 || !v15 )
          break;
        a1 = v15 - 1;
      }
      if ( *(_QWORD *)(v17 + v18 + 8) >= v12 || v15 == *(_DWORD *)(v8 + 12) - 1 )
        break;
      v14 = v15 + 1;
    }
    v20 = *(_QWORD *)(v17 + v18 + 16);
    if ( !v20 )
    {
      if ( *(_DWORD *)(v8 + 16) == 1 )
      {
        v20 = v18 + 32;
      }
      else
      {
        v29 = &NtfsPagedMcbEntryLookasideList;
        if ( *(_WORD *)(v8 + 10) != 1 )
          v29 = &NtfsNonPagedMcbEntryLookasideList;
        v10 = ExAllocateFromLookasideListEx(v29);
        v20 = (__int64)v10;
        if ( !v10 )
        {
LABEL_39:
          v9 = a6;
          goto LABEL_70;
        }
      }
      *(_QWORD *)(v20 + 24) = v8;
      *(_QWORD *)(v20 + 32) = v17 + *(_QWORD *)(v8 + 24);
      v11 = FsRtlInitializeBaseMcbEx((PBASE_MCB)(v20 + 40), (POOL_TYPE)*(unsigned __int16 *)(v8 + 10), 0);
      if ( !v11 )
        goto LABEL_39;
      if ( PoolType == PagedPool )
      {
        if ( KeTryToAcquireGuardedMutex(&NtfsMcbMutex) )
        {
          if ( *(_WORD *)(v8 + 10) != 1 || (*(_DWORD *)(*(_QWORD *)v8 + 512LL) & 0x400000) != 0 )
          {
            *(_QWORD *)(v20 + 8) = 0;
          }
          else
          {
            *(_QWORD *)(v20 + 16) = MEMORY[0xFFFFF78000000320];
            v21 = qword_140094F28;
            *(_QWORD *)qword_140094F28 = v20;
            *(_QWORD *)(v20 + 8) = v21;
            *(_QWORD *)v20 = &NtfsMcbLruQueue;
            qword_140094F28 = v20;
            ++NtfsMcbCurrentLevel;
          }
          *(_QWORD *)(v17 + *(_QWORD *)(v8 + 24) + 16) = v20;
          v10 = 0;
          if ( NtfsMcbCurrentLevel > (unsigned int)NtfsMcbHighWaterMark
            && !NtfsMcbCleanupInProgress
            && !NtfsMcbCleanupDelayed )
          {
            NtfsMcbCleanupInProgress = 1;
            NtfsMcbWorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)NtfsMcbCleanupLruQueue;
            NtfsMcbWorkItem.Parameter = &NtfsMcbWorkItem;
            NtfsMcbWorkItem.List.Flink = 0;
            ActivityIdThread = (__int64 *)IoGetActivityIdThread();
            if ( ActivityIdThread )
            {
              v27 = *ActivityIdThread;
              qword_140094F48 = *ActivityIdThread;
              qword_140094F50 = ActivityIdThread[1];
              NtfsMcbWorkItemActivityId = (__int64)&qword_140094F48;
            }
            else
            {
              NtfsMcbWorkItemActivityId = 0;
            }
            if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
            {
              LODWORD(v37) = 6;
              McTemplateK0pq_EtwWriteTransfer(
                v27,
                (const EVENT_DESCRIPTOR *)WORKITEM_QUEUE,
                (const GUID *)NtfsMcbWorkItemActivityId,
                v28,
                v37);
            }
            ExQueueWorkItem(&NtfsMcbWorkItem, CriticalWorkQueue);
          }
          KeReleaseGuardedMutex(&NtfsMcbMutex);
        }
        else
        {
          *(_QWORD *)(v20 + 8) = 0;
          ExpInterlockedPushEntrySList(&NtfsUnchainedMcbQueue, (PSLIST_ENTRY)v20);
          *(_QWORD *)(v17 + *(_QWORD *)(v8 + 24) + 16) = v20;
          v10 = 0;
        }
        v16 = v38;
        v19 = v40;
        v13 = v39;
      }
      else
      {
        *(_QWORD *)(v20 + 8) = 0;
        *(_QWORD *)(v17 + *(_QWORD *)(v8 + 24) + 16) = v20;
        v10 = 0;
        v16 = v38;
        v19 = v40;
        v13 = v39;
      }
    }
    if ( a3 == -1 )
    {
      v9 = a6;
LABEL_33:
      v11 = 1;
      goto LABEL_70;
    }
    v22 = v13 + v12 - 1;
    v23 = *(_QWORD *)(v8 + 24);
    if ( v22 > *(_QWORD *)(v17 + v23 + 8) && v16 + 1 == *(_DWORD *)(v8 + 12) )
    {
      v42 = *(_QWORD *)(v17 + v23 + 8);
      *(_QWORD *)(v17 + v23 + 8) = v22;
    }
    else
    {
      v22 = *(_QWORD *)(v17 + v23 + 8);
    }
    v24 = v22 - v12 + 1;
    if ( v24 > v13 )
      v24 = v13;
    if ( v22 - v19 < 0xFFFFFFFFLL )
      break;
    v30 = *(_QWORD *)(*(_QWORD *)v8 + 496LL);
    v24 = 0;
    if ( v30 )
    {
      v31 = *(_QWORD *)(v17 + *(_QWORD *)(v8 + 24));
      if ( v31 < *(_QWORD *)(v30 + 64) )
        *(_QWORD *)(v30 + 64) = v31;
      v32 = *(_QWORD *)(*(_QWORD *)v8 + 496LL);
      v33 = *(_QWORD *)(v17 + *(_QWORD *)(v8 + 24) + 8);
      if ( v33 > *(_QWORD *)(v32 + 72) )
        *(_QWORD *)(v32 + 72) = v33;
    }
    if ( FsRtlNumberOfRunsInBaseMcb((PBASE_MCB)(v20 + 40)) )
    {
      v34 = v42 + 1;
    }
    else if ( v12 == v40 )
    {
      v34 = v40 + 0xFFFFFFFFLL;
    }
    else
    {
      v34 = v12;
    }
    if ( !NtfsInsertNewRange(v8, v34, v38, 0) )
      goto LABEL_39;
LABEL_31:
    v12 += v24;
    Lbn += v24;
    v13 = v39 - v24;
    v39 -= v24;
    v9 = a6;
    v6 = a4;
    v7 = a2;
  }
  v25 = FsRtlAddBaseMcbEntryEx((PBASE_MCB)(v20 + 40), v12 - v19, Lbn, v24);
  if ( v25 >= 0 )
    goto LABEL_31;
  v9 = 0;
  a1 = a6;
  if ( v25 == -1073741670 )
    v9 = a6;
  v11 = 0;
LABEL_70:
  if ( !a5 )
    ExReleaseAutoExpandPushLockExclusive(v8 + 32, 0);
  if ( v10 )
  {
    v36 = &NtfsPagedMcbEntryLookasideList;
    if ( *(_WORD *)(v8 + 10) != 1 )
      v36 = &NtfsNonPagedMcbEntryLookasideList;
    ExFreeToLookasideListEx(v36, v10);
  }
  if ( !v11 && v9 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC000009A, 0x3C0660u);
    ExRaiseStatus(-1073741670);
  }
  if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 4) != 0 )
    McTemplateU0pd_EtwWriteTransfer(a1, mcbsup_c1635, v8, v11);
  return v11;
}

```

## disassembly

```asm
0x140031410  mov     rax, rsp
0x140031413  mov     [rax+20h], r9
0x140031417  mov     [rax+18h], r8
0x14003141b  mov     [rax+10h], rdx
0x14003141f  mov     [rax+8], rcx
0x140031423  push    rbx
0x140031424  push    rsi
0x140031425  push    rdi
0x140031426  push    r12
0x140031428  push    r13
0x14003142a  push    r14
0x14003142c  push    r15
0x14003142e  sub     rsp, 0A0h
0x140031435  mov     rsi, r9
0x140031438  mov     r12, rdx
0x14003143b  mov     rbx, rcx
0x14003143e  mov     dil, [rax+30h]
0x140031442  mov     [rsp+0D8h+var_94], edi
0x140031446  mov     [rsp+0D8h+var_97], dil
0x14003144b  xor     r15d, r15d
0x14003144e  mov     [rax-78h], r15
0x140031452  mov     [rax-58h], r15
0x140031456  xor     r14b, r14b
0x140031459  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x140031460  test    al, 4
0x140031462  jnz     loc_1400319E0
0x140031468  cmp     [rsp+0D8h+arg_20], r14b
0x140031470  jnz     short loc_140031485
0x140031472  lea     rcx, [rbx+20h]
0x140031476  xor     edx, edx
0x140031478  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x14003147f  nop     dword ptr [rax+rax+00h]
0x140031484  nop
0x140031485  mov     r13, r12
0x140031488  mov     [rsp+0D8h+var_50], r12
0x140031490  mov     rax, [rsp+0D8h+arg_10]
0x140031498  mov     [rsp+0D8h+Lbn], rax
0x14003149d  mov     r11, rsi
0x1400314a0  mov     [rsp+0D8h+var_80], rsi
0x1400314a5  mov     r8d, 1
0x1400314ab  lea     rax, [r12+rsi]
0x1400314af  cmp     r13, rax
0x1400314b2  jge     loc_1400316F7
0x1400314b8  xor     esi, esi
0x1400314ba  mov     [rsp+0D8h+var_84], esi
0x1400314be  mov     [rsp+0D8h+var_88], esi
0x1400314c2  mov     edx, esi
0x1400314c4  mov     [rsp+0D8h+var_84], edx
0x1400314c8  mov     ecx, [rbx+0Ch]
0x1400314cb  sub     ecx, r8d
0x1400314ce  mov     [rsp+0D8h+var_88], ecx
0x1400314d2  lea     eax, [rcx+rdx]
0x1400314d5  shr     eax, 1
0x1400314d7  mov     r9d, eax
0x1400314da  mov     [rsp+0D8h+var_90], r9
0x1400314df  mov     r12d, eax
0x1400314e2  shl     r12, 5
0x1400314e6  mov     r8, [rbx+18h]
0x1400314ea  mov     r10, [r12+r8]
0x1400314ee  mov     [rsp+0D8h+var_70], r10
0x1400314f3  cmp     r10, r13
0x1400314f6  jg      loc_140031750
0x1400314fc  mov     edx, 1
0x140031501  cmp     [r12+r8+8], r13
0x140031506  jge     short loc_14003151C
0x140031508  mov     eax, [rbx+0Ch]
0x14003150b  sub     eax, edx
0x14003150d  cmp     r9d, eax
0x140031510  jz      short loc_14003151C
0x140031512  lea     edx, [r9+1]
0x140031516  mov     [rsp+0D8h+var_84], edx
0x14003151a  jmp     short loc_1400314D2
0x14003151c  mov     rdi, [r12+r8+10h]
0x140031521  mov     [rsp+0D8h+var_60], rdi
0x140031526  test    rdi, rdi
0x140031529  jnz     loc_140031649
0x14003152f  cmp     [rbx+10h], edx
0x140031532  jnz     loc_140031808
0x140031538  lea     rdi, [r8+20h]
0x14003153c  mov     [rsp+0D8h+var_60], rdi
0x140031541  mov     [rdi+18h], rbx
0x140031545  mov     rcx, [rbx+18h]
0x140031549  add     rcx, r12
0x14003154c  mov     [rdi+20h], rcx
0x140031550  xor     r8d, r8d; Flags
0x140031553  movzx   edx, word ptr [rbx+0Ah]; PoolType
0x140031557  lea     rcx, [rdi+28h]; Mcb
0x14003155b  call    cs:__imp_FsRtlInitializeBaseMcbEx
0x140031562  nop     dword ptr [rax+rax+00h]
0x140031567  mov     r14b, al
0x14003156a  mov     [rsp+0D8h+var_98], al
0x14003156e  test    al, al
0x140031570  jz      loc_140031747
0x140031576  mov     r8d, 1
0x14003157c  cmp     cs:PoolType, r8d
0x140031583  jnz     loc_14003189E
0x140031589  lea     rcx, NtfsMcbMutex; Mutex
0x140031590  call    cs:__imp_KeTryToAcquireGuardedMutex
0x140031597  nop     dword ptr [rax+rax+00h]
0x14003159c  test    al, al
0x14003159e  jz      loc_14003186E
0x1400315a4  mov     edx, 1
0x1400315a9  cmp     [rbx+0Ah], dx
0x1400315ad  jnz     loc_140031846
0x1400315b3  mov     rax, [rbx]
0x1400315b6  test    dword ptr [rax+200h], 400000h
0x1400315c0  jnz     loc_140031846
0x1400315c6  mov     rax, 0FFFFF78000000320h
0x1400315d0  mov     rax, [rax]
0x1400315d3  mov     [rdi+10h], rax
0x1400315d7  mov     rax, cs:qword_140094F28
0x1400315de  mov     [rax], rdi
0x1400315e1  mov     [rdi+8], rax
0x1400315e5  lea     rax, NtfsMcbLruQueue
0x1400315ec  mov     [rdi], rax
0x1400315ef  mov     cs:qword_140094F28, rdi
0x1400315f6  mov     eax, cs:NtfsMcbCurrentLevel
0x1400315fc  add     eax, edx
0x1400315fe  mov     cs:NtfsMcbCurrentLevel, eax
0x140031604  mov     rax, [rbx+18h]
0x140031608  mov     [r12+rax+10h], rdi
0x14003160d  mov     r15, rsi
0x140031610  mov     [rsp+0D8h+var_78], rsi
0x140031615  mov     ecx, cs:NtfsMcbCurrentLevel
0x14003161b  cmp     ecx, cs:NtfsMcbHighWaterMark
0x140031621  ja      loc_14003184F
0x140031627  lea     rcx, NtfsMcbMutex; Mutex
0x14003162e  call    cs:__imp_KeReleaseGuardedMutex
0x140031635  nop     dword ptr [rax+rax+00h]
0x14003163a  mov     r9, [rsp+0D8h+var_90]
0x14003163f  mov     r10, [rsp+0D8h+var_70]
0x140031644  mov     r11, [rsp+0D8h+var_80]
0x140031649  mov     r8d, 1
0x14003164f  cmp     [rsp+0D8h+arg_10], 0FFFFFFFFFFFFFFFFh
0x140031658  jz      loc_1400316F3
0x14003165e  lea     rcx, [r13-1]
0x140031662  add     rcx, r11
0x140031665  mov     r8, [rbx+18h]
0x140031669  mov     rdx, [r12+r8+8]
0x14003166e  cmp     rcx, rdx
0x140031671  jg      loc_140031720
0x140031677  mov     rcx, rdx
0x14003167a  mov     rsi, rcx
0x14003167d  sub     rsi, r13
0x140031680  inc     rsi
0x140031683  cmp     rsi, r11
0x140031686  cmova   rsi, r11
0x14003168a  sub     rcx, r10
0x14003168d  mov     eax, 0FFFFFFFFh
0x140031692  cmp     rcx, rax
0x140031695  jge     loc_1400318C7
0x14003169b  mov     rdx, r13
0x14003169e  sub     rdx, r10; Vbn
0x1400316a1  lea     rcx, [rdi+28h]; Mcb
0x1400316a5  mov     r9, rsi; SectorCount
0x1400316a8  mov     r8, [rsp+0D8h+Lbn]; Lbn
0x1400316ad  call    cs:__imp_FsRtlAddBaseMcbEntryEx
0x1400316b4  nop     dword ptr [rax+rax+00h]
0x1400316b9  test    eax, eax
0x1400316bb  js      short loc_140031704
0x1400316bd  add     r13, rsi
0x1400316c0  mov     [rsp+0D8h+var_50], r13
0x1400316c8  add     [rsp+0D8h+Lbn], rsi
0x1400316cd  mov     r11, [rsp+0D8h+var_80]
0x1400316d2  sub     r11, rsi
0x1400316d5  mov     [rsp+0D8h+var_80], r11
0x1400316da  mov     edi, [rsp+0D8h+var_94]
0x1400316de  mov     rsi, [rsp+0D8h+arg_18]
0x1400316e6  mov     r12, [rsp+0D8h+arg_8]
0x1400316ee  jmp     loc_1400314A5
0x1400316f3  mov     edi, [rsp+0D8h+var_94]
0x1400316f7  mov     [rsp+0D8h+var_98], r8b
0x1400316fc  mov     r14b, r8b
0x1400316ff  jmp     loc_14003195C
0x140031704  xor     edi, edi
0x140031706  movzx   ecx, [rsp+0D8h+var_97]
0x14003170b  cmp     eax, 0C000009Ah
0x140031710  cmovz   edi, ecx
0x140031713  xor     r14b, r14b
0x140031716  mov     [rsp+0D8h+var_98], r14b
0x14003171b  jmp     loc_14003195C
0x140031720  lea     eax, [r9+1]
0x140031724  cmp     eax, [rbx+0Ch]
0x140031727  jnz     loc_140031677
0x14003172d  mov     [rsp+0D8h+var_58], rdx
0x140031735  mov     [rsp+0D8h+var_48], rdx
0x14003173d  mov     [r12+r8+8], rcx
0x140031742  jmp     loc_14003167A
0x140031747  mov     edi, [rsp+0D8h+var_94]
0x14003174b  jmp     loc_14003195C
0x140031750  test    eax, eax
0x140031752  jz      loc_1400314FC
0x140031758  lea     ecx, [rax-1]
0x14003175b  mov     [rsp+0D8h+var_88], ecx
0x14003175f  jmp     loc_14003151A
0x140031764  mov     cs:NtfsMcbCleanupInProgress, dl
0x14003176a  lea     rax, NtfsMcbCleanupLruQueue
0x140031771  mov     cs:NtfsMcbWorkItem.WorkerRoutine, rax
0x140031778  lea     rax, NtfsMcbWorkItem
0x14003177f  mov     cs:NtfsMcbWorkItem.Parameter, rax
0x140031786  mov     cs:NtfsMcbWorkItem.List.Flink, rsi
0x14003178d  call    cs:__imp_IoGetActivityIdThread
0x140031794  nop     dword ptr [rax+rax+00h]
0x140031799  test    rax, rax
0x14003179c  jz      short loc_1400317FF
0x14003179e  mov     rcx, [rax]
0x1400317a1  mov     cs:qword_140094F48, rcx
0x1400317a8  mov     rax, [rax+8]
0x1400317ac  mov     cs:qword_140094F50, rax
0x1400317b3  lea     rax, qword_140094F48
0x1400317ba  mov     cs:NtfsMcbWorkItemActivityId, rax
0x1400317c1  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x1400317c8  jz      short loc_1400317E5
0x1400317ca  mov     r8, cs:NtfsMcbWorkItemActivityId
0x1400317d1  mov     dword ptr [rsp+0D8h+var_B8], 6
0x1400317d9  lea     rdx, WORKITEM_QUEUE
0x1400317e0  call    McTemplateK0pq_EtwWriteTransfer
0x1400317e5  xor     edx, edx; QueueType
0x1400317e7  lea     rcx, NtfsMcbWorkItem; WorkItem
0x1400317ee  call    cs:__imp_ExQueueWorkItem
0x1400317f5  nop     dword ptr [rax+rax+00h]
0x1400317fa  jmp     loc_140031627
0x1400317ff  mov     cs:NtfsMcbWorkItemActivityId, rsi
0x140031806  jmp     short loc_1400317C1
0x140031808  cmp     [rbx+0Ah], dx
0x14003180c  lea     rcx, NtfsPagedMcbEntryLookasideList
0x140031813  jz      short loc_14003181C
0x140031815  lea     rcx, NtfsNonPagedMcbEntryLookasideList; Lookaside
0x14003181c  call    cs:__imp_ExAllocateFromLookasideListEx
0x140031823  nop     dword ptr [rax+rax+00h]
0x140031828  mov     r15, rax
0x14003182b  mov     rdi, rax
0x14003182e  mov     [rsp+0D8h+var_60], rax
0x140031833  mov     [rsp+0D8h+var_78], rax
0x140031838  test    rax, rax
0x14003183b  jz      loc_140031747
0x140031841  jmp     loc_140031541
0x140031846  mov     [rdi+8], rsi
0x14003184a  jmp     loc_140031604
0x14003184f  cmp     cs:NtfsMcbCleanupInProgress, sil
0x140031856  jnz     loc_140031627
0x14003185c  cmp     cs:NtfsMcbCleanupDelayed, sil
0x140031863  jnz     loc_140031627
0x140031869  jmp     loc_140031764
0x14003186e  mov     [rdi+8], rsi
0x140031872  mov     rdx, rdi; ListEntry
0x140031875  lea     rcx, NtfsUnchainedMcbQueue; ListHead
0x14003187c  call    cs:__imp_ExpInterlockedPushEntrySList
0x140031883  nop     dword ptr [rax+rax+00h]
0x140031888  mov     rax, [rbx+18h]
0x14003188c  mov     [r12+rax+10h], rdi
0x140031891  mov     r15, rsi
0x140031894  mov     [rsp+0D8h+var_78], rsi
0x140031899  jmp     loc_14003163A
0x14003189e  mov     [rdi+8], rsi
0x1400318a2  mov     rax, [rbx+18h]
0x1400318a6  mov     [r12+rax+10h], rdi
0x1400318ab  mov     r15, rsi
0x1400318ae  mov     [rsp+0D8h+var_78], rsi
0x1400318b3  mov     r9, [rsp+0D8h+var_90]
0x1400318b8  mov     r10, [rsp+0D8h+var_70]
0x1400318bd  mov     r11, [rsp+0D8h+var_80]
0x1400318c2  jmp     loc_14003164F
0x1400318c7  mov     rax, [rbx]
0x1400318ca  mov     rcx, [rax+1F0h]
0x1400318d1  xor     esi, esi
0x1400318d3  test    rcx, rcx
0x1400318d6  jz      short loc_140031907
0x1400318d8  mov     rax, [rbx+18h]
0x1400318dc  mov     rdx, [r12+rax]
0x1400318e0  cmp     rdx, [rcx+40h]
0x1400318e4  jge     short loc_1400318EA
0x1400318e6  mov     [rcx+40h], rdx
0x1400318ea  mov     rax, [rbx]
0x1400318ed  mov     rcx, [rax+1F0h]
0x1400318f4  mov     rax, [rbx+18h]
0x1400318f8  mov     rdx, [r12+rax+8]
0x1400318fd  cmp     rdx, [rcx+48h]
0x140031901  jle     short loc_140031907
0x140031903  mov     [rcx+48h], rdx
0x140031907  lea     rcx, [rdi+28h]; Mcb
0x14003190b  call    cs:__imp_FsRtlNumberOfRunsInBaseMcb
0x140031912  nop     dword ptr [rax+rax+00h]
0x140031917  test    eax, eax
0x140031919  jz      short loc_140031928
0x14003191b  mov     rdx, [rsp+0D8h+var_58]
0x140031923  inc     rdx
0x140031926  jmp     short loc_14003193F
0x140031928  mov     rax, [rsp+0D8h+var_70]
0x14003192d  cmp     r13, rax
0x140031930  jnz     short loc_14003193C
0x140031932  mov     edx, 0FFFFFFFFh
0x140031937  add     rdx, rax
0x14003193a  jmp     short loc_14003193F
0x14003193c  mov     rdx, r13
0x14003193f  xor     r9d, r9d
0x140031942  mov     r8d, dword ptr [rsp+0D8h+var_90]
0x140031947  mov     rcx, rbx
0x14003194a  call    NtfsInsertNewRange
0x14003194f  test    al, al
  ... truncated ...
```
