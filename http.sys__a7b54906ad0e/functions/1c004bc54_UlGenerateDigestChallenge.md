# UlGenerateDigestChallenge

- ea: `0x1c004bc54`
- end: `0x1c004bf66`
- name: `UlGenerateDigestChallenge`
- size: `786`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1c004aff4`

## callees

- `0x1c001a4b0`
- `0x1c004af18`
- `0x1c004bc54`
- `0x1c009c524`
- `0x1c013a5d0`
- `0x1c013ac74`
- `0x1c013b7cc`

## import_xrefs

- `ntoskrnl!RtlMapSecurityErrorToNtStatus` at `0x1c004bf0e`
- `ntoskrnl!RtlMapSecurityErrorToNtStatus` at `0x1c004bf0e`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c004bed8`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c004bed8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c004beb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c004beff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c004beb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c004beff`
- `ksecdd!AcceptSecurityContext` at `0x1c004be7f`
- `ksecdd!AcceptSecurityContext` at `0x1c004be7f`

## pseudocode

```c
__int64 __fastcall UlGenerateDigestChallenge(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        int a8,
        _QWORD *a9,
        _WORD *a10)
{
  __int64 v10; // r13
  SIZE_T v15; // rsi
  _OWORD *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned int v20; // r14d
  __int64 v21; // rbx
  __int64 result; // rax
  SECURITY_STATUS v23; // eax
  ULONG v24; // r14d
  unsigned int v25; // ecx
  PVOID PoolWithTagPriority; // rax
  void *v27; // rbx
  struct _SecHandle v28; // xmm0
  unsigned int pfContextAttr; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int fContextReq; // [rsp+54h] [rbp-ACh] BYREF
  __int128 v31; // [rsp+58h] [rbp-A8h] BYREF
  _WORD *v32; // [rsp+68h] [rbp-98h]
  struct _SecBufferDesc pInput; // [rsp+70h] [rbp-90h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v35; // [rsp+88h] [rbp-78h]
  struct _SecBufferDesc pOutput; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v37[3]; // [rsp+A0h] [rbp-60h] BYREF
  char v38; // [rsp+B8h] [rbp-48h]
  int v39; // [rsp+B9h] [rbp-47h]
  __int16 v40; // [rsp+BDh] [rbp-43h]
  char v41; // [rsp+BFh] [rbp-41h]
  struct _SecHandle phNewContext; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v43[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v44; // [rsp+D8h] [rbp-28h]
  int v45; // [rsp+E0h] [rbp-20h]
  int v46; // [rsp+E4h] [rbp-1Ch]
  __int64 v47; // [rsp+E8h] [rbp-18h]
  _OWORD v48[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v49; // [rsp+110h] [rbp+10h]
  int v50; // [rsp+114h] [rbp+14h]
  __int64 v51; // [rsp+118h] [rbp+18h]
  __int64 v52; // [rsp+120h] [rbp+20h]
  __int64 v53; // [rsp+128h] [rbp+28h]

  v10 = a1 + 384;
  v32 = a10;
  v35 = a9;
  pfContextAttr = 0;
  ptsExpiry.QuadPart = 0;
  v15 = 512;
  UlpDereferenceCredentials(a2);
  *(_QWORD *)a2 = v10;
  v48[0] = 0;
  pOutput.cBuffers = 1;
  *a10 = 0;
  phNewContext.dwUpper = -1;
  phNewContext.dwLower = -1;
  pOutput.pBuffers = (PSecBuffer)&v31;
  *a9 = 0;
  pInput.pBuffers = (PSecBuffer)v43;
  v45 = (unsigned __int16)a5;
  v16 = v48;
  v17 = 2;
  pOutput.ulVersion = 0;
  pInput.ulVersion = 0;
  v48[1] = 0;
  pInput.cBuffers = 6;
  v31 = 0;
  v43[1] = 2;
  v43[0] = 0;
  v44 = 0;
  v46 = 3;
  v47 = a4;
  do
  {
    *((_DWORD *)v16 + 1) = 3;
    *(_DWORD *)v16 = 0;
    *((_QWORD *)v16++ + 1) = 0;
    --v17;
  }
  while ( v17 );
  v49 = *(unsigned __int16 *)(a3 + 16);
  v51 = *(_QWORD *)(a3 + 24);
  v50 = 3;
  v52 = 0;
  v53 = 0;
  fContextReq = 0;
  v20 = UlpAdjustSspChannelBindParamsForDigestChallenge(a1, a2, a3, (unsigned int)&pInput, (__int64)&fContextReq);
  if ( v20 )
  {
LABEL_4:
    v21 = *(_QWORD *)(a2 - 656);
    if ( *(_BYTE *)(a1 + 1568) )
    {
      v39 = 0;
      v37[0] = a2 - 336;
      v40 = 0;
      v41 = 0;
      v37[2] = a1;
      v37[1] = 0;
      v38 = 0;
      McTemplateK0xsqqq_UlEtwWriteEventWrapper(
        v19,
        v18,
        (unsigned int)v37,
        v21,
        (__int64)"Digest Initial Authenticator",
        0,
        0,
        pfContextAttr);
    }
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 2) != 0 )
      WPP_SF_il(v19, v18, v21, pfContextAttr);
    return v20;
  }
  else
  {
    while ( 1 )
    {
      *(_QWORD *)&v31 = (unsigned int)v15 | 0x200000000LL;
      PoolWithTagPriority = ExAllocatePoolWithTagPriority(PagedPool, v15, 0x43586C55u, LowPoolPriority);
      v27 = PoolWithTagPriority;
      if ( !PoolWithTagPriority )
        return 3221225626LL;
      *((_QWORD *)&v31 + 1) = PoolWithTagPriority;
      v23 = AcceptSecurityContext(
              (PCredHandle)(v10 + 40),
              0,
              &pInput,
              fContextReq,
              0x10u,
              &phNewContext,
              &pOutput,
              &pfContextAttr,
              &ptsExpiry);
      v24 = v23;
      if ( v23 == 590610 )
        break;
      if ( v23 != -2146893056 || (v25 = 2 * v15, v15 = (unsigned int)(2 * v15), v25 > *(_DWORD *)(v10 + 112)) )
      {
        ExFreePoolWithTag(v27, 0);
        v20 = RtlMapSecurityErrorToNtStatus(v24);
        goto LABEL_4;
      }
      ExFreePoolWithTag(v27, 0);
    }
    *v32 = v31;
    *v35 = v27;
    if ( *(_QWORD *)(a2 + 8) != -1 && *(_QWORD *)(a2 + 16) != -1 )
      UlpCacheDigestContextHandle(a1, a2);
    v28 = phNewContext;
    *(_DWORD *)(a2 + 24) = pfContextAttr;
    result = 0;
    *(struct _SecHandle *)(a2 + 8) = v28;
  }
  return result;
}

