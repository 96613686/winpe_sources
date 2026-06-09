# PostLogonProcessingForShadowAccounts(_ApPluginPkg *,_USER_CACHE_ENTRY *,_APPLUGIN_USER_INFO *,_DPAPI_DECODED_AUTH_DATA *,bool)

- ea: `0x1800243d0`
- end: `0x180024a6e`
- name: `?PostLogonProcessingForShadowAccounts@@YAJPEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@PEAU_APPLUGIN_USER_INFO@@PEAU_DPAPI_DECODED_AUTH_DATA@@_N@Z`
- size: `1694`
- prototype: `__int64 __usercall@<rax>(struct _ApPluginPkg *@<rcx>, struct _USER_CACHE_ENTRY *@<rdx>, struct _APPLUGIN_USER_INFO *@<r8>, struct _DPAPI_DECODED_AUTH_DATA *@<r9>, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180011960`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x1800243d0`
- `0x180059560`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024645`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002463b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002463b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a4e`

## string_xrefs

- `0x180024405`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800245a1`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18002465a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800246d6`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180024752`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800247a3`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800247dd`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180024842`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800248ca`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180024905`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180024950`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180024675`: `ConvertSidToStringSidW`
- `0x180024980`: `UpdateCredentialScore`
- `0x1800249c0`: `UpdateCredentialScore`

## pseudocode

```c
__int64 __fastcall PostLogonProcessingForShadowAccounts(
        struct _ApPluginPkg *a1,
        struct _USER_CACHE_ENTRY *a2,
        struct _APPLUGIN_USER_INFO *a3,
        struct _DPAPI_DECODED_AUTH_DATA *a4,
        bool a5)
{
  const char *v6; // rdi
  int *v8; // rcx
  int v9; // r14d
  unsigned int updated; // ebx
  const char *v11; // r9
  char v12; // al
  const char *v13; // rcx
  bool v14; // zf
  char v15; // al
  char v17; // al
  const char *v18; // rcx
  bool v19; // zf
  const char *v20; // r9
  signed int LastError; // eax
  const char *v22; // r9
  __int64 v23; // rcx
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  const char *v28; // r9
  __int64 v29; // r9
  __int64 v30; // rax
  const char *v31; // r9
  const char *v32; // r9
  struct _DPAPI_DECODED_AUTH_DATA *v33; // rdi
  const char *v34; // rax
  const char *v35; // r9
  int v36; // ecx
  const char *v37; // r9
  __int64 v38; // [rsp+28h] [rbp-41h]
  __int64 v39; // [rsp+28h] [rbp-41h]
  __int64 v40; // [rsp+28h] [rbp-41h]
  __int64 v41; // [rsp+28h] [rbp-41h]
  int v42; // [rsp+48h] [rbp-21h] BYREF
  int *v43; // [rsp+50h] [rbp-19h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp-11h] BYREF
  __int64 v45; // [rsp+60h] [rbp-9h] BYREF
  _QWORD v46[4]; // [rsp+68h] [rbp-1h] BYREF
  int v47; // [rsp+C8h] [rbp+5Fh] BYREF
  struct _APPLUGIN_USER_INFO *v48; // [rsp+D8h] [rbp+6Fh]
  struct _DPAPI_DECODED_AUTH_DATA *v49; // [rsp+E0h] [rbp+77h]

  v49 = a4;
  v48 = a3;
  v6 = "";
  v14 = (*((_BYTE *)a1 + 160) & 1) == 0;
  v8 = 0;
  v43 = 0;
  memset(v46, 0, sizeof(v46));
  v42 = 0;
  StringSid = 0;
  v45 = 0;
  v47 = 0;
  if ( v14 )
  {
    v9 = 2;
  }
  else
  {
    v9 = 0;
    updated = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int **, int *))g_pLsaIdProvHostFunctionTable
               + 4))(
                *((_QWORD *)a1 + 2),
                *((_QWORD *)a2 + 12),
                0,
                6,
                &v43,
                &v47);
    if ( updated )
    {
      v11 = "";
      while ( 1 )
      {
        v12 = *(v11 - 1);
        v13 = v11--;
        v14 = v12 == 92;
        if ( v12 == 92 )
          break;
        if ( v11 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v14 = v12 == 92;
          break;
        }
      }
      if ( v14 )
        v11 = v13;
      LODWORD(v38) = 2093;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v11, v38, "LookUpUserInfo", &Class);
      goto LABEL_10;
    }
    if ( v47 != 4 )
    {
      updated = -1073741595;
      v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v38) = 2098;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v20, v38, "No shadow account", &Class);
