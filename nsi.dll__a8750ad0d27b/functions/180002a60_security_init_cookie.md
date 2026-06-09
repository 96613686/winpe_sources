# __security_init_cookie

- ea: `0x180002a60`
- end: `0x180002aa4`
- name: `__security_init_cookie`
- size: `68`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800028b8`

## callees

- `0x180002a60`
- `0x180002aac`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
    _security_init_cookie_ex(&_security_cookie);
  _security_cookie_complement = ~_security_cookie;
}

```

## disassembly

```asm
0x180002a60  sub     rsp, 28h
0x180002a64  cmp     cs:__security_cookie, 0
0x180002a6c  jz      short loc_180002A81
0x180002a6e  mov     rax, 2B992DDFA232h
0x180002a78  cmp     cs:__security_cookie, rax
0x180002a7f  jnz     short loc_180002A8E
0x180002a81  lea     rcx, __security_cookie
0x180002a88  call    __security_init_cookie_ex
0x180002a8d  nop
0x180002a8e  mov     rax, cs:__security_cookie
0x180002a95  not     rax
0x180002a98  mov     cs:__security_cookie_complement, rax
0x180002a9f  add     rsp, 28h
0x180002aa3  retn
```
