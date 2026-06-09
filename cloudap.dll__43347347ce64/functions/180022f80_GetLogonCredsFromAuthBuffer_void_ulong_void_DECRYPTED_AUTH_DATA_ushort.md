# GetLogonCredsFromAuthBuffer(void *,ulong,void *,_DECRYPTED_AUTH_DATA *,ushort * *)

- ea: `0x180022f80`
- end: `0x1800236f0`
- name: `?GetLogonCredsFromAuthBuffer@@YAJPEAXK0PEAU_DECRYPTED_AUTH_DATA@@PEAPEAG@Z`
- size: `1904`
- prototype: `__int64 __fastcall(struct _KERB_CERTIFICATE_LOGON *, unsigned int, void *, struct _DECRYPTED_AUTH_DATA *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011960`
- `0x180017780`

## callees

- `0x1800046f4`
- `0x180007fc0`
- `0x18000a600`
- `0x18000b9b0`
- `0x180022f80`
- `0x180026ec0`
- `0x18002db50`
- `0x1800335d4`
- `0x18003f5ec`
- `0x18004cf50`
- `0x180081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023221`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180023221`
- `ntdll!RtlReleaseResource` at `0x18002332c`
- `ntdll!RtlReleaseResource` at `0x1800233d8`
- `ntdll!RtlReleaseResource` at `0x18002364f`
- `ntdll!RtlReleaseResource` at `0x18002332c`
- `ntdll!RtlReleaseResource` at `0x1800233d8`
- `ntdll!RtlReleaseResource` at `0x18002364f`
- `ntdll!RtlInitUnicodeString` at `0x180023275`
- `ntdll!RtlInitUnicodeString` at `0x180023282`
- `ntdll!RtlInitUnicodeString` at `0x180023275`
- `ntdll!RtlInitUnicodeString` at `0x180023282`
- `ntdll!RtlAcquireResourceShared` at `0x1800231cc`
- `ntdll!RtlAcquireResourceShared` at `0x180023246`
- `ntdll!RtlAcquireResourceShared` at `0x180023266`
- `ntdll!RtlAcquireResourceShared` at `0x1800232b7`
- `ntdll!RtlAcquireResourceShared` at `0x1800231cc`
- `ntdll!RtlAcquireResourceShared` at `0x180023246`
- `ntdll!RtlAcquireResourceShared` at `0x180023266`
- `ntdll!RtlAcquireResourceShared` at `0x1800232b7`
- `ntdll!RtlCompareUnicodeString` at `0x180023293`
- `ntdll!RtlCompareUnicodeString` at `0x180023293`

## string_xrefs

- `0x180023006`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180023079`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800230cc`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18002315c`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180023398`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800233de`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180023426`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800234ad`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18002350f`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180023546`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800235dc`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800233b8`: `Surrogate Plugins not allowed to log in`

## pseudocode

