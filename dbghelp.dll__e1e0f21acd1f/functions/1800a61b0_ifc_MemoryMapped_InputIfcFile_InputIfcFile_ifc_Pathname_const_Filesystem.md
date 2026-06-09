# ifc::MemoryMapped::InputIfcFile::InputIfcFile(ifc::Pathname const &,Filesystem *)

- ea: `0x1800a61b0`
- end: `0x1800a63b8`
- name: `??0InputIfcFile@MemoryMapped@ifc@@AEAA@AEBUPathname@2@PEAUFilesystem@@@Z`
- size: `520`
- prototype: `_QWORD(ifc::MemoryMapped::InputIfcFile *__hidden this, const struct Pathname *, struct Filesystem *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800a5ae0`

## callees

- `0x180027440`
- `0x1800472b0`
- `0x1800a6030`
- `0x1800a61b0`
- `0x1800a6590`
- `0x1800a6620`
- `0x180169430`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800a6201`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800a6201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6234`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a6265`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a6265`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800a6226`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800a6226`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a6345`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a6345`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
ifc::MemoryMapped::InputIfcFile *__fastcall ifc::MemoryMapped::InputIfcFile::InputIfcFile(
        union _LARGE_INTEGER *this,
        const struct Pathname *a2,
        struct Filesystem *a3)
{
  HANDLE v5; // rbx
  union _LARGE_INTEGER v6; // rax
  HANDLE FileMappingW; // rdi
  char *QuadPart; // rcx
  LPVOID v9; // rax
  char *v10; // rdi
  size_t v11; // rbx
  union _LARGE_INTEGER v12; // rax
  char *v13; // rdx
  union _LARGE_INTEGER FileSize; // [rsp+30h] [rbp-58h] BYREF
  HANDLE hFile[2]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+48h] [rbp-40h] BYREF

  hFile[1] = (HANDLE)-2LL;
  ifc::MemoryMapped::_anonymous_namespace_::open_file_for_readonly_mapping(hFile, a2, a3);
  v5 = hFile[0];
  if ( hFile[0] == (HANDLE)-1LL )
  {
    v6.QuadPart = 0;
    FileMappingW = 0;
  }
  else
  {
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx(hFile[0], &FileSize) )
    {
      ifc::InaccessibleFileError::InaccessibleFileError((ifc::InaccessibleFileError *)pExceptionObject, a2);
      throw (ifc::ContentSizeError *)pExceptionObject;
    }
    FileMappingW = CreateFileMappingW(v5, 0, 2u, 0, 0, 0);
    if ( !FileMappingW && GetLastError() != 1006 )
    {
      ifc::InaccessibleFileError::InaccessibleFileError((ifc::InaccessibleFileError *)pExceptionObject, a2);
      throw (ifc::FileProjectionError *)pExceptionObject;
    }
    v6 = FileSize;
  }
  this->QuadPart = (LONGLONG)FileMappingW;
  this[1] = v6;
  if ( v5 != (HANDLE)-1LL )
    CloseHandle(v5);
  QuadPart = (char *)this->QuadPart;
  if ( this->QuadPart )
  {
    v9 = MapViewOfFile(QuadPart, 4u, 0, 0, 0);
    if ( !v9 )
    {
      ifc::InaccessibleFileError::InaccessibleFileError((ifc::InaccessibleFileError *)pExceptionObject, a2);
      throw (ifc::WholeContentReadError *)pExceptionObject;
    }
  }
  else
  {
    v9 = 0;
  }
  this[2].QuadPart = (LONGLONG)v9;
  this[3].QuadPart = (LONGLONG)v9;
  this[4].QuadPart = 0;
  this[5].QuadPart = 0;
  this[6].QuadPart = 0;
  this[7].QuadPart = 0;
  this[8].QuadPart = 0;
  this[9].QuadPart = 0;
  this[10].QuadPart = 0;
  this[11].QuadPart = 0;
  this[12].QuadPart = 0;
  this[13].QuadPart = 0;
  this[14].QuadPart = 0;
  this[15].QuadPart = 0;
  if ( *((_QWORD *)a2 + 1) != *(_QWORD *)a2 )
  {
    std::vector<char8_t>::_Buy_nonzero(&this[13]);
    v10 = (char *)this[13].QuadPart;
    v11 = *((_QWORD *)a2 + 1) - *(_QWORD *)a2;
    memmove_0(v10, *(const void **)a2, v11);
    this[14].QuadPart = (LONGLONG)&v10[v11];
  }
  v12 = this[1];
  if ( v12.QuadPart == -1
    || (QuadPart = (char *)this[2].QuadPart) == 0 && v12.QuadPart
    || (this[4] = v12, this[5].QuadPart = (LONGLONG)QuadPart, v13 = &QuadPart[this[4].QuadPart], QuadPart > v13) )
  {
    gsl::details::terminate((gsl::details *)QuadPart);
  }
  this[6].QuadPart = (LONGLONG)QuadPart;
  this[7].QuadPart = (LONGLONG)v13;
  this[8].QuadPart = (LONGLONG)QuadPart;
  return (ifc::MemoryMapped::InputIfcFile *)this;
}

