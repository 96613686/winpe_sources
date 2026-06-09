# GetString

- ea: `0x180001c04`
- end: `0x180001d80`
- name: `GetString`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002500`

## callees

- `0x1800018d8`
- `0x180001c04`
- `0x180001d88`

## import_xrefs

- `msvcrt!iswspace` at `0x180001c2b`
- `msvcrt!iswspace` at `0x180001cd6`
- `msvcrt!iswspace` at `0x180001c2b`
- `msvcrt!iswspace` at `0x180001cd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001d5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001d5e`

## pseudocode

```c
__int64 __fastcall GetString(wint_t **a1, __int64 a2)
{
  wint_t *v2; // rax
  wint_t v5; // ax
  int v6; // ebx
  const unsigned __int16 *v7; // rcx
  unsigned __int16 v8; // ax
  wint_t *v9; // rax
  HLOCAL hMem; // [rsp+40h] [rbp+20h] BYREF
  wint_t *v12; // [rsp+50h] [rbp+30h] BYREF

  v2 = *a1;
  hMem = 0;
  while ( *v2 && iswspace(*v2) )
    v2 = ++*a1;
  v5 = **a1;
  if ( v5 )
  {
    if ( v5 == 34 )
    {
      v7 = *a1 + 1;
      *a1 = (wint_t *)v7;
      v12 = (wint_t *)v7;
      while ( 1 )
      {
        v8 = *v7;
        if ( !*v7 || v8 == 34 )
          break;
        if ( v8 == 92 )
        {
          v6 = HandleBackslash(a1, &v12, &hMem);
          if ( v6 < 0 )
            goto LABEL_31;
        }
        else
        {
          *a1 = (wint_t *)(v7 + 1);
        }
        v7 = *a1;
      }
      if ( !*v7 )
        goto LABEL_6;
      v6 = ComposeFinalArgument((__int64)v7, v12, &hMem);
      if ( v6 < 0 )
        goto LABEL_31;
      ++*a1;
    }
    else
    {
      v12 = *a1;
      do
      {
        if ( iswspace(v5) )
          break;
        v9 = *a1;
        if ( **a1 == 92 )
        {
          v6 = HandleBackslash(a1, &v12, &hMem);
          if ( v6 < 0 )
            goto LABEL_31;
        }
        else
        {
          if ( *v9 == 34 )
            goto LABEL_6;
          *a1 = v9 + 1;
        }
        v5 = **a1;
      }
      while ( v5 );
      if ( *a1 == v12 && !hMem )
        goto LABEL_6;
      v6 = ComposeFinalArgument((__int64)*a1, v12, &hMem);
      if ( v6 < 0 )
        goto LABEL_31;
    }
    *(_QWORD *)(a2 + 8) = hMem;
    *(_DWORD *)a2 = 1;
    hMem = 0;
    goto LABEL_31;
  }
LABEL_6:
  v6 = -2147467259;
LABEL_31:
  LocalFree(hMem);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180001c04  mov     [rsp-18h+arg_8], rbx
0x180001c09  mov     [rsp-18h+arg_18], rsi
0x180001c0e  push    rbp
0x180001c0f  push    rdi
0x180001c10  push    r14
0x180001c12  mov     rbp, rsp
0x180001c15  sub     rsp, 20h
0x180001c19  mov     rax, [rcx]
0x180001c1c  xor     r14d, r14d
0x180001c1f  mov     [rbp+hMem], r14
0x180001c23  mov     rsi, rdx
0x180001c26  mov     rdi, rcx
0x180001c29  jmp     short loc_180001C42
0x180001c2b  call    cs:__imp_iswspace
0x180001c32  nop     dword ptr [rax+rax+00h]
0x180001c37  test    eax, eax
0x180001c39  jz      short loc_180001C4A
0x180001c3b  add     qword ptr [rdi], 2
0x180001c3f  mov     rax, [rdi]
0x180001c42  movzx   ecx, word ptr [rax]; C
0x180001c45  test    cx, cx
0x180001c48  jnz     short loc_180001C2B
0x180001c4a  mov     rcx, [rdi]
0x180001c4d  movzx   eax, word ptr [rcx]
0x180001c50  test    ax, ax
0x180001c53  jnz     short loc_180001C5F
0x180001c55  mov     ebx, 80004005h
0x180001c5a  jmp     loc_180001D5A
0x180001c5f  cmp     ax, 22h ; '"'
0x180001c63  jnz     short loc_180001CCF
0x180001c65  add     rcx, 2
0x180001c69  mov     [rdi], rcx
0x180001c6c  mov     [rbp+arg_10], rcx
0x180001c70  jmp     short loc_180001CA4
0x180001c72  cmp     ax, 22h ; '"'
0x180001c76  jz      short loc_180001CAC
0x180001c78  cmp     ax, 5Ch ; '\'
0x180001c7c  jnz     short loc_180001C9A
0x180001c7e  lea     r8, [rbp+hMem]
0x180001c82  mov     rcx, rdi
0x180001c85  lea     rdx, [rbp+arg_10]
0x180001c89  call    HandleBackslash
0x180001c8e  mov     ebx, eax
0x180001c90  test    eax, eax
0x180001c92  js      loc_180001D5A
0x180001c98  jmp     short loc_180001CA1
0x180001c9a  lea     rax, [rcx+2]
0x180001c9e  mov     [rdi], rax
0x180001ca1  mov     rcx, [rdi]
0x180001ca4  movzx   eax, word ptr [rcx]
0x180001ca7  test    ax, ax
0x180001caa  jnz     short loc_180001C72
0x180001cac  cmp     [rcx], r14w
0x180001cb0  jz      short loc_180001C55
0x180001cb2  mov     rdx, [rbp+arg_10]
0x180001cb6  lea     r8, [rbp+hMem]
0x180001cba  call    ComposeFinalArgument
0x180001cbf  mov     ebx, eax
0x180001cc1  test    eax, eax
0x180001cc3  js      loc_180001D5A
0x180001cc9  add     qword ptr [rdi], 2
0x180001ccd  jmp     short loc_180001D48
0x180001ccf  mov     [rbp+arg_10], rcx
0x180001cd3  movzx   ecx, ax; C
0x180001cd6  call    cs:__imp_iswspace
0x180001cdd  nop     dword ptr [rax+rax+00h]
0x180001ce2  test    eax, eax
0x180001ce4  jnz     short loc_180001D23
0x180001ce6  mov     rax, [rdi]
0x180001ce9  cmp     word ptr [rax], 5Ch ; '\'
0x180001ced  jnz     short loc_180001D07
0x180001cef  lea     r8, [rbp+hMem]
0x180001cf3  mov     rcx, rdi
0x180001cf6  lea     rdx, [rbp+arg_10]
0x180001cfa  call    HandleBackslash
0x180001cff  mov     ebx, eax
0x180001d01  test    eax, eax
0x180001d03  js      short loc_180001D5A
0x180001d05  jmp     short loc_180001D18
0x180001d07  cmp     word ptr [rax], 22h ; '"'
0x180001d0b  jz      loc_180001C55
0x180001d11  add     rax, 2
0x180001d15  mov     [rdi], rax
0x180001d18  mov     rax, [rdi]
0x180001d1b  movzx   eax, word ptr [rax]
0x180001d1e  test    ax, ax
0x180001d21  jnz     short loc_180001CD3
0x180001d23  mov     rdx, [rbp+arg_10]
0x180001d27  cmp     [rdi], rdx
0x180001d2a  jnz     short loc_180001D36
0x180001d2c  cmp     [rbp+hMem], r14
0x180001d30  jz      loc_180001C55
0x180001d36  mov     rcx, [rdi]
0x180001d39  lea     r8, [rbp+hMem]
0x180001d3d  call    ComposeFinalArgument
0x180001d42  mov     ebx, eax
0x180001d44  test    eax, eax
0x180001d46  js      short loc_180001D5A
0x180001d48  mov     rax, [rbp+hMem]
0x180001d4c  mov     [rsi+8], rax
0x180001d50  mov     dword ptr [rsi], 1
0x180001d56  mov     [rbp+hMem], r14
0x180001d5a  mov     rcx, [rbp+hMem]; hMem
0x180001d5e  call    cs:__imp_LocalFree
0x180001d65  nop     dword ptr [rax+rax+00h]
0x180001d6a  mov     rsi, [rsp+20h+arg_18]
0x180001d6f  mov     eax, ebx
0x180001d71  mov     rbx, [rsp+20h+arg_8]
0x180001d76  add     rsp, 20h
0x180001d7a  pop     r14
0x180001d7c  pop     rdi
0x180001d7d  pop     rbp
0x180001d7e  retn
```
