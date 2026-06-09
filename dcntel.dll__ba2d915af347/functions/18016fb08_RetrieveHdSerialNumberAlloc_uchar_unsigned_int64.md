# RetrieveHdSerialNumberAlloc(uchar * *,unsigned __int64 *)

- ea: `0x18016fb08`
- end: `0x18016fcd3`
- name: `?RetrieveHdSerialNumberAlloc@@YAJPEAPEAEPEA_K@Z`
- size: `459`
- prototype: `__int64 __fastcall(unsigned __int8 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18016f40c`

## callees

- `0x180008dc0`
- `0x18016f658`
- `0x18016fb08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016fb8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016fc46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016fb8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016fc46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18016fc7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18016fc7e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18016fbfb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18016fbfb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18016fc3c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18016fc3c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18016fb84`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18016fb84`

## pseudocode

```c
__int64 __fastcall RetrieveHdSerialNumberAlloc(unsigned __int8 **a1, unsigned __int64 *a2)
{
  UINT SystemDirectoryW; // eax
  signed int LastError; // eax
  signed int SerialNumberForDiskByNumberAlloc; // ebx
  __int64 v7; // rcx
  HANDLE FileW; // rdi
  unsigned int v9; // esi
  signed int v10; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  __int128 OutBuffer; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v14; // [rsp+58h] [rbp-A8h]
  WCHAR FileName[12]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  wcscpy(FileName, L"\\\\.\\X:");
  BytesReturned = 0;
  OutBuffer = 0;
  v14 = 0;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( !SystemDirectoryW )
    goto LABEL_2;
  if ( SystemDirectoryW > 0x104 )
    return (unsigned int)-2147024774;
  v7 = -1;
  do
    ++v7;
  while ( FileName[v7] );
  FileName[v7 - 2] = Buffer[0];
  FileW = CreateFileW(FileName, 0, 3u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_2:
    LastError = GetLastError();
    SerialNumberForDiskByNumberAlloc = LastError;
    if ( LastError > 0 )
      SerialNumberForDiskByNumberAlloc = (unsigned __int16)LastError | 0x80070000;
    if ( SerialNumberForDiskByNumberAlloc >= 0 )
      return (unsigned int)-2147467259;
  }
  else
  {
    v9 = 0;
    if ( DeviceIoControl(FileW, 0x560000u, 0, 0, &OutBuffer, 0x20u, &BytesReturned, 0) )
    {
      if ( (_DWORD)OutBuffer )
      {
        v9 = DWORD2(OutBuffer);
        SerialNumberForDiskByNumberAlloc = 0;
      }
      else
      {
        SerialNumberForDiskByNumberAlloc = -2147019873;
      }
    }
    else
    {
      v10 = GetLastError();
      SerialNumberForDiskByNumberAlloc = v10;
      if ( v10 > 0 )
        SerialNumberForDiskByNumberAlloc = (unsigned __int16)v10 | 0x80070000;
      if ( SerialNumberForDiskByNumberAlloc >= 0 )
        SerialNumberForDiskByNumberAlloc = -2147467259;
    }
    CloseHandle(FileW);
    if ( SerialNumberForDiskByNumberAlloc >= 0 )
    {
      SerialNumberForDiskByNumberAlloc = GetSerialNumberForDiskByNumberAlloc(a1, a2, v9);
      if ( SerialNumberForDiskByNumberAlloc >= 0 )
        return 0;
    }
  }
  return (unsigned int)SerialNumberForDiskByNumberAlloc;
}

