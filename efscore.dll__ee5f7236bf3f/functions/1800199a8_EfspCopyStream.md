# EfspCopyStream

- ea: `0x1800199a8`
- end: `0x180019d75`
- name: `EfspCopyStream`
- size: `973`
- prototype: `__int64 __fastcall(HANDLE hFile, HANDLE)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180013748`
- `0x180019598`
- `0x180019e9c`
- `0x18001a7a0`

## callees

- `0x1800102f0`
- `0x180010bf0`
- `0x1800199a8`
- `0x180019d7c`
- `0x180063698`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019bad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019bad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019cb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019cb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d06`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180019a09`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180019c2f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180019a09`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180019c2f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180019a32`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180019a32`
- `ntdll!NtFlushBuffersFile` at `0x180019d17`
- `ntdll!NtFlushBuffersFile` at `0x180019d17`
- `ntdll!NtSetInformationFile` at `0x180019af9`
- `ntdll!NtSetInformationFile` at `0x180019af9`
- `ntdll!NtFsControlFile` at `0x180019ac3`
- `ntdll!NtFsControlFile` at `0x180019b97`
- `ntdll!NtFsControlFile` at `0x180019ac3`
- `ntdll!NtFsControlFile` at `0x180019b97`
- `ntdll!RtlNtStatusToDosError` at `0x180019b2d`
- `ntdll!RtlNtStatusToDosError` at `0x180019ca7`
- `ntdll!RtlNtStatusToDosError` at `0x180019d44`
- `ntdll!RtlNtStatusToDosError` at `0x180019b2d`
- `ntdll!RtlNtStatusToDosError` at `0x180019ca7`
- `ntdll!RtlNtStatusToDosError` at `0x180019d44`

## pseudocode

```c
DWORD __fastcall EfspCopyStream(HANDLE hFile, HANDLE a2, __int64 a3)
{
  __int64 *v3; // r15
  HANDLE v6; // r14
  HANDLE FileMappingW; // r12
  DWORD LastError; // eax
  NTSTATUS v10; // eax
  NTSTATUS v11; // ebx
  NTSTATUS v12; // eax
  ULONG OutputBufferLength; // r15d
  char *OutputBuffer; // rax
  char *v15; // r13
  int Status; // ebx
  ULONG v17; // ebx
  unsigned int v18; // r14d
  unsigned int v19; // r15d
  ULONG v20; // eax
  ULONG v21; // eax
  NTSTATUS v22; // eax
  NTSTATUS v23; // r14d
  LONG DistanceToMoveHigh[2]; // [rsp+50h] [rbp-29h] BYREF
  HANDLE hFilea; // [rsp+58h] [rbp-21h]
  __int64 dwAllocationGranularity; // [rsp+60h] [rbp-19h] BYREF
  __int64 FileInformation; // [rsp+68h] [rbp-11h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  HANDLE FileHandle; // [rsp+80h] [rbp+7h]
  __m128i InputBuffer; // [rsp+88h] [rbp+Fh] BYREF

  FileHandle = a2;
  v3 = (__int64 *)(a3 + 8);
  hFilea = hFile;
  v6 = hFile;
  DistanceToMoveHigh[1] = 0;
  IoStatusBlock = 0;
  if ( !*(_QWORD *)(a3 + 8) )
    return 0;
  SetFilePointer(hFile, 0, 0, 0);
  dwAllocationGranularity = g_si.dwAllocationGranularity;
  FileMappingW = CreateFileMappingW(a2, 0, 2u, 0, 0, 0);
  if ( !FileMappingW )
  {
    LastError = GetLastError();
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 10, 249);
    return GetLastError();
  }
  if ( (*(_DWORD *)a3 & 0x200) != 0 )
  {
    InputBuffer = 0;
    v10 = NtFsControlFile(v6, 0, 0, 0, &IoStatusBlock, 0x900C4u, 0, 0, 0, 0);
    v11 = v10;
    if ( v10 < 0 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v10, 10, 23);
LABEL_10:
      CloseHandle(FileMappingW);
      return RtlNtStatusToDosError(v11);
    }
    FileInformation = *v3;
    v12 = NtSetInformationFile(v6, &IoStatusBlock, &FileInformation, 8u, FileEndOfFileInformation);
    v11 = v12;
    if ( v12 < 0 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v12, 10, 40);
      goto LABEL_10;
    }
    OutputBufferLength = 4096;
    InputBuffer = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      OutputBuffer = (char *)wil::details::heap_allocator::allocate(OutputBufferLength);
      v15 = OutputBuffer;
      if ( !OutputBuffer )
      {
        CloseHandle(FileMappingW);
        return 8;
      }
      Status = NtFsControlFile(
                 FileHandle,
                 0,
                 0,
                 0,
                 &IoStatusBlock,
                 0x940CFu,
                 &InputBuffer,
                 0x10u,
                 OutputBuffer,
                 OutputBufferLength);
      if ( Status == 259 )
      {
        WaitForSingleObject(FileHandle, 0xFFFFFFFF);
        Status = IoStatusBlock.Status;
      }
      if ( Status < 0 )
      {
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, Status, 10, 84);
        EfsFreeHeap(v15);
        v15 = 0;
        OutputBufferLength += 4096;
      }
    }
    while ( Status == -2147483643 );
    if ( Status < 0 )
    {
      v17 = RtlNtStatusToDosError(Status);
    }
    else
    {
      v17 = 0;
      v18 = LODWORD(IoStatusBlock.Information) >> 4;
      v19 = 0;
      if ( LODWORD(IoStatusBlock.Information) >> 4 )
      {
        while ( 1 )
        {
          FileInformation = 16LL * v19;
          *(_QWORD *)DistanceToMoveHigh = *(_QWORD *)&v15[FileInformation];
          if ( SetFilePointer(hFilea, DistanceToMoveHigh[0], &DistanceToMoveHigh[1], 0) != -1
            || (v17 = GetLastError()) != 0 )
          {
            v20 = EfspCopyStreamSection(hFilea, FileMappingW, (__int64)&dwAllocationGranularity);
            v17 = v20;
            if ( v20 )
              break;
          }
          if ( ++v19 >= v18 )
            goto LABEL_24;
        }
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v20, 10, 123);
      }
