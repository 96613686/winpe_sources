# CGenerateMSI::AddApl(_GUID const &,ushort const *,ulong)

- ea: `0x18002b600`
- end: `0x18002b815`
- name: `?AddApl@CGenerateMSI@@UEAAJAEBU_GUID@@PEBGK@Z`
- size: `533`
- prototype: `int __fastcall(CGenerateMSI *this, IID *rclsid, LPCWSTR lpFileName, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180009ee0`
- `0x18002b600`
- `0x18002dda8`
- `0x18002e708`
- `0x18002e888`
- `0x18002e91c`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b75e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b75e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6fc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b73f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b73f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002b6f2`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002b6f2`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002b753`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002b753`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002b644`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002b644`

## string_xrefs

- `0x18002b776`: `File, Component_, FileName, FileSize, Version, Language, Attributes, Sequence`
- `0x18002b6bd`: `Component_, ExpType`
- `0x18002b6c4`: `Complus`

## pseudocode

```c
int __fastcall CGenerateMSI::AddApl(CGenerateMSI *this, IID *rclsid, LPCWSTR lpFileName, unsigned int a4)
{
  const unsigned __int16 **v4; // rsi
  int result; // eax
  CGenerateMSI *v9; // rcx
  const unsigned __int16 **v10; // rdi
  HANDLE FileW; // rax
  void *v12; // rsi
  DWORD FileSize; // ebp
  unsigned int dwFlagsAndAttributes; // [rsp+28h] [rbp-4B0h]
  DWORD v15; // [rsp+38h] [rbp-4A0h]
  int v16; // [rsp+58h] [rbp-480h]
  LPWSTR FilePart; // [rsp+60h] [rbp-478h] BYREF
  unsigned __int16 v18[264]; // [rsp+70h] [rbp-468h] BYREF
  WCHAR Buffer[264]; // [rsp+280h] [rbp-258h] BYREF

  FilePart = 0;
  v4 = (const unsigned __int16 **)((char *)this + 640);
  result = StringFromCLSID(rclsid, (LPOLESTR *)this + 80);
  if ( result >= 0 )
  {
    result = StringCchPrintfW(v18, 0x104u, L"AppID_%s", *v4);
    if ( result >= 0 )
    {
      v10 = (const unsigned __int16 **)((char *)this + 632);
      result = CGenerateMSI::GenerateIdentifier(v9, (unsigned __int16 **)this + 79, v18);
      if ( result >= 0 )
      {
        result = CGenerateMSI::_InsertComponent(this, *v10, *v4, *((_DWORD *)this + 162));
        if ( result >= 0 )
        {
          dwFlagsAndAttributes = a4;
          result = CGenerateMSI::_InsertRow(
                     this,
                     L"Complus",
                     L"Component_, ExpType",
                     L"'%s', %d",
                     *v10,
                     dwFlagsAndAttributes);
          if ( result >= 0 )
          {
            if ( !GetFullPathNameW(lpFileName, 0x104u, Buffer, &FilePart)
              || (FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0, 0), v12 = FileW, FileW == (HANDLE)-1LL)
              || (FileSize = GetFileSize(FileW, 0), CloseHandle(v12), FileSize == -1) )
            {
              result = GetLastError();
              if ( result > 0 )
                result = (unsigned __int16)result | 0x80070000;
            }
            else
            {
              v16 = *((_DWORD *)this + 20);
              v15 = FileSize;
              result = CGenerateMSI::_InsertRow(
                         this,
                         L"File",
                         L"File, Component_, FileName, FileSize, Version, Language, Attributes, Sequence",
                         L"'%s', '%s', '%s', %ld, '%s', %d, %d, %d",
                         *v10,
                         *v10,
                         FilePart,
                         v15,
                         L"1.1.1.1",
                         0,
                         0,
                         v16);
              if ( result >= 0 )
              {
                result = CGenerateMSI::_GetMakeCab(this, a4);
                if ( result >= 0 )
                  result = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR, const unsigned __int16 *))(**((_QWORD **)this + 77)
                                                                                                + 32LL))(
                             *((_QWORD *)this + 77),
                             lpFileName,
                             *v10);
              }
            }
          }
        }
      }
    }
  }
  ++*((_DWORD *)this + 20);
  return result;
}

```

