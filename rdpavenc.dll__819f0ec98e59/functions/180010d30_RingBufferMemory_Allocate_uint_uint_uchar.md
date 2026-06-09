# RingBufferMemory::Allocate(uint,uint *,uchar * *)

- ea: `0x180010d30`
- end: `0x180010ec6`
- name: `?Allocate@RingBufferMemory@@UEAA?AW4_XBool32@@IPEAIPEAPEAE@Z`
- size: `406`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callees

- `0x180010d30`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010da7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010da7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180010d5d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180010d5d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180010d79`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180010d90`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180010d79`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180010d90`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180010e48`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180010e74`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180010e48`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180010e74`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180010e1e`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180010e1e`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180010e01`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180010e01`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180010ddf`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180010ddf`

## pseudocode

```c
__int64 __fastcall RingBufferMemory::Allocate(__int64 a1, int a2, _DWORD *a3, _QWORD *a4)
{
  const void *v8; // rcx
  const void *v9; // rcx
  void *v10; // rcx
  __int64 dwMaximumSizeLow; // rdi
  HANDLE FileMappingW; // rax
  char *v13; // rax
  char *v14; // rsi
  LPVOID v15; // rax
  _BYTE *v16; // rax
  _BYTE *v17; // rdx
  __int64 result; // rax
  struct _SYSTEM_INFO v19[2]; // [rsp+30h] [rbp-68h] BYREF

  memset(v19, 0, 48);
  GetSystemInfo(v19);
  if ( 2 * a2 < v19[0].dwAllocationGranularity )
    return 0;
  v8 = *(const void **)(a1 + 24);
  if ( v8 )
  {
    UnmapViewOfFile(v8);
    *(_QWORD *)(a1 + 24) = 0;
  }
  v9 = *(const void **)(a1 + 32);
  if ( v9 )
  {
    UnmapViewOfFile(v9);
    *(_QWORD *)(a1 + 32) = 0;
  }
  v10 = *(void **)(a1 + 16);
  if ( v10 )
  {
    CloseHandle(v10);
    *(_QWORD *)(a1 + 16) = 0;
  }
  dwMaximumSizeLow = v19[0].dwAllocationGranularity
                   + a2
                   - 1
                   - (v19[0].dwAllocationGranularity + a2 - 1) % v19[0].dwAllocationGranularity;
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, dwMaximumSizeLow, 0);
  *(_QWORD *)(a1 + 16) = FileMappingW;
  if ( !FileMappingW )
    return 0;
  v13 = (char *)VirtualAlloc(0, (unsigned int)(2 * dwMaximumSizeLow), 0x2000u, 1u);
  v14 = v13;
  if ( !v13 )
    return 0;
  if ( !VirtualFree(v13, 0, 0x8000u) )
    return 0;
  v15 = MapViewOfFileEx(*(HANDLE *)(a1 + 16), 0xF001Fu, 0, 0, (unsigned int)dwMaximumSizeLow, v14);
  *(_QWORD *)(a1 + 24) = v15;
  if ( !v15 )
    return 0;
  v16 = MapViewOfFileEx(*(HANDLE *)(a1 + 16), 0xF001Fu, 0, 0, (unsigned int)dwMaximumSizeLow, &v14[dwMaximumSizeLow]);
  *(_QWORD *)(a1 + 32) = v16;
  if ( !v16 )
    return 0;
  v17 = *(_BYTE **)(a1 + 24);
  if ( v16 != &v17[dwMaximumSizeLow] )
    return 0;
  *v17 = 88;
  **(_BYTE **)(a1 + 32) = 89;
  if ( **(_BYTE **)(a1 + 24) != 89 )
    return 0;
  *(_DWORD *)(a1 + 12) = dwMaximumSizeLow;
  result = 1;
  *a3 = dwMaximumSizeLow;
  *a4 = *(_QWORD *)(a1 + 24);
  return result;
}

```

## disassembly

