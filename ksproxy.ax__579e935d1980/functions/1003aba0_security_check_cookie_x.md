# __security_check_cookie(x)

- ea: `0x1003aba0`
- end: `0x1003abae`
- name: `@__security_check_cookie@4`
- size: `14`
- prototype: `void __fastcall(uintptr_t StackCookie)`
- caller_count: `92`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10005ef6`
- `0x10006043`
- `0x10006a5c`
- `0x10006e0a`
- `0x10007923`
- `0x10007aee`
- `0x100087bd`
- `0x10008c1d`
- `0x10009390`
- `0x10009670`
- `0x1000c1a0`
- `0x1000c740`
- `0x1000c970`
- `0x1000cc20`
- `0x1000cf60`
- `0x1000d790`
- `0x1000da20`
- `0x1000dcc0`
- `0x1000f748`
- `0x1000f7f1`
- `0x1000fa6a`
- `0x10010880`
- `0x10010e48`
- `0x10011c70`
- `0x10012740`
- `0x10012bf0`
- `0x10013340`
- `0x10014357`
- `0x10015b70`
- `0x10016b80`
- `0x10018aa0`
- `0x1001a270`
- `0x1001a323`
- `0x1001a414`
- `0x1001a516`
- `0x1001b660`
- `0x1001bc78`
- `0x1001bdb0`
- `0x1001c490`
- `0x1001e5ad`
- `0x1001f2b0`
- `0x100206a3`
- `0x100208f4`
- `0x10020ce6`
- `0x10020e70`
- `0x10021163`
- `0x1002168c`
- `0x100224d5`
- `0x10022cf8`
- `0x1002343f`

## callees

- `0x1003aba0`
- `0x1003b18f`

## pseudocode

```c
void __fastcall __security_check_cookie(uintptr_t StackCookie)
{
  if ( StackCookie != __security_cookie )
    __report_gsfailure();
}

```

## disassembly

```asm
0x1003aba0  cmp     ecx, ___security_cookie
0x1003aba6  jnz     short loc_1003ABA9
0x1003aba8  retn
0x1003aba9  jmp     ___report_gsfailure
```
