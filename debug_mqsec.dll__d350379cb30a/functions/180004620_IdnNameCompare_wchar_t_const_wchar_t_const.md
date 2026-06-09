# IdnNameCompare(wchar_t const *,wchar_t const *)

- ea: `0x180004620`
- end: `0x180004773`
- name: `?IdnNameCompare@@YAHPEB_W0@Z`
- size: `339`
- prototype: `__int64 __fastcall(LPCWSTR lpUnicodeCharStr, const wchar_t *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004074`
- `0x180004620`
- `0x18001722c`

## import_xrefs

- `msvcrt!free` at `0x180004728`
- `msvcrt!free` at `0x180004732`
- `msvcrt!free` at `0x180004740`
- `msvcrt!free` at `0x18000474a`
- `msvcrt!free` at `0x180004756`
- `msvcrt!free` at `0x180004728`
- `msvcrt!free` at `0x180004732`
- `msvcrt!free` at `0x180004740`
- `msvcrt!free` at `0x18000474a`
- `msvcrt!free` at `0x180004756`
- `Normaliz!IdnToNameprepUnicode` at `0x180004655`
- `Normaliz!IdnToNameprepUnicode` at `0x180004692`
- `Normaliz!IdnToNameprepUnicode` at `0x1800046c2`
- `Normaliz!IdnToNameprepUnicode` at `0x1800046f7`
- `Normaliz!IdnToNameprepUnicode` at `0x180004655`
- `Normaliz!IdnToNameprepUnicode` at `0x180004692`
- `Normaliz!IdnToNameprepUnicode` at `0x1800046c2`
- `Normaliz!IdnToNameprepUnicode` at `0x1800046f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall IdnNameCompare(LPCWSTR lpUnicodeCharStr, const wchar_t *a2)
{
  void *v4; // rbx
  int v5; // r14d
  unsigned int v6; // eax
  int cchNameprepChar; // ebp
  void *v8; // rdi
  int v9; // r14d
  unsigned int v10; // eax
  int v11; // ebp
  unsigned __int16 *v12; // rax
  signed __int64 v13; // rdx
  unsigned __int16 v14; // cx
  unsigned int v15; // esi

  v4 = 0;
  v5 = mqwcslen(lpUnicodeCharStr) + 1;
  v6 = IdnToNameprepUnicode(0, lpUnicodeCharStr, v5, 0, 0);
  cchNameprepChar = v6;
  if ( !v6
    || (v4 = MmAllocate(saturated_mul(v6, 2u)),
        !IdnToNameprepUnicode(0, lpUnicodeCharStr, v5, (LPWSTR)v4, cchNameprepChar)) )
  {
    free(v4);
    return 0x7FFFFFFF;
  }
  v8 = 0;
  v9 = mqwcslen(a2) + 1;
  v10 = IdnToNameprepUnicode(0, a2, v9, 0, 0);
  v11 = v10;
  if ( !v10 || (v8 = MmAllocate(saturated_mul(v10, 2u)), !IdnToNameprepUnicode(0, a2, v9, (LPWSTR)v8, v11)) )
  {
    free(v8);
    free(v4);
    return 0x7FFFFFFF;
  }
  v12 = (unsigned __int16 *)v4;
  v13 = (_BYTE *)v8 - (_BYTE *)v4;
  while ( 1 )
  {
    v14 = *v12;
    if ( *v12 != *(unsigned __int16 *)((char *)v12 + v13) )
      break;
    ++v12;
    if ( !v14 )
    {
      v15 = 0;
      goto LABEL_10;
    }
  }
  v15 = v14 < *(unsigned __int16 *)((char *)v12 + v13) ? -1 : 1;
LABEL_10:
  free(v8);
  free(v4);
  return v15;
}

```

## disassembly

