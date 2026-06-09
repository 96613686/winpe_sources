# RemoveAccessAllowedObjectACEFromSecurityDescriptor

- ea: `0x180122490`
- end: `0x180122ddc`
- name: `RemoveAccessAllowedObjectACEFromSecurityDescriptor`
- size: `2380`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1803cd7c4`
- `0x1803d329c`

## callees

- `0x180006330`
- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x180021a97`
- `0x180030af8`
- `0x18011db10`
- `0x180120480`
- `0x180120ecc`
- `0x180122490`
- `0x180123ad4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180122944`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180122944`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1801227ad`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1801227ad`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180122a76`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180122a76`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1801228dd`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1801228dd`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x180122965`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x180122965`
- `api-ms-win-security-base-l1-1-0!FindFirstFreeAce` at `0x180122b7c`
- `api-ms-win-security-base-l1-1-0!FindFirstFreeAce` at `0x180122b7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012287e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180122a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180122b49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012287e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180122a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180122b49`

## pseudocode

```c
__int64 __fastcall RemoveAccessAllowedObjectACEFromSecurityDescriptor(
        __int64 a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        void *Buf2,
        __int64 a6,
        _QWORD *a7)
{
  DWORD v7; // r14d
  __int64 v10; // rbx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  void *v14; // r12
  int v15; // edi
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // r9
  BOOL v20; // ebx
  int v21; // eax
  unsigned int SecurityDescriptorDacl; // r15d
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // r8
  __int64 v28; // r9
  BOOL v29; // ebx
  unsigned int AbsoluteSDHelper; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rbx
  _DWORD *v45; // rbx
  bool v46; // zf
  int v47; // eax
  BOOL v48; // eax
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r9
  __int64 v53; // r8
  __int64 v54; // r9
  BOOL v55; // r14d
  __int64 v56; // rbx
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 v61; // r8
  __int64 v62; // r9
  BOOL v63; // r14d
  __int64 v64; // rbx
  __int64 v65; // r14
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 v70; // r8
  __int64 v71; // r9
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 v76; // r8
  __int64 v77; // r9
  int v78; // r8d
  int v79; // r9d
  int v81; // [rsp+40h] [rbp-49h]
  int v82; // [rsp+50h] [rbp-39h]
  PACL pDacl; // [rsp+68h] [rbp-21h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+70h] [rbp-19h] BYREF
  __int64 v85; // [rsp+78h] [rbp-11h] BYREF
  LPVOID pAce; // [rsp+80h] [rbp-9h] BYREF
  LPVOID v87; // [rsp+88h] [rbp-1h] BYREF
  WINBOOL bDaclPresent; // [rsp+E0h] [rbp+57h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+F0h] [rbp+67h] BYREF

  v7 = 0;
  pDacl = 0;
  a6 = 0;
  v85 = 0;
  v10 = a1;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pSecurityDescriptor = 0;
  *a7 = 0;
  v11 = THStateCheckForTraceOverride(a1, a2);
  v14 = Buf2;
  v15 = 1;
  if ( v11
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v13, v12)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v13, v12, v16, v17)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
  {
    v20 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v13, v12)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v13, v12, v18, v19)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
    if ( (unsigned int)THStateCheckForTraceOverride(v13, v12)
      || (v46 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v21 = 0, !v46) )
    {
      v21 = 1;
    }
    WPP_SF__sid_D_guid__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52565551, v21, v20, 60, v81, a3, v82, (__int64)v14);
    v10 = a1;
  }
  if ( *(__int16 *)(a2 + 2) >= 0 )
  {
    SecurityDescriptorDacl = 0;
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v24, v23)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v24, v23)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v24, v23, v25, v26)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v29 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v24, v23)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v24, v23, v27, v28)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v24, v23)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v15 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565558,
        2,
        3,
        v15,
        v29,
        61,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
