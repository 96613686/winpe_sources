# BuildCertContext(unsigned __int64,uchar *,ulong,_CERT_CONTEXT const * *)

- ea: `0x1800770dc`
- end: `0x1800772e8`
- name: `?BuildCertContext@@YAK_KPEAEKPEAPEBU_CERT_CONTEXT@@@Z`
- size: `524`
- prototype: `unsigned int __fastcall(HCRYPTPROV hProv, unsigned __int8 *, unsigned int, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180077710`

## callees

- `0x180005010`
- `0x180010140`
- `0x1800770dc`
- `0x1800796c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007714f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077249`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007714f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077249`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800772b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800772c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800772b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800772c0`
- `CRYPT32!CertFreeCertificateContext` at `0x180077293`
- `CRYPT32!CertFreeCertificateContext` at `0x180077293`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180077239`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180077239`
- `CRYPT32!CertCreateCertificateContext` at `0x180077137`
- `CRYPT32!CertCreateCertificateContext` at `0x180077137`

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
0x1800770dc  mov     [rsp-28h+arg_8], rbx
0x1800770e1  mov     [rsp-28h+arg_10], rsi
0x1800770e6  push    rbp
0x1800770e7  push    rdi
0x1800770e8  push    r12
0x1800770ea  push    r14
0x1800770ec  push    r15
0x1800770ee  mov     rbp, rsp
0x1800770f1  sub     rsp, 60h
0x1800770f5  xorps   xmm0, xmm0
0x1800770f8  xor     r14d, r14d
0x1800770fb  xor     esi, esi
0x1800770fd  mov     [rbp+hMem], r14
0x180077101  mov     [rbp+arg_0], rsi
0x180077105  mov     r12, r9
0x180077108  mov     r15, rcx
0x18007710b  movups  [rbp+pvData], xmm0
0x18007710f  movups  [rbp+var_28], xmm0
0x180077113  movups  [rbp+var_18], xmm0
0x180077117  test    rcx, rcx
0x18007711a  jz      loc_1800772A1
0x180077120  test    rdx, rdx
0x180077123  jz      loc_1800772A1
0x180077129  test    r8d, r8d
0x18007712c  jz      loc_1800772A1
0x180077132  mov     ecx, 10001h; dwCertEncodingType
0x180077137  call    cs:__imp_CertCreateCertificateContext
0x18007713e  nop     dword ptr [rax+rax+00h]
0x180077143  mov     [r12], rax
0x180077147  test    rax, rax
0x18007714a  jnz     short loc_18007717C
0x18007714c  xor     r15d, r15d
0x18007714f  call    cs:__imp_GetLastError
0x180077156  nop     dword ptr [rax+rax+00h]
0x18007715b  mov     ebx, eax
0x18007715d  mov     rcx, cs:WPP_GLOBAL_Control
0x180077164  lea     rdi, WPP_GLOBAL_Control
0x18007716b  cmp     rcx, rdi
0x18007716e  jz      loc_18007727A
0x180077174  lea     edx, [rsi+12h]
0x180077177  jmp     loc_180077267
0x18007717c  lea     r8, [rbp+hMem]; unsigned __int16 **
0x180077180  mov     edx, 6; dwParam
0x180077185  mov     rcx, r15; hProv
0x180077188  call    ?LocalCryptGetProvParamW@@YAK_KKPEAPEAG@Z; LocalCryptGetProvParamW(unsigned __int64,ulong,ushort * *)
0x18007718d  mov     ebx, eax
0x18007718f  test    eax, eax
0x180077191  jnz     loc_18007728B
0x180077197  mov     rcx, cs:WPP_GLOBAL_Control
0x18007719e  lea     rdi, WPP_GLOBAL_Control
0x1800771a5  mov     r14, [rbp+hMem]
0x1800771a9  cmp     rcx, rdi
0x1800771ac  jz      short loc_1800771C4
0x1800771ae  mov     rcx, [rcx+10h]
0x1800771b2  lea     edx, [rax+13h]
0x1800771b5  mov     r9, r14
0x1800771b8  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x1800771bf  call    WPP_SF_S
0x1800771c4  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x1800771c8  mov     edx, 4; dwParam
0x1800771cd  mov     rcx, r15; hProv
0x1800771d0  call    ?LocalCryptGetProvParamW@@YAK_KKPEAPEAG@Z; LocalCryptGetProvParamW(unsigned __int64,ulong,ushort * *)
0x1800771d5  mov     ebx, eax
0x1800771d7  test    eax, eax
0x1800771d9  jnz     loc_180077285
0x1800771df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800771e6  mov     rsi, [rbp+arg_0]
0x1800771ea  cmp     rcx, rdi
0x1800771ed  jz      short loc_180077205
0x1800771ef  mov     rcx, [rcx+10h]
0x1800771f3  lea     edx, [rax+14h]
0x1800771f6  mov     r9, rsi
0x1800771f9  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180077200  call    WPP_SF_S
0x180077205  mov     rcx, [r12]; pCertContext
0x180077209  lea     r9, [rbp+pvData]; pvData
0x18007720d  mov     r15d, 1
0x180077213  mov     qword ptr [rbp+pvData], r14
0x180077217  xor     r8d, r8d; dwFlags
0x18007721a  mov     qword ptr [rbp+pvData+8], rsi
0x18007721e  mov     qword ptr [rbp+var_28], r15
0x180077222  mov     dword ptr [rbp+var_28+8], 0
0x180077229  lea     edx, [r15+1]; dwPropId
0x18007722d  mov     qword ptr [rbp+var_18], 0
0x180077235  mov     dword ptr [rbp+var_18+8], r15d
0x180077239  call    cs:__imp_CertSetCertificateContextProperty
0x180077240  nop     dword ptr [rax+rax+00h]
0x180077245  test    eax, eax
0x180077247  jnz     short loc_1800772AE
0x180077249  call    cs:__imp_GetLastError
0x180077250  nop     dword ptr [rax+rax+00h]
0x180077255  mov     ebx, eax
0x180077257  mov     rcx, cs:WPP_GLOBAL_Control
0x18007725e  cmp     rcx, rdi
0x180077261  jz      short loc_18007727A
0x180077263  lea     edx, [r15+14h]
0x180077267  mov     rcx, [rcx+10h]
0x18007726b  lea     r8, WPP_fb40f0a041ee378e7d6fb89397fbd37a_Traceguids
0x180077272  mov     r9d, eax
0x180077275  call    WPP_SF_d
0x18007727a  test    ebx, ebx
0x18007727c  jz      short loc_1800772AE
0x18007727e  test    r15d, r15d
0x180077281  jz      short loc_1800772A6
0x180077283  jmp     short loc_18007728F
0x180077285  mov     rsi, [rbp+arg_0]
0x180077289  jmp     short loc_18007728F
0x18007728b  mov     r14, [rbp+hMem]
0x18007728f  mov     rcx, [r12]; pCertContext
0x180077293  call    cs:__imp_CertFreeCertificateContext
0x18007729a  nop     dword ptr [rax+rax+00h]
0x18007729f  jmp     short loc_1800772A6
0x1800772a1  mov     ebx, 57h ; 'W'
0x1800772a6  mov     qword ptr [r12], 0
0x1800772ae  mov     rcx, r14; hMem
0x1800772b1  call    cs:__imp_LocalFree
0x1800772b8  nop     dword ptr [rax+rax+00h]
0x1800772bd  mov     rcx, rsi; hMem
0x1800772c0  call    cs:__imp_LocalFree
0x1800772c7  nop     dword ptr [rax+rax+00h]
0x1800772cc  lea     r11, [rsp+60h+var_s0]
0x1800772d1  mov     eax, ebx
0x1800772d3  mov     rbx, [r11+38h]
0x1800772d7  mov     rsi, [r11+40h]
0x1800772db  mov     rsp, r11
0x1800772de  pop     r15
0x1800772e0  pop     r14
0x1800772e2  pop     r12
0x1800772e4  pop     rdi
0x1800772e5  pop     rbp
0x1800772e6  retn
```