LABEL_10:
      v8 = v43;
      goto LABEL_14;
    }
    v8 = v43;
    v9 = *v43;
  }
  updated = 0;
LABEL_14:
  if ( v8 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( updated )
  {
    while ( 1 )
    {
      v17 = *(v6 - 1);
      v18 = v6--;
      v19 = v17 == 92;
      if ( v17 == 92 )
        break;
      if ( v6 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v19 = v17 == 92;
        break;
      }
    }
    if ( v19 )
      v6 = v18;
    LODWORD(v38) = 6474;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v6, v38, "GetUserType", &Class);
  }
  else
  {
    if ( v9 == 1 )
    {
      if ( !ConvertSidToStringSidW(*((PSID *)v48 + 2), &StringSid) )
      {
        LastError = GetLastError();
        updated = LastError;
        if ( LastError > 0 )
          updated = (unsigned __int16)LastError | 0xC0070000;
        v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v38) = 6487;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v22, v38, "ConvertSidToStringSidW", &Class);
        goto LABEL_22;
      }
      v23 = -1;
      do
        v14 = StringSid[++v23] == 0;
      while ( !v14 );
      updated = (*((__int64 (__fastcall **)(_QWORD, _QWORD, __int64, LPWSTR, int))g_pLsaIdProvHostFunctionTable + 5))(
                  *((_QWORD *)a1 + 2),
                  *((_QWORD *)a2 + 12),
                  2,
                  StringSid,
                  2 * (int)v23 + 2);
      if ( updated )
      {
        v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v38) = 6496;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v24, v38, "SaveUserInfo", &Class);
        goto LABEL_22;
      }
      if ( *((_QWORD *)a1 + 37) )
      {
        updated = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64 *, int *))g_pLsaIdProvHostFunctionTable
                   + 4))(
                    *((_QWORD *)a1 + 2),
                    *((_QWORD *)a2 + 12),
                    0,
                    14,
                    &v45,
                    &v42);
        if ( updated )
        {
          v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v39) = 6509;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v25, v39, "LookUpUserInfo", &Class);
          goto LABEL_22;
        }
        updated = ((__int64 (__fastcall *)(_QWORD *))g_pLsaFunctionTable->GetClientInfo)(v46);
        if ( updated )
        {
          v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v39) = 6512;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v26, v39, "GetClientInfo", &Class);
          goto LABEL_22;
        }
        if ( (v46[2] & 0x1000000LL) != 0 )
        {
          updated = -1073741558;
          v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v39) = 6517;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225738LL, v27, v39, "Caller is terminating", &Class);
          goto LABEL_22;
        }
        updated = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, char *))a1 + 37))(
                    *((_QWORD *)a1 + 1),
                    0,
                    v46[3],
                    v45,
                    (char *)a2 + 280);
        if ( updated )
        {
          v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v38) = 6526;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v28, v38, "ConnectIdentity", &Class);
          goto LABEL_22;
        }
      }
      v29 = *((_QWORD *)v48 + 1);
      if ( v29 )
      {
        v30 = -1;
        do
          v14 = *(_WORD *)(v29 + 2 * v30++ + 2) == 0;
        while ( !v14 );
        updated = (*((__int64 (__fastcall **)(_QWORD, _QWORD, __int64))g_pLsaIdProvHostFunctionTable + 5))(
                    *((_QWORD *)a1 + 2),
                    *((_QWORD *)a2 + 12),
                    1);
        if ( updated )
        {
          v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v38) = 6537;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v31, v38, "SaveUserInfo(LIIC_UserUniqueId)", &Class);
          goto LABEL_22;
        }
      }
      v15 = 1;
    }
    else
    {
      v15 = 0;
      if ( !v9 )
      {
        updated = -1073741595;
        v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v38) = 6544;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v32, v38, "Unknown UserType", &Class);
        goto LABEL_22;
      }
    }
    if ( a5 && !v15 )
      goto LABEL_21;
    v33 = v49;
    updated = UpdateCredentialScore(a1, a2, v49);
    if ( (updated & 0x80000000) != 0
      && ((v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp"),
           LODWORD(v38) = 6563,
           WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v34, v38, "UpdateCredentialScore", &Class),
           updated == -1073741801)
       || updated == -1073741670) )
    {
      v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v40) = 6567;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v35, v40, "UpdateCredentialScore", &Class);
    }
    else
    {
      if ( *(_DWORD *)v33 != 1
        || (v36 = *((_DWORD *)v33 + 1)) == 0
        || (updated = (*((__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, int))g_pLsaIdProvHostFunctionTable + 5))(
                        *((_QWORD *)a1 + 2),
                        *((_QWORD *)a2 + 12),
                        4,
                        *((_QWORD *)v33 + 1),
                        v36)) == 0 )
      {
LABEL_21:
        updated = 0;
        goto LABEL_22;
      }
      v37 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v41) = 6581;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v37, v41, "SaveUserInfo(LIIC_ClearTextPassword)", &Class);
    }
  }
