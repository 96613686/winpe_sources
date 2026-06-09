# FvepIsVolumeEncryptedNoDriverTest

- ea: `0x180171014`
- end: `0x180171218`
- name: `FvepIsVolumeEncryptedNoDriverTest`
- size: `516`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18016fde4`

## callees

- `0x180008dc0`
- `0x1801704b8`
- `0x180170c24`
- `0x180170f20`
- `0x180171014`
- `0x180171220`
- `0x1801847dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801710a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017110b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180171174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801710a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017110b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180171174`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801711ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801711ef`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18017116a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18017116a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180171091`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180171091`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180171101`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180171101`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180171146`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180171146`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1801711e6`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1801711e6`

## pseudocode

```c
__int64 __fastcall FvepIsVolumeEncryptedNoDriverTest(LPCWSTR lpFileName)
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
  int v14; // [rsp+40h] [rbp-30h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-2Ch] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-28h] BYREF
  __int128 OutBuffer; // [rsp+50h] [rbp-20h] BYREF
  __int64 v18; // [rsp+60h] [rbp-10h]

  v18 = 0;
  OutBuffer = 0;
  BytesReturned = 0;
  NumberOfBytesRead = 0;
  v14 = 0;
  if ( (unsigned int)FvepIsVolumeEncryptedCached(lpFileName, &v14) )
    return v14 == 0;
  FileW = CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x20000000u, 0);
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
      || (v7 = (HIDWORD(v18) + 511) & 0xFFFFFE00, v8 = VirtualAlloc(0, v7, 0x3000u, 4u), (v9 = v8) == 0) )
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
    FvepSetVolumeEncryptedCached((__int64)lpFileName, v11);
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
0x180171014  mov     [rsp-18h+arg_8], rbx
0x180171019  mov     [rsp-18h+arg_10], rsi
0x18017101e  push    rbp
0x18017101f  push    rdi
0x180171020  push    r14
0x180171022  mov     rbp, rsp
0x180171025  sub     rsp, 70h
0x180171029  mov     rax, cs:__security_cookie
0x180171030  xor     rax, rsp
0x180171033  mov     [rbp+var_8], rax
0x180171037  xor     eax, eax
0x180171039  lea     rdx, [rbp+var_30]
0x18017103d  xorps   xmm0, xmm0
0x180171040  mov     [rbp+var_10], rax
0x180171044  movups  [rbp+OutBuffer], xmm0
0x180171048  mov     [rbp+BytesReturned], eax
0x18017104b  mov     rsi, rcx
0x18017104e  mov     [rbp+NumberOfBytesRead], eax
0x180171051  mov     [rbp+var_30], eax
0x180171054  call    FvepIsVolumeEncryptedCached
0x180171059  test    eax, eax
0x18017105b  jz      short loc_18017106A
0x18017105d  xor     ebx, ebx
0x18017105f  cmp     [rbp+var_30], ebx
0x180171062  setz    bl
0x180171065  jmp     loc_1801711F5
0x18017106a  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180171073  mov     r8d, 3; dwShareMode
0x180171079  mov     [rsp+70h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x180171081  xor     r9d, r9d; lpSecurityAttributes
0x180171084  mov     edx, 80000000h; dwDesiredAccess
0x180171089  mov     [rsp+70h+dwCreationDisposition], r8d; dwCreationDisposition
0x18017108e  mov     rcx, rsi; lpFileName
0x180171091  call    cs:__imp_CreateFileW
0x180171097  mov     rdi, rax
0x18017109a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18017109e  jnz     short loc_1801710BE
0x1801710a0  call    cs:__imp_GetLastError
0x1801710a6  mov     ebx, eax
0x1801710a8  test    eax, eax
0x1801710aa  jle     loc_1801711F5
0x1801710b0  movzx   ebx, ax
0x1801710b3  or      ebx, 80070000h
0x1801710b9  jmp     loc_1801711F5
0x1801710be  mov     rcx, rdi; hDevice
0x1801710c1  call    FvepIsBandBitLockerManaged
0x1801710c6  mov     ebx, eax
0x1801710c8  test    eax, eax
0x1801710ca  jz      loc_1801711EC
0x1801710d0  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x1801710d9  lea     rax, [rbp+BytesReturned]
0x1801710dd  mov     [rsp+70h+hTemplateFile], rax; lpBytesReturned
0x1801710e2  xor     r9d, r9d; nInBufferSize
0x1801710e5  lea     rax, [rbp+OutBuffer]
0x1801710e9  mov     [rsp+70h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x1801710f1  xor     r8d, r8d; lpInBuffer
0x1801710f4  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; lpOutBuffer
0x1801710f9  mov     edx, 70000h; dwIoControlCode
0x1801710fe  mov     rcx, rdi; hDevice
0x180171101  call    cs:__imp_DeviceIoControl
0x180171107  test    eax, eax
0x180171109  jnz     short loc_180171129
0x18017110b  call    cs:__imp_GetLastError
0x180171111  mov     ebx, eax
0x180171113  test    eax, eax
0x180171115  jle     loc_1801711EC
0x18017111b  movzx   ebx, ax
0x18017111e  or      ebx, 80070000h
0x180171124  jmp     loc_1801711EC
0x180171129  mov     eax, dword ptr [rbp+var_10+4]
0x18017112c  xor     ecx, ecx; lpAddress
0x18017112e  add     eax, 1FFh
0x180171133  mov     r8d, 3000h; flAllocationType
0x180171139  and     eax, 0FFFFFE00h
0x18017113e  mov     edx, eax; dwSize
0x180171140  lea     r9d, [rcx+4]; flProtect
0x180171144  mov     ebx, eax
0x180171146  call    cs:__imp_VirtualAlloc
0x18017114c  mov     r14, rax
0x18017114f  test    rax, rax
0x180171152  jz      short loc_18017110B
0x180171154  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180171158  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180171161  mov     r8d, ebx; nNumberOfBytesToRead
0x180171164  mov     rdx, rax; lpBuffer
0x180171167  mov     rcx, rdi; hFile
0x18017116a  call    cs:__imp_ReadFile
0x180171170  test    eax, eax
0x180171172  jnz     short loc_180171198
0x180171174  call    cs:__imp_GetLastError
0x18017117a  mov     ebx, eax
0x18017117c  test    eax, eax
0x18017117e  jle     short loc_180171189
0x180171180  movzx   ebx, ax
0x180171183  or      ebx, 80070000h
0x180171189  cmp     ebx, 80310000h
0x18017118f  jnz     short loc_1801711DB
0x180171191  xor     ebx, ebx
0x180171193  lea     edx, [rbx+1]
0x180171196  jmp     short loc_1801711D3
0x180171198  mov     edx, [rbp+NumberOfBytesRead]
0x18017119b  xor     r8d, r8d
0x18017119e  mov     rcx, r14
0x1801711a1  call    FveCheckVolumeTypeEx
0x1801711a6  lea     ecx, [rax-2]
0x1801711a9  cmp     ecx, 1
0x1801711ac  jbe     short loc_1801711CA
0x1801711ae  cmp     eax, 1
0x1801711b1  jnz     short loc_1801711C3
0x1801711b3  mov     rcx, rdi; hDevice
0x1801711b6  call    FvepCheckForVolumeControlFiles
0x1801711bb  mov     ebx, eax
0x1801711bd  test    eax, eax
0x1801711bf  js      short loc_1801711DB
0x1801711c1  jmp     short loc_1801711CC
0x1801711c3  mov     ebx, 1
0x1801711c8  jmp     short loc_1801711CC
0x1801711ca  xor     ebx, ebx
0x1801711cc  xor     edx, edx
0x1801711ce  test    ebx, ebx
0x1801711d0  setz    dl
0x1801711d3  mov     rcx, rsi
0x1801711d6  call    FvepSetVolumeEncryptedCached
0x1801711db  xor     edx, edx; dwSize
0x1801711dd  mov     r8d, 8000h; dwFreeType
0x1801711e3  mov     rcx, r14; lpAddress
0x1801711e6  call    cs:__imp_VirtualFree
0x1801711ec  mov     rcx, rdi; hObject
0x1801711ef  call    cs:__imp_CloseHandle
0x1801711f5  mov     eax, ebx
0x1801711f7  mov     rcx, [rbp+var_8]
0x1801711fb  xor     rcx, rsp; StackCookie
0x1801711fe  call    __security_check_cookie
0x180171203  lea     r11, [rsp+70h+var_s0]
0x180171208  mov     rbx, [r11+28h]
0x18017120c  mov     rsi, [r11+30h]
0x180171210  mov     rsp, r11
0x180171213  pop     r14
0x180171215  pop     rdi
0x180171216  pop     rbp
0x180171217  retn
```
