# RtlpHpLfhOwnerCompact

- ea: `0x18006fdf0`
- end: `0x180070694`
- name: `RtlpHpLfhOwnerCompact`
- size: `2212`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006f184`
- `0x18006f468`
- `0x18006fdf0`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x18002dae0`
- `0x180053150`
- `0x180053dd0`
- `0x18006efcc`
- `0x18006fdf0`
- `0x18007069c`
- `0x180070d6c`
- `0x180070f70`
- `0x1800711f0`
- `0x18007132c`
- `0x1800713c0`
- `0x1800714f0`
- `0x1800715d0`
- `0x180162000`
- `0x18016f020`
- `0x18016f030`

## pseudocode

```c
unsigned __int64 *__fastcall RtlpHpLfhOwnerCompact(__int64 a1, unsigned __int8 *a2, unsigned int a3)
{
  volatile __int64 *v6; // rdi
  unsigned __int8 *i; // r13
  volatile __int32 **v8; // r15
  int v9; // ebx
  bool v10; // zf
  volatile signed __int32 *v11; // rdx
  _QWORD *SchedulerSharedDataSlot; // r8
  __int64 k; // rcx
  unsigned __int64 v14; // r8
  __int64 v15; // rcx
  int v16; // ecx
  volatile __int32 *v17; // rdi
  volatile __int32 **v18; // r12
  unsigned __int64 v19; // rbx
  int v20; // r8d
  bool v21; // bl
  unsigned __int64 **v22; // rcx
  unsigned __int64 *result; // rax
  unsigned __int64 *v24; // r8
  unsigned __int64 v25; // rax
  __int64 v26; // rdx
  unsigned __int8 *v27; // r15
  unsigned __int8 *m; // rbx
  unsigned __int8 v29; // al
  int v30; // r13d
  unsigned int v31; // r12d
  unsigned int EmptyUnits; // eax
  __int64 v33; // rbx
  unsigned int v34; // eax
  unsigned __int16 v35; // r8
  __int64 v36; // rdx
  __int64 j; // r15
  int v38; // r9d
  char v39; // cl
  unsigned int v40; // edx
  int v41; // ecx
  unsigned int v42; // r8d
  unsigned int v43; // ecx
  unsigned int v44; // eax
  char v45; // cl
  unsigned int v46; // eax
  unsigned int v47; // edx
  __int64 v48; // rcx
  size_t v49; // r8
  volatile __int32 *v50; // rbx
  __int64 v51; // rcx
  int v52; // eax
  __int64 v53; // r12
  unsigned __int8 v54; // cl
  __int64 v55; // rax
  unsigned int v56; // edi
  unsigned int v57; // ebx
  unsigned __int64 *v58; // rdi
  unsigned __int64 **v59; // rax
  int v60; // r8d
  unsigned __int64 *v61; // r8
  unsigned __int64 v62; // r8
  unsigned __int64 v63; // r8
  unsigned __int64 *v64; // rax
  unsigned __int64 **v65; // rcx
  unsigned __int64 **v66; // r8
  _QWORD *v67; // rax
  unsigned __int64 v68; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 *v69; // [rsp+38h] [rbp-C8h]
  unsigned int v70; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v71; // [rsp+48h] [rbp-B8h]
  int v72; // [rsp+50h] [rbp-B0h]
  int v73; // [rsp+54h] [rbp-ACh] BYREF
  int v74; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v75; // [rsp+5Ch] [rbp-A4h]
  unsigned __int16 v76[128]; // [rsp+60h] [rbp-A0h]

  if ( (*a2 & 1) != 0 )
  {
    v33 = 0;
    v34 = 0;
    for ( i = a2; v34 < *(unsigned __int8 *)(a1 + 64); ++v34 )
    {
      v35 = *(_WORD *)(a1 + 2 * (((unsigned __int64)v34 << 7) + ((unsigned __int64)*a2 >> 1)) + 1472);
      v36 = 0;
      if ( (_DWORD)v33 )
      {
        while ( v76[2 * v36] != v35 )
        {
          v36 = (unsigned int)(v36 + 1);
          if ( (unsigned int)v36 >= (unsigned int)v33 )
            goto LABEL_65;
        }
        ++v76[2 * v36 + 1];
      }
      else
      {
LABEL_65:
        *(_DWORD *)&v76[2 * v33] = 0;
        v76[2 * v33] = v35;
        v76[2 * v33 + 1] = 1;
        v33 = (unsigned int)(v33 + 1);
      }
    }
    v6 = 0;
    for ( j = 0; (unsigned int)j < (unsigned int)v33; j = (unsigned int)(j + 1) )
    {
      v6 = (volatile __int64 *)(a1 + ((unsigned __int64)v76[2 * j] << 6));
      RtlpHpLfhOwnerCompact(a1, v6, a3);
    }
  }
  else
  {
    v6 = (volatile __int64 *)a2;
    i = (unsigned __int8 *)(a1 + ((unsigned __int64)*((unsigned __int16 *)a2 + 1) << 6));
  }
  v8 = (volatile __int32 **)(a2 + 24);
  if ( *v8 != (volatile __int32 *)v8 || (result = (unsigned __int64 *)(a2 + 40), (unsigned __int64 *)*result != result) )
  {
    v9 = 7;
    if ( a3 )
      v9 = 3;
    v10 = (*a2 & 1) == 0;
    v72 = v9;
    v68 = (unsigned __int64)&v68;
    v69 = &v68;
    if ( !v10 || !*((_WORD *)a2 + 2) )
    {
      v11 = (volatile signed __int32 *)(a2 + 16);
      SchedulerSharedDataSlot = NtCurrentTeb()->SchedulerSharedDataSlot;
      if ( SchedulerSharedDataSlot )
      {
        for ( k = 0; (unsigned int)k < 8; k = (unsigned int)(k + 1) )
        {
          if ( !SchedulerSharedDataSlot[k] )
          {
            SchedulerSharedDataSlot[k] = v11;
            break;
          }
        }
      }
      if ( _interlockedbittestandset64(v11, 0) )
        RtlpAcquireSRWLockExclusiveContended(a2 + 16, v11);
    }
    if ( ((unsigned __int8)~*a2 & ((v9 & 4) != 0)) != 0 )
    {
      v14 = 0;
      v15 = _InterlockedExchange64(v6 + 7, 0);
      v71 = v15;
      if ( (v15 & 0xFFF) != 0 )
        v14 = v15 & 0xFFFFFFFFFFFFF000uLL;
      v16 = v15 & 0xFFF;
      if ( v16 )
        *(_WORD *)(v14 + 32) += v16;
    }
    v17 = *v8;
    if ( *v8 != (volatile __int32 *)v8 )
    {
      do
      {
        v18 = *(volatile __int32 ***)v17;
        if ( *((unsigned __int16 *)v17 + 9) + *((unsigned __int16 *)v17 + 16)
          || ((*a2 & 1) != 0 || ((unsigned __int64)v17 ^ *((_QWORD *)a2 + 7)) - 1 > 0xFFE)
          && !(unsigned int)RtlpHpLfhOwnerMoveSubsegment(a1, (_DWORD)a2, (_DWORD)v17, 1, 0) )
        {
          if ( (*((_WORD *)v17 + 9)
             || *((unsigned __int16 *)v17 + 9) + *((unsigned __int16 *)v17 + 16) == *((unsigned __int16 *)v17 + 17))
            && *((_WORD *)v17 + 9) )
          {
            v71 = 0;
            LODWORD(v71) = _InterlockedExchange(v17 + 4, 0);
            RtlpHpLfhSubsegmentDelayFreeListProcess(a1, v17, v71);
          }
          if ( *((_WORD *)v17 + 16) == *((_WORD *)v17 + 17) )
          {
            RtlpHpLfhOwnerMoveSubsegment(a1, (_DWORD)a2, (_DWORD)v17, 3, 0);
            v62 = v68;
            if ( *(unsigned __int64 **)(v68 + 8) != &v68 )
              goto LABEL_111;
            *(_QWORD *)v17 = v68;
            *((_QWORD *)v17 + 1) = &v68;
            *(_QWORD *)(v62 + 8) = v17;
            v68 = (unsigned __int64)v17;
          }
          else if ( (v9 & 4) != 0
                 && *((_BYTE *)v17 + 39) == 1
                 && *((_BYTE *)v17 + 38)
                 && ((*a2 & 1) != 0 || ((unsigned __int64)v17 ^ *((_QWORD *)a2 + 7)) - 1 > 0xFFE) )
          {
            v38 = *((unsigned __int8 *)v17 + 38);
            v39 = *((_BYTE *)v17 + 38);
            v73 = 0;
            LODWORD(v71) = 0;
            v40 = 4096 << v39;
            if ( (RtlpHpAppCompatFlags & 2) != 0 )
            {
              v44 = 4096 << v39;
            }
            else
            {
              v41 = (unsigned __int16)((unsigned __int64)v17 >> 12) ^ *((unsigned __int16 *)v17 + 20);
              LODWORD(v71) = 0;
              v42 = 2 * ((unsigned __int16)qword_1801C5EC8 ^ v41);
              if ( ((v42 - 1) & v42) != 0 )
              {
                _BitScanReverse(&v43, v42);
                v42 = 1 << (v43 + 1);
              }
              if ( v42 <= 0x1000 )
                v42 = 4096;
              v44 = v40 >> 6;
              if ( v42 > v40 >> 6 )
                v44 = v42;
              if ( v44 >= v40 )
                v44 = v40;
            }
            _BitScanForward(&v44, v44 >> 12);
            v75 = v44;
            if ( v44 != v38 )
            {
              v45 = v44;
              v46 = *((unsigned __int16 *)v17 + 17);
              v47 = v40 >> 12 >> v45;
              v48 = v47 * *((unsigned __int16 *)v17 + 16);
              LODWORD(v71) = v47;
              if ( (unsigned int)v48 >= v46 )
              {
                v74 = 0;
                if ( (unsigned int)RtlpHpLfhSubsegmentReformatCheck(v48, v17, &v74, &v73) )
                {
                  BYTE1(v70) = v71;
                  v49 = 2LL * (unsigned int)v71;
                  LOBYTE(v70) = v75;
                  *((_WORD *)v17 + 19) = v70;
                  v50 = &v17[2 * *((unsigned __int8 *)v17 + 24)];
                  memset_thunk_772440563353939046((void *)v50, 0, v49);
                  RtlpHpLfhSubsegmentConstructCommitState(v51, v17, v17 + 16, v50);
                  v52 = RtlpHpLfhSubsegmentCountEmptyUnits(v17);
                  if ( v52 )
                    RtlpHpLfhContextUpdateFreeCommitCount(
                      a1,
                      v17,
                      (unsigned __int64)(unsigned int)(v52 << 12 << *((_BYTE *)v17 + 38)) >> 12);
                  LOBYTE(v9) = v72;
                }
              }
            }
          }
        }
        v17 = (volatile __int32 *)v18;
      }
      while ( v18 != v8 );
    }
    v19 = _InterlockedExchange64((volatile __int64 *)a2 + 1, 0);
    if ( v19 )
    {
      while ( 1 )
      {
        v53 = *(_QWORD *)(v19 + 24);
        if ( (*(_WORD *)(v19 + 18)
           || *(unsigned __int16 *)(v19 + 18) + *(unsigned __int16 *)(v19 + 32) == *(unsigned __int16 *)(v19 + 34))
          && *(_WORD *)(v19 + 18) )
        {
          v71 = 0;
          LODWORD(v71) = _InterlockedExchange((volatile __int32 *)(v19 + 16), 0);
          RtlpHpLfhSubsegmentDelayFreeListProcess(a1, v19, v71);
        }
        if ( *(_WORD *)(v19 + 32) == *(_WORD *)(v19 + 34) )
        {
          RtlpHpLfhOwnerMoveSubsegment(a1, (_DWORD)a2, v19, 3, 0);
          v63 = v68;
          if ( *(unsigned __int64 **)(v68 + 8) != &v68 )
            goto LABEL_111;
          *(_QWORD *)v19 = v68;
          *(_QWORD *)(v19 + 8) = &v68;
          *(_QWORD *)(v63 + 8) = v19;
          v68 = v19;
        }
        else if ( !(unsigned int)RtlpHpLfhOwnerMoveSubsegment(a1, (_DWORD)a2, v19, 0, 0) )
        {
          RtlpHpLfhOwnerMoveSubsegment(a1, (_DWORD)a2, v60, 3, 0);
          v61 = v69;
          if ( (unsigned __int64 *)*v69 != &v68 )
            goto LABEL_111;
          *(_QWORD *)(v19 + 8) = v69;
          *(_QWORD *)v19 = &v68;
          *v61 = v19;
          v69 = (unsigned __int64 *)v19;
        }
        v19 = v53 & 0xFFFFFFFFFFFFF000uLL;
        if ( (v53 & 0xFFFFFFFFFFFFF000uLL) == 0 )
          goto LABEL_27;
      }
    }
    do
    {
LABEL_27:
      if ( (unsigned __int64 *)v68 == &v68 )
        goto LABEL_29;
      v20 = (int)v69;
      if ( *((_WORD *)v69 + 16) == *((_WORD *)v69 + 17) )
        goto LABEL_29;
      v64 = (unsigned __int64 *)*v69;
      if ( *(unsigned __int64 **)(*v69 + 8) != v69 )
        goto LABEL_111;
      v65 = (unsigned __int64 **)v69[1];
      if ( *v65 != v69 )
        goto LABEL_111;
      *v65 = v64;
      v64[1] = (unsigned __int64)v65;
    }
    while ( (unsigned int)RtlpHpLfhOwnerMoveSubsegment(a1, (_DWORD)a2, v20, 0, 0) );
    v67 = v69;
    if ( (unsigned __int64 *)*v69 != &v68 )
LABEL_111:
      __fastfail(3u);
    v66[1] = v69;
    *v66 = &v68;
    *v67 = v66;
    v69 = (unsigned __int64 *)v66;
LABEL_29:
    if ( (*a2 & 1) != 0 || !*((_WORD *)a2 + 2) )
      RtlReleaseSRWLockExclusive(a2 + 16);
    v21 = (*a2 & 1) == 0 && *((_WORD *)a2 + 2);
    v22 = (unsigned __int64 **)v68;
    if ( (unsigned __int64 *)v68 != &v68 )
    {
      do
      {
        v58 = *v22;
        if ( v21 || *((_WORD *)v22 + 16) != *((_WORD *)v22 + 17) )
        {
          if ( (*((_BYTE *)v22 + 51) & 1) != 0 )
            *((_BYTE *)v22 + 51) &= ~1u;
        }
        else
        {
          if ( (unsigned __int64 **)v58[1] != v22 )
            goto LABEL_111;
          v59 = (unsigned __int64 **)v22[1];
          if ( *v59 != (unsigned __int64 *)v22 )
            goto LABEL_111;
          *v59 = v58;
          v58[1] = (unsigned __int64)v59;
          RtlpHpLfhSubsegmentFree(a1, v22, i);
        }
        v22 = (unsigned __int64 **)v58;
      }
      while ( v58 != &v68 );
    }
    result = &v68;
    if ( (unsigned __int64 *)v68 != &v68 )
    {
      RtlAcquireSRWLockExclusive(i + 16);
      v24 = (unsigned __int64 *)v68;
      do
      {
        if ( (unsigned __int64 *)v24[1] != &v68 )
          goto LABEL_111;
        v25 = *v24;
        if ( *(unsigned __int64 **)(*v24 + 8) != v24 )
          goto LABEL_111;
        v68 = *v24;
        *(_QWORD *)(v25 + 8) = &v68;
        RtlpHpLfhOwnerMoveSubsegment(a1, (_DWORD)i, (_DWORD)v24, 0, 0);
        v24 = (unsigned __int64 *)v68;
      }
      while ( (unsigned __int64 *)v68 != &v68 );
      result = (unsigned __int64 *)RtlReleaseSRWLockExclusive(i + 16);
    }
    if ( (*a2 & 1) != 0 || !*((_WORD *)a2 + 2) )
    {
      RtlAcquireSRWLockShared(a2 + 16);
      v27 = (unsigned __int8 *)*((_QWORD *)a2 + 3);
      for ( m = a2 + 24; v27 != m; v27 = *(unsigned __int8 **)v27 )
      {
        v29 = v27[39];
        if ( v29 != 1 )
        {
          v30 = 0;
          v70 = 0;
          v31 = 1;
          if ( v29 > 1u )
          {
            do
            {
              EmptyUnits = RtlpHpLfhSubsegmentFindEmptyUnits(v27, v31, &v70);
              v31 = EmptyUnits;
              if ( EmptyUnits == -1 )
                break;
              v26 = v70;
              if ( v70 )
              {
                if ( v30 )
                {
                  v54 = v27[38];
                  v55 = EmptyUnits << 12 << v54;
                  v56 = v55;
                  v57 = v70 << 12 << v54;
                  ((void (__fastcall *)(_QWORD, unsigned __int8 *, _QWORD))(RtlpHpHeapGlobals ^ *(_QWORD *)(a1 + 32)
                                                                                              ^ a1))(
                    *(_QWORD *)a1,
                    &v27[v55],
                    v57);
                  RtlpHpLfhSubsegmentDecBlockCounts(a1, v27, v56, v57);
                  v31 += v70;
                }
                else
                {
                  v30 = 2;
                  RtlAcquireSRWLockExclusive(v27 + 56);
                }
              }
              else
              {
                v31 = EmptyUnits;
              }
            }
            while ( v31 < v27[39] );
            if ( v30 )
              RtlReleaseSRWLockExclusive(v27 + 56);
            m = a2 + 24;
          }
        }
      }
      return (unsigned __int64 *)RtlReleaseSRWLockShared(a2 + 16, v26);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006fdf0  mov     [rsp-8+arg_18], rbx
0x18006fdf5  push    rbp
0x18006fdf6  push    rsi
0x18006fdf7  push    rdi
0x18006fdf8  push    r12
0x18006fdfa  push    r13
0x18006fdfc  push    r14
0x18006fdfe  push    r15
0x18006fe00  lea     rbp, [rsp-70h]
0x18006fe05  sub     rsp, 170h
0x18006fe0c  mov     rax, cs:__security_cookie
0x18006fe13  xor     rax, rsp
0x18006fe16  mov     [rbp+0A0h+var_40], rax
0x18006fe1a  mov     r9d, 1
0x18006fe20  mov     r12d, r8d
0x18006fe23  mov     rsi, rdx
0x18006fe26  mov     r14, rcx
0x18006fe29  test    [rdx], r9b
0x18006fe2c  jnz     loc_180070101
0x18006fe32  movzx   r13d, word ptr [rdx+2]
0x18006fe37  mov     rdi, rdx
0x18006fe3a  shl     r13, 6
0x18006fe3e  add     r13, rcx
0x18006fe41  lea     r15, [rsi+18h]
0x18006fe45  cmp     [r15], r15
0x18006fe48  jz      loc_1800700F3
0x18006fe4e  test    r12d, r12d
0x18006fe51  mov     eax, 3
0x18006fe56  mov     ebx, 7
0x18006fe5b  cmovnz  ebx, eax
0x18006fe5e  test    byte ptr [rsi], 1
0x18006fe61  lea     rax, [rsp+1A0h+var_170]
0x18006fe66  mov     [rsp+1A0h+var_150], ebx
0x18006fe6a  mov     [rsp+1A0h+var_170], rax
0x18006fe6f  lea     rax, [rsp+1A0h+var_170]
0x18006fe74  mov     [rsp+1A0h+var_168], rax
0x18006fe79  jnz     short loc_18006FE82
0x18006fe7b  cmp     word ptr [rsi+4], 0
0x18006fe80  jnz     short loc_18006FEB2
0x18006fe82  mov     rax, gs:30h
0x18006fe8b  lea     rdx, [rsi+10h]
0x18006fe8f  mov     r8, [rax+1850h]
0x18006fe96  test    r8, r8
0x18006fe99  jz      short loc_18006FEA6
0x18006fe9b  xor     ecx, ecx
0x18006fe9d  cmp     ecx, 8
0x18006fea0  jb      loc_18007037F
0x18006fea6  lock bts qword ptr [rdx], 0
0x18006feac  jb      loc_1800705EC
0x18006feb2  movzx   eax, byte ptr [rsi]
0x18006feb5  test    bl, 4
0x18006feb8  not     al
0x18006feba  setnz   cl
0x18006febd  and     cl, al
0x18006febf  test    cl, 1
0x18006fec2  jz      short loc_18006FEFA
0x18006fec4  xor     ecx, ecx
0x18006fec6  xor     r8d, r8d
0x18006fec9  xchg    rcx, [rdi+38h]
0x18006fecd  mov     [rsp+1A0h+var_158], rcx
0x18006fed2  mov     rax, [rsp+1A0h+var_158]
0x18006fed7  mov     rdx, rax
0x18006feda  and     rax, 0FFFFFFFFFFFFF000h
0x18006fee0  and     edx, 0FFFh
0x18006fee6  test    rdx, rdx
0x18006fee9  cmovnz  r8, rax
0x18006feed  and     ecx, 0FFFh
0x18006fef3  jz      short loc_18006FEFA
0x18006fef5  add     [r8+20h], cx
0x18006fefa  mov     rdi, [r15]
0x18006fefd  cmp     rdi, r15
0x18006ff00  jz      short loc_18006FF5D
0x18006ff02  movzx   eax, word ptr [rdi+12h]
0x18006ff06  movzx   ecx, word ptr [rdi+20h]
0x18006ff0a  mov     r12, [rdi]
0x18006ff0d  add     ecx, eax
0x18006ff0f  jz      loc_180070395
0x18006ff15  movzx   eax, word ptr [rdi+12h]
0x18006ff19  test    ax, ax
0x18006ff1c  jnz     loc_18007034B
0x18006ff22  movzx   eax, word ptr [rdi+12h]
0x18006ff26  movzx   ecx, word ptr [rdi+20h]
0x18006ff2a  add     ecx, eax
0x18006ff2c  movzx   eax, word ptr [rdi+22h]
0x18006ff30  cmp     ecx, eax
0x18006ff32  jz      loc_18007034B
0x18006ff38  movzx   eax, word ptr [rdi+22h]
0x18006ff3c  cmp     [rdi+20h], ax
0x18006ff40  jz      loc_180070540
0x18006ff46  test    bl, 4
0x18006ff49  jz      short loc_18006FF55
0x18006ff4b  cmp     byte ptr [rdi+27h], 1
0x18006ff4f  jz      loc_18007019F
0x18006ff55  mov     rdi, r12
0x18006ff58  cmp     r12, r15
0x18006ff5b  jnz     short loc_18006FF02
0x18006ff5d  xor     ebx, ebx
0x18006ff5f  xchg    rbx, [rsi+8]
0x18006ff63  test    rbx, rbx
0x18006ff66  jnz     loc_1800703E0
0x18006ff6c  lea     rax, [rsp+1A0h+var_170]
0x18006ff71  cmp     [rsp+1A0h+var_170], rax
0x18006ff76  jz      short loc_18006FF8D
0x18006ff78  mov     r8, [rsp+1A0h+var_168]
0x18006ff7d  movzx   eax, word ptr [r8+22h]
0x18006ff82  cmp     [r8+20h], ax
0x18006ff87  jnz     loc_1800705F9
0x18006ff8d  test    byte ptr [rsi], 1
0x18006ff90  jnz     short loc_18006FF99
0x18006ff92  cmp     word ptr [rsi+4], 0
0x18006ff97  jnz     short loc_18006FFA2
0x18006ff99  lea     rcx, [rsi+10h]
0x18006ff9d  call    RtlReleaseSRWLockExclusive
0x18006ffa2  test    byte ptr [rsi], 1
0x18006ffa5  jnz     loc_180070344
0x18006ffab  cmp     word ptr [rsi+4], 0
0x18006ffb0  jz      loc_180070344
0x18006ffb6  mov     bl, 1
0x18006ffb8  mov     rcx, [rsp+1A0h+var_170]
0x18006ffbd  lea     rax, [rsp+1A0h+var_170]
0x18006ffc2  cmp     rcx, rax
0x18006ffc5  jnz     loc_180070470
0x18006ffcb  lea     rax, [rsp+1A0h+var_170]
0x18006ffd0  cmp     [rsp+1A0h+var_170], rax
0x18006ffd5  jz      short loc_18007003D
0x18006ffd7  lea     rcx, [r13+10h]
0x18006ffdb  call    RtlAcquireSRWLockExclusive
0x18006ffe0  mov     r8, [rsp+1A0h+var_170]
0x18006ffe5  lea     rax, [rsp+1A0h+var_170]
0x18006ffea  cmp     [r8+8], rax
0x18006ffee  jnz     loc_180070527
0x18006fff4  mov     rax, [r8]
0x18006fff7  cmp     [rax+8], r8
0x18006fffb  jnz     loc_180070527
0x180070001  lea     rcx, [rsp+1A0h+var_170]
0x180070006  mov     [rsp+1A0h+var_170], rax
0x18007000b  mov     [rax+8], rcx
0x18007000f  xor     r9d, r9d
0x180070012  mov     rcx, r14
0x180070015  mov     [rsp+1A0h+var_180], 0
0x18007001d  mov     rdx, r13
0x180070020  call    RtlpHpLfhOwnerMoveSubsegment
0x180070025  mov     r8, [rsp+1A0h+var_170]
0x18007002a  lea     rax, [rsp+1A0h+var_170]
0x18007002f  cmp     r8, rax
0x180070032  jnz     short loc_18006FFE5
0x180070034  lea     rcx, [r13+10h]
0x180070038  call    RtlReleaseSRWLockExclusive
0x18007003d  test    byte ptr [rsi], 1
0x180070040  jnz     short loc_18007004D
0x180070042  cmp     word ptr [rsi+4], 0
0x180070047  jnz     loc_1800700CB
0x18007004d  lea     rcx, [rsi+10h]
0x180070051  call    RtlAcquireSRWLockShared
0x180070056  mov     r15, [rsi+18h]
0x18007005a  lea     rbx, [rsi+18h]
0x18007005e  cmp     r15, rbx
0x180070061  jz      short loc_1800700C2
0x180070063  movzx   eax, byte ptr [r15+27h]
0x180070068  cmp     al, 1
0x18007006a  jz      short loc_1800700BA
0x18007006c  xor     r13d, r13d
0x18007006f  mov     [rsp+1A0h+var_160], 0
0x180070077  mov     r12d, 1
0x18007007d  cmp     al, r12b
0x180070080  jbe     short loc_1800700BA
0x180070082  lea     r8, [rsp+1A0h+var_160]
0x180070087  mov     edx, r12d
0x18007008a  mov     rcx, r15
0x18007008d  call    RtlpHpLfhSubsegmentFindEmptyUnits
0x180070092  mov     r12d, eax
0x180070095  cmp     eax, 0FFFFFFFFh
0x180070098  jnz     loc_18007030C
0x18007009e  test    r13d, r13d
0x1800700a1  jz      short loc_1800700B6
0x1800700a3  lea     rcx, [r15+38h]
0x1800700a7  cmp     r13d, 2
0x1800700ab  jnz     loc_180070536
0x1800700b1  call    RtlReleaseSRWLockExclusive
0x1800700b6  lea     rbx, [rsi+18h]
0x1800700ba  mov     r15, [r15]
0x1800700bd  cmp     r15, rbx
0x1800700c0  jnz     short loc_180070063
0x1800700c2  lea     rcx, [rsi+10h]
0x1800700c6  call    RtlReleaseSRWLockShared
0x1800700cb  mov     rcx, [rbp+0A0h+var_40]
0x1800700cf  xor     rcx, rsp; StackCookie
0x1800700d2  call    __security_check_cookie
0x1800700d7  mov     rbx, [rsp+1A0h+arg_18]
0x1800700df  add     rsp, 170h
0x1800700e6  pop     r15
0x1800700e8  pop     r14
0x1800700ea  pop     r13
0x1800700ec  pop     r12
0x1800700ee  pop     rdi
0x1800700ef  pop     rsi
0x1800700f0  pop     rbp
0x1800700f1  retn
0x1800700f3  lea     rax, [rsi+28h]
0x1800700f7  cmp     [rax], rax
0x1800700fa  jz      short loc_1800700CB
0x1800700fc  jmp     loc_18006FE4E
0x180070101  xor     ebx, ebx
0x180070103  xor     eax, eax
0x180070105  mov     r13, rsi
0x180070108  cmp     [rcx+40h], al
0x18007010b  jbe     short loc_18007014E
0x18007010d  nop     dword ptr [rax]
0x180070110  movzx   edx, byte ptr [rsi]
0x180070113  shr     rdx, 1
0x180070116  mov     ecx, eax
0x180070118  shl     rcx, 7
0x18007011c  add     rdx, rcx
0x18007011f  movzx   r8d, word ptr [r14+rdx*2+5C0h]
0x180070128  xor     edx, edx
0x18007012a  test    ebx, ebx
0x18007012c  jz      short loc_180070189
0x18007012e  lea     rcx, ds:0[rdx*4]
0x180070136  cmp     [rsp+rcx+1A0h+var_140], r8w
0x18007013c  jnz     short loc_180070183
0x18007013e  inc     [rsp+rcx+1A0h+var_140+2]
0x180070143  movzx   ecx, byte ptr [r14+40h]
0x180070148  inc     eax
0x18007014a  cmp     eax, ecx
0x18007014c  jb      short loc_180070110
0x18007014e  xor     edi, edi
0x180070150  xor     r15d, r15d
0x180070153  test    ebx, ebx
0x180070155  jz      loc_18006FE41
0x18007015b  movzx   edi, [rsp+r15*4+1A0h+var_140]
0x180070161  mov     r8d, r12d
0x180070164  shl     rdi, 6
0x180070168  mov     rcx, r14
0x18007016b  add     rdi, r14
0x18007016e  mov     rdx, rdi
0x180070171  call    RtlpHpLfhOwnerCompact
0x180070176  inc     r15d
0x180070179  cmp     r15d, ebx
0x18007017c  jb      short loc_18007015B
0x18007017e  jmp     loc_18006FE41
0x180070183  inc     edx
0x180070185  cmp     edx, ebx
0x180070187  jb      short loc_18007012E
0x180070189  xor     edx, edx
0x18007018b  mov     dword ptr [rsp+rbx*4+1A0h+var_140], edx
0x18007018f  mov     [rsp+rbx*4+1A0h+var_140], r8w
0x180070195  mov     [rsp+rbx*4+1A0h+var_140+2], r9w
0x18007019b  inc     ebx
0x18007019d  jmp     short loc_180070143
0x18007019f  cmp     byte ptr [rdi+26h], 0
0x1800701a3  jbe     loc_18006FF55
0x1800701a9  test    byte ptr [rsi], 1
0x1800701ac  jnz     short loc_1800701C4
0x1800701ae  mov     rax, [rsi+38h]
0x1800701b2  xor     rax, rdi
0x1800701b5  dec     rax
0x1800701b8  cmp     rax, 0FFEh
0x1800701be  jbe     loc_18006FF55
0x1800701c4  movzx   r9d, byte ptr [rdi+26h]
0x1800701c9  mov     r10d, 1000h
0x1800701cf  mov     ecx, r9d
0x1800701d2  mov     [rsp+1A0h+var_14C], 0
0x1800701da  mov     edx, r10d
0x1800701dd  mov     dword ptr [rsp+1A0h+var_158], 0
0x1800701e5  shl     edx, cl
0x1800701e7  test    byte ptr cs:RtlpHpAppCompatFlags, 2
0x1800701ee  jnz     loc_180070664
0x1800701f4  movzx   ecx, word ptr [rdi+28h]
0x1800701f8  mov     rax, rdi
0x1800701fb  shr     rax, 0Ch
0x1800701ff  movzx   eax, ax
0x180070202  xor     ecx, eax
0x180070204  mov     dword ptr [rsp+1A0h+var_158], 0
0x18007020c  movzx   eax, word ptr cs:qword_1801C5EC8
0x180070213  xor     ecx, eax
0x180070215  lea     r8d, [rcx+rcx]
0x180070219  lea     eax, [r8-1]
0x18007021d  test    r8d, eax
0x180070220  jz      short loc_180070231
0x180070222  bsr     ecx, r8d
0x180070226  mov     r8d, 1
0x18007022c  inc     ecx
0x18007022e  shl     r8d, cl
0x180070231  cmp     r8d, r10d
0x180070234  mov     eax, edx
0x180070236  cmovbe  r8d, r10d
0x18007023a  shr     eax, 6
0x18007023d  cmp     r8d, eax
0x180070240  cmova   eax, r8d
0x180070244  cmp     eax, edx
0x180070246  cmovnb  eax, edx
0x180070249  shr     eax, 0Ch
0x18007024c  bsf     eax, eax
0x18007024f  mov     [rsp+1A0h+var_144], eax
0x180070253  cmp     eax, r9d
0x180070256  jz      loc_18006FF55
0x18007025c  mov     ecx, eax
0x18007025e  shr     edx, 0Ch
0x180070261  movzx   eax, word ptr [rdi+22h]
0x180070265  shr     edx, cl
  ... truncated ...
```
