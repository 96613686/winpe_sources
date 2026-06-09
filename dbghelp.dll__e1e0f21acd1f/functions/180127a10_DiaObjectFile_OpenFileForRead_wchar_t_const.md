# DiaObjectFile::OpenFileForRead(wchar_t const *)

- ea: `0x180127a10`
- end: `0x180127b94`
- name: `?OpenFileForRead@DiaObjectFile@@IEAA_NPEB_W@Z`
- size: `388`
- prototype: `bool(DiaObjectFile *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180126ce0`

## callees

- `0x1800c0690`
- `0x180127a10`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!__doserrno` at `0x180127b49`
- `api-ms-win-crt-runtime-l1-1-0!__doserrno` at `0x180127b49`
- `api-ms-win-crt-private-l1-1-0!_o__open_osfhandle` at `0x180127b3b`
- `api-ms-win-crt-private-l1-1-0!_o__open_osfhandle` at `0x180127b3b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180127ac5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180127ac5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180127a5a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180127a5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180127a6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180127a6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180127b1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180127b1e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180127af0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180127af0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180127b11`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180127b11`

## pseudocode

```c
char __fastcall DiaObjectFile::OpenFileForRead(DiaObjectFile *this, const wchar_t *a2)
{
  HANDLE v4; // rax
  signed int LastError; // eax
  DWORD dwMaximumSizeLow; // eax
  SIZE_T v8; // rdi
  HANDLE FileMappingW; // rax
  void *v10; // rbp
  __int64 v11; // rcx
  int v12; // eax
  signed int v13; // edx
  struct _SECURITY_ATTRIBUTES v14; // [rsp+40h] [rbp-28h] BYREF
  DWORD FileSizeHigh; // [rsp+70h] [rbp+8h] BYREF

  v14.nLength = 24;
  v14.lpSecurityDescriptor = 0;
  v14.bInheritHandle = 0;
  v4 = CreateFileW(a2, 0x80000000, 5u, &v14, 3u, 0x80u, 0);
  *((_QWORD *)this + 3) = v4;
  if ( v4 == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    SymCache::ReportErrorViaCallback(*(SymCache **)(*((_QWORD *)this + 23) + 648LL), LastError, a2, 0);
    return 0;
  }
  else
  {
    if ( (*((_DWORD *)this + 12) & 0x800000) != 0 )
    {
      FileSizeHigh = 0;
      dwMaximumSizeLow = GetFileSize(v4, &FileSizeHigh);
      v8 = dwMaximumSizeLow;
      if ( dwMaximumSizeLow != -1 && !FileSizeHigh )
      {
        FileMappingW = CreateFileMappingW(*((HANDLE *)this + 3), 0, 2u, 0, dwMaximumSizeLow, 0);
        v10 = FileMappingW;
        if ( FileMappingW )
        {
          *((_QWORD *)this + 4) = MapViewOfFile(FileMappingW, 4u, 0, 0, v8);
          CloseHandle(v10);
          if ( *((_QWORD *)this + 4) )
            return 1;
        }
      }
    }
    v11 = *((_QWORD *)this + 3);
    *((_DWORD *)this + 12) &= ~0x800000u;
    v12 = _o__open_osfhandle(v11, 32896);
    *((_DWORD *)this + 4) = v12;
    if ( v12 != -1 )
    {
      return 1;
    }
    else
    {
      v13 = *__doserrno();
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      SymCache::ReportErrorViaCallback(*(SymCache **)(*((_QWORD *)this + 23) + 648LL), v13, a2, 0);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180127a10  mov     rax, rsp
0x180127a13  mov     [rax+18h], rbx
0x180127a17  mov     [rax+20h], rbp
0x180127a1b  push    rsi
0x180127a1c  sub     rsp, 60h
0x180127a20  xor     ebp, ebp
0x180127a22  mov     dword ptr [rax-28h], 18h
0x180127a29  mov     rsi, rdx
0x180127a2c  mov     [rax-38h], rbp
0x180127a30  mov     rbx, rcx
0x180127a33  mov     dword ptr [rax-40h], 80h
0x180127a3a  lea     r9, [rax-28h]; lpSecurityAttributes
0x180127a3e  mov     dword ptr [rax-48h], 3
0x180127a45  mov     edx, 80000000h; dwDesiredAccess
0x180127a4a  mov     [rax-20h], rbp
0x180127a4e  mov     r8d, 5; dwShareMode
0x180127a54  mov     [rax-18h], ebp
0x180127a57  mov     rcx, rsi; lpFileName
0x180127a5a  call    cs:__imp_CreateFileW
0x180127a60  mov     [rbx+18h], rax
0x180127a64  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180127a68  jnz     short loc_180127AAB
0x180127a6a  call    cs:__imp_GetLastError
0x180127a70  test    eax, eax
0x180127a72  jle     short loc_180127A7C
0x180127a74  movzx   eax, ax
0x180127a77  or      eax, 80070000h
0x180127a7c  mov     rcx, [rbx+0B8h]
0x180127a83  xor     r9d, r9d; wchar_t *
0x180127a86  mov     r8, rsi; wchar_t *
0x180127a89  mov     edx, eax; int
0x180127a8b  mov     rcx, [rcx+288h]; this
0x180127a92  call    ?ReportErrorViaCallback@SymCache@@QEAAXJPEB_W0@Z; SymCache::ReportErrorViaCallback(long,wchar_t const *,wchar_t const *)
0x180127a97  xor     al, al
0x180127a99  lea     r11, [rsp+68h+var_8]
0x180127a9e  mov     rbx, [r11+20h]
0x180127aa2  mov     rbp, [r11+28h]
0x180127aa6  mov     rsp, r11
0x180127aa9  pop     rsi
0x180127aaa  retn
0x180127aab  test    dword ptr [rbx+30h], 800000h
0x180127ab2  mov     [rsp+68h+arg_8], rdi
0x180127ab7  jz      short loc_180127B2B
0x180127ab9  lea     rdx, [rsp+68h+FileSizeHigh]; lpFileSizeHigh
0x180127abe  mov     [rsp+68h+FileSizeHigh], ebp
0x180127ac2  mov     rcx, rax; hFile
0x180127ac5  call    cs:__imp_GetFileSize
0x180127acb  mov     edi, eax
0x180127acd  cmp     eax, 0FFFFFFFFh
0x180127ad0  jz      short loc_180127B2B
0x180127ad2  cmp     [rsp+68h+FileSizeHigh], ebp
0x180127ad6  jnz     short loc_180127B2B
0x180127ad8  mov     rcx, [rbx+18h]; hFile
0x180127adc  xor     r9d, r9d; dwMaximumSizeHigh
0x180127adf  mov     [rsp+68h+lpName], rbp; lpName
0x180127ae4  xor     edx, edx; lpFileMappingAttributes
0x180127ae6  mov     r8d, 2; flProtect
0x180127aec  mov     [rsp+68h+dwMaximumSizeLow], edi; dwMaximumSizeLow
0x180127af0  call    cs:__imp_CreateFileMappingW
0x180127af6  mov     rbp, rax
0x180127af9  test    rax, rax
0x180127afc  jz      short loc_180127B2B
0x180127afe  xor     r9d, r9d; dwFileOffsetLow
0x180127b01  mov     qword ptr [rsp+68h+dwMaximumSizeLow], rdi; dwNumberOfBytesToMap
0x180127b06  xor     r8d, r8d; dwFileOffsetHigh
0x180127b09  mov     edx, 4; dwDesiredAccess
0x180127b0e  mov     rcx, rax; hFileMappingObject
0x180127b11  call    cs:__imp_MapViewOfFile
0x180127b17  mov     rcx, rbp; hObject
0x180127b1a  mov     [rbx+20h], rax
0x180127b1e  call    cs:__imp_CloseHandle
0x180127b24  cmp     qword ptr [rbx+20h], 0
0x180127b29  jnz     short loc_180127B7B
0x180127b2b  mov     rcx, [rbx+18h]
0x180127b2f  mov     edx, 8080h
0x180127b34  and     dword ptr [rbx+30h], 0FF7FFFFFh
0x180127b3b  call    cs:__imp__o__open_osfhandle
0x180127b41  mov     [rbx+10h], eax
0x180127b44  cmp     eax, 0FFFFFFFFh
0x180127b47  jnz     short loc_180127B7B
0x180127b49  call    cs:__imp___doserrno
0x180127b4f  mov     edx, [rax]
0x180127b51  test    edx, edx
0x180127b53  jle     short loc_180127B5E
0x180127b55  movzx   edx, dx
0x180127b58  or      edx, 80070000h; int
0x180127b5e  mov     rcx, [rbx+0B8h]
0x180127b65  xor     r9d, r9d; wchar_t *
0x180127b68  mov     r8, rsi; wchar_t *
0x180127b6b  mov     rcx, [rcx+288h]; this
0x180127b72  call    ?ReportErrorViaCallback@SymCache@@QEAAXJPEB_W0@Z; SymCache::ReportErrorViaCallback(long,wchar_t const *,wchar_t const *)
0x180127b77  xor     al, al
0x180127b79  jmp     short loc_180127B7D
0x180127b7b  mov     al, 1
0x180127b7d  mov     rdi, [rsp+68h+arg_8]
0x180127b82  lea     r11, [rsp+68h+var_8]
0x180127b87  mov     rbx, [r11+20h]
0x180127b8b  mov     rbp, [r11+28h]
0x180127b8f  mov     rsp, r11
0x180127b92  pop     rsi
0x180127b93  retn
```
