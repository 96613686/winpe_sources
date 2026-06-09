# HmacSha1(uchar *,ulong,uchar *,ulong,uchar *,ulong)

- ea: `0x180013430`
- end: `0x1800136dd`
- name: `?HmacSha1@@YAKPEAEK0K0K@Z`
- size: `685`
- prototype: `unsigned int __usercall@<eax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbOutput@<r8>, unsigned int@<r9d>, PUCHAR pbSecret, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180012bd0`
- `0x1800131f0`
- `0x18005cc50`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180013430`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001352b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001352b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136bc`
- `bcrypt!BCryptCreateHash` at `0x180013606`
- `bcrypt!BCryptCreateHash` at `0x180013606`
- `bcrypt!BCryptHashData` at `0x180013633`
- `bcrypt!BCryptHashData` at `0x180013633`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001369e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001369e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800134aa`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800134aa`
- `bcrypt!BCryptFinishHash` at `0x180013662`
- `bcrypt!BCryptFinishHash` at `0x180013662`
- `bcrypt!BCryptDestroyHash` at `0x1800136ae`
- `bcrypt!BCryptDestroyHash` at `0x1800136ae`
- `bcrypt!BCryptGetProperty` at `0x1800134f9`
- `bcrypt!BCryptGetProperty` at `0x180013589`
- `bcrypt!BCryptGetProperty` at `0x1800134f9`
- `bcrypt!BCryptGetProperty` at `0x180013589`

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
0x180013430  mov     rax, rsp
0x180013433  mov     [rax+8], rbx
0x180013437  mov     [rax+10h], rbp
0x18001343b  mov     [rax+20h], r9d
0x18001343f  push    rsi
0x180013440  push    rdi
0x180013441  push    r12
0x180013443  push    r14
0x180013445  push    r15
0x180013447  sub     rsp, 60h
0x18001344b  xor     r15d, r15d
0x18001344e  mov     rsi, r8
0x180013451  mov     [rax-44h], r15d
0x180013455  mov     ebx, r15d
0x180013458  mov     [rax-48h], r15d
0x18001345c  mov     ebp, edx
0x18001345e  mov     [rax+20h], r15d
0x180013462  mov     r14, rcx
0x180013465  mov     [rax-38h], r15
0x180013469  mov     [rax-40h], r15
0x18001346d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013474  lea     r12, WPP_GLOBAL_Control
0x18001347b  cmp     rcx, r12
0x18001347e  jz      short loc_180013495
0x180013480  mov     rcx, [rcx+10h]
0x180013484  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001348b  mov     edx, 4Dh ; 'M'
0x180013490  call    WPP_SF_
0x180013495  mov     r9d, 8; dwFlags
0x18001349b  lea     rdx, pszAlgId; "SHA1"
0x1800134a2  xor     r8d, r8d; pszImplementation
0x1800134a5  lea     rcx, [rsp+88h+phAlgorithm]; phAlgorithm
0x1800134aa  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800134b0  mov     edi, eax
0x1800134b2  test    eax, eax
0x1800134b4  jns     short loc_1800134D0
0x1800134b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134bd  cmp     rcx, r12
0x1800134c0  jz      loc_180013692
0x1800134c6  mov     edx, 4Eh ; 'N'
0x1800134cb  jmp     loc_18001367F
0x1800134d0  mov     rcx, [rsp+88h+phAlgorithm]; hObject
0x1800134d5  lea     rax, [rsp+88h+var_44]
0x1800134da  mov     [rsp+88h+dwFlags], r15d; dwFlags
0x1800134df  lea     r8, [rsp+88h+pbOutput]; pbOutput
0x1800134e7  mov     r9d, 4; cbOutput
0x1800134ed  mov     [rsp+88h+pcbResult], rax; pcbResult
0x1800134f2  lea     rdx, pszProperty; "ObjectLength"
0x1800134f9  call    cs:__imp_BCryptGetProperty
0x1800134ff  mov     edi, eax
0x180013501  test    eax, eax
0x180013503  jns     short loc_18001351F
0x180013505  mov     rcx, cs:WPP_GLOBAL_Control
0x18001350c  cmp     rcx, r12
0x18001350f  jz      loc_180013692
0x180013515  mov     edx, 4Fh ; 'O'
0x18001351a  jmp     loc_18001367F
0x18001351f  mov     edx, [rsp+88h+pbOutput]; uBytes
0x180013526  mov     ecx, 40h ; '@'; uFlags
0x18001352b  call    cs:__imp_LocalAlloc
0x180013531  mov     rbx, rax
0x180013534  test    rax, rax
0x180013537  jnz     short loc_180013563
0x180013539  mov     rcx, cs:WPP_GLOBAL_Control
0x180013540  cmp     rcx, r12
0x180013543  jz      loc_180013692
0x180013549  mov     rcx, [rcx+10h]
0x18001354d  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x180013554  mov     edx, 50h ; 'P'
0x180013559  call    WPP_SF_
0x18001355e  jmp     loc_180013692
0x180013563  mov     rcx, [rsp+88h+phAlgorithm]; hObject
0x180013568  lea     rax, [rsp+88h+var_44]
0x18001356d  mov     [rsp+88h+dwFlags], r15d; dwFlags
0x180013572  lea     r8, [rsp+88h+var_48]; pbOutput
0x180013577  mov     r9d, 4; cbOutput
0x18001357d  mov     [rsp+88h+pcbResult], rax; pcbResult
0x180013582  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180013589  call    cs:__imp_BCryptGetProperty
0x18001358f  mov     edi, eax
0x180013591  test    eax, eax
0x180013593  jns     short loc_1800135AF
0x180013595  mov     rcx, cs:WPP_GLOBAL_Control
0x18001359c  cmp     rcx, r12
0x18001359f  jz      loc_180013692
0x1800135a5  mov     edx, 51h ; 'Q'
0x1800135aa  jmp     loc_18001367F
0x1800135af  mov     r9d, dword ptr [rsp+88h+var_48]
0x1800135b4  cmp     r9d, 14h
0x1800135b8  jz      short loc_1800135D4
0x1800135ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800135c1  cmp     rcx, r12
0x1800135c4  jz      loc_180013692
0x1800135ca  mov     edx, 52h ; 'R'
0x1800135cf  jmp     loc_180013682
0x1800135d4  mov     eax, [rsp+88h+cbSecret]
0x1800135db  lea     rdx, [rsp+88h+phHash]; phHash
0x1800135e0  mov     r9d, [rsp+88h+pbOutput]; cbHashObject
0x1800135e8  mov     r8, rbx; pbHashObject
0x1800135eb  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x1800135f0  mov     [rsp+88h+var_58], r15d; dwFlags
0x1800135f5  mov     [rsp+88h+dwFlags], eax; cbSecret
0x1800135f9  mov     rax, [rsp+88h+pbSecret]
0x180013601  mov     [rsp+88h+pcbResult], rax; pbSecret
0x180013606  call    cs:__imp_BCryptCreateHash
0x18001360c  mov     edi, eax
0x18001360e  test    eax, eax
0x180013610  jns     short loc_180013625
0x180013612  mov     rcx, cs:WPP_GLOBAL_Control
0x180013619  cmp     rcx, r12
0x18001361c  jz      short loc_180013692
0x18001361e  mov     edx, 53h ; 'S'
0x180013623  jmp     short loc_18001367F
0x180013625  mov     rcx, [rsp+88h+phHash]; hHash
0x18001362a  xor     r9d, r9d; dwFlags
0x18001362d  mov     r8d, ebp; cbInput
0x180013630  mov     rdx, r14; pbInput
0x180013633  call    cs:__imp_BCryptHashData
0x180013639  mov     edi, eax
0x18001363b  test    eax, eax
0x18001363d  jns     short loc_180013652
0x18001363f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013646  cmp     rcx, r12
0x180013649  jz      short loc_180013692
0x18001364b  mov     edx, 54h ; 'T'
0x180013650  jmp     short loc_18001367F
0x180013652  mov     r8d, dword ptr [rsp+88h+var_48]; cbOutput
0x180013657  xor     r9d, r9d; dwFlags
0x18001365a  mov     rcx, [rsp+88h+phHash]; hHash
0x18001365f  mov     rdx, rsi; pbOutput
0x180013662  call    cs:__imp_BCryptFinishHash
0x180013668  mov     edi, eax
0x18001366a  test    eax, eax
0x18001366c  jns     short loc_180013692
0x18001366e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013675  cmp     rcx, r12
0x180013678  jz      short loc_180013692
0x18001367a  mov     edx, 55h ; 'U'
0x18001367f  mov     r9d, eax
0x180013682  mov     rcx, [rcx+10h]
0x180013686  lea     r8, WPP_a6a00b25ce0d3c50e563a1584b1c9ee6_Traceguids
0x18001368d  call    WPP_SF_d
0x180013692  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x180013697  test    rcx, rcx
0x18001369a  jz      short loc_1800136A4
0x18001369c  xor     edx, edx; dwFlags
0x18001369e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800136a4  mov     rcx, [rsp+88h+phHash]; hHash
0x1800136a9  test    rcx, rcx
0x1800136ac  jz      short loc_1800136B4
0x1800136ae  call    cs:__imp_BCryptDestroyHash
0x1800136b4  test    rbx, rbx
0x1800136b7  jz      short loc_1800136C2
0x1800136b9  mov     rcx, rbx; hMem
0x1800136bc  call    cs:__imp_LocalFree
0x1800136c2  lea     r11, [rsp+88h+var_28]
0x1800136c7  mov     eax, edi
0x1800136c9  mov     rbx, [r11+30h]
0x1800136cd  mov     rbp, [r11+38h]
0x1800136d1  mov     rsp, r11
0x1800136d4  pop     r15
0x1800136d6  pop     r14
0x1800136d8  pop     r12
0x1800136da  pop     rdi
0x1800136db  pop     rsi
0x1800136dc  retn
```
