# DecompressCBlock16To8

- ea: `0x180003f30`
- end: `0x180004504`
- name: `DecompressCBlock16To8`
- size: `1492`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800056f0`

## callees

- `0x180003f30`

## pseudocode

```c
__int16 *__fastcall DecompressCBlock16To8(int *a1, __int16 *a2, unsigned int *a3, int a4, int *a5)
{
  __int64 v6; // r15
  unsigned int v7; // r13d
  unsigned int v11; // edx
  unsigned __int16 v12; // bp
  __int64 v13; // rbx
  __int64 v14; // rdi
  unsigned int v15; // r9d
  int v16; // r11d
  char v17; // dl
  __int64 v18; // rdx
  __int16 v19; // ax
  __int16 *v20; // rbx
  __int16 v21; // ax
  __int64 v22; // r14
  unsigned int v23; // edx
  int v24; // r11d
  __int16 v25; // ax
  int v26; // r9d
  __int16 v27; // ax
  int v28; // r8d
  __int16 v29; // cx
  int v30; // edi
  int v31; // esi
  int v32; // ebx
  __int64 v33; // r14
  char v34; // al
  __int64 v35; // rax
  int v36; // edx
  int v37; // r8d
  int v38; // r9d
  int v39; // r10d
  int v40; // r11d
  __int16 *v41; // rbx
  unsigned int v42; // edx
  __int16 v43; // ax
  __int64 v44; // r14
  int v45; // r10d
  __int16 v46; // ax
  int v47; // r9d
  __int16 v48; // ax
  int v49; // r8d
  __int16 v50; // cx
  int v51; // esi
  int v52; // ebx
  __int64 v53; // rdi
  int v54; // r14d
  char v55; // al
  __int64 v56; // rax
  int v57; // edx
  int v58; // r8d
  int v59; // r9d
  int v60; // r10d
  int v61; // r11d
  __int64 v62; // r8
  int v63; // r9d
  __int16 v64; // cx
  __int64 v65; // rdi
  unsigned int v66; // r14d
  int v67; // r13d
  int v68; // esi
  char v69; // al
  __int64 v70; // rax
  int v71; // edx
  int v72; // r8d
  int v73; // r9d
  int v74; // r10d
  int v75; // r11d
  char v76; // cl
  int v77; // [rsp+4h] [rbp-64h]
  int v78; // [rsp+4h] [rbp-64h]
  __int16 *v79; // [rsp+8h] [rbp-60h]

  v6 = a4;
  v7 = 0;
  if ( *a5 > 0 )
  {
    --*a5;
    return a2;
  }
  v11 = *a3;
  if ( *a3 <= 1 )
  {
    v12 = 0;
LABEL_13:
    v19 = 0;
    v20 = a2;
LABEL_43:
    v62 = lpScale;
    v79 = v20;
    v63 = *(unsigned __int16 *)(lpScale + 2LL * (v19 & 0x7FFF));
    if ( v11 > 1 )
    {
      v64 = *v20;
      *a3 = v11 - 2;
      v79 = v20 + 1;
    }
    else
    {
      v64 = 0;
    }
    v65 = lpLookup;
    v66 = 0;
    v67 = v63;
    v68 = *(unsigned __int16 *)(v62 + 2LL * (v64 & 0x7FFF));
    do
    {
      v69 = v66++;
      v70 = 2LL * (v69 & 3);
      v71 = dword_18000953C[2 * v70];
      v72 = dword_180009538[2 * v70];
      v73 = dword_180009534[2 * v70];
      v74 = ditherr[2 * v70];
      v75 = *(unsigned __int8 *)(v74 + v68 + v65)
          | ((*(unsigned __int8 *)(v73 + v68 + v65)
            | ((*(unsigned __int8 *)(v72 + v68 + v65) | (*(unsigned __int8 *)(v71 + v68 + v65) << 8)) << 8)) << 8);
      v76 = v12;
      v12 >>= 4;
      *a1 = v75
          ^ ExpansionTable[v76 & 0xF]
          & (v75
           ^ (*(unsigned __int8 *)(v74 + v67 + v65)
            | ((*(unsigned __int8 *)(v73 + v67 + v65)
              | ((*(unsigned __int8 *)(v72 + v67 + v65) | (*(unsigned __int8 *)(v71 + v67 + v65) << 8)) << 8)) << 8)));
      a1 = (int *)((char *)a1 + v6);
    }
    while ( v66 < 4 );
    return v79;
  }
  v12 = *a2;
  v11 -= 2;
  ++a2;
  *a3 = v11;
  if ( (v12 & 0x8000u) != 0 )
  {
    if ( (v12 & 0xFC00) == 0x8400 )
    {
      *a5 = (v12 & 0x3FF) - 1;
    }
    else
    {
      v13 = lpLookup;
      v14 = a4;
      v15 = 0;
      v16 = *(unsigned __int16 *)(lpScale + 2LL * (v12 & 0x7FFF));
      do
      {
        v17 = v15++;
        v18 = 2LL * (v17 & 3);
        *a1 = *(unsigned __int8 *)(v16 + ditherr[2 * v18] + v13)
            | ((*(unsigned __int8 *)(v16 + dword_180009534[2 * v18] + v13)
              | ((*(unsigned __int8 *)(v16 + dword_180009538[2 * v18] + v13)
                | (*(unsigned __int8 *)(v16 + dword_18000953C[2 * v18] + v13) << 8)) << 8)) << 8);
        a1 = (int *)((char *)a1 + v14);
      }
      while ( v15 < 4 );
    }
    return a2;
  }
  if ( v11 <= 1 )
    goto LABEL_13;
  v21 = *a2;
  v20 = a2 + 1;
  if ( *a2 >= 0 )
  {
    v11 -= 2;
    *a3 = v11;
    v19 = *a2;
    goto LABEL_43;
  }
  v22 = lpScale;
  v23 = v11 - 2;
  v79 = a2 + 1;
  *a3 = v23;
  v24 = *(unsigned __int16 *)(v22 + 2LL * (v21 & 0x7FFF));
  if ( v23 > 1 )
  {
    v25 = a2[1];
    v20 = a2 + 2;
    v23 -= 2;
    v79 = a2 + 2;
    *a3 = v23;
  }
  else
  {
    v25 = 0;
  }
  v26 = *(unsigned __int16 *)(v22 + 2LL * (v25 & 0x7FFF));
  if ( v23 > 1 )
  {
    v27 = *v20++;
    v23 -= 2;
    v79 = v20;
    *a3 = v23;
  }
  else
  {
    v27 = 0;
  }
  v28 = *(unsigned __int16 *)(v22 + 2LL * (v27 & 0x7FFF));
  if ( v23 > 1 )
  {
    v29 = *v20;
    *a3 = v23 - 2;
    v79 = v20 + 1;
  }
  else
  {
    v29 = 0;
  }
  v30 = v28;
  v77 = v24;
  v31 = v26;
  v32 = *(unsigned __int16 *)(v22 + 2LL * (v29 & 0x7FFF));
  v33 = lpLookup;
  do
  {
    v34 = v7++;
    v35 = 2LL * (v34 & 3);
    v36 = dword_18000953C[2 * v35];
    v37 = dword_180009538[2 * v35];
    v38 = dword_180009534[2 * v35];
    v39 = ditherr[2 * v35];
    v40 = *(unsigned __int8 *)(v39 + v31 + v33)
        | ((*(unsigned __int8 *)(v38 + v31 + v33)
          | ((*(unsigned __int8 *)(v37 + v32 + v33) | (*(unsigned __int8 *)(v36 + v32 + v33) << 8)) << 8)) << 8);
    LOBYTE(v35) = v12;
    v12 >>= 4;
    *a1 = v40
        ^ ExpansionTable[v35 & 0xF]
        & (v40
         ^ (*(unsigned __int8 *)(v39 + v77 + v33)
          | ((*(unsigned __int8 *)(v38 + v77 + v33)
            | ((*(unsigned __int8 *)(v37 + v30 + v33) | (*(unsigned __int8 *)(v36 + v30 + v33) << 8)) << 8)) << 8)));
    a1 = (int *)((char *)a1 + v6);
  }
  while ( v7 < 2 );
  v41 = v79;
  v42 = *a3;
  if ( *a3 > 1 )
  {
    v43 = *v79;
    v41 = v79 + 1;
    v42 -= 2;
    ++v79;
    *a3 = v42;
  }
  else
  {
    v43 = 0;
  }
  v44 = lpScale;
  v45 = *(unsigned __int16 *)(lpScale + 2LL * (v43 & 0x7FFF));
  if ( v42 > 1 )
  {
    v46 = *v41++;
    v42 -= 2;
    v79 = v41;
    *a3 = v42;
  }
  else
  {
    v46 = 0;
  }
  v47 = *(unsigned __int16 *)(v44 + 2LL * (v46 & 0x7FFF));
  if ( v42 > 1 )
  {
    v48 = *v41++;
    v42 -= 2;
    v79 = v41;
    *a3 = v42;
  }
  else
  {
    v48 = 0;
  }
  v49 = *(unsigned __int16 *)(v44 + 2LL * (v48 & 0x7FFF));
  if ( v42 > 1 )
  {
    v50 = *v41++;
    *a3 = v42 - 2;
    v79 = v41;
  }
  else
  {
    v50 = 0;
  }
  if ( v7 >= 4 )
    return v41;
  v51 = *(unsigned __int16 *)(v44 + 2LL * (v50 & 0x7FFF));
  v52 = v49;
  v53 = lpLookup;
  v54 = v47;
  v78 = v45;
  do
  {
    v55 = v7++;
    v56 = 2LL * (v55 & 3);
    v57 = dword_18000953C[2 * v56];
    v58 = dword_180009538[2 * v56];
    v59 = dword_180009534[2 * v56];
    v60 = ditherr[2 * v56];
    v61 = *(unsigned __int8 *)(v60 + v54 + v53)
        | ((*(unsigned __int8 *)(v59 + v54 + v53)
          | ((*(unsigned __int8 *)(v58 + v51 + v53) | (*(unsigned __int8 *)(v57 + v51 + v53) << 8)) << 8)) << 8);
    LOBYTE(v56) = v12;
    v12 >>= 4;
    *a1 = v61
        ^ ExpansionTable[v56 & 0xF]
        & (v61
         ^ (*(unsigned __int8 *)(v60 + v78 + v53)
          | ((*(unsigned __int8 *)(v59 + v78 + v53)
            | ((*(unsigned __int8 *)(v58 + v52 + v53) | (*(unsigned __int8 *)(v57 + v52 + v53) << 8)) << 8)) << 8)));
    a1 = (int *)((char *)a1 + v6);
  }
  while ( v7 < 4 );
  return v79;
}

