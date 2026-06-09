# ATL::CRegKey::DeleteSubKey(char const *)

- ea: `0x18003ff6c`
- end: `0x18004001a`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBD@Z`
- size: `174`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180040308`

## callees

- `0x18003ff6c`
- `0x1800422cc`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x18003ff91`
- `KERNEL32!GetModuleHandleA` at `0x18003ff91`
- `KERNEL32!GetProcAddress` at `0x18003ffa6`
- `KERNEL32!GetProcAddress` at `0x18003ffcd`
- `KERNEL32!GetProcAddress` at `0x18003ffa6`
- `KERNEL32!GetProcAddress` at `0x18003ffcd`
- `KERNEL32!GetLastError` at `0x180040009`
- `KERNEL32!GetLastError` at `0x180040009`

## string_xrefs

- `0x18003ff8a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18003ff9c`: `RegDeleteKeyExA`
- `0x18003ffb2`: `advapi32.dll`
- `0x18003ffc3`: `RegDeleteKeyA`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const char *a2)
{
  HMODULE ModuleHandleA; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v6)(_QWORD, const char *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v8)(_QWORD, const char *); // rax

  if ( *(_OWORD *)((char *)this + 8) == 0 )
  {
    ModuleHandleA = GetModuleHandleA("API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
    if ( ModuleHandleA )
    {
      *((_QWORD *)this + 1) = GetProcAddress(ModuleHandleA, "RegDeleteKeyExA");
    }
    else
    {
      Library = IsolationAwareLoadLibraryExA("advapi32.dll");
      if ( Library )
        *((_QWORD *)this + 2) = GetProcAddress(Library, "RegDeleteKeyA");
    }
  }
  v6 = (__int64 (__fastcall *)(_QWORD, const char *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v6 )
    return v6(*(_QWORD *)this, a2, 0, 0);
  v8 = (__int64 (__fastcall *)(_QWORD, const char *))*((_QWORD *)this + 2);
  if ( v8 )
    return v8(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x18003ff6c  mov     [rsp+arg_0], rbx
0x18003ff71  push    rdi
0x18003ff72  sub     rsp, 30h
0x18003ff76  cmp     qword ptr [rcx+8], 0
0x18003ff7b  mov     rdi, rdx
0x18003ff7e  mov     rbx, rcx
0x18003ff81  jnz     short loc_18003FFD7
0x18003ff83  cmp     qword ptr [rcx+10h], 0
0x18003ff88  jnz     short loc_18003FFD7
0x18003ff8a  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18003ff91  call    cs:__imp_GetModuleHandleA
0x18003ff97  test    rax, rax
0x18003ff9a  jz      short loc_18003FFB2
0x18003ff9c  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExA"
0x18003ffa3  mov     rcx, rax; hModule
0x18003ffa6  call    cs:__imp_GetProcAddress
0x18003ffac  mov     [rbx+8], rax
0x18003ffb0  jmp     short loc_18003FFD7
0x18003ffb2  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x18003ffb9  call    IsolationAwareLoadLibraryExA
0x18003ffbe  test    rax, rax
0x18003ffc1  jz      short loc_18003FFD7
0x18003ffc3  lea     rdx, aRegdeletekeya; "RegDeleteKeyA"
0x18003ffca  mov     rcx, rax; hModule
0x18003ffcd  call    cs:__imp_GetProcAddress
0x18003ffd3  mov     [rbx+10h], rax
0x18003ffd7  mov     rax, [rbx+8]
0x18003ffdb  test    rax, rax
0x18003ffde  jz      short loc_18003FFF3
0x18003ffe0  mov     rcx, [rbx]
0x18003ffe3  xor     r9d, r9d
0x18003ffe6  xor     r8d, r8d
0x18003ffe9  mov     rdx, rdi
0x18003ffec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fff1  jmp     short loc_18004000F
0x18003fff3  mov     rax, [rbx+10h]
0x18003fff7  test    rax, rax
0x18003fffa  jz      short loc_180040009
0x18003fffc  mov     rcx, [rbx]
0x18003ffff  mov     rdx, rdi
0x180040002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040007  jmp     short loc_18004000F
0x180040009  call    cs:__imp_GetLastError
0x18004000f  mov     rbx, [rsp+38h+arg_0]
0x180040014  add     rsp, 30h
0x180040018  pop     rdi
0x180040019  retn
```
