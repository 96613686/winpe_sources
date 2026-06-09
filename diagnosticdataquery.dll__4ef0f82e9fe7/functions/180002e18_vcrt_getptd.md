# __vcrt_getptd

- ea: `0x180002e18`
- end: `0x180002e31`
- name: `__vcrt_getptd`
- size: `25`
- prototype: `__int64()`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x180001fc8`
- `0x180002614`
- `0x180002654`
- `0x1800026b0`
- `0x1800026c8`
- `0x1800026e0`
- `0x180002700`
- `0x180002720`
- `0x180002890`
- `0x180002910`
- `0x180002978`
- `0x1800033d8`
- `0x1800038f4`
- `0x180003e28`
- `0x1800040a8`
- `0x1800042e0`
- `0x1800046dc`
- `0x180004768`
- `0x1800047a0`

## callees

- `0x180002e18`
- `0x180002e38`
- `0x180005152`

## pseudocode

```c
__int64 _vcrt_getptd()
{
  __int64 result; // rax

  result = _vcrt_getptd_noexit();
  if ( !result )
    abort_0();
  return result;
}

```

## disassembly

```asm
0x180002e18  sub     rsp, 28h
0x180002e1c  call    __vcrt_getptd_noexit
0x180002e21  test    rax, rax
0x180002e24  jz      short loc_180002E2B
0x180002e26  add     rsp, 28h
0x180002e2a  retn
0x180002e2b  call    abort_0
```
