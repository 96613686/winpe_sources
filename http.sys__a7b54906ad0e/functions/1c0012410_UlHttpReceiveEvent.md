# UlHttpReceiveEvent

- ea: `0x1c0012410`
- end: `0x1c001289e`
- name: `UlHttpReceiveEvent`
- size: `1166`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1c0001118`
- `0x1c0006260`
- `0x1c0010ce8`
- `0x1c0012410`
- `0x1c00128b0`
- `0x1c001a4b0`
- `0x1c001b610`
- `0x1c001b640`
- `0x1c001b900`
- `0x1c002caa4`
- `0x1c002dc30`
- `0x1c002f6d8`
- `0x1c008f21c`
- `0x1c008f374`
- `0x1c008f3a8`
- `0x1c008f570`
- `0x1c008f680`
- `0x1c00903a4`
- `0x1c0090588`
- `0x1c0090c00`
- `0x1c009665c`
- `0x1c00971e0`
- `0x1c009764c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c0012823`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c0012823`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00125fd`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0025f31`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00125fd`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0025f31`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0025ef5`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0025ef5`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0012881`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0012881`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0012568`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0025dda`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0026133`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0012568`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0025dda`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0026133`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0012475`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0012475`

## pseudocode

```c
__int64 __fastcall UlHttpReceiveEvent(__int64 a1, __int64 a2, __int64 **a3, unsigned __int64 a4)
{
  __int64 v4; // rax
  char v5; // r12
  unsigned int v6; // r14d
  unsigned __int64 v7; // r15
  __int64 **v8; // r13
  KIRQL v10; // al
  __int64 v11; // rdx
  __int64 v12; // rcx
  KIRQL v13; // di
  int v14; // esi
  unsigned int v15; // r8d
  bool v16; // zf
  unsigned int v17; // r10d
  unsigned __int64 v18; // r9
  unsigned int v19; // r11d
  unsigned int v20; // edx
  unsigned int v21; // ecx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r9
  unsigned int v26; // edi
  __int64 v27; // r14
  unsigned int v28; // edx
  unsigned int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rbx
  char *PoolWithTagPriority; // rsi
  int v34; // ebx
  unsigned int v35; // eax
  __int64 v36; // r8
  struct _MDL *v37; // rbx
  __int64 v38; // rdx
  unsigned __int64 v39; // r12
  unsigned int ByteCount; // eax
  char *MappedSystemVa; // r10
  unsigned __int64 v42; // r14
  int v43; // ebx
  __int64 v44; // r8
  __int64 v45; // r9
  char *v47; // rax
  __int64 v48; // r8
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 (__fastcall *v51)(__int64, __int64, __int64, __int64); // rax
  __int64 v52; // rsi
  unsigned int v53; // edx
  unsigned int v54; // eax
  __int64 v55; // rcx
  __int64 v56; // rax
  int v57; // eax
  bool v58; // [rsp+40h] [rbp-A8h]
  int v59; // [rsp+44h] [rbp-A4h] BYREF
  int v60; // [rsp+48h] [rbp-A0h] BYREF
  unsigned int v61; // [rsp+4Ch] [rbp-9Ch]
  unsigned int v62; // [rsp+50h] [rbp-98h]
  __int64 v63; // [rsp+58h] [rbp-90h]
  __int64 v64; // [rsp+60h] [rbp-88h]
  _QWORD v65[2]; // [rsp+68h] [rbp-80h] BYREF
  _QWORD v66[2]; // [rsp+78h] [rbp-70h] BYREF
  _QWORD v67[2]; // [rsp+88h] [rbp-60h] BYREF

  v4 = *(_QWORD *)(a1 + 960);
  v64 = 0;
  v5 = 0;
  v6 = 0;
  v63 = v4;
  v59 = 0;
  v7 = a4;
  v60 = 0;
  v8 = a3;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qLqP(a1, a2, a1, (unsigned int)a2, a3, a4);
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 528));
  v13 = v10;
  if ( *(_BYTE *)(a1 + 677) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 528), v10);
    v43 = 0;
    goto LABEL_62;
  }
  v14 = *(_DWORD *)(a1 + 672);
  v58 = v14 == 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x2000) != 0 )
    WPP_SF_qilqq(v12, v11, a1, *(_QWORD *)(a1 + 24), 0, &v59, &v60);
  v15 = 0;
  v16 = (*(_DWORD *)(a1 + 520) & 0x400) == 0;
  v60 = 0;
  if ( v16 )
  {
    v17 = 1;
    v59 = 1;
  }
  else
  {
    v17 = 3;
    v15 = 12;
    v59 = 3;
    v60 = 12;
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    {
      WPP_SF_DD(21, WPP_95173837b5773721cd51a44381a2b960_Traceguids, 3, 12);
      v17 = v59;
      v15 = v60;
    }
  }
  v18 = v15 + v7;
  if ( v18 < v7 || v15 + 2 * v7 < v7 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 528), v13);
    if ( SLOBYTE(WPP_MAIN_CB.DeviceType) < 0 )
      WPP_SF_q(25, WPP_95173837b5773721cd51a44381a2b960_Traceguids, a1);
    v43 = -1073741595;
    goto LABEL_62;
  }
  v19 = *(_DWORD *)(*(_QWORD *)(a1 + 960) + 4164LL);
  if ( (*(_DWORD *)(a1 + 520) & 0x400) != 0 )
    v19 -= 5;
  v20 = *(_DWORD *)(a1 + 672);
  v21 = 0;
  if ( v19 > v20 )
    v21 = v19 - v20;
  if ( v18 > v21 )
  {
    *(_QWORD *)(a1 + 664) = v7;
    v7 = 0;
    if ( v21 > v15 && !*(_BYTE *)(a1 + 676) )
    {
      v5 = 1;
      v6 = v21 - v15;
      *(_BYTE *)(a1 + 676) = 1;
    }
  }
  else
  {
    v22 = *(_QWORD *)(a1 + 264);
    v20 += v15 + v7;
    *(_DWORD *)(a1 + 672) = v20;
    *(_QWORD *)(a1 + 264) = v22 + v17;
    v64 = v22;
  }
  if ( SBYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) < 0 )
    WPP_SF_qilq(26, WPP_95173837b5773721cd51a44381a2b960_Traceguids, a1, v20 - v7, v20, *(_QWORD *)(a1 + 664));
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 528), v13);
  if ( !v7 )
  {
    if ( v5 )
    {
      v57 = UlpReceiveData(a1, v6);
      if ( v57 < 0 && SLOBYTE(WPP_MAIN_CB.DeviceType) < 0 )
        WPP_SF_qD(30, WPP_95173837b5773721cd51a44381a2b960_Traceguids, a1, (unsigned int)v57);
    }
    v43 = -1073741285;
    goto LABEL_62;
  }
  v26 = v7;
  v27 = v63;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qLIl(v24, v23, v63, (unsigned int)v7, 0xFFFFFFFFLL, v58);
  if ( !v14 && (unsigned int)v7 <= 0x200 )
  {
    v26 = 512;
    if ( UxCompactMode )
    {
      v52 = UlLookaside;
      v53 = KeGetCurrentNodeNumber() + 1;
      v54 = *(_DWORD *)v52 - 1;
      if ( v53 < *(_DWORD *)v52 )
        v54 = v53;
      v55 = v54;
      v56 = *(_QWORD *)(v52 + 32);
      v32 = *(_QWORD *)(v56 + 8 * v55);
      if ( !*(_BYTE *)(v32 + 112) )
        PplpLazyInitializeLookasideList(v52, *(_QWORD *)(v56 + 8 * v55));
      ++*(_DWORD *)(v32 + 20);
      PoolWithTagPriority = (char *)ExpInterlockedPopEntrySList((PSLIST_HEADER)v32);
      if ( PoolWithTagPriority )
        goto LABEL_29;
    }
    else
    {
      v28 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v29 = *(_DWORD *)UlLookaside - 1;
      if ( v28 < *(_DWORD *)UlLookaside )
        v29 = v28;
      v30 = v29;
      v31 = *(_QWORD *)(UlLookaside + 32);
      v32 = *(_QWORD *)(v31 + 8 * v30);
      if ( !*(_BYTE *)(v32 + 112) )
        PplpLazyInitializeLookasideList(UlLookaside, *(_QWORD *)(v31 + 8 * v30));
      ++*(_DWORD *)(v32 + 20);
      PoolWithTagPriority = (char *)ExpInterlockedPopEntrySList((PSLIST_HEADER)v32);
      if ( PoolWithTagPriority )
        goto LABEL_29;
    }
    v48 = *(unsigned int *)(v32 + 40);
    v49 = *(unsigned int *)(v32 + 44);
    v50 = *(unsigned int *)(v32 + 36);
    v51 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v32 + 48);
    ++*(_DWORD *)(v32 + 24);
    PoolWithTagPriority = (char *)v51(v50, v49, v48, v32);
LABEL_29:
    v34 = 1;
    goto LABEL_30;
  }
  if ( (unsigned int)v7 >= (int)v7 + 144 )
  {
    PoolWithTagPriority = 0;
    goto LABEL_82;
  }
  PoolWithTagPriority = (char *)ExAllocatePoolWithTagPriority(
                                  (POOL_TYPE)512,
                                  (unsigned int)v7 + 144LL,
                                  0x50526C55u,
                                  LowPoolPriority);
  v34 = 0;
LABEL_30:
  if ( PoolWithTagPriority )
  {
    memset(PoolWithTagPriority, 0, 0x90u);
    *((_DWORD *)PoolWithTagPriority + 4) = 1347578965;
    *((_QWORD *)PoolWithTagPriority + 10) = 0;
    *((_QWORD *)PoolWithTagPriority + 12) = 0;
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      WPP_SF_qqq(48, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, PoolWithTagPriority, 0xFFFFFFFFLL, v26);
    v35 = *((_DWORD *)PoolWithTagPriority + 31) & 0xFFFFFFFE;
    *((_DWORD *)PoolWithTagPriority + 29) = v26;
    *((_QWORD *)PoolWithTagPriority + 16) = 0xFFFFFFFFLL;
    *((_DWORD *)PoolWithTagPriority + 31) = v34 | v35;
    *((_DWORD *)PoolWithTagPriority + 5) = 1;
    if ( *(_BYTE *)(v27 + 79) && Microsoft_Windows_Networking_CorrelationEnabled )
    {
      v65[1] = *((_QWORD *)&UlEtwBasePtrActivityGuid + 1);
      v65[0] = PoolWithTagPriority;
      UlEtwStartActivity(v65, 0);
    }
    goto LABEL_36;
  }
LABEL_82:
  if ( SLOBYTE(WPP_MAIN_CB.DeviceType) < 0 )
    WPP_SF_(47, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids);
LABEL_36:
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_q(49, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, PoolWithTagPriority);
  if ( PoolWithTagPriority )
  {
    if ( *(_BYTE *)(v27 + 79) && Microsoft_Windows_Networking_CorrelationEnabled )
    {
      v66[1] = 0;
      v66[0] = v8;
      v67[1] = *((_QWORD *)&UlEtwBasePtrActivityGuid + 1);
      v67[0] = PoolWithTagPriority;
      UlEtwTransferActivity(v67, v66, 1);
    }
    v36 = 0;
    *((_DWORD *)PoolWithTagPriority + 28) = v7;
    v61 = 0;
    if ( v8 )
    {
      do
      {
        v37 = (struct _MDL *)v8[1];
        v38 = *((unsigned int *)v8 + 4);
        v39 = (unsigned __int64)v8[3];
        v8 = (__int64 **)*v8;
        v62 = v38;
        if ( v37 )
        {
          while ( v39 )
          {
            ByteCount = v37->ByteCount;
            if ( (unsigned int)v38 >= ByteCount )
            {
              v38 = (unsigned int)v38 - ByteCount;
            }
            else
            {
              if ( (v37->MdlFlags & 5) != 0 )
              {
                MappedSystemVa = (char *)v37->MappedSystemVa;
              }
              else
              {
                v47 = (char *)MmMapLockedPagesSpecifyCache(v37, 0, MmCached, 0, 0, 0x40000000u);
                v38 = v62;
                MappedSystemVa = v47;
                v36 = v61;
              }
              if ( !MappedSystemVa )
              {
                v27 = v63;
                UlReleaseRequestBuffer(v63, PoolWithTagPriority, v36, v25);
                UlCloseConnection(a1);
                v43 = -1073741801;
                goto LABEL_87;
              }
              v42 = (unsigned int)(v37->ByteCount - v38);
              if ( v7 - (unsigned int)v36 <= v42 )
                LODWORD(v42) = v7 - v36;
              if ( (unsigned int)v42 > v39 )
                LODWORD(v42) = v39;
              memmove(&PoolWithTagPriority[(unsigned int)v36 + 136], &MappedSystemVa[v38], (unsigned int)v42);
              v39 -= (unsigned int)v42;
              v36 = (unsigned int)v42 + v61;
              v61 += v42;
              v38 = 0;
            }
            v37 = v37->Next;
            v62 = v38;
            if ( !v37 )
              break;
          }
        }
      }
      while ( v8 );
      v27 = v63;
    }
    *((_QWORD *)PoolWithTagPriority + 6) = a1;
    if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x2000) != 0 )
      WPP_SF_qqq(
        27,
        WPP_95173837b5773721cd51a44381a2b960_Traceguids,
        PoolWithTagPriority,
        *((_QWORD *)PoolWithTagPriority + 16),
        a1);
    if ( SBYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) < 0 )
    {
      WPP_SF_qqIPq(
        28,
        WPP_95173837b5773721cd51a44381a2b960_Traceguids,
        *(_QWORD *)(a1 + 456),
        PoolWithTagPriority,
        *((_QWORD *)PoolWithTagPriority + 16),
        v7,
        a1);
      if ( SBYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) < 0 )
        WPP_SF_(29, WPP_95173837b5773721cd51a44381a2b960_Traceguids);
    }
    v43 = UlpTransformAndQueueRequestBuffers(a1, (_DWORD)PoolWithTagPriority, v64, v58, v59, 0);
    if ( v43 < 0 )
LABEL_87:
      UlReleaseRequestBuffer(v27, PoolWithTagPriority, v44, v45);
    else
      v43 = 0;
  }
  else
  {
    UlCloseConnection(a1);
    v43 = -1073741801;
  }
LABEL_62:
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_D(31, WPP_95173837b5773721cd51a44381a2b960_Traceguids);
  return (unsigned int)v43;
}

```

