# RepoMan::FileSystem::CFileStream::CFileStream(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,RepoMan::FileSystem::OpenMode)

- ea: `0x18018da80`
- end: `0x18018dbc0`
- name: `??0CFileStream@FileSystem@RepoMan@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4OpenMode@12@@Z`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x18018e288`

## callees

- `0x18018b53c`
- `0x18018ce58`
- `0x18018da80`
- `0x18018f7a4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18018dba4`
- `KERNEL32!GetLastError` at `0x18018dba4`
- `KERNEL32!SetLastError` at `0x18018db84`
- `KERNEL32!SetLastError` at `0x18018db84`
- `KERNEL32!CreateFileW` at `0x18018db72`
- `KERNEL32!CreateFileW` at `0x18018db72`

## string_xrefs

- `0x18018dbae`: `CreateFile failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RepoMan::FileSystem::CFileStream::CFileStream(__int64 a1, const CHAR *a2, int a3)
{
  const WCHAR *v6; // r14
  DWORD v7; // edx
  DWORD v8; // r10d
  DWORD dwCreationDisposition; // ecx
  DWORD dwFlagsAndAttributes; // r9d
  int v11; // r8d
  int v12; // r8d
  int v13; // r8d
  HANDLE FileW; // rax
  DWORD LastError; // eax
  __int64 v17; // rdx

  *(_DWORD *)(a1 + 16) = 1;
  *(_QWORD *)a1 = &RepoMan::FileSystem::CFileStream::`vftable'{for `IStream'};
  *(_QWORD *)(a1 + 8) = &RepoMan::FileSystem::CFileStream::`vftable'{for `RepoMan::QIHelper<IStreamSideChannel>'};
  v6 = (const WCHAR *)(a1 + 24);
  RepoMan::utf8_to_wstring((LPWSTR)(a1 + 24), a2);
  *(_DWORD *)(a1 + 56) = a3;
  *(_BYTE *)(a1 + 60) = RepoMan::FileSystem::CanBeSigned(a2);
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  v7 = 0;
  v8 = 0;
  dwCreationDisposition = 0;
  dwFlagsAndAttributes = 128;
  v11 = *(_DWORD *)(a1 + 56);
  if ( !v11 )
  {
    v7 = 0x80000000;
    dwCreationDisposition = 3;
    v8 = 1;
    dwFlagsAndAttributes = 134217856;
    goto LABEL_9;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    v7 = -1073741824;
    dwCreationDisposition = 2;
    goto LABEL_10;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v7 = -1073741824;
    dwCreationDisposition = 4;
LABEL_9:
    *(_BYTE *)(a1 + 60) = 0;
    goto LABEL_10;
  }
  if ( v13 == 1 )
  {
    v7 = -1073741824;
    dwCreationDisposition = 4;
  }
LABEL_10:
  if ( *((_QWORD *)v6 + 3) > 7u )
    v6 = *(const WCHAR **)v6;
  FileW = CreateFileW(v6, v7, v8, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
  *(_QWORD *)(a1 + 64) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    RepoMan::RaiseException<RepoMan::Win32Exception,unsigned long>(376, v17, "CreateFile failed.", LastError);
  }
  SetLastError(0);
  return a1;
}

