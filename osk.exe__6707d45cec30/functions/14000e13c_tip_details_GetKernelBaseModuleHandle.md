# tip_details_GetKernelBaseModuleHandle

- ea: `0x14000e13c`
- end: `0x14000e165`
- name: `tip_details_GetKernelBaseModuleHandle`
- size: `41`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000b574`
- `0x14000d390`
- `0x14000dde4`
- `0x14000de30`
- `0x14000de7c`

## callees

- `0x14000e13c`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000e153`
- `KERNEL32!GetModuleHandleW` at `0x14000e153`

## string_xrefs

- `0x14000e14c`: `kernelbase.dll`

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
0x14000e13c  sub     rsp, 28h
0x14000e140  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x14000e147  test    rax, rax
0x14000e14a  jnz     short loc_14000E160
0x14000e14c  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000e153  call    cs:__imp_GetModuleHandleW
0x14000e159  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x14000e160  add     rsp, 28h
0x14000e164  retn
```
