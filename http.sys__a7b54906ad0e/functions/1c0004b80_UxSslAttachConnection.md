# UxSslAttachConnection

- ea: `0x1c0004b80`
- end: `0x1c00050d9`
- name: `UxSslAttachConnection`
- size: `1369`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c0008b90`

## callees

- `0x1c0001118`
- `0x1c0001ae0`
- `0x1c0002bc0`
- `0x1c0003f50`
- `0x1c0004b80`
- `0x1c0005cd4`
- `0x1c000e880`
- `0x1c001a548`
- `0x1c001b610`
- `0x1c001b900`
- `0x1c008f374`
- `0x1c008f4f0`
- `0x1c008f570`
- `0x1c008f76c`
- `0x1c0094d94`
- `0x1c009b51c`

## import_xrefs

- `ntoskrnl!InitializeSListHead` at `0x1c0004e98`
- `ntoskrnl!InitializeSListHead` at `0x1c0004e98`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0004c5b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c001cc9c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0004c5b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c001cc9c`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1c001cd1d`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1c001cd1d`
- `ntoskrnl!KeBugCheckEx` at `0x1c001cec6`
- `ntoskrnl!KeBugCheckEx` at `0x1c001cec6`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c001cc5c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c001cc5c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0005090`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0005090`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0005063`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0005063`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c0004d24`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c0004e1e`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c0004e6c`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c0004d24`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c0004e1e`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c0004e6c`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x1c0004df6`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x1c0004df6`

## pseudocode

