# EtwpWriteToPrivateBuffers

- ea: `0x1800866c0`
- end: `0x1800870fa`
- name: `EtwpWriteToPrivateBuffers`
- size: `2618`
- prototype: `__int64 __fastcall(_BYTE *, _OWORD *, __int16, unsigned __int16, __int16, _GUID *, _OWORD *, unsigned int, __int64, __int64)`
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x1800850d0`
- `0x180085cc0`
- `0x180085fe0`
- `0x180086330`

## callees

- `0x180013cb0`
- `0x180013d70`
- `0x1800866c0`
- `0x180087100`
- `0x1800871e0`
- `0x180087bc0`
- `0x180087e20`
- `0x180139f68`
- `0x18015e6f0`
- `0x180162000`
- `0x180163a80`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall EtwpWriteToPrivateBuffers(
        _BYTE *a1,
        _OWORD *a2,
        __int16 a3,
        unsigned __int16 a4,
        __int16 a5,
        _GUID *a6,
        _OWORD *a7,
        unsigned int a8,
        __int64 a9,
        __int64 a10)
{
  _OWORD *v10; // r14
  _BYTE *v11; // rdi
  unsigned int v12; // r13d
  unsigned int v13; // edx
  unsigned int i; // esi
  __int64 SystemTimePrecise; // rbx
  int v16; // eax
  _BYTE *v17; // rdi
  unsigned __int8 v18; // al
  __int64 v19; // rdx
  __int64 v20; // r15
  unsigned int v21; // eax
  __int64 v22; // rcx
  unsigned __int16 v23; // r11
  int v24; // r10d
  int v25; // r14d
  unsigned int v26; // esi
  int v27; // ecx
  unsigned int j; // ecx
  unsigned int v29; // r9d
  __int64 v30; // rdx
  char v31; // al
  int v32; // edx
  _DWORD *v33; // r10
  __int64 v34; // r8
  unsigned int Reserved; // r15d
  _DWORD *v36; // r9
  unsigned int v37; // r13d
  unsigned int v38; // edx
  unsigned int v39; // ecx
  unsigned __int16 *v40; // rax
  __int64 v41; // r14
  unsigned __int32 v42; // edi
  void *v43; // rcx
  unsigned int v44; // r15d
  __int64 v45; // r8
  unsigned int v46; // r14d
  struct _TEB *v47; // rcx
  __int64 v48; // rdi
  _WORD *v49; // r13
  _GUID ActivityId; // xmm0
  void *v51; // rdx
  unsigned __int16 *v52; // r13
  int v53; // edx
  __int64 *v54; // r9
  int v55; // ecx
  int v56; // ecx
  unsigned __int16 *v58; // rax
  unsigned __int16 v59; // r8
  unsigned __int16 v60; // r15
  unsigned __int16 *v61; // r14
  __int64 v62; // rsi
  unsigned __int16 *v63; // rcx
  __int64 v64; // rdx
  unsigned __int16 v65; // cx
  unsigned __int16 *v66; // rsi
  void *v67; // rsp
  __int16 v68; // bx
  int InformationToken; // eax
  size_t v70; // rsi
  _WORD *v71; // rsi
  unsigned __int16 v72; // r14
  _DWORD *v73; // rdx
  void *v74; // rsi
  unsigned __int16 v75; // r14
  char v76; // al
  __int16 v77; // [rsp+0h] [rbp-810h] BYREF
  int v78; // [rsp+2h] [rbp-80Eh]
  __int16 v79; // [rsp+6h] [rbp-80Ah]
  __int64 v80; // [rsp+8h] [rbp-808h]
  __int64 v81; // [rsp+10h] [rbp-800h] BYREF
  unsigned __int16 v82; // [rsp+810h] [rbp+0h]
  unsigned int v83; // [rsp+814h] [rbp+4h]
  char v84; // [rsp+818h] [rbp+8h]
  char v85; // [rsp+819h] [rbp+9h]
  char v86; // [rsp+81Ah] [rbp+Ah]
  int v87; // [rsp+81Ch] [rbp+Ch]
  int v88; // [rsp+820h] [rbp+10h] BYREF
  _DWORD Size[3]; // [rsp+824h] [rbp+14h] BYREF
  __int64 v90; // [rsp+830h] [rbp+20h]
  int v91; // [rsp+838h] [rbp+28h]
  _DWORD *v92; // [rsp+840h] [rbp+30h]
  int v93; // [rsp+848h] [rbp+38h]
  unsigned int v94; // [rsp+84Ch] [rbp+3Ch]
  void *v95; // [rsp+850h] [rbp+40h]
  unsigned __int16 *v96; // [rsp+858h] [rbp+48h]
  __int64 v97; // [rsp+860h] [rbp+50h]
  void *Src; // [rsp+868h] [rbp+58h]
  int v99; // [rsp+870h] [rbp+60h]
  unsigned int *v100; // [rsp+878h] [rbp+68h]
  unsigned __int16 *k; // [rsp+880h] [rbp+70h]
  __int64 v102; // [rsp+890h] [rbp+80h]
  _QWORD v103[2]; // [rsp+8A0h] [rbp+90h] BYREF
  _BYTE v104[16]; // [rsp+8B0h] [rbp+A0h] BYREF
  char v105[80]; // [rsp+8C0h] [rbp+B0h] BYREF

  v10 = a2;
  v11 = a1;
  *(_QWORD *)&Size[1] = a1;
  Src = a1;
  v90 = a9;
  v102 = a10;
  v100 = (unsigned int *)(a10 + 128);
  *(_DWORD *)(a10 + 128) = 0;
  v12 = a8;
  if ( a8 > 0x80 )
    return 87;
  v95 = 0;
  v97 = 0;
  v82 = 0;
  if ( (a1[232] & 4) != 0 && (unsigned __int8)EtwpCheckForEnoughStackSpace() )
  {
    v67 = alloca(2064);
    v95 = &v77;
    v103[1] = &v77;
    v68 = 8 * RtlWalkFrameChain(&v81, 256, 0);
    if ( v68 )
    {
      v97 = (unsigned __int16)(v68 + 23) & 0xFFF8;
      memset_thunk_772440563353939046(
        (char *)&v77 + (unsigned __int16)(v68 + 16),
        0,
        v97 - (unsigned __int16)(v68 + 16));
      v80 = 0;
      v77 = (v68 + 23) & 0xFFF8;
      v78 = 6;
      v79 = v68;
    }
    else
    {
      v95 = 0;
    }
  }
  v13 = 0;
  v83 = 0;
  LOWORD(v91) = 0;
  Src = 0;
  for ( i = 0; ; ++i )
  {
    while ( 1 )
    {
      v94 = i;
      if ( i >= 4 )
        return v13;
      SystemTimePrecise = 0;
      v103[0] = 0;
      Size[0] = 0;
      memset_thunk_772440563353939046(v104, 0, 0x58u);
      v16 = a4;
      if ( !_bittest(&v16, i) )
        break;
      v13 = v83;
      ++i;
    }
    v17 = &v11[24 * i + 120];
    if ( v17[20] )
    {
      v18 = v17[21];
      if ( *((_BYTE *)v10 + 4) <= v18 || !v18 )
      {
        v19 = *((_QWORD *)v10 + 1);
        if ( (v17[16] & 0x40) != 0 && !v19 )
          break;
        if ( (v19 & *((_QWORD *)v17 + 1)) != 0 && (v19 & *(_QWORD *)v17) == *(_QWORD *)v17 )
          break;
      }
    }
LABEL_63:
    v13 = v83;
LABEL_64:
    v11 = *(_BYTE **)&Size[1];
  }
  v92 = 0;
  v20 = (unsigned __int8)v17[22];
  v99 = v20;
  v21 = v20;
  v88 = v20;
  if ( !EtwpLoggerArray )
    goto LABEL_16;
  if ( (unsigned int)v20 < 0x40 )
  {
LABEL_14:
    v22 = 16LL * v21;
    _InterlockedIncrement((volatile signed __int32 *)(v22 + EtwpLoggerArray + 8));
    if ( (*(_QWORD *)(v22 + EtwpLoggerArray) & 1) == 0 )
    {
      v92 = *(_DWORD **)(v22 + EtwpLoggerArray);
      v13 = 0;
      goto LABEL_17;
    }
    _InterlockedDecrement((volatile signed __int32 *)(v22 + EtwpLoggerArray + 8));
LABEL_16:
    v13 = 4201;
LABEL_17:
    v83 = v13;
    goto LABEL_18;
  }
  v13 = EtwpDemuxUmTraceHandle((unsigned int)v20, &v88);
  v83 = v13;
  if ( !v13 )
  {
    v21 = v88;
    goto LABEL_14;
  }
LABEL_18:
  if ( v13 )
    goto LABEL_64;
  v85 = 0;
  v84 = 0;
  v86 = 0;
  LOWORD(v93) = 0;
  v23 = 0;
  v82 = 0;
  v24 = 0;
  v88 = 0;
  v25 = 104;
  if ( !a7 )
    v25 = 80;
  if ( (v17[16] & 1) != 0
    && (InformationToken = NtQueryInformationToken(-6, 1, v104, 88, Size), v24 = 0, v23 = 0, InformationToken >= 0) )
  {
    Size[0] -= 16;
    v93 = (LOWORD(Size[0]) + 15) & 0xFFF8;
    v84 = 1;
    v26 = v25 + v93;
  }
  else
  {
    v26 = v25;
  }
  v27 = *((_DWORD *)v17 + 4);
  if ( (v27 & 4) != 0 && v95 )
  {
    v86 = 1;
    v26 += (unsigned __int16)v97;
  }
  if ( (v27 & 2) != 0 )
  {
    v85 = 1;
    v26 += 16;
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= v12 )
    {
      v32 = v83;
      goto LABEL_35;
    }
    v29 = v26;
    v30 = 16LL * j;
    v31 = (*(_WORD *)(*(_QWORD *)&Size[1] + 86LL) & 0x4000) != 0 ? *(_BYTE *)(v90 + v30 + 12) : 0;
    if ( v31 )
    {
      if ( v31 == 1 )
      {
        v23 += *(_WORD *)(v90 + v30 + 8);
        v82 = v23;
        v88 = ++v24;
      }
      else if ( v31 == 2 )
      {
        Src = *(void **)(v90 + 16LL * j);
        v91 = *(unsigned __int16 *)(v90 + v30 + 8);
        v26 += (v91 + 15) & 0xFFFFFFF8;
      }
    }
    else
    {
      v26 += *(_DWORD *)(v90 + v30 + 8);
    }
    if ( v26 < v29 )
      break;
  }
  v32 = 534;
  v83 = 534;
LABEL_35:
  if ( v24 )
    v26 += (v23 + 15) & 0xFFFFFFF8;
  if ( v32 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(16 * v20 + EtwpLoggerArray + 8));
    return v83;
  }
  v33 = v100;
  v34 = v102 + 32LL * *v100;
  v96 = (unsigned __int16 *)v34;
  *(_DWORD *)(v34 + 24) = v26;
  Reserved = NtCurrentTeb()->CurrentIdealProcessor.Reserved;
  v36 = v92;
  if ( v26 <= v92[49] )
  {
    v37 = (v26 + 7) & 0xFFFFFFF8;
    v38 = v92[48];
    v87 = v38;
    v39 = v92[47];
    if ( Reserved >= v39 )
    {
      Reserved %= v39;
      v38 = v87;
    }
    v40 = (unsigned __int16 *)&v92[2 * Reserved + 140];
    for ( k = v40; ; v40 = k )
    {
      v41 = *(_QWORD *)v40;
      if ( *(_QWORD *)v40 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v41 + 12));
        if ( *(_DWORD *)(v41 + 44) == 1 && *(_DWORD *)(v41 + 8) <= v38 )
        {
          v42 = _InterlockedExchangeAdd((volatile signed __int32 *)(v41 + 8), v37);
          if ( v42 + v37 <= v38 )
          {
            if ( v36[4] == 2 )
            {
              SystemTimePrecise = RtlGetSystemTimePrecise();
LABEL_66:
              v36 = v92;
            }
            else
            {
              if ( v36[4] != 3 )
              {
                RtlQueryPerformanceCounter(v103);
                SystemTimePrecise = v103[0];
                goto LABEL_66;
              }
              SystemTimePrecise = __rdtsc();
            }
            v48 = v41 + v42;
            v34 = (__int64)v96;
            v33 = v100;
            goto LABEL_68;
          }
          if ( v42 <= v38 )
            *(_DWORD *)(v41 + 4) = v42;
        }
      }
      v76 = EtwpSwitchBuffer(v36, v41, Reserved);
      v36 = v92;
      if ( v76 != 1 )
      {
        v34 = (__int64)v96;
        v33 = v100;
        break;
      }
      v38 = v87;
    }
  }
  v41 = 0;
  _InterlockedIncrement(v36 + 92);
  if ( (v36[77] & 0x10000) != 0 )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v36 + 62)
                                                    + 12LL
                                                    * *(unsigned __int16 *)(*((_QWORD *)v36 + 67) + 4LL * Reserved)
                                                    + 4));
  v48 = 0;
LABEL_68:
  if ( v48 )
  {
    v49 = 0;
    v44 = 80;
    v87 = 80;
    v96 = 0;
    *(_QWORD *)v34 = v36;
    *(_QWORD *)(v34 + 8) = v48;
    *(_QWORD *)(v34 + 16) = v41;
    ++*v33;
    *(_DWORD *)v48 = v26 | 0xC0130000;
    *(_WORD *)(v48 + 4) = a5;
    *(_WORD *)(v48 + 6) = a3;
    *(_OWORD *)(v48 + 24) = *(_OWORD *)(*(_QWORD *)&Size[1] + 32LL);
    *(_OWORD *)(v48 + 40) = *a2;
    if ( a6 )
      ActivityId = *a6;
    else
      ActivityId = NtCurrentTeb()->ActivityId;
    *(_GUID *)(v48 + 64) = ActivityId;
    if ( a7 )
    {
      v49 = (_WORD *)(v48 + 80);
      *(_WORD *)(v48 + 80) = 24;
      *(_DWORD *)(v48 + 82) = 1;
      *(_WORD *)(v48 + 86) = 16;
      *(_OWORD *)(v48 + 88) = *a7;
      *(_WORD *)(v48 + 4) = a5 | 1;
      v44 = 104;
      v87 = 104;
    }
    if ( v84 == 1 )
    {
      v71 = (_WORD *)(v48 + v44);
      v72 = v93;
      *v71 = v93;
      v71[1] = 2;
      v71[3] = Size[0];
      v71[2] = 0;
      memmove(v71 + 4, v105, Size[0]);
      *(_WORD *)(v48 + 4) |= 1u;
      v44 += v72;
      v87 = v44;
      if ( v49 )
        v49[2] |= 1u;
      v49 = v71;
    }
    if ( v85 == 1 )
    {
      v73 = (_DWORD *)(v48 + v44);
      *v73 = 196624;
      v73[1] = 0x40000;
      v73[2] = NtCurrentPeb()->SessionId;
      *(_WORD *)(v48 + 4) |= 1u;
      v44 += 16;
      v87 = v44;
      if ( v49 )
        v49[2] |= 1u;
      v49 = v73;
    }
    if ( v86 == 1 )
    {
      v74 = (void *)(v48 + v44);
      v75 = v97;
      memmove(v74, v95, (unsigned __int16)v97);
      *(_WORD *)(v48 + 4) |= 1u;
      v44 += v75;
      v87 = v44;
      if ( v49 )
        v49[2] |= 1u;
      v49 = v74;
    }
    v51 = Src;
    if ( Src )
    {
      v58 = (unsigned __int16 *)(v48 + v44);
      k = v58;
      v59 = v91;
      v60 = (v91 + 15) & 0xFFF8;
      *v58 = v60;
      *(_DWORD *)(v58 + 1) = 12;
      v58[3] = v59;
      v61 = v58 + 4;
      v62 = v59;
      memmove(v58 + 4, v51, v59);
      memset_thunk_772440563353939046((char *)v61 + v62, 0, (unsigned __int16)(v60 - v91 - 8));
      *(_WORD *)(v48 + 4) |= 1u;
      v63 = k;
      v44 = *k + v87;
      if ( v49 )
        v49[2] |= 1u;
      v49 = v63;
    }
    if ( v88 )
    {
      v64 = v82;
      v65 = (v82 + 15) & 0xFFF8;
      v66 = (unsigned __int16 *)(v48 + v44);
      *v66 = v65;
      *(_DWORD *)(v66 + 1) = 11;
      v66[3] = v64;
      v96 = v66 + 4;
      memset_thunk_772440563353939046((char *)v66 + v64 + 8, 0, (unsigned __int16)(v65 - v64 - 8));
      *(_WORD *)(v48 + 4) |= 1u;
      v44 += *v66;
      if ( v49 )
        v49[2] |= 1u;
    }
    v46 = 0;
    v12 = a8;
    if ( a8 )
    {
      v52 = v96;
      v45 = v90;
      while ( 1 )
      {
        v53 = *(_DWORD *)(v45 + 16LL * v46 + 8);
        v54 = *(__int64 **)(v45 + 16LL * v46);
        if ( (*(_WORD *)(*(_QWORD *)&Size[1] + 86LL) & 0x4000) != 0
          && (v55 = *(unsigned __int8 *)(v45 + 16LL * v46 + 12), (_BYTE)v55) )
        {
          v56 = v55 - 1;
          if ( v56 )
          {
            if ( v56 == 2 && v53 == 8 )
              SystemTimePrecise = *v54;
            goto LABEL_58;
          }
          v70 = *(unsigned int *)(v45 + 16LL * v46 + 8);
          memmove(v52, v54, v70);
          v52 = (unsigned __int16 *)((char *)v52 + v70);
        }
        else
        {
          v43 = (void *)(v48 + v44);
          v44 += v53;
          memmove(v43, v54, *(unsigned int *)(v45 + 16LL * v46 + 8));
        }
        v45 = v90;
LABEL_58:
        if ( ++v46 >= a8 )
        {
          v12 = a8;
          break;
        }
      }
    }
    *(_QWORD *)(v48 + 16) = SystemTimePrecise;
    if ( v92[4] == 3 )
      *(_QWORD *)(v48 + 56) = SystemTimePrecise;
    else
      *(_QWORD *)(v48 + 56) = __rdtsc();
    v47 = NtCurrentTeb();
    *(_DWORD *)(v48 + 8) = v47->ClientId.UniqueThread;
    *(_DWORD *)(v48 + 12) = v47->ClientId.UniqueProcess;
    i = v94;
    v10 = a2;
    goto LABEL_63;
  }
  if ( v26 > 0xFFF8 )
  {
    v13 = 534;
  }
  else
  {
    v13 = 8;
    if ( v26 > v36[49] )
      v13 = 234;
  }
  _InterlockedDecrement((volatile signed __int32 *)(16LL * (unsigned __int8)v99 + EtwpLoggerArray + 8));
  return v13;
}

```

