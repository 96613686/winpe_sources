# KerbAddPacRequestPreAuth(KERB_KDC_REQUEST_preauth_data_s * *,ulong)

- ea: `0x18001e268`
- end: `0x18001e566`
- name: `?KerbAddPacRequestPreAuth@@YAJPEAPEAUKERB_KDC_REQUEST_preauth_data_s@@K@Z`
- size: `766`
- prototype: `__int64 __fastcall(struct KERB_KDC_REQUEST_preauth_data_s **, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180019678`

## callees

- `0x18001e268`
- `0x18001e570`
- `0x18006ccec`
- `0x18007108c`
- `0x1800744cf`
- `0x180077804`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e2cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e4b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e2cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e4b9`
- `MSASN1!ASN1_CreateModule` at `0x18001e363`
- `MSASN1!ASN1_CreateModule` at `0x18001e363`
- `MSASN1!ASN1_CreateEncoder` at `0x18001e38a`
- `MSASN1!ASN1_CreateEncoder` at `0x18001e38a`
- `MSASN1!ASN1_FreeEncoded` at `0x18001e42e`
- `MSASN1!ASN1_FreeEncoded` at `0x18001e42e`
- `MSASN1!ASN1_Encode` at `0x18001e3bd`
- `MSASN1!ASN1_Encode` at `0x18001e3bd`
- `MSASN1!ASN1_CloseEncoder` at `0x18001e46e`
- `MSASN1!ASN1_CloseEncoder` at `0x18001e46e`

## pseudocode

```c
__int64 __fastcall KerbAddPacRequestPreAuth(struct KERB_KDC_REQUEST_preauth_data_s **a1, char a2)
{
  _QWORD *v4; // rbx
  unsigned int v5; // ecx
  _OWORD *v7; // rax
  __int64 Module; // rax
  unsigned int v9; // eax
  int v10; // eax
  void *v11; // rsi
  int v12; // edi
  __int64 v13; // rcx
  int v14; // eax
  _QWORD **v15; // rdx
  _QWORD *i; // r8
  SIZE_T v17; // rdi
  HLOCAL v18; // rax
  bool v19; // [rsp+80h] [rbp+18h] BYREF
  __int64 v20; // [rsp+88h] [rbp+20h] BYREF

  v19 = 0;
  if ( KerbGlobalPackageState == 1 )
  {
    v4 = (_QWORD *)((__int64 (__fastcall *)(__int64))LsaFunctions->AllocateLsaHeap)(32);
  }
  else
  {
    v7 = LocalAlloc(0, 0x20u);
    v4 = v7;
    if ( v7 )
    {
      *v7 = 0;
      v7[1] = 0;
      goto LABEL_8;
    }
  }
  if ( !v4 )
    return (unsigned int)-1073741670;
LABEL_8:
  v20 = 0;
  v19 = (a2 & 1) == 0;
  if ( fKRB5ModuleStarted )
  {
    Module = KRB5_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               81,
               off_1800F62D0,
               off_1800F6040,
               off_1800F6560,
               qword_1800FE8B0,
               895644267);
    KRB5_Module = Module;
  }
  v9 = ASN1_CreateEncoder(Module, &v20, 0, 0, 0);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v9);
  }
  else
  {
    v10 = ASN1_Encode(v20, &v19, 28, 16, 0, 0);
    if ( v10 >= 0 )
    {
      if ( KerbGlobalPackageState == 1 )
      {
        v11 = (void *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocateLsaHeap)(*(unsigned int *)(v20 + 28));
      }
      else
      {
        v17 = *(unsigned int *)(v20 + 28);
        v18 = LocalAlloc(0, v17);
        v11 = v18;
        if ( v18 )
        {
          memset_0(v18, 0, v17);
          v4[3] = v11;
          goto LABEL_15;
        }
      }
      v4[3] = v11;
      if ( !v11 )
      {
        v13 = v20;
        v12 = 60;
        v14 = 0;
        goto LABEL_16;
      }
LABEL_15:
      v12 = 0;
      memcpy_0(v11, *(const void **)(v20 + 16), *(unsigned int *)(v20 + 28));
      v13 = v20;
      v14 = *(_DWORD *)(v20 + 28);
LABEL_16:
      *((_DWORD *)v4 + 4) = v14;
      ASN1_FreeEncoded(v13, *(_QWORD *)(v13 + 16));
      goto LABEL_17;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        &WPP_c655c859b2e13de8f31f421519d58447_Traceguids,
        (unsigned int)v10);
  }
  v12 = 60;
LABEL_17:
  if ( v20 )
    ASN1_CloseEncoder();
  if ( v12 )
  {
    KerbFreePreAuthData(v4);
    return (unsigned int)-1073741670;
  }
  *((_DWORD *)v4 + 2) = 128;
  v5 = 0;
  v15 = (_QWORD **)*a1;
  if ( *a1 )
  {
    for ( i = *v15; i; i = (_QWORD *)*i )
      v15 = (_QWORD **)i;
    *v15 = v4;
  }
  else
  {
    *a1 = (struct KERB_KDC_REQUEST_preauth_data_s *)v4;
  }
  *v4 = 0;
  return v5;
}

