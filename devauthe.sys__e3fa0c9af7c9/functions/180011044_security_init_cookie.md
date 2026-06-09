# __security_init_cookie

- ea: `0x180011044`
- end: `0x180011072`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011010`

## callees

- `0x180011044`

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
0x180011044  mov     rax, cs:__security_cookie
0x18001104b  test    rax, rax
0x18001104e  jz      short loc_18001106B
0x180011050  mov     rcx, 2B992DDFA232h
0x18001105a  cmp     rax, rcx
0x18001105d  jz      short loc_18001106B
0x18001105f  not     rax
0x180011062  mov     cs:__security_cookie_complement, rax
0x180011069  retn
0x18001106b  mov     ecx, 6
0x180011070  int     29h; Win8: RtlFailFast(ecx)
```
