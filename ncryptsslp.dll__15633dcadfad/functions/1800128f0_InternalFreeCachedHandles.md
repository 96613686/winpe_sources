# InternalFreeCachedHandles

- ea: `0x1800128f0`
- end: `0x180012972`
- name: `InternalFreeCachedHandles`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012838`

## callees

- `0x1800128f0`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180012956`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180012960`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001296a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180012956`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180012960`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001296a`

## pseudocode

```c
NTSTATUS __fastcall InternalFreeCachedHandles(__int64 a1, __int64 a2)
{
  __int64 i; // rbx
  NTSTATUS result; // eax
  void *v6; // rcx
  __int64 j; // rbx
  void *v8; // rcx
  void *v9; // rcx

  for ( i = 0; i != 16; ++i )
  {
    result = 2 * i;
    v6 = *(void **)(a1 + 16 * i);
    if ( v6 )
      result = BCryptCloseAlgorithmProvider(v6, 0);
  }
  for ( j = 0; j != 16; ++j )
  {
    v8 = *(void **)(32 * j + a2);
    if ( v8 )
      result = BCryptCloseAlgorithmProvider(v8, 0);
    v9 = *(void **)(32 * j + a2 + 8);
    if ( v9 )
      result = BCryptCloseAlgorithmProvider(v9, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1800128f0  mov     [rsp+arg_0], rbx
0x1800128f5  mov     [rsp+arg_8], rsi
0x1800128fa  push    rdi
0x1800128fb  sub     rsp, 20h
0x1800128ff  mov     rsi, rdx
0x180012902  mov     rdi, rcx
0x180012905  xor     ebx, ebx
0x180012907  mov     rax, rbx
0x18001290a  add     rax, rax
0x18001290d  mov     rcx, [rdi+rax*8]; hAlgorithm
0x180012911  test    rcx, rcx
0x180012914  jnz     short loc_18001295E
0x180012916  inc     rbx
0x180012919  cmp     rbx, 10h
0x18001291d  jnz     short loc_180012907
0x18001291f  xor     ebx, ebx
0x180012921  mov     rdi, rbx
0x180012924  shl     rdi, 5
0x180012928  mov     rcx, [rdi+rsi]; hAlgorithm
0x18001292c  test    rcx, rcx
0x18001292f  jnz     short loc_180012968
0x180012931  mov     rcx, [rdi+rsi+8]; hAlgorithm
0x180012936  test    rcx, rcx
0x180012939  jnz     short loc_180012954
0x18001293b  inc     rbx
0x18001293e  cmp     rbx, 10h
0x180012942  jnz     short loc_180012921
0x180012944  mov     rbx, [rsp+28h+arg_0]
0x180012949  mov     rsi, [rsp+28h+arg_8]
0x18001294e  add     rsp, 20h
0x180012952  pop     rdi
0x180012953  retn
0x180012954  xor     edx, edx; dwFlags
0x180012956  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001295c  jmp     short loc_18001293B
0x18001295e  xor     edx, edx; dwFlags
0x180012960  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180012966  jmp     short loc_180012916
0x180012968  xor     edx, edx; dwFlags
0x18001296a  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180012970  jmp     short loc_180012931
```
