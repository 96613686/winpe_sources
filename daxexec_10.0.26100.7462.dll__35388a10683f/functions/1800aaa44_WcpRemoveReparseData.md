# WcpRemoveReparseData

- ea: `0x1800aaa44`
- end: `0x1800aabea`
- name: `WcpRemoveReparseData`
- size: `422`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x180031fc0`
- `0x1800322f8`

## callees

- `0x1800053a0`
- `0x1800aa7b4`
- `0x1800aaa44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800aabb7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800aabb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aaadb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aab20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aaadb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aab20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aaba2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aaba2`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800aab8c`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800aab8c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800aaac6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800aaac6`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800aab10`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800aab10`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800aab6b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800aab6b`

## pseudocode

```c
__int64 __fastcall WcpRemoveReparseData(__int64 a1, int a2)
{
  signed int v3; // ebx
  HANDLE FileW; // rax
  void *v5; // rdi
  signed int LastError; // eax
  signed int v7; // eax
  LPCWSTR lpFileName; // [rsp+40h] [rbp-9h] BYREF
  void *Block; // [rsp+48h] [rbp-1h] BYREF
  _OWORD FileInformation[2]; // [rsp+50h] [rbp+7h] BYREF
  __int64 v12; // [rsp+70h] [rbp+27h]
  int InBuffer; // [rsp+78h] [rbp+2Fh] BYREF
  __int16 v14; // [rsp+7Ch] [rbp+33h]

  lpFileName = 0;
  v12 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  Block = 0;
  v3 = WcpConstructLongPath(a1, &Block, &lpFileName);
  if ( v3 >= 0 )
  {
    FileW = CreateFileW(lpFileName, 0x100u, 1u, 0, 3u, 0x2200000u, 0);
    v5 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      if ( GetFileInformationByHandleEx(FileW, FileBasicInfo, FileInformation, 0x28u)
        && (InBuffer = a2, v14 = 0, DeviceIoControl(v5, 0x900ACu, &InBuffer, 8u, 0, 0, 0, 0))
        && (LODWORD(v12) = v12 & 0xFFFFFBFF, SetFileInformationByHandle(v5, FileBasicInfo, FileInformation, 0x28u)) )
      {
        v3 = 0;
      }
      else
      {
        v7 = GetLastError();
        v3 = v7;
        if ( v7 > 0 )
          v3 = (unsigned __int16)v7 | 0x80070000;
      }
      CloseHandle(v5);
    }
  }
  if ( Block )
    free(Block);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800aaa44  mov     [rsp-8+arg_8], rbx
0x1800aaa49  mov     [rsp-8+arg_10], rsi
0x1800aaa4e  push    rbp
0x1800aaa4f  push    rdi
0x1800aaa50  push    r14
0x1800aaa52  lea     rbp, [rsp-47h]
0x1800aaa57  sub     rsp, 90h
0x1800aaa5e  mov     rax, cs:__security_cookie
0x1800aaa65  xor     rax, rsp
0x1800aaa68  mov     [rbp+57h+var_20], rax
0x1800aaa6c  xorps   xmm0, xmm0
0x1800aaa6f  lea     r8, [rbp+57h+lpFileName]
0x1800aaa73  mov     esi, edx
0x1800aaa75  xor     r14d, r14d
0x1800aaa78  xor     eax, eax
0x1800aaa7a  mov     [rbp+57h+lpFileName], r14
0x1800aaa7e  lea     rdx, [rbp+57h+Block]
0x1800aaa82  mov     [rbp+57h+var_30], rax
0x1800aaa86  movups  [rbp+57h+FileInformation], xmm0
0x1800aaa8a  mov     [rbp+57h+Block], r14
0x1800aaa8e  movups  [rbp+57h+var_40], xmm0
0x1800aaa92  call    WcpConstructLongPath
0x1800aaa97  mov     ebx, eax
0x1800aaa99  test    eax, eax
0x1800aaa9b  js      loc_1800AABAE
0x1800aaaa1  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800aaaa5  lea     r8d, [r14+1]; dwShareMode
0x1800aaaa9  mov     [rsp+0A0h+hTemplateFile], r14; hTemplateFile
0x1800aaaae  xor     r9d, r9d; lpSecurityAttributes
0x1800aaab1  mov     [rsp+0A0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800aaab9  mov     edx, 100h; dwDesiredAccess
0x1800aaabe  mov     [rsp+0A0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800aaac6  call    cs:__imp_CreateFileW
0x1800aaacd  nop     dword ptr [rax+rax+00h]
0x1800aaad2  mov     rdi, rax
0x1800aaad5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800aaad9  jnz     short loc_1800AAAFF
0x1800aaadb  call    cs:__imp_GetLastError
0x1800aaae2  nop     dword ptr [rax+rax+00h]
0x1800aaae7  mov     ebx, eax
0x1800aaae9  test    eax, eax
0x1800aaaeb  jle     loc_1800AABAE
0x1800aaaf1  movzx   ebx, ax
0x1800aaaf4  or      ebx, 80070000h
0x1800aaafa  jmp     loc_1800AABAE
0x1800aaaff  mov     ebx, 28h ; '('
0x1800aab04  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x1800aab08  mov     r9d, ebx; dwBufferSize
0x1800aab0b  xor     edx, edx; FileInformationClass
0x1800aab0d  mov     rcx, rdi; hFile
0x1800aab10  call    cs:__imp_GetFileInformationByHandleEx
0x1800aab17  nop     dword ptr [rax+rax+00h]
0x1800aab1c  test    eax, eax
0x1800aab1e  jnz     short loc_1800AAB3D
0x1800aab20  call    cs:__imp_GetLastError
0x1800aab27  nop     dword ptr [rax+rax+00h]
0x1800aab2c  mov     ebx, eax
0x1800aab2e  test    eax, eax
0x1800aab30  jle     short loc_1800AAB9F
0x1800aab32  movzx   ebx, ax
0x1800aab35  or      ebx, 80070000h
0x1800aab3b  jmp     short loc_1800AAB9F
0x1800aab3d  mov     [rsp+0A0h+lpOverlapped], r14; lpOverlapped
0x1800aab42  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x1800aab46  mov     [rsp+0A0h+hTemplateFile], r14; lpBytesReturned
0x1800aab4b  mov     r9d, 8; nInBufferSize
0x1800aab51  mov     [rsp+0A0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x1800aab56  mov     edx, 900ACh; dwIoControlCode
0x1800aab5b  mov     rcx, rdi; hDevice
0x1800aab5e  mov     qword ptr [rsp+0A0h+dwCreationDisposition], r14; lpOutBuffer
0x1800aab63  mov     [rbp+57h+InBuffer], esi
0x1800aab66  mov     [rbp+57h+var_24], r14w
0x1800aab6b  call    cs:__imp_DeviceIoControl
0x1800aab72  nop     dword ptr [rax+rax+00h]
0x1800aab77  test    eax, eax
0x1800aab79  jz      short loc_1800AAB20
0x1800aab7b  btr     dword ptr [rbp+57h+var_30], 0Ah
0x1800aab80  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x1800aab84  mov     r9d, ebx; dwBufferSize
0x1800aab87  xor     edx, edx; FileInformationClass
0x1800aab89  mov     rcx, rdi; hFile
0x1800aab8c  call    cs:__imp_SetFileInformationByHandle
0x1800aab93  nop     dword ptr [rax+rax+00h]
0x1800aab98  test    eax, eax
0x1800aab9a  jz      short loc_1800AAB20
0x1800aab9c  mov     ebx, r14d
0x1800aab9f  mov     rcx, rdi; hObject
0x1800aaba2  call    cs:__imp_CloseHandle
0x1800aaba9  nop     dword ptr [rax+rax+00h]
0x1800aabae  mov     rcx, [rbp+57h+Block]; Block
0x1800aabb2  test    rcx, rcx
0x1800aabb5  jz      short loc_1800AABC3
0x1800aabb7  call    cs:__imp_free
0x1800aabbe  nop     dword ptr [rax+rax+00h]
0x1800aabc3  mov     eax, ebx
0x1800aabc5  mov     rcx, [rbp+57h+var_20]
0x1800aabc9  xor     rcx, rsp; StackCookie
0x1800aabcc  call    __security_check_cookie
0x1800aabd1  lea     r11, [rsp+0A0h+var_10]
0x1800aabd9  mov     rbx, [r11+28h]
0x1800aabdd  mov     rsi, [r11+30h]
0x1800aabe1  mov     rsp, r11
0x1800aabe4  pop     r14
0x1800aabe6  pop     rdi
0x1800aabe7  pop     rbp
0x1800aabe8  retn
```
