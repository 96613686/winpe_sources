# HSTS_HANDLER::RedirectHttpToHttps(IHttpContext *,int *)

- ea: `0x180004230`
- end: `0x180004586`
- name: `?RedirectHttpToHttps@HSTS_HANDLER@@CAJPEAVIHttpContext@@PEAH@Z`
- size: `854`
- prototype: `__int64 __fastcall(struct IHttpContext *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180001580`

## callees

- `0x180002736`
- `0x180002760`
- `0x180004230`
- `0x180005010`

## import_xrefs

- `msvcrt!strchr` at `0x1800042eb`
- `msvcrt!strchr` at `0x18000430a`
- `msvcrt!strchr` at `0x180004329`
- `msvcrt!strchr` at `0x180004417`
- `msvcrt!strchr` at `0x1800042eb`
- `msvcrt!strchr` at `0x18000430a`
- `msvcrt!strchr` at `0x180004329`
- `msvcrt!strchr` at `0x180004417`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180004528`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180004528`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004553`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004553`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180004282`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180004282`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000437e`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800043fd`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000437e`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800043fd`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000442e`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180004469`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800044a7`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000442e`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180004469`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800044a7`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180004399`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000444d`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180004484`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180004399`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000444d`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180004484`

## string_xrefs

- `0x1800044e9`: `Moved Permanently`

## pseudocode

