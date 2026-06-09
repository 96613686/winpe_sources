# MakePrimaryCredentials(_LUID *,bool,_APPLUGIN_USER_INFO *,ushort *,_ApPluginPkg *,ushort const *,_SEC_WINNT_AUTH_PACKED_CREDENTIALS *,_DPAPI_DECODED_AUTH_DATA *,_SECPKG_PRIMARY_CRED_EX *)

- ea: `0x180027a10`
- end: `0x1800281b9`
- name: `?MakePrimaryCredentials@@YAJPEAU_LUID@@_NPEAU_APPLUGIN_USER_INFO@@PEAGPEAU_ApPluginPkg@@PEBGPEAU_SEC_WINNT_AUTH_PACKED_CREDENTIALS@@PEAU_DPAPI_DECODED_AUTH_DATA@@PEAU_SECPKG_PRIMARY_CRED_EX@@@Z`
- size: `1961`
- prototype: `int(struct _LUID *, bool, struct _APPLUGIN_USER_INFO *, unsigned __int16 *, struct _ApPluginPkg *, const unsigned __int16 *, struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *, struct _DPAPI_DECODED_AUTH_DATA *, struct _SECPKG_PRIMARY_CRED_EX *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180011960`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180011494`
- `0x180027a10`
- `0x1800281c0`
- `0x180028318`
- `0x18002bff0`
- `0x18004317c`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180027e48`
- `ntdll!RtlLengthSid` at `0x180027e48`
- `ntdll!RtlInitUnicodeString` at `0x180027b28`
- `ntdll!RtlInitUnicodeString` at `0x180027b28`

## string_xrefs

- `0x180027c4e`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180027bec`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180027c8a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180027ce7`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180027d37`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180027da4`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180027df9`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180027e7b`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180027f19`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180027f9e`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180028048`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180028156`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180027eb6`: `DuplicateSID`

## pseudocode

```c
__int64 __fastcall MakePrimaryCredentials(
        struct _LUID *a1,
        char a2,
        struct _APPLUGIN_USER_INFO *a3,
        unsigned __int16 *a4,
        struct _ApPluginPkg *a5,
        const unsigned __int16 *SourceString,
        struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *Src,
        struct _DPAPI_DECODED_AUTH_DATA *a8,
        struct _SECPKG_PRIMARY_CRED_EX *a9)
{
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int64 v26; // rax
  int v27; // ebx
  __int64 v28; // rdx
  size_t Length; // rsi
  void *v30; // rax
  unsigned int v31; // esi
  const WCHAR *v32; // rcx
  unsigned int v33; // ebx
  const char *v34; // r9
  char v35; // al
  const char *v36; // rdx
  bool v37; // zf
  const char *v38; // rax
  unsigned int v39; // r10d
  __int64 v40; // r8
  int v41; // r11d
  char v42; // al
  const char *v43; // r10
  bool v44; // zf
  __int64 v45; // r8
  const WCHAR *v46; // rcx
  const WCHAR *v47; // rcx
  int v48; // ebx
  void *v49; // rsi
  size_t v50; // r14
  void *v51; // rax
  const char *v52; // r9
  char v53; // al
  const char *v54; // rdx
  bool v55; // zf
  int v56; // eax
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v57; // r14
  PLSA_ALLOCATE_LSA_HEAP AllocateLsaHeap; // rax
  size_t v59; // rsi
  void *v60; // rax
  const char *v61; // r9
  PLSA_ALLOCATE_LSA_HEAP v62; // rax
  const char *v63; // r9
  __int128 v64; // xmm1
  __int128 v65; // xmm0
  __int128 v66; // xmm1
  __int128 v67; // xmm0
  __int128 v68; // xmm1
  __int128 v69; // xmm0
  __int128 v70; // xmm1
  __int128 v71; // xmm0
  __int128 v72; // xmm1
  __int128 v73; // xmm0
  __int128 v74; // xmm1
  __int128 v75; // xmm0
  __int128 v76; // xmm1
  __int64 v78; // [rsp+20h] [rbp-E0h]
  const char *v79; // [rsp+28h] [rbp-D8h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v81; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v82[208]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v83; // [rsp+130h] [rbp+30h]
  _OWORD v84[17]; // [rsp+140h] [rbp+40h] BYREF

