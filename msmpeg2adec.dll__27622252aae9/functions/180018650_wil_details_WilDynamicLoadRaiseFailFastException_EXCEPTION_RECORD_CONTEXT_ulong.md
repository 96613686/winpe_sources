# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180018650`
- end: `0x1800186b6`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `102`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180018650`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001866f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001866f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018685`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018685`

## string_xrefs

- `0x180018665`: `kernelbase.dll`

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
0x180018650  mov     [rsp+arg_0], rbx
0x180018655  mov     [rsp+arg_8], rsi
0x18001865a  push    rdi
0x18001865b  sub     rsp, 20h
0x18001865f  mov     rsi, rcx
0x180018662  mov     ebx, r8d
0x180018665  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001866c  mov     rdi, rdx
0x18001866f  call    cs:__imp_GetModuleHandleW
0x180018676  nop     dword ptr [rax+rax+00h]
0x18001867b  mov     rcx, rax; hModule
0x18001867e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180018685  call    cs:__imp_GetProcAddress
0x18001868c  nop     dword ptr [rax+rax+00h]
0x180018691  test    rax, rax
0x180018694  jz      short loc_1800186A5
0x180018696  mov     r8d, ebx
0x180018699  mov     rdx, rdi
0x18001869c  mov     rcx, rsi
0x18001869f  call    cs:__guard_dispatch_icall_fptr
0x1800186a5  mov     rbx, [rsp+28h+arg_0]
0x1800186aa  mov     rsi, [rsp+28h+arg_8]
0x1800186af  add     rsp, 20h
0x1800186b3  pop     rdi
0x1800186b4  retn
```
