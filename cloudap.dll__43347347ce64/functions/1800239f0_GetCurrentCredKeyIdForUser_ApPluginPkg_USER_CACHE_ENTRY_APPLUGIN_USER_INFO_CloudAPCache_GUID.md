# GetCurrentCredKeyIdForUser(_ApPluginPkg *,_USER_CACHE_ENTRY *,_APPLUGIN_USER_INFO *,_CloudAPCache *,_GUID *)

- ea: `0x1800239f0`
- end: `0x180023f22`
- name: `?GetCurrentCredKeyIdForUser@@YAJPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@PEAU_APPLUGIN_USER_INFO@@PEAU_CloudAPCache@@PEAU_GUID@@@Z`
- size: `1330`
- prototype: `__int64 __fastcall(struct _ApPluginPkg *, struct _USER_CACHE_ENTRY *, struct _APPLUGIN_USER_INFO *, struct _CloudAPCache *, struct _GUID *Uuid1)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001f8f0`
- `0x180037240`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x1800239f0`
- `0x1800528c0`
- `0x180053cbc`
- `0x180081010`

## import_xrefs

- `RPCRT4!UuidEqual` at `0x180023bc4`
- `RPCRT4!UuidEqual` at `0x180023bc4`

## string_xrefs

- `0x180023a1d`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180023b7b`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180023c38`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180023cb5`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180023dac`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180023d5e`: `Cache not found for surrogate plugin`
- `0x180023ed4`: `GetCredKeyIdFromCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCurrentCredKeyIdForUser(
        struct _ApPluginPkg *a1,
        struct _USER_CACHE_ENTRY *a2,
        struct _APPLUGIN_USER_INFO *a3,
        struct _CloudAPCache *a4,
        struct _GUID *Uuid1)
{
  struct _GUID *v5; // rsi
  int v7; // eax
  _DWORD *v8; // rcx
  const char *v9; // rdi
  int v10; // r12d
  unsigned int CredKeyIdFromCache; // ebx
  const char *v12; // r9
  const char *v13; // rax
  bool v14; // zf
  struct _USER_CACHE_ENTRY *v15; // r12
  __int64 v16; // rcx
  const char *v18; // rax
  bool v19; // zf
  const char *v20; // rax
  bool v21; // zf
  const char *v22; // rax
  bool v23; // zf
  const char *v24; // rax
  __int64 v25; // r8
  __int64 v26; // r10
  const char *v27; // r9
  const char *v28; // rax
  __int64 v29; // r8
  const char *v30; // rax
  const char *v31; // rax
  struct _GUID *v32; // rax
  const char *v33; // r9
  const char *v34; // r9
  __int64 v35; // [rsp+20h] [rbp-48h]
  __int64 v36; // [rsp+20h] [rbp-48h]
  RPC_STATUS Status; // [rsp+40h] [rbp-28h] BYREF
  _DWORD *v38; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v39[3]; // [rsp+50h] [rbp-18h] BYREF
  int v40; // [rsp+B0h] [rbp+48h] BYREF
  struct _USER_CACHE_ENTRY *v41; // [rsp+B8h] [rbp+50h]
  struct _APPLUGIN_USER_INFO *v42; // [rsp+C0h] [rbp+58h]
  struct _CloudAPCache *v43; // [rsp+C8h] [rbp+60h]

  v43 = a4;
  v42 = a3;
  v41 = a2;
  v5 = Uuid1;
  Status = 0;
  v40 = 0;
  v39[0] = 0;
  *Uuid1 = stru_180085DB8;
  *v5 = stru_180085DB8;
  v7 = *((_DWORD *)a1 + 40);
  if ( (v7 & 4) != 0 )
  {
    if ( a4 )
    {
      v15 = v41;
      *v5 = *(struct _GUID *)((char *)a4 + 4);
      goto LABEL_22;
    }
    CredKeyIdFromCache = -1073283070;
    v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v25, v24, 2192, "Cache not found for surrogate plugin", v26);
    goto LABEL_38;
  }
  v8 = 0;
  LODWORD(Uuid1) = 0;
  v38 = 0;
  v9 = "";
  if ( (v7 & 1) != 0 )
  {
    LOBYTE(v10) = 0;
    CredKeyIdFromCache = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _DWORD **, struct _GUID **))g_pLsaIdProvHostFunctionTable
                          + 4))(
                           *((_QWORD *)a1 + 2),
                           *((_QWORD *)a2 + 12),
                           0,
                           6,
                           &v38,
                           &Uuid1);
    if ( CredKeyIdFromCache )
    {
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
      LODWORD(v35) = 2093;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CredKeyIdFromCache, v12, v35, "LookUpUserInfo", &Class);
      goto LABEL_11;
    }
    if ( (_DWORD)Uuid1 != 4 )
    {
      CredKeyIdFromCache = -1073741595;
      v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v35) = 2098;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v27, v35, "No shadow account", &Class);
LABEL_11:
      v8 = v38;
      goto LABEL_15;
    }
    v8 = v38;
    v10 = *v38;
  }
  else
  {
    LOBYTE(v10) = 2;
  }
  CredKeyIdFromCache = 0;
LABEL_15:
  if ( v8 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( CredKeyIdFromCache )
  {
    while ( 1 )
    {
      v18 = v9--;
      v19 = *v9 == 92;
      if ( *v9 == 92 )
        break;
      if ( v9 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v19 = *v9 == 92;
        break;
      }
    }
    if ( v19 )
      v9 = v18;
    LODWORD(v35) = 2207;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CredKeyIdFromCache, v9, v35, "GetUserType", &Class);
    goto LABEL_38;
  }
  if ( (v10 & 2) == 0 )
  {
    CredKeyIdFromCache = -1073283070;
    v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(v35) = 2235;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v29, v28, v35, "No Cred Key for an unverified account", &Class);
LABEL_38:
    v15 = v41;
    goto LABEL_23;
  }
  v15 = v41;
  if ( (*((_BYTE *)a1 + 160) & 1) != 0 )
  {
    CredKeyIdFromCache = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _QWORD *, int *))g_pLsaIdProvHostFunctionTable
                          + 4))(
                           *((_QWORD *)a1 + 2),
                           *((_QWORD *)v41 + 12),
                           0,
                           14,
                           v39,
                           &v40);
    if ( CredKeyIdFromCache )
    {
      while ( 1 )
      {
        v20 = v9--;
        v21 = *v9 == 92;
        if ( *v9 == 92 )
          break;
        if ( v9 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v21 = *v9 == 92;
          break;
        }
      }
      if ( v21 )
        v9 = v20;
      LODWORD(v35) = 2220;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CredKeyIdFromCache, v9, v35, "LookUpUserInfo", &Class);
      goto LABEL_23;
    }
    v16 = v39[0];
  }
  else
  {
    v16 = *((_QWORD *)v42 + 2);
  }
  CredKeyIdFromCache = (*((__int64 (__fastcall **)(__int64, struct _GUID *))g_pLsaIdProvHostFunctionTable + 11))(
                         v16,
                         v5);
  if ( !CredKeyIdFromCache )
  {
LABEL_22:
    CredKeyIdFromCache = 0;
    goto LABEL_23;
  }
  while ( 1 )
  {
    v22 = v9--;
    v23 = *v9 == 92;
    if ( *v9 == 92 )
      break;
    if ( v9 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
    {
      v23 = *v9 == 92;
      break;
    }
  }
  if ( v23 )
    v9 = v22;
  LODWORD(v35) = 2230;
  WPPTraceLogA(
    0,
    "0x%08x %s:%u : %s:%ws",
    CredKeyIdFromCache,
    v9,
    v35,
    "g_pLsaIdProvHostFunctionTable->GetCurrentCredKeyIdForUser",
    &Class);
LABEL_23:
  if ( v39[0] )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( (CredKeyIdFromCache & 0x80000000) == 0 )
  {
    if ( !UuidEqual(v5, (UUID *)&stru_180085DB8, &Status) )
      return 0;
    CredKeyIdFromCache = -1073741116;
    v30 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(v35) = 2280;
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      3221226180LL,
      v30,
      v35,
      "GetCurrentCredKeyIdForUserFromDPAPI:CREDHIST from DPAPI returned empty GUID!",
      &Class);
    CloudAPProvider::CloudApDPAPICredHistZero();
  }
  v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  LODWORD(v35) = 2288;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CredKeyIdFromCache, v31, v35, "GetCurrentCredKeyIdForUserFromDPAPI", &Class);
  if ( CredKeyIdFromCache == -1073283058 || CredKeyIdFromCache == -1073283064 )
  {
    CredKeyIdFromCache = -1073741801;
LABEL_66:
    v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(v36) = 2298;
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      CredKeyIdFromCache,
      v34,
      v36,
      "GetCurrentCredKeyIdForUserFromDPAPI",
      &Class);
    return CredKeyIdFromCache;
  }
  if ( CredKeyIdFromCache == -1073741801 || CredKeyIdFromCache == -1073741670 )
    goto LABEL_66;
  v32 = (struct _GUID *)*((_QWORD *)v15 + 33);
  if ( v32 )
  {
    *v5 = v32[1];
  }
  else
  {
    CredKeyIdFromCache = GetCredKeyIdFromCache(a1, v15, v43, v5);
    if ( CredKeyIdFromCache )
    {
      v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v36) = 2322;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CredKeyIdFromCache, v33, v36, "GetCredKeyIdFromCache", &Class);
      return CredKeyIdFromCache;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800239f0  mov     r11, rsp
0x1800239f3  mov     [r11+20h], r9
0x1800239f7  mov     [r11+18h], r8
0x1800239fb  mov     [r11+10h], rdx
0x1800239ff  push    rbp
0x180023a00  push    rbx
0x180023a01  push    rsi
0x180023a02  push    rdi
0x180023a03  push    r12
0x180023a05  push    r13
0x180023a07  push    r14
0x180023a09  push    r15
0x180023a0b  mov     rbp, rsp
0x180023a0e  sub     rsp, 68h
0x180023a12  movups  xmm0, xmmword ptr cs:stru_180085DB8.Data1
0x180023a19  mov     rsi, [rbp+Uuid1]
0x180023a1d  lea     r15, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180023a24  mov     r13, rcx
0x180023a27  mov     [rbp+Status], 0
0x180023a2e  mov     [rbp+arg_0], 0
0x180023a35  lea     r10, Class
0x180023a3c  mov     [rbp+var_18], 0
0x180023a44  movdqu  xmmword ptr [rsi], xmm0
0x180023a48  movups  xmm0, xmmword ptr cs:stru_180085DB8.Data1
0x180023a4f  movdqu  xmmword ptr [rsi], xmm0
0x180023a53  mov     eax, [rcx+0A0h]
0x180023a59  test    al, 4
0x180023a5b  jnz     loc_180023C9A
0x180023a61  xor     ecx, ecx
0x180023a63  mov     dword ptr [rbp+Uuid1], 0
0x180023a6a  mov     [rbp+var_20], rcx
0x180023a6e  lea     rdi, aOnecoreDsExtCl_6+27h; ""
0x180023a75  test    al, 1
0x180023a77  jz      loc_180023C2D
0x180023a7d  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x180023a84  lea     rcx, [rbp+Uuid1]
0x180023a88  mov     rdx, [rdx+60h]
0x180023a8c  xor     r12d, r12d
0x180023a8f  mov     [r11-80h], rcx
0x180023a93  xor     r8d, r8d
0x180023a96  lea     rcx, [rbp+var_20]
0x180023a9a  mov     rax, [rax+20h]
0x180023a9e  mov     [rsp+68h+var_48], rcx
0x180023aa3  lea     r9d, [r12+6]
0x180023aa8  mov     rcx, [r13+10h]
0x180023aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ab1  mov     ebx, eax
0x180023ab3  test    eax, eax
0x180023ab5  jz      short loc_180023B0A
0x180023ab7  mov     r9, rdi
0x180023aba  mov     rax, r9
0x180023abd  dec     r9
0x180023ac0  cmp     byte ptr [r9], 5Ch ; '\'
0x180023ac4  jz      short loc_180023ACF
0x180023ac6  cmp     r9, r15
0x180023ac9  ja      short loc_180023ABA
0x180023acb  cmp     byte ptr [r9], 5Ch ; '\'
0x180023acf  cmovz   r9, rax
0x180023ad3  lea     rax, Class
0x180023ada  mov     [rsp+68h+var_38], rax
0x180023adf  lea     rax, aLookupuserinfo; "LookUpUserInfo"
0x180023ae6  mov     [rsp+68h+var_40], rax
0x180023aeb  mov     dword ptr [rsp+68h+var_48], 82Dh
0x180023af3  mov     r8d, ebx
0x180023af6  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180023afd  xor     ecx, ecx
0x180023aff  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180023b04  mov     rcx, [rbp+var_20]
0x180023b08  jmp     short loc_180023B1D
0x180023b0a  cmp     dword ptr [rbp+Uuid1], 4
0x180023b0e  jnz     loc_180023D77
0x180023b14  mov     rcx, [rbp+var_20]
0x180023b18  mov     r12d, [rcx]
0x180023b1b  xor     ebx, ebx
0x180023b1d  mov     r14d, 60h ; '`'
0x180023b23  lea     r15d, [r14-50h]
0x180023b27  test    rcx, rcx
0x180023b2a  jz      short loc_180023B3C
0x180023b2c  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180023b33  mov     rax, [rax+30h]
0x180023b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b3c  test    ebx, ebx
0x180023b3e  jnz     loc_180023C38
0x180023b44  test    r12b, 2
0x180023b48  jz      loc_180023DAC
0x180023b4e  test    byte ptr [r13+0A0h], 1
0x180023b56  mov     r12, [rbp+arg_8]
0x180023b5a  jnz     loc_180023BE7
0x180023b60  mov     rcx, [rbp+arg_10]
0x180023b64  mov     rcx, [rcx+10h]
0x180023b68  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x180023b6f  mov     rdx, rsi
0x180023b72  mov     rax, [rax+58h]
0x180023b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b7b  lea     r15, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180023b82  mov     ebx, eax
0x180023b84  test    eax, eax
0x180023b86  jnz     loc_180023D0C
0x180023b8c  xor     ebx, ebx
0x180023b8e  lea     rdi, Class
0x180023b95  mov     rcx, [rbp+var_18]
0x180023b99  test    rcx, rcx
0x180023b9c  jz      short loc_180023BAE
0x180023b9e  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180023ba5  mov     rax, [rax+30h]
0x180023ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bae  test    ebx, ebx
0x180023bb0  js      loc_180023E39
0x180023bb6  lea     r8, [rbp+Status]; Status
0x180023bba  mov     rcx, rsi; Uuid1
0x180023bbd  lea     rdx, stru_180085DB8; Uuid2
0x180023bc4  call    cs:__imp_UuidEqual
0x180023bca  test    eax, eax
0x180023bcc  jnz     loc_180023DFA
0x180023bd2  xor     ebx, ebx
0x180023bd4  mov     eax, ebx
0x180023bd6  add     rsp, 68h
0x180023bda  pop     r15
0x180023bdc  pop     r14
0x180023bde  pop     r13
0x180023be0  pop     r12
0x180023be2  pop     rdi
0x180023be3  pop     rsi
0x180023be4  pop     rbx
0x180023be5  pop     rbp
0x180023be6  retn
0x180023be7  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x180023bee  lea     rcx, [rbp+arg_0]
0x180023bf2  mov     rdx, [r14+r12]
0x180023bf6  mov     r9d, 0Eh
0x180023bfc  mov     [rsp+68h+var_40], rcx
0x180023c01  xor     r8d, r8d
0x180023c04  lea     rcx, [rbp+var_18]
0x180023c08  mov     rax, [rax+20h]
0x180023c0c  mov     [rsp+68h+var_48], rcx
0x180023c11  mov     rcx, [r15+r13]
0x180023c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c1a  mov     ebx, eax
0x180023c1c  test    eax, eax
0x180023c1e  jnz     loc_180023CB5
0x180023c24  mov     rcx, [rbp+var_18]
0x180023c28  jmp     loc_180023B68
0x180023c2d  mov     r12d, 2
0x180023c33  jmp     loc_180023B1B
0x180023c38  lea     r15, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180023c3f  mov     rax, rdi
0x180023c42  dec     rdi
0x180023c45  cmp     byte ptr [rdi], 5Ch ; '\'
0x180023c48  jz      short loc_180023C52
0x180023c4a  cmp     rdi, r15
0x180023c4d  ja      short loc_180023C3F
0x180023c4f  cmp     byte ptr [rdi], 5Ch ; '\'
0x180023c52  cmovz   rdi, rax
0x180023c56  mov     r8d, ebx
0x180023c59  lea     rax, Class
0x180023c60  mov     r9, rdi
0x180023c63  mov     [rsp+68h+var_38], rax
0x180023c68  lea     rax, aGetusertype; "GetUserType"
0x180023c6f  mov     [rsp+68h+var_40], rax
0x180023c74  mov     dword ptr [rsp+68h+var_48], 89Fh
0x180023c7c  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180023c83  xor     ecx, ecx
0x180023c85  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180023c8a  lea     rdi, Class
0x180023c91  mov     r12, [rbp+arg_8]
0x180023c95  jmp     loc_180023B95
0x180023c9a  test    r9, r9
0x180023c9d  jz      loc_180023D45
0x180023ca3  movups  xmm0, xmmword ptr [r9+4]
0x180023ca8  mov     r12, [rbp+arg_8]
0x180023cac  movdqu  xmmword ptr [rsi], xmm0
0x180023cb0  jmp     loc_180023B8C
0x180023cb5  lea     r15, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180023cbc  mov     rax, rdi
0x180023cbf  dec     rdi
0x180023cc2  cmp     byte ptr [rdi], 5Ch ; '\'
0x180023cc5  jz      short loc_180023CCF
0x180023cc7  cmp     rdi, r15
0x180023cca  ja      short loc_180023CBC
0x180023ccc  cmp     byte ptr [rdi], 5Ch ; '\'
0x180023ccf  cmovz   rdi, rax
0x180023cd3  lea     rax, Class
0x180023cda  mov     [rsp+68h+var_38], rax
0x180023cdf  lea     rax, aLookupuserinfo; "LookUpUserInfo"
0x180023ce6  mov     [rsp+68h+var_40], rax
0x180023ceb  mov     dword ptr [rsp+68h+var_48], 8ACh
0x180023cf3  mov     r9, rdi
0x180023cf6  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180023cfd  mov     r8d, ebx
0x180023d00  xor     ecx, ecx
0x180023d02  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180023d07  jmp     loc_180023B8E
0x180023d0c  mov     rax, rdi
0x180023d0f  dec     rdi
0x180023d12  cmp     byte ptr [rdi], 5Ch ; '\'
0x180023d15  jz      short loc_180023D1F
0x180023d17  cmp     rdi, r15
0x180023d1a  ja      short loc_180023D0C
0x180023d1c  cmp     byte ptr [rdi], 5Ch ; '\'
0x180023d1f  cmovz   rdi, rax
0x180023d23  lea     rax, Class
0x180023d2a  mov     [rsp+68h+var_38], rax
0x180023d2f  lea     rax, aGPlsaidprovhos; "g_pLsaIdProvHostFunctionTable->GetCurre"...
0x180023d36  mov     [rsp+68h+var_40], rax
0x180023d3b  mov     dword ptr [rsp+68h+var_48], 8B6h
0x180023d43  jmp     short loc_180023CF3
0x180023d45  mov     r8d, 0C0070002h
0x180023d4b  mov     rcx, r15; char *
0x180023d4e  mov     ebx, r8d
0x180023d51  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180023d56  mov     [rsp+68h+var_38], r10
0x180023d5b  mov     r9, rax
0x180023d5e  lea     rax, aCacheNotFoundF; "Cache not found for surrogate plugin"
0x180023d65  mov     [rsp+68h+var_40], rax
0x180023d6a  mov     dword ptr [rsp+68h+var_48], 890h
0x180023d72  jmp     loc_180023C7C
0x180023d77  mov     rcx, r15; char *
0x180023d7a  mov     ebx, 0C00000E5h
0x180023d7f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180023d84  mov     r9, rax
0x180023d87  lea     rax, Class
0x180023d8e  mov     [rsp+68h+var_38], rax
0x180023d93  lea     rax, aNoShadowAccoun; "No shadow account"
0x180023d9a  mov     [rsp+68h+var_40], rax
0x180023d9f  mov     dword ptr [rsp+68h+var_48], 832h
0x180023da7  jmp     loc_180023AF3
0x180023dac  lea     r15, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180023db3  mov     r8d, 0C0070002h
0x180023db9  mov     rcx, r15; char *
0x180023dbc  mov     ebx, r8d
0x180023dbf  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180023dc4  mov     r9, rax
0x180023dc7  lea     rdi, Class
0x180023dce  lea     rax, aNoCredKeyForAn; "No Cred Key for an unverified account"
0x180023dd5  mov     [rsp+68h+var_38], rdi
0x180023dda  mov     [rsp+68h+var_40], rax
0x180023ddf  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180023de6  xor     ecx, ecx
0x180023de8  mov     dword ptr [rsp+68h+var_48], 8BBh
0x180023df0  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180023df5  jmp     loc_180023C91
0x180023dfa  mov     rcx, r15; char *
0x180023dfd  mov     ebx, 0C00002C4h
0x180023e02  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180023e07  mov     r9, rax
0x180023e0a  mov     [rsp+68h+var_38], rdi
0x180023e0f  lea     rax, aGetcurrentcred_1; "GetCurrentCredKeyIdForUserFromDPAPI:CRE"...
0x180023e16  mov     r8d, ebx
0x180023e19  mov     [rsp+68h+var_40], rax
0x180023e1e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180023e25  xor     ecx, ecx
0x180023e27  mov     dword ptr [rsp+68h+var_48], 8E8h
0x180023e2f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180023e34  call    ?CloudApDPAPICredHistZero@CloudAPProvider@@SAXXZ; CloudAPProvider::CloudApDPAPICredHistZero(void)
0x180023e39  mov     rcx, r15; char *
0x180023e3c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180023e41  mov     [rsp+68h+var_38], rdi
0x180023e46  lea     r14, aGetcurrentcred; "GetCurrentCredKeyIdForUserFromDPAPI"
0x180023e4d  mov     [rsp+68h+var_40], r14
0x180023e52  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180023e59  mov     r9, rax
0x180023e5c  mov     dword ptr [rsp+68h+var_48], 8F0h
0x180023e64  mov     r8d, ebx
0x180023e67  xor     ecx, ecx
0x180023e69  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180023e6e  cmp     ebx, 0C007000Eh
0x180023e74  jz      short loc_180023EEA
0x180023e76  cmp     ebx, 0C0070008h
0x180023e7c  jz      short loc_180023EEA
0x180023e7e  cmp     ebx, 0C0000017h
0x180023e84  jz      short loc_180023EEF
0x180023e86  cmp     ebx, 0C000009Ah
0x180023e8c  jz      short loc_180023EEF
0x180023e8e  mov     rax, [r12+108h]
0x180023e96  test    rax, rax
0x180023e99  jz      short loc_180023EA8
0x180023e9b  movups  xmm0, xmmword ptr [rax+10h]
0x180023e9f  movdqu  xmmword ptr [rsi], xmm0
0x180023ea3  jmp     loc_180023BD2
0x180023ea8  mov     r8, [rbp+arg_18]; struct _CloudAPCache *
0x180023eac  mov     r9, rsi; struct _GUID *
0x180023eaf  mov     rdx, r12; struct _USER_CACHE_ENTRY *
0x180023eb2  mov     rcx, r13; struct _ApPluginPkg *
0x180023eb5  call    ?GetCredKeyIdFromCache@@YAJPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@PEAU_CloudAPCache@@PEAU_GUID@@@Z; GetCredKeyIdFromCache(_ApPluginPkg *,_USER_CACHE_ENTRY *,_CloudAPCache *,_GUID *)
0x180023eba  mov     ebx, eax
0x180023ebc  test    eax, eax
0x180023ebe  jz      loc_180023BD2
0x180023ec4  mov     rcx, r15; char *
0x180023ec7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180023ecc  mov     [rsp+68h+var_38], rdi
0x180023ed1  mov     r9, rax
0x180023ed4  lea     rax, aGetcredkeyidfr; "GetCredKeyIdFromCache"
0x180023edb  mov     [rsp+68h+var_40], rax
0x180023ee0  mov     dword ptr [rsp+68h+var_48], 912h
0x180023ee8  jmp     short loc_180023F0C
0x180023eea  mov     ebx, 0C0000017h
0x180023eef  mov     rcx, r15; char *
0x180023ef2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180023ef7  mov     [rsp+68h+var_38], rdi
0x180023efc  mov     r9, rax
  ... truncated ...
```
