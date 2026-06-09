# LsaDbpRebuildFtCacheGC(void)

- ea: `0x180026cf0`
- end: `0x180027331`
- name: `?LsaDbpRebuildFtCacheGC@@YAJXZ`
- size: `1601`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009b24`
- `0x18002a15c`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x18000fd18`
- `0x18000fd40`
- `0x180011d6c`
- `0x18001f3b4`
- `0x18001f5c0`
- `0x18001fbcc`
- `0x1800262bc`
- `0x180026594`
- `0x180026cf0`

## import_xrefs

- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x180026e3e`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x180026e3e`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180026e4d`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180026ea9`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180026eeb`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800272a0`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800272e5`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180026e4d`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180026ea9`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180026eeb`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800272a0`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800272e5`
- `LSASRV!LsapAllocateLsaHeap` at `0x180026f39`
- `LSASRV!LsapAllocateLsaHeap` at `0x180026fca`
- `LSASRV!LsapAllocateLsaHeap` at `0x180026f39`
- `LSASRV!LsapAllocateLsaHeap` at `0x180026fca`
- `LSASRV!LsapFreeLsaHeap` at `0x1800272a9`
- `LSASRV!LsapFreeLsaHeap` at `0x1800272b2`
- `LSASRV!LsapFreeLsaHeap` at `0x1800272a9`
- `LSASRV!LsapFreeLsaHeap` at `0x1800272b2`
- `NTDSA!DirNotifyRegister` at `0x1800270bd`
- `NTDSA!DirNotifyRegister` at `0x1800270bd`
- `NTDSA!SamIAmIGC` at `0x180026e8e`
- `NTDSA!SamIAmIGC` at `0x180026e8e`
- `NTDSA!THClearErrors` at `0x1800270cd`
- `NTDSA!THClearErrors` at `0x1800271d1`
- `NTDSA!THClearErrors` at `0x1800270cd`
- `NTDSA!THClearErrors` at `0x1800271d1`
- `NTDSA!InitCommarg` at `0x18002707a`
- `NTDSA!InitCommarg` at `0x1800271ab`
- `NTDSA!InitCommarg` at `0x18002707a`
- `NTDSA!InitCommarg` at `0x1800271ab`
- `NTDSA!DirSearch` at `0x1800271c1`
- `NTDSA!DirSearch` at `0x1800271c1`
- `NTDSA!GetConfigurationName` at `0x180026f2f`
- `NTDSA!GetConfigurationName` at `0x180026f79`
- `NTDSA!GetConfigurationName` at `0x180026f2f`
- `NTDSA!GetConfigurationName` at `0x180026f79`
- `NTDSA!AppendRDN` at `0x180026fc0`
- `NTDSA!AppendRDN` at `0x18002701d`
- `NTDSA!AppendRDN` at `0x180026fc0`
- `NTDSA!AppendRDN` at `0x18002701d`

## pseudocode

