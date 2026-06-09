# Win32PointerApi::IsMouseInPointerEnabled(void)

- ea: `0x140097edc`
- end: `0x140097f34`
- name: `?IsMouseInPointerEnabled@Win32PointerApi@@SAHXZ`
- size: `88`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14006590c`

## callees

- `0x140097edc`
- `0x140114010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140097ef4`
- `KERNEL32!LoadLibraryExW` at `0x140097ef4`
- `KERNEL32!FreeLibrary` at `0x140097f21`
- `KERNEL32!FreeLibrary` at `0x140097f21`
- `KERNEL32!GetProcAddress` at `0x140097f0c`
- `KERNEL32!GetProcAddress` at `0x140097f0c`

## string_xrefs

- `0x140097ee9`: `user32.dll`

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
0x140097edc  mov     [rsp+arg_0], rbx
0x140097ee1  push    rdi
0x140097ee2  sub     rsp, 20h
0x140097ee6  xor     r8d, r8d; dwFlags
0x140097ee9  lea     rcx, aUser32Dll_0; "user32.dll"
0x140097ef0  xor     edx, edx; hFile
0x140097ef2  xor     edi, edi
0x140097ef4  call    cs:__imp_LoadLibraryExW
0x140097efa  mov     rbx, rax
0x140097efd  test    rax, rax
0x140097f00  jz      short loc_140097F27
0x140097f02  lea     rdx, aIsmouseinpoint; "IsMouseInPointerEnabled"
0x140097f09  mov     rcx, rax; hModule
0x140097f0c  call    cs:__imp_GetProcAddress
0x140097f12  test    rax, rax
0x140097f15  jz      short loc_140097F1E
0x140097f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097f1c  mov     edi, eax
0x140097f1e  mov     rcx, rbx; hLibModule
0x140097f21  call    cs:__imp_FreeLibrary
0x140097f27  mov     rbx, [rsp+28h+arg_0]
0x140097f2c  mov     eax, edi
0x140097f2e  add     rsp, 20h
0x140097f32  pop     rdi
0x140097f33  retn
```
