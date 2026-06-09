# std::equal_range<SupportedKnownFolder const *,std::basic_string_view<ushort,std::char_traits<ushort>>,std::less<void>>(SupportedKnownFolder const *,SupportedKnownFolder const *,std::basic_string_view<ushort,std::char_traits<ushort>> const &,std::less<void>)

- ea: `0x18009c998`
- end: `0x18009cb94`
- name: `??$equal_range@PEBUSupportedKnownFolder@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@U?$less@X@3@@std@@YA?AU?$pair@PEBUSupportedKnownFolder@@PEBU1@@0@PEBUSupportedKnownFolder@@0AEBV?$basic_string_view@GU?$char_traits@G@std@@@0@U?$less@X@0@@Z`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18009d154`

## callees

- `0x18009c998`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009ca11`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009ca52`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009cadd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009cb66`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009ca11`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009ca52`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009cadd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009cb66`

## pseudocode

```c
const WCHAR ***__fastcall std::equal_range<SupportedKnownFolder const *,std::basic_string_view<unsigned short>,std::less<void>>(
        const WCHAR ***a1,
        const WCHAR **a2,
        __int64 a3,
        __int64 a4)
{
  const WCHAR **v5; // rsi
  unsigned __int64 i; // rbx
  __int64 v8; // rdx
  __int64 v9; // rdi
  const WCHAR **v10; // r15
  const WCHAR *v11; // rcx
  const WCHAR *v12; // r8
  __int64 v13; // r9
  const WCHAR **v14; // rdi
  const WCHAR **v15; // r15
  const WCHAR ***result; // rax
  unsigned __int64 v17; // rdi
  __int64 v18; // rdx
  const WCHAR **v19; // r12
  const WCHAR *v20; // rcx
  unsigned __int64 v21; // rbx
  __int64 v22; // r9
  const WCHAR **v23; // r14
  const WCHAR *v24; // r8
  const WCHAR **v25; // [rsp+80h] [rbp+8h]

  v5 = a2;
  for ( i = 0xAAAAAAAAAAAAAAABuLL * ((a3 - (__int64)a2) >> 3); ; i >>= 1 )
  {
    while ( 1 )
    {
      if ( (__int64)i <= 0 )
      {
        v14 = v5;
        v15 = v5;
        goto LABEL_12;
      }
      v8 = -1;
      v9 = 3 * (i >> 1);
      v10 = &v5[v9];
      v11 = v5[v9];
      v25 = &v5[v9];
      do
        ++v8;
      while ( v11[v8] );
      if ( CompareStringOrdinal(v11, v8, *(LPCWCH *)a4, *(_DWORD *)(a4 + 8), 1) != 1 )
        break;
      v5 = v10 + 3;
      i += -1LL - (i >> 1);
    }
    v12 = *v10;
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    if ( CompareStringOrdinal(*(LPCWCH *)a4, *(_DWORD *)(a4 + 8), v12, v13, 1) != 1 )
      break;
  }
  v17 = 0xAAAAAAAAAAAAAAABuLL * ((v9 * 8) >> 3);
  v15 = v5;
  while ( (__int64)v17 > 0 )
  {
    v18 = -1;
    v19 = &v15[3 * (v17 >> 1)];
    v20 = *v19;
    do
      ++v18;
    while ( v20[v18] );
    if ( CompareStringOrdinal(v20, v18, *(LPCWCH *)a4, *(_DWORD *)(a4 + 8), 1) == 1 )
    {
      v15 = v19 + 3;
      v17 += -1LL - (v17 >> 1);
    }
    else
    {
      v17 >>= 1;
    }
  }
  v14 = v25 + 3;
  v21 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)((__int64)v5 + 24 * i - (_QWORD)(v25 + 3)) >> 3);
  while ( (__int64)v21 > 0 )
  {
    v22 = -1;
    v23 = &v14[3 * (v21 >> 1)];
    v24 = *v23;
    do
      ++v22;
    while ( v24[v22] );
    if ( CompareStringOrdinal(*(LPCWCH *)a4, *(_DWORD *)(a4 + 8), v24, v22, 1) == 1 )
    {
      v21 >>= 1;
    }
    else
    {
      v14 = v23 + 3;
      v21 += -1LL - (v21 >> 1);
    }
  }
LABEL_12:
  *a1 = v15;
  result = a1;
  a1[1] = v14;
  return result;
}