```c
__int64 LsaDbpRebuildFtCacheGC(void)
{
  void *v0; // rcx
  __int64 v1; // rcx
  __int64 v3; // rcx
  int inited; // ebx
  __int64 v5; // r14
  __int64 LsaHeap; // rax
  __int64 v7; // rsi
  int ConfigurationName; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 appended; // rbx
  __int64 v13; // rax
  unsigned int v14; // eax
  int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // r8
  __int64 *v18; // rdi
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  char v24[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-CCh] BYREF
  struct _COMMRES *v26; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v29; // [rsp+58h] [rbp-A8h]
  __int128 v30; // [rsp+68h] [rbp-98h] BYREF
  __int128 v31; // [rsp+78h] [rbp-88h]
  char v32[8]; // [rsp+90h] [rbp-70h] BYREF
  char v33; // [rsp+98h] [rbp-68h]
  char v34; // [rsp+A0h] [rbp-60h]
  int v35; // [rsp+A8h] [rbp-58h]
  int v36; // [rsp+B0h] [rbp-50h]
  struct _DSNAME *v37; // [rsp+B8h] [rbp-48h]
  __int64 v38; // [rsp+110h] [rbp+10h] BYREF
  char v39; // [rsp+118h] [rbp+18h]
  int v40; // [rsp+11Ch] [rbp+1Ch]
  char *v41; // [rsp+120h] [rbp+20h]
  int v42; // [rsp+128h] [rbp+28h]
  __int128 *v43; // [rsp+130h] [rbp+30h]
  __int64 v44; // [rsp+138h] [rbp+38h]
  int v45; // [rsp+140h] [rbp+40h]
  _BYTE v46[192]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v47; // [rsp+208h] [rbp+108h]
  _DWORD v48[4]; // [rsp+220h] [rbp+120h] BYREF
  __int64 v49; // [rsp+230h] [rbp+130h]
  int v50; // [rsp+238h] [rbp+138h]
  int v51; // [rsp+240h] [rbp+140h]
  __int64 v52; // [rsp+248h] [rbp+148h]
  int v53; // [rsp+250h] [rbp+150h]
  int v54; // [rsp+258h] [rbp+158h]
  __int64 v55; // [rsp+260h] [rbp+160h]
  int v56; // [rsp+268h] [rbp+168h]
  int v57; // [rsp+270h] [rbp+170h]
  __int64 v58; // [rsp+278h] [rbp+178h]
  int v59; // [rsp+280h] [rbp+180h]
  int v60; // [rsp+288h] [rbp+188h]
  __int64 v61; // [rsp+290h] [rbp+190h]
  int v62; // [rsp+298h] [rbp+198h]
  int v63; // [rsp+2A0h] [rbp+1A0h]
  __int64 v64; // [rsp+2A8h] [rbp+1A8h]
  int v65; // [rsp+2B0h] [rbp+1B0h]
  int v66; // [rsp+2B8h] [rbp+1B8h]
  __int64 v67; // [rsp+2C0h] [rbp+1C0h]

  v25 = 0;
  memset_0(v32, 0, 0x78u);
  v28 = 0;
  v29 = 0;
  memset_0(&v38, 0, 0x108u);
  v26 = 0;
  v30 = 0;
  v27 = 0;
  v31 = 0;
  v24[0] = 0;
  v48[0] = 589957;
  v48[2] = 0;
  v49 = 0;
  v50 = 589945;
  v51 = 0;
  v52 = 0;
  v53 = 590294;
  v54 = 0;
  v55 = 0;
  v56 = 589956;
  v57 = 0;
  v58 = 0;
  v59 = 589960;
  v60 = 0;
  v61 = 0;
  v62 = 591526;
  v63 = 0;
  v64 = 0;
  v65 = 131120;
  v66 = 0;
  v67 = 0;
  v0 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 340, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
  LsapDbExpAcquireWriteLockTrustedDomainList(v0);
  if ( !g_FTCache )
  {
    LsapDbExpReleaseLockTrustedDomainList(v1);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 341, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, 3221225701LL);
    return 3221225701LL;
  }
  if ( !DcInRootDomain && (unsigned __int8)SamIAmIGC() )
  {
    if ( *((_BYTE *)g_FTCache + 2) )
    {
      LsapDbExpReleaseLockTrustedDomainList(v1);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 343, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
      return 0;
    }
    inited = LsaDbpDsInitAllocAsNeededEx(50331648, 0, v24);
    if ( inited < 0 )
    {
      LsapDbExpReleaseLockTrustedDomainList(v3);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          344,
          &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
          (unsigned int)inited);
      return (unsigned int)inited;
    }
    v25 = 0;
    v5 = 0;
    GetConfigurationName(5, &v25, 0);
    LsaHeap = LsapAllocateLsaHeap(v25);
    v7 = LsaHeap;
    if ( !LsaHeap )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 345, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
      inited = -1073741670;
      goto LABEL_51;
    }
    ConfigurationName = GetConfigurationName(5, &v25, LsaHeap);
    inited = ConfigurationName;
    if ( ConfigurationName < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v10 = 346;
        v11 = (unsigned int)ConfigurationName;
LABEL_50:
        WPP_SF_d(v9[2], v10, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, v11);
      }
LABEL_51:
      LsaDbpForestTrustCacheSetInvalid();
LABEL_46:
      LOBYTE(v17) = v24[0];
      LsaDbpDsDeleteAllocAsNeededEx(50331648, 0, v17);
      LsapDbExpReleaseLockTrustedDomainList(v19);
      LsapFreeLsaHeap(v7, v20, v21);
      LsapFreeLsaHeap(v5, v22, v23);
      return (unsigned int)inited;
    }
    appended = (unsigned int)AppendRDN(v7, 0, 0, L"System", 0, 3);
    v13 = LsapAllocateLsaHeap(appended);
    v5 = v13;
    if ( !v13 )
    {
      inited = -1073741670;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 347, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
      goto LABEL_51;
    }
    AppendRDN(v7, v13, (unsigned int)appended, L"System", 0, 3);
    v45 &= ~1u;
    *(_QWORD *)&v29 = v48;
    v33 = 73;
    v41 = v32;
    v34 = 8;
    v43 = &v28;
    LOBYTE(v28) = 76;
    DWORD2(v28) = 7;
    BYTE8(v29) = 86;
    v38 = v5;
    v39 = 1;
    v40 = 1;
    v42 = 0;
    v44 = 0;
    InitCommarg(v46);
    v47 = 0;
    *(_QWORD *)&v30 = LsaDbpNotifyPrepareToImpersonate;
    DWORD2(v31) = 0;
    *((_QWORD *)&v30 + 1) = LsaDbpForestTrustTransmitDataXrefChange;
    *(_QWORD *)&v31 = LsaDbpNotifyStopImpersonating;
    v14 = DirNotifyRegister(&v38, &v30, &v26);
    if ( v26 )
    {
      inited = LsaDbpDsMapDsReturnToStatusEx(v14, v26);
      if ( inited >= 0 )
      {
        LsaDbpDsContinueTransaction();
        XrefNotificationHandle = *((_DWORD *)v26 + 4);
        memset_0(v32, 0, 0x78u);
        v33 = 73;
        v34 = 0;
        v35 = 590606;
        v15 = *(_DWORD *)qword_180047050;
        v28 = 0;
        v36 = v15;
        *((_QWORD *)&v29 + 1) = 86;
        v37 = qword_180047050;
        *(_QWORD *)&v29 = v48;
        LOBYTE(v28) = 76;
        DWORD2(v28) = 7;
        memset_0(&v38, 0, 0x108u);
        v38 = v5;
        v41 = v32;
        v39 = 1;
        v43 = &v28;
        v40 = 1;
        v42 = 0;
        v44 = 0;
        v45 = 0;
        InitCommarg(v46);
        v47 = 0;
        v16 = DirSearch(&v38, &v27);
        if ( v27 )
        {
          inited = LsaDbpDsMapDsReturnToStatusEx(v16, (struct _COMMRES *)(v27 + 96));
          if ( inited >= 0 )
          {
            if ( !*(_DWORD *)(v27 + 16) || (v18 = (__int64 *)(v27 + 24), v27 == -24) )
            {
LABEL_42:
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
              inited = 0;
              *((_BYTE *)g_FTCache + 2) = 1;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 351, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
              goto LABEL_46;
            }
            while ( 1 )
            {
              inited = LsaDbpForestTrustCacheInsertEntInf((struct _ENTINF *)(v18 + 1));
              if ( (int)(inited + 0x80000000) >= 0 && inited != -1073741275 )
                break;
              v18 = (__int64 *)*v18;
              if ( !v18 )
                goto LABEL_42;
            }
            v9 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
              goto LABEL_51;
            v10 = 350;
LABEL_49:
            v11 = (unsigned int)inited;
            goto LABEL_50;
          }
        }
        else
        {
          THClearErrors();
          inited = -1073741801;
        }
        v9 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_51;
        v10 = 349;
        goto LABEL_49;
      }
    }
    else
    {
      THClearErrors();
      inited = -1073741801;
    }
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_51;
    v10 = 348;
    goto LABEL_49;
  }
  LsapDbExpReleaseLockTrustedDomainList(v1);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 342, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
  return 3221225693LL;
}

```

