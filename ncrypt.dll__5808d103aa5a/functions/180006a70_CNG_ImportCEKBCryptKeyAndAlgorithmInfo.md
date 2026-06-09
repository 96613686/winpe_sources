# CNG_ImportCEKBCryptKeyAndAlgorithmInfo

- ea: `0x180006a70`
- end: `0x180006bde`
- name: `CNG_ImportCEKBCryptKeyAndAlgorithmInfo`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180007098`

## callees

- `0x180004c00`
- `0x180005fa0`
- `0x180006a70`
- `0x180006be4`
- `0x18000d02c`
- `0x18000e120`
- `0x18001f175`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x180006af7`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180006af7`

## string_xrefs

- `0x180006b52`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x180006bc4`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`

## pseudocode

```c
__int64 __fastcall CNG_ImportCEKBCryptKeyAndAlgorithmInfo(__int64 a1, UCHAR *a2, ULONG a3, __int64 a4, __int64 a5)
{
  int v9; // edx
  unsigned int BCryptOidInfo; // ebx
  int v11; // edx
  int v12; // edx
  unsigned int v13; // eax

  memset_0((void *)(a5 + 8), 0, 0x70u);
  *(_QWORD *)a5 = a4;
  BCryptOidInfo = CNG_FindBCryptOidInfo(*(const void **)(a1 + 8), *(_DWORD *)a1, 1u, (_QWORD *)(a5 + 24));
  if ( BCryptOidInfo )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
        (unsigned int)"Status",
        BCryptOidInfo,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
        99);
  }
  else
  {
    BCryptOidInfo = CNG_GetBCryptHandle(*(char **)(*(_QWORD *)(a5 + 24) + 8LL), (_QWORD *)(a5 + 8));
    if ( BCryptOidInfo )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
          (unsigned int)"Status",
          BCryptOidInfo,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
          109);
    }
    else
    {
      BCryptOidInfo = BCryptGenerateSymmetricKey(
                        *(BCRYPT_ALG_HANDLE *)(a5 + 8),
                        (BCRYPT_KEY_HANDLE *)(a5 + 16),
                        0,
                        0,
                        a2,
                        a3,
                        0);
      if ( BCryptOidInfo )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
            (unsigned int)"Status",
            BCryptOidInfo,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
            124);
      }
      else
      {
        v13 = CNG_SetKeyPropertiesFromAlgInfo(a1, (__int64 *)a5);
        BCryptOidInfo = v13;
        if ( v13 )
          DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c", 902);
      }
    }
  }
  return BCryptOidInfo;
}

```

## disassembly

```asm
0x180006a70  push    rbx
0x180006a72  push    rbp
0x180006a73  push    rsi
0x180006a74  push    rdi
0x180006a75  push    r12
0x180006a77  push    r14
0x180006a79  push    r15
0x180006a7b  sub     rsp, 40h
0x180006a7f  mov     rdi, [rsp+78h+arg_20]
0x180006a87  mov     r12, rdx
0x180006a8a  xor     edx, edx; Val
0x180006a8c  mov     ebp, r8d
0x180006a8f  mov     r14, rcx
0x180006a92  mov     rbx, r9
0x180006a95  lea     rcx, [rdi+8]; void *
0x180006a99  lea     r8d, [rdx+70h]; Size
0x180006a9d  call    memset_0
0x180006aa2  mov     [rdi], rbx
0x180006aa5  lea     r9, [rdi+18h]
0x180006aa9  mov     edx, [r14]
0x180006aac  mov     r8d, 1
0x180006ab2  mov     rcx, [r14+8]
0x180006ab6  call    CNG_FindBCryptOidInfo
0x180006abb  mov     ebx, eax
0x180006abd  test    eax, eax
0x180006abf  jnz     short loc_180006B2D
0x180006ac1  mov     rcx, [rdi+18h]
0x180006ac5  lea     rdx, [rdi+8]
0x180006ac9  mov     rcx, [rcx+8]
0x180006acd  call    CNG_GetBCryptHandle
0x180006ad2  mov     ebx, eax
0x180006ad4  test    eax, eax
0x180006ad6  jnz     loc_180006B70
0x180006adc  mov     rcx, [rdi+8]; hAlgorithm
0x180006ae0  lea     rdx, [rdi+10h]; phKey
0x180006ae4  mov     [rsp+78h+dwFlags], eax; dwFlags
0x180006ae8  xor     r9d, r9d; cbKeyObject
0x180006aeb  mov     [rsp+78h+cbSecret], ebp; cbSecret
0x180006aef  xor     r8d, r8d; pbKeyObject
0x180006af2  mov     [rsp+78h+pbSecret], r12; pbSecret
0x180006af7  call    cs:__imp_BCryptGenerateSymmetricKey
0x180006afd  mov     ebx, eax
0x180006aff  test    eax, eax
0x180006b01  jnz     loc_180006B93
0x180006b07  mov     rdx, rdi
0x180006b0a  mov     rcx, r14
0x180006b0d  call    CNG_SetKeyPropertiesFromAlgInfo
0x180006b12  mov     ebx, eax
0x180006b14  test    eax, eax
0x180006b16  jnz     loc_180006BBE
0x180006b1c  mov     eax, ebx
0x180006b1e  add     rsp, 40h
0x180006b22  pop     r15
0x180006b24  pop     r14
0x180006b26  pop     r12
0x180006b28  pop     rdi
0x180006b29  pop     rsi
0x180006b2a  pop     rbp
0x180006b2b  pop     rbx
0x180006b2c  retn
0x180006b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b34  lea     rax, WPP_GLOBAL_Control
0x180006b3b  cmp     rcx, rax
0x180006b3e  jz      short loc_180006B1C
0x180006b40  test    byte ptr [rcx+1Ch], 1
0x180006b44  jz      short loc_180006B1C
0x180006b46  mov     [rsp+78h+dwFlags], 363h
0x180006b4e  mov     rcx, [rcx+10h]
0x180006b52  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006b59  mov     qword ptr [rsp+78h+cbSecret], r8
0x180006b5e  lea     r9, aStatus; "Status"
0x180006b65  mov     dword ptr [rsp+78h+pbSecret], ebx
0x180006b69  call    WPP_SF_sDsd
0x180006b6e  jmp     short loc_180006B1C
0x180006b70  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b77  lea     rax, WPP_GLOBAL_Control
0x180006b7e  cmp     rcx, rax
0x180006b81  jz      short loc_180006B1C
0x180006b83  test    byte ptr [rcx+1Ch], 1
0x180006b87  jz      short loc_180006B1C
0x180006b89  mov     [rsp+78h+dwFlags], 36Dh
0x180006b91  jmp     short loc_180006B4E
0x180006b93  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b9a  lea     rax, WPP_GLOBAL_Control
0x180006ba1  cmp     rcx, rax
0x180006ba4  jz      loc_180006B1C
0x180006baa  test    byte ptr [rcx+1Ch], 1
0x180006bae  jz      loc_180006B1C
0x180006bb4  mov     [rsp+78h+dwFlags], 37Ch
0x180006bbc  jmp     short loc_180006B4E
0x180006bbe  mov     r9d, 386h
0x180006bc4  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006bcb  lea     rdx, aStatus; "Status"
0x180006bd2  mov     ecx, eax
0x180006bd4  call    DebugTraceError
0x180006bd9  jmp     loc_180006B1C
```
