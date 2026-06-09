# SortByTag

- ea: `0x18000f294`
- end: `0x18000f2bd`
- name: `SortByTag`
- size: `41`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800079b8`
- `0x180009978`
- `0x18000c874`
- `0x18000d45c`

## callees

- `0x18000f294`

## import_xrefs

- `msvcrt!qsort` at `0x18000f2b2`
- `msvcrt!qsort` at `0x18000f2b2`

## pseudocode

```c
void __fastcall SortByTag(void *a1, unsigned __int16 a2)
{
  if ( a1 )
  {
    if ( a2 )
      qsort(a1, a2, 0x10u, (_CoreCrtNonSecureSearchSortCompareFunction)AscendingTagCompare);
  }
}

```

## disassembly

```asm
0x18000f294  sub     rsp, 28h
0x18000f298  test    rcx, rcx
0x18000f29b  jz      short loc_18000F2B8
0x18000f29d  test    dx, dx
0x18000f2a0  jz      short loc_18000F2B8
0x18000f2a2  movzx   edx, dx; NumOfElements
0x18000f2a5  lea     r9, AscendingTagCompare; CompareFunction
0x18000f2ac  mov     r8d, 10h; SizeOfElements
0x18000f2b2  call    cs:__imp_qsort
0x18000f2b8  add     rsp, 28h
0x18000f2bc  retn
```