```asm
0x180004620  mov     [rsp+arg_0], rbx
0x180004625  push    rbp
0x180004626  push    rsi
0x180004627  push    rdi
0x180004628  push    r12
0x18000462a  push    r14
0x18000462c  sub     rsp, 30h
0x180004630  mov     rsi, rdx
0x180004633  mov     rdi, rcx
0x180004636  xor     ebx, ebx
0x180004638  mov     [rsp+58h+arg_10], rbx
0x18000463d  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180004642  lea     r14d, [rax+1]
0x180004646  mov     [rsp+58h+cchNameprepChar], ebx; cchNameprepChar
0x18000464a  xor     r9d, r9d; lpNameprepCharStr
0x18000464d  mov     r8d, r14d; cchUnicodeChar
0x180004650  mov     rdx, rdi; lpUnicodeCharStr
0x180004653  xor     ecx, ecx; dwFlags
0x180004655  call    cs:__imp_IdnToNameprepUnicode
0x18000465b  mov     ebp, eax
0x18000465d  test    eax, eax
0x18000465f  jz      loc_180004753
0x180004665  lea     eax, [rbx+2]
0x180004668  mul     rbp
0x18000466b  lea     r12, [rbx-1]
0x18000466f  cmovb   rax, r12
0x180004673  mov     rcx, rax; unsigned __int64
0x180004676  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000467b  mov     rbx, rax
0x18000467e  mov     [rsp+58h+arg_10], rax
0x180004683  mov     [rsp+58h+cchNameprepChar], ebp; cchNameprepChar
0x180004687  mov     r9, rax; lpNameprepCharStr
0x18000468a  mov     r8d, r14d; cchUnicodeChar
0x18000468d  mov     rdx, rdi; lpUnicodeCharStr
0x180004690  xor     ecx, ecx; dwFlags
0x180004692  call    cs:__imp_IdnToNameprepUnicode
0x180004698  test    eax, eax
0x18000469a  jz      loc_180004753
0x1800046a0  xor     edi, edi
0x1800046a2  mov     [rsp+58h+arg_18], rdi
0x1800046a7  mov     rcx, rsi; wchar_t *
0x1800046aa  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800046af  lea     r14d, [rax+1]
0x1800046b3  mov     [rsp+58h+cchNameprepChar], edi; cchNameprepChar
0x1800046b7  xor     r9d, r9d; lpNameprepCharStr
0x1800046ba  mov     r8d, r14d; cchUnicodeChar
0x1800046bd  mov     rdx, rsi; lpUnicodeCharStr
0x1800046c0  xor     ecx, ecx; dwFlags
0x1800046c2  call    cs:__imp_IdnToNameprepUnicode
0x1800046c8  mov     ebp, eax
0x1800046ca  test    eax, eax
0x1800046cc  jz      short loc_18000473D
0x1800046ce  lea     eax, [rdi+2]
0x1800046d1  mul     rbp
0x1800046d4  cmovb   rax, r12
0x1800046d8  mov     rcx, rax; unsigned __int64
0x1800046db  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800046e0  mov     rdi, rax
0x1800046e3  mov     [rsp+58h+arg_18], rax
0x1800046e8  mov     [rsp+58h+cchNameprepChar], ebp; cchNameprepChar
0x1800046ec  mov     r9, rax; lpNameprepCharStr
0x1800046ef  mov     r8d, r14d; cchUnicodeChar
0x1800046f2  mov     rdx, rsi; lpUnicodeCharStr
0x1800046f5  xor     ecx, ecx; dwFlags
0x1800046f7  call    cs:__imp_IdnToNameprepUnicode
0x1800046fd  test    eax, eax
0x1800046ff  jz      short loc_18000473D
0x180004701  mov     rax, rbx
0x180004704  mov     rdx, rdi
0x180004707  sub     rdx, rbx
0x18000470a  movzx   ecx, word ptr [rax]
0x18000470d  cmp     cx, [rax+rdx]
0x180004711  jnz     short loc_180004720
0x180004713  add     rax, 2
0x180004717  test    cx, cx
0x18000471a  jnz     short loc_18000470A
0x18000471c  xor     esi, esi
0x18000471e  jmp     short loc_180004725
0x180004720  sbb     esi, esi
0x180004722  or      esi, 1
0x180004725  mov     rcx, rdi; Block
0x180004728  call    cs:__imp_free
0x18000472e  nop
0x18000472f  mov     rcx, rbx; Block
0x180004732  call    cs:__imp_free
0x180004738  nop
0x180004739  mov     eax, esi
0x18000473b  jmp     short loc_180004762
0x18000473d  mov     rcx, rdi; Block
0x180004740  call    cs:__imp_free
0x180004746  nop
0x180004747  mov     rcx, rbx; Block
0x18000474a  call    cs:__imp_free
0x180004750  nop
0x180004751  jmp     short loc_18000475D
0x180004753  mov     rcx, rbx; Block
0x180004756  call    cs:__imp_free
0x18000475c  nop
0x18000475d  mov     eax, 7FFFFFFFh
0x180004762  mov     rbx, [rsp+58h+arg_0]
0x180004767  add     rsp, 30h
0x18000476b  pop     r14
0x18000476d  pop     r12
0x18000476f  pop     rdi
0x180004770  pop     rsi
0x180004771  pop     rbp
0x180004772  retn
```
