# Windows::Internal::WebView::CoreWebViewRACProfileStatics::LoadRACProfileMap(ushort const *)

- ea: `0x18000a290`
- end: `0x18000a511`
- name: `?LoadRACProfileMap@CoreWebViewRACProfileStatics@WebView@Internal@Windows@@AEAAXPEBG@Z`
- size: `641`
- prototype: `void(Windows::Internal::WebView::CoreWebViewRACProfileStatics *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18001aad0`

## callees

- `0x18000a290`
- `0x18000a518`
- `0x18002b530`
- `0x18002c5b0`
- `0x180035b88`
- `0x180036418`
- `0x180036984`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a305`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a305`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4bb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000a2fb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000a2fb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000a4b1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000a4b1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a452`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a452`

## pseudocode

```c
void __fastcall Windows::Internal::WebView::CoreWebViewRACProfileStatics::LoadRACProfileMap(
        HANDLE *this,
        const unsigned __int16 *a2)
{
  unsigned __int64 v4; // rdx
  signed int LastError; // eax
  bool v6; // sf
  int v7; // eax
  unsigned __int64 v8; // rdx
  int v9; // eax
  unsigned __int64 v10; // rdx
  int v11; // eax
  unsigned __int64 v12; // rdx
  int v13; // eax
  unsigned __int64 v14; // rdx
  int v15; // eax
  HANDLE FileW; // rax
  DWORD v17; // eax
  signed int v18; // eax
  bool v19; // sf
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  _QWORD v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Dst[264]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  memset_0(FileName, 0, 0x208u);
  memset_0(Dst, 0, 0x208u);
  if ( !ExpandEnvironmentStringsW(L"%LOCALAPPDATA%", Dst, 0x104u) )
  {
    LastError = GetLastError();
    v6 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v6 = LastError < 0;
    }
    if ( v6 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewracprofilestatics.cpp",
        (const char *)(unsigned int)LastError,
        dwCreationDisposition);
  }
  v7 = StringCchCatW(FileName, v4, Dst);
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewracprofilestatics.cpp",
      (const char *)(unsigned int)v7,
      dwCreationDisposition);
  v9 = StringCchCatW(FileName, v8, L"\\Packages\\");
  if ( v9 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewracprofilestatics.cpp",
      (const char *)(unsigned int)v9,
      dwCreationDisposition);
  v11 = StringCchCatW(FileName, v10, a2);
  if ( v11 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewracprofilestatics.cpp",
      (const char *)(unsigned int)v11,
      dwCreationDisposition);
  v13 = StringCchCatW(FileName, v12, L"\\AppData\\");
  if ( v13 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewracprofilestatics.cpp",
      (const char *)(unsigned int)v13,
      dwCreationDisposition);
  v15 = StringCchCatW(FileName, v14, L"RACNameMap");
  if ( v15 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewracprofilestatics.cpp",
      (const char *)(unsigned int)v15,
      dwCreationDisposition);
  FileW = CreateFileW(FileName, 0xC0000000, 2u, 0, 4u, 0xA0000000, 0);
  v22[0] = FileW;
  if ( this + 13 != v22 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      this + 13,
      FileW);
    v22[0] = 0;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v22);
  v17 = GetLastError();
  if ( v17 != 183 && v17 && !ReadFile(this[13], this + 14, 0x10u, 0, 0) )
  {
    v18 = GetLastError();
    v19 = v18 < 0;
    if ( v18 > 0 )
    {
      v18 = (unsigned __int16)v18 | 0x80070000;
      v19 = v18 < 0;
    }
    if ( v19 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x7F,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewracprofilestatics.cpp",
        (const char *)(unsigned int)v18,
        dwCreationDispositiona);
  }
}

```

## disassembly

