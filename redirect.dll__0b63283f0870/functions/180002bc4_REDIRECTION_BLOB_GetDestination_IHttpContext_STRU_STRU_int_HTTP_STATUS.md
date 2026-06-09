# REDIRECTION_BLOB::GetDestination(IHttpContext *,STRU &,STRU *,int *,HTTP_STATUS *)

- ea: `0x180002bc4`
- end: `0x180003043`
- name: `?GetDestination@REDIRECTION_BLOB@@QEAAJPEAVIHttpContext@@AEAVSTRU@@PEAV3@PEAHPEAUHTTP_STATUS@@@Z`
- size: `1151`
- prototype: `__int64 __fastcall(REDIRECTION_BLOB *this, struct IHttpContext *, struct STRU *, struct STRU *, int *, struct HTTP_STATUS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180002758`

## callees

- `0x1800029d8`
- `0x180002bc4`
- `0x1800035c6`
- `0x1800035f0`
- `0x180004010`

## import_xrefs

- `msvcrt!wcschr` at `0x180002d5e`
- `msvcrt!wcschr` at `0x180002d70`
- `msvcrt!wcschr` at `0x180002d5e`
- `msvcrt!wcschr` at `0x180002d70`
- `msvcrt!iswdigit` at `0x180002ea6`
- `msvcrt!iswdigit` at `0x180002ea6`
- `msvcrt!free` at `0x180002db5`
- `msvcrt!free` at `0x180002f51`
- `msvcrt!free` at `0x180003000`
- `msvcrt!free` at `0x180002db5`
- `msvcrt!free` at `0x180002f51`
- `msvcrt!free` at `0x180003000`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180002cc4`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180002cc4`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002f3c`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002f84`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002f3c`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002f84`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002ef6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002f08`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002ef6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002f08`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180002f9b`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180002faa`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180002feb`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180002f9b`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180002faa`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180002feb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002d3d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002d3d`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180002e04`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180002e04`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002c38`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002c60`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002c38`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002c60`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000300d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003018`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000300d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003018`

## string_xrefs

- `0x180002d19`: `Moved Permanently`
- `0x180002d07`: `Moved Temporarily`

## pseudocode

