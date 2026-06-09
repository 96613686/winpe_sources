# UlpDigestAuthenticationHandler

- ea: `0x1c004c790`
- end: `0x1c004cb6d`
- name: `UlpDigestAuthenticationHandler`
- size: `989`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1c001a4b0`
- `0x1c001b900`
- `0x1c004adcc`
- `0x1c004af18`
- `0x1c004c790`
- `0x1c009c4d0`
- `0x1c009c570`
- `0x1c00a2b80`
- `0x1c0120858`
- `0x1c013a4dc`
- `0x1c013a818`
- `0x1c013ac74`
- `0x1c013b094`
- `0x1c013c5a8`

## import_xrefs

- `ntoskrnl!RtlMapSecurityErrorToNtStatus` at `0x1c004ca55`
- `ntoskrnl!RtlMapSecurityErrorToNtStatus` at `0x1c004ca55`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c004cb33`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c004cb33`
- `ksecdd!CompleteAuthToken` at `0x1c004c9dd`
- `ksecdd!CompleteAuthToken` at `0x1c004c9dd`
- `ksecdd!AcceptSecurityContext` at `0x1c004c9b7`
- `ksecdd!AcceptSecurityContext` at `0x1c004c9b7`
- `ksecdd!DeleteSecurityContext` at `0x1c004ca88`
- `ksecdd!DeleteSecurityContext` at `0x1c004ca88`

## pseudocode

```c
void __fastcall UlpDigestAuthenticationHandler(_QWORD *a1)
{
  __int64 Current; // rax
  __int64 *v3; // rsi
  __int64 v4; // r15
  __int64 v5; // rdi
  __int64 v6; // rax
  __int64 v7; // r12
  __int64 v8; // rdx
  int v9; // ecx
  __int64 v10; // rcx
  NTSTATUS v11; // r14d
  int v12; // ebx
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  int v17; // ecx
  signed int v18; // eax
  int phNewContext; // [rsp+30h] [rbp-D8h]
  int pOutput; // [rsp+38h] [rbp-D0h]
  int v21; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int pfContextAttr; // [rsp+5Ch] [rbp-ACh] BYREF
  int pInput; // [rsp+60h] [rbp-A8h] BYREF
  struct _SecBufferDesc pInput_8; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v25; // [rsp+78h] [rbp-90h] BYREF
  __int64 v26; // [rsp+88h] [rbp-80h]
  SECURITY_INTEGER ptsExpiry; // [rsp+90h] [rbp-78h] BYREF
  struct _SecBufferDesc v28; // [rsp+98h] [rbp-70h] BYREF
  __int64 *v29; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v30; // [rsp+B0h] [rbp-58h]
  __int64 v31; // [rsp+B8h] [rbp-50h]
  char v32; // [rsp+C0h] [rbp-48h]
  int v33; // [rsp+C1h] [rbp-47h]
  __int16 v34; // [rsp+C5h] [rbp-43h]
  char v35; // [rsp+C7h] [rbp-41h]
  struct _SecHandle phContext; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v37[12]; // [rsp+D8h] [rbp-30h] BYREF

  pfContextAttr = 0;
  pInput_8 = 0;
  ptsExpiry.QuadPart = 0;
  v28 = 0;
  LOBYTE(v21) = 0;
  v25 = 0;
  Current = UxPodGetCurrent();
  v3 = (__int64 *)a1[7];
  v4 = Current;
  v5 = a1[6];
  v6 = *v3;
  phContext.dwUpper = -1;
  phContext.dwLower = -1;
  v7 = *(v3 - 82);
  v8 = *(_DWORD *)(v3 - 20) & 2;
  v9 = *(_DWORD *)(v3 - 20) & 2;
  v26 = v6;
  v10 = (unsigned int)-v9;
  v11 = (_DWORD)v10 != 0 ? 0xC0000241 : 0;
  if ( (_DWORD)v8 )
  {
    v12 = -2146893053;
  }
  else
  {
    memset(v37, 0, sizeof(v37));
    pInput_8.cBuffers = 6;
    v28.pBuffers = (PSecBuffer)&v25;
    v13 = 2052;
    v28.cBuffers = 1;
    *((_QWORD *)&v25 + 1) = &v21;
    pInput_8.pBuffers = (PSecBuffer)v37;
    HIDWORD(v37[0]) = 2;
    *(_QWORD *)&v25 = 0x200000001LL;
    LODWORD(v37[0]) = *((_DWORD *)v3 + 10);
    v37[1] = v3[4];
    HIDWORD(v37[2]) = 3;
    LODWORD(v37[2]) = *(unsigned __int16 *)(v5 + 128);
    v37[3] = *(_QWORD *)(v5 + 120);
    v37[4] = 0x300000000LL;
    v37[5] = 0;
    v37[6] = 0x300000000LL;
    v37[7] = 0;
    v37[8] = 0x300000000LL;
    memset(&v37[9], 0, 24);
    v14 = *(_DWORD *)(v5 + 136);
    pInput = 2052;
    if ( (v14 & 1) != 0 )
    {
      v15 = UlpAdjustSspChannelBindParameters(v5, &pInput_8, &pInput);
      v11 = v15;
      if ( v15 < 0 )
      {
        v12 = UlMapNtStatusToSecurityStatus((unsigned int)v15);
        goto LABEL_20;
      }
      v13 = pInput;
      if ( *(_BYTE *)(v4 + 1568) )
      {
        v29 = v3 - 42;
        v33 = 0;
        v34 = 0;
        v35 = 0;
        v31 = v4;
        v30 = 0;
        v32 = 0;
        McTemplateK0xqq_UlEtwWriteEventWrapper(v17, v16, (unsigned int)&v29, v7, pInput_8.cBuffers, pInput);
      }
      if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 2) != 0 )
        WPP_SF_iLL(29, v16, v7, pInput_8.cBuffers, v13);
    }
    v18 = AcceptSecurityContext(
            (PCredHandle)(v26 + 40),
            0,
            &pInput_8,
            v13,
            0x10u,
            &phContext,
            &v28,
            &pfContextAttr,
            &ptsExpiry);
    v12 = v18;
    if ( v18 < 0 )
      goto LABEL_19;
    if ( v18 == 590611 )
    {
      v18 = CompleteAuthToken(&phContext, &pInput_8);
      v12 = v18;
      if ( v18 < 0 )
        goto LABEL_19;
    }
    v11 = UlpParseAndValidateDigestUri(v3, v5);
    if ( v11 < 0 )
    {
      v12 = -2146893018;
      goto LABEL_20;
    }
    if ( v3[1] != -1 && v3[2] != -1 )
      UlpCacheDigestContextHandle(v4, v3);
    *(struct _SecHandle *)(v3 + 1) = phContext;
    *((_DWORD *)v3 + 6) = pfContextAttr;
    phContext.dwUpper = -1;
    phContext.dwLower = -1;
    *((_BYTE *)v3 + 28) = 1;
    v18 = UlpCompleteAuthInfo(v4, v3, v5);
    v12 = v18;
    if ( v18 < 0 )
