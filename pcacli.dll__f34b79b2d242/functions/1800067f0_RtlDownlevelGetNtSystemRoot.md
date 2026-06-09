# RtlDownlevelGetNtSystemRoot

- ea: `0x1800067f0`
- end: `0x18000686d`
- name: `RtlDownlevelGetNtSystemRoot`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005620`
- `0x18000b9c0`

## callees

- `0x1800067f0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006844`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006844`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000681e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000681e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006836`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006836`

## string_xrefs

- `0x180006805`: `ntdll.dll`

## pseudocode

```c
__int64 RtlDownlevelGetNtSystemRoot()
{
  __int64 result; // rax
  __int64 v1; // rbx
  HMODULE Library; // rax
  HMODULE v3; // rdi
  __int64 (*ProcAddress)(void); // rax

  result = qword_180014830;
  if ( !qword_180014830 )
  {
    v1 = 2147352624;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v3 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
      if ( ProcAddress )
        v1 = ProcAddress();
      FreeLibrary(v3);
    }
    result = v1;
    qword_180014830 = v1;
  }
  return result;
}

```

## disassembly

```asm
0x1800067f0  sub     rsp, 28h
0x1800067f4  mov     rax, cs:qword_180014830
0x1800067fb  test    rax, rax
0x1800067fe  jnz     short loc_18000685E
0x180006800  mov     [rsp+28h+arg_0], rbx
0x180006805  lea     rcx, LibFileName; "ntdll.dll"
0x18000680c  xor     edx, edx; hFile
0x18000680e  mov     [rsp+28h+var_8], rdi
0x180006813  mov     r8d, 800h; dwFlags
0x180006819  mov     ebx, 7FFE0030h
0x18000681e  call    cs:__imp_LoadLibraryExW
0x180006824  mov     rdi, rax
0x180006827  test    rax, rax
0x18000682a  jz      short loc_18000684A
0x18000682c  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x180006833  mov     rcx, rax; hModule
0x180006836  call    cs:__imp_GetProcAddress
0x18000683c  test    rax, rax
0x18000683f  jnz     short loc_180006863
0x180006841  mov     rcx, rdi; hLibModule
0x180006844  call    cs:__imp_FreeLibrary
0x18000684a  mov     rdi, [rsp+28h+var_8]
0x18000684f  mov     rax, rbx
0x180006852  mov     cs:qword_180014830, rbx
0x180006859  mov     rbx, [rsp+28h+arg_0]
0x18000685e  add     rsp, 28h
0x180006862  retn
0x180006863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006868  mov     rbx, rax
0x18000686b  jmp     short loc_180006841
```
