# FeedbackHubUpdateActivityID(_GUID *)

- ea: `0x1801a7da8`
- end: `0x1801a80e3`
- name: `?FeedbackHubUpdateActivityID@@YAJPEAU_GUID@@@Z`
- size: `827`
- prototype: `__int64 __fastcall(IID *rclsid)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180177d94`

## callees

- `0x180001fb0`
- `0x1800829d4`
- `0x180082ad8`
- `0x180085e04`
- `0x1801a7cb8`
- `0x1801a7da8`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801a80bc`
- `KERNEL32!CloseHandle` at `0x1801a80bc`
- `KERNEL32!GetLastError` at `0x1801a7fd2`
- `KERNEL32!GetLastError` at `0x1801a8035`
- `KERNEL32!GetLastError` at `0x1801a7fd2`
- `KERNEL32!GetLastError` at `0x1801a8035`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1801a7f55`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1801a7f55`
- `KERNEL32!CreateFileW` at `0x1801a7fb5`
- `KERNEL32!CreateFileW` at `0x1801a7fb5`
- `KERNEL32!WriteFile` at `0x1801a8020`
- `KERNEL32!WriteFile` at `0x1801a8020`
- `OLE32!StringFromCLSID` at `0x1801a7e7a`
- `OLE32!StringFromCLSID` at `0x1801a7e7a`
- `OLE32!CoTaskMemFree` at `0x1801a80ae`
- `OLE32!CoTaskMemFree` at `0x1801a80ae`

## string_xrefs

- `0x1801a7e35`: `Got told to update activity id`
- `0x1801a7df8`: `Got told to update activity id, but NULL was passed`
- `0x1801a7ee9`: `{\n"ServerLinkId": "%s" \n}`
- `0x1801a7e95`: `StringFromCLSID failed`
- `0x1801a7f4e`: `%TEMP%\diagoutputdir\rdp\diagtrack_serverlink.json`
- `0x1801a7fe3`: `Failed to create file for writing`
- `0x1801a7f73`: `MAX_PATH is not large enough for ExpandEnvironmentStrings`
- `0x1801a8046`: `Failed to write file with activity id`

## pseudocode

```c
__int64 __fastcall FeedbackHubUpdateActivityID(IID *rclsid, __int64 a2, int a3, int a4)
{
  void *v5; // r14
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  const char *v9; // rax
  char *v10; // rdx
  __int64 v11; // rsi
  __int64 v12; // rcx
  HANDLE FileW; // rax
  int v14; // r8d
  int v15; // r9d
  int v16; // r8d
  int v17; // r9d
  int v18; // r8d
  int v19; // r9d
  const char *v21; // [rsp+40h] [rbp-C0h] BYREF
  const char *v22; // [rsp+48h] [rbp-B8h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-B0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Dst[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 Buffer[264]; // [rsp+270h] [rbp+170h] BYREF

  NumberOfBytesWritten = 0;
  lpsz = 0;
  v5 = 0;
  if ( !rclsid )
  {
    if ( (unsigned int)dword_1808B4BE0 > 4 )
    {
      v21 = "Got told to update activity id, but NULL was passed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_1808B4BE0,
        (unsigned int)qword_18085E218,
        0,
        a4,
        (__int64)&v21);
    }
    goto LABEL_28;
  }
  if ( (unsigned int)dword_1808B4BE0 > 4 )
  {
    v21 = (const char *)rclsid;
    v22 = "Got told to update activity id";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1808B4BE0,
      (unsigned int)byte_18085E23D,
      a3,
      a4,
      (__int64)&v22,
      (__int64)&v21);
  }
  *(_WORD *)&rclsid->Data4[6] |= 0x8000u;
  v6 = StringFromCLSID(rclsid, &lpsz);
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_1808B4BE0 <= 4 )
      goto LABEL_28;
    v9 = "StringFromCLSID failed";
    v10 = (char *)&word_18085E1EE;
