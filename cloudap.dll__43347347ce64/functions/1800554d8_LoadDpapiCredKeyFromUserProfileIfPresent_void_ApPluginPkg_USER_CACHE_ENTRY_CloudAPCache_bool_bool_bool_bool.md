# LoadDpapiCredKeyFromUserProfileIfPresent(void *,_ApPluginPkg *,_USER_CACHE_ENTRY *,_CloudAPCache *,bool *,bool *,bool *,bool *)

- ea: `0x1800554d8`
- end: `0x180055a57`
- name: `?LoadDpapiCredKeyFromUserProfileIfPresent@@YAJPEAXPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@PEAU_CloudAPCache@@PEA_N444@Z`
- size: `1407`
- prototype: `__int64 __fastcall(void *, struct _ApPluginPkg *, struct _USER_CACHE_ENTRY *, struct _CloudAPCache *, bool *, bool *, bool *, bool *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, installer_update`

## callers

- `0x180010aa0`

## callees

- `0x180003584`
- `0x180007fc0`
- `0x18000a600`
- `0x18002b6dc`
- `0x180032968`
- `0x180034d5c`
- `0x18003a8a8`
- `0x18003bf28`
- `0x180041504`
- `0x180042410`
- `0x180051914`
- `0x180051d34`
- `0x180052110`
- `0x1800554d8`
- `0x18005c058`
- `0x18005c464`
- `0x18005dfa0`
- `0x180081010`

## import_xrefs

- `RPCRT4!UuidEqual` at `0x180055670`
- `RPCRT4!UuidEqual` at `0x180055670`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180055864`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180055864`

## string_xrefs

