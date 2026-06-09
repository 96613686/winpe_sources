# __security_check_cookie(x)

- ea: `0x10035510`
- end: `0x1003551e`
- name: `@__security_check_cookie@4`
- size: `14`
- prototype: `void __fastcall(uintptr_t StackCookie)`
- caller_count: `137`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10006480`
- `0x100068a0`
- `0x10006bd0`
- `0x1000ab50`
- `0x1000b350`
- `0x1000bba0`
- `0x1000c670`
- `0x1000f530`
- `0x10010790`
- `0x10011280`
- `0x10012270`
- `0x10014900`
- `0x10014c50`
- `0x10015090`
- `0x100158d0`
- `0x10016950`
- `0x100192b0`
- `0x100197c0`
- `0x10019d40`
- `0x1001abf0`
- `0x1001b1e0`
- `0x1001b9a0`
- `0x1001c340`
- `0x1001cb00`
- `0x1001d010`
- `0x1001d870`
- `0x1001e2b0`
- `0x1001e690`
- `0x1001eba0`
- `0x1001ec10`
- `0x1001eca0`
- `0x1001f360`
- `0x1001f420`
- `0x1001f5a0`
- `0x1001f760`
- `0x1001f990`
- `0x1001fa20`
- `0x1001fe30`
- `0x100203a0`
- `0x100204f0`
- `0x10020600`
- `0x10020680`
- `0x10020780`
- `0x10020e70`
- `0x10021260`
- `0x100213d0`
- `0x10021e70`
- `0x10022160`
- `0x10022240`
- `0x100224b6`

## callees

- `0x10035510`
- `0x10035524`

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
0x10035510  cmp     ecx, ___security_cookie
0x10035516  jnz     short loc_10035519
0x10035518  retn
0x10035519  jmp     ___report_gsfailure
```
