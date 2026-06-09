# ISAPI_REQUEST::SetStatusAndHeaders(int,char *,char *,int)

- ea: `0x18000fb14`
- end: `0x1800100a5`
- name: `?SetStatusAndHeaders@ISAPI_REQUEST@@AEAAJHPEAD0H@Z`
- size: `1425`
- prototype: `__int64 __usercall@<rax>(ISAPI_REQUEST *__hidden this@<rcx>, int@<edx>, char *@<r8>, char *@<r9>, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000f7f0`
- `0x180010250`
- `0x180010460`

## callees

- `0x18000d1cc`
- `0x18000fb14`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `msvcrt!isspace` at `0x18000fe67`
- `msvcrt!isspace` at `0x18000fe77`
- `msvcrt!isspace` at `0x18000fe67`
- `msvcrt!isspace` at `0x18000fe77`
- `msvcrt!strpbrk` at `0x18000fbfa`
- `msvcrt!strpbrk` at `0x18000fbfa`
- `msvcrt!isdigit` at `0x18000fe4a`
- `msvcrt!isdigit` at `0x18000fe5a`
- `msvcrt!isdigit` at `0x18000fe4a`
- `msvcrt!isdigit` at `0x18000fe5a`
- `msvcrt!atoi` at `0x18000fe2c`
- `msvcrt!atoi` at `0x18000fe2c`
- `msvcrt!strchr` at `0x18000fee5`
- `msvcrt!strchr` at `0x18000fef6`
- `msvcrt!strchr` at `0x18000fee5`
- `msvcrt!strchr` at `0x18000fef6`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000fd84`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000ffb8`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000ffc5`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000fd84`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000ffb8`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000ffc5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000fde3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000fded`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000fdf7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180010084`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001008e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180010098`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000fde3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000fded`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000fdf7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180010084`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001008e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180010098`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000fb6a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000fb7b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000fb9d`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000fb6a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000fb7b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000fb9d`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000fd6c`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000fd94`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000ffac`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000fd6c`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000fd94`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000ffac`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000fcfb`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000fd3e`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000fd5b`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000fcfb`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000fd3e`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000fd5b`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000ff43`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000ff90`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000ff43`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000ff90`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000fcdf`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000fcdf`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000fcaa`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000fcaa`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::SetStatusAndHeaders(ISAPI_REQUEST *this, int a2, char *a3, char *a4, unsigned int a5)
{
  ISAPI_REQUEST *v7; // r15
  __int64 v9; // rax
  const char *v10; // r14
  __int64 i; // rdx
  char *v12; // rsi
  unsigned int v13; // r13d
  int v14; // ebx
  __int64 v15; // r12
  int AutomaticHeaders; // ebx
  __int64 v17; // rax
  int v18; // edx
  unsigned __int16 v20; // bx
  unsigned __int16 v21; // si
  int j; // ebx
  char *v23; // rdi
  const char *v24; // rcx
  char *v25; // rax
  char *v26; // r15
  char *k; // r8
  const char *v28; // r8
  const char *v29; // rdx
  __int64 (__fastcall *v30)(__int64, char *, char *, _QWORD, _DWORD); // rsi
  unsigned __int16 CCH; // di
  char *Str; // rbx
  char *v33; // rax
  const char *v34; // rcx
  __int64 v35; // rax
  _DWORD v37[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v38; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v39; // [rsp+60h] [rbp-A0h]
  _BYTE v40[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v41[56]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v42[56]; // [rsp+E0h] [rbp-20h] BYREF
  char v43[32]; // [rsp+118h] [rbp+18h] BYREF
  char v44[40]; // [rsp+138h] [rbp+38h] BYREF
  char v45[256]; // [rsp+160h] [rbp+60h] BYREF

  v37[1] = HIDWORD(a4);
  v7 = this;
  STRA::STRA((STRA *)v41, v43, 0x20u);
  STRA::STRA((STRA *)v42, v44, 0x20u);
  v38 = 0;
  v39 = 0;
  STRA::STRA((STRA *)v40, v45, 0x100u);
  v37[0] = 0;
  if ( a2 )
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v7 + 3) + 32LL))(*((_QWORD *)v7 + 3));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 96LL))(v9);
  }
  v10 = "\r\n";
  if ( a4 )
    v10 = a4;
  if ( !a3 || !*a3 )
    a3 = "200 OK";
  v12 = strpbrk(a3, "\r\n");
  if ( *((_DWORD *)v7 + 12) )
  {
LABEL_20:
    v13 = 0;
    v14 = 1;
    goto LABEL_21;
  }
  if ( *v10 != 13 || v10[1] != 10 )
  {
    for ( i = 0; v10[(unsigned int)i]; i = (unsigned int)(i + 1) )
    {
      if ( v10[(unsigned int)i] == 10 && v10[(unsigned int)(i + 1)] == 13 && v10[(unsigned int)(i + 2)] == 10 )
      {
        v13 = i + 3;
        goto LABEL_19;
      }
    }
    goto LABEL_20;
  }
  v13 = 2;
LABEL_19:
  v14 = 0;
LABEL_21:
  v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)v7 + 3) + 32LL))(*((_QWORD *)v7 + 3), i, 1);
  if ( v12 )
    v14 = 1;
  if ( v14 )
  {
    if ( !*((_DWORD *)v7 + 12) )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 128LL))(v15);
    AutomaticHeaders = STRA::Copy((STRA *)v40, "HTTP/1.1 ");
    if ( AutomaticHeaders < 0 )
      goto LABEL_43;
    if ( v12 )
    {
      LODWORD(v17) = (_DWORD)v12 - (_DWORD)a3;
    }
    else
    {
      v17 = -1;
      do
        ++v17;
      while ( a3[v17] );
    }
    AutomaticHeaders = STRA::Append((STRA *)v40, a3, v17);
    if ( AutomaticHeaders < 0 )
      goto LABEL_43;
    AutomaticHeaders = STRA::Append((STRA *)v40, "\r\n");
    if ( AutomaticHeaders < 0 )
      goto LABEL_43;
    AutomaticHeaders = ISAPI_REQUEST::GenerateAutomaticHeaders(v7, v18, (struct STRA *)v40);
    if ( AutomaticHeaders < 0 )
      goto LABEL_43;
    if ( v12 )
    {
      while ( *v12 == 13 || *v12 == 10 )
        ++v12;
      AutomaticHeaders = STRA::Append((STRA *)v40, v12);
      if ( AutomaticHeaders < 0 )
        goto LABEL_43;
    }
    if ( v10 && (AutomaticHeaders = STRA::Append((STRA *)v40, v10), AutomaticHeaders < 0)
      || STRA::QueryCCH((STRA *)v40)
      && (LODWORD(v38) = 0,
          *((_QWORD *)&v38 + 1) = STRA::QueryStr((STRA *)v40),
          LODWORD(v39) = STRA::QueryCCH((STRA *)v40),
          AutomaticHeaders = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD, int, _DWORD *, _QWORD))(*(_QWORD *)v15 + 168LL))(
                               v15,
                               &v38,
                               1,
                               0,
                               1,
                               v37,
                               0),
          AutomaticHeaders < 0) )
    {
LABEL_43:
      STRA::~STRA((STRA *)v40);
      STRA::~STRA((STRA *)v42);
      STRA::~STRA((STRA *)v41);
      return (unsigned int)AutomaticHeaders;
    }
  }
  else
  {
    v20 = 5;
    v21 = atoi(a3);
    if ( v21 != 401 )
      v20 = 0;
    for ( ; isdigit((unsigned __int8)*a3); ++a3 )
      ;
    if ( isspace((unsigned __int8)*a3) )
    {
      do
        ++a3;
      while ( isspace((unsigned __int8)*a3) );
      v7 = this;
    }
    AutomaticHeaders = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, _QWORD, _DWORD, _QWORD, unsigned int))(*(_QWORD *)v15 + 24LL))(
                         v15,
                         v21,
                         a3,
                         v20,
                         0,
                         0,
                         *((_DWORD *)v7 + 16) | a5);
    if ( AutomaticHeaders < 0 )
      goto LABEL_43;
    for ( j = 0; j + 3 < v13; j = (_DWORD)v26 - (_DWORD)v10 + 1 )
    {
      v23 = strchr(&v10[j], 58);
      v24 = &v10[j];
      do
      {
        do
        {
          v25 = strchr(v24, 10);
          v26 = v25;
          v24 = v25 + 1;
        }
        while ( v25[1] == 32 );
      }
      while ( *v24 == 9 );
      if ( !v23 || v23 >= v25 )
      {
        AutomaticHeaders = -2147024809;
        goto LABEL_43;
      }
      for ( k = v23 - 1; k >= &v10[j] && *k == 32; --k )
        ;
      AutomaticHeaders = STRA::Copy((STRA *)v42, &v10[j], (_DWORD)k - (_DWORD)v10 - j + 1);
      if ( AutomaticHeaders < 0 )
        goto LABEL_43;
      LODWORD(v23) = (_DWORD)v23 - (_DWORD)v10;
      do
        v23 = (char *)(unsigned int)((_DWORD)v23 + 1);
      while ( v10[(_QWORD)v23] == 32 );
      v28 = v26 - 1;
      v29 = &v10[(unsigned int)v23];
      while ( v28 >= v29 && (*v28 == 32 || *v28 == 13) )
        --v28;
      AutomaticHeaders = STRA::Copy((STRA *)v41, v29, (_DWORD)v28 - (_DWORD)v10 - (_DWORD)v23 + 1);
      if ( AutomaticHeaders < 0 )
        goto LABEL_43;
      v30 = *(__int64 (__fastcall **)(__int64, char *, char *, _QWORD, _DWORD))(*(_QWORD *)v15 + 40LL);
      CCH = STRA::QueryCCH((STRA *)v41);
      Str = STRA::QueryStr((STRA *)v41);
      v33 = STRA::QueryStr((STRA *)v42);
      AutomaticHeaders = v30(v15, v33, Str, CCH, 0);
      if ( AutomaticHeaders < 0 )
        goto LABEL_43;
    }
    v34 = &v10[v13];
    if ( *v34 )
    {
      LODWORD(v38) = 0;
      v35 = -1;
      *((_QWORD *)&v38 + 1) = &v10[v13];
      do
        ++v35;
      while ( v34[v35] );
      LODWORD(v39) = v35;
      AutomaticHeaders = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD, int, _DWORD *, _QWORD))(*(_QWORD *)v15 + 168LL))(
                           v15,
                           &v38,
                           1,
                           0,
                           1,
                           v37,
                           0);
      if ( AutomaticHeaders < 0 )
        goto LABEL_43;
    }
    v7 = this;
  }
  *((_DWORD *)v7 + 12) = 1;
  STRA::~STRA((STRA *)v40);
  STRA::~STRA((STRA *)v42);
  STRA::~STRA((STRA *)v41);
  return 0;
}

```

