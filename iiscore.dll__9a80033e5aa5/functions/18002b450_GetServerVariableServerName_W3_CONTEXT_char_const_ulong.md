# GetServerVariableServerName(W3_CONTEXT *,char const * *,ulong *)

- ea: `0x18002b450`
- end: `0x18002b65b`
- name: `?GetServerVariableServerName@@YAJPEAVW3_CONTEXT@@PEAPEBDPEAK@Z`
- size: `523`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const char **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800159e0`
- `0x180021490`
- `0x18002b450`
- `0x180034382`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!strchr` at `0x18002b4b1`
- `msvcrt!strchr` at `0x18002b4c7`
- `msvcrt!strchr` at `0x18002b4e5`
- `msvcrt!strchr` at `0x18002b4b1`
- `msvcrt!strchr` at `0x18002b4c7`
- `msvcrt!strchr` at `0x18002b4e5`
- `msvcrt!wcschr` at `0x18002b59d`
- `msvcrt!wcschr` at `0x18002b59d`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002b551`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002b551`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18002b53f`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18002b53f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002b62e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002b62e`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002b5d1`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002b5d1`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002b5df`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002b5df`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18002b481`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18002b481`
- `iisutil!?CopyW@STRA@@QEAAJPEBGK@Z` at `0x18002b5c0`
- `iisutil!?CopyW@STRA@@QEAAJPEBGK@Z` at `0x18002b5c0`

## pseudocode

