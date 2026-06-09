# cpExtensionMatch(_CERT_CONTEXT const *,ushort const *,_CERTFILTERDATA *,int *,int *)

- ea: `0x18001fb04`
- end: `0x18001fced`
- name: `?cpExtensionMatch@@YAJPEBU_CERT_CONTEXT@@PEBGPEAU_CERTFILTERDATA@@PEAH3@Z`
- size: `489`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, const unsigned __int16 *, struct _CERTFILTERDATA *, int *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001f61c`

## callees

- `0x180008400`
- `0x180008610`
- `0x18001f3f8`
- `0x18001fb04`
- `0x18002024c`
- `0x18002056c`

## import_xrefs

- `CRYPT32!CryptFindOIDInfo` at `0x18001fbe2`
- `CRYPT32!CryptFindOIDInfo` at `0x18001fbe2`

## pseudocode

```c
__int64 __fastcall cpExtensionMatch(
        PCCERT_CONTEXT pCertContext,
        const unsigned __int16 *a2,
        struct _CERTFILTERDATA *a3,
        int *a4,
        int *a5)
{
  unsigned int v5; // edi
  PCERT_INFO pCertInfo; // r8
  char *v10; // r10
  DWORD cExtension; // r14d
  CERT_EXTENSION *rgExtension; // r12
  int v13; // ebx
  char *v14; // rax
  signed __int64 v15; // r8
  int v16; // edx
  int v17; // ecx
  DWORD i; // ecx
  char *v19; // rdx
  int v20; // eax
  int v21; // r8d
  int matched; // eax
  unsigned int v23; // ecx
  int v25; // [rsp+80h] [rbp+40h] BYREF
  char *v26; // [rsp+90h] [rbp+50h] BYREF
  int *v27; // [rsp+98h] [rbp+58h]

  v27 = a4;
  v5 = 0;
  pCertInfo = pCertContext->pCertInfo;
  v25 = 0;
  *a4 = 0;
  v10 = (char *)*((_QWORD *)a3 + 8);
  cExtension = pCertInfo->cExtension;
  rgExtension = pCertInfo->rgExtension;
  v26 = v10;
  if ( v10 )
  {
    v13 = 1;
    if ( !strcmp(v10, pCertInfo->SignatureAlgorithm.pszObjId) )
      goto LABEL_26;
    v14 = v10;
    v15 = pCertInfo->SubjectPublicKeyInfo.Algorithm.pszObjId - v10;
    do
    {
      v16 = (unsigned __int8)v14[v15];
      v17 = (unsigned __int8)*v14 - v16;
      if ( v17 )
        break;
      ++v14;
    }
    while ( v16 );
    if ( !v17 )
      goto LABEL_26;
    for ( i = 0; ; ++i )
    {
      v19 = v10;
      if ( i >= cExtension )
        break;
      do
      {
        v20 = (unsigned __int8)v19[(unsigned __int64)(rgExtension[i].pszObjId - v10)];
        v21 = (unsigned __int8)*v19 - v20;
        if ( v21 )
          break;
        ++v19;
      }
      while ( v20 );
      if ( !v21 )
        goto LABEL_26;
    }
    if ( CryptFindOIDInfo(1u, v10, 7u) )
    {
      matched = cpCertMatchEKUOrApplicationPolicies(pCertContext, 1u, (const char *const *)&v26, 0, 0, 1, 1, &v25);
      v5 = matched;
      if ( matched )
      {
        v23 = 90636699;
LABEL_16:
        CSPrintErrorLineFile(v23, matched);
        v13 = v25;
        goto LABEL_26;
      }
      v13 = v25;
      if ( v25 )
        goto LABEL_26;
    }
    CSPrintErrorLineFileData2(a2, 0x56E019Bu, -2146885628, -2146885628);
  }
  matched = cpTemplateMatch(cExtension, rgExtension, a3, &v25);
  v5 = matched;
  if ( matched )
  {
    v23 = 91292059;
    goto LABEL_16;
  }
  v13 = v25;
  if ( v25 )
    goto LABEL_26;
  CSPrintErrorLineFileData2(a2, 0x577019Bu, -2146885628, -2146885628);
  matched = cpSubjectAltNameMatch(pCertContext, a3, v27, &v25);
  v5 = matched;
  if ( matched )
  {
    v23 = 91881883;
    goto LABEL_16;
  }
  v13 = v25;
  if ( !v25 )
    CSPrintErrorLineFileData2(a2, 0x580019Bu, -2146885628, -2146885628);
LABEL_26:
  *a5 = v13;
  return v5;
}

