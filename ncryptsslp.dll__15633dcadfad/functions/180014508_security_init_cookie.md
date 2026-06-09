# __security_init_cookie

- ea: `0x180014508`
- end: `0x18001454c`
- name: `__security_init_cookie`
- size: `68`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800145b8`

## callees

- `0x180014508`
- `0x180014554`

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
0x180014508  sub     rsp, 28h
0x18001450c  cmp     cs:__security_cookie, 0
0x180014514  jz      short loc_180014529
0x180014516  mov     rax, 2B992DDFA232h
0x180014520  cmp     cs:__security_cookie, rax
0x180014527  jnz     short loc_180014536
0x180014529  lea     rcx, __security_cookie
0x180014530  call    __security_init_cookie_ex
0x180014535  nop
0x180014536  mov     rax, cs:__security_cookie
0x18001453d  not     rax
0x180014540  mov     cs:__security_cookie_complement, rax
0x180014547  add     rsp, 28h
0x18001454b  retn
```
