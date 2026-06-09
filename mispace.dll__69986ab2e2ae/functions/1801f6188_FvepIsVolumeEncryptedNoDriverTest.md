# FvepIsVolumeEncryptedNoDriverTest

- ea: `0x1801f6188`
- end: `0x1801f63c3`
- name: `FvepIsVolumeEncryptedNoDriverTest`
- size: `571`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1801f4e0c`

## callees

- `0x180006350`
- `0x1801f5684`
- `0x1801f5d50`
- `0x1801f6080`
- `0x1801f6188`
- `0x1801f63cc`
- `0x1801f6690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f621a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f6291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f630c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f621a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f6291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f630c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f6393`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f6393`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801f6281`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801f6281`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801f6205`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801f6205`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801f62fc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801f62fc`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1801f62d2`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1801f62d2`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1801f6384`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1801f6384`

## pseudocode

```c
__int64 __fastcall FvepIsVolumeEncryptedNoDriverTest(STRSAFE_PCNZWCH pszSrc)
{
  unsigned int IsBandBitLockerManaged; // ebx
  HANDLE FileW; // rax
  void *v4; // rdi
  signed int v5; // eax
  signed int LastError; // eax
  DWORD v7; // ebx
  void *v8; // rax
  void *v9; // r14
  signed int v10; // eax
  BOOL v11; // edx
  int v12; // eax
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-2Ch] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-28h] BYREF
  __int128 OutBuffer; // [rsp+50h] [rbp-20h] BYREF
  __int64 v17; // [rsp+60h] [rbp-10h]

  v17 = 0;
  OutBuffer = 0;
  BytesReturned = 0;
  NumberOfBytesRead = 0;
  if ( (unsigned int)FvepIsVolumeEncryptedCached(pszSrc) )
    return 1;
  FileW = CreateFileW(pszSrc, 0x80000000, 3u, 0, 3u, 0x20000000u, 0);
  v4 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    IsBandBitLockerManaged = FvepIsBandBitLockerManaged(FileW);
    if ( !IsBandBitLockerManaged )
    {
LABEL_25:
      CloseHandle(v4);
      return IsBandBitLockerManaged;
    }
    if ( !DeviceIoControl(v4, 0x70000u, 0, 0, &OutBuffer, 0x18u, &BytesReturned, 0)
      || (v7 = (HIDWORD(v17) + 511) & 0xFFFFFE00, v8 = VirtualAlloc(0, v7, 0x3000u, 4u), (v9 = v8) == 0) )
    {
      LastError = GetLastError();
      IsBandBitLockerManaged = LastError;
      if ( LastError > 0 )
        IsBandBitLockerManaged = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_25;
    }
    if ( ReadFile(v4, v8, v7, &NumberOfBytesRead, 0) )
    {
      v12 = FveCheckVolumeTypeEx(v9, NumberOfBytesRead, 0);
      if ( (unsigned int)(v12 - 2) <= 1 )
      {
        IsBandBitLockerManaged = 0;
      }
      else if ( v12 == 1 )
      {
        IsBandBitLockerManaged = FvepCheckForVolumeControlFiles(v4);
        if ( (IsBandBitLockerManaged & 0x80000000) != 0 )
        {
LABEL_24:
          VirtualFree(v9, 0, 0x8000u);
          goto LABEL_25;
        }
      }
      else
      {
        IsBandBitLockerManaged = 1;
      }
      v11 = IsBandBitLockerManaged == 0;
    }
    else
    {
      v10 = GetLastError();
      IsBandBitLockerManaged = v10;
      if ( v10 > 0 )
        IsBandBitLockerManaged = (unsigned __int16)v10 | 0x80070000;
      if ( IsBandBitLockerManaged != -2144272384 )
        goto LABEL_24;
      IsBandBitLockerManaged = 0;
      v11 = 1;
    }
    FvepSetVolumeEncryptedCached(pszSrc, v11);
    goto LABEL_24;
  }
  v5 = GetLastError();
  IsBandBitLockerManaged = v5;
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return IsBandBitLockerManaged;
}