LABEL_9:
    v22 = v9;
    LODWORD(v21) = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1808B4BE0,
      (_DWORD)v10,
      v7,
      v8,
      (__int64)&v22,
      (__int64)&v21);
    goto LABEL_28;
  }
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( lpsz[v12] );
  lpsz[v12 - 1] = 0;
  v6 = StringCchPrintfW(Buffer, 0x104u, L"{\n\"ServerLinkId\": \"%s\" \n}", lpsz + 1);
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_1808B4BE0 <= 4 )
      goto LABEL_28;
    v9 = "StringCchPrintfW failed";
    v10 = byte_18085E191;
    goto LABEL_9;
  }
  do
    ++v11;
  while ( Buffer[v11] );
  v6 = ExpandEnvironmentStringsW(L"%TEMP%\\diagoutputdir\\rdp\\diagtrack_serverlink.json", Dst, 0x104u);
  if ( (unsigned int)v6 > 0x104 )
  {
    if ( (unsigned int)dword_1808B4BE0 <= 4 )
      goto LABEL_28;
    v9 = "MAX_PATH is not large enough for ExpandEnvironmentStrings";
    v10 = byte_18085E1BB;
    goto LABEL_9;
  }
  CreateDirectoryRecursive(Dst);
  FileW = CreateFileW(Dst, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v5 = FileW;
  if ( FileW )
  {
    if ( WriteFile(FileW, Buffer, 2 * v11, &NumberOfBytesWritten, 0) )
    {
      if ( (unsigned int)dword_1808B4BE0 > 4 )
      {
        v22 = (const char *)rclsid;
        v21 = "New activity id written successfully";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
          (unsigned int)&dword_1808B4BE0,
          (unsigned int)&word_18085E0F6,
          v16,
          v17,
          (__int64)&v21,
          (__int64)&v22);
      }
    }
    else if ( (unsigned int)dword_1808B4BE0 > 4 )
    {
      LODWORD(v21) = GetLastError();
      v22 = "Failed to write file with activity id";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1808B4BE0,
        (unsigned int)&byte_18085E127,
        v18,
        v19,
        (__int64)&v22,
        (__int64)&v21);
    }
  }
  else if ( (unsigned int)dword_1808B4BE0 > 4 )
  {
    LODWORD(v21) = GetLastError();
    v22 = "Failed to create file for writing";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1808B4BE0,
      (unsigned int)&dword_18085E15C,
      v14,
      v15,
      (__int64)&v22,
      (__int64)&v21);
  }
LABEL_28:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( v5 )
    CloseHandle(v5);
  return 0;
}

