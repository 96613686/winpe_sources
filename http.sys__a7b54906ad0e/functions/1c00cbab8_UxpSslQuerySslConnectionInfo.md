# UxpSslQuerySslConnectionInfo

- ea: `0x1c00cbab8`
- end: `0x1c00cbd60`
- name: `UxpSslQuerySslConnectionInfo`
- size: `680`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1c00ca9a0`

## callees

- `0x1c000f2c4`
- `0x1c001a4b0`
- `0x1c001b900`
- `0x1c00367a8`
- `0x1c0048878`
- `0x1c004935c`
- `0x1c008f570`
- `0x1c00cbab8`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x1c00cbb46`
- `HAL!KeQueryPerformanceCounter` at `0x1c00cbcf5`
- `HAL!KeQueryPerformanceCounter` at `0x1c00f6bd5`
- `HAL!KeQueryPerformanceCounter` at `0x1c00f6db3`
- `HAL!KeQueryPerformanceCounter` at `0x1c00cbb46`
- `HAL!KeQueryPerformanceCounter` at `0x1c00cbcf5`
- `HAL!KeQueryPerformanceCounter` at `0x1c00f6bd5`
- `HAL!KeQueryPerformanceCounter` at `0x1c00f6db3`
- `ksecdd!FreeContextBuffer` at `0x1c00f6b79`
- `ksecdd!FreeContextBuffer` at `0x1c00f6b79`
- `ksecdd!QuerySecurityContextToken` at `0x1c00f6d01`
- `ksecdd!QuerySecurityContextToken` at `0x1c00f6d01`
- `ksecdd!QueryContextAttributesW` at `0x1c00cbb6c`
- `ksecdd!QueryContextAttributesW` at `0x1c00cbbb3`
- `ksecdd!QueryContextAttributesW` at `0x1c00cbc10`
- `ksecdd!QueryContextAttributesW` at `0x1c00cbc51`
- `ksecdd!QueryContextAttributesW` at `0x1c00cbcad`
- `ksecdd!QueryContextAttributesW` at `0x1c00f6b13`
- `ksecdd!QueryContextAttributesW` at `0x1c00f6bf5`
- `ksecdd!QueryContextAttributesW` at `0x1c00f6c4b`
- `ksecdd!QueryContextAttributesW` at `0x1c00cbb6c`
- `ksecdd!QueryContextAttributesW` at `0x1c00cbbb3`
- `ksecdd!QueryContextAttributesW` at `0x1c00cbc10`
- `ksecdd!QueryContextAttributesW` at `0x1c00cbc51`
- `ksecdd!QueryContextAttributesW` at `0x1c00cbcad`
- `ksecdd!QueryContextAttributesW` at `0x1c00f6b13`
- `ksecdd!QueryContextAttributesW` at `0x1c00f6bf5`
- `ksecdd!QueryContextAttributesW` at `0x1c00f6c4b`

## string_xrefs

- `0x1c00f69b1`: `Attribute_StreamSizes`
- `0x1c00f6d46`: `ContextToken`

## pseudocode

