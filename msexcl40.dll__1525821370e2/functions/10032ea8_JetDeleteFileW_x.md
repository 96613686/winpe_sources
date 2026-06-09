# JetDeleteFileW(x)

- ea: `0x10032ea8`
- end: `0x10032f0a`
- name: `_JetDeleteFileW@4`
- size: `98`
- prototype: `int __stdcall(LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x10022920`
- `0x100278d3`
- `0x100279f0`
- `0x10029b60`

## callees

- `0x10032925`
- `0x10032956`
- `0x10032ea8`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x10032ecb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x10032ecb`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x10032ee6`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x10032ee6`

## pseudocode

```c
BOOL __stdcall JetDeleteFileW(LPCWSTR lpFileName)
{
  BOOL v1; // esi
  _BYTE v3[4]; // [esp+4h] [ebp-218h] BYREF
  LPCSTR v4; // [esp+8h] [ebp-214h]

  if ( wrap )
    return DeleteFileW(lpFileName);
  CStrIn::CStrIn((CStrIn *)v3, lpFileName);
  v1 = DeleteFileA(v4);
  CConvertStr::Free((CConvertStr *)v3);
  return v1;
}

```

## disassembly

```asm
0x10032ea8  mov     edi, edi
0x10032eaa  push    ebp
0x10032eab  mov     ebp, esp
0x10032ead  sub     esp, 218h
0x10032eb3  mov     eax, ___security_cookie
0x10032eb8  xor     eax, ebp
0x10032eba  mov     [ebp+var_4], eax
0x10032ebd  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10032ec4  mov     eax, [ebp+lpFileName]
0x10032ec7  push    esi
0x10032ec8  push    eax; unsigned __int16 *
0x10032ec9  jz      short loc_10032ED5
0x10032ecb  call    ds:__imp__DeleteFileW@4; DeleteFileW(x)
0x10032ed1  mov     esi, eax
0x10032ed3  jmp     short loc_10032EF9
0x10032ed5  lea     ecx, [ebp+var_218]; this
0x10032edb  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10032ee0  push    [ebp+var_214]; lpFileName
0x10032ee6  call    ds:__imp__DeleteFileA@4; DeleteFileA(x)
0x10032eec  lea     ecx, [ebp+var_218]; this
0x10032ef2  mov     esi, eax
0x10032ef4  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10032ef9  mov     ecx, [ebp+var_4]
0x10032efc  mov     eax, esi
0x10032efe  xor     ecx, ebp; StackCookie
0x10032f00  pop     esi
0x10032f01  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10032f06  leave
0x10032f07  retn    4
```
