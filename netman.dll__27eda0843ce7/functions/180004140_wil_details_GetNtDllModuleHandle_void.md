# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180004140`
- end: `0x180004169`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800031f0`
- `0x180004170`

## callees

- `0x180004140`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180004157`
- `KERNEL32!GetModuleHandleW` at `0x180004157`

## string_xrefs

- `0x180004150`: `ntdll.dll`

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
0x180004140  sub     rsp, 28h
0x180004144  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000414b  test    rax, rax
0x18000414e  jnz     short loc_180004164
0x180004150  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180004157  call    cs:__imp_GetModuleHandleW
0x18000415d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004164  add     rsp, 28h
0x180004168  retn
```
