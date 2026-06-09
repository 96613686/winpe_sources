# sub_1801EBFE0

- ea: `0x1801ebfe0`
- end: `0x1801ec465`
- name: `sub_1801EBFE0`
- size: `1157`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1801e7b90`

## callees

- `0x180023780`
- `0x1800299e0`
- `0x180031bb0`
- `0x180033b50`
- `0x1801ad820`
- `0x1801adc90`
- `0x1801b4140`
- `0x1801e6e50`
- `0x1801ebfe0`
- `0x1801eeb10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801ec39d`
- `KERNEL32!GetLastError` at `0x1801ec3c0`
- `KERNEL32!GetLastError` at `0x1801ec3f8`
- `KERNEL32!GetLastError` at `0x1801ec41b`
- `KERNEL32!GetLastError` at `0x1801ec43e`
- `KERNEL32!GetLastError` at `0x1801ec39d`
- `KERNEL32!GetLastError` at `0x1801ec3c0`
- `KERNEL32!GetLastError` at `0x1801ec3f8`
- `KERNEL32!GetLastError` at `0x1801ec41b`
- `KERNEL32!GetLastError` at `0x1801ec43e`
- `CRYPT32!CertOpenStore` at `0x1801ec043`
- `CRYPT32!CertOpenStore` at `0x1801ec043`
- `CRYPT32!CertCloseStore` at `0x1801ec311`
- `CRYPT32!CertCloseStore` at `0x1801ec36d`
- `CRYPT32!CertCloseStore` at `0x1801ec311`
- `CRYPT32!CertCloseStore` at `0x1801ec36d`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x1801ec0a0`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x1801ec0a0`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x1801ec147`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x1801ec147`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1801ec300`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1801ec35c`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1801ec300`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x1801ec35c`
- `CRYPT32!CertGetCertificateChain` at `0x1801ec197`
- `CRYPT32!CertGetCertificateChain` at `0x1801ec197`
- `CRYPT32!CertFreeCertificateChain` at `0x1801ec2ef`
- `CRYPT32!CertFreeCertificateChain` at `0x1801ec34b`
- `CRYPT32!CertFreeCertificateChain` at `0x1801ec2ef`
- `CRYPT32!CertFreeCertificateChain` at `0x1801ec34b`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1801ec1e0`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1801ec1e0`

## string_xrefs

- `0x1801ec38c`: `CertOpenStore failed`
- `0x1801ec3af`: `CertCreateCertificateChainEngine failed`

## pseudocode

```c
char __fastcall sub_1801EBFE0(__int64 a1, __int64 *a2, const CERT_CONTEXT *a3)
{
  HCERTSTORE v5; // rbx
  __int64 v6; // rdi
  __int64 i; // rsi
  BYTE *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  void *v11; // rcx
  void *v12; // rcx
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD LastError; // eax
  DWORD v17; // eax
  DWORD v18; // eax
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+40h] [rbp-C0h] BYREF
  HCERTCHAINENGINE phChainEngine; // [rsp+48h] [rbp-B8h] BYREF
  BYTE *pbCertEncoded[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+60h] [rbp-A0h]
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+68h] [rbp-98h] BYREF
  HCERTSTORE v24; // [rsp+80h] [rbp-80h]
  _CERT_CHAIN_ENGINE_CONFIG pConfig; // [rsp+90h] [rbp-70h] BYREF
  __int64 v26; // [rsp+E0h] [rbp-20h]
  _CERT_CHAIN_PARA pChainPara; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v28[3]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v29; // [rsp+128h] [rbp+28h]

  if ( *a2 == a2[1] || !a3 )
    return 0;
  v5 = CertOpenStore((LPCSTR)2, 0x10001u, 0, 0x2000u, 0);
  v24 = v5;
  if ( !v5 )
    goto LABEL_35;
  v6 = *a2;
  for ( i = a2[1]; v6 != i; v6 += 32 )
  {
    sub_1801EEB10(pbCertEncoded, v6);
    if ( !CertAddEncodedCertificateToStore(
            v5,
            0x10001u,
            pbCertEncoded[0],
            LODWORD(pbCertEncoded[1]) - LODWORD(pbCertEncoded[0]),
            1u,
            0) )
      goto LABEL_38;
    v8 = pbCertEncoded[0];
    if ( pbCertEncoded[0] )
    {
      if ( v22 - (unsigned __int64)pbCertEncoded[0] >= 0x1000 )
      {
        _mm_lfence();
        v8 = (BYTE *)*((_QWORD *)pbCertEncoded[0] - 1);
        if ( (unsigned __int64)(pbCertEncoded[0] - v8 - 8) > 0x1F )
        {
          sub_1801B4140(0, 0, 0, 0, 0);
LABEL_38:
          sub_180023780(v28, "CertAddEncodedCertificateToStore failed");
          LastError = GetLastError();
          sub_1801E6E50(v28, LastError);
        }
      }
      j_Free_0(v8);
      *(_OWORD *)pbCertEncoded = 0;
      v22 = 0;
    }
  }
  phChainEngine = 0;
  memset(&pConfig, 0, 64);
  pConfig.hExclusiveTrustedPeople = 0;
  v26 = 0;
  pConfig.cbSize = 88;
  pConfig.dwFlags = 48;
  pConfig.hExclusiveRoot = v5;
  if ( !CertCreateCertificateChainEngine(&pConfig, &phChainEngine) )
  {
    sub_180023780(v28, "CertCreateCertificateChainEngine failed");
    v15 = GetLastError();
    sub_1801E6E50(v28, v15);
  }
  pChainContext = 0;
  memset(&pChainPara, 0, sizeof(pChainPara));
  pChainPara.cbSize = 32;
  if ( !CertGetCertificateChain(phChainEngine, a3, 0, v5, &pChainPara, 0, 0, &pChainContext) )
  {
    sub_180023780(v28, "CertGetCertificateChain failed");
    v17 = GetLastError();
    sub_1801E6E50(v28, v17);
  }
  *(_OWORD *)pbCertEncoded = 0;
  LODWORD(pbCertEncoded[0]) = 16;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  pPolicyStatus.cbSize = 24;
  if ( !CertVerifyCertificateChainPolicy(
          (LPCSTR)4,
          pChainContext,
          (PCERT_CHAIN_POLICY_PARA)pbCertEncoded,
          &pPolicyStatus) )
  {
    sub_180023780(v28, "CertVerifyCertificateChainPolicy");
    v18 = GetLastError();
    sub_1801E6E50(v28, v18);
  }
  if ( pPolicyStatus.dwError )
  {
    v9 = sub_180033B50(v28, pPolicyStatus.dwError);
    v10 = sub_1800299E0(v9, 0, "CertVerifyCertificateChainPolicy sets certificateStatus ", 56);
    memset(&pChainPara, 0, sizeof(pChainPara));
    pChainPara = *(_CERT_CHAIN_PARA *)v10;
    *(_QWORD *)(v10 + 16) = 0;
    *(_QWORD *)(v10 + 24) = 15;
    *(_BYTE *)v10 = 0;
    sub_180031BB0(4, &pChainPara);
    if ( pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier > (LPSTR *)0xF )
    {
      v11 = *(void **)&pChainPara.cbSize;
      if ( (unsigned __int64)pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier + 1 >= 0x1000 )
      {
        v11 = *(void **)(*(_QWORD *)&pChainPara.cbSize - 8LL);
        if ( (unsigned __int64)(*(_QWORD *)&pChainPara.cbSize - (_QWORD)v11 - 8LL) > 0x1F )
        {
          sub_1801B4140(0, 0, 0, 0, 0);
          JUMPOUT(0x1801EC464LL);
        }
      }
      _mm_lfence();
      j_Free_0(v11);
    }
    pChainPara.RequestedUsage.Usage = (CERT_ENHKEY_USAGE)_mm_load_si128((const __m128i *)&xmmword_18041F110);
    LOBYTE(pChainPara.cbSize) = 0;
    if ( v29 <= 0xF )
      goto LABEL_23;
    v12 = (void *)v28[0];
    if ( v29 + 1 < 0x1000 || (v12 = *(void **)(v28[0] - 8LL), (unsigned __int64)(v28[0] - (_QWORD)v12 - 8LL) <= 0x1F) )
    {
      _mm_lfence();
      j_Free_0(v12);
LABEL_23:
      if ( pChainContext )
        CertFreeCertificateChain(pChainContext);
      if ( phChainEngine )
        CertFreeCertificateChainEngine(phChainEngine);
      CertCloseStore(v5, 0);
      return 0;
    }
    sub_1801B4140(0, 0, 0, 0, 0);
LABEL_35:
    sub_180023780(v28, "CertOpenStore failed");
    v14 = GetLastError();
    sub_1801E6E50(v28, v14);
  }
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  if ( phChainEngine )
    CertFreeCertificateChainEngine(phChainEngine);
  CertCloseStore(v5, 0);
  return 1;
}

