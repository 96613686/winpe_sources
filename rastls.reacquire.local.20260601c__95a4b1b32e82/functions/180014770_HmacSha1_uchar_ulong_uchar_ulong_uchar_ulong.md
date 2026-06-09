# HmacSha1(uchar *,ulong,uchar *,ulong,uchar *,ulong)

- ea: `0x180014770`
- end: `0x180014a5e`
- name: `?HmacSha1@@YAKPEAEK0K0K@Z`
- size: `750`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, __int64, PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180013eb0`
- `0x180014510`
- `0x1800602c4`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180014770`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014877`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014877`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a36`
- `bcrypt!BCryptCreateHash` at `0x18001495e`
- `bcrypt!BCryptCreateHash` at `0x18001495e`
- `bcrypt!BCryptHashData` at `0x180014995`
- `bcrypt!BCryptHashData` at `0x180014995`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180014a0c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180014a0c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800147ea`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800147ea`
- `bcrypt!BCryptFinishHash` at `0x1800149ca`
- `bcrypt!BCryptFinishHash` at `0x1800149ca`
- `bcrypt!BCryptDestroyHash` at `0x180014a22`
- `bcrypt!BCryptDestroyHash` at `0x180014a22`
- `bcrypt!BCryptGetProperty` at `0x18001483f`
- `bcrypt!BCryptGetProperty` at `0x1800148db`
- `bcrypt!BCryptGetProperty` at `0x18001483f`
- `bcrypt!BCryptGetProperty` at `0x1800148db`

## pseudocode

```c
__int64 __fastcall HmacSha1(
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbOutput,
        __int64 a4,
        PUCHAR pbSecret,
        ULONG cbSecret)
{
  UCHAR *v7; // rbx
  NTSTATUS Property; // eax
  unsigned int v11; // edi
  struct _EAPTLS_CONTROL_BLOCK *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  UCHAR v16[4]; // [rsp+40h] [rbp-48h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-44h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-40h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-38h] BYREF
  ULONG pbOutputa; // [rsp+A8h] [rbp+20h] BYREF

  pcbResult = 0;
  v7 = 0;
  *(_DWORD *)v16 = 0;
  pbOutputa = 0;
  phHash = 0;
  phAlgorithm = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", 0, 8u);
  v11 = Property;
  if ( Property < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v13 = 78;
    goto LABEL_27;
  }
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutputa, 4u, &pcbResult, 0);
  v11 = Property;
  if ( Property < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v13 = 79;
    goto LABEL_27;
  }
  v7 = (UCHAR *)LocalAlloc(0x40u, pbOutputa);
  if ( v7 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v16, 4u, &pcbResult, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_29;
      v13 = 81;
      goto LABEL_27;
    }
    v14 = *(unsigned int *)v16;
    if ( *(_DWORD *)v16 != 20 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_29;
      v13 = 82;
      goto LABEL_28;
    }
    Property = BCryptCreateHash(phAlgorithm, &phHash, v7, pbOutputa, pbSecret, cbSecret, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_29;
      v13 = 83;
      goto LABEL_27;
    }
    Property = BCryptHashData(phHash, pbInput, cbInput, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_29;
      v13 = 84;
      goto LABEL_27;
    }
    Property = BCryptFinishHash(phHash, pbOutput, *(ULONG *)v16, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v13 = 85;
LABEL_27:
        v14 = (unsigned int)Property;
LABEL_28:
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids, v14);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids);
  }
LABEL_29:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v7 )
    LocalFree(v7);
  return v11;
}

