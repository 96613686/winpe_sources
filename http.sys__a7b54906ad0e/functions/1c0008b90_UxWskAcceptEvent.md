# UxWskAcceptEvent

- ea: `0x1c0008b90`
- end: `0x1c0009230`
- name: `UxWskAcceptEvent`
- size: `1696`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1c0001118`
- `0x1c0003db0`
- `0x1c0004b80`
- `0x1c0008b90`
- `0x1c000935c`
- `0x1c00096e0`
- `0x1c000a178`
- `0x1c0014194`
- `0x1c001a4b0`
- `0x1c001a548`
- `0x1c001b610`
- `0x1c001b640`
- `0x1c001b900`
- `0x1c004a3b4`
- `0x1c008f570`
- `0x1c009bed0`
- `0x1c009da34`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1c0009222`
- `ntoskrnl!KeSetEvent` at `0x1c0009222`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1c0008cf5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1c00091b7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1c0008cf5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1c00091b7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1c0008d11`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1c00091e3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1c0008d11`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1c00091e3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0008c56`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0008ee2`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c001fa6b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0008c56`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0008ee2`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c001fa6b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0008ccc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0008ccc`
- `ntoskrnl!EtwActivityIdControl` at `0x1c0008f38`
- `ntoskrnl!EtwActivityIdControl` at `0x1c0008f38`
- `ntoskrnl!IoAllocateIrp` at `0x1c0008e7f`
- `ntoskrnl!IoAllocateIrp` at `0x1c0008e7f`
- `ntoskrnl!KeReadStateEvent` at `0x1c001f976`
- `ntoskrnl!KeReadStateEvent` at `0x1c001f976`
- `ntoskrnl!KeLowerIrql` at `0x1c001fcb1`
- `ntoskrnl!KeLowerIrql` at `0x1c001fcb1`
- `ntoskrnl!KfRaiseIrql` at `0x1c001f993`
- `ntoskrnl!KfRaiseIrql` at `0x1c001f993`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0008c3c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c001fa28`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0008c3c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c001fa28`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00090eb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00090eb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0009094`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0009094`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c0008d35`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c0008f10`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c0008d35`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c0008f10`
- `HAL!KeQueryPerformanceCounter` at `0x1c0008c95`
- `HAL!KeQueryPerformanceCounter` at `0x1c0008c95`
- `fwpkclnt!FwpiGetConnectionLuid0` at `0x1c001fb40`
- `fwpkclnt!FwpiGetConnectionLuid0` at `0x1c001fb40`

## pseudocode

```c
__int64 __fastcall UxWskAcceptEvent(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct _SLIST_ENTRY *a5,
        PSLIST_ENTRY *a6,
        _QWORD *a7)
{
  PSLIST_ENTRY v9; // rbx
  __int64 v11; // rbx
  __int64 v12; // rdi
  LARGE_INTEGER PerformanceCounter; // rax
  bool v14; // zf
  __int64 v15; // rdi
  __int64 v16; // rax
  UCHAR v17; // cl
  ADDRESS_FAMILY *v18; // r14
  __int64 v19; // rax
  UCHAR v20; // cl
  ADDRESS_FAMILY *v21; // r15
  PIRP Irp; // rax
  unsigned int v23; // r8d
  unsigned int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rdi
  PSLIST_ENTRY v28; // rax
  int ConnectionLuid0; // edi
  int v30; // eax
  const UCHAR *v31; // rdx
  __int64 v32; // rax
  UCHAR v33; // cl
  __int64 v34; // rax
  __int64 Pod; // rax
  int v36; // edx
  int v37; // ecx
  int v38; // r8d
  __int64 v39; // r9
  KIRQL v40; // al
  int v41; // ecx
  KIRQL v42; // r14
  int v43; // edx
  int v44; // edx
  int v45; // r15d
  struct _SLIST_ENTRY *Next; // rax
  __int64 v47; // rcx
  __int64 v49; // r8
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 (__fastcall *v52)(__int64, __int64, __int64, __int64); // rax
  unsigned int v53; // r9d
  unsigned int v54; // r8d
  unsigned int i; // edx
  __int64 v56; // r12
  unsigned int v57; // r8d
  unsigned int v58; // eax
  __int64 v59; // rdx
  __int64 v60; // rax
  __int64 v61; // rcx
  ADDRESS_FAMILY v62; // r10
  char *v63; // rcx
  __int64 v64; // r9
  __int64 v65; // rdx
  ADDRESS_FAMILY v66; // cx
  UCHAR v67; // al
  ADDRESS_FAMILY v68; // cx
  UCHAR v69; // al
  int v70; // r9d
  int v71; // ecx
  int v72; // edx
  int v73; // ecx
  __int16 v74; // [rsp+48h] [rbp-C0h]
  __int64 v75; // [rsp+58h] [rbp-B0h] BYREF
  struct _SLIST_ENTRY *v76; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD *v77; // [rsp+68h] [rbp-A0h]
  __int128 v78; // [rsp+78h] [rbp-90h]
  __int128 v79; // [rsp+88h] [rbp-80h]
  __int128 v80; // [rsp+98h] [rbp-70h] BYREF
  __int128 v81; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v82[3]; // [rsp+B8h] [rbp-50h] BYREF
  char v83; // [rsp+D0h] [rbp-38h]
  int v84; // [rsp+D1h] [rbp-37h]
  __int16 v85; // [rsp+D5h] [rbp-33h]
  char v86; // [rsp+D7h] [rbp-31h]
  __int128 v87; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v88; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v89; // [rsp+F8h] [rbp-10h] BYREF

  v9 = 0;
  *a6 = 0;
  *a7 = 0;
  v77 = a7;
  v74 = 0;
  if ( !a5 )
  {
    ConnectionLuid0 = -1073741616;
    goto LABEL_73;
  }
  if ( !*(_QWORD *)(a1 + 24) )
  {
    ConnectionLuid0 = -1073741436;
    goto LABEL_73;
  }
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 200) + 7264LL) && !KeReadStateEvent(UxHighNonPagedPoolEvent) )
  {
    ConnectionLuid0 = -1073741258;
    goto LABEL_73;
  }
  if ( KeGetCurrentIrql() < 2u )
  {
    HIBYTE(v74) = KfRaiseIrql(2u);
    LOBYTE(v74) = 1;
  }
  v11 = *(_QWORD *)(*(_QWORD *)(a1 + 200) + 7592LL);
  v12 = *(_QWORD *)(v11 + 8LL * KeGetCurrentNodeNumber() + 8);
  ++*(_DWORD *)(v12 + 20);
  v9 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v12);
  if ( !v9 )
  {
    ++*(_DWORD *)(v12 + 24);
    v9 = (PSLIST_ENTRY)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(v12 + 48))(
                         *(unsigned int *)(v12 + 36),
                         *(unsigned int *)(v12 + 44),
                         *(unsigned int *)(v12 + 40),
                         v12);
  }
  if ( !v9 )
  {
    ConnectionLuid0 = -1073741670;
    goto LABEL_73;
  }
  LODWORD(v9[2].Next) = 1129606229;
  _InterlockedIncrement((volatile signed __int32 *)&v9[2].Next + 1);
  memset(&v9[2].Next + 1, 0, 0x1F8u);
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v14 = UlEnableThreadAffinity == 0;
  *((LARGE_INTEGER *)&v9[32].Next + 1) = PerformanceCounter;
  v9[26].Next = 0;
  v9[27].Next = 0;
  v9[28].Next = 0;
  if ( v14 )
  {
    v53 = 0;
    v54 = -1;
    for ( i = 0; i < UxNumberOfProcessors; ++i )
    {
      if ( !v54 )
        break;
      if ( *(_DWORD *)(*((_QWORD *)UlPartitions + i) + 12LL) < v54 )
      {
        v53 = i;
        v54 = *(_DWORD *)(*((_QWORD *)UlPartitions + i) + 12LL);
      }
    }
    v15 = *((_QWORD *)UlPartitions + v53);
  }
  else
  {
    v15 = *((_QWORD *)UlPartitions + KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors);
  }
  v9[29].Next = (struct _SLIST_ENTRY *)v15;
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v15);
  if ( ++*(_DWORD *)(v15 + 12) == 1 )
  {
    KeAcquireSpinLockAtDpcLevel(&UlPartitionsSpinLock);
    if ( ++UlPartitionsActiveCount == 1 )
      KeSetEvent(&UlScavengerRefreshEvent, 0, 0);
    KeReleaseSpinLockFromDpcLevel(&UlPartitionsSpinLock);
  }
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v15);
  *(struct _SLIST_ENTRY *)((char *)&v9[2] + 8) = 0;
  *((_QWORD *)&v9[3].Next + 1) = 0;
  *((_DWORD *)&v9[3].Next + 2) = 1;
  KeInitializeSpinLock((PKSPIN_LOCK)&v9[7].Next + 1);
  v9[15].Next = 0;
  *((_QWORD *)&v9[8].Next + 1) = v9 + 8;
  v9[8].Next = v9 + 8;
  LODWORD(v9[32].Next) = 2;
  v9[13].Next = (struct _SLIST_ENTRY *)a1;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
  v16 = *a3;
  if ( (unsigned int)v16 >= 0x23 )
    v17 = 0;
  else
    v17 = sockaddr_size[v16];
  v18 = (ADDRESS_FAMILY *)&v9[9].Next + 2;
  memmove((char *)&v9[9].Next + 4, a3, v17);
  v19 = *a4;
  if ( (unsigned int)v19 >= 0x23 )
    v20 = 0;
  else
    v20 = sockaddr_size[v19];
  v21 = (ADDRESS_FAMILY *)&v9[11];
  memmove(&v9[11], a4, v20);
  if ( *v18 == 23
    && !*((_WORD *)&v9[9].Next + 6)
    && !*((_WORD *)&v9[9].Next + 7)
    && !LOWORD(v9[10].Next)
    && !WORD1(v9[10].Next)
    && !WORD2(v9[10].Next)
    && HIWORD(v9[10].Next) == 0xFFFF )
  {
    *v18 = 2;
    *((_DWORD *)&v9[9].Next + 2) = *((_DWORD *)&v9[10].Next + 2);
    *(struct _SLIST_ENTRY **)((char *)&v9[9].Next + 12) = 0;
  }
  if ( *v21 == 23
    && !*((_WORD *)&v9[11].Next + 4)
    && !*((_WORD *)&v9[11].Next + 5)
    && !*((_WORD *)&v9[11].Next + 6)
    && !*((_WORD *)&v9[11].Next + 7)
    && !LOWORD(v9[12].Next)
    && WORD1(v9[12].Next) == 0xFFFF )
  {
    *v21 = 2;
    HIDWORD(v9[11].Next) = HIDWORD(v9[12].Next);
    *((_QWORD *)&v9[11].Next + 1) = 0;
  }
  Irp = IoAllocateIrp(1, 0);
  v9[6].Next = (struct _SLIST_ENTRY *)Irp;
  if ( !Irp )
  {
    ConnectionLuid0 = -1073741670;
    goto LABEL_73;
  }
  if ( !UxCompactMode )
  {
    v23 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
    v24 = *(_DWORD *)qword_1C0074330 - 1;
    if ( v23 < *(_DWORD *)qword_1C0074330 )
      v24 = v23;
    v25 = v24;
    v26 = *(_QWORD *)(qword_1C0074330 + 32);
    v27 = *(_QWORD *)(v26 + 8 * v25);
    if ( !*(_BYTE *)(v27 + 112) )
      PplpLazyInitializeLookasideList(qword_1C0074330, *(_QWORD *)(v26 + 8 * v25));
    ++*(_DWORD *)(v27 + 20);
    v28 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v27);
    if ( v28 )
      goto LABEL_39;
