# __security_init_cookie_ex

- ea: `0x180002aac`
- end: `0x180002b0a`
- name: `__security_init_cookie_ex`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002a60`

## callees

- `0x180002aac`

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
0x180002aac  mov     [rsp+arg_0], rcx
0x180002ab1  rdtsc
0x180002ab3  shl     rdx, 20h
0x180002ab7  or      rax, rdx
0x180002aba  shr     rax, 4
0x180002abe  xor     rax, [rsp+arg_0]
0x180002ac3  mov     rcx, 0FFFFFFFFFFFFh
0x180002acd  and     rax, rcx
0x180002ad0  mov     rcx, [rsp+arg_0]
0x180002ad5  mov     [rcx], rax
0x180002ad8  mov     rax, [rsp+arg_0]
0x180002add  cmp     qword ptr [rax], 0
0x180002ae1  jz      short loc_180002AF7
0x180002ae3  mov     rax, [rsp+arg_0]
0x180002ae8  mov     rcx, 2B992DDFA232h
0x180002af2  cmp     [rax], rcx
0x180002af5  jnz     short locret_180002B09
0x180002af7  mov     rax, [rsp+arg_0]
0x180002afc  mov     rcx, 2B992DDFA233h
0x180002b06  mov     [rax], rcx
0x180002b09  retn
```