```c
__int64 __fastcall GetServerVariableServerName(struct W3_CONTEXT *a1, const char **a2, unsigned int *a3)
{
  W3_REQUEST *v6; // rcx
  const char *v7; // rax
  const char *Str; // rdi
  char *v9; // rax
  const char *v10; // rbx
  char *v11; // rax
  unsigned __int16 v12; // cx
  char *v13; // rax
  unsigned int CCH; // esi
  W3_METADATA *v15; // rcx
  __int64 v16; // rax
  STRU *v17; // rbx
  const unsigned __int16 *v18; // rbx
  const unsigned __int16 *AlternateHostName; // rax
  __int64 v20; // rax
  wchar_t v21; // dx
  wchar_t *v22; // rax
  int v23; // ebx
  char *v24; // rax
  const char *v25; // rbp
  unsigned __int16 v27; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v28[56]; // [rsp+28h] [rbp-80h] BYREF

  STRA::STRA((STRA *)v28);
  v6 = (W3_REQUEST *)*((_QWORD *)a1 + 6);
  v27 = 0;
  v7 = W3_REQUEST::QueryHeader(v6, 0x1Cu, &v27);
  Str = v7;
  if ( !v7 )
  {
    v15 = (W3_METADATA *)*((_QWORD *)a1 + 1114);
    if ( v15 )
    {
      AlternateHostName = W3_METADATA::QueryAlternateHostName(v15);
    }
    else
    {
      v16 = *((_QWORD *)a1 + 1009);
      if ( !v16 )
        goto LABEL_22;
      v17 = (STRU *)(v16 + 144);
      if ( STRU::IsEmpty((STRU *)(v16 + 144)) )
      {
        v18 = 0;
        goto LABEL_18;
      }
      AlternateHostName = STRU::QueryStr(v17);
    }
    v18 = AlternateHostName;
LABEL_18:
    if ( v18 )
    {
      v20 = -1;
      do
        ++v20;
      while ( v18[v20] );
LABEL_28:
      v23 = STRA::CopyW((STRA *)v28, v18, v20);
      if ( v23 < 0 )
        goto LABEL_34;
      Str = STRA::QueryStr((STRA *)v28);
      CCH = STRA::QueryCCH((STRA *)v28);
      goto LABEL_30;
    }
LABEL_22:
    v18 = *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)a1 + 6) + 40LL) + 80LL);
    if ( *v18 == 91 )
    {
      ++v18;
      v21 = 93;
    }
    else
    {
      v21 = 58;
    }
    v22 = wcschr(v18, v21);
    if ( !v22 )
    {
      v23 = -2147467259;
      goto LABEL_34;
    }
    v20 = v22 - v18;
    goto LABEL_28;
  }
  v9 = strchr(v7, 91);
  if ( !v9 )
  {
    v13 = strchr(Str, 58);
    if ( v13 )
    {
      v12 = (_WORD)v13 - (_WORD)Str;
      goto LABEL_8;
    }
LABEL_7:
    v12 = v27;
    goto LABEL_8;
  }
  v10 = v9 + 1;
  v11 = strchr(v9 + 1, 93);
  if ( !v11 )
    goto LABEL_7;
  Str = v10;
  v12 = (_WORD)v11 - (_WORD)v10;
LABEL_8:
  if ( !Str[v12] )
  {
    *a2 = Str;
    *a3 = v12;
LABEL_33:
    v23 = 0;
    goto LABEL_34;
  }
  CCH = v12;
LABEL_30:
  v24 = (char *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *, _QWORD))(*(_QWORD *)a1 + 144LL))(a1, CCH + 1);
  v25 = v24;
  if ( v24 )
  {
    memcpy_0(v24, Str, CCH);
    v25[CCH] = 0;
    *a2 = v25;
    *a3 = CCH;
    goto LABEL_33;
  }
  v23 = -2147024888;
LABEL_34:
  STRA::~STRA((STRA *)v28);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x18002b450  mov     [rsp+arg_18], rbx
0x18002b455  push    rbp
0x18002b456  push    rsi
0x18002b457  push    rdi
0x18002b458  push    r12
0x18002b45a  push    r13
0x18002b45c  push    r14
0x18002b45e  push    r15
0x18002b460  sub     rsp, 70h
0x18002b464  mov     rax, cs:__security_cookie
0x18002b46b  xor     rax, rsp
0x18002b46e  mov     [rsp+0A8h+var_48], rax
0x18002b473  mov     r14, rcx
0x18002b476  mov     r12, r8
0x18002b479  lea     rcx, [rsp+0A8h+var_80]
0x18002b47e  mov     r15, rdx
0x18002b481  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18002b487  mov     rcx, [r14+30h]; this
0x18002b48b  lea     r8, [rsp+0A8h+var_88]; unsigned __int16 *
0x18002b490  xor     r13d, r13d
0x18002b493  mov     [rsp+0A8h+var_88], r13w
0x18002b499  lea     edx, [r13+1Ch]; enum _HTTP_HEADER_ID
0x18002b49d  call    ?QueryHeader@W3_REQUEST@@QEBAPEBDW4_HTTP_HEADER_ID@@PEAG@Z; W3_REQUEST::QueryHeader(_HTTP_HEADER_ID,ushort *)
0x18002b4a2  mov     rdi, rax
0x18002b4a5  test    rax, rax
0x18002b4a8  jz      short loc_18002B51D
0x18002b4aa  lea     edx, [r13+5Bh]; Val
0x18002b4ae  mov     rcx, rax; Str
0x18002b4b1  call    cs:__imp_strchr
0x18002b4b7  test    rax, rax
0x18002b4ba  jz      short loc_18002B4DD
0x18002b4bc  lea     rbx, [rax+1]
0x18002b4c0  mov     rcx, rbx; Str
0x18002b4c3  lea     edx, [r13+5Dh]; Val
0x18002b4c7  call    cs:__imp_strchr
0x18002b4cd  mov     rcx, rax
0x18002b4d0  test    rax, rax
0x18002b4d3  jz      short loc_18002B4F8
0x18002b4d5  mov     rdi, rbx
0x18002b4d8  sub     cx, bx
0x18002b4db  jmp     short loc_18002B4FD
0x18002b4dd  mov     edx, 3Ah ; ':'; Val
0x18002b4e2  mov     rcx, rdi; Str
0x18002b4e5  call    cs:__imp_strchr
0x18002b4eb  test    rax, rax
0x18002b4ee  jz      short loc_18002B4F8
0x18002b4f0  sub     ax, di
0x18002b4f3  movzx   ecx, ax
0x18002b4f6  jmp     short loc_18002B4FD
0x18002b4f8  movzx   ecx, [rsp+0A8h+var_88]
0x18002b4fd  movzx   eax, cx
0x18002b500  cmp     [rax+rdi], r13b
0x18002b504  jnz     short loc_18002B515
0x18002b506  movzx   eax, cx
0x18002b509  mov     [r15], rdi
0x18002b50c  mov     [r12], eax
0x18002b510  jmp     loc_18002B626
0x18002b515  movzx   esi, cx
0x18002b518  jmp     loc_18002B5E7
0x18002b51d  mov     rcx, [r14+22D0h]; this
0x18002b524  test    rcx, rcx
0x18002b527  jnz     short loc_18002B559
0x18002b529  mov     rax, [r14+1F88h]
0x18002b530  test    rax, rax
0x18002b533  jz      short loc_18002B576
0x18002b535  lea     rbx, [rax+90h]
0x18002b53c  mov     rcx, rbx
0x18002b53f  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18002b545  test    al, al
0x18002b547  jz      short loc_18002B54E
0x18002b549  mov     rbx, r13
0x18002b54c  jmp     short loc_18002B561
0x18002b54e  mov     rcx, rbx
0x18002b551  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18002b557  jmp     short loc_18002B55E
0x18002b559  call    ?QueryAlternateHostName@W3_METADATA@@QEBAPEBGXZ; W3_METADATA::QueryAlternateHostName(void)
0x18002b55e  mov     rbx, rax
0x18002b561  test    rbx, rbx
0x18002b564  jz      short loc_18002B576
0x18002b566  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b56a  inc     rax
0x18002b56d  cmp     [rbx+rax*2], r13w
0x18002b572  jnz     short loc_18002B56A
0x18002b574  jmp     short loc_18002B5B5
0x18002b576  mov     rax, [r14+30h]
0x18002b57a  mov     rcx, [rax+28h]
0x18002b57e  mov     eax, 5Bh ; '['
0x18002b583  mov     rbx, [rcx+50h]
0x18002b587  cmp     [rbx], ax
0x18002b58a  jnz     short loc_18002B595
0x18002b58c  add     rbx, 2
0x18002b590  lea     edx, [rax+2]
0x18002b593  jmp     short loc_18002B59A
0x18002b595  mov     edx, 3Ah ; ':'; Ch
0x18002b59a  mov     rcx, rbx; Str
0x18002b59d  call    cs:__imp_wcschr
0x18002b5a3  test    rax, rax
0x18002b5a6  jnz     short loc_18002B5AF
0x18002b5a8  mov     ebx, 80004005h
0x18002b5ad  jmp     short loc_18002B629
0x18002b5af  sub     rax, rbx
0x18002b5b2  sar     rax, 1
0x18002b5b5  mov     r8d, eax
0x18002b5b8  lea     rcx, [rsp+0A8h+var_80]
0x18002b5bd  mov     rdx, rbx
0x18002b5c0  call    cs:__imp_?CopyW@STRA@@QEAAJPEBGK@Z; STRA::CopyW(ushort const *,ulong)
0x18002b5c6  mov     ebx, eax
0x18002b5c8  test    eax, eax
0x18002b5ca  js      short loc_18002B629
0x18002b5cc  lea     rcx, [rsp+0A8h+var_80]
0x18002b5d1  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002b5d7  lea     rcx, [rsp+0A8h+var_80]
0x18002b5dc  mov     rdi, rax
0x18002b5df  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18002b5e5  mov     esi, eax
0x18002b5e7  mov     r8, [r14]
0x18002b5ea  lea     edx, [rsi+1]
0x18002b5ed  mov     rcx, r14
0x18002b5f0  mov     rax, [r8+90h]
0x18002b5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5fc  mov     rbp, rax
0x18002b5ff  test    rax, rax
0x18002b602  jnz     short loc_18002B60B
0x18002b604  mov     ebx, 80070008h
0x18002b609  jmp     short loc_18002B629
0x18002b60b  mov     r8d, esi; Size
0x18002b60e  mov     rdx, rdi; Src
0x18002b611  mov     rcx, rbp; void *
0x18002b614  mov     ebx, esi
0x18002b616  call    memcpy_0
0x18002b61b  mov     [rbx+rbp], r13b
0x18002b61f  mov     [r15], rbp
0x18002b622  mov     [r12], esi
0x18002b626  mov     ebx, r13d
0x18002b629  lea     rcx, [rsp+0A8h+var_80]
0x18002b62e  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002b634  mov     eax, ebx
0x18002b636  mov     rcx, [rsp+0A8h+var_48]
0x18002b63b  xor     rcx, rsp; StackCookie
0x18002b63e  call    __security_check_cookie
0x18002b643  mov     rbx, [rsp+0A8h+arg_18]
0x18002b64b  add     rsp, 70h
0x18002b64f  pop     r15
0x18002b651  pop     r14
0x18002b653  pop     r13
0x18002b655  pop     r12
0x18002b657  pop     rdi
0x18002b658  pop     rsi
0x18002b659  pop     rbp
0x18002b65a  retn
```
