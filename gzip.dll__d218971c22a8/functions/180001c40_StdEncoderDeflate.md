# StdEncoderDeflate

- ea: `0x180001c40`
- end: `0x180002572`
- name: `StdEncoderDeflate`
- size: `2354`
- prototype: `__int16 __fastcall(__int64, int, int, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800028e0`

## callees

- `0x180001c40`
- `0x180002580`
- `0x1800026e0`
- `0x1800066ac`

## pseudocode

```c
__int16 __fastcall StdEncoderDeflate(__int64 a1, int a2, int a3, int a4, int a5)
{
  __int64 v6; // rbx
  int v7; // r8d
  int v8; // eax
  __int64 v9; // r14
  _BYTE *v10; // r10
  int v11; // r9d
  unsigned int v12; // r13d
  int v13; // edi
  unsigned __int8 *v14; // r12
  __int64 v15; // rax
  int v16; // edx
  int Match; // esi
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // rdx
  int v21; // edx
  int v22; // eax
  __int64 v23; // rax
  int v24; // r8d
  int v25; // ecx
  int v26; // r11d
  __int64 v27; // rax
  __int64 v28; // r8
  int v29; // r10d
  unsigned int v30; // r9d
  _BYTE *v31; // r13
  __int64 v32; // rax
  __int64 v33; // r13
  int v34; // r12d
  __int64 v35; // rcx
  int v36; // r11d
  __int64 v37; // rax
  unsigned int v38; // r8d
  int v39; // r9d
  _BYTE *v40; // r10
  char v41; // cl
  __int64 v42; // rax
  char v43; // cl
  unsigned int v44; // eax
  __int64 v45; // rax
  __int64 v46; // r12
  int v47; // r11d
  __int64 v48; // rcx
  int v49; // r10d
  __int64 v50; // rax
  _BYTE *v51; // rdx
  int v52; // r9d
  unsigned int v53; // r8d
  char v54; // cl
  __int64 v55; // rax
  int v56; // r13d
  char v57; // cl
  unsigned int v58; // eax
  __int64 v59; // rax
  __int64 v60; // r9
  int v61; // r12d
  __int64 v62; // rcx
  int v63; // r11d
  __int64 v64; // rax
  int v65; // r10d
  unsigned int v66; // r8d
  _BYTE *v67; // r13
  char v68; // cl
  __int64 v69; // rax
  int v70; // r13d
  _BYTE *v71; // rcx
  char v72; // cl
  unsigned int v73; // eax
  _BYTE *v74; // rcx
  int i; // esi
  __int64 v76; // rdx
  __int64 v77; // rax
  __int16 v78; // cx
  unsigned int v80; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v81; // [rsp+44h] [rbp-64h] BYREF
  __int64 v82; // [rsp+48h] [rbp-60h]
  _BYTE *v83; // [rsp+50h] [rbp-58h]
  int v84; // [rsp+B0h] [rbp+8h]
  __int64 v85; // [rsp+B0h] [rbp+8h]

  v6 = *(int *)(a1 + 32);
  v7 = a2;
  v8 = *(_DWORD *)(a1 + 36);
  v9 = *(_QWORD *)(a1 + 80);
  v10 = *(_BYTE **)(v9 + 181016);
  v11 = *(_DWORD *)(v9 + 181008);
  v12 = *(_DWORD *)(v9 + 181004);
  v13 = (32 * *(unsigned __int8 *)(v6 + v9)) ^ *(unsigned __int8 *)(v6 + v9 + 1);
  v83 = v10;
  v84 = v11;
  if ( (int)v6 >= v8 )
    goto LABEL_71;
  while ( 1 )
  {
    v80 = 0;
    v14 = (unsigned __int8 *)((int)v6 + v9);
    if ( v8 - (int)v6 <= 3 )
      goto LABEL_8;
    v13 = v14[2] ^ (32 * v13);
    v15 = v13 & 0x1FFF;
    v16 = *(unsigned __int16 *)(v9 + 2 * v15 + 131850);
    *(_WORD *)(v9 + 2 * v15 + 131850) = v6;
    *(_WORD *)(v9 + 2 * (v6 & 0x7FFF) + 65798) = v16;
    if ( !(_WORD)v16 )
      goto LABEL_8;
    Match = StdEncoderFindMatch(v9, (int)v9 + 65798, v6, v16, (__int64)&v80, v7, a5);
    v18 = *(_DWORD *)(a1 + 36);
    if ( Match + (int)v6 > v18 )
      Match = v18 - v6;
    if ( Match < 3 )
    {
      v11 = v84;
      v10 = v83;
LABEL_8:
      ++*(_DWORD *)(a1 + 28);
      ++*(_WORD *)(*(_QWORD *)(a1 + 80) + 2LL * *v14 + 193248);
      v19 = *v14;
      v20 = *(_QWORD *)(a1 + 80);
      v12 |= *(unsigned __int16 *)(v20 + 2 * v19 + 192672) << v11;
      v11 += *(unsigned __int8 *)(v20 + v19 + 192384);
      v84 = v11;
      if ( v11 >= 16 )
      {
        *(_WORD *)v10 = v12;
        v12 >>= 16;
        v11 -= 16;
        v83 = v10 + 2;
        v84 = v11;
      }
      LODWORD(v6) = v6 + 1;
      goto LABEL_11;
    }
    v21 = v6 + 1;
    v82 = (unsigned int)(v6 + 1);
    if ( Match > a3 )
    {
      LODWORD(v6) = v6 + 1;
      _mm_lfence();
      v59 = (v80 >> 7) + 256;
      if ( v80 < 0x100 )
        v59 = v80;
      ++*(_DWORD *)(a1 + 28);
      v60 = *((unsigned __int8 *)g_DistLookup + v59);
      v61 = (unsigned __int8)g_ExtraDistanceBits[v60];
      v62 = *((unsigned __int8 *)&qword_18000AC20[31] + Match + 5);
      v63 = *((unsigned __int8 *)&g_ExtraLengthBits + v62);
      ++*(_WORD *)(*(_QWORD *)(a1 + 80) + 2 * (v62 + 257) + 193248);
      ++*(_WORD *)(*(_QWORD *)(a1 + 80) + 2 * v60 + 195264);
      v64 = *(_QWORD *)(a1 + 80);
      v65 = v84 + *(unsigned __int8 *)(v64 + v62 + 257 + 192384);
      v66 = v12 | (*(unsigned __int16 *)(v64 + 2 * (v62 + 257) + 192672) << v84);
      v67 = v83;
      if ( v65 >= 16 )
      {
        *v83 = v66;
        v67[1] = BYTE1(v66);
        v67 += 2;
        v66 >>= 16;
        v83 = v67;
        v65 -= 16;
      }
      if ( v63 )
      {
        v68 = v65;
        v65 += v63;
        v66 |= ((Match - 3) & ((1 << v63) - 1)) << v68;
        if ( v65 >= 16 )
        {
          *(_WORD *)v67 = v66;
          v66 >>= 16;
          v83 = v67 + 2;
          v65 -= 16;
        }
      }
      v69 = *(_QWORD *)(a1 + 80);
      v70 = *(unsigned __int16 *)(v69 + 2 * v60 + 181824);
      v11 = v65 + *(unsigned __int8 *)(v60 + v69 + 181792);
      v12 = v66 | (v70 << v65);
      v84 = v11;
      if ( v11 >= 16 )
      {
        v71 = v83;
        *(_WORD *)v83 = v12;
        v12 >>= 16;
        v11 -= 16;
        v83 = v71 + 2;
        v84 = v11;
      }
      if ( v61 )
      {
        v72 = v11;
        v11 += v61;
        v73 = v12 | ((v80 & ((1 << v61) - 1)) << v72);
        v84 = v11;
        v12 = v73;
        if ( v11 >= 16 )
        {
          v74 = v83;
          *(_WORD *)v83 = v73;
          v12 = HIWORD(v73);
          v11 -= 16;
          v83 = v74 + 2;
          v84 = v11;
        }
      }
    }
    else
    {
      v22 = (32 * v13) ^ v14[3];
      v81 = 0;
      v13 = v22;
      v23 = v22 & 0x1FFF;
      v24 = *(unsigned __int16 *)(v9 + 2 * v23 + 131850);
      *(_WORD *)(v9 + 2 * v23 + 131850) = v21;
      *(_WORD *)(v9 + 2LL * (v21 & 0x7FFF) + 65798) = v24;
      if ( !(_WORD)v24 )
        goto LABEL_39;
      v25 = a2;
      if ( Match >= a4 )
        v25 = a2 >> 2;
      v26 = StdEncoderFindMatch(v9, (int)v9 + 65798, v21, v24, (__int64)&v81, v25, a5);
      if ( (int)v6 + v26 + 1 > *(_DWORD *)(a1 + 36) )
        v26 = *(_DWORD *)(a1 + 36) - v82;
      LODWORD(v82) = v26;
      if ( v26 > Match )
      {
        _mm_lfence();
        ++*(_DWORD *)(a1 + 28);
        ++*(_WORD *)(*(_QWORD *)(a1 + 80) + 2LL * *v14 + 193248);
        v27 = *v14;
        v28 = *(_QWORD *)(a1 + 80);
        v29 = v84 + *(unsigned __int8 *)(v28 + v27 + 192384);
        v30 = v12 | (*(unsigned __int16 *)(v28 + 2 * v27 + 192672) << v84);
        if ( v29 >= 16 )
        {
          v31 = v83;
          *(_WORD *)v83 = v30;
          v28 = *(_QWORD *)(a1 + 80);
          v30 >>= 16;
          v83 = v31 + 2;
          v29 -= 16;
        }
        v32 = (v81 >> 7) + 256;
        if ( v81 < 0x100 )
          v32 = v81;
        ++*(_DWORD *)(a1 + 28);
        v33 = *((unsigned __int8 *)g_DistLookup + v32);
        v85 = v33;
        v34 = (unsigned __int8)g_ExtraDistanceBits[v33];
        v35 = *((unsigned __int8 *)&qword_18000AC20[31] + v26 + 5);
        ++*(_WORD *)(v28 + 2 * v35 + 193762);
        v36 = *((unsigned __int8 *)&g_ExtraLengthBits + v35);
        ++*(_WORD *)(*(_QWORD *)(a1 + 80) + 2 * v33 + 195264);
        v37 = *(_QWORD *)(a1 + 80);
        v38 = v30 | (*(unsigned __int16 *)(v37 + 2 * (v35 + 257) + 192672) << v29);
        v39 = v29 + *(unsigned __int8 *)(v37 + v35 + 257 + 192384);
        v40 = v83;
        if ( v39 >= 16 )
        {
          *v83 = v38;
          v40[1] = BYTE1(v38);
          v40 += 2;
          v38 >>= 16;
          v83 = v40;
          v39 -= 16;
        }
        Match = v82;
        if ( v36 )
        {
          v41 = v39;
          v39 += v36;
          v38 |= (((_DWORD)v82 - 3) & ((1 << v36) - 1)) << v41;
          if ( v39 >= 16 )
          {
            *(_WORD *)v40 = v38;
            v40 += 2;
            v38 >>= 16;
            v83 = v40;
            v39 -= 16;
          }
        }
        v42 = *(_QWORD *)(a1 + 80);
        v12 = v38 | (*(unsigned __int16 *)(v42 + 2 * v33 + 181824) << v39);
        v11 = *(unsigned __int8 *)(v85 + v42 + 181792) + v39;
        v84 = v11;
        if ( v11 >= 16 )
        {
          *(_WORD *)v40 = v12;
          v40 += 2;
          v12 >>= 16;
          v11 -= 16;
          v83 = v40;
          v84 = v11;
        }
        if ( v34 )
        {
          v43 = v11;
          v11 += v34;
          v44 = v12 | ((v81 & ((1 << v34) - 1)) << v43);
          v84 = v11;
          v12 = v44;
          if ( v11 >= 16 )
          {
            *(_WORD *)v40 = v44;
            v12 = HIWORD(v44);
            v11 -= 16;
            v83 = v40 + 2;
            v84 = v11;
          }
        }
        LODWORD(v6) = v6 + 2;
      }
      else
      {
LABEL_39:
        _mm_lfence();
        v45 = (v80 >> 7) + 256;
        if ( v80 < 0x100 )
          v45 = v80;
        ++*(_DWORD *)(a1 + 28);
        v46 = *((unsigned __int8 *)g_DistLookup + v45);
        v47 = (unsigned __int8)g_ExtraDistanceBits[v46];
        v48 = *((unsigned __int8 *)&qword_18000AC20[31] + Match + 5);
        v49 = *((unsigned __int8 *)&g_ExtraLengthBits + v48);
        ++*(_WORD *)(*(_QWORD *)(a1 + 80) + 2 * (v48 + 257) + 193248);
        ++*(_WORD *)(*(_QWORD *)(a1 + 80) + 2 * v46 + 195264);
        v50 = *(_QWORD *)(a1 + 80);
        v51 = v83;
        v52 = v84 + *(unsigned __int8 *)(v50 + v48 + 257 + 192384);
        v53 = v12 | (*(unsigned __int16 *)(v50 + 2 * (v48 + 257) + 192672) << v84);
        if ( v52 >= 16 )
        {
          *v83 = v53;
          v51[1] = BYTE1(v53);
          v51 += 2;
          v53 >>= 16;
          v83 = v51;
          v52 -= 16;
        }
        if ( v49 )
        {
          v54 = v52;
          v52 += v49;
          v53 |= ((Match - 3) & ((1 << v49) - 1)) << v54;
          v51 = v83;
          if ( v52 >= 16 )
          {
            *v83 = v53;
            v51[1] = BYTE1(v53);
            v51 += 2;
            v53 >>= 16;
            v83 = v51;
            v52 -= 16;
          }
        }
        v55 = *(_QWORD *)(a1 + 80);
        v56 = *(unsigned __int16 *)(v55 + 2 * v46 + 181824) << v52;
        v11 = *(unsigned __int8 *)(v46 + v55 + 181792) + v52;
        v12 = v53 | v56;
        v84 = v11;
        if ( v11 >= 16 )
        {
          *(_WORD *)v51 = v12;
          v51 += 2;
          v12 >>= 16;
          v11 -= 16;
          v83 = v51;
          v84 = v11;
        }
        if ( v47 )
        {
          v57 = v11;
          v11 += v47;
          v58 = v12 | ((v80 & ((1 << v47) - 1)) << v57);
          v84 = v11;
          v12 = v58;
          if ( v11 >= 16 )
          {
            *(_WORD *)v51 = v58;
            v12 = HIWORD(v58);
            v11 -= 16;
            v83 = v51 + 2;
            v84 = v11;
          }
        }
        --Match;
        LODWORD(v6) = v6 + 2;
      }
    }
    if ( *(_DWORD *)(a1 + 36) - (int)v6 > Match )
    {
      for ( i = Match - 1; i > 0; *(_WORD *)(v9 + 2 * v76 + 65798) = v78 )
      {
        --i;
        v76 = v6 & 0x7FFF;
        v13 = (32 * v13) ^ *(unsigned __int8 *)(v9 + (int)v6 + 2);
        v77 = v13 & 0x1FFF;
        v78 = *(_WORD *)(v9 + 2 * v77 + 131850);
        *(_WORD *)(v9 + 2 * v77 + 131850) = v6;
        LODWORD(v6) = v6 + 1;
      }
    }
    else
    {
      LODWORD(v6) = Match + v6 - 1;
    }
LABEL_11:
    v10 = v83;
    if ( *(_DWORD *)(a1 + 28) < 0xFFF2u && (unsigned __int64)v83 < v9 + 180994 )
      goto LABEL_15;
    *v83 = v12;
    v10[1] = BYTE1(v12);
    v83 = v10 + 2;
    LOWORD(v8) = StdEncoderOutputBlock(a1);
    if ( *(_DWORD *)a1 )
      break;
    v10 = *(_BYTE **)(v9 + 181016);
    v11 = *(_DWORD *)(v9 + 181008);
    v12 = *(_DWORD *)(v9 + 181004);
    v83 = v10;
    v84 = v11;
LABEL_15:
    v8 = *(_DWORD *)(a1 + 36);
    v7 = a2;
    if ( (int)v6 >= v8 )
      goto LABEL_70;
  }
  v10 = v83;
LABEL_70:
  v11 = v84;
LABEL_71:
  *(_DWORD *)(v9 + 181004) = v12;
  *(_QWORD *)(v9 + 181016) = v10;
  *(_DWORD *)(v9 + 181008) = v11;
  *(_DWORD *)(a1 + 32) = v6;
  if ( (_DWORD)v6 == 0x10000 )
    LOWORD(v8) = StdEncoderMoveWindows(a1);
  return v8;
}

```

