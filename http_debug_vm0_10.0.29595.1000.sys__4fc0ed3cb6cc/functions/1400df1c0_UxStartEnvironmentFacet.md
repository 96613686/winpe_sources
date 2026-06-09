# UxStartEnvironmentFacet

- ea: `0x1400df1c0`
- end: `0x1400dfbcf`
- name: `UxStartEnvironmentFacet`
- size: `2575`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140090038`
- `0x1400d6ae8`
- `0x1400dea2c`
- `0x1400deb24`
- `0x1400deb44`
- `0x1400deb80`
- `0x1400ded10`
- `0x1400dee90`
- `0x1400df1c0`
- `0x1400e03d0`
- `0x14013f290`

## import_xrefs

- `ntoskrnl!RtlIsFunctionalityAvailable` at `0x1400df284`
- `ntoskrnl!RtlIsFunctionalityAvailable` at `0x1400df2a0`
- `ntoskrnl!RtlIsFunctionalityAvailable` at `0x1400df284`
- `ntoskrnl!RtlIsFunctionalityAvailable` at `0x1400df2a0`
- `ntoskrnl!ZwOpenKey` at `0x1400df26b`
- `ntoskrnl!ZwOpenKey` at `0x1400df26b`
- `ntoskrnl!ZwClose` at `0x1400dfb93`
- `ntoskrnl!ZwClose` at `0x1400dfb93`

## string_xrefs

- `0x1400df1e5`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters`
- `0x1400df2f2`: `BasicTokenCacheTTL`
- `0x1400df502`: `UriScavengerPeriod`
- `0x1400df487`: `UriCacheRangeChunk`
- `0x1400df42a`: `ExpandedUriMaxUriBytes`
- `0x1400df3ee`: `UriMaxUriBytes`
- `0x1400df3c6`: `UriMaxCacheMegabyteCount`
- `0x1400df392`: `UriEnableCache`
- `0x1400df639`: `SslDecryptOnSspiThread`
- `0x1400df563`: `EnableSslTokenBinding`
- `0x1400df67e`: `DisableSslClientCertChainCacheOnlyUrlRetrieval`
- `0x1400df950`: `Http2MaxWindowUpdatesPerSend`
- `0x1400dfb76`: `DisableLocalSystemAccountAuthToken`

## pseudocode

