# AslPathGetNtSystemRoot

- ea: `0x18000e4c0`
- end: `0x18000e533`
- name: `AslPathGetNtSystemRoot`
- size: `115`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b8e8`
- `0x18000d088`
- `0x180016590`

## callees

- `0x18000e4c0`
- `0x18001a010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000e518`
- `KERNEL32!FreeLibrary` at `0x18000e518`
- `KERNEL32!LoadLibraryExW` at `0x18000e4ea`
- `KERNEL32!LoadLibraryExW` at `0x18000e4ea`
- `KERNEL32!GetProcAddress` at `0x18000e502`
- `KERNEL32!GetProcAddress` at `0x18000e502`

## string_xrefs

- `0x18000e4d8`: `ntdll.dll`

## pseudocode

```c
__int64 AslPathGetNtSystemRoot()
{
  __int64 v0; // rbx
  HMODULE Library; // rax
  HMODULE v2; // rdi
  __int64 (*ProcAddress)(void); // rax

  v0 = qword_180026928;
  if ( !qword_180026928 )
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
    qword_180026928 = v0;
  }
  return v0;
}

```

## disassembly

```asm
0x18000e4c0  mov     [rsp+arg_0], rbx
0x18000e4c5  push    rdi
0x18000e4c6  sub     rsp, 20h
0x18000e4ca  mov     rbx, cs:qword_180026928
0x18000e4d1  test    rbx, rbx
0x18000e4d4  jnz     short loc_18000E525
0x18000e4d6  xor     edx, edx; hFile
0x18000e4d8  lea     rcx, LibFileName; "ntdll.dll"
0x18000e4df  mov     r8d, 800h; dwFlags
0x18000e4e5  mov     ebx, 7FFE0030h
0x18000e4ea  call    cs:__imp_LoadLibraryExW
0x18000e4f0  mov     rdi, rax
0x18000e4f3  test    rax, rax
0x18000e4f6  jz      short loc_18000E51E
0x18000e4f8  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x18000e4ff  mov     rcx, rax; hModule
0x18000e502  call    cs:__imp_GetProcAddress
0x18000e508  test    rax, rax
0x18000e50b  jz      short loc_18000E515
0x18000e50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e512  mov     rbx, rax
0x18000e515  mov     rcx, rdi; hLibModule
0x18000e518  call    cs:__imp_FreeLibrary
0x18000e51e  mov     cs:qword_180026928, rbx
0x18000e525  mov     rax, rbx
0x18000e528  mov     rbx, [rsp+28h+arg_0]
0x18000e52d  add     rsp, 20h
0x18000e531  pop     rdi
0x18000e532  retn
```
