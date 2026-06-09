# ScriptDiagnostics::EdpServer::DevToolsManager::GetEdgeDevToolsResourceString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180073cfc`
- end: `0x180073eb4`
- name: `?GetEdgeDevToolsResourceString@DevToolsManager@EdpServer@ScriptDiagnostics@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV45@@Z`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180021ca0`

## callees

- `0x180018b30`
- `0x18001b178`
- `0x180020bec`
- `0x180023964`
- `0x18002b530`
- `0x18002b5a0`
- `0x180073af4`
- `0x180073b4c`
- `0x180073b88`
- `0x180073cfc`
- `0x180073ed8`
- `0x180074334`

## import_xrefs

- `msvcp_win!??0?$codecvt@GDU_Mbstatet@@@std@@QEAA@_K@Z` at `0x180073e3e`
- `msvcp_win!??0?$codecvt@GDU_Mbstatet@@@std@@QEAA@_K@Z` at `0x180073e3e`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180073dff`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180073dff`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180073dce`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180073dce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180073d2a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180073d2a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180073daa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180073daa`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180073d82`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180073d82`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180073d58`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180073d58`

## string_xrefs

- `0x180073d23`: `edgehtml.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 ScriptDiagnostics::EdpServer::DevToolsManager::GetEdgeDevToolsResourceString()
{
  HMODULE Library; // rax
  HMODULE v1; // rbx
  const WCHAR *v2; // rdx
  HRSRC ResourceW; // rax
  const char *v4; // r9
  HRSRC v5; // rdi
  DWORD v6; // eax
  const char *v7; // r9
  __int64 v8; // rsi
  HGLOBAL Resource; // rax
  const char *v10; // r9
  char *v11; // rdi
  const char *v12; // r9
  _QWORD *v13; // rbx
  __int64 v14; // rax
  _QWORD v16[2]; // [rsp+20h] [rbp-89h] BYREF
  _QWORD v17[4]; // [rsp+30h] [rbp-79h] BYREF
  _BYTE v18[32]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v19[40]; // [rsp+70h] [rbp-39h] BYREF
  __int16 v20; // [rsp+98h] [rbp-11h]
  char v21; // [rsp+9Ah] [rbp-Fh]
  _BYTE v22[32]; // [rsp+B0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  Library = LoadLibraryExW(L"edgehtml.dll", 0, 0x800u);
  v1 = Library;
  v16[0] = Library;
  v2 = (const WCHAR *)&lpName;
  if ( (unsigned __int64)qword_1800B7038 > 7 )
    v2 = lpName;
  ResourceW = FindResourceW(Library, v2, (LPCWSTR)0xA);
  v5 = ResourceW;
  if ( !ResourceW )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecoreuap\\inetcore\\lib\\diagnostics\\edp\\devtoolsmanager.cpp",
      v4);
  v6 = SizeofResource(v1, ResourceW);
  v8 = v6;
  if ( !v6 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecoreuap\\inetcore\\lib\\diagnostics\\edp\\devtoolsmanager.cpp",
      v7);
  Resource = LoadResource(v1, v5);
  if ( !Resource )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecoreuap\\inetcore\\lib\\diagnostics\\edp\\devtoolsmanager.cpp",
      v10);
  v11 = (char *)LockResource(Resource);
  if ( !v11 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x13E,
      (unsigned int)"onecoreuap\\inetcore\\lib\\diagnostics\\edp\\devtoolsmanager.cpp",
      v12);
  v17[0] = &std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
  v17[3] = std::locale::_Init(1);
  std::string::string(v18);
  std::wstring::wstring(v19);
  v20 = 0;
  v21 = 0;
  v13 = operator new(0x40u);
  v16[1] = v13;
  std::codecvt<unsigned short,char,_Mbstatet>::codecvt<unsigned short,char,_Mbstatet>(v13, 0);
  *v13 = &std::codecvt_utf8<unsigned short,1114111,0>::`vftable';
  std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::_Init(
    v17,
    v13);
  v14 = std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
          v17,
          v22,
          v11,
          &v11[v8],
          v16[0]);
  std::wstring::operator=(&qword_1800B70A0, v14);
  std::wstring::_Tidy_deallocate(v22);
  std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v17);
  return wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v16);
}

```

## disassembly

