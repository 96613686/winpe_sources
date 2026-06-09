# sl_uncompress_tcp

- ea: `0x14002eed4`
- end: `0x14002f612`
- name: `sl_uncompress_tcp`
- size: `1854`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002cf98`

## callees

- `0x14000a290`
- `0x14000a2c0`
- `0x14000a5f4`
- `0x140016400`
- `0x14002eed4`

## pseudocode

```c
__int64 __fastcall sl_uncompress_tcp(char **a1, int *a2, _WORD *a3, _DWORD *a4, unsigned __int8 a5, __int64 a6)
{
  __int64 v6; // r9
  unsigned int v8; // r14d
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 result; // rax
  char *v13; // r13
  __int64 v14; // rdx
  __int64 v15; // r9
  unsigned int v16; // ecx
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r15
  __int64 v20; // rsi
  __int64 v21; // rbx
  char v22; // r10
  char *v23; // rbx
  char v24; // al
  __int64 v25; // rdi
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r15
  char v29; // cl
  unsigned __int8 v30; // al
  char *v31; // rbx
  char v32; // r8
  int v33; // eax
  __int16 v34; // ax
  __int16 v35; // dx
  __int16 v36; // ax
  __int16 v37; // r8
  int v38; // eax
  unsigned __int32 v39; // edx
  int v40; // eax
  unsigned __int32 v41; // edx
  int v42; // ecx
  int v43; // r8d
  int v44; // edx
  int v45; // ecx
  int v46; // ecx
  int v47; // eax
  int v48; // edx
  __int16 v49; // ax
  __int16 v50; // r8
  __int16 v51; // dx
  __int16 v52; // dx
  int v53; // r14d
  size_t v54; // r8
  unsigned __int16 *v55; // rcx
  int i; // edx
  int v57; // eax

  v6 = a5;
  v8 = *a2;
  if ( !a5 )
    goto LABEL_5;
  if ( a5 != 64 )
  {
    if ( a5 == 112 )
    {
      v13 = *a1;
      v14 = (unsigned __int8)(*a1)[9];
      if ( (unsigned __int8)v14 >= *(_BYTE *)(a6 + 12) )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        {
          goto LABEL_10;
        }
        v6 = (unsigned int)v14;
        v11 = 12;
LABEL_9:
        WPP_SF_d(v10->AttachedDevice, v11, WPP_902a8e7b50ad32c775796f1fa3c8f679_Traceguids, v6);
LABEL_10:
        *(_WORD *)(a6 + 10) |= 1u;
        ++*(_DWORD *)(a6 + 40);
        return 0;
      }
      *(_BYTE *)(a6 + 8) = v14;
      *(_WORD *)(a6 + 10) &= ~1u;
      v15 = *v13 & 0xF;
      if ( 4 * (int)v15 > v8 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        {
          goto LABEL_10;
        }
        v18 = 13;
      }
      else
      {
        v16 = (unsigned __int8)v13[4 * v15 + 12] >> 4;
        if ( v16 + (unsigned int)v15 >= v16 )
        {
          v19 = 4 * (v16 + (unsigned int)v15);
          if ( (unsigned int)v19 <= v8 )
          {
            v20 = 18 * v14;
            v21 = 144 * v14;
            memmove((void *)(144 * v14 + a6 + 2364), v13, (unsigned int)v19);
            *(_BYTE *)(a6 + 8 * v20 + 2373) = 6;
            memmove(a3, (const void *)(v21 + a6 + 2364), (unsigned int)v19);
            *(_WORD *)(a6 + 8 * v20 + 2374) = 0;
            *(_WORD *)(a6 + 8 * v20 + 2360) = v19;
            *a1 = &v13[v19];
            *a2 = v8 - v19;
            result = v8;
            *a4 = v19;
            ++*(_DWORD *)(a6 + 32);
            return result;
          }
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
          {
            goto LABEL_10;
          }
          v18 = 16;
          v15 = (unsigned int)v19;
        }
        else
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
          {
            goto LABEL_10;
          }
          v18 = 14;
          v15 = 0xFFFFFFFFLL;
        }
      }
      WPP_SF_dd(v17->AttachedDevice, v18, WPP_902a8e7b50ad32c775796f1fa3c8f679_Traceguids, v15, v8);
      goto LABEL_10;
    }
    if ( a5 != 128 )
    {
LABEL_5:
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        goto LABEL_10;
      }
      v11 = 11;
      goto LABEL_9;
    }
  }
  ++*(_DWORD *)(a6 + 36);
  v22 = **a1;
  v23 = *a1 + 1;
  if ( (v22 & 0x40) != 0 )
  {
    if ( (unsigned __int8)*v23 >= *(_BYTE *)(a6 + 12) )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        goto LABEL_10;
      }
      v6 = (unsigned __int8)*v23;
      v11 = 18;
      goto LABEL_9;
    }
    *(_WORD *)(a6 + 10) &= ~1u;
    v24 = *v23++;
    *(_BYTE *)(a6 + 8) = v24;
  }
  else if ( (*(_BYTE *)(a6 + 10) & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_902a8e7b50ad32c775796f1fa3c8f679_Traceguids);
    }
    ++*(_DWORD *)(a6 + 44);
    return 0;
  }
  v25 = a6 + 144LL * *(unsigned __int8 *)(a6 + 8) + 2352;
  if ( !*(_WORD *)(v25 + 8) )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      goto LABEL_10;
    }
    v27 = 20;
    goto LABEL_46;
  }
  v28 = 4 * (*(_BYTE *)(v25 + 12) & 0xFu);
  v29 = *(_BYTE *)(v28 + v25 + 25);
  *(_BYTE *)(v28 + v25 + 28) = *v23;
  v30 = v23[1];
  v31 = v23 + 2;
  *(_BYTE *)(v28 + v25 + 29) = v30;
  v32 = v29 | 8;
  if ( (v22 & 0x10) == 0 )
    v32 = v29 & 0xF7;
  v33 = v22 & 0xF;
  *(_BYTE *)(v28 + v25 + 25) = v32;
  if ( v33 == 11 )
  {
    v43 = *(unsigned __int8 *)(v25 + 15) + (*(unsigned __int8 *)(v25 + 14) << 8) - *(unsigned __int16 *)(v25 + 8);
    v44 = *(unsigned __int8 *)(v28 + v25 + 23)
        + v43
        + (*(unsigned __int8 *)(v28 + v25 + 21) << 16)
        + (*(unsigned __int8 *)(v28 + v25 + 20) << 24)
        + (*(unsigned __int8 *)(v28 + v25 + 22) << 8);
    v45 = *(unsigned __int8 *)(v28 + v25 + 18) << 8;
    *(_BYTE *)(v28 + v25 + 23) += *(_BYTE *)(v25 + 15) - *(_WORD *)(v25 + 8);
    v46 = v43 + v45;
    *(_BYTE *)(v28 + v25 + 22) = BYTE1(v44);
    *(_BYTE *)(v28 + v25 + 21) = BYTE2(v44);
    v47 = *(unsigned __int8 *)(v28 + v25 + 16) << 24;
    *(_BYTE *)(v28 + v25 + 20) = HIBYTE(v44);
    v48 = *(unsigned __int8 *)(v28 + v25 + 19) + v46 + v47 + (*(unsigned __int8 *)(v28 + v25 + 17) << 16);
    *(_BYTE *)(v28 + v25 + 19) += v46 + v47;
    *(_BYTE *)(v28 + v25 + 18) = BYTE1(v48);
    *(_BYTE *)(v28 + v25 + 16) = HIBYTE(v48);
    *(_BYTE *)(v28 + v25 + 17) = BYTE2(v48);
  }
  else if ( v33 == 15 )
  {
    v42 = *(unsigned __int8 *)(v28 + v25 + 19)
        + *(unsigned __int8 *)(v25 + 15)
        + (*(unsigned __int8 *)(v28 + v25 + 18) << 8)
        + (*(unsigned __int8 *)(v25 + 14) << 8)
        + (*(unsigned __int8 *)(v28 + v25 + 16) << 24)
        + (*(unsigned __int8 *)(v28 + v25 + 17) << 16)
        - *(unsigned __int16 *)(v25 + 8);
    *(_BYTE *)(v28 + v25 + 19) += *(_BYTE *)(v25 + 15) - *(_WORD *)(v25 + 8);
    *(_BYTE *)(v28 + v25 + 18) = BYTE1(v42);
    *(_BYTE *)(v28 + v25 + 16) = HIBYTE(v42);
    *(_BYTE *)(v28 + v25 + 17) = BYTE2(v42);
  }
  else
  {
    if ( (v22 & 1) != 0 )
    {
      *(_BYTE *)(v28 + v25 + 25) = v32 | 0x20;
      v34 = (unsigned __int8)*v31;
      if ( (_BYTE)v34 )
      {
        ++v31;
        v35 = v34;
      }
      else
      {
        v35 = (unsigned __int8)v31[2] + ((unsigned __int8)v31[1] << 8);
        v31 += 3;
      }
      *(_WORD *)(v28 + v25 + 30) = __ROR2__(v35, 8);
    }
    else
    {
      *(_BYTE *)(v28 + v25 + 25) = v32 & 0xDF;
    }
    if ( (v22 & 2) != 0 )
    {
      v36 = (unsigned __int8)*v31;
      v37 = __ROR2__(*(_WORD *)(v28 + v25 + 26), 8);
      if ( (_BYTE)v36 )
      {
        *(_WORD *)(v28 + v25 + 26) = __ROR2__(v37 + v36, 8);
        ++v31;
      }
      else
      {
        *(_WORD *)(v28 + v25 + 26) = __ROR2__(v37 + (unsigned __int8)v31[2] + ((unsigned __int8)v31[1] << 8), 8);
        v31 += 3;
      }
    }
    if ( (v22 & 4) != 0 )
    {
      v38 = (unsigned __int8)*v31;
      v39 = _byteswap_ulong(*(_DWORD *)(v28 + v25 + 20));
      if ( (_BYTE)v38 )
      {
        *(_DWORD *)(v28 + v25 + 20) = _byteswap_ulong(v39 + v38);
        ++v31;
      }
      else
      {
        *(_DWORD *)(v28 + v25 + 20) = _byteswap_ulong(v39 + ((unsigned __int8)v31[1] << 8) + (unsigned __int8)v31[2]);
        v31 += 3;
      }
    }
    if ( (v22 & 8) != 0 )
    {
      v40 = (unsigned __int8)*v31;
      v41 = _byteswap_ulong(*(_DWORD *)(v28 + v25 + 16));
      if ( (_BYTE)v40 )
      {
        *(_DWORD *)(v28 + v25 + 16) = _byteswap_ulong(v41 + v40);
        ++v31;
      }
      else
      {
        *(_DWORD *)(v28 + v25 + 16) = _byteswap_ulong(v41 + ((unsigned __int8)v31[1] << 8) + (unsigned __int8)v31[2]);
        v31 += 3;
      }
    }
  }
  if ( (v22 & 0x20) != 0 )
  {
    v49 = (unsigned __int8)*v31;
    v50 = __ROR2__(*(_WORD *)(v25 + 16), 8);
    if ( (_BYTE)v49 )
    {
      ++v31;
      v51 = v50 + v49;
    }
    else
    {
      v51 = v50 + (unsigned __int8)v31[2] + ((unsigned __int8)v31[1] << 8);
      v31 += 3;
    }
    *(_WORD *)(v25 + 16) = __ROR2__(v51, 8);
  }
  else
  {
    v52 = (unsigned __int8)(*(_BYTE *)(v25 + 17))++ + (*(unsigned __int8 *)(v25 + 16) << 8) + 1;
    *(_BYTE *)(v25 + 16) = HIBYTE(v52);
  }
  v53 = *(_DWORD *)a1 - (_DWORD)v31 + v8;
  if ( v53 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      goto LABEL_10;
    }
    v27 = 21;
