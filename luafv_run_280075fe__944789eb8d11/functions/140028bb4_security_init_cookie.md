# __security_init_cookie

- ea: `0x140028bb4`
- end: `0x140028be2`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140028b80`

## callees

- `0x140028bb4`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
    __fastfail(6u);
  _security_cookie_complement = ~_security_cookie;
}

```

## disassembly

```asm
0x140028bb4  mov     rax, cs:__security_cookie
0x140028bbb  test    rax, rax
0x140028bbe  jz      short loc_140028BDB
0x140028bc0  mov     rcx, 2B992DDFA232h
0x140028bca  cmp     rax, rcx
0x140028bcd  jz      short loc_140028BDB
0x140028bcf  not     rax
0x140028bd2  mov     cs:__security_cookie_complement, rax
0x140028bd9  retn
0x140028bdb  mov     ecx, 6
0x140028be0  int     29h; Win8: RtlFailFast(ecx)
```
