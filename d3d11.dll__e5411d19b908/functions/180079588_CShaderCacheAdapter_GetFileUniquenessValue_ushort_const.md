# CShaderCacheAdapter::GetFileUniquenessValue(ushort const *)

- ea: `0x180079588`
- end: `0x1800796a9`
- name: `?GetFileUniquenessValue@CShaderCacheAdapter@@SA_KPEBG@Z`
- size: `289`
- prototype: `unsigned __int64 __fastcall(LPCWSTR lpwstrFilename)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800792a0`

## callees

- `0x1800354b8`
- `0x180037290`
- `0x180079588`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800795e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800795e7`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18007965e`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18007965e`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180079607`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180079607`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x180079637`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x180079637`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800795b9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800795b9`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800795de`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800795de`

## pseudocode

```c
struct _FILETIME __fastcall CShaderCacheAdapter::GetFileUniquenessValue(LPCWSTR lpwstrFilename)
{
  HANDLE FileW; // rax
  void *v3; // rbx
  DWORD FileVersionInfoSize; // eax
  void *lpData; // rbx
  BOOL FileVersionInfo; // eax
  unsigned int v8; // edx
  __int64 v9; // [rsp+40h] [rbp-18h]
  DWORD dwLen; // [rsp+68h] [rbp+10h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+70h] [rbp+18h] BYREF
  LPVOID lpBuffer; // [rsp+78h] [rbp+20h] BYREF

  FileW = CreateFileW(lpwstrFilename, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v3 = FileW;
  LastWriteTime = 0;
  if ( FileW != (HANDLE)-1LL )
  {
    GetFileTime(FileW, 0, 0, &LastWriteTime);
    CloseHandle(v3);
    return LastWriteTime;
  }
  FileVersionInfoSize = GetFileVersionInfoSizeExW(1u, lpwstrFilename, 0);
  dwLen = FileVersionInfoSize;
  if ( !FileVersionInfoSize )
    return 0;
  try
  {
    lpData = operator new[](FileVersionInfoSize);
    FileVersionInfo = GetFileVersionInfoExW(3u, lpwstrFilename, 0, dwLen, lpData);
  }
  catch ( std::bad_alloc )
  {
    return 0;
  }
  if ( !FileVersionInfo || (lpBuffer = 0, !VerQueryValueW(lpData, L"\\", &lpBuffer, &dwLen)) )
  {
    if ( lpData )
      SmallDDIElLayout::operator delete(lpData, v8);
    return 0;
  }
  HIDWORD(v9) = *((_DWORD *)lpBuffer + 2);
  LODWORD(v9) = *((_DWORD *)lpBuffer + 3);
  if ( lpData )
    SmallDDIElLayout::operator delete(lpData, v8);
  return (struct _FILETIME)v9;
}

```

## disassembly

```asm
0x180079588  mov     rax, rsp
0x18007958b  mov     [rax+8], rbx
0x18007958f  push    rdi
0x180079590  sub     rsp, 50h
0x180079594  mov     rdi, rcx
0x180079597  mov     qword ptr [rax-28h], 0
0x18007959f  mov     dword ptr [rax-30h], 80h
0x1800795a6  mov     dword ptr [rax-38h], 3
0x1800795ad  xor     r9d, r9d; lpSecurityAttributes
0x1800795b0  mov     edx, 80000000h; dwDesiredAccess
0x1800795b5  lea     r8d, [r9+1]; dwShareMode
0x1800795b9  call    cs:__imp_CreateFileW
0x1800795bf  mov     rbx, rax
0x1800795c2  mov     qword ptr [rsp+58h+LastWriteTime.dwLowDateTime], 0
0x1800795cb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800795cf  jz      short loc_1800795FD
0x1800795d1  lea     r9, [rsp+58h+LastWriteTime]; lpLastWriteTime
0x1800795d6  xor     r8d, r8d; lpLastAccessTime
0x1800795d9  xor     edx, edx; lpCreationTime
0x1800795db  mov     rcx, rax; hFile
0x1800795de  call    cs:__imp_GetFileTime
0x1800795e4  mov     rcx, rbx; hObject
0x1800795e7  call    cs:__imp_CloseHandle
0x1800795ed  mov     rax, qword ptr [rsp+58h+LastWriteTime.dwLowDateTime]
0x1800795f2  mov     rbx, [rsp+58h+arg_0]
0x1800795f7  add     rsp, 50h
0x1800795fb  pop     rdi
0x1800795fc  retn
0x1800795fd  xor     r8d, r8d; lpdwHandle
0x180079600  mov     rdx, rdi; lpwstrFilename
0x180079603  lea     ecx, [r8+1]; dwFlags
0x180079607  call    cs:__imp_GetFileVersionInfoSizeExW
0x18007960d  mov     [rsp+58h+dwLen], eax
0x180079611  test    eax, eax
0x180079613  jz      loc_1800796A0
0x180079619  mov     ecx, eax; unsigned __int64
0x18007961b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180079620  mov     rbx, rax
0x180079623  mov     [rsp+58h+lpData], rax; lpData
0x180079628  mov     r9d, [rsp+58h+dwLen]; dwLen
0x18007962d  xor     r8d, r8d; dwHandle
0x180079630  mov     rdx, rdi; lpwstrFilename
0x180079633  lea     ecx, [r8+3]; dwFlags
0x180079637  call    cs:__imp_GetFileVersionInfoExW
0x18007963d  test    eax, eax
0x18007963f  jz      short loc_180079692
0x180079641  mov     [rsp+58h+lpBuffer], 0
0x18007964a  lea     r9, [rsp+58h+dwLen]; puLen
0x18007964f  lea     r8, [rsp+58h+lpBuffer]; lplpBuffer
0x180079654  lea     rdx, SubBlock; "\\"
0x18007965b  mov     rcx, rbx; pBlock
0x18007965e  call    cs:__imp_VerQueryValueW
0x180079664  test    eax, eax
0x180079666  jz      short loc_180079692
0x180079668  mov     rcx, [rsp+58h+lpBuffer]
0x18007966d  mov     eax, [rcx+8]
0x180079670  mov     dword ptr [rsp+58h+var_18+4], eax
0x180079674  mov     eax, [rcx+0Ch]
0x180079677  mov     dword ptr [rsp+58h+var_18], eax
0x18007967b  test    rbx, rbx
0x18007967e  jz      short loc_180079688
0x180079680  mov     rcx, rbx; void *
0x180079683  call    ??3SmallDDIElLayout@@KAXPEAXI@Z; SmallDDIElLayout::operator delete(void *,uint)
0x180079688  mov     rax, [rsp+58h+var_18]
0x18007968d  jmp     loc_1800795F2
0x180079692  test    rbx, rbx
0x180079695  jz      short loc_1800796A0
0x180079697  mov     rcx, rbx; void *
0x18007969a  call    ??3SmallDDIElLayout@@KAXPEAXI@Z; SmallDDIElLayout::operator delete(void *,uint)
0x18007969f  nop
0x1800796a0  xor     eax, eax
0x1800796a2  jmp     loc_1800795F2
0x1800796a7  jmp     short loc_1800796A0
```
