# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18004d204`
- end: `0x18004d236`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `50`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18005a070`
- `0x18005baa4`

## callees

- `0x18004d204`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18004d221`
- `KERNEL32!GetModuleHandleW` at `0x18004d221`

## string_xrefs

- `0x18004d21a`: `ntdll.dll`

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
0x18004d204  sub     rsp, 28h
0x18004d208  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18004d20f  test    rax, rax
0x18004d212  jz      short loc_18004D21A
0x18004d214  add     rsp, 28h
0x18004d218  retn
0x18004d21a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18004d221  call    cs:__imp_GetModuleHandleW
0x18004d228  nop     dword ptr [rax+rax+00h]
0x18004d22d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18004d234  jmp     short loc_18004D214
```
