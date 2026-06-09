# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x100076c0`
- end: `0x100076fe`
- name: `?FormatNtStatusMsg@details@wil@@YGXJPAGK@Z`
- size: `62`
- prototype: `void __stdcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x100076c0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x100076f4`
- `KERNEL32!FormatMessageW` at `0x100076f4`
- `KERNEL32!GetModuleHandleW` at `0x100076d3`
- `KERNEL32!GetModuleHandleW` at `0x100076d3`

## string_xrefs

- `0x100076ce`: `ntdll.dll`

## pseudocode

```c
void __stdcall wil::details::FormatNtStatusMsg(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int a4)
{
  HMODULE ModuleHandleW; // eax

  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x100076c0  mov     edi, edi
0x100076c2  push    ebp
0x100076c3  mov     ebp, esp
0x100076c5  mov     eax, ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x100076ca  test    eax, eax
0x100076cc  jnz     short loc_100076DE
0x100076ce  push    offset ModuleName; "ntdll.dll"
0x100076d3  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x100076d9  mov     ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A, eax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x100076de  push    0; Arguments
0x100076e0  push    [ebp+nSize]; nSize
0x100076e3  push    [ebp+lpBuffer]; lpBuffer
0x100076e6  push    400h; dwLanguageId
0x100076eb  push    [ebp+dwMessageId]; dwMessageId
0x100076ee  push    eax; lpSource
0x100076ef  push    1A00h; dwFlags
0x100076f4  call    ds:__imp__FormatMessageW@28; FormatMessageW(x,x,x,x,x,x,x)
0x100076fa  pop     ebp
0x100076fb  retn    0Ch
```
