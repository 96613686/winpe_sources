# Dns_NegotiateTkeyWithServer

- ea: `0x18006adbc`
- end: `0x18006b6fe`
- name: `Dns_NegotiateTkeyWithServer`
- size: `2370`
- prototype: `__int64 __fastcall(int, int, int, int, void *pAuthData)`
- caller_count: `1`
- callee_count: `42`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180069ce0`

## callees

- `0x18002b050`
- `0x180053404`
- `0x1800556e8`
- `0x18005ca78`
- `0x18005f1e8`
- `0x18005f3b0`
- `0x180062f60`
- `0x1800662b0`
- `0x180068fac`
- `0x180069548`
- `0x18006a11c`
- `0x18006a814`
- `0x18006adbc`
- `0x18006e2b4`
- `0x180073b7c`
- `0x18007d72c`
- `0x18007e524`
- `0x180080814`
- `0x180080d68`
- `0x180083954`
- `0x18008555c`
- `0x180086e4c`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800a63f4`
- `0x1800a65a0`
- `0x1800a6668`
- `0x1800a69dc`
- `0x1800a6cc0`
- `0x1800a7190`
- `0x1800a74ec`
- `0x1800cc234`
- `0x1800cd0e8`
- `0x1800d22b8`
- `0x1800d42dc`
- `0x1800d46e0`
- `0x1800d4da4`
- `0x1800dc27c`
- `0x1800dc9e0`
- `0x1800ddfa8`
- `0x1800de650`
- `0x1800e1b10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b17c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b17c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006aee8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006aee8`

## string_xrefs

- `0x18006afe4`: `User specified FORCE_SECURITY_NEGO flag.`
- `0x18006afdd`: `Incomplete negotiation key exists.`

## pseudocode

