# SpAcceptSecurityContext

- ea: `0x180001b50`
- end: `0x1800020c0`
- name: `SpAcceptSecurityContext`
- size: `1392`
- prototype: `int __fastcall(__int64, __int64, struct _SecBufferDesc *, unsigned int, unsigned int TargetDataRep, __int64, PSecBufferDesc pOutput, unsigned int *pfContextAttr, SECURITY_INTEGER *ptsExpiry)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001b50`
- `0x1800035b4`
- `0x1800039e4`
- `0x180003e20`

## import_xrefs

- `SspiCli!QueryContextAttributesW` at `0x180001e01`
- `SspiCli!QueryContextAttributesW` at `0x180001e01`
- `SspiCli!DeleteSecurityContext` at `0x180001c43`
- `SspiCli!DeleteSecurityContext` at `0x180001c43`
- `SspiCli!AcceptSecurityContext` at `0x180001c1d`
- `SspiCli!AcceptSecurityContext` at `0x180001d7f`
- `SspiCli!AcceptSecurityContext` at `0x180001eb7`
- `SspiCli!AcceptSecurityContext` at `0x18000201a`
- `SspiCli!AcceptSecurityContext` at `0x180001c1d`
- `SspiCli!AcceptSecurityContext` at `0x180001d7f`
- `SspiCli!AcceptSecurityContext` at `0x180001eb7`
- `SspiCli!AcceptSecurityContext` at `0x18000201a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001c34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001c34`

## pseudocode

