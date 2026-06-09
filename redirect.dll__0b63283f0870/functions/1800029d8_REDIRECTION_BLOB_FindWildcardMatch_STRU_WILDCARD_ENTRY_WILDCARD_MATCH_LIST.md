# REDIRECTION_BLOB::FindWildcardMatch(STRU &,WILDCARD_ENTRY * *,WILDCARD_MATCH_LIST *)

- ea: `0x1800029d8`
- end: `0x180002bbb`
- name: `?FindWildcardMatch@REDIRECTION_BLOB@@QEAAJAEAVSTRU@@PEAPEAUWILDCARD_ENTRY@@PEAVWILDCARD_MATCH_LIST@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(REDIRECTION_BLOB *this, const wchar_t **, struct WILDCARD_ENTRY **, struct WILDCARD_MATCH_LIST *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002bc4`

## callees

- `0x1800029d8`

## import_xrefs

- `msvcrt!wcschr` at `0x180002a7f`
- `msvcrt!wcschr` at `0x180002a7f`
- `msvcrt!towupper` at `0x180002a48`
- `msvcrt!towupper` at `0x180002a54`
- `msvcrt!towupper` at `0x180002a48`
- `msvcrt!towupper` at `0x180002a54`
- `msvcrt!_wcsnicmp` at `0x180002aad`
- `msvcrt!_wcsnicmp` at `0x180002aad`
- `msvcrt!malloc` at `0x180002ade`
- `msvcrt!malloc` at `0x180002b34`
- `msvcrt!malloc` at `0x180002ade`
- `msvcrt!malloc` at `0x180002b34`

## pseudocode

