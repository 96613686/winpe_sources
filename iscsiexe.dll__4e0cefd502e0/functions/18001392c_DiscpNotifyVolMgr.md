# DiscpNotifyVolMgr

- ea: `0x18001392c`
- end: `0x180013a13`
- name: `DiscpNotifyVolMgr`
- size: `231`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180013b24`

## callees

- `0x18001392c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139fe`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800139dd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800139dd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013977`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013977`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800139f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800139f6`

## pseudocode

```c
__int64 __fastcall DiscpNotifyVolMgr(char a1)
{
  HANDLE FileW; // rdi
  DWORD v3; // edx
  int *p_InBuffer; // r8
  DWORD LastError; // ebx
  int v7; // [rsp+58h] [rbp+10h] BYREF
  int InBuffer; // [rsp+60h] [rbp+18h] BYREF
  DWORD BytesReturned; // [rsp+68h] [rbp+20h] BYREF

  BytesReturned = 0;
  v7 = 0;
  InBuffer = 0;
  FileW = CreateFileW(L"\\\\.\\VolMgrControl", 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    if ( a1 )
    {
      v3 = 7783332;
      v7 = 1;
      p_InBuffer = &v7;
    }
    else
    {
      v3 = 7783336;
      InBuffer = 1;
      p_InBuffer = &InBuffer;
    }
    if ( DeviceIoControl(FileW, v3, p_InBuffer, 4u, 0, 0, &BytesReturned, 0) )
      LastError = 0;
    else
      LastError = GetLastError();
    CloseHandle(FileW);
  }
  return LastError;
}

```

## disassembly

```asm
0x18001392c  mov     rax, rsp
0x18001392f  mov     [rax+8], rbx
0x180013933  push    rdi
0x180013934  sub     rsp, 40h
0x180013938  mov     qword ptr [rax-18h], 0
0x180013940  mov     bl, cl
0x180013942  mov     r8d, 3; dwShareMode
0x180013948  mov     dword ptr [rax-20h], 0
0x18001394f  lea     rcx, FileName; "\\\\.\\VolMgrControl"
0x180013956  mov     [rax-28h], r8d
0x18001395a  xor     r9d, r9d; lpSecurityAttributes
0x18001395d  mov     dword ptr [rax+20h], 0
0x180013964  mov     edx, 0C0000000h; dwDesiredAccess
0x180013969  mov     dword ptr [rax+10h], 0
0x180013970  mov     dword ptr [rax+18h], 0
0x180013977  call    cs:__imp_CreateFileW
0x18001397d  mov     rdi, rax
0x180013980  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013984  jz      short loc_1800139FE
0x180013986  test    bl, bl
0x180013988  jz      short loc_18001399E
0x18001398a  mov     edx, 76C3A4h
0x18001398f  mov     [rsp+48h+arg_8], 1
0x180013997  lea     r8, [rsp+48h+arg_8]
0x18001399c  jmp     short loc_1800139B0
0x18001399e  mov     edx, 76C3A8h; dwIoControlCode
0x1800139a3  mov     [rsp+48h+InBuffer], 1
0x1800139ab  lea     r8, [rsp+48h+InBuffer]; lpInBuffer
0x1800139b0  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1800139b9  lea     rax, [rsp+48h+BytesReturned]
0x1800139be  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x1800139c3  mov     r9d, 4; nInBufferSize
0x1800139c9  mov     [rsp+48h+nOutBufferSize], 0; nOutBufferSize
0x1800139d1  mov     rcx, rdi; hDevice
0x1800139d4  mov     [rsp+48h+lpOutBuffer], 0; lpOutBuffer
0x1800139dd  call    cs:__imp_DeviceIoControl
0x1800139e3  test    eax, eax
0x1800139e5  jz      short loc_1800139EB
0x1800139e7  xor     ebx, ebx
0x1800139e9  jmp     short loc_1800139F3
0x1800139eb  call    cs:__imp_GetLastError
0x1800139f1  mov     ebx, eax
0x1800139f3  mov     rcx, rdi; hObject
0x1800139f6  call    cs:__imp_CloseHandle
0x1800139fc  jmp     short loc_180013A06
0x1800139fe  call    cs:__imp_GetLastError
0x180013a04  mov     ebx, eax
0x180013a06  mov     eax, ebx
0x180013a08  mov     rbx, [rsp+48h+arg_0]
0x180013a0d  add     rsp, 40h
0x180013a11  pop     rdi
0x180013a12  retn
```