```

## disassembly

```asm
0x18016fb08  mov     [rsp-8+arg_10], rbx
0x18016fb0d  mov     [rsp-8+arg_18], rsi
0x18016fb12  push    rbp
0x18016fb13  push    rdi
0x18016fb14  push    r12
0x18016fb16  push    r14
0x18016fb18  push    r15
0x18016fb1a  lea     rbp, [rsp-1A0h]
0x18016fb22  sub     rsp, 2A0h
0x18016fb29  mov     rax, cs:__security_cookie
0x18016fb30  xor     rax, rsp
0x18016fb33  mov     [rbp+1C0h+var_30], rax
0x18016fb3a  mov     eax, dword ptr cs:asc_1801B5940+8; "X:"
0x18016fb40  xorps   xmm0, xmm0
0x18016fb43  movsd   xmm1, qword ptr cs:asc_1801B5940; "\\\\.\\X:"
0x18016fb4b  mov     r15, rdx
0x18016fb4e  mov     [rsp+2C0h+var_250], eax
0x18016fb52  mov     r14, rcx
0x18016fb55  movzx   eax, word ptr cs:asc_1801B5940+0Ch; ""
0x18016fb5c  lea     rcx, [rbp+1C0h+Buffer]; lpBuffer
0x18016fb60  mov     ebx, 104h
0x18016fb65  mov     [rsp+2C0h+var_24C], ax
0x18016fb6a  xor     r12d, r12d
0x18016fb6d  movsd   qword ptr [rsp+2C0h+FileName], xmm1
0x18016fb73  mov     edx, ebx; uSize
0x18016fb75  mov     [rsp+2C0h+BytesReturned], r12d
0x18016fb7a  movups  [rsp+2C0h+OutBuffer], xmm0
0x18016fb7f  movups  [rsp+2C0h+var_268], xmm0
0x18016fb84  call    cs:__imp_GetSystemDirectoryW
0x18016fb8a  test    eax, eax
0x18016fb8c  jnz     short loc_18016FBB5
0x18016fb8e  call    cs:__imp_GetLastError
0x18016fb94  mov     ebx, eax
0x18016fb96  test    eax, eax
0x18016fb98  jle     short loc_18016FBA3
0x18016fb9a  movzx   ebx, ax
0x18016fb9d  or      ebx, 80070000h
0x18016fba3  test    ebx, ebx
0x18016fba5  js      loc_18016FCA6
0x18016fbab  mov     ebx, 80004005h
0x18016fbb0  jmp     loc_18016FCA6
0x18016fbb5  cmp     eax, ebx
0x18016fbb7  ja      loc_18016FCA1
0x18016fbbd  lea     rax, [rsp+2C0h+FileName]
0x18016fbc2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18016fbc6  inc     rcx
0x18016fbc9  cmp     [rax+rcx*2], r12w
0x18016fbce  jnz     short loc_18016FBC6
0x18016fbd0  movzx   eax, [rbp+1C0h+Buffer]
0x18016fbd4  mov     r8d, 3; dwShareMode
0x18016fbda  mov     word ptr [rsp+rcx*2+2C0h+var_268+0Ch], ax
0x18016fbdf  xor     r9d, r9d; lpSecurityAttributes
0x18016fbe2  mov     [rsp+2C0h+hTemplateFile], r12; hTemplateFile
0x18016fbe7  lea     rcx, [rsp+2C0h+FileName]; lpFileName
0x18016fbec  mov     [rsp+2C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18016fbf4  xor     edx, edx; dwDesiredAccess
0x18016fbf6  mov     [rsp+2C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18016fbfb  call    cs:__imp_CreateFileW
0x18016fc01  mov     rdi, rax
0x18016fc04  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18016fc08  jz      short loc_18016FB8E
0x18016fc0a  mov     [rsp+2C0h+lpOverlapped], r12; lpOverlapped
0x18016fc0f  lea     rax, [rsp+2C0h+BytesReturned]
0x18016fc14  mov     [rsp+2C0h+hTemplateFile], rax; lpBytesReturned
0x18016fc19  xor     r9d, r9d; nInBufferSize
0x18016fc1c  lea     rax, [rsp+2C0h+OutBuffer]
0x18016fc21  mov     [rsp+2C0h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x18016fc29  xor     r8d, r8d; lpInBuffer
0x18016fc2c  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rax; lpOutBuffer
0x18016fc31  mov     edx, 560000h; dwIoControlCode
0x18016fc36  mov     rcx, rdi; hDevice
0x18016fc39  mov     esi, r12d
0x18016fc3c  call    cs:__imp_DeviceIoControl
0x18016fc42  test    eax, eax
0x18016fc44  jnz     short loc_18016FC66
0x18016fc46  call    cs:__imp_GetLastError
0x18016fc4c  mov     ebx, eax
0x18016fc4e  test    eax, eax
0x18016fc50  jle     short loc_18016FC5B
0x18016fc52  movzx   ebx, ax
0x18016fc55  or      ebx, 80070000h
0x18016fc5b  test    ebx, ebx
0x18016fc5d  js      short loc_18016FC7B
0x18016fc5f  mov     ebx, 80004005h
0x18016fc64  jmp     short loc_18016FC7B
0x18016fc66  cmp     dword ptr [rsp+2C0h+OutBuffer], r12d
0x18016fc6b  jz      short loc_18016FC76
0x18016fc6d  mov     esi, dword ptr [rsp+2C0h+OutBuffer+8]
0x18016fc71  mov     ebx, r12d
0x18016fc74  jmp     short loc_18016FC7B
0x18016fc76  mov     ebx, 8007139Fh
0x18016fc7b  mov     rcx, rdi; hObject
0x18016fc7e  call    cs:__imp_CloseHandle
0x18016fc84  test    ebx, ebx
0x18016fc86  js      short loc_18016FCA6
0x18016fc88  mov     r8d, esi; unsigned int
0x18016fc8b  mov     rdx, r15; unsigned __int64 *
0x18016fc8e  mov     rcx, r14; unsigned __int8 **
0x18016fc91  call    ?GetSerialNumberForDiskByNumberAlloc@@YAJPEAPEAEPEA_KK@Z; GetSerialNumberForDiskByNumberAlloc(uchar * *,unsigned __int64 *,ulong)
0x18016fc96  mov     ebx, eax
0x18016fc98  test    eax, eax
0x18016fc9a  js      short loc_18016FCA6
0x18016fc9c  mov     ebx, r12d
0x18016fc9f  jmp     short loc_18016FCA6
0x18016fca1  mov     ebx, 8007007Ah
0x18016fca6  mov     eax, ebx
0x18016fca8  mov     rcx, [rbp+1C0h+var_30]
0x18016fcaf  xor     rcx, rsp; StackCookie
0x18016fcb2  call    __security_check_cookie
0x18016fcb7  lea     r11, [rsp+2C0h+var_20]
0x18016fcbf  mov     rbx, [r11+40h]
0x18016fcc3  mov     rsi, [r11+48h]
0x18016fcc7  mov     rsp, r11
0x18016fcca  pop     r15
0x18016fccc  pop     r14
0x18016fcce  pop     r12
0x18016fcd0  pop     rdi
0x18016fcd1  pop     rbp
0x18016fcd2  retn
```
