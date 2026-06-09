# MsgSetWorker

- ea: `0x14000cec0`
- end: `0x14000d47c`
- name: `MsgSetWorker`
- size: `1468`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140008620`
- `0x14000ce88`

## callees

- `0x140001508`
- `0x14000cec0`
- `0x14000d484`
- `0x14000d528`
- `0x14000e406`
- `0x14000e412`
- `0x14000e450`

## import_xrefs

- `msvcrt!isdigit` at `0x14000cf4d`
- `msvcrt!isdigit` at `0x14000cf6c`
- `msvcrt!isdigit` at `0x14000d1dc`
- `msvcrt!isdigit` at `0x14000d3b2`
- `msvcrt!isdigit` at `0x14000cf4d`
- `msvcrt!isdigit` at `0x14000cf6c`
- `msvcrt!isdigit` at `0x14000d1dc`
- `msvcrt!isdigit` at `0x14000d3b2`
- `msvcrt!atoi` at `0x14000cf5a`
- `msvcrt!atoi` at `0x14000d1ed`
- `msvcrt!atoi` at `0x14000cf5a`
- `msvcrt!atoi` at `0x14000d1ed`

## pseudocode

```c
__int64 __fastcall MsgSetWorker(char *a1, int a2, const char *a3, char *a4, _QWORD *a5)
{
  unsigned __int64 v6; // r13
  __int64 v9; // rax
  __int64 v10; // rcx
  char v11; // al
  int v12; // r12d
  const char *v13; // rbx
  int v14; // eax
  const char *v15; // r14
  int v16; // eax
  bool v17; // zf
  char *v18; // rdx
  unsigned __int64 v19; // rcx
  __int64 v20; // rsi
  const char *v21; // rax
  int v22; // eax
  __int64 v23; // rbx
  int v24; // eax
  int v25; // ebx
  const char *v26; // r14
  __int64 v27; // rax
  const char *v28; // rcx
  const char *v29; // r8
  __int64 v30; // rax
  int v31; // ebx
  int v32; // r14d
  char *v33; // rbx
  char v34; // al
  __int64 v35; // r12
  __int64 v36; // rsi
  const char *v37; // rax
  __int64 v38; // rsi
  const char *v39; // rax
  char *v40; // rax
  __int64 v42; // r10
  __int64 v43; // rcx
  __int64 v44; // rax
  char *v45; // r8
  char *v46; // rdx
  char *v47; // rax
  __int64 v48; // rax
  int v49; // ecx
  __int64 v50; // [rsp+28h] [rbp-D8h]
  __int64 v51; // [rsp+28h] [rbp-D8h]
  int v52; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v53; // [rsp+38h] [rbp-C8h]
  const char *v54; // [rsp+40h] [rbp-C0h]
  int v55; // [rsp+48h] [rbp-B8h]
  int v56; // [rsp+4Ch] [rbp-B4h]
  _QWORD v57[10]; // [rsp+50h] [rbp-B0h] BYREF
  char v58; // [rsp+A0h] [rbp-60h] BYREF
  char v59[31]; // [rsp+A1h] [rbp-5Fh] BYREF
  _BYTE v60[64]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v61[448]; // [rsp+100h] [rbp+0h] BYREF

  v6 = a2;
  v53 = a5;
  memset_0(v57, 0, sizeof(v57));
  v9 = 0;
  do
  {
    v10 = (unsigned int)v9;
    if ( (unsigned int)v9 >= 0x200uLL )
LABEL_117:
      _report_rangecheckfailure(v10);
    v60[v9] = 0;
    v9 = (unsigned int)(v9 + 1);
  }
  while ( (int)v9 < 512 );
  v11 = *a3;
  if ( !*a3 )
    goto LABEL_56;
  v12 = 0;
  v13 = a3;
  do
  {
    ++v13;
    if ( v11 == 37 )
    {
      if ( isdigit(*(unsigned __int8 *)v13) )
      {
        v14 = atoi(v13);
        if ( v14 > v12 )
          v12 = v14;
        while ( *v13 && isdigit(*(unsigned __int8 *)v13) )
          ++v13;
      }
      else
      {
        ++v13;
      }
    }
    v11 = *v13;
  }
  while ( *v13 );
  if ( v12 <= 0 )
  {
LABEL_56:
    v32 = v6;
    v33 = a1;
    if ( !*a3 )
    {
LABEL_113:
      if ( v33 - a1 < (__int64)v6 && v32 > 0 )
        *v33 = 0;
      return (unsigned int)((_DWORD)v33 - (_DWORD)a1);
    }
    while ( 1 )
    {
      if ( v32 <= 1 )
        goto LABEL_113;
      v34 = *a3++;
      if ( v34 != 37 )
        goto LABEL_111;
      if ( isdigit(*(unsigned __int8 *)a3) )
      {
        v35 = atoi(a3);
        while ( *a3 && isdigit(*(unsigned __int8 *)a3) )
          ++a3;
        v42 = *((_QWORD *)&v55 + v35);
        v43 = v32;
        if ( (unsigned __int64)v32 <= 0x7FFFFFFF )
        {
          v44 = 2147483646;
          v45 = (char *)*((_QWORD *)&v55 + v35);
          v46 = v33;
          do
          {
            if ( !v44 )
              break;
            if ( !*v45 )
              break;
            *v46++ = *v45++;
            --v44;
            --v43;
          }
          while ( v43 );
          v47 = v46 - 1;
          if ( v43 )
            v47 = v46;
          *v47 = 0;
        }
        else
        {
          *v33 = 0;
        }
        v48 = -1;
        do
          ++v48;
        while ( *(_BYTE *)(v42 + v48) );
        v49 = v32 - 1;
        if ( (int)v48 < v32 )
          v49 = v48;
        v33 += v49;
        v32 -= v49;
        goto LABEL_112;
      }
      *v33 = 37;
      --v32;
      v34 = *a3;
      ++v33;
      ++a3;
      if ( v34 != 37 )
      {
LABEL_111:
        *v33++ = v34;
        --v32;
      }
LABEL_112:
      if ( !*a3 )
        goto LABEL_113;
    }
  }
  v15 = v60;
  v16 = 0;
  v54 = v60;
  v56 = 0;
  while ( 1 )
  {
    v17 = *a4 == 37;
    v18 = a4;
    v57[v16] = v15;
    if ( !v17 )
      break;
    do
      ++a4;
    while ( *a4 && *a4 != 37 );
    v22 = (_DWORD)a4 - (_DWORD)v18;
    v23 = (int)a4 - (int)v18;
    if ( (int)a4 - (int)v18 < 2 || (unsigned __int64)v22 >= 0x20 )
    {
      v19 = v6;
      if ( !(_DWORD)v6 )
        return 0;
      if ( v6 <= 0x7FFFFFFF )
      {
        v38 = 2147483646;
        v39 = "[INTERR] Format specifier %% is invalid";
        do
        {
          if ( !v38 )
            break;
          if ( !*v39 )
            break;
          *a1++ = *v39++;
          --v38;
          --v19;
        }
        while ( v19 );
        goto LABEL_88;
      }
LABEL_91:
      *a1 = 0;
      return 0;
    }
    if ( v18[1] == 44 )
    {
      v58 = *v18;
      memcpy_0(v59, v18 + 2, v22 - 2);
      if ( (unsigned __int64)(v23 - 1) >= 0x20 )
        goto LABEL_117;
      *(&v58 + v23 - 1) = 0;
      v55 = 1;
    }
    else
    {
      v55 = 0;
      memcpy_0(&v58, v18, v22);
      v59[v23 - 1] = 0;
    }
    v24 = *(a4 - 1);
    if ( *(a4 - 1) <= 102 )
    {
      if ( *(a4 - 1) != 102 && v24 != 69 && v24 != 71 )
      {
        if ( v24 == 88 || v24 == 99 || v24 == 100 )
          goto LABEL_67;
        if ( v24 != 101 )
          goto LABEL_75;
      }
LABEL_43:
      v25 = 5;
      if ( *(a4 - 2) == 76 )
        v25 = 6;
      v52 = 1;
      v51 = *v53;
      goto LABEL_46;
    }
    if ( (_BYTE)v24 == 103 )
      goto LABEL_43;
    if ( (_BYTE)v24 == 105 || (_BYTE)v24 == 111 )
      goto LABEL_67;
    if ( (_BYTE)v24 != 115 )
    {
      if ( (_BYTE)v24 != 117 && (_BYTE)v24 != 120 )
      {
LABEL_75:
        v19 = v6;
        if ( !(_DWORD)v6 )
          return 0;
        if ( v6 > 0x7FFFFFFF )
          goto LABEL_91;
        v36 = 2147483646;
        v37 = "[INTERR] Format specifier has unknown type";
        do
        {
          if ( !v36 )
            break;
          if ( !*v37 )
            break;
          *a1++ = *v37++;
          --v36;
          --v19;
        }
        while ( v19 );
        goto LABEL_88;
      }
LABEL_67:
      v17 = *(a4 - 2) == 104;
      v26 = v54;
      v52 = 1;
      if ( v17 )
      {
        LODWORD(v50) = *(unsigned __int16 *)v53;
        v27 = CatSprintf(&v52, v60, 512, v54, &v58, v50);
        v25 = 1;
      }
      else
      {
        LODWORD(v50) = *(_DWORD *)v53;
        if ( *(a4 - 2) == 108 )
        {
          v27 = CatSprintf(&v52, v60, 512, v54, &v58, v50);
          v25 = 3;
        }
        else
        {
          v27 = CatSprintf(&v52, v60, 512, v54, &v58, v50);
          v25 = 2;
        }
      }
      goto LABEL_47;
    }
    if ( *(a4 - 2) == 70 )
    {
      v26 = v54;
      v52 = 1;
      v27 = CatSprintf(&v52, v60, 512, v54, &v58, *v53);
      v25 = 8;
      goto LABEL_47;
    }
    v25 = 7;
    v52 = 1;
    v51 = *v53;
LABEL_46:
    v26 = v54;
    v27 = CatSprintf(&v52, v60, 512, v54, &v58, v51);
LABEL_47:
    if ( v52 )
      return 0;
    v61[447] = 0;
    ++v53;
    v28 = &v26[v27 + 1];
    v29 = v26;
    v30 = -1;
    do
      ++v30;
    while ( v28[v30] );
    v15 = &v28[v30 + 1];
    v54 = v15;
    if ( v55 )
    {
      if ( v29 - v60 < 492 )
      {
        v31 = v25 - 1;
        if ( !v31 || (unsigned int)(v31 - 1) <= 1 )
        {
          v15 += (int)addCommas(v29, (unsigned int)v61 + 448 - (unsigned int)v29);
          v54 = v15;
        }
      }
    }
    v16 = v56 + 1;
    v56 = v16;
    if ( v16 >= v12 )
      goto LABEL_56;
  }
  v19 = v6;
  if ( !(_DWORD)v6 )
    return 0;
  if ( v6 > 0x7FFFFFFF )
    goto LABEL_91;
  v20 = 2147483646;
  v21 = "[INTERR] Format specifier missing %";
  do
  {
    if ( !v20 )
      break;
    if ( !*v21 )
      break;
    *a1++ = *v21++;
    --v20;
    --v19;
  }
  while ( v19 );
LABEL_88:
  v40 = a1 - 1;
  if ( v19 )
    v40 = a1;
  *v40 = 0;
  return 0;
}

