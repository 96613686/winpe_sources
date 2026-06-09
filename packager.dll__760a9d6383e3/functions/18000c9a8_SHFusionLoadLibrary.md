# SHFusionLoadLibrary

- ea: `0x18000c9a8`
- end: `0x18000ca00`
- name: `SHFusionLoadLibrary`
- size: `88`
- prototype: `HMODULE()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ca08`

## callees

- `0x18000c82c`
- `0x18000c9a8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c9dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c9dc`
- `KERNEL32!DeactivateActCtx` at `0x18000c9f1`
- `KERNEL32!DeactivateActCtx` at `0x18000c9f1`

## string_xrefs

- `0x18000c9cf`: `comctl32.dll`

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
0x18000c9a8  mov     [rsp+ulCookie], rcx
0x18000c9ad  push    rbx
0x18000c9ae  sub     rsp, 20h
0x18000c9b2  lea     rcx, [rsp+28h+ulCookie]
0x18000c9b7  mov     [rsp+28h+ulCookie], 0
0x18000c9c0  call    SHActivateContext
0x18000c9c5  test    eax, eax
0x18000c9c7  jnz     short loc_18000C9CD
0x18000c9c9  xor     eax, eax
0x18000c9cb  jmp     short loc_18000C9FA
0x18000c9cd  xor     edx, edx; hFile
0x18000c9cf  lea     rcx, LibFileName; "comctl32.dll"
0x18000c9d6  mov     r8d, 4000h; dwFlags
0x18000c9dc  call    cs:__imp_LoadLibraryExW
0x18000c9e2  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x18000c9e7  mov     rbx, rax
0x18000c9ea  test    rdx, rdx
0x18000c9ed  jz      short loc_18000C9F7
0x18000c9ef  xor     ecx, ecx; dwFlags
0x18000c9f1  call    cs:__imp_DeactivateActCtx
0x18000c9f7  mov     rax, rbx
0x18000c9fa  add     rsp, 20h
0x18000c9fe  pop     rbx
0x18000c9ff  retn
```
