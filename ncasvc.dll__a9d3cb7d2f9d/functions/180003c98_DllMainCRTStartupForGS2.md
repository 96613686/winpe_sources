# _DllMainCRTStartupForGS2

- ea: `0x180003c98`
- end: `0x180003cb0`
- name: `_DllMainCRTStartupForGS2`
- size: `24`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000343c`

## callees

- `0x180003c98`
- `0x1800041b4`

## pseudocode

```c
__int64 __fastcall DllMainCRTStartupForGS2(__int64 a1, int a2)
{
  if ( a2 == 1 )
    _security_init_cookie();
  return 1;
}

```

## disassembly

```asm
0x180003c98  sub     rsp, 28h
0x180003c9c  cmp     edx, 1
0x180003c9f  jnz     short loc_180003CA6
0x180003ca1  call    __security_init_cookie
0x180003ca6  mov     eax, 1
0x180003cab  add     rsp, 28h
0x180003caf  retn
```
