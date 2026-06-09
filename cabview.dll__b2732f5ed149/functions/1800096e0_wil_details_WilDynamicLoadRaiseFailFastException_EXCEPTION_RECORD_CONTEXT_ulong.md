# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800096e0`
- end: `0x180009730`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800032b8`
- `0x1800096e0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800096ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800096ff`

## string_xrefs

- `0x1800096f5`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  void (__fastcall *Proc)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD); // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  Proc = (void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,unsigned long)>(ModuleHandleW);
  if ( Proc )
    Proc(this, a2, v4);
}

```

## disassembly

```asm
0x1800096e0  mov     [rsp+arg_0], rbx
0x1800096e5  mov     [rsp+arg_8], rsi
0x1800096ea  push    rdi
0x1800096eb  sub     rsp, 20h
0x1800096ef  mov     rsi, rcx
0x1800096f2  mov     ebx, r8d
0x1800096f5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800096fc  mov     rdi, rdx
0x1800096ff  call    cs:__imp_GetModuleHandleW
0x180009705  mov     rcx, rax
0x180009708  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18000970d  test    rax, rax
0x180009710  jz      short loc_180009720
0x180009712  mov     r8d, ebx
0x180009715  mov     rdx, rdi
0x180009718  mov     rcx, rsi
0x18000971b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009720  mov     rbx, [rsp+28h+arg_0]
0x180009725  mov     rsi, [rsp+28h+arg_8]
0x18000972a  add     rsp, 20h
0x18000972e  pop     rdi
0x18000972f  retn
```
