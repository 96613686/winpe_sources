# TppWorkerFindTask

- ea: `0x180015d00`
- end: `0x18001654f`
- name: `TppWorkerFindTask`
- size: `2127`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016fa0`

## callees

- `0x180015d00`
- `0x180017e90`
- `0x1800183a0`
- `0x18001855c`
- `0x18002b3e0`
- `0x18002cde0`
- `0x18006f0d0`
- `0x1800e09f0`
- `0x1800e8868`
- `0x18015ec80`
- `0x18015f690`
- `0x18015f910`
- `0x180162810`

## pseudocode

```c
__int64 __fastcall TppWorkerFindTask(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned __int8 Number; // r14
  unsigned int v6; // r15d
  int Group; // esi
  int v8; // eax
  unsigned __int64 i; // rdx
  __int64 v10; // rax
  __int64 SchedulerSharedDataSlot; // r8
  __int64 v12; // rdi
  int v13; // esi
  __int64 j; // r9
  int v15; // eax
  unsigned int v16; // r12d
  int k; // r13d
  __int64 v18; // r9
  __int64 v19; // r12
  volatile signed __int32 *v20; // r14
  unsigned int m; // ecx
  __int64 v22; // rsi
  __int64 v23; // rax
  signed __int64 v24; // rax
  __int64 v25; // r14
  unsigned int v26; // ecx
  _BYTE *v27; // rdi
  __int64 v28; // r13
  __int64 v29; // rdi
  char v30; // r14
  int v31; // esi
  int v32; // eax
  int *v33; // rax
  int v34; // ecx
  __int64 v36; // rdx
  signed __int64 v37; // rcx
  signed __int64 v38; // rtt
  __int64 v39; // r13
  _QWORD *v40; // rdx
  _QWORD *v41; // rax
  __int64 v42; // rax
  bool v43; // zf
  signed __int64 v44; // rax
  __int64 v45; // rdi
  __int64 v46; // rcx
  __int64 v47; // r11
  __int64 v48; // rdx
  __int64 v49; // rcx
  unsigned __int16 v50; // r12
  __int64 v51; // r8
  __int64 v52; // r9
  __int64 v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // rcx
  signed __int64 v56; // rax
  __int64 v57; // r11
  __int64 v58; // r9
  __int64 v59; // r8
  __int64 v60; // rcx
  unsigned int v61; // eax
  __int16 v62; // ax
  __int64 v63; // rax
  int v64; // edi
  int v65; // [rsp+30h] [rbp-69h] BYREF
  int v66; // [rsp+34h] [rbp-65h] BYREF
  int v67; // [rsp+38h] [rbp-61h]
  _QWORD *v68; // [rsp+40h] [rbp-59h]
  __int64 v69; // [rsp+48h] [rbp-51h]
  _DWORD v70[2]; // [rsp+50h] [rbp-49h] BYREF
  __int64 v71; // [rsp+58h] [rbp-41h]
  __int128 v72; // [rsp+60h] [rbp-39h]
  __int64 v73; // [rsp+70h] [rbp-29h]
  int v74; // [rsp+78h] [rbp-21h]
  unsigned int v75; // [rsp+7Ch] [rbp-1Dh]
  __int16 v76; // [rsp+80h] [rbp-19h]
  unsigned __int16 v77; // [rsp+82h] [rbp-17h]
  __int64 v78; // [rsp+84h] [rbp-15h]
  int v79; // [rsp+8Ch] [rbp-Dh]
  __int128 v80; // [rsp+90h] [rbp-9h] BYREF
  __int128 v81; // [rsp+A0h] [rbp+7h] BYREF

  v68 = a3;
  v69 = a2;
  Number = NtCurrentTeb()->CurrentIdealProcessor.Number;
  v6 = TppNumberNodes;
  Group = NtCurrentTeb()->CurrentIdealProcessor.Group;
  if ( !a1 || (v8 = *(_DWORD *)(a1 + 440)) == 0 )
    v8 = MEMORY[0x7FFE03C0];
  if ( *(_DWORD *)(a1 + 424) != v8 )
  {
    RtlAcquireSRWLockExclusive(a1 + 72);
    TppAdjustRunningThreadGoalWithLock(a1);
    RtlReleaseSRWLockExclusive(a1 + 72);
  }
  for ( i = 0; (unsigned int)i < TppNumberNodes; i = (unsigned int)(i + 1) )
  {
    v10 = *(_QWORD *)(a1 + 48);
    if ( *(_WORD *)(v10 + 16LL * (unsigned int)(Group + TppMaximumGroups * i) + 8) == (_WORD)Group )
    {
      SchedulerSharedDataSlot = 1LL << Number;
      if ( ((1LL << Number) & *(_QWORD *)(v10 + 16LL * (unsigned int)(Group + TppMaximumGroups * i))) != 0 )
      {
        v6 = i;
        goto LABEL_11;
      }
    }
  }
  SchedulerSharedDataSlot = 1LL << Number;
LABEL_11:
  v12 = *(unsigned int *)(a2 + 352);
  v13 = *(unsigned __int16 *)(a2 + 362);
  j = 0xFFFF;
  v15 = *(_DWORD *)(a1 + 428);
  v66 = 0;
  v67 = 0xFFFF;
  v81 = 0;
  if ( v6 == (_DWORD)v12 )
  {
    if ( v15 == -1 && !*(_BYTE *)(a2 + 360) )
    {
      *(_BYTE *)(a2 + 360) = 1;
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 40) + 4LL * v6));
    }
  }
  else
  {
    if ( v15 == -1 )
    {
      if ( *(_BYTE *)(a2 + 360) )
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 40) + 4 * v12));
      else
        *(_BYTE *)(a2 + 360) = 1;
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 40) + 4LL * v6));
    }
    v47 = *(_QWORD *)(a1 + 48);
    v48 = TppMaximumGroups * v6;
    v49 = 2LL * (unsigned int)(v48 + v13);
    if ( (SchedulerSharedDataSlot & *(_QWORD *)(v47 + 16LL * (unsigned int)(v48 + v13))) != 0 )
    {
      v50 = v13;
    }
    else
    {
      v50 = -1;
      for ( j = 0; (unsigned __int16)j < (unsigned int)TppMaximumGroups; LOWORD(j) = j + 1 )
      {
        if ( (_WORD)j != (_WORD)v13 )
        {
          v49 = 2LL * ((unsigned int)v48 + (unsigned __int16)j);
          if ( (SchedulerSharedDataSlot & *(_QWORD *)(v47 + 16LL * ((unsigned int)v48 + (unsigned __int16)j))) != 0 )
          {
            v50 = j;
            break;
          }
        }
      }
    }
    *(_DWORD *)(a2 + 352) = v6;
    *(_WORD *)(a2 + 362) = v50;
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v49, v48, SchedulerSharedDataSlot, j) )
      v53 = (__int64)NtCurrentPeb()->SharedData + 556;
    else
      v53 = 2147353478;
    if ( *(_BYTE *)v53 )
    {
      v54 = *(_QWORD *)(a1 + 40);
      v78 = 0;
      v70[0] = 0;
      v70[1] = 472449024;
      v71 = 0;
      v72 = 0;
      v79 = 0;
      v73 = a1;
      v74 = v12;
      v75 = v6;
      v76 = v13;
      v77 = v50;
      LODWORD(v78) = *(_DWORD *)(v54 + 4 * v12);
      HIDWORD(v78) = *(_DWORD *)(v54 + 4LL * v6);
      if ( (unsigned int)RtlGetCurrentServiceSessionId(HIDWORD(v78), v54, v51, v52) )
        v55 = (__int64)NtCurrentPeb()->SharedData + 556;
      else
        v55 = 2147353478;
      NtTraceEvent(*(unsigned __int8 *)v55, 1026, 28, v70);
    }
    v81 = 0;
    NtSetInformationThread(-2, 30, &v81, 16);
    v66 = v50;
    BYTE2(v66) = Number;
    NtSetInformationThread(-2, 33, &v66, 4);
  }
  v16 = v6;
  if ( *(_DWORD *)(a1 + 428) == -1 && *(_DWORD *)(a2 + 356) >= 0x10u && !(unsigned int)TppAreNodeWorkersSteadyState(a1) )
  {
    do
    {
LABEL_43:
      if ( *(_BYTE *)(a1 + 377) )
        return 0;
      v64 = 0;
LABEL_117:
      ;
    }
    while ( v64 > 2 );
    while ( 1 )
    {
      v22 = TppQueueRemoveHead(*(_QWORD *)(a1 + 8LL * v64 + 16) + 24LL * v16, i, SchedulerSharedDataSlot, v18);
      if ( v22 )
        break;
      if ( ++v16 >= TppNumberNodes )
        v16 = 0;
      if ( v16 == v6 )
      {
        ++v64;
        goto LABEL_117;
      }
    }
  }
  else
  {
    for ( k = 0; ; ++k )
    {
      v65 = k;
      v18 = 3;
      if ( k > 2 )
      {
        v16 = v6;
        goto LABEL_43;
      }
      v19 = *(_QWORD *)(a1 + 8LL * k + 16) + 24LL * v6;
      v20 = (volatile signed __int32 *)(v19 + 16);
      SchedulerSharedDataSlot = (__int64)NtCurrentTeb()->SchedulerSharedDataSlot;
      if ( SchedulerSharedDataSlot )
      {
        for ( m = 0; m < 8; ++m )
        {
          if ( !*(_QWORD *)(SchedulerSharedDataSlot + 8LL * m) )
          {
            *(_QWORD *)(SchedulerSharedDataSlot + 8LL * m) = v20;
            break;
          }
        }
      }
      if ( _interlockedbittestandset64(v20, 0) )
        RtlpAcquireSRWLockExclusiveContended(v19 + 16);
      v22 = *(_QWORD *)v19;
      if ( *(_QWORD *)(*(_QWORD *)v19 + 8LL) != v19 || (v23 = *(_QWORD *)v22, *(_QWORD *)(*(_QWORD *)v22 + 8LL) != v22) )
        __fastfail(3u);
      *(_QWORD *)v19 = v23;
      *(_QWORD *)(v23 + 8) = v19;
      v24 = _InterlockedCompareExchange64((volatile signed __int64 *)v20, 0, 1);
      if ( v24 != 1 )
      {
        do
        {
          v36 = -1;
          if ( (v24 & 6) == 2 )
            v36 = 3;
          v37 = v36 + v24;
          v38 = v24;
          v24 = _InterlockedCompareExchange64((volatile signed __int64 *)v20, v36 + v24, v24);
        }
        while ( v38 != v24 );
        if ( v36 == 3 )
        {
          v39 = v19 + 16;
          while ( 1 )
          {
            while ( (v37 & 1) != 0 )
            {
              v56 = _InterlockedCompareExchange64((volatile signed __int64 *)v20, v37 - 4, v37);
              v43 = v37 == v56;
              v37 = v56;
              if ( v43 )
              {
                k = v65;
                goto LABEL_24;
              }
            }
            v40 = (_QWORD *)(v37 & 0xFFFFFFFFFFFFFFF0uLL);
            SchedulerSharedDataSlot = *(_QWORD *)((v37 & 0xFFFFFFFFFFFFFFF0uLL) + 8);
            if ( !SchedulerSharedDataSlot )
            {
              do
              {
                v41 = v40;
                v40 = (_QWORD *)*v40;
                v40[2] = v41;
                SchedulerSharedDataSlot = v40[1];
              }
              while ( !SchedulerSharedDataSlot );
              if ( v40 != (_QWORD *)(v37 & 0xFFFFFFFFFFFFFFF0uLL) )
                *(_QWORD *)((v37 & 0xFFFFFFFFFFFFFFF0uLL) + 8) = SchedulerSharedDataSlot;
            }
            if ( (*(_DWORD *)(SchedulerSharedDataSlot + 36) & 1) != 0 )
            {
              v42 = *(_QWORD *)(SchedulerSharedDataSlot + 16);
              if ( v42 )
                break;
            }
            v39 = 0;
            v44 = _InterlockedCompareExchange64((volatile signed __int64 *)v20, 0, v37);
            v43 = v37 == v44;
            v37 = v44;
            if ( v43 )
              goto LABEL_61;
          }
          *(_QWORD *)((v37 & 0xFFFFFFFFFFFFFFF0uLL) + 8) = v42;
          *(_QWORD *)(SchedulerSharedDataSlot + 16) = 0;
          _InterlockedAnd64((volatile signed __int64 *)v20, 0xFFFFFFFFFFFFFFFBuLL);
          do
          {
LABEL_61:
            v45 = *(_QWORD *)(SchedulerSharedDataSlot + 16);
            v46 = *(_QWORD *)(SchedulerSharedDataSlot + 24);
            _interlockedbittestandset((volatile signed __int32 *)(SchedulerSharedDataSlot + 36), 2u);
            if ( !_interlockedbittestandreset((volatile signed __int32 *)(SchedulerSharedDataSlot + 36), 1u) )
              ZwAlertThreadByThreadIdEx(v46, v39);
            SchedulerSharedDataSlot = v45;
          }
          while ( v45 );
          k = v65;
        }
      }
LABEL_24:
      i = (unsigned __int64)NtCurrentTeb()->SchedulerSharedDataSlot;
      if ( i )
      {
        v25 = (unsigned __int64)v20 & 0x7FFFFFFFFFFFFFFCLL;
        v26 = 0;
        SchedulerSharedDataSlot = 0x7FFFFFFFFFFFFFFCLL;
        while ( v26 < 8 )
        {
          v27 = (_BYTE *)(i + 8LL * v26);
          if ( (*(_QWORD *)v27 & 0x7FFFFFFFFFFFFFFCLL) == v25 )
          {
            *v27 |= 2u;
            if ( (char)v27[7] < 0 )
            {
              v80 = 0;
              *(_QWORD *)&v80 = (v27 - (char *)NtCurrentTeb()->SchedulerSharedDataSlot) >> 3;
              NtSetInformationThread(-2, 56, &v80, 16);
            }
            *(_QWORD *)v27 = 0;
            break;
          }
          ++v26;
        }
      }
      if ( v22 != v19 )
        break;
    }
    v16 = v6;
  }
  v28 = v69;
  *v68 = v22 - 16;
  v29 = *(unsigned int *)(v28 + 352);
  v30 = *(_BYTE *)(v22 - 16 + 12);
  v31 = *(unsigned __int16 *)(v28 + 362);
  v32 = *(_DWORD *)(a1 + 428);
  v65 = 0;
  v80 = 0;
  if ( v16 == (_DWORD)v29 )
  {
    if ( v32 == -1 && !*(_BYTE *)(v28 + 360) )
    {
      *(_BYTE *)(v28 + 360) = 1;
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 40) + 4LL * v16));
    }
  }
  else
  {
    if ( v32 == -1 )
    {
      if ( *(_BYTE *)(v28 + 360) )
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 40) + 4 * v29));
      else
        *(_BYTE *)(v28 + 360) = 1;
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 40) + 4LL * v16));
    }
    v57 = *(_QWORD *)(a1 + 48);
    v58 = TppMaximumGroups * v16;
    v59 = 1LL << v30;
    v60 = 2LL * (unsigned int)(v58 + v31);
    if ( ((1LL << v30) & *(_QWORD *)(v57 + 16LL * (unsigned int)(v58 + v31))) != 0 )
    {
      v62 = v31;
      v67 = (unsigned __int16)v31;
    }
    else
    {
      for ( i = 0; (unsigned __int16)i < (unsigned int)TppMaximumGroups; LOWORD(i) = i + 1 )
      {
        if ( (_WORD)i != (_WORD)v31 )
        {
          v61 = v58 + (unsigned __int16)i;
          v60 = 2LL * v61;
          if ( (v59 & *(_QWORD *)(v57 + 16LL * v61)) != 0 )
          {
            v62 = i;
            v67 = (unsigned __int16)i;
            goto LABEL_95;
          }
        }
      }
      v62 = -1;
    }
