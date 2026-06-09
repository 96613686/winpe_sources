# _TpmEndorsementKeyGetEkCertificateStores(void * *,void * *)

- ea: `0x180002850`
- end: `0x180002b0a`
- name: `?_TpmEndorsementKeyGetEkCertificateStores@@YAJPEAPEAX0@Z`
- size: `698`
- prototype: `__int64 __fastcall(void **, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001970`
- `0x180002b10`

## callees

- `0x180002850`
- `0x180003750`

## import_xrefs

- `CRYPT32!CertAddCertificateContextToStore` at `0x180002a1a`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180002a1a`
- `CRYPT32!CertFreeCertificateContext` at `0x180002a4a`
- `CRYPT32!CertFreeCertificateContext` at `0x180002adf`
- `CRYPT32!CertFreeCertificateContext` at `0x180002a4a`
- `CRYPT32!CertFreeCertificateContext` at `0x180002adf`
- `CRYPT32!CertFindCertificateInStore` at `0x180002a00`
- `CRYPT32!CertFindCertificateInStore` at `0x180002a00`
- `CRYPT32!CertOpenStore` at `0x180002997`
- `CRYPT32!CertOpenStore` at `0x180002997`
- `CRYPT32!CertCloseStore` at `0x180002aac`
- `CRYPT32!CertCloseStore` at `0x180002abc`
- `CRYPT32!CertCloseStore` at `0x180002ad1`
- `CRYPT32!CertCloseStore` at `0x180002aac`
- `CRYPT32!CertCloseStore` at `0x180002abc`
- `CRYPT32!CertCloseStore` at `0x180002ad1`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800029d5`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800029d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a24`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800028b3`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800028b3`
- `ncrypt!NCryptGetProperty` at `0x1800028fe`
- `ncrypt!NCryptGetProperty` at `0x180002946`
- `ncrypt!NCryptGetProperty` at `0x1800028fe`
- `ncrypt!NCryptGetProperty` at `0x180002946`
- `ncrypt!NCryptFreeObject` at `0x180002a9a`
- `ncrypt!NCryptFreeObject` at `0x180002a9a`

## string_xrefs

- `0x1800028c2`: `ERROR: NCryptOpenStorageProvider. Hr=%x\n`
- `0x1800029ba`: `ERROR: CertOpenStore. Hr=%x\n`

## pseudocode

```c
__int64 __fastcall _TpmEndorsementKeyGetEkCertificateStores(void **a1, void **a2)
{
  HCERTSTORE v4; // rsi
  const CERT_CONTEXT *v5; // rdi
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int Property; // eax
  unsigned int v9; // eax
  signed int LastError; // eax
  const char *v11; // r8
  unsigned int v12; // ecx
  const CERT_CONTEXT *i; // rdx
  PCCERT_CONTEXT v14; // rax
  const CERT_CONTEXT *CertificateInStore; // rax
  signed int v16; // eax
  HCERTSTORE v17; // rax
  DWORD pcbResult; // [rsp+70h] [rbp+8h] BYREF
  HCERTSTORE v20; // [rsp+78h] [rbp+10h] BYREF
  HCERTSTORE pbOutput; // [rsp+80h] [rbp+18h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+88h] [rbp+20h] BYREF

  ekTraceFmt(0x20912C2u, 2, "TRACE: _TpmEndorsementKeyGetEkCertificateStores start.\n");
  phProvider = 0;
  v20 = 0;
  pbOutput = 0;
  v4 = 0;
  pcbResult = 0;
  v5 = 0;
  *a1 = 0;
  *a2 = 0;
  v6 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0x40u);
  v7 = v6;
  if ( v6 )
  {
    ekTraceFmt(0x21B12C2u, 1, "ERROR: NCryptOpenStorageProvider. Hr=%x\n", v6);
    goto LABEL_25;
  }
  Property = NCryptGetProperty(phProvider, L"PCP_EKCERT", (PBYTE)&pbOutput, 8u, &pcbResult, 0);
  v7 = Property;
  if ( Property )
  {
    ekTraceFmt(0x22D12C2u, 1, "ERROR: NCryptGetProperty(EKCERT). Hr=%x\n", Property);
    goto LABEL_25;
  }
  v9 = NCryptGetProperty(phProvider, L"PCP_EKNVCERT", (PBYTE)&v20, 8u, &pcbResult, 0);
  v7 = v9;
  if ( v9 )
  {
    ekTraceFmt(0x24012C2u, 1, "ERROR: NCryptGetProperty(EKNVCERT). Hr=%x\n", v9);
    goto LABEL_25;
  }
  if ( !pbOutput || !v20 )
  {
    v7 = -2147024809;
    v11 = "ERROR: NCryptGetProperty. Hr=%x\n";
    v12 = 38212290;
    goto LABEL_24;
  }
  v4 = CertOpenStore((LPCSTR)2, 1u, 0, 0x2000u, 0);
  if ( !v4 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v11 = "ERROR: CertOpenStore. Hr=%x\n";
    v12 = 39064258;
    goto LABEL_24;
  }
  for ( i = 0; ; i = v5 )
  {
    v14 = CertEnumCertificatesInStore(pbOutput, i);
    v5 = v14;
    if ( !v14 )
    {
      v17 = v20;
      v7 = 0;
      *a2 = v4;
      v4 = 0;
      *a1 = v17;
      v20 = 0;
      goto LABEL_25;
    }
    CertificateInStore = CertFindCertificateInStore(v20, 1u, 0, 0xD0000u, v14, 0);
    if ( !CertificateInStore )
      break;
    CertFreeCertificateContext(CertificateInStore);
LABEL_21:
    ;
  }
  if ( CertAddCertificateContextToStore(v4, v5, 4u, 0) )
    goto LABEL_21;
  v16 = GetLastError();
  v7 = v16;
  if ( v16 > 0 )
    v7 = (unsigned __int16)v16 | 0x80070000;
  v11 = "ERROR: CertAddCertificateContextToStore. Hr=%x\n";
  v12 = 41095874;
