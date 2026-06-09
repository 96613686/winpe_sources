# SHFusionLoadLibrary

- ea: `0x180065f5c`
- end: `0x180065fac`
- name: `SHFusionLoadLibrary`
- size: `80`
- prototype: `HMODULE __fastcall(const wchar_t *lpLibFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180065fb4`

## callees

- `0x180065dbc`
- `0x180065e24`
- `0x180065f5c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180065f90`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180065f90`

## string_xrefs

- `0x180065f83`: `comctl32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
HMODULE __fastcall SHFusionLoadLibrary(const wchar_t *lpLibFileName)
{
  HMODULE Library; // rbx
  unsigned __int64 ulCookie; // [rsp+30h] [rbp+8h] BYREF

  ulCookie = 0;
  if ( !SHActivateContext(&ulCookie) )
    return 0;
  Library = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
  SHDeactivateContext(ulCookie);
  return Library;
}

```

## disassembly

```asm
0x180065f5c  mov     [rsp+ulCookie], rcx
0x180065f61  push    rbx
0x180065f62  sub     rsp, 20h
0x180065f66  lea     rcx, [rsp+28h+ulCookie]; pulCookie
0x180065f6b  mov     [rsp+28h+ulCookie], 0
0x180065f74  call    SHActivateContext
0x180065f79  test    eax, eax
0x180065f7b  jnz     short loc_180065F81
0x180065f7d  xor     eax, eax
0x180065f7f  jmp     short loc_180065FA6
0x180065f81  xor     edx, edx; hFile
0x180065f83  lea     rcx, LibFileName; "comctl32.dll"
0x180065f8a  mov     r8d, 4000h; dwFlags
0x180065f90  call    cs:__imp_LoadLibraryExW
0x180065f96  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x180065f9b  mov     rbx, rax
0x180065f9e  call    SHDeactivateContext
0x180065fa3  mov     rax, rbx
0x180065fa6  add     rsp, 20h
0x180065faa  pop     rbx
0x180065fab  retn
```
