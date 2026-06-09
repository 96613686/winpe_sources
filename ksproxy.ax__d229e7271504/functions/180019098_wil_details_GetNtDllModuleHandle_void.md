# wil_details_GetNtDllModuleHandle(void)

- ea: `0x180019098`
- end: `0x1800190c8`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `48`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180021f00`
- `0x180025804`

## callees

- `0x180019098`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800190af`
- `KERNEL32!GetModuleHandleW` at `0x1800190af`

## string_xrefs

- `0x1800190a8`: `ntdll.dll`

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
0x180019098  sub     rsp, 28h
0x18001909c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800190a3  test    rax, rax
0x1800190a6  jnz     short loc_1800190C2
0x1800190a8  lea     rcx, ModuleName; "ntdll.dll"
0x1800190af  call    cs:__imp_GetModuleHandleW
0x1800190b6  nop     dword ptr [rax+rax+00h]
0x1800190bb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800190c2  add     rsp, 28h
0x1800190c6  retn
```
