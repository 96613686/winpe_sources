# ATL::CAtlFileMappingBase::MapFile(void *,unsigned __int64,unsigned __int64,ulong,ulong)

- ea: `0x18001f080`
- end: `0x18001f14c`
- name: `?MapFile@CAtlFileMappingBase@ATL@@QEAAJPEAX_K1KK@Z`
- size: `204`
- prototype: `int(ATL::CAtlFileMappingBase *__hidden this, void *, unsigned __int64, unsigned __int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001f888`

## callees

- `0x180009994`
- `0x18001f080`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f12d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f12d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001f0a5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001f0a5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001f0ce`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001f0ce`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18001f114`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18001f114`

## pseudocode

```c
int __fastcall ATL::CAtlFileMappingBase::MapFile(ATL::CAtlFileMappingBase *this, void *a2)
{
  HANDLE FileMappingW; // rax
  void *v5; // rcx
  int result; // eax
  SIZE_T v7; // rax
  LPVOID v8; // rax
  signed int Error; // ebx
  SIZE_T dwNumberOfBytesToMap; // [rsp+58h] [rbp+20h] BYREF

  HIDWORD(dwNumberOfBytesToMap) = 0;
  LODWORD(dwNumberOfBytesToMap) = GetFileSize(a2, (LPDWORD)&dwNumberOfBytesToMap + 1);
  FileMappingW = CreateFileMappingW(a2, 0, 2u, HIDWORD(dwNumberOfBytesToMap), dwNumberOfBytesToMap, 0);
  *((_QWORD *)this + 2) = FileMappingW;
  v5 = FileMappingW;
  if ( !FileMappingW )
    return ATL::AtlHresultFromLastError();
  v7 = dwNumberOfBytesToMap;
  *((_QWORD *)this + 1) = dwNumberOfBytesToMap;
  *((_DWORD *)this + 8) = 4;
  *((_QWORD *)this + 3) = 0;
  v8 = MapViewOfFileEx(v5, 4u, 0, 0, v7, 0);
  *(_QWORD *)this = v8;
  if ( v8 )
    return 0;
  Error = ATL::AtlHresultFromLastError();
  CloseHandle(*((HANDLE *)this + 2));
  result = Error;
  *((_QWORD *)this + 2) = 0;
  return result;
}

```

## disassembly

```asm
0x18001f080  mov     rax, rsp
0x18001f083  mov     [rax+8], rbx
0x18001f087  mov     [rax+20h], r9
0x18001f08b  push    rdi
0x18001f08c  sub     rsp, 30h
0x18001f090  mov     rbx, rdx
0x18001f093  mov     qword ptr [rax+20h], 0
0x18001f09b  mov     rdi, rcx
0x18001f09e  lea     rdx, [rax+24h]; lpFileSizeHigh
0x18001f0a2  mov     rcx, rbx; hFile
0x18001f0a5  call    cs:__imp_GetFileSize
0x18001f0ab  xor     edx, edx; lpFileMappingAttributes
0x18001f0ad  mov     [rsp+38h+lpName], 0; lpName
0x18001f0b6  mov     dword ptr [rsp+38h+dwNumberOfBytesToMap], eax
0x18001f0ba  mov     rcx, rbx; hFile
0x18001f0bd  mov     r9, [rsp+38h+dwNumberOfBytesToMap]
0x18001f0c2  shr     r9, 20h; dwMaximumSizeHigh
0x18001f0c6  lea     r8d, [rdx+2]; flProtect
0x18001f0ca  mov     [rsp+38h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x18001f0ce  call    cs:__imp_CreateFileMappingW
0x18001f0d4  mov     [rdi+10h], rax
0x18001f0d8  mov     rcx, rax; hFileMappingObject
0x18001f0db  test    rax, rax
0x18001f0de  jnz     short loc_18001F0E7
0x18001f0e0  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001f0e5  jmp     short loc_18001F141
0x18001f0e7  mov     rax, [rsp+38h+dwNumberOfBytesToMap]
0x18001f0ec  mov     edx, 4; dwDesiredAccess
0x18001f0f1  mov     [rdi+8], rax
0x18001f0f5  xor     r9d, r9d; dwFileOffsetLow
0x18001f0f8  mov     [rsp+38h+lpName], 0; lpBaseAddress
0x18001f101  xor     r8d, r8d; dwFileOffsetHigh
0x18001f104  mov     [rdi+20h], edx
0x18001f107  mov     qword ptr [rdi+18h], 0
0x18001f10f  mov     qword ptr [rsp+38h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x18001f114  call    cs:__imp_MapViewOfFileEx
0x18001f11a  mov     [rdi], rax
0x18001f11d  test    rax, rax
0x18001f120  jnz     short loc_18001F13F
0x18001f122  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001f127  mov     rcx, [rdi+10h]; hObject
0x18001f12b  mov     ebx, eax
0x18001f12d  call    cs:__imp_CloseHandle
0x18001f133  mov     eax, ebx
0x18001f135  mov     qword ptr [rdi+10h], 0
0x18001f13d  jmp     short loc_18001F141
0x18001f13f  xor     eax, eax
0x18001f141  mov     rbx, [rsp+38h+arg_0]
0x18001f146  add     rsp, 30h
0x18001f14a  pop     rdi
0x18001f14b  retn
```
