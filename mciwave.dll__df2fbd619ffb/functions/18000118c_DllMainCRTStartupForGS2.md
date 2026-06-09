# _DllMainCRTStartupForGS2

- ea: `0x18000118c`
- end: `0x1800011a4`
- name: `_DllMainCRTStartupForGS2`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800053f0`

## callees

- `0x18000118c`
- `0x1800011ac`

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
0x18000118c  sub     rsp, 28h
0x180001190  cmp     edx, 1
0x180001193  jnz     short loc_18000119A
0x180001195  call    __security_init_cookie
0x18000119a  mov     eax, 1
0x18000119f  add     rsp, 28h
0x1800011a3  retn
```
