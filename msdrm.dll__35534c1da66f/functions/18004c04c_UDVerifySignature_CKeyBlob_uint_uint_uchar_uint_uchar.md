# UDVerifySignature(CKeyBlob *,uint,uint,uchar *,uint,uchar *)

- ea: `0x18004c04c`
- end: `0x18004c224`
- name: `?UDVerifySignature@@YAJPEAVCKeyBlob@@IIPEAEI1@Z`
- size: `472`
- prototype: `int(struct CKeyBlob *, unsigned int, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180040648`

## callees

- `0x18004c04c`
- `0x18004c904`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c1ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c1ce`
- `CRYPTSP!CryptDestroyHash` at `0x18004c1f7`
- `CRYPTSP!CryptDestroyHash` at `0x18004c1f7`
- `CRYPTSP!CryptCreateHash` at `0x18004c146`
- `CRYPTSP!CryptCreateHash` at `0x18004c146`
- `CRYPTSP!CryptDestroyKey` at `0x18004c209`
- `CRYPTSP!CryptDestroyKey` at `0x18004c209`
- `CRYPTSP!CryptSetHashParam` at `0x18004c15f`
- `CRYPTSP!CryptSetHashParam` at `0x18004c15f`
- `CRYPTSP!CryptVerifySignatureA` at `0x18004c1af`
- `CRYPTSP!CryptVerifySignatureA` at `0x18004c1af`

## pseudocode

```c
__int64 __fastcall UDVerifySignature(
        struct CKeyBlob *a1,
        ALG_ID a2,
        int a3,
        unsigned __int8 *a4,
        DWORD dwSigLen,
        unsigned __int8 *pbSignature)
{
  unsigned __int8 *v8; // rdi
  signed int v9; // ebx
  unsigned int v10; // edx
  unsigned int v11; // edx
  unsigned __int8 *v12; // r9
  unsigned __int8 *v13; // rsi
  unsigned __int8 *v14; // rdx
  unsigned __int8 v15; // cl
  BOOL v16; // eax
  unsigned __int8 v17; // dl
  signed int LastError; // eax
  HCRYPTHASH hHash; // [rsp+30h] [rbp-48h] BYREF
  HCRYPTKEY hPubKey; // [rsp+38h] [rbp-40h] BYREF
  HCRYPTPROV hProv[7]; // [rsp+40h] [rbp-38h] BYREF

  if ( (a2 != 32772 || a3 != 20) && (a2 != 32780 || a3 != 32) )
    return (unsigned int)-2147024809;
  hProv[0] = 0;
  hPubKey = 0;
  hHash = 0;
  if ( !a4 || (v8 = pbSignature) == 0 )
    return (unsigned int)-2147024809;
  if ( *((_BYTE *)a1 + 1) != 2 || *((_WORD *)a1 + 1) || (unsigned int)(*((_DWORD *)a1 + 293) - 84) > 0x440 )
    return (unsigned int)-2146893821;
  if ( *((_DWORD *)a1 + 2) == 826364754 )
  {
    if ( *(_BYTE *)a1 != 6 )
      return (unsigned int)-2146893821;
  }
  else if ( *((_DWORD *)a1 + 2) != 843141970 || *(_BYTE *)a1 != 7 )
  {
    return (unsigned int)-2146893821;
  }
  v10 = *((_DWORD *)a1 + 3);
  if ( (v10 & 7) != 0 )
    return (unsigned int)-2146893821;
  v11 = v10 >> 3;
  if ( ((v11 - 64) & 0xFFFFFF3F) != 0 || v11 == 192 )
    return (unsigned int)-2146893821;
  v9 = UDCAPI_ImportKey(a1, hProv, &hPubKey);
  if ( v9 >= 0 )
  {
    if ( !CryptCreateHash(hProv[0], a2, 0, 0, &hHash) || !CryptSetHashParam(hHash, 2u, a4, 0) )
      goto LABEL_28;
    v12 = pbSignature;
    v13 = &pbSignature[dwSigLen - 1];
    v14 = v13;
    if ( pbSignature < v13 )
    {
      do
      {
        v15 = *v12;
        *v12++ = *v14;
        *v14-- = v15;
      }
      while ( v12 < v14 );
    }
    v16 = CryptVerifySignatureA(hHash, pbSignature, dwSigLen, hPubKey, 0, 0);
    while ( v8 < v13 )
    {
      v17 = *v8;
      *v8++ = *v13;
      *v13-- = v17;
    }
    if ( !v16 )
    {
LABEL_28:
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( v9 >= 0 )
        v9 = -2147467259;
    }
  }
  if ( hHash )
    CryptDestroyHash(hHash);
  if ( hPubKey )
    CryptDestroyKey(hPubKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004c04c  push    rbx
0x18004c04e  push    rsi
0x18004c04f  push    rdi
0x18004c050  push    r14
0x18004c052  push    r15
0x18004c054  sub     rsp, 50h
0x18004c058  mov     r14, r9
0x18004c05b  mov     esi, edx
0x18004c05d  cmp     edx, 8004h
0x18004c063  jnz     short loc_18004C06B
0x18004c065  cmp     r8d, 14h
0x18004c069  jz      short loc_18004C081
0x18004c06b  cmp     esi, 800Ch
0x18004c071  jnz     loc_18004C211
0x18004c077  cmp     r8d, 20h ; ' '
0x18004c07b  jnz     loc_18004C211
0x18004c081  xor     r15d, r15d
0x18004c084  mov     [rsp+78h+hProv], r15
0x18004c089  mov     [rsp+78h+hPubKey], r15
0x18004c08e  mov     [rsp+78h+hHash], r15
0x18004c093  test    r8d, r8d
0x18004c096  jz      loc_18004C211
0x18004c09c  test    r14, r14
0x18004c09f  jz      loc_18004C211
0x18004c0a5  mov     rdi, [rsp+78h+pbSignature]
0x18004c0ad  test    rdi, rdi
0x18004c0b0  jz      loc_18004C211
0x18004c0b6  cmp     byte ptr [rcx+1], 2
0x18004c0ba  jnz     short loc_18004C0E1
0x18004c0bc  cmp     [rcx+2], r15w
0x18004c0c1  jnz     short loc_18004C0E1
0x18004c0c3  mov     eax, [rcx+494h]
0x18004c0c9  sub     eax, 54h ; 'T'
0x18004c0cc  cmp     eax, 440h
0x18004c0d1  ja      short loc_18004C0E1
0x18004c0d3  cmp     dword ptr [rcx+8], 31415352h
0x18004c0da  jnz     short loc_18004C0EB
0x18004c0dc  cmp     byte ptr [rcx], 6
0x18004c0df  jz      short loc_18004C0F9
0x18004c0e1  mov     ebx, 80090003h
0x18004c0e6  jmp     loc_18004C216
0x18004c0eb  cmp     dword ptr [rcx+8], 32415352h
0x18004c0f2  jnz     short loc_18004C0E1
0x18004c0f4  cmp     byte ptr [rcx], 7
0x18004c0f7  jnz     short loc_18004C0E1
0x18004c0f9  mov     edx, [rcx+0Ch]
0x18004c0fc  test    dl, 7
0x18004c0ff  jnz     short loc_18004C0E1
0x18004c101  shr     edx, 3
0x18004c104  lea     eax, [rdx-40h]
0x18004c107  test    eax, 0FFFFFF3Fh
0x18004c10c  jnz     short loc_18004C0E1
0x18004c10e  cmp     edx, 0C0h
0x18004c114  jz      short loc_18004C0E1
0x18004c116  lea     r8, [rsp+78h+hPubKey]; unsigned __int64 *
0x18004c11b  lea     rdx, [rsp+78h+hProv]; unsigned __int64 *
0x18004c120  call    ?UDCAPI_ImportKey@@YAJPEAVCKeyBlob@@PEA_K1@Z; UDCAPI_ImportKey(CKeyBlob *,unsigned __int64 *,unsigned __int64 *)
0x18004c125  mov     ebx, eax
0x18004c127  test    eax, eax
0x18004c129  js      loc_18004C1ED
0x18004c12f  mov     rcx, [rsp+78h+hProv]; hProv
0x18004c134  lea     rax, [rsp+78h+hHash]
0x18004c139  xor     r9d, r9d; dwFlags
0x18004c13c  mov     [rsp+78h+phHash], rax; phHash
0x18004c141  xor     r8d, r8d; hKey
0x18004c144  mov     edx, esi; Algid
0x18004c146  call    cs:__imp_CryptCreateHash
0x18004c14c  test    eax, eax
0x18004c14e  jz      short loc_18004C1CE
0x18004c150  mov     rcx, [rsp+78h+hHash]; hHash
0x18004c155  xor     r9d, r9d; dwFlags
0x18004c158  mov     r8, r14; pbData
0x18004c15b  lea     edx, [r9+2]; dwParam
0x18004c15f  call    cs:__imp_CryptSetHashParam
0x18004c165  test    eax, eax
0x18004c167  jz      short loc_18004C1CE
0x18004c169  mov     r8d, [rsp+78h+dwSigLen]; dwSigLen
0x18004c171  mov     r9, rdi
0x18004c174  lea     rsi, [r8-1]
0x18004c178  add     rsi, rdi
0x18004c17b  mov     rdx, rsi
0x18004c17e  cmp     rdi, rsi
0x18004c181  jnb     short loc_18004C198
0x18004c183  mov     al, [rdx]
0x18004c185  mov     cl, [r9]
0x18004c188  mov     [r9], al
0x18004c18b  inc     r9
0x18004c18e  mov     [rdx], cl
0x18004c190  dec     rdx
0x18004c193  cmp     r9, rdx
0x18004c196  jb      short loc_18004C183
0x18004c198  mov     r9, [rsp+78h+hPubKey]; hPubKey
0x18004c19d  mov     rdx, rdi; pbSignature
0x18004c1a0  mov     rcx, [rsp+78h+hHash]; hHash
0x18004c1a5  mov     [rsp+78h+dwFlags], r15d; dwFlags
0x18004c1aa  mov     [rsp+78h+phHash], r15; szDescription
0x18004c1af  call    cs:__imp_CryptVerifySignatureA
0x18004c1b5  jmp     short loc_18004C1C5
0x18004c1b7  mov     cl, [rsi]
0x18004c1b9  mov     dl, [rdi]
0x18004c1bb  mov     [rdi], cl
0x18004c1bd  inc     rdi
0x18004c1c0  mov     [rsi], dl
0x18004c1c2  dec     rsi
0x18004c1c5  cmp     rdi, rsi
0x18004c1c8  jb      short loc_18004C1B7
0x18004c1ca  test    eax, eax
0x18004c1cc  jnz     short loc_18004C1ED
0x18004c1ce  call    cs:__imp_GetLastError
0x18004c1d4  mov     ebx, eax
0x18004c1d6  test    eax, eax
0x18004c1d8  jle     short loc_18004C1E3
0x18004c1da  movzx   ebx, ax
0x18004c1dd  or      ebx, 80070000h
0x18004c1e3  test    ebx, ebx
0x18004c1e5  mov     eax, 80004005h
0x18004c1ea  cmovns  ebx, eax
0x18004c1ed  mov     rcx, [rsp+78h+hHash]; hHash
0x18004c1f2  test    rcx, rcx
0x18004c1f5  jz      short loc_18004C1FD
0x18004c1f7  call    cs:__imp_CryptDestroyHash
0x18004c1fd  cmp     [rsp+78h+hPubKey], r15
0x18004c202  jz      short loc_18004C216
0x18004c204  mov     rcx, [rsp+78h+hPubKey]; hKey
0x18004c209  call    cs:__imp_CryptDestroyKey
0x18004c20f  jmp     short loc_18004C216
0x18004c211  mov     ebx, 80070057h
0x18004c216  mov     eax, ebx
0x18004c218  add     rsp, 50h
0x18004c21c  pop     r15
0x18004c21e  pop     r14
0x18004c220  pop     rdi
0x18004c221  pop     rsi
0x18004c222  pop     rbx
0x18004c223  retn
```
