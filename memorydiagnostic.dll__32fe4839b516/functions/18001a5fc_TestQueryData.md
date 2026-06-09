# TestQueryData

- ea: `0x18001a5fc`
- end: `0x18001a6a5`
- name: `TestQueryData`
- size: `169`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180016694`
- `0x180016740`

## callees

- `0x18001a5fc`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001a63a`
- `KERNEL32!GetModuleHandleW` at `0x18001a63a`
- `KERNEL32!GetProcAddress` at `0x18001a657`
- `KERNEL32!GetProcAddress` at `0x18001a657`

## string_xrefs

- `0x18001a633`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall TestQueryData(__int64 a1, unsigned int a2, unsigned int a3, _OWORD *a4)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`TestQueryData'::`2'::s_pfnTestQueryData;
  if ( `TestQueryData'::`2'::s_pfnTestQueryData )
    return (FARPROC)((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _OWORD *))result)(a1, a2, a3, a4);
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "TestQueryData");
  `TestQueryData'::`2'::s_pfnTestQueryData = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _OWORD *))result)(a1, a2, a3, a4);
  *a4 = 0;
  a4[1] = 0;
  a4[2] = 0;
  return result;
}

```

## disassembly

```asm
0x18001a5fc  mov     [rsp+arg_0], rbx
0x18001a601  mov     [rsp+arg_8], rbp
0x18001a606  mov     [rsp+arg_10], rsi
0x18001a60b  push    rdi
0x18001a60c  sub     rsp, 30h
0x18001a610  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18001a617  mov     rbx, r9
0x18001a61a  mov     edi, r8d
0x18001a61d  mov     esi, edx
0x18001a61f  mov     rbp, rcx
0x18001a622  test    rax, rax
0x18001a625  jnz     short loc_18001A67F
0x18001a627  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18001a62e  test    rax, rax
0x18001a631  jnz     short loc_18001A64D
0x18001a633  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001a63a  call    cs:__imp_GetModuleHandleW
0x18001a641  nop     dword ptr [rax+rax+00h]
0x18001a646  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18001a64d  lea     rdx, aTestquerydata; "TestQueryData"
0x18001a654  mov     rcx, rax; hModule
0x18001a657  call    cs:__imp_GetProcAddress
0x18001a65e  nop     dword ptr [rax+rax+00h]
0x18001a663  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18001a66a  test    rax, rax
0x18001a66d  jnz     short loc_18001A67F
0x18001a66f  xorps   xmm0, xmm0
0x18001a672  movups  xmmword ptr [rbx], xmm0
0x18001a675  movups  xmmword ptr [rbx+10h], xmm0
0x18001a679  movups  xmmword ptr [rbx+20h], xmm0
0x18001a67d  jmp     short loc_18001A68F
0x18001a67f  mov     r9, rbx
0x18001a682  mov     r8d, edi
0x18001a685  mov     edx, esi
0x18001a687  mov     rcx, rbp
0x18001a68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a68f  mov     rbx, [rsp+38h+arg_0]
0x18001a694  mov     rbp, [rsp+38h+arg_8]
0x18001a699  mov     rsi, [rsp+38h+arg_10]
0x18001a69e  add     rsp, 30h
0x18001a6a2  pop     rdi
0x18001a6a3  retn
```
