# IkeProcessSspiInitiator

- ea: `0x180082cd0`
- end: `0x180083292`
- name: `IkeProcessSspiInitiator`
- size: `1474`
- prototype: `__int64 __fastcall(__int64, struct _SecBuffer *, unsigned int *, _DWORD *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800825a4`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x180008388`
- `0x180025cfc`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005bc40`
- `0x18005bce4`
- `0x18006dec8`
- `0x18007c950`
- `0x18007d46c`
- `0x18007f120`
- `0x180080058`
- `0x180082480`
- `0x180082cd0`
- `0x1800849cc`
- `0x180084c50`
- `0x180117fa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083048`
- `SspiCli!InitializeSecurityContextW` at `0x180082f20`
- `SspiCli!InitializeSecurityContextW` at `0x180082f20`

## string_xrefs

- `0x1800831b1`: `ISC outtoken:`
- `0x180082ec4`: `ISC intoken:`
- `0x180082e5b`: `Received NULL SSPI token`

## pseudocode

```c
__int64 __fastcall IkeProcessSspiInitiator(__int64 a1, struct _SecBuffer *a2, unsigned int *a3, _DWORD *a4)
{
  SIZE_T cbBuffer; // rcx
  __int64 SecBuffer; // rbx
  struct _SecBuffer *v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // r8d
  int v19; // r9d
  unsigned int v20; // r15d
  __int64 v21; // rax
  unsigned int *v22; // rbx
  __int64 v23; // rcx
  unsigned int v24; // edi
  __int64 v25; // rsi
  __int64 TlsPeerAddr; // rbx
  __int64 v27; // rcx
  int TlsMmLuid; // eax
  __int64 v29; // rcx
  __int64 v30; // rax
  int v31; // r8d
  int v32; // r9d
  __int64 v33; // rcx
  _QWORD *v34; // rdi
  __int64 v35; // rdi
  __int64 v36; // rbx
  __int64 v37; // rcx
  int v38; // eax
  __int64 v39; // rdi
  __int64 v40; // rbx
  __int64 v41; // rcx
  int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rax
  int v45; // r8d
  int v46; // r9d
  _DWORD *v47; // rax
  __int64 v48; // rcx
  unsigned int v49; // eax
  __int64 v51; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v52; // [rsp+68h] [rbp-98h]
  __int64 v53; // [rsp+70h] [rbp-90h]
  struct _SecBufferDesc pOutput; // [rsp+78h] [rbp-88h] BYREF
  size_t Size[2]; // [rsp+88h] [rbp-78h] BYREF
  struct _SecBufferDesc pInput; // [rsp+98h] [rbp-68h] BYREF
  unsigned int fContextReq; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v58; // [rsp+ACh] [rbp-54h] BYREF
  __int64 v59; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v60; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v61; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v62[32]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v63; // [rsp+F0h] [rbp-10h]
  __int64 v64; // [rsp+F8h] [rbp-8h]
  _BYTE v65[16]; // [rsp+100h] [rbp+0h] BYREF
  const char *p_fContextReq; // [rsp+110h] [rbp+10h]
  __int64 v67; // [rsp+118h] [rbp+18h]
  unsigned int *v68; // [rsp+120h] [rbp+20h]
  __int64 v69; // [rsp+128h] [rbp+28h]
  __int64 *v70; // [rsp+130h] [rbp+30h]
  __int64 v71; // [rsp+138h] [rbp+38h]

  v53 = a1;
  v52 = a4;
  fContextReq = 0;
  v51 = 0;
  pInput = 0;
  pOutput = 0;
  v60 = 0;
  *(_OWORD *)Size = 0;
  TraceLogHelper("IkeProcessSspiInitiator", 1);
  pInput.ulVersion = 0;
  pInput.cBuffers = 1;
  pOutput.ulVersion = 0;
  pOutput.cBuffers = 1;
  if ( *((_QWORD *)a3 + 12) )
  {
    cbBuffer = a2->cbBuffer;
    pInput.pBuffers = (PSecBuffer)Size;
    pOutput.pBuffers = (PSecBuffer)&v60;
    SecBuffer = IkeAllocateSecBuffer(cbBuffer);
    if ( SecBuffer )
      goto LABEL_53;
    memcpy_0((void *)Size[1], a2->pvBuffer, LODWORD(Size[0]));
    SecBuffer = IkeAllocateSecBuffer(*a3);
    if ( SecBuffer )
      goto LABEL_53;
  }
  else
  {
    v9 = (struct _SecBuffer *)*((_QWORD *)a3 + 13);
    v10 = *a3;
    pInput.pBuffers = a2;
    pOutput.pBuffers = v9;
    v9->cbBuffer = v10;
  }
  SetIscFlags(a1, a3, &fContextReq);
  if ( a2->cbBuffer )
  {
    SecBuffer = IkeImpersonate(a1, a3);
    if ( SecBuffer )
      goto LABEL_53;
    v21 = *((_QWORD *)a3 + 13);
    if ( v21 )
      ++*(_DWORD *)(v21 + 80);
    IkeDumpSspiToken(a2->pvBuffer, "ISC intoken:", a2->cbBuffer);
    v22 = a3 + 10;
    v20 = InitializeSecurityContextW(
            (PCredHandle)(a3 + 2),
            (PCtxtHandle)(a3 + 6),
            *((SEC_WCHAR **)a3 + 8),
            fContextReq,
            0,
            0x10u,
            &pInput,
            0,
            (PCtxtHandle)(a3 + 6),
            &pOutput,
            a3 + 10,
            (PTimeStamp)a3 + 6);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v24 = *v22;
      v25 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v23);
      TlsMmLuid = IkeGetTlsMmLuid(v27);
      WPP_SF_iSDD(
        v25,
        22,
        (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids,
        TlsMmLuid,
        TlsPeerAddr,
        v20,
        v24);
      v22 = a3 + 10;
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v59 = IkeGetTlsMmLuid(v23);
      v63 = &v59;
      v64 = 8;
      v30 = IkeGetTlsPeerAddr(v29);
      tlgCreate1Sz_wchar_t(v65, v30);
      fContextReq = v20;
      p_fContextReq = (const char *)&fContextReq;
      v58 = *v22;
      v68 = &v58;
      v67 = 4;
      v69 = 4;
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)byte_180155B61,
        v31,
        v32,
        6,
        (__int64)v62);
    }
    SecBuffer = IkeRevertImpersonation(a3);
    if ( SecBuffer )
      goto LABEL_53;
    if ( v20 == 590624 )
    {
      a3[18] |= 0x20u;
      v20 = 590610;
    }
    else if ( v20 && v20 != 590610 )
    {
      goto LABEL_28;
    }
LABEL_41:
    IkeDumpSspiToken(pOutput.pBuffers->pvBuffer, "ISC outtoken:", pOutput.pBuffers->cbBuffer);
    if ( !v20 )
    {
      v48 = *((_QWORD *)a3 + 13);
      if ( !v48 || (v49 = a3[18], (v49 & 8) != 0) )
      {
        if ( (a3[10] & 2) != 0
          || v48
          && ((SecBuffer = IkeGetPolicyFromSspi(v53, a3, &v51), (a3[18] & 0x800000) != 0)
           || (*(_BYTE *)(v51 + 48) & 8) != 0) )
        {
          *v52 = 1;
        }
      }
      else
      {
        a3[18] = v49 | 4;
      }
    }
    if ( *((_QWORD *)a3 + 12) )
      IkeProcessOakISCResponse(v20, Size, &v60);
    a3[18] |= 1u;
    goto LABEL_53;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v13 = IkeGetTlsPeerAddr(v11);
    v15 = IkeGetTlsMmLuid(v14);
    WPP_SF_iS(v12, 21, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v15, v13);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v59 = IkeGetTlsMmLuid(v11);
    v63 = &v59;
    v64 = 8;
    v17 = IkeGetTlsPeerAddr(v16);
    tlgCreate1Sz_wchar_t(v65, v17);
    v67 = 25;
    p_fContextReq = "Received NULL SSPI token";
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)byte_180155BAD,
      v18,
      v19,
      5,
      (__int64)v62);
  }
  v20 = -2146893048;
LABEL_28:
  fContextReq = GetLastError();
  v34 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v35 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v36 = IkeGetTlsPeerAddr(v33);
      v38 = IkeGetTlsMmLuid(v37);
      WPP_SF_iSL(v35, 23, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v38, v36, fContextReq);
      v34 = WPP_GLOBAL_Control;
    }
    if ( v34 != &WPP_GLOBAL_Control && *((_BYTE *)v34 + 25) >= 2u && (*((_BYTE *)v34 + 28) & 0x10) != 0 )
    {
      v39 = v34[2];
      v40 = IkeGetTlsPeerAddr(v33);
      v42 = IkeGetTlsMmLuid(v41);
      WPP_SF_iSL(v39, 24, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v42, v40, v20);
    }
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v61 = IkeGetTlsMmLuid(v33);
    v63 = &v61;
    v64 = 8;
    v44 = IkeGetTlsPeerAddr(v43);
    tlgCreate1Sz_wchar_t(v65, v44);
    v58 = fContextReq;
    p_fContextReq = "ISC failed";
    v68 = &v58;
    v67 = 11;
    v70 = &v59;
    v69 = 4;
    LODWORD(v59) = v20;
    v71 = 4;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)byte_180155B05,
      v45,
      v46,
      7,
      (__int64)v62);
  }
  SecBuffer = SetSspiError(a3, v20, 1);
  if ( !SecBuffer )
  {
    v47 = (_DWORD *)*((_QWORD *)a3 + 13);
    if ( v47 )
      *v47 = 0;
    goto LABEL_41;
  }
LABEL_53:
  WfpMemFree((LPCVOID *)&Size[1]);
  WfpMemFree((LPCVOID *)&v60 + 1);
  TraceLogHelper("IkeProcessSspiInitiator", 0);
  return IkeReturnError(SecBuffer, "IkeProcessSspiInitiator");
}

```

