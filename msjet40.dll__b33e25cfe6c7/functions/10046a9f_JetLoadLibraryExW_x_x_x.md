# JetLoadLibraryExW(x,x,x)

- ea: `0x10046a9f`
- end: `0x10046b23`
- name: `_JetLoadLibraryExW@12`
- size: `132`
- prototype: `int __stdcall(LPCWSTR lpLibFileName, HANDLE hFile, int)`
- caller_count: `12`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x100250e0`
- `0x10025150`
- `0x100251c0`
- `0x10025230`
- `0x100252a0`
- `0x10025310`
- `0x10025390`
- `0x10025400`
- `0x10026750`
- `0x10029740`
- `0x10032610`
- `0x100a43f2`

## callees

- `0x100466b3`
- `0x100466e4`
- `0x10046a9f`
- `0x10122f60`
- `0x10123e98`
- `0x10123f79`
- `0x10123fc7`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x10046ac6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x10046ac6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x10046aff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x10046aff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x10046aea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x10046aea`

## pseudocode

```c
HMODULE __stdcall JetLoadLibraryExW(LPCWSTR lpLibFileName, HANDLE hFile, int a3)
{
  HMODULE Library; // esi
  _BYTE v5[4]; // [esp+10h] [ebp-224h] BYREF
  LPCSTR v6; // [esp+14h] [ebp-220h]
  int v7; // [esp+220h] [ebp-14h]
  int v8; // [esp+230h] [ebp-4h]

  if ( wrap )
    return LoadLibraryExW(lpLibFileName, hFile, a3 | 8);
  CStrIn::CStrIn((CStrIn *)v5, lpLibFileName);
  if ( v7 < 260 )
  {
    Library = LoadLibraryExA(v6, hFile, a3 | 8);
  }
  else
  {
    SetLastError(0xA1u);
    Library = 0;
  }
  v8 = 0;
  CConvertStr::Free((CConvertStr *)v5);
  return Library;
}

```

## disassembly

```asm
0x10046a9f  push    218h
0x10046aa4  mov     eax, offset loc_10124AB9
0x10046aa9  call    __EH_prolog3_GS
0x10046aae  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10046ab5  mov     eax, [ebp+lpLibFileName]
0x10046ab8  mov     edi, [ebp+hFile]
0x10046abb  mov     esi, [ebp+arg_8]
0x10046abe  jz      short loc_10046AD0
0x10046ac0  or      esi, 8
0x10046ac3  push    esi; dwFlags
0x10046ac4  push    edi; hFile
0x10046ac5  push    eax; lpLibFileName
0x10046ac6  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x10046acc  mov     esi, eax
0x10046ace  jmp     short loc_10046B19
0x10046ad0  push    eax; unsigned __int16 *
0x10046ad1  lea     ecx, [ebp+var_224]; this
0x10046ad7  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10046adc  cmp     [ebp+var_14], 104h
0x10046ae3  jl      short loc_10046AF4
0x10046ae5  push    0A1h; dwErrCode
0x10046aea  call    ds:__imp__SetLastError@4; SetLastError(x)
0x10046af0  xor     esi, esi
0x10046af2  jmp     short loc_10046B07
0x10046af4  or      esi, 8
0x10046af7  push    esi; dwFlags
0x10046af8  push    edi; hFile
0x10046af9  push    [ebp+var_220]; lpLibFileName
0x10046aff  call    ds:__imp__LoadLibraryExA@12; LoadLibraryExA(x,x,x)
0x10046b05  mov     esi, eax
0x10046b07  lea     ecx, [ebp+var_224]; this
0x10046b0d  mov     [ebp+var_4], 0
0x10046b14  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10046b19  mov     eax, esi
0x10046b1b  call    __EH_epilog3_GS
0x10046b20  retn    0Ch
0x10123eb0  jmp     ds:__imp____std_terminate
0x10124ab9  nop
0x10124aba  nop
0x10124abb  mov     edx, [esp-4+hFile]
0x10124abf  lea     eax, [edx+0Ch]
0x10124ac2  mov     ecx, [edx-228h]
0x10124ac8  xor     ecx, eax; StackCookie
0x10124aca  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124acf  mov     ecx, [edx-4]
0x10124ad2  xor     ecx, eax; StackCookie
0x10124ad4  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124ad9  mov     eax, offset stru_101278F8
0x10124ade  jmp     ___CxxFrameHandler3
```
