# MatchPathInUrl(ushort const *,ulong,ushort const *)

- ea: `0x18000e660`
- end: `0x18000e901`
- name: `?MatchPathInUrl@@YAPEBGPEBGK0@Z`
- size: `673`
- prototype: `wchar_t *__fastcall(wchar_t *String1, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e420`
- `0x180024480`

## callees

- `0x18000e660`
- `0x18003776a`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000e6c8`
- `msvcrt!wcsrchr` at `0x18000e6e3`
- `msvcrt!wcsrchr` at `0x18000e6c8`
- `msvcrt!wcsrchr` at `0x18000e6e3`

## pseudocode

```c
wchar_t *__fastcall MatchPathInUrl(wchar_t *String1, unsigned int a2, const unsigned __int16 *a3)
{
  unsigned __int16 v3; // r12
  __int64 v4; // r13
  const unsigned __int16 *v5; // r15
  unsigned __int16 v7; // ax
  __int64 v8; // rax
  bool v9; // zf
  wchar_t *v11; // rax
  wchar_t *v12; // rax
  __int64 v13; // rax
  wchar_t *v14; // rbx
  wchar_t *v15; // rsi
  const unsigned __int16 *i; // rdi
  wchar_t v17; // cx
  wchar_t v18; // ax
  const wchar_t *v19; // r14
  wchar_t k; // ax
  wchar_t v21; // ax
  wchar_t *v22; // rdx
  wchar_t j; // ax
  __int64 v24; // rbp
  wchar_t m; // ax

  v3 = *a3;
  v4 = a2;
  v5 = a3;
  if ( *a3 != 42 )
  {
    if ( v3 == 47 )
      v5 = a3 + 1;
LABEL_17:
    v14 = String1 + 1;
    if ( *String1 != 47 )
      v14 = String1;
    v15 = v14;
    while ( 2 )
    {
      i = v5;
      while ( 1 )
      {
        v17 = *i;
        if ( *i == 63 )
        {
          while ( *v14 )
          {
            if ( *v14 == 47 )
              goto LABEL_56;
            v17 = i[1];
            ++i;
            ++v14;
            if ( v17 != 63 )
              goto LABEL_25;
          }
          return 0;
        }
LABEL_25:
        if ( v17 == 42 )
          v18 = i[1];
        else
          v18 = v17;
        v19 = i + 1;
        if ( v17 != 42 )
          v19 = i;
        if ( !v18 )
          break;
        v21 = *v19;
        for ( i = v19; v21 != 42; ++i )
        {
          if ( v21 == 63 )
            break;
          if ( !v21 )
            break;
          v21 = i[1];
        }
        if ( v17 == 42 )
        {
          if ( !*i )
          {
            v22 = &v14[i - v19];
            if ( v22 > &v15[v4] )
              return 0;
            for ( j = *v22; j != 47; ++v14 )
            {
              if ( !j )
                break;
              if ( *v14 == 47 )
                break;
              if ( !*v14 )
                break;
              j = v22[1];
              ++v22;
            }
          }
          v24 = i - v19;
          if ( wcsncmp_0(v14, v19, (unsigned int)v24) )
          {
            while ( *v14 )
            {
              if ( *v14 == 47 )
                goto LABEL_56;
              if ( !wcsncmp_0(++v14, v19, (unsigned int)v24) )
                goto LABEL_54;
            }
            return 0;
          }
        }
        else
        {
          v24 = i - v19;
          if ( wcsncmp_0(v14, v19, (unsigned int)v24) )
            goto LABEL_56;
        }
LABEL_54:
        v14 += v24;
      }
      if ( v17 == 42 )
      {
        for ( k = *v14; k != 47; ++v14 )
        {
          if ( !k )
            break;
          k = v14[1];
        }
      }
      if ( *v14 == 47 || !*v14 )
        return v14;
LABEL_56:
      if ( v3 != 47 )
      {
        for ( m = *v15; m != 47; ++v15 )
        {
          if ( !m )
            break;
          m = v15[1];
        }
        if ( *v15 )
        {
          v14 = ++v15;
          continue;
        }
      }
      return 0;
    }
  }
  v7 = a3[1];
  if ( !v7 )
  {
    v8 = -1;
    do
      v9 = String1[++v8] == 0;
    while ( !v9 );
    return &String1[v8];
  }
  if ( v7 != 46 || a3[2] )
    goto LABEL_17;
  v11 = wcsrchr(String1, 0x2Fu);
  if ( !v11 )
    v11 = String1;
  v12 = wcsrchr(v11, 0x2Eu);
  if ( v12 && v12[1] )
    return 0;
  v13 = -1;
  do
    v9 = String1[++v13] == 0;
  while ( !v9 );
  return &String1[v13];
}

