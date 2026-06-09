# ATL::CAtlFile::Seek(__int64,ulong)

- ea: `0x18002e998`
- end: `0x18002e9d8`
- name: `?Seek@CAtlFile@ATL@@QEAAJ_JK@Z`
- size: `64`
- prototype: `__int64 __fastcall(ATL::CAtlFile *__hidden this, __int64, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001de88`
- `0x18002e458`
- `0x18002eb40`
- `0x18002ed8c`
- `0x18005bc00`

## callees

- `0x180019034`
- `0x18002e998`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x18002e9b6`
- `KERNEL32!SetFilePointer` at `0x18002e9b6`

## pseudocode

```c
__int64 __fastcall ATL::CAtlFile::Seek(void **this, __int64 a2)
{
  void *v2; // rcx
  int Error; // ecx
  __int64 result; // rax
  LONG DistanceToMoveHigh; // [rsp+3Ch] [rbp+14h] BYREF

  v2 = *this;
  DistanceToMoveHigh = HIDWORD(a2);
  if ( SetFilePointer(v2, a2, &DistanceToMoveHigh, 0) != -1 )
    return 0;
  Error = ATL::AtlHresultFromLastError();
  result = 0;
  if ( Error < 0 )
    return (unsigned int)Error;
  return result;
}

```

## disassembly

```asm
0x18002e998  sub     rsp, 28h
0x18002e99c  mov     rcx, [rcx]; hFile
0x18002e99f  lea     r8, [rsp+28h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18002e9a4  mov     rax, rdx
0x18002e9a7  mov     [rsp+28h+arg_8], edx
0x18002e9ab  sar     rax, 20h
0x18002e9af  xor     r9d, r9d; dwMoveMethod
0x18002e9b2  mov     [rsp+28h+DistanceToMoveHigh], eax
0x18002e9b6  call    cs:__imp_SetFilePointer
0x18002e9bc  cmp     eax, 0FFFFFFFFh
0x18002e9bf  jnz     short loc_18002E9D1
0x18002e9c1  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002e9c6  mov     ecx, eax
0x18002e9c8  xor     eax, eax
0x18002e9ca  test    ecx, ecx
0x18002e9cc  cmovs   eax, ecx
0x18002e9cf  jmp     short loc_18002E9D3
0x18002e9d1  xor     eax, eax
0x18002e9d3  add     rsp, 28h
0x18002e9d7  retn
```