```c
int __fastcall SpAcceptSecurityContext(
        __int64 a1,
        __int64 a2,
        struct _SecBufferDesc *a3,
        unsigned int a4,
        unsigned int TargetDataRep,
        __int64 a6,
        PSecBufferDesc pOutput,
        unsigned int *pfContextAttr,
        SECURITY_INTEGER *ptsExpiry)
{
  SECURITY_INTEGER *v9; // rax
  unsigned int *v11; // r8
  struct _SecBuffer v12; // xmm7
  struct _SecHandle *v13; // r10
  int result; // eax
  SECURITY_STATUS v15; // ebx
  struct _SecHandle *v16; // rax
  __int64 phNewContext; // rdi
  struct _SecBuffer *v18; // r14
  struct _SecBuffer *v19; // rsi
  unsigned int v20; // edx
  PSecBuffer pBuffers; // r11
  struct _SecBuffer *v22; // rcx
  int v23; // eax
  struct _SecBufferDesc v24; // xmm6
  struct _SecBuffer *v25; // rax
  SECURITY_STATUS v26; // edx
  unsigned int *v27; // rax
  unsigned int v28; // edx
  char *pvBuffer; // rcx
  unsigned int cbBuffer; // r8d
  unsigned int v31; // r9d
  SECURITY_STATUS v32; // eax
  void *v33; // rcx
  _QWORD *p_cbBuffer; // rcx
  __int64 v35; // rax
  struct _SecHandle *v36; // rcx
  _OWORD *v37; // rcx
  int v38; // eax
  int v39; // eax
  int v40; // eax
  char v41; // [rsp+58h] [rbp-A1h]
  unsigned int fContextReq; // [rsp+5Ch] [rbp-9Dh]
  unsigned int v43; // [rsp+60h] [rbp-99h]
  _OWORD v44[2]; // [rsp+68h] [rbp-91h] BYREF
  struct _SecHandle *v45; // [rsp+88h] [rbp-71h]
  PTimeStamp v46; // [rsp+90h] [rbp-69h]
  unsigned int *v47; // [rsp+98h] [rbp-61h]
  void *v48; // [rsp+A0h] [rbp-59h]
  __int128 v49; // [rsp+A8h] [rbp-51h] BYREF
  struct _SecHandle phContext; // [rsp+B8h] [rbp-41h] BYREF

  v9 = ptsExpiry;
  v11 = pfContextAttr;
  v47 = pfContextAttr;
  v12 = 0;
  fContextReq = a4;
  v46 = ptsExpiry;
  phContext = 0;
  v49 = 0;
  if ( !a1 )
    return -2146893055;
  if ( !pOutput || !pOutput->pBuffers )
    return -2146893048;
  v13 = *(struct _SecHandle **)(a1 + 8);
  v45 = v13;
  if ( !a2 )
  {
    if ( a6 )
    {
      result = AcceptSecurityContext(
                 v13,
                 0,
                 a3,
                 a4 & 0xFFFFFFFD,
                 TargetDataRep,
                 &phContext,
                 pOutput,
                 pfContextAttr,
                 ptsExpiry);
      v15 = 590610;
      if ( result == 590610 )
      {
        v16 = (struct _SecHandle *)LocalAlloc(0x40u, 0x90u);
        if ( !v16 )
        {
          DeleteSecurityContext(&phContext);
          return -2146893056;
        }
        *v16 = phContext;
        *(_QWORD *)(a6 + 8) = v16;
        return v15;
      }
      if ( result != -2146893032 && result != 590624 )
        return -2146893052;
      return result;
    }
    return -2146893055;
  }
  phNewContext = *(_QWORD *)(a2 + 8);
  v18 = 0;
  v48 = 0;
  v19 = 0;
  v43 = 0;
  v41 = 0;
  if ( (*(_BYTE *)(phNewContext + 32) & 1) != 0 )
  {
LABEL_41:
    if ( (*(_BYTE *)(phNewContext + 32) & 4) != 0 )
    {
      v31 = a4 & 0xFFFFFFFD;
      if ( a6 )
        *(_QWORD *)(a6 + 8) = phNewContext;
      return AcceptSecurityContext(
               v13,
               (PCtxtHandle)phNewContext,
               a3,
               v31,
               TargetDataRep,
               (PCtxtHandle)phNewContext,
               pOutput,
               v11,
               v9);
    }
    if ( a3 )
    {
      v32 = SpDecryptToken((PCtxtHandle)phNewContext);
      v15 = v32;
      if ( v32 )
      {
        v33 = v48;
        if ( v48 )
        {
          if ( v32 == -2146893032 )
          {
            if ( v19 )
            {
              v15 = 590610;
              v19->pvBuffer = v18->pvBuffer;
              v19->cbBuffer = v18->cbBuffer;
              v19->BufferType = 5;
            }
            else
            {
              v15 = -2146892963;
            }
          }
          v18->cbBuffer = v43;
          v18->pvBuffer = v33;
        }
        return v15;
      }
      if ( (*(_BYTE *)(phNewContext + 32) & 2) == 0 )
      {
        if ( v41 )
          *pOutput->pBuffers = v12;
        p_cbBuffer = &a3->pBuffers->cbBuffer;
        *(_QWORD *)&v49 = 0x200000000LL;
        *((_QWORD *)&v49 + 1) = v44;
        *(_QWORD *)&v44[0] = *p_cbBuffer;
        v35 = p_cbBuffer[1];
        v36 = v45;
        *((_QWORD *)&v44[0] + 1) = v35;
        DWORD1(v44[1]) = -2147483646;
        LODWORD(v44[1]) = v45[2].dwLower;
        *((_QWORD *)&v44[1] + 1) = v45[2].dwUpper;
LABEL_61:
        v15 = AcceptSecurityContext(
                v36 + 1,
                (PCtxtHandle)((phNewContext + 16) & -(__int64)((*(_DWORD *)(phNewContext + 32) & 2) != 0)),
                (PSecBufferDesc)((unsigned __int64)&v49 & -(__int64)(a3 != 0)),
                fContextReq,
                TargetDataRep,
                (PCtxtHandle)(phNewContext + 16),
                pOutput,
                v47,
                v46);
        if ( v48 )
        {
          v18->pvBuffer = v48;
          v18->cbBuffer = v43;
        }
        if ( v15 < 0 )
          return v15;
        if ( a6 )
          *(_QWORD *)(a6 + 8) = phNewContext;
        v38 = *(_DWORD *)(phNewContext + 32);
        if ( v15 )
        {
          if ( (v38 & 2) != 0 )
          {
LABEL_71:
            if ( pOutput->pBuffers->cbBuffer )
            {
              v40 = SpEncryptToken((PCtxtHandle)phNewContext);
              if ( v40 < 0 )
                return v40;
            }
            return v15;
          }
          v39 = v38 | 2;
        }
        else
        {
          v39 = v38 | 4;
        }
        *(_DWORD *)(phNewContext + 32) = v39;
        goto LABEL_71;
      }
      v37 = &a3->pBuffers->cbBuffer;
      *(_QWORD *)&v49 = 0x100000000LL;
      *((_QWORD *)&v49 + 1) = v44;
      v44[0] = *v37;
    }
    v36 = v45;
    goto LABEL_61;
  }
  if ( !a3 || !a3->pBuffers )
    return -2146892963;
  if ( a6 )
    *(_QWORD *)(a6 + 8) = phNewContext;
  if ( !a3->cBuffers )
    return -2146892963;
  v20 = 0;
  pBuffers = a3->pBuffers;
  do
  {
    v22 = &pBuffers[v20];
    v23 = v22->BufferType & 0xFFFFFFF;
    if ( v23 == 2 )
    {
      if ( v22->cbBuffer )
        v18 = &pBuffers[v20];
    }
    else if ( !v23 )
    {
      v19 = &pBuffers[v20];
    }
    ++v20;
  }
  while ( v20 < a3->cBuffers );
  if ( !v18 )
    return -2146892963;
  v24 = *a3;
  a3->cBuffers = 2;
  a3->pBuffers = (PSecBuffer)v44;
  v44[0] = *v18;
  v25 = pOutput->pBuffers;
  *((_QWORD *)&v44[1] + 1) = 0;
  fContextReq = a4 & 0xFFFFFFFD;
  v12 = *v25;
  v26 = AcceptSecurityContext(
          v13,
          (PCtxtHandle)phNewContext,
          a3,
          a4 & 0xFFFFFFFD,
          TargetDataRep,
          (PCtxtHandle)phNewContext,
          pOutput,
          pfContextAttr,
          v46);
  *a3 = v24;
  if ( v26 )
  {
    *v18 = (struct _SecBuffer)v44[0];
    if ( v19 )
      *v19 = (struct _SecBuffer)v44[1];
    return v26;
  }
  if ( v19 )
    *v19 = (struct _SecBuffer)v44[1];
  v27 = v47;
  *(_DWORD *)(phNewContext + 32) |= 1u;
  v28 = *v27 & 0x10900;
  *(_DWORD *)(phNewContext + 36) = v28;
  result = QueryContextAttributesW((PCtxtHandle)phNewContext, (v28 >> 14) & 4, (void *)(phNewContext + 40));
  if ( result >= 0 )
  {
    if ( pOutput->pBuffers->cbBuffer )
      return 590610;
    if ( LODWORD(v44[1]) )
    {
      if ( LODWORD(v44[0]) < LODWORD(v44[1]) )
        return -1073741675;
      pvBuffer = (char *)v18->pvBuffer;
      cbBuffer = v18->cbBuffer;
      a4 = fContextReq;
      v13 = v45;
      v18->pvBuffer = &pvBuffer[LODWORD(v44[0]) - LODWORD(v44[1])];
      v18->cbBuffer = v44[1];
      v9 = v46;
      v43 = cbBuffer;
      v11 = v47;
      memset(v44, 0, sizeof(v44));
      v41 = 1;
      v48 = pvBuffer;
      goto LABEL_41;
    }
    return -2146893048;
  }
  return result;
}

```

