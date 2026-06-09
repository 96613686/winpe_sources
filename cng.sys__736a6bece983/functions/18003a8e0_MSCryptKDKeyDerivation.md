# MSCryptKDKeyDerivation

- ea: `0x18003a8e0`
- end: `0x18003aa16`
- name: `MSCryptKDKeyDerivation`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180074b50`

## callees

- `0x180004820`
- `0x18000743c`
- `0x1800082b0`
- `0x18003a8e0`
- `0x18003aa20`
- `0x18007dfb4`
- `0x18007e2a4`
- `0x18007e320`
- `0x18007e820`
- `0x18007e8b0`

## string_xrefs

- `0x18003a98b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18003a9b7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDKeyDerivation(
        __int64 a1,
        __int64 a2,
        void *a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int a6)
{
  int v9; // edx
  unsigned int v10; // ebx
  int v11; // r8d
  int v12; // eax
  __int64 v14[7]; // [rsp+40h] [rbp-38h] BYREF

  v14[0] = 0;
  if ( (a6 & 0xFFFFFFEF) != 0 )
  {
    v10 = -1073741811;
    DebugTraceError(
      3221225485LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      1640);
    return v10;
  }
  v10 = ValidateKeyDerivationKey(a1, v14);
  if ( (v10 & 0x80000000) == 0 )
  {
    switch ( *(_DWORD *)(v14[0] + 8) )
    {
      case 0x60001:
        v12 = DeriveKeySP800108_CTR_HMAC(v14[0], a2, (__int64)a3, a4, a5, a6);
        break;
      case 0x60002:
        v12 = DeriveKeySP80056A_CONCAT(v14[0], a2, (_DWORD)a3, a4, (__int64)a5, a6);
        break;
      case 0x60003:
        v12 = DeriveKeyPBKDF2(v14[0], a2, a3, a4, a5, a6);
        break;
      case 0x60004:
        v12 = DeriveKeyCAPI_KDF(v14[0], a2, (__int64)a3, a4, a5, a6);
        break;
      case 0x60005:
      case 0x60006:
        v12 = DeriveKeyTLS_KDF(v14[0], a2, (_DWORD)a3, a4, (__int64)a5, a6);
        break;
      case 0x60007:
        v12 = DeriveKeyHKDF(v14[0], a2, (_DWORD)a3, a4, (__int64)a5, a6);
        break;
      default:
        v10 = -1073741637;
LABEL_8:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v9,
            v11,
            (unsigned int)"Status",
            v10,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
            193);
        return v10;
    }
    v10 = v12;
    if ( v12 >= 0 )
      return 0;
    goto LABEL_8;
  }
  return v10;
}

