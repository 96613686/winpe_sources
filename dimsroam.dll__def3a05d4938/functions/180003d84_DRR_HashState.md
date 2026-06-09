# DRR_HashState

- ea: `0x180003d84`
- end: `0x180003e68`
- name: `DRR_HashState`
- size: `228`
- prototype: `__int64 __fastcall(__int64, BYTE *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800036c8`
- `0x180005c00`
- `0x180006230`

## callees

- `0x180003d84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e3e`
- `CRYPTSP!CryptGetHashParam` at `0x180003e34`
- `CRYPTSP!CryptGetHashParam` at `0x180003e34`
- `CRYPTSP!CryptCreateHash` at `0x180003dc4`
- `CRYPTSP!CryptCreateHash` at `0x180003dc4`
- `CRYPTSP!CryptDestroyHash` at `0x180003e50`
- `CRYPTSP!CryptDestroyHash` at `0x180003e50`
- `CRYPTSP!CryptHashData` at `0x180003dde`
- `CRYPTSP!CryptHashData` at `0x180003e05`
- `CRYPTSP!CryptHashData` at `0x180003dde`
- `CRYPTSP!CryptHashData` at `0x180003e05`

## pseudocode

```c
__int64 __fastcall DRR_HashState(__int64 a1, BYTE *a2)
{
  __int64 v4; // rbx
  DWORD LastError; // ebx
  DWORD pdwDataLen; // [rsp+50h] [rbp+18h] BYREF
  HCRYPTHASH hHash; // [rsp+58h] [rbp+20h] BYREF

  pdwDataLen = 0;
  hHash = 0;
  if ( CryptCreateHash(hProv, 0x8003u, 0, 0, &hHash) && CryptHashData(hHash, (const BYTE *)(a1 + 24), 0x58u, 0) )
  {
    v4 = 0;
    if ( *(_DWORD *)(a1 + 120) )
    {
      while ( CryptHashData(hHash, *(const BYTE **)(*(_QWORD *)(a1 + 112) + 8 * v4), 0x80u, 0) )
      {
        v4 = (unsigned int)(v4 + 1);
        if ( (unsigned int)v4 >= *(_DWORD *)(a1 + 120) )
          goto LABEL_6;
      }
    }
    else
    {
LABEL_6:
      LastError = 0;
      pdwDataLen = 16;
      if ( CryptGetHashParam(hHash, 2u, a2, &pdwDataLen, 0) )
        goto LABEL_8;
    }
  }
  LastError = GetLastError();
LABEL_8:
  if ( hHash )
    CryptDestroyHash(hHash);
  return LastError;
}

```

## disassembly

```asm
0x180003d84  mov     rax, rsp
0x180003d87  mov     [rax+8], rbx
0x180003d8b  mov     [rax+10h], rsi
0x180003d8f  push    rdi
0x180003d90  sub     rsp, 30h
0x180003d94  mov     dword ptr [rax+18h], 0
0x180003d9b  mov     rsi, rdx
0x180003d9e  mov     qword ptr [rax+20h], 0
0x180003da6  lea     rax, [rax+20h]
0x180003daa  mov     rdi, rcx
0x180003dad  mov     [rsp+38h+phHash], rax; phHash
0x180003db2  mov     rcx, cs:hProv; hProv
0x180003db9  xor     r9d, r9d; dwFlags
0x180003dbc  xor     r8d, r8d; hKey
0x180003dbf  mov     edx, 8003h; Algid
0x180003dc4  call    cs:__imp_CryptCreateHash
0x180003dca  test    eax, eax
0x180003dcc  jz      short loc_180003E3E
0x180003dce  mov     rcx, [rsp+38h+hHash]; hHash
0x180003dd3  lea     rdx, [rdi+18h]; pbData
0x180003dd7  xor     r9d, r9d; dwFlags
0x180003dda  lea     r8d, [r9+58h]; dwDataLen
0x180003dde  call    cs:__imp_CryptHashData
0x180003de4  test    eax, eax
0x180003de6  jz      short loc_180003E3E
0x180003de8  xor     ebx, ebx
0x180003dea  cmp     [rdi+78h], ebx
0x180003ded  jbe     short loc_180003E16
0x180003def  mov     rdx, [rdi+70h]
0x180003df3  xor     r9d, r9d; dwFlags
0x180003df6  mov     rcx, [rsp+38h+hHash]; hHash
0x180003dfb  mov     r8d, 80h; dwDataLen
0x180003e01  mov     rdx, [rdx+rbx*8]; pbData
0x180003e05  call    cs:__imp_CryptHashData
0x180003e0b  test    eax, eax
0x180003e0d  jz      short loc_180003E3E
0x180003e0f  inc     ebx
0x180003e11  cmp     ebx, [rdi+78h]
0x180003e14  jb      short loc_180003DEF
0x180003e16  mov     rcx, [rsp+38h+hHash]; hHash
0x180003e1b  lea     r9, [rsp+38h+pdwDataLen]; pdwDataLen
0x180003e20  xor     ebx, ebx
0x180003e22  mov     [rsp+38h+pdwDataLen], 10h
0x180003e2a  mov     r8, rsi; pbData
0x180003e2d  mov     dword ptr [rsp+38h+phHash], ebx; dwFlags
0x180003e31  lea     edx, [rbx+2]; dwParam
0x180003e34  call    cs:__imp_CryptGetHashParam
0x180003e3a  test    eax, eax
0x180003e3c  jnz     short loc_180003E46
0x180003e3e  call    cs:__imp_GetLastError
0x180003e44  mov     ebx, eax
0x180003e46  mov     rcx, [rsp+38h+hHash]; hHash
0x180003e4b  test    rcx, rcx
0x180003e4e  jz      short loc_180003E56
0x180003e50  call    cs:__imp_CryptDestroyHash
0x180003e56  mov     rsi, [rsp+38h+arg_8]
0x180003e5b  mov     eax, ebx
0x180003e5d  mov     rbx, [rsp+38h+arg_0]
0x180003e62  add     rsp, 30h
0x180003e66  pop     rdi
0x180003e67  retn
```
