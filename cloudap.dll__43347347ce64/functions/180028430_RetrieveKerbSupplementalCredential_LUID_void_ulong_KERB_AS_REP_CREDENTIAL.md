# RetrieveKerbSupplementalCredential(_LUID,void *,ulong,_KERB_AS_REP_CREDENTIAL * *)

- ea: `0x180028430`
- end: `0x180028d1f`
- name: `?RetrieveKerbSupplementalCredential@@YAJU_LUID@@PEAXKPEAPEAU_KERB_AS_REP_CREDENTIAL@@@Z`
- size: `2287`
- prototype: `int(struct _LUID, void *, unsigned int, struct _KERB_AS_REP_CREDENTIAL **)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting`

## callees

- `0x180007ef0`
- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000ce50`
- `0x18000e900`
- `0x180010320`
- `0x1800103c0`
- `0x180028430`
- `0x18002ce50`
- `0x180042410`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180028538`
- `ntdll!RtlReleaseResource` at `0x180028bdb`
- `ntdll!RtlReleaseResource` at `0x180028538`
- `ntdll!RtlReleaseResource` at `0x180028bdb`
- `ntdll!RtlEqualUnicodeString` at `0x180028ad5`
- `ntdll!RtlEqualUnicodeString` at `0x180028ad5`
- `ntdll!RtlAcquireResourceShared` at `0x1800284d4`
- `ntdll!RtlAcquireResourceShared` at `0x180028665`
- `ntdll!RtlAcquireResourceShared` at `0x1800284d4`
- `ntdll!RtlAcquireResourceShared` at `0x180028665`
- `ntdll!RtlEnterCriticalSection` at `0x18002866f`
- `ntdll!RtlEnterCriticalSection` at `0x18002866f`
- `ntdll!RtlLeaveCriticalSection` at `0x18002868a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002868a`

## string_xrefs

- `0x18002854a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800285bc`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180028607`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800286a7`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18002871f`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800289ca`: `RefreshToken`
- `0x18002876b`: `Plugin doesn't support cached logon`
- `0x180028a5a`: `Plugin doesnt support refresh token`

## pseudocode

