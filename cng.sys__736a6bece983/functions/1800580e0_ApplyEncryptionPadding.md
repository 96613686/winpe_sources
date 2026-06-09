# ApplyEncryptionPadding

- ea: `0x1800580e0`
- end: `0x180058369`
- name: `ApplyEncryptionPadding`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800071b0`

## callees

- `0x180003320`
- `0x180003c70`
- `0x18000743c`
- `0x180049b14`
- `0x1800580e0`
- `0x180068390`
- `0x180068438`
- `0x18009f780`

## string_xrefs

- `0x1800581f5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005823f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180058335`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall ApplyEncryptionPadding(char a1, __int64 a2, void *a3, unsigned int a4, __int64 a5, int a6)
{
  size_t v6; // r15
  BCRYPT_HANDLE v9; // rdi
  unsigned int v10; // eax
  __int64 v11; // r14
  ULONG v12; // r8d
  UCHAR *v13; // rdx
  NTSTATUS v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // r9
  __int64 v17; // rcx
  ULONG i; // esi
  int v19; // eax
  NTSTATUS Property; // eax
  __int64 v21; // r9
  __int64 v22; // rcx
  void *dwFlags; // [rsp+28h] [rbp-40h]
  size_t Size; // [rsp+38h] [rbp-30h]
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-18h] BYREF
  UCHAR v27[4]; // [rsp+54h] [rbp-14h] BYREF
  BCRYPT_HANDLE hObject[2]; // [rsp+58h] [rbp-10h] BYREF
  ULONG pcbResult; // [rsp+B0h] [rbp+48h] BYREF

  v6 = a4;
  hObject[0] = 0;
  *(_DWORD *)pbOutput = 0;
  *(_DWORD *)v27 = 0;
  v9 = 0;
  pcbResult = 0;
  if ( (a1 & 2) != 0 )
  {
    v10 = a4 + 3;
    if ( a4 + 3 < a4 )
    {
      v16 = 3641;
    }
    else
    {
      if ( a6 >= v10 )
      {
        v11 = a5;
        v12 = a6 - v10;
        pcbResult = a6 - v10;
        v13 = (UCHAR *)(a5 + 2);
        *(_WORD *)a5 = 512;
        v14 = BCryptGenRandom(0, v13, v12, 2u);
        v15 = v14;
        if ( v14 < 0 )
        {
          v16 = 3659;
LABEL_6:
          v17 = (unsigned int)v14;
          goto LABEL_18;
        }
        for ( i = 0; i < pcbResult; ++i )
        {
          while ( !*(_BYTE *)(i + 2 + v11) )
          {
            v14 = BCryptGenRandom(0, (PUCHAR)(v11 + i + 2LL), 1u, 2u);
            v15 = v14;
            if ( v14 < 0 )
            {
              v16 = 3673;
              goto LABEL_6;
            }
          }
        }
        *(_BYTE *)(pcbResult + 2 + v11) = 0;
        memmove((void *)(v11 + pcbResult + 3LL), a3, v6);
        goto LABEL_14;
      }
      v16 = 3646;
    }
    v15 = -2147024362;
    pcbResult = -1;
    v17 = 2147942934LL;
LABEL_18:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v16);
    return v15;
  }
  if ( (a1 & 4) != 0 )
  {
    if ( !a2 || !*(_QWORD *)a2 )
    {
      v15 = -1073741811;
      v16 = 3690;
      v17 = 3221225485LL;
      goto LABEL_18;
    }
    v19 = CachedOpenAlgorithmProvider(hObject);
    v15 = v19;
    if ( v19 < 0 )
    {
      DebugTraceError((unsigned int)v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 3701);
      v9 = hObject[0];
      goto LABEL_34;
    }
    v9 = hObject[0];
    Property = BCryptGetProperty(hObject[0], L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    v15 = Property;
    if ( Property >= 0 )
    {
      Property = BCryptGetProperty(v9, L"HashDigestLength", v27, 4u, &pcbResult, 0);
      v15 = Property;
      if ( Property >= 0 )
      {
        LODWORD(Size) = v6;
        Property = ApplyOAEPPaddingSeeded(
                     v9,
                     *(ULONG *)v27,
                     *(ULONG *)pbOutput,
                     *(_DWORD *)(a2 + 16),
                     dwFlags,
                     a3,
                     Size,
                     a5,
                     a6);
        v15 = Property;
        if ( Property >= 0 )
        {
LABEL_14:
          v15 = 0;
          goto LABEL_34;
        }
        v21 = 3740;
      }
      else
      {
        v21 = 3725;
      }
    }
    else
    {
      v21 = 3713;
    }
    v22 = (unsigned int)Property;
  }
  else
  {
    v15 = -1073741811;
    v21 = 3747;
    v22 = 3221225485LL;
  }
  DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v21);
LABEL_34:
  if ( v9 )
    CachedCloseAlgorithmProvider(v9);
  return v15;
}

```

