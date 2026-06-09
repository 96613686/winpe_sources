# CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::ReadAt<TupleHeader>(unsigned __int64,unsigned __int64)

- ea: `0x140045520`
- end: `0x140045539`
- name: `??$ReadAt@UTupleHeader@@@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAAEBUTupleHeader@@_K0@Z`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140044e14`
- `0x140045194`

## callees

- `0x140045520`
- `0x14007327c`

## pseudocode

```c
__int64 __fastcall CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::ReadAt<TupleHeader>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  if ( a1[1] < 4u )
    CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(
      a1,
      a2,
      a3,
      a4);
  return *a1;
}

```

## disassembly

```asm
0x140045520  sub     rsp, 28h
0x140045524  cmp     qword ptr [rcx+8], 4
0x140045529  jb      short loc_140045533
0x14004552b  mov     rax, [rcx]
0x14004552e  add     rsp, 28h
0x140045532  retn
0x140045533  call    ?FailOutOfRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAXXZ; CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(void)
```
