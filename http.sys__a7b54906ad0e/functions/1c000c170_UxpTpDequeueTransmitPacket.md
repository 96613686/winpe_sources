# UxpTpDequeueTransmitPacket

- ea: `0x1c000c170`
- end: `0x1c000c78c`
- name: `UxpTpDequeueTransmitPacket`
- size: `1564`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c000b920`
- `0x1c000bda0`
- `0x1c00c1c80`
- `0x1c00c1f40`
- `0x1c0138170`

## callees

- `0x1c0001118`
- `0x1c0001ae0`
- `0x1c000c170`
- `0x1c000c7b0`
- `0x1c001b610`
- `0x1c004d2d4`
- `0x1c00a9970`
- `0x1c00d6070`
- `0x1c00d60c4`
- `0x1c0116320`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c000c544`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c000c544`
- `ntoskrnl!ExQueryDepthSList` at `0x1c000c514`
- `ntoskrnl!ExQueryDepthSList` at `0x1c000c514`
- `ntoskrnl!KeReadStateEvent` at `0x1c000c267`
- `ntoskrnl!KeReadStateEvent` at `0x1c000c723`
- `ntoskrnl!KeReadStateEvent` at `0x1c000c759`
- `ntoskrnl!KeReadStateEvent` at `0x1c00224f9`
- `ntoskrnl!KeReadStateEvent` at `0x1c000c267`
- `ntoskrnl!KeReadStateEvent` at `0x1c000c723`
- `ntoskrnl!KeReadStateEvent` at `0x1c000c759`
- `ntoskrnl!KeReadStateEvent` at `0x1c00224f9`
- `ntoskrnl!KeBugCheckEx` at `0x1c000c67a`
- `ntoskrnl!KeBugCheckEx` at `0x1c00226fd`
- `ntoskrnl!KeBugCheckEx` at `0x1c00227e3`
- `ntoskrnl!KeBugCheckEx` at `0x1c002280e`
- `ntoskrnl!KeBugCheckEx` at `0x1c000c67a`
- `ntoskrnl!KeBugCheckEx` at `0x1c00226fd`
- `ntoskrnl!KeBugCheckEx` at `0x1c00227e3`
- `ntoskrnl!KeBugCheckEx` at `0x1c002280e`
- `ntoskrnl!PsReturnPoolQuota` at `0x1c000c469`
- `ntoskrnl!PsReturnPoolQuota` at `0x1c000c469`
- `ntoskrnl!ObfDereferenceObject` at `0x1c000c487`
- `ntoskrnl!ObfDereferenceObject` at `0x1c000c49c`
- `ntoskrnl!ObfDereferenceObject` at `0x1c000c487`
- `ntoskrnl!ObfDereferenceObject` at `0x1c000c49c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c002278a`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c002278a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c000c2b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c000c2b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c000c1b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c000c1b1`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c00226ae`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c00226ae`

## pseudocode

