# SHFusionLoadLibrary

- ea: `0x18000471c`
- end: `0x180004774`
- name: `SHFusionLoadLibrary`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000477c`

## callees

- `0x18000459c`
- `0x18000471c`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x180004765`
- `KERNEL32!DeactivateActCtx` at `0x180004765`
- `KERNEL32!LoadLibraryExW` at `0x180004750`
- `KERNEL32!LoadLibraryExW` at `0x180004750`

## string_xrefs

- `0x180004743`: `comctl32.dll`

## pseudocode

```c
HMODULE SHFusionLoadLibrary()
{
  HMODULE Library; // rbx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp+8h] BYREF

  ulCookie = 0;
  if ( !(unsigned int)SHActivateContext(&ulCookie) )
    return 0;
  Library = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
  if ( ulCookie )
    DeactivateActCtx(0, ulCookie);
  return Library;
}

```

## disassembly

```asm
0x18000471c  mov     [rsp+ulCookie], rcx
0x180004721  push    rbx
0x180004722  sub     rsp, 20h
0x180004726  lea     rcx, [rsp+28h+ulCookie]
0x18000472b  mov     [rsp+28h+ulCookie], 0
0x180004734  call    SHActivateContext
0x180004739  test    eax, eax
0x18000473b  jnz     short loc_180004741
0x18000473d  xor     eax, eax
0x18000473f  jmp     short loc_18000476E
0x180004741  xor     edx, edx; hFile
0x180004743  lea     rcx, LibFileName; "comctl32.dll"
0x18000474a  mov     r8d, 4000h; dwFlags
0x180004750  call    cs:__imp_LoadLibraryExW
0x180004756  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x18000475b  mov     rbx, rax
0x18000475e  test    rdx, rdx
0x180004761  jz      short loc_18000476B
0x180004763  xor     ecx, ecx; dwFlags
0x180004765  call    cs:__imp_DeactivateActCtx
0x18000476b  mov     rax, rbx
0x18000476e  add     rsp, 20h
0x180004772  pop     rbx
0x180004773  retn
```
