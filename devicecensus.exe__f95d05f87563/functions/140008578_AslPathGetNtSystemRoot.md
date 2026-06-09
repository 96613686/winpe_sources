# AslPathGetNtSystemRoot

- ea: `0x140008578`
- end: `0x1400085eb`
- name: `AslPathGetNtSystemRoot`
- size: `115`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140004dd4`
- `0x140009c7c`
- `0x14000b4ec`

## callees

- `0x140008578`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400085a2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400085a2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400085d0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400085d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400085ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400085ba`

## string_xrefs

- `0x140008590`: `ntdll.dll`

## pseudocode

```c
__int64 AslPathGetNtSystemRoot()
{
  __int64 v0; // rbx
  HMODULE Library; // rax
  HMODULE v2; // rdi
  __int64 (*ProcAddress)(void); // rax

  v0 = qword_14001C948;
  if ( !qword_14001C948 )
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
    qword_14001C948 = v0;
  }
  return v0;
}

```

## disassembly

```asm
0x140008578  mov     [rsp+arg_0], rbx
0x14000857d  push    rdi
0x14000857e  sub     rsp, 20h
0x140008582  mov     rbx, cs:qword_14001C948
0x140008589  test    rbx, rbx
0x14000858c  jnz     short loc_1400085DD
0x14000858e  xor     edx, edx; hFile
0x140008590  lea     rcx, LibFileName; "ntdll.dll"
0x140008597  mov     r8d, 800h; dwFlags
0x14000859d  mov     ebx, 7FFE0030h
0x1400085a2  call    cs:__imp_LoadLibraryExW
0x1400085a8  mov     rdi, rax
0x1400085ab  test    rax, rax
0x1400085ae  jz      short loc_1400085D6
0x1400085b0  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x1400085b7  mov     rcx, rax; hModule
0x1400085ba  call    cs:__imp_GetProcAddress
0x1400085c0  test    rax, rax
0x1400085c3  jz      short loc_1400085CD
0x1400085c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085ca  mov     rbx, rax
0x1400085cd  mov     rcx, rdi; hLibModule
0x1400085d0  call    cs:__imp_FreeLibrary
0x1400085d6  mov     cs:qword_14001C948, rbx
0x1400085dd  mov     rax, rbx
0x1400085e0  mov     rbx, [rsp+28h+arg_0]
0x1400085e5  add     rsp, 20h
0x1400085e9  pop     rdi
0x1400085ea  retn
```
