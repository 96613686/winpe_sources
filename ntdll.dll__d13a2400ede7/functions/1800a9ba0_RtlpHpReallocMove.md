# RtlpHpReallocMove

- ea: `0x1800a9ba0`
- end: `0x1800aa5dc`
- name: `RtlpHpReallocMove`
- size: `2620`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180041ca4`
- `0x180158084`

## callees

- `0x180017ee0`
- `0x180030500`
- `0x180043c30`
- `0x180043df0`
- `0x1800478fc`
- `0x180047a10`
- `0x18008a534`
- `0x18008aa20`
- `0x18008b25c`
- `0x180090f6c`
- `0x180092440`
- `0x1800a2840`
- `0x1800a9ba0`
- `0x1800beca8`
- `0x1800e4d78`
- `0x180118e14`
- `0x18011d208`
- `0x180157934`
- `0x180157f14`
- `0x180162810`
- `0x180163e50`
- `0x180164280`

## pseudocode

```c
char *__fastcall RtlpHpReallocMove(__int64 a1, unsigned __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned __int64 v4; // r15
  __int64 v5; // rbp
  unsigned int v6; // r12d
  __int64 v7; // r14
  unsigned __int64 v8; // rbx
  __int64 v9; // rsi
  __int64 v10; // rax
  int v11; // ecx
  char *Slow; // rdi
  unsigned int v13; // r13d
  int v14; // eax
  __int64 v15; // r14
  __int64 v16; // rbp
  unsigned int v17; // ecx
  __int64 v18; // rbx
  void **TlsExpansionSlots; // rdx
  unsigned __int64 v20; // rdi
  int v21; // edx
  unsigned __int64 v22; // rcx
  __int64 v23; // r10
  __int64 v24; // rax
  unsigned int v25; // r8d
  __int64 v26; // r11
  unsigned __int64 v27; // r11
  struct _TEB *v28; // r9
  int v29; // r10d
  __int64 v30; // r12
  unsigned __int64 v31; // rcx
  __int64 v32; // rbx
  bool v33; // cf
  unsigned __int64 v34; // r8
  unsigned __int64 v35; // rdx
  unsigned __int64 v36; // r8
  _DWORD *v37; // r8
  unsigned __int64 i; // rcx
  int v42; // esi
  signed __int64 v43; // rbx
  signed __int64 v44; // rax
  unsigned __int64 v45; // rbx
  int v46; // r10d
  struct _TEB *v47; // r8
  __int64 v48; // r12
  unsigned __int64 v49; // rcx
  unsigned __int64 v50; // r13
  unsigned __int64 v51; // rdx
  unsigned __int64 v52; // r9
  unsigned __int64 v53; // rdx
  int v54; // r11d
  unsigned int v55; // r14d
  volatile signed __int64 *v56; // r8
  volatile signed __int64 *v57; // rdi
  signed __int64 v58; // r9
  __int64 v63; // rdx
  unsigned __int64 v66; // rcx
  unsigned int v67; // ecx
  signed __int64 v69; // rcx
  signed __int64 v70; // rax
  __int64 v71; // r12
  int v72; // r8d
  __int64 v73; // r13
  unsigned int v74; // r14d
  int v75; // edi
  __int64 v76; // rdi
  __int16 v77; // ax
  signed __int64 v78; // rax
  char v79; // dl
  unsigned __int64 v80; // rdx
  signed __int64 v81; // rtt
  int v82; // eax
  __int64 v83; // r8
  signed __int64 v84; // rax
  unsigned __int64 *v85; // r10
  unsigned __int64 v86; // r9
  signed __int64 v87; // rax
  signed __int64 v88; // rtt
  signed __int64 v89; // rdx
  __int64 v90; // rax
  int v91; // r10d
  size_t v92; // r8
  __int64 v93; // rcx
  size_t v94; // rax
  char *v95; // rcx
  unsigned __int8 *v96; // rdx
  __int64 v97; // rax
  int v98; // eax
  __int64 v99; // r10
  unsigned __int64 v100; // r8
  char v101; // cl
  unsigned __int64 v102; // r9
  unsigned __int64 v103; // r9
  unsigned __int64 v104; // rdx
  unsigned __int8 v106; // [rsp+30h] [rbp-E8h]
  unsigned int v107; // [rsp+34h] [rbp-E4h]
  int v108; // [rsp+34h] [rbp-E4h]
  int v110; // [rsp+3Ch] [rbp-DCh]
  __int64 v111; // [rsp+40h] [rbp-D8h]
  int v112; // [rsp+44h] [rbp-D4h]
  unsigned int v113; // [rsp+48h] [rbp-D0h]
  signed __int64 v114[2]; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v115; // [rsp+60h] [rbp-B8h]
  unsigned int v116; // [rsp+68h] [rbp-B0h]
  __int64 v117; // [rsp+70h] [rbp-A8h]
  unsigned __int64 v118; // [rsp+78h] [rbp-A0h]
  unsigned __int64 *v119; // [rsp+80h] [rbp-98h]
  __int64 v120; // [rsp+88h] [rbp-90h]
  unsigned __int64 v121; // [rsp+90h] [rbp-88h]
  __int64 v122; // [rsp+98h] [rbp-80h]
  int *v123; // [rsp+A0h] [rbp-78h] BYREF
  int v124; // [rsp+A8h] [rbp-70h]
  int v125; // [rsp+ACh] [rbp-6Ch]
  __int16 *v126; // [rsp+B0h] [rbp-68h]
  int v127; // [rsp+B8h] [rbp-60h]
  int v128; // [rsp+BCh] [rbp-5Ch]

  v4 = *(_QWORD *)(a3 + 32);
  v5 = *(_QWORD *)(a3 + 24);
  v6 = a4;
  v7 = a3;
  v122 = a3;
  v8 = a2;
  v121 = a2;
  v9 = a1;
  v117 = a1;
  v118 = v4;
  v115 = v5;
  if ( (a4 & 0x1000) != 0 )
  {
    v10 = RtlpHpPgContextAllocate(a1 + 800, (unsigned int)v5, (unsigned int)v4);
    v11 = v4;
    Slow = (char *)v10;
    v113 = v4;
    if ( v10 )
      goto LABEL_106;
  }
  else
  {
    v11 = v4;
    v113 = v4;
  }
  v13 = v5;
  v107 = v5;
  if ( v4 >= *(unsigned __int16 *)(v9 + 1028) )
    goto LABEL_97;
  v14 = v11 + 2;
  v15 = v9 + 960;
  if ( (_DWORD)v5 == v11 )
    v14 = v11;
  v111 = v9 + 960;
  v16 = (unsigned int)*((unsigned __int8 *)RtlpLfhBucketIndexMap + ((unsigned __int64)(unsigned int)(v14 + 15) >> 4))
      - 1;
  v17 = (unsigned __int16)*(_DWORD *)(v9 + 1036);
  if ( v17 < 0x40 )
  {
    v18 = __readgsqword(8 * v17 + 5248);
    goto LABEL_12;
  }
  TlsExpansionSlots = NtCurrentTeb()->TlsExpansionSlots;
  if ( TlsExpansionSlots )
  {
    v18 = (__int64)TlsExpansionSlots[v17 - 64];
LABEL_12:
    if ( v18 )
      goto LABEL_14;
  }
  v18 = RtlpHpLfhThreadDataInitializeSet(v9 + 960);
LABEL_14:
  v20 = v15 + ((unsigned __int64)(unsigned __int16)v18 << 6);
  v21 = *(unsigned __int16 *)(2 * v16 + v20);
  if ( !*(_WORD *)(2 * v16 + v20) )
  {
    if ( !RtlpHpLfhBucketCheckAndUpdate(v15, (unsigned int)v16) )
    {
      v9 = v117;
LABEL_96:
      v5 = v115;
LABEL_97:
      if ( v4 > 0x20000 )
      {
        if ( v4 > *(unsigned int *)(v9 + 528) )
        {
          v90 = RtlpHpLargeAlloc(v9, v5, v4, v6);
        }
        else
        {
          v91 = v9 + 512;
          if ( v4 <= *(unsigned int *)(v9 + 336) )
            v91 = v9 + 320;
          v90 = RtlpHpSegAlloc(v91, v5, v4, v4, v6);
        }
      }
      else
      {
        v90 = RtlpHpVsContextAllocate(v9 + 704, v13, v113, v6);
      }
      Slow = (char *)v90;
      goto LABEL_105;
    }
    v22 = v15 + ((unsigned __int64)BYTE4(v18) << 8) + 1472;
    v21 = *(unsigned __int16 *)(v22 + 2 * v16);
    if ( v20 != v22 )
      *(_WORD *)(2 * v16 + v20) = *(_WORD *)(v22 + 2 * v16);
  }
  v23 = v15 + (unsigned int)(v21 << 6);
  v120 = v23;
  if ( *(_WORD *)(v23 + 4) )
  {
    v24 = *(_QWORD *)(v23 + 56);
    v25 = v115;
    if ( (v24 & 0xFFF) != 0 )
    {
      v26 = *(_QWORD *)(v23 + 56);
      *(_QWORD *)(v23 + 56) = v24 - 1;
      v27 = v26 & 0xFFFFFFFFFFFFF000uLL;
      if ( v27 )
      {
        v28 = NtCurrentTeb();
        v29 = *(unsigned __int8 *)(v27 + 24);
        v30 = 0x100000001LL;
        v31 = v28->RngState[0];
        v32 = (unsigned __int16)(qword_1801C5EC8 ^ *(_WORD *)(v27 + 40) ^ (v27 >> 12));
        v33 = v25 < (unsigned int)v32;
        v108 = qword_1801C5EC8 ^ *(_DWORD *)(v27 + 40) ^ (v27 >> 12);
        v34 = v28->RngState[1];
        if ( !v33 )
          v30 = 1;
        v35 = v34 + v31;
        v36 = v31 ^ v34;
        v28->RngState[1] = __ROL8__(v36, 37);
        v28->RngState[0] = v36 ^ __ROL8__(v31, 24) ^ (v36 << 16);
        v37 = (_DWORD *)(v27 + 64 + 8LL * *(unsigned __int8 *)(v27 + 36));
        for ( i = (unsigned int)~*v37; *v37 == -1; i = (unsigned int)~*v37 )
        {
          if ( v37 == (_DWORD *)(v27 + 64 + 8 * ((unsigned int)(v29 - 8) - 1LL)) )
            v37 = (_DWORD *)(v27 + 64);
          else
            v37 += 2;
        }
        _RAX = 1LL << ((unsigned __int16)(BYTE4(v35) * (unsigned __int16)__popcnt(i)) >> 8);
        __asm
        {
          pdep    rcx, rax, rcx
          tzcnt   rdx, rcx
        }
        *(_QWORD *)v37 |= v30 << _RDX;
        v6 = a4;
        LODWORD(_RAX) = _RDX + 4 * ((_DWORD)v37 - (v27 + 64));
        *(_BYTE *)(v27 + 36) = (unsigned int)_RAX >> 5;
        Slow = (char *)(v27 + (_DWORD)v32 * (_DWORD)_RAX + (unsigned int)HIWORD(v108));
        if ( (a4 & 2) != 0 )
          RtlHeapZero(Slow, (v13 + 15LL) & 0xFFFFFFFFFFFFFFF0uLL);
        if ( v13 < (unsigned int)v32 )
        {
          if ( (_DWORD)v32 - v13 == 1 )
            *(_WORD *)&Slow[v32 - 2] = 0x8000;
          else
            *(_WORD *)&Slow[v32 - 2] = v32 - v13;
        }
        goto LABEL_93;
      }
    }
LABEL_37:
    Slow = (char *)RtlpHpLfhSlotAllocateSlow(v15);
    goto LABEL_93;
  }
  v42 = 0;
  _m_prefetchw((const void *)(v23 + 56));
  v43 = *(_QWORD *)(v23 + 56);
  if ( (v43 & 0xFFF) == 0 )
    goto LABEL_37;
  while ( 1 )
  {
    v44 = _InterlockedCompareExchange64((volatile signed __int64 *)(v23 + 56), v43 - 1, v43);
    if ( v43 == v44 )
      break;
    v42 = 1;
    v43 = v44;
    if ( (v44 & 0xFFF) == 0 )
      goto LABEL_37;
  }
  v45 = v43 & 0xFFFFFFFFFFFFF000uLL;
  if ( !v45 )
    goto LABEL_37;
  v46 = *(unsigned __int8 *)(v45 + 24);
  v47 = NtCurrentTeb();
  v48 = 0x100000001LL;
  v110 = qword_1801C5EC8 ^ *(_DWORD *)(v45 + 40) ^ (v45 >> 12);
  v33 = v13 < (unsigned __int16)v110;
  v116 = (unsigned __int16)v110;
  v49 = v47->RngState[0];
  v50 = v45 + 64;
  if ( !v33 )
    v48 = 1;
  v119 = (unsigned __int64 *)(v45 + 24);
  v51 = v47->RngState[1];
  v52 = v51 + v49;
  v53 = v49 ^ v51;
  v54 = BYTE4(v52);
  v47->RngState[0] = v53 ^ __ROL8__(v49, 24) ^ (v53 << 16);
  v47->RngState[1] = __ROL8__(v53, 37);
  v55 = *(unsigned __int8 *)(v45 + 50);
  v106 = *(_BYTE *)(v45 + 39);
  v56 = (volatile signed __int64 *)(v50 + 8LL * *(unsigned __int8 *)(v45 + 36));
  v57 = (volatile signed __int64 *)(v50 + 8LL * (unsigned int)(v46 - 8) - 8);
LABEL_42:
  v58 = *v56;
  for ( _RAX = (unsigned int)~*(_DWORD *)v56; *(_DWORD *)v56 == -1; _RAX = (unsigned int)~*(_DWORD *)v56 )
  {
    if ( v56 == v57 )
      v56 = (volatile signed __int64 *)(v45 + 64);
    else
      ++v56;
    v58 = *v56;
  }
  while ( 1 )
  {
    if ( (qword_1801C5EE8 & 4) != 0 )
    {
      _RCX = 1LL << ((unsigned __int16)(v54 * __popcnt(_RAX)) >> 8);
      __asm
      {
        pdep    rdx, rcx, rax
        tzcnt   r10, rdx
      }
      v63 = v48 << _R10;
    }
    else
    {
      if ( v56 == v57 || v55 != 32 )
      {
        __asm { tzcnt   rdx, rax }
        _BitScanReverse64(&v66, _RAX);
        LODWORD(v114[0]) = _RDX;
        v67 = v66 - _RDX + 1;
        if ( v55 < v67 )
          v67 = v55;
        v54 = _RDX + ((v67 * v54) >> 8);
        _RAX = __ROR8__(_RAX, v54);
        __asm { tzcnt   r10, rax }
        LODWORD(_R10) = v54 + _R10;
      }
      else
      {
        _RCX = (unsigned int)__ROR4__(_RAX, v54);
        __asm { tzcnt   r10, rcx }
        LODWORD(_R10) = ((_BYTE)v54 + (_BYTE)_R10) & 0x1F;
      }
      v63 = v48 << _R10;
    }
    v69 = v58;
    v70 = _InterlockedCompareExchange64(v56, v58 | v63, v58);
    v58 = v70;
    if ( v70 == v69 )
      break;
    _RAX = (unsigned int)~(_DWORD)v70;
    if ( !_RAX )
    {
      if ( v56 == v57 )
        v56 = (volatile signed __int64 *)(v45 + 64);
      else
        ++v56;
      goto LABEL_42;
    }
  }
  v71 = v116;
  v72 = (_DWORD)v56 - v50;
  v73 = v111;
  v74 = _R10 + 4 * v72;
  v75 = v116 * v74;
  *(_BYTE *)(v45 + 36) = v74 >> 5;
  v76 = (unsigned int)HIWORD(v110) + v75;
  if ( v106 <= 1u )
  {
    if ( v74 > *(unsigned __int16 *)(v45 + 48) )
      RtlpHpLfhSubsegmentPrefetch(v111, v45, (unsigned int)v76, (unsigned int)v71);
    goto LABEL_67;
  }
  if ( (int)RtlpHpLfhSubsegmentCommitBlock(v111, v45, (unsigned int)v76, v70) >= 0 )
  {
LABEL_67:
    Slow = (char *)(v45 + v76);
    if ( (a4 & 2) != 0 )
      RtlHeapZero(Slow, (v107 + 15LL) & 0xFFFFFFFFFFFFFFF0uLL);
    if ( v107 < (unsigned int)v71 )
    {
      if ( (_DWORD)v71 - v107 == 1 )
        v77 = 0x8000;
      else
        v77 = v71 - v107;
      *(_WORD *)&Slow[v71 - 2] = v77;
    }
    goto LABEL_74;
  }
  Slow = 0;
  if ( v74 != -1 )
  {
    _InterlockedAnd64(
      (volatile signed __int64 *)(v45 + 8LL * (v74 >> 5) + 64),
      __ROL8__(0xFFFFFFFEFFFFFFFEuLL, v74 & 0x1F));
    goto LABEL_75;
  }
LABEL_74:
  if ( !Slow )
  {
LABEL_75:
    v78 = *(_QWORD *)(v45 + 16);
    do
    {
      v114[0] = v78;
      v79 = BYTE6(v78);
      v112 = HIDWORD(v78);
      if ( BYTE6(v78) == 1 )
        v79 = 2;
      ++WORD1(v114[0]);
      BYTE6(v114[0]) = v79;
      v80 = (unsigned __int64)*(unsigned __int16 *)(v45 + 44) << 6;
      v81 = v78;
      v78 = _InterlockedCompareExchange64((volatile signed __int64 *)(v45 + 16), v114[0], v78);
    }
    while ( v81 != v78 );
    if ( !*(_BYTE *)(v80 + v73 + 92) )
    {
      *(_BYTE *)(v80 + v73 + 92) = 1;
      v82 = qword_1801C6278;
      if ( !(_DWORD)qword_1801C6278 )
      {
        if ( qword_1801C6268 )
        {
          if ( byte_1801CA908 == (_BYTE)qword_1801C6278
            && v82 == _InterlockedCompareExchange((volatile signed __int32 *)&qword_1801C6278, 1, qword_1801C6278) )
          {
            TpSetTimerEx(qword_1801C6268, &qword_1801C6270, 0, 1000);
            if ( (RtlpHpHeapFeatures & 0x10) != 0 && (unsigned int)dword_1801C4680 > 5 )
            {
              v123 = off_1801C4688;
              v114[0] = 0x50B000000LL;
              v114[1] = 0;
              v124 = *(unsigned __int16 *)off_1801C4688;
              v126 = &word_18019B4B6;
              v125 = 2;
              v127 = 25;
              v128 = 1;
              EtwEventWriteTransfer(qword_1801C46A0, (unsigned int)v114, 0, 0, 2, (__int64)&v123);
            }
          }
        }
      }
    }
    if ( BYTE2(v112) == 1 )
    {
      v83 = v73 + ((unsigned __int64)(unsigned __int16)v112 << 6);
      _m_prefetchw((const void *)(v83 + 8));
      v84 = *(_QWORD *)(v83 + 8);
      v85 = v119;
      v86 = *v119;
      *v119 ^= (v84 ^ *v119) & 0xFFFFFFFFFFFFF000uLL;
      v88 = v84;
      v87 = _InterlockedCompareExchange64((volatile signed __int64 *)(v83 + 8), v45 | v84 & 0xFFF, v84);
      if ( v88 != v87 )
      {
        do
        {
          v89 = v87;
          *v85 = v86 ^ (v86 ^ v87) & 0xFFFFFFFFFFFFF000uLL;
          v87 = _InterlockedCompareExchange64((volatile signed __int64 *)(v83 + 8), v45 | v87 & 0xFFF, v87);
        }
        while ( v87 != v89 );
      }
    }
  }
  if ( v42 )
    RtlpHpLfhBucketUpdateAffinityMapping(v73, v73 + ((unsigned __int64)*(unsigned __int16 *)(v120 + 2) << 6));
  v6 = a4;
  v4 = v118;
  v13 = v107;
LABEL_93:
  v9 = v117;
  if ( Slow == (char *)-1LL )
    goto LABEL_96;
LABEL_105:
  v8 = v121;
  v7 = v122;
LABEL_106:
  if ( Slow )
  {
    v92 = *(_QWORD *)v7;
    if ( *(_QWORD *)v7 >= *(_QWORD *)(v7 + 24) )
      v92 = *(_QWORD *)(v7 + 24);
    memmove(Slow, (const void *)v8, v92);
    if ( *(_DWORD *)(v7 + 16) )
    {
      v93 = *(_QWORD *)(v7 + 24);
      v94 = *(_QWORD *)v7;
      if ( (v6 & 0x2000) != 0 )
      {
        v95 = &Slow[v93 + 16];
        v96 = (unsigned __int8 *)((v94 + v8 + 31) & 0xFFFFFFFFFFFFFFF0uLL);
      }
      else
      {
        v96 = (unsigned __int8 *)((v94 + v8 + 15) & 0xFFFFFFFFFFFFFFF0uLL);
        v95 = &Slow[v93];
      }
      memmove((void *)((unsigned __int64)(v95 + 15) & 0xFFFFFFFFFFFFFFF0uLL), v96, 16 * (v96[3] + 1LL));
      RtlpHpExtrasSetPresent(v9, Slow);
    }
    if ( ((v8 + 0xFFFF) & 0xFFFFFFFFFFFF0000uLL) == v8 )
    {
      v97 = RtlCSparseBitmapBitmaskRead(qword_1801C6920, 2 * ((v8 - qword_1801C6918) >> 20));
      if ( !v97 || (v98 = v97 - 1, v98 == 2) )
      {
        RtlpHpLargeFree(v9, v8);
        return Slow;
      }
      v99 = v9 + 320;
      if ( v98 == 1 )
        v99 = v9 + 512;
    }
    else
    {
      v99 = v9 + 320;
    }
    v100 = *(_QWORD *)v99 & v8;
    if ( RtlpHpHeapGlobals ^ v100 ^ *(_QWORD *)(v100 + 0x10) ^ v99 )
    {
      RtlpLogHeapFailure(9, *(_QWORD *)(v99 + 56), v8, 0, 0, 0);
    }
    else
    {
      v101 = *(_BYTE *)(v99 + 8);
      v102 = v100 + 32 * ((unsigned __int64)(unsigned int)(v8 - v100) >> v101);
      v103 = v102 - 32LL * *(unsigned __int8 *)(v102 + 26);
      v104 = v100 + ((unsigned int)((__int64)(v103 - v100) >> 5) << v101);
      if ( *(_BYTE *)(v103 + 24) + ((_DWORD)v8 == (_DWORD)v104) == 11 )
        RtlpHpLfhContextFree(*(_QWORD *)(v99 + 24), v104, v8);
      else
        RtlpHpSegFreeInternal(v99, v104, v8, v103, 0);
    }
  }
  return Slow;
}

