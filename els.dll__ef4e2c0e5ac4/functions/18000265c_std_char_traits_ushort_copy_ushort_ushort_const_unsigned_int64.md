# std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)

- ea: `0x18000265c`
- end: `0x180002678`
- name: `?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `28`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001010`
- `0x1800014a0`
- `0x180001620`
- `0x180001750`
- `0x180001910`
- `0x180001974`
- `0x180001a70`
- `0x180001b2c`
- `0x180001dd0`
- `0x180001f64`
- `0x180002044`
- `0x180002680`
- `0x180006040`

## callees

- `0x18000265c`
- `0x1800036a6`

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
0x18000265c  sub     rsp, 28h
0x180002660  test    r8, r8
0x180002663  jz      short loc_180002670
0x180002665  add     r8, r8; Size
0x180002668  call    memcpy_0
0x18000266d  mov     rcx, rax
0x180002670  mov     rax, rcx
0x180002673  add     rsp, 28h
0x180002677  retn
```
