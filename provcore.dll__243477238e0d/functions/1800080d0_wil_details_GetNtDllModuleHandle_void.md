# wil_details_GetNtDllModuleHandle(void)

- ea: `0x1800080d0`
- end: `0x1800080f9`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE__ *__fastcall()`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005c50`
- `0x180008100`

## callees

- `0x1800080d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800080e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800080e7`

## string_xrefs

- `0x1800080e0`: `ntdll.dll`

## pseudocode

```c
HMODULE __fastcall wil_details_GetNtDllModuleHandle()
{
  HMODULE result; // rax

  result = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    result = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = result;
  }
  return result;
}

```

## disassembly

```asm
0x1800080d0  sub     rsp, 28h
0x1800080d4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800080db  test    rax, rax
0x1800080de  jnz     short loc_1800080F4
0x1800080e0  lea     rcx, ModuleName; "ntdll.dll"
0x1800080e7  call    cs:__imp_GetModuleHandleW
0x1800080ed  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800080f4  add     rsp, 28h
0x1800080f8  retn
```
