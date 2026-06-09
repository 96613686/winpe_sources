# __security_init_cookie

- ea: `0x1400015b0`
- end: `0x1400015f4`
- name: `__security_init_cookie`
- size: `68`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`

## callees

- `0x1400015b0`
- `0x1400015fc`

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
0x1400015b0  sub     rsp, 28h
0x1400015b4  cmp     cs:__security_cookie, 0
0x1400015bc  jz      short loc_1400015D1
0x1400015be  mov     rax, 2B992DDFA232h
0x1400015c8  cmp     cs:__security_cookie, rax
0x1400015cf  jnz     short loc_1400015DE
0x1400015d1  lea     rcx, __security_cookie
0x1400015d8  call    __security_init_cookie_ex
0x1400015dd  nop
0x1400015de  mov     rax, cs:__security_cookie
0x1400015e5  not     rax
0x1400015e8  mov     cs:__security_cookie_complement, rax
0x1400015ef  add     rsp, 28h
0x1400015f3  retn
```
