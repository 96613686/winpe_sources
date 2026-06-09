# DataStoreServer::UpdateTemplatesTimestamp(void)

- ea: `0x18000be1c`
- end: `0x18000bf6c`
- name: `?UpdateTemplatesTimestamp@DataStoreServer@@QEAAJXZ`
- size: `336`
- prototype: `unsigned int __fastcall(DataStoreServer *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000b210`

## callees

- `0x18000a4a0`
- `0x18000be1c`
- `0x18000d064`
- `0x18000dce6`
- `0x18000dd10`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000bf04`
- `msvcrt!swprintf_s` at `0x18000bf04`
- `KERNEL32!CreateFileW` at `0x18000bebc`
- `KERNEL32!CreateFileW` at `0x18000bebc`
- `KERNEL32!GetFileInformationByHandle` at `0x18000bedd`
- `KERNEL32!GetFileInformationByHandle` at `0x18000bedd`
- `KERNEL32!CloseHandle` at `0x18000bf1a`
- `KERNEL32!CloseHandle` at `0x18000bf38`
- `KERNEL32!CloseHandle` at `0x18000bf1a`
- `KERNEL32!CloseHandle` at `0x18000bf38`
- `KERNEL32!GetLastError` at `0x18000becb`
- `KERNEL32!GetLastError` at `0x18000bf0f`
- `KERNEL32!GetLastError` at `0x18000becb`
- `KERNEL32!GetLastError` at `0x18000bf0f`

## string_xrefs

- `0x18000bf45`: `//Root/Children/TemplatesTimestamp`
- `0x18000be72`: `\iastemplates.xml`
- `0x18000beeb`: `<TemplatesTimestamp name="TemplatesTimestamp" xmlns:dt="urn:schemas-microsoft-com:datatypes" dt:dt="string">%d,%d</TemplatesTimestamp>`

## pseudocode

```c
unsigned int __fastcall DataStoreServer::UpdateTemplatesTimestamp(DataStoreServer *this)
{
  signed int DatabasePath; // ebx
  HANDLE FileW; // rax
  void *v4; // rdi
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Buffer[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp+190h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  memset(&FileInformation, 0, sizeof(FileInformation));
  DatabasePath = anonymous_namespace_::GetDatabasePath((wchar_t *)L"\\iastemplates.xml", FileName);
  if ( !DatabasePath )
  {
    FileW = CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0, 0);
    v4 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      DatabasePath = GetLastError();
    }
    else
    {
      if ( GetFileInformationByHandle(FileW, &FileInformation) )
      {
        LODWORD(dwCreationDisposition) = FileInformation.ftLastWriteTime.dwLowDateTime;
        if ( swprintf_s(
               Buffer,
               0x104u,
               L"<TemplatesTimestamp name=\"TemplatesTimestamp\" xmlns:dt=\"urn:schemas-microsoft-com:datatypes\" dt:dt=\""
                "string\">%d,%d</TemplatesTimestamp>",
               FileInformation.ftLastWriteTime.dwHighDateTime,
               dwCreationDisposition) != -1 )
        {
          CloseHandle(v4);
          return DataStoreServer::SetConfiguration(this, L"//Root/Children/TemplatesTimestamp", Buffer);
        }
      }
      DatabasePath = GetLastError();
      CloseHandle(v4);
    }
    if ( DatabasePath )
      goto LABEL_8;
    return DataStoreServer::SetConfiguration(this, L"//Root/Children/TemplatesTimestamp", Buffer);
  }
LABEL_8:
  if ( DatabasePath > 0 )
    return (unsigned __int16)DatabasePath | 0x80070000;
  return DatabasePath;
}

```

## disassembly

