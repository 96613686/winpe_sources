# jpeg_make_d_derived_tbl(jpeg_decompress_struct *,uchar,int,d_derived_tbl_tag * *,int)

- ea: `0x1800184a0`
- end: `0x180018bf2`
- name: `?jpeg_make_d_derived_tbl@@YAXPEAUjpeg_decompress_struct@@EHPEAPEAUd_derived_tbl_tag@@H@Z`
- size: `1874`
- prototype: `void __fastcall(struct jpeg_decompress_struct *, unsigned __int8, int, struct d_derived_tbl_tag **, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800182c0`

## callees

- `0x1800184a0`
- `0x180024220`
- `0x1800247c0`
- `0x180070010`

## pseudocode

```c
void __fastcall jpeg_make_d_derived_tbl(
        struct jpeg_decompress_struct *a1,
        char a2,
        unsigned int a3,
        struct d_derived_tbl_tag **a4,
        int a5)
{
  __int64 v5; // rdi
  char v7; // r13
  __int64 v9; // rbx
  __int64 v10; // r10
  char *v11; // rsi
  char *v12; // r10
  int v13; // r11d
  int i; // edi
  int v15; // r14d
  int v16; // r14d
  int v17; // r15d
  int v18; // r12d
  int v19; // edi
  __int64 v20; // rax
  __int64 v21; // rax
  int v22; // edi
  __int64 v23; // rax
  int v24; // edx
  __int64 v25; // r8
  int v26; // edx
  __int64 v27; // r8
  int v28; // edx
  __int64 v29; // r8
  int v30; // edx
  __int64 v31; // r8
  int v32; // edx
  __int64 v33; // r8
  int v34; // edx
  __int64 v35; // r8
  int v36; // edx
  __int64 v37; // r8
  int v38; // edx
  __int64 v39; // r8
  int v40; // edx
  __int64 v41; // r8
  int v42; // edx
  __int64 v43; // r8
  int v44; // edx
  __int64 v45; // r8
  int v46; // edx
  __int64 v47; // r8
  int v48; // edx
  __int64 v49; // r8
  int v50; // edx
  __int64 v51; // r8
  int v52; // edx
  __int64 v53; // r8
  __int64 v54; // rcx
  int v55; // r12d
  int v56; // r9d
  _DWORD *v57; // rdi
  char *v58; // r14
  int v59; // r11d
  int v60; // edi
  int j; // edx
  __int64 v62; // rax
  int v63; // r11d
  int v64; // edi
  struct jpeg_decompress_struct *v65; // r8
  __int64 v66; // rax
  int v68; // [rsp+24h] [rbp-DCh]
  char *v69; // [rsp+28h] [rbp-D8h]
  _DWORD v72[260]; // [rsp+40h] [rbp-C0h]
  char v73[272]; // [rsp+450h] [rbp+350h]

  v5 = (int)a3;
  v7 = a2;
  if ( a3 > 3 )
  {
    *(_DWORD *)(*(_QWORD *)a1 + 40LL) = 50;
    *(_DWORD *)(*(_QWORD *)a1 + 44LL) = a3;
    (**(void (__fastcall ***)(struct jpeg_decompress_struct *))a1)(a1);
  }
  v9 = (__int64)*a4;
  v10 = 3453;
  v11 = (char *)a1 + 274 * v5;
  if ( !v7 )
    v10 = 4549;
  v12 = &v11[v10];
  v69 = v12;
  if ( !v9 )
  {
    v9 = *((_QWORD *)a1 + 211) + 1176LL * ((v7 == 0) + 2 * ((int)v5 + 4 * a5));
    *a4 = (struct d_derived_tbl_tag *)v9;
  }
  v13 = 0;
  *(_QWORD *)(v9 + 144) = v12;
  v68 = 0;
  for ( i = 1; i <= 16; ++i )
  {
    v15 = (unsigned __int8)v12[i];
    if ( v15 + v13 > 256 )
    {
      *(_DWORD *)(*(_QWORD *)a1 + 40LL) = 8;
      (**(void (__fastcall ***)(struct jpeg_decompress_struct *))a1)(a1);
      v12 = v69;
      v13 = v68;
    }
    if ( v15 )
    {
      do
      {
        v66 = v13++;
        v73[v66] = i;
        --v15;
      }
      while ( v15 );
      v68 = v13;
    }
  }
  if ( (unsigned __int64)v13 >= 0x101 )
    _report_rangecheckfailure();
  v73[v13] = 0;
  if ( v73[0] )
  {
    v16 = 0;
    v17 = 0;
    v18 = v73[0];
    v19 = __ROL4__(1, v73[0]);
    do
    {
      for ( ; v73[v17] == v18; ++v16 )
      {
        v20 = v17++;
        v72[v20] = v16;
      }
      if ( v16 >= v19 )
      {
        *(_DWORD *)(*(_QWORD *)a1 + 40LL) = 8;
        (**(void (__fastcall ***)(struct jpeg_decompress_struct *))a1)(a1);
      }
      v16 *= 2;
      ++v18;
      v19 = __ROL4__(v19, 1);
    }
    while ( v73[v17] );
    v7 = a2;
    v12 = v69;
  }
  v21 = 3454;
  v22 = -1;
  if ( !v7 )
    v21 = 4550;
  if ( v11[v21] )
  {
    *(_DWORD *)(v9 + 76) = -v72[0];
    v23 = (unsigned __int8)v11[v21];
    v24 = v72[v23 - 1];
  }
  else
  {
    v23 = 0;
    v24 = -1;
  }
  *(_DWORD *)(v9 + 4) = v24;
  v25 = 3455;
  if ( !v7 )
    v25 = 4551;
  if ( v11[v25] )
  {
    *(_DWORD *)(v9 + 80) = v23 - v72[v23];
    v23 = (unsigned __int8)v11[v25] + (unsigned int)v23;
    v26 = v72[v23 - 1];
  }
  else
  {
    v26 = -1;
  }
  *(_DWORD *)(v9 + 8) = v26;
  v27 = 3456;
  if ( !v7 )
    v27 = 4552;
  if ( v11[v27] )
  {
    *(_DWORD *)(v9 + 84) = v23 - v72[v23];
    v23 = (unsigned __int8)v11[v27] + (unsigned int)v23;
    v28 = v72[v23 - 1];
  }
  else
  {
    v28 = -1;
  }
  *(_DWORD *)(v9 + 12) = v28;
  v29 = 3457;
  if ( !v7 )
    v29 = 4553;
  if ( v11[v29] )
  {
    *(_DWORD *)(v9 + 88) = v23 - v72[v23];
    v23 = (unsigned __int8)v11[v29] + (unsigned int)v23;
    v30 = v72[v23 - 1];
  }
  else
  {
    v30 = -1;
  }
  *(_DWORD *)(v9 + 16) = v30;
  v31 = 3458;
  if ( !v7 )
    v31 = 4554;
  if ( v11[v31] )
  {
    *(_DWORD *)(v9 + 92) = v23 - v72[v23];
    v23 = (unsigned __int8)v11[v31] + (unsigned int)v23;
    v32 = v72[v23 - 1];
  }
  else
  {
    v32 = -1;
  }
  *(_DWORD *)(v9 + 20) = v32;
  v33 = 3459;
  if ( !v7 )
    v33 = 4555;
  if ( v11[v33] )
  {
    *(_DWORD *)(v9 + 96) = v23 - v72[(int)v23];
    LODWORD(v23) = (unsigned __int8)v11[v33] + (_DWORD)v23;
    v34 = v72[(int)v23 - 1];
  }
  else
  {
    v34 = -1;
  }
  *(_DWORD *)(v9 + 24) = v34;
  v35 = 3460;
  if ( !v7 )
    v35 = 4556;
  if ( v11[v35] )
  {
    *(_DWORD *)(v9 + 100) = v23 - v72[(int)v23];
    LODWORD(v23) = (unsigned __int8)v11[v35] + (_DWORD)v23;
    v36 = v72[(int)v23 - 1];
  }
  else
  {
    v36 = -1;
  }
  *(_DWORD *)(v9 + 28) = v36;
  v37 = 3461;
  if ( !v7 )
    v37 = 4557;
  if ( v11[v37] )
  {
    *(_DWORD *)(v9 + 104) = v23 - v72[(int)v23];
    LODWORD(v23) = (unsigned __int8)v11[v37] + (_DWORD)v23;
    v38 = v72[(int)v23 - 1];
  }
  else
  {
    v38 = -1;
  }
  *(_DWORD *)(v9 + 32) = v38;
  v39 = 3462;
  if ( !v7 )
    v39 = 4558;
  if ( v11[v39] )
  {
    *(_DWORD *)(v9 + 108) = v23 - v72[(int)v23];
    LODWORD(v23) = (unsigned __int8)v11[v39] + (_DWORD)v23;
    v40 = v72[(int)v23 - 1];
  }
  else
  {
    v40 = -1;
  }
  *(_DWORD *)(v9 + 36) = v40;
  v41 = 3463;
  if ( !v7 )
    v41 = 4559;
  if ( v11[v41] )
  {
    *(_DWORD *)(v9 + 112) = v23 - v72[(int)v23];
    LODWORD(v23) = (unsigned __int8)v11[v41] + (_DWORD)v23;
    v42 = v72[(int)v23 - 1];
  }
  else
  {
    v42 = -1;
  }
  *(_DWORD *)(v9 + 40) = v42;
  v43 = 3464;
  if ( !v7 )
    v43 = 4560;
  if ( v11[v43] )
  {
    *(_DWORD *)(v9 + 116) = v23 - v72[(int)v23];
    LODWORD(v23) = (unsigned __int8)v11[v43] + (_DWORD)v23;
    v44 = v72[(int)v23 - 1];
  }
  else
  {
    v44 = -1;
  }
  *(_DWORD *)(v9 + 44) = v44;
  v45 = 3465;
  if ( !v7 )
    v45 = 4561;
  if ( v11[v45] )
  {
    *(_DWORD *)(v9 + 120) = v23 - v72[(int)v23];
    LODWORD(v23) = (unsigned __int8)v11[v45] + (_DWORD)v23;
    v46 = v72[(int)v23 - 1];
  }
  else
  {
    v46 = -1;
  }
  *(_DWORD *)(v9 + 48) = v46;
  v47 = 3466;
  if ( !v7 )
    v47 = 4562;
  if ( v11[v47] )
  {
    *(_DWORD *)(v9 + 124) = v23 - v72[(int)v23];
    LODWORD(v23) = (unsigned __int8)v11[v47] + (_DWORD)v23;
    v48 = v72[(int)v23 - 1];
  }
  else
  {
    v48 = -1;
  }
  *(_DWORD *)(v9 + 52) = v48;
  v49 = 3467;
  if ( !v7 )
    v49 = 4563;
  if ( v11[v49] )
  {
    *(_DWORD *)(v9 + 128) = v23 - v72[(int)v23];
    LODWORD(v23) = (unsigned __int8)v11[v49] + (_DWORD)v23;
    v50 = v72[(int)v23 - 1];
  }
  else
  {
    v50 = -1;
  }
  *(_DWORD *)(v9 + 56) = v50;
  v51 = 3468;
  if ( !v7 )
    v51 = 4564;
  if ( v11[v51] )
  {
    *(_DWORD *)(v9 + 132) = v23 - v72[(int)v23];
    LODWORD(v23) = (unsigned __int8)v11[v51] + (_DWORD)v23;
    v52 = v72[(int)v23 - 1];
  }
  else
  {
    v52 = -1;
  }
  *(_DWORD *)(v9 + 60) = v52;
  v53 = 3469;
  if ( !v7 )
    v53 = 4565;
  if ( v11[v53] )
  {
    *(_DWORD *)(v9 + 136) = v23 - v72[(int)v23];
    v22 = v72[(unsigned __int8)v11[v53] - 1 + (int)v23];
  }
  v54 = 256;
  v55 = 0;
  v56 = 1;
  *(_DWORD *)(v9 + 64) = v22;
  v57 = (_DWORD *)(v9 + 152);
  *(_DWORD *)(v9 + 140) = 0;
  *(_DWORD *)(v9 + 68) = 0xFFFFF;
  while ( v54 )
  {
    *v57++ = 2304;
    --v54;
  }
  do
  {
    v58 = &v12[v56];
    if ( *v58 )
    {
      v59 = 1;
      do
      {
        v60 = 1 << (8 - v56);
        for ( j = v72[v55] << (8 - v56);
              v60 > 0;
              *(_DWORD *)(v9 + 4 * v62 + 152) = (v56 << 8) | (unsigned __int8)v69[v55 + 17] )
        {
          --v60;
          v62 = j++;
        }
        ++v59;
        ++v55;
      }
      while ( v59 <= (unsigned __int8)*v58 );
      v12 = v69;
    }
    ++v56;
  }
  while ( v56 <= 8 );
  if ( a2 )
  {
    v63 = v68;
    v64 = 0;
    if ( v68 > 0 )
    {
      v65 = a1;
      do
      {
        if ( (unsigned __int8)v12[v64 + 17] > (unsigned int)(*(_BYTE *)(*((_QWORD *)v65 + 64) + 17LL) != 0) + 15 )
        {
          *(_DWORD *)(*(_QWORD *)v65 + 40LL) = 8;
          (**(void (__fastcall ***)(struct jpeg_decompress_struct *))v65)(v65);
          v12 = v69;
          v63 = v68;
          v65 = a1;
        }
        ++v64;
      }
      while ( v64 < v63 );
    }
  }
}

```