```

## disassembly

```asm
0x180003f30  mov     [rsp+arg_10], r8
0x180003f35  push    rbx
0x180003f36  push    rbp
0x180003f37  push    rsi
0x180003f38  push    rdi
0x180003f39  push    r12
0x180003f3b  push    r13
0x180003f3d  push    r14
0x180003f3f  push    r15
0x180003f41  sub     rsp, 28h
0x180003f45  mov     rdi, r8
0x180003f48  movsxd  r15, r9d
0x180003f4b  mov     r8, [rsp+68h+arg_20]
0x180003f53  xor     r13d, r13d
0x180003f56  mov     r10, rdx
0x180003f59  mov     r12, rcx
0x180003f5c  mov     eax, [r8]
0x180003f5f  test    eax, eax
0x180003f61  jle     short loc_180003F70
0x180003f63  dec     eax
0x180003f65  mov     [r8], eax
0x180003f68  mov     rax, r10
0x180003f6b  jmp     loc_1800044F3
0x180003f70  mov     edx, [rdi]
0x180003f72  mov     ecx, 1
0x180003f77  cmp     edx, ecx
0x180003f79  ja      short loc_180003F83
0x180003f7b  mov     ebp, r13d
0x180003f7e  jmp     loc_18000405C
0x180003f83  movzx   ebp, word ptr [r10]
0x180003f87  add     edx, 0FFFFFFFEh
0x180003f8a  add     r10, 2
0x180003f8e  mov     [rdi], edx
0x180003f90  test    bp, bp
0x180003f93  jns     loc_180004058
0x180003f99  movzx   ecx, bp
0x180003f9c  mov     eax, ecx
0x180003f9e  and     eax, 0FFFFFC00h
0x180003fa3  cmp     eax, 8400h
0x180003fa8  jnz     short loc_180003FB7
0x180003faa  and     ecx, 3FFh
0x180003fb0  dec     ecx
0x180003fb2  mov     [r8], ecx
0x180003fb5  jmp     short loc_180003F68
0x180003fb7  mov     rax, cs:lpScale
0x180003fbe  mov     esi, 7FFFh
0x180003fc3  mov     rbx, cs:lpLookup
0x180003fca  and     rbp, rsi
0x180003fcd  mov     rdi, r15
0x180003fd0  mov     r9d, r13d
0x180003fd3  lea     r15, cs:180000000h
0x180003fda  movzx   r11d, word ptr [rax+rbp*2]
0x180003fdf  mov     edx, r9d
0x180003fe2  inc     r9d
0x180003fe5  and     edx, 3
0x180003fe8  add     rdx, rdx
0x180003feb  mov     eax, ds:rva dword_18000953C[r15+rdx*8]
0x180003ff3  add     eax, r11d
0x180003ff6  cdqe
0x180003ff8  movzx   r8d, byte ptr [rax+rbx]
0x180003ffd  mov     eax, ds:rva dword_180009538[r15+rdx*8]
0x180004005  shl     r8d, 8
0x180004009  add     eax, r11d
0x18000400c  cdqe
0x18000400e  movzx   ecx, byte ptr [rax+rbx]
0x180004012  mov     eax, ds:rva dword_180009534[r15+rdx*8]
0x18000401a  or      r8d, ecx
0x18000401d  shl     r8d, 8
0x180004021  add     eax, r11d
0x180004024  cdqe
0x180004026  movzx   ecx, byte ptr [rax+rbx]
0x18000402a  or      r8d, ecx
0x18000402d  mov     ecx, ds:rva ditherr[r15+rdx*8]
0x180004035  add     ecx, r11d
0x180004038  shl     r8d, 8
0x18000403c  movsxd  rcx, ecx
0x18000403f  movzx   edx, byte ptr [rcx+rbx]
0x180004043  or      r8d, edx
0x180004046  mov     [r12], r8d
0x18000404a  add     r12, rdi
0x18000404d  cmp     r9d, 4
0x180004051  jb      short loc_180003FDF
0x180004053  jmp     loc_180003F68
0x180004058  cmp     edx, ecx
0x18000405a  ja      short loc_180004067
0x18000405c  mov     eax, r13d
0x18000405f  mov     rbx, r10
0x180004062  jmp     loc_1800043B5
0x180004067  movzx   eax, word ptr [r10]
0x18000406b  lea     rbx, [r10+2]
0x18000406f  test    ax, ax
0x180004072  jns     loc_1800043AA
0x180004078  mov     r14, cs:lpScale
0x18000407f  add     edx, 0FFFFFFFEh
0x180004082  mov     esi, 7FFFh
0x180004087  mov     [rsp+68h+var_60], rbx
0x18000408c  and     rax, rsi
0x18000408f  mov     [rdi], edx
0x180004091  movzx   r11d, word ptr [r14+rax*2]
0x180004096  cmp     edx, ecx
0x180004098  ja      short loc_18000409F
0x18000409a  mov     eax, r13d
0x18000409d  jmp     short loc_1800040B2
0x18000409f  movzx   eax, word ptr [r10+2]
0x1800040a4  add     rbx, 2
0x1800040a8  add     edx, 0FFFFFFFEh
0x1800040ab  mov     [rsp+68h+var_60], rbx
0x1800040b0  mov     [rdi], edx
0x1800040b2  movzx   eax, ax
0x1800040b5  and     rax, rsi
0x1800040b8  movzx   r9d, word ptr [r14+rax*2]
0x1800040bd  cmp     edx, ecx
0x1800040bf  ja      short loc_1800040C6
0x1800040c1  mov     eax, r13d
0x1800040c4  jmp     short loc_1800040D7
0x1800040c6  movzx   eax, word ptr [rbx]
0x1800040c9  add     rbx, 2
0x1800040cd  add     edx, 0FFFFFFFEh
0x1800040d0  mov     [rsp+68h+var_60], rbx
0x1800040d5  mov     [rdi], edx
0x1800040d7  movzx   eax, ax
0x1800040da  and     rax, rsi
0x1800040dd  movzx   r8d, word ptr [r14+rax*2]
0x1800040e2  cmp     edx, ecx
0x1800040e4  ja      short loc_1800040EB
0x1800040e6  mov     ecx, r13d
0x1800040e9  jmp     short loc_1800040FC
0x1800040eb  movzx   ecx, word ptr [rbx]
0x1800040ee  lea     eax, [rdx-2]
0x1800040f1  add     rbx, 2
0x1800040f5  mov     [rdi], eax
0x1800040f7  mov     [rsp+68h+var_60], rbx
0x1800040fc  movzx   eax, cx
0x1800040ff  mov     edi, r8d
0x180004102  and     rax, rsi
0x180004105  mov     [rsp+68h+var_58], r15
0x18000410a  mov     [rsp+68h+var_64], r11d
0x18000410f  lea     r15, cs:180000000h
0x180004116  mov     esi, r9d
0x180004119  movzx   ebx, word ptr [r14+rax*2]
0x18000411e  mov     r14, cs:lpLookup
0x180004125  mov     eax, r13d
0x180004128  inc     r13d
0x18000412b  and     eax, 3
0x18000412e  add     rax, rax
0x180004131  mov     edx, ds:rva dword_18000953C[r15+rax*8]
0x180004139  mov     r8d, ds:rva dword_180009538[r15+rax*8]
0x180004141  mov     r9d, ds:rva dword_180009534[r15+rax*8]
0x180004149  mov     r10d, ds:rva ditherr[r15+rax*8]
0x180004151  lea     eax, [rdx+rbx]
0x180004154  movsxd  rcx, eax
0x180004157  lea     eax, [r8+rbx]
0x18000415b  movzx   r11d, byte ptr [rcx+r14]
0x180004160  movsxd  rcx, eax
0x180004163  shl     r11d, 8
0x180004167  movzx   eax, byte ptr [rcx+r14]
0x18000416c  or      r11d, eax
0x18000416f  lea     eax, [r9+rsi]
0x180004173  movsxd  rcx, eax
0x180004176  shl     r11d, 8
0x18000417a  movzx   eax, byte ptr [rcx+r14]
0x18000417f  or      r11d, eax
0x180004182  lea     eax, [r10+rsi]
0x180004186  movsxd  rcx, eax
0x180004189  shl     r11d, 8
0x18000418d  movzx   eax, byte ptr [rcx+r14]
0x180004192  or      r11d, eax
0x180004195  lea     eax, [rdx+rdi]
0x180004198  movsxd  rcx, eax
0x18000419b  lea     eax, [r8+rdi]
0x18000419f  mov     r8d, [rsp+68h+var_64]
0x1800041a4  movzx   edx, byte ptr [rcx+r14]
0x1800041a9  shl     edx, 8
0x1800041ac  movsxd  rcx, eax
0x1800041af  movzx   eax, byte ptr [rcx+r14]
0x1800041b4  or      edx, eax
0x1800041b6  lea     eax, [r9+r8]
0x1800041ba  shl     edx, 8
0x1800041bd  movsxd  rcx, eax
0x1800041c0  movzx   eax, byte ptr [rcx+r14]
0x1800041c5  or      edx, eax
0x1800041c7  lea     eax, [r10+r8]
0x1800041cb  shl     edx, 8
0x1800041ce  movsxd  rcx, eax
0x1800041d1  movzx   eax, byte ptr [rcx+r14]
0x1800041d6  or      edx, eax
0x1800041d8  movzx   eax, bp
0x1800041db  xor     edx, r11d
0x1800041de  shr     bp, 4
0x1800041e2  and     eax, 0Fh
0x1800041e5  and     edx, ds:rva ExpansionTable[r15+rax*4]
0x1800041ed  xor     edx, r11d
0x1800041f0  mov     [r12], edx
0x1800041f4  add     r12, [rsp+68h+var_58]
0x1800041f9  cmp     r13d, 2
0x1800041fd  jb      loc_180004125
0x180004203  mov     rdi, [rsp+68h+arg_10]
0x18000420b  mov     rbx, [rsp+68h+var_60]
0x180004210  mov     edx, [rdi]
0x180004212  cmp     edx, 1
0x180004215  ja      short loc_18000421B
0x180004217  xor     eax, eax
0x180004219  jmp     short loc_18000422C
0x18000421b  movzx   eax, word ptr [rbx]
0x18000421e  add     rbx, 2
0x180004222  add     edx, 0FFFFFFFEh
0x180004225  mov     [rsp+68h+var_60], rbx
0x18000422a  mov     [rdi], edx
0x18000422c  mov     r14, cs:lpScale
0x180004233  mov     esi, 7FFFh
0x180004238  movzx   eax, ax
0x18000423b  and     rax, rsi
0x18000423e  movzx   r10d, word ptr [r14+rax*2]
0x180004243  cmp     edx, 1
0x180004246  ja      short loc_18000424C
0x180004248  xor     eax, eax
0x18000424a  jmp     short loc_18000425D
0x18000424c  movzx   eax, word ptr [rbx]
0x18000424f  add     rbx, 2
0x180004253  add     edx, 0FFFFFFFEh
0x180004256  mov     [rsp+68h+var_60], rbx
0x18000425b  mov     [rdi], edx
0x18000425d  movzx   eax, ax
0x180004260  and     rax, rsi
0x180004263  movzx   r9d, word ptr [r14+rax*2]
0x180004268  cmp     edx, 1
0x18000426b  ja      short loc_180004271
0x18000426d  xor     eax, eax
0x18000426f  jmp     short loc_180004282
0x180004271  movzx   eax, word ptr [rbx]
0x180004274  add     rbx, 2
0x180004278  add     edx, 0FFFFFFFEh
0x18000427b  mov     [rsp+68h+var_60], rbx
0x180004280  mov     [rdi], edx
0x180004282  movzx   eax, ax
0x180004285  and     rax, rsi
0x180004288  movzx   r8d, word ptr [r14+rax*2]
0x18000428d  cmp     edx, 1
0x180004290  ja      short loc_180004296
0x180004292  xor     ecx, ecx
0x180004294  jmp     short loc_1800042A7
0x180004296  movzx   ecx, word ptr [rbx]
0x180004299  lea     eax, [rdx-2]
0x18000429c  add     rbx, 2
0x1800042a0  mov     [rdi], eax
0x1800042a2  mov     [rsp+68h+var_60], rbx
0x1800042a7  movzx   eax, cx
0x1800042aa  and     rax, rsi
0x1800042ad  cmp     r13d, 4
0x1800042b1  jnb     loc_1800044F0
0x1800042b7  movzx   esi, word ptr [r14+rax*2]
0x1800042bc  mov     ebx, r8d
0x1800042bf  mov     rdi, cs:lpLookup
0x1800042c6  mov     r14d, r9d
0x1800042c9  mov     [rsp+68h+var_64], r10d
0x1800042ce  mov     eax, r13d
0x1800042d1  inc     r13d
0x1800042d4  and     eax, 3
0x1800042d7  add     rax, rax
0x1800042da  mov     edx, ds:rva dword_18000953C[r15+rax*8]
0x1800042e2  mov     r8d, ds:rva dword_180009538[r15+rax*8]
0x1800042ea  mov     r9d, ds:rva dword_180009534[r15+rax*8]
0x1800042f2  mov     r10d, ds:rva ditherr[r15+rax*8]
0x1800042fa  lea     eax, [rdx+rsi]
0x1800042fd  movsxd  rcx, eax
0x180004300  lea     eax, [r8+rsi]
0x180004304  movzx   r11d, byte ptr [rcx+rdi]
0x180004309  movsxd  rcx, eax
0x18000430c  shl     r11d, 8
0x180004310  movzx   eax, byte ptr [rcx+rdi]
0x180004314  or      r11d, eax
0x180004317  lea     eax, [r9+r14]
0x18000431b  movsxd  rcx, eax
0x18000431e  shl     r11d, 8
0x180004322  movzx   eax, byte ptr [rcx+rdi]
0x180004326  or      r11d, eax
0x180004329  lea     eax, [r10+r14]
0x18000432d  movsxd  rcx, eax
0x180004330  shl     r11d, 8
0x180004334  movzx   eax, byte ptr [rcx+rdi]
0x180004338  or      r11d, eax
0x18000433b  lea     eax, [rdx+rbx]
0x18000433e  movsxd  rcx, eax
0x180004341  lea     eax, [r8+rbx]
0x180004345  mov     r8d, [rsp+68h+var_64]
0x18000434a  movzx   edx, byte ptr [rcx+rdi]
0x18000434e  shl     edx, 8
0x180004351  movsxd  rcx, eax
0x180004354  movzx   eax, byte ptr [rcx+rdi]
0x180004358  or      edx, eax
0x18000435a  lea     eax, [r9+r8]
0x18000435e  shl     edx, 8
0x180004361  movsxd  rcx, eax
0x180004364  movzx   eax, byte ptr [rcx+rdi]
0x180004368  or      edx, eax
0x18000436a  lea     eax, [r10+r8]
0x18000436e  shl     edx, 8
0x180004371  movsxd  rcx, eax
0x180004374  movzx   eax, byte ptr [rcx+rdi]
0x180004378  or      edx, eax
  ... truncated ...
```
