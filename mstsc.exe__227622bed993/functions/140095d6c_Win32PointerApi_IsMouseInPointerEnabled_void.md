# Win32PointerApi::IsMouseInPointerEnabled(void)

- ea: `0x140095d6c`
- end: `0x140095dc4`
- name: `?IsMouseInPointerEnabled@Win32PointerApi@@SAHXZ`
- size: `88`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14006379c`

## callees

- `0x140095d6c`
- `0x140112010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140095d84`
- `KERNEL32!LoadLibraryExW` at `0x140095d84`
- `KERNEL32!FreeLibrary` at `0x140095db1`
- `KERNEL32!FreeLibrary` at `0x140095db1`
- `KERNEL32!GetProcAddress` at `0x140095d9c`
- `KERNEL32!GetProcAddress` at `0x140095d9c`

## string_xrefs

- `0x140095d79`: `user32.dll`

## pseudocode

```c
__int64 Win32PointerApi::IsMouseInPointerEnabled(void)
{
  unsigned int v0; // edi
  HMODULE Library; // rax
  HMODULE v2; // rbx
  __int64 (*ProcAddress)(void); // rax

  v0 = 0;
  Library = LoadLibraryExW(L"user32.dll", 0, 0);
  v2 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "IsMouseInPointerEnabled");
    if ( ProcAddress )
      v0 = ProcAddress();
    FreeLibrary(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x140095d6c  mov     [rsp+arg_0], rbx
0x140095d71  push    rdi
0x140095d72  sub     rsp, 20h
0x140095d76  xor     r8d, r8d; dwFlags
0x140095d79  lea     rcx, aUser32Dll_0; "user32.dll"
0x140095d80  xor     edx, edx; hFile
0x140095d82  xor     edi, edi
0x140095d84  call    cs:__imp_LoadLibraryExW
0x140095d8a  mov     rbx, rax
0x140095d8d  test    rax, rax
0x140095d90  jz      short loc_140095DB7
0x140095d92  lea     rdx, aIsmouseinpoint; "IsMouseInPointerEnabled"
0x140095d99  mov     rcx, rax; hModule
0x140095d9c  call    cs:__imp_GetProcAddress
0x140095da2  test    rax, rax
0x140095da5  jz      short loc_140095DAE
0x140095da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140095dac  mov     edi, eax
0x140095dae  mov     rcx, rbx; hLibModule
0x140095db1  call    cs:__imp_FreeLibrary
0x140095db7  mov     rbx, [rsp+28h+arg_0]
0x140095dbc  mov     eax, edi
0x140095dbe  add     rsp, 20h
0x140095dc2  pop     rdi
0x140095dc3  retn
```
