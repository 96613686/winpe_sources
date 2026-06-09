# IsWindowsUpdateInternetAvailable(void)

- ea: `0x18000c398`
- end: `0x18000c401`
- name: `?IsWindowsUpdateInternetAvailable@@YAHXZ`
- size: `105`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18000ca40`

## callees

- `0x18000c398`
- `0x18000cff4`
- `0x180020820`
- `0x18003a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c3ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c3ed`

## string_xrefs

- `0x18000c39e`: `wudriver.dll`

## pseudocode

```c
__int64 IsWindowsUpdateInternetAvailable(void)
{
  HMODULE LibraryUsingFullPath; // rbx
  unsigned int v1; // ebx
  __int64 (*ProcAddress)(void); // rax
  HMODULE v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  LibraryUsingFullPath = (HMODULE)LoadLibraryUsingFullPath(L"wudriver.dll");
  NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(&v4);
  if ( LibraryUsingFullPath )
  {
    v4 = LibraryUsingFullPath;
    ProcAddress = GetProcAddress(LibraryUsingFullPath, "DownloadIsInternetAvailable");
    if ( ProcAddress )
    {
      v1 = ProcAddress();
      goto LABEL_4;
    }
  }
  else
  {
    v4 = 0;
  }
  v1 = 0;
LABEL_4:
  NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(&v4);
  return v1;
}

```

## disassembly

```asm
0x18000c398  push    rbx
0x18000c39a  sub     rsp, 20h
0x18000c39e  lea     rcx, aWudriverDll; "wudriver.dll"
0x18000c3a5  mov     [rsp+28h+arg_0], 0
0x18000c3ae  call    LoadLibraryUsingFullPath
0x18000c3b3  lea     rcx, [rsp+28h+arg_0]
0x18000c3b8  mov     rbx, rax
0x18000c3bb  call    ?Reset@?$TGenericSP@PEAUHINSTANCE__@@VTAutoHandleHMODULE@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(void)
0x18000c3c0  test    rbx, rbx
0x18000c3c3  jnz     short loc_18000C3DE
0x18000c3c5  mov     [rsp+28h+arg_0], rbx
0x18000c3ca  xor     ebx, ebx
0x18000c3cc  lea     rcx, [rsp+28h+arg_0]
0x18000c3d1  call    ?Reset@?$TGenericSP@PEAUHINSTANCE__@@VTAutoHandleHMODULE@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(void)
0x18000c3d6  mov     eax, ebx
0x18000c3d8  add     rsp, 20h
0x18000c3dc  pop     rbx
0x18000c3dd  retn
0x18000c3de  lea     rdx, aDownloadisinte; "DownloadIsInternetAvailable"
0x18000c3e5  mov     [rsp+28h+arg_0], rbx
0x18000c3ea  mov     rcx, rbx; hModule
0x18000c3ed  call    cs:__imp_GetProcAddress
0x18000c3f3  test    rax, rax
0x18000c3f6  jz      short loc_18000C3CA
0x18000c3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3fd  mov     ebx, eax
0x18000c3ff  jmp     short loc_18000C3CC
```