```c
__int64 __fastcall UxStartEnvironmentFacet(__int64 a1)
{
  __int64 v2; // rbx
  int ComputerName; // r12d
  __int64 v4; // rax
  __int64 v5; // r8
  unsigned int LongParameter; // eax
  void *v7; // rcx
  __int64 v8; // r8
  unsigned int *v9; // rdi
  int v10; // ecx
  unsigned int v11; // edx
  unsigned int v12; // ebx
  unsigned int v13; // ecx
  unsigned int v14; // edx
  int v15; // ecx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // r8d
  int v20; // r9d
  int v21; // r8d
  int v22; // r9d
  int v23; // r8d
  int v24; // r9d
  int v25; // r8d
  int v26; // r9d
  int v27; // r8d
  int v28; // r9d
  int v29; // r8d
  int v30; // r9d
  __int64 v31; // r8
  __int64 v32; // r8
  int v33; // ecx
  int v34; // eax
  int v35; // ecx
  __int64 v36; // rax
  int v37; // ecx
  __int64 v38; // r8
  __int64 v39; // r8
  int v41; // [rsp+20h] [rbp-60h]
  int v42; // [rsp+20h] [rbp-60h]
  int v43; // [rsp+20h] [rbp-60h]
  int v44; // [rsp+20h] [rbp-60h]
  int v45; // [rsp+20h] [rbp-60h]
  int v46; // [rsp+20h] [rbp-60h]
  int v47; // [rsp+20h] [rbp-60h]
  int v48; // [rsp+28h] [rbp-58h]
  int v49; // [rsp+28h] [rbp-58h]
  int v50; // [rsp+28h] [rbp-58h]
  int v51; // [rsp+28h] [rbp-58h]
  int v52; // [rsp+28h] [rbp-58h]
  int v53; // [rsp+28h] [rbp-58h]
  int v54; // [rsp+28h] [rbp-58h]
  _QWORD v55[2]; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  char v57; // [rsp+C0h] [rbp+40h] BYREF
  void *KeyHandle; // [rsp+C8h] [rbp+48h] BYREF

  v55[0] = 8913030;
  v2 = a1 + 3472;
  v55[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Http\\Parameters";
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v57 = 0;
  ComputerName = UxGetComputerName((NTSTRSAFE_PWSTR)(a1 + 3472));
  if ( ComputerName >= 0 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(v2 + 2 * v4) );
    *(_DWORD *)(a1 + 3988) = v4;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v55;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
      KeyHandle = 0;
    *(_BYTE *)(a1 + 8352) = RtlIsFunctionalityAvailable(4);
    *(_BYTE *)(a1 + 8353) = RtlIsFunctionalityAvailable(1);
    UxTlCreateListenAddressList(a1);
    UxReadErrorLogSettings(a1, KeyHandle);
    ComputerName = UxReadHttp11ParserSettings(a1, KeyHandle);
    if ( ComputerName >= 0 )
    {
      if ( !UxCompactMode )
      {
        LOBYTE(v5) = 1;
        UxReadBooleanSetting(KeyHandle, L"BasicTokenCacheTTL", v5, a1 + 92);
      }
      UxReadBoundedULongSetting((_DWORD)KeyHandle, (unsigned int)L"DisableServerHeader", 0, 0, 2, 0, a1 + 4372);
      UxReadBooleanSetting(KeyHandle, L"DisableErrorResponse", 0, a1 + 4368);
      LongParameter = UlReadLongParameter(KeyHandle, L"MaxBufferedSendBytes", 0xFFFFFFFFLL);
      v7 = KeyHandle;
      if ( LongParameter > 0xFFFFF )
        LongParameter = -1;
      *(_DWORD *)(a1 + 4384) = LongParameter;
      UxReadBooleanSetting(v7, L"ExpandedSendBuffering", 0, &v57);
      LOBYTE(v8) = 1;
      *(_DWORD *)(a1 + 4388) = v57 != 0 ? 0x1000000 : 0xFFFFF;
      UxReadBooleanSetting(KeyHandle, L"UriEnableCache", v8, a1 + 1096);
      UxReadBoundedULongSetting((_DWORD)KeyHandle, (unsigned int)L"UriMaxCacheMegabyteCount", 0, 0, -1, 0, a1 + 1100);
      v9 = (unsigned int *)(a1 + 1116);
      v10 = (int)KeyHandle;
      *(_QWORD *)(a1 + 1104) = (unsigned __int64)*(unsigned int *)(a1 + 1100) << 20;
      UxReadBoundedULongSetting(v10, (unsigned int)L"UriMaxUriBytes", 0x40000, 4096, -1, 0, a1 + 1116);
      UxReadBooleanSetting(KeyHandle, L"ExpandedUriMaxUriBytes", 0, &v57);
      if ( !v57 && *v9 > 0x1000000 )
        *v9 = 0x1000000;
      v11 = *v9;
      v12 = 0x80000000;
      v13 = 0x80000000;
      if ( (*v9 & 0x80000000) == 0 )
      {
        v13 = (((v11
               | (v11 >> 1)
               | ((v11 | (v11 >> 1)) >> 2)
               | ((v11 | (v11 >> 1) | ((v11 | (v11 >> 1)) >> 2)) >> 4)
               | ((v11 | (v11 >> 1) | ((v11 | (v11 >> 1)) >> 2) | ((v11 | (v11 >> 1) | ((v11 | (v11 >> 1)) >> 2)) >> 4)) >> 8)) >> 16)
             | v11
             | (v11 >> 1)
             | ((v11 | (v11 >> 1)) >> 2)
             | ((v11 | (v11 >> 1) | ((v11 | (v11 >> 1)) >> 2)) >> 4)
             | ((v11 | (v11 >> 1) | ((v11 | (v11 >> 1)) >> 2) | ((v11 | (v11 >> 1) | ((v11 | (v11 >> 1)) >> 2)) >> 4)) >> 8))
            + 1;
        if ( ((4 * v11) & v13) == 0 )
          v13 >>= 1;
      }
      *v9 = v13;
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"UriCacheRangeChunk",
        0x10000,
        4096,
        v13,
        2,
        a1 + 1120);
      v14 = *(_DWORD *)(a1 + 1120);
      if ( (v14 & 0x80000000) == 0 )
      {
        v12 = (v14
             | (v14 >> 1)
             | ((v14 | (v14 >> 1)) >> 2)
             | ((v14 | (v14 >> 1) | ((v14 | (v14 >> 1)) >> 2)) >> 4)
             | ((v14 | (v14 >> 1) | ((v14 | (v14 >> 1)) >> 2) | ((v14 | (v14 >> 1) | ((v14 | (v14 >> 1)) >> 2)) >> 4)) >> 8)
             | ((v14
               | (v14 >> 1)
               | ((v14 | (v14 >> 1)) >> 2)
               | ((v14 | (v14 >> 1) | ((v14 | (v14 >> 1)) >> 2)) >> 4)
               | ((v14 | (v14 >> 1) | ((v14 | (v14 >> 1)) >> 2) | ((v14 | (v14 >> 1) | ((v14 | (v14 >> 1)) >> 2)) >> 4)) >> 8)) >> 16))
            + 1;
        if ( ((4 * v14) & v12) == 0 )
          v12 >>= 1;
      }
      v15 = (int)KeyHandle;
      *(_DWORD *)(a1 + 1120) = v12;
      UxReadBoundedULongSetting(v15, (unsigned int)L"UriScavengerPeriod", 120, 10, -1, 1, a1 + 1112);
      v16 = (int)KeyHandle;
      *(_BYTE *)(a1 + 1097) = 0;
      UxReadBoundedULongSetting(v16, (unsigned int)L"MaxConnections", -1, 0, -1, 0, a1 + 8404);
      UxReadBoundedLongSetting((_DWORD)KeyHandle, (unsigned int)L"EnableSslTokenBinding", v17, v18, v41, v48, a1 + 8180);
      UxReadBoundedLongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"EnableSslSessionTicket",
        v19,
        v20,
        v42,
        v49,
        a1 + 8184);
      UxReadBoundedLongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"EnableTlsClientHelloCaching",
        v21,
        v22,
        v43,
        v50,
        a1 + 8188);
      UxReadBoundedLongSetting((_DWORD)KeyHandle, (unsigned int)L"DisableTls12", v23, v24, v44, v51, a1 + 8168);
      UxReadBoundedLongSetting((_DWORD)KeyHandle, (unsigned int)L"DisableLegacyTls", v25, v26, v45, v52, a1 + 8172);
      UxReadBoundedLongSetting((_DWORD)KeyHandle, (unsigned int)L"DisableTls13", v27, v28, v46, v53, a1 + 8176);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"CertificateScavengerPeriod",
        1800,
        0,
        -1,
        0,
        a1 + 8196);
      UxReadBoundedLongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"SslDecryptOnSspiThread",
        v29,
        v30,
        v47,
        v54,
        a1 + 0x2000);
      if ( (unsigned int)(*(_DWORD *)(a1 + 8196) - 1) <= 0x76 )
        *(_DWORD *)(a1 + 8196) = 120;
      UxReadBooleanSetting(KeyHandle, L"EnableSslCloseNotify", 0, a1 + 8162);
      UxReadBooleanSetting(KeyHandle, L"DisableSslClientCertChainCacheOnlyUrlRetrieval", 0, a1 + 8161);
      UxReadBooleanSetting(KeyHandle, L"EnableSslHostCheck", 0, a1 + 8164);
      UxReadBooleanSetting(KeyHandle, L"DisableOcspStapling", 0, a1 + 8166);
      if ( UxKirAddDisableAiaFlag )
        UxReadBooleanSetting(KeyHandle, L"DisableAia", 0, a1 + 8167);
      else
        *(_BYTE *)(a1 + 8167) = 0;
      LOBYTE(v31) = 1;
      UxReadBooleanSetting(KeyHandle, L"EnableHttp2Tls", v31, a1 + 7108);
      UxReadBooleanSetting(KeyHandle, L"EnableHttp2Icw", 0, a1 + 7110);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2WindowSize",
        0xFFFF,
        0x100000,
        0x7FFFFFFF,
        0,
        a1 + 7144);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2MaxConcurrentClientStreams",
        100,
        0,
        -1,
        0,
        a1 + 7136);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2MaxSettingsPerFrame",
        2796202,
        7,
        2796202,
        3,
        a1 + 7148);
      UxReadBoundedULongSetting((_DWORD)KeyHandle, (unsigned int)L"Http2MaxSettingsPerMinute", -1, 7, -1, 3, a1 + 7152);
      UxReadBoundedULongSetting((_DWORD)KeyHandle, (unsigned int)L"Http2MaxPingsPerMinute", 0, 0, 255, 2, a1 + 7156);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2MaxServerResetsPerMinute",
        0,
        0,
        0xFFFF,
        2,
        a1 + 7172);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2MaxClientResetsPerMinute",
        400,
        0,
        0xFFFF,
        2,
        a1 + 7176);
      LOBYTE(v32) = 1;
      UxReadBooleanSetting(KeyHandle, L"Http2MaxClientResetsGoaway", v32, a1 + 7112);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2MaxPrioritiesPerStream",
        0,
        0,
        255,
        2,
        a1 + 7160);
      UxReadBoundedULongSetting((_DWORD)KeyHandle, (unsigned int)L"Http2MaxResetsPerStream", 0, 0, 255, 2, a1 + 7164);
      UxReadBoundedULongSetting((_DWORD)KeyHandle, (unsigned int)L"Http2MaxUnknownsPerStream", 0, 0, 255, 2, a1 + 7168);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2MinimumSendWindowSize",
        0,
        0,
        0xFFFF,
        2,
        a1 + 7224);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2MaxWindowUpdatesPerSend",
        0,
        0,
        255,
        2,
        a1 + 7208);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http3CancelPushThrottleFactor",
        0,
        0,
        255,
        2,
        a1 + 8148);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http3QpackMaxUnusedElementsPerMinute",
        0,
        0,
        -1,
        2,
        a1 + 8152);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http3QpackUnusedAllotmentPerUsedElement",
        0,
        0,
        255,
        2,
        a1 + 8156);
      UxReadBooleanSetting(KeyHandle, L"Http3QpackAllowUnackedEviction", 0, a1 + 8160);
      v33 = *(_DWORD *)(a1 + 7136);
      *(_QWORD *)(a1 + 7184) = (unsigned int)(4 * *(_DWORD *)(a1 + 7160) * v33);
      *(_QWORD *)(a1 + 7192) = (unsigned int)(4 * *(_DWORD *)(a1 + 7168) * v33);
      v34 = *(_DWORD *)(a1 + 7164) * v33;
      v35 = *(_DWORD *)(a1 + 7208) * v33;
      *(_QWORD *)(a1 + 7200) = (unsigned int)(4 * v34);
      v36 = (unsigned int)(4 * v35);
      v37 = (int)KeyHandle;
      *(_QWORD *)(a1 + 7216) = v36;
      UxReadBoundedULongSetting(v37, (unsigned int)L"Http2SettingsAckTimeout", 10, 0, -1, 0, a1 + 7140);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2SettingsMaxPendingBytes",
        0,
        0,
        -1,
        0,
        a1 + 7132);
      LOBYTE(v38) = 1;
      UxReadBooleanSetting(KeyHandle, L"Http2SettingsAckCheck", v38, a1 + 7111);
      LOBYTE(v39) = 1;
      UxReadBooleanSetting(KeyHandle, L"ClientSessionEnable", v39, a1 + 8704);
      UxReadBoundedULongSetting((_DWORD)KeyHandle, (unsigned int)L"Http3MaxBlockedStreams", 100, 0, -1, 3, a1 + 8076);
      UxReadBooleanSetting(KeyHandle, L"EnableFastForwarding", 0, a1 + 8736);
      UxReadBoundedULongSetting((_DWORD)KeyHandle, (unsigned int)L"DefaultAuthHardeningLevel", 1, 0, 2, 0, a1 + 1048);
      UxReadBooleanSetting(KeyHandle, L"DisableLocalSystemAccountAuthToken", 0, a1 + 1052);
      HttpCmnInitializeDynamicHttpCharsTable(a1);
    }
  }
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( ComputerName < 0 )
    UxStopEnvironmentFacet(a1);
  return (unsigned int)ComputerName;
}

```

