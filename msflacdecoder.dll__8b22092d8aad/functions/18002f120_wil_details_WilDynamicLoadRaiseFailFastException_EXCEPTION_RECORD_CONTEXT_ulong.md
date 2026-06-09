# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18002f120`
- end: `0x18002f170`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180029548`
- `0x18002f120`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f13f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f13f`

## string_xrefs

- `0x18002f135`: `kernelbase.dll`

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
0x18002f120  mov     [rsp+arg_0], rbx
0x18002f125  mov     [rsp+arg_8], rsi
0x18002f12a  push    rdi
0x18002f12b  sub     rsp, 20h
0x18002f12f  mov     rsi, rcx
0x18002f132  mov     ebx, r8d
0x18002f135  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002f13c  mov     rdi, rdx
0x18002f13f  call    cs:__imp_GetModuleHandleW
0x18002f145  mov     rcx, rax
0x18002f148  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18002f14d  test    rax, rax
0x18002f150  jz      short loc_18002F160
0x18002f152  mov     r8d, ebx
0x18002f155  mov     rdx, rdi
0x18002f158  mov     rcx, rsi
0x18002f15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f160  mov     rbx, [rsp+28h+arg_0]
0x18002f165  mov     rsi, [rsp+28h+arg_8]
0x18002f16a  add     rsp, 20h
0x18002f16e  pop     rdi
0x18002f16f  retn
```
