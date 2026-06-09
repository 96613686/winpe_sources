# SpInitializeSecurityContextW

- ea: `0x180002560`
- end: `0x180002e5b`
- name: `SpInitializeSecurityContextW`
- size: `2299`
- prototype: `int __fastcall(__int64, __int64, SEC_WCHAR *, unsigned int, int, unsigned int TargetDataRep, PSecBufferDesc pInput, int, __int64, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002560`
- `0x1800032a0`
- `0x18000351c`
- `0x1800035b4`
- `0x1800039e4`
- `0x180003dd9`
- `0x180003e20`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000289a`
- `msvcrt!wcsncpy_s` at `0x18000289a`
- `SspiCli!InitializeSecurityContextW` at `0x180002667`
- `SspiCli!InitializeSecurityContextW` at `0x1800027fa`
- `SspiCli!InitializeSecurityContextW` at `0x18000295f`
- `SspiCli!InitializeSecurityContextW` at `0x180002b66`
- `SspiCli!InitializeSecurityContextW` at `0x180002bd5`
- `SspiCli!InitializeSecurityContextW` at `0x180002d0b`
- `SspiCli!InitializeSecurityContextW` at `0x180002667`
- `SspiCli!InitializeSecurityContextW` at `0x1800027fa`
- `SspiCli!InitializeSecurityContextW` at `0x18000295f`
- `SspiCli!InitializeSecurityContextW` at `0x180002b66`
- `SspiCli!InitializeSecurityContextW` at `0x180002bd5`
- `SspiCli!InitializeSecurityContextW` at `0x180002d0b`
- `SspiCli!QueryContextAttributesW` at `0x18000298b`
- `SspiCli!QueryContextAttributesW` at `0x1800029a5`
- `SspiCli!QueryContextAttributesW` at `0x18000298b`
- `SspiCli!QueryContextAttributesW` at `0x1800029a5`
- `SspiCli!DeleteSecurityContext` at `0x180002707`
- `SspiCli!DeleteSecurityContext` at `0x1800028e3`
- `SspiCli!DeleteSecurityContext` at `0x180002707`
- `SspiCli!DeleteSecurityContext` at `0x1800028e3`
- `SspiCli!FreeContextBuffer` at `0x1800026dc`
- `SspiCli!FreeContextBuffer` at `0x1800028c2`
- `SspiCli!FreeContextBuffer` at `0x180002a6f`
- `SspiCli!FreeContextBuffer` at `0x180002af9`
- `SspiCli!FreeContextBuffer` at `0x1800026dc`
- `SspiCli!FreeContextBuffer` at `0x1800028c2`
- `SspiCli!FreeContextBuffer` at `0x180002a6f`
- `SspiCli!FreeContextBuffer` at `0x180002af9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000269c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000275f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002815`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002875`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002a42`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002c14`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000269c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000275f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002815`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002875`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002a42`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002c14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002724`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800028cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800028f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002dc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002724`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800028cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800028f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002dc2`
- `CRYPT32!CertFreeCertificateContext` at `0x1800029de`
- `CRYPT32!CertFreeCertificateContext` at `0x1800029de`

## pseudocode