```c
volatile signed __int32 *__fastcall UxpTpDequeueTransmitPacket(PKSPIN_LOCK SpinLock, unsigned int a2, int a3, char a4)
{
  __int64 v4; // rdi
  char v8; // r14
  char v9; // r13
  KIRQL v10; // r12
  KSPIN_LOCK v11; // rcx
  KSPIN_LOCK *v12; // rdx
  __int64 *v13; // rax
  unsigned int v14; // edi
  PKSPIN_LOCK v15; // rax
  __int64 *v16; // rcx
  LONG v17; // eax
  unsigned int v18; // ecx
  KSPIN_LOCK v19; // rsi
  PKSPIN_LOCK v20; // rcx
  __int64 v21; // r9
  volatile signed __int32 *result; // rax
  bool v23; // zf
  __int64 v24; // rcx
  volatile signed __int32 *v25; // rdi
  __int16 v26; // ax
  __int64 v27; // r8
  __int64 v28; // rcx
  unsigned int v29; // r9d
  unsigned int v30; // edx
  __int64 v31; // r11
  __int64 v32; // r8
  unsigned int v33; // r10d
  int *v34; // rcx
  int v35; // eax
  __int64 v36; // rsi
  _QWORD **v37; // r9
  _QWORD *v38; // rcx
  void (__fastcall *v39)(_QWORD, _QWORD, _QWORD); // rax
  PEPROCESS v40; // rcx
  void *v41; // rcx
  __int64 v42; // rsi
  __int64 v43; // rcx
  unsigned int v44; // r8d
  unsigned int v45; // eax
  __int64 v46; // rsi
  __int16 v47; // ax
  __int64 v48; // rdx
  KSPIN_LOCK v49; // rax
  KSPIN_LOCK v50; // r15
  int v51; // eax
  __int64 v52; // rdx
  __int16 v53; // ax
  KSPIN_LOCK v54; // rcx
  bool v55; // al
  LONG StateEvent; // eax
  unsigned int v57; // ecx
  unsigned int v58; // edx
  unsigned __int64 v59; // rax
  LONG v60; // eax
  unsigned int v61; // ecx
  PKSPIN_LOCK *v62; // rcx
  KSPIN_LOCK v63; // rcx
  PKSPIN_LOCK v64; // rax
  KSPIN_LOCK v65; // rdx
  __int64 *v66; // rdx
  __int64 **v67; // rax
  __int64 v68; // rsi
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v70; // r9
  __int64 v71; // rcx
  __int64 v72; // r14
  unsigned int v73; // r8d
  unsigned int v74; // eax
  __int64 v75; // [rsp+28h] [rbp-38h]
  __int64 v76; // [rsp+30h] [rbp-30h] BYREF
  __int64 *v77; // [rsp+38h] [rbp-28h]
  __int128 v78; // [rsp+40h] [rbp-20h] BYREF
  __int128 v79; // [rsp+50h] [rbp-10h] BYREF
  __int64 v80; // [rsp+A0h] [rbp+40h] BYREF

  v4 = a2;
  v77 = &v76;
  v80 = 0;
  v76 = (__int64)&v76;
  v8 = 0;
  v9 = 0;
  v10 = KeAcquireSpinLockRaiseToDpc(SpinLock);
  if ( a3 )
    *((_DWORD *)SpinLock + 4) = a3;
  if ( (_DWORD)v4 )
  {
    SpinLock[3] -= v4;
    v23 = (*((_DWORD *)SpinLock + 8))-- == 1;
    if ( v23 )
      v8 = 1;
  }
  if ( *((_BYTE *)SpinLock + 104) )
    goto LABEL_19;
  if ( !a4 && !a3 )
  {
    v11 = SpinLock[11];
    SpinLock[11] = 0;
    v12 = (KSPIN_LOCK *)(v11 + 24);
    if ( *(_DWORD *)(v11 + 132) == *(_DWORD *)(v11 + 128) )
    {
      --*((_DWORD *)SpinLock + 14);
      SpinLock[8] -= *(_QWORD *)(v11 + 200);
      if ( (*(_BYTE *)(v11 + 96) & 8) != 0 )
      {
        v62 = (PKSPIN_LOCK *)SpinLock[10];
        if ( *v62 != SpinLock + 9 )
          goto LABEL_157;
        *v12 = (KSPIN_LOCK)(SpinLock + 9);
        v12[1] = (KSPIN_LOCK)v62;
        *v62 = v12;
        SpinLock[10] = (KSPIN_LOCK)v12;
      }
      else
      {
        v13 = v77;
        if ( (__int64 *)*v77 != &v76 )
          goto LABEL_157;
        *(_QWORD *)(v11 + 32) = v77;
        *v12 = (KSPIN_LOCK)&v76;
        *v13 = (__int64)v12;
        v77 = (__int64 *)(v11 + 24);
      }
    }
    else
    {
      v63 = SpinLock[5];
      v64 = SpinLock + 5;
      if ( *(PKSPIN_LOCK *)(v63 + 8) != SpinLock + 5 )
        goto LABEL_157;
      *v12 = v63;
      v12[1] = (KSPIN_LOCK)v64;
      *(_QWORD *)(v63 + 8) = v12;
      *v64 = (KSPIN_LOCK)v12;
    }
  }
  v14 = 0x10000;
  if ( *((_DWORD *)SpinLock + 8) <= 1u )
    goto LABEL_12;
  if ( *(_DWORD *)(*(_QWORD *)(SpinLock[1] + 960) + 4172LL) == -1 )
  {
    StateEvent = KeReadStateEvent(UxHighNonPagedPoolEvent);
    v57 = *((_DWORD *)SpinLock + 4);
    if ( StateEvent )
    {
      v58 = 2 * v57;
    }
    else
    {
      v58 = 0x10000;
      if ( v57 < 0x10000 )
        v58 = *((_DWORD *)SpinLock + 4);
    }
    v59 = *(unsigned int *)(*(_QWORD *)(SpinLock[1] + 960) + 4176LL);
    if ( (unsigned int)v59 > v58 )
    {
      v60 = KeReadStateEvent(UxHighNonPagedPoolEvent);
      v61 = *((_DWORD *)SpinLock + 4);
      if ( v60 )
      {
        v59 = 2 * v61;
      }
      else
      {
        v59 = 0x10000;
        if ( v61 < 0x10000 )
          v59 = v61;
      }
    }
  }
  else
  {
    v59 = KeReadStateEvent(UxHighNonPagedPoolEvent)
        ? *(unsigned int *)(*(_QWORD *)(SpinLock[1] + 960) + 4172LL)
        : 0x10000LL;
  }
  if ( SpinLock[3] < v59 )
  {
LABEL_12:
    v15 = SpinLock + 9;
    while ( 1 )
    {
      v16 = (__int64 *)*v15;
      if ( (PKSPIN_LOCK)*v15 == v15 )
        break;
      if ( (PKSPIN_LOCK)v16[1] != v15 )
        goto LABEL_157;
      v65 = *v16;
      if ( *(__int64 **)(*v16 + 8) != v16 )
        goto LABEL_157;
      *v15 = v65;
      *(_QWORD *)(v65 + 8) = v15;
      v66 = v77;
      if ( (__int64 *)*v77 != &v76 )
        goto LABEL_157;
      v16[1] = (__int64)v77;
      *v16 = (__int64)&v76;
      *v66 = (__int64)v16;
      v77 = v16;
    }
  }
  v17 = KeReadStateEvent(UxHighNonPagedPoolEvent);
  v18 = *((_DWORD *)SpinLock + 4);
  if ( v17 )
  {
    v14 = 2 * v18;
  }
  else if ( v18 < 0x10000 )
  {
    v14 = *((_DWORD *)SpinLock + 4);
  }
  if ( SpinLock[3] >= v14 && *((_DWORD *)SpinLock + 8) >= 2u )
    goto LABEL_19;
  if ( SpinLock[11] )
    goto LABEL_19;
  v19 = SpinLock[5];
  v20 = SpinLock + 5;
  if ( (PKSPIN_LOCK)v19 == SpinLock + 5 )
    goto LABEL_19;
  v47 = *(_WORD *)(v19 + 72);
  if ( v47 >= 0 )
    v48 = (v47 & 0x4000) != 0 ? *(_QWORD *)(*(_QWORD *)(v19 + 120) + 16LL) : 0LL;
  else
    v48 = *(_QWORD *)(*(_QWORD *)(v19 + 120) + 152LL);
  if ( SpinLock[12] != v48 && *((_DWORD *)SpinLock + 8) )
    goto LABEL_19;
  if ( *(PKSPIN_LOCK *)(v19 + 8) != v20 )
    goto LABEL_157;
  v49 = *(_QWORD *)v19;
  if ( *(_QWORD *)(*(_QWORD *)v19 + 8LL) != v19 )
    goto LABEL_157;
  *v20 = v49;
  v50 = v19 - 24;
  *(_QWORD *)(v49 + 8) = v20;
  *(_QWORD *)(v19 + 8) = v19;
  *(_QWORD *)v19 = v19;
  SpinLock[11] = v19 - 24;
  v51 = UxpTpAllocateChunkTracker(v19 - 24, v14, &v80);
  v52 = v80;
  if ( v51 >= 0 )
  {
    if ( *(_DWORD *)(v80 + 268) )
    {
      ++*((_DWORD *)SpinLock + 8);
      SpinLock[3] += *(unsigned int *)(v52 + 268);
      v53 = *(_WORD *)(v50 + 96);
      if ( v53 >= 0 )
      {
        if ( (v53 & 0x4000) != 0 )
          v54 = *(_QWORD *)(*(_QWORD *)(v50 + 144) + 16LL);
        else
          v54 = 0;
      }
      else
      {
        v54 = *(_QWORD *)(*(_QWORD *)(v50 + 144) + 152LL);
      }
      if ( v54 != SpinLock[12] )
        v9 = 1;
      SpinLock[12] = v54;
      v8 = 0;
    }
    goto LABEL_75;
  }
  *(_DWORD *)(v50 + 68) = v51;
  v67 = (__int64 **)v77;
  SpinLock[11] = 0;
  if ( *v67 != &v76 )
LABEL_157:
    __fastfail(3u);
  *(_QWORD *)(v19 + 8) = v67;
  *(_QWORD *)v19 = &v76;
  *v67 = (__int64 *)v19;
  v77 = (__int64 *)v19;
  *((_BYTE *)SpinLock + 104) = 1;
LABEL_75:
  if ( v52 )
  {
    v55 = v9 || v8;
    *(_BYTE *)(v52 + 257) = v55;
  }
LABEL_19:
  if ( v8 )
    SpinLock[12] = 0;
  KeReleaseSpinLock(SpinLock, v10);
  while ( 1 )
  {
    result = (volatile signed __int32 *)v76;
    if ( (__int64 *)v76 == &v76 )
      break;
    if ( *(__int64 **)(v76 + 8) != &v76 )
      goto LABEL_157;
    v24 = *(_QWORD *)v76;
    if ( *(_QWORD *)(*(_QWORD *)v76 + 8LL) != v76 )
      goto LABEL_157;
    v76 = *(_QWORD *)v76;
    *(_QWORD *)(v24 + 8) = &v76;
    v25 = result - 6;
    *((_QWORD *)result + 1) = result;
    *(_QWORD *)result = result;
    if ( _InterlockedExchangeAdd(result - 1, 0xFFFFFFFF) != 1 )
      continue;
    v26 = *((_WORD *)v25 + 48);
    v27 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v25 + 5) + 8LL) + 952LL);
    v28 = *((_QWORD *)v25 + 18);
    if ( (v26 & 0x4000) != 0 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v28 + 24), 0xFFFFFFFF) == 1 )
      {
        v23 = *(_QWORD *)(v28 + 32) == 0;
        v68 = v28 + 32;
        v78 = 0;
        if ( !v23 || *(_QWORD *)(v28 + 48) || *(_QWORD *)(v28 + 64) )
          KeBugCheckEx(0xFAu, 1u, v28 + 32, (ULONG_PTR)"minio\\http\\sys\\flowrate.h", 0x69u);
        if ( KeGetCurrentIrql() )
        {
          LODWORD(v75) = -1;
          LOBYTE(v21) = 1;
          UlThreadPoolEnqueueWorkItem(0, v28 + 32, UlpFlCleanupFlowRateInfoWorker, v21, v27, v75);
        }
        else
        {
          UxPodAttachThread(v27, &v78);
          UlpFlCleanupFlowRateInfoWorker(v68);
          UxPodDetachThread(&v78);
        }
      }
    }
    else if ( v26 < 0 )
    {
      UlHkeDereferenceCalloutContext(v28, 0x4000, v27);
    }
    v29 = *((_DWORD *)v25 + 32);
    v30 = 1;
    *((_QWORD *)v25 + 18) = 0;
    if ( v29 <= 1 )
      goto LABEL_47;
    do
    {
      v31 = *((_QWORD *)v25 + 17);
      v32 = v31 + 80LL * (v30 - 1);
      if ( !v32 )
        goto LABEL_46;
      if ( *(_DWORD *)v32 != 3 )
        goto LABEL_46;
      v33 = v30;
      if ( v30 >= v29 )
        goto LABEL_46;
      while ( 1 )
      {
        v34 = (int *)(v31 + 80LL * v33);
        if ( !v34 )
          goto LABEL_81;
        v35 = *v34;
        if ( *v34 == 3 )
          break;
        if ( v35 != 2 )
        {
          if ( v35 == 4 )
          {
            if ( *((_QWORD *)v34 + 2) )
              goto LABEL_46;
            goto LABEL_136;
          }
LABEL_81:
          if ( v34[4] )
            goto LABEL_46;
          goto LABEL_136;
        }
        if ( *((_QWORD *)v34 + 2) )
          goto LABEL_46;
LABEL_136:
        if ( ++v33 >= *((_DWORD *)v25 + 32) )
          goto LABEL_46;
      }
      v36 = *((_QWORD *)v34 + 1);
      if ( !*(_DWORD *)(v36 + 40) )
        goto LABEL_136;
      v37 = *(_QWORD ***)(v32 + 8);
      v38 = *v37;
      if ( *v37 )
      {
        while ( v38 != (_QWORD *)v36 )
        {
          v37 = (_QWORD **)v38;
          v38 = (_QWORD *)*v38;
          if ( !v38 )
            goto LABEL_46;
        }
        *v37 = 0;
      }
LABEL_46:
      v29 = *((_DWORD *)v25 + 32);
      ++v30;
    }
    while ( v30 < v29 );
LABEL_47:
    v39 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD))*((_QWORD *)v25 + 10);
    if ( v39 )
      v39(*((_QWORD *)v25 + 11), *((unsigned int *)v25 + 17), *((_QWORD *)v25 + 9));
    PsReturnPoolQuota(*((PEPROCESS *)v25 + 6), (POOL_TYPE)512, (unsigned int)UxTpTransmitPacketSize);
    v40 = (PEPROCESS)*((_QWORD *)v25 + 6);
    if ( v40 && v40 != UxSystemProcess )
      ObfDereferenceObject(v40);
    v41 = (void *)*((_QWORD *)v25 + 7);
    if ( v41 )
      ObfDereferenceObject(v41);
    v42 = *(_QWORD *)(*((_QWORD *)v25 + 5) + 8LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v42 + 20), 0xFFFFFFFF) == 1 )
    {
      CurrentProcess = IoGetCurrentProcess();
      v71 = *(_QWORD *)(v42 + 952);
      if ( UxSystemProcess == CurrentProcess )
      {
        v23 = *(_QWORD *)(v42 + 32) == 0;
        v79 = 0;
        if ( !v23 || *(_QWORD *)(v42 + 48) || *(_QWORD *)(v42 + 64) )
          KeBugCheckEx(0xFAu, 1u, v42 + 32, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
        if ( !KeGetCurrentIrql() )
        {
          UxPodAttachThread(v71, &v79);
          UlFreeHttpConnection(v42 + 32);
          UxPodDetachThread(&v79);
          goto LABEL_55;
        }
      }
      else if ( *(_QWORD *)(v42 + 32) || *(_QWORD *)(v42 + 48) || *(_QWORD *)(v42 + 64) )
      {
        KeBugCheckEx(0xFAu, 1u, v42 + 32, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
      }
      LODWORD(v75) = -1;
      LOBYTE(v70) = 1;
      UlThreadPoolEnqueueWorkItem(0, v42 + 32, UlFreeHttpConnection, v70, v71, v75);
    }
LABEL_55:
    *((_DWORD *)v25 + 4) = 1095781493;
    if ( UxCompactMode )
    {
      v72 = qword_1C0074300;
      v73 = KeGetCurrentNodeNumber() + 1;
      v74 = *(_DWORD *)v72 - 1;
      if ( v73 < *(_DWORD *)v72 )
        v74 = v73;
      v46 = *(_QWORD *)(*(_QWORD *)(v72 + 32) + 8LL * v74);
      if ( !*(_BYTE *)(v46 + 112) )
      {
        v43 = v72;
        goto LABEL_59;
      }
    }
    else
    {
      v43 = qword_1C0074300;
      v44 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v45 = *(_DWORD *)qword_1C0074300 - 1;
      if ( v44 < *(_DWORD *)qword_1C0074300 )
        v45 = v44;
      v46 = *(_QWORD *)(*(_QWORD *)(qword_1C0074300 + 32) + 8LL * v45);
      if ( !*(_BYTE *)(v46 + 112) )
LABEL_59:
        PplpLazyInitializeLookasideList(v43, v46);
    }
    ++*(_DWORD *)(v46 + 28);
    if ( ExQueryDepthSList((PSLIST_HEADER)v46) < *(_WORD *)(v46 + 16) )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)v46, (PSLIST_ENTRY)v25);
    }
    else
    {
      ++*(_DWORD *)(v46 + 32);
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(v46 + 56))(v25, v46);
    }
  }
  if ( v80 )
  {
    if ( *(_QWORD *)(v80 + 208) || *(_QWORD *)(v80 + 224) || *(_QWORD *)(v80 + 240) )
      KeBugCheckEx(0xFAu, 1u, v80 + 208, (ULONG_PTR)"minio\\http\\sys\\tpacket.c", 0x7ADu);
    LODWORD(v75) = -1;
    LOBYTE(v21) = 1;
    return (volatile signed __int32 *)UlThreadPoolEnqueueWorkItem(
                                        0,
                                        v80 + 208,
                                        UxpTpProcessMdlRuns,
                                        v21,
                                        *(_QWORD *)(SpinLock[1] + 952),
                                        v75);
  }
  return result;
}

```

