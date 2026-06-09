# BuildCertContext(unsigned __int64,uchar *,ulong,_CERT_CONTEXT const * *)

- ea: `0x1800721c8`
- end: `0x1800723a9`
- name: `?BuildCertContext@@YAK_KPEAEKPEAPEBU_CERT_CONTEXT@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(HCRYPTPROV hProv, unsigned __int8 *, DWORD, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180072764`

## callees

- `0x180004bd0`
- `0x18000f350`
- `0x1800721c8`
- `0x180074460`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072323`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007237f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072388`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007237f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072388`
- `CRYPT32!CertFreeCertificateContext` at `0x180072367`
- `CRYPT32!CertFreeCertificateContext` at `0x180072367`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180072319`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180072319`
- `CRYPT32!CertCreateCertificateContext` at `0x180072223`
- `CRYPT32!CertCreateCertificateContext` at `0x180072223`

## pseudocode

```c
__int64 __fastcall BuildCertContext(HCRYPTPROV hProv, unsigned __int8 *a2, DWORD a3, const struct _CERT_CONTEXT **a4)
{
  HLOCAL v4; // r14
  HLOCAL v5; // rsi
  const struct _CERT_CONTEXT *CertificateContext; // rax
  int v9; // r15d
  DWORD LastError; // eax
  unsigned int ProvParamW; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v12; // rcx
  __int64 v13; // rdx
  const CERT_CONTEXT *v14; // rcx
  HLOCAL hMem; // [rsp+20h] [rbp-40h] BYREF
  __int128 pvData; // [rsp+28h] [rbp-38h] BYREF
  __int128 v18; // [rsp+38h] [rbp-28h]
  __int128 v19; // [rsp+48h] [rbp-18h]
  HLOCAL v20; // [rsp+90h] [rbp+30h] BYREF

  v4 = 0;
  v5 = 0;
  hMem = 0;
  v20 = 0;
  pvData = 0;
  v18 = 0;
  v19 = 0;
  if ( !hProv || !a2 || !a3 )
  {
    ProvParamW = 87;
    goto LABEL_24;
  }
  CertificateContext = CertCreateCertificateContext(0x10001u, a2, a3);
  *a4 = CertificateContext;
  if ( !CertificateContext )
  {
    v9 = 0;
    LastError = GetLastError();
    ProvParamW = LastError;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_17;
    v13 = 18;
    goto LABEL_16;
  }
  ProvParamW = LocalCryptGetProvParamW(hProv, 6u, (unsigned __int16 **)&hMem);
  if ( ProvParamW )
  {
    v4 = hMem;
    goto LABEL_22;
  }
  v4 = hMem;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, hMem);
  ProvParamW = LocalCryptGetProvParamW(hProv, 4u, (unsigned __int16 **)&v20);
  if ( ProvParamW )
  {
    v5 = v20;
    goto LABEL_22;
  }
  v5 = v20;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, v20);
  v14 = *a4;
  v9 = 1;
  *(_QWORD *)&pvData = v4;
  *((_QWORD *)&pvData + 1) = v5;
  *(_QWORD *)&v18 = 1;
  DWORD2(v18) = 0;
  *(_QWORD *)&v19 = 0;
  DWORD2(v19) = 1;
  if ( !CertSetCertificateContextProperty(v14, 2u, 0, &pvData) )
  {
    LastError = GetLastError();
    ProvParamW = LastError;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_17;
    v13 = 21;
LABEL_16:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids, LastError);
LABEL_17:
    if ( ProvParamW )
    {
      if ( !v9 )
      {
LABEL_24:
        *a4 = 0;
        goto LABEL_25;
      }
LABEL_22:
      CertFreeCertificateContext(*a4);
      goto LABEL_24;
    }
  }
LABEL_25:
  LocalFree(v4);
  LocalFree(v5);
  return ProvParamW;
}

