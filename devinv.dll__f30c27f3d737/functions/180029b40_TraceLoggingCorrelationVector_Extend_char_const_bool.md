# TraceLoggingCorrelationVector::Extend(char const *,bool)

- ea: `0x180029b40`
- end: `0x180029ef4`
- name: `?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z`
- size: `948`
- prototype: `struct TraceLoggingCorrelationVector *__fastcall(const char *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180027f40`
- `0x18002a500`

## callees

- `0x180005e40`
- `0x1800066f0`
- `0x180006ec4`
- `0x180025c1c`
- `0x180029b40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x180029c71`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x180029c71`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180029c69`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180029e1e`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180029e60`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180029e78`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180029ead`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180029c69`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180029e1e`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180029e60`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180029e78`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180029ead`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x180029c81`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x180029c81`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180029c9e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180029c9e`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180029b6a`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180029c34`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180029b6a`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180029c34`
- `RPCRT4!UuidCreate` at `0x180029d34`
- `RPCRT4!UuidCreate` at `0x180029dac`
- `RPCRT4!UuidCreate` at `0x180029d34`
- `RPCRT4!UuidCreate` at `0x180029dac`

## pseudocode

```c
struct TraceLoggingCorrelationVector *__fastcall TraceLoggingCorrelationVector::Extend(const char *a1)
{
  unsigned __int64 v2; // rdx
  int v3; // r8d
  char v4; // r12
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // r14
  struct TraceLoggingCorrelationVector *result; // rax
  unsigned __int64 i; // rcx
  __int64 v9; // r9
  unsigned __int64 v10; // r15
  char *v11; // rax
  unsigned __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r15
  char *v17; // rax
  char *v18; // rbx
  char *v19; // rax
  _BYTE *v20; // r14
  char v21; // r12
  char String[16]; // [rsp+20h] [rbp-28h] BYREF

  v2 = strchr(a1, 46) - a1;
  if ( v2 == 22 )
  {
    v4 = 2;
  }
  else
  {
    if ( v2 != 16 )
      return 0;
    v4 = 1;
  }
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  if ( v4 == 1 )
  {
    if ( v6 > 0x41 )
      return 0;
  }
  else if ( v6 > 0x81 )
  {
    return 0;
  }
  for ( i = 0; i < v2; ++i )
  {
    LOBYTE(v3) = a1[i];
    if ( (unsigned __int8)(v3 - 43) <= 0x2Fu )
    {
      v9 = 0xFFFFFFC07FF1LL;
      if ( _bittest64(&v9, (unsigned int)(v3 - 43)) )
        continue;
    }
    if ( (unsigned __int8)(v3 - 97) > 0x19u )
      return 0;
  }
  do
  {
    if ( a1[i] != 46 )
      return 0;
    v10 = i + 1;
    if ( i + 1 >= v6 )
      return 0;
    *(_QWORD *)String = 0;
    *(_WORD *)&String[8] = 0;
    String[10] = 0;
    v11 = strchr(&a1[v10], 46);
    v12 = v11 ? &v11[-v10] - a1 : v6 - v10;
    if ( v12 >= 0xB )
      return 0;
    _o_strncpy_s(String, 11, &a1[v10], v12);
    _o__set_errno(0);
    if ( !strtol(String, 0, 10) && String[0] != 48 && String[1] )
      return 0;
    if ( *(_DWORD *)_o__errno(v14, v13, v15) == 34 )
      return 0;
    i = v10 + v12;
  }
  while ( v10 + v12 < v6 );
  v16 = 65;
  if ( v4 != 1 )
    v16 = 129;
  do
    ++v5;
  while ( a1[v5] );
  if ( v5 < v16 - 1 || v5 == v16 - 1 && a1[v5 - 1] == 33 )
  {
    if ( v4 == 1 )
    {
      v19 = (char *)operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
      v18 = v19;
      if ( v19 )
      {
        v19[130] = 65;
        *(_OWORD *)String = 0;
        UuidCreate((UUID *)String);
        v18[129] = 17;
        *((_QWORD *)v18 + 17) = 0x1300000000LL;
        memset_0(v18, 0, 0x81u);
        TLV::Base64Encode<129>(String, 12, v18);
        *((_WORD *)v18 + 8) = 46;
        goto LABEL_40;
      }
    }
    else
    {
      if ( v4 != 2 )
        return 0;
      v17 = (char *)operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
      v18 = v17;
      if ( v17 )
      {
        v17[130] = -127;
        *(_OWORD *)String = 0;
        UuidCreate((UUID *)String);
        v18[129] = 23;
        *((_QWORD *)v18 + 17) = 0x1900000000LL;
        memset_0(v18, 0, 0x81u);
        TLV::Base64Encode<129>(String, 16, v18);
        *((_WORD *)v18 + 11) = 46;
        goto LABEL_40;
      }
    }
    v18 = 0;
LABEL_40:
    if ( !v18 )
      return 0;
    if ( v5 && a1[v5 - 1] == 33 )
    {
      _o_strncpy_s(v18, 129, a1, v5 - 1);
      v20 = v18 + 129;
      v18[129] = v5 - 1;
      *((_QWORD *)v18 + 17) = (v5 + 1) << 32;
    }
    else
    {
      v20 = v18 + 129;
      if ( v5 == v16 - 2 )
      {
        _o_strncpy_s(v18, 129, a1, v5);
        *v20 = v5;
      }
      else
      {
        v21 = v5 + 1;
        if ( v5 != v16 - 3 )
        {
          _o_strncpy_s(v18, 129, a1, v5);
          v18[v5] = 46;
          *v20 = v21;
          *((_QWORD *)v18 + 17) = (v5 + 3) << 32;
          *((_QWORD *)v18 + 17) &= ~0x8000000000000000uLL;
          goto LABEL_51;
        }
        _o_strncpy_s(v18, 129, a1, v5);
        v18[v5] = 46;
        *v20 = v21;
      }
      *((_QWORD *)v18 + 17) = v16 << 32;
    }
    *((_QWORD *)v18 + 17) |= 0x8000000000000000uLL;
LABEL_51:
    result = (struct TraceLoggingCorrelationVector *)v18;
    v18[(unsigned __int8)*v20] = 0;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x180029b40  push    rbp
0x180029b42  push    rbx
0x180029b43  push    rsi
0x180029b44  push    rdi
0x180029b45  push    r12
0x180029b47  push    r13
0x180029b49  push    r14
0x180029b4b  push    r15
0x180029b4d  mov     rbp, rsp
0x180029b50  sub     rsp, 48h
0x180029b54  mov     rax, cs:__security_cookie
0x180029b5b  xor     rax, rsp
0x180029b5e  mov     [rbp+var_18], rax
0x180029b62  mov     edx, 2Eh ; '.'; Val
0x180029b67  mov     rsi, rcx
0x180029b6a  call    cs:__imp_strchr
0x180029b70  mov     rdx, rax
0x180029b73  sub     rdx, rsi
0x180029b76  cmp     rdx, 16h
0x180029b7a  jnz     short loc_180029B81
0x180029b7c  mov     r12b, 2
0x180029b7f  jmp     short loc_180029B8A
0x180029b81  cmp     rdx, 10h
0x180029b85  jnz     short loc_180029BAE
0x180029b87  mov     r12b, 1
0x180029b8a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029b8e  mov     r14, rdi
0x180029b91  xor     r13d, r13d
0x180029b94  inc     r14
0x180029b97  cmp     [rsi+r14], r13b
0x180029b9b  jnz     short loc_180029B94
0x180029b9d  mov     eax, 81h
0x180029ba2  cmp     r12b, 1
0x180029ba6  jnz     short loc_180029BCD
0x180029ba8  cmp     r14, 41h ; 'A'
0x180029bac  jbe     short loc_180029BD8
0x180029bae  xor     eax, eax
0x180029bb0  mov     rcx, [rbp+var_18]
0x180029bb4  xor     rcx, rsp; StackCookie
0x180029bb7  call    __security_check_cookie
0x180029bbc  add     rsp, 48h
0x180029bc0  pop     r15
0x180029bc2  pop     r14
0x180029bc4  pop     r13
0x180029bc6  pop     r12
0x180029bc8  pop     rdi
0x180029bc9  pop     rsi
0x180029bca  pop     rbx
0x180029bcb  pop     rbp
0x180029bcc  retn
0x180029bcd  cmp     r12b, 2
0x180029bd1  jnz     short loc_180029BD8
0x180029bd3  cmp     r14, rax
0x180029bd6  ja      short loc_180029BAE
0x180029bd8  mov     rcx, r13
0x180029bdb  test    rdx, rdx
0x180029bde  jz      short loc_180029C0E
0x180029be0  mov     r8b, [rsi+rcx]
0x180029be4  lea     eax, [r8-2Bh]
0x180029be8  cmp     al, 2Fh ; '/'
0x180029bea  ja      short loc_180029BFC
0x180029bec  mov     r9, 0FFFFFFC07FF1h
0x180029bf6  bt      r9, rax
0x180029bfa  jb      short loc_180029C06
0x180029bfc  sub     r8b, 61h ; 'a'
0x180029c00  cmp     r8b, 19h
0x180029c04  ja      short loc_180029BAE
0x180029c06  inc     rcx
0x180029c09  cmp     rcx, rdx
0x180029c0c  jb      short loc_180029BE0
0x180029c0e  cmp     byte ptr [rsi+rcx], 2Eh ; '.'
0x180029c12  jnz     short loc_180029BAE
0x180029c14  lea     r15, [rcx+1]
0x180029c18  cmp     r15, r14
0x180029c1b  jnb     short loc_180029BAE
0x180029c1d  xor     eax, eax
0x180029c1f  lea     r13, [r15+rsi]
0x180029c23  mov     rcx, r13; Str
0x180029c26  mov     qword ptr [rbp+String], rax
0x180029c2a  mov     word ptr [rbp+String+8], ax
0x180029c2e  mov     [rbp+String+0Ah], al
0x180029c31  lea     edx, [rax+2Eh]; Val
0x180029c34  call    cs:__imp_strchr
0x180029c3a  mov     rbx, rax
0x180029c3d  test    rax, rax
0x180029c40  jnz     short loc_180029C4A
0x180029c42  mov     rbx, r14
0x180029c45  sub     rbx, r15
0x180029c48  jmp     short loc_180029C50
0x180029c4a  sub     rbx, r15
0x180029c4d  sub     rbx, rsi
0x180029c50  cmp     rbx, 0Bh
0x180029c54  jnb     loc_180029BAE
0x180029c5a  mov     r9, rbx
0x180029c5d  lea     rcx, [rbp+String]
0x180029c61  mov     r8, r13
0x180029c64  mov     edx, 0Bh
0x180029c69  call    cs:__imp__o_strncpy_s
0x180029c6f  xor     ecx, ecx
0x180029c71  call    cs:__imp__o__set_errno
0x180029c77  xor     edx, edx; EndPtr
0x180029c79  lea     rcx, [rbp+String]; String
0x180029c7d  lea     r8d, [rdx+0Ah]; Radix
0x180029c81  call    cs:__imp_strtol
0x180029c87  xor     r13d, r13d
0x180029c8a  test    eax, eax
0x180029c8c  jnz     short loc_180029C9E
0x180029c8e  cmp     [rbp+String], 30h ; '0'
0x180029c92  jz      short loc_180029C9E
0x180029c94  cmp     [rbp+String+1], r13b
0x180029c98  jnz     loc_180029BAE
0x180029c9e  call    cs:__imp__o__errno
0x180029ca4  cmp     dword ptr [rax], 22h ; '"'
0x180029ca7  jz      loc_180029BAE
0x180029cad  lea     rcx, [r15+rbx]
0x180029cb1  cmp     rcx, r14
0x180029cb4  jb      loc_180029C0E
0x180029cba  mov     r15d, 41h ; 'A'
0x180029cc0  cmp     r12b, 1
0x180029cc4  lea     r14d, [r15+40h]
0x180029cc8  cmovnz  r15d, r14d
0x180029ccc  inc     rdi
0x180029ccf  cmp     [rsi+rdi], r13b
0x180029cd3  jnz     short loc_180029CCC
0x180029cd5  lea     rax, [r15-1]
0x180029cd9  cmp     rdi, rax
0x180029cdc  jb      short loc_180029CEF
0x180029cde  jnz     loc_180029BAE
0x180029ce4  cmp     byte ptr [rdi+rsi-1], 21h ; '!'
0x180029ce9  jnz     loc_180029BAE
0x180029cef  movzx   ecx, r12b
0x180029cf3  sub     ecx, 1
0x180029cf6  jz      loc_180029D81
0x180029cfc  cmp     ecx, 1
0x180029cff  jnz     loc_180029BAE
0x180029d05  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029d0c  mov     ecx, 90h; unsigned __int64
0x180029d11  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180029d16  mov     rbx, rax
0x180029d19  test    rax, rax
0x180029d1c  jz      loc_180029DF9
0x180029d22  xorps   xmm0, xmm0
0x180029d25  mov     [rax+82h], r14b
0x180029d2c  lea     rcx, [rbp+String]; Uuid
0x180029d30  movups  xmmword ptr [rbp+String], xmm0
0x180029d34  call    cs:__imp_UuidCreate
0x180029d3a  movaps  xmm0, xmmword ptr [rbp+String]
0x180029d3e  mov     rax, 1900000000h
0x180029d48  movdqa  xmmword ptr [rbp+String], xmm0
0x180029d4d  mov     r8, r14; Size
0x180029d50  mov     byte ptr [rbx+81h], 17h
0x180029d57  xor     edx, edx; Val
0x180029d59  mov     rcx, rbx; void *
0x180029d5c  mov     [rbx+88h], rax
0x180029d63  call    memset_0
0x180029d68  mov     r8, rbx
0x180029d6b  lea     rcx, [rbp+String]
0x180029d6f  mov     edx, 10h
0x180029d74  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x180029d79  mov     word ptr [rbx+16h], 2Eh ; '.'
0x180029d7f  jmp     short loc_180029DFC
0x180029d81  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029d88  mov     ecx, 90h; unsigned __int64
0x180029d8d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180029d92  mov     rbx, rax
0x180029d95  test    rax, rax
0x180029d98  jz      short loc_180029DF9
0x180029d9a  xorps   xmm0, xmm0
0x180029d9d  mov     byte ptr [rax+82h], 41h ; 'A'
0x180029da4  lea     rcx, [rbp+String]; Uuid
0x180029da8  movups  xmmword ptr [rbp+String], xmm0
0x180029dac  call    cs:__imp_UuidCreate
0x180029db2  movaps  xmm0, xmmword ptr [rbp+String]
0x180029db6  mov     rax, 1300000000h
0x180029dc0  movdqa  xmmword ptr [rbp+String], xmm0
0x180029dc5  mov     r8, r14; Size
0x180029dc8  mov     byte ptr [rbx+81h], 11h
0x180029dcf  xor     edx, edx; Val
0x180029dd1  mov     rcx, rbx; void *
0x180029dd4  mov     [rbx+88h], rax
0x180029ddb  call    memset_0
0x180029de0  mov     r8, rbx
0x180029de3  lea     rcx, [rbp+String]
0x180029de7  mov     edx, 0Ch
0x180029dec  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x180029df1  mov     word ptr [rbx+10h], 2Eh ; '.'
0x180029df7  jmp     short loc_180029DFC
0x180029df9  mov     rbx, r13
0x180029dfc  test    rbx, rbx
0x180029dff  jz      loc_180029BAE
0x180029e05  test    rdi, rdi
0x180029e08  jz      short loc_180029E42
0x180029e0a  cmp     byte ptr [rdi+rsi-1], 21h ; '!'
0x180029e0f  jnz     short loc_180029E42
0x180029e11  lea     r9, [rdi-1]
0x180029e15  mov     r8, rsi
0x180029e18  mov     rdx, r14
0x180029e1b  mov     rcx, rbx
0x180029e1e  call    cs:__imp__o_strncpy_s
0x180029e24  lea     eax, [rdi-1]
0x180029e27  lea     r14, [rbx+81h]
0x180029e2e  mov     [r14], al
0x180029e31  lea     rax, [rdi+1]
0x180029e35  shl     rax, 20h
0x180029e39  mov     [rbx+88h], rax
0x180029e40  jmp     short loc_180029E90
0x180029e42  lea     rax, [r15-2]
0x180029e46  mov     r9, rdi
0x180029e49  lea     r14, [rbx+81h]
0x180029e50  mov     r8, rsi
0x180029e53  mov     edx, 81h
0x180029e58  mov     rcx, rbx
0x180029e5b  cmp     rdi, rax
0x180029e5e  jnz     short loc_180029E6B
0x180029e60  call    cs:__imp__o_strncpy_s
0x180029e66  mov     [r14], dil
0x180029e69  jmp     short loc_180029E85
0x180029e6b  lea     rax, [r15-3]
0x180029e6f  lea     r12d, [rdi+1]
0x180029e73  cmp     rdi, rax
0x180029e76  jnz     short loc_180029EAD
0x180029e78  call    cs:__imp__o_strncpy_s
0x180029e7e  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x180029e82  mov     [r14], r12b
0x180029e85  shl     r15, 20h
0x180029e89  mov     [rbx+88h], r15
0x180029e90  mov     rax, [rbx+88h]
0x180029e97  mov     rcx, 8000000000000000h
0x180029ea1  or      rax, rcx
0x180029ea4  mov     [rbx+88h], rax
0x180029eab  jmp     short loc_180029EE4
0x180029ead  call    cs:__imp__o_strncpy_s
0x180029eb3  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x180029eb7  lea     rcx, [rdi+3]
0x180029ebb  shl     rcx, 20h
0x180029ebf  mov     rax, 7FFFFFFFFFFFFFFFh
0x180029ec9  mov     [r14], r12b
0x180029ecc  mov     [rbx+88h], rcx
0x180029ed3  mov     rcx, [rbx+88h]
0x180029eda  and     rcx, rax
0x180029edd  mov     [rbx+88h], rcx
0x180029ee4  movzx   ecx, byte ptr [r14]
0x180029ee8  mov     rax, rbx
0x180029eeb  mov     [rcx+rbx], r13b
0x180029eef  jmp     loc_180029BB0
```
