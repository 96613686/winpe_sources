# SHFusionLoadLibrary

- ea: `0x18001c3a4`
- end: `0x18001c3f7`
- name: `SHFusionLoadLibrary`
- size: `83`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c888`
- `0x18001cc60`

## callees

- `0x18001c0c4`
- `0x18001c3a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001c3d3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001c3d3`
- `KERNEL32!DeactivateActCtx` at `0x18001c3e8`
- `KERNEL32!DeactivateActCtx` at `0x18001c3e8`

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
  if ( ulCookie )
    DeactivateActCtx(0, ulCookie);
  return Library;
}

```

## disassembly

```asm
0x18001c3a4  push    rbx
0x18001c3a6  sub     rsp, 20h
0x18001c3aa  mov     rbx, rcx
0x18001c3ad  mov     [rsp+28h+ulCookie], 0
0x18001c3b6  lea     rcx, [rsp+28h+ulCookie]
0x18001c3bb  call    SHActivateContext
0x18001c3c0  test    eax, eax
0x18001c3c2  jnz     short loc_18001C3C8
0x18001c3c4  xor     eax, eax
0x18001c3c6  jmp     short loc_18001C3F1
0x18001c3c8  xor     edx, edx; hFile
0x18001c3ca  mov     r8d, 4000h; dwFlags
0x18001c3d0  mov     rcx, rbx; lpLibFileName
0x18001c3d3  call    cs:__imp_LoadLibraryExW
0x18001c3d9  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x18001c3de  mov     rbx, rax
0x18001c3e1  test    rdx, rdx
0x18001c3e4  jz      short loc_18001C3EE
0x18001c3e6  xor     ecx, ecx; dwFlags
0x18001c3e8  call    cs:__imp_DeactivateActCtx
0x18001c3ee  mov     rax, rbx
0x18001c3f1  add     rsp, 20h
0x18001c3f5  pop     rbx
0x18001c3f6  retn
```
