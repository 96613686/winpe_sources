# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180007370`
- end: `0x1800073c8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007370`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000739f`
- `KERNEL32!GetProcAddress` at `0x18000739f`
- `KERNEL32!GetModuleHandleW` at `0x18000738f`
- `KERNEL32!GetModuleHandleW` at `0x18000738f`

## string_xrefs

- `0x180007385`: `kernelbase.dll`

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
0x180007370  mov     [rsp+arg_0], rbx
0x180007375  mov     [rsp+arg_8], rsi
0x18000737a  push    rdi
0x18000737b  sub     rsp, 20h
0x18000737f  mov     rsi, rcx
0x180007382  mov     ebx, r8d
0x180007385  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000738c  mov     rdi, rdx
0x18000738f  call    cs:__imp_GetModuleHandleW
0x180007395  mov     rcx, rax; hModule
0x180007398  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000739f  call    cs:__imp_GetProcAddress
0x1800073a5  test    rax, rax
0x1800073a8  jz      short loc_1800073B8
0x1800073aa  mov     r8d, ebx
0x1800073ad  mov     rdx, rdi
0x1800073b0  mov     rcx, rsi
0x1800073b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073b8  mov     rbx, [rsp+28h+arg_0]
0x1800073bd  mov     rsi, [rsp+28h+arg_8]
0x1800073c2  add     rsp, 20h
0x1800073c6  pop     rdi
0x1800073c7  retn
```
