# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x140004f44`
- end: `0x140004f71`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `45`
- prototype: `void __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140004fc4`
- `0x14000dbe0`
- `0x14000de94`
- `0x14000df28`
- `0x14000e2b0`
- `0x14000f85c`
- `0x140011a4c`
- `0x140012a94`
- `0x140012d24`

## callees

- `0x140003218`
- `0x140004f44`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(_QWORD *a1, unsigned __int64 a2)
{
  if ( a2 >= 0x1000 )
  {
    if ( (unsigned __int64)a1 - *(a1 - 1) - 8 > 0x1F )
      __fastfail(5u);
    a2 += 39LL;
    a1 = (_QWORD *)*(a1 - 1);
  }
  operator delete(a1, a2);
}

```

## disassembly

```asm
0x140004f44  cmp     rdx, 1000h
0x140004f4b  jb      short loc_140004F65
0x140004f4d  mov     rax, [rcx-8]
0x140004f51  sub     rcx, rax
0x140004f54  sub     rcx, 8
0x140004f58  cmp     rcx, 1Fh
0x140004f5c  ja      short loc_140004F6A
0x140004f5e  add     rdx, 27h ; '''; unsigned __int64
0x140004f62  mov     rcx, rax; void *
0x140004f65  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004f6a  mov     ecx, 5
0x140004f6f  int     29h; Win8: RtlFailFast(ecx)
```
