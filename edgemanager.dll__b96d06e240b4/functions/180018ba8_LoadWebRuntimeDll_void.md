# LoadWebRuntimeDll(void)

- ea: `0x180018ba8`
- end: `0x180018c03`
- name: `?LoadWebRuntimeDll@@YA_NXZ`
- size: `91`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800051c0`
- `0x180018a18`

## callees

- `0x180018ba8`
- `0x180021270`
- `0x1800212f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018bdb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018bdb`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180018bb9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180018bb9`

## string_xrefs

- `0x180018bb2`: `WebRuntimeManager.dll`

## pseudocode

```c
bool LoadWebRuntimeDll(void)
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rdi
  HMODULE v2; // rbx
  char v4; // [rsp+30h] [rbp+8h] BYREF

  LibraryW = LoadLibraryW(L"WebRuntimeManager.dll");
  v1 = hLibModule;
  v2 = LibraryW;
  if ( hLibModule )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v4);
    FreeLibrary(v1);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v4);
  }
  hLibModule = v2;
  return v2 != 0;
}

```

## disassembly

```asm
0x180018ba8  mov     [rsp+arg_8], rbx
0x180018bad  push    rdi
0x180018bae  sub     rsp, 20h
0x180018bb2  lea     rcx, aWebruntimemana; "WebRuntimeManager.dll"
0x180018bb9  call    cs:__imp_LoadLibraryW
0x180018bbf  mov     rdi, cs:hLibModule
0x180018bc6  mov     rbx, rax
0x180018bc9  test    rdi, rdi
0x180018bcc  jz      short loc_180018BEB
0x180018bce  lea     rcx, [rsp+28h+arg_0]; this
0x180018bd3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180018bd8  mov     rcx, rdi; hLibModule
0x180018bdb  call    cs:__imp_FreeLibrary
0x180018be1  lea     rcx, [rsp+28h+arg_0]; this
0x180018be6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180018beb  test    rbx, rbx
0x180018bee  mov     cs:hLibModule, rbx
0x180018bf5  mov     rbx, [rsp+28h+arg_8]
0x180018bfa  setnz   al
0x180018bfd  add     rsp, 20h
0x180018c01  pop     rdi
0x180018c02  retn
```
