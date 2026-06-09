# std::equal_range<SupportedKnownFolder const *,std::basic_string_view<ushort,std::char_traits<ushort>>,std::less<void>>(SupportedKnownFolder const *,SupportedKnownFolder const *,std::basic_string_view<ushort,std::char_traits<ushort>> const &,std::less<void>)

- ea: `0x18009b01c`
- end: `0x18009b241`
- name: `??$equal_range@PEBUSupportedKnownFolder@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@U?$less@X@3@@std@@YA?AU?$pair@PEBUSupportedKnownFolder@@PEBU1@@0@PEBUSupportedKnownFolder@@0AEBV?$basic_string_view@GU?$char_traits@G@std@@@0@U?$less@X@0@@Z`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18009b714`

## callees

- `0x18009b01c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009b09b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009b0de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009b179`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009b211`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009b09b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009b0de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009b179`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009b211`

## pseudocode

```c
const WCHAR ***__fastcall std::equal_range<SupportedKnownFolder const *,std::basic_string_view<unsigned short>,std::less<void>>(
        const WCHAR ***a1,
        const WCHAR **a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // r13
  const WCHAR **v5; // rsi
  unsigned __int64 v6; // rbx
  const WCHAR ***v7; // r12
  __int64 v8; // rdx
  __int64 v9; // rdi
  const WCHAR **v10; // rbp
  const WCHAR *v11; // rcx
  const WCHAR *v12; // r8
  __int64 v13; // r9
  const WCHAR **v14; // r14
  const WCHAR **v15; // r15
  const WCHAR ***result; // rax
  signed __int64 v17; // rdi
  __int64 v18; // rdx
  const WCHAR **v19; // r13
  const WCHAR *v20; // rcx
  unsigned __int64 v21; // rbx
  __int64 v22; // r9
  const WCHAR **v23; // rsi
  const WCHAR *v24; // r8

  v4 = a4;
  v5 = a2;
  v6 = 0xAAAAAAAAAAAAAAABuLL * ((a3 - (__int64)a2) >> 3);
  v7 = a1;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( (__int64)v6 <= 0 )
      {
        v14 = v5;
        v15 = v5;
        goto LABEL_12;
      }
      v8 = -1;
      v9 = 3 * (v6 >> 1);
      v10 = &v5[v9];
      v11 = v5[v9];
      do
        ++v8;
      while ( v11[v8] );
      if ( CompareStringOrdinal(v11, v8, *(LPCWCH *)v4, *(_DWORD *)(v4 + 8), 1) != 1 )
        break;
      v5 = v10 + 3;
      v6 += -1LL - (v6 >> 1);
    }
    v12 = *v10;
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    if ( CompareStringOrdinal(*(LPCWCH *)v4, *(_DWORD *)(v4 + 8), v12, v13, 1) != 1 )
      break;
    v6 >>= 1;
  }
  v17 = 0xAAAAAAAAAAAAAAABuLL * ((v9 * 8) >> 3);
  v15 = v5;
  if ( v17 > 0 )
  {
    do
    {
      v18 = -1;
      v19 = &v15[3 * ((unsigned __int64)v17 >> 1)];
      v20 = *v19;
      do
        ++v18;
      while ( v20[v18] );
      if ( CompareStringOrdinal(v20, v18, *(LPCWCH *)a4, *(_DWORD *)(a4 + 8), 1) == 1 )
      {
        v15 = v19 + 3;
        v17 += -1LL - ((unsigned __int64)v17 >> 1);
      }
      else
      {
        v17 = (unsigned __int64)v17 >> 1;
      }
    }
    while ( v17 > 0 );
    v7 = a1;
    v4 = a4;
  }
  v14 = v10 + 3;
  v21 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)((__int64)v5 + 24 * v6 - (_QWORD)(v10 + 3)) >> 3);
  while ( (__int64)v21 > 0 )
  {
    v22 = -1;
    v23 = &v14[3 * (v21 >> 1)];
    v24 = *v23;
    do
      ++v22;
    while ( v24[v22] );
    if ( CompareStringOrdinal(*(LPCWCH *)v4, *(_DWORD *)(v4 + 8), v24, v22, 1) == 1 )
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
  result = v7;
  *v7 = v15;
  v7[1] = v14;
  return result;
}

```

