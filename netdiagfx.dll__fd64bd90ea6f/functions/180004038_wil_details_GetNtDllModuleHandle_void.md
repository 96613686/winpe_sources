# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180004038`
- end: `0x180004061`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002b20`
- `0x180004068`

## callees

- `0x180004038`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000404f`
- `KERNEL32!GetModuleHandleW` at `0x18000404f`

## string_xrefs

- `0x180004048`: `ntdll.dll`

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
0x180004038  sub     rsp, 28h
0x18000403c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004043  test    rax, rax
0x180004046  jnz     short loc_18000405C
0x180004048  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000404f  call    cs:__imp_GetModuleHandleW
0x180004055  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000405c  add     rsp, 28h
0x180004060  retn
```
