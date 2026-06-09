# MigrateTBALPwd(_GUID const *,ushort const *,ushort const *)

- ea: `0x18005b1a4`
- end: `0x18005b593`
- name: `?MigrateTBALPwd@@YAJPEBU_GUID@@PEBG1@Z`
- size: `1007`
- prototype: `__int64 __fastcall(UUID *Uuid, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180055eb0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18002d71c`
- `0x18005b1a4`
- `0x180081010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18005b23f`
- `ntdll!RtlInitUnicodeString` at `0x18005b37d`
- `ntdll!RtlInitUnicodeString` at `0x18005b23f`
- `ntdll!RtlInitUnicodeString` at `0x18005b37d`
- `LSASRV!LsarClose` at `0x18005b536`
- `LSASRV!LsarClose` at `0x18005b547`
- `LSASRV!LsarClose` at `0x18005b536`
- `LSASRV!LsarClose` at `0x18005b547`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x18005b576`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x18005b576`
- `LSASRV!LsarQuerySecret` at `0x18005b2ad`
- `LSASRV!LsarQuerySecret` at `0x18005b2ad`
- `LSASRV!LsarDeleteObject` at `0x18005b47d`
- `LSASRV!LsarDeleteObject` at `0x18005b47d`
- `LSASRV!LsarSetSecret` at `0x18005b443`
- `LSASRV!LsarSetSecret` at `0x18005b443`
- `LSASRV!LsarCreateSecret` at `0x18005b3ff`
- `LSASRV!LsarCreateSecret` at `0x18005b3ff`
- `LSASRV!LsarOpenSecret` at `0x18005b25a`
- `LSASRV!LsarOpenSecret` at `0x18005b398`
- `LSASRV!LsarOpenSecret` at `0x18005b25a`
- `LSASRV!LsarOpenSecret` at `0x18005b398`

## string_xrefs

