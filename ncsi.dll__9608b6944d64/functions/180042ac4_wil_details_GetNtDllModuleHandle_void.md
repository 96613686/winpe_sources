# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180042ac4`
- end: `0x180042aed`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002c6c0`
- `0x180042a9c`
- `0x18004a330`

## callees

- `0x180042ac4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180042adb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180042adb`

## string_xrefs

- `0x180042ad4`: `ntdll.dll`

## pseudocode

```c
HINSTANCE wil_details_GetNtDllModuleHandle(void)
{
  HINSTANCE result; // rax

  result = (HINSTANCE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    result = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = (__int64)result;
  }
  return result;
}

```

## disassembly

```asm
0x180042ac4  sub     rsp, 28h
0x180042ac8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180042acf  test    rax, rax
0x180042ad2  jnz     short loc_180042AE8
0x180042ad4  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180042adb  call    cs:__imp_GetModuleHandleW
0x180042ae1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180042ae8  add     rsp, 28h
0x180042aec  retn
```
