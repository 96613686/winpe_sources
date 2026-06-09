# CallRegisterComponent(ushort const *,char *)

- ea: `0x180030808`
- end: `0x1800308d7`
- name: `?CallRegisterComponent@@YAJPEBGPEAD@Z`
- size: `207`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015b10`
- `0x180015b30`

## callees

- `0x180030808`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180030854`
- `msvcrt!wcscat_s` at `0x180030854`
- `KERNEL32!GetSystemDirectoryW` at `0x180030834`
- `KERNEL32!GetSystemDirectoryW` at `0x180030834`
- `KERNEL32!GetProcAddress` at `0x18003087b`
- `KERNEL32!GetProcAddress` at `0x18003087b`
- `KERNEL32!FreeLibrary` at `0x1800308a7`
- `KERNEL32!FreeLibrary` at `0x1800308a7`
- `KERNEL32!LoadLibraryExW` at `0x180030867`
- `KERNEL32!LoadLibraryExW` at `0x180030867`

## string_xrefs

- `0x180030896`: `metadata.dll`
- `0x180030843`: `\inetsrv\iisreg.dll`

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
    v6 = ((__int64 (__fastcall *)(const wchar_t *))ProcAddress)(L"metadata.dll");
  FreeLibrary(v4);
  return v6;
}

```

## disassembly

```asm
0x180030808  mov     [rsp+arg_0], rbx
0x18003080d  push    rdi
0x18003080e  sub     rsp, 240h
0x180030815  mov     rax, cs:__security_cookie
0x18003081c  xor     rax, rsp
0x18003081f  mov     [rsp+248h+var_18], rax
0x180030827  mov     rbx, rdx
0x18003082a  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x18003082f  mov     edx, 0F0h; uSize
0x180030834  call    cs:__imp_GetSystemDirectoryW
0x18003083a  dec     eax
0x18003083c  cmp     eax, 0EFh
0x180030841  ja      short loc_1800308B1
0x180030843  lea     r8, aInetsrvIisregD; "\\inetsrv\\iisreg.dll"
0x18003084a  mov     edx, 104h; SizeInWords
0x18003084f  lea     rcx, [rsp+248h+Buffer]; Destination
0x180030854  call    cs:__imp_wcscat_s
0x18003085a  xor     edx, edx; hFile
0x18003085c  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x180030861  mov     r8d, 900h; dwFlags
0x180030867  call    cs:__imp_LoadLibraryExW
0x18003086d  mov     rdi, rax
0x180030870  test    rax, rax
0x180030873  jz      short loc_1800308B1
0x180030875  mov     rdx, rbx; lpProcName
0x180030878  mov     rcx, rax; hModule
0x18003087b  call    cs:__imp_GetProcAddress
0x180030881  mov     rcx, rax
0x180030884  neg     rcx
0x180030887  sbb     ebx, ebx
0x180030889  not     ebx
0x18003088b  and     ebx, 80004005h
0x180030891  test    rax, rax
0x180030894  jz      short loc_1800308A4
0x180030896  lea     rcx, aMetadataDll_1; "metadata.dll"
0x18003089d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308a2  mov     ebx, eax
0x1800308a4  mov     rcx, rdi; hLibModule
0x1800308a7  call    cs:__imp_FreeLibrary
0x1800308ad  mov     eax, ebx
0x1800308af  jmp     short loc_1800308B6
0x1800308b1  mov     eax, 80070003h
0x1800308b6  mov     rcx, [rsp+248h+var_18]
0x1800308be  xor     rcx, rsp; StackCookie
0x1800308c1  call    __security_check_cookie
0x1800308c6  mov     rbx, [rsp+248h+arg_0]
0x1800308ce  add     rsp, 240h
0x1800308d5  pop     rdi
0x1800308d6  retn
```
