# wil_details_GetNtDllModuleHandle(void)

- ea: `0x14000d7e0`
- end: `0x14000d809`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140006380`
- `0x14000d810`

## callees

- `0x14000d7e0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000d7f7`
- `KERNEL32!GetModuleHandleW` at `0x14000d7f7`

## string_xrefs

- `0x14000d7f0`: `ntdll.dll`

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
0x14000d7e0  sub     rsp, 28h
0x14000d7e4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d7eb  test    rax, rax
0x14000d7ee  jnz     short loc_14000D804
0x14000d7f0  lea     rcx, ModuleName; "ntdll.dll"
0x14000d7f7  call    cs:__imp_GetModuleHandleW
0x14000d7fd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d804  add     rsp, 28h
0x14000d808  retn
```