```c
__int64 __fastcall REDIRECTION_BLOB::FindWildcardMatch(
        REDIRECTION_BLOB *this,
        const wchar_t **a2,
        struct WILDCARD_ENTRY **a3,
        struct WILDCARD_MATCH_LIST *a4)
{
  REDIRECTION_BLOB *v5; // r15
  REDIRECTION_BLOB *v7; // r12
  wint_t *v8; // rcx
  const wchar_t *v9; // r14
  wint_t v10; // bp
  const wchar_t *v11; // rsi
  wint_t v12; // bx
  wchar_t *v13; // rbx
  __int64 v14; // rbx
  _WORD *v15; // rcx
  wchar_t v16; // bp
  _WORD *v17; // rax
  _WORD *v18; // rdx
  _WORD *v19; // rax
  wchar_t *v21; // [rsp+20h] [rbp-48h]
  struct STRU *v23; // [rsp+78h] [rbp+10h]

  v23 = (struct STRU *)a2;
  v5 = (REDIRECTION_BLOB *)*((_QWORD *)this + 18);
  v7 = this;
  if ( v5 != (REDIRECTION_BLOB *)((char *)this + 144) )
  {
LABEL_2:
    v8 = (wint_t *)*((_QWORD *)v5 - 10);
    v9 = a2[4];
    *((_QWORD *)a4 + 1) = 0;
    v10 = *v8;
    v11 = v8 + 1;
    v21 = &v8[*((unsigned int *)v5 - 16)];
    while ( 1 )
    {
      if ( !v10 )
      {
        if ( !*v9 )
        {
          *a3 = (REDIRECTION_BLOB *)((char *)v5 - 112);
          return 0;
        }
LABEL_28:
        v5 = *(REDIRECTION_BLOB **)v5;
        if ( v5 == (REDIRECTION_BLOB *)((char *)v7 + 144) )
          break;
        a2 = (const wchar_t **)v23;
        goto LABEL_2;
      }
      if ( v10 == 42 )
      {
        while ( *v11 == 42 )
          ++v11;
        v13 = wcschr(v11, 0x2Au);
        if ( !v13 )
          v13 = v21;
        v14 = v13 - v11;
        if ( !*v9 )
          goto LABEL_19;
        do
        {
          if ( !_wcsnicmp(v11, v9, (int)v14) && (_DWORD)v14 )
            break;
          if ( *((_DWORD *)this + 4) )
          {
            v15 = *(_WORD **)a4;
            v16 = *v9;
            if ( !*(_QWORD *)a4 )
            {
              v17 = malloc(2LL * (unsigned int)(2 * *((_DWORD *)a4 + 4)));
              *(_QWORD *)a4 = v17;
              v15 = v17;
              if ( !v17 )
                return 2147942408LL;
            }
            v15[(*((_DWORD *)a4 + 2))++] = v16;
          }
          ++v9;
        }
        while ( *v9 );
        v7 = this;
        if ( !*v9 )
        {
LABEL_19:
          if ( (_DWORD)v14 )
            goto LABEL_28;
        }
        if ( *((_DWORD *)v7 + 4) )
        {
          ++*((_DWORD *)a4 + 3);
          v18 = *(_WORD **)a4;
          if ( !*(_QWORD *)a4 )
          {
            v19 = malloc(2LL * (unsigned int)(2 * *((_DWORD *)a4 + 4)));
            *(_QWORD *)a4 = v19;
            v18 = v19;
            if ( !v19 )
              return 2147942408LL;
          }
          v18[(*((_DWORD *)a4 + 2))++] = 0;
        }
      }
      else
      {
        v12 = towupper(*v9);
        if ( v12 != towupper(v10) )
          goto LABEL_28;
        ++v9;
      }
      v10 = *v11++;
    }
  }
  *a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800029d8  mov     [rsp+arg_10], rbx
0x1800029dd  mov     [rsp+arg_8], rdx
0x1800029e2  mov     [rsp+arg_0], rcx
0x1800029e7  push    rbp
0x1800029e8  push    rsi
0x1800029e9  push    rdi
0x1800029ea  push    r12
0x1800029ec  push    r13
0x1800029ee  push    r14
0x1800029f0  push    r15
0x1800029f2  sub     rsp, 30h
0x1800029f6  lea     rax, [rcx+90h]
0x1800029fd  mov     r13, r8
0x180002a00  mov     r15, [rax]
0x180002a03  xor     r8d, r8d
0x180002a06  mov     rdi, r9
0x180002a09  mov     r12, rcx
0x180002a0c  cmp     r15, rax
0x180002a0f  jz      loc_180002B9D
0x180002a15  mov     rcx, [r15-50h]
0x180002a19  mov     r14, [rdx+20h]
0x180002a1d  mov     qword ptr [rdi+8], 0
0x180002a25  mov     eax, [r15-40h]
0x180002a29  movzx   ebp, word ptr [rcx]
0x180002a2c  lea     rsi, [rcx+2]
0x180002a30  lea     rax, [rcx+rax*2]
0x180002a34  mov     [rsp+68h+var_48], rax
0x180002a39  jmp     loc_180002B5A
0x180002a3e  cmp     bp, r9w
0x180002a42  jz      short loc_180002A73
0x180002a44  movzx   ecx, word ptr [r14]; C
0x180002a48  call    cs:__imp_towupper
0x180002a4e  movzx   ecx, bp; C
0x180002a51  movzx   ebx, ax
0x180002a54  call    cs:__imp_towupper
0x180002a5a  cmp     bx, ax
0x180002a5d  jnz     loc_180002B79
0x180002a63  add     r14, 2
0x180002a67  xor     r8d, r8d
0x180002a6a  jmp     loc_180002B53
0x180002a6f  add     rsi, 2
0x180002a73  cmp     [rsi], r9w
0x180002a77  jz      short loc_180002A6F
0x180002a79  mov     edx, r9d; Ch
0x180002a7c  mov     rcx, rsi; Str
0x180002a7f  call    cs:__imp_wcschr
0x180002a85  xor     r8d, r8d
0x180002a88  mov     rbx, rax
0x180002a8b  test    rax, rax
0x180002a8e  jnz     short loc_180002A95
0x180002a90  mov     rbx, [rsp+68h+var_48]
0x180002a95  sub     rbx, rsi
0x180002a98  sar     rbx, 1
0x180002a9b  cmp     [r14], r8w
0x180002a9f  jz      short loc_180002B15
0x180002aa1  movsxd  r12, ebx
0x180002aa4  mov     r8, r12; MaxCount
0x180002aa7  mov     rdx, r14; String2
0x180002aaa  mov     rcx, rsi; String1
0x180002aad  call    cs:__imp__wcsnicmp
0x180002ab3  xor     r8d, r8d
0x180002ab6  test    eax, eax
0x180002ab8  jnz     short loc_180002ABE
0x180002aba  test    ebx, ebx
0x180002abc  jnz     short loc_180002B0A
0x180002abe  mov     rax, [rsp+68h+arg_0]
0x180002ac3  cmp     [rax+10h], r8d
0x180002ac7  jz      short loc_180002B00
0x180002ac9  mov     rcx, [rdi]
0x180002acc  movzx   ebp, word ptr [r14]
0x180002ad0  test    rcx, rcx
0x180002ad3  jnz     short loc_180002AF6
0x180002ad5  mov     eax, [rdi+10h]
0x180002ad8  lea     ecx, [rax+rax]
0x180002adb  add     rcx, rcx; Size
0x180002ade  call    cs:__imp_malloc
0x180002ae4  xor     r8d, r8d
0x180002ae7  mov     [rdi], rax
0x180002aea  mov     rcx, rax
0x180002aed  test    rax, rax
0x180002af0  jz      loc_180002B96
0x180002af6  mov     eax, [rdi+8]
0x180002af9  mov     [rcx+rax*2], bp
0x180002afd  inc     dword ptr [rdi+8]
0x180002b00  add     r14, 2
0x180002b04  cmp     [r14], r8w
0x180002b08  jnz     short loc_180002AA4
0x180002b0a  mov     r12, [rsp+68h+arg_0]
0x180002b0f  cmp     [r14], r8w
0x180002b13  jnz     short loc_180002B19
0x180002b15  test    ebx, ebx
0x180002b17  jnz     short loc_180002B7C
0x180002b19  cmp     [r12+10h], r8d
0x180002b1e  jz      short loc_180002B53
0x180002b20  inc     dword ptr [rdi+0Ch]
0x180002b23  mov     rdx, [rdi]
0x180002b26  test    rdx, rdx
0x180002b29  jnz     short loc_180002B48
0x180002b2b  mov     eax, [rdi+10h]
0x180002b2e  lea     ecx, [rax+rax]
0x180002b31  add     rcx, rcx; Size
0x180002b34  call    cs:__imp_malloc
0x180002b3a  xor     r8d, r8d
0x180002b3d  mov     [rdi], rax
0x180002b40  mov     rdx, rax
0x180002b43  test    rax, rax
0x180002b46  jz      short loc_180002B96
0x180002b48  mov     ecx, [rdi+8]
0x180002b4b  mov     [rdx+rcx*2], r8w
0x180002b50  inc     dword ptr [rdi+8]
0x180002b53  movzx   ebp, word ptr [rsi]
0x180002b56  add     rsi, 2
0x180002b5a  mov     r9d, 2Ah ; '*'
0x180002b60  test    bp, bp
0x180002b63  jnz     loc_180002A3E
0x180002b69  lea     rax, [r15-70h]
0x180002b6d  cmp     [r14], r8w
0x180002b71  jnz     short loc_180002B7C
0x180002b73  mov     [r13+0], rax
0x180002b77  jmp     short loc_180002BA1
0x180002b79  xor     r8d, r8d
0x180002b7c  mov     r15, [r15]
0x180002b7f  lea     rax, [r12+90h]
0x180002b87  cmp     r15, rax
0x180002b8a  jz      short loc_180002B9D
0x180002b8c  mov     rdx, [rsp+68h+arg_8]
0x180002b91  jmp     loc_180002A15
0x180002b96  mov     eax, 80070008h
0x180002b9b  jmp     short loc_180002BA3
0x180002b9d  mov     [r13+0], r8
0x180002ba1  xor     eax, eax
0x180002ba3  mov     rbx, [rsp+68h+arg_10]
0x180002bab  add     rsp, 30h
0x180002baf  pop     r15
0x180002bb1  pop     r14
0x180002bb3  pop     r13
0x180002bb5  pop     r12
0x180002bb7  pop     rdi
0x180002bb8  pop     rsi
0x180002bb9  pop     rbp
0x180002bba  retn
```