```

## disassembly

```asm
0x18000e660  push    rbx
0x18000e662  push    rbp
0x18000e663  push    rsi
0x18000e664  push    rdi
0x18000e665  push    r12
0x18000e667  push    r13
0x18000e669  push    r14
0x18000e66b  push    r15
0x18000e66d  sub     rsp, 28h
0x18000e671  movzx   r12d, word ptr [r8]
0x18000e675  lea     rax, [r8+2]
0x18000e679  mov     r13d, edx
0x18000e67c  mov     r15, r8
0x18000e67f  mov     rsi, rcx
0x18000e682  cmp     r12w, 2Ah ; '*'
0x18000e687  jnz     loc_18000E725
0x18000e68d  movzx   eax, word ptr [rax]
0x18000e690  test    ax, ax
0x18000e693  jnz     short loc_18000E6B5
0x18000e695  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000e69c  nop     dword ptr [rax+00h]
0x18000e6a0  cmp     word ptr [rcx+rax*2+2], 0
0x18000e6a6  lea     rax, [rax+1]
0x18000e6aa  jnz     short loc_18000E6A0
0x18000e6ac  lea     rax, [rcx+rax*2]
0x18000e6b0  jmp     loc_18000E8EF
0x18000e6b5  cmp     ax, 2Eh ; '.'
0x18000e6b9  jnz     short loc_18000E72E
0x18000e6bb  cmp     word ptr [r8+4], 0
0x18000e6c1  jnz     short loc_18000E72E
0x18000e6c3  mov     edx, 2Fh ; '/'; Ch
0x18000e6c8  call    cs:__imp_wcsrchr
0x18000e6cf  nop     dword ptr [rax+rax+00h]
0x18000e6d4  test    rax, rax
0x18000e6d7  mov     edx, 2Eh ; '.'; Ch
0x18000e6dc  cmovz   rax, rsi
0x18000e6e0  mov     rcx, rax; Str
0x18000e6e3  call    cs:__imp_wcsrchr
0x18000e6ea  nop     dword ptr [rax+rax+00h]
0x18000e6ef  test    rax, rax
0x18000e6f2  jz      short loc_18000E6FF
0x18000e6f4  cmp     word ptr [rax+2], 0
0x18000e6f9  jnz     loc_18000E8ED
0x18000e6ff  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000e706  nop     word ptr [rax+rax+00000000h]
0x18000e710  cmp     word ptr [rsi+rax*2+2], 0
0x18000e716  lea     rax, [rax+1]
0x18000e71a  jnz     short loc_18000E710
0x18000e71c  lea     rax, [rsi+rax*2]
0x18000e720  jmp     loc_18000E8EF
0x18000e725  cmp     r12w, 2Fh ; '/'
0x18000e72a  cmovz   r15, rax
0x18000e72e  cmp     word ptr [rcx], 2Fh ; '/'
0x18000e732  lea     rbx, [rcx+2]
0x18000e736  cmovnz  rbx, rsi
0x18000e73a  mov     rsi, rbx
0x18000e73d  mov     rdi, r15
0x18000e740  movzx   ecx, word ptr [rdi]
0x18000e743  cmp     cx, 3Fh ; '?'
0x18000e747  jnz     short loc_18000E778
0x18000e749  nop     dword ptr [rax+00000000h]
0x18000e750  movzx   eax, word ptr [rbx]
0x18000e753  test    ax, ax
0x18000e756  jz      loc_18000E8ED
0x18000e75c  cmp     ax, 2Fh ; '/'
0x18000e760  jz      loc_18000E8B8
0x18000e766  movzx   ecx, word ptr [rdi+2]
0x18000e76a  add     rdi, 2
0x18000e76e  add     rbx, 2
0x18000e772  cmp     cx, 3Fh ; '?'
0x18000e776  jz      short loc_18000E750
0x18000e778  cmp     cx, 2Ah ; '*'
0x18000e77c  jnz     short loc_18000E784
0x18000e77e  movzx   eax, word ptr [rdi+2]
0x18000e782  jmp     short loc_18000E787
0x18000e784  movzx   eax, cx
0x18000e787  lea     r14, [rdi+2]
0x18000e78b  cmovnz  r14, rdi
0x18000e78f  test    ax, ax
0x18000e792  jnz     short loc_18000E7D0
0x18000e794  cmp     cx, 2Ah ; '*'
0x18000e798  jnz     short loc_18000E7B6
0x18000e79a  movzx   eax, word ptr [rbx]
0x18000e79d  cmp     ax, 2Fh ; '/'
0x18000e7a1  jz      short loc_18000E7B6
0x18000e7a3  test    ax, ax
0x18000e7a6  jz      short loc_18000E7B6
0x18000e7a8  movzx   eax, word ptr [rbx+2]
0x18000e7ac  add     rbx, 2
0x18000e7b0  cmp     ax, 2Fh ; '/'
0x18000e7b4  jnz     short loc_18000E7A3
0x18000e7b6  movzx   eax, word ptr [rbx]
0x18000e7b9  cmp     ax, 2Fh ; '/'
0x18000e7bd  jz      short loc_18000E7C8
0x18000e7bf  test    ax, ax
0x18000e7c2  jnz     loc_18000E8B8
0x18000e7c8  mov     rax, rbx
0x18000e7cb  jmp     loc_18000E8EF
0x18000e7d0  movzx   eax, word ptr [r14]
0x18000e7d4  mov     rdi, r14
0x18000e7d7  cmp     ax, 2Ah ; '*'
0x18000e7db  jz      short loc_18000E7F9
0x18000e7dd  nop     dword ptr [rax]
0x18000e7e0  cmp     ax, 3Fh ; '?'
0x18000e7e4  jz      short loc_18000E7F9
0x18000e7e6  test    ax, ax
0x18000e7e9  jz      short loc_18000E7F9
0x18000e7eb  movzx   eax, word ptr [rdi+2]
0x18000e7ef  add     rdi, 2
0x18000e7f3  cmp     ax, 2Ah ; '*'
0x18000e7f7  jnz     short loc_18000E7E0
0x18000e7f9  cmp     cx, 2Ah ; '*'
0x18000e7fd  jnz     loc_18000E89D
0x18000e803  cmp     word ptr [rdi], 0
0x18000e807  jnz     short loc_18000E855
0x18000e809  mov     rax, rdi
0x18000e80c  lea     rcx, [rsi+r13*2]
0x18000e810  sub     rax, r14
0x18000e813  sar     rax, 1
0x18000e816  lea     rdx, [rbx+rax*2]
0x18000e81a  cmp     rdx, rcx
0x18000e81d  ja      loc_18000E8ED
0x18000e823  movzx   eax, word ptr [rdx]
0x18000e826  cmp     ax, 2Fh ; '/'
0x18000e82a  jz      short loc_18000E855
0x18000e82c  nop     dword ptr [rax+00h]
0x18000e830  test    ax, ax
0x18000e833  jz      short loc_18000E855
0x18000e835  movzx   eax, word ptr [rbx]
0x18000e838  cmp     ax, 2Fh ; '/'
0x18000e83c  jz      short loc_18000E855
0x18000e83e  test    ax, ax
0x18000e841  jz      short loc_18000E855
0x18000e843  movzx   eax, word ptr [rdx+2]
0x18000e847  add     rdx, 2
0x18000e84b  add     rbx, 2
0x18000e84f  cmp     ax, 2Fh ; '/'
0x18000e853  jnz     short loc_18000E830
0x18000e855  mov     rbp, rdi
0x18000e858  mov     rdx, r14; String2
0x18000e85b  sub     rbp, r14
0x18000e85e  mov     rcx, rbx; String1
0x18000e861  sar     rbp, 1
0x18000e864  mov     r8d, ebp; MaxCount
0x18000e867  call    wcsncmp_0
0x18000e86c  test    eax, eax
0x18000e86e  jz      short loc_18000E894
0x18000e870  movzx   eax, word ptr [rbx]
0x18000e873  test    ax, ax
0x18000e876  jz      short loc_18000E8ED
0x18000e878  cmp     ax, 2Fh ; '/'
0x18000e87c  jz      short loc_18000E8B8
0x18000e87e  add     rbx, 2
0x18000e882  mov     r8d, ebp; MaxCount
0x18000e885  mov     rcx, rbx; String1
0x18000e888  mov     rdx, r14; String2
0x18000e88b  call    wcsncmp_0
0x18000e890  test    eax, eax
0x18000e892  jnz     short loc_18000E870
0x18000e894  lea     rbx, [rbx+rbp*2]
0x18000e898  jmp     loc_18000E740
0x18000e89d  mov     rbp, rdi
0x18000e8a0  mov     rdx, r14; String2
0x18000e8a3  sub     rbp, r14
0x18000e8a6  mov     rcx, rbx; String1
0x18000e8a9  sar     rbp, 1
0x18000e8ac  mov     r8d, ebp; MaxCount
0x18000e8af  call    wcsncmp_0
0x18000e8b4  test    eax, eax
0x18000e8b6  jz      short loc_18000E894
0x18000e8b8  cmp     r12w, 2Fh ; '/'
0x18000e8bd  jz      short loc_18000E8ED
0x18000e8bf  movzx   eax, word ptr [rsi]
0x18000e8c2  cmp     ax, 2Fh ; '/'
0x18000e8c6  jz      short loc_18000E8DB
0x18000e8c8  test    ax, ax
0x18000e8cb  jz      short loc_18000E8DB
0x18000e8cd  movzx   eax, word ptr [rsi+2]
0x18000e8d1  add     rsi, 2
0x18000e8d5  cmp     ax, 2Fh ; '/'
0x18000e8d9  jnz     short loc_18000E8C8
0x18000e8db  cmp     word ptr [rsi], 0
0x18000e8df  jz      short loc_18000E8ED
0x18000e8e1  add     rsi, 2
0x18000e8e5  mov     rbx, rsi
0x18000e8e8  jmp     loc_18000E73D
0x18000e8ed  xor     eax, eax
0x18000e8ef  add     rsp, 28h
0x18000e8f3  pop     r15
0x18000e8f5  pop     r14
0x18000e8f7  pop     r13
0x18000e8f9  pop     r12
0x18000e8fb  pop     rdi
0x18000e8fc  pop     rsi
0x18000e8fd  pop     rbp
0x18000e8fe  pop     rbx
0x18000e8ff  retn
```
