# GetServerVariableServerName(W3_CONTEXT *,char const * *,ulong *)

- ea: `0x18002daf0`
- end: `0x18002dd45`
- name: `?GetServerVariableServerName@@YAJPEAVW3_CONTEXT@@PEAPEBDPEAK@Z`
- size: `597`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const char **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180016b40`
- `0x180023100`
- `0x18002daf0`
- `0x180037722`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!strchr` at `0x18002db5b`
- `msvcrt!strchr` at `0x18002db77`
- `msvcrt!strchr` at `0x18002db9b`
- `msvcrt!strchr` at `0x18002db5b`
- `msvcrt!strchr` at `0x18002db77`
- `msvcrt!strchr` at `0x18002db9b`
- `msvcrt!wcschr` at `0x18002dc65`
- `msvcrt!wcschr` at `0x18002dc65`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002dc13`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002dc13`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18002dbfb`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18002dbfb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002dd11`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002dd11`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002dca8`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002dca8`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002dcbc`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002dcbc`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18002db21`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18002db21`
- `iisutil!?CopyW@STRA@@QEAAJPEBGK@Z` at `0x18002dc91`
- `iisutil!?CopyW@STRA@@QEAAJPEBGK@Z` at `0x18002dc91`

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
  v7 = W3_REQUEST::QueryHeader(v6, HttpHeaderHost, &v27);
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
0x18002daf0  mov     [rsp+arg_18], rbx
0x18002daf5  push    rbp
0x18002daf6  push    rsi
0x18002daf7  push    rdi
0x18002daf8  push    r12
0x18002dafa  push    r13
0x18002dafc  push    r14
0x18002dafe  push    r15
0x18002db00  sub     rsp, 70h
0x18002db04  mov     rax, cs:__security_cookie
0x18002db0b  xor     rax, rsp
0x18002db0e  mov     [rsp+0A8h+var_48], rax
0x18002db13  mov     r14, rcx
0x18002db16  mov     r12, r8
0x18002db19  lea     rcx, [rsp+0A8h+var_80]
0x18002db1e  mov     r15, rdx
0x18002db21  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18002db28  nop     dword ptr [rax+rax+00h]
0x18002db2d  mov     rcx, [r14+30h]; this
0x18002db31  lea     r8, [rsp+0A8h+var_88]; unsigned __int16 *
0x18002db36  xor     r13d, r13d
0x18002db39  mov     [rsp+0A8h+var_88], r13w
0x18002db3f  lea     edx, [r13+1Ch]; enum _HTTP_HEADER_ID
0x18002db43  call    ?QueryHeader@W3_REQUEST@@QEBAPEBDW4_HTTP_HEADER_ID@@PEAG@Z; W3_REQUEST::QueryHeader(_HTTP_HEADER_ID,ushort *)
0x18002db48  mov     rdi, rax
0x18002db4b  test    rax, rax
0x18002db4e  jz      loc_18002DBD9
0x18002db54  lea     edx, [r13+5Bh]; Val
0x18002db58  mov     rcx, rax; Str
0x18002db5b  call    cs:__imp_strchr
0x18002db62  nop     dword ptr [rax+rax+00h]
0x18002db67  test    rax, rax
0x18002db6a  jz      short loc_18002DB93
0x18002db6c  lea     rbx, [rax+1]
0x18002db70  mov     rcx, rbx; Str
0x18002db73  lea     edx, [r13+5Dh]; Val
0x18002db77  call    cs:__imp_strchr
0x18002db7e  nop     dword ptr [rax+rax+00h]
0x18002db83  mov     rcx, rax
0x18002db86  test    rax, rax
0x18002db89  jz      short loc_18002DBB4
0x18002db8b  mov     rdi, rbx
0x18002db8e  sub     cx, bx
0x18002db91  jmp     short loc_18002DBB9
0x18002db93  mov     edx, 3Ah ; ':'; Val
0x18002db98  mov     rcx, rdi; Str
0x18002db9b  call    cs:__imp_strchr
0x18002dba2  nop     dword ptr [rax+rax+00h]
0x18002dba7  test    rax, rax
0x18002dbaa  jz      short loc_18002DBB4
0x18002dbac  sub     ax, di
0x18002dbaf  movzx   ecx, ax
0x18002dbb2  jmp     short loc_18002DBB9
0x18002dbb4  movzx   ecx, [rsp+0A8h+var_88]
0x18002dbb9  movzx   eax, cx
0x18002dbbc  cmp     [rax+rdi], r13b
0x18002dbc0  jnz     short loc_18002DBD1
0x18002dbc2  movzx   eax, cx
0x18002dbc5  mov     [r15], rdi
0x18002dbc8  mov     [r12], eax
0x18002dbcc  jmp     loc_18002DD09
0x18002dbd1  movzx   esi, cx
0x18002dbd4  jmp     loc_18002DCCA
0x18002dbd9  mov     rcx, [r14+22D0h]; this
0x18002dbe0  test    rcx, rcx
0x18002dbe3  jnz     short loc_18002DC21
0x18002dbe5  mov     rax, [r14+1F88h]
0x18002dbec  test    rax, rax
0x18002dbef  jz      short loc_18002DC3E
0x18002dbf1  lea     rbx, [rax+90h]
0x18002dbf8  mov     rcx, rbx
0x18002dbfb  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18002dc02  nop     dword ptr [rax+rax+00h]
0x18002dc07  test    al, al
0x18002dc09  jz      short loc_18002DC10
0x18002dc0b  mov     rbx, r13
0x18002dc0e  jmp     short loc_18002DC29
0x18002dc10  mov     rcx, rbx
0x18002dc13  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18002dc1a  nop     dword ptr [rax+rax+00h]
0x18002dc1f  jmp     short loc_18002DC26
0x18002dc21  call    ?QueryAlternateHostName@W3_METADATA@@QEBAPEBGXZ; W3_METADATA::QueryAlternateHostName(void)
0x18002dc26  mov     rbx, rax
0x18002dc29  test    rbx, rbx
0x18002dc2c  jz      short loc_18002DC3E
0x18002dc2e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002dc32  inc     rax
0x18002dc35  cmp     [rbx+rax*2], r13w
0x18002dc3a  jnz     short loc_18002DC32
0x18002dc3c  jmp     short loc_18002DC86
0x18002dc3e  mov     rax, [r14+30h]
0x18002dc42  mov     rcx, [rax+28h]
0x18002dc46  mov     eax, 5Bh ; '['
0x18002dc4b  mov     rbx, [rcx+50h]
0x18002dc4f  cmp     [rbx], ax
0x18002dc52  jnz     short loc_18002DC5D
0x18002dc54  add     rbx, 2
0x18002dc58  lea     edx, [rax+2]
0x18002dc5b  jmp     short loc_18002DC62
0x18002dc5d  mov     edx, 3Ah ; ':'; Ch
0x18002dc62  mov     rcx, rbx; Str
0x18002dc65  call    cs:__imp_wcschr
0x18002dc6c  nop     dword ptr [rax+rax+00h]
0x18002dc71  test    rax, rax
0x18002dc74  jnz     short loc_18002DC80
0x18002dc76  mov     ebx, 80004005h
0x18002dc7b  jmp     loc_18002DD0C
0x18002dc80  sub     rax, rbx
0x18002dc83  sar     rax, 1
0x18002dc86  mov     r8d, eax
0x18002dc89  lea     rcx, [rsp+0A8h+var_80]
0x18002dc8e  mov     rdx, rbx
0x18002dc91  call    cs:__imp_?CopyW@STRA@@QEAAJPEBGK@Z; STRA::CopyW(ushort const *,ulong)
0x18002dc98  nop     dword ptr [rax+rax+00h]
0x18002dc9d  mov     ebx, eax
0x18002dc9f  test    eax, eax
0x18002dca1  js      short loc_18002DD0C
0x18002dca3  lea     rcx, [rsp+0A8h+var_80]
0x18002dca8  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002dcaf  nop     dword ptr [rax+rax+00h]
0x18002dcb4  lea     rcx, [rsp+0A8h+var_80]
0x18002dcb9  mov     rdi, rax
0x18002dcbc  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18002dcc3  nop     dword ptr [rax+rax+00h]
0x18002dcc8  mov     esi, eax
0x18002dcca  mov     r8, [r14]
0x18002dccd  lea     edx, [rsi+1]
0x18002dcd0  mov     rcx, r14
0x18002dcd3  mov     rax, [r8+90h]
0x18002dcda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dcdf  mov     rbp, rax
0x18002dce2  test    rax, rax
0x18002dce5  jnz     short loc_18002DCEE
0x18002dce7  mov     ebx, 80070008h
0x18002dcec  jmp     short loc_18002DD0C
0x18002dcee  mov     r8d, esi; Size
0x18002dcf1  mov     rdx, rdi; Src
0x18002dcf4  mov     rcx, rbp; void *
0x18002dcf7  mov     ebx, esi
0x18002dcf9  call    memcpy_0
0x18002dcfe  mov     [rbx+rbp], r13b
0x18002dd02  mov     [r15], rbp
0x18002dd05  mov     [r12], esi
0x18002dd09  mov     ebx, r13d
0x18002dd0c  lea     rcx, [rsp+0A8h+var_80]
0x18002dd11  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002dd18  nop     dword ptr [rax+rax+00h]
0x18002dd1d  mov     eax, ebx
0x18002dd1f  mov     rcx, [rsp+0A8h+var_48]
0x18002dd24  xor     rcx, rsp; StackCookie
0x18002dd27  call    __security_check_cookie
0x18002dd2c  mov     rbx, [rsp+0A8h+arg_18]
0x18002dd34  add     rsp, 70h
0x18002dd38  pop     r15
0x18002dd3a  pop     r14
0x18002dd3c  pop     r13
0x18002dd3e  pop     r12
0x18002dd40  pop     rdi
0x18002dd41  pop     rsi
0x18002dd42  pop     rbp
0x18002dd43  retn
```