```c
__int64 __fastcall HSTS_HANDLER::RedirectHttpToHttps(struct IHttpContext *a1, int *a2)
{
  BOOL v4; // r14d
  __int64 v5; // rax
  __int64 v6; // rax
  const char *v7; // rbx
  int v8; // edi
  const char *v9; // rsi
  char *v10; // rbp
  const char *v11; // rcx
  char *v12; // rax
  __int64 v13; // rbx
  char *v14; // rax
  char *v15; // rbx
  const char *v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, char *, _QWORD, _QWORD); // rbx
  char *v20; // rax
  unsigned int v22; // [rsp+40h] [rbp-498h] BYREF
  char *Str; // [rsp+48h] [rbp-490h] BYREF
  _BYTE v24[64]; // [rsp+50h] [rbp-488h] BYREF
  char v25[1024]; // [rsp+90h] [rbp-448h] BYREF

  Str = 0;
  v22 = 0;
  v4 = 0;
  STRA::STRA((STRA *)v24, v25, 0x400u);
  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  v7 = *(const char **)(v6 + 56);
  if ( v7 && *v7 != 47 )
  {
    v8 = 0;
    if ( strncmp_0(*(const char **)(v6 + 56), "http://", 7u) )
      goto LABEL_38;
    v9 = v7 + 7;
    v10 = strchr(v7 + 7, 47);
    if ( v7 == (const char *)-7LL )
      goto LABEL_38;
    v11 = v7 + 7;
    if ( *v9 == 91 )
    {
      v12 = strchr(v11, 93);
      if ( !v12 )
        goto LABEL_38;
      v13 = v12 - v9 + 1;
      goto LABEL_17;
    }
    v14 = strchr(v11, 58);
    v15 = v14;
    if ( v14 )
    {
      if ( v10 && v10 <= v14 )
      {
        v13 = v10 - v9;
        goto LABEL_17;
      }
    }
    else
    {
      if ( !v10 )
      {
        v13 = -1;
        do
          ++v13;
        while ( v9[v13] );
        goto LABEL_17;
      }
      v15 = v10;
    }
    v13 = v15 - v9;
LABEL_17:
    if ( v13 <= 0 )
      goto LABEL_38;
    v8 = STRA::Copy((STRA *)v24, "https://");
    if ( v8 < 0 )
      goto LABEL_38;
    v8 = STRA::Append((STRA *)v24, v9, v13);
    if ( v8 < 0 )
      goto LABEL_38;
    v16 = "/";
    if ( v10 )
      v16 = v10;
    goto LABEL_34;
  }
  v8 = (*(__int64 (__fastcall **)(struct IHttpContext *, const char *, char **, unsigned int *))(*(_QWORD *)a1 + 120LL))(
         a1,
         "SERVER_NAME",
         &Str,
         &v22);
  if ( v8 < 0 )
    goto LABEL_38;
  if ( !v22 )
    goto LABEL_38;
  v8 = STRA::Copy((STRA *)v24, "https://");
  if ( v8 < 0 )
    goto LABEL_38;
  if ( strchr(Str, 58) )
  {
    v8 = STRA::Append((STRA *)v24, "[");
    if ( v8 < 0 )
      goto LABEL_38;
    v8 = STRA::Append((STRA *)v24, Str, v22);
    if ( v8 < 0 )
      goto LABEL_38;
    v8 = STRA::Append((STRA *)v24, "]");
    if ( v8 < 0 )
      goto LABEL_38;
  }
  else
  {
    v8 = STRA::Append((STRA *)v24, Str, v22);
    if ( v8 < 0 )
      goto LABEL_38;
  }
  v16 = "/";
  if ( v7 )
    v16 = v7;
LABEL_34:
  v8 = STRA::Append((STRA *)v24, v16);
  if ( v8 >= 0 )
  {
    v17 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, const char *, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v17 + 24LL))(
           v17,
           301,
           "Moved Permanently",
           0,
           0,
           0,
           0);
    if ( v8 >= 0 )
    {
      v18 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
      v19 = *(__int64 (__fastcall **)(__int64, char *, _QWORD, _QWORD))(*(_QWORD *)v18 + 152LL);
      v20 = STRA::QueryStr((STRA *)v24);
      v8 = v19(v18, v20, 0, 0);
      v4 = v8 >= 0;
    }
    else
    {
      v4 = 0;
    }
  }
LABEL_38:
  *a2 = v4;
  STRA::~STRA((STRA *)v24);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004230  mov     [rsp+arg_10], rbx
0x180004235  push    rbp
0x180004236  push    rsi
0x180004237  push    rdi
0x180004238  push    r12
0x18000423a  push    r13
0x18000423c  push    r14
0x18000423e  push    r15
0x180004240  sub     rsp, 4A0h
0x180004247  mov     rax, cs:__security_cookie
0x18000424e  xor     rax, rsp
0x180004251  mov     [rsp+4D8h+var_48], rax
0x180004259  xor     r13d, r13d
0x18000425c  mov     r12, rdx
0x18000425f  mov     r15, rcx
0x180004262  mov     [rsp+4D8h+Str], r13
0x180004267  lea     rdx, [rsp+4D8h+var_448]
0x18000426f  mov     [rsp+4D8h+var_498], r13d
0x180004274  lea     rcx, [rsp+4D8h+var_488]
0x180004279  mov     r8d, 400h
0x18000427f  mov     r14d, r13d
0x180004282  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180004288  mov     rax, [r15]
0x18000428b  mov     rcx, r15
0x18000428e  mov     rax, [rax+18h]
0x180004292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004297  mov     rdx, rax
0x18000429a  mov     rcx, [rax]
0x18000429d  mov     rax, [rcx+8]
0x1800042a1  mov     rcx, rdx
0x1800042a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042a9  mov     rbx, [rax+38h]
0x1800042ad  test    rbx, rbx
0x1800042b0  jz      loc_1800043BC
0x1800042b6  cmp     byte ptr [rbx], 2Fh ; '/'
0x1800042b9  jz      loc_1800043BC
0x1800042bf  mov     r8d, 7; MaxCount
0x1800042c5  lea     rdx, Str2; "http://"
0x1800042cc  mov     rcx, rbx; Str1
0x1800042cf  mov     edi, r13d
0x1800042d2  call    strncmp_0
0x1800042d7  test    eax, eax
0x1800042d9  jnz     loc_18000454A
0x1800042df  lea     rsi, [rbx+7]
0x1800042e3  mov     edx, 2Fh ; '/'; Val
0x1800042e8  mov     rcx, rsi; Str
0x1800042eb  call    cs:__imp_strchr
0x1800042f1  mov     rbp, rax
0x1800042f4  test    rsi, rsi
0x1800042f7  jz      loc_18000454A
0x1800042fd  cmp     byte ptr [rsi], 5Bh ; '['
0x180004300  mov     rcx, rsi; Str
0x180004303  jnz     short loc_180004324
0x180004305  mov     edx, 5Dh ; ']'; Val
0x18000430a  call    cs:__imp_strchr
0x180004310  mov     rbx, rax
0x180004313  test    rax, rax
0x180004316  jz      loc_18000454A
0x18000431c  sub     rbx, rsi
0x18000431f  inc     rbx
0x180004322  jmp     short loc_180004369
0x180004324  mov     edx, 3Ah ; ':'; Val
0x180004329  call    cs:__imp_strchr
0x18000432f  mov     rbx, rax
0x180004332  test    rax, rax
0x180004335  jz      short loc_180004349
0x180004337  test    rbp, rbp
0x18000433a  jz      short loc_180004351
0x18000433c  cmp     rbp, rax
0x18000433f  ja      short loc_180004351
0x180004341  mov     rbx, rbp
0x180004344  sub     rbx, rsi
0x180004347  jmp     short loc_180004369
0x180004349  test    rbp, rbp
0x18000434c  jz      short loc_180004356
0x18000434e  mov     rbx, rbp
0x180004351  sub     rbx, rsi
0x180004354  jmp     short loc_180004369
0x180004356  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000435d  nop     dword ptr [rax]
0x180004360  inc     rbx
0x180004363  cmp     [rsi+rbx], dil
0x180004367  jnz     short loc_180004360
0x180004369  test    rbx, rbx
0x18000436c  jle     loc_18000454A
0x180004372  lea     rdx, aHttps; "https://"
0x180004379  lea     rcx, [rsp+4D8h+var_488]
0x18000437e  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180004384  mov     edi, eax
0x180004386  test    eax, eax
0x180004388  js      loc_18000454A
0x18000438e  mov     r8d, ebx
0x180004391  lea     rcx, [rsp+4D8h+var_488]
0x180004396  mov     rdx, rsi
0x180004399  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18000439f  mov     edi, eax
0x1800043a1  test    eax, eax
0x1800043a3  js      loc_18000454A
0x1800043a9  test    rbp, rbp
0x1800043ac  lea     rdx, asc_1800068CC; "/"
0x1800043b3  cmovnz  rdx, rbp
0x1800043b7  jmp     loc_1800044A2
0x1800043bc  mov     rax, [r15]
0x1800043bf  lea     r9, [rsp+4D8h+var_498]
0x1800043c4  lea     r8, [rsp+4D8h+Str]
0x1800043c9  mov     rcx, r15
0x1800043cc  lea     rdx, aServerName; "SERVER_NAME"
0x1800043d3  mov     rax, [rax+78h]
0x1800043d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043dc  mov     edi, eax
0x1800043de  test    eax, eax
0x1800043e0  js      loc_18000454A
0x1800043e6  cmp     [rsp+4D8h+var_498], r13d
0x1800043eb  jbe     loc_18000454A
0x1800043f1  lea     rdx, aHttps; "https://"
0x1800043f8  lea     rcx, [rsp+4D8h+var_488]
0x1800043fd  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180004403  mov     edi, eax
0x180004405  test    eax, eax
0x180004407  js      loc_18000454A
0x18000440d  mov     rcx, [rsp+4D8h+Str]; Str
0x180004412  mov     edx, 3Ah ; ':'; Val
0x180004417  call    cs:__imp_strchr
0x18000441d  lea     rcx, [rsp+4D8h+var_488]
0x180004422  test    rax, rax
0x180004425  jz      short loc_18000447A
0x180004427  lea     rdx, asc_1800068C4; "["
0x18000442e  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180004434  mov     edi, eax
0x180004436  test    eax, eax
0x180004438  js      loc_18000454A
0x18000443e  mov     r8d, [rsp+4D8h+var_498]
0x180004443  lea     rcx, [rsp+4D8h+var_488]
0x180004448  mov     rdx, [rsp+4D8h+Str]
0x18000444d  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180004453  mov     edi, eax
0x180004455  test    eax, eax
0x180004457  js      loc_18000454A
0x18000445d  lea     rdx, asc_1800068C8; "]"
0x180004464  lea     rcx, [rsp+4D8h+var_488]
0x180004469  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000446f  mov     edi, eax
0x180004471  test    eax, eax
0x180004473  jns     short loc_180004494
0x180004475  jmp     loc_18000454A
0x18000447a  mov     r8d, [rsp+4D8h+var_498]
0x18000447f  mov     rdx, [rsp+4D8h+Str]
0x180004484  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18000448a  mov     edi, eax
0x18000448c  test    eax, eax
0x18000448e  js      loc_18000454A
0x180004494  test    rbx, rbx
0x180004497  lea     rdx, asc_1800068CC; "/"
0x18000449e  cmovnz  rdx, rbx
0x1800044a2  lea     rcx, [rsp+4D8h+var_488]
0x1800044a7  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x1800044ad  mov     edi, eax
0x1800044af  test    eax, eax
0x1800044b1  js      loc_18000454A
0x1800044b7  mov     rax, [r15]
0x1800044ba  mov     rcx, r15
0x1800044bd  mov     r14d, 1
0x1800044c3  mov     rax, [rax+20h]
0x1800044c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044cc  mov     r10, rax
0x1800044cf  mov     [rsp+4D8h+var_4A8], r13d
0x1800044d4  xor     r9d, r9d
0x1800044d7  mov     [rsp+4D8h+var_4B0], r13
0x1800044dc  mov     edx, 12Dh
0x1800044e1  mov     [rsp+4D8h+var_4B8], r13d
0x1800044e6  mov     rcx, [rax]
0x1800044e9  lea     r8, aMovedPermanent; "Moved Permanently"
0x1800044f0  mov     rax, [rcx+18h]
0x1800044f4  mov     rcx, r10
0x1800044f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044fc  mov     edi, eax
0x1800044fe  test    eax, eax
0x180004500  jns     short loc_180004507
0x180004502  mov     r14d, r13d
0x180004505  jmp     short loc_18000454A
0x180004507  mov     rax, [r15]
0x18000450a  mov     rcx, r15
0x18000450d  mov     rax, [rax+20h]
0x180004511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004516  mov     rdi, rax
0x180004519  mov     rcx, [rax]
0x18000451c  mov     rbx, [rcx+98h]
0x180004523  lea     rcx, [rsp+4D8h+var_488]
0x180004528  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000452e  xor     r9d, r9d
0x180004531  xor     r8d, r8d
0x180004534  mov     rdx, rax
0x180004537  mov     rcx, rdi
0x18000453a  mov     rax, rbx
0x18000453d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004542  test    eax, eax
0x180004544  mov     edi, eax
0x180004546  cmovs   r14d, r13d
0x18000454a  lea     rcx, [rsp+4D8h+var_488]
0x18000454f  mov     [r12], r14d
0x180004553  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180004559  mov     eax, edi
0x18000455b  mov     rcx, [rsp+4D8h+var_48]
0x180004563  xor     rcx, rsp; StackCookie
0x180004566  call    __security_check_cookie
0x18000456b  mov     rbx, [rsp+4D8h+arg_10]
0x180004573  add     rsp, 4A0h
0x18000457a  pop     r15
0x18000457c  pop     r14
0x18000457e  pop     r13
0x180004580  pop     r12
0x180004582  pop     rdi
0x180004583  pop     rsi
0x180004584  pop     rbp
0x180004585  retn
```
