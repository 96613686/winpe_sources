# UxpSslQuerySslConnectionInfo

- ea: `0x1400b94c8`
- end: `0x1400b9d75`
- name: `UxpSslQuerySslConnectionInfo`
- size: `2221`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140079aa4`

## callees

- `0x140092f60`
- `0x140094520`
- `0x140094764`
- `0x140094b00`
- `0x140098b00`
- `0x1400a9b00`
- `0x1400af720`
- `0x1400b94c8`
- `0x1400b9d7c`
- `0x140106574`
- `0x140167810`
- `0x140167c40`
- `0x1401c3f78`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x1400b9590`
- `HAL!KeQueryPerformanceCounter` at `0x1400b9a93`
- `HAL!KeQueryPerformanceCounter` at `0x1400b9abf`
- `HAL!KeQueryPerformanceCounter` at `0x1400b9d1a`
- `HAL!KeQueryPerformanceCounter` at `0x1400b9590`
- `HAL!KeQueryPerformanceCounter` at `0x1400b9a93`
- `HAL!KeQueryPerformanceCounter` at `0x1400b9abf`
- `HAL!KeQueryPerformanceCounter` at `0x1400b9d1a`
- `ksecdd!QueryContextAttributesW` at `0x1400b95b7`
- `ksecdd!QueryContextAttributesW` at `0x1400b96be`
- `ksecdd!QueryContextAttributesW` at `0x1400b979e`
- `ksecdd!QueryContextAttributesW` at `0x1400b98dc`
- `ksecdd!QueryContextAttributesW` at `0x1400b99d1`
- `ksecdd!QueryContextAttributesW` at `0x1400b9adf`
- `ksecdd!QueryContextAttributesW` at `0x1400b9b37`
- `ksecdd!QueryContextAttributesW` at `0x1400b95b7`
- `ksecdd!QueryContextAttributesW` at `0x1400b96be`
- `ksecdd!QueryContextAttributesW` at `0x1400b979e`
- `ksecdd!QueryContextAttributesW` at `0x1400b98dc`
- `ksecdd!QueryContextAttributesW` at `0x1400b99d1`
- `ksecdd!QueryContextAttributesW` at `0x1400b9adf`
- `ksecdd!QueryContextAttributesW` at `0x1400b9b37`
- `ksecdd!QuerySecurityContextToken` at `0x1400b9c25`
- `ksecdd!QuerySecurityContextToken` at `0x1400b9c25`

## string_xrefs