```c
int __fastcall SpInitializeSecurityContextW(
        __int64 a1,
        __int64 a2,
        SEC_WCHAR *a3,
        unsigned int a4,
        int a5,
        unsigned int TargetDataRep,
        PSecBufferDesc pInput,
        int a8,
        __int64 a9,
        PSecBufferDesc pOutput,
        unsigned int *pfContextAttr,
        PTimeStamp ptsExpiry)
{
  HLOCAL v12; // rbx
  SECURITY_INTEGER *v15; // rcx
  PSecBuffer pBuffers; // rax
  int result; // eax
  struct _SecHandle *v18; // r10
  unsigned int v19; // edi
  struct _SecHandle *v20; // rdi
  unsigned int *v21; // r14
  __int64 v22; // rdx
  __int64 v23; // rcx
  struct _SecBufferDesc *v24; // r12
  SECURITY_STATUS inited; // ebx
  unsigned int v26; // r15d
  void *pvBuffer; // rcx
  unsigned int v28; // eax
  struct _SecHandle *v29; // rax
  struct _SecHandle v30; // xmm1
  __int64 v31; // rax
  wchar_t *v32; // rax
  void *v33; // rcx
  __int64 v34; // rbx
  struct _SecBuffer v35; // xmm6
  unsigned int v36; // edx
  PSecBuffer v37; // rax
  const void **v38; // rdx
  char *v39; // rax
  char *v40; // rdi
  char *v41; // rcx
  size_t v42; // r8
  PSecBuffer v43; // r9
  PSecBuffer v44; // rax
  void *v45; // rcx
  SECURITY_STATUS v46; // eax
  SECURITY_STATUS v47; // edi
  SIZE_T v48; // rdx
  struct _SecBuffer *v49; // rdi
  struct _SecBuffer *v50; // rax
  unsigned int v51; // ecx
  void *v52; // rcx
  PSecBuffer v53; // rcx
  struct _SecBuffer *v54; // rdx
  HLOCAL v55; // [rsp+68h] [rbp-81h]
  struct _SecHandle *SizeInWords; // [rsp+70h] [rbp-79h]
  rsize_t SizeInWordsa; // [rsp+70h] [rbp-79h]
  unsigned int pszTargetNamea; // [rsp+80h] [rbp-69h]
  unsigned int pszTargetNameb; // [rsp+80h] [rbp-69h]
  unsigned int v62; // [rsp+88h] [rbp-61h] BYREF
  unsigned int *v63; // [rsp+90h] [rbp-59h]
  PCCERT_CONTEXT pBuffer; // [rsp+98h] [rbp-51h] BYREF
  struct _SecBuffer *v65; // [rsp+A0h] [rbp-49h]
  SECURITY_INTEGER v66; // [rsp+A8h] [rbp-41h] BYREF
  struct _SecHandle phNewContext; // [rsp+B0h] [rbp-39h] BYREF
  struct _SecHandle phContext; // [rsp+C0h] [rbp-29h] BYREF

  v12 = 0;
  v15 = ptsExpiry;
  v63 = pfContextAttr;
  v62 = 0;
  v66.QuadPart = 0;
  pBuffer = 0;
  phContext = 0;
  if ( !a1 )
    return -2146893055;
  if ( !pOutput )
    return -2146893048;
  pBuffers = pOutput->pBuffers;
  if ( !pBuffers )
    return -2146893048;
  if ( !pfContextAttr )
    return -2146892963;
  v18 = *(struct _SecHandle **)(a1 + 8);
  SizeInWords = v18;
  v19 = a4 & 0xFFF7FFFC | 0x80000;
  if ( !a2 )
  {
    if ( a9 )
    {
      phNewContext.dwUpper = -1;
      phNewContext.dwLower = -1;
      result = InitializeSecurityContextW(
                 v18,
                 0,
                 a3,
                 v19,
                 0,
                 TargetDataRep,
                 0,
                 0,
                 &phContext,
                 pOutput,
                 pfContextAttr,
                 ptsExpiry);
      if ( result < 0 )
        return result;
      if ( result != 590610 )
        return -2146893052;
      v55 = 0;
      v20 = 0;
      v21 = v63;
      v24 = (struct _SecBufferDesc *)LocalAlloc(0x40u, 0x20u);
      if ( !v24 )
        goto LABEL_12;
      if ( (*v63 & 0x100) == 0 )
      {
        v28 = uBytes;
        if ( !(_DWORD)uBytes )
        {
          inited = InitMaxToken(v23, v22, 0);
          if ( inited < 0 )
            goto LABEL_13;
          v28 = uBytes;
        }
        v55 = LocalAlloc(0x40u, v28);
        v12 = v55;
        if ( !v55 )
          goto LABEL_12;
      }
      v24->ulVersion = pOutput->ulVersion;
      v24->pBuffers = (PSecBuffer)&v24[1];
      v24->cBuffers = 1;
      v24[1].ulVersion = v12 != 0 ? uBytes : 0;
      v24[1].cBuffers = 2;
      v24->pBuffers->pvBuffer = v12;
      inited = InitializeSecurityContextW(
                 SizeInWords + 1,
                 0,
                 a3,
                 a4,
                 0,
                 TargetDataRep,
                 0,
                 0,
                 &phNewContext,
                 v24,
                 &v62,
                 &v66);
      if ( inited >= 0 )
      {
        v29 = (struct _SecHandle *)LocalAlloc(0x40u, 0x90u);
        v20 = v29;
        if ( v29 )
        {
          *v29 = phContext;
          v30 = phNewContext;
          v29[4].dwUpper = (ULONG_PTR)v24;
          v29[1] = v30;
          LODWORD(v29[5].dwLower) = v62;
          v29[5].dwUpper = v66.QuadPart;
          if ( !a3 )
          {
LABEL_34:
            *(_QWORD *)(a9 + 8) = v20;
            return inited;
          }
          v31 = -1;
          do
            ++v31;
          while ( a3[v31] );
          SizeInWordsa = (unsigned __int16)(v31 + 1);
          v32 = (wchar_t *)LocalAlloc(0x40u, 2LL * (unsigned __int16)SizeInWordsa);
          v20[4].dwLower = (ULONG_PTR)v32;
          if ( v32 )
          {
            wcsncpy_s(v32, SizeInWordsa, a3, SizeInWordsa - 1);
            goto LABEL_34;
          }
        }
LABEL_12:
        inited = -2146893056;
      }
LABEL_13:
      if ( (*v21 & 0x100) != 0 )
      {
        v26 = 0;
        if ( pOutput->cBuffers )
        {
          do
          {
            pvBuffer = pOutput->pBuffers[v26].pvBuffer;
            if ( pvBuffer )
            {
              FreeContextBuffer(pvBuffer);
              pOutput->pBuffers[v26].pvBuffer = 0;
              pOutput->pBuffers[v26].cbBuffer = 0;
            }
            ++v26;
          }
          while ( v26 < pOutput->cBuffers );
          v21 = v63;
        }
      }
      DeleteSecurityContext(&phContext);
      if ( v24 )
      {
        if ( v55 )
        {
          LocalFree(v55);
        }
        else if ( (*v21 & 0x100) != 0 )
        {
          v33 = v24->pBuffers->pvBuffer;
          if ( v33 )
            FreeContextBuffer(v33);
        }
        LocalFree(v24);
      }
      if ( phNewContext.dwLower != -1 && phNewContext.dwUpper != -1 )
        DeleteSecurityContext(&phNewContext);
      if ( v20 )
        LocalFree(v20);
      return inited;
    }
    return -2146893055;
  }
  v34 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v34 + 32) & 1) != 0 )
    goto LABEL_66;
  v35 = *pBuffers;
  pszTargetNamea = pBuffers->cbBuffer;
  if ( a9 )
    *(_QWORD *)(a9 + 8) = v34;
  result = InitializeSecurityContextW(
             v18,
             (PCtxtHandle)v34,
             *(SEC_WCHAR **)(v34 + 64),
             v19,
             0,
             TargetDataRep,
             pInput,
             0,
             (PCtxtHandle)v34,
             pOutput,
             pfContextAttr,
             ptsExpiry);
  if ( !result )
  {
    *(_DWORD *)(v34 + 32) |= 1u;
    v36 = *pfContextAttr & 0x8900;
    *(_DWORD *)(v34 + 36) = v36;
    result = QueryContextAttributesW((PCtxtHandle)v34, (v36 >> 13) & 4, (void *)(v34 + 40));
    if ( result >= 0 )
    {
      result = QueryContextAttributesW((PCtxtHandle)v34, 0x53u, &pBuffer);
      if ( result >= 0 )
      {
        LODWORD(v63) = CredSSPGetSerializedCerts(pBuffer, v34 + 128);
        CertFreeCertificateContext(pBuffer);
        result = (int)v63;
        pBuffer = 0;
        if ( (int)v63 >= 0 )
        {
          v37 = pOutput->pBuffers;
          if ( v37->cbBuffer )
          {
            result = SpEncryptToken((PCtxtHandle)v34);
            if ( result < 0 )
              return result;
            v38 = *(const void ***)(*(_QWORD *)(v34 + 72) + 8LL);
            if ( (*(_DWORD *)(v34 + 36) & 0x100) != 0 )
            {
              v39 = (char *)LocalAlloc(0x40u, *(_DWORD *)v38 + pOutput->pBuffers->cbBuffer);
              v40 = v39;
              if ( v39 )
              {
                memcpy_0(v39, pOutput->pBuffers->pvBuffer, pOutput->pBuffers->cbBuffer);
                FreeContextBuffer(pOutput->pBuffers->pvBuffer);
                pOutput->pBuffers->pvBuffer = v40;
                v38 = *(const void ***)(*(_QWORD *)(v34 + 72) + 8LL);
                v41 = &v40[pOutput->pBuffers->cbBuffer];
                v42 = *(unsigned int *)v38;
LABEL_59:
                memcpy_0(v41, v38[1], v42);
                pOutput->pBuffers->cbBuffer += **(_DWORD **)(*(_QWORD *)(v34 + 72) + 8LL);
                result = 590610;
                *(_DWORD *)(v34 + 32) |= 2u;
                return result;
              }
            }
            else
            {
              v43 = pOutput->pBuffers;
              if ( pszTargetNamea >= v43->cbBuffer + *(_DWORD *)v38 )
              {
                v42 = *(unsigned int *)v38;
                v41 = (char *)v43->pvBuffer + v43->cbBuffer;
                goto LABEL_59;
              }
            }
            return -2146893056;
          }
          *v37 = v35;
          if ( (a4 & 0x100) != 0 )
          {
            v44 = pOutput->pBuffers;
            if ( v44->cbBuffer )
            {
              v45 = v44->pvBuffer;
              if ( v45 )
                FreeContextBuffer(v45);
            }
            v15 = ptsExpiry;
            v18 = SizeInWords;
          }
          else
          {
            v15 = ptsExpiry;
            v18 = SizeInWords;
          }
LABEL_66:
          if ( (*(_BYTE *)(v34 + 32) & 4) != 0 )
          {
            if ( a9 )
              *(_QWORD *)(a9 + 8) = v34;
            return InitializeSecurityContextW(
                     v18,
                     (PCtxtHandle)v34,
                     *(SEC_WCHAR **)(v34 + 64),
                     v19,
                     0,
                     TargetDataRep,
                     pInput,
                     0,
                     (PCtxtHandle)v34,
                     pOutput,
                     pfContextAttr,
                     v15);
          }
          if ( (*(_BYTE *)(v34 + 32) & 2) != 0 )
          {
            result = SpDecryptToken((PCtxtHandle)v34);
            if ( result )
            {
              if ( result != 590625 )
                return result;
              v46 = InitializeSecurityContextW(
                      SizeInWords,
                      (PCtxtHandle)v34,
                      *(SEC_WCHAR **)(v34 + 64),
                      v19,
                      0,
                      TargetDataRep,
                      pInput,
                      0,
                      (PCtxtHandle)v34,
                      pOutput,
                      pfContextAttr,
                      ptsExpiry);
              v47 = 590610;
              if ( v46 )
                return v46;
              return v47;
            }
            v48 = 16;
            if ( *(_QWORD *)(v34 + 96) )
            {
              v48 = 32;
              if ( *(_QWORD *)(v34 + 128) )
                v48 = 48;
            }
            v49 = pInput->pBuffers;
            v65 = v49;
            v50 = (struct _SecBuffer *)LocalAlloc(0x40u, v48);
            pInput->pBuffers = v50;
            if ( !v50 )
            {
              pInput->pBuffers = v49;
              return -2146893056;
            }
            pszTargetNameb = pInput->cBuffers;
            if ( *(_QWORD *)(v34 + 96) )
              v51 = (*(_QWORD *)(v34 + 128) != 0) + 2;
            else
              v51 = 1;
            pInput->cBuffers = v51;
            *v50 = *v49;
            if ( *(_QWORD *)(v34 + 96) )
            {
              pInput->pBuffers[1].cbBuffer = *(_DWORD *)(v34 + 104);
              pInput->pBuffers[1].BufferType = -2147483646;
              pInput->pBuffers[1].pvBuffer = *(void **)(v34 + 96);
              if ( *(_QWORD *)(v34 + 128) )
              {
                pInput->pBuffers[2].cbBuffer = *(_DWORD *)(v34 + 136);
                pInput->pBuffers[2].BufferType = -2147483646;
                pInput->pBuffers[2].pvBuffer = *(void **)(v34 + 128);
              }
            }
            v47 = InitializeSecurityContextW(
                    SizeInWords + 1,
                    (PCtxtHandle)(v34 + 16),
                    *(SEC_WCHAR **)(v34 + 64),
                    a4,
                    0,
                    TargetDataRep,
                    pInput,
                    0,
                    (PCtxtHandle)(v34 + 16),
                    pOutput,
                    pfContextAttr,
                    ptsExpiry);
            LocalFree(pInput->pBuffers);
            pInput->cBuffers = pszTargetNameb;
            pInput->pBuffers = v65;
            v52 = *(void **)(v34 + 96);
            if ( v52 )
            {
              LocalFree(v52);
              *(_QWORD *)(v34 + 96) = 0;
            }
            if ( v47 < 0 )
              return v47;
            if ( !v47 )
              *(_DWORD *)(v34 + 32) |= 4u;
          }
          else
          {
            v53 = pOutput->pBuffers;
            v54 = *(struct _SecBuffer **)(*(_QWORD *)(v34 + 72) + 8LL);
            if ( (*(_DWORD *)(v34 + 36) & 0x100) != 0 )
            {
              *v53 = *v54;
            }
            else
            {
              if ( v53->cbBuffer < v54->cbBuffer )
                return -2146893056;
              v53->cbBuffer = v54->cbBuffer;
              pOutput->pBuffers->BufferType = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v34 + 72) + 8LL) + 4LL);
              memcpy_0(
                pOutput->pBuffers->pvBuffer,
                *(const void **)(*(_QWORD *)(*(_QWORD *)(v34 + 72) + 8LL) + 8LL),
                **(unsigned int **)(*(_QWORD *)(v34 + 72) + 8LL));
              LocalFree(*(HLOCAL *)(*(_QWORD *)(*(_QWORD *)(v34 + 72) + 8LL) + 8LL));
            }
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v34 + 72) + 8LL) + 8LL) = 0;
            if ( ptsExpiry )
              *ptsExpiry = *(PTimeStamp)(v34 + 88);
            v47 = 590610;
            *pfContextAttr = *(_DWORD *)(v34 + 80);
            *(_DWORD *)(v34 + 32) |= 2u;
          }
          if ( pOutput->pBuffers->cbBuffer )
          {
            result = SpEncryptToken((PCtxtHandle)v34);
            if ( result < 0 )
              return result;
          }
          if ( a9 )
            *(_QWORD *)(a9 + 8) = v34;
          return v47;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002560  mov     rax, rsp
0x180002563  push    rbp
0x180002564  push    rbx
0x180002565  push    rsi
0x180002566  push    rdi
0x180002567  push    r12
0x180002569  push    r13
0x18000256b  push    r14
0x18000256d  push    r15
0x18000256f  lea     rbp, [rax-47h]
0x180002573  sub     rsp, 0E8h
0x18000257a  movaps  xmmword ptr [rax-58h], xmm6
0x18000257e  mov     rax, cs:__security_cookie
0x180002585  xor     rax, rsp
0x180002588  mov     qword ptr [rbp+3Fh+var_58], rax
0x18000258c  mov     r12, [rbp+3Fh+arg_50]
0x180002593  xor     ebx, ebx
0x180002595  mov     rsi, [rbp+3Fh+arg_48]
0x18000259c  mov     r11d, r9d
0x18000259f  mov     r14, [rbp+3Fh+arg_30]
0x1800025a3  xorps   xmm0, xmm0
0x1800025a6  mov     r13, [rbp+3Fh+arg_40]
0x1800025ad  mov     [rbp+3Fh+fContextReq], r9d
0x1800025b1  mov     r9, rcx
0x1800025b4  mov     rcx, [rbp+3Fh+arg_58]
0x1800025bb  mov     [rsp+60h], rcx
0x1800025c0  mov     [rbp+3Fh+pszTargetName], r8
0x1800025c4  mov     [rbp+3Fh+var_98], r12
0x1800025c8  mov     [rbp+3Fh+var_A0], ebx
0x1800025cb  mov     qword ptr [rbp+3Fh+var_80], rbx
0x1800025cf  mov     [rbp+3Fh+pBuffer], rbx
0x1800025d3  movups  xmmword ptr [rbp+3Fh+phContext.dwLower], xmm0
0x1800025d7  test    r9, r9
0x1800025da  jz      loc_180002E2E
0x1800025e0  test    rsi, rsi
0x1800025e3  jz      loc_180002E27
0x1800025e9  mov     rax, [rsi+8]
0x1800025ed  test    rax, rax
0x1800025f0  jz      loc_180002E27
0x1800025f6  test    r12, r12
0x1800025f9  jnz     short loc_180002605
0x1800025fb  mov     eax, 8009035Dh
0x180002600  jmp     loc_180002E33
0x180002605  mov     r10, [r9+8]
0x180002609  mov     edi, r11d
0x18000260c  and     edi, 0FFFFFFFCh
0x18000260f  mov     [rbp+3Fh+SizeInWords], r10
0x180002613  bts     edi, 13h
0x180002617  test    rdx, rdx
0x18000261a  jnz     loc_1800028F9
0x180002620  test    r13, r13
0x180002623  jz      loc_180002E2E
0x180002629  mov     [rsp+120h+ptsExpiry], rcx; ptsExpiry
0x18000262e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002632  mov     [rsp+120h+pfContextAttr], r12; pfContextAttr
0x180002637  mov     r9d, edi; fContextReq
0x18000263a  mov     [rsp+120h+pOutput], rsi; pOutput
0x18000263f  mov     rcx, r10; phCredential
0x180002642  mov     [rbp+3Fh+var_78.dwUpper], rax
0x180002646  mov     [rbp+3Fh+var_78.dwLower], rax
0x18000264a  lea     rax, [rbp+3Fh+phContext]
0x18000264e  mov     [rsp+120h+phNewContext], rax; phNewContext
0x180002653  mov     eax, [rbp+3Fh+arg_28]
0x180002656  mov     [rsp+120h+Reserved2], ebx; Reserved2
0x18000265a  mov     [rsp+120h+pInput], rbx; pInput
0x18000265f  mov     [rsp+120h+TargetDataRep], eax; TargetDataRep
0x180002663  mov     [rsp+120h+Reserved1], ebx; Reserved1
0x180002667  call    cs:__imp_InitializeSecurityContextW
0x18000266d  test    eax, eax
0x18000266f  js      loc_180002E33
0x180002675  mov     edi, 90312h
0x18000267a  cmp     eax, edi
0x18000267c  jz      short loc_180002688
0x18000267e  mov     eax, 80090304h
0x180002683  jmp     loc_180002E33
0x180002688  mov     edx, 20h ; ' '; uBytes
0x18000268d  mov     [rsp+60h], rbx
0x180002692  mov     rdi, rbx
0x180002695  lea     r15d, [rdx+20h]
0x180002699  mov     ecx, r15d; uFlags
0x18000269c  call    cs:__imp_LocalAlloc
0x1800026a2  mov     r14, [rbp+3Fh+var_98]
0x1800026a6  xor     r8d, r8d
0x1800026a9  mov     r12, rax
0x1800026ac  test    rax, rax
0x1800026af  jnz     short loc_18000272F
0x1800026b1  mov     ebx, 80090300h
0x1800026b6  test    dword ptr [r14], 100h
0x1800026bd  jz      short loc_180002703
0x1800026bf  mov     r15d, r8d
0x1800026c2  cmp     [rsi+4], r8d
0x1800026c6  jbe     short loc_180002703
0x1800026c8  mov     rax, [rsi+8]
0x1800026cc  mov     r14d, r15d
0x1800026cf  add     r14, r14
0x1800026d2  mov     rcx, [rax+r14*8+8]; pvContextBuffer
0x1800026d7  test    rcx, rcx
0x1800026da  jz      short loc_1800026F6
0x1800026dc  call    cs:__imp_FreeContextBuffer
0x1800026e2  mov     rax, [rsi+8]
0x1800026e6  xor     r8d, r8d
0x1800026e9  mov     [rax+r14*8+8], r8
0x1800026ee  mov     rax, [rsi+8]
0x1800026f2  mov     [rax+r14*8], r8d
0x1800026f6  inc     r15d
0x1800026f9  cmp     r15d, [rsi+4]
0x1800026fd  jb      short loc_1800026C8
0x1800026ff  mov     r14, [rbp+3Fh+var_98]
0x180002703  lea     rcx, [rbp+3Fh+phContext]; phContext
0x180002707  call    cs:__imp_DeleteSecurityContext
0x18000270d  test    r12, r12
0x180002710  jz      loc_1800028D1
0x180002716  mov     rcx, [rsp+60h]; hMem
0x18000271b  test    rcx, rcx
0x18000271e  jz      loc_1800028AB
0x180002724  call    cs:__imp_LocalFree
0x18000272a  jmp     loc_1800028C8
0x18000272f  test    dword ptr [r14], 100h
0x180002736  jnz     short loc_180002779
0x180002738  mov     eax, cs:uBytes
0x18000273e  test    eax, eax
0x180002740  jnz     short loc_18000275A
0x180002742  call    InitMaxToken
0x180002747  xor     r8d, r8d
0x18000274a  mov     ebx, eax
0x18000274c  test    eax, eax
0x18000274e  js      loc_1800026B6
0x180002754  mov     eax, cs:uBytes
0x18000275a  mov     edx, eax; uBytes
0x18000275c  mov     ecx, r15d; uFlags
0x18000275f  call    cs:__imp_LocalAlloc
0x180002765  xor     r8d, r8d
0x180002768  mov     [rsp+60h], rax
0x18000276d  mov     rbx, rax
0x180002770  test    rax, rax
0x180002773  jz      loc_1800026B1
0x180002779  mov     eax, [rsi]
0x18000277b  lea     rdx, [r12+10h]
0x180002780  mov     r9d, [rbp+3Fh+fContextReq]; fContextReq
0x180002784  mov     [r12], eax
0x180002788  mov     rax, rbx
0x18000278b  neg     rax
0x18000278e  mov     [r12+8], rdx
0x180002793  mov     dword ptr [r12+4], 1
0x18000279c  sbb     ecx, ecx
0x18000279e  and     ecx, cs:uBytes
0x1800027a4  mov     [rdx], ecx
0x1800027a6  mov     rcx, [rbp+3Fh+SizeInWords]
0x1800027aa  mov     dword ptr [rdx+4], 2
0x1800027b1  add     rcx, 10h; phCredential
0x1800027b5  mov     rax, [r12+8]
0x1800027ba  xor     edx, edx; phContext
0x1800027bc  mov     [rax+8], rbx
0x1800027c0  lea     rax, [rbp+3Fh+var_80]
0x1800027c4  mov     [rsp+120h+ptsExpiry], rax; ptsExpiry
0x1800027c9  lea     rax, [rbp+3Fh+var_A0]
0x1800027cd  mov     [rsp+120h+pfContextAttr], rax; pfContextAttr
0x1800027d2  lea     rax, [rbp+3Fh+var_78]
0x1800027d6  mov     [rsp+120h+pOutput], r12; pOutput
0x1800027db  mov     [rsp+120h+phNewContext], rax; phNewContext
0x1800027e0  mov     eax, [rbp+3Fh+arg_28]
0x1800027e3  mov     [rsp+120h+Reserved2], r8d; Reserved2
0x1800027e8  mov     [rsp+120h+pInput], r8; pInput
0x1800027ed  mov     [rsp+120h+TargetDataRep], eax; TargetDataRep
0x1800027f1  mov     [rsp+120h+Reserved1], r8d; Reserved1
0x1800027f6  mov     r8, [rbp+3Fh+pszTargetName]; pszTargetName
0x1800027fa  call    cs:__imp_InitializeSecurityContextW
0x180002800  xor     r8d, r8d
0x180002803  mov     ebx, eax
0x180002805  test    eax, eax
0x180002807  js      loc_1800026B6
0x18000280d  mov     edx, 90h; uBytes
0x180002812  mov     ecx, r15d; uFlags
0x180002815  call    cs:__imp_LocalAlloc
0x18000281b  xor     r8d, r8d
0x18000281e  mov     rdi, rax
0x180002821  test    rax, rax
0x180002824  jz      loc_1800026B1
0x18000282a  movups  xmm0, xmmword ptr [rbp+3Fh+phContext.dwLower]
0x18000282e  mov     rcx, [rbp+3Fh+pszTargetName]
0x180002832  movdqu  xmmword ptr [rax], xmm0
0x180002836  movups  xmm1, xmmword ptr [rbp+3Fh+var_78.dwLower]
0x18000283a  mov     [rax+48h], r12
0x18000283e  movdqu  xmmword ptr [rax+10h], xmm1
0x180002843  mov     eax, [rbp+3Fh+var_A0]
0x180002846  mov     [rdi+50h], eax
0x180002849  mov     rax, qword ptr [rbp+3Fh+var_80]
0x18000284d  mov     [rdi+58h], rax
0x180002851  test    rcx, rcx
0x180002854  jz      short loc_1800028A0
0x180002856  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000285a  inc     rax
0x18000285d  cmp     [rcx+rax*2], r8w
0x180002862  jnz     short loc_18000285A
0x180002864  inc     ax
0x180002867  mov     ecx, r15d; uFlags
0x18000286a  movzx   eax, ax
0x18000286d  mov     [rbp+3Fh+SizeInWords], rax
0x180002871  lea     rdx, [rax+rax]; uBytes
0x180002875  call    cs:__imp_LocalAlloc
0x18000287b  xor     r8d, r8d
0x18000287e  mov     [rdi+40h], rax
0x180002882  test    rax, rax
0x180002885  jz      loc_1800026B1
0x18000288b  mov     rdx, [rbp+3Fh+SizeInWords]; SizeInWords
0x18000288f  mov     rcx, rax; Destination
0x180002892  mov     r8, [rbp+3Fh+pszTargetName]; Source
0x180002896  lea     r9, [rdx-1]; MaxCount
0x18000289a  call    cs:__imp_wcsncpy_s
0x1800028a0  mov     [r13+8], rdi
0x1800028a4  mov     eax, ebx
0x1800028a6  jmp     loc_180002E33
0x1800028ab  test    dword ptr [r14], 100h
0x1800028b2  jz      short loc_1800028C8
0x1800028b4  mov     rax, [r12+8]
0x1800028b9  mov     rcx, [rax+8]; pvContextBuffer
0x1800028bd  test    rcx, rcx
0x1800028c0  jz      short loc_1800028C8
0x1800028c2  call    cs:__imp_FreeContextBuffer
0x1800028c8  mov     rcx, r12; hMem
0x1800028cb  call    cs:__imp_LocalFree
0x1800028d1  cmp     [rbp+3Fh+var_78.dwLower], 0FFFFFFFFFFFFFFFFh
0x1800028d6  jz      short loc_1800028E9
0x1800028d8  cmp     [rbp+3Fh+var_78.dwUpper], 0FFFFFFFFFFFFFFFFh
0x1800028dd  jz      short loc_1800028E9
0x1800028df  lea     rcx, [rbp+3Fh+var_78]; phContext
0x1800028e3  call    cs:__imp_DeleteSecurityContext
0x1800028e9  test    rdi, rdi
0x1800028ec  jz      short loc_1800028A4
0x1800028ee  mov     rcx, rdi; hMem
0x1800028f1  call    cs:__imp_LocalFree
0x1800028f7  jmp     short loc_1800028A4
0x1800028f9  mov     rbx, [rdx+8]
0x1800028fd  mov     r15d, 100h
0x180002903  mov     edx, 1
0x180002908  test    [rbx+20h], dl
0x18000290b  jnz     loc_180002B1D
0x180002911  movups  xmm6, xmmword ptr [rax]
0x180002914  mov     eax, [rax]
0x180002916  mov     dword ptr [rbp+3Fh+pszTargetName], eax
0x180002919  test    r13, r13
0x18000291c  jz      short loc_180002922
0x18000291e  mov     [r13+8], rbx
0x180002922  mov     eax, [rbp+3Fh+arg_28]
0x180002925  mov     r9d, edi; fContextReq
0x180002928  mov     r8, [rbx+40h]; pszTargetName
0x18000292c  mov     rdx, rbx; phContext
0x18000292f  mov     [rsp+120h+ptsExpiry], rcx; ptsExpiry
0x180002934  mov     rcx, r10; phCredential
0x180002937  mov     [rsp+120h+pfContextAttr], r12; pfContextAttr
0x18000293c  mov     [rsp+120h+pOutput], rsi; pOutput
0x180002941  mov     [rsp+120h+phNewContext], rbx; phNewContext
0x180002946  mov     [rsp+120h+Reserved2], 0; Reserved2
0x18000294e  mov     [rsp+120h+pInput], r14; pInput
0x180002953  mov     [rsp+120h+TargetDataRep], eax; TargetDataRep
0x180002957  mov     [rsp+120h+Reserved1], 0; Reserved1
0x18000295f  call    cs:__imp_InitializeSecurityContextW
0x180002965  test    eax, eax
0x180002967  jnz     loc_180002E33
0x18000296d  or      dword ptr [rbx+20h], 1
0x180002971  lea     r8, [rbx+28h]; pBuffer
0x180002975  mov     edx, [r12]
0x180002979  mov     rcx, rbx; phContext
0x18000297c  and     edx, 8900h
0x180002982  mov     [rbx+24h], edx
0x180002985  shr     edx, 0Dh
0x180002988  and     edx, 4; ulAttribute
0x18000298b  call    cs:__imp_QueryContextAttributesW
0x180002991  test    eax, eax
0x180002993  js      loc_180002E33
0x180002999  lea     r8, [rbp+3Fh+pBuffer]; pBuffer
0x18000299d  mov     edx, 53h ; 'S'; ulAttribute
0x1800029a2  mov     rcx, rbx; phContext
0x1800029a5  call    cs:__imp_QueryContextAttributesW
0x1800029ab  test    eax, eax
0x1800029ad  js      loc_180002E33
0x1800029b3  mov     rcx, [rbp+3Fh+pBuffer]; pCertContext
0x1800029b7  lea     rax, [rbx+80h]
0x1800029be  lea     r9, [rbx+88h]
0x1800029c5  mov     qword ptr [rsp+120h+Reserved1], rax; __int64
0x1800029ca  lea     r8, [rbx+60h]
0x1800029ce  lea     rdx, [rbx+68h]
0x1800029d2  call    CredSSPGetSerializedCerts
0x1800029d7  mov     rcx, [rbp+3Fh+pBuffer]; pCertContext
0x1800029db  mov     dword ptr [rbp+3Fh+var_98], eax
0x1800029de  call    cs:__imp_CertFreeCertificateContext
0x1800029e4  mov     eax, dword ptr [rbp+3Fh+var_98]
0x1800029e7  mov     [rbp+3Fh+pBuffer], 0
0x1800029ef  test    eax, eax
0x1800029f1  js      loc_180002E33
0x1800029f7  mov     rax, [rsi+8]
0x1800029fb  cmp     dword ptr [rax], 0
0x1800029fe  jz      loc_180002ADA
0x180002a04  mov     r8d, cs:uBytes
0x180002a0b  mov     r9d, 1
0x180002a11  mov     rdx, [rbx+48h]
0x180002a15  mov     rcx, rbx; phContext
0x180002a18  call    SpEncryptToken
0x180002a1d  test    eax, eax
0x180002a1f  js      loc_180002E33
  ... truncated ...
```
