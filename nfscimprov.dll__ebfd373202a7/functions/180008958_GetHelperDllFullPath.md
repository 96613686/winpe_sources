# GetHelperDllFullPath

- ea: `0x180008958`
- end: `0x1800089fc`
- name: `GetHelperDllFullPath`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008a30`

## callees

- `0x180008958`
- `0x180035b40`

## import_xrefs

- `msvcrt!malloc` at `0x18000899a`
- `msvcrt!malloc` at `0x18000899a`
- `msvcrt!free` at `0x1800089d6`
- `msvcrt!free` at `0x1800089d6`
- `msvcrt!swprintf_s` at `0x1800089c8`
- `msvcrt!swprintf_s` at `0x1800089c8`
- `KERNEL32!GetSystemDirectoryW` at `0x180008984`
- `KERNEL32!GetSystemDirectoryW` at `0x180008984`

## string_xrefs

- `0x1800089a8`: `wmitomi.dll`

## pseudocode

```c
void *GetHelperDllFullPath()
{
  signed int SystemDirectoryW; // eax
  void *v1; // rbx
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  Buffer[0] = 0;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( !SystemDirectoryW )
    return 0;
  if ( SystemDirectoryW > 260 )
    return 0;
  v1 = malloc(0x208u);
  if ( !v1 )
    return 0;
  if ( swprintf_s((wchar_t *const)v1, 0x104u, L"%s\\%s", Buffer, L"wmitomi.dll") == -1 )
  {
    free(v1);
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x180008958  push    rbx
0x18000895a  sub     rsp, 250h
0x180008961  mov     rax, cs:__security_cookie
0x180008968  xor     rax, rsp
0x18000896b  mov     [rsp+258h+var_18], rax
0x180008973  xor     eax, eax
0x180008975  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18000897a  mov     edx, 104h; uSize
0x18000897f  mov     [rsp+258h+Buffer], ax
0x180008984  call    cs:__imp_GetSystemDirectoryW
0x18000898a  test    eax, eax
0x18000898c  jz      short loc_1800089DC
0x18000898e  cmp     eax, 104h
0x180008993  jg      short loc_1800089DC
0x180008995  mov     ecx, 208h; Size
0x18000899a  call    cs:__imp_malloc
0x1800089a0  mov     rbx, rax
0x1800089a3  test    rax, rax
0x1800089a6  jz      short loc_1800089DC
0x1800089a8  lea     rax, aWmitomiDll; "wmitomi.dll"
0x1800089af  mov     edx, 104h; BufferCount
0x1800089b4  lea     r9, [rsp+258h+Buffer]
0x1800089b9  mov     [rsp+258h+var_238], rax
0x1800089be  lea     r8, aSS; "%s\\%s"
0x1800089c5  mov     rcx, rbx; Buffer
0x1800089c8  call    cs:__imp_swprintf_s
0x1800089ce  cmp     eax, 0FFFFFFFFh
0x1800089d1  jnz     short loc_1800089F7
0x1800089d3  mov     rcx, rbx; Block
0x1800089d6  call    cs:__imp_free
0x1800089dc  xor     eax, eax
0x1800089de  mov     rcx, [rsp+258h+var_18]
0x1800089e6  xor     rcx, rsp; StackCookie
0x1800089e9  call    __security_check_cookie
0x1800089ee  add     rsp, 250h
0x1800089f5  pop     rbx
0x1800089f6  retn
0x1800089f7  mov     rax, rbx
0x1800089fa  jmp     short loc_1800089DE
```
