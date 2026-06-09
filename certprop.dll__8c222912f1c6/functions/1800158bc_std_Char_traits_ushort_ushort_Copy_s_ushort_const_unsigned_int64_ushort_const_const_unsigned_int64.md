# std::_Char_traits<ushort,ushort>::_Copy_s(ushort * const,unsigned __int64,ushort const * const,unsigned __int64)

- ea: `0x1800158bc`
- end: `0x1800158e9`
- name: `?_Copy_s@?$_Char_traits@GG@std@@SAPEAGQEAG_KQEBG1@Z`
- size: `45`
- prototype: `void *__fastcall(void *, unsigned __int64, const void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008e90`

## callees

- `0x1800158bc`
- `0x1800243f8`

## pseudocode

```c
void *__fastcall std::_Char_traits<unsigned short,unsigned short>::_Copy_s(
        void *a1,
        unsigned __int64 a2,
        const void *a3,
        unsigned __int64 a4)
{
  if ( a4 > a2 )
    __fastfail(5u);
  memcpy_0(a1, a3, 2 * a4);
  return a1;
}

```

## disassembly

```asm
0x1800158bc  push    rbx
0x1800158be  sub     rsp, 20h
0x1800158c2  mov     rax, r8
0x1800158c5  mov     rbx, rcx
0x1800158c8  cmp     r9, rdx
0x1800158cb  jbe     short loc_1800158D4
0x1800158cd  mov     ecx, 5; void *
0x1800158d2  int     29h; Win8: RtlFailFast(ecx)
0x1800158d4  lea     r8, [r9+r9]; Size
0x1800158d8  mov     rdx, rax; Src
0x1800158db  call    memcpy_0
0x1800158e0  mov     rax, rbx
0x1800158e3  add     rsp, 20h
0x1800158e7  pop     rbx
0x1800158e8  retn
```