```

## disassembly

```asm
0x18001e268  mov     rax, rsp
0x18001e26b  mov     [rax+8], rbx
0x18001e26f  mov     [rax+10h], rbp
0x18001e273  push    rsi
0x18001e274  push    rdi
0x18001e275  push    r14
0x18001e277  sub     rsp, 50h
0x18001e27b  mov     esi, 1
0x18001e280  mov     byte ptr [rax+18h], 0
0x18001e284  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, esi; KerberosState KerbGlobalPackageState
0x18001e28a  mov     edi, edx
0x18001e28c  mov     r14, rcx
0x18001e28f  jnz     short loc_18001E2C6
0x18001e291  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18001e298  lea     ecx, [rsi+1Fh]
0x18001e29b  mov     rax, [rax+28h]
0x18001e29f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2a4  mov     rbx, rax
0x18001e2a7  test    rbx, rbx
0x18001e2aa  jnz     short loc_18001E2E5
0x18001e2ac  mov     ecx, 0C000009Ah
0x18001e2b1  mov     rbx, [rsp+68h+arg_0]
0x18001e2b6  mov     eax, ecx
0x18001e2b8  mov     rbp, [rsp+68h+arg_8]
0x18001e2bd  add     rsp, 50h
0x18001e2c1  pop     r14
0x18001e2c3  pop     rdi
0x18001e2c4  pop     rsi
0x18001e2c5  retn
0x18001e2c6  mov     edx, 20h ; ' '; uBytes
0x18001e2cb  xor     ecx, ecx; uFlags
0x18001e2cd  call    cs:__imp_LocalAlloc
0x18001e2d3  mov     rbx, rax
0x18001e2d6  test    rax, rax
0x18001e2d9  jz      short loc_18001E2A7
0x18001e2db  xorps   xmm0, xmm0
0x18001e2de  movups  xmmword ptr [rax], xmm0
0x18001e2e1  movups  xmmword ptr [rax+10h], xmm0
0x18001e2e5  not     dil
0x18001e2e8  mov     [rsp+68h+arg_18], 0
0x18001e2f4  and     dil, sil
0x18001e2f7  mov     rbp, rbx
0x18001e2fa  cmp     cs:?fKRB5ModuleStarted@@3HA, 0; int fKRB5ModuleStarted
0x18001e301  mov     [rsp+68h+arg_10], dil
0x18001e309  jnz     loc_18001E4F5
0x18001e30f  mov     [rsp+68h+var_28], 3562726Bh
0x18001e317  lea     rax, qword_1800FE8B0
0x18001e31e  mov     [rsp+68h+var_30], rax
0x18001e323  mov     edx, 400h
0x18001e328  lea     rax, off_1800F6560
0x18001e32f  mov     cs:?fKRB5ModuleStarted@@3HA, esi; int fKRB5ModuleStarted
0x18001e335  mov     [rsp+68h+var_38], rax
0x18001e33a  mov     ecx, 10000h
0x18001e33f  lea     rax, off_1800F6040
0x18001e346  mov     r9d, 51h ; 'Q'
0x18001e34c  mov     [rsp+68h+var_40], rax
0x18001e351  mov     r8d, 1000h
0x18001e357  lea     rax, off_1800F62D0
0x18001e35e  mov     [rsp+68h+var_48], rax
0x18001e363  call    cs:__imp_ASN1_CreateModule
0x18001e369  mov     cs:KRB5_Module, rax
0x18001e370  xor     r9d, r9d
0x18001e373  mov     [rsp+68h+var_48], 0
0x18001e37c  xor     r8d, r8d
0x18001e37f  lea     rdx, [rsp+68h+arg_18]
0x18001e387  mov     rcx, rax
0x18001e38a  call    cs:__imp_ASN1_CreateEncoder
0x18001e390  test    eax, eax
0x18001e392  jnz     loc_18001E501
0x18001e398  mov     rcx, [rsp+68h+arg_18]
0x18001e3a0  lea     r9d, [rax+10h]
0x18001e3a4  mov     dword ptr [rsp+68h+var_40], eax
0x18001e3a8  lea     r8d, [rax+1Ch]
0x18001e3ac  lea     rdx, [rsp+68h+arg_10]
0x18001e3b4  mov     [rsp+68h+var_48], 0
0x18001e3bd  call    cs:__imp_ASN1_Encode
0x18001e3c3  test    eax, eax
0x18001e3c5  js      loc_18001E476
0x18001e3cb  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, esi; KerberosState KerbGlobalPackageState
0x18001e3d1  mov     rax, [rsp+68h+arg_18]
0x18001e3d9  mov     ecx, [rax+1Ch]
0x18001e3dc  jnz     loc_18001E4B1
0x18001e3e2  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18001e3e9  mov     rax, [rax+28h]
0x18001e3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3f2  mov     rsi, rax
0x18001e3f5  mov     [rbx+18h], rsi
0x18001e3f9  test    rsi, rsi
0x18001e3fc  jz      loc_18001E4E1
0x18001e402  mov     rdx, [rsp+68h+arg_18]
0x18001e40a  xor     edi, edi
0x18001e40c  mov     rcx, rsi; void *
0x18001e40f  mov     r8d, [rdx+1Ch]; Size
0x18001e413  mov     rdx, [rdx+10h]; Src
0x18001e417  call    memcpy_0
0x18001e41c  mov     rcx, [rsp+68h+arg_18]
0x18001e424  mov     eax, [rcx+1Ch]
0x18001e427  mov     [rbx+10h], eax
0x18001e42a  mov     rdx, [rcx+10h]
0x18001e42e  call    cs:__imp_ASN1_FreeEncoded
0x18001e434  mov     rcx, [rsp+68h+arg_18]
0x18001e43c  test    rcx, rcx
0x18001e43f  jnz     short loc_18001E46E
0x18001e441  test    edi, edi
0x18001e443  jnz     short loc_18001E4A4
0x18001e445  mov     dword ptr [rbx+8], 80h
0x18001e44c  xor     ecx, ecx
0x18001e44e  mov     rdx, [r14]
0x18001e451  test    rdx, rdx
0x18001e454  jz      short loc_18001E469
0x18001e456  mov     r8, [rdx]
0x18001e459  test    r8, r8
0x18001e45c  jnz     short loc_18001E494
0x18001e45e  mov     [rdx], rbx
0x18001e461  mov     [rbx], rcx
0x18001e464  jmp     loc_18001E2B1
0x18001e469  mov     [r14], rbx
0x18001e46c  jmp     short loc_18001E461
0x18001e46e  call    cs:__imp_ASN1_CloseEncoder
0x18001e474  jmp     short loc_18001E441
0x18001e476  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e47d  lea     rdx, WPP_GLOBAL_Control
0x18001e484  cmp     rcx, rdx
0x18001e487  jnz     loc_18001E53F
0x18001e48d  mov     edi, 3Ch ; '<'
0x18001e492  jmp     short loc_18001E434
0x18001e494  mov     rax, [r8]
0x18001e497  mov     rdx, r8
0x18001e49a  mov     r8, rax
0x18001e49d  test    rax, rax
0x18001e4a0  jz      short loc_18001E45E
0x18001e4a2  jmp     short loc_18001E494
0x18001e4a4  mov     rcx, rbp; hMem
0x18001e4a7  call    KerbFreePreAuthData
0x18001e4ac  jmp     loc_18001E2AC
0x18001e4b1  mov     rdi, rcx
0x18001e4b4  mov     rdx, rcx; uBytes
0x18001e4b7  xor     ecx, ecx; uFlags
0x18001e4b9  call    cs:__imp_LocalAlloc
0x18001e4bf  mov     rsi, rax
0x18001e4c2  test    rax, rax
0x18001e4c5  jz      loc_18001E3F5
0x18001e4cb  mov     r8, rdi; Size
0x18001e4ce  xor     edx, edx; Val
0x18001e4d0  mov     rcx, rax; void *
0x18001e4d3  call    memset_0
0x18001e4d8  mov     [rbx+18h], rsi
0x18001e4dc  jmp     loc_18001E402
0x18001e4e1  mov     rcx, [rsp+68h+arg_18]
0x18001e4e9  mov     edi, 3Ch ; '<'
0x18001e4ee  xor     eax, eax
0x18001e4f0  jmp     loc_18001E427
0x18001e4f5  mov     rax, cs:KRB5_Module
0x18001e4fc  jmp     loc_18001E370
0x18001e501  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e508  lea     rdx, WPP_GLOBAL_Control
0x18001e50f  cmp     rcx, rdx
0x18001e512  jz      loc_18001E48D
0x18001e518  test    [rcx+1Ch], sil
0x18001e51c  jz      loc_18001E48D
0x18001e522  mov     rcx, [rcx+10h]
0x18001e526  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x18001e52d  mov     edx, 24h ; '$'
0x18001e532  mov     r9d, eax
0x18001e535  call    WPP_SF_D
0x18001e53a  jmp     loc_18001E48D
0x18001e53f  test    [rcx+1Ch], sil
0x18001e543  jz      loc_18001E48D
0x18001e549  mov     rcx, [rcx+10h]
0x18001e54d  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x18001e554  mov     edx, 25h ; '%'
0x18001e559  mov     r9d, eax
0x18001e55c  call    WPP_SF_d
0x18001e561  jmp     loc_18001E48D
```
