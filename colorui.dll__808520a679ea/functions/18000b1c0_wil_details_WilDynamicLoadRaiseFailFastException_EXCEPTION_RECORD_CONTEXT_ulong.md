# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000b1c0`
- end: `0x18000b218`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b1c0`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000b1ef`
- `KERNEL32!GetProcAddress` at `0x18000b1ef`
- `KERNEL32!GetModuleHandleW` at `0x18000b1df`
- `KERNEL32!GetModuleHandleW` at `0x18000b1df`

## string_xrefs

- `0x18000b1d5`: `kernelbase.dll`

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
0x18000b1c0  mov     [rsp+arg_0], rbx
0x18000b1c5  mov     [rsp+arg_8], rsi
0x18000b1ca  push    rdi
0x18000b1cb  sub     rsp, 20h
0x18000b1cf  mov     rsi, rcx
0x18000b1d2  mov     ebx, r8d
0x18000b1d5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000b1dc  mov     rdi, rdx
0x18000b1df  call    cs:__imp_GetModuleHandleW
0x18000b1e5  mov     rcx, rax; hModule
0x18000b1e8  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000b1ef  call    cs:__imp_GetProcAddress
0x18000b1f5  test    rax, rax
0x18000b1f8  jz      short loc_18000B208
0x18000b1fa  mov     r8d, ebx
0x18000b1fd  mov     rdx, rdi
0x18000b200  mov     rcx, rsi
0x18000b203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b208  mov     rbx, [rsp+28h+arg_0]
0x18000b20d  mov     rsi, [rsp+28h+arg_8]
0x18000b212  add     rsp, 20h
0x18000b216  pop     rdi
0x18000b217  retn
```
