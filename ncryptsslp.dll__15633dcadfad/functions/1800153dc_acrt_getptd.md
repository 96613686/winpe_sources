# __acrt_getptd

- ea: `0x1800153dc`
- end: `0x1800153f5`
- name: `__acrt_getptd`
- size: `25`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180015934`
- `0x180015fd4`
- `0x180016668`
- `0x180016dcc`
- `0x180017904`
- `0x180018170`
- `0x180018400`

## callees

- `0x1800150f8`
- `0x1800153dc`
- `0x180015444`

## pseudocode

```c
__int64 _acrt_getptd()
{
  __int64 result; // rax

  result = _acrt_getptd_noexit();
  if ( !result )
    abort();
  return result;
}

```

## disassembly

```asm
0x1800153dc  sub     rsp, 28h
0x1800153e0  call    __acrt_getptd_noexit
0x1800153e5  test    rax, rax
0x1800153e8  jz      short loc_1800153EF
0x1800153ea  add     rsp, 28h
0x1800153ee  retn
0x1800153ef  call    abort
```