- `0x180055591`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800555e1`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005567a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180055736`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800557ca`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180055803`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005583b`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800558b2`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180055909`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800559cd`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800559e5`: `UpdateCredentialKey`

## pseudocode

```c
__int64 __fastcall LoadDpapiCredKeyFromUserProfileIfPresent(
        void *a1,
        struct _ApPluginPkg *a2,
        struct _USER_CACHE_ENTRY *a3,
        struct _CloudAPCache *a4,
        bool *a5,
        bool *a6,
        bool *a7,
        bool *a8)
{
  int v10; // eax
  unsigned int v11; // ebx
  const char *v13; // rax
  __int64 v14; // r8
  const char *v15; // r9
  unsigned int v16; // eax
  int KeyBlobForUser; // eax
  int v18; // eax
  unsigned int v19; // eax
  struct _CREDENTIAL_KEY *v20; // r8
  int updated; // eax
  int v22; // eax
  struct _CREDENTIAL_KEY *v23; // rcx
  int v24; // ebx
  GUID *v25; // r8
  GUID *v26; // rdx
  GUID *v27; // r8
  const char *v28; // rax
  int v29; // [rsp+20h] [rbp-D1h]
  struct _AP_BLOB *v30; // [rsp+20h] [rbp-D1h]
  int v31; // [rsp+20h] [rbp-D1h]
  char v32; // [rsp+50h] [rbp-A1h] BYREF
  struct _USER_CACHE_ENTRY *v33; // [rsp+58h] [rbp-99h] BYREF
  struct _CREDENTIAL_KEY *v34; // [rsp+60h] [rbp-91h] BYREF
  RPC_STATUS Status; // [rsp+68h] [rbp-89h] BYREF
  int v36; // [rsp+6Ch] [rbp-85h]
  unsigned __int16 *v37; // [rsp+70h] [rbp-81h] BYREF
  _QWORD v38[5]; // [rsp+78h] [rbp-79h] BYREF
  char v39; // [rsp+A0h] [rbp-51h]
  void *v40; // [rsp+A8h] [rbp-49h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp-41h] BYREF
  int v42[4]; // [rsp+B8h] [rbp-39h] BYREF
  UUID Uuid1[2]; // [rsp+C8h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+47h]

  v40 = a1;
  v33 = a3;
  v37 = 0;
  *(_OWORD *)v42 = 0;
  v34 = 0;
  v32 = 0;
  *a5 = 0;
  *a7 = 0;
  *a8 = 0;
  *a6 = 0;
  v38[0] = &v32;
  v38[1] = &v33;
  v38[2] = &v37;
  v38[3] = v42;
  v38[4] = &v34;
  v39 = 1;
  v10 = CreateUserProfileCacheFolder(a1, &v37);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x631,
      (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp",
      (const char *)(unsigned int)v10,
      v29);
    v39 = 0;
    lambda_cea53874f1c8872d02f40da6897a45ed_::operator()(v38);
    return v11;
  }
  memset(Uuid1, 0, 28);
  if ( (int)GetCredKeyInfo(v37, (const unsigned __int16 *)v33 + 52, (struct _CLOUDAP_CREDKEY_INFO *)Uuid1) >= 0 )
  {
    Status = 0;
    if ( UuidEqual((UUID *)&Uuid1[0].Data2, (UUID *)(*((_QWORD *)v33 + 33) + 16LL), &Status) )
    {
      v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      v16 = Status;
      if ( Status > 0 )
        v16 = (unsigned __int16)Status | 0xC0070000;
      WPPTraceLogA(2, "0x%08x %s:%u : %s:%ws", v16, v15, 1602, "Cred keys are in sync", &Class);
      v39 = 0;
      lambda_cea53874f1c8872d02f40da6897a45ed_::operator()(v38);
    }
    else
    {
      CloudAPProvider::UserKeySyncRequired<_GUID &,_GUID &>(&Uuid1[0].Data2, *((_QWORD *)v33 + 33) + 16LL);
      SystemTimeAsFileTime = 0;
      KeyBlobForUser = GetKeyBlobForUser(
                         v37,
                         (const unsigned __int16 *)v33 + 52,
                         *((const unsigned __int16 **)v33 + 11),
                         (UUID *)&Uuid1[0].Data2,
                         (struct _AP_BLOB *)v42,
                         &SystemTimeAsFileTime);
      if ( KeyBlobForUser < 0 )
      {
        v11 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x651,
                (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp",
                (const char *)(unsigned int)KeyBlobForUser,
                (int)v30);
        v39 = 0;
        lambda_cea53874f1c8872d02f40da6897a45ed_::operator()(v38);
        return v11;
      }
      SCLockConvertExclusiveToShared((PRTL_RESOURCE)(*((_QWORD *)v33 + 3) + 24LL));
      v32 = 1;
      v36 = 0;
      v18 = (*((__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 *, int *))a2 + 33))(
              *((_QWORD *)a2 + 1),
              (__int64)v33 + 280,
              &Uuid1[0].Data2,
              v42);
      if ( v18 < 0 )
      {
        v11 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x660,
                (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp",
                (const char *)(unsigned int)v18,
                0);
        v39 = 0;
        lambda_cea53874f1c8872d02f40da6897a45ed_::operator()(v38);
        return v11;
      }
      if ( v36 )
      {
        v11 = -805305817;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x664,
          (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp",
          (const char *)0xD0000227LL,
          0);
        v39 = 0;
        lambda_cea53874f1c8872d02f40da6897a45ed_::operator()(v38);
        return v11;
      }
      if ( !v34 )
      {
        v11 = -805305817;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x665,
          (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp",
          (const char *)0xD0000227LL,
          0);
        v39 = 0;
        lambda_cea53874f1c8872d02f40da6897a45ed_::operator()(v38);
        return v11;
      }
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v19 = I_CryptSubtractFileTimes(&SystemTimeAsFileTime, &Uuid1[1].Data2);
      v20 = v34;
      if ( v19 >= 0x76A700 )
      {
        v24 = (*((__int64 (__fastcall **)(_QWORD, void *, struct _CREDENTIAL_KEY *, _QWORD))g_pLsaIdProvHostFunctionTable
               + 7))(
                *((_QWORD *)a2 + 2),
                v40,
                v34,
                *((_QWORD *)v33 + 33));
        LODWORD(v40) = v24;
        v25 = (GUID *)*((_QWORD *)v33 + 33);
        v26 = &GUID_00000000_0000_0000_0000_000000000000;
        if ( v25 )
          v27 = v25 + 1;
        else
          v27 = &GUID_00000000_0000_0000_0000_000000000000;
        if ( v34 )
          v26 = (GUID *)((char *)v34 + 16);
        CloudAPProvider::NotifyDpapiToUpdateUserKeyInProfileOnExpiry<long &,_GUID &,_GUID &>(&v40, v26, v27);
        if ( v24 < 0 )
        {
          v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v30) = 1684;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v24, v28, v30, "UpdateCredentialKey", &Class);
          v11 = v24 | 0x10000000;
          v39 = 0;
          lambda_cea53874f1c8872d02f40da6897a45ed_::operator()(v38);
          return v11;
        }
        *a7 = 1;
      }
      else
      {
        *a6 = 1;
        updated = UpdateDPAPICredKey(
                    a4,
                    *((struct _CREDENTIAL_KEY **)v33 + 33),
                    v20,
                    (struct _USER_CACHE_ENTRY *)((char *)v33 + 280));
        if ( updated < 0 )
        {
          v11 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x672,
                  (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp",
                  (const char *)(unsigned int)updated,
                  0);
          v39 = 0;
          lambda_cea53874f1c8872d02f40da6897a45ed_::operator()(v38);
          return v11;
        }
        *a5 = 1;
        v22 = SaveKeyBlobForUser(
                *((const unsigned __int16 **)a2 + 43),
                (const unsigned __int16 *)v33 + 52,
                (UUID *)&Uuid1[0].Data2,
                (struct _AP_BLOB *)v42,
                0);
        if ( v22 < 0 )
        {
          v11 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x67A,
                  (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp",
                  (const char *)(unsigned int)v22,
                  v31);
          v39 = 0;
          lambda_cea53874f1c8872d02f40da6897a45ed_::operator()(v38);
          return v11;
        }
        SCLockConvertSharedToExclusive((PRTL_RESOURCE)(*((_QWORD *)v33 + 3) + 24LL));
        v32 = 0;
        v23 = (struct _CREDENTIAL_KEY *)*((_QWORD *)v33 + 33);
        *((_QWORD *)v33 + 33) = v34;
        v34 = v23;
      }
      v39 = 0;
      lambda_cea53874f1c8872d02f40da6897a45ed_::operator()(v38);
    }
  }
  else
  {
    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v14 = (unsigned __int16)v14;
    if ( (_WORD)v14 )
      v14 = (unsigned __int16)v14 | 0xC0070000;
    WPPTraceLogA(1, "0x%08x %s:%u : %s:%ws", v14, v13, 1593, "GetCredKeyInfo", &Class);
    *a8 = 1;
    *a7 = 1;
    v39 = 0;
    lambda_cea53874f1c8872d02f40da6897a45ed_::operator()(v38);
  }
  return 0;
}