LABEL_95:
    *(_DWORD *)(v28 + 352) = v16;
    *(_WORD *)(v28 + 362) = v62;
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v60, i, v59, v58) )
      v63 = (__int64)NtCurrentPeb()->SharedData + 556;
    else
      v63 = 2147353478;
    if ( *(_BYTE *)v63 )
      TppETWWorkerNodeSwitch(a1, v29, v16, (unsigned __int16)v31, v67);
    v80 = 0;
    NtSetInformationThread(-2, 30, &v80, 16);
    v65 = (unsigned __int16)v67;
    BYTE2(v65) = v30;
    NtSetInformationThread(-2, 33, &v65, 4);
  }
  v33 = (int *)(v28 + 356);
  if ( v16 == v6 )
  {
    if ( (unsigned int)*v33 < 0x10 )
      v34 = *v33 + 1;
    else
      v34 = 16;
  }
  else
  {
    v34 = 0;
  }
  *v33 = v34;
  return 1;
}

```

## disassembly

```asm
0x180015d00  mov     [rsp-8+arg_18], rbx
0x180015d05  push    rbp
0x180015d06  push    rsi
0x180015d07  push    rdi
0x180015d08  push    r12
0x180015d0a  push    r13
0x180015d0c  push    r14
0x180015d0e  push    r15
0x180015d10  lea     rbp, [rsp-27h]
0x180015d15  sub     rsp, 0C0h
0x180015d1c  mov     rax, cs:__security_cookie
0x180015d23  xor     rax, rsp
0x180015d26  mov     [rbp+57h+var_40], rax
0x180015d2a  mov     rax, gs:30h
0x180015d33  mov     r13, rdx
0x180015d36  mov     [rbp+57h+var_B0], r8
0x180015d3a  mov     rbx, rcx
0x180015d3d  mov     [rbp+57h+var_A8], rdx
0x180015d41  movzx   r14d, byte ptr [rax+1746h]
0x180015d49  mov     rax, gs:30h
0x180015d52  mov     r15d, cs:TppNumberNodes
0x180015d59  movzx   esi, word ptr [rax+1744h]
0x180015d60  test    rcx, rcx
0x180015d63  jz      short loc_180015D6F
0x180015d65  mov     eax, [rcx+1B8h]
0x180015d6b  test    eax, eax
0x180015d6d  jnz     short loc_180015D76
0x180015d6f  mov     eax, ds:7FFE03C0h
0x180015d76  cmp     [rcx+1A8h], eax
0x180015d7c  jz      short loc_180015D98
0x180015d7e  add     rcx, 48h ; 'H'
0x180015d82  call    RtlAcquireSRWLockExclusive
0x180015d87  mov     rcx, rbx
0x180015d8a  call    TppAdjustRunningThreadGoalWithLock
0x180015d8f  lea     rcx, [rbx+48h]
0x180015d93  call    RtlReleaseSRWLockExclusive
0x180015d98  xor     r11d, r11d
0x180015d9b  mov     edx, r11d
0x180015d9e  cmp     edx, cs:TppNumberNodes
0x180015da4  jnb     loc_180016534
0x180015daa  mov     rax, [rbx+30h]
0x180015dae  mov     r9d, edx
0x180015db1  imul    r9d, cs:TppMaximumGroups
0x180015db9  add     r9d, esi
0x180015dbc  add     r9, r9
0x180015dbf  cmp     [rax+r9*8+8], si
0x180015dc5  jnz     loc_180016105
0x180015dcb  mov     ecx, r14d
0x180015dce  mov     r8d, 1
0x180015dd4  shl     r8, cl
0x180015dd7  test    [rax+r9*8], r8
0x180015ddb  jz      loc_180016105
0x180015de1  mov     r15d, edx
0x180015de4  mov     edi, [r13+160h]
0x180015deb  xorps   xmm0, xmm0
0x180015dee  movzx   esi, word ptr [r13+16Ah]
0x180015df6  mov     r9d, 0FFFFh
0x180015dfc  mov     eax, [rbx+1ACh]
0x180015e02  mov     [rbp+57h+var_BC], r11d
0x180015e06  mov     [rbp+57h+var_B8], r9d
0x180015e0a  movups  [rbp+57h+var_50], xmm0
0x180015e0e  cmp     r15d, edi
0x180015e11  jnz     loc_18001610C
0x180015e17  cmp     eax, 0FFFFFFFFh
0x180015e1a  jz      loc_1800163D6
0x180015e20  mov     eax, [rbx+1ACh]
0x180015e26  mov     r12d, r15d
0x180015e29  cmp     eax, 0FFFFFFFFh
0x180015e2c  jz      loc_180016507
0x180015e32  mov     r13d, r11d
0x180015e35  mov     [rbp+57h+var_C0], r13d
0x180015e39  mov     r9d, 3
0x180015e3f  mov     rdi, 7FFFFFFFFFFFFFFCh
0x180015e49  cmp     r13d, 2
0x180015e4d  jg      loc_18001600B
0x180015e53  mov     eax, r15d
0x180015e56  movsxd  rdx, r13d
0x180015e59  lea     rcx, [rax+rax*2]
0x180015e5d  mov     rax, [rbx+rdx*8+10h]
0x180015e62  lea     r12, [rax+rcx*8]
0x180015e66  mov     rax, gs:30h
0x180015e6f  lea     r14, [r12+10h]
0x180015e74  mov     r8, [rax+1850h]
0x180015e7b  test    r8, r8
0x180015e7e  jz      short loc_180015E8C
0x180015e80  mov     ecx, r11d
0x180015e83  cmp     ecx, 8
0x180015e86  jb      loc_180015FEF
0x180015e8c  lock bts qword ptr [r14], 0
0x180015e92  jb      loc_1800163C0
0x180015e98  mov     rsi, [r12]
0x180015e9c  cmp     [rsi+8], r12
0x180015ea0  jnz     loc_1800163BB
0x180015ea6  mov     rax, [rsi]
0x180015ea9  cmp     [rax+8], rsi
0x180015ead  jnz     loc_1800163BB
0x180015eb3  mov     [r12], rax
0x180015eb7  mov     rcx, r11
0x180015eba  mov     [rax+8], r12
0x180015ebe  mov     eax, 1
0x180015ec3  lock cmpxchg [r14], rcx
0x180015ec8  jnz     loc_180016030
0x180015ece  mov     rax, gs:30h
0x180015ed7  mov     rdx, [rax+1850h]
0x180015ede  test    rdx, rdx
0x180015ee1  jz      short loc_180015F5B
0x180015ee3  and     r14, rdi
0x180015ee6  mov     ecx, r11d
0x180015ee9  mov     r8, 7FFFFFFFFFFFFFFCh
0x180015ef3  cmp     ecx, 8
0x180015ef6  jnb     short loc_180015F5B
0x180015ef8  mov     eax, ecx
0x180015efa  lea     rdi, [rdx+rax*8]
0x180015efe  mov     rax, [rdx+rax*8]
0x180015f02  and     rax, r8
0x180015f05  cmp     rax, r14
0x180015f08  jz      short loc_180015F0E
0x180015f0a  inc     ecx
0x180015f0c  jmp     short loc_180015EF3
0x180015f0e  or      byte ptr [rdi], 2
0x180015f11  nop
0x180015f12  cmp     byte ptr [rdi+7], 0
0x180015f16  jge     short loc_180015F58
0x180015f18  xorps   xmm0, xmm0
0x180015f1b  lea     r8, [rbp+57h+var_60]
0x180015f1f  movups  [rbp+57h+var_60], xmm0
0x180015f23  mov     rax, gs:30h
0x180015f2c  mov     rcx, rdi
0x180015f2f  mov     r9d, 10h
0x180015f35  mov     edx, 38h ; '8'
0x180015f3a  sub     rcx, [rax+1850h]
0x180015f41  sar     rcx, 3
0x180015f45  mov     qword ptr [rbp+57h+var_60], rcx
0x180015f49  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180015f50  call    NtSetInformationThread
0x180015f55  xor     r11d, r11d
0x180015f58  mov     [rdi], r11
0x180015f5b  cmp     rsi, r12
0x180015f5e  jz      loc_180016003
0x180015f64  mov     r12d, r15d
0x180015f67  mov     r13, [rbp+57h+var_A8]
0x180015f6b  lea     rax, [rsi-10h]
0x180015f6f  mov     rcx, [rbp+57h+var_B0]
0x180015f73  xorps   xmm0, xmm0
0x180015f76  mov     [rcx], rax
0x180015f79  mov     edi, [r13+160h]
0x180015f80  movzx   r14d, byte ptr [rax+0Ch]
0x180015f85  movzx   esi, word ptr [r13+16Ah]
0x180015f8d  mov     eax, [rbx+1ACh]
0x180015f93  mov     [rbp+57h+var_C0], r11d
0x180015f97  movups  [rbp+57h+var_60], xmm0
0x180015f9b  cmp     r12d, edi
0x180015f9e  jnz     loc_18001629E
0x180015fa4  cmp     eax, 0FFFFFFFFh
0x180015fa7  jz      loc_180016455
0x180015fad  lea     rax, [r13+164h]
0x180015fb4  cmp     r12d, r15d
0x180015fb7  jz      loc_1800163FB
0x180015fbd  mov     ecx, r11d
0x180015fc0  mov     [rax], ecx
0x180015fc2  mov     eax, 1
0x180015fc7  mov     rcx, [rbp+57h+var_40]
0x180015fcb  xor     rcx, rsp; StackCookie
0x180015fce  call    __security_check_cookie
0x180015fd3  mov     rbx, [rsp+0F0h+arg_18]
0x180015fdb  add     rsp, 0C0h
0x180015fe2  pop     r15
0x180015fe4  pop     r14
0x180015fe6  pop     r13
0x180015fe8  pop     r12
0x180015fea  pop     rdi
0x180015feb  pop     rsi
0x180015fec  pop     rbp
0x180015fed  retn
0x180015fef  mov     eax, ecx
0x180015ff1  cmp     qword ptr [r8+rax*8], 0
0x180015ff6  lea     rdx, [r8+rax*8]
0x180015ffa  jz      short loc_18001601F
0x180015ffc  inc     ecx
0x180015ffe  jmp     loc_180015E83
0x180016003  inc     r13d
0x180016006  jmp     loc_180015E35
0x18001600b  mov     r12d, r15d
0x18001600e  cmp     byte ptr [rbx+179h], 0
0x180016015  jz      loc_1800164B6
0x18001601b  xor     eax, eax
0x18001601d  jmp     short loc_180015FC7
0x18001601f  mov     [rdx], r14
0x180016022  jmp     loc_180015E8C
0x180016030  movzx   ecx, al
0x180016033  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18001603a  and     cl, 6
0x18001603d  cmp     cl, 2
0x180016040  cmovz   rdx, r9
0x180016044  lea     rcx, [rdx+rax]
0x180016048  lock cmpxchg [r14], rcx
0x18001604d  jnz     short loc_180016030
0x18001604f  cmp     rdx, 3
0x180016053  jnz     loc_180015ECE
0x180016059  mov     r13, r14
0x18001605c  test    cl, 1
0x18001605f  jnz     loc_180016280
0x180016065  mov     r9, rcx
0x180016068  and     r9, 0FFFFFFFFFFFFFFF0h
0x18001606c  mov     rdx, r9
0x18001606f  mov     r8, [r9+8]
0x180016073  test    r8, r8
0x180016076  jnz     short loc_180016094
0x180016078  mov     rax, rdx
0x18001607b  mov     rdx, [rdx]
0x18001607e  mov     [rdx+10h], rax
0x180016082  mov     r8, [rdx+8]
0x180016086  test    r8, r8
0x180016089  jz      short loc_180016078
0x18001608b  cmp     rdx, r9
0x18001608e  jz      short loc_180016094
0x180016090  mov     [r9+8], r8
0x180016094  mov     eax, [r8+24h]
0x180016098  test    al, 1
0x18001609a  jz      short loc_1800160A5
0x18001609c  mov     rax, [r8+10h]
0x1800160a0  test    rax, rax
0x1800160a3  jnz     short loc_1800160BA
0x1800160a5  mov     r13, r11
0x1800160a8  mov     rdx, r11
0x1800160ab  mov     rax, rcx
0x1800160ae  lock cmpxchg [r14], rdx
0x1800160b3  mov     rcx, rax
0x1800160b6  jnz     short loc_18001605C
0x1800160b8  jmp     short loc_1800160C7
0x1800160ba  mov     [r9+8], rax
0x1800160be  mov     [r8+10h], r11
0x1800160c2  lock and qword ptr [r14], 0FFFFFFFFFFFFFFFBh
0x1800160c7  mov     rdi, [r8+10h]
0x1800160cb  mov     rcx, [r8+18h]
0x1800160cf  lock bts dword ptr [r8+24h], 2
0x1800160d6  lock btr dword ptr [r8+24h], 1
0x1800160dd  jb      short loc_1800160E7
0x1800160df  mov     rdx, r13
0x1800160e2  call    ZwAlertThreadByThreadIdEx
0x1800160e7  mov     r8, rdi
0x1800160ea  test    rdi, rdi
0x1800160ed  jnz     short loc_1800160C7
0x1800160ef  mov     r13d, [rbp+57h+var_C0]
0x1800160f3  xor     r11d, r11d
0x1800160f6  mov     rdi, 7FFFFFFFFFFFFFFCh
0x180016100  jmp     loc_180015ECE
0x180016105  inc     edx
0x180016107  jmp     loc_180015D9E
0x18001610c  cmp     eax, 0FFFFFFFFh
0x18001610f  jnz     short loc_180016131
0x180016111  cmp     [r13+168h], r11b
0x180016118  jz      loc_18001643E
0x18001611e  mov     rax, [rbx+28h]
0x180016122  lock dec dword ptr [rax+rdi*4]
0x180016126  mov     rax, [rbx+28h]
0x18001612a  mov     ecx, r15d
0x18001612d  lock inc dword ptr [rax+rcx*4]
0x180016131  mov     r10d, cs:TppMaximumGroups
0x180016138  mov     edx, r15d
0x18001613b  mov     r11, [rbx+30h]
0x18001613f  imul    edx, r10d
0x180016143  lea     ecx, [rdx+rsi]
0x180016146  add     rcx, rcx
0x180016149  test    [r11+rcx*8], r8
0x18001614d  jnz     loc_180016419
0x180016153  mov     r12d, r9d
0x180016156  xor     r9d, r9d
0x180016159  movzx   eax, r9w
0x18001615d  cmp     eax, r10d
0x180016160  jnb     short loc_180016180
0x180016162  cmp     r9w, si
0x180016166  jz      loc_180016410
0x18001616c  lea     ecx, [rdx+rax]
0x18001616f  add     rcx, rcx
0x180016172  test    [r11+rcx*8], r8
0x180016176  jz      loc_180016410
0x18001617c  movzx   r12d, r9w
0x180016180  mov     [r13+160h], r15d
0x180016187  mov     [r13+16Ah], r12w
0x18001618f  call    RtlGetCurrentServiceSessionId
0x180016194  test    eax, eax
0x180016196  jnz     loc_180016422
0x18001619c  mov     ecx, 7FFE0386h
0x1800161a1  cmp     byte ptr [rcx], 0
0x1800161a4  jz      loc_18001622B
0x1800161aa  mov     rdx, [rbx+28h]
0x1800161ae  xor     ecx, ecx
0x1800161b0  mov     [rbp+57h+var_6C], rcx
0x1800161b4  xorps   xmm0, xmm0
0x1800161b7  mov     [rbp+57h+var_A0], ecx
0x1800161ba  mov     [rbp+57h+var_9C], 1C290000h
0x1800161c1  mov     [rbp+57h+var_98], rcx
0x1800161c5  movdqa  [rbp+57h+var_90], xmm0
0x1800161ca  mov     [rbp+57h+var_64], ecx
0x1800161cd  mov     [rbp+57h+var_80], rbx
0x1800161d1  mov     [rbp+57h+var_78], edi
0x1800161d4  mov     [rbp+57h+var_74], r15d
0x1800161d8  mov     [rbp+57h+var_70], si
0x1800161dc  mov     [rbp+57h+var_6E], r12w
  ... truncated ...
```
