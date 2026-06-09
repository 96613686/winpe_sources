# CFileStream::Read(void *,ulong,ulong *)

- ea: `0x18000da50`
- end: `0x18000daa5`
- name: `?Read@CFileStream@@UEAAJPEAXKPEAK@Z`
- size: `85`
- prototype: `__int64 __fastcall(FILE **this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000da50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18000da7a`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18000da7a`

## pseudocode

```c
__int64 __fastcall CFileStream::Read(FILE **this, void *a2, unsigned int a3, unsigned int *a4)
{
  if ( a3 != fread(a2, 1u, a3, this[68]) )
    return 2147500037LL;
  if ( a4 )
    *a4 = a3;
  return 0;
}

```

## disassembly

```asm
0x18000da50  mov     [rsp+arg_0], rbx
0x18000da55  mov     [rsp+arg_8], rsi
0x18000da5a  push    rdi
0x18000da5b  sub     rsp, 20h
0x18000da5f  mov     rax, rdx
0x18000da62  mov     esi, r8d
0x18000da65  mov     rdi, r9
0x18000da68  mov     r8d, r8d; ElementCount
0x18000da6b  mov     r9, [rcx+220h]; Stream
0x18000da72  mov     edx, 1; ElementSize
0x18000da77  mov     rcx, rax; Buffer
0x18000da7a  call    cs:__imp_fread
0x18000da80  cmp     rsi, rax
0x18000da83  jnz     short loc_18000DA90
0x18000da85  test    rdi, rdi
0x18000da88  jz      short loc_18000DA8C
0x18000da8a  mov     [rdi], esi
0x18000da8c  xor     eax, eax
0x18000da8e  jmp     short loc_18000DA95
0x18000da90  mov     eax, 80004005h
0x18000da95  mov     rbx, [rsp+28h+arg_0]
0x18000da9a  mov     rsi, [rsp+28h+arg_8]
0x18000da9f  add     rsp, 20h
0x18000daa3  pop     rdi
0x18000daa4  retn
```
