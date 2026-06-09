# FlushIoBuffer

- ea: `0x14000ab90`
- end: `0x14000abf8`
- name: `FlushIoBuffer`
- size: `104`
- prototype: `void()`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000a934`
- `0x14000c1e8`

## callees

- `0x14000ab90`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000abc7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000abc7`

## pseudocode

```c
void FlushIoBuffer()
{
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  if ( (_DWORD)qword_140054248
    && (!WriteFile(hObject, &WideCharStr, 2 * qword_140054248, &NumberOfBytesWritten, 0)
     || 2 * (_DWORD)qword_140054248 != NumberOfBytesWritten) )
  {
    g_FileErrorStringID = 802;
  }
  LODWORD(qword_140054248) = 0;
}

```

## disassembly

```asm
0x14000ab90  sub     rsp, 38h
0x14000ab94  mov     r8d, dword ptr cs:qword_140054248
0x14000ab9b  mov     [rsp+38h+NumberOfBytesWritten], 0
0x14000aba3  test    r8d, r8d
0x14000aba6  jz      short loc_14000ABE9
0x14000aba8  mov     rcx, cs:hObject; hFile
0x14000abaf  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000abb4  add     r8d, r8d; nNumberOfBytesToWrite
0x14000abb7  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x14000abc0  lea     rdx, WideCharStr; lpBuffer
0x14000abc7  call    cs:__imp_WriteFile
0x14000abcd  test    eax, eax
0x14000abcf  jz      short loc_14000ABDF
0x14000abd1  mov     eax, dword ptr cs:qword_140054248
0x14000abd7  add     eax, eax
0x14000abd9  cmp     eax, [rsp+38h+NumberOfBytesWritten]
0x14000abdd  jz      short loc_14000ABE9
0x14000abdf  mov     cs:g_FileErrorStringID, 322h
0x14000abe9  mov     dword ptr cs:qword_140054248, 0
0x14000abf3  add     rsp, 38h
0x14000abf7  retn
```
