# LoadNetshFunctions(void)

- ea: `0x18000880c`
- end: `0x180008917`
- name: `?LoadNetshFunctions@@YAKXZ`
- size: `267`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180008730`

## callees

- `0x18000880c`
- `0x18000b4a4`
- `0x18000c924`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008822`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008822`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800088e6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008904`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800088e6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008904`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008858`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008879`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000889a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800088bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008858`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008879`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000889a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800088bb`

## string_xrefs

- `0x18000883a`: `onecore\net\netprofiles\service\src\public\dll\netshhelper.cpp`
- `0x1800088d5`: `onecore\net\netprofiles\service\src\public\dll\netshhelper.cpp`

## pseudocode

```c
__int64 LoadNetshFunctions(void)
{
  HMODULE Library; // rax
  const char *v1; // r9
  HMODULE v2; // rbx
  const char *v4; // r9
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int LastError; // edi
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hLibModule; // [rsp+30h] [rbp+8h] BYREF

  Library = LoadLibraryExW(L"netsh.exe", 0, 0);
  hLibModule = Library;
  v2 = Library;
  if ( !Library )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1E,
             (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\dll\\netshhelper.cpp",
             v1);
  g_netshRegisterContext = (unsigned int (*)(const struct _NS_CONTEXT_ATTRIBUTES *))GetProcAddress(
                                                                                      Library,
                                                                                      "RegisterContext");
  if ( !g_netshRegisterContext )
  {
    v5 = 33;
LABEL_11:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v5,
                  (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\dll\\netshhelper.cpp",
                  v4);
    FreeLibrary(v2);
    return LastError;
  }
  g_netshRegisterHelper = (unsigned int (*)(const struct _GUID *, const struct _NS_HELPER_ATTRIBUTES *))GetProcAddress(v2, "RegisterHelper");
  if ( !g_netshRegisterHelper )
  {
    v5 = 35;
    goto LABEL_11;
  }
  g_netshPrintMessageFromModule = (unsigned int (*)(void *, unsigned int, ...))GetProcAddress(
                                                                                 v2,
                                                                                 "PrintMessageFromModule");
  if ( !g_netshPrintMessageFromModule )
  {
    v5 = 38;
    goto LABEL_11;
  }
  g_netshMatchEnumTag = (unsigned int (*)(void *, const wchar_t *, unsigned int, const struct _TOKEN_VALUE *, unsigned int *))GetProcAddress(v2, "MatchEnumTag");
  if ( !g_netshMatchEnumTag )
  {
    v5 = 40;
    goto LABEL_11;
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::replace(
    v6,
    &hLibModule);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  return 0;
}

```

## disassembly

```asm
0x18000880c  mov     [rsp+arg_8], rbx
0x180008811  push    rdi
0x180008812  sub     rsp, 20h
0x180008816  xor     r8d, r8d; dwFlags
0x180008819  lea     rcx, LibFileName; "netsh.exe"
0x180008820  xor     edx, edx; hFile
0x180008822  call    cs:__imp_LoadLibraryExW
0x180008828  mov     [rsp+28h+hLibModule], rax
0x18000882d  mov     rbx, rax
0x180008830  test    rax, rax
0x180008833  jnz     short loc_18000884E
0x180008835  mov     rcx, [rsp+28h]; this
0x18000883a  lea     r8, aOnecoreNetNetp_12; "onecore\\net\\netprofiles\\service\\src"...
0x180008841  lea     edx, [rax+1Eh]; void *
0x180008844  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008849  jmp     loc_18000890C
0x18000884e  lea     rdx, aRegistercontex; "RegisterContext"
0x180008855  mov     rcx, rbx; hModule
0x180008858  call    cs:__imp_GetProcAddress
0x18000885e  mov     cs:?g_netshRegisterContext@@3P6AKPEBU_NS_CONTEXT_ATTRIBUTES@@@ZEA, rax; ulong (*g_netshRegisterContext)(_NS_CONTEXT_ATTRIBUTES const *)
0x180008865  test    rax, rax
0x180008868  jnz     short loc_18000886F
0x18000886a  lea     edx, [rax+21h]
0x18000886d  jmp     short loc_1800088D0
0x18000886f  lea     rdx, aRegisterhelper; "RegisterHelper"
0x180008876  mov     rcx, rbx; hModule
0x180008879  call    cs:__imp_GetProcAddress
0x18000887f  mov     cs:?g_netshRegisterHelper@@3P6AKPEBU_GUID@@PEBU_NS_HELPER_ATTRIBUTES@@@ZEA, rax; ulong (*g_netshRegisterHelper)(_GUID const *,_NS_HELPER_ATTRIBUTES const *)
0x180008886  test    rax, rax
0x180008889  jnz     short loc_180008890
0x18000888b  lea     edx, [rax+23h]
0x18000888e  jmp     short loc_1800088D0
0x180008890  lea     rdx, aPrintmessagefr; "PrintMessageFromModule"
0x180008897  mov     rcx, rbx; hModule
0x18000889a  call    cs:__imp_GetProcAddress
0x1800088a0  mov     cs:?g_netshPrintMessageFromModule@@3P6AKPEAXKZZEA, rax; ulong (*g_netshPrintMessageFromModule)(void *,ulong,...)
0x1800088a7  test    rax, rax
0x1800088aa  jnz     short loc_1800088B1
0x1800088ac  lea     edx, [rax+26h]
0x1800088af  jmp     short loc_1800088D0
0x1800088b1  lea     rdx, aMatchenumtag; "MatchEnumTag"
0x1800088b8  mov     rcx, rbx; hModule
0x1800088bb  call    cs:__imp_GetProcAddress
0x1800088c1  mov     cs:?g_netshMatchEnumTag@@3P6AKPEAXPEB_WKPEBU_TOKEN_VALUE@@PEAK@ZEA, rax; ulong (*g_netshMatchEnumTag)(void *,wchar_t const *,ulong,_TOKEN_VALUE const *,ulong *)
0x1800088c8  test    rax, rax
0x1800088cb  jnz     short loc_1800088F0
0x1800088cd  lea     edx, [rax+28h]; void *
0x1800088d0  mov     rcx, [rsp+28h]; this
0x1800088d5  lea     r8, aOnecoreNetNetp_12; "onecore\\net\\netprofiles\\service\\src"...
0x1800088dc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800088e1  mov     rcx, rbx; hLibModule
0x1800088e4  mov     edi, eax
0x1800088e6  call    cs:__imp_FreeLibrary
0x1800088ec  mov     eax, edi
0x1800088ee  jmp     short loc_18000890C
0x1800088f0  lea     rdx, [rsp+28h+hLibModule]
0x1800088f5  call    ?replace@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@IEAAX$$QEAV123@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::replace(wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>> &&)
0x1800088fa  mov     rcx, [rsp+28h+hLibModule]; hLibModule
0x1800088ff  test    rcx, rcx
0x180008902  jz      short loc_18000890A
0x180008904  call    cs:__imp_FreeLibrary
0x18000890a  xor     eax, eax
0x18000890c  mov     rbx, [rsp+28h+arg_8]
0x180008911  add     rsp, 20h
0x180008915  pop     rdi
0x180008916  retn
```