```

## disassembly

```asm
0x1800554d8  push    rbp
0x1800554da  push    rbx
0x1800554db  push    rsi
0x1800554dc  push    rdi
0x1800554dd  push    r12
0x1800554df  push    r13
0x1800554e1  push    r14
0x1800554e3  push    r15
0x1800554e5  lea     rbp, [rsp-7]
0x1800554ea  sub     rsp, 0F8h
0x1800554f1  mov     rax, cs:__security_cookie
0x1800554f8  xor     rax, rsp
0x1800554fb  mov     [rbp+3Fh+var_48], rax
0x1800554ff  mov     r13, r9
0x180055502  mov     rdi, rdx
0x180055505  mov     rax, rcx
0x180055508  mov     [rbp+3Fh+var_88], rcx
0x18005550c  mov     [rsp+130h+var_D8], r8
0x180055511  mov     r15, [rbp+3Fh+arg_20]
0x180055515  mov     r12, [rbp+3Fh+arg_28]
0x180055519  mov     rsi, [rbp+3Fh+arg_30]
0x18005551d  mov     r14, [rbp+3Fh+arg_38]
0x180055524  xor     ecx, ecx
0x180055526  mov     [rsp+130h+var_C0], rcx
0x18005552b  xorps   xmm0, xmm0
0x18005552e  movups  xmmword ptr [rbp+3Fh+var_78], xmm0
0x180055532  mov     [rsp+130h+var_D0], rcx
0x180055537  mov     [rsp+130h+var_E0], cl
0x18005553b  mov     [r15], cl
0x18005553e  mov     [rsi], cl
0x180055540  mov     [r14], cl
0x180055543  mov     [r12], cl
0x180055547  lea     rcx, [rsp+130h+var_E0]
0x18005554c  mov     [rbp+3Fh+var_B8], rcx
0x180055550  lea     rcx, [rsp+130h+var_D8]
0x180055555  mov     [rbp+3Fh+var_B0], rcx
0x180055559  lea     rcx, [rsp+130h+var_C0]
0x18005555e  mov     [rbp+3Fh+var_A8], rcx
0x180055562  lea     rcx, [rbp+3Fh+var_78]
0x180055566  mov     [rbp+3Fh+var_A0], rcx
0x18005556a  lea     rcx, [rsp+130h+var_D0]
0x18005556f  mov     [rbp+3Fh+var_98], rcx
0x180055573  mov     [rbp+3Fh+var_90], 1
0x180055577  lea     rdx, [rsp+130h+var_C0]; unsigned __int16 **
0x18005557c  mov     rcx, rax; hToken
0x18005557f  call    ?CreateUserProfileCacheFolder@@YAJPEAXPEAPEAG@Z; CreateUserProfileCacheFolder(void *,ushort * *)
0x180055584  mov     ebx, eax
0x180055586  test    eax, eax
0x180055588  jns     short loc_1800555B8
0x18005558a  mov     rcx, [rbp+47h]; this
0x18005558e  mov     r9d, eax; char *
0x180055591  lea     r8, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180055598  mov     edx, 631h; void *
0x18005559d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800555a2  nop
0x1800555a3  mov     [rbp+3Fh+var_90], 0
0x1800555a7  lea     rcx, [rbp+3Fh+var_B8]
0x1800555ab  call    _lambda_cea53874f1c8872d02f40da6897a45ed___operator__
0x1800555b0  nop
0x1800555b1  mov     eax, ebx
0x1800555b3  jmp     loc_180055A37
0x1800555b8  xorps   xmm0, xmm0
0x1800555bb  movups  xmmword ptr [rbp+3Fh+Uuid1.Data1], xmm0
0x1800555bf  movups  xmmword ptr [rbp+3Fh+Uuid1.Data4+4], xmm0
0x1800555c3  mov     rdx, [rsp+130h+var_D8]
0x1800555c8  add     rdx, 68h ; 'h'; unsigned __int16 *
0x1800555cc  lea     r8, [rbp+3Fh+Uuid1]; struct _CLOUDAP_CREDKEY_INFO *
0x1800555d0  mov     rcx, [rsp+130h+var_C0]; unsigned __int16 *
0x1800555d5  call    ?GetCredKeyInfo@@YAJPEBG0PEAU_CLOUDAP_CREDKEY_INFO@@@Z; GetCredKeyInfo(ushort const *,ushort const *,_CLOUDAP_CREDKEY_INFO *)
0x1800555da  mov     r8d, eax
0x1800555dd  test    eax, eax
0x1800555df  jns     short loc_18005564F
0x1800555e1  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800555e8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800555ed  movzx   r8d, r8w
0x1800555f1  mov     ecx, r8d
0x1800555f4  or      ecx, 0C0070000h
0x1800555fa  test    r8d, r8d
0x1800555fd  cmovnz  r8d, ecx
0x180055601  lea     rcx, Class
0x180055608  mov     [rsp+130h+var_100], rcx
0x18005560d  lea     rcx, aGetcredkeyinfo; "GetCredKeyInfo"
0x180055614  mov     [rsp+130h+var_108], rcx
0x180055619  mov     dword ptr [rsp+130h+var_110], 639h
0x180055621  mov     r9, rax
0x180055624  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005562b  mov     ecx, 1
0x180055630  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180055635  mov     byte ptr [r14], 1
0x180055639  mov     byte ptr [rsi], 1
0x18005563c  mov     [rbp+3Fh+var_90], 0
0x180055640  lea     rcx, [rbp+3Fh+var_B8]
0x180055644  call    _lambda_cea53874f1c8872d02f40da6897a45ed___operator__
0x180055649  nop
0x18005564a  jmp     loc_180055A35
0x18005564f  xor     r14d, r14d
0x180055652  mov     [rsp+130h+Status], r14d
0x180055657  mov     rax, [rsp+130h+var_D8]
0x18005565c  mov     rdx, [rax+108h]
0x180055663  add     rdx, 10h; Uuid2
0x180055667  lea     r8, [rsp+130h+Status]; Status
0x18005566c  lea     rcx, [rbp+3Fh+Uuid1.Data2]; Uuid1
0x180055670  call    cs:__imp_UuidEqual
0x180055676  test    eax, eax
0x180055678  jz      short loc_1800556E1
0x18005567a  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180055681  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180055686  mov     r9, rax
0x180055689  mov     eax, [rsp+130h+Status]
0x18005568d  test    eax, eax
0x18005568f  jle     short loc_180055699
0x180055691  movzx   eax, ax
0x180055694  or      eax, 0C0070000h
0x180055699  lea     rcx, Class
0x1800556a0  mov     [rsp+130h+var_100], rcx
0x1800556a5  lea     rcx, aCredKeysAreInS; "Cred keys are in sync"
0x1800556ac  mov     [rsp+130h+var_108], rcx
0x1800556b1  mov     dword ptr [rsp+130h+var_110], 642h
0x1800556b9  mov     r8d, eax
0x1800556bc  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800556c3  mov     ecx, 2
0x1800556c8  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800556cd  nop
0x1800556ce  mov     [rbp+3Fh+var_90], r14b
0x1800556d2  lea     rcx, [rbp+3Fh+var_B8]
0x1800556d6  call    _lambda_cea53874f1c8872d02f40da6897a45ed___operator__
0x1800556db  nop
0x1800556dc  jmp     loc_180055A35
0x1800556e1  mov     rax, [rsp+130h+var_D8]
0x1800556e6  mov     rdx, [rax+108h]
0x1800556ed  add     rdx, 10h
0x1800556f1  lea     rcx, [rbp+3Fh+Uuid1.Data2]
0x1800556f5  call    ??$UserKeySyncRequired@AEAU_GUID@@AEAU1@@CloudAPProvider@@SAXAEAU_GUID@@0@Z; CloudAPProvider::UserKeySyncRequired<_GUID &,_GUID &>(_GUID &,_GUID &)
0x1800556fa  mov     qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime], r14
0x1800556fe  mov     r8, [rsp+130h+var_D8]
0x180055703  lea     rdx, [r8+68h]; unsigned __int16 *
0x180055707  lea     rax, [rbp+3Fh+SystemTimeAsFileTime]
0x18005570b  mov     [rsp+130h+var_108], rax; struct _FILETIME *
0x180055710  lea     rax, [rbp+3Fh+var_78]
0x180055714  mov     [rsp+130h+var_110], rax; int
0x180055719  lea     r9, [rbp+3Fh+Uuid1.Data2]; Uuid
0x18005571d  mov     r8, [r8+58h]; Src
0x180055721  mov     rcx, [rsp+130h+var_C0]; unsigned __int16 *
0x180055726  call    ?GetKeyBlobForUser@@YAJPEBG00PEAU_GUID@@PEAU_AP_BLOB@@PEAU_FILETIME@@@Z; GetKeyBlobForUser(ushort const *,ushort const *,ushort const *,_GUID *,_AP_BLOB *,_FILETIME *)
0x18005572b  test    eax, eax
0x18005572d  jns     short loc_18005575C
0x18005572f  mov     rcx, [rbp+47h]; this
0x180055733  mov     r9d, eax; char *
0x180055736  lea     r8, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18005573d  mov     edx, 651h; void *
0x180055742  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180055747  mov     ebx, eax
0x180055749  mov     [rbp+3Fh+var_90], r14b
0x18005574d  lea     rcx, [rbp+3Fh+var_B8]
0x180055751  call    _lambda_cea53874f1c8872d02f40da6897a45ed___operator__
0x180055756  nop
0x180055757  jmp     loc_1800555B1
0x18005575c  mov     rax, [rsp+130h+var_D8]
0x180055761  mov     rcx, [rax+18h]
0x180055765  add     rcx, 18h; Resource
0x180055769  call    SCLockConvertExclusiveToShared
0x18005576e  mov     [rsp+130h+var_E0], 1
0x180055773  mov     [rsp+130h+var_C4], r14d
0x180055778  mov     rdx, [rsp+130h+var_D8]
0x18005577d  add     rdx, 118h
0x180055784  mov     [rsp+130h+var_F0], r14
0x180055789  mov     [rsp+130h+var_F8], r14
0x18005578e  lea     rax, [rsp+130h+var_C4]
0x180055793  mov     [rsp+130h+var_100], rax
0x180055798  lea     rax, [rsp+130h+var_D0]
0x18005579d  mov     [rsp+130h+var_108], rax
0x1800557a2  mov     dword ptr [rsp+130h+var_110], r14d; int
0x1800557a7  lea     r9, [rbp+3Fh+var_78]
0x1800557ab  lea     r8, [rbp+3Fh+Uuid1.Data2]
0x1800557af  mov     rcx, [rdi+8]
0x1800557b3  mov     rax, [rdi+108h]
0x1800557ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800557bf  test    eax, eax
0x1800557c1  jns     short loc_1800557F0
0x1800557c3  mov     rcx, [rbp+47h]; this
0x1800557c7  mov     r9d, eax; char *
0x1800557ca  lea     r8, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800557d1  mov     edx, 660h; void *
0x1800557d6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800557db  mov     ebx, eax
0x1800557dd  mov     [rbp+3Fh+var_90], r14b
0x1800557e1  lea     rcx, [rbp+3Fh+var_B8]
0x1800557e5  call    _lambda_cea53874f1c8872d02f40da6897a45ed___operator__
0x1800557ea  nop
0x1800557eb  jmp     loc_1800555B1
0x1800557f0  cmp     [rsp+130h+var_C4], r14d
0x1800557f5  jz      short loc_180055828
0x1800557f7  mov     rcx, [rbp+47h]; this
0x1800557fb  mov     ebx, 0D0000227h
0x180055800  mov     r9d, ebx; char *
0x180055803  lea     r8, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18005580a  mov     edx, 664h; void *
0x18005580f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055814  nop
0x180055815  mov     [rbp+3Fh+var_90], r14b
0x180055819  lea     rcx, [rbp+3Fh+var_B8]
0x18005581d  call    _lambda_cea53874f1c8872d02f40da6897a45ed___operator__
0x180055822  nop
0x180055823  jmp     loc_1800555B1
0x180055828  cmp     [rsp+130h+var_D0], r14
0x18005582d  jnz     short loc_180055860
0x18005582f  mov     rcx, [rbp+47h]; this
0x180055833  mov     ebx, 0D0000227h
0x180055838  mov     r9d, ebx; char *
0x18005583b  lea     r8, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180055842  mov     edx, 665h; void *
0x180055847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005584c  nop
0x18005584d  mov     [rbp+3Fh+var_90], r14b
0x180055851  lea     rcx, [rbp+3Fh+var_B8]
0x180055855  call    _lambda_cea53874f1c8872d02f40da6897a45ed___operator__
0x18005585a  nop
0x18005585b  jmp     loc_1800555B1
0x180055860  lea     rcx, [rbp+3Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180055864  call    cs:__imp_GetSystemTimeAsFileTime
0x18005586a  lea     rdx, [rbp+3Fh+var_54]
0x18005586e  lea     rcx, [rbp+3Fh+SystemTimeAsFileTime]
0x180055872  call    I_CryptSubtractFileTimes
0x180055877  mov     r8, [rsp+130h+var_D0]; struct _CREDENTIAL_KEY *
0x18005587c  cmp     eax, 76A700h
0x180055881  jnb     loc_180055968
0x180055887  mov     byte ptr [r12], 1
0x18005588c  mov     rdx, [rsp+130h+var_D8]
0x180055891  lea     r9, [rdx+118h]; struct _AP_BLOB *
0x180055898  mov     rdx, [rdx+108h]; struct _CREDENTIAL_KEY *
0x18005589f  mov     rcx, r13; struct _CloudAPCache *
0x1800558a2  call    ?UpdateDPAPICredKey@@YAJPEAU_CloudAPCache@@PEAU_CREDENTIAL_KEY@@1PEAU_AP_BLOB@@@Z; UpdateDPAPICredKey(_CloudAPCache *,_CREDENTIAL_KEY *,_CREDENTIAL_KEY *,_AP_BLOB *)
0x1800558a7  test    eax, eax
0x1800558a9  jns     short loc_1800558D8
0x1800558ab  mov     rcx, [rbp+47h]; this
0x1800558af  mov     r9d, eax; char *
0x1800558b2  lea     r8, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800558b9  mov     edx, 672h; void *
0x1800558be  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800558c3  mov     ebx, eax
0x1800558c5  mov     [rbp+3Fh+var_90], r14b
0x1800558c9  lea     rcx, [rbp+3Fh+var_B8]
0x1800558cd  call    _lambda_cea53874f1c8872d02f40da6897a45ed___operator__
0x1800558d2  nop
0x1800558d3  jmp     loc_1800555B1
0x1800558d8  mov     byte ptr [r15], 1
0x1800558dc  mov     rdx, [rsp+130h+var_D8]
0x1800558e1  add     rdx, 68h ; 'h'; unsigned __int16 *
0x1800558e5  mov     [rsp+130h+var_110], r14; int
0x1800558ea  lea     r9, [rbp+3Fh+var_78]; struct _AP_BLOB *
0x1800558ee  lea     r8, [rbp+3Fh+Uuid1.Data2]; Uuid
0x1800558f2  mov     rcx, [rdi+158h]; unsigned __int16 *
0x1800558f9  call    ?SaveKeyBlobForUser@@YAJPEBG0PEAU_GUID@@PEAU_AP_BLOB@@PEAX@Z; SaveKeyBlobForUser(ushort const *,ushort const *,_GUID *,_AP_BLOB *,void *)
0x1800558fe  test    eax, eax
0x180055900  jns     short loc_18005592F
0x180055902  mov     rcx, [rbp+47h]; this
0x180055906  mov     r9d, eax; char *
0x180055909  lea     r8, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180055910  mov     edx, 67Ah; void *
0x180055915  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005591a  mov     ebx, eax
0x18005591c  mov     [rbp+3Fh+var_90], r14b
0x180055920  lea     rcx, [rbp+3Fh+var_B8]
0x180055924  call    _lambda_cea53874f1c8872d02f40da6897a45ed___operator__
0x180055929  nop
0x18005592a  jmp     loc_1800555B1
0x18005592f  mov     rax, [rsp+130h+var_D8]
0x180055934  mov     rcx, [rax+18h]
0x180055938  add     rcx, 18h; Resource
0x18005593c  call    SCLockConvertSharedToExclusive
0x180055941  mov     [rsp+130h+var_E0], r14b
0x180055946  mov     rdx, [rsp+130h+var_D8]
0x18005594b  mov     rcx, [rdx+108h]
0x180055952  mov     rax, [rsp+130h+var_D0]
0x180055957  mov     [rdx+108h], rax
0x18005595e  mov     [rsp+130h+var_D0], rcx
0x180055963  jmp     loc_180055A27
0x180055968  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x18005596f  mov     r9, [rsp+130h+var_D8]
0x180055974  mov     r9, [r9+108h]
0x18005597b  mov     rdx, [rbp+3Fh+var_88]
0x18005597f  mov     rcx, [rdi+10h]
0x180055983  mov     rax, [rax+38h]
0x180055987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005598c  mov     ebx, eax
0x18005598e  mov     dword ptr [rbp+3Fh+var_88], eax
0x180055991  mov     rax, [rsp+130h+var_D8]
0x180055996  mov     r8, [rax+108h]
0x18005599d  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000
0x1800559a4  test    r8, r8
0x1800559a7  jz      short loc_1800559AF
0x1800559a9  add     r8, 10h
0x1800559ad  jmp     short loc_1800559B2
0x1800559af  mov     r8, rdx
0x1800559b2  mov     rax, [rsp+130h+var_D0]
0x1800559b7  test    rax, rax
0x1800559ba  jz      short loc_1800559C0
0x1800559bc  lea     rdx, [rax+10h]
0x1800559c0  lea     rcx, [rbp+3Fh+var_88]
0x1800559c4  call    ??$NotifyDpapiToUpdateUserKeyInProfileOnExpiry@AEAJAEAU_GUID@@AEAU1@@CloudAPProvider@@SAXAEAJAEAU_GUID@@1@Z; CloudAPProvider::NotifyDpapiToUpdateUserKeyInProfileOnExpiry<long &,_GUID &,_GUID &>(long &,_GUID &,_GUID &)
  ... truncated ...
```
