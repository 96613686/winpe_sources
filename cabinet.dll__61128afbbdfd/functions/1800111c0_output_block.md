# output_block

- ea: `0x1800111c0`
- end: `0x18001131e`
- name: `output_block`
- size: `350`
- prototype: `errno_t __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800019d0`
- `0x180010f7c`

## callees

- `0x18000e4a0`
- `0x18000e558`
- `0x18000f2a8`
- `0x1800111c0`
- `0x18001562a`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18001127b`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800112ca`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800112f9`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18001127b`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800112ca`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800112f9`

## pseudocode

```c
errno_t __fastcall output_block(__int64 a1, int a2)
{
  int v2; // r9d
  int v3; // r8d
  __int64 v5; // rsi
  unsigned __int64 v6; // rdi
  unsigned int v7; // r8d
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  signed int v11; // eax
  errno_t result; // eax
  __int64 v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v17; // [rsp+58h] [rbp+10h] BYREF

  v2 = *(_DWORD *)(a1 + 60);
  v3 = *(_DWORD *)(a1 + 56);
  v17 = 0;
  v16 = 0;
  *(_BYTE *)(a1 + 2481) = 0;
  split_block(a1, a2, v3, v2, (__int64)&v17, (__int64)&v16);
  v5 = v16;
  v6 = v17;
  do_block_output(a1, v17, v16);
  v7 = *(_DWORD *)(a1 + 56);
  if ( (_DWORD)v6 == v7 )
  {
    memset_0(*(void **)(a1 + 80), 0, 0x2000u);
    *(_QWORD *)(a1 + 56) = 0;
    return fix_tree_cost_estimates(a1, v8, v9, v10);
  }
  v11 = (v7 >> 3) - ((unsigned int)v6 >> 3) + 1;
  if ( v11 >= 0x2000 - (int)v6 / 8 )
    v11 = 0x2000 - (int)v6 / 8;
  result = memmove_s(*(void *const *)(a1 + 80), 0x2000u, (const void *const)(*(_QWORD *)(a1 + 80) + (v6 >> 3)), v11);
  if ( !result )
  {
    v13 = (unsigned int)(*(_DWORD *)(a1 + 56) - v6) >> 3;
    memset_0((void *)(*(_QWORD *)(a1 + 80) + (unsigned int)(v13 + 1)), 0, 0x1FFF - v13);
    v14 = *(_DWORD *)(a1 + 56) - v6;
    if ( v14 >= 0x10000 - (int)v6 )
      v14 = 0x10000 - v6;
    result = memmove_s(*(void *const *)(a1 + 72), 0x10000u, (const void *const)(*(_QWORD *)(a1 + 72) + v6), v14);
    if ( !result )
    {
      v15 = *(_DWORD *)(a1 + 60) - v5;
      if ( v15 >= 0x8000 - (int)v5 )
        v15 = 0x8000 - v5;
      result = memmove_s(
                 *(void *const *)(a1 + 64),
                 0x20000u,
                 (const void *const)(*(_QWORD *)(a1 + 64) + 4 * v5),
                 4LL * v15);
      if ( !result )
      {
        *(_DWORD *)(a1 + 56) -= v6;
        *(_DWORD *)(a1 + 60) -= v5;
        return fix_tree_cost_estimates(a1, v8, v9, v10);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800111c0  mov     r11, rsp
0x1800111c3  mov     [r11+18h], rbx
0x1800111c7  push    rbp
0x1800111c8  push    rsi
0x1800111c9  push    rdi
0x1800111ca  sub     rsp, 30h
0x1800111ce  mov     r9d, [rcx+3Ch]
0x1800111d2  lea     rax, [r11+8]
0x1800111d6  mov     r8d, [rcx+38h]
0x1800111da  mov     rbx, rcx
0x1800111dd  mov     [r11-20h], rax
0x1800111e1  lea     rax, [r11+10h]
0x1800111e5  mov     [r11-28h], rax
0x1800111e9  mov     [rsp+48h+arg_8], 0
0x1800111f1  mov     [rsp+48h+arg_0], 0
0x1800111f9  mov     byte ptr [rcx+9B1h], 0
0x180011200  call    split_block
0x180011205  mov     esi, [rsp+48h+arg_0]
0x180011209  mov     rcx, rbx
0x18001120c  mov     edi, [rsp+48h+arg_8]
0x180011210  mov     r8d, esi
0x180011213  mov     edx, edi
0x180011215  call    do_block_output
0x18001121a  mov     r8d, [rbx+38h]
0x18001121e  cmp     edi, r8d
0x180011221  jnz     short loc_180011241
0x180011223  mov     rcx, [rbx+50h]; void *
0x180011227  xor     edx, edx; Val
0x180011229  mov     r8d, 2000h; Size
0x18001122f  call    memset_0
0x180011234  mov     qword ptr [rbx+38h], 0
0x18001123c  jmp     loc_180011309
0x180011241  shr     r8d, 3
0x180011245  mov     ecx, 8
0x18001124a  mov     eax, edi
0x18001124c  cdq
0x18001124d  idiv    ecx
0x18001124f  mov     edx, 2000h; DestinationSize
0x180011254  mov     ecx, edx
0x180011256  sub     ecx, eax
0x180011258  mov     eax, edi
0x18001125a  shr     eax, 3
0x18001125d  sub     r8d, eax
0x180011260  lea     eax, [r8+1]
0x180011264  mov     r8, rdi
0x180011267  cmp     eax, ecx
0x180011269  cmovge  eax, ecx
0x18001126c  mov     rcx, [rbx+50h]; Destination
0x180011270  shr     r8, 3
0x180011274  add     r8, [rbx+50h]; Source
0x180011278  movsxd  r9, eax; SourceSize
0x18001127b  call    cs:__imp_memmove_s
0x180011281  test    eax, eax
0x180011283  jnz     loc_180011311
0x180011289  mov     eax, [rbx+38h]
0x18001128c  mov     r8d, 1FFFh
0x180011292  sub     eax, edi
0x180011294  xor     edx, edx; Val
0x180011296  shr     eax, 3
0x180011299  sub     r8, rax; Size
0x18001129c  lea     ecx, [rax+1]
0x18001129f  add     rcx, [rbx+50h]; void *
0x1800112a3  call    memset_0
0x1800112a8  mov     eax, [rbx+38h]
0x1800112ab  mov     edx, 10000h; DestinationSize
0x1800112b0  mov     rcx, [rbx+48h]; Destination
0x1800112b4  mov     r8d, edx
0x1800112b7  sub     r8d, edi
0x1800112ba  sub     eax, edi
0x1800112bc  cmp     eax, r8d
0x1800112bf  cmovnb  eax, r8d
0x1800112c3  lea     r8, [rcx+rdi]; Source
0x1800112c7  mov     r9d, eax; SourceSize
0x1800112ca  call    cs:__imp_memmove_s
0x1800112d0  test    eax, eax
0x1800112d2  jnz     short loc_180011311
0x1800112d4  mov     eax, [rbx+3Ch]
0x1800112d7  mov     edx, 8000h
0x1800112dc  mov     rcx, [rbx+40h]; Destination
0x1800112e0  sub     edx, esi
0x1800112e2  sub     eax, esi
0x1800112e4  cmp     eax, edx
0x1800112e6  cmovnb  eax, edx
0x1800112e9  lea     r8, [rcx+rsi*4]; Source
0x1800112ed  mov     r9d, eax
0x1800112f0  mov     edx, 20000h; DestinationSize
0x1800112f5  shl     r9, 2; SourceSize
0x1800112f9  call    cs:__imp_memmove_s
0x1800112ff  test    eax, eax
0x180011301  jnz     short loc_180011311
0x180011303  sub     [rbx+38h], edi
0x180011306  sub     [rbx+3Ch], esi
0x180011309  mov     rcx, rbx
0x18001130c  call    fix_tree_cost_estimates
0x180011311  mov     rbx, [rsp+48h+arg_10]
0x180011316  add     rsp, 30h
0x18001131a  pop     rdi
0x18001131b  pop     rsi
0x18001131c  pop     rbp
0x18001131d  retn
```
