# SHFusionLoadLibrary

- ea: `0x180017df0`
- end: `0x180017e43`
- name: `SHFusionLoadLibrary`
- size: `83`
- prototype: `HMODULE __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180018110`
- `0x180018434`

## callees

- `0x180017c70`
- `0x180017df0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180017e1f`
- `KERNEL32!LoadLibraryExW` at `0x180017e1f`
- `KERNEL32!DeactivateActCtx` at `0x180017e34`
- `KERNEL32!DeactivateActCtx` at `0x180017e34`

## pseudocode

```c
HMODULE __fastcall SHFusionLoadLibrary(LPCWSTR lpLibFileName)
{
  HMODULE Library; // rbx
  ULONG_PTR ulCookie; // [rsp+38h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !SHActivateContext(&ulCookie) )
    return 0;
  Library = LoadLibraryExW(lpLibFileName, 0, 0x4000u);
  if ( ulCookie )
    DeactivateActCtx(0, ulCookie);
  return Library;
}

```

## disassembly

```asm
0x180017df0  push    rbx
0x180017df2  sub     rsp, 20h
0x180017df6  mov     rbx, rcx
0x180017df9  mov     [rsp+28h+ulCookie], 0
0x180017e02  lea     rcx, [rsp+28h+ulCookie]
0x180017e07  call    SHActivateContext
0x180017e0c  test    eax, eax
0x180017e0e  jnz     short loc_180017E14
0x180017e10  xor     eax, eax
0x180017e12  jmp     short loc_180017E3D
0x180017e14  xor     edx, edx; hFile
0x180017e16  mov     r8d, 4000h; dwFlags
0x180017e1c  mov     rcx, rbx; lpLibFileName
0x180017e1f  call    cs:__imp_LoadLibraryExW
0x180017e25  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x180017e2a  mov     rbx, rax
0x180017e2d  test    rdx, rdx
0x180017e30  jz      short loc_180017E3A
0x180017e32  xor     ecx, ecx; dwFlags
0x180017e34  call    cs:__imp_DeactivateActCtx
0x180017e3a  mov     rax, rbx
0x180017e3d  add     rsp, 20h
0x180017e41  pop     rbx
0x180017e42  retn
```
