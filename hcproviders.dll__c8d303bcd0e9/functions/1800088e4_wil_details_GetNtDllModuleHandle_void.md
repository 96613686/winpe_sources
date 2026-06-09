# wil_details_GetNtDllModuleHandle(void)

- ea: `0x1800088e4`
- end: `0x180008914`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `48`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006a80`
- `0x18000891c`

## callees

- `0x1800088e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800088fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800088fb`

## string_xrefs

- `0x1800088f4`: `ntdll.dll`

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
0x1800088e4  sub     rsp, 28h
0x1800088e8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800088ef  test    rax, rax
0x1800088f2  jnz     short loc_18000890E
0x1800088f4  lea     rcx, ModuleName; "ntdll.dll"
0x1800088fb  call    cs:__imp_GetModuleHandleW
0x180008902  nop     dword ptr [rax+rax+00h]
0x180008907  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000890e  add     rsp, 28h
0x180008912  retn
```
