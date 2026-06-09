# _drr_GetCertificateHash(DRR_ROAMING_TOKEN const *,uchar *,ulong *)

- ea: `0x1800047d4`
- end: `0x180004a26`
- name: `?_drr_GetCertificateHash@@YAKPEBUDRR_ROAMING_TOKEN@@PEAEPEAK@Z`
- size: `594`
- prototype: `__int64 __fastcall(const struct DRR_ROAMING_TOKEN *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003fb4`

## callees

- `0x1800047d4`
- `0x180004a84`
- `0x180004c58`
- `0x18000d892`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000496a`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000496a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000484e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000490f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004932`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000484e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000490f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004932`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000499a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800049ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004a1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000499a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800049ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004a1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049e0`
- `CRYPT32!CertFreeCertificateContext` at `0x1800049f1`
- `CRYPT32!CertFreeCertificateContext` at `0x1800049f1`
- `CRYPT32!CryptHashCertificate` at `0x1800049d6`
- `CRYPT32!CryptHashCertificate` at `0x1800049d6`
- `CRYPT32!CertAddSerializedElementToStore` at `0x180004830`
- `CRYPT32!CertAddSerializedElementToStore` at `0x180004830`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800048f0`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000494d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800048f0`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000494d`

## pseudocode

```c
__int64 __fastcall _drr_GetCertificateHash(const struct DRR_ROAMING_TOKEN *a1, unsigned __int8 *a2, unsigned int *a3)
{
  DWORD v3; // r8d
  BYTE *v4; // rdi
  SIZE_T cbCertEncoded; // r13
  BYTE *v6; // rax
  DWORD LastError; // ebx
  __int64 v8; // r15
  unsigned int v9; // esi
  const CERT_CONTEXT *v10; // r12
  HLOCAL v11; // rbx
  DWORD v12; // r14d
  int v13; // eax
  HLOCAL v14; // rax
  HLOCAL v15; // rax
  BYTE *v16; // rax
  DWORD Src; // [rsp+40h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-20h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+50h] [rbp-18h] BYREF
  DWORD pcbData; // [rsp+B0h] [rbp+48h] BYREF
  BYTE *pbComputedHash; // [rsp+B8h] [rbp+50h]
  DWORD *pcbComputedHash; // [rsp+C0h] [rbp+58h]
  size_t Size; // [rsp+C8h] [rbp+60h] BYREF

  pcbComputedHash = a3;
  pbComputedHash = a2;
  v3 = *((_DWORD *)a1 + 32);
  pCertContext = 0;
  if ( !CertAddSerializedElementToStore(0, (const BYTE *)a1 + 132, v3, 4u, 0, 2u, 0, (const void **)&pCertContext) )
  {
    v4 = 0;
LABEL_25:
    LastError = GetLastError();
    goto LABEL_26;
  }
  cbCertEncoded = pCertContext->cbCertEncoded;
  v6 = (BYTE *)LocalAlloc(0, cbCertEncoded);
  v4 = v6;
  if ( !v6 )
    goto LABEL_4;
  memcpy_0(v6, pCertContext->pbCertEncoded, cbCertEncoded);
  v8 = 0;
  if ( !dword_180013890 )
  {
LABEL_24:
    LastError = 0;
    if ( CryptHashCertificate(0, 0x8004u, 0, v4, cbCertEncoded, pbComputedHash, pcbComputedHash) )
      goto LABEL_26;
    goto LABEL_25;
  }
  while ( 1 )
  {
    v9 = 0;
    v10 = pCertContext;
    v11 = 0;
    LODWORD(Size) = 0;
    pcbData = 0;
    v12 = *((_DWORD *)::hMem + v8);
    Src = v12;
    hMem = 0;
    if ( v12 == 2 )
    {
      v13 = _drr_MarshalKeyProvInfoContextProperty(pCertContext, &hMem, (unsigned int *)&Size);
      goto LABEL_10;
    }
    if ( v12 == 9 )
    {
      v13 = _drr_MarshalEKUContextProperty(pCertContext, &hMem, (unsigned int *)&Size);
LABEL_10:
      v11 = hMem;
      if ( v13 )
      {
        v9 = Size;
        goto LABEL_19;
      }
      goto LABEL_21;
    }
    if ( !CertGetCertificateContextProperty(pCertContext, v12, 0, &pcbData) )
      goto LABEL_21;
    if ( !pcbData )
      break;
    v15 = LocalAlloc(0, pcbData);
    v11 = v15;
    if ( v15 && CertGetCertificateContextProperty(v10, v12, v15, &pcbData) )
      goto LABEL_18;
LABEL_21:
    if ( v11 )
      goto LABEL_22;
LABEL_23:
    v8 = (unsigned int)(v8 + 1);
    if ( (unsigned int)v8 >= dword_180013890 )
      goto LABEL_24;
  }
  pcbData = 4;
  v14 = LocalAlloc(0, 4u);
  v11 = v14;
  if ( !v14 )
    goto LABEL_19;
  memcpy_0(v14, &Src, pcbData);
LABEL_18:
  v9 = pcbData;
LABEL_19:
  v16 = (BYTE *)LocalReAlloc(v4, v9 + (unsigned int)cbCertEncoded, 2u);
  if ( v16 )
  {
    v4 = v16;
    memcpy_0(&v16[(unsigned int)cbCertEncoded], v11, v9);
    LODWORD(cbCertEncoded) = v9 + cbCertEncoded;
LABEL_22:
    LocalFree(v11);
    goto LABEL_23;
  }
  LocalFree(v4);
LABEL_4:
  LastError = 8;
LABEL_26:
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v4 )
    LocalFree(v4);
  return LastError;
}

