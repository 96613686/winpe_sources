# HTTP_COMPRESSION::FindMatchingSchemes(char *,COMPRESSION_TO_PERFORM,ulong * const,ulong *)

- ea: `0x180002f20`
- end: `0x1800035aa`
- name: `?FindMatchingSchemes@HTTP_COMPRESSION@@CAXPEADW4COMPRESSION_TO_PERFORM@@QEAKPEAK@Z`
- size: `1674`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001eb0`

## callees

- `0x180002f20`
- `0x180004bd2`
- `0x180004c10`

## import_xrefs

- `msvcrt!_stricmp` at `0x18000349b`
- `msvcrt!_stricmp` at `0x18000349b`
- `msvcrt!atof` at `0x180003092`
- `msvcrt!atof` at `0x180003092`
- `msvcrt!isalnum` at `0x180002fbf`
- `msvcrt!isalnum` at `0x180002fde`
- `msvcrt!isalnum` at `0x180002ff7`
- `msvcrt!isalnum` at `0x180002fbf`
- `msvcrt!isalnum` at `0x180002fde`
- `msvcrt!isalnum` at `0x180002ff7`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003488`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180003488`

## pseudocode

```c
_DWORD *__fastcall HTTP_COMPRESSION::FindMatchingSchemes(char *a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  char v4; // al
  int v5; // r12d
  char *m; // rbx
  unsigned int v7; // edi
  unsigned int v8; // r14d
  char *v9; // rsi
  int v10; // ecx
  double v11; // xmm6_8
  __int64 v12; // rax
  int v13; // ecx
  unsigned __int8 i; // al
  unsigned __int8 v15; // al
  unsigned __int8 *j; // rbx
  unsigned __int8 v17; // al
  unsigned __int8 *k; // rbx
  char n; // al
  unsigned int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // edx
  __int64 v23; // r11
  __int64 v24; // r8
  __int64 *v25; // r9
  __int64 v26; // rcx
  __int64 v27; // xmm0_8
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // xmm0_8
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // xmm0_8
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // xmm0_8
  __int64 v37; // r11
  __int64 v38; // r9
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // xmm0_8
  unsigned int v42; // ecx
  double v43; // xmm0_8
  double v44; // xmm1_8
  unsigned int v45; // edx
  double v46; // xmm1_8
  double v47; // xmm1_8
  double v48; // xmm1_8
  double v49; // xmm1_8
  unsigned int v50; // r15d
  __int64 v51; // r13
  __int64 v52; // r14
  unsigned int v53; // ebx
  unsigned int v54; // esi
  const char *Str; // rax
  __int64 ii; // rcx
  struct COMPRESSION_SCHEME * near *v57; // rax
  __int64 v58; // rax
  _DWORD *result; // rax
  unsigned int v60; // [rsp+28h] [rbp-E0h]
  int v61; // [rsp+2Ch] [rbp-DCh]
  int v62; // [rsp+30h] [rbp-D8h]
  _QWORD v66[199]; // [rsp+50h] [rbp-B8h]
  _DWORD v67[104]; // [rsp+688h] [rbp+580h]
  _DWORD v68[100]; // [rsp+828h] [rbp+720h] BYREF

  v4 = *a1;
  v5 = 0;
  m = a1;
  v7 = 0;
  v8 = 0;
  v60 = 0;
  v62 = 0;
  v61 = 0;
  if ( *a1 )
  {
    v9 = 0;
    do
    {
      if ( v4 == 32 )
      {
        do
          ++m;
        while ( *m == 32 );
      }
      if ( isalnum((unsigned __int8)*m) )
      {
        v10 = (unsigned __int8)*m;
        v11 = DOUBLE_1_0;
        v12 = 2LL * v7;
        v66[v12 - 1] = m;
        v66[v12] = 0x3FF0000000000000LL;
        if ( isalnum(v10) )
        {
          do
            v13 = (unsigned __int8)*++m;
          while ( isalnum(v13) );
        }
        v9 = m;
      }
      else
      {
        if ( *m != 42 )
          break;
        v8 = 1;
        v11 = DOUBLE_1_0;
        ++m;
        v66[2 * v7] = 0x3FF0000000000000LL;
      }
      for ( i = *m; i == 32; ++m )
        i = m[1];
      if ( i == 59 )
      {
        v15 = m[1];
        for ( j = (unsigned __int8 *)(m + 1); v15 == 32; ++j )
          v15 = j[1];
        if ( v15 != 113 )
          break;
        v17 = j[1];
        for ( k = j + 1; v17 == 32; ++k )
          v17 = k[1];
        if ( v17 != 61 )
          break;
        for ( m = (char *)(k + 1); *m == 32; ++m )
          ;
        v11 = atof(m);
        *(double *)&v66[2 * v7] = v11;
        for ( n = *m; n; n = *++m )
        {
          if ( n == 44 )
            break;
        }
      }
      if ( *m == 44 )
        ++m;
      if ( v8 )
      {
        if ( v11 != 0.0 )
          v62 = 1;
      }
      else
      {
        ++v7;
        *v9 = 0;
        if ( v7 >= 0x64 )
          break;
      }
      v4 = *m;
    }
    while ( *m );
    v8 = 0;
  }
  v20 = 0;
  if ( v7 )
  {
    do
    {
      while ( 1 )
      {
        v21 = v20 + 1;
        v22 = v20 + 1;
        if ( v20 + 1 >= v7 )
          break;
        v23 = v20;
        if ( v7 - v22 >= 4 )
        {
          v24 = 2LL * v20;
          v25 = &v66[v24 - 1];
          do
          {
            if ( *(double *)&v66[2 * v22] > *(double *)&v66[2 * (unsigned int)v23] )
            {
              v25 = &v66[v24 - 1];
              v26 = v66[v24 - 1];
              v66[v24 - 1] = v66[2 * v22 - 1];
              v66[2 * v22 - 1] = v26;
              v27 = v66[2 * v23];
              v66[2 * v23] = v66[2 * v22];
              v66[2 * v22] = v27;
            }
            if ( *(double *)&v66[2 * v22 + 2] > *(double *)&v66[2 * (unsigned int)v23] )
            {
              v28 = *v25;
              *v25 = v66[2 * v22 + 1];
              v29 = v66[2 * v22 + 2];
              v66[2 * v22 + 1] = v28;
              v30 = v66[2 * (unsigned int)v23];
              v66[2 * (unsigned int)v23] = v29;
              v66[2 * v22 + 2] = v30;
            }
            if ( *(double *)&v66[2 * v22 + 4] > *(double *)&v66[2 * (unsigned int)v23] )
            {
              v31 = *v25;
              *v25 = v66[2 * v22 + 3];
              v32 = v66[2 * v22 + 4];
              v66[2 * v22 + 3] = v31;
              v33 = v66[2 * (unsigned int)v23];
              v66[2 * (unsigned int)v23] = v32;
              v66[2 * v22 + 4] = v33;
            }
            if ( *(double *)&v66[2 * v22 + 6] <= *(double *)&v66[2 * (unsigned int)v23] )
            {
              v25 = &v66[v24 - 1];
            }
            else
            {
              v34 = *v25;
              *v25 = v66[2 * v22 + 5];
              v35 = v66[2 * v22 + 6];
              v66[2 * v22 + 5] = v34;
              v36 = v66[2 * (unsigned int)v23];
              v66[2 * (unsigned int)v23] = v35;
              v66[2 * v22 + 6] = v36;
            }
            v22 += 4;
          }
          while ( v22 < v7 - 3 );
        }
        if ( v22 >= v7 )
          break;
        v37 = 2 * v23;
        v38 = v22;
        do
        {
          if ( *(double *)&v66[2 * v38] > *(double *)&v66[v37] )
          {
            v39 = v66[v37 - 1];
            v66[v37 - 1] = v66[2 * v38 - 1];
            v40 = v66[2 * v38];
            v66[2 * v38 - 1] = v39;
            v41 = v66[v37];
            v66[v37] = v40;
            v66[2 * v38] = v41;
          }
          ++v22;
          ++v38;
        }
        while ( v22 < v7 );
        v20 = v21;
      }
      v20 = v21;
    }
    while ( v21 < v7 );
    v42 = 1;
    v67[0] = 0;
    if ( v7 > 1 )
    {
      v43 = *(double *)v66;
      if ( v7 - 1 < 4 )
      {
        do
        {
LABEL_70:
          v49 = *(double *)&v66[2 * v42];
          if ( v49 == 0.0 )
            break;
          if ( v43 > v49 )
          {
            ++v8;
            v43 = *(double *)&v66[2 * v42];
            v67[v8] = v42;
          }
          ++v42;
        }
        while ( v42 < v7 );
      }
      else
      {
        while ( 1 )
        {
          v44 = *(double *)&v66[2 * v42];
          if ( v44 == 0.0 )
            break;
          if ( v43 > v44 )
          {
            ++v8;
            v43 = *(double *)&v66[2 * v42];
            v67[v8] = v42;
          }
          v45 = v42 + 1;
          v46 = *(double *)&v66[2 * v42 + 2];
          if ( v46 == 0.0 )
            goto LABEL_86;
          if ( v43 > v46 )
          {
            ++v8;
            v43 = *(double *)&v66[2 * v42 + 2];
            v67[v8] = v45;
          }
          v45 = v42 + 2;
          v47 = *(double *)&v66[2 * v42 + 4];
          if ( v47 == 0.0 )
            goto LABEL_86;
          if ( v43 > v47 )
          {
            ++v8;
            v43 = *(double *)&v66[2 * v42 + 4];
            v67[v8] = v45;
          }
          v45 = v42 + 3;
          v48 = *(double *)&v66[2 * v42 + 6];
          if ( v48 == 0.0 )
          {
LABEL_86:
            v42 = v45;
            break;
          }
          if ( v43 > v48 )
          {
            ++v8;
            v43 = *(double *)&v66[2 * v42 + 6];
            v67[v8] = v45;
          }
          v42 += 4;
          if ( v42 >= v7 - 3 )
          {
            if ( v42 >= v7 )
              break;
            goto LABEL_70;
          }
        }
      }
    }
    v60 = ++v8;
    v67[v8] = v42;
  }
  v50 = HTTP_COMPRESSION::sm_dwNumberOfSchemes;
  if ( HTTP_COMPRESSION::sm_dwNumberOfSchemes )
    memset_0(v68, 0, 4LL * HTTP_COMPRESSION::sm_dwNumberOfSchemes);
  v51 = 0;
  if ( v8 )
  {
    do
    {
      if ( v50 )
      {
        v52 = 0;
        do
        {
          if ( *((_DWORD *)(&HTTP_COMPRESSION::sm_pCompressionSchemes)[v52] + 59) )
          {
            if ( !v68[v52] )
            {
              v53 = v67[v51];
              v54 = v67[(unsigned int)(v51 + 1)];
              if ( v53 < v54 )
              {
                while ( 1 )
                {
                  Str = STRA::QueryStr((STRA *)((&HTTP_COMPRESSION::sm_pCompressionSchemes)[v52] + 7));
                  if ( !_stricmp((const char *)v66[2 * v53 - 1], Str) )
                    break;
                  if ( ++v53 >= v54 )
                    goto LABEL_88;
                }
                v68[v52] = 1;
                *(_DWORD *)(a3 + 4LL * v61++) = v52;
LABEL_88:
                v50 = HTTP_COMPRESSION::sm_dwNumberOfSchemes;
              }
            }
          }
          v52 = (unsigned int)(v52 + 1);
        }
        while ( (unsigned int)v52 < v50 );
        v8 = v60;
      }
      v51 = (unsigned int)(v51 + 1);
    }
    while ( (unsigned int)v51 < v8 );
    v5 = v61;
  }
  if ( v62 )
  {
    for ( ii = 0; (unsigned int)ii < v50; ii = (unsigned int)(ii + 1) )
    {
      if ( !v68[ii] )
      {
        v57 = (&HTTP_COMPRESSION::sm_pCompressionSchemes)[ii];
        v68[ii] = 1;
        if ( *((_DWORD *)v57 + 59) )
        {
          v58 = v5++;
          *(_DWORD *)(a3 + 4 * v58) = ii;
          v50 = HTTP_COMPRESSION::sm_dwNumberOfSchemes;
        }
      }
    }
  }
  result = a4;
  *a4 = v5;
  return result;
}