## disassembly

```asm
0x180001b50  mov     rax, rsp
0x180001b53  push    rbp
0x180001b54  push    rbx
0x180001b55  push    rsi
0x180001b56  push    rdi
0x180001b57  push    r12
0x180001b59  push    r13
0x180001b5b  push    r14
0x180001b5d  push    r15
0x180001b5f  lea     rbp, [rax-47h]
0x180001b63  sub     rsp, 0F8h
0x180001b6a  movaps  xmmword ptr [rax-58h], xmm6
0x180001b6e  movaps  xmmword ptr [rax-68h], xmm7
0x180001b72  mov     rax, cs:__security_cookie
0x180001b79  xor     rax, rsp
0x180001b7c  mov     [rbp+3Fh+var_70], rax
0x180001b80  mov     rax, [rbp+3Fh+arg_40]
0x180001b87  mov     r15, r8
0x180001b8a  mov     r8, [rbp+3Fh+arg_38]
0x180001b91  xor     r11d, r11d
0x180001b94  mov     r12, [rbp+3Fh+arg_28]
0x180001b98  xorps   xmm0, xmm0
0x180001b9b  mov     r13, [rbp+3Fh+arg_30]
0x180001b9f  xorps   xmm1, xmm1
0x180001ba2  mov     [rbp+3Fh+var_A0], r8
0x180001ba6  xorps   xmm7, xmm7
0x180001ba9  mov     [rsp+130h+fContextReq], r9d
0x180001bae  mov     [rbp+3Fh+var_A8], rax
0x180001bb2  movups  xmmword ptr [rbp+3Fh+phContext.dwLower], xmm0
0x180001bb6  movups  [rbp+3Fh+var_90], xmm1
0x180001bba  test    rcx, rcx
0x180001bbd  jz      loc_18000208D
0x180001bc3  test    r13, r13
0x180001bc6  jz      loc_180002086
0x180001bcc  cmp     [r13+8], r11
0x180001bd0  jz      loc_180002086
0x180001bd6  mov     r10, [rcx+8]
0x180001bda  mov     [rbp+3Fh+var_B0], r10
0x180001bde  test    rdx, rdx
0x180001be1  jnz     loc_180001C84
0x180001be7  test    r12, r12
0x180001bea  jz      loc_18000208D
0x180001bf0  mov     [rsp+130h+ptsExpiry], rax; ptsExpiry
0x180001bf5  mov     ebx, 0FFFFFFFDh
0x180001bfa  mov     [rsp+130h+pfContextAttr], r8; pfContextAttr
0x180001bff  lea     rax, [rbp+3Fh+phContext]
0x180001c03  mov     [rsp+130h+pOutput], r13; pOutput
0x180001c08  and     r9d, ebx; fContextReq
0x180001c0b  mov     [rsp+130h+phNewContext], rax; phNewContext
0x180001c10  mov     r8, r15; pInput
0x180001c13  mov     eax, [rbp+3Fh+arg_20]
0x180001c16  mov     rcx, r10; phCredential
0x180001c19  mov     [rsp+130h+TargetDataRep], eax; TargetDataRep
0x180001c1d  call    cs:__imp_AcceptSecurityContext
0x180001c23  mov     ebx, 90312h
0x180001c28  cmp     eax, ebx
0x180001c2a  jnz     short loc_180001C67
0x180001c2c  mov     edx, 90h; uBytes
0x180001c31  lea     ecx, [rdx-50h]; uFlags
0x180001c34  call    cs:__imp_LocalAlloc
0x180001c3a  test    rax, rax
0x180001c3d  jnz     short loc_180001C53
0x180001c3f  lea     rcx, [rbp+3Fh+phContext]; phContext
0x180001c43  call    cs:__imp_DeleteSecurityContext
0x180001c49  mov     eax, 80090300h
0x180001c4e  jmp     loc_180002092
0x180001c53  movups  xmm0, xmmword ptr [rbp+3Fh+phContext.dwLower]
0x180001c57  movdqu  xmmword ptr [rax], xmm0
0x180001c5b  mov     [r12+8], rax
0x180001c60  mov     eax, ebx
0x180001c62  jmp     loc_180002092
0x180001c67  cmp     eax, 80090318h
0x180001c6c  jz      loc_180002092
0x180001c72  cmp     eax, 90320h
0x180001c77  mov     ecx, 80090304h
0x180001c7c  cmovnz  eax, ecx
0x180001c7f  jmp     loc_180002092
0x180001c84  mov     rdi, [rdx+8]
0x180001c88  mov     r14, r11
0x180001c8b  mov     [rbp+3Fh+var_98], r11
0x180001c8f  mov     rsi, r11
0x180001c92  mov     dword ptr [rsp+130h+var_D8], r11d
0x180001c97  mov     ebx, 0FFFFFFFDh
0x180001c9c  mov     byte ptr [rsp+130h+var_E0], r11b
0x180001ca1  test    byte ptr [rdi+20h], 1
0x180001ca5  jnz     loc_180001E80
0x180001cab  test    r15, r15
0x180001cae  jz      loc_180001ECC
0x180001cb4  cmp     [r15+8], r11
0x180001cb8  jz      loc_180001ECC
0x180001cbe  test    r12, r12
0x180001cc1  jz      short loc_180001CC8
0x180001cc3  mov     [r12+8], rdi
0x180001cc8  cmp     [r15+4], r11d
0x180001ccc  jbe     loc_180001ECC
0x180001cd2  mov     edx, r11d
0x180001cd5  mov     r11, [r15+8]
0x180001cd9  mov     ecx, edx
0x180001cdb  shl     rcx, 4
0x180001cdf  add     rcx, r11
0x180001ce2  mov     eax, [rcx+4]
0x180001ce5  and     eax, 0FFFFFFFh
0x180001cea  cmp     eax, 2
0x180001ced  jnz     short loc_180001CF9
0x180001cef  cmp     dword ptr [rcx], 0
0x180001cf2  jz      short loc_180001CFF
0x180001cf4  mov     r14, rcx
0x180001cf7  jmp     short loc_180001CFF
0x180001cf9  test    eax, eax
0x180001cfb  cmovz   rsi, rcx
0x180001cff  inc     edx
0x180001d01  cmp     edx, [r15+4]
0x180001d05  jb      short loc_180001CD9
0x180001d07  xor     ecx, ecx
0x180001d09  test    r14, r14
0x180001d0c  jz      loc_180001ECC
0x180001d12  movups  xmm6, xmmword ptr [r15]
0x180001d16  mov     dword ptr [r15+4], 2
0x180001d1e  lea     rax, [rsp+130h+var_D8+8]
0x180001d23  mov     [r15+8], rax
0x180001d27  and     r9d, ebx; fContextReq
0x180001d2a  mov     eax, [r14+4]
0x180001d2e  mov     rdx, rdi; phContext
0x180001d31  mov     dword ptr [rsp+130h+var_D8+0Ch], eax
0x180001d35  mov     eax, [r14]
0x180001d38  mov     dword ptr [rsp+130h+var_D8+8], eax
0x180001d3c  mov     rax, [r14+8]
0x180001d40  mov     qword ptr [rsp+130h+var_C8], rax
0x180001d45  mov     rax, [r13+8]
0x180001d49  mov     qword ptr [rsp+130h+var_C8+8], rcx
0x180001d4e  mov     [rbp+3Fh+var_B8], rcx
0x180001d52  mov     rcx, r10; phCredential
0x180001d55  mov     [rsp+130h+fContextReq], r9d
0x180001d5a  movups  xmm7, xmmword ptr [rax]
0x180001d5d  mov     rax, [rbp+3Fh+var_A8]
0x180001d61  mov     [rsp+130h+ptsExpiry], rax; ptsExpiry
0x180001d66  mov     eax, [rbp+3Fh+arg_20]
0x180001d69  mov     [rsp+130h+pfContextAttr], r8; pfContextAttr
0x180001d6e  mov     r8, r15; pInput
0x180001d71  mov     [rsp+130h+pOutput], r13; pOutput
0x180001d76  mov     [rsp+130h+phNewContext], rdi; phNewContext
0x180001d7b  mov     [rsp+130h+TargetDataRep], eax; TargetDataRep
0x180001d7f  call    cs:__imp_AcceptSecurityContext
0x180001d85  mov     edx, eax
0x180001d87  movdqu  xmmword ptr [r15], xmm6
0x180001d8c  test    eax, eax
0x180001d8e  jz      short loc_180001DC8
0x180001d90  mov     ecx, dword ptr [rsp+130h+var_D8+8]
0x180001d94  mov     [r14], ecx
0x180001d97  mov     ecx, dword ptr [rsp+130h+var_D8+0Ch]
0x180001d9b  mov     [r14+4], ecx
0x180001d9f  mov     rcx, qword ptr [rsp+130h+var_C8]
0x180001da4  mov     [r14+8], rcx
0x180001da8  test    rsi, rsi
0x180001dab  jz      short loc_180001DC1
0x180001dad  mov     eax, dword ptr [rsp+130h+var_C8+8]
0x180001db1  mov     [rsi], eax
0x180001db3  mov     eax, dword ptr [rbp+3Fh+var_C8+0Ch]
0x180001db6  mov     [rsi+4], eax
0x180001db9  mov     rax, [rbp+3Fh+var_B8]
0x180001dbd  mov     [rsi+8], rax
0x180001dc1  mov     eax, edx
0x180001dc3  jmp     loc_180002092
0x180001dc8  test    rsi, rsi
0x180001dcb  jz      short loc_180001DE1
0x180001dcd  mov     eax, dword ptr [rsp+130h+var_C8+8]
0x180001dd1  mov     [rsi], eax
0x180001dd3  mov     eax, dword ptr [rbp+3Fh+var_C8+0Ch]
0x180001dd6  mov     [rsi+4], eax
0x180001dd9  mov     rax, [rbp+3Fh+var_B8]
0x180001ddd  mov     [rsi+8], rax
0x180001de1  mov     rax, [rbp+3Fh+var_A0]
0x180001de5  lea     r8, [rdi+28h]; pBuffer
0x180001de9  or      dword ptr [rdi+20h], 1
0x180001ded  mov     rcx, rdi; phContext
0x180001df0  mov     edx, [rax]
0x180001df2  and     edx, 10900h
0x180001df8  mov     [rdi+24h], edx
0x180001dfb  shr     edx, 0Eh
0x180001dfe  and     edx, 4; ulAttribute
0x180001e01  call    cs:__imp_QueryContextAttributesW
0x180001e07  xor     r11d, r11d
0x180001e0a  test    eax, eax
0x180001e0c  js      loc_180002092
0x180001e12  mov     rax, [r13+8]
0x180001e16  cmp     [rax], r11d
0x180001e19  jz      short loc_180001E25
0x180001e1b  mov     eax, 90312h
0x180001e20  jmp     loc_180002092
0x180001e25  mov     edx, dword ptr [rsp+130h+var_C8+8]
0x180001e29  test    edx, edx
0x180001e2b  jz      loc_180002086
0x180001e31  mov     eax, dword ptr [rsp+130h+var_D8+8]
0x180001e35  cmp     eax, edx
0x180001e37  jb      loc_180001EC2
0x180001e3d  mov     rcx, [r14+8]
0x180001e41  sub     eax, edx
0x180001e43  mov     r8d, [r14]
0x180001e46  add     rax, rcx
0x180001e49  mov     r9d, [rsp+130h+fContextReq]
0x180001e4e  xorps   xmm0, xmm0
0x180001e51  mov     r10, [rbp+3Fh+var_B0]
0x180001e55  mov     [r14+8], rax
0x180001e59  mov     eax, dword ptr [rsp+130h+var_C8+8]
0x180001e5d  mov     [r14], eax
0x180001e60  mov     rax, [rbp+3Fh+var_A8]
0x180001e64  mov     dword ptr [rsp+130h+var_D8], r8d
0x180001e69  mov     r8, [rbp+3Fh+var_A0]
0x180001e6d  movups  [rsp+130h+var_D8+8], xmm0
0x180001e72  mov     byte ptr [rsp+130h+var_E0], 1
0x180001e77  movups  [rsp+130h+var_C8+8], xmm0
0x180001e7c  mov     [rbp+3Fh+var_98], rcx
0x180001e80  test    byte ptr [rdi+20h], 4
0x180001e84  jz      short loc_180001ED6
0x180001e86  and     r9d, ebx; fContextReq
0x180001e89  test    r12, r12
0x180001e8c  jz      short loc_180001E93
0x180001e8e  mov     [r12+8], rdi
0x180001e93  mov     [rsp+130h+ptsExpiry], rax; ptsExpiry
0x180001e98  mov     rdx, rdi; phContext
0x180001e9b  mov     eax, [rbp+3Fh+arg_20]
0x180001e9e  mov     rcx, r10; phCredential
0x180001ea1  mov     [rsp+130h+pfContextAttr], r8; pfContextAttr
0x180001ea6  mov     r8, r15; pInput
0x180001ea9  mov     [rsp+130h+pOutput], r13; pOutput
0x180001eae  mov     [rsp+130h+phNewContext], rdi; phNewContext
0x180001eb3  mov     [rsp+130h+TargetDataRep], eax; TargetDataRep
0x180001eb7  call    cs:__imp_AcceptSecurityContext
0x180001ebd  jmp     loc_180002092
0x180001ec2  mov     eax, 0C0000095h
0x180001ec7  jmp     loc_180002092
0x180001ecc  mov     eax, 8009035Dh
0x180001ed1  jmp     loc_180002092
0x180001ed6  test    r15, r15
0x180001ed9  jz      loc_180001FC6
0x180001edf  xor     r8d, r8d
0x180001ee2  mov     rdx, r15
0x180001ee5  mov     rcx, rdi; phContext
0x180001ee8  call    SpDecryptToken
0x180001eed  xor     edx, edx
0x180001eef  mov     ebx, eax
0x180001ef1  test    eax, eax
0x180001ef3  jz      short loc_180001F3C
0x180001ef5  mov     rcx, [rbp+3Fh+var_98]
0x180001ef9  test    rcx, rcx
0x180001efc  jz      loc_180001C60
0x180001f02  cmp     eax, 80090318h
0x180001f07  jnz     short loc_180001F2C
0x180001f09  test    rsi, rsi
0x180001f0c  jnz     short loc_180001F13
0x180001f0e  lea     ebx, [rax+45h]
0x180001f11  jmp     short loc_180001F2C
0x180001f13  mov     rax, [r14+8]
0x180001f17  mov     ebx, 90312h
0x180001f1c  mov     [rsi+8], rax
0x180001f20  mov     eax, [r14]
0x180001f23  mov     [rsi], eax
0x180001f25  mov     dword ptr [rsi+4], 5
0x180001f2c  mov     eax, dword ptr [rsp+130h+var_D8]
0x180001f30  mov     [r14], eax
0x180001f33  mov     [r14+8], rcx
0x180001f37  jmp     loc_180001C60
0x180001f3c  test    byte ptr [rdi+20h], 2
0x180001f40  jnz     short loc_180001F99
0x180001f42  cmp     byte ptr [rsp+130h+var_E0], dl
0x180001f46  jz      short loc_180001F50
0x180001f48  mov     rax, [r13+8]
0x180001f4c  movdqu  xmmword ptr [rax], xmm7
0x180001f50  mov     rcx, [r15+8]
0x180001f54  lea     rax, [rsp+130h+var_D8+8]
0x180001f59  mov     dword ptr [rbp+3Fh+var_90+4], 2
0x180001f60  mov     dword ptr [rbp+3Fh+var_90], edx
0x180001f63  mov     qword ptr [rbp+3Fh+var_90+8], rax
0x180001f67  mov     eax, [rcx+4]
0x180001f6a  mov     dword ptr [rsp+130h+var_D8+0Ch], eax
0x180001f6e  mov     eax, [rcx]
0x180001f70  mov     dword ptr [rsp+130h+var_D8+8], eax
0x180001f74  mov     rax, [rcx+8]
0x180001f78  mov     rcx, [rbp+3Fh+var_B0]
0x180001f7c  mov     qword ptr [rsp+130h+var_C8], rax
0x180001f81  mov     dword ptr [rbp+3Fh+var_C8+0Ch], 80000002h
0x180001f88  mov     eax, [rcx+20h]
0x180001f8b  mov     dword ptr [rsp+130h+var_C8+8], eax
0x180001f8f  mov     rax, [rcx+28h]
0x180001f93  mov     [rbp+3Fh+var_B8], rax
0x180001f97  jmp     short loc_180001FCA
0x180001f99  mov     rcx, [r15+8]
0x180001f9d  lea     rax, [rsp+130h+var_D8+8]
0x180001fa2  mov     dword ptr [rbp+3Fh+var_90+4], 1
0x180001fa9  mov     dword ptr [rbp+3Fh+var_90], edx
0x180001fac  mov     qword ptr [rbp+3Fh+var_90+8], rax
0x180001fb0  mov     eax, [rcx+4]
0x180001fb3  mov     dword ptr [rsp+130h+var_D8+0Ch], eax
0x180001fb7  mov     eax, [rcx]
0x180001fb9  mov     dword ptr [rsp+130h+var_D8+8], eax
0x180001fbd  mov     rax, [rcx+8]
0x180001fc1  mov     qword ptr [rsp+130h+var_C8], rax
0x180001fc6  mov     rcx, [rbp+3Fh+var_B0]
0x180001fca  mov     rax, [r13+8]
0x180001fce  lea     r10, [rdi+10h]
  ... truncated ...
```
