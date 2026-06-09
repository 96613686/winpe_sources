# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180004008`
- end: `0x1800040b9`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `177`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180004be8`
- `0x180005130`

## callees

- `0x180004008`
- `0x180006984`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180004042`
- `KERNEL32!GetProcAddress` at `0x18000406c`
- `KERNEL32!GetProcAddress` at `0x180004042`
- `KERNEL32!GetProcAddress` at `0x18000406c`
- `KERNEL32!GetLastError` at `0x1800040a8`
- `KERNEL32!GetLastError` at `0x1800040a8`
- `KERNEL32!GetModuleHandleW` at `0x18000402d`
- `KERNEL32!GetModuleHandleW` at `0x18000402d`

## string_xrefs

- `0x180004026`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180004038`: `RegDeleteKeyExW`
- `0x180004051`: `advapi32.dll`
- `0x180004062`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  __int64 v5; // rdx
  HMODULE Library; // rax
  __int64 (__fastcall *v7)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v9)(_QWORD, const unsigned __int16 *); // rax

  if ( *(_OWORD *)((char *)this + 8) == 0 )
  {
    ModuleHandleW = GetModuleHandleW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
    if ( ModuleHandleW )
    {
      *((_QWORD *)this + 1) = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
    }
    else
    {
      Library = IsolationAwareLoadLibraryExW(L"advapi32.dll", v5, 0);
      if ( Library )
        *((_QWORD *)this + 2) = GetProcAddress(Library, "RegDeleteKeyW");
    }
  }
  v7 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v7 )
    return v7(*(_QWORD *)this, a2, 0, 0);
  v9 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *))*((_QWORD *)this + 2);
  if ( v9 )
    return v9(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180004008  mov     [rsp+arg_0], rbx
0x18000400d  push    rdi
0x18000400e  sub     rsp, 30h
0x180004012  cmp     qword ptr [rcx+8], 0
0x180004017  mov     rdi, rdx
0x18000401a  mov     rbx, rcx
0x18000401d  jnz     short loc_180004076
0x18000401f  cmp     qword ptr [rcx+10h], 0
0x180004024  jnz     short loc_180004076
0x180004026  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000402d  call    cs:__imp_GetModuleHandleW
0x180004033  test    rax, rax
0x180004036  jz      short loc_18000404E
0x180004038  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000403f  mov     rcx, rax; hModule
0x180004042  call    cs:__imp_GetProcAddress
0x180004048  mov     [rbx+8], rax
0x18000404c  jmp     short loc_180004076
0x18000404e  xor     r8d, r8d
0x180004051  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180004058  call    IsolationAwareLoadLibraryExW
0x18000405d  test    rax, rax
0x180004060  jz      short loc_180004076
0x180004062  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180004069  mov     rcx, rax; hModule
0x18000406c  call    cs:__imp_GetProcAddress
0x180004072  mov     [rbx+10h], rax
0x180004076  mov     rax, [rbx+8]
0x18000407a  test    rax, rax
0x18000407d  jz      short loc_180004092
0x18000407f  mov     rcx, [rbx]
0x180004082  xor     r9d, r9d
0x180004085  xor     r8d, r8d
0x180004088  mov     rdx, rdi
0x18000408b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004090  jmp     short loc_1800040AE
0x180004092  mov     rax, [rbx+10h]
0x180004096  test    rax, rax
0x180004099  jz      short loc_1800040A8
0x18000409b  mov     rcx, [rbx]
0x18000409e  mov     rdx, rdi
0x1800040a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040a6  jmp     short loc_1800040AE
0x1800040a8  call    cs:__imp_GetLastError
0x1800040ae  mov     rbx, [rsp+38h+arg_0]
0x1800040b3  add     rsp, 30h
0x1800040b7  pop     rdi
0x1800040b8  retn
```