```

## disassembly

```asm
0x180002f20  mov     r11, rsp
0x180002f23  push    rbp
0x180002f24  push    r12
0x180002f26  push    r15
0x180002f28  lea     rbp, [r11-928h]
0x180002f2f  sub     rsp, 0A10h
0x180002f36  mov     rax, cs:__security_cookie
0x180002f3d  xor     rax, rsp
0x180002f40  mov     [rbp+920h+var_70], rax
0x180002f47  movzx   eax, byte ptr [rcx]
0x180002f4a  xor     r12d, r12d
0x180002f4d  mov     [r11+10h], rbx
0x180002f51  mov     rbx, rcx
0x180002f54  mov     [r11-20h], rsi
0x180002f58  mov     [r11-28h], rdi
0x180002f5c  xor     edi, edi
0x180002f5e  mov     [r11-30h], r13
0x180002f62  mov     [r11-38h], r14
0x180002f66  xor     r14d, r14d
0x180002f69  movaps  xmmword ptr [r11-68h], xmm8
0x180002f6e  xorps   xmm8, xmm8
0x180002f72  mov     [rsp+0A20h+var_9F0], r9
0x180002f77  mov     [rsp+0A20h+var_9E8], r8
0x180002f7c  mov     [rsp+0A20h+var_A00], r14d
0x180002f81  mov     dword ptr [rsp+0A20h+var_9F8], edi
0x180002f85  mov     [rsp+24h], r12d
0x180002f8a  test    al, al
0x180002f8c  jz      loc_180003107
0x180002f92  movaps  xmmword ptr [r11-58h], xmm7
0x180002f97  xor     esi, esi
0x180002f99  movsd   xmm7, cs:__real@3ff0000000000000
0x180002fa1  mov     r15, 3FF0000000000000h
0x180002fab  movaps  xmmword ptr [r11-48h], xmm6
0x180002fb0  cmp     al, 20h ; ' '
0x180002fb2  jnz     short loc_180002FBC
0x180002fb4  inc     rbx
0x180002fb7  cmp     byte ptr [rbx], 20h ; ' '
0x180002fba  jz      short loc_180002FB4
0x180002fbc  movzx   ecx, byte ptr [rbx]; C
0x180002fbf  call    cs:__imp_isalnum
0x180002fc5  test    eax, eax
0x180002fc7  jz      short loc_180003006
0x180002fc9  movzx   ecx, byte ptr [rbx]; C
0x180002fcc  movaps  xmm6, xmm7
0x180002fcf  mov     eax, edi
0x180002fd1  add     rax, rax
0x180002fd4  mov     [rsp+rax*8+0A20h+String1], rbx
0x180002fd9  mov     [rsp+rax*8+48h], r15
0x180002fde  call    cs:__imp_isalnum
0x180002fe4  test    eax, eax
0x180002fe6  jz      short loc_180003001
0x180002fe8  nop     dword ptr [rax+rax+00000000h]
0x180002ff0  movzx   ecx, byte ptr [rbx+1]; C
0x180002ff4  inc     rbx
0x180002ff7  call    cs:__imp_isalnum
0x180002ffd  test    eax, eax
0x180002fff  jnz     short loc_180002FF0
0x180003001  mov     rsi, rbx
0x180003004  jmp     short loc_180003025
0x180003006  cmp     byte ptr [rbx], 2Ah ; '*'
0x180003009  jnz     loc_1800030F4
0x18000300f  mov     eax, edi
0x180003011  mov     r14d, 1
0x180003017  add     rax, rax
0x18000301a  movaps  xmm6, xmm7
0x18000301d  inc     rbx
0x180003020  mov     [rsp+rax*8+48h], r15
0x180003025  movzx   eax, byte ptr [rbx]
0x180003028  cmp     al, 20h ; ' '
0x18000302a  jnz     short loc_18000303B
0x18000302c  nop     dword ptr [rax+00h]
0x180003030  movzx   eax, byte ptr [rbx+1]
0x180003034  inc     rbx
0x180003037  cmp     al, 20h ; ' '
0x180003039  jz      short loc_180003030
0x18000303b  cmp     al, 3Bh ; ';'
0x18000303d  jnz     loc_1800030BF
0x180003043  movzx   eax, byte ptr [rbx+1]
0x180003047  inc     rbx
0x18000304a  cmp     al, 20h ; ' '
0x18000304c  jnz     short loc_18000305B
0x18000304e  xchg    ax, ax
0x180003050  movzx   eax, byte ptr [rbx+1]
0x180003054  inc     rbx
0x180003057  cmp     al, 20h ; ' '
0x180003059  jz      short loc_180003050
0x18000305b  cmp     al, 71h ; 'q'
0x18000305d  jnz     loc_1800030F4
0x180003063  movzx   eax, byte ptr [rbx+1]
0x180003067  inc     rbx
0x18000306a  cmp     al, 20h ; ' '
0x18000306c  jnz     short loc_18000307B
0x18000306e  xchg    ax, ax
0x180003070  movzx   eax, byte ptr [rbx+1]
0x180003074  inc     rbx
0x180003077  cmp     al, 20h ; ' '
0x180003079  jz      short loc_180003070
0x18000307b  cmp     al, 3Dh ; '='
0x18000307d  jnz     short loc_1800030F4
0x18000307f  inc     rbx
0x180003082  cmp     byte ptr [rbx], 20h ; ' '
0x180003085  jnz     short loc_18000308F
0x180003087  inc     rbx
0x18000308a  cmp     byte ptr [rbx], 20h ; ' '
0x18000308d  jz      short loc_180003087
0x18000308f  mov     rcx, rbx; String
0x180003092  call    cs:__imp_atof
0x180003098  mov     eax, edi
0x18000309a  movaps  xmm6, xmm0
0x18000309d  add     rax, rax
0x1800030a0  movsd   qword ptr [rsp+rax*8+48h], xmm0
0x1800030a6  movzx   eax, byte ptr [rbx]
0x1800030a9  test    al, al
0x1800030ab  jz      short loc_1800030BF
0x1800030ad  nop     dword ptr [rax]
0x1800030b0  cmp     al, 2Ch ; ','
0x1800030b2  jz      short loc_1800030BF
0x1800030b4  movzx   eax, byte ptr [rbx+1]
0x1800030b8  inc     rbx
0x1800030bb  test    al, al
0x1800030bd  jnz     short loc_1800030B0
0x1800030bf  cmp     byte ptr [rbx], 2Ch ; ','
0x1800030c2  jnz     short loc_1800030C7
0x1800030c4  inc     rbx
0x1800030c7  test    r14d, r14d
0x1800030ca  jz      short loc_1800030DF
0x1800030cc  ucomisd xmm6, xmm8
0x1800030d1  jp      short loc_1800030D5
0x1800030d3  jz      short loc_1800030E9
0x1800030d5  mov     dword ptr [rsp+0A20h+var_9F8], 1
0x1800030dd  jmp     short loc_1800030E9
0x1800030df  inc     edi
0x1800030e1  mov     [rsi], r12b
0x1800030e4  cmp     edi, 64h ; 'd'
0x1800030e7  jnb     short loc_1800030F4
0x1800030e9  movzx   eax, byte ptr [rbx]
0x1800030ec  test    al, al
0x1800030ee  jnz     loc_180002FB0
0x1800030f4  movaps  xmm7, [rsp+0A20h+var_58+8]
0x1800030fc  mov     r14d, r12d
0x1800030ff  movaps  xmm6, [rsp+0A20h+var_48+8]
0x180003107  xor     eax, eax
0x180003109  test    edi, edi
0x18000310b  jz      loc_1800033F9
0x180003111  lea     esi, [rax+1]
0x180003114  mov     edx, esi
0x180003116  cmp     esi, edi
0x180003118  jnb     loc_1800032BF
0x18000311e  mov     r11d, eax
0x180003121  mov     eax, edi
0x180003123  sub     eax, edx
0x180003125  cmp     eax, 4
0x180003128  jb      loc_180003263
0x18000312e  mov     r8d, r11d
0x180003131  lea     r9, [rsp+0A20h+String1]
0x180003136  shl     r8, 4
0x18000313a  lea     ebx, [rdi-3]
0x18000313d  add     r9, r8
0x180003140  mov     r10d, edx
0x180003143  add     r10, r10
0x180003146  movsd   xmm0, qword ptr [rsp+r10*8+48h]
0x18000314d  comisd  xmm0, qword ptr [rsp+r8+48h]
0x180003154  jbe     short loc_180003191
0x180003156  mov     rax, [rsp+r10*8+0A20h+String1]
0x18000315b  lea     r9, [rsp+0A20h+String1]
0x180003160  add     r9, r8
0x180003163  mov     rcx, [r9]
0x180003166  mov     [r9], rax
0x180003169  mov     rax, r11
0x18000316c  mov     [rsp+r10*8+0A20h+String1], rcx
0x180003171  add     rax, rax
0x180003174  mov     rcx, r11
0x180003177  add     rcx, rcx
0x18000317a  movsd   xmm0, qword ptr [rsp+rax*8+48h]
0x180003180  mov     rax, [rsp+r10*8+48h]
0x180003185  mov     [rsp+rcx*8+48h], rax
0x18000318a  movsd   qword ptr [rsp+r10*8+48h], xmm0
0x180003191  lea     r10d, [rdx+1]
0x180003195  add     r10, r10
0x180003198  movsd   xmm0, qword ptr [rsp+r10*8+48h]
0x18000319f  comisd  xmm0, qword ptr [rsp+r8+48h]
0x1800031a6  jbe     short loc_1800031D0
0x1800031a8  mov     rax, [rsp+r10*8+0A20h+String1]
0x1800031ad  mov     rcx, [r9]
0x1800031b0  mov     [r9], rax
0x1800031b3  mov     rax, [rsp+r10*8+48h]
0x1800031b8  mov     [rsp+r10*8+0A20h+String1], rcx
0x1800031bd  movsd   xmm0, qword ptr [rsp+r8+48h]
0x1800031c4  mov     [rsp+r8+48h], rax
0x1800031c9  movsd   qword ptr [rsp+r10*8+48h], xmm0
0x1800031d0  lea     r10d, [rdx+2]
0x1800031d4  add     r10, r10
0x1800031d7  movsd   xmm0, qword ptr [rsp+r10*8+48h]
0x1800031de  comisd  xmm0, qword ptr [rsp+r8+48h]
0x1800031e5  jbe     short loc_18000320F
0x1800031e7  mov     rax, [rsp+r10*8+0A20h+String1]
0x1800031ec  mov     rcx, [r9]
0x1800031ef  mov     [r9], rax
0x1800031f2  mov     rax, [rsp+r10*8+48h]
0x1800031f7  mov     [rsp+r10*8+0A20h+String1], rcx
0x1800031fc  movsd   xmm0, qword ptr [rsp+r8+48h]
0x180003203  mov     [rsp+r8+48h], rax
0x180003208  movsd   qword ptr [rsp+r10*8+48h], xmm0
0x18000320f  lea     r10d, [rdx+3]
0x180003213  add     r10, r10
0x180003216  movsd   xmm0, qword ptr [rsp+r10*8+48h]
0x18000321d  comisd  xmm0, qword ptr [rsp+r8+48h]
0x180003224  jbe     short loc_180003250
0x180003226  mov     rax, [rsp+r10*8+0A20h+String1]
0x18000322b  mov     rcx, [r9]
0x18000322e  mov     [r9], rax
0x180003231  mov     rax, [rsp+r10*8+48h]
0x180003236  mov     [rsp+r10*8+0A20h+String1], rcx
0x18000323b  movsd   xmm0, qword ptr [rsp+r8+48h]
0x180003242  mov     [rsp+r8+48h], rax
0x180003247  movsd   qword ptr [rsp+r10*8+48h], xmm0
0x18000324e  jmp     short loc_180003258
0x180003250  lea     r9, [rsp+0A20h+String1]
0x180003255  add     r9, r8
0x180003258  add     edx, 4
0x18000325b  cmp     edx, ebx
0x18000325d  jb      loc_180003140
0x180003263  cmp     edx, edi
0x180003265  jnb     short loc_1800032BF
0x180003267  add     r11, r11
0x18000326a  mov     r9d, edx
0x18000326d  mov     r8, r9
0x180003270  add     r8, r8
0x180003273  movsd   xmm0, qword ptr [rsp+r8*8+48h]
0x18000327a  comisd  xmm0, qword ptr [rsp+r11*8+48h]
0x180003281  jbe     short loc_1800032AF
0x180003283  mov     rax, [rsp+r8*8+0A20h+String1]
0x180003288  mov     rcx, [rsp+r11*8+0A20h+String1]
0x18000328d  mov     [rsp+r11*8+0A20h+String1], rax
0x180003292  mov     rax, [rsp+r8*8+48h]
0x180003297  mov     [rsp+r8*8+0A20h+String1], rcx
0x18000329c  movsd   xmm0, qword ptr [rsp+r11*8+48h]
0x1800032a3  mov     [rsp+r11*8+48h], rax
0x1800032a8  movsd   qword ptr [rsp+r8*8+48h], xmm0
0x1800032af  inc     edx
0x1800032b1  inc     r9
0x1800032b4  cmp     edx, edi
0x1800032b6  jb      short loc_18000326D
0x1800032b8  mov     eax, esi
0x1800032ba  jmp     loc_180003111
0x1800032bf  mov     eax, esi
0x1800032c1  cmp     esi, edi
0x1800032c3  jb      loc_180003111
0x1800032c9  mov     ecx, 1
0x1800032ce  mov     [rbp+920h+var_3A0], r12d
0x1800032d5  cmp     edi, ecx
0x1800032d7  jbe     loc_1800033E9
0x1800032dd  movsd   xmm0, qword ptr [rsp+48h]
0x1800032e3  lea     eax, [rdi-1]
0x1800032e6  cmp     eax, 4
0x1800032e9  jb      loc_1800033BB
0x1800032ef  nop
0x1800032f0  mov     eax, ecx
0x1800032f2  add     rax, rax
0x1800032f5  movsd   xmm1, qword ptr [rsp+rax*8+48h]
0x1800032fb  ucomisd xmm1, xmm8
0x180003300  jp      short loc_180003308
0x180003302  jz      loc_1800033E9
0x180003308  comisd  xmm0, xmm1
0x18000330c  jbe     short loc_18000331C
0x18000330e  inc     r14d
0x180003311  movaps  xmm0, xmm1
0x180003314  mov     [rbp+r14*4+920h+var_3A0], ecx
0x18000331c  lea     edx, [rcx+1]
0x18000331f  mov     eax, edx
0x180003321  add     rax, rax
0x180003324  movsd   xmm1, qword ptr [rsp+rax*8+48h]
0x18000332a  ucomisd xmm1, xmm8
0x18000332f  jp      short loc_180003337
0x180003331  jz      loc_1800034B4
0x180003337  comisd  xmm0, xmm1
0x18000333b  jbe     short loc_18000334B
0x18000333d  inc     r14d
0x180003340  movaps  xmm0, xmm1
0x180003343  mov     [rbp+r14*4+920h+var_3A0], edx
0x18000334b  lea     edx, [rcx+2]
0x18000334e  mov     eax, edx
0x180003350  add     rax, rax
0x180003353  movsd   xmm1, qword ptr [rsp+rax*8+48h]
0x180003359  ucomisd xmm1, xmm8
0x18000335e  jp      short loc_180003366
0x180003360  jz      loc_1800034B4
0x180003366  comisd  xmm0, xmm1
0x18000336a  jbe     short loc_18000337A
0x18000336c  inc     r14d
0x18000336f  movaps  xmm0, xmm1
0x180003372  mov     [rbp+r14*4+920h+var_3A0], edx
0x18000337a  lea     edx, [rcx+3]
0x18000337d  mov     eax, edx
0x18000337f  add     rax, rax
0x180003382  movsd   xmm1, qword ptr [rsp+rax*8+48h]
0x180003388  ucomisd xmm1, xmm8
0x18000338d  jp      short loc_180003395
0x18000338f  jz      loc_1800034B4
0x180003395  comisd  xmm0, xmm1
  ... truncated ...
```
