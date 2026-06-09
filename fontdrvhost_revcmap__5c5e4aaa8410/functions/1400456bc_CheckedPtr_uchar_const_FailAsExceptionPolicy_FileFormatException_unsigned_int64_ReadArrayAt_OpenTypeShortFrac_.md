# CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::ReadArrayAt<OpenTypeShortFrac>(unsigned __int64,unsigned __int64)

- ea: `0x1400456bc`
- end: `0x1400456e5`
- name: `??$ReadArrayAt@UOpenTypeShortFrac@@@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAPEBUOpenTypeShortFrac@@_K0@Z`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140044e14`
- `0x140045194`

## callees

- `0x1400456bc`
- `0x14007327c`

## pseudocode

```c
unsigned __int64 __fastcall CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::ReadArrayAt<OpenTypeShortFrac>(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        __int64 a4)
{
  unsigned __int64 v4; // rax

  v4 = a1[1];
  if ( a2 > v4 || (v4 - a2) >> 1 < a3 )
    CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(
      a1,
      a2,
      a3,
      a4);
  return a2 + *a1;
}

```

## disassembly

```asm
0x1400456bc  sub     rsp, 28h
0x1400456c0  mov     rax, [rcx+8]
0x1400456c4  cmp     rdx, rax
0x1400456c7  ja      short loc_1400456DF
0x1400456c9  sub     rax, rdx
0x1400456cc  shr     rax, 1
0x1400456cf  cmp     rax, r8
0x1400456d2  jb      short loc_1400456DF
0x1400456d4  mov     rax, [rcx]
0x1400456d7  add     rax, rdx
0x1400456da  add     rsp, 28h
0x1400456de  retn
0x1400456df  call    ?FailOutOfRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAXXZ; CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(void)
```
