# IsCLRGetStagedPackageOriginAvailable(void)

- ea: `0x1800083e0`
- end: `0x180008432`
- name: `?IsCLRGetStagedPackageOriginAvailable@@YA_NXZ`
- size: `82`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002f454`

## callees

- `0x1800083e0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800083f9`
- `KERNEL32!LoadLibraryExW` at `0x1800083f9`
- `KERNEL32!GetProcAddress` at `0x18000840e`
- `KERNEL32!GetProcAddress` at `0x18000840e`

## string_xrefs

- `0x1800083f0`: `api-ms-win-appmodel-runtime-l1-1-1.dll`

## pseudocode

```c
bool IsCLRGetStagedPackageOriginAvailable(void)
{
  HMODULE Library; // rax

  if ( !bGetStagedPackageOriginProbed )
  {
    Library = LoadLibraryExW(L"api-ms-win-appmodel-runtime-l1-1-1.dll", 0, 0);
    if ( Library )
      qword_18006FFE8 = (__int64)GetProcAddress(Library, "GetStagedPackageOrigin");
    bGetStagedPackageOriginProbed = 1;
  }
  return qword_18006FFE8 != 0;
}

```

## disassembly

```asm
0x1800083e0  sub     rsp, 28h
0x1800083e4  cmp     cs:?bGetStagedPackageOriginProbed@@3_NA, 0; bool bGetStagedPackageOriginProbed
0x1800083eb  jnz     short loc_180008422
0x1800083ed  xor     r8d, r8d; dwFlags
0x1800083f0  lea     rcx, aApiMsWinAppmod; "api-ms-win-appmodel-runtime-l1-1-1.dll"
0x1800083f7  xor     edx, edx; hFile
0x1800083f9  call    cs:__imp_LoadLibraryExW
0x1800083ff  test    rax, rax
0x180008402  jz      short loc_18000841B
0x180008404  lea     rdx, aGetstagedpacka; "GetStagedPackageOrigin"
0x18000840b  mov     rcx, rax; hModule
0x18000840e  call    cs:__imp_GetProcAddress
0x180008414  mov     cs:qword_18006FFE8, rax
0x18000841b  mov     cs:?bGetStagedPackageOriginProbed@@3_NA, 1; bool bGetStagedPackageOriginProbed
0x180008422  cmp     cs:qword_18006FFE8, 0
0x18000842a  setnz   al
0x18000842d  add     rsp, 28h
0x180008431  retn
```
