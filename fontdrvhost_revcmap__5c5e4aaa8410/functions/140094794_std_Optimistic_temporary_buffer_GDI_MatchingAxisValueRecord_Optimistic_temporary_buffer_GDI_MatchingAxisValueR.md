# std::_Optimistic_temporary_buffer<GDI::MatchingAxisValueRecord>::~_Optimistic_temporary_buffer<GDI::MatchingAxisValueRecord>(void)

- ea: `0x140094794`
- end: `0x1400947af`
- name: `??1?$_Optimistic_temporary_buffer@UMatchingAxisValueRecord@GDI@@@std@@QEAA@XZ`
- size: `27`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140059bec`
- `0x14005dedc`
- `0x1400972ed`

## callees

- `0x140076620`
- `0x140094794`

## pseudocode

```c
void __fastcall std::_Optimistic_temporary_buffer<GDI::MatchingAxisValueRecord>::~_Optimistic_temporary_buffer<GDI::MatchingAxisValueRecord>(
        __int64 a1)
{
  if ( *(_QWORD *)(a1 + 8) > 0x80u )
    operator delete(*(void **)a1);
}

```

## disassembly

```asm
0x140094794  sub     rsp, 28h
0x140094798  cmp     qword ptr [rcx+8], 80h
0x1400947a0  jbe     short loc_1400947AA
0x1400947a2  mov     rcx, [rcx]; Block
0x1400947a5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400947aa  add     rsp, 28h
0x1400947ae  retn
```
