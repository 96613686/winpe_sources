# Win32PointerApi::EnableMouseInPointer(int)

- ea: `0x140097e78`
- end: `0x140097ed5`
- name: `?EnableMouseInPointer@Win32PointerApi@@SAHH@Z`
- size: `93`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14006590c`

## callees

- `0x140097e78`
- `0x140114010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140097e93`
- `KERNEL32!LoadLibraryExW` at `0x140097e93`
- `KERNEL32!FreeLibrary` at `0x140097ec2`
- `KERNEL32!FreeLibrary` at `0x140097ec2`
- `KERNEL32!GetProcAddress` at `0x140097eab`
- `KERNEL32!GetProcAddress` at `0x140097eab`

## string_xrefs

- `0x140097e85`: `user32.dll`

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
0x140097e78  mov     [rsp+arg_0], rbx
0x140097e7d  push    rdi
0x140097e7e  sub     rsp, 20h
0x140097e82  xor     r8d, r8d; dwFlags
0x140097e85  lea     rcx, aUser32Dll_0; "user32.dll"
0x140097e8c  xor     edx, edx; hFile
0x140097e8e  mov     edi, 1
0x140097e93  call    cs:__imp_LoadLibraryExW
0x140097e99  mov     rbx, rax
0x140097e9c  test    rax, rax
0x140097e9f  jz      short loc_140097EC8
0x140097ea1  lea     rdx, aEnablemouseinp; "EnableMouseInPointer"
0x140097ea8  mov     rcx, rax; hModule
0x140097eab  call    cs:__imp_GetProcAddress
0x140097eb1  test    rax, rax
0x140097eb4  jz      short loc_140097EBF
0x140097eb6  xor     ecx, ecx
0x140097eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097ebd  mov     edi, eax
0x140097ebf  mov     rcx, rbx; hLibModule
0x140097ec2  call    cs:__imp_FreeLibrary
0x140097ec8  mov     rbx, [rsp+28h+arg_0]
0x140097ecd  mov     eax, edi
0x140097ecf  add     rsp, 20h
0x140097ed3  pop     rdi
0x140097ed4  retn
```
