# CallRegisterComponent(ushort const *,char *)

- ea: `0x18000eaec`
- end: `0x18000ebbb`
- name: `?CallRegisterComponent@@YAJPEBGPEAD@Z`
- size: `207`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a6c0`
- `0x18000a6e0`

## callees

- `0x18000eaec`
- `0x18000eca0`
- `0x180010010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000eb38`
- `msvcrt!wcscat_s` at `0x18000eb38`
- `KERNEL32!GetSystemDirectoryW` at `0x18000eb18`
- `KERNEL32!GetSystemDirectoryW` at `0x18000eb18`
- `KERNEL32!FreeLibrary` at `0x18000eb8b`
- `KERNEL32!FreeLibrary` at `0x18000eb8b`
- `KERNEL32!LoadLibraryExW` at `0x18000eb4b`
- `KERNEL32!LoadLibraryExW` at `0x18000eb4b`
- `KERNEL32!GetProcAddress` at `0x18000eb5f`
- `KERNEL32!GetProcAddress` at `0x18000eb5f`

## string_xrefs

- `0x18000eb7a`: `iislog.dll`
- `0x18000eb27`: `\inetsrv\iisreg.dll`

## pseudocode

```c
__int64 __fastcall CallRegisterComponent(const unsigned __int16 *a1, char *a2)
{
  HMODULE Library; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rax
  unsigned int v6; // ebx
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( GetSystemDirectoryW(Buffer, 0xF0u) - 1 > 0xEF )
    return 2147942403LL;
  wcscat_s(Buffer, 0x104u, L"\\inetsrv\\iisreg.dll");
  Library = LoadLibraryExW(Buffer, 0, 0x900u);
  v4 = Library;
  if ( !Library )
    return 2147942403LL;
  ProcAddress = GetProcAddress(Library, a2);
  v6 = ProcAddress == 0 ? 0x80004005 : 0;
  if ( ProcAddress )
    v6 = ((__int64 (__fastcall *)(const wchar_t *))ProcAddress)(L"iislog.dll");
  FreeLibrary(v4);
  return v6;
}

```

## disassembly

```asm
0x18000eaec  mov     [rsp+arg_0], rbx
0x18000eaf1  push    rdi
0x18000eaf2  sub     rsp, 240h
0x18000eaf9  mov     rax, cs:__security_cookie
0x18000eb00  xor     rax, rsp
0x18000eb03  mov     [rsp+248h+var_18], rax
0x18000eb0b  mov     rbx, rdx
0x18000eb0e  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x18000eb13  mov     edx, 0F0h; uSize
0x18000eb18  call    cs:__imp_GetSystemDirectoryW
0x18000eb1e  dec     eax
0x18000eb20  cmp     eax, 0EFh
0x18000eb25  ja      short loc_18000EB95
0x18000eb27  lea     r8, aInetsrvIisregD; "\\inetsrv\\iisreg.dll"
0x18000eb2e  mov     edx, 104h; SizeInWords
0x18000eb33  lea     rcx, [rsp+248h+Buffer]; Destination
0x18000eb38  call    cs:__imp_wcscat_s
0x18000eb3e  xor     edx, edx; hFile
0x18000eb40  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x18000eb45  mov     r8d, 900h; dwFlags
0x18000eb4b  call    cs:__imp_LoadLibraryExW
0x18000eb51  mov     rdi, rax
0x18000eb54  test    rax, rax
0x18000eb57  jz      short loc_18000EB95
0x18000eb59  mov     rdx, rbx; lpProcName
0x18000eb5c  mov     rcx, rax; hModule
0x18000eb5f  call    cs:__imp_GetProcAddress
0x18000eb65  mov     rcx, rax
0x18000eb68  neg     rcx
0x18000eb6b  sbb     ebx, ebx
0x18000eb6d  not     ebx
0x18000eb6f  and     ebx, 80004005h
0x18000eb75  test    rax, rax
0x18000eb78  jz      short loc_18000EB88
0x18000eb7a  lea     rcx, aIislogDll_0; "iislog.dll"
0x18000eb81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb86  mov     ebx, eax
0x18000eb88  mov     rcx, rdi; hLibModule
0x18000eb8b  call    cs:__imp_FreeLibrary
0x18000eb91  mov     eax, ebx
0x18000eb93  jmp     short loc_18000EB9A
0x18000eb95  mov     eax, 80070003h
0x18000eb9a  mov     rcx, [rsp+248h+var_18]
0x18000eba2  xor     rcx, rsp; StackCookie
0x18000eba5  call    __security_check_cookie
0x18000ebaa  mov     rbx, [rsp+248h+arg_0]
0x18000ebb2  add     rsp, 240h
0x18000ebb9  pop     rdi
0x18000ebba  retn
```
