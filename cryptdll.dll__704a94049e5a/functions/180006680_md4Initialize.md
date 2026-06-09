# md4Initialize

- ea: `0x180006680`
- end: `0x1800066ee`
- name: `md4Initialize`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006700`

## callees

- `0x180006680`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006692`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006692`
- `bcrypt!BCryptCreateHash` at `0x1800066cd`
- `bcrypt!BCryptCreateHash` at `0x1800066cd`

## pseudocode

```c
__int64 __fastcall md4Initialize(__int64 a1, BCRYPT_HASH_HANDLE **a2)
{
  BCRYPT_HASH_HANDLE *v3; // rax
  BCRYPT_HASH_HANDLE *v4; // rbx

  v3 = (BCRYPT_HASH_HANDLE *)malloc(0x18u);
  v4 = v3;
  if ( !v3 )
    return 3221225495LL;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x11, v3, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  *a2 = v4;
  return 0;
}

```

## disassembly

```asm
0x180006680  mov     [rsp+arg_0], rbx
0x180006685  push    rdi
0x180006686  sub     rsp, 40h
0x18000668a  mov     ecx, 18h; Size
0x18000668f  mov     rdi, rdx
0x180006692  call    cs:__imp_malloc
0x180006698  mov     rbx, rax
0x18000669b  test    rax, rax
0x18000669e  jnz     short loc_1800066A7
0x1800066a0  mov     eax, 0C0000017h
0x1800066a5  jmp     short loc_1800066E3
0x1800066a7  xor     r9d, r9d; cbHashObject
0x1800066aa  mov     [rsp+48h+dwFlags], 0; dwFlags
0x1800066b2  mov     [rsp+48h+cbSecret], 0; cbSecret
0x1800066ba  xor     r8d, r8d; pbHashObject
0x1800066bd  mov     rdx, rbx; phHash
0x1800066c0  mov     [rsp+48h+pbSecret], 0; pbSecret
0x1800066c9  lea     ecx, [r9+11h]; hAlgorithm
0x1800066cd  call    cs:__imp_BCryptCreateHash
0x1800066d3  test    eax, eax
0x1800066d5  jns     short loc_1800066DE
0x1800066d7  mov     ecx, 7
0x1800066dc  int     29h; Win8: RtlFailFast(ecx)
0x1800066de  mov     [rdi], rbx
0x1800066e1  xor     eax, eax
0x1800066e3  mov     rbx, [rsp+48h+arg_0]
0x1800066e8  add     rsp, 40h
0x1800066ec  pop     rdi
0x1800066ed  retn
```
