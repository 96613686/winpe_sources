# __security_init_cookie_ex

- ea: `0x180008b9c`
- end: `0x180008bfa`
- name: `__security_init_cookie_ex`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008b50`

## callees

- `0x180008b9c`

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
0x180008b9c  mov     [rsp+arg_0], rcx
0x180008ba1  rdtsc
0x180008ba3  shl     rdx, 20h
0x180008ba7  or      rax, rdx
0x180008baa  shr     rax, 4
0x180008bae  xor     rax, [rsp+arg_0]
0x180008bb3  mov     rcx, 0FFFFFFFFFFFFh
0x180008bbd  and     rax, rcx
0x180008bc0  mov     rcx, [rsp+arg_0]
0x180008bc5  mov     [rcx], rax
0x180008bc8  mov     rax, [rsp+arg_0]
0x180008bcd  cmp     qword ptr [rax], 0
0x180008bd1  jz      short loc_180008BE7
0x180008bd3  mov     rax, [rsp+arg_0]
0x180008bd8  mov     rcx, 2B992DDFA232h
0x180008be2  cmp     [rax], rcx
0x180008be5  jnz     short locret_180008BF9
0x180008be7  mov     rax, [rsp+arg_0]
0x180008bec  mov     rcx, 2B992DDFA233h
0x180008bf6  mov     [rax], rcx
0x180008bf9  retn
```
