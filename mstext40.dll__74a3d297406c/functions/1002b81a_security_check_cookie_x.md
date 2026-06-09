# __security_check_cookie(x)

- ea: `0x1002b81a`
- end: `0x1002b829`
- name: `@__security_check_cookie@4`
- size: `15`
- prototype: `void __fastcall(uintptr_t StackCookie)`
- caller_count: `161`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10008b40`
- `0x10009650`
- `0x100096d0`
- `0x10009800`
- `0x10009c40`
- `0x1000a470`
- `0x1000a590`
- `0x1000a740`
- `0x1000aa30`
- `0x1000b470`
- `0x1000b6d0`
- `0x1000b7a0`
- `0x1000b860`
- `0x1000bab0`
- `0x1000bfc0`
- `0x1000c370`
- `0x1000ca60`
- `0x1000cbf0`
- `0x1000d020`
- `0x1000d130`
- `0x1000d2c0`
- `0x1000d7a0`
- `0x1000d8d0`
- `0x1000db20`
- `0x1000dd10`
- `0x1000dfa0`
- `0x1000e3b0`
- `0x1000e950`
- `0x1000ed90`
- `0x1000f0e0`
- `0x1000f530`
- `0x1000f8f0`
- `0x1000fa40`
- `0x1000fc70`
- `0x10010020`
- `0x10010450`
- `0x100108e0`
- `0x10010f00`
- `0x100113f0`
- `0x10011650`
- `0x10011870`
- `0x10011d90`
- `0x10012e70`
- `0x100130e0`
- `0x100131b0`
- `0x100133f0`
- `0x100148d0`
- `0x10015000`
- `0x10015100`
- `0x100154f0`

## callees

- `0x1002b81a`
- `0x1002c158`

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
0x1002b81a  cmp     ecx, ___security_cookie
0x1002b820  jnz     short $failure$26820
0x1002b822  rep retn
0x1002b824  jmp     ___report_gsfailure
```
