# SampDsSetInformationUser(void *,_DSNAME *,ulong,SAMP_CALL_MAPPING *,SAMP_ATTRIBUTE_MAPPING *,uchar)

- ea: `0x180405b2c`
- end: `0x18040666a`
- name: `?SampDsSetInformationUser@@YAJPEAXPEAU_DSNAME@@KPEAUSAMP_CALL_MAPPING@@PEAUSAMP_ATTRIBUTE_MAPPING@@E@Z`
- size: `2878`
- prototype: `int(void *, struct _DSNAME *, unsigned int, struct SAMP_CALL_MAPPING *, struct SAMP_ATTRIBUTE_MAPPING *, unsigned __int8)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180403960`

## callees

- `0x18000bb80`
- `0x18001e090`
- `0x18001ea60`
- `0x180404fa4`
- `0x180405b2c`
- `0x1804066ac`
- `0x1804066e8`
- `0x180406804`
- `0x1804068bc`
- `0x180406908`
- `0x180406944`
- `0x180407464`
- `0x180407590`
- `0x1804076fc`
- `0x180407820`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804060c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180406408`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18040662b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804060c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180406408`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18040662b`
- `ntdll!RtlCompareUnicodeString` at `0x180406244`
- `ntdll!RtlCompareUnicodeString` at `0x180406244`
- `ntdll!RtlFreeHeap` at `0x1804061c4`
- `ntdll!RtlFreeHeap` at `0x1804061c4`
- `ntdll!RtlInitUnicodeString` at `0x180405c16`
- `ntdll!RtlInitUnicodeString` at `0x180406094`
- `ntdll!RtlInitUnicodeString` at `0x1804060d6`
- `ntdll!RtlInitUnicodeString` at `0x1804063d7`
- `ntdll!RtlInitUnicodeString` at `0x180406415`
- `ntdll!RtlInitUnicodeString` at `0x180406638`
- `ntdll!RtlInitUnicodeString` at `0x180405c16`
- `ntdll!RtlInitUnicodeString` at `0x180406094`
- `ntdll!RtlInitUnicodeString` at `0x1804060d6`
- `ntdll!RtlInitUnicodeString` at `0x1804063d7`
- `ntdll!RtlInitUnicodeString` at `0x180406415`
- `ntdll!RtlInitUnicodeString` at `0x180406638`
- `SAMSRV!SampPasswordChangeNotify` at `0x18040637e`
- `SAMSRV!SampPasswordChangeNotify` at `0x18040637e`
- `SAMSRV!SampAuditAccountEnableDisableChange` at `0x180406317`
- `SAMSRV!SampAuditAccountEnableDisableChange` at `0x180406317`
- `SAMSRV!SampSetUserAccountControl` at `0x180405ed9`
- `SAMSRV!SampSetUserAccountControl` at `0x180405ed9`
- `SAMSRV!SampUpdateComputedUserAccountControlBits` at `0x180405e99`
- `SAMSRV!SampUpdateComputedUserAccountControlBits` at `0x180405e99`
- `SAMSRV!SampGetUserAccountSettings` at `0x180405e78`
- `SAMSRV!SampGetUserAccountSettings` at `0x180405e78`
- `SAMSRV!SampDsSetPasswordUser` at `0x180406110`
- `SAMSRV!SampDsSetPasswordUser` at `0x18040644f`
- `SAMSRV!SampDsSetPasswordUser` at `0x180406110`
- `SAMSRV!SampDsSetPasswordUser` at `0x18040644f`
- `SAMSRV!SampComputePasswordExpired` at `0x18040604f`
- `SAMSRV!SampComputePasswordExpired` at `0x18040604f`
- `SAMSRV!SampGetHasNeverTime` at `0x180406032`
- `SAMSRV!SampGetHasNeverTime` at `0x180406032`
- `SAMSRV!SampReplaceUserLogonHours` at `0x18040615e`
- `SAMSRV!SampReplaceUserLogonHours` at `0x18040615e`
- `SAMSRV!SampChangeUserAccountName` at `0x180406229`
- `SAMSRV!SampChangeUserAccountName` at `0x180406229`
- `SAMSRV!SampConvertUiListToApiList` at `0x18040618d`
- `SAMSRV!SampConvertUiListToApiList` at `0x18040618d`
- `SAMSRV!SampAuditAccountNameChange` at `0x1804062f5`
- `SAMSRV!SampAuditAccountNameChange` at `0x1804062f5`
- `SAMSRV!SampSetUnicodeStringAttribute` at `0x1804061a9`
- `SAMSRV!SampSetUnicodeStringAttribute` at `0x1804061f4`
- `SAMSRV!SampSetUnicodeStringAttribute` at `0x1804061a9`
- `SAMSRV!SampSetUnicodeStringAttribute` at `0x1804061f4`
- `SAMSRV!SampReplaceUserV1aFixed` at `0x180405f93`
- `SAMSRV!SampReplaceUserV1aFixed` at `0x1804064e2`
- `SAMSRV!SampReplaceUserV1aFixed` at `0x18040654a`
- `SAMSRV!SampReplaceUserV1aFixed` at `0x180405f93`
- `SAMSRV!SampReplaceUserV1aFixed` at `0x1804064e2`
- `SAMSRV!SampReplaceUserV1aFixed` at `0x18040654a`
- `SAMSRV!SampAssignPrimaryGroup` at `0x180405f68`
- `SAMSRV!SampAssignPrimaryGroup` at `0x180405f68`
- `SAMSRV!SampFlagsToAccountControlEx` at `0x180405e50`
- `SAMSRV!SampFlagsToAccountControlEx` at `0x180405e50`
- `SAMSRV!SampGetUnicodeStringAttribute` at `0x180405d46`
- `SAMSRV!SampGetUnicodeStringAttribute` at `0x180405d46`
- `SAMSRV!SampFreeUnicodeString` at `0x1804065c2`
- `SAMSRV!SampFreeUnicodeString` at `0x1804065cc`
- `SAMSRV!SampFreeUnicodeString` at `0x1804065c2`
- `SAMSRV!SampFreeUnicodeString` at `0x1804065cc`
- `SAMSRV!SampRetrieveUserV1aFixed` at `0x180405d00`
- `SAMSRV!SampRetrieveUserV1aFixed` at `0x180405d00`
- `SAMSRV!SampDeReferenceContext` at `0x1804062c1`
- `SAMSRV!SampDeReferenceContext` at `0x18040657f`
- `SAMSRV!SampDeReferenceContext` at `0x1804062c1`
- `SAMSRV!SampDeReferenceContext` at `0x18040657f`
- `SAMSRV!SampLookupContext` at `0x180405cd5`
- `SAMSRV!SampLookupContext` at `0x180405cd5`
- `SAMSRV!SampIncrementActiveThreads` at `0x180405c1c`
- `SAMSRV!SampIncrementActiveThreads` at `0x180405c1c`
- `SAMSRV!SampDecrementActiveThreads` at `0x1804065b8`
- `SAMSRV!SampDecrementActiveThreads` at `0x1804065b8`
- `SAMSRV!SampValidatePwdSettingAttempt` at `0x18040601f`
- `SAMSRV!SampValidatePwdSettingAttempt` at `0x18040601f`
- `SAMSRV!SampGetBehaviorVersion` at `0x18040638f`
- `SAMSRV!SampGetBehaviorVersion` at `0x18040638f`
- `SAMSRV!SampGetSuccessAccountAuditingEnabled` at `0x1804062d5`
- `SAMSRV!SampGetSuccessAccountAuditingEnabled` at `0x1804062d5`

## pseudocode

```c
__int64 __fastcall SampDsSetInformationUser(
        _DWORD *a1,
        struct _DSNAME *a2,
        unsigned int a3,
        struct SAMP_CALL_MAPPING *a4,
        struct SAMP_ATTRIBUTE_MAPPING *a5,
        unsigned __int8 a6)
{
  bool v6; // si
  __int64 v10; // rcx
  struct _UNICODE_STRING *v11; // rax
  __int64 result; // rax
  __int64 v13; // rdx
  char v14; // r13
  unsigned int v15; // r9d
  __int64 v16; // r8
  __int64 v17; // rax
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  signed int UserV1aFixed; // ebx
  unsigned int v29; // r15d
  char v30; // r12
  __int64 v31; // r8
  int v32; // eax
  __int64 v33; // r9
  unsigned int v34; // r15d
  __int64 v35; // rcx
  unsigned int v36; // edx
  unsigned int v37; // edx
  unsigned int v38; // edx
  unsigned int v39; // edx
  unsigned int v40; // edx
  unsigned int v41; // edx
  unsigned int v42; // edx
  unsigned int v43; // edx
  unsigned int v44; // edx
  __int64 v45; // rdx
  char v46; // al
  __int64 v47; // r9
  unsigned int v48; // esi
  int v49; // eax
  signed int v50; // eax
  __int64 v51; // rcx
  _QWORD *HasNeverTime; // rax
  int UShortFromAttrVal; // eax
  __int64 v54; // rax
  PWSTR v55; // rcx
  PWSTR v56; // rcx
  __int64 v57; // rax
  __int64 v58; // rdx
  unsigned __int16 *v59; // r9
  __int16 v60; // r10
  unsigned int v61; // eax
  UNICODE_STRING *p_String2; // rdx
  __int64 v63; // rcx
  __int64 Length; // rax
  PWSTR Buffer; // rcx
  PWSTR v66; // rcx
  __int64 v67; // rax
  char v68; // r8
  int v69; // eax
  __int64 v70; // rdx
  __int64 v71; // rcx
  PWSTR v72; // rax
  PWSTR v73; // rcx
  __int64 v74; // rax
  struct SAMP_CALL_MAPPING *p_DestinationString; // [rsp+20h] [rbp-E0h]
  bool v76; // [rsp+40h] [rbp-C0h]
  unsigned int v77; // [rsp+44h] [rbp-BCh]
  char v78; // [rsp+48h] [rbp-B8h]
  char v79; // [rsp+49h] [rbp-B7h]
  char v80; // [rsp+4Ah] [rbp-B6h]
  char v81; // [rsp+4Ch] [rbp-B4h]
  struct _UNICODE_STRING v82; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v84; // [rsp+70h] [rbp-90h]
  unsigned int v85; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v86; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v87; // [rsp+7Ch] [rbp-84h] BYREF
  UNICODE_STRING String1; // [rsp+80h] [rbp-80h] BYREF
  int v89; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v90; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v91; // [rsp+98h] [rbp-68h]
  unsigned int v92; // [rsp+9Ch] [rbp-64h]
  unsigned int *v93; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v94[2]; // [rsp+A8h] [rbp-58h] BYREF
  union _LARGE_INTEGER v95; // [rsp+B8h] [rbp-48h] BYREF
  union _LARGE_INTEGER v96; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v97; // [rsp+C8h] [rbp-38h]
  union _LARGE_INTEGER v98; // [rsp+D0h] [rbp-30h] BYREF
  struct _DSNAME *v99; // [rsp+D8h] [rbp-28h]
  __int128 v100; // [rsp+E0h] [rbp-20h] BYREF
  UNICODE_STRING String2; // [rsp+F0h] [rbp-10h] BYREF
  PVOID P[2]; // [rsp+100h] [rbp+0h] BYREF
  struct _UNICODE_STRING v103; // [rsp+110h] [rbp+10h] BYREF
  struct _UNICODE_STRING v104; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v105[24]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v106[3]; // [rsp+148h] [rbp+48h] BYREF
  unsigned int v107; // [rsp+164h] [rbp+64h]
  unsigned int v108; // [rsp+168h] [rbp+68h]
  char v109; // [rsp+16Ch] [rbp+6Ch] BYREF
  unsigned __int16 v110; // [rsp+16Eh] [rbp+6Eh] BYREF
  _OWORD v111[3]; // [rsp+180h] [rbp+80h] BYREF

  v6 = 0;
  v99 = a2;
  v89 = 0;
  v85 = 0;
  v84 = a3;
  v86 = 0;
  v87 = 0;
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = 0;
  v94[0] = 0;
  v103 = 0;
  v94[1] = 0;
  *(_OWORD *)P = 0;
  String2 = 0;
  v79 = 0;
  v104 = 0;
  v78 = 0;
  v82 = 0;
  v96.QuadPart = 0;
  DestinationString = 0;
  v95.QuadPart = 0;
  v100 = 0;
  v98.QuadPart = 0;
  v90 = 0;
  v93 = 0;
  memset(v111, 0, sizeof(v111));
  memset_0(v105, 0, 0x50u);
  v10 = 16;
  v11 = &v82;
  do
  {
    LOBYTE(v11->Length) = 0;
    v11 = (struct _UNICODE_STRING *)((char *)v11 + 1);
    --v10;
  }
  while ( v10 );
  RtlInitUnicodeString(&DestinationString, 0);
  result = SampIncrementActiveThreads();
  if ( (int)result < 0 )
    return result;
  v80 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  if ( a3 )
  {
    v16 = 0;
    while ( 1 )
    {
      v17 = 56 * v16;
      if ( !*((_DWORD *)a4 + 14 * v16) || *(_DWORD *)((char *)a4 + v17 + 4) )
        goto LABEL_26;
      v18 = *((_DWORD *)a5 + 8 * *(unsigned int *)((char *)a4 + v17 + 40));
      if ( v18 <= 0x67 )
        break;
      v24 = v18 - 106;
      if ( !v24 )
      {
        v80 = 1;
LABEL_25:
        v13 = (unsigned int)v13 | 0x20;
        goto LABEL_26;
      }
      v25 = v24 - 1;
      if ( !v25 )
        goto LABEL_25;
      v26 = v25 - 1;
      if ( !v26 || (v27 = v26 - 1) == 0 )
      {
        v13 = (unsigned int)v13 | 4;
        goto LABEL_26;
      }
      if ( v27 == 18 )
        goto LABEL_22;
LABEL_26:
      ++v15;
      ++v16;
      if ( v15 >= a3 )
      {
        v14 = 0;
        goto LABEL_28;
      }
    }
    if ( v18 == 103 )
      goto LABEL_25;
    v19 = v18 - 1;
    if ( !v19 )
      goto LABEL_25;
    v20 = v19 - 2;
    if ( !v20 )
      goto LABEL_25;
    v21 = v20 - 7;
    if ( !v21 )
      goto LABEL_25;
    v22 = v21 - 1;
    if ( !v22 )
      goto LABEL_25;
    v23 = v22 - 3;
    if ( v23 && v23 != 88 )
      goto LABEL_26;
LABEL_22:
    LODWORD(v13) = v13 | 0x80;
    goto LABEL_26;
  }
LABEL_28:
  UserV1aFixed = SampLookupContext(a1, v13, 4, &v89);
  if ( UserV1aFixed < 0 )
    goto LABEL_171;
  v92 = a1[62];
  v29 = 0;
  v76 = 0;
  v30 = 0;
  UserV1aFixed = SampRetrieveUserV1aFixed(a1, v105);
  if ( UserV1aFixed < 0 )
  {
LABEL_113:
    SampDeReferenceContext(a1, 0, v31);
    goto LABEL_114;
  }
  v77 = v108;
  if ( (v108 & 0x40) != 0 && (a1[5] & 0x20) == 0 )
  {
    UserV1aFixed = -1073741790;
LABEL_112:
    v29 = v77;
    goto LABEL_113;
  }
  v91 = v107;
  LOBYTE(v31) = 1;
  UserV1aFixed = SampGetUnicodeStringAttribute(a1, 1, v31, v94);
  if ( UserV1aFixed < 0 )
    goto LABEL_112;
  v32 = SampDsHandleLdapCompatibility(v84, a4, a5, a6, &v90, &v93);
  v31 = 0;
  UserV1aFixed = v32;
  if ( v32 < 0 )
    goto LABEL_112;
  v34 = 0;
  v81 = 0;
  if ( !v84 )
    goto LABEL_159;
  do
  {
    v35 = 56LL * v34;
    if ( *(_DWORD *)((char *)a4 + v35) == (_DWORD)v31 || *(_DWORD *)((char *)a4 + v35 + 4) != (_DWORD)v31 )
      goto LABEL_157;
    v36 = *((_DWORD *)a5 + 8 * *(unsigned int *)((char *)a4 + v35 + 40));
    if ( v36 > 0x6C )
    {
      if ( v36 != 109 )
      {
        switch ( v36 )
        {
          case 0x74u:
            v50 = SampWriteSidHistory(a1, v34, v99, v33, a4);
            break;
          case 0x75u:
            SampGetLargeIntegerFromAttrVal(v34, a4, v31, &v98);
            v69 = SampWriteLockoutTime(
                    (struct _SAMP_OBJECT *)a1,
                    (struct _SAMP_V1_0A_FIXED_LENGTH_USER *)v105,
                    v98,
                    v78 == v68);
            v31 = 0;
            UserV1aFixed = v69;
            if ( v69 < 0 )
              goto LABEL_112;
            v78 = 1;
            goto LABEL_157;
          case 0x7Au:
          case 0x7Cu:
          case 0x7Du:
            v50 = SampWriteNoGCLogonAttrs((void *)v35, v36, v34, v99, (unsigned int)p_DestinationString, a4);
            break;
          case 0x7Fu:
            if ( (unsigned int)SampGetBehaviorVersion((unsigned int)a1[50]) < 2 )
            {
              UserV1aFixed = -1073741637;
              goto LABEL_112;
            }
            if ( v14 )
            {
              Length = v82.Length;
              Buffer = v82.Buffer;
              if ( v82.Length )
              {
                do
                {
                  *(_BYTE *)Buffer = 0;
                  Buffer = (PWSTR)((char *)Buffer + 1);
                  --Length;
                }
                while ( Length );
                Buffer = v82.Buffer;
              }
              DSFreeAux(Buffer, 520949039);
              RtlInitUnicodeString(&v82, 0);
              v14 = 0;
            }
            v66 = DestinationString.Buffer;
            if ( DestinationString.Buffer )
            {
              v67 = DestinationString.Length;
              if ( DestinationString.Length )
              {
                do
                {
                  *(_BYTE *)v66 = 0;
                  v66 = (PWSTR)((char *)v66 + 1);
                  --v67;
                }
                while ( v67 );
                v66 = DestinationString.Buffer;
              }
              LocalFree(v66);
              RtlInitUnicodeString(&DestinationString, 0);
            }
            UserV1aFixed = SampGetNewUTF8PasswordFromAttrVal(v34, a4, &v82);
            if ( UserV1aFixed < 0 )
              goto LABEL_112;
            p_DestinationString = (struct SAMP_CALL_MAPPING *)&DestinationString;
            v50 = SampDsSetPasswordUser(a1, &v82, v105, v93);
            v14 = 1;
            break;
          case 0x84u:
            UserV1aFixed = -1073741141;
            goto LABEL_112;
          default:
            goto LABEL_154;
        }
        goto LABEL_152;
      }
      v59 = &v110;
      goto LABEL_149;
    }
    if ( v36 == 108 )
    {
      v59 = (unsigned __int16 *)&v109;
LABEL_149:
      UShortFromAttrVal = SampGetUShortFromAttrVal(v34, a4, v31, v59);
LABEL_150:
      UserV1aFixed = UShortFromAttrVal;
      if ( UShortFromAttrVal < 0 )
        goto LABEL_112;
      goto LABEL_151;
    }
    v37 = v36 - 1;
    if ( v37 )
    {
      v38 = v37 - 2;
      if ( !v38 )
      {
        UserV1aFixed = SampGetUnicodeStringFromAttrVal(v34, a4, v31, &v104);
        if ( UserV1aFixed < 0 )
          goto LABEL_112;
        v50 = SampSetUnicodeStringAttribute(a1, 3, &v104);
        goto LABEL_152;
      }
      v39 = v38 - 7;
      if ( !v39 )
      {
        UserV1aFixed = SampGetUnicodeStringFromAttrVal(v34, a4, v31, &v103);
        if ( UserV1aFixed < 0 )
          goto LABEL_112;
        UserV1aFixed = SampConvertUiListToApiList(&v103, P, 0);
        if ( UserV1aFixed < 0 )
          goto LABEL_112;
        UserV1aFixed = SampSetUnicodeStringAttribute(a1, 10, P);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
        goto LABEL_153;
      }
      v40 = v39 - 1;
      if ( !v40 )
      {
        if ( *(_WORD *)((char *)a4 + v35 + 8) == 82
          || *(_DWORD *)((char *)a4 + v35 + 24) == (_DWORD)v31
          || (v58 = *(_QWORD *)((char *)a4 + v35 + 32), *(_DWORD *)v58 == (_DWORD)v31) )
        {
          LOWORD(v100) = v31;
          *((_QWORD *)&v100 + 1) = v31;
        }
        else
        {
          LOWORD(v100) = 8 * *(_WORD *)v58;
          *((_QWORD *)&v100 + 1) = *(_QWORD *)(v58 + 8);
        }
        v50 = SampReplaceUserLogonHours(a1, &v100);
        goto LABEL_152;
      }
      v41 = v40 - 3;
      if ( !v41 )
      {
        if ( v14 )
        {
          v54 = v82.Length;
          v55 = v82.Buffer;
          if ( v82.Length )
          {
            do
            {
              *(_BYTE *)v55 = v31;
              v55 = (PWSTR)((char *)v55 + 1);
              --v54;
            }
            while ( v54 );
            v55 = v82.Buffer;
          }
          DSFreeAux(v55, 520949004);
          RtlInitUnicodeString(&v82, 0);
          LOBYTE(v31) = 0;
          v14 = 0;
        }
        v56 = DestinationString.Buffer;
        if ( DestinationString.Buffer )
        {
          v57 = DestinationString.Length;
          if ( DestinationString.Length )
          {
            do
            {
              *(_BYTE *)v56 = v31;
              v56 = (PWSTR)((char *)v56 + 1);
              --v57;
            }
            while ( v57 );
            v56 = DestinationString.Buffer;
          }
          LocalFree(v56);
          RtlInitUnicodeString(&DestinationString, 0);
        }
        UserV1aFixed = SampGetNewUnicodePasswordFromAttrVal(v34, a4, &v82);
        if ( UserV1aFixed < 0 )
          goto LABEL_112;
        p_DestinationString = (struct SAMP_CALL_MAPPING *)&DestinationString;
        v50 = SampDsSetPasswordUser(a1, &v82, v105, v93);
        goto LABEL_152;
      }
      v42 = v41 - 88;
      if ( v42 )
      {
        v43 = v42 - 1;
        if ( v43 )
        {
          v44 = v43 - 3;
          if ( v44 )
          {
            if ( v44 != 1 )
              goto LABEL_154;
            SampGetUlongFromAttrVal(v34, a4, v31, &v85);
            LOBYTE(v45) = a6;
            SampFlagsToAccountControlEx(v85, v45, &v86);
            v46 = v81;
            if ( !v80 )
              v46 = 1;
            v81 = v46;
            UserV1aFixed = SampGetUserAccountSettings(a1, v111);
            if ( UserV1aFixed < 0 )
              goto LABEL_112;
            SampUpdateComputedUserAccountControlBits(a1, v105, v111, 0);
            LOBYTE(v47) = v81;
            p_DestinationString = (struct SAMP_CALL_MAPPING *)v111;
            UserV1aFixed = SampSetUserAccountControl(a1, v86, v105, v47);
            if ( UserV1aFixed < 0 )
              goto LABEL_112;
            goto LABEL_151;
          }
          SampGetUlongFromAttrVal(v34, a4, v31, &v87);
          v48 = v87;
          if ( (v108 & 0x100000) != 0 && v107 == 521 )
          {
            v49 = 521;
            goto LABEL_60;
          }
          if ( (v108 & 0x100) != 0 && v107 == 516 )
          {
            v49 = 516;
LABEL_60:
            UserV1aFixed = v87 != v49 ? 0xC00002D0 : 0;
          }
          else
          {
            UserV1aFixed = SampAssignPrimaryGroup(a1, v87);
            v31 = 0;
          }
          if ( UserV1aFixed < 0 )
            goto LABEL_112;
          if ( v48 == v107 )
          {
            v6 = v76;
            goto LABEL_157;
          }
          v79 = 1;
          v107 = v48;
          v50 = SampReplaceUserV1aFixed(a1, v105, v31);
          v6 = v76;
          goto LABEL_152;
        }
        SampGetLargeIntegerFromAttrVal(v34, a4, v31, &v95);
        if ( (a1[5] & 0x20) == 0 && a1[62] == 500 && v95.QuadPart )
        {
          UserV1aFixed = -1073741532;
          goto LABEL_154;
        }
        v106[1] = v95.QuadPart;
LABEL_151:
        v50 = SampReplaceUserV1aFixed(a1, v105, v31);
LABEL_152:
        UserV1aFixed = v50;
LABEL_153:
        v31 = 0;
LABEL_154:
        if ( UserV1aFixed < 0 )
          goto LABEL_112;
        goto LABEL_157;
      }
      SampGetLargeIntegerFromAttrVal(v34, a4, v31, &v96);
      v97 = -1;
      if ( !v96.QuadPart )
      {
        v30 = 1;
LABEL_75:
        LOBYTE(v51) = v30;
        UShortFromAttrVal = SampComputePasswordExpired(v51, v106, v31);
        goto LABEL_150;
      }
      if ( v96.QuadPart != v97 )
      {
        UserV1aFixed = -1073741811;
        goto LABEL_112;
      }
      v30 = 0;
      UserV1aFixed = SampValidatePwdSettingAttempt(a1, 0, v108, &GUID_CONTROL_UnexpirePassword);
      if ( UserV1aFixed < 0 )
        goto LABEL_112;
      HasNeverTime = (_QWORD *)SampGetHasNeverTime();
      v51 = v106[0];
      v31 = 0;
      if ( *HasNeverTime == v106[0] )
        goto LABEL_75;
    }
    else
    {
      UserV1aFixed = SampGetUnicodeStringFromAttrVal(v34, a4, v31, &String2);
      if ( UserV1aFixed < 0 )
        goto LABEL_112;
      UserV1aFixed = SampChangeUserAccountName(a1, &String2, v108, &String1);
      if ( UserV1aFixed < 0 )
      {
        String1.Buffer = 0;
        goto LABEL_112;
      }
      v6 = RtlCompareUnicodeString(&String1, &String2, 1u) != 0;
      v31 = 0;
      v76 = v6;
    }
LABEL_157:
    ++v34;
  }
  while ( v34 < v84 );
  v76 = v6;
  if ( UserV1aFixed < 0 )
    goto LABEL_112;
LABEL_159:
  v70 = v107;
  if ( v107 != v91 )
  {
    LOBYTE(v33) = v79;
    UserV1aFixed = SampDsMaintainPrimaryGroupIdChange(a1, v107, v91, v33);
    if ( UserV1aFixed < 0 )
      goto LABEL_112;
  }
  if ( (a1[5] & 0xC) == 0 )
  {
    UserV1aFixed = SampReplaceUserV1aFixed(a1, v105, v31);
    if ( UserV1aFixed < 0 )
      goto LABEL_112;
  }
  if ( (v108 & 0x1C0) == 0 && (v30 || v78) )
    *((_BYTE *)a1 + 28) |= 0x20u;
  LOBYTE(v70) = 1;
  v29 = v77;
  UserV1aFixed = SampDeReferenceContext(a1, v70, v31);
LABEL_114:
  if ( UserV1aFixed >= 0 )
  {
    if ( (unsigned __int8)SampGetSuccessAccountAuditingEnabled() != 1 )
      goto LABEL_120;
    if ( v76 )
      SampAuditAccountNameChange(a1, &String2, &String1);
    v60 = v108;
    if ( (((unsigned __int8)v29 ^ (unsigned __int8)v108) & 1) != 0 )
    {
      SampAuditAccountEnableDisableChange(a1, v108, v29, v94);
LABEL_120:
      v60 = v108;
    }
    v61 = v30 != 0;
    if ( v78 )
      v61 |= 2u;
    if ( v82.Length )
      v61 |= 4u;
    if ( v61 )
    {
      LOBYTE(p_DestinationString) = 1;
      p_String2 = (UNICODE_STRING *)v94;
      if ( v76 )
        p_String2 = &String2;
      v63 = v61 | 8;
      if ( (v60 & 0x1C0) == 0 )
        v63 = v61;
      SampPasswordChangeNotify(v63, p_String2, v92, &DestinationString, p_DestinationString);
    }
  }
LABEL_171:
  SampDecrementActiveThreads();
  SampFreeUnicodeString(&String1);
  SampFreeUnicodeString(v94);
  if ( v82.Length )
  {
    v71 = v82.Length;
    v72 = v82.Buffer;
    do
    {
      *(_BYTE *)v72 = 0;
      v72 = (PWSTR)((char *)v72 + 1);
      --v71;
    }
    while ( v71 );
  }
  if ( v14 )
    DSFreeAux(v82.Buffer, 520949384);
  v73 = DestinationString.Buffer;
  if ( DestinationString.Buffer )
  {
    v74 = DestinationString.Length;
    if ( DestinationString.Length )
    {
      do
      {
        *(_BYTE *)v73 = 0;
        v73 = (PWSTR)((char *)v73 + 1);
        --v74;
      }
      while ( v74 );
      v73 = DestinationString.Buffer;
    }
    LocalFree(v73);
    RtlInitUnicodeString(&DestinationString, 0);
  }
  return (unsigned int)UserV1aFixed;
}

