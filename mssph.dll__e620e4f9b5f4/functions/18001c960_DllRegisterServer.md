# DllRegisterServer

- ea: `0x18001c960`
- end: `0x18001caa5`
- name: `DllRegisterServer`
- size: `325`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007158`
- `0x18000fcd0`
- `0x180017670`
- `0x18001a73c`
- `0x18001c960`
- `0x18001ceb8`
- `0x18001d200`
- `0x18001e9ec`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ca04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ca04`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c9f4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c9f4`

## string_xrefs

- `0x18001c989`: `ProtocolHandlers`
- `0x18001c9a3`: `ProtocolHandlers`
- `0x18001ca0a`: `ConfigHelpers`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  const wchar_t *v0; // rdx
  unsigned int v1; // r8d
  DWORD v2; // ecx
  LSTATUS v3; // eax
  __int64 v4; // rbx
  HRESULT result; // eax
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax
  _BYTE v7[176]; // [rsp+40h] [rbp-198h] BYREF
  HKEY hKey; // [rsp+F0h] [rbp-E8h]
  _BYTE v9[192]; // [rsp+100h] [rbp-D8h] BYREF
  void *retaddr; // [rsp+1D8h] [rbp+0h]

  try
  {
    CSearchRootRegistry::CSearchRootRegistry((CSearchRootRegistry *)v9, v0, v1);
    CRegistry::CreateSubKey((CRegistry *)v9, L"ProtocolHandlers");
    CRegistry::CRegistry((CRegistry *)v7, (struct CRegistry *)v9, L"ProtocolHandlers", 0xF003Fu);
    if ( hKey )
    {
      v3 = RegSetValueExW(hKey, L"File", 0, 1u, L"Search.FileHandler.1", 0x2Au);
      if ( v3 )
        v2 = v3;
      else
        v2 = 0;
    }
    else
    {
      v2 = 6;
    }
    SetLastError(v2);
    CRegistry::CreateSubKey((CRegistry *)v7, L"ConfigHelpers");
    CRegistry::~CRegistry((CRegistry *)v7);
    CRegistry::~CRegistry((CRegistry *)v9);
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      90,
      "onecoreuap\\base\\appmodel\\search\\mssph\\dll\\mssph.cxx");
  }
  v4 = qword_1800364D8;
  if ( qword_1800364D8 )
  {
    while ( *(_QWORD *)v4 )
    {
      result = (*(__int64 (__fastcall **)(__int64))(v4 + 8))(1);
      if ( result < 0 )
        return result;
      v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v4 + 56))();
      result = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v4, v6, 1);
      if ( result < 0 )
        return result;
      v4 += 72;
    }
  }
  return ATL::CAtlModuleT<ATL::CComModule>::RegisterServer();
}

```

## disassembly

```asm
0x18001c960  push    rbx
0x18001c962  sub     rsp, 1D0h
0x18001c969  mov     rax, cs:__security_cookie
0x18001c970  xor     rax, rsp
0x18001c973  mov     [rsp+1D8h+var_18], rax
0x18001c97b  lea     rcx, [rsp+1D8h+var_D8]; this
0x18001c983  call    ??0CSearchRootRegistry@@QEAA@PEB_WK@Z; CSearchRootRegistry::CSearchRootRegistry(wchar_t const *,ulong)
0x18001c988  nop
0x18001c989  lea     rdx, aProtocolhandle; "ProtocolHandlers"
0x18001c990  lea     rcx, [rsp+1D8h+var_D8]; this
0x18001c998  call    ?CreateSubKey@CRegistry@@UEAAHPEB_W@Z; CRegistry::CreateSubKey(wchar_t const *)
0x18001c99d  mov     r9d, 0F003Fh; unsigned int
0x18001c9a3  lea     r8, aProtocolhandle; "ProtocolHandlers"
0x18001c9aa  lea     rdx, [rsp+1D8h+var_D8]; struct CRegistry *
0x18001c9b2  lea     rcx, [rsp+1D8h+var_198]; this
0x18001c9b7  call    ??0CRegistry@@QEAA@PEAV0@PEB_WK@Z; CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)
0x18001c9bc  mov     rcx, [rsp+1D8h+hKey]; hKey
0x18001c9c4  test    rcx, rcx
0x18001c9c7  jnz     short loc_18001C9D0
0x18001c9c9  mov     ecx, 6
0x18001c9ce  jmp     short loc_18001CA04
0x18001c9d0  mov     [rsp+1D8h+cbData], 2Ah ; '*'; cbData
0x18001c9d8  lea     rax, Data; "Search.FileHandler.1"
0x18001c9df  mov     [rsp+1D8h+lpData], rax; lpData
0x18001c9e4  mov     r9d, 1; dwType
0x18001c9ea  xor     r8d, r8d; Reserved
0x18001c9ed  lea     rdx, aFile_0; "File"
0x18001c9f4  call    cs:__imp_RegSetValueExW
0x18001c9fa  test    eax, eax
0x18001c9fc  jz      short loc_18001CA02
0x18001c9fe  mov     ecx, eax
0x18001ca00  jmp     short loc_18001CA04
0x18001ca02  xor     ecx, ecx; dwErrCode
0x18001ca04  call    cs:__imp_SetLastError
0x18001ca0a  lea     rdx, aConfighelpers; "ConfigHelpers"
0x18001ca11  lea     rcx, [rsp+1D8h+var_198]; this
0x18001ca16  call    ?CreateSubKey@CRegistry@@UEAAHPEB_W@Z; CRegistry::CreateSubKey(wchar_t const *)
0x18001ca1b  lea     rcx, [rsp+1D8h+var_198]; this
0x18001ca20  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18001ca25  nop
0x18001ca26  lea     rcx, [rsp+1D8h+var_D8]; this
0x18001ca2e  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18001ca33  nop
0x18001ca34  jmp     short loc_18001CA3E
0x18001ca36  mov     eax, [rsp+1D8h+var_1A8]
0x18001ca3a  test    eax, eax
0x18001ca3c  js      short loc_18001CA8C
0x18001ca3e  mov     rbx, cs:qword_1800364D8
0x18001ca45  test    rbx, rbx
0x18001ca48  jz      short loc_18001CA86
0x18001ca4a  jmp     short loc_18001CA80
0x18001ca4c  mov     ecx, 1
0x18001ca51  mov     rax, [rbx+8]
0x18001ca55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca5a  test    eax, eax
0x18001ca5c  js      short loc_18001CA8C
0x18001ca5e  mov     rax, [rbx+38h]
0x18001ca62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca67  mov     r8d, 1; int
0x18001ca6d  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18001ca70  mov     rcx, [rbx]; rguid
0x18001ca73  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18001ca78  test    eax, eax
0x18001ca7a  js      short loc_18001CA8C
0x18001ca7c  add     rbx, 48h ; 'H'
0x18001ca80  cmp     qword ptr [rbx], 0
0x18001ca84  jnz     short loc_18001CA4C
0x18001ca86  call    ?RegisterServer@?$CAtlModuleT@VCComModule@ATL@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<ATL::CComModule>::RegisterServer(int,_GUID const *)
0x18001ca8b  nop
0x18001ca8c  mov     rcx, [rsp+1D8h+var_18]
0x18001ca94  xor     rcx, rsp; StackCookie
0x18001ca97  call    __security_check_cookie
0x18001ca9c  add     rsp, 1D0h
0x18001caa3  pop     rbx
0x18001caa4  retn
```
