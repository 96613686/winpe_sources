# CNtfsStream::SyncWriteAtFile(_ULARGE_INTEGER,void const *,ulong,ulong *)

- ea: `0x180058a80`
- end: `0x180058add`
- name: `?SyncWriteAtFile@CNtfsStream@@AEAAJT_ULARGE_INTEGER@@PEBXKPEAK@Z`
- size: `93`
- prototype: `int(CNtfsStream *__hidden this, union _ULARGE_INTEGER, const void *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180040240`
- `0x180058cc0`

## callees

- `0x180058a80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058ac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058ac0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180058ab6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180058ab6`

## pseudocode

```c
__int64 __fastcall CNtfsStream::SyncWriteAtFile(
        CNtfsStream *this,
        union _ULARGE_INTEGER a2,
        const void *a3,
        DWORD a4,
        unsigned int *lpNumberOfBytesWritten)
{
  unsigned int v5; // ebx
  signed int LastError; // eax

  *((union _ULARGE_INTEGER *)this + 21) = a2;
  v5 = 0;
  if ( !WriteFile(*((HANDLE *)this + 12), a3, a4, lpNumberOfBytesWritten, (LPOVERLAPPED)((char *)this + 152)) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v5;
}

```

## disassembly

```asm
0x180058a80  push    rbx
0x180058a82  sub     rsp, 30h
0x180058a86  lea     rax, [rcx+98h]
0x180058a8d  mov     r10d, r9d
0x180058a90  mov     r9, [rsp+38h+lpNumberOfBytesWritten]; lpNumberOfBytesWritten
0x180058a95  mov     r11, r8
0x180058a98  mov     [rax+10h], edx
0x180058a9b  mov     r8d, r10d; nNumberOfBytesToWrite
0x180058a9e  shr     rdx, 20h
0x180058aa2  xor     ebx, ebx
0x180058aa4  mov     [rcx+0ACh], edx
0x180058aaa  mov     rdx, r11; lpBuffer
0x180058aad  mov     rcx, [rcx+60h]; hFile
0x180058ab1  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x180058ab6  call    cs:__imp_WriteFile
0x180058abc  test    eax, eax
0x180058abe  jnz     short loc_180058AD5
0x180058ac0  call    cs:__imp_GetLastError
0x180058ac6  mov     ebx, eax
0x180058ac8  test    eax, eax
0x180058aca  jle     short loc_180058AD5
0x180058acc  movzx   ebx, ax
0x180058acf  or      ebx, 80070000h
0x180058ad5  mov     eax, ebx
0x180058ad7  add     rsp, 30h
0x180058adb  pop     rbx
0x180058adc  retn
```