```

## disassembly

```asm
0x1c004bc54  mov     [rsp-8+arg_18], rbx
0x1c004bc59  push    rbp
0x1c004bc5a  push    rsi
0x1c004bc5b  push    rdi
0x1c004bc5c  push    r12
0x1c004bc5e  push    r13
0x1c004bc60  push    r14
0x1c004bc62  push    r15
0x1c004bc64  lea     rbp, [rsp-40h]
0x1c004bc69  sub     rsp, 140h
0x1c004bc70  mov     rax, cs:__security_cookie
0x1c004bc77  xor     rax, rsp
0x1c004bc7a  mov     [rbp+70h+var_40], rax
0x1c004bc7e  mov     rax, [rbp+70h+arg_48]
0x1c004bc85  lea     r13, [rcx+180h]
0x1c004bc8c  mov     r12, [rbp+70h+arg_40]
0x1c004bc93  mov     r15, rcx
0x1c004bc96  mov     [rsp+170h+var_108], rax
0x1c004bc9b  mov     rcx, rdx
0x1c004bc9e  xor     eax, eax
0x1c004bca0  mov     [rbp+70h+var_E8], r12
0x1c004bca4  mov     [rsp+170h+var_120], eax
0x1c004bca8  mov     rbx, r9
0x1c004bcab  mov     qword ptr [rbp+70h+var_F0], rax
0x1c004bcaf  mov     r14, r8
0x1c004bcb2  mov     rdi, rdx
0x1c004bcb5  mov     esi, 200h
0x1c004bcba  call    UlpDereferenceCredentials
0x1c004bcbf  mov     rax, [rsp+170h+var_108]
0x1c004bcc4  xor     ecx, ecx
0x1c004bcc6  xorps   xmm0, xmm0
0x1c004bcc9  mov     [rdi], r13
0x1c004bccc  movups  [rbp+70h+var_80], xmm0
0x1c004bcd0  mov     [rbp+70h+var_E0.cBuffers], 1
0x1c004bcd7  mov     [rax], cx
0x1c004bcda  or      rax, 0FFFFFFFFFFFFFFFFh
0x1c004bcde  mov     [rbp+70h+var_B0.dwUpper], rax
0x1c004bce2  mov     [rbp+70h+var_B0.dwLower], rax
0x1c004bce6  lea     rax, [rsp+170h+var_118]
0x1c004bceb  mov     [rbp+70h+var_E0.pBuffers], rax
0x1c004bcef  lea     rax, [rbp+70h+var_A0]
0x1c004bcf3  mov     [r12], rcx
0x1c004bcf7  xor     r12d, r12d
0x1c004bcfa  mov     [rsp+170h+pInput.pBuffers], rax
0x1c004bcff  movzx   eax, word ptr [rbp+70h+arg_20]
0x1c004bd06  mov     [rbp+70h+var_90], eax
0x1c004bd09  lea     rax, [rbp+70h+var_80]
0x1c004bd0d  lea     ecx, [r12+2]
0x1c004bd12  mov     [rbp+70h+var_E0.ulVersion], r12d
0x1c004bd16  lea     edx, [rcx+1]
0x1c004bd19  mov     [rsp+170h+pInput.ulVersion], r12d
0x1c004bd1e  movups  [rbp+70h+var_70], xmm0
0x1c004bd22  mov     [rsp+170h+pInput.cBuffers], 6
0x1c004bd2a  movups  [rsp+170h+var_118], xmm0
0x1c004bd2f  mov     [rbp+70h+var_9C], ecx
0x1c004bd32  mov     [rbp+70h+var_A0], r12d
0x1c004bd36  mov     [rbp+70h+var_98], r12
0x1c004bd3a  mov     [rbp+70h+var_8C], edx
0x1c004bd3d  mov     [rbp+70h+var_88], rbx
0x1c004bd41  mov     [rax+4], edx
0x1c004bd44  mov     [rax], r12d
0x1c004bd47  mov     [rax+8], r12
0x1c004bd4b  lea     rax, [rax+10h]
0x1c004bd4f  sub     rcx, 1
0x1c004bd53  jnz     short loc_1C004BD41
0x1c004bd55  movzx   eax, word ptr [r14+10h]
0x1c004bd5a  lea     r9, [rsp+170h+pInput]
0x1c004bd5f  mov     [rbp+70h+var_60], eax
0x1c004bd62  mov     r8, r14
0x1c004bd65  mov     rax, [r14+18h]
0x1c004bd69  mov     rcx, r15
0x1c004bd6c  mov     [rbp+70h+var_58], rax
0x1c004bd70  lea     rax, [rsp+170h+fContextReq]
0x1c004bd75  mov     [rbp+70h+var_5C], edx
0x1c004bd78  mov     rdx, rdi
0x1c004bd7b  mov     qword ptr [rsp+170h+TargetDataRep], rax
0x1c004bd80  mov     [rbp+70h+var_50], r12
0x1c004bd84  mov     [rbp+70h+var_48], r12
0x1c004bd88  mov     [rsp+170h+fContextReq], r12d
0x1c004bd8d  call    UlpAdjustSspChannelBindParamsForDigestChallenge
0x1c004bd92  mov     r14d, eax
0x1c004bd95  test    eax, eax
0x1c004bd97  jz      loc_1C004BEBC
0x1c004bd9d  mov     rbx, [rdi-290h]
0x1c004bda4  cmp     [r15+620h], r12b
0x1c004bdab  jz      short loc_1C004BDFB
0x1c004bdad  lea     rax, [rdi-150h]
0x1c004bdb4  mov     [rbp+70h+var_B7], r12d
0x1c004bdb8  mov     [rbp+70h+var_D0], rax
0x1c004bdbc  lea     r8, [rbp+70h+var_D0]
0x1c004bdc0  mov     eax, [rsp+170h+var_120]
0x1c004bdc4  mov     r9, rbx
0x1c004bdc7  mov     dword ptr [rsp+170h+pfContextAttr], eax
0x1c004bdcb  lea     rax, aDigestInitialA; "Digest Initial Authenticator"
0x1c004bdd2  mov     dword ptr [rsp+170h+pOutput], r12d
0x1c004bdd7  mov     dword ptr [rsp+170h+phNewContext], r12d
0x1c004bddc  mov     qword ptr [rsp+170h+TargetDataRep], rax
0x1c004bde1  mov     [rbp+70h+var_B3], r12w
0x1c004bde6  mov     [rbp+70h+var_B1], r12b
0x1c004bdea  mov     [rbp+70h+var_C0], r15
0x1c004bdee  mov     [rbp+70h+var_C8], r12
0x1c004bdf2  mov     [rbp+70h+var_B8], r12b
0x1c004bdf6  call    McTemplateK0xsqqq_UlEtwWriteEventWrapper
0x1c004bdfb  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c004be01  test    al, 2
0x1c004be03  jz      short loc_1C004BE12
0x1c004be05  mov     r9d, [rsp+170h+var_120]
0x1c004be0a  mov     r8, rbx
0x1c004be0d  call    WPP_SF_il
0x1c004be12  mov     eax, r14d
0x1c004be15  mov     rcx, [rbp+70h+var_40]
0x1c004be19  xor     rcx, rsp; StackCookie
0x1c004be1c  call    __security_check_cookie
0x1c004be21  mov     rbx, [rsp+170h+arg_18]
0x1c004be29  add     rsp, 140h
0x1c004be30  pop     r15
0x1c004be32  pop     r14
0x1c004be34  pop     r13
0x1c004be36  pop     r12
0x1c004be38  pop     rdi
0x1c004be39  pop     rsi
0x1c004be3a  pop     rbp
0x1c004be3b  retn
0x1c004be3d  mov     r9d, [rsp+170h+fContextReq]; fContextReq
0x1c004be42  lea     rax, [rbp+70h+var_F0]
0x1c004be46  mov     [rsp+170h+ptsExpiry], rax; ptsExpiry
0x1c004be4b  lea     r8, [rsp+170h+pInput]; pInput
0x1c004be50  lea     rax, [rsp+170h+var_120]
0x1c004be55  mov     qword ptr [rsp+170h+var_118+8], rbx
0x1c004be5a  mov     [rsp+170h+pfContextAttr], rax; pfContextAttr
0x1c004be5f  lea     rcx, [r13+28h]; phCredential
0x1c004be63  lea     rax, [rbp+70h+var_E0]
0x1c004be67  xor     edx, edx; phContext
0x1c004be69  mov     [rsp+170h+pOutput], rax; pOutput
0x1c004be6e  lea     rax, [rbp+70h+var_B0]
0x1c004be72  mov     [rsp+170h+phNewContext], rax; phNewContext
0x1c004be77  mov     [rsp+170h+TargetDataRep], 10h; TargetDataRep
0x1c004be7f  call    cs:__imp_AcceptSecurityContext
0x1c004be86  nop     dword ptr [rax+rax+00h]
0x1c004be8b  mov     r14d, eax
0x1c004be8e  cmp     eax, 90312h
0x1c004be93  jz      loc_1C004BF22
0x1c004be99  cmp     eax, 80090300h
0x1c004be9e  jnz     short loc_1C004BEFA
0x1c004bea0  lea     ecx, [rsi+rsi]
0x1c004bea3  mov     esi, ecx
0x1c004bea5  cmp     ecx, [r13+70h]
0x1c004bea9  ja      short loc_1C004BEFA
0x1c004beab  xor     edx, edx; Tag
0x1c004bead  mov     rcx, rbx; P
0x1c004beb0  call    cs:__imp_ExFreePoolWithTag
0x1c004beb7  nop     dword ptr [rax+rax+00h]
0x1c004bebc  xor     r9d, r9d; Priority
0x1c004bebf  mov     dword ptr [rsp+170h+var_118+4], 2
0x1c004bec7  mov     r8d, 43586C55h; Tag
0x1c004becd  mov     dword ptr [rsp+170h+var_118], esi
0x1c004bed1  mov     rdx, rsi; NumberOfBytes
0x1c004bed4  lea     ecx, [r9+1]; PoolType
0x1c004bed8  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c004bedf  nop     dword ptr [rax+rax+00h]
0x1c004bee4  mov     rbx, rax
0x1c004bee7  test    rax, rax
0x1c004beea  jnz     loc_1C004BE3D
0x1c004bef0  mov     eax, 0C000009Ah
0x1c004bef5  jmp     loc_1C004BE15
0x1c004befa  xor     edx, edx; Tag
0x1c004befc  mov     rcx, rbx; P
0x1c004beff  call    cs:__imp_ExFreePoolWithTag
0x1c004bf06  nop     dword ptr [rax+rax+00h]
0x1c004bf0b  mov     ecx, r14d; SecurityError
0x1c004bf0e  call    cs:__imp_RtlMapSecurityErrorToNtStatus
0x1c004bf15  nop     dword ptr [rax+rax+00h]
0x1c004bf1a  mov     r14d, eax
0x1c004bf1d  jmp     loc_1C004BD9D
0x1c004bf22  movzx   eax, word ptr [rsp+170h+var_118]
0x1c004bf27  mov     rcx, [rsp+170h+var_108]
0x1c004bf2c  mov     [rcx], ax
0x1c004bf2f  mov     rax, [rbp+70h+var_E8]
0x1c004bf33  mov     [rax], rbx
0x1c004bf36  cmp     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x1c004bf3b  jz      short loc_1C004BF4F
0x1c004bf3d  cmp     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x1c004bf42  jz      short loc_1C004BF4F
0x1c004bf44  mov     rdx, rdi
0x1c004bf47  mov     rcx, r15
0x1c004bf4a  call    UlpCacheDigestContextHandle
0x1c004bf4f  mov     eax, [rsp+170h+var_120]
0x1c004bf53  movups  xmm0, xmmword ptr [rbp+70h+var_B0.dwLower]
0x1c004bf57  mov     [rdi+18h], eax
0x1c004bf5a  xor     eax, eax
0x1c004bf5c  movdqu  xmmword ptr [rdi+8], xmm0
0x1c004bf61  jmp     loc_1C004BE15
```
