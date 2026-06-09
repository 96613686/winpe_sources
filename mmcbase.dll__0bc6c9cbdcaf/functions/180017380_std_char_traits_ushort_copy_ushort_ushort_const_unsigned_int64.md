# std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)

- ea: `0x180017380`
- end: `0x18001739c`
- name: `?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `28`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180016e04`
- `0x180016fc0`
- `0x180017024`
- `0x1800170ec`
- `0x1800171b0`
- `0x1800172dc`

## callees

- `0x18000a506`
- `0x180017380`

## pseudocode

```c
void *__fastcall std::char_traits<unsigned short>::copy(void *a1, const void *a2, __int64 a3)
{
  if ( a3 )
    return memcpy_0(a1, a2, 2 * a3);
  return a1;
}

```

## disassembly

```asm
0x180017380  sub     rsp, 28h
0x180017384  test    r8, r8
0x180017387  jz      short loc_180017394
0x180017389  add     r8, r8; Size
0x18001738c  call    memcpy_0
0x180017391  mov     rcx, rax
0x180017394  mov     rax, rcx
0x180017397  add     rsp, 28h
0x18001739b  retn
```