```

## disassembly

```asm
0x1800a9ba0  push    rbx
0x1800a9ba2  push    rbp
0x1800a9ba3  push    rsi
0x1800a9ba4  push    rdi
0x1800a9ba5  push    r12
0x1800a9ba7  push    r13
0x1800a9ba9  push    r14
0x1800a9bab  push    r15
0x1800a9bad  sub     rsp, 0D8h
0x1800a9bb4  mov     rax, cs:__security_cookie
0x1800a9bbb  xor     rax, rsp
0x1800a9bbe  mov     [rsp+118h+var_58], rax
0x1800a9bc6  mov     r15, [r8+20h]
0x1800a9bca  xor     r13d, r13d
0x1800a9bcd  mov     rbp, [r8+18h]
0x1800a9bd1  mov     r12d, r9d
0x1800a9bd4  mov     [rsp+118h+var_E0], r9d
0x1800a9bd9  mov     r14, r8
0x1800a9bdc  mov     [rsp+118h+var_80], r8
0x1800a9be4  mov     rbx, rdx
0x1800a9be7  mov     [rsp+118h+var_88], rdx
0x1800a9bef  mov     rsi, rcx
0x1800a9bf2  mov     [rsp+118h+var_A8], rcx
0x1800a9bf7  mov     [rsp+118h+var_A0], r15
0x1800a9bfc  mov     [rsp+118h+var_B8], rbp
0x1800a9c01  bt      r9d, 0Ch
0x1800a9c06  jnb     short loc_1800A9C2E
0x1800a9c08  add     rcx, 320h
0x1800a9c0f  mov     r8d, r15d
0x1800a9c12  mov     edx, ebp
0x1800a9c14  call    RtlpHpPgContextAllocate
0x1800a9c19  mov     ecx, r15d
0x1800a9c1c  mov     rdi, rax
0x1800a9c1f  mov     [rsp+118h+var_D0], ecx
0x1800a9c23  test    rax, rax
0x1800a9c26  jnz     loc_1800AA440
0x1800a9c2c  jmp     short loc_1800A9C35
0x1800a9c2e  mov     ecx, r15d
0x1800a9c31  mov     [rsp+118h+var_D0], ecx
0x1800a9c35  movzx   eax, word ptr [rsi+404h]
0x1800a9c3c  mov     r13d, ebp
0x1800a9c3f  mov     [rsp+118h+var_E4], ebp
0x1800a9c43  cmp     r15, rax
0x1800a9c46  jnb     loc_1800AA3C2
0x1800a9c4c  cmp     ebp, ecx
0x1800a9c4e  lea     eax, [rcx+2]
0x1800a9c51  lea     r14, [rsi+3C0h]
0x1800a9c58  cmovz   eax, ecx
0x1800a9c5b  mov     [rsp+118h+var_D8], r14
0x1800a9c60  add     eax, 0Fh
0x1800a9c63  lea     rcx, RtlpLfhBucketIndexMap
0x1800a9c6a  shr     rax, 4
0x1800a9c6e  movzx   ebp, byte ptr [rax+rcx]
0x1800a9c72  mov     ecx, [r14+4Ch]
0x1800a9c76  dec     ebp
0x1800a9c78  movzx   ecx, cx
0x1800a9c7b  cmp     ecx, 40h ; '@'
0x1800a9c7e  jnb     short loc_1800A9C8D
0x1800a9c80  lea     ebx, ds:1480h[rcx*8]
0x1800a9c87  mov     rbx, gs:[rbx]
0x1800a9c8b  jmp     short loc_1800A9CA9
0x1800a9c8d  mov     rax, gs:30h
0x1800a9c96  mov     rdx, [rax+1780h]
0x1800a9c9d  test    rdx, rdx
0x1800a9ca0  jz      short loc_1800A9CAE
0x1800a9ca2  lea     eax, [rcx-40h]
0x1800a9ca5  mov     rbx, [rdx+rax*8]
0x1800a9ca9  test    rbx, rbx
0x1800a9cac  jnz     short loc_1800A9CB9
0x1800a9cae  mov     rcx, r14
0x1800a9cb1  call    RtlpHpLfhThreadDataInitializeSet
0x1800a9cb6  mov     rbx, rax
0x1800a9cb9  movzx   edi, bx
0x1800a9cbc  lea     rsi, ds:0[rbp*2]
0x1800a9cc4  shl     rdi, 6
0x1800a9cc8  add     rdi, r14
0x1800a9ccb  movzx   eax, word ptr [rsi+rdi]
0x1800a9ccf  mov     edx, eax
0x1800a9cd1  test    eax, eax
0x1800a9cd3  jnz     short loc_1800A9D0C
0x1800a9cd5  mov     edx, ebp
0x1800a9cd7  mov     rcx, r14
0x1800a9cda  call    RtlpHpLfhBucketCheckAndUpdate
0x1800a9cdf  test    rax, rax
0x1800a9ce2  jz      loc_1800AA3B8
0x1800a9ce8  shr     rbx, 20h
0x1800a9cec  movzx   ecx, bl
0x1800a9cef  shl     rcx, 8
0x1800a9cf3  add     rcx, 5C0h
0x1800a9cfa  add     rcx, r14
0x1800a9cfd  movzx   eax, word ptr [rcx+rsi]
0x1800a9d01  mov     edx, eax
0x1800a9d03  cmp     rdi, rcx
0x1800a9d06  jz      short loc_1800A9D0C
0x1800a9d08  mov     [rsi+rdi], ax
0x1800a9d0c  shl     edx, 6
0x1800a9d0f  mov     r10d, edx
0x1800a9d12  add     r10, r14
0x1800a9d15  mov     [rsp+118h+var_90], r10
0x1800a9d1d  cmp     word ptr [r10+4], 0
0x1800a9d23  jz      loc_1800A9E9B
0x1800a9d29  mov     rax, [r10+38h]
0x1800a9d2d  mov     r8d, dword ptr [rsp+118h+var_B8]
0x1800a9d32  test    rax, 0FFFh
0x1800a9d38  jz      loc_1800A9EDF
0x1800a9d3e  mov     r11, rax
0x1800a9d41  lea     rax, [rax-1]
0x1800a9d45  mov     [r10+38h], rax
0x1800a9d49  and     r11, 0FFFFFFFFFFFFF000h
0x1800a9d50  jz      loc_1800A9EDF
0x1800a9d56  mov     r9, gs:30h
0x1800a9d5f  mov     rax, r11
0x1800a9d62  movzx   r10d, byte ptr [r11+18h]
0x1800a9d67  mov     ebp, 1
0x1800a9d6c  shr     rax, 0Ch
0x1800a9d70  mov     r12, 100000001h
0x1800a9d7a  xor     eax, [r11+28h]
0x1800a9d7e  xor     eax, dword ptr cs:qword_1801C5EC8
0x1800a9d84  mov     rcx, [r9+260h]
0x1800a9d8b  movzx   ebx, ax
0x1800a9d8e  cmp     r8d, ebx
0x1800a9d91  mov     [rsp+118h+var_E4], eax
0x1800a9d95  mov     r8, [r9+268h]
0x1800a9d9c  cmovnb  r12, rbp
0x1800a9da0  add     r10d, 0FFFFFFF8h
0x1800a9da4  lea     rdx, [r8+rcx]
0x1800a9da8  xor     r8, rcx
0x1800a9dab  shr     rdx, 20h
0x1800a9daf  mov     rax, r8
0x1800a9db2  shl     rax, 10h
0x1800a9db6  movzx   esi, dl
0x1800a9db9  rol     rcx, 18h
0x1800a9dbd  xor     rax, rcx
0x1800a9dc0  mov     edx, r10d
0x1800a9dc3  xor     rax, r8
0x1800a9dc6  rol     r8, 25h
0x1800a9dca  mov     [r9+268h], r8
0x1800a9dd1  dec     rdx
0x1800a9dd4  mov     [r9+260h], rax
0x1800a9ddb  lea     r9, [r11+40h]
0x1800a9ddf  movzx   eax, byte ptr [r11+24h]
0x1800a9de4  lea     rdx, [r9+rdx*8]
0x1800a9de8  lea     r8, [r9+rax*8]
0x1800a9dec  mov     eax, [r8]
0x1800a9def  not     eax
0x1800a9df1  mov     ecx, eax
0x1800a9df3  test    eax, eax
0x1800a9df5  jnz     short loc_1800A9E10
0x1800a9df7  cmp     r8, rdx
0x1800a9dfa  jz      short loc_1800A9E02
0x1800a9dfc  add     r8, 8
0x1800a9e00  jmp     short loc_1800A9E05
0x1800a9e02  mov     r8, r9
0x1800a9e05  mov     eax, [r8]
0x1800a9e08  not     eax
0x1800a9e0a  mov     ecx, eax
0x1800a9e0c  test    eax, eax
0x1800a9e0e  jz      short loc_1800A9DF7
0x1800a9e10  movzx   edi, word ptr [rsp+118h+var_E4+2]
0x1800a9e15  popcnt  rax, rcx
0x1800a9e1a  imul    eax, esi
0x1800a9e1d  shr     eax, 8
0x1800a9e20  shlx    rax, rbp, rax
0x1800a9e25  pdep    rcx, rax, rcx
0x1800a9e2a  tzcnt   rdx, rcx
0x1800a9e2f  shlx    rcx, r12, rdx
0x1800a9e34  or      [r8], rcx
0x1800a9e37  sub     r8d, r9d
0x1800a9e3a  mov     r12d, [rsp+118h+var_E0]
0x1800a9e3f  lea     ecx, [rdx+r8*4]
0x1800a9e43  mov     eax, ecx
0x1800a9e45  imul    ecx, ebx
0x1800a9e48  shr     eax, 5
0x1800a9e4b  mov     [r11+24h], al
0x1800a9e4f  add     edi, ecx
0x1800a9e51  add     rdi, r11
0x1800a9e54  test    r12b, 2
0x1800a9e58  jz      short loc_1800A9E6D
0x1800a9e5a  mov     edx, r13d
0x1800a9e5d  mov     rcx, rdi
0x1800a9e60  add     rdx, 0Fh
0x1800a9e64  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800a9e68  call    RtlHeapZero
0x1800a9e6d  cmp     r13d, ebx
0x1800a9e70  jnb     loc_1800AA3AB
0x1800a9e76  mov     ecx, ebx
0x1800a9e78  sub     ecx, r13d
0x1800a9e7b  cmp     ecx, ebp
0x1800a9e7d  jnz     short loc_1800A9E8E
0x1800a9e7f  mov     eax, 8000h
0x1800a9e84  mov     [rbx+rdi-2], ax
0x1800a9e89  jmp     loc_1800AA3AB
0x1800a9e8e  movzx   eax, cx
0x1800a9e91  mov     [rbx+rdi-2], cx
0x1800a9e96  jmp     loc_1800AA3AB
0x1800a9e9b  xor     esi, esi
0x1800a9e9d  prefetchw byte ptr [r10+38h]
0x1800a9ea2  mov     rbx, [r10+38h]
0x1800a9ea6  test    rbx, 0FFFh
0x1800a9ead  jz      short loc_1800A9EDC
0x1800a9eaf  mov     edx, 1
0x1800a9eb4  nop     dword ptr [rax+00h]
0x1800a9eb8  nop     dword ptr [rax+rax+00000000h]
0x1800a9ec0  lea     rcx, [rbx-1]
0x1800a9ec4  mov     rax, rbx
0x1800a9ec7  lock cmpxchg [r10+38h], rcx
0x1800a9ecd  jz      short loc_1800A9EF5
0x1800a9ecf  mov     esi, edx
0x1800a9ed1  mov     rbx, rax
0x1800a9ed4  test    rax, 0FFFh
0x1800a9eda  jnz     short loc_1800A9EC0
0x1800a9edc  mov     r8d, r13d
0x1800a9edf  mov     r9d, r12d
0x1800a9ee2  mov     rdx, r10
0x1800a9ee5  mov     rcx, r14; __int64
0x1800a9ee8  call    RtlpHpLfhSlotAllocateSlow
0x1800a9eed  mov     rdi, rax
0x1800a9ef0  jmp     loc_1800AA3AB
0x1800a9ef5  and     rbx, 0FFFFFFFFFFFFF000h
0x1800a9efc  jz      short loc_1800A9EDC
0x1800a9efe  movzx   r10d, byte ptr [rbx+18h]
0x1800a9f03  mov     rax, rbx
0x1800a9f06  mov     r8, gs:30h
0x1800a9f0f  mov     r12, 100000001h
0x1800a9f19  shr     rax, 0Ch
0x1800a9f1d  mov     r15, rbx
0x1800a9f20  xor     eax, [rbx+28h]
0x1800a9f23  mov     rbp, rbx
0x1800a9f26  xor     eax, dword ptr cs:qword_1801C5EC8
0x1800a9f2c  movzx   ecx, ax
0x1800a9f2f  mov     [rsp+118h+var_DC], eax
0x1800a9f33  cmp     r13d, ecx
0x1800a9f36  lea     rax, [rbx+18h]
0x1800a9f3a  mov     [rsp+118h+var_B0], ecx
0x1800a9f3e  mov     rcx, [r8+260h]
0x1800a9f45  lea     r13, [rbx+40h]
0x1800a9f49  cmovnb  r12, rdx
0x1800a9f4d  mov     [rsp+118h+var_98], rax
0x1800a9f55  mov     rdx, [r8+268h]
0x1800a9f5c  add     r10d, 0FFFFFFF8h
0x1800a9f60  lea     r9, [rdx+rcx]
0x1800a9f64  xor     rdx, rcx
0x1800a9f67  mov     rax, rdx
0x1800a9f6a  rol     rcx, 18h
0x1800a9f6e  shl     rax, 10h
0x1800a9f72  lea     rdi, ds:0FFFFFFFFFFFFFFF8h[r10*8]
0x1800a9f7a  xor     rax, rcx
0x1800a9f7d  shr     r9, 20h
0x1800a9f81  xor     rax, rdx
0x1800a9f84  movzx   r11d, r9b
0x1800a9f88  mov     [r8+260h], rax
0x1800a9f8f  rol     rdx, 25h
0x1800a9f93  mov     [r8+268h], rdx
0x1800a9f9a  movzx   eax, byte ptr [rbx+27h]
0x1800a9f9e  movzx   r14d, byte ptr [rbx+32h]
0x1800a9fa3  mov     [rsp+118h+var_E8], al
0x1800a9fa7  movzx   eax, byte ptr [rbx+24h]
0x1800a9fab  lea     r8, ds:0[rax*8]
0x1800a9fb3  add     r8, r13
0x1800a9fb6  add     rdi, r13
0x1800a9fb9  nop     dword ptr [rax+00000000h]
0x1800a9fc0  mov     r9, [r8]
0x1800a9fc3  mov     eax, r9d
0x1800a9fc6  not     eax
0x1800a9fc8  test    rax, rax
0x1800a9fcb  jnz     short loc_1800A9FF0
0x1800a9fcd  nop     dword ptr [rax]
0x1800a9fd0  cmp     r8, rdi
0x1800a9fd3  jz      short loc_1800A9FDB
0x1800a9fd5  add     r8, 8
0x1800a9fd9  jmp     short loc_1800A9FDE
0x1800a9fdb  mov     r8, r13
0x1800a9fde  mov     r9, [r8]
0x1800a9fe1  mov     eax, r9d
0x1800a9fe4  not     eax
0x1800a9fe6  test    rax, rax
0x1800a9fe9  jz      short loc_1800A9FD0
0x1800a9feb  nop     dword ptr [rax+rax+00h]
0x1800a9ff0  test    byte ptr cs:qword_1801C5EE8, 4
0x1800a9ff7  jz      short loc_1800AA020
0x1800a9ff9  popcnt  rcx, rax
0x1800a9ffe  imul    ecx, r11d
0x1800aa002  mov     edx, 1
0x1800aa007  shr     ecx, 8
0x1800aa00a  shlx    rcx, rdx, rcx
0x1800aa00f  pdep    rdx, rcx, rax
0x1800aa014  tzcnt   r10, rdx
0x1800aa019  shlx    rdx, r12, r10
0x1800aa01e  jmp     short loc_1800AA07A
0x1800aa020  cmp     r8, rdi
0x1800aa023  jz      short loc_1800AA040
0x1800aa025  cmp     r14d, 20h ; ' '
0x1800aa029  jnz     short loc_1800AA040
0x1800aa02b  mov     ecx, r11d
0x1800aa02e  ror     eax, cl
0x1800aa030  mov     ecx, eax
0x1800aa032  tzcnt   r10, rcx
0x1800aa037  add     r10d, r11d
0x1800aa03a  and     r10d, 1Fh
0x1800aa03e  jmp     short loc_1800AA071
  ... truncated ...
```