```

## disassembly

```asm
0x180405b2c  mov     [rsp-8+arg_10], rbx
0x180405b31  push    rbp
0x180405b32  push    rsi
0x180405b33  push    rdi
0x180405b34  push    r12
0x180405b36  push    r13
0x180405b38  push    r14
0x180405b3a  push    r15
0x180405b3c  lea     rbp, [rsp-0C0h]
0x180405b44  sub     rsp, 1C0h
0x180405b4b  mov     rax, cs:__security_cookie
0x180405b52  xor     rax, rsp
0x180405b55  mov     [rbp+0F0h+var_40], rax
0x180405b5c  xor     esi, esi
0x180405b5e  mov     [rbp+0F0h+var_118], rdx
0x180405b62  xorps   xmm0, xmm0
0x180405b65  mov     [rbp+0F0h+var_160], esi
0x180405b68  mov     ebx, r8d
0x180405b6b  mov     [rsp+1F0h+var_17C], esi
0x180405b6f  xorps   xmm1, xmm1
0x180405b72  mov     [rsp+1F0h+var_180], ebx
0x180405b76  mov     rdi, rcx
0x180405b79  mov     [rsp+1F0h+var_178], esi
0x180405b7d  lea     r8d, [rsi+50h]; Size
0x180405b81  mov     [rsp+1F0h+var_174], esi
0x180405b85  xor     edx, edx; Val
0x180405b87  mov     qword ptr [rbp+0F0h+String1.Length], rsi
0x180405b8b  lea     rcx, [rbp+0F0h+var_C0]; void *
0x180405b8f  mov     [rbp+0F0h+String1.Buffer], rsi
0x180405b93  mov     r14, r9
0x180405b96  mov     [rbp+0F0h+var_148], rsi
0x180405b9a  movups  xmmword ptr [rbp+0F0h+var_E0.Length], xmm0
0x180405b9e  mov     [rbp+0F0h+var_140], rsi
0x180405ba2  movups  xmmword ptr [rbp+0F0h+P], xmm1
0x180405ba6  mov     [rsp+1F0h+var_1A5], sil
0x180405bab  movups  xmmword ptr [rbp+0F0h+String2.Length], xmm0
0x180405baf  mov     [rsp+1F0h+var_1A7], sil
0x180405bb4  movups  xmmword ptr [rbp+0F0h+var_D0.Length], xmm0
0x180405bb8  mov     [rsp+1F0h+var_1A8], sil
0x180405bbd  movups  xmmword ptr [rsp+1F0h+var_1A0.Length], xmm0
0x180405bc2  mov     qword ptr [rbp+0F0h+var_130], rsi
0x180405bc6  movups  xmmword ptr [rsp+1F0h+DestinationString.Length], xmm1
0x180405bcb  mov     qword ptr [rbp+0F0h+var_138], rsi
0x180405bcf  movups  [rbp+0F0h+var_110], xmm0
0x180405bd3  mov     qword ptr [rbp+0F0h+var_120], rsi
0x180405bd7  mov     [rbp+0F0h+var_15C], esi
0x180405bda  mov     [rbp+0F0h+var_150], rsi
0x180405bde  movups  [rbp+0F0h+var_70], xmm0
0x180405be5  movups  [rbp+0F0h+var_60], xmm0
0x180405bec  movups  [rbp+0F0h+var_50], xmm0
0x180405bf3  call    memset_0
0x180405bf8  lea     ecx, [rsi+10h]
0x180405bfb  lea     rax, [rsp+1F0h+var_1A0]
0x180405c00  lea     r15d, [rsi+1]
0x180405c04  mov     [rax], sil
0x180405c07  add     rax, r15
0x180405c0a  sub     rcx, r15
0x180405c0d  jnz     short loc_180405C04
0x180405c0f  xor     edx, edx; SourceString
0x180405c11  lea     rcx, [rsp+1F0h+DestinationString]; DestinationString
0x180405c16  call    cs:__imp_RtlInitUnicodeString
0x180405c1c  call    cs:__imp_SampIncrementActiveThreads
0x180405c22  test    eax, eax
0x180405c24  js      loc_180406640
0x180405c2a  mov     [rsp+1F0h+var_1A6], sil
0x180405c2f  mov     edx, esi
0x180405c31  mov     r13b, sil
0x180405c34  mov     r9d, esi
0x180405c37  test    ebx, ebx
0x180405c39  jz      loc_180405CC8
0x180405c3f  mov     r13, [rbp+0F0h+arg_20]
0x180405c46  mov     r8, rsi
0x180405c49  imul    rax, r8, 38h ; '8'
0x180405c4d  cmp     [rax+r14], esi
0x180405c51  jz      short loc_180405CBA
0x180405c53  cmp     [rax+r14+4], esi
0x180405c58  jnz     short loc_180405CBA
0x180405c5a  mov     eax, [rax+r14+28h]
0x180405c5f  shl     rax, 5
0x180405c63  mov     ecx, [rax+r13]
0x180405c67  cmp     ecx, 67h ; 'g'
0x180405c6a  ja      short loc_180405C8E
0x180405c6c  jz      short loc_180405CB7
0x180405c6e  sub     ecx, r15d
0x180405c71  jz      short loc_180405CB7
0x180405c73  sub     ecx, 2
0x180405c76  jz      short loc_180405CB7
0x180405c78  sub     ecx, 7
0x180405c7b  jz      short loc_180405CB7
0x180405c7d  sub     ecx, r15d
0x180405c80  jz      short loc_180405CB7
0x180405c82  sub     ecx, 3
0x180405c85  jz      short loc_180405CA7
0x180405c87  cmp     ecx, 58h ; 'X'
0x180405c8a  jz      short loc_180405CA7
0x180405c8c  jmp     short loc_180405CBA
0x180405c8e  sub     ecx, 6Ah ; 'j'
0x180405c91  jz      short loc_180405CB2
0x180405c93  sub     ecx, r15d
0x180405c96  jz      short loc_180405CB7
0x180405c98  sub     ecx, r15d
0x180405c9b  jz      short loc_180405CAD
0x180405c9d  sub     ecx, r15d
0x180405ca0  jz      short loc_180405CAD
0x180405ca2  cmp     ecx, 12h
0x180405ca5  jnz     short loc_180405CBA
0x180405ca7  bts     edx, 7
0x180405cab  jmp     short loc_180405CBA
0x180405cad  or      edx, 4
0x180405cb0  jmp     short loc_180405CBA
0x180405cb2  mov     [rsp+1F0h+var_1A6], r15b
0x180405cb7  or      edx, 20h
0x180405cba  add     r9d, r15d
0x180405cbd  add     r8, r15
0x180405cc0  cmp     r9d, ebx
0x180405cc3  jb      short loc_180405C49
0x180405cc5  mov     r13b, sil
0x180405cc8  lea     r9, [rbp+0F0h+var_160]
0x180405ccc  mov     r8d, 4
0x180405cd2  mov     rcx, rdi
0x180405cd5  call    cs:__imp_SampLookupContext
0x180405cdb  mov     ebx, eax
0x180405cdd  test    eax, eax
0x180405cdf  js      loc_1804065B8
0x180405ce5  mov     eax, [rdi+0F8h]
0x180405ceb  lea     rdx, [rbp+0F0h+var_C0]
0x180405cef  mov     rcx, rdi
0x180405cf2  mov     [rbp+0F0h+var_154], eax
0x180405cf5  mov     r15d, esi
0x180405cf8  mov     [rsp+1F0h+var_1B0], sil
0x180405cfd  mov     r12b, sil
0x180405d00  call    cs:__imp_SampRetrieveUserV1aFixed
0x180405d06  mov     ebx, eax
0x180405d08  test    eax, eax
0x180405d0a  js      loc_1804062BC
0x180405d10  mov     r15d, [rbp+0F0h+var_88]
0x180405d14  mov     [rsp+1F0h+var_1AC], r15d
0x180405d19  test    r15b, 40h
0x180405d1d  jz      short loc_180405D2F
0x180405d1f  test    byte ptr [rdi+14h], 20h
0x180405d23  jnz     short loc_180405D2F
0x180405d25  mov     ebx, 0C0000022h
0x180405d2a  jmp     loc_1804062B7
0x180405d2f  mov     eax, [rbp+0F0h+var_8C]
0x180405d32  lea     r9, [rbp+0F0h+var_148]
0x180405d36  mov     [rbp+0F0h+var_158], eax
0x180405d39  mov     rcx, rdi
0x180405d3c  mov     eax, 1
0x180405d41  mov     r8b, al
0x180405d44  mov     edx, eax
0x180405d46  call    cs:__imp_SampGetUnicodeStringAttribute
0x180405d4c  mov     ebx, eax
0x180405d4e  test    eax, eax
0x180405d50  js      loc_1804062B7
0x180405d56  mov     r9b, [rbp+0F0h+arg_28]; unsigned __int8
0x180405d5d  lea     rax, [rbp+0F0h+var_150]
0x180405d61  mov     r8, [rbp+0F0h+arg_20]; struct SAMP_ATTRIBUTE_MAPPING *
0x180405d68  mov     rdx, r14; struct SAMP_CALL_MAPPING *
0x180405d6b  mov     ecx, [rsp+1F0h+var_180]; unsigned int
0x180405d6f  mov     [rsp+1F0h+var_1C8], rax; unsigned int **
0x180405d74  lea     rax, [rbp+0F0h+var_15C]
0x180405d78  mov     [rsp+1F0h+var_1D0], rax; unsigned int
0x180405d7d  call    ?SampDsHandleLdapCompatibility@@YAJKPEAUSAMP_CALL_MAPPING@@PEAUSAMP_ATTRIBUTE_MAPPING@@EPEAKPEAPEAK@Z; SampDsHandleLdapCompatibility(ulong,SAMP_CALL_MAPPING *,SAMP_ATTRIBUTE_MAPPING *,uchar,ulong *,ulong * *)
0x180405d82  xor     r8d, r8d; unsigned __int8
0x180405d85  mov     ebx, eax
0x180405d87  test    eax, eax
0x180405d89  js      loc_1804062B7
0x180405d8f  mov     r15d, r8d
0x180405d92  mov     byte ptr [rsp+1F0h+var_1A4], r8b
0x180405d97  cmp     [rsp+1F0h+var_180], r8d
0x180405d9c  jbe     loc_180406519
0x180405da2  mov     eax, r15d
0x180405da5  imul    rcx, rax, 38h ; '8'; void *
0x180405da9  cmp     [rcx+r14], r8d
0x180405dad  jz      loc_1804064FC
0x180405db3  cmp     [rcx+r14+4], r8d
0x180405db8  jnz     loc_1804064FC
0x180405dbe  mov     eax, [rcx+r14+28h]
0x180405dc3  mov     rdx, [rbp+0F0h+arg_20]
0x180405dca  shl     rax, 5
0x180405dce  mov     edx, [rax+rdx]; unsigned int
0x180405dd1  cmp     edx, 6Ch ; 'l'
0x180405dd4  ja      loc_180406266
0x180405dda  jz      loc_18040625D
0x180405de0  sub     edx, 1
0x180405de3  jz      loc_1804061FF
0x180405de9  sub     edx, 2
0x180405dec  jz      loc_1804061CF
0x180405df2  sub     edx, 7
0x180405df5  jz      loc_180406169
0x180405dfb  sub     edx, 1
0x180405dfe  jz      loc_18040611B
0x180405e04  sub     edx, 3
0x180405e07  jz      loc_18040605A
0x180405e0d  sub     edx, 58h ; 'X'
0x180405e10  jz      loc_180405FE0
0x180405e16  sub     edx, 1
0x180405e19  jz      loc_180405FA3
0x180405e1f  sub     edx, 3
0x180405e22  jz      loc_180405F11
0x180405e28  cmp     edx, 1
0x180405e2b  jnz     loc_1804064ED
0x180405e31  lea     r9, [rsp+1F0h+var_17C]; unsigned int *
0x180405e36  mov     rdx, r14; struct SAMP_CALL_MAPPING *
0x180405e39  mov     ecx, r15d; unsigned int
0x180405e3c  call    ?SampGetUlongFromAttrVal@@YAXKPEAUSAMP_CALL_MAPPING@@EPEAK@Z; SampGetUlongFromAttrVal(ulong,SAMP_CALL_MAPPING *,uchar,ulong *)
0x180405e41  mov     ecx, [rsp+1F0h+var_17C]
0x180405e45  lea     r8, [rsp+1F0h+var_178]
0x180405e4a  mov     dl, [rbp+0F0h+arg_28]
0x180405e50  call    cs:__imp_SampFlagsToAccountControlEx
0x180405e56  mov     eax, [rsp+1F0h+var_1A4]
0x180405e5a  lea     rdx, [rbp+0F0h+var_70]
0x180405e61  cmp     [rsp+1F0h+var_1A6], 0
0x180405e66  mov     ecx, 1
0x180405e6b  movzx   eax, al
0x180405e6e  cmovz   eax, ecx
0x180405e71  mov     rcx, rdi
0x180405e74  mov     [rsp+1F0h+var_1A4], eax
0x180405e78  call    cs:__imp_SampGetUserAccountSettings
0x180405e7e  mov     ebx, eax
0x180405e80  test    eax, eax
0x180405e82  js      loc_1804062B5
0x180405e88  xor     r9d, r9d
0x180405e8b  lea     r8, [rbp+0F0h+var_70]
0x180405e92  lea     rdx, [rbp+0F0h+var_C0]
0x180405e96  mov     rcx, rdi
0x180405e99  call    cs:__imp_SampUpdateComputedUserAccountControlBits
0x180405e9f  mov     r9b, byte ptr [rsp+1F0h+var_1A4]
0x180405ea4  lea     rax, [rsp+1F0h+var_1A7]
0x180405ea9  mov     edx, [rsp+1F0h+var_178]
0x180405ead  lea     r8, [rbp+0F0h+var_C0]
0x180405eb1  mov     [rsp+1F0h+var_1B8], rax
0x180405eb6  mov     rcx, rdi
0x180405eb9  lea     rax, [rsp+1F0h+var_1A5]
0x180405ebe  mov     [rsp+1F0h+var_1C0], rax
0x180405ec3  lea     rax, [rsp+1F0h+var_1A8]
0x180405ec8  mov     [rsp+1F0h+var_1C8], rax
0x180405ecd  lea     rax, [rbp+0F0h+var_70]
0x180405ed4  mov     [rsp+1F0h+var_1D0], rax
0x180405ed9  call    cs:__imp_SampSetUserAccountControl
0x180405edf  mov     ebx, eax
0x180405ee1  test    eax, eax
0x180405ee3  js      loc_1804062B5
0x180405ee9  cmp     [rsp+1F0h+var_1A5], 0
0x180405eee  jz      loc_1804064DB
0x180405ef4  movzx   eax, byte ptr [rsp+1F0h+var_1A4]
0x180405ef9  mov     ecx, 1
0x180405efe  test    [rbp+0F0h+var_88], 100100h
0x180405f05  cmovnz  eax, ecx
0x180405f08  mov     byte ptr [rsp+1F0h+var_1A4], al
0x180405f0c  jmp     loc_1804064DB
0x180405f11  lea     r9, [rsp+1F0h+var_174]; unsigned int *
0x180405f16  mov     rdx, r14; struct SAMP_CALL_MAPPING *
0x180405f19  mov     ecx, r15d; unsigned int
0x180405f1c  call    ?SampGetUlongFromAttrVal@@YAXKPEAUSAMP_CALL_MAPPING@@EPEAK@Z; SampGetUlongFromAttrVal(ulong,SAMP_CALL_MAPPING *,uchar,ulong *)
0x180405f21  test    [rbp+0F0h+var_88], 100000h
0x180405f28  mov     esi, [rsp+1F0h+var_174]
0x180405f2c  jz      short loc_180405F3E
0x180405f2e  cmp     [rbp+0F0h+var_8C], 209h
0x180405f35  jnz     short loc_180405F3E
0x180405f37  mov     eax, 209h
0x180405f3c  jmp     short loc_180405F55
0x180405f3e  test    [rbp+0F0h+var_88], 100h
0x180405f45  jz      short loc_180405F63
0x180405f47  cmp     [rbp+0F0h+var_8C], 204h
0x180405f4e  jnz     short loc_180405F63
0x180405f50  mov     eax, 204h
0x180405f55  sub     eax, esi
0x180405f57  neg     eax
0x180405f59  sbb     ebx, ebx
0x180405f5b  and     ebx, 0C00002D0h
0x180405f61  jmp     short loc_180405F73
0x180405f63  mov     edx, esi
0x180405f65  mov     rcx, rdi
0x180405f68  call    cs:__imp_SampAssignPrimaryGroup
0x180405f6e  mov     ebx, eax
0x180405f70  xor     r8d, r8d
0x180405f73  test    ebx, ebx
0x180405f75  js      loc_1804062B5
0x180405f7b  cmp     esi, [rbp+0F0h+var_8C]
0x180405f7e  jz      loc_1804064F7
0x180405f84  lea     rdx, [rbp+0F0h+var_C0]
0x180405f88  mov     [rsp+1F0h+var_1A7], 1
0x180405f8d  mov     rcx, rdi
0x180405f90  mov     [rbp+0F0h+var_8C], esi
0x180405f93  call    cs:__imp_SampReplaceUserV1aFixed
0x180405f99  mov     sil, [rsp+1F0h+var_1B0]
0x180405f9e  jmp     loc_1804064E8
0x180405fa3  lea     r9, [rbp+0F0h+var_138]; union _LARGE_INTEGER *
0x180405fa7  mov     rdx, r14; struct SAMP_CALL_MAPPING *
0x180405faa  mov     ecx, r15d; unsigned int
0x180405fad  call    ?SampGetLargeIntegerFromAttrVal@@YAXKPEAUSAMP_CALL_MAPPING@@EPEAT_LARGE_INTEGER@@@Z; SampGetLargeIntegerFromAttrVal(ulong,SAMP_CALL_MAPPING *,uchar,_LARGE_INTEGER *)
0x180405fb2  test    byte ptr [rdi+14h], 20h
0x180405fb6  mov     rax, qword ptr [rbp+0F0h+var_138]
0x180405fba  jnz     short loc_180405FD7
0x180405fbc  cmp     dword ptr [rdi+0F8h], 1F4h
0x180405fc6  jnz     short loc_180405FD7
0x180405fc8  test    rax, rax
0x180405fcb  jz      short loc_180405FD7
0x180405fcd  mov     ebx, 0C0000124h
  ... truncated ...
```