```c
__int64 __fastcall GetLogonCredsFromAuthBuffer(
        struct _KERB_CERTIFICATE_LOGON *a1,
        unsigned int a2,
        void *a3,
        struct _DECRYPTED_AUTH_DATA *a4,
        unsigned __int16 **a5)
{
  unsigned __int16 **v5; // r15
  void *v7; // r12
  unsigned int v8; // r14d
  struct _KERB_CERTIFICATE_LOGON *v9; // rsi
  char *v10; // rdi
  unsigned int LogonCredsFromIdentityEx2; // ebx
  const char *v12; // r9
  char v13; // al
  const char *v14; // rdx
  bool v15; // zf
  const char *v16; // r9
  const char *v17; // r9
  char v18; // al
  WCHAR *v19; // rdi
  struct _ApPluginPkg *v20; // rcx
  unsigned int v21; // r12d
  __int64 v22; // r15
  const WCHAR *v23; // rbx
  LONG v24; // eax
  PRTL_RESOURCE *v25; // r14
  char *v26; // rbx
  char *v27; // rsi
  struct _RTL_BALANCED_NODE *v28; // rbx
  int v29; // eax
  struct _RTL_BALANCED_NODE *v30; // rbx
  int v31; // eax
  const char *v32; // r9
  const char *v33; // r9
  const char *v34; // rax
  const char *v35; // r9
  const char *v36; // r9
  const char *v37; // r9
  const char *v38; // r9
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v39; // rax
  __int64 v40; // rcx
  struct _KERB_CERTIFICATE_LOGON *v42; // [rsp+20h] [rbp-A1h]
  struct _KERB_CERTIFICATE_LOGON *v43; // [rsp+20h] [rbp-A1h]
  const char *v44; // [rsp+28h] [rbp-99h]
  PCWSTR SourceString; // [rsp+60h] [rbp-61h] BYREF
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v46; // [rsp+68h] [rbp-59h] BYREF
  unsigned __int16 *v47; // [rsp+70h] [rbp-51h] BYREF
  unsigned __int16 *v48; // [rsp+78h] [rbp-49h] BYREF
  UNICODE_STRING String2; // [rsp+80h] [rbp-41h] BYREF
  __int128 v50; // [rsp+90h] [rbp-31h] BYREF
  __int64 v51; // [rsp+A0h] [rbp-21h]
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-19h] BYREF
  _DWORD v53[22]; // [rsp+B8h] [rbp-9h] BYREF

  v5 = a5;
  v53[0] = 0;
  *(_QWORD *)&String2.Length = 0;
  v51 = 0;
  v47 = 0;
  v7 = a3;
  v48 = 0;
  v8 = a2;
  SourceString = 0;
  v9 = a1;
  v46 = 0;
  v10 = 0;
  *(_OWORD *)a4 = 0;
  *((_QWORD *)a4 + 2) = 0;
  *a5 = 0;
  memset(&v53[1], 0, 28);
  v50 = 0;
  if ( a2 < 4 )
  {
    LogonCredsFromIdentityEx2 = -1073741811;
    v12 = "";
    while ( 1 )
    {
      v13 = *(v12 - 1);
      v14 = v12--;
      v15 = v13 == 92;
      if ( v13 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v15 = v13 == 92;
        break;
      }
    }
    v44 = "Invalid Buffer length";
    LODWORD(v42) = 592;
LABEL_7:
    if ( v15 )
      v12 = v14;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCredsFromIdentityEx2, v12, v42, v44, &Class);
    goto LABEL_77;
  }
  if ( a1->MessageType != 513 )
  {
    if ( !((unsigned __int8 (__fastcall *)(__int128 *))g_pLsaFunctionTable->GetCallInfo)(&v50) )
    {
      LogonCredsFromIdentityEx2 = -1073741595;
      v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v17, 609, "GetCallInfo", &Class);
      goto LABEL_77;
    }
    LogonCredsFromIdentityEx2 = SCardConvertLegacyBufferToEx2PackedCreds(
                                  g_pLsaFunctionTable->AllocateLsaHeap,
                                  g_pLsaFunctionTable->FreeLsaHeap,
                                  (BYTE8(v50) & 0x40) != 0,
                                  0,
                                  v9,
                                  v8,
                                  v7,
                                  0,
                                  0,
                                  0,
                                  (unsigned __int16 **)&SourceString);
    if ( LogonCredsFromIdentityEx2 )
    {
      v12 = "";
      while ( 1 )
      {
        v18 = *(v12 - 1);
        v14 = v12--;
        v15 = v18 == 92;
        if ( v18 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v15 = v18 == 92;
          break;
        }
      }
      v44 = "SCardConvertLegacyBufferToEx2PackedCreds";
      LODWORD(v42) = 629;
      goto LABEL_7;
    }
    v19 = (WCHAR *)SourceString;
    if ( !SourceString || !*SourceString )
    {
      LogonCredsFromIdentityEx2 = RefDefaultPackage((struct _ApPluginPkg **)&String2);
      if ( LogonCredsFromIdentityEx2 )
      {
        v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v42) = 636;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCredsFromIdentityEx2, v34, v42, "RefDefaultPackage", &Class);
        v10 = *(char **)&String2.Length;
      }
      else
      {
        if ( SourceString )
        {
          ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
          SourceString = 0;
        }
        v10 = *(char **)&String2.Length;
        LogonCredsFromIdentityEx2 = DuplicateString(
                                      (const unsigned __int16 *)(*(_QWORD *)&String2.Length + 24LL),
                                      0,
                                      (unsigned __int16 **)&SourceString);
        if ( !LogonCredsFromIdentityEx2 )
          goto LABEL_58;
        v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        LODWORD(v42) = 648;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCredsFromIdentityEx2, v35, v42, "DuplicateString", &Class);
      }
LABEL_75:
      if ( v10 )
        RtlReleaseResource(&g_PackageListLock);
      goto LABEL_77;
    }
    RtlAcquireResourceShared(&g_PackageListLock, 1u);
    v20 = g_pPlugins;
    if ( !g_pPlugins || (v21 = 0, !g_cPlugins) )
    {
LABEL_60:
      RtlReleaseResource(&g_PackageListLock);
      LogonCredsFromIdentityEx2 = -2146893039;
      v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(v42) = 655;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 2148074257LL, v33, v42, "RefPackageByProvName", &Class);
      goto LABEL_77;
    }
    while ( 1 )
    {
      v22 = 392LL * v21;
      DestinationString = 0;
      String2 = 0;
      v23 = (const WCHAR *)((char *)v20 + v22 + 24);
      if ( (g_ulTestFlags & 2) != 0 )
      {
        v24 = _o__wcsicmp(v19, (char *)v20 + v22 + 24);
      }
      else
      {
        if ( !v19 )
        {
          if ( !v23 )
            goto LABEL_56;
          v25 = (PRTL_RESOURCE *)((char *)v20 + v22 + 360);
          RtlAcquireResourceShared(*v25, 1u);
          goto LABEL_52;
        }
        if ( !v23 )
        {
          v26 = (char *)v20 + v22;
          v25 = (PRTL_RESOURCE *)((char *)v20 + v22 + 360);
          RtlAcquireResourceShared(*v25, 1u);
LABEL_36:
          v27 = v26;
          v28 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)v26 + 47);
          while ( v28 )
          {
            v29 = SubPkgTable_CompareNames(v19, v28);
            if ( v29 >= 0 )
            {
              if ( v29 <= 0 )
              {
LABEL_54:
                DerefSubPackage((PRTL_RESOURCE *)((char *)g_pPlugins + v22), (struct _ApPluginSubPkg *)v28);
                v10 = (char *)g_pPlugins + v22;
                goto LABEL_57;
              }
              v28 = v28->Children[1];
            }
            else
            {
              v28 = v28->Children[0];
            }
          }
          v30 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)v27 + 48);
          if ( v30 )
          {
            while ( 1 )
            {
              v31 = SubPkgTable_CompareDnsNames(v19, v30);
              if ( v31 >= 0 )
              {
                if ( v31 <= 0 )
                {
                  v28 = v30 - 1;
                  goto LABEL_54;
                }
                v30 = v30->Children[1];
              }
              else
              {
                v30 = v30->Children[0];
              }
              if ( !v30 )
                goto LABEL_52;
            }
          }
          goto LABEL_52;
        }
        RtlInitUnicodeString(&DestinationString, v19);
        RtlInitUnicodeString(&String2, v23);
        v24 = RtlCompareUnicodeString(&DestinationString, &String2, 1u);
      }
      if ( !v24 )
      {
        v20 = g_pPlugins;
LABEL_56:
        v10 = (char *)v20 + v22;
LABEL_57:
        v9 = a1;
        v8 = a2;
        v5 = a5;
        v7 = a3;
LABEL_58:
        if ( (v10[160] & 4) != 0 )
        {
          LogonCredsFromIdentityEx2 = -2146893039;
          v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v42) = 661;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            2148074257LL,
            v32,
            v42,
            "Surrogate Plugins not allowed to log in",
            &Class);
          goto LABEL_75;
        }
        LogonCredsFromIdentityEx2 = ((__int64 (__fastcall *)(_DWORD *))g_pLsaFunctionTable->GetClientInfo)(v53);
        if ( LogonCredsFromIdentityEx2 )
        {
          v36 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v42) = 668;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCredsFromIdentityEx2, v36, v42, "GetClientInfo", &Class);
          goto LABEL_75;
        }
        if ( (v53[4] & 0x1000000) != 0 )
        {
          LogonCredsFromIdentityEx2 = -1073741558;
          v37 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v42) = 673;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225738LL, v37, v42, "Caller is terminating", &Class);
          goto LABEL_75;
        }
        LogonCredsFromIdentityEx2 = SCardConvertLegacyBufferToEx2PackedCreds(
                                      g_pLsaFunctionTable->AllocateLsaHeap,
                                      g_pLsaFunctionTable->FreeLsaHeap,
                                      (BYTE8(v50) & 0x40) != 0,
                                      *(void **)&v53[6],
                                      v9,
                                      v8,
                                      v7,
                                      &v46,
                                      &v47,
                                      &v48,
                                      0);
        if ( LogonCredsFromIdentityEx2 )
        {
          v38 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(v43) = 688;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            LogonCredsFromIdentityEx2,
            v38,
            v43,
            "SCardConvertLegacyBufferToEx2PackedCreds",
            &Class);
          goto LABEL_75;
        }
        *(_QWORD *)a4 = v47;
        *((_QWORD *)a4 + 1) = v48;
        *((_QWORD *)a4 + 2) = v46;
        *v5 = (unsigned __int16 *)SourceString;
        v47 = 0;
        v48 = 0;
        v46 = 0;
        SourceString = 0;
LABEL_74:
        LogonCredsFromIdentityEx2 = 0;
        goto LABEL_75;
      }
      v26 = (char *)g_pPlugins + v22;
      v25 = (PRTL_RESOURCE *)((char *)g_pPlugins + v22 + 360);
      RtlAcquireResourceShared(*v25, 1u);
      if ( v19 )
        goto LABEL_36;
LABEL_52:
      RtlReleaseResource(*v25);
      if ( ++v21 >= g_cPlugins )
        goto LABEL_60;
      v20 = g_pPlugins;
    }
  }
  LogonCredsFromIdentityEx2 = GetLogonCredsFromIdentityEx2((char *)a1, a2, a4, a5);
  if ( !LogonCredsFromIdentityEx2 )
    goto LABEL_74;
  v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LogonCredsFromIdentityEx2, v16, 602, "GetLogonCredsFromIdentityEx2", &Class);
LABEL_77:
  if ( v47 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v48 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( SourceString )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  v39 = v46;
  if ( v46 )
  {
    v40 = *((unsigned __int16 *)v46 + 1);
    if ( *((_WORD *)v46 + 1) )
    {
      do
      {
        *(_BYTE *)v39 = 0;
        v39 = (struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *)((char *)v39 + 1);
        --v40;
      }
      while ( v40 );
    }
    ((void (__fastcall *)(struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *))g_pLsaFunctionTable->FreeLsaHeap)(v46);
  }
  return LogonCredsFromIdentityEx2;
}

```

