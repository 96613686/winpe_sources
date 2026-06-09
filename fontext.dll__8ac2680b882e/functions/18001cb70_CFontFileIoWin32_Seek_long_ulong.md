# CFontFileIoWin32::Seek(long,ulong)

- ea: `0x18001cb70`
- end: `0x18001cb9d`
- name: `?Seek@CFontFileIoWin32@@UEAAKJK@Z`
- size: `45`
- prototype: `unsigned int(CFontFileIoWin32 *__hidden this, int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18001cb70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb8d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001cb82`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001cb82`

## pseudocode

```c
__int64 __fastcall CFontFileIoWin32::Seek(HANDLE *this, LONG a2, DWORD a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( SetFilePointer(this[2], a2, 0, a3) == -1 )
    return GetLastError();
  return v3;
}

```

## disassembly

```asm
0x18001cb70  push    rbx
0x18001cb72  sub     rsp, 20h
0x18001cb76  mov     rcx, [rcx+10h]; hFile
0x18001cb7a  mov     r9d, r8d; dwMoveMethod
0x18001cb7d  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001cb80  xor     ebx, ebx
0x18001cb82  call    cs:__imp_SetFilePointer
0x18001cb88  cmp     eax, 0FFFFFFFFh
0x18001cb8b  jnz     short loc_18001CB95
0x18001cb8d  call    cs:__imp_GetLastError
0x18001cb93  mov     ebx, eax
0x18001cb95  mov     eax, ebx
0x18001cb97  add     rsp, 20h
0x18001cb9b  pop     rbx
0x18001cb9c  retn
```