```

## disassembly

```asm
0x1800721c8  mov     [rsp-28h+arg_8], rbx
0x1800721cd  mov     [rsp-28h+arg_10], rsi
0x1800721d2  push    rbp
0x1800721d3  push    rdi
0x1800721d4  push    r12
0x1800721d6  push    r14
0x1800721d8  push    r15
0x1800721da  mov     rbp, rsp
0x1800721dd  sub     rsp, 60h
0x1800721e1  xorps   xmm0, xmm0
0x1800721e4  xor     r14d, r14d
0x1800721e7  xor     esi, esi
0x1800721e9  mov     [rbp+hMem], r14
0x1800721ed  mov     [rbp+arg_0], rsi
0x1800721f1  mov     r12, r9
0x1800721f4  mov     r15, rcx
0x1800721f7  movups  [rbp+pvData], xmm0
0x1800721fb  movups  [rbp+var_28], xmm0
0x1800721ff  movups  [rbp+var_18], xmm0
0x180072203  test    rcx, rcx
0x180072206  jz      loc_18007236F
0x18007220c  test    rdx, rdx
0x18007220f  jz      loc_18007236F
0x180072215  test    r8d, r8d
0x180072218  jz      loc_18007236F
0x18007221e  mov     ecx, 10001h; dwCertEncodingType
0x180072223  call    cs:__imp_CertCreateCertificateContext
0x180072229  mov     [r12], rax
0x18007222d  test    rax, rax
0x180072230  jnz     short loc_18007225C
0x180072232  xor     r15d, r15d
0x180072235  call    cs:__imp_GetLastError
0x18007223b  mov     ebx, eax
0x18007223d  mov     rcx, cs:WPP_GLOBAL_Control
0x180072244  lea     rdi, WPP_GLOBAL_Control
0x18007224b  cmp     rcx, rdi
0x18007224e  jz      loc_18007234E
0x180072254  lea     edx, [rsi+12h]
0x180072257  jmp     loc_18007233B
0x18007225c  lea     r8, [rbp+hMem]; unsigned __int16 **
0x180072260  mov     edx, 6; dwParam
0x180072265  mov     rcx, r15; hProv
0x180072268  call    ?LocalCryptGetProvParamW@@YAK_KKPEAPEAG@Z; LocalCryptGetProvParamW(unsigned __int64,ulong,ushort * *)
0x18007226d  mov     ebx, eax
0x18007226f  test    eax, eax
0x180072271  jnz     loc_18007235F
0x180072277  mov     rcx, cs:WPP_GLOBAL_Control
0x18007227e  lea     rdi, WPP_GLOBAL_Control
0x180072285  mov     r14, [rbp+hMem]
0x180072289  cmp     rcx, rdi
0x18007228c  jz      short loc_1800722A4
0x18007228e  mov     rcx, [rcx+10h]
0x180072292  lea     edx, [rax+13h]
0x180072295  mov     r9, r14
0x180072298  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x18007229f  call    WPP_SF_S
0x1800722a4  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x1800722a8  mov     edx, 4; dwParam
0x1800722ad  mov     rcx, r15; hProv
0x1800722b0  call    ?LocalCryptGetProvParamW@@YAK_KKPEAPEAG@Z; LocalCryptGetProvParamW(unsigned __int64,ulong,ushort * *)
0x1800722b5  mov     ebx, eax
0x1800722b7  test    eax, eax
0x1800722b9  jnz     loc_180072359
0x1800722bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800722c6  mov     rsi, [rbp+arg_0]
0x1800722ca  cmp     rcx, rdi
0x1800722cd  jz      short loc_1800722E5
0x1800722cf  mov     rcx, [rcx+10h]
0x1800722d3  lea     edx, [rax+14h]
0x1800722d6  mov     r9, rsi
0x1800722d9  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x1800722e0  call    WPP_SF_S
0x1800722e5  mov     rcx, [r12]; pCertContext
0x1800722e9  lea     r9, [rbp+pvData]; pvData
0x1800722ed  mov     r15d, 1
0x1800722f3  mov     qword ptr [rbp+pvData], r14
0x1800722f7  xor     r8d, r8d; dwFlags
0x1800722fa  mov     qword ptr [rbp+pvData+8], rsi
0x1800722fe  mov     qword ptr [rbp+var_28], r15
0x180072302  mov     dword ptr [rbp+var_28+8], 0
0x180072309  lea     edx, [r15+1]; dwPropId
0x18007230d  mov     qword ptr [rbp+var_18], 0
0x180072315  mov     dword ptr [rbp+var_18+8], r15d
0x180072319  call    cs:__imp_CertSetCertificateContextProperty
0x18007231f  test    eax, eax
0x180072321  jnz     short loc_18007237C
0x180072323  call    cs:__imp_GetLastError
0x180072329  mov     ebx, eax
0x18007232b  mov     rcx, cs:WPP_GLOBAL_Control
0x180072332  cmp     rcx, rdi
0x180072335  jz      short loc_18007234E
0x180072337  lea     edx, [r15+14h]
0x18007233b  mov     rcx, [rcx+10h]
0x18007233f  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180072346  mov     r9d, eax
0x180072349  call    WPP_SF_d
0x18007234e  test    ebx, ebx
0x180072350  jz      short loc_18007237C
0x180072352  test    r15d, r15d
0x180072355  jz      short loc_180072374
0x180072357  jmp     short loc_180072363
0x180072359  mov     rsi, [rbp+arg_0]
0x18007235d  jmp     short loc_180072363
0x18007235f  mov     r14, [rbp+hMem]
0x180072363  mov     rcx, [r12]; pCertContext
0x180072367  call    cs:__imp_CertFreeCertificateContext
0x18007236d  jmp     short loc_180072374
0x18007236f  mov     ebx, 57h ; 'W'
0x180072374  mov     qword ptr [r12], 0
0x18007237c  mov     rcx, r14; hMem
0x18007237f  call    cs:__imp_LocalFree
0x180072385  mov     rcx, rsi; hMem
0x180072388  call    cs:__imp_LocalFree
0x18007238e  lea     r11, [rsp+60h+var_s0]
0x180072393  mov     eax, ebx
0x180072395  mov     rbx, [r11+38h]
0x180072399  mov     rsi, [r11+40h]
0x18007239d  mov     rsp, r11
0x1800723a0  pop     r15
0x1800723a2  pop     r14
0x1800723a4  pop     r12
0x1800723a6  pop     rdi
0x1800723a7  pop     rbp
0x1800723a8  retn
```
