# DelayLoadCC

- ea: `0x18001c888`
- end: `0x18001c8d9`
- name: `DelayLoadCC`
- size: `81`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e918`
- `0x180015870`
- `0x18001c134`
- `0x18001c210`
- `0x18001c298`
- `0x18001cc10`

## callees

- `0x18001c3a4`
- `0x18001c888`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001c8bd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001c8bd`

## string_xrefs

- `0x18001c896`: `comctl32.dll`
- `0x18001c8b0`: `comctl32.dll`

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
0x18001c888  sub     rsp, 28h
0x18001c88c  cmp     cs:g_hinstCC, 0
0x18001c894  jnz     short loc_18001C8CF
0x18001c896  lea     rcx, LibFileName; "comctl32.dll"
0x18001c89d  call    SHFusionLoadLibrary
0x18001c8a2  mov     cs:g_hinstCC, rax
0x18001c8a9  test    rax, rax
0x18001c8ac  jnz     short loc_18001C8CF
0x18001c8ae  xor     edx, edx; hFile
0x18001c8b0  lea     rcx, LibFileName; "comctl32.dll"
0x18001c8b7  mov     r8d, 4000h; dwFlags
0x18001c8bd  call    cs:__imp_LoadLibraryExW
0x18001c8c3  mov     cs:g_hinstCC, rax
0x18001c8ca  test    rax, rax
0x18001c8cd  jz      short loc_18001C8D4
0x18001c8cf  mov     eax, 1
0x18001c8d4  add     rsp, 28h
0x18001c8d8  retn
```
