# _CloudAPIsCloudToOnPremTgtPresentInCache(_LUID *,int *)

- ea: `0x18004bb2c`
- end: `0x18004bf77`
- name: `?_CloudAPIsCloudToOnPremTgtPresentInCache@@YAJPEAU_LUID@@PEAH@Z`
- size: `1099`
- prototype: `__int64 __fastcall(struct _LUID *, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800483b0`

## callees

- `0x180007ef0`
- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x18000ce50`
- `0x18000e7e0`
- `0x18000e900`
- `0x18000ee60`
- `0x180010320`
- `0x18002ae10`
- `0x18002ce50`
- `0x180042410`
- `0x18004bb2c`
- `0x180064658`
- `0x180081010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18004bde6`
- `ntdll!RtlEqualUnicodeString` at `0x18004bde6`

## string_xrefs

- `0x18004bb76`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004bc0c`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004bc64`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004bcb9`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004bd34`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004bd86`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18004be0f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _CloudAPIsCloudToOnPremTgtPresentInCache(struct _LUID *a1, int *a2)
{
  struct _USER_CACHE_ENTRY *v3; // r12
  unsigned int v4; // r14d
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v5; // rdi
  const char *v6; // rax
  unsigned int v7; // eax
  struct _LOGON_SESSION *v8; // r13
  unsigned int v9; // ebx
  const char *v10; // r9
  unsigned __int8 *v11; // rsi
  const char *v12; // r9
  const char *v13; // r9
  const char *v14; // rax
  const char *v15; // rax
  __int64 v16; // r15
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  const char *v21; // rax
  _DWORD *v22; // r8
  __int64 v23; // rax
  unsigned __int8 *v24; // rcx
  ULONG i; // ecx
  __int64 v26; // rax
  __int64 CredentialSize; // r8
  PUCHAR v28; // rdx
  PUCHAR Credentials; // r14
  struct _APPLUGIN_USER_INFO **v31; // [rsp+20h] [rbp-79h]
  struct _APPLUGIN_USER_INFO **v32; // [rsp+20h] [rbp-79h]
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v34; // [rsp+50h] [rbp-49h] BYREF
  struct _ApPluginPkg *v35; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int8 *v36[2]; // [rsp+60h] [rbp-39h] BYREF
  struct _LOGON_SESSION *v37; // [rsp+70h] [rbp-29h] BYREF
  struct _APPLUGIN_USER_INFO *v38; // [rsp+78h] [rbp-21h] BYREF
  UNICODE_STRING String2; // [rsp+80h] [rbp-19h] BYREF
  __int128 v40; // [rsp+90h] [rbp-9h] BYREF
  __int128 v41; // [rsp+A0h] [rbp+7h] BYREF
  wchar_t v42; // [rsp+B0h] [rbp+17h]

  v42 = aKerberos[8];
  *(_OWORD *)v36 = 0;
  v40 = 0;
  v3 = 0;
  LOBYTE(v4) = 0;
  v37 = 0;
  v5 = 0;
  v35 = 0;
  v41 = *(_OWORD *)L"Kerberos";
  v34 = 0;
  v38 = 0;
  *(_QWORD *)&String2.Length = 1179664;
  String2.Buffer = (PWSTR)&v41;
  *a2 = 0;
  v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
  WPPTraceLogA(2, "0x%08x %s:%u : %s:%ws", 0, v6, 3632, "%!FUNC! start", &Class);
  v7 = _AcquireLogonSession(1, a1, &v37);
  v8 = v37;
  v9 = v7;
  if ( v7 )
  {
    v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    LODWORD(v31) = 3635;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v9, v10, v31, "AcquireLogonSession", &Class);
LABEL_3:
    v11 = v36[1];
    goto LABEL_17;
  }
  v9 = RefPackage((struct _GUID *)((char *)v37 + 36), &v35);
  if ( v9 )
  {
    v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    LODWORD(v31) = 3640;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v9, v12, v31, "RefPackage", &Class);
    goto LABEL_3;
  }
  v3 = (struct _USER_CACHE_ENTRY *)*((_QWORD *)v8 + 7);
  LockAndUnProtectUserCacheEntry(v3, 0);
  v9 = DuplicateCredentialData(v3, (struct _AP_BLOB *)v36, (struct _tagCacheNodeIdentifier *)&v40);
  if ( v9 )
  {
    LOBYTE(v4) = 1;
    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    LODWORD(v31) = 3651;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v9, v13, v31, "DuplicateCredentialData", &Class);
    goto LABEL_3;
  }
  UnlockAndProtectUserCacheEntry(v3);
  v11 = v36[1];
  v9 = ValidateUserInfo(v35, 0, v36[1], (unsigned int)v36[0], &v38, 0, 0, &v34);
  if ( v9 )
  {
    v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    LODWORD(v32) = 3666;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v9, v14, v32, "ValidateUserInfo", &Class);
    v5 = v34;
    goto LABEL_17;
  }
  v5 = v34;
  if ( !v34 )
  {
    v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    LODWORD(v32) = 3670;
    WPPTraceLogA(2, "0x%08x %s:%u : %s:%ws", 0, v15, v32, "NoKerberosCredReturned", &Class);
    goto LABEL_17;
  }
  v4 = 0;
  if ( v34->CredentialCount )
  {
    while ( 1 )
    {
      v16 = v4;
      if ( RtlEqualUnicodeString(&v5->Credentials[v16].PackageName, &String2, 1u) )
      {
        if ( v5->Credentials[v16].CredentialSize >= 0x44 )
          break;
      }
      if ( ++v4 >= v5->CredentialCount )
        goto LABEL_16;
    }
    Credentials = v5->Credentials[v16].Credentials;
    if ( (*Credentials & 1) != 0 )
    {
LABEL_16:
      LOBYTE(v4) = 0;
      goto LABEL_17;
    }
    if ( !*((_DWORD *)Credentials + 4) )
    {
      if ( !*((_DWORD *)Credentials + 6) )
      {
        LOBYTE(v4) = 0;
        goto LABEL_17;
      }
      MicrosoftTelemetryAssertTriggeredNoArgs(v18, v17, v19, v20);
    }
    if ( !*((_DWORD *)Credentials + 6) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v18, v17, v19, v20);
    LOBYTE(v4) = 0;
    *a2 = 1;
  }
