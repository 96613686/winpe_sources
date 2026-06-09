# DelayLoadCC

- ea: `0x14000db28`
- end: `0x14000db79`
- name: `DelayLoadCC`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d998`

## callees

- `0x14000dabc`
- `0x14000db28`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14000db56`
- `KERNEL32!LoadLibraryExW` at `0x14000db56`

## string_xrefs

- `0x14000db49`: `comctl32.dll`

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
0x14000db28  sub     rsp, 28h
0x14000db2c  cmp     cs:g_hinstCC, 0
0x14000db34  jnz     short loc_14000DB6E
0x14000db36  call    SHFusionLoadLibrary
0x14000db3b  mov     cs:g_hinstCC, rax
0x14000db42  test    rax, rax
0x14000db45  jnz     short loc_14000DB6E
0x14000db47  xor     edx, edx; hFile
0x14000db49  lea     rcx, aComctl32Dll; "comctl32.dll"
0x14000db50  mov     r8d, 4000h; dwFlags
0x14000db56  call    cs:__imp_LoadLibraryExW
0x14000db5d  nop     dword ptr [rax+rax+00h]
0x14000db62  mov     cs:g_hinstCC, rax
0x14000db69  test    rax, rax
0x14000db6c  jz      short loc_14000DB73
0x14000db6e  mov     eax, 1
0x14000db73  add     rsp, 28h
0x14000db77  retn
```
