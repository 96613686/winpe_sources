# RemoveAccessAllowedACEFromSecurityDescriptor

- ea: `0x180121b5c`
- end: `0x180122488`
- name: `RemoveAccessAllowedACEFromSecurityDescriptor`
- size: `2348`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180160c6c`
- `0x1803cd7c4`
- `0x1803d329c`

## callees

- `0x180006330`
- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x180030af8`
- `0x18003de48`
- `0x18011db10`
- `0x180120480`
- `0x180120ecc`
- `0x180121b5c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180121fe7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180121fe7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180121e98`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180121e98`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18012210d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18012210d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180121fcd`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180121fcd`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x180122005`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x180122005`
- `api-ms-win-security-base-l1-1-0!FindFirstFreeAce` at `0x180122211`
- `api-ms-win-security-base-l1-1-0!FindFirstFreeAce` at `0x180122211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121f6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801220d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801221de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121f6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801220d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801221de`

## pseudocode

```c
__int64 __fastcall RemoveAccessAllowedACEFromSecurityDescriptor(__int64 a1, __int64 a2, void *a3, int a4, LPVOID pAce)
{
  _QWORD *v5; // r13
  unsigned int AbsoluteSDHelper; // r15d
  __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // esi
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // r9
  BOOL v18; // ebx
  bool v19; // zf
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // r8
  __int64 v26; // r9
  BOOL v27; // ebx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // r8
  __int64 v33; // r9
  BOOL v34; // ebx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // r8
  __int64 v41; // r9
  BOOL v42; // r14d
  __int64 v43; // rbx
  DWORD i; // ebx
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // r8
  __int64 v50; // r9
  BOOL v51; // r14d
  __int64 v52; // rbx
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // r8
  __int64 v56; // r9
  __int64 v57; // r8
  __int64 v58; // r9
  BOOL v59; // r14d
  __int64 v60; // rbx
  __int64 v61; // r14
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // r8
  __int64 v65; // r9
  __int64 v66; // r8
  __int64 v67; // r9
  BOOL v68; // ebx
  __int64 v69; // rbx
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // r8
  __int64 v73; // r9
  __int64 v74; // r8
  __int64 v75; // r9
  BOOL v76; // ebx
  int v77; // r8d
  int v78; // r9d
  WINBOOL bDaclPresent; // [rsp+50h] [rbp-30h] BYREF
  __int64 v81; // [rsp+58h] [rbp-28h]
  PACL pDacl; // [rsp+60h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+68h] [rbp-18h] BYREF
  __int64 v84; // [rsp+70h] [rbp-10h] BYREF
  LPVOID v85; // [rsp+78h] [rbp-8h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+C8h] [rbp+48h] BYREF

  v5 = pAce;
  AbsoluteSDHelper = 0;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  *(_QWORD *)pAce = 0;
  v10 = a1;
  pSecurityDescriptor = 0;
  v81 = 0;
  v84 = 0;
  v13 = 1;
  if ( (unsigned int)THStateCheckForTraceOverride(a1, a2)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v12, v11)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v12, v11, v14, v15)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
  {
    v18 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v12, v11)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v12, v11, v16, v17)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
    if ( (unsigned int)THStateCheckForTraceOverride(v12, v11)
      || (v19 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v20 = 0, !v19) )
    {
      v20 = 1;
    }
    WPP_SF__sid_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52565752,
      4,
      3,
      v20,
      v18,
      68,
      &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids,
      a3,
      a4);
    v10 = a1;
  }
  if ( *(__int16 *)(a2 + 2) >= 0 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v22, v21)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v22, v21)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v22, v21, v23, v24)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v27 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v22, v21)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v22, v21, v25, v26)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v22, v21)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v13 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565759,
        2,
        3,
        v13,
        v27,
        69,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
