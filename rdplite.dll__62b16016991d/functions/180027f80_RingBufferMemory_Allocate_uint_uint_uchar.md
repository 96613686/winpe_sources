# RingBufferMemory::Allocate(uint,uint *,uchar * *)

- ea: `0x180027f80`
- end: `0x1800280d9`
- name: `?Allocate@RingBufferMemory@@UEAA?AW4_XBool32@@IPEAIPEAPEAE@Z`
- size: `345`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x180027f80`
- `0x180028124`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180027fad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180027fad`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180027ff2`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180027ff2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18002805b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180028087`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18002805b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180028087`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180028014`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180028014`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180028031`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180028031`

## pseudocode

```c
__int64 __fastcall RingBufferMemory::Allocate(__int64 a1, int a2, _DWORD *a3, _QWORD *a4)
{
  __int64 dwMaximumSizeLow; // rdi
  HANDLE FileMappingW; // rax
  char *v10; // rax
  char *v11; // rsi
  LPVOID v12; // rax
  _BYTE *v13; // rax
  _BYTE *v14; // rdx
  __int64 result; // rax
  struct _SYSTEM_INFO v16[2]; // [rsp+30h] [rbp-68h] BYREF

  memset(v16, 0, 48);
  GetSystemInfo(v16);
  if ( 2 * a2 < v16[0].dwAllocationGranularity )
    return 0;
  RingBufferMemory::Free((RingBufferMemory *)a1);
  dwMaximumSizeLow = v16[0].dwAllocationGranularity
                   + a2
                   - 1
                   - (v16[0].dwAllocationGranularity + a2 - 1) % v16[0].dwAllocationGranularity;
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, dwMaximumSizeLow, 0);
  *(_QWORD *)(a1 + 16) = FileMappingW;
  if ( !FileMappingW )
    return 0;
  v10 = (char *)VirtualAlloc(0, (unsigned int)(2 * dwMaximumSizeLow), 0x2000u, 1u);
  v11 = v10;
  if ( !v10 )
    return 0;
  if ( !VirtualFree(v10, 0, 0x8000u) )
    return 0;
  v12 = MapViewOfFileEx(*(HANDLE *)(a1 + 16), 0xF001Fu, 0, 0, (unsigned int)dwMaximumSizeLow, v11);
  *(_QWORD *)(a1 + 24) = v12;
  if ( !v12 )
    return 0;
  v13 = MapViewOfFileEx(*(HANDLE *)(a1 + 16), 0xF001Fu, 0, 0, (unsigned int)dwMaximumSizeLow, &v11[dwMaximumSizeLow]);
  *(_QWORD *)(a1 + 32) = v13;
  if ( !v13 )
    return 0;
  v14 = *(_BYTE **)(a1 + 24);
  if ( v13 != &v14[dwMaximumSizeLow] )
    return 0;
  *v14 = 88;
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
0x180027f80  mov     rax, rsp
0x180027f83  push    rbx
0x180027f84  push    rbp
0x180027f85  push    rsi
0x180027f86  push    rdi
0x180027f87  push    r14
0x180027f89  push    r15
0x180027f8b  sub     rsp, 68h
0x180027f8f  xorps   xmm0, xmm0
0x180027f92  mov     rbx, rcx
0x180027f95  lea     rcx, [rax-68h]; lpSystemInfo
0x180027f99  mov     r15, r9
0x180027f9c  movups  xmmword ptr [rax-68h], xmm0
0x180027fa0  mov     rbp, r8
0x180027fa3  mov     edi, edx
0x180027fa5  movups  xmmword ptr [rax-58h], xmm0
0x180027fa9  movups  xmmword ptr [rax-48h], xmm0
0x180027fad  call    cs:__imp_GetSystemInfo
0x180027fb3  lea     eax, [rdi+rdi]
0x180027fb6  cmp     eax, [rsp+98h+var_40]
0x180027fba  jb      loc_1800280CA
0x180027fc0  mov     rcx, rbx; this
0x180027fc3  call    ?Free@RingBufferMemory@@AEAAXXZ; RingBufferMemory::Free(void)
0x180027fc8  xor     edx, edx
0x180027fca  mov     [rsp+98h+lpName], 0; lpName
0x180027fd3  dec     edi
0x180027fd5  xor     r9d, r9d; dwMaximumSizeHigh
0x180027fd8  add     edi, [rsp+98h+var_40]
0x180027fdc  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180027fe0  mov     eax, edi
0x180027fe2  div     [rsp+98h+var_40]
0x180027fe6  lea     r8d, [r9+4]; flProtect
0x180027fea  sub     edi, edx
0x180027fec  xor     edx, edx; lpFileMappingAttributes
0x180027fee  mov     [rsp+98h+dwMaximumSizeLow], edi; dwMaximumSizeLow
0x180027ff2  call    cs:__imp_CreateFileMappingW
0x180027ff8  mov     [rbx+10h], rax
0x180027ffc  test    rax, rax
0x180027fff  jz      loc_1800280CA
0x180028005  xor     ecx, ecx; lpAddress
0x180028007  lea     edx, [rdi+rdi]; dwSize
0x18002800a  mov     r8d, 2000h; flAllocationType
0x180028010  lea     r9d, [rcx+1]; flProtect
0x180028014  call    cs:__imp_VirtualAlloc
0x18002801a  mov     rsi, rax
0x18002801d  test    rax, rax
0x180028020  jz      loc_1800280CA
0x180028026  xor     edx, edx; dwSize
0x180028028  mov     r8d, 8000h; dwFreeType
0x18002802e  mov     rcx, rax; lpAddress
0x180028031  call    cs:__imp_VirtualFree
0x180028037  test    eax, eax
0x180028039  jz      loc_1800280CA
0x18002803f  mov     rcx, [rbx+10h]; hFileMappingObject
0x180028043  xor     r9d, r9d; dwFileOffsetLow
0x180028046  mov     r14d, edi
0x180028049  xor     r8d, r8d; dwFileOffsetHigh
0x18002804c  mov     [rsp+98h+lpName], rsi; lpBaseAddress
0x180028051  mov     edx, 0F001Fh; dwDesiredAccess
0x180028056  mov     qword ptr [rsp+98h+dwMaximumSizeLow], r14; dwNumberOfBytesToMap
0x18002805b  call    cs:__imp_MapViewOfFileEx
0x180028061  mov     [rbx+18h], rax
0x180028065  test    rax, rax
0x180028068  jz      short loc_1800280CA
0x18002806a  mov     rcx, [rbx+10h]; hFileMappingObject
0x18002806e  lea     rax, [rdi+rsi]
0x180028072  mov     [rsp+98h+lpName], rax; lpBaseAddress
0x180028077  xor     r9d, r9d; dwFileOffsetLow
0x18002807a  xor     r8d, r8d; dwFileOffsetHigh
0x18002807d  mov     qword ptr [rsp+98h+dwMaximumSizeLow], r14; dwNumberOfBytesToMap
0x180028082  mov     edx, 0F001Fh; dwDesiredAccess
0x180028087  call    cs:__imp_MapViewOfFileEx
0x18002808d  mov     [rbx+20h], rax
0x180028091  test    rax, rax
0x180028094  jz      short loc_1800280CA
0x180028096  mov     rdx, [rbx+18h]
0x18002809a  lea     rcx, [rdx+rdi]
0x18002809e  cmp     rax, rcx
0x1800280a1  jnz     short loc_1800280CA
0x1800280a3  mov     byte ptr [rdx], 58h ; 'X'
0x1800280a6  mov     rcx, [rbx+20h]
0x1800280aa  mov     byte ptr [rcx], 59h ; 'Y'
0x1800280ad  mov     rcx, [rbx+18h]
0x1800280b1  cmp     byte ptr [rcx], 59h ; 'Y'
0x1800280b4  jnz     short loc_1800280CA
0x1800280b6  mov     [rbx+0Ch], edi
0x1800280b9  mov     eax, 1
0x1800280be  mov     [rbp+0], edi
0x1800280c1  mov     rcx, [rbx+18h]
0x1800280c5  mov     [r15], rcx
0x1800280c8  jmp     short loc_1800280CC
0x1800280ca  xor     eax, eax
0x1800280cc  add     rsp, 68h
0x1800280d0  pop     r15
0x1800280d2  pop     r14
0x1800280d4  pop     rdi
0x1800280d5  pop     rsi
0x1800280d6  pop     rbp
0x1800280d7  pop     rbx
0x1800280d8  retn
```
