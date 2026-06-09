# AslPathGetNtSystemRoot

- ea: `0x1400166c8`
- end: `0x14001673b`
- name: `AslPathGetNtSystemRoot`
- size: `115`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400145a4`
- `0x140016744`
- `0x140017fb4`

## callees

- `0x1400166c8`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001670a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001670a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400166f2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400166f2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140016720`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140016720`

## string_xrefs

- `0x1400166e0`: `ntdll.dll`

## pseudocode

```c
__int64 AslPathGetNtSystemRoot()
{
  __int64 v0; // rbx
  HMODULE Library; // rax
  HMODULE v2; // rdi
  __int64 (*ProcAddress)(void); // rax

  v0 = qword_1400C90F0;
  if ( !qword_1400C90F0 )
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
    qword_1400C90F0 = v0;
  }
  return v0;
}

```

## disassembly

```asm
0x1400166c8  mov     [rsp+arg_0], rbx
0x1400166cd  push    rdi
0x1400166ce  sub     rsp, 20h
0x1400166d2  mov     rbx, cs:qword_1400C90F0
0x1400166d9  test    rbx, rbx
0x1400166dc  jnz     short loc_14001672D
0x1400166de  xor     edx, edx; hFile
0x1400166e0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1400166e7  mov     r8d, 800h; dwFlags
0x1400166ed  mov     ebx, 7FFE0030h
0x1400166f2  call    cs:__imp_LoadLibraryExW
0x1400166f8  mov     rdi, rax
0x1400166fb  test    rax, rax
0x1400166fe  jz      short loc_140016726
0x140016700  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x140016707  mov     rcx, rax; hModule
0x14001670a  call    cs:__imp_GetProcAddress
0x140016710  test    rax, rax
0x140016713  jz      short loc_14001671D
0x140016715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001671a  mov     rbx, rax
0x14001671d  mov     rcx, rdi; hLibModule
0x140016720  call    cs:__imp_FreeLibrary
0x140016726  mov     cs:qword_1400C90F0, rbx
0x14001672d  mov     rax, rbx
0x140016730  mov     rbx, [rsp+28h+arg_0]
0x140016735  add     rsp, 20h
0x140016739  pop     rdi
0x14001673a  retn
```
