# LsapDbLookupNamesInLocalDomainEx(ulong,ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_TRUST_INFORMATION_EX *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,ulong *,ulong *)

- ea: `0x18001cc60`
- end: `0x18001ddb3`
- name: `?LsapDbLookupNamesInLocalDomainEx@@YAJKKPEAU_LSAPR_UNICODE_STRING@@0PEAU_LSAPR_TRUST_INFORMATION_EX@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAK4@Z`
- size: `4435`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_UNICODE_STRING *, PSID, struct _LSAPR_REFERENCED_DOMAIN_LIST *, struct _LSAPR_TRANSLATED_SIDS_EX2 *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b1f4`
- `0x18001cbe0`

## callees

- `0x180011278`
- `0x1800162a8`
- `0x18001cc60`
- `0x18001ddc0`
- `0x18001ecf0`
- `0x18001f290`
- `0x18001f340`
- `0x1800364d0`
- `0x1800385a8`
- `0x1800765a8`
- `0x18007fbd0`
- `0x18008ff30`
- `0x1800ada18`
- `0x1800bbbfc`
- `0x1800bd6e0`
- `0x1801236b4`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d2c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d2df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d9a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d9c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001da71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dabf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dc80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dcbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dcd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dd1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dd38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d2c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d2df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d9a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d9c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001da71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dabf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dc80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dcbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dcd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dd1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dd38`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d1c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d23b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d37c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d3f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d456`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d5b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d61f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d679`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d799`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d1c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d23b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d37c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d3f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d456`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d5b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d61f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d679`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d799`
- `ntdll!RtlFreeHeap` at `0x18001d0ef`
- `ntdll!RtlFreeHeap` at `0x18001d112`
- `ntdll!RtlFreeHeap` at `0x18001d0ef`
- `ntdll!RtlFreeHeap` at `0x18001d112`
- `ntdll!RtlEqualDomainName` at `0x18001d288`
- `ntdll!RtlEqualDomainName` at `0x18001d288`
- `ntdll!RtlAllocateHeap` at `0x18001cd86`
- `ntdll!RtlAllocateHeap` at `0x18001cdbc`
- `ntdll!RtlAllocateHeap` at `0x18001cd86`
- `ntdll!RtlAllocateHeap` at `0x18001cdbc`
- `ntdll!RtlCopyUnicodeString` at `0x18001d419`
- `ntdll!RtlCopyUnicodeString` at `0x18001d642`
- `ntdll!RtlCopyUnicodeString` at `0x18001d419`
- `ntdll!RtlCopyUnicodeString` at `0x18001d642`
- `ntdll!RtlLengthSid` at `0x18001d43c`
- `ntdll!RtlLengthSid` at `0x18001d65f`
- `ntdll!RtlLengthSid` at `0x18001d77f`
- `ntdll!RtlLengthSid` at `0x18001d43c`
- `ntdll!RtlLengthSid` at `0x18001d65f`
- `ntdll!RtlLengthSid` at `0x18001d77f`
- `ntdll!RtlEqualSid` at `0x18001d934`
- `ntdll!RtlEqualSid` at `0x18001d952`
- `ntdll!RtlEqualSid` at `0x18001d934`
- `ntdll!RtlEqualSid` at `0x18001d952`
- `DNSAPI!DnsNameCompare_W` at `0x18001d2a5`
- `DNSAPI!DnsNameCompare_W` at `0x18001d2a5`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFreeRealmList` at `0x18001d169`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFreeRealmList` at `0x18001d169`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_ULONG_ARRAY` at `0x18001d131`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_ULONG_ARRAY` at `0x18001d150`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_ULONG_ARRAY` at `0x18001d131`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_ULONG_ARRAY` at `0x18001d150`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrCloseHandle` at `0x18001dd72`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrCloseHandle` at `0x18001dd72`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrLookupNamesInDomain2` at `0x18001d540`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrLookupNamesInDomain2` at `0x18001d540`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFreeVoid` at `0x18001d7dd`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFreeVoid` at `0x18001d7dd`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrRidToSid` at `0x18001d754`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrRidToSid` at `0x18001d754`

## pseudocode

