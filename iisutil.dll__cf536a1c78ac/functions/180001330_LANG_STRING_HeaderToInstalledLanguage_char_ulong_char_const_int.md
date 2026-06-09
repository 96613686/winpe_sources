# LANG_STRING::HeaderToInstalledLanguage(char *,ulong,char const * *,int)

- ea: `0x180001330`
- end: `0x1800017bd`
- name: `?HeaderToInstalledLanguage@LANG_STRING@@AEAAJPEADKPEAPEBDH@Z`
- size: `1165`
- prototype: `__int64 __fastcall(LANG_STRING *this, char *String, int, const char **, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180001200`

## callees

- `0x180001330`
- `0x1800018a0`
- `0x180001920`
- `0x1800034f0`
- `0x18002e52e`
- `0x18002e560`

## import_xrefs

- `msvcrt!strtok` at `0x18000139b`
- `msvcrt!strtok` at `0x1800013d3`
- `msvcrt!strtok` at `0x1800013f1`
- `msvcrt!strtok` at `0x180001650`
- `msvcrt!strtok` at `0x18000139b`
- `msvcrt!strtok` at `0x1800013d3`
- `msvcrt!strtok` at `0x1800013f1`
- `msvcrt!strtok` at `0x180001650`
- `msvcrt!isdigit` at `0x18000168e`
- `msvcrt!isdigit` at `0x18000168e`
- `msvcrt!atof` at `0x1800016bd`
- `msvcrt!atof` at `0x1800016bd`
- `msvcrt!_stricmp` at `0x180001550`
- `msvcrt!_stricmp` at `0x180001550`

## pseudocode

