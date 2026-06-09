# SurrogateLogonUser(_SECURITY_LOGON_TYPE,_ApPluginPkg *,_LUID *,ulong,ushort const *,_DECRYPTED_AUTH_DATA * const,_SECPKG_SUPPLEMENTAL_CRED *,ulong)

- ea: `0x1800035b4`
- end: `0x180003e5d`
- name: `?SurrogateLogonUser@@YAJW4_SECURITY_LOGON_TYPE@@PEAU_ApPluginPkg@@PEAU_LUID@@KPEBGQEAU_DECRYPTED_AUTH_DATA@@PEAU_SECPKG_SUPPLEMENTAL_CRED@@K@Z`
- size: `2217`
- prototype: `int(enum _SECURITY_LOGON_TYPE, struct _ApPluginPkg *, struct _LUID *, unsigned int, const unsigned __int16 *, struct _DECRYPTED_AUTH_DATA *const, struct _SECPKG_SUPPLEMENTAL_CRED *, unsigned int)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180020b10`

## callees

- `0x1800035b4`
- `0x180003e70`
- `0x180007ef0`
- `0x180007fc0`
- `0x18000a600`
- `0x18000ce50`
- `0x18000e7e0`
- `0x18000f100`
- `0x18000fd50`
- `0x180010320`
- `0x180015c88`
- `0x180018a20`
- `0x180023700`
- `0x180029650`
- `0x18002c130`
- `0x18002f080`
- `0x180032884`
- `0x180032998`
- `0x180034e20`
- `0x180036cc8`
- `0x180039090`
- `0x1800400ec`
- `0x1800401c0`
- `0x180042410`
- `0x18004d294`
- `0x18004d96c`
- `0x18004dd08`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003985`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003985`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d2a`
- `ntdll!RtlAcquireResourceExclusive` at `0x180003cb8`
- `ntdll!RtlAcquireResourceExclusive` at `0x180003cb8`
- `ntdll!RtlReleaseResource` at `0x180003cd0`
- `ntdll!RtlReleaseResource` at `0x180003cd0`
- `ntdll!RtlEqualUnicodeString` at `0x180003baa`
- `ntdll!RtlEqualUnicodeString` at `0x180003baa`

## string_xrefs

- `0x180003705`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18000377e`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x1800037e4`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18000384d`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x1800038bb`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x180003915`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x1800038d6`: `CreateOrAcquireUserCacheEntry`
- `0x180003c38`: `SaveCaches`
- `0x180003afc`: `CreateLogonSession`
- `0x180003799`: `GetUnlockBufferForDPAPICache`
- `0x180003868`: `Failed to acquire SSO UserCacheEntry`
- `0x180003957`: `UpdateLogonSessionScardEntry`
- `0x180003c5e`: `SurrogateLogonUser success (bCachedLogon)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SurrogateLogonUser(
        enum _SECURITY_LOGON_TYPE a1,
        struct _ApPluginPkg *a2,
        struct _LUID *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        struct _DECRYPTED_AUTH_DATA *const a6,
        struct _SECPKG_SUPPLEMENTAL_CRED *String1,
        unsigned int a8)
{
  __int16 v8; // r15
  char v11; // r14
  struct _USER_CACHE_ENTRY *v12; // rsi
  struct _DECRYPTED_AUTH_DATA *v13; // r9
  unsigned __int16 *v14; // r10
  unsigned int UnlockBufferForDPAPICache; // r12d
  const char *v16; // r9
  const char *v17; // rax
  bool v18; // zf
  int v19; // r14d
  const char *v20; // r9
  const char *v21; // r9
  unsigned int v22; // eax
  const char *v23; // r9
  int v24; // r15d
  struct _USER_CACHE_ENTRY *v25; // rcx
  const char *v26; // r9
  const char *v27; // rax
  __int64 v28; // r8
  DWORD CurrentThreadId; // eax
  __int64 v30; // r8
  unsigned int v31; // r9d
  bool v32; // al
  const char *v33; // r9
  const char *v34; // r9
  const char *v35; // r9
  unsigned __int8 *v36; // r14
  ULONG CredentialSize; // r15d
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v38; // rcx
  PUCHAR Credentials; // rcx
  __int64 v40; // rdx
  const char *v41; // r9
  const char *v42; // rax
  BOOL v43; // ebx
  BOOL v44; // edi
  BOOL v45; // esi
  BOOL v46; // r14d
  BOOL v47; // r15d
  DWORD v48; // eax
  _BYTE *v49; // rcx
  __int64 v50; // rax
  struct _USER_CACHE_ENTRY **v52; // [rsp+20h] [rbp-110h]
  struct _USER_CACHE_ENTRY **v53; // [rsp+20h] [rbp-110h]
  struct _USER_CACHE_ENTRY **v54; // [rsp+20h] [rbp-110h]
  char v55; // [rsp+B0h] [rbp-80h]
  bool v56; // [rsp+B1h] [rbp-7Fh] BYREF
  bool v57; // [rsp+B2h] [rbp-7Eh] BYREF
  bool v58; // [rsp+B3h] [rbp-7Dh] BYREF
  char v59; // [rsp+B4h] [rbp-7Ch]
  char v60; // [rsp+B5h] [rbp-7Bh]
  bool v61; // [rsp+B6h] [rbp-7Ah] BYREF
  bool v62; // [rsp+B7h] [rbp-79h] BYREF
  bool v63; // [rsp+B8h] [rbp-78h] BYREF
  struct _USER_CACHE_ENTRY *v64; // [rsp+C0h] [rbp-70h] BYREF
  enum _SECURITY_LOGON_TYPE v65; // [rsp+C8h] [rbp-68h]
  __int64 v66; // [rsp+D0h] [rbp-60h]
  __int64 v67; // [rsp+D8h] [rbp-58h]
  struct _SCARD_PIN *v68; // [rsp+E0h] [rbp-50h] BYREF
  struct _LOGON_SESSION *v69; // [rsp+E8h] [rbp-48h] BYREF
  unsigned __int16 *Src; // [rsp+F0h] [rbp-40h] BYREF
  unsigned int SourceSid[4]; // [rsp+F8h] [rbp-38h] BYREF
  __int128 v72; // [rsp+108h] [rbp-28h] BYREF
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v73; // [rsp+118h] [rbp-18h]
  unsigned int v74; // [rsp+120h] [rbp-10h]
  struct _APPLUGIN_USER_INFO *v75; // [rsp+128h] [rbp-8h] BYREF
  HLOCAL hMem; // [rsp+130h] [rbp+0h] BYREF
  struct _ApPluginPkg *v77; // [rsp+138h] [rbp+8h]
  struct _LUID *v78; // [rsp+140h] [rbp+10h]
  UNICODE_STRING String2; // [rsp+148h] [rbp+18h] BYREF
  __int128 v80; // [rsp+158h] [rbp+28h] BYREF
  __int64 v81; // [rsp+168h] [rbp+38h]
  unsigned __int16 *v82; // [rsp+170h] [rbp+40h]
  _QWORD v83[42]; // [rsp+180h] [rbp+50h] BYREF
  _QWORD v84[42]; // [rsp+2D0h] [rbp+1A0h] BYREF
  __int128 v85; // [rsp+420h] [rbp+2F0h] BYREF

  v8 = a4;
  v74 = a4;
  v78 = a3;
  v77 = a2;
  v65 = a1;
  v82 = a5;
  v56 = (a4 & 0x40000) != 0;
  v59 = 0;
  v11 = 0;
  v55 = 0;
  v58 = 0;
  v63 = 0;
  v62 = 0;
  v61 = 0;
  v57 = 0;
  v60 = 0;
  v80 = 0;
  v81 = 0;
  *(_OWORD *)SourceSid = 0;
  v64 = 0;
  v12 = 0;
  v75 = 0;
  hMem = 0;
  v69 = 0;
  v72 = 0;
  v73 = 0;
  Src = 0;
  v68 = 0;
  v85 = *(_OWORD *)L"CloudAP";
  *(_QWORD *)&String2.Length = 1048590;
  String2.Buffer = (PWSTR)&v85;
  v66 = 0x41F8E32C8ECE955BLL;
  v67 = 0x363268237C953684LL;
  wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v84,
    "SurrogateLogonUser",
    a3,
    a6);
  v84[0] = &CloudAPProvider::SurrogateLogonUser::`vftable';
  UnlockBufferForDPAPICache = ConvertAuthDataToAuthDataInt(1u, a2, v14, v13, (unsigned __int16 **)&v72, &Src, &v68);
  if ( !UnlockBufferForDPAPICache )
  {
    v19 = v8 & 0x2004;
    if ( (v8 & 0x2004) != 0
      || (UnlockBufferForDPAPICache = GetUnlockBufferForDPAPICache(
                                        a2,
                                        (struct _DECRYPTED_AUTH_DATA *)&v72,
                                        (struct _DPAPI_DECODED_AUTH_DATA *)SourceSid)) == 0 )
    {
      if ( ((unsigned __int8 (__fastcall *)(__int128 *))g_pLsaFunctionTable->GetCallInfo)(&v80) )
      {
        if ( a8 )
          DWORD2(v80) |= a8;
        if ( SourceSid[0] == 1
          && (v22 = AcquireSSOUserCacheEntry((struct _GUID *)((char *)a2 + 68), Src, 1, (struct _LIST_ENTRY **)&v64),
              UnlockBufferForDPAPICache = v22,
              v22 != -1073741724)
          && v22 )
        {
          v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
          LODWORD(v52) = 1312;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            UnlockBufferForDPAPICache,
            v23,
            v52,
            "Failed to acquire SSO UserCacheEntry",
            &Class);
        }
        else
        {
          v24 = 0;
          v25 = v64;
          if ( !v64 )
          {
            LOBYTE(v24) = (WORD4(v80) & 0x1800) != 0;
            UnlockBufferForDPAPICache = _CreateOrAcquireUserCacheEntry(
                                          v24,
                                          (struct _GUID *)((char *)a2 + 68),
                                          Src,
                                          0,
                                          &v64);
            if ( UnlockBufferForDPAPICache )
            {
              v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
              LODWORD(v52) = 1327;
              WPPTraceLogA(
                0,
                "0x%08x %s:%u : %s:%ws",
                UnlockBufferForDPAPICache,
                v26,
                v52,
                "CreateOrAcquireUserCacheEntry",
                &Class);
              goto LABEL_54;
            }
            v25 = v64;
          }
          LockAndUnProtectUserCacheEntry(v25, 1);
          v59 = 1;
          UnlockBufferForDPAPICache = CreateLogonSession(a3, v64, v68, &v69);
          if ( UnlockBufferForDPAPICache == -1073741586 )
          {
            if ( v68 && (unsigned int)UpdateLogonSessionScardEntry(v78, v68) )
            {
              v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
              LODWORD(v52) = 1366;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v28, v27, v52, "UpdateLogonSessionScardEntry", &Class);
            }
            UnlockBufferForDPAPICache = 0;
          }
          else if ( UnlockBufferForDPAPICache )
          {
            v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
            LODWORD(v52) = 1370;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UnlockBufferForDPAPICache, v34, v52, "CreateLogonSession", &Class);
            goto LABEL_54;
          }
          if ( !v19 )
          {
            CurrentThreadId = GetCurrentThreadId();
            wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
              v83,
              "SurrogateLogonUser",
              v30,
              CurrentThreadId);
            v83[0] = &CloudAPProvider::SurrogateLogonUser::`vftable';
            CloudAPProvider::SurrogateLogonUser::StartActivity((CloudAPProvider::SurrogateLogonUser *)v83, v31);
            CloudAPProvider::SurrogateLogonUser::operator=(v84, v83);
            CloudAPProvider::SurrogateLogonUser::~SurrogateLogonUser((CloudAPProvider::SurrogateLogonUser *)v83);
            v60 = 1;
            _InterlockedIncrement((volatile signed __int32 *)v64 + 4);
            v12 = v64;
            *((_DWORD *)v64 + 86) = SourceSid[0];
            v11 = 0;
            if ( v56 || (WORD4(v80) & 0x800) == 0 || (v32 = 1, ((v65 - 10) & 0xFFFFFFFD) == 0) )
              v32 = 0;
            UnlockBufferForDPAPICache = LogonCloudUser(
                                          v65,
                                          v77,
                                          v24,
                                          &v64,
                                          (const unsigned __int16 **)&v72,
                                          (struct _DPAPI_DECODED_AUTH_DATA *)SourceSid,
                                          0,
                                          v68,
                                          v32,
                                          &v56,
                                          (struct _CloudAPCache **)&hMem,
                                          &v58,
                                          &v63,
                                          &v62,
                                          &v61,
                                          &v57,
                                          0,
                                          &v75,
                                          0,
                                          0,
                                          0,
                                          0);
            if ( UnlockBufferForDPAPICache )
            {
              v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
              LODWORD(v53) = 1414;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UnlockBufferForDPAPICache, v33, v53, "LogonCloudUser", &Class);
              goto LABEL_55;
            }
            LockAndUnProtectUserCacheEntry(v12, 1);
            v11 = 1;
            v55 = 1;
            if ( CloudAPCompareStrings(*((PCWSTR *)v12 + 12), *((PCWSTR *)v64 + 12)) )
            {
              UnlockBufferForDPAPICache = TransferLogonSessions(v12, v64);
              if ( UnlockBufferForDPAPICache )
              {
                v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
                LODWORD(v53) = 1424;
                WPPTraceLogA(
                  0,
                  "0x%08x %s:%u : %s:%ws",
                  UnlockBufferForDPAPICache,
                  v35,
                  v53,
                  "TransferLogonSessions",
                  &Class);
                goto LABEL_55;
              }
            }
            v36 = 0;
            CredentialSize = 0;
            v38 = v73;
            if ( SEC_WINNT_AUTH_DATA_TYPE_FIDO == *(_QWORD *)((char *)v73 + 4)
              && *(_QWORD *)((char *)v73 + 12) == 0x5C13C6660F46C583LL
              && String1 )
            {
              if ( RtlEqualUnicodeString(&String1->PackageName, &String2, 1u) )
              {
                Credentials = String1->Credentials;
                if ( Credentials )
                {
                  if ( String1->CredentialSize > 0x10
                    && v66 == *(_QWORD *)Credentials
                    && v67 == *((_QWORD *)Credentials + 1) )
                  {
                    v36 = String1->Credentials;
                    CredentialSize = String1->CredentialSize;
                  }
                }
              }
              v38 = v73;
            }
            v40 = (__int64)v38 + *((unsigned int *)v38 + 5);
            LOBYTE(v40) = v58;
            UnlockBufferForDPAPICache = SaveCaches(
                                          (const unsigned __int16 **)v77,
                                          v40,
                                          !v56,
                                          (struct _CloudAPCache *)hMem,
                                          v64,
                                          v75,
                                          (struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *)((char *)v38
                                                                                      + *((unsigned int *)v38 + 5)),
                                          v36,
                                          CredentialSize);
            if ( UnlockBufferForDPAPICache )
            {
              v41 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
              LODWORD(v54) = 1451;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UnlockBufferForDPAPICache, v41, v54, "SaveCaches", &Class);
            }
            else
            {
              v42 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
              WPPTraceLogA(2, "0x%08x %s:%u : %s:%u", 0, v42, 1453, "SurrogateLogonUser success (bCachedLogon)", v56);
            }
          }
        }
      }
      else
      {
        UnlockBufferForDPAPICache = -1073741595;
        v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
        LODWORD(v52) = 1293;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v21, v52, "GetCallInfo", &Class);
      }
    }
    else
    {
      v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
      LODWORD(v52) = 1287;
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        UnlockBufferForDPAPICache,
        v20,
        v52,
        "GetUnlockBufferForDPAPICache",
        &Class);
    }