```c
__int64 __fastcall UxSslAttachConnection(struct _SLIST_ENTRY *a1, __int64 a2, PSLIST_ENTRY *a3, _QWORD *a4, int a5)
{
  PSLIST_ENTRY *v6; // r14
  int v9; // edi
  unsigned int v10; // r8d
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdi
  PSLIST_ENTRY v15; // rbx
  struct _SLIST_ENTRY *v16; // rsi
  struct _SLIST_ENTRY *v17; // rdi
  __int64 v18; // rbp
  unsigned __int16 v19; // r8
  char i; // al
  __int64 v21; // rdx
  ADDRESS_FAMILY *v22; // r15
  ADDRESS_FAMILY *v23; // rbp
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 (__fastcall *v28)(__int64, __int64, __int64, __int64); // rax
  KIRQL v29; // di
  __int64 v30; // rbx
  unsigned int v31; // r8d
  unsigned int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rax
  ADDRESS_FAMILY v35; // cx
  UCHAR v36; // al
  ADDRESS_FAMILY v37; // cx
  UCHAR v38; // al
  int v39; // ecx
  __int64 v40; // [rsp+28h] [rbp-90h]
  __int64 v41; // [rsp+40h] [rbp-78h] BYREF
  struct _SLIST_ENTRY *v42; // [rsp+48h] [rbp-70h] BYREF
  __int128 v43; // [rsp+50h] [rbp-68h]
  __int128 v44; // [rsp+60h] [rbp-58h]
  __int128 v45; // [rsp+70h] [rbp-48h] BYREF
  __int128 v46; // [rsp+80h] [rbp-38h] BYREF

  v42 = 0;
  v6 = a3;
  v41 = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000) != 0 )
    WPP_SF_qiqqL(10, WPP_8ecfc4db63433714fa4cc8be4e523449_Traceguids, a1, a2, a3, a4, a5);
  if ( (a5 & 0x10) == 0 )
  {
    v9 = UxDuoAttachConnection((_DWORD)a1, a2, (_DWORD)v6, (_DWORD)a4, a5);
    goto LABEL_30;
  }
  v9 = (*(__int64 (__fastcall **)(struct _SLIST_ENTRY *, __int64, struct _SLIST_ENTRY **, __int64 *, _QWORD, _QWORD))(a2 + 120))(
         a1,
         27,
         &v42,
         &v41,
         0,
         0);
  if ( v9 < 0 )
    goto LABEL_30;
  if ( !UxCompactMode )
  {
    v10 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
    v11 = *(_DWORD *)qword_1C0074390 - 1;
    if ( v10 < *(_DWORD *)qword_1C0074390 )
      v11 = v10;
    v12 = v11;
    v13 = *(_QWORD *)(qword_1C0074390 + 32);
    v14 = *(_QWORD *)(v13 + 8 * v12);
    if ( !*(_BYTE *)(v14 + 112) )
      PplpLazyInitializeLookasideList(qword_1C0074390, *(_QWORD *)(v13 + 8 * v12));
    ++*(_DWORD *)(v14 + 20);
    v15 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v14);
    if ( v15 )
      goto LABEL_11;
LABEL_33:
    v25 = *(unsigned int *)(v14 + 40);
    v26 = *(unsigned int *)(v14 + 44);
    v27 = *(unsigned int *)(v14 + 36);
    v28 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v14 + 48);
    ++*(_DWORD *)(v14 + 24);
    v15 = (PSLIST_ENTRY)v28(v27, v26, v25, v14);
    goto LABEL_11;
  }
  v30 = qword_1C0074390;
  v31 = KeGetCurrentNodeNumber() + 1;
  v32 = *(_DWORD *)v30 - 1;
  if ( v31 < *(_DWORD *)v30 )
    v32 = v31;
  v33 = v32;
  v34 = *(_QWORD *)(v30 + 32);
  v14 = *(_QWORD *)(v34 + 8 * v33);
  if ( !*(_BYTE *)(v14 + 112) )
    PplpLazyInitializeLookasideList(v30, *(_QWORD *)(v34 + 8 * v33));
  ++*(_DWORD *)(v14 + 20);
  v15 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v14);
  if ( !v15 )
    goto LABEL_33;
LABEL_11:
  if ( !v15 )
  {
    v9 = -1073741670;
    UxPodDereferenceSilo(v41, 1129606229);
    v41 = 0;
    goto LABEL_30;
  }
  memset(v15, 0, (unsigned int)UxSslConnectionSize);
  HIDWORD(v15[1].Next) = 1;
  LODWORD(v15[1].Next) = 1095989333;
  v15[13].Next = 0;
  v15[10].Next = 0;
  v15[11].Next = 0;
  v15[12].Next = 0;
  *((_QWORD *)&v15[13].Next + 1) = 0;
  LODWORD(v15[14].Next) = 0;
  LODWORD(v15[31].Next) = 1;
  *(struct _SLIST_ENTRY *)((char *)&v15[1] + 8) = 0;
  *((_QWORD *)&v15[2].Next + 1) = 0;
  *((_DWORD *)&v15[2].Next + 2) = 1;
  v15[4].Next = 0;
  LODWORD(v15[4].Next) = 1;
  v15[3].Next = a1;
  *((_QWORD *)&v15[3].Next + 1) = a2;
  (*(void (__fastcall **)(struct _SLIST_ENTRY *, __int64, PSLIST_ENTRY))(a2 + 120))(a1, 5, v15 + 9);
  KeInitializeSpinLock((PKSPIN_LOCK)&v15[15].Next + 1);
  v16 = v15 + 16;
  v17 = v42;
  v18 = (__int64)&v15[9].Next[1];
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x40000) != 0 )
    WPP_SF_qD(10, WPP_20c69057ee6a3f9e768305e1cbf86669_Traceguids, &v15[16], 1);
  memset((char *)&v15[16].Next + 4, 0, 0x7Cu);
  *(__m128i *)((char *)&v15[22] + 8) = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v15[17].Next = (PSLIST_ENTRY)((char *)v15 + 248);
  *((_QWORD *)&v15[16].Next + 1) = v18;
  v19 = 0;
  BYTE4(v15[22].Next) = 1;
  LODWORD(v16->Next) = 1;
  for ( i = BYTE2(UlTimersPerBundle); v19 < WORD1(UlTimersPerBundle); i = BYTE2(UlTimersPerBundle) )
  {
    v21 = v19++;
    *((_DWORD *)&v16[4].Next + v21 + 2) = *((_DWORD *)&v17[254].Next + *((int *)qword_1C0076F18 + v21));
  }
  LODWORD(v15[22].Next) = (1 << i) - 1;
  if ( _InterlockedIncrement((volatile signed __int32 *)(v18 + 64)) == 1 )
  {
    v29 = KeAcquireSpinLockRaiseToDpc(&UlHotAddCommitLock);
    if ( ++UlMetronomeCount != 1 )
    {
LABEL_35:
      KeReleaseSpinLock(&UlHotAddCommitLock, v29);
      goto LABEL_17;
    }
    if ( UlMetronomeState )
    {
      if ( UlMetronomeState != 1 )
        goto LABEL_35;
    }
    else
    {
      UlpResumeTimerWheels();
      KeSetCoalescableTimer(&UlMetronomeTimer, (LARGE_INTEGER)-50000000LL, 0, 0x1F4u, &UlMetronomeDpc);
    }
    UlMetronomeState = 2;
    goto LABEL_35;
  }
LABEL_17:
  RtlInitializeTimerWheelEntry(0, &v15[17].Next + 1, 0, 0);
  v15[28].Next = (struct _SLIST_ENTRY *)-1LL;
  *((_QWORD *)&v15[27].Next + 1) = -1;
  KeInitializeSpinLock((PKSPIN_LOCK)&v15[32]);
  *((_DWORD *)&v15[33].Next + 2) = 0;
  v15[33].Next = (PSLIST_ENTRY)((char *)v15 + 520);
  *((_QWORD *)&v15[32].Next + 1) = (char *)v15 + 520;
  *((_DWORD *)&v15[33].Next + 3) = -1;
  v15[59].Next = (PSLIST_ENTRY)((char *)v15 + 936);
  *((_QWORD *)&v15[58].Next + 1) = (char *)v15 + 936;
  v15[40].Next = (PSLIST_ENTRY)((char *)v15 + 632);
  *((_QWORD *)&v15[39].Next + 1) = (char *)v15 + 632;
  KeInitializeSpinLock((PKSPIN_LOCK)&v15[41]);
  v15[56] = 0;
  WORD1(v15[56].Next) = 0;
  *((_QWORD *)&v15[56].Next + 1) = 0;
  InitializeSListHead((PSLIST_HEADER)&v15[43]);
  *((_DWORD *)&v15[49].Next + 2) |= 2u;
  v15[48].Next = (PSLIST_ENTRY)((char *)v15 + 760);
  *((_QWORD *)&v15[47].Next + 1) = (char *)v15 + 760;
  v15[49].Next = (PSLIST_ENTRY)((char *)v15 + 776);
  *((_QWORD *)&v15[48].Next + 1) = (char *)v15 + 776;
  LODWORD(v15[68].Next) = 1685280885;
  *((_QWORD *)&v15[50].Next + 1) = v15 + 68;
  v15[44].Next = 0;
  v15[45].Next = 0;
  v15[46].Next = 0;
  HIDWORD(v15[58].Next) = 3072;
  *((_DWORD *)&v15[41].Next + 3) = 33792;
  v15[60].Next = v42;
  v42 = 0;
  *((_QWORD *)&v15[59].Next + 1) = v41;
  v41 = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
    WPP_SF_qLqqqq(10, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids, &v15[3], 3, &v15[4].Next + 1, 0, 0, 0);
  HIDWORD(v40) = 0;
  v9 = (*(__int64 (__fastcall **)(struct _SLIST_ENTRY *, __int64, struct _SLIST_ENTRY **))(*((_QWORD *)&v15[3].Next + 1)
                                                                                         + 120LL))(
         v15[3].Next,
         3,
         &v15[4].Next + 1);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
    WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
  if ( v9 < 0 )
    goto LABEL_48;
  v22 = (ADDRESS_FAMILY *)&v15[7].Next + 2;
  v23 = (ADDRESS_FAMILY *)(&v15[5].Next + 1);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
    WPP_SF_qLqqqq(
      10,
      WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids,
      &v15[3],
      0,
      &v15[5].Next + 1,
      (char *)&v15[7].Next + 4,
      0,
      0);
  v9 = (*(__int64 (__fastcall **)(struct _SLIST_ENTRY *, _QWORD, struct _SLIST_ENTRY **, __int64, _QWORD, _QWORD))(*((_QWORD *)&v15[3].Next + 1) + 120LL))(
         v15[3].Next,
         0,
         &v15[5].Next + 1,
         (__int64)&v15[7].Next + 4,
         0,
         0);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
    WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
  if ( v9 < 0 )
  {
LABEL_48:
    UlCleanupBundle(&v15[16]);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v15[1].Next + 1, 0xFFFFFFFF) == 1 )
    {
      if ( v15[10].Next || v15[11].Next || v15[12].Next )
        KeBugCheckEx(0xFAu, 1u, (ULONG_PTR)&v15[10], (ULONG_PTR)"minio\\http\\sys\\sslconn.h", 0x3FFu);
      LODWORD(v40) = -1;
      UlThreadPoolEnqueueWorkItem(1, &v15[10], UxSslFreeConnection, 1, *((_QWORD *)&v15[59].Next + 1), v40);
    }
    v6 = a3;
  }
  else
  {
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000) != 0 )
    {
      v35 = *v22;
      v43 = (unsigned __int64)v22;
      v36 = SOCKADDR_SIZE(v35);
      v37 = *v23;
      WORD4(v43) = v36;
      v45 = v43;
      v44 = (unsigned __int64)v23;
      v38 = SOCKADDR_SIZE(v37);
      WORD4(v44) = v38;
      v46 = v44;
      WPP_SF_q_SOCKADDR__SOCKADDR_q(v39, v38, (_DWORD)v15, (unsigned int)&v46, (__int64)&v45);
    }
    v6 = a3;
    *a3 = v15;
    *a4 = &UxSslDispatch;
    LODWORD(v15[4].Next) = 2;
  }
LABEL_30:
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000) != 0 )
    WPP_SF_qqD(12, WPP_8ecfc4db63433714fa4cc8be4e523449_Traceguids, *v6, *a4, v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1c0004b80  mov     [rsp+arg_18], rbx
0x1c0004b85  mov     [rsp+arg_10], r8
0x1c0004b8a  push    rbp
0x1c0004b8b  push    rsi
0x1c0004b8c  push    r12
0x1c0004b8e  push    r13
0x1c0004b90  push    r14
0x1c0004b92  sub     rsp, 90h
0x1c0004b99  xor     ebp, ebp
0x1c0004b9b  mov     r13, r9
0x1c0004b9e  mov     [rsp+0B8h+var_70], rbp
0x1c0004ba3  mov     r14, r8
0x1c0004ba6  mov     [rsp+0B8h+var_78], rbp
0x1c0004bab  mov     rsi, rdx
0x1c0004bae  mov     r12, rcx
0x1c0004bb1  test    dword ptr cs:WPP_MAIN_CB.Queue, 10000h
0x1c0004bbb  mov     ebx, [rsp+0B8h+arg_20]
0x1c0004bc2  jnz     loc_1C001CC2A
0x1c0004bc8  mov     [rsp+0B8h+arg_0], rdi
0x1c0004bd0  mov     rcx, r12
0x1c0004bd3  mov     [rsp+0B8h+arg_8], r15
0x1c0004bdb  test    bl, 10h
0x1c0004bde  jz      loc_1C00050A1
0x1c0004be4  mov     rax, [rsi+78h]
0x1c0004be8  lea     r9, [rsp+0B8h+var_78]
0x1c0004bed  mov     [rsp+0B8h+var_90], rbp
0x1c0004bf2  lea     r8, [rsp+0B8h+var_70]
0x1c0004bf7  mov     edx, 1Bh
0x1c0004bfc  mov     [rsp+0B8h+Dpc], rbp
0x1c0004c01  call    cs:__guard_dispatch_icall_fptr
0x1c0004c07  mov     edi, eax
0x1c0004c09  test    eax, eax
0x1c0004c0b  js      loc_1C0004FFF
0x1c0004c11  cmp     cs:UxCompactMode, bpl
0x1c0004c18  jnz     loc_1C001CC55
0x1c0004c1e  mov     eax, gs:1A4h
0x1c0004c26  mov     rcx, cs:qword_1C0074390
0x1c0004c2d  lea     r8d, [rax+1]
0x1c0004c31  mov     edx, [rcx]
0x1c0004c33  cmp     r8d, edx
0x1c0004c36  lea     eax, [rdx-1]
0x1c0004c39  cmovb   eax, r8d
0x1c0004c3d  mov     edx, eax
0x1c0004c3f  mov     rax, [rcx+20h]
0x1c0004c43  mov     rdi, [rax+rdx*8]
0x1c0004c47  cmp     [rdi+70h], bpl
0x1c0004c4b  jnz     short loc_1C0004C55
0x1c0004c4d  mov     rdx, rdi
0x1c0004c50  call    PplpLazyInitializeLookasideList
0x1c0004c55  inc     dword ptr [rdi+14h]
0x1c0004c58  mov     rcx, rdi; ListHead
0x1c0004c5b  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0004c62  nop     dword ptr [rax+rax+00h]
0x1c0004c67  mov     rbx, rax
0x1c0004c6a  test    rax, rax
0x1c0004c6d  jz      loc_1C000503A
0x1c0004c73  test    rbx, rbx
0x1c0004c76  jz      loc_1C001CCB9
0x1c0004c7c  mov     r8d, cs:UxSslConnectionSize; Size
0x1c0004c83  xor     edx, edx; Val
0x1c0004c85  mov     rcx, rbx; void *
0x1c0004c88  call    memset
0x1c0004c8d  mov     dword ptr [rbx+14h], 1
0x1c0004c94  lea     r8, [rbx+90h]
0x1c0004c9b  mov     dword ptr [rbx+10h], 41537855h
0x1c0004ca2  xor     eax, eax
0x1c0004ca4  mov     [rbx+0D0h], rbp
0x1c0004cab  xorps   xmm0, xmm0
0x1c0004cae  mov     [rbx+0A0h], rbp
0x1c0004cb5  xor     r9d, r9d
0x1c0004cb8  mov     [rbx+0B0h], rbp
0x1c0004cbf  mov     rcx, r12
0x1c0004cc2  mov     [rbx+0C0h], rbp
0x1c0004cc9  mov     [rbx+0D8h], rbp
0x1c0004cd0  mov     [rbx+0E0h], ebp
0x1c0004cd6  lea     edx, [r9+5]
0x1c0004cda  mov     dword ptr [rbx+1F0h], 1
0x1c0004ce4  movups  xmmword ptr [rbx+18h], xmm0
0x1c0004ce8  mov     [rbx+28h], rax
0x1c0004cec  mov     dword ptr [rbx+28h], 1
0x1c0004cf3  mov     [rbx+40h], rbp
0x1c0004cf7  mov     dword ptr [rbx+40h], 1
0x1c0004cfe  mov     [rbx+30h], r12
0x1c0004d02  mov     [rbx+38h], rsi
0x1c0004d06  mov     rax, [rsi+78h]
0x1c0004d0a  mov     [rsp+0B8h+var_90], rbp
0x1c0004d0f  mov     [rsp+0B8h+Dpc], rbp
0x1c0004d14  call    cs:__guard_dispatch_icall_fptr
0x1c0004d1a  lea     r15, [rbx+0F8h]
0x1c0004d21  mov     rcx, r15; SpinLock
0x1c0004d24  call    cs:__imp_KeInitializeSpinLock
0x1c0004d2b  nop     dword ptr [rax+rax+00h]
0x1c0004d30  mov     rbp, [rbx+90h]
0x1c0004d37  lea     rsi, [rbx+100h]
0x1c0004d3e  mov     rdi, [rsp+0B8h+var_70]
0x1c0004d43  add     rbp, 10h
0x1c0004d47  test    dword ptr cs:WPP_MAIN_CB.Queue, 40000h
0x1c0004d51  jnz     loc_1C001CCD7
0x1c0004d57  xor     edx, edx; Val
0x1c0004d59  lea     rcx, [rbx+104h]; void *
0x1c0004d60  lea     r8d, [rdx+7Ch]; Size
0x1c0004d64  call    memset
0x1c0004d69  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1c0004d71  movups  xmmword ptr [rsi+68h], xmm0
0x1c0004d75  mov     [rsi+10h], r15
0x1c0004d79  xor     r15d, r15d
0x1c0004d7c  mov     [rsi+8], rbp
0x1c0004d80  movzx   r8d, r15w
0x1c0004d84  mov     byte ptr [rsi+64h], 1
0x1c0004d88  mov     dword ptr [rsi], 1
0x1c0004d8e  movzx   eax, word ptr cs:UlTimersPerBundle+2
0x1c0004d95  cmp     r15w, ax
0x1c0004d99  jnb     short loc_1C0004DC6
0x1c0004d9b  lea     r9, qword_1C0076F18
0x1c0004da2  movzx   edx, r8w
0x1c0004da6  inc     r8w
0x1c0004daa  movsxd  rax, dword ptr [r9+rdx*4]
0x1c0004dae  mov     ecx, [rdi+rax*4+0FE0h]
0x1c0004db5  mov     [rsi+rdx*4+48h], ecx
0x1c0004db9  movzx   eax, word ptr cs:UlTimersPerBundle+2
0x1c0004dc0  cmp     r8w, ax
0x1c0004dc4  jb      short loc_1C0004DA2
0x1c0004dc6  movzx   ecx, al
0x1c0004dc9  mov     eax, 1
0x1c0004dce  shl     eax, cl
0x1c0004dd0  dec     eax
0x1c0004dd2  mov     [rsi+60h], eax
0x1c0004dd5  mov     eax, 1
0x1c0004dda  lock xadd [rbp+40h], eax
0x1c0004ddf  inc     eax
0x1c0004de1  cmp     eax, 1
0x1c0004de4  jz      loc_1C000505C
0x1c0004dea  lea     rdx, [rsi+18h]
0x1c0004dee  xor     r9d, r9d
0x1c0004df1  xor     r8d, r8d
0x1c0004df4  xor     ecx, ecx
0x1c0004df6  call    cs:__imp_RtlInitializeTimerWheelEntry
0x1c0004dfd  nop     dword ptr [rax+rax+00h]
0x1c0004e02  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x1c0004e09  lea     rcx, [rbx+200h]; SpinLock
0x1c0004e10  mov     [rbx+1C0h], rbp
0x1c0004e17  mov     [rbx+1B8h], rbp
0x1c0004e1e  call    cs:__imp_KeInitializeSpinLock
0x1c0004e25  nop     dword ptr [rax+rax+00h]
0x1c0004e2a  mov     [rbx+218h], r15d
0x1c0004e31  lea     rax, [rbx+208h]
0x1c0004e38  mov     [rax+8], rax
0x1c0004e3c  lea     rcx, [rbx+290h]; SpinLock
0x1c0004e43  mov     [rax], rax
0x1c0004e46  lea     rax, [rbx+3A8h]
0x1c0004e4d  mov     dword ptr [rbx+21Ch], 0FFFFFFFFh
0x1c0004e57  mov     [rax+8], rax
0x1c0004e5b  mov     [rax], rax
0x1c0004e5e  lea     rax, [rbx+278h]
0x1c0004e65  mov     [rax+8], rax
0x1c0004e69  mov     [rax], rax
0x1c0004e6c  call    cs:__imp_KeInitializeSpinLock
0x1c0004e73  nop     dword ptr [rax+rax+00h]
0x1c0004e78  xorps   xmm0, xmm0
0x1c0004e7b  lea     rcx, [rbx+2B0h]; SListHead
0x1c0004e82  movups  xmmword ptr [rbx+380h], xmm0
0x1c0004e89  mov     [rbx+382h], r15w
0x1c0004e91  mov     [rbx+388h], r15
0x1c0004e98  call    cs:__imp_InitializeSListHead
0x1c0004e9f  nop     dword ptr [rax+rax+00h]
0x1c0004ea4  or      dword ptr [rbx+318h], 2
0x1c0004eab  lea     rax, [rbx+2F8h]
0x1c0004eb2  mov     [rax+8], rax
0x1c0004eb6  lea     rdi, [rbx+48h]
0x1c0004eba  mov     [rax], rax
0x1c0004ebd  lea     rax, [rbx+308h]
0x1c0004ec4  mov     [rax+8], rax
0x1c0004ec8  mov     [rax], rax
0x1c0004ecb  lea     rax, [rbx+440h]
0x1c0004ed2  mov     dword ptr [rax], 64735875h
0x1c0004ed8  mov     [rbx+328h], rax
0x1c0004edf  mov     [rbx+2C0h], r15
0x1c0004ee6  mov     [rbx+2D0h], r15
0x1c0004eed  mov     [rbx+2E0h], r15
0x1c0004ef4  mov     dword ptr [rbx+3A4h], 0C00h
0x1c0004efe  mov     dword ptr [rbx+29Ch], 8400h
0x1c0004f08  mov     rax, [rsp+0B8h+var_70]
0x1c0004f0d  mov     [rbx+3C0h], rax
0x1c0004f14  mov     rax, [rsp+0B8h+var_78]
0x1c0004f19  mov     [rsp+0B8h+var_70], r15
0x1c0004f1e  mov     [rbx+3B8h], rax
0x1c0004f25  mov     [rsp+0B8h+var_78], r15
0x1c0004f2a  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c0004f34  jnz     loc_1C001CD2F
0x1c0004f3a  mov     rax, [rbx+38h]
0x1c0004f3e  xor     r9d, r9d
0x1c0004f41  mov     rcx, [rbx+30h]
0x1c0004f45  mov     r8, rdi
0x1c0004f48  mov     [rsp+0B8h+var_90], r15
0x1c0004f4d  mov     [rsp+0B8h+Dpc], r15
0x1c0004f52  mov     rax, [rax+78h]
0x1c0004f56  lea     edx, [r9+3]
0x1c0004f5a  call    cs:__guard_dispatch_icall_fptr
0x1c0004f60  mov     edi, eax
0x1c0004f62  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c0004f6c  jnz     loc_1C001CD62
0x1c0004f72  test    edi, edi
0x1c0004f74  js      loc_1C001CE49
0x1c0004f7a  lea     r15, [rbx+74h]
0x1c0004f7e  lea     rbp, [rbx+58h]
0x1c0004f82  xor     edi, edi
0x1c0004f84  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c0004f8e  jnz     loc_1C001CD7C
0x1c0004f94  mov     rax, [rbx+38h]
0x1c0004f98  mov     r9, r15
0x1c0004f9b  mov     rcx, [rbx+30h]
0x1c0004f9f  mov     r8, rbp
0x1c0004fa2  mov     [rsp+0B8h+var_90], rdi
0x1c0004fa7  xor     edx, edx
0x1c0004fa9  mov     [rsp+0B8h+Dpc], rdi
0x1c0004fae  mov     rax, [rax+78h]
0x1c0004fb2  call    cs:__guard_dispatch_icall_fptr
0x1c0004fb8  mov     edi, eax
0x1c0004fba  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c0004fc4  jnz     loc_1C001CDAE
0x1c0004fca  test    edi, edi
0x1c0004fcc  js      loc_1C001CE42
0x1c0004fd2  test    dword ptr cs:WPP_MAIN_CB.Queue, 10000h
0x1c0004fdc  jnz     loc_1C001CDC8
0x1c0004fe2  mov     r14, [rsp+0B8h+arg_10]
0x1c0004fea  lea     rax, UxSslDispatch
0x1c0004ff1  mov     [r14], rbx
0x1c0004ff4  mov     [r13+0], rax
0x1c0004ff8  mov     dword ptr [rbx+40h], 2
0x1c0004fff  test    dword ptr cs:WPP_MAIN_CB.Queue, 10000h
0x1c0005009  jnz     loc_1C001CED3
0x1c000500f  mov     r15, [rsp+0B8h+arg_8]
0x1c0005017  mov     eax, edi
0x1c0005019  mov     rdi, [rsp+0B8h+arg_0]
0x1c0005021  mov     rbx, [rsp+0B8h+arg_18]
0x1c0005029  add     rsp, 90h
0x1c0005030  pop     r14
0x1c0005032  pop     r13
0x1c0005034  pop     r12
0x1c0005036  pop     rsi
0x1c0005037  pop     rbp
0x1c0005038  retn
0x1c000503a  mov     r8d, [rdi+28h]
0x1c000503e  mov     r9, rdi
0x1c0005041  mov     edx, [rdi+2Ch]
0x1c0005044  mov     ecx, [rdi+24h]
0x1c0005047  mov     rax, [rdi+30h]
0x1c000504b  inc     dword ptr [rdi+18h]
0x1c000504e  call    cs:__guard_dispatch_icall_fptr
0x1c0005054  mov     rbx, rax
0x1c0005057  jmp     loc_1C0004C73
0x1c000505c  lea     rcx, UlHotAddCommitLock; SpinLock
0x1c0005063  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c000506a  nop     dword ptr [rax+rax+00h]
0x1c000506f  mov     ecx, cs:UlMetronomeCount
0x1c0005075  movzx   edi, al
0x1c0005078  inc     ecx
0x1c000507a  mov     cs:UlMetronomeCount, ecx
0x1c0005080  cmp     ecx, 1
0x1c0005083  jz      short loc_1C00050BA
0x1c0005085  movzx   edx, dil; NewIrql
0x1c0005089  lea     rcx, UlHotAddCommitLock; SpinLock
0x1c0005090  call    cs:__imp_KeReleaseSpinLock
0x1c0005097  nop     dword ptr [rax+rax+00h]
0x1c000509c  jmp     loc_1C0004DEA
0x1c00050a1  mov     r9, r13
0x1c00050a4  mov     dword ptr [rsp+0B8h+Dpc], ebx
0x1c00050a8  mov     r8, r14
0x1c00050ab  mov     rdx, rsi
0x1c00050ae  call    UxDuoAttachConnection
0x1c00050b3  mov     edi, eax
0x1c00050b5  jmp     loc_1C0004FFF
0x1c00050ba  mov     eax, cs:UlMetronomeState
0x1c00050c0  test    eax, eax
0x1c00050c2  jz      loc_1C001CCF5
0x1c00050c8  cmp     eax, 1
0x1c00050cb  jnz     short loc_1C0005085
0x1c00050cd  mov     cs:UlMetronomeState, 2
0x1c00050d7  jmp     short loc_1C0005085
0x1c001cc2a  mov     dword ptr [rsp+0B8h+var_88], ebx
0x1c001cc2e  lea     rdx, WPP_8ecfc4db63433714fa4cc8be4e523449_Traceguids
0x1c001cc35  mov     [rsp+0B8h+var_90], r13
0x1c001cc3a  mov     ecx, 0Ah
0x1c001cc3f  mov     r9, rsi
0x1c001cc42  mov     [rsp+0B8h+Dpc], r14
0x1c001cc47  mov     r8, r12
0x1c001cc4a  call    WPP_SF_qiqqL
0x1c001cc4f  nop
0x1c001cc50  jmp     loc_1C0004BC8
0x1c001cc55  mov     rbx, cs:qword_1C0074390
0x1c001cc5c  call    cs:__imp_KeGetCurrentNodeNumber
0x1c001cc63  nop     dword ptr [rax+rax+00h]
0x1c001cc68  mov     edx, [rbx]
0x1c001cc6a  movzx   r8d, ax
0x1c001cc6e  inc     r8d
0x1c001cc71  cmp     r8d, edx
0x1c001cc74  lea     eax, [rdx-1]
0x1c001cc77  cmovb   eax, r8d
0x1c001cc7b  mov     edx, eax
0x1c001cc7d  mov     rax, [rbx+20h]
  ... truncated ...
```