```asm
0x18000be1c  push    rbp
0x18000be1e  push    rbx
0x18000be1f  push    rsi
0x18000be20  push    rdi
0x18000be21  lea     rbp, [rsp-3B8h]
0x18000be29  sub     rsp, 4B8h
0x18000be30  mov     rax, cs:__security_cookie
0x18000be37  xor     rax, rsp
0x18000be3a  mov     [rbp+3D0h+var_30], rax
0x18000be41  mov     rsi, rcx
0x18000be44  xor     edx, edx; Val
0x18000be46  lea     rcx, [rbp+3D0h+Buffer]; void *
0x18000be4a  mov     r8d, 20Ah; Size
0x18000be50  call    memset_0
0x18000be55  xorps   xmm0, xmm0
0x18000be58  mov     [rsp+4D0h+var_490], 104h
0x18000be60  xor     eax, eax
0x18000be62  lea     r8, [rsp+4D0h+var_490]
0x18000be67  lea     rdx, [rbp+3D0h+FileName]; Destination
0x18000be6e  mov     [rsp+4D0h+FileInformation.nFileIndexLow], eax
0x18000be72  lea     rcx, aIastemplatesXm; "\\iastemplates.xml"
0x18000be79  movups  xmmword ptr [rsp+4D0h+FileInformation.dwFileAttributes], xmm0
0x18000be7e  movups  xmmword ptr [rsp+4D0h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18000be83  movups  xmmword ptr [rsp+4D0h+FileInformation.nFileSizeHigh], xmm0
0x18000be88  call    _anonymous_namespace___GetDatabasePath
0x18000be8d  mov     ebx, eax
0x18000be8f  test    eax, eax
0x18000be91  jnz     loc_18000BF24
0x18000be97  mov     [rsp+4D0h+hTemplateFile], 0; hTemplateFile
0x18000bea0  lea     r8d, [rax+3]; dwShareMode
0x18000bea4  mov     [rsp+4D0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18000bea8  lea     rcx, [rbp+3D0h+FileName]; lpFileName
0x18000beaf  xor     r9d, r9d; lpSecurityAttributes
0x18000beb2  mov     dword ptr [rsp+4D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000beb7  mov     edx, 80000000h; dwDesiredAccess
0x18000bebc  call    cs:__imp_CreateFileW
0x18000bec2  mov     rdi, rax
0x18000bec5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000bec9  jnz     short loc_18000BED5
0x18000becb  call    cs:__imp_GetLastError
0x18000bed1  mov     ebx, eax
0x18000bed3  jmp     short loc_18000BF20
0x18000bed5  lea     rdx, [rsp+4D0h+FileInformation]; lpFileInformation
0x18000beda  mov     rcx, rdi; hFile
0x18000bedd  call    cs:__imp_GetFileInformationByHandle
0x18000bee3  test    eax, eax
0x18000bee5  jz      short loc_18000BF0F
0x18000bee7  mov     eax, [rsp+4D0h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x18000beeb  lea     r8, aTemplatestimes; "<TemplatesTimestamp name=\"TemplatesTim"...
0x18000bef2  mov     r9d, [rsp+4D0h+FileInformation.ftLastWriteTime.dwHighDateTime]
0x18000bef7  lea     rcx, [rbp+3D0h+Buffer]; Buffer
0x18000befb  mov     edx, 104h; BufferCount
0x18000bf00  mov     dword ptr [rsp+4D0h+dwCreationDisposition], eax
0x18000bf04  call    cs:__imp_swprintf_s
0x18000bf0a  cmp     eax, 0FFFFFFFFh
0x18000bf0d  jnz     short loc_18000BF35
0x18000bf0f  call    cs:__imp_GetLastError
0x18000bf15  mov     rcx, rdi; hObject
0x18000bf18  mov     ebx, eax
0x18000bf1a  call    cs:__imp_CloseHandle
0x18000bf20  test    ebx, ebx
0x18000bf22  jz      short loc_18000BF3E
0x18000bf24  test    ebx, ebx
0x18000bf26  jle     short loc_18000BF31
0x18000bf28  movzx   ebx, bx
0x18000bf2b  or      ebx, 80070000h
0x18000bf31  mov     eax, ebx
0x18000bf33  jmp     short loc_18000BF51
0x18000bf35  mov     rcx, rdi; hObject
0x18000bf38  call    cs:__imp_CloseHandle
0x18000bf3e  lea     r8, [rbp+3D0h+Buffer]; unsigned __int16 *
0x18000bf42  mov     rcx, rsi; this
0x18000bf45  lea     rdx, aRootChildrenTe; "//Root/Children/TemplatesTimestamp"
0x18000bf4c  call    ?SetConfiguration@DataStoreServer@@QEAAJPEBG0@Z; DataStoreServer::SetConfiguration(ushort const *,ushort const *)
0x18000bf51  mov     rcx, [rbp+3D0h+var_30]
0x18000bf58  xor     rcx, rsp; StackCookie
0x18000bf5b  call    __security_check_cookie
0x18000bf60  add     rsp, 4B8h
0x18000bf67  pop     rdi
0x18000bf68  pop     rsi
0x18000bf69  pop     rbx
0x18000bf6a  pop     rbp
0x18000bf6b  retn
```
