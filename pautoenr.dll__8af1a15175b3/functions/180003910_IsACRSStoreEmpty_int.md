# IsACRSStoreEmpty(int)

- ea: `0x180003910`
- end: `0x180003a28`
- name: `?IsACRSStoreEmpty@@YAHH@Z`
- size: `280`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d90`

## callees

- `0x180003910`

## import_xrefs

- `CRYPT32!CertRegisterPhysicalStore` at `0x180003983`
- `CRYPT32!CertRegisterPhysicalStore` at `0x180003983`
- `CRYPT32!CertOpenStore` at `0x1800039a6`
- `CRYPT32!CertOpenStore` at `0x1800039a6`
- `CRYPT32!CertCloseStore` at `0x180003a14`
- `CRYPT32!CertCloseStore` at `0x180003a14`
- `CRYPT32!CertFindCTLInStore` at `0x1800039f9`
- `CRYPT32!CertFindCTLInStore` at `0x1800039f9`
- `CRYPT32!CertFreeCTLContext` at `0x180003a09`
- `CRYPT32!CertFreeCTLContext` at `0x180003a09`

## pseudocode

```c
__int64 __fastcall IsACRSStoreEmpty(int a1)
{
  DWORD v1; // edi
  unsigned int v2; // ebx
  HCERTSTORE v3; // rdi
  const CTL_CONTEXT *CTLInStore; // rax
  __int128 pvFindPara; // [rsp+30h] [rbp-88h] BYREF
  __int128 v7; // [rsp+40h] [rbp-78h]
  __int128 v8; // [rsp+50h] [rbp-68h]
  struct _CERT_PHYSICAL_STORE_INFO v9; // [rsp+60h] [rbp-58h] BYREF
  const char *v10; // [rsp+C8h] [rbp+10h] BYREF

  v10 = 0;
  v1 = 163840;
  v2 = 1;
  pvFindPara = 0;
  v7 = 0;
  v8 = 0;
  memset(&v9, 0, sizeof(v9));
  if ( a1
    || (v9.cbSize = 48,
        v9.dwFlags = 2,
        v1 = 98304,
        CertRegisterPhysicalStore(L"ACRS", 0x10000u, L".LocalMachine", &v9, 0)) )
  {
    v3 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, v1, L"ACRS");
    if ( v3 )
    {
      v10 = "1.3.6.1.4.1.311.20.1";
      LODWORD(pvFindPara) = 48;
      *(_QWORD *)&v7 = &v10;
      DWORD2(pvFindPara) = 1;
      CTLInStore = CertFindCTLInStore(v3, 1u, 1u, 3u, &pvFindPara, 0);
      if ( CTLInStore )
      {
        v2 = 0;
        CertFreeCTLContext(CTLInStore);
      }
      CertCloseStore(v3, 0);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180003910  mov     rax, rsp
0x180003913  push    rbx
0x180003914  push    rbp
0x180003915  push    rsi
0x180003916  push    rdi
0x180003917  sub     rsp, 98h
0x18000391e  xorps   xmm1, xmm1
0x180003921  lea     rsi, aAcrs; "ACRS"
0x180003928  xorps   xmm0, xmm0
0x18000392b  xor     ebp, ebp
0x18000392d  mov     [rax+10h], rbp
0x180003931  mov     edi, 28000h
0x180003936  mov     ebx, 1
0x18000393b  movups  [rsp+0B8h+pvFindPara], xmm1
0x180003940  movups  xmmword ptr [rax-78h], xmm1
0x180003944  movups  xmmword ptr [rax-68h], xmm1
0x180003948  movups  xmmword ptr [rax-58h], xmm0
0x18000394c  movups  xmmword ptr [rax-48h], xmm0
0x180003950  movups  xmmword ptr [rax-38h], xmm0
0x180003954  test    ecx, ecx
0x180003956  jnz     short loc_180003991
0x180003958  lea     r9, [rax-58h]; pStoreInfo
0x18000395c  mov     dword ptr [rax-58h], 30h ; '0'
0x180003963  lea     r8, pwszStoreName; ".LocalMachine"
0x18000396a  mov     dword ptr [rax-30h], 2
0x180003971  mov     edx, 10000h; dwFlags
0x180003976  mov     [rsp+0B8h+pvReserved], rbp; pvReserved
0x18000397b  mov     rcx, rsi; pvSystemStore
0x18000397e  mov     edi, 18000h
0x180003983  call    cs:__imp_CertRegisterPhysicalStore
0x180003989  test    eax, eax
0x18000398b  jz      loc_180003A1A
0x180003991  mov     r9d, edi; dwFlags
0x180003994  mov     [rsp+0B8h+pvReserved], rsi; pvPara
0x180003999  xor     r8d, r8d; hCryptProv
0x18000399c  mov     edx, 10001h; dwEncodingType
0x1800039a1  mov     ecx, 0Ah; lpszStoreProvider
0x1800039a6  call    cs:__imp_CertOpenStore
0x1800039ac  mov     rdi, rax
0x1800039af  test    rax, rax
0x1800039b2  jz      short loc_180003A1A
0x1800039b4  lea     rax, a136141311201; "1.3.6.1.4.1.311.20.1"
0x1800039bb  mov     [rsp+0B8h+pPrevCtlContext], rbp; pPrevCtlContext
0x1800039c0  mov     [rsp+0B8h+arg_8], rax
0x1800039c8  mov     r9d, 3; dwFindType
0x1800039ce  lea     rax, [rsp+0B8h+arg_8]
0x1800039d6  mov     dword ptr [rsp+0B8h+pvFindPara], 30h ; '0'
0x1800039de  mov     qword ptr [rsp+0B8h+var_78], rax
0x1800039e3  mov     r8d, ebx; dwFindFlags
0x1800039e6  lea     rax, [rsp+0B8h+pvFindPara]
0x1800039eb  mov     dword ptr [rsp+0B8h+pvFindPara+8], ebx
0x1800039ef  mov     edx, ebx; dwMsgAndCertEncodingType
0x1800039f1  mov     [rsp+0B8h+pvReserved], rax; pvFindPara
0x1800039f6  mov     rcx, rdi; hCertStore
0x1800039f9  call    cs:__imp_CertFindCTLInStore
0x1800039ff  test    rax, rax
0x180003a02  jz      short loc_180003A0F
0x180003a04  mov     ebx, ebp
0x180003a06  mov     rcx, rax; pCtlContext
0x180003a09  call    cs:__imp_CertFreeCTLContext
0x180003a0f  xor     edx, edx; dwFlags
0x180003a11  mov     rcx, rdi; hCertStore
0x180003a14  call    cs:__imp_CertCloseStore
0x180003a1a  mov     eax, ebx
0x180003a1c  add     rsp, 98h
0x180003a23  pop     rdi
0x180003a24  pop     rsi
0x180003a25  pop     rbp
0x180003a26  pop     rbx
0x180003a27  retn
```