LABEL_24:
  ekTraceFmt(v12, 1, v11, v7);
LABEL_25:
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( v20 )
    CertCloseStore(v20, 0);
  if ( v4 )
    CertCloseStore(v4, 0);
  if ( pbOutput )
    CertCloseStore(pbOutput, 0);
  if ( v5 )
    CertFreeCertificateContext(v5);
  ekTraceFmt(0x29A12C2u, 2, "TRACE: _TpmEndorsementKeyGetEkCertificateStores end.\n");
  return v7;
}

```

## disassembly

```asm
0x180002850  push    rbx
0x180002852  push    rbp
0x180002853  push    rsi
0x180002854  push    rdi
0x180002855  push    r14
0x180002857  push    r15
0x180002859  sub     rsp, 38h
0x18000285d  mov     r14, rdx
0x180002860  lea     r8, aTraceTpmendors; "TRACE: _TpmEndorsementKeyGetEkCertifica"...
0x180002867  mov     r15, rcx
0x18000286a  mov     edx, 2; unsigned int
0x18000286f  mov     ecx, 20912C2h; unsigned int
0x180002874  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002879  xor     ebp, ebp
0x18000287b  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180002882  mov     r8d, 40h ; '@'; dwFlags
0x180002888  mov     [rsp+68h+phProvider], rbp
0x180002890  lea     rcx, [rsp+68h+phProvider]; phProvider
0x180002898  mov     [rsp+68h+arg_8], rbp
0x18000289d  mov     [rsp+68h+pbOutput], rbp
0x1800028a5  mov     esi, ebp
0x1800028a7  mov     [rsp+68h+arg_0], ebp
0x1800028ab  mov     edi, ebp
0x1800028ad  mov     [r15], rbp
0x1800028b0  mov     [r14], rbp
0x1800028b3  call    cs:__imp_NCryptOpenStorageProvider
0x1800028b9  mov     ebx, eax
0x1800028bb  test    eax, eax
0x1800028bd  jz      short loc_1800028D3
0x1800028bf  mov     r9d, eax
0x1800028c2  lea     r8, aErrorNcryptope; "ERROR: NCryptOpenStorageProvider. Hr=%x"...
0x1800028c9  mov     ecx, 21B12C2h
0x1800028ce  jmp     loc_180002A83
0x1800028d3  mov     rcx, [rsp+68h+phProvider]; hObject
0x1800028db  lea     rax, [rsp+68h+arg_0]
0x1800028e0  mov     [rsp+68h+dwFlags], ebp; dwFlags
0x1800028e4  lea     r8, [rsp+68h+pbOutput]; pbOutput
0x1800028ec  mov     r9d, 8; cbOutput
0x1800028f2  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1800028f7  lea     rdx, pszProperty; "PCP_EKCERT"
0x1800028fe  call    cs:__imp_NCryptGetProperty
0x180002904  mov     ebx, eax
0x180002906  test    eax, eax
0x180002908  jz      short loc_18000291E
0x18000290a  mov     r9d, eax
0x18000290d  lea     r8, aErrorNcryptget_2; "ERROR: NCryptGetProperty(EKCERT). Hr=%x"...
0x180002914  mov     ecx, 22D12C2h
0x180002919  jmp     loc_180002A83
0x18000291e  mov     rcx, [rsp+68h+phProvider]; hObject
0x180002926  lea     rax, [rsp+68h+arg_0]
0x18000292b  mov     [rsp+68h+dwFlags], ebp; dwFlags
0x18000292f  lea     r8, [rsp+68h+arg_8]; pbOutput
0x180002934  mov     r9d, 8; cbOutput
0x18000293a  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18000293f  lea     rdx, aPcpEknvcert; "PCP_EKNVCERT"
0x180002946  call    cs:__imp_NCryptGetProperty
0x18000294c  mov     ebx, eax
0x18000294e  test    eax, eax
0x180002950  jz      short loc_180002966
0x180002952  mov     r9d, eax
0x180002955  lea     r8, aErrorNcryptget_1; "ERROR: NCryptGetProperty(EKNVCERT). Hr="...
0x18000295c  mov     ecx, 24012C2h
0x180002961  jmp     loc_180002A83
0x180002966  cmp     [rsp+68h+pbOutput], rsi
0x18000296e  jz      loc_180002A6F
0x180002974  cmp     [rsp+68h+arg_8], rsi
0x180002979  jz      loc_180002A6F
0x18000297f  mov     r9d, 2000h; dwFlags
0x180002985  mov     [rsp+68h+pcbResult], rbp; pvPara
0x18000298a  xor     r8d, r8d; hCryptProv
0x18000298d  mov     edx, 1; dwEncodingType
0x180002992  mov     ecx, 2; lpszStoreProvider
0x180002997  call    cs:__imp_CertOpenStore
0x18000299d  mov     rsi, rax
0x1800029a0  test    rax, rax
0x1800029a3  jnz     short loc_1800029CB
0x1800029a5  call    cs:__imp_GetLastError
0x1800029ab  mov     ebx, eax
0x1800029ad  test    eax, eax
0x1800029af  jle     short loc_1800029BA
0x1800029b1  movzx   ebx, ax
0x1800029b4  or      ebx, 80070000h
0x1800029ba  lea     r8, aErrorCertopens_0; "ERROR: CertOpenStore. Hr=%x\n"
0x1800029c1  mov     ecx, 25412C2h
0x1800029c6  jmp     loc_180002A80
0x1800029cb  xor     edx, edx; pPrevCertContext
0x1800029cd  mov     rcx, [rsp+68h+pbOutput]; hCertStore
0x1800029d5  call    cs:__imp_CertEnumCertificatesInStore
0x1800029db  mov     rdi, rax
0x1800029de  test    rax, rax
0x1800029e1  jz      short loc_180002A58
0x1800029e3  mov     rcx, [rsp+68h+arg_8]; hCertStore
0x1800029e8  mov     r9d, 0D0000h; dwFindType
0x1800029ee  mov     qword ptr [rsp+68h+dwFlags], rbp; pPrevCertContext
0x1800029f3  xor     r8d, r8d; dwFindFlags
0x1800029f6  mov     edx, 1; dwCertEncodingType
0x1800029fb  mov     [rsp+68h+pcbResult], rax; pvFindPara
0x180002a00  call    cs:__imp_CertFindCertificateInStore
0x180002a06  test    rax, rax
0x180002a09  jnz     short loc_180002A47
0x180002a0b  xor     r9d, r9d; ppStoreContext
0x180002a0e  mov     r8d, 4; dwAddDisposition
0x180002a14  mov     rdx, rdi; pCertContext
0x180002a17  mov     rcx, rsi; hCertStore
0x180002a1a  call    cs:__imp_CertAddCertificateContextToStore
0x180002a20  test    eax, eax
0x180002a22  jnz     short loc_180002A50
0x180002a24  call    cs:__imp_GetLastError
0x180002a2a  mov     ebx, eax
0x180002a2c  test    eax, eax
0x180002a2e  jle     short loc_180002A39
0x180002a30  movzx   ebx, ax
0x180002a33  or      ebx, 80070000h
0x180002a39  lea     r8, aErrorCertaddce; "ERROR: CertAddCertificateContextToStore"...
0x180002a40  mov     ecx, 27312C2h
0x180002a45  jmp     short loc_180002A80
0x180002a47  mov     rcx, rax; pCertContext
0x180002a4a  call    cs:__imp_CertFreeCertificateContext
0x180002a50  mov     rdx, rdi
0x180002a53  jmp     loc_1800029CD
0x180002a58  mov     rax, [rsp+68h+arg_8]
0x180002a5d  mov     ebx, ebp
0x180002a5f  mov     [r14], rsi
0x180002a62  mov     rsi, rbp
0x180002a65  mov     [r15], rax
0x180002a68  mov     [rsp+68h+arg_8], rbp
0x180002a6d  jmp     short loc_180002A8D
0x180002a6f  mov     ebx, 80070057h
0x180002a74  lea     r8, aErrorNcryptget_3; "ERROR: NCryptGetProperty. Hr=%x\n"
0x180002a7b  mov     ecx, 24712C2h; unsigned int
0x180002a80  mov     r9d, ebx
0x180002a83  mov     edx, 1; unsigned int
0x180002a88  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002a8d  mov     rcx, [rsp+68h+phProvider]; hObject
0x180002a95  test    rcx, rcx
0x180002a98  jz      short loc_180002AA0
0x180002a9a  call    cs:__imp_NCryptFreeObject
0x180002aa0  mov     rcx, [rsp+68h+arg_8]; hCertStore
0x180002aa5  test    rcx, rcx
0x180002aa8  jz      short loc_180002AB2
0x180002aaa  xor     edx, edx; dwFlags
0x180002aac  call    cs:__imp_CertCloseStore
0x180002ab2  test    rsi, rsi
0x180002ab5  jz      short loc_180002AC2
0x180002ab7  xor     edx, edx; dwFlags
0x180002ab9  mov     rcx, rsi; hCertStore
0x180002abc  call    cs:__imp_CertCloseStore
0x180002ac2  mov     rcx, [rsp+68h+pbOutput]; hCertStore
0x180002aca  test    rcx, rcx
0x180002acd  jz      short loc_180002AD7
0x180002acf  xor     edx, edx; dwFlags
0x180002ad1  call    cs:__imp_CertCloseStore
0x180002ad7  test    rdi, rdi
0x180002ada  jz      short loc_180002AE5
0x180002adc  mov     rcx, rdi; pCertContext
0x180002adf  call    cs:__imp_CertFreeCertificateContext
0x180002ae5  lea     r8, aTraceTpmendors_0; "TRACE: _TpmEndorsementKeyGetEkCertifica"...
0x180002aec  mov     edx, 2; unsigned int
0x180002af1  mov     ecx, 29A12C2h; unsigned int
0x180002af6  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180002afb  mov     eax, ebx
0x180002afd  add     rsp, 38h
0x180002b01  pop     r15
0x180002b03  pop     r14
0x180002b05  pop     rdi
0x180002b06  pop     rsi
0x180002b07  pop     rbp
0x180002b08  pop     rbx
0x180002b09  retn
```