LABEL_54:
    v11 = v55;
    goto LABEL_55;
  }
  v16 = "";
  while ( 1 )
  {
    v17 = v16--;
    v18 = *v16 == 92;
    if ( *v16 == 92 )
      break;
    if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp" )
    {
      v18 = *v16 == 92;
      break;
    }
  }
  if ( v18 )
    v16 = v17;
  LODWORD(v52) = 1278;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UnlockBufferForDPAPICache, v16, v52, "ConvertAuthDataToAuthDataInt", &Class);
LABEL_55:
  if ( v57 && v69 && ((int)(UnlockBufferForDPAPICache + 0x80000000) < 0 || UnlockBufferForDPAPICache == -1073741608) )
  {
    RtlAcquireResourceExclusive(&g_LogonSessionListLock, 1u);
    *((_DWORD *)v69 + 6) = 1;
    RtlReleaseResource(&g_LogonSessionListLock);
  }
  ReleaseLogonSession(v69);
  if ( v11 )
    UnlockAndProtectUserCacheEntry(v12);
  _ReleaseUserCacheEntry(0, v12);
  if ( v59 )
    UnlockAndProtectUserCacheEntry(v64);
  _ReleaseUserCacheEntry(0, v64);
  if ( v60 )
  {
    v43 = v57;
    v44 = v61;
    v45 = v62;
    v46 = v63;
    v47 = v56;
    v48 = GetCurrentThreadId();
    CloudAPProvider::SurrogateLogonUser::Stop(
      (CloudAPProvider::SurrogateLogonUser *)v84,
      v78,
      v48,
      v82,
      SourceSid[0],
      v74,
      v47,
      v46,
      v45,
      v44,
      v43,
      UnlockBufferForDPAPICache);
  }
  v49 = *(_BYTE **)&SourceSid[2];
  if ( *(_QWORD *)&SourceSid[2] )
  {
    v50 = SourceSid[1];
    if ( SourceSid[1] )
    {
      do
      {
        *v49++ = 0;
        --v50;
      }
      while ( v50 );
    }
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  }
  FreeUserInfo(v75);
  FreeCloudAPCache(hMem);
  FreePackedCreds(v73);
  if ( (_QWORD)v72 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( *((_QWORD *)&v72 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v72 = 0;
  v73 = 0;
  if ( Src )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v68 )
    FreeScardPin(v68);
  CloudAPProvider::SurrogateLogonUser::~SurrogateLogonUser((CloudAPProvider::SurrogateLogonUser *)v84);
  return UnlockBufferForDPAPICache;
}

```

## disassembly

```asm
0x1800035b4  mov     [rsp-8+arg_18], rbx
0x1800035b9  push    rbp
0x1800035ba  push    rsi
0x1800035bb  push    rdi
0x1800035bc  push    r12
0x1800035be  push    r13
0x1800035c0  push    r14
0x1800035c2  push    r15
0x1800035c4  lea     rbp, [rsp-310h]
0x1800035cc  sub     rsp, 440h
0x1800035d3  mov     rax, cs:__security_cookie
0x1800035da  xor     rax, rsp
0x1800035dd  mov     [rbp+340h+var_40], rax
0x1800035e4  mov     r15d, r9d
0x1800035e7  mov     [rbp+340h+var_350], r9d
0x1800035eb  mov     rdi, r8
0x1800035ee  mov     [rbp+340h+var_330], r8
0x1800035f2  mov     rbx, rdx
0x1800035f5  mov     [rbp+340h+var_338], rdx
0x1800035f9  mov     [rbp+340h+var_3A8], ecx
0x1800035fc  mov     r10, [rbp+340h+arg_20]
0x180003603  mov     [rbp+340h+var_300], r10
0x180003607  mov     r9, [rbp+340h+arg_28]
0x18000360e  mov     r13, [rbp+340h+String1]
0x180003615  mov     eax, r15d
0x180003618  shr     eax, 12h
0x18000361b  and     al, 1
0x18000361d  mov     [rbp+340h+var_3BF], al
0x180003620  xor     ecx, ecx
0x180003622  mov     [rbp+340h+var_3BC], cl
0x180003625  mov     r14b, cl
0x180003628  mov     [rbp+340h+var_3C0], cl
0x18000362b  mov     [rbp+340h+var_3BD], cl
0x18000362e  mov     [rbp+340h+var_3B8], cl
0x180003631  mov     [rbp+340h+var_3B9], cl
0x180003634  mov     [rbp+340h+var_3BA], cl
0x180003637  mov     [rbp+340h+var_3BE], cl
0x18000363a  mov     [rbp+340h+var_3BB], cl
0x18000363d  xorps   xmm0, xmm0
0x180003640  xor     eax, eax
0x180003642  movups  [rbp+340h+var_318], xmm0
0x180003646  mov     [rbp+340h+var_308], rax
0x18000364a  movups  xmmword ptr [rbp+340h+var_378], xmm0
0x18000364e  mov     [rbp+340h+var_3B0], rcx
0x180003652  mov     esi, ecx
0x180003654  mov     [rbp+340h+var_348], rcx
0x180003658  mov     [rbp+340h+hMem], rcx
0x18000365c  mov     [rbp+340h+var_388], rcx
0x180003660  movups  [rbp+340h+var_368], xmm0
0x180003664  mov     [rbp+340h+var_358], rax
0x180003668  mov     [rbp+340h+Src], rcx
0x18000366c  mov     [rbp+340h+var_390], rcx
0x180003670  movups  xmm0, xmmword ptr cs:aCloudap; "CloudAP"
0x180003677  movdqu  [rbp+340h+var_50], xmm0
0x18000367f  mov     qword ptr [rbp+340h+String2.Length], 10000Eh
0x180003687  lea     rax, [rbp+340h+var_50]
0x18000368e  mov     [rbp+340h+String2.Buffer], rax
0x180003692  mov     dword ptr [rbp+340h+var_3A0], 8ECE955Bh
0x180003699  mov     dword ptr [rbp+340h+var_3A0+4], 41F8E32Ch
0x1800036a0  mov     dword ptr [rbp+340h+var_398], 7C953684h
0x1800036a7  mov     dword ptr [rbp+340h+var_398+4], 36326823h
0x1800036ae  lea     rdx, aSurrogatelogon; "SurrogateLogonUser"
0x1800036b5  lea     rcx, [rbp+340h+var_1A0]
0x1800036bc  call    ??0?$ActivityBase@VCloudAPProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800036c1  lea     rax, ??_7SurrogateLogonUser@CloudAPProvider@@6B@; const CloudAPProvider::SurrogateLogonUser::`vftable'
0x1800036c8  mov     [rbp+340h+var_1A0], rax
0x1800036cf  lea     rax, [rbp+340h+var_390]
0x1800036d3  mov     [rsp+470h+var_440], rax; struct _SCARD_PIN **
0x1800036d8  lea     rax, [rbp+340h+Src]
0x1800036dc  mov     [rsp+470h+SourceSid], rax; unsigned __int16 **
0x1800036e1  lea     rax, [rbp+340h+var_368]
0x1800036e5  mov     [rsp+470h+var_450], rax; struct _DECRYPTED_AUTH_DATA *
0x1800036ea  mov     r8, r10; unsigned __int16 *
0x1800036ed  mov     rdx, rbx; struct _ApPluginPkg *
0x1800036f0  mov     cl, 1; bool
0x1800036f2  call    ?ConvertAuthDataToAuthDataInt@@YAJ_NPEAU_ApPluginPkg@@PEBGPEAU_DECRYPTED_AUTH_DATA@@3PEAPEAGPEAPEAU_SCARD_PIN@@@Z; ConvertAuthDataToAuthDataInt(bool,_ApPluginPkg *,ushort const *,_DECRYPTED_AUTH_DATA *,_DECRYPTED_AUTH_DATA *,ushort * *,_SCARD_PIN * *)
0x1800036f7  mov     r12d, eax
0x1800036fa  test    eax, eax
0x1800036fc  jz      short loc_18000375B
0x1800036fe  lea     r9, aOnecoreDsExtCl+2Eh; ""
0x180003705  lea     rbx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18000370c  mov     rax, r9
0x18000370f  dec     r9
0x180003712  cmp     byte ptr [r9], 5Ch ; '\'
0x180003716  jz      short loc_180003721
0x180003718  cmp     r9, rbx
0x18000371b  ja      short loc_18000370C
0x18000371d  cmp     byte ptr [r9], 5Ch ; '\'
0x180003721  cmovz   r9, rax
0x180003725  lea     rdi, Class
0x18000372c  mov     [rsp+470h+var_440], rdi
0x180003731  lea     rax, aConvertauthdat; "ConvertAuthDataToAuthDataInt"
0x180003738  mov     [rsp+470h+SourceSid], rax
0x18000373d  mov     dword ptr [rsp+470h+var_450], 4FEh
0x180003745  mov     r8d, r12d
0x180003748  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000374f  xor     ecx, ecx
0x180003751  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180003756  jmp     loc_180003C8C
0x18000375b  mov     r14d, r15d
0x18000375e  and     r14d, 2004h
0x180003765  jnz     short loc_1800037C3
0x180003767  lea     r8, [rbp+340h+var_378]; struct _DPAPI_DECODED_AUTH_DATA *
0x18000376b  lea     rdx, [rbp+340h+var_368]; struct _DECRYPTED_AUTH_DATA *
0x18000376f  mov     rcx, rbx; struct _ApPluginPkg *
0x180003772  call    ?GetUnlockBufferForDPAPICache@@YAJPEAU_ApPluginPkg@@PEAU_DECRYPTED_AUTH_DATA@@PEAU_DPAPI_DECODED_AUTH_DATA@@@Z; GetUnlockBufferForDPAPICache(_ApPluginPkg *,_DECRYPTED_AUTH_DATA *,_DPAPI_DECODED_AUTH_DATA *)
0x180003777  mov     r12d, eax
0x18000377a  test    eax, eax
0x18000377c  jz      short loc_1800037C3
0x18000377e  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x180003785  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000378a  mov     r9, rax
0x18000378d  lea     rdi, Class
0x180003794  mov     [rsp+470h+var_440], rdi
0x180003799  lea     rax, aGetunlockbuffe; "GetUnlockBufferForDPAPICache"
0x1800037a0  mov     [rsp+470h+SourceSid], rax
0x1800037a5  mov     dword ptr [rsp+470h+var_450], 507h
0x1800037ad  mov     r8d, r12d
0x1800037b0  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800037b7  xor     ecx, ecx
0x1800037b9  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800037be  jmp     loc_180003C88
0x1800037c3  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800037ca  lea     rcx, [rbp+340h+var_318]
0x1800037ce  mov     rax, [rax+0C0h]
0x1800037d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037da  test    al, al
0x1800037dc  jnz     short loc_180003815
0x1800037de  mov     r12d, 0C00000E5h
0x1800037e4  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x1800037eb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800037f0  mov     r9, rax
0x1800037f3  lea     rdi, Class
0x1800037fa  mov     [rsp+470h+var_440], rdi
0x1800037ff  lea     rax, aGetcallinfo; "GetCallInfo"
0x180003806  mov     [rsp+470h+SourceSid], rax
0x18000380b  mov     dword ptr [rsp+470h+var_450], 50Dh
0x180003813  jmp     short loc_1800037AD
0x180003815  mov     eax, [rbp+340h+arg_38]
0x18000381b  test    eax, eax
0x18000381d  jz      short loc_180003822
0x18000381f  or      dword ptr [rbp+340h+var_318+8], eax
0x180003822  cmp     [rbp+340h+var_378], 1
0x180003826  jnz     short loc_180003881
0x180003828  lea     rcx, [rbx+44h]; Buf1
0x18000382c  lea     r9, [rbp+340h+var_3B0]; struct _USER_CACHE_ENTRY **
0x180003830  mov     r8d, 1; unsigned int
0x180003836  mov     rdx, [rbp+340h+Src]; Src
0x18000383a  call    ?AcquireSSOUserCacheEntry@@YAJPEAU_GUID@@PEBGKPEAPEAU_USER_CACHE_ENTRY@@@Z; AcquireSSOUserCacheEntry(_GUID *,ushort const *,ulong,_USER_CACHE_ENTRY * *)
0x18000383f  mov     r12d, eax
0x180003842  cmp     eax, 0C0000064h
0x180003847  jz      short loc_180003881
0x180003849  test    eax, eax
0x18000384b  jz      short loc_180003881
0x18000384d  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x180003854  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180003859  mov     r9, rax
0x18000385c  lea     rdi, Class
0x180003863  mov     [rsp+470h+var_440], rdi
0x180003868  lea     rax, aFailedToAcquir; "Failed to acquire SSO UserCacheEntry"
0x18000386f  mov     [rsp+470h+SourceSid], rax
0x180003874  mov     dword ptr [rsp+470h+var_450], 520h
0x18000387c  jmp     loc_1800037AD
0x180003881  xor     r15d, r15d
0x180003884  mov     rcx, [rbp+340h+var_3B0]
0x180003888  test    rcx, rcx
0x18000388b  jnz     short loc_1800038F3
0x18000388d  test    dword ptr [rbp+340h+var_318+8], 1800h
0x180003894  setnz   r15b
0x180003898  lea     rdx, [rbx+44h]; struct _GUID *
0x18000389c  lea     rax, [rbp+340h+var_3B0]
0x1800038a0  mov     [rsp+470h+var_450], rax; struct _USER_CACHE_ENTRY **
0x1800038a5  xor     r9d, r9d; int
0x1800038a8  mov     r8, [rbp+340h+Src]; unsigned __int16 *
0x1800038ac  mov     ecx, r15d; int
0x1800038af  call    ?_CreateOrAcquireUserCacheEntry@@YAJHPEAU_GUID@@PEBGHPEAPEAU_USER_CACHE_ENTRY@@@Z; _CreateOrAcquireUserCacheEntry(int,_GUID *,ushort const *,int,_USER_CACHE_ENTRY * *)
0x1800038b4  mov     r12d, eax
0x1800038b7  test    eax, eax
0x1800038b9  jz      short loc_1800038EF
0x1800038bb  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x1800038c2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800038c7  mov     r9, rax
0x1800038ca  lea     rdi, Class
0x1800038d1  mov     [rsp+470h+var_440], rdi
0x1800038d6  lea     rax, aCreateoracquir_3; "CreateOrAcquireUserCacheEntry"
0x1800038dd  mov     [rsp+470h+SourceSid], rax
0x1800038e2  mov     dword ptr [rsp+470h+var_450], 52Fh
0x1800038ea  jmp     loc_1800037AD
0x1800038ef  mov     rcx, [rbp+340h+var_3B0]; struct _USER_CACHE_ENTRY *
0x1800038f3  mov     dl, 1; bool
0x1800038f5  call    ?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z; LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)
0x1800038fa  mov     [rbp+340h+var_3BC], 1
0x1800038fe  lea     r9, [rbp+340h+var_388]; struct _LOGON_SESSION **
0x180003902  mov     r8, [rbp+340h+var_390]; struct _SCARD_PIN *
0x180003906  mov     rdx, [rbp+340h+var_3B0]; struct _USER_CACHE_ENTRY *
0x18000390a  mov     rcx, rdi; struct _LUID *
0x18000390d  call    ?CreateLogonSession@@YAJPEAU_LUID@@PEAU_USER_CACHE_ENTRY@@PEAU_SCARD_PIN@@PEAPEAU_LOGON_SESSION@@@Z; CreateLogonSession(_LUID *,_USER_CACHE_ENTRY *,_SCARD_PIN *,_LOGON_SESSION * *)
0x180003912  mov     r12d, eax
0x180003915  lea     rbx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18000391c  lea     rdi, Class
0x180003923  cmp     eax, 0C00000EEh
0x180003928  jnz     loc_180003AE3
0x18000392e  mov     rdx, [rbp+340h+var_390]; struct _SCARD_PIN *
0x180003932  test    rdx, rdx
0x180003935  jz      short loc_180003979
0x180003937  mov     rcx, [rbp+340h+var_330]; struct _LUID *
0x18000393b  call    ?UpdateLogonSessionScardEntry@@YAJPEAU_LUID@@PEAU_SCARD_PIN@@@Z; UpdateLogonSessionScardEntry(_LUID *,_SCARD_PIN *)
0x180003940  mov     r8d, eax
0x180003943  test    eax, eax
0x180003945  jz      short loc_180003979
0x180003947  mov     rcx, rbx; char *
0x18000394a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000394f  mov     r9, rax
0x180003952  mov     [rsp+470h+var_440], rdi
0x180003957  lea     rax, aUpdatelogonses_0; "UpdateLogonSessionScardEntry"
0x18000395e  mov     [rsp+470h+SourceSid], rax
0x180003963  mov     dword ptr [rsp+470h+var_450], 556h
0x18000396b  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180003972  xor     ecx, ecx
0x180003974  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180003979  xor     r12d, r12d
0x18000397c  test    r14d, r14d
0x18000397f  jnz     loc_180003C88
0x180003985  call    cs:__imp_GetCurrentThreadId
0x18000398b  mov     r9d, eax
0x18000398e  lea     rdx, aSurrogatelogon; "SurrogateLogonUser"
0x180003995  lea     rcx, [rbp+340h+var_2F0]
0x180003999  call    ??0?$ActivityBase@VCloudAPProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000399e  lea     rcx, ??_7SurrogateLogonUser@CloudAPProvider@@6B@; const CloudAPProvider::SurrogateLogonUser::`vftable'
0x1800039a5  mov     [rbp+340h+var_2F0], rcx
0x1800039a9  mov     edx, r9d; unsigned int
0x1800039ac  lea     rcx, [rbp+340h+var_2F0]; this
0x1800039b0  call    ?StartActivity@SurrogateLogonUser@CloudAPProvider@@QEAAXK@Z; CloudAPProvider::SurrogateLogonUser::StartActivity(ulong)
0x1800039b5  nop
0x1800039b6  lea     rdx, [rbp+340h+var_2F0]
0x1800039ba  lea     rcx, [rbp+340h+var_1A0]
0x1800039c1  call    ??4SurrogateLogonUser@CloudAPProvider@@QEAAAEAV01@$$QEAV01@@Z; CloudAPProvider::SurrogateLogonUser::operator=(CloudAPProvider::SurrogateLogonUser &&)
0x1800039c6  lea     rcx, [rbp+340h+var_2F0]; this
0x1800039ca  call    ??1SurrogateLogonUser@CloudAPProvider@@QEAA@XZ; CloudAPProvider::SurrogateLogonUser::~SurrogateLogonUser(void)
0x1800039cf  mov     [rbp+340h+var_3BB], 1
0x1800039d3  mov     rax, [rbp+340h+var_3B0]
0x1800039d7  lock inc dword ptr [rax+10h]
0x1800039db  mov     rsi, [rbp+340h+var_3B0]
0x1800039df  mov     eax, [rbp+340h+var_378]
0x1800039e2  mov     [rsi+158h], eax
0x1800039e8  xor     r14d, r14d
0x1800039eb  mov     ecx, [rbp+340h+var_3A8]; enum _SECURITY_LOGON_TYPE
0x1800039ee  cmp     [rbp+340h+var_3BF], r14b
0x1800039f2  jnz     short loc_180003A09
0x1800039f4  test    dword ptr [rbp+340h+var_318+8], 800h
0x1800039fb  jz      short loc_180003A09
0x1800039fd  lea     eax, [rcx-0Ah]
0x180003a00  test    eax, 0FFFFFFFDh
0x180003a05  mov     al, 1
0x180003a07  jnz     short loc_180003A0C
0x180003a09  mov     al, r14b
0x180003a0c  mov     [rsp+470h+var_3C8], r14; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x180003a14  mov     [rsp+470h+var_3D0], r14; struct _tagCacheNodeIdentifier *
0x180003a1c  mov     [rsp+470h+var_3D8], r14; struct _AP_BLOB *
0x180003a24  mov     [rsp+470h+var_3E0], r14; struct _ApPluginSubPkg **
0x180003a2c  lea     rdx, [rbp+340h+var_348]
0x180003a30  mov     [rsp+470h+var_3E8], rdx; struct _APPLUGIN_USER_INFO **
0x180003a38  mov     [rsp+470h+var_3F0], r14; bool *
0x180003a40  lea     rdx, [rbp+340h+var_3BE]
0x180003a44  mov     [rsp+470h+var_3F8], rdx; bool *
0x180003a49  lea     rdx, [rbp+340h+var_3BA]
0x180003a4d  mov     [rsp+470h+var_400], rdx; bool *
0x180003a52  lea     rdx, [rbp+340h+var_3B9]
0x180003a56  mov     [rsp+470h+var_408], rdx; bool *
0x180003a5b  lea     rdx, [rbp+340h+var_3B8]
0x180003a5f  mov     [rsp+470h+var_410], rdx; bool *
0x180003a64  lea     rdx, [rbp+340h+var_3BD]
0x180003a68  mov     [rsp+470h+var_418], rdx; bool *
0x180003a6d  lea     rdx, [rbp+340h+hMem]
0x180003a71  mov     [rsp+470h+var_420], rdx; struct _CloudAPCache **
0x180003a76  lea     rdx, [rbp+340h+var_3BF]
0x180003a7a  mov     [rsp+470h+var_428], rdx; bool *
0x180003a7f  mov     [rsp+470h+var_430], al; bool
0x180003a83  mov     rax, [rbp+340h+var_390]
0x180003a87  mov     [rsp+470h+var_438], rax; struct _SCARD_PIN *
0x180003a8c  mov     byte ptr [rsp+470h+var_440], r14b; bool
0x180003a91  lea     rax, [rbp+340h+var_378]
0x180003a95  mov     [rsp+470h+SourceSid], rax; SourceSid
0x180003a9a  lea     rax, [rbp+340h+var_368]
0x180003a9e  mov     [rsp+470h+var_450], rax; struct _DECRYPTED_AUTH_DATA *
0x180003aa3  lea     r9, [rbp+340h+var_3B0]; struct _USER_CACHE_ENTRY **
0x180003aa7  mov     r8d, r15d; int
0x180003aaa  mov     rdx, [rbp+340h+var_338]; struct _ApPluginPkg *
0x180003aae  call    ?LogonCloudUser@@YAJW4_SECURITY_LOGON_TYPE@@PEAU_ApPluginPkg@@HPEAPEAU_USER_CACHE_ENTRY@@PEAU_DECRYPTED_AUTH_DATA@@PEAU_DPAPI_DECODED_AUTH_DATA@@_NPEAU_SCARD_PIN@@5PEA_NPEAPEAU_CloudAPCache@@777777PEAPEAU_APPLUGIN_USER_INFO@@PEAPEAU_ApPluginSubPkg@@PEAU_AP_BLOB@@PEAU_tagCacheNodeIdentifier@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z; LogonCloudUser(_SECURITY_LOGON_TYPE,_ApPluginPkg *,int,_USER_CACHE_ENTRY * *,_DECRYPTED_AUTH_DATA *,_DPAPI_DECODED_AUTH_DATA *,bool,_SCARD_PIN *,bool,bool *,_CloudAPCache * *,bool *,bool *,bool *,bool *,bool *,bool *,_APPLUGIN_USER_INFO * *,_ApPluginSubPkg * *,_AP_BLOB *,_tagCacheNodeIdentifier *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x180003ab3  mov     r12d, eax
0x180003ab6  test    eax, eax
0x180003ab8  jz      short loc_180003B15
0x180003aba  mov     rcx, rbx; char *
0x180003abd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180003ac2  mov     r9, rax
0x180003ac5  mov     [rsp+470h+var_440], rdi
0x180003aca  lea     rax, aLogonclouduser; "LogonCloudUser"
0x180003ad1  mov     [rsp+470h+SourceSid], rax
0x180003ad6  mov     dword ptr [rsp+470h+var_450], 586h
0x180003ade  jmp     loc_180003745
  ... truncated ...
```
