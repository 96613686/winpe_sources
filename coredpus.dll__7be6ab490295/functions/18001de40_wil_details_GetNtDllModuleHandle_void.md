# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18001de40`
- end: `0x18001de70`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `48`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800197d0`
- `0x18001de78`

## callees

- `0x18001de40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001de57`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001de57`

## string_xrefs

- `0x18001de50`: `ntdll.dll`

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
0x18001de40  sub     rsp, 28h
0x18001de44  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001de4b  test    rax, rax
0x18001de4e  jnz     short loc_18001DE6A
0x18001de50  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001de57  call    cs:__imp_GetModuleHandleW
0x18001de5e  nop     dword ptr [rax+rax+00h]
0x18001de63  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001de6a  add     rsp, 28h
0x18001de6e  retn
```
