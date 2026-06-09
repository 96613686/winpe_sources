# tip_details_GetKernelBaseModuleHandle

- ea: `0x18002f92c`
- end: `0x18002f95c`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `48`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002d79c`
- `0x18002edb4`
- `0x18002f4fc`
- `0x18002f550`
- `0x18002f5c8`
- `0x18002f61c`

## callees

- `0x18002f92c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f943`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f943`

## string_xrefs

- `0x18002f93c`: `kernelbase.dll`

## pseudocode

```c
HMODULE tip_details_GetKernelBaseModuleHandle()
{
  HMODULE result; // rax

  result = (HMODULE)g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    result = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = (__int64)result;
  }
  return result;
}

```

## disassembly

```asm
0x18002f92c  sub     rsp, 28h
0x18002f930  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18002f937  test    rax, rax
0x18002f93a  jnz     short loc_18002F956
0x18002f93c  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002f943  call    cs:__imp_GetModuleHandleW
0x18002f94a  nop     dword ptr [rax+rax+00h]
0x18002f94f  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18002f956  add     rsp, 28h
0x18002f95a  retn
```
