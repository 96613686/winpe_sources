# DelayLoadCC

- ea: `0x14001c234`
- end: `0x14001c27e`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001bf88`
- `0x14001c010`
- `0x14001c0c4`

## callees

- `0x14001c1dc`
- `0x14001c234`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14001c262`
- `KERNEL32!LoadLibraryExW` at `0x14001c262`

## string_xrefs

- `0x14001c255`: `comctl32.dll`

## pseudocode

```c
__int64 DelayLoadCC()
{
  __int64 result; // rax

  if ( g_hinstCC )
    return 1;
  g_hinstCC = (__int64)SHFusionLoadLibrary();
  if ( g_hinstCC )
    return 1;
  result = (__int64)LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
  g_hinstCC = result;
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x14001c234  sub     rsp, 28h
0x14001c238  cmp     cs:g_hinstCC, 0
0x14001c240  jnz     short loc_14001C274
0x14001c242  call    SHFusionLoadLibrary
0x14001c247  mov     cs:g_hinstCC, rax
0x14001c24e  test    rax, rax
0x14001c251  jnz     short loc_14001C274
0x14001c253  xor     edx, edx; hFile
0x14001c255  lea     rcx, aComctl32Dll; "comctl32.dll"
0x14001c25c  mov     r8d, 4000h; dwFlags
0x14001c262  call    cs:__imp_LoadLibraryExW
0x14001c268  mov     cs:g_hinstCC, rax
0x14001c26f  test    rax, rax
0x14001c272  jz      short loc_14001C279
0x14001c274  mov     eax, 1
0x14001c279  add     rsp, 28h
0x14001c27d  retn
```
