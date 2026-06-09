# RollDpapiKey(void *,_ApPluginPkg *,_USER_CACHE_ENTRY *,bool,_CloudAPCache *,bool *)

- ea: `0x180010aa0`
- end: `0x18001128c`
- name: `?RollDpapiKey@@YAJPEAXPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@_NPEAU_CloudAPCache@@PEA_N@Z`
- size: `2028`
- prototype: `int(void *, struct _ApPluginPkg *, struct _USER_CACHE_ENTRY *, bool, struct _CloudAPCache *, bool *)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, installer_update`

## callers

- `0x1800104c0`

## callees

- `0x180003584`
- `0x180007fc0`
- `0x18000a600`
- `0x180010aa0`
- `0x180011294`
- `0x180011424`
- `0x180016410`
- `0x1800165f0`
- `0x1800237d4`
- `0x18002cc60`
- `0x180032968`
- `0x180039ff8`
- `0x180041504`
- `0x180042410`
- `0x1800463d8`
- `0x1800516c0`
- `0x180051844`
- `0x1800519e4`
- `0x180051c4c`
- `0x1800554d8`
- `0x1800597ac`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800111d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800111d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001119f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001119f`
- `RPCRT4!UuidEqual` at `0x180010e61`
- `RPCRT4!UuidEqual` at `0x180010e61`

## string_xrefs

- `0x180010c11`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180010ca2`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180010dc4`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180010ef1`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180010fb0`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800110bc`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180010f09`: `UpdateCredentialKey`
- `0x180010fd0`: `UpdateCredentialKey(RollBack)`
- `0x180011012`: `UpdateDPAPICredKey`
- `0x1800110db`: `UpdateDPAPICredKeyInUserProfile`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RollDpapiKey(
        void *a1,
        struct _ApPluginPkg *a2,
        struct _USER_CACHE_ENTRY *a3,
        bool a4,
        struct _CloudAPCache *a5,
        bool *a6)
{
  int updated; // r14d
  int v9; // r15d
  bool v10; // bl
  unsigned int *v11; // rcx
  const char *v12; // r9
  const char *v13; // rcx
  bool v14; // zf
  void *v15; // rax
  const char *v16; // r9
  __int128 *v17; // r12
  char v18; // r13
  int v19; // eax
  unsigned __int16 v20; // bx
  int v21; // eax
  unsigned int v22; // eax
  const char *v23; // rax
  __int64 v24; // r8
  unsigned int v25; // r9d
  unsigned int *v26; // r15
  UUID *v27; // rcx
  void *v28; // r15
  __int64 v29; // r8
  __int128 *v30; // r8
  __int64 v31; // rax
  __int128 *v32; // rdx
  const char *v33; // rax
  struct _CloudAPCache *v34; // rbx
  unsigned int v35; // r15d
  __int64 v36; // r8
  __int128 *v37; // r8
  __int64 v38; // rax
  const char *v39; // rax
  const char *v40; // rax
  unsigned int v41; // eax
  const char *v42; // rax
  __int64 v43; // r8
  unsigned int v44; // r9d
  __int64 v45; // rax
  __int64 v46; // rdx
  _BYTE *v47; // rax
  RTL_SRWLOCK *v48; // rbx
  char v49; // di
  struct wil::FailureInfo *v50; // rdx
  int v51; // ecx
  int v52; // eax
  bool *v54; // [rsp+20h] [rbp-E0h]
  bool v55; // [rsp+40h] [rbp-C0h] BYREF
  bool v56; // [rsp+41h] [rbp-BFh] BYREF
  bool v57; // [rsp+42h] [rbp-BEh] BYREF
  bool v58; // [rsp+43h] [rbp-BDh] BYREF
  bool v59; // [rsp+44h] [rbp-BCh]
  bool v60; // [rsp+45h] [rbp-BBh]
  int v61; // [rsp+48h] [rbp-B8h] BYREF
  RPC_STATUS Status; // [rsp+4Ch] [rbp-B4h] BYREF
  bool *v63; // [rsp+50h] [rbp-B0h]
  void *v64; // [rsp+58h] [rbp-A8h]
  struct _CloudAPCache *v65; // [rsp+60h] [rbp-A0h]
  _OWORD v66[9]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v67; // [rsp+100h] [rbp+0h]
  void **v68; // [rsp+110h] [rbp+10h] BYREF
  int v69; // [rsp+118h] [rbp+18h] BYREF
  char v70; // [rsp+11Ch] [rbp+1Ch]
  int v71; // [rsp+140h] [rbp+40h] BYREF
  const char *v72; // [rsp+148h] [rbp+48h]
  __int64 v73; // [rsp+150h] [rbp+50h]
  char v74; // [rsp+158h] [rbp+58h]
  int v75; // [rsp+160h] [rbp+60h]
  __int128 v76; // [rsp+168h] [rbp+68h]
  __int128 v77; // [rsp+178h] [rbp+78h]
  __int128 v78; // [rsp+188h] [rbp+88h]
  __int128 v79; // [rsp+198h] [rbp+98h]
  __int128 v80; // [rsp+1A8h] [rbp+A8h]
  __int128 v81; // [rsp+1B8h] [rbp+B8h]
  __int128 v82; // [rsp+1C8h] [rbp+C8h]
  __int128 v83; // [rsp+1D8h] [rbp+D8h]
  __int128 v84; // [rsp+1E8h] [rbp+E8h]
  __int64 v85; // [rsp+1F8h] [rbp+F8h]
  __int128 v86; // [rsp+200h] [rbp+100h]
  int v87; // [rsp+210h] [rbp+110h]
  __int64 v88; // [rsp+218h] [rbp+118h]
  struct wil::FailureInfo *v89; // [rsp+220h] [rbp+120h]
  _QWORD v90[4]; // [rsp+228h] [rbp+128h] BYREF
  int v91; // [rsp+248h] [rbp+148h]
  int *v92; // [rsp+250h] [rbp+150h]
  char v93; // [rsp+258h] [rbp+158h]

  v59 = a4;
  v64 = a1;
  v65 = a5;
  v63 = a6;
  updated = 0;
  Status = 0;
  v9 = *(_DWORD *)a5 & 2;
  v60 = v9 != 0;
  v55 = 0;
  v10 = 0;
  v56 = 0;
  v69 = 0;
  v70 = 0;
  v74 = 0;
  v71 = 0;
  v72 = "RollDpapiKey";
  v73 = 0;
  v75 = 0;
  v86 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v87 = 1;
  v88 = 0;
  v89 = (struct wil::FailureInfo *)&v69;
  v90[0] = 0;
  v90[1] = 0;
  v90[2] = &v68;
  v90[3] = 0;
  v91 = 0;
  v92 = &v71;
  v93 = 0;
  v68 = &CloudAPProvider::RollDpapiKey::`vftable';
  CloudAPProvider::RollDpapiKey::StartActivity((CloudAPProvider::RollDpapiKey *)&v68);
  *a6 = 0;
  v11 = (unsigned int *)*((_QWORD *)a3 + 33);
  if ( v11 )
  {
    if ( v9 && !*((_QWORD *)a3 + 34) )
    {
      v15 = (void *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(*v11);
      *((_QWORD *)a3 + 34) = v15;
      if ( !v15 )
      {
        updated = -1073741801;
        v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v16, 1785, "AllocateLsaHeap", &Class);
        goto LABEL_61;
      }
      memcpy_0(v15, *((const void **)a3 + 33), **((unsigned int **)a3 + 33));
    }
    v17 = (__int128 *)&GUID_00000000_0000_0000_0000_000000000000;
    if ( (*((_DWORD *)a2 + 40) & 0x22) == 0
      && *((_QWORD *)a2 + 33)
      && (wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::GetImpl'::`2'::impl),
          IsLoadAadCredKeyFromProfileEnabled()) )
    {
      v18 = 1;
      if ( !*((_DWORD *)a3 + 88) )
      {
        v57 = 0;
        v19 = LoadDpapiCredKeyFromUserProfileIfPresent(v64, a2, a3, v65, v63, &v55, &v56, &v57);
        v20 = v19;
        v61 = v19;
        v21 = ((v19 >> 31) & 1) + 1;
        *((_DWORD *)a3 + 88) = v21;
        v58 = v21 == 2;
        CloudAPProvider::LoadDpapiCredKeyFromUserProfileIfPresent<bool &,bool &,bool,long &>(&v57, &v55, &v58, &v61);
        v22 = v20;
        if ( v20 )
          v22 = v20 | 0xC0070000;
        if ( v22 )
        {
          v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          if ( (_DWORD)v24 )
            v24 = v25;
          LODWORD(v54) = 1823;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v24, v23, v54, "LoadDpapiCredKeyFromUserProfileIfPresent", &Class);
          goto LABEL_61;
        }
        v10 = v56;
        if ( v55 )
        {
          v26 = (unsigned int *)*((_QWORD *)a3 + 34);
          *((_QWORD *)a3 + 34) = 0;
          goto LABEL_47;
        }
      }
    }
    else
    {
      v18 = 0;
    }
    if ( v9
      || (v26 = 0, (v27 = (UUID *)*((_QWORD *)a3 + 34)) != 0)
      && !UuidEqual(v27 + 1, (UUID *)(*((_QWORD *)a3 + 33) + 16LL), &Status) )
    {
      SCLockConvertExclusiveToShared((PRTL_RESOURCE)(*((_QWORD *)a3 + 3) + 24LL));
      v28 = v64;
      updated = (*((__int64 (__fastcall **)(_QWORD, void *, _QWORD, _QWORD))g_pLsaIdProvHostFunctionTable + 7))(
                  *((_QWORD *)a2 + 2),
                  v64,
                  *((_QWORD *)a3 + 33),
                  *((_QWORD *)a3 + 34));
      v61 = updated;
      v29 = *((_QWORD *)a3 + 34);
      if ( v29 )
        v30 = (__int128 *)(v29 + 16);
      else
        v30 = (__int128 *)&GUID_00000000_0000_0000_0000_000000000000;
      v31 = *((_QWORD *)a3 + 33);
      v32 = (__int128 *)(v31 + 16);
      if ( !v31 )
        v32 = (__int128 *)&GUID_00000000_0000_0000_0000_000000000000;
      CloudAPProvider::NotifyDpapiToUpdateCurrentUserKey<long &,_GUID &,_GUID &>(&v61, v32, v30);
      if ( updated < 0 )
      {
        SCLockConvertSharedToExclusive((PRTL_RESOURCE)(*((_QWORD *)a3 + 3) + 24LL));
        v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v54) = 1863;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)updated, v33, v54, "UpdateCredentialKey", &Class);
        goto LABEL_61;
      }
      v34 = v65;
      updated = UpdateDPAPICredKey(
                  v65,
                  *((struct _CREDENTIAL_KEY **)a3 + 33),
                  *((struct _CREDENTIAL_KEY **)a3 + 34),
                  (struct _USER_CACHE_ENTRY *)((char *)a3 + 280));
      if ( updated < 0 )
      {
        v35 = (*((__int64 (__fastcall **)(_QWORD, void *, _QWORD, _QWORD))g_pLsaIdProvHostFunctionTable + 7))(
                *((_QWORD *)a2 + 2),
                v28,
                *((_QWORD *)a3 + 34),
                *((_QWORD *)a3 + 33));
        v61 = v35;
        v36 = *((_QWORD *)a3 + 33);
        if ( v36 )
          v37 = (__int128 *)(v36 + 16);
        else
          v37 = (__int128 *)&GUID_00000000_0000_0000_0000_000000000000;
        v38 = *((_QWORD *)a3 + 34);
        if ( v38 )
          v17 = (__int128 *)(v38 + 16);
        CloudAPProvider::NotifyDpapiToUpdateUserKeyRollBack<long &,_GUID &,_GUID &>(&v61, v17, v37);
        if ( v35 )
        {
          v39 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v54) = 1886;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v35, v39, v54, "UpdateCredentialKey(RollBack)", &Class);
        }
        SCLockConvertSharedToExclusive((PRTL_RESOURCE)(*((_QWORD *)a3 + 3) + 24LL));
        v40 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v54) = 1889;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)updated, v40, v54, "UpdateDPAPICredKey", &Class);
        goto LABEL_61;
      }
      SCLockConvertSharedToExclusive((PRTL_RESOURCE)(*((_QWORD *)a3 + 3) + 24LL));
      WriteCredKeyEventLog(a3, 0);
      WriteCredKeyEventLog(a3, 1u);
      v26 = (unsigned int *)*((_QWORD *)a3 + 33);
      *((_QWORD *)a3 + 33) = *((_QWORD *)a3 + 34);
      *((_QWORD *)a3 + 34) = 0;
      *(_DWORD *)v34 &= ~2u;
      *v63 = 1;
      v10 = v18;
    }
