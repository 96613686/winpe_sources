# LoadRasTlsDll

- ea: `0x1800c5520`
- end: `0x1800c558a`
- name: `LoadRasTlsDll`
- size: `106`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800357e8`
- `0x18007c380`
- `0x1800a7f48`

## callees

- `0x1800c5480`
- `0x1800c5520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5555`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c5577`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c5577`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c5547`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c5547`

## string_xrefs

- `0x1800c553a`: `RASTLS.DLL`

## pseudocode

```c
DWORD LoadRasTlsDll()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  int RasTlsDLLGlobalFunctions; // edi

  if ( g_hRasTlsDll )
    return 0;
  Library = LoadLibraryExW(L"RASTLS.DLL", 0, 0x800u);
  v2 = Library;
  if ( !Library )
    return GetLastError();
  RasTlsDLLGlobalFunctions = LoadRasTlsDLLGlobalFunctions(Library);
  if ( RasTlsDLLGlobalFunctions )
    FreeLibrary(v2);
  else
    g_hRasTlsDll = v2;
  return RasTlsDLLGlobalFunctions;
}

```

## disassembly

```asm
0x1800c5520  mov     [rsp+arg_0], rbx
0x1800c5525  push    rdi
0x1800c5526  sub     rsp, 20h
0x1800c552a  cmp     cs:g_hRasTlsDll, 0
0x1800c5532  jz      short loc_1800C5538
0x1800c5534  xor     eax, eax
0x1800c5536  jmp     short loc_1800C557F
0x1800c5538  xor     edx, edx; hFile
0x1800c553a  lea     rcx, aRastlsDll; "RASTLS.DLL"
0x1800c5541  mov     r8d, 800h; dwFlags
0x1800c5547  call    cs:__imp_LoadLibraryExW
0x1800c554d  mov     rbx, rax
0x1800c5550  test    rax, rax
0x1800c5553  jnz     short loc_1800C555D
0x1800c5555  call    cs:__imp_GetLastError
0x1800c555b  jmp     short loc_1800C557F
0x1800c555d  mov     rcx, rbx; hModule
0x1800c5560  call    LoadRasTlsDLLGlobalFunctions
0x1800c5565  mov     edi, eax
0x1800c5567  test    eax, eax
0x1800c5569  jnz     short loc_1800C5574
0x1800c556b  mov     cs:g_hRasTlsDll, rbx
0x1800c5572  jmp     short loc_1800C557D
0x1800c5574  mov     rcx, rbx; hLibModule
0x1800c5577  call    cs:__imp_FreeLibrary
0x1800c557d  mov     eax, edi
0x1800c557f  mov     rbx, [rsp+28h+arg_0]
0x1800c5584  add     rsp, 20h
0x1800c5588  pop     rdi
0x1800c5589  retn
```