```c
__int64 __fastcall UxpSslQuerySslConnectionInfo(__int64 a1)
{
  unsigned int v2; // r14d
  int v3; // eax
  int v4; // edi
  __int64 v5; // xmm1_8
  int v6; // eax
  char v7; // r12
  unsigned int ContextAttributesW; // eax
  int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // r14d
  unsigned int v12; // eax
  __int128 v13; // xmm1
  __int64 v14; // xmm0_8
  __int64 v16; // rcx
  __int64 v17; // r9
  unsigned __int8 *v18; // rax
  unsigned int v19; // eax
  __int64 v20; // rcx
  __m128i v21; // xmm0
  int v22; // ecx
  unsigned int SecurityContextToken; // edi
  __m128i v24; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v25; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v26; // [rsp+58h] [rbp-B0h]
  __int64 v27; // [rsp+68h] [rbp-A0h]
  __int128 v28; // [rsp+70h] [rbp-98h] BYREF
  __int64 v29; // [rsp+80h] [rbp-88h]
  char v30; // [rsp+88h] [rbp-80h]
  int v31; // [rsp+89h] [rbp-7Fh]
  __int16 v32; // [rsp+8Dh] [rbp-7Bh]
  char v33; // [rsp+8Fh] [rbp-79h]
  __int128 pBuffer; // [rsp+90h] [rbp-78h] BYREF
  int v35; // [rsp+A0h] [rbp-68h]
  _BYTE v36[20]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v37; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v38; // [rsp+D0h] [rbp-38h]
  int v39; // [rsp+D8h] [rbp-30h]
  _BYTE v40[272]; // [rsp+E8h] [rbp-20h] BYREF

  v38 = 0;
  v39 = 0;
  v27 = 0;
  v35 = 0;
  v24 = 0;
  v37 = 0;
  memset(v36, 0, sizeof(v36));
  v25 = 0;
  v26 = 0;
  pBuffer = 0;
  memset(v40, 0, 0x108u);
  if ( !*(_BYTE *)(a1 + 232) )
    *(LARGE_INTEGER *)(a1 + 992) = KeQueryPerformanceCounter(0);
  v2 = QueryContextAttributesW((PCtxtHandle)(a1 + 440), 4u, &pBuffer);
  if ( v2 )
  {
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 960) + 1568LL) )
    {
      v29 = *(_QWORD *)(a1 + 960);
      v31 = 0;
      v32 = 0;
      v33 = 0;
      v28 = (unsigned __int64)(a1 + 72);
      v30 = 0;
      McTemplateK0pqs_UlEtwWriteEventWrapper(
        a1 + 72,
        (unsigned int)HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE,
        (unsigned int)&v28,
        a1,
        v2,
        (__int64)"Attribute_StreamSizes");
    }
    v4 = UxSslMapSecurityStatusToNtStatus(v2);
    if ( (WPP_MAIN_CB.DeviceType & 0x10000) == 0 )
      goto LABEL_21;
    v16 = 49;
    goto LABEL_29;
  }
  *(_QWORD *)(a1 + 456) = pBuffer;
  v3 = DWORD2(pBuffer);
  if ( DWORD2(pBuffer) > 0x4000 )
    v3 = 0x4000;
  *(_DWORD *)(a1 + 464) = v3;
  v2 = QueryContextAttributesW((PCtxtHandle)(a1 + 440), 0x5Au, &v37);
  if ( v2 )
  {
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 960) + 1568LL) )
    {
      v29 = *(_QWORD *)(a1 + 960);
      v31 = 0;
      v32 = 0;
      v33 = 0;
      v28 = (unsigned __int64)(a1 + 72);
      v30 = 0;
      McTemplateK0pqs_UlEtwWriteEventWrapper(
        a1 + 72,
        (unsigned int)HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE,
        (unsigned int)&v28,
        a1,
        v2,
        (__int64)"Attribute_ConnInfo");
    }
    v4 = UxSslMapSecurityStatusToNtStatus(v2);
    if ( (WPP_MAIN_CB.DeviceType & 0x10000) == 0 )
      goto LABEL_21;
    v16 = 50;
    goto LABEL_29;
  }
  v4 = 0;
  v5 = v38;
  v6 = v39;
  v7 = 1;
  *(_OWORD *)(a1 + 468) = v37;
  *(_QWORD *)(a1 + 484) = v5;
  *(_DWORD *)(a1 + 492) = v6;
  if ( !*(_BYTE *)(a1 + 232) )
  {
    ContextAttributesW = QueryContextAttributesW((PCtxtHandle)(a1 + 440), 0x23u, v40);
    v2 = ContextAttributesW;
    if ( ContextAttributesW )
    {
      v4 = UxSslMapSecurityStatusToNtStatus(ContextAttributesW);
      if ( (WPP_MAIN_CB.DeviceType & 0x10000) == 0 )
        goto LABEL_21;
      v16 = 51;
LABEL_29:
      v17 = v2;
LABEL_30:
      WPP_SF_qD(v16, WPP_a22469013d8d37a4fc03866b4ef29eb7_Traceguids, a1, v17);
      goto LABEL_21;
    }
    v9 = UxpSslProcessApplicationProtocolQuery(a1, v40);
    v4 = v9;
    if ( v9 < 0 )
    {
      if ( (WPP_MAIN_CB.DeviceType & 0x10000) == 0 )
        goto LABEL_21;
      v16 = 52;
      v17 = (unsigned int)v9;
      goto LABEL_30;
    }
    v28 = 0;
    v10 = QueryContextAttributesW((PCtxtHandle)(a1 + 440), v2 + 109, &v28);
    v11 = v10;
    if ( v10 )
    {
      v4 = UxSslMapSecurityStatusToNtStatus(v10);
      if ( (WPP_MAIN_CB.DeviceType & 0x10000) == 0 )
        goto LABEL_12;
      v20 = 56;
    }
    else
    {
      v4 = 0;
      if ( !(_WORD)v28 || !WORD1(v28) )
        goto LABEL_12;
      if ( WORD1(v28) != 1 )
      {
        v4 = -1073741637;
        goto LABEL_12;
      }
      v18 = (unsigned __int8 *)*((_QWORD *)&v28 + 1);
      *(_BYTE *)(a1 + 392) = 1;
      *(_DWORD *)(a1 + 396) = *v18;
      v19 = QueryContextAttributesW((PCtxtHandle)(a1 + 440), 0x6Fu, (void *)(a1 + 416));
      v11 = v19;
      if ( !v19 || (v4 = UxSslMapSecurityStatusToNtStatus(v19), (WPP_MAIN_CB.DeviceType & 0x10000) == 0) )
      {
LABEL_12:
        if ( *((_QWORD *)&v28 + 1) )
          FreeContextBuffer(*((PVOID *)&v28 + 1));
        if ( v4 < 0 )
        {
          if ( (WPP_MAIN_CB.DeviceType & 0x10000) == 0 )
            goto LABEL_21;
          v16 = 53;
          v17 = (unsigned int)v4;
          goto LABEL_30;
        }
        goto LABEL_15;
      }
      v20 = 57;
    }
    WPP_SF_qD(v20, WPP_a22469013d8d37a4fc03866b4ef29eb7_Traceguids, a1, v11);
    goto LABEL_12;
  }
LABEL_15:
  if ( !*(_DWORD *)(a1 + 600) )
  {
    v12 = QueryContextAttributesW((PCtxtHandle)(a1 + 440), 0x63u, &v25);
    if ( v12 )
    {
      v4 = UxSslMapSecurityStatusToNtStatus(v12);
      goto LABEL_21;
    }
    v4 = 0;
    v13 = v26;
    *(_OWORD *)(a1 + 584) = v25;
    v14 = v27;
    *(_OWORD *)(a1 + 600) = v13;
    *(_QWORD *)(a1 + 616) = v14;
  }
  if ( !*(_BYTE *)(a1 + 232) )
    *(LARGE_INTEGER *)(a1 + 1000) = KeQueryPerformanceCounter(0);
  if ( (*(_DWORD *)(a1 + 504) & 2) != 0 )
  {
    if ( !*(_BYTE *)(a1 + 232) )
      *(LARGE_INTEGER *)(a1 + 1008) = KeQueryPerformanceCounter(0);
    if ( QueryContextAttributesW((PCtxtHandle)(a1 + 440), 0x5Fu, &v24) || !v24.m128i_i32[1] )
    {
      *(_QWORD *)(a1 + 552) = 0;
      *(_QWORD *)(a1 + 544) = 0;
    }
    else
    {
      v21 = v24;
      *(__m128i *)(a1 + 544) = v24;
      *(_DWORD *)(a1 + 508) = *(_DWORD *)_mm_srli_si128(v21, 8).m128i_i32[0];
      *(_OWORD *)&v36[4] = UxSslClientCertPolicyGuid;
      v2 = QueryContextAttributesW((PCtxtHandle)(a1 + 440), 0x61u, v36);
      if ( v2 )
      {
        if ( *(_BYTE *)(*(_QWORD *)(a1 + 960) + 1568LL) )
        {
          v29 = *(_QWORD *)(a1 + 960);
          v31 = 0;
          v32 = 0;
          v33 = 0;
          v28 = (unsigned __int64)(a1 + 72);
          v30 = 0;
          McTemplateK0pqs_UlEtwWriteEventWrapper(
            a1 + 72,
            (unsigned int)HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE,
            (unsigned int)&v28,
            a1,
            v2,
            (__int64)"Attribute_PolicyResult");
        }
        v4 = UxSslMapSecurityStatusToNtStatus(v2);
        if ( (WPP_MAIN_CB.DeviceType & 0x10000) == 0 )
          goto LABEL_21;
        v16 = 54;
        goto LABEL_29;
      }
      *(_DWORD *)(a1 + 560) = UxSslMapSecurityStatusToCertError(*(unsigned int *)v36);
      if ( (*(_BYTE *)(*(_QWORD *)(a1 + 432) + 688LL) & 1) == 0 )
        goto LABEL_21;
      SecurityContextToken = QuerySecurityContextToken((PCtxtHandle)(a1 + 440), (void **)(a1 + 568));
      if ( SecurityContextToken )
      {
        if ( *(_BYTE *)(*(_QWORD *)(a1 + 960) + 1568LL) )
        {
          v29 = *(_QWORD *)(a1 + 960);
          v31 = 0;
          v28 = (unsigned __int64)(a1 + 72);
          v32 = 0;
          v33 = 0;
          v30 = 0;
          McTemplateK0pqs_UlEtwWriteEventWrapper(
            v22,
            (unsigned int)HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE,
            (unsigned int)&v28,
            a1,
            SecurityContextToken,
            (__int64)"ContextToken");
        }
        if ( (*(_DWORD *)&WPP_MAIN_CB.StackSize & 0x10000) != 0 )
          WPP_SF_qD(55, WPP_a22469013d8d37a4fc03866b4ef29eb7_Traceguids, a1, SecurityContextToken);
        *(_QWORD *)(a1 + 568) = 0;
      }
      else
      {
        v7 = 0;
      }
      *(_BYTE *)(a1 + 576) = v7;
    }
    v4 = 0;
  }
LABEL_21:
  if ( !*(_BYTE *)(a1 + 232) && (*(_DWORD *)(a1 + 504) & 2) != 0 )
    *(LARGE_INTEGER *)(a1 + 1016) = KeQueryPerformanceCounter(0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1c00cbab8  mov     rax, rsp
0x1c00cbabb  mov     [rax+10h], rbx
0x1c00cbabf  mov     [rax+18h], rsi
0x1c00cbac3  mov     [rax+20h], rdi
0x1c00cbac7  push    rbp
0x1c00cbac8  push    r12
0x1c00cbaca  push    r13
0x1c00cbacc  push    r14
0x1c00cbace  push    r15
0x1c00cbad0  lea     rbp, [rax-128h]
0x1c00cbad7  sub     rsp, 200h
0x1c00cbade  mov     rax, cs:__security_cookie
0x1c00cbae5  xor     rax, rsp
0x1c00cbae8  mov     [rbp+120h+var_30], rax
0x1c00cbaef  xor     eax, eax
0x1c00cbaf1  xorps   xmm0, xmm0
0x1c00cbaf4  xorps   xmm1, xmm1
0x1c00cbaf7  mov     [rbp+120h+var_158], rax
0x1c00cbafb  mov     rbx, rcx
0x1c00cbafe  mov     [rbp+120h+var_150], eax
0x1c00cbb01  lea     rcx, [rbp+120h+var_140]; void *
0x1c00cbb05  mov     [rbp+120h+var_170], eax
0x1c00cbb08  xor     edx, edx; Val
0x1c00cbb0a  mov     qword ptr [rsp+220h+var_1C0], rax
0x1c00cbb0f  mov     r8d, 108h; Size
0x1c00cbb15  mov     [rbp+120h+var_188], eax
0x1c00cbb18  movups  [rsp+220h+var_1F8+8], xmm0
0x1c00cbb1d  movups  [rbp+120h+var_168], xmm1
0x1c00cbb21  movups  [rbp+120h+var_180], xmm0
0x1c00cbb25  movups  [rsp+220h+var_1E8+8], xmm1
0x1c00cbb2a  movups  xmmword ptr [rsp+220h+var_1D8+8], xmm1
0x1c00cbb2f  movups  [rbp+120h+pBuffer], xmm0
0x1c00cbb33  call    memset
0x1c00cbb38  xor     r13d, r13d
0x1c00cbb3b  cmp     [rbx+0E8h], r13b
0x1c00cbb42  jnz     short loc_1C00CBB59
0x1c00cbb44  xor     ecx, ecx; PerformanceFrequency
0x1c00cbb46  call    cs:__imp_KeQueryPerformanceCounter
0x1c00cbb4d  nop     dword ptr [rax+rax+00h]
0x1c00cbb52  mov     [rbx+3E0h], rax
0x1c00cbb59  lea     r15, [rbx+1B8h]
0x1c00cbb60  mov     edx, 4; ulAttribute
0x1c00cbb65  mov     rcx, r15; phContext
0x1c00cbb68  lea     r8, [rbp+120h+pBuffer]; pBuffer
0x1c00cbb6c  call    cs:__imp_QueryContextAttributesW
0x1c00cbb73  nop     dword ptr [rax+rax+00h]
0x1c00cbb78  mov     r14d, eax
0x1c00cbb7b  test    eax, eax
0x1c00cbb7d  jnz     loc_1C00F6998
0x1c00cbb83  mov     eax, dword ptr [rbp+120h+pBuffer]
0x1c00cbb86  lea     r8, [rbp+120h+var_168]; pBuffer
0x1c00cbb8a  mov     [rbx+1C8h], eax
0x1c00cbb90  lea     edx, [r14+5Ah]; ulAttribute
0x1c00cbb94  mov     eax, dword ptr [rbp+120h+pBuffer+4]
0x1c00cbb97  mov     ecx, 4000h
0x1c00cbb9c  mov     [rbx+1CCh], eax
0x1c00cbba2  mov     eax, dword ptr [rbp+120h+pBuffer+8]
0x1c00cbba5  cmp     eax, ecx
0x1c00cbba7  cmova   eax, ecx
0x1c00cbbaa  mov     rcx, r15; phContext
0x1c00cbbad  mov     [rbx+1D0h], eax
0x1c00cbbb3  call    cs:__imp_QueryContextAttributesW
0x1c00cbbba  nop     dword ptr [rax+rax+00h]
0x1c00cbbbf  mov     r14d, eax
0x1c00cbbc2  test    eax, eax
0x1c00cbbc4  jnz     loc_1C00F6A3A
0x1c00cbbca  mov     edi, r13d
0x1c00cbbcd  movsd   xmm1, [rbp+120h+var_158]
0x1c00cbbd2  mov     esi, 10000h
0x1c00cbbd7  mov     eax, [rbp+120h+var_150]
0x1c00cbbda  mov     r12w, 1
0x1c00cbbdf  movups  xmm0, [rbp+120h+var_168]
0x1c00cbbe3  movups  xmmword ptr [rbx+1D4h], xmm0
0x1c00cbbea  movsd   qword ptr [rbx+1E4h], xmm1
0x1c00cbbf2  mov     [rbx+1ECh], eax
0x1c00cbbf8  cmp     [rbx+0E8h], r13b
0x1c00cbbff  jnz     loc_1C00CBC97
0x1c00cbc05  lea     r8, [rbp+120h+var_140]; pBuffer
0x1c00cbc09  mov     rcx, r15; phContext
0x1c00cbc0c  lea     edx, [r14+23h]; ulAttribute
0x1c00cbc10  call    cs:__imp_QueryContextAttributesW
0x1c00cbc17  nop     dword ptr [rax+rax+00h]
0x1c00cbc1c  mov     r14d, eax
0x1c00cbc1f  test    eax, eax
0x1c00cbc21  jnz     loc_1C00F6B9C
0x1c00cbc27  lea     rdx, [rbp+120h+var_140]
0x1c00cbc2b  mov     rcx, rbx
0x1c00cbc2e  call    UxpSslProcessApplicationProtocolQuery
0x1c00cbc33  mov     edi, eax
0x1c00cbc35  test    eax, eax
0x1c00cbc37  js      loc_1C00F6AB8
0x1c00cbc3d  xorps   xmm0, xmm0
0x1c00cbc40  lea     r8, [rsp+220h+var_1C0+8]; pBuffer
0x1c00cbc45  lea     edx, [r14+6Dh]; ulAttribute
0x1c00cbc49  mov     rcx, r15; phContext
0x1c00cbc4c  movups  [rsp+220h+var_1C0+8], xmm0
0x1c00cbc51  call    cs:__imp_QueryContextAttributesW
0x1c00cbc58  nop     dword ptr [rax+rax+00h]
0x1c00cbc5d  mov     r14d, eax
0x1c00cbc60  test    eax, eax
0x1c00cbc62  jnz     loc_1C00F6B46
0x1c00cbc68  mov     edi, r13d
0x1c00cbc6b  cmp     byte ptr [rsp+220h+var_1C0+8], r13b
0x1c00cbc70  jnz     loc_1C00F6AD1
0x1c00cbc76  cmp     byte ptr [rsp+220h+var_1C0+9], r13b
0x1c00cbc7b  jnz     loc_1C00F6AD1
0x1c00cbc81  mov     rcx, [rsp+220h+pvContextBuffer]; pvContextBuffer
0x1c00cbc86  test    rcx, rcx
0x1c00cbc89  jnz     loc_1C00F6B79
0x1c00cbc8f  test    edi, edi
0x1c00cbc91  js      loc_1C00F6B8B
0x1c00cbc97  cmp     [rbx+258h], r13d
0x1c00cbc9e  jnz     short loc_1C00CBCEA
0x1c00cbca0  lea     r8, [rsp+220h+var_1E8+8]; pBuffer
0x1c00cbca5  mov     edx, 63h ; 'c'; ulAttribute
0x1c00cbcaa  mov     rcx, r15; phContext
0x1c00cbcad  call    cs:__imp_QueryContextAttributesW
0x1c00cbcb4  nop     dword ptr [rax+rax+00h]
0x1c00cbcb9  test    eax, eax
0x1c00cbcbb  jnz     loc_1C00F6BBC
0x1c00cbcc1  movups  xmm0, [rsp+220h+var_1E8+8]
0x1c00cbcc6  mov     edi, r13d
0x1c00cbcc9  movups  xmm1, xmmword ptr [rsp+220h+var_1D8+8]
0x1c00cbcce  movups  xmmword ptr [rbx+248h], xmm0
0x1c00cbcd5  movsd   xmm0, qword ptr [rsp+220h+var_1C0]
0x1c00cbcdb  movups  xmmword ptr [rbx+258h], xmm1
0x1c00cbce2  movsd   qword ptr [rbx+268h], xmm0
0x1c00cbcea  cmp     [rbx+0E8h], r13b
0x1c00cbcf1  jnz     short loc_1C00CBD08
0x1c00cbcf3  xor     ecx, ecx; PerformanceFrequency
0x1c00cbcf5  call    cs:__imp_KeQueryPerformanceCounter
0x1c00cbcfc  nop     dword ptr [rax+rax+00h]
0x1c00cbd01  mov     [rbx+3E8h], rax
0x1c00cbd08  mov     eax, [rbx+1F8h]
0x1c00cbd0e  test    al, 2
0x1c00cbd10  jnz     loc_1C00F6BCA
0x1c00cbd16  cmp     [rbx+0E8h], r13b
0x1c00cbd1d  jnz     short loc_1C00CBD2D
0x1c00cbd1f  mov     eax, [rbx+1F8h]
0x1c00cbd25  test    al, 2
0x1c00cbd27  jnz     loc_1C00F6DB1
0x1c00cbd2d  mov     eax, edi
0x1c00cbd2f  mov     rcx, [rbp+120h+var_30]
0x1c00cbd36  xor     rcx, rsp; StackCookie
0x1c00cbd39  call    __security_check_cookie
0x1c00cbd3e  lea     r11, [rsp+220h+var_20]
0x1c00cbd46  mov     rbx, [r11+38h]
0x1c00cbd4a  mov     rsi, [r11+40h]
0x1c00cbd4e  mov     rdi, [r11+48h]
0x1c00cbd52  mov     rsp, r11
0x1c00cbd55  pop     r15
0x1c00cbd57  pop     r14
0x1c00cbd59  pop     r13
0x1c00cbd5b  pop     r12
0x1c00cbd5d  pop     rbp
0x1c00cbd5e  retn
0x1c00f6998  mov     rax, [rbx+3C0h]
0x1c00f699f  cmp     [rax+620h], r13b
0x1c00f69a6  jz      short loc_1C00F69F1
0x1c00f69a8  mov     [rsp+220h+var_1A8], rax
0x1c00f69ad  lea     rcx, [rbx+48h]
0x1c00f69b1  lea     rax, aAttributeStrea; "Attribute_StreamSizes"
0x1c00f69b8  mov     [rbp+120h+var_19F], r13d
0x1c00f69bc  mov     qword ptr [rsp+220h+var_1F8], rax
0x1c00f69c1  lea     r8, [rsp+220h+var_1C0+8]
0x1c00f69c6  mov     r9, rbx
0x1c00f69c9  mov     dword ptr [rsp+220h+var_200], r14d
0x1c00f69ce  lea     rdx, HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE
0x1c00f69d5  mov     [rbp+120h+var_19B], r13w
0x1c00f69da  mov     [rbp+120h+var_199], r13b
0x1c00f69de  mov     qword ptr [rsp+220h+var_1C0+8], rcx
0x1c00f69e3  mov     [rsp+220h+pvContextBuffer], r13
0x1c00f69e8  mov     [rbp+120h+var_1A0], r13b
0x1c00f69ec  call    McTemplateK0pqs_UlEtwWriteEventWrapper
0x1c00f69f1  mov     ecx, r14d
0x1c00f69f4  call    UxSslMapSecurityStatusToNtStatus
0x1c00f69f9  mov     edi, eax
0x1c00f69fb  mov     esi, 10000h
0x1c00f6a00  test    cs:WPP_MAIN_CB.DeviceType, esi
0x1c00f6a06  jz      loc_1C00CBD16
0x1c00f6a0c  mov     ecx, 31h ; '1'
0x1c00f6a11  jmp     short loc_1C00F6A18
0x1c00f6a13  mov     ecx, 36h ; '6'
0x1c00f6a18  mov     r9d, r14d
0x1c00f6a1b  jmp     short loc_1C00F6A25
0x1c00f6a1d  mov     ecx, 35h ; '5'
0x1c00f6a22  mov     r9d, edi
0x1c00f6a25  mov     r8, rbx
0x1c00f6a28  lea     rdx, WPP_a22469013d8d37a4fc03866b4ef29eb7_Traceguids
0x1c00f6a2f  call    WPP_SF_qD
0x1c00f6a34  nop
0x1c00f6a35  jmp     loc_1C00CBD16
0x1c00f6a3a  mov     rax, [rbx+3C0h]
0x1c00f6a41  cmp     [rax+620h], r13b
0x1c00f6a48  jz      short loc_1C00F6A93
0x1c00f6a4a  mov     [rsp+220h+var_1A8], rax
0x1c00f6a4f  lea     rcx, [rbx+48h]
0x1c00f6a53  lea     rax, aAttributeConni; "Attribute_ConnInfo"
0x1c00f6a5a  mov     [rbp+120h+var_19F], r13d
0x1c00f6a5e  mov     qword ptr [rsp+220h+var_1F8], rax
0x1c00f6a63  lea     r8, [rsp+220h+var_1C0+8]
0x1c00f6a68  mov     r9, rbx
0x1c00f6a6b  mov     dword ptr [rsp+220h+var_200], r14d
0x1c00f6a70  lea     rdx, HTTP_EVENT_SSL_QUERY_CONN_INFO_FAILURE
0x1c00f6a77  mov     [rbp+120h+var_19B], r13w
0x1c00f6a7c  mov     [rbp+120h+var_199], r13b
0x1c00f6a80  mov     qword ptr [rsp+220h+var_1C0+8], rcx
0x1c00f6a85  mov     [rsp+220h+pvContextBuffer], r13
0x1c00f6a8a  mov     [rbp+120h+var_1A0], r13b
0x1c00f6a8e  call    McTemplateK0pqs_UlEtwWriteEventWrapper
0x1c00f6a93  mov     ecx, r14d
0x1c00f6a96  call    UxSslMapSecurityStatusToNtStatus
0x1c00f6a9b  mov     edi, eax
0x1c00f6a9d  mov     esi, 10000h
0x1c00f6aa2  test    cs:WPP_MAIN_CB.DeviceType, esi
0x1c00f6aa8  jz      loc_1C00CBD16
0x1c00f6aae  mov     ecx, 32h ; '2'
0x1c00f6ab3  jmp     loc_1C00F6A18
0x1c00f6ab8  test    cs:WPP_MAIN_CB.DeviceType, esi
0x1c00f6abe  jz      loc_1C00CBD16
0x1c00f6ac4  mov     ecx, 34h ; '4'
0x1c00f6ac9  mov     r9d, eax
0x1c00f6acc  jmp     loc_1C00F6A25
0x1c00f6ad1  movzx   eax, word ptr [rsp+220h+var_1C0+0Ah]
0x1c00f6ad6  test    ax, ax
0x1c00f6ad9  jz      loc_1C00CBC81
0x1c00f6adf  cmp     ax, r12w
0x1c00f6ae3  jz      short loc_1C00F6AEF
0x1c00f6ae5  mov     edi, 0C00000BBh
0x1c00f6aea  jmp     loc_1C00CBC81
0x1c00f6aef  mov     rax, [rsp+220h+pvContextBuffer]
0x1c00f6af4  lea     r8, [rbx+1A0h]; pBuffer
0x1c00f6afb  mov     [rbx+188h], r12b
0x1c00f6b02  mov     edx, 6Fh ; 'o'; ulAttribute
0x1c00f6b07  movzx   ecx, byte ptr [rax]
0x1c00f6b0a  mov     [rbx+18Ch], ecx
0x1c00f6b10  mov     rcx, r15; phContext
0x1c00f6b13  call    cs:__imp_QueryContextAttributesW
0x1c00f6b1a  nop     dword ptr [rax+rax+00h]
0x1c00f6b1f  mov     r14d, eax
0x1c00f6b22  test    eax, eax
0x1c00f6b24  jz      loc_1C00CBC81
0x1c00f6b2a  mov     ecx, eax
0x1c00f6b2c  call    UxSslMapSecurityStatusToNtStatus
0x1c00f6b31  mov     edi, eax
0x1c00f6b33  test    cs:WPP_MAIN_CB.DeviceType, esi
0x1c00f6b39  jz      loc_1C00CBC81
0x1c00f6b3f  mov     ecx, 39h ; '9'
0x1c00f6b44  jmp     short loc_1C00F6B61
0x1c00f6b46  mov     ecx, r14d
0x1c00f6b49  call    UxSslMapSecurityStatusToNtStatus
0x1c00f6b4e  mov     edi, eax
0x1c00f6b50  test    cs:WPP_MAIN_CB.DeviceType, esi
0x1c00f6b56  jz      loc_1C00CBC81
0x1c00f6b5c  mov     ecx, 38h ; '8'
0x1c00f6b61  mov     r9d, r14d
0x1c00f6b64  lea     rdx, WPP_a22469013d8d37a4fc03866b4ef29eb7_Traceguids
0x1c00f6b6b  mov     r8, rbx
0x1c00f6b6e  call    WPP_SF_qD
0x1c00f6b73  nop
0x1c00f6b74  jmp     loc_1C00CBC81
0x1c00f6b79  call    cs:__imp_FreeContextBuffer
0x1c00f6b80  nop     dword ptr [rax+rax+00h]
0x1c00f6b85  nop
0x1c00f6b86  jmp     loc_1C00CBC8F
0x1c00f6b8b  test    cs:WPP_MAIN_CB.DeviceType, esi
0x1c00f6b91  jz      loc_1C00CBD16
0x1c00f6b97  jmp     loc_1C00F6A1D
0x1c00f6b9c  mov     ecx, r14d
0x1c00f6b9f  call    UxSslMapSecurityStatusToNtStatus
0x1c00f6ba4  mov     edi, eax
0x1c00f6ba6  test    cs:WPP_MAIN_CB.DeviceType, esi
0x1c00f6bac  jz      loc_1C00CBD16
0x1c00f6bb2  mov     ecx, 33h ; '3'
0x1c00f6bb7  jmp     loc_1C00F6A18
0x1c00f6bbc  mov     ecx, eax
0x1c00f6bbe  call    UxSslMapSecurityStatusToNtStatus
0x1c00f6bc3  mov     edi, eax
0x1c00f6bc5  jmp     loc_1C00CBD16
0x1c00f6bca  cmp     [rbx+0E8h], r13b
0x1c00f6bd1  jnz     short loc_1C00F6BE8
0x1c00f6bd3  xor     ecx, ecx; PerformanceFrequency
0x1c00f6bd5  call    cs:__imp_KeQueryPerformanceCounter
0x1c00f6bdc  nop     dword ptr [rax+rax+00h]
0x1c00f6be1  mov     [rbx+3F0h], rax
0x1c00f6be8  lea     r8, [rsp+220h+var_1F8+8]; pBuffer
0x1c00f6bed  mov     edx, 5Fh ; '_'; ulAttribute
0x1c00f6bf2  mov     rcx, r15; phContext
0x1c00f6bf5  call    cs:__imp_QueryContextAttributesW
0x1c00f6bfc  nop     dword ptr [rax+rax+00h]
0x1c00f6c01  test    eax, eax
0x1c00f6c03  jnz     loc_1C00F6D9B
0x1c00f6c09  cmp     dword ptr [rsp+220h+var_1F8+0Ch], r13d
0x1c00f6c0e  jz      loc_1C00F6D9B
0x1c00f6c14  movups  xmm0, [rsp+220h+var_1F8+8]
0x1c00f6c19  lea     r8, [rbp+120h+var_180]; pBuffer
0x1c00f6c1d  mov     edx, 61h ; 'a'; ulAttribute
0x1c00f6c22  movdqu  xmmword ptr [rbx+220h], xmm0
0x1c00f6c2a  psrldq  xmm0, 8
0x1c00f6c2f  movq    rax, xmm0
  ... truncated ...
```
