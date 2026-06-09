# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800071f4`
- end: `0x1800072a9`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180006d40`

## callees

- `0x1800071f4`
- `0x180039010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007297`
- `KERNEL32!GetLastError` at `0x180007297`
- `KERNEL32!GetProcAddress` at `0x18000722e`
- `KERNEL32!GetProcAddress` at `0x18000725b`
- `KERNEL32!GetProcAddress` at `0x18000722e`
- `KERNEL32!GetProcAddress` at `0x18000725b`
- `KERNEL32!LoadLibraryExW` at `0x180007246`
- `KERNEL32!LoadLibraryExW` at `0x180007246`
- `KERNEL32!GetModuleHandleW` at `0x180007219`
- `KERNEL32!GetModuleHandleW` at `0x180007219`

## string_xrefs

- `0x180007212`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180007224`: `RegDeleteKeyExW`
- `0x18000723f`: `advapi32.dll`
- `0x180007251`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v6)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v8)(_QWORD, const unsigned __int16 *); // rax

  if ( *(_OWORD *)((char *)this + 8) == 0 )
  {
    ModuleHandleW = GetModuleHandleW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
    if ( ModuleHandleW )
    {
      *((_QWORD *)this + 1) = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
    }
    else
    {
      Library = LoadLibraryExW(L"advapi32.dll", 0, 0);
      if ( Library )
        *((_QWORD *)this + 2) = GetProcAddress(Library, "RegDeleteKeyW");
    }
  }
  v6 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v6 )
    return v6(*(_QWORD *)this, a2, 0, 0);
  v8 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *))*((_QWORD *)this + 2);
  if ( v8 )
    return v8(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1800071f4  mov     [rsp+arg_0], rbx
0x1800071f9  push    rdi
0x1800071fa  sub     rsp, 30h
0x1800071fe  mov     rdi, rdx
0x180007201  mov     rbx, rcx
0x180007204  cmp     qword ptr [rcx+8], 0
0x180007209  jnz     short loc_180007265
0x18000720b  cmp     qword ptr [rcx+10h], 0
0x180007210  jnz     short loc_180007265
0x180007212  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180007219  call    cs:__imp_GetModuleHandleW
0x18000721f  test    rax, rax
0x180007222  jz      short loc_18000723A
0x180007224  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000722b  mov     rcx, rax; hModule
0x18000722e  call    cs:__imp_GetProcAddress
0x180007234  mov     [rbx+8], rax
0x180007238  jmp     short loc_180007265
0x18000723a  xor     r8d, r8d; dwFlags
0x18000723d  xor     edx, edx; hFile
0x18000723f  lea     rcx, LibFileName; "advapi32.dll"
0x180007246  call    cs:__imp_LoadLibraryExW
0x18000724c  test    rax, rax
0x18000724f  jz      short loc_180007265
0x180007251  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180007258  mov     rcx, rax; hModule
0x18000725b  call    cs:__imp_GetProcAddress
0x180007261  mov     [rbx+10h], rax
0x180007265  mov     rax, [rbx+8]
0x180007269  test    rax, rax
0x18000726c  jz      short loc_180007281
0x18000726e  xor     r9d, r9d
0x180007271  xor     r8d, r8d
0x180007274  mov     rdx, rdi
0x180007277  mov     rcx, [rbx]
0x18000727a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000727f  jmp     short loc_18000729E
0x180007281  mov     rax, [rbx+10h]
0x180007285  test    rax, rax
0x180007288  jz      short loc_180007297
0x18000728a  mov     rdx, rdi
0x18000728d  mov     rcx, [rbx]
0x180007290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007295  jmp     short loc_18000729E
0x180007297  call    cs:__imp_GetLastError
0x18000729d  nop
0x18000729e  mov     rbx, [rsp+38h+arg_0]
0x1800072a3  add     rsp, 30h
0x1800072a7  pop     rdi
0x1800072a8  retn
```
