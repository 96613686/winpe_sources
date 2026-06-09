# __security_init_cookie_ex

- ea: `0x1400015fc`
- end: `0x14000165a`
- name: `__security_init_cookie_ex`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400015b0`

## callees

- `0x1400015fc`

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
0x1400015fc  mov     [rsp+arg_0], rcx
0x140001601  rdtsc
0x140001603  shl     rdx, 20h
0x140001607  or      rax, rdx
0x14000160a  shr     rax, 4
0x14000160e  xor     rax, [rsp+arg_0]
0x140001613  mov     rcx, 0FFFFFFFFFFFFh
0x14000161d  and     rax, rcx
0x140001620  mov     rcx, [rsp+arg_0]
0x140001625  mov     [rcx], rax
0x140001628  mov     rax, [rsp+arg_0]
0x14000162d  cmp     qword ptr [rax], 0
0x140001631  jz      short loc_140001647
0x140001633  mov     rax, [rsp+arg_0]
0x140001638  mov     rcx, 2B992DDFA232h
0x140001642  cmp     [rax], rcx
0x140001645  jnz     short locret_140001659
0x140001647  mov     rax, [rsp+arg_0]
0x14000164c  mov     rcx, 2B992DDFA233h
0x140001656  mov     [rax], rcx
0x140001659  retn
```