LABEL_156:
    v65 = a1;
    v10 = a6;
    goto LABEL_157;
  }
  AbsoluteSDHelper = MakeAbsoluteSDHelper(v10, a2, &pSecurityDescriptor);
  LODWORD(v10) = 0;
  SecurityDescriptorDacl = AbsoluteSDHelper;
  if ( !AbsoluteSDHelper )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v32, v31)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v32, v31)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v32, v31, v33, v34)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v32, v31)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v32, v31, v35, v36)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        LODWORD(v10) = 1;
      }
      if ( !(unsigned int)THStateCheckForTraceOverride(v32, v31)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v15 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565569,
        2,
        3,
        v15,
        v10,
        62,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_156;
  }
  SecurityDescriptorDacl = GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted);
  if ( !SecurityDescriptorDacl )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v39, v38)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v39, v38)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v39, v38, v40, v41)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v39, v38)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v39, v38, v42, v43)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        v7 = 1;
      }
      if ( !(unsigned int)THStateCheckForTraceOverride(v39, v38)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v15 = 0;
      }
      v44 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      GetLastError();
      WPP_SF__ATTRTYP_LOG_(v44, 52565581, 2, 3, v15, v7, 63, (__int64)&WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_156;
  }
  while ( 1 )
  {
    if ( v7 >= pDacl->AceCount )
    {
      SecurityDescriptorDacl = 0;
      if ( (unsigned int)THStateCheckForTraceOverride(pDacl, v37)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v73, v72)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v73, v72, v74, v75)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 3)) )
      {
        if ( gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v73, v72)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v73, v72, v76, v77)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 3)) )
        {
          LODWORD(v10) = 1;
        }
        if ( !(unsigned int)THStateCheckForTraceOverride(v73, v72)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 3) )
        {
          v15 = 0;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52565637,
          5,
          3,
          v15,
          v10,
          64,
          &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
      }
      goto LABEL_156;
    }
    pAce = 0;
    if ( GetAce(pDacl, v7, &pAce) )
    {
      v45 = pAce;
      if ( *(_BYTE *)pAce != 5 )
        goto LABEL_89;
      if ( v14 )
      {
        if ( (*((_BYTE *)pAce + 8) & 1) == 0 )
          goto LABEL_89;
        v46 = memcmp_0((char *)pAce + 12, v14, 0x10u) == 0;
      }
      else
      {
        v46 = (*((_BYTE *)pAce + 8) & 1) == 0;
      }
      if ( !v46 || (v47 = v45[2], (v47 & 2) != 0) )
      {
LABEL_89:
        LODWORD(v10) = 0;
        goto LABEL_90;
      }
      v48 = EqualSid(&v45[4 * (v47 & 1) + 3], a3);
      v10 = 0;
      if ( v48 )
      {
        if ( *((_DWORD *)pAce + 1) == 32 )
          break;
      }
    }
LABEL_90:
    ++v7;
  }
  SecurityDescriptorDacl = DeleteAce(pDacl, v7);
  if ( !SecurityDescriptorDacl )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v50, v49)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v50, v49)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v50, v49, v51, v52)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v55 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v50, v49)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v50, v49, v53, v54)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v50, v49)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v15 = 0;
      }
      v56 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      GetLastError();
      WPP_SF__ATTRTYP_LOG_(v56, 52565644, 2, 3, v15, v55, 65, (__int64)&WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_156;
  }
  SecurityDescriptorDacl = SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0);
  if ( !SecurityDescriptorDacl )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v58, v57)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v58, v57)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v58, v57, v59, v60)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v63 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v58, v57)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v58, v57, v61, v62)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v58, v57)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v15 = 0;
      }
      v64 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      GetLastError();
      WPP_SF__ATTRTYP_LOG_(v64, 52565658, 2, 3, v15, v63, 66, (__int64)&WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_156;
  }
  v87 = 0;
  if ( FindFirstFreeAce(pDacl, &v87) && v87 )
    pDacl->AclSize = (_WORD)v87 - (_WORD)pDacl;
  v65 = a1;
  SecurityDescriptorDacl = MakeSelfRelativeSDHelper(a1, pSecurityDescriptor, &v85);
  if ( SecurityDescriptorDacl )
  {
    *a7 = v85;
  }
  else
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v67, v66)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v67, v66)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v67, v66, v68, v69)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v67, v66)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v67, v66, v70, v71)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        LODWORD(v10) = 1;
      }
      if ( !(unsigned int)THStateCheckForTraceOverride(v67, v66)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v15 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565674,
        2,
        3,
        v15,
        v10,
        67,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    v10 = v85;
  }
