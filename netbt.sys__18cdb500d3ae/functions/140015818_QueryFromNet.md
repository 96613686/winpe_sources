# QueryFromNet

- ea: `0x140015818`
- end: `0x1400167ce`
- name: `QueryFromNet`
- size: `4022`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140009150`

## callees

- `0x140005fb0`
- `0x140007978`
- `0x1400079a8`
- `0x140007c4c`
- `0x140007ed8`
- `0x140008160`
- `0x1400089c8`
- `0x140009600`
- `0x14000e31c`
- `0x140015818`
- `0x1400167d4`
- `0x140016c14`
- `0x140017140`
- `0x140017198`
- `0x1400171d8`
- `0x140017214`
- `0x1400242e0`
- `0x1400247f8`
- `0x14002571c`
- `0x140027b78`
- `0x14002bd9c`
- `0x140030f40`
- `0x140030f80`
- `0x140031440`
- `0x140040294`
- `0x1400402b4`
- `0x140040b90`
- `0x140040c40`
- `0x140040d78`
- `0x140040e08`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140015dab`
- `ntoskrnl!KeCancelTimer` at `0x140015dab`
- `ntoskrnl!RtlCompareMemory` at `0x1400159c5`
- `ntoskrnl!RtlCompareMemory` at `0x1400159c5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015969`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015aa7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015b6d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015eeb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016055`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016664`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015969`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015aa7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015b6d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015eeb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016055`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016664`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400159dd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015adc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015c64`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015d11`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015e98`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015f0f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400165e8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001662c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400166bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400159dd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015adc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015c64`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015d11`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015e98`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015f0f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400165e8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001662c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400166bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016298`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016361`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015d2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016298`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016361`
- `ntoskrnl!ExAllocatePool2` at `0x140016138`
- `ntoskrnl!ExAllocatePool2` at `0x140016138`

## pseudocode

```c
__int64 __fastcall QueryFromNet(__int64 a1, __int64 a2, char *a3, int a4, signed __int16 a5, char a6)
{
  unsigned int v7; // r12d
  unsigned __int16 v8; // r13
  char *v9; // r15
  unsigned int v10; // r12d
  int v11; // r8d
  __int128 *p_Source1; // r10
  int *v13; // r9
  int v14; // r11d
  int v15; // edx
  __int16 v16; // ax
  int v17; // edx
  int v18; // ecx
  int v19; // r8d
  int *v20; // rax
  int v21; // r14d
  unsigned int v22; // r14d
  KIRQL v23; // si
  __int64 v25; // r9
  __int64 v26; // r8
  __int64 v27; // rsi
  __int64 v28; // rcx
  KIRQL v29; // r11
  __int64 v30; // r9
  unsigned int v31; // r8d
  unsigned int v32; // ecx
  int v33; // edx
  __int64 v34; // r13
  __int64 *v35; // rbx
  __int64 v36; // rsi
  __int64 v37; // r11
  __int16 v38; // ax
  __int64 v39; // rax
  unsigned int v40; // r14d
  __int64 v41; // r11
  __int64 v42; // rax
  PVOID v43; // rcx
  __int64 v44; // r10
  KIRQL v45; // dl
  __int64 v46; // r9
  __int64 v47; // rcx
  KIRQL v48; // dl
  char v49; // al
  bool v50; // zf
  __int64 v51; // r14
  __int64 v52; // rax
  __int64 *v53; // rcx
  char v54; // al
  int v55; // r11d
  __int64 v56; // rax
  KIRQL v57; // r12
  PVOID v58; // rsi
  unsigned int updated; // ebx
  KIRQL v60; // r12
  __int64 v61; // rcx
  void *Pool2; // rax
  _DWORD *v63; // rsi
  __int64 v64; // r14
  __int64 v65; // rbx
  __int64 v66; // r15
  unsigned int v67; // r12d
  unsigned int v68; // r8d
  int v69; // r10d
  __int64 v70; // r12
  _DWORD *v71; // rdi
  __int64 v72; // rdx
  __int64 v73; // r9
  __int64 v74; // r15
  unsigned int j; // r8d
  int v76; // ecx
  unsigned int v77; // edx
  __int64 v78; // r9
  int v79; // eax
  void (__fastcall *v80)(_QWORD, __int64, _QWORD); // rax
  __int64 v81; // rdx
  char IsNameServer; // al
  __int16 v83; // r11
  _DWORD *v84; // rbx
  int v85; // r8d
  unsigned int i; // edx
  __int64 v87; // rsi
  const char *v88; // r9
  KIRQL v89; // al
  __int64 v90; // rbx
  int v91; // r8d
  int v92; // eax
  int v93; // r8d
  int v94; // r9d
  PVOID v95; // rbx
  int v96; // edx
  __int64 v97; // r13
  int v98; // r8d
  const char *v99; // rcx
  const char *v100; // rcx
  int v101; // [rsp+28h] [rbp-A1h]
  int v102; // [rsp+38h] [rbp-91h]
  KIRQL v103; // [rsp+38h] [rbp-91h]
  KIRQL NewIrql; // [rsp+50h] [rbp-79h]
  unsigned __int16 v105; // [rsp+52h] [rbp-77h]
  PVOID v106; // [rsp+58h] [rbp-71h] BYREF
  unsigned int v107; // [rsp+60h] [rbp-69h]
  PVOID P; // [rsp+68h] [rbp-61h]
  __int64 v109; // [rsp+70h] [rbp-59h]
  unsigned int v110; // [rsp+78h] [rbp-51h]
  unsigned int v111; // [rsp+7Ch] [rbp-4Dh]
  __int64 v112; // [rsp+80h] [rbp-49h]
  __int64 v113; // [rsp+88h] [rbp-41h]
  char *v114; // [rsp+90h] [rbp-39h]
  __int64 v115; // [rsp+98h] [rbp-31h]
  int *v116; // [rsp+A0h] [rbp-29h]
  _QWORD *v117; // [rsp+A8h] [rbp-21h]
  __int64 v118; // [rsp+B0h] [rbp-19h]
  __int128 Source1; // [rsp+B8h] [rbp-11h] BYREF

  v7 = *(_DWORD *)(a2 + 10);
  v8 = __ROR2__(*(_WORD *)(a2 + 8), 8);
  v9 = a3;
  v114 = a3;
  v113 = a2;
  v109 = a1;
  v106 = 0;
  v105 = v8;
  v10 = _byteswap_ulong(v7);
  v110 = v10;
  if ( a4 < (unsigned __int16)word_1400395DC + 49 )
    return 3221226011LL;
  v11 = a4 - 13;
  if ( a4 - 13 <= 33 || v9[12] != 32 )
    return 3221226011LL;
  p_Source1 = &Source1;
  v13 = (int *)(v9 + 13);
  v14 = 8;
  do
  {
    v15 = *v13++;
    v15 -= 1094795585;
    v18 = v15 >> 16;
    LOWORD(v18) = 16 * (v15 & 0xF) + (HIWORD(v15) & 0xF00);
    v16 = (v15 >> 8) & 0xF;
    v17 = v15 >> 4;
    LOWORD(v17) = v17 & 0xF000;
    LOWORD(v18) = v17 + v16 + v18;
    *(_WORD *)p_Source1 = v18;
    p_Source1 = (__int128 *)((char *)p_Source1 + 2);
    --v14;
  }
  while ( v14 );
  v19 = v11 - 34;
  v116 = v13;
  v20 = v13;
  v21 = 0;
  if ( v19 <= 0 )
  {
LABEL_9:
    if ( *(_BYTE *)v20 )
      return 3221226011LL;
  }
  else
  {
    while ( *(_BYTE *)v20 )
    {
      ++v21;
      v20 = (int *)((char *)v20 + 1);
      if ( v21 >= v19 )
        goto LABEL_9;
    }
  }
  if ( v21 > 240 )
    return 3221226011LL;
  v22 = v21 + 33;
  v111 = v22;
  if ( (a5 & 0x80u) != 0 )
  {
    if ( (a5 & 4) == 0 )
      return 3221226011LL;
    v27 = (__int64)&v9[v22 + 13];
    v118 = (int)v22;
    if ( *(_BYTE *)(v27 + 1) == 33 )
    {
      v29 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
      if ( byte_140039758 || (unsigned __int8)IsAddrOnLocalSubnet(v10) || (unsigned __int8)SrcIsNameServer(v61, v8) )
      {
        KeReleaseSpinLock(&SpinLock, v29);
        if ( a4 >= (int)(v22 + 24) && a4 >= (int)(v22 + 24 + 18 * (unsigned __int8)v9[v22 + 23]) )
          DecodeNodeStatusResponse((_DWORD)v9, a4, (unsigned int)&Source1, v22, v10);
        return 3221226011LL;
      }
LABEL_60:
      v45 = v29;
      goto LABEL_51;
    }
    KeAcquireSpinLockRaiseToDpc(&SpinLock);
    if ( (unsigned __int8)SrcIsUs(v10) && !pWinsInfo
      || !byte_140039758 && !(unsigned __int8)IsAddrOnLocalSubnet(v28) && !(unsigned __int8)SrcIsNameServer(v47, v8) )
    {
      goto LABEL_60;
    }
    KeReleaseSpinLock(&SpinLock, v29);
    a5 &= 0xF00u;
    if ( a4 < (int)(v22 + (a5 != 0 ? 23 : 29)) )
      return 3221226011LL;
    v30 = v27 + 10;
    v31 = (unsigned __int16)__ROR2__(*(_WORD *)(v27 + 8), 8);
    P = 0;
    v112 = v27 + 10;
    v32 = a4 + -(v22 + 13) - 10;
    if ( v31 >= v32 )
      v31 = a4 + -(v22 + 13) - 10;
    v33 = (2863311531u * (unsigned __int64)v31) >> 32;
    v107 = v31;
    LODWORD(v34) = v31 / 6;
    if ( byte_1400395D4 && (__int16)__ROR2__(*(_WORD *)v30, 8) >= 0 && (_DWORD)v34 && 6 * (_DWORD)v34 == v31 )
    {
      Pool2 = (void *)ExAllocatePool2(64, 8LL * (unsigned int)v34, 858874446);
      P = Pool2;
      v63 = Pool2;
      if ( Pool2 )
      {
        memset(Pool2, 0, 8LL * (unsigned int)v34);
        v64 = v109;
        v65 = 0;
        v66 = v112;
        v67 = 0;
        do
        {
          v63[2 * v65] = *(_DWORD *)(v66 + 6 * v65 + 2);
          NbtGetOutgoingInterfaceForSend(*(unsigned int *)(v66 + 6 * v65 + 2), v64, &v63[2 * v65 + 1]);
          ++v67;
          ++v65;
        }
        while ( v67 < (unsigned int)v34 );
        v22 = v111;
        v9 = v114;
        v10 = v110;
      }
      v30 = v112;
    }
    if ( (BYTE11(xmmword_140038420) & 2) != 0 )
      WPP_SF_sdD(v32, v33, v31, (unsigned int)&Source1, v34, *(_DWORD *)(v30 + 2));
    NewIrql = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    v35 = &qword_1400394A0;
    while ( 1 )
    {
      v35 = (__int64 *)*v35;
      if ( v35 == &qword_1400394A0 )
      {
        if ( (_BYTE)word_140039670 )
          goto LABEL_63;
        if ( (int)FindInHashTable(qword_140039468, &Source1, v116, &v106) < 0 )
          goto LABEL_164;
        v84 = v106;
        v85 = *((_DWORD *)v106 + 18);
        if ( (v85 & 0x800) != 0 )
          goto LABEL_164;
        for ( i = 0; i < *((unsigned __int16 *)v106 + 64); ++i )
        {
          if ( *(_DWORD *)(*((_QWORD *)v106 + 3) + 16LL * i) == v10 )
            goto LABEL_164;
        }
        if ( (v85 & 0x10) == 0 || (v85 & 2) == 0 || (v87 = v109, (unsigned __int8)IsNameServerForDevice(v10, v109)) )
        {
LABEL_164:
          v60 = NewIrql;
        }
        else
        {
          if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
            WPP_SF_qddds(
              v84[5],
              12,
              (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
              (_DWORD)v84,
              v84[5],
              v84[5] + 1,
              237,
              (__int64)"minio\\netbt\\sys\\inbound.c");
          NbtReferenceName(v84, 13);
          LOBYTE(v102) = NewIrql;
          UdpSendResponse(v22, v9, v84, v113 + 8, v87, 7, 6, v102);
          v60 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
          v84[18] = v84[18] & 0xFFFFFF0F | 0x20;
          NbtCheckNameAddrTimer(v84);
          if ( v84[5] == 2 )
            NbtDereferenceName(v84, (__int64)"minio\\netbt\\sys\\inbound.c");
          NbtDereferenceName(v84, (__int64)"minio\\netbt\\sys\\inbound.c");
        }
        v48 = v60;
LABEL_64:
        KeReleaseSpinLock(&SpinLock, v48);
        goto LABEL_65;
      }
      v36 = v35[14];
      if ( v36 )
      {
        v37 = *(_QWORD *)(v36 + 48);
        v117 = (_QWORD *)(v36 + 48);
        v38 = *(_WORD *)v9;
        v115 = v37;
        if ( *(_WORD *)(v37 + 128) == v38 )
        {
          v39 = *(__int64 *)((char *)v35 + 164) - Source1;
          if ( !v39 )
            v39 = *(__int64 *)((char *)v35 + 172) - *((_QWORD *)&Source1 + 1);
          if ( !v39 )
            break;
        }
      }
    }
    v40 = *(_DWORD *)(v37 + 240);
    v111 = v40;
    if ( (unsigned __int8)SrcIsNameServer(v10, v105) && (v40 & 8) != 0 )
      *(_WORD *)(*(_QWORD *)(v41 + 32) + 554LL) = *(_WORD *)(v41 + 204);
    if ( !*((_BYTE *)v35 + 132) && a5 )
    {
      if ( (NodeType & 0xE) != 0 && (v40 & 6) != 0 )
      {
        *(_DWORD *)(v41 + 240) |= 0x200u;
        ExpireTimer((PVOID)v36);
LABEL_65:
        if ( P )
          ExFreePoolWithTag(P, 0);
        return 3221226011LL;
      }
LABEL_63:
      v48 = NewIrql;
      goto LABEL_64;
    }
    v42 = v35[8];
    v43 = P;
    if ( v42 )
    {
      if ( P )
      {
        v68 = 0;
        v69 = *(_DWORD *)(*(_QWORD *)(v42 + 32) + 700LL);
        if ( (_DWORD)v34 )
        {
          v70 = v112;
          v71 = P;
          do
          {
            if ( v71[2 * v68 + 1] != v69 )
            {
              v50 = (_DWORD)v34 == 1;
              v34 = (unsigned int)(v34 - 1);
              if ( v50 )
              {
                v73 = 0;
              }
              else
              {
                v71[2 * v68 + 1] = v71[2 * v34 + 1];
                v72 = 3LL * v68;
                v73 = (unsigned int)v34;
                *(_DWORD *)(v70 + 2 * v72) = *(_DWORD *)(v70 + 6 * v34);
                *(_WORD *)(v70 + 2 * v72 + 4) = *(_WORD *)(v70 + 6 * v34 + 4);
              }
              --v68;
              *(_DWORD *)(v70 + 6 * v73 + 2) = 0;
            }
            ++v68;
          }
          while ( v68 < (unsigned int)v34 );
          v10 = v110;
          v43 = P;
        }
        ExFreePoolWithTag(v43, 0);
        v41 = v115;
        P = 0;
      }
      v44 = *(_QWORD *)(v35[8] + 192);
      if ( v44 && *(_QWORD *)(v36 + 72) )
      {
        v74 = v112;
        for ( j = 0; j < 0xA; ++j )
        {
          v76 = *(_DWORD *)(v44 + 4LL * j);
          if ( !v76 )
            break;
          if ( (_DWORD)v34 )
          {
            v77 = 0;
            do
            {
              v78 = 3LL * v77;
              if ( v76 == _byteswap_ulong(*(_DWORD *)(v74 + 6LL * v77 + 2)) )
              {
                v34 = (unsigned int)(v34 - 1);
                --v77;
                *(_DWORD *)(v74 + 2 * v78) = *(_DWORD *)(v74 + 6 * v34);
                *(_WORD *)(v74 + 2 * v78 + 4) = *(_WORD *)(v74 + 6 * v34 + 4);
                *(_DWORD *)(v74 + 6 * v34 + 2) = 0;
                v76 = *(_DWORD *)(v44 + 4LL * j);
              }
              ++v77;
            }
            while ( v77 < (unsigned int)v34 );
          }
        }
        v9 = v114;
        v10 = v110;
      }
      v107 = 6 * v34;
      if ( !(6 * (_DWORD)v34) )
      {
        if ( (NodeType & 0xE) == 0 || (v79 = *(_DWORD *)(v41 + 240), (v79 & 6) == 0) )
        {
          v45 = NewIrql;
          goto LABEL_51;
        }
        *(_DWORD *)(v41 + 240) = v79 | 0x200;
        ExpireTimer((PVOID)v36);
        return 3221226011LL;
      }
      *(_DWORD *)(v35[8] + 184) = *(_DWORD *)(v41 + 240);
      *(_WORD *)(v35[8] + 204) = *(_WORD *)(v41 + 204);
      *(_WORD *)(v35[8] + 206) = *(_WORD *)(v41 + 206);
    }
    else if ( P )
    {
      ExFreePoolWithTag(P, 0);
      v41 = v115;
      P = 0;
    }
    v114 = *(char **)(v41 + 32);
    v35[14] = 0;
    if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
      WPP_SF_qddds(
        *((_DWORD *)v35 + 5),
        12,
        (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
        (_DWORD)v35,
        *((_DWORD *)v35 + 5),
        *((_DWORD *)v35 + 5) + 1,
        32,
        (__int64)"minio\\netbt\\sys\\inbound.c");
    NbtReferenceName(v35, 1);
    v49 = *(_BYTE *)(v36 + 23);
    if ( v49 == 1 )
    {
      v50 = (*(_BYTE *)(v36 + 256) & 8) == 0;
      v51 = *(_QWORD *)(v36 + 72);
      v106 = *(PVOID *)(v36 + 64);
      *(_QWORD *)(v36 + 72) = 0;
      if ( v50 && !KeCancelTimer((PKTIMER)(v36 + 192)) )
      {
        v80 = *(void (__fastcall **)(_QWORD, __int64, _QWORD))(v36 + 40);
        if ( v80 )
        {
          v81 = *(_QWORD *)(v36 + 56);
          *(_QWORD *)(v36 + 40) = 0;
          v80(*v117, v81, 0);
        }
        *(_BYTE *)(v36 + 23) = 2;
      }
      else
      {
        CleanupCTETimer((PVOID)v36);
      }
    }
    else
    {
      if ( v49 != 2 )
        goto LABEL_86;
      v51 = *(_QWORD *)(v36 + 72);
      if ( v51 )
      {
        v106 = *(PVOID *)(v36 + 64);
        *(_QWORD *)(v36 + 72) = 0;
      }
      else
      {
        v51 = 0;
        v106 = 0;
      }
      *(_BYTE *)(v36 + 23) = 3;
    }
    if ( v51 )
    {
      v52 = *v35;
      if ( *(__int64 **)(*v35 + 8) != v35 || (v53 = (__int64 *)v35[1], (__int64 *)*v53 != v35) )
        __fastfail(3u);
      *v53 = v52;
      *(_QWORD *)(v52 + 8) = v53;
      v35[1] = (__int64)v35;
      *v35 = (__int64)v35;
      if ( a5 )
      {
        *((_DWORD *)v35 + 18) = v35[9] & 0xFFFFFF0F | 0x20;
        NbtCheckNameAddrTimer(v35);
        if ( (NodeType & 0x10) != 0 )
        {
          if ( *((_BYTE *)v35 + 132) != 2 )
          {
            IsNameServer = SrcIsNameServer(v10, v105);
            AddToHashTable(
              qword_140039468,
              (char *)v35 + 164,
              Str2,
              *((unsigned int *)v35 + 8),
              0,
              v35,
              0,
              v114,
              v83 + (IsNameServer != 0 ? 0xFFF0 : 0));
          }
        }
        else
        {
          NbtDereferenceName(v35, (__int64)"minio\\netbt\\sys\\inbound.c");
        }
        v58 = v106;
        updated = -1073741634;
        v57 = NewIrql;
      }
      else
      {
        v54 = SrcIsNameServer(v10, v105);
        if ( !v54 )
        {
          *(_OWORD *)&NameStatsInfo[16 * dword_140039390++ + 20] = Source1;
          if ( (unsigned int)dword_140039390 >= 8 )
            dword_140039390 = v55;
        }
        v56 = v54 != 0 ? 8 : 0;
        ++*(_DWORD *)&NameStatsInfo[v56];
        if ( (NodeType & 0x10) != 0 )
        {
          *((_BYTE *)v35 + 133) = (v9[v118 + 23] & 0x60) == 32;
          if ( SBYTE3(xmmword_140038420) < (char)v55 )
            WPP_SF_sD(
              1055,
              11,
              (unsigned int)WPP_80b00531435b366d117ee6d697c26c58_Traceguids,
              (_DWORD)v35 + 164,
              *((_BYTE *)v35 + 179));
        }
        v35[10] |= *((_QWORD *)v114 + 70);
        SrcIsNameServer(v10, v105);
        v57 = NewIrql;
        v58 = v106;
        updated = UpdateNameState(v112, v35, v107);
      }
      if ( (v111 & 0x200) == 0 && *(_DWORD *)(v113 + 10) == _byteswap_ulong(*(_DWORD *)(v109 + 508)) )
        SwitchToBackup();
      KeReleaseSpinLock(&SpinLock, v57);
      if ( updated != 259 )
        CompleteClientReq(v51, v58, updated);
      return 3221226011LL;
    }
LABEL_86:
    NbtDereferenceName(v35, (__int64)"minio\\netbt\\sys\\inbound.c");
    goto LABEL_63;
  }
  if ( (BYTE11(xmmword_140038420) & 2) != 0 )
  {
    v88 = "Broad";
    if ( !a6 )
      v88 = "Uni";
    WPP_SF_ss(v18, v17, v19, (_DWORD)v88, (__int64)&Source1);
  }
  if ( a4 >= (int)(v22 + 17) )
  {
    v23 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    if ( (int)FindInHashTable(qword_140039460, &Source1, v116, &v106) >= 0 && (*((_DWORD *)v106 + 18) & 0x90) != 0 )
    {
      if ( v9[v22 + 14] != 33 )
      {
        if ( !(unsigned __int8)SrcIsUs(v10) || !_bittest16(&a5, 0xCu) && pWinsInfo != v46 )
        {
          v103 = v23;
          v101 = v46;
          v25 = v113 + 8;
          goto LABEL_24;
        }
        goto LABEL_50;
      }
      KeReleaseSpinLock(&SpinLock, v23);
      if ( a6 )
      {
        if ( (BYTE3(xmmword_140038420) & 2) != 0 )
          WPP_SF_(1049, 13, WPP_80b00531435b366d117ee6d697c26c58_Traceguids);
        return 3221226011LL;
      }
LABEL_19:
      SendNodeStatusResponse(v9, (unsigned int)a4, v10, v8, v109);
      return 3221226011LL;
    }
    if ( v9[v22 + 14] == 33 && !a6 && RtlCompareMemory(&Source1, "*", 0x10u) == 16 )
    {
      KeReleaseSpinLock(&SpinLock, v23);
      goto LABEL_19;
    }
    if ( !_bittest16(&a5, 0xCu) )
    {
      if ( v9[v22 + 14] == 32 )
      {
        v103 = v23;
        v101 = 0;
        v25 = v113 + 8;
        v26 = 0;
LABEL_24:
        UdpSendResponse(v22, v9, v26, v25, v109, v101, 3, v103);
        return 3221226011LL;
      }
      goto LABEL_50;
    }
    KeReleaseSpinLock(&SpinLock, v23);
    if ( !(unsigned __int8)SrcIsUs(v10) && (NodeType & 0x10) != 0 && v9[v22 + 14] == 32 )
    {
      v89 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
      v90 = (__int64)v116;
      v23 = v89;
      if ( (int)FindInHashTable(qword_140039468, &Source1, v116, &v106) < 0 )
      {
        LOBYTE(v91) = 1;
        v92 = FindOnPendingList((unsigned int)&Source1, (_DWORD)v9, v91, 0, (__int64)&v106);
        v45 = v23;
        if ( v92 < 0 )
        {
          KeReleaseSpinLock(&SpinLock, v23);
          RegOrQueryFromNet(0, v109, v93, v94, (__int64)&Source1, v90);
          return 3221226011LL;
        }
        goto LABEL_51;
      }
      v95 = v106;
      v96 = *((_DWORD *)v106 + 18);
      if ( (v96 & 0x10) != 0 )
      {
        v97 = v109;
        v98 = *((_DWORD *)v106 + 8);
        if ( (v10 & *(_DWORD *)(v109 + 492)) != (v98 & *(_DWORD *)(v109 + 492))
          || *((_BYTE *)v106 + 133)
          || (v96 & 2) == 0 )
        {
          if ( SBYTE3(xmmword_140038420) < 0 )
          {
            v99 = "UNIQUE";
            if ( (v96 & 2) == 0 )
              v99 = "INET_GROUP";
            WPP_SF_sDsd((_DWORD)v99, v96, v98, (_DWORD)v106 + 164, *((_BYTE *)v106 + 179), (__int64)v99, v98);
          }
          UdpSendResponse(v22, v9, v95, v113 + 8, v97, 0, 3, v23);
          return 3221226011LL;
        }
      }
      else if ( SBYTE3(xmmword_140038420) < 0 )
      {
        v100 = "RELEASED";
        if ( (v96 & 0x20) == 0 )
          v100 = "RESOLVING";
        WPP_SF_sDs((_DWORD)v100, v96, v91, (_DWORD)v106 + 164, *((_BYTE *)v106 + 179), (__int64)v100);
      }
LABEL_50:
      v45 = v23;
LABEL_51:
      KeReleaseSpinLock(&SpinLock, v45);
    }
  }
  return 3221226011LL;
}

```

## disassembly

```asm
0x140015818  push    rbp
0x14001581a  push    rbx
0x14001581b  push    rsi
0x14001581c  push    rdi
0x14001581d  push    r12
0x14001581f  push    r13
0x140015821  push    r14
0x140015823  push    r15
0x140015825  lea     rbp, [rsp-0Fh]
0x14001582a  sub     rsp, 0D8h
0x140015831  mov     rax, cs:__security_cookie
0x140015838  xor     rax, rsp
0x14001583b  mov     [rbp+47h+var_48], rax
0x14001583f  movzx   r13d, word ptr [rdx+8]
0x140015844  xor     edi, edi
0x140015846  movzx   eax, cs:word_1400395DC
0x14001584d  mov     ebx, r9d
0x140015850  mov     r12d, [rdx+0Ah]
0x140015854  add     eax, 31h ; '1'
0x140015857  ror     r13w, 8
0x14001585c  mov     r15, r8
0x14001585f  mov     [rbp+47h+var_80], r8
0x140015863  mov     [rbp+47h+var_88], rdx
0x140015867  mov     [rbp+47h+var_A0], rcx
0x14001586b  mov     [rbp+47h+var_B8], rdi
0x14001586f  mov     [rbp+47h+var_BE], r13w
0x140015874  bswap   r12d
0x140015877  mov     [rbp+47h+var_98], r12d
0x14001587b  cmp     r9d, eax
0x14001587e  jl      loc_140015A0D
0x140015884  lea     r8d, [r9-0Dh]
0x140015888  cmp     r8d, 21h ; '!'
0x14001588c  jle     loc_140015A0D
0x140015892  cmp     byte ptr [r15+0Ch], 20h ; ' '
0x140015897  jnz     loc_140015A0D
0x14001589d  lea     r10, [rbp+47h+Source1]
0x1400158a1  mov     esi, 0F00h
0x1400158a6  lea     r9, [r15+0Dh]
0x1400158aa  lea     r11d, [rdi+8]
0x1400158ae  mov     edx, [r9]
0x1400158b1  add     r9, 4
0x1400158b5  add     edx, 0BEBEBEBFh
0x1400158bb  movzx   eax, dx
0x1400158be  mov     ecx, edx
0x1400158c0  and     ax, 0Fh
0x1400158c4  sar     ecx, 10h
0x1400158c7  shl     ax, 4
0x1400158cb  and     cx, si
0x1400158ce  add     cx, ax
0x1400158d1  mov     eax, edx
0x1400158d3  sar     eax, 8
0x1400158d6  and     ax, 0Fh
0x1400158da  sar     edx, 4
0x1400158dd  add     cx, ax
0x1400158e0  mov     eax, 0F000h
0x1400158e5  and     dx, ax
0x1400158e8  add     cx, dx
0x1400158eb  mov     [r10], cx
0x1400158ef  lea     r10, [r10+2]
0x1400158f3  sub     r11d, 1
0x1400158f7  jnz     short loc_1400158AE
0x1400158f9  add     r8d, 0FFFFFFDEh
0x1400158fd  mov     [rbp+47h+var_70], r9
0x140015901  mov     rax, r9
0x140015904  mov     r14d, edi
0x140015907  test    r8d, r8d
0x14001590a  jle     short loc_14001591C
0x14001590c  cmp     [rax], dil
0x14001590f  jz      short loc_140015925
0x140015911  inc     r14d
0x140015914  inc     rax
0x140015917  cmp     r14d, r8d
0x14001591a  jl      short loc_14001590C
0x14001591c  cmp     [rax], dil
0x14001591f  jnz     loc_140015A0D
0x140015925  cmp     r14d, 0F0h
0x14001592c  jg      loc_140015A0D
0x140015932  movzx   eax, [rbp+47h+arg_20]
0x140015936  add     r14d, 21h ; '!'
0x14001593a  mov     [rbp+47h+var_94], r14d
0x14001593e  test    al, al
0x140015940  js      loc_140015A81
0x140015946  test    byte ptr cs:xmmword_140038420+0Bh, 2
0x14001594d  jnz     loc_1400165B9
0x140015953  lea     eax, [r14+11h]
0x140015957  cmp     ebx, eax
0x140015959  jl      loc_140015A0D
0x14001595f  lea     rdi, SpinLock
0x140015966  mov     rcx, rdi; SpinLock
0x140015969  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015970  nop     dword ptr [rax+rax+00h]
0x140015975  mov     r8, [rbp+47h+var_70]
0x140015979  lea     r9, [rbp+47h+var_B8]
0x14001597d  mov     rcx, cs:qword_140039460
0x140015984  lea     rdx, [rbp+47h+Source1]
0x140015988  mov     sil, al
0x14001598b  movsxd  r13, r14d
0x14001598e  call    FindInHashTable
0x140015993  xor     r9d, r9d
0x140015996  test    eax, eax
0x140015998  jns     loc_140015C75
0x14001599e  cmp     byte ptr [r15+r13+0Eh], 21h ; '!'
0x1400159a4  jnz     loc_140015A36
0x1400159aa  cmp     [rbp+47h+arg_28], r9b
0x1400159ae  jnz     loc_140015A36
0x1400159b4  mov     r8d, 10h; Length
0x1400159ba  lea     rdx, asc_1400331A0; "*"
0x1400159c1  lea     rcx, [rbp+47h+Source1]; Source1
0x1400159c5  call    cs:__imp_RtlCompareMemory
0x1400159cc  nop     dword ptr [rax+rax+00h]
0x1400159d1  cmp     rax, 10h
0x1400159d5  jnz     short loc_140015A33
0x1400159d7  mov     dl, sil; NewIrql
0x1400159da  mov     rcx, rdi; SpinLock
0x1400159dd  call    cs:__imp_KeReleaseSpinLock
0x1400159e4  nop     dword ptr [rax+rax+00h]
0x1400159e9  mov     rax, [rbp+47h+var_A0]
0x1400159ed  mov     r9d, r14d
0x1400159f0  mov     [rsp+110h+var_E0], rax; __int64
0x1400159f5  mov     edx, ebx; Size
0x1400159f7  movzx   eax, [rbp+47h+var_BE]
0x1400159fb  mov     rcx, r15; Src
0x1400159fe  mov     [rsp+110h+var_E8], ax; __int16
0x140015a03  mov     dword ptr [rsp+110h+var_F0], r12d; int
0x140015a08  call    SendNodeStatusResponse
0x140015a0d  mov     eax, 0C000021Bh
0x140015a12  mov     rcx, [rbp+47h+var_48]
0x140015a16  xor     rcx, rsp; StackCookie
0x140015a19  call    __security_check_cookie
0x140015a1e  add     rsp, 0D8h
0x140015a25  pop     r15
0x140015a27  pop     r14
0x140015a29  pop     r13
0x140015a2b  pop     r12
0x140015a2d  pop     rdi
0x140015a2e  pop     rsi
0x140015a2f  pop     rbx
0x140015a30  pop     rbp
0x140015a31  retn
0x140015a33  xor     r9d, r9d
0x140015a36  bt      [rbp+47h+arg_20], 0Ch
0x140015a3c  jb      loc_140016626
0x140015a42  cmp     byte ptr [r15+r13+0Eh], 20h ; ' '
0x140015a48  jnz     loc_140015C5E
0x140015a4e  mov     byte ptr [rsp+110h+var_D8], sil
0x140015a53  mov     dword ptr [rsp+110h+var_E0], 3
0x140015a5b  mov     dword ptr [rsp+110h+var_E8], r9d
0x140015a60  mov     r9, [rbp+47h+var_88]
0x140015a64  add     r9, 8
0x140015a68  xor     r8d, r8d
0x140015a6b  mov     rax, [rbp+47h+var_A0]
0x140015a6f  mov     [rsp+110h+var_F0], rax
0x140015a74  mov     rdx, r15
0x140015a77  mov     ecx, r14d
0x140015a7a  call    UdpSendResponse
0x140015a7f  jmp     short loc_140015A0D
0x140015a81  test    al, 4
0x140015a83  jz      short loc_140015A0D
0x140015a85  movsxd  rax, r14d
0x140015a88  lea     rsi, [r15+0Dh]
0x140015a8c  add     rsi, rax
0x140015a8f  mov     [rbp+47h+var_60], rax
0x140015a93  lea     rdi, SpinLock
0x140015a9a  mov     rcx, rdi; SpinLock
0x140015a9d  cmp     byte ptr [rsi+1], 21h ; '!'
0x140015aa1  jz      loc_140015EEB
0x140015aa7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015aae  nop     dword ptr [rax+rax+00h]
0x140015ab3  mov     ecx, r12d
0x140015ab6  mov     r11b, al
0x140015ab9  call    SrcIsUs
0x140015abe  xor     r9d, r9d
0x140015ac1  test    al, al
0x140015ac3  jnz     loc_1400160E1
0x140015ac9  cmp     cs:byte_140039758, r9b
0x140015ad0  jz      loc_140015CCE
0x140015ad6  mov     dl, r11b; NewIrql
0x140015ad9  mov     rcx, rdi; SpinLock
0x140015adc  call    cs:__imp_KeReleaseSpinLock
0x140015ae3  nop     dword ptr [rax+rax+00h]
0x140015ae8  movzx   ecx, [rbp+47h+arg_20]
0x140015aec  mov     eax, 0F00h
0x140015af1  and     cx, ax
0x140015af4  movzx   eax, cx
0x140015af7  mov     [rbp+47h+arg_20], cx
0x140015afb  neg     ax
0x140015afe  sbb     ecx, ecx
0x140015b00  and     ecx, 0FFFFFFFAh
0x140015b03  add     ecx, 1Dh
0x140015b06  add     ecx, r14d
0x140015b09  cmp     ebx, ecx
0x140015b0b  jl      loc_140015A0D
0x140015b11  movzx   eax, word ptr [rsi+8]
0x140015b15  lea     r9, [rsi+0Ah]
0x140015b19  ror     ax, 8
0x140015b1d  xor     r10d, r10d
0x140015b20  movzx   r8d, ax
0x140015b24  mov     ecx, r15d
0x140015b27  sub     ecx, esi
0x140015b29  mov     [rbp+47h+P], r10
0x140015b2d  add     ecx, 0FFFFFFF6h
0x140015b30  mov     [rbp+47h+var_90], r9
0x140015b34  add     ecx, ebx
0x140015b36  mov     eax, 0AAAAAAABh
0x140015b3b  cmp     r8d, ecx
0x140015b3e  cmovnb  r8d, ecx
0x140015b42  mul     r8d
0x140015b45  mov     [rbp+47h+var_B0], r8d
0x140015b49  mov     r13d, edx
0x140015b4c  shr     r13d, 2
0x140015b50  cmp     cs:byte_1400395D4, r10b
0x140015b57  jnz     loc_1400160F3
0x140015b5d  test    byte ptr cs:xmmword_140038420+0Bh, 2
0x140015b64  jnz     loc_1400161B4
0x140015b6a  mov     rcx, rdi; SpinLock
0x140015b6d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015b74  nop     dword ptr [rax+rax+00h]
0x140015b79  lea     r8, qword_1400394A0
0x140015b80  mov     [rbp+47h+NewIrql], al
0x140015b83  mov     rbx, r8
0x140015b86  mov     [rbp+47h+var_BF], al
0x140015b89  mov     rbx, [rbx]
0x140015b8c  cmp     rbx, r8
0x140015b8f  jz      loc_140016526
0x140015b95  mov     rsi, [rbx+70h]
0x140015b99  test    rsi, rsi
0x140015b9c  jz      short loc_140015B89
0x140015b9e  lea     rax, [rsi+30h]
0x140015ba2  mov     r11, [rax]
0x140015ba5  mov     [rbp+47h+var_68], rax
0x140015ba9  movzx   eax, word ptr [r15]
0x140015bad  mov     [rbp+47h+var_78], r11
0x140015bb1  cmp     [r11+80h], ax
0x140015bb9  jnz     short loc_140015B89
0x140015bbb  lea     rcx, [rbx+0A4h]
0x140015bc2  mov     rax, [rcx]
0x140015bc5  sub     rax, qword ptr [rbp+47h+Source1]
0x140015bc9  jnz     short loc_140015BD3
0x140015bcb  mov     rax, [rcx+8]
0x140015bcf  sub     rax, qword ptr [rbp+47h+Source1+8]
0x140015bd3  test    rax, rax
0x140015bd6  jnz     short loc_140015B89
0x140015bd8  mov     r14d, [r11+0F0h]
0x140015bdf  mov     ecx, r12d
0x140015be2  movzx   edx, [rbp+47h+var_BE]
0x140015be6  mov     [rbp+47h+var_94], r14d
0x140015bea  call    SrcIsNameServer
0x140015bef  xor     edx, edx; Tag
0x140015bf1  test    al, al
0x140015bf3  jnz     loc_1400161CF
0x140015bf9  cmp     [rbx+84h], dl
0x140015bff  jz      loc_140015CF4
0x140015c05  mov     rax, [rbx+40h]
0x140015c09  xor     r14d, r14d
0x140015c0c  mov     rcx, [rbp+47h+P]; P
0x140015c10  test    rax, rax
0x140015c13  jz      loc_140015D40
0x140015c19  test    rcx, rcx
0x140015c1c  jnz     loc_140016215
0x140015c22  mov     rax, [rbx+40h]
0x140015c26  mov     r10, [rax+0C0h]
0x140015c2d  test    r10, r10
0x140015c30  jnz     loc_1400162B1
0x140015c36  lea     edx, ds:0[r13*2]
0x140015c3e  add     edx, r13d
0x140015c41  add     edx, edx
0x140015c43  mov     [rbp+47h+var_B0], edx
0x140015c46  jnz     loc_140015F59
0x140015c4c  test    byte ptr cs:NodeType, 0Eh
0x140015c53  jnz     loc_140016336
0x140015c59  mov     dl, [rbp+47h+NewIrql]
0x140015c5c  jmp     short loc_140015C61
0x140015c5e  mov     dl, sil; NewIrql
0x140015c61  mov     rcx, rdi; SpinLock
0x140015c64  call    cs:__imp_KeReleaseSpinLock
0x140015c6b  nop     dword ptr [rax+rax+00h]
0x140015c70  jmp     loc_140015A0D
0x140015c75  mov     r8, [rbp+47h+var_B8]
0x140015c79  mov     ecx, [r8+48h]
0x140015c7d  test    cl, 90h
0x140015c80  jz      loc_14001599E
0x140015c86  cmp     byte ptr [r15+r13+0Eh], 21h ; '!'
0x140015c8c  jz      loc_1400165E2
0x140015c92  mov     ecx, r12d
0x140015c95  call    SrcIsUs
0x140015c9a  test    al, al
0x140015c9c  jz      short loc_140015CAF
0x140015c9e  bt      [rbp+47h+arg_20], 0Ch
0x140015ca4  jb      short loc_140015C5E
0x140015ca6  cmp     cs:pWinsInfo, r9
0x140015cad  jz      short loc_140015C5E
0x140015caf  mov     byte ptr [rsp+110h+var_D8], sil
0x140015cb4  mov     dword ptr [rsp+110h+var_E0], 3
0x140015cbc  mov     dword ptr [rsp+110h+var_E8], r9d
0x140015cc1  mov     r9, [rbp+47h+var_88]
0x140015cc5  add     r9, 8
0x140015cc9  jmp     loc_140015A6B
0x140015cce  call    IsAddrOnLocalSubnet
0x140015cd3  test    al, al
0x140015cd5  jnz     loc_140015AD6
  ... truncated ...
```
