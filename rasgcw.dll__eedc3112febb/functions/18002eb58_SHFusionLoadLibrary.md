# SHFusionLoadLibrary

- ea: `0x18002eb58`
- end: `0x18002eba3`
- name: `SHFusionLoadLibrary`
- size: `75`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002ebac`
- `0x18002ef90`

## callees

- `0x18002e9b8`
- `0x18002ea20`
- `0x18002eb58`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002eb87`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002eb87`

## pseudocode

```c
HMODULE __fastcall SHFusionLoadLibrary(LPCWSTR lpLibFileName)
{
  HMODULE Library; // rbx
  ULONG_PTR ulCookie; // [rsp+38h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !(unsigned int)SHActivateContext(&ulCookie) )
    return 0;
  Library = LoadLibraryExW(lpLibFileName, 0, 0x4000u);
  SHDeactivateContext(ulCookie);
  return Library;
}

```

## disassembly

```asm
0x18002eb58  push    rbx
0x18002eb5a  sub     rsp, 20h
0x18002eb5e  mov     rbx, rcx
0x18002eb61  mov     [rsp+28h+ulCookie], 0
0x18002eb6a  lea     rcx, [rsp+28h+ulCookie]
0x18002eb6f  call    SHActivateContext
0x18002eb74  test    eax, eax
0x18002eb76  jnz     short loc_18002EB7C
0x18002eb78  xor     eax, eax
0x18002eb7a  jmp     short loc_18002EB9D
0x18002eb7c  xor     edx, edx; hFile
0x18002eb7e  mov     r8d, 4000h; dwFlags
0x18002eb84  mov     rcx, rbx; lpLibFileName
0x18002eb87  call    cs:__imp_LoadLibraryExW
0x18002eb8d  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x18002eb92  mov     rbx, rax
0x18002eb95  call    SHDeactivateContext
0x18002eb9a  mov     rax, rbx
0x18002eb9d  add     rsp, 20h
0x18002eba1  pop     rbx
0x18002eba2  retn
```