```asm
0x180010d30  mov     rax, rsp
0x180010d33  push    rbx
0x180010d34  push    rbp
0x180010d35  push    rsi
0x180010d36  push    rdi
0x180010d37  push    r14
0x180010d39  push    r15
0x180010d3b  sub     rsp, 68h
0x180010d3f  xorps   xmm0, xmm0
0x180010d42  mov     rbx, rcx
0x180010d45  lea     rcx, [rax-68h]; lpSystemInfo
0x180010d49  mov     r15, r9
0x180010d4c  movups  xmmword ptr [rax-68h], xmm0
0x180010d50  mov     rbp, r8
0x180010d53  mov     edi, edx
0x180010d55  movups  xmmword ptr [rax-58h], xmm0
0x180010d59  movups  xmmword ptr [rax-48h], xmm0
0x180010d5d  call    cs:__imp_GetSystemInfo
0x180010d63  lea     eax, [rdi+rdi]
0x180010d66  cmp     eax, [rsp+98h+var_40]
0x180010d6a  jb      loc_180010EB7
0x180010d70  mov     rcx, [rbx+18h]; lpBaseAddress
0x180010d74  test    rcx, rcx
0x180010d77  jz      short loc_180010D87
0x180010d79  call    cs:__imp_UnmapViewOfFile
0x180010d7f  mov     qword ptr [rbx+18h], 0
0x180010d87  mov     rcx, [rbx+20h]; lpBaseAddress
0x180010d8b  test    rcx, rcx
0x180010d8e  jz      short loc_180010D9E
0x180010d90  call    cs:__imp_UnmapViewOfFile
0x180010d96  mov     qword ptr [rbx+20h], 0
0x180010d9e  mov     rcx, [rbx+10h]; hObject
0x180010da2  test    rcx, rcx
0x180010da5  jz      short loc_180010DB5
0x180010da7  call    cs:__imp_CloseHandle
0x180010dad  mov     qword ptr [rbx+10h], 0
0x180010db5  xor     edx, edx
0x180010db7  mov     [rsp+98h+lpName], 0; lpName
0x180010dc0  dec     edi
0x180010dc2  xor     r9d, r9d; dwMaximumSizeHigh
0x180010dc5  add     edi, [rsp+98h+var_40]
0x180010dc9  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180010dcd  mov     eax, edi
0x180010dcf  div     [rsp+98h+var_40]
0x180010dd3  lea     r8d, [r9+4]; flProtect
0x180010dd7  sub     edi, edx
0x180010dd9  xor     edx, edx; lpFileMappingAttributes
0x180010ddb  mov     [rsp+98h+dwMaximumSizeLow], edi; dwMaximumSizeLow
0x180010ddf  call    cs:__imp_CreateFileMappingW
0x180010de5  mov     [rbx+10h], rax
0x180010de9  test    rax, rax
0x180010dec  jz      loc_180010EB7
0x180010df2  xor     ecx, ecx; lpAddress
0x180010df4  lea     edx, [rdi+rdi]; dwSize
0x180010df7  mov     r8d, 2000h; flAllocationType
0x180010dfd  lea     r9d, [rcx+1]; flProtect
0x180010e01  call    cs:__imp_VirtualAlloc
0x180010e07  mov     rsi, rax
0x180010e0a  test    rax, rax
0x180010e0d  jz      loc_180010EB7
0x180010e13  xor     edx, edx; dwSize
0x180010e15  mov     r8d, 8000h; dwFreeType
0x180010e1b  mov     rcx, rax; lpAddress
0x180010e1e  call    cs:__imp_VirtualFree
0x180010e24  test    eax, eax
0x180010e26  jz      loc_180010EB7
0x180010e2c  mov     rcx, [rbx+10h]; hFileMappingObject
0x180010e30  xor     r9d, r9d; dwFileOffsetLow
0x180010e33  mov     r14d, edi
0x180010e36  xor     r8d, r8d; dwFileOffsetHigh
0x180010e39  mov     [rsp+98h+lpName], rsi; lpBaseAddress
0x180010e3e  mov     edx, 0F001Fh; dwDesiredAccess
0x180010e43  mov     qword ptr [rsp+98h+dwMaximumSizeLow], r14; dwNumberOfBytesToMap
0x180010e48  call    cs:__imp_MapViewOfFileEx
0x180010e4e  mov     [rbx+18h], rax
0x180010e52  test    rax, rax
0x180010e55  jz      short loc_180010EB7
0x180010e57  mov     rcx, [rbx+10h]; hFileMappingObject
0x180010e5b  lea     rax, [rdi+rsi]
0x180010e5f  mov     [rsp+98h+lpName], rax; lpBaseAddress
0x180010e64  xor     r9d, r9d; dwFileOffsetLow
0x180010e67  xor     r8d, r8d; dwFileOffsetHigh
0x180010e6a  mov     qword ptr [rsp+98h+dwMaximumSizeLow], r14; dwNumberOfBytesToMap
0x180010e6f  mov     edx, 0F001Fh; dwDesiredAccess
0x180010e74  call    cs:__imp_MapViewOfFileEx
0x180010e7a  mov     [rbx+20h], rax
0x180010e7e  test    rax, rax
0x180010e81  jz      short loc_180010EB7
0x180010e83  mov     rdx, [rbx+18h]
0x180010e87  lea     rcx, [rdi+rdx]
0x180010e8b  cmp     rax, rcx
0x180010e8e  jnz     short loc_180010EB7
0x180010e90  mov     byte ptr [rdx], 58h ; 'X'
0x180010e93  mov     rcx, [rbx+20h]
0x180010e97  mov     byte ptr [rcx], 59h ; 'Y'
0x180010e9a  mov     rcx, [rbx+18h]
0x180010e9e  cmp     byte ptr [rcx], 59h ; 'Y'
0x180010ea1  jnz     short loc_180010EB7
0x180010ea3  mov     [rbx+0Ch], edi
0x180010ea6  mov     eax, 1
0x180010eab  mov     [rbp+0], edi
0x180010eae  mov     rcx, [rbx+18h]
0x180010eb2  mov     [r15], rcx
0x180010eb5  jmp     short loc_180010EB9
0x180010eb7  xor     eax, eax
0x180010eb9  add     rsp, 68h
0x180010ebd  pop     r15
0x180010ebf  pop     r14
0x180010ec1  pop     rdi
0x180010ec2  pop     rsi
0x180010ec3  pop     rbp
0x180010ec4  pop     rbx
0x180010ec5  retn
```