## disassembly

```asm
0x1800184a0  push    rbp
0x1800184a2  push    rbx
0x1800184a3  push    rsi
0x1800184a4  push    rdi
0x1800184a5  push    r13
0x1800184a7  push    r14
0x1800184a9  push    r15
0x1800184ab  lea     rbp, [rsp-470h]
0x1800184b3  sub     rsp, 570h
0x1800184ba  mov     rax, cs:__security_cookie
0x1800184c1  xor     rax, rsp
0x1800184c4  mov     [rbp+4A0h+var_40], rax
0x1800184cb  movsxd  rdi, r8d
0x1800184ce  mov     r14, r9
0x1800184d1  mov     [rsp+5A0h+var_580], dl
0x1800184d5  movzx   r13d, dl
0x1800184d9  mov     [rsp+5A0h+var_570], rcx
0x1800184de  mov     r15, rcx
0x1800184e1  cmp     edi, 3
0x1800184e4  ja      loc_180018B0F
0x1800184ea  mov     rbx, [r14]
0x1800184ed  mov     ecx, 11C5h
0x1800184f2  imul    rsi, rdi, 112h
0x1800184f9  mov     r10d, 0D7Dh
0x1800184ff  add     rsi, r15
0x180018502  test    r13b, r13b
0x180018505  cmovz   r10d, ecx
0x180018509  add     r10, rsi
0x18001850c  mov     [rsp+5A0h+var_578], r10
0x180018511  test    rbx, rbx
0x180018514  jz      loc_180018B2F
0x18001851a  xor     r11d, r11d
0x18001851d  mov     [rbx+90h], r10
0x180018524  mov     [rsp+5A0h+var_57C], r11d
0x180018529  mov     edi, 1
0x18001852e  mov     eax, edi
0x180018530  movzx   r14d, byte ptr [rax+r10]
0x180018535  lea     eax, [r14+r11]
0x180018539  cmp     eax, 100h
0x18001853e  jg      loc_180018B5C
0x180018544  test    r14d, r14d
0x180018547  jnz     loc_180018B83
0x18001854d  inc     edi
0x18001854f  cmp     edi, 10h
0x180018552  jle     short loc_18001852E
0x180018554  movsxd  rax, r11d
0x180018557  cmp     rax, 101h
0x18001855d  jnb     loc_180018BEC
0x180018563  mov     [rbp+rax+4A0h+var_150], 0
0x18001856b  movsx   eax, [rbp+4A0h+var_150]
0x180018572  mov     [rsp+5A0h+arg_8], r12
0x18001857a  test    al, al
0x18001857c  jz      short loc_1800185EC
0x18001857e  mov     r13, [rsp+5A0h+var_570]
0x180018583  xor     r14d, r14d
0x180018586  xor     r15d, r15d
0x180018589  mov     ecx, eax
0x18001858b  mov     edi, 1
0x180018590  mov     r12d, eax
0x180018593  rol     edi, cl
0x180018595  movsxd  rax, r15d
0x180018598  movsx   ecx, [rbp+rax+4A0h+var_150]
0x1800185a0  cmp     ecx, r12d
0x1800185a3  jnz     short loc_1800185C3
0x1800185a5  movsxd  rax, r15d
0x1800185a8  inc     r15d
0x1800185ab  mov     [rsp+rax*4+5A0h+var_560], r14d
0x1800185b0  inc     r14d
0x1800185b3  movsxd  rax, r15d
0x1800185b6  movsx   ecx, [rbp+rax+4A0h+var_150]
0x1800185be  cmp     ecx, r12d
0x1800185c1  jz      short loc_1800185A5
0x1800185c3  cmp     r14d, edi
0x1800185c6  jge     loc_180018BA1
0x1800185cc  movsxd  rax, r15d
0x1800185cf  add     r14d, r14d
0x1800185d2  inc     r12d
0x1800185d5  rol     edi, 1
0x1800185d7  cmp     [rbp+rax+4A0h+var_150], 0
0x1800185df  jnz     short loc_180018595
0x1800185e1  movzx   r13d, [rsp+5A0h+var_580]
0x1800185e7  mov     r10, [rsp+5A0h+var_578]
0x1800185ec  test    r13b, r13b
0x1800185ef  mov     ecx, 11C6h
0x1800185f4  mov     eax, 0D7Eh
0x1800185f9  mov     edi, 0FFFFFFFFh
0x1800185fe  cmovz   eax, ecx
0x180018601  cmp     byte ptr [rax+rsi], 0
0x180018605  lea     rcx, [rax+rsi]
0x180018609  jz      loc_180018A5A
0x18001860f  mov     eax, [rsp+5A0h+var_560]
0x180018613  neg     eax
0x180018615  mov     [rbx+4Ch], eax
0x180018618  movzx   eax, byte ptr [rcx]
0x18001861b  mov     edx, [rsp+rax*4+5A0h+var_564]
0x18001861f  mov     [rbx+4], edx
0x180018622  test    r13b, r13b
0x180018625  mov     edx, 11C7h
0x18001862a  mov     r8d, 0D7Fh
0x180018630  cmovz   r8d, edx
0x180018634  cmp     byte ptr [r8+rsi], 0
0x180018639  jz      loc_180018A63
0x18001863f  mov     edx, eax
0x180018641  sub     edx, [rsp+rax*4+5A0h+var_560]
0x180018645  mov     [rbx+50h], edx
0x180018648  movzx   ecx, byte ptr [r8+rsi]
0x18001864d  add     eax, ecx
0x18001864f  mov     edx, [rsp+rax*4+5A0h+var_564]
0x180018653  mov     [rbx+8], edx
0x180018656  test    r13b, r13b
0x180018659  mov     edx, 11C8h
0x18001865e  mov     r8d, 0D80h
0x180018664  cmovz   r8d, edx
0x180018668  cmp     byte ptr [r8+rsi], 0
0x18001866d  jz      loc_180018A6A
0x180018673  mov     edx, eax
0x180018675  sub     edx, [rsp+rax*4+5A0h+var_560]
0x180018679  mov     [rbx+54h], edx
0x18001867c  movzx   ecx, byte ptr [r8+rsi]
0x180018681  add     eax, ecx
0x180018683  mov     edx, [rsp+rax*4+5A0h+var_564]
0x180018687  mov     [rbx+0Ch], edx
0x18001868a  test    r13b, r13b
0x18001868d  mov     edx, 11C9h
0x180018692  mov     r8d, 0D81h
0x180018698  cmovz   r8d, edx
0x18001869c  cmp     byte ptr [r8+rsi], 0
0x1800186a1  jz      loc_180018A71
0x1800186a7  mov     edx, eax
0x1800186a9  sub     edx, [rsp+rax*4+5A0h+var_560]
0x1800186ad  mov     [rbx+58h], edx
0x1800186b0  movzx   ecx, byte ptr [r8+rsi]
0x1800186b5  add     eax, ecx
0x1800186b7  mov     edx, [rsp+rax*4+5A0h+var_564]
0x1800186bb  mov     [rbx+10h], edx
0x1800186be  test    r13b, r13b
0x1800186c1  mov     edx, 11CAh
0x1800186c6  mov     r8d, 0D82h
0x1800186cc  cmovz   r8d, edx
0x1800186d0  cmp     byte ptr [r8+rsi], 0
0x1800186d5  jz      loc_180018A78
0x1800186db  mov     edx, eax
0x1800186dd  sub     edx, [rsp+rax*4+5A0h+var_560]
0x1800186e1  mov     [rbx+5Ch], edx
0x1800186e4  movzx   ecx, byte ptr [r8+rsi]
0x1800186e9  add     eax, ecx
0x1800186eb  mov     edx, [rsp+rax*4+5A0h+var_564]
0x1800186ef  mov     [rbx+14h], edx
0x1800186f2  test    r13b, r13b
0x1800186f5  mov     edx, 11CBh
0x1800186fa  mov     r8d, 0D83h
0x180018700  cmovz   r8d, edx
0x180018704  cmp     byte ptr [r8+rsi], 0
0x180018709  jz      loc_180018A7F
0x18001870f  movsxd  rcx, eax
0x180018712  mov     edx, eax
0x180018714  sub     edx, [rsp+rcx*4+5A0h+var_560]
0x180018718  mov     [rbx+60h], edx
0x18001871b  movzx   ecx, byte ptr [r8+rsi]
0x180018720  add     eax, ecx
0x180018722  movsxd  rcx, eax
0x180018725  mov     edx, [rsp+rcx*4+5A0h+var_564]
0x180018729  mov     [rbx+18h], edx
0x18001872c  test    r13b, r13b
0x18001872f  mov     edx, 11CCh
0x180018734  mov     r8d, 0D84h
0x18001873a  cmovz   r8d, edx
0x18001873e  cmp     byte ptr [r8+rsi], 0
0x180018743  jz      loc_180018A86
0x180018749  movsxd  rcx, eax
0x18001874c  mov     edx, eax
0x18001874e  sub     edx, [rsp+rcx*4+5A0h+var_560]
0x180018752  mov     [rbx+64h], edx
0x180018755  movzx   ecx, byte ptr [r8+rsi]
0x18001875a  add     eax, ecx
0x18001875c  movsxd  rcx, eax
0x18001875f  mov     edx, [rsp+rcx*4+5A0h+var_564]
0x180018763  mov     [rbx+1Ch], edx
0x180018766  test    r13b, r13b
0x180018769  mov     edx, 11CDh
0x18001876e  mov     r8d, 0D85h
0x180018774  cmovz   r8d, edx
0x180018778  cmp     byte ptr [r8+rsi], 0
0x18001877d  jz      loc_180018A8D
0x180018783  movsxd  rcx, eax
0x180018786  mov     edx, eax
0x180018788  sub     edx, [rsp+rcx*4+5A0h+var_560]
0x18001878c  mov     [rbx+68h], edx
0x18001878f  movzx   ecx, byte ptr [r8+rsi]
0x180018794  add     eax, ecx
0x180018796  movsxd  rcx, eax
0x180018799  mov     edx, [rsp+rcx*4+5A0h+var_564]
0x18001879d  mov     [rbx+20h], edx
0x1800187a0  test    r13b, r13b
0x1800187a3  mov     edx, 11CEh
0x1800187a8  mov     r8d, 0D86h
0x1800187ae  cmovz   r8d, edx
0x1800187b2  cmp     byte ptr [r8+rsi], 0
0x1800187b7  jz      loc_180018A94
0x1800187bd  movsxd  rcx, eax
0x1800187c0  mov     edx, eax
0x1800187c2  sub     edx, [rsp+rcx*4+5A0h+var_560]
0x1800187c6  mov     [rbx+6Ch], edx
0x1800187c9  movzx   ecx, byte ptr [r8+rsi]
0x1800187ce  add     eax, ecx
0x1800187d0  movsxd  rcx, eax
0x1800187d3  mov     edx, [rsp+rcx*4+5A0h+var_564]
0x1800187d7  mov     [rbx+24h], edx
0x1800187da  test    r13b, r13b
0x1800187dd  mov     edx, 11CFh
0x1800187e2  mov     r8d, 0D87h
0x1800187e8  cmovz   r8d, edx
0x1800187ec  cmp     byte ptr [r8+rsi], 0
0x1800187f1  jz      loc_180018A9B
0x1800187f7  movsxd  rcx, eax
0x1800187fa  mov     edx, eax
0x1800187fc  sub     edx, [rsp+rcx*4+5A0h+var_560]
0x180018800  mov     [rbx+70h], edx
0x180018803  movzx   ecx, byte ptr [r8+rsi]
0x180018808  add     eax, ecx
0x18001880a  movsxd  rcx, eax
0x18001880d  mov     edx, [rsp+rcx*4+5A0h+var_564]
0x180018811  mov     [rbx+28h], edx
0x180018814  test    r13b, r13b
0x180018817  mov     edx, 11D0h
0x18001881c  mov     r8d, 0D88h
0x180018822  cmovz   r8d, edx
0x180018826  cmp     byte ptr [r8+rsi], 0
0x18001882b  jz      loc_180018AA2
0x180018831  movsxd  rcx, eax
0x180018834  mov     edx, eax
0x180018836  sub     edx, [rsp+rcx*4+5A0h+var_560]
0x18001883a  mov     [rbx+74h], edx
0x18001883d  movzx   ecx, byte ptr [r8+rsi]
0x180018842  add     eax, ecx
0x180018844  movsxd  rcx, eax
0x180018847  mov     edx, [rsp+rcx*4+5A0h+var_564]
0x18001884b  mov     [rbx+2Ch], edx
0x18001884e  test    r13b, r13b
0x180018851  mov     edx, 11D1h
0x180018856  mov     r8d, 0D89h
0x18001885c  cmovz   r8d, edx
0x180018860  cmp     byte ptr [r8+rsi], 0
0x180018865  jz      loc_180018AA9
0x18001886b  movsxd  rcx, eax
0x18001886e  mov     edx, eax
0x180018870  sub     edx, [rsp+rcx*4+5A0h+var_560]
0x180018874  mov     [rbx+78h], edx
0x180018877  movzx   ecx, byte ptr [r8+rsi]
0x18001887c  add     eax, ecx
0x18001887e  movsxd  rcx, eax
0x180018881  mov     edx, [rsp+rcx*4+5A0h+var_564]
0x180018885  mov     [rbx+30h], edx
0x180018888  test    r13b, r13b
0x18001888b  mov     edx, 11D2h
0x180018890  mov     r8d, 0D8Ah
0x180018896  cmovz   r8d, edx
0x18001889a  cmp     byte ptr [r8+rsi], 0
0x18001889f  jz      loc_180018AB0
0x1800188a5  movsxd  rcx, eax
0x1800188a8  mov     edx, eax
0x1800188aa  sub     edx, [rsp+rcx*4+5A0h+var_560]
0x1800188ae  mov     [rbx+7Ch], edx
0x1800188b1  movzx   ecx, byte ptr [r8+rsi]
0x1800188b6  add     eax, ecx
0x1800188b8  movsxd  rcx, eax
0x1800188bb  mov     edx, [rsp+rcx*4+5A0h+var_564]
0x1800188bf  mov     [rbx+34h], edx
0x1800188c2  test    r13b, r13b
0x1800188c5  mov     edx, 11D3h
0x1800188ca  mov     r8d, 0D8Bh
0x1800188d0  cmovz   r8d, edx
0x1800188d4  cmp     byte ptr [r8+rsi], 0
0x1800188d9  jz      loc_180018AB7
0x1800188df  movsxd  rcx, eax
0x1800188e2  mov     edx, eax
0x1800188e4  sub     edx, [rsp+rcx*4+5A0h+var_560]
0x1800188e8  mov     [rbx+80h], edx
0x1800188ee  movzx   ecx, byte ptr [r8+rsi]
0x1800188f3  add     eax, ecx
0x1800188f5  movsxd  rcx, eax
0x1800188f8  mov     edx, [rsp+rcx*4+5A0h+var_564]
0x1800188fc  mov     [rbx+38h], edx
0x1800188ff  test    r13b, r13b
0x180018902  mov     edx, 11D4h
0x180018907  mov     r8d, 0D8Ch
0x18001890d  cmovz   r8d, edx
0x180018911  cmp     byte ptr [r8+rsi], 0
0x180018916  jz      loc_180018ABE
0x18001891c  movsxd  rcx, eax
0x18001891f  mov     edx, eax
0x180018921  sub     edx, [rsp+rcx*4+5A0h+var_560]
0x180018925  mov     [rbx+84h], edx
0x18001892b  movzx   ecx, byte ptr [r8+rsi]
0x180018930  add     eax, ecx
0x180018932  movsxd  rcx, eax
0x180018935  mov     edx, [rsp+rcx*4+5A0h+var_564]
0x180018939  mov     [rbx+3Ch], edx
0x18001893c  test    r13b, r13b
0x18001893f  mov     edx, 11D5h
  ... truncated ...
```
