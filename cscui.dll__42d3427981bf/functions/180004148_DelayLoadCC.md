# DelayLoadCC

- ea: `0x180004148`
- end: `0x1800041de`
- name: `DelayLoadCC`
- size: `150`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003f80`
- `0x180004070`
- `0x1800040f0`
- `0x18002e2d8`

## callees

- `0x180004148`
- `0x1800088dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000418b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800041c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000418b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800041c1`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800041a0`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800041a0`

## string_xrefs

- `0x18000417e`: `comctl32.dll`
- `0x1800041b4`: `comctl32.dll`

## pseudocode

```c
HMODULE DelayLoadCC()
{
  HMODULE Library; // rbx
  HMODULE result; // rax
  ULONG_PTR ulCookie; // [rsp+30h] [rbp+8h] BYREF

  if ( !g_hinstCC )
  {
    ulCookie = 0;
    if ( !(unsigned int)SHActivateContext(&ulCookie) )
    {
      g_hinstCC = 0;
      goto LABEL_7;
    }
    Library = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
    if ( ulCookie )
      DeactivateActCtx(0, ulCookie);
    g_hinstCC = Library;
    if ( !Library )
    {
LABEL_7:
      result = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
      g_hinstCC = result;
      if ( !result )
        return result;
    }
  }
  return (HMODULE)1;
}

```

## disassembly

```asm
0x180004148  push    rbx
0x18000414a  sub     rsp, 20h
0x18000414e  cmp     cs:g_hinstCC, 0
0x180004156  jnz     short loc_1800041D3
0x180004158  lea     rcx, [rsp+28h+ulCookie]
0x18000415d  mov     [rsp+28h+ulCookie], 0
0x180004166  call    SHActivateContext
0x18000416b  test    eax, eax
0x18000416d  jnz     short loc_18000417C
0x18000416f  mov     cs:g_hinstCC, 0
0x18000417a  jmp     short loc_1800041B2
0x18000417c  xor     edx, edx; hFile
0x18000417e  lea     rcx, LibFileName; "comctl32.dll"
0x180004185  mov     r8d, 4000h; dwFlags
0x18000418b  call    cs:__imp_LoadLibraryExW
0x180004191  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x180004196  mov     rbx, rax
0x180004199  test    rdx, rdx
0x18000419c  jz      short loc_1800041A6
0x18000419e  xor     ecx, ecx; dwFlags
0x1800041a0  call    cs:__imp_DeactivateActCtx
0x1800041a6  mov     cs:g_hinstCC, rbx
0x1800041ad  test    rbx, rbx
0x1800041b0  jnz     short loc_1800041D3
0x1800041b2  xor     edx, edx; hFile
0x1800041b4  lea     rcx, LibFileName; "comctl32.dll"
0x1800041bb  mov     r8d, 4000h; dwFlags
0x1800041c1  call    cs:__imp_LoadLibraryExW
0x1800041c7  mov     cs:g_hinstCC, rax
0x1800041ce  test    rax, rax
0x1800041d1  jz      short loc_1800041D8
0x1800041d3  mov     eax, 1
0x1800041d8  add     rsp, 20h
0x1800041dc  pop     rbx
0x1800041dd  retn
```