LABEL_68:
    v49 = *(unsigned int *)(v27 + 40);
    v50 = *(unsigned int *)(v27 + 44);
    v51 = *(unsigned int *)(v27 + 36);
    v52 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v27 + 48);
    ++*(_DWORD *)(v27 + 24);
    v28 = (PSLIST_ENTRY)v52(v51, v50, v49, v27);
    goto LABEL_39;
  }
  v56 = qword_1C0074330;
  v57 = KeGetCurrentNodeNumber() + 1;
  v58 = *(_DWORD *)v56 - 1;
  if ( v57 < *(_DWORD *)v56 )
    v58 = v57;
  v59 = v58;
  v60 = *(_QWORD *)(v56 + 32);
  v27 = *(_QWORD *)(v60 + 8 * v59);
  if ( !*(_BYTE *)(v27 + 112) )
    PplpLazyInitializeLookasideList(v56, *(_QWORD *)(v60 + 8 * v59));
  ++*(_DWORD *)(v27 + 20);
  v28 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v27);
  if ( !v28 )
    goto LABEL_68;
LABEL_39:
  *((_QWORD *)&v9[6].Next + 1) = v28;
  if ( !v28 )
  {
    ConnectionLuid0 = -1073741670;
LABEL_73:
    if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 200) + 7336LL), 1u) )
      UlEnablePeriodicScavenger(*(_QWORD *)(a1 + 200) + 7344LL);
    goto LABEL_62;
  }
  *((_QWORD *)&v9[4].Next + 1) = 1;
  KeInitializeSpinLock((PKSPIN_LOCK)&v9[4]);
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 200) + 1568LL) )
    EtwActivityIdControl(3u, (LPGUID)&v9[25]);
  ConnectionLuid0 = 0;
  if ( (*v18 != 23
     || *((_DWORD *)&v9[9].Next + 3) != *(_DWORD *)in6addr_teredoprefix.u.Byte
     && *((_DWORD *)&v9[9].Next + 3) != *(_DWORD *)in6addr_teredoprefix_old.u.Byte)
    && HIDWORD(v9[13].Next[11].Next) )
  {
    v61 = 184;
    v62 = *v18;
    if ( *v21 != 23 )
      v61 = 180;
    v63 = (char *)v9 + v61;
    if ( v62 == 23 )
    {
      v64 = *((unsigned int *)&v9[10].Next + 3);
      v65 = 156;
    }
    else
    {
      v64 = 0;
      v65 = 152;
    }
    ConnectionLuid0 = FwpiGetConnectionLuid0(
                        6,
                        v62,
                        (char *)v9 + v65,
                        v64,
                        HIWORD(v9[9].Next),
                        v63,
                        WORD1(v9[11].Next),
                        &v9[14]);
    if ( ConnectionLuid0 >= 0 )
      *((_BYTE *)&v9[14].Next + 8) = 1;
  }
  if ( ConnectionLuid0 < 0 )
    goto LABEL_73;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x400000) != 0 )
  {
    v66 = *v21;
    v78 = (unsigned __int64)&v9[11];
    v67 = SOCKADDR_SIZE(v66);
    v68 = *v18;
    *((_QWORD *)&v78 + 1) = v67;
    v80 = v78;
    v79 = (unsigned __int64)v18;
    v69 = SOCKADDR_SIZE(v68);
    v70 = *(_DWORD *)(a1 + 12);
    WORD4(v79) = v69;
    v81 = v79;
    WPP_SF_qD_SOCKADDR__SOCKADDR_(v71, v69, (_DWORD)v9, v70, (__int64)&v81, (__int64)&v80);
  }
  _InterlockedIncrement((volatile signed __int32 *)&v9[2].Next + 1);
  v30 = *(_DWORD *)(a1 + 12);
  v75 = 0;
  v76 = 0;
  ConnectionLuid0 = UxSslAttachConnection(
                      (_DWORD)v9,
                      (unsigned int)UxTlDispatch,
                      (unsigned int)&v75,
                      (unsigned int)&v76,
                      v30);
  if ( ConnectionLuid0 < 0 )
  {
    if ( (WPP_MAIN_CB.DeviceType & 0x400000) != 0 )
      WPP_SF_qD(11, WPP_ba8bc14f277239e038f542b60538f85e_Traceguids, v9, (unsigned int)ConnectionLuid0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v9[2].Next + 1, 0xFFFFFFFF) == 1 )
      UxTlDestroyConnection(v9);
  }
  else
  {
    *((_QWORD *)&v9[2].Next + 1) = v75;
    v9[3].Next = v76;
    *((_DWORD *)&v9[3].Next + 2) = 2;
    v31 = sockaddr_size;
    *a6 = v9;
    v87 = 0;
    v88 = 0;
    *v77 = UxWskClientConnDispatch;
    v9[5].Next = a5;
    v32 = *v18;
    v89 = 0;
    if ( (unsigned int)v32 >= 0x23 )
      v33 = 0;
    else
      v33 = sockaddr_size[v32];
    v34 = *v21;
    if ( (unsigned int)v34 >= 0x23 )
      LOBYTE(v31) = 0;
    else
      v31 = (const UCHAR *)sockaddr_size[v34];
    Pod = UxWskGetPod(v9, v31, v33);
    if ( *(_BYTE *)(Pod + 1568) != (_BYTE)v39 )
    {
      v82[2] = Pod;
      v82[0] = v9 + 25;
      v84 = v39;
      v85 = v39;
      v86 = v39;
      v82[1] = v39;
      v83 = v39;
      McTemplateK0pqbr1qbr3_UlEtwWriteEventWrapper(
        v37,
        v36,
        (unsigned int)v82,
        (_DWORD)v9,
        v38,
        (__int64)&v9[9].Next + 4,
        (unsigned __int8)v36,
        (__int64)&v9[11]);
    }
    v40 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&v9[4]);
    v41 = *((_DWORD *)&v9[4].Next + 3);
    v42 = v40;
    v43 = *((_DWORD *)&v9[4].Next + 2);
    LODWORD(v87) = v43;
    DWORD2(v87) = v41;
    if ( !v41
      && (v44 = v43 | 0x4002, *((_DWORD *)&v9[4].Next + 3) = 2, *((_DWORD *)&v9[4].Next + 2) = v44, (v44 & 0x8000) != 0) )
    {
      v45 = -1073741301;
    }
    else
    {
      v45 = 0;
    }
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x400000) != 0 )
    {
      UxpTlWppCapturePostState(v9, &v87);
      WPP_SF_qdLsLs(v73, v72, (_DWORD)v9, v45, SBYTE8(v87), (__int64)&v88, SBYTE12(v87), (__int64)&v89);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)&v9[4], v42);
    if ( v45 < 0 )
    {
      if ( (WPP_MAIN_CB.DeviceType & 0x400000) != 0 )
        WPP_SF_qD(12, WPP_ba8bc14f277239e038f542b60538f85e_Traceguids, v9, (unsigned int)ConnectionLuid0);
    }
    else
    {
      Next = v9[3].Next;
      v47 = *((_QWORD *)&v9[2].Next + 1);
      *((_DWORD *)&v9[3].Next + 2) = 3;
      (*((void (__fastcall **)(__int64))&Next[1].Next + 1))(v47);
      v9 = 0;
    }
  }
  if ( ConnectionLuid0 < 0 )
    goto LABEL_73;
