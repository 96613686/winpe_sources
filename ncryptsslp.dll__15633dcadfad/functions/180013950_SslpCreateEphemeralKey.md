# SslpCreateEphemeralKey

- ea: `0x180013950`
- end: `0x180013b79`
- name: `SslpCreateEphemeralKey`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011a40`

## callees

- `0x18000b594`
- `0x18000b654`
- `0x180013950`
- `0x180013b80`
- `0x180013e6c`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x180013a52`
- `ncrypt!NCryptSetProperty` at `0x180013a87`
- `ncrypt!NCryptSetProperty` at `0x180013acf`
- `ncrypt!NCryptSetProperty` at `0x180013a52`
- `ncrypt!NCryptSetProperty` at `0x180013a87`
- `ncrypt!NCryptSetProperty` at `0x180013acf`
- `ncrypt!NCryptFinalizeKey` at `0x180013aeb`
- `ncrypt!NCryptFinalizeKey` at `0x180013aeb`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800139e7`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800139e7`

## string_xrefs

- `0x1800139a8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsephemeral.c`
- `0x1800139f9`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsephemeral.c`
- `0x180013b29`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsephemeral.c`

## pseudocode

```c
__int64 __fastcall SslpCreateEphemeralKey(
        __int64 *a1,
        const WCHAR *a2,
        int a3,
        unsigned __int16 a4,
        PBYTE pbInput,
        BYTE a6,
        PBYTE a7,
        DWORD cbInput)
{
  __int64 v11; // rdi
  int v12; // eax
  unsigned int v13; // ebx
  NCRYPT_HANDLE *v14; // r14
  SECURITY_STATUS PersistedKey; // eax
  __int64 v16; // r9
  __int64 v17; // r9
  __int64 v19; // [rsp+70h] [rbp+8h] BYREF

  v19 = 0;
  v11 = 0;
  if ( a1 && a2 )
  {
    v12 = SslpCreateBaseEphemeralKeyStruct((__int64)a1, a4, a3, &v19);
    v13 = v12;
    if ( v12 < 0 )
    {
      DebugTraceError(
        (unsigned int)v12,
        "status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsephemeral.c",
        156);
      v11 = v19;
      goto LABEL_28;
    }
    v11 = v19;
    v14 = (NCRYPT_HANDLE *)(v19 + 24);
    PersistedKey = NCryptCreatePersistedKey(*(_QWORD *)(v19 + 16), (NCRYPT_KEY_HANDLE *)(v19 + 24), a2, 0, 0, 0);
    v13 = PersistedKey;
    if ( PersistedKey < 0 )
    {
      v16 = 169;
LABEL_7:
      DebugTraceError(
        (unsigned int)PersistedKey,
        "status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsephemeral.c",
        v16);
      goto LABEL_28;
    }
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)&pbInput[2 * v17] );
    if ( a3 == 196618 && pbInput && v17 )
    {
      PersistedKey = NCryptSetProperty(*v14, L"ECCCurveName", pbInput, 2 * v17 + 2, 0);
      v13 = PersistedKey;
      if ( PersistedKey < 0 )
      {
        v16 = 186;
        goto LABEL_7;
      }
    }
    else
    {
      PersistedKey = NCryptSetProperty(*v14, L"Length", &a6, 4u, 0);
      v13 = PersistedKey;
      if ( PersistedKey < 0 )
      {
        v16 = 200;
        goto LABEL_7;
      }
      if ( a3 == 196610 )
      {
        if ( a7 )
        {
          if ( cbInput )
          {
            PersistedKey = NCryptSetProperty(*v14, L"DHParameters", a7, cbInput, 0);
            v13 = PersistedKey;
            if ( PersistedKey < 0 )
            {
              v16 = 215;
              goto LABEL_7;
            }
          }
        }
      }
    }
    PersistedKey = NCryptFinalizeKey(*v14, 0);
    v13 = PersistedKey;
    if ( PersistedKey >= 0 )
    {
      *a1 = v11;
      return v13;
    }
    v16 = 225;
    goto LABEL_7;
  }
  v13 = -2146893785;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return v13;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    (_DWORD)a2,
    a3,
    (unsigned int)"status",
    39,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsephemeral.c",
    145);
LABEL_28:
  if ( v11 )
    SslpFreeEphemeralKey(v11);
  return v13;
}

```