LABEL_17:
  v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
  WPPTraceLogA(2, "0x%08x %s:%u : %s:%u", v9, v21, 3704, "%!FUNC! end (IsPresent)", *v22);
  if ( (_BYTE)v4 )
    UnlockAndProtectUserCacheEntry(v3);
  DerefPackage(v35);
  ReleaseLogonSession(v8);
  if ( v11 )
  {
    v23 = LODWORD(v36[0]);
    v24 = v11;
    if ( LODWORD(v36[0]) )
    {
      do
      {
        *v24++ = 0;
        --v23;
      }
      while ( v23 );
    }
    ((void (__fastcall *)(unsigned __int8 *))g_pLsaFunctionTable->FreeLsaHeap)(v11);
  }
  if ( *((_QWORD *)&v40 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v5 )
  {
    for ( i = 0; i < v5->CredentialCount; ++i )
    {
      v26 = i;
      CredentialSize = v5->Credentials[v26].CredentialSize;
      v28 = v5->Credentials[v26].Credentials;
      if ( v5->Credentials[v26].CredentialSize )
      {
        do
        {
          *v28++ = 0;
          --CredentialSize;
        }
        while ( CredentialSize );
      }
    }
    ((void (__fastcall *)(struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *))g_pLsaFunctionTable->FreeLsaHeap)(v5);
  }
  FreeUserInfo(v38);
  return v9;
}