LABEL_24:
      v6 = hFilea;
    }
    EfsFreeHeap(v15);
  }
  else
  {
    DistanceToMoveHigh[1] = 0;
    v21 = EfspCopyStreamSection(v6, FileMappingW, (__int64)&dwAllocationGranularity);
    v17 = v21;
    if ( v21 )
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v21, 10, 157);
  }
  CloseHandle(FileMappingW);
  if ( !v17 )
  {
    v22 = NtFlushBuffersFile(v6, &IoStatusBlock);
    v23 = v22;
    if ( v22 < 0 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v22, 10, 173);
      return RtlNtStatusToDosError(v23);
    }
  }
  return v17;
}

```

## disassembly

```asm
0x1800199a8  mov     [rsp-8+arg_18], rbx
0x1800199ad  push    rbp
0x1800199ae  push    rsi
0x1800199af  push    rdi
0x1800199b0  push    r12
0x1800199b2  push    r13
0x1800199b4  push    r14
0x1800199b6  push    r15
0x1800199b8  lea     rbp, [rsp-27h]
0x1800199bd  sub     rsp, 0A0h
0x1800199c4  mov     rax, cs:__security_cookie
0x1800199cb  xor     rax, rsp
0x1800199ce  mov     [rbp+57h+var_38], rax
0x1800199d2  xor     r13d, r13d
0x1800199d5  mov     [rbp+57h+FileHandle], rdx
0x1800199d9  lea     r15, [r8+8]
0x1800199dd  mov     [rbp+57h+hFile], rcx
0x1800199e1  xorps   xmm0, xmm0
0x1800199e4  mov     rbx, r8
0x1800199e7  mov     rdi, rdx
0x1800199ea  mov     r14, rcx
0x1800199ed  mov     qword ptr [rbp+57h+DistanceToMoveHigh], r13
0x1800199f1  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800199f5  cmp     [r15], r13
0x1800199f8  jnz     short loc_180019A01
0x1800199fa  xor     eax, eax
0x1800199fc  jmp     loc_180019D4E
0x180019a01  xor     r9d, r9d; dwMoveMethod
0x180019a04  xor     r8d, r8d; lpDistanceToMoveHigh
0x180019a07  xor     edx, edx; lDistanceToMove
0x180019a09  call    cs:__imp_SetFilePointer
0x180019a0f  mov     eax, cs:?g_si@@3U_SYSTEM_INFO@@A.dwAllocationGranularity; _SYSTEM_INFO g_si ...
0x180019a15  xor     r9d, r9d; dwMaximumSizeHigh
0x180019a18  mov     [rsp+0D0h+lpName], r13; lpName
0x180019a1d  xor     edx, edx; lpFileMappingAttributes
0x180019a1f  mov     rcx, rdi; hFile
0x180019a22  mov     dword ptr [rbp+57h+var_70+4], r13d
0x180019a26  mov     dword ptr [rbp+57h+var_70], eax
0x180019a29  lea     r8d, [r9+2]; flProtect
0x180019a2d  mov     [rsp+0D0h+dwMaximumSizeLow], r13d; dwMaximumSizeLow
0x180019a32  call    cs:__imp_CreateFileMappingW
0x180019a38  mov     r12, rax
0x180019a3b  test    rax, rax
0x180019a3e  jnz     short loc_180019A74
0x180019a40  call    cs:__imp_GetLastError
0x180019a46  mov     rcx, cs:g_hPublisher
0x180019a4d  lea     r9d, [r12+0Ah]
0x180019a52  mov     r8d, eax
0x180019a55  mov     [rsp+0D0h+dwMaximumSizeLow], 0AF9h
0x180019a5d  lea     rdx, EFS_API_ERROR
0x180019a64  call    fnEfsLogTrace1
0x180019a69  call    cs:__imp_GetLastError
0x180019a6f  jmp     loc_180019D4E
0x180019a74  test    dword ptr [rbx], 200h
0x180019a7a  lea     rsi, EFS_API_ERROR
0x180019a81  mov     edi, 0Ah
0x180019a86  mov     rcx, r14; hFile
0x180019a89  jz      loc_180019CC4
0x180019a8f  mov     [rsp+0D0h+OutputBufferLength], r13d; OutputBufferLength
0x180019a94  lea     rax, [rbp+57h+IoStatusBlock]
0x180019a98  mov     [rsp+0D0h+OutputBuffer], r13; OutputBuffer
0x180019a9d  xorps   xmm0, xmm0
0x180019aa0  mov     [rsp+0D0h+InputBufferLength], r13d; InputBufferLength
0x180019aa5  xor     r9d, r9d; ApcContext
0x180019aa8  mov     [rsp+0D0h+InputBuffer], r13; InputBuffer
0x180019aad  xor     r8d, r8d; ApcRoutine
0x180019ab0  mov     dword ptr [rsp+0D0h+lpName], 900C4h; FsControlCode
0x180019ab8  xor     edx, edx; Event
0x180019aba  mov     qword ptr [rsp+0D0h+dwMaximumSizeLow], rax; IoStatusBlock
0x180019abf  movups  [rbp+57h+var_48], xmm0
0x180019ac3  call    cs:__imp_NtFsControlFile
0x180019ac9  mov     ebx, eax
0x180019acb  test    eax, eax
0x180019acd  jns     short loc_180019AD9
0x180019acf  mov     [rsp+0D0h+dwMaximumSizeLow], 0B17h
0x180019ad7  jmp     short loc_180019B0D
0x180019ad9  mov     rax, [r15]
0x180019adc  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180019ae0  mov     r9d, 8; Length
0x180019ae6  mov     [rbp+57h+FileInformation], rax
0x180019aea  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180019aee  mov     [rsp+0D0h+dwMaximumSizeLow], 14h; FileInformationClass
0x180019af6  mov     rcx, r14; FileHandle
0x180019af9  call    cs:__imp_NtSetInformationFile
0x180019aff  mov     ebx, eax
0x180019b01  test    eax, eax
0x180019b03  jns     short loc_180019B38
0x180019b05  mov     [rsp+0D0h+dwMaximumSizeLow], 0B28h
0x180019b0d  mov     rcx, cs:g_hPublisher
0x180019b14  mov     r9d, edi
0x180019b17  mov     r8d, eax
0x180019b1a  mov     rdx, rsi
0x180019b1d  call    fnEfsLogTrace1
0x180019b22  mov     rcx, r12; hObject
0x180019b25  call    cs:__imp_CloseHandle
0x180019b2b  mov     ecx, ebx; Status
0x180019b2d  call    cs:__imp_RtlNtStatusToDosError
0x180019b33  jmp     loc_180019D4E
0x180019b38  movdqa  xmm0, cs:__xmm@7fffffffffffffff0000000000000000
0x180019b40  mov     r15d, 1000h
0x180019b46  movdqu  [rbp+57h+var_48], xmm0
0x180019b4b  mov     ecx, r15d; unsigned __int64
0x180019b4e  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180019b53  mov     r13, rax
0x180019b56  test    rax, rax
0x180019b59  jz      loc_180019CB1
0x180019b5f  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180019b63  xor     r9d, r9d; ApcContext
0x180019b66  mov     [rsp+0D0h+OutputBufferLength], r15d; OutputBufferLength
0x180019b6b  xor     r8d, r8d; ApcRoutine
0x180019b6e  mov     [rsp+0D0h+OutputBuffer], rax; OutputBuffer
0x180019b73  xor     edx, edx; Event
0x180019b75  mov     [rsp+0D0h+InputBufferLength], 10h; InputBufferLength
0x180019b7d  lea     rax, [rbp+57h+var_48]
0x180019b81  mov     [rsp+0D0h+InputBuffer], rax; InputBuffer
0x180019b86  lea     rax, [rbp+57h+IoStatusBlock]
0x180019b8a  mov     dword ptr [rsp+0D0h+lpName], 940CFh; FsControlCode
0x180019b92  mov     qword ptr [rsp+0D0h+dwMaximumSizeLow], rax; IoStatusBlock
0x180019b97  call    cs:__imp_NtFsControlFile
0x180019b9d  mov     ebx, eax
0x180019b9f  cmp     eax, 103h
0x180019ba4  jnz     short loc_180019BB6
0x180019ba6  mov     rcx, [rbp+57h+FileHandle]; hHandle
0x180019baa  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180019bad  call    cs:__imp_WaitForSingleObject
0x180019bb3  mov     ebx, dword ptr [rbp+57h+IoStatusBlock]
0x180019bb6  test    ebx, ebx
0x180019bb8  jns     short loc_180019BE9
0x180019bba  mov     rcx, cs:g_hPublisher
0x180019bc1  mov     r9d, edi
0x180019bc4  mov     r8d, ebx
0x180019bc7  mov     [rsp+0D0h+dwMaximumSizeLow], 0B54h
0x180019bcf  mov     rdx, rsi
0x180019bd2  call    fnEfsLogTrace1
0x180019bd7  mov     rcx, r13; lpMem
0x180019bda  call    EfsFreeHeap
0x180019bdf  xor     r13d, r13d
0x180019be2  add     r15d, 1000h
0x180019be9  cmp     ebx, 80000005h
0x180019bef  jz      loc_180019B4B
0x180019bf5  test    ebx, ebx
0x180019bf7  js      loc_180019CA5
0x180019bfd  mov     r14d, dword ptr [rbp+57h+IoStatusBlock.Information]
0x180019c01  xor     ebx, ebx
0x180019c03  shr     r14d, 4
0x180019c07  xor     r15d, r15d
0x180019c0a  test    r14d, r14d
0x180019c0d  jz      short loc_180019C78
0x180019c0f  mov     rcx, [rbp+57h+hFile]; hFile
0x180019c13  lea     r8, [rbp+57h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x180019c17  mov     eax, r15d
0x180019c1a  xor     r9d, r9d; dwMoveMethod
0x180019c1d  shl     rax, 4
0x180019c21  mov     [rbp+57h+FileInformation], rax
0x180019c25  mov     rax, [rax+r13]
0x180019c29  mov     edx, eax; lDistanceToMove
0x180019c2b  mov     qword ptr [rbp+57h+DistanceToMoveHigh], rax
0x180019c2f  call    cs:__imp_SetFilePointer
0x180019c35  cmp     eax, 0FFFFFFFFh
0x180019c38  jnz     short loc_180019C46
0x180019c3a  call    cs:__imp_GetLastError
0x180019c40  mov     ebx, eax
0x180019c42  test    eax, eax
0x180019c44  jz      short loc_180019C70
0x180019c46  mov     r9, [rbp+57h+FileInformation]
0x180019c4a  lea     rax, [rbp+57h+var_70]
0x180019c4e  mov     rcx, [rbp+57h+hFile]; hFile
0x180019c52  lea     r8, [rbp+57h+DistanceToMoveHigh]
0x180019c56  add     r9, 8
0x180019c5a  mov     qword ptr [rsp+0D0h+dwMaximumSizeLow], rax; __int64
0x180019c5f  add     r9, r13
0x180019c62  mov     rdx, r12; hFileMappingObject
0x180019c65  call    EfspCopyStreamSection
0x180019c6a  mov     ebx, eax
0x180019c6c  test    eax, eax
0x180019c6e  jnz     short loc_180019C86
0x180019c70  inc     r15d
0x180019c73  cmp     r15d, r14d
0x180019c76  jb      short loc_180019C0F
0x180019c78  mov     r14, [rbp+57h+hFile]
0x180019c7c  mov     rcx, r13; lpMem
0x180019c7f  call    EfsFreeHeap
0x180019c84  jmp     short loc_180019D03
0x180019c86  mov     rcx, cs:g_hPublisher
0x180019c8d  mov     r9d, edi
0x180019c90  mov     r8d, eax
0x180019c93  mov     [rsp+0D0h+dwMaximumSizeLow], 0B7Bh
0x180019c9b  mov     rdx, rsi
0x180019c9e  call    fnEfsLogTrace1
0x180019ca3  jmp     short loc_180019C78
0x180019ca5  mov     ecx, ebx; Status
0x180019ca7  call    cs:__imp_RtlNtStatusToDosError
0x180019cad  mov     ebx, eax
0x180019caf  jmp     short loc_180019C7C
0x180019cb1  mov     rcx, r12; hObject
0x180019cb4  call    cs:__imp_CloseHandle
0x180019cba  mov     eax, 8
0x180019cbf  jmp     loc_180019D4E
0x180019cc4  lea     rax, [rbp+57h+var_70]
0x180019cc8  mov     qword ptr [rbp+57h+DistanceToMoveHigh], r13
0x180019ccc  mov     r9, r15
0x180019ccf  mov     qword ptr [rsp+0D0h+dwMaximumSizeLow], rax; __int64
0x180019cd4  lea     r8, [rbp+57h+DistanceToMoveHigh]
0x180019cd8  mov     rdx, r12; hFileMappingObject
0x180019cdb  call    EfspCopyStreamSection
0x180019ce0  mov     ebx, eax
0x180019ce2  test    eax, eax
0x180019ce4  jz      short loc_180019D03
0x180019ce6  mov     rcx, cs:g_hPublisher
0x180019ced  mov     r9d, edi
0x180019cf0  mov     r8d, eax
0x180019cf3  mov     [rsp+0D0h+dwMaximumSizeLow], 0B9Dh
0x180019cfb  mov     rdx, rsi
0x180019cfe  call    fnEfsLogTrace1
0x180019d03  mov     rcx, r12; hObject
0x180019d06  call    cs:__imp_CloseHandle
0x180019d0c  test    ebx, ebx
0x180019d0e  jnz     short loc_180019D4C
0x180019d10  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180019d14  mov     rcx, r14; FileHandle
0x180019d17  call    cs:__imp_NtFlushBuffersFile
0x180019d1d  mov     r14d, eax
0x180019d20  test    eax, eax
0x180019d22  jns     short loc_180019D4C
0x180019d24  mov     rcx, cs:g_hPublisher
0x180019d2b  mov     r9d, edi
0x180019d2e  mov     r8d, eax
0x180019d31  mov     [rsp+0D0h+dwMaximumSizeLow], 0BADh
0x180019d39  mov     rdx, rsi
0x180019d3c  call    fnEfsLogTrace1
0x180019d41  mov     ecx, r14d; Status
0x180019d44  call    cs:__imp_RtlNtStatusToDosError
0x180019d4a  mov     ebx, eax
0x180019d4c  mov     eax, ebx
0x180019d4e  mov     rcx, [rbp+57h+var_38]
0x180019d52  xor     rcx, rsp; StackCookie
0x180019d55  call    __security_check_cookie
0x180019d5a  mov     rbx, [rsp+0D0h+arg_18]
0x180019d62  add     rsp, 0A0h
0x180019d69  pop     r15
0x180019d6b  pop     r14
0x180019d6d  pop     r13
0x180019d6f  pop     r12
0x180019d71  pop     rdi
0x180019d72  pop     rsi
0x180019d73  pop     rbp
0x180019d74  retn
```