```

## disassembly

```asm
0x18001fb04  mov     [rsp-38h+arg_8], rbx
0x18001fb09  mov     [rsp-38h+arg_18], r9
0x18001fb0e  push    rbp
0x18001fb0f  push    rsi
0x18001fb10  push    rdi
0x18001fb11  push    r12
0x18001fb13  push    r13
0x18001fb15  push    r14
0x18001fb17  push    r15
0x18001fb19  mov     rbp, rsp
0x18001fb1c  sub     rsp, 40h
0x18001fb20  xor     edi, edi
0x18001fb22  mov     r15, r8
0x18001fb25  mov     r8, [rcx+18h]
0x18001fb29  mov     rsi, rdx
0x18001fb2c  mov     r13, rcx
0x18001fb2f  mov     [rbp+arg_0], edi
0x18001fb32  mov     [r9], edi
0x18001fb35  mov     r10, [r15+40h]
0x18001fb39  mov     r14d, [r8+0C0h]
0x18001fb40  mov     r12, [r8+0C8h]
0x18001fb47  mov     [rbp+arg_10], r10
0x18001fb4b  test    r10, r10
0x18001fb4e  jz      loc_18001FC51
0x18001fb54  mov     r9, [r8+18h]
0x18001fb58  lea     ebx, [rdi+1]
0x18001fb5b  sub     r9, r10
0x18001fb5e  mov     rax, r10
0x18001fb61  movzx   edx, byte ptr [rax]
0x18001fb64  movzx   ecx, byte ptr [rax+r9]
0x18001fb69  sub     edx, ecx
0x18001fb6b  jnz     short loc_18001FB74
0x18001fb6d  add     rax, rbx
0x18001fb70  test    ecx, ecx
0x18001fb72  jnz     short loc_18001FB61
0x18001fb74  test    edx, edx
0x18001fb76  jz      loc_18001FCCD
0x18001fb7c  mov     r8, [r8+60h]
0x18001fb80  mov     rax, r10
0x18001fb83  sub     r8, r10
0x18001fb86  movzx   ecx, byte ptr [rax]
0x18001fb89  movzx   edx, byte ptr [rax+r8]
0x18001fb8e  sub     ecx, edx
0x18001fb90  jnz     short loc_18001FB99
0x18001fb92  add     rax, rbx
0x18001fb95  test    edx, edx
0x18001fb97  jnz     short loc_18001FB86
0x18001fb99  test    ecx, ecx
0x18001fb9b  jz      loc_18001FCCD
0x18001fba1  mov     ecx, edi
0x18001fba3  mov     rdx, r10; pvKey
0x18001fba6  cmp     ecx, r14d
0x18001fba9  jnb     short loc_18001FBDA
0x18001fbab  mov     eax, ecx
0x18001fbad  shl     rax, 5
0x18001fbb1  mov     r9, [rax+r12]
0x18001fbb5  sub     r9, r10
0x18001fbb8  movzx   r8d, byte ptr [rdx]
0x18001fbbc  movzx   eax, byte ptr [rdx+r9]
0x18001fbc1  sub     r8d, eax
0x18001fbc4  jnz     short loc_18001FBCD
0x18001fbc6  add     rdx, rbx
0x18001fbc9  test    eax, eax
0x18001fbcb  jnz     short loc_18001FBB8
0x18001fbcd  test    r8d, r8d
0x18001fbd0  jz      loc_18001FCCD
0x18001fbd6  add     ecx, ebx
0x18001fbd8  jmp     short loc_18001FBA3
0x18001fbda  mov     r8d, 7; dwGroupId
0x18001fbe0  mov     ecx, ebx; dwKeyType
0x18001fbe2  call    cs:__imp_CryptFindOIDInfo
0x18001fbe8  test    rax, rax
0x18001fbeb  jz      short loc_18001FC39
0x18001fbed  lea     rax, [rbp+arg_0]
0x18001fbf1  xor     r9d, r9d; unsigned int
0x18001fbf4  mov     [rsp+40h+var_8], rax; int *
0x18001fbf9  lea     r8, [rbp+arg_10]; char **
0x18001fbfd  mov     [rsp+40h+var_10], ebx; int
0x18001fc01  mov     edx, ebx; unsigned int
0x18001fc03  mov     [rsp+40h+var_18], ebx; int
0x18001fc07  mov     rcx, r13; pCertContext
0x18001fc0a  mov     [rsp+40h+var_20], rdi; struct CERTFILTERSTRING *
0x18001fc0f  call    ?cpCertMatchEKUOrApplicationPolicies@@YAJPEBU_CERT_CONTEXT@@KPEBQEBDKPEAVCERTFILTERSTRING@@HHPEAH@Z; cpCertMatchEKUOrApplicationPolicies(_CERT_CONTEXT const *,ulong,char const * const *,ulong,CERTFILTERSTRING *,int,int,int *)
0x18001fc14  mov     edi, eax
0x18001fc16  test    eax, eax
0x18001fc18  jz      short loc_18001FC2E
0x18001fc1a  mov     ecx, 567019Bh; unsigned int
0x18001fc1f  mov     edx, eax; int
0x18001fc21  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001fc26  mov     ebx, [rbp+arg_0]
0x18001fc29  jmp     loc_18001FCCD
0x18001fc2e  mov     ebx, [rbp+arg_0]
0x18001fc31  test    ebx, ebx
0x18001fc33  jnz     loc_18001FCCD
0x18001fc39  mov     eax, 80092004h
0x18001fc3e  mov     edx, 56E019Bh; unsigned int
0x18001fc43  mov     r9d, eax; int
0x18001fc46  mov     r8d, eax; int
0x18001fc49  mov     rcx, rsi; unsigned __int16 *
0x18001fc4c  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18001fc51  lea     r9, [rbp+arg_0]; int *
0x18001fc55  mov     r8, r15; struct _CERTFILTERDATA *
0x18001fc58  mov     rdx, r12; rgExtensions
0x18001fc5b  mov     ecx, r14d; cExtensions
0x18001fc5e  call    ?cpTemplateMatch@@YAJKPEBU_CERT_EXTENSION@@PEAU_CERTFILTERDATA@@PEAH@Z; cpTemplateMatch(ulong,_CERT_EXTENSION const *,_CERTFILTERDATA *,int *)
0x18001fc63  mov     edi, eax
0x18001fc65  test    eax, eax
0x18001fc67  jz      short loc_18001FC70
0x18001fc69  mov     ecx, 571019Bh
0x18001fc6e  jmp     short loc_18001FC1F
0x18001fc70  mov     ebx, [rbp+arg_0]
0x18001fc73  test    ebx, ebx
0x18001fc75  jnz     short loc_18001FCCD
0x18001fc77  mov     r14d, 80092004h
0x18001fc7d  mov     edx, 577019Bh; unsigned int
0x18001fc82  mov     r9d, r14d; int
0x18001fc85  mov     r8d, r14d; int
0x18001fc88  mov     rcx, rsi; unsigned __int16 *
0x18001fc8b  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18001fc90  mov     r8, [rbp+arg_18]; int *
0x18001fc94  lea     r9, [rbp+arg_0]; int *
0x18001fc98  mov     rdx, r15; struct _CERTFILTERDATA *
0x18001fc9b  mov     rcx, r13; struct _CERT_CONTEXT *
0x18001fc9e  call    ?cpSubjectAltNameMatch@@YAJPEBU_CERT_CONTEXT@@PEAU_CERTFILTERDATA@@PEAH2@Z; cpSubjectAltNameMatch(_CERT_CONTEXT const *,_CERTFILTERDATA *,int *,int *)
0x18001fca3  mov     edi, eax
0x18001fca5  test    eax, eax
0x18001fca7  jz      short loc_18001FCB3
0x18001fca9  mov     ecx, 57A019Bh
0x18001fcae  jmp     loc_18001FC1F
0x18001fcb3  mov     ebx, [rbp+arg_0]
0x18001fcb6  test    ebx, ebx
0x18001fcb8  jnz     short loc_18001FCCD
0x18001fcba  mov     r9d, r14d; int
0x18001fcbd  mov     r8d, r14d; int
0x18001fcc0  mov     edx, 580019Bh; unsigned int
0x18001fcc5  mov     rcx, rsi; unsigned __int16 *
0x18001fcc8  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18001fccd  mov     rax, [rbp+arg_20]
0x18001fcd1  mov     [rax], ebx
0x18001fcd3  mov     eax, edi
0x18001fcd5  mov     rbx, [rsp+40h+arg_8]
0x18001fcdd  add     rsp, 40h
0x18001fce1  pop     r15
0x18001fce3  pop     r14
0x18001fce5  pop     r13
0x18001fce7  pop     r12
0x18001fce9  pop     rdi
0x18001fcea  pop     rsi
0x18001fceb  pop     rbp
0x18001fcec  retn
```
