# wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)

- ea: `0x180007e0c`
- end: `0x180007e71`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180007c18`
- `0x180007ca4`

## callees

- `0x180007e0c`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180007e39`
- `KERNEL32!GetModuleHandleW` at `0x180007e39`
- `KERNEL32!GetProcAddress` at `0x180007e50`
- `KERNEL32!GetProcAddress` at `0x180007e50`

## string_xrefs

- `0x180007e32`: `kernelbase.dll`

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
0x180007e0c  push    rbx
0x180007e0e  sub     rsp, 20h
0x180007e12  mov     rbx, [rcx]
0x180007e15  test    rbx, rbx
0x180007e18  jz      short loc_180007E6B
0x180007e1a  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180007e21  test    rax, rax
0x180007e24  jnz     short loc_180007E62
0x180007e26  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180007e2d  test    rax, rax
0x180007e30  jnz     short loc_180007E46
0x180007e32  lea     rcx, ModuleName; "kernelbase.dll"
0x180007e39  call    cs:__imp_GetModuleHandleW
0x180007e3f  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180007e46  lea     rdx, ProcName; "TestClose"
0x180007e4d  mov     rcx, rax; hModule
0x180007e50  call    cs:__imp_GetProcAddress
0x180007e56  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180007e5d  test    rax, rax
0x180007e60  jz      short loc_180007E6B
0x180007e62  mov     rcx, rbx
0x180007e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e6a  nop
0x180007e6b  add     rsp, 20h
0x180007e6f  pop     rbx
0x180007e70  retn
```
