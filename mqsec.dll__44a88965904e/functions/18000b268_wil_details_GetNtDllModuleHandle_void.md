# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18000b268`
- end: `0x18000b291`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006900`
- `0x18000b298`

## callees

- `0x18000b268`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000b27f`
- `KERNEL32!GetModuleHandleW` at `0x18000b27f`

## string_xrefs

- `0x18000b278`: `ntdll.dll`

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
0x18000b268  sub     rsp, 28h
0x18000b26c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b273  test    rax, rax
0x18000b276  jnz     short loc_18000B28C
0x18000b278  lea     rcx, ModuleName; "ntdll.dll"
0x18000b27f  call    cs:__imp_GetModuleHandleW
0x18000b285  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b28c  add     rsp, 28h
0x18000b290  retn
```
