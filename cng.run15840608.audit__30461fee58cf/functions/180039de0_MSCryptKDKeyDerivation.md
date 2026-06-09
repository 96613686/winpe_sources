# MSCryptKDKeyDerivation

- ea: `0x180039de0`
- end: `0x180039f16`
- name: `MSCryptKDKeyDerivation`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180074150`

## callees

- `0x180004820`
- `0x18000743c`
- `0x1800082b0`
- `0x180039de0`
- `0x180039f20`
- `0x18007cfc4`
- `0x18007d2b4`
- `0x18007d330`
- `0x18007d830`
- `0x18007d8c0`

## string_xrefs

- `0x180039e8b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180039eb7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

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
        v12 = DeriveKeySP80056A_CONCAT(v14[0], a2, (__int64)a3, a4, (__int64)a5, a6);
        break;
      case 0x60003:
        v12 = DeriveKeyPBKDF2(v14[0], a2, a3, a4, a5, a6);
        break;
      case 0x60004:
        v12 = DeriveKeyCAPI_KDF(v14[0], a2, (__int64)a3, a4, a5, a6);
        break;
      case 0x60005:
      case 0x60006:
        v12 = DeriveKeyTLS_KDF(v14[0], a2, (__int64)a3, a4, a5, a6);
        break;
      case 0x60007:
        v12 = DeriveKeyHKDF(v14[0], a2, (__int64)a3, a4, a5, a6);
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
0x180039de0  push    rbx
0x180039de2  push    rbp
0x180039de3  push    rsi
0x180039de4  push    rdi
0x180039de5  push    r14
0x180039de7  sub     rsp, 50h
0x180039deb  mov     edi, [rsp+78h+arg_28]
0x180039df2  mov     esi, r9d
0x180039df5  mov     [rsp+78h+var_38], 0
0x180039dfe  mov     rbp, r8
0x180039e01  mov     r14, rdx
0x180039e04  test    edi, 0FFFFFFEFh
0x180039e0a  jnz     loc_180039EB1
0x180039e10  lea     rdx, [rsp+78h+var_38]
0x180039e15  call    ValidateKeyDerivationKey
0x180039e1a  mov     ebx, eax
0x180039e1c  test    eax, eax
0x180039e1e  js      short loc_180039E5F
0x180039e20  mov     r10, [rsp+78h+var_38]
0x180039e25  mov     ecx, [r10+8]
0x180039e29  sub     ecx, 60001h
0x180039e2f  jnz     loc_180039ED6
0x180039e35  mov     rax, [rsp+78h+arg_20]
0x180039e3d  mov     r9d, esi
0x180039e40  mov     dword ptr [rsp+78h+var_50], edi
0x180039e44  mov     r8, rbp
0x180039e47  mov     rdx, r14
0x180039e4a  mov     [rsp+78h+var_58], rax
0x180039e4f  mov     rcx, r10
0x180039e52  call    DeriveKeySP800108_CTR_HMAC
0x180039e57  mov     ebx, eax
0x180039e59  test    eax, eax
0x180039e5b  js      short loc_180039E6D
0x180039e5d  xor     ebx, ebx
0x180039e5f  mov     eax, ebx
0x180039e61  add     rsp, 50h
0x180039e65  pop     r14
0x180039e67  pop     rdi
0x180039e68  pop     rsi
0x180039e69  pop     rbp
0x180039e6a  pop     rbx
0x180039e6b  retn
0x180039e6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e74  lea     rax, WPP_GLOBAL_Control
0x180039e7b  cmp     rcx, rax
0x180039e7e  jz      short loc_180039E5F
0x180039e80  mov     eax, [rcx+2Ch]
0x180039e83  test    al, 1
0x180039e85  jz      short loc_180039E5F
0x180039e87  mov     rcx, [rcx+18h]
0x180039e8b  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039e92  mov     [rsp+78h+var_48], 6C1h
0x180039e9a  lea     r9, aStatus; "Status"
0x180039ea1  mov     [rsp+78h+var_50], rax
0x180039ea6  mov     dword ptr [rsp+78h+var_58], ebx
0x180039eaa  call    WPP_SF_sDsd
0x180039eaf  jmp     short loc_180039E5F
0x180039eb1  mov     r9d, 668h
0x180039eb7  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039ebe  lea     rdx, aStatus; "Status"
0x180039ec5  mov     ecx, 0C000000Dh
0x180039eca  mov     ebx, 0C000000Dh
0x180039ecf  call    DebugTraceError
0x180039ed4  jmp     short loc_180039E5F
0x180039ed6  sub     ecx, 1
0x180039ed9  jz      loc_1800A12AC
0x180039edf  sub     ecx, 1
0x180039ee2  jz      loc_1800A1284
0x180039ee8  sub     ecx, 1
0x180039eeb  jz      loc_1800A125C
0x180039ef1  sub     ecx, 1
0x180039ef4  jz      loc_1800A1234
0x180039efa  sub     ecx, 1
0x180039efd  jz      loc_1800A1234
0x180039f03  cmp     ecx, 1
0x180039f06  jz      loc_1800A120C
0x180039f0c  mov     ebx, 0C00000BBh
0x180039f11  jmp     loc_180039E6D
0x1800a120c  mov     rax, [rsp+78h+arg_20]
0x1800a1214  mov     r9d, esi
0x1800a1217  mov     dword ptr [rsp+78h+var_50], edi
0x1800a121b  mov     r8, rbp
0x1800a121e  mov     rdx, r14
0x1800a1221  mov     [rsp+78h+var_58], rax
0x1800a1226  mov     rcx, r10
0x1800a1229  call    DeriveKeyHKDF
0x1800a122e  nop
0x1800a122f  jmp     loc_180039E57
0x1800a1234  mov     rax, [rsp+78h+arg_20]
0x1800a123c  mov     r9d, esi
0x1800a123f  mov     dword ptr [rsp+78h+var_50], edi
0x1800a1243  mov     r8, rbp
0x1800a1246  mov     rdx, r14
0x1800a1249  mov     [rsp+78h+var_58], rax
0x1800a124e  mov     rcx, r10
0x1800a1251  call    DeriveKeyTLS_KDF
0x1800a1256  nop
0x1800a1257  jmp     loc_180039E57
0x1800a125c  mov     rax, [rsp+78h+arg_20]
0x1800a1264  mov     r9d, esi
0x1800a1267  mov     dword ptr [rsp+78h+var_50], edi
0x1800a126b  mov     r8, rbp
0x1800a126e  mov     rdx, r14
0x1800a1271  mov     [rsp+78h+var_58], rax
0x1800a1276  mov     rcx, r10
0x1800a1279  call    DeriveKeyCAPI_KDF
0x1800a127e  nop
0x1800a127f  jmp     loc_180039E57
0x1800a1284  mov     rax, [rsp+78h+arg_20]
0x1800a128c  mov     r9d, esi
0x1800a128f  mov     dword ptr [rsp+78h+var_50], edi
0x1800a1293  mov     r8, rbp
0x1800a1296  mov     rdx, r14
0x1800a1299  mov     [rsp+78h+var_58], rax
0x1800a129e  mov     rcx, r10
0x1800a12a1  call    DeriveKeyPBKDF2
0x1800a12a6  nop
0x1800a12a7  jmp     loc_180039E57
0x1800a12ac  mov     rax, [rsp+78h+arg_20]
0x1800a12b4  mov     r9d, esi
0x1800a12b7  mov     dword ptr [rsp+78h+var_50], edi
0x1800a12bb  mov     r8, rbp
0x1800a12be  mov     rdx, r14
0x1800a12c1  mov     [rsp+78h+var_58], rax
0x1800a12c6  mov     rcx, r10
0x1800a12c9  call    DeriveKeySP80056A_CONCAT
0x1800a12ce  nop
0x1800a12cf  jmp     loc_180039E57
```
