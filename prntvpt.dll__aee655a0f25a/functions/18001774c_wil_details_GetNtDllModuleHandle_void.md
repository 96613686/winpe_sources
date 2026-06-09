# wil_details_GetNtDllModuleHandle(void)

- ea: `0x18001774c`
- end: `0x180017775`
- name: `?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012b70`
- `0x18001777c`

## callees

- `0x18001774c`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180017763`
- `KERNEL32!GetModuleHandleW` at `0x180017763`

## string_xrefs

- `0x18001775c`: `ntdll.dll`

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
0x18001774c  sub     rsp, 28h
0x180017750  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180017757  test    rax, rax
0x18001775a  jnz     short loc_180017770
0x18001775c  lea     rcx, aNtdllDll; "ntdll.dll"
0x180017763  call    cs:__imp_GetModuleHandleW
0x180017769  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180017770  add     rsp, 28h
0x180017774  retn
```
