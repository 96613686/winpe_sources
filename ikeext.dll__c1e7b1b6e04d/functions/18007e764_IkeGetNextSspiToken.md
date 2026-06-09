# IkeGetNextSspiToken

- ea: `0x18007e764`
- end: `0x18007ec31`
- name: `IkeGetNextSspiToken`
- size: `1229`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007ca4c`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x180008388`
- `0x180025cfc`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005bce4`
- `0x18006dec8`
- `0x180074314`
- `0x18007c950`
- `0x18007d46c`
- `0x18007e764`
- `0x180080058`
- `0x1800849cc`
- `0x180084c50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ea72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ea72`
- `SspiCli!InitializeSecurityContextW` at `0x18007e965`
- `SspiCli!InitializeSecurityContextW` at `0x18007e965`

## string_xrefs

- `0x18007e79f`: `IkeGetNextSspiToken`
- `0x18007ebef`: `IkeGetNextSspiToken`
- `0x18007ebfe`: `IkeGetNextSspiToken`
- `0x18007ebda`: `ISC outtoken:`

## pseudocode

```c
__int64 __fastcall IkeGetNextSspiToken(__int64 a1, unsigned int *a2)
{
  __int64 SecBuffer; // rbx
  unsigned int v5; // eax
  __int64 v6; // rcx
  struct _SecBuffer *v7; // r15
  SIZE_T v8; // rcx
  struct _SecHandle *v9; // r12
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rsi
  __int64 TlsPeerAddr; // rbx
  __int64 v15; // rcx
  int TlsMmLuid; // eax
  __int64 v17; // rcx
  __int64 v18; // rax
  int v19; // r8d
  int v20; // r9d
  int *v21; // r13
  __int64 v22; // rcx
  unsigned int v23; // r12d
  int v24; // edi
  __int64 v25; // rsi
  __int64 v26; // rbx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rax
  int v31; // r8d
  int v32; // r9d
  __int64 v33; // rcx
  DWORD LastError; // esi
  _QWORD *v35; // rdi
  __int64 v36; // rdi
  __int64 v37; // rbx
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // rdi
  __int64 v41; // rbx
  __int64 v42; // rcx
  int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // rax
  int v46; // r8d
  int v47; // r9d
  struct _SecBufferDesc pOutput; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int fContextReq; // [rsp+70h] [rbp-90h] BYREF
  __int64 v51; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v52[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v53[32]; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v54; // [rsp+B0h] [rbp-50h]
  __int64 v55; // [rsp+B8h] [rbp-48h]
  _BYTE v56[16]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int *p_fContextReq; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v58; // [rsp+D8h] [rbp-28h]
  __int64 *v59; // [rsp+E0h] [rbp-20h]
  __int64 v60; // [rsp+E8h] [rbp-18h]
  unsigned int *v61; // [rsp+F0h] [rbp-10h]
  __int64 v62; // [rsp+F8h] [rbp-8h]

  fContextReq = 0;
  SecBuffer = 0;
  pOutput = 0;
  TraceLogHelper("IkeGetNextSspiToken", 1);
  v5 = a2[18];
  if ( (v5 & 0x210) != 0 )
    goto LABEL_41;
  if ( (v5 & 1) == 0 )
  {
    v7 = (struct _SecBuffer *)*((_QWORD *)a2 + 12);
    if ( !v7 )
      v7 = (struct _SecBuffer *)*((_QWORD *)a2 + 13);
    v8 = *a2;
    pOutput.ulVersion = 0;
    pOutput.cBuffers = 1;
    pOutput.pBuffers = v7;
    if ( v7->pvBuffer )
    {
      v9 = (struct _SecHandle *)(a2 + 6);
      **((_DWORD **)a2 + 13) = v8;
    }
    else
    {
      SecBuffer = IkeAllocateSecBuffer(v8);
      if ( SecBuffer )
        goto LABEL_41;
      v9 = 0;
    }
    SetIscFlags(a1, a2, &fContextReq);
    SecBuffer = IkeImpersonate(a1, a2);
    if ( SecBuffer )
      goto LABEL_41;
    v11 = *((_QWORD *)a2 + 13);
    if ( v11 )
      ++*(_DWORD *)(v11 + 80);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v12 = *((_QWORD *)a2 + 8);
      v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v10);
      TlsMmLuid = IkeGetTlsMmLuid(v15);
      WPP_SF_iSS(v13, 17, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, TlsMmLuid, TlsPeerAddr, v12);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v51 = IkeGetTlsMmLuid(v10);
      v54 = &v51;
      v55 = 8;
      v18 = IkeGetTlsPeerAddr(v17);
      tlgCreate1Sz_wchar_t(v56, v18);
      tlgCreate1Sz_wchar_t(&p_fContextReq, *((_QWORD *)a2 + 8));
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)byte_180155BEB,
        v19,
        v20,
        5,
        (__int64)v53);
    }
    v21 = (int *)(a2 + 10);
    v23 = InitializeSecurityContextW(
            (PCredHandle)(a2 + 2),
            v9,
            *((SEC_WCHAR **)a2 + 8),
            fContextReq,
            0,
            0x10u,
            0,
            0,
            (PCtxtHandle)(a2 + 6),
            &pOutput,
            a2 + 10,
            (PTimeStamp)a2 + 6);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v24 = *v21;
      v25 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v26 = IkeGetTlsPeerAddr(v22);
      v28 = IkeGetTlsMmLuid(v27);
      WPP_SF_iSDD(v25, 18, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v28, v26, v23, v24);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v52[0] = IkeGetTlsMmLuid(v22);
      v54 = v52;
      v55 = 8;
      v30 = IkeGetTlsPeerAddr(v29);
      tlgCreate1Sz_wchar_t(v56, v30);
      fContextReq = v23;
      p_fContextReq = &fContextReq;
      LODWORD(v51) = *v21;
      v59 = &v51;
      v58 = 4;
      v60 = 4;
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)word_180155CC2,
        v31,
        v32,
        6,
        (__int64)v53);
    }
    SecBuffer = IkeRevertImpersonation(a2);
    if ( SecBuffer )
      goto LABEL_41;
    if ( v23 && v23 != 590610 )
    {
      LastError = GetLastError();
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v36 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v37 = IkeGetTlsPeerAddr(v33);
          v39 = IkeGetTlsMmLuid(v38);
          WPP_SF_iSL(v36, 19, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v39, v37, LastError);
          v35 = WPP_GLOBAL_Control;
        }
        if ( v35 != &WPP_GLOBAL_Control && *((_BYTE *)v35 + 25) >= 4u && (*((_BYTE *)v35 + 28) & 0x10) != 0 )
        {
          v40 = v35[2];
          v41 = IkeGetTlsPeerAddr(v33);
          v43 = IkeGetTlsMmLuid(v42);
          WPP_SF_iSL(v40, 20, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v43, v41, v23);
        }
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v52[0] = IkeGetTlsMmLuid(v33);
        v55 = 8;
        v54 = v52;
        v45 = IkeGetTlsPeerAddr(v44);
        tlgCreate1Sz_wchar_t(v56, v45);
        v58 = 11;
        v59 = &v51;
        p_fContextReq = (unsigned int *)"ISC failed";
        v61 = &fContextReq;
        LODWORD(v51) = LastError;
        v60 = 4;
        fContextReq = v23;
        v62 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_180155C6A,
          v46,
          v47,
          7,
          (__int64)v53);
      }
      SecBuffer = SetSspiError(a2, v23, 1);
      if ( SecBuffer )
        goto LABEL_41;
      v7->cbBuffer = 0;
    }
    IkeDumpSspiToken(pOutput.pBuffers->pvBuffer, "ISC outtoken:", pOutput.pBuffers->cbBuffer);