```c
__int64 __fastcall RetrieveKerbSupplementalCredential(
        struct _LUID a1,
        char *a2,
        __int64 a3,
        struct _KERB_AS_REP_CREDENTIAL **a4)
{
  struct _APPLUGIN_USER_INFO *v4; // r15
  char *v5; // rbx
  unsigned int v6; // edx
  struct _ApPluginPkg *v7; // r13
  unsigned int v8; // esi
  const char *v9; // rbx
  char v10; // al
  const char *v11; // rcx
  bool v12; // zf
  const char *v13; // r9
  struct _LOGON_SESSION *v14; // r12
  const char *v15; // rax
  const char *v16; // rax
  __int64 (__fastcall *v17)(_QWORD, _QWORD, __int128 *, struct _ApPluginPkg **, __int64 *, _QWORD, unsigned int **); // rax
  const char *v18; // rbx
  const char *v19; // rax
  char v20; // cl
  const char *v21; // rdx
  int v22; // r14d
  __int64 v23; // r10
  int v24; // esi
  int v25; // ecx
  const char *v26; // rdx
  const char *v27; // r11
  char v28; // r8
  const char *v29; // r9
  unsigned int *v30; // r8
  unsigned int v31; // r9d
  __int64 v32; // rax
  __int64 v33; // rdx
  _BYTE *v34; // rcx
  unsigned int *v35; // r8
  unsigned int v36; // r9d
  __int64 v37; // rax
  __int64 v38; // rdx
  _BYTE *v39; // rcx
  __int64 (__fastcall *v40)(_QWORD, struct _LOGON_SESSION **, _QWORD, char *, __int128 *, unsigned int **); // rax
  char v41; // al
  const char *v42; // rcx
  bool v43; // zf
  unsigned int *v44; // rcx
  char v45; // al
  char v46; // al
  char v47; // al
  int v48; // esi
  unsigned int *v49; // r14
  struct _KERB_AS_REP_CREDENTIAL **v50; // rax
  const void *v51; // r15
  struct _KERB_AS_REP_CREDENTIAL *v52; // rax
  struct _KERB_AS_REP_CREDENTIAL *v53; // rsi
  char v54; // al
  char v55; // al
  _BYTE *v56; // rcx
  __int64 v57; // rax
  struct _LOGON_SESSION *v58; // rcx
  __int64 v59; // rax
  unsigned int *v60; // r9
  unsigned int v61; // r8d
  __int64 v62; // rax
  __int64 v63; // rdx
  _BYTE *v64; // rcx
  __int64 v66; // [rsp+28h] [rbp-E0h]
  const char *v67; // [rsp+30h] [rbp-D8h]
  unsigned int *v68; // [rsp+48h] [rbp-C0h] BYREF
  struct _ApPluginPkg *v69; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int *v70; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v71; // [rsp+60h] [rbp-A8h] BYREF
  struct _KERB_AS_REP_CREDENTIAL **v72; // [rsp+68h] [rbp-A0h]
  struct _ApPluginPkg *v73; // [rsp+70h] [rbp-98h]
  struct _LOGON_SESSION *v74; // [rsp+78h] [rbp-90h] BYREF
  struct _LOGON_SESSION *v75[2]; // [rsp+80h] [rbp-88h] BYREF
  __int128 v76; // [rsp+90h] [rbp-78h] BYREF
  UNICODE_STRING String2; // [rsp+A0h] [rbp-68h] BYREF
  struct _LUID v78; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v79; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v80; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v81; // [rsp+D8h] [rbp-30h] BYREF
  wchar_t v82; // [rsp+E8h] [rbp-20h]

  v4 = 0;
  v5 = a2;
  v82 = aKerberos[8];
  v72 = a4;
  v78 = a1;
  v74 = 0;
  v69 = 0;
  v68 = 0;
  v73 = 0;
  *(_QWORD *)&String2.Length = 1179664;
  String2.Buffer = (PWSTR)&v81;
  v76 = 0;
  v80 = 0;
  *a4 = 0;
  *(_OWORD *)v75 = 0;
  v81 = *(_OWORD *)L"Kerberos";
  if ( !a2 )
  {
    v8 = _AcquireLogonSession(1, &v78, &v74);
    if ( v8 )
    {
      v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v8, v13, 5292, "AcquireLogonSession", &Class);
      goto LABEL_106;
    }
    v14 = v74;
    v8 = RefPackage((struct _GUID *)((char *)v74 + 36), &v69);
    if ( v8 )
    {
      v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v8, v15, 5297, "RefPackage", &Class);
      v7 = v69;
LABEL_103:
      if ( v7 )
        RtlReleaseResource(&g_PackageListLock);
      v4 = v73;
      goto LABEL_106;
    }
    v5 = (char *)*((_QWORD *)v14 + 7);
    v7 = v69;
LABEL_19:
    RtlAcquireResourceShared((PRTL_RESOURCE)(*((_QWORD *)v5 + 3) + 24LL), 1u);
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v5 + 32));
    if ( !*((_DWORD *)v5 + 19) )
      _UnprotectUserCacheEntry((struct _USER_CACHE_ENTRY *)v5);
    ++*((_DWORD *)v5 + 19);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v5 + 32));
    v8 = DuplicateCredentialData(
           (struct _USER_CACHE_ENTRY *)v5,
           (struct _AP_BLOB *)v75,
           (struct _tagCacheNodeIdentifier *)&v80);
    if ( v8 )
    {
      v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v8, v16, 5309, "DuplicateCredentialData", &Class);
      UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v5);
      goto LABEL_103;
    }
    UnlockAndProtectUserCacheEntry((struct _USER_CACHE_ENTRY *)v5);
    v17 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int128 *, struct _ApPluginPkg **, __int64 *, _QWORD, unsigned int **))*((_QWORD *)v7 + 23);
    v18 = "";
    LODWORD(v71) = 0;
    v70 = 0;
    v69 = 0;
    v79 = 0;
    if ( v17 )
    {
      LODWORD(v79) = v75[0];
      *((struct _LOGON_SESSION **)&v79 + 1) = v75[1];
      v24 = v17(*((_QWORD *)v7 + 1), 0, &v79, &v69, &v71, 0, &v70);
      if ( v24 < 0 )
      {
        v22 = 0;
        v69 = 0;
        v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        v26 = "ValidateUserInfo";
        v25 = 2024;
LABEL_41:
        LODWORD(v66) = v25;
        WPPTraceLogA(v23, v27, (unsigned int)v24, v19, v66, v26, &Class);
        v30 = v70;
        if ( !v70 )
          goto LABEL_49;
        v31 = 0;
        if ( *v70 )
        {
          do
          {
            v32 = 8LL * v31;
            v33 = v30[v32 + 6];
            v34 = *(_BYTE **)&v30[v32 + 8];
            if ( v30[v32 + 6] )
            {
              do
              {
                *v34++ = 0;
                --v33;
              }
              while ( v33 );
              v30 = v70;
            }
            ++v31;
          }
          while ( v31 < *v30 );
        }
        ((void (__fastcall *)(unsigned int *))g_pLsaFunctionTable->FreeLsaHeap)(v30);
LABEL_48:
        v70 = 0;
LABEL_49:
        FreeUserInfo(v69);
        if ( v22 )
        {
          v35 = v68;
          if ( v68 )
          {
            v36 = 0;
            if ( *v68 )
            {
              do
              {
                v37 = 8LL * v36;
                v38 = v35[v37 + 6];
                v39 = *(_BYTE **)&v35[v37 + 8];
                if ( v35[v37 + 6] )
                {
                  do
                  {
                    *v39++ = 0;
                    --v38;
                  }
                  while ( v38 );
                  v35 = v68;
                }
                ++v36;
              }
              while ( v36 < *v35 );
            }
            ((void (__fastcall *)(unsigned int *))g_pLsaFunctionTable->FreeLsaHeap)(v35);
            v68 = 0;
          }
          v40 = (__int64 (__fastcall *)(_QWORD, struct _LOGON_SESSION **, _QWORD, char *, __int128 *, unsigned int **))*((_QWORD *)v7 + 32);
          if ( !v40 )
          {
            v8 = -1073741637;
            while ( 1 )
            {
              v46 = *(v18 - 1);
              v42 = v18--;
              v43 = v46 == 92;
              if ( v46 == 92 )
                break;
              if ( v18 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
              {
                v43 = v46 == 92;
                break;
              }
            }
            v67 = "Plugin doesnt support refresh token";
            LODWORD(v66) = 5365;
            goto LABEL_100;
          }
          v8 = v40(*((_QWORD *)v7 + 1), v75, 0, (char *)&v76 + 8, &v76, &v68);
          if ( (v8 & 0x80000000) != 0 )
          {
            *((_QWORD *)&v76 + 1) = 0;
            while ( 1 )
            {
              v41 = *(v18 - 1);
              v42 = v18--;
              v43 = v41 == 92;
              if ( v41 == 92 )
                break;
              if ( v18 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
              {
                v43 = v41 == 92;
                break;
              }
            }
            v67 = "RefreshToken";
            LODWORD(v66) = 5353;
            goto LABEL_100;
          }
          v44 = v68;
          if ( !v68 )
          {
            v8 = -1073741637;
            while ( 1 )
            {
              v45 = *(v18 - 1);
              v42 = v18--;
              v43 = v45 == 92;
              if ( v45 == 92 )
                break;
              if ( v18 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
              {
                v43 = v45 == 92;
                break;
              }
            }
            v67 = "NoKerberosCredReturned";
            LODWORD(v66) = 5359;
            goto LABEL_100;
          }
        }
        else
        {
          v44 = v68;
          if ( !v68 )
          {
            v8 = -1073741637;
            while ( 1 )
            {
              v47 = *(v18 - 1);
              v42 = v18--;
              v43 = v47 == 92;
              if ( v47 == 92 )
                break;
              if ( v18 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
              {
                v43 = v47 == 92;
                break;
              }
            }
            v67 = "NoKerberosCredReturned";
            LODWORD(v66) = 5371;
            goto LABEL_100;
          }
        }
        v48 = 0;
        if ( *v44 )
        {
          while ( 1 )
          {
            v49 = &v44[8 * v48];
            if ( RtlEqualUnicodeString((PCUNICODE_STRING)(v49 + 2), &String2, 1u) )
            {
              if ( v49[6] >= 0x44 )
                break;
            }
            v44 = v68;
            if ( ++v48 >= *v68 )
              goto LABEL_85;
          }
          v51 = (const void *)*((_QWORD *)v49 + 4);
          v52 = (struct _KERB_AS_REP_CREDENTIAL *)((__int64 (*)(void))g_pLsaFunctionTable->AllocateLsaHeap)();
          v53 = v52;
          if ( !v52 )
          {
            v8 = -1073741801;
            while ( 1 )
            {
              v54 = *(v18 - 1);
              v42 = v18--;
              v43 = v54 == 92;
              if ( v54 == 92 )
                break;
              if ( v18 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
              {
                v43 = v54 == 92;
                break;
              }
            }
            v67 = "AllocateLsaHeap";
            LODWORD(v66) = 5387;
            goto LABEL_100;
          }
          memcpy_0(v52, v51, v49[6]);
          v50 = v72;
          *v72 = v53;
        }
        else
        {
LABEL_85:
          v50 = v72;
        }
        if ( *v50 )
        {
          v8 = 0;
          goto LABEL_103;
        }
        v8 = -1073741637;
        while ( 1 )
        {
          v55 = *(v18 - 1);
          v42 = v18--;
          v43 = v55 == 92;
          if ( v55 == 92 )
            break;
          if ( v18 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
          {
            v43 = v55 == 92;
            break;
          }
        }
        v67 = "NoKerberosCredFound";
        LODWORD(v66) = 5404;
LABEL_100:
        if ( v43 )
          v18 = v42;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v8, v18, v66, v67, &Class);
        goto LABEL_103;
      }
      if ( v69 && *((_QWORD *)v69 + 2) )
      {
        v22 = v71;
        v68 = v70;
        v73 = v69;
        v69 = 0;
        goto LABEL_48;
      }
      v19 = "";
      do
      {
        v28 = *(v19 - 1);
        v29 = v19--;
      }
      while ( v28 != 92 && v19 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
      v22 = 0;
      v26 = "UserInfo is invalid";
      v23 = 0;
      v24 = -1073741715;
      v25 = 2031;
      if ( v28 == 92 )
        v19 = v29;
    }
    else
    {
      v19 = "";
      do
      {
        v20 = *(v19 - 1);
        v21 = v19--;
      }
      while ( v20 != 92 && v19 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
      v22 = 0;
      v23 = 0;
      v12 = v20 == 92;
      v24 = -2146893039;
      v25 = 2007;
      if ( v12 )
        v19 = v21;
      v26 = "Plugin doesn't support cached logon";
    }
    v27 = "0x%08x %s:%u : %s:%ws";
    goto LABEL_41;
  }
  RtlAcquireResourceShared(&g_PackageListLock, 1u);
  if ( g_pPlugins )
  {
    v6 = 0;
    if ( g_cPlugins )
    {
      do
      {
        v7 = (struct _ApPluginPkg *)((char *)g_pPlugins + 392 * v6);
        if ( *((_QWORD *)v5 + 31) == *(_QWORD *)((char *)v7 + 68)
          && *((_QWORD *)v5 + 32) == *(_QWORD *)((char *)v7 + 76) )
        {
          goto LABEL_19;
        }
      }
      while ( ++v6 < g_cPlugins );
    }
  }
  RtlReleaseResource(&g_PackageListLock);
  v8 = -2146893039;
  v9 = "";
  while ( 1 )
  {
    v10 = *(v9 - 1);
    v11 = v9--;
    v12 = v10 == 92;
    if ( v10 == 92 )
      break;
    if ( v9 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
    {
      v12 = v10 == 92;
      break;
    }
  }
  if ( v12 )
    v9 = v11;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 2148074257LL, v9, 5287, "RefPackage", &Class);
LABEL_106:
  ReleaseLogonSession(v74);
  v56 = (_BYTE *)*((_QWORD *)&v76 + 1);
  if ( *((_QWORD *)&v76 + 1) )
  {
    v57 = (unsigned int)v76;
    if ( (_DWORD)v76 )
    {
      do
      {
        *v56++ = 0;
        --v57;
      }
      while ( v57 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  v58 = v75[1];
  if ( v75[1] )
  {
    v59 = LODWORD(v75[0]);
    if ( LODWORD(v75[0]) )
    {
      do
      {
        *(_BYTE *)v58 = 0;
        v58 = (struct _LOGON_SESSION *)((char *)v58 + 1);
        --v59;
      }
      while ( v59 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  FreeUserInfo(0);
  if ( *((_QWORD *)&v80 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v60 = v68;
  if ( v68 )
  {
    v61 = 0;
    if ( *v68 )
    {
      do
      {
        v62 = 8LL * v61;
        v63 = v60[v62 + 6];
        v64 = *(_BYTE **)&v60[v62 + 8];
        if ( v60[v62 + 6] )
        {
          do
          {
            *v64++ = 0;
            --v63;
          }
          while ( v63 );
          v60 = v68;
        }
        ++v61;
      }
      while ( v61 < *v60 );
    }
    ((void (__fastcall *)(unsigned int *))g_pLsaFunctionTable->FreeLsaHeap)(v60);
  }
  FreeUserInfo(v4);
  return v8;
}

```

