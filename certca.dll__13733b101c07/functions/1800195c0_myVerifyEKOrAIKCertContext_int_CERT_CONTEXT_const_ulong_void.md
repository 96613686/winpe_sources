# myVerifyEKOrAIKCertContext(int,_CERT_CONTEXT const *,ulong,void *)

- ea: `0x1800195c0`
- end: `0x180019765`
- name: `?myVerifyEKOrAIKCertContext@@YAJHPEBU_CERT_CONTEXT@@KPEAX@Z`
- size: `421`
- prototype: `__int64 __fastcall(int, const struct _CERT_CONTEXT *, int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800195a0`

## callees

- `0x180008400`
- `0x180012450`
- `0x1800195c0`
- `0x18001bb30`
- `0x180038262`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x180019639`
- `CRYPT32!CertOpenStore` at `0x180019672`
- `CRYPT32!CertOpenStore` at `0x180019639`
- `CRYPT32!CertOpenStore` at `0x180019672`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x1800196bb`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x1800196bb`
- `CRYPT32!CertCloseStore` at `0x18001972e`
- `CRYPT32!CertCloseStore` at `0x18001973e`
- `CRYPT32!CertCloseStore` at `0x18001972e`
- `CRYPT32!CertCloseStore` at `0x18001973e`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18001974d`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18001974d`

## pseudocode

```c
__int64 __fastcall myVerifyEKOrAIKCertContext(int a1, const struct _CERT_CONTEXT *a2, int a3, void *a4)
{
  unsigned int v8; // ebx
  HCERTSTORE v9; // rdi
  int v10; // edx
  unsigned int v11; // ecx
  unsigned int v12; // eax
  unsigned int v13; // r8d
  HCERTCHAINENGINE phChainEngine; // [rsp+40h] [rbp-49h] BYREF
  char *v16; // [rsp+48h] [rbp-41h] BYREF
  _CERT_CHAIN_ENGINE_CONFIG pConfig; // [rsp+50h] [rbp-39h] BYREF
  HCERTSTORE hCertStore; // [rsp+F8h] [rbp+6Fh] BYREF

  memset_0(&pConfig, 0, 0x58u);
  v16 = 0;
  phChainEngine = 0;
  hCertStore = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    v9 = 0;
    v10 = -2147024809;
    v11 = 114295194;
LABEL_14:
    CSPrintErrorLineFile(v11, v10);
    goto LABEL_15;
  }
  v9 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x28000u, L"EKRoot");
  if ( !v9 )
  {
    v12 = myHLastError();
    v8 = v12;
    v11 = 115278234;
LABEL_13:
    v10 = v12;
    goto LABEL_14;
  }
  hCertStore = CertOpenStore((LPCSTR)0xA, 0, 0, 0x28000u, L"EKCA");
  if ( !hCertStore )
  {
    v12 = myHLastError();
    v8 = v12;
    v11 = 116130202;
    goto LABEL_13;
  }
  pConfig.hExclusiveRoot = v9;
  pConfig.rghAdditionalStore = &hCertStore;
  pConfig.cAdditionalStore = 1;
  pConfig.dwFlags = 8;
  pConfig.cbSize = 88;
  if ( !CertCreateCertificateChainEngine(&pConfig, &phChainEngine) )
  {
    v12 = myHLastError();
    v8 = v12;
    v11 = 116916634;
    goto LABEL_13;
  }
  v13 = 0;
  if ( !a1 )
  {
    v16 = "2.23.133.8.3";
    v13 = 1;
  }
  v12 = myVerifyCertContext(a2, a3 | 0x40u, v13, (const char *const *)&v16, phChainEngine, a4, 0);
  v8 = v12;
  if ( v12 )
  {
    v11 = 118096282;
    goto LABEL_13;
  }
LABEL_15:
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( v9 )
    CertCloseStore(v9, 0);
  if ( phChainEngine )
    CertFreeCertificateChainEngine(phChainEngine);
  return v8;
}

