# AslPathGetNtSystemRoot

- ea: `0x18006b324`
- end: `0x18006b397`
- name: `AslPathGetNtSystemRoot`
- size: `115`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18006a718`
- `0x18006b3a0`
- `0x18006cc28`

## callees

- `0x18006b324`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006b34e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006b34e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b37c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b37c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b366`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b366`

## string_xrefs

- `0x18006b33c`: `ntdll.dll`

## pseudocode

```c
__int64 AslPathGetNtSystemRoot()
{
  __int64 v0; // rbx
  HMODULE Library; // rax
  HMODULE v2; // rdi
  __int64 (*ProcAddress)(void); // rax

  v0 = qword_180157AC0;
  if ( !qword_180157AC0 )
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
    qword_180157AC0 = v0;
  }
  return v0;
}

```

## disassembly

```asm
0x18006b324  mov     [rsp+arg_0], rbx
0x18006b329  push    rdi
0x18006b32a  sub     rsp, 20h
0x18006b32e  mov     rbx, cs:qword_180157AC0
0x18006b335  test    rbx, rbx
0x18006b338  jnz     short loc_18006B389
0x18006b33a  xor     edx, edx; hFile
0x18006b33c  lea     rcx, LibFileName; "ntdll.dll"
0x18006b343  mov     r8d, 800h; dwFlags
0x18006b349  mov     ebx, 7FFE0030h
0x18006b34e  call    cs:__imp_LoadLibraryExW
0x18006b354  mov     rdi, rax
0x18006b357  test    rax, rax
0x18006b35a  jz      short loc_18006B382
0x18006b35c  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x18006b363  mov     rcx, rax; hModule
0x18006b366  call    cs:__imp_GetProcAddress
0x18006b36c  test    rax, rax
0x18006b36f  jz      short loc_18006B379
0x18006b371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b376  mov     rbx, rax
0x18006b379  mov     rcx, rdi; hLibModule
0x18006b37c  call    cs:__imp_FreeLibrary
0x18006b382  mov     cs:qword_180157AC0, rbx
0x18006b389  mov     rax, rbx
0x18006b38c  mov     rbx, [rsp+28h+arg_0]
0x18006b391  add     rsp, 20h
0x18006b395  pop     rdi
0x18006b396  retn
```
