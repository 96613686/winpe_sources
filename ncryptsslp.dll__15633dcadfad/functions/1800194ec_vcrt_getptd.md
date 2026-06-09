# __vcrt_getptd

- ea: `0x1800194ec`
- end: `0x180019505`
- name: `__vcrt_getptd`
- size: `25`
- prototype: ``
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x180018b40`
- `0x180018bc0`
- `0x180018c28`
- `0x180018ea0`
- `0x180018efc`
- `0x180019308`
- `0x180019348`
- `0x1800193a4`
- `0x1800193bc`
- `0x1800193d4`
- `0x1800193f4`
- `0x180019414`
- `0x180019498`
- `0x180019b08`
- `0x180019fc4`
- `0x18001a31c`
- `0x18001a650`
- `0x18001a86c`
- `0x18001a8f8`

## callees

- `0x1800150f8`
- `0x1800194ec`
- `0x18001950c`

## pseudocode

```c
__int64 _vcrt_getptd()
{
  __int64 result; // rax

  result = _vcrt_getptd_noexit();
  if ( !result )
    abort();
  return result;
}

```

## disassembly

```asm
0x1800194ec  sub     rsp, 28h
0x1800194f0  call    __vcrt_getptd_noexit
0x1800194f5  test    rax, rax
0x1800194f8  jz      short loc_1800194FF
0x1800194fa  add     rsp, 28h
0x1800194fe  retn
0x1800194ff  call    abort
```
