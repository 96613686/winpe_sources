# PortablePDB::MapPortablePDB(wchar_t const *,IStream *,long &)

- ea: `0x18004c770`
- end: `0x18004ca46`
- name: `?MapPortablePDB@PortablePDB@@QEAAHPEB_WPEAUIStream@@AEAJ@Z`
- size: `726`
- prototype: `int(PortablePDB *__hidden this, const wchar_t *, struct IStream *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800333d0`

## callees

- `0x1800274e0`
- `0x18004c770`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18004c854`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18004ca18`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18004c854`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18004ca18`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004c825`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004c825`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18004c959`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18004c959`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004c937`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004c937`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c96b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c9a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c9d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c96b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c9a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c9d9`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18004c9cd`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18004c9cd`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18004c993`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18004c993`

## pseudocode

```c
__int64 __fastcall PortablePDB::MapPortablePDB(PortablePDB *this, const wchar_t *a2, struct IStream *a3, int *a4)
{
  unsigned int (*v8)(void); // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  SIZE_T v14; // r15
  void *v15; // rcx
  HANDLE FileMappingW; // rax
  void *v17; // r12
  LPVOID v18; // r13
  int v19; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+68h] [rbp-A0h]
  wchar_t *FullPath[2]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v22; // [rsp+80h] [rbp-88h]
  __int128 v23; // [rsp+90h] [rbp-78h]
  __int128 v24; // [rsp+A0h] [rbp-68h]
  __int128 v25; // [rsp+B0h] [rbp-58h]

  v20 = -2;
  if ( a3 )
  {
    if ( !a2 )
    {
      *(_DWORD *)this = 1;
      *(_OWORD *)FullPath = 0;
      v22 = 0;
      v23 = 0;
      v24 = 0;
      v25 = 0;
      if ( (*(int (__fastcall **)(struct IStream *, wchar_t **, _QWORD))(*(_QWORD *)a3 + 96LL))(a3, FullPath, 0) >= 0 )
      {
        if ( FullPath[0] )
          _wsplitpath_s(FullPath[0], 0, 0, 0, 0, (wchar_t *)this + 56, 0x104u, 0, 0);
        else
          _o_wcscpy_s((char *)this + 112, 260, L"* Portable PDB *");
        if ( (unsigned int)v22 == (_QWORD)v22 )
        {
          try
          {
            std::vector<unsigned char>::_Resize<std::_Value_init_tag>();
            v8 = *(unsigned int (**)(void))(*(_QWORD *)a3 + 40LL);
          }
          catch ( std::bad_alloc )
          {
            MEMORY[0] = 2;
            return 0;
          }
          if ( !v8()
            && !(*(unsigned int (__fastcall **)(struct IStream *, _QWORD, _QWORD, int *))(*(_QWORD *)a3 + 24LL))(
                  a3,
                  *((_QWORD *)this + 2),
                  *((_DWORD *)this + 6) - (unsigned int)*((_QWORD *)this + 2),
                  &v19) )
          {
            v9 = *((_QWORD *)this + 2);
            v10 = *((_QWORD *)this + 3) - v9;
            if ( v10 == v19 )
            {
              *((_QWORD *)this + 5) = v9;
              *((_QWORD *)this + 6) = v10;
              return 1;
            }
          }
        }
      }
LABEL_19:
      *a4 = 3;
      return 0;
    }
LABEL_14:
    *a4 = 1;
    return 0;
  }
  if ( !a2 )
    goto LABEL_14;
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  *((_QWORD *)this + 1) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    *a4 = 4;
    return 0;
  }
  FileSize = GetFileSize(FileW, 0);
  v14 = FileSize;
  v15 = (void *)*((_QWORD *)this + 1);
  if ( FileSize == -1 )
  {
    CloseHandle(v15);
    goto LABEL_19;
  }
  FileMappingW = CreateFileMappingW(v15, 0, 2u, 0, FileSize, 0);
  v17 = FileMappingW;
  if ( !FileMappingW || (v18 = MapViewOfFileEx(FileMappingW, 4u, 0, 0, v14, 0), CloseHandle(v17), !v18) )
  {
    CloseHandle(*((HANDLE *)this + 1));
    *a4 = 2;
    return 0;
  }
  *((_QWORD *)this + 5) = v18;
  *((_QWORD *)this + 6) = v14;
  _wsplitpath_s(a2, 0, 0, 0, 0, (wchar_t *)this + 56, 0x104u, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x18004c770  mov     r11, rsp
0x18004c773  push    rbx
0x18004c774  push    rsi
0x18004c775  push    rdi
0x18004c776  push    r12
0x18004c778  push    r13
0x18004c77a  push    r14
0x18004c77c  push    r15
0x18004c77e  sub     rsp, 0D0h
0x18004c785  mov     [rsp+108h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18004c78e  mov     rax, cs:__security_cookie
0x18004c795  xor     rax, rsp
0x18004c798  mov     [rsp+108h+var_48], rax
0x18004c7a0  mov     rsi, r9
0x18004c7a3  mov     r15, r8
0x18004c7a6  mov     r14, rdx
0x18004c7a9  mov     rbx, rcx
0x18004c7ac  mov     [rsp+108h+var_B0], r9
0x18004c7b1  test    r8, r8
0x18004c7b4  jz      loc_18004C8FC
0x18004c7ba  test    rdx, rdx
0x18004c7bd  jnz     loc_18004C901
0x18004c7c3  mov     dword ptr [rcx], 1
0x18004c7c9  xorps   xmm0, xmm0
0x18004c7cc  movups  xmmword ptr [rsp+108h+FullPath], xmm0
0x18004c7d1  movups  [rsp+108h+var_88], xmm0
0x18004c7d9  movups  xmmword ptr [r11-78h], xmm0
0x18004c7de  movups  xmmword ptr [r11-68h], xmm0
0x18004c7e3  movups  xmmword ptr [r11-58h], xmm0
0x18004c7e8  mov     rax, [r8]
0x18004c7eb  xor     r8d, r8d
0x18004c7ee  lea     rdx, [rsp+108h+FullPath]
0x18004c7f3  mov     rcx, r15
0x18004c7f6  mov     rax, [rax+60h]
0x18004c7fa  call    cs:__guard_dispatch_icall_fptr
0x18004c800  test    eax, eax
0x18004c802  js      loc_18004C971
0x18004c808  lea     rax, [rbx+70h]
0x18004c80c  mov     rcx, [rsp+108h+FullPath]; FullPath
0x18004c811  test    rcx, rcx
0x18004c814  jnz     short loc_18004C82D
0x18004c816  lea     r8, aPortablePdb; "* Portable PDB *"
0x18004c81d  mov     edx, 104h
0x18004c822  mov     rcx, rax
0x18004c825  call    cs:__imp__o_wcscpy_s
0x18004c82b  jmp     short loc_18004C85A
0x18004c82d  xor     edi, edi
0x18004c82f  mov     [rsp+108h+ExtCount], rdi; ExtCount
0x18004c834  mov     [rsp+108h+Ext], rdi; Ext
0x18004c839  mov     [rsp+108h+FilenameCount], 104h; FilenameCount
0x18004c842  mov     [rsp+108h+Filename], rax; Filename
0x18004c847  mov     [rsp+108h+DirCount], rdi; DirCount
0x18004c84c  xor     r9d, r9d; Dir
0x18004c84f  xor     r8d, r8d; DriveCount
0x18004c852  xor     edx, edx; Drive
0x18004c854  call    cs:__imp__wsplitpath_s
0x18004c85a  mov     rax, qword ptr [rsp+108h+var_88]
0x18004c862  mov     edx, eax
0x18004c864  cmp     rdx, rax
0x18004c867  jnz     loc_18004C971
0x18004c86d  lea     r8, [rsp+108h+var_B8]
0x18004c872  lea     rcx, [rbx+10h]
0x18004c876  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18004c87b  nop
0x18004c87c  mov     [rsp+108h+var_B0], 0
0x18004c885  mov     rax, [r15]
0x18004c888  xor     r9d, r9d
0x18004c88b  xor     r8d, r8d
0x18004c88e  mov     rdx, [rsp+108h+var_B0]
0x18004c893  mov     rcx, r15
0x18004c896  mov     rax, [rax+28h]
0x18004c89a  call    cs:__guard_dispatch_icall_fptr
0x18004c8a0  test    eax, eax
0x18004c8a2  jnz     loc_18004C971
0x18004c8a8  mov     rdx, [rbx+10h]
0x18004c8ac  mov     r8d, [rbx+18h]
0x18004c8b0  sub     r8d, edx
0x18004c8b3  mov     rax, [r15]
0x18004c8b6  lea     r9, [rsp+108h+var_A8]
0x18004c8bb  mov     rcx, r15
0x18004c8be  mov     rax, [rax+18h]
0x18004c8c2  call    cs:__guard_dispatch_icall_fptr
0x18004c8c8  test    eax, eax
0x18004c8ca  jnz     loc_18004C971
0x18004c8d0  mov     rdx, [rbx+10h]
0x18004c8d4  mov     rcx, [rbx+18h]
0x18004c8d8  sub     rcx, rdx
0x18004c8db  mov     eax, [rsp+108h+var_A8]
0x18004c8df  cmp     rcx, rax
0x18004c8e2  jnz     loc_18004C971
0x18004c8e8  mov     [rbx+28h], rdx
0x18004c8ec  mov     [rbx+30h], rcx
0x18004c8f0  jmp     loc_18004CA1E
0x18004c8f5  xor     eax, eax
0x18004c8f7  jmp     loc_18004CA23
0x18004c8fc  test    r14, r14
0x18004c8ff  jnz     short loc_18004C90F
0x18004c901  mov     dword ptr [r9], 1
0x18004c908  xor     eax, eax
0x18004c90a  jmp     loc_18004CA23
0x18004c90f  xor     edi, edi
0x18004c911  mov     [rsp+108h+FilenameCount], rdi; hTemplateFile
0x18004c916  mov     dword ptr [rsp+108h+Filename], 80h; dwFlagsAndAttributes
0x18004c91e  mov     dword ptr [rsp+108h+DirCount], 3; dwCreationDisposition
0x18004c926  xor     r9d, r9d; lpSecurityAttributes
0x18004c929  mov     edx, 80000000h; dwDesiredAccess
0x18004c92e  mov     r8d, 1; dwShareMode
0x18004c934  mov     rcx, r14; lpFileName
0x18004c937  call    cs:__imp_CreateFileW
0x18004c93d  mov     [rbx+8], rax
0x18004c941  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004c945  jnz     short loc_18004C954
0x18004c947  mov     dword ptr [rsi], 4
0x18004c94d  xor     eax, eax
0x18004c94f  jmp     loc_18004CA23
0x18004c954  xor     edx, edx; lpFileSizeHigh
0x18004c956  mov     rcx, rax; hFile
0x18004c959  call    cs:__imp_GetFileSize
0x18004c95f  mov     r15d, eax
0x18004c962  mov     rcx, [rbx+8]; hFile
0x18004c966  cmp     eax, 0FFFFFFFFh
0x18004c969  jnz     short loc_18004C97E
0x18004c96b  call    cs:__imp_CloseHandle
0x18004c971  mov     dword ptr [rsi], 3
0x18004c977  xor     eax, eax
0x18004c979  jmp     loc_18004CA23
0x18004c97e  mov     [rsp+108h+Filename], rdi; lpName
0x18004c983  mov     dword ptr [rsp+108h+DirCount], r15d; dwMaximumSizeLow
0x18004c988  xor     r9d, r9d; dwMaximumSizeHigh
0x18004c98b  xor     edx, edx; lpFileMappingAttributes
0x18004c98d  mov     r8d, 2; flProtect
0x18004c993  call    cs:__imp_CreateFileMappingW
0x18004c999  mov     r12, rax
0x18004c99c  test    rax, rax
0x18004c99f  jnz     short loc_18004C9B5
0x18004c9a1  mov     rcx, [rbx+8]; hObject
0x18004c9a5  call    cs:__imp_CloseHandle
0x18004c9ab  mov     dword ptr [rsi], 2
0x18004c9b1  xor     eax, eax
0x18004c9b3  jmp     short loc_18004CA23
0x18004c9b5  mov     [rsp+108h+Filename], rdi; lpBaseAddress
0x18004c9ba  mov     [rsp+108h+DirCount], r15; dwNumberOfBytesToMap
0x18004c9bf  xor     r9d, r9d; dwFileOffsetLow
0x18004c9c2  xor     r8d, r8d; dwFileOffsetHigh
0x18004c9c5  mov     edx, 4; dwDesiredAccess
0x18004c9ca  mov     rcx, r12; hFileMappingObject
0x18004c9cd  call    cs:__imp_MapViewOfFileEx
0x18004c9d3  mov     r13, rax
0x18004c9d6  mov     rcx, r12; hObject
0x18004c9d9  call    cs:__imp_CloseHandle
0x18004c9df  test    r13, r13
0x18004c9e2  jz      short loc_18004C9A1
0x18004c9e4  mov     [rbx+28h], r13
0x18004c9e8  mov     [rbx+30h], r15
0x18004c9ec  lea     rdx, [rbx+70h]
0x18004c9f0  mov     [rsp+108h+ExtCount], rdi; ExtCount
0x18004c9f5  mov     [rsp+108h+Ext], rdi; Ext
0x18004c9fa  mov     [rsp+108h+FilenameCount], 104h; FilenameCount
0x18004ca03  mov     [rsp+108h+Filename], rdx; Filename
0x18004ca08  mov     [rsp+108h+DirCount], rdi; DirCount
0x18004ca0d  xor     r9d, r9d; Dir
0x18004ca10  xor     r8d, r8d; DriveCount
0x18004ca13  xor     edx, edx; Drive
0x18004ca15  mov     rcx, r14; FullPath
0x18004ca18  call    cs:__imp__wsplitpath_s
0x18004ca1e  mov     eax, 1
0x18004ca23  mov     rcx, [rsp+108h+var_48]
0x18004ca2b  xor     rcx, rsp; StackCookie
0x18004ca2e  call    __security_check_cookie
0x18004ca33  add     rsp, 0D0h
0x18004ca3a  pop     r15
0x18004ca3c  pop     r14
0x18004ca3e  pop     r13
0x18004ca40  pop     r12
0x18004ca42  pop     rdi
0x18004ca43  pop     rsi
0x18004ca44  pop     rbx
0x18004ca45  retn
```
