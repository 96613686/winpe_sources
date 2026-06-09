# UxStartEnvironmentFacet

- ea: `0x1c00d7630`
- end: `0x1c00d7ec2`
- name: `UxStartEnvironmentFacet`
- size: `2194`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1c00d69a8`
- `0x1c00d6c00`
- `0x1c00d6fe0`
- `0x1c00d72d4`
- `0x1c00d75ec`
- `0x1c00d7630`
- `0x1c00d7ec8`
- `0x1c00d7f38`
- `0x1c00d8344`
- `0x1c0114ff0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1c00d76d4`
- `ntoskrnl!ZwOpenKey` at `0x1c00d76d4`
- `ntoskrnl!ZwClose` at `0x1c00d7e8c`
- `ntoskrnl!ZwClose` at `0x1c00d7e8c`

## string_xrefs

- `0x1c00d773a`: `BasicTokenCacheTTL`
- `0x1c00d7811`: `UriEnableCache`
- `0x1c00d7839`: `UriMaxCacheMegabyteCount`
- `0x1c00d7856`: `UriMaxUriBytes`
- `0x1c00d78c2`: `UriCacheRangeChunk`
- `0x1c00d792d`: `UriScavengerPeriod`
- `0x1c00d795a`: `UriEnableRangeCache`
- `0x1c00d79a8`: `EnableSslTokenBinding`
- `0x1c00d7a9d`: `DisableSslClientCertChainCacheOnlyUrlRetrieval`
- `0x1c00d765f`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters`
- `0x1c00d7d40`: `Http2MaxWindowUpdatesPerSend`

## pseudocode

