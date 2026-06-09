# ApplyEncryptionPadding

- ea: `0x1800577f0`
- end: `0x180057a79`
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
- `0x180049084`
- `0x1800577f0`
- `0x180067990`
- `0x180067a38`
- `0x18009da40`

## string_xrefs

- `0x180057905`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005794f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180057a45`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x1800577f0  push    rbp
0x1800577f2  push    rbx
0x1800577f3  push    rsi
0x1800577f4  push    rdi
0x1800577f5  push    r12
0x1800577f7  push    r13
0x1800577f9  push    r14
0x1800577fb  push    r15
0x1800577fd  mov     rbp, rsp
0x180057800  sub     rsp, 68h
0x180057804  xor     r12d, r12d
0x180057807  mov     r15d, r9d
0x18005780a  mov     [rbp+hObject], r12
0x18005780e  mov     r13, r8
0x180057811  mov     dword ptr [rbp+pbOutput], r12d
0x180057815  mov     rsi, rdx
0x180057818  mov     dword ptr [rbp+var_14], r12d
0x18005781c  mov     edi, r12d
0x18005781f  mov     [rbp+arg_0], r12d
0x180057823  test    cl, 2
0x180057826  jz      loc_180057916
0x18005782c  lea     eax, [r15+3]
0x180057830  cmp     eax, r15d
0x180057833  jb      loc_1800578E7
0x180057839  mov     r8d, [rbp+arg_28]
0x18005783d  cmp     r8d, eax
0x180057840  jb      loc_1800578DF
0x180057846  mov     r14, [rbp+arg_20]
0x18005784a  lea     r9d, [r12+2]; dwFlags
0x18005784f  sub     r8d, eax; cbBuffer
0x180057852  xor     ecx, ecx; hAlgorithm
0x180057854  mov     [rbp+arg_0], r8d
0x180057858  lea     rdx, [r14+2]; pbBuffer
0x18005785c  mov     word ptr [r14], 200h
0x180057862  call    BCryptGenRandom
0x180057867  mov     ebx, eax
0x180057869  test    eax, eax
0x18005786b  jns     short loc_18005787A
0x18005786d  mov     r9d, 0E4Bh
0x180057873  mov     ecx, eax
0x180057875  jmp     loc_1800578FE
0x18005787a  mov     esi, r12d
0x18005787d  mov     eax, [rbp+arg_0]
0x180057880  cmp     esi, eax
0x180057882  jnb     short loc_1800578B8
0x180057884  lea     r12d, [rsi+2]
0x180057888  cmp     [r12+r14], dil
0x18005788c  jnz     short loc_1800578B4
0x18005788e  xor     ecx, ecx; hAlgorithm
0x180057890  mov     edx, esi
0x180057892  add     rdx, 2
0x180057896  add     rdx, r14; pbBuffer
0x180057899  lea     r9d, [rcx+2]; dwFlags
0x18005789d  lea     r8d, [rcx+1]; cbBuffer
0x1800578a1  call    BCryptGenRandom
0x1800578a6  mov     ebx, eax
0x1800578a8  test    eax, eax
0x1800578aa  jns     short loc_180057888
0x1800578ac  mov     r9d, 0E59h
0x1800578b2  jmp     short loc_180057873
0x1800578b4  inc     esi
0x1800578b6  jmp     short loc_18005787D
0x1800578b8  add     eax, 2
0x1800578bb  xor     r12d, r12d
0x1800578be  mov     r8, r15; Size
0x1800578c1  mov     rdx, r13; Src
0x1800578c4  mov     [rax+r14], r12b
0x1800578c8  mov     ecx, [rbp+arg_0]
0x1800578cb  add     rcx, 3
0x1800578cf  add     rcx, r14; void *
0x1800578d2  call    memmove
0x1800578d7  mov     ebx, r12d
0x1800578da  jmp     loc_180057A58
0x1800578df  mov     r9d, 0E3Eh
0x1800578e5  jmp     short loc_1800578ED
0x1800578e7  mov     r9d, 0E39h
0x1800578ed  mov     ebx, 80070216h
0x1800578f2  mov     [rbp+arg_0], 0FFFFFFFFh
0x1800578f9  mov     ecx, 80070216h
0x1800578fe  lea     rdx, aStatus; "Status"
0x180057905  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005790c  call    DebugTraceError
0x180057911  jmp     loc_180057A65
0x180057916  mov     r14d, 4
0x18005791c  test    r14b, cl
0x18005791f  jz      loc_180057A35
0x180057925  test    rsi, rsi
0x180057928  jz      loc_180057A20
0x18005792e  mov     rdx, [rdx]
0x180057931  test    rdx, rdx
0x180057934  jz      loc_180057A20
0x18005793a  lea     rcx, [rbp+hObject]
0x18005793e  call    CachedOpenAlgorithmProvider
0x180057943  mov     ebx, eax
0x180057945  test    eax, eax
0x180057947  jns     short loc_18005796D
0x180057949  mov     r9d, 0E75h
0x18005794f  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180057956  lea     rdx, aStatus; "Status"
0x18005795d  mov     ecx, eax
0x18005795f  call    DebugTraceError
0x180057964  mov     rdi, [rbp+hObject]
0x180057968  jmp     loc_180057A58
0x18005796d  mov     rdi, [rbp+hObject]
0x180057971  lea     rax, [rbp+arg_0]
0x180057975  mov     rcx, rdi; hObject
0x180057978  mov     dword ptr [rsp+68h+dwFlags], r12d; dwFlags
0x18005797d  mov     r9d, r14d; cbOutput
0x180057980  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180057985  lea     r8, [rbp+pbOutput]; pbOutput
0x180057989  lea     rdx, aObjectlength; "ObjectLength"
0x180057990  call    BCryptGetProperty
0x180057995  mov     ebx, eax
0x180057997  test    eax, eax
0x180057999  jns     short loc_1800579A8
0x18005799b  mov     r9d, 0E81h
0x1800579a1  mov     ecx, eax
0x1800579a3  jmp     loc_180057A45
0x1800579a8  lea     rax, [rbp+arg_0]
0x1800579ac  mov     dword ptr [rsp+68h+dwFlags], r12d; phHash
0x1800579b1  mov     r9d, r14d; cbOutput
0x1800579b4  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1800579b9  lea     r8, [rbp+var_14]; pbOutput
0x1800579bd  mov     rcx, rdi; hObject
0x1800579c0  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800579c7  call    BCryptGetProperty
0x1800579cc  mov     ebx, eax
0x1800579ce  test    eax, eax
0x1800579d0  jns     short loc_1800579DA
0x1800579d2  mov     r9d, 0E8Dh
0x1800579d8  jmp     short loc_1800579A1
0x1800579da  mov     eax, [rbp+arg_28]
0x1800579dd  mov     rcx, rdi; hAlgorithm
0x1800579e0  mov     r9, [rsi+8]
0x1800579e4  mov     r8d, dword ptr [rbp+pbOutput]; cbHashObject
0x1800579e8  mov     edx, dword ptr [rbp+var_14]; cbBuffer
0x1800579eb  mov     [rsp+68h+var_20], eax; int
0x1800579ef  mov     rax, [rbp+arg_20]
0x1800579f3  mov     [rsp+68h+var_28], rax; __int64
0x1800579f8  mov     eax, [rsi+10h]
0x1800579fb  mov     dword ptr [rsp+68h+Size], r15d; Size
0x180057a00  mov     [rsp+68h+Src], r13; Src
0x180057a05  mov     dword ptr [rsp+68h+pcbResult], eax; cbInput
0x180057a09  call    ApplyOAEPPaddingSeeded
0x180057a0e  mov     ebx, eax
0x180057a10  test    eax, eax
0x180057a12  jns     loc_1800578D7
0x180057a18  mov     r9d, 0E9Ch
0x180057a1e  jmp     short loc_1800579A1
0x180057a20  mov     ebx, 0C000000Dh
0x180057a25  mov     r9d, 0E6Ah
0x180057a2b  mov     ecx, 0C000000Dh
0x180057a30  jmp     loc_1800578FE
0x180057a35  mov     ebx, 0C000000Dh
0x180057a3a  mov     r9d, 0EA3h
0x180057a40  mov     ecx, 0C000000Dh
0x180057a45  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180057a4c  lea     rdx, aStatus; "Status"
0x180057a53  call    DebugTraceError
0x180057a58  test    rdi, rdi
0x180057a5b  jz      short loc_180057A65
0x180057a5d  mov     rcx, rdi; hAlgorithm
0x180057a60  call    CachedCloseAlgorithmProvider
0x180057a65  mov     eax, ebx
0x180057a67  add     rsp, 68h
0x180057a6b  pop     r15
0x180057a6d  pop     r14
0x180057a6f  pop     r13
0x180057a71  pop     r12
0x180057a73  pop     rdi
0x180057a74  pop     rsi
0x180057a75  pop     rbx
0x180057a76  pop     rbp
0x180057a77  retn
```
