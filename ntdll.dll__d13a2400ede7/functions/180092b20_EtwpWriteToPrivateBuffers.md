# EtwpWriteToPrivateBuffers

- ea: `0x180092b20`
- end: `0x18009355a`
- name: `EtwpWriteToPrivateBuffers`
- size: `2618`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x180091530`
- `0x180092120`
- `0x180092440`
- `0x180092790`

## callees

- `0x180013cb0`
- `0x180013d70`
- `0x180092b20`
- `0x180093560`
- `0x180093640`
- `0x180094020`
- `0x180094280`
- `0x18013aa58`
- `0x18015ef00`
- `0x180162810`
- `0x180164280`
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
0x180092b20  mov     [rsp-8+arg_18], r9w
0x180092b26  mov     [rsp-8+arg_10], r8w
0x180092b2c  mov     [rsp-8+arg_8], rdx
0x180092b31  push    rbp
0x180092b32  push    rbx
0x180092b33  push    rsi
0x180092b34  push    rdi
0x180092b35  push    r12
0x180092b37  push    r13
0x180092b39  push    r14
0x180092b3b  push    r15
0x180092b3d  sub     rsp, 148h
0x180092b44  lea     rbp, [rsp+30h]
0x180092b49  mov     rax, cs:__security_cookie
0x180092b50  xor     rax, rbp
0x180092b53  mov     [rbp+150h+var_50], rax
0x180092b5a  mov     r14, rdx
0x180092b5d  mov     rdi, rcx
0x180092b60  mov     qword ptr [rbp+150h+Size+4], rcx
0x180092b64  mov     [rbp+150h+Src], rcx
0x180092b68  mov     rbx, [rbp+150h+arg_40]
0x180092b6f  mov     [rbp+150h+var_130], rbx
0x180092b73  mov     rbx, [rbp+150h+arg_48]
0x180092b7a  mov     [rbp+150h+var_D0], rbx
0x180092b81  lea     rax, [rbx+80h]
0x180092b88  mov     [rbp+150h+var_E8], rax
0x180092b8c  xor     r12d, r12d
0x180092b8f  mov     [rax], r12d
0x180092b92  mov     r13d, [rbp+150h+arg_38]
0x180092b99  cmp     r13d, 80h
0x180092ba0  ja      loc_1800932DA
0x180092ba6  mov     [rbp+150h+var_110], r12
0x180092baa  movzx   r15d, r12w
0x180092bae  mov     [rbp+150h+var_100], r15
0x180092bb2  mov     [rbp+150h+var_150], r12w
0x180092bb7  test    byte ptr [rcx+0E8h], 4
0x180092bbe  jnz     loc_18009324D
0x180092bc4  mov     edx, r12d
0x180092bc7  mov     [rbp+150h+var_14C], edx
0x180092bca  mov     word ptr [rbp+150h+var_128], r12w
0x180092bcf  mov     [rbp+150h+Src], r12
0x180092bd3  mov     esi, r12d
0x180092bd6  mov     [rbp+150h+var_114], esi
0x180092bd9  cmp     esi, 4
0x180092bdc  jnb     loc_180093117
0x180092be2  mov     rbx, r12
0x180092be5  mov     [rbp+150h+var_C0], rbx
0x180092bec  mov     dword ptr [rbp+150h+Size], r12d
0x180092bf0  xor     edx, edx; Val
0x180092bf2  mov     r8d, 58h ; 'X'; Size
0x180092bf8  lea     rcx, [rbp+150h+var_B0]; void *
0x180092bff  call    memset$thunk$772440563353939046
0x180092c04  movzx   eax, [rbp+150h+arg_18]
0x180092c0b  bt      eax, esi
0x180092c0e  jb      loc_180092ED0
0x180092c14  mov     eax, esi
0x180092c16  add     rax, 5
0x180092c1a  lea     rax, [rax+rax*2]
0x180092c1e  lea     rdi, [rdi+rax*8]
0x180092c22  cmp     byte ptr [rdi+14h], 0
0x180092c26  jz      loc_180092F4C
0x180092c2c  movzx   eax, byte ptr [rdi+15h]
0x180092c30  cmp     [r14+4], al
0x180092c34  ja      loc_180093544
0x180092c3a  mov     rdx, [r14+8]
0x180092c3e  test    byte ptr [rdi+10h], 40h
0x180092c42  jz      short loc_180092C49
0x180092c44  test    rdx, rdx
0x180092c47  jz      short loc_180092C62
0x180092c49  test    [rdi+8], rdx
0x180092c4d  jz      loc_180092F4C
0x180092c53  mov     rax, [rdi]
0x180092c56  and     rax, rdx
0x180092c59  cmp     rax, [rdi]
0x180092c5c  jnz     loc_180092F4C
0x180092c62  mov     [rbp+150h+var_120], r12
0x180092c66  movzx   r15d, byte ptr [rdi+16h]
0x180092c6b  mov     [rbp+150h+var_F0], r15d
0x180092c6f  mov     eax, r15d
0x180092c72  mov     [rbp+150h+var_140], eax
0x180092c75  cmp     cs:EtwpLoggerArray, 0
0x180092c7d  jz      short loc_180092CBB
0x180092c7f  cmp     r15d, 40h ; '@'
0x180092c83  jnb     loc_180093457
0x180092c89  mov     ecx, eax
0x180092c8b  shl     rcx, 4
0x180092c8f  mov     rax, cs:EtwpLoggerArray
0x180092c96  lock inc dword ptr [rcx+rax+8]
0x180092c9b  mov     rax, cs:EtwpLoggerArray
0x180092ca2  mov     rdx, [rcx+rax]
0x180092ca6  test    dl, 1
0x180092ca9  jz      loc_180092EB7
0x180092caf  mov     rax, cs:EtwpLoggerArray
0x180092cb6  lock dec dword ptr [rcx+rax+8]
0x180092cbb  mov     edx, 1069h
0x180092cc0  mov     [rbp+150h+var_14C], edx
0x180092cc3  test    edx, edx
0x180092cc5  jnz     loc_180092F4F
0x180092ccb  mov     [rbp+150h+var_147], dl
0x180092cce  mov     [rbp+150h+var_148], dl
0x180092cd1  mov     [rbp+150h+var_146], dl
0x180092cd4  mov     word ptr [rbp+150h+var_118], r12w
0x180092cd9  movzx   r11d, r12w
0x180092cdd  mov     [rbp+150h+var_150], r12w
0x180092ce2  mov     r10d, r12d
0x180092ce5  mov     [rbp+150h+var_140], r12d
0x180092ce9  mov     r14d, 68h ; 'h'
0x180092cef  cmp     [rbp+150h+arg_30], 0
0x180092cf7  mov     eax, 50h ; 'P'
0x180092cfc  cmovz   r14d, eax
0x180092d00  test    byte ptr [rdi+10h], 1
0x180092d04  jnz     loc_1800932E4
0x180092d0a  mov     esi, r14d
0x180092d0d  mov     ecx, [rdi+10h]
0x180092d10  test    cl, 4
0x180092d13  jnz     loc_180093342
0x180092d19  test    cl, 2
0x180092d1c  jnz     loc_180092E64
0x180092d22  mov     ecx, r12d
0x180092d25  cmp     ecx, r13d
0x180092d28  jnb     short loc_180092D67
0x180092d2a  mov     r9d, esi
0x180092d2d  mov     edx, ecx
0x180092d2f  shl     rdx, 4
0x180092d33  mov     rax, qword ptr [rbp+150h+Size+4]
0x180092d37  mov     r8d, 4000h
0x180092d3d  test    [rax+56h], r8w
0x180092d42  jnz     loc_180092E70
0x180092d48  xor     al, al
0x180092d4a  test    al, al
0x180092d4c  jnz     loc_180092E7E
0x180092d52  mov     rax, [rbp+150h+var_130]
0x180092d56  add     esi, [rax+rdx+8]
0x180092d5a  cmp     esi, r9d
0x180092d5d  jb      loc_180092EC3
0x180092d63  inc     ecx
0x180092d65  jmp     short loc_180092D25
0x180092d67  mov     edx, [rbp+150h+var_14C]
0x180092d6a  test    r10d, r10d
0x180092d6d  jz      short loc_180092D7B
0x180092d6f  movzx   eax, r11w
0x180092d73  add     eax, 0Fh
0x180092d76  and     eax, 0FFFFFFF8h
0x180092d79  add     esi, eax
0x180092d7b  test    edx, edx
0x180092d7d  jnz     loc_18009313D
0x180092d83  mov     r10, [rbp+150h+var_E8]
0x180092d87  mov     r8d, [r10]
0x180092d8a  shl     r8, 5
0x180092d8e  add     r8, [rbp+150h+var_D0]
0x180092d95  mov     [rbp+150h+var_108], r8
0x180092d99  mov     [r8+18h], esi
0x180092d9d  mov     rax, gs:30h
0x180092da6  movzx   r15d, byte ptr [rax+1747h]
0x180092dae  mov     r9, [rbp+150h+var_120]
0x180092db2  cmp     esi, [r9+0C4h]
0x180092db9  ja      loc_1800934B4
0x180092dbf  lea     r13d, [rsi+7]
0x180092dc3  and     r13d, 0FFFFFFF8h
0x180092dc7  mov     edx, [r9+0C0h]
0x180092dce  mov     [rbp+150h+var_144], edx
0x180092dd1  mov     ecx, [r9+0BCh]
0x180092dd8  cmp     r15d, ecx
0x180092ddb  jb      short loc_180092DEA
0x180092ddd  xor     edx, edx
0x180092ddf  mov     eax, r15d
0x180092de2  div     ecx
0x180092de4  mov     r15d, edx
0x180092de7  mov     edx, [rbp+150h+var_144]
0x180092dea  mov     eax, r15d
0x180092ded  add     rax, 46h ; 'F'
0x180092df1  lea     rax, [r9+rax*8]
0x180092df5  mov     [rbp+150h+var_E0], rax
0x180092df9  mov     r14, [rax]
0x180092dfc  test    r14, r14
0x180092dff  jz      loc_180093480
0x180092e05  lock inc dword ptr [r14+0Ch]
0x180092e0a  cmp     dword ptr [r14+2Ch], 1
0x180092e0f  jnz     loc_180093480
0x180092e15  mov     eax, [r14+8]
0x180092e19  cmp     eax, edx
0x180092e1b  ja      loc_180093480
0x180092e21  mov     edi, r13d
0x180092e24  lock xadd [r14+8], edi
0x180092e2a  lea     eax, [rdi+r13]
0x180092e2e  cmp     eax, edx
0x180092e30  ja      loc_180093478
0x180092e36  mov     ecx, [r9+10h]
0x180092e3a  sub     ecx, 2
0x180092e3d  jz      loc_180092F5A
0x180092e43  cmp     ecx, 1
0x180092e46  jz      loc_180093533
0x180092e4c  lea     rcx, [rbp+150h+var_C0]
0x180092e53  call    RtlQueryPerformanceCounter
0x180092e58  mov     rbx, [rbp+150h+var_C0]
0x180092e5f  jmp     loc_180092F62
0x180092e64  mov     [rbp+150h+var_147], 1
0x180092e68  add     esi, 10h
0x180092e6b  jmp     loc_180092D22
0x180092e70  mov     rax, [rbp+150h+var_130]
0x180092e74  movzx   eax, byte ptr [rax+rdx+0Ch]
0x180092e79  jmp     loc_180092D4A
0x180092e7e  movzx   r8d, al
0x180092e82  sub     r8d, 1
0x180092e86  jz      loc_180093232
0x180092e8c  cmp     r8d, 1
0x180092e90  jnz     loc_180092D5A
0x180092e96  mov     rax, [rbp+150h+var_130]
0x180092e9a  mov     r8, [rax+rdx]
0x180092e9e  mov     [rbp+150h+Src], r8
0x180092ea2  movzx   eax, word ptr [rax+rdx+8]
0x180092ea7  mov     [rbp+150h+var_128], eax
0x180092eaa  add     eax, 0Fh
0x180092ead  and     eax, 0FFFFFFF8h
0x180092eb0  add     esi, eax
0x180092eb2  jmp     loc_180092D5A
0x180092eb7  mov     [rbp+150h+var_120], rdx
0x180092ebb  mov     edx, r12d
0x180092ebe  jmp     loc_180092CC0
0x180092ec3  mov     edx, 216h
0x180092ec8  mov     [rbp+150h+var_14C], edx
0x180092ecb  jmp     loc_180092D6A
0x180092ed0  mov     edx, [rbp+150h+var_14C]
0x180092ed3  inc     esi
0x180092ed5  jmp     loc_180092BD6
0x180092eda  mov     ecx, r15d
0x180092edd  add     rcx, rdi; void *
0x180092ee0  add     r15d, edx
0x180092ee3  mov     r8, rdx; Size
0x180092ee6  mov     rdx, r9; Src
0x180092ee9  call    memmove
0x180092eee  mov     r10d, 4000h
0x180092ef4  mov     r8, [rbp+150h+var_130]
0x180092ef8  inc     r14d
0x180092efb  cmp     r14d, r12d
0x180092efe  jb      loc_180093094
0x180092f04  xor     r12d, r12d
0x180092f07  mov     r13d, [rbp+150h+arg_38]
0x180092f0e  mov     [rdi+10h], rbx
0x180092f12  mov     rdx, [rbp+150h+var_120]
0x180092f16  cmp     dword ptr [rdx+10h], 3
0x180092f1a  jz      loc_180093551
0x180092f20  rdtsc
0x180092f22  shl     rdx, 20h
0x180092f26  or      rax, rdx
0x180092f29  mov     [rdi+38h], rax
0x180092f2d  mov     rcx, gs:30h
0x180092f36  mov     eax, [rcx+48h]
0x180092f39  mov     [rdi+8], eax
0x180092f3c  mov     eax, [rcx+40h]
0x180092f3f  mov     [rdi+0Ch], eax
0x180092f42  mov     esi, [rbp+150h+var_114]
0x180092f45  mov     r14, [rbp+150h+arg_8]
0x180092f4c  mov     edx, [rbp+150h+var_14C]
0x180092f4f  mov     rdi, qword ptr [rbp+150h+Size+4]
0x180092f53  inc     esi
0x180092f55  jmp     loc_180092BD6
0x180092f5a  call    RtlGetSystemTimePrecise
0x180092f5f  mov     rbx, rax
0x180092f62  mov     r9, [rbp+150h+var_120]
0x180092f66  mov     edi, edi
0x180092f68  add     rdi, r14
0x180092f6b  mov     r8, [rbp+150h+var_108]
0x180092f6f  mov     r10, [rbp+150h+var_E8]
0x180092f73  test    rdi, rdi
0x180092f76  jz      loc_1800930E3
0x180092f7c  mov     r13, r12
0x180092f7f  mov     r15d, 50h ; 'P'
0x180092f85  mov     [rbp+150h+var_144], r15d
0x180092f89  mov     [rbp+150h+var_108], r12
0x180092f8d  mov     [r8], r9
0x180092f90  mov     [r8+8], rdi
0x180092f94  mov     [r8+10h], r14
0x180092f98  inc     dword ptr [r10]
0x180092f9b  or      esi, 0C0130000h
0x180092fa1  mov     [rdi], esi
0x180092fa3  movzx   ecx, [rbp+150h+arg_20]
0x180092faa  mov     [rdi+4], cx
0x180092fae  movzx   eax, [rbp+150h+arg_10]
0x180092fb5  mov     [rdi+6], ax
0x180092fb9  mov     rax, qword ptr [rbp+150h+Size+4]
0x180092fbd  movups  xmm0, xmmword ptr [rax+20h]
0x180092fc1  movups  xmmword ptr [rdi+18h], xmm0
0x180092fc5  mov     rax, [rbp+150h+arg_8]
0x180092fcc  movups  xmm0, xmmword ptr [rax]
0x180092fcf  movups  xmmword ptr [rdi+28h], xmm0
0x180092fd3  mov     rax, [rbp+150h+arg_28]
0x180092fda  test    rax, rax
0x180092fdd  jnz     loc_18009344F
0x180092fe3  mov     rax, gs:30h
0x180092fec  movups  xmm0, xmmword ptr [rax+1710h]
0x180092ff3  movups  xmmword ptr [rdi+40h], xmm0
0x180092ff7  mov     rax, [rbp+150h+arg_30]
0x180092ffe  test    rax, rax
0x180093001  jz      short loc_180093037
0x180093003  lea     r13, [rdi+50h]
0x180093007  mov     word ptr [r13+0], 18h
0x18009300e  mov     dword ptr [rdi+52h], 1
0x180093015  mov     word ptr [rdi+56h], 10h
0x18009301b  movups  xmm0, xmmword ptr [rax]
  ... truncated ...
```
