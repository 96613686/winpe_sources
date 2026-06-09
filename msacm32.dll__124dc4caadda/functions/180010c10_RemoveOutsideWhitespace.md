# RemoveOutsideWhitespace

- ea: `0x180010c10`
- end: `0x180010cc7`
- name: `RemoveOutsideWhitespace`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000f8a0`

## callees

- `0x180007380`
- `0x180010c10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x180010c39`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x180010cab`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x180010c39`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x180010cab`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010c46`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010c81`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010c46`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010c81`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x180010c9a`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x180010c9a`

## pseudocode

```c
__int64 __fastcall RemoveOutsideWhitespace(__int64 a1, unsigned __int16 *a2)
{
  wchar_t *v2; // rdi
  wint_t v3; // ax
  const WCHAR *v5; // rbx
  const WCHAR *i; // rax
  const WCHAR *j; // rdx
  wint_t *v8; // rbx

  v2 = a2 + 1;
  v3 = a2[1];
  v5 = a2 + 1;
  if ( !v3 )
    return 0;
  do
  {
    if ( !iswctype(v3, 8u) )
      break;
    v5 = CharNextW(v5);
    v3 = *v5;
  }
  while ( *v5 );
  if ( !*v5 )
    return 0;
  if ( v5 != v2 )
    StringCchCopyW(v2, ((unsigned __int64)*a2 - 2) >> 1, v5);
  for ( i = v2; *i; i = CharNextW(i) )
    ;
  for ( j = i; ; j = v8 )
  {
    v8 = CharPrevW(v2, j);
    if ( !iswctype(*v8, 8u) )
      break;
    *v8 = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180010c10  push    rbx
0x180010c12  push    rbp
0x180010c13  push    rsi
0x180010c14  push    rdi
0x180010c15  sub     rsp, 28h
0x180010c19  lea     rdi, [rdx+2]
0x180010c1d  xor     ebp, ebp
0x180010c1f  movzx   eax, word ptr [rdi]
0x180010c22  mov     rsi, rdx
0x180010c25  mov     rbx, rdi
0x180010c28  test    ax, ax
0x180010c2b  jz      loc_180010CBC
0x180010c31  mov     edx, 8; Type
0x180010c36  movzx   ecx, ax; C
0x180010c39  call    cs:__imp_iswctype
0x180010c3f  test    eax, eax
0x180010c41  jz      short loc_180010C57
0x180010c43  mov     rcx, rbx; lpsz
0x180010c46  call    cs:__imp_CharNextW
0x180010c4c  mov     rbx, rax
0x180010c4f  movzx   eax, word ptr [rax]
0x180010c52  test    ax, ax
0x180010c55  jnz     short loc_180010C31
0x180010c57  cmp     [rbx], bp
0x180010c5a  jz      short loc_180010CBC
0x180010c5c  cmp     rbx, rdi
0x180010c5f  jz      short loc_180010C76
0x180010c61  movzx   edx, word ptr [rsi]
0x180010c64  mov     r8, rbx; pszSrc
0x180010c67  sub     rdx, 2
0x180010c6b  mov     rcx, rdi; pszDest
0x180010c6e  shr     rdx, 1; cchDest
0x180010c71  call    StringCchCopyW
0x180010c76  mov     rax, rdi
0x180010c79  cmp     [rdi], bp
0x180010c7c  jz      short loc_180010C8C
0x180010c7e  mov     rcx, rax; lpsz
0x180010c81  call    cs:__imp_CharNextW
0x180010c87  cmp     [rax], bp
0x180010c8a  jnz     short loc_180010C7E
0x180010c8c  mov     rdx, rax
0x180010c8f  jmp     short loc_180010C97
0x180010c91  mov     [rbx], bp
0x180010c94  mov     rdx, rbx; lpszCurrent
0x180010c97  mov     rcx, rdi; lpszStart
0x180010c9a  call    cs:__imp_CharPrevW
0x180010ca0  mov     edx, 8; Type
0x180010ca5  mov     rbx, rax
0x180010ca8  movzx   ecx, word ptr [rax]; C
0x180010cab  call    cs:__imp_iswctype
0x180010cb1  test    eax, eax
0x180010cb3  jnz     short loc_180010C91
0x180010cb5  mov     eax, 1
0x180010cba  jmp     short loc_180010CBE
0x180010cbc  xor     eax, eax
0x180010cbe  add     rsp, 28h
0x180010cc2  pop     rdi
0x180010cc3  pop     rsi
0x180010cc4  pop     rbp
0x180010cc5  pop     rbx
0x180010cc6  retn
```
