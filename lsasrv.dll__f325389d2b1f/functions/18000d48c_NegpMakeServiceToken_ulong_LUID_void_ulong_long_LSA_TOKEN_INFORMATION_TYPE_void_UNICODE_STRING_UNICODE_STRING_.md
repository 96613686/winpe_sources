# NegpMakeServiceToken(ulong,_LUID *,void * *,ulong *,long *,_LSA_TOKEN_INFORMATION_TYPE *,void * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x18000d48c`
- end: `0x18000dc67`
- name: `?NegpMakeServiceToken@@YAJKPEAU_LUID@@PEAPEAXPEAKPEAJPEAW4_LSA_TOKEN_INFORMATION_TYPE@@1PEAPEAU_UNICODE_STRING@@55PEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `2011`
- prototype: `int(unsigned int, struct _LUID *, void **, unsigned int *, int *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009ac50`

## callees

- `0x1800093b0`
- `0x180009410`
- `0x18000b7d0`
- `0x18000c0f0`
- `0x18000c300`
- `0x18000d3b0`
- `0x18000d48c`
- `0x18000dc70`
- `0x18000dca0`
- `0x18000dd1c`
- `0x1800162a8`
- `0x180016f70`
- `0x18005c8b4`
- `0x18005e150`
- `0x18005e770`
- `0x1800b1f9c`
- `0x1800b86d0`
- `0x1800bbbfc`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000d63b`
- `ntdll!RtlFreeHeap` at `0x18000d63b`
- `ntdll!RtlCopySid` at `0x18000d889`
- `ntdll!RtlCopySid` at `0x18000d8e6`
- `ntdll!RtlCopySid` at `0x18000d916`
- `ntdll!RtlCopySid` at `0x18000d942`
- `ntdll!RtlCopySid` at `0x18000dbbb`
- `ntdll!RtlCopySid` at `0x18000d889`
- `ntdll!RtlCopySid` at `0x18000d8e6`
- `ntdll!RtlCopySid` at `0x18000d916`
- `ntdll!RtlCopySid` at `0x18000d942`
- `ntdll!RtlCopySid` at `0x18000dbbb`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000d98f`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000d9a7`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000d98f`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000d9a7`
- `ntdll!RtlCreateAcl` at `0x18000d967`
- `ntdll!RtlCreateAcl` at `0x18000d967`
- `ntdll!RtlTimeFieldsToTime` at `0x18000d82d`
- `ntdll!RtlTimeFieldsToTime` at `0x18000d82d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dac9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000db33`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dac9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000db33`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000da97`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000da97`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000d6d2`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000d6d2`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000d6b8`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000d6b8`
- `ntdll!RtlLengthSid` at `0x18000d6f5`
- `ntdll!RtlLengthSid` at `0x18000d706`
- `ntdll!RtlLengthSid` at `0x18000d7ac`
- `ntdll!RtlLengthSid` at `0x18000d7bd`
- `ntdll!RtlLengthSid` at `0x18000d7cf`
- `ntdll!RtlLengthSid` at `0x18000d7e0`
- `ntdll!RtlLengthSid` at `0x18000d868`
- `ntdll!RtlLengthSid` at `0x18000d8d0`
- `ntdll!RtlLengthSid` at `0x18000d900`
- `ntdll!RtlLengthSid` at `0x18000d92c`
- `ntdll!RtlLengthSid` at `0x18000db65`
- `ntdll!RtlLengthSid` at `0x18000db9b`
- `ntdll!RtlLengthSid` at `0x18000d6f5`
- `ntdll!RtlLengthSid` at `0x18000d706`
- `ntdll!RtlLengthSid` at `0x18000d7ac`
- `ntdll!RtlLengthSid` at `0x18000d7bd`
- `ntdll!RtlLengthSid` at `0x18000d7cf`
- `ntdll!RtlLengthSid` at `0x18000d7e0`
- `ntdll!RtlLengthSid` at `0x18000d868`
- `ntdll!RtlLengthSid` at `0x18000d8d0`
- `ntdll!RtlLengthSid` at `0x18000d900`
- `ntdll!RtlLengthSid` at `0x18000d92c`
- `ntdll!RtlLengthSid` at `0x18000db65`
- `ntdll!RtlLengthSid` at `0x18000db9b`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d5c3`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d5c3`
- `ntdll!RtlEnterCriticalSection` at `0x18000d594`
- `ntdll!RtlEnterCriticalSection` at `0x18000d594`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIGetResourceGroupMembershipsTransitive` at `0x18000d767`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIGetResourceGroupMembershipsTransitive` at `0x18000d767`

## pseudocode

```c
__int64 __fastcall NegpMakeServiceToken(
        int a1,
        struct _LUID *a2,
        void **a3,
        unsigned int *a4,
        int *a5,
        enum _LSA_TOKEN_INFORMATION_TYPE *a6,
        void **a7,
        struct _UNICODE_STRING **a8,
        struct _UNICODE_STRING **a9,
        struct _UNICODE_STRING **a10,
        struct _SECPKG_PRIMARY_CRED *a11,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a12)
{
  struct _RTL_BALANCED_NODE **v13; // r13
  struct _RTL_BALANCED_NODE **v14; // r14
  struct _LSAP_LOGON_SESSION *LogonSession; // r15
  __int64 v17; // rdx
  int ClientInfo; // ebx
  void *v19; // r14
  struct _RTL_BALANCED_NODE **v20; // rdi
  struct _RTL_BALANCED_NODE *UserSid; // rcx
  int v23; // eax
  ULONG v24; // edi
  ULONG v25; // r13d
  __int64 v26; // rcx
  __int64 v27; // r8
  void *v28; // rbx
  struct _SAMPR_PSID_ARRAY *v29; // rcx
  ULONG v30; // r13d
  int v31; // r12d
  __int64 v32; // rbx
  void *v33; // rbx
  ULONG v34; // edi
  ULONG v35; // eax
  union _LARGE_INTEGER *v36; // rax
  union _LARGE_INTEGER *v37; // r12
  union _LARGE_INTEGER *v38; // r12
  __int64 v39; // rcx
  union _LARGE_INTEGER *v40; // rdi
  ULONG v41; // eax
  __int64 v42; // rsi
  char *v43; // rsi
  __int64 v44; // r13
  struct _SAMPR_PSID_ARRAY *i; // rcx
  __int64 v46; // rdi
  ULONG v47; // eax
  __int64 v48; // rbx
  char *v49; // rsi
  ULONG v50; // eax
  __int64 v51; // rbx
  char *v52; // rsi
  ULONG v53; // eax
  __int64 v54; // rbx
  ULONG v55; // edx
  struct _ACL *v56; // rbx
  void **v57; // rax
  DWORD v58; // eax
  unsigned __int8 IsRunning; // al
  ULONG v60; // eax
  ULONG v61; // eax
  __int64 v62; // rdi
  __int64 v63; // rcx
  void *v64; // rdx
  void *v65; // rdx
  void *v66; // rdx
  struct _SAMPR_PSID_ARRAY *v67; // [rsp+48h] [rbp-A1h] BYREF
  ULONG AclSize; // [rsp+50h] [rbp-99h]
  struct _UNICODE_STRING **v69; // [rsp+58h] [rbp-91h]
  _OWORD v70[2]; // [rsp+60h] [rbp-89h] BYREF
  void *v71; // [rsp+80h] [rbp-69h] BYREF
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v72; // [rsp+88h] [rbp-61h]
  int *v73; // [rsp+90h] [rbp-59h]
  void **v74; // [rsp+98h] [rbp-51h]
  unsigned int *v75; // [rsp+A0h] [rbp-49h]
  enum _LSA_TOKEN_INFORMATION_TYPE *v76; // [rsp+A8h] [rbp-41h]
  void **v77; // [rsp+B0h] [rbp-39h]
  struct _UNICODE_STRING **v78; // [rsp+B8h] [rbp-31h]
  __int128 v79; // [rsp+C0h] [rbp-29h] BYREF
  struct _TIME_FIELDS TimeFields; // [rsp+D0h] [rbp-19h] BYREF

  v13 = (struct _RTL_BALANCED_NODE **)a8;
  v14 = (struct _RTL_BALANCED_NODE **)a10;
  v73 = a5;
  v76 = a6;
  LogonSession = 0;
  v77 = a7;
  v78 = a9;
  v71 = 0;
  v67 = 0;
  v75 = a4;
  *a12 = 0;
  v74 = a3;
  v69 = a8;
  v72 = a12;
  TimeFields = 0;
  memset(v70, 0, sizeof(v70));
  v79 = 0;
  ClientInfo = LsapGetClientInfoEx((struct _SECPKG_CLIENT_INFO_EX *)v70, 0x20u);
  if ( ClientInfo < 0 )
    goto LABEL_7;
  if ( *(_QWORD *)&v70[0] != 999 )
  {
    ClientInfo = -1073741790;
    goto LABEL_7;
  }
  v17 = 8216;
  if ( a1 != 8216 )
  {
    if ( a1 == 8217 )
    {
      v19 = (void *)*((_QWORD *)WellKnownSids + 162);
      RtlEnterCriticalSection(&NegComputerNamesLock);
      ClientInfo = NegpCopyCredsToBuffer(&NegPrimarySystemCredentials, NegSupplementalSystemCredentials, a11, v72);
      RtlLeaveCriticalSection(&NegComputerNamesLock);
      if ( ClientInfo < 0 )
      {
LABEL_6:
        v14 = (struct _RTL_BALANCED_NODE **)a10;
LABEL_7:
        v20 = (struct _RTL_BALANCED_NODE **)v78;
        if ( *v78 )
        {
          LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)(*v78)->Buffer, (void *)v17);
          LsapSubProv_FreeRoutine(*v20, v64);
          *v20 = 0;
        }
        if ( *v13 )
        {
          LsapSubProv_FreeRoutine((*v13)->Children[1], (void *)v17);
          LsapSubProv_FreeRoutine(*v13, v65);
          *v13 = 0;
        }
        if ( *v14 )
        {
          LsapSubProv_FreeRoutine((*v14)->Children[1], (void *)v17);
          LsapSubProv_FreeRoutine(*v14, v66);
          *v14 = 0;
        }
        NegpFreePrimaryCred(a11);
        LsapFreeSupplementalCredentials(v72);
        LsapSamExtFreeSidArray(v67);
        if ( LogonSession )
          LsapReleaseLogonSession(LogonSession);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, 0);
        *v73 = ClientInfo;
        return (unsigned int)ClientInfo;
      }
      a11->LogonId = (LUID)996LL;
      *a2 = (struct _LUID)996LL;
      UserSid = (struct _RTL_BALANCED_NODE *)a11->UserSid;
      if ( UserSid )
      {
        LsapSubProv_FreeRoutine(UserSid, (void *)v17);
        a11->UserSid = 0;
      }
      v23 = LsapDuplicateSid(&a11->UserSid, v19);
      goto LABEL_19;
    }
    if ( a1 != 8225 )
    {
      ClientInfo = -1073741729;
      goto LABEL_7;
    }
  }
  v70[0] = 0u;
  if ( a1 == 8216 )
    v19 = (void *)*((_QWORD *)WellKnownSids + 156);
  else
    v19 = (void *)*((_QWORD *)WellKnownSids + 168);
  v58 = 997;
  if ( a1 != 8216 )
    v58 = 995;
  a11->LogonId.LowPart = v58;
  a11->LogonId.HighPart = 0;
  a2->LowPart = v58;
  a2->HighPart = 0;
  ClientInfo = LsapDuplicateSid(&a11->UserSid, v19);
  if ( ClientInfo < 0 )
    goto LABEL_6;
  ClientInfo = LsapDuplicateString(&a11->DomainName, v70);
  if ( ClientInfo < 0 )
    goto LABEL_6;
  ClientInfo = LsapDuplicateString(&a11->DownlevelName, v70);
  if ( ClientInfo < 0 )
    goto LABEL_6;
  v23 = LsapDuplicateString(&a11->Password, v70);
