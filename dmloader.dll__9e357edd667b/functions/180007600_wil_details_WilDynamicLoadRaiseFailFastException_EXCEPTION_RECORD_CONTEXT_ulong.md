# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180007600`
- end: `0x180007658`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007600`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000761f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000761f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000762f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000762f`

## string_xrefs

- `0x180007615`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v4);
}

```

## disassembly

```asm
0x180007600  mov     [rsp+arg_0], rbx
0x180007605  mov     [rsp+arg_8], rsi
0x18000760a  push    rdi
0x18000760b  sub     rsp, 20h
0x18000760f  mov     rsi, rcx
0x180007612  mov     ebx, r8d
0x180007615  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000761c  mov     rdi, rdx
0x18000761f  call    cs:__imp_GetModuleHandleW
0x180007625  mov     rcx, rax; hModule
0x180007628  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000762f  call    cs:__imp_GetProcAddress
0x180007635  test    rax, rax
0x180007638  jz      short loc_180007648
0x18000763a  mov     r8d, ebx
0x18000763d  mov     rdx, rdi
0x180007640  mov     rcx, rsi
0x180007643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007648  mov     rbx, [rsp+28h+arg_0]
0x18000764d  mov     rsi, [rsp+28h+arg_8]
0x180007652  add     rsp, 20h
0x180007656  pop     rdi
0x180007657  retn
```