```c
__int64 __fastcall UxStartEnvironmentFacet(__int64 a1)
{
  __int64 v1; // rdi
  int ComputerName; // ebx
  __int64 v4; // rax
  NTSTATUS v5; // eax
  void *v6; // rcx
  bool v7; // r12
  int v8; // ecx
  int LongParameter; // eax
  void *v10; // rcx
  int v11; // eax
  bool v12; // al
  unsigned int v13; // eax
  void *v14; // rcx
  int v15; // eax
  bool v16; // al
  int v17; // eax
  bool v18; // al
  int v19; // ecx
  unsigned int v20; // edx
  unsigned int v21; // ecx
  unsigned int v22; // edx
  unsigned int v23; // ecx
  int v24; // ecx
  int v25; // eax
  bool v26; // al
  int v27; // r8d
  int v28; // r9d
  int v29; // r8d
  int v30; // r9d
  int v31; // r8d
  int v32; // r9d
  int v33; // r8d
  int v34; // r9d
  int v35; // r8d
  int v36; // r9d
  void *v37; // rcx
  int v38; // eax
  bool v39; // al
  int v40; // eax
  bool v41; // al
  int v42; // eax
  bool v43; // al
  int v44; // eax
  bool v45; // al
  int v46; // eax
  bool v47; // al
  int v48; // eax
  bool v49; // al
  int v50; // ecx
  int v51; // eax
  int v52; // ecx
  __int64 v53; // rax
  int v54; // ecx
  void *v55; // rcx
  int v56; // eax
  int v57; // eax
  bool v58; // al
  int v60; // [rsp+20h] [rbp-60h]
  int v61; // [rsp+20h] [rbp-60h]
  int v62; // [rsp+20h] [rbp-60h]
  int v63; // [rsp+20h] [rbp-60h]
  int v64; // [rsp+20h] [rbp-60h]
  int v65; // [rsp+28h] [rbp-58h]
  int v66; // [rsp+28h] [rbp-58h]
  int v67; // [rsp+28h] [rbp-58h]
  int v68; // [rsp+28h] [rbp-58h]
  int v69; // [rsp+28h] [rbp-58h]
  _QWORD v70[2]; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  int Http11ParserSettings; // [rsp+C0h] [rbp+40h]
  void *KeyHandle; // [rsp+C8h] [rbp+48h] BYREF

  v70[0] = 8913030;
  v1 = a1 + 3280;
  KeyHandle = 0;
  v70[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Http\\Parameters";
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ComputerName = UxGetComputerName((NTSTRSAFE_PWSTR)(a1 + 3280));
  if ( ComputerName >= 0 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(v1 + 2 * v4) );
    *(_DWORD *)(a1 + 3796) = v4;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v70;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v5 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    v6 = KeyHandle;
    if ( v5 < 0 )
      v6 = 0;
    KeyHandle = v6;
    UxTlCreateListenAddressList(a1);
    UxReadErrorLogSettings(a1, KeyHandle);
    Http11ParserSettings = UxReadHttp11ParserSettings(a1, KeyHandle);
    ComputerName = Http11ParserSettings;
    if ( Http11ParserSettings >= 0 )
    {
      v7 = 1;
      v8 = (int)KeyHandle;
      if ( !UxCompactMode )
      {
        if ( KeyHandle )
        {
          LongParameter = UlReadLongParameter(KeyHandle, L"BasicTokenCacheTTL", 1);
          v8 = (int)KeyHandle;
          *(_BYTE *)(a1 + 92) = LongParameter != 0;
        }
        else
        {
          *(_BYTE *)(a1 + 92) = 1;
        }
      }
      UxReadBoundedULongSetting(v8, (unsigned int)L"DisableServerHeader", 0, 0, 2, 0, a1 + 4160);
      v10 = KeyHandle;
      if ( KeyHandle )
      {
        v11 = UlReadLongParameter(KeyHandle, L"DisableErrorResponse", 0);
        v10 = KeyHandle;
        v12 = v11 != 0;
      }
      else
      {
        v12 = 0;
      }
      *(_BYTE *)(a1 + 4156) = v12;
      v13 = UlReadLongParameter(v10, L"MaxBufferedSendBytes", 0xFFFFFFFFLL);
      v14 = KeyHandle;
      if ( v13 > 0xFFFFF )
        v13 = -1;
      *(_DWORD *)(a1 + 4172) = v13;
      if ( v14 )
      {
        v15 = UlReadLongParameter(v14, L"ExpandedSendBuffering", 0);
        v14 = KeyHandle;
        v16 = v15 != 0;
      }
      else
      {
        v16 = 0;
      }
      *(_DWORD *)(a1 + 4176) = v16 ? 0x1000000 : 0xFFFFF;
      if ( v14 )
      {
        v17 = UlReadLongParameter(v14, L"UriEnableCache", 1);
        LODWORD(v14) = (_DWORD)KeyHandle;
        v18 = v17 != 0;
      }
      else
      {
        v18 = 1;
      }
      *(_BYTE *)(a1 + 1088) = v18;
      UxReadBoundedULongSetting((_DWORD)v14, (unsigned int)L"UriMaxCacheMegabyteCount", 0, 0, -1, 0, a1 + 1092);
      v19 = (int)KeyHandle;
      *(_QWORD *)(a1 + 1096) = (unsigned __int64)*(unsigned int *)(a1 + 1092) << 20;
      UxReadBoundedULongSetting(v19, (unsigned int)L"UriMaxUriBytes", 0x40000, 4096, 0x1000000, 0, a1 + 1108);
      v20 = *(_DWORD *)(a1 + 1108);
      v21 = 1;
      if ( !v20 )
        goto LABEL_22;
      do
      {
        if ( v21 == 0x10000000 )
          break;
        v21 *= 2;
      }
      while ( v21 <= v20 );
      if ( v21 > v20 )
      {
LABEL_22:
        if ( ((v21 >> 2) & v20) == 0 )
          v21 >>= 1;
      }
      *(_DWORD *)(a1 + 1108) = v21;
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"UriCacheRangeChunk",
        0x10000,
        4096,
        v21,
        2,
        a1 + 1112);
      v22 = *(_DWORD *)(a1 + 1112);
      v23 = 1;
      if ( !v22 )
        goto LABEL_28;
      do
      {
        if ( v23 == 0x10000000 )
          break;
        v23 *= 2;
      }
      while ( v23 <= v22 );
      if ( v23 > v22 )
      {
LABEL_28:
        if ( ((v23 >> 2) & v22) == 0 )
          v23 >>= 1;
      }
      *(_DWORD *)(a1 + 1112) = v23;
      UxReadBoundedULongSetting((_DWORD)KeyHandle, (unsigned int)L"UriScavengerPeriod", 120, 10, -1, 1, a1 + 1104);
      v24 = (int)KeyHandle;
      if ( KeyHandle )
      {
        v25 = UlReadLongParameter(KeyHandle, L"UriEnableRangeCache", 0);
        v24 = (int)KeyHandle;
        v26 = v25 != 0;
      }
      else
      {
        v26 = 0;
      }
      *(_BYTE *)(a1 + 1089) = v26;
      UxReadBoundedULongSetting(v24, (unsigned int)L"MaxConnections", -1, 0, -1, 0, a1 + 7316);
      UxReadBoundedLongSetting((_DWORD)KeyHandle, (unsigned int)L"EnableSslTokenBinding", v27, v28, v60, v65, a1 + 7100);
      UxReadBoundedLongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"EnableSslSessionTicket",
        v29,
        v30,
        v61,
        v66,
        a1 + 7104);
      UxReadBoundedLongSetting((_DWORD)KeyHandle, (unsigned int)L"DisableTls12", v31, v32, v62, v67, a1 + 7088);
      UxReadBoundedLongSetting((_DWORD)KeyHandle, (unsigned int)L"DisableLegacyTls", v33, v34, v63, v68, a1 + 7092);
      UxReadBoundedLongSetting((_DWORD)KeyHandle, (unsigned int)L"DisableTls13", v35, v36, v64, v69, a1 + 7096);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"CertificateScavengerPeriod",
        1800,
        0,
        -1,
        0,
        a1 + 7108);
      if ( (unsigned int)(*(_DWORD *)(a1 + 7108) - 1) <= 0x76 )
        *(_DWORD *)(a1 + 7108) = 120;
      v37 = KeyHandle;
      if ( KeyHandle )
      {
        v38 = UlReadLongParameter(KeyHandle, L"EnableSslCloseNotify", 0);
        v37 = KeyHandle;
        v39 = v38 != 0;
      }
      else
      {
        v39 = 0;
      }
      *(_BYTE *)(a1 + 7082) = v39;
      if ( v37 )
      {
        v40 = UlReadLongParameter(v37, L"DisableSslClientCertChainCacheOnlyUrlRetrieval", 0);
        v37 = KeyHandle;
        v41 = v40 != 0;
      }
      else
      {
        v41 = 0;
      }
      *(_BYTE *)(a1 + 7081) = v41;
      if ( v37 )
      {
        v42 = UlReadLongParameter(v37, L"EnableSslHostCheck", 0);
        v37 = KeyHandle;
        v43 = v42 != 0;
      }
      else
      {
        v43 = 0;
      }
      *(_BYTE *)(a1 + 7084) = v43;
      if ( v37 )
      {
        v44 = UlReadLongParameter(v37, L"DisableOcspStapling", 0);
        v37 = KeyHandle;
        v45 = v44 != 0;
      }
      else
      {
        v45 = 0;
      }
      *(_BYTE *)(a1 + 7086) = v45;
      if ( v37 )
      {
        v46 = UlReadLongParameter(v37, L"EnableHttp2Tls", 1);
        v37 = KeyHandle;
        v47 = v46 != 0;
      }
      else
      {
        v47 = 1;
      }
      *(_BYTE *)(a1 + 6892) = v47;
      if ( v37 )
      {
        v48 = UlReadLongParameter(v37, L"EnableHttp2Icw", 0);
        LODWORD(v37) = (_DWORD)KeyHandle;
        v49 = v48 != 0;
      }
      else
      {
        v49 = 0;
      }
      *(_BYTE *)(a1 + 6894) = v49;
      UxReadBoundedULongSetting(
        (_DWORD)v37,
        (unsigned int)L"Http2WindowSize",
        0xFFFF,
        0x100000,
        0x7FFFFFFF,
        0,
        a1 + 6924);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2MaxConcurrentClientStreams",
        100,
        0,
        -1,
        0,
        a1 + 6916);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2MaxSettingsPerFrame",
        2796202,
        7,
        2796202,
        3,
        a1 + 6928);
      UxReadBoundedULongSetting((_DWORD)KeyHandle, (unsigned int)L"Http2MaxSettingsPerMinute", -1, 7, -1, 3, a1 + 6932);
      UxReadBoundedULongSetting((_DWORD)KeyHandle, (unsigned int)L"Http2MaxPingsPerMinute", 0, 0, 255, 2, a1 + 6936);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2MaxServerResetsPerMinute",
        0,
        0,
        0xFFFF,
        2,
        a1 + 6952);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2MaxPrioritiesPerStream",
        0,
        0,
        255,
        2,
        a1 + 6940);
      UxReadBoundedULongSetting((_DWORD)KeyHandle, (unsigned int)L"Http2MaxResetsPerStream", 0, 0, 255, 2, a1 + 6944);
      UxReadBoundedULongSetting((_DWORD)KeyHandle, (unsigned int)L"Http2MaxUnknownsPerStream", 0, 0, 255, 2, a1 + 6948);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2MinimumSendWindowSize",
        0,
        0,
        0xFFFF,
        2,
        a1 + 7000);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2MaxWindowUpdatesPerSend",
        0,
        0,
        255,
        2,
        a1 + 6984);
      v50 = *(_DWORD *)(a1 + 6916);
      *(_QWORD *)(a1 + 6960) = (unsigned int)(4 * *(_DWORD *)(a1 + 6940) * v50);
      *(_QWORD *)(a1 + 6968) = (unsigned int)(4 * *(_DWORD *)(a1 + 6948) * v50);
      v51 = *(_DWORD *)(a1 + 6944) * v50;
      v52 = *(_DWORD *)(a1 + 6984) * v50;
      *(_QWORD *)(a1 + 6976) = (unsigned int)(4 * v51);
      v53 = (unsigned int)(4 * v52);
      v54 = (int)KeyHandle;
      *(_QWORD *)(a1 + 6992) = v53;
      UxReadBoundedULongSetting(v54, (unsigned int)L"Http2SettingsAckTimeout", 10, 0, -1, 0, a1 + 6920);
      UxReadBoundedULongSetting(
        (_DWORD)KeyHandle,
        (unsigned int)L"Http2SettingsMaxPendingBytes",
        0,
        0,
        -1,
        0,
        a1 + 6912);
      v55 = KeyHandle;
      if ( KeyHandle )
      {
        v56 = UlReadLongParameter(KeyHandle, L"Http2SettingsAckCheck", 1);
        v55 = KeyHandle;
        v7 = v56 != 0;
      }
      *(_BYTE *)(a1 + 6895) = v7;
      if ( v55 )
      {
        v57 = UlReadLongParameter(v55, L"ClientSessionEnable", 0);
        LODWORD(v55) = (_DWORD)KeyHandle;
        v58 = v57 != 0;
      }
      else
      {
        v58 = 0;
      }
      *(_BYTE *)(a1 + 7616) = v58;
      UxReadBoundedULongSetting((_DWORD)v55, (unsigned int)L"Http3MaxBlockedStreams", 100, 0, -1, 3, a1 + 7008);
      HttpCmnInitializeDynamicHttpCharsTable(a1);
      ComputerName = Http11ParserSettings;
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
0x1c00d7630  mov     [rsp-38h+arg_10], rbx
0x1c00d7635  push    rbp
0x1c00d7636  push    rsi
0x1c00d7637  push    rdi
0x1c00d7638  push    r12
0x1c00d763a  push    r13
0x1c00d763c  push    r14
0x1c00d763e  push    r15
0x1c00d7640  mov     rbp, rsp
0x1c00d7643  sub     rsp, 80h
0x1c00d764a  xorps   xmm0, xmm0
0x1c00d764d  mov     [rbp+var_40], 880086h
0x1c00d7655  lea     rdi, [rcx+0CD0h]
0x1c00d765c  mov     r13, rcx
0x1c00d765f  lea     rax, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x1c00d7666  xor     esi, esi
0x1c00d7668  mov     rcx, rdi; pszDest
0x1c00d766b  mov     [rbp+KeyHandle], rsi
0x1c00d766f  mov     [rbp+var_38], rax
0x1c00d7673  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1c00d7677  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1c00d767b  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1c00d767f  call    UxGetComputerName
0x1c00d7684  mov     ebx, eax
0x1c00d7686  test    eax, eax
0x1c00d7688  js      loc_1C00D7E83
0x1c00d768e  or      r14, 0FFFFFFFFFFFFFFFFh
0x1c00d7692  mov     rax, r14
0x1c00d7695  inc     rax
0x1c00d7698  cmp     [rdi+rax*2], si
0x1c00d769c  jnz     short loc_1C00D7695
0x1c00d769e  mov     [r13+0ED4h], eax
0x1c00d76a5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1c00d76a9  lea     rax, [rbp+var_40]
0x1c00d76ad  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1c00d76b4  xorps   xmm0, xmm0
0x1c00d76b7  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1c00d76bb  mov     edx, 20019h; DesiredAccess
0x1c00d76c0  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x1c00d76c4  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1c00d76c8  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1c00d76cf  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1c00d76d4  call    cs:__imp_ZwOpenKey
0x1c00d76db  nop     dword ptr [rax+rax+00h]
0x1c00d76e0  mov     rcx, [rbp+KeyHandle]
0x1c00d76e4  test    eax, eax
0x1c00d76e6  cmovs   rcx, rsi
0x1c00d76ea  mov     [rbp+KeyHandle], rcx
0x1c00d76ee  mov     rcx, r13
0x1c00d76f1  call    UxTlCreateListenAddressList
0x1c00d76f6  mov     rdx, [rbp+KeyHandle]
0x1c00d76fa  mov     rcx, r13
0x1c00d76fd  call    UxReadErrorLogSettings
0x1c00d7702  mov     rdx, [rbp+KeyHandle]
0x1c00d7706  mov     rcx, r13
0x1c00d7709  call    UxReadHttp11ParserSettings
0x1c00d770e  mov     [rbp+arg_0], eax
0x1c00d7711  mov     ebx, eax
0x1c00d7713  test    eax, eax
0x1c00d7715  js      loc_1C00D7E83
0x1c00d771b  cmp     cs:UxCompactMode, sil
0x1c00d7722  mov     r12d, 1
0x1c00d7728  mov     rcx, [rbp+KeyHandle]
0x1c00d772c  jnz     short loc_1C00D7753
0x1c00d772e  test    rcx, rcx
0x1c00d7731  jz      loc_1C00FCE60
0x1c00d7737  mov     r8d, r12d
0x1c00d773a  lea     rdx, aBasictokencach; "BasicTokenCacheTTL"
0x1c00d7741  call    UlReadLongParameter
0x1c00d7746  mov     rcx, [rbp+KeyHandle]
0x1c00d774a  test    eax, eax
0x1c00d774c  setnz   al
0x1c00d774f  mov     [r13+5Ch], al
0x1c00d7753  lea     rax, [r13+1040h]
0x1c00d775a  xor     r9d, r9d
0x1c00d775d  mov     [rsp+80h+var_50], rax
0x1c00d7762  lea     rdx, aDisableserverh; "DisableServerHeader"
0x1c00d7769  mov     [rsp+80h+var_58], esi
0x1c00d776d  xor     r8d, r8d
0x1c00d7770  mov     [rsp+80h+var_60], 2
0x1c00d7778  call    UxReadBoundedULongSetting
0x1c00d777d  mov     rcx, [rbp+KeyHandle]
0x1c00d7781  test    rcx, rcx
0x1c00d7784  jz      loc_1C00FCE69
0x1c00d778a  xor     r8d, r8d
0x1c00d778d  lea     rdx, aDisableerrorre; "DisableErrorResponse"
0x1c00d7794  call    UlReadLongParameter
0x1c00d7799  mov     rcx, [rbp+KeyHandle]
0x1c00d779d  test    eax, eax
0x1c00d779f  setnz   al
0x1c00d77a2  mov     r8d, r14d
0x1c00d77a5  mov     [r13+103Ch], al
0x1c00d77ac  lea     rdx, aMaxbufferedsen; "MaxBufferedSendBytes"
0x1c00d77b3  call    UlReadLongParameter
0x1c00d77b8  mov     rcx, [rbp+KeyHandle]
0x1c00d77bc  or      r14d, 0FFFFFFFFh
0x1c00d77c0  mov     ebx, 0FFFFFh
0x1c00d77c5  cmp     eax, ebx
0x1c00d77c7  cmova   eax, r14d
0x1c00d77cb  mov     [r13+104Ch], eax
0x1c00d77d2  test    rcx, rcx
0x1c00d77d5  jz      loc_1C00FCE71
0x1c00d77db  xor     r8d, r8d
0x1c00d77de  lea     rdx, aExpandedsendbu; "ExpandedSendBuffering"
0x1c00d77e5  call    UlReadLongParameter
0x1c00d77ea  mov     rcx, [rbp+KeyHandle]
0x1c00d77ee  test    eax, eax
0x1c00d77f0  setnz   al
0x1c00d77f3  neg     al
0x1c00d77f5  sbb     eax, eax
0x1c00d77f7  and     eax, 0F00001h
0x1c00d77fc  add     eax, ebx
0x1c00d77fe  mov     [r13+1050h], eax
0x1c00d7805  test    rcx, rcx
0x1c00d7808  jz      loc_1C00FCE79
0x1c00d780e  mov     r8d, r12d
0x1c00d7811  lea     rdx, aUrienablecache; "UriEnableCache"
0x1c00d7818  call    UlReadLongParameter
0x1c00d781d  mov     rcx, [rbp+KeyHandle]
0x1c00d7821  test    eax, eax
0x1c00d7823  setnz   al
0x1c00d7826  lea     rbx, [r13+444h]
0x1c00d782d  mov     [r13+440h], al
0x1c00d7834  mov     [rsp+80h+var_50], rbx
0x1c00d7839  lea     rdx, aUrimaxcachemeg; "UriMaxCacheMegabyteCount"
0x1c00d7840  mov     [rsp+80h+var_58], esi
0x1c00d7844  xor     r9d, r9d
0x1c00d7847  xor     r8d, r8d
0x1c00d784a  mov     [rsp+80h+var_60], r14d
0x1c00d784f  call    UxReadBoundedULongSetting
0x1c00d7854  mov     eax, [rbx]
0x1c00d7856  lea     rdx, aUrimaxuribytes; "UriMaxUriBytes"
0x1c00d785d  mov     rcx, [rbp+KeyHandle]
0x1c00d7861  lea     rbx, [r13+454h]
0x1c00d7868  mov     [rsp+80h+var_50], rbx
0x1c00d786d  mov     r15d, 1000h
0x1c00d7873  shl     rax, 14h
0x1c00d7877  mov     r9d, r15d
0x1c00d787a  mov     [rsp+80h+var_58], esi
0x1c00d787e  mov     r8d, 40000h
0x1c00d7884  mov     [rsp+80h+var_60], 1000000h
0x1c00d788c  mov     [r13+448h], rax
0x1c00d7893  call    UxReadBoundedULongSetting
0x1c00d7898  mov     edx, [rbx]
0x1c00d789a  mov     ecx, r12d
0x1c00d789d  mov     edi, 10000000h
0x1c00d78a2  cmp     edx, r12d
0x1c00d78a5  jb      short loc_1C00D78B5
0x1c00d78a7  cmp     ecx, edi
0x1c00d78a9  jz      short loc_1C00D78B1
0x1c00d78ab  add     ecx, ecx
0x1c00d78ad  cmp     ecx, edx
0x1c00d78af  jbe     short loc_1C00D78A7
0x1c00d78b1  cmp     ecx, edx
0x1c00d78b3  jbe     short loc_1C00D78C0
0x1c00d78b5  mov     eax, ecx
0x1c00d78b7  shr     eax, 2
0x1c00d78ba  test    edx, eax
0x1c00d78bc  jnz     short loc_1C00D78C0
0x1c00d78be  shr     ecx, 1
0x1c00d78c0  mov     [rbx], ecx
0x1c00d78c2  lea     rdx, aUricacherangec; "UriCacheRangeChunk"
0x1c00d78c9  lea     rbx, [r13+458h]
0x1c00d78d0  mov     r9d, r15d
0x1c00d78d3  mov     [rsp+80h+var_50], rbx
0x1c00d78d8  mov     r8d, 10000h
0x1c00d78de  mov     [rsp+80h+var_58], 2
0x1c00d78e6  mov     [rsp+80h+var_60], ecx
0x1c00d78ea  mov     rcx, [rbp+KeyHandle]
0x1c00d78ee  call    UxReadBoundedULongSetting
0x1c00d78f3  mov     edx, [rbx]
0x1c00d78f5  mov     ecx, r12d
0x1c00d78f8  cmp     edx, r12d
0x1c00d78fb  jb      short loc_1C00D790B
0x1c00d78fd  cmp     ecx, edi
0x1c00d78ff  jz      short loc_1C00D7907
0x1c00d7901  add     ecx, ecx
0x1c00d7903  cmp     ecx, edx
0x1c00d7905  jbe     short loc_1C00D78FD
0x1c00d7907  cmp     ecx, edx
0x1c00d7909  jbe     short loc_1C00D7916
0x1c00d790b  mov     eax, ecx
0x1c00d790d  shr     eax, 2
0x1c00d7910  test    edx, eax
0x1c00d7912  jnz     short loc_1C00D7916
0x1c00d7914  shr     ecx, 1
0x1c00d7916  mov     edi, 78h ; 'x'
0x1c00d791b  mov     [rbx], ecx
0x1c00d791d  mov     rcx, [rbp+KeyHandle]
0x1c00d7921  lea     rax, [r13+450h]
0x1c00d7928  mov     [rsp+80h+var_50], rax
0x1c00d792d  lea     rdx, aUriscavengerpe; "UriScavengerPeriod"
0x1c00d7934  mov     [rsp+80h+var_58], r12d
0x1c00d7939  mov     r8d, edi
0x1c00d793c  lea     r9d, [rdi-6Eh]
0x1c00d7940  mov     [rsp+80h+var_60], r14d
0x1c00d7945  call    UxReadBoundedULongSetting
0x1c00d794a  mov     rcx, [rbp+KeyHandle]
0x1c00d794e  test    rcx, rcx
0x1c00d7951  jz      loc_1C00FCE81
0x1c00d7957  xor     r8d, r8d
0x1c00d795a  lea     rdx, aUrienablerange; "UriEnableRangeCache"
0x1c00d7961  call    UlReadLongParameter
0x1c00d7966  mov     rcx, [rbp+KeyHandle]
0x1c00d796a  test    eax, eax
0x1c00d796c  setnz   al
0x1c00d796f  mov     [r13+441h], al
0x1c00d7976  lea     rdx, aMaxconnections; "MaxConnections"
0x1c00d797d  lea     rax, [r13+1C94h]
0x1c00d7984  xor     r9d, r9d
0x1c00d7987  mov     [rsp+80h+var_50], rax
0x1c00d798c  mov     r8d, r14d
0x1c00d798f  mov     [rsp+80h+var_58], esi
0x1c00d7993  mov     [rsp+80h+var_60], r14d
0x1c00d7998  call    UxReadBoundedULongSetting
0x1c00d799d  mov     rcx, [rbp+KeyHandle]
0x1c00d79a1  lea     rax, [r13+1BBCh]
0x1c00d79a8  lea     rdx, aEnablessltoken; "EnableSslTokenBinding"
0x1c00d79af  mov     [rsp+80h+var_50], rax
0x1c00d79b4  call    UxReadBoundedLongSetting
0x1c00d79b9  mov     rcx, [rbp+KeyHandle]
0x1c00d79bd  lea     rax, [r13+1BC0h]
0x1c00d79c4  lea     rdx, aEnablesslsessi; "EnableSslSessionTicket"
0x1c00d79cb  mov     [rsp+80h+var_50], rax
0x1c00d79d0  call    UxReadBoundedLongSetting
0x1c00d79d5  mov     rcx, [rbp+KeyHandle]
0x1c00d79d9  lea     rax, [r13+1BB0h]
0x1c00d79e0  lea     rdx, aDisabletls12; "DisableTls12"
0x1c00d79e7  mov     [rsp+80h+var_50], rax
0x1c00d79ec  call    UxReadBoundedLongSetting
0x1c00d79f1  mov     rcx, [rbp+KeyHandle]
0x1c00d79f5  lea     rax, [r13+1BB4h]
0x1c00d79fc  lea     rdx, aDisablelegacyt; "DisableLegacyTls"
0x1c00d7a03  mov     [rsp+80h+var_50], rax
0x1c00d7a08  call    UxReadBoundedLongSetting
0x1c00d7a0d  mov     rcx, [rbp+KeyHandle]
0x1c00d7a11  lea     rax, [r13+1BB8h]
0x1c00d7a18  lea     rdx, aDisabletls13; "DisableTls13"
0x1c00d7a1f  mov     [rsp+80h+var_50], rax
0x1c00d7a24  call    UxReadBoundedLongSetting
0x1c00d7a29  mov     rcx, [rbp+KeyHandle]
0x1c00d7a2d  lea     rbx, [r13+1BC4h]
0x1c00d7a34  mov     [rsp+80h+var_50], rbx
0x1c00d7a39  lea     rdx, aCertificatesca; "CertificateScavengerPeriod"
0x1c00d7a40  mov     [rsp+80h+var_58], esi
0x1c00d7a44  xor     r9d, r9d
0x1c00d7a47  mov     r8d, 708h
0x1c00d7a4d  mov     [rsp+80h+var_60], r14d
0x1c00d7a52  call    UxReadBoundedULongSetting
0x1c00d7a57  mov     eax, [rbx]
0x1c00d7a59  sub     eax, r12d
0x1c00d7a5c  cmp     eax, 76h ; 'v'
0x1c00d7a5f  jbe     loc_1C00FCE89
0x1c00d7a65  mov     rcx, [rbp+KeyHandle]
0x1c00d7a69  test    rcx, rcx
0x1c00d7a6c  jz      loc_1C00FCE90
0x1c00d7a72  xor     r8d, r8d
0x1c00d7a75  lea     rdx, aEnablesslclose; "EnableSslCloseNotify"
0x1c00d7a7c  call    UlReadLongParameter
0x1c00d7a81  mov     rcx, [rbp+KeyHandle]
0x1c00d7a85  test    eax, eax
0x1c00d7a87  setnz   al
0x1c00d7a8a  mov     [r13+1BAAh], al
0x1c00d7a91  test    rcx, rcx
0x1c00d7a94  jz      loc_1C00FCE98
0x1c00d7a9a  xor     r8d, r8d
0x1c00d7a9d  lea     rdx, aDisablesslclie; "DisableSslClientCertChainCacheOnlyUrlRe"...
0x1c00d7aa4  call    UlReadLongParameter
0x1c00d7aa9  mov     rcx, [rbp+KeyHandle]
0x1c00d7aad  test    eax, eax
0x1c00d7aaf  setnz   al
0x1c00d7ab2  mov     [r13+1BA9h], al
0x1c00d7ab9  test    rcx, rcx
0x1c00d7abc  jz      loc_1C00FCEA0
0x1c00d7ac2  xor     r8d, r8d
0x1c00d7ac5  lea     rdx, aEnablesslhostc; "EnableSslHostCheck"
0x1c00d7acc  call    UlReadLongParameter
0x1c00d7ad1  mov     rcx, [rbp+KeyHandle]
0x1c00d7ad5  test    eax, eax
0x1c00d7ad7  setnz   al
0x1c00d7ada  mov     [r13+1BACh], al
0x1c00d7ae1  test    rcx, rcx
0x1c00d7ae4  jz      loc_1C00FCEA8
0x1c00d7aea  xor     r8d, r8d
0x1c00d7aed  lea     rdx, aDisableocspsta; "DisableOcspStapling"
0x1c00d7af4  call    UlReadLongParameter
0x1c00d7af9  mov     rcx, [rbp+KeyHandle]
0x1c00d7afd  test    eax, eax
0x1c00d7aff  setnz   al
0x1c00d7b02  mov     [r13+1BAEh], al
0x1c00d7b09  test    rcx, rcx
0x1c00d7b0c  jz      loc_1C00FCEB0
0x1c00d7b12  mov     r8d, r12d
0x1c00d7b15  lea     rdx, aEnablehttp2tls; "EnableHttp2Tls"
0x1c00d7b1c  call    UlReadLongParameter
0x1c00d7b21  mov     rcx, [rbp+KeyHandle]
0x1c00d7b25  test    eax, eax
0x1c00d7b27  setnz   al
0x1c00d7b2a  mov     [r13+1AECh], al
0x1c00d7b31  test    rcx, rcx
  ... truncated ...
```