```c
__int64 __fastcall LsapDbLookupNamesInLocalDomainEx(
        unsigned int a1,
        unsigned int a2,
        struct _LSAPR_UNICODE_STRING *a3,
        struct _LSAPR_UNICODE_STRING *a4,
        size_t a5,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a6,
        struct _LSAPR_TRANSLATED_SIDS_EX2 *a7,
        unsigned int *a8,
        unsigned int *a9)
{
  struct _RPC_UNICODE_STRING *Heap; // r15
  int v10; // r12d
  struct _UNICODE_STRING *v12; // rsi
  int InformationPolicy; // ebx
  _DWORD *v14; // r14
  __int64 v15; // r8
  __int64 Buffer; // rcx
  unsigned int v17; // edx
  PVOID ProcessHeap; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  bool v21; // zf
  size_t v22; // rcx
  char *v23; // rax
  unsigned __int64 v24; // rdx
  __int64 i; // rdx
  struct _LSAPR_TRANSLATED_SIDS_EX2 *v26; // rdi
  int v27; // eax
  __m128i si128; // xmm6
  unsigned int v29; // edx
  unsigned int v30; // r11d
  __int64 v31; // r10
  __int64 v32; // r12
  __m128i v33; // xmm5
  __m128i v34; // xmm4
  __m128i v35; // xmm2
  __m128i v36; // xmm1
  __m128i v37; // xmm3
  __int64 v38; // rax
  __m128i v39; // xmm0
  __m128i v40; // xmm4
  __m128i v41; // xmm4
  unsigned int v42; // eax
  unsigned int *v43; // rsi
  unsigned int v44; // r11d
  __int64 v45; // r10
  __int64 v46; // r13
  __m128i v47; // xmm5
  __m128i v48; // xmm4
  __m128i v49; // xmm2
  __m128i v50; // xmm1
  __m128i v51; // xmm3
  __int64 v52; // rax
  __m128i v53; // xmm0
  __m128i v54; // xmm4
  __m128i v55; // xmm4
  unsigned int v56; // eax
  LsaHandleCache *v57; // rcx
  WCHAR *v59; // rax
  unsigned __int64 Length; // rdx
  int v61; // eax
  struct _LSAPR_REFERENCED_DOMAIN_LIST *v62; // rbx
  void *v63; // rdx
  int v64; // eax
  struct _UNICODE_STRING *v65; // r8
  int v66; // ecx
  unsigned int v67; // ecx
  PUNICODE_STRING v68; // rcx
  const void *v69; // r9
  int v70; // eax
  unsigned int v71; // r8d
  HLOCAL v72; // rax
  HLOCAL v73; // rax
  struct _LSAPR_REFERENCED_DOMAIN_LIST *v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // rax
  struct _LSA_TRANSLATED_SID_EX2 *v77; // rdi
  int v78; // eax
  struct _LSAPR_REFERENCED_DOMAIN_LIST *v79; // rdi
  PSID v80; // rdx
  int v81; // ebx
  int v82; // esi
  unsigned int v83; // esi
  unsigned int v84; // ebx
  void *v85; // rax
  void *v86; // rcx
  HLOCAL v87; // rax
  PSID v88; // rsi
  HLOCAL v89; // rax
  __int64 v90; // rax
  __int64 j; // rdi
  __int64 v92; // rsi
  unsigned int *v93; // rax
  unsigned int v94; // ebx
  __int64 v95; // rdx
  __int64 v96; // r8
  HLOCAL v97; // rax
  void *v98; // rcx
  void *v99; // rcx
  __int64 v100; // rdi
  void *v101; // rcx
  int v102; // eax
  __int64 v103; // rdx
  unsigned __int16 *v104; // rcx
  __int64 v105; // rax
  char v106; // [rsp+30h] [rbp-C1h]
  char v107; // [rsp+31h] [rbp-C0h]
  unsigned int v108; // [rsp+34h] [rbp-BDh]
  int v109; // [rsp+38h] [rbp-B9h] BYREF
  size_t Size; // [rsp+40h] [rbp-B1h]
  __int64 v111; // [rsp+48h] [rbp-A9h]
  PUNICODE_STRING DomainName1; // [rsp+50h] [rbp-A1h]
  PCWSTR pName2; // [rsp+58h] [rbp-99h]
  int v114; // [rsp+60h] [rbp-91h]
  int v115; // [rsp+64h] [rbp-8Dh]
  _BYTE DestinationString[24]; // [rsp+68h] [rbp-89h] BYREF
  PCWSTR pName1; // [rsp+80h] [rbp-71h]
  UNICODE_STRING SourceString; // [rsp+88h] [rbp-69h] BYREF
  PSID Sid; // [rsp+98h] [rbp-59h]
  struct _LSA_TRANSLATED_SID_EX2 *v120; // [rsp+A0h] [rbp-51h]
  __int128 v121; // [rsp+A8h] [rbp-49h] BYREF
  __int64 v122; // [rsp+B8h] [rbp-39h] BYREF
  __int128 v123; // [rsp+C0h] [rbp-31h] BYREF
  __int128 v124; // [rsp+D0h] [rbp-21h] BYREF

  Heap = 0;
  v122 = 0;
  v10 = -1;
  Sid = 0;
  v109 = -1;
  v121 = 0;
  v123 = 0;
  SourceString = 0;
  v124 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 25, WPP_f0978fc1336a326ebe269f72ca0dc488_Traceguids);
  v12 = (struct _UNICODE_STRING *)a5;
  LODWORD(v121) = 0;
  SourceString = *(UNICODE_STRING *)(a5 + 16);
  Sid = *(PSID *)(a5 + 32);
  *((_QWORD *)&v121 + 1) = 0;
  LODWORD(v123) = 0;
  *((_QWORD *)&v123 + 1) = 0;
  pName2 = 0;
  pName1 = 0;
  a5 = 0;
  if ( LsapSamOpened == 1 )
  {
    InformationPolicy = 0;
  }
  else
  {
    InformationPolicy = LsapWaitForSamForAwhile();
    if ( InformationPolicy < 0 )
      goto LABEL_193;
    InformationPolicy = LsarQueryInformationPolicy(LsapPolicyHandle, PolicyAccountDomainInformation);
    if ( InformationPolicy >= 0 )
    {
      if ( LsapProductType != NtProductLanManNt
        || (InformationPolicy = LsarQueryInformationPolicy(LsapPolicyHandle, PolicyLocalAccountDomainInformation),
            InformationPolicy >= 0) )
      {
        InformationPolicy = LsapSamExtConnect(v104, (void **)&a5, 1u, 1u);
        if ( InformationPolicy >= 0 )
        {
          InformationPolicy = LsapSamExtOpenDomain(
                                (void *)a5,
                                0xF07FFu,
                                *((struct _RPC_SID **)pName2 + 2),
                                &LsapAccountDomainHandle);
          if ( InformationPolicy >= 0 )
          {
            InformationPolicy = LsapSamExtOpenDomain(
                                  (void *)a5,
                                  0xF07FFu,
                                  *((struct _RPC_SID **)WellKnownSids + 84),
                                  &LsapBuiltinDomainHandle);
            if ( InformationPolicy >= 0 )
            {
              if ( LsapProductType == NtProductLanManNt
                && (InformationPolicy = LsapSamExtOpenDomain(
                                          (void *)a5,
                                          0xF07FFu,
                                          *((struct _RPC_SID **)pName1 + 2),
                                          &LsapLocalAccountDomainHandle),
                    InformationPolicy < 0) )
              {
                LsapSamExtCloseHandle(&LsapAccountDomainHandle);
                LsapSamExtCloseHandle(&LsapBuiltinDomainHandle);
              }
              else
              {
                LsapSamOpened = 1;
              }
            }
            else
            {
              LsapSamExtCloseHandle(&LsapAccountDomainHandle);
            }
          }
        }
      }
    }
    if ( a5 )
      LsapSamExtCloseHandle((void **)&a5);
    if ( InformationPolicy < 0 )
    {
LABEL_193:
      v57 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x40) == 0 )
        return (unsigned int)InformationPolicy;
      v103 = 26;
      goto LABEL_184;
    }
  }
  v14 = 0;
  v15 = 0;
  v111 = 0;
  Buffer = *a9;
  v17 = *a8;
  if ( *a8 + (unsigned int)Buffer > a2 )
  {
    InformationPolicy = -1073741811;
    goto LABEL_136;
  }
  if ( !(_DWORD)Buffer )
    goto LABEL_18;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  v111 = *((_QWORD *)a7 + 1);
  a5 = a2 - v17;
  Heap = (struct _RPC_UNICODE_STRING *)RtlAllocateHeap(ProcessHeap, 8u, 16LL * (unsigned int)a5);
  if ( !Heap )
  {
    InformationPolicy = -1073741670;
LABEL_135:
    v15 = v111;
LABEL_136:
    for ( i = 0; (unsigned int)i < (unsigned int)v121; *(_DWORD *)(v15 + 8 * v105 + 16) = -1 )
    {
      Buffer = (unsigned int)v14[i];
      i = (unsigned int)(i + 1);
      v105 = 3 * Buffer;
      *(_DWORD *)(v15 + 8 * v105) = 8;
    }
    if ( v122 )
    {
      SamrCloseHandle(&v122);
      v122 = 0;
    }
    goto LABEL_139;
  }
  v14 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 4 * a5);
  if ( !v14 )
  {
    InformationPolicy = -1073741670;
    goto LABEL_135;
  }
  v19 = 0;
  Buffer = 0;
  v108 = 0;
  v114 = 0;
  if ( !a2 )
    goto LABEL_18;
  v20 = v111;
  do
  {
    v21 = *(_DWORD *)(v20 + 24 * Buffer) == 8;
    v120 = (struct _LSA_TRANSLATED_SID_EX2 *)(v20 + 24 * Buffer);
    if ( !v21 )
      goto LABEL_15;
    v22 = 16 * Buffer;
    v23 = (char *)a3 + v22;
    Size = v22;
    DomainName1 = (PUNICODE_STRING)((char *)a3 + v22);
    v24 = *(unsigned __int16 *)((char *)a3 + v22);
    if ( !(_WORD)v24 )
    {
      a5 = (size_t)a4 + v22;
      if ( !*(_WORD *)((char *)a4 + v22) )
        goto LABEL_14;
      if ( !(unsigned __int8)LsapCompareDomainNames((PUNICODE_STRING)((char *)a4 + v22), v12, v12 + 1) )
      {
        v20 = v111;
        *((_OWORD *)Heap + v108) = *(_OWORD *)a5;
        v14[v108] = v114;
        v19 = ++v108;
        goto LABEL_15;
      }
LABEL_172:
      v102 = LsapDbLookupTranslateNameDomain((struct _LSAPR_TRUST_INFORMATION *)&SourceString, v120, a6, &v109);
      v10 = v109;
      InformationPolicy = v102;
      if ( v102 >= 0 )
      {
        ++*a8;
LABEL_170:
        v20 = v111;
LABEL_14:
        v19 = v108;
        goto LABEL_15;
      }
      goto LABEL_164;
    }
    a5 = (size_t)(v23 + 8);
    if ( *((_WORD *)v23 + 1) <= (unsigned __int16)v24 )
    {
      a5 = (size_t)(v23 + 8);
LABEL_58:
      v59 = (WCHAR *)LocalAlloc(0x40u, v24 + 2);
      pName1 = v59;
      if ( !v59 )
        goto LABEL_170;
      v106 = 1;
      memcpy_0(v59, *(const void **)a5, DomainName1->Length);
      pName1[(unsigned __int64)DomainName1->Length >> 1] = 0;
      goto LABEL_60;
    }
    pName1 = (PCWSTR)*((_QWORD *)v23 + 1);
    if ( pName1[v24 >> 1] )
      goto LABEL_58;
    v106 = 0;
LABEL_60:
    Length = v12->Length;
    LOBYTE(a5) = 0;
    v115 = 0;
    v107 = 0;
    if ( v12->MaximumLength <= (unsigned __int16)Length
      || (Buffer = (__int64)v12->Buffer, pName2 = (PCWSTR)Buffer, *(_WORD *)(Buffer + 2 * (Length >> 1))) )
    {
      pName2 = (PCWSTR)LocalAlloc(0x40u, Length + 2);
      Buffer = (__int64)pName2;
      if ( pName2 )
      {
        v107 = 1;
        memcpy_0((void *)pName2, v12->Buffer, v12->Length);
        Buffer = (__int64)pName2;
        v61 = 0;
        pName2[(unsigned __int64)v12->Length >> 1] = 0;
      }
      else
      {
        v61 = -1073741801;
      }
    }
    else
    {
      v61 = v115;
    }
    if ( v61 >= 0 )
      LOBYTE(a5) = RtlEqualDomainName(DomainName1, v12 + 1) || DnsNameCompare_W(pName1, pName2);
    if ( v106 )
      LocalFree((HLOCAL)pName1);
    if ( v107 )
      LocalFree((HLOCAL)pName2);
    if ( !(_BYTE)a5 )
      goto LABEL_170;
    pName2 = (PCWSTR)((char *)a4 + Size);
    if ( !*(_WORD *)((char *)a4 + Size) )
      goto LABEL_172;
    if ( v10 != -1 )
      goto LABEL_93;
    v62 = a6;
    memset(DestinationString, 0, sizeof(DestinationString));
    if ( !a6 )
    {
      InformationPolicy = -1073741811;
      goto LABEL_164;
    }
    v63 = Sid;
    v64 = 0;
    v65 = (struct _UNICODE_STRING *)*((_QWORD *)a6 + 1);
    v66 = *(_DWORD *)a6;
    Size = (size_t)Sid;
    DomainName1 = v65;
    v115 = v66;
    v109 = -1;
    while ( 1 )
    {
      LODWORD(a5) = v64;
      if ( v64 >= v66 || !v63 )
      {
        v67 = *((_DWORD *)v62 + 4);
        LODWORD(a5) = v67;
        if ( *(_DWORD *)v62 >= v67 && v67 < v67 + 32 )
        {
          DomainName1 = (PUNICODE_STRING)LocalAlloc(0x40u, 24 * (v67 + 32));
          v68 = DomainName1;
          if ( !DomainName1 )
            goto LABEL_185;
          v69 = (const void *)*((_QWORD *)v62 + 1);
          Size = (size_t)v69;
          if ( v69 )
          {
            memcpy_0(DomainName1, v69, (unsigned int)(24 * a5));
            LocalFree((HLOCAL)Size);
            v68 = DomainName1;
          }
          v70 = a5 + 32;
          *((_QWORD *)v62 + 1) = v68;
          *((_DWORD *)v62 + 4) = v70;
        }
        v71 = *(_DWORD *)v62;
        *(UNICODE_STRING *)DestinationString = SourceString;
        LODWORD(a5) = v71;
        if ( SourceString.Buffer )
        {
          if ( SourceString.MaximumLength )
          {
            v72 = LocalAlloc(0x40u, SourceString.MaximumLength);
            *(_QWORD *)&DestinationString[8] = v72;
            if ( !v72 )
            {
LABEL_186:
              InformationPolicy = -1073741670;
              if ( v72 )
                LocalFree(v72);
              Buffer = *(_QWORD *)&DestinationString[16];
              if ( *(_QWORD *)&DestinationString[16] )
                LocalFree(*(HLOCAL *)&DestinationString[16]);
              goto LABEL_164;
            }
            RtlCopyUnicodeString((PUNICODE_STRING)DestinationString, &SourceString);
            v71 = a5;
          }
          else
          {
            *(_QWORD *)&DestinationString[8] = 0;
          }
        }
        InformationPolicy = 0;
        DomainName1 = (PUNICODE_STRING)Sid;
        if ( !Sid )
        {
LABEL_90:
          v74 = a6;
          v10 = v71;
          v109 = v71;
          v75 = 3LL * v71;
          v76 = *((_QWORD *)a6 + 1);
          *(_OWORD *)(v76 + 8 * v75) = *(_OWORD *)DestinationString;
          *(_QWORD *)(v76 + 8 * v75 + 16) = *(_QWORD *)&DestinationString[16];
          ++*(_DWORD *)v74;
          goto LABEL_93;
        }
        Size = RtlLengthSid(Sid);
        v73 = LocalAlloc(0x40u, Size);
        *(_QWORD *)&DestinationString[16] = v73;
        if ( v73 )
        {
          memcpy_0(v73, DomainName1, Size);
          v71 = a5;
          goto LABEL_90;
        }
LABEL_185:
        v72 = *(HLOCAL *)&DestinationString[8];
        goto LABEL_186;
      }
      v99 = (void *)*((_QWORD *)&v65[1].Length + 3 * v64);
      if ( !v99 )
        goto LABEL_146;
      if ( RtlEqualSid(v99, v63) )
        break;
      v63 = (void *)Size;
      v65 = DomainName1;
LABEL_146:
      v66 = v115;
      v64 = a5 + 1;
    }
    v10 = a5;
    InformationPolicy = 0;
    v109 = a5;
LABEL_93:
    v20 = v111;
    *((_OWORD *)Heap + v108) = *(_OWORD *)pName2;
    v14[v108] = v114;
    v19 = ++v108;
    *((_DWORD *)v120 + 4) = v10;
LABEL_15:
    Buffer = (unsigned int)(v114 + 1);
    v114 = Buffer;
  }
  while ( (unsigned int)Buffer < a2 );
  if ( InformationPolicy < 0 )
    goto LABEL_164;
  if ( !(_DWORD)v19 )
    goto LABEL_18;
  if ( a1 == 1 )
  {
    v77 = (struct _LSA_TRANSLATED_SID_EX2 *)LsapBuiltinDomainHandle;
  }
  else
  {
    v77 = (struct _LSA_TRANSLATED_SID_EX2 *)LsapLocalAccountDomainHandle;
    if ( a1 == 2 )
      v77 = (struct _LSA_TRANSLATED_SID_EX2 *)LsapAccountDomainHandle;
  }
  v120 = v77;
  if ( !(unsigned __int8)IsSamIDecodeClaimsBlobPresent(Buffer, v19, v20) )
  {
LABEL_163:
    InformationPolicy = -1073741637;
    goto LABEL_164;
  }
  v78 = SamrLookupNamesInDomain2(v77, v108, Heap, &v121, &v123);
  InformationPolicy = v78;
  if ( v78 < 0 )
  {
    if ( v78 == -1073741604 )
      InformationPolicy = LsapSamExtLookupNamesInDomain2(
                            v77,
                            v108,
                            Heap,
                            (struct _SAMPR_ULONG_ARRAY *)&v121,
                            (struct _SAMPR_ULONG_ARRAY *)&v123);
    if ( InformationPolicy == -1073741709 )
      goto LABEL_18;
LABEL_164:
    v79 = a6;
    goto LABEL_165;
  }
  v79 = a6;
  memset(DestinationString, 0, sizeof(DestinationString));
  if ( !a6 )
  {
    InformationPolicy = -1073741811;
LABEL_165:
    if ( v10 >= 0 )
    {
      v100 = *((_QWORD *)v79 + 1) + 24LL * v10;
      v101 = *(void **)(v100 + 16);
      if ( v101 )
      {
        LocalFree(v101);
        *(_QWORD *)(v100 + 16) = 0;
      }
      Buffer = *(_QWORD *)(v100 + 8);
      if ( Buffer )
      {
        LocalFree((HLOCAL)Buffer);
        *(_QWORD *)(v100 + 8) = 0;
        *(_DWORD *)v100 = 0;
      }
    }
    goto LABEL_135;
  }
  v80 = Sid;
  v81 = 0;
  v15 = *((_QWORD *)a6 + 1);
  v10 = -1;
  v82 = *(_DWORD *)a6;
  a5 = (size_t)Sid;
  Size = v15;
  while ( v81 < v82 && v80 )
  {
    v98 = *(void **)(v15 + 24LL * v81 + 16);
    if ( v98 )
    {
      if ( RtlEqualSid(v98, v80) )
      {
        v10 = v81;
        InformationPolicy = 0;
        goto LABEL_120;
      }
      v80 = (PSID)a5;
      v15 = Size;
    }
    ++v81;
  }
  v83 = *((_DWORD *)v79 + 4);
  if ( *(_DWORD *)v79 >= v83 )
  {
    v84 = v83 + 32;
    if ( v83 < v83 + 32 )
    {
      v85 = LocalAlloc(0x40u, 24 * v84);
      Size = (size_t)v85;
      if ( v85 )
      {
        v86 = (void *)*((_QWORD *)v79 + 1);
        a5 = (size_t)v86;
        if ( v86 )
        {
          memcpy_0(v85, v86, 24 * v83);
          LocalFree((HLOCAL)a5);
          v85 = (void *)Size;
        }
        *((_QWORD *)v79 + 1) = v85;
        *((_DWORD *)v79 + 4) = v84;
        goto LABEL_108;
      }
LABEL_178:
      v87 = *(HLOCAL *)&DestinationString[8];
LABEL_179:
      InformationPolicy = -1073741670;
      if ( v87 )
        LocalFree(v87);
      Buffer = *(_QWORD *)&DestinationString[16];
      if ( *(_QWORD *)&DestinationString[16] )
        LocalFree(*(HLOCAL *)&DestinationString[16]);
      goto LABEL_165;
    }
  }
LABEL_108:
  i = *(unsigned int *)v79;
  *(UNICODE_STRING *)DestinationString = SourceString;
  LODWORD(a5) = i;
  if ( SourceString.Buffer )
  {
    if ( SourceString.MaximumLength )
    {
      v87 = LocalAlloc(0x40u, SourceString.MaximumLength);
      *(_QWORD *)&DestinationString[8] = v87;
      if ( !v87 )
        goto LABEL_179;
      RtlCopyUnicodeString((PUNICODE_STRING)DestinationString, &SourceString);
      i = (unsigned int)a5;
    }
    else
    {
      *(_QWORD *)&DestinationString[8] = 0;
    }
  }
  v88 = Sid;
  InformationPolicy = 0;
  if ( Sid )
  {
    Size = RtlLengthSid(Sid);
    v89 = LocalAlloc(0x40u, Size);
    *(_QWORD *)&DestinationString[16] = v89;
    if ( !v89 )
      goto LABEL_178;
    memcpy_0(v89, v88, Size);
    i = (unsigned int)a5;
  }
  v10 = i;
  Buffer = 3LL * (unsigned int)i;
  v90 = *((_QWORD *)v79 + 1);
  *(_OWORD *)(v90 + 8 * Buffer) = *(_OWORD *)DestinationString;
  *(_QWORD *)(v90 + 8 * Buffer + 16) = *(_QWORD *)&DestinationString[16];
  ++*(_DWORD *)v79;
LABEL_120:
  for ( j = 0; (unsigned int)j < (unsigned int)v121; j = (unsigned int)(j + 1) )
  {
    i = 4 * j;
    Buffer = 3LL * (unsigned int)v14[j];
    v92 = v111 + 24LL * (unsigned int)v14[j];
    if ( *(_DWORD *)v92 == 8 )
    {
      Buffer = *(unsigned int *)(*((_QWORD *)&v123 + 1) + 4 * j);
      if ( (_DWORD)Buffer != 8 )
      {
        v93 = a8;
        *(_DWORD *)v92 = Buffer;
        a5 = 0;
        ++*v93;
        v94 = *(_DWORD *)(*((_QWORD *)&v121 + 1) + 4 * j);
        if ( !(unsigned __int8)IsSamIDecodeClaimsBlobPresent(Buffer, i, v15) )
          goto LABEL_163;
        InformationPolicy = SamrRidToSid(v120, v94, &a5);
        if ( InformationPolicy < 0 )
          goto LABEL_164;
        DomainName1 = (PUNICODE_STRING)a5;
        if ( a5 )
        {
          Size = RtlLengthSid((PSID)a5);
          v97 = LocalAlloc(0x40u, Size);
          *(_QWORD *)(v92 + 8) = v97;
          if ( v97 )
          {
            InformationPolicy = 0;
            memcpy_0(v97, DomainName1, Size);
          }
          else
          {
            InformationPolicy = -1073741670;
          }
        }
        else
        {
          InformationPolicy = 0;
          *(_QWORD *)(v92 + 8) = 0;
        }
        Size = a5;
        if ( (unsigned __int8)IsSamIDecodeClaimsBlobPresent(Buffer, v95, v96) )
          SamIFreeVoid(Size);
        if ( InformationPolicy < 0 )
          goto LABEL_164;
        *(_DWORD *)(v92 + 16) = v10;
      }
    }
  }
LABEL_139:
  if ( InformationPolicy >= 0 )
  {
LABEL_18:
    InformationPolicy = LsapLoadLsaDbExtensionDll();
    if ( InformationPolicy >= 0 )
      InformationPolicy = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))g_pLsaExtensionTableLsaDb + 23))(
                            a2,
                            a1,
                            (unsigned int)v10,
                            v111);
    Buffer = 0x80000000LL;
    if ( (int)(InformationPolicy + 0x80000000) < 0 || InformationPolicy == -1073741637 )
    {
      v26 = a7;
      v27 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      if ( InformationPolicy != -1073741637 )
        v27 = InformationPolicy;
      v29 = 0;
      v30 = *(_DWORD *)a7;
      InformationPolicy = v27;
      if ( *(_DWORD *)a7 )
      {
        v31 = 0;
        if ( v30 < 8 )
          goto LABEL_28;
        v32 = *((_QWORD *)a7 + 1);
        v33 = 0;
        v34 = 0;
        do
        {
          v35 = _mm_unpacklo_epi32(
                  _mm_cvtsi32_si128(*(_DWORD *)(v32 + 24LL * (unsigned int)(v31 + 2) + 16)),
                  _mm_cvtsi32_si128(*(_DWORD *)(v32 + 24LL * (unsigned int)(v31 + 3) + 16)));
          v36 = _mm_cvtsi32_si128(*(_DWORD *)(v32 + 24LL * (unsigned int)(v31 + 7) + 16));
          v15 = 3LL * (unsigned int)(v31 + 6);
          Buffer = 3 * v31;
          v37 = _mm_unpacklo_epi32(
                  _mm_cvtsi32_si128(*(_DWORD *)(v32 + 24 * v31 + 16)),
                  _mm_cvtsi32_si128(*(_DWORD *)(v32 + 24LL * (unsigned int)(v31 + 1) + 16)));
          v38 = 3LL * (unsigned int)(v31 + 4);
          v39 = _mm_cvtsi32_si128(*(_DWORD *)(v32 + 24LL * (unsigned int)(v31 + 5) + 16));
          v31 = (unsigned int)(v31 + 8);
          v33 = _mm_sub_epi32(v33, _mm_cmpeq_epi32(_mm_unpacklo_epi64(v37, v35), si128));
          v34 = _mm_sub_epi32(
                  v34,
                  _mm_cmpeq_epi32(
                    _mm_unpacklo_epi64(
                      _mm_unpacklo_epi32(_mm_cvtsi32_si128(*(_DWORD *)(v32 + 8 * v38 + 16)), v39),
                      _mm_unpacklo_epi32(_mm_cvtsi32_si128(*(_DWORD *)(v32 + 8 * v15 + 16)), v36)),
                    si128));
        }
        while ( (unsigned int)v31 < (v30 & 0xFFFFFFF8) );
        v40 = _mm_add_epi32(v34, v33);
        v41 = _mm_add_epi32(v40, _mm_srli_si128(v40, 8));
        v29 = _mm_cvtsi128_si32(_mm_add_epi32(v41, _mm_srli_si128(v41, 4)));
        if ( (unsigned int)v31 < v30 )
        {
LABEL_28:
          v15 = *((_QWORD *)a7 + 1);
          do
          {
            Buffer = 3 * v31;
            v42 = v29 + 1;
            if ( *(_DWORD *)(v15 + 24 * v31 + 16) != -1 )
              v42 = v29;
            v31 = (unsigned int)(v31 + 1);
            v29 = v42;
          }
          while ( (unsigned int)v31 < v30 );
        }
      }
      v43 = a9;
      *a9 = v29;
      i = 0;
      v44 = *(_DWORD *)v26;
      if ( *(_DWORD *)v26 )
      {
        v45 = 0;
        if ( v44 < 8 )
          goto LABEL_37;
        v46 = *((_QWORD *)v26 + 1);
        v47 = 0;
        v48 = 0;
        do
        {
          v49 = _mm_unpacklo_epi32(
                  _mm_cvtsi32_si128(*(_DWORD *)(v46 + 24LL * (unsigned int)(v45 + 2) + 16)),
                  _mm_cvtsi32_si128(*(_DWORD *)(v46 + 24LL * (unsigned int)(v45 + 3) + 16)));
          v50 = _mm_cvtsi32_si128(*(_DWORD *)(v46 + 24LL * (unsigned int)(v45 + 7) + 16));
          v15 = 3LL * (unsigned int)(v45 + 6);
          Buffer = 3 * v45;
          v51 = _mm_unpacklo_epi32(
                  _mm_cvtsi32_si128(*(_DWORD *)(v46 + 24 * v45 + 16)),
                  _mm_cvtsi32_si128(*(_DWORD *)(v46 + 24LL * (unsigned int)(v45 + 1) + 16)));
          v52 = 3LL * (unsigned int)(v45 + 4);
          v53 = _mm_cvtsi32_si128(*(_DWORD *)(v46 + 24LL * (unsigned int)(v45 + 5) + 16));
          v45 = (unsigned int)(v45 + 8);
          v47 = _mm_sub_epi32(v47, _mm_cmpeq_epi32(_mm_unpacklo_epi64(v51, v49), si128));
          v48 = _mm_sub_epi32(
                  v48,
                  _mm_cmpeq_epi32(
                    _mm_unpacklo_epi64(
                      _mm_unpacklo_epi32(_mm_cvtsi32_si128(*(_DWORD *)(v46 + 8 * v52 + 16)), v53),
                      _mm_unpacklo_epi32(_mm_cvtsi32_si128(*(_DWORD *)(v46 + 8 * v15 + 16)), v50)),
                    si128));
        }
        while ( (unsigned int)v45 < (v44 & 0xFFFFFFF8) );
        v54 = _mm_add_epi32(v48, v47);
        v55 = _mm_add_epi32(v54, _mm_srli_si128(v54, 8));
        i = (unsigned int)_mm_cvtsi128_si32(_mm_add_epi32(v55, _mm_srli_si128(v55, 4)));
        if ( (unsigned int)v45 < v44 )
        {
LABEL_37:
          v15 = *((_QWORD *)v26 + 1);
          do
          {
            Buffer = 3 * v45;
            v56 = i + 1;
            if ( *(_DWORD *)(v15 + 24 * v45 + 16) != -1 )
              v56 = i;
            v45 = (unsigned int)(v45 + 1);
            i = v56;
          }
          while ( (unsigned int)v45 < v44 );
        }
      }
      *v43 = i;
    }
  }
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v14 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
  if ( (_DWORD)v121 && (unsigned __int8)IsSamIDecodeClaimsBlobPresent(Buffer, i, v15) )
    SamIFree_SAMPR_ULONG_ARRAY(&v121);
  if ( (_DWORD)v123 && (unsigned __int8)IsSamIDecodeClaimsBlobPresent(Buffer, i, v15) )
    SamIFree_SAMPR_ULONG_ARRAY(&v123);
  if ( (unsigned __int8)IsSamIDecodeClaimsBlobPresent(Buffer, i, v15) )
    SamIFreeRealmList(&v124);
  v57 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x40) != 0 )
  {
    v103 = 27;
LABEL_184:
    WPP_SF_d(
      *((_QWORD *)v57 + 12),
      v103,
      WPP_f0978fc1336a326ebe269f72ca0dc488_Traceguids,
      (unsigned int)InformationPolicy);
  }
  return (unsigned int)InformationPolicy;
}

```

