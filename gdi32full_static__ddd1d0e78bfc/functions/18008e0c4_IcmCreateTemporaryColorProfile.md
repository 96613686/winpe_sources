# IcmCreateTemporaryColorProfile

- ea: `0x18008e0c4`
- end: `0x18008e26a`
- name: `IcmCreateTemporaryColorProfile`
- size: `422`
- prototype: `__int64 __fastcall(unsigned __int16 *, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18003b834`

## callees

- `0x18003a6f8`
- `0x18006c658`
- `0x18006fde0`
- `0x18007ff9c`
- `0x18008e0c4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18008e168`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18008e168`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008e1bb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008e1bb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008e1ee`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008e1ee`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008e236`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008e236`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008e211`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008e227`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008e211`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008e227`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18008e113`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18008e113`

## pseudocode

```c
_BOOL8 __fastcall IcmCreateTemporaryColorProfile(unsigned __int16 *a1, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  BOOL v6; // edi
  int v7; // ebx
  unsigned __int64 v8; // rdx
  int v9; // eax
  UINT TempFileNameW; // ecx
  BOOL v11; // ebx
  int v12; // edi
  HANDLE FileW; // rax
  void *v14; // rbx
  unsigned __int16 *v16; // [rsp+40h] [rbp-58h] BYREF
  const unsigned __int16 *v17; // [rsp+48h] [rbp-50h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+B8h] [rbp+20h] BYREF

  v6 = 0;
  v17 = (const unsigned __int16 *)operator new[](0x208u);
  v16 = (unsigned __int16 *)operator new[](0x208u);
  if ( (unsigned int)GetTempPath2W(260, v17) )
  {
    if ( *a1 )
    {
      v7 = StringCchCopyW(v16, 0x104u, v17);
      v9 = StringCchCatW(v16, v8, a1);
      TempFileNameW = 0;
      v11 = v7 >= 0;
      if ( v9 >= 0 )
        TempFileNameW = v11;
    }
    else
    {
      TempFileNameW = GetTempFileNameW(v17, L"ICM", 0, v16);
    }
    if ( TempFileNameW )
    {
      if ( !nNumberOfBytesToWrite )
      {
        v12 = StringCchCopyW(a1, 0x104u, v16);
LABEL_13:
        v6 = v12 >= 0;
        goto LABEL_15;
      }
      FileW = CreateFileW(v16, 0xC0000000, 0, 0, 2u, 0x80u, 0);
      v14 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        NumberOfBytesWritten = 0;
        if ( !WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
        {
          CloseHandle(v14);
          DeleteFileW(v16);
          goto LABEL_15;
        }
        v12 = StringCchCopyW(a1, 0x104u, v16);
        CloseHandle(v14);
        goto LABEL_13;
      }
    }
  }
LABEL_15:
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v16);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v17);
  return v6;
}

