# CreateRootDomainObject(ushort *,_GUID *,_CROSS_REF *)

- ea: `0x18018cd44`
- end: `0x18018d790`
- name: `?CreateRootDomainObject@@YAJPEAGPEAU_GUID@@PEAU_CROSS_REF@@@Z`
- size: `2636`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GUID *, struct _CROSS_REF *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180194070`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180030af8`
- `0x180030bd4`
- `0x1800334d0`
- `0x180033b28`
- `0x180037ce0`
- `0x1800528dc`
- `0x180100488`
- `0x18010e330`
- `0x180172edc`
- `0x18018cd44`
- `0x180192394`
- `0x1801972a8`
- `0x180197580`
- `0x180197a2c`
- `0x180199ed0`
- `0x18019a400`
- `0x18019a4bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18018cfbd`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18018cfbd`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18018cdd4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18018cdd4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18018ce24`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18018ce24`
- `ntdll!RtlFreeHeap` at `0x18018d55b`
- `ntdll!RtlFreeHeap` at `0x18018d55b`
- `ntdll!RtlLengthSid` at `0x18018d395`
- `ntdll!RtlLengthSid` at `0x18018d395`
- `ADVAPI32!LsaOpenPolicy` at `0x18018d103`
- `ADVAPI32!LsaOpenPolicy` at `0x18018d103`
- `ADVAPI32!LsaClose` at `0x18018d21c`
- `ADVAPI32!LsaClose` at `0x18018d21c`
- `ADVAPI32!LsaFreeMemory` at `0x18018d549`
- `ADVAPI32!LsaFreeMemory` at `0x18018d549`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18018d20f`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18018d20f`

## pseudocode

```c
__int64 __fastcall CreateRootDomainObject(unsigned __int16 *a1, struct _GUID *a2, struct _CROSS_REF *a3)
{
  int v6; // r15d
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rbx
  unsigned __int16 *i; // r15
  int v10; // esi
  LPVOID Value; // rax
  int v12; // eax
  unsigned int v13; // ebx
  unsigned int j; // ecx
  __int64 v15; // r15
  struct _GUID *v16; // rcx
  int v17; // r9d
  BOOL v18; // r14d
  int v19; // eax
  int v20; // r13d
  bool v21; // zf
  NTSTATUS v22; // r15d
  BOOL v24; // r14d
  NTSTATUS v25; // r12d
  BOOL v26; // r14d
  __int64 v27; // r15
  void *v28; // r13
  unsigned int v29; // eax
  int v30; // ebx
  unsigned __int16 v31; // r14
  int v32; // eax
  int v33; // r14d
  int v34; // edx
  int v35; // r8d
  int v36; // r9d
  int v37; // esi
  int v38; // esi
  BOOL v39; // r14d
  int v40; // [rsp+30h] [rbp-D0h]
  int v41; // [rsp+38h] [rbp-C8h]
  int v42; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v43; // [rsp+74h] [rbp-8Ch] BYREF
  int v44; // [rsp+78h] [rbp-88h] BYREF
  int v45; // [rsp+7Ch] [rbp-84h] BYREF
  PVOID Buffer; // [rsp+80h] [rbp-80h] BYREF
  PVOID PolicyHandle; // [rsp+88h] [rbp-78h] BYREF
  __int64 v48; // [rsp+90h] [rbp-70h] BYREF
  __int128 v49; // [rsp+98h] [rbp-68h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v51[24]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v52; // [rsp+F8h] [rbp-8h]
  __int64 v53; // [rsp+108h] [rbp+8h]
  __int64 v54; // [rsp+110h] [rbp+10h]
  __int64 v55; // [rsp+118h] [rbp+18h]
  void *v56; // [rsp+150h] [rbp+50h] BYREF
  __int16 v57; // [rsp+158h] [rbp+58h]
  __int64 v58; // [rsp+160h] [rbp+60h]
  __int16 v59; // [rsp+168h] [rbp+68h]
  int v60; // [rsp+170h] [rbp+70h]
  int v61; // [rsp+178h] [rbp+78h]
  __int128 *v62; // [rsp+180h] [rbp+80h]
  _BYTE v63[216]; // [rsp+1D8h] [rbp+D8h] BYREF

  memset_0(&v56, 0, 0x160u);
  v6 = 0;
  v48 = 0;
  v49 = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  PolicyHandle = 0;
  NODE::NODE((NODE *)v51, (char *)qword_180526CB0);
  if ( v52 )
  {
    v7 = wcschr(a1, 0x3Du);
    v8 = v7;
    if ( !v7 || a1 == v7 )
    {
      v37 = 1;
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride()
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride()
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        if ( gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride()
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
        {
          v6 = 1;
        }
        if ( !(unsigned int)THStateCheckForTraceOverride()
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
        {
          v37 = 0;
        }
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          117506960,
          2,
          3,
          v37,
          v6,
          12,
          &WPP_917fdaafcb49317f4b06728749c09966_Traceguids,
          (__int64)a1);
      }
      NODE::~NODE((NODE *)v51);
      return 3221225523LL;
    }
    else
    {
      for ( i = a1; *i == 32; ++i )
        ;
      do
        --v8;
      while ( *v8 == 32 );
      v10 = 1;
      Value = TlsGetValue(dwTSindex);
      v12 = KeyToAttrType(Value, i, (unsigned int)(v8 - i) + 1);
      v13 = 0;
      v42 = v12;
      for ( j = 0; ; ++j )
      {
        if ( j >= 5 )
        {
          v15 = 0;
          if ( j != 5 )
            goto LABEL_12;
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
            || (unsigned int)THStateCheckForTraceOverride()
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride()
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
          {
            v18 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride()
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
            if ( !(unsigned int)THStateCheckForTraceOverride()
              && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
            {
              v10 = 0;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              117506997,
              2,
              3,
              v10,
              v18,
              13,
              (__int64)&WPP_917fdaafcb49317f4b06728749c09966_Traceguids);
          }
          goto LABEL_154;
        }
        if ( v12 == *((_DWORD *)&rDomainMappings + 4 * j) )
          break;
      }
      v15 = (__int64)*(&rDomainMappings + 2 * j + 1);
LABEL_12:
      if ( !a3 || (unsigned int)fNullUuid(*(_QWORD *)a3 + 8LL) )
      {
        DsUuidCreate(a2);
        if ( a3 )
          *(struct _GUID *)(*(_QWORD *)a3 + 8LL) = *a2;
      }
      else
      {
        *a2 = *v16;
      }
      v19 = v55;
      v20 = 0;
      if ( (_DWORD)v55 )
      {
        do
        {
          v21 = (unsigned int)_o__stricmp("objectClass", *(_QWORD *)(v53 + 8LL * v13)) == 0;
          v19 = v55;
          if ( v21 )
            break;
          ++v13;
        }
        while ( v13 < (unsigned int)v55 );
      }
      if ( v13 != v19 )
        *(_QWORD *)(v54 + 8LL * v13) = v15;
      v22 = AddOneObjectEx((struct NODE *)v51, a1, a2, v17);
      if ( v22 < 0 )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride()
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride()
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
        {
          if ( gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride()
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
          {
            v20 = 1;
          }
          if ( !(unsigned int)THStateCheckForTraceOverride()
            && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
          {
            v10 = 0;
          }
          WPP_SF_S_guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v20, v40, v41, (__int64)a1, (__int64)a2, v22);
        }
LABEL_57:
        NODE::~NODE((NODE *)v51);
        return (unsigned int)v22;
      }
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v22 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
      if ( v22 < 0 )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride()
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride()
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
        {
          v24 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride()
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
          if ( !(unsigned int)THStateCheckForTraceOverride()
            && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
          {
            v10 = 0;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            117507079,
            2,
            3,
            v10,
            v24,
            15,
            (__int64)&WPP_917fdaafcb49317f4b06728749c09966_Traceguids);
        }
        goto LABEL_57;
      }
      v25 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
      LsaClose(PolicyHandle);
      if ( v25 >= 0 )
      {
        v27 = -1;
        do
          ++v27;
        while ( a1[v27] );
        v28 = XCalloc(1u, 2 * (int)v27 + 58);
        *(_DWORD *)v28 = 2 * v27 + 58;
        *((_DWORD *)v28 + 13) = v27;
        StringCchCopyW((unsigned __int16 *)v28 + 28, (unsigned int)(v27 + 1), a1);
        v56 = v28;
        v57 = 1;
        v58 = 0;
        v60 = 589970;
        v59 = 65;
        v62 = &v49;
        v61 = 1;
        LODWORD(v49) = RtlLengthSid(*((PSID *)Buffer + 8));
        *((_QWORD *)&v49 + 1) = *((_QWORD *)Buffer + 8);
        InitCommarg(v63);
        v29 = DirModifyEntryNative(&v56, &v48);
        if ( v29 )
        {
          v30 = v48;
          v45 = 0;
          v31 = 0;
          v44 = 0;
          v42 = 0;
          v43 = 0;
          if ( v48 )
          {
            v22 = DirErrorToNtStatus(v29);
            GetDirErrInfo(v30, (unsigned int)&v43, (unsigned int)&v42, (unsigned int)&v45, (__int64)&v44);
            v31 = v43;
          }
          else
          {
            v22 = -1073741801;
            v42 = 8;
          }
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
            || (unsigned int)THStateCheckForTraceOverride()
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride()
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
          {
            v32 = v31;
            v33 = 0;
            v44 = v32;
            if ( gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride()
               || (unsigned int)ThStateCheckIfTraceToSecondProvier()
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
            {
              v33 = 1;
            }
            if ( !(unsigned int)THStateCheckForTraceOverride()
              && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
            {
              v10 = 0;
            }
            WPP_SF_dDddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, v35, v36, v10, v33);
          }
          goto LABEL_57;
        }
        if ( Buffer )
          LsaFreeMemory(Buffer);
        RtlFreeHeap(ghInstallHeap, 0, v28);
      }
      else if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
             || (unsigned int)THStateCheckForTraceOverride()
             || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
             || gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride()
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        v26 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride()
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
        if ( !(unsigned int)THStateCheckForTraceOverride()
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
        {
          v10 = 0;
        }
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          117507096,
          2,
          3,
          v10,
          v26,
          16,
          (__int64)&WPP_917fdaafcb49317f4b06728749c09966_Traceguids);
      }
      NODE::~NODE((NODE *)v51);
      return (unsigned int)v25;
    }
  }
  else
  {
    v38 = 1;
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride()
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride()
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
    {
      v39 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride()
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride() && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
        v38 = 0;
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        117506942,
        2,
        3,
        v38,
        v39,
        11,
        &WPP_917fdaafcb49317f4b06728749c09966_Traceguids);
    }
LABEL_154:
    NODE::~NODE((NODE *)v51);
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x18018cd44  mov     [rsp-8+arg_18], rbx
0x18018cd49  push    rbp
0x18018cd4a  push    rsi
0x18018cd4b  push    rdi
0x18018cd4c  push    r12
0x18018cd4e  push    r13
0x18018cd50  push    r14
0x18018cd52  push    r15
0x18018cd54  lea     rbp, [rsp-1C0h]
0x18018cd5c  sub     rsp, 2C0h
0x18018cd63  mov     rax, cs:__security_cookie
0x18018cd6a  xor     rax, rsp
0x18018cd6d  mov     [rbp+1F0h+var_40], rax
0x18018cd74  mov     r13, r8
0x18018cd77  mov     r12, rdx
0x18018cd7a  mov     r14, rcx
0x18018cd7d  xor     edx, edx; Val
0x18018cd7f  mov     r8d, 160h; Size
0x18018cd85  lea     rcx, [rbp+1F0h+var_1A0]; void *
0x18018cd89  call    memset_0
0x18018cd8e  mov     rdx, cs:qword_180526CB0; char *
0x18018cd95  lea     rcx, [rbp+1F0h+var_210]; this
0x18018cd99  xorps   xmm1, xmm1
0x18018cd9c  xor     r15d, r15d
0x18018cd9f  xorps   xmm0, xmm0
0x18018cda2  mov     [rbp+1F0h+var_260], r15
0x18018cda6  movups  [rbp+1F0h+var_258], xmm0
0x18018cdaa  mov     [rbp+1F0h+Buffer], r15
0x18018cdae  movups  xmmword ptr [rbp+1F0h+ObjectAttributes.Length], xmm1
0x18018cdb2  mov     [rbp+1F0h+PolicyHandle], r15
0x18018cdb6  movups  xmmword ptr [rbp+1F0h+ObjectAttributes.ObjectName], xmm1
0x18018cdba  movups  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x18018cdbe  call    ??0NODE@@QEAA@PEAD@Z; NODE::NODE(char *)
0x18018cdc3  cmp     [rbp+1F0h+var_1F8], r15
0x18018cdc7  jz      loc_18018D66A
0x18018cdcd  lea     edx, [r15+3Dh]; Ch
0x18018cdd1  mov     rcx, r14; Str
0x18018cdd4  call    cs:__imp_wcschr
0x18018cdda  mov     rbx, rax
0x18018cddd  test    rax, rax
0x18018cde0  jz      loc_18018D566
0x18018cde6  cmp     r14, rax
0x18018cde9  jz      loc_18018D566
0x18018cdef  mov     eax, 20h ; ' '
0x18018cdf4  mov     r15, r14
0x18018cdf7  lea     edi, [rax-1Eh]
0x18018cdfa  cmp     ax, [r14]
0x18018cdfe  jnz     short loc_18018CE09
0x18018ce00  add     r15, rdi
0x18018ce03  cmp     ax, [r15]
0x18018ce07  jz      short loc_18018CE00
0x18018ce09  sub     rbx, rdi
0x18018ce0c  cmp     ax, [rbx]
0x18018ce0f  jz      short loc_18018CE09
0x18018ce11  mov     ecx, cs:dwTSindex; dwTlsIndex
0x18018ce17  sub     rbx, r15
0x18018ce1a  sar     rbx, 1
0x18018ce1d  mov     esi, 1
0x18018ce22  add     ebx, esi
0x18018ce24  call    cs:__imp_TlsGetValue
0x18018ce2a  mov     r8d, ebx
0x18018ce2d  mov     rdx, r15
0x18018ce30  mov     rcx, rax
0x18018ce33  call    KeyToAttrType
0x18018ce38  xor     ebx, ebx
0x18018ce3a  mov     [rsp+2F0h+var_280], eax
0x18018ce3e  mov     ecx, ebx
0x18018ce40  lea     r15, ?rDomainMappings@@3PAUClassMapping@@A; ClassMapping near * rDomainMappings
0x18018ce47  cmp     ecx, 5
0x18018ce4a  jnb     short loc_18018CE8C
0x18018ce4c  mov     edx, ecx
0x18018ce4e  add     rdx, rdx
0x18018ce51  cmp     eax, [r15+rdx*8]
0x18018ce55  jz      short loc_18018CE5B
0x18018ce57  add     ecx, esi
0x18018ce59  jmp     short loc_18018CE47
0x18018ce5b  mov     r15, [r15+rdx*8+8]
0x18018ce60  test    r13, r13
0x18018ce63  jz      loc_18018CF86
0x18018ce69  mov     rcx, [r13+0]
0x18018ce6d  add     rcx, 8
0x18018ce71  call    fNullUuid
0x18018ce76  test    eax, eax
0x18018ce78  jnz     loc_18018CF86
0x18018ce7e  movups  xmm0, xmmword ptr [rcx]
0x18018ce81  movdqu  xmmword ptr [r12], xmm0
0x18018ce87  jmp     loc_18018CFA1
0x18018ce8c  mov     r15, rbx
0x18018ce8f  jnz     short loc_18018CE60
0x18018ce91  mov     ecx, edi
0x18018ce93  call    IncrementWPPPerfCountersForLevel
0x18018ce98  mov     ebx, 3
0x18018ce9d  test    eax, eax
0x18018ce9f  jnz     short loc_18018CEF2
0x18018cea1  call    THStateCheckForTraceOverride
0x18018cea6  test    eax, eax
0x18018cea8  jnz     short loc_18018CEF2
0x18018ceaa  mov     r8d, ebx
0x18018cead  mov     edx, edi
0x18018ceaf  xor     ecx, ecx
0x18018ceb1  call    CheckWPPLevelFlagsEnabledForProvider
0x18018ceb6  test    eax, eax
0x18018ceb8  jnz     short loc_18018CEF2
0x18018ceba  mov     eax, cs:gfTraceToSecondProvider
0x18018cec0  test    eax, eax
0x18018cec2  jz      loc_18018D758
0x18018cec8  call    THStateCheckForTraceOverride
0x18018cecd  test    eax, eax
0x18018cecf  jnz     short loc_18018CEF2
0x18018ced1  call    ThStateCheckIfTraceToSecondProvier
0x18018ced6  test    eax, eax
0x18018ced8  jz      loc_18018D758
0x18018cede  mov     r8d, ebx
0x18018cee1  mov     edx, edi
0x18018cee3  mov     ecx, esi
0x18018cee5  call    CheckWPPLevelFlagsEnabledForProvider
0x18018ceea  test    eax, eax
0x18018ceec  jz      loc_18018D758
0x18018cef2  mov     eax, cs:gfTraceToSecondProvider
0x18018cef8  test    eax, eax
0x18018cefa  jz      short loc_18018CF23
0x18018cefc  call    THStateCheckForTraceOverride
0x18018cf01  test    eax, eax
0x18018cf03  jnz     short loc_18018CF1E
0x18018cf05  call    ThStateCheckIfTraceToSecondProvier
0x18018cf0a  test    eax, eax
0x18018cf0c  jz      short loc_18018CF23
0x18018cf0e  mov     r8d, ebx
0x18018cf11  mov     edx, edi
0x18018cf13  mov     ecx, esi
0x18018cf15  call    CheckWPPLevelFlagsEnabledForProvider
0x18018cf1a  test    eax, eax
0x18018cf1c  jz      short loc_18018CF23
0x18018cf1e  mov     r14d, esi
0x18018cf21  jmp     short loc_18018CF26
0x18018cf23  mov     r14d, r15d
0x18018cf26  call    THStateCheckForTraceOverride
0x18018cf2b  test    eax, eax
0x18018cf2d  jnz     short loc_18018CF42
0x18018cf2f  mov     r8d, ebx
0x18018cf32  mov     edx, edi
0x18018cf34  xor     ecx, ecx
0x18018cf36  call    CheckWPPLevelFlagsEnabledForProvider
0x18018cf3b  test    eax, eax
0x18018cf3d  jnz     short loc_18018CF42
0x18018cf3f  mov     esi, r15d
0x18018cf42  mov     eax, [rsp+2F0h+var_280]
0x18018cf46  mov     r9d, ebx
0x18018cf49  mov     rcx, cs:WPP_GLOBAL_Control
0x18018cf50  mov     r8d, edi
0x18018cf53  mov     dword ptr [rsp+2F0h+var_2B0], eax
0x18018cf57  mov     edx, 70103B5h
0x18018cf5c  lea     rax, WPP_917fdaafcb49317f4b06728749c09966_Traceguids
0x18018cf63  mov     [rsp+2F0h+var_2B8], rax
0x18018cf68  mov     rcx, [rcx+10h]
0x18018cf6c  mov     [rsp+2F0h+var_2C0], 0Dh
0x18018cf73  mov     [rsp+2F0h+var_2C8], r14d
0x18018cf78  mov     [rsp+2F0h+var_2D0], esi
0x18018cf7c  call    WPP_SF__ATTRTYP_LOG_
0x18018cf81  jmp     loc_18018D758
0x18018cf86  mov     rcx, r12
0x18018cf89  call    DsUuidCreate
0x18018cf8e  test    r13, r13
0x18018cf91  jz      short loc_18018CFA1
0x18018cf93  mov     rax, [r13+0]
0x18018cf97  movups  xmm0, xmmword ptr [r12]
0x18018cf9c  movdqu  xmmword ptr [rax+8], xmm0
0x18018cfa1  mov     rax, [rbp+1F0h+var_1D8]
0x18018cfa5  xor     r13d, r13d
0x18018cfa8  test    eax, eax
0x18018cfaa  jz      short loc_18018CFD1
0x18018cfac  mov     rdx, [rbp+1F0h+var_1E8]
0x18018cfb0  lea     rcx, aObjectclass_4; "objectClass"
0x18018cfb7  mov     eax, ebx
0x18018cfb9  mov     rdx, [rdx+rax*8]
0x18018cfbd  call    cs:__imp__o__stricmp
0x18018cfc3  test    eax, eax
0x18018cfc5  mov     rax, [rbp+1F0h+var_1D8]
0x18018cfc9  jz      short loc_18018CFD1
0x18018cfcb  add     ebx, esi
0x18018cfcd  cmp     ebx, eax
0x18018cfcf  jb      short loc_18018CFAC
0x18018cfd1  cmp     ebx, eax
0x18018cfd3  jz      short loc_18018CFDF
0x18018cfd5  mov     rax, [rbp+1F0h+var_1E0]
0x18018cfd9  mov     ecx, ebx
0x18018cfdb  mov     [rax+rcx*8], r15
0x18018cfdf  mov     r8, r12; struct _GUID *
0x18018cfe2  lea     rcx, [rbp+1F0h+var_210]; struct NODE *
0x18018cfe6  mov     rdx, r14; unsigned __int16 *
0x18018cfe9  call    ?AddOneObjectEx@@YAJPEAVNODE@@PEAGPEAU_GUID@@H@Z; AddOneObjectEx(NODE *,ushort *,_GUID *,int)
0x18018cfee  mov     r15d, eax
0x18018cff1  test    eax, eax
0x18018cff3  jns     loc_18018D0DB
0x18018cff9  mov     ecx, edi
0x18018cffb  call    IncrementWPPPerfCountersForLevel
0x18018d000  mov     ebx, 3
0x18018d005  test    eax, eax
0x18018d007  jnz     short loc_18018D056
0x18018d009  call    THStateCheckForTraceOverride
0x18018d00e  test    eax, eax
0x18018d010  jnz     short loc_18018D056
0x18018d012  mov     r8d, ebx
0x18018d015  mov     edx, edi
0x18018d017  xor     ecx, ecx
0x18018d019  call    CheckWPPLevelFlagsEnabledForProvider
0x18018d01e  test    eax, eax
0x18018d020  jnz     short loc_18018D056
0x18018d022  mov     eax, cs:gfTraceToSecondProvider
0x18018d028  test    eax, eax
0x18018d02a  jz      loc_18018D0CA
0x18018d030  call    THStateCheckForTraceOverride
0x18018d035  test    eax, eax
0x18018d037  jnz     short loc_18018D056
0x18018d039  call    ThStateCheckIfTraceToSecondProvier
0x18018d03e  test    eax, eax
0x18018d040  jz      loc_18018D0CA
0x18018d046  mov     r8d, ebx
0x18018d049  mov     edx, edi
0x18018d04b  mov     ecx, esi
0x18018d04d  call    CheckWPPLevelFlagsEnabledForProvider
0x18018d052  test    eax, eax
0x18018d054  jz      short loc_18018D0CA
0x18018d056  mov     eax, cs:gfTraceToSecondProvider
0x18018d05c  test    eax, eax
0x18018d05e  jz      short loc_18018D085
0x18018d060  call    THStateCheckForTraceOverride
0x18018d065  test    eax, eax
0x18018d067  jnz     short loc_18018D082
0x18018d069  call    ThStateCheckIfTraceToSecondProvier
0x18018d06e  test    eax, eax
0x18018d070  jz      short loc_18018D085
0x18018d072  mov     r8d, ebx
0x18018d075  mov     edx, edi
0x18018d077  mov     ecx, esi
0x18018d079  call    CheckWPPLevelFlagsEnabledForProvider
0x18018d07e  test    eax, eax
0x18018d080  jz      short loc_18018D085
0x18018d082  mov     r13d, esi
0x18018d085  call    THStateCheckForTraceOverride
0x18018d08a  test    eax, eax
0x18018d08c  jnz     short loc_18018D0A2
0x18018d08e  mov     r8d, ebx
0x18018d091  mov     edx, edi
0x18018d093  xor     ecx, ecx
0x18018d095  call    CheckWPPLevelFlagsEnabledForProvider
0x18018d09a  xor     ecx, ecx
0x18018d09c  test    eax, eax
0x18018d09e  jnz     short loc_18018D0A2
0x18018d0a0  mov     esi, ecx
0x18018d0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18018d0a9  mov     dword ptr [rsp+2F0h+var_2A0], r15d; char
0x18018d0ae  mov     [rsp+2F0h+var_2A8], r12; __int64
0x18018d0b3  mov     [rsp+2F0h+var_2B0], r14; __int64
0x18018d0b8  mov     rcx, [rcx+10h]; int
0x18018d0bc  mov     [rsp+2F0h+var_2C8], r13d; int
0x18018d0c1  mov     [rsp+2F0h+var_2D0], esi; int
0x18018d0c5  call    WPP_SF_S_guid_d
0x18018d0ca  lea     rcx, [rbp+1F0h+var_210]; this
0x18018d0ce  call    ??1NODE@@QEAA@XZ; NODE::~NODE(void)
0x18018d0d3  mov     eax, r15d
0x18018d0d6  jmp     loc_18018D766
0x18018d0db  xorps   xmm0, xmm0
0x18018d0de  mov     [rbp+1F0h+ObjectAttributes.Length], 30h ; '0'
0x18018d0e5  lea     r9, [rbp+1F0h+PolicyHandle]; PolicyHandle
0x18018d0e9  mov     [rbp+1F0h+ObjectAttributes.RootDirectory], r13
0x18018d0ed  mov     r8d, esi; DesiredAccess
0x18018d0f0  mov     [rbp+1F0h+ObjectAttributes.Attributes], r13d
0x18018d0f4  lea     rdx, [rbp+1F0h+ObjectAttributes]; ObjectAttributes
0x18018d0f8  mov     [rbp+1F0h+ObjectAttributes.ObjectName], r13
0x18018d0fc  xor     ecx, ecx; SystemName
0x18018d0fe  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18018d103  call    cs:__imp_LsaOpenPolicy
0x18018d109  mov     r15d, eax
0x18018d10c  test    eax, eax
0x18018d10e  jns     loc_18018D202
0x18018d114  mov     ecx, edi
0x18018d116  call    IncrementWPPPerfCountersForLevel
0x18018d11b  mov     ebx, 3
0x18018d120  test    eax, eax
0x18018d122  jnz     short loc_18018D171
0x18018d124  call    THStateCheckForTraceOverride
0x18018d129  test    eax, eax
0x18018d12b  jnz     short loc_18018D171
0x18018d12d  mov     r8d, ebx
0x18018d130  mov     edx, edi
0x18018d132  xor     ecx, ecx
0x18018d134  call    CheckWPPLevelFlagsEnabledForProvider
0x18018d139  test    eax, eax
0x18018d13b  jnz     short loc_18018D171
0x18018d13d  mov     eax, cs:gfTraceToSecondProvider
0x18018d143  test    eax, eax
0x18018d145  jz      short loc_18018D0CA
0x18018d147  call    THStateCheckForTraceOverride
0x18018d14c  test    eax, eax
0x18018d14e  jnz     short loc_18018D171
0x18018d150  call    ThStateCheckIfTraceToSecondProvier
0x18018d155  test    eax, eax
0x18018d157  jz      loc_18018D0CA
0x18018d15d  mov     r8d, ebx
  ... truncated ...
```
