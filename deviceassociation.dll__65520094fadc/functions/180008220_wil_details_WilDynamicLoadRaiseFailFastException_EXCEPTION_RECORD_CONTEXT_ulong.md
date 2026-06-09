# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180008220`
- end: `0x180008278`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008220`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000824f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000824f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000823f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000823f`

## string_xrefs

- `0x180008235`: `kernelbase.dll`

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
0x180008220  mov     [rsp+arg_0], rbx
0x180008225  mov     [rsp+arg_8], rsi
0x18000822a  push    rdi
0x18000822b  sub     rsp, 20h
0x18000822f  mov     rsi, rcx
0x180008232  mov     ebx, r8d
0x180008235  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000823c  mov     rdi, rdx
0x18000823f  call    cs:__imp_GetModuleHandleW
0x180008245  mov     rcx, rax; hModule
0x180008248  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000824f  call    cs:__imp_GetProcAddress
0x180008255  test    rax, rax
0x180008258  jz      short loc_180008268
0x18000825a  mov     r8d, ebx
0x18000825d  mov     rdx, rdi
0x180008260  mov     rcx, rsi
0x180008263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008268  mov     rbx, [rsp+28h+arg_0]
0x18000826d  mov     rsi, [rsp+28h+arg_8]
0x180008272  add     rsp, 20h
0x180008276  pop     rdi
0x180008277  retn
```
