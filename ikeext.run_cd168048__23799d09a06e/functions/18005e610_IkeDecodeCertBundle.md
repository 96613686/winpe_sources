# IkeDecodeCertBundle

- ea: `0x18005e610`
- end: `0x18005e8ea`
- name: `IkeDecodeCertBundle`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18008c8cc`

## callees

- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x1800162a4`
- `0x180050850`
- `0x18005e610`
- `0x18008fe98`
- `0x18008ffe8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e823`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e823`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e848`
- `MSASN1!ASN1_CloseDecoder` at `0x18005e89a`
- `MSASN1!ASN1_CloseDecoder` at `0x18005e89a`
- `MSASN1!ASN1_FreeDecoded` at `0x18005e88b`
- `MSASN1!ASN1_FreeDecoded` at `0x18005e88b`
- `MSASN1!ASN1_Decode` at `0x18005e6d3`
- `MSASN1!ASN1_Decode` at `0x18005e6d3`
- `MSASN1!ASN1_CreateDecoder` at `0x18005e691`
- `MSASN1!ASN1_CreateDecoder` at `0x18005e691`
- `CRYPT32!CertCreateCertificateContext` at `0x18005e7ed`
- `CRYPT32!CertCreateCertificateContext` at `0x18005e7ed`
- `CRYPT32!CertCreateCRLContext` at `0x18005e807`
- `CRYPT32!CertCreateCRLContext` at `0x18005e807`

## string_xrefs

- `0x18005e84e`: `CertCreateCRLContext`
- `0x18005e829`: `CertCreateCertificateContext`

## pseudocode

```c
__int64 __fastcall IkeDecodeCertBundle(__int64 a1, int a2, _QWORD *a3, unsigned int *a4, _QWORD *a5, unsigned int *a6)
{
  __int64 v8; // r15
  unsigned int v9; // r12d
  __int64 v10; // r14
  unsigned int v11; // r13d
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rbx
  unsigned int v15; // r9d
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned int v19; // r12d
  unsigned int v20; // r13d
  unsigned int i; // esi
  __int64 v22; // rax
  DWORD v23; // r8d
  const BYTE *v24; // rdx
  PCCERT_CONTEXT CertificateContext; // rax
  PCCRL_CONTEXT CRLContext; // rax
  DWORD LastError; // eax
  __int64 v28; // rcx
  const char *v29; // rdx
  __int64 v30; // rax
  SIZE_T dwBytes; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v33; // [rsp+38h] [rbp-51h]
  __int64 v34; // [rsp+40h] [rbp-49h]
  __int64 v35; // [rsp+48h] [rbp-41h]
  _QWORD *v36; // [rsp+50h] [rbp-39h]
  unsigned int *v37; // [rsp+58h] [rbp-31h]
  _QWORD *v38; // [rsp+60h] [rbp-29h]
  unsigned int *v39; // [rsp+68h] [rbp-21h]
  __int64 v40; // [rsp+70h] [rbp-19h] BYREF
  __int64 v41; // [rsp+78h] [rbp-11h] BYREF

  v38 = a5;
  v39 = a6;
  v37 = a4;
  v8 = 0;
  v36 = a3;
  v34 = 0;
  v9 = 0;
  v10 = 0;
  v35 = 0;
  v11 = 0;
  v33 = 0;
  v40 = 0;
  v41 = 0;
  dwBytes = 0;
  if ( (int)ASN1_CreateDecoder(gIkeAsn1Module, &v41, 0, 0, 0) < 0 )
  {
    v13 = 14;
LABEL_3:
    v14 = WfpReportSysErrorAsWinError(v12, "IkeDecodeCertBundle", v13, 1);
    goto LABEL_29;
  }
  if ( (int)ASN1_Decode(v41, &v40, 0, 8, a1, a2) < 0 )
  {
    v13 = 87;
    goto LABEL_3;
  }
  v14 = 0;
  if ( !*(_DWORD *)v40 )
    goto LABEL_17;
  v15 = 0;
  do
  {
    v16 = v9 + 1;
    if ( *(_WORD *)(*(_QWORD *)(v40 + 8) + 24LL * v15) )
    {
      v16 = v9;
      ++v11;
    }
    ++v15;
    v9 = v16;
  }
  while ( v15 < *(_DWORD *)v40 );
  HIDWORD(dwBytes) = v16;
  v33 = v11;
  if ( !(_DWORD)v16
    || (v14 = WfpUINT32Multiply(v16, 8, &dwBytes)) == 0
    && (v17 = WfpMemAlloc((unsigned int)dwBytes, 8u), v8 = v34, (v14 = v17) == 0) )
  {
    if ( !v11
      || (v14 = WfpUINT32Multiply(v11, 8, &dwBytes)) == 0
      && (v18 = WfpMemAlloc((unsigned int)dwBytes, 8u), v10 = v35, (v14 = v18) == 0) )
    {
LABEL_17:
      v19 = 0;
      v20 = 0;
      for ( i = 0; i < *(_DWORD *)v40; ++i )
      {
        v22 = *(_QWORD *)(v40 + 8);
        v23 = *(_DWORD *)(v22 + 24LL * i + 8);
        v24 = *(const BYTE **)(v22 + 24LL * i + 16);
        if ( *(_WORD *)(v22 + 24LL * i) )
        {
          CRLContext = CertCreateCRLContext(1u, v24, v23);
          *(_QWORD *)(v10 + 8LL * v20) = CRLContext;
          if ( !CRLContext )
          {
            LastError = GetLastError();
            v29 = "CertCreateCRLContext";
            goto LABEL_26;
          }
          ++v20;
        }
        else
        {
          CertificateContext = CertCreateCertificateContext(1u, v24, v23);
          *(_QWORD *)(v8 + 8LL * v19) = CertificateContext;
          if ( !CertificateContext )
          {
            LastError = GetLastError();
            v29 = "CertCreateCertificateContext";
LABEL_26:
            v30 = WfpReportSysErrorAsWinError(v28, v29, LastError, 1);
            v11 = v33;
            v14 = v30;
            v9 = HIDWORD(dwBytes);
            goto LABEL_29;
          }
          ++v19;
        }
      }
      v9 = HIDWORD(dwBytes);
      v11 = v33;
      *v36 = v8;
      *v37 = v9;
      *v38 = v10;
      *v39 = v11;
    }
  }
LABEL_29:
  if ( v40 )
    ASN1_FreeDecoded(v41, v40, 0);
  if ( v41 )
    ASN1_CloseDecoder();
  if ( v14 )
  {
    IkeFreeCertCtxtArray(v8, v9);
    IkeFreeCrlCtxtArray(v10, v11);
  }
  return IkeReturnError(v14, "IkeDecodeCertBundle");
}

```