```

## disassembly

```asm
0x14000cec0  push    rbp
0x14000cec2  push    rbx
0x14000cec3  push    rsi
0x14000cec4  push    rdi
0x14000cec5  push    r12
0x14000cec7  push    r13
0x14000cec9  push    r14
0x14000cecb  push    r15
0x14000cecd  lea     rbp, [rsp-1D8h]
0x14000ced5  sub     rsp, 2D8h
0x14000cedc  mov     rax, cs:__security_cookie
0x14000cee3  xor     rax, rsp
0x14000cee6  mov     [rbp+210h+var_50], rax
0x14000ceed  mov     rax, [rbp+210h+arg_20]
0x14000cef4  mov     r15, r8
0x14000cef7  movsxd  r13, edx
0x14000cefa  mov     rdi, rcx
0x14000cefd  xor     edx, edx; Val
0x14000ceff  mov     [rsp+310h+var_2D8], rax
0x14000cf04  lea     rcx, [rsp+310h+var_2C0]; void *
0x14000cf09  mov     rsi, r9
0x14000cf0c  lea     r8d, [rdx+50h]; Size
0x14000cf10  call    memset_0
0x14000cf15  xor     eax, eax
0x14000cf17  mov     edx, 200h
0x14000cf1c  mov     ecx, eax
0x14000cf1e  cmp     rcx, rdx
0x14000cf21  jnb     loc_14000D476
0x14000cf27  mov     [rbp+rax+210h+var_250], 0
0x14000cf2c  inc     eax
0x14000cf2e  cmp     eax, edx
0x14000cf30  jl      short loc_14000CF1C
0x14000cf32  mov     al, [r15]
0x14000cf35  test    al, al
0x14000cf37  jz      loc_14000D1AB
0x14000cf3d  xor     r12d, r12d
0x14000cf40  mov     rbx, r15
0x14000cf43  inc     rbx
0x14000cf46  cmp     al, 25h ; '%'
0x14000cf48  jnz     short loc_14000CF84
0x14000cf4a  movzx   ecx, byte ptr [rbx]; C
0x14000cf4d  call    cs:__imp_isdigit
0x14000cf53  test    eax, eax
0x14000cf55  jz      short loc_14000CF81
0x14000cf57  mov     rcx, rbx; String
0x14000cf5a  call    cs:__imp_atoi
0x14000cf60  cmp     eax, r12d
0x14000cf63  cmovg   r12d, eax
0x14000cf67  jmp     short loc_14000CF79
0x14000cf69  movzx   ecx, al; C
0x14000cf6c  call    cs:__imp_isdigit
0x14000cf72  test    eax, eax
0x14000cf74  jz      short loc_14000CF84
0x14000cf76  inc     rbx
0x14000cf79  mov     al, [rbx]
0x14000cf7b  test    al, al
0x14000cf7d  jnz     short loc_14000CF69
0x14000cf7f  jmp     short loc_14000CF84
0x14000cf81  inc     rbx
0x14000cf84  mov     al, [rbx]
0x14000cf86  test    al, al
0x14000cf88  jnz     short loc_14000CF43
0x14000cf8a  test    r12d, r12d
0x14000cf8d  jle     loc_14000D1AB
0x14000cf93  lea     r14, [rbp+210h+var_250]
0x14000cf97  xor     eax, eax
0x14000cf99  mov     [rsp+310h+var_2D0], r14
0x14000cf9e  mov     [rsp+310h+var_2C4], eax
0x14000cfa2  cmp     byte ptr [rsi], 25h ; '%'
0x14000cfa5  mov     rdx, rsi
0x14000cfa8  cdqe
0x14000cfaa  mov     [rsp+rax*8+310h+var_2C0], r14
0x14000cfaf  jz      short loc_14000D004
0x14000cfb1  mov     rcx, r13
0x14000cfb4  test    r13d, r13d
0x14000cfb7  jz      loc_14000D38A
0x14000cfbd  cmp     rcx, 7FFFFFFFh
0x14000cfc4  ja      loc_14000D387
0x14000cfca  mov     esi, 7FFFFFFEh
0x14000cfcf  lea     rax, aInterrFormatSp_1; "[INTERR] Format specifier missing %"
0x14000cfd6  test    rsi, rsi
0x14000cfd9  jz      loc_14000D377
0x14000cfdf  mov     dl, [rax]
0x14000cfe1  test    dl, dl
0x14000cfe3  jz      loc_14000D377
0x14000cfe9  mov     [rdi], dl
0x14000cfeb  inc     rax
0x14000cfee  inc     rdi
0x14000cff1  dec     rsi
0x14000cff4  sub     rcx, 1
0x14000cff8  jnz     short loc_14000CFD6
0x14000cffa  jmp     loc_14000D377
0x14000cfff  cmp     byte ptr [rsi], 25h ; '%'
0x14000d002  jz      short loc_14000D00C
0x14000d004  inc     rsi
0x14000d007  cmp     byte ptr [rsi], 0
0x14000d00a  jnz     short loc_14000CFFF
0x14000d00c  mov     eax, esi
0x14000d00e  sub     eax, edx
0x14000d010  movsxd  rbx, eax
0x14000d013  cmp     ebx, 2
0x14000d016  jl      loc_14000D33E
0x14000d01c  cmp     rbx, 20h ; ' '
0x14000d020  jnb     loc_14000D33E
0x14000d026  cmp     byte ptr [rdx+1], 2Ch ; ','
0x14000d02a  jnz     short loc_14000D064
0x14000d02c  mov     al, [rdx]
0x14000d02e  lea     rcx, [rbp+210h+var_26F]; void *
0x14000d032  mov     [rbp+210h+var_270], al
0x14000d035  add     rdx, 2; Src
0x14000d039  lea     eax, [rbx-2]
0x14000d03c  movsxd  r8, eax; Size
0x14000d03f  call    memcpy_0
0x14000d044  lea     rax, [rbx-1]
0x14000d048  cmp     rax, 20h ; ' '
0x14000d04c  jnb     loc_14000D476
0x14000d052  mov     r8d, 1
0x14000d058  mov     [rbp+rax+210h+var_270], 0
0x14000d05d  mov     [rsp+310h+var_2C8], r8d
0x14000d062  jmp     short loc_14000D083
0x14000d064  mov     r8, rbx; Size
0x14000d067  mov     [rsp+310h+var_2C8], 0
0x14000d06f  lea     rcx, [rbp+210h+var_270]; void *
0x14000d073  call    memcpy_0
0x14000d078  mov     r8d, 1
0x14000d07e  mov     [rbp+rbx+210h+var_270], 0
0x14000d083  movsx   eax, byte ptr [rsi-1]
0x14000d087  cmp     al, 66h ; 'f'
0x14000d089  jg      loc_14000D1FB
0x14000d08f  jz      short loc_14000D0C1
0x14000d091  mov     ecx, eax
0x14000d093  sub     ecx, 45h ; 'E'
0x14000d096  jz      short loc_14000D0C1
0x14000d098  sub     ecx, 2
0x14000d09b  jz      short loc_14000D0C1
0x14000d09d  sub     ecx, 11h
0x14000d0a0  jz      loc_14000D21B
0x14000d0a6  sub     ecx, 0Bh
0x14000d0a9  jz      loc_14000D21B
0x14000d0af  sub     ecx, 1
0x14000d0b2  jz      loc_14000D21B
0x14000d0b8  cmp     ecx, 1
0x14000d0bb  jnz     loc_14000D304
0x14000d0c1  cmp     byte ptr [rsi-2], 4Ch ; 'L'
0x14000d0c5  mov     eax, r8d
0x14000d0c8  mov     ebx, 5
0x14000d0cd  jnz     short loc_14000D0D4
0x14000d0cf  mov     ebx, 6
0x14000d0d4  mov     [rsp+310h+var_2E0], eax
0x14000d0d8  mov     rax, [rsp+310h+var_2D8]
0x14000d0dd  movsd   xmm0, qword ptr [rax]
0x14000d0e1  movsd   [rsp+310h+var_2E8], xmm0
0x14000d0e7  mov     r14, [rsp+310h+var_2D0]
0x14000d0ec  lea     rax, [rbp+210h+var_270]
0x14000d0f0  mov     r9, r14
0x14000d0f3  mov     [rsp+310h+var_2F0], rax
0x14000d0f8  mov     r8d, 200h
0x14000d0fe  lea     rdx, [rbp+210h+var_250]
0x14000d102  lea     rcx, [rsp+310h+var_2E0]
0x14000d107  call    _CatSprintf
0x14000d10c  mov     ecx, 8
0x14000d111  cmp     [rsp+310h+var_2E0], 0
0x14000d116  mov     rdx, [rsp+310h+var_2D8]
0x14000d11b  jnz     loc_14000D38A
0x14000d121  add     rdx, rcx
0x14000d124  mov     [rbp+210h+var_51], 0
0x14000d12b  lea     rcx, [rax+1]
0x14000d12f  mov     [rsp+310h+var_2D8], rdx
0x14000d134  add     rcx, r14
0x14000d137  mov     r8, r14
0x14000d13a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d13e  inc     rax
0x14000d141  cmp     byte ptr [rcx+rax], 0
0x14000d145  jnz     short loc_14000D13E
0x14000d147  lea     r14, [rax+1]
0x14000d14b  add     r14, rcx
0x14000d14e  cmp     [rsp+310h+var_2C8], 0
0x14000d153  mov     [rsp+310h+var_2D0], r14
0x14000d158  jz      short loc_14000D198
0x14000d15a  lea     rcx, [rbp+210h+var_250]
0x14000d15e  mov     rax, r8
0x14000d161  sub     rax, rcx
0x14000d164  cmp     rax, 1ECh
0x14000d16a  jge     short loc_14000D198
0x14000d16c  sub     ebx, 1
0x14000d16f  jz      short loc_14000D17B
0x14000d171  sub     ebx, 1
0x14000d174  jz      short loc_14000D17B
0x14000d176  cmp     ebx, 1
0x14000d179  jnz     short loc_14000D198
0x14000d17b  lea     rdx, [rbp+210h+var_50]
0x14000d182  mov     rcx, r8
0x14000d185  sub     edx, r8d
0x14000d188  call    addCommas
0x14000d18d  movsxd  rcx, eax
0x14000d190  add     r14, rcx
0x14000d193  mov     [rsp+310h+var_2D0], r14
0x14000d198  mov     eax, [rsp+310h+var_2C4]
0x14000d19c  inc     eax
0x14000d19e  mov     [rsp+310h+var_2C4], eax
0x14000d1a2  cmp     eax, r12d
0x14000d1a5  jl      loc_14000CFA2
0x14000d1ab  cmp     byte ptr [r15], 0
0x14000d1af  mov     r14d, r13d
0x14000d1b2  mov     rbx, rdi
0x14000d1b5  jz      loc_14000D45A
0x14000d1bb  mov     esi, 7FFFFFFEh
0x14000d1c0  cmp     r14d, 1
0x14000d1c4  jle     loc_14000D45A
0x14000d1ca  mov     al, [r15]
0x14000d1cd  inc     r15
0x14000d1d0  cmp     al, 25h ; '%'
0x14000d1d2  jnz     loc_14000D448
0x14000d1d8  movzx   ecx, byte ptr [r15]; C
0x14000d1dc  call    cs:__imp_isdigit
0x14000d1e2  test    eax, eax
0x14000d1e4  jz      loc_14000D435
0x14000d1ea  mov     rcx, r15; String
0x14000d1ed  call    cs:__imp_atoi
0x14000d1f3  movsxd  r12, eax
0x14000d1f6  jmp     loc_14000D3BF
0x14000d1fb  cmp     al, 67h ; 'g'
0x14000d1fd  jz      loc_14000D0C1
0x14000d203  cmp     al, 69h ; 'i'
0x14000d205  jz      short loc_14000D21B
0x14000d207  cmp     al, 6Fh ; 'o'
0x14000d209  jz      short loc_14000D21B
0x14000d20b  cmp     al, 73h ; 's'
0x14000d20d  jz      short loc_14000D26A
0x14000d20f  cmp     al, 75h ; 'u'
0x14000d211  jz      short loc_14000D21B
0x14000d213  cmp     al, 78h ; 'x'
0x14000d215  jnz     loc_14000D304
0x14000d21b  cmp     byte ptr [rsi-2], 68h ; 'h'
0x14000d21f  lea     rdx, [rbp+210h+var_250]
0x14000d223  mov     r14, [rsp+310h+var_2D0]
0x14000d228  lea     rcx, [rsp+310h+var_2E0]
0x14000d22d  mov     rax, [rsp+310h+var_2D8]
0x14000d232  mov     r9, r14
0x14000d235  mov     [rsp+310h+var_2E0], r8d
0x14000d23a  mov     r8d, 200h
0x14000d240  jz      loc_14000D2E5
0x14000d246  cmp     byte ptr [rsi-2], 6Ch ; 'l'
0x14000d24a  mov     eax, [rax]
0x14000d24c  mov     dword ptr [rsp+310h+var_2E8], eax
0x14000d250  lea     rax, [rbp+210h+var_270]
0x14000d254  mov     [rsp+310h+var_2F0], rax
0x14000d259  jz      short loc_14000D2D6
0x14000d25b  call    _CatSprintf
0x14000d260  mov     ebx, 2
0x14000d265  jmp     loc_14000D10C
0x14000d26a  cmp     byte ptr [rsi-2], 46h ; 'F'
0x14000d26e  jz      short loc_14000D28E
0x14000d270  mov     eax, r8d
0x14000d273  mov     ebx, 7
0x14000d278  mov     [rsp+310h+var_2E0], eax
0x14000d27c  mov     rax, [rsp+310h+var_2D8]
0x14000d281  mov     rax, [rax]
0x14000d284  mov     [rsp+310h+var_2E8], rax
0x14000d289  jmp     loc_14000D0E7
0x14000d28e  mov     rax, [rsp+310h+var_2D8]
0x14000d293  lea     rdx, [rbp+210h+var_250]
0x14000d297  mov     r14, [rsp+310h+var_2D0]
0x14000d29c  lea     rcx, [rsp+310h+var_2E0]
0x14000d2a1  mov     [rsp+310h+var_2E0], r8d
0x14000d2a6  mov     r9, r14
0x14000d2a9  mov     r8d, 200h
0x14000d2af  mov     rax, [rax]
0x14000d2b2  mov     [rsp+310h+var_2E8], rax
0x14000d2b7  lea     rax, [rbp+210h+var_270]
0x14000d2bb  mov     [rsp+310h+var_2F0], rax
0x14000d2c0  call    _CatSprintf
0x14000d2c5  mov     r8d, 8
0x14000d2cb  mov     ecx, r8d
0x14000d2ce  mov     ebx, r8d
0x14000d2d1  jmp     loc_14000D111
0x14000d2d6  call    _CatSprintf
0x14000d2db  mov     ebx, 3
0x14000d2e0  jmp     loc_14000D10C
0x14000d2e5  movzx   eax, word ptr [rax]
0x14000d2e8  mov     dword ptr [rsp+310h+var_2E8], eax
0x14000d2ec  lea     rax, [rbp+210h+var_270]
0x14000d2f0  mov     [rsp+310h+var_2F0], rax
0x14000d2f5  call    _CatSprintf
0x14000d2fa  mov     ebx, 1
0x14000d2ff  jmp     loc_14000D10C
0x14000d304  mov     rcx, r13
0x14000d307  test    r13d, r13d
0x14000d30a  jz      short loc_14000D38A
0x14000d30c  cmp     rcx, 7FFFFFFFh
0x14000d313  ja      short loc_14000D387
0x14000d315  mov     esi, 7FFFFFFEh
0x14000d31a  lea     rax, aInterrFormatSp; "[INTERR] Format specifier has unknown t"...
0x14000d321  test    rsi, rsi
0x14000d324  jz      short loc_14000D377
0x14000d326  mov     dl, [rax]
0x14000d328  test    dl, dl
0x14000d32a  jz      short loc_14000D377
0x14000d32c  mov     [rdi], dl
0x14000d32e  add     rax, r8
  ... truncated ...
```
