# SetNewCaConfig(ulong,MQ_CA_CONFIG *,HKEY__ *)

- ea: `0x180009ee4`
- end: `0x18000a02d`
- name: `?SetNewCaConfig@@YAJKPEAVMQ_CA_CONFIG@@PEAUHKEY__@@@Z`
- size: `329`
- prototype: `int(unsigned int, struct MQ_CA_CONFIG *, HKEY)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007f20`

## callees

- `0x180005d68`
- `0x180005d8c`
- `0x180009ee4`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x180009f16`
- `CRYPT32!CertOpenStore` at `0x180009f16`
- `CRYPT32!CertFindCertificateInStore` at `0x180009f8a`
- `CRYPT32!CertFindCertificateInStore` at `0x180009f8a`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180009fa4`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180009fa4`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180009fdb`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180009fdb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetNewCaConfig(unsigned int a1, struct MQ_CA_CONFIG *a2, HKEY pvPara)
{
  HCERTSTORE v5; // rbx
  __int64 i; // rdi
  const CERT_CONTEXT *CertificateInStore; // rax
  unsigned int v9; // ebx
  HCERTSTORE v10; // [rsp+30h] [rbp-38h] BYREF
  _DWORD pvFindPara[2]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v12; // [rsp+40h] [rbp-28h]
  _QWORD pvData[4]; // [rsp+48h] [rbp-20h] BYREF
  const CERT_CONTEXT *v14; // [rsp+B8h] [rbp+50h] BYREF

  v5 = CertOpenStore((LPCSTR)4, 0x10001u, 0, 0, pvPara);
  v10 = v5;
  if ( v5 )
  {
    for ( i = 0; (unsigned int)i < a1; i = (unsigned int)(i + 1) )
    {
      v14 = 0;
      pvFindPara[0] = *((_DWORD *)a2 + 10 * i + 6);
      pvFindPara[1] = 0;
      v12 = *((_QWORD *)a2 + 5 * i + 2);
      CertificateInStore = CertFindCertificateInStore(v5, 1u, 0, 0x10000u, pvFindPara, 0);
      v14 = CertificateInStore;
      if ( !CertificateInStore )
        goto LABEL_12;
      if ( *((_DWORD *)a2 + 10 * i + 8) )
      {
        if ( !CertDeleteCertificateFromStore(CertificateInStore) )
        {
LABEL_12:
          CPCCertContext::~CPCCertContext((CPCCertContext *)&v14);
          goto LABEL_2;
        }
        v14 = 0;
      }
      else
      {
        pvData[0] = 4;
        pvData[1] = (char *)a2 + 40 * i + 28;
        if ( !CertSetCertificateContextProperty(CertificateInStore, 0x8000u, 0, pvData) )
        {
          CPCCertContext::~CPCCertContext((CPCCertContext *)&v14);
          v9 = -1072824319;
          goto LABEL_14;
        }
      }
      CPCCertContext::~CPCCertContext((CPCCertContext *)&v14);
    }
    v9 = 0;
LABEL_14:
    CHCertStore::~CHCertStore((CHCertStore *)&v10);
    return v9;
  }
  else
  {
LABEL_2:
    CHCertStore::~CHCertStore((CHCertStore *)&v10);
    return 3222142977LL;
  }
}

