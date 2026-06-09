# md4Initialize

- ea: `0x14000ea50`
- end: `0x14000ead4`
- name: `md4Initialize`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000eae0`

## callees

- `0x14000ea50`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000ea6b`
- `ntoskrnl!ExAllocatePool2` at `0x14000ea6b`
- `cng!BCryptCreateHash` at `0x14000eaac`
- `cng!BCryptCreateHash` at `0x14000eaac`

## pseudocode

```c
__int64 __fastcall md4Initialize(__int64 a1, BCRYPT_HASH_HANDLE **a2)
{
  BCRYPT_HASH_HANDLE *Pool2; // rax
  BCRYPT_HASH_HANDLE *v4; // rbx

  Pool2 = (BCRYPT_HASH_HANDLE *)ExAllocatePool2(64, 24, 1887007299);
  v4 = Pool2;
  if ( !Pool2 )
    return 3221225495LL;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x11, Pool2, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  *a2 = v4;
  return 0;
}

```

## disassembly

```asm
0x14000ea50  mov     [rsp+arg_0], rbx
0x14000ea55  push    rdi
0x14000ea56  sub     rsp, 40h
0x14000ea5a  mov     rdi, rdx
0x14000ea5d  mov     r8d, 70797243h
0x14000ea63  mov     edx, 18h
0x14000ea68  lea     ecx, [rdx+28h]
0x14000ea6b  call    cs:__imp_ExAllocatePool2
0x14000ea72  nop     dword ptr [rax+rax+00h]
0x14000ea77  mov     rbx, rax
0x14000ea7a  test    rax, rax
0x14000ea7d  jnz     short loc_14000EA86
0x14000ea7f  mov     eax, 0C0000017h
0x14000ea84  jmp     short loc_14000EAC8
0x14000ea86  xor     r9d, r9d; cbHashObject
0x14000ea89  mov     [rsp+48h+dwFlags], 0; dwFlags
0x14000ea91  mov     [rsp+48h+cbSecret], 0; cbSecret
0x14000ea99  xor     r8d, r8d; pbHashObject
0x14000ea9c  mov     rdx, rbx; phHash
0x14000ea9f  mov     [rsp+48h+pbSecret], 0; pbSecret
0x14000eaa8  lea     ecx, [r9+11h]; hAlgorithm
0x14000eaac  call    cs:__imp_BCryptCreateHash
0x14000eab3  nop     dword ptr [rax+rax+00h]
0x14000eab8  test    eax, eax
0x14000eaba  jns     short loc_14000EAC3
0x14000eabc  mov     ecx, 7
0x14000eac1  int     29h; Win8: RtlFailFast(ecx)
0x14000eac3  mov     [rdi], rbx
0x14000eac6  xor     eax, eax
0x14000eac8  mov     rbx, [rsp+48h+arg_0]
0x14000eacd  add     rsp, 40h
0x14000ead1  pop     rdi
0x14000ead2  retn
```
