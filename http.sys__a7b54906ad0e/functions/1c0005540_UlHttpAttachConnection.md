# UlHttpAttachConnection

- ea: `0x1c0005540`
- end: `0x1c0005c2a`
- name: `UlHttpAttachConnection`
- size: `1770`
- prototype: ``
- caller_count: `4`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c0003f50`
- `0x1c0040800`
- `0x1c00b94d0`
- `0x1c01130c0`

## callees

- `0x1c0001118`
- `0x1c0001ae0`
- `0x1c0002bc0`
- `0x1c0005540`
- `0x1c0005c30`
- `0x1c000e880`
- `0x1c001b610`
- `0x1c001b900`
- `0x1c008f21c`
- `0x1c008f374`
- `0x1c008f4f0`
- `0x1c008f570`
- `0x1c008f680`
- `0x1c008f76c`
- `0x1c0094d94`
- `0x1c00a9970`
- `0x1c00d6070`
- `0x1c00d60c4`

## import_xrefs

- `ntoskrnl!InitializeSListHead` at `0x1c00056a0`
- `ntoskrnl!InitializeSListHead` at `0x1c00056a0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0005602`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c001d063`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0005602`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c001d063`
- `ntoskrnl!KeBugCheckEx` at `0x1c001d42e`
- `ntoskrnl!KeBugCheckEx` at `0x1c001d49b`
- `ntoskrnl!KeBugCheckEx` at `0x1c001d42e`
- `ntoskrnl!KeBugCheckEx` at `0x1c001d49b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c001d023`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c001d023`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c00056bd`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c00056f6`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c00056bd`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c00056f6`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c001d3b8`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c001d3b8`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x1c000586f`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x1c000586f`

## pseudocode

```c
__int64 __fastcall UlHttpAttachConnection(struct _SLIST_ENTRY *a1, __int64 a2, PSLIST_ENTRY *a3, _QWORD *a4, int a5)
{
  int v9; // ebx
  unsigned int v10; // r8d
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rbx
  PSLIST_ENTRY v15; // rdi
  struct _SLIST_ENTRY *v16; // r14
  _DWORD *v17; // rsi
  struct _SLIST_ENTRY *v18; // rbx
  __int64 v19; // rbp
  unsigned __int16 v20; // ax
  char i; // cl
  __int64 v22; // r8
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 (__fastcall *v27)(__int64, __int64, __int64, __int64); // rax
  __int64 v28; // rdi
  unsigned int v29; // r8d
  unsigned int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rax
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v34; // r9
  __int64 v35; // rcx
  ULONG_PTR v36; // rdi
  __int64 v37; // [rsp+28h] [rbp-70h]
  __int64 v38; // [rsp+40h] [rbp-58h] BYREF
  struct _SLIST_ENTRY *v39; // [rsp+48h] [rbp-50h] BYREF
  ULONG_PTR BugCheckParameter2; // [rsp+50h] [rbp-48h]
  _OWORD v41[4]; // [rsp+58h] [rbp-40h] BYREF

  v39 = 0;
  v38 = 0;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qiqqL(15, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, a1, a2, a3, a4, a5);
  v9 = (*(__int64 (__fastcall **)(struct _SLIST_ENTRY *, __int64, struct _SLIST_ENTRY **, __int64 *, _QWORD, _QWORD))(a2 + 120))(
         a1,
         27,
         &v39,
         &v38,
         0,
         0);
  if ( v9 < 0 )
    goto LABEL_67;
  if ( !UxCompactMode )
  {
    v10 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
    v11 = *(_DWORD *)qword_1C0074360 - 1;
    if ( v10 < *(_DWORD *)qword_1C0074360 )
      v11 = v10;
    v12 = v11;
    v13 = *(_QWORD *)(qword_1C0074360 + 32);
    v14 = *(_QWORD *)(v13 + 8 * v12);
    if ( !*(_BYTE *)(v14 + 112) )
      PplpLazyInitializeLookasideList(qword_1C0074360, *(_QWORD *)(v13 + 8 * v12));
    ++*(_DWORD *)(v14 + 20);
    v15 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v14);
    if ( v15 )
      goto LABEL_10;
LABEL_70:
    v24 = *(unsigned int *)(v14 + 40);
    v25 = *(unsigned int *)(v14 + 44);
    v26 = *(unsigned int *)(v14 + 36);
    v27 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v14 + 48);
    ++*(_DWORD *)(v14 + 24);
    v15 = (PSLIST_ENTRY)v27(v26, v25, v24, v14);
    goto LABEL_10;
  }
  v28 = qword_1C0074360;
  v29 = KeGetCurrentNodeNumber() + 1;
  v30 = *(_DWORD *)v28 - 1;
  if ( v29 < *(_DWORD *)v28 )
    v30 = v29;
  v31 = v30;
  v32 = *(_QWORD *)(v28 + 32);
  v14 = *(_QWORD *)(v32 + 8 * v31);
  if ( !*(_BYTE *)(v14 + 112) )
    PplpLazyInitializeLookasideList(v28, *(_QWORD *)(v32 + 8 * v31));
  ++*(_DWORD *)(v14 + 20);
  v15 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v14);
  if ( !v15 )
    goto LABEL_70;