```c
__int64 __fastcall Dns_NegotiateTkeyWithServer(__int64 *a1, int a2, __int64 a3, __int64 a4, void *pAuthData)
{
  __int64 v7; // rdi
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  __int64 v11; // r15
  void *v12; // r13
  __int64 v13; // rsi
  unsigned int started; // eax
  unsigned int v15; // ebx
  void *CredKey; // rax
  DWORD CurrentProcessId; // eax
  unsigned __int64 v18; // rax
  __int128 v19; // xmm0
  __int128 v20; // xmm3
  __int128 v21; // xmm2
  __int64 v22; // rax
  int v23; // r8d
  int v24; // ecx
  const char *v25; // rax
  __int128 v26; // xmm1
  _OWORD *v27; // r12
  __int128 v28; // xmm3
  __int128 v29; // xmm2
  __int64 v30; // rax
  __int64 MsgBuf; // rax
  __int64 v32; // rax
  __int64 v33; // rdx
  DWORD LastError; // eax
  __int64 v35; // rax
  __int16 RandomXid; // ax
  __int64 v37; // rdx
  int inited; // eax
  int i; // ebx
  __int64 v40; // rax
  __int64 v41; // r14
  __int64 v42; // rax
  unsigned int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // rdx
  char v46; // al
  unsigned int v47; // eax
  int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // eax
  int v51; // edx
  int v52; // r8d
  void *v54; // [rsp+40h] [rbp-C0h]
  int v55; // [rsp+48h] [rbp-B8h]
  int v56; // [rsp+4Ch] [rbp-B4h] BYREF
  int v57; // [rsp+50h] [rbp-B0h]
  __int64 v58; // [rsp+58h] [rbp-A8h]
  LPVOID lpMem; // [rsp+60h] [rbp-A0h]
  __int64 v60; // [rsp+68h] [rbp-98h]
  __int64 v61; // [rsp+70h] [rbp-90h]
  _OWORD *v62; // [rsp+78h] [rbp-88h]
  __int64 *v63; // [rsp+80h] [rbp-80h]
  __int128 Buf1; // [rsp+90h] [rbp-70h] BYREF
  __int128 v65; // [rsp+A0h] [rbp-60h]
  __int128 v66; // [rsp+B0h] [rbp-50h]
  __int128 v67; // [rsp+C0h] [rbp-40h]
  __int128 v68; // [rsp+D0h] [rbp-30h]
  void *v69; // [rsp+E0h] [rbp-20h]
  __int128 v70; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v71; // [rsp+100h] [rbp+0h]
  __int128 v72; // [rsp+110h] [rbp+10h]
  __int128 v73; // [rsp+120h] [rbp+20h]
  __int128 v74; // [rsp+130h] [rbp+30h]
  void *v75; // [rsp+140h] [rbp+40h]
  __int64 v76; // [rsp+150h] [rbp+50h] BYREF
  char v77[136]; // [rsp+158h] [rbp+58h] BYREF
  char pszDest[64]; // [rsp+1E0h] [rbp+E0h] BYREF

  v57 = a2;
  v63 = a1;
  v58 = a3;
  v61 = a4;
  v7 = 0;
  memset_0(&v76, 0, 0x90u);
  lpMem = 0;
  memset_0(&v70, 0, 0x58u);
  v11 = 0;
  v56 = 0;
  v12 = 0;
  v13 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
    WPP_SF_D_SOCKADDR_Sq(v9, v8, v10, v57, a4 + 32, a3, (__int64)pAuthData);
  memset_0(v77, 0, sizeof(v77));
  v76 = 0;
  if ( g_fVelocityDisableInternalExports )
    started = Dns_InitializeSecurityPackage();
  else
    started = Dns_StartSecurity(0);
  v15 = started;
  if ( started )
    goto LABEL_47;
  memset_0(&v70, 0, 0x58u);
  if ( pAuthData )
  {
    CredKey = (void *)MakeCredKey(pAuthData);
    lpMem = CredKey;
    if ( !CredKey )
    {
      if ( SBYTE3(xmmword_1801119E0) < 0 )
        WPP_SF_(1055, v15 + 97, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids);
      goto LABEL_11;
    }
    v75 = CredKey;
  }
  CurrentProcessId = GetCurrentProcessId();
  StringCbPrintfA(pszDest, 0x40u, "%d-ms-%d", CurrentProcessId, 7);
  if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
    WPP_SF_s(1038, 98, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids, pszDest);
  *((_QWORD *)&v74 + 1) = pszDest;
  if ( *(_DWORD *)(a4 + 4) )
  {
    do
    {
      v18 = (unsigned __int64)(unsigned int)v11 << 6;
      v19 = *(_OWORD *)(v18 + a4 + 80);
      v20 = *(_OWORD *)(v18 + a4 + 32);
      v21 = *(_OWORD *)(v18 + a4 + 48);
      v72 = *(_OWORD *)(v18 + a4 + 64);
      v73 = v19;
      v66 = v72;
      v67 = v19;
      v68 = v74;
      v69 = v75;
      v70 = v20;
      v71 = v21;
      Buf1 = v20;
      v65 = v21;
      v22 = Dns_DequeueSecurityContextByKey(&Buf1);
      v7 = v22;
      if ( v22 )
      {
        v24 = *(_DWORD *)(v22 + 148);
        if ( v24 && (v57 & 0x800) == 0 )
        {
          ++*(_DWORD *)(v22 + 152);
          if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
            WPP_SF_q(1038, 100, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids, v22);
          goto LABEL_29;
        }
        if ( SBYTE3(xmmword_1801119E0) < 0 )
        {
          v25 = "User specified FORCE_SECURITY_NEGO flag.";
          if ( !v24 )
            v25 = "Incomplete negotiation key exists.";
          WPP_SF__SOCKADDR_ss(
            v24,
            (unsigned int)"Incomplete negotiation key exists.",
            v23,
            (unsigned int)&v70,
            v74,
            (__int64)v25);
        }
        Dns_FreeSecurityContext((LPVOID)v7);
      }
      LODWORD(v11) = v11 + 1;
    }
    while ( (unsigned int)v11 < *(_DWORD *)(a4 + 4) );
  }
  v26 = *(_OWORD *)(a4 + 64);
  v27 = (_OWORD *)(a4 + 32);
  v62 = v27;
  v72 = v26;
  v66 = v26;
  v28 = *v27;
  v29 = v27[1];
  v73 = v27[3];
  v67 = v73;
  v68 = v74;
  v69 = v75;
  v70 = v28;
  v71 = v29;
  Buf1 = v28;
  v65 = v29;
  v30 = Dns_FindOrCreateSecurityContext(&Buf1);
  v7 = v30;
  if ( !v30 )
  {
    v15 = 2;
LABEL_29:
    v11 = 0;
    goto LABEL_47;
  }
  v76 = v30;
  *(_DWORD *)(v30 + 128) = 7;
  if ( pAuthData )
  {
    v15 = Dns_AcquireCredHandle((PCredHandle)(v30 + 112), pAuthData);
    if ( v15 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
        WPP_SF_(1038, 101, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids);
      goto LABEL_29;
    }
    *(_DWORD *)(v7 + 140) = 1;
  }
  MsgBuf = Packet_AllocateMsgBuf(0xFFFF);
  v11 = MsgBuf;
  v54 = (void *)MsgBuf;
  if ( g_fVelocityDnsKernelApi )
  {
    if ( !MsgBuf )
    {
LABEL_11:
      v15 = 14;
      goto LABEL_47;
    }
  }
  else if ( !MsgBuf )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    {
      v33 = 102;
      goto LABEL_43;
    }
LABEL_44:
    LastError = GetLastError();
    goto LABEL_45;
  }
  AddRefDnsMessage(MsgBuf);
  v32 = Packet_AllocateMsgBuf(0xFFFF);
  v13 = v32;
  if ( !v32 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    {
      v33 = 103;
LABEL_43:
      WPP_SF_(1035, v33, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  *(_BYTE *)(v32 + 648) = 1;
  *(_WORD *)(v32 + 653) = 0;
  *(_DWORD *)(v32 + 624) = 15000;
  *(_WORD *)(v32 + 698) = 0;
  *(_QWORD *)(v32 + 680) = 0;
  v35 = Packet_WriteQuestionToMessage(v11, *(_QWORD *)(v7 + 88), 249, 0);
  if ( !v35 )
  {
    v15 = 87;
    goto LABEL_47;
  }
  *(_BYTE *)(v11 + 702) &= 0x86u;
  v55 = 0;
  v60 = v35 - v11;
  RandomXid = Packet_GetRandomXid();
  v37 = v58;
  *(_WORD *)(v11 + 700) = RandomXid;
  v12 = (void *)v11;
  inited = Dns_InitClientSecurityContext(&v76, v37, &v56);
  v7 = v76;
  v15 = inited;
  if ( !inited )
    goto LABEL_87;
  while ( 2 )
  {
    if ( v15 != 9801 )
    {
LABEL_46:
      v11 = (__int64)v54;
      goto LABEL_47;
    }
    for ( i = v55; ; i = 1 )
    {
      v40 = Dns_CloneMsgBuf(v12);
      v41 = v40;
      if ( !v40 )
      {
        v15 = 14;
        goto LABEL_46;
      }
      AddRefDnsMessage(v40);
      if ( v12 != v54 )
        DeRefDnsMessage(v12);
      v12 = (void *)v41;
      if ( i )
      {
        v42 = v60;
        *(_DWORD *)(v7 + 128) = 3;
        *(_QWORD *)(v41 + 600) = v41 + v42;
        *(_WORD *)(v41 + 710) = 0;
        *(_WORD *)(v41 + 706) = 0;
      }
      v15 = Dns_WriteGssTkeyToMessage(&v76, v41 + 700, *(_QWORD *)(v41 + 592), v41 + 600);
      if ( v15 )
        goto LABEL_46;
      if ( v56 )
      {
        if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
          WPP_SF_q(1038, 107, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids, v41);
        if ( (unsigned int)Dns_SignMessageWithGssTsig(&v76, v41 + 700, *(_QWORD *)(v41 + 592), v41 + 600)
          && (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
        {
          WPP_SF_q(1038, 108, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids, v41);
        }
      }
      v43 = DnsSendSecureUpdate(v41, v13, 2, v61, 0);
      v15 = v43;
      if ( v43 == 1460 )
      {
        if ( v55 )
          goto LABEL_115;
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        {
          v45 = 109;
LABEL_73:
          WPP_SF_(1035, v45, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids);
          goto LABEL_74;
        }
        goto LABEL_74;
      }
      if ( v43 && !(unsigned __int8)Dns_IsStatusRcode(v43) )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_d(1035, 110, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids, v15);
        *(_BYTE *)(v13 + 703) &= 0xF2u;
        *(_BYTE *)(v13 + 703) |= 2u;
        goto LABEL_113;
      }
      *(_OWORD *)(v7 + 24) = *(_OWORD *)(v13 + 60);
      *(_OWORD *)(v7 + 40) = *(_OWORD *)(v13 + 76);
      *(_OWORD *)(v7 + 56) = *(_OWORD *)(v13 + 92);
      *(_OWORD *)(v7 + 72) = *(_OWORD *)(v13 + 108);
      v46 = BYTE1(xmmword_1801119E0);
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      {
        WPP_SF__SOCKADDR_(1035, 111, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids);
        v46 = BYTE1(xmmword_1801119E0);
      }
      if ( (*(_BYTE *)(v13 + 703) & 0xF) == 0 )
        break;
      if ( (*(_BYTE *)(v13 + 703) & 0xF) != 1 || v55 )
      {
        if ( (v46 & 8) != 0 )
          WPP_SF_d(1035, 113, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids, *(_BYTE *)(v13 + 703) & 0xF);
        goto LABEL_99;
      }
      if ( (v46 & 8) != 0 )
      {
        v45 = 112;
        goto LABEL_73;
      }
LABEL_74:
      v55 = 1;
    }
    v47 = Dns_ExtractGssTkeyFromMessage(&v76, v13 + 700, v13 + *(unsigned __int16 *)(v13 + 698) + 700LL);
    v15 = v47;
    if ( !v47 )
    {
      v48 = Dns_InitClientSecurityContext(&v76, v58, &v56);
      v7 = v76;
      v15 = v48;
      if ( v48 )
        continue;
      v27 = v62;
LABEL_87:
      if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
        WPP_SF_(1038, 104, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids);
      v49 = Dns_ExtractGssTsigFromMessage(&v76, v13 + 700, v13 + *(unsigned __int16 *)(v13 + 698) + 700LL);
      v15 = v49;
      if ( v49 )
      {
        if ( v49 == 9505 )
        {
          if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
            WPP_SF_q_SOCKADDR_(
              1038,
              106,
              (unsigned int)WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids,
              v13,
              (__int64)v27);
          v15 = 0;
        }
      }
      else
      {
        v50 = Dns_VerifySignatureOnPacket(&v76);
        v15 = v50;
        if ( v50 )
        {
          if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
            WPP_SF_q_SOCKADDR_D(v44, v51, v52, v13, (__int64)v27, v50);
          v15 = 9016;
        }
      }
      if ( !v12 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v44);
      if ( v15 )
      {
LABEL_112:
        if ( v15 == 1460 )
        {
LABEL_115:
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF__SOCKADDR_q(
              v44,
              115,
              (unsigned int)WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids,
              (_DWORD)v12 + 60,
              (__int64)v12);
        }
        else
        {
LABEL_113:
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF__SOCKADDR_qD(
              v44,
              116,
              (unsigned int)WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids,
              (_DWORD)v12 + 60,
              (__int64)v12,
              v15);
        }
        goto LABEL_46;
      }
LABEL_99:
      LastError = Dns_MapRcodeToStatus(*(_BYTE *)(v13 + 703) & 0xF);
LABEL_45:
      v15 = LastError;
      goto LABEL_46;
    }
    break;
  }
  if ( v47 != 9505 )
    goto LABEL_112;
  v11 = (__int64)v54;
  if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
    WPP_SF__SOCKADDR_(1038, 114, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids);
  v15 = 0;
LABEL_47:
  if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
    WPP_SF_d(1038, 117, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids, v15);
  if ( v15 )
    goto LABEL_119;
  if ( v63 )
  {
    *v63 = v7;
    goto LABEL_121;
  }
  if ( (v57 & 0x200) == 0 )
  {
LABEL_119:
    if ( v7 )
      Dns_FreeSecurityContext((LPVOID)v7);
  }
  else
  {
    Dns_EnlistSecurityContext(v7);
  }
LABEL_121:
  Dns_CleanupSecurityPacketInfoEx(&v76);
  if ( v13 )
    Packet_FreeMsgBuf((LPVOID)v13);
  if ( v12 != (void *)v11 )
    DeRefDnsMessage(v12);
  DeRefDnsMessage((LPVOID)v11);
  if ( lpMem )
    DnsApiFree(lpMem);
  return v15;
}

```

