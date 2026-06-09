# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x140003018`
- end: `0x1400030cc`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140003e48`
- `0x1400042ec`
- `0x14000552c`

## callees

- `0x140003018`
- `0x140007010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400030bb`
- `KERNEL32!GetLastError` at `0x1400030bb`
- `KERNEL32!GetProcAddress` at `0x140003052`
- `KERNEL32!GetProcAddress` at `0x14000307f`
- `KERNEL32!GetProcAddress` at `0x140003052`
- `KERNEL32!GetProcAddress` at `0x14000307f`
- `KERNEL32!LoadLibraryExW` at `0x14000306a`
- `KERNEL32!LoadLibraryExW` at `0x14000306a`
- `KERNEL32!GetModuleHandleW` at `0x14000303d`
- `KERNEL32!GetModuleHandleW` at `0x14000303d`

## string_xrefs

- `0x140003036`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x140003048`: `RegDeleteKeyExW`
- `0x140003061`: `advapi32.dll`
- `0x140003075`: `RegDeleteKeyW`

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
0x140003018  mov     [rsp+arg_0], rbx
0x14000301d  push    rdi
0x14000301e  sub     rsp, 30h
0x140003022  cmp     qword ptr [rcx+8], 0
0x140003027  mov     rdi, rdx
0x14000302a  mov     rbx, rcx
0x14000302d  jnz     short loc_140003089
0x14000302f  cmp     qword ptr [rcx+10h], 0
0x140003034  jnz     short loc_140003089
0x140003036  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x14000303d  call    cs:__imp_GetModuleHandleW
0x140003043  test    rax, rax
0x140003046  jz      short loc_14000305E
0x140003048  lea     rdx, ProcName; "RegDeleteKeyExW"
0x14000304f  mov     rcx, rax; hModule
0x140003052  call    cs:__imp_GetProcAddress
0x140003058  mov     [rbx+8], rax
0x14000305c  jmp     short loc_140003089
0x14000305e  xor     r8d, r8d; dwFlags
0x140003061  lea     rcx, LibFileName; "advapi32.dll"
0x140003068  xor     edx, edx; hFile
0x14000306a  call    cs:__imp_LoadLibraryExW
0x140003070  test    rax, rax
0x140003073  jz      short loc_140003089
0x140003075  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x14000307c  mov     rcx, rax; hModule
0x14000307f  call    cs:__imp_GetProcAddress
0x140003085  mov     [rbx+10h], rax
0x140003089  mov     rax, [rbx+8]
0x14000308d  test    rax, rax
0x140003090  jz      short loc_1400030A5
0x140003092  mov     rcx, [rbx]
0x140003095  xor     r9d, r9d
0x140003098  xor     r8d, r8d
0x14000309b  mov     rdx, rdi
0x14000309e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400030a3  jmp     short loc_1400030C1
0x1400030a5  mov     rax, [rbx+10h]
0x1400030a9  test    rax, rax
0x1400030ac  jz      short loc_1400030BB
0x1400030ae  mov     rcx, [rbx]
0x1400030b1  mov     rdx, rdi
0x1400030b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400030b9  jmp     short loc_1400030C1
0x1400030bb  call    cs:__imp_GetLastError
0x1400030c1  mov     rbx, [rsp+38h+arg_0]
0x1400030c6  add     rsp, 30h
0x1400030ca  pop     rdi
0x1400030cb  retn
```
