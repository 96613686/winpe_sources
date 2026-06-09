# __security_init_cookie

- ea: `0x140047044`
- end: `0x140047072`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140047010`

## callees

- `0x140047044`

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
0x140047044  mov     rax, cs:__security_cookie
0x14004704b  test    rax, rax
0x14004704e  jz      short loc_14004706B
0x140047050  mov     rcx, 2B992DDFA232h
0x14004705a  cmp     rax, rcx
0x14004705d  jz      short loc_14004706B
0x14004705f  not     rax
0x140047062  mov     cs:__security_cookie_complement, rax
0x140047069  retn
0x14004706b  mov     ecx, 6
0x140047070  int     29h; Win8: RtlFailFast(ecx)
```