```

## disassembly

```asm
0x18003a8e0  push    rbx
0x18003a8e2  push    rbp
0x18003a8e3  push    rsi
0x18003a8e4  push    rdi
0x18003a8e5  push    r14
0x18003a8e7  sub     rsp, 50h
0x18003a8eb  mov     edi, [rsp+78h+arg_28]
0x18003a8f2  mov     esi, r9d
0x18003a8f5  mov     [rsp+78h+var_38], 0
0x18003a8fe  mov     rbp, r8
0x18003a901  mov     r14, rdx
0x18003a904  test    edi, 0FFFFFFEFh
0x18003a90a  jnz     loc_18003A9B1
0x18003a910  lea     rdx, [rsp+78h+var_38]
0x18003a915  call    ValidateKeyDerivationKey
0x18003a91a  mov     ebx, eax
0x18003a91c  test    eax, eax
0x18003a91e  js      short loc_18003A95F
0x18003a920  mov     r10, [rsp+78h+var_38]
0x18003a925  mov     ecx, [r10+8]
0x18003a929  sub     ecx, 60001h
0x18003a92f  jnz     loc_18003A9D6
0x18003a935  mov     rax, [rsp+78h+arg_20]
0x18003a93d  mov     r9d, esi
0x18003a940  mov     dword ptr [rsp+78h+var_50], edi
0x18003a944  mov     r8, rbp
0x18003a947  mov     rdx, r14
0x18003a94a  mov     [rsp+78h+var_58], rax
0x18003a94f  mov     rcx, r10
0x18003a952  call    DeriveKeySP800108_CTR_HMAC
0x18003a957  mov     ebx, eax
0x18003a959  test    eax, eax
0x18003a95b  js      short loc_18003A96D
0x18003a95d  xor     ebx, ebx
0x18003a95f  mov     eax, ebx
0x18003a961  add     rsp, 50h
0x18003a965  pop     r14
0x18003a967  pop     rdi
0x18003a968  pop     rsi
0x18003a969  pop     rbp
0x18003a96a  pop     rbx
0x18003a96b  retn
0x18003a96d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a974  lea     rax, WPP_GLOBAL_Control
0x18003a97b  cmp     rcx, rax
0x18003a97e  jz      short loc_18003A95F
0x18003a980  mov     eax, [rcx+2Ch]
0x18003a983  test    al, 1
0x18003a985  jz      short loc_18003A95F
0x18003a987  mov     rcx, [rcx+18h]
0x18003a98b  lea     rax, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003a992  mov     [rsp+78h+var_48], 6C1h
0x18003a99a  lea     r9, aStatus; "Status"
0x18003a9a1  mov     [rsp+78h+var_50], rax
0x18003a9a6  mov     dword ptr [rsp+78h+var_58], ebx
0x18003a9aa  call    WPP_SF_sDsd
0x18003a9af  jmp     short loc_18003A95F
0x18003a9b1  mov     r9d, 668h
0x18003a9b7  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003a9be  lea     rdx, aStatus; "Status"
0x18003a9c5  mov     ecx, 0C000000Dh
0x18003a9ca  mov     ebx, 0C000000Dh
0x18003a9cf  call    DebugTraceError
0x18003a9d4  jmp     short loc_18003A95F
0x18003a9d6  sub     ecx, 1
0x18003a9d9  jz      loc_1800A30DC
0x18003a9df  sub     ecx, 1
0x18003a9e2  jz      loc_1800A30B4
0x18003a9e8  sub     ecx, 1
0x18003a9eb  jz      loc_1800A308C
0x18003a9f1  sub     ecx, 1
0x18003a9f4  jz      loc_1800A3064
0x18003a9fa  sub     ecx, 1
0x18003a9fd  jz      loc_1800A3064
0x18003aa03  cmp     ecx, 1
0x18003aa06  jz      loc_1800A303C
0x18003aa0c  mov     ebx, 0C00000BBh
0x18003aa11  jmp     loc_18003A96D
0x1800a303c  mov     rax, [rsp+78h+arg_20]
0x1800a3044  mov     r9d, esi
0x1800a3047  mov     dword ptr [rsp+78h+var_50], edi
0x1800a304b  mov     r8, rbp
0x1800a304e  mov     rdx, r14
0x1800a3051  mov     [rsp+78h+var_58], rax
0x1800a3056  mov     rcx, r10
0x1800a3059  call    DeriveKeyHKDF
0x1800a305e  nop
0x1800a305f  jmp     loc_18003A957
0x1800a3064  mov     rax, [rsp+78h+arg_20]
0x1800a306c  mov     r9d, esi
0x1800a306f  mov     dword ptr [rsp+78h+var_50], edi
0x1800a3073  mov     r8, rbp
0x1800a3076  mov     rdx, r14
0x1800a3079  mov     [rsp+78h+var_58], rax
0x1800a307e  mov     rcx, r10
0x1800a3081  call    DeriveKeyTLS_KDF
0x1800a3086  nop
0x1800a3087  jmp     loc_18003A957
0x1800a308c  mov     rax, [rsp+78h+arg_20]
0x1800a3094  mov     r9d, esi
0x1800a3097  mov     dword ptr [rsp+78h+var_50], edi
0x1800a309b  mov     r8, rbp
0x1800a309e  mov     rdx, r14
0x1800a30a1  mov     [rsp+78h+var_58], rax
0x1800a30a6  mov     rcx, r10
0x1800a30a9  call    DeriveKeyCAPI_KDF
0x1800a30ae  nop
0x1800a30af  jmp     loc_18003A957
0x1800a30b4  mov     rax, [rsp+78h+arg_20]
0x1800a30bc  mov     r9d, esi
0x1800a30bf  mov     dword ptr [rsp+78h+var_50], edi
0x1800a30c3  mov     r8, rbp
0x1800a30c6  mov     rdx, r14
0x1800a30c9  mov     [rsp+78h+var_58], rax
0x1800a30ce  mov     rcx, r10
0x1800a30d1  call    DeriveKeyPBKDF2
0x1800a30d6  nop
0x1800a30d7  jmp     loc_18003A957
0x1800a30dc  mov     rax, [rsp+78h+arg_20]
0x1800a30e4  mov     r9d, esi
0x1800a30e7  mov     dword ptr [rsp+78h+var_50], edi
0x1800a30eb  mov     r8, rbp
0x1800a30ee  mov     rdx, r14
0x1800a30f1  mov     [rsp+78h+var_58], rax
0x1800a30f6  mov     rcx, r10
0x1800a30f9  call    DeriveKeySP80056A_CONCAT
0x1800a30fe  nop
0x1800a30ff  jmp     loc_18003A957
```
