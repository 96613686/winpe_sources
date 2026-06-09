# UxpSslQuerySslConnectionInfo

- ea: `0x1400b95a8`
- end: `0x1400b9e55`
- name: `UxpSslQuerySslConnectionInfo`
- size: `2221`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140079ac4`

## callees

- `0x140092f80`
- `0x140094540`
- `0x140094784`
- `0x140094b20`
- `0x140098b20`
- `0x1400a9b20`
- `0x1400af800`
- `0x1400b95a8`
- `0x1400b9e5c`
- `0x140106544`
- `0x140167700`
- `0x140167b40`
- `0x1401c3f78`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x1400b9670`
- `HAL!KeQueryPerformanceCounter` at `0x1400b9b73`
- `HAL!KeQueryPerformanceCounter` at `0x1400b9b9f`
- `HAL!KeQueryPerformanceCounter` at `0x1400b9dfa`
- `HAL!KeQueryPerformanceCounter` at `0x1400b9670`
- `HAL!KeQueryPerformanceCounter` at `0x1400b9b73`
- `HAL!KeQueryPerformanceCounter` at `0x1400b9b9f`
- `HAL!KeQueryPerformanceCounter` at `0x1400b9dfa`
- `ksecdd!QueryContextAttributesW` at `0x1400b9697`
- `ksecdd!QueryContextAttributesW` at `0x1400b979e`
- `ksecdd!QueryContextAttributesW` at `0x1400b987e`
- `ksecdd!QueryContextAttributesW` at `0x1400b99bc`
- `ksecdd!QueryContextAttributesW` at `0x1400b9ab1`
- `ksecdd!QueryContextAttributesW` at `0x1400b9bbf`
- `ksecdd!QueryContextAttributesW` at `0x1400b9c17`
- `ksecdd!QueryContextAttributesW` at `0x1400b9697`
- `ksecdd!QueryContextAttributesW` at `0x1400b979e`
- `ksecdd!QueryContextAttributesW` at `0x1400b987e`
- `ksecdd!QueryContextAttributesW` at `0x1400b99bc`
- `ksecdd!QueryContextAttributesW` at `0x1400b9ab1`
- `ksecdd!QueryContextAttributesW` at `0x1400b9bbf`
- `ksecdd!QueryContextAttributesW` at `0x1400b9c17`
- `ksecdd!QuerySecurityContextToken` at `0x1400b9d05`
- `ksecdd!QuerySecurityContextToken` at `0x1400b9d05`

## string_xrefs

- `0x1400b9708`: `Attribute_StreamSizes`
- `0x1400b9d74`: `ContextToken`

## pseudocode

