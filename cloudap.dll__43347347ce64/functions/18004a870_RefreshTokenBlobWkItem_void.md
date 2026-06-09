# RefreshTokenBlobWkItem(void *)

- ea: `0x18004a870`
- end: `0x18004af0e`
- name: `?RefreshTokenBlobWkItem@@YAKPEAX@Z`
- size: `1694`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, installer_update`

## callees

- `0x180007ef0`
- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000ce50`
- `0x18000e7e0`
- `0x18000e900`
- `0x18000ee60`
- `0x18000fb70`
- `0x18000fd50`
- `0x180010320`
- `0x18002223c`
- `0x18002ae10`
- `0x18002ce50`
- `0x1800335f4`
- `0x180039090`
- `0x180046f44`
- `0x18004a870`
- `0x18007f9f0`
- `0x180081010`

## string_xrefs

- `0x18004a8db`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a93d`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004a99e`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004aa2b`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004aaad`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004ab18`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004abcc`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004ac54`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004acdb`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004ad44`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004abb6`: `CacheData`
- `0x18004abee`: `GetLogonCacheForUser`
- `0x18004aac9`: `RefreshToken`
- `0x18004ab3e`: `%!FUNC!: Aborting operation because a online logon thread is in progress`
- `0x18004acf3`: `UpdatePluginOpaqueCacheBlob`
- `0x18004ad5c`: `SaveCaches`

## pseudocode