LABEL_10:
  if ( !v15 )
  {
    v9 = -1073741670;
    UxPodDereferenceSilo(v38, 1129606229);
    v38 = 0;
    goto LABEL_67;
  }
  memset(v15, 0, 0x3E0u);
  HIDWORD(v15[1].Next) = 1;
  v15[2].Next = 0;
  BugCheckParameter2 = (ULONG_PTR)&v15[2];
  v15[3].Next = 0;
  v15[4].Next = 0;
  v15[30].Next = (PSLIST_ENTRY)((char *)v15 + 472);
  *((_QWORD *)&v15[29].Next + 1) = (char *)v15 + 472;
  LODWORD(v15[1].Next) = 1128819797;
  v15[5].Next = 0;
  v15[6].Next = 0;
  v15[7].Next = 0;
  v15[8].Next = 0;
  v15[9].Next = 0;
  v15[10].Next = 0;
  v15[11].Next = 0;
  v15[12].Next = 0;
  v15[13].Next = 0;
  InitializeSListHead((PSLIST_HEADER)&v15[14]);
  v15[29].Next = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)&v15[33]);
  *((_QWORD *)&v15[43].Next + 1) = -1;
  v15[43].Next = (struct _SLIST_ENTRY *)-1LL;
  v15[53].Next = v15;
  *((_DWORD *)&v15[53].Next + 2) = 0x10000;
  KeInitializeSpinLock((PKSPIN_LOCK)&v15[52].Next + 1);
  *((_QWORD *)&v15[55].Next + 1) = v15 + 55;
  v15[55].Next = v15 + 55;
  *((_QWORD *)&v15[57].Next + 1) = v15 + 57;
  v15[57].Next = v15 + 57;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_q(18, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, &v15[50].Next + 1);
  v15[51].Next = 0;
  *((_QWORD *)&v15[51].Next + 1) = 0;
  v15[52].Next = 0;
  *((_QWORD *)&v15[50].Next + 1) = 0;
  *((_QWORD *)&v15[51].Next + 1) = v15 + 51;
  v15[51].Next = v15 + 51;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_(19, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  v16 = v15 + 24;
  *((_QWORD *)&v15[24].Next + 1) = 0;
  v15[25].Next = 0;
  LODWORD(v15[25].Next) = 1;
  v15[24].Next = a1;
  *((_QWORD *)&v15[24].Next + 1) = a2;
  (*(void (__fastcall **)(struct _SLIST_ENTRY *, __int64, struct _SLIST_ENTRY **, _QWORD, _QWORD, _QWORD))(a2 + 120))(
    a1,
    5,
    &v15[22].Next + 1,
    0,
    0,
    0);
  v17 = &v15[33].Next + 1;
  v18 = v39;
  v19 = *((_QWORD *)&v15[22].Next + 1) + 16LL;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x40000) != 0 )
    WPP_SF_qD(10, WPP_20c69057ee6a3f9e768305e1cbf86669_Traceguids, &v15[33].Next + 1, 0);
  memset((char *)&v15[33].Next + 12, 0, 0x7Cu);
  v15[40] = (struct _SLIST_ENTRY)_mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *((_QWORD *)&v15[34].Next + 1) = v15 + 33;
  v15[34].Next = (struct _SLIST_ENTRY *)v19;
  v20 = 0;
  *((_BYTE *)&v15[39].Next + 12) = 1;
  *v17 = 0;
  for ( i = UlTimersPerBundle; v20 < (unsigned __int16)UlTimersPerBundle; i = UlTimersPerBundle )
  {
    v22 = v20++;
    v17[v22 + 18] = *((_DWORD *)&v18[254].Next + UlTimerIdLookup[v22]);
  }
  *((_DWORD *)&v15[39].Next + 2) = (1 << i) - 1;
  if ( _InterlockedIncrement((volatile signed __int32 *)(v19 + 64)) == 1 )
    UlpIncrementMetronome();
  RtlInitializeTimerWheelEntry(0, &v15[35], 0, 0);
  *((_DWORD *)&v15[32].Next + 2) |= 0x40u;
  v15[60].Next = v39;
  v39 = 0;
  *((_QWORD *)&v15[59].Next + 1) = v38;
  v38 = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
    WPP_SF_qLqqqq(
      10,
      WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids,
      &v15[24],
      0,
      &v15[18],
      (char *)&v15[19].Next + 12,
      0,
      0);
  v9 = (*(__int64 (__fastcall **)(struct _SLIST_ENTRY *, _QWORD, PSLIST_ENTRY, __int64, _QWORD, _QWORD))(*((_QWORD *)&v15[24].Next + 1) + 120LL))(
         v16->Next,
         0,
         v15 + 18,
         (__int64)&v15[19].Next + 12,
         0,
         0);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
    WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
  if ( v9 >= 0 )
  {
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
      WPP_SF_qLqqqq(10, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids, &v15[24], 3, &v15[21].Next + 1, 0, 0, 0);
    HIDWORD(v37) = 0;
    v9 = (*(__int64 (__fastcall **)(struct _SLIST_ENTRY *, __int64, struct _SLIST_ENTRY **))(*((_QWORD *)&v15[24].Next
                                                                                             + 1)
                                                                                           + 120LL))(
           v16->Next,
           3,
           &v15[21].Next + 1);
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
      WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
    if ( v9 >= 0 )
    {
      if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
        WPP_SF_qLqqqq(
          10,
          WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids,
          &v15[24],
          6,
          (char *)&v15[23].Next + 1,
          0,
          0,
          0);
      HIDWORD(v37) = 0;
      v9 = (*(__int64 (__fastcall **)(struct _SLIST_ENTRY *, __int64, __int64))(*((_QWORD *)&v15[24].Next + 1) + 120LL))(
             v16->Next,
             6,
             (__int64)&v15[23].Next + 1);
      if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
        WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
      if ( v9 >= 0 )
      {
        if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
          WPP_SF_qLqqqq(10, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids, &v15[24], 1, &v15[23].Next + 1, 0, 0, 0);
        HIDWORD(v37) = 0;
        v9 = (*(__int64 (__fastcall **)(struct _SLIST_ENTRY *, __int64, struct _SLIST_ENTRY **))(*((_QWORD *)&v15[24].Next
                                                                                                 + 1)
                                                                                               + 120LL))(
               v16->Next,
               1,
               &v15[23].Next + 1);
        if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
          WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
        if ( v9 >= 0 )
        {
          if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
            WPP_SF_qLqqqq(10, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids, &v15[24], 6, &v15[23], 0, 0, 0);
          HIDWORD(v37) = 0;
          v9 = (*(__int64 (__fastcall **)(struct _SLIST_ENTRY *, __int64, PSLIST_ENTRY))(*((_QWORD *)&v15[24].Next + 1)
                                                                                       + 120LL))(
                 v16->Next,
                 6,
                 v15 + 23);
          if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
            WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
          if ( v9 >= 0 )
          {
            if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
              WPP_SF_qLqqqq(
                10,
                WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids,
                &v15[24],
                23,
                (char *)&v15[25].Next + 13,
                0,
                0,
                0);
            HIDWORD(v37) = 0;
            v9 = (*(__int64 (__fastcall **)(struct _SLIST_ENTRY *, __int64, __int64))(*((_QWORD *)&v15[24].Next + 1)
                                                                                    + 120LL))(
                   v16->Next,
                   23,
                   (__int64)&v15[25].Next + 13);
            if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
              WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
            if ( v9 >= 0 )
            {
              if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
                WPP_SF_qLqqqq(
                  10,
                  WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids,
                  &v15[24],
                  41,
                  (char *)&v15[60].Next + 12,
                  0,
                  0,
                  0);
              HIDWORD(v37) = 0;
              v9 = (*(__int64 (__fastcall **)(struct _SLIST_ENTRY *, __int64, __int64))(*((_QWORD *)&v15[24].Next + 1)
                                                                                      + 120LL))(
                     v16->Next,
                     41,
                     (__int64)&v15[60].Next + 12);
              if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
                WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
              if ( v9 >= 0 )
              {
                if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
                  WPP_SF_qLqqqq(10, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids, &v15[24], 42, &v15[61], 0, 0, 0);
                HIDWORD(v37) = 0;
                v9 = (*(__int64 (__fastcall **)(struct _SLIST_ENTRY *, __int64, PSLIST_ENTRY))(*((_QWORD *)&v15[24].Next
                                                                                               + 1)
                                                                                             + 120LL))(
                       v16->Next,
                       42,
                       v15 + 61);
                if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
                  WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
                if ( v9 >= 0 )
                {
                  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
                    WPP_SF_qLqqqq(
                      10,
                      WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids,
                      &v15[24],
                      45,
                      (char *)&v15[23].Next + 2,
                      0,
                      0,
                      0);
                  HIDWORD(v37) = 0;
                  v9 = (*(__int64 (__fastcall **)(struct _SLIST_ENTRY *, __int64, __int64))(*((_QWORD *)&v15[24].Next + 1)
                                                                                          + 120LL))(
                         v16->Next,
                         45,
                         (__int64)&v15[23].Next + 2);
                  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
                    WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
                  if ( v9 >= 0 )
                  {
                    *a3 = v15;
                    *a4 = &UlHttpDispatch;
                    LODWORD(v15[25].Next) = 2;
                    goto LABEL_67;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  UlCleanupBundle(&v15[33].Next + 1);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v15[1].Next + 1, 0xFFFFFFFF) == 1 )
  {
    CurrentProcess = IoGetCurrentProcess();
    v35 = *((_QWORD *)&v15[59].Next + 1);
    v36 = BugCheckParameter2;
    if ( UxSystemProcess != CurrentProcess )
    {
      if ( *(_QWORD *)BugCheckParameter2 || *(_QWORD *)(BugCheckParameter2 + 16) || *(_QWORD *)(BugCheckParameter2 + 32) )
        KeBugCheckEx(0xFAu, 1u, BugCheckParameter2, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
LABEL_83:
      LODWORD(v37) = -1;
      LOBYTE(v34) = 1;
      UlThreadPoolEnqueueWorkItem(0, BugCheckParameter2, UlFreeHttpConnection, v34, v35, v37);
      goto LABEL_67;
    }
    v41[0] = 0;
    if ( *(_QWORD *)BugCheckParameter2 || *(_QWORD *)(BugCheckParameter2 + 16) || *(_QWORD *)(BugCheckParameter2 + 32) )
      KeBugCheckEx(0xFAu, 1u, BugCheckParameter2, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
    if ( KeGetCurrentIrql() )
      goto LABEL_83;
    UxPodAttachThread(v35, v41);
    UlFreeHttpConnection(v36);
    UxPodDetachThread(v41);
  }
LABEL_67:
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qqD(16, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, *a3, *a4, v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1c0005540  mov     [rsp+arg_18], rbx
0x1c0005545  push    rbp
0x1c0005546  push    rsi
0x1c0005547  push    r12
0x1c0005549  push    r13
0x1c000554b  push    r14
0x1c000554d  sub     rsp, 70h
0x1c0005551  xor     r14d, r14d
0x1c0005554  mov     r12, r9
0x1c0005557  mov     [rsp+98h+var_50], r14
0x1c000555c  mov     r13, r8
0x1c000555f  mov     [rsp+98h+var_58], r14
0x1c0005564  mov     rsi, rdx
0x1c0005567  mov     rbp, rcx
0x1c000556a  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0005570  test    al, al
0x1c0005572  js      loc_1C001CFEA
0x1c0005578  mov     rax, [rsi+78h]
0x1c000557c  lea     r9, [rsp+98h+var_58]
0x1c0005581  mov     [rsp+98h+arg_0], rdi
0x1c0005589  lea     r8, [rsp+98h+var_50]
0x1c000558e  mov     [rsp+98h+var_70], r14
0x1c0005593  mov     edx, 1Bh
0x1c0005598  mov     rcx, rbp
0x1c000559b  mov     [rsp+98h+arg_10], r15
0x1c00055a3  mov     [rsp+98h+BugCheckParameter4], r14
0x1c00055a8  call    cs:__guard_dispatch_icall_fptr
0x1c00055ae  mov     ebx, eax
0x1c00055b0  test    eax, eax
0x1c00055b2  js      loc_1C0005BC8
0x1c00055b8  cmp     cs:UxCompactMode, r14b
0x1c00055bf  jnz     loc_1C001D01C
0x1c00055c5  mov     eax, gs:1A4h
0x1c00055cd  mov     rcx, cs:qword_1C0074360
0x1c00055d4  lea     r8d, [rax+1]
0x1c00055d8  mov     edx, [rcx]
0x1c00055da  cmp     r8d, edx
0x1c00055dd  lea     eax, [rdx-1]
0x1c00055e0  cmovb   eax, r8d
0x1c00055e4  mov     edx, eax
0x1c00055e6  mov     rax, [rcx+20h]
0x1c00055ea  mov     rbx, [rax+rdx*8]
0x1c00055ee  cmp     [rbx+70h], r14b
0x1c00055f2  jnz     short loc_1C00055FC
0x1c00055f4  mov     rdx, rbx
0x1c00055f7  call    PplpLazyInitializeLookasideList
0x1c00055fc  inc     dword ptr [rbx+14h]
0x1c00055ff  mov     rcx, rbx; ListHead
0x1c0005602  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0005609  nop     dword ptr [rax+rax+00h]
0x1c000560e  mov     rdi, rax
0x1c0005611  test    rax, rax
0x1c0005614  jz      loc_1C0005BFE
0x1c000561a  test    rdi, rdi
0x1c000561d  jz      loc_1C001D080
0x1c0005623  xor     edx, edx; Val
0x1c0005625  mov     r8d, 3E0h; Size
0x1c000562b  mov     rcx, rdi; void *
0x1c000562e  call    memset
0x1c0005633  lea     rax, [rdi+20h]
0x1c0005637  mov     dword ptr [rdi+14h], 1
0x1c000563e  mov     [rax], r14
0x1c0005641  lea     rcx, [rdi+0E0h]; SListHead
0x1c0005648  mov     [rsp+98h+BugCheckParameter2], rax
0x1c000564d  mov     [rax+10h], r14
0x1c0005651  mov     [rax+20h], r14
0x1c0005655  lea     rax, [rdi+1D8h]
0x1c000565c  mov     [rax+8], rax
0x1c0005660  mov     [rax], rax
0x1c0005663  mov     dword ptr [rdi+10h], 43486C55h
0x1c000566a  mov     [rdi+50h], r14
0x1c000566e  mov     [rdi+60h], r14
0x1c0005672  mov     [rdi+70h], r14
0x1c0005676  mov     [rdi+80h], r14
0x1c000567d  mov     [rdi+90h], r14
0x1c0005684  mov     [rdi+0A0h], r14
0x1c000568b  mov     [rdi+0B0h], r14
0x1c0005692  mov     [rdi+0C0h], r14
0x1c0005699  mov     [rdi+0D0h], r14
0x1c00056a0  call    cs:__imp_InitializeSListHead
0x1c00056a7  nop     dword ptr [rax+rax+00h]
0x1c00056ac  lea     r15, [rdi+210h]
0x1c00056b3  mov     [rdi+1D0h], r14
0x1c00056ba  mov     rcx, r15; SpinLock
0x1c00056bd  call    cs:__imp_KeInitializeSpinLock
0x1c00056c4  nop     dword ptr [rax+rax+00h]
0x1c00056c9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1c00056d0  lea     rcx, [rdi+348h]; SpinLock
0x1c00056d7  mov     [rdi+2B8h], rax
0x1c00056de  mov     [rdi+2B0h], rax
0x1c00056e5  mov     [rdi+350h], rdi
0x1c00056ec  mov     dword ptr [rdi+358h], 10000h
0x1c00056f6  call    cs:__imp_KeInitializeSpinLock
0x1c00056fd  nop     dword ptr [rax+rax+00h]
0x1c0005702  lea     rax, [rdi+370h]
0x1c0005709  mov     [rax+8], rax
0x1c000570d  mov     [rax], rax
0x1c0005710  lea     rax, [rdi+390h]
0x1c0005717  mov     [rax+8], rax
0x1c000571b  mov     [rax], rax
0x1c000571e  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0005724  test    al, al
0x1c0005726  js      loc_1C001D09E
0x1c000572c  mov     [rdi+330h], r14
0x1c0005733  lea     rax, [rdi+330h]
0x1c000573a  mov     [rdi+338h], r14
0x1c0005741  mov     [rdi+340h], r14
0x1c0005748  mov     [rdi+328h], r14
0x1c000574f  mov     [rax+8], rax
0x1c0005753  mov     [rax], rax
0x1c0005756  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c000575c  test    al, al
0x1c000575e  js      loc_1C001D0BC
0x1c0005764  xor     ecx, ecx
0x1c0005766  lea     r14, [rdi+180h]
0x1c000576d  mov     [rdi+188h], rcx
0x1c0005774  lea     r8, [rdi+168h]
0x1c000577b  mov     [rdi+190h], rcx
0x1c0005782  xor     r9d, r9d
0x1c0005785  mov     [rsp+98h+var_70], rcx
0x1c000578a  lea     edx, [rcx+5]
0x1c000578d  mov     dword ptr [r14+10h], 1
0x1c0005795  mov     [r14], rbp
0x1c0005798  mov     [r14+8], rsi
0x1c000579c  mov     rax, [rsi+78h]
0x1c00057a0  mov     [rsp+98h+BugCheckParameter4], rcx
0x1c00057a5  mov     rcx, rbp
0x1c00057a8  call    cs:__guard_dispatch_icall_fptr
0x1c00057ae  mov     rbp, [rdi+168h]
0x1c00057b5  lea     rsi, [rdi+218h]
0x1c00057bc  mov     rbx, [rsp+98h+var_50]
0x1c00057c1  add     rbp, 10h
0x1c00057c5  test    dword ptr cs:WPP_MAIN_CB.Queue, 40000h
0x1c00057cf  jnz     loc_1C001D0D3
0x1c00057d5  xor     edx, edx; Val
0x1c00057d7  lea     rcx, [rdi+21Ch]; void *
0x1c00057de  lea     r8d, [rdx+7Ch]; Size
0x1c00057e2  call    memset
0x1c00057e7  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1c00057ef  movups  xmmword ptr [rsi+68h], xmm0
0x1c00057f3  mov     [rsi+10h], r15
0x1c00057f7  xor     r15d, r15d
0x1c00057fa  mov     [rsi+8], rbp
0x1c00057fe  movzx   eax, r15w
0x1c0005802  mov     byte ptr [rsi+64h], 1
0x1c0005806  mov     dword ptr [rsi], 0
0x1c000580c  mov     ecx, dword ptr cs:UlTimersPerBundle
0x1c0005812  cmp     r15w, cx
0x1c0005816  jnb     short loc_1C0005842
0x1c0005818  lea     r9, UlTimerIdLookup
0x1c000581f  nop
0x1c0005820  movzx   r8d, ax
0x1c0005824  inc     ax
0x1c0005827  movsxd  rcx, dword ptr [r9+r8*4]
0x1c000582b  mov     edx, [rbx+rcx*4+0FE0h]
0x1c0005832  mov     [rsi+r8*4+48h], edx
0x1c0005837  mov     ecx, dword ptr cs:UlTimersPerBundle
0x1c000583d  cmp     ax, cx
0x1c0005840  jb      short loc_1C0005820
0x1c0005842  mov     eax, 1
0x1c0005847  shl     eax, cl
0x1c0005849  dec     eax
0x1c000584b  mov     [rsi+60h], eax
0x1c000584e  mov     eax, 1
0x1c0005853  lock xadd [rbp+40h], eax
0x1c0005858  inc     eax
0x1c000585a  cmp     eax, 1
0x1c000585d  jz      loc_1C0005C20
0x1c0005863  lea     rdx, [rsi+18h]
0x1c0005867  xor     r9d, r9d
0x1c000586a  xor     r8d, r8d
0x1c000586d  xor     ecx, ecx
0x1c000586f  call    cs:__imp_RtlInitializeTimerWheelEntry
0x1c0005876  nop     dword ptr [rax+rax+00h]
0x1c000587b  or      dword ptr [rdi+208h], 40h
0x1c0005882  lea     rbx, [rdi+13Ch]
0x1c0005889  mov     rax, [rsp+98h+var_50]
0x1c000588e  lea     rbp, [rdi+120h]
0x1c0005895  mov     [rdi+3C0h], rax
0x1c000589c  mov     rax, [rsp+98h+var_58]
0x1c00058a1  mov     [rsp+98h+var_50], r15
0x1c00058a6  mov     [rdi+3B8h], rax
0x1c00058ad  mov     [rsp+98h+var_58], r15
0x1c00058b2  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c00058bc  jnz     loc_1C001D0F0
0x1c00058c2  mov     rax, [r14+8]
0x1c00058c6  mov     r9, rbx
0x1c00058c9  mov     rcx, [r14]
0x1c00058cc  mov     r8, rbp
0x1c00058cf  mov     [rsp+98h+var_70], r15
0x1c00058d4  xor     edx, edx
0x1c00058d6  mov     [rsp+98h+BugCheckParameter4], r15
0x1c00058db  mov     rax, [rax+78h]
0x1c00058df  call    cs:__guard_dispatch_icall_fptr
0x1c00058e5  mov     ebx, eax
0x1c00058e7  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c00058f1  jnz     loc_1C001D121
0x1c00058f7  test    ebx, ebx
0x1c00058f9  js      loc_1C001D39B
0x1c00058ff  lea     rbx, [rdi+158h]
0x1c0005906  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c0005910  jnz     loc_1C001D13B
0x1c0005916  mov     rax, [r14+8]
0x1c000591a  xor     r9d, r9d
0x1c000591d  mov     rcx, [r14]
0x1c0005920  mov     r8, rbx
0x1c0005923  mov     [rsp+98h+var_70], r15
0x1c0005928  mov     [rsp+98h+BugCheckParameter4], r15
0x1c000592d  mov     rax, [rax+78h]
0x1c0005931  lea     edx, [r9+3]
0x1c0005935  call    cs:__guard_dispatch_icall_fptr
0x1c000593b  mov     ebx, eax
0x1c000593d  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c0005947  jnz     loc_1C001D16D
0x1c000594d  test    ebx, ebx
0x1c000594f  js      loc_1C001D39B
0x1c0005955  lea     rbx, [rdi+171h]
0x1c000595c  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c0005966  jnz     loc_1C001D187
0x1c000596c  mov     rax, [r14+8]
0x1c0005970  xor     r9d, r9d
0x1c0005973  mov     rcx, [r14]
0x1c0005976  mov     r8, rbx
0x1c0005979  mov     [rsp+98h+var_70], r15
0x1c000597e  mov     [rsp+98h+BugCheckParameter4], r15
0x1c0005983  mov     rax, [rax+78h]
0x1c0005987  lea     edx, [r9+6]
0x1c000598b  call    cs:__guard_dispatch_icall_fptr
0x1c0005991  mov     ebx, eax
0x1c0005993  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c000599d  jnz     loc_1C001D1B9
0x1c00059a3  test    ebx, ebx
0x1c00059a5  js      loc_1C001D39B
0x1c00059ab  lea     rbx, [rdi+178h]
0x1c00059b2  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c00059bc  jnz     loc_1C001D1D3
0x1c00059c2  mov     rax, [r14+8]
0x1c00059c6  xor     r9d, r9d
0x1c00059c9  mov     rcx, [r14]
0x1c00059cc  mov     r8, rbx
0x1c00059cf  mov     [rsp+98h+var_70], r15
0x1c00059d4  mov     [rsp+98h+BugCheckParameter4], r15
0x1c00059d9  mov     rax, [rax+78h]
0x1c00059dd  lea     edx, [r9+1]
0x1c00059e1  call    cs:__guard_dispatch_icall_fptr
0x1c00059e7  mov     ebx, eax
0x1c00059e9  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c00059f3  jnz     loc_1C001D205
0x1c00059f9  test    ebx, ebx
0x1c00059fb  js      loc_1C001D39B
0x1c0005a01  lea     rbx, [rdi+170h]
0x1c0005a08  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c0005a12  jnz     loc_1C001D21F
0x1c0005a18  mov     rax, [r14+8]
0x1c0005a1c  xor     r9d, r9d
0x1c0005a1f  mov     rcx, [r14]
0x1c0005a22  mov     r8, rbx
0x1c0005a25  mov     [rsp+98h+var_70], r15
0x1c0005a2a  mov     [rsp+98h+BugCheckParameter4], r15
0x1c0005a2f  mov     rax, [rax+78h]
0x1c0005a33  lea     edx, [r9+6]
0x1c0005a37  call    cs:__guard_dispatch_icall_fptr
0x1c0005a3d  mov     ebx, eax
0x1c0005a3f  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c0005a49  jnz     loc_1C001D251
0x1c0005a4f  test    ebx, ebx
0x1c0005a51  js      loc_1C001D39B
0x1c0005a57  lea     rbx, [rdi+19Dh]
0x1c0005a5e  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c0005a68  jnz     loc_1C001D26B
0x1c0005a6e  mov     rax, [r14+8]
0x1c0005a72  xor     r9d, r9d
0x1c0005a75  mov     rcx, [r14]
0x1c0005a78  mov     r8, rbx
0x1c0005a7b  mov     [rsp+98h+var_70], r15
0x1c0005a80  mov     [rsp+98h+BugCheckParameter4], r15
0x1c0005a85  mov     rax, [rax+78h]
0x1c0005a89  lea     edx, [r9+17h]
0x1c0005a8d  call    cs:__guard_dispatch_icall_fptr
0x1c0005a93  mov     ebx, eax
0x1c0005a95  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c0005a9f  jnz     loc_1C001D29D
0x1c0005aa5  test    ebx, ebx
0x1c0005aa7  js      loc_1C001D39B
0x1c0005aad  lea     rbx, [rdi+3CCh]
0x1c0005ab4  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c0005abe  jnz     loc_1C001D2B7
0x1c0005ac4  mov     rax, [r14+8]
0x1c0005ac8  xor     r9d, r9d
0x1c0005acb  mov     rcx, [r14]
0x1c0005ace  mov     r8, rbx
0x1c0005ad1  mov     [rsp+98h+var_70], r15
0x1c0005ad6  mov     [rsp+98h+BugCheckParameter4], r15
0x1c0005adb  mov     rax, [rax+78h]
0x1c0005adf  lea     edx, [r9+29h]
0x1c0005ae3  call    cs:__guard_dispatch_icall_fptr
0x1c0005ae9  mov     ebx, eax
0x1c0005aeb  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c0005af5  jnz     loc_1C001D2E9
0x1c0005afb  test    ebx, ebx
  ... truncated ...
```
