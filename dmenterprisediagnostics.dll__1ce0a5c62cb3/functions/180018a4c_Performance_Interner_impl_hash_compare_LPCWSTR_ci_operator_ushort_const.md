# Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)

- ea: `0x180018a4c`
- end: `0x180018ac9`
- name: `??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z`
- size: `125`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018328`
- `0x18001a3c0`
- `0x18001a5d0`

## callees

- `0x180018a4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180018a78`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180018a78`

## pseudocode

```c
__int64 __fastcall Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(__int64 a1, unsigned __int16 *a2)
{
  __int64 v2; // rax
  unsigned __int16 *v3; // rbx
  unsigned __int16 *v4; // rsi
  int v5; // edi
  unsigned __int16 v6; // ax
  int v7; // ecx
  __int64 result; // rax

  v2 = -1;
  v3 = a2;
  do
    ++v2;
  while ( a2[v2] );
  v4 = &a2[v2];
  v5 = -2128831035;
  if ( a2 != v4 )
  {
    do
    {
      v6 = _o_towlower(*v3++);
      v5 = v6 ^ (16777619 * v5);
    }
    while ( v3 != v4 );
  }
  v7 = 16807 * v5 - 0x7FFFFFFF * (v5 / 127773);
  LODWORD(result) = v7 + 0x7FFFFFFF;
  if ( v7 >= 0 )
    LODWORD(result) = 16807 * v5 - 0x7FFFFFFF * (v5 / 127773);
  return (int)result;
}

```

## disassembly

```asm
0x180018a4c  push    rbx
0x180018a4e  push    rbp
0x180018a4f  push    rsi
0x180018a50  push    rdi
0x180018a51  sub     rsp, 28h
0x180018a55  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018a59  mov     rbx, rdx
0x180018a5c  xor     ebp, ebp
0x180018a5e  inc     rax
0x180018a61  cmp     [rdx+rax*2], bp
0x180018a65  jnz     short loc_180018A5E
0x180018a67  lea     rsi, [rdx+rax*2]
0x180018a6b  mov     edi, 811C9DC5h
0x180018a70  cmp     rdx, rsi
0x180018a73  jz      short loc_180018A94
0x180018a75  movzx   ecx, word ptr [rbx]
0x180018a78  call    cs:__imp__o_towlower
0x180018a7e  imul    rdi, 1000193h
0x180018a85  movzx   ecx, ax
0x180018a88  add     rbx, 2
0x180018a8c  xor     rdi, rcx
0x180018a8f  cmp     rbx, rsi
0x180018a92  jnz     short loc_180018A75
0x180018a94  mov     eax, 834E0B5Fh
0x180018a99  imul    ecx, edi, 41A7h
0x180018a9f  imul    edi
0x180018aa1  add     edx, edi
0x180018aa3  sar     edx, 10h
0x180018aa6  mov     eax, edx
0x180018aa8  shr     eax, 1Fh
0x180018aab  add     edx, eax
0x180018aad  imul    eax, edx, 7FFFFFFFh
0x180018ab3  sub     ecx, eax
0x180018ab5  lea     eax, [rcx+7FFFFFFFh]
0x180018abb  cmovns  eax, ecx
0x180018abe  cdqe
0x180018ac0  add     rsp, 28h
0x180018ac4  pop     rdi
0x180018ac5  pop     rsi
0x180018ac6  pop     rbp
0x180018ac7  pop     rbx
0x180018ac8  retn
```
