# CreateFileLockBytesOnHFILE(int,int,ulong,ulong,void * *,ILockBytes * *)

- ea: `0x180031f58`
- end: `0x180032106`
- name: `?CreateFileLockBytesOnHFILE@@YAJHHKKPEAPEAXPEAPEAUILockBytes@@@Z`
- size: `430`
- prototype: `int(int, int, unsigned int, unsigned int, void **, struct ILockBytes **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180012b70`
- `0x180031e20`

## callees

- `0x18000f900`
- `0x180031f58`
- `0x18003210c`
- `0x18005b084`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032043`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800320fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032043`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800320fe`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180031f99`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180031f99`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18003203a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18003203a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180031fc7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180031fc7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180032013`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180032013`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800320d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800320d4`

## pseudocode

```c
__int64 __fastcall CreateFileLockBytesOnHFILE(int a1, int a2, DWORD a3, int a4, void **a5, struct ILockBytes **a6)
{
  void *v6; // rbp
  DWORD FileSize; // esi
  HANDLE FileMappingW; // rbx
  DWORD dwAllocationGranularity; // ecx
  DWORD v12; // r15d
  __int64 v13; // r12
  SIZE_T v14; // rax
  char *v15; // r14
  FileLockBytesMemory *v16; // rax
  __int64 v18; // rdx
  void **v19; // rax
  struct ILockBytes **v20; // rax
  FileLockBytes *v21; // rax
  __int64 v22; // rcx
  _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-58h] BYREF
  DWORD v24; // [rsp+98h] [rbp+10h] BYREF

  v6 = (void *)a1;
  if ( a2 )
    goto LABEL_14;
  v24 = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  FileSize = GetFileSize((HANDLE)a1, &v24);
  if ( FileSize == -1 )
  {
    if ( GetLastError() )
      goto LABEL_14;
  }
  FileMappingW = CreateFileMappingW(v6, 0, 2u, 0, 0, 0);
  if ( !FileMappingW )
    goto LABEL_14;
  dwAllocationGranularity = dword_1800C341C;
  if ( !dword_1800C341C )
  {
    GetSystemInfo(&SystemInfo);
    dwAllocationGranularity = SystemInfo.dwAllocationGranularity;
    dword_1800C341C = SystemInfo.dwAllocationGranularity;
  }
  v12 = a3 - a3 % dwAllocationGranularity;
  v13 = a3 % dwAllocationGranularity;
  v14 = a3 % dwAllocationGranularity + a4;
  if ( !a4 )
    v14 = 0;
  v15 = (char *)MapViewOfFile(FileMappingW, 4u, 0, a3 - a3 % dwAllocationGranularity, v14);
  if ( !v15 )
  {
    a3 = v12;
    CloseHandle(FileMappingW);
LABEL_14:
    *a5 = 0;
    v21 = (FileLockBytes *)MemAlloc(24);
    if ( !v21 )
      return 2147942414LL;
    FileLockBytes::FileLockBytes(v21);
    *(_DWORD *)(v22 + 16) = a3;
    goto LABEL_13;
  }
  v16 = (FileLockBytesMemory *)MemAlloc(48);
  if ( !v16 )
  {
    UnmapViewOfFile(v15);
    CloseHandle(FileMappingW);
    return 2147942414LL;
  }
  FileLockBytesMemory::FileLockBytesMemory(v16);
  v19 = a5;
  *(_QWORD *)(v18 + 16) = FileMappingW;
  *(_DWORD *)(v18 + 40) = FileSize - a3;
  *(_QWORD *)(v18 + 24) = v15;
  *v19 = &v15[v13];
  *(_QWORD *)(v18 + 32) = &v15[v13];
LABEL_13:
  v20 = a6;
  *(_DWORD *)(v18 + 12) = (_DWORD)v6;
  *v20 = (struct ILockBytes *)v18;
  return 0;
}

```

## disassembly

