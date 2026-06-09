# SCHEMA_ATTRIBUTE::GetStringFlagsValue(ushort const *,ulong *)

- ea: `0x1800192e0`
- end: `0x18001951b`
- name: `?GetStringFlagsValue@SCHEMA_ATTRIBUTE@@AEAAJPEBGPEAK@Z`
- size: `571`
- prototype: `int(SCHEMA_ATTRIBUTE *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800124bc`

## callees

- `0x1800192e0`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `msvcrt!wcschr` at `0x180019384`
- `msvcrt!wcschr` at `0x180019384`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800194ec`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800194ec`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800193d8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800193f8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180019418`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180019461`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800193d8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800193f8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180019418`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180019461`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180019333`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180019333`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800193e5`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180019405`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180019425`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180019438`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001944f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800193e5`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180019405`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180019425`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180019438`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001944f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800193bb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800193bb`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800193a2`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800193a2`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180019445`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180019445`

## pseudocode

```c
__int64 __fastcall SCHEMA_ATTRIBUTE::GetStringFlagsValue(
        SCHEMA_ATTRIBUTE *this,
        const unsigned __int16 *a2,
        unsigned int *a3)
{
  unsigned int v6; // esi
  unsigned __int64 v7; // rax
  __int64 v8; // rcx
  wchar_t *v9; // rax
  wchar_t *v10; // rdi
  int v11; // ebx
  const unsigned __int16 *v12; // rdi
  unsigned __int16 *Str; // rbx
  unsigned __int16 *v14; // rbx
  unsigned __int16 *v15; // rbx
  unsigned int CCH; // eax
  unsigned __int16 *v17; // rbx
  __int64 v18; // rcx
  _QWORD *v19; // r8
  _QWORD *v20; // rcx
  const WCHAR *v21; // rax
  _QWORD *v22; // rdx
  signed __int64 v23; // r11
  int v24; // r9d
  int v25; // r10d
  _BYTE v27[64]; // [rsp+20h] [rbp-69h] BYREF
  unsigned __int16 v28[32]; // [rsp+60h] [rbp-29h] BYREF

  memset_0(v28, 0, sizeof(v28));
  STRU::STRU((STRU *)v27, v28, 0x20u);
  if ( a2 && a3 )
  {
    v6 = 0;
    while ( 1 )
    {
      v7 = *a2;
      if ( !(_WORD)v7 )
        break;
      while ( (unsigned __int16)v7 <= 0x20u )
      {
        v8 = 0x100002200LL;
        if ( !_bittest64(&v8, v7) )
          break;
        v7 = *++a2;
      }
      v9 = wcschr(a2, 0x2Cu);
      v10 = v9;
      if ( v9 )
      {
        v11 = STRU::Copy((STRU *)v27, a2, v9 - a2);
        if ( v11 < 0 )
          goto LABEL_33;
        v12 = v10 + 1;
      }
      else
      {
        v11 = STRU::Copy((STRU *)v27, a2);
        if ( v11 < 0 )
          goto LABEL_33;
        v12 = &szDomain;
      }
      while ( STRU::QueryCCH((STRU *)v27) )
      {
        Str = STRU::QueryStr((STRU *)v27);
        if ( Str[STRU::QueryCCH((STRU *)v27) - 1] != 32 )
        {
          v14 = STRU::QueryStr((STRU *)v27);
          if ( v14[STRU::QueryCCH((STRU *)v27) - 1] != 9 )
          {
            v15 = STRU::QueryStr((STRU *)v27);
            if ( v15[STRU::QueryCCH((STRU *)v27) - 1] != 13 )
              break;
          }
        }
        CCH = STRU::QueryCCH((STRU *)v27);
        STRU::SetLen((STRU *)v27, CCH - 1);
      }
      v17 = STRU::QueryStr((STRU *)v27);
      if ( !v17 )
        goto LABEL_32;
      v18 = *((_QWORD *)this + 7);
      if ( !v18 )
        goto LABEL_30;
      v19 = (_QWORD *)(v18 + 16);
      v20 = *(_QWORD **)(v18 + 16);
      if ( v20 == v19 )
        goto LABEL_30;
      do
      {
        v21 = &szDomain;
        v22 = v20;
        if ( v20[2] )
          v21 = (const WCHAR *)v20[2];
        v23 = (char *)v17 - (char *)v21;
        do
        {
          v24 = *(const WCHAR *)((char *)v21 + v23);
          v25 = *v21 - v24;
          if ( v25 )
            break;
          ++v21;
        }
        while ( v24 );
        if ( !v25 )
          break;
        v20 = (_QWORD *)*v20;
        v22 = 0;
      }
      while ( v20 != v19 );
      if ( !v22 )
      {
LABEL_30:
        v11 = -2147023483;
        goto LABEL_33;
      }
      v6 |= *((_DWORD *)v22 + 6);
      a2 = v12;
    }
    *a3 = v6;
    v11 = 0;
  }
  else
  {
LABEL_32:
    v11 = -2147024809;
  }
LABEL_33:
  STRU::~STRU((STRU *)v27);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800192e0  mov     [rsp-8+arg_0], rbx
0x1800192e5  push    rbp
0x1800192e6  push    rsi
0x1800192e7  push    rdi
0x1800192e8  push    r12
0x1800192ea  push    r13
0x1800192ec  push    r14
0x1800192ee  push    r15
0x1800192f0  lea     rbp, [rsp-27h]
0x1800192f5  sub     rsp, 0B0h
0x1800192fc  mov     rax, cs:__security_cookie
0x180019303  xor     rax, rsp
0x180019306  mov     [rbp+57h+var_40], rax
0x18001930a  mov     rbx, rdx
0x18001930d  mov     r14, r8
0x180019310  xor     edx, edx; Val
0x180019312  mov     r15, rcx
0x180019315  lea     rcx, [rbp+57h+var_80]; void *
0x180019319  lea     r8d, [rdx+40h]; Size
0x18001931d  call    memset_0
0x180019322  mov     r13d, 20h ; ' '
0x180019328  lea     rdx, [rbp+57h+var_80]
0x18001932c  mov     r8d, r13d
0x18001932f  lea     rcx, [rbp+57h+var_C0]
0x180019333  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180019339  xor     r12d, r12d
0x18001933c  test    rbx, rbx
0x18001933f  jz      loc_1800194E3
0x180019345  test    r14, r14
0x180019348  jz      loc_1800194E3
0x18001934e  mov     esi, r12d
0x180019351  movzx   eax, word ptr [rbx]
0x180019354  test    ax, ax
0x180019357  jz      loc_1800194DB
0x18001935d  cmp     ax, r13w
0x180019361  ja      short loc_18001937C
0x180019363  mov     rcx, 100002200h
0x18001936d  bt      rcx, rax
0x180019371  jnb     short loc_18001937C
0x180019373  add     rbx, 2
0x180019377  movzx   eax, word ptr [rbx]
0x18001937a  jmp     short loc_18001935D
0x18001937c  mov     edx, 2Ch ; ','; Ch
0x180019381  mov     rcx, rbx; Str
0x180019384  call    cs:__imp_wcschr
0x18001938a  mov     rdx, rbx
0x18001938d  lea     rcx, [rbp+57h+var_C0]
0x180019391  mov     rdi, rax
0x180019394  test    rax, rax
0x180019397  jz      short loc_1800193BB
0x180019399  mov     r8, rax
0x18001939c  sub     r8, rbx
0x18001939f  sar     r8, 1
0x1800193a2  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800193a8  mov     ebx, eax
0x1800193aa  test    eax, eax
0x1800193ac  js      loc_1800194E8
0x1800193b2  add     rdi, 2
0x1800193b6  jmp     loc_18001944B
0x1800193bb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800193c1  mov     ebx, eax
0x1800193c3  test    eax, eax
0x1800193c5  js      loc_1800194E8
0x1800193cb  lea     rdi, szDomain
0x1800193d2  jmp     short loc_18001944B
0x1800193d4  lea     rcx, [rbp+57h+var_C0]
0x1800193d8  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800193de  lea     rcx, [rbp+57h+var_C0]
0x1800193e2  mov     rbx, rax
0x1800193e5  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800193eb  dec     eax
0x1800193ed  cmp     [rbx+rax*2], r13w
0x1800193f2  jz      short loc_180019434
0x1800193f4  lea     rcx, [rbp+57h+var_C0]
0x1800193f8  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800193fe  lea     rcx, [rbp+57h+var_C0]
0x180019402  mov     rbx, rax
0x180019405  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18001940b  dec     eax
0x18001940d  cmp     word ptr [rbx+rax*2], 9
0x180019412  jz      short loc_180019434
0x180019414  lea     rcx, [rbp+57h+var_C0]
0x180019418  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001941e  lea     rcx, [rbp+57h+var_C0]
0x180019422  mov     rbx, rax
0x180019425  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18001942b  dec     eax
0x18001942d  cmp     word ptr [rbx+rax*2], 0Dh
0x180019432  jnz     short loc_18001945D
0x180019434  lea     rcx, [rbp+57h+var_C0]
0x180019438  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18001943e  lea     rcx, [rbp+57h+var_C0]
0x180019442  lea     edx, [rax-1]
0x180019445  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18001944b  lea     rcx, [rbp+57h+var_C0]
0x18001944f  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180019455  test    eax, eax
0x180019457  jnz     loc_1800193D4
0x18001945d  lea     rcx, [rbp+57h+var_C0]
0x180019461  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180019467  mov     rbx, rax
0x18001946a  test    rax, rax
0x18001946d  jz      short loc_1800194E3
0x18001946f  mov     rcx, [r15+38h]
0x180019473  test    rcx, rcx
0x180019476  jz      short loc_1800194D4
0x180019478  lea     r8, [rcx+10h]
0x18001947c  mov     rcx, [r8]
0x18001947f  cmp     rcx, r8
0x180019482  jz      short loc_1800194D4
0x180019484  cmp     [rcx+10h], r12
0x180019488  lea     rax, szDomain
0x18001948f  mov     r11, rbx
0x180019492  mov     rdx, rcx
0x180019495  cmovnz  rax, [rcx+10h]
0x18001949a  sub     r11, rax
0x18001949d  movzx   r10d, word ptr [rax]
0x1800194a1  movzx   r9d, word ptr [rax+r11]
0x1800194a6  sub     r10d, r9d
0x1800194a9  jnz     short loc_1800194B4
0x1800194ab  add     rax, 2
0x1800194af  test    r9d, r9d
0x1800194b2  jnz     short loc_18001949D
0x1800194b4  test    r10d, r10d
0x1800194b7  jz      short loc_1800194C4
0x1800194b9  mov     rcx, [rcx]
0x1800194bc  mov     rdx, r12
0x1800194bf  cmp     rcx, r8
0x1800194c2  jnz     short loc_180019484
0x1800194c4  test    rdx, rdx
0x1800194c7  jz      short loc_1800194D4
0x1800194c9  or      esi, [rdx+18h]
0x1800194cc  mov     rbx, rdi
0x1800194cf  jmp     loc_180019351
0x1800194d4  mov     ebx, 80070585h
0x1800194d9  jmp     short loc_1800194E8
0x1800194db  mov     [r14], esi
0x1800194de  mov     ebx, r12d
0x1800194e1  jmp     short loc_1800194E8
0x1800194e3  mov     ebx, 80070057h
0x1800194e8  lea     rcx, [rbp+57h+var_C0]
0x1800194ec  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800194f2  mov     eax, ebx
0x1800194f4  mov     rcx, [rbp+57h+var_40]
0x1800194f8  xor     rcx, rsp; StackCookie
0x1800194fb  call    __security_check_cookie
0x180019500  mov     rbx, [rsp+0E0h+arg_0]
0x180019508  add     rsp, 0B0h
0x18001950f  pop     r15
0x180019511  pop     r14
0x180019513  pop     r13
0x180019515  pop     r12
0x180019517  pop     rdi
0x180019518  pop     rsi
0x180019519  pop     rbp
0x18001951a  retn
```
