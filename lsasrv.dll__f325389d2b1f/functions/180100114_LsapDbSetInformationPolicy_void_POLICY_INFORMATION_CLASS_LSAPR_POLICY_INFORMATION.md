# LsapDbSetInformationPolicy(void *,_POLICY_INFORMATION_CLASS,_LSAPR_POLICY_INFORMATION *)

- ea: `0x180100114`
- end: `0x18010086b`
- name: `?LsapDbSetInformationPolicy@@YAJPEAXW4_POLICY_INFORMATION_CLASS@@PEAT_LSAPR_POLICY_INFORMATION@@@Z`
- size: `1879`
- prototype: `__int64 __fastcall(void *, enum _POLICY_INFORMATION_CLASS, PUNICODE_STRING DomainName1)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180101050`

## callees

- `0x18000e530`
- `0x180011278`
- `0x18001f290`
- `0x1800532cc`
- `0x180053d70`
- `0x18007a2f0`
- `0x1800a0840`
- `0x1800ada18`
- `0x1800b2704`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bb068`
- `0x1800bc040`
- `0x180100114`
- `0x180100874`
- `0x18010cd80`
- `0x18010cde0`
- `0x18010ce80`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180100527`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180100527`
- `ntdll!RtlEqualDomainName` at `0x180100271`
- `ntdll!RtlEqualDomainName` at `0x180100271`
- `ntdll!RtlEqualSid` at `0x1801002a6`
- `ntdll!RtlEqualSid` at `0x1801002a6`
- `ext-ms-win-netprovision-netprovfw-l1-1-0!NetpProvDomainJoinLicensingCheck` at `0x1801002c8`
- `ext-ms-win-netprovision-netprovfw-l1-1-0!NetpProvDomainJoinLicensingCheck` at `0x18010032e`
- `ext-ms-win-netprovision-netprovfw-l1-1-0!NetpProvDomainJoinLicensingCheck` at `0x1801002c8`
- `ext-ms-win-netprovision-netprovfw-l1-1-0!NetpProvDomainJoinLicensingCheck` at `0x18010032e`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtGenerateLsaAuditEvent` at `0x1801004d5`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtGenerateLsaAuditEvent` at `0x1801004d5`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtApplySystemPolicyUpdates` at `0x180100482`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtApplySystemPolicyUpdates` at `0x180100482`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapUpdateSamAuditPolicy` at `0x18010048e`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapUpdateSamAuditPolicy` at `0x18010048e`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtApplyOldPublicPolicyOnStorage` at `0x180100668`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtApplyOldPublicPolicyOnStorage` at `0x180100668`

## pseudocode

```c
__int64 __fastcall LsapDbSetInformationPolicy(_BYTE *a1, signed int a2, PUNICODE_STRING DomainName1)
{
  _BYTE *v5; // r15
  PUNICODE_STRING v6; // r14
  unsigned int v7; // esi
  unsigned int v8; // r12d
  __int64 v9; // rdx
  signed int InformationPolicy; // ebx
  char v11; // di
  int *v12; // rdi
  void *v13; // rcx
  void *v14; // rdx
  struct _UNICODE_STRING v15; // xmm0
  PUNICODE_STRING v16; // r15
  PUNICODE_STRING v17; // r14
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  void *v22; // rcx
  unsigned __int8 v24; // dl
  int v25; // eax
  PWSTR v26; // rcx
  PWSTR Buffer; // rcx
  char v28; // [rsp+50h] [rbp-B0h]
  char v29; // [rsp+50h] [rbp-B0h]
  char v30; // [rsp+51h] [rbp-AFh]
  PUNICODE_STRING DomainName2; // [rsp+58h] [rbp-A8h] BYREF
  PUNICODE_STRING v32; // [rsp+60h] [rbp-A0h]
  _BYTE *v33; // [rsp+68h] [rbp-98h]
  _OWORD v34[4]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+B0h] [rbp-50h]
  int v36; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v37; // [rsp+C8h] [rbp-38h]
  PUNICODE_STRING v38; // [rsp+D0h] [rbp-30h]
  int v39; // [rsp+D8h] [rbp-28h]
  __int16 v40; // [rsp+DCh] [rbp-24h]
  char v41; // [rsp+DEh] [rbp-22h]
  _BYTE v42[40]; // [rsp+E8h] [rbp-18h] BYREF
  int v43; // [rsp+110h] [rbp+10h] BYREF
  __int64 *v44; // [rsp+118h] [rbp+18h]
  PUNICODE_STRING v45; // [rsp+120h] [rbp+20h]
  int v46; // [rsp+128h] [rbp+28h]
  __int16 v47; // [rsp+12Ch] [rbp+2Ch]
  char v48; // [rsp+12Eh] [rbp+2Eh]
  char v49[40]; // [rsp+138h] [rbp+38h] BYREF
  _OWORD v50[9]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v51; // [rsp+270h] [rbp+170h]
  _OWORD v52[9]; // [rsp+278h] [rbp+178h] BYREF
  __int64 v53; // [rsp+308h] [rbp+208h]

  v33 = a1;
  DomainName2 = 0;
  v5 = a1;
  v6 = 0;
  memset_0(v34, 0, 0x48u);
  v7 = 0;
  v28 = 0;
  v8 = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 44, &WPP_a5273d544b883828eaa2592a0f0a6148_Traceguids);
  v9 = 2;
  if ( a2 > 7 )
  {
    switch ( a2 )
    {
      case 8:
        v38 = DomainName1;
        v36 = 5;
        v7 = 1;
        v37 = qword_18019E860;
        v39 = 48;
        v11 = 0;
        v40 = 0;
        v41 = 0;
        goto LABEL_44;
      case 10:
        goto LABEL_83;
      case 12:
LABEL_31:
        if ( !LsapIsContainerized
          && (unsigned __int8)IsNetpProvCheckOfflineLsaPolicyUpdatePresent()
          && (int)NetpProvDomainJoinLicensingCheck() >= 0
          || DomainName2 )
        {
          goto LABEL_37;
        }
        InformationPolicy = LsapDbQueryInformationPolicy(
                              (__int64)LsapPolicyHandle,
                              12,
                              (union _LSAPR_POLICY_INFORMATION **)&DomainName2);
        if ( InformationPolicy < 0 )
          goto LABEL_53;
        if ( !*(_QWORD *)&DomainName1[4].Length )
        {
LABEL_37:
          v16 = DomainName1 + 1;
          LOBYTE(v9) = 1;
          v17 = DomainName1 + 2;
          v29 = LsapRemoveTrailingDot(&DomainName1[1], v9);
          LOBYTE(v18) = 1;
          v30 = LsapRemoveTrailingDot(&DomainName1[2], v18);
          LsapDbMakeInvalidInformationPolicy(3u);
          InformationPolicy = LsapDbMakeUnicodeAttribute(DomainName1, 22, &v36);
          if ( InformationPolicy < 0 )
            goto LABEL_53;
          LsapDbMakeUnicodeAttribute(&DomainName1[1], 18, v42);
          LsapDbMakeUnicodeAttribute(&DomainName1[2], 19, &v43);
          LsapDbMakeGuidAttribute(&DomainName1[3], 20, v49);
          v8 = 4;
          v7 = 4;
          InformationPolicy = LsapDbMakeSidAttribute(*(PSID *)&DomainName1[4].Length);
          if ( InformationPolicy < 0 )
            goto LABEL_53;
          v7 = 5;
          v32 = DomainName1;
          v11 = 1;
          if ( v29 )
            v16->Length += 2;
          v5 = v33;
          if ( v30 )
            v17->Length += 2;
          v6 = v32;
          goto LABEL_44;
        }
LABEL_83:
        InformationPolicy = -1073741637;
        goto LABEL_58;
      case 15:
        Buffer = DomainName1->Buffer;
        v39 = 4;
        v37 = qword_18019EC00;
        v36 = 63;
        v38 = DomainName1;
        v40 = 0;
        v41 = 0;
        InformationPolicy = LsapDbMakeSidAttribute(Buffer);
        v7 = 2;
        break;
      case 16:
        v26 = DomainName1->Buffer;
        v39 = 4;
        v37 = qword_18019EC00;
        v36 = 63;
        v38 = DomainName1;
        v40 = 0;
        v41 = 0;
        InformationPolicy = LsapDbMakeSidAttribute(v26);
        v47 = 0;
        v48 = 0;
        v44 = qword_18019EC20;
        v7 = 3;
        v43 = 65;
        v45 = DomainName1 + 1;
        v46 = 16;
        break;
      default:
        goto LABEL_78;
    }
LABEL_81:
    if ( InformationPolicy < 0 )
      goto LABEL_53;
    v11 = v28;
    goto LABEL_44;
  }
  switch ( a2 )
  {
    case 7:
      InformationPolicy = LsapDbMakeUnicodeAttribute(DomainName1, 25, &v36);
      if ( InformationPolicy < 0 )
        goto LABEL_53;
      InformationPolicy = LsapDbMakeUnicodeAttribute(&DomainName1[1], 26, v42);
      if ( InformationPolicy < 0 )
        goto LABEL_16;
      v7 = 2;
      v11 = 0;
LABEL_44:
      InformationPolicy = LsapDbWriteAttributesObject(v5);
      if ( InformationPolicy >= 0 )
      {
        if ( (unsigned __int8)IsLsapAdtInitializeCrashOnAuditFailPresent(v19)
          && (unsigned __int8)IsLsapAdtInitializeCrashOnAuditFailPresent(v20)
          && (unsigned __int8)IsLsapAdtInitializeCrashOnAuditFailPresent(v21)
          && a2 == 2 )
        {
          LsapAdtApplySystemPolicyUpdates(v50);
          LsapUpdateSamAuditPolicy();
          LsapAdtGenerateLsaAuditEvent(v5, 6, 4719, 0, 0, 0, 0, 0, v50, v52);
        }
        LsapDbMakeInvalidInformationPolicy(a2);
        if ( v11 )
        {
          LsaINotifyChangeNotification(v8);
          if ( v8 == 4 )
            LsapNotifyUBPM(2 - (*(_QWORD *)&v6[4].Length != 0));
        }
      }
LABEL_53:
      LODWORD(v6) = 0;
      v12 = &v36;
      if ( !v7 )
        goto LABEL_58;
      goto LABEL_54;
    case 1:
      InformationPolicy = v5[133] == 0 ? 0xC0000002 : 0;
      goto LABEL_81;
    case 2:
      if ( (unsigned __int8)IsLsapAdtInitializeCrashOnAuditFailPresent(0) )
      {
        InformationPolicy = LsapDbQueryAuditPolicyInternal((struct _LSA_AUDIT_POLICY_STORAGE *)v52, v24);
        if ( InformationPolicy < 0 )
          goto LABEL_53;
        v51 = v53;
        v50[0] = v52[0];
        v50[1] = v52[1];
        v50[2] = v52[2];
        v50[3] = v52[3];
        v50[4] = v52[4];
        v50[5] = v52[5];
        v50[6] = v52[6];
        v50[7] = v52[7];
        v50[8] = v52[8];
        v25 = LsapAdtApplyOldPublicPolicyOnStorage(DomainName1, v50);
        InformationPolicy = v25;
        if ( v25 < 0 )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x100) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              45,
              &WPP_a5273d544b883828eaa2592a0f0a6148_Traceguids,
              (unsigned int)v25);
            goto LABEL_58;
          }
          goto LABEL_53;
        }
        v36 = 15;
        v37 = (__int64 *)&stru_18019E900;
        v7 = 1;
        v39 = 152;
        v38 = (PUNICODE_STRING)v50;
        v40 = 0;
        v41 = 0;
        v28 = 1;
      }
      else
      {
        InformationPolicy = -1073741822;
      }
      v8 = v7;
      goto LABEL_81;
    case 3:
      InformationPolicy = LsapDbQueryInformationPolicy(
                            (__int64)LsapPolicyHandle,
                            12,
                            (union _LSAPR_POLICY_INFORMATION **)&DomainName2);
      if ( InformationPolicy < 0 )
        goto LABEL_53;
      if ( RtlEqualDomainName(DomainName1, DomainName2) )
      {
        v13 = *(void **)&DomainName1[1].Length;
        if ( v13 )
        {
          v14 = *(void **)&DomainName2[4].Length;
          if ( v14 && RtlEqualSid(v13, v14) )
            goto LABEL_21;
        }
        else if ( !*(_QWORD *)&DomainName2[4].Length )
        {
LABEL_21:
          v11 = 0;
          goto LABEL_44;
        }
      }
      if ( LsapIsContainerized || !(unsigned __int8)IsNetpProvCheckOfflineLsaPolicyUpdatePresent() )
      {
        InformationPolicy = -1073741637;
      }
      else
      {
        InformationPolicy = NetpProvDomainJoinLicensingCheck();
        if ( InformationPolicy >= 0 )
        {
LABEL_30:
          memset_0(v34, 0, 0x48u);
          v15 = *DomainName1;
          v35 = *(_QWORD *)&DomainName1[1].Length;
          DomainName1 = (PUNICODE_STRING)v34;
          v34[0] = v15;
          LsapDbMakeInvalidInformationPolicy(0xCu);
          goto LABEL_31;
        }
      }
      if ( *(_QWORD *)&DomainName1[1].Length )
        goto LABEL_53;
      goto LABEL_30;
    case 4:
      goto LABEL_78;
  }
  if ( a2 != 5 )
  {
    if ( a2 == 6 )
    {
      InformationPolicy = -1073741822;
      goto LABEL_58;
    }
    goto LABEL_78;
  }
  if ( !*(_QWORD *)&DomainName1[1].Length )
  {
LABEL_78:
    InformationPolicy = -1073741811;
    goto LABEL_58;
  }
  InformationPolicy = LsapDbMakeUnicodeAttribute(DomainName1, 16, &v36);
  if ( InformationPolicy < 0 )
    goto LABEL_53;
  InformationPolicy = LsapDbMakeSidAttribute(*(PSID *)&DomainName1[1].Length);
  if ( InformationPolicy >= 0 )
  {
    v11 = 1;
    v7 = 2;
    v8 = 2;
    goto LABEL_44;
  }