```

## disassembly

```asm
0x1800195c0  push    rbp
0x1800195c2  push    rbx
0x1800195c3  push    rsi
0x1800195c4  push    rdi
0x1800195c5  push    r14
0x1800195c7  push    r15
0x1800195c9  lea     rbp, [rsp-2Fh]
0x1800195ce  sub     rsp, 0B8h
0x1800195d5  mov     r14, rdx
0x1800195d8  mov     ebx, r8d
0x1800195db  xor     edx, edx; Val
0x1800195dd  mov     esi, ecx
0x1800195df  lea     rcx, [rbp+57h+pConfig]; void *
0x1800195e3  mov     r15, r9
0x1800195e6  lea     r8d, [rdx+58h]; Size
0x1800195ea  call    memset_0
0x1800195ef  mov     [rbp+57h+var_98], 0
0x1800195f7  mov     [rbp+57h+phChainEngine], 0
0x1800195ff  mov     [rbp+57h+hCertStore], 0
0x180019607  test    r14, r14
0x18001960a  jnz     short loc_18001961F
0x18001960c  mov     ebx, 80070057h
0x180019611  xor     edi, edi
0x180019613  mov     edx, ebx
0x180019615  mov     ecx, 6D0019Ah
0x18001961a  jmp     loc_18001971E
0x18001961f  xor     edx, edx; dwEncodingType
0x180019621  lea     rax, aEkroot; "EKRoot"
0x180019628  mov     r9d, 28000h; dwFlags
0x18001962e  mov     [rsp+0E0h+pvPara], rax; pvPara
0x180019633  xor     r8d, r8d; hCryptProv
0x180019636  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180019639  call    cs:__imp_CertOpenStore
0x18001963f  mov     rdi, rax
0x180019642  test    rax, rax
0x180019645  jnz     short loc_180019658
0x180019647  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001964c  mov     ebx, eax
0x18001964e  mov     ecx, 6DF019Ah
0x180019653  jmp     loc_18001971C
0x180019658  xor     edx, edx; dwEncodingType
0x18001965a  lea     rax, aEkca; "EKCA"
0x180019661  mov     r9d, 28000h; dwFlags
0x180019667  mov     [rsp+0E0h+pvPara], rax; pvPara
0x18001966c  xor     r8d, r8d; hCryptProv
0x18001966f  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180019672  call    cs:__imp_CertOpenStore
0x180019678  mov     [rbp+57h+hCertStore], rax
0x18001967c  test    rax, rax
0x18001967f  jnz     short loc_180019692
0x180019681  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180019686  mov     ebx, eax
0x180019688  mov     ecx, 6EC019Ah
0x18001968d  jmp     loc_18001971C
0x180019692  lea     rax, [rbp+57h+hCertStore]
0x180019696  mov     [rbp+57h+pConfig.hExclusiveRoot], rdi
0x18001969a  lea     rdx, [rbp+57h+phChainEngine]; phChainEngine
0x18001969e  mov     [rbp+57h+pConfig.rghAdditionalStore], rax
0x1800196a2  lea     rcx, [rbp+57h+pConfig]; pConfig
0x1800196a6  mov     [rbp+57h+pConfig.cAdditionalStore], 1
0x1800196ad  mov     [rbp+57h+pConfig.dwFlags], 8
0x1800196b4  mov     [rbp+57h+pConfig.cbSize], 58h ; 'X'
0x1800196bb  call    cs:__imp_CertCreateCertificateChainEngine
0x1800196c1  test    eax, eax
0x1800196c3  jnz     short loc_1800196D3
0x1800196c5  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800196ca  mov     ebx, eax
0x1800196cc  mov     ecx, 6F8019Ah
0x1800196d1  jmp     short loc_18001971C
0x1800196d3  xor     r8d, r8d
0x1800196d6  test    esi, esi
0x1800196d8  jnz     short loc_1800196E9
0x1800196da  lea     rax, a22313383; "2.23.133.8.3"
0x1800196e1  mov     [rbp+57h+var_98], rax
0x1800196e5  lea     r8d, [rsi+1]; unsigned int
0x1800196e9  mov     rax, [rbp+57h+phChainEngine]
0x1800196ed  lea     r9, [rbp+57h+var_98]; char **
0x1800196f1  mov     [rsp+0E0h+var_B0], 0; unsigned __int16 **
0x1800196fa  or      ebx, 40h
0x1800196fd  mov     edx, ebx; unsigned int
0x1800196ff  mov     [rsp+0E0h+var_B8], r15; void *
0x180019704  mov     rcx, r14; struct _CERT_CONTEXT *
0x180019707  mov     [rsp+0E0h+pvPara], rax; void *
0x18001970c  call    ?myVerifyCertContext@@YAJPEBU_CERT_CONTEXT@@KKPEBQEBDPEAX2PEAPEAG@Z; myVerifyCertContext(_CERT_CONTEXT const *,ulong,ulong,char const * const *,void *,void *,ushort * *)
0x180019711  mov     ebx, eax
0x180019713  test    eax, eax
0x180019715  jz      short loc_180019723
0x180019717  mov     ecx, 70A019Ah; unsigned int
0x18001971c  mov     edx, eax; int
0x18001971e  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180019723  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x180019727  test    rcx, rcx
0x18001972a  jz      short loc_180019734
0x18001972c  xor     edx, edx; dwFlags
0x18001972e  call    cs:__imp_CertCloseStore
0x180019734  test    rdi, rdi
0x180019737  jz      short loc_180019744
0x180019739  xor     edx, edx; dwFlags
0x18001973b  mov     rcx, rdi; hCertStore
0x18001973e  call    cs:__imp_CertCloseStore
0x180019744  mov     rcx, [rbp+57h+phChainEngine]; hChainEngine
0x180019748  test    rcx, rcx
0x18001974b  jz      short loc_180019753
0x18001974d  call    cs:__imp_CertFreeCertificateChainEngine
0x180019753  mov     eax, ebx
0x180019755  add     rsp, 0B8h
0x18001975c  pop     r15
0x18001975e  pop     r14
0x180019760  pop     rdi
0x180019761  pop     rsi
0x180019762  pop     rbx
0x180019763  pop     rbp
0x180019764  retn
```
