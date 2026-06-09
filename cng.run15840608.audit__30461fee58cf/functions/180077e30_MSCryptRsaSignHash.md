# MSCryptRsaSignHash

- ea: `0x180077e30`
- end: `0x180078053`
- name: `MSCryptRsaSignHash`
- size: `547`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180077d80`

## callees

- `0x180001cc4`
- `0x180006470`
- `0x18000743c`
- `0x18003fc68`
- `0x180044750`
- `0x180047ce0`
- `0x180077658`
- `0x180077e30`
- `0x1800898b8`

## string_xrefs

- `0x180077f0a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180077fd9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180078019`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptRsaSignHash(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        unsigned int *a7,
        int a8)
{
  unsigned int v8; // ebx
  void *v12; // rdi
  unsigned int v13; // esi
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r15
  int HashOidList; // eax
  __int64 v19; // r9
  unsigned int v20; // eax
  int v21; // eax
  unsigned int v23; // [rsp+50h] [rbp-28h] BYREF
  __int64 v24; // [rsp+58h] [rbp-20h]
  _QWORD *v25; // [rsp+60h] [rbp-18h] BYREF
  __int64 v26; // [rsp+68h] [rbp-10h] BYREF

  v8 = 0;
  v26 = 0;
  v12 = 0;
  v25 = 0;
  v23 = 0;
  v13 = 0;
  if ( (a8 & 0xFFFFFFF5) != 0 )
  {
    v14 = 2011;
  }
  else
  {
    v16 = validateMSCryptRsaKey(a1);
    v17 = v16;
    if ( !v16 || !*(_DWORD *)(v16 + 16) )
    {
      v8 = -1073741816;
      v14 = 2021;
      v15 = 3221225480LL;
      goto LABEL_32;
    }
    v13 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(v16 + 32) + 16LL) + 7) >> 3;
    v24 = v13;
    if ( !a5 )
      goto LABEL_33;
    if ( a2 && a3 && a4 )
    {
      if ( a6 < v13 )
      {
        v8 = -1073741789;
        goto LABEL_33;
      }
      if ( (a8 & 2) != 0 )
      {
        HashOidList = GetHashOidList((_QWORD *)a2, a4, &v25, &v23);
        v8 = HashOidList;
        if ( HashOidList < 0 )
        {
          DebugTraceError(
            (unsigned int)HashOidList,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
            2064);
          v12 = v25;
          goto LABEL_33;
        }
        v12 = v25;
        if ( v25 )
          v19 = v25[1];
        else
          LODWORD(v19) = 0;
        if ( a4 > v13 )
          a4 = v13;
        v20 = SymCryptRsaPkcs1Sign(*(_QWORD *)(v17 + 32), a3, a4, v19);
      }
      else
      {
        v21 = CheckAndGetPssHashAlgorithm(a2, a4, &v26);
        v8 = v21;
        if ( v21 < 0 )
        {
          v14 = 2090;
          v15 = (unsigned int)v21;
          goto LABEL_32;
        }
        if ( a4 > v13 )
          a4 = v13;
        v20 = SymCryptRsaPssSign(*(_QWORD *)(v17 + 32), a3, a4, v26, *(unsigned int *)(a2 + 8));
      }
      if ( v20 )
      {
        v8 = SymcryptErrorCodeToNtStatus(v20);
        DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 2110);
      }
      else
      {
        v8 = 0;
      }
      v13 = v24;
      goto LABEL_33;
    }
    v14 = 2039;
  }
  v8 = -1073741811;
  v15 = 3221225485LL;
LABEL_32:
  DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v14);
LABEL_33:
  *a7 = v13;
  if ( v12 )
    MSCryptFree(v12);
  return v8;
}

```

## disassembly

