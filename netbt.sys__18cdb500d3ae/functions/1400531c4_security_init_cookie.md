# __security_init_cookie

- ea: `0x1400531c4`
- end: `0x1400531f2`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140053190`

## callees

- `0x1400531c4`

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
0x1400531c4  mov     rax, cs:__security_cookie
0x1400531cb  test    rax, rax
0x1400531ce  jz      short loc_1400531EB
0x1400531d0  mov     rcx, 2B992DDFA232h
0x1400531da  cmp     rax, rcx
0x1400531dd  jz      short loc_1400531EB
0x1400531df  not     rax
0x1400531e2  mov     cs:__security_cookie_complement, rax
0x1400531e9  retn
0x1400531eb  mov     ecx, 6
0x1400531f0  int     29h; Win8: RtlFailFast(ecx)
```