## disassembly

```asm
0x180082cd0  push    rbp
0x180082cd2  push    rbx
0x180082cd3  push    rsi
0x180082cd4  push    rdi
0x180082cd5  push    r12
0x180082cd7  push    r13
0x180082cd9  push    r14
0x180082cdb  push    r15
0x180082cdd  lea     rbp, [rsp-58h]
0x180082ce2  sub     rsp, 158h
0x180082ce9  mov     rax, cs:__security_cookie
0x180082cf0  xor     rax, rsp
0x180082cf3  mov     [rbp+90h+var_50], rax
0x180082cf7  xor     r15d, r15d
0x180082cfa  mov     [rsp+190h+var_120], rcx
0x180082cff  xorps   xmm0, xmm0
0x180082d02  mov     [rsp+190h+var_128], r9
0x180082d07  xorps   xmm1, xmm1
0x180082d0a  mov     [rbp+90h+fContextReq], r15d
0x180082d0e  mov     rdi, rdx
0x180082d11  mov     [rsp+190h+var_130], r15
0x180082d16  mov     rsi, rcx
0x180082d19  lea     r12d, [r15+1]
0x180082d1d  mov     edx, r12d
0x180082d20  lea     rcx, aIkeprocesssspi; "IkeProcessSspiInitiator"
0x180082d27  mov     r14, r8
0x180082d2a  movups  xmmword ptr [rbp+90h+var_F8.ulVersion], xmm0
0x180082d2e  movups  xmmword ptr [rsp+190h+var_118.ulVersion], xmm1
0x180082d33  movups  [rbp+90h+var_D8], xmm0
0x180082d37  movups  xmmword ptr [rbp+90h+Size], xmm1
0x180082d3b  call    TraceLogHelper
0x180082d40  mov     [rbp+90h+var_F8.ulVersion], r15d
0x180082d44  mov     [rbp+90h+var_F8.cBuffers], r12d
0x180082d48  mov     [rsp+190h+var_118.ulVersion], r15d
0x180082d4d  mov     [rsp+190h+var_118.cBuffers], r12d
0x180082d52  cmp     [r14+60h], r15
0x180082d56  jz      short loc_180082DAA
0x180082d58  mov     ecx, [rdi]; dwBytes
0x180082d5a  lea     rax, [rbp+90h+Size]
0x180082d5e  mov     [rbp+90h+var_F8.pBuffers], rax
0x180082d62  lea     rdx, [rbp+90h+Size]
0x180082d66  lea     rax, [rbp+90h+var_D8]
0x180082d6a  mov     [rbp+90h+var_118.pBuffers], rax
0x180082d6e  call    IkeAllocateSecBuffer
0x180082d73  mov     rbx, rax
0x180082d76  test    rax, rax
0x180082d79  jnz     loc_180083243
0x180082d7f  mov     r8d, dword ptr [rbp+90h+Size]; Size
0x180082d83  mov     rdx, [rdi+8]; Src
0x180082d87  mov     rcx, [rbp+90h+Size+8]; void *
0x180082d8b  call    memcpy_0
0x180082d90  mov     ecx, [r14]; dwBytes
0x180082d93  lea     rdx, [rbp+90h+var_D8]
0x180082d97  call    IkeAllocateSecBuffer
0x180082d9c  mov     rbx, rax
0x180082d9f  test    rax, rax
0x180082da2  jnz     loc_180083243
0x180082da8  jmp     short loc_180082DBB
0x180082daa  mov     rcx, [r14+68h]
0x180082dae  mov     eax, [r14]
0x180082db1  mov     [rbp+90h+var_F8.pBuffers], rdi
0x180082db5  mov     [rbp+90h+var_118.pBuffers], rcx
0x180082db9  mov     [rcx], eax
0x180082dbb  lea     r8, [rbp+90h+fContextReq]
0x180082dbf  mov     rdx, r14
0x180082dc2  mov     rcx, rsi
0x180082dc5  call    SetIscFlags
0x180082dca  cmp     [rdi], r15d
0x180082dcd  jnz     loc_180082E9D
0x180082dd3  mov     rdi, cs:WPP_GLOBAL_Control
0x180082dda  lea     r13, WPP_GLOBAL_Control
0x180082de1  mov     r12d, 4
0x180082de7  cmp     rdi, r13
0x180082dea  jz      short loc_180082E25
0x180082dec  cmp     [rdi+19h], r12b
0x180082df0  jb      short loc_180082E25
0x180082df2  test    byte ptr [rdi+1Ch], 10h
0x180082df6  jz      short loc_180082E25
0x180082df8  mov     rdi, [rdi+10h]
0x180082dfc  call    IkeGetTlsPeerAddr
0x180082e01  mov     rbx, rax
0x180082e04  call    IkeGetTlsMmLuid
0x180082e09  mov     r9, rax
0x180082e0c  mov     qword ptr [rsp+190h+Reserved1], rbx
0x180082e11  lea     edx, [r12+11h]
0x180082e16  mov     rcx, rdi
0x180082e19  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180082e20  call    WPP_SF_iS
0x180082e25  mov     eax, cs:dword_180173278
0x180082e2b  mov     esi, 8
0x180082e30  cmp     eax, r12d
0x180082e33  jbe     short loc_180082E92
0x180082e35  call    IkeGetTlsMmLuid
0x180082e3a  mov     [rbp+90h+var_E0], rax
0x180082e3e  lea     rax, [rbp+90h+var_E0]
0x180082e42  mov     [rbp+90h+var_A0], rax
0x180082e46  mov     [rbp+90h+var_98], rsi
0x180082e4a  call    IkeGetTlsPeerAddr
0x180082e4f  mov     rdx, rax
0x180082e52  lea     rcx, [rbp+90h+var_90]
0x180082e56  call    _tlgCreate1Sz_wchar_t
0x180082e5b  lea     rcx, aReceivedNullSs; "Received NULL SSPI token"
0x180082e62  mov     [rbp+90h+var_78], 19h
0x180082e6a  lea     rax, [rbp+90h+var_C0]
0x180082e6e  mov     [rbp+90h+var_80], rcx
0x180082e72  mov     qword ptr [rsp+190h+TargetDataRep], rax
0x180082e77  lea     rcx, dword_180173278
0x180082e7e  lea     rdx, byte_180155BAD
0x180082e85  mov     [rsp+190h+Reserved1], 5
0x180082e8d  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180082e92  mov     r15d, 80090308h
0x180082e98  jmp     loc_180083048
0x180082e9d  mov     rdx, r14
0x180082ea0  mov     rcx, rsi
0x180082ea3  call    IkeImpersonate
0x180082ea8  mov     rbx, rax
0x180082eab  test    rax, rax
0x180082eae  jnz     loc_180083243
0x180082eb4  mov     rax, [r14+68h]
0x180082eb8  test    rax, rax
0x180082ebb  jz      short loc_180082EC1
0x180082ebd  add     [rax+50h], r12d
0x180082ec1  mov     r8d, [rdi]
0x180082ec4  lea     rdx, aIscIntoken; "ISC intoken:"
0x180082ecb  mov     rcx, [rdi+8]
0x180082ecf  call    IkeDumpSspiToken
0x180082ed4  mov     r9d, [rbp+90h+fContextReq]; fContextReq
0x180082ed8  lea     rax, [r14+30h]
0x180082edc  mov     r8, [r14+40h]; pszTargetName
0x180082ee0  lea     rdx, [r14+18h]; phContext
0x180082ee4  mov     [rsp+190h+ptsExpiry], rax; ptsExpiry
0x180082ee9  lea     rbx, [r14+28h]
0x180082eed  mov     [rsp+190h+pfContextAttr], rbx; pfContextAttr
0x180082ef2  lea     rax, [rsp+190h+var_118]
0x180082ef7  mov     [rsp+190h+pOutput], rax; pOutput
0x180082efc  lea     rcx, [r14+8]; phCredential
0x180082f00  mov     [rsp+190h+phNewContext], rdx; phNewContext
0x180082f05  lea     rax, [rbp+90h+var_F8]
0x180082f09  mov     [rsp+190h+Reserved2], r15d; Reserved2
0x180082f0e  mov     [rsp+190h+pInput], rax; pInput
0x180082f13  mov     [rsp+190h+TargetDataRep], 10h; TargetDataRep
0x180082f1b  mov     [rsp+190h+Reserved1], r15d; Reserved1
0x180082f20  call    cs:__imp_InitializeSecurityContextW
0x180082f26  mov     r15d, eax
0x180082f29  mov     rsi, cs:WPP_GLOBAL_Control
0x180082f30  lea     r13, WPP_GLOBAL_Control
0x180082f37  mov     r12d, 4
0x180082f3d  cmp     rsi, r13
0x180082f40  jz      short loc_180082F8A
0x180082f42  cmp     [rsi+19h], r12b
0x180082f46  jb      short loc_180082F8A
0x180082f48  test    byte ptr [rsi+1Ch], 10h
0x180082f4c  jz      short loc_180082F8A
0x180082f4e  mov     edi, [rbx]
0x180082f50  mov     rsi, [rsi+10h]
0x180082f54  call    IkeGetTlsPeerAddr
0x180082f59  mov     rbx, rax
0x180082f5c  call    IkeGetTlsMmLuid
0x180082f61  mov     dword ptr [rsp+190h+pInput], edi
0x180082f65  lea     edx, [r12+12h]
0x180082f6a  mov     r9, rax
0x180082f6d  mov     [rsp+190h+TargetDataRep], r15d
0x180082f72  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180082f79  mov     qword ptr [rsp+190h+Reserved1], rbx
0x180082f7e  mov     rcx, rsi
0x180082f81  call    WPP_SF_iSDD
0x180082f86  lea     rbx, [r14+28h]
0x180082f8a  mov     eax, cs:dword_180173278
0x180082f90  mov     esi, 8
0x180082f95  cmp     eax, r12d
0x180082f98  jbe     short loc_180083005
0x180082f9a  call    IkeGetTlsMmLuid
0x180082f9f  mov     [rbp+90h+var_E0], rax
0x180082fa3  lea     rax, [rbp+90h+var_E0]
0x180082fa7  mov     [rbp+90h+var_A0], rax
0x180082fab  mov     [rbp+90h+var_98], rsi
0x180082faf  call    IkeGetTlsPeerAddr
0x180082fb4  mov     rdx, rax
0x180082fb7  lea     rcx, [rbp+90h+var_90]
0x180082fbb  call    _tlgCreate1Sz_wchar_t
0x180082fc0  lea     rax, [rbp+90h+fContextReq]
0x180082fc4  mov     [rbp+90h+fContextReq], r15d
0x180082fc8  mov     [rbp+90h+var_80], rax
0x180082fcc  lea     rdx, byte_180155B61
0x180082fd3  mov     eax, [rbx]
0x180082fd5  lea     rcx, dword_180173278
0x180082fdc  mov     [rbp+90h+var_E4], eax
0x180082fdf  lea     rax, [rbp+90h+var_E4]
0x180082fe3  mov     [rbp+90h+var_70], rax
0x180082fe7  lea     rax, [rbp+90h+var_C0]
0x180082feb  mov     qword ptr [rsp+190h+TargetDataRep], rax
0x180082ff0  mov     [rsp+190h+Reserved1], 6
0x180082ff8  mov     [rbp+90h+var_78], r12
0x180082ffc  mov     [rbp+90h+var_68], r12
0x180083000  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180083005  mov     rcx, r14
0x180083008  call    IkeRevertImpersonation
0x18008300d  mov     rbx, rax
0x180083010  test    rax, rax
0x180083013  jnz     loc_180083243
0x180083019  cmp     r15d, 90320h
0x180083020  jnz     short loc_180083032
0x180083022  or      dword ptr [r14+48h], 20h
0x180083027  mov     r15d, 90312h
0x18008302d  jmp     loc_1800831AD
0x180083032  test    r15d, r15d
0x180083035  jz      loc_1800831AD
0x18008303b  cmp     r15d, 90312h
0x180083042  jz      loc_1800831AD
0x180083048  call    cs:__imp_GetLastError
0x18008304e  mov     [rbp+90h+fContextReq], eax
0x180083051  mov     rdi, cs:WPP_GLOBAL_Control
0x180083058  cmp     rdi, r13
0x18008305b  jz      loc_1800830EB
0x180083061  cmp     [rdi+19h], r12b
0x180083065  jb      short loc_1800830A8
0x180083067  test    byte ptr [rdi+1Ch], 10h
0x18008306b  jz      short loc_1800830A8
0x18008306d  mov     rdi, [rdi+10h]
0x180083071  call    IkeGetTlsPeerAddr
0x180083076  mov     rbx, rax
0x180083079  call    IkeGetTlsMmLuid
0x18008307e  mov     r9, rax
0x180083081  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180083088  mov     eax, [rbp+90h+fContextReq]
0x18008308b  mov     edx, 17h
0x180083090  mov     [rsp+190h+TargetDataRep], eax
0x180083094  mov     rcx, rdi
0x180083097  mov     qword ptr [rsp+190h+Reserved1], rbx
0x18008309c  call    WPP_SF_iSL
0x1800830a1  mov     rdi, cs:WPP_GLOBAL_Control
0x1800830a8  cmp     rdi, r13
0x1800830ab  jz      short loc_1800830EB
0x1800830ad  cmp     byte ptr [rdi+19h], 2
0x1800830b1  jb      short loc_1800830EB
0x1800830b3  test    byte ptr [rdi+1Ch], 10h
0x1800830b7  jz      short loc_1800830EB
0x1800830b9  mov     rdi, [rdi+10h]
0x1800830bd  call    IkeGetTlsPeerAddr
0x1800830c2  mov     rbx, rax
0x1800830c5  call    IkeGetTlsMmLuid
0x1800830ca  mov     r9, rax
0x1800830cd  mov     [rsp+190h+TargetDataRep], r15d
0x1800830d2  mov     edx, 18h
0x1800830d7  mov     qword ptr [rsp+190h+Reserved1], rbx
0x1800830dc  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x1800830e3  mov     rcx, rdi
0x1800830e6  call    WPP_SF_iSL
0x1800830eb  mov     eax, cs:dword_180173278
0x1800830f1  cmp     eax, r12d
0x1800830f4  jbe     loc_180083185
0x1800830fa  call    IkeGetTlsMmLuid
0x1800830ff  mov     [rbp+90h+var_C8], rax
0x180083103  lea     rax, [rbp+90h+var_C8]
0x180083107  mov     [rbp+90h+var_A0], rax
0x18008310b  mov     [rbp+90h+var_98], 8
0x180083113  call    IkeGetTlsPeerAddr
0x180083118  mov     rdx, rax
0x18008311b  lea     rcx, [rbp+90h+var_90]
0x18008311f  call    _tlgCreate1Sz_wchar_t
0x180083124  mov     eax, [rbp+90h+fContextReq]
0x180083127  lea     rcx, aIscFailed; "ISC failed"
0x18008312e  mov     [rbp+90h+var_E4], eax
0x180083131  lea     rdx, byte_180155B05
0x180083138  lea     rax, [rbp+90h+var_E4]
0x18008313c  mov     [rbp+90h+var_80], rcx
0x180083140  mov     [rbp+90h+var_70], rax
0x180083144  lea     rcx, dword_180173278
0x18008314b  lea     rax, [rbp+90h+var_E0]
0x18008314f  mov     [rbp+90h+var_78], 0Bh
0x180083157  mov     [rbp+90h+var_60], rax
0x18008315b  lea     rax, [rbp+90h+var_C0]
0x18008315f  mov     qword ptr [rsp+190h+TargetDataRep], rax
0x180083164  mov     [rsp+190h+Reserved1], 7
0x18008316c  mov     [rbp+90h+var_68], 4
0x180083174  mov     dword ptr [rbp+90h+var_E0], r15d
0x180083178  mov     [rbp+90h+var_58], 4
0x180083180  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180083185  mov     r8d, 1
0x18008318b  mov     edx, r15d
0x18008318e  mov     rcx, r14
0x180083191  call    SetSspiError
0x180083196  mov     rbx, rax
0x180083199  test    rax, rax
0x18008319c  jnz     loc_180083243
0x1800831a2  mov     rax, [r14+68h]
0x1800831a6  test    rax, rax
0x1800831a9  jz      short loc_1800831AD
0x1800831ab  mov     [rax], ebx
0x1800831ad  mov     rcx, [rbp+90h+var_118.pBuffers]
0x1800831b1  lea     rdx, aIscOuttoken; "ISC outtoken:"
0x1800831b8  mov     r8d, [rcx]
0x1800831bb  mov     rcx, [rcx+8]
0x1800831bf  call    IkeDumpSspiToken
0x1800831c4  test    r15d, r15d
0x1800831c7  jnz     short loc_180083225
0x1800831c9  mov     rcx, [r14+68h]
0x1800831cd  test    rcx, rcx
0x1800831d0  jz      short loc_1800831E4
0x1800831d2  mov     eax, [r14+48h]
  ... truncated ...
```