```

## disassembly

```asm
0x1800047d4  mov     r11, rsp
0x1800047d7  mov     [r11+18h], r8
0x1800047db  mov     [r11+10h], rdx
0x1800047df  push    rbp
0x1800047e0  push    rbx
0x1800047e1  push    rsi
0x1800047e2  push    rdi
0x1800047e3  push    r12
0x1800047e5  push    r13
0x1800047e7  push    r14
0x1800047e9  push    r15
0x1800047eb  mov     rbp, rsp
0x1800047ee  sub     rsp, 68h
0x1800047f2  mov     r8d, [rcx+80h]; cbElement
0x1800047f9  lea     rax, [rbp+pCertContext]
0x1800047fd  mov     [r11-70h], rax
0x180004801  lea     rdx, [rcx+84h]; pbElement
0x180004808  mov     qword ptr [r11-78h], 0
0x180004810  mov     r9d, 4; dwAddDisposition
0x180004816  mov     [rsp+68h+dwContextTypeFlags], 2; dwContextTypeFlags
0x18000481e  xor     ecx, ecx; hCertStore
0x180004820  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180004828  mov     [rbp+pCertContext], 0
0x180004830  call    cs:__imp_CertAddSerializedElementToStore
0x180004836  test    eax, eax
0x180004838  jnz     short loc_180004841
0x18000483a  xor     edi, edi
0x18000483c  jmp     loc_1800049E0
0x180004841  mov     rax, [rbp+pCertContext]
0x180004845  xor     ecx, ecx; uFlags
0x180004847  mov     r13d, [rax+10h]
0x18000484b  mov     edx, r13d; uBytes
0x18000484e  call    cs:__imp_LocalAlloc
0x180004854  mov     rdi, rax
0x180004857  test    rax, rax
0x18000485a  jnz     short loc_180004866
0x18000485c  mov     ebx, 8
0x180004861  jmp     loc_1800049E8
0x180004866  mov     rdx, [rbp+pCertContext]
0x18000486a  mov     r8, r13; Size
0x18000486d  mov     rcx, rax; void *
0x180004870  mov     rdx, [rdx+8]; Src
0x180004874  call    memcpy_0
0x180004879  xor     r15d, r15d
0x18000487c  cmp     cs:dword_180013890, r15d
0x180004883  jbe     loc_1800049B0
0x180004889  mov     rax, cs:hMem
0x180004890  xor     esi, esi
0x180004892  mov     r12, [rbp+pCertContext]
0x180004896  xor     ebx, ebx
0x180004898  mov     dword ptr [rbp+Size], esi
0x18000489b  mov     rcx, r12; pCertContext
0x18000489e  mov     [rbp+pcbData], esi
0x1800048a1  mov     r14d, [rax+r15*4]
0x1800048a5  mov     [rbp+Src], r14d
0x1800048a9  mov     [rbp+hMem], rbx
0x1800048ad  cmp     r14d, 2
0x1800048b1  jnz     short loc_1800048C2
0x1800048b3  lea     r8, [rbp+Size]; unsigned int *
0x1800048b7  lea     rdx, [rbp+hMem]; void **
0x1800048bb  call    ?_drr_MarshalKeyProvInfoContextProperty@@YAHPEBU_CERT_CONTEXT@@PEAPEAXPEAK@Z; _drr_MarshalKeyProvInfoContextProperty(_CERT_CONTEXT const *,void * *,ulong *)
0x1800048c0  jmp     short loc_1800048D5
0x1800048c2  cmp     r14d, 9
0x1800048c6  jnz     short loc_1800048E6
0x1800048c8  lea     r8, [rbp+Size]; unsigned int *
0x1800048cc  lea     rdx, [rbp+hMem]; void **
0x1800048d0  call    ?_drr_MarshalEKUContextProperty@@YAHPEBU_CERT_CONTEXT@@PEAPEAXPEAK@Z; _drr_MarshalEKUContextProperty(_CERT_CONTEXT const *,void * *,ulong *)
0x1800048d5  mov     rbx, [rbp+hMem]
0x1800048d9  test    eax, eax
0x1800048db  jz      loc_180004992
0x1800048e1  mov     esi, dword ptr [rbp+Size]
0x1800048e4  jmp     short loc_18000495A
0x1800048e6  lea     r9, [rbp+pcbData]; pcbData
0x1800048ea  xor     r8d, r8d; pvData
0x1800048ed  mov     edx, r14d; dwPropId
0x1800048f0  call    cs:__imp_CertGetCertificateContextProperty
0x1800048f6  test    eax, eax
0x1800048f8  jz      loc_180004992
0x1800048fe  mov     eax, [rbp+pcbData]
0x180004901  xor     ecx, ecx; uFlags
0x180004903  test    eax, eax
0x180004905  jnz     short loc_18000492F
0x180004907  lea     eax, [rcx+4]
0x18000490a  mov     edx, eax; uBytes
0x18000490c  mov     [rbp+pcbData], eax
0x18000490f  call    cs:__imp_LocalAlloc
0x180004915  mov     rbx, rax
0x180004918  test    rax, rax
0x18000491b  jz      short loc_18000495A
0x18000491d  mov     r8d, [rbp+pcbData]; Size
0x180004921  lea     rdx, [rbp+Src]; Src
0x180004925  mov     rcx, rax; void *
0x180004928  call    memcpy_0
0x18000492d  jmp     short loc_180004957
0x18000492f  mov     rdx, rax; uBytes
0x180004932  call    cs:__imp_LocalAlloc
0x180004938  mov     rbx, rax
0x18000493b  test    rax, rax
0x18000493e  jz      short loc_180004992
0x180004940  lea     r9, [rbp+pcbData]; pcbData
0x180004944  mov     r8, rax; pvData
0x180004947  mov     edx, r14d; dwPropId
0x18000494a  mov     rcx, r12; pCertContext
0x18000494d  call    cs:__imp_CertGetCertificateContextProperty
0x180004953  test    eax, eax
0x180004955  jz      short loc_180004992
0x180004957  mov     esi, [rbp+pcbData]
0x18000495a  lea     r14d, [rsi+r13]
0x18000495e  mov     r8d, 2; uFlags
0x180004964  mov     edx, r14d; uBytes
0x180004967  mov     rcx, rdi; hMem
0x18000496a  call    cs:__imp_LocalReAlloc
0x180004970  test    rax, rax
0x180004973  jz      loc_180004A18
0x180004979  mov     ecx, r13d
0x18000497c  mov     rdx, rbx; Src
0x18000497f  add     rcx, rax; void *
0x180004982  mov     r8d, esi; Size
0x180004985  mov     rdi, rax
0x180004988  call    memcpy_0
0x18000498d  mov     r13d, r14d
0x180004990  jmp     short loc_180004997
0x180004992  test    rbx, rbx
0x180004995  jz      short loc_1800049A0
0x180004997  mov     rcx, rbx; hMem
0x18000499a  call    cs:__imp_LocalFree
0x1800049a0  inc     r15d
0x1800049a3  cmp     r15d, cs:dword_180013890
0x1800049aa  jb      loc_180004889
0x1800049b0  mov     rax, [rbp+arg_10]
0x1800049b4  mov     r9, rdi; pbEncoded
0x1800049b7  mov     [rsp+68h+pcbComputedHash], rax; pcbComputedHash
0x1800049bc  xor     r8d, r8d; dwFlags
0x1800049bf  mov     rax, [rbp+pbComputedHash]
0x1800049c3  mov     edx, 8004h; Algid
0x1800049c8  mov     qword ptr [rsp+68h+dwContextTypeFlags], rax; pbComputedHash
0x1800049cd  xor     ecx, ecx; hCryptProv
0x1800049cf  mov     [rsp+68h+dwFlags], r13d; cbEncoded
0x1800049d4  xor     ebx, ebx
0x1800049d6  call    cs:__imp_CryptHashCertificate
0x1800049dc  test    eax, eax
0x1800049de  jnz     short loc_1800049E8
0x1800049e0  call    cs:__imp_GetLastError
0x1800049e6  mov     ebx, eax
0x1800049e8  mov     rcx, [rbp+pCertContext]; pCertContext
0x1800049ec  test    rcx, rcx
0x1800049ef  jz      short loc_1800049F7
0x1800049f1  call    cs:__imp_CertFreeCertificateContext
0x1800049f7  test    rdi, rdi
0x1800049fa  jz      short loc_180004A05
0x1800049fc  mov     rcx, rdi; hMem
0x1800049ff  call    cs:__imp_LocalFree
0x180004a05  mov     eax, ebx
0x180004a07  add     rsp, 68h
0x180004a0b  pop     r15
0x180004a0d  pop     r14
0x180004a0f  pop     r13
0x180004a11  pop     r12
0x180004a13  pop     rdi
0x180004a14  pop     rsi
0x180004a15  pop     rbx
0x180004a16  pop     rbp
0x180004a17  retn
0x180004a18  mov     rcx, rdi; hMem
0x180004a1b  call    cs:__imp_LocalFree
0x180004a21  jmp     loc_18000485C
```
