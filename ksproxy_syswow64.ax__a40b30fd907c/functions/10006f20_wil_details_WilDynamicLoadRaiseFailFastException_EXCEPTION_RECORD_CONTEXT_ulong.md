# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x10006f20`
- end: `0x10006f5b`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YGXPAU_EXCEPTION_RECORD@@PAU_CONTEXT@@K@Z`
- size: `59`
- prototype: `void __stdcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x10006f20`
- `0x1002d510`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x10006f37`
- `KERNEL32!GetProcAddress` at `0x10006f37`
- `KERNEL32!GetModuleHandleW` at `0x10006f2b`
- `KERNEL32!GetModuleHandleW` at `0x10006f2b`

## string_xrefs

- `0x10006f26`: `kernelbase.dll`

## pseudocode

```c
void __stdcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3,
        unsigned int a4)
{
  HMODULE ModuleHandleW; // eax
  void (__stdcall *RaiseFailFastException)(PEXCEPTION_RECORD, PCONTEXT, DWORD); // eax

  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  RaiseFailFastException = (void (__stdcall *)(PEXCEPTION_RECORD, PCONTEXT, DWORD))GetProcAddress(
                                                                                     ModuleHandleW,
                                                                                     "RaiseFailFastException");
  if ( RaiseFailFastException )
    ((void (__thiscall *)(void (__stdcall *)(PEXCEPTION_RECORD, PCONTEXT, DWORD), wil::details *, struct _EXCEPTION_RECORD *, struct _CONTEXT *))RaiseFailFastException)(
      RaiseFailFastException,
      this,
      a2,
      a3);
}

```

## disassembly

```asm
0x10006f20  mov     edi, edi
0x10006f22  push    ebp
0x10006f23  mov     ebp, esp
0x10006f25  push    esi
0x10006f26  push    offset aKernelbaseDll; "kernelbase.dll"
0x10006f2b  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x10006f31  push    offset aRaisefailfaste; "RaiseFailFastException"
0x10006f36  push    eax; hModule
0x10006f37  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10006f3d  mov     esi, eax
0x10006f3f  test    esi, esi
0x10006f41  jz      short loc_10006F56
0x10006f43  push    [ebp+arg_8]
0x10006f46  mov     ecx, esi; this
0x10006f48  push    [ebp+arg_4]
0x10006f4b  push    [ebp+this]
0x10006f4e  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10006f54  call    esi
0x10006f56  pop     esi
0x10006f57  pop     ebp
0x10006f58  retn    0Ch
```
