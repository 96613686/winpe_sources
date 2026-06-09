# __security_init_cookie

- ea: `0x18001a400`
- end: `0x18001a444`
- name: `__security_init_cookie`
- size: `68`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a258`

## callees

- `0x18001a400`
- `0x18001a44c`

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
0x18001a400  sub     rsp, 28h
0x18001a404  cmp     cs:__security_cookie, 0
0x18001a40c  jz      short loc_18001A421
0x18001a40e  mov     rax, 2B992DDFA232h
0x18001a418  cmp     cs:__security_cookie, rax
0x18001a41f  jnz     short loc_18001A42E
0x18001a421  lea     rcx, __security_cookie
0x18001a428  call    __security_init_cookie_ex
0x18001a42d  nop
0x18001a42e  mov     rax, cs:__security_cookie
0x18001a435  not     rax
0x18001a438  mov     cs:__security_cookie_complement, rax
0x18001a43f  add     rsp, 28h
0x18001a443  retn
```