LABEL_154:
    v61 = a1;
    v69 = v81;
    goto LABEL_155;
  }
  AbsoluteSDHelper = MakeAbsoluteSDHelper(v10, a2, &pSecurityDescriptor);
  if ( !AbsoluteSDHelper )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v29, v28)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v29, v28)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v29, v28, v30, v31)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v34 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v29, v28)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v29, v28, v32, v33)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v29, v28)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v13 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565770,
        2,
        3,
        v13,
        v34,
        70,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_154;
  }
  AbsoluteSDHelper = GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted);
  if ( !AbsoluteSDHelper )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v37, v36)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v37, v36)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v37, v36, v38, v39)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v42 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v37, v36)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v37, v36, v40, v41)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v37, v36)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v13 = 0;
      }
      v43 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      GetLastError();
      WPP_SF__ATTRTYP_LOG_(v43, 52565782, 2, 3, v13, v42, 71, (__int64)&WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_154;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= pDacl->AceCount )
    {
      AbsoluteSDHelper = 0;
      if ( (unsigned int)THStateCheckForTraceOverride(pDacl, v35)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v71, v70, v72, v73)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 3)) )
      {
        v76 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v71, v70, v74, v75)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 3));
        if ( !(unsigned int)THStateCheckForTraceOverride(v71, v70)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 3) )
        {
          v13 = 0;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52565808,
          5,
          3,
          v13,
          v76,
          72,
          &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
      }
      goto LABEL_154;
    }
    pAce = 0;
    if ( GetAce(pDacl, i, &pAce) )
    {
      if ( !*(_BYTE *)pAce && EqualSid((char *)pAce + 8, a3) && *((_DWORD *)pAce + 1) == a4 )
        break;
    }
  }
  AbsoluteSDHelper = DeleteAce(pDacl, i);
  if ( !AbsoluteSDHelper )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v46, v45)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v46, v45)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v46, v45, v47, v48)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v51 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v46, v45)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v46, v45, v49, v50)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v46, v45)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v13 = 0;
      }
      v52 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      GetLastError();
      WPP_SF__ATTRTYP_LOG_(v52, 52565815, 2, 3, v13, v51, 73, (__int64)&WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_154;
  }
  AbsoluteSDHelper = SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0);
  if ( !AbsoluteSDHelper )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v54, v53)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v54, v53)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v54, v53, v55, v56)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v59 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v54, v53)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v54, v53, v57, v58)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v54, v53)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v13 = 0;
      }
      v60 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      GetLastError();
      WPP_SF__ATTRTYP_LOG_(v60, 52565829, 2, 3, v13, v59, 74, (__int64)&WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    goto LABEL_154;
  }
  v85 = 0;
  if ( FindFirstFreeAce(pDacl, &v85) && v85 )
    pDacl->AclSize = (_WORD)v85 - (_WORD)pDacl;
  v61 = a1;
  AbsoluteSDHelper = MakeSelfRelativeSDHelper(a1, pSecurityDescriptor, &v84);
  if ( AbsoluteSDHelper )
  {
    v69 = 0;
    *v5 = v84;
  }
  else
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v63, v62)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v63, v62)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v63, v62, v64, v65)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v68 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v63, v62)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v63, v62, v66, v67)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v63, v62)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v13 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52565845,
        2,
        3,
        v13,
        v68,
        75,
        &WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids);
    }
    v69 = v84;
  }
LABEL_155:
  FreeAbsoluteSDHelper(v61, pSecurityDescriptor);
  if ( v69 )
    THFreeAux(v61, v69, v77, v78, 52565855);
  return AbsoluteSDHelper;
}

