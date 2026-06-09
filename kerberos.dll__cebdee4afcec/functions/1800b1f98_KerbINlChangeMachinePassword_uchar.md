# KerbINlChangeMachinePassword(uchar)

- ea: `0x1800b1f98`
- end: `0x1800b28c2`
- name: `?KerbINlChangeMachinePassword@@YAJE@Z`
- size: `2346`
- prototype: `__int64 __fastcall(unsigned __int8)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800b29f0`

## callees

- `0x1800063e8`
- `0x1800068d0`
- `0x1800069a0`
- `0x1800069e0`
- `0x1800093f0`
- `0x18000d0d0`
- `0x180010e90`
- `0x180018de8`
- `0x18001deb0`
- `0x180032964`
- `0x18003aef0`
- `0x18003e170`
- `0x180065c48`
- `0x18006e748`
- `0x180070680`
- `0x1800744cf`
- `0x18007a670`
- `0x18008b2f4`
- `0x18008b70c`
- `0x180090040`
- `0x1800a80bc`
- `0x1800afe8c`
- `0x1800b00d4`
- `0x1800b11cc`
- `0x1800b1a0c`
- `0x1800b1f98`
- `0x1800b3df4`
- `0x1800b3f24`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b21ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b21ad`
- `LSASRV!LsarClose` at `0x1800b287b`
- `LSASRV!LsarClose` at `0x1800b288d`
- `LSASRV!LsarClose` at `0x1800b287b`
- `LSASRV!LsarClose` at `0x1800b288d`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x1800b2717`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x1800b2717`
- `LSASRV!LsarDeleteObject` at `0x1800b257f`
- `LSASRV!LsarDeleteObject` at `0x1800b25bf`
- `LSASRV!LsarDeleteObject` at `0x1800b2600`
- `LSASRV!LsarDeleteObject` at `0x1800b2643`
- `LSASRV!LsarDeleteObject` at `0x1800b2724`
- `LSASRV!LsarDeleteObject` at `0x1800b257f`
- `LSASRV!LsarDeleteObject` at `0x1800b25bf`
- `LSASRV!LsarDeleteObject` at `0x1800b2600`
- `LSASRV!LsarDeleteObject` at `0x1800b2643`
- `LSASRV!LsarDeleteObject` at `0x1800b2724`
- `LSASRV!LsarQuerySecret` at `0x1800b26f9`
- `LSASRV!LsarQuerySecret` at `0x1800b26f9`

## string_xrefs

- `0x1800b2395`: `Failed to create AP request for kpasswd: 0x%x`
- `0x1800b22bf`: `Failed to create machine password: 0x%x`
- `0x1800b258f`: `Failed to delete VBS-bound machine secret: 0x%x`
- `0x1800b260c`: `Failed to delete VBS-bound machine secret: 0x%x`
- `0x1800b25cf`: `Failed to delete LSA-bound machine secret: 0x%x`
- `0x1800b264f`: `Failed to delete LSA-bound machine secret: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall KerbINlChangeMachinePassword(char a1)
{
  int v2; // esi
  char v3; // r13
  int v4; // r15d
  int v5; // r14d
  __int64 v6; // rax
  struct _KERB_LOGON_SESSION *v7; // rbx
  int KpasswdTicket; // edi
  int MachinePasswordHandlesAndLastChangedTime; // eax
  int v10; // eax
  signed int LowPart; // ebx
  int ApRequest; // edi
  size_t v13; // r12
  unsigned int v14; // ecx
  unsigned int v15; // ebx
  char *v16; // rax
  char *v17; // rdi
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  int v21; // eax
  const char *v22; // r9
  __int64 v23; // r8
  __int64 *CorrelationId; // rax
  int v25; // edx
  int v26; // ecx
  PEVENT_DATA_DESCRIPTOR v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+28h] [rbp-D8h]
  unsigned int v30; // [rsp+70h] [rbp-90h] BYREF
  void *v31; // [rsp+78h] [rbp-88h] BYREF
  void *v32; // [rsp+80h] [rbp-80h] BYREF
  int v33; // [rsp+88h] [rbp-78h] BYREF
  int v34; // [rsp+8Ch] [rbp-74h] BYREF
  struct _KERB_RPC_HOST_ADDRESS *v35; // [rsp+90h] [rbp-70h] BYREF
  struct _KDC_PROXY_CACHE_ENTRY *v36; // [rsp+98h] [rbp-68h] BYREF
  struct _KERB_TICKET_CACHE_ENTRY *v37; // [rsp+A0h] [rbp-60h] BYREF
  struct _KERB_LOGON_SESSION *v38; // [rsp+A8h] [rbp-58h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp-50h] BYREF
  union _LARGE_INTEGER v40; // [rsp+B8h] [rbp-48h] BYREF
  union _LARGE_INTEGER v41[2]; // [rsp+C0h] [rbp-40h] BYREF
  void *Src[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v43; // [rsp+E0h] [rbp-20h] BYREF
  struct _KERB_INTERNAL_NAME *v44; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v45; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v46; // [rsp+100h] [rbp+0h]
  size_t Size[2]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v48[2]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v49[2]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v50; // [rsp+140h] [rbp+40h] BYREF
  __int128 v51; // [rsp+150h] [rbp+50h] BYREF
  UNICODE_STRING String1; // [rsp+160h] [rbp+60h] BYREF
  __int128 v53; // [rsp+170h] [rbp+70h] BYREF
  __int128 v54; // [rsp+180h] [rbp+80h] BYREF
  __int128 v55; // [rsp+190h] [rbp+90h]
  __int64 v56; // [rsp+1A0h] [rbp+A0h]
  _OWORD v57[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  void **v58; // [rsp+1C8h] [rbp+C8h]
  void **v59; // [rsp+1D0h] [rbp+D0h]
  char v60; // [rsp+1D8h] [rbp+D8h]
  _OWORD v61[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v62; // [rsp+200h] [rbp+100h]
  struct _EVENT_DATA_DESCRIPTOR v63; // [rsp+210h] [rbp+110h] BYREF
  struct _KERB_RPC_HOST_ADDRESS **v64; // [rsp+230h] [rbp+130h]
  __int64 v65; // [rsp+238h] [rbp+138h]
  struct _KDC_PROXY_CACHE_ENTRY **v66; // [rsp+240h] [rbp+140h]
  __int64 v67; // [rsp+248h] [rbp+148h]
  unsigned int *v68; // [rsp+250h] [rbp+150h]
  __int64 v69; // [rsp+258h] [rbp+158h]
  int *v70; // [rsp+260h] [rbp+160h]
  __int64 v71; // [rsp+268h] [rbp+168h]
  int *v72; // [rsp+270h] [rbp+170h]
  __int64 v73; // [rsp+278h] [rbp+178h]
  union _LARGE_INTEGER *v74; // [rsp+280h] [rbp+180h]
  __int64 v75; // [rsp+288h] [rbp+188h]
  _OWORD v76[2]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t v77; // [rsp+2B0h] [rbp+1B0h]
  _OWORD v78[2]; // [rsp+2B8h] [rbp+1B8h] BYREF

  v2 = 0;
  v3 = 0;
  v35 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  *(_OWORD *)Size = 0;
  v57[0] = 0;
  v45 = 0;
  v53 = 0;
  v51 = 0;
  v50 = 0;
  SystemTimeAsFileTime = 0;
  v40.QuadPart = 0;
  v32 = 0;
  v31 = 0;
  v4 = 0;
  v33 = 0;
  v34 = 0;
  v43 = 999;
  v38 = 0;
  v44 = 0;
  String1 = 0;
  v37 = 0;
  v46 = 0;
  *(_OWORD *)Src = 0;
  v36 = 0;
  v5 = 0;
  v30 = 0;
  v78[0] = *(_OWORD *)L"$MACHINE.ACC";
  *(_OWORD *)((char *)v78 + 10) = *(_OWORD *)L"INE.ACC";
  v49[0] = 1703960;
  v49[1] = v78;
  v76[0] = *(_OWORD *)L"$MACHINE.ACC.IUM";
  v76[1] = *(_OWORD *)L".ACC.IUM";
  v77 = aMachineAccIum[16];
  v48[0] = 2228256;
  v48[1] = v76;
  v58 = &v32;
  v59 = &v31;
  v60 = 1;
  v6 = KerbLocateLogonSessionUnique(v41, &v43);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_KERB_LOGON_SESSION *,void (_KERB_LOGON_SESSION *),&void KerbDereferenceLogonSession(_KERB_LOGON_SESSION *),wistd::integral_constant<unsigned __int64,0>,_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,0,std::nullptr_t>>>::operator=(
    &v38,
    v6);
  wil::details::unique_storage<wil::details::resource_policy<_KERB_LOGON_SESSION *,void (_KERB_LOGON_SESSION *),&void KerbDereferenceLogonSession(_KERB_LOGON_SESSION *),wistd::integral_constant<unsigned __int64,0>,_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_KERB_LOGON_SESSION *,void (_KERB_LOGON_SESSION *),&void KerbDereferenceLogonSession(_KERB_LOGON_SESSION *),wistd::integral_constant<unsigned __int64,0>,_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,0,std::nullptr_t>>(v41);
  v7 = v38;
  if ( !v38 )
  {
    KpasswdTicket = -1073741729;
    v2 = 8;
    goto LABEL_52;
  }
  MachinePasswordHandlesAndLastChangedTime = GetMachinePasswordHandlesAndLastChangedTime(
                                               (struct _LSAPR_UNICODE_STRING *)v49,
                                               (struct _LSAPR_UNICODE_STRING *)v48,
                                               &v32,
                                               &v31,
                                               &v40,
                                               &v33,
                                               (enum KerbMachinePasswordProtection *)&v30,
                                               &v34,
                                               (struct _UNICODE_STRING *)((char *)v38 + 120));
  KpasswdTicket = MachinePasswordHandlesAndLastChangedTime;
  if ( MachinePasswordHandlesAndLastChangedTime < 0 )
  {
    KerbTracerT::Log(
      1,
      "KerbINlChangeMachinePassword",
      4109,
      "Failed to fetch the secret handles or the last changed time: 0x%x\n",
      MachinePasswordHandlesAndLastChangedTime);
    v2 = 1;
    v4 = v33;
    v5 = v30;
    goto LABEL_52;
  }
  v4 = v33;
  if ( !v33 && !a1 && !v34 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( GetNlMaximumPasswordAge_100ns() > *(_QWORD *)&SystemTimeAsFileTime - v40.QuadPart )
    {
LABEL_11:
      v5 = v30;
      goto LABEL_52;
    }
  }
  *((_DWORD *)v7 + 132) |= 0x10u;
  KpasswdTicket = KerbGetKpasswdTicket(v7, &v37, &String1, &v44, &v36);
  if ( KpasswdTicket < 0 )
  {
    v2 = 2;
    goto LABEL_11;
  }
  KpasswdTicket = KerbGetOutgoingKerbHostAddress(&String1, &v35);
  if ( KpasswdTicket < 0 )
  {
    KerbTracerT::Log(1, "KerbINlChangeMachinePassword", 4148, "Failed to get IP address for message\n");
LABEL_14:
    v2 = 9;
    goto LABEL_11;
  }
  if ( !v35 )
  {
    KerbTracerT::Log(1, "KerbINlChangeMachinePassword", 4155, "No IP addresses.");
    KpasswdTicket = -1073741071;
    goto LABEL_14;
  }
  v5 = v30;
  v10 = (*(__int64 (__fastcall **)(_QWORD, struct _KERB_RPC_HOST_ADDRESS *, char *, _QWORD, __int128 *, __int128 *, __int128 *, size_t *))(**((_QWORD **)v37 + 21) + 272LL))(
          *((_QWORD *)v37 + 21),
          v35,
          (char *)v37 + 168,
          v30,
          &v45,
          &v53,
          &v54,
          Size);
  KpasswdTicket = v10;
  if ( v10 < 0 )
  {
    KerbTracerT::Log(1, "KerbINlChangeMachinePassword", 4174, "Failed to create machine password: 0x%x", v10);
    v2 = 3;
    goto LABEL_52;
  }
  v41[0].QuadPart = 10000000LL * *((int *)v37 + 86);
  LowPart = v41[0].LowPart;
  ApRequest = KerbCreateApRequest(
                *((struct _KERB_INTERNAL_NAME **)v37 + 18),
                (struct _UNICODE_STRING *)v37 + 6,
                (struct _KERB_TICKET_CACHE_ENTRY *)((char *)v37 + 168),
                (struct _KERB_ENCRYPTION_KEY *)&v54,
                0,
                0,
                0,
                (struct _KERB_TICKET_CACHE_ENTRY *)((char *)v37 + 272),
                0,
                0,
                v41,
                0xBu,
                (unsigned int *)Src,
                (unsigned __int8 **)&Src[1]);
  _InterlockedExchange((volatile __int32 *)v37 + 86, LowPart / 10000000 + LowPart);
  if ( ApRequest )
  {
    KerbTracerT::Log(
      1,
      "KerbINlChangeMachinePassword",
      4202,
      "Failed to create AP request for kpasswd: 0x%x",
      ApRequest);
    KpasswdTicket = KerbMapKerbError(ApRequest);
    v2 = 4;
    goto LABEL_52;
  }
  v13 = LODWORD(Src[0]);
  v14 = LODWORD(Size[0]) + LODWORD(Src[0]);
  if ( (unsigned int)(LODWORD(Size[0]) + LODWORD(Src[0])) < LODWORD(Size[0])
    || (LODWORD(v46) = LODWORD(Size[0]) + LODWORD(Src[0]), v15 = v14 + 6, v14 + 6 < v14) )
  {
    KpasswdTicket = -1073741675;
    goto LABEL_51;
  }
  LODWORD(v46) = v14 + 6;
  v16 = (char *)MIDL_user_allocate(v15);
  v17 = v16;
  *((_QWORD *)&v46 + 1) = v16;
  if ( !v16 )
  {
    KpasswdTicket = -1073741670;
LABEL_51:
    v2 = 7;
    goto LABEL_52;
  }
  *v16 = BYTE1(v15);
  v16[1] = v15;
  *((_WORD *)v16 + 1) = 256;
  v16[4] = BYTE1(v13);
  v16[5] = v13;
  memcpy_0(v16 + 6, Src[1], v13);
  memcpy_0(&v17[v13 + 6], (const void *)Size[1], LODWORD(Size[0]));
  v61[0] = v54;
  v61[1] = v55;
  v62 = v56;
  *(UNICODE_STRING *)Src = String1;
  *(_OWORD *)&v41[0].LowPart = v46;
  LOBYTE(v29) = 0;
  v18 = KerbIMakeKdcCall(v37, v36, v41, Src, v61, v29, 0);
  KpasswdTicket = v18;
  if ( v18 >= 0 )
  {
    if ( *((_QWORD *)&v45 + 1) )
    {
      LODWORD(v51) = (unsigned __int16)v45;
      DWORD1(v51) = WORD1(v45);
      *((_QWORD *)&v51 + 1) = *((_QWORD *)&v45 + 1);
    }
    if ( *((_QWORD *)&v53 + 1) )
    {
      LODWORD(v50) = v53;
      DWORD1(v50) = v53;
      *((_QWORD *)&v50 + 1) = *((_QWORD *)&v53 + 1);
    }
    KpasswdTicket = SetMachinePasswordInRegistry(v32, v31, &v51, &v50, v5, v4);
    if ( KpasswdTicket < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v19);
      KerbTracerT::Log(
        1,
        "KerbINlChangeMachinePassword",
        4279,
        "Failed to save machine password after rolling it: 0x%x",
        KpasswdTicket);
      v2 = 6;
    }
    if ( v31 )
    {
      if ( !v5 )
      {
        v20 = LsarDeleteObject(&v31);
        KpasswdTicket = v20;
        if ( v20 < 0 )
        {
          KerbTracerT::Log(
            1,
            "KerbINlChangeMachinePassword",
            4289,
            "Failed to delete VBS-bound machine secret: 0x%x",
            v20);
          KpasswdTicket = 0;
        }
      }
    }
    if ( v32 )
    {
      if ( v5 == 2 )
      {
        v21 = LsarDeleteObject(&v32);
        KpasswdTicket = v21;
        if ( v21 < 0 )
        {
          KerbTracerT::Log(
            1,
            "KerbINlChangeMachinePassword",
            4300,
            "Failed to delete LSA-bound machine secret: 0x%x",
            v21);
          KpasswdTicket = 0;
        }
      }
    }
    if ( !v31 || v5 || (KpasswdTicket = LsarDeleteObject(&v31), KpasswdTicket >= 0) )
    {
      if ( !v32 )
        goto LABEL_52;
      if ( v5 != 2 )
        goto LABEL_52;
      KpasswdTicket = LsarDeleteObject(&v32);
      if ( KpasswdTicket >= 0 )
        goto LABEL_52;
      v22 = "Failed to delete LSA-bound machine secret: 0x%x";
      v23 = 4322;
    }
    else
    {
      v22 = "Failed to delete VBS-bound machine secret: 0x%x";
      v23 = 4311;
    }
    LODWORD(v28) = KpasswdTicket;
    KerbTracerT::Log(1, "KerbINlChangeMachinePassword", v23, v22, v28);
    goto LABEL_77;
  }
  KerbTracerT::Log(1, "KerbINlChangeMachinePassword", 4252, "KerbIMakeKdcCall failed: 0x%x", v18);
  v2 = 5;
LABEL_52:
  KerbSecureFreeString(v57);
  KerbSecureFreeString(&v45);
  KerbFreeString((__int64)&String1);
  KerbFreeKdcName(&v44);
  if ( v37 )
    KerbDereferenceTicketCacheEntry(v37);
  if ( *((_QWORD *)&v46 + 1) )
    KerbFree(*((_QWORD *)&v46 + 1));
  if ( *((_QWORD *)&v55 + 1) )
    KerbFree(*((_QWORD *)&v55 + 1));
  if ( v36 )
    KerbDereferenceKdcProxyCacheEntry(v36);
  if ( Size[1] )
    KerbFree(Size[1]);
  if ( v4 == 1 )
  {
    v35 = 0;
    if ( (int)LsarQuerySecret(v31, &v35, 0, 0, 0) >= 0 )
    {
      if ( v35 && *((_QWORD *)v35 + 1) && *(_DWORD *)v35 )
        LsaIFree_LSAPR_CR_CIPHER_VALUE(v35);
      else
        LsarDeleteObject(&v31);
    }
  }
  if ( v2 )
  {
    if ( (Microsoft_Windows_Security_KerberosEnableBits & 4) != 0 )
    {
      CorrelationId = (__int64 *)KerbTracerT::GetCorrelationId(v57);
      v3 = 1;
      McTemplateU0qtqqz_EtwEventWriteTransfer(v26, v25, KpasswdTicket, v4, v5, v2, *CorrelationId);
    }
    if ( (v3 & 1) != 0 )
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v57);
  }
  if ( (unsigned int)dword_180140048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
  {
    v41[0].QuadPart = 0x1000000;
    v34 = v2;
    v33 = v5;
    v30 = v4;
    LODWORD(v36) = KpasswdTicket;
    v35 = (struct _KERB_RPC_HOST_ADDRESS *)1;
    v74 = v41;
    v75 = 8;
    v72 = &v34;
    v73 = 4;
    v70 = &v33;
    v71 = 4;
    v68 = &v30;
    v69 = 4;
    v66 = &v36;
    v67 = 4;
    v64 = &v35;
    v65 = 8;
    tlgWriteAgg((int)&dword_180140048, (int)&word_18012C802, 0, 8, &v63);
  }
LABEL_77:
  if ( v32 )
    LsarClose(&v32);
  if ( v31 )
    LsarClose(&v31);
  wil::details::unique_storage<wil::details::resource_policy<_KERB_LOGON_SESSION *,void (_KERB_LOGON_SESSION *),&void KerbDereferenceLogonSession(_KERB_LOGON_SESSION *),wistd::integral_constant<unsigned __int64,0>,_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_KERB_LOGON_SESSION *,void (_KERB_LOGON_SESSION *),&void KerbDereferenceLogonSession(_KERB_LOGON_SESSION *),wistd::integral_constant<unsigned __int64,0>,_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,0,std::nullptr_t>>(&v38);
  return (unsigned int)KpasswdTicket;
}

```

## disassembly

```asm
0x1800b1f98  push    rbp
0x1800b1f9a  push    rbx
0x1800b1f9b  push    rsi
0x1800b1f9c  push    rdi
0x1800b1f9d  push    r12
0x1800b1f9f  push    r13
0x1800b1fa1  push    r14
0x1800b1fa3  push    r15
0x1800b1fa5  lea     rbp, [rsp-1E8h]
0x1800b1fad  sub     rsp, 2E8h
0x1800b1fb4  mov     rax, cs:__security_cookie
0x1800b1fbb  xor     rax, rsp
0x1800b1fbe  mov     [rbp+220h+var_48], rax
0x1800b1fc5  mov     r12b, cl
0x1800b1fc8  xor     esi, esi
0x1800b1fca  mov     r13d, esi
0x1800b1fcd  mov     dword ptr [rbp+220h+var_288], esi
0x1800b1fd0  mov     [rbp+220h+var_290], rsi
0x1800b1fd4  xorps   xmm0, xmm0
0x1800b1fd7  xor     eax, eax
0x1800b1fd9  movups  [rbp+220h+var_1A0], xmm0
0x1800b1fe0  movups  [rbp+220h+var_190], xmm0
0x1800b1fe7  mov     [rbp+220h+var_180], rax
0x1800b1fee  movups  xmmword ptr [rbp+220h+Size], xmm0
0x1800b1ff2  xorps   xmm1, xmm1
0x1800b1ff5  movups  [rbp+220h+var_178], xmm1
0x1800b1ffc  movups  [rbp+220h+var_230], xmm0
0x1800b2000  movups  [rbp+220h+var_1B0], xmm1
0x1800b2004  movups  [rbp+220h+var_1D0], xmm0
0x1800b2008  movups  [rbp+220h+var_1E0], xmm1
0x1800b200c  mov     qword ptr [rbp+220h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x1800b2010  mov     qword ptr [rbp+220h+var_268], rsi
0x1800b2014  mov     [rbp+220h+var_2A0], rsi
0x1800b2018  mov     [rsp+320h+var_2A8], rsi
0x1800b201d  mov     r15d, esi
0x1800b2020  mov     [rbp+220h+var_298], esi
0x1800b2023  mov     [rbp+220h+var_294], esi
0x1800b2026  mov     [rbp+220h+var_240], 3E7h
0x1800b202e  mov     [rbp+220h+var_278], rsi
0x1800b2032  mov     [rbp+220h+var_238], rsi
0x1800b2036  movups  xmmword ptr [rbp+220h+String1.Length], xmm0
0x1800b203a  mov     [rbp+220h+var_280], rsi
0x1800b203e  movups  [rbp+220h+var_220], xmm1
0x1800b2042  movups  xmmword ptr [rbp+220h+Src], xmm0
0x1800b2046  mov     [rbp+220h+var_288], rsi
0x1800b204a  mov     r14d, esi
0x1800b204d  mov     [rsp+320h+var_2B0], esi
0x1800b2051  movups  xmm0, xmmword ptr cs:aMachineAcc; "$MACHINE.ACC"
0x1800b2058  movups  xmmword ptr [rbp+220h+var_68], xmm0
0x1800b205f  movups  xmm1, xmmword ptr cs:aMachineAcc+0Ah; "INE.ACC"
0x1800b2066  movups  xmmword ptr [rbp+220h+var_68+0Ah], xmm1
0x1800b206d  mov     [rbp+220h+var_1F0], 1A0018h
0x1800b2075  lea     rax, [rbp+220h+var_68]
0x1800b207c  mov     [rbp+220h+var_1E8], rax
0x1800b2080  movups  xmm0, xmmword ptr cs:aMachineAccIum; "$MACHINE.ACC.IUM"
0x1800b2087  movups  [rbp+220h+var_90], xmm0
0x1800b208e  movups  xmm1, xmmword ptr cs:aMachineAccIum+10h; ".ACC.IUM"
0x1800b2095  movups  [rbp+220h+var_80], xmm1
0x1800b209c  movzx   eax, word ptr cs:aMachineAccIum+20h; ""
0x1800b20a3  mov     [rbp+220h+var_70], ax
0x1800b20aa  mov     [rbp+220h+var_200], 220020h
0x1800b20b2  lea     rax, [rbp+220h+var_90]
0x1800b20b9  mov     [rbp+220h+var_1F8], rax
0x1800b20bd  lea     rax, [rbp+220h+var_2A0]
0x1800b20c1  mov     [rbp+220h+var_158], rax
0x1800b20c8  lea     rax, [rsp+320h+var_2A8]
0x1800b20cd  mov     [rbp+220h+var_150], rax
0x1800b20d4  mov     [rbp+220h+var_148], 1
0x1800b20db  lea     rdx, [rbp+220h+var_240]
0x1800b20df  lea     rcx, [rbp+220h+var_260]
0x1800b20e3  call    ?KerbLocateLogonSessionUnique@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_KERB_LOGON_SESSION@@$$A6AXPEAU1@@Z$1?KerbDereferenceLogonSession@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBU_LUID@@E@Z; KerbLocateLogonSessionUnique(_LUID const *,uchar)
0x1800b20e8  mov     rdx, rax
0x1800b20eb  lea     rcx, [rbp+220h+var_278]
0x1800b20ef  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_KERB_LOGON_SESSION@@$$A6AXPEAU1@@Z$1?KerbDereferenceLogonSession@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_KERB_LOGON_SESSION *,void (_KERB_LOGON_SESSION *),&KerbDereferenceLogonSession(_KERB_LOGON_SESSION *),wistd::integral_constant<unsigned __int64,0>,_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_KERB_LOGON_SESSION *,void (_KERB_LOGON_SESSION *),&KerbDereferenceLogonSession(_KERB_LOGON_SESSION *),wistd::integral_constant<unsigned __int64,0>,_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,0,std::nullptr_t>>> &&)
0x1800b20f4  lea     rcx, [rbp+220h+var_260]
0x1800b20f8  call    ??1?$unique_storage@U?$resource_policy@PEAU_KERB_LOGON_SESSION@@$$A6AXPEAU1@@Z$1?KerbDereferenceLogonSession@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_KERB_LOGON_SESSION *,void (_KERB_LOGON_SESSION *),&KerbDereferenceLogonSession(_KERB_LOGON_SESSION *),wistd::integral_constant<unsigned __int64,0>,_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_KERB_LOGON_SESSION *,void (_KERB_LOGON_SESSION *),&KerbDereferenceLogonSession(_KERB_LOGON_SESSION *),wistd::integral_constant<unsigned __int64,0>,_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,0,std::nullptr_t>>(void)
0x1800b20fd  mov     rbx, [rbp+220h+var_278]
0x1800b2101  test    rbx, rbx
0x1800b2104  jnz     short loc_1800B2113
0x1800b2106  mov     edi, 0C000005Fh
0x1800b210b  lea     esi, [rbx+8]
0x1800b210e  jmp     loc_1800B2668
0x1800b2113  lea     rax, [rbx+78h]
0x1800b2117  mov     [rsp+320h+var_2E0], rax; struct _UNICODE_STRING *
0x1800b211c  lea     rax, [rbp+220h+var_294]
0x1800b2120  mov     [rsp+320h+var_2E8], rax; int *
0x1800b2125  lea     rax, [rsp+320h+var_2B0]
0x1800b212a  mov     [rsp+320h+var_2F0], rax; enum KerbMachinePasswordProtection *
0x1800b212f  lea     rax, [rbp+220h+var_298]
0x1800b2133  mov     [rsp+320h+var_2F8], rax; int *
0x1800b2138  lea     rax, [rbp+220h+var_268]
0x1800b213c  mov     [rsp+320h+var_300], rax; union _LARGE_INTEGER *
0x1800b2141  lea     r9, [rsp+320h+var_2A8]; void **
0x1800b2146  lea     r8, [rbp+220h+var_2A0]; void **
0x1800b214a  lea     rdx, [rbp+220h+var_200]; struct _LSAPR_UNICODE_STRING *
0x1800b214e  lea     rcx, [rbp+220h+var_1F0]; struct _LSAPR_UNICODE_STRING *
0x1800b2152  call    ?GetMachinePasswordHandlesAndLastChangedTime@@YAJPEAU_LSAPR_UNICODE_STRING@@0PEAPEAX1PEAT_LARGE_INTEGER@@PEAHPEAW4KerbMachinePasswordProtection@@3PEAU_UNICODE_STRING@@@Z; GetMachinePasswordHandlesAndLastChangedTime(_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,void * *,void * *,_LARGE_INTEGER *,int *,KerbMachinePasswordProtection *,int *,_UNICODE_STRING *)
0x1800b2157  mov     edi, eax
0x1800b2159  test    eax, eax
0x1800b215b  jns     short loc_1800B2192
0x1800b215d  mov     dword ptr [rsp+320h+var_300], eax
0x1800b2161  lea     r9, aFailedToFetchT_0; "Failed to fetch the secret handles or t"...
0x1800b2168  mov     r8d, 100Dh
0x1800b216e  lea     rdx, aKerbinlchangem; "KerbINlChangeMachinePassword"
0x1800b2175  mov     ecx, 1
0x1800b217a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b217f  mov     esi, 1
0x1800b2184  mov     r15d, [rbp+220h+var_298]
0x1800b2188  mov     r14d, [rsp+320h+var_2B0]
0x1800b218d  jmp     loc_1800B2668
0x1800b2192  mov     r15d, [rbp+220h+var_298]
0x1800b2196  test    r15d, r15d
0x1800b2199  jnz     short loc_1800B21C7
0x1800b219b  test    r12b, r12b
0x1800b219e  jnz     short loc_1800B21C7
0x1800b21a0  xor     r12d, r12d
0x1800b21a3  cmp     [rbp+220h+var_294], r12d
0x1800b21a7  jnz     short loc_1800B21CA
0x1800b21a9  lea     rcx, [rbp+220h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800b21ad  call    cs:__imp_GetSystemTimeAsFileTime
0x1800b21b3  call    ?GetNlMaximumPasswordAge_100ns@@YA_JXZ; GetNlMaximumPasswordAge_100ns(void)
0x1800b21b8  mov     rcx, qword ptr [rbp+220h+SystemTimeAsFileTime.dwLowDateTime]
0x1800b21bc  sub     rcx, qword ptr [rbp+220h+var_268]
0x1800b21c0  cmp     rax, rcx
0x1800b21c3  jle     short loc_1800B21CA
0x1800b21c5  jmp     short loc_1800B21F9
0x1800b21c7  xor     r12d, r12d
0x1800b21ca  or      dword ptr [rbx+210h], 10h
0x1800b21d1  lea     rax, [rbp+220h+var_288]
0x1800b21d5  mov     [rsp+320h+var_300], rax; struct _KDC_PROXY_CACHE_ENTRY **
0x1800b21da  lea     r9, [rbp+220h+var_238]; struct _KERB_INTERNAL_NAME **
0x1800b21de  lea     r8, [rbp+220h+String1]; struct _UNICODE_STRING *
0x1800b21e2  lea     rdx, [rbp+220h+var_280]; struct _KERB_TICKET_CACHE_ENTRY **
0x1800b21e6  mov     rcx, rbx; struct _KERB_LOGON_SESSION *
0x1800b21e9  call    ?KerbGetKpasswdTicket@@YAJPEAU_KERB_LOGON_SESSION@@PEAPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_UNICODE_STRING@@PEAPEAU_KERB_INTERNAL_NAME@@PEAPEAU_KDC_PROXY_CACHE_ENTRY@@@Z; KerbGetKpasswdTicket(_KERB_LOGON_SESSION *,_KERB_TICKET_CACHE_ENTRY * *,_UNICODE_STRING *,_KERB_INTERNAL_NAME * *,_KDC_PROXY_CACHE_ENTRY * *)
0x1800b21ee  mov     edi, eax
0x1800b21f0  test    eax, eax
0x1800b21f2  jns     short loc_1800B2203
0x1800b21f4  mov     esi, 2
0x1800b21f9  mov     r14d, [rsp+320h+var_2B0]
0x1800b21fe  jmp     loc_1800B266B
0x1800b2203  lea     rdx, [rbp+220h+var_290]; struct _KERB_RPC_HOST_ADDRESS **
0x1800b2207  lea     rcx, [rbp+220h+String1]; String1
0x1800b220b  call    ?KerbGetOutgoingKerbHostAddress@@YAJPEAU_UNICODE_STRING@@PEAPEAU_KERB_RPC_HOST_ADDRESS@@@Z; KerbGetOutgoingKerbHostAddress(_UNICODE_STRING *,_KERB_RPC_HOST_ADDRESS * *)
0x1800b2210  mov     edi, eax
0x1800b2212  test    eax, eax
0x1800b2214  jns     short loc_1800B223B
0x1800b2216  lea     r9, aFailedToGetIpA; "Failed to get IP address for message\n"
0x1800b221d  mov     r8d, 1034h
0x1800b2223  lea     rdx, aKerbinlchangem; "KerbINlChangeMachinePassword"
0x1800b222a  mov     ecx, 1
0x1800b222f  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b2234  mov     esi, 9
0x1800b2239  jmp     short loc_1800B21F9
0x1800b223b  mov     rdx, [rbp+220h+var_290]
0x1800b223f  test    rdx, rdx
0x1800b2242  jnz     short loc_1800B2269
0x1800b2244  lea     r9, aNoIpAddresses; "No IP addresses."
0x1800b224b  mov     r8d, 103Bh
0x1800b2251  lea     rdx, aKerbinlchangem; "KerbINlChangeMachinePassword"
0x1800b2258  mov     ecx, 1
0x1800b225d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b2262  mov     edi, 0C00002F1h
0x1800b2267  jmp     short loc_1800B2234
0x1800b2269  mov     r8, [rbp+220h+var_280]
0x1800b226d  add     r8, 0A8h
0x1800b2274  mov     rcx, [r8]
0x1800b2277  mov     rax, [rcx]
0x1800b227a  lea     r9, [rbp+220h+Size]
0x1800b227e  mov     [rsp+320h+var_2E8], r9
0x1800b2283  lea     r9, [rbp+220h+var_1A0]
0x1800b228a  mov     [rsp+320h+var_2F0], r9
0x1800b228f  lea     r9, [rbp+220h+var_1B0]
0x1800b2293  mov     [rsp+320h+var_2F8], r9
0x1800b2298  lea     r9, [rbp+220h+var_230]
0x1800b229c  mov     [rsp+320h+var_300], r9
0x1800b22a1  mov     r14d, [rsp+320h+var_2B0]
0x1800b22a6  mov     r9d, r14d
0x1800b22a9  mov     rax, [rax+110h]
0x1800b22b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b22b5  mov     edi, eax
0x1800b22b7  test    eax, eax
0x1800b22b9  jns     short loc_1800B22E7
0x1800b22bb  mov     dword ptr [rsp+320h+var_300], eax
0x1800b22bf  lea     r9, aFailedToCreate_24; "Failed to create machine password: 0x%x"
0x1800b22c6  mov     r8d, 104Eh
0x1800b22cc  lea     rdx, aKerbinlchangem; "KerbINlChangeMachinePassword"
0x1800b22d3  mov     ecx, 1
0x1800b22d8  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b22dd  mov     esi, 3
0x1800b22e2  jmp     loc_1800B266B
0x1800b22e7  mov     rcx, [rbp+220h+var_280]
0x1800b22eb  movsxd  rax, dword ptr [rcx+158h]
0x1800b22f2  imul    rbx, rax, 989680h
0x1800b22f9  mov     qword ptr [rbp+220h+var_260], rbx
0x1800b22fd  lea     rax, [rcx+110h]
0x1800b2304  lea     r8, [rcx+0A8h]; struct _KERB_ENCRYPTION_KEY *
0x1800b230b  lea     rdx, [rcx+60h]; struct _UNICODE_STRING *
0x1800b230f  lea     r9, [rbp+220h+Src+8]
0x1800b2313  mov     [rsp+320h+var_2B8], r9; unsigned __int8 **
0x1800b2318  lea     r9, [rbp+220h+Src]
0x1800b231c  mov     [rsp+320h+var_2C0], r9; unsigned int *
0x1800b2321  mov     [rsp+320h+var_2C8], 0Bh; unsigned int
0x1800b2329  lea     r9, [rbp+220h+var_260]
0x1800b232d  mov     [rsp+320h+var_2D0], r9; union _LARGE_INTEGER *
0x1800b2332  mov     [rsp+320h+var_2D8], r12; struct KERB_CHECKSUM *
0x1800b2337  mov     dword ptr [rsp+320h+var_2E0], r12d; unsigned int
0x1800b233c  mov     [rsp+320h+var_2E8], rax; struct KERB_TICKET *
0x1800b2341  mov     [rsp+320h+var_2F0], r12; union _LARGE_INTEGER *
0x1800b2346  mov     dword ptr [rsp+320h+var_2F8], r12d; unsigned int
0x1800b234b  mov     [rsp+320h+var_300], r12; struct PKERB_AUTHORIZATION_DATA_s *
0x1800b2350  lea     r9, [rbp+220h+var_1A0]; struct _KERB_ENCRYPTION_KEY *
0x1800b2357  mov     rcx, [rcx+90h]; struct _KERB_INTERNAL_NAME *
0x1800b235e  call    ?KerbCreateApRequest@@YAJPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@PEAU_KERB_ENCRYPTION_KEY@@2PEAUPKERB_AUTHORIZATION_DATA_s@@KPEAT_LARGE_INTEGER@@PEAUKERB_TICKET@@KPEAUKERB_CHECKSUM@@4KPEAKPEAPEAE@Z; KerbCreateApRequest(_KERB_INTERNAL_NAME *,_UNICODE_STRING *,_KERB_ENCRYPTION_KEY *,_KERB_ENCRYPTION_KEY *,PKERB_AUTHORIZATION_DATA_s *,ulong,_LARGE_INTEGER *,KERB_TICKET *,ulong,KERB_CHECKSUM *,_LARGE_INTEGER *,ulong,ulong *,uchar * *)
0x1800b2363  mov     edi, eax
0x1800b2365  mov     rax, 0D6BF94D5E57A42BDh
0x1800b236f  imul    rbx
0x1800b2372  add     rdx, rbx
0x1800b2375  sar     rdx, 17h
0x1800b2379  mov     rcx, rdx
0x1800b237c  shr     rcx, 3Fh
0x1800b2380  add     rdx, rcx
0x1800b2383  mov     rcx, [rbp+220h+var_280]
0x1800b2387  xchg    edx, [rcx+158h]
0x1800b238d  test    edi, edi
0x1800b238f  jz      short loc_1800B23C6
0x1800b2391  mov     dword ptr [rsp+320h+var_300], edi
0x1800b2395  lea     r9, aFailedToCreate_29; "Failed to create AP request for kpasswd"...
0x1800b239c  mov     r8d, 106Ah
0x1800b23a2  lea     rdx, aKerbinlchangem; "KerbINlChangeMachinePassword"
0x1800b23a9  mov     ecx, 1
0x1800b23ae  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b23b3  mov     ecx, edi; int
0x1800b23b5  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x1800b23ba  mov     edi, eax
0x1800b23bc  mov     esi, 4
0x1800b23c1  jmp     loc_1800B266B
0x1800b23c6  mov     eax, dword ptr [rbp+220h+Size]
0x1800b23c9  mov     r12d, dword ptr [rbp+220h+Src]
0x1800b23cd  lea     ecx, [rax+r12]
0x1800b23d1  cmp     ecx, eax
0x1800b23d3  jb      loc_1800B265E
0x1800b23d9  mov     dword ptr [rbp+220h+var_220], ecx
0x1800b23dc  lea     ebx, [rcx+6]
0x1800b23df  cmp     ebx, ecx
0x1800b23e1  jb      loc_1800B265E
0x1800b23e7  mov     ecx, ebx; size
0x1800b23e9  mov     dword ptr [rbp+220h+var_220], ebx
0x1800b23ec  call    MIDL_user_allocate
0x1800b23f1  mov     rdi, rax
0x1800b23f4  mov     qword ptr [rbp+220h+var_220+8], rax
0x1800b23f8  test    rax, rax
0x1800b23fb  jnz     short loc_1800B2407
0x1800b23fd  mov     edi, 0C000009Ah
0x1800b2402  jmp     loc_1800B2663
0x1800b2407  movzx   eax, bx
0x1800b240a  shr     ax, 8
0x1800b240e  mov     [rdi], al
0x1800b2410  mov     [rdi+1], bl
0x1800b2413  mov     word ptr [rdi+2], 100h
0x1800b2419  movzx   eax, r12w
0x1800b241d  shr     ax, 8
0x1800b2421  mov     [rdi+4], al
0x1800b2424  mov     [rdi+5], r12b
0x1800b2428  lea     rcx, [rdi+6]; void *
0x1800b242c  mov     r8, r12; Size
0x1800b242f  mov     rdx, [rbp+220h+Src+8]; Src
0x1800b2433  call    memcpy_0
0x1800b2438  mov     r8d, dword ptr [rbp+220h+Size]; Size
0x1800b243c  lea     rcx, [r12+6]
0x1800b2441  add     rcx, rdi; void *
0x1800b2444  mov     rdx, [rbp+220h+Size+8]; Src
0x1800b2448  call    memcpy_0
0x1800b244d  movups  xmm0, [rbp+220h+var_1A0]
0x1800b2454  movaps  [rbp+220h+var_140], xmm0
0x1800b245b  movups  xmm1, [rbp+220h+var_190]
0x1800b2462  movaps  [rbp+220h+var_130], xmm1
0x1800b2469  movsd   xmm0, [rbp+220h+var_180]
0x1800b2471  movsd   [rbp+220h+var_120], xmm0
0x1800b2479  movaps  xmm1, xmmword ptr [rbp+220h+String1.Length]
0x1800b247d  movdqa  xmmword ptr [rbp+220h+Src], xmm1
0x1800b2482  movaps  xmm0, [rbp+220h+var_220]
0x1800b2486  movdqa  xmmword ptr [rbp+220h+var_260], xmm0
0x1800b248b  xor     r12d, r12d
0x1800b248e  mov     [rsp+320h+var_2F0], r12
0x1800b2493  mov     byte ptr [rsp+320h+var_2F8], r12b
0x1800b2498  lea     rax, [rbp+220h+var_140]
0x1800b249f  mov     [rsp+320h+var_300], rax
0x1800b24a4  lea     r9, [rbp+220h+Src]
0x1800b24a8  lea     r8, [rbp+220h+var_260]
0x1800b24ac  mov     rdx, [rbp+220h+var_288]
0x1800b24b0  mov     rcx, [rbp+220h+var_280]
0x1800b24b4  call    ?KerbIMakeKdcCall@@YAJPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KDC_PROXY_CACHE_ENTRY@@U_KERB_MESSAGE_BUFFER@@U_UNICODE_STRING@@U_KERB_ENCRYPTION_KEY@@EPEAPEAU_DOMAIN_PASSWORD_INFORMATION@@@Z; KerbIMakeKdcCall(_KERB_TICKET_CACHE_ENTRY *,_KDC_PROXY_CACHE_ENTRY *,_KERB_MESSAGE_BUFFER,_UNICODE_STRING,_KERB_ENCRYPTION_KEY,uchar,_DOMAIN_PASSWORD_INFORMATION * *)
0x1800b24b9  mov     edi, eax
0x1800b24bb  test    eax, eax
0x1800b24bd  jns     short loc_1800B24EB
0x1800b24bf  mov     dword ptr [rsp+320h+var_300], eax
0x1800b24c3  lea     r9, aKerbimakekdcca; "KerbIMakeKdcCall failed: 0x%x"
0x1800b24ca  mov     r8d, 109Ch
0x1800b24d0  lea     rdx, aKerbinlchangem; "KerbINlChangeMachinePassword"
  ... truncated ...
```
