# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x140017180`
- end: `0x14001723a`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `186`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14001706c`

## callees

- `0x140017180`
- `0x140027010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140017233`
- `KERNEL32!GetProcAddress` at `0x1400171b3`
- `KERNEL32!GetProcAddress` at `0x1400171e0`
- `KERNEL32!GetProcAddress` at `0x1400171b3`
- `KERNEL32!GetProcAddress` at `0x1400171e0`
- `KERNEL32!GetModuleHandleW` at `0x14001719e`
- `KERNEL32!GetModuleHandleW` at `0x14001719e`
- `KERNEL32!LoadLibraryExW` at `0x1400171cb`
- `KERNEL32!LoadLibraryExW` at `0x1400171cb`

## string_xrefs

- `0x140017197`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1400171a9`: `RegDeleteKeyExW`
- `0x1400171c4`: `advapi32.dll`
- `0x1400171d6`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v5)(_QWORD, const wchar_t *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v7)(_QWORD, const wchar_t *); // rax

  if ( !*((_QWORD *)this + 1) && !*((_QWORD *)this + 2) )
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
  v5 = (__int64 (__fastcall *)(_QWORD, const wchar_t *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v5 )
    return v5(*(_QWORD *)this, L"osk", 0, 0);
  v7 = (__int64 (__fastcall *)(_QWORD, const wchar_t *))*((_QWORD *)this + 2);
  if ( v7 )
    return v7(*(_QWORD *)this, L"osk");
  else
    return GetLastError();
}

```

## disassembly

```asm
0x140017180  push    rbx
0x140017182  sub     rsp, 30h
0x140017186  mov     rbx, rcx
0x140017189  cmp     qword ptr [rcx+8], 0
0x14001718e  jnz     short loc_1400171EA
0x140017190  cmp     qword ptr [rcx+10h], 0
0x140017195  jnz     short loc_1400171EA
0x140017197  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x14001719e  call    cs:__imp_GetModuleHandleW
0x1400171a4  test    rax, rax
0x1400171a7  jz      short loc_1400171BF
0x1400171a9  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1400171b0  mov     rcx, rax; hModule
0x1400171b3  call    cs:__imp_GetProcAddress
0x1400171b9  mov     [rbx+8], rax
0x1400171bd  jmp     short loc_1400171EA
0x1400171bf  xor     r8d, r8d; dwFlags
0x1400171c2  xor     edx, edx; hFile
0x1400171c4  lea     rcx, LibFileName; "advapi32.dll"
0x1400171cb  call    cs:__imp_LoadLibraryExW
0x1400171d1  test    rax, rax
0x1400171d4  jz      short loc_1400171EA
0x1400171d6  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1400171dd  mov     rcx, rax; hModule
0x1400171e0  call    cs:__imp_GetProcAddress
0x1400171e6  mov     [rbx+10h], rax
0x1400171ea  mov     rax, [rbx+8]
0x1400171ee  test    rax, rax
0x1400171f1  jz      short loc_14001720F
0x1400171f3  xor     r9d, r9d
0x1400171f6  xor     r8d, r8d
0x1400171f9  lea     rdx, aOsk_1; "osk"
0x140017200  mov     rcx, [rbx]
0x140017203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017208  nop
0x140017209  add     rsp, 30h
0x14001720d  pop     rbx
0x14001720e  retn
0x14001720f  mov     rax, [rbx+10h]
0x140017213  test    rax, rax
0x140017216  jz      short loc_14001722E
0x140017218  lea     rdx, aOsk_1; "osk"
0x14001721f  mov     rcx, [rbx]
0x140017222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017227  nop
0x140017228  add     rsp, 30h
0x14001722c  pop     rbx
0x14001722d  retn
0x14001722e  add     rsp, 30h
0x140017232  pop     rbx
0x140017233  jmp     cs:__imp_GetLastError
```
