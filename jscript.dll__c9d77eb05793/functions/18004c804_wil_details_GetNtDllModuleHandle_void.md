# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18004c804`
- end: `0x18004c82f`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `43`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180059090`
- `0x18005a998`

## callees

- `0x18004c804`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18004c820`
- `KERNEL32!GetModuleHandleW` at `0x18004c820`

## string_xrefs

- `0x18004c819`: `ntdll.dll`

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
0x18004c804  sub     rsp, 28h
0x18004c808  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18004c80f  test    rax, rax
0x18004c812  jz      short loc_18004C819
0x18004c814  add     rsp, 28h
0x18004c818  retn
0x18004c819  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18004c820  call    cs:__imp_GetModuleHandleW
0x18004c826  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18004c82d  jmp     short loc_18004C814
```
