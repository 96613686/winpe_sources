# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x10008d10`
- end: `0x10008d4b`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YGXPAU_EXCEPTION_RECORD@@PAU_CONTEXT@@K@Z`
- size: `59`
- prototype: `void __stdcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x10008d10`
- `0x1000eb60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10008d27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10008d27`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x10008d1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x10008d1b`

## string_xrefs

- `0x10008d16`: `kernelbase.dll`

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
0x10008d10  mov     edi, edi
0x10008d12  push    ebp
0x10008d13  mov     ebp, esp
0x10008d15  push    esi
0x10008d16  push    offset aKernelbaseDll; "kernelbase.dll"
0x10008d1b  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x10008d21  push    offset aRaisefailfaste; "RaiseFailFastException"
0x10008d26  push    eax; hModule
0x10008d27  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10008d2d  mov     esi, eax
0x10008d2f  test    esi, esi
0x10008d31  jz      short loc_10008D46
0x10008d33  push    [ebp+arg_8]
0x10008d36  mov     ecx, esi
0x10008d38  push    [ebp+arg_4]; unsigned int
0x10008d3b  push    [ebp+this]; void *
0x10008d3e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10008d44  call    esi
0x10008d46  pop     esi
0x10008d47  pop     ebp
0x10008d48  retn    0Ch
```
