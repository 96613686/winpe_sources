# IcmCreateTemporaryColorProfile

- ea: `0x180088b54`
- end: `0x180088ccc`
- name: `IcmCreateTemporaryColorProfile`
- size: `376`
- prototype: `__int64 __fastcall(unsigned __int16 *, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800356cc`

## callees

- `0x1800346b8`
- `0x1800683b0`
- `0x18006b4ec`
- `0x18007b3ec`
- `0x180088b54`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180088bf2`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180088bf2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180088c3c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180088c3c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180088c69`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180088c69`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180088c9f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180088c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088c86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088c96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088c86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088c96`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180088ba3`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180088ba3`

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
0x180088b54  push    rbx
0x180088b56  push    rbp
0x180088b57  push    rsi
0x180088b58  push    rdi
0x180088b59  push    r12
0x180088b5b  push    r13
0x180088b5d  push    r14
0x180088b5f  push    r15
0x180088b61  sub     rsp, 58h
0x180088b65  mov     rbp, rcx
0x180088b68  mov     esi, 208h
0x180088b6d  xor     r12d, r12d
0x180088b70  mov     ecx, esi; unsigned __int64
0x180088b72  mov     r14d, r8d
0x180088b75  mov     r15, rdx
0x180088b78  mov     edi, r12d
0x180088b7b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180088b80  mov     ecx, esi; unsigned __int64
0x180088b82  mov     [rsp+98h+var_50], rax
0x180088b87  mov     rbx, rax
0x180088b8a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180088b8f  mov     r13d, 104h
0x180088b95  mov     [rsp+98h+var_58], rax
0x180088b9a  mov     ecx, r13d
0x180088b9d  mov     rdx, rbx
0x180088ba0  mov     rsi, rax
0x180088ba3  call    cs:__imp_GetTempPath2W
0x180088ba9  test    eax, eax
0x180088bab  jz      loc_180088CA5
0x180088bb1  cmp     [rbp+0], r12w
0x180088bb6  jz      short loc_180088BE2
0x180088bb8  mov     r8, rbx; unsigned __int16 *
0x180088bbb  mov     edx, r13d; unsigned __int64
0x180088bbe  mov     rcx, rsi; unsigned __int16 *
0x180088bc1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180088bc6  mov     r8, rbp; unsigned __int16 *
0x180088bc9  mov     rcx, rsi; unsigned __int16 *
0x180088bcc  mov     ebx, eax
0x180088bce  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180088bd3  not     ebx
0x180088bd5  mov     ecx, r12d
0x180088bd8  shr     ebx, 1Fh
0x180088bdb  test    eax, eax
0x180088bdd  cmovns  ecx, ebx
0x180088be0  jmp     short loc_180088BFA
0x180088be2  mov     r9, rsi; lpTempFileName
0x180088be5  lea     rdx, aIcm; "ICM"
0x180088bec  xor     r8d, r8d; uUnique
0x180088bef  mov     rcx, rbx; lpPathName
0x180088bf2  call    cs:__imp_GetTempFileNameW
0x180088bf8  mov     ecx, eax
0x180088bfa  test    ecx, ecx
0x180088bfc  jz      loc_180088CA5
0x180088c02  test    r14d, r14d
0x180088c05  jnz     short loc_180088C19
0x180088c07  mov     r8, rsi; unsigned __int16 *
0x180088c0a  mov     rdx, r13; unsigned __int64
0x180088c0d  mov     rcx, rbp; unsigned __int16 *
0x180088c10  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180088c15  mov     edi, eax
0x180088c17  jmp     short loc_180088C8C
0x180088c19  mov     [rsp+98h+hTemplateFile], r12; hTemplateFile
0x180088c1e  xor     r9d, r9d; lpSecurityAttributes
0x180088c21  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180088c29  xor     r8d, r8d; dwShareMode
0x180088c2c  mov     edx, 0C0000000h; dwDesiredAccess
0x180088c31  mov     [rsp+98h+dwCreationDisposition], 2; dwCreationDisposition
0x180088c39  mov     rcx, rsi; lpFileName
0x180088c3c  call    cs:__imp_CreateFileW
0x180088c42  mov     rbx, rax
0x180088c45  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180088c49  jz      short loc_180088CA5
0x180088c4b  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180088c53  mov     [rsp+98h+NumberOfBytesWritten], r12d
0x180088c5b  mov     r8d, r14d; nNumberOfBytesToWrite
0x180088c5e  mov     qword ptr [rsp+98h+dwCreationDisposition], r12; lpOverlapped
0x180088c63  mov     rdx, r15; lpBuffer
0x180088c66  mov     rcx, rax; hFile
0x180088c69  call    cs:__imp_WriteFile
0x180088c6f  test    eax, eax
0x180088c71  jz      short loc_180088C93
0x180088c73  mov     r8, rsi; unsigned __int16 *
0x180088c76  mov     rdx, r13; unsigned __int64
0x180088c79  mov     rcx, rbp; unsigned __int16 *
0x180088c7c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180088c81  mov     rcx, rbx; hObject
0x180088c84  mov     edi, eax
0x180088c86  call    cs:__imp_CloseHandle
0x180088c8c  not     edi
0x180088c8e  shr     edi, 1Fh
0x180088c91  jmp     short loc_180088CA5
0x180088c93  mov     rcx, rbx; hObject
0x180088c96  call    cs:__imp_CloseHandle
0x180088c9c  mov     rcx, rsi; lpFileName
0x180088c9f  call    cs:__imp_DeleteFileW
0x180088ca5  lea     rcx, [rsp+98h+var_58]
0x180088caa  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180088caf  lea     rcx, [rsp+98h+var_50]
0x180088cb4  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180088cb9  mov     eax, edi
0x180088cbb  add     rsp, 58h
0x180088cbf  pop     r15
0x180088cc1  pop     r14
0x180088cc3  pop     r13
0x180088cc5  pop     r12
0x180088cc7  pop     rdi
0x180088cc8  pop     rsi
0x180088cc9  pop     rbp
0x180088cca  pop     rbx
0x180088ccb  retn
```