## disassembly

```asm
0x1800866c0  mov     [rsp-8+arg_18], r9w
0x1800866c6  mov     [rsp-8+arg_10], r8w
0x1800866cc  mov     [rsp-8+arg_8], rdx
0x1800866d1  push    rbp
0x1800866d2  push    rbx
0x1800866d3  push    rsi
0x1800866d4  push    rdi
0x1800866d5  push    r12
0x1800866d7  push    r13
0x1800866d9  push    r14
0x1800866db  push    r15
0x1800866dd  sub     rsp, 148h
0x1800866e4  lea     rbp, [rsp+30h]
0x1800866e9  mov     rax, cs:__security_cookie
0x1800866f0  xor     rax, rbp
0x1800866f3  mov     [rbp+150h+var_50], rax
0x1800866fa  mov     r14, rdx
0x1800866fd  mov     rdi, rcx
0x180086700  mov     qword ptr [rbp+150h+Size+4], rcx
0x180086704  mov     [rbp+150h+Src], rcx
0x180086708  mov     rbx, [rbp+150h+arg_40]
0x18008670f  mov     [rbp+150h+var_130], rbx
0x180086713  mov     rbx, [rbp+150h+arg_48]
0x18008671a  mov     [rbp+150h+var_D0], rbx
0x180086721  lea     rax, [rbx+80h]
0x180086728  mov     [rbp+150h+var_E8], rax
0x18008672c  xor     r12d, r12d
0x18008672f  mov     [rax], r12d
0x180086732  mov     r13d, [rbp+150h+arg_38]
0x180086739  cmp     r13d, 80h
0x180086740  ja      loc_180086E7A
0x180086746  mov     [rbp+150h+var_110], r12
0x18008674a  movzx   r15d, r12w
0x18008674e  mov     [rbp+150h+var_100], r15
0x180086752  mov     [rbp+150h+var_150], r12w
0x180086757  test    byte ptr [rcx+0E8h], 4
0x18008675e  jnz     loc_180086DED
0x180086764  mov     edx, r12d
0x180086767  mov     [rbp+150h+var_14C], edx
0x18008676a  mov     word ptr [rbp+150h+var_128], r12w
0x18008676f  mov     [rbp+150h+Src], r12
0x180086773  mov     esi, r12d
0x180086776  mov     [rbp+150h+var_114], esi
0x180086779  cmp     esi, 4
0x18008677c  jnb     loc_180086CB7
0x180086782  mov     rbx, r12
0x180086785  mov     [rbp+150h+var_C0], rbx
0x18008678c  mov     dword ptr [rbp+150h+Size], r12d
0x180086790  xor     edx, edx; Val
0x180086792  mov     r8d, 58h ; 'X'; Size
0x180086798  lea     rcx, [rbp+150h+var_B0]; void *
0x18008679f  call    memset$thunk$772440563353939046
0x1800867a4  movzx   eax, [rbp+150h+arg_18]
0x1800867ab  bt      eax, esi
0x1800867ae  jb      loc_180086A70
0x1800867b4  mov     eax, esi
0x1800867b6  add     rax, 5
0x1800867ba  lea     rax, [rax+rax*2]
0x1800867be  lea     rdi, [rdi+rax*8]
0x1800867c2  cmp     byte ptr [rdi+14h], 0
0x1800867c6  jz      loc_180086AEC
0x1800867cc  movzx   eax, byte ptr [rdi+15h]
0x1800867d0  cmp     [r14+4], al
0x1800867d4  ja      loc_1800870E4
0x1800867da  mov     rdx, [r14+8]
0x1800867de  test    byte ptr [rdi+10h], 40h
0x1800867e2  jz      short loc_1800867E9
0x1800867e4  test    rdx, rdx
0x1800867e7  jz      short loc_180086802
0x1800867e9  test    [rdi+8], rdx
0x1800867ed  jz      loc_180086AEC
0x1800867f3  mov     rax, [rdi]
0x1800867f6  and     rax, rdx
0x1800867f9  cmp     rax, [rdi]
0x1800867fc  jnz     loc_180086AEC
0x180086802  mov     [rbp+150h+var_120], r12
0x180086806  movzx   r15d, byte ptr [rdi+16h]
0x18008680b  mov     [rbp+150h+var_F0], r15d
0x18008680f  mov     eax, r15d
0x180086812  mov     [rbp+150h+var_140], eax
0x180086815  cmp     cs:EtwpLoggerArray, 0
0x18008681d  jz      short loc_18008685B
0x18008681f  cmp     r15d, 40h ; '@'
0x180086823  jnb     loc_180086FF7
0x180086829  mov     ecx, eax
0x18008682b  shl     rcx, 4
0x18008682f  mov     rax, cs:EtwpLoggerArray
0x180086836  lock inc dword ptr [rcx+rax+8]
0x18008683b  mov     rax, cs:EtwpLoggerArray
0x180086842  mov     rdx, [rcx+rax]
0x180086846  test    dl, 1
0x180086849  jz      loc_180086A57
0x18008684f  mov     rax, cs:EtwpLoggerArray
0x180086856  lock dec dword ptr [rcx+rax+8]
0x18008685b  mov     edx, 1069h
0x180086860  mov     [rbp+150h+var_14C], edx
0x180086863  test    edx, edx
0x180086865  jnz     loc_180086AEF
0x18008686b  mov     [rbp+150h+var_147], dl
0x18008686e  mov     [rbp+150h+var_148], dl
0x180086871  mov     [rbp+150h+var_146], dl
0x180086874  mov     word ptr [rbp+150h+var_118], r12w
0x180086879  movzx   r11d, r12w
0x18008687d  mov     [rbp+150h+var_150], r12w
0x180086882  mov     r10d, r12d
0x180086885  mov     [rbp+150h+var_140], r12d
0x180086889  mov     r14d, 68h ; 'h'
0x18008688f  cmp     [rbp+150h+arg_30], 0
0x180086897  mov     eax, 50h ; 'P'
0x18008689c  cmovz   r14d, eax
0x1800868a0  test    byte ptr [rdi+10h], 1
0x1800868a4  jnz     loc_180086E84
0x1800868aa  mov     esi, r14d
0x1800868ad  mov     ecx, [rdi+10h]
0x1800868b0  test    cl, 4
0x1800868b3  jnz     loc_180086EE2
0x1800868b9  test    cl, 2
0x1800868bc  jnz     loc_180086A04
0x1800868c2  mov     ecx, r12d
0x1800868c5  cmp     ecx, r13d
0x1800868c8  jnb     short loc_180086907
0x1800868ca  mov     r9d, esi
0x1800868cd  mov     edx, ecx
0x1800868cf  shl     rdx, 4
0x1800868d3  mov     rax, qword ptr [rbp+150h+Size+4]
0x1800868d7  mov     r8d, 4000h
0x1800868dd  test    [rax+56h], r8w
0x1800868e2  jnz     loc_180086A10
0x1800868e8  xor     al, al
0x1800868ea  test    al, al
0x1800868ec  jnz     loc_180086A1E
0x1800868f2  mov     rax, [rbp+150h+var_130]
0x1800868f6  add     esi, [rax+rdx+8]
0x1800868fa  cmp     esi, r9d
0x1800868fd  jb      loc_180086A63
0x180086903  inc     ecx
0x180086905  jmp     short loc_1800868C5
0x180086907  mov     edx, [rbp+150h+var_14C]
0x18008690a  test    r10d, r10d
0x18008690d  jz      short loc_18008691B
0x18008690f  movzx   eax, r11w
0x180086913  add     eax, 0Fh
0x180086916  and     eax, 0FFFFFFF8h
0x180086919  add     esi, eax
0x18008691b  test    edx, edx
0x18008691d  jnz     loc_180086CDD
0x180086923  mov     r10, [rbp+150h+var_E8]
0x180086927  mov     r8d, [r10]
0x18008692a  shl     r8, 5
0x18008692e  add     r8, [rbp+150h+var_D0]
0x180086935  mov     [rbp+150h+var_108], r8
0x180086939  mov     [r8+18h], esi
0x18008693d  mov     rax, gs:30h
0x180086946  movzx   r15d, byte ptr [rax+1747h]
0x18008694e  mov     r9, [rbp+150h+var_120]
0x180086952  cmp     esi, [r9+0C4h]
0x180086959  ja      loc_180087054
0x18008695f  lea     r13d, [rsi+7]
0x180086963  and     r13d, 0FFFFFFF8h
0x180086967  mov     edx, [r9+0C0h]
0x18008696e  mov     [rbp+150h+var_144], edx
0x180086971  mov     ecx, [r9+0BCh]
0x180086978  cmp     r15d, ecx
0x18008697b  jb      short loc_18008698A
0x18008697d  xor     edx, edx
0x18008697f  mov     eax, r15d
0x180086982  div     ecx
0x180086984  mov     r15d, edx
0x180086987  mov     edx, [rbp+150h+var_144]
0x18008698a  mov     eax, r15d
0x18008698d  add     rax, 46h ; 'F'
0x180086991  lea     rax, [r9+rax*8]
0x180086995  mov     [rbp+150h+var_E0], rax
0x180086999  mov     r14, [rax]
0x18008699c  test    r14, r14
0x18008699f  jz      loc_180087020
0x1800869a5  lock inc dword ptr [r14+0Ch]
0x1800869aa  cmp     dword ptr [r14+2Ch], 1
0x1800869af  jnz     loc_180087020
0x1800869b5  mov     eax, [r14+8]
0x1800869b9  cmp     eax, edx
0x1800869bb  ja      loc_180087020
0x1800869c1  mov     edi, r13d
0x1800869c4  lock xadd [r14+8], edi
0x1800869ca  lea     eax, [rdi+r13]
0x1800869ce  cmp     eax, edx
0x1800869d0  ja      loc_180087018
0x1800869d6  mov     ecx, [r9+10h]
0x1800869da  sub     ecx, 2
0x1800869dd  jz      loc_180086AFA
0x1800869e3  cmp     ecx, 1
0x1800869e6  jz      loc_1800870D3
0x1800869ec  lea     rcx, [rbp+150h+var_C0]
0x1800869f3  call    RtlQueryPerformanceCounter
0x1800869f8  mov     rbx, [rbp+150h+var_C0]
0x1800869ff  jmp     loc_180086B02
0x180086a04  mov     [rbp+150h+var_147], 1
0x180086a08  add     esi, 10h
0x180086a0b  jmp     loc_1800868C2
0x180086a10  mov     rax, [rbp+150h+var_130]
0x180086a14  movzx   eax, byte ptr [rax+rdx+0Ch]
0x180086a19  jmp     loc_1800868EA
0x180086a1e  movzx   r8d, al
0x180086a22  sub     r8d, 1
0x180086a26  jz      loc_180086DD2
0x180086a2c  cmp     r8d, 1
0x180086a30  jnz     loc_1800868FA
0x180086a36  mov     rax, [rbp+150h+var_130]
0x180086a3a  mov     r8, [rax+rdx]
0x180086a3e  mov     [rbp+150h+Src], r8
0x180086a42  movzx   eax, word ptr [rax+rdx+8]
0x180086a47  mov     [rbp+150h+var_128], eax
0x180086a4a  add     eax, 0Fh
0x180086a4d  and     eax, 0FFFFFFF8h
0x180086a50  add     esi, eax
0x180086a52  jmp     loc_1800868FA
0x180086a57  mov     [rbp+150h+var_120], rdx
0x180086a5b  mov     edx, r12d
0x180086a5e  jmp     loc_180086860
0x180086a63  mov     edx, 216h
0x180086a68  mov     [rbp+150h+var_14C], edx
0x180086a6b  jmp     loc_18008690A
0x180086a70  mov     edx, [rbp+150h+var_14C]
0x180086a73  inc     esi
0x180086a75  jmp     loc_180086776
0x180086a7a  mov     ecx, r15d
0x180086a7d  add     rcx, rdi; void *
0x180086a80  add     r15d, edx
0x180086a83  mov     r8, rdx; Size
0x180086a86  mov     rdx, r9; Src
0x180086a89  call    memmove
0x180086a8e  mov     r10d, 4000h
0x180086a94  mov     r8, [rbp+150h+var_130]
0x180086a98  inc     r14d
0x180086a9b  cmp     r14d, r12d
0x180086a9e  jb      loc_180086C34
0x180086aa4  xor     r12d, r12d
0x180086aa7  mov     r13d, [rbp+150h+arg_38]
0x180086aae  mov     [rdi+10h], rbx
0x180086ab2  mov     rdx, [rbp+150h+var_120]
0x180086ab6  cmp     dword ptr [rdx+10h], 3
0x180086aba  jz      loc_1800870F1
0x180086ac0  rdtsc
0x180086ac2  shl     rdx, 20h
0x180086ac6  or      rax, rdx
0x180086ac9  mov     [rdi+38h], rax
0x180086acd  mov     rcx, gs:30h
0x180086ad6  mov     eax, [rcx+48h]
0x180086ad9  mov     [rdi+8], eax
0x180086adc  mov     eax, [rcx+40h]
0x180086adf  mov     [rdi+0Ch], eax
0x180086ae2  mov     esi, [rbp+150h+var_114]
0x180086ae5  mov     r14, [rbp+150h+arg_8]
0x180086aec  mov     edx, [rbp+150h+var_14C]
0x180086aef  mov     rdi, qword ptr [rbp+150h+Size+4]
0x180086af3  inc     esi
0x180086af5  jmp     loc_180086776
0x180086afa  call    RtlGetSystemTimePrecise
0x180086aff  mov     rbx, rax
0x180086b02  mov     r9, [rbp+150h+var_120]
0x180086b06  mov     edi, edi
0x180086b08  add     rdi, r14
0x180086b0b  mov     r8, [rbp+150h+var_108]
0x180086b0f  mov     r10, [rbp+150h+var_E8]
0x180086b13  test    rdi, rdi
0x180086b16  jz      loc_180086C83
0x180086b1c  mov     r13, r12
0x180086b1f  mov     r15d, 50h ; 'P'
0x180086b25  mov     [rbp+150h+var_144], r15d
0x180086b29  mov     [rbp+150h+var_108], r12
0x180086b2d  mov     [r8], r9
0x180086b30  mov     [r8+8], rdi
0x180086b34  mov     [r8+10h], r14
0x180086b38  inc     dword ptr [r10]
0x180086b3b  or      esi, 0C0130000h
0x180086b41  mov     [rdi], esi
0x180086b43  movzx   ecx, [rbp+150h+arg_20]
0x180086b4a  mov     [rdi+4], cx
0x180086b4e  movzx   eax, [rbp+150h+arg_10]
0x180086b55  mov     [rdi+6], ax
0x180086b59  mov     rax, qword ptr [rbp+150h+Size+4]
0x180086b5d  movups  xmm0, xmmword ptr [rax+20h]
0x180086b61  movups  xmmword ptr [rdi+18h], xmm0
0x180086b65  mov     rax, [rbp+150h+arg_8]
0x180086b6c  movups  xmm0, xmmword ptr [rax]
0x180086b6f  movups  xmmword ptr [rdi+28h], xmm0
0x180086b73  mov     rax, [rbp+150h+arg_28]
0x180086b7a  test    rax, rax
0x180086b7d  jnz     loc_180086FEF
0x180086b83  mov     rax, gs:30h
0x180086b8c  movups  xmm0, xmmword ptr [rax+1710h]
0x180086b93  movups  xmmword ptr [rdi+40h], xmm0
0x180086b97  mov     rax, [rbp+150h+arg_30]
0x180086b9e  test    rax, rax
0x180086ba1  jz      short loc_180086BD7
0x180086ba3  lea     r13, [rdi+50h]
0x180086ba7  mov     word ptr [r13+0], 18h
0x180086bae  mov     dword ptr [rdi+52h], 1
0x180086bb5  mov     word ptr [rdi+56h], 10h
0x180086bbb  movups  xmm0, xmmword ptr [rax]
  ... truncated ...
```
