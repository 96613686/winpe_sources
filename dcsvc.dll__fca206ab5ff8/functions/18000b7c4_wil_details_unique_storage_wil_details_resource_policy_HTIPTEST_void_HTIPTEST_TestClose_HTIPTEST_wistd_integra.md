# wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)

- ea: `0x18000b7c4`
- end: `0x18000b829`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b6b0`

## callees

- `0x18000b7c4`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b808`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b808`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b7f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b7f1`

## string_xrefs

- `0x18000b7ea`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(
        __int64 *a1)
{
  __int64 v1; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  v1 = *a1;
  if ( *a1 )
  {
    ProcAddress = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
    if ( `TestClose'::`2'::s_pfnTestClose )
      goto LABEL_6;
    ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "TestClose");
    `TestClose'::`2'::s_pfnTestClose = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_6:
      ((void (__fastcall *)(__int64))ProcAddress)(v1);
  }
}

```

## disassembly

```asm
0x18000b7c4  push    rbx
0x18000b7c6  sub     rsp, 20h
0x18000b7ca  mov     rbx, [rcx]
0x18000b7cd  test    rbx, rbx
0x18000b7d0  jz      short loc_18000B823
0x18000b7d2  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18000b7d9  test    rax, rax
0x18000b7dc  jnz     short loc_18000B81A
0x18000b7de  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000b7e5  test    rax, rax
0x18000b7e8  jnz     short loc_18000B7FE
0x18000b7ea  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000b7f1  call    cs:__imp_GetModuleHandleW
0x18000b7f7  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000b7fe  lea     rdx, aTestclose; "TestClose"
0x18000b805  mov     rcx, rax; hModule
0x18000b808  call    cs:__imp_GetProcAddress
0x18000b80e  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18000b815  test    rax, rax
0x18000b818  jz      short loc_18000B823
0x18000b81a  mov     rcx, rbx
0x18000b81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b822  nop
0x18000b823  add     rsp, 20h
0x18000b827  pop     rbx
0x18000b828  retn
```
