# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14000bce0`
- end: `0x14000bd45`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000bce0`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bd15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bd15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bcff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bcff`

## string_xrefs

- `0x14000bcf5`: `kernelbase.dll`

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
0x14000bce0  mov     [rsp+arg_0], rbx
0x14000bce5  mov     [rsp+arg_8], rsi
0x14000bcea  push    rdi
0x14000bceb  sub     rsp, 20h
0x14000bcef  mov     rsi, rcx
0x14000bcf2  mov     ebx, r8d
0x14000bcf5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000bcfc  mov     rdi, rdx
0x14000bcff  call    cs:__imp_GetModuleHandleW
0x14000bd06  nop     dword ptr [rax+rax+00h]
0x14000bd0b  mov     rcx, rax; hModule
0x14000bd0e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000bd15  call    cs:__imp_GetProcAddress
0x14000bd1c  nop     dword ptr [rax+rax+00h]
0x14000bd21  test    rax, rax
0x14000bd24  jz      short loc_14000BD34
0x14000bd26  mov     r8d, ebx
0x14000bd29  mov     rdx, rdi
0x14000bd2c  mov     rcx, rsi
0x14000bd2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd34  mov     rbx, [rsp+28h+arg_0]
0x14000bd39  mov     rsi, [rsp+28h+arg_8]
0x14000bd3e  add     rsp, 20h
0x14000bd42  pop     rdi
0x14000bd43  retn
```
