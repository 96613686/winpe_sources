# RtlpHpReallocMove

- ea: `0x1800a11d0`
- end: `0x1800a1c0c`
- name: `RtlpHpReallocMove`
- size: `2620`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18009eed4`
- `0x1801576f4`

## callees

- `0x180017ee0`
- `0x180031200`
- `0x18006da84`
- `0x18006df70`
- `0x18006e7ac`
- `0x180084b0c`
- `0x180085fe0`
- `0x180096a70`
- `0x18009d7e0`
- `0x18009d990`
- `0x1800a11d0`
- `0x1800e49f8`
- `0x1800eae38`
- `0x180117520`
- `0x180117eb8`
- `0x180118324`
- `0x18011c718`
- `0x180156fd4`
- `0x180157584`
- `0x180162000`
- `0x180163640`
- `0x180163a80`

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
  __int64 v91; // r10
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
      v82 = qword_1801C6280;
      if ( !(_DWORD)qword_1801C6280 )
      {
        if ( qword_1801C6270 )
        {
          if ( byte_1801CA908 == (_BYTE)qword_1801C6280
            && v82 == _InterlockedCompareExchange((volatile signed __int32 *)&qword_1801C6280, 1, qword_1801C6280) )
          {
            TpSetTimerEx(qword_1801C6270, &qword_1801C6278, 0, 1000);
            if ( (RtlpHpHeapFeatures & 0x10) != 0 && (unsigned int)dword_1801C4680 > 5 )
            {
              v123 = off_1801C4688;
              v114[0] = 0x50B000000LL;
              v114[1] = 0;
              v124 = *(unsigned __int16 *)off_1801C4688;
              v126 = &word_18019B4CE;
              v125 = 2;
              v127 = 25;
              v128 = 1;
              EtwEventWriteTransfer(qword_1801C46A0, (__int64)v114, 0, 0, 2u, (__int64)&v123);
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
      v97 = RtlCSparseBitmapBitmaskRead(qword_1801C6930, 2 * ((v8 - qword_1801C6928) >> 20));
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
0x1800a11d0  push    rbx
0x1800a11d2  push    rbp
0x1800a11d3  push    rsi
0x1800a11d4  push    rdi
0x1800a11d5  push    r12
0x1800a11d7  push    r13
0x1800a11d9  push    r14
0x1800a11db  push    r15
0x1800a11dd  sub     rsp, 0D8h
0x1800a11e4  mov     rax, cs:__security_cookie
0x1800a11eb  xor     rax, rsp
0x1800a11ee  mov     [rsp+118h+var_58], rax
0x1800a11f6  mov     r15, [r8+20h]
0x1800a11fa  xor     r13d, r13d
0x1800a11fd  mov     rbp, [r8+18h]
0x1800a1201  mov     r12d, r9d
0x1800a1204  mov     [rsp+118h+var_E0], r9d
0x1800a1209  mov     r14, r8
0x1800a120c  mov     [rsp+118h+var_80], r8
0x1800a1214  mov     rbx, rdx
0x1800a1217  mov     [rsp+118h+var_88], rdx
0x1800a121f  mov     rsi, rcx
0x1800a1222  mov     [rsp+118h+var_A8], rcx
0x1800a1227  mov     [rsp+118h+var_A0], r15
0x1800a122c  mov     [rsp+118h+var_B8], rbp
0x1800a1231  bt      r9d, 0Ch
0x1800a1236  jnb     short loc_1800A125E
0x1800a1238  add     rcx, 320h
0x1800a123f  mov     r8d, r15d
0x1800a1242  mov     edx, ebp
0x1800a1244  call    RtlpHpPgContextAllocate
0x1800a1249  mov     ecx, r15d
0x1800a124c  mov     rdi, rax
0x1800a124f  mov     [rsp+118h+var_D0], ecx
0x1800a1253  test    rax, rax
0x1800a1256  jnz     loc_1800A1A70
0x1800a125c  jmp     short loc_1800A1265
0x1800a125e  mov     ecx, r15d
0x1800a1261  mov     [rsp+118h+var_D0], ecx
0x1800a1265  movzx   eax, word ptr [rsi+404h]
0x1800a126c  mov     r13d, ebp
0x1800a126f  mov     [rsp+118h+var_E4], ebp
0x1800a1273  cmp     r15, rax
0x1800a1276  jnb     loc_1800A19F2
0x1800a127c  cmp     ebp, ecx
0x1800a127e  lea     eax, [rcx+2]
0x1800a1281  lea     r14, [rsi+3C0h]
0x1800a1288  cmovz   eax, ecx
0x1800a128b  mov     [rsp+118h+var_D8], r14
0x1800a1290  add     eax, 0Fh
0x1800a1293  lea     rcx, RtlpLfhBucketIndexMap
0x1800a129a  shr     rax, 4
0x1800a129e  movzx   ebp, byte ptr [rax+rcx]
0x1800a12a2  mov     ecx, [r14+4Ch]
0x1800a12a6  dec     ebp
0x1800a12a8  movzx   ecx, cx
0x1800a12ab  cmp     ecx, 40h ; '@'
0x1800a12ae  jnb     short loc_1800A12BD
0x1800a12b0  lea     ebx, ds:1480h[rcx*8]
0x1800a12b7  mov     rbx, gs:[rbx]
0x1800a12bb  jmp     short loc_1800A12D9
0x1800a12bd  mov     rax, gs:30h
0x1800a12c6  mov     rdx, [rax+1780h]
0x1800a12cd  test    rdx, rdx
0x1800a12d0  jz      short loc_1800A12DE
0x1800a12d2  lea     eax, [rcx-40h]
0x1800a12d5  mov     rbx, [rdx+rax*8]
0x1800a12d9  test    rbx, rbx
0x1800a12dc  jnz     short loc_1800A12E9
0x1800a12de  mov     rcx, r14
0x1800a12e1  call    RtlpHpLfhThreadDataInitializeSet
0x1800a12e6  mov     rbx, rax
0x1800a12e9  movzx   edi, bx
0x1800a12ec  lea     rsi, ds:0[rbp*2]
0x1800a12f4  shl     rdi, 6
0x1800a12f8  add     rdi, r14
0x1800a12fb  movzx   eax, word ptr [rsi+rdi]
0x1800a12ff  mov     edx, eax
0x1800a1301  test    eax, eax
0x1800a1303  jnz     short loc_1800A133C
0x1800a1305  mov     edx, ebp
0x1800a1307  mov     rcx, r14
0x1800a130a  call    RtlpHpLfhBucketCheckAndUpdate
0x1800a130f  test    rax, rax
0x1800a1312  jz      loc_1800A19E8
0x1800a1318  shr     rbx, 20h
0x1800a131c  movzx   ecx, bl
0x1800a131f  shl     rcx, 8
0x1800a1323  add     rcx, 5C0h
0x1800a132a  add     rcx, r14
0x1800a132d  movzx   eax, word ptr [rcx+rsi]
0x1800a1331  mov     edx, eax
0x1800a1333  cmp     rdi, rcx
0x1800a1336  jz      short loc_1800A133C
0x1800a1338  mov     [rsi+rdi], ax
0x1800a133c  shl     edx, 6
0x1800a133f  mov     r10d, edx
0x1800a1342  add     r10, r14
0x1800a1345  mov     [rsp+118h+var_90], r10
0x1800a134d  cmp     word ptr [r10+4], 0
0x1800a1353  jz      loc_1800A14CB
0x1800a1359  mov     rax, [r10+38h]
0x1800a135d  mov     r8d, dword ptr [rsp+118h+var_B8]
0x1800a1362  test    rax, 0FFFh
0x1800a1368  jz      loc_1800A150F
0x1800a136e  mov     r11, rax
0x1800a1371  lea     rax, [rax-1]
0x1800a1375  mov     [r10+38h], rax
0x1800a1379  and     r11, 0FFFFFFFFFFFFF000h
0x1800a1380  jz      loc_1800A150F
0x1800a1386  mov     r9, gs:30h
0x1800a138f  mov     rax, r11
0x1800a1392  movzx   r10d, byte ptr [r11+18h]
0x1800a1397  mov     ebp, 1
0x1800a139c  shr     rax, 0Ch
0x1800a13a0  mov     r12, 100000001h
0x1800a13aa  xor     eax, [r11+28h]
0x1800a13ae  xor     eax, dword ptr cs:qword_1801C5EC8
0x1800a13b4  mov     rcx, [r9+260h]
0x1800a13bb  movzx   ebx, ax
0x1800a13be  cmp     r8d, ebx
0x1800a13c1  mov     [rsp+118h+var_E4], eax
0x1800a13c5  mov     r8, [r9+268h]
0x1800a13cc  cmovnb  r12, rbp
0x1800a13d0  add     r10d, 0FFFFFFF8h
0x1800a13d4  lea     rdx, [r8+rcx]
0x1800a13d8  xor     r8, rcx
0x1800a13db  shr     rdx, 20h
0x1800a13df  mov     rax, r8
0x1800a13e2  shl     rax, 10h
0x1800a13e6  movzx   esi, dl
0x1800a13e9  rol     rcx, 18h
0x1800a13ed  xor     rax, rcx
0x1800a13f0  mov     edx, r10d
0x1800a13f3  xor     rax, r8
0x1800a13f6  rol     r8, 25h
0x1800a13fa  mov     [r9+268h], r8
0x1800a1401  dec     rdx
0x1800a1404  mov     [r9+260h], rax
0x1800a140b  lea     r9, [r11+40h]
0x1800a140f  movzx   eax, byte ptr [r11+24h]
0x1800a1414  lea     rdx, [r9+rdx*8]
0x1800a1418  lea     r8, [r9+rax*8]
0x1800a141c  mov     eax, [r8]
0x1800a141f  not     eax
0x1800a1421  mov     ecx, eax
0x1800a1423  test    eax, eax
0x1800a1425  jnz     short loc_1800A1440
0x1800a1427  cmp     r8, rdx
0x1800a142a  jz      short loc_1800A1432
0x1800a142c  add     r8, 8
0x1800a1430  jmp     short loc_1800A1435
0x1800a1432  mov     r8, r9
0x1800a1435  mov     eax, [r8]
0x1800a1438  not     eax
0x1800a143a  mov     ecx, eax
0x1800a143c  test    eax, eax
0x1800a143e  jz      short loc_1800A1427
0x1800a1440  movzx   edi, word ptr [rsp+118h+var_E4+2]
0x1800a1445  popcnt  rax, rcx
0x1800a144a  imul    eax, esi
0x1800a144d  shr     eax, 8
0x1800a1450  shlx    rax, rbp, rax
0x1800a1455  pdep    rcx, rax, rcx
0x1800a145a  tzcnt   rdx, rcx
0x1800a145f  shlx    rcx, r12, rdx
0x1800a1464  or      [r8], rcx
0x1800a1467  sub     r8d, r9d
0x1800a146a  mov     r12d, [rsp+118h+var_E0]
0x1800a146f  lea     ecx, [rdx+r8*4]
0x1800a1473  mov     eax, ecx
0x1800a1475  imul    ecx, ebx
0x1800a1478  shr     eax, 5
0x1800a147b  mov     [r11+24h], al
0x1800a147f  add     edi, ecx
0x1800a1481  add     rdi, r11
0x1800a1484  test    r12b, 2
0x1800a1488  jz      short loc_1800A149D
0x1800a148a  mov     edx, r13d
0x1800a148d  mov     rcx, rdi
0x1800a1490  add     rdx, 0Fh
0x1800a1494  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800a1498  call    RtlHeapZero
0x1800a149d  cmp     r13d, ebx
0x1800a14a0  jnb     loc_1800A19DB
0x1800a14a6  mov     ecx, ebx
0x1800a14a8  sub     ecx, r13d
0x1800a14ab  cmp     ecx, ebp
0x1800a14ad  jnz     short loc_1800A14BE
0x1800a14af  mov     eax, 8000h
0x1800a14b4  mov     [rbx+rdi-2], ax
0x1800a14b9  jmp     loc_1800A19DB
0x1800a14be  movzx   eax, cx
0x1800a14c1  mov     [rbx+rdi-2], cx
0x1800a14c6  jmp     loc_1800A19DB
0x1800a14cb  xor     esi, esi
0x1800a14cd  prefetchw byte ptr [r10+38h]
0x1800a14d2  mov     rbx, [r10+38h]
0x1800a14d6  test    rbx, 0FFFh
0x1800a14dd  jz      short loc_1800A150C
0x1800a14df  mov     edx, 1
0x1800a14e4  nop     dword ptr [rax+00h]
0x1800a14e8  nop     dword ptr [rax+rax+00000000h]
0x1800a14f0  lea     rcx, [rbx-1]
0x1800a14f4  mov     rax, rbx
0x1800a14f7  lock cmpxchg [r10+38h], rcx
0x1800a14fd  jz      short loc_1800A1525
0x1800a14ff  mov     esi, edx
0x1800a1501  mov     rbx, rax
0x1800a1504  test    rax, 0FFFh
0x1800a150a  jnz     short loc_1800A14F0
0x1800a150c  mov     r8d, r13d
0x1800a150f  mov     r9d, r12d
0x1800a1512  mov     rdx, r10
0x1800a1515  mov     rcx, r14; __int64
0x1800a1518  call    RtlpHpLfhSlotAllocateSlow
0x1800a151d  mov     rdi, rax
0x1800a1520  jmp     loc_1800A19DB
0x1800a1525  and     rbx, 0FFFFFFFFFFFFF000h
0x1800a152c  jz      short loc_1800A150C
0x1800a152e  movzx   r10d, byte ptr [rbx+18h]
0x1800a1533  mov     rax, rbx
0x1800a1536  mov     r8, gs:30h
0x1800a153f  mov     r12, 100000001h
0x1800a1549  shr     rax, 0Ch
0x1800a154d  mov     r15, rbx
0x1800a1550  xor     eax, [rbx+28h]
0x1800a1553  mov     rbp, rbx
0x1800a1556  xor     eax, dword ptr cs:qword_1801C5EC8
0x1800a155c  movzx   ecx, ax
0x1800a155f  mov     [rsp+118h+var_DC], eax
0x1800a1563  cmp     r13d, ecx
0x1800a1566  lea     rax, [rbx+18h]
0x1800a156a  mov     [rsp+118h+var_B0], ecx
0x1800a156e  mov     rcx, [r8+260h]
0x1800a1575  lea     r13, [rbx+40h]
0x1800a1579  cmovnb  r12, rdx
0x1800a157d  mov     [rsp+118h+var_98], rax
0x1800a1585  mov     rdx, [r8+268h]
0x1800a158c  add     r10d, 0FFFFFFF8h
0x1800a1590  lea     r9, [rdx+rcx]
0x1800a1594  xor     rdx, rcx
0x1800a1597  mov     rax, rdx
0x1800a159a  rol     rcx, 18h
0x1800a159e  shl     rax, 10h
0x1800a15a2  lea     rdi, ds:0FFFFFFFFFFFFFFF8h[r10*8]
0x1800a15aa  xor     rax, rcx
0x1800a15ad  shr     r9, 20h
0x1800a15b1  xor     rax, rdx
0x1800a15b4  movzx   r11d, r9b
0x1800a15b8  mov     [r8+260h], rax
0x1800a15bf  rol     rdx, 25h
0x1800a15c3  mov     [r8+268h], rdx
0x1800a15ca  movzx   eax, byte ptr [rbx+27h]
0x1800a15ce  movzx   r14d, byte ptr [rbx+32h]
0x1800a15d3  mov     [rsp+118h+var_E8], al
0x1800a15d7  movzx   eax, byte ptr [rbx+24h]
0x1800a15db  lea     r8, ds:0[rax*8]
0x1800a15e3  add     r8, r13
0x1800a15e6  add     rdi, r13
0x1800a15e9  nop     dword ptr [rax+00000000h]
0x1800a15f0  mov     r9, [r8]
0x1800a15f3  mov     eax, r9d
0x1800a15f6  not     eax
0x1800a15f8  test    rax, rax
0x1800a15fb  jnz     short loc_1800A1620
0x1800a15fd  nop     dword ptr [rax]
0x1800a1600  cmp     r8, rdi
0x1800a1603  jz      short loc_1800A160B
0x1800a1605  add     r8, 8
0x1800a1609  jmp     short loc_1800A160E
0x1800a160b  mov     r8, r13
0x1800a160e  mov     r9, [r8]
0x1800a1611  mov     eax, r9d
0x1800a1614  not     eax
0x1800a1616  test    rax, rax
0x1800a1619  jz      short loc_1800A1600
0x1800a161b  nop     dword ptr [rax+rax+00h]
0x1800a1620  test    byte ptr cs:qword_1801C5EE8, 4
0x1800a1627  jz      short loc_1800A1650
0x1800a1629  popcnt  rcx, rax
0x1800a162e  imul    ecx, r11d
0x1800a1632  mov     edx, 1
0x1800a1637  shr     ecx, 8
0x1800a163a  shlx    rcx, rdx, rcx
0x1800a163f  pdep    rdx, rcx, rax
0x1800a1644  tzcnt   r10, rdx
0x1800a1649  shlx    rdx, r12, r10
0x1800a164e  jmp     short loc_1800A16AA
0x1800a1650  cmp     r8, rdi
0x1800a1653  jz      short loc_1800A1670
0x1800a1655  cmp     r14d, 20h ; ' '
0x1800a1659  jnz     short loc_1800A1670
0x1800a165b  mov     ecx, r11d
0x1800a165e  ror     eax, cl
0x1800a1660  mov     ecx, eax
0x1800a1662  tzcnt   r10, rcx
0x1800a1667  add     r10d, r11d
0x1800a166a  and     r10d, 1Fh
0x1800a166e  jmp     short loc_1800A16A1
  ... truncated ...
```
