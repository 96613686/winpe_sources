# JetDeleteFileW(x)

- ea: `0x10046e20`
- end: `0x10046e7b`
- name: `_JetDeleteFileW@4`
- size: `91`
- prototype: `int __stdcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1005112a`
- `0x100536bc`
- `0x1005e0ce`

## callees

- `0x10046833`
- `0x10046864`
- `0x10046e20`
- `0x10123110`
- `0x10124048`
- `0x10124129`
- `0x10124177`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x10046e3c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x10046e3c`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x10046e57`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x10046e57`

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
0x10046e20  push    218h
0x10046e25  mov     eax, offset loc_10124C69
0x10046e2a  call    __EH_prolog3_GS
0x10046e2f  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10046e36  mov     eax, [ebp+lpFileName]
0x10046e39  push    eax; unsigned __int16 *
0x10046e3a  jz      short loc_10046E46
0x10046e3c  call    ds:__imp__DeleteFileW@4; DeleteFileW(x)
0x10046e42  mov     esi, eax
0x10046e44  jmp     short loc_10046E71
0x10046e46  lea     ecx, [ebp+var_224]; this
0x10046e4c  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10046e51  push    [ebp+var_220]; lpFileName
0x10046e57  call    ds:__imp__DeleteFileA@4; DeleteFileA(x)
0x10046e5d  mov     esi, eax
0x10046e5f  lea     ecx, [ebp+var_224]; this
0x10046e65  mov     [ebp+var_4], 0
0x10046e6c  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10046e71  mov     eax, esi
0x10046e73  call    __EH_epilog3_GS
0x10046e78  retn    4
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
