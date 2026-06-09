# DelayLoadCC

- ea: `0x18000477c`
- end: `0x1800047c6`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004604`
- `0x18000489c`

## callees

- `0x18000471c`
- `0x18000477c`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800047aa`
- `KERNEL32!LoadLibraryExW` at `0x1800047aa`

## string_xrefs

- `0x18000479d`: `comctl32.dll`

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
0x18000477c  sub     rsp, 28h
0x180004780  cmp     cs:g_hinstCC, 0
0x180004788  jnz     short loc_1800047BC
0x18000478a  call    SHFusionLoadLibrary
0x18000478f  mov     cs:g_hinstCC, rax
0x180004796  test    rax, rax
0x180004799  jnz     short loc_1800047BC
0x18000479b  xor     edx, edx; hFile
0x18000479d  lea     rcx, LibFileName; "comctl32.dll"
0x1800047a4  mov     r8d, 4000h; dwFlags
0x1800047aa  call    cs:__imp_LoadLibraryExW
0x1800047b0  mov     cs:g_hinstCC, rax
0x1800047b7  test    rax, rax
0x1800047ba  jz      short loc_1800047C1
0x1800047bc  mov     eax, 1
0x1800047c1  add     rsp, 28h
0x1800047c5  retn
```