```asm
0x18000a290  mov     [rsp-8+arg_10], rbx
0x18000a295  mov     [rsp-8+arg_18], rdi
0x18000a29a  push    rbp
0x18000a29b  lea     rbp, [rsp-380h]
0x18000a2a3  sub     rsp, 480h
0x18000a2aa  mov     rax, cs:__security_cookie
0x18000a2b1  xor     rax, rsp
0x18000a2b4  mov     [rbp+380h+var_10], rax
0x18000a2bb  mov     rbx, rdx
0x18000a2be  mov     rdi, rcx
0x18000a2c1  xor     edx, edx; Val
0x18000a2c3  lea     rcx, [rsp+480h+FileName]; void *
0x18000a2c8  mov     r8d, 208h; Size
0x18000a2ce  call    memset_0
0x18000a2d3  xor     edx, edx; Val
0x18000a2d5  lea     rcx, [rbp+380h+Dst]; void *
0x18000a2dc  mov     r8d, 208h; Size
0x18000a2e2  call    memset_0
0x18000a2e7  mov     r8d, 104h; nSize
0x18000a2ed  lea     rdx, [rbp+380h+Dst]; lpDst
0x18000a2f4  lea     rcx, Src; "%LOCALAPPDATA%"
0x18000a2fb  call    cs:__imp_ExpandEnvironmentStringsW
0x18000a301  test    eax, eax
0x18000a303  jnz     short loc_18000A337
0x18000a305  call    cs:__imp_GetLastError
0x18000a30b  test    eax, eax
0x18000a30d  jle     short loc_18000A319
0x18000a30f  movzx   eax, ax
0x18000a312  or      eax, 80070000h
0x18000a317  test    eax, eax
0x18000a319  jns     short loc_18000A337
0x18000a31b  mov     rcx, [rbp+388h]; this
0x18000a322  lea     r8, aOnecoreuapInet_35; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18000a329  mov     r9d, eax; char *
0x18000a32c  mov     edx, 62h ; 'b'; void *
0x18000a331  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000a337  lea     r8, [rbp+380h+Dst]; unsigned __int16 *
0x18000a33e  lea     rcx, [rsp+480h+FileName]; unsigned __int16 *
0x18000a343  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a348  test    eax, eax
0x18000a34a  jns     short loc_18000A368
0x18000a34c  mov     rcx, [rbp+388h]; this
0x18000a353  lea     r8, aOnecoreuapInet_35; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18000a35a  mov     r9d, eax; char *
0x18000a35d  mov     edx, 65h ; 'e'; void *
0x18000a362  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000a368  lea     r8, aPackages; "\\Packages\\"
0x18000a36f  lea     rcx, [rsp+480h+FileName]; unsigned __int16 *
0x18000a374  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a379  test    eax, eax
0x18000a37b  jns     short loc_18000A399
0x18000a37d  mov     rcx, [rbp+388h]; this
0x18000a384  lea     r8, aOnecoreuapInet_35; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18000a38b  mov     r9d, eax; char *
0x18000a38e  mov     edx, 66h ; 'f'; void *
0x18000a393  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000a399  mov     r8, rbx; unsigned __int16 *
0x18000a39c  lea     rcx, [rsp+480h+FileName]; unsigned __int16 *
0x18000a3a1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a3a6  test    eax, eax
0x18000a3a8  jns     short loc_18000A3C6
0x18000a3aa  mov     rcx, [rbp+388h]; this
0x18000a3b1  lea     r8, aOnecoreuapInet_35; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18000a3b8  mov     r9d, eax; char *
0x18000a3bb  mov     edx, 67h ; 'g'; void *
0x18000a3c0  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000a3c6  lea     r8, aAppdata; "\\AppData\\"
0x18000a3cd  lea     rcx, [rsp+480h+FileName]; unsigned __int16 *
0x18000a3d2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a3d7  test    eax, eax
0x18000a3d9  jns     short loc_18000A3F7
0x18000a3db  mov     rcx, [rbp+388h]; this
0x18000a3e2  lea     r8, aOnecoreuapInet_35; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18000a3e9  mov     r9d, eax; char *
0x18000a3ec  mov     edx, 68h ; 'h'; void *
0x18000a3f1  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000a3f7  lea     r8, aRacnamemap; "RACNameMap"
0x18000a3fe  lea     rcx, [rsp+480h+FileName]; unsigned __int16 *
0x18000a403  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a408  test    eax, eax
0x18000a40a  jns     short loc_18000A428
0x18000a40c  mov     rcx, [rbp+388h]; this
0x18000a413  lea     r8, aOnecoreuapInet_35; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18000a41a  mov     r9d, eax; char *
0x18000a41d  mov     edx, 69h ; 'i'; void *
0x18000a422  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000a428  xor     r9d, r9d; lpSecurityAttributes
0x18000a42b  mov     [rsp+480h+hTemplateFile], 0; hTemplateFile
0x18000a434  mov     [rsp+480h+dwFlagsAndAttributes], 0A0000000h; dwFlagsAndAttributes
0x18000a43c  lea     rcx, [rsp+480h+FileName]; lpFileName
0x18000a441  mov     edx, 0C0000000h; dwDesiredAccess
0x18000a446  mov     [rsp+480h+dwCreationDisposition], 4; dwCreationDisposition
0x18000a44e  lea     r8d, [r9+2]; dwShareMode
0x18000a452  call    cs:__imp_CreateFileW
0x18000a458  lea     rcx, [rsp+480h+var_440]
0x18000a45d  mov     [rsp+480h+var_440], rax
0x18000a462  lea     rbx, [rdi+68h]
0x18000a466  cmp     rbx, rcx
0x18000a469  jz      short loc_18000A47F
0x18000a46b  mov     rdx, rax
0x18000a46e  mov     rcx, rbx
0x18000a471  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000a476  mov     [rsp+480h+var_440], 0
0x18000a47f  lea     rcx, [rsp+480h+var_440]
0x18000a484  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a489  call    cs:__imp_GetLastError
0x18000a48f  cmp     eax, 0B7h
0x18000a494  jz      short loc_18000A4ED
0x18000a496  test    eax, eax
0x18000a498  jz      short loc_18000A4ED
0x18000a49a  mov     rcx, [rbx]; hFile
0x18000a49d  lea     rdx, [rdi+70h]; lpBuffer
0x18000a4a1  xor     r9d, r9d; lpNumberOfBytesRead
0x18000a4a4  mov     qword ptr [rsp+480h+dwCreationDisposition], 0; int
0x18000a4ad  lea     r8d, [r9+10h]; nNumberOfBytesToRead
0x18000a4b1  call    cs:__imp_ReadFile
0x18000a4b7  test    eax, eax
0x18000a4b9  jnz     short loc_18000A4ED
0x18000a4bb  call    cs:__imp_GetLastError
0x18000a4c1  test    eax, eax
0x18000a4c3  jle     short loc_18000A4CF
0x18000a4c5  movzx   eax, ax
0x18000a4c8  or      eax, 80070000h
0x18000a4cd  test    eax, eax
0x18000a4cf  jns     short loc_18000A4ED
0x18000a4d1  mov     rcx, [rbp+388h]; this
0x18000a4d8  lea     r8, aOnecoreuapInet_35; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18000a4df  mov     r9d, eax; char *
0x18000a4e2  mov     edx, 7Fh; void *
0x18000a4e7  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000a4ed  mov     rcx, [rbp+380h+var_10]
0x18000a4f4  xor     rcx, rsp; StackCookie
0x18000a4f7  call    __security_check_cookie
0x18000a4fc  lea     r11, [rsp+480h+var_s0]
0x18000a504  mov     rbx, [r11+20h]
0x18000a508  mov     rdi, [r11+28h]
0x18000a50c  mov     rsp, r11
0x18000a50f  pop     rbp
0x18000a510  retn
```
