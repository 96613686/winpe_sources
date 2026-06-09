# CreateSOSHostInterface(SOSHOST_CLIENTID,ushort const * const,ISOSHost * * const)

- ea: `0x100469f80`
- end: `0x10046a008`
- name: `?CreateSOSHostInterface@@YAJW4SOSHOST_CLIENTID@@QEBGQEAPEAUISOSHost@@@Z`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10046a010`

## callees

- `0x100469f80`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x100469fa2`
- `KERNEL32!GetModuleHandleW` at `0x100469fa2`
- `KERNEL32!GetLastError` at `0x100469fdb`
- `KERNEL32!GetLastError` at `0x100469fdb`
- `KERNEL32!GetProcAddress` at `0x100469fb7`
- `KERNEL32!GetProcAddress` at `0x100469fb7`

## string_xrefs

- `0x100469f95`: `SQLOS.DLL`
- `0x100469fad`: `CreateVersionedSOSHostObject`

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
               &GUID_61dd042f_ec99_427f_92be_09c9a29161f3,
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
0x100469f80  mov     [rsp+arg_0], rbx
0x100469f85  mov     [rsp+arg_8], rsi
0x100469f8a  push    rdi
0x100469f8b  sub     rsp, 30h
0x100469f8f  and     qword ptr [r8], 0
0x100469f93  mov     esi, ecx
0x100469f95  lea     rcx, aSqlosDll; "SQLOS.DLL"
0x100469f9c  mov     rbx, r8
0x100469f9f  mov     rdi, rdx
0x100469fa2  call    cs:__imp_GetModuleHandleW
0x100469fa8  test    rax, rax
0x100469fab  jz      short loc_100469FF1
0x100469fad  lea     rdx, aCreateversione; "CreateVersionedSOSHostObject"
0x100469fb4  mov     rcx, rax; hModule
0x100469fb7  call    cs:__imp_GetProcAddress
0x100469fbd  test    rax, rax
0x100469fc0  jz      short loc_100469FDB
0x100469fc2  mov     r9, rbx
0x100469fc5  lea     rcx, _GUID_61dd042f_ec99_427f_92be_09c9a29161f3
0x100469fcc  mov     r8, rdi
0x100469fcf  mov     edx, esi
0x100469fd1  call    cs:__guard_dispatch_icall_fptr
0x100469fd7  mov     ecx, eax
0x100469fd9  jmp     short loc_100469FF6
0x100469fdb  call    cs:__imp_GetLastError
0x100469fe1  movzx   ecx, ax
0x100469fe4  or      ecx, 80070000h
0x100469fea  test    eax, eax
0x100469fec  cmovle  ecx, eax
0x100469fef  jmp     short loc_100469FF6
0x100469ff1  mov     ecx, 80040007h
0x100469ff6  mov     rbx, [rsp+38h+arg_0]
0x100469ffb  mov     eax, ecx
0x100469ffd  mov     rsi, [rsp+38h+arg_8]
0x10046a002  add     rsp, 30h
0x10046a006  pop     rdi
0x10046a007  retn
```
