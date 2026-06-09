# MSCryptKDKeyDerivation

- ea: `0x180043e70`
- end: `0x180043fa6`
- name: `MSCryptKDKeyDerivation`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18007e2f0`

## callees

- `0x18000e940`
- `0x18001155c`
- `0x1800123d0`
- `0x180043e70`
- `0x180043fb0`
- `0x1800871c4`
- `0x1800874b4`
- `0x180087530`
- `0x180087a30`
- `0x180087ac0`

## string_xrefs

- `0x180043f1b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180043f47`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

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
0x180043e70  push    rbx
0x180043e72  push    rbp
0x180043e73  push    rsi
0x180043e74  push    rdi
0x180043e75  push    r14
0x180043e77  sub     rsp, 50h
0x180043e7b  mov     edi, [rsp+78h+arg_28]
0x180043e82  mov     esi, r9d
0x180043e85  mov     [rsp+78h+var_38], 0
0x180043e8e  mov     rbp, r8
0x180043e91  mov     r14, rdx
0x180043e94  test    edi, 0FFFFFFEFh
0x180043e9a  jnz     loc_180043F41
0x180043ea0  lea     rdx, [rsp+78h+var_38]
0x180043ea5  call    ValidateKeyDerivationKey
0x180043eaa  mov     ebx, eax
0x180043eac  test    eax, eax
0x180043eae  js      short loc_180043EEF
0x180043eb0  mov     r10, [rsp+78h+var_38]
0x180043eb5  mov     ecx, [r10+8]
0x180043eb9  sub     ecx, 60001h
0x180043ebf  jnz     loc_180043F66
0x180043ec5  mov     rax, [rsp+78h+arg_20]
0x180043ecd  mov     r9d, esi
0x180043ed0  mov     dword ptr [rsp+78h+var_50], edi
0x180043ed4  mov     r8, rbp
0x180043ed7  mov     rdx, r14
0x180043eda  mov     [rsp+78h+var_58], rax
0x180043edf  mov     rcx, r10
0x180043ee2  call    DeriveKeySP800108_CTR_HMAC
0x180043ee7  mov     ebx, eax
0x180043ee9  test    eax, eax
0x180043eeb  js      short loc_180043EFD
0x180043eed  xor     ebx, ebx
0x180043eef  mov     eax, ebx
0x180043ef1  add     rsp, 50h
0x180043ef5  pop     r14
0x180043ef7  pop     rdi
0x180043ef8  pop     rsi
0x180043ef9  pop     rbp
0x180043efa  pop     rbx
0x180043efb  retn
0x180043efd  mov     rcx, cs:WPP_GLOBAL_Control
0x180043f04  lea     rax, WPP_GLOBAL_Control
0x180043f0b  cmp     rcx, rax
0x180043f0e  jz      short loc_180043EEF
0x180043f10  mov     eax, [rcx+2Ch]
0x180043f13  test    al, 1
0x180043f15  jz      short loc_180043EEF
0x180043f17  mov     rcx, [rcx+18h]
0x180043f1b  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180043f22  mov     [rsp+78h+var_48], 6C1h
0x180043f2a  lea     r9, aStatus; "Status"
0x180043f31  mov     [rsp+78h+var_50], rax
0x180043f36  mov     dword ptr [rsp+78h+var_58], ebx
0x180043f3a  call    WPP_SF_sDsd
0x180043f3f  jmp     short loc_180043EEF
0x180043f41  mov     r9d, 668h
0x180043f47  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180043f4e  lea     rdx, aStatus; "Status"
0x180043f55  mov     ecx, 0C000000Dh
0x180043f5a  mov     ebx, 0C000000Dh
0x180043f5f  call    DebugTraceError
0x180043f64  jmp     short loc_180043EEF
0x180043f66  sub     ecx, 1
0x180043f69  jz      loc_1800A804A
0x180043f6f  sub     ecx, 1
0x180043f72  jz      loc_1800A8022
0x180043f78  sub     ecx, 1
0x180043f7b  jz      loc_1800A7FFA
0x180043f81  sub     ecx, 1
0x180043f84  jz      loc_1800A7FD2
0x180043f8a  sub     ecx, 1
0x180043f8d  jz      loc_1800A7FD2
0x180043f93  cmp     ecx, 1
0x180043f96  jz      loc_1800A7FAA
0x180043f9c  mov     ebx, 0C00000BBh
0x180043fa1  jmp     loc_180043EFD
0x1800a7faa  mov     rax, [rsp+78h+arg_20]
0x1800a7fb2  mov     r9d, esi
0x1800a7fb5  mov     dword ptr [rsp+78h+var_50], edi
0x1800a7fb9  mov     r8, rbp
0x1800a7fbc  mov     rdx, r14
0x1800a7fbf  mov     [rsp+78h+var_58], rax
0x1800a7fc4  mov     rcx, r10
0x1800a7fc7  call    DeriveKeyHKDF
0x1800a7fcc  nop
0x1800a7fcd  jmp     loc_180043EE7
0x1800a7fd2  mov     rax, [rsp+78h+arg_20]
0x1800a7fda  mov     r9d, esi
0x1800a7fdd  mov     dword ptr [rsp+78h+var_50], edi
0x1800a7fe1  mov     r8, rbp
0x1800a7fe4  mov     rdx, r14
0x1800a7fe7  mov     [rsp+78h+var_58], rax
0x1800a7fec  mov     rcx, r10
0x1800a7fef  call    DeriveKeyTLS_KDF
0x1800a7ff4  nop
0x1800a7ff5  jmp     loc_180043EE7
0x1800a7ffa  mov     rax, [rsp+78h+arg_20]
0x1800a8002  mov     r9d, esi
0x1800a8005  mov     dword ptr [rsp+78h+var_50], edi
0x1800a8009  mov     r8, rbp
0x1800a800c  mov     rdx, r14
0x1800a800f  mov     [rsp+78h+var_58], rax
0x1800a8014  mov     rcx, r10
0x1800a8017  call    DeriveKeyCAPI_KDF
0x1800a801c  nop
0x1800a801d  jmp     loc_180043EE7
0x1800a8022  mov     rax, [rsp+78h+arg_20]
0x1800a802a  mov     r9d, esi
0x1800a802d  mov     dword ptr [rsp+78h+var_50], edi
0x1800a8031  mov     r8, rbp
0x1800a8034  mov     rdx, r14
0x1800a8037  mov     [rsp+78h+var_58], rax
0x1800a803c  mov     rcx, r10
0x1800a803f  call    DeriveKeyPBKDF2
0x1800a8044  nop
0x1800a8045  jmp     loc_180043EE7
0x1800a804a  mov     rax, [rsp+78h+arg_20]
0x1800a8052  mov     r9d, esi
0x1800a8055  mov     dword ptr [rsp+78h+var_50], edi
0x1800a8059  mov     r8, rbp
0x1800a805c  mov     rdx, r14
0x1800a805f  mov     [rsp+78h+var_58], rax
0x1800a8064  mov     rcx, r10
0x1800a8067  call    DeriveKeySP80056A_CONCAT
0x1800a806c  nop
0x1800a806d  jmp     loc_180043EE7
```
