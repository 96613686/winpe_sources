# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180011e84`
- end: `0x180011f38`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180012d14`
- `0x180013134`
- `0x180041a34`

## callees

- `0x180011e84`
- `0x18004a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180011ea9`
- `KERNEL32!GetModuleHandleW` at `0x180011ea9`
- `KERNEL32!LoadLibraryExW` at `0x180011ed6`
- `KERNEL32!LoadLibraryExW` at `0x180011ed6`
- `KERNEL32!GetProcAddress` at `0x180011ebe`
- `KERNEL32!GetProcAddress` at `0x180011eeb`
- `KERNEL32!GetProcAddress` at `0x180011ebe`
- `KERNEL32!GetProcAddress` at `0x180011eeb`
- `KERNEL32!GetLastError` at `0x180011f27`
- `KERNEL32!GetLastError` at `0x180011f27`

## string_xrefs

- `0x180011ea2`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180011eb4`: `RegDeleteKeyExW`
- `0x180011ecd`: `advapi32.dll`
- `0x180011ee1`: `RegDeleteKeyW`

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
0x180011e84  mov     [rsp+arg_0], rbx
0x180011e89  push    rdi
0x180011e8a  sub     rsp, 30h
0x180011e8e  cmp     qword ptr [rcx+8], 0
0x180011e93  mov     rdi, rdx
0x180011e96  mov     rbx, rcx
0x180011e99  jnz     short loc_180011EF5
0x180011e9b  cmp     qword ptr [rcx+10h], 0
0x180011ea0  jnz     short loc_180011EF5
0x180011ea2  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180011ea9  call    cs:__imp_GetModuleHandleW
0x180011eaf  test    rax, rax
0x180011eb2  jz      short loc_180011ECA
0x180011eb4  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180011ebb  mov     rcx, rax; hModule
0x180011ebe  call    cs:__imp_GetProcAddress
0x180011ec4  mov     [rbx+8], rax
0x180011ec8  jmp     short loc_180011EF5
0x180011eca  xor     r8d, r8d; dwFlags
0x180011ecd  lea     rcx, LibFileName; "advapi32.dll"
0x180011ed4  xor     edx, edx; hFile
0x180011ed6  call    cs:__imp_LoadLibraryExW
0x180011edc  test    rax, rax
0x180011edf  jz      short loc_180011EF5
0x180011ee1  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180011ee8  mov     rcx, rax; hModule
0x180011eeb  call    cs:__imp_GetProcAddress
0x180011ef1  mov     [rbx+10h], rax
0x180011ef5  mov     rax, [rbx+8]
0x180011ef9  test    rax, rax
0x180011efc  jz      short loc_180011F11
0x180011efe  mov     rcx, [rbx]
0x180011f01  xor     r9d, r9d
0x180011f04  xor     r8d, r8d
0x180011f07  mov     rdx, rdi
0x180011f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f0f  jmp     short loc_180011F2D
0x180011f11  mov     rax, [rbx+10h]
0x180011f15  test    rax, rax
0x180011f18  jz      short loc_180011F27
0x180011f1a  mov     rcx, [rbx]
0x180011f1d  mov     rdx, rdi
0x180011f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f25  jmp     short loc_180011F2D
0x180011f27  call    cs:__imp_GetLastError
0x180011f2d  mov     rbx, [rsp+38h+arg_0]
0x180011f32  add     rsp, 30h
0x180011f36  pop     rdi
0x180011f37  retn
```
