# CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)

- ea: `0x180007500`
- end: `0x18000757c`
- name: `?_EqualKeys@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@CA_N_K0@Z`
- size: `124`
- prototype: `bool __fastcall(_DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007500`
- `0x180008ba6`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180007542`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000754e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180007542`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000754e`
- `iisutil!?Equals@STRU@@QEBA_NAEBV1@@Z` at `0x18000752b`
- `iisutil!?Equals@STRU@@QEBA_NAEBV1@@Z` at `0x18000752b`

## pseudocode

```c
bool __fastcall CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_EqualKeys(
        _DWORD *a1,
        _DWORD *a2)
{
  unsigned int v4; // edi
  const void *Ptr; // rbx
  const void *v6; // rax
  bool result; // al

  result = 0;
  if ( a1[13] == a2[13] && STRU::Equals((STRU *)(a1 + 44), (const struct STRU *)(a2 + 44)) && a1[12] == a2[12] )
  {
    v4 = a1[12];
    Ptr = BUFFER::QueryPtr((BUFFER *)a2);
    v6 = BUFFER::QueryPtr((BUFFER *)a1);
    if ( !memcmp_0(v6, Ptr, v4) )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180007500  mov     [rsp+arg_0], rbx
0x180007505  mov     [rsp+arg_8], rsi
0x18000750a  push    rdi
0x18000750b  sub     rsp, 20h
0x18000750f  mov     eax, [rdx+34h]
0x180007512  mov     rbx, rdx
0x180007515  mov     rsi, rcx
0x180007518  cmp     [rcx+34h], eax
0x18000751b  jnz     short loc_18000756A
0x18000751d  add     rdx, 0B0h
0x180007524  add     rcx, 0B0h
0x18000752b  call    cs:__imp_?Equals@STRU@@QEBA_NAEBV1@@Z; STRU::Equals(STRU const &)
0x180007531  test    al, al
0x180007533  jz      short loc_18000756A
0x180007535  mov     eax, [rsi+30h]
0x180007538  cmp     eax, [rbx+30h]
0x18000753b  jnz     short loc_18000756A
0x18000753d  mov     rcx, rbx
0x180007540  mov     edi, eax
0x180007542  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180007548  mov     rcx, rsi
0x18000754b  mov     rbx, rax
0x18000754e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180007554  mov     r8d, edi; Size
0x180007557  mov     rdx, rbx; Buf2
0x18000755a  mov     rcx, rax; Buf1
0x18000755d  call    memcmp_0
0x180007562  test    eax, eax
0x180007564  jnz     short loc_18000756A
0x180007566  mov     al, 1
0x180007568  jmp     short loc_18000756C
0x18000756a  xor     al, al
0x18000756c  mov     rbx, [rsp+28h+arg_0]
0x180007571  mov     rsi, [rsp+28h+arg_8]
0x180007576  add     rsp, 20h
0x18000757a  pop     rdi
0x18000757b  retn
```
