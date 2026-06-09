# FlushIoBuffer

- ea: `0x14000b24c`
- end: `0x14000b2bb`
- name: `FlushIoBuffer`
- size: `111`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000afd4`
- `0x14000c9dc`

## callees

- `0x14000b24c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000b283`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000b283`

## pseudocode

```c
void FlushIoBuffer()
{
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  if ( (_DWORD)qword_140055248
    && (!WriteFile(hObject, &WideCharStr, 2 * qword_140055248, &NumberOfBytesWritten, 0)
     || 2 * (_DWORD)qword_140055248 != NumberOfBytesWritten) )
  {
    g_FileErrorStringID = 802;
  }
  LODWORD(qword_140055248) = 0;
}

```

## disassembly

```asm
0x14000b24c  sub     rsp, 38h
0x14000b250  mov     r8d, dword ptr cs:qword_140055248
0x14000b257  mov     [rsp+38h+NumberOfBytesWritten], 0
0x14000b25f  test    r8d, r8d
0x14000b262  jz      short loc_14000B2AB
0x14000b264  mov     rcx, cs:hObject; hFile
0x14000b26b  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000b270  add     r8d, r8d; nNumberOfBytesToWrite
0x14000b273  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x14000b27c  lea     rdx, WideCharStr; lpBuffer
0x14000b283  call    cs:__imp_WriteFile
0x14000b28a  nop     dword ptr [rax+rax+00h]
0x14000b28f  test    eax, eax
0x14000b291  jz      short loc_14000B2A1
0x14000b293  mov     eax, dword ptr cs:qword_140055248
0x14000b299  add     eax, eax
0x14000b29b  cmp     eax, [rsp+38h+NumberOfBytesWritten]
0x14000b29f  jz      short loc_14000B2AB
0x14000b2a1  mov     cs:g_FileErrorStringID, 322h
0x14000b2ab  mov     dword ptr cs:qword_140055248, 0
0x14000b2b5  add     rsp, 38h
0x14000b2b9  retn
```
