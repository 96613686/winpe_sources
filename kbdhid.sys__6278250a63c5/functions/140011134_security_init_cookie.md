# __security_init_cookie

- ea: `0x140011134`
- end: `0x140011162`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140011100`

## callees

- `0x140011134`

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
0x140011134  mov     rax, cs:__security_cookie
0x14001113b  test    rax, rax
0x14001113e  jz      short loc_14001115B
0x140011140  mov     rcx, 2B992DDFA232h
0x14001114a  cmp     rax, rcx
0x14001114d  jz      short loc_14001115B
0x14001114f  not     rax
0x140011152  mov     cs:__security_cookie_complement, rax
0x140011159  retn
0x14001115b  mov     ecx, 6
0x140011160  int     29h; Win8: RtlFailFast(ecx)
```
