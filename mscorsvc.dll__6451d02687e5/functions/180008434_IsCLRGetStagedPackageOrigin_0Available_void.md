# IsCLRGetStagedPackageOrigin_0Available(void)

- ea: `0x180008434`
- end: `0x180008486`
- name: `?IsCLRGetStagedPackageOrigin_0Available@@YA_NXZ`
- size: `82`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002f454`

## callees

- `0x180008434`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000844d`
- `KERNEL32!LoadLibraryExW` at `0x18000844d`
- `KERNEL32!GetProcAddress` at `0x180008462`
- `KERNEL32!GetProcAddress` at `0x180008462`

## string_xrefs

- `0x180008444`: `api-ms-win-appmodel-runtime-l1-1-0.dll`

## pseudocode

```c
bool IsCLRGetStagedPackageOrigin_0Available(void)
{
  HMODULE Library; // rax

  if ( !bGetStagedPackageOrigin_0Probed )
  {
    Library = LoadLibraryExW(L"api-ms-win-appmodel-runtime-l1-1-0.dll", 0, 0);
    if ( Library )
      qword_18006FFF0 = (__int64)GetProcAddress(Library, "GetStagedPackageOrigin");
    bGetStagedPackageOrigin_0Probed = 1;
  }
  return qword_18006FFF0 != 0;
}

```

## disassembly

```asm
0x180008434  sub     rsp, 28h
0x180008438  cmp     cs:?bGetStagedPackageOrigin_0Probed@@3_NA, 0; bool bGetStagedPackageOrigin_0Probed
0x18000843f  jnz     short loc_180008476
0x180008441  xor     r8d, r8d; dwFlags
0x180008444  lea     rcx, aApiMsWinAppmod_0; "api-ms-win-appmodel-runtime-l1-1-0.dll"
0x18000844b  xor     edx, edx; hFile
0x18000844d  call    cs:__imp_LoadLibraryExW
0x180008453  test    rax, rax
0x180008456  jz      short loc_18000846F
0x180008458  lea     rdx, aGetstagedpacka; "GetStagedPackageOrigin"
0x18000845f  mov     rcx, rax; hModule
0x180008462  call    cs:__imp_GetProcAddress
0x180008468  mov     cs:qword_18006FFF0, rax
0x18000846f  mov     cs:?bGetStagedPackageOrigin_0Probed@@3_NA, 1; bool bGetStagedPackageOrigin_0Probed
0x180008476  cmp     cs:qword_18006FFF0, 0
0x18000847e  setnz   al
0x180008481  add     rsp, 28h
0x180008485  retn
```