## disassembly

```asm
0x180001c40  mov     r11, rsp
0x180001c43  mov     [r11+20h], r9d
0x180001c47  mov     [r11+18h], r8d
0x180001c4b  mov     [rsp+arg_8], edx
0x180001c4f  push    rbp
0x180001c50  sub     rsp, 0A0h
0x180001c57  mov     [r11-10h], rbx
0x180001c5b  mov     rbp, rcx
0x180001c5e  movsxd  rbx, dword ptr [rcx+20h]
0x180001c62  mov     r8d, edx
0x180001c65  mov     [r11-20h], rdi
0x180001c69  mov     [r11-30h], r13
0x180001c6d  mov     eax, [rbp+24h]
0x180001c70  mov     [r11-38h], r14
0x180001c74  mov     r14, [rcx+50h]
0x180001c78  mov     [r11-40h], r15
0x180001c7c  movzx   ecx, byte ptr [rbx+r14]
0x180001c81  movzx   edi, byte ptr [rbx+r14+1]
0x180001c87  mov     r10, [r14+2C318h]
0x180001c8e  mov     r9d, [r14+2C310h]
0x180001c95  mov     r13d, [r14+2C30Ch]
0x180001c9c  shl     ecx, 5
0x180001c9f  xor     edi, ecx
0x180001ca1  mov     [rsp+0A8h+var_58], r10
0x180001ca6  mov     dword ptr [rsp+0A8h+arg_0], r9d
0x180001cae  cmp     ebx, eax
0x180001cb0  jge     loc_180002522
0x180001cb6  mov     [r11-18h], rsi
0x180001cba  mov     [r11-28h], r12
0x180001cbe  xchg    ax, ax
0x180001cc0  movsxd  rcx, ebx
0x180001cc3  sub     eax, ebx
0x180001cc5  mov     [rsp+0A8h+var_68], 0
0x180001ccd  lea     r12, [rcx+r14]
0x180001cd1  cmp     eax, 3
0x180001cd4  jle     loc_180001D67
0x180001cda  movzx   eax, byte ptr [r12+2]
0x180001ce0  and     ecx, 7FFFh
0x180001ce6  shl     edi, 5
0x180001ce9  xor     edi, eax
0x180001ceb  mov     eax, edi
0x180001ced  and     eax, 1FFFh
0x180001cf2  movzx   edx, word ptr [r14+rax*2+2030Ah]
0x180001cfb  mov     [r14+rax*2+2030Ah], bx
0x180001d04  mov     [r14+rcx*2+10106h], dx
0x180001d0d  test    dx, dx
0x180001d10  jz      short loc_180001D67
0x180001d12  mov     eax, [rsp+0A8h+arg_20]
0x180001d19  mov     r9d, edx
0x180001d1c  mov     [rsp+0A8h+var_78], eax
0x180001d20  lea     rdx, [r14+10106h]
0x180001d27  mov     [rsp+0A8h+var_80], r8d
0x180001d2c  lea     rax, [rsp+0A8h+var_68]
0x180001d31  mov     r8d, ebx
0x180001d34  mov     [rsp+0A8h+var_88], rax
0x180001d39  mov     rcx, r14
0x180001d3c  call    StdEncoderFindMatch
0x180001d41  mov     esi, eax
0x180001d43  mov     eax, [rbp+24h]
0x180001d46  lea     ecx, [rsi+rbx]
0x180001d49  cmp     ecx, eax
0x180001d4b  jle     short loc_180001D51
0x180001d4d  mov     esi, eax
0x180001d4f  sub     esi, ebx
0x180001d51  cmp     esi, 3
0x180001d54  jge     loc_180001E53
0x180001d5a  mov     r9d, dword ptr [rsp+0A8h+arg_0]
0x180001d62  mov     r10, [rsp+0A8h+var_58]
0x180001d67  inc     dword ptr [rbp+1Ch]
0x180001d6a  movzx   ecx, byte ptr [r12]
0x180001d6f  mov     rax, [rbp+50h]
0x180001d73  inc     word ptr [rax+rcx*2+2F2E0h]
0x180001d7b  mov     ecx, r9d
0x180001d7e  movzx   r8d, byte ptr [r12]
0x180001d83  mov     rdx, [rbp+50h]
0x180001d87  movzx   eax, word ptr [rdx+r8*2+2F0A0h]
0x180001d90  shl     eax, cl
0x180001d92  or      r13d, eax
0x180001d95  movzx   eax, byte ptr [rdx+r8+2EF80h]
0x180001d9e  add     r9d, eax
0x180001da1  mov     dword ptr [rsp+0A8h+arg_0], r9d
0x180001da9  cmp     r9d, 10h
0x180001dad  jl      short loc_180001DD5
0x180001daf  mov     [r10], r13b
0x180001db2  mov     eax, r13d
0x180001db5  shr     eax, 8
0x180001db8  mov     [r10+1], al
0x180001dbc  add     r10, 2
0x180001dc0  shr     r13d, 10h
0x180001dc4  add     r9d, 0FFFFFFF0h
0x180001dc8  mov     [rsp+0A8h+var_58], r10
0x180001dcd  mov     dword ptr [rsp+0A8h+arg_0], r9d
0x180001dd5  inc     ebx
0x180001dd7  cmp     dword ptr [rbp+1Ch], 0FFF2h
0x180001dde  mov     r10, [rsp+0A8h+var_58]
0x180001de3  jnb     short loc_180001DF1
0x180001de5  lea     rax, [r14+2C302h]
0x180001dec  cmp     r10, rax
0x180001def  jb      short loc_180001E3B
0x180001df1  mov     [r10], r13b
0x180001df4  mov     eax, r13d
0x180001df7  shr     eax, 8
0x180001dfa  mov     rcx, rbp
0x180001dfd  mov     [r10+1], al
0x180001e01  add     r10, 2
0x180001e05  mov     [rsp+0A8h+var_58], r10
0x180001e0a  call    StdEncoderOutputBlock
0x180001e0f  cmp     dword ptr [rbp+0], 0
0x180001e13  jnz     loc_180002505
0x180001e19  mov     r10, [r14+2C318h]
0x180001e20  mov     r9d, [r14+2C310h]
0x180001e27  mov     r13d, [r14+2C30Ch]
0x180001e2e  mov     [rsp+0A8h+var_58], r10
0x180001e33  mov     dword ptr [rsp+0A8h+arg_0], r9d
0x180001e3b  mov     eax, [rbp+24h]
0x180001e3e  mov     r8d, [rsp+0A8h+arg_8]
0x180001e46  cmp     ebx, eax
0x180001e48  jl      loc_180001CC0
0x180001e4e  jmp     loc_18000250A
0x180001e53  lea     edx, [rbx+1]
0x180001e56  mov     [rsp+0A8h+var_60], rdx
0x180001e5b  cmp     esi, [rsp+0A8h+arg_10]
0x180001e62  jg      loc_1800022F2
0x180001e68  movzx   eax, byte ptr [r12+3]
0x180001e6e  shl     edi, 5
0x180001e71  xor     eax, edi
0x180001e73  mov     [rsp+0A8h+var_64], 0
0x180001e7b  mov     edi, eax
0x180001e7d  and     eax, 1FFFh
0x180001e82  movzx   r8d, word ptr [r14+rax*2+2030Ah]
0x180001e8b  mov     [r14+rax*2+2030Ah], dx
0x180001e94  mov     eax, edx
0x180001e96  and     eax, 7FFFh
0x180001e9b  mov     [r14+rax*2+10106h], r8w
0x180001ea4  test    r8w, r8w
0x180001ea8  jz      loc_18000213F
0x180001eae  mov     ecx, [rsp+0A8h+arg_8]
0x180001eb5  mov     r9d, r8d
0x180001eb8  mov     eax, ecx
0x180001eba  mov     r8d, edx
0x180001ebd  sar     eax, 2
0x180001ec0  lea     rdx, [r14+10106h]
0x180001ec7  cmp     esi, [rsp+0A8h+arg_18]
0x180001ece  cmovge  ecx, eax
0x180001ed1  mov     eax, [rsp+0A8h+arg_20]
0x180001ed8  mov     [rsp+0A8h+var_78], eax
0x180001edc  lea     rax, [rsp+0A8h+var_64]
0x180001ee1  mov     [rsp+0A8h+var_80], ecx
0x180001ee5  mov     rcx, r14
0x180001ee8  mov     [rsp+0A8h+var_88], rax
0x180001eed  call    StdEncoderFindMatch
0x180001ef2  mov     edx, [rbp+24h]
0x180001ef5  mov     r11d, eax
0x180001ef8  sub     edx, dword ptr [rsp+0A8h+var_60]
0x180001efc  lea     ecx, [rax+1]
0x180001eff  add     ecx, ebx
0x180001f01  cmp     ecx, [rbp+24h]
0x180001f04  cmovg   r11d, edx
0x180001f08  mov     dword ptr [rsp+0A8h+var_60], r11d
0x180001f0d  cmp     r11d, esi
0x180001f10  jle     loc_18000213F
0x180001f16  lfence
0x180001f19  inc     dword ptr [rbp+1Ch]
0x180001f1c  movzx   ecx, byte ptr [r12]
0x180001f21  mov     rax, [rbp+50h]
0x180001f25  inc     word ptr [rax+rcx*2+2F2E0h]
0x180001f2d  movzx   eax, byte ptr [r12]
0x180001f32  mov     r8, [rbp+50h]
0x180001f36  mov     ecx, dword ptr [rsp+0A8h+arg_0]
0x180001f3d  movzx   r9d, word ptr [r8+rax*2+2F0A0h]
0x180001f46  movzx   r10d, byte ptr [r8+rax+2EF80h]
0x180001f4f  shl     r9d, cl
0x180001f52  add     r10d, ecx
0x180001f55  or      r9d, r13d
0x180001f58  cmp     r10d, 10h
0x180001f5c  jl      short loc_180001F86
0x180001f5e  mov     r13, [rsp+0A8h+var_58]
0x180001f63  mov     eax, r9d
0x180001f66  shr     eax, 8
0x180001f69  mov     [r13+0], r9b
0x180001f6d  mov     [r13+1], al
0x180001f71  add     r13, 2
0x180001f75  mov     r8, [rbp+50h]
0x180001f79  shr     r9d, 10h
0x180001f7d  mov     [rsp+0A8h+var_58], r13
0x180001f82  add     r10d, 0FFFFFFF0h
0x180001f86  mov     ecx, [rsp+0A8h+var_64]
0x180001f8a  lea     rdx, cs:180000000h
0x180001f91  mov     eax, ecx
0x180001f93  shr     eax, 7
0x180001f96  add     eax, 100h
0x180001f9b  cmp     ecx, 100h
0x180001fa1  cmovb   eax, ecx
0x180001fa4  inc     dword ptr [rbp+1Ch]
0x180001fa7  movzx   r13d, byte ptr [rax+rdx+0AB20h]
0x180001fb0  movsxd  rax, r11d
0x180001fb3  mov     [rsp+0A8h+arg_0], r13
0x180001fbb  movzx   r12d, ds:rva g_ExtraDistanceBits[rdx+r13]
0x180001fc4  movzx   ecx, byte ptr [rax+rdx+0AD1Dh]
0x180001fcc  inc     word ptr [r8+rcx*2+2F4E2h]
0x180001fd5  mov     rax, [rbp+50h]
0x180001fd9  movzx   r11d, byte ptr [rcx+rdx+7940h]
0x180001fe2  lea     rdx, [rcx+101h]
0x180001fe9  mov     ecx, r10d
0x180001fec  inc     word ptr [rax+r13*2+2FAC0h]
0x180001ff5  mov     rax, [rbp+50h]
0x180001ff9  movzx   r8d, word ptr [rax+rdx*2+2F0A0h]
0x180002002  shl     r8d, cl
0x180002005  or      r8d, r9d
0x180002008  movzx   r9d, byte ptr [rax+rdx+2EF80h]
0x180002011  add     r9d, r10d
0x180002014  mov     r10, [rsp+0A8h+var_58]
0x180002019  cmp     r9d, 10h
0x18000201d  jl      short loc_18000203D
0x18000201f  mov     [r10], r8b
0x180002022  mov     eax, r8d
0x180002025  shr     eax, 8
0x180002028  mov     [r10+1], al
0x18000202c  add     r10, 2
0x180002030  shr     r8d, 10h
0x180002034  mov     [rsp+0A8h+var_58], r10
0x180002039  add     r9d, 0FFFFFFF0h
0x18000203d  mov     esi, dword ptr [rsp+0A8h+var_60]
0x180002041  test    r11d, r11d
0x180002044  jz      short loc_180002086
0x180002046  mov     ecx, r11d
0x180002049  lea     eax, [rsi-3]
0x18000204c  mov     edx, 1
0x180002051  shl     edx, cl
0x180002053  mov     ecx, r9d
0x180002056  dec     edx
0x180002058  add     r9d, r11d
0x18000205b  and     edx, eax
0x18000205d  shl     edx, cl
0x18000205f  or      r8d, edx
0x180002062  cmp     r9d, 10h
0x180002066  jl      short loc_180002086
0x180002068  mov     [r10], r8b
0x18000206b  mov     eax, r8d
0x18000206e  shr     eax, 8
0x180002071  mov     [r10+1], al
0x180002075  add     r10, 2
0x180002079  shr     r8d, 10h
0x18000207d  mov     [rsp+0A8h+var_58], r10
0x180002082  add     r9d, 0FFFFFFF0h
0x180002086  mov     rax, [rbp+50h]
0x18000208a  mov     ecx, r9d
0x18000208d  movzx   r13d, word ptr [rax+r13*2+2C640h]
0x180002096  shl     r13d, cl
0x180002099  mov     rcx, [rsp+0A8h+arg_0]
0x1800020a1  or      r13d, r8d
0x1800020a4  movzx   eax, byte ptr [rcx+rax+2C620h]
0x1800020ac  add     r9d, eax
0x1800020af  mov     dword ptr [rsp+0A8h+arg_0], r9d
0x1800020b7  cmp     r9d, 10h
0x1800020bb  jl      short loc_1800020E3
0x1800020bd  mov     [r10], r13b
0x1800020c0  mov     eax, r13d
0x1800020c3  shr     eax, 8
0x1800020c6  mov     [r10+1], al
0x1800020ca  add     r10, 2
0x1800020ce  shr     r13d, 10h
0x1800020d2  add     r9d, 0FFFFFFF0h
0x1800020d6  mov     [rsp+0A8h+var_58], r10
0x1800020db  mov     dword ptr [rsp+0A8h+arg_0], r9d
0x1800020e3  test    r12d, r12d
0x1800020e6  jz      short loc_180002137
0x1800020e8  mov     ecx, r12d
0x1800020eb  mov     eax, 1
0x1800020f0  shl     eax, cl
0x1800020f2  mov     ecx, r9d
0x1800020f5  dec     eax
0x1800020f7  add     r9d, r12d
0x1800020fa  and     eax, [rsp+0A8h+var_64]
0x1800020fe  shl     eax, cl
0x180002100  or      eax, r13d
0x180002103  mov     dword ptr [rsp+0A8h+arg_0], r9d
0x18000210b  mov     r13d, eax
0x18000210e  cmp     r9d, 10h
0x180002112  jl      short loc_180002137
0x180002114  mov     [r10], r13b
0x180002117  shr     eax, 8
0x18000211a  mov     [r10+1], al
0x18000211e  add     r10, 2
0x180002122  shr     r13d, 10h
0x180002126  add     r9d, 0FFFFFFF0h
0x18000212a  mov     [rsp+0A8h+var_58], r10
0x18000212f  mov     dword ptr [rsp+0A8h+arg_0], r9d
0x180002137  add     ebx, 2
0x18000213a  jmp     loc_1800024A6
0x18000213f  lfence
0x180002142  mov     ecx, [rsp+0A8h+var_68]
0x180002146  lea     rdx, cs:180000000h
0x18000214d  mov     eax, ecx
0x18000214f  shr     eax, 7
0x180002152  add     eax, 100h
0x180002157  cmp     ecx, 100h
0x18000215d  cmovb   eax, ecx
0x180002160  inc     dword ptr [rbp+1Ch]
0x180002163  movzx   r12d, byte ptr [rax+rdx+0AB20h]
  ... truncated ...
```