## disassembly

```asm
0x1400df1c0  mov     [rsp-38h+arg_10], rbx
0x1400df1c5  push    rbp
0x1400df1c6  push    rsi
0x1400df1c7  push    rdi
0x1400df1c8  push    r12
0x1400df1ca  push    r13
0x1400df1cc  push    r14
0x1400df1ce  push    r15
0x1400df1d0  mov     rbp, rsp
0x1400df1d3  sub     rsp, 80h
0x1400df1da  xorps   xmm0, xmm0
0x1400df1dd  mov     [rbp+var_40], 880086h
0x1400df1e5  lea     rax, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400df1ec  mov     r13, rcx
0x1400df1ef  lea     rbx, [rcx+0D90h]
0x1400df1f6  mov     [rbp+var_38], rax
0x1400df1fa  xor     esi, esi
0x1400df1fc  xor     eax, eax
0x1400df1fe  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400df202  mov     rcx, rbx; pszDest
0x1400df205  mov     [rbp+KeyHandle], rsi
0x1400df209  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400df20d  mov     [rbp+arg_0], sil
0x1400df211  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400df215  call    UxGetComputerName
0x1400df21a  mov     r12d, eax
0x1400df21d  test    eax, eax
0x1400df21f  js      loc_1400DFB8A
0x1400df225  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400df229  mov     rax, rdi
0x1400df22c  inc     rax
0x1400df22f  cmp     [rbx+rax*2], si
0x1400df233  jnz     short loc_1400DF22C
0x1400df235  mov     [r13+0F94h], eax
0x1400df23c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400df240  lea     rax, [rbp+var_40]
0x1400df244  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400df24b  xorps   xmm0, xmm0
0x1400df24e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400df252  mov     edx, 20019h; DesiredAccess
0x1400df257  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x1400df25b  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400df25f  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400df266  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400df26b  call    cs:__imp_ZwOpenKey
0x1400df272  nop     dword ptr [rax+rax+00h]
0x1400df277  test    eax, eax
0x1400df279  jns     short loc_1400DF27F
0x1400df27b  mov     [rbp+KeyHandle], rsi
0x1400df27f  mov     ecx, 4
0x1400df284  call    cs:__imp_RtlIsFunctionalityAvailable
0x1400df28b  nop     dword ptr [rax+rax+00h]
0x1400df290  mov     r15d, 1
0x1400df296  mov     [r13+20A0h], al
0x1400df29d  mov     ecx, r15d
0x1400df2a0  call    cs:__imp_RtlIsFunctionalityAvailable
0x1400df2a7  nop     dword ptr [rax+rax+00h]
0x1400df2ac  mov     rcx, r13
0x1400df2af  mov     [r13+20A1h], al
0x1400df2b6  call    UxTlCreateListenAddressList
0x1400df2bb  mov     rdx, [rbp+KeyHandle]
0x1400df2bf  mov     rcx, r13
0x1400df2c2  call    UxReadErrorLogSettings
0x1400df2c7  mov     rdx, [rbp+KeyHandle]
0x1400df2cb  mov     rcx, r13
0x1400df2ce  call    UxReadHttp11ParserSettings
0x1400df2d3  mov     r12d, eax
0x1400df2d6  test    eax, eax
0x1400df2d8  js      loc_1400DFB8A
0x1400df2de  cmp     cs:UxCompactMode, sil
0x1400df2e5  jnz     short loc_1400DF2FE
0x1400df2e7  mov     rcx, [rbp+KeyHandle]
0x1400df2eb  lea     r9, [r13+5Ch]
0x1400df2ef  mov     r8b, r15b
0x1400df2f2  lea     rdx, aBasictokencach; "BasicTokenCacheTTL"
0x1400df2f9  call    UxReadBooleanSetting
0x1400df2fe  mov     rcx, [rbp+KeyHandle]
0x1400df302  lea     rax, [r13+1114h]
0x1400df309  mov     [rsp+80h+var_50], rax
0x1400df30e  lea     rdx, aDisableserverh; "DisableServerHeader"
0x1400df315  mov     [rsp+80h+var_58], esi
0x1400df319  xor     r9d, r9d
0x1400df31c  xor     r8d, r8d
0x1400df31f  mov     [rsp+80h+var_60], 2
0x1400df327  call    UxReadBoundedULongSetting
0x1400df32c  mov     rcx, [rbp+KeyHandle]
0x1400df330  lea     r9, [r13+1110h]
0x1400df337  xor     r8d, r8d
0x1400df33a  lea     rdx, aDisableerrorre; "DisableErrorResponse"
0x1400df341  call    UxReadBooleanSetting
0x1400df346  mov     rcx, [rbp+KeyHandle]
0x1400df34a  lea     rdx, aMaxbufferedsen; "MaxBufferedSendBytes"
0x1400df351  mov     r8d, edi
0x1400df354  call    UlReadLongParameter
0x1400df359  mov     rcx, [rbp+KeyHandle]
0x1400df35d  lea     r9, [rbp+arg_0]
0x1400df361  or      r14d, 0FFFFFFFFh
0x1400df365  lea     rdx, aExpandedsendbu; "ExpandedSendBuffering"
0x1400df36c  mov     ebx, 0FFFFFh
0x1400df371  cmp     eax, ebx
0x1400df373  cmova   eax, r14d
0x1400df377  xor     r8d, r8d
0x1400df37a  mov     [r13+1120h], eax
0x1400df381  call    UxReadBooleanSetting
0x1400df386  mov     al, [rbp+arg_0]
0x1400df389  lea     r9, [r13+448h]
0x1400df390  neg     al
0x1400df392  lea     rdx, aUrienablecache; "UriEnableCache"
0x1400df399  mov     r8b, r15b
0x1400df39c  sbb     ecx, ecx
0x1400df39e  and     ecx, 0F00001h
0x1400df3a4  add     ecx, ebx
0x1400df3a6  mov     [r13+1124h], ecx
0x1400df3ad  mov     rcx, [rbp+KeyHandle]
0x1400df3b1  call    UxReadBooleanSetting
0x1400df3b6  mov     rcx, [rbp+KeyHandle]
0x1400df3ba  lea     rbx, [r13+44Ch]
0x1400df3c1  mov     [rsp+80h+var_50], rbx
0x1400df3c6  lea     rdx, aUrimaxcachemeg; "UriMaxCacheMegabyteCount"
0x1400df3cd  mov     [rsp+80h+var_58], esi
0x1400df3d1  xor     r9d, r9d
0x1400df3d4  xor     r8d, r8d
0x1400df3d7  mov     [rsp+80h+var_60], r14d
0x1400df3dc  call    UxReadBoundedULongSetting
0x1400df3e1  mov     eax, [rbx]
0x1400df3e3  lea     rdi, [r13+45Ch]
0x1400df3ea  mov     rcx, [rbp+KeyHandle]
0x1400df3ee  lea     rdx, aUrimaxuribytes; "UriMaxUriBytes"
0x1400df3f5  shl     rax, 14h
0x1400df3f9  mov     r9d, 1000h
0x1400df3ff  mov     [rsp+80h+var_50], rdi
0x1400df404  mov     r8d, 40000h
0x1400df40a  mov     [rsp+80h+var_58], esi
0x1400df40e  mov     [r13+450h], rax
0x1400df415  mov     [rsp+80h+var_60], r14d
0x1400df41a  call    UxReadBoundedULongSetting
0x1400df41f  mov     rcx, [rbp+KeyHandle]
0x1400df423  lea     r9, [rbp+arg_0]
0x1400df427  xor     r8d, r8d
0x1400df42a  lea     rdx, aExpandedurimax; "ExpandedUriMaxUriBytes"
0x1400df431  call    UxReadBooleanSetting
0x1400df436  cmp     [rbp+arg_0], sil
0x1400df43a  jnz     short loc_1400DF447
0x1400df43c  mov     eax, 1000000h
0x1400df441  cmp     [rdi], eax
0x1400df443  jbe     short loc_1400DF447
0x1400df445  mov     [rdi], eax
0x1400df447  mov     edx, [rdi]
0x1400df449  mov     ebx, 80000000h
0x1400df44e  mov     ecx, ebx
0x1400df450  test    edx, edx
0x1400df452  js      short loc_1400DF485
0x1400df454  mov     eax, edx
0x1400df456  shr     eax, 1
0x1400df458  or      eax, edx
0x1400df45a  mov     ecx, eax
0x1400df45c  shr     ecx, 2
0x1400df45f  or      ecx, eax
0x1400df461  mov     eax, ecx
0x1400df463  shr     eax, 4
0x1400df466  or      eax, ecx
0x1400df468  mov     ecx, eax
0x1400df46a  shr     ecx, 8
0x1400df46d  or      ecx, eax
0x1400df46f  mov     eax, ecx
0x1400df471  shr     eax, 10h
0x1400df474  or      ecx, eax
0x1400df476  lea     eax, ds:0[rdx*4]
0x1400df47d  inc     ecx
0x1400df47f  test    ecx, eax
0x1400df481  jnz     short loc_1400DF485
0x1400df483  shr     ecx, 1
0x1400df485  mov     [rdi], ecx
0x1400df487  lea     rdx, aUricacherangec; "UriCacheRangeChunk"
0x1400df48e  lea     rdi, [r13+460h]
0x1400df495  mov     r9d, 1000h
0x1400df49b  mov     [rsp+80h+var_50], rdi
0x1400df4a0  mov     r8d, 10000h
0x1400df4a6  mov     [rsp+80h+var_58], 2
0x1400df4ae  mov     [rsp+80h+var_60], ecx
0x1400df4b2  mov     rcx, [rbp+KeyHandle]
0x1400df4b6  call    UxReadBoundedULongSetting
0x1400df4bb  mov     edx, [rdi]
0x1400df4bd  test    edx, edx
0x1400df4bf  js      short loc_1400DF4F2
0x1400df4c1  mov     eax, edx
0x1400df4c3  shr     eax, 1
0x1400df4c5  or      eax, edx
0x1400df4c7  mov     ecx, eax
0x1400df4c9  shr     ecx, 2
0x1400df4cc  or      ecx, eax
0x1400df4ce  mov     eax, ecx
0x1400df4d0  shr     eax, 4
0x1400df4d3  or      eax, ecx
0x1400df4d5  mov     ecx, eax
0x1400df4d7  shr     ecx, 8
0x1400df4da  or      ecx, eax
0x1400df4dc  lea     eax, ds:0[rdx*4]
0x1400df4e3  mov     ebx, ecx
0x1400df4e5  shr     ebx, 10h
0x1400df4e8  or      ebx, ecx
0x1400df4ea  inc     ebx
0x1400df4ec  test    ebx, eax
0x1400df4ee  jnz     short loc_1400DF4F2
0x1400df4f0  shr     ebx, 1
0x1400df4f2  mov     rcx, [rbp+KeyHandle]
0x1400df4f6  lea     rax, [r13+458h]
0x1400df4fd  mov     [rsp+80h+var_50], rax
0x1400df502  lea     rdx, aUriscavengerpe; "UriScavengerPeriod"
0x1400df509  mov     [rdi], ebx
0x1400df50b  mov     edi, 78h ; 'x'
0x1400df510  mov     [rsp+80h+var_58], r15d
0x1400df515  mov     r8d, edi
0x1400df518  mov     [rsp+80h+var_60], r14d
0x1400df51d  lea     r9d, [rdi-6Eh]
0x1400df521  call    UxReadBoundedULongSetting
0x1400df526  mov     rcx, [rbp+KeyHandle]
0x1400df52a  lea     rax, [r13+20D4h]
0x1400df531  mov     [rsp+80h+var_50], rax
0x1400df536  lea     rdx, aMaxconnections; "MaxConnections"
0x1400df53d  mov     [rsp+80h+var_58], esi
0x1400df541  xor     r9d, r9d
0x1400df544  mov     r8d, r14d
0x1400df547  mov     [rsp+80h+var_60], r14d
0x1400df54c  mov     [r13+449h], sil
0x1400df553  call    UxReadBoundedULongSetting
0x1400df558  mov     rcx, [rbp+KeyHandle]
0x1400df55c  lea     rax, [r13+1FF4h]
0x1400df563  lea     rdx, aEnablessltoken; "EnableSslTokenBinding"
0x1400df56a  mov     [rsp+80h+var_50], rax
0x1400df56f  call    UxReadBoundedLongSetting
0x1400df574  mov     rcx, [rbp+KeyHandle]
0x1400df578  lea     rax, [r13+1FF8h]
0x1400df57f  lea     rdx, aEnablesslsessi; "EnableSslSessionTicket"
0x1400df586  mov     [rsp+80h+var_50], rax
0x1400df58b  call    UxReadBoundedLongSetting
0x1400df590  mov     rcx, [rbp+KeyHandle]
0x1400df594  lea     rax, [r13+1FFCh]
0x1400df59b  lea     rdx, aEnabletlsclien; "EnableTlsClientHelloCaching"
0x1400df5a2  mov     [rsp+80h+var_50], rax
0x1400df5a7  call    UxReadBoundedLongSetting
0x1400df5ac  mov     rcx, [rbp+KeyHandle]
0x1400df5b0  lea     rax, [r13+1FE8h]
0x1400df5b7  lea     rdx, aDisabletls12; "DisableTls12"
0x1400df5be  mov     [rsp+80h+var_50], rax
0x1400df5c3  call    UxReadBoundedLongSetting
0x1400df5c8  mov     rcx, [rbp+KeyHandle]
0x1400df5cc  lea     rax, [r13+1FECh]
0x1400df5d3  lea     rdx, aDisablelegacyt; "DisableLegacyTls"
0x1400df5da  mov     [rsp+80h+var_50], rax
0x1400df5df  call    UxReadBoundedLongSetting
0x1400df5e4  mov     rcx, [rbp+KeyHandle]
0x1400df5e8  lea     rax, [r13+1FF0h]
0x1400df5ef  lea     rdx, aDisabletls13; "DisableTls13"
0x1400df5f6  mov     [rsp+80h+var_50], rax
0x1400df5fb  call    UxReadBoundedLongSetting
0x1400df600  mov     rcx, [rbp+KeyHandle]
0x1400df604  lea     rbx, [r13+2004h]
0x1400df60b  mov     [rsp+80h+var_50], rbx
0x1400df610  lea     rdx, aCertificatesca; "CertificateScavengerPeriod"
0x1400df617  mov     [rsp+80h+var_58], esi
0x1400df61b  xor     r9d, r9d
0x1400df61e  mov     r8d, 708h
0x1400df624  mov     [rsp+80h+var_60], r14d
0x1400df629  call    UxReadBoundedULongSetting
0x1400df62e  mov     rcx, [rbp+KeyHandle]
0x1400df632  lea     rax, [r13+2000h]
0x1400df639  lea     rdx, aSsldecryptonss; "SslDecryptOnSspiThread"
0x1400df640  mov     [rsp+80h+var_50], rax
0x1400df645  call    UxReadBoundedLongSetting
0x1400df64a  mov     eax, [rbx]
0x1400df64c  sub     eax, r15d
0x1400df64f  cmp     eax, 76h ; 'v'
0x1400df652  ja      short loc_1400DF656
0x1400df654  mov     [rbx], edi
0x1400df656  mov     rcx, [rbp+KeyHandle]
0x1400df65a  lea     r9, [r13+1FE2h]
0x1400df661  xor     r8d, r8d
0x1400df664  lea     rdx, aEnablesslclose; "EnableSslCloseNotify"
0x1400df66b  call    UxReadBooleanSetting
0x1400df670  mov     rcx, [rbp+KeyHandle]
0x1400df674  lea     r9, [r13+1FE1h]
0x1400df67b  xor     r8d, r8d
0x1400df67e  lea     rdx, aDisablesslclie; "DisableSslClientCertChainCacheOnlyUrlRe"...
0x1400df685  call    UxReadBooleanSetting
0x1400df68a  mov     rcx, [rbp+KeyHandle]
0x1400df68e  lea     r9, [r13+1FE4h]
0x1400df695  xor     r8d, r8d
0x1400df698  lea     rdx, aEnablesslhostc; "EnableSslHostCheck"
0x1400df69f  call    UxReadBooleanSetting
0x1400df6a4  mov     rcx, [rbp+KeyHandle]
0x1400df6a8  lea     r9, [r13+1FE6h]
0x1400df6af  xor     r8d, r8d
0x1400df6b2  lea     rdx, aDisableocspsta; "DisableOcspStapling"
0x1400df6b9  call    UxReadBooleanSetting
0x1400df6be  cmp     cs:UxKirAddDisableAiaFlag, sil
0x1400df6c5  lea     rax, [r13+1FE7h]
0x1400df6cc  jz      short loc_1400DF6E6
0x1400df6ce  mov     rcx, [rbp+KeyHandle]
0x1400df6d2  lea     rdx, aDisableaia; "DisableAia"
  ... truncated ...
```