## disassembly

```asm
0x18001cc60  mov     [rsp-8+arg_18], r9
0x18001cc65  mov     [rsp-8+arg_10], r8
0x18001cc6a  mov     [rsp-8+arg_0], ecx
0x18001cc6e  push    rbp
0x18001cc6f  push    rsi
0x18001cc70  push    rdi
0x18001cc71  push    r12
0x18001cc73  push    r13
0x18001cc75  push    r15
0x18001cc77  lea     rbp, [rsp-7]
0x18001cc7c  sub     rsp, 0F8h
0x18001cc83  xorps   xmm0, xmm0
0x18001cc86  xor     r15d, r15d
0x18001cc89  xor     eax, eax
0x18001cc8b  mov     [rbp+2Fh+var_68], r15
0x18001cc8f  mov     r12d, 0FFFFFFFFh
0x18001cc95  mov     [rbp+2Fh+Sid], rax
0x18001cc99  xorps   xmm1, xmm1
0x18001cc9c  mov     [rsp+120h+var_E8], r12d
0x18001cca1  mov     r13d, edx
0x18001cca4  movups  [rbp+2Fh+var_78], xmm0
0x18001cca8  movups  [rbp+2Fh+var_60], xmm1
0x18001ccac  movups  xmmword ptr [rbp+2Fh+SourceString.Length], xmm0
0x18001ccb0  movups  [rbp+2Fh+var_50], xmm0
0x18001ccb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccbb  test    byte ptr [rcx+6Ch], 40h
0x18001ccbf  jnz     loc_18001DB10
0x18001ccc5  cmp     cs:?LsapSamOpened@@3EA, 1; uchar LsapSamOpened
0x18001cccc  mov     rsi, [rbp+2Fh+arg_20]
0x18001ccd0  mov     [rsp+120h+arg_8], rbx
0x18001ccd8  mov     [rsp+120h+var_30], r14
0x18001cce0  mov     dword ptr [rbp+2Fh+var_78], r15d
0x18001cce4  movzx   eax, word ptr [rsi+10h]
0x18001cce8  mov     [rbp+2Fh+SourceString.Length], ax
0x18001ccec  movzx   eax, word ptr [rsi+12h]
0x18001ccf0  mov     [rbp+2Fh+SourceString.MaximumLength], ax
0x18001ccf4  mov     eax, [rsi+14h]
0x18001ccf7  mov     dword ptr [rbp+2Fh+SourceString+4], eax
0x18001ccfa  mov     rax, [rsi+18h]
0x18001ccfe  mov     [rbp+2Fh+SourceString.Buffer], rax
0x18001cd02  mov     rax, [rsi+20h]
0x18001cd06  mov     [rbp+2Fh+Sid], rax
0x18001cd0a  mov     qword ptr [rbp+2Fh+var_78+8], r15
0x18001cd0e  mov     dword ptr [rbp+2Fh+var_60], r15d
0x18001cd12  mov     qword ptr [rbp+2Fh+var_60+8], r15
0x18001cd16  mov     [rsp+120h+pName2], r15
0x18001cd1b  mov     [rbp+2Fh+pName1], r15
0x18001cd1f  mov     [rbp+2Fh+arg_20], r15
0x18001cd23  jnz     loc_18001DB2A
0x18001cd29  mov     ebx, r15d
0x18001cd2c  mov     rcx, [rbp+2Fh+arg_40]
0x18001cd30  mov     r14, r15
0x18001cd33  mov     rdx, [rbp+2Fh+arg_38]
0x18001cd37  mov     r8, r15
0x18001cd3a  mov     [rsp+120h+var_D8], r15
0x18001cd3f  mov     ecx, [rcx]
0x18001cd41  mov     edx, [rdx]
0x18001cd43  lea     eax, [rdx+rcx]
0x18001cd46  cmp     eax, r13d
0x18001cd49  ja      loc_18001DC91
0x18001cd4f  test    ecx, ecx
0x18001cd51  jz      loc_18001CE55
0x18001cd57  mov     rcx, gs:60h
0x18001cd60  mov     rax, [rbp+2Fh+arg_30]
0x18001cd64  mov     rcx, [rcx+30h]; HeapHandle
0x18001cd68  mov     rax, [rax+8]
0x18001cd6c  mov     [rsp+120h+var_D8], rax
0x18001cd71  mov     eax, r13d
0x18001cd74  sub     eax, edx
0x18001cd76  mov     edx, 8; Flags
0x18001cd7b  mov     r8d, eax
0x18001cd7e  mov     [rbp+2Fh+arg_20], rax
0x18001cd82  shl     r8, 4; Size
0x18001cd86  call    cs:__imp_RtlAllocateHeap
0x18001cd8d  nop     dword ptr [rax+rax+00h]
0x18001cd92  mov     r15, rax
0x18001cd95  test    rax, rax
0x18001cd98  jz      loc_18001D7FC
0x18001cd9e  mov     rcx, gs:60h
0x18001cda7  mov     edx, 8; Flags
0x18001cdac  mov     r8, [rbp+2Fh+arg_20]
0x18001cdb0  mov     rcx, [rcx+30h]; HeapHandle
0x18001cdb4  lea     r8, ds:0[r8*4]; Size
0x18001cdbc  call    cs:__imp_RtlAllocateHeap
0x18001cdc3  nop     dword ptr [rax+rax+00h]
0x18001cdc8  mov     r14, rax
0x18001cdcb  test    rax, rax
0x18001cdce  jz      loc_18001DC9B
0x18001cdd4  xor     edx, edx
0x18001cdd6  xor     ecx, ecx
0x18001cdd8  mov     [rsp+120h+var_EC], edx
0x18001cddc  mov     [rsp+120h+var_C0], ecx
0x18001cde0  test    r13d, r13d
0x18001cde3  jz      short loc_18001CE55
0x18001cde5  mov     r8, [rsp+120h+var_D8]
0x18001cdea  lea     rax, [rcx+rcx*2]
0x18001cdee  cmp     dword ptr [r8+rax*8], 8
0x18001cdf3  lea     rax, [r8+rax*8]
0x18001cdf7  mov     [rbp+2Fh+var_80], rax
0x18001cdfb  jnz     short loc_18001CE36
0x18001cdfd  mov     rax, [rbp+2Fh+arg_10]
0x18001ce01  shl     rcx, 4
0x18001ce05  add     rax, rcx
0x18001ce08  mov     [rsp+120h+Size], rcx
0x18001ce0d  mov     [rsp+120h+DomainName1], rax
0x18001ce12  movzx   edx, word ptr [rax]
0x18001ce15  test    dx, dx
0x18001ce18  jnz     loc_18001D1AA
0x18001ce1e  mov     rax, [rbp+2Fh+arg_18]
0x18001ce22  add     rax, rcx
0x18001ce25  mov     [rbp+2Fh+arg_20], rax
0x18001ce29  cmp     [rax], dx
0x18001ce2c  jnz     loc_18001D8EF
0x18001ce32  mov     edx, [rsp+120h+var_EC]
0x18001ce36  mov     ecx, [rsp+120h+var_C0]
0x18001ce3a  inc     ecx
0x18001ce3c  mov     [rsp+120h+var_C0], ecx
0x18001ce40  cmp     ecx, r13d
0x18001ce43  jb      short loc_18001CDEA
0x18001ce45  test    ebx, ebx
0x18001ce47  js      loc_18001D97B
0x18001ce4d  test    edx, edx
0x18001ce4f  jnz     loc_18001D4F8
0x18001ce55  call    ?LsapLoadLsaDbExtensionDll@@YAJXZ; LsapLoadLsaDbExtensionDll(void)
0x18001ce5a  mov     ebx, eax
0x18001ce5c  test    eax, eax
0x18001ce5e  jns     loc_18001DD8B
0x18001ce64  mov     ecx, 80000000h
0x18001ce69  lea     eax, [rbx+rcx]
0x18001ce6c  test    ecx, eax
0x18001ce6e  jz      loc_18001D6CA
0x18001ce74  mov     rdi, [rbp+2Fh+arg_30]
0x18001ce78  xor     eax, eax
0x18001ce7a  cmp     ebx, 0C00000BBh
0x18001ce80  movaps  [rsp+120h+var_40], xmm6
0x18001ce88  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18001ce90  cmovnz  eax, ebx
0x18001ce93  xor     edx, edx
0x18001ce95  mov     r11d, [rdi]
0x18001ce98  mov     ebx, eax
0x18001ce9a  test    r11d, r11d
0x18001ce9d  jz      loc_18001CFAE
0x18001cea3  xor     r10d, r10d
0x18001cea6  cmp     r11d, 8
0x18001ceaa  jb      loc_18001CF90
0x18001ceb0  mov     r12, [rdi+8]
0x18001ceb4  mov     esi, r11d
0x18001ceb7  and     esi, 0FFFFFFF8h
0x18001ceba  xorps   xmm5, xmm5
0x18001cebd  xorps   xmm4, xmm4
0x18001cec0  lea     eax, [r10+3]
0x18001cec4  lea     r9, [rax+rax*2]
0x18001cec8  movd    xmm1, dword ptr [r12+r9*8+10h]
0x18001cecf  lea     eax, [r10+2]
0x18001ced3  lea     r8, [rax+rax*2]
0x18001ced7  movd    xmm2, dword ptr [r12+r8*8+10h]
0x18001cede  lea     eax, [r10+1]
0x18001cee2  lea     rdx, [rax+rax*2]
0x18001cee6  punpckldq xmm2, xmm1
0x18001ceea  movd    xmm0, dword ptr [r12+rdx*8+10h]
0x18001cef1  lea     eax, [r10+7]
0x18001cef5  lea     r9, [rax+rax*2]
0x18001cef9  movd    xmm1, dword ptr [r12+r9*8+10h]
0x18001cf00  lea     eax, [r10+6]
0x18001cf04  lea     r8, [rax+rax*2]
0x18001cf08  lea     eax, [r10+5]
0x18001cf0c  lea     rdx, [rax+rax*2]
0x18001cf10  lea     rcx, [r10+r10*2]
0x18001cf14  movd    xmm3, dword ptr [r12+rcx*8+10h]
0x18001cf1b  lea     eax, [r10+4]
0x18001cf1f  punpckldq xmm3, xmm0
0x18001cf23  lea     rax, [rax+rax*2]
0x18001cf27  movd    xmm0, dword ptr [r12+rdx*8+10h]
0x18001cf2e  add     r10d, 8
0x18001cf32  punpcklqdq xmm3, xmm2
0x18001cf36  movd    xmm2, dword ptr [r12+r8*8+10h]
0x18001cf3d  pcmpeqd xmm3, xmm6
0x18001cf41  punpckldq xmm2, xmm1
0x18001cf45  psubd   xmm5, xmm3
0x18001cf49  movd    xmm3, dword ptr [r12+rax*8+10h]
0x18001cf50  punpckldq xmm3, xmm0
0x18001cf54  punpcklqdq xmm3, xmm2
0x18001cf58  pcmpeqd xmm3, xmm6
0x18001cf5c  psubd   xmm4, xmm3
0x18001cf60  cmp     r10d, esi
0x18001cf63  jb      loc_18001CEC0
0x18001cf69  paddd   xmm4, xmm5
0x18001cf6d  movdqa  xmm0, xmm4
0x18001cf71  psrldq  xmm0, 8
0x18001cf76  paddd   xmm4, xmm0
0x18001cf7a  movdqa  xmm0, xmm4
0x18001cf7e  psrldq  xmm0, 4
0x18001cf83  paddd   xmm4, xmm0
0x18001cf87  movd    edx, xmm4
0x18001cf8b  cmp     r10d, r11d
0x18001cf8e  jnb     short loc_18001CFAE
0x18001cf90  mov     r8, [rdi+8]
0x18001cf94  lea     rcx, [r10+r10*2]
0x18001cf98  cmp     dword ptr [r8+rcx*8+10h], 0FFFFFFFFh
0x18001cf9e  lea     eax, [rdx+1]
0x18001cfa1  cmovnz  eax, edx
0x18001cfa4  inc     r10d
0x18001cfa7  mov     edx, eax
0x18001cfa9  cmp     r10d, r11d
0x18001cfac  jb      short loc_18001CF94
0x18001cfae  mov     rsi, [rbp+2Fh+arg_40]
0x18001cfb2  mov     [rsi], edx
0x18001cfb4  xor     edx, edx
0x18001cfb6  mov     r11d, [rdi]
0x18001cfb9  test    r11d, r11d
0x18001cfbc  jz      loc_18001D0CE
0x18001cfc2  xor     r10d, r10d
0x18001cfc5  cmp     r11d, 8
0x18001cfc9  jb      loc_18001D0B0
0x18001cfcf  mov     r13, [rdi+8]
0x18001cfd3  mov     r12d, r11d
0x18001cfd6  and     r12d, 0FFFFFFF8h
0x18001cfda  xorps   xmm5, xmm5
0x18001cfdd  xorps   xmm4, xmm4
0x18001cfe0  lea     eax, [r10+3]
0x18001cfe4  lea     r9, [rax+rax*2]
0x18001cfe8  movd    xmm1, dword ptr [r13+r9*8+10h]
0x18001cfef  lea     eax, [r10+2]
0x18001cff3  lea     r8, [rax+rax*2]
0x18001cff7  movd    xmm2, dword ptr [r13+r8*8+10h]
0x18001cffe  lea     eax, [r10+1]
0x18001d002  lea     rdx, [rax+rax*2]
0x18001d006  punpckldq xmm2, xmm1
0x18001d00a  movd    xmm0, dword ptr [r13+rdx*8+10h]
0x18001d011  lea     eax, [r10+7]
0x18001d015  lea     r9, [rax+rax*2]
0x18001d019  movd    xmm1, dword ptr [r13+r9*8+10h]
0x18001d020  lea     eax, [r10+6]
0x18001d024  lea     r8, [rax+rax*2]
0x18001d028  lea     eax, [r10+5]
0x18001d02c  lea     rdx, [rax+rax*2]
0x18001d030  lea     rcx, [r10+r10*2]
0x18001d034  movd    xmm3, dword ptr [r13+rcx*8+10h]
0x18001d03b  lea     eax, [r10+4]
0x18001d03f  punpckldq xmm3, xmm0
0x18001d043  lea     rax, [rax+rax*2]
0x18001d047  movd    xmm0, dword ptr [r13+rdx*8+10h]
0x18001d04e  add     r10d, 8
0x18001d052  punpcklqdq xmm3, xmm2
0x18001d056  movd    xmm2, dword ptr [r13+r8*8+10h]
0x18001d05d  pcmpeqd xmm3, xmm6
0x18001d061  punpckldq xmm2, xmm1
0x18001d065  psubd   xmm5, xmm3
0x18001d069  movd    xmm3, dword ptr [r13+rax*8+10h]
0x18001d070  punpckldq xmm3, xmm0
0x18001d074  punpcklqdq xmm3, xmm2
0x18001d078  pcmpeqd xmm3, xmm6
0x18001d07c  psubd   xmm4, xmm3
0x18001d080  cmp     r10d, r12d
0x18001d083  jb      loc_18001CFE0
0x18001d089  paddd   xmm4, xmm5
0x18001d08d  movdqa  xmm0, xmm4
0x18001d091  psrldq  xmm0, 8
0x18001d096  paddd   xmm4, xmm0
0x18001d09a  movdqa  xmm0, xmm4
0x18001d09e  psrldq  xmm0, 4
0x18001d0a3  paddd   xmm4, xmm0
0x18001d0a7  movd    edx, xmm4
0x18001d0ab  cmp     r10d, r11d
0x18001d0ae  jnb     short loc_18001D0CE
0x18001d0b0  mov     r8, [rdi+8]
0x18001d0b4  lea     rcx, [r10+r10*2]
0x18001d0b8  cmp     dword ptr [r8+rcx*8+10h], 0FFFFFFFFh
0x18001d0be  lea     eax, [rdx+1]
0x18001d0c1  cmovnz  eax, edx
0x18001d0c4  inc     r10d
0x18001d0c7  mov     edx, eax
0x18001d0c9  cmp     r10d, r11d
0x18001d0cc  jb      short loc_18001D0B4
0x18001d0ce  movaps  xmm6, [rsp+120h+var_40]
0x18001d0d6  mov     [rsi], edx
0x18001d0d8  test    r15, r15
0x18001d0db  jz      short loc_18001D0FB
0x18001d0dd  mov     rcx, gs:60h
0x18001d0e6  mov     r8, r15; P
0x18001d0e9  xor     edx, edx; Flags
0x18001d0eb  mov     rcx, [rcx+30h]; HeapHandle
0x18001d0ef  call    cs:__imp_RtlFreeHeap
0x18001d0f6  nop     dword ptr [rax+rax+00h]
0x18001d0fb  test    r14, r14
0x18001d0fe  jz      short loc_18001D11E
0x18001d100  mov     rcx, gs:60h
0x18001d109  mov     r8, r14; P
0x18001d10c  xor     edx, edx; Flags
0x18001d10e  mov     rcx, [rcx+30h]; HeapHandle
0x18001d112  call    cs:__imp_RtlFreeHeap
0x18001d119  nop     dword ptr [rax+rax+00h]
0x18001d11e  cmp     dword ptr [rbp+2Fh+var_78], 0
0x18001d122  jz      short loc_18001D13D
0x18001d124  call    IsSamIDecodeClaimsBlobPresent
0x18001d129  test    al, al
0x18001d12b  jz      short loc_18001D13D
0x18001d12d  lea     rcx, [rbp+2Fh+var_78]
0x18001d131  call    cs:__imp_SamIFree_SAMPR_ULONG_ARRAY
0x18001d138  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