  v81 = 0;
  memset_0(v82, 0, 0xE0u);
  memset_0(v84, 0, 0xE0u);
  v13 = v84[1];
  *(_OWORD *)&a9->LogonId.LowPart = v84[0];
  v14 = v84[2];
  *(_OWORD *)&a9->DownlevelName.Buffer = v13;
  v15 = v84[3];
  *(_OWORD *)&a9->DomainName.Buffer = v14;
  v16 = v84[4];
  *(_OWORD *)&a9->Password.Buffer = v15;
  v17 = v84[5];
  *(_OWORD *)&a9->OldPassword.Buffer = v16;
  v18 = v84[6];
  *(_OWORD *)&a9->Flags = v17;
  v19 = v84[7];
  *(_OWORD *)&a9->DnsDomainName.Buffer = v18;
  v20 = v84[8];
  *(_OWORD *)&a9->Upn.Buffer = v19;
  v21 = v84[9];
  *(_OWORD *)&a9->LogonServer.Buffer = v20;
  v22 = v84[10];
  *(_OWORD *)&a9->Spare1.Buffer = v21;
  v23 = v84[11];
  *(_OWORD *)&a9->Spare2.Buffer = v22;
  v24 = v84[12];
  *(_OWORD *)&a9->Spare3.Buffer = v23;
  v25 = v84[13];
  *(_OWORD *)&a9->Spare4.Buffer = v24;
  *(_OWORD *)&a9->PrevLogonId.LowPart = v25;
  v26 = (__int64)*a1;
  v27 = 4096;
  *(_DWORD *)&v82[80] = 4096;
  *(_QWORD *)v82 = v26;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a4);
  *(_OWORD *)&v82[104] = 0;
  if ( DestinationString.Buffer && DestinationString.MaximumLength )
  {
    Length = DestinationString.Length;
    if ( DestinationString.Length > DestinationString.MaximumLength || (DestinationString.Length & 1) != 0 )
    {
      v31 = -1073741811;
LABEL_19:
      v38 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      WPPTraceLogA(v39, "0x%08x %s:%u : %s:%ws", v31, v38, v41, v40, &Class);
      v34 = "";
      v33 = v31;
      while ( 1 )
      {
        v42 = *(v34 - 1);
        v43 = v34--;
        v44 = v42 == 92;
        if ( v42 == 92 )
          break;
        if ( v34 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v44 = v42 == 92;
          break;
        }
      }
      v79 = "DuplicateUnicodeString3";
      if ( v44 )
        v34 = v43;
      LODWORD(v78) = 4695;
      v45 = v31;
      goto LABEL_80;
    }
    *(_DWORD *)&v82[104] = *(_DWORD *)&DestinationString.Length + 0x20000;
    v30 = (void *)((__int64 (*)(void))g_pLsaFunctionTable->AllocateLsaHeap)();
    *(_QWORD *)&v82[112] = v30;
    if ( !v30 )
    {
      v31 = -1073741801;
      goto LABEL_19;
    }
    memcpy_0(v30, DestinationString.Buffer, Length);
  }
  if ( (*((_BYTE *)a5 + 160) & 8) != 0 )
  {
    v32 = (const WCHAR *)*((_QWORD *)a3 + 9);
    if ( v32 )
    {
      v33 = DuplicateUnicodeString3(v32, (struct _UNICODE_STRING *)&v82[8]);
      if ( v33 )
      {
        v34 = "";
        while ( 1 )
        {
          v35 = *(v34 - 1);
          v36 = v34--;
          v37 = v35 == 92;
          if ( v35 == 92 )
            break;
          if ( v34 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
          {
            v37 = v35 == 92;
            break;
          }
        }
        if ( v37 )
          v34 = v36;
        v79 = "DuplicateUnicodeString3";
        LODWORD(v78) = 4705;
        goto LABEL_79;
      }
      v27 = *(_DWORD *)&v82[80];
    }
    v46 = (const WCHAR *)*((_QWORD *)a3 + 11);
    if ( v46 )
    {
      v33 = DuplicateUnicodeString3(v46, (struct _UNICODE_STRING *)&v82[88]);
      if ( v33 )
      {
        v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        v79 = "DuplicateUnicodeString3";
        LODWORD(v78) = 4714;
LABEL_79:
        v45 = v33;
LABEL_80:
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v45, v34, v78, v79, &Class);
        goto LABEL_81;
      }
      v27 = *(_DWORD *)&v82[80];
    }
    v47 = (const WCHAR *)*((_QWORD *)a3 + 10);
    if ( v47 )
    {
      v33 = DuplicateUnicodeString3(v47, (struct _UNICODE_STRING *)&v82[24]);
      if ( v33 )
      {
        v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        v79 = "DuplicateUnicodeString3";
        LODWORD(v78) = 4723;
        goto LABEL_79;
      }
      v27 = *(_DWORD *)&v82[80];
    }
    LOBYTE(v28) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers>::GetImpl'::`2'::impl,
      v28);
    v48 = v27 | 0x10000;
  }
  else
  {
    v48 = 4352;
  }
  *(_DWORD *)&v82[80] = v48;
  if ( !*(_QWORD *)&v82[16] )
  {
    v33 = DuplicateUnicodeString3(a4, (struct _UNICODE_STRING *)&v82[8]);
    if ( v33 )
    {
      v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      v79 = "DuplicateUnicodeString3";
      LODWORD(v78) = 4779;
      goto LABEL_79;
    }
    v48 = *(_DWORD *)&v82[80];
  }
  if ( !*(_QWORD *)&v82[32] )
  {
    v33 = DuplicateUnicodeString3(SourceString, (struct _UNICODE_STRING *)&v82[24]);
    if ( v33 )
    {
      v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      v79 = "DuplicateUnicodeString3";
      LODWORD(v78) = 4787;
      goto LABEL_79;
    }
    v48 = *(_DWORD *)&v82[80];
  }
  v49 = (void *)*((_QWORD *)a3 + 2);
  *(_QWORD *)&v82[72] = 0;
  if ( !v49 )
  {
LABEL_55:
    v56 = *(_DWORD *)a8;
    if ( *(_DWORD *)a8 == 1 )
    {
      v81.Buffer = (PWSTR)*((_QWORD *)a8 + 1);
      v81.MaximumLength = *((_WORD *)a8 + 2);
      v81.Length = v81.MaximumLength;
      v33 = DuplicateUnicodeString2(&v81, (struct _UNICODE_STRING *)&v82[40]);
      if ( v33 )
      {
        v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        v79 = "DuplicateUnicodeString2";
        LODWORD(v78) = 4802;
        goto LABEL_79;
      }
      v48 = *(_DWORD *)&v82[80] | 1;
      goto LABEL_75;
    }
    if ( v56 == 5 )
    {
      v48 |= 0x88000u;
      v57 = Src;
      *(_DWORD *)&v82[80] = v48;
      AllocateLsaHeap = g_pLsaFunctionTable->AllocateLsaHeap;
      v59 = *((unsigned __int16 *)Src + 1);
      *(_WORD *)&v82[138] = v59;
      *(_WORD *)&v82[136] = v59;
      v60 = (void *)((__int64 (__fastcall *)(size_t))AllocateLsaHeap)(v59);
      *(_QWORD *)&v82[144] = v60;
      if ( !v60 )
      {
        v33 = -1073741801;
        v61 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v61, 4817, "AllocateLsaHeap", &Class);
        goto LABEL_81;
      }
    }
    else
    {
      if ( v56 == 3 )
      {
        if ( (v48 & 0x10000) != 0 && (g_ulPlatformId == 10 || g_ulPlatformId == 3) )
          v48 |= 1u;
        goto LABEL_75;
      }
      if ( v56 != 4 )
      {
        if ( v56 == 7 )
        {
          v48 |= 0x100000u;
        }
        else
        {
          if ( v56 != 6 )
          {
            v33 = -1073741595;
            v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            v79 = "Cred Type should be either password or NGC";
            LODWORD(v78) = 4857;
            goto LABEL_79;
          }
          DWORD2(v83) |= 1u;
        }
        goto LABEL_75;
      }
      v48 |= 0x8040u;
      v57 = Src;
      *(_DWORD *)&v82[80] = v48;
      v62 = g_pLsaFunctionTable->AllocateLsaHeap;
      v59 = *((unsigned __int16 *)Src + 1);
      *(_WORD *)&v82[138] = v59;
      *(_WORD *)&v82[136] = v59;
      v60 = (void *)((__int64 (__fastcall *)(size_t))v62)(v59);
      *(_QWORD *)&v82[144] = v60;
      if ( !v60 )
      {
        v33 = -1073741801;
        v63 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v63, 4841, "AllocateLsaHeap", &Class);
        goto LABEL_81;
      }
    }
    memcpy_0(v60, v57, v59);