## disassembly

```asm
0x180026cf0  push    rbp
0x180026cf2  push    rbx
0x180026cf3  push    rsi
0x180026cf4  push    rdi
0x180026cf5  push    r12
0x180026cf7  push    r13
0x180026cf9  push    r14
0x180026cfb  push    r15
0x180026cfd  lea     rbp, [rsp-1E8h]
0x180026d05  sub     rsp, 2E8h
0x180026d0c  mov     rax, cs:__security_cookie
0x180026d13  xor     rax, rsp
0x180026d16  mov     [rbp+220h+var_50], rax
0x180026d1d  xor     r15d, r15d
0x180026d20  lea     rcx, [rbp+220h+var_290]; void *
0x180026d24  xor     edx, edx; Val
0x180026d26  mov     [rsp+320h+var_2EC], r15d
0x180026d2b  lea     r8d, [r15+78h]; Size
0x180026d2f  call    memset_0
0x180026d34  xorps   xmm0, xmm0
0x180026d37  lea     rcx, [rbp+220h+var_210]; void *
0x180026d3b  xor     edx, edx; Val
0x180026d3d  mov     r8d, 108h; Size
0x180026d43  movups  [rsp+320h+var_2D8], xmm0
0x180026d48  movups  [rsp+320h+var_2C8], xmm0
0x180026d4d  call    memset_0
0x180026d52  xorps   xmm0, xmm0
0x180026d55  mov     [rsp+320h+var_2E8], r15
0x180026d5a  movups  [rsp+320h+var_2B8], xmm0
0x180026d5f  mov     [rsp+320h+var_2E0], r15
0x180026d64  movups  [rsp+320h+var_2A8], xmm0
0x180026d69  mov     [rsp+320h+var_2F0], r15b
0x180026d6e  mov     [rbp+220h+var_100], 90085h
0x180026d78  mov     [rbp+220h+var_F8], r15d
0x180026d7f  mov     [rbp+220h+var_F0], r15
0x180026d86  mov     [rbp+220h+var_E8], 90079h
0x180026d90  mov     [rbp+220h+var_E0], r15d
0x180026d97  mov     [rbp+220h+var_D8], r15
0x180026d9e  mov     [rbp+220h+var_D0], 901D6h
0x180026da8  mov     [rbp+220h+var_C8], r15d
0x180026daf  mov     [rbp+220h+var_C0], r15
0x180026db6  mov     [rbp+220h+var_B8], 90084h
0x180026dc0  mov     [rbp+220h+var_B0], r15d
0x180026dc7  mov     [rbp+220h+var_A8], r15
0x180026dce  mov     [rbp+220h+var_A0], 90088h
0x180026dd8  mov     [rbp+220h+var_98], r15d
0x180026ddf  mov     [rbp+220h+var_90], r15
0x180026de6  mov     [rbp+220h+var_88], 906A6h
0x180026df0  mov     [rbp+220h+var_80], r15d
0x180026df7  mov     [rbp+220h+var_78], r15
0x180026dfe  mov     [rbp+220h+var_70], 20030h
0x180026e08  mov     [rbp+220h+var_68], r15d
0x180026e0f  mov     [rbp+220h+var_60], r15
0x180026e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e1d  lea     r13, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180026e24  mov     r12b, 8
0x180026e27  test    [rcx+1Ch], r12b
0x180026e2b  jz      short loc_180026E3E
0x180026e2d  mov     rcx, [rcx+10h]
0x180026e31  mov     edx, 154h
0x180026e36  mov     r8, r13
0x180026e39  call    WPP_SF_
0x180026e3e  call    cs:__imp_LsapDbExpAcquireWriteLockTrustedDomainList
0x180026e44  cmp     cs:?g_FTCache@@3PEAVFTCache@@EA, r15; FTCache * g_FTCache
0x180026e4b  jnz     short loc_180026E81
0x180026e4d  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x180026e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e5a  test    [rcx+1Ch], r12b
0x180026e5e  jz      short loc_180026E77
0x180026e60  mov     rcx, [rcx+10h]
0x180026e64  mov     edx, 155h
0x180026e69  mov     r9d, 0C00000E5h
0x180026e6f  mov     r8, r13
0x180026e72  call    WPP_SF_d
0x180026e77  mov     eax, 0C00000E5h
0x180026e7c  jmp     loc_18002730E
0x180026e81  cmp     cs:?DcInRootDomain@@3EA, r15b; uchar DcInRootDomain
0x180026e88  jnz     loc_1800272E5
0x180026e8e  call    cs:__imp_SamIAmIGC
0x180026e94  test    al, al
0x180026e96  jz      loc_1800272E5
0x180026e9c  mov     rax, cs:?g_FTCache@@3PEAVFTCache@@EA; FTCache * g_FTCache
0x180026ea3  cmp     [rax+2], r15b
0x180026ea7  jz      short loc_180026ED4
0x180026ea9  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x180026eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180026eb6  test    [rcx+1Ch], r12b
0x180026eba  jz      short loc_180026ECD
0x180026ebc  mov     rcx, [rcx+10h]
0x180026ec0  mov     edx, 157h
0x180026ec5  mov     r8, r13
0x180026ec8  call    WPP_SF_
0x180026ecd  xor     eax, eax
0x180026ecf  jmp     loc_18002730E
0x180026ed4  lea     r8, [rsp+320h+var_2F0]
0x180026ed9  xor     edx, edx
0x180026edb  mov     ecx, 3000000h
0x180026ee0  call    ?LsaDbpDsInitAllocAsNeededEx@@YAJKW4_LSAP_DB_OBJECT_TYPE_ID@@PEAE@Z; LsaDbpDsInitAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar *)
0x180026ee5  mov     ebx, eax
0x180026ee7  test    eax, eax
0x180026ee9  jns     short loc_180026F19
0x180026eeb  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x180026ef1  mov     rcx, cs:WPP_GLOBAL_Control
0x180026ef8  test    [rcx+1Ch], r12b
0x180026efc  jz      short loc_180026F12
0x180026efe  mov     rcx, [rcx+10h]
0x180026f02  mov     edx, 158h
0x180026f07  mov     r9d, ebx
0x180026f0a  mov     r8, r13
0x180026f0d  call    WPP_SF_d
0x180026f12  mov     eax, ebx
0x180026f14  jmp     loc_18002730E
0x180026f19  xor     r8d, r8d
0x180026f1c  mov     [rsp+320h+var_2EC], r15d
0x180026f21  lea     rdx, [rsp+320h+var_2EC]
0x180026f26  mov     r14, r15
0x180026f29  lea     ebx, [r8+5]
0x180026f2d  mov     ecx, ebx
0x180026f2f  call    cs:__imp_GetConfigurationName
0x180026f35  mov     ecx, [rsp+320h+var_2EC]
0x180026f39  call    cs:__imp_LsapAllocateLsaHeap
0x180026f3f  mov     rsi, rax
0x180026f42  test    rax, rax
0x180026f45  jnz     short loc_180026F6F
0x180026f47  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f4e  test    [rcx+1Ch], r12b
0x180026f52  jz      short loc_180026F65
0x180026f54  mov     rcx, [rcx+10h]
0x180026f58  mov     edx, 159h
0x180026f5d  mov     r8, r13
0x180026f60  call    WPP_SF_
0x180026f65  mov     ebx, 0C000009Ah
0x180026f6a  jmp     loc_1800272DE
0x180026f6f  mov     r8, rsi
0x180026f72  lea     rdx, [rsp+320h+var_2EC]
0x180026f77  mov     ecx, ebx
0x180026f79  call    cs:__imp_GetConfigurationName
0x180026f7f  mov     ebx, eax
0x180026f81  test    eax, eax
0x180026f83  jns     short loc_180026FA3
0x180026f85  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f8c  test    [rcx+1Ch], r12b
0x180026f90  jz      loc_1800272DE
0x180026f96  mov     edx, 15Ah
0x180026f9b  mov     r9d, eax
0x180026f9e  jmp     loc_1800272D2
0x180026fa3  mov     edi, 3
0x180026fa8  lea     r9, aSystem; "System"
0x180026faf  mov     [rsp+320h+var_2F8], edi
0x180026fb3  xor     r8d, r8d
0x180026fb6  xor     edx, edx
0x180026fb8  mov     [rsp+320h+var_300], r15d
0x180026fbd  mov     rcx, rsi
0x180026fc0  call    cs:__imp_AppendRDN
0x180026fc6  mov     ecx, eax
0x180026fc8  mov     ebx, eax
0x180026fca  call    cs:__imp_LsapAllocateLsaHeap
0x180026fd0  mov     r14, rax
0x180026fd3  test    rax, rax
0x180026fd6  jnz     short loc_180027004
0x180026fd8  mov     ebx, 0C000009Ah
0x180026fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180026fe4  test    [rcx+1Ch], r12b
0x180026fe8  jz      loc_1800272DE
0x180026fee  mov     rcx, [rcx+10h]
0x180026ff2  mov     edx, 15Bh
0x180026ff7  mov     r8, r13
0x180026ffa  call    WPP_SF_
0x180026fff  jmp     loc_1800272DE
0x180027004  mov     [rsp+320h+var_2F8], edi
0x180027008  lea     r9, aSystem; "System"
0x18002700f  mov     r8d, ebx
0x180027012  mov     [rsp+320h+var_300], r15d
0x180027017  mov     rdx, r14
0x18002701a  mov     rcx, rsi
0x18002701d  call    cs:__imp_AppendRDN
0x180027023  and     [rbp+220h+var_1E0], 0FFFFFFFEh
0x180027027  lea     rax, [rbp+220h+var_100]
0x18002702e  mov     qword ptr [rsp+320h+var_2C8], rax
0x180027033  lea     rcx, [rbp+220h+var_1D8]
0x180027037  lea     rax, [rbp+220h+var_290]
0x18002703b  mov     [rbp+220h+var_288], 49h ; 'I'
0x18002703f  mov     [rbp+220h+var_200], rax
0x180027043  mov     edi, 1
0x180027048  lea     rax, [rsp+320h+var_2D8]
0x18002704d  mov     [rbp+220h+var_280], r12b
0x180027051  mov     [rbp+220h+var_1F0], rax
0x180027055  mov     byte ptr [rsp+320h+var_2D8], 4Ch ; 'L'
0x18002705a  mov     dword ptr [rsp+320h+var_2D8+8], 7
0x180027062  mov     byte ptr [rsp+320h+var_2C8+8], 56h ; 'V'
0x180027067  mov     [rbp+220h+var_210], r14
0x18002706b  mov     [rbp+220h+var_208], dil
0x18002706f  mov     [rbp+220h+var_204], edi
0x180027072  mov     [rbp+220h+var_1F8], r15d
0x180027076  mov     [rbp+220h+var_1E8], r15
0x18002707a  call    cs:__imp_InitCommarg
0x180027080  lea     rax, ?LsaDbpNotifyPrepareToImpersonate@@YAHKKPEAPEAX@Z; LsaDbpNotifyPrepareToImpersonate(ulong,ulong,void * *)
0x180027087  mov     [rbp+220h+var_118], r15
0x18002708e  mov     qword ptr [rsp+320h+var_2B8], rax
0x180027093  lea     r8, [rsp+320h+var_2E8]
0x180027098  lea     rax, ?LsaDbpForestTrustTransmitDataXrefChange@@YAXKKPEAU_ENTINF@@@Z; LsaDbpForestTrustTransmitDataXrefChange(ulong,ulong,_ENTINF *)
0x18002709f  mov     dword ptr [rbp+220h+var_2A8+8], r15d
0x1800270a3  mov     qword ptr [rsp+320h+var_2B8+8], rax
0x1800270a8  lea     rdx, [rsp+320h+var_2B8]
0x1800270ad  lea     rax, ?LsaDbpNotifyStopImpersonating@@YAXKKPEAX@Z; LsaDbpNotifyStopImpersonating(ulong,ulong,void *)
0x1800270b4  lea     rcx, [rbp+220h+var_210]
0x1800270b8  mov     qword ptr [rsp+320h+var_2A8], rax
0x1800270bd  call    cs:__imp_DirNotifyRegister
0x1800270c3  mov     rdx, [rsp+320h+var_2E8]; struct _COMMRES *
0x1800270c8  test    rdx, rdx
0x1800270cb  jnz     short loc_1800270DA
0x1800270cd  call    cs:__imp_THClearErrors
0x1800270d3  mov     ebx, 0C0000017h
0x1800270d8  jmp     short loc_1800270E7
0x1800270da  mov     ecx, eax; unsigned int
0x1800270dc  call    ?LsaDbpDsMapDsReturnToStatusEx@@YAJKPEAU_COMMRES@@@Z; LsaDbpDsMapDsReturnToStatusEx(ulong,_COMMRES *)
0x1800270e1  mov     ebx, eax
0x1800270e3  test    eax, eax
0x1800270e5  jns     short loc_180027102
0x1800270e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800270ee  test    [rcx+1Ch], r12b
0x1800270f2  jz      loc_1800272DE
0x1800270f8  mov     edx, 15Ch
0x1800270fd  jmp     loc_1800272CF
0x180027102  call    ?LsaDbpDsContinueTransaction@@YAXXZ; LsaDbpDsContinueTransaction(void)
0x180027107  mov     rax, [rsp+320h+var_2E8]
0x18002710c  xor     edx, edx; Val
0x18002710e  mov     ecx, [rax+10h]
0x180027111  lea     r8d, [rdx+78h]; Size
0x180027115  mov     cs:?XrefNotificationHandle@@3KA, ecx; ulong XrefNotificationHandle
0x18002711b  lea     rcx, [rbp+220h+var_290]; void *
0x18002711f  call    memset_0
0x180027124  mov     rcx, cs:qword_180047050
0x18002712b  xorps   xmm0, xmm0
0x18002712e  mov     [rbp+220h+var_288], 49h ; 'I'
0x180027132  xor     edx, edx; Val
0x180027134  mov     [rbp+220h+var_280], r15b
0x180027138  mov     r8d, 108h; Size
0x18002713e  mov     [rbp+220h+var_278], 9030Eh
0x180027145  mov     eax, [rcx]
0x180027147  movups  [rsp+320h+var_2D8], xmm0
0x18002714c  mov     [rbp+220h+var_270], eax
0x18002714f  lea     rax, [rbp+220h+var_100]
0x180027156  movups  [rsp+320h+var_2C8], xmm0
0x18002715b  mov     [rbp+220h+var_268], rcx
0x18002715f  lea     rcx, [rbp+220h+var_210]; void *
0x180027163  mov     qword ptr [rsp+320h+var_2C8], rax
0x180027168  mov     byte ptr [rsp+320h+var_2D8], 4Ch ; 'L'
0x18002716d  mov     dword ptr [rsp+320h+var_2D8+8], 7
0x180027175  mov     byte ptr [rsp+320h+var_2C8+8], 56h ; 'V'
0x18002717a  call    memset_0
0x18002717f  lea     rax, [rbp+220h+var_290]
0x180027183  mov     [rbp+220h+var_210], r14
0x180027187  mov     [rbp+220h+var_200], rax
0x18002718b  lea     rcx, [rbp+220h+var_1D8]
0x18002718f  lea     rax, [rsp+320h+var_2D8]
0x180027194  mov     [rbp+220h+var_208], dil
0x180027198  mov     [rbp+220h+var_1F0], rax
0x18002719c  mov     [rbp+220h+var_204], edi
0x18002719f  mov     [rbp+220h+var_1F8], r15d
0x1800271a3  mov     [rbp+220h+var_1E8], r15
0x1800271a7  mov     [rbp+220h+var_1E0], r15d
0x1800271ab  call    cs:__imp_InitCommarg
0x1800271b1  lea     rdx, [rsp+320h+var_2E0]
0x1800271b6  mov     [rbp+220h+var_118], r15
0x1800271bd  lea     rcx, [rbp+220h+var_210]
0x1800271c1  call    cs:__imp_DirSearch
0x1800271c7  mov     rdx, [rsp+320h+var_2E0]
0x1800271cc  test    rdx, rdx
0x1800271cf  jnz     short loc_1800271DE
0x1800271d1  call    cs:__imp_THClearErrors
0x1800271d7  mov     ebx, 0C0000017h
0x1800271dc  jmp     short loc_1800271EF
0x1800271de  add     rdx, 60h ; '`'; struct _COMMRES *
0x1800271e2  mov     ecx, eax; unsigned int
0x1800271e4  call    ?LsaDbpDsMapDsReturnToStatusEx@@YAJKPEAU_COMMRES@@@Z; LsaDbpDsMapDsReturnToStatusEx(ulong,_COMMRES *)
0x1800271e9  mov     ebx, eax
0x1800271eb  test    eax, eax
0x1800271ed  jns     short loc_18002720A
0x1800271ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271f6  test    [rcx+1Ch], r12b
0x1800271fa  jz      loc_1800272DE
0x180027200  mov     edx, 15Dh
0x180027205  jmp     loc_1800272CF
0x18002720a  mov     rdi, [rsp+320h+var_2E0]
0x18002720f  cmp     [rdi+10h], r15d
0x180027213  jbe     short loc_180027245
0x180027215  add     rdi, 18h
0x180027219  jz      short loc_180027245
0x18002721b  lea     rcx, [rdi+8]; struct _ENTINF *
0x18002721f  call    ?LsaDbpForestTrustCacheInsertEntInf@@YAJPEAU_ENTINF@@@Z; LsaDbpForestTrustCacheInsertEntInf(_ENTINF *)
0x180027224  mov     ecx, 80000000h
0x180027229  mov     ebx, eax
0x18002722b  add     eax, ecx
0x18002722d  test    ecx, eax
0x18002722f  jnz     short loc_18002723D
0x180027231  cmp     ebx, 0C0000225h
0x180027237  jnz     loc_1800272BD
0x18002723d  mov     rdi, [rdi]
0x180027240  test    rdi, rdi
  ... truncated ...
```
