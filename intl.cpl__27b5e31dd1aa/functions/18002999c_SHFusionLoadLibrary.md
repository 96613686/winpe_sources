# SHFusionLoadLibrary

- ea: `0x18002999c`
- end: `0x1800299ec`
- name: `SHFusionLoadLibrary`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029c34`

## callees

- `0x180029800`
- `0x180029870`
- `0x18002999c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800299d0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800299d0`

## string_xrefs

- `0x1800299c3`: `comctl32.dll`

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
0x18002999c  mov     [rsp+ulCookie], rcx
0x1800299a1  push    rbx
0x1800299a2  sub     rsp, 20h
0x1800299a6  lea     rcx, [rsp+28h+ulCookie]
0x1800299ab  mov     [rsp+28h+ulCookie], 0
0x1800299b4  call    SHActivateContext
0x1800299b9  test    eax, eax
0x1800299bb  jnz     short loc_1800299C1
0x1800299bd  xor     eax, eax
0x1800299bf  jmp     short loc_1800299E6
0x1800299c1  xor     edx, edx; hFile
0x1800299c3  lea     rcx, aComctl32Dll; "comctl32.dll"
0x1800299ca  mov     r8d, 4000h; dwFlags
0x1800299d0  call    cs:__imp_LoadLibraryExW
0x1800299d6  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x1800299db  mov     rbx, rax
0x1800299de  call    SHDeactivateContext
0x1800299e3  mov     rax, rbx
0x1800299e6  add     rsp, 20h
0x1800299ea  pop     rbx
0x1800299eb  retn
```