LABEL_46:
    WPP_SF_(v26->AttachedDevice, v27, WPP_902a8e7b50ad32c775796f1fa3c8f679_Traceguids);
    goto LABEL_10;
  }
  v54 = *(unsigned __int16 *)(v25 + 8);
  *(_WORD *)(v25 + 14) = __ROR2__(v54 + v53, 8);
  memmove(a3, (const void *)(v25 + 12), v54);
  *a1 = v31;
  *a2 = v53;
  *a4 = *(unsigned __int16 *)(v25 + 8);
  v55 = a3;
  for ( i = 0; (_DWORD)v28; LODWORD(v28) = v28 - 2 )
  {
    v57 = *v55++;
    i += v57;
  }
  a3[5] = ~(HIWORD(i) + i + (((i >> 16) + (unsigned int)(unsigned __int16)i) >> 16));
  return v53 + (unsigned int)*(unsigned __int16 *)(v25 + 8);
}

```

## disassembly

```asm
0x14002eed4  mov     rax, rsp
0x14002eed7  mov     [rax+8], rbx
0x14002eedb  mov     [rax+20h], r9
0x14002eedf  mov     [rax+18h], r8
0x14002eee3  mov     [rax+10h], rdx
0x14002eee7  push    rbp
0x14002eee8  push    rsi
0x14002eee9  push    rdi
0x14002eeea  push    r12
0x14002eeec  push    r13
0x14002eeee  push    r14
0x14002eef0  push    r15
0x14002eef2  sub     rsp, 30h
0x14002eef6  movzx   r9d, [rsp+68h+arg_20]
0x14002eeff  mov     r13, r8
0x14002ef02  mov     r14d, [rdx]
0x14002ef05  mov     r12, rcx
0x14002ef08  mov     rbp, [rsp+68h+arg_28]
0x14002ef10  xor     edx, edx
0x14002ef12  mov     r10d, r9d
0x14002ef15  mov     esi, 1
0x14002ef1a  test    r9d, r9d
0x14002ef1d  jz      short loc_14002EF39
0x14002ef1f  sub     r10d, 40h ; '@'
0x14002ef23  jz      loc_14002F14C
0x14002ef29  sub     r10d, 30h ; '0'
0x14002ef2d  jz      short loc_14002EF8D
0x14002ef2f  cmp     r10d, 10h
0x14002ef33  jz      loc_14002F14C
0x14002ef39  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ef40  lea     rax, WPP_GLOBAL_Control
0x14002ef47  cmp     rcx, rax
0x14002ef4a  jz      short loc_14002EF6E
0x14002ef4c  mov     eax, [rcx+2Ch]
0x14002ef4f  test    al, al
0x14002ef51  jns     short loc_14002EF6E
0x14002ef53  cmp     byte ptr [rcx+29h], 3
0x14002ef57  jb      short loc_14002EF6E
0x14002ef59  mov     edx, 0Bh
0x14002ef5e  mov     rcx, [rcx+18h]
0x14002ef62  lea     r8, WPP_902a8e7b50ad32c775796f1fa3c8f679_Traceguids
0x14002ef69  call    WPP_SF_d
0x14002ef6e  or      [rbp+0Ah], si
0x14002ef72  add     [rbp+28h], esi
0x14002ef75  xor     eax, eax
0x14002ef77  mov     rbx, [rsp+68h+arg_0]
0x14002ef7c  add     rsp, 30h
0x14002ef80  pop     r15
0x14002ef82  pop     r14
0x14002ef84  pop     r13
0x14002ef86  pop     r12
0x14002ef88  pop     rdi
0x14002ef89  pop     rsi
0x14002ef8a  pop     rbp
0x14002ef8b  retn
0x14002ef8d  mov     r13, [rcx]
0x14002ef90  movzx   edx, byte ptr [r13+9]
0x14002ef95  cmp     dl, [rbp+0Ch]
0x14002ef98  jb      short loc_14002EFC4
0x14002ef9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002efa1  lea     rax, WPP_GLOBAL_Control
0x14002efa8  cmp     rcx, rax
0x14002efab  jz      short loc_14002EF6E
0x14002efad  mov     eax, [rcx+2Ch]
0x14002efb0  test    al, al
0x14002efb2  jns     short loc_14002EF6E
0x14002efb4  cmp     byte ptr [rcx+29h], 3
0x14002efb8  jb      short loc_14002EF6E
0x14002efba  mov     r9d, edx
0x14002efbd  mov     edx, 0Ch
0x14002efc2  jmp     short loc_14002EF5E
0x14002efc4  mov     eax, 0FFFEh
0x14002efc9  mov     [rbp+8], dl
0x14002efcc  and     [rbp+0Ah], ax
0x14002efd0  movzx   r9d, byte ptr [r13+0]
0x14002efd5  and     r9d, 0Fh
0x14002efd9  lea     eax, ds:0[r9*4]
0x14002efe1  cmp     eax, r14d
0x14002efe4  ja      loc_14002F101
0x14002efea  movzx   ecx, byte ptr [r13+r9*4+0Ch]
0x14002eff0  shr     ecx, 4
0x14002eff3  lea     r15d, [rcx+r9]
0x14002eff7  cmp     r15d, ecx
0x14002effa  jnb     short loc_14002F036
0x14002effc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f003  lea     rax, WPP_GLOBAL_Control
0x14002f00a  cmp     rcx, rax
0x14002f00d  jz      loc_14002EF6E
0x14002f013  mov     eax, [rcx+2Ch]
0x14002f016  test    al, al
0x14002f018  jns     loc_14002EF6E
0x14002f01e  cmp     byte ptr [rcx+29h], 3
0x14002f022  jb      loc_14002EF6E
0x14002f028  mov     edx, 0Eh
0x14002f02d  or      r9d, 0FFFFFFFFh
0x14002f031  jmp     loc_14002F132
0x14002f036  shl     r15d, 2
0x14002f03a  cmp     r15d, r14d
0x14002f03d  jbe     short loc_14002F078
0x14002f03f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f046  lea     rax, WPP_GLOBAL_Control
0x14002f04d  cmp     rcx, rax
0x14002f050  jz      loc_14002EF6E
0x14002f056  mov     eax, [rcx+2Ch]
0x14002f059  test    al, al
0x14002f05b  jns     loc_14002EF6E
0x14002f061  cmp     byte ptr [rcx+29h], 3
0x14002f065  jb      loc_14002EF6E
0x14002f06b  mov     edx, 10h
0x14002f070  mov     r9d, r15d
0x14002f073  jmp     loc_14002F132
0x14002f078  lea     rsi, [rdx+rdx*8]
0x14002f07c  mov     r8d, r15d; Size
0x14002f07f  add     rsi, rsi
0x14002f082  lea     rcx, [rbp+93Ch]
0x14002f089  mov     rdx, r13; Src
0x14002f08c  lea     rbx, ds:0[rsi*8]
0x14002f094  add     rcx, rbx; void *
0x14002f097  call    memmove
0x14002f09c  mov     rcx, [rsp+68h+arg_10]; void *
0x14002f0a4  lea     rdx, [rbp+93Ch]
0x14002f0ab  add     rdx, rbx; Src
0x14002f0ae  mov     r8d, r15d; Size
0x14002f0b1  mov     byte ptr [rbp+rsi*8+945h], 6
0x14002f0b9  call    memmove
0x14002f0be  xor     ecx, ecx
0x14002f0c0  mov     [rbp+rsi*8+946h], cx
0x14002f0c8  lea     rcx, [r15+r13]
0x14002f0cc  mov     [rbp+rsi*8+938h], r15w
0x14002f0d5  mov     esi, 1
0x14002f0da  mov     rax, [rsp+68h+arg_8]
0x14002f0df  mov     [r12], rcx
0x14002f0e3  mov     ecx, r14d
0x14002f0e6  sub     ecx, r15d
0x14002f0e9  mov     [rax], ecx
0x14002f0eb  mov     eax, r14d
0x14002f0ee  mov     rcx, [rsp+68h+arg_18]
0x14002f0f6  mov     [rcx], r15d
0x14002f0f9  add     [rbp+20h], esi
0x14002f0fc  jmp     loc_14002EF77
0x14002f101  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f108  lea     rax, WPP_GLOBAL_Control
0x14002f10f  cmp     rcx, rax
0x14002f112  jz      loc_14002EF6E
0x14002f118  mov     eax, [rcx+2Ch]
0x14002f11b  test    al, al
0x14002f11d  jns     loc_14002EF6E
0x14002f123  cmp     byte ptr [rcx+29h], 3
0x14002f127  jb      loc_14002EF6E
0x14002f12d  mov     edx, 0Dh
0x14002f132  mov     rcx, [rcx+18h]
0x14002f136  lea     r8, WPP_902a8e7b50ad32c775796f1fa3c8f679_Traceguids
0x14002f13d  mov     [rsp+68h+var_48], r14d
0x14002f142  call    WPP_SF_dd
0x14002f147  jmp     loc_14002EF6E
0x14002f14c  add     [rbp+24h], esi
0x14002f14f  mov     rax, [rcx]
0x14002f152  movzx   r10d, byte ptr [rax]
0x14002f156  lea     rbx, [rax+1]
0x14002f15a  test    r10b, 40h
0x14002f15e  jz      loc_14002F21C
0x14002f164  mov     al, [rbp+0Ch]
0x14002f167  cmp     [rbx], al
0x14002f169  jb      short loc_14002F1A5
0x14002f16b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f172  lea     rax, WPP_GLOBAL_Control
0x14002f179  cmp     rcx, rax
0x14002f17c  jz      loc_14002EF6E
0x14002f182  mov     eax, [rcx+2Ch]
0x14002f185  test    al, al
0x14002f187  jns     loc_14002EF6E
0x14002f18d  cmp     byte ptr [rcx+29h], 3
0x14002f191  jb      loc_14002EF6E
0x14002f197  movzx   r9d, byte ptr [rbx]
0x14002f19b  mov     edx, 12h
0x14002f1a0  jmp     loc_14002EF5E
0x14002f1a5  mov     eax, 0FFFEh
0x14002f1aa  and     [rbp+0Ah], ax
0x14002f1ae  mov     al, [rbx]
0x14002f1b0  inc     rbx
0x14002f1b3  mov     [rbp+8], al
0x14002f1b6  movzx   eax, byte ptr [rbp+8]
0x14002f1ba  lea     rdi, [rax+rax*8]
0x14002f1be  shl     rdi, 4
0x14002f1c2  add     rdi, 930h
0x14002f1c9  add     rdi, rbp
0x14002f1cc  cmp     [rdi+8], dx
0x14002f1d0  jnz     loc_14002F25F
0x14002f1d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f1dd  lea     rax, WPP_GLOBAL_Control
0x14002f1e4  cmp     rcx, rax
0x14002f1e7  jz      loc_14002EF6E
0x14002f1ed  mov     eax, [rcx+2Ch]
0x14002f1f0  test    al, al
0x14002f1f2  jns     loc_14002EF6E
0x14002f1f8  cmp     byte ptr [rcx+29h], 3
0x14002f1fc  jb      loc_14002EF6E
0x14002f202  mov     edx, 14h
0x14002f207  mov     rcx, [rcx+18h]
0x14002f20b  lea     r8, WPP_902a8e7b50ad32c775796f1fa3c8f679_Traceguids
0x14002f212  call    WPP_SF_
0x14002f217  jmp     loc_14002EF6E
0x14002f21c  test    [rbp+0Ah], sil
0x14002f220  jz      short loc_14002F1B6
0x14002f222  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f229  lea     rax, WPP_GLOBAL_Control
0x14002f230  cmp     rcx, rax
0x14002f233  jz      short loc_14002F257
0x14002f235  mov     eax, [rcx+2Ch]
0x14002f238  test    al, al
0x14002f23a  jns     short loc_14002F257
0x14002f23c  cmp     byte ptr [rcx+29h], 3
0x14002f240  jb      short loc_14002F257
0x14002f242  mov     rcx, [rcx+18h]
0x14002f246  lea     r8, WPP_902a8e7b50ad32c775796f1fa3c8f679_Traceguids
0x14002f24d  mov     edx, 13h
0x14002f252  call    WPP_SF_
0x14002f257  add     [rbp+2Ch], esi
0x14002f25a  jmp     loc_14002EF75
0x14002f25f  mov     al, [rbx]
0x14002f261  mov     edx, 100h
0x14002f266  movzx   r15d, byte ptr [rdi+0Ch]
0x14002f26b  and     r15d, 0Fh
0x14002f26f  shl     r15d, 2
0x14002f273  mov     cl, [r15+rdi+19h]
0x14002f278  mov     [r15+rdi+1Ch], al
0x14002f27d  mov     al, [rbx+1]
0x14002f280  add     rbx, 2
0x14002f284  mov     [r15+rdi+1Dh], al
0x14002f289  mov     al, cl
0x14002f28b  and     al, 0F7h
0x14002f28d  or      cl, 8
0x14002f290  movzx   eax, al
0x14002f293  test    r10b, 10h
0x14002f297  movzx   r8d, cl
0x14002f29b  cmovz   r8d, eax
0x14002f29f  mov     eax, r10d
0x14002f2a2  and     eax, 0Fh
0x14002f2a5  mov     [r15+rdi+19h], r8b
0x14002f2aa  cmp     eax, 0Bh
0x14002f2ad  jz      loc_14002F43F
0x14002f2b3  cmp     eax, 0Fh
0x14002f2b6  jz      loc_14002F3DD
0x14002f2bc  test    sil, r10b
0x14002f2bf  jz      short loc_14002F300
0x14002f2c1  or      r8b, 20h
0x14002f2c5  mov     [r15+rdi+19h], r8b
0x14002f2ca  movzx   eax, byte ptr [rbx]
0x14002f2cd  test    al, al
0x14002f2cf  jnz     short loc_14002F2E9
0x14002f2d1  movzx   eax, byte ptr [rbx+1]
0x14002f2d5  mov     ecx, edx
0x14002f2d7  mov     edx, eax
0x14002f2d9  movzx   eax, byte ptr [rbx+2]
0x14002f2dd  imul    edx, ecx
0x14002f2e0  add     dx, ax
0x14002f2e3  add     rbx, 3
0x14002f2e7  jmp     short loc_14002F2EF
0x14002f2e9  add     rbx, rsi
0x14002f2ec  movzx   edx, ax
0x14002f2ef  ror     dx, 8
0x14002f2f3  mov     [r15+rdi+1Eh], dx
0x14002f2f9  mov     edx, 100h
0x14002f2fe  jmp     short loc_14002F309
0x14002f300  and     r8b, 0DFh
0x14002f304  mov     [r15+rdi+19h], r8b
0x14002f309  test    r10b, 2
0x14002f30d  jz      short loc_14002F359
0x14002f30f  movzx   r8d, word ptr [r15+rdi+1Ah]
0x14002f315  movzx   eax, byte ptr [rbx]
0x14002f318  ror     r8w, 8
0x14002f31d  test    al, al
0x14002f31f  jnz     short loc_14002F348
0x14002f321  movzx   eax, byte ptr [rbx+1]
0x14002f325  movzx   ecx, dx
0x14002f328  mov     edx, eax
0x14002f32a  movzx   eax, byte ptr [rbx+2]
0x14002f32e  imul    edx, ecx
0x14002f331  add     dx, ax
0x14002f334  add     dx, r8w
0x14002f338  ror     dx, 8
0x14002f33c  mov     [r15+rdi+1Ah], dx
0x14002f342  add     rbx, 3
0x14002f346  jmp     short loc_14002F359
0x14002f348  add     ax, r8w
0x14002f34c  ror     ax, 8
0x14002f350  mov     [r15+rdi+1Ah], ax
0x14002f356  add     rbx, rsi
0x14002f359  test    r10b, 4
0x14002f35d  jz      short loc_14002F395
0x14002f35f  movzx   eax, byte ptr [rbx]
0x14002f362  mov     edx, [r15+rdi+14h]
0x14002f367  bswap   edx
0x14002f369  test    al, al
0x14002f36b  jnz     short loc_14002F389
0x14002f36d  movzx   eax, byte ptr [rbx+1]
0x14002f371  movzx   ecx, byte ptr [rbx+2]
0x14002f375  shl     eax, 8
0x14002f378  add     eax, edx
0x14002f37a  add     ecx, eax
  ... truncated ...
```
