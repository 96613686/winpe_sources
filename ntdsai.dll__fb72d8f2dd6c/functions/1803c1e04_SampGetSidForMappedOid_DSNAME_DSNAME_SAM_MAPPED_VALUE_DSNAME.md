# SampGetSidForMappedOid(_DSNAME *,_DSNAME *,SAM_MAPPED_VALUE *,_DSNAME * *)

- ea: `0x1803c1e04`
- end: `0x1803c23be`
- name: `?SampGetSidForMappedOid@@YAJPEAU_DSNAME@@0PEAUSAM_MAPPED_VALUE@@PEAPEAU1@@Z`
- size: `1466`
- prototype: `int(struct _DSNAME *, struct _DSNAME *, struct SAM_MAPPED_VALUE *, struct _DSNAME **)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1803c1b50`
- `0x1803c2594`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x180030af8`
- `0x1800389f0`
- `0x18003dc50`
- `0x1801726c4`
- `0x1803b9960`
- `0x1803c0e88`
- `0x1803c1e04`
- `0x1803e0ae8`
- `0x1803f6ec0`
- `0x1803fc830`
- `0x180424e8c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803c214e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803c214e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803c21b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803c238f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803c21b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803c238f`
- `ntdll!RtlInitUnicodeString` at `0x1803c1fd2`
- `ntdll!RtlInitUnicodeString` at `0x1803c2073`
- `ntdll!RtlInitUnicodeString` at `0x1803c20ef`
- `ntdll!RtlInitUnicodeString` at `0x1803c2113`
- `ntdll!RtlInitUnicodeString` at `0x1803c213f`
- `ntdll!RtlInitUnicodeString` at `0x1803c2164`
- `ntdll!RtlInitUnicodeString` at `0x1803c22e6`
- `ntdll!RtlInitUnicodeString` at `0x1803c230a`
- `ntdll!RtlInitUnicodeString` at `0x1803c2336`
- `ntdll!RtlInitUnicodeString` at `0x1803c2343`
- `ntdll!RtlInitUnicodeString` at `0x1803c1fd2`
- `ntdll!RtlInitUnicodeString` at `0x1803c2073`
- `ntdll!RtlInitUnicodeString` at `0x1803c20ef`
- `ntdll!RtlInitUnicodeString` at `0x1803c2113`
- `ntdll!RtlInitUnicodeString` at `0x1803c213f`
- `ntdll!RtlInitUnicodeString` at `0x1803c2164`
- `ntdll!RtlInitUnicodeString` at `0x1803c22e6`
- `ntdll!RtlInitUnicodeString` at `0x1803c230a`
- `ntdll!RtlInitUnicodeString` at `0x1803c2336`
- `ntdll!RtlInitUnicodeString` at `0x1803c2343`
- `ntdll!RtlValidSid` at `0x1803c22be`
- `ntdll!RtlValidSid` at `0x1803c22be`
- `SAMSRV!SampWriteEventLog` at `0x1803c2021`
- `SAMSRV!SampWriteEventLog` at `0x1803c2044`
- `SAMSRV!SampWriteEventLog` at `0x1803c2094`
- `SAMSRV!SampWriteEventLog` at `0x1803c21a2`
- `SAMSRV!SampWriteEventLog` at `0x1803c2381`
- `SAMSRV!SampWriteEventLog` at `0x1803c2021`
- `SAMSRV!SampWriteEventLog` at `0x1803c2044`
- `SAMSRV!SampWriteEventLog` at `0x1803c2094`
- `SAMSRV!SampWriteEventLog` at `0x1803c21a2`
- `SAMSRV!SampWriteEventLog` at `0x1803c2381`

## pseudocode

```c
__int64 __fastcall SampGetSidForMappedOid(
        struct _DSNAME *a1,
        struct _DSNAME *a2,
        const unsigned __int16 **a3,
        struct _DSNAME **a4)
{
  int v4; // r12d
  int v8; // ebx
  size_t v9; // rbx
  unsigned __int16 *v10; // rax
  const WCHAR *v11; // r14
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // r14d
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // r8
  __int64 v18; // r9
  BOOL v19; // edi
  int v20; // eax
  __int64 v21; // r9
  WCHAR *v22; // r13
  int v23; // eax
  struct _DSNAME *v24; // rdi
  int v25; // eax
  const WCHAR *v26; // rdx
  WCHAR *v27; // rdx
  BOOL v28; // eax
  const WCHAR *v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rcx
  int v32; // r14d
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // r8
  __int64 v36; // r9
  const WCHAR *v37; // rdx
  WCHAR *v38; // rdx
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v42; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v43; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING v44; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp-68h] BYREF
  struct _DSNAME *v46; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING v47; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SourceString[40]; // [rsp+C0h] [rbp-40h] BYREF

  v4 = 0;
  hMem = 0;
  v46 = 0;
  LODWORD(StringSid) = 0;
  DestinationString = 0;
  v44 = 0;
  v43 = 0;
  v42 = 0;
  v47 = 0;
  if ( a4 )
    *a4 = 0;
  if ( SampValidateMappedAttributeSet((struct _SAM_MAPPED_ATTRIBUTE_SET *)a3) )
  {
    v8 = 0;
    if ( *(_DWORD *)a3 )
    {
      v9 = (unsigned int)(*(_DWORD *)a3 + 2);
      v10 = (unsigned __int16 *)MIDL_user_allocate(v9);
      v11 = v10;
      if ( v10 )
      {
        v8 = RtlStringCchCopyNW(v10, v9 >> 1, a3[1], (unsigned __int64)*(unsigned int *)a3 >> 1);
        if ( v8 >= 0 )
        {
          RtlInitUnicodeString(&DestinationString, v11);
          v20 = SampDsLookupObjectByAlternateId(a1, 591260, &DestinationString, &hMem);
          v22 = (WCHAR *)hMem;
          v8 = v20;
          if ( v20 >= 0 )
          {
            v8 = SampDsReadSingleAttribute(hMem, 591875, &v46, &StringSid);
            if ( v8 >= 0 )
            {
              v23 = SampAmIGC();
              v24 = v46;
              if ( v23 && (v25 = SampEnforceMappedGroupChecks(v46), v8 = v25, v25 < 0) )
              {
                StringSid = 0;
                if ( v25 == -1073741722 || v25 == -1073741141 || v25 == -1073741100 || v25 == -1073700729 )
                {
                  RtlInitUnicodeString(&v44, v22 + 28);
                  if ( !*((_DWORD *)v24 + 13)
                    || (v26 = (const WCHAR *)((char *)v24 + 56), v24 == (struct _DSNAME *)-56LL) )
                  {
                    v26 = L"N/A";
                  }
                  RtlInitUnicodeString(&v43, v26);
                  DsUuidToStructuredStringCchW((char *)v24 + 8, SourceString, 40);
                  v27 = (WCHAR *)L"N/A";
                  if ( SourceString[0] != 48 )
                    v27 = SourceString;
                  RtlInitUnicodeString(&v42, v27);
                  v28 = ConvertSidToStringSidW((char *)v24 + 24, &StringSid);
                  v29 = StringSid;
                  if ( !v28 )
                    v29 = L"N/A";
                  RtlInitUnicodeString(&v47, v29);
                  SampWriteEventLog(SAMMSG_INVALID_OID_TO_GROUP_LINK, L"uuuuud", &DestinationString, &v44);
                  if ( StringSid )
                    LocalFree(StringSid);
                }
                v32 = 1;
                if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
                  || (unsigned int)THStateCheckForTraceOverride(v31, v30)
                  || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
                  || gfTraceToSecondProvider
                  && ((unsigned int)THStateCheckForTraceOverride(v31, v30)
                   || (unsigned int)ThStateCheckIfTraceToSecondProvier(v31, v30, v33, v34)
                   && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
                {
                  if ( gfTraceToSecondProvider
                    && ((unsigned int)THStateCheckForTraceOverride(v31, v30)
                     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v31, v30, v35, v36)
                     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
                  {
                    v4 = 1;
                  }
                  if ( !(unsigned int)THStateCheckForTraceOverride(v31, v30)
                    && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
                  {
                    v32 = 0;
                  }
                  WPP_SF__DS_NAME_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    522783379,
                    2,
                    13,
                    v32,
                    v4,
                    23,
                    &WPP_b833ca7a2b883f3b7342df060f8a2301_Traceguids,
                    (__int64)v24,
                    v8);
                }
              }
              else if ( *((_DWORD *)v24 + 1) && RtlValidSid((char *)v24 + 24) )
              {
                if ( a4 )
                  *a4 = v24;
              }
              else
              {
                v8 = -1073741704;
                RtlInitUnicodeString(&v44, v22 + 28);
                if ( !*((_DWORD *)v24 + 13) || (v37 = (const WCHAR *)((char *)v24 + 56), v24 == (struct _DSNAME *)-56LL) )
                  v37 = L"N/A";
                RtlInitUnicodeString(&v43, v37);
                DsUuidToStructuredStringCchW((char *)v24 + 8, SourceString, 40);
                v38 = (WCHAR *)L"N/A";
                if ( SourceString[0] != 48 )
                  v38 = SourceString;
                RtlInitUnicodeString(&v42, v38);
                RtlInitUnicodeString(&v47, L"N/A");
                SampWriteEventLog(SAMMSG_INVALID_OID_TO_GROUP_LINK, L"uuuuud", &DestinationString, &v44);
              }
            }
            else
            {
              RtlInitUnicodeString(&v44, v22 + 28);
              SampWriteEventLog(SAMMSG_NO_OID_TO_GROUP_LINK_ATTRIBUTE, L"uud", &DestinationString, &v44);
            }
          }
          else if ( v20 == -1073741771 )
          {
            SampWriteEventLog(SAMMSG_DUPLICATE_OID_OBJECT, L"u", &DestinationString, v21);
          }
          else if ( v20 == -1073741275 )
          {
            SampWriteEventLog(SAMMSG_OID_NOT_FOUND, L"ud", &DestinationString, 3221226021LL);
            v8 = -1073700728;
          }
          if ( v22 )
            LocalFree(v22);
        }
        else
        {
          v14 = 1;
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
            || (unsigned int)THStateCheckForTraceOverride(v13, v12)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v13, v12)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v13, v12, v15, v16)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
          {
            v19 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v13, v12)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v13, v12, v17, v18)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
            if ( !(unsigned int)THStateCheckForTraceOverride(v13, v12)
              && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
            {
              v14 = 0;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              522783255,
              2,
              13,
              v14,
              v19,
              22,
              (__int64)&WPP_b833ca7a2b883f3b7342df060f8a2301_Traceguids);
          }
        }
      }
      else
      {
        return (unsigned int)-1073741801;
      }
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1803c1e04  mov     [rsp-8+arg_8], rbx
0x1803c1e09  push    rbp
0x1803c1e0a  push    rsi
0x1803c1e0b  push    rdi
0x1803c1e0c  push    r12
0x1803c1e0e  push    r13
0x1803c1e10  push    r14
0x1803c1e12  push    r15
0x1803c1e14  lea     rbp, [rsp-20h]
0x1803c1e19  sub     rsp, 120h
0x1803c1e20  mov     rax, cs:__security_cookie
0x1803c1e27  xor     rax, rsp
0x1803c1e2a  mov     [rbp+50h+var_40], rax
0x1803c1e2e  xor     r12d, r12d
0x1803c1e31  xorps   xmm0, xmm0
0x1803c1e34  mov     [rbp+50h+hMem], r12
0x1803c1e38  xorps   xmm1, xmm1
0x1803c1e3b  mov     [rbp+50h+var_B0], r12
0x1803c1e3f  mov     rsi, r9
0x1803c1e42  mov     dword ptr [rsp+150h+StringSid], r12d
0x1803c1e47  mov     rdi, r8
0x1803c1e4a  mov     r15, rcx
0x1803c1e4d  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x1803c1e52  movups  xmmword ptr [rbp+50h+var_C8.Length], xmm1
0x1803c1e56  movups  xmmword ptr [rsp+150h+var_D8.Length], xmm0
0x1803c1e5b  movups  xmmword ptr [rsp+150h+var_E8.Length], xmm1
0x1803c1e60  movups  xmmword ptr [rbp+50h+var_A8.Length], xmm0
0x1803c1e64  test    r9, r9
0x1803c1e67  jz      short loc_1803C1E6C
0x1803c1e69  mov     [r9], r12
0x1803c1e6c  mov     rcx, rdi; struct _SAM_MAPPED_ATTRIBUTE_SET *
0x1803c1e6f  call    ?SampValidateMappedAttributeSet@@YAEPEAU_SAM_MAPPED_ATTRIBUTE_SET@@@Z; SampValidateMappedAttributeSet(_SAM_MAPPED_ATTRIBUTE_SET *)
0x1803c1e74  test    al, al
0x1803c1e76  jnz     short loc_1803C1E82
0x1803c1e78  mov     ebx, 0C000000Dh
0x1803c1e7d  jmp     loc_1803C2395
0x1803c1e82  mov     eax, [rdi]
0x1803c1e84  mov     ebx, r12d
0x1803c1e87  test    eax, eax
0x1803c1e89  jz      loc_1803C2395
0x1803c1e8f  add     eax, 2
0x1803c1e92  mov     ecx, eax; size
0x1803c1e94  mov     ebx, eax
0x1803c1e96  call    MIDL_user_allocate
0x1803c1e9b  mov     r14, rax
0x1803c1e9e  test    rax, rax
0x1803c1ea1  jnz     short loc_1803C1EAD
0x1803c1ea3  mov     ebx, 0C0000017h
0x1803c1ea8  jmp     loc_1803C2395
0x1803c1ead  mov     r9d, [rdi]
0x1803c1eb0  mov     rcx, r14; unsigned __int16 *
0x1803c1eb3  mov     r8, [rdi+8]; unsigned __int16 *
0x1803c1eb7  shr     rbx, 1
0x1803c1eba  shr     r9, 1; unsigned __int64
0x1803c1ebd  mov     rdx, rbx; unsigned __int64
0x1803c1ec0  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1803c1ec5  mov     ebx, eax
0x1803c1ec7  test    eax, eax
0x1803c1ec9  jns     loc_1803C1FCA
0x1803c1ecf  mov     esi, 2
0x1803c1ed4  mov     ecx, esi
0x1803c1ed6  call    IncrementWPPPerfCountersForLevel
0x1803c1edb  lea     r15d, [rsi+0Bh]
0x1803c1edf  lea     r14d, [rsi-1]
0x1803c1ee3  test    eax, eax
0x1803c1ee5  jnz     short loc_1803C1F39
0x1803c1ee7  call    THStateCheckForTraceOverride
0x1803c1eec  test    eax, eax
0x1803c1eee  jnz     short loc_1803C1F39
0x1803c1ef0  mov     r8d, r15d
0x1803c1ef3  mov     edx, esi
0x1803c1ef5  xor     ecx, ecx
0x1803c1ef7  call    CheckWPPLevelFlagsEnabledForProvider
0x1803c1efc  test    eax, eax
0x1803c1efe  jnz     short loc_1803C1F39
0x1803c1f00  mov     eax, cs:gfTraceToSecondProvider
0x1803c1f06  test    eax, eax
0x1803c1f08  jz      loc_1803C2395
0x1803c1f0e  call    THStateCheckForTraceOverride
0x1803c1f13  test    eax, eax
0x1803c1f15  jnz     short loc_1803C1F39
0x1803c1f17  call    ThStateCheckIfTraceToSecondProvier
0x1803c1f1c  test    eax, eax
0x1803c1f1e  jz      loc_1803C2395
0x1803c1f24  mov     r8d, r15d
0x1803c1f27  mov     edx, esi
0x1803c1f29  mov     ecx, r14d
0x1803c1f2c  call    CheckWPPLevelFlagsEnabledForProvider
0x1803c1f31  test    eax, eax
0x1803c1f33  jz      loc_1803C2395
0x1803c1f39  mov     eax, cs:gfTraceToSecondProvider
0x1803c1f3f  test    eax, eax
0x1803c1f41  jz      short loc_1803C1F6B
0x1803c1f43  call    THStateCheckForTraceOverride
0x1803c1f48  test    eax, eax
0x1803c1f4a  jnz     short loc_1803C1F66
0x1803c1f4c  call    ThStateCheckIfTraceToSecondProvier
0x1803c1f51  test    eax, eax
0x1803c1f53  jz      short loc_1803C1F6B
0x1803c1f55  mov     r8d, r15d
0x1803c1f58  mov     edx, esi
0x1803c1f5a  mov     ecx, r14d
0x1803c1f5d  call    CheckWPPLevelFlagsEnabledForProvider
0x1803c1f62  test    eax, eax
0x1803c1f64  jz      short loc_1803C1F6B
0x1803c1f66  mov     edi, r14d
0x1803c1f69  jmp     short loc_1803C1F6E
0x1803c1f6b  mov     edi, r12d
0x1803c1f6e  call    THStateCheckForTraceOverride
0x1803c1f73  test    eax, eax
0x1803c1f75  jnz     short loc_1803C1F8A
0x1803c1f77  mov     r8d, r15d
0x1803c1f7a  mov     edx, esi
0x1803c1f7c  xor     ecx, ecx
0x1803c1f7e  call    CheckWPPLevelFlagsEnabledForProvider
0x1803c1f83  test    eax, eax
0x1803c1f85  jnz     short loc_1803C1F8A
0x1803c1f87  mov     r14d, r12d
0x1803c1f8a  mov     rcx, cs:WPP_GLOBAL_Control
0x1803c1f91  lea     rax, WPP_b833ca7a2b883f3b7342df060f8a2301_Traceguids
0x1803c1f98  mov     dword ptr [rsp+150h+var_110], ebx
0x1803c1f9c  mov     r9d, r15d
0x1803c1f9f  mov     [rsp+150h+var_118], rax
0x1803c1fa4  mov     r8d, esi
0x1803c1fa7  mov     [rsp+150h+var_120], 16h
0x1803c1fae  mov     edx, 1F290A17h
0x1803c1fb3  mov     rcx, [rcx+10h]
0x1803c1fb7  mov     [rsp+150h+var_128], edi
0x1803c1fbb  mov     [rsp+150h+var_130], r14d
0x1803c1fc0  call    WPP_SF__ATTRTYP_LOG_
0x1803c1fc5  jmp     loc_1803C2395
0x1803c1fca  mov     rdx, r14; SourceString
0x1803c1fcd  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x1803c1fd2  call    cs:__imp_RtlInitUnicodeString
0x1803c1fd8  lea     r9, [rbp+50h+hMem]
0x1803c1fdc  mov     edx, 9059Ch
0x1803c1fe1  lea     r8, [rsp+150h+DestinationString]
0x1803c1fe6  mov     rcx, r15
0x1803c1fe9  call    SampDsLookupObjectByAlternateId
0x1803c1fee  mov     r13, [rbp+50h+hMem]
0x1803c1ff2  mov     ebx, eax
0x1803c1ff4  test    eax, eax
0x1803c1ff6  jns     short loc_1803C204F
0x1803c1ff8  cmp     eax, 0C0000035h
0x1803c1ffd  jz      short loc_1803C2031
0x1803c1fff  mov     r9d, 0C0000225h
0x1803c2005  cmp     eax, r9d
0x1803c2008  jnz     loc_1803C2387
0x1803c200e  lea     r8, [rsp+150h+DestinationString]
0x1803c2013  lea     rdx, aUd; "ud"
0x1803c201a  lea     rcx, SAMMSG_OID_NOT_FOUND
0x1803c2021  call    cs:__imp_SampWriteEventLog
0x1803c2027  mov     ebx, 0C000A088h
0x1803c202c  jmp     loc_1803C2387
0x1803c2031  lea     r8, [rsp+150h+DestinationString]
0x1803c2036  lea     rdx, aU; "u"
0x1803c203d  lea     rcx, SAMMSG_DUPLICATE_OID_OBJECT
0x1803c2044  call    cs:__imp_SampWriteEventLog
0x1803c204a  jmp     loc_1803C2387
0x1803c204f  lea     r9, [rsp+150h+StringSid]
0x1803c2054  mov     edx, 90803h
0x1803c2059  lea     r8, [rbp+50h+var_B0]
0x1803c205d  mov     rcx, r13
0x1803c2060  call    SampDsReadSingleAttribute
0x1803c2065  mov     ebx, eax
0x1803c2067  test    eax, eax
0x1803c2069  jns     short loc_1803C209F
0x1803c206b  lea     rdx, [r13+38h]; SourceString
0x1803c206f  lea     rcx, [rbp+50h+var_C8]; DestinationString
0x1803c2073  call    cs:__imp_RtlInitUnicodeString
0x1803c2079  lea     r9, [rbp+50h+var_C8]
0x1803c207d  mov     [rsp+150h+var_130], ebx
0x1803c2081  lea     r8, [rsp+150h+DestinationString]
0x1803c2086  lea     rdx, aUud; "uud"
0x1803c208d  lea     rcx, SAMMSG_NO_OID_TO_GROUP_LINK_ATTRIBUTE
0x1803c2094  call    cs:__imp_SampWriteEventLog
0x1803c209a  jmp     loc_1803C2387
0x1803c209f  call    SampAmIGC
0x1803c20a4  mov     rdi, [rbp+50h+var_B0]
0x1803c20a8  test    eax, eax
0x1803c20aa  jz      loc_1803C22B4
0x1803c20b0  mov     rcx, rdi; struct _DSNAME *
0x1803c20b3  call    SampEnforceMappedGroupChecks
0x1803c20b8  mov     ebx, eax
0x1803c20ba  test    eax, eax
0x1803c20bc  jns     loc_1803C22B4
0x1803c20c2  mov     [rsp+150h+StringSid], r12
0x1803c20c7  cmp     eax, 0C0000066h
0x1803c20cc  jz      short loc_1803C20E7
0x1803c20ce  cmp     eax, 0C00002ABh
0x1803c20d3  jz      short loc_1803C20E7
0x1803c20d5  cmp     eax, 0C00002D4h
0x1803c20da  jz      short loc_1803C20E7
0x1803c20dc  cmp     eax, 0C000A087h
0x1803c20e1  jnz     loc_1803C21B8
0x1803c20e7  lea     rdx, [r13+38h]; SourceString
0x1803c20eb  lea     rcx, [rbp+50h+var_C8]; DestinationString
0x1803c20ef  call    cs:__imp_RtlInitUnicodeString
0x1803c20f5  lea     rsi, aNA_0; "N/A"
0x1803c20fc  cmp     [rdi+34h], r12d
0x1803c2100  jbe     short loc_1803C210B
0x1803c2102  lea     rdx, [rdi+38h]
0x1803c2106  test    rdx, rdx
0x1803c2109  jnz     short loc_1803C210E
0x1803c210b  mov     rdx, rsi; SourceString
0x1803c210e  lea     rcx, [rsp+150h+var_D8]; DestinationString
0x1803c2113  call    cs:__imp_RtlInitUnicodeString
0x1803c2119  lea     rcx, [rdi+8]
0x1803c211d  mov     r8d, 28h ; '('
0x1803c2123  lea     rdx, [rbp+50h+SourceString]
0x1803c2127  call    DsUuidToStructuredStringCchW
0x1803c212c  cmp     [rbp+50h+SourceString], 30h ; '0'
0x1803c2131  lea     rcx, [rsp+150h+var_E8]; DestinationString
0x1803c2136  mov     rdx, rsi
0x1803c2139  jz      short loc_1803C213F
0x1803c213b  lea     rdx, [rbp+50h+SourceString]; SourceString
0x1803c213f  call    cs:__imp_RtlInitUnicodeString
0x1803c2145  lea     rcx, [rdi+18h]; Sid
0x1803c2149  lea     rdx, [rsp+150h+StringSid]; StringSid
0x1803c214e  call    cs:__imp_ConvertSidToStringSidW
0x1803c2154  mov     rdx, [rsp+150h+StringSid]
0x1803c2159  lea     rcx, [rbp+50h+var_A8]; DestinationString
0x1803c215d  test    eax, eax
0x1803c215f  jnz     short loc_1803C2164
0x1803c2161  mov     rdx, rsi; SourceString
0x1803c2164  call    cs:__imp_RtlInitUnicodeString
0x1803c216a  mov     dword ptr [rsp+150h+var_118], ebx
0x1803c216e  lea     rax, [rbp+50h+var_A8]
0x1803c2172  mov     qword ptr [rsp+150h+var_120], rax
0x1803c2177  lea     r9, [rbp+50h+var_C8]
0x1803c217b  lea     rax, [rsp+150h+var_E8]
0x1803c2180  mov     qword ptr [rsp+150h+var_128], rax
0x1803c2185  lea     r8, [rsp+150h+DestinationString]
0x1803c218a  lea     rax, [rsp+150h+var_D8]
0x1803c218f  lea     rdx, aUuuuud; "uuuuud"
0x1803c2196  mov     qword ptr [rsp+150h+var_130], rax
0x1803c219b  lea     rcx, SAMMSG_INVALID_OID_TO_GROUP_LINK
0x1803c21a2  call    cs:__imp_SampWriteEventLog
0x1803c21a8  mov     rcx, [rsp+150h+StringSid]; hMem
0x1803c21ad  test    rcx, rcx
0x1803c21b0  jz      short loc_1803C21B8
0x1803c21b2  call    cs:__imp_LocalFree
0x1803c21b8  mov     esi, 2
0x1803c21bd  mov     ecx, esi
0x1803c21bf  call    IncrementWPPPerfCountersForLevel
0x1803c21c4  lea     r15d, [rsi+0Bh]
0x1803c21c8  lea     r14d, [rsi-1]
0x1803c21cc  test    eax, eax
0x1803c21ce  jnz     short loc_1803C2222
0x1803c21d0  call    THStateCheckForTraceOverride
0x1803c21d5  test    eax, eax
0x1803c21d7  jnz     short loc_1803C2222
0x1803c21d9  mov     r8d, r15d
0x1803c21dc  mov     edx, esi
0x1803c21de  xor     ecx, ecx
0x1803c21e0  call    CheckWPPLevelFlagsEnabledForProvider
0x1803c21e5  test    eax, eax
0x1803c21e7  jnz     short loc_1803C2222
0x1803c21e9  mov     eax, cs:gfTraceToSecondProvider
0x1803c21ef  test    eax, eax
0x1803c21f1  jz      loc_1803C2387
0x1803c21f7  call    THStateCheckForTraceOverride
0x1803c21fc  test    eax, eax
0x1803c21fe  jnz     short loc_1803C2222
0x1803c2200  call    ThStateCheckIfTraceToSecondProvier
0x1803c2205  test    eax, eax
0x1803c2207  jz      loc_1803C2387
0x1803c220d  mov     r8d, r15d
0x1803c2210  mov     edx, esi
0x1803c2212  mov     ecx, r14d
0x1803c2215  call    CheckWPPLevelFlagsEnabledForProvider
0x1803c221a  test    eax, eax
0x1803c221c  jz      loc_1803C2387
0x1803c2222  mov     eax, cs:gfTraceToSecondProvider
0x1803c2228  test    eax, eax
0x1803c222a  jz      short loc_1803C2252
0x1803c222c  call    THStateCheckForTraceOverride
0x1803c2231  test    eax, eax
0x1803c2233  jnz     short loc_1803C224F
0x1803c2235  call    ThStateCheckIfTraceToSecondProvier
0x1803c223a  test    eax, eax
0x1803c223c  jz      short loc_1803C2252
0x1803c223e  mov     r8d, r15d
0x1803c2241  mov     edx, esi
0x1803c2243  mov     ecx, r14d
0x1803c2246  call    CheckWPPLevelFlagsEnabledForProvider
0x1803c224b  test    eax, eax
0x1803c224d  jz      short loc_1803C2252
0x1803c224f  mov     r12d, r14d
0x1803c2252  call    THStateCheckForTraceOverride
0x1803c2257  test    eax, eax
0x1803c2259  jnz     short loc_1803C226E
0x1803c225b  mov     r8d, r15d
0x1803c225e  mov     edx, esi
0x1803c2260  xor     ecx, ecx
0x1803c2262  call    CheckWPPLevelFlagsEnabledForProvider
0x1803c2267  test    eax, eax
0x1803c2269  jnz     short loc_1803C226E
0x1803c226b  xor     r14d, r14d
0x1803c226e  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