```

## disassembly

```asm
0x1800a61b0  mov     rax, rsp
0x1800a61b3  mov     [rax+8], rcx
0x1800a61b7  push    rbp
0x1800a61b8  push    rsi
0x1800a61b9  push    rdi
0x1800a61ba  push    r14
0x1800a61bc  push    r15
0x1800a61be  sub     rsp, 60h
0x1800a61c2  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800a61ca  mov     [rax+10h], rbx
0x1800a61ce  mov     r14, rdx
0x1800a61d1  mov     rsi, rcx
0x1800a61d4  xor     ebp, ebp
0x1800a61d6  mov     [rax+20h], ebp
0x1800a61d9  lea     rcx, [rax-50h]
0x1800a61dd  call    ifc__MemoryMapped___anonymous_namespace___open_file_for_readonly_mapping
0x1800a61e2  nop
0x1800a61e3  mov     rbx, [rsp+88h+hFile]
0x1800a61e8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a61ec  jnz     short loc_1800A61F4
0x1800a61ee  mov     eax, ebp
0x1800a61f0  mov     edi, ebp
0x1800a61f2  jmp     short loc_1800A624A
0x1800a61f4  mov     qword ptr [rsp+88h+FileSize], rbp
0x1800a61f9  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x1800a61fe  mov     rcx, rbx; hFile
0x1800a6201  call    cs:__imp_GetFileSizeEx
0x1800a6207  test    eax, eax
0x1800a6209  jz      loc_1800A637A
0x1800a620f  mov     [rsp+88h+lpName], rbp; lpName
0x1800a6214  mov     [rsp+88h+dwMaximumSizeLow], ebp; dwMaximumSizeLow
0x1800a6218  xor     r9d, r9d; dwMaximumSizeHigh
0x1800a621b  xor     edx, edx; lpFileMappingAttributes
0x1800a621d  mov     r8d, 2; flProtect
0x1800a6223  mov     rcx, rbx; hFile
0x1800a6226  call    cs:__imp_CreateFileMappingW
0x1800a622c  mov     rdi, rax
0x1800a622f  test    rax, rax
0x1800a6232  jnz     short loc_1800A6245
0x1800a6234  call    cs:__imp_GetLastError
0x1800a623a  cmp     eax, 3EEh
0x1800a623f  jnz     loc_1800A6399
0x1800a6245  mov     rax, qword ptr [rsp+88h+FileSize]
0x1800a624a  mov     [rsi], rdi
0x1800a624d  mov     [rsi+8], rax
0x1800a6251  mov     [rsp+88h+arg_18], 1
0x1800a625c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a6260  jz      short loc_1800A626C
0x1800a6262  mov     rcx, rbx; hObject
0x1800a6265  call    cs:__imp_CloseHandle
0x1800a626b  nop
0x1800a626c  mov     rcx, [rsi]; hFileMappingObject
0x1800a626f  test    rcx, rcx
0x1800a6272  jnz     loc_1800A6335
0x1800a6278  mov     rax, rbp
0x1800a627b  mov     [rsi+10h], rax
0x1800a627f  mov     [rsi+18h], rax
0x1800a6283  mov     [rsi+20h], rbp
0x1800a6287  mov     [rsi+28h], rbp
0x1800a628b  mov     [rsi+30h], rbp
0x1800a628f  mov     [rsi+38h], rbp
0x1800a6293  mov     [rsi+40h], rbp
0x1800a6297  mov     [rsi+48h], rbp
0x1800a629b  mov     [rsi+50h], rbp
0x1800a629f  mov     [rsi+58h], rbp
0x1800a62a3  mov     [rsi+60h], rbp
0x1800a62a7  mov     [rsi+68h], rbp
0x1800a62ab  mov     [rsi+70h], rbp
0x1800a62af  mov     [rsi+78h], rbp
0x1800a62b3  mov     rdx, [r14+8]
0x1800a62b7  sub     rdx, [r14]
0x1800a62ba  jz      short loc_1800A62E6
0x1800a62bc  lea     rcx, [rsi+68h]
0x1800a62c0  call    ?_Buy_nonzero@?$vector@_QV?$allocator@_Q@std@@@std@@AEAAX_K@Z; std::vector<char8_t>::_Buy_nonzero(unsigned __int64)
0x1800a62c5  mov     rdi, [rsi+68h]
0x1800a62c9  mov     rdx, [r14]; Src
0x1800a62cc  mov     rbx, [r14+8]
0x1800a62d0  sub     rbx, rdx
0x1800a62d3  mov     r8, rbx; Size
0x1800a62d6  mov     rcx, rdi; void *
0x1800a62d9  call    memmove_0
0x1800a62de  lea     rax, [rbx+rdi]
0x1800a62e2  mov     [rsi+70h], rax
0x1800a62e6  mov     rax, [rsi+8]
0x1800a62ea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a62ee  jz      short loc_1800A6355
0x1800a62f0  mov     rcx, [rsi+10h]
0x1800a62f4  test    rcx, rcx
0x1800a62f7  jnz     short loc_1800A62FE
0x1800a62f9  test    rax, rax
0x1800a62fc  jnz     short loc_1800A6355
0x1800a62fe  mov     [rsi+20h], rax
0x1800a6302  mov     [rsi+28h], rcx
0x1800a6306  mov     rdx, [rsi+20h]
0x1800a630a  add     rdx, rcx
0x1800a630d  cmp     rcx, rdx
0x1800a6310  ja      short loc_1800A6355
0x1800a6312  mov     [rsi+30h], rcx
0x1800a6316  mov     [rsi+38h], rdx
0x1800a631a  mov     [rsi+40h], rcx
0x1800a631e  mov     rax, rsi
0x1800a6321  mov     rbx, [rsp+88h+arg_8]
0x1800a6329  add     rsp, 60h
0x1800a632d  pop     r15
0x1800a632f  pop     r14
0x1800a6331  pop     rdi
0x1800a6332  pop     rsi
0x1800a6333  pop     rbp
0x1800a6334  retn
0x1800a6335  mov     qword ptr [rsp+88h+dwMaximumSizeLow], rbp; dwNumberOfBytesToMap
0x1800a633a  xor     r9d, r9d; dwFileOffsetLow
0x1800a633d  xor     r8d, r8d; dwFileOffsetHigh
0x1800a6340  mov     edx, 4; dwDesiredAccess
0x1800a6345  call    cs:__imp_MapViewOfFile
0x1800a634b  test    rax, rax
0x1800a634e  jz      short loc_1800A635B
0x1800a6350  jmp     loc_1800A627B
0x1800a6355  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x1800a635b  mov     rdx, r14; struct ifc::InaccessibleFileError *
0x1800a635e  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800a6363  call    ??0InaccessibleFileError@ifc@@QEAA@AEBU01@@Z; ifc::InaccessibleFileError::InaccessibleFileError(ifc::InaccessibleFileError const &)
0x1800a6368  lea     rdx, _TI1?AUWholeContentReadError@ifc@@; pThrowInfo
0x1800a636f  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800a6374  call    _CxxThrowException_0
0x1800a637a  mov     rdx, r14; struct ifc::InaccessibleFileError *
0x1800a637d  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800a6382  call    ??0InaccessibleFileError@ifc@@QEAA@AEBU01@@Z; ifc::InaccessibleFileError::InaccessibleFileError(ifc::InaccessibleFileError const &)
0x1800a6387  lea     rdx, _TI1?AUContentSizeError@ifc@@; pThrowInfo
0x1800a638e  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800a6393  call    _CxxThrowException_0
0x1800a6399  mov     rdx, r14; struct ifc::InaccessibleFileError *
0x1800a639c  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800a63a1  call    ??0InaccessibleFileError@ifc@@QEAA@AEBU01@@Z; ifc::InaccessibleFileError::InaccessibleFileError(ifc::InaccessibleFileError const &)
0x1800a63a6  lea     rdx, _TI1?AUFileProjectionError@ifc@@; pThrowInfo
0x1800a63ad  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800a63b2  call    _CxxThrowException_0
```