```

## disassembly

```asm
0x18004bb2c  mov     [rsp-8+arg_10], rbx
0x18004bb31  push    rbp
0x18004bb32  push    rsi
0x18004bb33  push    rdi
0x18004bb34  push    r12
0x18004bb36  push    r13
0x18004bb38  push    r14
0x18004bb3a  push    r15
0x18004bb3c  lea     rbp, [rsp-27h]
0x18004bb41  sub     rsp, 0C0h
0x18004bb48  mov     rax, cs:__security_cookie
0x18004bb4f  xor     rax, rsp
0x18004bb52  mov     [rbp+57h+var_38], rax
0x18004bb56  movzx   eax, word ptr cs:aKerberos+10h; ""
0x18004bb5d  xor     r15d, r15d
0x18004bb60  xorps   xmm0, xmm0
0x18004bb63  mov     [rbp+57h+var_40], ax
0x18004bb67  lea     rax, [rbp+57h+var_50]
0x18004bb6b  mov     [rbp+57h+var_A8], rdx
0x18004bb6f  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18004bb73  mov     rbx, rcx
0x18004bb76  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004bb7d  movups  [rbp+57h+var_60], xmm0
0x18004bb81  mov     r12d, r15d
0x18004bb84  mov     r14b, r15b
0x18004bb87  movups  xmm0, xmmword ptr cs:aKerberos; "Kerberos"
0x18004bb8e  mov     [rbp+57h+var_80], r15
0x18004bb92  mov     edi, r15d
0x18004bb95  mov     [rbp+57h+var_98], r15
0x18004bb99  movups  [rbp+57h+var_50], xmm0
0x18004bb9d  mov     [rbp+57h+var_A0], r15
0x18004bba1  mov     [rbp+57h+var_78], r15
0x18004bba5  mov     qword ptr [rbp+57h+String2.Length], 120010h
0x18004bbad  mov     [rbp+57h+String2.Buffer], rax
0x18004bbb1  mov     [rdx], r15d
0x18004bbb4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004bbb9  mov     r9, rax
0x18004bbbc  lea     rsi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004bbc3  lea     rax, Class
0x18004bbca  xor     r8d, r8d
0x18004bbcd  mov     [rsp+0F0h+var_C0], rax
0x18004bbd2  lea     ecx, [r15+2]
0x18004bbd6  lea     rax, aFuncStart; "%!FUNC! start"
0x18004bbdd  mov     rdx, rsi
0x18004bbe0  mov     [rsp+0F0h+var_C8], rax
0x18004bbe5  mov     dword ptr [rsp+0F0h+var_D0], 0E30h
0x18004bbed  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004bbf2  lea     r8, [rbp+57h+var_80]; struct _LOGON_SESSION **
0x18004bbf6  mov     rdx, rbx; struct _LUID *
0x18004bbf9  lea     ecx, [r15+1]; int
0x18004bbfd  call    ?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z; _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)
0x18004bc02  mov     r13, [rbp+57h+var_80]
0x18004bc06  mov     ebx, eax
0x18004bc08  test    eax, eax
0x18004bc0a  jz      short loc_18004BC51
0x18004bc0c  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004bc13  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004bc18  mov     r9, rax
0x18004bc1b  lea     rax, Class
0x18004bc22  mov     [rsp+0F0h+var_C0], rax
0x18004bc27  lea     rax, aAcquirelogonse_0; "AcquireLogonSession"
0x18004bc2e  mov     [rsp+0F0h+var_C8], rax
0x18004bc33  mov     dword ptr [rsp+0F0h+var_D0], 0E33h
0x18004bc3b  mov     r8d, ebx
0x18004bc3e  mov     rdx, rsi
0x18004bc41  xor     ecx, ecx
0x18004bc43  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004bc48  mov     rsi, [rbp+57h+var_90+8]
0x18004bc4c  jmp     loc_18004BE0B
0x18004bc51  lea     rcx, [r13+24h]; struct _GUID *
0x18004bc55  lea     rdx, [rbp+57h+var_98]; struct _ApPluginPkg **
0x18004bc59  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x18004bc5e  mov     ebx, eax
0x18004bc60  test    eax, eax
0x18004bc62  jz      short loc_18004BC95
0x18004bc64  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004bc6b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004bc70  mov     r9, rax
0x18004bc73  lea     rax, Class
0x18004bc7a  mov     [rsp+0F0h+var_C0], rax
0x18004bc7f  lea     rax, aRefpackage; "RefPackage"
0x18004bc86  mov     [rsp+0F0h+var_C8], rax
0x18004bc8b  mov     dword ptr [rsp+0F0h+var_D0], 0E38h
0x18004bc93  jmp     short loc_18004BC3B
0x18004bc95  mov     r12, [r13+38h]
0x18004bc99  xor     edx, edx; bool
0x18004bc9b  mov     rcx, r12; struct _USER_CACHE_ENTRY *
0x18004bc9e  call    ?LockAndUnProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@_N@Z; LockAndUnProtectUserCacheEntry(_USER_CACHE_ENTRY *,bool)
0x18004bca3  lea     r8, [rbp+57h+var_60]; struct _tagCacheNodeIdentifier *
0x18004bca7  mov     rcx, r12; struct _USER_CACHE_ENTRY *
0x18004bcaa  lea     rdx, [rbp+57h+var_90]; struct _AP_BLOB *
0x18004bcae  call    ?DuplicateCredentialData@@YAJPEAU_USER_CACHE_ENTRY@@PEAU_AP_BLOB@@PEAU_tagCacheNodeIdentifier@@@Z; DuplicateCredentialData(_USER_CACHE_ENTRY *,_AP_BLOB *,_tagCacheNodeIdentifier *)
0x18004bcb3  mov     ebx, eax
0x18004bcb5  test    eax, eax
0x18004bcb7  jz      short loc_18004BCF0
0x18004bcb9  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004bcc0  mov     r14b, 1
0x18004bcc3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004bcc8  mov     r9, rax
0x18004bccb  lea     rax, Class
0x18004bcd2  mov     [rsp+0F0h+var_C0], rax
0x18004bcd7  lea     rax, aDuplicatecrede; "DuplicateCredentialData"
0x18004bcde  mov     [rsp+0F0h+var_C8], rax
0x18004bce3  mov     dword ptr [rsp+0F0h+var_D0], 0E43h
0x18004bceb  jmp     loc_18004BC3B
0x18004bcf0  mov     rcx, r12; struct _USER_CACHE_ENTRY *
0x18004bcf3  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x18004bcf8  mov     rsi, [rbp+57h+var_90+8]
0x18004bcfc  lea     rax, [rbp+57h+var_A0]
0x18004bd00  mov     r9d, dword ptr [rbp+57h+var_90]; unsigned int
0x18004bd04  mov     r8, rsi; unsigned __int8 *
0x18004bd07  mov     rcx, [rbp+57h+var_98]; struct _ApPluginPkg *
0x18004bd0b  xor     edx, edx; struct _GUID *
0x18004bd0d  mov     [rsp+0F0h+var_B8], rax; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x18004bd12  lea     rax, [rbp+57h+var_78]
0x18004bd16  mov     [rsp+0F0h+var_C0], r15; int *
0x18004bd1b  mov     [rsp+0F0h+var_C8], r15; int *
0x18004bd20  mov     [rsp+0F0h+var_D0], rax; struct _APPLUGIN_USER_INFO **
0x18004bd25  mov     [rbp+57h+var_B0], r15b
0x18004bd29  call    ?ValidateUserInfo@@YAJPEAU_ApPluginPkg@@PEAU_GUID@@PEAEKPEAPEAU_APPLUGIN_USER_INFO@@PEAH4PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z; ValidateUserInfo(_ApPluginPkg *,_GUID *,uchar *,ulong,_APPLUGIN_USER_INFO * *,int *,int *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x18004bd2e  mov     ebx, eax
0x18004bd30  test    eax, eax
0x18004bd32  jz      short loc_18004BD7D
0x18004bd34  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004bd3b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004bd40  mov     r9, rax
0x18004bd43  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004bd4a  lea     rax, Class
0x18004bd51  mov     r8d, ebx
0x18004bd54  mov     [rsp+0F0h+var_C0], rax
0x18004bd59  xor     ecx, ecx
0x18004bd5b  lea     rax, aValidateuserin; "ValidateUserInfo"
0x18004bd62  mov     [rsp+0F0h+var_C8], rax
0x18004bd67  mov     dword ptr [rsp+0F0h+var_D0], 0E52h
0x18004bd6f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004bd74  mov     rdi, [rbp+57h+var_A0]
0x18004bd78  jmp     loc_18004BE0B
0x18004bd7d  mov     rdi, [rbp+57h+var_A0]
0x18004bd81  test    rdi, rdi
0x18004bd84  jnz     short loc_18004BDC9
0x18004bd86  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004bd8d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004bd92  mov     r9, rax
0x18004bd95  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004bd9c  lea     rax, Class
0x18004bda3  xor     r8d, r8d
0x18004bda6  mov     [rsp+0F0h+var_C0], rax
0x18004bdab  lea     ecx, [rdi+2]
0x18004bdae  lea     rax, aNokerberoscred; "NoKerberosCredReturned"
0x18004bdb5  mov     [rsp+0F0h+var_C8], rax
0x18004bdba  mov     dword ptr [rsp+0F0h+var_D0], 0E56h
0x18004bdc2  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004bdc7  jmp     short loc_18004BE0B
0x18004bdc9  mov     r14d, r15d
0x18004bdcc  cmp     [rdi], r15d
0x18004bdcf  jbe     short loc_18004BE0B
0x18004bdd1  mov     r15d, r14d
0x18004bdd4  lea     rcx, [rdi+8]
0x18004bdd8  shl     r15, 5
0x18004bddc  lea     rdx, [rbp+57h+String2]; String2
0x18004bde0  add     rcx, r15; String1
0x18004bde3  mov     r8b, 1; CaseInsensitive
0x18004bde6  call    cs:__imp_RtlEqualUnicodeString
0x18004bdec  test    al, al
0x18004bdee  jz      short loc_18004BDFC
0x18004bdf0  cmp     dword ptr [r15+rdi+18h], 44h ; 'D'
0x18004bdf6  jnb     loc_18004BF2C
0x18004bdfc  inc     r14d
0x18004bdff  cmp     r14d, [rdi]
0x18004be02  jb      short loc_18004BDD1
0x18004be04  xor     r15d, r15d
0x18004be07  mov     r14b, [rbp+57h+var_B0]
0x18004be0b  mov     r8, [rbp+57h+var_A8]
0x18004be0f  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18004be16  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004be1b  mov     edx, [r8]
0x18004be1e  mov     r9, rax
0x18004be21  mov     dword ptr [rsp+0F0h+var_C0], edx
0x18004be25  mov     r8d, ebx
0x18004be28  lea     rdx, aFuncEndIsprese; "%!FUNC! end (IsPresent)"
0x18004be2f  mov     ecx, 2
0x18004be34  mov     [rsp+0F0h+var_C8], rdx
0x18004be39  lea     rdx, a0x08xSUSU; "0x%08x %s:%u : %s:%u"
0x18004be40  mov     dword ptr [rsp+0F0h+var_D0], 0E78h
0x18004be48  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004be4d  test    r14b, r14b
0x18004be50  jz      short loc_18004BE5A
0x18004be52  mov     rcx, r12; struct _USER_CACHE_ENTRY *
0x18004be55  call    ?UnlockAndProtectUserCacheEntry@@YAXPEAU_USER_CACHE_ENTRY@@@Z; UnlockAndProtectUserCacheEntry(_USER_CACHE_ENTRY *)
0x18004be5a  mov     rcx, [rbp+57h+var_98]; struct _ApPluginPkg *
0x18004be5e  call    ?DerefPackage@@YAXPEAU_ApPluginPkg@@@Z; DerefPackage(_ApPluginPkg *)
0x18004be63  mov     rcx, r13; struct _LOGON_SESSION *
0x18004be66  call    ?ReleaseLogonSession@@YAXPEAU_LOGON_SESSION@@@Z; ReleaseLogonSession(_LOGON_SESSION *)
0x18004be6b  test    rsi, rsi
0x18004be6e  jz      short loc_18004BE9A
0x18004be70  mov     eax, dword ptr [rbp+57h+var_90]
0x18004be73  mov     rcx, rsi
0x18004be76  test    rax, rax
0x18004be79  jz      short loc_18004BE87
0x18004be7b  mov     [rcx], r15b
0x18004be7e  inc     rcx
0x18004be81  sub     rax, 1
0x18004be85  jnz     short loc_18004BE7B
0x18004be87  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004be8e  mov     rcx, rsi
0x18004be91  mov     rax, [rax+30h]
0x18004be95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be9a  mov     rcx, qword ptr [rbp+57h+var_60+8]
0x18004be9e  test    rcx, rcx
0x18004bea1  jz      short loc_18004BEB3
0x18004bea3  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004beaa  mov     rax, [rax+30h]
0x18004beae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004beb3  test    rdi, rdi
0x18004beb6  jz      short loc_18004BEFA
0x18004beb8  mov     ecx, r15d
0x18004bebb  cmp     [rdi], r15d
0x18004bebe  jbe     short loc_18004BEE7
0x18004bec0  mov     eax, ecx
0x18004bec2  shl     rax, 5
0x18004bec6  mov     r8d, [rax+rdi+18h]
0x18004becb  mov     rdx, [rax+rdi+20h]
0x18004bed0  test    r8, r8
0x18004bed3  jz      short loc_18004BEE1
0x18004bed5  mov     [rdx], r15b
0x18004bed8  inc     rdx
0x18004bedb  sub     r8, 1
0x18004bedf  jnz     short loc_18004BED5
0x18004bee1  inc     ecx
0x18004bee3  cmp     ecx, [rdi]
0x18004bee5  jb      short loc_18004BEC0
0x18004bee7  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004beee  mov     rcx, rdi
0x18004bef1  mov     rax, [rax+30h]
0x18004bef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004befa  mov     rcx, [rbp+57h+var_78]; struct _APPLUGIN_USER_INFO *
0x18004befe  call    ?FreeUserInfo@@YAXPEAU_APPLUGIN_USER_INFO@@@Z; FreeUserInfo(_APPLUGIN_USER_INFO *)
0x18004bf03  mov     eax, ebx
0x18004bf05  mov     rcx, [rbp+57h+var_38]
0x18004bf09  xor     rcx, rsp; StackCookie
0x18004bf0c  call    __security_check_cookie
0x18004bf11  mov     rbx, [rsp+0F0h+arg_10]
0x18004bf19  add     rsp, 0C0h
0x18004bf20  pop     r15
0x18004bf22  pop     r14
0x18004bf24  pop     r13
0x18004bf26  pop     r12
0x18004bf28  pop     rdi
0x18004bf29  pop     rsi
0x18004bf2a  pop     rbp
0x18004bf2b  retn
0x18004bf2c  mov     r14, [r15+rdi+20h]
0x18004bf31  xor     r15d, r15d
0x18004bf34  test    byte ptr [r14], 1
0x18004bf38  jnz     loc_18004BE07
0x18004bf3e  mov     eax, [r14+10h]
0x18004bf42  test    eax, eax
0x18004bf44  jnz     short loc_18004BF51
0x18004bf46  cmp     [r14+18h], r15d
0x18004bf4a  jz      short loc_18004BF6F
0x18004bf4c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004bf51  cmp     [r14+18h], r15d
0x18004bf55  ja      short loc_18004BF5C
0x18004bf57  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004bf5c  mov     r8, [rbp+57h+var_A8]
0x18004bf60  mov     r14b, r15b
0x18004bf63  mov     dword ptr [r8], 1
0x18004bf6a  jmp     loc_18004BE0F
0x18004bf6f  mov     r14b, r15b
0x18004bf72  jmp     loc_18004BE0B
```
