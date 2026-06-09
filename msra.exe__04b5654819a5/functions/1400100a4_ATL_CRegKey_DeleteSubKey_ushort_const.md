# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1400100a4`
- end: `0x140010178`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1400154e0`
- `0x140015bdc`

## callees

- `0x1400100a4`
- `0x14004d010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140010102`
- `KERNEL32!LoadLibraryExW` at `0x140010102`
- `KERNEL32!GetModuleHandleW` at `0x1400100c9`
- `KERNEL32!GetModuleHandleW` at `0x1400100c9`
- `KERNEL32!GetProcAddress` at `0x1400100e4`
- `KERNEL32!GetProcAddress` at `0x14001011d`
- `KERNEL32!GetProcAddress` at `0x1400100e4`
- `KERNEL32!GetProcAddress` at `0x14001011d`
- `KERNEL32!GetLastError` at `0x14001015f`
- `KERNEL32!GetLastError` at `0x14001015f`

## string_xrefs

- `0x1400100c2`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1400100da`: `RegDeleteKeyExW`
- `0x1400100fb`: `advapi32.dll`
- `0x140010113`: `RegDeleteKeyW`

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
0x1400100a4  mov     [rsp+arg_0], rbx
0x1400100a9  push    rdi
0x1400100aa  sub     rsp, 30h
0x1400100ae  mov     rdi, rdx
0x1400100b1  mov     rbx, rcx
0x1400100b4  cmp     qword ptr [rcx+8], 0
0x1400100b9  jnz     short loc_14001012D
0x1400100bb  cmp     qword ptr [rcx+10h], 0
0x1400100c0  jnz     short loc_14001012D
0x1400100c2  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1400100c9  call    cs:__imp_GetModuleHandleW
0x1400100d0  nop     dword ptr [rax+rax+00h]
0x1400100d5  test    rax, rax
0x1400100d8  jz      short loc_1400100F6
0x1400100da  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1400100e1  mov     rcx, rax; hModule
0x1400100e4  call    cs:__imp_GetProcAddress
0x1400100eb  nop     dword ptr [rax+rax+00h]
0x1400100f0  mov     [rbx+8], rax
0x1400100f4  jmp     short loc_14001012D
0x1400100f6  xor     r8d, r8d; dwFlags
0x1400100f9  xor     edx, edx; hFile
0x1400100fb  lea     rcx, LibFileName; "advapi32.dll"
0x140010102  call    cs:__imp_LoadLibraryExW
0x140010109  nop     dword ptr [rax+rax+00h]
0x14001010e  test    rax, rax
0x140010111  jz      short loc_14001012D
0x140010113  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x14001011a  mov     rcx, rax; hModule
0x14001011d  call    cs:__imp_GetProcAddress
0x140010124  nop     dword ptr [rax+rax+00h]
0x140010129  mov     [rbx+10h], rax
0x14001012d  mov     rax, [rbx+8]
0x140010131  test    rax, rax
0x140010134  jz      short loc_140010149
0x140010136  xor     r9d, r9d
0x140010139  xor     r8d, r8d
0x14001013c  mov     rdx, rdi
0x14001013f  mov     rcx, [rbx]
0x140010142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010147  jmp     short loc_14001016C
0x140010149  mov     rax, [rbx+10h]
0x14001014d  test    rax, rax
0x140010150  jz      short loc_14001015F
0x140010152  mov     rdx, rdi
0x140010155  mov     rcx, [rbx]
0x140010158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001015d  jmp     short loc_14001016C
0x14001015f  call    cs:__imp_GetLastError
0x140010166  nop     dword ptr [rax+rax+00h]
0x14001016b  nop
0x14001016c  mov     rbx, [rsp+38h+arg_0]
0x140010171  add     rsp, 30h
0x140010175  pop     rdi
0x140010176  retn
```