LABEL_157:
  FreeAbsoluteSDHelper(v65, pSecurityDescriptor);
  if ( v10 )
    THFreeAux(v65, v10, v78, v79, 52565684);
  return SecurityDescriptorDacl;
}

```

## disassembly

```asm
0x180122490  mov     rax, rsp
0x180122493  mov     [rax+18h], rbx
0x180122497  mov     [rax+20h], r9d
0x18012249b  mov     [rax+8], rcx
0x18012249f  push    rbp
0x1801224a0  push    rsi
0x1801224a1  push    rdi
0x1801224a2  push    r12
0x1801224a4  push    r13
0x1801224a6  push    r14
0x1801224a8  push    r15
0x1801224aa  lea     rbp, [rax-47h]
0x1801224ae  sub     rsp, 90h
0x1801224b5  xor     r14d, r14d
0x1801224b8  mov     r13, r8
0x1801224bb  mov     eax, r14d
0x1801224be  mov     [rbp+3Fh+pDacl], r14
0x1801224c2  mov     [rbp+3Fh+arg_28], rax
0x1801224c6  mov     rsi, rdx
0x1801224c9  mov     [rbp+3Fh+var_50], rax
0x1801224cd  mov     rbx, rcx
0x1801224d0  mov     rax, [rbp+3Fh+arg_30]
0x1801224d4  mov     [rbp+3Fh+bDaclPresent], r14d
0x1801224d8  mov     [rbp+3Fh+bDaclDefaulted], r14d
0x1801224dc  mov     [rbp+3Fh+pSecurityDescriptor], r14
0x1801224e0  mov     [rax], r14
0x1801224e3  call    THStateCheckForTraceOverride
0x1801224e8  mov     r12, [rbp+3Fh+Buf2]
0x1801224ec  lea     edi, [r14+1]
0x1801224f0  lea     r15d, [r14+3]
0x1801224f4  test    eax, eax
0x1801224f6  jnz     short loc_180122542
0x1801224f8  mov     r8d, r15d
0x1801224fb  lea     edx, [rdi+3]
0x1801224fe  xor     ecx, ecx
0x180122500  call    CheckWPPLevelFlagsEnabledForProvider
0x180122505  test    eax, eax
0x180122507  jnz     short loc_180122542
0x180122509  mov     eax, cs:gfTraceToSecondProvider
0x18012250f  test    eax, eax
0x180122511  jz      loc_1801225C9
0x180122517  call    THStateCheckForTraceOverride
0x18012251c  test    eax, eax
0x18012251e  jnz     short loc_180122542
0x180122520  call    ThStateCheckIfTraceToSecondProvier
0x180122525  test    eax, eax
0x180122527  jz      loc_1801225C9
0x18012252d  mov     r8d, r15d
0x180122530  lea     edx, [rdi+3]
0x180122533  mov     ecx, edi
0x180122535  call    CheckWPPLevelFlagsEnabledForProvider
0x18012253a  test    eax, eax
0x18012253c  jz      loc_1801225C9
0x180122542  mov     eax, cs:gfTraceToSecondProvider
0x180122548  test    eax, eax
0x18012254a  jz      short loc_180122575
0x18012254c  call    THStateCheckForTraceOverride
0x180122551  test    eax, eax
0x180122553  jnz     short loc_180122571
0x180122555  call    ThStateCheckIfTraceToSecondProvier
0x18012255a  test    eax, eax
0x18012255c  jz      short loc_180122575
0x18012255e  mov     r8d, r15d
0x180122561  mov     edx, 4
0x180122566  mov     ecx, edi
0x180122568  call    CheckWPPLevelFlagsEnabledForProvider
0x18012256d  test    eax, eax
0x18012256f  jz      short loc_180122575
0x180122571  mov     ebx, edi
0x180122573  jmp     short loc_180122578
0x180122575  mov     ebx, r14d
0x180122578  call    THStateCheckForTraceOverride
0x18012257d  test    eax, eax
0x18012257f  jnz     short loc_180122595
0x180122581  mov     r8d, r15d
0x180122584  lea     edx, [rax+4]
0x180122587  xor     ecx, ecx
0x180122589  call    CheckWPPLevelFlagsEnabledForProvider
0x18012258e  test    eax, eax
0x180122590  mov     eax, r14d
0x180122593  jz      short loc_180122597
0x180122595  mov     eax, edi
0x180122597  mov     rcx, cs:WPP_GLOBAL_Control
0x18012259e  mov     edx, 322162Fh; int
0x1801225a3  mov     qword ptr [rsp+0C0h+var_78+8], r12; __int64
0x1801225a8  mov     qword ptr [rsp+0C0h+var_88+8], r13; pSid
0x1801225ad  mov     [rsp+0C0h+var_90], 3Ch ; '<'; __int16
0x1801225b4  mov     rcx, [rcx+10h]; int
0x1801225b8  mov     [rsp+0C0h+var_98], ebx; int
0x1801225bc  mov     [rsp+0C0h+var_A0], eax; int
0x1801225c0  call    WPP_SF__sid_D_guid__guid_
0x1801225c5  mov     rbx, [rbp+3Fh+arg_0]
0x1801225c9  cmp     [rsi+2], r14w
0x1801225ce  jl      loc_1801226B0
0x1801225d4  mov     r15d, r14d
0x1801225d7  mov     esi, 2
0x1801225dc  mov     ecx, esi
0x1801225de  call    IncrementWPPPerfCountersForLevel
0x1801225e3  test    eax, eax
0x1801225e5  jnz     short loc_18012263E
0x1801225e7  call    THStateCheckForTraceOverride
0x1801225ec  lea     r12d, [rsi+1]
0x1801225f0  test    eax, eax
0x1801225f2  jnz     short loc_180122644
0x1801225f4  mov     r8d, r12d
0x1801225f7  mov     edx, esi
0x1801225f9  xor     ecx, ecx
0x1801225fb  call    CheckWPPLevelFlagsEnabledForProvider
0x180122600  test    eax, eax
0x180122602  jnz     short loc_180122644
0x180122604  mov     eax, cs:gfTraceToSecondProvider
0x18012260a  test    eax, eax
0x18012260c  jz      loc_180122D92
0x180122612  call    THStateCheckForTraceOverride
0x180122617  test    eax, eax
0x180122619  jnz     short loc_180122644
0x18012261b  call    ThStateCheckIfTraceToSecondProvier
0x180122620  test    eax, eax
0x180122622  jz      loc_180122D92
0x180122628  mov     r8d, r12d
0x18012262b  mov     edx, esi
0x18012262d  mov     ecx, edi
0x18012262f  call    CheckWPPLevelFlagsEnabledForProvider
0x180122634  test    eax, eax
0x180122636  jz      loc_180122D92
0x18012263c  jmp     short loc_180122644
0x18012263e  mov     r12d, 3
0x180122644  mov     eax, cs:gfTraceToSecondProvider
0x18012264a  test    eax, eax
0x18012264c  jz      short loc_180122674
0x18012264e  call    THStateCheckForTraceOverride
0x180122653  test    eax, eax
0x180122655  jnz     short loc_180122670
0x180122657  call    ThStateCheckIfTraceToSecondProvier
0x18012265c  test    eax, eax
0x18012265e  jz      short loc_180122674
0x180122660  mov     r8d, r12d
0x180122663  mov     edx, esi
0x180122665  mov     ecx, edi
0x180122667  call    CheckWPPLevelFlagsEnabledForProvider
0x18012266c  test    eax, eax
0x18012266e  jz      short loc_180122674
0x180122670  mov     ebx, edi
0x180122672  jmp     short loc_180122677
0x180122674  mov     ebx, r14d
0x180122677  call    THStateCheckForTraceOverride
0x18012267c  test    eax, eax
0x18012267e  jnz     short loc_180122693
0x180122680  mov     r8d, r12d
0x180122683  mov     edx, esi
0x180122685  xor     ecx, ecx
0x180122687  call    CheckWPPLevelFlagsEnabledForProvider
0x18012268c  test    eax, eax
0x18012268e  jnz     short loc_180122693
0x180122690  mov     edi, r14d
0x180122693  lea     rax, WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids
0x18012269a  mov     edx, 3221636h
0x18012269f  mov     qword ptr [rsp+0C0h+var_88], rax
0x1801226a4  mov     [rsp+0C0h+var_90], 3Dh ; '='
0x1801226ab  jmp     loc_180122D74
0x1801226b0  lea     r8, [rbp+3Fh+pSecurityDescriptor]
0x1801226b4  mov     rdx, rsi
0x1801226b7  mov     rcx, rbx
0x1801226ba  call    MakeAbsoluteSDHelper
0x1801226bf  xor     ebx, ebx
0x1801226c1  mov     r15d, eax
0x1801226c4  test    eax, eax
0x1801226c6  jnz     loc_18012279D
0x1801226cc  lea     esi, [rax+2]
0x1801226cf  mov     ecx, esi
0x1801226d1  call    IncrementWPPPerfCountersForLevel
0x1801226d6  test    eax, eax
0x1801226d8  jnz     short loc_180122731
0x1801226da  call    THStateCheckForTraceOverride
0x1801226df  lea     r12d, [r15+3]
0x1801226e3  test    eax, eax
0x1801226e5  jnz     short loc_180122737
0x1801226e7  mov     r8d, r12d
0x1801226ea  mov     edx, esi
0x1801226ec  xor     ecx, ecx
0x1801226ee  call    CheckWPPLevelFlagsEnabledForProvider
0x1801226f3  test    eax, eax
0x1801226f5  jnz     short loc_180122737
0x1801226f7  mov     eax, cs:gfTraceToSecondProvider
0x1801226fd  test    eax, eax
0x1801226ff  jz      loc_180122D92
0x180122705  call    THStateCheckForTraceOverride
0x18012270a  test    eax, eax
0x18012270c  jnz     short loc_180122737
0x18012270e  call    ThStateCheckIfTraceToSecondProvier
0x180122713  test    eax, eax
0x180122715  jz      loc_180122D92
0x18012271b  mov     r8d, r12d
0x18012271e  mov     edx, esi
0x180122720  mov     ecx, edi
0x180122722  call    CheckWPPLevelFlagsEnabledForProvider
0x180122727  test    eax, eax
0x180122729  jz      loc_180122D92
0x18012272f  jmp     short loc_180122737
0x180122731  mov     r12d, 3
0x180122737  mov     eax, cs:gfTraceToSecondProvider
0x18012273d  test    eax, eax
0x18012273f  jz      short loc_180122765
0x180122741  call    THStateCheckForTraceOverride
0x180122746  test    eax, eax
0x180122748  jnz     short loc_180122763
0x18012274a  call    ThStateCheckIfTraceToSecondProvier
0x18012274f  test    eax, eax
0x180122751  jz      short loc_180122765
0x180122753  mov     r8d, r12d
0x180122756  mov     edx, esi
0x180122758  mov     ecx, edi
0x18012275a  call    CheckWPPLevelFlagsEnabledForProvider
0x18012275f  test    eax, eax
0x180122761  jz      short loc_180122765
0x180122763  mov     ebx, edi
0x180122765  call    THStateCheckForTraceOverride
0x18012276a  test    eax, eax
0x18012276c  jnz     short loc_180122780
0x18012276e  mov     r8d, r12d
0x180122771  mov     edx, esi
0x180122773  xor     ecx, ecx
0x180122775  call    CheckWPPLevelFlagsEnabledForProvider
0x18012277a  test    eax, eax
0x18012277c  jnz     short loc_180122780
0x18012277e  xor     edi, edi
0x180122780  lea     rax, WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids
0x180122787  mov     edx, 3221641h
0x18012278c  mov     qword ptr [rsp+0C0h+var_88], rax
0x180122791  mov     [rsp+0C0h+var_90], 3Eh ; '>'
0x180122798  jmp     loc_180122D74
0x18012279d  mov     rcx, [rbp+3Fh+pSecurityDescriptor]; pSecurityDescriptor
0x1801227a1  lea     r9, [rbp+3Fh+bDaclDefaulted]; lpbDaclDefaulted
0x1801227a5  lea     r8, [rbp+3Fh+pDacl]; pDacl
0x1801227a9  lea     rdx, [rbp+3Fh+bDaclPresent]; lpbDaclPresent
0x1801227ad  call    cs:__imp_GetSecurityDescriptorDacl
0x1801227b3  mov     r15d, eax
0x1801227b6  test    eax, eax
0x1801227b8  jnz     loc_1801228BC
0x1801227be  lea     esi, [rax+2]
0x1801227c1  mov     ecx, esi
0x1801227c3  call    IncrementWPPPerfCountersForLevel
0x1801227c8  test    eax, eax
0x1801227ca  jnz     short loc_180122823
0x1801227cc  call    THStateCheckForTraceOverride
0x1801227d1  lea     r12d, [r15+3]
0x1801227d5  test    eax, eax
0x1801227d7  jnz     short loc_180122829
0x1801227d9  mov     r8d, r12d
0x1801227dc  mov     edx, esi
0x1801227de  xor     ecx, ecx
0x1801227e0  call    CheckWPPLevelFlagsEnabledForProvider
0x1801227e5  test    eax, eax
0x1801227e7  jnz     short loc_180122829
0x1801227e9  mov     eax, cs:gfTraceToSecondProvider
0x1801227ef  test    eax, eax
0x1801227f1  jz      loc_180122D92
0x1801227f7  call    THStateCheckForTraceOverride
0x1801227fc  test    eax, eax
0x1801227fe  jnz     short loc_180122829
0x180122800  call    ThStateCheckIfTraceToSecondProvier
0x180122805  test    eax, eax
0x180122807  jz      loc_180122D92
0x18012280d  mov     r8d, r12d
0x180122810  mov     edx, esi
0x180122812  mov     ecx, edi
0x180122814  call    CheckWPPLevelFlagsEnabledForProvider
0x180122819  test    eax, eax
0x18012281b  jz      loc_180122D92
0x180122821  jmp     short loc_180122829
0x180122823  mov     r12d, 3
0x180122829  mov     eax, cs:gfTraceToSecondProvider
0x18012282f  test    eax, eax
0x180122831  jz      short loc_180122858
0x180122833  call    THStateCheckForTraceOverride
0x180122838  test    eax, eax
0x18012283a  jnz     short loc_180122855
0x18012283c  call    ThStateCheckIfTraceToSecondProvier
0x180122841  test    eax, eax
0x180122843  jz      short loc_180122858
0x180122845  mov     r8d, r12d
0x180122848  mov     edx, esi
0x18012284a  mov     ecx, edi
0x18012284c  call    CheckWPPLevelFlagsEnabledForProvider
0x180122851  test    eax, eax
0x180122853  jz      short loc_180122858
0x180122855  mov     r14d, edi
0x180122858  call    THStateCheckForTraceOverride
0x18012285d  test    eax, eax
0x18012285f  jnz     short loc_180122873
0x180122861  mov     r8d, r12d
0x180122864  mov     edx, esi
0x180122866  xor     ecx, ecx
0x180122868  call    CheckWPPLevelFlagsEnabledForProvider
0x18012286d  test    eax, eax
0x18012286f  jnz     short loc_180122873
0x180122871  mov     edi, ebx
0x180122873  mov     rax, cs:WPP_GLOBAL_Control
0x18012287a  mov     rbx, [rax+10h]
0x18012287e  call    cs:__imp_GetLastError
  ... truncated ...
```