```

## disassembly

```asm
0x180121b5c  mov     [rsp-38h+arg_10], rbx
0x180121b61  mov     [rsp-38h+arg_0], rcx
0x180121b66  push    rbp
0x180121b67  push    rsi
0x180121b68  push    rdi
0x180121b69  push    r12
0x180121b6b  push    r13
0x180121b6d  push    r14
0x180121b6f  push    r15
0x180121b71  mov     rbp, rsp
0x180121b74  sub     rsp, 80h
0x180121b7b  mov     r13, [rbp+pAce]
0x180121b7f  xor     r15d, r15d
0x180121b82  mov     eax, r15d
0x180121b85  mov     [rbp+pDacl], r15
0x180121b89  mov     r14d, r9d
0x180121b8c  mov     [rbp+bDaclPresent], r15d
0x180121b90  mov     r12, r8
0x180121b93  mov     [rbp+bDaclDefaulted], r15d
0x180121b97  mov     [r13+0], r15
0x180121b9b  mov     rdi, rdx
0x180121b9e  mov     rbx, rcx
0x180121ba1  mov     [rbp+pSecurityDescriptor], r15
0x180121ba5  mov     [rbp+var_28], rax
0x180121ba9  mov     [rbp+var_10], rax
0x180121bad  call    THStateCheckForTraceOverride
0x180121bb2  lea     esi, [r15+1]
0x180121bb6  test    eax, eax
0x180121bb8  jnz     short loc_180121C06
0x180121bba  lea     edx, [rsi+3]
0x180121bbd  xor     ecx, ecx
0x180121bbf  lea     r8d, [r15+3]
0x180121bc3  call    CheckWPPLevelFlagsEnabledForProvider
0x180121bc8  test    eax, eax
0x180121bca  jnz     short loc_180121C06
0x180121bcc  mov     eax, cs:gfTraceToSecondProvider
0x180121bd2  test    eax, eax
0x180121bd4  jz      loc_180121CA5
0x180121bda  call    THStateCheckForTraceOverride
0x180121bdf  test    eax, eax
0x180121be1  jnz     short loc_180121C06
0x180121be3  call    ThStateCheckIfTraceToSecondProvier
0x180121be8  test    eax, eax
0x180121bea  jz      loc_180121CA5
0x180121bf0  lea     edx, [rsi+3]
0x180121bf3  mov     ecx, esi
0x180121bf5  lea     r8d, [r15+3]
0x180121bf9  call    CheckWPPLevelFlagsEnabledForProvider
0x180121bfe  test    eax, eax
0x180121c00  jz      loc_180121CA5
0x180121c06  mov     eax, cs:gfTraceToSecondProvider
0x180121c0c  test    eax, eax
0x180121c0e  jz      short loc_180121C3A
0x180121c10  call    THStateCheckForTraceOverride
0x180121c15  test    eax, eax
0x180121c17  jnz     short loc_180121C36
0x180121c19  call    ThStateCheckIfTraceToSecondProvier
0x180121c1e  test    eax, eax
0x180121c20  jz      short loc_180121C3A
0x180121c22  mov     edx, 4
0x180121c27  mov     ecx, esi
0x180121c29  lea     r8d, [rdx-1]
0x180121c2d  call    CheckWPPLevelFlagsEnabledForProvider
0x180121c32  test    eax, eax
0x180121c34  jz      short loc_180121C3A
0x180121c36  mov     ebx, esi
0x180121c38  jmp     short loc_180121C3D
0x180121c3a  mov     ebx, r15d
0x180121c3d  call    THStateCheckForTraceOverride
0x180121c42  test    eax, eax
0x180121c44  jnz     short loc_180121C5B
0x180121c46  lea     edx, [rax+4]
0x180121c49  xor     ecx, ecx
0x180121c4b  lea     r8d, [rax+3]
0x180121c4f  call    CheckWPPLevelFlagsEnabledForProvider
0x180121c54  test    eax, eax
0x180121c56  mov     eax, r15d
0x180121c59  jz      short loc_180121C5D
0x180121c5b  mov     eax, esi
0x180121c5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180121c64  lea     rdx, WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids
0x180121c6b  mov     dword ptr [rsp+80h+var_38], r14d; char
0x180121c70  mov     r9d, 3; int
0x180121c76  mov     [rsp+80h+pSid], r12; pSid
0x180121c7b  mov     [rsp+80h+var_48], rdx; LPCGUID
0x180121c80  mov     edx, 32216F8h; int
0x180121c85  mov     rcx, [rcx+10h]; int
0x180121c89  mov     [rsp+80h+var_50], 44h ; 'D'; __int16
0x180121c90  lea     r8d, [r9+1]; int
0x180121c94  mov     [rsp+80h+var_58], ebx; int
0x180121c98  mov     [rsp+80h+var_60], eax; int
0x180121c9c  call    WPP_SF__sid_D
0x180121ca1  mov     rbx, [rbp+arg_0]
0x180121ca5  cmp     [rdi+2], r15w
0x180121caa  jl      loc_180121D91
0x180121cb0  xor     r12d, r12d
0x180121cb3  lea     edi, [r12+2]
0x180121cb8  mov     ecx, edi
0x180121cba  call    IncrementWPPPerfCountersForLevel
0x180121cbf  test    eax, eax
0x180121cc1  jnz     short loc_180121D18
0x180121cc3  call    THStateCheckForTraceOverride
0x180121cc8  test    eax, eax
0x180121cca  jnz     short loc_180121D18
0x180121ccc  lea     r8d, [r12+3]
0x180121cd1  mov     edx, edi
0x180121cd3  xor     ecx, ecx
0x180121cd5  call    CheckWPPLevelFlagsEnabledForProvider
0x180121cda  test    eax, eax
0x180121cdc  jnz     short loc_180121D18
0x180121cde  mov     eax, cs:gfTraceToSecondProvider
0x180121ce4  test    eax, eax
0x180121ce6  jz      loc_18012243E
0x180121cec  call    THStateCheckForTraceOverride
0x180121cf1  test    eax, eax
0x180121cf3  jnz     short loc_180121D18
0x180121cf5  call    ThStateCheckIfTraceToSecondProvier
0x180121cfa  test    eax, eax
0x180121cfc  jz      loc_18012243E
0x180121d02  lea     r8d, [r12+3]
0x180121d07  mov     edx, edi
0x180121d09  mov     ecx, esi
0x180121d0b  call    CheckWPPLevelFlagsEnabledForProvider
0x180121d10  test    eax, eax
0x180121d12  jz      loc_18012243E
0x180121d18  mov     eax, cs:gfTraceToSecondProvider
0x180121d1e  test    eax, eax
0x180121d20  jz      short loc_180121D4B
0x180121d22  call    THStateCheckForTraceOverride
0x180121d27  test    eax, eax
0x180121d29  jnz     short loc_180121D47
0x180121d2b  call    ThStateCheckIfTraceToSecondProvier
0x180121d30  test    eax, eax
0x180121d32  jz      short loc_180121D4B
0x180121d34  mov     r8d, 3
0x180121d3a  mov     edx, edi
0x180121d3c  mov     ecx, esi
0x180121d3e  call    CheckWPPLevelFlagsEnabledForProvider
0x180121d43  test    eax, eax
0x180121d45  jz      short loc_180121D4B
0x180121d47  mov     ebx, esi
0x180121d49  jmp     short loc_180121D4E
0x180121d4b  mov     ebx, r12d
0x180121d4e  call    THStateCheckForTraceOverride
0x180121d53  test    eax, eax
0x180121d55  jnz     short loc_180121D6B
0x180121d57  lea     r8d, [rax+3]
0x180121d5b  mov     edx, edi
0x180121d5d  xor     ecx, ecx
0x180121d5f  call    CheckWPPLevelFlagsEnabledForProvider
0x180121d64  test    eax, eax
0x180121d66  jnz     short loc_180121D6B
0x180121d68  mov     esi, r12d
0x180121d6b  lea     rcx, WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids
0x180121d72  mov     r9d, 3
0x180121d78  mov     [rsp+80h+var_48], rcx
0x180121d7d  mov     r8d, edi
0x180121d80  mov     [rsp+80h+var_50], 45h ; 'E'
0x180121d87  mov     edx, 32216FFh
0x180121d8c  jmp     loc_180122426
0x180121d91  lea     r8, [rbp+pSecurityDescriptor]
0x180121d95  mov     rdx, rdi
0x180121d98  mov     rcx, rbx
0x180121d9b  call    MakeAbsoluteSDHelper
0x180121da0  mov     r15d, eax
0x180121da3  test    eax, eax
0x180121da5  jnz     loc_180121E88
0x180121dab  lea     edi, [rax+2]
0x180121dae  mov     ecx, edi
0x180121db0  call    IncrementWPPPerfCountersForLevel
0x180121db5  xor     r12d, r12d
0x180121db8  test    eax, eax
0x180121dba  jnz     short loc_180121E0F
0x180121dbc  call    THStateCheckForTraceOverride
0x180121dc1  test    eax, eax
0x180121dc3  jnz     short loc_180121E0F
0x180121dc5  lea     r8d, [r15+3]
0x180121dc9  mov     edx, edi
0x180121dcb  xor     ecx, ecx
0x180121dcd  call    CheckWPPLevelFlagsEnabledForProvider
0x180121dd2  test    eax, eax
0x180121dd4  jnz     short loc_180121E0F
0x180121dd6  mov     eax, cs:gfTraceToSecondProvider
0x180121ddc  test    eax, eax
0x180121dde  jz      loc_18012243E
0x180121de4  call    THStateCheckForTraceOverride
0x180121de9  test    eax, eax
0x180121deb  jnz     short loc_180121E0F
0x180121ded  call    ThStateCheckIfTraceToSecondProvier
0x180121df2  test    eax, eax
0x180121df4  jz      loc_18012243E
0x180121dfa  lea     r8d, [r15+3]
0x180121dfe  mov     edx, edi
0x180121e00  mov     ecx, esi
0x180121e02  call    CheckWPPLevelFlagsEnabledForProvider
0x180121e07  test    eax, eax
0x180121e09  jz      loc_18012243E
0x180121e0f  mov     eax, cs:gfTraceToSecondProvider
0x180121e15  test    eax, eax
0x180121e17  jz      short loc_180121E42
0x180121e19  call    THStateCheckForTraceOverride
0x180121e1e  test    eax, eax
0x180121e20  jnz     short loc_180121E3E
0x180121e22  call    ThStateCheckIfTraceToSecondProvier
0x180121e27  test    eax, eax
0x180121e29  jz      short loc_180121E42
0x180121e2b  mov     r8d, 3
0x180121e31  mov     edx, edi
0x180121e33  mov     ecx, esi
0x180121e35  call    CheckWPPLevelFlagsEnabledForProvider
0x180121e3a  test    eax, eax
0x180121e3c  jz      short loc_180121E42
0x180121e3e  mov     ebx, esi
0x180121e40  jmp     short loc_180121E45
0x180121e42  mov     ebx, r12d
0x180121e45  call    THStateCheckForTraceOverride
0x180121e4a  test    eax, eax
0x180121e4c  jnz     short loc_180121E62
0x180121e4e  lea     r8d, [rax+3]
0x180121e52  mov     edx, edi
0x180121e54  xor     ecx, ecx
0x180121e56  call    CheckWPPLevelFlagsEnabledForProvider
0x180121e5b  test    eax, eax
0x180121e5d  jnz     short loc_180121E62
0x180121e5f  mov     esi, r12d
0x180121e62  lea     rcx, WPP_f2d6e7c1e0bd38d19c25d81c667d5425_Traceguids
0x180121e69  mov     r9d, 3
0x180121e6f  mov     [rsp+80h+var_48], rcx
0x180121e74  mov     r8d, edi
0x180121e77  mov     [rsp+80h+var_50], 46h ; 'F'
0x180121e7e  mov     edx, 322170Ah
0x180121e83  jmp     loc_180122426
0x180121e88  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180121e8c  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180121e90  lea     r8, [rbp+pDacl]; pDacl
0x180121e94  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180121e98  call    cs:__imp_GetSecurityDescriptorDacl
0x180121e9e  mov     r15d, eax
0x180121ea1  test    eax, eax
0x180121ea3  jnz     loc_180121FAD
0x180121ea9  lea     edi, [rax+2]
0x180121eac  mov     ecx, edi
0x180121eae  call    IncrementWPPPerfCountersForLevel
0x180121eb3  xor     r12d, r12d
0x180121eb6  test    eax, eax
0x180121eb8  jnz     short loc_180121F0D
0x180121eba  call    THStateCheckForTraceOverride
0x180121ebf  test    eax, eax
0x180121ec1  jnz     short loc_180121F0D
0x180121ec3  lea     r8d, [r15+3]
0x180121ec7  mov     edx, edi
0x180121ec9  xor     ecx, ecx
0x180121ecb  call    CheckWPPLevelFlagsEnabledForProvider
0x180121ed0  test    eax, eax
0x180121ed2  jnz     short loc_180121F0D
0x180121ed4  mov     eax, cs:gfTraceToSecondProvider
0x180121eda  test    eax, eax
0x180121edc  jz      loc_18012243E
0x180121ee2  call    THStateCheckForTraceOverride
0x180121ee7  test    eax, eax
0x180121ee9  jnz     short loc_180121F0D
0x180121eeb  call    ThStateCheckIfTraceToSecondProvier
0x180121ef0  test    eax, eax
0x180121ef2  jz      loc_18012243E
0x180121ef8  lea     r8d, [r15+3]
0x180121efc  mov     edx, edi
0x180121efe  mov     ecx, esi
0x180121f00  call    CheckWPPLevelFlagsEnabledForProvider
0x180121f05  test    eax, eax
0x180121f07  jz      loc_18012243E
0x180121f0d  mov     eax, cs:gfTraceToSecondProvider
0x180121f13  test    eax, eax
0x180121f15  jz      short loc_180121F41
0x180121f17  call    THStateCheckForTraceOverride
0x180121f1c  test    eax, eax
0x180121f1e  jnz     short loc_180121F3C
0x180121f20  call    ThStateCheckIfTraceToSecondProvier
0x180121f25  test    eax, eax
0x180121f27  jz      short loc_180121F41
0x180121f29  mov     r8d, 3
0x180121f2f  mov     edx, edi
0x180121f31  mov     ecx, esi
0x180121f33  call    CheckWPPLevelFlagsEnabledForProvider
0x180121f38  test    eax, eax
0x180121f3a  jz      short loc_180121F41
0x180121f3c  mov     r14d, esi
0x180121f3f  jmp     short loc_180121F44
0x180121f41  mov     r14d, r12d
0x180121f44  call    THStateCheckForTraceOverride
0x180121f49  test    eax, eax
0x180121f4b  jnz     short loc_180121F61
0x180121f4d  lea     r8d, [rax+3]
0x180121f51  mov     edx, edi
0x180121f53  xor     ecx, ecx
0x180121f55  call    CheckWPPLevelFlagsEnabledForProvider
0x180121f5a  test    eax, eax
0x180121f5c  jnz     short loc_180121F61
0x180121f5e  mov     esi, r12d
0x180121f61  mov     rax, cs:WPP_GLOBAL_Control
0x180121f68  mov     rbx, [rax+10h]
  ... truncated ...
```
