# wil_details_GetNtDllModuleHandle(void)

- ea: `0x1800066ac`
- end: `0x1800066dc`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `48`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004170`
- `0x1800066e4`

## callees

- `0x1800066ac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800066c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800066c3`

## string_xrefs

- `0x1800066bc`: `ntdll.dll`

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
0x1800066ac  sub     rsp, 28h
0x1800066b0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800066b7  test    rax, rax
0x1800066ba  jnz     short loc_1800066D6
0x1800066bc  lea     rcx, aNtdllDll; "ntdll.dll"
0x1800066c3  call    cs:__imp_GetModuleHandleW
0x1800066ca  nop     dword ptr [rax+rax+00h]
0x1800066cf  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800066d6  add     rsp, 28h
0x1800066da  retn
```