```

## disassembly

```asm
0x18009c998  push    rbx
0x18009c99a  push    rbp
0x18009c99b  push    rsi
0x18009c99c  push    rdi
0x18009c99d  push    r12
0x18009c99f  push    r13
0x18009c9a1  push    r14
0x18009c9a3  push    r15
0x18009c9a5  sub     rsp, 38h
0x18009c9a9  mov     rbx, r8
0x18009c9ac  mov     rax, 0AAAAAAAAAAAAAAABh
0x18009c9b6  sub     rbx, rdx
0x18009c9b9  mov     rbp, r9
0x18009c9bc  sar     rbx, 3
0x18009c9c0  mov     rsi, rdx
0x18009c9c3  imul    rbx, rax
0x18009c9c7  xor     r12d, r12d
0x18009c9ca  mov     r13, rcx
0x18009c9cd  jmp     loc_18009CA66
0x18009c9d2  mov     r14, rbx
0x18009c9d5  shr     r14, 1
0x18009c9d8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18009c9dc  lea     rax, [r14+r14*2]
0x18009c9e0  lea     rdi, ds:0[rax*8]
0x18009c9e8  lea     r15, [rdi+rsi]
0x18009c9ec  mov     rcx, [r15]; lpString1
0x18009c9ef  mov     [rsp+78h+arg_0], r15
0x18009c9f7  inc     rdx; cchCount1
0x18009c9fa  cmp     [rcx+rdx*2], r12w
0x18009c9ff  jnz     short loc_18009C9F7
0x18009ca01  mov     r9d, [rbp+8]; cchCount2
0x18009ca05  mov     r8, [rbp+0]; lpString2
0x18009ca09  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18009ca11  call    cs:__imp_CompareStringOrdinal
0x18009ca18  nop     dword ptr [rax+rax+00h]
0x18009ca1d  cmp     eax, 1
0x18009ca20  jnz     short loc_18009CA32
0x18009ca22  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009ca26  lea     rsi, [r15+18h]
0x18009ca2a  sub     rax, r14
0x18009ca2d  add     rbx, rax
0x18009ca30  jmp     short loc_18009CA66
0x18009ca32  mov     r8, [r15]; lpString2
0x18009ca35  or      r9, 0FFFFFFFFFFFFFFFFh
0x18009ca39  inc     r9; cchCount2
0x18009ca3c  cmp     [r8+r9*2], r12w
0x18009ca41  jnz     short loc_18009CA39
0x18009ca43  mov     edx, [rbp+8]; cchCount1
0x18009ca46  mov     rcx, [rbp+0]; lpString1
0x18009ca4a  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18009ca52  call    cs:__imp_CompareStringOrdinal
0x18009ca59  nop     dword ptr [rax+rax+00h]
0x18009ca5e  cmp     eax, 1
0x18009ca61  jnz     short loc_18009CA92
0x18009ca63  mov     rbx, r14
0x18009ca66  test    rbx, rbx
0x18009ca69  jg      loc_18009C9D2
0x18009ca6f  mov     rdi, rsi
0x18009ca72  mov     r15, rsi
0x18009ca75  mov     [r13+0], r15
0x18009ca79  mov     rax, r13
0x18009ca7c  mov     [r13+8], rdi
0x18009ca80  add     rsp, 38h
0x18009ca84  pop     r15
0x18009ca86  pop     r14
0x18009ca88  pop     r13
0x18009ca8a  pop     r12
0x18009ca8c  pop     rdi
0x18009ca8d  pop     rsi
0x18009ca8e  pop     rbp
0x18009ca8f  pop     rbx
0x18009ca90  retn
0x18009ca92  sar     rdi, 3
0x18009ca96  mov     rax, 0AAAAAAAAAAAAAAABh
0x18009caa0  imul    rdi, rax
0x18009caa4  mov     r15, rsi
0x18009caa7  test    rdi, rdi
0x18009caaa  jle     short loc_18009CB14
0x18009caac  mov     r14, rdi
0x18009caaf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18009cab3  shr     r14, 1
0x18009cab6  lea     rax, [r14+r14*2]
0x18009caba  lea     r12, [r15+rax*8]
0x18009cabe  xor     eax, eax
0x18009cac0  mov     rcx, [r12]; lpString1
0x18009cac4  inc     rdx; cchCount1
0x18009cac7  cmp     [rcx+rdx*2], ax
0x18009cacb  jnz     short loc_18009CAC4
0x18009cacd  mov     r9d, [rbp+8]; cchCount2
0x18009cad1  mov     r8, [rbp+0]; lpString2
0x18009cad5  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18009cadd  call    cs:__imp_CompareStringOrdinal
0x18009cae4  nop     dword ptr [rax+rax+00h]
0x18009cae9  cmp     eax, 1
0x18009caec  jnz     short loc_18009CAFF
0x18009caee  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009caf2  lea     r15, [r12+18h]
0x18009caf7  sub     rax, r14
0x18009cafa  add     rdi, rax
0x18009cafd  jmp     short loc_18009CB02
0x18009caff  mov     rdi, r14
0x18009cb02  xor     r12d, r12d
0x18009cb05  test    rdi, rdi
0x18009cb08  jg      short loc_18009CAAC
0x18009cb0a  mov     rax, 0AAAAAAAAAAAAAAABh
0x18009cb14  mov     rdi, [rsp+78h+arg_0]
0x18009cb1c  lea     rbx, [rbx+rbx*2]
0x18009cb20  shl     rbx, 3
0x18009cb24  add     rdi, 18h
0x18009cb28  sub     rbx, rdi
0x18009cb2b  add     rbx, rsi
0x18009cb2e  sar     rbx, 3
0x18009cb32  imul    rbx, rax
0x18009cb36  jmp     short loc_18009CB8A
0x18009cb38  mov     rsi, rbx
0x18009cb3b  shr     rsi, 1
0x18009cb3e  or      r9, 0FFFFFFFFFFFFFFFFh
0x18009cb42  lea     rax, [rsi+rsi*2]
0x18009cb46  lea     r14, [rdi+rax*8]
0x18009cb4a  mov     r8, [r14]; lpString2
0x18009cb4d  inc     r9; cchCount2
0x18009cb50  cmp     [r8+r9*2], r12w
0x18009cb55  jnz     short loc_18009CB4D
0x18009cb57  mov     edx, [rbp+8]; cchCount1
0x18009cb5a  mov     rcx, [rbp+0]; lpString1
0x18009cb5e  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18009cb66  call    cs:__imp_CompareStringOrdinal
0x18009cb6d  nop     dword ptr [rax+rax+00h]
0x18009cb72  cmp     eax, 1
0x18009cb75  jnz     short loc_18009CB7C
0x18009cb77  mov     rbx, rsi
0x18009cb7a  jmp     short loc_18009CB8A
0x18009cb7c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009cb80  lea     rdi, [r14+18h]
0x18009cb84  sub     rax, rsi
0x18009cb87  add     rbx, rax
0x18009cb8a  test    rbx, rbx
0x18009cb8d  jg      short loc_18009CB38
0x18009cb8f  jmp     loc_18009CA75
```