## disassembly

```asm
0x1800580e0  push    rbp
0x1800580e2  push    rbx
0x1800580e3  push    rsi
0x1800580e4  push    rdi
0x1800580e5  push    r12
0x1800580e7  push    r13
0x1800580e9  push    r14
0x1800580eb  push    r15
0x1800580ed  mov     rbp, rsp
0x1800580f0  sub     rsp, 68h
0x1800580f4  xor     r12d, r12d
0x1800580f7  mov     r15d, r9d
0x1800580fa  mov     [rbp+hObject], r12
0x1800580fe  mov     r13, r8
0x180058101  mov     dword ptr [rbp+pbOutput], r12d
0x180058105  mov     rsi, rdx
0x180058108  mov     dword ptr [rbp+var_14], r12d
0x18005810c  mov     edi, r12d
0x18005810f  mov     [rbp+arg_0], r12d
0x180058113  test    cl, 2
0x180058116  jz      loc_180058206
0x18005811c  lea     eax, [r15+3]
0x180058120  cmp     eax, r15d
0x180058123  jb      loc_1800581D7
0x180058129  mov     r8d, [rbp+arg_28]
0x18005812d  cmp     r8d, eax
0x180058130  jb      loc_1800581CF
0x180058136  mov     r14, [rbp+arg_20]
0x18005813a  lea     r9d, [r12+2]; dwFlags
0x18005813f  sub     r8d, eax; cbBuffer
0x180058142  xor     ecx, ecx; hAlgorithm
0x180058144  mov     [rbp+arg_0], r8d
0x180058148  lea     rdx, [r14+2]; pbBuffer
0x18005814c  mov     word ptr [r14], 200h
0x180058152  call    BCryptGenRandom
0x180058157  mov     ebx, eax
0x180058159  test    eax, eax
0x18005815b  jns     short loc_18005816A
0x18005815d  mov     r9d, 0E4Bh
0x180058163  mov     ecx, eax
0x180058165  jmp     loc_1800581EE
0x18005816a  mov     esi, r12d
0x18005816d  mov     eax, [rbp+arg_0]
0x180058170  cmp     esi, eax
0x180058172  jnb     short loc_1800581A8
0x180058174  lea     r12d, [rsi+2]
0x180058178  cmp     [r12+r14], dil
0x18005817c  jnz     short loc_1800581A4
0x18005817e  xor     ecx, ecx; hAlgorithm
0x180058180  mov     edx, esi
0x180058182  add     rdx, 2
0x180058186  add     rdx, r14; pbBuffer
0x180058189  lea     r9d, [rcx+2]; dwFlags
0x18005818d  lea     r8d, [rcx+1]; cbBuffer
0x180058191  call    BCryptGenRandom
0x180058196  mov     ebx, eax
0x180058198  test    eax, eax
0x18005819a  jns     short loc_180058178
0x18005819c  mov     r9d, 0E59h
0x1800581a2  jmp     short loc_180058163
0x1800581a4  inc     esi
0x1800581a6  jmp     short loc_18005816D
0x1800581a8  add     eax, 2
0x1800581ab  xor     r12d, r12d
0x1800581ae  mov     r8, r15; Size
0x1800581b1  mov     rdx, r13; Src
0x1800581b4  mov     [rax+r14], r12b
0x1800581b8  mov     ecx, [rbp+arg_0]
0x1800581bb  add     rcx, 3
0x1800581bf  add     rcx, r14; void *
0x1800581c2  call    memmove
0x1800581c7  mov     ebx, r12d
0x1800581ca  jmp     loc_180058348
0x1800581cf  mov     r9d, 0E3Eh
0x1800581d5  jmp     short loc_1800581DD
0x1800581d7  mov     r9d, 0E39h
0x1800581dd  mov     ebx, 80070216h
0x1800581e2  mov     [rbp+arg_0], 0FFFFFFFFh
0x1800581e9  mov     ecx, 80070216h
0x1800581ee  lea     rdx, aStatus; "Status"
0x1800581f5  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800581fc  call    DebugTraceError
0x180058201  jmp     loc_180058355
0x180058206  mov     r14d, 4
0x18005820c  test    r14b, cl
0x18005820f  jz      loc_180058325
0x180058215  test    rsi, rsi
0x180058218  jz      loc_180058310
0x18005821e  mov     rdx, [rdx]
0x180058221  test    rdx, rdx
0x180058224  jz      loc_180058310
0x18005822a  lea     rcx, [rbp+hObject]
0x18005822e  call    CachedOpenAlgorithmProvider
0x180058233  mov     ebx, eax
0x180058235  test    eax, eax
0x180058237  jns     short loc_18005825D
0x180058239  mov     r9d, 0E75h
0x18005823f  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180058246  lea     rdx, aStatus; "Status"
0x18005824d  mov     ecx, eax
0x18005824f  call    DebugTraceError
0x180058254  mov     rdi, [rbp+hObject]
0x180058258  jmp     loc_180058348
0x18005825d  mov     rdi, [rbp+hObject]
0x180058261  lea     rax, [rbp+arg_0]
0x180058265  mov     rcx, rdi; hObject
0x180058268  mov     dword ptr [rsp+68h+dwFlags], r12d; dwFlags
0x18005826d  mov     r9d, r14d; cbOutput
0x180058270  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180058275  lea     r8, [rbp+pbOutput]; pbOutput
0x180058279  lea     rdx, aObjectlength; "ObjectLength"
0x180058280  call    BCryptGetProperty
0x180058285  mov     ebx, eax
0x180058287  test    eax, eax
0x180058289  jns     short loc_180058298
0x18005828b  mov     r9d, 0E81h
0x180058291  mov     ecx, eax
0x180058293  jmp     loc_180058335
0x180058298  lea     rax, [rbp+arg_0]
0x18005829c  mov     dword ptr [rsp+68h+dwFlags], r12d; phHash
0x1800582a1  mov     r9d, r14d; cbOutput
0x1800582a4  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1800582a9  lea     r8, [rbp+var_14]; pbOutput
0x1800582ad  mov     rcx, rdi; hObject
0x1800582b0  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800582b7  call    BCryptGetProperty
0x1800582bc  mov     ebx, eax
0x1800582be  test    eax, eax
0x1800582c0  jns     short loc_1800582CA
0x1800582c2  mov     r9d, 0E8Dh
0x1800582c8  jmp     short loc_180058291
0x1800582ca  mov     eax, [rbp+arg_28]
0x1800582cd  mov     rcx, rdi; hAlgorithm
0x1800582d0  mov     r9, [rsi+8]
0x1800582d4  mov     r8d, dword ptr [rbp+pbOutput]; cbHashObject
0x1800582d8  mov     edx, dword ptr [rbp+var_14]; cbBuffer
0x1800582db  mov     [rsp+68h+var_20], eax; int
0x1800582df  mov     rax, [rbp+arg_20]
0x1800582e3  mov     [rsp+68h+var_28], rax; __int64
0x1800582e8  mov     eax, [rsi+10h]
0x1800582eb  mov     dword ptr [rsp+68h+Size], r15d; Size
0x1800582f0  mov     [rsp+68h+Src], r13; Src
0x1800582f5  mov     dword ptr [rsp+68h+pcbResult], eax; cbInput
0x1800582f9  call    ApplyOAEPPaddingSeeded
0x1800582fe  mov     ebx, eax
0x180058300  test    eax, eax
0x180058302  jns     loc_1800581C7
0x180058308  mov     r9d, 0E9Ch
0x18005830e  jmp     short loc_180058291
0x180058310  mov     ebx, 0C000000Dh
0x180058315  mov     r9d, 0E6Ah
0x18005831b  mov     ecx, 0C000000Dh
0x180058320  jmp     loc_1800581EE
0x180058325  mov     ebx, 0C000000Dh
0x18005832a  mov     r9d, 0EA3h
0x180058330  mov     ecx, 0C000000Dh
0x180058335  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005833c  lea     rdx, aStatus; "Status"
0x180058343  call    DebugTraceError
0x180058348  test    rdi, rdi
0x18005834b  jz      short loc_180058355
0x18005834d  mov     rcx, rdi; hAlgorithm
0x180058350  call    CachedCloseAlgorithmProvider
0x180058355  mov     eax, ebx
0x180058357  add     rsp, 68h
0x18005835b  pop     r15
0x18005835d  pop     r14
0x18005835f  pop     r13
0x180058361  pop     r12
0x180058363  pop     rdi
0x180058364  pop     rsi
0x180058365  pop     rbx
0x180058366  pop     rbp
0x180058367  retn
```