```c
__int64 __fastcall REDIRECTION_BLOB::GetDestination(
        REDIRECTION_BLOB *this,
        struct IHttpContext *a2,
        struct STRU *a3,
        struct STRU *a4,
        int *a5,
        struct HTTP_STATUS *a6)
{
  int *v6; // r12
  struct STRU *v7; // rdi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // ecx
  void *v15; // rbx
  __int64 v16; // rdx
  int WildcardMatch; // edi
  const char *v18; // rax
  wchar_t *v19; // rax
  void *v20; // rcx
  void *v21; // rcx
  const struct STRU *v22; // rdi
  struct WILDCARD_ENTRY **v23; // rdi
  __int16 v24; // ax
  struct WILDCARD_ENTRY **v25; // r15
  int v26; // r12d
  struct WILDCARD_ENTRY **v27; // rdx
  _WORD *v28; // rax
  unsigned int v29; // r8d
  const unsigned __int16 *v30; // rdx
  unsigned int v31; // r8d
  __int64 v32; // rax
  int v33; // eax
  int v34; // r15d
  const struct STRU *v35; // rdx
  int v36; // eax
  unsigned int v38; // [rsp+20h] [rbp-E0h]
  struct WILDCARD_ENTRY *v39; // [rsp+28h] [rbp-D8h] BYREF
  struct STRU *v40; // [rsp+30h] [rbp-D0h]
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v42; // [rsp+40h] [rbp-C0h]
  int v43; // [rsp+48h] [rbp-B8h]
  struct WILDCARD_ENTRY **v44; // [rsp+50h] [rbp-B0h]
  int *v45; // [rsp+58h] [rbp-A8h]
  _BYTE v46[32]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *Str; // [rsp+80h] [rbp-80h]
  _BYTE v48[48]; // [rsp+98h] [rbp-68h] BYREF
  int v49; // [rsp+C8h] [rbp-38h]
  unsigned __int16 v50[264]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v51[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v6 = a5;
  v7 = a3;
  v40 = a3;
  v45 = a5;
  memset_0(v50, 0, 0x208u);
  STRU::STRU((STRU *)v46, v50, 0x104u);
  memset_0(v51, 0, 0x208u);
  STRU::STRU((STRU *)v48, v51, 0x104u);
  v11 = *(_QWORD *)a2;
  v39 = 0;
  v12 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v11 + 24))(a2);
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  v14 = *((_DWORD *)v7 + 12);
  v15 = 0;
  Block = 0;
  v42 = 0;
  v16 = *(_QWORD *)(v13 + 96);
  v38 = 0;
  v43 = v14;
  if ( v16 )
  {
    WildcardMatch = STRU::Copy(
                      (STRU *)v48,
                      (const unsigned __int16 *)(v16 + 2),
                      (*(unsigned __int16 *)(v13 + 70) >> 1) - 1);
    if ( WildcardMatch < 0 )
      goto LABEL_77;
    v7 = v40;
  }
  *(_WORD *)a6 = *((_WORD *)this + 4);
  switch ( *((_WORD *)this + 4) )
  {
    case 0x12D:
      v18 = "Moved Permanently";
      goto LABEL_12;
    case 0x12E:
      goto LABEL_10;
    case 0x133:
      v18 = "Moved Temporarily";
      goto LABEL_12;
  }
  if ( *((_WORD *)this + 4) != 308 )
  {
LABEL_10:
    v18 = "Redirect";
    goto LABEL_12;
  }
  v18 = "Redirected Permanently";
LABEL_12:
  *((_QWORD *)a6 + 1) = v18;
  *((_WORD *)a6 + 8) = 0;
  WildcardMatch = STRU::Copy(
                    (STRU *)v46,
                    (const unsigned __int16 *)(*((_QWORD *)v7 + 4) + 2LL * *((unsigned int *)this + 34)));
  if ( WildcardMatch < 0 )
    goto LABEL_77;
  if ( *((_DWORD *)this + 6) )
  {
    v19 = wcschr(Str, 0x2Fu);
    if ( v19 == Str )
      v19 = wcschr(v19 + 1, 0x2Fu);
    if ( v19 )
    {
      *a5 = 0;
LABEL_76:
      WildcardMatch = 0;
      goto LABEL_77;
    }
  }
  if ( *((_DWORD *)this + 7) )
  {
    WildcardMatch = REDIRECTION_BLOB::FindWildcardMatch(
                      this,
                      (struct STRU *)v46,
                      &v39,
                      (struct WILDCARD_MATCH_LIST *)&Block);
    if ( WildcardMatch < 0 )
    {
      v20 = Block;
      if ( !Block )
        goto LABEL_77;
LABEL_21:
      free(v20);
      goto LABEL_77;
    }
    if ( !v39 )
    {
      v21 = Block;
      *a5 = 0;
      if ( !v21 )
        goto LABEL_76;
LABEL_75:
      free(v21);
      goto LABEL_76;
    }
    v22 = (struct WILDCARD_ENTRY *)((char *)v39 + 56);
    v15 = Block;
    v38 = HIDWORD(v42);
  }
  else
  {
    v22 = (REDIRECTION_BLOB *)((char *)this + 32);
  }
  if ( !*((_DWORD *)this + 4) )
  {
    WildcardMatch = STRU::Copy(a4, v22);
    if ( WildcardMatch < 0 )
      goto LABEL_29;
    goto LABEL_71;
  }
  v23 = (struct WILDCARD_ENTRY **)*((_QWORD *)v22 + 4);
  LODWORD(v39) = 0;
  v24 = *(_WORD *)v23;
  if ( !*(_WORD *)v23 )
  {
LABEL_71:
    *v6 = 1;
    if ( *((_DWORD *)this + 5) )
    {
      if ( !v15 )
        goto LABEL_76;
      v21 = v15;
      goto LABEL_75;
    }
    WildcardMatch = STRU::Append(a4, (const struct STRU *)v46);
LABEL_29:
    if ( !v15 )
      goto LABEL_77;
    v20 = v15;
    goto LABEL_21;
  }
  while ( 1 )
  {
    v25 = (struct WILDCARD_ENTRY **)((char *)v23 + 2);
    v26 = *((unsigned __int16 *)v23 + 1);
    if ( v24 != 36 )
      break;
    switch ( v26 )
    {
      case 'P':
        v35 = (const struct STRU *)v48;
LABEL_66:
        v36 = STRU::Append(a4, v35);
LABEL_67:
        WildcardMatch = v36;
        if ( v36 < 0 )
          goto LABEL_29;
LABEL_68:
        v23 = v25;
        goto LABEL_69;
      case 'Q':
        if ( v49 )
        {
          WildcardMatch = STRU::Append(a4, L"?", 1u);
          if ( WildcardMatch < 0 )
            goto LABEL_29;
          v36 = STRU::Append(a4, (const struct STRU *)v48);
          goto LABEL_67;
        }
        goto LABEL_68;
      case 'S':
        v35 = (const struct STRU *)v46;
        goto LABEL_66;
      case 'V':
        v35 = v40;
        goto LABEL_66;
    }
    v44 = v23;
    v23 = (struct WILDCARD_ENTRY **)((char *)v23 + 2);
    if ( iswdigit(v26) )
    {
      v30 = (const unsigned __int16 *)v15;
      if ( v15 && v26 - 48 < v38 )
      {
        v31 = 0;
        if ( v26 != 48 )
        {
          do
          {
            v32 = -1;
            do
              ++v32;
            while ( v30[v32] );
            ++v31;
            v30 += v32 + 1;
          }
          while ( v31 < v26 - 48 );
        }
      }
      else
      {
        v30 = 0;
      }
      v33 = STRU::Append(a4, v30);
      goto LABEL_56;
    }
    v34 = STRU::Append(a4, L"$");
    if ( v34 < 0 )
      goto LABEL_57;
    if ( (_WORD)v26 )
    {
      LOWORD(v39) = v26;
      v27 = &v39;
      v29 = 1;
      goto LABEL_55;
    }
    v23 = v44;
LABEL_69:
    v23 = (struct WILDCARD_ENTRY **)((char *)v23 + 2);
    v24 = *(_WORD *)v23;
    if ( !*(_WORD *)v23 )
    {
      v6 = v45;
      goto LABEL_71;
    }
  }
  v27 = v23;
  if ( v26 != 36 )
  {
    do
    {
      v28 = (_WORD *)v23 + 1;
      if ( !*((_WORD *)v23 + 1) )
        break;
      v23 = (struct WILDCARD_ENTRY **)((char *)v23 + 2);
    }
    while ( v28[1] != 36 );
  }
  v29 = (((char *)v23 - (char *)v27) >> 1) + 1;
LABEL_55:
  v33 = STRU::Append(a4, (const unsigned __int16 *)v27, v29);
LABEL_56:
  v34 = v33;
  if ( v33 >= 0 )
    goto LABEL_69;
LABEL_57:
  if ( v15 )
    free(v15);
  WildcardMatch = v34;
LABEL_77:
  STRU::~STRU((STRU *)v48);
  STRU::~STRU((STRU *)v46);
  return (unsigned int)WildcardMatch;
}

```

