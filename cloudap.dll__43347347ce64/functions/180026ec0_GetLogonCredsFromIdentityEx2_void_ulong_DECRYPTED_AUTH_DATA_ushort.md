# GetLogonCredsFromIdentityEx2(void *,ulong,_DECRYPTED_AUTH_DATA *,ushort * *)

- ea: `0x180026ec0`
- end: `0x18002730c`
- name: `?GetLogonCredsFromIdentityEx2@@YAJPEAXKPEAU_DECRYPTED_AUTH_DATA@@PEAPEAG@Z`
- size: `1100`
- prototype: `__int64 __fastcall(char *AuthIdentityByteArray, unsigned int AuthIdentityLength, struct _DECRYPTED_AUTH_DATA *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020b10`
- `0x180022f80`
- `0x180048530`
- `0x180058090`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000d000`
- `0x180026ec0`
- `0x18003d8dc`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `SspiCli!SspiCopyAuthIdentity` at `0x18002711f`
- `SspiCli!SspiCopyAuthIdentity` at `0x18002711f`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800272a3`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800272fd`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800272a3`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800272fd`
- `SspiCli!SspiUnmarshalAuthIdentity` at `0x180026f50`
- `SspiCli!SspiUnmarshalAuthIdentity` at `0x180026f50`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180027092`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180027092`

## string_xrefs

- `0x180026f5c`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180026fab`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180026ffd`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18002704f`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800270a0`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800270eb`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180027132`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800271a5`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180027223`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180027162`: `SspiCopyAuthIdentity`
- `0x18002706a`: `ImpersonateClient`

## pseudocode