```

## disassembly

```asm
0x18018da80  mov     rax, rsp
0x18018da83  mov     [rax+10h], rbx
0x18018da87  mov     [rax+18h], rsi
0x18018da8b  mov     [rax+20h], rdi
0x18018da8f  mov     [rax+8], rcx
0x18018da93  push    r14
0x18018da95  sub     rsp, 40h
0x18018da99  mov     ebx, r8d
0x18018da9c  mov     rdi, rdx
0x18018da9f  mov     rsi, rcx
0x18018daa2  mov     dword ptr [rcx+10h], 1
0x18018daa9  lea     rax, ??_7CFileStream@FileSystem@RepoMan@@6BIStream@@@; const RepoMan::FileSystem::CFileStream::`vftable'{for `IStream'}
0x18018dab0  mov     [rcx], rax
0x18018dab3  lea     rax, ??_7CFileStream@FileSystem@RepoMan@@6B?$QIHelper@UIStreamSideChannel@@@2@@; const RepoMan::FileSystem::CFileStream::`vftable'{for `RepoMan::QIHelper<IStreamSideChannel>'}
0x18018daba  mov     [rcx+8], rax
0x18018dabe  lea     r14, [rcx+18h]
0x18018dac2  mov     rcx, r14; lpWideCharStr
0x18018dac5  call    ?utf8_to_wstring@RepoMan@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; RepoMan::utf8_to_wstring(std::string const &)
0x18018daca  nop
0x18018dacb  mov     [rsi+38h], ebx
0x18018dace  mov     rcx, rdi
0x18018dad1  call    ?CanBeSigned@FileSystem@RepoMan@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; RepoMan::FileSystem::CanBeSigned(std::string const &)
0x18018dad6  mov     [rsi+3Ch], al
0x18018dad9  xor     r11d, r11d
0x18018dadc  mov     [rsi+48h], r11
0x18018dae0  mov     [rsi+50h], r11
0x18018dae4  mov     [rsi+58h], r11
0x18018dae8  mov     [rsi+60h], r11
0x18018daec  mov     edx, r11d
0x18018daef  mov     r10d, r11d
0x18018daf2  mov     ecx, r11d
0x18018daf5  mov     r9d, 80h
0x18018dafb  mov     r8d, [rsi+38h]
0x18018daff  test    r8d, r8d
0x18018db02  jz      short loc_18018DB39
0x18018db04  sub     r8d, 1
0x18018db08  jz      short loc_18018DB2D
0x18018db0a  sub     r8d, 1
0x18018db0e  jz      short loc_18018DB21
0x18018db10  cmp     r8d, 1
0x18018db14  jnz     short loc_18018DB51
0x18018db16  mov     edx, 0C0000000h
0x18018db1b  lea     ecx, [r11+4]
0x18018db1f  jmp     short loc_18018DB51
0x18018db21  mov     edx, 0C0000000h
0x18018db26  mov     ecx, 4
0x18018db2b  jmp     short loc_18018DB4D
0x18018db2d  mov     edx, 0C0000000h
0x18018db32  mov     ecx, 2
0x18018db37  jmp     short loc_18018DB51
0x18018db39  mov     edx, 80000000h; dwDesiredAccess
0x18018db3e  mov     ecx, 3
0x18018db43  lea     r10d, [rcx-2]
0x18018db47  mov     r9d, 8000080h
0x18018db4d  mov     [rsi+3Ch], r11b
0x18018db51  cmp     qword ptr [r14+18h], 7
0x18018db56  jbe     short loc_18018DB5B
0x18018db58  mov     r14, [r14]
0x18018db5b  mov     [rsp+48h+hTemplateFile], r11; hTemplateFile
0x18018db60  mov     [rsp+48h+dwFlagsAndAttributes], r9d; dwFlagsAndAttributes
0x18018db65  mov     [rsp+48h+dwCreationDisposition], ecx; dwCreationDisposition
0x18018db69  xor     r9d, r9d; lpSecurityAttributes
0x18018db6c  mov     r8d, r10d; dwShareMode
0x18018db6f  mov     rcx, r14; lpFileName
0x18018db72  call    cs:__imp_CreateFileW
0x18018db78  mov     [rsi+40h], rax
0x18018db7c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18018db80  jz      short loc_18018DBA4
0x18018db82  xor     ecx, ecx; dwErrCode
0x18018db84  call    cs:__imp_SetLastError
0x18018db8a  nop
0x18018db8b  mov     rax, rsi
0x18018db8e  mov     rbx, [rsp+48h+arg_8]
0x18018db93  mov     rsi, [rsp+48h+arg_10]
0x18018db98  mov     rdi, [rsp+48h+arg_18]
0x18018db9d  add     rsp, 40h
0x18018dba1  pop     r14
0x18018dba3  retn
0x18018dba4  call    cs:__imp_GetLastError
0x18018dbaa  nop
0x18018dbab  mov     r9d, eax
0x18018dbae  lea     r8, aCreatefileFail; "CreateFile failed."
0x18018dbb5  mov     ecx, 178h
0x18018dbba  call    ??$RaiseException@VWin32Exception@RepoMan@@K@RepoMan@@YAXHQEBDPEBDKW4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Win32Exception,ulong>(int,char const * const,char const *,ulong,RepoMan::ILogger::Verbosity)
```