```

## disassembly

```asm
0x1801a7da8  push    rbp
0x1801a7daa  push    rbx
0x1801a7dab  push    rsi
0x1801a7dac  push    rdi
0x1801a7dad  push    r14
0x1801a7daf  push    r15
0x1801a7db1  lea     rbp, [rsp-398h]
0x1801a7db9  sub     rsp, 498h
0x1801a7dc0  mov     rax, cs:__security_cookie
0x1801a7dc7  xor     rax, rsp
0x1801a7dca  mov     [rbp+3C0h+var_40], rax
0x1801a7dd1  mov     eax, cs:dword_1808B4BE0
0x1801a7dd7  xor     r15d, r15d
0x1801a7dda  mov     [rsp+4C0h+NumberOfBytesWritten], r15d
0x1801a7ddf  mov     rdi, rcx
0x1801a7de2  mov     [rsp+4C0h+lpsz], r15
0x1801a7de7  mov     r14d, r15d
0x1801a7dea  test    rcx, rcx
0x1801a7ded  jnz     short loc_1801A7E29
0x1801a7def  cmp     eax, 4
0x1801a7df2  jbe     loc_1801A80A4
0x1801a7df8  lea     rax, aGotToldToUpdat; "Got told to update activity id, but NUL"...
0x1801a7dff  xor     r8d, r8d
0x1801a7e02  mov     [rsp+4C0h+var_480], rax
0x1801a7e07  lea     rdx, qword_18085E218
0x1801a7e0e  lea     rax, [rsp+4C0h+var_480]
0x1801a7e13  lea     rcx, dword_1808B4BE0
0x1801a7e1a  mov     qword ptr [rsp+4C0h+dwCreationDisposition], rax
0x1801a7e1f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1801a7e24  jmp     loc_1801A80A4
0x1801a7e29  lea     rbx, dword_1808B4BE0
0x1801a7e30  cmp     eax, 4
0x1801a7e33  jbe     short loc_1801A7E69
0x1801a7e35  lea     rax, aGotToldToUpdat_0; "Got told to update activity id"
0x1801a7e3c  mov     [rsp+4C0h+var_480], rdi
0x1801a7e41  mov     [rsp+4C0h+var_478], rax
0x1801a7e46  lea     rdx, byte_18085E23D
0x1801a7e4d  lea     rax, [rsp+4C0h+var_480]
0x1801a7e52  mov     rcx, rbx
0x1801a7e55  mov     qword ptr [rsp+4C0h+dwFlagsAndAttributes], rax
0x1801a7e5a  lea     rax, [rsp+4C0h+var_478]
0x1801a7e5f  mov     qword ptr [rsp+4C0h+dwCreationDisposition], rax
0x1801a7e64  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x1801a7e69  mov     eax, 8000h
0x1801a7e6e  lea     rdx, [rsp+4C0h+lpsz]; lplpsz
0x1801a7e73  or      [rdi+0Eh], ax
0x1801a7e77  mov     rcx, rdi; rclsid
0x1801a7e7a  call    cs:__imp_StringFromCLSID
0x1801a7e80  mov     ecx, eax
0x1801a7e82  test    eax, eax
0x1801a7e84  jns     short loc_1801A7ECD
0x1801a7e86  mov     eax, cs:dword_1808B4BE0
0x1801a7e8c  cmp     eax, 4
0x1801a7e8f  jbe     loc_1801A80A4
0x1801a7e95  lea     rax, aStringfromclsi_0; "StringFromCLSID failed"
0x1801a7e9c  lea     rdx, word_18085E1EE
0x1801a7ea3  mov     [rsp+4C0h+var_478], rax
0x1801a7ea8  lea     rax, [rsp+4C0h+var_480]
0x1801a7ead  mov     qword ptr [rsp+4C0h+dwFlagsAndAttributes], rax
0x1801a7eb2  lea     rax, [rsp+4C0h+var_478]
0x1801a7eb7  mov     qword ptr [rsp+4C0h+dwCreationDisposition], rax
0x1801a7ebc  mov     dword ptr [rsp+4C0h+var_480], ecx
0x1801a7ec0  mov     rcx, rbx
0x1801a7ec3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801a7ec8  jmp     loc_1801A80A4
0x1801a7ecd  mov     rdx, [rsp+4C0h+lpsz]
0x1801a7ed2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801a7ed6  mov     rcx, rsi
0x1801a7ed9  inc     rcx
0x1801a7edc  cmp     [rdx+rcx*2], r15w
0x1801a7ee1  jnz     short loc_1801A7ED9
0x1801a7ee3  mov     [rdx+rcx*2-2], r15w
0x1801a7ee9  lea     r8, aServerlinkidS; "{\n\"ServerLinkId\": \"%s\" \n}"
0x1801a7ef0  mov     r9, [rsp+4C0h+lpsz]
0x1801a7ef5  lea     rcx, [rbp+3C0h+Buffer]; unsigned __int16 *
0x1801a7efc  add     r9, 2
0x1801a7f00  mov     edx, 104h; unsigned __int64
0x1801a7f05  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801a7f0a  mov     ecx, eax
0x1801a7f0c  test    eax, eax
0x1801a7f0e  jns     short loc_1801A7F32
0x1801a7f10  mov     eax, cs:dword_1808B4BE0
0x1801a7f16  cmp     eax, 4
0x1801a7f19  jbe     loc_1801A80A4
0x1801a7f1f  lea     rax, aStringcchprint_9; "StringCchPrintfW failed"
0x1801a7f26  lea     rdx, byte_18085E191
0x1801a7f2d  jmp     loc_1801A7EA3
0x1801a7f32  lea     rax, [rbp+3C0h+Buffer]
0x1801a7f39  inc     rsi
0x1801a7f3c  cmp     [rax+rsi*2], r15w
0x1801a7f41  jnz     short loc_1801A7F39
0x1801a7f43  mov     r8d, 104h; nSize
0x1801a7f49  lea     rdx, [rsp+4C0h+Dst]; lpDst
0x1801a7f4e  lea     rcx, Src; "%TEMP%\\diagoutputdir\\rdp\\diagtrack_s"...
0x1801a7f55  call    cs:__imp_ExpandEnvironmentStringsW
0x1801a7f5b  mov     ecx, eax
0x1801a7f5d  cmp     eax, 104h
0x1801a7f62  jbe     short loc_1801A7F86
0x1801a7f64  mov     eax, cs:dword_1808B4BE0
0x1801a7f6a  cmp     eax, 4
0x1801a7f6d  jbe     loc_1801A80A4
0x1801a7f73  lea     rax, aMaxPathIsNotLa; "MAX_PATH is not large enough for Expand"...
0x1801a7f7a  lea     rdx, byte_18085E1BB
0x1801a7f81  jmp     loc_1801A7EA3
0x1801a7f86  lea     rcx, [rsp+4C0h+Dst]; Source
0x1801a7f8b  call    ?CreateDirectoryRecursive@@YAXPEAG@Z; CreateDirectoryRecursive(ushort *)
0x1801a7f90  mov     [rsp+4C0h+hTemplateFile], r15; hTemplateFile
0x1801a7f95  lea     rcx, [rsp+4C0h+Dst]; lpFileName
0x1801a7f9a  mov     [rsp+4C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1801a7fa2  xor     r9d, r9d; lpSecurityAttributes
0x1801a7fa5  xor     r8d, r8d; dwShareMode
0x1801a7fa8  mov     [rsp+4C0h+dwCreationDisposition], 2; dwCreationDisposition
0x1801a7fb0  mov     edx, 40000000h; dwDesiredAccess
0x1801a7fb5  call    cs:__imp_CreateFileW
0x1801a7fbb  mov     r14, rax
0x1801a7fbe  test    rax, rax
0x1801a7fc1  jnz     short loc_1801A8008
0x1801a7fc3  mov     ecx, cs:dword_1808B4BE0
0x1801a7fc9  cmp     ecx, 4
0x1801a7fcc  jbe     loc_1801A80A4
0x1801a7fd2  call    cs:__imp_GetLastError
0x1801a7fd8  mov     dword ptr [rsp+4C0h+var_480], eax
0x1801a7fdc  lea     rdx, dword_18085E15C
0x1801a7fe3  lea     rax, aFailedToCreate_35; "Failed to create file for writing"
0x1801a7fea  mov     [rsp+4C0h+var_478], rax
0x1801a7fef  lea     rax, [rsp+4C0h+var_480]
0x1801a7ff4  mov     qword ptr [rsp+4C0h+dwFlagsAndAttributes], rax
0x1801a7ff9  lea     rax, [rsp+4C0h+var_478]
0x1801a7ffe  mov     qword ptr [rsp+4C0h+dwCreationDisposition], rax
0x1801a8003  jmp     loc_1801A7EC0
0x1801a8008  lea     r8d, [rsi+rsi]; nNumberOfBytesToWrite
0x1801a800c  mov     qword ptr [rsp+4C0h+dwCreationDisposition], r15; lpOverlapped
0x1801a8011  lea     r9, [rsp+4C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801a8016  mov     rcx, rax; hFile
0x1801a8019  lea     rdx, [rbp+3C0h+Buffer]; lpBuffer
0x1801a8020  call    cs:__imp_WriteFile
0x1801a8026  test    eax, eax
0x1801a8028  mov     eax, cs:dword_1808B4BE0
0x1801a802e  jnz     short loc_1801A806B
0x1801a8030  cmp     eax, 4
0x1801a8033  jbe     short loc_1801A80A4
0x1801a8035  call    cs:__imp_GetLastError
0x1801a803b  mov     dword ptr [rsp+4C0h+var_480], eax
0x1801a803f  lea     rdx, byte_18085E127
0x1801a8046  lea     rax, aFailedToWriteF; "Failed to write file with activity id"
0x1801a804d  mov     [rsp+4C0h+var_478], rax
0x1801a8052  lea     rax, [rsp+4C0h+var_480]
0x1801a8057  mov     qword ptr [rsp+4C0h+dwFlagsAndAttributes], rax
0x1801a805c  lea     rax, [rsp+4C0h+var_478]
0x1801a8061  mov     qword ptr [rsp+4C0h+dwCreationDisposition], rax
0x1801a8066  jmp     loc_1801A7EC0
0x1801a806b  cmp     eax, 4
0x1801a806e  jbe     short loc_1801A80A4
0x1801a8070  lea     rax, aNewActivityIdW; "New activity id written successfully"
0x1801a8077  mov     [rsp+4C0h+var_478], rdi
0x1801a807c  mov     [rsp+4C0h+var_480], rax
0x1801a8081  lea     rdx, word_18085E0F6
0x1801a8088  lea     rax, [rsp+4C0h+var_478]
0x1801a808d  mov     rcx, rbx
0x1801a8090  mov     qword ptr [rsp+4C0h+dwFlagsAndAttributes], rax
0x1801a8095  lea     rax, [rsp+4C0h+var_480]
0x1801a809a  mov     qword ptr [rsp+4C0h+dwCreationDisposition], rax
0x1801a809f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x1801a80a4  mov     rcx, [rsp+4C0h+lpsz]; pv
0x1801a80a9  test    rcx, rcx
0x1801a80ac  jz      short loc_1801A80B4
0x1801a80ae  call    cs:__imp_CoTaskMemFree
0x1801a80b4  test    r14, r14
0x1801a80b7  jz      short loc_1801A80C2
0x1801a80b9  mov     rcx, r14; hObject
0x1801a80bc  call    cs:__imp_CloseHandle
0x1801a80c2  xor     eax, eax
0x1801a80c4  mov     rcx, [rbp+3C0h+var_40]
0x1801a80cb  xor     rcx, rsp; StackCookie
0x1801a80ce  call    __security_check_cookie
0x1801a80d3  add     rsp, 498h
0x1801a80da  pop     r15
0x1801a80dc  pop     r14
0x1801a80de  pop     rdi
0x1801a80df  pop     rsi
0x1801a80e0  pop     rbx
0x1801a80e1  pop     rbp
0x1801a80e2  retn
```