```asm
0x180073cfc  push    rbp
0x180073cfe  push    rbx
0x180073cff  push    rsi
0x180073d00  push    rdi
0x180073d01  lea     rbp, [rsp-3Fh]
0x180073d06  sub     rsp, 0E8h
0x180073d0d  mov     rax, cs:__security_cookie
0x180073d14  xor     rax, rsp
0x180073d17  mov     [rbp+57h+var_30], rax
0x180073d1b  xor     edx, edx; hFile
0x180073d1d  mov     r8d, 800h; dwFlags
0x180073d23  lea     rcx, aEdgehtmlDll; "edgehtml.dll"
0x180073d2a  call    cs:__imp_LoadLibraryExW
0x180073d30  mov     rbx, rax
0x180073d33  mov     [rsp+100h+var_E0], rax
0x180073d38  lea     rdx, lpName
0x180073d3f  cmp     cs:qword_1800B7038, 7
0x180073d47  cmova   rdx, cs:lpName; lpName
0x180073d4f  mov     r8d, 0Ah; lpType
0x180073d55  mov     rcx, rax; hModule
0x180073d58  call    cs:__imp_FindResourceW
0x180073d5e  mov     rdi, rax
0x180073d61  mov     rcx, [rbp+5Fh]; this
0x180073d65  test    rax, rax
0x180073d68  jnz     short loc_180073D7C
0x180073d6a  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\lib\\diagnostics"...
0x180073d71  mov     edx, 136h; void *
0x180073d76  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180073d7c  mov     rdx, rdi; hResInfo
0x180073d7f  mov     rcx, rbx; hModule
0x180073d82  call    cs:__imp_SizeofResource
0x180073d88  mov     esi, eax
0x180073d8a  mov     rcx, [rbp+5Fh]; this
0x180073d8e  test    eax, eax
0x180073d90  jnz     short loc_180073DA4
0x180073d92  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\lib\\diagnostics"...
0x180073d99  mov     edx, 13Ah; void *
0x180073d9e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180073da4  mov     rdx, rdi; hResInfo
0x180073da7  mov     rcx, rbx; hModule
0x180073daa  call    cs:__imp_LoadResource
0x180073db0  mov     rcx, [rbp+5Fh]; this
0x180073db4  test    rax, rax
0x180073db7  jnz     short loc_180073DCB
0x180073db9  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\lib\\diagnostics"...
0x180073dc0  mov     edx, 13Ch; void *
0x180073dc5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180073dcb  mov     rcx, rax; hResData
0x180073dce  call    cs:__imp_LockResource
0x180073dd4  mov     rdi, rax
0x180073dd7  mov     rcx, [rbp+5Fh]; this
0x180073ddb  test    rax, rax
0x180073dde  jnz     short loc_180073DF2
0x180073de0  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\lib\\diagnostics"...
0x180073de7  mov     edx, 13Eh; void *
0x180073dec  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180073df2  lea     rax, ??_7?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x180073df9  mov     [rbp+57h+var_D0], rax
0x180073dfd  mov     cl, 1
0x180073dff  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180073e05  mov     [rbp+57h+var_B8], rax
0x180073e09  lea     rcx, [rbp+57h+var_B0]
0x180073e0d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180073e12  nop
0x180073e13  lea     rcx, [rbp+57h+var_90]
0x180073e17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180073e1c  nop
0x180073e1d  mov     [rbp+57h+var_68], 0
0x180073e23  mov     [rbp+57h+var_66], 0
0x180073e27  mov     ecx, 40h ; '@'; Size
0x180073e2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180073e31  mov     rbx, rax
0x180073e34  mov     [rsp+100h+var_D8], rax
0x180073e39  xor     edx, edx
0x180073e3b  mov     rcx, rax
0x180073e3e  call    cs:__imp_??0?$codecvt@GDU_Mbstatet@@@std@@QEAA@_K@Z; std::codecvt<ushort,char,_Mbstatet>::codecvt<ushort,char,_Mbstatet>(unsigned __int64)
0x180073e44  lea     rax, ??_7?$codecvt_utf8@G$0BAPPPP@$0A@@std@@6B@; const std::codecvt_utf8<ushort,1114111,0>::`vftable'
0x180073e4b  mov     [rbx], rax
0x180073e4e  mov     rdx, rbx
0x180073e51  lea     rcx, [rbp+57h+var_D0]
0x180073e55  call    ?_Init@?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@AEAAXPEBV?$codecvt_utf8@G$0BAPPPP@$0A@@2@@Z; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::_Init(std::codecvt_utf8<ushort,1114111,0> const *)
0x180073e5a  nop
0x180073e5b  lea     r9, [rdi+rsi]
0x180073e5f  mov     r8, rdi
0x180073e62  lea     rdx, [rbp+57h+var_50]
0x180073e66  lea     rcx, [rbp+57h+var_D0]
0x180073e6a  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x180073e6f  mov     rdx, rax
0x180073e72  lea     rcx, qword_1800B70A0
0x180073e79  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180073e7e  lea     rcx, [rbp+57h+var_50]
0x180073e82  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073e87  nop
0x180073e88  lea     rcx, [rbp+57h+var_D0]
0x180073e8c  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180073e91  nop
0x180073e92  lea     rcx, [rsp+100h+var_E0]
0x180073e97  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180073e9c  mov     rcx, [rbp+57h+var_30]
0x180073ea0  xor     rcx, rsp; StackCookie
0x180073ea3  call    __security_check_cookie
0x180073ea8  add     rsp, 0E8h
0x180073eaf  pop     rdi
0x180073eb0  pop     rsi
0x180073eb1  pop     rbx
0x180073eb2  pop     rbp
0x180073eb3  retn
```