LABEL_19:
      v11 = RtlMapSecurityErrorToNtStatus(v18);
  }
LABEL_20:
  if ( v11 < 0 )
  {
    *(_DWORD *)v5 |= 1u;
    *(_DWORD *)(v5 + 16) = 2;
    *(_DWORD *)(v5 + 20) = v12;
    if ( phContext.dwLower != -1 && phContext.dwUpper != -1 )
      DeleteSecurityContext(&phContext);
  }
  if ( *(_BYTE *)(v4 + 1568) )
  {
    v33 = 0;
    v29 = v3 - 42;
    pOutput = *(_DWORD *)(v5 + 16);
    phNewContext = *(_DWORD *)(v5 + 20);
    v34 = 0;
    v35 = 0;
    v31 = v4;
    v30 = 0;
    v32 = 0;
    McTemplateK0xsqqq_UlEtwWriteEventWrapper(
      v10,
      v8,
      (unsigned int)&v29,
      v7,
      (__int64)"Digest Authenticator",
      phNewContext,
      pOutput,
      pfContextAttr);
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 2) != 0 )
    WPP_SF_ilLl(v10, v8, v7, *(unsigned int *)(v5 + 20), *(_DWORD *)(v5 + 16), pfContextAttr);
  UlpAuthenticationComplete(v4, (_DWORD)v3, v11, a1[8], a1[9]);
  ExFreePoolWithTag(a1 - 2, 0);
}

