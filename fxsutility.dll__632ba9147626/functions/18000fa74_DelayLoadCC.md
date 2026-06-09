# DelayLoadCC

- ea: `0x18000fa74`
- end: `0x18000fabe`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f908`
- `0x18000fac4`

## callees

- `0x18000fa14`
- `0x18000fa74`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000faa2`
- `KERNEL32!LoadLibraryExW` at `0x18000faa2`

## string_xrefs

- `0x18000fa95`: `comctl32.dll`

## pseudocode

```c
__int64 DelayLoadCC()
{
  __int64 result; // rax

  if ( g_hinstCC )
    return 1;
  g_hinstCC = SHFusionLoadLibrary();
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
0x18000fa74  sub     rsp, 28h
0x18000fa78  cmp     cs:g_hinstCC, 0
0x18000fa80  jnz     short loc_18000FAB4
0x18000fa82  call    SHFusionLoadLibrary
0x18000fa87  mov     cs:g_hinstCC, rax
0x18000fa8e  test    rax, rax
0x18000fa91  jnz     short loc_18000FAB4
0x18000fa93  xor     edx, edx; hFile
0x18000fa95  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18000fa9c  mov     r8d, 4000h; dwFlags
0x18000faa2  call    cs:__imp_LoadLibraryExW
0x18000faa8  mov     cs:g_hinstCC, rax
0x18000faaf  test    rax, rax
0x18000fab2  jz      short loc_18000FAB9
0x18000fab4  mov     eax, 1
0x18000fab9  add     rsp, 28h
0x18000fabd  retn
```
