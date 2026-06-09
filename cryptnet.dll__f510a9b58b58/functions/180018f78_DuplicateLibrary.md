# DuplicateLibrary

- ea: `0x180018f78`
- end: `0x180018ff1`
- name: `DuplicateLibrary`
- size: `121`
- prototype: `HMODULE()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d5d0`

## callees

- `0x180018f78`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018fca`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018fca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180018fab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180018fab`

## pseudocode

```c
HMODULE DuplicateLibrary()
{
  HMODULE result; // rax
  WCHAR Filename[264]; // [rsp+20h] [rbp-228h] BYREF

  result = hCrobuModule;
  if ( hCrobuModule )
  {
    if ( !GetModuleFileNameW(hCrobuModule, Filename, 0x104u) )
      return 0;
    Filename[260] = 0;
    result = LoadLibraryExW(Filename, 0, 0x11u);
    if ( !result )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180018f78  sub     rsp, 248h
0x180018f7f  mov     rax, cs:__security_cookie
0x180018f86  xor     rax, rsp
0x180018f89  mov     [rsp+248h+var_18], rax
0x180018f91  mov     rax, cs:?hCrobuModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hCrobuModule
0x180018f98  test    rax, rax
0x180018f9b  jz      short loc_180018FD5
0x180018f9d  mov     r8d, 104h; nSize
0x180018fa3  lea     rdx, [rsp+248h+Filename]; lpFilename
0x180018fa8  mov     rcx, rax; hModule
0x180018fab  call    cs:__imp_GetModuleFileNameW
0x180018fb1  test    eax, eax
0x180018fb3  jz      short loc_180018FED
0x180018fb5  xor     eax, eax
0x180018fb7  lea     rcx, [rsp+248h+Filename]; lpLibFileName
0x180018fbc  xor     edx, edx; hFile
0x180018fbe  mov     [rsp+248h+var_20], ax
0x180018fc6  lea     r8d, [rax+11h]; dwFlags
0x180018fca  call    cs:__imp_LoadLibraryExW
0x180018fd0  test    rax, rax
0x180018fd3  jz      short loc_180018FED
0x180018fd5  mov     rcx, [rsp+248h+var_18]
0x180018fdd  xor     rcx, rsp; StackCookie
0x180018fe0  call    __security_check_cookie
0x180018fe5  add     rsp, 248h
0x180018fec  retn
0x180018fed  xor     eax, eax
0x180018fef  jmp     short loc_180018FD5
```
