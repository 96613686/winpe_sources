# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x10009e70`
- end: `0x10009eae`
- name: `?FormatNtStatusMsg@details@wil@@YGXJPAGK@Z`
- size: `62`
- prototype: `void __stdcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x10009e70`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x10009ea4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x10009ea4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x10009e83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x10009e83`

## string_xrefs

- `0x10009e7e`: `ntdll.dll`

## pseudocode

```c
void __stdcall wil::details::FormatNtStatusMsg(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int a4)
{
  HMODULE ModuleHandleW; // eax

  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  FormatMessageW(0x1A00u, ModuleHandleW, dwMessageId, 0x400u, lpBuffer, nSize, 0);
}

```

## disassembly

```asm
0x10009e70  mov     edi, edi
0x10009e72  push    ebp
0x10009e73  mov     ebp, esp
0x10009e75  mov     eax, ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x10009e7a  test    eax, eax
0x10009e7c  jnz     short loc_10009E8E
0x10009e7e  push    offset ModuleName; "ntdll.dll"
0x10009e83  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x10009e89  mov     ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A, eax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x10009e8e  push    0; Arguments
0x10009e90  push    [ebp+nSize]; nSize
0x10009e93  push    [ebp+lpBuffer]; lpBuffer
0x10009e96  push    400h; dwLanguageId
0x10009e9b  push    [ebp+dwMessageId]; dwMessageId
0x10009e9e  push    eax; lpSource
0x10009e9f  push    1A00h; dwFlags
0x10009ea4  call    ds:__imp__FormatMessageW@28; FormatMessageW(x,x,x,x,x,x,x)
0x10009eaa  pop     ebp
0x10009eab  retn    0Ch
```
