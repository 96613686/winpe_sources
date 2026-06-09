# ApplyEncryptionPadding

- ea: `0x1800619c0`
- end: `0x180061c49`
- name: `ApplyEncryptionPadding`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800112d0`

## callees

- `0x18000d440`
- `0x18000dd90`
- `0x18001155c`
- `0x180053184`
- `0x1800619c0`
- `0x180071b30`
- `0x180071bd8`
- `0x1800a45c0`

## string_xrefs

- `0x180061ad5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180061b1f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180061c15`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x1800619c0  push    rbp
0x1800619c2  push    rbx
0x1800619c3  push    rsi
0x1800619c4  push    rdi
0x1800619c5  push    r12
0x1800619c7  push    r13
0x1800619c9  push    r14
0x1800619cb  push    r15
0x1800619cd  mov     rbp, rsp
0x1800619d0  sub     rsp, 68h
0x1800619d4  xor     r12d, r12d
0x1800619d7  mov     r15d, r9d
0x1800619da  mov     [rbp+hObject], r12
0x1800619de  mov     r13, r8
0x1800619e1  mov     dword ptr [rbp+pbOutput], r12d
0x1800619e5  mov     rsi, rdx
0x1800619e8  mov     dword ptr [rbp+var_14], r12d
0x1800619ec  mov     edi, r12d
0x1800619ef  mov     [rbp+arg_0], r12d
0x1800619f3  test    cl, 2
0x1800619f6  jz      loc_180061AE6
0x1800619fc  lea     eax, [r15+3]
0x180061a00  cmp     eax, r15d
0x180061a03  jb      loc_180061AB7
0x180061a09  mov     r8d, [rbp+arg_28]
0x180061a0d  cmp     r8d, eax
0x180061a10  jb      loc_180061AAF
0x180061a16  mov     r14, [rbp+arg_20]
0x180061a1a  lea     r9d, [r12+2]; dwFlags
0x180061a1f  sub     r8d, eax; cbBuffer
0x180061a22  xor     ecx, ecx; hAlgorithm
0x180061a24  mov     [rbp+arg_0], r8d
0x180061a28  lea     rdx, [r14+2]; pbBuffer
0x180061a2c  mov     word ptr [r14], 200h
0x180061a32  call    BCryptGenRandom
0x180061a37  mov     ebx, eax
0x180061a39  test    eax, eax
0x180061a3b  jns     short loc_180061A4A
0x180061a3d  mov     r9d, 0E4Bh
0x180061a43  mov     ecx, eax
0x180061a45  jmp     loc_180061ACE
0x180061a4a  mov     esi, r12d
0x180061a4d  mov     eax, [rbp+arg_0]
0x180061a50  cmp     esi, eax
0x180061a52  jnb     short loc_180061A88
0x180061a54  lea     r12d, [rsi+2]
0x180061a58  cmp     [r12+r14], dil
0x180061a5c  jnz     short loc_180061A84
0x180061a5e  xor     ecx, ecx; hAlgorithm
0x180061a60  mov     edx, esi
0x180061a62  add     rdx, 2
0x180061a66  add     rdx, r14; pbBuffer
0x180061a69  lea     r9d, [rcx+2]; dwFlags
0x180061a6d  lea     r8d, [rcx+1]; cbBuffer
0x180061a71  call    BCryptGenRandom
0x180061a76  mov     ebx, eax
0x180061a78  test    eax, eax
0x180061a7a  jns     short loc_180061A58
0x180061a7c  mov     r9d, 0E59h
0x180061a82  jmp     short loc_180061A43
0x180061a84  inc     esi
0x180061a86  jmp     short loc_180061A4D
0x180061a88  add     eax, 2
0x180061a8b  xor     r12d, r12d
0x180061a8e  mov     r8, r15; Size
0x180061a91  mov     rdx, r13; Src
0x180061a94  mov     [rax+r14], r12b
0x180061a98  mov     ecx, [rbp+arg_0]
0x180061a9b  add     rcx, 3
0x180061a9f  add     rcx, r14; void *
0x180061aa2  call    memmove
0x180061aa7  mov     ebx, r12d
0x180061aaa  jmp     loc_180061C28
0x180061aaf  mov     r9d, 0E3Eh
0x180061ab5  jmp     short loc_180061ABD
0x180061ab7  mov     r9d, 0E39h
0x180061abd  mov     ebx, 80070216h
0x180061ac2  mov     [rbp+arg_0], 0FFFFFFFFh
0x180061ac9  mov     ecx, 80070216h
0x180061ace  lea     rdx, aStatus; "Status"
0x180061ad5  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180061adc  call    DebugTraceError
0x180061ae1  jmp     loc_180061C35
0x180061ae6  mov     r14d, 4
0x180061aec  test    r14b, cl
0x180061aef  jz      loc_180061C05
0x180061af5  test    rsi, rsi
0x180061af8  jz      loc_180061BF0
0x180061afe  mov     rdx, [rdx]
0x180061b01  test    rdx, rdx
0x180061b04  jz      loc_180061BF0
0x180061b0a  lea     rcx, [rbp+hObject]
0x180061b0e  call    CachedOpenAlgorithmProvider
0x180061b13  mov     ebx, eax
0x180061b15  test    eax, eax
0x180061b17  jns     short loc_180061B3D
0x180061b19  mov     r9d, 0E75h
0x180061b1f  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180061b26  lea     rdx, aStatus; "Status"
0x180061b2d  mov     ecx, eax
0x180061b2f  call    DebugTraceError
0x180061b34  mov     rdi, [rbp+hObject]
0x180061b38  jmp     loc_180061C28
0x180061b3d  mov     rdi, [rbp+hObject]
0x180061b41  lea     rax, [rbp+arg_0]
0x180061b45  mov     rcx, rdi; hObject
0x180061b48  mov     dword ptr [rsp+68h+dwFlags], r12d; dwFlags
0x180061b4d  mov     r9d, r14d; cbOutput
0x180061b50  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180061b55  lea     r8, [rbp+pbOutput]; pbOutput
0x180061b59  lea     rdx, aObjectlength; "ObjectLength"
0x180061b60  call    BCryptGetProperty
0x180061b65  mov     ebx, eax
0x180061b67  test    eax, eax
0x180061b69  jns     short loc_180061B78
0x180061b6b  mov     r9d, 0E81h
0x180061b71  mov     ecx, eax
0x180061b73  jmp     loc_180061C15
0x180061b78  lea     rax, [rbp+arg_0]
0x180061b7c  mov     dword ptr [rsp+68h+dwFlags], r12d; phHash
0x180061b81  mov     r9d, r14d; cbOutput
0x180061b84  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180061b89  lea     r8, [rbp+var_14]; pbOutput
0x180061b8d  mov     rcx, rdi; hObject
0x180061b90  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180061b97  call    BCryptGetProperty
0x180061b9c  mov     ebx, eax
0x180061b9e  test    eax, eax
0x180061ba0  jns     short loc_180061BAA
0x180061ba2  mov     r9d, 0E8Dh
0x180061ba8  jmp     short loc_180061B71
0x180061baa  mov     eax, [rbp+arg_28]
0x180061bad  mov     rcx, rdi; hAlgorithm
0x180061bb0  mov     r9, [rsi+8]
0x180061bb4  mov     r8d, dword ptr [rbp+pbOutput]; cbHashObject
0x180061bb8  mov     edx, dword ptr [rbp+var_14]; cbBuffer
0x180061bbb  mov     [rsp+68h+var_20], eax; int
0x180061bbf  mov     rax, [rbp+arg_20]
0x180061bc3  mov     [rsp+68h+var_28], rax; __int64
0x180061bc8  mov     eax, [rsi+10h]
0x180061bcb  mov     dword ptr [rsp+68h+Size], r15d; Size
0x180061bd0  mov     [rsp+68h+Src], r13; Src
0x180061bd5  mov     dword ptr [rsp+68h+pcbResult], eax; cbInput
0x180061bd9  call    ApplyOAEPPaddingSeeded
0x180061bde  mov     ebx, eax
0x180061be0  test    eax, eax
0x180061be2  jns     loc_180061AA7
0x180061be8  mov     r9d, 0E9Ch
0x180061bee  jmp     short loc_180061B71
0x180061bf0  mov     ebx, 0C000000Dh
0x180061bf5  mov     r9d, 0E6Ah
0x180061bfb  mov     ecx, 0C000000Dh
0x180061c00  jmp     loc_180061ACE
0x180061c05  mov     ebx, 0C000000Dh
0x180061c0a  mov     r9d, 0EA3h
0x180061c10  mov     ecx, 0C000000Dh
0x180061c15  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180061c1c  lea     rdx, aStatus; "Status"
0x180061c23  call    DebugTraceError
0x180061c28  test    rdi, rdi
0x180061c2b  jz      short loc_180061C35
0x180061c2d  mov     rcx, rdi; hAlgorithm
0x180061c30  call    CachedCloseAlgorithmProvider
0x180061c35  mov     eax, ebx
0x180061c37  add     rsp, 68h
0x180061c3b  pop     r15
0x180061c3d  pop     r14
0x180061c3f  pop     r13
0x180061c41  pop     r12
0x180061c43  pop     rdi
0x180061c44  pop     rsi
0x180061c45  pop     rbx
0x180061c46  pop     rbp
0x180061c47  retn
```
