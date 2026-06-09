# __security_init_cookie

- ea: `0x140032044`
- end: `0x140032072`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140032010`

## callees

- `0x140032044`

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
0x140032044  mov     rax, cs:__security_cookie
0x14003204b  test    rax, rax
0x14003204e  jz      short loc_14003206B
0x140032050  mov     rcx, 2B992DDFA232h
0x14003205a  cmp     rax, rcx
0x14003205d  jz      short loc_14003206B
0x14003205f  not     rax
0x140032062  mov     cs:__security_cookie_complement, rax
0x140032069  retn
0x14003206b  mov     ecx, 6
0x140032070  int     29h; Win8: RtlFailFast(ecx)
```