```

## disassembly

```asm
0x1801ebfe0  mov     [rsp-8+arg_0], rbx
0x1801ebfe5  mov     [rsp-8+arg_18], rsi
0x1801ebfea  push    rbp
0x1801ebfeb  push    rdi
0x1801ebfec  push    r12
0x1801ebfee  push    r14
0x1801ebff0  push    r15
0x1801ebff2  lea     rbp, [rsp-40h]
0x1801ebff7  sub     rsp, 140h
0x1801ebffe  mov     rax, cs:__security_cookie
0x1801ec005  xor     rax, rsp
0x1801ec008  mov     [rbp+60h+var_30], rax
0x1801ec00c  mov     r14, r8
0x1801ec00f  mov     rsi, rdx
0x1801ec012  xor     r12d, r12d
0x1801ec015  mov     rax, [rdx+8]
0x1801ec019  cmp     [rdx], rax
0x1801ec01c  jz      loc_1801EC317
0x1801ec022  test    r8, r8
0x1801ec025  jz      loc_1801EC317
0x1801ec02b  mov     [rsp+160h+pvPara], r12; pvPara
0x1801ec030  mov     r9d, 2000h; dwFlags
0x1801ec036  xor     r8d, r8d; hCryptProv
0x1801ec039  mov     edx, 10001h; dwEncodingType
0x1801ec03e  mov     ecx, 2; lpszStoreProvider
0x1801ec043  call    cs:CertOpenStore
0x1801ec049  mov     rbx, rax
0x1801ec04c  mov     [rbp+60h+var_E0], rax
0x1801ec050  test    rax, rax
0x1801ec053  setnz   r15b
0x1801ec057  test    rax, rax
0x1801ec05a  jz      loc_1801EC38C
0x1801ec060  mov     rdi, [rsi]
0x1801ec063  mov     rsi, [rsi+8]
0x1801ec067  cmp     rdi, rsi
0x1801ec06a  jz      loc_1801EC10A
0x1801ec070  mov     rdx, rdi
0x1801ec073  lea     rcx, [rsp+160h+pbCertEncoded]
0x1801ec078  call    sub_1801EEB10
0x1801ec07d  nop
0x1801ec07e  mov     r9d, dword ptr [rsp+160h+pbCertEncoded+8]
0x1801ec083  mov     r8, [rsp+160h+pbCertEncoded]; pbCertEncoded
0x1801ec088  sub     r9d, r8d; cbCertEncoded
0x1801ec08b  mov     [rsp+160h+ppCertContext], r12; ppCertContext
0x1801ec090  mov     dword ptr [rsp+160h+pvPara], 1; dwAddDisposition
0x1801ec098  mov     edx, 10001h; dwCertEncodingType
0x1801ec09d  mov     rcx, rbx; hCertStore
0x1801ec0a0  call    cs:CertAddEncodedCertificateToStore
0x1801ec0a6  test    eax, eax
0x1801ec0a8  jz      loc_1801EC3E7
0x1801ec0ae  mov     rcx, [rsp+160h+pbCertEncoded]
0x1801ec0b3  test    rcx, rcx
0x1801ec0b6  jz      short loc_1801EC0FD
0x1801ec0b8  mov     rdx, [rsp+160h+var_100]
0x1801ec0bd  sub     rdx, rcx
0x1801ec0c0  cmp     rdx, 1000h
0x1801ec0c7  jb      short loc_1801EC0EA
0x1801ec0c9  lfence
0x1801ec0cc  add     rdx, 27h ; '''
0x1801ec0d0  mov     rax, [rsp+160h+pbCertEncoded]
0x1801ec0d5  mov     rcx, [rax-8]; lpMem
0x1801ec0d9  sub     rax, rcx
0x1801ec0dc  sub     rax, 8
0x1801ec0e0  cmp     rax, 1Fh
0x1801ec0e4  ja      loc_1801EC3D2
0x1801ec0ea  call    j_Free_0
0x1801ec0ef  xorps   xmm0, xmm0
0x1801ec0f2  movdqu  xmmword ptr [rsp+160h+pbCertEncoded], xmm0
0x1801ec0f8  mov     [rsp+160h+var_100], r12
0x1801ec0fd  add     rdi, 20h ; ' '
0x1801ec101  cmp     rdi, rsi
0x1801ec104  jnz     loc_1801EC070
0x1801ec10a  mov     [rsp+160h+phChainEngine], r12
0x1801ec10f  xorps   xmm0, xmm0
0x1801ec112  xor     eax, eax
0x1801ec114  movups  xmmword ptr [rbp+60h+pConfig.cbSize], xmm0
0x1801ec118  movups  xmmword ptr [rbp+60h+pConfig.hRestrictedTrust], xmm0
0x1801ec11c  movups  xmmword ptr [rbp+60h+pConfig.cAdditionalStore], xmm0
0x1801ec120  movups  xmmword ptr [rbp+60h+pConfig.dwFlags], xmm0
0x1801ec124  movups  xmmword ptr [rbp+60h+pConfig.hExclusiveRoot], xmm0
0x1801ec128  mov     [rbp+60h+var_80], rax
0x1801ec12c  mov     [rbp+60h+pConfig.cbSize], 58h ; 'X'
0x1801ec133  mov     [rbp+60h+pConfig.dwFlags], 30h ; '0'
0x1801ec13a  mov     [rbp+60h+pConfig.hExclusiveRoot], rbx
0x1801ec13e  lea     rdx, [rsp+160h+phChainEngine]; phChainEngine
0x1801ec143  lea     rcx, [rbp+60h+pConfig]; pConfig
0x1801ec147  call    cs:CertCreateCertificateChainEngine
0x1801ec14d  test    eax, eax
0x1801ec14f  jz      loc_1801EC3AF
0x1801ec155  mov     [rsp+160h+pChainContext], r12
0x1801ec15a  xorps   xmm0, xmm0
0x1801ec15d  movups  xmmword ptr [rbp+60h+pChainPara.cbSize], xmm0
0x1801ec161  movups  xmmword ptr [rbp+60h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x1801ec165  mov     [rbp+60h+pChainPara.cbSize], 20h ; ' '
0x1801ec16c  lea     rax, [rsp+160h+pChainContext]
0x1801ec171  mov     [rsp+160h+ppChainContext], rax; ppChainContext
0x1801ec176  mov     [rsp+160h+pvReserved], r12; pvReserved
0x1801ec17b  mov     dword ptr [rsp+160h+ppCertContext], r12d; dwFlags
0x1801ec180  lea     rax, [rbp+60h+pChainPara]
0x1801ec184  mov     [rsp+160h+pvPara], rax; pChainPara
0x1801ec189  mov     r9, rbx; hAdditionalStore
0x1801ec18c  xor     r8d, r8d; pTime
0x1801ec18f  mov     rdx, r14; pCertContext
0x1801ec192  mov     rcx, [rsp+160h+phChainEngine]; hChainEngine
0x1801ec197  call    cs:CertGetCertificateChain
0x1801ec19d  test    eax, eax
0x1801ec19f  jz      loc_1801EC40A
0x1801ec1a5  xorps   xmm0, xmm0
0x1801ec1a8  movups  xmmword ptr [rsp+160h+pbCertEncoded], xmm0
0x1801ec1ad  mov     dword ptr [rsp+160h+pbCertEncoded], 10h
0x1801ec1b5  xorps   xmm1, xmm1
0x1801ec1b8  xor     eax, eax
0x1801ec1ba  movups  xmmword ptr [rsp+160h+pPolicyStatus.cbSize], xmm1
0x1801ec1bf  mov     [rsp+160h+pPolicyStatus.pvExtraPolicyStatus], rax
0x1801ec1c4  mov     [rsp+160h+pPolicyStatus.cbSize], 18h
0x1801ec1cc  lea     r9, [rsp+160h+pPolicyStatus]; pPolicyStatus
0x1801ec1d1  lea     r8, [rsp+160h+pbCertEncoded]; pPolicyPara
0x1801ec1d6  mov     rdx, [rsp+160h+pChainContext]; pChainContext
0x1801ec1db  mov     ecx, 4; pszPolicyOID
0x1801ec1e0  call    cs:CertVerifyCertificateChainPolicy
0x1801ec1e6  test    eax, eax
0x1801ec1e8  jz      loc_1801EC42D
0x1801ec1ee  mov     edx, [rsp+160h+pPolicyStatus.dwError]
0x1801ec1f2  test    edx, edx
0x1801ec1f4  jz      loc_1801EC341
0x1801ec1fa  lea     rcx, [rbp+60h+var_50]
0x1801ec1fe  call    sub_180033B50
0x1801ec203  nop
0x1801ec204  mov     r9d, 38h ; '8'
0x1801ec20a  lea     r8, aCertverifycert; "CertVerifyCertificateChainPolicy sets c"...
0x1801ec211  xor     edx, edx
0x1801ec213  mov     rcx, rax
0x1801ec216  call    sub_1800299E0
0x1801ec21b  xorps   xmm0, xmm0
0x1801ec21e  movups  xmmword ptr [rbp+60h+pChainPara.cbSize], xmm0
0x1801ec222  xorps   xmm1, xmm1
0x1801ec225  movdqu  xmmword ptr [rbp+60h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm1
0x1801ec22a  movups  xmm0, xmmword ptr [rax]
0x1801ec22d  movups  xmmword ptr [rbp+60h+pChainPara.cbSize], xmm0
0x1801ec231  movups  xmm1, xmmword ptr [rax+10h]
0x1801ec235  movups  xmmword ptr [rbp+60h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm1
0x1801ec239  mov     [rax+10h], r12
0x1801ec23d  mov     qword ptr [rax+18h], 0Fh
0x1801ec245  mov     byte ptr [rax], 0
0x1801ec248  lea     rdx, [rbp+60h+pChainPara]
0x1801ec24c  mov     ecx, 4
0x1801ec251  call    sub_180031BB0
0x1801ec256  nop
0x1801ec257  mov     rdx, [rbp+60h+pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier]
0x1801ec25b  cmp     rdx, 0Fh
0x1801ec25f  jbe     short loc_1801EC295
0x1801ec261  inc     rdx
0x1801ec264  mov     rcx, qword ptr [rbp+60h+pChainPara.cbSize]
0x1801ec268  mov     rax, rcx
0x1801ec26b  cmp     rdx, 1000h
0x1801ec272  jb      short loc_1801EC28D
0x1801ec274  add     rdx, 27h ; '''
0x1801ec278  mov     rcx, [rcx-8]; lpMem
0x1801ec27c  sub     rax, rcx
0x1801ec27f  sub     rax, 8
0x1801ec283  cmp     rax, 1Fh
0x1801ec287  ja      loc_1801EC450
0x1801ec28d  lfence
0x1801ec290  call    j_Free_0
0x1801ec295  movdqa  xmm0, cs:xmmword_18041F110
0x1801ec29d  movdqu  xmmword ptr [rbp+60h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x1801ec2a2  mov     byte ptr [rbp+60h+pChainPara.cbSize], 0
0x1801ec2a6  mov     rdx, [rbp+60h+var_38]
0x1801ec2aa  cmp     rdx, 0Fh
0x1801ec2ae  jbe     short loc_1801EC2E5
0x1801ec2b0  inc     rdx
0x1801ec2b3  mov     rcx, [rbp+60h+var_50]
0x1801ec2b7  mov     rax, rcx
0x1801ec2ba  cmp     rdx, 1000h
0x1801ec2c1  jb      short loc_1801EC2DC
0x1801ec2c3  add     rdx, 27h ; '''
0x1801ec2c7  mov     rcx, [rcx-8]; lpMem
0x1801ec2cb  sub     rax, rcx
0x1801ec2ce  sub     rax, 8
0x1801ec2d2  cmp     rax, 1Fh
0x1801ec2d6  ja      loc_1801EC377
0x1801ec2dc  lfence
0x1801ec2df  call    j_Free_0
0x1801ec2e4  nop
0x1801ec2e5  mov     rcx, [rsp+160h+pChainContext]; pChainContext
0x1801ec2ea  test    rcx, rcx
0x1801ec2ed  jz      short loc_1801EC2F6
0x1801ec2ef  call    cs:CertFreeCertificateChain
0x1801ec2f5  nop
0x1801ec2f6  mov     rcx, [rsp+160h+phChainEngine]; hChainEngine
0x1801ec2fb  test    rcx, rcx
0x1801ec2fe  jz      short loc_1801EC307
0x1801ec300  call    cs:CertFreeCertificateChainEngine
0x1801ec306  nop
0x1801ec307  test    r15b, r15b
0x1801ec30a  jz      short loc_1801EC317
0x1801ec30c  xor     edx, edx; dwFlags
0x1801ec30e  mov     rcx, rbx; hCertStore
0x1801ec311  call    cs:CertCloseStore
0x1801ec317  xor     al, al
0x1801ec319  mov     rcx, [rbp+60h+var_30]
0x1801ec31d  xor     rcx, rsp; StackCookie
0x1801ec320  call    __security_check_cookie
0x1801ec325  lea     r11, [rsp+160h+var_20]
0x1801ec32d  mov     rbx, [r11+30h]
0x1801ec331  mov     rsi, [r11+48h]
0x1801ec335  mov     rsp, r11
0x1801ec338  pop     r15
0x1801ec33a  pop     r14
0x1801ec33c  pop     r12
0x1801ec33e  pop     rdi
0x1801ec33f  pop     rbp
0x1801ec340  retn
0x1801ec341  mov     rcx, [rsp+160h+pChainContext]; pChainContext
0x1801ec346  test    rcx, rcx
0x1801ec349  jz      short loc_1801EC352
0x1801ec34b  call    cs:CertFreeCertificateChain
0x1801ec351  nop
0x1801ec352  mov     rcx, [rsp+160h+phChainEngine]; hChainEngine
0x1801ec357  test    rcx, rcx
0x1801ec35a  jz      short loc_1801EC363
0x1801ec35c  call    cs:CertFreeCertificateChainEngine
0x1801ec362  nop
0x1801ec363  test    r15b, r15b
0x1801ec366  jz      short loc_1801EC373
0x1801ec368  xor     edx, edx; dwFlags
0x1801ec36a  mov     rcx, rbx; hCertStore
0x1801ec36d  call    cs:CertCloseStore
0x1801ec373  mov     al, 1
0x1801ec375  jmp     short loc_1801EC319
0x1801ec377  mov     [rsp+160h+pvPara], r12
0x1801ec37c  xor     r9d, r9d
0x1801ec37f  xor     r8d, r8d
0x1801ec382  xor     edx, edx
0x1801ec384  xor     ecx, ecx
0x1801ec386  call    sub_1801B4140
0x1801ec38b  nop
0x1801ec38c  lea     rdx, aCertopenstoreF; "CertOpenStore failed"
0x1801ec393  lea     rcx, [rbp+60h+var_50]
0x1801ec397  call    sub_180023780
0x1801ec39c  nop
0x1801ec39d  call    cs:__imp_GetLastError
0x1801ec3a3  mov     edx, eax
0x1801ec3a5  lea     rcx, [rbp+60h+var_50]
0x1801ec3a9  call    sub_1801E6E50
0x1801ec3af  lea     rdx, aCertcreatecert; "CertCreateCertificateChainEngine failed"
0x1801ec3b6  lea     rcx, [rbp+60h+var_50]
0x1801ec3ba  call    sub_180023780
0x1801ec3bf  nop
0x1801ec3c0  call    cs:__imp_GetLastError
0x1801ec3c6  mov     edx, eax
0x1801ec3c8  lea     rcx, [rbp+60h+var_50]
0x1801ec3cc  call    sub_1801E6E50
0x1801ec3d2  mov     [rsp+160h+pvPara], r12
0x1801ec3d7  xor     r9d, r9d
0x1801ec3da  xor     r8d, r8d
0x1801ec3dd  xor     edx, edx
0x1801ec3df  xor     ecx, ecx
0x1801ec3e1  call    sub_1801B4140
0x1801ec3e6  nop
0x1801ec3e7  lea     rdx, aCertaddencoded; "CertAddEncodedCertificateToStore failed"
0x1801ec3ee  lea     rcx, [rbp+60h+var_50]
0x1801ec3f2  call    sub_180023780
0x1801ec3f7  nop
0x1801ec3f8  call    cs:__imp_GetLastError
0x1801ec3fe  mov     edx, eax
0x1801ec400  lea     rcx, [rbp+60h+var_50]
0x1801ec404  call    sub_1801E6E50
0x1801ec40a  lea     rdx, aCertgetcertifi; "CertGetCertificateChain failed"
0x1801ec411  lea     rcx, [rbp+60h+var_50]
0x1801ec415  call    sub_180023780
0x1801ec41a  nop
0x1801ec41b  call    cs:__imp_GetLastError
0x1801ec421  mov     edx, eax
0x1801ec423  lea     rcx, [rbp+60h+var_50]
0x1801ec427  call    sub_1801E6E50
0x1801ec42d  lea     rdx, aCertverifycert_0; "CertVerifyCertificateChainPolicy"
0x1801ec434  lea     rcx, [rbp+60h+var_50]
0x1801ec438  call    sub_180023780
0x1801ec43d  nop
0x1801ec43e  call    cs:__imp_GetLastError
0x1801ec444  mov     edx, eax
0x1801ec446  lea     rcx, [rbp+60h+var_50]
0x1801ec44a  call    sub_1801E6E50
0x1801ec450  mov     [rsp+160h+pvPara], r12
0x1801ec455  xor     r9d, r9d
0x1801ec458  xor     r8d, r8d
0x1801ec45b  xor     edx, edx
0x1801ec45d  xor     ecx, ecx
0x1801ec45f  call    sub_1801B4140
```
