# Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)

- ea: `0x180019414`
- end: `0x180019498`
- name: `??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z`
- size: `132`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018cd8`
- `0x18001ae58`
- `0x18001b06c`

## callees

- `0x180019414`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180019440`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180019440`

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
0x180019414  push    rbx
0x180019416  push    rbp
0x180019417  push    rsi
0x180019418  push    rdi
0x180019419  sub     rsp, 28h
0x18001941d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019421  mov     rbx, rdx
0x180019424  xor     ebp, ebp
0x180019426  inc     rax
0x180019429  cmp     [rdx+rax*2], bp
0x18001942d  jnz     short loc_180019426
0x18001942f  lea     rsi, [rdx+rax*2]
0x180019433  mov     edi, 811C9DC5h
0x180019438  cmp     rdx, rsi
0x18001943b  jz      short loc_180019462
0x18001943d  movzx   ecx, word ptr [rbx]
0x180019440  call    cs:__imp__o_towlower
0x180019447  nop     dword ptr [rax+rax+00h]
0x18001944c  imul    rdi, 1000193h
0x180019453  movzx   ecx, ax
0x180019456  add     rbx, 2
0x18001945a  xor     rdi, rcx
0x18001945d  cmp     rbx, rsi
0x180019460  jnz     short loc_18001943D
0x180019462  mov     eax, 834E0B5Fh
0x180019467  imul    ecx, edi, 41A7h
0x18001946d  imul    edi
0x18001946f  add     edx, edi
0x180019471  sar     edx, 10h
0x180019474  mov     eax, edx
0x180019476  shr     eax, 1Fh
0x180019479  add     edx, eax
0x18001947b  imul    eax, edx, 7FFFFFFFh
0x180019481  sub     ecx, eax
0x180019483  lea     eax, [rcx+7FFFFFFFh]
0x180019489  cmovns  eax, ecx
0x18001948c  cdqe
0x18001948e  add     rsp, 28h
0x180019492  pop     rdi
0x180019493  pop     rsi
0x180019494  pop     rbp
0x180019495  pop     rbx
0x180019496  retn
```