LABEL_62:
  if ( v9 )
    UxTlCleanupConnection(v9, 0);
  if ( (_BYTE)v74 )
    KeLowerIrql(HIBYTE(v74));
  if ( ConnectionLuid0 < 0 )
    return 3221225680LL;
  else
    return 0;
}

```

## disassembly

```asm
0x1c0008b90  mov     r11, rsp
0x1c0008b93  push    rbp
0x1c0008b94  lea     rbp, [r11-48h]
0x1c0008b98  sub     rsp, 140h
0x1c0008b9f  mov     rax, cs:__security_cookie
0x1c0008ba6  xor     rax, rsp
0x1c0008ba9  mov     [rbp+40h+var_40], rax
0x1c0008bad  mov     rax, [rbp+40h+arg_28]
0x1c0008bb1  mov     [r11+10h], rbx
0x1c0008bb5  mov     [r11-10h], rsi
0x1c0008bb9  mov     [r11-18h], rdi
0x1c0008bbd  mov     [r11-20h], r12
0x1c0008bc1  mov     r12, r9
0x1c0008bc4  mov     [r11-28h], r13
0x1c0008bc8  mov     r13, rcx
0x1c0008bcb  mov     rcx, [rbp+40h+arg_30]
0x1c0008bd2  mov     [r11-30h], r14
0x1c0008bd6  xor     r14d, r14d
0x1c0008bd9  mov     ebx, r14d
0x1c0008bdc  mov     [r11-38h], r15
0x1c0008be0  mov     r15, r8
0x1c0008be3  mov     [rax], r14
0x1c0008be6  mov     [rcx], r14
0x1c0008be9  mov     [rsp+140h+var_F8], rax
0x1c0008bee  mov     [rsp+140h+var_E0], rcx
0x1c0008bf3  mov     byte ptr [rsp+140h+var_100], bl
0x1c0008bf7  mov     byte ptr [rsp+140h+var_100+1], bl
0x1c0008bfb  cmp     [rbp+40h+arg_20], r14
0x1c0008bff  jz      loc_1C001F92A
0x1c0008c05  cmp     [r13+18h], rbx
0x1c0008c09  jz      loc_1C001F968
0x1c0008c0f  mov     rax, [r13+0C8h]
0x1c0008c16  cmp     [rax+1C60h], bl
0x1c0008c1c  jnz     loc_1C001F96F
0x1c0008c22  mov     rax, cr8
0x1c0008c26  cmp     al, 2
0x1c0008c28  jb      loc_1C001F991
0x1c0008c2e  mov     rcx, [r13+0C8h]
0x1c0008c35  mov     rbx, [rcx+1DA8h]
0x1c0008c3c  call    cs:__imp_KeGetCurrentNodeNumber
0x1c0008c43  nop     dword ptr [rax+rax+00h]
0x1c0008c48  movzx   ecx, ax
0x1c0008c4b  mov     rdi, [rbx+rcx*8+8]
0x1c0008c50  mov     rcx, rdi; ListHead
0x1c0008c53  inc     dword ptr [rdi+14h]
0x1c0008c56  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0008c5d  nop     dword ptr [rax+rax+00h]
0x1c0008c62  mov     rbx, rax
0x1c0008c65  test    rax, rax
0x1c0008c68  jz      loc_1C00091F4
0x1c0008c6e  test    rbx, rbx
0x1c0008c71  jz      loc_1C001F9AD
0x1c0008c77  mov     dword ptr [rbx+20h], 43546C55h
0x1c0008c7e  lock inc dword ptr [rbx+24h]
0x1c0008c82  xor     edx, edx; Val
0x1c0008c84  lea     rcx, [rbx+28h]; void *
0x1c0008c88  mov     r8d, 1F8h; Size
0x1c0008c8e  call    memset
0x1c0008c93  xor     ecx, ecx; PerformanceFrequency
0x1c0008c95  call    cs:__imp_KeQueryPerformanceCounter
0x1c0008c9c  nop     dword ptr [rax+rax+00h]
0x1c0008ca1  cmp     cs:UlEnableThreadAffinity, r14b
0x1c0008ca8  mov     [rbx+208h], rax
0x1c0008caf  mov     [rbx+1A0h], r14
0x1c0008cb6  mov     [rbx+1B0h], r14
0x1c0008cbd  mov     [rbx+1C0h], r14
0x1c0008cc4  jz      loc_1C001F9B7
0x1c0008cca  xor     ecx, ecx; ProcNumber
0x1c0008ccc  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1c0008cd3  nop     dword ptr [rax+rax+00h]
0x1c0008cd8  xor     edx, edx
0x1c0008cda  div     cs:UxNumberOfProcessors
0x1c0008ce0  mov     rax, cs:UlPartitions
0x1c0008ce7  mov     rdi, [rax+rdx*8]
0x1c0008ceb  mov     rcx, rdi; SpinLock
0x1c0008cee  mov     [rbx+1D0h], rdi
0x1c0008cf5  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1c0008cfc  nop     dword ptr [rax+rax+00h]
0x1c0008d01  inc     dword ptr [rdi+0Ch]
0x1c0008d04  cmp     dword ptr [rdi+0Ch], 1
0x1c0008d08  jz      loc_1C00091B0
0x1c0008d0e  mov     rcx, rdi; SpinLock
0x1c0008d11  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1c0008d18  nop     dword ptr [rax+rax+00h]
0x1c0008d1d  xorps   xmm0, xmm0
0x1c0008d20  lea     rcx, [rbx+78h]; SpinLock
0x1c0008d24  movups  xmmword ptr [rbx+28h], xmm0
0x1c0008d28  xor     eax, eax
0x1c0008d2a  mov     [rbx+38h], rax
0x1c0008d2e  mov     dword ptr [rbx+38h], 1
0x1c0008d35  call    cs:__imp_KeInitializeSpinLock
0x1c0008d3c  nop     dword ptr [rax+rax+00h]
0x1c0008d41  lea     rax, [rbx+80h]
0x1c0008d48  mov     [rbx+0F0h], r14
0x1c0008d4f  mov     [rax+8], rax
0x1c0008d53  mov     [rax], rax
0x1c0008d56  mov     eax, 2
0x1c0008d5b  mov     [rbx+200h], eax
0x1c0008d61  mov     [rbx+0D0h], r13
0x1c0008d68  lock inc dword ptr [r13+8]
0x1c0008d6d  movzx   eax, word ptr [r15]
0x1c0008d71  lea     rdi, sockaddr_size
0x1c0008d78  cmp     eax, 23h ; '#'
0x1c0008d7b  jnb     loc_1C001FA09
0x1c0008d81  movzx   ecx, byte ptr [rax+rdi]
0x1c0008d85  movzx   r8d, cl; Size
0x1c0008d89  lea     r14, [rbx+94h]
0x1c0008d90  mov     rcx, r14; void *
0x1c0008d93  mov     rdx, r15; Src
0x1c0008d96  call    memmove
0x1c0008d9b  movzx   eax, word ptr [r12]
0x1c0008da0  cmp     eax, 23h ; '#'
0x1c0008da3  jnb     loc_1C001FA10
0x1c0008da9  movzx   ecx, byte ptr [rax+rdi]
0x1c0008dad  movzx   r8d, cl; Size
0x1c0008db1  lea     r15, [rbx+0B0h]
0x1c0008db8  mov     rcx, r15; void *
0x1c0008dbb  mov     rdx, r12; Src
0x1c0008dbe  call    memmove
0x1c0008dc3  mov     ecx, 17h
0x1c0008dc8  mov     edx, 0FFFFh
0x1c0008dcd  lea     r8d, [rcx-15h]
0x1c0008dd1  cmp     cx, [r14]
0x1c0008dd5  jnz     short loc_1C0008E26
0x1c0008dd7  cmp     word ptr [rbx+9Ch], 0
0x1c0008ddf  jnz     short loc_1C0008E26
0x1c0008de1  cmp     word ptr [rbx+9Eh], 0
0x1c0008de9  jnz     short loc_1C0008E26
0x1c0008deb  cmp     word ptr [rbx+0A0h], 0
0x1c0008df3  jnz     short loc_1C0008E26
0x1c0008df5  cmp     word ptr [rbx+0A2h], 0
0x1c0008dfd  jnz     short loc_1C0008E26
0x1c0008dff  cmp     word ptr [rbx+0A4h], 0
0x1c0008e07  jnz     short loc_1C0008E26
0x1c0008e09  cmp     [rbx+0A6h], dx
0x1c0008e10  jnz     short loc_1C0008E26
0x1c0008e12  mov     [r14], r8w
0x1c0008e16  mov     eax, [rbx+0A8h]
0x1c0008e1c  mov     [r14+4], eax
0x1c0008e20  xor     eax, eax
0x1c0008e22  mov     [r14+8], rax
0x1c0008e26  cmp     cx, [r15]
0x1c0008e2a  jnz     short loc_1C0008E7B
0x1c0008e2c  cmp     word ptr [rbx+0B8h], 0
0x1c0008e34  jnz     short loc_1C0008E7B
0x1c0008e36  cmp     word ptr [rbx+0BAh], 0
0x1c0008e3e  jnz     short loc_1C0008E7B
0x1c0008e40  cmp     word ptr [rbx+0BCh], 0
0x1c0008e48  jnz     short loc_1C0008E7B
0x1c0008e4a  cmp     word ptr [rbx+0BEh], 0
0x1c0008e52  jnz     short loc_1C0008E7B
0x1c0008e54  cmp     word ptr [rbx+0C0h], 0
0x1c0008e5c  jnz     short loc_1C0008E7B
0x1c0008e5e  cmp     [rbx+0C2h], dx
0x1c0008e65  jnz     short loc_1C0008E7B
0x1c0008e67  mov     [r15], r8w
0x1c0008e6b  mov     eax, [rbx+0C4h]
0x1c0008e71  mov     [r15+4], eax
0x1c0008e75  xor     eax, eax
0x1c0008e77  mov     [r15+8], rax
0x1c0008e7b  xor     edx, edx; ChargeQuota
0x1c0008e7d  mov     cl, 1; StackSize
0x1c0008e7f  call    cs:__imp_IoAllocateIrp
0x1c0008e86  nop     dword ptr [rax+rax+00h]
0x1c0008e8b  mov     [rbx+60h], rax
0x1c0008e8f  test    rax, rax
0x1c0008e92  jz      loc_1C001FA17
0x1c0008e98  cmp     cs:UxCompactMode, 0
0x1c0008e9f  jnz     loc_1C001FA21
0x1c0008ea5  mov     eax, gs:1A4h
0x1c0008ead  mov     rcx, cs:qword_1C0074330
0x1c0008eb4  lea     r8d, [rax+1]
0x1c0008eb8  mov     edx, [rcx]
0x1c0008eba  cmp     r8d, edx
0x1c0008ebd  lea     eax, [rdx-1]
0x1c0008ec0  cmovb   eax, r8d
0x1c0008ec4  mov     edx, eax
0x1c0008ec6  mov     rax, [rcx+20h]
0x1c0008eca  mov     rdi, [rax+rdx*8]
0x1c0008ece  cmp     byte ptr [rdi+70h], 0
0x1c0008ed2  jnz     short loc_1C0008EDC
0x1c0008ed4  mov     rdx, rdi
0x1c0008ed7  call    PplpLazyInitializeLookasideList
0x1c0008edc  inc     dword ptr [rdi+14h]
0x1c0008edf  mov     rcx, rdi; ListHead
0x1c0008ee2  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0008ee9  nop     dword ptr [rax+rax+00h]
0x1c0008eee  test    rax, rax
0x1c0008ef1  jz      loc_1C0009191
0x1c0008ef7  mov     [rbx+68h], rax
0x1c0008efb  test    rax, rax
0x1c0008efe  jz      loc_1C001FA85
0x1c0008f04  lea     rcx, [rbx+40h]; SpinLock
0x1c0008f08  mov     qword ptr [rbx+48h], 1
0x1c0008f10  call    cs:__imp_KeInitializeSpinLock
0x1c0008f17  nop     dword ptr [rax+rax+00h]
0x1c0008f1c  mov     rax, [r13+0C8h]
0x1c0008f23  cmp     byte ptr [rax+620h], 0
0x1c0008f2a  jz      short loc_1C0008F44
0x1c0008f2c  lea     rdx, [rbx+190h]; ActivityId
0x1c0008f33  mov     ecx, 3; ControlCode
0x1c0008f38  call    cs:__imp_EtwActivityIdControl
0x1c0008f3f  nop     dword ptr [rax+rax+00h]
0x1c0008f44  xor     edx, edx
0x1c0008f46  cmp     word ptr [r14], 17h
0x1c0008f4b  mov     edi, edx
0x1c0008f4d  jz      loc_1C001FA8F
0x1c0008f53  mov     rax, [rbx+0D0h]
0x1c0008f5a  mov     ecx, [rax+0B4h]
0x1c0008f60  test    ecx, ecx
0x1c0008f62  jnz     loc_1C001FAD9
0x1c0008f68  test    edi, edi
0x1c0008f6a  js      loc_1C001F92F
0x1c0008f70  test    dword ptr cs:WPP_MAIN_CB.Queue, 400000h
0x1c0008f7a  jnz     loc_1C001FB64
0x1c0008f80  lock inc dword ptr [rbx+24h]
0x1c0008f84  mov     eax, [r13+0Ch]
0x1c0008f88  lea     r9, [rsp+140h+var_E8]
0x1c0008f8d  mov     [rsp+140h+var_F0], rdx
0x1c0008f92  lea     r8, [rsp+140h+var_F0]
0x1c0008f97  mov     [rsp+140h+var_E8], rdx
0x1c0008f9c  mov     rcx, rbx
0x1c0008f9f  lea     rdx, UxTlDispatch
0x1c0008fa6  mov     dword ptr [rsp+140h+var_120], eax
0x1c0008faa  call    UxSslAttachConnection
0x1c0008faf  mov     edi, eax
0x1c0008fb1  test    eax, eax
0x1c0008fb3  js      short loc_1C0008FCE
0x1c0008fb5  mov     rax, [rsp+140h+var_F0]
0x1c0008fba  mov     [rbx+28h], rax
0x1c0008fbe  mov     rax, [rsp+140h+var_E8]
0x1c0008fc3  mov     [rbx+30h], rax
0x1c0008fc7  mov     dword ptr [rbx+38h], 2
0x1c0008fce  test    edi, edi
0x1c0008fd0  js      loc_1C001FBD5
0x1c0008fd6  mov     rax, [rsp+140h+var_F8]
0x1c0008fdb  lea     rcx, UxWskClientConnDispatch
0x1c0008fe2  xorps   xmm0, xmm0
0x1c0008fe5  lea     rdx, sockaddr_size
0x1c0008fec  xor     r9d, r9d
0x1c0008fef  mov     dword ptr [rsp+140h+var_F8], r9d
0x1c0008ff4  mov     [rax], rbx
0x1c0008ff7  mov     rax, [rsp+140h+var_E0]
0x1c0008ffc  movups  [rbp+40h+var_70], xmm0
0x1c0009000  movups  [rbp+40h+var_60], xmm0
0x1c0009004  mov     [rax], rcx
0x1c0009007  mov     rax, [rbp+40h+arg_20]
0x1c000900b  mov     [rbx+50h], rax
0x1c000900f  movzx   eax, word ptr [r14]
0x1c0009013  movups  [rbp+40h+var_50], xmm0
0x1c0009017  cmp     eax, 23h ; '#'
0x1c000901a  jnb     loc_1C001FC19
0x1c0009020  movzx   ecx, byte ptr [rax+rdx]
0x1c0009024  movzx   eax, word ptr [r15]
0x1c0009028  movzx   r8d, cl
0x1c000902c  cmp     eax, 23h ; '#'
0x1c000902f  jnb     loc_1C001FC20
0x1c0009035  movzx   edx, byte ptr [rax+rdx]
0x1c0009039  mov     rcx, rbx
0x1c000903c  call    UxWskGetPod
0x1c0009041  cmp     [rax+620h], r9b
0x1c0009048  jz      short loc_1C0009090
0x1c000904a  mov     [rbp+40h+var_80], rax
0x1c000904e  lea     rax, [rbx+190h]
0x1c0009055  mov     qword ptr [rsp+140h+var_108], r15
0x1c000905a  mov     [rbp+40h+var_90], rax
0x1c000905e  movzx   eax, dl
0x1c0009061  mov     dword ptr [rsp+140h+var_110], eax
0x1c0009065  mov     [rbp+40h+var_77], r9d
0x1c0009069  mov     [rbp+40h+var_73], r9w
0x1c000906e  mov     [rbp+40h+var_71], r9b
0x1c0009072  mov     [rbp+40h+var_88], r9
0x1c0009076  mov     [rbp+40h+var_78], r9b
0x1c000907a  mov     r9, rbx
0x1c000907d  mov     qword ptr [rsp+140h+var_118], r14
0x1c0009082  mov     dword ptr [rsp+140h+var_120], r8d
0x1c0009087  lea     r8, [rbp+40h+var_90]
0x1c000908b  call    McTemplateK0pqbr1qbr3_UlEtwWriteEventWrapper
0x1c0009090  lea     rcx, [rbx+40h]; SpinLock
0x1c0009094  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c000909b  nop     dword ptr [rax+rax+00h]
0x1c00090a0  mov     ecx, [rbx+4Ch]
0x1c00090a3  movzx   r14d, al
0x1c00090a7  mov     edx, [rbx+48h]
0x1c00090aa  mov     dword ptr [rbp+40h+var_70], edx
0x1c00090ad  mov     dword ptr [rbp+40h+var_70+8], ecx
0x1c00090b0  test    ecx, ecx
0x1c00090b2  jnz     short loc_1C00090CE
0x1c00090b4  or      edx, 4002h
0x1c00090ba  mov     dword ptr [rbx+4Ch], 2
0x1c00090c1  mov     [rbx+48h], edx
0x1c00090c4  bt      edx, 0Fh
0x1c00090c8  jb      loc_1C001FC27
0x1c00090ce  mov     r15d, dword ptr [rsp+140h+var_F8]
0x1c00090d3  test    dword ptr cs:WPP_MAIN_CB.Queue, 400000h
0x1c00090dd  jnz     loc_1C001FC32
0x1c00090e3  movzx   edx, r14b; NewIrql
0x1c00090e7  lea     rcx, [rbx+40h]; SpinLock
0x1c00090eb  call    cs:__imp_KeReleaseSpinLock
0x1c00090f2  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
