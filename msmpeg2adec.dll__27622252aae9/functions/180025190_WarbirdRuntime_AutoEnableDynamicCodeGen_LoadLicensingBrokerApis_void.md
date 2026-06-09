# WarbirdRuntime::AutoEnableDynamicCodeGen::LoadLicensingBrokerApis(void)

- ea: `0x180025190`
- end: `0x1800251fb`
- name: `?LoadLicensingBrokerApis@AutoEnableDynamicCodeGen@WarbirdRuntime@@AEAA_NXZ`
- size: `107`
- prototype: `bool __fastcall(WarbirdRuntime::AutoEnableDynamicCodeGen *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f500`

## callees

- `0x180025190`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002519b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002519b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800251dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800251dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800251bb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800251bb`

## string_xrefs

- `0x180025194`: `api-ms-win-core-com-l1-1-1.dll`
- `0x1800251ae`: `api-ms-win-core-com-l1-1-1.dll`
- `0x1800251d2`: `CoCreateInstanceFromApp`

## pseudocode

```c
bool __fastcall WarbirdRuntime::AutoEnableDynamicCodeGen::LoadLicensingBrokerApis(
        WarbirdRuntime::AutoEnableDynamicCodeGen *this)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-com-l1-1-1.dll");
  if ( ModuleHandleW || (ModuleHandleW = LoadLibraryExW(L"api-ms-win-core-com-l1-1-1.dll", 0, 0x800u)) != 0 )
  {
    WarbirdRuntime::AutoEnableDynamicCodeGen::CoCreateInstanceFromAppProc = (int (*)(const struct _GUID *, struct IUnknown *, unsigned int, void *, unsigned int, struct tagMULTI_QI *))GetProcAddress(ModuleHandleW, "CoCreateInstanceFromApp");
    LOBYTE(ModuleHandleW) = WarbirdRuntime::AutoEnableDynamicCodeGen::CoCreateInstanceFromAppProc != 0;
  }
  return (char)ModuleHandleW;
}

```

## disassembly

```asm
0x180025190  sub     rsp, 28h
0x180025194  lea     rcx, aApiMsWinCoreCo_0; "api-ms-win-core-com-l1-1-1.dll"
0x18002519b  call    cs:__imp_GetModuleHandleW
0x1800251a2  nop     dword ptr [rax+rax+00h]
0x1800251a7  test    rax, rax
0x1800251aa  jnz     short loc_1800251D2
0x1800251ac  xor     edx, edx; hFile
0x1800251ae  lea     rcx, aApiMsWinCoreCo_0; "api-ms-win-core-com-l1-1-1.dll"
0x1800251b5  mov     r8d, 800h; dwFlags
0x1800251bb  call    cs:__imp_LoadLibraryExW
0x1800251c2  nop     dword ptr [rax+rax+00h]
0x1800251c7  test    rax, rax
0x1800251ca  jnz     short loc_1800251D2
0x1800251cc  add     rsp, 28h
0x1800251d0  retn
0x1800251d2  lea     rdx, aCocreateinstan; "CoCreateInstanceFromApp"
0x1800251d9  mov     rcx, rax; hModule
0x1800251dc  call    cs:__imp_GetProcAddress
0x1800251e3  nop     dword ptr [rax+rax+00h]
0x1800251e8  test    rax, rax
0x1800251eb  mov     cs:?CoCreateInstanceFromAppProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AJAEBU_GUID@@PEAUIUnknown@12@KPEAXKPEAUtagMULTI_QI@12@@ZEA, rax; long (*WarbirdRuntime::AutoEnableDynamicCodeGen::CoCreateInstanceFromAppProc)(_GUID const &,WarbirdRuntime::AutoEnableDynamicCodeGen::IUnknown *,ulong,void *,ulong,WarbirdRuntime::AutoEnableDynamicCodeGen::tagMULTI_QI *)
0x1800251f2  setnz   al
0x1800251f5  add     rsp, 28h
0x1800251f9  retn
```