LABEL_47:
    if ( v10 )
    {
      v61 = UpdateDPAPICredKeyInUserProfile(v64, (__int64)a2, (__int64)a3);
      v41 = (unsigned __int16)v61;
      if ( (_WORD)v61 )
        v41 = (unsigned __int16)v61 | 0xC0070000;
      if ( v41 )
      {
        v42 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        if ( (_DWORD)v43 )
          v43 = v44;
        LODWORD(v54) = 1917;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v43, v42, v54, "UpdateDPAPICredKeyInUserProfile", &Class);
      }
      v45 = *((_QWORD *)a3 + 33);
      if ( v45 )
        v17 = (__int128 *)(v45 + 16);
      CloudAPProvider::UpdateDpapiCredKeyInUserProfile<long &,_GUID &>(&v61, v17);
    }
    updated = 0;
    if ( v26 )
    {
      v46 = *v26;
      v47 = v26;
      if ( *v26 )
      {
        do
        {
          *v47++ = 0;
          --v46;
        }
        while ( v46 );
      }
      ((void (__fastcall *)(unsigned int *))g_pLsaFunctionTable->FreeLsaHeap)(v26);
    }
    goto LABEL_61;
  }
  updated = -1073741595;
  v12 = "";
  while ( 1 )
  {
    v13 = v12--;
    v14 = *v12 == 92;
    if ( *v12 == 92 )
      break;
    if ( v12 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
    {
      v14 = *v12 == 92;
      break;
    }
  }
  if ( v14 )
    v12 = v13;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v12, 1773, "No Current Cred Key", &Class);
