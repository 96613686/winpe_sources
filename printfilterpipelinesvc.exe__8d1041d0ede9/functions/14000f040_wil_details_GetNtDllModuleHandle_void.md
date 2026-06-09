# wil_details_GetNtDllModuleHandle(void)

- ea: `0x14000f040`
- end: `0x14000f069`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000a390`
- `0x14000f070`

## callees

- `0x14000f040`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000f057`
- `KERNEL32!GetModuleHandleW` at `0x14000f057`

## string_xrefs

- `0x14000f050`: `ntdll.dll`

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
0x14000f040  sub     rsp, 28h
0x14000f044  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000f04b  test    rax, rax
0x14000f04e  jnz     short loc_14000F064
0x14000f050  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000f057  call    cs:__imp_GetModuleHandleW
0x14000f05d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000f064  add     rsp, 28h
0x14000f068  retn
```
