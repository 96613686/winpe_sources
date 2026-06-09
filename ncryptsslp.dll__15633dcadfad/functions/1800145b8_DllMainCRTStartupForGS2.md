# _DllMainCRTStartupForGS2

- ea: `0x1800145b8`
- end: `0x1800145d0`
- name: `_DllMainCRTStartupForGS2`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012220`

## callees

- `0x180014508`
- `0x1800145b8`

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
0x1800145b8  sub     rsp, 28h
0x1800145bc  cmp     edx, 1
0x1800145bf  jnz     short loc_1800145C6
0x1800145c1  call    __security_init_cookie
0x1800145c6  mov     eax, 1
0x1800145cb  add     rsp, 28h
0x1800145cf  retn
```