LABEL_61:
  CloudAPProvider::RollDpapiKey::Stop((CloudAPProvider::RollDpapiKey *)&v68, v60, v59, *v63, updated);
  v68 = &CloudAPProvider::RollDpapiKey::`vftable';
  if ( !v90[0] )
    goto LABEL_69;
  v48 = (RTL_SRWLOCK *)(v90[0] + 264LL);
  AcquireSRWLockExclusive((PSRWLOCK)(v90[0] + 264LL));
  if ( v90[0] && *(_DWORD *)v90[0] == 1 )
  {
    v49 = 1;
  }
  else
  {
    v49 = 0;
    wil::details::shared_object<wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CloudAPProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v90);
  }
  if ( v48 )
    ReleaseSRWLockExclusive(v48);
  if ( v49 )
  {
LABEL_69:
    v50 = v89;
    if ( *(_DWORD *)v89 == 1 )
    {
      v51 = -2147024322;
      if ( *((int *)v89 + 22) < 0 )
        v51 = *((_DWORD *)v89 + 22);
      v52 = *((_DWORD *)v89 + 62);
      if ( v52 < 1 )
      {
        memset(v66, 0, sizeof(v66));
        v67 = 0;
        wil::details::WilFailFast((wil::details *)v66, v89);
      }
      if ( *((int *)v89 + 18) >= 0 )
        *((_DWORD *)v89 + 18) = v51;
      *((_DWORD *)v50 + 62) = v52 - 1;
      ((void (__fastcall *)(void ***))v68[1])(&v68);
    }
  }
  wil::ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CloudAPProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(&v68);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180010aa0  push    rbp
0x180010aa2  push    rbx
0x180010aa3  push    rsi
0x180010aa4  push    rdi
0x180010aa5  push    r12
0x180010aa7  push    r13
0x180010aa9  push    r14
0x180010aab  push    r15
0x180010aad  lea     rbp, [rsp-178h]
0x180010ab5  sub     rsp, 278h
0x180010abc  mov     rax, cs:__security_cookie
0x180010ac3  xor     rax, rsp
0x180010ac6  mov     [rbp+1B0h+var_50], rax
0x180010acd  mov     [rsp+2B0h+var_26C], r9b
0x180010ad2  mov     rdi, r8
0x180010ad5  mov     rsi, rdx
0x180010ad8  mov     [rsp+2B0h+var_258], rcx
0x180010add  mov     rax, [rbp+1B0h+arg_20]
0x180010ae4  mov     [rsp+2B0h+var_250], rax
0x180010ae9  mov     rcx, [rbp+1B0h+arg_28]
0x180010af0  mov     [rsp+2B0h+var_260], rcx
0x180010af5  xor     r13d, r13d
0x180010af8  mov     r14d, r13d
0x180010afb  mov     [rsp+2B0h+Status], r13d
0x180010b00  mov     r15d, [rax]
0x180010b03  and     r15d, 2
0x180010b07  setnz   [rsp+2B0h+var_26B]
0x180010b0c  mov     [rsp+2B0h+var_270], r13b
0x180010b11  xor     bl, bl
0x180010b13  mov     [rsp+2B0h+var_26F], bl
0x180010b17  mov     [rbp+1B0h+var_198], r13d
0x180010b1b  mov     [rbp+1B0h+var_194], bl
0x180010b1e  mov     [rbp+1B0h+var_158], bl
0x180010b21  mov     [rbp+1B0h+var_170], r13d
0x180010b25  lea     rax, aRolldpapikey; "RollDpapiKey"
0x180010b2c  mov     [rbp+1B0h+var_168], rax
0x180010b30  mov     [rbp+1B0h+var_160], r13
0x180010b34  mov     [rbp+1B0h+var_150], r13d
0x180010b38  xorps   xmm0, xmm0
0x180010b3b  movdqa  [rbp+1B0h+var_B0], xmm0
0x180010b43  xorps   xmm1, xmm1
0x180010b46  xor     eax, eax
0x180010b48  movups  [rbp+1B0h+var_148], xmm1
0x180010b4c  movups  [rbp+1B0h+var_138], xmm1
0x180010b50  movups  [rbp+1B0h+var_128], xmm1
0x180010b57  movups  [rbp+1B0h+var_118], xmm1
0x180010b5e  movups  [rbp+1B0h+var_108], xmm1
0x180010b65  movups  [rbp+1B0h+var_F8], xmm1
0x180010b6c  movups  [rbp+1B0h+var_E8], xmm1
0x180010b73  movups  [rbp+1B0h+var_D8], xmm1
0x180010b7a  movups  [rbp+1B0h+var_C8], xmm1
0x180010b81  mov     [rbp+1B0h+var_B8], rax
0x180010b88  mov     [rbp+1B0h+var_A0], 1
0x180010b92  mov     [rbp+1B0h+var_98], rax
0x180010b99  lea     rax, [rbp+1B0h+var_198]
0x180010b9d  mov     [rbp+1B0h+var_90], rax
0x180010ba4  mov     [rbp+1B0h+var_88], r13
0x180010bab  mov     [rbp+1B0h+var_80], r13
0x180010bb2  lea     rax, [rbp+1B0h+var_1A0]
0x180010bb6  mov     [rbp+1B0h+var_78], rax
0x180010bbd  mov     [rbp+1B0h+var_70], r13
0x180010bc4  mov     [rbp+1B0h+var_68], r13d
0x180010bcb  lea     rax, [rbp+1B0h+var_170]
0x180010bcf  mov     [rbp+1B0h+var_60], rax
0x180010bd6  mov     [rbp+1B0h+var_58], bl
0x180010bdc  lea     rax, ??_7RollDpapiKey@CloudAPProvider@@6B@; const CloudAPProvider::RollDpapiKey::`vftable'
0x180010be3  mov     [rbp+1B0h+var_1A0], rax
0x180010be7  lea     rcx, [rbp+1B0h+var_1A0]; this
0x180010beb  call    ?StartActivity@RollDpapiKey@CloudAPProvider@@QEAAXXZ; CloudAPProvider::RollDpapiKey::StartActivity(void)
0x180010bf0  nop
0x180010bf1  mov     rax, [rsp+2B0h+var_260]
0x180010bf6  mov     [rax], bl
0x180010bf8  mov     rcx, [rdi+108h]
0x180010bff  test    rcx, rcx
0x180010c02  jnz     short loc_180010C6F
0x180010c04  mov     r14d, 0C00000E5h
0x180010c0a  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x180010c11  lea     rbx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180010c18  nop     dword ptr [rax+rax+00000000h]
0x180010c20  mov     rcx, r9
0x180010c23  dec     r9
0x180010c26  movzx   eax, byte ptr [r9]
0x180010c2a  cmp     al, 5Ch ; '\'
0x180010c2c  jz      short loc_180010C35
0x180010c2e  cmp     r9, rbx
0x180010c31  ja      short loc_180010C20
0x180010c33  cmp     al, 5Ch ; '\'
0x180010c35  cmovz   r9, rcx
0x180010c39  lea     rsi, Class
0x180010c40  mov     [rsp+2B0h+var_280], rsi
0x180010c45  lea     rax, aNoCurrentCredK; "No Current Cred Key"
0x180010c4c  mov     [rsp+2B0h+var_288], rax
0x180010c51  mov     dword ptr [rsp+2B0h+var_290], 6EDh
0x180010c59  mov     r8d, r14d
0x180010c5c  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180010c63  xor     ecx, ecx
0x180010c65  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180010c6a  jmp     loc_180011150
0x180010c6f  test    r15d, r15d
0x180010c72  jz      short loc_180010CE5
0x180010c74  cmp     qword ptr [rdi+110h], 0
0x180010c7c  jnz     short loc_180010CE5
0x180010c7e  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180010c85  mov     ecx, [rcx]
0x180010c87  mov     rax, [rax+28h]
0x180010c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c90  mov     [rdi+110h], rax
0x180010c97  test    rax, rax
0x180010c9a  jnz     short loc_180010CD3
0x180010c9c  mov     r14d, 0C0000017h
0x180010ca2  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180010ca9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010cae  lea     rsi, Class
0x180010cb5  mov     [rsp+2B0h+var_280], rsi
0x180010cba  lea     rcx, aAllocatelsahea_3; "AllocateLsaHeap"
0x180010cc1  mov     [rsp+2B0h+var_288], rcx
0x180010cc6  mov     dword ptr [rsp+2B0h+var_290], 6F9h
0x180010cce  mov     r9, rax
0x180010cd1  jmp     short loc_180010C59
0x180010cd3  mov     rdx, [rdi+108h]; Src
0x180010cda  mov     r8d, [rdx]; Size
0x180010cdd  mov     rcx, rax; void *
0x180010ce0  call    memcpy_0
0x180010ce5  mov     eax, [rsi+0A0h]
0x180010ceb  lea     r12, _GUID_00000000_0000_0000_0000_000000000000
0x180010cf2  test    al, 22h
0x180010cf4  jnz     loc_180010E32
0x180010cfa  cmp     qword ptr [rsi+108h], 0
0x180010d02  jz      loc_180010E32
0x180010d08  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile> `wil::Feature<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::GetImpl(void)'::`2'::impl
0x180010d0f  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180010d14  call    ?IsLoadAadCredKeyFromProfileEnabled@@YA_NXZ; IsLoadAadCredKeyFromProfileEnabled(void)
0x180010d19  test    al, al
0x180010d1b  jz      loc_180010E32
0x180010d21  mov     r13b, 1
0x180010d24  cmp     dword ptr [rdi+160h], 0
0x180010d2b  jnz     loc_180010E35
0x180010d31  mov     [rsp+2B0h+var_26E], 0
0x180010d36  lea     rax, [rsp+2B0h+var_26E]
0x180010d3b  mov     [rsp+2B0h+var_278], rax; bool *
0x180010d40  lea     rax, [rsp+2B0h+var_26F]
0x180010d45  mov     [rsp+2B0h+var_280], rax; bool *
0x180010d4a  lea     rax, [rsp+2B0h+var_270]
0x180010d4f  mov     [rsp+2B0h+var_288], rax; bool *
0x180010d54  mov     rax, [rsp+2B0h+var_260]
0x180010d59  mov     [rsp+2B0h+var_290], rax; bool *
0x180010d5e  mov     r9, [rsp+2B0h+var_250]; struct _CloudAPCache *
0x180010d63  mov     r8, rdi; struct _USER_CACHE_ENTRY *
0x180010d66  mov     rdx, rsi; struct _ApPluginPkg *
0x180010d69  mov     rcx, [rsp+2B0h+var_258]; void *
0x180010d6e  call    ?LoadDpapiCredKeyFromUserProfileIfPresent@@YAJPEAXPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@PEAU_CloudAPCache@@PEA_N444@Z; LoadDpapiCredKeyFromUserProfileIfPresent(void *,_ApPluginPkg *,_USER_CACHE_ENTRY *,_CloudAPCache *,bool *,bool *,bool *,bool *)
0x180010d73  mov     ebx, eax
0x180010d75  mov     [rsp+2B0h+var_268], eax
0x180010d79  sar     eax, 1Fh
0x180010d7c  and     eax, 1
0x180010d7f  inc     eax
0x180010d81  mov     [rdi+160h], eax
0x180010d87  cmp     eax, 2
0x180010d8a  setz    [rsp+2B0h+var_26D]
0x180010d8f  lea     r9, [rsp+2B0h+var_268]
0x180010d94  lea     r8, [rsp+2B0h+var_26D]
0x180010d99  lea     rdx, [rsp+2B0h+var_270]
0x180010d9e  lea     rcx, [rsp+2B0h+var_26E]
0x180010da3  call    ??$LoadDpapiCredKeyFromUserProfileIfPresent@AEA_NAEA_N_NAEAJ@CloudAPProvider@@SAXAEA_N0$$QEA_NAEAJ@Z; CloudAPProvider::LoadDpapiCredKeyFromUserProfileIfPresent<bool &,bool &,bool,long &>(bool &,bool &,bool &&,long &)
0x180010da8  movzx   r8d, bx
0x180010dac  mov     r9d, r8d
0x180010daf  or      r9d, 0C0070000h
0x180010db6  mov     eax, r8d
0x180010db9  test    r8d, r8d
0x180010dbc  cmovnz  eax, r9d
0x180010dc0  test    eax, eax
0x180010dc2  jz      short loc_180010E10
0x180010dc4  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180010dcb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010dd0  test    r8d, r8d
0x180010dd3  cmovnz  r8d, r9d
0x180010dd7  lea     rsi, Class
0x180010dde  mov     [rsp+2B0h+var_280], rsi
0x180010de3  lea     rcx, aLoaddpapicredk; "LoadDpapiCredKeyFromUserProfileIfPresen"...
0x180010dea  mov     [rsp+2B0h+var_288], rcx
0x180010def  mov     dword ptr [rsp+2B0h+var_290], 71Fh
0x180010df7  mov     r9, rax
0x180010dfa  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180010e01  xor     ecx, ecx
0x180010e03  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180010e08  xor     r13d, r13d
0x180010e0b  jmp     loc_180011150
0x180010e10  movzx   ebx, [rsp+2B0h+var_26F]
0x180010e15  cmp     [rsp+2B0h+var_270], 0
0x180010e1a  jz      short loc_180010E35
0x180010e1c  mov     r15, [rdi+110h]
0x180010e23  xor     r13d, r13d
0x180010e26  mov     [rdi+110h], r13
0x180010e2d  jmp     loc_180011084
0x180010e32  xor     r13b, r13b
0x180010e35  test    r15d, r15d
0x180010e38  jnz     short loc_180010E6F
0x180010e3a  xor     r15d, r15d
0x180010e3d  mov     rcx, [rdi+110h]
0x180010e44  test    rcx, rcx
0x180010e47  jz      loc_180011081
0x180010e4d  mov     rdx, [rdi+108h]
0x180010e54  add     rdx, 10h; Uuid2
0x180010e58  add     rcx, 10h; Uuid1
0x180010e5c  lea     r8, [rsp+2B0h+Status]; Status
0x180010e61  call    cs:__imp_UuidEqual
0x180010e67  test    eax, eax
0x180010e69  jnz     loc_180011081
0x180010e6f  mov     rcx, [rdi+18h]
0x180010e73  add     rcx, 18h; Resource
0x180010e77  call    SCLockConvertExclusiveToShared
0x180010e7c  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x180010e83  mov     r9, [rdi+110h]
0x180010e8a  mov     r8, [rdi+108h]
0x180010e91  mov     r15, [rsp+2B0h+var_258]
0x180010e96  mov     rdx, r15
0x180010e99  mov     rcx, [rsi+10h]
0x180010e9d  mov     rax, [rax+38h]
0x180010ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ea6  mov     r14d, eax
0x180010ea9  mov     [rsp+2B0h+var_268], eax
0x180010ead  mov     r8, [rdi+110h]
0x180010eb4  test    r8, r8
0x180010eb7  jz      short loc_180010EBF
0x180010eb9  add     r8, 10h
0x180010ebd  jmp     short loc_180010EC2
0x180010ebf  mov     r8, r12
0x180010ec2  mov     rax, [rdi+108h]
0x180010ec9  test    rax, rax
0x180010ecc  lea     rdx, [rax+10h]
0x180010ed0  jnz     short loc_180010ED5
0x180010ed2  mov     rdx, r12
0x180010ed5  lea     rcx, [rsp+2B0h+var_268]
0x180010eda  call    ??$NotifyDpapiToUpdateCurrentUserKey@AEAJAEAU_GUID@@AEAU1@@CloudAPProvider@@SAXAEAJAEAU_GUID@@1@Z; CloudAPProvider::NotifyDpapiToUpdateCurrentUserKey<long &,_GUID &,_GUID &>(long &,_GUID &,_GUID &)
0x180010edf  test    r14d, r14d
0x180010ee2  jns     short loc_180010F25
0x180010ee4  mov     rcx, [rdi+18h]
0x180010ee8  add     rcx, 18h; Resource
0x180010eec  call    SCLockConvertSharedToExclusive
0x180010ef1  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180010ef8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010efd  lea     rsi, Class
0x180010f04  mov     [rsp+2B0h+var_280], rsi
0x180010f09  lea     rcx, aUpdatecredenti_1; "UpdateCredentialKey"
0x180010f10  mov     [rsp+2B0h+var_288], rcx
0x180010f15  mov     dword ptr [rsp+2B0h+var_290], 747h
0x180010f1d  mov     r8d, r14d
0x180010f20  jmp     loc_180010DF7
0x180010f25  lea     r9, [rdi+118h]; struct _AP_BLOB *
0x180010f2c  mov     r8, [rdi+110h]; struct _CREDENTIAL_KEY *
0x180010f33  mov     rdx, [rdi+108h]; struct _CREDENTIAL_KEY *
0x180010f3a  mov     rbx, [rsp+2B0h+var_250]
0x180010f3f  mov     rcx, rbx; struct _CloudAPCache *
0x180010f42  call    ?UpdateDPAPICredKey@@YAJPEAU_CloudAPCache@@PEAU_CREDENTIAL_KEY@@1PEAU_AP_BLOB@@@Z; UpdateDPAPICredKey(_CloudAPCache *,_CREDENTIAL_KEY *,_CREDENTIAL_KEY *,_AP_BLOB *)
0x180010f47  mov     r14d, eax
0x180010f4a  test    eax, eax
0x180010f4c  jns     loc_18001102E
0x180010f52  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x180010f59  mov     r9, [rdi+108h]
0x180010f60  mov     r8, [rdi+110h]
0x180010f67  mov     rdx, r15
0x180010f6a  mov     rcx, [rsi+10h]
0x180010f6e  mov     rax, [rax+38h]
0x180010f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f77  mov     r15d, eax
0x180010f7a  mov     [rsp+2B0h+var_268], eax
0x180010f7e  mov     r8, [rdi+108h]
0x180010f85  test    r8, r8
0x180010f88  jz      short loc_180010F90
0x180010f8a  add     r8, 10h
0x180010f8e  jmp     short loc_180010F93
0x180010f90  mov     r8, r12
0x180010f93  mov     rax, [rdi+110h]
0x180010f9a  test    rax, rax
0x180010f9d  jz      short loc_180010FA3
0x180010f9f  lea     r12, [rax+10h]
0x180010fa3  mov     rdx, r12
0x180010fa6  lea     rcx, [rsp+2B0h+var_268]
0x180010fab  call    ??$NotifyDpapiToUpdateUserKeyRollBack@AEAJAEAU_GUID@@AEAU1@@CloudAPProvider@@SAXAEAJAEAU_GUID@@1@Z; CloudAPProvider::NotifyDpapiToUpdateUserKeyRollBack<long &,_GUID &,_GUID &>(long &,_GUID &,_GUID &)
0x180010fb0  lea     rbx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180010fb7  lea     rsi, Class
0x180010fbe  test    r15d, r15d
0x180010fc1  jz      short loc_180010FF8
0x180010fc3  mov     rcx, rbx; char *
0x180010fc6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010fcb  mov     [rsp+2B0h+var_280], rsi
0x180010fd0  lea     rcx, aUpdatecredenti; "UpdateCredentialKey(RollBack)"
0x180010fd7  mov     [rsp+2B0h+var_288], rcx
0x180010fdc  mov     dword ptr [rsp+2B0h+var_290], 75Eh
0x180010fe4  mov     r9, rax
0x180010fe7  mov     r8d, r15d
0x180010fea  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180010ff1  xor     ecx, ecx
0x180010ff3  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180010ff8  mov     rcx, [rdi+18h]
0x180010ffc  add     rcx, 18h; Resource
0x180011000  call    SCLockConvertSharedToExclusive
0x180011005  mov     rcx, rbx; char *
0x180011008  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001100d  mov     [rsp+2B0h+var_280], rsi
  ... truncated ...
```