## disassembly

```asm
0x180013950  mov     r11, rsp
0x180013953  mov     [r11+10h], rbx
0x180013957  mov     [r11+18h], rbp
0x18001395b  push    rsi
0x18001395c  push    rdi
0x18001395d  push    r12
0x18001395f  push    r14
0x180013961  push    r15
0x180013963  sub     rsp, 40h
0x180013967  xor     r12d, r12d
0x18001396a  movzx   eax, r9w
0x18001396e  mov     [r11+8], r12
0x180013972  mov     esi, r8d
0x180013975  mov     rbp, rdx
0x180013978  mov     r15, rcx
0x18001397b  mov     edi, r12d
0x18001397e  test    rcx, rcx
0x180013981  jz      loc_180013B07
0x180013987  test    rdx, rdx
0x18001398a  jz      loc_180013B07
0x180013990  lea     r9, [r11+8]
0x180013994  movzx   edx, ax
0x180013997  call    SslpCreateBaseEphemeralKeyStruct
0x18001399c  mov     ebx, eax
0x18001399e  test    eax, eax
0x1800139a0  jns     short loc_1800139C7
0x1800139a2  mov     r9d, 9Ch
0x1800139a8  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800139af  lea     rdx, aStatus_0; "status"
0x1800139b6  mov     ecx, eax
0x1800139b8  call    DebugTraceError
0x1800139bd  mov     rdi, [rsp+68h+arg_0]
0x1800139c2  jmp     loc_180013B51
0x1800139c7  mov     rdi, [rsp+68h+arg_0]
0x1800139cc  xor     r9d, r9d; pszKeyName
0x1800139cf  mov     [rsp+68h+dwFlags], r12d; dwFlags
0x1800139d4  mov     r8, rbp; pszAlgId
0x1800139d7  mov     [rsp+68h+dwLegacyKeySpec], r12d; dwLegacyKeySpec
0x1800139dc  mov     rcx, [rdi+10h]; hProvider
0x1800139e0  lea     r14, [rdi+18h]
0x1800139e4  mov     rdx, r14; phKey
0x1800139e7  call    cs:__imp_NCryptCreatePersistedKey
0x1800139ed  mov     ebx, eax
0x1800139ef  test    eax, eax
0x1800139f1  jns     short loc_180013A13
0x1800139f3  mov     r9d, 0A9h
0x1800139f9  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013a00  mov     ecx, eax
0x180013a02  lea     rdx, aStatus_0; "status"
0x180013a09  call    DebugTraceError
0x180013a0e  jmp     loc_180013B51
0x180013a13  mov     r8, [rsp+68h+pbInput]; pbInput
0x180013a1b  or      r9, 0FFFFFFFFFFFFFFFFh
0x180013a1f  inc     r9
0x180013a22  cmp     [r8+r9*2], r12w
0x180013a27  jnz     short loc_180013A1F
0x180013a29  cmp     esi, 3000Ah
0x180013a2f  jnz     short loc_180013A6A
0x180013a31  test    r8, r8
0x180013a34  jz      short loc_180013A6A
0x180013a36  test    r9, r9
0x180013a39  jz      short loc_180013A6A
0x180013a3b  mov     rcx, [r14]; hObject
0x180013a3e  lea     r9d, ds:2[r9*2]; cbInput
0x180013a46  lea     rdx, aEcccurvename; "ECCCurveName"
0x180013a4d  mov     [rsp+68h+dwLegacyKeySpec], r12d; dwFlags
0x180013a52  call    cs:__imp_NCryptSetProperty
0x180013a58  mov     ebx, eax
0x180013a5a  test    eax, eax
0x180013a5c  jns     loc_180013AE6
0x180013a62  mov     r9d, 0BAh
0x180013a68  jmp     short loc_1800139F9
0x180013a6a  mov     rcx, [r14]; hObject
0x180013a6d  lea     r8, [rsp+68h+arg_28]; pbInput
0x180013a75  mov     r9d, 4; cbInput
0x180013a7b  mov     [rsp+68h+dwLegacyKeySpec], r12d; dwFlags
0x180013a80  lea     rdx, aLength; "Length"
0x180013a87  call    cs:__imp_NCryptSetProperty
0x180013a8d  mov     ebx, eax
0x180013a8f  test    eax, eax
0x180013a91  jns     short loc_180013A9E
0x180013a93  mov     r9d, 0C8h
0x180013a99  jmp     loc_1800139F9
0x180013a9e  cmp     esi, 30002h
0x180013aa4  jnz     short loc_180013AE6
0x180013aa6  mov     r8, [rsp+68h+arg_30]; pbInput
0x180013aae  test    r8, r8
0x180013ab1  jz      short loc_180013AE6
0x180013ab3  mov     r9d, [rsp+68h+cbInput]; cbInput
0x180013abb  test    r9d, r9d
0x180013abe  jz      short loc_180013AE6
0x180013ac0  mov     rcx, [r14]; hObject
0x180013ac3  lea     rdx, aDhparameters; "DHParameters"
0x180013aca  mov     [rsp+68h+dwLegacyKeySpec], r12d; dwFlags
0x180013acf  call    cs:__imp_NCryptSetProperty
0x180013ad5  mov     ebx, eax
0x180013ad7  test    eax, eax
0x180013ad9  jns     short loc_180013AE6
0x180013adb  mov     r9d, 0D7h
0x180013ae1  jmp     loc_1800139F9
0x180013ae6  mov     rcx, [r14]; hKey
0x180013ae9  xor     edx, edx; dwFlags
0x180013aeb  call    cs:__imp_NCryptFinalizeKey
0x180013af1  mov     ebx, eax
0x180013af3  test    eax, eax
0x180013af5  jns     short loc_180013B02
0x180013af7  mov     r9d, 0E1h
0x180013afd  jmp     loc_1800139F9
0x180013b02  mov     [r15], rdi
0x180013b05  jmp     short loc_180013B5E
0x180013b07  mov     ebx, 80090027h
0x180013b0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b13  lea     rax, WPP_GLOBAL_Control
0x180013b1a  cmp     rcx, rax
0x180013b1d  jz      short loc_180013B5E
0x180013b1f  test    byte ptr [rcx+1Ch], 1
0x180013b23  jz      short loc_180013B5E
0x180013b25  mov     rcx, [rcx+10h]
0x180013b29  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013b30  mov     [rsp+68h+var_38], 91h
0x180013b38  lea     r9, aStatus_0; "status"
0x180013b3f  mov     qword ptr [rsp+68h+dwFlags], rax
0x180013b44  mov     [rsp+68h+dwLegacyKeySpec], 80090027h
0x180013b4c  call    WPP_SF_sDsd
0x180013b51  test    rdi, rdi
0x180013b54  jz      short loc_180013B5E
0x180013b56  mov     rcx, rdi
0x180013b59  call    SslpFreeEphemeralKey
0x180013b5e  lea     r11, [rsp+68h+var_28]
0x180013b63  mov     eax, ebx
0x180013b65  mov     rbx, [r11+38h]
0x180013b69  mov     rbp, [r11+40h]
0x180013b6d  mov     rsp, r11
0x180013b70  pop     r15
0x180013b72  pop     r14
0x180013b74  pop     r12
0x180013b76  pop     rdi
0x180013b77  pop     rsi
0x180013b78  retn
```