LABEL_19:
  ClientInfo = v23;
  if ( v23 < 0 )
    goto LABEL_6;
  RtlAcquireSRWLockShared(&qword_1801A0930);
  LogonSession = LsapLocateLogonSession(a2);
  RtlReleaseSRWLockShared(&qword_1801A0930);
  if ( !LogonSession )
  {
    RtlAcquireSRWLockExclusive(&qword_1801A0930);
    LogonSession = LsapLocateLogonSession(a2);
    if ( LogonSession )
    {
      RtlReleaseSRWLockExclusive(&qword_1801A0930);
    }
    else
    {
      LsapCreateLogonSession(a2);
      LogonSession = LsapLocateLogonSession(a2);
      RtlReleaseSRWLockExclusive(&qword_1801A0930);
      if ( !LogonSession )
      {
        ClientInfo = -1073741729;
        goto LABEL_6;
      }
      if ( a2->LowPart == 996 && !a2->HighPart )
        LsapSetLogonSessionAccountInfo(a2, &a11->DownlevelName, &a11->DomainName, 0, a11->UserSid, Service, 0, a11);
    }
  }
  v24 = RtlLengthSid(*((PSID *)WellKnownSids + 90));
  v25 = RtlLengthSid(v19);
  ClientInfo = LsapWaitForSamForAwhile();
  if ( ClientInfo < 0 )
    goto LABEL_53;
  if ( LsapProductType != NtProductLanManNt
    || (IsRunning = LsapSamExtDsIsRunning(), v28 = LsapLocalAccountDomainHandle, IsRunning) )
  {
    v28 = LsapAccountDomainHandle;
  }
  v71 = v19;
  *((_QWORD *)&v79 + 1) = &v71;
  LODWORD(v79) = 1;
  if ( !(unsigned __int8)IsSamIDecodeClaimsBlobPresent(v26, v17, v27) )
  {
    ClientInfo = -1073741637;
    goto LABEL_53;
  }
  ClientInfo = SamIGetResourceGroupMembershipsTransitive(v28, &v79, 0, &v67);
  if ( ClientInfo < 0 )
  {
LABEL_53:
    v13 = (struct _RTL_BALANCED_NODE **)v69;
    goto LABEL_6;
  }
  v29 = v67;
  v30 = v24 + v25 + 24;
  v31 = 0;
  v32 = 0;
  for ( AclSize = v30; (unsigned int)v32 < *(_DWORD *)v67; v31 += v60 )
  {
    v60 = RtlLengthSid(*(PSID *)(*((_QWORD *)v29 + 1) + 8 * v32));
    v29 = v67;
    v32 = (unsigned int)(v32 + 1);
  }
  v33 = (void *)*((_QWORD *)WellKnownSids + 102);
  v34 = RtlLengthSid(v19);
  LODWORD(v33) = v34 + RtlLengthSid(v33);
  LODWORD(v33) = RtlLengthSid(v19) + (_DWORD)v33;
  v35 = RtlLengthSid(v19);
  v36 = (union _LARGE_INTEGER *)LsapAllocate((_DWORD)v33 + v35 + 88 + v31 + v30 + 16 * *(_DWORD *)v67);
  *(_QWORD *)&v70[0] = v36;
  v37 = v36;
  if ( !v36 )
  {
    ClientInfo = -1073741801;
    goto LABEL_53;
  }
  TimeFields = (struct _TIME_FIELDS)_mm_load_si128((const __m128i *)&_xmm);
  RtlTimeFieldsToTime(&TimeFields, v36);
  v38 = v37 + 8;
  v39 = *(unsigned int *)v67;
  v38->LowPart = v39 + 1;
  v40 = &v38[2 * v39 + 3];
  v41 = RtlLengthSid(*((PSID *)WellKnownSids + 102));
  v42 = v41;
  RtlCopySid(v41, v40, *((PSID *)WellKnownSids + 102));
  v38[1].QuadPart = (LONGLONG)v40;
  v43 = (char *)v40 + v42;
  v38[2].LowPart = 7;
  v44 = 0;
  for ( i = v67; (unsigned int)v44 < *(_DWORD *)v67; i = v67 )
  {
    v61 = RtlLengthSid(*(PSID *)(*((_QWORD *)i + 1) + 8 * v44));
    v62 = v61;
    RtlCopySid(v61, v43, *(PSID *)(*((_QWORD *)v67 + 1) + 8 * v44));
    v44 = (unsigned int)(v44 + 1);
    v63 = 2LL * (unsigned int)v44;
    v38[v63 + 1].QuadPart = (LONGLONG)v43;
    v43 += v62;
    v38[v63 + 2].LowPart = 536870919;
  }
  LsapSamExtFreeSidArray(i);
  v46 = *(_QWORD *)&v70[0];
  v67 = 0;
  *(_QWORD *)(*(_QWORD *)&v70[0] + 24LL) = v38;
  v47 = RtlLengthSid(v19);
  v48 = v47;
  RtlCopySid(v47, v43, v19);
  *(_QWORD *)(v46 + 8) = v43;
  *(_DWORD *)(v46 + 16) = 0;
  v49 = &v43[v48];
  v50 = RtlLengthSid(v19);
  v51 = v50;
  RtlCopySid(v50, v49, v19);
  *(_QWORD *)(v46 + 32) = v49;
  v52 = &v49[v51];
  v53 = RtlLengthSid(v19);
  v54 = v53;
  RtlCopySid(v53, v52, v19);
  v55 = AclSize;
  v56 = (struct _ACL *)&v52[v54];
  *(_QWORD *)(v46 + 48) = v52;
  *(_QWORD *)(v46 + 40) = 0;
  RtlCreateAcl(v56, v55, 2u);
  RtlAddAccessAllowedAce(v56, 2u, 0x10000000u, *((PSID *)WellKnownSids + 90));
  RtlAddAccessAllowedAce(v56, 2u, 0x10000000u, v19);
  v57 = v74;
  *(_QWORD *)(v46 + 56) = v56;
  *v57 = 0;
  *v75 = 0;
  *v76 = LsaTokenInformationV2;
  *v77 = (void *)v46;
  LsapReleaseLogonSession(LogonSession);
  *v73 = 0;
  return 0;
}

