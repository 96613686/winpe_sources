# JetDeleteFileW(x)

- ea: `0x10046ca0`
- end: `0x10046cfb`
- name: `_JetDeleteFileW@4`
- size: `91`
- prototype: `int __stdcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x10050f9a`
- `0x1005352c`
- `0x1005df3e`

## callees

- `0x100466b3`
- `0x100466e4`
- `0x10046ca0`
- `0x10122f60`
- `0x10123e98`
- `0x10123f79`
- `0x10123fc7`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x10046cbc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x10046cbc`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x10046cd7`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x10046cd7`

## pseudocode

```c
BOOL __stdcall JetDeleteFileW(LPCWSTR lpFileName)
{
  BOOL v1; // esi
  _BYTE v3[4]; // [esp+10h] [ebp-224h] BYREF
  LPCSTR v4; // [esp+14h] [ebp-220h]
  int v5; // [esp+230h] [ebp-4h]

  if ( wrap )
    return DeleteFileW(lpFileName);
  CStrIn::CStrIn((CStrIn *)v3, lpFileName);
  v1 = DeleteFileA(v4);
  v5 = 0;
  CConvertStr::Free((CConvertStr *)v3);
  return v1;
}

```

## disassembly

```asm
0x10046ca0  push    218h
0x10046ca5  mov     eax, offset loc_10124AB9
0x10046caa  call    __EH_prolog3_GS
0x10046caf  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10046cb6  mov     eax, [ebp+lpFileName]
0x10046cb9  push    eax; unsigned __int16 *
0x10046cba  jz      short loc_10046CC6
0x10046cbc  call    ds:__imp__DeleteFileW@4; DeleteFileW(x)
0x10046cc2  mov     esi, eax
0x10046cc4  jmp     short loc_10046CF1
0x10046cc6  lea     ecx, [ebp+var_224]; this
0x10046ccc  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10046cd1  push    [ebp+var_220]; lpFileName
0x10046cd7  call    ds:__imp__DeleteFileA@4; DeleteFileA(x)
0x10046cdd  mov     esi, eax
0x10046cdf  lea     ecx, [ebp+var_224]; this
0x10046ce5  mov     [ebp+var_4], 0
0x10046cec  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10046cf1  mov     eax, esi
0x10046cf3  call    __EH_epilog3_GS
0x10046cf8  retn    4
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