- `0x18005b203`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18005b266`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18005b2b9`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18005b329`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18005b3b4`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18005b40b`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18005b44f`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18005b489`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18005b4b3`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18005b41f`: `LsarCreateSecret`
- `0x18005b49d`: `LsarDeleteObject`
- `0x18005b281`: `LsarOpenSecret`

## pseudocode

```c
__int64 __fastcall MigrateTBALPwd(UUID *Uuid, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  PCWSTR v4; // rsi
  unsigned int LSASecretName; // ebx
  const char *v7; // r9
  const char *v8; // r9
  const char *v9; // r9
  const char *v10; // rax
  const char *v11; // rax
  __int64 v12; // r8
  const char *v13; // r9
  const char *v14; // r9
  const char *v15; // r9
  const char *v16; // r9
  _BYTE *v17; // rax
  __int64 v18; // rdx
  bool v20[8]; // [rsp+20h] [rbp-50h]
  bool v21[8]; // [rsp+20h] [rbp-50h]
  bool v22[8]; // [rsp+20h] [rbp-50h]
  __int64 v23; // [rsp+40h] [rbp-30h] BYREF
  unsigned int *v24; // [rsp+48h] [rbp-28h] BYREF
  PCWSTR SourceString; // [rsp+50h] [rbp-20h] BYREF
  PCWSTR v26; // [rsp+58h] [rbp-18h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  __int64 v28; // [rsp+A8h] [rbp+38h] BYREF

  v24 = 0;
  v28 = 0;
  v4 = 0;
  v23 = 0;
  v26 = 0;
  SourceString = 0;
  DestinationString = 0;
  LSASecretName = GetLSASecretName(Uuid, a2, (unsigned __int16 **)&SourceString, 0, 1);
  if ( LSASecretName )
  {
    v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
    *(_DWORD *)v20 = 694;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v7, *(_QWORD *)v20, "GetLSASecretName", &Class);
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    LSASecretName = LsarOpenSecret(g_LsaPolicyHandle, &DestinationString, 2, &v28);
    if ( LSASecretName )
    {
      v8 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
      *(_DWORD *)v20 = 702;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v8, *(_QWORD *)v20, "LsarOpenSecret", &Class);
    }
    else
    {
      LSASecretName = LsarQuerySecret(v28, &v24, 0, 0, 0);
      if ( LSASecretName )
      {
        v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
        *(_DWORD *)v21 = 710;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v9, *(_QWORD *)v21, "LsarQuerySecret", &Class);
      }
      else if ( v24 && *((_QWORD *)v24 + 1) && *v24 )
      {
        LSASecretName = GetLSASecretName(Uuid, a3, (unsigned __int16 **)&v26, 0, 0);
        if ( LSASecretName )
        {
          v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
          *(_DWORD *)v22 = 726;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v10, *(_QWORD *)v22, "GetLSASecretName", &Class);
          v4 = v26;
        }
        else
        {
          v4 = v26;
          RtlInitUnicodeString(&DestinationString, v26);
          if ( (unsigned int)LsarOpenSecret(g_LsaPolicyHandle, &DestinationString, 3, &v23) == -1073741772
            && (v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp"),
                *(_DWORD *)v22 = 737,
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v12, v11, *(_QWORD *)v22, "TBAL secret not found", &Class),
                (LSASecretName = LsarCreateSecret(g_LsaPolicyHandle, &DestinationString, 983043, &v23)) != 0) )
          {
            v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
            *(_DWORD *)v22 = 744;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v13, *(_QWORD *)v22, "LsarCreateSecret", &Class);
          }
          else
          {
            LSASecretName = LsarSetSecret(v23, v24, 0);
            if ( LSASecretName )
            {
              v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
              *(_DWORD *)v22 = 751;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v14, *(_QWORD *)v22, "LsarSetSecret", &Class);
            }
            else
            {
              LSASecretName = LsarDeleteObject(&v28);
              if ( LSASecretName )
              {
                v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
                *(_DWORD *)v22 = 755;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v15, *(_QWORD *)v22, "LsarDeleteObject", &Class);
              }
            }
          }
        }
      }
      else
      {
        LSASecretName = -1073740943;
        v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
        *(_DWORD *)v21 = 717;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221226353LL, v16, *(_QWORD *)v21, "No TBAL Secret", &Class);
      }
    }
  }
  if ( SourceString )
    ((void (__fastcall *)(PCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(SourceString);
  if ( v4 )
    ((void (__fastcall *)(PCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v4);
  if ( v28 )
    LsarClose(&v28);
  if ( v23 )
    LsarClose(&v23);
  if ( v24 )
  {
    v17 = (_BYTE *)*((_QWORD *)v24 + 1);
    if ( v17 )
    {
      v18 = *v24;
      if ( *v24 )
      {
        do
        {
          *v17++ = 0;
          --v18;
        }
        while ( v18 );
      }
    }
    LsaIFree_LSAPR_CR_CIPHER_VALUE();
  }
  return LSASecretName;
}

```

## disassembly

```asm
0x18005b1a4  mov     [rsp-18h+arg_0], rbx
0x18005b1a9  mov     [rsp-18h+arg_8], rsi
0x18005b1ae  push    rbp
0x18005b1af  push    rdi
0x18005b1b0  push    r15
0x18005b1b2  mov     rbp, rsp
0x18005b1b5  sub     rsp, 70h
0x18005b1b9  mov     r15, r8
0x18005b1bc  mov     [rbp+var_28], 0
0x18005b1c4  xorps   xmm0, xmm0
0x18005b1c7  mov     [rbp+arg_18], 0
0x18005b1cf  xor     esi, esi
0x18005b1d1  mov     [rbp+var_30], 0
0x18005b1d9  lea     r8, [rbp+SourceString]; unsigned __int16 **
0x18005b1dd  mov     [rbp+var_18], rsi
0x18005b1e1  xor     r9d, r9d; bool
0x18005b1e4  mov     [rbp+SourceString], 0
0x18005b1ec  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18005b1f0  mov     rdi, rcx
0x18005b1f3  mov     [rsp+70h+var_50], 1; bool
0x18005b1f8  call    ?GetLSASecretName@@YAJPEBU_GUID@@PEBGPEAPEAG_N3@Z; GetLSASecretName(_GUID const *,ushort const *,ushort * *,bool,bool)
0x18005b1fd  mov     ebx, eax
0x18005b1ff  test    eax, eax
0x18005b201  jz      short loc_18005B237
0x18005b203  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18005b20a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005b20f  mov     r9, rax
0x18005b212  lea     rdi, Class
0x18005b219  mov     [rsp+70h+var_40], rdi
0x18005b21e  lea     rax, aGetlsasecretna; "GetLSASecretName"
0x18005b225  mov     [rsp+70h+var_48], rax
0x18005b22a  mov     dword ptr [rsp+70h+var_50], 2B6h
0x18005b232  jmp     loc_18005B4E7
0x18005b237  mov     rdx, [rbp+SourceString]; SourceString
0x18005b23b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005b23f  call    cs:__imp_RtlInitUnicodeString
0x18005b245  mov     rcx, cs:?g_LsaPolicyHandle@@3PEAXEA; void * g_LsaPolicyHandle
0x18005b24c  lea     r9, [rbp+arg_18]
0x18005b250  mov     r8d, 2
0x18005b256  lea     rdx, [rbp+DestinationString]
0x18005b25a  call    cs:__imp_LsarOpenSecret
0x18005b260  mov     ebx, eax
0x18005b262  test    eax, eax
0x18005b264  jz      short loc_18005B29A
0x18005b266  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18005b26d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005b272  mov     r9, rax
0x18005b275  lea     rdi, Class
0x18005b27c  mov     [rsp+70h+var_40], rdi
0x18005b281  lea     rax, aLsaropensecret_0; "LsarOpenSecret"
0x18005b288  mov     [rsp+70h+var_48], rax
0x18005b28d  mov     dword ptr [rsp+70h+var_50], 2BEh
0x18005b295  jmp     loc_18005B4E7
0x18005b29a  mov     rcx, [rbp+arg_18]
0x18005b29e  lea     rdx, [rbp+var_28]
0x18005b2a2  xor     r9d, r9d
0x18005b2a5  mov     qword ptr [rsp+70h+var_50], rsi
0x18005b2aa  xor     r8d, r8d
0x18005b2ad  call    cs:__imp_LsarQuerySecret
0x18005b2b3  mov     ebx, eax
0x18005b2b5  test    eax, eax
0x18005b2b7  jz      short loc_18005B2ED
0x18005b2b9  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18005b2c0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005b2c5  mov     r9, rax
0x18005b2c8  lea     rdi, Class
0x18005b2cf  mov     [rsp+70h+var_40], rdi
0x18005b2d4  lea     rax, aLsarquerysecre; "LsarQuerySecret"
0x18005b2db  mov     [rsp+70h+var_48], rax
0x18005b2e0  mov     dword ptr [rsp+70h+var_50], 2C6h
0x18005b2e8  jmp     loc_18005B4E7
0x18005b2ed  mov     rax, [rbp+var_28]
0x18005b2f1  test    rax, rax
0x18005b2f4  jz      loc_18005B4B3
0x18005b2fa  cmp     [rax+8], rsi
0x18005b2fe  jz      loc_18005B4B3
0x18005b304  cmp     [rax], esi
0x18005b306  jz      loc_18005B4B3
0x18005b30c  xor     r9d, r9d; bool
0x18005b30f  mov     [rsp+70h+var_50], sil; bool
0x18005b314  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18005b318  mov     rdx, r15; unsigned __int16 *
0x18005b31b  mov     rcx, rdi; Uuid
0x18005b31e  call    ?GetLSASecretName@@YAJPEBU_GUID@@PEBGPEAPEAG_N3@Z; GetLSASecretName(_GUID const *,ushort const *,ushort * *,bool,bool)
0x18005b323  mov     ebx, eax
0x18005b325  test    eax, eax
0x18005b327  jz      short loc_18005B372
0x18005b329  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18005b330  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005b335  mov     r9, rax
0x18005b338  lea     rdi, Class
0x18005b33f  lea     rax, aGetlsasecretna; "GetLSASecretName"
0x18005b346  mov     [rsp+70h+var_40], rdi
0x18005b34b  mov     [rsp+70h+var_48], rax
0x18005b350  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005b357  mov     r8d, ebx
0x18005b35a  mov     dword ptr [rsp+70h+var_50], 2D6h
0x18005b362  xor     ecx, ecx
0x18005b364  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005b369  mov     rsi, [rbp+var_18]
0x18005b36d  jmp     loc_18005B4F8
0x18005b372  mov     rsi, [rbp+var_18]
0x18005b376  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005b37a  mov     rdx, rsi; SourceString
0x18005b37d  call    cs:__imp_RtlInitUnicodeString
0x18005b383  mov     rcx, cs:?g_LsaPolicyHandle@@3PEAXEA; void * g_LsaPolicyHandle
0x18005b38a  lea     r9, [rbp+var_30]
0x18005b38e  mov     r8d, 3
0x18005b394  lea     rdx, [rbp+DestinationString]
0x18005b398  call    cs:__imp_LsarOpenSecret
0x18005b39e  mov     r8d, 0C0000034h
0x18005b3a4  lea     rdi, Class
0x18005b3ab  cmp     eax, r8d
0x18005b3ae  jnz     loc_18005B438
0x18005b3b4  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18005b3bb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005b3c0  mov     r9, rax
0x18005b3c3  mov     [rsp+70h+var_40], rdi
0x18005b3c8  lea     rax, aTbalSecretNotF; "TBAL secret not found"
0x18005b3cf  xor     ecx, ecx
0x18005b3d1  mov     [rsp+70h+var_48], rax
0x18005b3d6  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005b3dd  mov     dword ptr [rsp+70h+var_50], 2E1h
0x18005b3e5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005b3ea  mov     rcx, cs:?g_LsaPolicyHandle@@3PEAXEA; void * g_LsaPolicyHandle
0x18005b3f1  lea     r9, [rbp+var_30]
0x18005b3f5  mov     r8d, 0F0003h
0x18005b3fb  lea     rdx, [rbp+DestinationString]
0x18005b3ff  call    cs:__imp_LsarCreateSecret
0x18005b405  mov     ebx, eax
0x18005b407  test    eax, eax
0x18005b409  jz      short loc_18005B438
0x18005b40b  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18005b412  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005b417  mov     [rsp+70h+var_40], rdi
0x18005b41c  mov     r9, rax
0x18005b41f  lea     rax, aLsarcreatesecr; "LsarCreateSecret"
0x18005b426  mov     [rsp+70h+var_48], rax
0x18005b42b  mov     dword ptr [rsp+70h+var_50], 2E8h
0x18005b433  jmp     loc_18005B4E7
0x18005b438  mov     rdx, [rbp+var_28]
0x18005b43c  xor     r8d, r8d
0x18005b43f  mov     rcx, [rbp+var_30]
0x18005b443  call    cs:__imp_LsarSetSecret
0x18005b449  mov     ebx, eax
0x18005b44b  test    eax, eax
0x18005b44d  jz      short loc_18005B479
0x18005b44f  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18005b456  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005b45b  mov     [rsp+70h+var_40], rdi
0x18005b460  mov     r9, rax
0x18005b463  lea     rax, aLsarsetsecret; "LsarSetSecret"
0x18005b46a  mov     [rsp+70h+var_48], rax
0x18005b46f  mov     dword ptr [rsp+70h+var_50], 2EFh
0x18005b477  jmp     short loc_18005B4E7
0x18005b479  lea     rcx, [rbp+arg_18]
0x18005b47d  call    cs:__imp_LsarDeleteObject
0x18005b483  mov     ebx, eax
0x18005b485  test    eax, eax
0x18005b487  jz      short loc_18005B4F8
0x18005b489  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18005b490  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005b495  mov     [rsp+70h+var_40], rdi
0x18005b49a  mov     r9, rax
0x18005b49d  lea     rax, aLsardeleteobje_0; "LsarDeleteObject"
0x18005b4a4  mov     [rsp+70h+var_48], rax
0x18005b4a9  mov     dword ptr [rsp+70h+var_50], 2F3h
0x18005b4b1  jmp     short loc_18005B4E7
0x18005b4b3  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18005b4ba  mov     ebx, 0C0000371h
0x18005b4bf  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005b4c4  mov     r9, rax
0x18005b4c7  lea     rdi, Class
0x18005b4ce  mov     [rsp+70h+var_40], rdi
0x18005b4d3  lea     rax, aNoTbalSecret; "No TBAL Secret"
0x18005b4da  mov     [rsp+70h+var_48], rax
0x18005b4df  mov     dword ptr [rsp+70h+var_50], 2CDh
0x18005b4e7  mov     r8d, ebx
0x18005b4ea  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005b4f1  xor     ecx, ecx
0x18005b4f3  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005b4f8  cmp     [rbp+SourceString], 0
0x18005b4fd  jz      short loc_18005B513
0x18005b4ff  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005b506  mov     rcx, [rbp+SourceString]
0x18005b50a  mov     rax, [rax+30h]
0x18005b50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b513  test    rsi, rsi
0x18005b516  jz      short loc_18005B52B
0x18005b518  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005b51f  mov     rcx, rsi
0x18005b522  mov     rax, [rax+30h]
0x18005b526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b52b  cmp     [rbp+arg_18], 0
0x18005b530  jz      short loc_18005B53C
0x18005b532  lea     rcx, [rbp+arg_18]
0x18005b536  call    cs:__imp_LsarClose
0x18005b53c  cmp     [rbp+var_30], 0
0x18005b541  jz      short loc_18005B54D
0x18005b543  lea     rcx, [rbp+var_30]
0x18005b547  call    cs:__imp_LsarClose
0x18005b54d  mov     rcx, [rbp+var_28]
0x18005b551  test    rcx, rcx
0x18005b554  jz      short loc_18005B57C
0x18005b556  mov     rax, [rcx+8]
0x18005b55a  test    rax, rax
0x18005b55d  jz      short loc_18005B576
0x18005b55f  mov     edx, [rcx]
0x18005b561  test    rdx, rdx
0x18005b564  jz      short loc_18005B576
0x18005b566  mov     byte ptr [rax], 0
0x18005b569  inc     rax
0x18005b56c  sub     rdx, 1
0x18005b570  jnz     short loc_18005B566
0x18005b572  mov     rcx, [rbp+var_28]
0x18005b576  call    cs:__imp_LsaIFree_LSAPR_CR_CIPHER_VALUE
0x18005b57c  lea     r11, [rsp+70h+var_s0]
0x18005b581  mov     eax, ebx
0x18005b583  mov     rbx, [r11+20h]
0x18005b587  mov     rsi, [r11+28h]
0x18005b58b  mov     rsp, r11
0x18005b58e  pop     r15
0x18005b590  pop     rdi
0x18005b591  pop     rbp
0x18005b592  retn
```
