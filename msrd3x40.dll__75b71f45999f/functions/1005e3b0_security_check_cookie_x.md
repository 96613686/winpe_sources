# __security_check_cookie(x)

- ea: `0x1005e3b0`
- end: `0x1005e3be`
- name: `@__security_check_cookie@4`
- size: `14`
- prototype: `void __fastcall(uintptr_t StackCookie)`
- caller_count: `244`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10008670`
- `0x10008950`
- `0x10008bc0`
- `0x10008d60`
- `0x10009170`
- `0x10009540`
- `0x10009850`
- `0x10009ce0`
- `0x10009d30`
- `0x1000a000`
- `0x1000a1b0`
- `0x1000a6c0`
- `0x1000a9c0`
- `0x1000b0e0`
- `0x1000be30`
- `0x1000c260`
- `0x1000c5c0`
- `0x1000c690`
- `0x1000c850`
- `0x1000cd70`
- `0x1000d370`
- `0x1000d600`
- `0x1000d7c0`
- `0x1000dcc0`
- `0x1000e040`
- `0x1000e110`
- `0x1000e470`
- `0x1000e680`
- `0x1000e770`
- `0x1000e820`
- `0x1000ebe0`
- `0x1000eef0`
- `0x1000f290`
- `0x1000f4b0`
- `0x100106b0`
- `0x10010d60`
- `0x10011400`
- `0x10011540`
- `0x10011f50`
- `0x10012190`
- `0x100128e0`
- `0x10012b50`
- `0x10013420`
- `0x10015df0`
- `0x100160c0`
- `0x100179b0`
- `0x10017c60`
- `0x10018200`
- `0x10018450`
- `0x10018700`

## callees

- `0x1005e3b0`
- `0x1005e7d0`

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
0x1005e3b0  cmp     ecx, ___security_cookie
0x1005e3b6  jnz     short loc_1005E3B9
0x1005e3b8  retn
0x1005e3b9  jmp     ___report_gsfailure
```
