# ForceOnlineVolume(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800299e4`
- end: `0x180029b02`
- name: `?ForceOnlineVolume@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002a118`

## callees

- `0x180002690`
- `0x180008fac`
- `0x1800299e4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029a36`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029a36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029ad5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029ad5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029a84`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029ac6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029a84`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029ac6`

## pseudocode

```c
__int64 __fastcall ForceOnlineVolume(char *a1)
{
  bool v1; // cc
  char **v2; // rdi
  char *FileW; // rbx
  DWORD BytesReturned; // [rsp+40h] [rbp-18h] BYREF

  v1 = *((_QWORD *)a1 + 3) <= 7u;
  v2 = (char **)a1;
  BytesReturned = 0;
  if ( !v1 )
    a1 = *(char **)a1;
  FileW = (char *)CreateFileW((LPCWSTR)a1, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( DeviceIoControl(FileW, 0x560010u, 0, 0, 0, 0, &BytesReturned, 0) )
      DeviceIoControl(FileW, 0x56C008u, 0, 0, 0, 0, &BytesReturned, 0);
    CloseHandle(FileW);
  }
  return std::wstring::~wstring(v2);
}

```

## disassembly

```asm
0x1800299e4  mov     [rsp+arg_8], rbx
0x1800299e9  push    rdi
0x1800299ea  sub     rsp, 50h
0x1800299ee  mov     rax, cs:__security_cookie
0x1800299f5  xor     rax, rsp
0x1800299f8  mov     [rsp+58h+var_10], rax
0x1800299fd  cmp     qword ptr [rcx+18h], 7
0x180029a02  mov     rdi, rcx
0x180029a05  mov     [rsp+58h+BytesReturned], 0
0x180029a0d  jbe     short loc_180029A12
0x180029a0f  mov     rcx, [rcx]; lpFileName
0x180029a12  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180029a1b  mov     r8d, 3; dwShareMode
0x180029a21  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180029a29  xor     r9d, r9d; lpSecurityAttributes
0x180029a2c  mov     edx, 0C0000000h; dwDesiredAccess
0x180029a31  mov     [rsp+58h+dwCreationDisposition], r8d; dwCreationDisposition
0x180029a36  call    cs:__imp_CreateFileW
0x180029a3d  nop     dword ptr [rax+rax+00h]
0x180029a42  mov     rbx, rax
0x180029a45  dec     rax
0x180029a48  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180029a4c  ja      loc_180029AE1
0x180029a52  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x180029a5b  lea     rax, [rsp+58h+BytesReturned]
0x180029a60  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x180029a65  xor     r9d, r9d; nInBufferSize
0x180029a68  mov     [rsp+58h+dwFlagsAndAttributes], 0; nOutBufferSize
0x180029a70  xor     r8d, r8d; lpInBuffer
0x180029a73  mov     edx, 560010h; dwIoControlCode
0x180029a78  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOutBuffer
0x180029a81  mov     rcx, rbx; hDevice
0x180029a84  call    cs:__imp_DeviceIoControl
0x180029a8b  nop     dword ptr [rax+rax+00h]
0x180029a90  test    eax, eax
0x180029a92  jz      short loc_180029AD2
0x180029a94  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x180029a9d  lea     rax, [rsp+58h+BytesReturned]
0x180029aa2  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x180029aa7  xor     r9d, r9d; nInBufferSize
0x180029aaa  mov     [rsp+58h+dwFlagsAndAttributes], 0; nOutBufferSize
0x180029ab2  xor     r8d, r8d; lpInBuffer
0x180029ab5  mov     edx, 56C008h; dwIoControlCode
0x180029aba  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOutBuffer
0x180029ac3  mov     rcx, rbx; hDevice
0x180029ac6  call    cs:__imp_DeviceIoControl
0x180029acd  nop     dword ptr [rax+rax+00h]
0x180029ad2  mov     rcx, rbx; hObject
0x180029ad5  call    cs:__imp_CloseHandle
0x180029adc  nop     dword ptr [rax+rax+00h]
0x180029ae1  mov     rcx, rdi
0x180029ae4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029ae9  mov     rcx, [rsp+58h+var_10]
0x180029aee  xor     rcx, rsp; StackCookie
0x180029af1  call    __security_check_cookie
0x180029af6  mov     rbx, [rsp+58h+arg_8]
0x180029afb  add     rsp, 50h
0x180029aff  pop     rdi
0x180029b00  retn
```