## disassembly

```asm
0x1c000c170  mov     [rsp-38h+arg_10], rbx
0x1c000c175  push    rbp
0x1c000c176  push    rsi
0x1c000c177  push    rdi
0x1c000c178  push    r12
0x1c000c17a  push    r13
0x1c000c17c  push    r14
0x1c000c17e  push    r15
0x1c000c180  mov     rbp, rsp
0x1c000c183  sub     rsp, 60h
0x1c000c187  lea     rax, [rbp+var_30]
0x1c000c18b  mov     edi, edx
0x1c000c18d  mov     [rbp+var_28], rax
0x1c000c191  movzx   r15d, r9b
0x1c000c195  lea     rax, [rbp+var_30]
0x1c000c199  mov     [rbp+arg_0], 0
0x1c000c1a1  mov     [rbp+var_30], rax
0x1c000c1a5  mov     esi, r8d
0x1c000c1a8  mov     rbx, rcx
0x1c000c1ab  xor     r14b, r14b
0x1c000c1ae  xor     r13b, r13b
0x1c000c1b1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c000c1b8  nop     dword ptr [rax+rax+00h]
0x1c000c1bd  movzx   r12d, al
0x1c000c1c1  test    esi, esi
0x1c000c1c3  jnz     loc_1C000C3FB
0x1c000c1c9  test    edi, edi
0x1c000c1cb  jnz     loc_1C000C2F0
0x1c000c1d1  cmp     [rbx+68h], r13b
0x1c000c1d5  jnz     loc_1C000C2A5
0x1c000c1db  test    r15b, r15b
0x1c000c1de  jnz     short loc_1C000C241
0x1c000c1e0  test    esi, esi
0x1c000c1e2  jnz     short loc_1C000C241
0x1c000c1e4  mov     rcx, [rbx+58h]
0x1c000c1e8  mov     qword ptr [rbx+58h], 0
0x1c000c1f0  mov     eax, [rcx+80h]
0x1c000c1f6  lea     rdx, [rcx+18h]
0x1c000c1fa  cmp     [rcx+84h], eax
0x1c000c200  jnz     loc_1C00224D4
0x1c000c206  dec     dword ptr [rbx+38h]
0x1c000c209  mov     rax, [rcx+0C8h]
0x1c000c210  sub     [rbx+40h], rax
0x1c000c214  test    byte ptr [rcx+60h], 8
0x1c000c218  jnz     loc_1C00224B0
0x1c000c21e  mov     rax, [rbp+var_28]
0x1c000c222  lea     rcx, [rbp+var_30]
0x1c000c226  cmp     [rax], rcx
0x1c000c229  jnz     loc_1C002281B
0x1c000c22f  mov     [rdx+8], rax
0x1c000c233  lea     rcx, [rbp+var_30]
0x1c000c237  mov     [rdx], rcx
0x1c000c23a  mov     [rax], rdx
0x1c000c23d  mov     [rbp+var_28], rdx
0x1c000c241  cmp     dword ptr [rbx+20h], 1
0x1c000c245  mov     edi, 10000h
0x1c000c24a  ja      loc_1C000C704
0x1c000c250  lea     rax, [rbx+48h]
0x1c000c254  mov     rcx, [rax]
0x1c000c257  cmp     rcx, rax
0x1c000c25a  jnz     loc_1C0022526
0x1c000c260  mov     rcx, cs:UxHighNonPagedPoolEvent; Event
0x1c000c267  call    cs:__imp_KeReadStateEvent
0x1c000c26e  nop     dword ptr [rax+rax+00h]
0x1c000c273  mov     ecx, [rbx+10h]
0x1c000c276  test    eax, eax
0x1c000c278  jz      loc_1C002256C
0x1c000c27e  lea     edi, [rcx+rcx]
0x1c000c281  mov     eax, edi
0x1c000c283  cmp     [rbx+18h], rax
0x1c000c287  jnb     loc_1C0022576
0x1c000c28d  cmp     qword ptr [rbx+58h], 0
0x1c000c292  jnz     short loc_1C000C2A5
0x1c000c294  mov     rsi, [rbx+28h]
0x1c000c298  lea     rcx, [rbx+28h]
0x1c000c29c  cmp     rsi, rcx
0x1c000c29f  jnz     loc_1C000C555
0x1c000c2a5  test    r14b, r14b
0x1c000c2a8  jnz     short loc_1C000C306
0x1c000c2aa  movzx   edx, r12b; NewIrql
0x1c000c2ae  mov     rcx, rbx; SpinLock
0x1c000c2b1  call    cs:__imp_KeReleaseSpinLock
0x1c000c2b8  nop     dword ptr [rax+rax+00h]
0x1c000c2bd  mov     rax, [rbp+var_30]
0x1c000c2c1  lea     rcx, [rbp+var_30]
0x1c000c2c5  cmp     rax, rcx
0x1c000c2c8  jnz     short loc_1C000C310
0x1c000c2ca  mov     rcx, [rbp+arg_0]
0x1c000c2ce  test    rcx, rcx
0x1c000c2d1  jnz     loc_1C000C644
0x1c000c2d7  mov     rbx, [rsp+60h+arg_10]
0x1c000c2df  add     rsp, 60h
0x1c000c2e3  pop     r15
0x1c000c2e5  pop     r14
0x1c000c2e7  pop     r13
0x1c000c2e9  pop     r12
0x1c000c2eb  pop     rdi
0x1c000c2ec  pop     rsi
0x1c000c2ed  pop     rbp
0x1c000c2ee  retn
0x1c000c2f0  sub     [rbx+18h], rdi
0x1c000c2f4  add     dword ptr [rbx+20h], 0FFFFFFFFh
0x1c000c2f8  jnz     loc_1C000C1D1
0x1c000c2fe  mov     r14b, 1
0x1c000c301  jmp     loc_1C000C1D1
0x1c000c306  mov     qword ptr [rbx+60h], 0
0x1c000c30e  jmp     short loc_1C000C2AA
0x1c000c310  lea     rcx, [rbp+var_30]
0x1c000c314  cmp     [rax+8], rcx
0x1c000c318  jnz     loc_1C002281B
0x1c000c31e  mov     rcx, [rax]
0x1c000c321  cmp     [rcx+8], rax
0x1c000c325  jnz     loc_1C002281B
0x1c000c32b  mov     [rbp+var_30], rcx
0x1c000c32f  lea     rdx, [rbp+var_30]
0x1c000c333  mov     [rcx+8], rdx
0x1c000c337  lea     rdi, [rax-18h]
0x1c000c33b  mov     [rax+8], rax
0x1c000c33f  mov     [rax], rax
0x1c000c342  mov     eax, 0FFFFFFFFh
0x1c000c347  lock xadd [rdi+14h], eax
0x1c000c34c  cmp     eax, 1
0x1c000c34f  jnz     loc_1C000C2BD
0x1c000c355  mov     rax, [rdi+28h]
0x1c000c359  mov     edx, 4000h
0x1c000c35e  mov     rcx, [rax+8]
0x1c000c362  movzx   eax, word ptr [rdi+60h]
0x1c000c366  mov     r8, [rcx+3B8h]
0x1c000c36d  mov     rcx, [rdi+90h]
0x1c000c374  test    dx, ax
0x1c000c377  jnz     loc_1C00225DB
0x1c000c37d  test    ax, ax
0x1c000c380  js      loc_1C002266C
0x1c000c386  mov     r9d, [rdi+80h]
0x1c000c38d  mov     edx, 1
0x1c000c392  mov     qword ptr [rdi+90h], 0
0x1c000c39d  cmp     r9d, edx
0x1c000c3a0  jbe     loc_1C000C43F
0x1c000c3a6  mov     r11, [rdi+88h]
0x1c000c3ad  lea     eax, [rdx-1]
0x1c000c3b0  lea     r8, [rax+rax*4]
0x1c000c3b4  shl     r8, 4
0x1c000c3b8  add     r8, r11
0x1c000c3bb  jz      short loc_1C000C42D
0x1c000c3bd  cmp     dword ptr [r8], 3
0x1c000c3c1  jnz     short loc_1C000C42D
0x1c000c3c3  mov     r10d, edx
0x1c000c3c6  cmp     edx, r9d
0x1c000c3c9  jnb     short loc_1C000C42D
0x1c000c3cb  mov     eax, r10d
0x1c000c3ce  lea     rcx, [rax+rax*4]
0x1c000c3d2  shl     rcx, 4
0x1c000c3d6  add     rcx, r11
0x1c000c3d9  jz      loc_1C000C635
0x1c000c3df  mov     eax, [rcx]
0x1c000c3e1  cmp     eax, 3
0x1c000c3e4  jz      short loc_1C000C403
0x1c000c3e6  cmp     eax, 2
0x1c000c3e9  jnz     loc_1C000C62C
0x1c000c3ef  cmp     qword ptr [rcx+10h], 0
0x1c000c3f4  jnz     short loc_1C000C42D
0x1c000c3f6  jmp     loc_1C0022682
0x1c000c3fb  mov     [rbx+10h], esi
0x1c000c3fe  jmp     loc_1C000C1C9
0x1c000c403  mov     rsi, [rcx+8]
0x1c000c407  cmp     dword ptr [rsi+28h], 0
0x1c000c40b  jz      loc_1C0022682
0x1c000c411  mov     r9, [r8+8]
0x1c000c415  mov     rcx, [r9]
0x1c000c418  test    rcx, rcx
0x1c000c41b  jz      short loc_1C000C42D
0x1c000c41d  cmp     rcx, rsi
0x1c000c420  jnz     loc_1C0022697
0x1c000c426  mov     qword ptr [r9], 0
0x1c000c42d  mov     r9d, [rdi+80h]
0x1c000c434  inc     edx
0x1c000c436  cmp     edx, r9d
0x1c000c439  jb      loc_1C000C3A6
0x1c000c43f  mov     rax, [rdi+50h]
0x1c000c443  mov     r8, [rdi+48h]
0x1c000c447  test    rax, rax
0x1c000c44a  jz      short loc_1C000C459
0x1c000c44c  mov     edx, [rdi+44h]
0x1c000c44f  mov     rcx, [rdi+58h]
0x1c000c453  call    cs:__guard_dispatch_icall_fptr
0x1c000c459  mov     r8d, cs:UxTpTransmitPacketSize; Amount
0x1c000c460  mov     edx, 200h; PoolType
0x1c000c465  mov     rcx, [rdi+30h]; Process
0x1c000c469  call    cs:__imp_PsReturnPoolQuota
0x1c000c470  nop     dword ptr [rax+rax+00h]
0x1c000c475  mov     rcx, [rdi+30h]; Object
0x1c000c479  test    rcx, rcx
0x1c000c47c  jz      short loc_1C000C493
0x1c000c47e  cmp     rcx, cs:UxSystemProcess
0x1c000c485  jz      short loc_1C000C493
0x1c000c487  call    cs:__imp_ObfDereferenceObject
0x1c000c48e  nop     dword ptr [rax+rax+00h]
0x1c000c493  mov     rcx, [rdi+38h]; Object
0x1c000c497  test    rcx, rcx
0x1c000c49a  jz      short loc_1C000C4A8
0x1c000c49c  call    cs:__imp_ObfDereferenceObject
0x1c000c4a3  nop     dword ptr [rax+rax+00h]
0x1c000c4a8  mov     rax, [rdi+28h]
0x1c000c4ac  mov     rsi, [rax+8]
0x1c000c4b0  mov     eax, 0FFFFFFFFh
0x1c000c4b5  lock xadd [rsi+14h], eax
0x1c000c4ba  cmp     eax, 1
0x1c000c4bd  jz      loc_1C00226AE
0x1c000c4c3  mov     dword ptr [rdi+10h], 41504C75h
0x1c000c4ca  cmp     cs:UxCompactMode, 0
0x1c000c4d1  jnz     loc_1C0022783
0x1c000c4d7  mov     eax, gs:1A4h
0x1c000c4df  mov     rcx, cs:qword_1C0074300
0x1c000c4e6  lea     r8d, [rax+1]
0x1c000c4ea  mov     edx, [rcx]
0x1c000c4ec  cmp     r8d, edx
0x1c000c4ef  lea     eax, [rdx-1]
0x1c000c4f2  cmovb   eax, r8d
0x1c000c4f6  mov     edx, eax
0x1c000c4f8  mov     rax, [rcx+20h]
0x1c000c4fc  mov     rsi, [rax+rdx*8]
0x1c000c500  cmp     byte ptr [rsi+70h], 0
0x1c000c504  jnz     short loc_1C000C50E
0x1c000c506  mov     rdx, rsi
0x1c000c509  call    PplpLazyInitializeLookasideList
0x1c000c50e  inc     dword ptr [rsi+1Ch]
0x1c000c511  mov     rcx, rsi; SListHead
0x1c000c514  call    cs:__imp_ExQueryDepthSList
0x1c000c51b  nop     dword ptr [rax+rax+00h]
0x1c000c520  cmp     ax, [rsi+10h]
0x1c000c524  jb      short loc_1C000C53E
0x1c000c526  inc     dword ptr [rsi+20h]
0x1c000c529  mov     rdx, rsi
0x1c000c52c  mov     rax, [rsi+38h]
0x1c000c530  mov     rcx, rdi
0x1c000c533  call    cs:__guard_dispatch_icall_fptr
0x1c000c539  jmp     loc_1C000C2BD
0x1c000c53e  mov     rdx, rdi; ListEntry
0x1c000c541  mov     rcx, rsi; ListHead
0x1c000c544  call    cs:__imp_ExpInterlockedPushEntrySList
0x1c000c54b  nop     dword ptr [rax+rax+00h]
0x1c000c550  jmp     loc_1C000C2BD
0x1c000c555  movzx   eax, word ptr [rsi+48h]
0x1c000c559  mov     r8, [rbx+60h]
0x1c000c55d  test    ax, ax
0x1c000c560  jns     loc_1C000C687
0x1c000c566  mov     rax, [rsi+78h]
0x1c000c56a  mov     rdx, [rax+98h]
0x1c000c571  cmp     r8, rdx
0x1c000c574  jnz     loc_1C0022585
0x1c000c57a  cmp     [rsi+8], rcx
0x1c000c57e  jnz     loc_1C002281B
0x1c000c584  mov     rax, [rsi]
0x1c000c587  cmp     [rax+8], rsi
0x1c000c58b  jnz     loc_1C002281B
0x1c000c591  mov     [rcx], rax
0x1c000c594  lea     r15, [rsi-18h]
0x1c000c598  mov     [rax+8], rcx
0x1c000c59c  lea     r8, [rbp+arg_0]
0x1c000c5a0  mov     [rsi+8], rsi
0x1c000c5a4  mov     rcx, r15
0x1c000c5a7  mov     [rsi], rsi
0x1c000c5aa  mov     edx, edi
0x1c000c5ac  mov     [rbx+58h], r15
0x1c000c5b0  call    UxpTpAllocateChunkTracker
0x1c000c5b5  mov     rdx, [rbp+arg_0]
0x1c000c5b9  test    eax, eax
0x1c000c5bb  js      loc_1C0022594
0x1c000c5c1  cmp     dword ptr [rdx+10Ch], 0
0x1c000c5c8  jz      short loc_1C000C604
0x1c000c5ca  inc     dword ptr [rbx+20h]
0x1c000c5cd  mov     eax, [rdx+10Ch]
0x1c000c5d3  add     [rbx+18h], rax
0x1c000c5d7  movzx   eax, word ptr [r15+60h]
0x1c000c5dc  test    ax, ax
0x1c000c5df  jns     loc_1C000C698
0x1c000c5e5  mov     rax, [r15+90h]
0x1c000c5ec  mov     rcx, [rax+98h]
0x1c000c5f3  cmp     rcx, [rbx+60h]
0x1c000c5f7  jnz     loc_1C00225CC
0x1c000c5fd  mov     [rbx+60h], rcx
0x1c000c601  xor     r14b, r14b
0x1c000c604  test    rdx, rdx
0x1c000c607  jz      loc_1C000C2A5
0x1c000c60d  test    r13b, r13b
0x1c000c610  jnz     loc_1C00225D4
0x1c000c616  test    r14b, r14b
0x1c000c619  jnz     loc_1C00225D4
0x1c000c61f  xor     al, al
0x1c000c621  mov     [rdx+101h], al
0x1c000c627  jmp     loc_1C000C2A5
0x1c000c62c  cmp     eax, 4
0x1c000c62f  jz      loc_1C0022677
0x1c000c635  cmp     dword ptr [rcx+10h], 0
0x1c000c639  jnz     loc_1C000C42D
0x1c000c63f  jmp     loc_1C0022682
0x1c000c644  cmp     qword ptr [rcx+0D0h], 0
0x1c000c64c  mov     rax, [rbx+8]
0x1c000c650  mov     rdx, [rax+3B8h]
0x1c000c657  jz      short loc_1C000C6A9
  ... truncated ...
```
