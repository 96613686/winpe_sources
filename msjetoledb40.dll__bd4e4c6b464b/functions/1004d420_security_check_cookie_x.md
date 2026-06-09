# __security_check_cookie(x)

- ea: `0x1004d420`
- end: `0x1004d430`
- name: `@__security_check_cookie@4`
- size: `16`
- prototype: `void __fastcall(uintptr_t StackCookie)`
- caller_count: `144`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1000c0d0`
- `0x1000c750`
- `0x1000ce70`
- `0x1000cff0`
- `0x1000d150`
- `0x1000d5b0`
- `0x1000d8e0`
- `0x1000ddb0`
- `0x1000e140`
- `0x1000eab0`
- `0x1000f260`
- `0x1000fc70`
- `0x1000fcf0`
- `0x10010b50`
- `0x10011380`
- `0x10011530`
- `0x100118b0`
- `0x10011d40`
- `0x10012270`
- `0x100124f0`
- `0x10012e10`
- `0x10012f70`
- `0x10013020`
- `0x10013100`
- `0x100132e0`
- `0x10013890`
- `0x10013d50`
- `0x10014d90`
- `0x100153e0`
- `0x10015dc0`
- `0x10016040`
- `0x10016f60`
- `0x10017160`
- `0x10017960`
- `0x10017b50`
- `0x10018750`
- `0x100188a0`
- `0x10019070`
- `0x100198d0`
- `0x10019cd0`
- `0x1001a540`
- `0x1001a700`
- `0x1001a970`
- `0x1001af60`
- `0x1001b4a0`
- `0x1001b720`
- `0x1001b930`
- `0x1001ba90`
- `0x1001bc50`
- `0x1001bdc0`

## callees

- `0x1004d420`
- `0x1004d48c`

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
0x1004d420  cmp     ecx, ___security_cookie
0x1004d426  jnz     short loc_1004D42B
0x1004d428  retn    0
0x1004d42b  jmp     ___report_gsfailure
```