```

## disassembly

```asm
0x1801f6188  mov     [rsp-18h+arg_8], rbx
0x1801f618d  mov     [rsp-18h+arg_10], rsi
0x1801f6192  push    rbp
0x1801f6193  push    rdi
0x1801f6194  push    r14
0x1801f6196  mov     rbp, rsp
0x1801f6199  sub     rsp, 70h
0x1801f619d  mov     rax, cs:__security_cookie
0x1801f61a4  xor     rax, rsp
0x1801f61a7  mov     [rbp+var_8], rax
0x1801f61ab  xor     eax, eax
0x1801f61ad  lea     rdx, [rbp+var_30]
0x1801f61b1  xorps   xmm0, xmm0
0x1801f61b4  mov     [rbp+var_10], rax
0x1801f61b8  movups  [rbp+OutBuffer], xmm0
0x1801f61bc  mov     [rbp+BytesReturned], eax
0x1801f61bf  mov     rsi, rcx
0x1801f61c2  mov     [rbp+NumberOfBytesRead], eax
0x1801f61c5  mov     [rbp+var_30], eax
0x1801f61c8  call    FvepIsVolumeEncryptedCached
0x1801f61cd  test    eax, eax
0x1801f61cf  jz      short loc_1801F61DE
0x1801f61d1  xor     ebx, ebx
0x1801f61d3  cmp     [rbp+var_30], ebx
0x1801f61d6  setz    bl
0x1801f61d9  jmp     loc_1801F639F
0x1801f61de  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x1801f61e7  mov     r8d, 3; dwShareMode
0x1801f61ed  mov     [rsp+70h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x1801f61f5  xor     r9d, r9d; lpSecurityAttributes
0x1801f61f8  mov     edx, 80000000h; dwDesiredAccess
0x1801f61fd  mov     [rsp+70h+dwCreationDisposition], r8d; dwCreationDisposition
0x1801f6202  mov     rcx, rsi; lpFileName
0x1801f6205  call    cs:__imp_CreateFileW
0x1801f620c  nop     dword ptr [rax+rax+00h]
0x1801f6211  mov     rdi, rax
0x1801f6214  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801f6218  jnz     short loc_1801F623E
0x1801f621a  call    cs:__imp_GetLastError
0x1801f6221  nop     dword ptr [rax+rax+00h]
0x1801f6226  mov     ebx, eax
0x1801f6228  test    eax, eax
0x1801f622a  jle     loc_1801F639F
0x1801f6230  movzx   ebx, ax
0x1801f6233  or      ebx, 80070000h
0x1801f6239  jmp     loc_1801F639F
0x1801f623e  mov     rcx, rdi; hDevice
0x1801f6241  call    FvepIsBandBitLockerManaged
0x1801f6246  mov     ebx, eax
0x1801f6248  test    eax, eax
0x1801f624a  jz      loc_1801F6390
0x1801f6250  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x1801f6259  lea     rax, [rbp+BytesReturned]
0x1801f625d  mov     [rsp+70h+hTemplateFile], rax; lpBytesReturned
0x1801f6262  xor     r9d, r9d; nInBufferSize
0x1801f6265  lea     rax, [rbp+OutBuffer]
0x1801f6269  mov     [rsp+70h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x1801f6271  xor     r8d, r8d; lpInBuffer
0x1801f6274  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; lpOutBuffer
0x1801f6279  mov     edx, 70000h; dwIoControlCode
0x1801f627e  mov     rcx, rdi; hDevice
0x1801f6281  call    cs:__imp_DeviceIoControl
0x1801f6288  nop     dword ptr [rax+rax+00h]
0x1801f628d  test    eax, eax
0x1801f628f  jnz     short loc_1801F62B5
0x1801f6291  call    cs:__imp_GetLastError
0x1801f6298  nop     dword ptr [rax+rax+00h]
0x1801f629d  mov     ebx, eax
0x1801f629f  test    eax, eax
0x1801f62a1  jle     loc_1801F6390
0x1801f62a7  movzx   ebx, ax
0x1801f62aa  or      ebx, 80070000h
0x1801f62b0  jmp     loc_1801F6390
0x1801f62b5  mov     eax, dword ptr [rbp+var_10+4]
0x1801f62b8  xor     ecx, ecx; lpAddress
0x1801f62ba  add     eax, 1FFh
0x1801f62bf  mov     r8d, 3000h; flAllocationType
0x1801f62c5  and     eax, 0FFFFFE00h
0x1801f62ca  mov     edx, eax; dwSize
0x1801f62cc  lea     r9d, [rcx+4]; flProtect
0x1801f62d0  mov     ebx, eax
0x1801f62d2  call    cs:__imp_VirtualAlloc
0x1801f62d9  nop     dword ptr [rax+rax+00h]
0x1801f62de  mov     r14, rax
0x1801f62e1  test    rax, rax
0x1801f62e4  jz      short loc_1801F6291
0x1801f62e6  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1801f62ea  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x1801f62f3  mov     r8d, ebx; nNumberOfBytesToRead
0x1801f62f6  mov     rdx, rax; lpBuffer
0x1801f62f9  mov     rcx, rdi; hFile
0x1801f62fc  call    cs:__imp_ReadFile
0x1801f6303  nop     dword ptr [rax+rax+00h]
0x1801f6308  test    eax, eax
0x1801f630a  jnz     short loc_1801F6336
0x1801f630c  call    cs:__imp_GetLastError
0x1801f6313  nop     dword ptr [rax+rax+00h]
0x1801f6318  mov     ebx, eax
0x1801f631a  test    eax, eax
0x1801f631c  jle     short loc_1801F6327
0x1801f631e  movzx   ebx, ax
0x1801f6321  or      ebx, 80070000h
0x1801f6327  cmp     ebx, 80310000h
0x1801f632d  jnz     short loc_1801F6379
0x1801f632f  xor     ebx, ebx
0x1801f6331  lea     edx, [rbx+1]
0x1801f6334  jmp     short loc_1801F6371
0x1801f6336  mov     edx, [rbp+NumberOfBytesRead]
0x1801f6339  xor     r8d, r8d
0x1801f633c  mov     rcx, r14
0x1801f633f  call    FveCheckVolumeTypeEx
0x1801f6344  lea     ecx, [rax-2]
0x1801f6347  cmp     ecx, 1
0x1801f634a  jbe     short loc_1801F6368
0x1801f634c  cmp     eax, 1
0x1801f634f  jnz     short loc_1801F6361
0x1801f6351  mov     rcx, rdi; hDevice
0x1801f6354  call    FvepCheckForVolumeControlFiles
0x1801f6359  mov     ebx, eax
0x1801f635b  test    eax, eax
0x1801f635d  js      short loc_1801F6379
0x1801f635f  jmp     short loc_1801F636A
0x1801f6361  mov     ebx, 1
0x1801f6366  jmp     short loc_1801F636A
0x1801f6368  xor     ebx, ebx
0x1801f636a  xor     edx, edx
0x1801f636c  test    ebx, ebx
0x1801f636e  setz    dl
0x1801f6371  mov     rcx, rsi; pszSrc
0x1801f6374  call    FvepSetVolumeEncryptedCached
0x1801f6379  xor     edx, edx; dwSize
0x1801f637b  mov     r8d, 8000h; dwFreeType
0x1801f6381  mov     rcx, r14; lpAddress
0x1801f6384  call    cs:__imp_VirtualFree
0x1801f638b  nop     dword ptr [rax+rax+00h]
0x1801f6390  mov     rcx, rdi; hObject
0x1801f6393  call    cs:__imp_CloseHandle
0x1801f639a  nop     dword ptr [rax+rax+00h]
0x1801f639f  mov     eax, ebx
0x1801f63a1  mov     rcx, [rbp+var_8]
0x1801f63a5  xor     rcx, rsp; StackCookie
0x1801f63a8  call    __security_check_cookie
0x1801f63ad  lea     r11, [rsp+70h+var_s0]
0x1801f63b2  mov     rbx, [r11+28h]
0x1801f63b6  mov     rsi, [r11+30h]
0x1801f63ba  mov     rsp, r11
0x1801f63bd  pop     r14
0x1801f63bf  pop     rdi
0x1801f63c0  pop     rbp
0x1801f63c1  retn
```
