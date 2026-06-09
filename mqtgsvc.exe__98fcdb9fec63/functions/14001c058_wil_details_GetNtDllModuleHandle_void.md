# wil_details_GetNtDllModuleHandle(void)

- ea: `0x14001c058`
- end: `0x14001c081`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140017fc0`
- `0x14001c088`

## callees

- `0x14001c058`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14001c06f`
- `KERNEL32!GetModuleHandleW` at `0x14001c06f`

## string_xrefs

- `0x14001c068`: `ntdll.dll`

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
0x14001c058  sub     rsp, 28h
0x14001c05c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001c063  test    rax, rax
0x14001c066  jnz     short loc_14001C07C
0x14001c068  lea     rcx, ModuleName; "ntdll.dll"
0x14001c06f  call    cs:__imp_GetModuleHandleW
0x14001c075  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001c07c  add     rsp, 28h
0x14001c080  retn
```
