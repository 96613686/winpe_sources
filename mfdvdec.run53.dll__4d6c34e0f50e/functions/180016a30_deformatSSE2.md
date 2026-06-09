# deformatSSE2

- ea: `0x180016a30`
- end: `0x18001731e`
- name: `deformatSSE2`
- size: `2286`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180016700`
- `0x180019d30`

## callees

- `0x180001580`
- `0x180001eb0`
- `0x180016a30`

## pseudocode

```c
unsigned __int64 __fastcall deformatSSE2(__int64 a1, __int64 a2, _WORD *a3)
{
  __int64 v3; // rbx
  __int64 v4; // rdi
  char *v5; // rdx
  char v6; // cl
  char **v7; // r14
  char *v8; // r15
  char *v9; // r12
  _WORD *v10; // r10
  int v11; // r13d
  __int64 v12; // rsi
  __int64 v13; // r8
  unsigned __int8 *v14; // rdx
  int v15; // r9d
  char v16; // dl
  __int64 v17; // rax
  int v18; // r9d
  int v19; // edi
  int v20; // ebx
  unsigned __int8 *v21; // r11
  int v22; // r8d
  unsigned int v23; // r8d
  int v24; // r9d
  char v25; // cl
  unsigned __int64 result; // rax
  int v27; // r9d
  char v28; // cl
  int v29; // r9d
  __int64 v30; // rax
  char v31; // cl
  char v32; // cl
  __int64 v33; // rax
  __int64 **v34; // rsi
  unsigned __int64 *v35; // rbx
  __int64 *v36; // r11
  unsigned int v37; // r8d
  unsigned __int8 **v38; // rdi
  char v39; // dl
  __int64 v40; // r13
  unsigned __int8 *v41; // r15
  int v42; // r14d
  int v43; // r12d
  unsigned int v44; // r9d
  int v45; // r8d
  char v46; // cl
  int v47; // r8d
  char v48; // cl
  int v49; // r8d
  __int64 v50; // rax
  char v51; // cl
  __int64 v52; // rax
  __int64 *v53; // rax
  _QWORD *v54; // rcx
  unsigned __int64 *v55; // rcx
  int v56; // r9d
  char v57; // dl
  int v58; // eax
  bool v59; // zf
  __int64 **v60; // r12
  unsigned __int8 ***v61; // r15
  __int64 *i; // r10
  unsigned __int8 **v63; // rbx
  char v64; // dl
  __int64 v65; // r13
  unsigned __int8 *v66; // rdi
  int v67; // r11d
  int v68; // r14d
  unsigned int v69; // r8d
  int v70; // r9d
  char v71; // cl
  int v72; // r9d
  char v73; // cl
  int v74; // r9d
  char v75; // cl
  __int64 v76; // rax
  unsigned int v77; // r8d
  char v78; // dl
  BOOL v81; // [rsp+30h] [rbp-D0h]
  int v82; // [rsp+34h] [rbp-CCh]
  int v83; // [rsp+38h] [rbp-C8h]
  unsigned __int64 *v84; // [rsp+40h] [rbp-C0h]
  __int64 v85; // [rsp+48h] [rbp-B8h]
  _QWORD *v86; // [rsp+50h] [rbp-B0h]
  char *v87; // [rsp+58h] [rbp-A8h]
  __int64 v88; // [rsp+60h] [rbp-A0h]
  _QWORD v89[7]; // [rsp+70h] [rbp-90h] BYREF
  char v90; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v91[31]; // [rsp+B0h] [rbp-50h] BYREF
  char v92; // [rsp+1A8h] [rbp+A8h] BYREF
  char v93; // [rsp+1B0h] [rbp+B0h] BYREF

  v3 = a2;
  v85 = a2;
  v4 = a1;
  memset_0(v89, 0, 0x40u);
  memset_0(v91, 0, 0x100u);
  v83 = 0;
  v86 = v91;
  v5 = (char *)(v3 + 3);
  v88 = v3 + 3;
  v84 = (unsigned __int64 *)&v92;
  v87 = &v93;
  v82 = 5;
  while ( 2 )
  {
    if ( (unsigned __int64)v5 < *(_QWORD *)v4 || (unsigned __int64)&v5[-*(_QWORD *)v4] > *(unsigned int *)(v4 + 8) )
    {
      v6 = -1;
      v7 = (char **)v89;
      v8 = &v90;
    }
    else
    {
      v6 = *v5;
      v7 = (char **)v89;
      v8 = &v90;
      v81 = 0;
      if ( (*v5 & 0xF0) == 0 )
        goto LABEL_9;
    }
    v83 = 1;
    v81 = (v6 & 0x70) == 112;
LABEL_9:
    v9 = v87;
    v10 = a3;
    v11 = v6 & 0xF;
    v12 = 0;
    while ( 2 )
    {
      v13 = (unsigned __int8)offset2[4 * v12];
      v14 = (unsigned __int8 *)(v3 + v13);
      if ( (unsigned __int64)(v3 + v13) < *(_QWORD *)v4
        || (unsigned __int64)&v14[-*(_QWORD *)v4] >= *(unsigned int *)(v4 + 8) )
      {
        v15 = 0xFFFF;
      }
      else
      {
        v15 = v14[1] + (*v14 << 8);
      }
      *v10 = v15;
      v16 = 20;
      v17 = v11 + (v15 & 0x70u);
      v18 = v15 << 28;
      v19 = (unsigned int)v12 < 4 ? 5 : 3;
      v20 = (unsigned __int16)VLDecodeZigOffset720[v17];
      v21 = (unsigned __int8 *)(v13 + v85 + 2);
      if ( (unsigned __int64)v21 < *(_QWORD *)a1 || (unsigned __int64)&v21[-*(_QWORD *)a1] >= *(unsigned int *)(a1 + 8) )
        v22 = 0xFFFF;
      else
        v22 = v21[1] + (*v21 << 8);
      v23 = v18 + (v22 << 12);
      while ( 1 )
      {
        while ( 1 )
        {
          if ( v16 < 16 && v19 > 0 )
          {
            v21 += 2;
            if ( (unsigned __int64)v21 < *(_QWORD *)a1
              || (unsigned __int64)&v21[-*(_QWORD *)a1] >= *(unsigned int *)(a1 + 8) )
            {
              v24 = 0xFFFF;
            }
            else
            {
              v24 = v21[1] + (*v21 << 8);
            }
            v25 = 16 - v16;
            v16 += 16;
            v23 += v24 << v25;
            --v19;
            if ( v20 >= 1664 )
              v20 = 0;
          }
          result = (unsigned __int64)v23 >> 22;
          v27 = VLDecodeTableRoot[result];
          v28 = VLDecodeTableRoot[result] & 0xF;
          if ( !v28 )
            break;
LABEL_37:
          v16 -= v28;
          if ( v16 < 0 )
            goto LABEL_42;
          v23 <<= v28;
          v20 += (v27 >> 4) & 0x3F;
          if ( BYTE1(v27) > 3u )
          {
            v32 = byte_180022A61[2 * v20];
            v33 = (unsigned __int8)nzigtable[2 * v20++];
            a3[v33] = (unsigned __int16)(v27 >> 8) << v32;
          }
          v10 = a3;
        }
        if ( v27 > 0 )
          break;
        if ( !VLDecodeTableRoot[result] )
        {
          result = (v23 >> 19) - 7936;
          v27 = VLDecodeTableExtra[result];
          v28 = VLDecodeTableExtra[result] & 0xF;
          goto LABEL_37;
        }
        v16 -= 16;
        if ( v16 < 0 )
        {
          v28 = 16;
LABEL_42:
          v16 += v28;
LABEL_43:
          *v7++ = v9;
          *((_DWORD *)v9 + 3) = v23;
          *((_DWORD *)v9 + 2) = v20;
          *(_QWORD *)v9 = v10;
LABEL_44:
          v9[16] = v16;
          v9 += 24;
          goto LABEL_45;
        }
        v29 = (v23 >> 15) & 0x3FC;
        v30 = (unsigned __int8)nzigtable[2 * v20];
        if ( (v23 & 0x10000) != 0 )
          v29 = -v29;
        v23 <<= 16;
        v31 = byte_180022A61[2 * v20];
        v10 = a3;
        ++v20;
        a3[v30] = (_WORD)v29 << v31;
      }
      if ( v16 < 4 )
        goto LABEL_43;
      v37 = 16 * v23;
      v16 -= 4;
      if ( v16 <= 16 )
      {
        result = v37;
      }
      else
      {
        v16 -= 16;
        v21 -= 2;
        ++v19;
        result = v37 & (-1 << (32 - v16));
      }
      if ( v16 || v19 )
      {
        *(_QWORD *)v8 = v9;
        v8 -= 8;
        *((_DWORD *)v9 + 3) = result;
        *((_DWORD *)v9 + 2) = v19;
        *(_QWORD *)v9 = v21;
        goto LABEL_44;
      }
LABEL_45:
      v3 = v85;
      v10 += 64;
      v12 = (unsigned int)(v12 + 1);
      a3 = v10;
      if ( (int)v12 < 6 )
      {
        v4 = a1;
        continue;
      }
      break;
    }
    v87 = v9;
    if ( v81 )
    {
      v55 = v84;
      goto LABEL_98;
    }
    *v7 = 0;
    v34 = (__int64 **)v89;
    *(_QWORD *)v8 = 0;
    v35 = (unsigned __int64 *)&v90;
    v36 = (__int64 *)v89[0];
LABEL_80:
    if ( v36 )
    {
      v38 = (unsigned __int8 **)*v35;
      if ( *v35 )
      {
        v39 = *((_BYTE *)v38 + 16) + *((_BYTE *)v36 + 16);
        v40 = *v36;
        v41 = *v38;
        v42 = *((_DWORD *)v36 + 2);
        v43 = *((_DWORD *)v38 + 2);
        v44 = *((_DWORD *)v36 + 3) + (*((_DWORD *)v38 + 3) >> *((_BYTE *)v36 + 16));
        while ( 1 )
        {
          while ( 1 )
          {
            if ( v39 < 16 && v43 > 0 )
            {
              v41 += 2;
              if ( (unsigned __int64)v41 < *(_QWORD *)a1
                || (unsigned __int64)&v41[-*(_QWORD *)a1] >= *(unsigned int *)(a1 + 8) )
              {
                v45 = 0xFFFF;
              }
              else
              {
                v45 = v41[1] + (*v41 << 8);
              }
              v46 = 16 - v39;
              v39 += 16;
              v44 += v45 << v46;
              --v43;
              if ( v42 >= 1664 )
                v42 = 0;
            }
            v47 = VLDecodeTableRoot[(unsigned __int64)v44 >> 22];
            v48 = VLDecodeTableRoot[(unsigned __int64)v44 >> 22] & 0xF;
            if ( !v48 )
              break;
LABEL_73:
            v39 -= v48;
            if ( v39 < 0 )
              goto LABEL_77;
            v44 <<= v48;
            v42 += (v47 >> 4) & 0x3F;
            if ( BYTE1(v47) > 3u )
            {
              v51 = byte_180022A61[2 * v42];
              v52 = (unsigned __int8)nzigtable[2 * v42++];
              *(_WORD *)(v40 + 2 * v52) = (unsigned __int16)(v47 >> 8) << v51;
            }
          }
          if ( v47 > 0 )
          {
            if ( v39 < 4 )
              goto LABEL_78;
            v56 = 16 * v44;
            v57 = v39 - 4;
            if ( v57 <= 16 )
            {
              v58 = v56;
            }
            else
            {
              v57 -= 16;
              v41 -= 2;
              ++v43;
              v58 = v56 & (-1 << (32 - v57));
            }
            if ( v57 || v43 )
            {
              *((_DWORD *)v38 + 3) = v58;
              *((_BYTE *)v38 + 16) = v57;
              *v38 = v41;
              *((_DWORD *)v38 + 2) = v43;
            }
            else
            {
              --v35;
            }
            ++v34;
LABEL_79:
            v36 = *v34;
            goto LABEL_80;
          }
          if ( !VLDecodeTableRoot[(unsigned __int64)v44 >> 22] )
          {
            v50 = (v44 >> 19) - 7936;
            v47 = VLDecodeTableExtra[v50];
            v48 = VLDecodeTableExtra[v50] & 0xF;
            goto LABEL_73;
          }
          v39 -= 16;
          if ( v39 < 0 )
          {
            v48 = 16;
LABEL_77:
            v39 += v48;
LABEL_78:
            *((_DWORD *)v36 + 3) = v44;
            --v35;
            *((_BYTE *)v36 + 16) = v39;
            *((_DWORD *)v36 + 2) = v42;
            goto LABEL_79;
          }
          v49 = (v44 >> 15) & 0x3FC;
          if ( (v44 & 0x10000) != 0 )
            v49 = -v49;
          v44 <<= 16;
          v38 = (unsigned __int8 **)*v35;
          *(_WORD *)(v40 + 2LL * (unsigned __int8)nzigtable[2 * v42]) = (_WORD)v49 << byte_180022A61[2 * v42];
          ++v42;
        }
      }
    }
    v53 = *v34;
    if ( *v34 )
    {
      v54 = v86;
      do
      {
        *v54 = v53;
        v53 = *++v34;
        ++v54;
      }
      while ( *v34 );
      v86 = v54;
    }
    result = *v35;
    v55 = v84;
    if ( *v35 )
    {
      do
      {
        *v55 = result;
        result = *--v35;
        --v55;
      }
      while ( *v35 );
      v84 = v55;
    }
LABEL_98:
    v3 = v85 + 80;
    v5 = (char *)(v88 + 80);
    v85 += 80;
    v59 = v82-- == 1;
    v88 += 80;
    if ( !v59 )
    {
      v4 = a1;
      continue;
    }
    break;
  }
  if ( !v83 )
  {
    result = (unsigned __int64)v86;
    v60 = (__int64 **)v91;
    v61 = (unsigned __int8 ***)&v92;
    *v86 = 0;
    *v55 = 0;
    for ( i = (__int64 *)v91[0]; ; i = *v60 )
    {
      if ( !i )
        return result;
      v63 = *v61;
      if ( !*v61 )
        return result;
      v64 = *((_BYTE *)v63 + 16) + *((_BYTE *)i + 16);
      v65 = *i;
      v66 = *v63;
      v67 = *((_DWORD *)i + 2);
      v68 = *((_DWORD *)v63 + 2);
      v69 = *((_DWORD *)i + 3) + (*((_DWORD *)v63 + 3) >> *((_BYTE *)i + 16));
      while ( 1 )
      {
        while ( 1 )
        {
          if ( v64 < 16 && v68 > 0 )
          {
            v66 += 2;
            if ( (unsigned __int64)v66 < *(_QWORD *)a1
              || (unsigned __int64)&v66[-*(_QWORD *)a1] >= *(unsigned int *)(a1 + 8) )
            {
              v70 = 0xFFFF;
            }
            else
            {
              v70 = v66[1] + (*v66 << 8);
            }
            v71 = 16 - v64;
            v64 += 16;
            v69 += v70 << v71;
            --v68;
            if ( v67 >= 1664 )
              v67 = 0;
          }
          result = (unsigned __int64)v69 >> 22;
          v72 = VLDecodeTableRoot[result];
          v73 = VLDecodeTableRoot[result] & 0xF;
          if ( !v73 )
            break;
LABEL_119:
          v64 -= v73;
          if ( v64 < 0 )
            goto LABEL_123;
          v69 <<= v73;
          v67 += (v72 >> 4) & 0x3F;
          if ( BYTE1(v72) > 3u )
          {
            v75 = byte_180022A61[2 * v67];
            v76 = (unsigned __int8)nzigtable[2 * v67++];
            *(_WORD *)(v65 + 2 * v76) = (unsigned __int16)(v72 >> 8) << v75;
          }
        }
        if ( v72 > 0 )
          break;
        if ( !VLDecodeTableRoot[result] )
        {
          result = (v69 >> 19) - 7936;
          v72 = VLDecodeTableExtra[result];
          v73 = VLDecodeTableExtra[result] & 0xF;
          goto LABEL_119;
        }
        v64 -= 16;
        if ( v64 < 0 )
        {
          v73 = 16;
LABEL_123:
          v64 += v73;
LABEL_124:
          *((_DWORD *)i + 3) = v69;
          --v61;
          *((_BYTE *)i + 16) = v64;
          *((_DWORD *)i + 2) = v67;
          goto LABEL_125;
        }
        v74 = (v69 >> 15) & 0x3FC;
        if ( (v69 & 0x10000) != 0 )
          v74 = -v74;
        v69 <<= 16;
        v63 = *v61;
        *(_WORD *)(v65 + 2LL * (unsigned __int8)nzigtable[2 * v67]) = (_WORD)v74 << byte_180022A61[2 * v67];
        ++v67;
      }
      if ( v64 < 4 )
        goto LABEL_124;
      v77 = 16 * v69;
      v78 = v64 - 4;
      if ( v78 <= 16 )
      {
        result = v77;
      }
      else
      {
        v78 -= 16;
        v66 -= 2;
        ++v68;
        result = v77 & (-1 << (32 - v78));
      }
      if ( v78 || v68 )
      {
        *((_DWORD *)v63 + 3) = result;
        *((_BYTE *)v63 + 16) = v78;
        *v63 = v66;
        *((_DWORD *)v63 + 2) = v68;
      }
      else
      {
        --v61;
      }
      ++v60;
LABEL_125:
      ;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016a30  mov     [rsp-8+arg_0], rbx
0x180016a35  push    rbp
0x180016a36  push    rsi
0x180016a37  push    rdi
0x180016a38  push    r12
0x180016a3a  push    r13
0x180016a3c  push    r14
0x180016a3e  push    r15
0x180016a40  lea     rbp, [rsp-390h]
0x180016a48  sub     rsp, 490h
0x180016a4f  mov     rax, cs:__security_cookie
0x180016a56  xor     rax, rsp
0x180016a59  mov     [rbp+3C0h+var_40], rax
0x180016a60  mov     rbx, rdx
0x180016a63  mov     [rsp+4C0h+var_478], rdx
0x180016a68  xor     edx, edx; Val
0x180016a6a  mov     [rsp+4C0h+var_4A0], r8
0x180016a6f  mov     rdi, rcx
0x180016a72  mov     [rsp+4C0h+var_498], rcx
0x180016a77  lea     rcx, [rsp+4C0h+var_450]; void *
0x180016a7c  lea     r8d, [rdx+40h]; Size
0x180016a80  call    memset_0
0x180016a85  xor     edx, edx; Val
0x180016a87  lea     rcx, [rbp+3C0h+var_410]; void *
0x180016a8b  mov     r8d, 100h; Size
0x180016a91  call    memset_0
0x180016a96  lea     rax, [rbp+3C0h+var_410]
0x180016a9a  mov     [rsp+4C0h+var_488], 0
0x180016aa2  mov     [rsp+4C0h+var_470], rax
0x180016aa7  lea     rdx, [rbx+3]
0x180016aab  lea     rax, [rbp+3C0h+var_318]
0x180016ab2  mov     [rsp+4C0h+var_460], rdx
0x180016ab7  mov     [rsp+4C0h+var_480], rax
0x180016abc  lea     rax, [rbp+3C0h+var_310]
0x180016ac3  mov     [rsp+4C0h+var_468], rax
0x180016ac8  mov     [rsp+4C0h+var_48C], 5
0x180016ad0  jmp     short loc_180016AD7
0x180016ad2  mov     rdi, [rsp+4C0h+var_498]
0x180016ad7  lea     r11, cs:180000000h
0x180016ade  cmp     rdx, [rdi]
0x180016ae1  jb      short loc_180016B0B
0x180016ae3  mov     eax, [rdi+8]
0x180016ae6  mov     rcx, rdx
0x180016ae9  sub     rcx, [rdi]
0x180016aec  cmp     rcx, rax
0x180016aef  ja      short loc_180016B0B
0x180016af1  mov     cl, [rdx]
0x180016af3  lea     r14, [rsp+4C0h+var_450]
0x180016af8  xor     r12d, r12d
0x180016afb  lea     r15, [rbp+3C0h+var_418]
0x180016aff  mov     [rsp+4C0h+var_490], r12d
0x180016b04  test    cl, 0F0h
0x180016b07  jz      short loc_180016B30
0x180016b09  jmp     short loc_180016B16
0x180016b0b  mov     cl, 0FFh
0x180016b0d  lea     r14, [rsp+4C0h+var_450]
0x180016b12  lea     r15, [rbp+3C0h+var_418]
0x180016b16  xor     r12d, r12d
0x180016b19  mov     [rsp+4C0h+var_488], 1
0x180016b21  mov     al, cl
0x180016b23  and     al, 70h
0x180016b25  cmp     al, 70h ; 'p'
0x180016b27  setz    r12b
0x180016b2b  mov     [rsp+4C0h+var_490], r12d
0x180016b30  mov     r12, [rsp+4C0h+var_468]
0x180016b35  mov     r10, [rsp+4C0h+var_4A0]
0x180016b3a  movzx   r13d, cl
0x180016b3e  and     r13d, 0Fh
0x180016b42  xor     esi, esi
0x180016b44  jmp     short loc_180016B52
0x180016b46  mov     rdi, [rsp+4C0h+var_498]
0x180016b4b  lea     r11, cs:180000000h
0x180016b52  movzx   r8d, rva offset2[r11+rsi*4]
0x180016b5b  lea     rdx, [rbx+r8]
0x180016b5f  cmp     rdx, [rdi]
0x180016b62  jb      short loc_180016B83
0x180016b64  mov     eax, [rdi+8]
0x180016b67  mov     rcx, rdx
0x180016b6a  sub     rcx, [rdi]
0x180016b6d  cmp     rcx, rax
0x180016b70  jnb     short loc_180016B83
0x180016b72  movzx   r9d, byte ptr [rdx]
0x180016b76  movzx   eax, byte ptr [rdx+1]
0x180016b7a  shl     r9d, 8
0x180016b7e  add     r9d, eax
0x180016b81  jmp     short loc_180016B89
0x180016b83  mov     r9d, 0FFFFh
0x180016b89  mov     eax, r9d
0x180016b8c  mov     [r10], r9w
0x180016b90  cmp     esi, 4
0x180016b93  mov     dl, 14h
0x180016b95  sbb     edi, edi
0x180016b97  and     eax, 70h
0x180016b9a  add     eax, r13d
0x180016b9d  shl     r9d, 1Ch
0x180016ba1  and     edi, 2
0x180016ba4  add     edi, 3
0x180016ba7  movzx   ebx, rva VLDecodeZigOffset720[r11+rax*2]
0x180016bb0  mov     r11, [rsp+4C0h+var_478]
0x180016bb5  mov     rax, [rsp+4C0h+var_498]
0x180016bba  add     r11, 2
0x180016bbe  add     r11, r8
0x180016bc1  cmp     r11, [rax]
0x180016bc4  jb      short loc_180016BE6
0x180016bc6  mov     rcx, r11
0x180016bc9  sub     rcx, [rax]
0x180016bcc  mov     eax, [rax+8]
0x180016bcf  cmp     rcx, rax
0x180016bd2  jnb     short loc_180016BE6
0x180016bd4  movzx   r8d, byte ptr [r11]
0x180016bd8  movzx   eax, byte ptr [r11+1]
0x180016bdd  shl     r8d, 8
0x180016be1  add     r8d, eax
0x180016be4  jmp     short loc_180016BEC
0x180016be6  mov     r8d, 0FFFFh
0x180016bec  shl     r8d, 0Ch
0x180016bf0  add     r8d, r9d
0x180016bf3  jmp     short loc_180016BFA
0x180016bf5  mov     r10, [rsp+4C0h+var_4A0]
0x180016bfa  cmp     dl, 10h
0x180016bfd  jge     short loc_180016C57
0x180016bff  test    edi, edi
0x180016c01  jle     short loc_180016C57
0x180016c03  mov     rax, [rsp+4C0h+var_498]
0x180016c08  add     r11, 2
0x180016c0c  cmp     r11, [rax]
0x180016c0f  jb      short loc_180016C31
0x180016c11  mov     rcx, r11
0x180016c14  sub     rcx, [rax]
0x180016c17  mov     eax, [rax+8]
0x180016c1a  cmp     rcx, rax
0x180016c1d  jnb     short loc_180016C31
0x180016c1f  movzx   r9d, byte ptr [r11]
0x180016c23  movzx   eax, byte ptr [r11+1]
0x180016c28  shl     r9d, 8
0x180016c2c  add     r9d, eax
0x180016c2f  jmp     short loc_180016C37
0x180016c31  mov     r9d, 0FFFFh
0x180016c37  movsx   eax, dl
0x180016c3a  mov     ecx, 10h
0x180016c3f  sub     ecx, eax
0x180016c41  add     dl, 10h
0x180016c44  shl     r9d, cl
0x180016c47  xor     eax, eax
0x180016c49  add     r8d, r9d
0x180016c4c  dec     edi
0x180016c4e  cmp     ebx, 680h
0x180016c54  cmovge  ebx, eax
0x180016c57  lea     rcx, cs:180000000h
0x180016c5e  mov     eax, r8d
0x180016c61  shr     rax, 16h
0x180016c65  movsx   r9d, rva VLDecodeTableRoot[rcx+rax*2]
0x180016c6e  mov     ecx, r9d
0x180016c71  and     ecx, 0Fh
0x180016c74  jnz     loc_180016D01
0x180016c7a  test    r9d, r9d
0x180016c7d  jg      loc_180016DC6
0x180016c83  jz      short loc_180016CE0
0x180016c85  add     dl, 0F0h
0x180016c88  js      loc_180016D57
0x180016c8e  mov     r9d, r8d
0x180016c91  movsxd  rcx, ebx
0x180016c94  shr     r9d, 0Fh
0x180016c98  lea     rax, cs:180000000h
0x180016c9f  and     r9d, 3FCh
0x180016ca6  movzx   eax, rva nzigtable[rax+rcx*2]
0x180016cae  bt      r8d, 10h
0x180016cb3  jnb     short loc_180016CB8
0x180016cb5  neg     r9d
0x180016cb8  lea     r10, cs:180000000h
0x180016cbf  shl     r8d, 10h
0x180016cc3  mov     cl, rva byte_180022A61[r10+rcx*2]
0x180016ccb  mov     r10, [rsp+4C0h+var_4A0]
0x180016cd0  shl     r9w, cl
0x180016cd4  inc     ebx
0x180016cd6  mov     [r10+rax*2], r9w
0x180016cdb  jmp     loc_180016BFA
0x180016ce0  mov     eax, r8d
0x180016ce3  lea     rcx, cs:180000000h
0x180016cea  shr     eax, 13h
0x180016ced  sub     eax, 1F00h
0x180016cf2  movsx   r9d, rva VLDecodeTableExtra[rcx+rax*2]
0x180016cfb  mov     ecx, r9d
0x180016cfe  and     ecx, 0Fh
0x180016d01  sub     dl, cl
0x180016d03  js      short loc_180016D5C
0x180016d05  sar     r9d, 4
0x180016d09  mov     r10d, r9d
0x180016d0c  shl     r8d, cl
0x180016d0f  and     r9d, 3Fh
0x180016d13  sar     r10d, 4
0x180016d17  add     ebx, r9d
0x180016d1a  cmp     r10b, 3
0x180016d1e  jbe     loc_180016BF5
0x180016d24  movsxd  rax, ebx
0x180016d27  lea     r9, cs:180000000h
0x180016d2e  mov     cl, rva byte_180022A61[r9+rax*2]
0x180016d36  movzx   eax, rva nzigtable[r9+rax*2]
0x180016d3f  mov     r9, [rsp+4C0h+var_4A0]
0x180016d44  shl     r10w, cl
0x180016d48  inc     ebx
0x180016d4a  mov     [r9+rax*2], r10w
0x180016d4f  mov     r10, r9
0x180016d52  jmp     loc_180016BFA
0x180016d57  mov     ecx, 10h
0x180016d5c  add     dl, cl
0x180016d5e  mov     [r14], r12
0x180016d61  add     r14, 8
0x180016d65  mov     [r12+0Ch], r8d
0x180016d6a  mov     [r12+8], ebx
0x180016d6f  mov     [r12], r10
0x180016d73  mov     [r12+10h], dl
0x180016d78  add     r12, 18h
0x180016d7c  mov     rbx, [rsp+4C0h+var_478]
0x180016d81  sub     r10, 0FFFFFFFFFFFFFF80h
0x180016d85  inc     esi
0x180016d87  mov     [rsp+4C0h+var_4A0], r10
0x180016d8c  cmp     esi, 6
0x180016d8f  jl      loc_180016B46
0x180016d95  cmp     [rsp+4C0h+var_490], 0
0x180016d9a  mov     [rsp+4C0h+var_468], r12
0x180016d9f  jnz     loc_180017082
0x180016da5  mov     qword ptr [r14], 0
0x180016dac  lea     rsi, [rsp+4C0h+var_450]
0x180016db1  mov     qword ptr [r15], 0
0x180016db8  lea     rbx, [rbp+3C0h+var_418]
0x180016dbc  mov     r11, [rsp+4C0h+var_450]
0x180016dc1  jmp     loc_180016FD6
0x180016dc6  cmp     dl, 4
0x180016dc9  jl      short loc_180016D5E
0x180016dcb  shl     r8d, 4
0x180016dcf  sub     dl, 4
0x180016dd2  cmp     dl, 10h
0x180016dd5  jle     short loc_180016DF4
0x180016dd7  sub     dl, 10h
0x180016dda  mov     ecx, 20h ; ' '
0x180016ddf  movsx   eax, dl
0x180016de2  sub     r11, 2
0x180016de6  sub     ecx, eax
0x180016de8  inc     edi
0x180016dea  or      eax, 0FFFFFFFFh
0x180016ded  shl     eax, cl
0x180016def  and     eax, r8d
0x180016df2  jmp     short loc_180016DF7
0x180016df4  mov     eax, r8d
0x180016df7  test    dl, dl
0x180016df9  jnz     short loc_180016E03
0x180016dfb  test    edi, edi
0x180016dfd  jz      loc_180016D7C
0x180016e03  mov     [r15], r12
0x180016e06  sub     r15, 8
0x180016e0a  mov     [r12+0Ch], eax
0x180016e0f  mov     [r12+8], edi
0x180016e14  mov     [r12], r11
0x180016e18  jmp     loc_180016D73
0x180016e1d  mov     rdi, [rbx]
0x180016e20  test    rdi, rdi
0x180016e23  jz      loc_180016FDF
0x180016e29  mov     cl, [r11+10h]
0x180016e2d  lea     r8, cs:180000000h
0x180016e34  mov     r9d, [rdi+0Ch]
0x180016e38  mov     dl, cl
0x180016e3a  add     dl, [rdi+10h]
0x180016e3d  mov     r13, [r11]
0x180016e40  mov     r15, [rdi]
0x180016e43  mov     r14d, [r11+8]
0x180016e47  mov     r12d, [rdi+8]
0x180016e4b  shr     r9d, cl
0x180016e4e  add     r9d, [r11+0Ch]
0x180016e52  mov     r10d, 10h
0x180016e58  cmp     dl, r10b
0x180016e5b  jge     short loc_180016EBE
0x180016e5d  test    r12d, r12d
0x180016e60  jle     short loc_180016EBE
0x180016e62  mov     rax, [rsp+4C0h+var_498]
0x180016e67  add     r15, 2
0x180016e6b  cmp     r15, [rax]
0x180016e6e  jb      short loc_180016E90
0x180016e70  mov     rcx, r15
0x180016e73  sub     rcx, [rax]
0x180016e76  mov     eax, [rax+8]
0x180016e79  cmp     rcx, rax
0x180016e7c  jnb     short loc_180016E90
0x180016e7e  movzx   r8d, byte ptr [r15]
0x180016e82  movzx   eax, byte ptr [r15+1]
0x180016e87  shl     r8d, 8
0x180016e8b  add     r8d, eax
0x180016e8e  jmp     short loc_180016E96
0x180016e90  mov     r8d, 0FFFFh
0x180016e96  movsx   eax, dl
0x180016e99  mov     ecx, r10d
0x180016e9c  sub     ecx, eax
0x180016e9e  add     dl, r10b
0x180016ea1  shl     r8d, cl
0x180016ea4  xor     eax, eax
0x180016ea6  add     r9d, r8d
0x180016ea9  dec     r12d
0x180016eac  cmp     r14d, 680h
0x180016eb3  lea     r8, cs:180000000h
0x180016eba  cmovge  r14d, eax
  ... truncated ...
```
