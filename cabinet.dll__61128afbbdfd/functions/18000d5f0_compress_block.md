# compress_block

- ea: `0x18000d5f0`
- end: `0x18000db12`
- name: `compress_block`
- size: `1314`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000cd6c`

## callees

- `0x18000d5f0`
- `0x18000dd50`

## pseudocode

```c
__int64 __fastcall compress_block(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int16 v3; // r9
  unsigned __int16 v4; // r13
  unsigned __int16 v5; // r12
  unsigned __int8 v6; // r10
  __int64 v7; // r14
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r11
  int v13; // edx
  __int64 v14; // rbp
  _QWORD *v15; // r15
  unsigned __int16 v16; // di
  int v17; // esi
  __int16 v18; // bx
  int v19; // r8d
  __int16 v20; // di
  int v21; // esi
  int v22; // r11d
  __int16 v23; // bx
  int v24; // r11d
  __int64 v25; // rdx
  unsigned int v26; // ebx
  unsigned __int8 v27; // dl
  __int64 v28; // r14
  unsigned __int16 v29; // si
  int v30; // ebp
  __int16 v31; // di
  int v32; // r8d
  __int16 v33; // si
  int v34; // r11d
  int v35; // ebx
  __int16 v36; // di
  int v37; // ecx
  int v38; // ebx
  unsigned __int16 v39; // r11
  __int16 v40; // r8
  unsigned int v41; // r8d
  __int64 v42; // rdx
  __int64 v43; // r8
  int v44; // ecx
  unsigned int v45; // r8d
  __int64 v46; // rdx
  __int64 v47; // r8
  int v48; // ecx
  unsigned int v49; // edi
  __int64 v50; // rdx
  __int64 v51; // r8
  int v52; // ecx
  unsigned int v53; // r8d
  __int64 v54; // rdx
  __int64 v55; // r8
  int v56; // edx
  unsigned int v57; // r8d
  __int64 v58; // rdx
  __int64 v59; // r8
  int v60; // edx

  v3 = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = a2;
  if ( *(_WORD *)(a1 + 96) )
  {
    while ( 1 )
    {
      if ( (v3 & 7) == 0 )
      {
        v10 = v5++;
        v6 = *(_BYTE *)(v10 + a1 + 8108);
      }
      v11 = v3++;
      v12 = *(unsigned __int8 *)(v11 + *(_QWORD *)a1);
      v13 = *(_DWORD *)(a1 + 72);
      if ( (v6 & 1) != 0 )
        break;
      v38 = *(unsigned __int16 *)(v7 + 4 * v12 + 2);
      v39 = *(_WORD *)(v7 + 4 * v12);
      v40 = *(_WORD *)(a1 + 68) | (v39 << v13);
      if ( v13 > 16 - v38 )
      {
        v49 = *(_DWORD *)(a1 + 28);
        v50 = *(unsigned __int16 *)(a1 + 24);
        *(_WORD *)(a1 + 68) = v40;
        if ( (unsigned int)v50 < v49 - 2 )
        {
          *(_BYTE *)(v50 + *(_QWORD *)(a1 + 8)) = v40;
          v51 = (unsigned __int16)++*(_WORD *)(a1 + 24);
          goto LABEL_35;
        }
        if ( (unsigned int)v50 < v49 )
        {
          *(_BYTE *)(v50 + *(_QWORD *)(a1 + 8)) = v40;
          LOWORD(v50) = ++*(_WORD *)(a1 + 24);
        }
        else
        {
          *(_DWORD *)(a1 + 64) = 1;
        }
        if ( (unsigned int)(unsigned __int16)v50 < *(_DWORD *)(a1 + 28) )
        {
          v51 = (unsigned __int16)v50;
LABEL_35:
          *(_BYTE *)(v51 + *(_QWORD *)(a1 + 8)) = *(_BYTE *)(a1 + 69);
          ++*(_WORD *)(a1 + 24);
        }
        else
        {
          *(_DWORD *)(a1 + 64) = 1;
        }
        v52 = *(_DWORD *)(a1 + 72);
        *(_WORD *)(a1 + 68) = v39 >> (16 - v52);
        *(_DWORD *)(a1 + 72) = v52 + v38 - 16;
        goto LABEL_20;
      }
      *(_WORD *)(a1 + 68) = v40;
      *(_DWORD *)(a1 + 72) = v13 + v38;
LABEL_20:
      v6 >>= 1;
      if ( v3 >= *(_WORD *)(a1 + 96) )
        return send_bits(a1, *(unsigned __int16 *)(v7 + 1024), *(unsigned __int16 *)(v7 + 1026));
    }
    v14 = *(unsigned __int8 *)(v12 + a1 + 7101);
    v15 = (_QWORD *)(a1 + 8);
    v16 = *(_WORD *)(v7 + 4 * v14 + 1028);
    v17 = *(unsigned __int16 *)(v7 + 4 * v14 + 1030);
    v18 = *(_WORD *)(a1 + 68) | (v16 << v13);
    if ( v13 <= 16 - v17 )
    {
      v19 = v13 + v17;
      v20 = *(_WORD *)(a1 + 68) | (v16 << v13);
      goto LABEL_8;
    }
    v41 = *(_DWORD *)(a1 + 28);
    v42 = *(unsigned __int16 *)(a1 + 24);
    *(_WORD *)(a1 + 68) = v18;
    if ( (unsigned int)v42 >= v41 - 2 )
    {
      if ( (unsigned int)v42 < v41 )
      {
        *(_BYTE *)(v42 + *v15) = v18;
        LOWORD(v42) = ++*(_WORD *)(a1 + 24);
      }
      else
      {
        *(_DWORD *)(a1 + 64) = 1;
      }
      if ( (unsigned int)(unsigned __int16)v42 >= *(_DWORD *)(a1 + 28) )
      {
        *(_DWORD *)(a1 + 64) = 1;
        goto LABEL_28;
      }
      v43 = (unsigned __int16)v42;
    }
    else
    {
      *(_BYTE *)(v42 + *v15) = v18;
      v43 = (unsigned __int16)++*(_WORD *)(a1 + 24);
    }
    *(_BYTE *)(v43 + *v15) = *(_BYTE *)(a1 + 69);
    ++*(_WORD *)(a1 + 24);
LABEL_28:
    v44 = *(_DWORD *)(a1 + 72);
    v19 = v17 + v44 - 16;
    v20 = v16 >> (16 - v44);
LABEL_8:
    *(_WORD *)(a1 + 68) = v20;
    *(_DWORD *)(a1 + 72) = v19;
    v21 = dword_18001E880[v14];
    if ( !v21 )
    {
      LOWORD(v24) = v20;
LABEL_11:
      v25 = v4++;
      v26 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 16) + 2 * v25);
      if ( v26 < 0x100 )
      {
        _mm_lfence();
        v27 = *(_BYTE *)(*(unsigned __int16 *)(*(_QWORD *)(a1 + 16) + 2 * v25) + a1 + 7357);
      }
      else
      {
        v27 = *(_BYTE *)(((unsigned __int64)*(unsigned __int16 *)(*(_QWORD *)(a1 + 16) + 2 * v25) >> 7) + a1 + 7613);
      }
      v28 = v27;
      v29 = *(_WORD *)(a3 + 4LL * v27);
      v30 = *(unsigned __int16 *)(a3 + 4LL * v27 + 2);
      v31 = v24 | (v29 << v19);
      if ( v19 <= 16 - v30 )
      {
        v32 = v30 + v19;
        v33 = v31;
        goto LABEL_15;
      }
      v45 = *(_DWORD *)(a1 + 28);
      v46 = *(unsigned __int16 *)(a1 + 24);
      *(_WORD *)(a1 + 68) = v31;
      if ( (unsigned int)v46 >= v45 - 2 )
      {
        if ( (unsigned int)v46 < v45 )
        {
          *(_BYTE *)(v46 + *v15) = v31;
          LOWORD(v46) = ++*(_WORD *)(a1 + 24);
        }
        else
        {
          *(_DWORD *)(a1 + 64) = 1;
        }
        if ( (unsigned int)(unsigned __int16)v46 >= *(_DWORD *)(a1 + 28) )
        {
          *(_DWORD *)(a1 + 64) = 1;
          goto LABEL_32;
        }
        v47 = (unsigned __int16)v46;
      }
      else
      {
        *(_BYTE *)(v46 + *v15) = v31;
        v47 = (unsigned __int16)++*(_WORD *)(a1 + 24);
      }
      *(_BYTE *)(v47 + *v15) = *(_BYTE *)(a1 + 69);
      ++*(_WORD *)(a1 + 24);
LABEL_32:
      v48 = *(_DWORD *)(a1 + 72);
      v32 = v30 + v48 - 16;
      v33 = v29 >> (16 - v48);
LABEL_15:
      *(_WORD *)(a1 + 68) = v33;
      *(_DWORD *)(a1 + 72) = v32;
      v34 = dword_18001E800[v28];
      if ( !v34 )
      {
LABEL_19:
        v7 = a2;
        goto LABEL_20;
      }
      v35 = v26 - *(_DWORD *)(a1 + 4 * v28 + 7988);
      v36 = v33 | ((_WORD)v35 << v32);
      *(_WORD *)(a1 + 68) = v36;
      if ( v32 <= 16 - v34 )
      {
        v37 = v32 + v34;
LABEL_18:
        *(_DWORD *)(a1 + 72) = v37;
        goto LABEL_19;
      }
      v53 = *(_DWORD *)(a1 + 28);
      v54 = *(unsigned __int16 *)(a1 + 24);
      if ( (unsigned int)v54 >= v53 - 2 )
      {
        if ( (unsigned int)v54 < v53 )
        {
          *(_BYTE *)(v54 + *v15) = v36;
          LOWORD(v54) = ++*(_WORD *)(a1 + 24);
        }
        else
        {
          *(_DWORD *)(a1 + 64) = 1;
        }
        if ( (unsigned int)(unsigned __int16)v54 >= *(_DWORD *)(a1 + 28) )
        {
          *(_DWORD *)(a1 + 64) = 1;
          goto LABEL_40;
        }
        v55 = (unsigned __int16)v54;
      }
      else
      {
        *(_BYTE *)(v54 + *v15) = v36;
        v55 = (unsigned __int16)++*(_WORD *)(a1 + 24);
      }
      *(_BYTE *)(v55 + *v15) = *(_BYTE *)(a1 + 69);
      ++*(_WORD *)(a1 + 24);
LABEL_40:
      v56 = *(_DWORD *)(a1 + 72);
      *(_WORD *)(a1 + 68) = v35 >> (16 - v56);
      v37 = v34 + v56 - 16;
      goto LABEL_18;
    }
    v22 = v12 - *(_DWORD *)(a1 + 4 * v14 + 7872);
    v23 = v20 | ((_WORD)v22 << v19);
    *(_WORD *)(a1 + 68) = v23;
    if ( v19 <= 16 - v21 )
    {
      v19 += v21;
      LOWORD(v24) = v23;
      *(_DWORD *)(a1 + 72) = v19;
      goto LABEL_11;
    }
    v57 = *(_DWORD *)(a1 + 28);
    v58 = *(unsigned __int16 *)(a1 + 24);
    if ( (unsigned int)v58 >= v57 - 2 )
    {
      if ( (unsigned int)v58 < v57 )
      {
        *(_BYTE *)(v58 + *v15) = v23;
        LOWORD(v58) = ++*(_WORD *)(a1 + 24);
      }
      else
      {
        *(_DWORD *)(a1 + 64) = 1;
      }
      if ( (unsigned int)(unsigned __int16)v58 >= *(_DWORD *)(a1 + 28) )
      {
        *(_DWORD *)(a1 + 64) = 1;
        goto LABEL_44;
      }
      v59 = (unsigned __int16)v58;
    }
    else
    {
      *(_BYTE *)(v58 + *v15) = v23;
      v59 = (unsigned __int16)++*(_WORD *)(a1 + 24);
    }
    *(_BYTE *)(v59 + *v15) = *(_BYTE *)(a1 + 69);
    ++*(_WORD *)(a1 + 24);