## disassembly

```asm
0x180028430  mov     r11, rsp
0x180028433  push    rbp
0x180028434  push    rsi
0x180028435  push    r15
0x180028437  lea     rbp, [r11-28h]
0x18002843b  sub     rsp, 110h
0x180028442  mov     rax, cs:__security_cookie
0x180028449  xor     rax, rsp
0x18002844c  mov     [rbp+20h+var_38], rax
0x180028450  movzx   eax, word ptr cs:aKerberos+10h; ""
0x180028457  xorps   xmm0, xmm0
0x18002845a  mov     [r11+18h], rbx
0x18002845e  xor     r15d, r15d
0x180028461  mov     [r11-20h], rdi
0x180028465  xorps   xmm1, xmm1
0x180028468  mov     [r11-28h], r12
0x18002846c  mov     rbx, rdx
0x18002846f  xor     r12d, r12d
0x180028472  mov     [rbp+20h+var_40], ax
0x180028476  mov     [r11-30h], r13
0x18002847a  lea     rax, [rbp+20h+var_50]
0x18002847e  mov     [rsp+120h+var_C0], r9
0x180028483  mov     qword ptr [rbp+20h+var_78.LowPart], rcx
0x180028487  mov     [rsp+120h+var_B0], r12
0x18002848c  mov     [rsp+120h+var_D8], r12
0x180028491  mov     [rsp+120h+var_E0], r12
0x180028496  mov     [rsp+120h+var_B8], r15
0x18002849b  mov     qword ptr [rbp+20h+String2.Length], 120010h
0x1800284a3  mov     [rbp+20h+String2.Buffer], rax
0x1800284a7  movups  [rbp+20h+var_98], xmm0
0x1800284ab  movups  [rbp+20h+var_60], xmm0
0x1800284af  movups  xmm0, xmmword ptr cs:aKerberos; "Kerberos"
0x1800284b6  mov     [r9], r12
0x1800284b9  movups  xmmword ptr [rsp+120h+var_B0+8], xmm1
0x1800284be  movups  [rbp+20h+var_50], xmm0
0x1800284c2  test    rdx, rdx
0x1800284c5  jz      loc_1800285A3
0x1800284cb  mov     dl, 1; Wait
0x1800284cd  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x1800284d4  call    cs:__imp_RtlAcquireResourceShared
0x1800284da  mov     r9, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x1800284e1  test    r9, r9
0x1800284e4  jz      short loc_180028531
0x1800284e6  mov     r8d, cs:?g_cPlugins@@3KA; ulong g_cPlugins
0x1800284ed  xor     edx, edx
0x1800284ef  test    r8d, r8d
0x1800284f2  jz      short loc_180028531
0x1800284f4  nop     dword ptr [rax+00h]
0x1800284f8  nop     dword ptr [rax+rax+00000000h]
0x180028500  mov     eax, edx
0x180028502  imul    r13, rax, 188h
0x180028509  mov     rax, [rbx+0F8h]
0x180028510  add     r13, r9
0x180028513  cmp     rax, [r13+44h]
0x180028517  jnz     short loc_18002852A
0x180028519  mov     rax, [rbx+100h]
0x180028520  cmp     rax, [r13+4Ch]
0x180028524  jz      loc_18002865B
0x18002852a  inc     edx
0x18002852c  cmp     edx, r8d
0x18002852f  jb      short loc_180028500
0x180028531  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x180028538  call    cs:__imp_RtlReleaseResource
0x18002853e  mov     esi, 80090311h
0x180028543  lea     rbx, aOnecoreDsExtCl_6+27h; ""
0x18002854a  lea     rdi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180028551  movzx   eax, byte ptr [rbx-1]
0x180028555  mov     rcx, rbx
0x180028558  dec     rbx
0x18002855b  cmp     al, 5Ch ; '\'
0x18002855d  jz      short loc_180028566
0x18002855f  cmp     rbx, rdi
0x180028562  ja      short loc_180028551
0x180028564  cmp     al, 5Ch ; '\'
0x180028566  lea     r12, Class
0x18002856d  cmovz   rbx, rcx
0x180028571  mov     [rsp+30h], r12
0x180028576  lea     rax, aRefpackage; "RefPackage"
0x18002857d  mov     [rsp+120h+var_F8], rax
0x180028582  mov     r9, rbx
0x180028585  mov     dword ptr [rsp+120h+var_100], 14A7h
0x18002858d  mov     r8d, esi
0x180028590  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180028597  xor     ecx, ecx
0x180028599  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002859e  jmp     loc_180028BE6
0x1800285a3  lea     r8, [rsp+120h+var_B0]; struct _LOGON_SESSION **
0x1800285a8  mov     ecx, 1; int
0x1800285ad  lea     rdx, [rbp+20h+var_78]; struct _LUID *
0x1800285b1  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x1800285b6  mov     esi, eax
0x1800285b8  test    eax, eax
0x1800285ba  jz      short loc_1800285ED
0x1800285bc  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800285c3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800285c8  mov     r9, rax
0x1800285cb  lea     r12, Class
0x1800285d2  mov     [rsp+30h], r12
0x1800285d7  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x1800285de  mov     [rsp+120h+var_F8], rax
0x1800285e3  mov     dword ptr [rsp+120h+var_100], 14ACh
0x1800285eb  jmp     short loc_18002858D
0x1800285ed  mov     r12, [rsp+120h+var_B0]
0x1800285f2  lea     rdx, [rsp+120h+var_D8]; struct _ApPluginPkg **
0x1800285f7  lea     rcx, [r12+24h]; struct _GUID *
0x1800285fc  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x180028601  mov     esi, eax
0x180028603  test    eax, eax
0x180028605  jz      short loc_180028651
0x180028607  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18002860e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180028613  mov     r9, rax
0x180028616  lea     r12, Class
0x18002861d  lea     rax, aRefpackage; "RefPackage"
0x180028624  mov     [rsp+30h], r12
0x180028629  mov     [rsp+120h+var_F8], rax
0x18002862e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180028635  mov     r8d, esi
0x180028638  mov     dword ptr [rsp+120h+var_100], 14B1h
0x180028640  xor     ecx, ecx
0x180028642  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180028647  mov     r13, [rsp+120h+var_D8]
0x18002864c  jmp     loc_180028BCF
0x180028651  mov     rbx, [r12+38h]
0x180028656  mov     r13, [rsp+120h+var_D8]
0x18002865b  mov     rcx, [rbx+18h]
0x18002865f  mov     dl, 1; Wait
0x180028661  add     rcx, 18h; Resource
0x180028665  call    cs:__imp_RtlAcquireResourceShared
0x18002866b  lea     rcx, [rbx+20h]; CriticalSection
0x18002866f  call    cs:__imp_RtlEnterCriticalSection
0x180028675  cmp     [rbx+4Ch], r15d
0x180028679  jnz     short loc_180028683
0x18002867b  mov     rcx, rbx; struct _USER_CACHE_ENTRY *
0x18002867e  call    ?_UnprotectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; _UnprotectUserCacheEntry(_USER_CACHE_ENTRY *)
0x180028683  inc     dword ptr [rbx+4Ch]
0x180028686  lea     rcx, [rbx+20h]; CriticalSection
0x18002868a  call    cs:__imp_RtlLeaveCriticalSection
0x180028690  lea     r8, [rbp+20h+var_60]; struct _tagCacheNodeIdentifier *
0x180028694  mov     rcx, rbx; struct _USER_CACHE_ENTRY *
0x180028697  lea     rdx, [rsp+120h+var_B0+8]; struct _AP_BLOB *
0x18002869c  call    ?DuplicateCredentialData@@YAJPEAU_USER_CACHE_ENTRY@@PEAU_AP_BLOB@@PEAU_tagCacheNodeIdentifier@@@Z; DuplicateCredentialData(_USER_CACHE_ENTRY *,_AP_BLOB *,_tagCacheNodeIdentifier *)
0x1800286a1  mov     esi, eax
0x1800286a3  test    eax, eax
0x1800286a5  jz      short loc_1800286F4
0x1800286a7  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800286ae  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800286b3  mov     r9, rax
0x1800286b6  lea     r12, Class
0x1800286bd  lea     rax, aDuplicatecrede; "DuplicateCredentialData"
0x1800286c4  mov     [rsp+30h], r12
0x1800286c9  mov     [rsp+120h+var_F8], rax
0x1800286ce  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800286d5  mov     r8d, esi
0x1800286d8  mov     dword ptr [rsp+120h+var_100], 14BDh
0x1800286e0  xor     ecx, ecx
0x1800286e2  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800286e7  mov     rcx, rbx; struct _USER_CACHE_ENTRY *
0x1800286ea  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x1800286ef  jmp     loc_180028BCF
0x1800286f4  mov     rcx, rbx; struct _USER_CACHE_ENTRY *
0x1800286f7  mov     [rsp+120h+var_30], r14
0x1800286ff  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x180028704  mov     rax, [r13+0B8h]
0x18002870b  lea     rbx, aOnecoreDsExtCl_6+27h; ""
0x180028712  mov     dword ptr [rsp+120h+var_C8], r15d
0x180028717  xorps   xmm0, xmm0
0x18002871a  mov     [rsp+120h+var_D0], r15
0x18002871f  lea     rdi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180028726  mov     [rsp+120h+var_D8], r15
0x18002872b  lea     r12, Class
0x180028732  movups  [rbp+20h+var_70], xmm0
0x180028736  test    rax, rax
0x180028739  jnz     short loc_180028777
0x18002873b  mov     rax, rbx
0x18002873e  xchg    ax, ax
0x180028740  movzx   ecx, byte ptr [rax-1]
0x180028744  mov     rdx, rax
0x180028747  dec     rax
0x18002874a  cmp     cl, 5Ch ; '\'
0x18002874d  jz      short loc_180028754
0x18002874f  cmp     rax, rdi
0x180028752  ja      short loc_180028740
0x180028754  xor     r14d, r14d
0x180028757  xor     r10d, r10d
0x18002875a  cmp     cl, 5Ch ; '\'
0x18002875d  mov     esi, 80090311h
0x180028762  mov     ecx, 7D7h
0x180028767  cmovz   rax, rdx
0x18002876b  lea     rdx, aPluginDoesnTSu; "Plugin doesn't support cached logon"
0x180028772  jmp     loc_180028855
0x180028777  mov     ecx, dword ptr [rsp+120h+var_B0+8]
0x18002877b  lea     r9, [rsp+120h+var_D8]
0x180028780  mov     dword ptr [rbp+20h+var_70], ecx
0x180028783  lea     r8, [rbp+20h+var_70]
0x180028787  mov     rcx, [rbp+20h+var_A0]
0x18002878b  xor     edx, edx
0x18002878d  mov     qword ptr [rbp+20h+var_70+8], rcx
0x180028791  lea     rcx, [rsp+120h+var_D0]
0x180028796  mov     [rsp+30h], rcx
0x18002879b  lea     rcx, [rsp+120h+var_C8]
0x1800287a0  mov     [rsp+120h+var_F8], r15
0x1800287a5  mov     [rsp+120h+var_100], rcx
0x1800287aa  mov     rcx, [r13+8]
0x1800287ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287b3  mov     esi, eax
0x1800287b5  test    eax, eax
0x1800287b7  jns     short loc_1800287E1
0x1800287b9  xor     r14d, r14d
0x1800287bc  mov     [rsp+120h+var_D8], r15
0x1800287c1  xor     r10d, r10d
0x1800287c4  lea     r11, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800287cb  mov     rcx, rdi; char *
0x1800287ce  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800287d3  lea     rdx, aValidateuserin; "ValidateUserInfo"
0x1800287da  mov     ecx, 7E8h
0x1800287df  jmp     short loc_18002885C
0x1800287e1  mov     rcx, [rsp+120h+var_D8]
0x1800287e6  test    rcx, rcx
0x1800287e9  jz      short loc_18002880F
0x1800287eb  cmp     [rcx+10h], r15
0x1800287ef  jz      short loc_18002880F
0x1800287f1  mov     rax, [rsp+120h+var_D0]
0x1800287f6  mov     r14d, dword ptr [rsp+120h+var_C8]
0x1800287fb  mov     [rsp+120h+var_E0], rax
0x180028800  mov     [rsp+120h+var_B8], rcx
0x180028805  mov     [rsp+120h+var_D8], r15
0x18002880a  jmp     loc_1800288DD
0x18002880f  mov     rax, rbx
0x180028812  nop     dword ptr [rax+00h]
0x180028816  nop     word ptr [rax+rax+00000000h]
0x180028820  movzx   r8d, byte ptr [rax-1]
0x180028825  mov     r9, rax
0x180028828  dec     rax
0x18002882b  cmp     r8b, 5Ch ; '\'
0x18002882f  jz      short loc_180028836
0x180028831  cmp     rax, rdi
0x180028834  ja      short loc_180028820
0x180028836  xor     r14d, r14d
0x180028839  lea     rdx, aUserinfoIsInva; "UserInfo is invalid"
0x180028840  xor     r10d, r10d
0x180028843  mov     esi, 0C000006Dh
0x180028848  cmp     r8b, 5Ch ; '\'
0x18002884c  mov     ecx, 7EFh
0x180028851  cmovz   rax, r9
0x180028855  lea     r11, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002885c  mov     r8, r12
0x18002885f  mov     [rsp+30h], r12
0x180028864  mov     r9, rax
0x180028867  mov     [rsp+120h+var_F8], rdx
0x18002886c  mov     r8d, esi
0x18002886f  mov     dword ptr [rsp+120h+var_100], ecx
0x180028873  mov     rdx, r11
0x180028876  mov     rcx, r10
0x180028879  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002887e  mov     r8, [rsp+120h+var_D0]
0x180028883  test    r8, r8
0x180028886  jz      short loc_1800288E2
0x180028888  xor     r9d, r9d
0x18002888b  cmp     [r8], r9d
0x18002888e  jbe     short loc_1800288CA
0x180028890  mov     eax, r9d
0x180028893  shl     rax, 5
0x180028897  mov     edx, [rax+r8+18h]
0x18002889c  mov     rcx, [rax+r8+20h]
0x1800288a1  test    rdx, rdx
0x1800288a4  jz      short loc_1800288C2
0x1800288a6  nop     word ptr [rax+rax+00000000h]
0x1800288b0  mov     [rcx], r15b
0x1800288b3  lea     rcx, [rcx+1]
0x1800288b7  sub     rdx, 1
0x1800288bb  jnz     short loc_1800288B0
0x1800288bd  mov     r8, [rsp+120h+var_D0]
0x1800288c2  inc     r9d
0x1800288c5  cmp     r9d, [r8]
0x1800288c8  jb      short loc_180028890
0x1800288ca  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800288d1  mov     rcx, r8
0x1800288d4  mov     rax, [rax+30h]
0x1800288d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288dd  mov     [rsp+120h+var_D0], r15
0x1800288e2  mov     rcx, [rsp+120h+var_D8]; struct _APPLUGIN_USER_INFO *
0x1800288e7  call    ?FreeUserInfo@@YAXPEAU_APPLUGIN_USER_INFO@@@Z; FreeUserInfo(_APPLUGIN_USER_INFO *)
0x1800288ec  test    r14d, r14d
0x1800288ef  jz      loc_180028A73
0x1800288f5  mov     r8, [rsp+120h+var_E0]
0x1800288fa  test    r8, r8
0x1800288fd  jz      short loc_180028962
0x1800288ff  xor     r9d, r9d
0x180028902  cmp     [r8], r9d
0x180028905  jbe     short loc_18002894A
0x180028907  nop     word ptr [rax+rax+00000000h]
0x180028910  mov     eax, r9d
0x180028913  shl     rax, 5
0x180028917  mov     edx, [rax+r8+18h]
0x18002891c  mov     rcx, [rax+r8+20h]
0x180028921  test    rdx, rdx
0x180028924  jz      short loc_180028942
0x180028926  nop     word ptr [rax+rax+00000000h]
0x180028930  mov     [rcx], r15b
  ... truncated ...
```
