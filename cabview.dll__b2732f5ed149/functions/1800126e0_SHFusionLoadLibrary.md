# SHFusionLoadLibrary

- ea: `0x1800126e0`
- end: `0x180012730`
- name: `SHFusionLoadLibrary`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012894`

## callees

- `0x180012544`
- `0x1800125b4`
- `0x1800126e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012714`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012714`

## string_xrefs

- `0x180012707`: `comctl32.dll`

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
0x1800126e0  mov     [rsp+ulCookie], rcx
0x1800126e5  push    rbx
0x1800126e6  sub     rsp, 20h
0x1800126ea  lea     rcx, [rsp+28h+ulCookie]
0x1800126ef  mov     [rsp+28h+ulCookie], 0
0x1800126f8  call    SHActivateContext
0x1800126fd  test    eax, eax
0x1800126ff  jnz     short loc_180012705
0x180012701  xor     eax, eax
0x180012703  jmp     short loc_18001272A
0x180012705  xor     edx, edx; hFile
0x180012707  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18001270e  mov     r8d, 4000h; dwFlags
0x180012714  call    cs:__imp_LoadLibraryExW
0x18001271a  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x18001271f  mov     rbx, rax
0x180012722  call    SHDeactivateContext
0x180012727  mov     rax, rbx
0x18001272a  add     rsp, 20h
0x18001272e  pop     rbx
0x18001272f  retn
```
