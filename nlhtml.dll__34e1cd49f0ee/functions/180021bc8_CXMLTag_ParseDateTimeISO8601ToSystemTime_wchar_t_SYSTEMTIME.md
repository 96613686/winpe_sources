# CXMLTag::ParseDateTimeISO8601ToSystemTime(wchar_t *,_SYSTEMTIME *)

- ea: `0x180021bc8`
- end: `0x180021dc6`
- name: `?ParseDateTimeISO8601ToSystemTime@CXMLTag@@AEAA_NPEA_WPEAU_SYSTEMTIME@@@Z`
- size: `510`
- prototype: `bool(CXMLTag *__hidden this, wchar_t *, struct _SYSTEMTIME *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000fb70`

## callees

- `0x180021a2c`
- `0x180021bc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021cb3`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021ccc`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021cde`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021d76`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021d84`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021d92`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021cb3`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021ccc`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021cde`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021d76`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021d84`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021d92`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180021c93`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180021d2f`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180021c93`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180021d2f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180021c35`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180021c35`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180021be9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180021c26`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180021c44`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180021d44`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180021be9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180021c26`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180021c44`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180021d44`

## pseudocode

```c
char __fastcall CXMLTag::ParseDateTimeISO8601ToSystemTime(CXMLTag *this, wchar_t *a2, struct _SYSTEMTIME *a3)
{
  wchar_t *v5; // rax
  CXMLTag *v6; // rcx
  wchar_t *v7; // rdi
  const wchar_t *v8; // rdi
  wchar_t *v9; // r14
  wchar_t *v10; // rbx
  wchar_t *v11; // rax
  wchar_t *v12; // r15
  __int64 v13; // rax
  int j; // ebx
  wchar_t v15; // bx
  wchar_t v16; // bx
  __int64 v17; // rax
  int i; // esi
  wchar_t *v19; // rcx

  v5 = wcschr(a2, 0x54u);
  v7 = v5;
  if ( !v5 )
    return 0;
  *v5 = 0;
  if ( !CXMLTag::ParseDateISO8601ToSystemTime(v6, a2, a3) )
    return 0;
  *v7 = 84;
  v8 = v7 + 1;
  v9 = wcschr(v8, 0x3Au);
  v10 = wcsrchr(v8, 0x3Au);
  v11 = wcschr(v8, 0x5Au);
  v12 = v11;
  if ( !v11 )
    return 0;
  *v11 = 0;
  if ( v9 )
  {
    if ( v10 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v8[v17] );
      if ( v17 != 8 )
        return 0;
      for ( i = 0; i < 8; ++i )
      {
        v19 = (wchar_t *)&v8[i];
        if ( v19 != v9 && v19 != v10 && !(unsigned int)_o_iswdigit(*v19) )
          return 0;
      }
      if ( wcschr(v9 + 1, 0x3Au) != v10 || (unsigned int)(v9 - v8) != 2 || (unsigned int)(v10 - v8) != 5 )
        return 0;
      *v9 = 0;
      *v10 = 0;
      a3->wHour = _o__wtoi(v8);
      a3->wMinute = _o__wtoi(v8 + 3);
      *(_DWORD *)&a3->wSecond = (unsigned __int16)_o__wtoi(v8 + 6);
      *v9 = 58;
      *v10 = 58;
    }
LABEL_28:
    *v12 = 90;
    return 1;
  }
  if ( v10 )
    goto LABEL_28;
  v13 = -1;
  do
    ++v13;
  while ( v8[v13] );
  if ( v13 == 6 )
  {
    for ( j = 0; j < 6; ++j )
    {
      if ( !(unsigned int)_o_iswdigit(v8[j]) )
        return 0;
    }
    v15 = v8[2];
    *((_WORD *)v8 + 2) = 0;
    a3->wHour = _o__wtoi(v8);
    *((_WORD *)v8 + 2) = v15;
    v16 = v8[4];
    *((_WORD *)v8 + 4) = 0;
    a3->wMinute = _o__wtoi(v8 + 2);
    *((_WORD *)v8 + 4) = v16;
    *(_DWORD *)&a3->wSecond = (unsigned __int16)_o__wtoi(v8 + 4);
    goto LABEL_28;
  }
  return 0;
}

```

