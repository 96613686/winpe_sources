# __security_init_cookie

- ea: `0x180008b50`
- end: `0x180008b94`
- name: `__security_init_cookie`
- size: `68`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008990`

## callees

- `0x180008b50`
- `0x180008b9c`

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
0x180008b50  sub     rsp, 28h
0x180008b54  cmp     cs:__security_cookie, 0
0x180008b5c  jz      short loc_180008B71
0x180008b5e  mov     rax, 2B992DDFA232h
0x180008b68  cmp     cs:__security_cookie, rax
0x180008b6f  jnz     short loc_180008B7E
0x180008b71  lea     rcx, __security_cookie
0x180008b78  call    __security_init_cookie_ex
0x180008b7d  nop
0x180008b7e  mov     rax, cs:__security_cookie
0x180008b85  not     rax
0x180008b88  mov     cs:__security_cookie_complement, rax
0x180008b8f  add     rsp, 28h
0x180008b93  retn
```