## disassembly

```asm
0x18002b600  push    rbx
0x18002b602  push    rbp
0x18002b603  push    rsi
0x18002b604  push    rdi
0x18002b605  push    r14
0x18002b607  push    r15
0x18002b609  sub     rsp, 4A8h
0x18002b610  mov     rax, cs:__security_cookie
0x18002b617  xor     rax, rsp
0x18002b61a  mov     [rsp+4D8h+var_48], rax
0x18002b622  mov     rax, rdx
0x18002b625  mov     [rsp+4D8h+FilePart], 0
0x18002b62e  lea     rsi, [rcx+280h]
0x18002b635  mov     rbx, rcx
0x18002b638  mov     rdx, rsi; lplpsz
0x18002b63b  mov     rcx, rax; rclsid
0x18002b63e  mov     r15d, r9d
0x18002b641  mov     r14, r8
0x18002b644  call    cs:__imp_StringFromCLSID
0x18002b64a  test    eax, eax
0x18002b64c  js      loc_18002B7F2
0x18002b652  mov     r9, [rsi]
0x18002b655  lea     r8, aAppidS_0; "AppID_%s"
0x18002b65c  mov     ebp, 104h
0x18002b661  lea     rcx, [rsp+4D8h+var_468]; unsigned __int16 *
0x18002b666  mov     edx, ebp; unsigned __int64
0x18002b668  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002b66d  test    eax, eax
0x18002b66f  js      loc_18002B7F2
0x18002b675  lea     rdi, [rbx+278h]
0x18002b67c  mov     rdx, rdi; unsigned __int16 **
0x18002b67f  lea     r8, [rsp+4D8h+var_468]; unsigned __int16 *
0x18002b684  call    ?GenerateIdentifier@CGenerateMSI@@AEAAJPEAPEAGPEBG@Z; CGenerateMSI::GenerateIdentifier(ushort * *,ushort const *)
0x18002b689  test    eax, eax
0x18002b68b  js      loc_18002B7F2
0x18002b691  mov     r9d, [rbx+288h]; unsigned int
0x18002b698  mov     rcx, rbx; this
0x18002b69b  mov     r8, [rsi]; unsigned __int16 *
0x18002b69e  mov     rdx, [rdi]; unsigned __int16 *
0x18002b6a1  call    ?_InsertComponent@CGenerateMSI@@QEAAJPEBG0K@Z; CGenerateMSI::_InsertComponent(ushort const *,ushort const *,ulong)
0x18002b6a6  test    eax, eax
0x18002b6a8  js      loc_18002B7F2
0x18002b6ae  mov     rax, [rdi]
0x18002b6b1  lea     r9, aSD; "'%s', %d"
0x18002b6b8  mov     [rsp+4D8h+dwFlagsAndAttributes], r15d
0x18002b6bd  lea     r8, aComponentExpty; "Component_, ExpType"
0x18002b6c4  lea     rdx, aComplus_0; "Complus"
0x18002b6cb  mov     qword ptr [rsp+4D8h+dwCreationDisposition], rax
0x18002b6d0  mov     rcx, rbx; this
0x18002b6d3  call    ?_InsertRow@CGenerateMSI@@QEAAJPEBG00ZZ; CGenerateMSI::_InsertRow(ushort const *,ushort const *,ushort const *,...)
0x18002b6d8  test    eax, eax
0x18002b6da  js      loc_18002B7F2
0x18002b6e0  lea     r9, [rsp+4D8h+FilePart]; lpFilePart
0x18002b6e5  mov     edx, ebp; nBufferLength
0x18002b6e7  lea     r8, [rsp+4D8h+Buffer]; lpBuffer
0x18002b6ef  mov     rcx, r14; lpFileName
0x18002b6f2  call    cs:__imp_GetFullPathNameW
0x18002b6f8  test    eax, eax
0x18002b6fa  jnz     short loc_18002B717
0x18002b6fc  call    cs:__imp_GetLastError
0x18002b702  test    eax, eax
0x18002b704  jle     loc_18002B7F2
0x18002b70a  movzx   eax, ax
0x18002b70d  or      eax, 80070000h
0x18002b712  jmp     loc_18002B7F2
0x18002b717  xor     r9d, r9d; lpSecurityAttributes
0x18002b71a  mov     [rsp+4D8h+hTemplateFile], 0; hTemplateFile
0x18002b723  mov     [rsp+4D8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18002b72b  mov     edx, 80000000h; dwDesiredAccess
0x18002b730  mov     rcx, r14; lpFileName
0x18002b733  mov     [rsp+4D8h+dwCreationDisposition], 3; dwCreationDisposition
0x18002b73b  lea     r8d, [r9+1]; dwShareMode
0x18002b73f  call    cs:__imp_CreateFileW
0x18002b745  mov     rsi, rax
0x18002b748  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b74c  jz      short loc_18002B6FC
0x18002b74e  xor     edx, edx; lpFileSizeHigh
0x18002b750  mov     rcx, rax; hFile
0x18002b753  call    cs:__imp_GetFileSize
0x18002b759  mov     rcx, rsi; hObject
0x18002b75c  mov     ebp, eax
0x18002b75e  call    cs:__imp_CloseHandle
0x18002b764  cmp     ebp, 0FFFFFFFFh
0x18002b767  jz      short loc_18002B6FC
0x18002b769  mov     rcx, [rdi]
0x18002b76c  lea     r9, aSSSLdSDDD; "'%s', '%s', '%s', %ld, '%s', %d, %d, %d"
0x18002b773  mov     eax, [rbx+50h]
0x18002b776  lea     r8, aFileComponentF; "File, Component_, FileName, FileSize, V"...
0x18002b77d  mov     [rsp+4D8h+var_480], eax
0x18002b781  lea     rdx, aFile_0; "File"
0x18002b788  mov     [rsp+4D8h+var_488], 0
0x18002b791  lea     rax, a1111; "1.1.1.1"
0x18002b798  mov     [rsp+4D8h+var_490], 0
0x18002b7a1  mov     [rsp+4D8h+var_498], rax
0x18002b7a6  mov     rax, [rsp+4D8h+FilePart]
0x18002b7ab  mov     [rsp+4D8h+var_4A0], ebp
0x18002b7af  mov     [rsp+4D8h+hTemplateFile], rax
0x18002b7b4  mov     qword ptr [rsp+4D8h+dwFlagsAndAttributes], rcx
0x18002b7b9  mov     qword ptr [rsp+4D8h+dwCreationDisposition], rcx
0x18002b7be  mov     rcx, rbx; this
0x18002b7c1  call    ?_InsertRow@CGenerateMSI@@QEAAJPEBG00ZZ; CGenerateMSI::_InsertRow(ushort const *,ushort const *,ushort const *,...)
0x18002b7c6  test    eax, eax
0x18002b7c8  js      short loc_18002B7F2
0x18002b7ca  mov     edx, r15d; unsigned int
0x18002b7cd  mov     rcx, rbx; this
0x18002b7d0  call    ?_GetMakeCab@CGenerateMSI@@QEAAJK@Z; CGenerateMSI::_GetMakeCab(ulong)
0x18002b7d5  test    eax, eax
0x18002b7d7  js      short loc_18002B7F2
0x18002b7d9  mov     rcx, [rbx+268h]
0x18002b7e0  mov     rdx, r14
0x18002b7e3  mov     r8, [rdi]
0x18002b7e6  mov     rax, [rcx]
0x18002b7e9  mov     rax, [rax+20h]
0x18002b7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7f2  inc     dword ptr [rbx+50h]
0x18002b7f5  mov     rcx, [rsp+4D8h+var_48]
0x18002b7fd  xor     rcx, rsp; StackCookie
0x18002b800  call    __security_check_cookie
0x18002b805  add     rsp, 4A8h
0x18002b80c  pop     r15
0x18002b80e  pop     r14
0x18002b810  pop     rdi
0x18002b811  pop     rsi
0x18002b812  pop     rbp
0x18002b813  pop     rbx
0x18002b814  retn
```
