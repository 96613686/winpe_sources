# std::_Partition_by_pivot_unchecked<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> *,bool (*)(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &)>(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> *,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> *,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> *,bool (*)(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value> const &))

- ea: `0x140004bc0`
- end: `0x140005053`
- name: `??$_Partition_by_pivot_unchecked@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YA?AU?$pair@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@PEAU12@@0@PEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@0@00P6A_NAEBU20@1@Z@Z`
- size: `1171`
- prototype: `__int128 **__fastcall(__int128 **, unsigned __int64, __int128 *, unsigned __int64, unsigned __int8 (__fastcall *)(char *, __int128 *))`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140005960`

## callees

- `0x140004bc0`
- `0x14003e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int128 **__fastcall std::_Partition_by_pivot_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
        __int128 **a1,
        unsigned __int64 a2,
        __int128 *a3,
        unsigned __int64 a4,
        unsigned __int8 (__fastcall *a5)(char *, __int128 *))
{
  __int128 *v6; // rbx
  __int128 *v7; // rdi
  char *v9; // rsi
  __int128 *v10; // rsi
  __int128 *v11; // r14
  __int128 v12; // xmm2
  char *v13; // rdx
  __int128 v14; // xmm3
  __int64 v15; // rcx
  __int64 v16; // rax
  bool v17; // zf
  __int128 *v18; // rbp
  __int128 v19; // xmm2
  char *v20; // rdx
  __int128 v21; // xmm3
  __int64 v22; // rcx
  __int64 v23; // rax
  __int128 v24; // xmm2
  __int128 v25; // xmm3
  __int64 v26; // rcx
  char *v27; // rdx
  __int64 v28; // rax
  __int128 v29; // xmm2
  __int128 v30; // xmm3
  __int64 v31; // rcx
  char *v32; // rdx
  __int64 v33; // rax
  __int128 *v34; // rax
  __int128 v35; // xmm2
  __int128 *v36; // r8
  __int128 v37; // xmm3
  char *v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int128 v41; // xmm2
  __int128 v42; // xmm3
  __int64 v43; // rcx
  char *v44; // rdx
  __int64 v45; // rax
  __int128 v46; // xmm2
  __int128 v47; // xmm3
  __int64 v48; // rcx
  char *v49; // rdx
  __int64 v50; // rax
  __int128 **result; // rax
  char v53; // [rsp+28h] [rbp-70h] BYREF
  char v54; // [rsp+30h] [rbp-68h] BYREF
  char v55; // [rsp+38h] [rbp-60h] BYREF
  char v56; // [rsp+40h] [rbp-58h] BYREF
  char v57; // [rsp+48h] [rbp-50h] BYREF
  char v58; // [rsp+50h] [rbp-48h] BYREF
  char v59; // [rsp+58h] [rbp-40h] BYREF

  v6 = a3;
  v7 = (__int128 *)((char *)a3 + 40);
  if ( a2 < (unsigned __int64)a3 )
  {
    do
    {
      v9 = (char *)v6 - 40;
      if ( a5((char *)v6 - 40, v6) )
        break;
      if ( a5((char *)v6, (__int128 *)((char *)v6 - 40)) )
        break;
      v6 = (__int128 *)((char *)v6 - 40);
    }
    while ( a2 < (unsigned __int64)v9 );
  }
  for ( ; (unsigned __int64)v7 < a4; v7 = (__int128 *)((char *)v7 + 40) )
  {
    if ( a5((char *)v7, v6) )
      break;
    if ( a5((char *)v6, v7) )
      break;
  }
  v10 = v7;
  v11 = v6;
  while ( 1 )
  {
    while ( 1 )
    {
      for ( ; (unsigned __int64)v10 < a4; v10 = (__int128 *)((char *)v10 + 40) )
      {
        if ( !a5((char *)v6, v10) )
        {
          if ( a5((char *)v10, v6) )
            break;
          if ( v7 != v10 )
          {
            v12 = *v7;
            v13 = (char *)(v10 + 2);
            v14 = v7[1];
            *v7 = *v10;
            v7[1] = v10[1];
            *v10 = v12;
            v10[1] = v14;
            v15 = *((_QWORD *)v7 + 4);
            *((_QWORD *)v7 + 4) = 0;
            if ( v7 + 2 != v10 + 2 )
            {
              *((_QWORD *)v7 + 4) = *(_QWORD *)v13;
              *(_QWORD *)v13 = 0;
            }
            if ( v13 != &v53 )
            {
              v16 = *(_QWORD *)v13;
              *(_QWORD *)v13 = v15;
              v15 = v16;
            }
            if ( v15 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 192LL))(v15, 1);
          }
          v7 = (__int128 *)((char *)v7 + 40);
        }
      }
      v17 = v11 == (__int128 *)a2;
      if ( (unsigned __int64)v11 > a2 )
      {
        do
        {
          v18 = (__int128 *)((char *)v11 - 40);
          if ( !a5((char *)v11 - 40, v6) )
          {
            if ( a5((char *)v6, (__int128 *)((char *)v11 - 40)) )
              break;
            v6 = (__int128 *)((char *)v6 - 40);
            if ( v6 != v18 )
            {
              v19 = *v6;
              v20 = (char *)(v18 + 2);
              v21 = v6[1];
              *v6 = *v18;
              v6[1] = v18[1];
              *v18 = v19;
              v18[1] = v21;
              v22 = *((_QWORD *)v6 + 4);
              *((_QWORD *)v6 + 4) = 0;
              if ( v6 + 2 != v18 + 2 )
              {
                *((_QWORD *)v6 + 4) = *(_QWORD *)v20;
                *(_QWORD *)v20 = 0;
              }
              if ( v20 != &v54 )
              {
                v23 = *(_QWORD *)v20;
                *(_QWORD *)v20 = v22;
                v22 = v23;
              }
              if ( v22 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 192LL))(v22, 1);
            }
          }
          v11 = (__int128 *)((char *)v11 - 40);
        }
        while ( a2 < (unsigned __int64)v18 );
        v17 = v11 == (__int128 *)a2;
      }
      if ( v17 )
        break;
      v34 = (__int128 *)((char *)v11 - 40);
      v11 = (__int128 *)((char *)v11 - 40);
      if ( v10 == (__int128 *)a4 )
      {
        v6 = (__int128 *)((char *)v6 - 40);
        if ( v34 != v6 )
        {
          v35 = *v34;
          v36 = v34 + 2;
          v37 = v34[1];
          v38 = (char *)(v6 + 2);
          *v34 = *v6;
          v34[1] = v6[1];
          *v6 = v35;
          v6[1] = v37;
          v39 = *((_QWORD *)v34 + 4);
          *((_QWORD *)v34 + 4) = 0;
          v40 = *((_QWORD *)v6 + 4);
          if ( v36 != v6 + 2 )
          {
            *(_QWORD *)v36 = v40;
            v40 = 0;
            *(_QWORD *)v38 = 0;
          }
          if ( v38 != &v57 )
          {
            *(_QWORD *)v38 = v39;
            v39 = v40;
          }
          if ( v39 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 192LL))(v39, 1);
        }
        v7 = (__int128 *)((char *)v7 - 40);
        if ( v6 != v7 )
        {
          v41 = *v6;
          v42 = v6[1];
          *v6 = *v7;
          v6[1] = v7[1];
          *v7 = v41;
          v7[1] = v42;
        }
        v43 = *((_QWORD *)v6 + 4);
        v44 = (char *)(v7 + 2);
        *((_QWORD *)v6 + 4) = 0;
        if ( v6 + 2 != v7 + 2 )
        {
          *((_QWORD *)v6 + 4) = *(_QWORD *)v44;
          *(_QWORD *)v44 = 0;
        }
        if ( v44 != &v58 )
        {
          v45 = *(_QWORD *)v44;
          *(_QWORD *)v44 = v43;
          v43 = v45;
        }
        if ( v43 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 192LL))(v43, 1);
      }
      else
      {
        if ( v10 != v34 )
        {
          v46 = *v10;
          v47 = v10[1];
          *v10 = *v34;
          v10[1] = v34[1];
          *v34 = v46;
          v34[1] = v47;
        }
        v48 = *((_QWORD *)v10 + 4);
        v49 = (char *)(v34 + 2);
        *((_QWORD *)v10 + 4) = 0;
        if ( v10 + 2 != v34 + 2 )
        {
          *((_QWORD *)v10 + 4) = *(_QWORD *)v49;
          *(_QWORD *)v49 = 0;
        }
        if ( v49 != &v59 )
        {
          v50 = *(_QWORD *)v49;
          *(_QWORD *)v49 = v48;
          v48 = v50;
        }
        if ( v48 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v48 + 192LL))(v48, 1);
        v10 = (__int128 *)((char *)v10 + 40);
      }
    }
    if ( v10 == (__int128 *)a4 )
      break;
    if ( v7 != v10 )
    {
      if ( v6 != v7 )
      {
        v24 = *v6;
        v25 = v6[1];
        *v6 = *v7;
        v6[1] = v7[1];
        *v7 = v24;
        v7[1] = v25;
      }
      v26 = *((_QWORD *)v6 + 4);
      v27 = (char *)(v7 + 2);
      *((_QWORD *)v6 + 4) = 0;
      if ( v6 + 2 != v7 + 2 )
      {
        *((_QWORD *)v6 + 4) = *(_QWORD *)v27;
        *(_QWORD *)v27 = 0;
      }
      if ( v27 != &v55 )
      {
        v28 = *(_QWORD *)v27;
        *(_QWORD *)v27 = v26;
        v26 = v28;
      }
      if ( v26 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 192LL))(v26, 1);
    }
    v7 = (__int128 *)((char *)v7 + 40);
    if ( v6 != v10 )
    {
      v29 = *v6;
      v30 = v6[1];
      *v6 = *v10;
      v6[1] = v10[1];
      *v10 = v29;
      v10[1] = v30;
    }
    v31 = *((_QWORD *)v6 + 4);
    v32 = (char *)(v10 + 2);
    *((_QWORD *)v6 + 4) = 0;
    if ( v6 + 2 != v10 + 2 )
    {
      *((_QWORD *)v6 + 4) = *(_QWORD *)v32;
      *(_QWORD *)v32 = 0;
    }
    if ( v32 != &v56 )
    {
      v33 = *(_QWORD *)v32;
      *(_QWORD *)v32 = v31;
      v31 = v33;
    }
    if ( v31 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 192LL))(v31, 1);
    v6 = (__int128 *)((char *)v6 + 40);
    v10 = (__int128 *)((char *)v10 + 40);
  }
  result = a1;
  *a1 = v6;
  a1[1] = v7;
  return result;
}

