# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180008258`
- end: `0x180008281`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004450`
- `0x180008288`

## callees

- `0x180008258`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000826f`
- `KERNEL32!GetModuleHandleW` at `0x18000826f`

## string_xrefs

- `0x180008268`: `ntdll.dll`

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
0x180008258  sub     rsp, 28h
0x18000825c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008263  test    rax, rax
0x180008266  jnz     short loc_18000827C
0x180008268  lea     rcx, ModuleName; "ntdll.dll"
0x18000826f  call    cs:__imp_GetModuleHandleW
0x180008275  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000827c  add     rsp, 28h
0x180008280  retn
```
