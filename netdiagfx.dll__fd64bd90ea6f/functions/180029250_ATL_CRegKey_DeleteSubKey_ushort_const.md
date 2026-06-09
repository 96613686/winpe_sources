# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180029250`
- end: `0x180029305`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180029788`

## callees

- `0x180029250`
- `0x18002f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002928a`
- `KERNEL32!GetProcAddress` at `0x1800292b7`
- `KERNEL32!GetProcAddress` at `0x18002928a`
- `KERNEL32!GetProcAddress` at `0x1800292b7`
- `KERNEL32!GetModuleHandleW` at `0x180029275`
- `KERNEL32!GetModuleHandleW` at `0x180029275`
- `KERNEL32!GetLastError` at `0x1800292f3`
- `KERNEL32!GetLastError` at `0x1800292f3`
- `KERNEL32!LoadLibraryExW` at `0x1800292a2`
- `KERNEL32!LoadLibraryExW` at `0x1800292a2`

## string_xrefs

- `0x18002926e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180029280`: `RegDeleteKeyExW`
- `0x18002929b`: `advapi32.dll`
- `0x1800292ad`: `RegDeleteKeyW`

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
0x180029250  mov     [rsp+arg_0], rbx
0x180029255  push    rdi
0x180029256  sub     rsp, 30h
0x18002925a  mov     rdi, rdx
0x18002925d  mov     rbx, rcx
0x180029260  cmp     qword ptr [rcx+8], 0
0x180029265  jnz     short loc_1800292C1
0x180029267  cmp     qword ptr [rcx+10h], 0
0x18002926c  jnz     short loc_1800292C1
0x18002926e  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180029275  call    cs:__imp_GetModuleHandleW
0x18002927b  test    rax, rax
0x18002927e  jz      short loc_180029296
0x180029280  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180029287  mov     rcx, rax; hModule
0x18002928a  call    cs:__imp_GetProcAddress
0x180029290  mov     [rbx+8], rax
0x180029294  jmp     short loc_1800292C1
0x180029296  xor     r8d, r8d; dwFlags
0x180029299  xor     edx, edx; hFile
0x18002929b  lea     rcx, LibFileName; "advapi32.dll"
0x1800292a2  call    cs:__imp_LoadLibraryExW
0x1800292a8  test    rax, rax
0x1800292ab  jz      short loc_1800292C1
0x1800292ad  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800292b4  mov     rcx, rax; hModule
0x1800292b7  call    cs:__imp_GetProcAddress
0x1800292bd  mov     [rbx+10h], rax
0x1800292c1  mov     rax, [rbx+8]
0x1800292c5  test    rax, rax
0x1800292c8  jz      short loc_1800292DD
0x1800292ca  xor     r9d, r9d
0x1800292cd  xor     r8d, r8d
0x1800292d0  mov     rdx, rdi
0x1800292d3  mov     rcx, [rbx]
0x1800292d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292db  jmp     short loc_1800292FA
0x1800292dd  mov     rax, [rbx+10h]
0x1800292e1  test    rax, rax
0x1800292e4  jz      short loc_1800292F3
0x1800292e6  mov     rdx, rdi
0x1800292e9  mov     rcx, [rbx]
0x1800292ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292f1  jmp     short loc_1800292FA
0x1800292f3  call    cs:__imp_GetLastError
0x1800292f9  nop
0x1800292fa  mov     rbx, [rsp+38h+arg_0]
0x1800292ff  add     rsp, 30h
0x180029303  pop     rdi
0x180029304  retn
```
