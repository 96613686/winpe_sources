# CreateAndAddToBeRunAddHpkpJob

- ea: `0x180010d3c`
- end: `0x180010f5b`
- name: `CreateAndAddToBeRunAddHpkpJob`
- size: `543`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000fcd8`

## callees

- `0x1800033a0`
- `0x1800068f0`
- `0x180010748`
- `0x180010ba4`
- `0x180010d3c`
- `0x180010f64`
- `0x180016854`
- `0x180016cb4`
- `0x180016cf4`
- `0x1800174fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010f1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010f1e`
- `CRYPT32!CertFreeCertificateContext` at `0x180010f3e`
- `CRYPT32!CertFreeCertificateContext` at `0x180010f3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010ee9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010ee9`

## pseudocode

```c
__int64 __fastcall CreateAndAddToBeRunAddHpkpJob(_DWORD *a1, unsigned int a2)
{
  __int64 v2; // r9
  __int64 v3; // rbp
  _DWORD *v4; // rbx
  const CERT_CONTEXT *v5; // rdi
  __int64 v6; // r12
  size_t v7; // r13
  __int64 v8; // rdx
  char *v9; // r8
  BYTE *v10; // r15
  DWORD v11; // ecx
  __int64 v12; // rsi
  unsigned int i; // r14d
  unsigned int v14; // eax
  const CERT_CONTEXT *v15; // rax
  __int64 v16; // rax
  unsigned int v17; // esi
  BYTE *pbCertEncoded; // [rsp+70h] [rbp+18h]
  void *Src; // [rsp+78h] [rbp+20h]

  v2 = a2;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  if ( a2 - 16 > 0x9920 )
    goto LABEL_31;
  if ( (unsigned int)(*a1 - 1) > 9 )
    goto LABEL_31;
  v6 = (unsigned int)a1[1];
  if ( (unsigned int)v6 > 0x7530 )
    goto LABEL_31;
  v7 = (unsigned int)a1[2];
  if ( (unsigned int)(v7 - 2) > 0x3FE )
    goto LABEL_31;
  v8 = (unsigned int)a1[3];
  if ( (unsigned int)(v8 - 2) > 0x1FFE )
    goto LABEL_31;
  if ( v8 + v7 + v6 + 16 != v2 )
    goto LABEL_31;
  v9 = (char *)a1 + v6 + 16;
  pbCertEncoded = (BYTE *)(a1 + 4);
  Src = v9;
  if ( v9[(unsigned int)(v7 - 1)] )
    goto LABEL_31;
  v10 = (BYTE *)&v9[v7];
  if ( v9[v7 + (unsigned int)(v8 - 1)] )
    goto LABEL_31;
  if ( g_HpkpPara )
  {
    v11 = 1058;
LABEL_32:
    SetLastError(v11);
    goto LABEL_33;
  }
  if ( v10 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v10[v12] );
  }
  else
  {
    LODWORD(v12) = 0;
  }
  v4 = (_DWORD *)PkiZeroAlloc(0x28u);
  if ( !v4 )
    goto LABEL_17;
  for ( i = 0; i < (unsigned int)v12; i += ParseHpkpDirective(&v10[i], (unsigned int)v12 - i, v4) )
    ;
  if ( (*v4 & 0xFFFFFFEF) != 0 )
  {
LABEL_17:
    v11 = 13;
    goto LABEL_32;
  }
  v14 = v4[2];
  if ( v14 < dword_180020340 )
  {
    v11 = 1901;
    goto LABEL_32;
  }
  if ( v14 > dword_180020344 )
    v4[2] = dword_180020344;
  v15 = (const CERT_CONTEXT *)ParseInCerts(pbCertEncoded, v6);
  v5 = v15;
  if ( !v15 )
  {
LABEL_31:
    v11 = -2147024809;
    goto LABEL_32;
  }
  if ( (unsigned int)ValidateInCerts(v15, (LPCCH)Src) )
  {
    v16 = PkiZeroAlloc((unsigned int)(v7 + 72));
    v3 = v16;
    if ( v16 )
    {
      *(_QWORD *)(v16 + 32) = v16 + 72;
      memcpy_0((void *)(v16 + 72), Src, v7);
      *(_QWORD *)(v3 + 40) = v4;
      v4 = 0;
      GetSystemTimeAsFileTime((LPFILETIME)(v3 + 64));
      if ( (unsigned int)CertGetHpkpHeaderThumbprint(v10) )
      {
        v17 = 1;
        if ( (unsigned int)AddToBeRunJobEx(v3, 7, 0) )
          goto LABEL_34;
      }
    }
  }