```asm
0x180031f58  mov     rax, rsp
0x180031f5b  mov     [rax+8], rbx
0x180031f5f  mov     [rax+18h], rbp
0x180031f63  push    rsi
0x180031f64  push    rdi
0x180031f65  push    r12
0x180031f67  push    r14
0x180031f69  push    r15
0x180031f6b  sub     rsp, 60h
0x180031f6f  movsxd  rbp, ecx
0x180031f72  mov     r14d, r9d
0x180031f75  mov     edi, r8d
0x180031f78  test    edx, edx
0x180031f7a  jnz     loc_1800320A1
0x180031f80  xorps   xmm0, xmm0
0x180031f83  mov     [rax+10h], edx
0x180031f86  lea     rdx, [rax+10h]; lpFileSizeHigh
0x180031f8a  mov     rcx, rbp; hFile
0x180031f8d  movups  xmmword ptr [rax-58h], xmm0
0x180031f91  movups  xmmword ptr [rax-48h], xmm0
0x180031f95  movups  xmmword ptr [rax-38h], xmm0
0x180031f99  call    cs:__imp_GetFileSize
0x180031f9f  mov     esi, eax
0x180031fa1  cmp     eax, 0FFFFFFFFh
0x180031fa4  jz      loc_1800320E9
0x180031faa  xor     r9d, r9d; dwMaximumSizeHigh
0x180031fad  mov     [rsp+88h+lpName], 0; lpName
0x180031fb6  xor     edx, edx; lpFileMappingAttributes
0x180031fb8  mov     [rsp+88h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x180031fc0  mov     rcx, rbp; hFile
0x180031fc3  lea     r8d, [r9+2]; flProtect
0x180031fc7  call    cs:__imp_CreateFileMappingW
0x180031fcd  mov     rbx, rax
0x180031fd0  test    rax, rax
0x180031fd3  jz      loc_1800320A1
0x180031fd9  mov     ecx, cs:dword_1800C341C
0x180031fdf  test    ecx, ecx
0x180031fe1  jz      loc_1800320CF
0x180031fe7  xor     edx, edx
0x180031fe9  mov     eax, edi
0x180031feb  div     ecx
0x180031fed  mov     r15d, edi
0x180031ff0  mov     rcx, rbx; hFileMappingObject
0x180031ff3  sub     r15d, edx
0x180031ff6  mov     r12d, edx
0x180031ff9  test    r14d, r14d
0x180031ffc  mov     r9d, r15d; dwFileOffsetLow
0x180031fff  lea     eax, [rdx+r14]
0x180032003  cmovz   eax, r14d
0x180032007  xor     r8d, r8d; dwFileOffsetHigh
0x18003200a  mov     qword ptr [rsp+88h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x18003200f  lea     edx, [r8+4]; dwDesiredAccess
0x180032013  call    cs:__imp_MapViewOfFile
0x180032019  mov     r14, rax
0x18003201c  test    rax, rax
0x18003201f  jz      loc_1800320F8
0x180032025  mov     ecx, 30h ; '0'
0x18003202a  call    MemAlloc
0x18003202f  mov     rdx, rax
0x180032032  test    rax, rax
0x180032035  jnz     short loc_180032067
0x180032037  mov     rcx, r14; lpBaseAddress
0x18003203a  call    cs:__imp_UnmapViewOfFile
0x180032040  mov     rcx, rbx; hObject
0x180032043  call    cs:__imp_CloseHandle
0x180032049  mov     eax, 8007000Eh
0x18003204e  lea     r11, [rsp+88h+var_28]
0x180032053  mov     rbx, [r11+30h]
0x180032057  mov     rbp, [r11+40h]
0x18003205b  mov     rsp, r11
0x18003205e  pop     r15
0x180032060  pop     r14
0x180032062  pop     r12
0x180032064  pop     rdi
0x180032065  pop     rsi
0x180032066  retn
0x180032067  mov     rcx, rdx; this
0x18003206a  call    ??0FileLockBytesMemory@@IEAA@XZ; FileLockBytesMemory::FileLockBytesMemory(void)
0x18003206f  mov     rax, [rsp+88h+arg_20]
0x180032077  lea     rcx, [r14+r12]
0x18003207b  sub     esi, edi
0x18003207d  mov     [rdx+10h], rbx
0x180032081  mov     [rdx+28h], esi
0x180032084  mov     [rdx+18h], r14
0x180032088  mov     [rax], rcx
0x18003208b  mov     [rdx+20h], rcx
0x18003208f  mov     rax, [rsp+88h+arg_28]
0x180032097  mov     [rdx+0Ch], ebp
0x18003209a  mov     [rax], rdx
0x18003209d  xor     eax, eax
0x18003209f  jmp     short loc_18003204E
0x1800320a1  mov     rax, [rsp+88h+arg_20]
0x1800320a9  mov     ecx, 18h
0x1800320ae  mov     qword ptr [rax], 0
0x1800320b5  call    MemAlloc
0x1800320ba  mov     rdx, rax
0x1800320bd  test    rax, rax
0x1800320c0  jz      short loc_180032049
0x1800320c2  mov     rcx, rax; this
0x1800320c5  call    ??0FileLockBytes@@IEAA@XZ; FileLockBytes::FileLockBytes(void)
0x1800320ca  mov     [rcx+10h], edi
0x1800320cd  jmp     short loc_18003208F
0x1800320cf  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x1800320d4  call    cs:__imp_GetSystemInfo
0x1800320da  mov     ecx, [rsp+88h+SystemInfo.dwAllocationGranularity]
0x1800320de  mov     cs:dword_1800C341C, ecx
0x1800320e4  jmp     loc_180031FE7
0x1800320e9  call    cs:__imp_GetLastError
0x1800320ef  test    eax, eax
0x1800320f1  jnz     short loc_1800320A1
0x1800320f3  jmp     loc_180031FAA
0x1800320f8  mov     rcx, rbx; hObject
0x1800320fb  mov     edi, r15d
0x1800320fe  call    cs:__imp_CloseHandle
0x180032104  jmp     short loc_1800320A1
```
