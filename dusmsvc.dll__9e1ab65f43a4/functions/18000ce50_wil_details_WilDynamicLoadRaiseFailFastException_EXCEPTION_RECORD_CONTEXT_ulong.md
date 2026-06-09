# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000ce50`
- end: `0x18000cea0`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009ea4`
- `0x18000ce50`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ce6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ce6f`

## string_xrefs

- `0x18000ce65`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  void (__fastcall *Proc)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD); // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  Proc = (void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,unsigned long)>(ModuleHandleW);
  if ( Proc )
    Proc(this, a2, v4);
}

```

## disassembly

```asm
0x18000ce50  mov     [rsp+arg_0], rbx
0x18000ce55  mov     [rsp+arg_8], rsi
0x18000ce5a  push    rdi
0x18000ce5b  sub     rsp, 20h
0x18000ce5f  mov     rsi, rcx
0x18000ce62  mov     ebx, r8d
0x18000ce65  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000ce6c  mov     rdi, rdx
0x18000ce6f  call    cs:__imp_GetModuleHandleW
0x18000ce75  mov     rcx, rax
0x18000ce78  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18000ce7d  test    rax, rax
0x18000ce80  jz      short loc_18000CE90
0x18000ce82  mov     r8d, ebx
0x18000ce85  mov     rdx, rdi
0x18000ce88  mov     rcx, rsi
0x18000ce8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce90  mov     rbx, [rsp+28h+arg_0]
0x18000ce95  mov     rsi, [rsp+28h+arg_8]
0x18000ce9a  add     rsp, 20h
0x18000ce9e  pop     rdi
0x18000ce9f  retn
```