LABEL_75:
    if ( a2 )
      v48 |= 0x40008u;
    v64 = *(_OWORD *)&v82[16];
    *(_OWORD *)&a9->LogonId.LowPart = *(_OWORD *)v82;
    *(_DWORD *)&v82[80] = v48 | 0x24000000;
    v65 = *(_OWORD *)&v82[32];
    *(_OWORD *)&a9->DownlevelName.Buffer = v64;
    v66 = *(_OWORD *)&v82[48];
    *(_OWORD *)&a9->DomainName.Buffer = v65;
    v67 = *(_OWORD *)&v82[64];
    *(_OWORD *)&a9->Password.Buffer = v66;
    v68 = *(_OWORD *)&v82[80];
    *(_OWORD *)&a9->OldPassword.Buffer = v67;
    v69 = *(_OWORD *)&v82[96];
    *(_OWORD *)&a9->Flags = v68;
    v70 = *(_OWORD *)&v82[112];
    *(_OWORD *)&a9->DnsDomainName.Buffer = v69;
    v71 = *(_OWORD *)&v82[128];
    *(_OWORD *)&a9->Upn.Buffer = v70;
    v72 = *(_OWORD *)&v82[144];
    *(_OWORD *)&a9->LogonServer.Buffer = v71;
    v73 = *(_OWORD *)&v82[160];
    *(_OWORD *)&a9->Spare1.Buffer = v72;
    v74 = *(_OWORD *)&v82[176];
    *(_OWORD *)&a9->Spare2.Buffer = v73;
    v75 = *(_OWORD *)&v82[192];
    *(_OWORD *)&a9->Spare3.Buffer = v74;
    v76 = v83;
    *(_OWORD *)&a9->Spare4.Buffer = v75;
    *(_OWORD *)&a9->PrevLogonId.LowPart = v76;
    memset_0(v82, 0, 0xE0u);
    v33 = 0;
    goto LABEL_81;
  }
  v50 = RtlLengthSid(v49);
  v51 = (void *)((__int64 (__fastcall *)(size_t))g_pLsaFunctionTable->AllocateLsaHeap)(v50);
  *(_QWORD *)&v82[72] = v51;
  if ( v51 )
  {
    memcpy_0(v51, v49, v50);
    goto LABEL_55;
  }
  v52 = "";
  v33 = -1073741801;
  while ( 1 )
  {
    v53 = *(v52 - 1);
    v54 = v52--;
    v55 = v53 == 92;
    if ( v53 == 92 )
      break;
    if ( v52 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
    {
      v55 = v53 == 92;
      break;
    }
  }
  if ( v55 )
    v52 = v54;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v52, 4791, "DuplicateSID", &Class);
