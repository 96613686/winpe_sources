# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18001b490`
- end: `0x18001b4e7`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `87`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800128e8`
- `0x18001b490`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b4af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b4af`

## string_xrefs

- `0x18001b4a5`: `kernelbase.dll`

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
0x18001b490  mov     [rsp+arg_0], rbx
0x18001b495  mov     [rsp+arg_8], rsi
0x18001b49a  push    rdi
0x18001b49b  sub     rsp, 20h
0x18001b49f  mov     rsi, rcx
0x18001b4a2  mov     ebx, r8d
0x18001b4a5  lea     rcx, aKernelbaseDll_0; "kernelbase.dll"
0x18001b4ac  mov     rdi, rdx
0x18001b4af  call    cs:__imp_GetModuleHandleW
0x18001b4b6  nop     dword ptr [rax+rax+00h]
0x18001b4bb  mov     rcx, rax
0x18001b4be  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18001b4c3  test    rax, rax
0x18001b4c6  jz      short loc_18001B4D6
0x18001b4c8  mov     r8d, ebx
0x18001b4cb  mov     rdx, rdi
0x18001b4ce  mov     rcx, rsi
0x18001b4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4d6  mov     rbx, [rsp+28h+arg_0]
0x18001b4db  mov     rsi, [rsp+28h+arg_8]
0x18001b4e0  add     rsp, 20h
0x18001b4e4  pop     rdi
0x18001b4e5  retn
```