```c
__int64 __fastcall GetLogonCredsFromIdentityEx2(
        char *AuthIdentityByteArray,
        unsigned int AuthIdentityLength,
        struct _DECRYPTED_AUTH_DATA *a3,
        unsigned __int16 **a4)
{
  unsigned int v7; // edx
  unsigned int v8; // ebx
  const char *v9; // r9
  const char *v10; // r9
  int v11; // eax
  const char *v12; // r9
  const char *v13; // r9
  const char *v14; // r9
  const char *v15; // r9
  const char *v16; // r9
  char v17; // al
  const char *v18; // rdx
  bool v19; // zf
  unsigned __int16 *v20; // rsi
  size_t v21; // r14
  void *v22; // rax
  void *v23; // rbx
  const char *v24; // r9
  unsigned __int16 *v25; // rax
  char v26; // al
  int v28; // [rsp+20h] [rbp-58h]
  const char *v29; // [rsp+28h] [rbp-50h]
  unsigned __int16 *v30; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int16 *v31; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int16 *v32; // [rsp+50h] [rbp-28h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthDataCopy; // [rsp+90h] [rbp+18h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE ppAuthIdentity; // [rsp+A8h] [rbp+30h] BYREF

  ppAuthIdentity = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  AuthDataCopy = 0;
  *(_OWORD *)a3 = 0;
  *((_QWORD *)a3 + 2) = 0;
  *a4 = 0;
  if ( AuthIdentityByteArray
    && AuthIdentityLength >= 0x30
    && *(_DWORD *)AuthIdentityByteArray == 513
    && (v7 = *((_DWORD *)AuthIdentityByteArray + 2), v7 <= AuthIdentityLength)
    && *((unsigned __int16 *)AuthIdentityByteArray + 2) <= v7 )
  {
    v8 = SspiUnmarshalAuthIdentity(AuthIdentityLength, AuthIdentityByteArray, &ppAuthIdentity);
    if ( v8 )
    {
      v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v8, v9, 473, "SspiUnmarshalAuthIdentity", &Class);
      goto LABEL_38;
    }
    v8 = ValidateAuthIdEx2((struct _SEC_WINNT_AUTH_IDENTITY_EX2 *)ppAuthIdentity, &v30, &v31, &v32);
    if ( v8 )
    {
      v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v8, v10, 480, "ValidateAuthIdEx2", &Class);
      goto LABEL_38;
    }
    v11 = *((_DWORD *)ppAuthIdentity + 9);
    if ( (v11 & 0x20) != 0 )
    {
      v8 = DecryptAuthIdEx2((struct _SEC_WINNT_AUTH_IDENTITY_EX2 *)ppAuthIdentity, &AuthDataCopy);
      if ( v8 )
      {
        v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v8, v12, 486, "DecryptAuthIdEx2(System Protected)", &Class);
        goto LABEL_38;
      }
      goto LABEL_27;
    }
    if ( (v11 & 0x40) != 0 )
    {
      v8 = g_pLsaFunctionTable->ImpersonateClient();
      if ( v8 )
      {
        v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v8, v13, 491, "ImpersonateClient", &Class);
        goto LABEL_38;
      }
      v8 = DecryptAuthIdEx2((struct _SEC_WINNT_AUTH_IDENTITY_EX2 *)ppAuthIdentity, &AuthDataCopy);
      RevertToSelf();
      if ( v8 )
      {
        v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v8, v14, 495, "DecryptAuthIdEx2(User Protected)", &Class);
        goto LABEL_38;
      }
      goto LABEL_27;
    }
    if ( (v11 & 0x80u) != 0 )
    {
      v8 = DecryptAuthIdEx2((struct _SEC_WINNT_AUTH_IDENTITY_EX2 *)ppAuthIdentity, &AuthDataCopy);
      if ( v8 )
      {
        v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v8, v15, 500, "DecryptAuthIdEx2(System Encrypted)", &Class);
        goto LABEL_38;
      }
      goto LABEL_27;
    }
    v8 = SspiCopyAuthIdentity(ppAuthIdentity, &AuthDataCopy);
    if ( !v8 )
    {
LABEL_27:
      v20 = (unsigned __int16 *)((char *)AuthDataCopy + *((unsigned int *)AuthDataCopy + 7));
      v21 = v20[1];
      v22 = (void *)((__int64 (__fastcall *)(size_t))g_pLsaFunctionTable->AllocateLsaHeap)(v21);
      v23 = v22;
      if ( v22 )
      {
        memcpy_0(v22, v20, v21);
        *(_QWORD *)a3 = v31;
        *((_QWORD *)a3 + 1) = v32;
        v25 = v30;
        *((_QWORD *)a3 + 2) = v23;
        v8 = 0;
        *a4 = v25;
        v31 = 0;
        v32 = 0;
        v30 = 0;
      }
      else
      {
        v8 = -1073741801;
        v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v24, 519, "AllocateLsaHeap", &Class);
      }
      goto LABEL_38;
    }
    v16 = "";
    while ( 1 )
    {
      v17 = *(v16 - 1);
      v18 = v16--;
      v19 = v17 == 92;
      if ( v17 == 92 )
        break;
      if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v19 = v17 == 92;
        break;
      }
    }
    v29 = "SspiCopyAuthIdentity";
    v28 = 507;
  }
  else
  {
    v8 = -1073741811;
    v16 = "";
    while ( 1 )
    {
      v26 = *(v16 - 1);
      v18 = v16--;
      v19 = v26 == 92;
      if ( v26 == 92 )
        break;
      if ( v16 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v19 = v26 == 92;
        break;
      }
    }
    v29 = "PackedLogonCred is invalid";
    v28 = 468;
  }
  if ( v19 )
    v16 = v18;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v8, v16, v28, v29, &Class);
LABEL_38:
  if ( ppAuthIdentity )
    SspiFreeAuthIdentity(ppAuthIdentity);
  if ( v30 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v31 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v32 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( AuthDataCopy )
    SspiFreeAuthIdentity(AuthDataCopy);
  return v8;
}

```

## disassembly

