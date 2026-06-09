# __security_init_cookie

- ea: `0x14001331c`
- end: `0x14001334a`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005110`

## callees

- `0x14001331c`

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
0x14001331c  mov     rax, cs:__security_cookie
0x140013323  test    rax, rax
0x140013326  jz      short loc_140013343
0x140013328  mov     rcx, 2B992DDFA232h
0x140013332  cmp     rax, rcx
0x140013335  jz      short loc_140013343
0x140013337  not     rax
0x14001333a  mov     cs:__security_cookie_complement, rax
0x140013341  retn
0x140013343  mov     ecx, 6
0x140013348  int     29h; Win8: RtlFailFast(ecx)
```
