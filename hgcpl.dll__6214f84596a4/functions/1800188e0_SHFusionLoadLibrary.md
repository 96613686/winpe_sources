# SHFusionLoadLibrary

- ea: `0x1800188e0`
- end: `0x180018930`
- name: `SHFusionLoadLibrary`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018938`

## callees

- `0x180018740`
- `0x1800187a8`
- `0x1800188e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018914`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018914`

## string_xrefs

- `0x180018907`: `comctl32.dll`

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
0x1800188e0  mov     [rsp+ulCookie], rcx
0x1800188e5  push    rbx
0x1800188e6  sub     rsp, 20h
0x1800188ea  lea     rcx, [rsp+28h+ulCookie]
0x1800188ef  mov     [rsp+28h+ulCookie], 0
0x1800188f8  call    SHActivateContext
0x1800188fd  test    eax, eax
0x1800188ff  jnz     short loc_180018905
0x180018901  xor     eax, eax
0x180018903  jmp     short loc_18001892A
0x180018905  xor     edx, edx; hFile
0x180018907  lea     rcx, aComctl32Dll_0; "comctl32.dll"
0x18001890e  mov     r8d, 4000h; dwFlags
0x180018914  call    cs:__imp_LoadLibraryExW
0x18001891a  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x18001891f  mov     rbx, rax
0x180018922  call    SHDeactivateContext
0x180018927  mov     rax, rbx
0x18001892a  add     rsp, 20h
0x18001892e  pop     rbx
0x18001892f  retn
```
