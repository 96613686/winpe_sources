# SslpImportKemKeyWithNCrypt

- ea: `0x180022420`
- end: `0x1800225ff`
- name: `SslpImportKemKeyWithNCrypt`
- size: `479`
- prototype: `__int64 __fastcall(PBYTE pbData, DWORD cbData, LPCWSTR pszBlobType, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800234b0`

## callees

- `0x18000b654`
- `0x1800185e0`
- `0x180021a74`
- `0x180022164`
- `0x180022420`
- `0x180024ef0`
- `0x180024fb0`

## import_xrefs

- `ncrypt!NCryptImportKey` at `0x18002257b`
- `ncrypt!NCryptImportKey` at `0x18002257b`

## string_xrefs

- `0x1800224a4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`
- `0x1800225ca`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`

## pseudocode

```c
__int64 __fastcall SslpImportKemKeyWithNCrypt(PBYTE pbData, DWORD cbData, LPCWSTR pszBlobType, _QWORD *a4)
{
  __int64 v4; // rdi
  unsigned __int64 v5; // rsi
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rcx
  size_t v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r9
  SECURITY_STATUS v18; // eax
  __int64 v20; // [rsp+40h] [rbp-68h] BYREF
  wchar_t String1[12]; // [rsp+48h] [rbp-60h] BYREF

  v4 = 0;
  v5 = cbData;
  v20 = 0;
  if ( pbData && cbData && pszBlobType && a4 )
  {
    if ( !wcscmp(pszBlobType, L"MLKEMPUBLICBLOB") )
    {
      if ( (unsigned int)v5 < 0xC )
      {
        v9 = 430;
LABEL_8:
        v10 = -2146893819;
        v11 = 2148073477LL;
LABEL_9:
        DebugTraceError(v11, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c", v9);
        return v10;
      }
      v12 = *((unsigned int *)pbData + 1);
      if ( v5 < *((unsigned int *)pbData + 2) + v12 + 12 )
      {
        v9 = 438;
        goto LABEL_8;
      }
      memmove(String1, pbData + 12, v12);
      if ( !wcscmp(String1, L"512") )
      {
        v14 = 512;
        goto LABEL_18;
      }
      if ( !wcscmp(String1, L"768") )
      {
        v14 = 513;
        goto LABEL_18;
      }
      if ( !wcscmp(String1, L"1024") )
      {
        v14 = 514;
LABEL_18:
        v15 = SslpCreateBaseKemKeyStruct(v13, v14, 458753, &v20);
        v4 = v20;
        v10 = v15;
        if ( v15 >= 0 )
        {
          v18 = NCryptImportKey(
                  *(_QWORD *)(v20 + 16),
                  0,
                  pszBlobType,
                  0,
                  (NCRYPT_KEY_HANDLE *)(v20 + 24),
                  pbData,
                  v5,
                  0);
          v10 = v18;
          if ( v18 >= 0 )
          {
            *a4 = v4;
            return v10;
          }
          v16 = (unsigned int)v18;
          v17 = 494;
        }
        else
        {
          v16 = (unsigned int)v15;
          v17 = 479;
        }
        goto LABEL_27;
      }
      v9 = 459;
    }
    else
    {
      v9 = 468;
    }
    v10 = -2146893783;
    v11 = 2148073513LL;
    goto LABEL_9;
  }
  v10 = -2146893785;
  v16 = 2148073511LL;
  v17 = 419;
LABEL_27:
  DebugTraceError(v16, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c", v17);
  if ( v4 )
    SslpFreeKemKey(v4);
  return v10;
}

```

## disassembly

```asm
0x180022420  push    rbx
0x180022422  push    rbp
0x180022423  push    rsi
0x180022424  push    rdi
0x180022425  push    r14
0x180022427  push    r15
0x180022429  sub     rsp, 78h
0x18002242d  mov     rax, cs:__security_cookie
0x180022434  xor     rax, rsp
0x180022437  mov     [rsp+0A8h+var_48], rax
0x18002243c  xor     edi, edi
0x18002243e  mov     esi, edx
0x180022440  mov     [rsp+0A8h+var_68], rdi
0x180022445  mov     r15, r9
0x180022448  mov     r14, r8
0x18002244b  mov     rbp, rcx
0x18002244e  test    rcx, rcx
0x180022451  jz      loc_1800225B3
0x180022457  test    edx, edx
0x180022459  jz      loc_1800225B3
0x18002245f  test    r8, r8
0x180022462  jz      loc_1800225B3
0x180022468  test    r9, r9
0x18002246b  jz      loc_1800225B3
0x180022471  lea     rdx, aMlkempublicblo; "MLKEMPUBLICBLOB"
0x180022478  mov     rcx, r8; String1
0x18002247b  call    wcscmp
0x180022480  test    eax, eax
0x180022482  jnz     loc_1800225AB
0x180022488  cmp     esi, 0Ch
0x18002248b  jnb     short loc_1800224B5
0x18002248d  mov     r9d, 1AEh
0x180022493  mov     ebx, 80090005h
0x180022498  mov     ecx, 80090005h
0x18002249d  lea     rdx, aStatus_0; "status"
0x1800224a4  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800224ab  call    DebugTraceError
0x1800224b0  jmp     loc_1800225E3
0x1800224b5  mov     r8d, [rbp+4]; Size
0x1800224b9  mov     eax, [rbp+8]
0x1800224bc  lea     rcx, [r8+0Ch]
0x1800224c0  add     rcx, rax
0x1800224c3  cmp     rsi, rcx
0x1800224c6  jnb     short loc_1800224D0
0x1800224c8  mov     r9d, 1B6h
0x1800224ce  jmp     short loc_180022493
0x1800224d0  lea     rdx, [rbp+0Ch]; Src
0x1800224d4  lea     rcx, [rsp+0A8h+String1]; void *
0x1800224d9  call    memmove
0x1800224de  lea     rdx, a512; "512"
0x1800224e5  lea     rcx, [rsp+0A8h+String1]; String1
0x1800224ea  call    wcscmp
0x1800224ef  test    eax, eax
0x1800224f1  jnz     short loc_1800224FA
0x1800224f3  mov     edx, 200h
0x1800224f8  jmp     short loc_180022530
0x1800224fa  lea     rdx, a768; "768"
0x180022501  lea     rcx, [rsp+0A8h+String1]; String1
0x180022506  call    wcscmp
0x18002250b  test    eax, eax
0x18002250d  jnz     short loc_180022516
0x18002250f  mov     edx, 201h
0x180022514  jmp     short loc_180022530
0x180022516  lea     rdx, a1024; "1024"
0x18002251d  lea     rcx, [rsp+0A8h+String1]; String1
0x180022522  call    wcscmp
0x180022527  test    eax, eax
0x180022529  jnz     short loc_180022596
0x18002252b  mov     edx, 202h
0x180022530  lea     r9, [rsp+0A8h+var_68]
0x180022535  mov     r8d, 70001h
0x18002253b  call    SslpCreateBaseKemKeyStruct
0x180022540  mov     rdi, [rsp+0A8h+var_68]
0x180022545  mov     ebx, eax
0x180022547  test    eax, eax
0x180022549  jns     short loc_180022555
0x18002254b  mov     ecx, eax
0x18002254d  mov     r9d, 1DFh
0x180022553  jmp     short loc_1800225C3
0x180022555  mov     rcx, [rdi+10h]; hProvider
0x180022559  lea     rax, [rdi+18h]
0x18002255d  mov     [rsp+0A8h+dwFlags], 0; dwFlags
0x180022565  xor     r9d, r9d; pParameterList
0x180022568  mov     [rsp+0A8h+cbData], esi; cbData
0x18002256c  mov     r8, r14; pszBlobType
0x18002256f  mov     [rsp+0A8h+pbData], rbp; pbData
0x180022574  xor     edx, edx; hImportKey
0x180022576  mov     [rsp+0A8h+phKey], rax; phKey
0x18002257b  call    cs:__imp_NCryptImportKey
0x180022581  mov     ebx, eax
0x180022583  test    eax, eax
0x180022585  jns     short loc_180022591
0x180022587  mov     ecx, eax
0x180022589  mov     r9d, 1EEh
0x18002258f  jmp     short loc_1800225C3
0x180022591  mov     [r15], rdi
0x180022594  jmp     short loc_1800225E3
0x180022596  mov     r9d, 1CBh
0x18002259c  mov     ebx, 80090029h
0x1800225a1  mov     ecx, 80090029h
0x1800225a6  jmp     loc_18002249D
0x1800225ab  mov     r9d, 1D4h
0x1800225b1  jmp     short loc_18002259C
0x1800225b3  mov     ebx, 80090027h
0x1800225b8  mov     ecx, 80090027h
0x1800225bd  mov     r9d, 1A3h
0x1800225c3  lea     rdx, aStatus_0; "status"
0x1800225ca  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800225d1  call    DebugTraceError
0x1800225d6  test    rdi, rdi
0x1800225d9  jz      short loc_1800225E3
0x1800225db  mov     rcx, rdi
0x1800225de  call    SslpFreeKemKey
0x1800225e3  mov     eax, ebx
0x1800225e5  mov     rcx, [rsp+0A8h+var_48]
0x1800225ea  xor     rcx, rsp; StackCookie
0x1800225ed  call    __security_check_cookie
0x1800225f2  add     rsp, 78h
0x1800225f6  pop     r15
0x1800225f8  pop     r14
0x1800225fa  pop     rdi
0x1800225fb  pop     rsi
0x1800225fc  pop     rbp
0x1800225fd  pop     rbx
0x1800225fe  retn
```
