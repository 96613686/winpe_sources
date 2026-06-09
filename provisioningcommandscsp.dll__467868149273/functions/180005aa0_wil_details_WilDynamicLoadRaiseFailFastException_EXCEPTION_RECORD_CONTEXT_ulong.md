# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180005aa0`
- end: `0x180005b05`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005aa0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005abf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005abf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005ad5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005ad5`

## string_xrefs

- `0x180005ab5`: `kernelbase.dll`

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
0x180005aa0  mov     [rsp+arg_0], rbx
0x180005aa5  mov     [rsp+arg_8], rsi
0x180005aaa  push    rdi
0x180005aab  sub     rsp, 20h
0x180005aaf  mov     rsi, rcx
0x180005ab2  mov     ebx, r8d
0x180005ab5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005abc  mov     rdi, rdx
0x180005abf  call    cs:__imp_GetModuleHandleW
0x180005ac6  nop     dword ptr [rax+rax+00h]
0x180005acb  mov     rcx, rax; hModule
0x180005ace  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180005ad5  call    cs:__imp_GetProcAddress
0x180005adc  nop     dword ptr [rax+rax+00h]
0x180005ae1  test    rax, rax
0x180005ae4  jz      short loc_180005AF4
0x180005ae6  mov     r8d, ebx
0x180005ae9  mov     rdx, rdi
0x180005aec  mov     rcx, rsi
0x180005aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af4  mov     rbx, [rsp+28h+arg_0]
0x180005af9  mov     rsi, [rsp+28h+arg_8]
0x180005afe  add     rsp, 20h
0x180005b02  pop     rdi
0x180005b03  retn
```