```c
__int64 __fastcall UxpSslQuerySslConnectionInfo(__int64 a1)
{
  unsigned int ContextAttributesW; // esi
  __int64 v3; // r10
  int SslConnectionPostHandshakeClientAuth; // edi
  __int64 v5; // rdx
  int v6; // eax
  __int64 v7; // r10
  __int128 v8; // xmm1
  __int64 v9; // r10
  __int64 v10; // rdx
  _OWORD *v11; // rcx
  _OWORD *v12; // rax
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int64 v22; // rax
  __int64 v23; // r10
  char v24; // r15
  unsigned int v25; // eax
  int SslTokenBindingInfo; // eax
  __int64 v27; // rdx
  __m128i v28; // xmm0
  __int64 v29; // r10
  SECURITY_STATUS SecurityContextToken; // edi
  __int64 v31; // rcx
  __m128i v33; // [rsp+40h] [rbp-C0h] BYREF
  __int128 pBuffer; // [rsp+50h] [rbp-B0h] BYREF
  int v35; // [rsp+60h] [rbp-A0h]
  _BYTE v36[20]; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v37[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v38[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+C0h] [rbp-40h]
  _BYTE v40[272]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v41[688]; // [rsp+1E0h] [rbp+E0h] BYREF

  memset(v37, 0, 28);
  v35 = 0;
  pBuffer = 0;
  memset(v41, 0, 0x2A8u);
  v39 = 0;
  memset(v38, 0, sizeof(v38));
  memset(v40, 0, 0x108u);
  v33 = 0;
  memset(v36, 0, sizeof(v36));
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1041, 210, WPP_6033a49e77e7395416619077875677ff_Traceguids, a1);
  if ( !*(_BYTE *)(a1 + 232) )
    *(LARGE_INTEGER *)(a1 + 1728) = KeQueryPerformanceCounter(0);
  ContextAttributesW = QueryContextAttributesW((PCtxtHandle)(a1 + 440), 4u, &pBuffer);
  if ( ContextAttributesW )
  {
    v3 = *(_QWORD *)(a1 + 1696);
    if ( (*(_BYTE *)(v3 + 1763) & 8) != 0
      && (!*(_QWORD *)(v3 + 1776)
       || UlEtwEvaluateFilter(v3, a1 + 88, a1 + 116, 0, *(_QWORD *)(a1 + 1656), *(unsigned __int16 *)(a1 + 1648), 0, 0)) )
    {
      McTemplateK0pqs_EtwWriteTransfer(
        *(_QWORD *)(a1 + 1696) + 1688,
        (unsigned int)HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE,
        a1 + 72,
        a1,
        ContextAttributesW,
        (__int64)"Attribute_StreamSizes");
    }
    SslConnectionPostHandshakeClientAuth = UxSslMapSecurityStatusToErrorNtStatus(ContextAttributesW);
    if ( (BYTE2(xmmword_1401A2C90) & 2) != 0 )
    {
      v5 = 211;
LABEL_12:
      WPP_SF_qD(529, v5, WPP_6033a49e77e7395416619077875677ff_Traceguids, a1, ContextAttributesW);
      goto LABEL_82;
    }
    goto LABEL_82;
  }
  *(_QWORD *)(a1 + 456) = pBuffer;
  v6 = DWORD2(pBuffer);
  if ( DWORD2(pBuffer) > 0x4000 )
    v6 = 0x4000;
  *(_DWORD *)(a1 + 464) = v6;
  ContextAttributesW = QueryContextAttributesW((PCtxtHandle)(a1 + 440), 0x5Au, v37);
  if ( !ContextAttributesW )
  {
    v8 = *(_OWORD *)((char *)v37 + 12);
    *(_OWORD *)(a1 + 468) = v37[0];
    *(_OWORD *)(a1 + 480) = v8;
    ContextAttributesW = QueryContextAttributesW((PCtxtHandle)(a1 + 440), 0x64u, v41);
    if ( ContextAttributesW )
    {
      v9 = *(_QWORD *)(a1 + 1696);
      if ( (*(_BYTE *)(v9 + 1763) & 8) != 0
        && (!*(_QWORD *)(v9 + 1776)
         || UlEtwEvaluateFilter(
              v9,
              a1 + 88,
              a1 + 116,
              0,
              *(_QWORD *)(a1 + 1656),
              *(unsigned __int16 *)(a1 + 1648),
              0,
              0)) )
      {
        McTemplateK0pqs_EtwWriteTransfer(
          *(_QWORD *)(a1 + 1696) + 1688,
          (unsigned int)HTTP_EVENT_SSL_QUERY_CIPHER_INFO_FAILURE,
          a1 + 72,
          a1,
          ContextAttributesW,
          (__int64)"Attribute_CipherInfo");
      }
      SslConnectionPostHandshakeClientAuth = UxSslMapSecurityStatusToErrorNtStatus(ContextAttributesW);
      if ( (BYTE2(xmmword_1401A2C90) & 2) != 0 )
      {
        v5 = 213;
        goto LABEL_12;
      }
      goto LABEL_82;
    }
    v10 = 5;
    v11 = (_OWORD *)(a1 + 496);
    v12 = v41;
    do
    {
      v13 = v12[1];
      *v11 = *v12;
      v14 = v12[2];
      v11[1] = v13;
      v15 = v12[3];
      v11[2] = v14;
      v16 = v12[4];
      v11[3] = v15;
      v17 = v12[5];
      v11[4] = v16;
      v18 = v12[6];
      v11[5] = v17;
      v19 = v12[7];
      v12 += 8;
      v11[6] = v18;
      v11[7] = v19;
      v11 += 8;
      --v10;
    }
    while ( v10 );
    v20 = *v12;
    v21 = v12[1];
    v22 = *((_QWORD *)v12 + 4);
    *v11 = v20;
    v11[1] = v21;
    *((_QWORD *)v11 + 4) = v22;
    ContextAttributesW = QueryContextAttributesW((PCtxtHandle)(a1 + 440), 0x5Du, v38);
    if ( ContextAttributesW )
    {
      v23 = *(_QWORD *)(a1 + 1696);
      if ( (*(_BYTE *)(v23 + 1763) & 8) != 0
        && (!*(_QWORD *)(v23 + 1776)
         || UlEtwEvaluateFilter(
              v23,
              a1 + 88,
              a1 + 116,
              0,
              *(_QWORD *)(a1 + 1656),
              *(unsigned __int16 *)(a1 + 1648),
              0,
              0)) )
      {
        McTemplateK0pqs_EtwWriteTransfer(
          *(_QWORD *)(a1 + 1696) + 1688,
          (unsigned int)HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE,
          a1 + 72,
          a1,
          ContextAttributesW,
          (__int64)"Attribute_SessionInfo");
      }
      SslConnectionPostHandshakeClientAuth = UxSslMapSecurityStatusToErrorNtStatus(ContextAttributesW);
      if ( (BYTE2(xmmword_1401A2C90) & 2) != 0 )
      {
        v5 = 214;
        goto LABEL_12;
      }
      goto LABEL_82;
    }
    v24 = 1;
    *(_BYTE *)(a1 + 1176) = v38[0] & 1;
    SslConnectionPostHandshakeClientAuth = UxpSslQuerySslConnectionPostHandshakeClientAuth(a1);
    if ( SslConnectionPostHandshakeClientAuth < 0 )
      goto LABEL_82;
    if ( !*(_BYTE *)(a1 + 232) )
    {
      v25 = QueryContextAttributesW((PCtxtHandle)(a1 + 440), 0x23u, v40);
      ContextAttributesW = v25;
      if ( v25 )
      {
        SslConnectionPostHandshakeClientAuth = UxSslMapSecurityStatusToErrorNtStatus(v25);
        if ( (BYTE2(xmmword_1401A2C90) & 2) != 0 )
        {
          v5 = 215;
          goto LABEL_12;
        }
        goto LABEL_82;
      }
      SslTokenBindingInfo = UxpSslProcessApplicationProtocolQuery(a1, v40);
      SslConnectionPostHandshakeClientAuth = SslTokenBindingInfo;
      if ( SslTokenBindingInfo < 0 )
      {
        if ( (BYTE2(xmmword_1401A2C90) & 2) == 0 )
          goto LABEL_82;
        v27 = 216;
LABEL_45:
        WPP_SF_qD(529, v27, WPP_6033a49e77e7395416619077875677ff_Traceguids, a1, SslTokenBindingInfo);
        goto LABEL_82;
      }
      SslTokenBindingInfo = UxpSslQuerySslTokenBindingInfo(a1);
      SslConnectionPostHandshakeClientAuth = SslTokenBindingInfo;
      if ( SslTokenBindingInfo < 0 )
      {
        if ( (BYTE2(xmmword_1401A2C90) & 2) == 0 )
          goto LABEL_82;
        v27 = 217;
        goto LABEL_45;
      }
      SslTokenBindingInfo = UxpSslQueryChannelBindingInfo(a1);
      SslConnectionPostHandshakeClientAuth = SslTokenBindingInfo;
      if ( SslTokenBindingInfo < 0 )
      {
        if ( (BYTE2(xmmword_1401A2C90) & 2) == 0 )
          goto LABEL_82;
        v27 = 218;
        goto LABEL_45;
      }
    }
    SslConnectionPostHandshakeClientAuth = UxSslGetServerCertSubjectAndIssuer(a1, 0);
    if ( SslConnectionPostHandshakeClientAuth < 0 )
      goto LABEL_82;
    if ( !*(_BYTE *)(a1 + 232) )
      *(LARGE_INTEGER *)(a1 + 1736) = KeQueryPerformanceCounter(0);
    if ( (*(_DWORD *)(a1 + 1184) & 4) == 0 )
      goto LABEL_82;
    if ( !*(_BYTE *)(a1 + 232) )
      *(LARGE_INTEGER *)(a1 + 1744) = KeQueryPerformanceCounter(0);
    if ( QueryContextAttributesW((PCtxtHandle)(a1 + 440), 0x5Fu, &v33) || !v33.m128i_i32[1] )
    {
      *(_QWORD *)(a1 + 1264) = 0;
      *(_QWORD *)(a1 + 1256) = 0;
    }
    else
    {
      v28 = v33;
      *(__m128i *)(a1 + 1256) = v33;
      *(_DWORD *)(a1 + 1188) = *(_DWORD *)_mm_srli_si128(v28, 8).m128i_i32[0];
      *(_OWORD *)&v36[4] = UxSslClientCertPolicyGuid;
      ContextAttributesW = QueryContextAttributesW((PCtxtHandle)(a1 + 440), 0x61u, v36);
      if ( ContextAttributesW )
      {
        v29 = *(_QWORD *)(a1 + 1696);
        if ( (*(_BYTE *)(v29 + 1763) & 8) != 0
          && (!*(_QWORD *)(v29 + 1776)
           || UlEtwEvaluateFilter(
                v29,
                a1 + 88,
                a1 + 116,
                0,
                *(_QWORD *)(a1 + 1656),
                *(unsigned __int16 *)(a1 + 1648),
                0,
                0)) )
        {
          McTemplateK0pqs_EtwWriteTransfer(
            *(_QWORD *)(a1 + 1696) + 1688,
            (unsigned int)HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE,
            a1 + 72,
            a1,
            ContextAttributesW,
            (__int64)"Attribute_PolicyResult");
        }
        SslConnectionPostHandshakeClientAuth = UxSslMapSecurityStatusToErrorNtStatus(ContextAttributesW);
        if ( (BYTE2(xmmword_1401A2C90) & 2) != 0 )
        {
          v5 = 219;
          goto LABEL_12;
        }
        goto LABEL_82;
      }
      *(_DWORD *)(a1 + 1272) = UxSslMapSecurityStatusToCertError(*(unsigned int *)v36);
      if ( (*(_DWORD *)(*(_QWORD *)(a1 + 432) + 688LL) & 1) == 0 )
        goto LABEL_82;
      SecurityContextToken = QuerySecurityContextToken((PCtxtHandle)(a1 + 440), (void **)(a1 + 1280));
      if ( SecurityContextToken )
      {
        v31 = *(_QWORD *)(a1 + 1696);
        if ( (*(_BYTE *)(v31 + 1763) & 8) != 0
          && (!*(_QWORD *)(v31 + 1776)
           || UlEtwEvaluateFilter(
                v31,
                a1 + 88,
                a1 + 116,
                0,
                *(_QWORD *)(a1 + 1656),
                *(unsigned __int16 *)(a1 + 1648),
                0,
                0)) )
        {
          McTemplateK0pqs_EtwWriteTransfer(
            *(_QWORD *)(a1 + 1696) + 1688,
            (unsigned int)HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE,
            a1 + 72,
            a1,
            SecurityContextToken,
            (__int64)"ContextToken");
        }
        if ( (BYTE10(xmmword_1401A2C90) & 2) != 0 )
          WPP_SF_qD(785, 220, WPP_6033a49e77e7395416619077875677ff_Traceguids, a1, SecurityContextToken);
        *(_QWORD *)(a1 + 1280) = 0;
      }
      else
      {
        v24 = 0;
      }
      *(_BYTE *)(a1 + 1288) = v24;
    }
    SslConnectionPostHandshakeClientAuth = 0;
    goto LABEL_82;
  }
  v7 = *(_QWORD *)(a1 + 1696);
  if ( (*(_BYTE *)(v7 + 1763) & 8) != 0
    && (!*(_QWORD *)(v7 + 1776)
     || UlEtwEvaluateFilter(v7, a1 + 88, a1 + 116, 0, *(_QWORD *)(a1 + 1656), *(unsigned __int16 *)(a1 + 1648), 0, 0)) )
  {
    McTemplateK0pqs_EtwWriteTransfer(
      *(_QWORD *)(a1 + 1696) + 1688,
      (unsigned int)HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE,
      a1 + 72,
      a1,
      ContextAttributesW,
      (__int64)"Attribute_ConnInfo");
  }
  SslConnectionPostHandshakeClientAuth = UxSslMapSecurityStatusToErrorNtStatus(ContextAttributesW);
  if ( (BYTE2(xmmword_1401A2C90) & 2) != 0 )
  {
    v5 = 212;
    goto LABEL_12;
  }
LABEL_82:
  if ( !*(_BYTE *)(a1 + 232) && (*(_DWORD *)(a1 + 1184) & 4) != 0 )
    *(LARGE_INTEGER *)(a1 + 1752) = KeQueryPerformanceCounter(0);
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(
      1041,
      221,
      WPP_6033a49e77e7395416619077875677ff_Traceguids,
      (unsigned int)SslConnectionPostHandshakeClientAuth);
  return (unsigned int)SslConnectionPostHandshakeClientAuth;
}

```

