# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140005660`
- end: `0x1400056b8`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005660`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000568f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000568f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000567f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000567f`

## string_xrefs

- `0x140005675`: `kernelbase.dll`

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
0x140005660  mov     [rsp+arg_0], rbx
0x140005665  mov     [rsp+arg_8], rsi
0x14000566a  push    rdi
0x14000566b  sub     rsp, 20h
0x14000566f  mov     rsi, rcx
0x140005672  mov     ebx, r8d
0x140005675  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000567c  mov     rdi, rdx
0x14000567f  call    cs:__imp_GetModuleHandleW
0x140005685  mov     rcx, rax; hModule
0x140005688  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000568f  call    cs:__imp_GetProcAddress
0x140005695  test    rax, rax
0x140005698  jz      short loc_1400056A8
0x14000569a  mov     r8d, ebx
0x14000569d  mov     rdx, rdi
0x1400056a0  mov     rcx, rsi
0x1400056a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400056a8  mov     rbx, [rsp+28h+arg_0]
0x1400056ad  mov     rsi, [rsp+28h+arg_8]
0x1400056b2  add     rsp, 20h
0x1400056b6  pop     rdi
0x1400056b7  retn
```