LABEL_22:
  if ( StringSid )
    LocalFree(StringSid);
  if ( v45 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  return updated;
}

```

## disassembly

```asm
0x1800243d0  mov     rax, rsp
0x1800243d3  mov     [rax+20h], r9
0x1800243d7  mov     [rax+18h], r8
0x1800243db  push    rbp
0x1800243dc  push    rbx
0x1800243dd  lea     rbp, [rax-57h]
0x1800243e1  sub     rsp, 0A8h
0x1800243e8  mov     [rax+10h], rsi
0x1800243ec  xorps   xmm0, xmm0
0x1800243ef  mov     [rax-18h], rdi
0x1800243f3  mov     rsi, rcx
0x1800243f6  mov     [rax-20h], r12
0x1800243fa  lea     rdi, aOnecoreDsExtCl_6+27h; ""
0x180024401  mov     [rax-28h], r13
0x180024405  lea     r12, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18002440c  mov     [rax-30h], r14
0x180024410  mov     r13, rdx
0x180024413  mov     [rax-38h], r15
0x180024417  xor     r15d, r15d
0x18002441a  test    byte ptr [rsi+0A0h], 1
0x180024421  mov     ecx, r15d
0x180024424  movups  [rbp+4Fh+var_4C], xmm0
0x180024428  mov     [rbp+4Fh+var_68], rcx
0x18002442c  mov     [rbp+4Fh+var_50], r15d
0x180024430  movups  [rbp+4Fh+var_4C+0Ch], xmm0
0x180024434  mov     [rbp+4Fh+var_70], r15d
0x180024438  mov     [rbp+4Fh+StringSid], r15
0x18002443c  mov     [rbp+4Fh+var_58], r15
0x180024440  mov     [rbp+4Fh+arg_0], r15d
0x180024444  jz      loc_180024596
0x18002444a  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x180024451  lea     rcx, [rbp+4Fh+arg_0]
0x180024455  mov     rdx, [rdx+60h]
0x180024459  mov     r9d, 6
0x18002445f  mov     [rsp+0B0h+var_88], rcx
0x180024464  xor     r8d, r8d
0x180024467  lea     rcx, [rbp+4Fh+var_68]
0x18002446b  mov     r14d, r15d
0x18002446e  mov     rax, [rax+20h]
0x180024472  mov     [rsp+0B0h+var_90], rcx
0x180024477  mov     rcx, [rsi+10h]
0x18002447b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024480  mov     ebx, eax
0x180024482  test    eax, eax
0x180024484  jz      short loc_1800244DA
0x180024486  mov     r9, rdi
0x180024489  movzx   eax, byte ptr [r9-1]
0x18002448e  mov     rcx, r9
0x180024491  dec     r9
0x180024494  cmp     al, 5Ch ; '\'
0x180024496  jz      short loc_18002449F
0x180024498  cmp     r9, r12
0x18002449b  ja      short loc_180024489
0x18002449d  cmp     al, 5Ch ; '\'
0x18002449f  lea     rax, Class
0x1800244a6  cmovz   r9, rcx
0x1800244aa  mov     [rsp+30h], rax
0x1800244af  lea     rax, aLookupuserinfo; "LookUpUserInfo"
0x1800244b6  mov     [rsp+0B0h+var_88], rax
0x1800244bb  mov     dword ptr [rsp+0B0h+var_90], 82Dh
0x1800244c3  mov     r8d, ebx
0x1800244c6  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800244cd  xor     ecx, ecx
0x1800244cf  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800244d4  mov     rcx, [rbp+4Fh+var_68]
0x1800244d8  jmp     short loc_1800244EE
0x1800244da  cmp     [rbp+4Fh+arg_0], 4
0x1800244de  jnz     loc_1800245FA
0x1800244e4  mov     rcx, [rbp+4Fh+var_68]
0x1800244e8  mov     r14d, [rcx]
0x1800244eb  mov     ebx, r15d
0x1800244ee  mov     r15d, 60h ; '`'
0x1800244f4  mov     r12d, 10h
0x1800244fa  test    rcx, rcx
0x1800244fd  jz      short loc_18002450F
0x1800244ff  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180024506  mov     rax, [rax+30h]
0x18002450a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002450f  test    ebx, ebx
0x180024511  jnz     loc_1800245A1
0x180024517  cmp     r14d, 1
0x18002451b  jz      loc_18002462F
0x180024521  xor     al, al
0x180024523  test    r14d, r14d
0x180024526  jz      loc_180024905
0x18002452c  cmp     [rbp+4Fh+arg_20], 0
0x180024530  jz      loc_18002493E
0x180024536  test    al, al
0x180024538  jnz     loc_18002493E
0x18002453e  xor     ebx, ebx
0x180024540  mov     rcx, [rbp+4Fh+StringSid]; hMem
0x180024544  mov     r15, [rsp+0B0h+var_30]
0x18002454c  mov     r14, [rsp+0B0h+var_28]
0x180024554  mov     r13, [rsp+0B0h+var_20]
0x18002455c  mov     r12, [rsp+0B0h+var_18]
0x180024564  mov     rdi, [rsp+0A0h]
0x18002456c  mov     rsi, [rsp+0B0h+arg_8]
0x180024574  test    rcx, rcx
0x180024577  jnz     loc_180024A4E
0x18002457d  mov     rcx, [rbp+4Fh+var_58]
0x180024581  test    rcx, rcx
0x180024584  jnz     loc_180024A59
0x18002458a  mov     eax, ebx
0x18002458c  add     rsp, 0A8h
0x180024593  pop     rbx
0x180024594  pop     rbp
0x180024595  retn
0x180024596  mov     r14d, 2
0x18002459c  jmp     loc_1800244EB
0x1800245a1  lea     r14, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800245a8  movzx   eax, byte ptr [rdi-1]
0x1800245ac  mov     rcx, rdi
0x1800245af  dec     rdi
0x1800245b2  cmp     al, 5Ch ; '\'
0x1800245b4  jz      short loc_1800245BD
0x1800245b6  cmp     rdi, r14
0x1800245b9  ja      short loc_1800245A8
0x1800245bb  cmp     al, 5Ch ; '\'
0x1800245bd  lea     rax, Class
0x1800245c4  cmovz   rdi, rcx
0x1800245c8  mov     [rsp+30h], rax
0x1800245cd  mov     r9, rdi
0x1800245d0  lea     rax, aGetusertype; "GetUserType"
0x1800245d7  mov     [rsp+0B0h+var_88], rax
0x1800245dc  mov     dword ptr [rsp+0B0h+var_90], 194Ah
0x1800245e4  mov     r8d, ebx
0x1800245e7  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800245ee  xor     ecx, ecx
0x1800245f0  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800245f5  jmp     loc_180024540
0x1800245fa  mov     rcx, r12; char *
0x1800245fd  mov     ebx, 0C00000E5h
0x180024602  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180024607  mov     r9, rax
0x18002460a  lea     rax, Class
0x180024611  mov     [rsp+30h], rax
0x180024616  lea     rax, aNoShadowAccoun; "No shadow account"
0x18002461d  mov     [rsp+0B0h+var_88], rax
0x180024622  mov     dword ptr [rsp+0B0h+var_90], 832h
0x18002462a  jmp     loc_1800244C3
0x18002462f  mov     rcx, [rbp+4Fh+arg_10]
0x180024633  lea     rdx, [rbp+4Fh+StringSid]; StringSid
0x180024637  mov     rcx, [rcx+10h]; Sid
0x18002463b  call    cs:__imp_ConvertSidToStringSidW
0x180024641  test    eax, eax
0x180024643  jnz     short loc_18002468E
0x180024645  call    cs:__imp_GetLastError
0x18002464b  mov     ebx, eax
0x18002464d  test    eax, eax
0x18002464f  jle     short loc_18002465A
0x180024651  movzx   ebx, ax
0x180024654  or      ebx, 0C0070000h
0x18002465a  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180024661  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180024666  mov     r9, rax
0x180024669  lea     rax, Class
0x180024670  mov     [rsp+30h], rax
0x180024675  lea     rax, aConvertsidtost_0; "ConvertSidToStringSidW"
0x18002467c  mov     [rsp+0B0h+var_88], rax
0x180024681  mov     dword ptr [rsp+0B0h+var_90], 1957h
0x180024689  jmp     loc_1800245E4
0x18002468e  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x180024695  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002469c  mov     r9, [rbp+4Fh+StringSid]
0x1800246a0  cmp     word ptr [r9+rcx*2+2], 0
0x1800246a7  lea     rcx, [rcx+1]
0x1800246ab  jnz     short loc_1800246A0
0x1800246ad  mov     rdx, [r13+r15+0]
0x1800246b2  lea     ecx, ds:2[rcx*2]
0x1800246b9  mov     rax, [rax+28h]
0x1800246bd  mov     r8d, 2
0x1800246c3  mov     dword ptr [rsp+0B0h+var_90], ecx
0x1800246c7  mov     rcx, [r12+rsi]
0x1800246cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246d0  mov     ebx, eax
0x1800246d2  test    eax, eax
0x1800246d4  jz      short loc_18002470A
0x1800246d6  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800246dd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800246e2  mov     r9, rax
0x1800246e5  lea     rax, Class
0x1800246ec  mov     [rsp+30h], rax
0x1800246f1  lea     rax, aSaveuserinfo; "SaveUserInfo"
0x1800246f8  mov     [rsp+0B0h+var_88], rax
0x1800246fd  mov     dword ptr [rsp+0B0h+var_90], 1960h
0x180024705  jmp     loc_1800245E4
0x18002470a  cmp     qword ptr [rsi+128h], 0
0x180024712  jz      loc_180024876
0x180024718  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x18002471f  lea     rcx, [rbp+4Fh+var_70]
0x180024723  mov     rdx, [r13+r15+0]
0x180024728  mov     r9d, 0Eh
0x18002472e  mov     [rsp+0B0h+var_88], rcx
0x180024733  xor     r8d, r8d
0x180024736  lea     rcx, [rbp+4Fh+var_58]
0x18002473a  mov     rax, [rax+20h]
0x18002473e  mov     [rsp+0B0h+var_90], rcx
0x180024743  mov     rcx, [r12+rsi]
0x180024747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002474c  mov     ebx, eax
0x18002474e  test    eax, eax
0x180024750  jz      short loc_180024786
0x180024752  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180024759  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002475e  mov     r9, rax
0x180024761  lea     rax, Class
0x180024768  mov     [rsp+30h], rax
0x18002476d  lea     rax, aLookupuserinfo; "LookUpUserInfo"
0x180024774  mov     [rsp+0B0h+var_88], rax
0x180024779  mov     dword ptr [rsp+0B0h+var_90], 196Dh
0x180024781  jmp     loc_1800245E4
0x180024786  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002478d  lea     rcx, [rbp+4Fh+var_50]
0x180024791  mov     rax, [rax+80h]
0x180024798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002479d  mov     ebx, eax
0x18002479f  test    eax, eax
0x1800247a1  jz      short loc_1800247D7
0x1800247a3  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800247aa  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800247af  mov     r9, rax
0x1800247b2  lea     rax, Class
0x1800247b9  mov     [rsp+30h], rax
0x1800247be  lea     rax, aGetclientinfo; "GetClientInfo"
0x1800247c5  mov     [rsp+0B0h+var_88], rax
0x1800247ca  mov     dword ptr [rsp+0B0h+var_90], 1970h
0x1800247d2  jmp     loc_1800245E4
0x1800247d7  test    byte ptr [rbp+4Fh+var_4C+0Fh], 1
0x1800247db  jz      short loc_180024816
0x1800247dd  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800247e4  mov     ebx, 0C000010Ah
0x1800247e9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800247ee  mov     r9, rax
0x1800247f1  lea     rax, Class
0x1800247f8  mov     [rsp+30h], rax
0x1800247fd  lea     rax, aCallerIsTermin; "Caller is terminating"
0x180024804  mov     [rsp+0B0h+var_88], rax
0x180024809  mov     dword ptr [rsp+0B0h+var_90], 1975h
0x180024811  jmp     loc_1800245E4
0x180024816  mov     r9, [rbp+4Fh+var_58]
0x18002481a  lea     rcx, [r13+118h]
0x180024821  mov     r8, [rbp+4Fh+var_38]
0x180024825  xor     edx, edx
0x180024827  mov     rax, [rsi+128h]
0x18002482e  mov     [rsp+0B0h+var_90], rcx
0x180024833  mov     rcx, [rsi+8]
0x180024837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002483c  mov     ebx, eax
0x18002483e  test    eax, eax
0x180024840  jz      short loc_180024876
0x180024842  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180024849  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002484e  mov     r9, rax
0x180024851  lea     rax, Class
0x180024858  mov     [rsp+30h], rax
0x18002485d  lea     rax, aConnectidentit; "ConnectIdentity"
0x180024864  mov     [rsp+0B0h+var_88], rax
0x180024869  mov     dword ptr [rsp+0B0h+var_90], 197Eh
0x180024871  jmp     loc_1800245E4
0x180024876  mov     rax, [rbp+4Fh+arg_10]
0x18002487a  mov     r9, [rax+8]
0x18002487e  test    r9, r9
0x180024881  jz      short loc_1800248FE
0x180024883  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x18002488a  mov     r10, [rax+28h]
0x18002488e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180024895  cmp     word ptr [r9+rax*2+2], 0
0x18002489c  lea     rax, [rax+1]
0x1800248a0  jnz     short loc_180024895
0x1800248a2  mov     rdx, [r13+r15+0]
0x1800248a7  lea     ecx, ds:2[rax*2]
0x1800248ae  mov     dword ptr [rsp+0B0h+var_90], ecx
0x1800248b2  mov     r8d, 1
0x1800248b8  mov     rcx, [r12+rsi]
0x1800248bc  mov     rax, r10
0x1800248bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248c4  mov     ebx, eax
0x1800248c6  test    eax, eax
0x1800248c8  jz      short loc_1800248FE
0x1800248ca  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800248d1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800248d6  mov     r9, rax
0x1800248d9  lea     rax, Class
0x1800248e0  mov     [rsp+30h], rax
0x1800248e5  lea     rax, aSaveuserinfoLi_4; "SaveUserInfo(LIIC_UserUniqueId)"
0x1800248ec  mov     [rsp+0B0h+var_88], rax
0x1800248f1  mov     dword ptr [rsp+0B0h+var_90], 1989h
0x1800248f9  jmp     loc_1800245E4
0x1800248fe  mov     al, 1
0x180024900  jmp     loc_18002452C
0x180024905  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18002490c  mov     ebx, 0C00000E5h
0x180024911  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180024916  mov     r9, rax
0x180024919  lea     rax, Class
0x180024920  mov     [rsp+30h], rax
0x180024925  lea     rax, aUnknownUsertyp; "Unknown UserType"
0x18002492c  mov     [rsp+0B0h+var_88], rax
0x180024931  mov     dword ptr [rsp+0B0h+var_90], 1990h
0x180024939  jmp     loc_1800245E4
  ... truncated ...
```
