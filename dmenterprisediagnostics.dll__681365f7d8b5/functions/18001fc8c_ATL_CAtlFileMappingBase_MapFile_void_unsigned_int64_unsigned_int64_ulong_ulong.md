# ATL::CAtlFileMappingBase::MapFile(void *,unsigned __int64,unsigned __int64,ulong,ulong)

- ea: `0x18001fc8c`
- end: `0x18001fd71`
- name: `?MapFile@CAtlFileMappingBase@ATL@@QEAAJPEAX_K1KK@Z`
- size: `229`
- prototype: `int(ATL::CAtlFileMappingBase *__hidden this, void *, unsigned __int64, unsigned __int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180020508`

## callees

- `0x180009e70`
- `0x18001fc8c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fd4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fd4b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001fcb1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001fcb1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001fce0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001fce0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18001fd2c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18001fd2c`

## pseudocode

```c
__int64 __fastcall ATL::CAtlFileMappingBase::MapFile(ATL::CAtlFileMappingBase *this, void *a2)
{
  HANDLE FileMappingW; // rax
  void *v5; // rcx
  __int64 result; // rax
  SIZE_T v7; // rax
  LPVOID v8; // rax
  unsigned int Error; // ebx
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
0x18001fc8c  mov     rax, rsp
0x18001fc8f  mov     [rax+8], rbx
0x18001fc93  mov     [rax+20h], r9
0x18001fc97  push    rdi
0x18001fc98  sub     rsp, 30h
0x18001fc9c  mov     rbx, rdx
0x18001fc9f  mov     qword ptr [rax+20h], 0
0x18001fca7  mov     rdi, rcx
0x18001fcaa  lea     rdx, [rax+24h]; lpFileSizeHigh
0x18001fcae  mov     rcx, rbx; hFile
0x18001fcb1  call    cs:__imp_GetFileSize
0x18001fcb8  nop     dword ptr [rax+rax+00h]
0x18001fcbd  xor     edx, edx; lpFileMappingAttributes
0x18001fcbf  mov     [rsp+38h+lpName], 0; lpName
0x18001fcc8  mov     dword ptr [rsp+38h+dwNumberOfBytesToMap], eax
0x18001fccc  mov     rcx, rbx; hFile
0x18001fccf  mov     r9, [rsp+38h+dwNumberOfBytesToMap]
0x18001fcd4  shr     r9, 20h; dwMaximumSizeHigh
0x18001fcd8  lea     r8d, [rdx+2]; flProtect
0x18001fcdc  mov     [rsp+38h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x18001fce0  call    cs:__imp_CreateFileMappingW
0x18001fce7  nop     dword ptr [rax+rax+00h]
0x18001fcec  mov     [rdi+10h], rax
0x18001fcf0  mov     rcx, rax; hFileMappingObject
0x18001fcf3  test    rax, rax
0x18001fcf6  jnz     short loc_18001FCFF
0x18001fcf8  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001fcfd  jmp     short loc_18001FD65
0x18001fcff  mov     rax, [rsp+38h+dwNumberOfBytesToMap]
0x18001fd04  mov     edx, 4; dwDesiredAccess
0x18001fd09  mov     [rdi+8], rax
0x18001fd0d  xor     r9d, r9d; dwFileOffsetLow
0x18001fd10  mov     [rsp+38h+lpName], 0; lpBaseAddress
0x18001fd19  xor     r8d, r8d; dwFileOffsetHigh
0x18001fd1c  mov     [rdi+20h], edx
0x18001fd1f  mov     qword ptr [rdi+18h], 0
0x18001fd27  mov     qword ptr [rsp+38h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x18001fd2c  call    cs:__imp_MapViewOfFileEx
0x18001fd33  nop     dword ptr [rax+rax+00h]
0x18001fd38  mov     [rdi], rax
0x18001fd3b  test    rax, rax
0x18001fd3e  jnz     short loc_18001FD63
0x18001fd40  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001fd45  mov     rcx, [rdi+10h]; hObject
0x18001fd49  mov     ebx, eax
0x18001fd4b  call    cs:__imp_CloseHandle
0x18001fd52  nop     dword ptr [rax+rax+00h]
0x18001fd57  mov     eax, ebx
0x18001fd59  mov     qword ptr [rdi+10h], 0
0x18001fd61  jmp     short loc_18001FD65
0x18001fd63  xor     eax, eax
0x18001fd65  mov     rbx, [rsp+38h+arg_0]
0x18001fd6a  add     rsp, 30h
0x18001fd6e  pop     rdi
0x18001fd6f  retn
```
