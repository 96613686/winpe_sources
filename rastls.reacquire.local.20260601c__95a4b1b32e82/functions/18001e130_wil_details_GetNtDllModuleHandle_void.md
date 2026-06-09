# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18001e130`
- end: `0x18001e160`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `48`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002ca50`
- `0x18003ba60`

## callees

- `0x18001e130`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e147`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e147`

## string_xrefs

- `0x18001e140`: `ntdll.dll`

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
0x18001e130  sub     rsp, 28h
0x18001e134  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001e13b  test    rax, rax
0x18001e13e  jnz     short loc_18001E15A
0x18001e140  lea     rcx, ModuleName; "ntdll.dll"
0x18001e147  call    cs:__imp_GetModuleHandleW
0x18001e14e  nop     dword ptr [rax+rax+00h]
0x18001e153  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001e15a  add     rsp, 28h
0x18001e15e  retn
```
