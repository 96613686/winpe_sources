# JetLoadLibraryExW(x,x,x)

- ea: `0x10046c1f`
- end: `0x10046ca3`
- name: `_JetLoadLibraryExW@12`
- size: `132`
- prototype: `int __stdcall(LPCWSTR lpLibFileName, HANDLE hFile, int)`
- caller_count: `12`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x10025240`
- `0x100252b0`
- `0x10025320`
- `0x10025390`
- `0x10025400`
- `0x10025470`
- `0x100254f0`
- `0x10025560`
- `0x100268b0`
- `0x10029910`
- `0x100327b0`
- `0x100a4582`

## callees

- `0x10046833`
- `0x10046864`
- `0x10046c1f`
- `0x10123110`
- `0x10124048`
- `0x10124129`
- `0x10124177`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x10046c46`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x10046c46`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x10046c7f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x10046c7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x10046c6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x10046c6a`

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
0x10046c1f  push    218h
0x10046c24  mov     eax, offset loc_10124C69
0x10046c29  call    __EH_prolog3_GS
0x10046c2e  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10046c35  mov     eax, [ebp+lpLibFileName]
0x10046c38  mov     edi, [ebp+hFile]
0x10046c3b  mov     esi, [ebp+arg_8]
0x10046c3e  jz      short loc_10046C50
0x10046c40  or      esi, 8
0x10046c43  push    esi; dwFlags
0x10046c44  push    edi; hFile
0x10046c45  push    eax; lpLibFileName
0x10046c46  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x10046c4c  mov     esi, eax
0x10046c4e  jmp     short loc_10046C99
0x10046c50  push    eax; unsigned __int16 *
0x10046c51  lea     ecx, [ebp+var_224]; this
0x10046c57  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10046c5c  cmp     [ebp+var_14], 104h
0x10046c63  jl      short loc_10046C74
0x10046c65  push    0A1h; dwErrCode
0x10046c6a  call    ds:__imp__SetLastError@4; SetLastError(x)
0x10046c70  xor     esi, esi
0x10046c72  jmp     short loc_10046C87
0x10046c74  or      esi, 8
0x10046c77  push    esi; dwFlags
0x10046c78  push    edi; hFile
0x10046c79  push    [ebp+var_220]; lpLibFileName
0x10046c7f  call    ds:__imp__LoadLibraryExA@12; LoadLibraryExA(x,x,x)
0x10046c85  mov     esi, eax
0x10046c87  lea     ecx, [ebp+var_224]; this
0x10046c8d  mov     [ebp+var_4], 0
0x10046c94  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10046c99  mov     eax, esi
0x10046c9b  call    __EH_epilog3_GS
0x10046ca0  retn    0Ch
0x10124060  jmp     ds:__imp____std_terminate
0x10124c69  nop
0x10124c6a  nop
0x10124c6b  mov     edx, [esp-4+hFile]
0x10124c6f  lea     eax, [edx+0Ch]
0x10124c72  mov     ecx, [edx-228h]
0x10124c78  xor     ecx, eax; StackCookie
0x10124c7a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124c7f  mov     ecx, [edx-4]
0x10124c82  xor     ecx, eax; StackCookie
0x10124c84  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124c89  mov     eax, offset stru_10127AA8
0x10124c8e  jmp     ___CxxFrameHandler3
```
