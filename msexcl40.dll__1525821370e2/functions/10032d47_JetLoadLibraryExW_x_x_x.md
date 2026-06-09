# JetLoadLibraryExW(x,x,x)

- ea: `0x10032d47`
- end: `0x10032dd4`
- name: `_JetLoadLibraryExW@12`
- size: `141`
- prototype: `int __stdcall(LPCWSTR lpLibFileName, HANDLE hFile, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x10022628`
- `0x1002496b`
- `0x10032dda`
- `0x10034880`

## callees

- `0x10032925`
- `0x10032956`
- `0x10032d47`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x10032daf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x10032daf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x10032d76`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x10032d76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x10032d9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x10032d9a`

## pseudocode

```c
HMODULE __stdcall JetLoadLibraryExW(LPCWSTR lpLibFileName, HANDLE hFile, int a3)
{
  HMODULE Library; // esi
  _BYTE v5[4]; // [esp+8h] [ebp-218h] BYREF
  LPCSTR v6; // [esp+Ch] [ebp-214h]
  int v7; // [esp+218h] [ebp-8h]

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
  CConvertStr::Free((CConvertStr *)v5);
  return Library;
}

```

## disassembly

```asm
0x10032d47  mov     edi, edi
0x10032d49  push    ebp
0x10032d4a  mov     ebp, esp
0x10032d4c  sub     esp, 218h
0x10032d52  mov     eax, ___security_cookie
0x10032d57  xor     eax, ebp
0x10032d59  mov     [ebp+var_4], eax
0x10032d5c  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10032d63  mov     eax, [ebp+lpLibFileName]
0x10032d66  push    esi
0x10032d67  mov     esi, [ebp+arg_8]
0x10032d6a  push    edi
0x10032d6b  mov     edi, [ebp+hFile]
0x10032d6e  jz      short loc_10032D80
0x10032d70  or      esi, 8
0x10032d73  push    esi; dwFlags
0x10032d74  push    edi; hFile
0x10032d75  push    eax; lpLibFileName
0x10032d76  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x10032d7c  mov     esi, eax
0x10032d7e  jmp     short loc_10032DC2
0x10032d80  push    eax; unsigned __int16 *
0x10032d81  lea     ecx, [ebp+var_218]; this
0x10032d87  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10032d8c  cmp     [ebp+var_8], 104h
0x10032d93  jl      short loc_10032DA4
0x10032d95  push    0A1h; dwErrCode
0x10032d9a  call    ds:__imp__SetLastError@4; SetLastError(x)
0x10032da0  xor     esi, esi
0x10032da2  jmp     short loc_10032DB7
0x10032da4  or      esi, 8
0x10032da7  push    esi; dwFlags
0x10032da8  push    edi; hFile
0x10032da9  push    [ebp+var_214]; lpLibFileName
0x10032daf  call    ds:__imp__LoadLibraryExA@12; LoadLibraryExA(x,x,x)
0x10032db5  mov     esi, eax
0x10032db7  lea     ecx, [ebp+var_218]; this
0x10032dbd  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10032dc2  mov     ecx, [ebp+var_4]
0x10032dc5  mov     eax, esi
0x10032dc7  pop     edi
0x10032dc8  xor     ecx, ebp; StackCookie
0x10032dca  pop     esi
0x10032dcb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10032dd0  leave
0x10032dd1  retn    0Ch
```
