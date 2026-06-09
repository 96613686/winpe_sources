# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x180009014`
- end: `0x180009041`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `45`
- prototype: `void __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `21`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009154`
- `0x1800094bc`
- `0x1800095fc`
- `0x1800096ac`
- `0x18000a570`
- `0x18000a594`
- `0x18000a5b8`
- `0x18000a614`
- `0x18000a6d0`
- `0x18000a76c`
- `0x18000bd10`
- `0x18000bec8`
- `0x18000c498`
- `0x18000d578`
- `0x18000d8e8`
- `0x18000ddac`
- `0x18000ddec`
- `0x18000dee0`
- `0x18000df04`
- `0x18000ed90`
- `0x18000fcc4`

## callees

- `0x180001a74`
- `0x180009014`

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
0x180009014  cmp     rdx, 1000h
0x18000901b  jb      short loc_180009035
0x18000901d  mov     rax, [rcx-8]
0x180009021  sub     rcx, rax
0x180009024  sub     rcx, 8
0x180009028  cmp     rcx, 1Fh
0x18000902c  ja      short loc_18000903A
0x18000902e  add     rdx, 27h ; '''; unsigned __int64
0x180009032  mov     rcx, rax; void *
0x180009035  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000903a  mov     ecx, 5
0x18000903f  int     29h; Win8: RtlFailFast(ecx)
```
