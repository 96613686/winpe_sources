# attachFunc

- ea: `0x14001d100`
- end: `0x14001d613`
- name: `attachFunc`
- size: `1299`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `broker_com_uri`

## callees

- `0x14001d100`
- `0x1400203ec`
- `0x1400206dc`
- `0x140020730`
- `0x14004d1ac`
- `0x14004efa0`
- `0x14004fa1c`
- `0x14004fc80`
- `0x140053e3c`
- `0x140053e9c`
- `0x140053ef0`
- `0x140054094`
- `0x140054178`
- `0x14005fd9c`
- `0x140062bfc`
- `0x1400636dc`
- `0x140065754`
- `0x14006b6ec`
- `0x14006cc68`
- `0x140073758`
- `0x14007c6ac`
- `0x14008ac90`
- `0x14008ad20`
- `0x14008c390`
- `0x14008fc10`
- `0x140092d90`

## string_xrefs

- `0x14001d41e`: `database is already attached`
- `0x14001d310`: `database %s is already in use`
- `0x14001d5da`: `unable to open database: %s`

## pseudocode

```c
_OWORD *__fastcall attachFunc(__int64 *a1, __int64 a2, __int64 *a3)
{
  __int64 v3; // rax
  __int64 v5; // rcx
  __int64 *v7; // rsi
  __int64 v8; // r13
  __int64 v9; // rax
  __int64 v10; // rdx
  const unsigned __int16 *v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  const unsigned __int16 *v16; // r15
  const unsigned __int16 *v17; // rcx
  unsigned int v18; // ebx
  _OWORD *result; // rax
  unsigned int v20; // edi
  __int64 v21; // r9
  __int64 v22; // rbx
  __int64 v23; // r15
  __int64 v24; // r14
  __int64 v25; // rcx
  int v26; // r8d
  int v27; // r14d
  __int64 *v28; // rdx
  _OWORD *v29; // rdx
  _OWORD *v30; // rcx
  __int64 v31; // r14
  const char *v32; // rdx
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // r9
  __int64 v36; // rdx
  __int64 v37; // rcx
  unsigned int v38; // eax
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 *v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rbx
  unsigned int v45; // eax
  __int64 v46; // rcx
  bool v47; // zf
  __int64 v48; // rbx
  int v49; // r14d
  __int64 v50; // rcx
  __int64 v51; // [rsp+20h] [rbp-30h]
  __int64 v52; // [rsp+30h] [rbp-20h] BYREF
  __int64 v53; // [rsp+38h] [rbp-18h] BYREF
  const unsigned __int16 *v54; // [rsp+40h] [rbp-10h]
  __int64 v55; // [rsp+90h] [rbp+40h] BYREF
  __int64 v56; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v57; // [rsp+A8h] [rbp+58h] BYREF

  v3 = *a1;
  v52 = 0;
  v5 = *a3;
  LOBYTE(a2) = 1;
  v57 = 0;
  v7 = *(__int64 **)(v3 + 24);
  v8 = 0;
  v56 = 0;
  v53 = 0;
  v9 = sqlite3ValueText(v5, a2);
  LOBYTE(v10) = 1;
  v11 = (const unsigned __int16 *)v9;
  v12 = sqlite3ValueText(a3[1], v10);
  v16 = &dword_1400ACDEC;
  v17 = &dword_1400ACDEC;
  if ( v11 )
    v17 = v11;
  v18 = 0;
  v54 = v17;
  if ( v12 )
    v16 = (const unsigned __int16 *)v12;
  if ( (v7[25] & 4) != 0 )
  {
    v55 = 0;
    result = (_OWORD *)sqlite3_vfs_find("memdb", v13, v14, v15);
    if ( !result )
      return result;
    v20 = sqlite3BtreeOpen(result, "x", v7, &v55, 0, 256);
    if ( v20 )
      goto LABEL_13;
    v22 = v55;
    v23 = sqlite3SchemaGet(v7, v55);
    if ( !v23 )
    {
      sqlite3BtreeClose(v22);
      v20 = 7;
      goto LABEL_13;
    }
    v24 = v7[4] + 32LL * *((unsigned __int8 *)v7 + 196);
    v25 = *(_QWORD *)(v24 + 8);
    if ( v25 )
      sqlite3BtreeClose(v25);
    *(_QWORD *)(v24 + 8) = v22;
    *(_QWORD *)(v24 + 24) = v23;
    goto LABEL_37;
  }
  v26 = *((_DWORD *)v7 + 41);
  v20 = 0;
  v27 = *((_DWORD *)v7 + 10);
  if ( v27 >= v26 + 2 )
  {
    result = (_OWORD *)sqlite3MPrintf(v7, "too many attached databases - max %d", v26);
LABEL_22:
    v56 = (__int64)result;
LABEL_14:
    if ( !result )
    {
LABEL_17:
      if ( v20 )
        return (_OWORD *)sqlite3_result_error_code(a1, v20);
      return result;
    }
LABEL_15:
    *((_DWORD *)a1 + 9) = 1;
    LOBYTE(v21) = 1;
    result = (_OWORD *)sqlite3VdbeMemSetStr(*a1, result, -1, v21, -1);
    if ( v56 )
      result = (_OWORD *)sqlite3DbFreeNN(v7);
    goto LABEL_17;
  }
  if ( v27 > 0 )
  {
    while ( !(unsigned int)sqlite3DbIsNamed(v7, v18, v16) )
    {
      if ( (int)++v18 >= v27 )
        goto LABEL_26;
    }
    result = (_OWORD *)sqlite3MPrintf(v7, "database %s is already in use", v16);
    goto LABEL_22;
  }
LABEL_26:
  v28 = (__int64 *)v7[4];
  if ( v28 == v7 + 84 )
  {
    result = (_OWORD *)sqlite3DbMallocRawNN(v7, 96);
    v29 = result;
    if ( !result )
      return result;
    v30 = (_OWORD *)v7[4];
    *result = *v30;
    result[1] = v30[1];
    result[2] = v30[2];
    result[3] = v30[3];
  }
  else
  {
    result = (_OWORD *)sqlite3DbRealloc(v7, v28, 32LL * (v27 + 1));
    v29 = result;
    if ( !result )
      return result;
  }
  v31 = *((int *)v7 + 10);
  v7[4] = (__int64)v29;
  v24 = (__int64)&v29[2 * v31];
  v32 = (const char *)v54;
  *(_OWORD *)v24 = 0;
  *(_OWORD *)(v24 + 16) = 0;
  v33 = *v7;
  LODWORD(v55) = *((_DWORD *)v7 + 19);
  v34 = sqlite3ParseUri(*(const char **)(v33 + 24), v32, (unsigned int *)&v55, &v53, &v52, &v57);
  if ( v34 )
  {
    if ( v34 == 7 )
      sqlite3OomFault(v7);
    v36 = v57;
    v37 = *a1;
    LOBYTE(v35) = 1;
    *((_DWORD *)a1 + 9) = 1;
    sqlite3VdbeMemSetStr(v37, v36, -1, v35, -1);
    return (_OWORD *)sqlite3_free(v57);
  }
  v8 = v52;
  LODWORD(v51) = 0;
  v38 = sqlite3BtreeOpen(v53, v52, v7, v24 + 8, v51, (unsigned int)v55 | 0x100);
  ++*((_DWORD *)v7 + 10);
  v20 = v38;
  *(_QWORD *)v24 = sqlite3DbStrDup(v7, v16);
LABEL_37:
  *((_BYTE *)v7 + 111) = 0;
  if ( v20 == 19 )
  {
    v20 = 1;
    v56 = sqlite3MPrintf(v7, "database is already attached");
  }
  else if ( !v20 )
  {
    v39 = sqlite3SchemaGet(v7, *(_QWORD *)(v24 + 8));
    *(_QWORD *)(v24 + 24) = v39;
    if ( v39 )
    {
      if ( *(_BYTE *)(v39 + 112) && *(_BYTE *)(v39 + 113) != *((_BYTE *)v7 + 100) )
      {
        v56 = sqlite3MPrintf(v7, "attached databases must use the same text encoding as main database");
        v20 = 1;
      }
    }
    else
    {
      v20 = 7;
    }
    v40 = *(_QWORD *)(v24 + 8);
    if ( *(_BYTE *)(v40 + 17) )
    {
      ++*(_DWORD *)(v40 + 20);
      if ( !*(_BYTE *)(v40 + 18) )
        btreeLockCarefully(v40);
    }
    v41 = *(__int64 **)(*(_QWORD *)(v24 + 8) + 8LL);
    v42 = *v41;
    if ( !*(_BYTE *)(*v41 + 16) )
    {
      v43 = *(_QWORD *)(v42 + 296);
      if ( !v43 || *(_BYTE *)(v43 + 63) != 2 )
        *(_BYTE *)(v42 + 8) = *((_BYTE *)v7 + 105);
    }
    v44 = *(_QWORD *)(v24 + 8);
    v45 = sqlite3BtreeSecureDelete(*(_QWORD *)(v7[4] + 8), 0xFFFFFFFFLL);
    sqlite3BtreeSecureDelete(v44, v45);
    sqlite3BtreeSetPagerFlags(*(_QWORD *)(v24 + 8), v7[6] & 0x38 | 3);
    v46 = *(_QWORD *)(v24 + 8);
    if ( *(_BYTE *)(v46 + 17) )
    {
      v47 = (*(_DWORD *)(v46 + 20))-- == 1;
      if ( v47 )
        unlockBtreeMutex();
    }
  }
  *(_BYTE *)(v24 + 16) = 3;
  if ( !v20 && !*(_QWORD *)v24 )
    v20 = 7;
  result = (_OWORD *)sqlite3_free_filename(v8);
  if ( v20 )
    goto LABEL_66;
  if ( !*((_BYTE *)v7 + 111) )
    result = (_OWORD *)btreeEnterAll(v7);
  *((_DWORD *)v7 + 11) &= ~0x10u;
  v47 = (v7[25] & 4) == 0;
  *((_BYTE *)v7 + 196) = 0;
  if ( v47 )
  {
    result = (_OWORD *)sqlite3Init(v7, &v56);
    v20 = (unsigned int)result;
  }
  if ( !*((_BYTE *)v7 + 111) )
    result = (_OWORD *)btreeLeaveAll(v7);
  if ( v20 )
  {
LABEL_66:
    if ( (v7[25] & 4) == 0 )
    {
      v48 = 32LL * *((int *)v7 + 10);
      v49 = *((_DWORD *)v7 + 10) - 1;
      v50 = *(_QWORD *)(v48 + v7[4] - 24);
      if ( v50 )
      {
        sqlite3BtreeClose(v50);
        *(_QWORD *)(v48 + v7[4] - 24) = 0;
        *(_QWORD *)(v48 + v7[4] - 8) = 0;
      }
      sqlite3ResetAllSchemasOfConnection(v7);
      *((_DWORD *)v7 + 10) = v49;
      if ( v20 == 7 || v20 == 3082 )
      {
        sqlite3OomFault(v7);
        if ( v56 )
          sqlite3DbFreeNN(v7);
        result = (_OWORD *)sqlite3MPrintf(v7, "out of memory");
      }
      else
      {
        result = (_OWORD *)v56;
        if ( v56 )
          goto LABEL_15;
        result = (_OWORD *)sqlite3MPrintf(v7, "unable to open database: %s", v54);
      }
      goto LABEL_22;
    }
LABEL_13:
    result = (_OWORD *)v56;
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x14001d100  mov     [rsp-38h+arg_8], rbx
0x14001d105  push    rbp
0x14001d106  push    rsi
0x14001d107  push    rdi
0x14001d108  push    r12
0x14001d10a  push    r13
0x14001d10c  push    r14
0x14001d10e  push    r15
0x14001d110  mov     rbp, rsp
0x14001d113  sub     rsp, 50h
0x14001d117  mov     rax, [rcx]
0x14001d11a  xor     r14d, r14d
0x14001d11d  mov     r12, rcx
0x14001d120  mov     [rbp+var_20], r14
0x14001d124  mov     rcx, [r8]
0x14001d127  mov     dl, 1
0x14001d129  mov     rdi, r8
0x14001d12c  mov     [rbp+arg_18], r14
0x14001d130  mov     rsi, [rax+18h]
0x14001d134  mov     r13d, r14d
0x14001d137  mov     [rbp+arg_10], r14
0x14001d13b  mov     [rbp+var_18], r14
0x14001d13f  call    sqlite3ValueText
0x14001d144  mov     rcx, [rdi+8]
0x14001d148  mov     dl, 1
0x14001d14a  mov     rbx, rax
0x14001d14d  call    sqlite3ValueText
0x14001d152  test    rbx, rbx
0x14001d155  lea     r15, dword_1400ACDEC
0x14001d15c  mov     rcx, r15
0x14001d15f  cmovnz  rcx, rbx
0x14001d163  xor     ebx, ebx
0x14001d165  test    rax, rax
0x14001d168  mov     [rbp+var_10], rcx
0x14001d16c  cmovnz  r15, rax
0x14001d170  test    byte ptr [rsi+0C8h], 4
0x14001d177  jz      loc_14001D273
0x14001d17d  lea     rcx, aMemdb; "memdb"
0x14001d184  mov     [rbp+arg_0], rbx
0x14001d188  call    sqlite3_vfs_find
0x14001d18d  test    rax, rax
0x14001d190  jz      loc_14001D25B
0x14001d196  mov     dword ptr [rsp+50h+var_28], 100h
0x14001d19e  lea     r9, [rbp+arg_0]
0x14001d1a2  mov     r8, rsi
0x14001d1a5  mov     dword ptr [rsp+50h+var_30], ebx
0x14001d1a9  lea     rdx, asc_1400B9690; "x"
0x14001d1b0  mov     rcx, rax
0x14001d1b3  call    sqlite3BtreeOpen
0x14001d1b8  mov     edi, eax
0x14001d1ba  test    eax, eax
0x14001d1bc  jnz     short loc_14001D20F
0x14001d1be  mov     rbx, [rbp+arg_0]
0x14001d1c2  mov     rcx, rsi
0x14001d1c5  mov     rdx, rbx
0x14001d1c8  call    sqlite3SchemaGet
0x14001d1cd  mov     r15, rax
0x14001d1d0  test    rax, rax
0x14001d1d3  jz      short loc_14001D202
0x14001d1d5  movzx   r14d, byte ptr [rsi+0C4h]
0x14001d1dd  shl     r14, 5
0x14001d1e1  add     r14, [rsi+20h]
0x14001d1e5  mov     rcx, [r14+8]
0x14001d1e9  test    rcx, rcx
0x14001d1ec  jz      short loc_14001D1F3
0x14001d1ee  call    sqlite3BtreeClose
0x14001d1f3  mov     [r14+8], rbx
0x14001d1f7  xor     ebx, ebx
0x14001d1f9  mov     [r14+18h], r15
0x14001d1fd  jmp     loc_14001D410
0x14001d202  mov     rcx, rbx
0x14001d205  call    sqlite3BtreeClose
0x14001d20a  mov     edi, 7
0x14001d20f  mov     rax, [rbp+arg_10]
0x14001d213  test    rax, rax
0x14001d216  jz      short loc_14001D24D
0x14001d218  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14001d21c  mov     dword ptr [r12+24h], 1
0x14001d225  mov     [rsp+50h+var_30], rcx
0x14001d22a  mov     r8, rcx
0x14001d22d  mov     rcx, [r12]
0x14001d231  mov     r9b, 1
0x14001d234  mov     rdx, rax
0x14001d237  call    sqlite3VdbeMemSetStr
0x14001d23c  mov     rdx, [rbp+arg_10]
0x14001d240  test    rdx, rdx
0x14001d243  jz      short loc_14001D24D
0x14001d245  mov     rcx, rsi
0x14001d248  call    sqlite3DbFreeNN
0x14001d24d  test    edi, edi
0x14001d24f  jz      short loc_14001D25B
0x14001d251  mov     edx, edi
0x14001d253  mov     rcx, r12
0x14001d256  call    sqlite3_result_error_code
0x14001d25b  mov     rbx, [rsp+50h+arg_8]
0x14001d263  add     rsp, 50h
0x14001d267  pop     r15
0x14001d269  pop     r14
0x14001d26b  pop     r13
0x14001d26d  pop     r12
0x14001d26f  pop     rdi
0x14001d270  pop     rsi
0x14001d271  pop     rbp
0x14001d272  retn
0x14001d273  mov     r8d, [rsi+0A4h]
0x14001d27a  mov     edi, ebx
0x14001d27c  mov     r14d, [rsi+28h]
0x14001d280  lea     eax, [r8+2]
0x14001d284  cmp     r14d, eax
0x14001d287  jl      short loc_14001D2A1
0x14001d289  lea     rdx, aTooManyAttache; "too many attached databases - max %d"
0x14001d290  mov     rcx, rsi
0x14001d293  call    sqlite3MPrintf
0x14001d298  mov     [rbp+arg_10], rax
0x14001d29c  jmp     loc_14001D213
0x14001d2a1  test    r14d, r14d
0x14001d2a4  jle     short loc_14001D2BE
0x14001d2a6  mov     r8, r15
0x14001d2a9  mov     edx, ebx
0x14001d2ab  mov     rcx, rsi
0x14001d2ae  call    sqlite3DbIsNamed
0x14001d2b3  test    eax, eax
0x14001d2b5  jnz     short loc_14001D30D
0x14001d2b7  inc     ebx
0x14001d2b9  cmp     ebx, r14d
0x14001d2bc  jl      short loc_14001D2A6
0x14001d2be  mov     rdx, [rsi+20h]
0x14001d2c2  lea     rax, [rsi+2A0h]
0x14001d2c9  mov     rcx, rsi
0x14001d2cc  cmp     rdx, rax
0x14001d2cf  jnz     short loc_14001D324
0x14001d2d1  mov     edx, 60h ; '`'
0x14001d2d6  call    sqlite3DbMallocRawNN
0x14001d2db  xor     ebx, ebx
0x14001d2dd  mov     rdx, rax
0x14001d2e0  test    rax, rax
0x14001d2e3  jz      loc_14001D25B
0x14001d2e9  mov     rcx, [rsi+20h]
0x14001d2ed  movups  xmm0, xmmword ptr [rcx]
0x14001d2f0  movups  xmmword ptr [rax], xmm0
0x14001d2f3  movups  xmm1, xmmword ptr [rcx+10h]
0x14001d2f7  movups  xmmword ptr [rax+10h], xmm1
0x14001d2fb  movups  xmm0, xmmword ptr [rcx+20h]
0x14001d2ff  movups  xmmword ptr [rax+20h], xmm0
0x14001d303  movups  xmm1, xmmword ptr [rcx+30h]
0x14001d307  movups  xmmword ptr [rax+30h], xmm1
0x14001d30b  jmp     short loc_14001D342
0x14001d30d  mov     r8, r15
0x14001d310  lea     rdx, aDatabaseSIsAlr; "database %s is already in use"
0x14001d317  mov     rcx, rsi
0x14001d31a  call    sqlite3MPrintf
0x14001d31f  jmp     loc_14001D298
0x14001d324  lea     eax, [r14+1]
0x14001d328  movsxd  r8, eax
0x14001d32b  shl     r8, 5
0x14001d32f  call    sqlite3DbRealloc
0x14001d334  xor     ebx, ebx
0x14001d336  mov     rdx, rax
0x14001d339  test    rax, rax
0x14001d33c  jz      loc_14001D25B
0x14001d342  movsxd  r14, dword ptr [rsi+28h]
0x14001d346  lea     r9, [rbp+var_18]
0x14001d34a  mov     [rsi+20h], rdx
0x14001d34e  lea     r8, [rbp+arg_0]
0x14001d352  xorps   xmm0, xmm0
0x14001d355  shl     r14, 5
0x14001d359  add     r14, rdx
0x14001d35c  mov     rdx, [rbp+var_10]
0x14001d360  movups  xmmword ptr [r14], xmm0
0x14001d364  movups  xmmword ptr [r14+10h], xmm0
0x14001d369  mov     eax, [rsi+4Ch]
0x14001d36c  mov     rcx, [rsi]
0x14001d36f  mov     dword ptr [rbp+arg_0], eax
0x14001d372  lea     rax, [rbp+arg_18]
0x14001d376  mov     [rsp+50h+var_28], rax
0x14001d37b  lea     rax, [rbp+var_20]
0x14001d37f  mov     [rsp+50h+var_30], rax
0x14001d384  mov     rcx, [rcx+18h]
0x14001d388  call    sqlite3ParseUri
0x14001d38d  test    eax, eax
0x14001d38f  jz      short loc_14001D3D7
0x14001d391  mov     r15d, 7
0x14001d397  cmp     eax, r15d
0x14001d39a  jnz     short loc_14001D3A4
0x14001d39c  mov     rcx, rsi
0x14001d39f  call    sqlite3OomFault
0x14001d3a4  mov     rdx, [rbp+arg_18]
0x14001d3a8  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001d3ac  mov     rcx, [r12]
0x14001d3b0  mov     r8, rax
0x14001d3b3  mov     r9b, 1
0x14001d3b6  mov     dword ptr [r12+24h], 1
0x14001d3bf  mov     [rsp+50h+var_30], rax
0x14001d3c4  call    sqlite3VdbeMemSetStr
0x14001d3c9  mov     rcx, [rbp+arg_18]
0x14001d3cd  call    sqlite3_free
0x14001d3d2  jmp     loc_14001D25B
0x14001d3d7  mov     eax, dword ptr [rbp+arg_0]
0x14001d3da  lea     r9, [r14+8]
0x14001d3de  mov     r13, [rbp+var_20]
0x14001d3e2  bts     eax, 8
0x14001d3e6  mov     rcx, [rbp+var_18]
0x14001d3ea  mov     r8, rsi
0x14001d3ed  mov     dword ptr [rsp+50h+var_28], eax
0x14001d3f1  mov     rdx, r13
0x14001d3f4  mov     dword ptr [rsp+50h+var_30], ebx
0x14001d3f8  call    sqlite3BtreeOpen
0x14001d3fd  inc     dword ptr [rsi+28h]
0x14001d400  mov     rdx, r15
0x14001d403  mov     rcx, rsi
0x14001d406  mov     edi, eax
0x14001d408  call    sqlite3DbStrDup
0x14001d40d  mov     [r14], rax
0x14001d410  mov     [rsi+6Fh], bl
0x14001d413  mov     r15d, 7
0x14001d419  cmp     edi, 13h
0x14001d41c  jnz     short loc_14001D43A
0x14001d41e  lea     rdx, aDatabaseIsAlre; "database is already attached"
0x14001d425  mov     rcx, rsi
0x14001d428  lea     edi, [r15-6]
0x14001d42c  call    sqlite3MPrintf
0x14001d431  mov     [rbp+arg_10], rax
0x14001d435  jmp     loc_14001D508
0x14001d43a  test    edi, edi
0x14001d43c  jnz     loc_14001D508
0x14001d442  mov     rdx, [r14+8]
0x14001d446  mov     rcx, rsi
0x14001d449  call    sqlite3SchemaGet
0x14001d44e  mov     [r14+18h], rax
0x14001d452  mov     rcx, rax
0x14001d455  test    rax, rax
0x14001d458  jnz     short loc_14001D45F
0x14001d45a  mov     edi, r15d
0x14001d45d  jmp     short loc_14001D484
0x14001d45f  cmp     [rax+70h], bl
0x14001d462  jz      short loc_14001D484
0x14001d464  mov     al, [rsi+64h]
0x14001d467  cmp     [rcx+71h], al
0x14001d46a  jz      short loc_14001D484
0x14001d46c  lea     rdx, aAttachedDataba; "attached databases must use the same te"...
0x14001d473  mov     rcx, rsi
0x14001d476  call    sqlite3MPrintf
0x14001d47b  mov     [rbp+arg_10], rax
0x14001d47f  mov     edi, 1
0x14001d484  mov     rcx, [r14+8]
0x14001d488  cmp     [rcx+11h], bl
0x14001d48b  jz      short loc_14001D49A
0x14001d48d  inc     dword ptr [rcx+14h]
0x14001d490  cmp     [rcx+12h], bl
0x14001d493  jnz     short loc_14001D49A
0x14001d495  call    btreeLockCarefully
0x14001d49a  mov     rax, [r14+8]
0x14001d49e  mov     rcx, [rax+8]
0x14001d4a2  mov     rdx, [rcx]
0x14001d4a5  cmp     [rdx+10h], bl
0x14001d4a8  jnz     short loc_14001D4C2
0x14001d4aa  mov     rax, [rdx+128h]
0x14001d4b1  test    rax, rax
0x14001d4b4  jz      short loc_14001D4BC
0x14001d4b6  cmp     byte ptr [rax+3Fh], 2
0x14001d4ba  jz      short loc_14001D4C2
0x14001d4bc  mov     al, [rsi+69h]
0x14001d4bf  mov     [rdx+8], al
0x14001d4c2  mov     rcx, [rsi+20h]
0x14001d4c6  or      edx, 0FFFFFFFFh
0x14001d4c9  mov     rbx, [r14+8]
0x14001d4cd  mov     rcx, [rcx+8]
0x14001d4d1  call    sqlite3BtreeSecureDelete
0x14001d4d6  mov     edx, eax
0x14001d4d8  mov     rcx, rbx
0x14001d4db  call    sqlite3BtreeSecureDelete
0x14001d4e0  mov     edx, [rsi+30h]
0x14001d4e3  mov     rcx, [r14+8]
0x14001d4e7  and     edx, 38h
0x14001d4ea  or      edx, 3
0x14001d4ed  call    sqlite3BtreeSetPagerFlags
0x14001d4f2  mov     rcx, [r14+8]
0x14001d4f6  xor     ebx, ebx
0x14001d4f8  cmp     [rcx+11h], bl
0x14001d4fb  jz      short loc_14001D508
0x14001d4fd  sub     dword ptr [rcx+14h], 1
0x14001d501  jnz     short loc_14001D508
0x14001d503  call    unlockBtreeMutex
0x14001d508  mov     byte ptr [r14+10h], 3
0x14001d50d  test    edi, edi
0x14001d50f  jnz     short loc_14001D518
0x14001d511  cmp     [r14], rbx
0x14001d514  cmovz   edi, r15d
0x14001d518  mov     rcx, r13
0x14001d51b  call    sqlite3_free_filename
0x14001d520  test    edi, edi
0x14001d522  jnz     short loc_14001D567
0x14001d524  cmp     [rsi+6Fh], bl
0x14001d527  jnz     short loc_14001D531
0x14001d529  mov     rcx, rsi
0x14001d52c  call    btreeEnterAll
0x14001d531  and     dword ptr [rsi+2Ch], 0FFFFFFEFh
0x14001d535  test    byte ptr [rsi+0C8h], 4
0x14001d53c  mov     [rsi+0C4h], bl
0x14001d542  jnz     short loc_14001D552
  ... truncated ...
```