LABEL_16:
  v7 = 1;
  v12 = &v36;
  do
  {
LABEL_54:
    if ( *((_BYTE *)v12 + 28) )
    {
      v22 = (void *)*((_QWORD *)v12 + 2);
      if ( v22 )
      {
        LocalFree(v22);
        *((_BYTE *)v12 + 28) = 0;
        *((_QWORD *)v12 + 2) = 0;
      }
    }
    v12 += 10;
    LODWORD(v6) = (_DWORD)v6 + 1;
  }
  while ( (unsigned int)v6 < v7 );
LABEL_58:
  LsaIFree_LSAPR_POLICY_INFORMATION(12);
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x100) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      46,
      &WPP_a5273d544b883828eaa2592a0f0a6148_Traceguids,
      (unsigned int)InformationPolicy);
  return (unsigned int)InformationPolicy;
}

```

## disassembly

```asm
0x180100114  mov     [rsp-8+arg_18], rbx
0x180100119  push    rbp
0x18010011a  push    rsi
0x18010011b  push    rdi
0x18010011c  push    r12
0x18010011e  push    r13
0x180100120  push    r14
0x180100122  push    r15
0x180100124  lea     rbp, [rsp-220h]
0x18010012c  sub     rsp, 320h
0x180100133  mov     rax, cs:__security_cookie
0x18010013a  xor     rax, rsp
0x18010013d  mov     [rbp+250h+var_40], rax
0x180100144  xor     ebx, ebx
0x180100146  mov     [rsp+350h+var_2E8], rcx
0x18010014b  mov     rdi, r8
0x18010014e  mov     [rsp+350h+DomainName2], rbx
0x180100153  mov     r13d, edx
0x180100156  mov     r15, rcx
0x180100159  xor     edx, edx; Val
0x18010015b  lea     rcx, [rsp+350h+var_2E0]; void *
0x180100160  lea     r8d, [rbx+48h]; Size
0x180100164  mov     r14d, ebx
0x180100167  call    memset_0
0x18010016c  mov     esi, ebx
0x18010016e  mov     [rsp+350h+var_300], bl
0x180100172  mov     r12d, ebx
0x180100175  mov     rcx, cs:WPP_GLOBAL_Control
0x18010017c  test    dword ptr [rcx+6Ch], 100h
0x180100183  jz      short loc_180100198
0x180100185  mov     rcx, [rcx+60h]
0x180100189  lea     edx, [rbx+2Ch]
0x18010018c  lea     r8, WPP_a5273d544b883828eaa2592a0f0a6148_Traceguids
0x180100193  call    WPP_SF_
0x180100198  mov     edx, 2
0x18010019d  lea     r8d, [rdx+2]
0x1801001a1  cmp     r13d, 7
0x1801001a5  jg      loc_18010074E
0x1801001ab  jz      loc_18010070A
0x1801001b1  mov     ecx, r13d
0x1801001b4  sub     ecx, 1
0x1801001b7  jz      loc_1801006F1
0x1801001bd  sub     ecx, 1
0x1801001c0  jz      loc_1801005AF
0x1801001c6  sub     ecx, 1
0x1801001c9  jz      short loc_180100249
0x1801001cb  sub     ecx, 1
0x1801001ce  jz      loc_180100774
0x1801001d4  sub     ecx, 1
0x1801001d7  jz      short loc_1801001EC
0x1801001d9  cmp     ecx, 1
0x1801001dc  jnz     loc_180100774
0x1801001e2  mov     ebx, 0C0000002h
0x1801001e7  jmp     loc_18010054B
0x1801001ec  cmp     [rdi+10h], rbx
0x1801001f0  jz      loc_180100774
0x1801001f6  lea     r8, [rbp+250h+var_290]
0x1801001fa  mov     edx, 10h
0x1801001ff  mov     rcx, rdi
0x180100202  call    LsapDbMakeUnicodeAttribute
0x180100207  mov     ebx, eax
0x180100209  test    eax, eax
0x18010020b  js      loc_18010050D
0x180100211  mov     rcx, [rdi+10h]; Sid
0x180100215  lea     r8, [rbp+250h+var_268]
0x180100219  mov     edx, 11h
0x18010021e  call    LsapDbMakeSidAttribute
0x180100223  mov     ebx, eax
0x180100225  test    eax, eax
0x180100227  js      short loc_18010023B
0x180100229  mov     eax, 2
0x18010022e  mov     dil, 1
0x180100231  mov     esi, eax
0x180100233  mov     r12d, eax
0x180100236  jmp     loc_180100441
0x18010023b  mov     esi, 1
0x180100240  lea     rdi, [rbp+250h+var_290]
0x180100244  jmp     loc_180100518
0x180100249  mov     rcx, cs:?LsapPolicyHandle@@3PEAXEA; void * LsapPolicyHandle
0x180100250  lea     r8, [rsp+350h+DomainName2]
0x180100255  mov     edx, 0Ch
0x18010025a  call    LsapDbQueryInformationPolicy
0x18010025f  mov     ebx, eax
0x180100261  test    eax, eax
0x180100263  js      loc_18010050D
0x180100269  mov     rdx, [rsp+350h+DomainName2]; DomainName2
0x18010026e  mov     rcx, rdi; DomainName1
0x180100271  call    cs:__imp_RtlEqualDomainName
0x180100278  nop     dword ptr [rax+rax+00h]
0x18010027d  test    al, al
0x18010027f  jz      short loc_1801002B6
0x180100281  mov     rcx, [rdi+10h]; Sid1
0x180100285  mov     rax, [rsp+350h+DomainName2]
0x18010028a  test    rcx, rcx
0x18010028d  jnz     short loc_18010029D
0x18010028f  cmp     [rax+40h], rsi
0x180100293  jnz     short loc_1801002B6
0x180100295  mov     dil, sil
0x180100298  jmp     loc_180100441
0x18010029d  mov     rdx, [rax+40h]; Sid2
0x1801002a1  test    rdx, rdx
0x1801002a4  jz      short loc_1801002B6
0x1801002a6  call    cs:__imp_RtlEqualSid
0x1801002ad  nop     dword ptr [rax+rax+00h]
0x1801002b2  test    al, al
0x1801002b4  jnz     short loc_180100295
0x1801002b6  cmp     cs:?LsapIsContainerized@@3EA, sil; uchar LsapIsContainerized
0x1801002bd  jnz     short loc_1801002DC
0x1801002bf  call    IsNetpProvCheckOfflineLsaPolicyUpdatePresent
0x1801002c4  test    al, al
0x1801002c6  jz      short loc_1801002DC
0x1801002c8  call    cs:__imp_NetpProvDomainJoinLicensingCheck
0x1801002cf  nop     dword ptr [rax+rax+00h]
0x1801002d4  mov     ebx, eax
0x1801002d6  test    eax, eax
0x1801002d8  jns     short loc_1801002EB
0x1801002da  jmp     short loc_1801002E1
0x1801002dc  mov     ebx, 0C00000BBh
0x1801002e1  cmp     [rdi+10h], rsi
0x1801002e5  jnz     loc_18010050D
0x1801002eb  xor     edx, edx; Val
0x1801002ed  lea     rcx, [rsp+350h+var_2E0]; void *
0x1801002f2  lea     r8d, [rdx+48h]; Size
0x1801002f6  call    memset_0
0x1801002fb  movups  xmm0, xmmword ptr [rdi]
0x1801002fe  mov     rax, [rdi+10h]
0x180100302  mov     ecx, 0Ch; unsigned int
0x180100307  mov     [rbp+250h+var_2A0], rax
0x18010030b  lea     rdi, [rsp+350h+var_2E0]
0x180100310  movdqu  [rsp+350h+var_2E0], xmm0
0x180100316  call    ?LsapDbMakeInvalidInformationPolicy@@YAXK@Z; LsapDbMakeInvalidInformationPolicy(ulong)
0x18010031b  xor     ebx, ebx
0x18010031d  cmp     cs:?LsapIsContainerized@@3EA, bl; uchar LsapIsContainerized
0x180100323  jnz     short loc_18010033E
0x180100325  call    IsNetpProvCheckOfflineLsaPolicyUpdatePresent
0x18010032a  test    al, al
0x18010032c  jz      short loc_18010033E
0x18010032e  call    cs:__imp_NetpProvDomainJoinLicensingCheck
0x180100335  nop     dword ptr [rax+rax+00h]
0x18010033a  test    eax, eax
0x18010033c  jns     short loc_18010036F
0x18010033e  cmp     [rsp+350h+DomainName2], rbx
0x180100343  jnz     short loc_18010036F
0x180100345  mov     rcx, cs:?LsapPolicyHandle@@3PEAXEA; void * LsapPolicyHandle
0x18010034c  lea     r8, [rsp+350h+DomainName2]
0x180100351  mov     edx, 0Ch
0x180100356  call    LsapDbQueryInformationPolicy
0x18010035b  mov     ebx, eax
0x18010035d  test    eax, eax
0x18010035f  js      loc_18010050D
0x180100365  cmp     [rdi+40h], rsi
0x180100369  jnz     loc_18010082F
0x18010036f  lea     r15, [rdi+10h]
0x180100373  mov     dl, 1
0x180100375  mov     rcx, r15
0x180100378  call    LsapRemoveTrailingDot
0x18010037d  lea     r14, [rdi+20h]
0x180100381  mov     [rsp+350h+var_300], al
0x180100385  mov     rcx, r14
0x180100388  mov     dl, 1
0x18010038a  call    LsapRemoveTrailingDot
0x18010038f  mov     ecx, 3; unsigned int
0x180100394  mov     [rsp+350h+var_2FF], al
0x180100398  call    ?LsapDbMakeInvalidInformationPolicy@@YAXK@Z; LsapDbMakeInvalidInformationPolicy(ulong)
0x18010039d  lea     r8, [rbp+250h+var_290]
0x1801003a1  mov     edx, 16h
0x1801003a6  mov     rcx, rdi
0x1801003a9  call    LsapDbMakeUnicodeAttribute
0x1801003ae  mov     ebx, eax
0x1801003b0  test    eax, eax
0x1801003b2  js      loc_18010050D
0x1801003b8  lea     r8, [rbp+250h+var_268]
0x1801003bc  mov     edx, 12h
0x1801003c1  mov     rcx, r15
0x1801003c4  call    LsapDbMakeUnicodeAttribute
0x1801003c9  lea     r8, [rbp+250h+var_240]
0x1801003cd  mov     edx, 13h
0x1801003d2  mov     rcx, r14
0x1801003d5  call    LsapDbMakeUnicodeAttribute
0x1801003da  lea     rcx, [rdi+30h]
0x1801003de  mov     edx, 14h
0x1801003e3  lea     r8, [rbp+250h+var_218]
0x1801003e7  call    LsapDbMakeGuidAttribute
0x1801003ec  mov     rcx, [rdi+40h]; Sid
0x1801003f0  lea     r8, [rbp+250h+var_1F0]
0x1801003f4  mov     r12d, 4
0x1801003fa  mov     esi, r12d
0x1801003fd  lea     edx, [r12+13h]
0x180100402  call    LsapDbMakeSidAttribute
0x180100407  mov     ebx, eax
0x180100409  test    eax, eax
0x18010040b  js      loc_18010050D
0x180100411  cmp     [rsp+350h+var_300], 0
0x180100416  lea     esi, [r12+1]
0x18010041b  mov     [rsp+350h+var_2F0], rdi
0x180100420  lea     eax, [rsi-3]
0x180100423  mov     dil, 1
0x180100426  jz      short loc_18010042C
0x180100428  add     [r15], ax
0x18010042c  cmp     [rsp+350h+var_2FF], 0
0x180100431  mov     r15, [rsp+350h+var_2E8]
0x180100436  jz      short loc_18010043C
0x180100438  add     [r14], ax
0x18010043c  mov     r14, [rsp+350h+var_2F0]
0x180100441  mov     r8d, esi
0x180100444  lea     rdx, [rbp+250h+var_290]
0x180100448  mov     rcx, r15; void *
0x18010044b  call    LsapDbWriteAttributesObject
0x180100450  mov     ebx, eax
0x180100452  test    eax, eax
0x180100454  js      loc_18010050D
0x18010045a  call    IsLsapAdtInitializeCrashOnAuditFailPresent
0x18010045f  test    al, al
0x180100461  jz      short loc_1801004E1
0x180100463  call    IsLsapAdtInitializeCrashOnAuditFailPresent
0x180100468  test    al, al
0x18010046a  jz      short loc_1801004E1
0x18010046c  call    IsLsapAdtInitializeCrashOnAuditFailPresent
0x180100471  test    al, al
0x180100473  jz      short loc_1801004E1
0x180100475  cmp     r13d, 2
0x180100479  jnz     short loc_1801004E1
0x18010047b  lea     rcx, [rbp+250h+var_170]
0x180100482  call    cs:__imp_LsapAdtApplySystemPolicyUpdates
0x180100489  nop     dword ptr [rax+rax+00h]
0x18010048e  call    cs:__imp_LsapUpdateSamAuditPolicy
0x180100495  nop     dword ptr [rax+rax+00h]
0x18010049a  lea     rax, [rbp+250h+var_D8]
0x1801004a1  xor     r9d, r9d
0x1801004a4  mov     [rsp+350h+var_308], rax
0x1801004a9  mov     r8d, 126Fh
0x1801004af  lea     rax, [rbp+250h+var_170]
0x1801004b6  mov     rcx, r15
0x1801004b9  mov     [rsp+350h+var_310], rax
0x1801004be  xor     eax, eax
0x1801004c0  mov     [rsp+350h+var_318], rax
0x1801004c5  mov     [rsp+350h+var_320], eax
0x1801004c9  mov     [rsp+350h+var_328], rax
0x1801004ce  lea     edx, [rax+6]
0x1801004d1  mov     [rsp+350h+var_330], eax
0x1801004d5  call    cs:__imp_LsapAdtGenerateLsaAuditEvent
0x1801004dc  nop     dword ptr [rax+rax+00h]
0x1801004e1  mov     ecx, r13d; unsigned int
0x1801004e4  call    ?LsapDbMakeInvalidInformationPolicy@@YAXK@Z; LsapDbMakeInvalidInformationPolicy(ulong)
0x1801004e9  test    dil, dil
0x1801004ec  jz      short loc_18010050D
0x1801004ee  mov     ecx, r12d
0x1801004f1  call    LsaINotifyChangeNotification
0x1801004f6  cmp     r12d, 4
0x1801004fa  jnz     short loc_18010050D
0x1801004fc  mov     rax, [r14+40h]
0x180100500  neg     rax
0x180100503  sbb     ecx, ecx
0x180100505  add     ecx, 2; unsigned int
0x180100508  call    ?LsapNotifyUBPM@@YAJK@Z; LsapNotifyUBPM(ulong)
0x18010050d  xor     r14d, r14d
0x180100510  lea     rdi, [rbp+250h+var_290]
0x180100514  test    esi, esi
0x180100516  jz      short loc_18010054B
0x180100518  cmp     byte ptr [rdi+1Ch], 0
0x18010051c  jz      short loc_18010053F
0x18010051e  mov     rcx, [rdi+10h]; hMem
0x180100522  test    rcx, rcx
0x180100525  jz      short loc_18010053F
0x180100527  call    cs:__imp_LocalFree
0x18010052e  nop     dword ptr [rax+rax+00h]
0x180100533  mov     byte ptr [rdi+1Ch], 0
0x180100537  mov     qword ptr [rdi+10h], 0
0x18010053f  add     rdi, 28h ; '('
0x180100543  inc     r14d
0x180100546  cmp     r14d, esi
0x180100549  jb      short loc_180100518
0x18010054b  mov     rdx, [rsp+350h+DomainName2]
0x180100550  mov     ecx, 0Ch
0x180100555  call    LsaIFree_LSAPR_POLICY_INFORMATION
0x18010055a  mov     rcx, cs:WPP_GLOBAL_Control
0x180100561  test    dword ptr [rcx+6Ch], 100h
0x180100568  jz      short loc_180100582
0x18010056a  mov     rcx, [rcx+60h]
0x18010056e  lea     r8, WPP_a5273d544b883828eaa2592a0f0a6148_Traceguids
0x180100575  mov     edx, 2Eh ; '.'
0x18010057a  mov     r9d, ebx
0x18010057d  call    WPP_SF_d
0x180100582  mov     eax, ebx
0x180100584  mov     rcx, [rbp+250h+var_40]
0x18010058b  xor     rcx, rsp; StackCookie
0x18010058e  call    __security_check_cookie
0x180100593  mov     rbx, [rsp+350h+arg_18]
0x18010059b  add     rsp, 320h
0x1801005a2  pop     r15
0x1801005a4  pop     r14
0x1801005a6  pop     r13
0x1801005a8  pop     r12
0x1801005aa  pop     rdi
0x1801005ab  pop     rsi
0x1801005ac  pop     rbp
0x1801005ad  retn
0x1801005af  call    IsLsapAdtInitializeCrashOnAuditFailPresent
0x1801005b4  test    al, al
0x1801005b6  jz      loc_1801006E4
  ... truncated ...
```
