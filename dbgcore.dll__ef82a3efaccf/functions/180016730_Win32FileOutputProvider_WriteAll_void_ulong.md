# Win32FileOutputProvider::WriteAll(void *,ulong)

- ea: `0x180016730`
- end: `0x180016797`
- name: `?WriteAll@Win32FileOutputProvider@@UEAAJPEAXK@Z`
- size: `103`
- prototype: `__int64 __fastcall(Win32FileOutputProvider *__hidden this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180016730`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001675d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001675d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016767`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180016753`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180016753`

## pseudocode

```c
signed int __fastcall Win32FileOutputProvider::WriteAll(Win32FileOutputProvider *this, void *a2, DWORD a3)
{
  void *v3; // rcx
  signed int result; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  v3 = (void *)*((_QWORD *)this + 1);
  NumberOfBytesWritten = 0;
  if ( WriteFile(v3, a2, a3, &NumberOfBytesWritten, 0) )
    return a3 != NumberOfBytesWritten ? 0x8007001D : 0;
  if ( !GetLastError() )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180016730  push    rbx
0x180016732  sub     rsp, 30h
0x180016736  mov     rcx, [rcx+8]; hFile
0x18001673a  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001673f  mov     ebx, r8d
0x180016742  mov     [rsp+38h+NumberOfBytesWritten], 0
0x18001674a  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180016753  call    cs:__imp_WriteFile
0x180016759  test    eax, eax
0x18001675b  jnz     short loc_180016782
0x18001675d  call    cs:__imp_GetLastError
0x180016763  test    eax, eax
0x180016765  jz      short loc_18001677B
0x180016767  call    cs:__imp_GetLastError
0x18001676d  test    eax, eax
0x18001676f  jle     short loc_180016791
0x180016771  movzx   eax, ax
0x180016774  or      eax, 80070000h
0x180016779  jmp     short loc_180016791
0x18001677b  mov     eax, 80004005h
0x180016780  jmp     short loc_180016791
0x180016782  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x180016786  sub     eax, ebx
0x180016788  neg     eax
0x18001678a  sbb     eax, eax
0x18001678c  and     eax, 8007001Dh
0x180016791  add     rsp, 30h
0x180016795  pop     rbx
0x180016796  retn
```