```c
__int64 __fastcall RefreshTokenBlobWkItem(char *Parameter)
{
  struct _LOGON_SESSION *v2; // r14
  struct _ApPluginPkg *v3; // rdi
  struct _CloudAPCache *v4; // r15
  const char *v5; // rax
  __int64 v6; // r8
  const char *v7; // rax
  __int64 v8; // r8
  const char *v9; // rax
  __int64 v10; // r8
  __int64 v11; // rbx
  const char *v12; // rax
  __int64 v13; // r8
  const char *v14; // rax
  __int64 v15; // r8
  const char *v16; // rax
  __int64 v17; // r8
  const char *v18; // rax
  __int64 v19; // r8
  const char *v20; // rax
  __int64 v21; // r8
  __int64 v22; // rdx
  const char *v23; // rax
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  const char *v27; // rax
  __int64 v28; // r8
  _BYTE *v29; // rax
  __int64 v30; // rcx
  _BYTE *v31; // rcx
  __int64 v32; // rax
  _BYTE *v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  char *v36; // rcx
  _DWORD *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // r9
  _BYTE *v41; // r8
  struct _APPLUGIN_USER_INFO **v43; // [rsp+20h] [rbp-89h]
  struct _APPLUGIN_USER_INFO **v44; // [rsp+20h] [rbp-89h]
  struct _APPLUGIN_USER_INFO **v45; // [rsp+20h] [rbp-89h]
  struct _APPLUGIN_USER_INFO **v46; // [rsp+20h] [rbp-89h]
  struct _ApPluginPkg *v47; // [rsp+50h] [rbp-59h] BYREF
  struct _CloudAPCache *v48; // [rsp+58h] [rbp-51h] BYREF
  struct _APPLUGIN_USER_INFO *v49; // [rsp+60h] [rbp-49h] BYREF
  _DWORD *v50; // [rsp+68h] [rbp-41h] BYREF
  __int128 v51; // [rsp+70h] [rbp-39h] BYREF
  __int128 v52; // [rsp+80h] [rbp-29h] BYREF
  _DWORD v53[2]; // [rsp+90h] [rbp-19h] BYREF
  void *v54; // [rsp+98h] [rbp-11h]
  __int128 v55; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v56; // [rsp+B0h] [rbp+7h] BYREF
  __int128 v57; // [rsp+C0h] [rbp+17h]
  unsigned int LogonCacheForUser; // [rsp+110h] [rbp+67h] BYREF
  size_t Size; // [rsp+118h] [rbp+6Fh] BYREF
  void *Buf1; // [rsp+120h] [rbp+77h] BYREF
  struct _LOGON_SESSION *v61; // [rsp+128h] [rbp+7Fh] BYREF

  v53[1] = 0;
  LODWORD(Size) = 0;
  v61 = 0;
  v2 = 0;
  v47 = 0;
  v3 = 0;
  v48 = 0;
  v4 = 0;
  Buf1 = 0;
  v49 = 0;
  v50 = 0;
  v52 = 0;
  v56 = 0;
  v57 = 0;
  v55 = 0;
  v51 = 0;
  if ( !Parameter )
  {
    LogonCacheForUser = -1073741595;
    v5 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v6, v5, 2406, "Shouldn't happen", &Class);
    goto LABEL_36;
  }
  LogonCacheForUser = _AcquireLogonSession(1, (struct _LUID *)(Parameter + 4), &v61);
  if ( LogonCacheForUser )
  {
    v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v8, v7, 2412, "AcquireLogonSession", &Class);
    v2 = v61;
    goto LABEL_36;
  }
  v2 = v61;
  LogonCacheForUser = RefPackage((struct _GUID *)((char *)v61 + 36), &v47);
  if ( LogonCacheForUser )
  {
    v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v9, 2417, "RefPackage", &Class);
    v3 = v47;
    goto LABEL_36;
  }
  v3 = v47;
  if ( *((_QWORD *)v47 + 32) )
  {
    *((_QWORD *)&v52 + 1) = Parameter + 16;
    LODWORD(v52) = *((_DWORD *)Parameter + 3);
    v11 = *((_QWORD *)v2 + 7);
    LockAndUnProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v11, 0);
    LogonCacheForUser = DuplicateCredentialData(
                          (struct _USER_CACHE_ENTRY *)v11,
                          (struct _AP_BLOB *)&v51,
                          (struct _tagCacheNodeIdentifier *)&v55);
    if ( LogonCacheForUser )
    {
      v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v12, 2433, "DuplicateCredentialData", &Class);
      goto LABEL_34;
    }
    UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v11);
    LogonCacheForUser = (*((__int64 (__fastcall **)(_QWORD, __int128 *, __int128 *, void **, size_t *, _DWORD **))v3 + 32))(
                          *((_QWORD *)v3 + 1),
                          &v51,
                          &v52,
                          &Buf1,
                          &Size,
                          &v50);
    if ( (LogonCacheForUser & 0x80000000) != 0 )
    {
      Buf1 = 0;
      v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(v43) = 2448;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v15, v14, v43, "RefreshToken", &Class);
      goto LABEL_36;
    }
    if ( Buf1 && (_DWORD)Size )
    {
      v11 = *((_QWORD *)v2 + 7);
      LockAndUnProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v11, 1);
      if ( !**(_DWORD **)(v11 + 360) )
      {
        if ( (_DWORD)Size != *(_DWORD *)(v11 + 280) || memcmp_0(Buf1, *(const void **)(v11 + 288), (unsigned int)Size) )
        {
          if ( !(unsigned int)IsCredentialDataSame(
                                (struct _USER_CACHE_ENTRY *)v11,
                                (struct _AP_BLOB *)&v51,
                                (struct _tagCacheNodeIdentifier *)&v55) )
          {
            LogonCacheForUser = -1073741564;
            goto LABEL_34;
          }
          LogonCacheForUser = _GetLogonCacheForUser(
                                *((const unsigned __int16 **)v3 + 43),
                                (const unsigned __int16 *)(v11 + 104),
                                L"CacheData",
                                &v48);
          if ( LogonCacheForUser )
          {
            v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            LODWORD(v43) = 2502;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v19, v18, v43, "GetLogonCacheForUser", &Class);
            v4 = v48;
            goto LABEL_34;
          }
          v4 = v48;
          v54 = Buf1;
          v53[0] = Size;
          LogonCacheForUser = ValidateUserInfo(
                                v3,
                                (struct _GUID *)((char *)v48 + 4),
                                (unsigned __int8 *)Buf1,
                                Size,
                                &v49,
                                0,
                                0,
                                0);
          if ( LogonCacheForUser )
          {
            v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            LODWORD(v44) = 2516;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v21, v20, v44, "ValidateUserInfo", &Class);
            goto LABEL_34;
          }
          *(_QWORD *)&v56 = *((_QWORD *)v3 + 1);
          *((_QWORD *)&v56 + 1) = *((_QWORD *)v3 + 29);
          *(_QWORD *)&v57 = *((_QWORD *)v3 + 30);
          *((_QWORD *)&v57 + 1) = SecureFreeCacheData;
          LogonCacheForUser = UpdatePluginOpaqueCacheBlob(
                                v4,
                                (struct _tagCacheNodeIdentifier *)(v11 + 296),
                                *(struct _CREDENTIAL_KEY **)(v11 + 264),
                                (struct _AP_BLOB *)v53,
                                (struct _tagCacheDataFuncs *)&v56);
          if ( LogonCacheForUser )
          {
            v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            LODWORD(v45) = 2529;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v24, v23, v45, "UpdatePluginOpaqueCacheBlob", &Class);
            goto LABEL_34;
          }
          LOBYTE(v22) = 1;
          LogonCacheForUser = SaveCaches(
                                (const unsigned __int16 **)v3,
                                v22,
                                1,
                                v4,
                                (struct _USER_CACHE_ENTRY *)v11,
                                v49,
                                0,
                                0,
                                0);
          v26 = LogonCacheForUser;
          if ( LogonCacheForUser )
          {
            v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            LODWORD(v46) = 2541;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v28, v27, v46, "SaveCaches", &Class);
            goto LABEL_34;
          }
          v29 = *(_BYTE **)(v11 + 288);
          if ( v29 )
          {
            v30 = *(unsigned int *)(v11 + 280);
            if ( *(_DWORD *)(v11 + 280) )
            {
              do
              {
                *v29++ = 0;
                --v30;
              }
              while ( v30 );
            }
            ((void (__fastcall *)(_QWORD, __int64, __int64))g_pLsaFunctionTable->FreeLsaHeap)(
              *(_QWORD *)(v11 + 288),
              v25,
              v26);
          }
          *(_QWORD *)(v11 + 288) = Buf1;
          *(_DWORD *)(v11 + 280) = Size;
          Buf1 = 0;
        }
        LogonCacheForUser = 0;
        goto LABEL_34;
      }
      LogonCacheForUser = -1073741248;
      v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(v43) = 2473;
      WPPTraceLogA(
        1,
        "0x%08x %s:%u : %s:%ws",
        v17,
        v16,
        v43,
        "%!FUNC!: Aborting operation because a online logon thread is in progress",
        &Class);
LABEL_34:
      UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v11);
      goto LABEL_36;
    }
  }
  LogonCacheForUser = 0;
LABEL_36:
  CloudAPProvider::RefreshTokenBlob<long &>((int *)&LogonCacheForUser);
  DerefPackage(v3);
  ReleaseLogonSession(v2);
  FreeCloudAPCache(v4);
  v31 = Buf1;
  if ( Buf1 )
  {
    v32 = (unsigned int)Size;
    if ( (_DWORD)Size )
    {
      do
      {
        *v31++ = 0;
        --v32;
      }
      while ( v32 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  v33 = (_BYTE *)*((_QWORD *)&v51 + 1);
  if ( *((_QWORD *)&v51 + 1) )
  {
    v34 = (unsigned int)v51;
    if ( (_DWORD)v51 )
    {
      do
      {
        *v33++ = 0;
        --v34;
      }
      while ( v34 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  if ( Parameter )
  {
    v35 = *((unsigned int *)Parameter + 3);
    v36 = Parameter + 16;
    if ( *((_DWORD *)Parameter + 3) )
    {
      do
      {
        *v36++ = 0;
        --v35;
      }
      while ( v35 );
    }
    ((void (__fastcall *)(char *))g_pLsaFunctionTable->FreeLsaHeap)(Parameter);
  }
  FreeUserInfo(v49);
  v37 = v50;
  if ( v50 )
  {
    v38 = 0;
    if ( *v50 )
    {
      do
      {
        v39 = 8LL * (unsigned int)v38;
        v40 = (unsigned int)v37[v39 + 6];
        v41 = *(_BYTE **)&v37[v39 + 8];
        if ( v37[v39 + 6] )
        {
          do
          {
            *v41++ = 0;
            --v40;
          }
          while ( v40 );
          v37 = v50;
        }
        v38 = (unsigned int)(v38 + 1);
      }
      while ( (unsigned int)v38 < *v37 );
    }
    ((void (__fastcall *)(_DWORD *, __int64))g_pLsaFunctionTable->FreeLsaHeap)(v37, v38);
  }
  if ( *((_QWORD *)&v55 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  return 0;
}

```

