# __security_init_cookie_ex

- ea: `0x18001a44c`
- end: `0x18001a4aa`
- name: `__security_init_cookie_ex`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a400`

## callees

- `0x18001a44c`

## pseudocode

```c
unsigned __int64 *__fastcall _security_init_cookie_ex(unsigned __int64 *a1)
{
  unsigned __int64 v1; // rax
  unsigned __int64 *result; // rax

  v1 = __rdtsc();
  *a1 = ((unsigned __int64)a1 ^ ((((unsigned __int64)HIDWORD(v1) << 32) | (unsigned int)v1) >> 4)) & 0xFFFFFFFFFFFFLL;
  if ( !*a1 || (result = a1, *a1 == 0x2B992DDFA232LL) )
  {
    result = a1;
    *a1 = 0x2B992DDFA233LL;
  }
  return result;
}

```

## disassembly

```asm
0x18001a44c  mov     [rsp+arg_0], rcx
0x18001a451  rdtsc
0x18001a453  shl     rdx, 20h
0x18001a457  or      rax, rdx
0x18001a45a  shr     rax, 4
0x18001a45e  xor     rax, [rsp+arg_0]
0x18001a463  mov     rcx, 0FFFFFFFFFFFFh
0x18001a46d  and     rax, rcx
0x18001a470  mov     rcx, [rsp+arg_0]
0x18001a475  mov     [rcx], rax
0x18001a478  mov     rax, [rsp+arg_0]
0x18001a47d  cmp     qword ptr [rax], 0
0x18001a481  jz      short loc_18001A497
0x18001a483  mov     rax, [rsp+arg_0]
0x18001a488  mov     rcx, 2B992DDFA232h
0x18001a492  cmp     [rax], rcx
0x18001a495  jnz     short locret_18001A4A9
0x18001a497  mov     rax, [rsp+arg_0]
0x18001a49c  mov     rcx, 2B992DDFA233h
0x18001a4a6  mov     [rax], rcx
0x18001a4a9  retn
```
