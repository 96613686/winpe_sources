# SHFusionLoadLibrary

- ea: `0x180030ac0`
- end: `0x180030b10`
- name: `SHFusionLoadLibrary`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030c38`

## callees

- `0x180030920`
- `0x180030988`
- `0x180030ac0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030af4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030af4`

## string_xrefs

- `0x180030ae7`: `comctl32.dll`

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
0x180030ac0  mov     [rsp+ulCookie], rcx
0x180030ac5  push    rbx
0x180030ac6  sub     rsp, 20h
0x180030aca  lea     rcx, [rsp+28h+ulCookie]
0x180030acf  mov     [rsp+28h+ulCookie], 0
0x180030ad8  call    SHActivateContext
0x180030add  test    eax, eax
0x180030adf  jnz     short loc_180030AE5
0x180030ae1  xor     eax, eax
0x180030ae3  jmp     short loc_180030B0A
0x180030ae5  xor     edx, edx; hFile
0x180030ae7  lea     rcx, aComctl32Dll_0; "comctl32.dll"
0x180030aee  mov     r8d, 4000h; dwFlags
0x180030af4  call    cs:__imp_LoadLibraryExW
0x180030afa  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x180030aff  mov     rbx, rax
0x180030b02  call    SHDeactivateContext
0x180030b07  mov     rax, rbx
0x180030b0a  add     rsp, 20h
0x180030b0e  pop     rbx
0x180030b0f  retn
```
