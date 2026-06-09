# wil_details_GetNtDllModuleHandle(void)

- ea: `0x140005434`
- end: `0x14000545d`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400032e0`
- `0x140005464`

## callees

- `0x140005434`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000544b`
- `KERNEL32!GetModuleHandleW` at `0x14000544b`

## string_xrefs

- `0x140005444`: `ntdll.dll`

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
0x140005434  sub     rsp, 28h
0x140005438  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000543f  test    rax, rax
0x140005442  jnz     short loc_140005458
0x140005444  lea     rcx, aNtdllDll; "ntdll.dll"
0x14000544b  call    cs:__imp_GetModuleHandleW
0x140005451  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005458  add     rsp, 28h
0x14000545c  retn
```
