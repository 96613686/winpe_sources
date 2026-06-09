# CSimpStream::Init(CSimpStorage *,void *,ulong)

- ea: `0x180023d24`
- end: `0x180023d86`
- name: `?Init@CSimpStream@@QEAAJPEAUCSimpStorage@@PEAXK@Z`
- size: `98`
- prototype: `int(CSimpStream *__hidden this, struct CSimpStorage *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180023b80`

## callees

- `0x180023d24`
- `0x180026bc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d74`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180023d53`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180023d53`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180023d62`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180023d62`

## pseudocode

```c
__int64 __fastcall CSimpStream::Init(CSimpStream *this, struct CSimpStorage *a2, void *a3, LONG a4)
{
  DWORD LastError; // eax

  *((_QWORD *)this + 5) = a3;
  *((_QWORD *)this + 4) = a2;
  *((_DWORD *)this + 5) = a4;
  *((_DWORD *)this + 6) = a4;
  *((_DWORD *)this + 4) = 1;
  if ( SetFilePointer(a3, a4, 0, 0) != -1 && SetEndOfFile(*((HANDLE *)this + 5)) )
    return 0;
  LastError = GetLastError();
  return Win32ErrorToScode(LastError);
}

```

## disassembly

```asm
0x180023d24  push    rbx
0x180023d26  sub     rsp, 20h
0x180023d2a  mov     eax, r9d
0x180023d2d  mov     [rcx+28h], r8
0x180023d31  mov     r10, r8
0x180023d34  mov     [rcx+20h], rdx
0x180023d38  mov     [rcx+14h], eax
0x180023d3b  mov     rbx, rcx
0x180023d3e  mov     [rcx+18h], eax
0x180023d41  xor     r9d, r9d; dwMoveMethod
0x180023d44  mov     dword ptr [rcx+10h], 1
0x180023d4b  xor     r8d, r8d; lpDistanceToMoveHigh
0x180023d4e  mov     rcx, r10; hFile
0x180023d51  mov     edx, eax; lDistanceToMove
0x180023d53  call    cs:__imp_SetFilePointer
0x180023d59  cmp     eax, 0FFFFFFFFh
0x180023d5c  jz      short loc_180023D74
0x180023d5e  mov     rcx, [rbx+28h]; hFile
0x180023d62  call    cs:__imp_SetEndOfFile
0x180023d68  test    eax, eax
0x180023d6a  jz      short loc_180023D74
0x180023d6c  xor     eax, eax
0x180023d6e  add     rsp, 20h
0x180023d72  pop     rbx
0x180023d73  retn
0x180023d74  call    cs:__imp_GetLastError
0x180023d7a  mov     ecx, eax; unsigned int
0x180023d7c  add     rsp, 20h
0x180023d80  pop     rbx
0x180023d81  jmp     ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
```