```

## disassembly

```asm
0x180009ee4  push    rbp
0x180009ee6  push    rbx
0x180009ee7  push    rsi
0x180009ee8  push    rdi
0x180009ee9  push    r14
0x180009eeb  push    r15
0x180009eed  mov     rbp, rsp
0x180009ef0  sub     rsp, 68h
0x180009ef4  mov     rsi, rdx
0x180009ef7  mov     r15d, ecx
0x180009efa  mov     [rbp+var_38], 0
0x180009f02  mov     [rsp+68h+pvPara], r8; pvPara
0x180009f07  xor     r9d, r9d; dwFlags
0x180009f0a  xor     r8d, r8d; hCryptProv
0x180009f0d  mov     edx, 10001h; dwEncodingType
0x180009f12  lea     ecx, [r9+4]; lpszStoreProvider
0x180009f16  call    cs:__imp_CertOpenStore
0x180009f1c  mov     rbx, rax
0x180009f1f  mov     [rbp+var_38], rax
0x180009f23  test    rax, rax
0x180009f26  jnz     short loc_180009F3B
0x180009f28  lea     rcx, [rbp+var_38]; this
0x180009f2c  call    ??1CHCertStore@@QEAA@XZ; CHCertStore::~CHCertStore(void)
0x180009f31  mov     eax, 0C00E0001h
0x180009f36  jmp     loc_18000A020
0x180009f3b  xor     edi, edi
0x180009f3d  cmp     edi, r15d
0x180009f40  jnb     loc_18000A013
0x180009f46  mov     [rbp+arg_18], 0
0x180009f4e  lea     r14, [rdi+rdi*4]
0x180009f52  mov     eax, [rsi+r14*8+18h]
0x180009f57  mov     [rbp+pvFindPara], eax
0x180009f5a  xor     eax, eax
0x180009f5c  mov     [rbp+var_2C], eax
0x180009f5f  mov     rax, [rsi+r14*8+10h]
0x180009f64  mov     [rbp+var_28], rax
0x180009f68  mov     [rsp+68h+pPrevCertContext], 0; pPrevCertContext
0x180009f71  lea     rax, [rbp+pvFindPara]
0x180009f75  mov     [rsp+68h+pvPara], rax; pvFindPara
0x180009f7a  mov     r9d, 10000h; dwFindType
0x180009f80  xor     r8d, r8d; dwFindFlags
0x180009f83  lea     edx, [r8+1]; dwCertEncodingType
0x180009f87  mov     rcx, rbx; hCertStore
0x180009f8a  call    cs:__imp_CertFindCertificateInStore
0x180009f90  mov     [rbp+arg_18], rax
0x180009f94  test    rax, rax
0x180009f97  jz      short loc_18000A005
0x180009f99  cmp     dword ptr [rsi+r14*8+20h], 0
0x180009f9f  jz      short loc_180009FB8
0x180009fa1  mov     rcx, rax; pCertContext
0x180009fa4  call    cs:__imp_CertDeleteCertificateFromStore
0x180009faa  test    eax, eax
0x180009fac  jz      short loc_18000A005
0x180009fae  mov     [rbp+arg_18], 0
0x180009fb6  jmp     short loc_180009FE5
0x180009fb8  mov     [rbp+pvData], 4
0x180009fc0  lea     rcx, [rsi+1Ch]
0x180009fc4  lea     rcx, [rcx+r14*8]
0x180009fc8  mov     [rbp+var_18], rcx
0x180009fcc  lea     r9, [rbp+pvData]; pvData
0x180009fd0  xor     r8d, r8d; dwFlags
0x180009fd3  mov     edx, 8000h; dwPropId
0x180009fd8  mov     rcx, rax; pCertContext
0x180009fdb  call    cs:__imp_CertSetCertificateContextProperty
0x180009fe1  test    eax, eax
0x180009fe3  jz      short loc_180009FF5
0x180009fe5  lea     rcx, [rbp+arg_18]; this
0x180009fe9  call    ??1CPCCertContext@@QEAA@XZ; CPCCertContext::~CPCCertContext(void)
0x180009fee  inc     edi
0x180009ff0  jmp     loc_180009F3D
0x180009ff5  lea     rcx, [rbp+arg_18]; this
0x180009ff9  call    ??1CPCCertContext@@QEAA@XZ; CPCCertContext::~CPCCertContext(void)
0x180009ffe  mov     ebx, 0C00E0001h
0x18000a003  jmp     short loc_18000A015
0x18000a005  lea     rcx, [rbp+arg_18]; this
0x18000a009  call    ??1CPCCertContext@@QEAA@XZ; CPCCertContext::~CPCCertContext(void)
0x18000a00e  jmp     loc_180009F28
0x18000a013  xor     ebx, ebx
0x18000a015  lea     rcx, [rbp+var_38]; this
0x18000a019  call    ??1CHCertStore@@QEAA@XZ; CHCertStore::~CHCertStore(void)
0x18000a01e  mov     eax, ebx
0x18000a020  add     rsp, 68h
0x18000a024  pop     r15
0x18000a026  pop     r14
0x18000a028  pop     rdi
0x18000a029  pop     rsi
0x18000a02a  pop     rbx
0x18000a02b  pop     rbp
0x18000a02c  retn
```
