# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x14000bd70`
- end: `0x14000bdd5`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000bd70`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000bda5`
- `KERNEL32!GetProcAddress` at `0x14000bda5`
- `KERNEL32!GetModuleHandleW` at `0x14000bd8f`
- `KERNEL32!GetModuleHandleW` at `0x14000bd8f`

## string_xrefs

- `0x14000bd85`: `kernelbase.dll`

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
0x14000bd70  mov     [rsp+arg_0], rbx
0x14000bd75  mov     [rsp+arg_8], rsi
0x14000bd7a  push    rdi
0x14000bd7b  sub     rsp, 20h
0x14000bd7f  mov     rsi, rcx
0x14000bd82  mov     ebx, r8d
0x14000bd85  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000bd8c  mov     rdi, rdx
0x14000bd8f  call    cs:__imp_GetModuleHandleW
0x14000bd96  nop     dword ptr [rax+rax+00h]
0x14000bd9b  mov     rcx, rax; hModule
0x14000bd9e  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x14000bda5  call    cs:__imp_GetProcAddress
0x14000bdac  nop     dword ptr [rax+rax+00h]
0x14000bdb1  test    rax, rax
0x14000bdb4  jz      short loc_14000BDC4
0x14000bdb6  mov     r8d, ebx
0x14000bdb9  mov     rdx, rdi
0x14000bdbc  mov     rcx, rsi
0x14000bdbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bdc4  mov     rbx, [rsp+28h+arg_0]
0x14000bdc9  mov     rsi, [rsp+28h+arg_8]
0x14000bdce  add     rsp, 20h
0x14000bdd2  pop     rdi
0x14000bdd3  retn
```
