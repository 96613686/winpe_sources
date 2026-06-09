# CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)

- ea: `0x1800074a0`
- end: `0x1800074f7`
- name: `?_CalcKeyHash@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@CAK_K@Z`
- size: `87`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002ee0`
- `0x1800074a0`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800074ce`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800074ce`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800074b3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800074b3`

## pseudocode

```c
__int64 __fastcall CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_CalcKeyHash(
        unsigned int *a1)
{
  const unsigned __int16 *Str; // rax
  unsigned int v3; // edx
  unsigned int v4; // eax
  __int64 v5; // rbp
  int v6; // esi
  int v7; // edi
  unsigned __int8 *i; // rax
  int v9; // ecx

  Str = STRU::QueryStr((STRU *)(a1 + 44));
  v4 = HashString(Str, v3);
  v5 = a1[12];
  v6 = a1[13] ^ v4;
  v7 = 0;
  for ( i = (unsigned __int8 *)BUFFER::QueryPtr((BUFFER *)a1); v5; --v5 )
  {
    v9 = *i++;
    v7 = v9 + 101 * v7;
  }
  return v7 ^ (unsigned int)v6;
}

```

## disassembly

```asm
0x1800074a0  push    rbx
0x1800074a2  push    rbp
0x1800074a3  push    rsi
0x1800074a4  push    rdi
0x1800074a5  sub     rsp, 28h
0x1800074a9  mov     rbx, rcx
0x1800074ac  add     rcx, 0B0h
0x1800074b3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800074b9  mov     rcx, rax; unsigned __int16 *
0x1800074bc  call    ?HashString@@YAKPEBGK@Z; HashString(ushort const *,ulong)
0x1800074c1  mov     ebp, [rbx+30h]
0x1800074c4  mov     esi, eax
0x1800074c6  xor     esi, [rbx+34h]
0x1800074c9  mov     rcx, rbx
0x1800074cc  xor     edi, edi
0x1800074ce  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800074d4  test    rbp, rbp
0x1800074d7  jz      short loc_1800074EA
0x1800074d9  movzx   ecx, byte ptr [rax]
0x1800074dc  inc     rax
0x1800074df  imul    edi, 65h ; 'e'
0x1800074e2  add     edi, ecx
0x1800074e4  sub     rbp, 1
0x1800074e8  jnz     short loc_1800074D9
0x1800074ea  xor     esi, edi
0x1800074ec  mov     eax, esi
0x1800074ee  add     rsp, 28h
0x1800074f2  pop     rdi
0x1800074f3  pop     rsi
0x1800074f4  pop     rbp
0x1800074f5  pop     rbx
0x1800074f6  retn
```
