# __security_init_cookie

- ea: `0x18000c360`
- end: `0x18000c3a4`
- name: `__security_init_cookie`
- size: `68`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c1b8`
- `0x18000c7b0`

## callees

- `0x18000c360`
- `0x18000c3ac`

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
0x18000c360  sub     rsp, 28h
0x18000c364  cmp     cs:__security_cookie, 0
0x18000c36c  jz      short loc_18000C381
0x18000c36e  mov     rax, 2B992DDFA232h
0x18000c378  cmp     cs:__security_cookie, rax
0x18000c37f  jnz     short loc_18000C38E
0x18000c381  lea     rcx, __security_cookie
0x18000c388  call    __security_init_cookie_ex
0x18000c38d  nop
0x18000c38e  mov     rax, cs:__security_cookie
0x18000c395  not     rax
0x18000c398  mov     cs:__security_cookie_complement, rax
0x18000c39f  add     rsp, 28h
0x18000c3a3  retn
```