LABEL_44:
    v60 = *(_DWORD *)(a1 + 72);
    v24 = v22 >> (16 - v60);
    *(_WORD *)(a1 + 68) = v24;
    v19 = v21 + v60 - 16;
    *(_DWORD *)(a1 + 72) = v19;
    goto LABEL_11;
  }
  return send_bits(a1, *(unsigned __int16 *)(v7 + 1024), *(unsigned __int16 *)(v7 + 1026));
}

```

## disassembly

```asm
0x18000d5f0  mov     [rsp+arg_10], r8
0x18000d5f5  mov     [rsp+arg_8], rdx
0x18000d5fa  push    r12
0x18000d5fc  push    r13
0x18000d5fe  push    r14
0x18000d600  sub     rsp, 40h
0x18000d604  xor     r9d, r9d
0x18000d607  xor     r13d, r13d
0x18000d60a  xor     r12d, r12d
0x18000d60d  xor     r10b, r10b
0x18000d610  mov     r14, rdx
0x18000d613  mov     rax, rcx
0x18000d616  cmp     [rcx+60h], r9w
0x18000d61b  jnz     short loc_18000D63F
0x18000d61d  movzx   r8d, word ptr [r14+402h]
0x18000d625  mov     rcx, rax
0x18000d628  movzx   edx, word ptr [r14+400h]
0x18000d630  add     rsp, 40h
0x18000d634  pop     r14
0x18000d636  pop     r13
0x18000d638  pop     r12
0x18000d63a  jmp     send_bits
0x18000d63f  mov     [rsp+58h+arg_0], rbx
0x18000d644  mov     [rsp+58h+var_20], rbp
0x18000d649  mov     [rsp+58h+var_28], rsi
0x18000d64e  mov     [rsp+58h+var_30], rdi
0x18000d653  mov     [rsp+58h+var_38], r15
0x18000d658  test    r9b, 7
0x18000d65c  jnz     short loc_18000D66F
0x18000d65e  movzx   ecx, r12w
0x18000d662  inc     r12w
0x18000d666  movzx   r10d, byte ptr [rcx+rax+1FACh]
0x18000d66f  mov     rcx, [rax]
0x18000d672  movzx   edx, r9w
0x18000d676  inc     r9w
0x18000d67a  movzx   r11d, byte ptr [rdx+rcx]
0x18000d67f  mov     edx, [rax+48h]
0x18000d682  mov     ecx, edx
0x18000d684  test    r10b, 1
0x18000d688  jz      loc_18000D7FD
0x18000d68e  movzx   ebp, byte ptr [r11+rax+1BBDh]
0x18000d697  lea     r15, [rax+8]
0x18000d69b  movzx   edi, word ptr [r14+rbp*4+404h]
0x18000d6a4  movzx   esi, word ptr [r14+rbp*4+406h]
0x18000d6ad  movzx   ebx, di
0x18000d6b0  shl     bx, cl
0x18000d6b3  mov     ecx, 10h
0x18000d6b8  or      bx, [rax+44h]
0x18000d6bc  sub     ecx, esi
0x18000d6be  cmp     edx, ecx
0x18000d6c0  jg      loc_18000D847
0x18000d6c6  lea     r8d, [rdx+rsi]
0x18000d6ca  movzx   edi, bx
0x18000d6cd  mov     [rax+44h], di
0x18000d6d1  lea     rsi, __ImageBase
0x18000d6d8  mov     [rax+48h], r8d
0x18000d6dc  mov     esi, ds:rva dword_18001E880[rsi+rbp*4]
0x18000d6e3  test    esi, esi
0x18000d6e5  jz      loc_18000D9E9
0x18000d6eb  sub     r11d, [rax+rbp*4+1EC0h]
0x18000d6f3  mov     ecx, r8d
0x18000d6f6  movzx   ebx, r11w
0x18000d6fa  shl     bx, cl
0x18000d6fd  mov     ecx, 10h
0x18000d702  or      bx, di
0x18000d705  sub     ecx, esi
0x18000d707  mov     [rax+44h], bx
0x18000d70b  cmp     r8d, ecx
0x18000d70e  jg      loc_18000D995
0x18000d714  add     r8d, esi
0x18000d717  movzx   r11d, bx
0x18000d71b  mov     [rax+48h], r8d
0x18000d71f  mov     rcx, [rax+10h]
0x18000d723  movzx   edx, r13w
0x18000d727  inc     r13w
0x18000d72b  movzx   ebx, word ptr [rcx+rdx*2]
0x18000d72f  cmp     ebx, 100h
0x18000d735  jb      loc_18000D834
0x18000d73b  mov     ecx, ebx
0x18000d73d  shr     rcx, 7
0x18000d741  movzx   edx, byte ptr [rcx+rax+1DBDh]
0x18000d749  mov     rcx, [rsp+58h+arg_10]
0x18000d74e  movzx   r14d, dl
0x18000d752  movzx   esi, word ptr [rcx+r14*4]
0x18000d757  movzx   ebp, word ptr [rcx+r14*4+2]
0x18000d75d  movzx   edi, si
0x18000d760  mov     ecx, r8d
0x18000d763  shl     di, cl
0x18000d766  mov     ecx, 10h
0x18000d76b  sub     ecx, ebp
0x18000d76d  or      di, r11w
0x18000d771  cmp     r8d, ecx
0x18000d774  jg      loc_18000D899
0x18000d77a  add     r8d, ebp
0x18000d77d  movzx   esi, di
0x18000d780  mov     [rax+44h], si
0x18000d784  lea     rcx, __ImageBase
0x18000d78b  mov     [rax+48h], r8d
0x18000d78f  mov     r11d, ds:rva dword_18001E800[rcx+r14*4]
0x18000d797  test    r11d, r11d
0x18000d79a  jz      short loc_18000D7CC
0x18000d79c  sub     ebx, [rax+r14*4+1F34h]
0x18000d7a4  mov     ecx, r8d
0x18000d7a7  movzx   edi, bx
0x18000d7aa  shl     di, cl
0x18000d7ad  mov     ecx, 10h
0x18000d7b2  or      di, si
0x18000d7b5  sub     ecx, r11d
0x18000d7b8  mov     [rax+44h], di
0x18000d7bc  cmp     r8d, ecx
0x18000d7bf  jg      loc_18000D947
0x18000d7c5  lea     ecx, [r8+r11]
0x18000d7c9  mov     [rax+48h], ecx
0x18000d7cc  mov     r14, [rsp+58h+arg_8]
0x18000d7d1  shr     r10b, 1
0x18000d7d4  cmp     r9w, [rax+60h]
0x18000d7d9  jb      loc_18000D658
0x18000d7df  mov     r15, [rsp+58h+var_38]
0x18000d7e4  mov     rdi, [rsp+58h+var_30]
0x18000d7e9  mov     rsi, [rsp+58h+var_28]
0x18000d7ee  mov     rbp, [rsp+58h+var_20]
0x18000d7f3  mov     rbx, [rsp+58h+arg_0]
0x18000d7f8  jmp     loc_18000D61D
0x18000d7fd  movzx   ebx, word ptr [r14+r11*4+2]
0x18000d803  movzx   r11d, word ptr [r14+r11*4]
0x18000d808  movzx   r8d, r11w
0x18000d80c  shl     r8w, cl
0x18000d810  mov     ecx, 10h
0x18000d815  or      r8w, [rax+44h]
0x18000d81a  sub     ecx, ebx
0x18000d81c  cmp     edx, ecx
0x18000d81e  jg      loc_18000D8EC
0x18000d824  add     ebx, edx
0x18000d826  mov     [rax+44h], r8w
0x18000d82b  mov     [rax+48h], ebx
0x18000d82e  movzx   r11d, r8w
0x18000d832  jmp     short loc_18000D7D1
0x18000d834  lfence
0x18000d837  movsxd  rcx, ebx
0x18000d83a  movzx   edx, byte ptr [rcx+rax+1CBDh]
0x18000d842  jmp     loc_18000D749
0x18000d847  mov     r8d, [rax+1Ch]
0x18000d84b  movzx   edx, word ptr [rax+18h]
0x18000d84f  mov     [rax+44h], bx
0x18000d853  lea     ecx, [r8-2]
0x18000d857  cmp     edx, ecx
0x18000d859  jnb     loc_18000DA2C
0x18000d85f  mov     rcx, [r15]
0x18000d862  mov     [rdx+rcx], bl
0x18000d865  inc     word ptr [rax+18h]
0x18000d869  movzx   r8d, word ptr [rax+18h]
0x18000d86e  mov     rdx, [r15]
0x18000d871  movzx   ecx, byte ptr [rax+45h]
0x18000d875  mov     [r8+rdx], cl
0x18000d879  inc     word ptr [rax+18h]
0x18000d87d  mov     ecx, [rax+48h]
0x18000d880  mov     edx, 10h
0x18000d885  sub     dl, cl
0x18000d887  lea     r8d, [rcx-10h]
0x18000d88b  movzx   ecx, dl
0x18000d88e  add     r8d, esi
0x18000d891  shr     di, cl
0x18000d894  jmp     loc_18000D6CD
0x18000d899  mov     r8d, [rax+1Ch]
0x18000d89d  movzx   edx, word ptr [rax+18h]
0x18000d8a1  mov     [rax+44h], di
0x18000d8a5  lea     ecx, [r8-2]
0x18000d8a9  cmp     edx, ecx
0x18000d8ab  jnb     loc_18000DA9E
0x18000d8b1  mov     rcx, [r15]
0x18000d8b4  mov     [rdx+rcx], dil
0x18000d8b8  inc     word ptr [rax+18h]
0x18000d8bc  movzx   r8d, word ptr [rax+18h]
0x18000d8c1  mov     rdx, [r15]
0x18000d8c4  movzx   ecx, byte ptr [rax+45h]
0x18000d8c8  mov     [r8+rdx], cl
0x18000d8cc  inc     word ptr [rax+18h]
0x18000d8d0  mov     ecx, [rax+48h]
0x18000d8d3  mov     edx, 10h
0x18000d8d8  sub     dl, cl
0x18000d8da  lea     r8d, [rcx-10h]
0x18000d8de  movzx   ecx, dl
0x18000d8e1  add     r8d, ebp
0x18000d8e4  shr     si, cl
0x18000d8e7  jmp     loc_18000D780
0x18000d8ec  mov     edi, [rax+1Ch]
0x18000d8ef  movzx   edx, word ptr [rax+18h]
0x18000d8f3  mov     [rax+44h], r8w
0x18000d8f8  lea     ecx, [rdi-2]
0x18000d8fb  cmp     edx, ecx
0x18000d8fd  jnb     loc_18000D9F2
0x18000d903  mov     rcx, [rax+8]
0x18000d907  mov     [rdx+rcx], r8b
0x18000d90b  inc     word ptr [rax+18h]
0x18000d90f  movzx   r8d, word ptr [rax+18h]
0x18000d914  mov     rdx, [rax+8]
0x18000d918  movzx   ecx, byte ptr [rax+45h]
0x18000d91c  mov     [r8+rdx], cl
0x18000d920  inc     word ptr [rax+18h]
0x18000d924  mov     ecx, [rax+48h]
0x18000d927  add     ebx, 0FFFFFFF0h
0x18000d92a  add     ebx, ecx
0x18000d92c  mov     edx, 10h
0x18000d931  sub     dl, cl
0x18000d933  movzx   ecx, dl
0x18000d936  shr     r11w, cl
0x18000d93a  mov     [rax+44h], r11w
0x18000d93f  mov     [rax+48h], ebx
0x18000d942  jmp     loc_18000D7D1
0x18000d947  mov     r8d, [rax+1Ch]
0x18000d94b  movzx   edx, word ptr [rax+18h]
0x18000d94f  lea     ecx, [r8-2]
0x18000d953  cmp     edx, ecx
0x18000d955  jnb     loc_18000DAD8
0x18000d95b  mov     rcx, [r15]
0x18000d95e  mov     [rdx+rcx], dil
0x18000d962  inc     word ptr [rax+18h]
0x18000d966  movzx   r8d, word ptr [rax+18h]
0x18000d96b  mov     rdx, [r15]
0x18000d96e  movzx   ecx, byte ptr [rax+45h]
0x18000d972  mov     [r8+rdx], cl
0x18000d976  inc     word ptr [rax+18h]
0x18000d97a  mov     edx, [rax+48h]
0x18000d97d  mov     ecx, 10h
0x18000d982  sub     ecx, edx
0x18000d984  sar     ebx, cl
0x18000d986  mov     [rax+44h], bx
0x18000d98a  lea     ecx, [rdx-10h]
0x18000d98d  add     ecx, r11d
0x18000d990  jmp     loc_18000D7C9
0x18000d995  mov     r8d, [rax+1Ch]
0x18000d999  movzx   edx, word ptr [rax+18h]
0x18000d99d  lea     ecx, [r8-2]
0x18000d9a1  cmp     edx, ecx
0x18000d9a3  jnb     loc_18000DA65
0x18000d9a9  mov     rcx, [r15]
0x18000d9ac  mov     [rdx+rcx], bl
0x18000d9af  inc     word ptr [rax+18h]
0x18000d9b3  movzx   r8d, word ptr [rax+18h]
0x18000d9b8  mov     rdx, [r15]
0x18000d9bb  movzx   ecx, byte ptr [rax+45h]
0x18000d9bf  mov     [r8+rdx], cl
0x18000d9c3  inc     word ptr [rax+18h]
0x18000d9c7  mov     edx, [rax+48h]
0x18000d9ca  mov     ecx, 10h
0x18000d9cf  sub     ecx, edx
0x18000d9d1  sar     r11d, cl
0x18000d9d4  mov     [rax+44h], r11w
0x18000d9d9  lea     r8d, [rdx-10h]
0x18000d9dd  add     r8d, esi
0x18000d9e0  mov     [rax+48h], r8d
0x18000d9e4  jmp     loc_18000D71F
0x18000d9e9  movzx   r11d, di
0x18000d9ed  jmp     loc_18000D71F
0x18000d9f2  cmp     edx, edi
0x18000d9f4  jb      short loc_18000D9FF
0x18000d9f6  mov     dword ptr [rax+40h], 1
0x18000d9fd  jmp     short loc_18000DA0F
0x18000d9ff  mov     rcx, [rax+8]
0x18000da03  mov     [rdx+rcx], r8b
0x18000da07  inc     word ptr [rax+18h]
0x18000da0b  movzx   edx, word ptr [rax+18h]
0x18000da0f  movzx   ecx, dx
0x18000da12  cmp     ecx, [rax+1Ch]
0x18000da15  jb      short loc_18000DA23
0x18000da17  mov     dword ptr [rax+40h], 1
0x18000da1e  jmp     loc_18000D924
0x18000da23  movzx   r8d, dx
0x18000da27  jmp     loc_18000D914
0x18000da2c  cmp     edx, r8d
0x18000da2f  jb      short loc_18000DA3A
0x18000da31  mov     dword ptr [rax+40h], 1
0x18000da38  jmp     short loc_18000DA48
0x18000da3a  mov     rcx, [r15]
0x18000da3d  mov     [rdx+rcx], bl
0x18000da40  inc     word ptr [rax+18h]
0x18000da44  movzx   edx, word ptr [rax+18h]
0x18000da48  movzx   ecx, dx
0x18000da4b  cmp     ecx, [rax+1Ch]
0x18000da4e  jb      short loc_18000DA5C
0x18000da50  mov     dword ptr [rax+40h], 1
0x18000da57  jmp     loc_18000D87D
0x18000da5c  movzx   r8d, dx
0x18000da60  jmp     loc_18000D86E
0x18000da65  cmp     edx, r8d
0x18000da68  jb      short loc_18000DA73
0x18000da6a  mov     dword ptr [rax+40h], 1
0x18000da71  jmp     short loc_18000DA81
0x18000da73  mov     rcx, [r15]
0x18000da76  mov     [rdx+rcx], bl
0x18000da79  inc     word ptr [rax+18h]
0x18000da7d  movzx   edx, word ptr [rax+18h]
0x18000da81  movzx   ecx, dx
0x18000da84  cmp     ecx, [rax+1Ch]
0x18000da87  jb      short loc_18000DA95
0x18000da89  mov     dword ptr [rax+40h], 1
0x18000da90  jmp     loc_18000D9C7
0x18000da95  movzx   r8d, dx
0x18000da99  jmp     loc_18000D9B8
0x18000da9e  cmp     edx, r8d
  ... truncated ...
```
