# CreateSOSHostInterface(SOSHOST_CLIENTID,wchar_t const * const,ISOSHost * * const)

- ea: `0x1801323c8`
- end: `0x180132450`
- name: `?CreateSOSHostInterface@@YAJW4SOSHOST_CLIENTID@@QEB_WQEAPEAUISOSHost@@@Z`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180132458`

## callees

- `0x1801323c8`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180132423`
- `KERNEL32!GetLastError` at `0x180132423`
- `KERNEL32!GetProcAddress` at `0x1801323ff`
- `KERNEL32!GetProcAddress` at `0x1801323ff`
- `KERNEL32!GetModuleHandleW` at `0x1801323ea`
- `KERNEL32!GetModuleHandleW` at `0x1801323ea`

## string_xrefs

- `0x1801323dd`: `SQLOS.DLL`
- `0x1801323f5`: `CreateVersionedSOSHostObject`

## pseudocode

```c
__int64 __fastcall CreateSOSHostInterface(unsigned int a1, __int64 a2, _QWORD *a3)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned int v8; // ecx
  signed int LastError; // eax

  *a3 = 0;
  ModuleHandleW = GetModuleHandleW(L"SQLOS.DLL");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "CreateVersionedSOSHostObject");
    if ( ProcAddress )
    {
      return ((unsigned int (__fastcall *)(GUID *, _QWORD, __int64, _QWORD *))ProcAddress)(
               &GUID_3e1aeffe_a6ff_4774_a3ea_dc1517ed7dfa,
               a1,
               a2,
               a3);
    }
    else
    {
      LastError = GetLastError();
      v8 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        return (unsigned int)LastError;
    }
  }
  else
  {
    return (unsigned int)-2147221497;
  }
  return v8;
}

```

## disassembly

```asm
0x1801323c8  mov     [rsp+arg_0], rbx
0x1801323cd  mov     [rsp+arg_8], rsi
0x1801323d2  push    rdi
0x1801323d3  sub     rsp, 30h
0x1801323d7  and     qword ptr [r8], 0
0x1801323db  mov     esi, ecx
0x1801323dd  lea     rcx, aSqlosDll; "SQLOS.DLL"
0x1801323e4  mov     rbx, r8
0x1801323e7  mov     rdi, rdx
0x1801323ea  call    cs:__imp_GetModuleHandleW
0x1801323f0  test    rax, rax
0x1801323f3  jz      short loc_180132439
0x1801323f5  lea     rdx, aCreateversione; "CreateVersionedSOSHostObject"
0x1801323fc  mov     rcx, rax; hModule
0x1801323ff  call    cs:__imp_GetProcAddress
0x180132405  test    rax, rax
0x180132408  jz      short loc_180132423
0x18013240a  mov     r9, rbx
0x18013240d  lea     rcx, _GUID_3e1aeffe_a6ff_4774_a3ea_dc1517ed7dfa
0x180132414  mov     r8, rdi
0x180132417  mov     edx, esi
0x180132419  call    cs:__guard_dispatch_icall_fptr
0x18013241f  mov     ecx, eax
0x180132421  jmp     short loc_18013243E
0x180132423  call    cs:__imp_GetLastError
0x180132429  movzx   ecx, ax
0x18013242c  or      ecx, 80070000h
0x180132432  test    eax, eax
0x180132434  cmovle  ecx, eax
0x180132437  jmp     short loc_18013243E
0x180132439  mov     ecx, 80040007h
0x18013243e  mov     rbx, [rsp+38h+arg_0]
0x180132443  mov     eax, ecx
0x180132445  mov     rsi, [rsp+38h+arg_8]
0x18013244a  add     rsp, 30h
0x18013244e  pop     rdi
0x18013244f  retn
```
