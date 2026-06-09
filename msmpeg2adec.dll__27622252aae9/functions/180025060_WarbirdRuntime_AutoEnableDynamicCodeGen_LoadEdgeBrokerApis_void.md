# WarbirdRuntime::AutoEnableDynamicCodeGen::LoadEdgeBrokerApis(void)

- ea: `0x180025060`
- end: `0x18002517e`
- name: `?LoadEdgeBrokerApis@AutoEnableDynamicCodeGen@WarbirdRuntime@@AEAA_NXZ`
- size: `286`
- prototype: `bool __fastcall(WarbirdRuntime::AutoEnableDynamicCodeGen *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f500`

## callees

- `0x180025060`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025070`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800250d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025070`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800250d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800250bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025116`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025133`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800250bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025116`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025133`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025090`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800250f8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025090`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800250f8`

## string_xrefs

- `0x180025083`: `api-ms-win-core-com-l1-1-1.dll`
- `0x180025066`: `api-ms-win-core-winrt-l1-1-0.dll`
- `0x1800250c7`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x1800250eb`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x18002510c`: `WindowsCreateString`
- `0x180025122`: `WindowsDeleteString`

## pseudocode

```c
_BOOL8 __fastcall WarbirdRuntime::AutoEnableDynamicCodeGen::LoadEdgeBrokerApis(
        WarbirdRuntime::AutoEnableDynamicCodeGen *this)
{
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rbx
  int (*ProcAddress)(void *); // rcx

  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-winrt-l1-1-0.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = LoadLibraryExW(L"api-ms-win-core-com-l1-1-1.dll", 0, 0x800u);
    if ( !ModuleHandleW )
      return 0;
  }
  WarbirdRuntime::AutoEnableDynamicCodeGen::RoGetActivationFactoryProc = (int (*)(void *, const struct _GUID *, void **))GetProcAddress(ModuleHandleW, "RoGetActivationFactory");
  Library = GetModuleHandleW(L"api-ms-win-core-winrt-string-l1-1-0.dll");
  if ( (Library || (Library = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u)) != 0)
    && (WarbirdRuntime::AutoEnableDynamicCodeGen::WindowsCreateStringProc = (int (*)(const unsigned __int16 *, unsigned int, void **))GetProcAddress(Library, "WindowsCreateString"),
        ProcAddress = (int (*)(void *))GetProcAddress(Library, "WindowsDeleteString"),
        WarbirdRuntime::AutoEnableDynamicCodeGen::WindowsDeleteStringProc = ProcAddress,
        WarbirdRuntime::AutoEnableDynamicCodeGen::WindowsCreateStringProc) )
  {
    return ProcAddress != 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180025060  push    rdi
0x180025062  sub     rsp, 20h
0x180025066  lea     rcx, aApiMsWinCoreWi_0; "api-ms-win-core-winrt-l1-1-0.dll"
0x18002506d  xor     dil, dil
0x180025070  call    cs:__imp_GetModuleHandleW
0x180025077  nop     dword ptr [rax+rax+00h]
0x18002507c  test    rax, rax
0x18002507f  jnz     short loc_1800250AC
0x180025081  xor     edx, edx; hFile
0x180025083  lea     rcx, aApiMsWinCoreCo_0; "api-ms-win-core-com-l1-1-1.dll"
0x18002508a  mov     r8d, 800h; dwFlags
0x180025090  call    cs:__imp_LoadLibraryExW
0x180025097  nop     dword ptr [rax+rax+00h]
0x18002509c  test    rax, rax
0x18002509f  jnz     short loc_1800250AC
0x1800250a1  movzx   eax, dil
0x1800250a5  add     rsp, 20h
0x1800250a9  pop     rdi
0x1800250aa  retn
0x1800250ac  lea     rdx, aRogetactivatio; "RoGetActivationFactory"
0x1800250b3  mov     [rsp+28h+arg_0], rbx
0x1800250b8  mov     rcx, rax; hModule
0x1800250bb  call    cs:__imp_GetProcAddress
0x1800250c2  nop     dword ptr [rax+rax+00h]
0x1800250c7  lea     rcx, aApiMsWinCoreWi; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x1800250ce  mov     cs:?RoGetActivationFactoryProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AJPEAXAEBU_GUID@@PEAPEAX@ZEA, rax; long (*WarbirdRuntime::AutoEnableDynamicCodeGen::RoGetActivationFactoryProc)(void *,_GUID const &,void * *)
0x1800250d5  call    cs:__imp_GetModuleHandleW
0x1800250dc  nop     dword ptr [rax+rax+00h]
0x1800250e1  mov     rbx, rax
0x1800250e4  test    rax, rax
0x1800250e7  jnz     short loc_18002510C
0x1800250e9  xor     edx, edx; hFile
0x1800250eb  lea     rcx, aApiMsWinCoreWi; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x1800250f2  mov     r8d, 800h; dwFlags
0x1800250f8  call    cs:__imp_LoadLibraryExW
0x1800250ff  nop     dword ptr [rax+rax+00h]
0x180025104  mov     rbx, rax
0x180025107  test    rax, rax
0x18002510a  jz      short loc_18002516E
0x18002510c  lea     rdx, aWindowscreates; "WindowsCreateString"
0x180025113  mov     rcx, rbx; hModule
0x180025116  call    cs:__imp_GetProcAddress
0x18002511d  nop     dword ptr [rax+rax+00h]
0x180025122  lea     rdx, aWindowsdeletes; "WindowsDeleteString"
0x180025129  mov     rcx, rbx; hModule
0x18002512c  mov     cs:?WindowsCreateStringProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AJPEBGIPEAPEAX@ZEA, rax; long (*WarbirdRuntime::AutoEnableDynamicCodeGen::WindowsCreateStringProc)(ushort const *,uint,void * *)
0x180025133  call    cs:__imp_GetProcAddress
0x18002513a  nop     dword ptr [rax+rax+00h]
0x18002513f  cmp     cs:?WindowsCreateStringProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AJPEBGIPEAPEAX@ZEA, 0; long (*WarbirdRuntime::AutoEnableDynamicCodeGen::WindowsCreateStringProc)(ushort const *,uint,void * *)
0x180025147  mov     rcx, rax
0x18002514a  mov     cs:?WindowsDeleteStringProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AJPEAX@ZEA, rax; long (*WarbirdRuntime::AutoEnableDynamicCodeGen::WindowsDeleteStringProc)(void *)
0x180025151  jz      short loc_18002516E
0x180025153  mov     rbx, [rsp+28h+arg_0]
0x180025158  test    rcx, rcx
0x18002515b  movzx   eax, dil
0x18002515f  mov     edx, 1
0x180025164  cmovnz  eax, edx
0x180025167  add     rsp, 20h
0x18002516b  pop     rdi
0x18002516c  retn
0x18002516e  mov     rbx, [rsp+28h+arg_0]
0x180025173  movzx   eax, dil
0x180025177  add     rsp, 20h
0x18002517b  pop     rdi
0x18002517c  retn
```
