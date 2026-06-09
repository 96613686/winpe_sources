# sub_1800CDDA8

- ea: `0x1800cdda8`
- end: `0x1800cddc1`
- name: `sub_1800CDDA8`
- size: `25`
- prototype: ``
- caller_count: `36`
- callee_count: `3`
- tags: ``

## callers

- `0x1800cca08`
- `0x1800cca64`
- `0x1800ccac0`
- `0x1800cd4bc`
- `0x1800cd4fc`
- `0x1800cd558`
- `0x1800cd570`
- `0x1800cd588`
- `0x1800cd5a8`
- `0x1800cd5c8`
- `0x1800cd640`
- `0x1800cd830`
- `0x1800cd898`
- `0x1800cd904`
- `0x1800cd91c`
- `0x1800ce818`
- `0x1800cecd4`
- `0x1800cf1f0`
- `0x1800cf430`
- `0x1800cf964`
- `0x1800cfb78`
- `0x1800cfe04`
- `0x1800d0090`
- `0x1800d02b0`
- `0x1800d06ac`
- `0x1800d0738`
- `0x1800d0770`
- `0x1800d0914`
- `0x1801386a5`
- `0x180138752`
- `0x18013880d`
- `0x1801388a5`
- `0x1801388e8`
- `0x180138996`
- `0x180138a40`
- `0x180138a7f`

## callees

- `0x1800cdda8`
- `0x1800cddc8`
- `0x1800fbfce`

## pseudocode

```c
__int64 sub_1800CDDA8()
{
  __int64 result; // rax

  result = sub_1800CDDC8();
  if ( !result )
    abort();
  return result;
}

```

## disassembly

```asm
0x1800cdda8  sub     rsp, 28h
0x1800cddac  call    sub_1800CDDC8
0x1800cddb1  test    rax, rax
0x1800cddb4  jz      short loc_1800CDDBB
0x1800cddb6  add     rsp, 28h
0x1800cddba  retn
0x1800cddbb  call    abort
```
