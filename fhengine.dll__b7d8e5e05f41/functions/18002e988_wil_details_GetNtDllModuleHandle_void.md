# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18002e988`
- end: `0x18002e9b1`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180028ed0`
- `0x18002e9b8`

## callees

- `0x18002e988`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18002e99f`
- `KERNEL32!GetModuleHandleW` at `0x18002e99f`

## string_xrefs

- `0x18002e998`: `ntdll.dll`

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
0x18002e988  sub     rsp, 28h
0x18002e98c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002e993  test    rax, rax
0x18002e996  jnz     short loc_18002E9AC
0x18002e998  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18002e99f  call    cs:__imp_GetModuleHandleW
0x18002e9a5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002e9ac  add     rsp, 28h
0x18002e9b0  retn
```
