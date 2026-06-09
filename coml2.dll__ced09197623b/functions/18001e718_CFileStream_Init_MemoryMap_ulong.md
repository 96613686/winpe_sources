# CFileStream::Init_MemoryMap(ulong)

- ea: `0x18001e718`
- end: `0x18001ea91`
- name: `?Init_MemoryMap@CFileStream@@AEAAJK@Z`
- size: `889`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18001defc`

## callees

- `0x18001e718`
- `0x180025958`
- `0x180026bc4`
- `0x18003990c`
- `0x18003995c`
- `0x18003e8e4`
- `0x180042800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e95f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e96d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e95f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e96d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea3c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001ea7d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001ea7d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001e76b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001e88a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001e76b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001e88a`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18001ea86`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18001ea86`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001e9f8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001e9f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea57`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001e874`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001e874`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e9cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e9cd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001e9bb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001e9bb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GlobalMemoryStatus` at `0x18001e7e1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GlobalMemoryStatus` at `0x18001e7e1`

## pseudocode

```c
__int64 __fastcall CFileStream::Init_MemoryMap(CFileStream *this)
{
  __int64 v1; // rax
  HANDLE *v2; // rbx
  HANDLE dwMaximumSizeLow; // r12
  DWORD FileSize; // eax
  SIZE_T v6; // r15
  __int64 v7; // rax
  DWORD v8; // ebp
  unsigned int v9; // r13d
  unsigned int v10; // r9d
  __int64 *v11; // rdx
  HANDLE *v12; // r14
  __int64 i; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdi
  DWORD v18; // edi
  int v20; // edi
  DWORD LastError; // eax
  DWORD v22; // r8d
  HANDLE CurrentProcess; // rax
  DWORD v24; // eax
  DWORD v25; // eax
  DWORD FileSizeHigh; // [rsp+40h] [rbp-98h] BYREF
  int v27; // [rsp+44h] [rbp-94h]
  _MEMORYSTATUS Buffer; // [rsp+48h] [rbp-90h] BYREF

  v1 = *((_QWORD *)this + 6);
  v2 = (HANDLE *)((char *)this + 64);
  dwMaximumSizeLow = 0;
  FileSizeHigh = 0;
  v27 = 0;
  if ( (*(_DWORD *)(v1 + 36) & 0xA00) != 0 )
    goto LABEL_30;
  FileSize = GetFileSize(*v2, &FileSizeHigh);
  v6 = FileSize;
  if ( FileSize == -1 && GetLastError() )
  {
    LastError = GetLastError();
    v20 = Win32ErrorToScode(LastError);
    goto LABEL_26;
  }
  if ( FileSizeHigh )
  {
    v20 = -2147286767;
    goto LABEL_26;
  }
  if ( (*(_DWORD *)(*((_QWORD *)this + 6) + 32LL) & 0x280) != 0x200 && (unsigned int)DfIsRemoteFile(*v2) )
  {
LABEL_30:
    v20 = -2147287039;
    goto LABEL_26;
  }
  v7 = *((_QWORD *)this + 6);
  if ( *(char *)(v7 + 32) < 0 )
  {
    if ( (_DWORD)v6 )
      goto LABEL_34;
    if ( (*(_BYTE *)(v7 + 36) & 0xC4) == 0 )
      goto LABEL_25;
    if ( (int)CFileStream::MakeFileStub(this) < 0 )
    {
LABEL_34:
      v8 = 4;
      if ( (unsigned int)v6 >= 0x40000 )
      {
        v9 = 2 * v6;
        goto LABEL_8;
      }
    }
    else
    {
      v27 = 1;
      v8 = 4;
    }
    v9 = 0x80000;
  }
  else
  {
    v8 = 2;
    v9 = v6;
  }
LABEL_8:
  memset(&Buffer, 0, sizeof(Buffer));
  GlobalMemoryStatus(&Buffer);
  if ( v6 <= Buffer.dwTotalPhys >> 1 && Buffer.dwAvailVirtual >= 0x40000000 )
  {
    v11 = (__int64 *)*((_QWORD *)this + 6);
    if ( (*((_BYTE *)v11 + 68) & 1) == 0 )
    {
      v20 = -2147467259;
      goto LABEL_26;
    }
    v12 = (HANDLE *)((char *)this + 96);
    if ( !*((_QWORD *)this + 12) )
    {
      for ( i = *v11; ; i = *(_QWORD *)(v17 + 40) )
      {
        v14 = i ? i + *(_QWORD *)NtCurrentTeb()->ReservedForOle : (__int64)dwMaximumSizeLow;
        v15 = v14 - 32;
        v16 = -v14;
        v17 = v15 & -(__int64)(v16 != 0);
        if ( !v17 )
          break;
        if ( this != (CFileStream *)v17 && *(HANDLE *)((v15 & -(__int64)(v16 != 0)) + 0x60) != dwMaximumSizeLow )
        {
          v22 = *(_DWORD *)((v15 & -(__int64)(v16 != 0)) + 0x20);
          if ( v22 )
          {
            dwMaximumSizeLow = OpenProcess(0x40u, 0, v22);
            if ( dwMaximumSizeLow )
            {
              CurrentProcess = GetCurrentProcess();
              if ( DuplicateHandle(
                     dwMaximumSizeLow,
                     *(HANDLE *)(v17 + 96),
                     CurrentProcess,
                     (LPHANDLE)this + 12,
                     0,
                     0,
                     2u) )
              {
                v20 = 0;
              }
              else
              {
                v24 = GetLastError();
                v20 = Win32ErrorToScode(v24);
              }
              CloseHandle(dwMaximumSizeLow);
              dwMaximumSizeLow = 0;
              if ( v20 < 0 )
                goto LABEL_26;
              break;
            }
          }
        }
      }
      if ( *v12 != dwMaximumSizeLow )
        goto LABEL_21;
      *v12 = CreateFileMappingW(*v2, 0, v8, 0, (DWORD)dwMaximumSizeLow, (LPCWSTR)dwMaximumSizeLow);
      if ( (_DWORD)v6 )
      {
        v18 = GetFileSize(*v2, &FileSizeHigh);
        if ( v18 == -1 && GetLastError() )
        {
          v25 = GetLastError();
          v20 = Win32ErrorToScode(v25);
          if ( *v12 )
          {
            CloseHandle(*v12);
            *v12 = dwMaximumSizeLow;
          }
          goto LABEL_26;
        }
        *(_DWORD *)(*((_QWORD *)this + 6) + 60LL) = v18;
        *(_DWORD *)(*((_QWORD *)this + 6) + 64LL) = v18;
      }
      if ( *v12 == dwMaximumSizeLow )
        goto LABEL_25;
    }
LABEL_21:
    if ( CFileStream::MapView(this, v9, v8, v10) >= 0 )
      return 0;
    CFileStream::TurnOffAllMappings(this);
  }
LABEL_25:
  v20 = -2147024882;
LABEL_26:
  *(_DWORD *)(*((_QWORD *)this + 6) + 68LL) &= ~1u;
  if ( v27 != (_DWORD)dwMaximumSizeLow )
  {
    SetFilePointer(*v2, 0, 0, 0);
    SetEndOfFile(*v2);
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18001e718  push    rbx
0x18001e71a  push    rbp
0x18001e71b  push    rsi
0x18001e71c  push    rdi
0x18001e71d  push    r12
0x18001e71f  push    r13
0x18001e721  push    r14
0x18001e723  push    r15
0x18001e725  sub     rsp, 98h
0x18001e72c  mov     rax, cs:__security_cookie
0x18001e733  xor     rax, rsp
0x18001e736  mov     [rsp+0D8h+var_58], rax
0x18001e73e  mov     rax, [rcx+30h]
0x18001e742  lea     rbx, [rcx+40h]
0x18001e746  xor     r12d, r12d
0x18001e749  mov     rsi, rcx
0x18001e74c  mov     [rsp+0D8h+FileSizeHigh], r12d
0x18001e751  mov     [rsp+0D8h+var_94], r12d
0x18001e756  test    dword ptr [rax+24h], 0A00h
0x18001e75d  jnz     loc_18001E91F
0x18001e763  mov     rcx, [rbx]; hFile
0x18001e766  lea     rdx, [rsp+0D8h+FileSizeHigh]; lpFileSizeHigh
0x18001e76b  call    cs:__imp_GetFileSize
0x18001e771  mov     r15d, eax
0x18001e774  cmp     eax, 0FFFFFFFFh
0x18001e777  jz      loc_18001E95F
0x18001e77d  cmp     [rsp+0D8h+FileSizeHigh], r12d
0x18001e782  ja      loc_18001E97E
0x18001e788  mov     rax, [rsi+30h]
0x18001e78c  mov     ecx, [rax+20h]
0x18001e78f  and     ecx, 280h
0x18001e795  cmp     ecx, 200h
0x18001e79b  jz      short loc_18001E7AD
0x18001e79d  mov     rcx, [rbx]; void *
0x18001e7a0  call    ?DfIsRemoteFile@@YAHPEAX@Z; DfIsRemoteFile(void *)
0x18001e7a5  test    eax, eax
0x18001e7a7  jnz     loc_18001E91F
0x18001e7ad  mov     rax, [rsi+30h]
0x18001e7b1  test    byte ptr [rax+20h], 80h
0x18001e7b5  jnz     loc_18001E926
0x18001e7bb  mov     ebp, 2
0x18001e7c0  mov     r13d, r15d
0x18001e7c3  xorps   xmm0, xmm0
0x18001e7c6  lea     rcx, [rsp+0D8h+Buffer]; lpBuffer
0x18001e7cb  xor     eax, eax
0x18001e7cd  movups  xmmword ptr [rsp+0D8h+Buffer.dwLength], xmm0
0x18001e7d2  mov     [rsp+0D8h+Buffer.dwAvailVirtual], rax
0x18001e7d7  movups  xmmword ptr [rsp+0D8h+Buffer.dwAvailPhys], xmm0
0x18001e7dc  movups  xmmword ptr [rsp+0D8h+Buffer.dwAvailPageFile], xmm0
0x18001e7e1  call    cs:__imp_GlobalMemoryStatus
0x18001e7e7  mov     rcx, [rsp+0D8h+Buffer.dwTotalPhys]
0x18001e7ec  shr     rcx, 1
0x18001e7ef  cmp     r15, rcx
0x18001e7f2  ja      loc_18001E8FC
0x18001e7f8  cmp     [rsp+0D8h+Buffer.dwAvailVirtual], 40000000h
0x18001e801  jb      loc_18001E8FC
0x18001e807  mov     rdx, [rsi+30h]
0x18001e80b  test    byte ptr [rdx+44h], 1
0x18001e80f  jz      loc_18001E918
0x18001e815  lea     r14, [rsi+60h]
0x18001e819  cmp     [r14], r12
0x18001e81c  jnz     loc_18001E8AE
0x18001e822  mov     rdx, [rdx]
0x18001e825  test    rdx, rdx
0x18001e828  jz      loc_18001E997
0x18001e82e  mov     rax, gs:30h
0x18001e837  mov     rcx, [rax+1758h]
0x18001e83e  mov     rcx, [rcx]
0x18001e841  add     rcx, rdx
0x18001e844  lea     rax, [rcx-20h]
0x18001e848  neg     rcx
0x18001e84b  sbb     rdi, rdi
0x18001e84e  and     rdi, rax
0x18001e851  test    rdi, rdi
0x18001e854  jnz     loc_18001E8EA
0x18001e85a  cmp     [r14], r12
0x18001e85d  jnz     short loc_18001E8AE
0x18001e85f  mov     rcx, [rbx]; hFile
0x18001e862  xor     r9d, r9d; dwMaximumSizeHigh
0x18001e865  mov     [rsp+0D8h+lpName], r12; lpName
0x18001e86a  mov     r8d, ebp; flProtect
0x18001e86d  xor     edx, edx; lpFileMappingAttributes
0x18001e86f  mov     [rsp+0D8h+dwMaximumSizeLow], r12d; dwMaximumSizeLow
0x18001e874  call    cs:__imp_CreateFileMappingW
0x18001e87a  mov     [r14], rax
0x18001e87d  test    r15d, r15d
0x18001e880  jz      short loc_18001E8A9
0x18001e882  mov     rcx, [rbx]; hFile
0x18001e885  lea     rdx, [rsp+0D8h+FileSizeHigh]; lpFileSizeHigh
0x18001e88a  call    cs:__imp_GetFileSize
0x18001e890  mov     edi, eax
0x18001e892  cmp     eax, 0FFFFFFFFh
0x18001e895  jz      loc_18001EA2E
0x18001e89b  mov     rax, [rsi+30h]
0x18001e89f  mov     [rax+3Ch], edi
0x18001e8a2  mov     rax, [rsi+30h]
0x18001e8a6  mov     [rax+40h], edi
0x18001e8a9  cmp     [r14], r12
0x18001e8ac  jz      short loc_18001E8FC
0x18001e8ae  mov     edx, r13d; unsigned __int64
0x18001e8b1  mov     r8d, ebp; unsigned int
0x18001e8b4  mov     rcx, rsi; this
0x18001e8b7  call    ?MapView@CFileStream@@AEAAJ_KKK@Z; CFileStream::MapView(unsigned __int64,ulong,ulong)
0x18001e8bc  test    eax, eax
0x18001e8be  js      loc_18001EA65
0x18001e8c4  xor     eax, eax
0x18001e8c6  mov     rcx, [rsp+0D8h+var_58]
0x18001e8ce  xor     rcx, rsp; StackCookie
0x18001e8d1  call    __security_check_cookie
0x18001e8d6  add     rsp, 98h
0x18001e8dd  pop     r15
0x18001e8df  pop     r14
0x18001e8e1  pop     r13
0x18001e8e3  pop     r12
0x18001e8e5  pop     rdi
0x18001e8e6  pop     rsi
0x18001e8e7  pop     rbp
0x18001e8e8  pop     rbx
0x18001e8e9  retn
0x18001e8ea  cmp     rsi, rdi
0x18001e8ed  jnz     loc_18001E99F
0x18001e8f3  mov     rdx, [rdi+28h]
0x18001e8f7  jmp     loc_18001E825
0x18001e8fc  mov     edi, 8007000Eh
0x18001e901  mov     rax, [rsi+30h]
0x18001e905  and     dword ptr [rax+44h], 0FFFFFFFEh
0x18001e909  cmp     [rsp+0D8h+var_94], r12d
0x18001e90e  jnz     loc_18001EA72
0x18001e914  mov     eax, edi
0x18001e916  jmp     short loc_18001E8C6
0x18001e918  mov     edi, 80004005h
0x18001e91d  jmp     short loc_18001E901
0x18001e91f  mov     edi, 80030001h
0x18001e924  jmp     short loc_18001E901
0x18001e926  test    r15d, r15d
0x18001e929  jnz     short loc_18001E93D
0x18001e92b  test    byte ptr [rax+24h], 0C4h
0x18001e92f  jz      short loc_18001E8FC
0x18001e931  mov     rcx, rsi; this
0x18001e934  call    ?MakeFileStub@CFileStream@@AEAAJXZ; CFileStream::MakeFileStub(void)
0x18001e939  test    eax, eax
0x18001e93b  jns     short loc_18001E988
0x18001e93d  mov     ebp, 4
0x18001e942  cmp     r15d, 40000h
0x18001e949  jnb     short loc_18001E956
0x18001e94b  mov     r13d, 80000h
0x18001e951  jmp     loc_18001E7C3
0x18001e956  lea     r13d, [r15+r15]
0x18001e95a  jmp     loc_18001E7C3
0x18001e95f  call    cs:__imp_GetLastError
0x18001e965  test    eax, eax
0x18001e967  jz      loc_18001E77D
0x18001e96d  call    cs:__imp_GetLastError
0x18001e973  mov     ecx, eax; unsigned int
0x18001e975  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18001e97a  mov     edi, eax
0x18001e97c  jmp     short loc_18001E901
0x18001e97e  mov     edi, 80030111h
0x18001e983  jmp     loc_18001E901
0x18001e988  mov     [rsp+0D8h+var_94], 1
0x18001e990  mov     ebp, 4
0x18001e995  jmp     short loc_18001E94B
0x18001e997  mov     rcx, r12
0x18001e99a  jmp     loc_18001E844
0x18001e99f  cmp     [rdi+60h], r12
0x18001e9a3  jz      loc_18001E8F3
0x18001e9a9  mov     r8d, [rdi+20h]; dwProcessId
0x18001e9ad  test    r8d, r8d
0x18001e9b0  jz      loc_18001E8F3
0x18001e9b6  xor     edx, edx; bInheritHandle
0x18001e9b8  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18001e9bb  call    cs:__imp_OpenProcess
0x18001e9c1  mov     r12, rax
0x18001e9c4  test    rax, rax
0x18001e9c7  jz      loc_18001E8F3
0x18001e9cd  call    cs:__imp_GetCurrentProcess
0x18001e9d3  mov     rdx, [rdi+60h]; hSourceHandle
0x18001e9d7  mov     r9, r14; lpTargetHandle
0x18001e9da  mov     [rsp+0D8h+dwOptions], 2; dwOptions
0x18001e9e2  mov     r8, rax; hTargetProcessHandle
0x18001e9e5  mov     dword ptr [rsp+0D8h+lpName], 0; bInheritHandle
0x18001e9ed  mov     rcx, r12; hSourceProcessHandle
0x18001e9f0  mov     [rsp+0D8h+dwMaximumSizeLow], 0; dwDesiredAccess
0x18001e9f8  call    cs:__imp_DuplicateHandle
0x18001e9fe  test    eax, eax
0x18001ea00  jz      short loc_18001EA06
0x18001ea02  xor     edi, edi
0x18001ea04  jmp     short loc_18001EA15
0x18001ea06  call    cs:__imp_GetLastError
0x18001ea0c  mov     ecx, eax; unsigned int
0x18001ea0e  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18001ea13  mov     edi, eax
0x18001ea15  mov     rcx, r12; hObject
0x18001ea18  call    cs:__imp_CloseHandle
0x18001ea1e  xor     r12d, r12d
0x18001ea21  test    edi, edi
0x18001ea23  js      loc_18001E901
0x18001ea29  jmp     loc_18001E85A
0x18001ea2e  call    cs:__imp_GetLastError
0x18001ea34  test    eax, eax
0x18001ea36  jz      loc_18001E89B
0x18001ea3c  call    cs:__imp_GetLastError
0x18001ea42  mov     ecx, eax; unsigned int
0x18001ea44  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18001ea49  mov     rcx, [r14]; hObject
0x18001ea4c  mov     edi, eax
0x18001ea4e  test    rcx, rcx
0x18001ea51  jz      loc_18001E901
0x18001ea57  call    cs:__imp_CloseHandle
0x18001ea5d  mov     [r14], r12
0x18001ea60  jmp     loc_18001E901
0x18001ea65  mov     rcx, rsi; this
0x18001ea68  call    ?TurnOffAllMappings@CFileStream@@QEAAXXZ; CFileStream::TurnOffAllMappings(void)
0x18001ea6d  jmp     loc_18001E8FC
0x18001ea72  mov     rcx, [rbx]; hFile
0x18001ea75  xor     r9d, r9d; dwMoveMethod
0x18001ea78  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001ea7b  xor     edx, edx; lDistanceToMove
0x18001ea7d  call    cs:__imp_SetFilePointer
0x18001ea83  mov     rcx, [rbx]; hFile
0x18001ea86  call    cs:__imp_SetEndOfFile
0x18001ea8c  jmp     loc_18001E914
```