```

## disassembly

```asm
0x180014770  mov     rax, rsp
0x180014773  mov     [rax+8], rbx
0x180014777  mov     [rax+10h], rbp
0x18001477b  mov     [rax+20h], r9d
0x18001477f  push    rsi
0x180014780  push    rdi
0x180014781  push    r12
0x180014783  push    r14
0x180014785  push    r15
0x180014787  sub     rsp, 60h
0x18001478b  xor     r15d, r15d
0x18001478e  mov     rsi, r8
0x180014791  mov     [rax-44h], r15d
0x180014795  mov     ebx, r15d
0x180014798  mov     [rax-48h], r15d
0x18001479c  mov     ebp, edx
0x18001479e  mov     [rax+20h], r15d
0x1800147a2  mov     r14, rcx
0x1800147a5  mov     [rax-38h], r15
0x1800147a9  mov     [rax-40h], r15
0x1800147ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147b4  lea     r12, WPP_GLOBAL_Control
0x1800147bb  cmp     rcx, r12
0x1800147be  jz      short loc_1800147D5
0x1800147c0  mov     rcx, [rcx+10h]
0x1800147c4  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x1800147cb  mov     edx, 4Dh ; 'M'
0x1800147d0  call    WPP_SF_
0x1800147d5  mov     r9d, 8; dwFlags
0x1800147db  lea     rdx, pszAlgId; "SHA1"
0x1800147e2  xor     r8d, r8d; pszImplementation
0x1800147e5  lea     rcx, [rsp+88h+phAlgorithm]; phAlgorithm
0x1800147ea  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800147f1  nop     dword ptr [rax+rax+00h]
0x1800147f6  mov     edi, eax
0x1800147f8  test    eax, eax
0x1800147fa  jns     short loc_180014816
0x1800147fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180014803  cmp     rcx, r12
0x180014806  jz      loc_180014A00
0x18001480c  mov     edx, 4Eh ; 'N'
0x180014811  jmp     loc_1800149ED
0x180014816  mov     rcx, [rsp+88h+phAlgorithm]; hObject
0x18001481b  lea     rax, [rsp+88h+var_44]
0x180014820  mov     [rsp+88h+dwFlags], r15d; dwFlags
0x180014825  lea     r8, [rsp+88h+pbOutput]; pbOutput
0x18001482d  mov     r9d, 4; cbOutput
0x180014833  mov     [rsp+88h+pcbResult], rax; pcbResult
0x180014838  lea     rdx, pszProperty; "ObjectLength"
0x18001483f  call    cs:__imp_BCryptGetProperty
0x180014846  nop     dword ptr [rax+rax+00h]
0x18001484b  mov     edi, eax
0x18001484d  test    eax, eax
0x18001484f  jns     short loc_18001486B
0x180014851  mov     rcx, cs:WPP_GLOBAL_Control
0x180014858  cmp     rcx, r12
0x18001485b  jz      loc_180014A00
0x180014861  mov     edx, 4Fh ; 'O'
0x180014866  jmp     loc_1800149ED
0x18001486b  mov     edx, [rsp+88h+pbOutput]; uBytes
0x180014872  mov     ecx, 40h ; '@'; uFlags
0x180014877  call    cs:__imp_LocalAlloc
0x18001487e  nop     dword ptr [rax+rax+00h]
0x180014883  mov     rbx, rax
0x180014886  test    rax, rax
0x180014889  jnz     short loc_1800148B5
0x18001488b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014892  cmp     rcx, r12
0x180014895  jz      loc_180014A00
0x18001489b  mov     rcx, [rcx+10h]
0x18001489f  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x1800148a6  mov     edx, 50h ; 'P'
0x1800148ab  call    WPP_SF_
0x1800148b0  jmp     loc_180014A00
0x1800148b5  mov     rcx, [rsp+88h+phAlgorithm]; hObject
0x1800148ba  lea     rax, [rsp+88h+var_44]
0x1800148bf  mov     [rsp+88h+dwFlags], r15d; dwFlags
0x1800148c4  lea     r8, [rsp+88h+var_48]; pbOutput
0x1800148c9  mov     r9d, 4; cbOutput
0x1800148cf  mov     [rsp+88h+pcbResult], rax; pcbResult
0x1800148d4  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800148db  call    cs:__imp_BCryptGetProperty
0x1800148e2  nop     dword ptr [rax+rax+00h]
0x1800148e7  mov     edi, eax
0x1800148e9  test    eax, eax
0x1800148eb  jns     short loc_180014907
0x1800148ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800148f4  cmp     rcx, r12
0x1800148f7  jz      loc_180014A00
0x1800148fd  mov     edx, 51h ; 'Q'
0x180014902  jmp     loc_1800149ED
0x180014907  mov     r9d, dword ptr [rsp+88h+var_48]
0x18001490c  cmp     r9d, 14h
0x180014910  jz      short loc_18001492C
0x180014912  mov     rcx, cs:WPP_GLOBAL_Control
0x180014919  cmp     rcx, r12
0x18001491c  jz      loc_180014A00
0x180014922  mov     edx, 52h ; 'R'
0x180014927  jmp     loc_1800149F0
0x18001492c  mov     eax, [rsp+88h+cbSecret]
0x180014933  lea     rdx, [rsp+88h+phHash]; phHash
0x180014938  mov     r9d, [rsp+88h+pbOutput]; cbHashObject
0x180014940  mov     r8, rbx; pbHashObject
0x180014943  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x180014948  mov     [rsp+88h+var_58], r15d; dwFlags
0x18001494d  mov     [rsp+88h+dwFlags], eax; cbSecret
0x180014951  mov     rax, [rsp+88h+pbSecret]
0x180014959  mov     [rsp+88h+pcbResult], rax; pbSecret
0x18001495e  call    cs:__imp_BCryptCreateHash
0x180014965  nop     dword ptr [rax+rax+00h]
0x18001496a  mov     edi, eax
0x18001496c  test    eax, eax
0x18001496e  jns     short loc_180014987
0x180014970  mov     rcx, cs:WPP_GLOBAL_Control
0x180014977  cmp     rcx, r12
0x18001497a  jz      loc_180014A00
0x180014980  mov     edx, 53h ; 'S'
0x180014985  jmp     short loc_1800149ED
0x180014987  mov     rcx, [rsp+88h+phHash]; hHash
0x18001498c  xor     r9d, r9d; dwFlags
0x18001498f  mov     r8d, ebp; cbInput
0x180014992  mov     rdx, r14; pbInput
0x180014995  call    cs:__imp_BCryptHashData
0x18001499c  nop     dword ptr [rax+rax+00h]
0x1800149a1  mov     edi, eax
0x1800149a3  test    eax, eax
0x1800149a5  jns     short loc_1800149BA
0x1800149a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149ae  cmp     rcx, r12
0x1800149b1  jz      short loc_180014A00
0x1800149b3  mov     edx, 54h ; 'T'
0x1800149b8  jmp     short loc_1800149ED
0x1800149ba  mov     r8d, dword ptr [rsp+88h+var_48]; cbOutput
0x1800149bf  xor     r9d, r9d; dwFlags
0x1800149c2  mov     rcx, [rsp+88h+phHash]; hHash
0x1800149c7  mov     rdx, rsi; pbOutput
0x1800149ca  call    cs:__imp_BCryptFinishHash
0x1800149d1  nop     dword ptr [rax+rax+00h]
0x1800149d6  mov     edi, eax
0x1800149d8  test    eax, eax
0x1800149da  jns     short loc_180014A00
0x1800149dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149e3  cmp     rcx, r12
0x1800149e6  jz      short loc_180014A00
0x1800149e8  mov     edx, 55h ; 'U'
0x1800149ed  mov     r9d, eax
0x1800149f0  mov     rcx, [rcx+10h]
0x1800149f4  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x1800149fb  call    WPP_SF_d
0x180014a00  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x180014a05  test    rcx, rcx
0x180014a08  jz      short loc_180014A18
0x180014a0a  xor     edx, edx; dwFlags
0x180014a0c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180014a13  nop     dword ptr [rax+rax+00h]
0x180014a18  mov     rcx, [rsp+88h+phHash]; hHash
0x180014a1d  test    rcx, rcx
0x180014a20  jz      short loc_180014A2E
0x180014a22  call    cs:__imp_BCryptDestroyHash
0x180014a29  nop     dword ptr [rax+rax+00h]
0x180014a2e  test    rbx, rbx
0x180014a31  jz      short loc_180014A42
0x180014a33  mov     rcx, rbx; hMem
0x180014a36  call    cs:__imp_LocalFree
0x180014a3d  nop     dword ptr [rax+rax+00h]
0x180014a42  lea     r11, [rsp+88h+var_28]
0x180014a47  mov     eax, edi
0x180014a49  mov     rbx, [r11+30h]
0x180014a4d  mov     rbp, [r11+38h]
0x180014a51  mov     rsp, r11
0x180014a54  pop     r15
0x180014a56  pop     r14
0x180014a58  pop     r12
0x180014a5a  pop     rdi
0x180014a5b  pop     rsi
0x180014a5c  retn
```
