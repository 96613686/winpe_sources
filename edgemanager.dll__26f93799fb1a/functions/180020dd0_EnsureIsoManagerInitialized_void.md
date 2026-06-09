# EnsureIsoManagerInitialized(void)

- ea: `0x180020dd0`
- end: `0x180020e32`
- name: `?EnsureIsoManagerInitialized@@YAXXZ`
- size: `98`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180020c34`

## callees

- `0x180018b30`
- `0x180020dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020e07`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020e07`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180020ddb`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180020ddb`

## string_xrefs

- `0x180020dd4`: `EdgeManager.dll`

## pseudocode

```c
void EnsureIsoManagerInitialized(void)
{
  HMODULE LibraryW; // rax
  const char *v1; // r9
  void (*ProcAddress)(void); // rax
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  LibraryW = LoadLibraryW(L"EdgeManager.dll");
  if ( !LibraryW )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webdriver\\webdriverdispatcher.cxx",
      v1);
  ProcAddress = (void (*)(void))GetProcAddress(LibraryW, "EnsureWebDriverForWebViewHost");
  if ( !ProcAddress )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xBC,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webdriver\\webdriverdispatcher.cxx",
      v3);
  ProcAddress();
}

```

## disassembly

```asm
0x180020dd0  sub     rsp, 28h
0x180020dd4  lea     rcx, aEdgemanagerDll_1; "EdgeManager.dll"
0x180020ddb  call    cs:__imp_LoadLibraryW
0x180020de1  test    rax, rax
0x180020de4  jnz     short loc_180020DFD
0x180020de6  mov     rcx, [rsp+28h]; this
0x180020deb  lea     r8, aOnecoreuapInet_25; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180020df2  mov     edx, 0B6h; void *
0x180020df7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180020dfd  lea     rdx, aEnsurewebdrive_0; "EnsureWebDriverForWebViewHost"
0x180020e04  mov     rcx, rax; hModule
0x180020e07  call    cs:__imp_GetProcAddress
0x180020e0d  test    rax, rax
0x180020e10  jnz     short loc_180020E29
0x180020e12  mov     rcx, [rsp+28h]; this
0x180020e17  lea     r8, aOnecoreuapInet_25; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180020e1e  mov     edx, 0BCh; void *
0x180020e23  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180020e29  add     rsp, 28h
0x180020e2d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
