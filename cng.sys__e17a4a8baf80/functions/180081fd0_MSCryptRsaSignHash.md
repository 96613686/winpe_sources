# MSCryptRsaSignHash

- ea: `0x180081fd0`
- end: `0x1800821f3`
- name: `MSCryptRsaSignHash`
- size: `547`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180081f20`

## callees

- `0x18000bde4`
- `0x180010590`
- `0x18001155c`
- `0x180049c28`
- `0x18004e840`
- `0x180051dd0`
- `0x1800817f8`
- `0x180081fd0`
- `0x1800938e8`

## string_xrefs

- `0x1800820aa`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180082179`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x1800821b9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

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
0x180081fd0  push    rbp
0x180081fd2  push    rbx
0x180081fd3  push    rsi
0x180081fd4  push    rdi
0x180081fd5  push    r12
0x180081fd7  push    r13
0x180081fd9  push    r14
0x180081fdb  push    r15
0x180081fdd  mov     rbp, rsp
0x180081fe0  sub     rsp, 78h
0x180081fe4  xor     ebx, ebx
0x180081fe6  mov     r14d, r9d
0x180081fe9  test    [rbp+arg_38], 0FFFFFFF5h
0x180081ff3  mov     r13, r8
0x180081ff6  mov     r12, rdx
0x180081ff9  mov     [rbp+var_10], rbx
0x180081ffd  mov     edi, ebx
0x180081fff  mov     [rbp+var_18], rbx
0x180082003  mov     [rbp+var_28], ebx
0x180082006  mov     esi, ebx
0x180082008  jz      short loc_18008201F
0x18008200a  mov     r9d, 7DBh
0x180082010  mov     ebx, 0C000000Dh
0x180082015  mov     ecx, 0C000000Dh
0x18008201a  jmp     loc_1800821B9
0x18008201f  call    validateMSCryptRsaKey
0x180082024  mov     r15, rax
0x180082027  test    rax, rax
0x18008202a  jz      loc_1800821A9
0x180082030  cmp     [rax+10h], ebx
0x180082033  jz      loc_1800821A9
0x180082039  mov     rax, [rax+20h]
0x18008203d  mov     esi, [rax+10h]
0x180082040  add     esi, 7
0x180082043  shr     esi, 3
0x180082046  mov     [rbp+var_20], rsi
0x18008204a  cmp     [rbp+arg_20], rbx
0x18008204e  jz      loc_1800821CC
0x180082054  test    r12, r12
0x180082057  jz      loc_18008219E
0x18008205d  test    r13, r13
0x180082060  jz      loc_18008219E
0x180082066  test    r14d, r14d
0x180082069  jz      loc_18008219E
0x18008206f  cmp     [rbp+arg_28], esi
0x180082072  jnb     short loc_18008207E
0x180082074  mov     ebx, 0C0000023h
0x180082079  jmp     loc_1800821CC
0x18008207e  test    byte ptr [rbp+arg_38], 2
0x180082085  mov     edx, r14d
0x180082088  mov     rcx, r12
0x18008208b  jz      loc_180082115
0x180082091  lea     r9, [rbp+var_28]
0x180082095  lea     r8, [rbp+var_18]
0x180082099  call    GetHashOidList
0x18008209e  mov     ebx, eax
0x1800820a0  test    eax, eax
0x1800820a2  jns     short loc_1800820C8
0x1800820a4  mov     r9d, 810h
0x1800820aa  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800820b1  lea     rdx, aStatus; "Status"
0x1800820b8  mov     ecx, eax
0x1800820ba  call    DebugTraceError
0x1800820bf  mov     rdi, [rbp+var_18]
0x1800820c3  jmp     loc_1800821CC
0x1800820c8  mov     rdi, [rbp+var_18]
0x1800820cc  xor     eax, eax
0x1800820ce  test    rdi, rdi
0x1800820d1  setz    al
0x1800820d4  test    rdi, rdi
0x1800820d7  jz      short loc_1800820DF
0x1800820d9  mov     r9, [rdi+8]
0x1800820dd  jmp     short loc_1800820E2
0x1800820df  xor     r9d, r9d
0x1800820e2  lea     rcx, [rbp+var_20]
0x1800820e6  cmp     r14d, esi
0x1800820e9  mov     [rsp+78h+var_30], rcx
0x1800820ee  mov     rdx, r13
0x1800820f1  mov     rcx, [rbp+arg_20]
0x1800820f5  cmova   r14d, esi
0x1800820f9  mov     [rsp+78h+var_38], rsi
0x1800820fe  mov     [rsp+78h+var_40], rcx
0x180082103  mov     rcx, [r15+20h]
0x180082107  mov     r8d, r14d
0x18008210a  mov     [rsp+78h+var_50], eax
0x18008210e  call    SymCryptRsaPkcs1Sign
0x180082113  jmp     short loc_18008216C
0x180082115  lea     r8, [rbp+var_10]
0x180082119  call    CheckAndGetPssHashAlgorithm
0x18008211e  mov     ebx, eax
0x180082120  test    eax, eax
0x180082122  jns     short loc_180082131
0x180082124  mov     r9d, 82Ah
0x18008212a  mov     ecx, eax
0x18008212c  jmp     loc_1800821B9
0x180082131  mov     eax, [r12+8]
0x180082136  lea     rcx, [rbp+var_20]
0x18008213a  mov     r9, [rbp+var_10]
0x18008213e  cmp     r14d, esi
0x180082141  mov     [rsp+78h+var_30], rcx
0x180082146  mov     rdx, r13
0x180082149  mov     rcx, [rbp+arg_20]
0x18008214d  cmova   r14d, esi
0x180082151  mov     [rsp+78h+var_38], rsi
0x180082156  mov     [rsp+78h+var_40], rcx
0x18008215b  mov     rcx, [r15+20h]
0x18008215f  mov     r8d, r14d
0x180082162  mov     [rsp+78h+var_58], rax
0x180082167  call    SymCryptRsaPssSign
0x18008216c  test    eax, eax
0x18008216e  jz      short loc_18008219A
0x180082170  mov     ecx, eax
0x180082172  call    SymcryptErrorCodeToNtStatus
0x180082177  mov     ecx, eax
0x180082179  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180082180  mov     r9d, 83Eh
0x180082186  lea     rdx, aStatus; "Status"
0x18008218d  mov     ebx, eax
0x18008218f  call    DebugTraceError
0x180082194  mov     rsi, [rbp+var_20]
0x180082198  jmp     short loc_1800821CC
0x18008219a  xor     ebx, ebx
0x18008219c  jmp     short loc_180082194
0x18008219e  mov     r9d, 7F7h
0x1800821a4  jmp     loc_180082010
0x1800821a9  mov     ebx, 0C0000008h
0x1800821ae  mov     r9d, 7E5h
0x1800821b4  mov     ecx, 0C0000008h
0x1800821b9  lea     r8, aOnecoreDsSecur_34; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800821c0  lea     rdx, aStatus; "Status"
0x1800821c7  call    DebugTraceError
0x1800821cc  mov     rax, [rbp+arg_30]
0x1800821d0  mov     [rax], esi
0x1800821d2  test    rdi, rdi
0x1800821d5  jz      short loc_1800821DF
0x1800821d7  mov     rcx, rdi; P
0x1800821da  call    MSCryptFree
0x1800821df  mov     eax, ebx
0x1800821e1  add     rsp, 78h
0x1800821e5  pop     r15
0x1800821e7  pop     r14
0x1800821e9  pop     r13
0x1800821eb  pop     r12
0x1800821ed  pop     rdi
0x1800821ee  pop     rsi
0x1800821ef  pop     rbx
0x1800821f0  pop     rbp
0x1800821f1  retn
```