LABEL_41:
    TraceLogHelper("IkeGetNextSspiToken", 0);
    v6 = SecBuffer;
    return IkeReturnError(v6, "IkeGetNextSspiToken");
  }
  a2[18] = v5 & 0xFFFFFFFE;
  v6 = 0;
  return IkeReturnError(v6, "IkeGetNextSspiToken");
}

```

## disassembly

```asm
0x18007e764  mov     [rsp-8+arg_10], rbx
0x18007e769  push    rbp
0x18007e76a  push    rsi
0x18007e76b  push    rdi
0x18007e76c  push    r12
0x18007e76e  push    r13
0x18007e770  push    r14
0x18007e772  push    r15
0x18007e774  lea     rbp, [rsp-10h]
0x18007e779  sub     rsp, 110h
0x18007e780  mov     rax, cs:__security_cookie
0x18007e787  xor     rax, rsp
0x18007e78a  mov     [rbp+40h+var_40], rax
0x18007e78e  xor     r13d, r13d
0x18007e791  mov     r14, rdx
0x18007e794  mov     rdi, rcx
0x18007e797  mov     [rsp+140h+fContextReq], r13d
0x18007e79c  xorps   xmm0, xmm0
0x18007e79f  lea     rcx, aIkegetnextsspi; "IkeGetNextSspiToken"
0x18007e7a6  mov     ebx, r13d
0x18007e7a9  lea     esi, [r13+1]
0x18007e7ad  mov     edx, esi
0x18007e7af  movups  xmmword ptr [rsp+140h+var_E0.ulVersion], xmm0
0x18007e7b4  call    TraceLogHelper
0x18007e7b9  mov     eax, [r14+48h]
0x18007e7bd  test    eax, 210h
0x18007e7c2  jnz     loc_18007EBED
0x18007e7c8  test    sil, al
0x18007e7cb  jz      short loc_18007E7DB
0x18007e7cd  and     eax, 0FFFFFFFEh
0x18007e7d0  mov     [r14+48h], eax
0x18007e7d4  xor     ecx, ecx
0x18007e7d6  jmp     loc_18007EBFE
0x18007e7db  mov     r15, [r14+60h]
0x18007e7df  test    r15, r15
0x18007e7e2  jnz     short loc_18007E7E8
0x18007e7e4  mov     r15, [r14+68h]
0x18007e7e8  mov     ecx, [r14]; dwBytes
0x18007e7eb  mov     [rsp+140h+var_E0.ulVersion], r13d
0x18007e7f0  mov     [rsp+140h+var_E0.cBuffers], esi
0x18007e7f4  mov     [rsp+140h+var_E0.pBuffers], r15
0x18007e7f9  cmp     [r15+8], r13
0x18007e7fd  jnz     short loc_18007E818
0x18007e7ff  mov     rdx, r15
0x18007e802  call    IkeAllocateSecBuffer
0x18007e807  mov     rbx, rax
0x18007e80a  test    rax, rax
0x18007e80d  jnz     loc_18007EBED
0x18007e813  mov     r12, r13
0x18007e816  jmp     short loc_18007E822
0x18007e818  mov     rax, [r14+68h]
0x18007e81c  lea     r12, [r14+18h]
0x18007e820  mov     [rax], ecx
0x18007e822  lea     r8, [rsp+140h+fContextReq]
0x18007e827  mov     rdx, r14
0x18007e82a  mov     rcx, rdi
0x18007e82d  call    SetIscFlags
0x18007e832  mov     rdx, r14
0x18007e835  mov     rcx, rdi
0x18007e838  call    IkeImpersonate
0x18007e83d  mov     rbx, rax
0x18007e840  test    rax, rax
0x18007e843  jnz     loc_18007EBED
0x18007e849  mov     rax, [r14+68h]
0x18007e84d  test    rax, rax
0x18007e850  jz      short loc_18007E855
0x18007e852  add     [rax+50h], esi
0x18007e855  mov     rsi, cs:WPP_GLOBAL_Control
0x18007e85c  lea     rbx, WPP_GLOBAL_Control
0x18007e863  cmp     rsi, rbx
0x18007e866  jz      short loc_18007E8B1
0x18007e868  cmp     byte ptr [rsi+19h], 4
0x18007e86c  jb      short loc_18007E8B1
0x18007e86e  test    byte ptr [rsi+1Ch], 10h
0x18007e872  jz      short loc_18007E8B1
0x18007e874  mov     rdi, [r14+40h]
0x18007e878  mov     rsi, [rsi+10h]
0x18007e87c  call    IkeGetTlsPeerAddr
0x18007e881  mov     rbx, rax
0x18007e884  call    IkeGetTlsMmLuid
0x18007e889  mov     r9, rax
0x18007e88c  mov     qword ptr [rsp+140h+TargetDataRep], rdi
0x18007e891  mov     edx, 11h
0x18007e896  mov     qword ptr [rsp+140h+Reserved1], rbx
0x18007e89b  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x18007e8a2  mov     rcx, rsi
0x18007e8a5  call    WPP_SF_iSS
0x18007e8aa  lea     rbx, WPP_GLOBAL_Control
0x18007e8b1  mov     eax, cs:dword_180173278
0x18007e8b7  cmp     eax, 4
0x18007e8ba  jbe     short loc_18007E919
0x18007e8bc  call    IkeGetTlsMmLuid
0x18007e8c1  mov     [rsp+140h+var_C8], rax
0x18007e8c6  lea     rax, [rsp+140h+var_C8]
0x18007e8cb  mov     [rbp+40h+var_90], rax
0x18007e8cf  mov     [rbp+40h+var_88], 8
0x18007e8d7  call    IkeGetTlsPeerAddr
0x18007e8dc  mov     rdx, rax
0x18007e8df  lea     rcx, [rbp+40h+var_80]
0x18007e8e3  call    _tlgCreate1Sz_wchar_t
0x18007e8e8  mov     rdx, [r14+40h]
0x18007e8ec  lea     rcx, [rbp+40h+var_70]
0x18007e8f0  call    _tlgCreate1Sz_wchar_t
0x18007e8f5  lea     rcx, [rbp+40h+var_B0]
0x18007e8f9  mov     qword ptr [rsp+140h+TargetDataRep], rcx
0x18007e8fe  lea     rdx, byte_180155BEB
0x18007e905  lea     rcx, dword_180173278
0x18007e90c  mov     [rsp+140h+Reserved1], 5
0x18007e914  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18007e919  mov     r9d, [rsp+140h+fContextReq]; fContextReq
0x18007e91e  lea     rax, [r14+30h]
0x18007e922  mov     [rsp+140h+ptsExpiry], rax; ptsExpiry
0x18007e927  lea     r8, [r14+18h]
0x18007e92b  xor     edi, edi
0x18007e92d  lea     rax, [rsp+140h+var_E0]
0x18007e932  lea     r13, [r14+28h]
0x18007e936  mov     rdx, r12; phContext
0x18007e939  mov     [rsp+140h+pfContextAttr], r13; pfContextAttr
0x18007e93e  lea     rcx, [r14+8]; phCredential
0x18007e942  mov     [rsp+140h+pOutput], rax; pOutput
0x18007e947  mov     [rsp+140h+phNewContext], r8; phNewContext
0x18007e94c  mov     r8, [r14+40h]; pszTargetName
0x18007e950  mov     [rsp+140h+Reserved2], edi; Reserved2
0x18007e954  mov     [rsp+140h+pInput], rdi; pInput
0x18007e959  mov     [rsp+140h+TargetDataRep], 10h; TargetDataRep
0x18007e961  mov     [rsp+140h+Reserved1], edi; Reserved1
0x18007e965  call    cs:__imp_InitializeSecurityContextW
0x18007e96b  mov     r12d, eax
0x18007e96e  mov     rsi, cs:WPP_GLOBAL_Control
0x18007e975  cmp     rsi, rbx
0x18007e978  jz      short loc_18007E9C0
0x18007e97a  cmp     byte ptr [rsi+19h], 4
0x18007e97e  jb      short loc_18007E9C0
0x18007e980  test    byte ptr [rsi+1Ch], 10h
0x18007e984  jz      short loc_18007E9C0
0x18007e986  mov     edi, [r13+0]
0x18007e98a  mov     rsi, [rsi+10h]
0x18007e98e  call    IkeGetTlsPeerAddr
0x18007e993  mov     rbx, rax
0x18007e996  call    IkeGetTlsMmLuid
0x18007e99b  mov     dword ptr [rsp+140h+pInput], edi
0x18007e99f  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x18007e9a6  mov     r9, rax
0x18007e9a9  mov     [rsp+140h+TargetDataRep], r12d
0x18007e9ae  mov     edx, 12h
0x18007e9b3  mov     qword ptr [rsp+140h+Reserved1], rbx
0x18007e9b8  mov     rcx, rsi
0x18007e9bb  call    WPP_SF_iSDD
0x18007e9c0  mov     eax, cs:dword_180173278
0x18007e9c6  cmp     eax, 4
0x18007e9c9  jbe     short loc_18007EA48
0x18007e9cb  call    IkeGetTlsMmLuid
0x18007e9d0  mov     [rbp+40h+var_C0], rax
0x18007e9d4  lea     rax, [rbp+40h+var_C0]
0x18007e9d8  mov     [rbp+40h+var_90], rax
0x18007e9dc  mov     [rbp+40h+var_88], 8
0x18007e9e4  call    IkeGetTlsPeerAddr
0x18007e9e9  mov     rdx, rax
0x18007e9ec  lea     rcx, [rbp+40h+var_80]
0x18007e9f0  call    _tlgCreate1Sz_wchar_t
0x18007e9f5  lea     rax, [rsp+140h+fContextReq]
0x18007e9fa  mov     [rsp+140h+fContextReq], r12d
0x18007e9ff  mov     [rbp+40h+var_70], rax
0x18007ea03  lea     rdx, word_180155CC2
0x18007ea0a  mov     eax, [r13+0]
0x18007ea0e  lea     rcx, dword_180173278
0x18007ea15  mov     dword ptr [rsp+140h+var_C8], eax
0x18007ea19  lea     rax, [rsp+140h+var_C8]
0x18007ea1e  mov     [rbp+40h+var_60], rax
0x18007ea22  lea     rax, [rbp+40h+var_B0]
0x18007ea26  mov     qword ptr [rsp+140h+TargetDataRep], rax
0x18007ea2b  mov     [rsp+140h+Reserved1], 6
0x18007ea33  mov     [rbp+40h+var_68], 4
0x18007ea3b  mov     [rbp+40h+var_58], 4
0x18007ea43  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18007ea48  mov     rcx, r14
0x18007ea4b  call    IkeRevertImpersonation
0x18007ea50  mov     rbx, rax
0x18007ea53  test    rax, rax
0x18007ea56  jnz     loc_18007EBED
0x18007ea5c  test    r12d, r12d
0x18007ea5f  jz      loc_18007EBD5
0x18007ea65  cmp     r12d, 90312h
0x18007ea6c  jz      loc_18007EBD5
0x18007ea72  call    cs:__imp_GetLastError
0x18007ea78  mov     esi, eax
0x18007ea7a  mov     rdi, cs:WPP_GLOBAL_Control
0x18007ea81  lea     r13, WPP_GLOBAL_Control
0x18007ea88  cmp     rdi, r13
0x18007ea8b  jz      loc_18007EB18
0x18007ea91  cmp     byte ptr [rdi+19h], 4
0x18007ea95  jb      short loc_18007EAD5
0x18007ea97  test    byte ptr [rdi+1Ch], 10h
0x18007ea9b  jz      short loc_18007EAD5
0x18007ea9d  mov     rdi, [rdi+10h]
0x18007eaa1  call    IkeGetTlsPeerAddr
0x18007eaa6  mov     rbx, rax
0x18007eaa9  call    IkeGetTlsMmLuid
0x18007eaae  mov     r9, rax
0x18007eab1  mov     [rsp+140h+TargetDataRep], esi
0x18007eab5  mov     edx, 13h
0x18007eaba  mov     qword ptr [rsp+140h+Reserved1], rbx
0x18007eabf  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x18007eac6  mov     rcx, rdi
0x18007eac9  call    WPP_SF_iSL
0x18007eace  mov     rdi, cs:WPP_GLOBAL_Control
0x18007ead5  cmp     rdi, r13
0x18007ead8  jz      short loc_18007EB18
0x18007eada  cmp     byte ptr [rdi+19h], 4
0x18007eade  jb      short loc_18007EB18
0x18007eae0  test    byte ptr [rdi+1Ch], 10h
0x18007eae4  jz      short loc_18007EB18
0x18007eae6  mov     rdi, [rdi+10h]
0x18007eaea  call    IkeGetTlsPeerAddr
0x18007eaef  mov     rbx, rax
0x18007eaf2  call    IkeGetTlsMmLuid
0x18007eaf7  mov     r9, rax
0x18007eafa  mov     [rsp+140h+TargetDataRep], r12d
0x18007eaff  mov     edx, 14h
0x18007eb04  mov     qword ptr [rsp+140h+Reserved1], rbx
0x18007eb09  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x18007eb10  mov     rcx, rdi
0x18007eb13  call    WPP_SF_iSL
0x18007eb18  mov     eax, cs:dword_180173278
0x18007eb1e  cmp     eax, 4
0x18007eb21  jbe     loc_18007EBB7
0x18007eb27  call    IkeGetTlsMmLuid
0x18007eb2c  mov     [rbp+40h+var_C0], rax
0x18007eb30  xor     edi, edi
0x18007eb32  lea     rax, [rbp+40h+var_C0]
0x18007eb36  mov     [rbp+40h+var_88], 8
0x18007eb3e  mov     [rbp+40h+var_90], rax
0x18007eb42  call    IkeGetTlsPeerAddr
0x18007eb47  mov     rdx, rax
0x18007eb4a  lea     rcx, [rbp+40h+var_80]
0x18007eb4e  call    _tlgCreate1Sz_wchar_t
0x18007eb53  lea     rax, [rsp+140h+var_C8]
0x18007eb58  mov     [rbp+40h+var_68], 0Bh
0x18007eb60  mov     [rbp+40h+var_60], rax
0x18007eb64  lea     rcx, aIscFailed; "ISC failed"
0x18007eb6b  lea     rax, [rsp+140h+fContextReq]
0x18007eb70  mov     [rbp+40h+var_70], rcx
0x18007eb74  mov     [rbp+40h+var_50], rax
0x18007eb78  lea     rdx, word_180155C6A
0x18007eb7f  lea     rax, [rbp+40h+var_B0]
0x18007eb83  mov     dword ptr [rsp+140h+var_C8], esi
0x18007eb87  mov     qword ptr [rsp+140h+TargetDataRep], rax
0x18007eb8c  lea     rcx, dword_180173278
0x18007eb93  mov     [rsp+140h+Reserved1], 7
0x18007eb9b  mov     [rbp+40h+var_58], 4
0x18007eba3  mov     [rsp+140h+fContextReq], r12d
0x18007eba8  mov     [rbp+40h+var_48], 4
0x18007ebb0  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18007ebb5  jmp     short loc_18007EBB9
0x18007ebb7  xor     edi, edi
0x18007ebb9  mov     r8d, 1
0x18007ebbf  mov     edx, r12d
0x18007ebc2  mov     rcx, r14
0x18007ebc5  call    SetSspiError
0x18007ebca  mov     rbx, rax
0x18007ebcd  test    rax, rax
0x18007ebd0  jnz     short loc_18007EBED
0x18007ebd2  mov     [r15], edi
0x18007ebd5  mov     rcx, [rsp+140h+var_E0.pBuffers]
0x18007ebda  lea     rdx, aIscOuttoken; "ISC outtoken:"
0x18007ebe1  mov     r8d, [rcx]
0x18007ebe4  mov     rcx, [rcx+8]
0x18007ebe8  call    IkeDumpSspiToken
0x18007ebed  xor     edx, edx
0x18007ebef  lea     rcx, aIkegetnextsspi; "IkeGetNextSspiToken"
0x18007ebf6  call    TraceLogHelper
0x18007ebfb  mov     rcx, rbx
0x18007ebfe  lea     rdx, aIkegetnextsspi; "IkeGetNextSspiToken"
0x18007ec05  call    IkeReturnError
0x18007ec0a  mov     rcx, [rbp+40h+var_40]
0x18007ec0e  xor     rcx, rsp; StackCookie
0x18007ec11  call    __security_check_cookie
0x18007ec16  mov     rbx, [rsp+140h+arg_10]
0x18007ec1e  add     rsp, 110h
0x18007ec25  pop     r15
0x18007ec27  pop     r14
0x18007ec29  pop     r13
0x18007ec2b  pop     r12
0x18007ec2d  pop     rdi
0x18007ec2e  pop     rsi
0x18007ec2f  pop     rbp
0x18007ec30  retn
```
