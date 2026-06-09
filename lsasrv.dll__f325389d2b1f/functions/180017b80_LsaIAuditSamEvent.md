# LsaIAuditSamEvent

- ea: `0x180017b80`
- end: `0x1800189df`
- name: `LsaIAuditSamEvent`
- size: `3679`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000c300`
- `0x180016f70`
- `0x180017b80`
- `0x180019f58`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bc040`
- `0x1800ed098`
- `0x1800ed6d0`

## import_xrefs

- `LSAADT!__imp_LsapAuditFailed` at `0x180017d65`
- `LSAADT!__imp_LsapAuditFailed` at `0x180017d65`
- `LSAADT!__imp_LsapSidListSize` at `0x1800186c2`
- `LSAADT!__imp_LsapSidListSize` at `0x1800186c2`
- `LSAADT!__imp_LsapQueryClientInfo` at `0x180017cc8`
- `LSAADT!__imp_LsapQueryClientInfo` at `0x180017cc8`
- `LSAADT!__imp_?LsapSubsystemName@@3U_UNICODE_STRING@@A` at `0x180017ef4`
- `LSAADT!__imp_?LsapAdtCheckAuditAvailableInArray@@YAJQEAY01GKGPEAG@Z` at `0x180017d48`
- `LSAADT!__imp_?LsapAdtCheckAuditAvailableInArray@@YAJQEAY01GKGPEAG@Z` at `0x180017d48`
- `ntdll!RtlFreeHeap` at `0x180017e14`
- `ntdll!RtlFreeHeap` at `0x180017e14`
- `ntdll!RtlCopySid` at `0x180018050`
- `ntdll!RtlCopySid` at `0x180018559`
- `ntdll!RtlCopySid` at `0x180018050`
- `ntdll!RtlCopySid` at `0x180018559`
- `ntdll!RtlSubAuthorityCountSid` at `0x180018012`
- `ntdll!RtlSubAuthorityCountSid` at `0x180018074`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001847a`
- `ntdll!RtlSubAuthorityCountSid` at `0x180018580`
- `ntdll!RtlSubAuthorityCountSid` at `0x180018012`
- `ntdll!RtlSubAuthorityCountSid` at `0x180018074`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001847a`
- `ntdll!RtlSubAuthorityCountSid` at `0x180018580`
- `ntdll!RtlSubAuthoritySid` at `0x180018063`
- `ntdll!RtlSubAuthoritySid` at `0x18001856f`
- `ntdll!RtlSubAuthoritySid` at `0x180018063`
- `ntdll!RtlSubAuthoritySid` at `0x18001856f`
- `ntdll!RtlLengthRequiredSid` at `0x180018024`
- `ntdll!RtlLengthRequiredSid` at `0x180018490`
- `ntdll!RtlLengthRequiredSid` at `0x180018024`
- `ntdll!RtlLengthRequiredSid` at `0x180018490`
- `ntdll!RtlLengthSid` at `0x180017ed7`
- `ntdll!RtlLengthSid` at `0x1800180af`
- `ntdll!RtlLengthSid` at `0x180018203`
- `ntdll!RtlLengthSid` at `0x180018258`
- `ntdll!RtlLengthSid` at `0x1800185b9`
- `ntdll!RtlLengthSid` at `0x1800185e3`
- `ntdll!RtlLengthSid` at `0x18001862b`
- `ntdll!RtlLengthSid` at `0x180017ed7`
- `ntdll!RtlLengthSid` at `0x1800180af`
- `ntdll!RtlLengthSid` at `0x180018203`
- `ntdll!RtlLengthSid` at `0x180018258`
- `ntdll!RtlLengthSid` at `0x1800185b9`
- `ntdll!RtlLengthSid` at `0x1800185e3`
- `ntdll!RtlLengthSid` at `0x18001862b`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180017e84`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180017e84`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtWriteLogEx` at `0x1800181b9`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtWriteLogEx` at `0x1800181b9`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapGetImageNameFromProcessId` at `0x180018168`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapGetImageNameFromProcessId` at `0x180018168`

## pseudocode

