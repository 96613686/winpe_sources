# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18003664c`
- end: `0x180036675`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180032d70`
- `0x18003667c`

## callees

- `0x18003664c`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180036663`
- `KERNEL32!GetModuleHandleW` at `0x180036663`

## string_xrefs

- `0x18003665c`: `ntdll.dll`

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
0x18003664c  sub     rsp, 28h
0x180036650  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180036657  test    rax, rax
0x18003665a  jnz     short loc_180036670
0x18003665c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180036663  call    cs:__imp_GetModuleHandleW
0x180036669  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180036670  add     rsp, 28h
0x180036674  retn
```
