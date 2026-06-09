# Win32PointerApi::EnableMouseInPointer(int)

- ea: `0x140095d08`
- end: `0x140095d65`
- name: `?EnableMouseInPointer@Win32PointerApi@@SAHH@Z`
- size: `93`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14006379c`

## callees

- `0x140095d08`
- `0x140112010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140095d23`
- `KERNEL32!LoadLibraryExW` at `0x140095d23`
- `KERNEL32!FreeLibrary` at `0x140095d52`
- `KERNEL32!FreeLibrary` at `0x140095d52`
- `KERNEL32!GetProcAddress` at `0x140095d3b`
- `KERNEL32!GetProcAddress` at `0x140095d3b`

## string_xrefs

- `0x140095d15`: `user32.dll`

## pseudocode

```c
__int64 __fastcall Win32PointerApi::EnableMouseInPointer()
{
  unsigned int v0; // edi
  HMODULE Library; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rax

  v0 = 1;
  Library = LoadLibraryExW(L"user32.dll", 0, 0);
  v2 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "EnableMouseInPointer");
    if ( ProcAddress )
      v0 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(0);
    FreeLibrary(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x140095d08  mov     [rsp+arg_0], rbx
0x140095d0d  push    rdi
0x140095d0e  sub     rsp, 20h
0x140095d12  xor     r8d, r8d; dwFlags
0x140095d15  lea     rcx, aUser32Dll_0; "user32.dll"
0x140095d1c  xor     edx, edx; hFile
0x140095d1e  mov     edi, 1
0x140095d23  call    cs:__imp_LoadLibraryExW
0x140095d29  mov     rbx, rax
0x140095d2c  test    rax, rax
0x140095d2f  jz      short loc_140095D58
0x140095d31  lea     rdx, aEnablemouseinp; "EnableMouseInPointer"
0x140095d38  mov     rcx, rax; hModule
0x140095d3b  call    cs:__imp_GetProcAddress
0x140095d41  test    rax, rax
0x140095d44  jz      short loc_140095D4F
0x140095d46  xor     ecx, ecx
0x140095d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140095d4d  mov     edi, eax
0x140095d4f  mov     rcx, rbx; hLibModule
0x140095d52  call    cs:__imp_FreeLibrary
0x140095d58  mov     rbx, [rsp+28h+arg_0]
0x140095d5d  mov     eax, edi
0x140095d5f  add     rsp, 20h
0x140095d63  pop     rdi
0x140095d64  retn
```
