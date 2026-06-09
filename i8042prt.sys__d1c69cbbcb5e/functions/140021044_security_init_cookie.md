# __security_init_cookie

- ea: `0x140021044`
- end: `0x140021072`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140021010`

## callees

- `0x140021044`

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
0x140021044  mov     rax, cs:__security_cookie
0x14002104b  test    rax, rax
0x14002104e  jz      short loc_14002106B
0x140021050  mov     rcx, 2B992DDFA232h
0x14002105a  cmp     rax, rcx
0x14002105d  jz      short loc_14002106B
0x14002105f  not     rax
0x140021062  mov     cs:__security_cookie_complement, rax
0x140021069  retn
0x14002106b  mov     ecx, 6
0x140021070  int     29h; Win8: RtlFailFast(ecx)
```
