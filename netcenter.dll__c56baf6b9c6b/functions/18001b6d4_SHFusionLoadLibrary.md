# SHFusionLoadLibrary

- ea: `0x18001b6d4`
- end: `0x18001b724`
- name: `SHFusionLoadLibrary`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b72c`

## callees

- `0x18001b538`
- `0x18001b5a8`
- `0x18001b6d4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b708`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b708`

## string_xrefs

- `0x18001b6fb`: `comctl32.dll`

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
  SHDeactivateContext(ulCookie);
  return Library;
}

```

## disassembly

```asm
0x18001b6d4  mov     [rsp+ulCookie], rcx
0x18001b6d9  push    rbx
0x18001b6da  sub     rsp, 20h
0x18001b6de  lea     rcx, [rsp+28h+ulCookie]
0x18001b6e3  mov     [rsp+28h+ulCookie], 0
0x18001b6ec  call    SHActivateContext
0x18001b6f1  test    eax, eax
0x18001b6f3  jnz     short loc_18001B6F9
0x18001b6f5  xor     eax, eax
0x18001b6f7  jmp     short loc_18001B71E
0x18001b6f9  xor     edx, edx; hFile
0x18001b6fb  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18001b702  mov     r8d, 4000h; dwFlags
0x18001b708  call    cs:__imp_LoadLibraryExW
0x18001b70e  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x18001b713  mov     rbx, rax
0x18001b716  call    SHDeactivateContext
0x18001b71b  mov     rax, rbx
0x18001b71e  add     rsp, 20h
0x18001b722  pop     rbx
0x18001b723  retn
```