```asm
0x180077e30  push    rbp
0x180077e32  push    rbx
0x180077e33  push    rsi
0x180077e34  push    rdi
0x180077e35  push    r12
0x180077e37  push    r13
0x180077e39  push    r14
0x180077e3b  push    r15
0x180077e3d  mov     rbp, rsp
0x180077e40  sub     rsp, 78h
0x180077e44  xor     ebx, ebx
0x180077e46  mov     r14d, r9d
0x180077e49  test    [rbp+arg_38], 0FFFFFFF5h
0x180077e53  mov     r13, r8
0x180077e56  mov     r12, rdx
0x180077e59  mov     [rbp+var_10], rbx
0x180077e5d  mov     edi, ebx
0x180077e5f  mov     [rbp+var_18], rbx
0x180077e63  mov     [rbp+var_28], ebx
0x180077e66  mov     esi, ebx
0x180077e68  jz      short loc_180077E7F
0x180077e6a  mov     r9d, 7DBh
0x180077e70  mov     ebx, 0C000000Dh
0x180077e75  mov     ecx, 0C000000Dh
0x180077e7a  jmp     loc_180078019
0x180077e7f  call    validateMSCryptRsaKey
0x180077e84  mov     r15, rax
0x180077e87  test    rax, rax
0x180077e8a  jz      loc_180078009
0x180077e90  cmp     [rax+10h], ebx
0x180077e93  jz      loc_180078009
0x180077e99  mov     rax, [rax+20h]
0x180077e9d  mov     esi, [rax+10h]
0x180077ea0  add     esi, 7
0x180077ea3  shr     esi, 3
0x180077ea6  mov     [rbp+var_20], rsi
0x180077eaa  cmp     [rbp+arg_20], rbx
0x180077eae  jz      loc_18007802C
0x180077eb4  test    r12, r12
0x180077eb7  jz      loc_180077FFE
0x180077ebd  test    r13, r13
0x180077ec0  jz      loc_180077FFE
0x180077ec6  test    r14d, r14d
0x180077ec9  jz      loc_180077FFE
0x180077ecf  cmp     [rbp+arg_28], esi
0x180077ed2  jnb     short loc_180077EDE
0x180077ed4  mov     ebx, 0C0000023h
0x180077ed9  jmp     loc_18007802C
0x180077ede  test    byte ptr [rbp+arg_38], 2
0x180077ee5  mov     edx, r14d
0x180077ee8  mov     rcx, r12
0x180077eeb  jz      loc_180077F75
0x180077ef1  lea     r9, [rbp+var_28]
0x180077ef5  lea     r8, [rbp+var_18]
0x180077ef9  call    GetHashOidList
0x180077efe  mov     ebx, eax
0x180077f00  test    eax, eax
0x180077f02  jns     short loc_180077F28
0x180077f04  mov     r9d, 810h
0x180077f0a  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180077f11  lea     rdx, aStatus; "Status"
0x180077f18  mov     ecx, eax
0x180077f1a  call    DebugTraceError
0x180077f1f  mov     rdi, [rbp+var_18]
0x180077f23  jmp     loc_18007802C
0x180077f28  mov     rdi, [rbp+var_18]
0x180077f2c  xor     eax, eax
0x180077f2e  test    rdi, rdi
0x180077f31  setz    al
0x180077f34  test    rdi, rdi
0x180077f37  jz      short loc_180077F3F
0x180077f39  mov     r9, [rdi+8]
0x180077f3d  jmp     short loc_180077F42
0x180077f3f  xor     r9d, r9d
0x180077f42  lea     rcx, [rbp+var_20]
0x180077f46  cmp     r14d, esi
0x180077f49  mov     [rsp+78h+var_30], rcx
0x180077f4e  mov     rdx, r13
0x180077f51  mov     rcx, [rbp+arg_20]
0x180077f55  cmova   r14d, esi
0x180077f59  mov     [rsp+78h+var_38], rsi
0x180077f5e  mov     [rsp+78h+var_40], rcx
0x180077f63  mov     rcx, [r15+20h]
0x180077f67  mov     r8d, r14d
0x180077f6a  mov     [rsp+78h+var_50], eax
0x180077f6e  call    SymCryptRsaPkcs1Sign
0x180077f73  jmp     short loc_180077FCC
0x180077f75  lea     r8, [rbp+var_10]
0x180077f79  call    CheckAndGetPssHashAlgorithm
0x180077f7e  mov     ebx, eax
0x180077f80  test    eax, eax
0x180077f82  jns     short loc_180077F91
0x180077f84  mov     r9d, 82Ah
0x180077f8a  mov     ecx, eax
0x180077f8c  jmp     loc_180078019
0x180077f91  mov     eax, [r12+8]
0x180077f96  lea     rcx, [rbp+var_20]
0x180077f9a  mov     r9, [rbp+var_10]
0x180077f9e  cmp     r14d, esi
0x180077fa1  mov     [rsp+78h+var_30], rcx
0x180077fa6  mov     rdx, r13
0x180077fa9  mov     rcx, [rbp+arg_20]
0x180077fad  cmova   r14d, esi
0x180077fb1  mov     [rsp+78h+var_38], rsi
0x180077fb6  mov     [rsp+78h+var_40], rcx
0x180077fbb  mov     rcx, [r15+20h]
0x180077fbf  mov     r8d, r14d
0x180077fc2  mov     [rsp+78h+var_58], rax
0x180077fc7  call    SymCryptRsaPssSign
0x180077fcc  test    eax, eax
0x180077fce  jz      short loc_180077FFA
0x180077fd0  mov     ecx, eax
0x180077fd2  call    SymcryptErrorCodeToNtStatus
0x180077fd7  mov     ecx, eax
0x180077fd9  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180077fe0  mov     r9d, 83Eh
0x180077fe6  lea     rdx, aStatus; "Status"
0x180077fed  mov     ebx, eax
0x180077fef  call    DebugTraceError
0x180077ff4  mov     rsi, [rbp+var_20]
0x180077ff8  jmp     short loc_18007802C
0x180077ffa  xor     ebx, ebx
0x180077ffc  jmp     short loc_180077FF4
0x180077ffe  mov     r9d, 7F7h
0x180078004  jmp     loc_180077E70
0x180078009  mov     ebx, 0C0000008h
0x18007800e  mov     r9d, 7E5h
0x180078014  mov     ecx, 0C0000008h
0x180078019  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180078020  lea     rdx, aStatus; "Status"
0x180078027  call    DebugTraceError
0x18007802c  mov     rax, [rbp+arg_30]
0x180078030  mov     [rax], esi
0x180078032  test    rdi, rdi
0x180078035  jz      short loc_18007803F
0x180078037  mov     rcx, rdi; P
0x18007803a  call    MSCryptFree
0x18007803f  mov     eax, ebx
0x180078041  add     rsp, 78h
0x180078045  pop     r15
0x180078047  pop     r14
0x180078049  pop     r13
0x18007804b  pop     r12
0x18007804d  pop     rdi
0x18007804e  pop     rsi
0x18007804f  pop     rbx
0x180078050  pop     rbp
0x180078051  retn
```
