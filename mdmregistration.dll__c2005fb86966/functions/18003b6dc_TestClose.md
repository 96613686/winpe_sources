# TestClose

- ea: `0x18003b6dc`
- end: `0x18003b748`
- name: `TestClose`
- size: `108`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180031274`
- `0x18003ae5c`

## callees

- `0x18003b6dc`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003b704`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003b704`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b721`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b721`

## string_xrefs

- `0x18003b6fd`: `kernelbase.dll`

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
0x18003b6dc  push    rbx
0x18003b6de  sub     rsp, 20h
0x18003b6e2  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18003b6e9  mov     rbx, rcx
0x18003b6ec  test    rax, rax
0x18003b6ef  jnz     short loc_18003B739
0x18003b6f1  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18003b6f8  test    rax, rax
0x18003b6fb  jnz     short loc_18003B717
0x18003b6fd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003b704  call    cs:__imp_GetModuleHandleW
0x18003b70b  nop     dword ptr [rax+rax+00h]
0x18003b710  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18003b717  lea     rdx, aTestclose; "TestClose"
0x18003b71e  mov     rcx, rax; hModule
0x18003b721  call    cs:__imp_GetProcAddress
0x18003b728  nop     dword ptr [rax+rax+00h]
0x18003b72d  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18003b734  test    rax, rax
0x18003b737  jz      short loc_18003B741
0x18003b739  mov     rcx, rbx
0x18003b73c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b741  add     rsp, 20h
0x18003b745  pop     rbx
0x18003b746  retn
```
