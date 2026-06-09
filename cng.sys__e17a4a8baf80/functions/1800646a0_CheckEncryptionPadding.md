# CheckEncryptionPadding

- ea: `0x1800646a0`
- end: `0x1800648a5`
- name: `CheckEncryptionPadding`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180011c80`

## callees

- `0x18000dd90`
- `0x18001155c`
- `0x18004a28c`
- `0x1800646a0`
- `0x18006d584`
- `0x180071b30`
- `0x180071bd8`
- `0x1800726a0`

## string_xrefs

- `0x1800646d4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180064779`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180064875`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall CheckEncryptionPadding(
        char a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        _DWORD *a8)
{
  BCRYPT_HANDLE v8; // rdi
  __int64 v12; // r9
  unsigned int v13; // ebx
  unsigned int v14; // eax
  int v15; // eax
  NTSTATUS Property; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-18h] BYREF
  UCHAR v21[4]; // [rsp+54h] [rbp-14h] BYREF
  BCRYPT_HANDLE hObject[2]; // [rsp+58h] [rbp-10h] BYREF
  ULONG pcbResult; // [rsp+B8h] [rbp+50h] BYREF

  v8 = 0;
  hObject[0] = 0;
  *(_DWORD *)pbOutput = 0;
  *(_DWORD *)v21 = 0;
  pcbResult = 0;
  if ( a5 < a4 )
  {
    v12 = 3783;
LABEL_3:
    v13 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v12);
    return v13;
  }
  if ( (a1 & 2) != 0 )
  {
    hObject[0] = 0;
    v14 = SymCryptRsaPkcs1RemoveEncryptionPadding(a3, a4, a5, a6, a7, (__int64)hObject);
    v13 = SymCryptMapUint32(v14, 3221225485LL, &symmErrorsMap);
    *a8 = hObject[0];
    return v13;
  }
  if ( (a1 & 4) != 0 )
  {
    if ( !a2 || !*(_QWORD *)a2 )
    {
      v12 = 3813;
      goto LABEL_3;
    }
    v15 = CachedOpenAlgorithmProvider(hObject);
    v13 = v15;
    if ( v15 < 0 )
    {
      DebugTraceError((unsigned int)v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 3824);
      v8 = hObject[0];
      goto LABEL_21;
    }
    v8 = hObject[0];
    Property = BCryptGetProperty(hObject[0], L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    v13 = Property;
    if ( Property >= 0 )
    {
      Property = BCryptGetProperty(v8, L"HashDigestLength", v21, 4u, &pcbResult, 0);
      v13 = Property;
      if ( Property >= 0 )
      {
        Property = CheckOAEPPadding(
                     v8,
                     *(unsigned int *)v21,
                     *(unsigned int *)pbOutput,
                     *(_QWORD *)(a2 + 8),
                     *(_DWORD *)(a2 + 16),
                     a3,
                     a4,
                     a6,
                     a7,
                     a8);
        v13 = Property;
        if ( Property >= 0 )
          goto LABEL_21;
        v17 = 3864;
      }
      else
      {
        v17 = 3848;
      }
    }
    else
    {
      v17 = 3836;
    }
    v18 = (unsigned int)Property;
  }
  else
  {
    v13 = -1073741811;
    v17 = 3871;
    v18 = 3221225485LL;
  }
  DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v17);
LABEL_21:
  if ( v8 )
    CachedCloseAlgorithmProvider(v8);
  return v13;
}