- `0x1400b9628`: `Attribute_StreamSizes`
- `0x1400b9c94`: `ContextToken`

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
0x1400b94c8  push    rbp
0x1400b94ca  push    rbx
0x1400b94cb  push    rsi
0x1400b94cc  push    rdi
0x1400b94cd  push    r12
0x1400b94cf  push    r13
0x1400b94d1  push    r14
0x1400b94d3  push    r15
0x1400b94d5  lea     rbp, [rsp-3A8h]
0x1400b94dd  sub     rsp, 4A8h
0x1400b94e4  mov     rax, cs:__security_cookie
0x1400b94eb  xor     rax, rsp
0x1400b94ee  mov     [rbp+3E0h+var_50], rax
0x1400b94f5  xorps   xmm1, xmm1
0x1400b94f8  mov     rbx, rcx
0x1400b94fb  xorps   xmm0, xmm0
0x1400b94fe  lea     rcx, [rbp+3E0h+var_300]; void *
0x1400b9505  xor     eax, eax
0x1400b9507  xor     edx, edx; Val
0x1400b9509  movups  xmmword ptr [rbp+3E0h+var_460], xmm1
0x1400b950d  mov     r8d, 2A8h; Size
0x1400b9513  mov     [rsp+4E0h+var_480], eax
0x1400b9517  movups  xmmword ptr [rbp+3E0h+var_460+0Ch], xmm1
0x1400b951b  movups  [rsp+4E0h+pBuffer], xmm0
0x1400b9520  call    memset
0x1400b9525  xorps   xmm0, xmm0
0x1400b9528  lea     rcx, [rbp+3E0h+var_410]; void *
0x1400b952c  xor     eax, eax
0x1400b952e  xor     edx, edx; Val
0x1400b9530  mov     r8d, 108h; Size
0x1400b9536  mov     [rbp+3E0h+var_420], rax
0x1400b953a  movups  [rbp+3E0h+var_440], xmm0
0x1400b953e  movups  [rbp+3E0h+var_430], xmm0
0x1400b9542  call    memset
0x1400b9547  xorps   xmm0, xmm0
0x1400b954a  xorps   xmm1, xmm1
0x1400b954d  xor     eax, eax
0x1400b954f  movups  [rsp+4E0h+var_4A0], xmm0
0x1400b9554  mov     [rsp+4E0h+var_468], eax
0x1400b9558  movups  [rsp+4E0h+var_478], xmm1
0x1400b955d  mov     r13b, 2
0x1400b9560  test    byte ptr cs:xmmword_1401A2CA0+2, r13b
0x1400b9567  jz      short loc_1400B9582
0x1400b9569  mov     edx, 0D2h
0x1400b956e  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x1400b9575  mov     ecx, 411h
0x1400b957a  mov     r9, rbx
0x1400b957d  call    WPP_SF_q
0x1400b9582  xor     r12d, r12d
0x1400b9585  cmp     [rbx+0E8h], r12b
0x1400b958c  jnz     short loc_1400B95A3
0x1400b958e  xor     ecx, ecx; PerformanceFrequency
0x1400b9590  call    cs:__imp_KeQueryPerformanceCounter
0x1400b9597  nop     dword ptr [rax+rax+00h]
0x1400b959c  mov     [rbx+6C0h], rax
0x1400b95a3  lea     r14, [rbx+1B8h]
0x1400b95aa  mov     edx, 4; ulAttribute
0x1400b95af  mov     rcx, r14; phContext
0x1400b95b2  lea     r8, [rsp+4E0h+pBuffer]; pBuffer
0x1400b95b7  call    cs:__imp_QueryContextAttributesW
0x1400b95be  nop     dword ptr [rax+rax+00h]
0x1400b95c3  mov     esi, eax
0x1400b95c5  test    eax, eax
0x1400b95c7  jz      loc_1400B968A
0x1400b95cd  mov     r10, [rbx+6A0h]
0x1400b95d4  test    byte ptr [r10+6E3h], 8
0x1400b95dc  jz      short loc_1400B9652
0x1400b95de  cmp     [r10+6F0h], r12
0x1400b95e5  jz      short loc_1400B9621
0x1400b95e7  movzx   r9d, word ptr [rbx+670h]
0x1400b95ef  lea     r8, [rbx+74h]
0x1400b95f3  mov     rax, [rbx+678h]
0x1400b95fa  lea     rdx, [rbx+58h]
0x1400b95fe  mov     [rsp+4E0h+var_4A8], r12d
0x1400b9603  mov     rcx, r10
0x1400b9606  mov     [rsp+4E0h+var_4B0], r12
0x1400b960b  mov     dword ptr [rsp+4E0h+var_4B8], r9d
0x1400b9610  xor     r9d, r9d
0x1400b9613  mov     [rsp+4E0h+var_4C0], rax
0x1400b9618  call    UlEtwEvaluateFilter
0x1400b961d  test    al, al
0x1400b961f  jz      short loc_1400B9652
0x1400b9621  mov     rcx, [rbx+6A0h]
0x1400b9628  lea     rax, aAttributeStrea; "Attribute_StreamSizes"
0x1400b962f  mov     [rsp+4E0h+var_4B8], rax
0x1400b9634  lea     r8, [rbx+48h]
0x1400b9638  add     rcx, 698h
0x1400b963f  mov     dword ptr [rsp+4E0h+var_4C0], esi
0x1400b9643  mov     r9, rbx
0x1400b9646  lea     rdx, HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE
0x1400b964d  call    McTemplateK0pqs_EtwWriteTransfer
0x1400b9652  mov     ecx, esi
0x1400b9654  call    UxSslMapSecurityStatusToErrorNtStatus
0x1400b9659  mov     edi, eax
0x1400b965b  test    byte ptr cs:xmmword_1401A2C90+2, r13b
0x1400b9662  jz      loc_1400B9D05
0x1400b9668  mov     edx, 0D3h
0x1400b966d  mov     dword ptr [rsp+4E0h+var_4C0], esi
0x1400b9671  mov     ecx, 211h
0x1400b9676  lea     r8, WPP_6033a49e77e7395416619077875677ff_Traceguids
0x1400b967d  mov     r9, rbx
0x1400b9680  call    WPP_SF_qD
0x1400b9685  jmp     loc_1400B9D05
0x1400b968a  mov     eax, dword ptr [rsp+4E0h+pBuffer]
0x1400b968e  lea     r8, [rbp+3E0h+var_460]; pBuffer
0x1400b9692  mov     [rbx+1C8h], eax
0x1400b9698  mov     ecx, 4000h
0x1400b969d  mov     eax, dword ptr [rsp+4E0h+pBuffer+4]
0x1400b96a1  mov     edx, 5Ah ; 'Z'; ulAttribute
0x1400b96a6  mov     [rbx+1CCh], eax
0x1400b96ac  mov     eax, dword ptr [rsp+4E0h+pBuffer+8]
0x1400b96b0  cmp     eax, ecx
0x1400b96b2  cmova   eax, ecx
0x1400b96b5  mov     rcx, r14; phContext
0x1400b96b8  mov     [rbx+1D0h], eax
0x1400b96be  call    cs:__imp_QueryContextAttributesW
0x1400b96c5  nop     dword ptr [rax+rax+00h]
0x1400b96ca  mov     esi, eax
0x1400b96cc  test    eax, eax
0x1400b96ce  jz      loc_1400B9779
0x1400b96d4  mov     r10, [rbx+6A0h]
0x1400b96db  test    byte ptr [r10+6E3h], 8
0x1400b96e3  jz      short loc_1400B9759
0x1400b96e5  cmp     [r10+6F0h], r12
0x1400b96ec  jz      short loc_1400B9728
0x1400b96ee  movzx   r9d, word ptr [rbx+670h]
0x1400b96f6  lea     r8, [rbx+74h]
0x1400b96fa  mov     rax, [rbx+678h]
0x1400b9701  lea     rdx, [rbx+58h]
0x1400b9705  mov     [rsp+4E0h+var_4A8], r12d
0x1400b970a  mov     rcx, r10
0x1400b970d  mov     [rsp+4E0h+var_4B0], r12
0x1400b9712  mov     dword ptr [rsp+4E0h+var_4B8], r9d
0x1400b9717  xor     r9d, r9d
0x1400b971a  mov     [rsp+4E0h+var_4C0], rax
0x1400b971f  call    UlEtwEvaluateFilter
0x1400b9724  test    al, al
0x1400b9726  jz      short loc_1400B9759
0x1400b9728  mov     rcx, [rbx+6A0h]
0x1400b972f  lea     rax, aAttributeConni; "Attribute_ConnInfo"
0x1400b9736  mov     [rsp+4E0h+var_4B8], rax
0x1400b973b  lea     r8, [rbx+48h]
0x1400b973f  add     rcx, 698h
0x1400b9746  mov     dword ptr [rsp+4E0h+var_4C0], esi
0x1400b974a  mov     r9, rbx
0x1400b974d  lea     rdx, HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE
0x1400b9754  call    McTemplateK0pqs_EtwWriteTransfer
0x1400b9759  mov     ecx, esi
0x1400b975b  call    UxSslMapSecurityStatusToErrorNtStatus
0x1400b9760  mov     edi, eax
0x1400b9762  test    byte ptr cs:xmmword_1401A2C90+2, r13b
0x1400b9769  jz      loc_1400B9D05
0x1400b976f  mov     edx, 0D4h
0x1400b9774  jmp     loc_1400B966D
0x1400b9779  movups  xmm0, xmmword ptr [rbp+3E0h+var_460]
0x1400b977d  lea     r8, [rbp+3E0h+var_300]; pBuffer
0x1400b9784  mov     edx, 64h ; 'd'; ulAttribute
0x1400b9789  movups  xmm1, xmmword ptr [rbp+3E0h+var_460+0Ch]
0x1400b978d  mov     rcx, r14; phContext
0x1400b9790  movups  xmmword ptr [rbx+1D4h], xmm0
0x1400b9797  movups  xmmword ptr [rbx+1E0h], xmm1
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
0x1400b980f  lea     rax, aAttributeCiphe; "Attribute_CipherInfo"
0x1400b9816  mov     [rsp+4E0h+var_4B8], rax
0x1400b981b  lea     r8, [rbx+48h]
0x1400b981f  add     rcx, 698h
0x1400b9826  mov     dword ptr [rsp+4E0h+var_4C0], esi
0x1400b982a  mov     r9, rbx
0x1400b982d  lea     rdx, HTTP_EVENT_SSL_QUERY_CIPHER_INFO_FAILURE
0x1400b9834  call    McTemplateK0pqs_EtwWriteTransfer
0x1400b9839  mov     ecx, esi
0x1400b983b  call    UxSslMapSecurityStatusToErrorNtStatus
0x1400b9840  mov     edi, eax
0x1400b9842  test    byte ptr cs:xmmword_1401A2C90+2, r13b
0x1400b9849  jz      loc_1400B9D05
0x1400b984f  mov     edx, 0D5h
0x1400b9854  jmp     loc_1400B966D
0x1400b9859  mov     edx, 5
0x1400b985e  lea     rcx, [rbx+1F0h]
0x1400b9865  lea     rax, [rbp+3E0h+var_300]
0x1400b986c  lea     r8d, [rdx+7Bh]
0x1400b9870  movups  xmm0, xmmword ptr [rax]
0x1400b9873  movups  xmm1, xmmword ptr [rax+10h]
0x1400b9877  movups  xmmword ptr [rcx], xmm0
0x1400b987a  movups  xmm0, xmmword ptr [rax+20h]
0x1400b987e  movups  xmmword ptr [rcx+10h], xmm1
0x1400b9882  movups  xmm1, xmmword ptr [rax+30h]
0x1400b9886  movups  xmmword ptr [rcx+20h], xmm0
0x1400b988a  movups  xmm0, xmmword ptr [rax+40h]
0x1400b988e  movups  xmmword ptr [rcx+30h], xmm1
0x1400b9892  movups  xmm1, xmmword ptr [rax+50h]
0x1400b9896  movups  xmmword ptr [rcx+40h], xmm0
0x1400b989a  movups  xmm0, xmmword ptr [rax+60h]
0x1400b989e  movups  xmmword ptr [rcx+50h], xmm1
0x1400b98a2  movups  xmm1, xmmword ptr [rax+70h]
0x1400b98a6  add     rax, r8
0x1400b98a9  movups  xmmword ptr [rcx+60h], xmm0
0x1400b98ad  movups  xmmword ptr [rcx+70h], xmm1
0x1400b98b1  add     rcx, r8
0x1400b98b4  sub     rdx, 1
0x1400b98b8  jnz     short loc_1400B9870
0x1400b98ba  movups  xmm0, xmmword ptr [rax]
0x1400b98bd  lea     r8, [rbp+3E0h+var_440]; pBuffer
0x1400b98c1  mov     edx, 5Dh ; ']'; ulAttribute
0x1400b98c6  movups  xmm1, xmmword ptr [rax+10h]
0x1400b98ca  mov     rax, [rax+20h]
0x1400b98ce  movups  xmmword ptr [rcx], xmm0
0x1400b98d1  movups  xmmword ptr [rcx+10h], xmm1
0x1400b98d5  mov     [rcx+20h], rax
0x1400b98d9  mov     rcx, r14; phContext
0x1400b98dc  call    cs:__imp_QueryContextAttributesW
0x1400b98e3  nop     dword ptr [rax+rax+00h]
0x1400b98e8  mov     esi, eax
0x1400b98ea  test    eax, eax
0x1400b98ec  jz      loc_1400B9997
0x1400b98f2  mov     r10, [rbx+6A0h]
0x1400b98f9  test    byte ptr [r10+6E3h], 8
0x1400b9901  jz      short loc_1400B9977
0x1400b9903  cmp     [r10+6F0h], r12
0x1400b990a  jz      short loc_1400B9946
0x1400b990c  movzx   r9d, word ptr [rbx+670h]
0x1400b9914  lea     r8, [rbx+74h]
0x1400b9918  mov     rax, [rbx+678h]
0x1400b991f  lea     rdx, [rbx+58h]
0x1400b9923  mov     [rsp+4E0h+var_4A8], r12d
0x1400b9928  mov     rcx, r10
0x1400b992b  mov     [rsp+4E0h+var_4B0], r12
0x1400b9930  mov     dword ptr [rsp+4E0h+var_4B8], r9d
0x1400b9935  xor     r9d, r9d
0x1400b9938  mov     [rsp+4E0h+var_4C0], rax
0x1400b993d  call    UlEtwEvaluateFilter
0x1400b9942  test    al, al
0x1400b9944  jz      short loc_1400B9977
0x1400b9946  mov     rcx, [rbx+6A0h]
0x1400b994d  lea     rax, aAttributeSessi; "Attribute_SessionInfo"
0x1400b9954  mov     [rsp+4E0h+var_4B8], rax
0x1400b9959  lea     r8, [rbx+48h]
0x1400b995d  add     rcx, 698h
0x1400b9964  mov     dword ptr [rsp+4E0h+var_4C0], esi
0x1400b9968  mov     r9, rbx
0x1400b996b  lea     rdx, HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE
0x1400b9972  call    McTemplateK0pqs_EtwWriteTransfer
0x1400b9977  mov     ecx, esi
0x1400b9979  call    UxSslMapSecurityStatusToErrorNtStatus
0x1400b997e  mov     edi, eax
0x1400b9980  test    byte ptr cs:xmmword_1401A2C90+2, r13b
0x1400b9987  jz      loc_1400B9D05
0x1400b998d  mov     edx, 0D6h
0x1400b9992  jmp     loc_1400B966D
0x1400b9997  mov     eax, dword ptr [rbp+3E0h+var_440]
0x1400b999a  mov     r15b, 1
0x1400b999d  and     al, r15b
0x1400b99a0  mov     rcx, rbx
0x1400b99a3  mov     [rbx+498h], al
0x1400b99a9  call    UxpSslQuerySslConnectionPostHandshakeClientAuth
0x1400b99ae  mov     edi, eax
0x1400b99b0  test    eax, eax
0x1400b99b2  js      loc_1400B9D05
0x1400b99b8  cmp     [rbx+0E8h], r12b
0x1400b99bf  jnz     loc_1400B9A74
0x1400b99c5  lea     r8, [rbp+3E0h+var_410]; pBuffer
0x1400b99c9  mov     edx, 23h ; '#'; ulAttribute
0x1400b99ce  mov     rcx, r14; phContext
0x1400b99d1  call    cs:__imp_QueryContextAttributesW
0x1400b99d8  nop     dword ptr [rax+rax+00h]
0x1400b99dd  mov     esi, eax
0x1400b99df  test    eax, eax
0x1400b99e1  jnz     short loc_1400B9A54
0x1400b99e3  lea     rdx, [rbp+3E0h+var_410]
0x1400b99e7  mov     rcx, rbx
0x1400b99ea  call    UxpSslProcessApplicationProtocolQuery
0x1400b99ef  mov     edi, eax
0x1400b99f1  test    eax, eax
0x1400b99f3  jns     short loc_1400B9A10
0x1400b99f5  test    byte ptr cs:xmmword_1401A2C90+2, r13b
0x1400b99fc  jz      loc_1400B9D05
0x1400b9a02  mov     edx, 0D8h
  ... truncated ...
```
