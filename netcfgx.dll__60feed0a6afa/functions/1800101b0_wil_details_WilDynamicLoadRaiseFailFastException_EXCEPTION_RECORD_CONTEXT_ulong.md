# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800101b0`
- end: `0x180010208`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800101b0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800101cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800101cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800101df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800101df`

## string_xrefs

- `0x1800101c5`: `kernelbase.dll`

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
0x1800101b0  mov     [rsp+arg_0], rbx
0x1800101b5  mov     [rsp+arg_8], rsi
0x1800101ba  push    rdi
0x1800101bb  sub     rsp, 20h
0x1800101bf  mov     rsi, rcx
0x1800101c2  mov     ebx, r8d
0x1800101c5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800101cc  mov     rdi, rdx
0x1800101cf  call    cs:__imp_GetModuleHandleW
0x1800101d5  mov     rcx, rax; hModule
0x1800101d8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x1800101df  call    cs:__imp_GetProcAddress
0x1800101e5  test    rax, rax
0x1800101e8  jz      short loc_1800101F8
0x1800101ea  mov     r8d, ebx
0x1800101ed  mov     rdx, rdi
0x1800101f0  mov     rcx, rsi
0x1800101f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101f8  mov     rbx, [rsp+28h+arg_0]
0x1800101fd  mov     rsi, [rsp+28h+arg_8]
0x180010202  add     rsp, 20h
0x180010206  pop     rdi
0x180010207  retn
```