```

## disassembly

```asm
0x18008e0c4  push    rbx
0x18008e0c6  push    rbp
0x18008e0c7  push    rsi
0x18008e0c8  push    rdi
0x18008e0c9  push    r12
0x18008e0cb  push    r13
0x18008e0cd  push    r14
0x18008e0cf  push    r15
0x18008e0d1  sub     rsp, 58h
0x18008e0d5  mov     rbp, rcx
0x18008e0d8  mov     esi, 208h
0x18008e0dd  xor     r12d, r12d
0x18008e0e0  mov     ecx, esi; unsigned __int64
0x18008e0e2  mov     r14d, r8d
0x18008e0e5  mov     r15, rdx
0x18008e0e8  mov     edi, r12d
0x18008e0eb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008e0f0  mov     ecx, esi; unsigned __int64
0x18008e0f2  mov     [rsp+98h+var_50], rax
0x18008e0f7  mov     rbx, rax
0x18008e0fa  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008e0ff  mov     r13d, 104h
0x18008e105  mov     [rsp+98h+var_58], rax
0x18008e10a  mov     ecx, r13d
0x18008e10d  mov     rdx, rbx
0x18008e110  mov     rsi, rax
0x18008e113  call    cs:__imp_GetTempPath2W
0x18008e11a  nop     dword ptr [rax+rax+00h]
0x18008e11f  test    eax, eax
0x18008e121  jz      loc_18008E242
0x18008e127  cmp     [rbp+0], r12w
0x18008e12c  jz      short loc_18008E158
0x18008e12e  mov     r8, rbx; unsigned __int16 *
0x18008e131  mov     edx, r13d; unsigned __int64
0x18008e134  mov     rcx, rsi; unsigned __int16 *
0x18008e137  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008e13c  mov     r8, rbp; unsigned __int16 *
0x18008e13f  mov     rcx, rsi; unsigned __int16 *
0x18008e142  mov     ebx, eax
0x18008e144  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008e149  not     ebx
0x18008e14b  mov     ecx, r12d
0x18008e14e  shr     ebx, 1Fh
0x18008e151  test    eax, eax
0x18008e153  cmovns  ecx, ebx
0x18008e156  jmp     short loc_18008E176
0x18008e158  mov     r9, rsi; lpTempFileName
0x18008e15b  lea     rdx, aIcm; "ICM"
0x18008e162  xor     r8d, r8d; uUnique
0x18008e165  mov     rcx, rbx; lpPathName
0x18008e168  call    cs:__imp_GetTempFileNameW
0x18008e16f  nop     dword ptr [rax+rax+00h]
0x18008e174  mov     ecx, eax
0x18008e176  test    ecx, ecx
0x18008e178  jz      loc_18008E242
0x18008e17e  test    r14d, r14d
0x18008e181  jnz     short loc_18008E198
0x18008e183  mov     r8, rsi; unsigned __int16 *
0x18008e186  mov     rdx, r13; unsigned __int64
0x18008e189  mov     rcx, rbp; unsigned __int16 *
0x18008e18c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008e191  mov     edi, eax
0x18008e193  jmp     loc_18008E21D
0x18008e198  mov     [rsp+98h+hTemplateFile], r12; hTemplateFile
0x18008e19d  xor     r9d, r9d; lpSecurityAttributes
0x18008e1a0  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008e1a8  xor     r8d, r8d; dwShareMode
0x18008e1ab  mov     edx, 0C0000000h; dwDesiredAccess
0x18008e1b0  mov     [rsp+98h+dwCreationDisposition], 2; dwCreationDisposition
0x18008e1b8  mov     rcx, rsi; lpFileName
0x18008e1bb  call    cs:__imp_CreateFileW
0x18008e1c2  nop     dword ptr [rax+rax+00h]
0x18008e1c7  mov     rbx, rax
0x18008e1ca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008e1ce  jz      short loc_18008E242
0x18008e1d0  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008e1d8  mov     [rsp+98h+NumberOfBytesWritten], r12d
0x18008e1e0  mov     r8d, r14d; nNumberOfBytesToWrite
0x18008e1e3  mov     qword ptr [rsp+98h+dwCreationDisposition], r12; lpOverlapped
0x18008e1e8  mov     rdx, r15; lpBuffer
0x18008e1eb  mov     rcx, rax; hFile
0x18008e1ee  call    cs:__imp_WriteFile
0x18008e1f5  nop     dword ptr [rax+rax+00h]
0x18008e1fa  test    eax, eax
0x18008e1fc  jz      short loc_18008E224
0x18008e1fe  mov     r8, rsi; unsigned __int16 *
0x18008e201  mov     rdx, r13; unsigned __int64
0x18008e204  mov     rcx, rbp; unsigned __int16 *
0x18008e207  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008e20c  mov     rcx, rbx; hObject
0x18008e20f  mov     edi, eax
0x18008e211  call    cs:__imp_CloseHandle
0x18008e218  nop     dword ptr [rax+rax+00h]
0x18008e21d  not     edi
0x18008e21f  shr     edi, 1Fh
0x18008e222  jmp     short loc_18008E242
0x18008e224  mov     rcx, rbx; hObject
0x18008e227  call    cs:__imp_CloseHandle
0x18008e22e  nop     dword ptr [rax+rax+00h]
0x18008e233  mov     rcx, rsi; lpFileName
0x18008e236  call    cs:__imp_DeleteFileW
0x18008e23d  nop     dword ptr [rax+rax+00h]
0x18008e242  lea     rcx, [rsp+98h+var_58]
0x18008e247  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18008e24c  lea     rcx, [rsp+98h+var_50]
0x18008e251  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18008e256  mov     eax, edi
0x18008e258  add     rsp, 58h
0x18008e25c  pop     r15
0x18008e25e  pop     r14
0x18008e260  pop     r13
0x18008e262  pop     r12
0x18008e264  pop     rdi
0x18008e265  pop     rsi
0x18008e266  pop     rbp
0x18008e267  pop     rbx
0x18008e268  retn
```
