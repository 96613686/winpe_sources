# __security_init_cookie

- ea: `0x180045044`
- end: `0x180045072`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180038560`
- `0x180045010`

## callees

- `0x180045044`

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
0x180045044  mov     rax, cs:__security_cookie
0x18004504b  test    rax, rax
0x18004504e  jz      short loc_18004506B
0x180045050  mov     rcx, 2B992DDFA232h
0x18004505a  cmp     rax, rcx
0x18004505d  jz      short loc_18004506B
0x18004505f  not     rax
0x180045062  mov     cs:__security_cookie_complement, rax
0x180045069  retn
0x18004506b  mov     ecx, 6
0x180045070  int     29h; Win8: RtlFailFast(ecx)
```