## disassembly

```asm
0x180022f80  mov     [rsp-8+arg_18], rbx
0x180022f85  mov     [rsp-8+arg_10], r8
0x180022f8a  mov     [rsp-8+arg_8], edx
0x180022f8e  mov     [rsp-8+arg_0], rcx
0x180022f93  push    rbp
0x180022f94  push    rsi
0x180022f95  push    rdi
0x180022f96  push    r12
0x180022f98  push    r13
0x180022f9a  push    r14
0x180022f9c  push    r15
0x180022f9e  lea     rbp, [rsp-1Fh]
0x180022fa3  sub     rsp, 0E0h
0x180022faa  mov     r15, [rbp+4Fh+arg_20]
0x180022fae  xor     ebx, ebx
0x180022fb0  xorps   xmm0, xmm0
0x180022fb3  mov     [rbp+4Fh+var_58], ebx
0x180022fb6  xor     eax, eax
0x180022fb8  mov     qword ptr [rbp+4Fh+String2.Length], rbx
0x180022fbc  mov     [rbp+4Fh+var_70], rax
0x180022fc0  mov     r13, r9
0x180022fc3  mov     [rbp+4Fh+var_A0], rbx
0x180022fc7  mov     r12, r8
0x180022fca  mov     [rbp+4Fh+var_98], rbx
0x180022fce  mov     r14d, edx
0x180022fd1  mov     [rbp+4Fh+SourceString], rbx
0x180022fd5  mov     rsi, rcx
0x180022fd8  mov     [rbp+4Fh+var_A8], rbx
0x180022fdc  mov     edi, ebx
0x180022fde  movups  xmmword ptr [r9], xmm0
0x180022fe2  mov     [r9+10h], rax
0x180022fe6  mov     [r15], rbx
0x180022fe9  movups  [rbp+4Fh+var_54], xmm0
0x180022fed  movups  [rbp+4Fh+var_80], xmm0
0x180022ff1  movups  [rbp+4Fh+var_54+0Ch], xmm0
0x180022ff5  cmp     edx, 4
0x180022ff8  jnb     short loc_180023060
0x180022ffa  mov     ebx, 0C000000Dh
0x180022fff  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x180023006  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18002300d  nop     dword ptr [rax]
0x180023010  movzx   eax, byte ptr [r9-1]
0x180023015  mov     rdx, r9
0x180023018  dec     r9
0x18002301b  cmp     al, 5Ch ; '\'
0x18002301d  jz      short loc_180023026
0x18002301f  cmp     r9, rcx
0x180023022  ja      short loc_180023010
0x180023024  cmp     al, 5Ch ; '\'
0x180023026  lea     rax, Class
0x18002302d  mov     [rsp+110h+var_E0], rax
0x180023032  lea     rax, aInvalidBufferL; "Invalid Buffer length"
0x180023039  mov     qword ptr [rsp+110h+var_E8], rax
0x18002303e  mov     dword ptr [rsp+110h+var_F0], 250h
0x180023046  cmovz   r9, rdx
0x18002304a  mov     r8d, ebx
0x18002304d  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180023054  xor     ecx, ecx
0x180023056  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002305b  jmp     loc_180023655
0x180023060  cmp     dword ptr [rcx], 201h
0x180023066  jnz     short loc_1800230B1
0x180023068  mov     r9, r15; unsigned __int16 **
0x18002306b  mov     r8, r13; struct _DECRYPTED_AUTH_DATA *
0x18002306e  call    ?GetLogonCredsFromIdentityEx2@@YAJPEAXKPEAU_DECRYPTED_AUTH_DATA@@PEAPEAG@Z; GetLogonCredsFromIdentityEx2(void *,ulong,_DECRYPTED_AUTH_DATA *,ushort * *)
0x180023073  mov     ebx, eax
0x180023075  test    eax, eax
0x180023077  jz      short loc_1800230AA
0x180023079  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180023080  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180023085  mov     r9, rax
0x180023088  lea     rax, Class
0x18002308f  mov     [rsp+110h+var_E0], rax
0x180023094  lea     rax, aGetlogoncredsf_0; "GetLogonCredsFromIdentityEx2"
0x18002309b  mov     qword ptr [rsp+110h+var_E8], rax
0x1800230a0  mov     dword ptr [rsp+110h+var_F0], 25Ah
0x1800230a8  jmp     short loc_18002304A
0x1800230aa  xor     ecx, ecx
0x1800230ac  jmp     loc_180023641
0x1800230b1  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800230b8  lea     rcx, [rbp+4Fh+var_80]
0x1800230bc  mov     rax, [rax+0C0h]
0x1800230c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230c8  test    al, al
0x1800230ca  jnz     short loc_180023105
0x1800230cc  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800230d3  mov     ebx, 0C00000E5h
0x1800230d8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800230dd  mov     r9, rax
0x1800230e0  lea     rax, Class
0x1800230e7  mov     [rsp+110h+var_E0], rax
0x1800230ec  lea     rax, aGetcallinfo; "GetCallInfo"
0x1800230f3  mov     qword ptr [rsp+110h+var_E8], rax
0x1800230f8  mov     dword ptr [rsp+110h+var_F0], 261h
0x180023100  jmp     loc_18002304A
0x180023105  mov     rcx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002310c  lea     rax, [rbp+4Fh+SourceString]
0x180023110  mov     r8d, dword ptr [rbp+4Fh+var_80+8]
0x180023114  xor     r9d, r9d; void *
0x180023117  mov     [rsp+110h+var_C0], rax; unsigned __int16 **
0x18002311c  mov     [rsp+110h+var_C8], rbx; unsigned __int16 **
0x180023121  mov     rdx, [rcx+30h]; void (*)(void *)
0x180023125  mov     rcx, [rcx+28h]; void *(*)(unsigned int)
0x180023129  mov     [rsp+110h+var_D0], rbx; unsigned __int16 **
0x18002312e  mov     [rsp+110h+var_D8], rbx; struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS **
0x180023133  shr     r8d, 6
0x180023137  mov     [rsp+110h+var_E0], r12; void *
0x18002313c  and     r8b, 1; bool
0x180023140  mov     [rsp+110h+var_E8], r14d; unsigned int
0x180023145  mov     [rsp+110h+var_F0], rsi; struct _KERB_CERTIFICATE_LOGON *
0x18002314a  call    ?SCardConvertLegacyBufferToEx2PackedCreds@@YAJP6APEAXK@ZP6AXPEAX@Z_N11K1PEAPEAU_SEC_WINNT_AUTH_PACKED_CREDENTIALS@@PEAPEAG55@Z; SCardConvertLegacyBufferToEx2PackedCreds(void * (*)(ulong),void (*)(void *),bool,void *,void *,ulong,void *,_SEC_WINNT_AUTH_PACKED_CREDENTIALS * *,ushort * *,ushort * *,ushort * *)
0x18002314f  mov     ebx, eax
0x180023151  test    eax, eax
0x180023153  jz      short loc_1800231AB
0x180023155  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x18002315c  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180023163  nop     dword ptr [rax+00h]
0x180023167  nop     word ptr [rax+rax+00000000h]
0x180023170  movzx   eax, byte ptr [r9-1]
0x180023175  mov     rdx, r9
0x180023178  dec     r9
0x18002317b  cmp     al, 5Ch ; '\'
0x18002317d  jz      short loc_180023186
0x18002317f  cmp     r9, rcx
0x180023182  ja      short loc_180023170
0x180023184  cmp     al, 5Ch ; '\'
0x180023186  lea     rax, Class
0x18002318d  mov     [rsp+110h+var_E0], rax
0x180023192  lea     rax, aScardconvertle; "SCardConvertLegacyBufferToEx2PackedCred"...
0x180023199  mov     qword ptr [rsp+110h+var_E8], rax
0x18002319e  mov     dword ptr [rsp+110h+var_F0], 275h
0x1800231a6  jmp     loc_180023046
0x1800231ab  mov     rdi, [rbp+4Fh+SourceString]
0x1800231af  test    rdi, rdi
0x1800231b2  jz      loc_180023417
0x1800231b8  xor     eax, eax
0x1800231ba  cmp     ax, [rdi]
0x1800231bd  jz      loc_180023417
0x1800231c3  mov     dl, 1; Wait
0x1800231c5  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x1800231cc  call    cs:__imp_RtlAcquireResourceShared
0x1800231d2  mov     rcx, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x1800231d9  test    rcx, rcx
0x1800231dc  jz      loc_1800233D1
0x1800231e2  xor     r12d, r12d
0x1800231e5  cmp     cs:?g_cPlugins@@3KA, r12d; ulong g_cPlugins
0x1800231ec  jbe     loc_1800233D1
0x1800231f2  mov     eax, r12d
0x1800231f5  lea     rbx, [rcx+18h]
0x1800231f9  imul    r15, rax, 188h
0x180023200  xorps   xmm0, xmm0
0x180023203  xorps   xmm1, xmm1
0x180023206  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x18002320a  movups  xmmword ptr [rbp+4Fh+String2.Length], xmm1
0x18002320e  mov     eax, cs:?g_ulTestFlags@@3KA; ulong g_ulTestFlags
0x180023214  add     rbx, r15
0x180023217  test    al, 2
0x180023219  jz      short loc_180023229
0x18002321b  mov     rdx, rbx
0x18002321e  mov     rcx, rdi
0x180023221  call    cs:__imp__o__wcsicmp
0x180023227  jmp     short loc_180023299
0x180023229  test    rdi, rdi
0x18002322c  jnz     short loc_180023251
0x18002322e  test    rbx, rbx
0x180023231  jz      loc_180023377
0x180023237  lea     r14, [rcx+168h]
0x18002323e  mov     dl, 1; Wait
0x180023240  add     r14, r15
0x180023243  mov     rcx, [r14]; Resource
0x180023246  call    cs:__imp_RtlAcquireResourceShared
0x18002324c  jmp     loc_180023329
0x180023251  test    rbx, rbx
0x180023254  jnz     short loc_18002326E
0x180023256  lea     rbx, [r15+rcx]
0x18002325a  mov     dl, 1; Wait
0x18002325c  lea     r14, [rbx+168h]
0x180023263  mov     rcx, [r14]; Resource
0x180023266  call    cs:__imp_RtlAcquireResourceShared
0x18002326c  jmp     short loc_1800232C2
0x18002326e  mov     rdx, rdi; SourceString
0x180023271  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x180023275  call    cs:__imp_RtlInitUnicodeString
0x18002327b  mov     rdx, rbx; SourceString
0x18002327e  lea     rcx, [rbp+4Fh+String2]; DestinationString
0x180023282  call    cs:__imp_RtlInitUnicodeString
0x180023288  mov     r8b, 1; CaseInsensitive
0x18002328b  lea     rdx, [rbp+4Fh+String2]; String2
0x18002328f  lea     rcx, [rbp+4Fh+DestinationString]; String1
0x180023293  call    cs:__imp_RtlCompareUnicodeString
0x180023299  test    eax, eax
0x18002329b  jz      loc_180023370
0x1800232a1  mov     rbx, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x1800232a8  mov     dl, 1; Wait
0x1800232aa  add     rbx, r15
0x1800232ad  lea     r14, [rbx+168h]
0x1800232b4  mov     rcx, [r14]; Resource
0x1800232b7  call    cs:__imp_RtlAcquireResourceShared
0x1800232bd  test    rdi, rdi
0x1800232c0  jz      short loc_180023329
0x1800232c2  mov     rsi, rbx
0x1800232c5  mov     rbx, [rbx+178h]
0x1800232cc  test    rbx, rbx
0x1800232cf  jz      short loc_1800232F7
0x1800232d1  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x1800232d4  mov     rcx, rdi; SourceString
0x1800232d7  call    ?SubPkgTable_CompareNames@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; SubPkgTable_CompareNames(void *,_RTL_BALANCED_NODE *)
0x1800232dc  test    eax, eax
0x1800232de  jns     short loc_1800232E5
0x1800232e0  mov     rbx, [rbx]
0x1800232e3  jmp     short loc_1800232EB
0x1800232e5  jle     short loc_1800232F2
0x1800232e7  mov     rbx, [rbx+8]
0x1800232eb  test    rbx, rbx
0x1800232ee  jnz     short loc_1800232D1
0x1800232f0  jmp     short loc_1800232F7
0x1800232f2  test    rbx, rbx
0x1800232f5  jnz     short loc_180023352
0x1800232f7  mov     rbx, [rsi+180h]
0x1800232fe  test    rbx, rbx
0x180023301  jz      short loc_180023329
0x180023303  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x180023306  mov     rcx, rdi; void *
0x180023309  call    ?SubPkgTable_CompareDnsNames@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; SubPkgTable_CompareDnsNames(void *,_RTL_BALANCED_NODE *)
0x18002330e  test    eax, eax
0x180023310  jns     short loc_180023317
0x180023312  mov     rbx, [rbx]
0x180023315  jmp     short loc_18002331D
0x180023317  jle     short loc_180023324
0x180023319  mov     rbx, [rbx+8]
0x18002331d  test    rbx, rbx
0x180023320  jnz     short loc_180023303
0x180023322  jmp     short loc_180023329
0x180023324  test    rbx, rbx
0x180023327  jnz     short loc_18002334E
0x180023329  mov     rcx, [r14]; Resource
0x18002332c  call    cs:__imp_RtlReleaseResource
0x180023332  inc     r12d
0x180023335  cmp     r12d, cs:?g_cPlugins@@3KA; ulong g_cPlugins
0x18002333c  jnb     loc_1800233D1
0x180023342  mov     rcx, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x180023349  jmp     loc_1800231F2
0x18002334e  add     rbx, 0FFFFFFFFFFFFFFE8h
0x180023352  mov     rcx, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x180023359  mov     rdx, rbx; struct _ApPluginSubPkg *
0x18002335c  add     rcx, r15; struct _ApPluginPkg *
0x18002335f  call    ?DerefSubPackage@@YAXPEAU_ApPluginPkg@@PEAU_ApPluginSubPkg@@@Z; DerefSubPackage(_ApPluginPkg *,_ApPluginSubPkg *)
0x180023364  mov     rdi, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x18002336b  add     rdi, r15
0x18002336e  jmp     short loc_18002337B
0x180023370  mov     rcx, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x180023377  lea     rdi, [r15+rcx]
0x18002337b  mov     rsi, [rbp+4Fh+arg_0]
0x18002337f  mov     r14d, [rbp+4Fh+arg_8]
0x180023383  mov     r15, [rbp+4Fh+arg_20]
0x180023387  mov     r12, [rbp+4Fh+arg_10]
0x18002338b  test    byte ptr [rdi+0A0h], 4
0x180023392  jz      loc_1800234F2
0x180023398  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18002339f  mov     ebx, 80090311h
0x1800233a4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800233a9  mov     r9, rax
0x1800233ac  lea     rax, Class
0x1800233b3  mov     [rsp+110h+var_E0], rax
0x1800233b8  lea     rax, aSurrogatePlugi; "Surrogate Plugins not allowed to log in"
0x1800233bf  mov     qword ptr [rsp+110h+var_E8], rax
0x1800233c4  mov     dword ptr [rsp+110h+var_F0], 295h
0x1800233cc  jmp     loc_1800234DC
0x1800233d1  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x1800233d8  call    cs:__imp_RtlReleaseResource
0x1800233de  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800233e5  mov     ebx, 80090311h
0x1800233ea  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800233ef  mov     r9, rax
0x1800233f2  lea     rax, Class
0x1800233f9  mov     [rsp+110h+var_E0], rax
0x1800233fe  lea     rax, aRefpackagebypr; "RefPackageByProvName"
0x180023405  mov     qword ptr [rsp+110h+var_E8], rax
0x18002340a  mov     dword ptr [rsp+110h+var_F0], 28Fh
0x180023412  jmp     loc_18002304A
0x180023417  lea     rcx, [rbp+4Fh+String2]; struct _ApPluginPkg **
0x18002341b  call    ?RefDefaultPackage@@YAJPEAPEAU_ApPluginPkg@@@Z; RefDefaultPackage(_ApPluginPkg * *)
0x180023420  mov     ebx, eax
0x180023422  test    eax, eax
0x180023424  jz      short loc_18002346F
0x180023426  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18002342d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180023432  mov     r9, rax
0x180023435  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002343c  lea     rax, Class
0x180023443  mov     r8d, ebx
0x180023446  mov     [rsp+110h+var_E0], rax
0x18002344b  xor     ecx, ecx
0x18002344d  lea     rax, aRefdefaultpack; "RefDefaultPackage"
0x180023454  mov     qword ptr [rsp+110h+var_E8], rax
0x180023459  mov     dword ptr [rsp+110h+var_F0], 27Ch
0x180023461  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180023466  mov     rdi, qword ptr [rbp+4Fh+String2.Length]
0x18002346a  jmp     loc_180023643
0x18002346f  mov     rcx, [rbp+4Fh+SourceString]
  ... truncated ...
```
