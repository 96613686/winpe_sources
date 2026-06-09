# __security_init_cookie_ex

- ea: `0x180014554`
- end: `0x1800145b2`
- name: `__security_init_cookie_ex`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014508`

## callees

- `0x180014554`

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
0x180014554  mov     [rsp+arg_0], rcx
0x180014559  rdtsc
0x18001455b  shl     rdx, 20h
0x18001455f  or      rax, rdx
0x180014562  shr     rax, 4
0x180014566  xor     rax, [rsp+arg_0]
0x18001456b  mov     rcx, 0FFFFFFFFFFFFh
0x180014575  and     rax, rcx
0x180014578  mov     rcx, [rsp+arg_0]
0x18001457d  mov     [rcx], rax
0x180014580  mov     rax, [rsp+arg_0]
0x180014585  cmp     qword ptr [rax], 0
0x180014589  jz      short loc_18001459F
0x18001458b  mov     rax, [rsp+arg_0]
0x180014590  mov     rcx, 2B992DDFA232h
0x18001459a  cmp     [rax], rcx
0x18001459d  jnz     short locret_1800145B1
0x18001459f  mov     rax, [rsp+arg_0]
0x1800145a4  mov     rcx, 2B992DDFA233h
0x1800145ae  mov     [rax], rcx
0x1800145b1  retn
```
