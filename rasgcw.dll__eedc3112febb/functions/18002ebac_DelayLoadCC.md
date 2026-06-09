# DelayLoadCC

- ea: `0x18002ebac`
- end: `0x18002ebfd`
- name: `DelayLoadCC`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ea40`
- `0x18002ef40`

## callees

- `0x18002eb58`
- `0x18002ebac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002ebe1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002ebe1`

## string_xrefs

- `0x18002ebba`: `comctl32.dll`
- `0x18002ebd4`: `comctl32.dll`

## pseudocode

```c
__int64 DelayLoadCC()
{
  __int64 result; // rax

  if ( g_hinstCC )
    return 1;
  g_hinstCC = (HMODULE)SHFusionLoadLibrary(L"comctl32.dll");
  if ( g_hinstCC )
    return 1;
  result = (__int64)LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
  g_hinstCC = (HMODULE)result;
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x18002ebac  sub     rsp, 28h
0x18002ebb0  cmp     cs:g_hinstCC, 0
0x18002ebb8  jnz     short loc_18002EBF3
0x18002ebba  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18002ebc1  call    SHFusionLoadLibrary
0x18002ebc6  mov     cs:g_hinstCC, rax
0x18002ebcd  test    rax, rax
0x18002ebd0  jnz     short loc_18002EBF3
0x18002ebd2  xor     edx, edx; hFile
0x18002ebd4  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18002ebdb  mov     r8d, 4000h; dwFlags
0x18002ebe1  call    cs:__imp_LoadLibraryExW
0x18002ebe7  mov     cs:g_hinstCC, rax
0x18002ebee  test    rax, rax
0x18002ebf1  jz      short loc_18002EBF8
0x18002ebf3  mov     eax, 1
0x18002ebf8  add     rsp, 28h
0x18002ebfc  retn
```