## disassembly

```asm
0x180002bc4  push    rbp
0x180002bc6  push    rbx
0x180002bc7  push    rsi
0x180002bc8  push    rdi
0x180002bc9  push    r12
0x180002bcb  push    r13
0x180002bcd  push    r14
0x180002bcf  push    r15
0x180002bd1  lea     rbp, [rsp-408h]
0x180002bd9  sub     rsp, 508h
0x180002be0  mov     rax, cs:__security_cookie
0x180002be7  xor     rax, rsp
0x180002bea  mov     [rbp+440h+var_50], rax
0x180002bf1  mov     r12, [rbp+440h+arg_20]
0x180002bf8  mov     rdi, r8
0x180002bfb  mov     r15, [rbp+440h+arg_28]
0x180002c02  mov     rbx, rdx
0x180002c05  mov     [rsp+540h+var_510], r8
0x180002c0a  mov     r14, rcx
0x180002c0d  xor     edx, edx; Val
0x180002c0f  mov     [rsp+540h+var_4E8], r12
0x180002c14  mov     r8d, 208h; Size
0x180002c1a  lea     rcx, [rbp+440h+var_470]; void *
0x180002c1e  mov     rsi, r9
0x180002c21  call    memset_0
0x180002c26  mov     r13d, 104h
0x180002c2c  lea     rdx, [rbp+440h+var_470]
0x180002c30  mov     r8d, r13d
0x180002c33  lea     rcx, [rsp+540h+var_4E0]
0x180002c38  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002c3e  xor     edx, edx; Val
0x180002c40  lea     rcx, [rbp+440h+var_260]; void *
0x180002c47  mov     r8d, 208h; Size
0x180002c4d  call    memset_0
0x180002c52  mov     r8d, r13d
0x180002c55  lea     rdx, [rbp+440h+var_260]
0x180002c5c  lea     rcx, [rbp+440h+var_4A8]
0x180002c60  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002c66  mov     rax, [rbx]
0x180002c69  xor     r13d, r13d
0x180002c6c  mov     rcx, rbx
0x180002c6f  mov     [rsp+540h+var_518], r13
0x180002c74  mov     rax, [rax+18h]
0x180002c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c7d  mov     rdx, rax
0x180002c80  mov     rcx, [rax]
0x180002c83  mov     rax, [rcx+8]
0x180002c87  mov     rcx, rdx
0x180002c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c8f  mov     ecx, [rdi+30h]
0x180002c92  mov     ebx, r13d
0x180002c95  mov     [rsp+540h+Block], rbx
0x180002c9a  mov     [rsp+540h+var_500], r13
0x180002c9f  mov     rdx, [rax+60h]
0x180002ca3  mov     [rsp+540h+var_520], r13d
0x180002ca8  mov     [rsp+540h+var_4F8], ecx
0x180002cac  test    rdx, rdx
0x180002caf  jz      short loc_180002CD9
0x180002cb1  movzx   r8d, word ptr [rax+46h]
0x180002cb6  lea     rcx, [rbp+440h+var_4A8]
0x180002cba  shr     r8d, 1
0x180002cbd  add     rdx, 2
0x180002cc1  dec     r8d
0x180002cc4  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180002cca  mov     edi, eax
0x180002ccc  test    eax, eax
0x180002cce  js      loc_180003009
0x180002cd4  mov     rdi, [rsp+540h+var_510]
0x180002cd9  movzx   eax, word ptr [r14+8]
0x180002cde  mov     [r15], ax
0x180002ce2  movzx   ecx, word ptr [r14+8]
0x180002ce7  sub     ecx, 12Dh
0x180002ced  jz      short loc_180002D19
0x180002cef  sub     ecx, 1
0x180002cf2  jz      short loc_180002D10
0x180002cf4  sub     ecx, 5
0x180002cf7  jz      short loc_180002D07
0x180002cf9  cmp     ecx, 1
0x180002cfc  jnz     short loc_180002D10
0x180002cfe  lea     rax, aRedirectedPerm; "Redirected Permanently"
0x180002d05  jmp     short loc_180002D20
0x180002d07  lea     rax, aMovedTemporari; "Moved Temporarily"
0x180002d0e  jmp     short loc_180002D20
0x180002d10  lea     rax, aRedirect; "Redirect"
0x180002d17  jmp     short loc_180002D20
0x180002d19  lea     rax, aMovedPermanent; "Moved Permanently"
0x180002d20  mov     [r15+8], rax
0x180002d24  mov     [r15+10h], r13w
0x180002d29  mov     ecx, [r14+88h]
0x180002d30  mov     rax, [rdi+20h]
0x180002d34  lea     rdx, [rax+rcx*2]
0x180002d38  lea     rcx, [rsp+540h+var_4E0]
0x180002d3d  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002d43  mov     edi, eax
0x180002d45  test    eax, eax
0x180002d47  js      loc_180003009
0x180002d4d  cmp     [r14+18h], r13d
0x180002d51  jz      short loc_180002D84
0x180002d53  mov     rcx, [rbp+440h+Str]; Str
0x180002d57  mov     edi, 2Fh ; '/'
0x180002d5c  mov     edx, edi; Ch
0x180002d5e  call    cs:__imp_wcschr
0x180002d64  cmp     rax, [rbp+440h+Str]
0x180002d68  jnz     short loc_180002D76
0x180002d6a  mov     edx, edi; Ch
0x180002d6c  lea     rcx, [rax+2]; Str
0x180002d70  call    cs:__imp_wcschr
0x180002d76  test    rax, rax
0x180002d79  jz      short loc_180002D84
0x180002d7b  mov     [r12], r13d
0x180002d7f  jmp     loc_180003006
0x180002d84  cmp     [r14+1Ch], r13d
0x180002d88  jz      short loc_180002DF4
0x180002d8a  lea     r9, [rsp+540h+Block]; struct WILDCARD_MATCH_LIST *
0x180002d8f  mov     rcx, r14; this
0x180002d92  lea     r8, [rsp+540h+var_518]; struct WILDCARD_ENTRY **
0x180002d97  lea     rdx, [rsp+540h+var_4E0]; struct STRU *
0x180002d9c  call    ?FindWildcardMatch@REDIRECTION_BLOB@@QEAAJAEAVSTRU@@PEAPEAUWILDCARD_ENTRY@@PEAVWILDCARD_MATCH_LIST@@@Z; REDIRECTION_BLOB::FindWildcardMatch(STRU &,WILDCARD_ENTRY * *,WILDCARD_MATCH_LIST *)
0x180002da1  mov     edi, eax
0x180002da3  test    eax, eax
0x180002da5  jns     short loc_180002DC0
0x180002da7  mov     rcx, [rsp+540h+Block]; Block
0x180002dac  test    rcx, rcx
0x180002daf  jz      loc_180003009
0x180002db5  call    cs:__imp_free
0x180002dbb  jmp     loc_180003009
0x180002dc0  mov     rdi, [rsp+540h+var_518]
0x180002dc5  test    rdi, rdi
0x180002dc8  jnz     short loc_180002DE1
0x180002dca  mov     rcx, [rsp+540h+Block]
0x180002dcf  mov     [r12], r13d
0x180002dd3  test    rcx, rcx
0x180002dd6  jz      loc_180003006
0x180002ddc  jmp     loc_180003000
0x180002de1  mov     eax, dword ptr [rsp+540h+var_500+4]
0x180002de5  add     rdi, 38h ; '8'
0x180002de9  mov     rbx, [rsp+540h+Block]
0x180002dee  mov     [rsp+540h+var_520], eax
0x180002df2  jmp     short loc_180002DF8
0x180002df4  lea     rdi, [r14+20h]
0x180002df8  cmp     [r14+10h], r13d
0x180002dfc  jnz     short loc_180002E22
0x180002dfe  mov     rdx, rdi
0x180002e01  mov     rcx, rsi
0x180002e04  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180002e0a  mov     edi, eax
0x180002e0c  test    eax, eax
0x180002e0e  jns     loc_180002FD5
0x180002e14  test    rbx, rbx
0x180002e17  jz      loc_180003009
0x180002e1d  mov     rcx, rbx
0x180002e20  jmp     short loc_180002DB5
0x180002e22  mov     rdi, [rdi+20h]
0x180002e26  mov     dword ptr [rsp+540h+var_518], r13d
0x180002e2b  movzx   eax, word ptr [rdi]
0x180002e2e  test    ax, ax
0x180002e31  jz      loc_180002FD5
0x180002e37  lea     r15, [rdi+2]
0x180002e3b  movzx   r12d, word ptr [r15]
0x180002e3f  cmp     ax, 24h ; '$'
0x180002e43  jz      short loc_180002E73
0x180002e45  mov     rdx, rdi
0x180002e48  cmp     r12d, 24h ; '$'
0x180002e4c  jz      short loc_180002E62
0x180002e4e  lea     rax, [rdi+2]
0x180002e52  cmp     [rax], r13w
0x180002e56  jz      short loc_180002E62
0x180002e58  cmp     word ptr [rax+2], 24h ; '$'
0x180002e5d  mov     rdi, rax
0x180002e60  jnz     short loc_180002E4E
0x180002e62  mov     r8, rdi
0x180002e65  sub     r8, rdx
0x180002e68  sar     r8, 1
0x180002e6b  inc     r8d
0x180002e6e  jmp     loc_180002F39
0x180002e73  mov     ecx, r12d
0x180002e76  sub     ecx, 50h ; 'P'
0x180002e79  jz      loc_180002FA3
0x180002e7f  sub     ecx, 1
0x180002e82  jz      loc_180002F6D
0x180002e88  sub     ecx, 2
0x180002e8b  jz      loc_180002F66
0x180002e91  cmp     ecx, 3
0x180002e94  jz      loc_180002F5F
0x180002e9a  mov     [rsp+540h+var_4F0], rdi
0x180002e9f  movzx   ecx, r12w; C
0x180002ea3  mov     rdi, r15
0x180002ea6  call    cs:__imp_iswdigit
0x180002eac  test    eax, eax
0x180002eae  jz      short loc_180002EFE
0x180002eb0  mov     rdx, rbx
0x180002eb3  test    rbx, rbx
0x180002eb6  jz      short loc_180002EED
0x180002eb8  lea     ecx, [r12-30h]
0x180002ebd  cmp     ecx, [rsp+540h+var_520]
0x180002ec1  jnb     short loc_180002EED
0x180002ec3  xor     r13d, r13d
0x180002ec6  mov     r8d, r13d
0x180002ec9  test    ecx, ecx
0x180002ecb  jz      short loc_180002EF3
0x180002ecd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002ed1  inc     rax
0x180002ed4  cmp     [rdx+rax*2], r13w
0x180002ed9  jnz     short loc_180002ED1
0x180002edb  lea     rdx, [rdx+rax*2]
0x180002edf  inc     r8d
0x180002ee2  add     rdx, 2
0x180002ee6  cmp     r8d, ecx
0x180002ee9  jb      short loc_180002ECD
0x180002eeb  jmp     short loc_180002EF3
0x180002eed  xor     r13d, r13d
0x180002ef0  mov     edx, r13d
0x180002ef3  mov     rcx, rsi
0x180002ef6  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002efc  jmp     short loc_180002F42
0x180002efe  lea     rdx, asc_180005C78; "$"
0x180002f05  mov     rcx, rsi
0x180002f08  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002f0e  xor     r13d, r13d
0x180002f11  mov     r15d, eax
0x180002f14  test    eax, eax
0x180002f16  js      short loc_180002F49
0x180002f18  test    r12w, r12w
0x180002f1c  jnz     short loc_180002F28
0x180002f1e  mov     rdi, [rsp+540h+var_4F0]
0x180002f23  jmp     loc_180002FC0
0x180002f28  mov     word ptr [rsp+540h+var_518], r12w
0x180002f2e  lea     rdx, [rsp+540h+var_518]
0x180002f33  mov     r8d, 1
0x180002f39  mov     rcx, rsi
0x180002f3c  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180002f42  mov     r15d, eax
0x180002f45  test    eax, eax
0x180002f47  jns     short loc_180002FC0
0x180002f49  test    rbx, rbx
0x180002f4c  jz      short loc_180002F57
0x180002f4e  mov     rcx, rbx; Block
0x180002f51  call    cs:__imp_free
0x180002f57  mov     edi, r15d
0x180002f5a  jmp     loc_180003009
0x180002f5f  mov     rdx, [rsp+540h+var_510]
0x180002f64  jmp     short loc_180002FA7
0x180002f66  lea     rdx, [rsp+540h+var_4E0]
0x180002f6b  jmp     short loc_180002FA7
0x180002f6d  xor     r13d, r13d
0x180002f70  cmp     [rbp+440h+var_478], r13d
0x180002f74  jz      short loc_180002FBD
0x180002f76  lea     r8d, [r13+1]
0x180002f7a  mov     rcx, rsi
0x180002f7d  lea     rdx, asc_180005C74; "?"
0x180002f84  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180002f8a  mov     edi, eax
0x180002f8c  test    eax, eax
0x180002f8e  js      loc_180002E14
0x180002f94  lea     rdx, [rbp+440h+var_4A8]
0x180002f98  mov     rcx, rsi
0x180002f9b  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x180002fa1  jmp     short loc_180002FB3
0x180002fa3  lea     rdx, [rbp+440h+var_4A8]
0x180002fa7  mov     rcx, rsi
0x180002faa  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x180002fb0  xor     r13d, r13d
0x180002fb3  mov     edi, eax
0x180002fb5  test    eax, eax
0x180002fb7  js      loc_180002E14
0x180002fbd  mov     rdi, r15
0x180002fc0  add     rdi, 2
0x180002fc4  movzx   eax, word ptr [rdi]
0x180002fc7  test    ax, ax
0x180002fca  jnz     loc_180002E37
0x180002fd0  mov     r12, [rsp+540h+var_4E8]
0x180002fd5  mov     dword ptr [r12], 1
0x180002fdd  cmp     [r14+14h], r13d
0x180002fe1  jnz     short loc_180002FF8
0x180002fe3  lea     rdx, [rsp+540h+var_4E0]
0x180002fe8  mov     rcx, rsi
0x180002feb  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x180002ff1  mov     edi, eax
0x180002ff3  jmp     loc_180002E14
0x180002ff8  test    rbx, rbx
0x180002ffb  jz      short loc_180003006
0x180002ffd  mov     rcx, rbx; Block
0x180003000  call    cs:__imp_free
0x180003006  mov     edi, r13d
0x180003009  lea     rcx, [rbp+440h+var_4A8]
0x18000300d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003013  lea     rcx, [rsp+540h+var_4E0]
0x180003018  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000301e  mov     eax, edi
0x180003020  mov     rcx, [rbp+440h+var_50]
0x180003027  xor     rcx, rsp; StackCookie
0x18000302a  call    __security_check_cookie
0x18000302f  add     rsp, 508h
0x180003036  pop     r15
0x180003038  pop     r14
0x18000303a  pop     r13
0x18000303c  pop     r12
0x18000303e  pop     rdi
0x18000303f  pop     rsi
0x180003040  pop     rbx
  ... truncated ...
```