## disassembly

```asm
0x18006adbc  push    rbp
0x18006adbe  push    rbx
0x18006adbf  push    rsi
0x18006adc0  push    rdi
0x18006adc1  push    r12
0x18006adc3  push    r13
0x18006adc5  push    r14
0x18006adc7  push    r15
0x18006adc9  lea     rbp, [rsp-138h]
0x18006add1  sub     rsp, 238h
0x18006add8  mov     rax, cs:__security_cookie
0x18006addf  xor     rax, rsp
0x18006ade2  mov     [rbp+170h+var_50], rax
0x18006ade9  mov     r14, [rbp+170h+pAuthData]
0x18006adf0  mov     rbx, r8
0x18006adf3  mov     [rsp+270h+var_220], edx
0x18006adf7  mov     r8d, 90h; Size
0x18006adfd  mov     [rbp+170h+var_1F0], rcx
0x18006ae01  xor     edx, edx; Val
0x18006ae03  lea     rcx, [rbp+170h+var_120]; void *
0x18006ae07  mov     [rsp+270h+var_218], rbx
0x18006ae0c  mov     r12, r9
0x18006ae0f  mov     [rsp+270h+var_200], r9
0x18006ae14  xor     edi, edi
0x18006ae16  call    memset_0
0x18006ae1b  xor     edx, edx; Val
0x18006ae1d  mov     [rsp+270h+lpMem], rdi
0x18006ae22  lea     r8d, [rdi+58h]; Size
0x18006ae26  lea     rcx, [rbp+170h+var_180]; void *
0x18006ae2a  call    memset_0
0x18006ae2f  xor     r15d, r15d
0x18006ae32  mov     [rsp+270h+var_224], edi
0x18006ae36  xor     r13d, r13d
0x18006ae39  xor     esi, esi
0x18006ae3b  test    byte ptr cs:xmmword_1801119E0+1, 40h
0x18006ae42  jz      short loc_18006AE62
0x18006ae44  mov     r9d, [rsp+270h+var_220]
0x18006ae49  lea     rax, [r12+20h]
0x18006ae4e  mov     [rsp+270h+var_240], r14
0x18006ae53  mov     [rsp+270h+var_248], rbx
0x18006ae58  mov     [rsp+270h+var_250], rax
0x18006ae5d  call    WPP_SF_D_SOCKADDR_Sq
0x18006ae62  xor     edx, edx; Val
0x18006ae64  lea     rcx, [rbp+170h+var_118]; void *
0x18006ae68  mov     r8d, 88h; Size
0x18006ae6e  call    memset_0
0x18006ae73  cmp     cs:g_fVelocityDisableInternalExports, esi
0x18006ae79  mov     [rbp+170h+var_120], rsi
0x18006ae7d  jz      short loc_18006AE86
0x18006ae7f  call    Dns_InitializeSecurityPackage
0x18006ae84  jmp     short loc_18006AE8D
0x18006ae86  xor     ecx, ecx
0x18006ae88  call    Dns_StartSecurity
0x18006ae8d  mov     ebx, eax
0x18006ae8f  test    eax, eax
0x18006ae91  jnz     loc_18006B18F
0x18006ae97  xor     edx, edx; Val
0x18006ae99  lea     r8d, [rax+58h]; Size
0x18006ae9d  lea     rcx, [rbp+170h+var_180]; void *
0x18006aea1  call    memset_0
0x18006aea6  test    r14, r14
0x18006aea9  jz      short loc_18006AEE8
0x18006aeab  mov     rcx, r14
0x18006aeae  call    MakeCredKey
0x18006aeb3  mov     [rsp+270h+lpMem], rax
0x18006aeb8  test    rax, rax
0x18006aebb  jnz     short loc_18006AEE4
0x18006aebd  cmp     byte ptr cs:xmmword_1801119E0+3, sil
0x18006aec4  jge     short loc_18006AEDA
0x18006aec6  lea     edx, [rbx+61h]
0x18006aec9  mov     ecx, 41Fh
0x18006aece  lea     r8, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids
0x18006aed5  call    WPP_SF_
0x18006aeda  mov     ebx, 0Eh
0x18006aedf  jmp     loc_18006B18F
0x18006aee4  mov     [rbp+170h+var_130], rax
0x18006aee8  call    cs:__imp_GetCurrentProcessId
0x18006aeef  nop     dword ptr [rax+rax+00h]
0x18006aef4  lea     r8, aDMsD; "%d-ms-%d"
0x18006aefb  mov     dword ptr [rsp+270h+var_250], 7
0x18006af03  mov     r9d, eax
0x18006af06  lea     rcx, [rbp+170h+pszDest]; pszDest
0x18006af0d  mov     edx, 40h ; '@'; cbDest
0x18006af12  call    StringCbPrintfA
0x18006af17  test    byte ptr cs:xmmword_1801119E0+1, 40h
0x18006af1e  jz      short loc_18006AF3D
0x18006af20  mov     edx, 62h ; 'b'
0x18006af25  lea     r9, [rbp+170h+pszDest]
0x18006af2c  mov     ecx, 40Eh
0x18006af31  lea     r8, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids
0x18006af38  call    WPP_SF_s
0x18006af3d  lea     rax, [rbp+170h+pszDest]
0x18006af44  mov     qword ptr [rbp+170h+var_140+8], rax
0x18006af48  cmp     [r12+4], esi
0x18006af4d  jbe     loc_18006B01C
0x18006af53  mov     eax, r15d
0x18006af56  lea     rcx, [rbp+170h+Buf1]; Buf1
0x18006af5a  shl     rax, 6
0x18006af5e  mov     edx, 1
0x18006af63  movups  xmm1, xmmword ptr [rax+r12+40h]
0x18006af69  movups  xmm0, xmmword ptr [rax+r12+50h]
0x18006af6f  movups  xmm3, xmmword ptr [rax+r12+20h]
0x18006af75  movups  xmm2, xmmword ptr [rax+r12+30h]
0x18006af7b  movaps  [rbp+170h+var_160], xmm1
0x18006af7f  movaps  [rbp+170h+var_150], xmm0
0x18006af83  movaps  [rbp+170h+var_1C0], xmm1
0x18006af87  movsd   xmm1, [rbp+170h+var_130]
0x18006af8c  movaps  [rbp+170h+var_1B0], xmm0
0x18006af90  movaps  xmm0, xmmword ptr [rbp+30h]
0x18006af94  movaps  [rbp+170h+var_1A0], xmm0
0x18006af98  movsd   [rbp+170h+var_190], xmm1
0x18006af9d  movaps  [rbp+170h+var_180], xmm3
0x18006afa1  movaps  [rbp+170h+var_170], xmm2
0x18006afa5  movaps  [rbp+170h+Buf1], xmm3
0x18006afa9  movaps  [rbp+170h+var_1D0], xmm2
0x18006afad  call    Dns_DequeueSecurityContextByKey
0x18006afb2  mov     rdi, rax
0x18006afb5  test    rax, rax
0x18006afb8  jz      short loc_18006B00E
0x18006afba  mov     ecx, [rax+94h]
0x18006afc0  test    ecx, ecx
0x18006afc2  jz      short loc_18006AFD2
0x18006afc4  test    [rsp+270h+var_220], 800h
0x18006afcc  jz      loc_18006B084
0x18006afd2  cmp     byte ptr cs:xmmword_1801119E0+3, sil
0x18006afd9  jge     short loc_18006B006
0x18006afdb  test    ecx, ecx
0x18006afdd  lea     rdx, aIncompleteNego; "Incomplete negotiation key exists."
0x18006afe4  lea     rax, aUserSpecifiedF; "User specified FORCE_SECURITY_NEGO flag"...
0x18006afeb  cmovz   rax, rdx
0x18006afef  lea     r9, [rbp+170h+var_180]
0x18006aff3  mov     [rsp+270h+var_248], rax
0x18006aff8  mov     rax, qword ptr [rbp+170h+var_140]
0x18006affc  mov     [rsp+270h+var_250], rax
0x18006b001  call    WPP_SF__SOCKADDR_ss
0x18006b006  mov     rcx, rdi; lpMem
0x18006b009  call    Dns_FreeSecurityContext
0x18006b00e  inc     r15d
0x18006b011  cmp     r15d, [r12+4]
0x18006b016  jb      loc_18006AF53
0x18006b01c  movups  xmm1, xmmword ptr [r12+40h]
0x18006b022  add     r12, 20h ; ' '
0x18006b026  lea     rcx, [rbp+170h+Buf1]
0x18006b02a  mov     [rsp+270h+var_1F8], r12
0x18006b02f  movaps  [rbp+170h+var_160], xmm1
0x18006b033  movaps  [rbp+170h+var_1C0], xmm1
0x18006b037  movups  xmm0, xmmword ptr [r12+30h]
0x18006b03d  movups  xmm3, xmmword ptr [r12]
0x18006b042  movups  xmm2, xmmword ptr [r12+10h]
0x18006b048  movsd   xmm1, [rbp+170h+var_130]
0x18006b04d  movaps  [rbp+170h+var_150], xmm0
0x18006b051  movaps  [rbp+170h+var_1B0], xmm0
0x18006b055  movaps  xmm0, [rbp+170h+var_140]
0x18006b059  movaps  [rbp+170h+var_1A0], xmm0
0x18006b05d  movsd   [rbp+170h+var_190], xmm1
0x18006b062  movaps  [rbp+170h+var_180], xmm3
0x18006b066  movaps  [rbp+170h+var_170], xmm2
0x18006b06a  movaps  [rbp+170h+Buf1], xmm3
0x18006b06e  movaps  [rbp+170h+var_1D0], xmm2
0x18006b072  call    Dns_FindOrCreateSecurityContext
0x18006b077  mov     rdi, rax
0x18006b07a  test    rax, rax
0x18006b07d  jnz     short loc_18006B0B4
0x18006b07f  lea     ebx, [rax+2]
0x18006b082  jmp     short loc_18006B0AC
0x18006b084  inc     dword ptr [rax+98h]
0x18006b08a  test    byte ptr cs:xmmword_1801119E0+1, 40h
0x18006b091  jz      short loc_18006B0AC
0x18006b093  mov     edx, 64h ; 'd'
0x18006b098  lea     r8, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids
0x18006b09f  mov     ecx, 40Eh
0x18006b0a4  mov     r9, rdi
0x18006b0a7  call    WPP_SF_q
0x18006b0ac  mov     r15, rsi
0x18006b0af  jmp     loc_18006B18F
0x18006b0b4  mov     [rbp+170h+var_120], rdi
0x18006b0b8  mov     dword ptr [rax+80h], 7
0x18006b0c2  test    r14, r14
0x18006b0c5  jz      short loc_18006B104
0x18006b0c7  lea     rcx, [rax+70h]; phCredential
0x18006b0cb  mov     rdx, r14; pAuthData
0x18006b0ce  call    Dns_AcquireCredHandle
0x18006b0d3  mov     ebx, eax
0x18006b0d5  test    eax, eax
0x18006b0d7  jz      short loc_18006B0FA
0x18006b0d9  test    byte ptr cs:xmmword_1801119E0+1, 40h
0x18006b0e0  jz      short loc_18006B0AC
0x18006b0e2  mov     edx, 65h ; 'e'
0x18006b0e7  lea     r8, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids
0x18006b0ee  mov     ecx, 40Eh
0x18006b0f3  call    WPP_SF_
0x18006b0f8  jmp     short loc_18006B0AC
0x18006b0fa  mov     dword ptr [rdi+8Ch], 1
0x18006b104  mov     ebx, 0FFFFh
0x18006b109  mov     ecx, ebx
0x18006b10b  call    Packet_AllocateMsgBuf
0x18006b110  cmp     cs:g_fVelocityDnsKernelApi, esi
0x18006b116  mov     r15, rax
0x18006b119  mov     [rsp+270h+var_230], rax
0x18006b11e  jz      short loc_18006B155
0x18006b120  test    rax, rax
0x18006b123  jz      loc_18006AEDA
0x18006b129  mov     rcx, r15
0x18006b12c  call    AddRefDnsMessage
0x18006b131  mov     ecx, ebx
0x18006b133  call    Packet_AllocateMsgBuf
0x18006b138  mov     rsi, rax
0x18006b13b  test    rax, rax
0x18006b13e  jnz     loc_18006B1CE
0x18006b144  mov     r15b, 8
0x18006b147  test    byte ptr cs:xmmword_1801119E0+1, r15b
0x18006b14e  jz      short loc_18006B17C
0x18006b150  lea     edx, [rax+67h]
0x18006b153  jmp     short loc_18006B16B
0x18006b155  test    r15, r15
0x18006b158  jnz     short loc_18006B129
0x18006b15a  mov     r15b, 8
0x18006b15d  test    byte ptr cs:xmmword_1801119E0+1, r15b
0x18006b164  jz      short loc_18006B17C
0x18006b166  mov     edx, 66h ; 'f'
0x18006b16b  mov     ecx, 40Bh
0x18006b170  lea     r8, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids
0x18006b177  call    WPP_SF_
0x18006b17c  call    cs:__imp_GetLastError
0x18006b183  nop     dword ptr [rax+rax+00h]
0x18006b188  mov     ebx, eax
0x18006b18a  mov     r15, [rsp+270h+var_230]
0x18006b18f  test    byte ptr cs:xmmword_1801119E0+1, 40h
0x18006b196  jz      short loc_18006B1B1
0x18006b198  mov     edx, 75h ; 'u'
0x18006b19d  lea     r8, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids
0x18006b1a4  mov     ecx, 40Eh
0x18006b1a9  mov     r9d, ebx
0x18006b1ac  call    WPP_SF_d
0x18006b1b1  test    ebx, ebx
0x18006b1b3  jnz     loc_18006B68E
0x18006b1b9  mov     rax, [rbp+170h+var_1F0]
0x18006b1bd  test    rax, rax
0x18006b1c0  jz      loc_18006B67A
0x18006b1c6  mov     [rax], rdi
0x18006b1c9  jmp     loc_18006B69B
0x18006b1ce  mov     byte ptr [rax+288h], 1
0x18006b1d5  mov     r8d, 0F9h
0x18006b1db  mov     [rax+28Dh], r13w
0x18006b1e3  xor     r9d, r9d
0x18006b1e6  xor     eax, eax
0x18006b1e8  mov     dword ptr [rsi+270h], 3A98h
0x18006b1f2  mov     [rsi+2BAh], ax
0x18006b1f9  mov     rcx, r15
0x18006b1fc  mov     [rsi+2A8h], rax
0x18006b203  mov     rdx, [rdi+58h]
0x18006b207  call    Packet_WriteQuestionToMessage
0x18006b20c  test    rax, rax
0x18006b20f  jnz     short loc_18006B219
0x18006b211  lea     ebx, [rax+57h]
0x18006b214  jmp     loc_18006B18F
0x18006b219  and     byte ptr [r15+2BEh], 86h
0x18006b221  xor     ecx, ecx
0x18006b223  sub     rax, r15
0x18006b226  mov     [rsp+270h+var_228], ecx
0x18006b22a  mov     [rsp+270h+var_208], rax
0x18006b22f  call    Packet_GetRandomXid
0x18006b234  mov     rdx, [rsp+270h+var_218]
0x18006b239  lea     r8, [rsp+270h+var_224]
0x18006b23e  lea     rcx, [rbp+170h+var_120]
0x18006b242  mov     [r15+2BCh], ax
0x18006b24a  mov     r13, r15
0x18006b24d  call    Dns_InitClientSecurityContext
0x18006b252  mov     rdi, [rbp+170h+var_120]
0x18006b256  mov     ebx, eax
0x18006b258  mov     r15b, 8
0x18006b25b  test    eax, eax
0x18006b25d  jz      loc_18006B4AB
0x18006b263  mov     r12d, 40Bh
0x18006b269  cmp     ebx, 2649h
0x18006b26f  jnz     loc_18006B18A
0x18006b275  mov     ebx, [rsp+270h+var_228]
0x18006b279  mov     rcx, r13
0x18006b27c  call    Dns_CloneMsgBuf
0x18006b281  mov     r14, rax
0x18006b284  test    rax, rax
0x18006b287  jz      loc_18006B5CA
0x18006b28d  mov     rcx, rax
0x18006b290  call    AddRefDnsMessage
0x18006b295  cmp     r13, [rsp+270h+var_230]
0x18006b29a  jz      short loc_18006B2A4
0x18006b29c  mov     rcx, r13; lpMem
0x18006b29f  call    DeRefDnsMessage
0x18006b2a4  lea     rcx, [r14+258h]
0x18006b2ab  mov     r13, r14
0x18006b2ae  test    ebx, ebx
0x18006b2b0  jz      short loc_18006B2D9
0x18006b2b2  mov     rax, [rsp+270h+var_208]
0x18006b2b7  mov     dword ptr [rdi+80h], 3
0x18006b2c1  add     rax, r14
0x18006b2c4  mov     [rcx], rax
0x18006b2c7  xor     eax, eax
0x18006b2c9  mov     [r14+2C6h], ax
0x18006b2d1  mov     [r14+2C2h], ax
0x18006b2d9  mov     r8, [r14+250h]
  ... truncated ...
```
