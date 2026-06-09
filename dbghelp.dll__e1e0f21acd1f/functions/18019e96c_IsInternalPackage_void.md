# IsInternalPackage(void)

- ea: `0x18019e96c`
- end: `0x18019eb64`
- name: `?IsInternalPackage@@YA_NXZ`
- size: `504`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1801a03ec`
- `0x1801a09a0`

## callees

- `0x180012e6c`
- `0x180012ed4`
- `0x180027430`
- `0x18019e96c`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x18019eb08`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x18019eb08`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18019ea49`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18019ea49`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18019eae5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18019eae5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019eaac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019eaac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019eb2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019eb2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019eb1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019eb1b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18019e9f8`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18019e9f8`

## pseudocode

```c
bool IsInternalPackage(void)
{
  bool v0; // zf
  char *FileW; // rax
  void *v3; // rbx
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Drive[4]; // [rsp+58h] [rbp-A8h] BYREF
  char Buffer[64]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Dir[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  NumberOfBytesRead = 0;
  memset_0(Filename, 0, 0x20Au);
  *(_QWORD *)Drive = 0;
  memset_0(Dir, 0, 0x202u);
  v0 = dword_1802B29B0 == 0;
  if ( dword_1802B29B0 >= 0 )
    return v0;
  if ( GetModuleFileNameW(0, Filename, 0x105u) )
  {
    _wsplitpath_s(Filename, Drive, 4u, Dir, 0x101u, 0, 0, 0, 0);
    wcscpy_s_ex(Filename, 0x105u, Drive);
    wcscat_s_ex(Filename, 0x105u, Dir);
    wcscat_s_ex(Filename, 0x105u, L"\\winxp\\triage.ini");
    FileW = (char *)CreateFileW(Filename, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v3 = FileW;
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      dword_1802B29B0 = 1;
      if ( ReadFile(FileW, Buffer, 0x40u, &NumberOfBytesRead, 0)
        && NumberOfBytesRead > 0x11
        && !_strnicmp(Buffer, ";internal_package", 0x11u) )
      {
        dword_1802B29B0 = 0;
      }
      CloseHandle(v3);
      return dword_1802B29B0 == 0;
    }
    if ( GetLastError() == 2 )
      dword_1802B29B0 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18019e96c  mov     [rsp-8+arg_0], rbx
0x18019e971  push    rbp
0x18019e972  lea     rbp, [rsp-3D0h]
0x18019e97a  sub     rsp, 4D0h
0x18019e981  mov     rax, cs:__security_cookie
0x18019e988  xor     rax, rsp
0x18019e98b  mov     [rbp+3D0h+var_10], rax
0x18019e992  xor     edx, edx; Val
0x18019e994  lea     rcx, [rsp+4D0h+Buffer]; void *
0x18019e999  lea     r8d, [rdx+40h]; Size
0x18019e99d  call    memset_0
0x18019e9a2  xor     edx, edx; Val
0x18019e9a4  mov     [rsp+4D0h+NumberOfBytesRead], 0
0x18019e9ac  mov     r8d, 20Ah; Size
0x18019e9b2  lea     rcx, [rbp+3D0h+Filename]; void *
0x18019e9b6  call    memset_0
0x18019e9bb  xor     edx, edx; Val
0x18019e9bd  mov     qword ptr [rsp+4D0h+Drive], 0
0x18019e9c6  mov     r8d, 202h; Size
0x18019e9cc  lea     rcx, [rbp+3D0h+Dir]; void *
0x18019e9d3  call    memset_0
0x18019e9d8  mov     eax, cs:dword_1802B29B0
0x18019e9de  test    eax, eax
0x18019e9e0  js      short loc_18019E9EA
0x18019e9e2  setz    al
0x18019e9e5  jmp     loc_18019EB44
0x18019e9ea  mov     ebx, 105h
0x18019e9ef  lea     rdx, [rbp+3D0h+Filename]; lpFilename
0x18019e9f3  mov     r8d, ebx; nSize
0x18019e9f6  xor     ecx, ecx; hModule
0x18019e9f8  call    cs:__imp_GetModuleFileNameW
0x18019e9fe  test    eax, eax
0x18019ea00  jz      loc_18019EB42
0x18019ea06  mov     [rsp+4D0h+ExtCount], 0; ExtCount
0x18019ea0f  lea     r9, [rbp+3D0h+Dir]; Dir
0x18019ea16  mov     [rsp+4D0h+Ext], 0; Ext
0x18019ea1f  lea     rdx, [rsp+4D0h+Drive]; Drive
0x18019ea24  mov     [rsp+4D0h+FilenameCount], 0; FilenameCount
0x18019ea2d  lea     rcx, [rbp+3D0h+Filename]; FullPath
0x18019ea31  mov     qword ptr [rsp+4D0h+dwFlagsAndAttributes], 0; Filename
0x18019ea3a  mov     r8d, 4; DriveCount
0x18019ea40  mov     [rsp+4D0h+DirCount], 101h; DirCount
0x18019ea49  call    cs:__imp__wsplitpath_s
0x18019ea4f  lea     r8, [rsp+4D0h+Drive]; unsigned __int16 *
0x18019ea54  mov     edx, ebx; unsigned __int64
0x18019ea56  lea     rcx, [rbp+3D0h+Filename]; unsigned __int16 *
0x18019ea5a  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x18019ea5f  lea     r8, [rbp+3D0h+Dir]; unsigned __int16 *
0x18019ea66  mov     edx, ebx; unsigned __int64
0x18019ea68  lea     rcx, [rbp+3D0h+Filename]; unsigned __int16 *
0x18019ea6c  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x18019ea71  lea     r8, aWinxpTriageIni; "\\winxp\\triage.ini"
0x18019ea78  mov     edx, ebx; unsigned __int64
0x18019ea7a  lea     rcx, [rbp+3D0h+Filename]; unsigned __int16 *
0x18019ea7e  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x18019ea83  xor     r9d, r9d; lpSecurityAttributes
0x18019ea86  mov     [rsp+4D0h+FilenameCount], 0; hTemplateFile
0x18019ea8f  mov     [rsp+4D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18019ea97  lea     rcx, [rbp+3D0h+Filename]; lpFileName
0x18019ea9b  mov     edx, 80000000h; dwDesiredAccess
0x18019eaa0  mov     dword ptr [rsp+4D0h+DirCount], 3; dwCreationDisposition
0x18019eaa8  lea     r8d, [r9+1]; dwShareMode
0x18019eaac  call    cs:__imp_CreateFileW
0x18019eab2  mov     rbx, rax
0x18019eab5  lea     rcx, [rax-1]
0x18019eab9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18019eabd  ja      short loc_18019EB2D
0x18019eabf  lea     r9, [rsp+4D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18019eac4  mov     cs:dword_1802B29B0, 1
0x18019eace  mov     r8d, 40h ; '@'; nNumberOfBytesToRead
0x18019ead4  mov     [rsp+4D0h+DirCount], 0; lpOverlapped
0x18019eadd  lea     rdx, [rsp+4D0h+Buffer]; lpBuffer
0x18019eae2  mov     rcx, rax; hFile
0x18019eae5  call    cs:__imp_ReadFile
0x18019eaeb  test    eax, eax
0x18019eaed  jz      short loc_18019EB18
0x18019eaef  mov     r8d, 11h; MaxCount
0x18019eaf5  cmp     [rsp+4D0h+NumberOfBytesRead], r8d
0x18019eafa  jbe     short loc_18019EB18
0x18019eafc  lea     rdx, aInternalPackag; ";internal_package"
0x18019eb03  lea     rcx, [rsp+4D0h+Buffer]; String1
0x18019eb08  call    cs:__imp__strnicmp
0x18019eb0e  test    eax, eax
0x18019eb10  jnz     short loc_18019EB18
0x18019eb12  mov     cs:dword_1802B29B0, eax
0x18019eb18  mov     rcx, rbx; hObject
0x18019eb1b  call    cs:__imp_CloseHandle
0x18019eb21  cmp     cs:dword_1802B29B0, 0
0x18019eb28  jmp     loc_18019E9E2
0x18019eb2d  call    cs:__imp_GetLastError
0x18019eb33  cmp     eax, 2
0x18019eb36  jnz     short loc_18019EB42
0x18019eb38  mov     cs:dword_1802B29B0, 1
0x18019eb42  xor     al, al
0x18019eb44  mov     rcx, [rbp+3D0h+var_10]
0x18019eb4b  xor     rcx, rsp; StackCookie
0x18019eb4e  call    __security_check_cookie
0x18019eb53  mov     rbx, [rsp+4D0h+arg_0]
0x18019eb5b  add     rsp, 4D0h
0x18019eb62  pop     rbp
0x18019eb63  retn
```