```c
__int64 __fastcall LANG_STRING::HeaderToInstalledLanguage(
        LANG_STRING *this,
        char *String,
        int a3,
        const char **a4,
        int a5)
{
  __int64 v7; // rdi
  char *i; // rcx
  char *v9; // rax
  __int64 j; // r14
  char *v11; // rbx
  char *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // r14
  __int64 v15; // rdx
  __int64 v16; // rcx
  const char **v17; // rsi
  int ParentLanguage; // ebx
  int v19; // r15d
  unsigned int m; // r12d
  double v21; // xmm1_8
  unsigned int v22; // r8d
  __int64 n; // rcx
  char *v24; // xmm0_8
  char *v25; // rdi
  __int64 v26; // rsi
  const char *v28; // r12
  int v29; // esi
  _BYTE *k; // rbx
  double v31; // xmm0_8
  __int64 ii; // rdi
  __int64 v33; // rdx
  char *v34; // rdx
  unsigned __int16 *v35; // rax
  int v36; // ecx
  int v37; // edx
  int v39; // [rsp+30h] [rbp-D8h]
  _BYTE v42[32]; // [rsp+48h] [rbp-C0h] BYREF
  char *v43; // [rsp+68h] [rbp-A0h]
  int v44; // [rsp+70h] [rbp-98h]
  __int16 v45; // [rsp+74h] [rbp-94h]
  _BYTE v46[32]; // [rsp+78h] [rbp-90h] BYREF
  char *v47; // [rsp+98h] [rbp-70h]
  int v48; // [rsp+A0h] [rbp-68h]
  __int16 v49; // [rsp+A4h] [rbp-64h]
  _OWORD v50[2]; // [rsp+A8h] [rbp-60h] BYREF
  _OWORD v51[2]; // [rsp+C8h] [rbp-40h] BYREF
  char *Stringa[2]; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v53[44]; // [rsp+F8h] [rbp-10h]

  v7 = 0;
  Stringa[0] = 0;
  memset_0(&Stringa[1], 0, 0x160u);
  for ( i = String; ; i = 0 )
  {
    v9 = strtok(i, ",");
    if ( !v9 || (unsigned int)v7 >= 0xF )
      break;
    v13 = 3 * v7;
    v7 = (unsigned int)(v7 + 1);
    Stringa[v13] = v9;
  }
  for ( j = 0; (unsigned int)j < (unsigned int)v7; j = (unsigned int)(j + 1) )
  {
    v11 = Stringa[3 * j];
    if ( *v11 )
    {
      if ( v11 != strtok(Stringa[3 * j], ";") )
        return (unsigned int)-2147024883;
      v12 = strtok(0, ";");
      if ( v12 )
      {
        if ( strtok(0, ";") )
          return (unsigned int)-2147024883;
        if ( *v12 != 113 )
          return (unsigned int)-2147024883;
        if ( v12[1] != 61 )
          return (unsigned int)-2147024883;
        v28 = v12 + 2;
        if ( (unsigned __int8)(v12[2] - 48) > 1u )
          return (unsigned int)-2147024883;
        if ( v12[3] == 46 )
        {
          v29 = 0;
          for ( k = v12 + 4; *k; ++k )
          {
            if ( !isdigit((unsigned __int8)*k) )
              return (unsigned int)-2147024883;
            if ( (unsigned int)++v29 > 3 )
              return (unsigned int)-2147024883;
          }
          if ( !v29 )
            return (unsigned int)-2147024883;
        }
        v31 = atof(v28);
        if ( v31 < 0.0 || v31 > 1.0 )
          return (unsigned int)-2147024883;
        *(double *)&Stringa[3 * j + 1] = v31;
      }
      else
      {
        Stringa[3 * j + 1] = (char *)0x3FF0000000000000LL;
      }
    }
    else
    {
      LODWORD(v53[3 * j]) = 1;
    }
  }
  v14 = 0;
  v15 = 0;
  if ( !(_DWORD)v7 )
    return (unsigned int)-2147024883;
  do
  {
    if ( !LODWORD(v53[3 * v15]) )
    {
      v16 = 3 * v14;
      v14 = (unsigned int)(v14 + 1);
      *(_OWORD *)&Stringa[v16] = *(_OWORD *)&Stringa[3 * v15];
      v53[v16] = v53[3 * v15];
    }
    v15 = (unsigned int)(v15 + 1);
  }
  while ( (unsigned int)v15 < (unsigned int)v7 );
  v39 = v14;
  if ( !(_DWORD)v14 )
    return (unsigned int)-2147024883;
  v17 = a4;
  ParentLanguage = 0;
  v19 = 0;
  for ( m = 0; ; ++m )
  {
    if ( m >= (unsigned int)v14 )
    {
      if ( !v19 )
        *v17 = (const char *)**((_QWORD **)this + 4);
      return (unsigned int)ParentLanguage;
    }
    if ( v19 )
      return (unsigned int)ParentLanguage;
    v21 = DOUBLE_N1_0;
    v22 = 0;
    for ( n = 0; (unsigned int)n < (unsigned int)v14; n = (unsigned int)(n + 1) )
    {
      if ( !LODWORD(v53[3 * n]) && *(double *)&Stringa[3 * n + 1] > v21 )
      {
        v21 = *(double *)&Stringa[3 * n + 1];
        v22 = n;
      }
    }
    v24 = Stringa[3 * v22 + 1];
    LODWORD(v53[3 * v22]) = 1;
    if ( *(double *)&v24 > 0.0 )
      break;
LABEL_38:
    ;
  }
  v25 = Stringa[3 * v22];
  if ( v25 < String || v25 > &String[a3] || !(unsigned int)LANG_STRING::ValidLanguage(this, Stringa[3 * v22]) )
    return (unsigned int)-2147024883;
  if ( *v25 == 42 )
  {
    v19 = 1;
    *v17 = (const char *)**((_QWORD **)this + 4);
    goto LABEL_38;
  }
  v26 = 0;
  if ( *((_DWORD *)this + 10) )
  {
    do
    {
      if ( !_stricmp(v25, *(const char **)(*((_QWORD *)this + 4) + 8 * v26)) )
      {
        v19 = 1;
        *a4 = *(const char **)(*((_QWORD *)this + 4) + 8 * v26);
      }
      v26 = (unsigned int)(v26 + 1);
    }
    while ( (unsigned int)v26 < *((_DWORD *)this + 10) );
    LODWORD(v14) = v39;
  }
  if ( !a5 || v19 )
  {
    v17 = a4;
    goto LABEL_38;
  }
  v48 = 32;
  v49 = 256;
  v47 = (char *)v50;
  memset(v50, 0, sizeof(v50));
  ParentLanguage = LANG_STRING::GetParentLanguage(this, v25, (struct BUFFER *)v46);
  if ( ParentLanguage >= 0 )
  {
    for ( ii = 0; ; ii = (unsigned int)(ii + 1) )
    {
      if ( (unsigned int)ii >= *((_DWORD *)this + 10) )
      {
        v17 = a4;
        goto LABEL_71;
      }
      v33 = *((_QWORD *)this + 4);
      v43 = (char *)v51;
      memset(v51, 0, sizeof(v51));
      v34 = *(char **)(v33 + 8 * ii);
      v44 = 32;
      v45 = 256;
      ParentLanguage = LANG_STRING::GetParentLanguage(this, v34, (struct BUFFER *)v42);
      if ( ParentLanguage < 0 )
        break;
      v35 = (unsigned __int16 *)v47;
      do
      {
        v36 = *(unsigned __int16 *)((char *)v35 + v43 - v47);
        v37 = *v35 - v36;
        if ( v37 )
          break;
        ++v35;
      }
      while ( v36 );
      if ( !v37 )
      {
        v19 = 1;
        v17 = a4;
        *a4 = *(const char **)(*((_QWORD *)this + 4) + 8 * ii);
        BUFFER::~BUFFER((BUFFER *)v42);
LABEL_71:
        BUFFER::~BUFFER((BUFFER *)v46);
        goto LABEL_38;
      }
      BUFFER::~BUFFER((BUFFER *)v42);
    }
    BUFFER::~BUFFER((BUFFER *)v42);
  }
  BUFFER::~BUFFER((BUFFER *)v46);
  return (unsigned int)ParentLanguage;
}

```

