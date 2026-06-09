# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x1800058c8`
- end: `0x1800058f5`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `45`
- prototype: `void __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002f04`
- `0x180002f94`
- `0x18000b610`

## callees

- `0x180004724`
- `0x1800058c8`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(_QWORD *a1, unsigned __int64 a2)
{
  if ( a2 >= 0x1000 )
  {
    if ( (unsigned __int64)a1 - *(a1 - 1) - 8 > 0x1F )
      __fastfail(5u);
    a1 = (_QWORD *)*(a1 - 1);
  }
  operator delete(a1);
}

```

## disassembly

```asm
0x1800058c8  cmp     rdx, 1000h
0x1800058cf  jb      short loc_1800058E9
0x1800058d1  mov     rax, [rcx-8]
0x1800058d5  sub     rcx, rax
0x1800058d8  sub     rcx, 8
0x1800058dc  cmp     rcx, 1Fh
0x1800058e0  ja      short loc_1800058EE
0x1800058e2  add     rdx, 27h ; '''
0x1800058e6  mov     rcx, rax; Block
0x1800058e9  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800058ee  mov     ecx, 5
0x1800058f3  int     29h; Win8: RtlFailFast(ecx)
```
