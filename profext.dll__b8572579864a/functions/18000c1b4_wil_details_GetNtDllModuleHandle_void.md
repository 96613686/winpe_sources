# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18000c1b4`
- end: `0x18000c1e6`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `50`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180016fb0`
- `0x18001c438`

## callees

- `0x18000c1b4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c1d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c1d1`

## string_xrefs

- `0x18000c1ca`: `ntdll.dll`

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
0x18000c1b4  sub     rsp, 28h
0x18000c1b8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c1bf  test    rax, rax
0x18000c1c2  jz      short loc_18000C1CA
0x18000c1c4  add     rsp, 28h
0x18000c1c8  retn
0x18000c1ca  lea     rcx, ModuleName; "ntdll.dll"
0x18000c1d1  call    cs:__imp_GetModuleHandleW
0x18000c1d8  nop     dword ptr [rax+rax+00h]
0x18000c1dd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c1e4  jmp     short loc_18000C1C4
```
