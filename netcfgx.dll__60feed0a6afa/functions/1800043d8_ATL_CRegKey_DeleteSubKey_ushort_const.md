# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800043d8`
- end: `0x18000448d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004d58`
- `0x18000521c`

## callees

- `0x1800043d8`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000447b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000447b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800043fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800043fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004412`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000443f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004412`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000443f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000442a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000442a`

## string_xrefs

- `0x1800043f6`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180004408`: `RegDeleteKeyExW`
- `0x180004423`: `advapi32.dll`
- `0x180004435`: `RegDeleteKeyW`

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
0x1800043d8  mov     [rsp+arg_0], rbx
0x1800043dd  push    rdi
0x1800043de  sub     rsp, 30h
0x1800043e2  mov     rdi, rdx
0x1800043e5  mov     rbx, rcx
0x1800043e8  cmp     qword ptr [rcx+8], 0
0x1800043ed  jnz     short loc_180004449
0x1800043ef  cmp     qword ptr [rcx+10h], 0
0x1800043f4  jnz     short loc_180004449
0x1800043f6  lea     rcx, aApiMsWinCoreLo_1; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800043fd  call    cs:__imp_GetModuleHandleW
0x180004403  test    rax, rax
0x180004406  jz      short loc_18000441E
0x180004408  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000440f  mov     rcx, rax; hModule
0x180004412  call    cs:__imp_GetProcAddress
0x180004418  mov     [rbx+8], rax
0x18000441c  jmp     short loc_180004449
0x18000441e  xor     r8d, r8d; dwFlags
0x180004421  xor     edx, edx; hFile
0x180004423  lea     rcx, LibFileName; "advapi32.dll"
0x18000442a  call    cs:__imp_LoadLibraryExW
0x180004430  test    rax, rax
0x180004433  jz      short loc_180004449
0x180004435  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000443c  mov     rcx, rax; hModule
0x18000443f  call    cs:__imp_GetProcAddress
0x180004445  mov     [rbx+10h], rax
0x180004449  mov     rax, [rbx+8]
0x18000444d  test    rax, rax
0x180004450  jz      short loc_180004465
0x180004452  xor     r9d, r9d
0x180004455  xor     r8d, r8d
0x180004458  mov     rdx, rdi
0x18000445b  mov     rcx, [rbx]
0x18000445e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004463  jmp     short loc_180004482
0x180004465  mov     rax, [rbx+10h]
0x180004469  test    rax, rax
0x18000446c  jz      short loc_18000447B
0x18000446e  mov     rdx, rdi
0x180004471  mov     rcx, [rbx]
0x180004474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004479  jmp     short loc_180004482
0x18000447b  call    cs:__imp_GetLastError
0x180004481  nop
0x180004482  mov     rbx, [rsp+38h+arg_0]
0x180004487  add     rsp, 30h
0x18000448b  pop     rdi
0x18000448c  retn
```