```

## disassembly

```asm
0x18000d48c  mov     [rsp-8+arg_0], rbx
0x18000d491  push    rbp
0x18000d492  push    rsi
0x18000d493  push    rdi
0x18000d494  push    r12
0x18000d496  push    r13
0x18000d498  push    r14
0x18000d49a  push    r15
0x18000d49c  lea     rbp, [rsp-7]
0x18000d4a1  sub     rsp, 0F0h
0x18000d4a8  mov     rax, cs:__security_cookie
0x18000d4af  xor     rax, rsp
0x18000d4b2  mov     [rbp+37h+var_40], rax
0x18000d4b6  mov     rax, [rbp+37h+arg_20]
0x18000d4ba  mov     r12d, ecx
0x18000d4bd  mov     r13, [rbp+37h+arg_38]
0x18000d4c1  xor     ecx, ecx
0x18000d4c3  mov     r14, [rbp+37h+arg_48]
0x18000d4ca  xorps   xmm0, xmm0
0x18000d4cd  mov     rsi, [rbp+37h+arg_50]
0x18000d4d4  xorps   xmm1, xmm1
0x18000d4d7  mov     [rbp+37h+var_90], rax
0x18000d4db  mov     rdi, rdx
0x18000d4de  mov     rax, [rbp+37h+arg_28]
0x18000d4e2  lea     edx, [rcx+20h]; Size
0x18000d4e5  mov     [rbp+37h+var_78], rax
0x18000d4e9  mov     r15d, ecx
0x18000d4ec  mov     rax, [rbp+37h+arg_30]
0x18000d4f0  mov     [rbp+37h+var_70], rax
0x18000d4f4  mov     rax, [rbp+37h+arg_40]
0x18000d4fb  mov     [rbp+37h+var_68], rax
0x18000d4ff  mov     rax, [rbp+37h+arg_58]
0x18000d506  mov     [rbp+37h+var_A0], rcx
0x18000d50a  mov     [rsp+120h+var_D8], rcx
0x18000d50f  mov     [rbp+37h+var_80], r9
0x18000d513  mov     [rax], rcx
0x18000d516  lea     rcx, [rsp+120h+var_C0]; struct _SECPKG_CLIENT_INFO_EX *
0x18000d51b  mov     [rbp+37h+var_88], r8
0x18000d51f  mov     [rsp+120h+var_C8], r13
0x18000d524  mov     [rsp+120h+var_E0], r14
0x18000d529  mov     [rbp+37h+var_98], rax
0x18000d52d  movups  xmmword ptr [rbp+37h+TimeFields.Year], xmm0
0x18000d531  movups  [rsp+120h+var_C0], xmm1
0x18000d536  movups  [rbp+37h+var_B0], xmm1
0x18000d53a  movups  [rbp+37h+var_60], xmm0
0x18000d53e  call    ?LsapGetClientInfoEx@@YAJPEAU_SECPKG_CLIENT_INFO_EX@@K@Z; LsapGetClientInfoEx(_SECPKG_CLIENT_INFO_EX *,ulong)
0x18000d543  mov     ebx, eax
0x18000d545  test    eax, eax
0x18000d547  js      loc_18000D5DC
0x18000d54d  cmp     dword ptr [rsp+120h+var_C0], 3E7h
0x18000d555  jnz     loc_18000DBF7
0x18000d55b  cmp     dword ptr [rsp+120h+var_C0+4], r15d
0x18000d560  jnz     loc_18000DBF7
0x18000d566  mov     eax, r12d
0x18000d569  mov     edx, 2018h
0x18000d56e  sub     eax, edx
0x18000d570  jz      loc_18000D9F2
0x18000d576  sub     eax, 1
0x18000d579  jnz     loc_18000D9E9
0x18000d57f  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18000d586  lea     rcx, ?NegComputerNamesLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000d58d  mov     r14, [rax+510h]
0x18000d594  call    cs:__imp_RtlEnterCriticalSection
0x18000d59b  nop     dword ptr [rax+rax+00h]
0x18000d5a0  mov     r9, [rbp+37h+var_98]; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x18000d5a4  lea     rcx, ?NegPrimarySystemCredentials@@3U_SECPKG_PRIMARY_CRED@@A; struct _SECPKG_PRIMARY_CRED *
0x18000d5ab  mov     rdx, cs:?NegSupplementalSystemCredentials@@3PEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@EA; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *
0x18000d5b2  mov     r8, rsi; struct _SECPKG_PRIMARY_CRED *
0x18000d5b5  call    ?NegpCopyCredsToBuffer@@YAJPEAU_SECPKG_PRIMARY_CRED@@PEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@0PEAPEAU2@@Z; NegpCopyCredsToBuffer(_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x18000d5ba  lea     rcx, ?NegComputerNamesLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000d5c1  mov     ebx, eax
0x18000d5c3  call    cs:__imp_RtlLeaveCriticalSection
0x18000d5ca  nop     dword ptr [rax+rax+00h]
0x18000d5cf  test    ebx, ebx
0x18000d5d1  jns     loc_18000D677
0x18000d5d7  mov     r14, [rsp+120h+var_E0]
0x18000d5dc  mov     rdi, [rbp+37h+var_68]
0x18000d5e0  mov     rcx, [rdi]
0x18000d5e3  test    rcx, rcx
0x18000d5e6  jnz     loc_18000DC01
0x18000d5ec  mov     rcx, [r13+0]
0x18000d5f0  test    rcx, rcx
0x18000d5f3  jnz     loc_18000DC1E
0x18000d5f9  mov     rcx, [r14]
0x18000d5fc  test    rcx, rcx
0x18000d5ff  jnz     loc_18000DC3D
0x18000d605  mov     rcx, rsi; struct _SECPKG_PRIMARY_CRED *
0x18000d608  call    ?NegpFreePrimaryCred@@YAXPEAU_SECPKG_PRIMARY_CRED@@@Z; NegpFreePrimaryCred(_SECPKG_PRIMARY_CRED *)
0x18000d60d  mov     rcx, [rbp+37h+var_98]; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x18000d611  call    ?LsapFreeSupplementalCredentials@@YAXPEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z; LsapFreeSupplementalCredentials(_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x18000d616  mov     rcx, [rsp+120h+var_D8]; struct _SAMPR_PSID_ARRAY *
0x18000d61b  call    ?LsapSamExtFreeSidArray@@YAXPEAU_SAMPR_PSID_ARRAY@@@Z; LsapSamExtFreeSidArray(_SAMPR_PSID_ARRAY *)
0x18000d620  test    r15, r15
0x18000d623  jnz     loc_18000DC5A
0x18000d629  mov     rcx, gs:60h
0x18000d632  xor     r8d, r8d; P
0x18000d635  xor     edx, edx; Flags
0x18000d637  mov     rcx, [rcx+30h]; HeapHandle
0x18000d63b  call    cs:__imp_RtlFreeHeap
0x18000d642  nop     dword ptr [rax+rax+00h]
0x18000d647  mov     rax, [rbp+37h+var_90]
0x18000d64b  mov     [rax], ebx
0x18000d64d  mov     eax, ebx
0x18000d64f  mov     rcx, [rbp+37h+var_40]
0x18000d653  xor     rcx, rsp; StackCookie
0x18000d656  call    __security_check_cookie
0x18000d65b  mov     rbx, [rsp+120h+arg_0]
0x18000d663  add     rsp, 0F0h
0x18000d66a  pop     r15
0x18000d66c  pop     r14
0x18000d66e  pop     r13
0x18000d670  pop     r12
0x18000d672  pop     rdi
0x18000d673  pop     rsi
0x18000d674  pop     rbp
0x18000d675  retn
0x18000d677  mov     qword ptr [rsi], 3E4h
0x18000d67e  lea     rbx, [rsi+48h]
0x18000d682  mov     qword ptr [rdi], 3E4h
0x18000d689  mov     rcx, [rbx]; struct _RTL_BALANCED_NODE *
0x18000d68c  test    rcx, rcx
0x18000d68f  jz      short loc_18000D699
0x18000d691  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18000d696  mov     [rbx], r15
0x18000d699  mov     rdx, r14
0x18000d69c  mov     rcx, rbx
0x18000d69f  call    LsapDuplicateSid
0x18000d6a4  mov     ebx, eax
0x18000d6a6  test    eax, eax
0x18000d6a8  js      loc_18000D5D7
0x18000d6ae  lea     rbx, qword_1801A0930
0x18000d6b5  mov     rcx, rbx
0x18000d6b8  call    cs:__imp_RtlAcquireSRWLockShared
0x18000d6bf  nop     dword ptr [rax+rax+00h]
0x18000d6c4  mov     rcx, rdi; struct _LUID *
0x18000d6c7  call    ?LsapLocateLogonSession@@YAPEAU_LSAP_LOGON_SESSION@@PEAU_LUID@@@Z; LsapLocateLogonSession(_LUID *)
0x18000d6cc  mov     rcx, rbx
0x18000d6cf  mov     r15, rax
0x18000d6d2  call    cs:__imp_RtlReleaseSRWLockShared
0x18000d6d9  nop     dword ptr [rax+rax+00h]
0x18000d6de  test    r15, r15
0x18000d6e1  jz      loc_18000DA94
0x18000d6e7  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18000d6ee  mov     rcx, [rcx+2D0h]; Sid
0x18000d6f5  call    cs:__imp_RtlLengthSid
0x18000d6fc  nop     dword ptr [rax+rax+00h]
0x18000d701  mov     rcx, r14; Sid
0x18000d704  mov     edi, eax
0x18000d706  call    cs:__imp_RtlLengthSid
0x18000d70d  nop     dword ptr [rax+rax+00h]
0x18000d712  mov     r13d, eax
0x18000d715  call    ?LsapWaitForSamForAwhile@@YAJXZ; LsapWaitForSamForAwhile(void)
0x18000d71a  mov     ebx, eax
0x18000d71c  test    eax, eax
0x18000d71e  js      loc_18000DB89
0x18000d724  cmp     cs:LsapProductType, 2
0x18000d72b  jz      loc_18000DB44
0x18000d731  mov     rbx, cs:?LsapAccountDomainHandle@@3PEAXEA; void * LsapAccountDomainHandle
0x18000d738  lea     rax, [rbp+37h+var_A0]
0x18000d73c  mov     [rbp+37h+var_A0], r14
0x18000d740  mov     qword ptr [rbp+37h+var_60+8], rax
0x18000d744  mov     dword ptr [rbp+37h+var_60], 1
0x18000d74b  call    IsSamIDecodeClaimsBlobPresent
0x18000d750  test    al, al
0x18000d752  jz      loc_18000DBF0
0x18000d758  lea     r9, [rsp+120h+var_D8]
0x18000d75d  xor     r8d, r8d
0x18000d760  lea     rdx, [rbp+37h+var_60]
0x18000d764  mov     rcx, rbx
0x18000d767  call    cs:__imp_SamIGetResourceGroupMembershipsTransitive
0x18000d76e  nop     dword ptr [rax+rax+00h]
0x18000d773  mov     ebx, eax
0x18000d775  test    eax, eax
0x18000d777  js      loc_18000DB89
0x18000d77d  mov     rcx, [rsp+120h+var_D8]
0x18000d782  add     r13d, 18h
0x18000d786  add     r13d, edi
0x18000d789  xor     r12d, r12d
0x18000d78c  xor     ebx, ebx
0x18000d78e  mov     [rsp+120h+AclSize], r13d
0x18000d793  cmp     [rcx], ebx
0x18000d795  ja      loc_18000DB5D
0x18000d79b  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18000d7a2  mov     rcx, r14; Sid
0x18000d7a5  mov     rbx, [rax+330h]
0x18000d7ac  call    cs:__imp_RtlLengthSid
0x18000d7b3  nop     dword ptr [rax+rax+00h]
0x18000d7b8  mov     rcx, rbx; Sid
0x18000d7bb  mov     edi, eax
0x18000d7bd  call    cs:__imp_RtlLengthSid
0x18000d7c4  nop     dword ptr [rax+rax+00h]
0x18000d7c9  mov     rcx, r14; Sid
0x18000d7cc  lea     ebx, [rdi+rax]
0x18000d7cf  call    cs:__imp_RtlLengthSid
0x18000d7d6  nop     dword ptr [rax+rax+00h]
0x18000d7db  mov     rcx, r14; Sid
0x18000d7de  add     ebx, eax
0x18000d7e0  call    cs:__imp_RtlLengthSid
0x18000d7e7  nop     dword ptr [rax+rax+00h]
0x18000d7ec  lea     edx, [rax+58h]
0x18000d7ef  mov     rax, [rsp+120h+var_D8]
0x18000d7f4  add     edx, ebx
0x18000d7f6  mov     ecx, [rax]
0x18000d7f8  shl     ecx, 4
0x18000d7fb  add     ecx, r13d
0x18000d7fe  add     ecx, r12d
0x18000d801  add     ecx, edx
0x18000d803  call    LsapAllocate
0x18000d808  mov     qword ptr [rsp+120h+var_C0], rax
0x18000d80d  mov     r12, rax
0x18000d810  test    rax, rax
0x18000d813  jz      loc_18000DB84
0x18000d819  movdqa  xmm0, cs:__xmm@00010001000100010001000100010bb8
0x18000d821  lea     rcx, [rbp+37h+TimeFields]; TimeFields
0x18000d825  mov     rdx, rax; Time
0x18000d828  movdqu  xmmword ptr [rbp+37h+TimeFields.Year], xmm0
0x18000d82d  call    cs:__imp_RtlTimeFieldsToTime
0x18000d834  nop     dword ptr [rax+rax+00h]
0x18000d839  mov     rax, [rsp+120h+var_D8]
0x18000d83e  add     r12, 40h ; '@'
0x18000d842  mov     ecx, [rax]
0x18000d844  lea     eax, [rcx+1]
0x18000d847  lea     rdi, [rcx+1]
0x18000d84b  mov     [r12], eax
0x18000d84f  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18000d856  shl     rdi, 4
0x18000d85a  add     rdi, 8
0x18000d85e  add     rdi, r12
0x18000d861  mov     rcx, [rcx+330h]; Sid
0x18000d868  call    cs:__imp_RtlLengthSid
0x18000d86f  nop     dword ptr [rax+rax+00h]
0x18000d874  mov     r8, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18000d87b  mov     rdx, rdi; DestinationSid
0x18000d87e  mov     ecx, eax; DestinationSidLength
0x18000d880  mov     esi, eax
0x18000d882  mov     r8, [r8+330h]; SourceSid
0x18000d889  call    cs:__imp_RtlCopySid
0x18000d890  nop     dword ptr [rax+rax+00h]
0x18000d895  mov     [r12+8], rdi
0x18000d89a  add     rsi, rdi
0x18000d89d  mov     dword ptr [r12+10h], 7
0x18000d8a6  xor     r13d, r13d
0x18000d8a9  mov     rcx, [rsp+120h+var_D8]; struct _SAMPR_PSID_ARRAY *
0x18000d8ae  cmp     [rcx], r13d
0x18000d8b1  ja      loc_18000DB93
0x18000d8b7  call    ?LsapSamExtFreeSidArray@@YAXPEAU_SAMPR_PSID_ARRAY@@@Z; LsapSamExtFreeSidArray(_SAMPR_PSID_ARRAY *)
0x18000d8bc  mov     rdi, qword ptr [rsp+120h+var_C0]
0x18000d8c1  xor     r13d, r13d
0x18000d8c4  mov     [rsp+120h+var_D8], r13
0x18000d8c9  mov     rcx, r14; Sid
0x18000d8cc  mov     [rdi+18h], r12
0x18000d8d0  call    cs:__imp_RtlLengthSid
0x18000d8d7  nop     dword ptr [rax+rax+00h]
0x18000d8dc  mov     r8, r14; SourceSid
0x18000d8df  mov     rdx, rsi; DestinationSid
0x18000d8e2  mov     ecx, eax; DestinationSidLength
0x18000d8e4  mov     ebx, eax
0x18000d8e6  call    cs:__imp_RtlCopySid
0x18000d8ed  nop     dword ptr [rax+rax+00h]
0x18000d8f2  mov     [rdi+8], rsi
0x18000d8f6  mov     rcx, r14; Sid
0x18000d8f9  mov     [rdi+10h], r13d
0x18000d8fd  add     rsi, rbx
0x18000d900  call    cs:__imp_RtlLengthSid
0x18000d907  nop     dword ptr [rax+rax+00h]
0x18000d90c  mov     r8, r14; SourceSid
0x18000d90f  mov     rdx, rsi; DestinationSid
0x18000d912  mov     ecx, eax; DestinationSidLength
0x18000d914  mov     ebx, eax
0x18000d916  call    cs:__imp_RtlCopySid
0x18000d91d  nop     dword ptr [rax+rax+00h]
0x18000d922  mov     [rdi+20h], rsi
0x18000d926  mov     rcx, r14; Sid
0x18000d929  add     rsi, rbx
0x18000d92c  call    cs:__imp_RtlLengthSid
0x18000d933  nop     dword ptr [rax+rax+00h]
0x18000d938  mov     r8, r14; SourceSid
0x18000d93b  mov     rdx, rsi; DestinationSid
0x18000d93e  mov     ecx, eax; DestinationSidLength
0x18000d940  mov     ebx, eax
0x18000d942  call    cs:__imp_RtlCopySid
0x18000d949  nop     dword ptr [rax+rax+00h]
0x18000d94e  mov     edx, [rsp+120h+AclSize]; AclSize
0x18000d952  lea     r12d, [r13+2]
0x18000d956  add     rbx, rsi
0x18000d959  mov     [rdi+30h], rsi
0x18000d95d  mov     r8d, r12d; AclRevision
0x18000d960  mov     [rdi+28h], r13
0x18000d964  mov     rcx, rbx; Acl
0x18000d967  call    cs:__imp_RtlCreateAcl
0x18000d96e  nop     dword ptr [rax+rax+00h]
0x18000d973  mov     r9, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18000d97a  mov     esi, 10000000h
0x18000d97f  mov     r8d, esi; AccessMask
0x18000d982  mov     edx, r12d; Revision
0x18000d985  mov     rcx, rbx; Acl
0x18000d988  mov     r9, [r9+2D0h]; Sid
0x18000d98f  call    cs:__imp_RtlAddAccessAllowedAce
0x18000d996  nop     dword ptr [rax+rax+00h]
0x18000d99b  mov     r9, r14; Sid
  ... truncated ...
```