```

## disassembly

```asm
0x140004bc0  mov     [rsp+arg_8], rbx
0x140004bc5  push    rbp
0x140004bc6  push    rsi
0x140004bc7  push    rdi
0x140004bc8  push    r12
0x140004bca  push    r13
0x140004bcc  push    r14
0x140004bce  push    r15
0x140004bd0  sub     rsp, 60h
0x140004bd4  mov     r15, [rsp+98h+arg_20]
0x140004bdc  mov     r12, r9
0x140004bdf  mov     [rsp+98h+var_78], rcx
0x140004be4  mov     rbx, r8
0x140004be7  lea     rdi, [r8+28h]
0x140004beb  mov     r13, rdx
0x140004bee  cmp     rdx, r8
0x140004bf1  jnb     short loc_140004C23
0x140004bf3  lea     rsi, [rbx-28h]
0x140004bf7  mov     rdx, rbx
0x140004bfa  mov     rcx, rsi
0x140004bfd  mov     rax, r15
0x140004c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c05  test    al, al
0x140004c07  jnz     short loc_140004C23
0x140004c09  mov     rdx, rsi
0x140004c0c  mov     rcx, rbx
0x140004c0f  mov     rax, r15
0x140004c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c17  test    al, al
0x140004c19  jnz     short loc_140004C23
0x140004c1b  mov     rbx, rsi
0x140004c1e  cmp     r13, rsi
0x140004c21  jb      short loc_140004BF3
0x140004c23  cmp     rdi, r12
0x140004c26  jnb     short loc_140004C5D
0x140004c28  nop     dword ptr [rax+rax+00000000h]
0x140004c30  mov     rdx, rbx
0x140004c33  mov     rcx, rdi
0x140004c36  mov     rax, r15
0x140004c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c3e  test    al, al
0x140004c40  jnz     short loc_140004C5D
0x140004c42  mov     rdx, rdi
0x140004c45  mov     rcx, rbx
0x140004c48  mov     rax, r15
0x140004c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c50  test    al, al
0x140004c52  jnz     short loc_140004C5D
0x140004c54  add     rdi, 28h ; '('
0x140004c58  cmp     rdi, r12
0x140004c5b  jb      short loc_140004C30
0x140004c5d  mov     rsi, rdi
0x140004c60  mov     r14, rbx
0x140004c63  xor     ebp, ebp
0x140004c65  cmp     rsi, r12
0x140004c68  jnb     loc_140004D0E
0x140004c6e  xchg    ax, ax
0x140004c70  mov     rdx, rsi
0x140004c73  mov     rcx, rbx
0x140004c76  mov     rax, r15
0x140004c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c7e  test    al, al
0x140004c80  jnz     short loc_140004D01
0x140004c82  mov     rdx, rbx
0x140004c85  mov     rcx, rsi
0x140004c88  mov     rax, r15
0x140004c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c90  test    al, al
0x140004c92  jnz     short loc_140004D0E
0x140004c94  cmp     rdi, rsi
0x140004c97  jz      short loc_140004CFD
0x140004c99  movups  xmm0, xmmword ptr [rsi]
0x140004c9c  lea     r8, [rdi+20h]
0x140004ca0  movups  xmm2, xmmword ptr [rdi]
0x140004ca3  lea     rdx, [rsi+20h]
0x140004ca7  movups  xmm3, xmmword ptr [rdi+10h]
0x140004cab  movups  xmmword ptr [rdi], xmm0
0x140004cae  movups  xmm1, xmmword ptr [rsi+10h]
0x140004cb2  movups  xmmword ptr [rdi+10h], xmm1
0x140004cb6  movups  xmmword ptr [rsi], xmm2
0x140004cb9  movups  xmmword ptr [rsi+10h], xmm3
0x140004cbd  mov     rcx, [r8]
0x140004cc0  mov     [r8], rbp
0x140004cc3  cmp     r8, rdx
0x140004cc6  jz      short loc_140004CD1
0x140004cc8  mov     rax, [rdx]
0x140004ccb  mov     [r8], rax
0x140004cce  mov     [rdx], rbp
0x140004cd1  lea     rax, [rsp+98h+var_70]
0x140004cd6  cmp     rdx, rax
0x140004cd9  jz      short loc_140004CE4
0x140004cdb  mov     rax, [rdx]
0x140004cde  mov     [rdx], rcx
0x140004ce1  mov     rcx, rax
0x140004ce4  test    rcx, rcx
0x140004ce7  jz      short loc_140004CFD
0x140004ce9  mov     rax, [rcx]
0x140004cec  mov     edx, 1
0x140004cf1  mov     rax, [rax+0C0h]
0x140004cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004cfd  add     rdi, 28h ; '('
0x140004d01  add     rsi, 28h ; '('
0x140004d05  cmp     rsi, r12
0x140004d08  jb      loc_140004C70
0x140004d0e  cmp     r14, r13
0x140004d11  jbe     loc_140004DCF
0x140004d17  nop     word ptr [rax+rax+00000000h]
0x140004d20  lea     rbp, [r14-28h]
0x140004d24  mov     rdx, rbx
0x140004d27  mov     rcx, rbp
0x140004d2a  mov     rax, r15
0x140004d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004d32  test    al, al
0x140004d34  jnz     loc_140004DBE
0x140004d3a  mov     rdx, rbp
0x140004d3d  mov     rcx, rbx
0x140004d40  mov     rax, r15
0x140004d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004d48  test    al, al
0x140004d4a  jnz     short loc_140004DCA
0x140004d4c  sub     rbx, 28h ; '('
0x140004d50  cmp     rbx, rbp
0x140004d53  jz      short loc_140004DBE
0x140004d55  movups  xmm0, xmmword ptr [rbp+0]
0x140004d59  lea     r8, [rbx+20h]
0x140004d5d  xor     r9d, r9d
0x140004d60  movups  xmm2, xmmword ptr [rbx]
0x140004d63  lea     rdx, [rbp+20h]
0x140004d67  movups  xmm3, xmmword ptr [rbx+10h]
0x140004d6b  movups  xmmword ptr [rbx], xmm0
0x140004d6e  movups  xmm1, xmmword ptr [rbp+10h]
0x140004d72  movups  xmmword ptr [rbx+10h], xmm1
0x140004d76  movups  xmmword ptr [rbp+0], xmm2
0x140004d7a  movups  xmmword ptr [rbp+10h], xmm3
0x140004d7e  mov     rcx, [r8]
0x140004d81  mov     [r8], r9
0x140004d84  cmp     r8, rdx
0x140004d87  jz      short loc_140004D92
0x140004d89  mov     rax, [rdx]
0x140004d8c  mov     [r8], rax
0x140004d8f  mov     [rdx], r9
0x140004d92  lea     rax, [rsp+98h+var_68]
0x140004d97  cmp     rdx, rax
0x140004d9a  jz      short loc_140004DA5
0x140004d9c  mov     rax, [rdx]
0x140004d9f  mov     [rdx], rcx
0x140004da2  mov     rcx, rax
0x140004da5  test    rcx, rcx
0x140004da8  jz      short loc_140004DBE
0x140004daa  mov     rax, [rcx]
0x140004dad  mov     edx, 1
0x140004db2  mov     rax, [rax+0C0h]
0x140004db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004dbe  mov     r14, rbp
0x140004dc1  cmp     r13, rbp
0x140004dc4  jb      loc_140004D20
0x140004dca  xor     ebp, ebp
0x140004dcc  cmp     r14, r13
0x140004dcf  jnz     loc_140004EC8
0x140004dd5  cmp     rsi, r12
0x140004dd8  jz      loc_14000502F
0x140004dde  cmp     rdi, rsi
0x140004de1  jz      short loc_140004E4D
0x140004de3  cmp     rbx, rdi
0x140004de6  jz      short loc_140004E04
0x140004de8  movups  xmm0, xmmword ptr [rdi]
0x140004deb  movups  xmm2, xmmword ptr [rbx]
0x140004dee  movups  xmm3, xmmword ptr [rbx+10h]
0x140004df2  movups  xmmword ptr [rbx], xmm0
0x140004df5  movups  xmm1, xmmword ptr [rdi+10h]
0x140004df9  movups  xmmword ptr [rbx+10h], xmm1
0x140004dfd  movups  xmmword ptr [rdi], xmm2
0x140004e00  movups  xmmword ptr [rdi+10h], xmm3
0x140004e04  mov     rcx, [rbx+20h]
0x140004e08  lea     r8, [rbx+20h]
0x140004e0c  lea     rdx, [rdi+20h]
0x140004e10  mov     [r8], rbp
0x140004e13  cmp     r8, rdx
0x140004e16  jz      short loc_140004E21
0x140004e18  mov     rax, [rdx]
0x140004e1b  mov     [r8], rax
0x140004e1e  mov     [rdx], rbp
0x140004e21  lea     rax, [rsp+98h+var_60]
0x140004e26  cmp     rdx, rax
0x140004e29  jz      short loc_140004E34
0x140004e2b  mov     rax, [rdx]
0x140004e2e  mov     [rdx], rcx
0x140004e31  mov     rcx, rax
0x140004e34  test    rcx, rcx
0x140004e37  jz      short loc_140004E4D
0x140004e39  mov     rax, [rcx]
0x140004e3c  mov     edx, 1
0x140004e41  mov     rax, [rax+0C0h]
0x140004e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e4d  add     rdi, 28h ; '('
0x140004e51  cmp     rbx, rsi
0x140004e54  jz      short loc_140004E72
0x140004e56  movups  xmm0, xmmword ptr [rsi]
0x140004e59  movups  xmm2, xmmword ptr [rbx]
0x140004e5c  movups  xmm3, xmmword ptr [rbx+10h]
0x140004e60  movups  xmmword ptr [rbx], xmm0
0x140004e63  movups  xmm1, xmmword ptr [rsi+10h]
0x140004e67  movups  xmmword ptr [rbx+10h], xmm1
0x140004e6b  movups  xmmword ptr [rsi], xmm2
0x140004e6e  movups  xmmword ptr [rsi+10h], xmm3
0x140004e72  mov     rcx, [rbx+20h]
0x140004e76  lea     r8, [rbx+20h]
0x140004e7a  lea     rdx, [rsi+20h]
0x140004e7e  mov     [r8], rbp
0x140004e81  cmp     r8, rdx
0x140004e84  jz      short loc_140004E8F
0x140004e86  mov     rax, [rdx]
0x140004e89  mov     [r8], rax
0x140004e8c  mov     [rdx], rbp
0x140004e8f  lea     rax, [rsp+98h+var_58]
0x140004e94  cmp     rdx, rax
0x140004e97  jz      short loc_140004EA2
0x140004e99  mov     rax, [rdx]
0x140004e9c  mov     [rdx], rcx
0x140004e9f  mov     rcx, rax
0x140004ea2  test    rcx, rcx
0x140004ea5  jz      short loc_140004EBB
0x140004ea7  mov     rax, [rcx]
0x140004eaa  mov     edx, 1
0x140004eaf  mov     rax, [rax+0C0h]
0x140004eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ebb  add     rbx, 28h ; '('
0x140004ebf  add     rsi, 28h ; '('
0x140004ec3  jmp     loc_140004C65
0x140004ec8  lea     rax, [r14-28h]
0x140004ecc  mov     r14, rax
0x140004ecf  cmp     rsi, r12
0x140004ed2  jnz     loc_140004FBC
0x140004ed8  sub     rbx, 28h ; '('
0x140004edc  cmp     rax, rbx
0x140004edf  jz      short loc_140004F45
0x140004ee1  movups  xmm2, xmmword ptr [rax]
0x140004ee4  lea     r8, [rax+20h]
0x140004ee8  movups  xmm3, xmmword ptr [rax+10h]
0x140004eec  lea     rdx, [rbx+20h]
0x140004ef0  movups  xmm0, xmmword ptr [rbx]
0x140004ef3  movups  xmmword ptr [rax], xmm0
0x140004ef6  movups  xmm1, xmmword ptr [rbx+10h]
0x140004efa  movups  xmmword ptr [rax+10h], xmm1
0x140004efe  movups  xmmword ptr [rbx], xmm2
0x140004f01  movups  xmmword ptr [rbx+10h], xmm3
0x140004f05  mov     rcx, [r8]
0x140004f08  mov     [r8], rbp
0x140004f0b  mov     rax, [rdx]
0x140004f0e  cmp     r8, rdx
0x140004f11  jz      short loc_140004F1C
0x140004f13  mov     [r8], rax
0x140004f16  mov     rax, rbp
0x140004f19  mov     [rdx], rbp
0x140004f1c  lea     r8, [rsp+98h+var_50]
0x140004f21  cmp     rdx, r8
0x140004f24  jz      short loc_140004F2C
0x140004f26  mov     [rdx], rcx
0x140004f29  mov     rcx, rax
0x140004f2c  test    rcx, rcx
0x140004f2f  jz      short loc_140004F45
0x140004f31  mov     rax, [rcx]
0x140004f34  mov     edx, 1
0x140004f39  mov     rax, [rax+0C0h]
0x140004f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f45  sub     rdi, 28h ; '('
0x140004f49  cmp     rbx, rdi
0x140004f4c  jz      short loc_140004F6A
0x140004f4e  movups  xmm0, xmmword ptr [rdi]
0x140004f51  movups  xmm2, xmmword ptr [rbx]
0x140004f54  movups  xmm3, xmmword ptr [rbx+10h]
0x140004f58  movups  xmmword ptr [rbx], xmm0
0x140004f5b  movups  xmm1, xmmword ptr [rdi+10h]
0x140004f5f  movups  xmmword ptr [rbx+10h], xmm1
0x140004f63  movups  xmmword ptr [rdi], xmm2
0x140004f66  movups  xmmword ptr [rdi+10h], xmm3
0x140004f6a  mov     rcx, [rbx+20h]
0x140004f6e  lea     r8, [rbx+20h]
0x140004f72  lea     rdx, [rdi+20h]
0x140004f76  mov     [r8], rbp
0x140004f79  cmp     r8, rdx
0x140004f7c  jz      short loc_140004F87
0x140004f7e  mov     rax, [rdx]
0x140004f81  mov     [r8], rax
0x140004f84  mov     [rdx], rbp
0x140004f87  lea     rax, [rsp+98h+var_48]
0x140004f8c  cmp     rdx, rax
0x140004f8f  jz      short loc_140004F9A
0x140004f91  mov     rax, [rdx]
0x140004f94  mov     [rdx], rcx
0x140004f97  mov     rcx, rax
0x140004f9a  test    rcx, rcx
0x140004f9d  jz      loc_140004C65
0x140004fa3  mov     rax, [rcx]
0x140004fa6  mov     edx, 1
0x140004fab  mov     rax, [rax+0C0h]
0x140004fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fb7  jmp     loc_140004C65
0x140004fbc  cmp     rsi, rax
0x140004fbf  jz      short loc_140004FDD
  ... truncated ...
```
