# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180069278`
- end: `0x180069346`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `206`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180069594`

## callees

- `0x180069278`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1800692d1`
- `KERNEL32!LoadLibraryW` at `0x1800692d1`
- `KERNEL32!GetProcAddress` at `0x1800692b8`
- `KERNEL32!GetProcAddress` at `0x1800692ec`
- `KERNEL32!GetProcAddress` at `0x1800692b8`
- `KERNEL32!GetProcAddress` at `0x1800692ec`
- `KERNEL32!GetModuleHandleW` at `0x18006929d`
- `KERNEL32!GetModuleHandleW` at `0x18006929d`
- `KERNEL32!GetLastError` at `0x18006932e`
- `KERNEL32!GetLastError` at `0x18006932e`

## string_xrefs

- `0x180069296`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800692ae`: `RegDeleteKeyExW`
- `0x1800692ca`: `advapi32.dll`
- `0x1800692e2`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE LibraryW; // rax
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
      LibraryW = LoadLibraryW(L"advapi32.dll");
      if ( LibraryW )
        *((_QWORD *)this + 2) = GetProcAddress(LibraryW, "RegDeleteKeyW");
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
0x180069278  mov     [rsp+arg_0], rbx
0x18006927d  push    rdi
0x18006927e  sub     rsp, 30h
0x180069282  cmp     qword ptr [rcx+8], 0
0x180069287  mov     rdi, rdx
0x18006928a  mov     rbx, rcx
0x18006928d  jnz     short loc_1800692FC
0x18006928f  cmp     qword ptr [rcx+10h], 0
0x180069294  jnz     short loc_1800692FC
0x180069296  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18006929d  call    cs:__imp_GetModuleHandleW
0x1800692a4  nop     dword ptr [rax+rax+00h]
0x1800692a9  test    rax, rax
0x1800692ac  jz      short loc_1800692CA
0x1800692ae  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800692b5  mov     rcx, rax; hModule
0x1800692b8  call    cs:__imp_GetProcAddress
0x1800692bf  nop     dword ptr [rax+rax+00h]
0x1800692c4  mov     [rbx+8], rax
0x1800692c8  jmp     short loc_1800692FC
0x1800692ca  lea     rcx, LibFileName; "advapi32.dll"
0x1800692d1  call    cs:__imp_LoadLibraryW
0x1800692d8  nop     dword ptr [rax+rax+00h]
0x1800692dd  test    rax, rax
0x1800692e0  jz      short loc_1800692FC
0x1800692e2  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800692e9  mov     rcx, rax; hModule
0x1800692ec  call    cs:__imp_GetProcAddress
0x1800692f3  nop     dword ptr [rax+rax+00h]
0x1800692f8  mov     [rbx+10h], rax
0x1800692fc  mov     rax, [rbx+8]
0x180069300  test    rax, rax
0x180069303  jz      short loc_180069318
0x180069305  mov     rcx, [rbx]
0x180069308  xor     r9d, r9d
0x18006930b  xor     r8d, r8d
0x18006930e  mov     rdx, rdi
0x180069311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069316  jmp     short loc_18006933A
0x180069318  mov     rax, [rbx+10h]
0x18006931c  test    rax, rax
0x18006931f  jz      short loc_18006932E
0x180069321  mov     rcx, [rbx]
0x180069324  mov     rdx, rdi
0x180069327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006932c  jmp     short loc_18006933A
0x18006932e  call    cs:__imp_GetLastError
0x180069335  nop     dword ptr [rax+rax+00h]
0x18006933a  mov     rbx, [rsp+38h+arg_0]
0x18006933f  add     rsp, 30h
0x180069343  pop     rdi
0x180069344  retn
```