## disassembly

```asm
0x18005e610  push    rbp
0x18005e612  push    rbx
0x18005e613  push    rsi
0x18005e614  push    rdi
0x18005e615  push    r12
0x18005e617  push    r13
0x18005e619  push    r14
0x18005e61b  push    r15
0x18005e61d  lea     rbp, [rsp-0Fh]
0x18005e622  sub     rsp, 98h
0x18005e629  mov     rax, cs:__security_cookie
0x18005e630  xor     rax, rsp
0x18005e633  mov     [rbp+47h+var_50], rax
0x18005e637  mov     rax, [rbp+47h+arg_20]
0x18005e63b  mov     edi, edx
0x18005e63d  mov     [rbp+47h+var_70], rax
0x18005e641  lea     rdx, [rbp+47h+var_58]
0x18005e645  mov     rax, [rbp+47h+arg_28]
0x18005e649  mov     rbx, rcx
0x18005e64c  mov     rcx, cs:gIkeAsn1Module
0x18005e653  mov     [rbp+47h+var_68], rax
0x18005e657  xor     eax, eax
0x18005e659  mov     [rbp+47h+var_78], r9
0x18005e65d  mov     r15d, eax
0x18005e660  mov     [rbp+47h+var_80], r8
0x18005e664  xor     r9d, r9d
0x18005e667  xor     r8d, r8d
0x18005e66a  mov     [rbp+47h+var_90], rax
0x18005e66e  mov     r12d, eax
0x18005e671  mov     dword ptr [rbp+47h+dwBytes+4], eax
0x18005e674  mov     r14d, eax
0x18005e677  mov     [rbp+47h+var_88], rax
0x18005e67b  mov     r13d, eax
0x18005e67e  mov     [rbp+47h+var_98], eax
0x18005e681  mov     [rbp+47h+var_60], rax
0x18005e685  mov     [rbp+47h+var_58], rax
0x18005e689  mov     dword ptr [rbp+47h+dwBytes], eax
0x18005e68c  mov     [rsp+0D0h+var_B0], rax
0x18005e691  call    cs:__imp_ASN1_CreateDecoder
0x18005e697  test    eax, eax
0x18005e699  jns     short loc_18005E6B9
0x18005e69b  lea     r8d, [r14+0Eh]
0x18005e69f  mov     r9d, 1
0x18005e6a5  lea     rdx, aIkedecodecertb; "IkeDecodeCertBundle"
0x18005e6ac  call    WfpReportSysErrorAsWinError
0x18005e6b1  mov     rbx, rax
0x18005e6b4  jmp     loc_18005E87B
0x18005e6b9  mov     rcx, [rbp+47h+var_58]
0x18005e6bd  lea     rdx, [rbp+47h+var_60]
0x18005e6c1  mov     [rsp+0D0h+var_A8], edi
0x18005e6c5  mov     r9d, 8
0x18005e6cb  xor     r8d, r8d
0x18005e6ce  mov     [rsp+0D0h+var_B0], rbx
0x18005e6d3  call    cs:__imp_ASN1_Decode
0x18005e6d9  xor     r11d, r11d
0x18005e6dc  test    eax, eax
0x18005e6de  jns     short loc_18005E6E6
0x18005e6e0  lea     r8d, [r11+57h]
0x18005e6e4  jmp     short loc_18005E69F
0x18005e6e6  mov     rdx, [rbp+47h+var_60]
0x18005e6ea  mov     rbx, r11
0x18005e6ed  mov     edi, 1
0x18005e6f2  mov     r8d, [rdx]
0x18005e6f5  test    r8d, r8d
0x18005e6f8  jz      loc_18005E7BB
0x18005e6fe  mov     r10, [rdx+8]
0x18005e702  mov     r9d, r11d
0x18005e705  mov     eax, r9d
0x18005e708  lea     rcx, [rax+rax*2]
0x18005e70c  movzx   edx, word ptr [r10+rcx*8]
0x18005e711  lea     eax, [r13+1]
0x18005e715  test    dx, dx
0x18005e718  lea     ecx, [r12+1]
0x18005e71d  cmovnz  ecx, r12d
0x18005e721  cmovnz  r13d, eax
0x18005e725  add     r9d, edi
0x18005e728  mov     r12d, ecx
0x18005e72b  cmp     r9d, r8d
0x18005e72e  jb      short loc_18005E705
0x18005e730  mov     dword ptr [rbp+47h+dwBytes+4], ecx
0x18005e733  mov     [rbp+47h+var_98], r13d
0x18005e737  test    ecx, ecx
0x18005e739  jz      short loc_18005E777
0x18005e73b  lea     r8, [rbp+47h+dwBytes]
0x18005e73f  mov     edx, 8
0x18005e744  call    WfpUINT32Multiply
0x18005e749  mov     rbx, rax
0x18005e74c  test    rax, rax
0x18005e74f  jnz     loc_18005E87B
0x18005e755  mov     ecx, dword ptr [rbp+47h+dwBytes]; dwBytes
0x18005e758  lea     r8, [rbp+47h+var_90]
0x18005e75c  lea     edx, [rax+8]; dwFlags
0x18005e75f  call    WfpMemAlloc
0x18005e764  mov     r15, [rbp+47h+var_90]
0x18005e768  xor     r11d, r11d
0x18005e76b  mov     rbx, rax
0x18005e76e  test    rax, rax
0x18005e771  jnz     loc_18005E87B
0x18005e777  test    r13d, r13d
0x18005e77a  jz      short loc_18005E7BB
0x18005e77c  lea     r8, [rbp+47h+dwBytes]
0x18005e780  mov     edx, 8
0x18005e785  mov     ecx, r13d
0x18005e788  call    WfpUINT32Multiply
0x18005e78d  mov     rbx, rax
0x18005e790  test    rax, rax
0x18005e793  jnz     loc_18005E87B
0x18005e799  mov     ecx, dword ptr [rbp+47h+dwBytes]; dwBytes
0x18005e79c  lea     r8, [rbp+47h+var_88]
0x18005e7a0  lea     edx, [rax+8]; dwFlags
0x18005e7a3  call    WfpMemAlloc
0x18005e7a8  mov     r14, [rbp+47h+var_88]
0x18005e7ac  xor     r11d, r11d
0x18005e7af  mov     rbx, rax
0x18005e7b2  test    rax, rax
0x18005e7b5  jnz     loc_18005E87B
0x18005e7bb  mov     r12d, r11d
0x18005e7be  mov     r13d, r11d
0x18005e7c1  mov     esi, r11d
0x18005e7c4  mov     rdx, [rbp+47h+var_60]
0x18005e7c8  cmp     esi, [rdx]
0x18005e7ca  jnb     loc_18005E857
0x18005e7d0  mov     eax, esi
0x18005e7d2  lea     rcx, [rax+rax*2]
0x18005e7d6  mov     rax, [rdx+8]
0x18005e7da  mov     r8d, [rax+rcx*8+8]; cbCrlEncoded
0x18005e7df  mov     rdx, [rax+rcx*8+10h]; pbCrlEncoded
0x18005e7e4  cmp     [rax+rcx*8], r11w
0x18005e7e9  mov     ecx, edi; dwCertEncodingType
0x18005e7eb  jnz     short loc_18005E807
0x18005e7ed  call    cs:__imp_CertCreateCertificateContext
0x18005e7f3  mov     ecx, r12d
0x18005e7f6  xor     r11d, r11d
0x18005e7f9  mov     [r15+rcx*8], rax
0x18005e7fd  test    rax, rax
0x18005e800  jz      short loc_18005E823
0x18005e802  add     r12d, edi
0x18005e805  jmp     short loc_18005E81F
0x18005e807  call    cs:__imp_CertCreateCRLContext
0x18005e80d  mov     ecx, r13d
0x18005e810  xor     r11d, r11d
0x18005e813  mov     [r14+rcx*8], rax
0x18005e817  test    rax, rax
0x18005e81a  jz      short loc_18005E848
0x18005e81c  add     r13d, edi
0x18005e81f  add     esi, edi
0x18005e821  jmp     short loc_18005E7C4
0x18005e823  call    cs:__imp_GetLastError
0x18005e829  lea     rdx, aCertcreatecert_0; "CertCreateCertificateContext"
0x18005e830  mov     r9d, edi
0x18005e833  mov     r8d, eax
0x18005e836  call    WfpReportSysErrorAsWinError
0x18005e83b  mov     r13d, [rbp+47h+var_98]
0x18005e83f  mov     rbx, rax
0x18005e842  mov     r12d, dword ptr [rbp+47h+dwBytes+4]
0x18005e846  jmp     short loc_18005E87B
0x18005e848  call    cs:__imp_GetLastError
0x18005e84e  lea     rdx, aCertcreatecrlc_0; "CertCreateCRLContext"
0x18005e855  jmp     short loc_18005E830
0x18005e857  mov     rax, [rbp+47h+var_80]
0x18005e85b  mov     r12d, dword ptr [rbp+47h+dwBytes+4]
0x18005e85f  mov     r13d, [rbp+47h+var_98]
0x18005e863  mov     [rax], r15
0x18005e866  mov     rax, [rbp+47h+var_78]
0x18005e86a  mov     [rax], r12d
0x18005e86d  mov     rax, [rbp+47h+var_70]
0x18005e871  mov     [rax], r14
0x18005e874  mov     rax, [rbp+47h+var_68]
0x18005e878  mov     [rax], r13d
0x18005e87b  mov     rdx, [rbp+47h+var_60]
0x18005e87f  test    rdx, rdx
0x18005e882  jz      short loc_18005E891
0x18005e884  mov     rcx, [rbp+47h+var_58]
0x18005e888  xor     r8d, r8d
0x18005e88b  call    cs:__imp_ASN1_FreeDecoded
0x18005e891  mov     rcx, [rbp+47h+var_58]
0x18005e895  test    rcx, rcx
0x18005e898  jz      short loc_18005E8A0
0x18005e89a  call    cs:__imp_ASN1_CloseDecoder
0x18005e8a0  test    rbx, rbx
0x18005e8a3  jz      short loc_18005E8BB
0x18005e8a5  mov     edx, r12d
0x18005e8a8  mov     rcx, r15
0x18005e8ab  call    IkeFreeCertCtxtArray
0x18005e8b0  mov     edx, r13d
0x18005e8b3  mov     rcx, r14
0x18005e8b6  call    IkeFreeCrlCtxtArray
0x18005e8bb  lea     rdx, aIkedecodecertb; "IkeDecodeCertBundle"
0x18005e8c2  mov     rcx, rbx
0x18005e8c5  call    IkeReturnError
0x18005e8ca  mov     rcx, [rbp+47h+var_50]
0x18005e8ce  xor     rcx, rsp; StackCookie
0x18005e8d1  call    __security_check_cookie
0x18005e8d6  add     rsp, 98h
0x18005e8dd  pop     r15
0x18005e8df  pop     r14
0x18005e8e1  pop     r13
0x18005e8e3  pop     r12
0x18005e8e5  pop     rdi
0x18005e8e6  pop     rsi
0x18005e8e7  pop     rbx
0x18005e8e8  pop     rbp
0x18005e8e9  retn
```