```c
__int64 __fastcall LsaIAuditSamEvent(
        int a1,
        unsigned int a2,
        ULONG a3,
        void *a4,
        unsigned __int16 *a5,
        ULONG *a6,
        void *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        ULONG *a10,
        int *a11,
        ULONG_PTR *a12,
        struct _LSAP_AUDIT_USER_ATTR_VALUES *a13)
{
  struct _RTL_BALANCED_NODE *v13; // r13
  int v15; // edi
  void **v16; // rax
  void *v17; // r13
  USHORT v18; // ax
  void *v19; // rdx
  ULONG *p_Length; // rdi
  __int64 v22; // rax
  PSID v23; // r13
  ULONG v24; // ecx
  ULONG v25; // ecx
  __int16 *p_DestinationSid; // rdi
  ULONG *v27; // rbx
  ULONG v28; // esi
  ULONG v29; // eax
  ULONG v30; // r15d
  ULONG v31; // ebx
  ULONG *v32; // rbx
  ULONG ParameterCount; // edx
  struct _LSAP_AUDIT_USER_ATTR_VALUES *v34; // rdi
  ULONG_PTR v35; // rax
  struct _RTL_BALANCED_NODE *v36; // rdx
  ULONG v37; // eax
  PSID v38; // rcx
  ULONG *v39; // rdi
  struct _RTL_BALANCED_NODE *v40; // rax
  struct _LSAP_AUDIT_USER_ATTR_VALUES *v41; // rdi
  unsigned __int16 *v42; // rdx
  _WORD *v43; // rdx
  unsigned __int16 *v44; // rdx
  ULONG v45; // eax
  ULONG v46; // edi
  ULONG v47; // edi
  PUCHAR v48; // rax
  ULONG *v49; // rdi
  ULONG *v50; // rdi
  int v51; // eax
  ULONG v52; // ecx
  struct _LSAP_AUDIT_USER_ATTR_VALUES *v53; // rdi
  struct _LSAP_AUDIT_USER_ATTR_VALUES *v54; // rcx
  ULONG *v55; // rbx
  struct _LSAP_AUDIT_USER_ATTR_VALUES *v56; // rdi
  unsigned __int16 *v57; // rdx
  unsigned __int16 *v58; // rdx
  ULONG_PTR v59; // rcx
  struct _LSAP_AUDIT_USER_ATTR_VALUES *v60; // rdi
  __int64 v61; // rax
  int v62; // edx
  __int64 v63; // rax
  ULONG_PTR v64; // rax
  int v65; // [rsp+48h] [rbp-C0h] BYREF
  USHORT v66; // [rsp+4Ch] [rbp-BCh] BYREF
  ULONG SubAuthority[2]; // [rsp+50h] [rbp-B8h]
  struct _LSAP_AUDIT_USER_ATTR_VALUES *v68; // [rsp+58h] [rbp-B0h]
  __int64 v69; // [rsp+60h] [rbp-A8h]
  __int64 v70; // [rsp+68h] [rbp-A0h]
  PSID Sid; // [rsp+70h] [rbp-98h]
  ULONG_PTR v72; // [rsp+78h] [rbp-90h] BYREF
  void **v73; // [rsp+80h] [rbp-88h] BYREF
  struct _RTL_BALANCED_NODE *v74; // [rsp+88h] [rbp-80h] BYREF
  struct _RTL_BALANCED_NODE *v75; // [rsp+90h] [rbp-78h]
  PSID v76; // [rsp+98h] [rbp-70h]
  struct _UNICODE_STRING v77; // [rsp+A0h] [rbp-68h] BYREF
  struct _UNICODE_STRING v78; // [rsp+B0h] [rbp-58h] BYREF
  struct _UNICODE_STRING v79; // [rsp+C0h] [rbp-48h] BYREF
  struct _UNICODE_STRING v80; // [rsp+D0h] [rbp-38h] BYREF
  struct _UNICODE_STRING v81; // [rsp+E0h] [rbp-28h] BYREF
  _SE_ADT_PARAMETER_ARRAY_EX v82; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v83[544]; // [rsp+518h] [rbp+410h] BYREF
  char v84; // [rsp+738h] [rbp+630h] BYREF
  char DestinationSid; // [rsp+838h] [rbp+730h] BYREF

  v13 = 0;
  v68 = a13;
  SubAuthority[0] = a3;
  LODWORD(v69) = a1;
  Sid = a4;
  v76 = a7;
  v72 = 999;
  v75 = 0;
  v70 = 0;
  v66 = 0;
  v73 = 0;
  memset_0(&v82, 0, sizeof(v82));
  LOBYTE(v65) = 0;
  memset_0(v83, 0, 0x21Au);
  v74 = (struct _RTL_BALANCED_NODE *)v83;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  if ( a5 && a5[1] < *a5 || a8 && a8[1] < *a8 || a9 && a9[1] < *a9 )
  {
    v15 = -1073741811;
    goto LABEL_15;
  }
  if ( a11 && (unsigned int)*a11 >= 0x43 )
  {
    v15 = -1073741811;
    goto LABEL_15;
  }
  if ( a2 == 644 )
  {
    v16 = (void **)((char *)WellKnownSids + 720);
LABEL_11:
    v17 = *v16;
    memset_0(&v82, 0, sizeof(v82));
    v82.CategoryId = (a2 != 643) + 6;
    v82.AuditId = a2 | 0x1000;
    v82.Version = SubAuthority[0];
    v18 = 8;
    if ( (int)v69 < 0 )
      v18 = 16;
    v82.Type = v18;
    v82.ParameterCount = 0;
    v15 = LsapAdtCheckAuditAvailableInArray((unsigned __int16 (*const)[2])qword_18019B900, 0x41u, a2, &v66);
    if ( v15 < 0
      || (unsigned __int8)IsLsapAdtInitializeCrashOnAuditFailPresent()
      && (v15 = LsapAdtAuditingEnabledByLogonId(v66, &v72, v82.Type, &v65), v15 < 0) )
    {
LABEL_14:
      v13 = (struct _RTL_BALANCED_NODE *)v70;
      goto LABEL_15;
    }
    if ( !(_BYTE)v65 )
      goto LABEL_20;
    v82.FlatSubCategoryId = v66;
    v82.Parameters[v82.ParameterCount].Type = SeAdtParmTypeSid;
    p_Length = &v82.Parameters[v82.ParameterCount].Length;
    if ( v17 )
    {
      *p_Length = RtlLengthSid(v17);
      v82.Parameters[v82.ParameterCount].Address = v17;
    }
    else
    {
      *p_Length = RtlLengthSid(&AdtpNullSid);
      v82.Parameters[v82.ParameterCount].Address = &AdtpNullSid;
    }
    v82.Parameters[++v82.ParameterCount].Type = SeAdtParmTypeString;
    v82.Parameters[v82.ParameterCount].Length = LsapSubsystemName.Length + 16;
    v82.Parameters[v82.ParameterCount].Address = *(PVOID *)&LsapSubsystemName.Length;
    v22 = ++v82.ParameterCount;
    if ( a5 )
    {
      v82.Parameters[(unsigned int)v22].Type = SeAdtParmTypeString;
      v82.Parameters[v82.ParameterCount].Length = *a5 + 16;
      v82.Parameters[v82.ParameterCount].Address = a5;
      v22 = ++v82.ParameterCount;
    }
    if ( a6 )
    {
      SubAuthority[0] = *RtlSubAuthorityCountSid(Sid);
      v45 = RtlLengthRequiredSid(SubAuthority[0] + 1);
      v46 = v45;
      if ( v45 <= 0x100 )
      {
        v13 = (struct _RTL_BALANCED_NODE *)&v84;
      }
      else
      {
        v70 = LsapAllocate(v45);
        v13 = (struct _RTL_BALANCED_NODE *)v70;
        if ( !v70 )
        {
          v15 = -1073741801;
          goto LABEL_15;
        }
      }
      RtlCopySid(v46, v13, Sid);
      v47 = *a6;
      *RtlSubAuthoritySid(v13, SubAuthority[0]) = v47;
      v48 = RtlSubAuthorityCountSid(v13);
      *v48 = LOBYTE(SubAuthority[0]) + 1;
      v82.Parameters[v82.ParameterCount].Type = SeAdtParmTypeSid;
      v49 = &v82.Parameters[v82.ParameterCount].Length;
      if ( v13 )
      {
        *v49 = RtlLengthSid(v13);
        v82.Parameters[v82.ParameterCount].Address = v13;
      }
      else
      {
        *v49 = RtlLengthSid(&AdtpNullSid);
        v82.Parameters[v82.ParameterCount].Address = &AdtpNullSid;
      }
      v22 = ++v82.ParameterCount;
    }
    v23 = v76;
    if ( v76 )
    {
      v38 = v76;
      v82.Parameters[v22].Type = SeAdtParmTypeSid;
      v39 = &v82.Parameters[v82.ParameterCount].Length;
      *v39 = RtlLengthSid(v38);
      v82.Parameters[v82.ParameterCount].Address = v23;
    }
    else
    {
      if ( a2 != 669 && a2 != 734 )
        goto LABEL_48;
      v82.Parameters[v22].Type = SeAdtParmTypeSid;
      v50 = &v82.Parameters[v82.ParameterCount].Length;
      *v50 = RtlLengthSid(&AdtpNullSid);
      v82.Parameters[v82.ParameterCount].Address = &AdtpNullSid;
    }
    v22 = ++v82.ParameterCount;
LABEL_48:
    if ( a8 )
    {
      v24 = *a8 + 16;
      v82.Parameters[v22].Type = SeAdtParmTypeString;
      v82.Parameters[v82.ParameterCount].Length = v24;
      v82.Parameters[v82.ParameterCount].Address = a8;
      v22 = ++v82.ParameterCount;
    }
    if ( a9 )
    {
      v25 = *a9 + 16;
      v82.Parameters[v22].Type = SeAdtParmTypeString;
      v82.Parameters[v82.ParameterCount].Length = v25;
      v82.Parameters[v82.ParameterCount].Address = a9;
      v22 = ++v82.ParameterCount;
    }
    p_DestinationSid = (__int16 *)Sid;
    if ( !Sid || a6 )
    {
      v27 = a10;
      if ( !a10 )
      {
LABEL_60:
        v82.Parameters[v22].Type = SeAdtParmTypeLogonId;
        v82.Parameters[v82.ParameterCount].Length = 8;
        v82.Parameters[v82.ParameterCount].Data[0] = v72;
        ParameterCount = ++v82.ParameterCount;
        if ( a11 )
        {
          v51 = *a11;
          v82.Parameters[ParameterCount].Type = SeAdtParmTypePrivs;
          if ( v51 )
            v52 = 12 * v51 + 8;
          else
            v52 = 8;
          v82.Parameters[v82.ParameterCount].Length = v52;
          v82.Parameters[v82.ParameterCount].Address = a11;
          ParameterCount = ++v82.ParameterCount;
          if ( a2 == 4799 )
            goto LABEL_62;
        }
        else
        {
          if ( a2 - 4798 <= 1 )
            goto LABEL_62;
          v82.ParameterCount = ++ParameterCount;
        }
        if ( a2 > 0x12BE )
        {
LABEL_67:
          LsapAdtWriteLogEx(0, &v82, 0);
          v13 = (struct _RTL_BALANCED_NODE *)v70;
          v15 = 0;
          goto LABEL_16;
        }
        if ( a2 != 4798 )
        {
          switch ( a2 )
          {
            case 0x270u:
            case 0x282u:
              LsapAdtAppendUserAttrValues(&v82, v68, 0);
              goto LABEL_67;
            case 0x277u:
            case 0x27Bu:
            case 0x27Fu:
            case 0x281u:
            case 0x288u:
            case 0x289u:
            case 0x28Du:
            case 0x28Eu:
            case 0x292u:
            case 0x293u:
            case 0x297u:
            case 0x298u:
            case 0x2AFu:
            case 0x2B0u:
            case 0x2B6u:
            case 0x2B7u:
              LsapAdtAppendGroupAttrValues(&v82, v68);
              goto LABEL_67;
            case 0x278u:
            case 0x27Cu:
            case 0x28Au:
            case 0x28Fu:
            case 0x294u:
            case 0x299u:
            case 0x2B1u:
              if ( a12 )
              {
                v64 = *a12;
                v82.Parameters[ParameterCount].Type = SeAdtParmTypeTime;
                v82.Parameters[v82.ParameterCount].Length = 8;
                v82.Parameters[v82.ParameterCount].Data[0] = v64;
                goto LABEL_88;
              }
              goto LABEL_67;
            case 0x283u:
              LsapAdtAppendDomainAttrValues(&v82, v68, &v77, &v78, &v79, &v80, &v81);
              goto LABEL_67;
            case 0x285u:
            case 0x286u:
              LsapAdtAppendUserAttrValues(&v82, v68, 1);
              goto LABEL_67;
            case 0x29Du:
            case 0x2DEu:
              v53 = v68;
              if ( v68 )
              {
                v54 = v68;
                v82.Parameters[ParameterCount].Type = SeAdtParmTypeSidList;
                v55 = &v82.Parameters[v82.ParameterCount].Length;
                *v55 = LsapSidListSize(v54);
                v82.Parameters[v82.ParameterCount].Address = v53;
                ParameterCount = v82.ParameterCount;
              }
              v82.ParameterCount = ParameterCount + 1;
              goto LABEL_67;
            case 0x2B9u:
              v82.ParameterCount = ParameterCount - 1;
              _mm_lfence();
              v56 = v68;
              v57 = *(unsigned __int16 **)v68;
              if ( **(_WORD **)v68 )
              {
                v82.Parameters[v82.ParameterCount].Type = SeAdtParmTypeString;
                v82.Parameters[v82.ParameterCount].Length = *v57 + 16;
                v82.Parameters[v82.ParameterCount].Address = v57;
              }
              else
              {
                v82.Parameters[v82.ParameterCount].Type = SeAdtParmTypeNone;
                v82.Parameters[v82.ParameterCount].Length = 0;
                v82.Parameters[v82.ParameterCount].Address = 0;
              }
              ++v82.ParameterCount;
              if ( **((_WORD **)v56 + 1) )
              {
                _mm_lfence();
                v58 = (unsigned __int16 *)*((_QWORD *)v56 + 1);
                v82.Parameters[v82.ParameterCount].Type = SeAdtParmTypeString;
                v82.Parameters[v82.ParameterCount].Length = *v58 + 16;
                v82.Parameters[v82.ParameterCount].Address = v58;
                goto LABEL_124;
              }
              v82.Parameters[v82.ParameterCount].Type = SeAdtParmTypeNone;
              goto LABEL_123;
            case 0x2BAu:
              v60 = v68;
              v61 = ParameterCount - 1;
              v82.ParameterCount = ParameterCount - 1;
              v62 = *(unsigned __int16 *)v68;
              v63 = v61;
              if ( (_WORD)v62 )
              {
                v82.Parameters[v63].Type = SeAdtParmTypeString;
                v82.Parameters[v82.ParameterCount].Length = v62 + 16;
                v82.Parameters[v82.ParameterCount].Address = v60;
              }
              else
              {
                v82.Parameters[v63].Type = SeAdtParmTypeNone;
LABEL_123:
                v82.Parameters[v82.ParameterCount].Length = 0;
                v82.Parameters[v82.ParameterCount].Address = 0;
              }
LABEL_124:
              v82.Parameters[++v82.ParameterCount].Type = SeAdtParmTypeHexUlong;
              v59 = (unsigned int)v69;
              v82.Parameters[v82.ParameterCount].Length = 4;
              v82.Parameters[v82.ParameterCount].Data[0] = v59;
              goto LABEL_88;
            case 0x2BDu:
              v82.ParameterCount = ParameterCount - 1;
              _mm_lfence();
              v41 = v68;
              v42 = *(unsigned __int16 **)v68;
              if ( **(_WORD **)v68 )
              {
                v82.Parameters[v82.ParameterCount].Type = SeAdtParmTypeString;
                v82.Parameters[v82.ParameterCount].Length = *v42 + 16;
                v82.Parameters[v82.ParameterCount].Address = v42;
              }
              else
              {
                v82.Parameters[v82.ParameterCount].Type = SeAdtParmTypeNone;
                v82.Parameters[v82.ParameterCount].Length = 0;
                v82.Parameters[v82.ParameterCount].Address = 0;
              }
              v43 = (_WORD *)*((_QWORD *)v41 + 1);
              ++v82.ParameterCount;
              if ( *v43 )
              {
                v82.Parameters[v82.ParameterCount].Type = SeAdtParmTypeString;
                v82.Parameters[v82.ParameterCount].Length = (unsigned __int16)*v43 + 16;
                v82.Parameters[v82.ParameterCount].Address = v43;
              }
              else
              {
                v82.Parameters[v82.ParameterCount].Type = SeAdtParmTypeNone;
                v82.Parameters[v82.ParameterCount].Length = 0;
                v82.Parameters[v82.ParameterCount].Address = 0;
              }
              ++v82.ParameterCount;
              if ( **((_WORD **)v41 + 2) )
              {
                _mm_lfence();
                v44 = (unsigned __int16 *)*((_QWORD *)v41 + 2);
                v82.Parameters[v82.ParameterCount].Type = SeAdtParmTypeString;
                v82.Parameters[v82.ParameterCount].Length = *v44 + 16;
                v82.Parameters[v82.ParameterCount].Address = v44;
LABEL_88:
                ++v82.ParameterCount;
              }
              else
              {
                v82.Parameters[v82.ParameterCount].Type = SeAdtParmTypeNone;
                v82.Parameters[v82.ParameterCount].Length = 0;
                v82.Parameters[v82.ParameterCount++].Address = 0;
              }
              break;
            default:
              goto LABEL_67;
          }
          goto LABEL_67;
        }
LABEL_62:
        v34 = v68;
        v82.Parameters[ParameterCount].Type = SeAdtParmTypePtr;
        v82.Parameters[v82.ParameterCount].Length = 8;
        if ( v34 )
        {
          v35 = *(_QWORD *)v34;
          v82.Parameters[v82.ParameterCount++].Data[0] = *(_QWORD *)v34;
          if ( !(unsigned int)LsapGetImageNameFromProcessId((unsigned int)v35, 538, &v74) )
          {
            v36 = v74;
            v82.Parameters[v82.ParameterCount].Type = SeAdtParmTypeString;
            v82.Parameters[v82.ParameterCount].Length = LOWORD(v36->Children[0]) + 16;
            v82.Parameters[v82.ParameterCount].Address = v36;
          }
          v37 = v82.ParameterCount;
        }
        else
        {
          v82.Parameters[v82.ParameterCount].Data[0] = 0;
          v37 = v82.ParameterCount + 1;
        }
        v82.ParameterCount = v37 + 1;
        goto LABEL_67;
      }
    }
    else
    {
      v27 = a10;
      if ( !a10 )
      {
        v82.Parameters[v22].Type = SeAdtParmTypeSid;
LABEL_59:
        v32 = &v82.Parameters[v82.ParameterCount].Length;
        *v32 = RtlLengthSid(p_DestinationSid);
        v82.Parameters[v82.ParameterCount].Address = p_DestinationSid;
        v22 = ++v82.ParameterCount;
        goto LABEL_60;
      }
    }
    v28 = *RtlSubAuthorityCountSid(Sid);
    v29 = RtlLengthRequiredSid(v28 + 1);
    v30 = v29;
    if ( v29 <= 0x100 )
    {
      p_DestinationSid = (__int16 *)&DestinationSid;
      goto LABEL_57;
    }
    v40 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v29);
    v75 = v40;
    if ( v40 )
    {
      p_DestinationSid = (__int16 *)v40;
LABEL_57:
      RtlCopySid(v30, p_DestinationSid, Sid);
      v31 = *v27;
      *RtlSubAuthoritySid(p_DestinationSid, v28) = v31;
      *RtlSubAuthorityCountSid(p_DestinationSid) = v28 + 1;
      v82.Parameters[v82.ParameterCount].Type = SeAdtParmTypeSid;
      if ( !p_DestinationSid )
        p_DestinationSid = &AdtpNullSid;
      goto LABEL_59;
    }
    v15 = -1073741801;
    goto LABEL_14;
  }
  v15 = LsapQueryClientInfo(&v73, &v72);
  if ( v15 >= 0 )
  {
    v16 = v73;
    goto LABEL_11;
  }
LABEL_15:
  LsapAuditFailed((unsigned int)v15);
LABEL_16:
  if ( v13 )
    LsapSubProv_FreeRoutine(v13, v19);
  if ( v75 )
    LsapSubProv_FreeRoutine(v75, v19);
LABEL_20:
  if ( v77.Buffer )
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v77.Buffer, v19);
  if ( v78.Buffer )
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v78.Buffer, v19);
  if ( v79.Buffer )
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v79.Buffer, v19);
  if ( v80.Buffer )
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v80.Buffer, v19);
  if ( v81.Buffer )
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v81.Buffer, v19);
  if ( v73 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v73);
  if ( v74 && v74 != (struct _RTL_BALANCED_NODE *)v83 )
    LsapSubProv_FreeRoutine(v74, v19);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180017b80  mov     r11, rsp
0x180017b83  push    rbp
0x180017b84  push    rdi
0x180017b85  lea     rbp, [r11-878h]
0x180017b8c  sub     rsp, 968h
0x180017b93  mov     rax, cs:__security_cookie
0x180017b9a  xor     rax, rsp
0x180017b9d  mov     [rbp+870h+var_40], rax
0x180017ba4  mov     rax, [rbp+870h+arg_60]
0x180017bab  xor     edi, edi
0x180017bad  mov     [r11+8], rbx
0x180017bb1  mov     [r11-18h], rsi
0x180017bb5  mov     [r11-20h], r12
0x180017bb9  mov     [r11-28h], r13
0x180017bbd  mov     r13d, edi
0x180017bc0  mov     [r11-30h], r14
0x180017bc4  mov     r14d, edx
0x180017bc7  mov     [rsp+970h+var_920], rax
0x180017bcc  xor     edx, edx; Val
0x180017bce  mov     rax, [rbp+870h+arg_30]
0x180017bd5  mov     [rsp+970h+SubAuthority], r8d
0x180017bda  mov     r8d, 420h; Size
0x180017be0  mov     dword ptr [rsp+970h+var_918], ecx
0x180017be4  lea     rcx, [rbp+870h+var_880]; void *
0x180017be8  mov     [r11-38h], r15
0x180017bec  mov     [rsp+970h+Sid], r9
0x180017bf1  mov     [rbp+870h+var_8E0], rax
0x180017bf5  mov     [rsp+970h+var_900], 3E7h
0x180017bfe  mov     [rbp+870h+var_8E8], rdi
0x180017c02  mov     [rsp+970h+var_910], rdi
0x180017c07  mov     [rsp+970h+var_92C], di
0x180017c0c  mov     [rsp+970h+var_8F8], rdi
0x180017c11  call    memset_0
0x180017c16  xor     edx, edx; Val
0x180017c18  mov     byte ptr [rsp+970h+var_930], dil
0x180017c1d  mov     r8d, 21Ah; Size
0x180017c23  lea     rcx, [rbp+870h+var_460]; void *
0x180017c2a  call    memset_0
0x180017c2f  mov     r15, [rbp+870h+arg_20]
0x180017c36  lea     rax, [rbp+870h+var_460]
0x180017c3d  mov     [rbp+870h+var_8F0], rax
0x180017c41  xorps   xmm0, xmm0
0x180017c44  xorps   xmm1, xmm1
0x180017c47  movups  xmmword ptr [rbp+870h+var_8D8.Length], xmm0
0x180017c4b  movups  xmmword ptr [rbp+870h+var_8C8.Length], xmm1
0x180017c4f  movups  xmmword ptr [rbp+870h+var_8B8.Length], xmm0
0x180017c53  movups  xmmword ptr [rbp+870h+var_8A8.Length], xmm1
0x180017c57  movups  xmmword ptr [rbp+870h+var_898.Length], xmm0
0x180017c5b  test    r15, r15
0x180017c5e  jz      short loc_180017C6F
0x180017c60  movzx   eax, word ptr [r15]
0x180017c64  cmp     [r15+2], ax
0x180017c69  jb      loc_180018304
0x180017c6f  mov     rbx, [rbp+870h+arg_38]
0x180017c76  test    rbx, rbx
0x180017c79  jz      short loc_180017C88
0x180017c7b  movzx   eax, word ptr [rbx]
0x180017c7e  cmp     [rbx+2], ax
0x180017c82  jb      loc_180018304
0x180017c88  mov     rsi, [rbp+870h+arg_40]
0x180017c8f  test    rsi, rsi
0x180017c92  jz      short loc_180017CA1
0x180017c94  movzx   eax, word ptr [rsi]
0x180017c97  cmp     [rsi+2], ax
0x180017c9b  jb      loc_180018304
0x180017ca1  mov     r12, [rbp+870h+arg_50]
0x180017ca8  test    r12, r12
0x180017cab  jnz     loc_1800184FC
0x180017cb1  cmp     r14d, 284h
0x180017cb8  jz      loc_180017E55
0x180017cbe  lea     rdx, [rsp+970h+var_900]
0x180017cc3  lea     rcx, [rsp+970h+var_8F8]
0x180017cc8  call    cs:__imp_LsapQueryClientInfo
0x180017ccf  nop     dword ptr [rax+rax+00h]
0x180017cd4  mov     edi, eax
0x180017cd6  test    eax, eax
0x180017cd8  js      loc_180017D63
0x180017cde  mov     rax, [rsp+970h+var_8F8]
0x180017ce3  xor     edi, edi
0x180017ce5  mov     r13, [rax]
0x180017ce8  lea     rcx, [rbp+870h+var_880]; void *
0x180017cec  xor     edx, edx; Val
0x180017cee  mov     r8d, 420h; Size
0x180017cf4  call    memset_0
0x180017cf9  cmp     r14d, 283h
0x180017d00  mov     eax, edi
0x180017d02  setnz   al
0x180017d05  add     eax, 6
0x180017d08  mov     [rbp+870h+var_880.CategoryId], eax
0x180017d0b  mov     eax, r14d
0x180017d0e  bts     eax, 0Ch
0x180017d12  cmp     dword ptr [rsp+970h+var_918], 0
0x180017d17  mov     [rbp+870h+var_880.AuditId], eax
0x180017d1a  mov     eax, [rsp+970h+SubAuthority]
0x180017d1e  mov     [rbp+870h+var_880.Version], eax
0x180017d21  mov     eax, 8
0x180017d26  jl      loc_180018247
0x180017d2c  movzx   r8d, r14w
0x180017d30  mov     [rbp+870h+var_880.Type], ax
0x180017d34  lea     r9, [rsp+970h+var_92C]
0x180017d39  mov     [rbp+870h+var_880.ParameterCount], edi
0x180017d3c  mov     edx, 41h ; 'A'
0x180017d41  lea     rcx, qword_18019B900
0x180017d48  call    cs:__imp_?LsapAdtCheckAuditAvailableInArray@@YAJQEAY01GKGPEAG@Z; LsapAdtCheckAuditAvailableInArray(ushort (* const)[2],ulong,ushort,ushort *)
0x180017d4f  nop     dword ptr [rax+rax+00h]
0x180017d54  mov     edi, eax
0x180017d56  test    eax, eax
0x180017d58  jns     loc_180017E67
0x180017d5e  mov     r13, [rsp+970h+var_910]
0x180017d63  mov     ecx, edi
0x180017d65  call    cs:__imp_LsapAuditFailed
0x180017d6c  nop     dword ptr [rax+rax+00h]
0x180017d71  test    r13, r13
0x180017d74  jnz     loc_1800188F3
0x180017d7a  mov     rcx, [rbp+870h+var_8E8]; struct _RTL_BALANCED_NODE *
0x180017d7e  test    rcx, rcx
0x180017d81  jnz     loc_180018900
0x180017d87  mov     rcx, [rbp+870h+var_8D8.Buffer]; struct _RTL_BALANCED_NODE *
0x180017d8b  mov     r15, [rsp+970h+var_30]
0x180017d93  mov     r14, [rsp+970h+var_28]
0x180017d9b  mov     r13, [rsp+970h+var_20]
0x180017da3  mov     r12, [rsp+970h+var_18]
0x180017dab  mov     rsi, [rsp+960h]
0x180017db3  mov     rbx, [rsp+970h+arg_0]
0x180017dbb  test    rcx, rcx
0x180017dbe  jnz     loc_18001890A
0x180017dc4  mov     rcx, [rbp+870h+var_8C8.Buffer]; struct _RTL_BALANCED_NODE *
0x180017dc8  test    rcx, rcx
0x180017dcb  jnz     loc_180018914
0x180017dd1  mov     rcx, [rbp+870h+var_8B8.Buffer]; struct _RTL_BALANCED_NODE *
0x180017dd5  test    rcx, rcx
0x180017dd8  jnz     loc_18001891E
0x180017dde  mov     rcx, [rbp+870h+var_8A8.Buffer]; struct _RTL_BALANCED_NODE *
0x180017de2  test    rcx, rcx
0x180017de5  jnz     loc_180018928
0x180017deb  mov     rcx, [rbp+870h+var_898.Buffer]; struct _RTL_BALANCED_NODE *
0x180017def  test    rcx, rcx
0x180017df2  jnz     loc_180018932
0x180017df8  cmp     [rsp+970h+var_8F8], 0
0x180017dfe  jz      short loc_180017E20
0x180017e00  mov     rcx, gs:60h
0x180017e09  xor     edx, edx; Flags
0x180017e0b  mov     r8, [rsp+970h+var_8F8]; P
0x180017e10  mov     rcx, [rcx+30h]; HeapHandle
0x180017e14  call    cs:__imp_RtlFreeHeap
0x180017e1b  nop     dword ptr [rax+rax+00h]
0x180017e20  mov     rcx, [rbp+870h+var_8F0]; struct _RTL_BALANCED_NODE *
0x180017e24  test    rcx, rcx
0x180017e27  jz      short loc_180017E39
0x180017e29  lea     rax, [rbp+870h+var_460]
0x180017e30  cmp     rcx, rax
0x180017e33  jnz     loc_18001893C
0x180017e39  mov     eax, edi
0x180017e3b  mov     rcx, [rbp+870h+var_40]
0x180017e42  xor     rcx, rsp; StackCookie
0x180017e45  call    __security_check_cookie
0x180017e4a  add     rsp, 968h
0x180017e51  pop     rdi
0x180017e52  pop     rbp
0x180017e53  retn
0x180017e55  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180017e5c  add     rax, 2D0h
0x180017e62  jmp     loc_180017CE5
0x180017e67  call    IsLsapAdtInitializeCrashOnAuditFailPresent
0x180017e6c  test    al, al
0x180017e6e  jz      short loc_180017E9A
0x180017e70  movzx   r8d, [rbp+870h+var_880.Type]
0x180017e75  lea     r9, [rsp+970h+var_930]
0x180017e7a  movzx   ecx, [rsp+970h+var_92C]
0x180017e7f  lea     rdx, [rsp+970h+var_900]
0x180017e84  call    cs:__imp_LsapAdtAuditingEnabledByLogonId
0x180017e8b  nop     dword ptr [rax+rax+00h]
0x180017e90  mov     edi, eax
0x180017e92  test    eax, eax
0x180017e94  js      loc_180017D5E
0x180017e9a  cmp     byte ptr [rsp+970h+var_930], 0
0x180017e9f  jz      loc_180017D87
0x180017ea5  movzx   eax, [rsp+970h+var_92C]
0x180017eaa  lea     rdi, [rbp+870h+var_880.Parameters.Length]
0x180017eae  mov     [rbp+870h+var_880.FlatSubCategoryId], ax
0x180017eb2  mov     eax, [rbp+870h+var_880.ParameterCount]
0x180017eb5  shl     rax, 5
0x180017eb9  mov     [rbp+rax+870h+var_880.Parameters.Type], 4
0x180017ec1  mov     eax, [rbp+870h+var_880.ParameterCount]
0x180017ec4  shl     rax, 5
0x180017ec8  add     rdi, rax
0x180017ecb  test    r13, r13
0x180017ece  jz      loc_180018251
0x180017ed4  mov     rcx, r13; Sid
0x180017ed7  call    cs:__imp_RtlLengthSid
0x180017ede  nop     dword ptr [rax+rax+00h]
0x180017ee3  mov     [rdi], eax
0x180017ee5  mov     eax, [rbp+870h+var_880.ParameterCount]
0x180017ee8  shl     rax, 5
0x180017eec  mov     [rbp+rax+870h+var_880.Parameters.Address], r13
0x180017ef1  mov     eax, [rbp+870h+var_880.ParameterCount]
0x180017ef4  mov     rdx, cs:__imp_?LsapSubsystemName@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING LsapSubsystemName
0x180017efb  inc     eax
0x180017efd  mov     [rbp+870h+var_880.ParameterCount], eax
0x180017f00  mov     ecx, eax
0x180017f02  shl     rcx, 5
0x180017f06  mov     [rbp+rcx+870h+var_880.Parameters.Type], 1
0x180017f0e  movzx   ecx, word ptr [rdx]
0x180017f11  mov     eax, [rbp+870h+var_880.ParameterCount]
0x180017f14  add     ecx, 10h
0x180017f17  shl     rax, 5
0x180017f1b  mov     [rbp+rax+870h+var_880.Parameters.Length], ecx
0x180017f1f  mov     eax, [rbp+870h+var_880.ParameterCount]
0x180017f22  shl     rax, 5
0x180017f26  mov     [rbp+rax+870h+var_880.Parameters.Address], rdx
0x180017f2b  mov     eax, [rbp+870h+var_880.ParameterCount]
0x180017f2e  inc     eax
0x180017f30  mov     [rbp+870h+var_880.ParameterCount], eax
0x180017f33  mov     ecx, eax
0x180017f35  test    r15, r15
0x180017f38  jnz     loc_180018511
0x180017f3e  mov     r15, [rbp+870h+arg_28]
0x180017f45  test    r15, r15
0x180017f48  jnz     loc_180018475
0x180017f4e  lea     rcx, AdtpNullSid; Sid
0x180017f55  mov     r13, [rbp+870h+var_8E0]
0x180017f59  test    r13, r13
0x180017f5c  jnz     loc_1800181E6
0x180017f62  cmp     r14d, 29Dh
0x180017f69  jz      loc_180018611
0x180017f6f  cmp     r14d, 2DEh
0x180017f76  jz      loc_180018611
0x180017f7c  test    rbx, rbx
0x180017f7f  jz      short loc_180017FB2
0x180017f81  movzx   ecx, word ptr [rbx]
0x180017f84  shl     rax, 5
0x180017f88  add     ecx, 10h
0x180017f8b  mov     [rbp+rax+870h+var_880.Parameters.Type], 1
0x180017f93  mov     eax, [rbp+870h+var_880.ParameterCount]
0x180017f96  shl     rax, 5
0x180017f9a  mov     [rbp+rax+870h+var_880.Parameters.Length], ecx
0x180017f9e  mov     eax, [rbp+870h+var_880.ParameterCount]
0x180017fa1  shl     rax, 5
0x180017fa5  mov     [rbp+rax+870h+var_880.Parameters.Address], rbx
0x180017faa  mov     eax, [rbp+870h+var_880.ParameterCount]
0x180017fad  inc     eax
0x180017faf  mov     [rbp+870h+var_880.ParameterCount], eax
0x180017fb2  test    rsi, rsi
0x180017fb5  jz      short loc_180017FE8
0x180017fb7  movzx   ecx, word ptr [rsi]
0x180017fba  shl     rax, 5
0x180017fbe  add     ecx, 10h
0x180017fc1  mov     [rbp+rax+870h+var_880.Parameters.Type], 1
0x180017fc9  mov     eax, [rbp+870h+var_880.ParameterCount]
0x180017fcc  shl     rax, 5
0x180017fd0  mov     [rbp+rax+870h+var_880.Parameters.Length], ecx
0x180017fd4  mov     eax, [rbp+870h+var_880.ParameterCount]
0x180017fd7  shl     rax, 5
0x180017fdb  mov     [rbp+rax+870h+var_880.Parameters.Address], rsi
0x180017fe0  mov     eax, [rbp+870h+var_880.ParameterCount]
0x180017fe3  inc     eax
0x180017fe5  mov     [rbp+870h+var_880.ParameterCount], eax
0x180017fe8  mov     rdi, [rsp+970h+Sid]
0x180017fed  test    rdi, rdi
0x180017ff0  jz      loc_1800181D1
0x180017ff6  test    r15, r15
0x180017ff9  jnz     loc_1800181D1
0x180017fff  mov     rbx, [rbp+870h+arg_48]
0x180018006  test    rbx, rbx
0x180018009  jz      loc_180018651
0x18001800f  mov     rcx, rdi; Sid
0x180018012  call    cs:__imp_RtlSubAuthorityCountSid
0x180018019  nop     dword ptr [rax+rax+00h]
0x18001801e  movzx   esi, byte ptr [rax]
0x180018021  lea     ecx, [rsi+1]; SubAuthorityCount
0x180018024  call    cs:__imp_RtlLengthRequiredSid
0x18001802b  nop     dword ptr [rax+rax+00h]
0x180018030  mov     r15d, eax
0x180018033  cmp     eax, 100h
0x180018038  ja      loc_18001822A
0x18001803e  lea     rdi, [rbp+870h+DestinationSid]
0x180018045  mov     r8, [rsp+970h+Sid]; SourceSid
0x18001804a  mov     rdx, rdi; DestinationSid
0x18001804d  mov     ecx, r15d; DestinationSidLength
0x180018050  call    cs:__imp_RtlCopySid
0x180018057  nop     dword ptr [rax+rax+00h]
0x18001805c  mov     ebx, [rbx]
0x18001805e  mov     edx, esi; SubAuthority
0x180018060  mov     rcx, rdi; Sid
0x180018063  call    cs:__imp_RtlSubAuthoritySid
0x18001806a  nop     dword ptr [rax+rax+00h]
0x18001806f  mov     rcx, rdi; Sid
0x180018072  mov     [rax], ebx
0x180018074  call    cs:__imp_RtlSubAuthorityCountSid
0x18001807b  nop     dword ptr [rax+rax+00h]
0x180018080  inc     sil
0x180018083  mov     [rax], sil
0x180018086  mov     eax, [rbp+870h+var_880.ParameterCount]
0x180018089  shl     rax, 5
0x18001808d  mov     [rbp+rax+870h+var_880.Parameters.Type], 4
0x180018095  test    rdi, rdi
0x180018098  jz      loc_1800182C8
0x18001809e  mov     eax, [rbp+870h+var_880.ParameterCount]
0x1800180a1  lea     rbx, [rbp+870h+var_880.Parameters.Length]
0x1800180a5  shl     rax, 5
  ... truncated ...
```