## disassembly

```asm
0x18004a870  push    rbp
0x18004a872  push    rbx
0x18004a873  push    rsi
0x18004a874  push    rdi
0x18004a875  push    r12
0x18004a877  push    r14
0x18004a879  push    r15
0x18004a87b  lea     rbp, [rsp-27h]
0x18004a880  sub     rsp, 0D0h
0x18004a887  xor     r12d, r12d
0x18004a88a  xorps   xmm0, xmm0
0x18004a88d  mov     [rbp+57h+var_6C], r12d
0x18004a891  xorps   xmm1, xmm1
0x18004a894  mov     dword ptr [rbp+57h+Size], r12d
0x18004a898  mov     rsi, rcx
0x18004a89b  mov     [rbp+57h+arg_18], r12
0x18004a89f  mov     r14d, r12d
0x18004a8a2  mov     [rbp+57h+var_B0], r12
0x18004a8a6  mov     edi, r12d
0x18004a8a9  mov     [rbp+57h+var_A8], r12
0x18004a8ad  mov     r15d, r12d
0x18004a8b0  mov     [rbp+57h+Buf1], r12
0x18004a8b4  mov     [rbp+57h+var_A0], r12
0x18004a8b8  mov     [rbp+57h+var_98], r12
0x18004a8bc  movups  [rbp+57h+var_80], xmm0
0x18004a8c0  movups  [rbp+57h+var_50], xmm0
0x18004a8c4  movups  [rbp+57h+var_40], xmm0
0x18004a8c8  movups  [rbp+57h+var_60], xmm0
0x18004a8cc  movups  [rbp+57h+var_90], xmm1
0x18004a8d0  test    rcx, rcx
0x18004a8d3  jnz     short loc_18004A921
0x18004a8d5  mov     r8d, 0C00000E5h
0x18004a8db  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a8e2  mov     [rbp+57h+arg_0], r8d
0x18004a8e6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a8eb  lea     rcx, Class
0x18004a8f2  mov     [rsp+100h+var_D0], rcx
0x18004a8f7  lea     rcx, aShouldnTHappen; "Shouldn't happen"
0x18004a8fe  mov     [rsp+100h+var_D8], rcx
0x18004a903  mov     dword ptr [rsp+100h+var_E0], 966h
0x18004a90b  mov     r9, rax
0x18004a90e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004a915  xor     ecx, ecx
0x18004a917  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004a91c  jmp     loc_18004ADD9
0x18004a921  lea     rdx, [rcx+4]; struct _LUID *
0x18004a925  mov     ecx, 1; int
0x18004a92a  lea     r8, [rbp+57h+arg_18]; struct _LOGON_SESSION **
0x18004a92e  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x18004a933  mov     [rbp+57h+arg_0], eax
0x18004a936  mov     r8d, eax
0x18004a939  test    eax, eax
0x18004a93b  jz      short loc_18004A983
0x18004a93d  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a944  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a949  lea     rcx, Class
0x18004a950  mov     r9, rax
0x18004a953  mov     [rsp+100h+var_D0], rcx
0x18004a958  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004a95f  lea     rcx, aAcquirelogonse_0; "AcquireLogonSession"
0x18004a966  mov     [rsp+100h+var_D8], rcx
0x18004a96b  xor     ecx, ecx
0x18004a96d  mov     dword ptr [rsp+100h+var_E0], 96Ch
0x18004a975  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004a97a  mov     r14, [rbp+57h+arg_18]
0x18004a97e  jmp     loc_18004ADD9
0x18004a983  mov     r14, [rbp+57h+arg_18]
0x18004a987  lea     rdx, [rbp+57h+var_B0]; struct _ApPluginPkg **
0x18004a98b  lea     rcx, [r14+24h]; struct _GUID *
0x18004a98f  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x18004a994  mov     [rbp+57h+arg_0], eax
0x18004a997  mov     r8d, eax
0x18004a99a  test    eax, eax
0x18004a99c  jz      short loc_18004A9E4
0x18004a99e  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004a9a5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004a9aa  lea     rcx, Class
0x18004a9b1  mov     r9, rax
0x18004a9b4  mov     [rsp+100h+var_D0], rcx
0x18004a9b9  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004a9c0  lea     rcx, aRefpackage; "RefPackage"
0x18004a9c7  mov     [rsp+100h+var_D8], rcx
0x18004a9cc  xor     ecx, ecx
0x18004a9ce  mov     dword ptr [rsp+100h+var_E0], 971h
0x18004a9d6  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004a9db  mov     rdi, [rbp+57h+var_B0]
0x18004a9df  jmp     loc_18004ADD9
0x18004a9e4  mov     rdi, [rbp+57h+var_B0]
0x18004a9e8  cmp     [rdi+100h], r12
0x18004a9ef  jz      loc_18004ADD5
0x18004a9f5  lea     rax, [rsi+10h]
0x18004a9f9  xor     edx, edx; bool
0x18004a9fb  mov     qword ptr [rbp+57h+var_80+8], rax
0x18004a9ff  mov     eax, [rsi+0Ch]
0x18004aa02  mov     dword ptr [rbp+57h+var_80], eax
0x18004aa05  mov     rbx, [r14+38h]
0x18004aa09  mov     rcx, rbx; struct _USER_CACHE_ENTRY *
0x18004aa0c  call    ?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z; LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)
0x18004aa11  lea     r8, [rbp+57h+var_60]; struct _tagCacheNodeIdentifier *
0x18004aa15  mov     rcx, rbx; struct _USER_CACHE_ENTRY *
0x18004aa18  lea     rdx, [rbp+57h+var_90]; struct _AP_BLOB *
0x18004aa1c  call    ?DuplicateCredentialData@@YAJPEAU_USER_CACHE_ENTRY@@PEAU_AP_BLOB@@PEAU_tagCacheNodeIdentifier@@@Z; DuplicateCredentialData(_USER_CACHE_ENTRY *,_AP_BLOB *,_tagCacheNodeIdentifier *)
0x18004aa21  mov     [rbp+57h+arg_0], eax
0x18004aa24  mov     r8d, eax
0x18004aa27  test    eax, eax
0x18004aa29  jz      short loc_18004AA6D
0x18004aa2b  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004aa32  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004aa37  lea     rcx, Class
0x18004aa3e  mov     [rsp+100h+var_D0], rcx
0x18004aa43  lea     rcx, aDuplicatecrede; "DuplicateCredentialData"
0x18004aa4a  mov     [rsp+100h+var_D8], rcx
0x18004aa4f  mov     dword ptr [rsp+100h+var_E0], 981h
0x18004aa57  mov     r9, rax
0x18004aa5a  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004aa61  xor     ecx, ecx
0x18004aa63  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004aa68  jmp     loc_18004ADCB
0x18004aa6d  mov     rcx, rbx; struct _USER_CACHE_ENTRY *
0x18004aa70  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x18004aa75  mov     rcx, [rdi+8]
0x18004aa79  lea     rax, [rbp+57h+var_98]
0x18004aa7d  mov     [rsp+100h+var_D8], rax
0x18004aa82  lea     r9, [rbp+57h+Buf1]
0x18004aa86  lea     rax, [rbp+57h+Size]
0x18004aa8a  mov     [rsp+100h+var_E0], rax
0x18004aa8f  lea     r8, [rbp+57h+var_80]
0x18004aa93  mov     rax, [rdi+100h]
0x18004aa9a  lea     rdx, [rbp+57h+var_90]
0x18004aa9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aaa3  mov     [rbp+57h+arg_0], eax
0x18004aaa6  mov     r8d, eax
0x18004aaa9  test    eax, eax
0x18004aaab  jns     short loc_18004AAE2
0x18004aaad  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004aab4  mov     [rbp+57h+Buf1], r12
0x18004aab8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004aabd  lea     rcx, Class
0x18004aac4  mov     [rsp+100h+var_D0], rcx
0x18004aac9  lea     rcx, aRefreshtoken; "RefreshToken"
0x18004aad0  mov     [rsp+100h+var_D8], rcx
0x18004aad5  mov     dword ptr [rsp+100h+var_E0], 990h
0x18004aadd  jmp     loc_18004A90B
0x18004aae2  cmp     [rbp+57h+Buf1], r12
0x18004aae6  jz      loc_18004ADD5
0x18004aaec  cmp     dword ptr [rbp+57h+Size], r12d
0x18004aaf0  jz      loc_18004ADD5
0x18004aaf6  mov     rbx, [r14+38h]
0x18004aafa  mov     dl, 1; bool
0x18004aafc  mov     rcx, rbx; struct _USER_CACHE_ENTRY *
0x18004aaff  call    ?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z; LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)
0x18004ab04  mov     rax, [rbx+168h]
0x18004ab0b  mov     ecx, [rax]
0x18004ab0d  nop
0x18004ab0e  test    ecx, ecx
0x18004ab10  jz      short loc_18004AB61
0x18004ab12  mov     r8d, 0C0000240h
0x18004ab18  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004ab1f  mov     [rbp+57h+arg_0], r8d
0x18004ab23  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004ab28  lea     rcx, Class
0x18004ab2f  mov     r9, rax
0x18004ab32  mov     [rsp+100h+var_D0], rcx
0x18004ab37  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004ab3e  lea     rcx, aFuncAbortingOp; "%!FUNC!: Aborting operation because a o"...
0x18004ab45  mov     [rsp+100h+var_D8], rcx
0x18004ab4a  mov     ecx, 1
0x18004ab4f  mov     dword ptr [rsp+100h+var_E0], 9A9h
0x18004ab57  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004ab5c  jmp     loc_18004ADCB
0x18004ab61  mov     eax, dword ptr [rbp+57h+Size]
0x18004ab64  cmp     eax, [rbx+118h]
0x18004ab6a  jnz     short loc_18004AB87
0x18004ab6c  mov     rdx, [rbx+120h]; Buf2
0x18004ab73  mov     r8d, eax; Size
0x18004ab76  mov     rcx, [rbp+57h+Buf1]; Buf1
0x18004ab7a  call    memcmp_0
0x18004ab7f  test    eax, eax
0x18004ab81  jz      loc_18004ADC7
0x18004ab87  lea     r8, [rbp+57h+var_60]; struct _tagCacheNodeIdentifier *
0x18004ab8b  mov     rcx, rbx; struct _USER_CACHE_ENTRY *
0x18004ab8e  lea     rdx, [rbp+57h+var_90]; struct _AP_BLOB *
0x18004ab92  call    ?IsCredentialDataSame@@YAHPEAU_USER_CACHE_ENTRY@@PEAU_AP_BLOB@@PEAU_tagCacheNodeIdentifier@@@Z; IsCredentialDataSame(_USER_CACHE_ENTRY *,_AP_BLOB *,_tagCacheNodeIdentifier *)
0x18004ab97  test    eax, eax
0x18004ab99  jnz     short loc_18004ABA7
0x18004ab9b  mov     [rbp+57h+arg_0], 0C0000104h
0x18004aba2  jmp     loc_18004ADCB
0x18004aba7  mov     rcx, [rdi+158h]; unsigned __int16 *
0x18004abae  lea     rdx, [rbx+68h]; unsigned __int16 *
0x18004abb2  lea     r9, [rbp+57h+var_A8]; struct _CloudAPCache **
0x18004abb6  lea     r8, aCachedata; "CacheData"
0x18004abbd  call    ?_GetLogonCacheForUser@@YAJPEBG00PEAPEAU_CloudAPCache@@@Z; _GetLogonCacheForUser(ushort const *,ushort const *,ushort const *,_CloudAPCache * *)
0x18004abc2  mov     [rbp+57h+arg_0], eax
0x18004abc5  mov     r8d, eax
0x18004abc8  test    eax, eax
0x18004abca  jz      short loc_18004AC12
0x18004abcc  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004abd3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004abd8  lea     rcx, Class
0x18004abdf  mov     r9, rax
0x18004abe2  mov     [rsp+100h+var_D0], rcx
0x18004abe7  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004abee  lea     rcx, aGetlogoncachef; "GetLogonCacheForUser"
0x18004abf5  mov     [rsp+100h+var_D8], rcx
0x18004abfa  xor     ecx, ecx
0x18004abfc  mov     dword ptr [rsp+100h+var_E0], 9C6h
0x18004ac04  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004ac09  mov     r15, [rbp+57h+var_A8]
0x18004ac0d  jmp     loc_18004ADCB
0x18004ac12  mov     r8, [rbp+57h+Buf1]; unsigned __int8 *
0x18004ac16  lea     rax, [rbp+57h+var_A0]
0x18004ac1a  mov     r9d, dword ptr [rbp+57h+Size]; unsigned int
0x18004ac1e  mov     rcx, rdi; struct _ApPluginPkg *
0x18004ac21  mov     r15, [rbp+57h+var_A8]
0x18004ac25  mov     [rsp+100h+var_C8], r12; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x18004ac2a  mov     [rsp+100h+var_D0], r12; int *
0x18004ac2f  mov     [rsp+100h+var_D8], r12; int *
0x18004ac34  lea     rdx, [r15+4]; struct _GUID *
0x18004ac38  mov     [rbp+57h+var_68], r8
0x18004ac3c  mov     [rbp+57h+var_70], r9d
0x18004ac40  mov     [rsp+100h+var_E0], rax; struct _APPLUGIN_USER_INFO **
0x18004ac45  call    ?ValidateUserInfo@@YAJPEAU_ApPluginPkg@@PEAU_GUID@@PEAEKPEAPEAU_APPLUGIN_USER_INFO@@PEAH4PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z; ValidateUserInfo(_ApPluginPkg *,_GUID *,uchar *,ulong,_APPLUGIN_USER_INFO * *,int *,int *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x18004ac4a  mov     [rbp+57h+arg_0], eax
0x18004ac4d  mov     r8d, eax
0x18004ac50  test    eax, eax
0x18004ac52  jz      short loc_18004AC85
0x18004ac54  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004ac5b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004ac60  lea     rcx, Class
0x18004ac67  mov     [rsp+100h+var_D0], rcx
0x18004ac6c  lea     rcx, aValidateuserin; "ValidateUserInfo"
0x18004ac73  mov     [rsp+100h+var_D8], rcx
0x18004ac78  mov     dword ptr [rsp+100h+var_E0], 9D4h
0x18004ac80  jmp     loc_18004AA57
0x18004ac85  mov     rax, [rdi+8]
0x18004ac89  lea     rdx, [rbx+128h]; struct _tagCacheNodeIdentifier *
0x18004ac90  mov     qword ptr [rbp+57h+var_50], rax
0x18004ac94  lea     r9, [rbp+57h+var_70]; struct _AP_BLOB *
0x18004ac98  mov     rax, [rdi+0E8h]
0x18004ac9f  mov     rcx, r15; struct _CloudAPCache *
0x18004aca2  mov     qword ptr [rbp+57h+var_50+8], rax
0x18004aca6  mov     rax, [rdi+0F0h]
0x18004acad  mov     qword ptr [rbp+57h+var_40], rax
0x18004acb1  lea     rax, ?SecureFreeCacheData@@YAXPEAU_AP_BLOB@@@Z; SecureFreeCacheData(_AP_BLOB *)
0x18004acb8  mov     qword ptr [rbp+57h+var_40+8], rax
0x18004acbc  lea     rax, [rbp+57h+var_50]
0x18004acc0  mov     r8, [rbx+108h]; struct _CREDENTIAL_KEY *
0x18004acc7  mov     [rsp+100h+var_E0], rax; struct _tagCacheDataFuncs *
0x18004accc  call    ?UpdatePluginOpaqueCacheBlob@@YAJPEAU_CloudAPCache@@PEAU_tagCacheNodeIdentifier@@PEAU_CREDENTIAL_KEY@@PEAU_AP_BLOB@@PEAU_tagCacheDataFuncs@@@Z; UpdatePluginOpaqueCacheBlob(_CloudAPCache *,_tagCacheNodeIdentifier *,_CREDENTIAL_KEY *,_AP_BLOB *,_tagCacheDataFuncs *)
0x18004acd1  mov     [rbp+57h+arg_0], eax
0x18004acd4  mov     r8d, eax
0x18004acd7  test    eax, eax
0x18004acd9  jz      short loc_18004AD0C
0x18004acdb  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004ace2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004ace7  lea     rcx, Class
0x18004acee  mov     [rsp+100h+var_D0], rcx
0x18004acf3  lea     rcx, aUpdatepluginop; "UpdatePluginOpaqueCacheBlob"
0x18004acfa  mov     [rsp+100h+var_D8], rcx
0x18004acff  mov     dword ptr [rsp+100h+var_E0], 9E1h
0x18004ad07  jmp     loc_18004AA57
0x18004ad0c  mov     rax, [rbp+57h+var_A0]
0x18004ad10  mov     r8b, 1; bool
0x18004ad13  mov     [rsp+100h+var_C0], r12d; unsigned int
0x18004ad18  mov     r9, r15; struct _CloudAPCache *
0x18004ad1b  mov     [rsp+100h+var_C8], r12; unsigned __int8 *
0x18004ad20  mov     dl, r8b; bool
0x18004ad23  mov     [rsp+100h+var_D0], r12; struct _SEC_WINNT_AUTH_FIDO_DATA *
0x18004ad28  mov     rcx, rdi; struct _ApPluginPkg *
0x18004ad2b  mov     [rsp+100h+var_D8], rax; struct _APPLUGIN_USER_INFO *
0x18004ad30  mov     [rsp+100h+var_E0], rbx; struct _USER_CACHE_ENTRY *
0x18004ad35  call    ?SaveCaches@@YAJPEAU_ApPluginPkg@@_N1PEAU_CloudAPCache@@PEAU_USER_CACHE_ENTRY@@PEAU_APPLUGIN_USER_INFO@@PEAU_SEC_WINNT_AUTH_FIDO_DATA@@PEAEK@Z; SaveCaches(_ApPluginPkg *,bool,bool,_CloudAPCache *,_USER_CACHE_ENTRY *,_APPLUGIN_USER_INFO *,_SEC_WINNT_AUTH_FIDO_DATA *,uchar *,ulong)
0x18004ad3a  mov     [rbp+57h+arg_0], eax
0x18004ad3d  mov     r8d, eax
0x18004ad40  test    eax, eax
0x18004ad42  jz      short loc_18004AD75
0x18004ad44  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004ad4b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004ad50  lea     rcx, Class
0x18004ad57  mov     [rsp+100h+var_D0], rcx
0x18004ad5c  lea     rcx, aSavecaches; "SaveCaches"
0x18004ad63  mov     [rsp+100h+var_D8], rcx
0x18004ad68  mov     dword ptr [rsp+100h+var_E0], 9EDh
0x18004ad70  jmp     loc_18004AA57
0x18004ad75  mov     rax, [rbx+120h]
0x18004ad7c  test    rax, rax
0x18004ad7f  jz      short loc_18004ADAF
0x18004ad81  mov     ecx, [rbx+118h]
0x18004ad87  test    rcx, rcx
0x18004ad8a  jz      short loc_18004AD98
0x18004ad8c  mov     [rax], r12b
0x18004ad8f  inc     rax
0x18004ad92  sub     rcx, 1
0x18004ad96  jnz     short loc_18004AD8C
0x18004ad98  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004ad9f  mov     rcx, [rbx+120h]
0x18004ada6  mov     rax, [rax+30h]
0x18004adaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004adaf  mov     rax, [rbp+57h+Buf1]
0x18004adb3  mov     [rbx+120h], rax
  ... truncated ...
```
