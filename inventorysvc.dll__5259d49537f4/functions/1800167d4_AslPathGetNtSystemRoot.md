# AslPathGetNtSystemRoot

- ea: `0x1800167d4`
- end: `0x180016847`
- name: `AslPathGetNtSystemRoot`
- size: `115`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001304c`
- `0x180017f84`
- `0x1800197f4`

## callees

- `0x1800167d4`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016816`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016816`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800167fe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800167fe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001682c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001682c`

## string_xrefs

- `0x1800167ec`: `ntdll.dll`

## pseudocode

```c
__int64 AslPathGetNtSystemRoot()
{
  __int64 v0; // rbx
  HMODULE Library; // rax
  HMODULE v2; // rdi
  __int64 (*ProcAddress)(void); // rax

  v0 = qword_1800FF408;
  if ( !qword_1800FF408 )
  {
    v0 = 2147352624;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v2 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
      if ( ProcAddress )
        v0 = ProcAddress();
      FreeLibrary(v2);
    }
    qword_1800FF408 = v0;
  }
  return v0;
}

```

## disassembly

```asm
0x1800167d4  mov     [rsp+arg_0], rbx
0x1800167d9  push    rdi
0x1800167da  sub     rsp, 20h
0x1800167de  mov     rbx, cs:qword_1800FF408
0x1800167e5  test    rbx, rbx
0x1800167e8  jnz     short loc_180016839
0x1800167ea  xor     edx, edx; hFile
0x1800167ec  lea     rcx, LibFileName; "ntdll.dll"
0x1800167f3  mov     r8d, 800h; dwFlags
0x1800167f9  mov     ebx, 7FFE0030h
0x1800167fe  call    cs:__imp_LoadLibraryExW
0x180016804  mov     rdi, rax
0x180016807  test    rax, rax
0x18001680a  jz      short loc_180016832
0x18001680c  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x180016813  mov     rcx, rax; hModule
0x180016816  call    cs:__imp_GetProcAddress
0x18001681c  test    rax, rax
0x18001681f  jz      short loc_180016829
0x180016821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016826  mov     rbx, rax
0x180016829  mov     rcx, rdi; hLibModule
0x18001682c  call    cs:__imp_FreeLibrary
0x180016832  mov     cs:qword_1800FF408, rbx
0x180016839  mov     rax, rbx
0x18001683c  mov     rbx, [rsp+28h+arg_0]
0x180016841  add     rsp, 20h
0x180016845  pop     rdi
0x180016846  retn
```
