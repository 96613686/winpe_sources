# CallRegisterComponent(ushort const *,char *)

- ea: `0x18000f998`
- end: `0x18000fa67`
- name: `?CallRegisterComponent@@YAJPEBGPEAD@Z`
- size: `207`
- prototype: `int(const unsigned __int16 *, char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009f40`
- `0x180009f60`

## callees

- `0x18000f998`
- `0x18000fb50`
- `0x180010010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000f9e4`
- `msvcrt!wcscat_s` at `0x18000f9e4`
- `KERNEL32!GetSystemDirectoryW` at `0x18000f9c4`
- `KERNEL32!GetSystemDirectoryW` at `0x18000f9c4`
- `KERNEL32!GetProcAddress` at `0x18000fa0b`
- `KERNEL32!GetProcAddress` at `0x18000fa0b`
- `KERNEL32!FreeLibrary` at `0x18000fa37`
- `KERNEL32!FreeLibrary` at `0x18000fa37`
- `KERNEL32!LoadLibraryExW` at `0x18000f9f7`
- `KERNEL32!LoadLibraryExW` at `0x18000f9f7`

## string_xrefs

- `0x18000fa26`: `coadmin.dll`
- `0x18000f9d3`: `\inetsrv\iisreg.dll`

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
    v6 = ((__int64 (__fastcall *)(const wchar_t *))ProcAddress)(L"coadmin.dll");
  FreeLibrary(v4);
  return v6;
}

```

## disassembly

```asm
0x18000f998  mov     [rsp+arg_0], rbx
0x18000f99d  push    rdi
0x18000f99e  sub     rsp, 240h
0x18000f9a5  mov     rax, cs:__security_cookie
0x18000f9ac  xor     rax, rsp
0x18000f9af  mov     [rsp+248h+var_18], rax
0x18000f9b7  mov     rbx, rdx
0x18000f9ba  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x18000f9bf  mov     edx, 0F0h; uSize
0x18000f9c4  call    cs:__imp_GetSystemDirectoryW
0x18000f9ca  dec     eax
0x18000f9cc  cmp     eax, 0EFh
0x18000f9d1  ja      short loc_18000FA41
0x18000f9d3  lea     r8, aInetsrvIisregD; "\\inetsrv\\iisreg.dll"
0x18000f9da  mov     edx, 104h; SizeInWords
0x18000f9df  lea     rcx, [rsp+248h+Buffer]; Destination
0x18000f9e4  call    cs:__imp_wcscat_s
0x18000f9ea  xor     edx, edx; hFile
0x18000f9ec  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x18000f9f1  mov     r8d, 900h; dwFlags
0x18000f9f7  call    cs:__imp_LoadLibraryExW
0x18000f9fd  mov     rdi, rax
0x18000fa00  test    rax, rax
0x18000fa03  jz      short loc_18000FA41
0x18000fa05  mov     rdx, rbx; lpProcName
0x18000fa08  mov     rcx, rax; hModule
0x18000fa0b  call    cs:__imp_GetProcAddress
0x18000fa11  mov     rcx, rax
0x18000fa14  neg     rcx
0x18000fa17  sbb     ebx, ebx
0x18000fa19  not     ebx
0x18000fa1b  and     ebx, 80004005h
0x18000fa21  test    rax, rax
0x18000fa24  jz      short loc_18000FA34
0x18000fa26  lea     rcx, aCoadminDll_0; "coadmin.dll"
0x18000fa2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa32  mov     ebx, eax
0x18000fa34  mov     rcx, rdi; hLibModule
0x18000fa37  call    cs:__imp_FreeLibrary
0x18000fa3d  mov     eax, ebx
0x18000fa3f  jmp     short loc_18000FA46
0x18000fa41  mov     eax, 80070003h
0x18000fa46  mov     rcx, [rsp+248h+var_18]
0x18000fa4e  xor     rcx, rsp; StackCookie
0x18000fa51  call    __security_check_cookie
0x18000fa56  mov     rbx, [rsp+248h+arg_0]
0x18000fa5e  add     rsp, 240h
0x18000fa65  pop     rdi
0x18000fa66  retn
```
