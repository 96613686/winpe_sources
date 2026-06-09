# tip_details_GetKernelBaseModuleHandle

- ea: `0x18002e844`
- end: `0x18002e86d`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `41`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002c7f4`
- `0x18002dd44`
- `0x18002e454`
- `0x18002e4a0`
- `0x18002e510`
- `0x18002e55c`

## callees

- `0x18002e844`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002e85b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002e85b`

## string_xrefs

- `0x18002e854`: `kernelbase.dll`

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
0x18002e844  sub     rsp, 28h
0x18002e848  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18002e84f  test    rax, rax
0x18002e852  jnz     short loc_18002E868
0x18002e854  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002e85b  call    cs:__imp_GetModuleHandleW
0x18002e861  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18002e868  add     rsp, 28h
0x18002e86c  retn
```
