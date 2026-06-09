# XMLParserShimFileStream::Write(void const *,ulong,ulong *)

- ea: `0x1800303b0`
- end: `0x1800303e4`
- name: `?Write@XMLParserShimFileStream@@UEAAJPEBXKPEAK@Z`
- size: `52`
- prototype: `__int64 __fastcall(XMLParserShimFileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x1800303b0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1800303ce`
- `KERNEL32!WriteFile` at `0x1800303ce`

## pseudocode

```c
__int64 __fastcall XMLParserShimFileStream::Write(HANDLE *this, const void *a2, DWORD a3, unsigned int *a4)
{
  if ( *((_BYTE *)this + 24) )
    return 2147500037LL;
  else
    return !WriteFile(this[2], a2, a3, a4, 0) ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x1800303b0  sub     rsp, 38h
0x1800303b4  cmp     byte ptr [rcx+18h], 0
0x1800303b8  jz      short loc_1800303C1
0x1800303ba  mov     eax, 80004005h
0x1800303bf  jmp     short loc_1800303DF
0x1800303c1  mov     rcx, [rcx+10h]; hFile
0x1800303c5  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800303ce  call    cs:__imp_WriteFile
0x1800303d4  neg     eax
0x1800303d6  sbb     eax, eax
0x1800303d8  not     eax
0x1800303da  and     eax, 80004005h
0x1800303df  add     rsp, 38h
0x1800303e3  retn
```