## disassembly

```asm
0x18000fb14  mov     [rsp-8+arg_8], rbx
0x18000fb19  push    rbp
0x18000fb1a  push    rsi
0x18000fb1b  push    rdi
0x18000fb1c  push    r12
0x18000fb1e  push    r13
0x18000fb20  push    r14
0x18000fb22  push    r15
0x18000fb24  lea     rbp, [rsp-170h]
0x18000fb2c  sub     rsp, 270h
0x18000fb33  mov     rax, cs:__security_cookie
0x18000fb3a  xor     rax, rsp
0x18000fb3d  mov     [rbp+1A0h+var_40], rax
0x18000fb44  mov     rdi, r8
0x18000fb47  mov     [rsp+2A0h+var_260], rcx
0x18000fb4c  mov     ebx, edx
0x18000fb4e  mov     [rsp+2A0h+var_258], r9
0x18000fb53  mov     r15, rcx
0x18000fb56  lea     rdx, [rbp+1A0h+var_188]
0x18000fb5a  mov     r14d, 20h ; ' '
0x18000fb60  lea     rcx, [rbp+1A0h+var_1F8]
0x18000fb64  mov     r8d, r14d
0x18000fb67  mov     rsi, r9
0x18000fb6a  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000fb70  mov     r8d, r14d
0x18000fb73  lea     rdx, [rbp+1A0h+var_168]
0x18000fb77  lea     rcx, [rbp+1A0h+var_1C0]
0x18000fb7b  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000fb81  xorps   xmm0, xmm0
0x18000fb84  lea     rdx, [rbp+1A0h+var_140]
0x18000fb88  mov     r8d, 100h
0x18000fb8e  lea     rcx, [rsp+2A0h+var_230]
0x18000fb93  movups  [rsp+2A0h+var_250], xmm0
0x18000fb98  movups  [rsp+2A0h+var_240], xmm0
0x18000fb9d  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000fba3  xor     r12d, r12d
0x18000fba6  mov     dword ptr [rsp+2A0h+var_258], r12d
0x18000fbab  test    ebx, ebx
0x18000fbad  jz      short loc_18000FBD1
0x18000fbaf  mov     rcx, [r15+18h]
0x18000fbb3  mov     rax, [rcx]
0x18000fbb6  mov     rax, [rax+20h]
0x18000fbba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbbf  mov     rdx, rax
0x18000fbc2  mov     rcx, [rax]
0x18000fbc5  mov     rax, [rcx+60h]
0x18000fbc9  mov     rcx, rdx
0x18000fbcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbd1  test    rsi, rsi
0x18000fbd4  lea     r14, Control; "\r\n"
0x18000fbdb  cmovnz  r14, rsi
0x18000fbdf  test    rdi, rdi
0x18000fbe2  jz      short loc_18000FBE9
0x18000fbe4  cmp     [rdi], r12b
0x18000fbe7  jnz     short loc_18000FBF0
0x18000fbe9  lea     rdi, a200Ok; "200 OK"
0x18000fbf0  lea     rdx, Control; "\r\n"
0x18000fbf7  mov     rcx, rdi; Str
0x18000fbfa  call    cs:__imp_strpbrk
0x18000fc00  mov     r8d, 1
0x18000fc06  mov     rsi, rax
0x18000fc09  cmp     [r15+30h], r12d
0x18000fc0d  jnz     short loc_18000FC56
0x18000fc0f  cmp     byte ptr [r14], 0Dh
0x18000fc13  jnz     short loc_18000FC22
0x18000fc15  cmp     byte ptr [r14+1], 0Ah
0x18000fc1a  jnz     short loc_18000FC22
0x18000fc1c  lea     r13d, [r8+1]
0x18000fc20  jmp     short loc_18000FC51
0x18000fc22  mov     edx, r12d
0x18000fc25  mov     eax, edx
0x18000fc27  cmp     [rax+r14], r12b
0x18000fc2b  jz      short loc_18000FC56
0x18000fc2d  cmp     byte ptr [rax+r14], 0Ah
0x18000fc32  jnz     short loc_18000FC48
0x18000fc34  lea     eax, [rdx+1]
0x18000fc37  cmp     byte ptr [rax+r14], 0Dh
0x18000fc3c  jnz     short loc_18000FC48
0x18000fc3e  lea     eax, [rdx+2]
0x18000fc41  cmp     byte ptr [rax+r14], 0Ah
0x18000fc46  jz      short loc_18000FC4D
0x18000fc48  add     edx, r8d
0x18000fc4b  jmp     short loc_18000FC25
0x18000fc4d  lea     r13d, [rdx+3]
0x18000fc51  mov     ebx, r12d
0x18000fc54  jmp     short loc_18000FC5C
0x18000fc56  mov     r13d, r12d
0x18000fc59  mov     ebx, r8d
0x18000fc5c  mov     rcx, [r15+18h]
0x18000fc60  mov     rax, [rcx]
0x18000fc63  mov     rax, [rax+20h]
0x18000fc67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc6c  test    rsi, rsi
0x18000fc6f  mov     r12, rax
0x18000fc72  mov     eax, 1
0x18000fc77  cmovnz  ebx, eax
0x18000fc7a  test    ebx, ebx
0x18000fc7c  jz      loc_18000FE29
0x18000fc82  xor     r13d, r13d
0x18000fc85  cmp     [r15+30h], r13d
0x18000fc89  jnz     short loc_18000FC9E
0x18000fc8b  mov     rcx, [r12]
0x18000fc8f  mov     rax, [rcx+80h]
0x18000fc96  mov     rcx, r12
0x18000fc99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc9e  lea     rdx, aHttp11; "HTTP/1.1 "
0x18000fca5  lea     rcx, [rsp+2A0h+var_230]
0x18000fcaa  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000fcb0  mov     ebx, eax
0x18000fcb2  test    eax, eax
0x18000fcb4  js      loc_18000FDDE
0x18000fcba  test    rsi, rsi
0x18000fcbd  jz      short loc_18000FCC7
0x18000fcbf  mov     rax, rsi
0x18000fcc2  sub     rax, rdi
0x18000fcc5  jmp     short loc_18000FCD4
0x18000fcc7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fccb  inc     rax
0x18000fcce  cmp     [rdi+rax], r13b
0x18000fcd2  jnz     short loc_18000FCCB
0x18000fcd4  mov     r8d, eax
0x18000fcd7  lea     rcx, [rsp+2A0h+var_230]
0x18000fcdc  mov     rdx, rdi
0x18000fcdf  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18000fce5  mov     ebx, eax
0x18000fce7  test    eax, eax
0x18000fce9  js      loc_18000FDDE
0x18000fcef  lea     rdx, Control; "\r\n"
0x18000fcf6  lea     rcx, [rsp+2A0h+var_230]
0x18000fcfb  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000fd01  mov     ebx, eax
0x18000fd03  test    eax, eax
0x18000fd05  js      loc_18000FDDE
0x18000fd0b  lea     r8, [rsp+2A0h+var_230]; struct STRA *
0x18000fd10  mov     rcx, r15; this
0x18000fd13  call    ?GenerateAutomaticHeaders@ISAPI_REQUEST@@AEAAJHPEAVSTRA@@@Z; ISAPI_REQUEST::GenerateAutomaticHeaders(int,STRA *)
0x18000fd18  mov     ebx, eax
0x18000fd1a  test    eax, eax
0x18000fd1c  js      loc_18000FDDE
0x18000fd22  test    rsi, rsi
0x18000fd25  jz      short loc_18000FD4E
0x18000fd27  cmp     byte ptr [rsi], 0Dh
0x18000fd2a  jz      short loc_18000FD31
0x18000fd2c  cmp     byte ptr [rsi], 0Ah
0x18000fd2f  jnz     short loc_18000FD36
0x18000fd31  inc     rsi
0x18000fd34  jmp     short loc_18000FD27
0x18000fd36  mov     rdx, rsi
0x18000fd39  lea     rcx, [rsp+2A0h+var_230]
0x18000fd3e  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000fd44  mov     ebx, eax
0x18000fd46  test    eax, eax
0x18000fd48  js      loc_18000FDDE
0x18000fd4e  test    r14, r14
0x18000fd51  jz      short loc_18000FD67
0x18000fd53  mov     rdx, r14
0x18000fd56  lea     rcx, [rsp+2A0h+var_230]
0x18000fd5b  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000fd61  mov     ebx, eax
0x18000fd63  test    eax, eax
0x18000fd65  js      short loc_18000FDDE
0x18000fd67  lea     rcx, [rsp+2A0h+var_230]
0x18000fd6c  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18000fd72  test    eax, eax
0x18000fd74  jz      loc_180010077
0x18000fd7a  lea     rcx, [rsp+2A0h+var_230]
0x18000fd7f  mov     dword ptr [rsp+2A0h+var_250], r13d
0x18000fd84  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000fd8a  lea     rcx, [rsp+2A0h+var_230]
0x18000fd8f  mov     qword ptr [rsp+2A0h+var_250+8], rax
0x18000fd94  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18000fd9a  lea     rcx, [rsp+2A0h+var_258]
0x18000fd9f  mov     [rsp+2A0h+var_270], r13
0x18000fda4  mov     [rsp+2A0h+var_278], rcx
0x18000fda9  lea     rdx, [rsp+2A0h+var_250]
0x18000fdae  mov     dword ptr [rsp+2A0h+var_240], eax
0x18000fdb2  mov     ecx, 1
0x18000fdb7  mov     rax, [r12]
0x18000fdbb  mov     r8d, ecx
0x18000fdbe  mov     [rsp+2A0h+var_280], ecx
0x18000fdc2  xor     r9d, r9d
0x18000fdc5  mov     rcx, r12
0x18000fdc8  mov     rax, [rax+0A8h]
0x18000fdcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdd4  mov     ebx, eax
0x18000fdd6  test    eax, eax
0x18000fdd8  jns     loc_180010077
0x18000fdde  lea     rcx, [rsp+2A0h+var_230]
0x18000fde3  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000fde9  lea     rcx, [rbp+1A0h+var_1C0]
0x18000fded  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000fdf3  lea     rcx, [rbp+1A0h+var_1F8]
0x18000fdf7  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000fdfd  mov     eax, ebx
0x18000fdff  mov     rcx, [rbp+1A0h+var_40]
0x18000fe06  xor     rcx, rsp; StackCookie
0x18000fe09  call    __security_check_cookie
0x18000fe0e  mov     rbx, [rsp+2A0h+arg_8]
0x18000fe16  add     rsp, 270h
0x18000fe1d  pop     r15
0x18000fe1f  pop     r14
0x18000fe21  pop     r13
0x18000fe23  pop     r12
0x18000fe25  pop     rdi
0x18000fe26  pop     rsi
0x18000fe27  pop     rbp
0x18000fe28  retn
0x18000fe29  mov     rcx, rdi; String
0x18000fe2c  call    cs:__imp_atoi
0x18000fe32  xor     ecx, ecx
0x18000fe34  mov     ebx, 5
0x18000fe39  mov     esi, eax
0x18000fe3b  mov     eax, 191h
0x18000fe40  cmp     si, ax
0x18000fe43  cmovnz  bx, cx
0x18000fe47  movzx   ecx, byte ptr [rdi]; C
0x18000fe4a  call    cs:__imp_isdigit
0x18000fe50  test    eax, eax
0x18000fe52  jz      short loc_18000FE64
0x18000fe54  inc     rdi
0x18000fe57  movzx   ecx, byte ptr [rdi]; C
0x18000fe5a  call    cs:__imp_isdigit
0x18000fe60  test    eax, eax
0x18000fe62  jnz     short loc_18000FE54
0x18000fe64  movzx   ecx, byte ptr [rdi]; C
0x18000fe67  call    cs:__imp_isspace
0x18000fe6d  test    eax, eax
0x18000fe6f  jz      short loc_18000FE86
0x18000fe71  inc     rdi
0x18000fe74  movzx   ecx, byte ptr [rdi]; C
0x18000fe77  call    cs:__imp_isspace
0x18000fe7d  test    eax, eax
0x18000fe7f  jnz     short loc_18000FE71
0x18000fe81  mov     r15, [rsp+2A0h+var_260]
0x18000fe86  mov     rax, [r12]
0x18000fe8a  movzx   r9d, bx
0x18000fe8e  mov     ecx, [rbp+1A0h+arg_20]
0x18000fe94  mov     r8, rdi
0x18000fe97  or      ecx, [r15+40h]
0x18000fe9b  movzx   edx, si
0x18000fe9e  mov     dword ptr [rsp+2A0h+var_270], ecx
0x18000fea2  xor     r15d, r15d
0x18000fea5  mov     rax, [rax+18h]
0x18000fea9  mov     rcx, r12
0x18000feac  mov     [rsp+2A0h+var_278], r15
0x18000feb1  mov     [rsp+2A0h+var_280], r15d
0x18000feb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000febb  mov     ebx, eax
0x18000febd  test    eax, eax
0x18000febf  js      loc_18000FDDE
0x18000fec5  mov     ebx, r15d
0x18000fec8  lea     edx, [r15+1]
0x18000fecc  lea     eax, [rbx+3]
0x18000fecf  cmp     eax, r13d
0x18000fed2  jnb     loc_18001000E
0x18000fed8  mov     esi, ebx
0x18000feda  mov     edx, 3Ah ; ':'; Val
0x18000fedf  add     rsi, r14
0x18000fee2  mov     rcx, rsi; Str
0x18000fee5  call    cs:__imp_strchr
0x18000feeb  mov     rdi, rax
0x18000feee  mov     rcx, rsi; Str
0x18000fef1  mov     edx, 0Ah; Val
0x18000fef6  call    cs:__imp_strchr
0x18000fefc  mov     r15, rax
0x18000feff  lea     rcx, [rax+1]
0x18000ff03  cmp     byte ptr [rcx], 20h ; ' '
0x18000ff06  jz      short loc_18000FEF1
0x18000ff08  cmp     byte ptr [rcx], 9
0x18000ff0b  jz      short loc_18000FEF1
0x18000ff0d  test    rdi, rdi
0x18000ff10  jz      loc_180010004
0x18000ff16  cmp     rdi, rax
0x18000ff19  jnb     loc_180010004
0x18000ff1f  lea     r8, [rdi-1]
0x18000ff23  jmp     short loc_18000FF2E
0x18000ff25  cmp     byte ptr [r8], 20h ; ' '
0x18000ff29  jnz     short loc_18000FF33
0x18000ff2b  dec     r8
0x18000ff2e  cmp     r8, rsi
0x18000ff31  jnb     short loc_18000FF25
0x18000ff33  sub     r8d, r14d
0x18000ff36  lea     rcx, [rbp+1A0h+var_1C0]
0x18000ff3a  sub     r8d, ebx
0x18000ff3d  mov     rdx, rsi
0x18000ff40  inc     r8d
0x18000ff43  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18000ff49  mov     ebx, eax
0x18000ff4b  test    eax, eax
0x18000ff4d  js      loc_18000FDDE
0x18000ff53  sub     edi, r14d
0x18000ff56  mov     ecx, 1
0x18000ff5b  add     edi, ecx
0x18000ff5d  cmp     byte ptr [rdi+r14], 20h ; ' '
0x18000ff62  jz      short loc_18000FF5B
0x18000ff64  mov     edx, edi
0x18000ff66  lea     r8, [r15-1]
0x18000ff6a  add     rdx, r14
0x18000ff6d  jmp     short loc_18000FF7E
0x18000ff6f  cmp     byte ptr [r8], 20h ; ' '
  ... truncated ...
```