## disassembly

```asm
0x180001330  mov     rax, rsp
0x180001333  mov     [rax+18h], rbx
0x180001337  push    rbp
0x180001338  push    rsi
0x180001339  push    rdi
0x18000133a  push    r12
0x18000133c  push    r13
0x18000133e  push    r14
0x180001340  push    r15
0x180001342  lea     rbp, [rax-1A8h]
0x180001349  sub     rsp, 270h
0x180001350  movaps  xmmword ptr [rax-48h], xmm6
0x180001354  mov     rax, cs:__security_cookie
0x18000135b  xor     rax, rsp
0x18000135e  mov     [rbp+1A0h+var_50], rax
0x180001365  mov     dword ptr [rsp+2A0h+var_270], r8d
0x18000136a  mov     rbx, rdx
0x18000136d  mov     qword ptr [rsp+2A0h+var_268], rdx
0x180001372  mov     r13, rcx
0x180001375  xor     edi, edi
0x180001377  mov     qword ptr [rsp+2A0h+var_280], r9
0x18000137c  xor     edx, edx; Val
0x18000137e  mov     [rbp+1A0h+String], rdi
0x180001382  mov     r8d, 160h; Size
0x180001388  lea     rcx, [rbp+1A0h+String+8]; void *
0x18000138c  call    memset_0
0x180001391  mov     rcx, rbx; String
0x180001394  lea     rdx, Delimiter; ","
0x18000139b  call    cs:__imp_strtok
0x1800013a2  nop     dword ptr [rax+rax+00h]
0x1800013a7  test    rax, rax
0x1800013aa  jnz     short loc_18000141D
0x1800013ac  xor     r14d, r14d
0x1800013af  xorps   xmm6, xmm6
0x1800013b2  cmp     r14d, edi
0x1800013b5  jnb     short loc_180001434
0x1800013b7  lea     r15, [r14+r14*2]
0x1800013bb  mov     rbx, [rbp+r15*8+1A0h+String]
0x1800013c0  cmp     byte ptr [rbx], 0
0x1800013c3  jz      loc_180001639
0x1800013c9  lea     rdx, asc_180031FB0; ";"
0x1800013d0  mov     rcx, rbx; String
0x1800013d3  call    cs:__imp_strtok
0x1800013da  nop     dword ptr [rax+rax+00h]
0x1800013df  cmp     rbx, rax
0x1800013e2  jnz     loc_18000161D
0x1800013e8  lea     rdx, asc_180031FB0; ";"
0x1800013ef  xor     ecx, ecx; String
0x1800013f1  call    cs:__imp_strtok
0x1800013f8  nop     dword ptr [rax+rax+00h]
0x1800013fd  mov     rbx, rax
0x180001400  test    rax, rax
0x180001403  jnz     loc_180001647
0x180001409  mov     rax, 3FF0000000000000h
0x180001413  mov     [rbp+r15*8+1A0h+String+8], rax
0x180001418  inc     r14d
0x18000141b  jmp     short loc_1800013B2
0x18000141d  cmp     edi, 0Fh
0x180001420  jnb     short loc_1800013AC
0x180001422  lea     rdx, [rdi+rdi*2]
0x180001426  inc     edi
0x180001428  xor     ecx, ecx
0x18000142a  mov     [rbp+rdx*8+1A0h+String], rax
0x18000142f  jmp     loc_180001394
0x180001434  xor     r14d, r14d
0x180001437  xor     edx, edx
0x180001439  test    edi, edi
0x18000143b  jz      loc_18000161D
0x180001441  lea     r8, [rdx+rdx*2]
0x180001445  cmp     dword ptr [rbp+r8*8+1A0h+var_1B0], 0
0x18000144b  jnz     short loc_18000146C
0x18000144d  movups  xmm0, xmmword ptr [rbp+r8*8+1A0h+String]
0x180001453  lea     rcx, [r14+r14*2]
0x180001457  inc     r14d
0x18000145a  movups  xmmword ptr [rbp+rcx*8+1A0h+String], xmm0
0x18000145f  movsd   xmm1, [rbp+r8*8+1A0h+var_1B0]
0x180001466  movsd   [rbp+rcx*8+1A0h+var_1B0], xmm1
0x18000146c  inc     edx
0x18000146e  cmp     edx, edi
0x180001470  jb      short loc_180001441
0x180001472  mov     [rsp+2A0h+var_278], r14d
0x180001477  test    r14d, r14d
0x18000147a  jz      loc_18000161D
0x180001480  mov     rsi, qword ptr [rsp+2A0h+var_280]
0x180001485  xor     ebx, ebx
0x180001487  xor     r15d, r15d
0x18000148a  xor     r12d, r12d
0x18000148d  mov     [rsp+2A0h+var_274], r12d
0x180001492  cmp     r12d, r14d
0x180001495  jnb     loc_18000159C
0x18000149b  test    r15d, r15d
0x18000149e  jnz     loc_1800015A5
0x1800014a4  movsd   xmm1, cs:__real@bff0000000000000
0x1800014ac  xor     r8d, r8d
0x1800014af  xor     ecx, ecx
0x1800014b1  test    r14d, r14d
0x1800014b4  jz      short loc_1800014DA
0x1800014b6  lea     rdx, [rcx+rcx*2]
0x1800014ba  cmp     dword ptr [rbp+rdx*8+1A0h+var_1B0], 0
0x1800014bf  jnz     short loc_1800014D3
0x1800014c1  movsd   xmm0, [rbp+rdx*8+1A0h+String+8]
0x1800014c7  comisd  xmm0, xmm1
0x1800014cb  jbe     short loc_1800014D3
0x1800014cd  movaps  xmm1, xmm0
0x1800014d0  mov     r8d, ecx
0x1800014d3  inc     ecx
0x1800014d5  cmp     ecx, r14d
0x1800014d8  jb      short loc_1800014B6
0x1800014da  mov     eax, r8d
0x1800014dd  lea     rdi, [rax+rax*2]
0x1800014e1  movsd   xmm0, [rbp+rdi*8+1A0h+String+8]
0x1800014e7  comisd  xmm0, xmm6
0x1800014eb  mov     dword ptr [rbp+rdi*8+1A0h+var_1B0], 1
0x1800014f3  jbe     loc_180001594
0x1800014f9  mov     rdi, [rbp+rdi*8+1A0h+String]
0x1800014fe  mov     rcx, qword ptr [rsp+2A0h+var_268]
0x180001503  cmp     rdi, rcx
0x180001506  jb      loc_18000161D
0x18000150c  mov     eax, dword ptr [rsp+2A0h+var_270]
0x180001510  add     rax, rcx
0x180001513  cmp     rdi, rax
0x180001516  ja      loc_18000161D
0x18000151c  mov     rdx, rdi; char *
0x18000151f  mov     rcx, r13; this
0x180001522  call    ?ValidLanguage@LANG_STRING@@AEAAHPEBD@Z; LANG_STRING::ValidLanguage(char const *)
0x180001527  test    eax, eax
0x180001529  jz      loc_18000161D
0x18000152f  cmp     byte ptr [rdi], 2Ah ; '*'
0x180001532  jz      loc_180001624
0x180001538  xor     esi, esi
0x18000153a  cmp     [r13+28h], esi
0x18000153e  jbe     short loc_180001581
0x180001540  mov     r14, qword ptr [rsp+2A0h+var_280]
0x180001545  mov     rdx, [r13+20h]
0x180001549  mov     rcx, rdi; String1
0x18000154c  mov     rdx, [rdx+rsi*8]; String2
0x180001550  call    cs:__imp__stricmp
0x180001557  nop     dword ptr [rax+rax+00h]
0x18000155c  test    eax, eax
0x18000155e  jnz     short loc_18000156F
0x180001560  lea     r15d, [rax+1]
0x180001564  mov     rax, [r13+20h]
0x180001568  mov     rcx, [rax+rsi*8]
0x18000156c  mov     [r14], rcx
0x18000156f  inc     esi
0x180001571  cmp     esi, [r13+28h]
0x180001575  jb      short loc_180001545
0x180001577  mov     r14d, [rsp+2A0h+var_278]
0x18000157c  mov     r12d, [rsp+2A0h+var_274]
0x180001581  cmp     [rbp+1A0h+arg_20], 0
0x180001588  jz      short loc_18000158F
0x18000158a  test    r15d, r15d
0x18000158d  jz      short loc_1800015D7
0x18000158f  mov     rsi, qword ptr [rsp+2A0h+var_280]
0x180001594  inc     r12d
0x180001597  jmp     loc_18000148D
0x18000159c  test    r15d, r15d
0x18000159f  jz      loc_1800017AE
0x1800015a5  mov     eax, ebx
0x1800015a7  mov     rcx, [rbp+1A0h+var_50]
0x1800015ae  xor     rcx, rsp; StackCookie
0x1800015b1  call    __security_check_cookie
0x1800015b6  lea     r11, [rsp+2A0h+var_30]
0x1800015be  mov     rbx, [r11+50h]
0x1800015c2  movaps  xmm6, xmmword ptr [r11-10h]
0x1800015c7  mov     rsp, r11
0x1800015ca  pop     r15
0x1800015cc  pop     r14
0x1800015ce  pop     r13
0x1800015d0  pop     r12
0x1800015d2  pop     rdi
0x1800015d3  pop     rsi
0x1800015d4  pop     rbp
0x1800015d5  retn
0x1800015d7  xorps   xmm0, xmm0
0x1800015da  mov     [rbp+1A0h+var_208], 20h ; ' '
0x1800015e1  lea     rax, [rbp+1A0h+var_200]
0x1800015e5  mov     [rbp+1A0h+var_204], 100h
0x1800015eb  lea     r8, [rsp+2A0h+var_230]; struct BUFFER *
0x1800015f0  mov     [rbp+1A0h+var_210], rax
0x1800015f4  mov     rdx, rdi; char *
0x1800015f7  mov     rcx, r13; this
0x1800015fa  movups  [rbp+1A0h+var_200], xmm0
0x1800015fe  movups  [rbp+1A0h+var_1F0], xmm0
0x180001602  call    ?GetParentLanguage@LANG_STRING@@AEAAJPEADPEAVBUFFER@@@Z; LANG_STRING::GetParentLanguage(char *,BUFFER *)
0x180001607  mov     ebx, eax
0x180001609  test    eax, eax
0x18000160b  jns     loc_1800016ED
0x180001611  lea     rcx, [rsp+2A0h+var_230]; this
0x180001616  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000161b  jmp     short loc_1800015A5
0x18000161d  mov     ebx, 8007000Dh
0x180001622  jmp     short loc_1800015A5
0x180001624  mov     rax, [r13+20h]
0x180001628  mov     r15d, 1
0x18000162e  mov     rcx, [rax]
0x180001631  mov     [rsi], rcx
0x180001634  jmp     loc_180001594
0x180001639  mov     dword ptr [rbp+r15*8+1A0h+var_1B0], 1
0x180001642  jmp     loc_180001418
0x180001647  lea     rdx, asc_180031FB0; ";"
0x18000164e  xor     ecx, ecx; String
0x180001650  call    cs:__imp_strtok
0x180001657  nop     dword ptr [rax+rax+00h]
0x18000165c  test    rax, rax
0x18000165f  jnz     short loc_18000161D
0x180001661  cmp     byte ptr [rbx], 71h ; 'q'
0x180001664  jnz     short loc_18000161D
0x180001666  cmp     byte ptr [rbx+1], 3Dh ; '='
0x18000166a  jnz     short loc_18000161D
0x18000166c  lea     r12, [rbx+2]
0x180001670  mov     al, [r12]
0x180001674  sub     al, 30h ; '0'
0x180001676  cmp     al, 1
0x180001678  ja      short loc_18000161D
0x18000167a  cmp     byte ptr [rbx+3], 2Eh ; '.'
0x18000167e  jnz     short loc_1800016BA
0x180001680  xor     esi, esi
0x180001682  add     rbx, 4
0x180001686  cmp     byte ptr [rbx], 0
0x180001689  jz      short loc_1800016B2
0x18000168b  movzx   ecx, byte ptr [rbx]; C
0x18000168e  call    cs:__imp_isdigit
0x180001695  nop     dword ptr [rax+rax+00h]
0x18000169a  test    eax, eax
0x18000169c  jz      loc_18000161D
0x1800016a2  inc     esi
0x1800016a4  cmp     esi, 3
0x1800016a7  ja      loc_18000161D
0x1800016ad  inc     rbx
0x1800016b0  jmp     short loc_180001686
0x1800016b2  test    esi, esi
0x1800016b4  jz      loc_18000161D
0x1800016ba  mov     rcx, r12; String
0x1800016bd  call    cs:__imp_atof
0x1800016c4  nop     dword ptr [rax+rax+00h]
0x1800016c9  comisd  xmm6, xmm0
0x1800016cd  ja      loc_18000161D
0x1800016d3  comisd  xmm0, cs:__real@3ff0000000000000
0x1800016db  ja      loc_18000161D
0x1800016e1  movsd   [rbp+r15*8+1A0h+String+8], xmm0
0x1800016e8  jmp     loc_180001418
0x1800016ed  xor     edi, edi
0x1800016ef  cmp     edi, [r13+28h]
0x1800016f3  jnb     loc_18000178B
0x1800016f9  mov     rdx, [r13+20h]
0x1800016fd  lea     rax, [rbp+1A0h+var_1E0]
0x180001701  xorps   xmm0, xmm0
0x180001704  mov     [rsp+2A0h+var_240], rax
0x180001709  movups  [rbp+1A0h+var_1E0], xmm0
0x18000170d  lea     r8, [rsp+2A0h+var_260]; struct BUFFER *
0x180001712  mov     rcx, r13; this
0x180001715  movups  [rbp+1A0h+var_1D0], xmm0
0x180001719  mov     rdx, [rdx+rdi*8]; char *
0x18000171d  mov     [rsp+2A0h+var_238], 20h ; ' '
0x180001725  mov     [rsp+2A0h+var_234], 100h
0x18000172c  call    ?GetParentLanguage@LANG_STRING@@AEAAJPEADPEAVBUFFER@@@Z; LANG_STRING::GetParentLanguage(char *,BUFFER *)
0x180001731  mov     ebx, eax
0x180001733  test    eax, eax
0x180001735  js      short loc_18000179F
0x180001737  mov     rax, [rbp+1A0h+var_210]
0x18000173b  mov     r8, [rsp+2A0h+var_240]
0x180001740  sub     r8, rax
0x180001743  movzx   edx, word ptr [rax]
0x180001746  movzx   ecx, word ptr [rax+r8]
0x18000174b  sub     edx, ecx
0x18000174d  jnz     short loc_180001757
0x18000174f  add     rax, 2
0x180001753  test    ecx, ecx
0x180001755  jnz     short loc_180001743
0x180001757  test    edx, edx
0x180001759  jz      short loc_180001769
0x18000175b  lea     rcx, [rsp+2A0h+var_260]; this
0x180001760  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180001765  inc     edi
0x180001767  jmp     short loc_1800016EF
0x180001769  mov     rax, [r13+20h]
0x18000176d  mov     r15d, 1
0x180001773  mov     rsi, qword ptr [rsp+2A0h+var_280]
0x180001778  mov     rcx, [rax+rdi*8]
0x18000177c  mov     [rsi], rcx
0x18000177f  lea     rcx, [rsp+2A0h+var_260]; this
0x180001784  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180001789  jmp     short loc_180001790
0x18000178b  mov     rsi, qword ptr [rsp+2A0h+var_280]
0x180001790  lea     rcx, [rsp+2A0h+var_230]; this
0x180001795  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000179a  jmp     loc_180001594
0x18000179f  lea     rcx, [rsp+2A0h+var_260]; this
0x1800017a4  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800017a9  jmp     loc_180001611
0x1800017ae  mov     rax, [r13+20h]
0x1800017b2  mov     rcx, [rax]
0x1800017b5  mov     [rsi], rcx
0x1800017b8  jmp     loc_1800015A5
```
