# MSCryptRsaSignHash

- ea: `0x180078840`
- end: `0x180078a63`
- name: `MSCryptRsaSignHash`
- size: `547`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180078790`

## callees

- `0x180001cc4`
- `0x180006470`
- `0x18000743c`
- `0x1800407f8`
- `0x1800451e0`
- `0x180048770`
- `0x180078068`
- `0x180078840`
- `0x18008a8c8`

## string_xrefs

- `0x18007891a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x1800789e9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180078a29`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

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
  int v23; // [rsp+50h] [rbp-28h] BYREF
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
0x180078840  push    rbp
0x180078842  push    rbx
0x180078843  push    rsi
0x180078844  push    rdi
0x180078845  push    r12
0x180078847  push    r13
0x180078849  push    r14
0x18007884b  push    r15
0x18007884d  mov     rbp, rsp
0x180078850  sub     rsp, 78h
0x180078854  xor     ebx, ebx
0x180078856  mov     r14d, r9d
0x180078859  test    [rbp+arg_38], 0FFFFFFF5h
0x180078863  mov     r13, r8
0x180078866  mov     r12, rdx
0x180078869  mov     [rbp+var_10], rbx
0x18007886d  mov     edi, ebx
0x18007886f  mov     [rbp+var_18], rbx
0x180078873  mov     [rbp+var_28], ebx
0x180078876  mov     esi, ebx
0x180078878  jz      short loc_18007888F
0x18007887a  mov     r9d, 7DBh
0x180078880  mov     ebx, 0C000000Dh
0x180078885  mov     ecx, 0C000000Dh
0x18007888a  jmp     loc_180078A29
0x18007888f  call    validateMSCryptRsaKey
0x180078894  mov     r15, rax
0x180078897  test    rax, rax
0x18007889a  jz      loc_180078A19
0x1800788a0  cmp     [rax+10h], ebx
0x1800788a3  jz      loc_180078A19
0x1800788a9  mov     rax, [rax+20h]
0x1800788ad  mov     esi, [rax+10h]
0x1800788b0  add     esi, 7
0x1800788b3  shr     esi, 3
0x1800788b6  mov     [rbp+var_20], rsi
0x1800788ba  cmp     [rbp+arg_20], rbx
0x1800788be  jz      loc_180078A3C
0x1800788c4  test    r12, r12
0x1800788c7  jz      loc_180078A0E
0x1800788cd  test    r13, r13
0x1800788d0  jz      loc_180078A0E
0x1800788d6  test    r14d, r14d
0x1800788d9  jz      loc_180078A0E
0x1800788df  cmp     [rbp+arg_28], esi
0x1800788e2  jnb     short loc_1800788EE
0x1800788e4  mov     ebx, 0C0000023h
0x1800788e9  jmp     loc_180078A3C
0x1800788ee  test    byte ptr [rbp+arg_38], 2
0x1800788f5  mov     edx, r14d
0x1800788f8  mov     rcx, r12
0x1800788fb  jz      loc_180078985
0x180078901  lea     r9, [rbp+var_28]
0x180078905  lea     r8, [rbp+var_18]
0x180078909  call    GetHashOidList
0x18007890e  mov     ebx, eax
0x180078910  test    eax, eax
0x180078912  jns     short loc_180078938
0x180078914  mov     r9d, 810h
0x18007891a  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180078921  lea     rdx, aStatus; "Status"
0x180078928  mov     ecx, eax
0x18007892a  call    DebugTraceError
0x18007892f  mov     rdi, [rbp+var_18]
0x180078933  jmp     loc_180078A3C
0x180078938  mov     rdi, [rbp+var_18]
0x18007893c  xor     eax, eax
0x18007893e  test    rdi, rdi
0x180078941  setz    al
0x180078944  test    rdi, rdi
0x180078947  jz      short loc_18007894F
0x180078949  mov     r9, [rdi+8]
0x18007894d  jmp     short loc_180078952
0x18007894f  xor     r9d, r9d
0x180078952  lea     rcx, [rbp+var_20]
0x180078956  cmp     r14d, esi
0x180078959  mov     [rsp+78h+var_30], rcx
0x18007895e  mov     rdx, r13
0x180078961  mov     rcx, [rbp+arg_20]
0x180078965  cmova   r14d, esi
0x180078969  mov     [rsp+78h+var_38], rsi
0x18007896e  mov     [rsp+78h+var_40], rcx
0x180078973  mov     rcx, [r15+20h]
0x180078977  mov     r8d, r14d
0x18007897a  mov     [rsp+78h+var_50], eax
0x18007897e  call    SymCryptRsaPkcs1Sign
0x180078983  jmp     short loc_1800789DC
0x180078985  lea     r8, [rbp+var_10]
0x180078989  call    CheckAndGetPssHashAlgorithm
0x18007898e  mov     ebx, eax
0x180078990  test    eax, eax
0x180078992  jns     short loc_1800789A1
0x180078994  mov     r9d, 82Ah
0x18007899a  mov     ecx, eax
0x18007899c  jmp     loc_180078A29
0x1800789a1  mov     eax, [r12+8]
0x1800789a6  lea     rcx, [rbp+var_20]
0x1800789aa  mov     r9, [rbp+var_10]
0x1800789ae  cmp     r14d, esi
0x1800789b1  mov     [rsp+78h+var_30], rcx
0x1800789b6  mov     rdx, r13
0x1800789b9  mov     rcx, [rbp+arg_20]
0x1800789bd  cmova   r14d, esi
0x1800789c1  mov     [rsp+78h+var_38], rsi
0x1800789c6  mov     [rsp+78h+var_40], rcx
0x1800789cb  mov     rcx, [r15+20h]
0x1800789cf  mov     r8d, r14d
0x1800789d2  mov     [rsp+78h+var_58], rax
0x1800789d7  call    SymCryptRsaPssSign
0x1800789dc  test    eax, eax
0x1800789de  jz      short loc_180078A0A
0x1800789e0  mov     ecx, eax
0x1800789e2  call    SymcryptErrorCodeToNtStatus
0x1800789e7  mov     ecx, eax
0x1800789e9  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800789f0  mov     r9d, 83Eh
0x1800789f6  lea     rdx, aStatus; "Status"
0x1800789fd  mov     ebx, eax
0x1800789ff  call    DebugTraceError
0x180078a04  mov     rsi, [rbp+var_20]
0x180078a08  jmp     short loc_180078A3C
0x180078a0a  xor     ebx, ebx
0x180078a0c  jmp     short loc_180078A04
0x180078a0e  mov     r9d, 7F7h
0x180078a14  jmp     loc_180078880
0x180078a19  mov     ebx, 0C0000008h
0x180078a1e  mov     r9d, 7E5h
0x180078a24  mov     ecx, 0C0000008h
0x180078a29  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180078a30  lea     rdx, aStatus; "Status"
0x180078a37  call    DebugTraceError
0x180078a3c  mov     rax, [rbp+arg_30]
0x180078a40  mov     [rax], esi
0x180078a42  test    rdi, rdi
0x180078a45  jz      short loc_180078A4F
0x180078a47  mov     rcx, rdi; P
0x180078a4a  call    MSCryptFree
0x180078a4f  mov     eax, ebx
0x180078a51  add     rsp, 78h
0x180078a55  pop     r15
0x180078a57  pop     r14
0x180078a59  pop     r13
0x180078a5b  pop     r12
0x180078a5d  pop     rdi
0x180078a5e  pop     rsi
0x180078a5f  pop     rbx
0x180078a60  pop     rbp
0x180078a61  retn
```
