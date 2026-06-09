# FileStream::Write(void const *,ulong,ulong *)

- ea: `0x180038290`
- end: `0x1800382c6`
- name: `?Write@FileStream@@UEAAJPEBXKPEAK@Z`
- size: `54`
- prototype: `__int64 __fastcall(FileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180038290`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800382af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800382af`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800382a1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800382a1`

## pseudocode

```c
signed int __fastcall FileStream::Write(HANDLE *this, const void *a2, DWORD a3, unsigned int *a4)
{
  signed int result; // eax

  if ( WriteFile(this[1], a2, a3, a4, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180038290  sub     rsp, 38h
0x180038294  mov     rcx, [rcx+8]; hFile
0x180038298  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800382a1  call    cs:__imp_WriteFile
0x1800382a7  test    eax, eax
0x1800382a9  jz      short loc_1800382AF
0x1800382ab  xor     eax, eax
0x1800382ad  jmp     short loc_1800382C1
0x1800382af  call    cs:__imp_GetLastError
0x1800382b5  test    eax, eax
0x1800382b7  jle     short loc_1800382C1
0x1800382b9  movzx   eax, ax
0x1800382bc  or      eax, 80070000h
0x1800382c1  add     rsp, 38h
0x1800382c5  retn
```