## disassembly

```asm
0x1c0012410  push    rbx
0x1c0012412  push    rbp
0x1c0012413  push    rsi
0x1c0012414  push    rdi
0x1c0012415  push    r12
0x1c0012417  push    r13
0x1c0012419  push    r14
0x1c001241b  push    r15
0x1c001241d  sub     rsp, 0A8h
0x1c0012424  mov     rax, cs:__security_cookie
0x1c001242b  xor     rax, rsp
0x1c001242e  mov     [rsp+0E8h+var_50], rax
0x1c0012436  mov     rax, [rcx+3C0h]
0x1c001243d  xor     esi, esi
0x1c001243f  mov     [rsp+0E8h+var_88], rsi
0x1c0012444  xor     r12b, r12b
0x1c0012447  mov     r14d, esi
0x1c001244a  mov     [rsp+0E8h+var_90], rax
0x1c001244f  mov     [rsp+0E8h+var_A4], esi
0x1c0012453  mov     r15, r9
0x1c0012456  mov     [rsp+0E8h+var_A0], esi
0x1c001245a  mov     r13, r8
0x1c001245d  mov     rbp, rcx
0x1c0012460  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0012466  test    al, al
0x1c0012468  js      loc_1C0025DB4
0x1c001246e  lea     rcx, [rbp+210h]; SpinLock
0x1c0012475  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c001247c  nop     dword ptr [rax+rax+00h]
0x1c0012481  movzx   edi, al
0x1c0012484  cmp     [rbp+2A5h], sil
0x1c001248b  jnz     loc_1C0025DCF
0x1c0012491  mov     esi, [rbp+2A0h]
0x1c0012497  test    esi, esi
0x1c0012499  setz    [rsp+0E8h+var_A8]
0x1c001249e  test    dword ptr cs:WPP_MAIN_CB.Queue, 2000h
0x1c00124a8  jnz     loc_1C0025DED
0x1c00124ae  xor     r8d, r8d
0x1c00124b1  test    dword ptr [rbp+208h], 400h
0x1c00124bb  mov     [rsp+0E8h+var_A0], r8d
0x1c00124c0  jnz     loc_1C0025E18
0x1c00124c6  mov     r10d, 1
0x1c00124cc  mov     [rsp+0E8h+var_A4], r10d
0x1c00124d1  mov     eax, r8d
0x1c00124d4  lea     r9, [rax+r15]
0x1c00124d8  cmp     r9, r15
0x1c00124db  jb      loc_1C0026128
0x1c00124e1  lea     rax, [rax+r15*2]
0x1c00124e5  cmp     rax, r15
0x1c00124e8  jb      loc_1C0026128
0x1c00124ee  test    dword ptr [rbp+208h], 400h
0x1c00124f8  mov     rax, [rbp+3C0h]
0x1c00124ff  mov     r11d, [rax+1044h]
0x1c0012506  jnz     loc_1C0025E61
0x1c001250c  mov     edx, [rbp+2A0h]
0x1c0012512  xor     ecx, ecx
0x1c0012514  mov     eax, r11d
0x1c0012517  sub     eax, edx
0x1c0012519  cmp     r11d, edx
0x1c001251c  cmova   ecx, eax
0x1c001251f  mov     eax, ecx
0x1c0012521  cmp     r9, rax
0x1c0012524  ja      loc_1C0025E6A
0x1c001252a  mov     rcx, [rbp+108h]
0x1c0012531  add     edx, r15d
0x1c0012534  add     edx, r8d
0x1c0012537  mov     eax, r10d
0x1c001253a  add     rax, rcx
0x1c001253d  mov     [rbp+2A0h], edx
0x1c0012543  mov     [rbp+108h], rax
0x1c001254a  mov     [rsp+0E8h+var_88], rcx
0x1c001254f  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c0012555  test    al, al
0x1c0012557  js      loc_1C0025E9F
0x1c001255d  movzx   edx, dil; NewIrql
0x1c0012561  lea     rcx, [rbp+210h]; SpinLock
0x1c0012568  call    cs:__imp_KeReleaseSpinLock
0x1c001256f  nop     dword ptr [rax+rax+00h]
0x1c0012574  test    r15, r15
0x1c0012577  jz      loc_1C00260E9
0x1c001257d  mov     edi, r15d
0x1c0012580  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0012586  mov     r12d, 0FFFFFFFFh
0x1c001258c  mov     r14, [rsp+0E8h+var_90]
0x1c0012591  test    al, al
0x1c0012593  js      loc_1C0025ECF
0x1c0012599  test    esi, esi
0x1c001259b  jnz     loc_1C0012862
0x1c00125a1  cmp     edi, 200h
0x1c00125a7  ja      loc_1C0012862
0x1c00125ad  cmp     cs:UxCompactMode, sil
0x1c00125b4  mov     edi, 200h
0x1c00125b9  jnz     loc_1C0025EEE
0x1c00125bf  mov     eax, gs:1A4h
0x1c00125c7  mov     r8, cs:UlLookaside
0x1c00125ce  lea     edx, [rax+1]
0x1c00125d1  mov     ecx, [r8]
0x1c00125d4  cmp     edx, ecx
0x1c00125d6  lea     eax, [rcx-1]
0x1c00125d9  cmovb   eax, edx
0x1c00125dc  mov     ecx, eax
0x1c00125de  mov     rax, [r8+20h]
0x1c00125e2  mov     rbx, [rax+rcx*8]
0x1c00125e6  cmp     [rbx+70h], sil
0x1c00125ea  jnz     short loc_1C00125F7
0x1c00125ec  mov     rdx, rbx
0x1c00125ef  mov     rcx, r8
0x1c00125f2  call    PplpLazyInitializeLookasideList
0x1c00125f7  inc     dword ptr [rbx+14h]
0x1c00125fa  mov     rcx, rbx; ListHead
0x1c00125fd  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0012604  nop     dword ptr [rax+rax+00h]
0x1c0012609  mov     rsi, rax
0x1c001260c  test    rax, rax
0x1c001260f  jz      loc_1C0012840
0x1c0012615  mov     ebx, 1
0x1c001261a  test    rsi, rsi
0x1c001261d  jz      loc_1C0025F95
0x1c0012623  xor     edx, edx; Val
0x1c0012625  mov     r8d, 90h; Size
0x1c001262b  mov     rcx, rsi; void *
0x1c001262e  call    memset
0x1c0012633  mov     dword ptr [rsi+10h], 50526C55h
0x1c001263a  mov     qword ptr [rsi+50h], 0
0x1c0012642  mov     qword ptr [rsi+60h], 0
0x1c001264a  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0012650  test    al, al
0x1c0012652  js      loc_1C0025F4E
0x1c0012658  mov     eax, [rsi+7Ch]
0x1c001265b  and     eax, 0FFFFFFFEh
0x1c001265e  mov     [rsi+74h], edi
0x1c0012661  or      eax, ebx
0x1c0012663  mov     [rsi+80h], r12
0x1c001266a  mov     [rsi+7Ch], eax
0x1c001266d  mov     dword ptr [rsi+14h], 1
0x1c0012674  cmp     byte ptr [r14+4Fh], 0
0x1c0012679  jz      short loc_1C0012689
0x1c001267b  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1c0012681  test    eax, eax
0x1c0012683  jnz     loc_1C0025F72
0x1c0012689  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c001268f  test    al, al
0x1c0012691  js      loc_1C0025FBA
0x1c0012697  test    rsi, rsi
0x1c001269a  jz      loc_1C0025FD4
0x1c00126a0  cmp     byte ptr [r14+4Fh], 0
0x1c00126a5  jz      short loc_1C00126B5
0x1c00126a7  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1c00126ad  test    eax, eax
0x1c00126af  jnz     loc_1C0025FE8
0x1c00126b5  xor     r8d, r8d
0x1c00126b8  mov     [rsi+70h], r15d
0x1c00126bc  mov     [rsp+0E8h+var_9C], r8d
0x1c00126c1  test    r13, r13
0x1c00126c4  jz      loc_1C0012781
0x1c00126ca  mov     rbx, [r13+8]
0x1c00126ce  mov     edx, [r13+10h]
0x1c00126d2  mov     r12, [r13+18h]
0x1c00126d6  mov     r13, [r13+0]
0x1c00126da  mov     [rsp+0E8h+var_98], edx
0x1c00126de  test    rbx, rbx
0x1c00126e1  jz      loc_1C0012773
0x1c00126e7  test    r12, r12
0x1c00126ea  jz      loc_1C0012773
0x1c00126f0  mov     eax, [rbx+28h]
0x1c00126f3  cmp     edx, eax
0x1c00126f5  jnb     loc_1C002602E
0x1c00126fb  test    byte ptr [rbx+0Ah], 5
0x1c00126ff  jz      loc_1C0012807
0x1c0012705  mov     r10, [rbx+18h]
0x1c0012709  test    r10, r10
0x1c001270c  jz      loc_1C002603D
0x1c0012712  mov     r14d, [rbx+28h]
0x1c0012716  mov     rcx, r15
0x1c0012719  mov     r9d, r8d
0x1c001271c  sub     r14d, edx
0x1c001271f  sub     rcx, r9
0x1c0012722  cmp     rcx, r14
0x1c0012725  ja      short loc_1C001272D
0x1c0012727  mov     r14d, r15d
0x1c001272a  sub     r14d, r8d
0x1c001272d  mov     eax, r14d
0x1c0012730  cmp     rax, r12
0x1c0012733  ja      loc_1C0026035
0x1c0012739  lea     rcx, [r9+88h]
0x1c0012740  mov     r8d, r14d; Size
0x1c0012743  add     rcx, rsi; void *
0x1c0012746  mov     edi, r14d
0x1c0012749  add     rdx, r10; Src
0x1c001274c  call    memmove
0x1c0012751  mov     r8d, [rsp+0E8h+var_9C]
0x1c0012756  sub     r12, rdi
0x1c0012759  add     r8d, r14d
0x1c001275c  mov     [rsp+0E8h+var_9C], r8d
0x1c0012761  xor     edx, edx
0x1c0012763  mov     rbx, [rbx]
0x1c0012766  mov     [rsp+0E8h+var_98], edx
0x1c001276a  test    rbx, rbx
0x1c001276d  jnz     loc_1C00126E7
0x1c0012773  test    r13, r13
0x1c0012776  jnz     loc_1C00126CA
0x1c001277c  mov     r14, [rsp+0E8h+var_90]
0x1c0012781  mov     [rsi+30h], rbp
0x1c0012785  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 2000h
0x1c001278f  jnz     loc_1C002606D
0x1c0012795  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c001279b  test    al, al
0x1c001279d  js      loc_1C0026093
0x1c00127a3  mov     eax, [rsp+0E8h+var_A4]
0x1c00127a7  mov     rdx, rsi
0x1c00127aa  movzx   r9d, [rsp+0E8h+var_A8]
0x1c00127b0  mov     rcx, rbp
0x1c00127b3  mov     r8, [rsp+0E8h+var_88]
0x1c00127b8  mov     byte ptr [rsp+0E8h+Priority], 0
0x1c00127bd  mov     [rsp+0E8h+BugCheckOnFailure], eax
0x1c00127c1  call    UlpTransformAndQueueRequestBuffers
0x1c00127c6  mov     ebx, eax
0x1c00127c8  test    eax, eax
0x1c00127ca  js      loc_1C002605C
0x1c00127d0  xor     ebx, ebx
0x1c00127d2  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00127d8  test    al, al
0x1c00127da  js      loc_1C0026167
0x1c00127e0  mov     eax, ebx
0x1c00127e2  mov     rcx, [rsp+0E8h+var_50]
0x1c00127ea  xor     rcx, rsp; StackCookie
0x1c00127ed  call    __security_check_cookie
0x1c00127f2  add     rsp, 0A8h
0x1c00127f9  pop     r15
0x1c00127fb  pop     r14
0x1c00127fd  pop     r13
0x1c00127ff  pop     r12
0x1c0012801  pop     rdi
0x1c0012802  pop     rsi
0x1c0012803  pop     rbp
0x1c0012804  pop     rbx
0x1c0012805  retn
0x1c0012807  xor     r9d, r9d; RequestedAddress
0x1c001280a  mov     [rsp+0E8h+Priority], 40000000h; Priority
0x1c0012812  xor     edx, edx; AccessMode
0x1c0012814  mov     [rsp+0E8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1c001281c  mov     rcx, rbx; MemoryDescriptorList
0x1c001281f  lea     r8d, [r9+1]; CacheType
0x1c0012823  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1c001282a  nop     dword ptr [rax+rax+00h]
0x1c001282f  mov     edx, [rsp+0E8h+var_98]
0x1c0012833  mov     r10, rax
0x1c0012836  mov     r8d, [rsp+0E8h+var_9C]
0x1c001283b  jmp     loc_1C0012709
0x1c0012840  mov     r8d, [rbx+28h]
0x1c0012844  mov     r9, rbx
0x1c0012847  mov     edx, [rbx+2Ch]
0x1c001284a  mov     ecx, [rbx+24h]
0x1c001284d  mov     rax, [rbx+30h]
0x1c0012851  inc     dword ptr [rbx+18h]
0x1c0012854  call    cs:__guard_dispatch_icall_fptr
0x1c001285a  mov     rsi, rax
0x1c001285d  jmp     loc_1C0012615
0x1c0012862  lea     eax, [rdi+90h]
0x1c0012868  cmp     edi, eax
0x1c001286a  ja      short loc_1C0012897
0x1c001286c  lea     rdx, [rdi+90h]; NumberOfBytes
0x1c0012873  xor     r9d, r9d; Priority
0x1c0012876  mov     ecx, 200h; PoolType
0x1c001287b  mov     r8d, 50526C55h; Tag
0x1c0012881  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c0012888  nop     dword ptr [rax+rax+00h]
0x1c001288d  mov     rsi, rax
0x1c0012890  xor     ebx, ebx
0x1c0012892  jmp     loc_1C001261A
0x1c0012897  xor     esi, esi
0x1c0012899  jmp     loc_1C0025F95
0x1c0025db4  mov     qword ptr [rsp+0E8h+Priority], r15
0x1c0025db9  mov     r9d, edx
0x1c0025dbc  mov     r8, rbp
0x1c0025dbf  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], r13
0x1c0025dc4  call    WPP_SF_qLqP
0x1c0025dc9  nop
0x1c0025dca  jmp     loc_1C001246E
0x1c0025dcf  movzx   edx, dil; NewIrql
0x1c0025dd3  lea     rcx, [rbp+210h]; SpinLock
0x1c0025dda  call    cs:__imp_KeReleaseSpinLock
0x1c0025de1  nop     dword ptr [rax+rax+00h]
0x1c0025de6  mov     ebx, esi
0x1c0025de8  jmp     loc_1C00127D2
0x1c0025ded  mov     r9, [rbp+18h]
0x1c0025df1  lea     rax, [rsp+0E8h+var_A0]
0x1c0025df6  mov     [rsp+0E8h+var_B8], rax
0x1c0025dfb  mov     r8, rbp
0x1c0025dfe  lea     rax, [rsp+0E8h+var_A4]
0x1c0025e03  mov     qword ptr [rsp+0E8h+Priority], rax
0x1c0025e08  mov     [rsp+0E8h+BugCheckOnFailure], r14d
0x1c0025e0d  call    WPP_SF_qilqq
0x1c0025e12  nop
0x1c0025e13  jmp     loc_1C00124AE
0x1c0025e18  mov     r10d, 3
0x1c0025e1e  mov     r8d, 0Ch
0x1c0025e24  mov     [rsp+0E8h+var_A4], r10d
0x1c0025e29  mov     [rsp+0E8h+var_A0], r8d
0x1c0025e2e  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
  ... truncated ...
```
