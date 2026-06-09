# WcpRemoveReparseData

- ea: `0x1800ac054`
- end: `0x1800ac1e7`
- name: `WcpRemoveReparseData`
- size: `403`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x180033bb0`
- `0x180033edc`

## callees

- `0x180004f70`
- `0x1800abdd4`
- `0x1800ac054`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ac1c0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ac1c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac12c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac12c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac1ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac1ab`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800ac196`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800ac196`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ac0d2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ac0d2`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800ac11c`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800ac11c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800ac175`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800ac175`

## pseudocode

```c
__int64 __fastcall WcpRemoveReparseData(__int64 a1, int a2)
{
  signed int v3; // ebx
  HANDLE FileW; // rax
  void *v5; // rdi
  signed int LastError; // eax
  signed int v7; // eax
  LPCWSTR lpFileName; // [rsp+40h] [rbp-19h] BYREF
  void *Block; // [rsp+48h] [rbp-11h] BYREF
  _OWORD FileInformation[2]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v12; // [rsp+70h] [rbp+17h]
  int InBuffer; // [rsp+78h] [rbp+1Fh] BYREF
  __int16 v14; // [rsp+7Ch] [rbp+23h]

  lpFileName = 0;
  v12 = 0;
  Block = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
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
0x1800ac054  push    rbp
0x1800ac056  push    rbx
0x1800ac057  push    rsi
0x1800ac058  push    rdi
0x1800ac059  lea     rbp, [rsp-3Fh]
0x1800ac05e  sub     rsp, 98h
0x1800ac065  mov     rax, cs:__security_cookie
0x1800ac06c  xor     rax, rsp
0x1800ac06f  mov     [rbp+57h+var_30], rax
0x1800ac073  xorps   xmm0, xmm0
0x1800ac076  mov     [rbp+57h+lpFileName], 0
0x1800ac07e  xor     eax, eax
0x1800ac080  lea     r8, [rbp+57h+lpFileName]
0x1800ac084  mov     esi, edx
0x1800ac086  mov     [rbp+57h+var_40], rax
0x1800ac08a  lea     rdx, [rbp+57h+Block]
0x1800ac08e  mov     [rbp+57h+Block], rax
0x1800ac092  movups  [rbp+57h+FileInformation], xmm0
0x1800ac096  movups  [rbp+57h+var_50], xmm0
0x1800ac09a  call    WcpConstructLongPath
0x1800ac09f  mov     ebx, eax
0x1800ac0a1  test    eax, eax
0x1800ac0a3  js      loc_1800AC1B7
0x1800ac0a9  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800ac0ad  xor     r9d, r9d; lpSecurityAttributes
0x1800ac0b0  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x1800ac0b9  mov     edx, 100h; dwDesiredAccess
0x1800ac0be  mov     [rsp+0B0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800ac0c6  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800ac0ce  lea     r8d, [r9+1]; dwShareMode
0x1800ac0d2  call    cs:__imp_CreateFileW
0x1800ac0d9  nop     dword ptr [rax+rax+00h]
0x1800ac0de  mov     rdi, rax
0x1800ac0e1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ac0e5  jnz     short loc_1800AC10B
0x1800ac0e7  call    cs:__imp_GetLastError
0x1800ac0ee  nop     dword ptr [rax+rax+00h]
0x1800ac0f3  mov     ebx, eax
0x1800ac0f5  test    eax, eax
0x1800ac0f7  jle     loc_1800AC1B7
0x1800ac0fd  movzx   ebx, ax
0x1800ac100  or      ebx, 80070000h
0x1800ac106  jmp     loc_1800AC1B7
0x1800ac10b  mov     ebx, 28h ; '('
0x1800ac110  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x1800ac114  mov     r9d, ebx; dwBufferSize
0x1800ac117  xor     edx, edx; FileInformationClass
0x1800ac119  mov     rcx, rdi; hFile
0x1800ac11c  call    cs:__imp_GetFileInformationByHandleEx
0x1800ac123  nop     dword ptr [rax+rax+00h]
0x1800ac128  test    eax, eax
0x1800ac12a  jnz     short loc_1800AC149
0x1800ac12c  call    cs:__imp_GetLastError
0x1800ac133  nop     dword ptr [rax+rax+00h]
0x1800ac138  mov     ebx, eax
0x1800ac13a  test    eax, eax
0x1800ac13c  jle     short loc_1800AC1A8
0x1800ac13e  movzx   ebx, ax
0x1800ac141  or      ebx, 80070000h
0x1800ac147  jmp     short loc_1800AC1A8
0x1800ac149  xor     eax, eax
0x1800ac14b  mov     [rbp+57h+InBuffer], esi
0x1800ac14e  mov     [rsp+0B0h+lpOverlapped], rax; lpOverlapped
0x1800ac153  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x1800ac157  mov     [rsp+0B0h+hTemplateFile], rax; lpBytesReturned
0x1800ac15c  mov     edx, 900ACh; dwIoControlCode
0x1800ac161  mov     [rsp+0B0h+dwFlagsAndAttributes], eax; nOutBufferSize
0x1800ac165  mov     rcx, rdi; hDevice
0x1800ac168  lea     r9d, [rax+8]; nInBufferSize
0x1800ac16c  mov     [rbp+57h+var_34], ax
0x1800ac170  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; lpOutBuffer
0x1800ac175  call    cs:__imp_DeviceIoControl
0x1800ac17c  nop     dword ptr [rax+rax+00h]
0x1800ac181  test    eax, eax
0x1800ac183  jz      short loc_1800AC12C
0x1800ac185  btr     dword ptr [rbp+57h+var_40], 0Ah
0x1800ac18a  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x1800ac18e  mov     r9d, ebx; dwBufferSize
0x1800ac191  xor     edx, edx; FileInformationClass
0x1800ac193  mov     rcx, rdi; hFile
0x1800ac196  call    cs:__imp_SetFileInformationByHandle
0x1800ac19d  nop     dword ptr [rax+rax+00h]
0x1800ac1a2  test    eax, eax
0x1800ac1a4  jz      short loc_1800AC12C
0x1800ac1a6  xor     ebx, ebx
0x1800ac1a8  mov     rcx, rdi; hObject
0x1800ac1ab  call    cs:__imp_CloseHandle
0x1800ac1b2  nop     dword ptr [rax+rax+00h]
0x1800ac1b7  mov     rcx, [rbp+57h+Block]; Block
0x1800ac1bb  test    rcx, rcx
0x1800ac1be  jz      short loc_1800AC1CC
0x1800ac1c0  call    cs:__imp_free
0x1800ac1c7  nop     dword ptr [rax+rax+00h]
0x1800ac1cc  mov     eax, ebx
0x1800ac1ce  mov     rcx, [rbp+57h+var_30]
0x1800ac1d2  xor     rcx, rsp; StackCookie
0x1800ac1d5  call    __security_check_cookie
0x1800ac1da  add     rsp, 98h
0x1800ac1e1  pop     rdi
0x1800ac1e2  pop     rsi
0x1800ac1e3  pop     rbx
0x1800ac1e4  pop     rbp
0x1800ac1e5  retn
```