```asm
0x180026ec0  mov     rax, rsp
0x180026ec3  push    rbp
0x180026ec4  push    rbx
0x180026ec5  mov     rbp, rsp
0x180026ec8  sub     rsp, 78h
0x180026ecc  mov     [rax+10h], rsi
0x180026ed0  xorps   xmm0, xmm0
0x180026ed3  mov     [rax+18h], rdi
0x180026ed7  mov     r10d, edx
0x180026eda  mov     [rax-18h], r12
0x180026ede  mov     rdi, r8
0x180026ee1  xor     r12d, r12d
0x180026ee4  mov     [rax-20h], r14
0x180026ee8  mov     [rax-28h], r15
0x180026eec  mov     r15, r9
0x180026eef  xor     eax, eax
0x180026ef1  mov     [rbp+ppAuthIdentity], r12
0x180026ef5  mov     [rbp+var_38], r12
0x180026ef9  mov     [rbp+var_30], r12
0x180026efd  mov     [rbp+var_28], r12
0x180026f01  mov     [rbp+AuthDataCopy], r12
0x180026f05  movups  xmmword ptr [r8], xmm0
0x180026f09  mov     [r8+10h], rax
0x180026f0d  mov     [r9], r12
0x180026f10  test    rcx, rcx
0x180026f13  jz      loc_180027217
0x180026f19  cmp     edx, 30h ; '0'
0x180026f1c  jb      loc_180027217
0x180026f22  cmp     dword ptr [rcx], 201h
0x180026f28  jnz     loc_180027217
0x180026f2e  mov     edx, [rcx+8]
0x180026f31  cmp     edx, r10d
0x180026f34  ja      loc_180027217
0x180026f3a  movzx   eax, word ptr [rcx+4]
0x180026f3e  cmp     eax, edx
0x180026f40  ja      loc_180027217
0x180026f46  mov     rdx, rcx; AuthIdentityByteArray
0x180026f49  lea     r8, [rbp+ppAuthIdentity]; ppAuthIdentity
0x180026f4d  mov     ecx, r10d; AuthIdentityLength
0x180026f50  call    cs:__imp_SspiUnmarshalAuthIdentity
0x180026f56  mov     ebx, eax
0x180026f58  test    eax, eax
0x180026f5a  jz      short loc_180026F90
0x180026f5c  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180026f63  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180026f68  mov     r9, rax
0x180026f6b  lea     rax, Class
0x180026f72  mov     [rsp+78h+var_48], rax
0x180026f77  lea     rax, aSspiunmarshala; "SspiUnmarshalAuthIdentity"
0x180026f7e  mov     [rsp+78h+var_50], rax
0x180026f83  mov     [rsp+78h+var_58], 1D9h
0x180026f8b  jmp     loc_18002726A
0x180026f90  mov     rcx, [rbp+ppAuthIdentity]; struct _SEC_WINNT_AUTH_IDENTITY_EX2 *
0x180026f94  lea     r9, [rbp+var_28]; unsigned __int16 **
0x180026f98  lea     r8, [rbp+var_30]; unsigned __int16 **
0x180026f9c  lea     rdx, [rbp+var_38]; unsigned __int16 **
0x180026fa0  call    ?ValidateAuthIdEx2@@YAJPEAU_SEC_WINNT_AUTH_IDENTITY_EX2@@PEAPEAG11@Z; ValidateAuthIdEx2(_SEC_WINNT_AUTH_IDENTITY_EX2 *,ushort * *,ushort * *,ushort * *)
0x180026fa5  mov     ebx, eax
0x180026fa7  test    eax, eax
0x180026fa9  jz      short loc_180026FDF
0x180026fab  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180026fb2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180026fb7  mov     r9, rax
0x180026fba  lea     rax, Class
0x180026fc1  mov     [rsp+78h+var_48], rax
0x180026fc6  lea     rax, aValidateauthid; "ValidateAuthIdEx2"
0x180026fcd  mov     [rsp+78h+var_50], rax
0x180026fd2  mov     [rsp+78h+var_58], 1E0h
0x180026fda  jmp     loc_18002726A
0x180026fdf  mov     rcx, [rbp+ppAuthIdentity]; struct _SEC_WINNT_AUTH_IDENTITY_EX2 *
0x180026fe3  mov     eax, [rcx+24h]
0x180026fe6  test    al, 20h
0x180026fe8  jz      short loc_180027031
0x180026fea  lea     rdx, [rbp+AuthDataCopy]; struct _SEC_WINNT_AUTH_IDENTITY_EX2 **
0x180026fee  call    ?DecryptAuthIdEx2@@YAJPEAU_SEC_WINNT_AUTH_IDENTITY_EX2@@PEAPEAU1@@Z; DecryptAuthIdEx2(_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 * *)
0x180026ff3  mov     ebx, eax
0x180026ff5  test    eax, eax
0x180026ff7  jz      loc_18002717B
0x180026ffd  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180027004  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180027009  mov     r9, rax
0x18002700c  lea     rax, Class
0x180027013  mov     [rsp+78h+var_48], rax
0x180027018  lea     rax, aDecryptauthide_1; "DecryptAuthIdEx2(System Protected)"
0x18002701f  mov     [rsp+78h+var_50], rax
0x180027024  mov     [rsp+78h+var_58], 1E6h
0x18002702c  jmp     loc_18002726A
0x180027031  test    al, 40h
0x180027033  jz      loc_1800270D4
0x180027039  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180027040  mov     rax, [rax+58h]
0x180027044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027049  mov     ebx, eax
0x18002704b  test    eax, eax
0x18002704d  jz      short loc_180027083
0x18002704f  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180027056  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002705b  mov     r9, rax
0x18002705e  lea     rax, Class
0x180027065  mov     [rsp+78h+var_48], rax
0x18002706a  lea     rax, aImpersonatecli; "ImpersonateClient"
0x180027071  mov     [rsp+78h+var_50], rax
0x180027076  mov     [rsp+78h+var_58], 1EBh
0x18002707e  jmp     loc_18002726A
0x180027083  mov     rcx, [rbp+ppAuthIdentity]; struct _SEC_WINNT_AUTH_IDENTITY_EX2 *
0x180027087  lea     rdx, [rbp+AuthDataCopy]; struct _SEC_WINNT_AUTH_IDENTITY_EX2 **
0x18002708b  call    ?DecryptAuthIdEx2@@YAJPEAU_SEC_WINNT_AUTH_IDENTITY_EX2@@PEAPEAU1@@Z; DecryptAuthIdEx2(_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 * *)
0x180027090  mov     ebx, eax
0x180027092  call    cs:__imp_RevertToSelf
0x180027098  test    ebx, ebx
0x18002709a  jz      loc_18002717B
0x1800270a0  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800270a7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800270ac  mov     r9, rax
0x1800270af  lea     rax, Class
0x1800270b6  mov     [rsp+78h+var_48], rax
0x1800270bb  lea     rax, aDecryptauthide_0; "DecryptAuthIdEx2(User Protected)"
0x1800270c2  mov     [rsp+78h+var_50], rax
0x1800270c7  mov     [rsp+78h+var_58], 1EFh
0x1800270cf  jmp     loc_18002726A
0x1800270d4  lea     rdx, [rbp+AuthDataCopy]; struct _SEC_WINNT_AUTH_IDENTITY_EX2 **
0x1800270d8  test    al, al
0x1800270da  jns     short loc_18002711F
0x1800270dc  call    ?DecryptAuthIdEx2@@YAJPEAU_SEC_WINNT_AUTH_IDENTITY_EX2@@PEAPEAU1@@Z; DecryptAuthIdEx2(_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 * *)
0x1800270e1  mov     ebx, eax
0x1800270e3  test    eax, eax
0x1800270e5  jz      loc_18002717B
0x1800270eb  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800270f2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800270f7  mov     r9, rax
0x1800270fa  lea     rax, Class
0x180027101  mov     [rsp+78h+var_48], rax
0x180027106  lea     rax, aDecryptauthide; "DecryptAuthIdEx2(System Encrypted)"
0x18002710d  mov     [rsp+78h+var_50], rax
0x180027112  mov     [rsp+78h+var_58], 1F4h
0x18002711a  jmp     loc_18002726A
0x18002711f  call    cs:__imp_SspiCopyAuthIdentity
0x180027125  mov     ebx, eax
0x180027127  test    eax, eax
0x180027129  jz      short loc_18002717B
0x18002712b  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x180027132  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180027139  nop     dword ptr [rax+00000000h]
0x180027140  movzx   eax, byte ptr [r9-1]
0x180027145  mov     rdx, r9
0x180027148  dec     r9
0x18002714b  cmp     al, 5Ch ; '\'
0x18002714d  jz      short loc_180027156
0x18002714f  cmp     r9, rcx
0x180027152  ja      short loc_180027140
0x180027154  cmp     al, 5Ch ; '\'
0x180027156  lea     rax, Class
0x18002715d  mov     [rsp+78h+var_48], rax
0x180027162  lea     rax, aSspicopyauthid; "SspiCopyAuthIdentity"
0x180027169  mov     [rsp+78h+var_50], rax
0x18002716e  mov     [rsp+78h+var_58], 1FBh
0x180027176  jmp     loc_180027266
0x18002717b  mov     rcx, [rbp+AuthDataCopy]
0x18002717f  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180027186  mov     esi, [rcx+1Ch]
0x180027189  mov     rax, [rax+28h]
0x18002718d  add     rsi, rcx
0x180027190  movzx   r14d, word ptr [rsi+2]
0x180027195  mov     ecx, r14d
0x180027198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002719d  mov     rbx, rax
0x1800271a0  test    rax, rax
0x1800271a3  jnz     short loc_1800271DE
0x1800271a5  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800271ac  mov     ebx, 0C0000017h
0x1800271b1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800271b6  mov     r9, rax
0x1800271b9  lea     rax, Class
0x1800271c0  mov     [rsp+78h+var_48], rax
0x1800271c5  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x1800271cc  mov     [rsp+78h+var_50], rax
0x1800271d1  mov     [rsp+78h+var_58], 207h
0x1800271d9  jmp     loc_18002726A
0x1800271de  mov     r8, r14; Size
0x1800271e1  mov     rdx, rsi; Src
0x1800271e4  mov     rcx, rbx; void *
0x1800271e7  call    memcpy_0
0x1800271ec  mov     rax, [rbp+var_30]
0x1800271f0  mov     [rdi], rax
0x1800271f3  mov     rax, [rbp+var_28]
0x1800271f7  mov     [rdi+8], rax
0x1800271fb  mov     rax, [rbp+var_38]
0x1800271ff  mov     [rdi+10h], rbx
0x180027203  mov     ebx, r12d
0x180027206  mov     [r15], rax
0x180027209  mov     [rbp+var_30], r12
0x18002720d  mov     [rbp+var_28], r12
0x180027211  mov     [rbp+var_38], r12
0x180027215  jmp     short loc_18002727B
0x180027217  mov     ebx, 0C000000Dh
0x18002721c  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x180027223  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18002722a  nop     word ptr [rax+rax+00h]
0x180027230  movzx   eax, byte ptr [r9-1]
0x180027235  mov     rdx, r9
0x180027238  dec     r9
0x18002723b  cmp     al, 5Ch ; '\'
0x18002723d  jz      short loc_180027246
0x18002723f  cmp     r9, rcx
0x180027242  ja      short loc_180027230
0x180027244  cmp     al, 5Ch ; '\'
0x180027246  lea     rax, Class
0x18002724d  mov     [rsp+78h+var_48], rax
0x180027252  lea     rax, aPackedlogoncre; "PackedLogonCred is invalid"
0x180027259  mov     [rsp+78h+var_50], rax
0x18002725e  mov     [rsp+78h+var_58], 1D4h
0x180027266  cmovz   r9, rdx
0x18002726a  mov     r8d, ebx
0x18002726d  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180027274  xor     ecx, ecx
0x180027276  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002727b  mov     rcx, [rbp+ppAuthIdentity]; AuthData
0x18002727f  mov     r15, [rsp+78h+var_18]
0x180027284  mov     r14, [rsp+78h+var_10]
0x180027289  mov     r12, [rsp+78h+var_8]
0x18002728e  mov     rdi, [rsp+78h+arg_10]
0x180027296  mov     rsi, [rsp+78h+arg_8]
0x18002729e  test    rcx, rcx
0x1800272a1  jz      short loc_1800272A9
0x1800272a3  call    cs:__imp_SspiFreeAuthIdentity
0x1800272a9  mov     rcx, [rbp+var_38]
0x1800272ad  test    rcx, rcx
0x1800272b0  jz      short loc_1800272C2
0x1800272b2  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800272b9  mov     rax, [rax+30h]
0x1800272bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272c2  mov     rcx, [rbp+var_30]
0x1800272c6  test    rcx, rcx
0x1800272c9  jz      short loc_1800272DB
0x1800272cb  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800272d2  mov     rax, [rax+30h]
0x1800272d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272db  mov     rcx, [rbp+var_28]
0x1800272df  test    rcx, rcx
0x1800272e2  jz      short loc_1800272F4
0x1800272e4  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800272eb  mov     rax, [rax+30h]
0x1800272ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272f4  mov     rcx, [rbp+AuthDataCopy]; AuthData
0x1800272f8  test    rcx, rcx
0x1800272fb  jz      short loc_180027303
0x1800272fd  call    cs:__imp_SspiFreeAuthIdentity
0x180027303  mov     eax, ebx
0x180027305  add     rsp, 78h
0x180027309  pop     rbx
0x18002730a  pop     rbp
0x18002730b  retn
```
