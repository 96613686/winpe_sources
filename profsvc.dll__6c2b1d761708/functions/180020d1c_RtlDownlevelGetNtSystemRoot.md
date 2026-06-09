# RtlDownlevelGetNtSystemRoot

- ea: `0x180020d1c`
- end: `0x180020da2`
- name: `RtlDownlevelGetNtSystemRoot`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001f680`
- `0x1800245c0`

## callees

- `0x180020d1c`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020d80`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020d80`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020d46`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020d46`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020d64`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020d64`

## string_xrefs

- `0x180020d34`: `ntdll.dll`

## pseudocode

```c
__int64 RtlDownlevelGetNtSystemRoot()
{
  __int64 v0; // rbx
  HMODULE Library; // rax
  HMODULE v2; // rdi
  __int64 (*ProcAddress)(void); // rax

  v0 = qword_180082BB0;
  if ( !qword_180082BB0 )
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
    qword_180082BB0 = v0;
  }
  return v0;
}

```

## disassembly

```asm
0x180020d1c  mov     [rsp+arg_0], rbx
0x180020d21  push    rdi
0x180020d22  sub     rsp, 20h
0x180020d26  mov     rbx, cs:qword_180082BB0
0x180020d2d  test    rbx, rbx
0x180020d30  jnz     short loc_180020D93
0x180020d32  xor     edx, edx; hFile
0x180020d34  lea     rcx, LibFileName; "ntdll.dll"
0x180020d3b  mov     r8d, 800h; dwFlags
0x180020d41  mov     ebx, 7FFE0030h
0x180020d46  call    cs:__imp_LoadLibraryExW
0x180020d4d  nop     dword ptr [rax+rax+00h]
0x180020d52  mov     rdi, rax
0x180020d55  test    rax, rax
0x180020d58  jz      short loc_180020D8C
0x180020d5a  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x180020d61  mov     rcx, rax; hModule
0x180020d64  call    cs:__imp_GetProcAddress
0x180020d6b  nop     dword ptr [rax+rax+00h]
0x180020d70  test    rax, rax
0x180020d73  jz      short loc_180020D7D
0x180020d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d7a  mov     rbx, rax
0x180020d7d  mov     rcx, rdi; hLibModule
0x180020d80  call    cs:__imp_FreeLibrary
0x180020d87  nop     dword ptr [rax+rax+00h]
0x180020d8c  mov     cs:qword_180082BB0, rbx
0x180020d93  mov     rax, rbx
0x180020d96  mov     rbx, [rsp+28h+arg_0]
0x180020d9b  add     rsp, 20h
0x180020d9f  pop     rdi
0x180020da0  retn
```
