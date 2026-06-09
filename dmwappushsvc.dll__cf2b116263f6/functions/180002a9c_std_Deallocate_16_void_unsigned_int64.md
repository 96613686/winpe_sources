# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x180002a9c`
- end: `0x180002ac9`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `45`
- prototype: `void __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002ad0`
- `0x180004248`
- `0x1800042dc`
- `0x180004320`
- `0x180006fa8`
- `0x180007820`
- `0x180011ca0`

## callees

- `0x180001a94`
- `0x180002a9c`

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
0x180002a9c  cmp     rdx, 1000h
0x180002aa3  jb      short loc_180002ABD
0x180002aa5  mov     rax, [rcx-8]
0x180002aa9  sub     rcx, rax
0x180002aac  sub     rcx, 8
0x180002ab0  cmp     rcx, 1Fh
0x180002ab4  ja      short loc_180002AC2
0x180002ab6  add     rdx, 27h ; '''
0x180002aba  mov     rcx, rax; Block
0x180002abd  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002ac2  mov     ecx, 5
0x180002ac7  int     29h; Win8: RtlFailFast(ecx)
```
