# wil_details_GetNtDllModuleHandle(void)

- ea: `0x140005a40`
- end: `0x140005a6b`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `43`
- prototype: `HINSTANCE(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400057c0`
- `0x14000e99c`
- `0x140011c10`

## callees

- `0x140005a40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005a5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005a5c`

## string_xrefs

- `0x140005a55`: `ntdll.dll`

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
0x140005a40  sub     rsp, 28h
0x140005a44  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005a4b  test    rax, rax
0x140005a4e  jz      short loc_140005A55
0x140005a50  add     rsp, 28h
0x140005a54  retn
0x140005a55  lea     rcx, ModuleName; "ntdll.dll"
0x140005a5c  call    cs:__imp_GetModuleHandleW
0x140005a62  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005a69  jmp     short loc_140005A50
```
