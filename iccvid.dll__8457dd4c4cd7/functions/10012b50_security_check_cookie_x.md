# __security_check_cookie(x)

- ea: `0x10012b50`
- end: `0x10012b5e`
- name: `@__security_check_cookie@4`
- size: `14`
- prototype: `void __fastcall(uintptr_t StackCookie)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1000f076`
- `0x1000f240`
- `0x1000f4d0`
- `0x1000f75a`
- `0x10010a12`

## callees

- `0x10012b50`
- `0x100130b9`

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
0x10012b50  cmp     ecx, ___security_cookie
0x10012b56  jnz     short loc_10012B59
0x10012b58  retn
0x10012b59  jmp     ___report_gsfailure
```
