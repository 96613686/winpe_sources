# __security_init_cookie

- ea: `0x140012044`
- end: `0x140012072`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140012010`

## callees

- `0x140012044`

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
0x140012044  mov     rax, cs:__security_cookie
0x14001204b  test    rax, rax
0x14001204e  jz      short loc_14001206B
0x140012050  mov     rcx, 2B992DDFA232h
0x14001205a  cmp     rax, rcx
0x14001205d  jz      short loc_14001206B
0x14001205f  not     rax
0x140012062  mov     cs:__security_cookie_complement, rax
0x140012069  retn
0x14001206b  mov     ecx, 6
0x140012070  int     29h; Win8: RtlFailFast(ecx)
```