```

## disassembly

```asm
0x1800646a0  push    rbp
0x1800646a2  push    rbx
0x1800646a3  push    rsi
0x1800646a4  push    rdi
0x1800646a5  push    r14
0x1800646a7  push    r15
0x1800646a9  mov     rbp, rsp
0x1800646ac  sub     rsp, 68h
0x1800646b0  xor     edi, edi
0x1800646b2  mov     r14d, r9d
0x1800646b5  mov     r15, r8
0x1800646b8  mov     rsi, rdx
0x1800646bb  mov     [rbp+hObject], rdi
0x1800646bf  mov     dword ptr [rbp+pbOutput], edi
0x1800646c2  mov     dword ptr [rbp+var_14], edi
0x1800646c5  mov     [rbp+arg_18], edi
0x1800646c8  cmp     [rbp+arg_20], r9d
0x1800646cc  jnb     short loc_1800646F6
0x1800646ce  mov     r9d, 0EC7h
0x1800646d4  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800646db  mov     ecx, 0C000000Dh
0x1800646e0  lea     rdx, aStatus; "Status"
0x1800646e7  mov     ebx, 0C000000Dh
0x1800646ec  call    DebugTraceError
0x1800646f1  jmp     loc_180064895
0x1800646f6  test    cl, 2
0x1800646f9  jz      short loc_180064746
0x1800646fb  mov     eax, [rbp+arg_30]
0x1800646fe  lea     rcx, [rbp+hObject]
0x180064702  mov     r8d, [rbp+arg_20]
0x180064706  mov     rdx, r14
0x180064709  mov     r9, [rbp+arg_28]
0x18006470d  mov     qword ptr [rsp+68h+dwFlags], rcx
0x180064712  mov     rcx, r15
0x180064715  mov     [rbp+hObject], rdi
0x180064719  mov     [rsp+68h+pcbResult], rax
0x18006471e  call    SymCryptRsaPkcs1RemoveEncryptionPadding
0x180064723  lea     r8, symmErrorsMap
0x18006472a  mov     edx, 0C000000Dh
0x18006472f  mov     ecx, eax
0x180064731  call    SymCryptMapUint32
0x180064736  mov     rdx, [rbp+arg_38]
0x18006473a  mov     ebx, eax
0x18006473c  mov     ecx, dword ptr [rbp+hObject]
0x18006473f  mov     [rdx], ecx
0x180064741  jmp     loc_180064895
0x180064746  test    cl, 4
0x180064749  jz      loc_180064865
0x18006474f  test    rsi, rsi
0x180064752  jz      loc_18006485A
0x180064758  mov     rdx, [rdx]
0x18006475b  test    rdx, rdx
0x18006475e  jz      loc_18006485A
0x180064764  lea     rcx, [rbp+hObject]
0x180064768  call    CachedOpenAlgorithmProvider
0x18006476d  mov     ebx, eax
0x18006476f  test    eax, eax
0x180064771  jns     short loc_180064797
0x180064773  mov     r9d, 0EF0h
0x180064779  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180064780  lea     rdx, aStatus; "Status"
0x180064787  mov     ecx, eax
0x180064789  call    DebugTraceError
0x18006478e  mov     rdi, [rbp+hObject]
0x180064792  jmp     loc_180064888
0x180064797  mov     [rsp+68h+dwFlags], edi; dwFlags
0x18006479b  lea     rax, [rbp+arg_18]
0x18006479f  mov     rdi, [rbp+hObject]
0x1800647a3  lea     r8, [rbp+pbOutput]; pbOutput
0x1800647a7  mov     rcx, rdi; hObject
0x1800647aa  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1800647af  mov     r9d, 4; cbOutput
0x1800647b5  lea     rdx, aObjectlength; "ObjectLength"
0x1800647bc  call    BCryptGetProperty
0x1800647c1  mov     ebx, eax
0x1800647c3  test    eax, eax
0x1800647c5  jns     short loc_1800647D4
0x1800647c7  mov     r9d, 0EFCh
0x1800647cd  mov     ecx, eax
0x1800647cf  jmp     loc_180064875
0x1800647d4  lea     rax, [rbp+arg_18]
0x1800647d8  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1800647e0  mov     r9d, 4; cbOutput
0x1800647e6  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1800647eb  lea     r8, [rbp+var_14]; pbOutput
0x1800647ef  mov     rcx, rdi; hObject
0x1800647f2  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800647f9  call    BCryptGetProperty
0x1800647fe  mov     ebx, eax
0x180064800  test    eax, eax
0x180064802  jns     short loc_18006480C
0x180064804  mov     r9d, 0F08h
0x18006480a  jmp     short loc_1800647CD
0x18006480c  mov     rax, [rbp+arg_38]
0x180064810  mov     rcx, rdi
0x180064813  mov     r9, [rsi+8]
0x180064817  mov     r8d, dword ptr [rbp+pbOutput]
0x18006481b  mov     edx, dword ptr [rbp+var_14]
0x18006481e  mov     [rsp+68h+var_20], rax
0x180064823  mov     eax, [rbp+arg_30]
0x180064826  mov     [rsp+68h+var_28], eax
0x18006482a  mov     rax, [rbp+arg_28]
0x18006482e  mov     [rsp+68h+var_30], rax
0x180064833  mov     eax, [rsi+10h]
0x180064836  mov     [rsp+68h+var_38], r14d
0x18006483b  mov     qword ptr [rsp+68h+dwFlags], r15
0x180064840  mov     dword ptr [rsp+68h+pcbResult], eax
0x180064844  call    CheckOAEPPadding
0x180064849  mov     ebx, eax
0x18006484b  test    eax, eax
0x18006484d  jns     short loc_180064888
0x18006484f  mov     r9d, 0F18h
0x180064855  jmp     loc_1800647CD
0x18006485a  mov     r9d, 0EE5h
0x180064860  jmp     loc_1800646D4
0x180064865  mov     ebx, 0C000000Dh
0x18006486a  mov     r9d, 0F1Fh
0x180064870  mov     ecx, 0C000000Dh
0x180064875  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006487c  lea     rdx, aStatus; "Status"
0x180064883  call    DebugTraceError
0x180064888  test    rdi, rdi
0x18006488b  jz      short loc_180064895
0x18006488d  mov     rcx, rdi; hAlgorithm
0x180064890  call    CachedCloseAlgorithmProvider
0x180064895  mov     eax, ebx
0x180064897  add     rsp, 68h
0x18006489b  pop     r15
0x18006489d  pop     r14
0x18006489f  pop     rdi
0x1800648a0  pop     rsi
0x1800648a1  pop     rbx
0x1800648a2  pop     rbp
0x1800648a3  retn
```