## disassembly

```asm
0x1400b95a8  push    rbp
0x1400b95aa  push    rbx
0x1400b95ab  push    rsi
0x1400b95ac  push    rdi
0x1400b95ad  push    r12
0x1400b95af  push    r13
0x1400b95b1  push    r14
0x1400b95b3  push    r15
0x1400b95b5  lea     rbp, [rsp-3A8h]
0x1400b95bd  sub     rsp, 4A8h
0x1400b95c4  mov     rax, cs:__security_cookie
0x1400b95cb  xor     rax, rsp
0x1400b95ce  mov     [rbp+3E0h+var_50], rax
0x1400b95d5  xorps   xmm1, xmm1
0x1400b95d8  mov     rbx, rcx
0x1400b95db  xorps   xmm0, xmm0
0x1400b95de  lea     rcx, [rbp+3E0h+var_300]; void *
0x1400b95e5  xor     eax, eax
0x1400b95e7  xor     edx, edx; Val
0x1400b95e9  movups  xmmword ptr [rbp+3E0h+var_460], xmm1
0x1400b95ed  mov     r8d, 2A8h; Size
0x1400b95f3  mov     [rsp+4E0h+var_480], eax
0x1400b95f7  movups  xmmword ptr [rbp+3E0h+var_460+0Ch], xmm1
0x1400b95fb  movups  [rsp+4E0h+pBuffer], xmm0
0x1400b9600  call    memset
0x1400b9605  xorps   xmm0, xmm0
0x1400b9608  lea     rcx, [rbp+3E0h+var_410]; void *
0x1400b960c  xor     eax, eax
0x1400b960e  xor     edx, edx; Val
0x1400b9610  mov     r8d, 108h; Size
0x1400b9616  mov     [rbp+3E0h+var_420], rax
0x1400b961a  movups  [rbp+3E0h+var_440], xmm0
0x1400b961e  movups  [rbp+3E0h+var_430], xmm0
0x1400b9622  call    memset
0x1400b9627  xorps   xmm0, xmm0
0x1400b962a  xorps   xmm1, xmm1
0x1400b962d  xor     eax, eax
0x1400b962f  movups  [rsp+4E0h+var_4A0], xmm0
0x1400b9634  mov     [rsp+4E0h+var_468], eax
0x1400b9638  movups  [rsp+4E0h+var_478], xmm1
0x1400b963d  mov     r13b, 2
0x1400b9640  test    byte ptr cs:xmmword_1401A2CA0+2, r13b
0x1400b9647  jz      short loc_1400B9662
0x1400b9649  mov     edx, 0D2h
0x1400b964e  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x1400b9655  mov     ecx, 411h
0x1400b965a  mov     r9, rbx
0x1400b965d  call    WPP_SF_q
0x1400b9662  xor     r12d, r12d
0x1400b9665  cmp     [rbx+0E8h], r12b
0x1400b966c  jnz     short loc_1400B9683
0x1400b966e  xor     ecx, ecx; PerformanceFrequency
0x1400b9670  call    cs:__imp_KeQueryPerformanceCounter
0x1400b9677  nop     dword ptr [rax+rax+00h]
0x1400b967c  mov     [rbx+6C0h], rax
0x1400b9683  lea     r14, [rbx+1B8h]
0x1400b968a  mov     edx, 4; ulAttribute
0x1400b968f  mov     rcx, r14; phContext
0x1400b9692  lea     r8, [rsp+4E0h+pBuffer]; pBuffer
0x1400b9697  call    cs:__imp_QueryContextAttributesW
0x1400b969e  nop     dword ptr [rax+rax+00h]
0x1400b96a3  mov     esi, eax
0x1400b96a5  test    eax, eax
0x1400b96a7  jz      loc_1400B976A
0x1400b96ad  mov     r10, [rbx+6A0h]
0x1400b96b4  test    byte ptr [r10+6E3h], 8
0x1400b96bc  jz      short loc_1400B9732
0x1400b96be  cmp     [r10+6F0h], r12
0x1400b96c5  jz      short loc_1400B9701
0x1400b96c7  movzx   r9d, word ptr [rbx+670h]
0x1400b96cf  lea     r8, [rbx+74h]
0x1400b96d3  mov     rax, [rbx+678h]
0x1400b96da  lea     rdx, [rbx+58h]
0x1400b96de  mov     [rsp+4E0h+var_4A8], r12d
0x1400b96e3  mov     rcx, r10
0x1400b96e6  mov     [rsp+4E0h+var_4B0], r12
0x1400b96eb  mov     dword ptr [rsp+4E0h+var_4B8], r9d
0x1400b96f0  xor     r9d, r9d
0x1400b96f3  mov     [rsp+4E0h+var_4C0], rax
0x1400b96f8  call    UlEtwEvaluateFilter
0x1400b96fd  test    al, al
0x1400b96ff  jz      short loc_1400B9732
0x1400b9701  mov     rcx, [rbx+6A0h]
0x1400b9708  lea     rax, aAttributeStrea; "Attribute_StreamSizes"
0x1400b970f  mov     [rsp+4E0h+var_4B8], rax
0x1400b9714  lea     r8, [rbx+48h]
0x1400b9718  add     rcx, 698h
0x1400b971f  mov     dword ptr [rsp+4E0h+var_4C0], esi
0x1400b9723  mov     r9, rbx
0x1400b9726  lea     rdx, HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE
0x1400b972d  call    McTemplateK0pqs_EtwWriteTransfer
0x1400b9732  mov     ecx, esi
0x1400b9734  call    UxSslMapSecurityStatusToErrorNtStatus
0x1400b9739  mov     edi, eax
0x1400b973b  test    byte ptr cs:xmmword_1401A2C90+2, r13b
0x1400b9742  jz      loc_1400B9DE5
0x1400b9748  mov     edx, 0D3h
0x1400b974d  mov     dword ptr [rsp+4E0h+var_4C0], esi
0x1400b9751  mov     ecx, 211h
0x1400b9756  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x1400b975d  mov     r9, rbx
0x1400b9760  call    WPP_SF_qD
0x1400b9765  jmp     loc_1400B9DE5
0x1400b976a  mov     eax, dword ptr [rsp+4E0h+pBuffer]
0x1400b976e  lea     r8, [rbp+3E0h+var_460]; pBuffer
0x1400b9772  mov     [rbx+1C8h], eax
0x1400b9778  mov     ecx, 4000h
0x1400b977d  mov     eax, dword ptr [rsp+4E0h+pBuffer+4]
0x1400b9781  mov     edx, 5Ah ; 'Z'; ulAttribute
0x1400b9786  mov     [rbx+1CCh], eax
0x1400b978c  mov     eax, dword ptr [rsp+4E0h+pBuffer+8]
0x1400b9790  cmp     eax, ecx
0x1400b9792  cmova   eax, ecx
0x1400b9795  mov     rcx, r14; phContext
0x1400b9798  mov     [rbx+1D0h], eax
0x1400b979e  call    cs:__imp_QueryContextAttributesW
0x1400b97a5  nop     dword ptr [rax+rax+00h]
0x1400b97aa  mov     esi, eax
0x1400b97ac  test    eax, eax
0x1400b97ae  jz      loc_1400B9859
0x1400b97b4  mov     r10, [rbx+6A0h]
0x1400b97bb  test    byte ptr [r10+6E3h], 8
0x1400b97c3  jz      short loc_1400B9839
0x1400b97c5  cmp     [r10+6F0h], r12
0x1400b97cc  jz      short loc_1400B9808
0x1400b97ce  movzx   r9d, word ptr [rbx+670h]
0x1400b97d6  lea     r8, [rbx+74h]
0x1400b97da  mov     rax, [rbx+678h]
0x1400b97e1  lea     rdx, [rbx+58h]
0x1400b97e5  mov     [rsp+4E0h+var_4A8], r12d
0x1400b97ea  mov     rcx, r10
0x1400b97ed  mov     [rsp+4E0h+var_4B0], r12
0x1400b97f2  mov     dword ptr [rsp+4E0h+var_4B8], r9d
0x1400b97f7  xor     r9d, r9d
0x1400b97fa  mov     [rsp+4E0h+var_4C0], rax
0x1400b97ff  call    UlEtwEvaluateFilter
0x1400b9804  test    al, al
0x1400b9806  jz      short loc_1400B9839
0x1400b9808  mov     rcx, [rbx+6A0h]
0x1400b980f  lea     rax, aAttributeConni; "Attribute_ConnInfo"
0x1400b9816  mov     [rsp+4E0h+var_4B8], rax
0x1400b981b  lea     r8, [rbx+48h]
0x1400b981f  add     rcx, 698h
0x1400b9826  mov     dword ptr [rsp+4E0h+var_4C0], esi
0x1400b982a  mov     r9, rbx
0x1400b982d  lea     rdx, HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE
0x1400b9834  call    McTemplateK0pqs_EtwWriteTransfer
0x1400b9839  mov     ecx, esi
0x1400b983b  call    UxSslMapSecurityStatusToErrorNtStatus
0x1400b9840  mov     edi, eax
0x1400b9842  test    byte ptr cs:xmmword_1401A2C90+2, r13b
0x1400b9849  jz      loc_1400B9DE5
0x1400b984f  mov     edx, 0D4h
0x1400b9854  jmp     loc_1400B974D
0x1400b9859  movups  xmm0, xmmword ptr [rbp+3E0h+var_460]
0x1400b985d  lea     r8, [rbp+3E0h+var_300]; pBuffer
0x1400b9864  mov     edx, 64h ; 'd'; ulAttribute
0x1400b9869  movups  xmm1, xmmword ptr [rbp+3E0h+var_460+0Ch]
0x1400b986d  mov     rcx, r14; phContext
0x1400b9870  movups  xmmword ptr [rbx+1D4h], xmm0
0x1400b9877  movups  xmmword ptr [rbx+1E0h], xmm1
0x1400b987e  call    cs:__imp_QueryContextAttributesW
0x1400b9885  nop     dword ptr [rax+rax+00h]
0x1400b988a  mov     esi, eax
0x1400b988c  test    eax, eax
0x1400b988e  jz      loc_1400B9939
0x1400b9894  mov     r10, [rbx+6A0h]
0x1400b989b  test    byte ptr [r10+6E3h], 8
0x1400b98a3  jz      short loc_1400B9919
0x1400b98a5  cmp     [r10+6F0h], r12
0x1400b98ac  jz      short loc_1400B98E8
0x1400b98ae  movzx   r9d, word ptr [rbx+670h]
0x1400b98b6  lea     r8, [rbx+74h]
0x1400b98ba  mov     rax, [rbx+678h]
0x1400b98c1  lea     rdx, [rbx+58h]
0x1400b98c5  mov     [rsp+4E0h+var_4A8], r12d
0x1400b98ca  mov     rcx, r10
0x1400b98cd  mov     [rsp+4E0h+var_4B0], r12
0x1400b98d2  mov     dword ptr [rsp+4E0h+var_4B8], r9d
0x1400b98d7  xor     r9d, r9d
0x1400b98da  mov     [rsp+4E0h+var_4C0], rax
0x1400b98df  call    UlEtwEvaluateFilter
0x1400b98e4  test    al, al
0x1400b98e6  jz      short loc_1400B9919
0x1400b98e8  mov     rcx, [rbx+6A0h]
0x1400b98ef  lea     rax, aAttributeCiphe; "Attribute_CipherInfo"
0x1400b98f6  mov     [rsp+4E0h+var_4B8], rax
0x1400b98fb  lea     r8, [rbx+48h]
0x1400b98ff  add     rcx, 698h
0x1400b9906  mov     dword ptr [rsp+4E0h+var_4C0], esi
0x1400b990a  mov     r9, rbx
0x1400b990d  lea     rdx, HTTP_EVENT_SSL_QUERY_CIPHER_INFO_FAILURE
0x1400b9914  call    McTemplateK0pqs_EtwWriteTransfer
0x1400b9919  mov     ecx, esi
0x1400b991b  call    UxSslMapSecurityStatusToErrorNtStatus
0x1400b9920  mov     edi, eax
0x1400b9922  test    byte ptr cs:xmmword_1401A2C90+2, r13b
0x1400b9929  jz      loc_1400B9DE5
0x1400b992f  mov     edx, 0D5h
0x1400b9934  jmp     loc_1400B974D
0x1400b9939  mov     edx, 5
0x1400b993e  lea     rcx, [rbx+1F0h]
0x1400b9945  lea     rax, [rbp+3E0h+var_300]
0x1400b994c  lea     r8d, [rdx+7Bh]
0x1400b9950  movups  xmm0, xmmword ptr [rax]
0x1400b9953  movups  xmm1, xmmword ptr [rax+10h]
0x1400b9957  movups  xmmword ptr [rcx], xmm0
0x1400b995a  movups  xmm0, xmmword ptr [rax+20h]
0x1400b995e  movups  xmmword ptr [rcx+10h], xmm1
0x1400b9962  movups  xmm1, xmmword ptr [rax+30h]
0x1400b9966  movups  xmmword ptr [rcx+20h], xmm0
0x1400b996a  movups  xmm0, xmmword ptr [rax+40h]
0x1400b996e  movups  xmmword ptr [rcx+30h], xmm1
0x1400b9972  movups  xmm1, xmmword ptr [rax+50h]
0x1400b9976  movups  xmmword ptr [rcx+40h], xmm0
0x1400b997a  movups  xmm0, xmmword ptr [rax+60h]
0x1400b997e  movups  xmmword ptr [rcx+50h], xmm1
0x1400b9982  movups  xmm1, xmmword ptr [rax+70h]
0x1400b9986  add     rax, r8
0x1400b9989  movups  xmmword ptr [rcx+60h], xmm0
0x1400b998d  movups  xmmword ptr [rcx+70h], xmm1
0x1400b9991  add     rcx, r8
0x1400b9994  sub     rdx, 1
0x1400b9998  jnz     short loc_1400B9950
0x1400b999a  movups  xmm0, xmmword ptr [rax]
0x1400b999d  lea     r8, [rbp+3E0h+var_440]; pBuffer
0x1400b99a1  mov     edx, 5Dh ; ']'; ulAttribute
0x1400b99a6  movups  xmm1, xmmword ptr [rax+10h]
0x1400b99aa  mov     rax, [rax+20h]
0x1400b99ae  movups  xmmword ptr [rcx], xmm0
0x1400b99b1  movups  xmmword ptr [rcx+10h], xmm1
0x1400b99b5  mov     [rcx+20h], rax
0x1400b99b9  mov     rcx, r14; phContext
0x1400b99bc  call    cs:__imp_QueryContextAttributesW
0x1400b99c3  nop     dword ptr [rax+rax+00h]
0x1400b99c8  mov     esi, eax
0x1400b99ca  test    eax, eax
0x1400b99cc  jz      loc_1400B9A77
0x1400b99d2  mov     r10, [rbx+6A0h]
0x1400b99d9  test    byte ptr [r10+6E3h], 8
0x1400b99e1  jz      short loc_1400B9A57
0x1400b99e3  cmp     [r10+6F0h], r12
0x1400b99ea  jz      short loc_1400B9A26
0x1400b99ec  movzx   r9d, word ptr [rbx+670h]
0x1400b99f4  lea     r8, [rbx+74h]
0x1400b99f8  mov     rax, [rbx+678h]
0x1400b99ff  lea     rdx, [rbx+58h]
0x1400b9a03  mov     [rsp+4E0h+var_4A8], r12d
0x1400b9a08  mov     rcx, r10
0x1400b9a0b  mov     [rsp+4E0h+var_4B0], r12
0x1400b9a10  mov     dword ptr [rsp+4E0h+var_4B8], r9d
0x1400b9a15  xor     r9d, r9d
0x1400b9a18  mov     [rsp+4E0h+var_4C0], rax
0x1400b9a1d  call    UlEtwEvaluateFilter
0x1400b9a22  test    al, al
0x1400b9a24  jz      short loc_1400B9A57
0x1400b9a26  mov     rcx, [rbx+6A0h]
0x1400b9a2d  lea     rax, aAttributeSessi; "Attribute_SessionInfo"
0x1400b9a34  mov     [rsp+4E0h+var_4B8], rax
0x1400b9a39  lea     r8, [rbx+48h]
0x1400b9a3d  add     rcx, 698h
0x1400b9a44  mov     dword ptr [rsp+4E0h+var_4C0], esi
0x1400b9a48  mov     r9, rbx
0x1400b9a4b  lea     rdx, HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE
0x1400b9a52  call    McTemplateK0pqs_EtwWriteTransfer
0x1400b9a57  mov     ecx, esi
0x1400b9a59  call    UxSslMapSecurityStatusToErrorNtStatus
0x1400b9a5e  mov     edi, eax
0x1400b9a60  test    byte ptr cs:xmmword_1401A2C90+2, r13b
0x1400b9a67  jz      loc_1400B9DE5
0x1400b9a6d  mov     edx, 0D6h
0x1400b9a72  jmp     loc_1400B974D
0x1400b9a77  mov     eax, dword ptr [rbp+3E0h+var_440]
0x1400b9a7a  mov     r15b, 1
0x1400b9a7d  and     al, r15b
0x1400b9a80  mov     rcx, rbx
0x1400b9a83  mov     [rbx+498h], al
0x1400b9a89  call    UxpSslQuerySslConnectionPostHandshakeClientAuth
0x1400b9a8e  mov     edi, eax
0x1400b9a90  test    eax, eax
0x1400b9a92  js      loc_1400B9DE5
0x1400b9a98  cmp     [rbx+0E8h], r12b
0x1400b9a9f  jnz     loc_1400B9B54
0x1400b9aa5  lea     r8, [rbp+3E0h+var_410]; pBuffer
0x1400b9aa9  mov     edx, 23h ; '#'; ulAttribute
0x1400b9aae  mov     rcx, r14; phContext
0x1400b9ab1  call    cs:__imp_QueryContextAttributesW
0x1400b9ab8  nop     dword ptr [rax+rax+00h]
0x1400b9abd  mov     esi, eax
0x1400b9abf  test    eax, eax
0x1400b9ac1  jnz     short loc_1400B9B34
0x1400b9ac3  lea     rdx, [rbp+3E0h+var_410]
0x1400b9ac7  mov     rcx, rbx
0x1400b9aca  call    UxpSslProcessApplicationProtocolQuery
0x1400b9acf  mov     edi, eax
0x1400b9ad1  test    eax, eax
0x1400b9ad3  jns     short loc_1400B9AF0
0x1400b9ad5  test    byte ptr cs:xmmword_1401A2C90+2, r13b
0x1400b9adc  jz      loc_1400B9DE5
0x1400b9ae2  mov     edx, 0D8h
  ... truncated ...
```
