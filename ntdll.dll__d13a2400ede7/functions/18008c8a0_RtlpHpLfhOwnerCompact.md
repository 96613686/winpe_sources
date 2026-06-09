# RtlpHpLfhOwnerCompact

- ea: `0x18008c8a0`
- end: `0x18008d144`
- name: `RtlpHpLfhOwnerCompact`
- size: `2212`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18008bc34`
- `0x18008bf18`
- `0x18008c8a0`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x18002cde0`
- `0x18006fb30`
- `0x1800707b0`
- `0x18008ba7c`
- `0x18008c8a0`
- `0x18008d14c`
- `0x18008d81c`
- `0x18008da20`
- `0x18008dca0`
- `0x18008dddc`
- `0x18008de70`
- `0x18008dfa0`
- `0x18008e080`
- `0x180162810`
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
        RtlpAcquireSRWLockExclusiveContended(a2 + 16);
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
0x18008c8a0  mov     [rsp-8+arg_18], rbx
0x18008c8a5  push    rbp
0x18008c8a6  push    rsi
0x18008c8a7  push    rdi
0x18008c8a8  push    r12
0x18008c8aa  push    r13
0x18008c8ac  push    r14
0x18008c8ae  push    r15
0x18008c8b0  lea     rbp, [rsp-70h]
0x18008c8b5  sub     rsp, 170h
0x18008c8bc  mov     rax, cs:__security_cookie
0x18008c8c3  xor     rax, rsp
0x18008c8c6  mov     [rbp+0A0h+var_40], rax
0x18008c8ca  mov     r9d, 1
0x18008c8d0  mov     r12d, r8d
0x18008c8d3  mov     rsi, rdx
0x18008c8d6  mov     r14, rcx
0x18008c8d9  test    [rdx], r9b
0x18008c8dc  jnz     loc_18008CBB1
0x18008c8e2  movzx   r13d, word ptr [rdx+2]
0x18008c8e7  mov     rdi, rdx
0x18008c8ea  shl     r13, 6
0x18008c8ee  add     r13, rcx
0x18008c8f1  lea     r15, [rsi+18h]
0x18008c8f5  cmp     [r15], r15
0x18008c8f8  jz      loc_18008CBA3
0x18008c8fe  test    r12d, r12d
0x18008c901  mov     eax, 3
0x18008c906  mov     ebx, 7
0x18008c90b  cmovnz  ebx, eax
0x18008c90e  test    byte ptr [rsi], 1
0x18008c911  lea     rax, [rsp+1A0h+var_170]
0x18008c916  mov     [rsp+1A0h+var_150], ebx
0x18008c91a  mov     [rsp+1A0h+var_170], rax
0x18008c91f  lea     rax, [rsp+1A0h+var_170]
0x18008c924  mov     [rsp+1A0h+var_168], rax
0x18008c929  jnz     short loc_18008C932
0x18008c92b  cmp     word ptr [rsi+4], 0
0x18008c930  jnz     short loc_18008C962
0x18008c932  mov     rax, gs:30h
0x18008c93b  lea     rdx, [rsi+10h]
0x18008c93f  mov     r8, [rax+1850h]
0x18008c946  test    r8, r8
0x18008c949  jz      short loc_18008C956
0x18008c94b  xor     ecx, ecx
0x18008c94d  cmp     ecx, 8
0x18008c950  jb      loc_18008CE2F
0x18008c956  lock bts qword ptr [rdx], 0
0x18008c95c  jb      loc_18008D09C
0x18008c962  movzx   eax, byte ptr [rsi]
0x18008c965  test    bl, 4
0x18008c968  not     al
0x18008c96a  setnz   cl
0x18008c96d  and     cl, al
0x18008c96f  test    cl, 1
0x18008c972  jz      short loc_18008C9AA
0x18008c974  xor     ecx, ecx
0x18008c976  xor     r8d, r8d
0x18008c979  xchg    rcx, [rdi+38h]
0x18008c97d  mov     [rsp+1A0h+var_158], rcx
0x18008c982  mov     rax, [rsp+1A0h+var_158]
0x18008c987  mov     rdx, rax
0x18008c98a  and     rax, 0FFFFFFFFFFFFF000h
0x18008c990  and     edx, 0FFFh
0x18008c996  test    rdx, rdx
0x18008c999  cmovnz  r8, rax
0x18008c99d  and     ecx, 0FFFh
0x18008c9a3  jz      short loc_18008C9AA
0x18008c9a5  add     [r8+20h], cx
0x18008c9aa  mov     rdi, [r15]
0x18008c9ad  cmp     rdi, r15
0x18008c9b0  jz      short loc_18008CA0D
0x18008c9b2  movzx   eax, word ptr [rdi+12h]
0x18008c9b6  movzx   ecx, word ptr [rdi+20h]
0x18008c9ba  mov     r12, [rdi]
0x18008c9bd  add     ecx, eax
0x18008c9bf  jz      loc_18008CE45
0x18008c9c5  movzx   eax, word ptr [rdi+12h]
0x18008c9c9  test    ax, ax
0x18008c9cc  jnz     loc_18008CDFB
0x18008c9d2  movzx   eax, word ptr [rdi+12h]
0x18008c9d6  movzx   ecx, word ptr [rdi+20h]
0x18008c9da  add     ecx, eax
0x18008c9dc  movzx   eax, word ptr [rdi+22h]
0x18008c9e0  cmp     ecx, eax
0x18008c9e2  jz      loc_18008CDFB
0x18008c9e8  movzx   eax, word ptr [rdi+22h]
0x18008c9ec  cmp     [rdi+20h], ax
0x18008c9f0  jz      loc_18008CFF0
0x18008c9f6  test    bl, 4
0x18008c9f9  jz      short loc_18008CA05
0x18008c9fb  cmp     byte ptr [rdi+27h], 1
0x18008c9ff  jz      loc_18008CC4F
0x18008ca05  mov     rdi, r12
0x18008ca08  cmp     r12, r15
0x18008ca0b  jnz     short loc_18008C9B2
0x18008ca0d  xor     ebx, ebx
0x18008ca0f  xchg    rbx, [rsi+8]
0x18008ca13  test    rbx, rbx
0x18008ca16  jnz     loc_18008CE90
0x18008ca1c  lea     rax, [rsp+1A0h+var_170]
0x18008ca21  cmp     [rsp+1A0h+var_170], rax
0x18008ca26  jz      short loc_18008CA3D
0x18008ca28  mov     r8, [rsp+1A0h+var_168]
0x18008ca2d  movzx   eax, word ptr [r8+22h]
0x18008ca32  cmp     [r8+20h], ax
0x18008ca37  jnz     loc_18008D0A9
0x18008ca3d  test    byte ptr [rsi], 1
0x18008ca40  jnz     short loc_18008CA49
0x18008ca42  cmp     word ptr [rsi+4], 0
0x18008ca47  jnz     short loc_18008CA52
0x18008ca49  lea     rcx, [rsi+10h]
0x18008ca4d  call    RtlReleaseSRWLockExclusive
0x18008ca52  test    byte ptr [rsi], 1
0x18008ca55  jnz     loc_18008CDF4
0x18008ca5b  cmp     word ptr [rsi+4], 0
0x18008ca60  jz      loc_18008CDF4
0x18008ca66  mov     bl, 1
0x18008ca68  mov     rcx, [rsp+1A0h+var_170]
0x18008ca6d  lea     rax, [rsp+1A0h+var_170]
0x18008ca72  cmp     rcx, rax
0x18008ca75  jnz     loc_18008CF20
0x18008ca7b  lea     rax, [rsp+1A0h+var_170]
0x18008ca80  cmp     [rsp+1A0h+var_170], rax
0x18008ca85  jz      short loc_18008CAED
0x18008ca87  lea     rcx, [r13+10h]
0x18008ca8b  call    RtlAcquireSRWLockExclusive
0x18008ca90  mov     r8, [rsp+1A0h+var_170]
0x18008ca95  lea     rax, [rsp+1A0h+var_170]
0x18008ca9a  cmp     [r8+8], rax
0x18008ca9e  jnz     loc_18008CFD7
0x18008caa4  mov     rax, [r8]
0x18008caa7  cmp     [rax+8], r8
0x18008caab  jnz     loc_18008CFD7
0x18008cab1  lea     rcx, [rsp+1A0h+var_170]
0x18008cab6  mov     [rsp+1A0h+var_170], rax
0x18008cabb  mov     [rax+8], rcx
0x18008cabf  xor     r9d, r9d
0x18008cac2  mov     rcx, r14
0x18008cac5  mov     [rsp+1A0h+var_180], 0
0x18008cacd  mov     rdx, r13
0x18008cad0  call    RtlpHpLfhOwnerMoveSubsegment
0x18008cad5  mov     r8, [rsp+1A0h+var_170]
0x18008cada  lea     rax, [rsp+1A0h+var_170]
0x18008cadf  cmp     r8, rax
0x18008cae2  jnz     short loc_18008CA95
0x18008cae4  lea     rcx, [r13+10h]
0x18008cae8  call    RtlReleaseSRWLockExclusive
0x18008caed  test    byte ptr [rsi], 1
0x18008caf0  jnz     short loc_18008CAFD
0x18008caf2  cmp     word ptr [rsi+4], 0
0x18008caf7  jnz     loc_18008CB7B
0x18008cafd  lea     rcx, [rsi+10h]
0x18008cb01  call    RtlAcquireSRWLockShared
0x18008cb06  mov     r15, [rsi+18h]
0x18008cb0a  lea     rbx, [rsi+18h]
0x18008cb0e  cmp     r15, rbx
0x18008cb11  jz      short loc_18008CB72
0x18008cb13  movzx   eax, byte ptr [r15+27h]
0x18008cb18  cmp     al, 1
0x18008cb1a  jz      short loc_18008CB6A
0x18008cb1c  xor     r13d, r13d
0x18008cb1f  mov     [rsp+1A0h+var_160], 0
0x18008cb27  mov     r12d, 1
0x18008cb2d  cmp     al, r12b
0x18008cb30  jbe     short loc_18008CB6A
0x18008cb32  lea     r8, [rsp+1A0h+var_160]
0x18008cb37  mov     edx, r12d
0x18008cb3a  mov     rcx, r15
0x18008cb3d  call    RtlpHpLfhSubsegmentFindEmptyUnits
0x18008cb42  mov     r12d, eax
0x18008cb45  cmp     eax, 0FFFFFFFFh
0x18008cb48  jnz     loc_18008CDBC
0x18008cb4e  test    r13d, r13d
0x18008cb51  jz      short loc_18008CB66
0x18008cb53  lea     rcx, [r15+38h]
0x18008cb57  cmp     r13d, 2
0x18008cb5b  jnz     loc_18008CFE6
0x18008cb61  call    RtlReleaseSRWLockExclusive
0x18008cb66  lea     rbx, [rsi+18h]
0x18008cb6a  mov     r15, [r15]
0x18008cb6d  cmp     r15, rbx
0x18008cb70  jnz     short loc_18008CB13
0x18008cb72  lea     rcx, [rsi+10h]
0x18008cb76  call    RtlReleaseSRWLockShared
0x18008cb7b  mov     rcx, [rbp+0A0h+var_40]
0x18008cb7f  xor     rcx, rsp; StackCookie
0x18008cb82  call    __security_check_cookie
0x18008cb87  mov     rbx, [rsp+1A0h+arg_18]
0x18008cb8f  add     rsp, 170h
0x18008cb96  pop     r15
0x18008cb98  pop     r14
0x18008cb9a  pop     r13
0x18008cb9c  pop     r12
0x18008cb9e  pop     rdi
0x18008cb9f  pop     rsi
0x18008cba0  pop     rbp
0x18008cba1  retn
0x18008cba3  lea     rax, [rsi+28h]
0x18008cba7  cmp     [rax], rax
0x18008cbaa  jz      short loc_18008CB7B
0x18008cbac  jmp     loc_18008C8FE
0x18008cbb1  xor     ebx, ebx
0x18008cbb3  xor     eax, eax
0x18008cbb5  mov     r13, rsi
0x18008cbb8  cmp     [rcx+40h], al
0x18008cbbb  jbe     short loc_18008CBFE
0x18008cbbd  nop     dword ptr [rax]
0x18008cbc0  movzx   edx, byte ptr [rsi]
0x18008cbc3  shr     rdx, 1
0x18008cbc6  mov     ecx, eax
0x18008cbc8  shl     rcx, 7
0x18008cbcc  add     rdx, rcx
0x18008cbcf  movzx   r8d, word ptr [r14+rdx*2+5C0h]
0x18008cbd8  xor     edx, edx
0x18008cbda  test    ebx, ebx
0x18008cbdc  jz      short loc_18008CC39
0x18008cbde  lea     rcx, ds:0[rdx*4]
0x18008cbe6  cmp     [rsp+rcx+1A0h+var_140], r8w
0x18008cbec  jnz     short loc_18008CC33
0x18008cbee  inc     [rsp+rcx+1A0h+var_140+2]
0x18008cbf3  movzx   ecx, byte ptr [r14+40h]
0x18008cbf8  inc     eax
0x18008cbfa  cmp     eax, ecx
0x18008cbfc  jb      short loc_18008CBC0
0x18008cbfe  xor     edi, edi
0x18008cc00  xor     r15d, r15d
0x18008cc03  test    ebx, ebx
0x18008cc05  jz      loc_18008C8F1
0x18008cc0b  movzx   edi, [rsp+r15*4+1A0h+var_140]
0x18008cc11  mov     r8d, r12d
0x18008cc14  shl     rdi, 6
0x18008cc18  mov     rcx, r14
0x18008cc1b  add     rdi, r14
0x18008cc1e  mov     rdx, rdi
0x18008cc21  call    RtlpHpLfhOwnerCompact
0x18008cc26  inc     r15d
0x18008cc29  cmp     r15d, ebx
0x18008cc2c  jb      short loc_18008CC0B
0x18008cc2e  jmp     loc_18008C8F1
0x18008cc33  inc     edx
0x18008cc35  cmp     edx, ebx
0x18008cc37  jb      short loc_18008CBDE
0x18008cc39  xor     edx, edx
0x18008cc3b  mov     dword ptr [rsp+rbx*4+1A0h+var_140], edx
0x18008cc3f  mov     [rsp+rbx*4+1A0h+var_140], r8w
0x18008cc45  mov     [rsp+rbx*4+1A0h+var_140+2], r9w
0x18008cc4b  inc     ebx
0x18008cc4d  jmp     short loc_18008CBF3
0x18008cc4f  cmp     byte ptr [rdi+26h], 0
0x18008cc53  jbe     loc_18008CA05
0x18008cc59  test    byte ptr [rsi], 1
0x18008cc5c  jnz     short loc_18008CC74
0x18008cc5e  mov     rax, [rsi+38h]
0x18008cc62  xor     rax, rdi
0x18008cc65  dec     rax
0x18008cc68  cmp     rax, 0FFEh
0x18008cc6e  jbe     loc_18008CA05
0x18008cc74  movzx   r9d, byte ptr [rdi+26h]
0x18008cc79  mov     r10d, 1000h
0x18008cc7f  mov     ecx, r9d
0x18008cc82  mov     [rsp+1A0h+var_14C], 0
0x18008cc8a  mov     edx, r10d
0x18008cc8d  mov     dword ptr [rsp+1A0h+var_158], 0
0x18008cc95  shl     edx, cl
0x18008cc97  test    byte ptr cs:RtlpHpAppCompatFlags, 2
0x18008cc9e  jnz     loc_18008D114
0x18008cca4  movzx   ecx, word ptr [rdi+28h]
0x18008cca8  mov     rax, rdi
0x18008ccab  shr     rax, 0Ch
0x18008ccaf  movzx   eax, ax
0x18008ccb2  xor     ecx, eax
0x18008ccb4  mov     dword ptr [rsp+1A0h+var_158], 0
0x18008ccbc  movzx   eax, word ptr cs:qword_1801C5EC8
0x18008ccc3  xor     ecx, eax
0x18008ccc5  lea     r8d, [rcx+rcx]
0x18008ccc9  lea     eax, [r8-1]
0x18008cccd  test    r8d, eax
0x18008ccd0  jz      short loc_18008CCE1
0x18008ccd2  bsr     ecx, r8d
0x18008ccd6  mov     r8d, 1
0x18008ccdc  inc     ecx
0x18008ccde  shl     r8d, cl
0x18008cce1  cmp     r8d, r10d
0x18008cce4  mov     eax, edx
0x18008cce6  cmovbe  r8d, r10d
0x18008ccea  shr     eax, 6
0x18008cced  cmp     r8d, eax
0x18008ccf0  cmova   eax, r8d
0x18008ccf4  cmp     eax, edx
0x18008ccf6  cmovnb  eax, edx
0x18008ccf9  shr     eax, 0Ch
0x18008ccfc  bsf     eax, eax
0x18008ccff  mov     [rsp+1A0h+var_144], eax
0x18008cd03  cmp     eax, r9d
0x18008cd06  jz      loc_18008CA05
0x18008cd0c  mov     ecx, eax
0x18008cd0e  shr     edx, 0Ch
0x18008cd11  movzx   eax, word ptr [rdi+22h]
0x18008cd15  shr     edx, cl
  ... truncated ...
```