LABEL_81:
  FreePrimaryCred((struct _SECPKG_PRIMARY_CRED *)v82);
  return v33;
}

```

## disassembly

```asm
0x180027a10  push    rbp
0x180027a12  push    rbx
0x180027a13  push    rsi
0x180027a14  push    rdi
0x180027a15  push    r12
0x180027a17  push    r14
0x180027a19  push    r15
0x180027a1b  lea     rbp, [rsp-120h]
0x180027a23  sub     rsp, 220h
0x180027a2a  mov     r14, r8
0x180027a2d  movzx   r15d, dl
0x180027a31  mov     rbx, rcx
0x180027a34  xorps   xmm0, xmm0
0x180027a37  xor     edx, edx; Val
0x180027a39  lea     rcx, [rsp+250h+var_1F0]; void *
0x180027a3e  mov     r8d, 0E0h; Size
0x180027a44  mov     r12, r9
0x180027a47  movups  xmmword ptr [rsp+250h+var_200.Length], xmm0
0x180027a4c  call    memset_0
0x180027a51  xor     edx, edx; Val
0x180027a53  lea     rcx, [rbp+150h+var_110]; void *
0x180027a57  mov     r8d, 0E0h; Size
0x180027a5d  call    memset_0
0x180027a62  mov     rdi, [rbp+150h+arg_40]
0x180027a69  lea     rcx, [rsp+250h+DestinationString]; DestinationString
0x180027a6e  movups  xmm0, [rbp+150h+var_110]
0x180027a72  mov     rdx, r12; SourceString
0x180027a75  movups  xmm1, [rbp+150h+var_100]
0x180027a79  movups  xmmword ptr [rdi], xmm0
0x180027a7c  movups  xmm0, [rbp+150h+var_F0]
0x180027a80  movups  xmmword ptr [rdi+10h], xmm1
0x180027a84  movups  xmm1, [rbp+150h+var_E0]
0x180027a88  movups  xmmword ptr [rdi+20h], xmm0
0x180027a8c  movups  xmm0, [rbp+150h+var_D0]
0x180027a93  movups  xmmword ptr [rdi+30h], xmm1
0x180027a97  movups  xmm1, [rbp+150h+var_C0]
0x180027a9e  movups  xmmword ptr [rdi+40h], xmm0
0x180027aa2  movups  xmm0, [rbp+150h+var_B0]
0x180027aa9  movups  xmmword ptr [rdi+50h], xmm1
0x180027aad  movups  xmm1, [rbp+150h+var_A0]
0x180027ab4  movups  xmmword ptr [rdi+60h], xmm0
0x180027ab8  movups  xmm0, [rbp+150h+var_90]
0x180027abf  movups  xmmword ptr [rdi+70h], xmm1
0x180027ac3  movups  xmm1, [rbp+150h+var_80]
0x180027aca  movups  xmmword ptr [rdi+80h], xmm0
0x180027ad1  movups  xmm0, [rbp+150h+var_70]
0x180027ad8  movups  xmmword ptr [rdi+90h], xmm1
0x180027adf  movups  xmm1, [rbp+150h+var_60]
0x180027ae6  movups  xmmword ptr [rdi+0A0h], xmm0
0x180027aed  movups  xmm0, [rbp+150h+var_50]
0x180027af4  movups  xmmword ptr [rdi+0B0h], xmm1
0x180027afb  movups  xmm1, [rbp+150h+var_40]
0x180027b02  movups  xmmword ptr [rdi+0C0h], xmm0
0x180027b09  movups  xmmword ptr [rdi+0D0h], xmm1
0x180027b10  mov     rax, [rbx]
0x180027b13  mov     ebx, 1000h
0x180027b18  xorps   xmm0, xmm0
0x180027b1b  mov     dword ptr [rbp+150h+var_1F0+50h], ebx
0x180027b1e  mov     qword ptr [rsp+250h+var_1F0], rax
0x180027b23  movups  xmmword ptr [rsp+250h+DestinationString.Length], xmm0
0x180027b28  call    cs:__imp_RtlInitUnicodeString
0x180027b2e  cmp     [rsp+250h+DestinationString.Buffer], 0
0x180027b34  xorps   xmm0, xmm0
0x180027b37  movups  xmmword ptr [rbp+150h+var_1F0+68h], xmm0
0x180027b3b  jz      short loc_180027BB0
0x180027b3d  movzx   ecx, [rsp+250h+DestinationString.MaximumLength]
0x180027b42  xor     eax, eax
0x180027b44  cmp     ax, cx
0x180027b47  jz      short loc_180027BB0
0x180027b49  movzx   esi, [rsp+250h+DestinationString.Length]
0x180027b4e  cmp     si, cx
0x180027b51  ja      loc_180027C32
0x180027b57  test    sil, 1
0x180027b5b  jnz     loc_180027C32
0x180027b61  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180027b68  add     cx, 2
0x180027b6c  movzx   ecx, cx
0x180027b6f  mov     word ptr [rbp+150h+var_1F0+68h], si
0x180027b73  mov     word ptr [rbp+150h+var_1F0+6Ah], cx
0x180027b77  mov     rax, [rax+28h]
0x180027b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b80  mov     qword ptr [rbp+150h+var_1F0+70h], rax
0x180027b84  test    rax, rax
0x180027b87  jnz     short loc_180027BA0
0x180027b89  mov     esi, 0C0000017h
0x180027b8e  lea     r8, aAllocatelsahea_3; "AllocateLsaHeap"
0x180027b95  mov     r11d, 10Bh
0x180027b9b  jmp     loc_180027C44
0x180027ba0  mov     rdx, [rsp+250h+DestinationString.Buffer]; Src
0x180027ba5  mov     r8, rsi; Size
0x180027ba8  mov     rcx, rax; void *
0x180027bab  call    memcpy_0
0x180027bb0  mov     rax, [rbp+150h+arg_20]
0x180027bb7  test    byte ptr [rax+0A0h], 8
0x180027bbe  jz      loc_180027D82
0x180027bc4  mov     rcx, [r14+48h]; SourceString
0x180027bc8  test    rcx, rcx
0x180027bcb  jz      loc_180027CCF
0x180027bd1  lea     rdx, [rsp+250h+var_1F0+8]; struct _UNICODE_STRING *
0x180027bd6  call    ?DuplicateUnicodeString3@@YAJPEBGPEAU_UNICODE_STRING@@@Z; DuplicateUnicodeString3(ushort const *,_UNICODE_STRING *)
0x180027bdb  mov     ebx, eax
0x180027bdd  test    eax, eax
0x180027bdf  jz      loc_180027CCC
0x180027be5  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x180027bec  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180027bf3  movzx   eax, byte ptr [r9-1]
0x180027bf8  mov     rdx, r9
0x180027bfb  dec     r9
0x180027bfe  cmp     al, 5Ch ; '\'
0x180027c00  jz      short loc_180027C09
0x180027c02  cmp     r9, rcx
0x180027c05  ja      short loc_180027BF3
0x180027c07  cmp     al, 5Ch ; '\'
0x180027c09  lea     rdi, Class
0x180027c10  cmovz   r9, rdx
0x180027c14  mov     [rsp+250h+var_220], rdi
0x180027c19  lea     rax, aDuplicateunico_10; "DuplicateUnicodeString3"
0x180027c20  mov     [rsp+250h+var_228], rax
0x180027c25  mov     dword ptr [rsp+250h+var_230], 1261h
0x180027c2d  jmp     loc_18002818A
0x180027c32  mov     esi, 0C000000Dh
0x180027c37  lea     r8, aMalformedSourc; "Malformed source string"
0x180027c3e  mov     r11d, 102h
0x180027c44  lea     rdi, Class
0x180027c4b  xor     r10d, r10d
0x180027c4e  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180027c55  mov     rbx, rdi
0x180027c58  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180027c5d  mov     [rsp+250h+var_220], rbx
0x180027c62  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180027c69  mov     [rsp+250h+var_228], r8
0x180027c6e  mov     r9, rax
0x180027c71  mov     r8d, esi
0x180027c74  mov     dword ptr [rsp+250h+var_230], r11d
0x180027c79  mov     ecx, r10d
0x180027c7c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180027c81  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x180027c88  mov     ebx, esi
0x180027c8a  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180027c91  movzx   eax, byte ptr [r9-1]
0x180027c96  mov     r10, r9
0x180027c99  dec     r9
0x180027c9c  cmp     al, 5Ch ; '\'
0x180027c9e  jz      short loc_180027CA7
0x180027ca0  cmp     r9, rcx
0x180027ca3  ja      short loc_180027C91
0x180027ca5  cmp     al, 5Ch ; '\'
0x180027ca7  mov     [rsp+250h+var_220], rdi
0x180027cac  lea     rax, aDuplicateunico_10; "DuplicateUnicodeString3"
0x180027cb3  mov     [rsp+250h+var_228], rax
0x180027cb8  cmovz   r9, r10
0x180027cbc  mov     dword ptr [rsp+250h+var_230], 1257h
0x180027cc4  mov     r8d, esi
0x180027cc7  jmp     loc_18002818D
0x180027ccc  mov     ebx, dword ptr [rbp+150h+var_1F0+50h]
0x180027ccf  mov     rcx, [r14+58h]; SourceString
0x180027cd3  test    rcx, rcx
0x180027cd6  jz      short loc_180027D1E
0x180027cd8  lea     rdx, [rbp+150h+var_1F0+58h]; struct _UNICODE_STRING *
0x180027cdc  call    ?DuplicateUnicodeString3@@YAJPEBGPEAU_UNICODE_STRING@@@Z; DuplicateUnicodeString3(ushort const *,_UNICODE_STRING *)
0x180027ce1  mov     ebx, eax
0x180027ce3  test    eax, eax
0x180027ce5  jz      short loc_180027D1B
0x180027ce7  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180027cee  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180027cf3  mov     r9, rax
0x180027cf6  lea     rdi, Class
0x180027cfd  mov     [rsp+250h+var_220], rdi
0x180027d02  lea     rax, aDuplicateunico_10; "DuplicateUnicodeString3"
0x180027d09  mov     [rsp+250h+var_228], rax
0x180027d0e  mov     dword ptr [rsp+250h+var_230], 126Ah
0x180027d16  jmp     loc_18002818A
0x180027d1b  mov     ebx, dword ptr [rbp+150h+var_1F0+50h]
0x180027d1e  mov     rcx, [r14+50h]; SourceString
0x180027d22  test    rcx, rcx
0x180027d25  jz      short loc_180027D6E
0x180027d27  lea     rdx, [rsp+250h+var_1F0+18h]; struct _UNICODE_STRING *
0x180027d2c  call    ?DuplicateUnicodeString3@@YAJPEBGPEAU_UNICODE_STRING@@@Z; DuplicateUnicodeString3(ushort const *,_UNICODE_STRING *)
0x180027d31  mov     ebx, eax
0x180027d33  test    eax, eax
0x180027d35  jz      short loc_180027D6B
0x180027d37  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180027d3e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180027d43  mov     r9, rax
0x180027d46  lea     rdi, Class
0x180027d4d  mov     [rsp+250h+var_220], rdi
0x180027d52  lea     rax, aDuplicateunico_10; "DuplicateUnicodeString3"
0x180027d59  mov     [rsp+250h+var_228], rax
0x180027d5e  mov     dword ptr [rsp+250h+var_230], 1273h
0x180027d66  jmp     loc_18002818A
0x180027d6b  mov     ebx, dword ptr [rbp+150h+var_1F0+50h]
0x180027d6e  mov     dl, 1
0x180027d70  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers> `wil::Feature<__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers>::GetImpl(void)'::`2'::impl
0x180027d77  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudKerberosForCloudOnlyUsers>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180027d7c  bts     ebx, 10h
0x180027d80  jmp     short loc_180027D86
0x180027d82  bts     ebx, 8
0x180027d86  cmp     qword ptr [rsp+250h+var_1F0+10h], 0
0x180027d8c  mov     dword ptr [rbp+150h+var_1F0+50h], ebx
0x180027d8f  jnz     short loc_180027DDB
0x180027d91  lea     rdx, [rsp+250h+var_1F0+8]; struct _UNICODE_STRING *
0x180027d96  mov     rcx, r12; SourceString
0x180027d99  call    ?DuplicateUnicodeString3@@YAJPEBGPEAU_UNICODE_STRING@@@Z; DuplicateUnicodeString3(ushort const *,_UNICODE_STRING *)
0x180027d9e  mov     ebx, eax
0x180027da0  test    eax, eax
0x180027da2  jz      short loc_180027DD8
0x180027da4  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180027dab  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180027db0  mov     r9, rax
0x180027db3  lea     rdi, Class
0x180027dba  mov     [rsp+250h+var_220], rdi
0x180027dbf  lea     rax, aDuplicateunico_10; "DuplicateUnicodeString3"
0x180027dc6  mov     [rsp+250h+var_228], rax
0x180027dcb  mov     dword ptr [rsp+250h+var_230], 12ABh
0x180027dd3  jmp     loc_18002818A
0x180027dd8  mov     ebx, dword ptr [rbp+150h+var_1F0+50h]
0x180027ddb  cmp     qword ptr [rbp+150h+var_1F0+20h], 0
0x180027de0  jnz     short loc_180027E30
0x180027de2  mov     rcx, [rbp+150h+SourceString]; SourceString
0x180027de9  lea     rdx, [rsp+250h+var_1F0+18h]; struct _UNICODE_STRING *
0x180027dee  call    ?DuplicateUnicodeString3@@YAJPEBGPEAU_UNICODE_STRING@@@Z; DuplicateUnicodeString3(ushort const *,_UNICODE_STRING *)
0x180027df3  mov     ebx, eax
0x180027df5  test    eax, eax
0x180027df7  jz      short loc_180027E2D
0x180027df9  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180027e00  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180027e05  mov     r9, rax
0x180027e08  lea     rdi, Class
0x180027e0f  mov     [rsp+250h+var_220], rdi
0x180027e14  lea     rax, aDuplicateunico_10; "DuplicateUnicodeString3"
0x180027e1b  mov     [rsp+250h+var_228], rax
0x180027e20  mov     dword ptr [rsp+250h+var_230], 12B3h
0x180027e28  jmp     loc_18002818A
0x180027e2d  mov     ebx, dword ptr [rbp+150h+var_1F0+50h]
0x180027e30  mov     rsi, [r14+10h]
0x180027e34  mov     qword ptr [rbp+150h+var_1F0+48h], 0
0x180027e3c  test    rsi, rsi
0x180027e3f  jz      loc_180027EE0
0x180027e45  mov     rcx, rsi; Sid
0x180027e48  call    cs:__imp_RtlLengthSid
0x180027e4e  mov     rcx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180027e55  mov     r14d, eax
0x180027e58  mov     rax, [rcx+28h]
0x180027e5c  mov     ecx, r14d
0x180027e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e64  mov     qword ptr [rbp+150h+var_1F0+48h], rax
0x180027e68  test    rax, rax
0x180027e6b  jnz     short loc_180027ED2
0x180027e6d  mov     esi, 0C0000017h
0x180027e72  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x180027e79  mov     ebx, esi
0x180027e7b  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180027e82  nop     dword ptr [rax+00h]
0x180027e86  nop     word ptr [rax+rax+00000000h]
0x180027e90  movzx   eax, byte ptr [r9-1]
0x180027e95  mov     rdx, r9
0x180027e98  dec     r9
0x180027e9b  cmp     al, 5Ch ; '\'
0x180027e9d  jz      short loc_180027EA6
0x180027e9f  cmp     r9, rcx
0x180027ea2  ja      short loc_180027E90
0x180027ea4  cmp     al, 5Ch ; '\'
0x180027ea6  lea     rdi, Class
0x180027ead  cmovz   r9, rdx
0x180027eb1  mov     [rsp+250h+var_220], rdi
0x180027eb6  lea     rax, aDuplicatesid; "DuplicateSID"
0x180027ebd  mov     [rsp+250h+var_228], rax
0x180027ec2  mov     r8d, esi
0x180027ec5  mov     dword ptr [rsp+250h+var_230], 12B7h
0x180027ecd  jmp     loc_18002818D
0x180027ed2  mov     r8, r14; Size
0x180027ed5  mov     rdx, rsi; Src
0x180027ed8  mov     rcx, rax; void *
0x180027edb  call    memcpy_0
0x180027ee0  mov     rcx, [rbp+150h+arg_38]
0x180027ee7  mov     eax, [rcx]
0x180027ee9  cmp     eax, 1
0x180027eec  jnz     short loc_180027F58
0x180027eee  mov     rax, [rcx+8]
0x180027ef2  lea     rdx, [rbp+150h+var_1F0+28h]; struct _UNICODE_STRING *
0x180027ef6  mov     [rsp+250h+var_200.Buffer], rax
0x180027efb  movzx   eax, word ptr [rcx+4]
0x180027eff  lea     rcx, [rsp+250h+var_200]; struct _UNICODE_STRING *
0x180027f04  mov     [rsp+250h+var_200.MaximumLength], ax
0x180027f09  mov     [rsp+250h+var_200.Length], ax
0x180027f0e  call    ?DuplicateUnicodeString2@@YAJPEAU_UNICODE_STRING@@0@Z; DuplicateUnicodeString2(_UNICODE_STRING *,_UNICODE_STRING *)
0x180027f13  mov     ebx, eax
0x180027f15  test    eax, eax
0x180027f17  jz      short loc_180027F4D
0x180027f19  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180027f20  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180027f25  mov     r9, rax
0x180027f28  lea     rdi, Class
0x180027f2f  mov     [rsp+250h+var_220], rdi
0x180027f34  lea     rax, aDuplicateunico; "DuplicateUnicodeString2"
0x180027f3b  mov     [rsp+250h+var_228], rax
0x180027f40  mov     dword ptr [rsp+250h+var_230], 12C2h
0x180027f48  jmp     loc_18002818A
0x180027f4d  mov     ebx, dword ptr [rbp+150h+var_1F0+50h]
0x180027f50  or      ebx, 1
  ... truncated ...
```
