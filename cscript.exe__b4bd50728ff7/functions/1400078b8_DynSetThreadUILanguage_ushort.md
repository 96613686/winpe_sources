# DynSetThreadUILanguage(ushort)

- ea: `0x1400078b8`
- end: `0x14000790f`
- name: `?DynSetThreadUILanguage@@YAGG@Z`
- size: `87`
- prototype: `unsigned __int16 __fastcall(unsigned __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000380c`

## callees

- `0x1400078b8`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400078e3`
- `KERNEL32!GetProcAddress` at `0x1400078e3`
- `KERNEL32!FreeLibrary` at `0x1400078fb`
- `KERNEL32!FreeLibrary` at `0x1400078fb`
- `KERNEL32!LoadLibraryW` at `0x1400078cb`
- `KERNEL32!LoadLibraryW` at `0x1400078cb`

## string_xrefs

- `0x1400078c2`: `kernel32.dll`
- `0x1400078d9`: `SetThreadUILanguage`

## pseudocode

```c
__int64 __fastcall DynSetThreadUILanguage()
{
  unsigned __int16 v0; // di
  HMODULE LibraryW; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax

  v0 = 0;
  LibraryW = LoadLibraryW(L"kernel32.dll");
  v2 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "SetThreadUILanguage");
    if ( ProcAddress )
      v0 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(0);
    FreeLibrary(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x1400078b8  mov     [rsp+arg_0], rbx
0x1400078bd  push    rdi
0x1400078be  sub     rsp, 20h
0x1400078c2  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1400078c9  xor     edi, edi
0x1400078cb  call    cs:__imp_LoadLibraryW
0x1400078d1  mov     rbx, rax
0x1400078d4  test    rax, rax
0x1400078d7  jz      short loc_140007901
0x1400078d9  lea     rdx, aSetthreaduilan; "SetThreadUILanguage"
0x1400078e0  mov     rcx, rax; hModule
0x1400078e3  call    cs:__imp_GetProcAddress
0x1400078e9  test    rax, rax
0x1400078ec  jz      short loc_1400078F8
0x1400078ee  xor     ecx, ecx
0x1400078f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400078f5  movzx   edi, ax
0x1400078f8  mov     rcx, rbx; hLibModule
0x1400078fb  call    cs:__imp_FreeLibrary
0x140007901  mov     rbx, [rsp+28h+arg_0]
0x140007906  movzx   eax, di
0x140007909  add     rsp, 20h
0x14000790d  pop     rdi
0x14000790e  retn
```
