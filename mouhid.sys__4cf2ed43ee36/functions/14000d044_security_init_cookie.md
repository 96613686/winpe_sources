# __security_init_cookie

- ea: `0x14000d044`
- end: `0x14000d072`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d010`

## callees

- `0x14000d044`

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
0x14000d044  mov     rax, cs:__security_cookie
0x14000d04b  test    rax, rax
0x14000d04e  jz      short loc_14000D06B
0x14000d050  mov     rcx, 2B992DDFA232h
0x14000d05a  cmp     rax, rcx
0x14000d05d  jz      short loc_14000D06B
0x14000d05f  not     rax
0x14000d062  mov     cs:__security_cookie_complement, rax
0x14000d069  retn
0x14000d06b  mov     ecx, 6
0x14000d070  int     29h; Win8: RtlFailFast(ecx)
```