## disassembly

```asm
0x180021bc8  push    rbx
0x180021bca  push    rbp
0x180021bcb  push    rsi
0x180021bcc  push    rdi
0x180021bcd  push    r12
0x180021bcf  push    r13
0x180021bd1  push    r14
0x180021bd3  push    r15
0x180021bd5  sub     rsp, 28h
0x180021bd9  mov     rbx, rdx
0x180021bdc  mov     esi, 54h ; 'T'
0x180021be1  mov     edx, esi; Ch
0x180021be3  mov     rcx, rbx; Str
0x180021be6  mov     rbp, r8
0x180021be9  call    cs:__imp_wcschr
0x180021bef  xor     r12d, r12d
0x180021bf2  mov     rdi, rax
0x180021bf5  test    rax, rax
0x180021bf8  jz      loc_180021DB3
0x180021bfe  mov     r8, rbp; struct _SYSTEMTIME *
0x180021c01  mov     [rax], r12w
0x180021c05  mov     rdx, rbx; wchar_t *
0x180021c08  call    ?ParseDateISO8601ToSystemTime@CXMLTag@@AEAA_NPEA_WPEAU_SYSTEMTIME@@@Z; CXMLTag::ParseDateISO8601ToSystemTime(wchar_t *,_SYSTEMTIME *)
0x180021c0d  test    al, al
0x180021c0f  jz      loc_180021DB3
0x180021c15  mov     [rdi], si
0x180021c18  lea     r13d, [rsi-1Ah]
0x180021c1c  add     rdi, 2
0x180021c20  mov     edx, r13d; Ch
0x180021c23  mov     rcx, rdi; Str
0x180021c26  call    cs:__imp_wcschr
0x180021c2c  mov     edx, r13d; Ch
0x180021c2f  mov     rcx, rdi; Str
0x180021c32  mov     r14, rax
0x180021c35  call    cs:__imp_wcsrchr
0x180021c3b  lea     edx, [rsi+6]; Ch
0x180021c3e  mov     rcx, rdi; Str
0x180021c41  mov     rbx, rax
0x180021c44  call    cs:__imp_wcschr
0x180021c4a  mov     r15, rax
0x180021c4d  test    rax, rax
0x180021c50  jz      loc_180021DB3
0x180021c56  mov     [rax], r12w
0x180021c5a  test    r14, r14
0x180021c5d  jnz     loc_180021CF2
0x180021c63  test    rbx, rbx
0x180021c66  jnz     loc_180021DA9
0x180021c6c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021c70  inc     rax
0x180021c73  cmp     [rdi+rax*2], r12w
0x180021c78  jnz     short loc_180021C70
0x180021c7a  cmp     rax, 6
0x180021c7e  jnz     loc_180021DB3
0x180021c84  mov     ebx, r12d
0x180021c87  cmp     ebx, 6
0x180021c8a  jge     short loc_180021CA5
0x180021c8c  movsxd  rcx, ebx
0x180021c8f  movzx   ecx, word ptr [rdi+rcx*2]
0x180021c93  call    cs:__imp__o_iswdigit
0x180021c99  test    eax, eax
0x180021c9b  jz      loc_180021DB3
0x180021ca1  inc     ebx
0x180021ca3  jmp     short loc_180021C87
0x180021ca5  lea     rsi, [rdi+4]
0x180021ca9  mov     rcx, rdi
0x180021cac  movzx   ebx, word ptr [rsi]
0x180021caf  mov     [rsi], r12w
0x180021cb3  call    cs:__imp__o__wtoi
0x180021cb9  mov     [rbp+8], ax
0x180021cbd  mov     rcx, rsi
0x180021cc0  mov     [rsi], bx
0x180021cc3  movzx   ebx, word ptr [rdi+8]
0x180021cc7  mov     [rdi+8], r12w
0x180021ccc  call    cs:__imp__o__wtoi
0x180021cd2  mov     [rbp+0Ah], ax
0x180021cd6  lea     rcx, [rdi+8]
0x180021cda  mov     [rdi+8], bx
0x180021cde  call    cs:__imp__o__wtoi
0x180021ce4  mov     [rbp+0Ch], ax
0x180021ce8  mov     [rbp+0Eh], r12w
0x180021ced  jmp     loc_180021DA9
0x180021cf2  test    rbx, rbx
0x180021cf5  jz      loc_180021DA9
0x180021cfb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021cff  inc     rax
0x180021d02  cmp     [rdi+rax*2], r12w
0x180021d07  jnz     short loc_180021CFF
0x180021d09  cmp     rax, 8
0x180021d0d  jnz     loc_180021DB3
0x180021d13  mov     esi, r12d
0x180021d16  cmp     esi, 8
0x180021d19  jge     short loc_180021D3D
0x180021d1b  movsxd  rax, esi
0x180021d1e  lea     rcx, [rdi+rax*2]
0x180021d22  cmp     rcx, r14
0x180021d25  jz      short loc_180021D39
0x180021d27  cmp     rcx, rbx
0x180021d2a  jz      short loc_180021D39
0x180021d2c  movzx   ecx, word ptr [rcx]
0x180021d2f  call    cs:__imp__o_iswdigit
0x180021d35  test    eax, eax
0x180021d37  jz      short loc_180021DB3
0x180021d39  inc     esi
0x180021d3b  jmp     short loc_180021D16
0x180021d3d  mov     edx, r13d; Ch
0x180021d40  lea     rcx, [r14+2]; Str
0x180021d44  call    cs:__imp_wcschr
0x180021d4a  cmp     rax, rbx
0x180021d4d  jnz     short loc_180021DB3
0x180021d4f  mov     rax, r14
0x180021d52  sub     rax, rdi
0x180021d55  sar     rax, 1
0x180021d58  cmp     eax, 2
0x180021d5b  jnz     short loc_180021DB3
0x180021d5d  mov     rax, rbx
0x180021d60  sub     rax, rdi
0x180021d63  sar     rax, 1
0x180021d66  cmp     eax, 5
0x180021d69  jnz     short loc_180021DB3
0x180021d6b  mov     [r14], r12w
0x180021d6f  mov     rcx, rdi
0x180021d72  mov     [rbx], r12w
0x180021d76  call    cs:__imp__o__wtoi
0x180021d7c  lea     rcx, [rdi+6]
0x180021d80  mov     [rbp+8], ax
0x180021d84  call    cs:__imp__o__wtoi
0x180021d8a  lea     rcx, [rdi+0Ch]
0x180021d8e  mov     [rbp+0Ah], ax
0x180021d92  call    cs:__imp__o__wtoi
0x180021d98  mov     [rbp+0Ch], ax
0x180021d9c  mov     [rbp+0Eh], r12w
0x180021da1  mov     [r14], r13w
0x180021da5  mov     [rbx], r13w
0x180021da9  mov     word ptr [r15], 5Ah ; 'Z'
0x180021daf  mov     al, 1
0x180021db1  jmp     short loc_180021DB5
0x180021db3  xor     al, al
0x180021db5  add     rsp, 28h
0x180021db9  pop     r15
0x180021dbb  pop     r14
0x180021dbd  pop     r13
0x180021dbf  pop     r12
0x180021dc1  pop     rdi
0x180021dc2  pop     rsi
0x180021dc3  pop     rbp
0x180021dc4  pop     rbx
0x180021dc5  retn
```