## disassembly

```asm
0x18009b01c  mov     [rsp+arg_8], rbx
0x18009b021  mov     [rsp+arg_18], r9
0x18009b026  mov     [rsp+arg_0], rcx
0x18009b02b  push    rbp
0x18009b02c  push    rsi
0x18009b02d  push    rdi
0x18009b02e  push    r12
0x18009b030  push    r13
0x18009b032  push    r14
0x18009b034  push    r15
0x18009b036  sub     rsp, 30h
0x18009b03a  mov     rbx, r8
0x18009b03d  mov     rax, 0AAAAAAAAAAAAAAABh
0x18009b047  sub     rbx, rdx
0x18009b04a  mov     r13, r9
0x18009b04d  sar     rbx, 3
0x18009b051  mov     rsi, rdx
0x18009b054  imul    rbx, rax
0x18009b058  xor     r15d, r15d
0x18009b05b  mov     r12, rcx
0x18009b05e  jmp     loc_18009B0F2
0x18009b063  mov     r14, rbx
0x18009b066  shr     r14, 1
0x18009b069  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18009b06d  lea     rax, [r14+r14*2]
0x18009b071  lea     rdi, ds:0[rax*8]
0x18009b079  lea     rbp, [rdi+rsi]
0x18009b07d  mov     rcx, [rbp+0]; lpString1
0x18009b081  inc     rdx; cchCount1
0x18009b084  cmp     [rcx+rdx*2], r15w
0x18009b089  jnz     short loc_18009B081
0x18009b08b  mov     r9d, [r13+8]; cchCount2
0x18009b08f  mov     r8, [r13+0]; lpString2
0x18009b093  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x18009b09b  call    cs:__imp_CompareStringOrdinal
0x18009b0a2  nop     dword ptr [rax+rax+00h]
0x18009b0a7  cmp     eax, 1
0x18009b0aa  jnz     short loc_18009B0BC
0x18009b0ac  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009b0b0  lea     rsi, [rbp+18h]
0x18009b0b4  sub     rax, r14
0x18009b0b7  add     rbx, rax
0x18009b0ba  jmp     short loc_18009B0F2
0x18009b0bc  mov     r8, [rbp+0]; lpString2
0x18009b0c0  or      r9, 0FFFFFFFFFFFFFFFFh
0x18009b0c4  inc     r9; cchCount2
0x18009b0c7  cmp     [r8+r9*2], r15w
0x18009b0cc  jnz     short loc_18009B0C4
0x18009b0ce  mov     edx, [r13+8]; cchCount1
0x18009b0d2  mov     rcx, [r13+0]; lpString1
0x18009b0d6  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x18009b0de  call    cs:__imp_CompareStringOrdinal
0x18009b0e5  nop     dword ptr [rax+rax+00h]
0x18009b0ea  cmp     eax, 1
0x18009b0ed  jnz     short loc_18009B123
0x18009b0ef  mov     rbx, r14
0x18009b0f2  test    rbx, rbx
0x18009b0f5  jg      loc_18009B063
0x18009b0fb  mov     r14, rsi
0x18009b0fe  mov     r15, rsi
0x18009b101  mov     rbx, [rsp+68h+arg_8]
0x18009b106  mov     rax, r12
0x18009b109  mov     [r12], r15
0x18009b10d  mov     [r12+8], r14
0x18009b112  add     rsp, 30h
0x18009b116  pop     r15
0x18009b118  pop     r14
0x18009b11a  pop     r13
0x18009b11c  pop     r12
0x18009b11e  pop     rdi
0x18009b11f  pop     rsi
0x18009b120  pop     rbp
0x18009b121  retn
0x18009b123  sar     rdi, 3
0x18009b127  mov     rax, 0AAAAAAAAAAAAAAABh
0x18009b131  imul    rdi, rax
0x18009b135  xor     r10d, r10d
0x18009b138  mov     r15, rsi
0x18009b13b  test    rdi, rdi
0x18009b13e  jle     short loc_18009B1BC
0x18009b140  mov     r12, [rsp+68h+arg_18]
0x18009b148  mov     r14, rdi
0x18009b14b  shr     r14, 1
0x18009b14e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18009b152  lea     rax, [r14+r14*2]
0x18009b156  lea     r13, [r15+rax*8]
0x18009b15a  mov     rcx, [r13+0]; lpString1
0x18009b15e  inc     rdx; cchCount1
0x18009b161  cmp     [rcx+rdx*2], r10w
0x18009b166  jnz     short loc_18009B15E
0x18009b168  mov     r9d, [r12+8]; cchCount2
0x18009b16d  mov     r8, [r12]; lpString2
0x18009b171  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x18009b179  call    cs:__imp_CompareStringOrdinal
0x18009b180  nop     dword ptr [rax+rax+00h]
0x18009b185  cmp     eax, 1
0x18009b188  jnz     short loc_18009B19A
0x18009b18a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009b18e  lea     r15, [r13+18h]
0x18009b192  sub     rax, r14
0x18009b195  add     rdi, rax
0x18009b198  jmp     short loc_18009B19D
0x18009b19a  mov     rdi, r14
0x18009b19d  xor     r10d, r10d
0x18009b1a0  test    rdi, rdi
0x18009b1a3  jg      short loc_18009B148
0x18009b1a5  mov     r12, [rsp+68h+arg_0]
0x18009b1aa  mov     rax, 0AAAAAAAAAAAAAAABh
0x18009b1b4  mov     r13, [rsp+68h+arg_18]
0x18009b1bc  lea     rbx, [rbx+rbx*2]
0x18009b1c0  shl     rbx, 3
0x18009b1c4  lea     r14, [rbp+18h]
0x18009b1c8  sub     rbx, r14
0x18009b1cb  add     rbx, rsi
0x18009b1ce  sar     rbx, 3
0x18009b1d2  imul    rbx, rax
0x18009b1d6  test    rbx, rbx
0x18009b1d9  jle     loc_18009B101
0x18009b1df  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18009b1e3  mov     rdi, rbx
0x18009b1e6  mov     r9, rbp
0x18009b1e9  shr     rdi, 1
0x18009b1ec  lea     rax, [rdi+rdi*2]
0x18009b1f0  lea     rsi, [r14+rax*8]
0x18009b1f4  mov     r8, [rsi]; lpString2
0x18009b1f7  inc     r9; cchCount2
0x18009b1fa  cmp     [r8+r9*2], r10w
0x18009b1ff  jnz     short loc_18009B1F7
0x18009b201  mov     edx, [r13+8]; cchCount1
0x18009b205  mov     rcx, [r13+0]; lpString1
0x18009b209  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x18009b211  call    cs:__imp_CompareStringOrdinal
0x18009b218  nop     dword ptr [rax+rax+00h]
0x18009b21d  cmp     eax, 1
0x18009b220  jnz     short loc_18009B227
0x18009b222  mov     rbx, rdi
0x18009b225  jmp     short loc_18009B234
0x18009b227  mov     rax, rbp
0x18009b22a  lea     r14, [rsi+18h]
0x18009b22e  sub     rax, rdi
0x18009b231  add     rbx, rax
0x18009b234  xor     r10d, r10d
0x18009b237  test    rbx, rbx
0x18009b23a  jg      short loc_18009B1E3
0x18009b23c  jmp     loc_18009B101
```