LABEL_33:
  CertFreeHpkpHeaderValue(v4);
  FreeAddHpkpJob((HLOCAL)v3);
  v17 = 0;
  if ( v5 )
LABEL_34:
    CertFreeCertificateContext(v5);
  return v17;
}

```

## disassembly

```asm
0x180010d3c  mov     [rsp+arg_0], rbx
0x180010d41  push    rbp
0x180010d42  push    rsi
0x180010d43  push    rdi
0x180010d44  push    r12
0x180010d46  push    r13
0x180010d48  push    r14
0x180010d4a  push    r15
0x180010d4c  sub     rsp, 20h
0x180010d50  mov     r9d, edx
0x180010d53  xor     ebp, ebp
0x180010d55  xor     ebx, ebx
0x180010d57  xor     edi, edi
0x180010d59  mov     r8, rcx
0x180010d5c  lea     eax, [r9-10h]
0x180010d60  cmp     eax, 9920h
0x180010d65  ja      loc_180010F19
0x180010d6b  mov     eax, [rcx]
0x180010d6d  mov     [rsp+58h+arg_8], eax
0x180010d71  dec     eax
0x180010d73  cmp     eax, 9
0x180010d76  ja      loc_180010F19
0x180010d7c  mov     r12d, [rcx+4]
0x180010d80  cmp     r12d, 7530h
0x180010d87  ja      loc_180010F19
0x180010d8d  mov     r13d, [rcx+8]
0x180010d91  lea     eax, [r13-2]
0x180010d95  cmp     eax, 3FEh
0x180010d9a  ja      loc_180010F19
0x180010da0  mov     edx, [rcx+0Ch]
0x180010da3  lea     eax, [rdx-2]
0x180010da6  cmp     eax, 1FFEh
0x180010dab  ja      loc_180010F19
0x180010db1  lea     rax, [rdx+r13]
0x180010db5  lea     rcx, [r12+10h]
0x180010dba  add     rcx, rax
0x180010dbd  cmp     rcx, r9
0x180010dc0  jnz     loc_180010F19
0x180010dc6  lea     rax, [r8+10h]
0x180010dca  lea     r8, [rax+r12]
0x180010dce  mov     [rsp+58h+pbCertEncoded], rax
0x180010dd3  lea     eax, [r13-1]
0x180010dd7  mov     [rsp+58h+Src], r8
0x180010ddc  cmp     [rax+r8], bl
0x180010de0  jnz     loc_180010F19
0x180010de6  lea     r15, [r8+r13]
0x180010dea  lea     eax, [rdx-1]
0x180010ded  cmp     [rax+r15], bl
0x180010df1  jnz     loc_180010F19
0x180010df7  cmp     cs:g_HpkpPara, ebx
0x180010dfd  jz      short loc_180010E09
0x180010dff  mov     ecx, 422h
0x180010e04  jmp     loc_180010F1E
0x180010e09  test    r15, r15
0x180010e0c  jz      short loc_180010E1D
0x180010e0e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180010e12  inc     rsi
0x180010e15  cmp     [r15+rsi], bl
0x180010e19  jnz     short loc_180010E12
0x180010e1b  jmp     short loc_180010E1F
0x180010e1d  xor     esi, esi
0x180010e1f  mov     ecx, 28h ; '('; uBytes
0x180010e24  call    PkiZeroAlloc
0x180010e29  mov     rbx, rax
0x180010e2c  test    rax, rax
0x180010e2f  jnz     short loc_180010E3B
0x180010e31  mov     ecx, 0Dh
0x180010e36  jmp     loc_180010F1E
0x180010e3b  xor     r14d, r14d
0x180010e3e  test    esi, esi
0x180010e40  jz      short loc_180010E5D
0x180010e42  mov     edx, esi
0x180010e44  mov     ecx, r14d
0x180010e47  sub     edx, r14d
0x180010e4a  add     rcx, r15
0x180010e4d  mov     r8, rbx
0x180010e50  call    _ParseHpkpDirective
0x180010e55  add     r14d, eax
0x180010e58  cmp     r14d, esi
0x180010e5b  jb      short loc_180010E42
0x180010e5d  test    dword ptr [rbx], 0FFFFFFEFh
0x180010e63  jnz     short loc_180010E31
0x180010e65  mov     eax, [rbx+8]
0x180010e68  cmp     eax, cs:dword_180020340
0x180010e6e  jnb     short loc_180010E7A
0x180010e70  mov     ecx, 76Dh
0x180010e75  jmp     loc_180010F1E
0x180010e7a  mov     r8d, cs:dword_180020344
0x180010e81  cmp     eax, r8d
0x180010e84  jbe     short loc_180010E8A
0x180010e86  mov     [rbx+8], r8d
0x180010e8a  mov     r8d, [rsp+58h+arg_8]
0x180010e8f  mov     edx, r12d; cbCertEncoded
0x180010e92  mov     rcx, [rsp+58h+pbCertEncoded]; pbCertEncoded
0x180010e97  call    _ParseInCerts
0x180010e9c  mov     rdi, rax
0x180010e9f  test    rax, rax
0x180010ea2  jz      short loc_180010F19
0x180010ea4  mov     rsi, [rsp+58h+Src]
0x180010ea9  mov     r8, rbx
0x180010eac  mov     rdx, rsi; lpMultiByteStr
0x180010eaf  mov     rcx, rax; pCertContext
0x180010eb2  call    _ValidateInCerts
0x180010eb7  test    eax, eax
0x180010eb9  jz      short loc_180010F24
0x180010ebb  lea     ecx, [r13+48h]; uBytes
0x180010ebf  call    PkiZeroAlloc
0x180010ec4  mov     rbp, rax
0x180010ec7  test    rax, rax
0x180010eca  jz      short loc_180010F24
0x180010ecc  lea     rcx, [rax+48h]; void *
0x180010ed0  mov     r8, r13; Size
0x180010ed3  mov     rdx, rsi; Src
0x180010ed6  mov     [rax+20h], rcx
0x180010eda  call    memcpy_0
0x180010edf  mov     [rbp+28h], rbx
0x180010ee3  lea     rcx, [rbp+40h]; lpSystemTimeAsFileTime
0x180010ee7  xor     ebx, ebx
0x180010ee9  call    cs:__imp_GetSystemTimeAsFileTime
0x180010eef  lea     rdx, [rbp+30h]
0x180010ef3  mov     rcx, r15; pbEncoded
0x180010ef6  call    CertGetHpkpHeaderThumbprint
0x180010efb  test    eax, eax
0x180010efd  jz      short loc_180010F24
0x180010eff  lea     esi, [rbx+1]
0x180010f02  xor     r8d, r8d
0x180010f05  mov     r9d, esi
0x180010f08  lea     edx, [rbx+7]
0x180010f0b  mov     rcx, rbp
0x180010f0e  call    AddToBeRunJobEx
0x180010f13  test    eax, eax
0x180010f15  jz      short loc_180010F24
0x180010f17  jmp     short loc_180010F3B
0x180010f19  mov     ecx, 80070057h; dwErrCode
0x180010f1e  call    cs:__imp_SetLastError
0x180010f24  mov     rcx, rbx; hMem
0x180010f27  call    CertFreeHpkpHeaderValue
0x180010f2c  mov     rcx, rbp; hMem
0x180010f2f  call    FreeAddHpkpJob
0x180010f34  xor     esi, esi
0x180010f36  test    rdi, rdi
0x180010f39  jz      short loc_180010F44
0x180010f3b  mov     rcx, rdi; pCertContext
0x180010f3e  call    cs:__imp_CertFreeCertificateContext
0x180010f44  mov     rbx, [rsp+58h+arg_0]
0x180010f49  mov     eax, esi
0x180010f4b  add     rsp, 20h
0x180010f4f  pop     r15
0x180010f51  pop     r14
0x180010f53  pop     r13
0x180010f55  pop     r12
0x180010f57  pop     rdi
0x180010f58  pop     rsi
0x180010f59  pop     rbp
0x180010f5a  retn
```