```

## disassembly

```asm
0x1c004c790  mov     rax, rsp
0x1c004c793  mov     [rax+10h], rbx
0x1c004c797  mov     [rax+18h], rsi
0x1c004c79b  mov     [rax+20h], rdi
0x1c004c79f  push    rbp
0x1c004c7a0  push    r12
0x1c004c7a2  push    r13
0x1c004c7a4  push    r14
0x1c004c7a6  push    r15
0x1c004c7a8  lea     rbp, [rax-68h]
0x1c004c7ac  sub     rsp, 140h
0x1c004c7b3  mov     rax, cs:__security_cookie
0x1c004c7ba  xor     rax, rsp
0x1c004c7bd  mov     [rbp+60h+var_30], rax
0x1c004c7c1  xor     eax, eax
0x1c004c7c3  xorps   xmm0, xmm0
0x1c004c7c6  xorps   xmm1, xmm1
0x1c004c7c9  mov     [rsp+160h+var_10C], eax
0x1c004c7cd  movups  xmmword ptr [rsp+160h+pInput.pBuffers], xmm0
0x1c004c7d2  mov     qword ptr [rbp+60h+var_D8], rax
0x1c004c7d6  mov     r13, rcx
0x1c004c7d9  movups  xmmword ptr [rbp+60h+var_D0.ulVersion], xmm1
0x1c004c7dd  mov     byte ptr [rsp+160h+var_110], al
0x1c004c7e1  movups  [rsp+160h+var_F8+8], xmm0
0x1c004c7e6  call    UxPodGetCurrent
0x1c004c7eb  mov     rsi, [r13+38h]
0x1c004c7ef  mov     r15, rax
0x1c004c7f2  mov     rdi, [r13+30h]
0x1c004c7f6  mov     rax, [rsi]
0x1c004c7f9  or      [rbp+60h+phContext.dwUpper], 0FFFFFFFFFFFFFFFFh
0x1c004c7fe  or      [rbp+60h+phContext.dwLower], 0FFFFFFFFFFFFFFFFh
0x1c004c803  mov     edx, [rsi-0A0h]
0x1c004c809  mov     r12, [rsi-290h]
0x1c004c810  and     edx, 2
0x1c004c813  mov     ecx, edx
0x1c004c815  mov     [rbp+60h+var_E0], rax
0x1c004c819  neg     ecx
0x1c004c81b  sbb     r14d, r14d
0x1c004c81e  and     r14d, 0C0000241h
0x1c004c825  test    edx, edx
0x1c004c827  jz      short loc_1C004C833
0x1c004c829  mov     ebx, 80090303h
0x1c004c82e  jmp     loc_1C004CA64
0x1c004c833  xor     edx, edx; Val
0x1c004c835  lea     rcx, [rbp+60h+var_90]; void *
0x1c004c839  lea     r8d, [rdx+60h]; Size
0x1c004c83d  call    memset
0x1c004c842  xor     r14d, r14d
0x1c004c845  mov     dword ptr [rsp+160h+pInput.pBuffers+4], 6
0x1c004c84d  mov     edx, 1
0x1c004c852  lea     rax, [rsp+160h+var_F8+8]
0x1c004c857  mov     [rbp+60h+var_D0.pBuffers], rax
0x1c004c85b  mov     ebx, 804h
0x1c004c860  mov     [rbp+60h+var_D0.cBuffers], edx
0x1c004c863  lea     rax, [rsp+160h+var_110]
0x1c004c868  mov     [rsp+160h+var_E8], rax
0x1c004c86d  lea     rax, [rbp+60h+var_90]
0x1c004c871  mov     qword ptr [rsp+160h+var_F8], rax
0x1c004c876  lea     ecx, [rdx+1]
0x1c004c879  mov     dword ptr [rsp+160h+var_F8+0Ch], ecx
0x1c004c87d  mov     [rbp+60h+var_8C], ecx
0x1c004c880  lea     ecx, [rdx+2]
0x1c004c883  mov     dword ptr [rsp+160h+var_F8+8], edx
0x1c004c887  mov     eax, [rsi+28h]
0x1c004c88a  mov     [rbp+60h+var_90], eax
0x1c004c88d  mov     rax, [rsi+20h]
0x1c004c891  mov     [rbp+60h+var_88], rax
0x1c004c895  mov     [rbp+60h+var_7C], ecx
0x1c004c898  movzx   eax, word ptr [rdi+80h]
0x1c004c89f  mov     [rbp+60h+var_80], eax
0x1c004c8a2  mov     rax, [rdi+78h]
0x1c004c8a6  mov     [rbp+60h+var_78], rax
0x1c004c8aa  mov     [rbp+60h+var_6C], ecx
0x1c004c8ad  mov     [rbp+60h+var_70], r14d
0x1c004c8b1  mov     [rbp+60h+var_68], r14
0x1c004c8b5  mov     [rbp+60h+var_5C], ecx
0x1c004c8b8  mov     [rbp+60h+var_60], r14d
0x1c004c8bc  mov     [rbp+60h+var_58], r14
0x1c004c8c0  mov     [rbp+60h+var_4C], ecx
0x1c004c8c3  mov     [rbp+60h+var_50], r14d
0x1c004c8c7  mov     [rbp+60h+var_48], r14
0x1c004c8cb  mov     [rbp+60h+var_40], r14
0x1c004c8cf  mov     [rbp+60h+var_38], r14
0x1c004c8d3  mov     eax, [rdi+88h]
0x1c004c8d9  mov     [rsp+160h+pInput.ulVersion], ebx
0x1c004c8dd  test    dl, al
0x1c004c8df  jz      loc_1C004C978
0x1c004c8e5  lea     r8, [rsp+160h+pInput]
0x1c004c8ea  mov     rcx, rdi
0x1c004c8ed  lea     rdx, [rsp+160h+pInput.pBuffers]
0x1c004c8f2  call    UlpAdjustSspChannelBindParameters
0x1c004c8f7  mov     r14d, eax
0x1c004c8fa  test    eax, eax
0x1c004c8fc  jns     short loc_1C004C90C
0x1c004c8fe  mov     ecx, eax
0x1c004c900  call    UlMapNtStatusToSecurityStatus
0x1c004c905  mov     ebx, eax
0x1c004c907  jmp     loc_1C004CA64
0x1c004c90c  mov     ebx, [rsp+160h+pInput.ulVersion]
0x1c004c910  xor     r14d, r14d
0x1c004c913  cmp     [r15+620h], r14b
0x1c004c91a  jz      short loc_1C004C958
0x1c004c91c  lea     rax, [rsi-150h]
0x1c004c923  mov     dword ptr [rsp+160h+phNewContext], ebx
0x1c004c927  mov     [rbp+60h+var_C0], rax
0x1c004c92b  lea     r8, [rbp+60h+var_C0]
0x1c004c92f  mov     eax, dword ptr [rsp+160h+pInput.pBuffers+4]
0x1c004c933  mov     r9, r12
0x1c004c936  mov     [rsp+160h+TargetDataRep], eax
0x1c004c93a  mov     [rbp+60h+var_A7], r14d
0x1c004c93e  mov     [rbp+60h+var_A3], r14w
0x1c004c943  mov     [rbp+60h+var_A1], r14b
0x1c004c947  mov     [rbp+60h+var_B0], r15
0x1c004c94b  mov     [rbp+60h+var_B8], r14
0x1c004c94f  mov     [rbp+60h+var_A8], r14b
0x1c004c953  call    McTemplateK0xqq_UlEtwWriteEventWrapper
0x1c004c958  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c004c95e  test    al, 2
0x1c004c960  jz      short loc_1C004C978
0x1c004c962  mov     r9d, dword ptr [rsp+160h+pInput.pBuffers+4]
0x1c004c967  mov     ecx, 1Dh
0x1c004c96c  mov     r8, r12
0x1c004c96f  mov     [rsp+160h+TargetDataRep], ebx
0x1c004c973  call    WPP_SF_iLL
0x1c004c978  mov     rcx, [rbp+60h+var_E0]
0x1c004c97c  lea     rax, [rbp+60h+var_D8]
0x1c004c980  mov     [rsp+160h+ptsExpiry], rax; ptsExpiry
0x1c004c985  lea     r8, [rsp+160h+pInput.pBuffers]; pInput
0x1c004c98a  lea     rax, [rsp+160h+var_10C]
0x1c004c98f  add     rcx, 28h ; '('; phCredential
0x1c004c993  mov     [rsp+160h+pfContextAttr], rax; pfContextAttr
0x1c004c998  mov     r9d, ebx; fContextReq
0x1c004c99b  lea     rax, [rbp+60h+var_D0]
0x1c004c99f  xor     edx, edx; phContext
0x1c004c9a1  mov     [rsp+160h+pOutput], rax; pOutput
0x1c004c9a6  lea     rax, [rbp+60h+phContext]
0x1c004c9aa  mov     [rsp+160h+phNewContext], rax; phNewContext
0x1c004c9af  mov     [rsp+160h+TargetDataRep], 10h; TargetDataRep
0x1c004c9b7  call    cs:__imp_AcceptSecurityContext
0x1c004c9be  nop     dword ptr [rax+rax+00h]
0x1c004c9c3  mov     ebx, eax
0x1c004c9c5  test    eax, eax
0x1c004c9c7  js      loc_1C004CA53
0x1c004c9cd  cmp     eax, 90313h
0x1c004c9d2  jnz     short loc_1C004C9EF
0x1c004c9d4  lea     rdx, [rsp+160h+pInput.pBuffers]; pToken
0x1c004c9d9  lea     rcx, [rbp+60h+phContext]; phContext
0x1c004c9dd  call    cs:__imp_CompleteAuthToken
0x1c004c9e4  nop     dword ptr [rax+rax+00h]
0x1c004c9e9  mov     ebx, eax
0x1c004c9eb  test    eax, eax
0x1c004c9ed  js      short loc_1C004CA53
0x1c004c9ef  mov     rdx, rdi
0x1c004c9f2  mov     rcx, rsi
0x1c004c9f5  call    UlpParseAndValidateDigestUri
0x1c004c9fa  mov     r14d, eax
0x1c004c9fd  test    eax, eax
0x1c004c9ff  jns     short loc_1C004CA08
0x1c004ca01  mov     ebx, 80090326h
0x1c004ca06  jmp     short loc_1C004CA64
0x1c004ca08  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1c004ca0c  cmp     [rsi+8], rbx
0x1c004ca10  jz      short loc_1C004CA23
0x1c004ca12  cmp     [rsi+10h], rbx
0x1c004ca16  jz      short loc_1C004CA23
0x1c004ca18  mov     rdx, rsi
0x1c004ca1b  mov     rcx, r15
0x1c004ca1e  call    UlpCacheDigestContextHandle
0x1c004ca23  movups  xmm0, xmmword ptr [rbp+60h+phContext.dwLower]
0x1c004ca27  mov     r8, rdi
0x1c004ca2a  mov     rdx, rsi
0x1c004ca2d  mov     rcx, r15
0x1c004ca30  movdqu  xmmword ptr [rsi+8], xmm0
0x1c004ca35  mov     eax, [rsp+160h+var_10C]
0x1c004ca39  mov     [rsi+18h], eax
0x1c004ca3c  mov     [rbp+60h+phContext.dwUpper], rbx
0x1c004ca40  mov     [rbp+60h+phContext.dwLower], rbx
0x1c004ca44  mov     byte ptr [rsi+1Ch], 1
0x1c004ca48  call    UlpCompleteAuthInfo
0x1c004ca4d  mov     ebx, eax
0x1c004ca4f  test    eax, eax
0x1c004ca51  jns     short loc_1C004CA64
0x1c004ca53  mov     ecx, eax; SecurityError
0x1c004ca55  call    cs:__imp_RtlMapSecurityErrorToNtStatus
0x1c004ca5c  nop     dword ptr [rax+rax+00h]
0x1c004ca61  mov     r14d, eax
0x1c004ca64  test    r14d, r14d
0x1c004ca67  jns     short loc_1C004CA94
0x1c004ca69  or      dword ptr [rdi], 1
0x1c004ca6c  mov     dword ptr [rdi+10h], 2
0x1c004ca73  mov     [rdi+14h], ebx
0x1c004ca76  cmp     [rbp+60h+phContext.dwLower], 0FFFFFFFFFFFFFFFFh
0x1c004ca7b  jz      short loc_1C004CA94
0x1c004ca7d  cmp     [rbp+60h+phContext.dwUpper], 0FFFFFFFFFFFFFFFFh
0x1c004ca82  jz      short loc_1C004CA94
0x1c004ca84  lea     rcx, [rbp+60h+phContext]; phContext
0x1c004ca88  call    cs:__imp_DeleteSecurityContext
0x1c004ca8f  nop     dword ptr [rax+rax+00h]
0x1c004ca94  xor     ebx, ebx
0x1c004ca96  cmp     [r15+620h], bl
0x1c004ca9d  jz      short loc_1C004CAED
0x1c004ca9f  lea     rax, [rsi-150h]
0x1c004caa6  mov     [rbp+60h+var_A7], ebx
0x1c004caa9  mov     [rbp+60h+var_C0], rax
0x1c004caad  lea     r8, [rbp+60h+var_C0]
0x1c004cab1  mov     eax, [rsp+160h+var_10C]
0x1c004cab5  mov     r9, r12
0x1c004cab8  mov     dword ptr [rsp+160h+pfContextAttr], eax
0x1c004cabc  mov     eax, [rdi+10h]
0x1c004cabf  mov     dword ptr [rsp+160h+pOutput], eax
0x1c004cac3  mov     eax, [rdi+14h]
0x1c004cac6  mov     dword ptr [rsp+160h+phNewContext], eax
0x1c004caca  lea     rax, aDigestAuthenti; "Digest Authenticator"
0x1c004cad1  mov     qword ptr [rsp+160h+TargetDataRep], rax
0x1c004cad6  mov     [rbp+60h+var_A3], bx
0x1c004cada  mov     [rbp+60h+var_A1], bl
0x1c004cadd  mov     [rbp+60h+var_B0], r15
0x1c004cae1  mov     [rbp+60h+var_B8], rbx
0x1c004cae5  mov     [rbp+60h+var_A8], bl
0x1c004cae8  call    McTemplateK0xsqqq_UlEtwWriteEventWrapper
0x1c004caed  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c004caf3  test    al, 2
0x1c004caf5  jz      short loc_1C004CB12
0x1c004caf7  mov     eax, [rsp+160h+var_10C]
0x1c004cafb  mov     r8, r12
0x1c004cafe  mov     r9d, [rdi+14h]
0x1c004cb02  mov     dword ptr [rsp+160h+phNewContext], eax
0x1c004cb06  mov     eax, [rdi+10h]
0x1c004cb09  mov     [rsp+160h+TargetDataRep], eax
0x1c004cb0d  call    WPP_SF_ilLl
0x1c004cb12  mov     rax, [r13+48h]
0x1c004cb16  mov     r8d, r14d
0x1c004cb19  mov     r9, [r13+40h]
0x1c004cb1d  mov     rdx, rsi
0x1c004cb20  mov     rcx, r15
0x1c004cb23  mov     qword ptr [rsp+160h+TargetDataRep], rax
0x1c004cb28  call    UlpAuthenticationComplete
0x1c004cb2d  xor     edx, edx; Tag
0x1c004cb2f  lea     rcx, [r13-10h]; P
0x1c004cb33  call    cs:__imp_ExFreePoolWithTag
0x1c004cb3a  nop     dword ptr [rax+rax+00h]
0x1c004cb3f  mov     rcx, [rbp+60h+var_30]
0x1c004cb43  xor     rcx, rsp; StackCookie
0x1c004cb46  call    __security_check_cookie
0x1c004cb4b  lea     r11, [rsp+160h+var_20]
0x1c004cb53  mov     rbx, [r11+38h]
0x1c004cb57  mov     rsi, [r11+40h]
0x1c004cb5b  mov     rdi, [r11+48h]
0x1c004cb5f  mov     rsp, r11
0x1c004cb62  pop     r15
0x1c004cb64  pop     r14
0x1c004cb66  pop     r13
0x1c004cb68  pop     r12
0x1c004cb6a  pop     rbp
0x1c004cb6b  retn
```
