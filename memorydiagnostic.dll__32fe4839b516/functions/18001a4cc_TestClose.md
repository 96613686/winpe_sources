# TestClose

- ea: `0x18001a4cc`
- end: `0x18001a538`
- name: `TestClose`
- size: `108`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006a0c`
- `0x180007c64`
- `0x180019a18`

## callees

- `0x18001a4cc`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001a4f4`
- `KERNEL32!GetModuleHandleW` at `0x18001a4f4`
- `KERNEL32!GetProcAddress` at `0x18001a511`
- `KERNEL32!GetProcAddress` at `0x18001a511`

## string_xrefs

- `0x18001a4ed`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall TestClose(__int64 a1)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
  if ( `TestClose'::`2'::s_pfnTestClose )
    return (FARPROC)((__int64 (__fastcall *)(__int64))result)(a1);
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "TestClose");
  `TestClose'::`2'::s_pfnTestClose = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(__int64))result)(a1);
  return result;
}

```

## disassembly

```asm
0x18001a4cc  push    rbx
0x18001a4ce  sub     rsp, 20h
0x18001a4d2  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18001a4d9  mov     rbx, rcx
0x18001a4dc  test    rax, rax
0x18001a4df  jnz     short loc_18001A529
0x18001a4e1  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18001a4e8  test    rax, rax
0x18001a4eb  jnz     short loc_18001A507
0x18001a4ed  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001a4f4  call    cs:__imp_GetModuleHandleW
0x18001a4fb  nop     dword ptr [rax+rax+00h]
0x18001a500  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18001a507  lea     rdx, aTestclose; "TestClose"
0x18001a50e  mov     rcx, rax; hModule
0x18001a511  call    cs:__imp_GetProcAddress
0x18001a518  nop     dword ptr [rax+rax+00h]
0x18001a51d  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18001a524  test    rax, rax
0x18001a527  jz      short loc_18001A531
0x18001a529  mov     rcx, rbx
0x18001a52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a531  add     rsp, 20h
0x18001a535  pop     rbx
0x18001a536  retn
```
