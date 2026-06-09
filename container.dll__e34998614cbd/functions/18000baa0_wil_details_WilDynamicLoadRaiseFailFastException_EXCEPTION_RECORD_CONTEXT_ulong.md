# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000baa0`
- end: `0x18000bb05`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000baa0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000babf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000babf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bad5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bad5`

## string_xrefs

- `0x18000bab5`: `kernelbase.dll`

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
0x18000baa0  mov     [rsp+arg_0], rbx
0x18000baa5  mov     [rsp+arg_8], rsi
0x18000baaa  push    rdi
0x18000baab  sub     rsp, 20h
0x18000baaf  mov     rsi, rcx
0x18000bab2  mov     ebx, r8d
0x18000bab5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000babc  mov     rdi, rdx
0x18000babf  call    cs:__imp_GetModuleHandleW
0x18000bac6  nop     dword ptr [rax+rax+00h]
0x18000bacb  mov     rcx, rax; hModule
0x18000bace  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000bad5  call    cs:__imp_GetProcAddress
0x18000badc  nop     dword ptr [rax+rax+00h]
0x18000bae1  test    rax, rax
0x18000bae4  jz      short loc_18000BAF4
0x18000bae6  mov     r8d, ebx
0x18000bae9  mov     rdx, rdi
0x18000baec  mov     rcx, rsi
0x18000baef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baf4  mov     rbx, [rsp+28h+arg_0]
0x18000baf9  mov     rsi, [rsp+28h+arg_8]
0x18000bafe  add     rsp, 20h
0x18000bb02  pop     rdi
0x18000bb03  retn
```
