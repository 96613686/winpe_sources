# _DllMainCRTStartupForGS2

- ea: `0x18000c1b8`
- end: `0x18000c1d0`
- name: `_DllMainCRTStartupForGS2`
- size: `24`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009aa4`

## callees

- `0x18000c1b8`
- `0x18000c360`

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
0x18000c1b8  sub     rsp, 28h
0x18000c1bc  cmp     edx, 1
0x18000c1bf  jnz     short loc_18000C1C6
0x18000c1c1  call    __security_init_cookie
0x18000c1c6  mov     eax, 1
0x18000c1cb  add     rsp, 28h
0x18000c1cf  retn
```
