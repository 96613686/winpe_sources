# NegpMakeSystemToken(_LUID *,void * *,ulong *,long *,_LSA_TOKEN_INFORMATION_TYPE *,void * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x18000acb0`
- end: `0x18000b7c1`
- name: `?NegpMakeSystemToken@@YAJPEAU_LUID@@PEAPEAXPEAKPEAJPEAW4_LSA_TOKEN_INFORMATION_TYPE@@1PEAPEAU_UNICODE_STRING@@55PEAU_SECPKG_PRIMARY_CRED@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `2833`
- prototype: `__int64 __fastcall(struct _LUID *, void **, unsigned int *, int *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _SECPKG_PRIMARY_CRED *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009ac50`

## callees

- `0x18000acb0`
- `0x18000b7d0`
- `0x18000c0f0`
- `0x18000c300`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bd6e0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000add2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ae14`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000add2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ae14`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000aec0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000b79d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000aec0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000b79d`
- `ntdll!RtlFreeHeap` at `0x18000b328`
- `ntdll!RtlFreeHeap` at `0x18000b346`
- `ntdll!RtlFreeHeap` at `0x18000b373`
- `ntdll!RtlFreeHeap` at `0x18000b391`
- `ntdll!RtlFreeHeap` at `0x18000b3bc`
- `ntdll!RtlFreeHeap` at `0x18000b3db`
- `ntdll!RtlFreeHeap` at `0x18000b3fe`
- `ntdll!RtlFreeHeap` at `0x18000b421`
- `ntdll!RtlFreeHeap` at `0x18000b447`
- `ntdll!RtlFreeHeap` at `0x18000b490`
- `ntdll!RtlFreeHeap` at `0x18000b546`
- `ntdll!RtlFreeHeap` at `0x18000b5bb`
- `ntdll!RtlFreeHeap` at `0x18000b328`
- `ntdll!RtlFreeHeap` at `0x18000b346`
- `ntdll!RtlFreeHeap` at `0x18000b373`
- `ntdll!RtlFreeHeap` at `0x18000b391`
- `ntdll!RtlFreeHeap` at `0x18000b3bc`
- `ntdll!RtlFreeHeap` at `0x18000b3db`
- `ntdll!RtlFreeHeap` at `0x18000b3fe`
- `ntdll!RtlFreeHeap` at `0x18000b421`
- `ntdll!RtlFreeHeap` at `0x18000b447`
- `ntdll!RtlFreeHeap` at `0x18000b490`
- `ntdll!RtlFreeHeap` at `0x18000b546`
- `ntdll!RtlFreeHeap` at `0x18000b5bb`
- `ntdll!RtlCopySid` at `0x18000b171`
- `ntdll!RtlCopySid` at `0x18000b171`
- `ntdll!RtlAllocateHeap` at `0x18000b08f`
- `ntdll!RtlAllocateHeap` at `0x18000b61b`
- `ntdll!RtlAllocateHeap` at `0x18000b08f`
- `ntdll!RtlAllocateHeap` at `0x18000b61b`
- `ntdll!NtClose` at `0x18000b2e1`
- `ntdll!NtClose` at `0x18000b55c`
- `ntdll!NtClose` at `0x18000b2e1`
- `ntdll!NtClose` at `0x18000b55c`
- `ntdll!RtlImpersonateSelfEx` at `0x18000b664`
- `ntdll!RtlImpersonateSelfEx` at `0x18000b664`
- `ntdll!RtlTimeFieldsToTime` at `0x18000b0bf`
- `ntdll!RtlTimeFieldsToTime` at `0x18000b0bf`
- `ntdll!RtlLengthSid` at `0x18000b053`
- `ntdll!RtlLengthSid` at `0x18000b15b`
- `ntdll!RtlLengthSid` at `0x18000b5fb`
- `ntdll!RtlLengthSid` at `0x18000b053`
- `ntdll!RtlLengthSid` at `0x18000b15b`
- `ntdll!RtlLengthSid` at `0x18000b5fb`
- `ntdll!RtlEqualSid` at `0x18000b594`
- `ntdll!RtlEqualSid` at `0x18000b594`
- `ntdll!RtlLeaveCriticalSection` at `0x18000af0f`
- `ntdll!RtlLeaveCriticalSection` at `0x18000af0f`
- `ntdll!RtlEnterCriticalSection` at `0x18000aedb`
- `ntdll!RtlEnterCriticalSection` at `0x18000aedb`
- `ntdll!NtSetInformationThread` at `0x18000b702`
- `ntdll!NtSetInformationThread` at `0x18000b731`
- `ntdll!NtSetInformationThread` at `0x18000b702`
- `ntdll!NtSetInformationThread` at `0x18000b731`
- `ntdll!NtQueryInformationToken` at `0x18000af6b`
- `ntdll!NtQueryInformationToken` at `0x18000af9e`
- `ntdll!NtQueryInformationToken` at `0x18000afd1`
- `ntdll!NtQueryInformationToken` at `0x18000b004`
- `ntdll!NtQueryInformationToken` at `0x18000b037`
- `ntdll!NtQueryInformationToken` at `0x18000b0ec`
- `ntdll!NtQueryInformationToken` at `0x18000b135`
- `ntdll!NtQueryInformationToken` at `0x18000b1b5`
- `ntdll!NtQueryInformationToken` at `0x18000b1fb`
- `ntdll!NtQueryInformationToken` at `0x18000b245`
- `ntdll!NtQueryInformationToken` at `0x18000af6b`
- `ntdll!NtQueryInformationToken` at `0x18000af9e`
- `ntdll!NtQueryInformationToken` at `0x18000afd1`
- `ntdll!NtQueryInformationToken` at `0x18000b004`
- `ntdll!NtQueryInformationToken` at `0x18000b037`
- `ntdll!NtQueryInformationToken` at `0x18000b0ec`
- `ntdll!NtQueryInformationToken` at `0x18000b135`
- `ntdll!NtQueryInformationToken` at `0x18000b1b5`
- `ntdll!NtQueryInformationToken` at `0x18000b1fb`
- `ntdll!NtQueryInformationToken` at `0x18000b245`
- `ntdll!NtOpenThreadToken` at `0x18000ae88`
- `ntdll!NtOpenThreadToken` at `0x18000aeb2`
- `ntdll!NtOpenThreadToken` at `0x18000ae88`
- `ntdll!NtOpenThreadToken` at `0x18000aeb2`
- `RPCRT4!RpcRevertToSelf` at `0x18000b78f`
- `RPCRT4!RpcRevertToSelf` at `0x18000b78f`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000ae5a`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000ae5a`
- `RPCRT4!RpcImpersonateClient` at `0x18000ae38`
- `RPCRT4!RpcImpersonateClient` at `0x18000ae38`
- `lsass!LsaImpersonateKsecCaller` at `0x18000b6c8`
- `lsass!LsaImpersonateKsecCaller` at `0x18000b6c8`

## pseudocode

```c
__int64 __fastcall NegpMakeSystemToken(
        struct _LUID *a1,
        void **a2,
        unsigned int *a3,
        int *a4,
        enum _LSA_TOKEN_INFORMATION_TYPE *a5,
        void **a6,
        struct _UNICODE_STRING **a7,
        struct _UNICODE_STRING **a8,
        struct _UNICODE_STRING **a9,
        struct _SECPKG_PRIMARY_CRED *a10,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a11)
{
  __int64 v13; // rsi
  int ClientInfo; // eax
  struct _HANDLE_PACKAGE *v15; // rax
  void *v16; // rcx
  __int64 (__fastcall *v17)(void *, _TIME_FIELDS *); // rax
  char *Value; // rax
  int v19; // edi
  void **v20; // rbx
  int v21; // esi
  _DWORD *v22; // rax
  RPC_STATUS v23; // eax
  NTSTATUS v24; // eax
  NTSTATUS v25; // eax
  NTSTATUS v26; // ebx
  struct _SECPKG_PRIMARY_CRED *v27; // rdi
  PSID UserSid; // rdx
  void *v29; // rsi
  NTSTATUS v30; // eax
  NTSTATUS v31; // eax
  NTSTATUS v32; // eax
  NTSTATUS v33; // eax
  NTSTATUS v34; // eax
  ULONG v35; // eax
  union _LARGE_INTEGER *v36; // rax
  union _LARGE_INTEGER *v37; // rbx
  void *v38; // rbx
  NTSTATUS v39; // eax
  void *v40; // rdi
  ULONG v41; // ebx
  _DWORD *v42; // rsi
  _QWORD *v43; // rbx
  _QWORD *v44; // rbx
  _QWORD *v45; // rbx
  unsigned int *v46; // rax
  _BYTE *Buffer; // rax
  __int64 MaximumLength; // rcx
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v50; // rdi
  struct _RTL_BALANCED_NODE *v51; // rdx
  ULONG v52; // r8d
  __int64 v53; // rax
  __int64 v54; // rcx
  struct _RTL_BALANCED_NODE *i; // rax
  ULONG v56; // ebx
  PVOID Heap; // rax
  __int64 v58; // [rsp+38h] [rbp-A9h]
  ULONG v59; // [rsp+40h] [rbp-A1h] BYREF
  ULONG v60; // [rsp+44h] [rbp-9Dh] BYREF
  ULONG v61; // [rsp+48h] [rbp-99h] BYREF
  ULONG TokenInformationLength; // [rsp+4Ch] [rbp-95h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-91h] BYREF
  ULONG ReturnLength; // [rsp+58h] [rbp-89h] BYREF
  struct _SECPKG_PRIMARY_CRED *v65; // [rsp+60h] [rbp-81h]
  PVOID P; // [rsp+68h] [rbp-79h]
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v67; // [rsp+70h] [rbp-71h]
  int *v68; // [rsp+78h] [rbp-69h]
  unsigned int *v69; // [rsp+80h] [rbp-61h]
  enum _LSA_TOKEN_INFORMATION_TYPE *v70; // [rsp+88h] [rbp-59h]
  void **v71; // [rsp+90h] [rbp-51h] BYREF
  __int64 v72; // [rsp+98h] [rbp-49h]
  _TIME_FIELDS v73; // [rsp+A0h] [rbp-41h] BYREF
  _TIME_FIELDS TimeFields; // [rsp+C0h] [rbp-21h] BYREF

  v70 = a5;
  v71 = a6;
  v69 = a3;
  v13 = 0;
  TokenHandle = 0;
  v61 = 0;
  TokenInformationLength = 0;
  v60 = 0;
  v59 = 0;
  ReturnLength = 0;
  P = 0;
  v68 = a4;
  v65 = a10;
  v67 = a11;
  TimeFields = 0;
  memset(&v73, 0, 32);
  memset_0(a10, 0, sizeof(struct _SECPKG_PRIMARY_CRED));
  *a11 = 0;
  ClientInfo = LsapGetClientInfoEx((struct _SECPKG_CLIENT_INFO_EX *)&v73, 0x20u);
  if ( ClientInfo < 0 )
  {
    v27 = v65;
    v26 = ClientInfo;
    goto LABEL_42;
  }
  if ( *(_QWORD *)&v73.Year != 999 )
  {
    v27 = v65;
    v26 = -1073741790;
    goto LABEL_42;
  }
  v15 = LogonSessionPackage;
  v16 = LogonSessionTable;
  *a1 = (struct _LUID)999LL;
  *(_QWORD *)&v73.Year = 0;
  v17 = (__int64 (__fastcall *)(void *, _TIME_FIELDS *))*((_QWORD *)v15 + 9);
  *(_QWORD *)&v73.Minute = 999;
  v58 = v17(v16, &v73);
  v13 = v58;
  if ( !v58 )
  {
    v27 = v65;
    v26 = -1073741729;
    goto LABEL_42;
  }
  Value = (char *)TlsGetValue(dwCallInfo);
  if ( !Value )
  {
    v26 = -1071513572;
    goto LABEL_94;
  }
  v19 = 0;
  v20 = (void **)(Value + 272);
  v21 = 0;
  if ( *((_QWORD *)Value + 34) )
  {
    if ( !Value[60] || *((int *)Value + 14) >= 2 )
    {
      v25 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, Value + 272, 8u);
      goto LABEL_15;
    }
    v26 = -1073741659;
LABEL_93:
    v13 = v58;
LABEL_94:
    v27 = v65;
    goto LABEL_42;
  }
  if ( *((_DWORD *)Value + 16) )
  {
    if ( *((_QWORD *)Value + 43) )
    {
      v24 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, Value + 344, 8u);
      if ( v24 >= 0 )
      {
        v19 = 1;
        goto LABEL_14;
      }
LABEL_92:
      v26 = v24;
      goto LABEL_93;
    }
LABEL_72:
    v25 = RtlImpersonateSelfEx(2, 0x2000000, v20);
    goto LABEL_15;
  }
  if ( (Value[32] & 0x20) != 0 )
  {
    v26 = -1073741558;
    goto LABEL_93;
  }
  v22 = TlsGetValue(dwSession);
  if ( !v22 )
    goto LABEL_72;
  if ( (v22[8] & 0x1000) == 0 || (int)LsaImpersonateKsecCaller(v20) < 0 )
  {
    v23 = RpcImpersonateClient(0);
    if ( v23 == 5 )
    {
      v26 = -1073741659;
      goto LABEL_93;
    }
    if ( v23 == 1765 )
    {
      v26 = -1073741769;
      goto LABEL_93;
    }
    v24 = I_RpcMapWin32Status(v23);
    if ( v24 >= 0 )
    {
      v19 = 1;
      v21 = 1;
LABEL_14:
      v25 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000000u, 1u, v20);
LABEL_15:
      v26 = v25;
      if ( v25 >= 0 )
        goto LABEL_16;
      if ( v19 )
      {
        if ( v21 )
          RpcRevertToSelf();
        else
          RevertToSelf();
      }
      goto LABEL_93;
    }
    goto LABEL_92;
  }
LABEL_16:
  v26 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  RevertToSelf();
  if ( v26 < 0 )
  {
LABEL_40:
    v27 = v65;
    goto LABEL_41;
  }
  RtlEnterCriticalSection(&NegComputerNamesLock);
  v27 = v65;
  v26 = NegpCopyCredsToBuffer(&NegPrimarySystemCredentials, NegSupplementalSystemCredentials, v65, v67);
  RtlLeaveCriticalSection(&NegComputerNamesLock);
  if ( v26 >= 0 )
  {
    UserSid = v27->UserSid;
    v27->LogonId = (LUID)999LL;
    v29 = (void *)*((_QWORD *)WellKnownSids + 90);
    if ( UserSid && !RtlEqualSid(*((PSID *)WellKnownSids + 90), UserSid) )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v27->UserSid);
      v27->UserSid = 0;
    }
    if ( !v27->UserSid )
    {
      v56 = RtlLengthSid(v29);
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v56);
      v27->UserSid = Heap;
      if ( !Heap )
      {
        v26 = -1073741670;
        goto LABEL_41;
      }
      memcpy_0(Heap, v29, v56);
    }
    v30 = NtQueryInformationToken(TokenHandle, TokenDefaultDacl, 0, 0, &ReturnLength);
    v26 = v30;
    if ( v30 != -2147483643 && v30 != -1073741789 )
      goto LABEL_41;
    v31 = NtQueryInformationToken(TokenHandle, TokenPrivileges, 0, 0, &v61);
    v26 = v31;
    if ( v31 != -2147483643 && v31 != -1073741789 )
      goto LABEL_41;
    v32 = NtQueryInformationToken(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength);
    v26 = v32;
    if ( v32 != -2147483643 && v32 != -1073741789 )
      goto LABEL_41;
    v33 = NtQueryInformationToken(TokenHandle, TokenPrimaryGroup, 0, 0, &v60);
    v26 = v33;
    if ( v33 != -2147483643 && v33 != -1073741789 )
      goto LABEL_41;
    v34 = NtQueryInformationToken(TokenHandle, TokenOwner, 0, 0, &v59);
    v26 = v34;
    if ( v34 != -2147483643 && v34 != -1073741789 )
      goto LABEL_41;
    v35 = RtlLengthSid(v29);
    v36 = (union _LARGE_INTEGER *)RtlAllocateHeap(
                                    NtCurrentPeb()->ProcessHeap,
                                    8u,
                                    TokenInformationLength + v60 + v59 + ReturnLength + v35 + v61 + 112);
    P = v36;
    v37 = v36;
    if ( !v36 )
    {
      v26 = -1073741801;
      goto LABEL_41;
    }
    TimeFields = (_TIME_FIELDS)_mm_load_si128((const __m128i *)&_xmm);
    RtlTimeFieldsToTime(&TimeFields, v36);
    v37[3].QuadPart = (LONGLONG)&v37[8];
    v26 = NtQueryInformationToken(TokenHandle, TokenGroups, &v37[8], TokenInformationLength, &TokenInformationLength);
    if ( v26 >= 0 )
    {
      v38 = (void *)(((unsigned __int64)P + TokenInformationLength + 71) & 0xFFFFFFFFFFFFFFF8uLL);
      *((_QWORD *)P + 5) = v38;
      v39 = NtQueryInformationToken(TokenHandle, TokenPrivileges, v38, v61, &v61);
      if ( v39 >= 0 )
      {
        v40 = (void *)(((unsigned __int64)v38 + v61 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
        v41 = RtlLengthSid(v29);
        RtlCopySid(v41, v40, v29);
        v42 = P;
        v43 = (_QWORD *)(((unsigned __int64)v40 + v41 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
        *((_QWORD *)P + 1) = v40;
        v42[4] = 0;
        v39 = NtQueryInformationToken(TokenHandle, TokenPrimaryGroup, v43, v60, &v60);
        if ( v39 >= 0 )
        {
          *((_QWORD *)v42 + 4) = *v43;
          v44 = (_QWORD *)(((unsigned __int64)v43 + v60 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
          v39 = NtQueryInformationToken(TokenHandle, TokenOwner, v44, v59, &v59);
          if ( v39 >= 0 )
          {
            *((_QWORD *)v42 + 6) = *v44;
            v45 = (_QWORD *)(((unsigned __int64)v44 + v59 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
            *((_QWORD *)v42 + 7) = v45;
            v39 = NtQueryInformationToken(TokenHandle, TokenDefaultDacl, v45, ReturnLength, &ReturnLength);
            if ( v39 >= 0 )
            {
              *((_QWORD *)v42 + 7) = *v45;
              if ( ReturnLength && v59 && v60 && v61 && TokenInformationLength )
              {
                v46 = v69;
                *a2 = 0;
                *v46 = 0;
                *v70 = LsaTokenInformationV2;
                *v71 = v42;
                v71 = (void **)*(int *)(v58 + 116);
                v72 = *(unsigned int *)(v58 + 112);
                (*((void (__fastcall **)(void *, void ***))LogonSessionPackage + 10))(LogonSessionTable, &v71);
                if ( TokenHandle )
                  NtClose(TokenHandle);
                *v68 = 0;
                return 0;
              }
              v26 = -1073741811;
              goto LABEL_40;
            }
          }
        }
        v27 = v65;
      }
      v26 = v39;
    }
  }
LABEL_41:
  v13 = v58;
LABEL_42:
  if ( *a8 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (*a8)->Buffer);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a8);
    *a8 = 0;
  }
  if ( *a7 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (*a7)->Buffer);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a7);
    *a7 = 0;
  }
  if ( *a9 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (*a9)->Buffer);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a9);
    *a9 = 0;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v27->UserSid);
  v27->UserSid = 0;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v27->DomainName.Buffer);
  v27->DomainName = 0;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v27->DownlevelName.Buffer);
  v27->DownlevelName = 0;
  Buffer = v27->Password.Buffer;
  if ( Buffer )
  {
    MaximumLength = v27->Password.MaximumLength;
    if ( v27->Password.MaximumLength )
    {
      do
      {
        *Buffer++ = 0;
        --MaximumLength;
      }
      while ( MaximumLength );
    }
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v27->Password.Buffer);
  v27->Password = 0;
  if ( v13 )
  {
    v71 = (void **)*(int *)(v13 + 116);
    v72 = *(unsigned int *)(v13 + 112);
    (*((void (__fastcall **)(void *, void ***))LogonSessionPackage + 10))(LogonSessionTable, &v71);
  }
  v50 = v67;
  v51 = (struct _RTL_BALANCED_NODE *)*v67;
  if ( *v67 )
  {
    if ( v51 != (struct _RTL_BALANCED_NODE *)-8LL && LODWORD(v51->Children[0]) )
    {
      v52 = 0;
      do
      {
        v53 = 4LL * v52;
        v54 = LODWORD(v51[1].Children[v53]);
        for ( i = v51[1].Children[v53 + 1]; v54; --v54 )
        {
          LOBYTE(i->Children[0]) = 0;
          i = (struct _RTL_BALANCED_NODE *)((char *)i + 1);
        }
        v51 = (struct _RTL_BALANCED_NODE *)*v50;
        ++v52;
      }
      while ( v52 < (*v50)->CredentialCount );
    }
    LsapSubProv_FreeRoutine(v51, v51);
    *v50 = 0;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( TokenHandle )
    NtClose(TokenHandle);
  *v68 = v26;
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x18000acb0  push    rbp
0x18000acb2  push    rbx
0x18000acb3  push    rsi
0x18000acb4  push    rdi
0x18000acb5  push    r12
0x18000acb7  push    r13
0x18000acb9  push    r14
0x18000acbb  push    r15
0x18000acbd  lea     rbp, [rsp-7]
0x18000acc2  sub     rsp, 0E8h
0x18000acc9  mov     rax, cs:__security_cookie
0x18000acd0  xor     rax, rsp
0x18000acd3  mov     [rbp+3Fh+var_50], rax
0x18000acd7  mov     rax, [rbp+3Fh+arg_20]
0x18000acdb  xorps   xmm1, xmm1
0x18000acde  mov     rdi, [rbp+3Fh+arg_50]
0x18000ace5  mov     rbx, rcx
0x18000ace8  mov     rcx, [rbp+3Fh+arg_48]; void *
0x18000acef  mov     r13, rdx
0x18000acf2  mov     r15, [rbp+3Fh+arg_30]
0x18000acf6  xorps   xmm0, xmm0
0x18000acf9  mov     r14, [rbp+3Fh+arg_38]
0x18000ad00  xor     edx, edx; Val
0x18000ad02  mov     r12, [rbp+3Fh+arg_40]
0x18000ad09  mov     [rbp+3Fh+var_98], rax
0x18000ad0d  mov     rax, [rbp+3Fh+arg_28]
0x18000ad11  mov     [rbp+3Fh+var_90], rax
0x18000ad15  xor     eax, eax
0x18000ad17  mov     [rbp+3Fh+var_A0], r8
0x18000ad1b  mov     esi, eax
0x18000ad1d  mov     r8d, 0C8h; Size
0x18000ad23  mov     [rsp+120h+TokenHandle], rax
0x18000ad28  mov     [rsp+120h+var_D8], eax
0x18000ad2c  mov     [rsp+120h+TokenInformationLength], eax
0x18000ad30  mov     [rsp+120h+var_DC], eax
0x18000ad34  mov     [rsp+120h+var_E0], eax
0x18000ad38  mov     [rsp+120h+var_C8], eax
0x18000ad3c  mov     [rbp+3Fh+P], rax
0x18000ad40  mov     [rbp+3Fh+var_A8], r9
0x18000ad44  mov     [rsp+120h+var_C0], rcx
0x18000ad49  mov     [rbp+3Fh+var_B0], rdi
0x18000ad4d  movups  xmmword ptr [rbp+3Fh+TimeFields.Year], xmm0
0x18000ad51  movups  xmmword ptr [rbp+3Fh+var_80.Year], xmm1
0x18000ad55  movups  [rbp+3Fh+var_70], xmm1
0x18000ad59  call    memset_0
0x18000ad5e  mov     edx, 20h ; ' '; Size
0x18000ad63  mov     [rdi], rsi
0x18000ad66  lea     rcx, [rbp+3Fh+var_80]; struct _SECPKG_CLIENT_INFO_EX *
0x18000ad6a  call    ?LsapGetClientInfoEx@@YAJPEAU_SECPKG_CLIENT_INFO_EX@@K@Z; LsapGetClientInfoEx(_SECPKG_CLIENT_INFO_EX *,ulong)
0x18000ad6f  test    eax, eax
0x18000ad71  js      loc_18000B7B5
0x18000ad77  cmp     dword ptr [rbp+3Fh+var_80.Year], 3E7h
0x18000ad7e  jnz     loc_18000B5D0
0x18000ad84  cmp     dword ptr [rbp+3Fh+var_80.Day], esi
0x18000ad87  jnz     loc_18000B5D0
0x18000ad8d  mov     rax, cs:?LogonSessionPackage@@3PEAU_HANDLE_PACKAGE@@EA; _HANDLE_PACKAGE * LogonSessionPackage
0x18000ad94  lea     rdx, [rbp+3Fh+var_80]
0x18000ad98  mov     rcx, cs:?LogonSessionTable@@3PEAXEA; void * LogonSessionTable
0x18000ad9f  mov     qword ptr [rbx], 3E7h
0x18000ada6  mov     qword ptr [rbp+3Fh+var_80.Year], rsi
0x18000adaa  mov     rax, [rax+48h]
0x18000adae  mov     qword ptr [rbp+3Fh+var_80.Minute], 3E7h
0x18000adb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adbb  mov     [rsp+120h+var_E8], rax
0x18000adc0  mov     rsi, rax
0x18000adc3  test    rax, rax
0x18000adc6  jz      loc_18000B5DF
0x18000adcc  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x18000add2  call    cs:__imp_TlsGetValue
0x18000add9  nop     dword ptr [rax+rax+00h]
0x18000adde  test    rax, rax
0x18000ade1  jz      loc_18000B764
0x18000ade7  xor     edi, edi
0x18000ade9  lea     rbx, [rax+110h]
0x18000adf0  xor     esi, esi
0x18000adf2  cmp     [rbx], rsi
0x18000adf5  jnz     loc_18000B6E1
0x18000adfb  cmp     [rax+40h], esi
0x18000adfe  jnz     loc_18000B647
0x18000ae04  test    byte ptr [rax+20h], 20h
0x18000ae08  jnz     loc_18000B772
0x18000ae0e  mov     ecx, cs:?dwSession@@3KA; dwTlsIndex
0x18000ae14  call    cs:__imp_TlsGetValue
0x18000ae1b  nop     dword ptr [rax+rax+00h]
0x18000ae20  test    rax, rax
0x18000ae23  jz      loc_18000B657
0x18000ae29  test    dword ptr [rax+20h], 1000h
0x18000ae30  jnz     loc_18000B6C5
0x18000ae36  xor     ecx, ecx; BindingHandle
0x18000ae38  call    cs:__imp_RpcImpersonateClient
0x18000ae3f  nop     dword ptr [rax+rax+00h]
0x18000ae44  cmp     eax, 5
0x18000ae47  jz      loc_18000B779
0x18000ae4d  cmp     eax, 6E5h
0x18000ae52  jz      loc_18000B780
0x18000ae58  mov     ecx, eax; Status
0x18000ae5a  call    cs:__imp_I_RpcMapWin32Status
0x18000ae61  nop     dword ptr [rax+rax+00h]
0x18000ae66  test    eax, eax
0x18000ae68  js      loc_18000B74B
0x18000ae6e  mov     edi, 1
0x18000ae73  mov     esi, edi
0x18000ae75  mov     r9, rbx; TokenHandle
0x18000ae78  movzx   r8d, dil; OpenAsSelf
0x18000ae7c  mov     edx, 2000000h; DesiredAccess
0x18000ae81  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000ae88  call    cs:__imp_NtOpenThreadToken
0x18000ae8f  nop     dword ptr [rax+rax+00h]
0x18000ae94  mov     ebx, eax
0x18000ae96  test    eax, eax
0x18000ae98  js      loc_18000B787
0x18000ae9e  lea     r9, [rsp+120h+TokenHandle]; TokenHandle
0x18000aea3  mov     r8b, 1; OpenAsSelf
0x18000aea6  mov     edx, 8; DesiredAccess
0x18000aeab  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000aeb2  call    cs:__imp_NtOpenThreadToken
0x18000aeb9  nop     dword ptr [rax+rax+00h]
0x18000aebe  mov     ebx, eax
0x18000aec0  call    cs:__imp_RevertToSelf
0x18000aec7  nop     dword ptr [rax+rax+00h]
0x18000aecc  test    ebx, ebx
0x18000aece  js      loc_18000B2FF
0x18000aed4  lea     rcx, ?NegComputerNamesLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000aedb  call    cs:__imp_RtlEnterCriticalSection
0x18000aee2  nop     dword ptr [rax+rax+00h]
0x18000aee7  mov     rdi, [rsp+120h+var_C0]
0x18000aeec  lea     rcx, ?NegPrimarySystemCredentials@@3U_SECPKG_PRIMARY_CRED@@A; struct _SECPKG_PRIMARY_CRED *
0x18000aef3  mov     r9, [rbp+3Fh+var_B0]; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x18000aef7  mov     r8, rdi; struct _SECPKG_PRIMARY_CRED *
0x18000aefa  mov     rdx, cs:?NegSupplementalSystemCredentials@@3PEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@EA; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *
0x18000af01  call    ?NegpCopyCredsToBuffer@@YAJPEAU_SECPKG_PRIMARY_CRED@@PEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@0PEAPEAU2@@Z; NegpCopyCredsToBuffer(_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY *,_SECPKG_PRIMARY_CRED *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x18000af06  lea     rcx, ?NegComputerNamesLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000af0d  mov     ebx, eax
0x18000af0f  call    cs:__imp_RtlLeaveCriticalSection
0x18000af16  nop     dword ptr [rax+rax+00h]
0x18000af1b  test    ebx, ebx
0x18000af1d  js      loc_18000B304
0x18000af23  mov     rdx, [rdi+48h]; Sid2
0x18000af27  xor     ebx, ebx
0x18000af29  mov     qword ptr [rdi], 3E7h
0x18000af30  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18000af37  mov     rsi, [rax+2D0h]
0x18000af3e  test    rdx, rdx
0x18000af41  jnz     loc_18000B591
0x18000af47  cmp     [rdi+48h], rbx
0x18000af4b  jz      loc_18000B5F8
0x18000af51  mov     rcx, [rsp+120h+TokenHandle]; TokenHandle
0x18000af56  lea     rax, [rsp+120h+var_C8]
0x18000af5b  xor     r9d, r9d; TokenInformationLength
0x18000af5e  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18000af63  xor     r8d, r8d; TokenInformation
0x18000af66  mov     edx, 6; TokenInformationClass
0x18000af6b  call    cs:__imp_NtQueryInformationToken
0x18000af72  nop     dword ptr [rax+rax+00h]
0x18000af77  mov     ebx, eax
0x18000af79  cmp     eax, 80000005h
0x18000af7e  jnz     loc_18000B6A5
0x18000af84  mov     rcx, [rsp+120h+TokenHandle]; TokenHandle
0x18000af89  lea     rax, [rsp+120h+var_D8]
0x18000af8e  xor     r9d, r9d; TokenInformationLength
0x18000af91  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18000af96  xor     r8d, r8d; TokenInformation
0x18000af99  mov     edx, 3; TokenInformationClass
0x18000af9e  call    cs:__imp_NtQueryInformationToken
0x18000afa5  nop     dword ptr [rax+rax+00h]
0x18000afaa  mov     ebx, eax
0x18000afac  cmp     eax, 80000005h
0x18000afb1  jnz     loc_18000B685
0x18000afb7  mov     rcx, [rsp+120h+TokenHandle]; TokenHandle
0x18000afbc  lea     rax, [rsp+120h+TokenInformationLength]
0x18000afc1  xor     r9d, r9d; TokenInformationLength
0x18000afc4  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18000afc9  xor     r8d, r8d; TokenInformation
0x18000afcc  mov     edx, 2; TokenInformationClass
0x18000afd1  call    cs:__imp_NtQueryInformationToken
0x18000afd8  nop     dword ptr [rax+rax+00h]
0x18000afdd  mov     ebx, eax
0x18000afdf  cmp     eax, 80000005h
0x18000afe4  jnz     loc_18000B695
0x18000afea  mov     rcx, [rsp+120h+TokenHandle]; TokenHandle
0x18000afef  lea     rax, [rsp+120h+var_DC]
0x18000aff4  xor     r9d, r9d; TokenInformationLength
0x18000aff7  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18000affc  xor     r8d, r8d; TokenInformation
0x18000afff  mov     edx, 5; TokenInformationClass
0x18000b004  call    cs:__imp_NtQueryInformationToken
0x18000b00b  nop     dword ptr [rax+rax+00h]
0x18000b010  mov     ebx, eax
0x18000b012  cmp     eax, 80000005h
0x18000b017  jnz     loc_18000B6B5
0x18000b01d  mov     rcx, [rsp+120h+TokenHandle]; TokenHandle
0x18000b022  lea     rax, [rsp+120h+var_E0]
0x18000b027  xor     r9d, r9d; TokenInformationLength
0x18000b02a  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18000b02f  xor     r8d, r8d; TokenInformation
0x18000b032  mov     edx, 4; TokenInformationClass
0x18000b037  call    cs:__imp_NtQueryInformationToken
0x18000b03e  nop     dword ptr [rax+rax+00h]
0x18000b043  mov     ebx, eax
0x18000b045  cmp     eax, 80000005h
0x18000b04a  jnz     loc_18000B675
0x18000b050  mov     rcx, rsi; Sid
0x18000b053  call    cs:__imp_RtlLengthSid
0x18000b05a  nop     dword ptr [rax+rax+00h]
0x18000b05f  mov     r8d, [rsp+120h+var_D8]
0x18000b064  mov     edx, 8; Flags
0x18000b069  mov     ecx, eax
0x18000b06b  add     r8d, 70h ; 'p'
0x18000b06f  add     ecx, [rsp+120h+var_C8]
0x18000b073  add     ecx, [rsp+120h+var_E0]
0x18000b077  add     ecx, [rsp+120h+var_DC]
0x18000b07b  add     ecx, [rsp+120h+TokenInformationLength]
0x18000b07f  add     r8d, ecx; Size
0x18000b082  mov     rcx, gs:60h
0x18000b08b  mov     rcx, [rcx+30h]; HeapHandle
0x18000b08f  call    cs:__imp_RtlAllocateHeap
0x18000b096  nop     dword ptr [rax+rax+00h]
0x18000b09b  mov     [rbp+3Fh+P], rax
0x18000b09f  mov     rbx, rax
0x18000b0a2  test    rax, rax
0x18000b0a5  jz      loc_18000B5EE
0x18000b0ab  movdqa  xmm0, cs:__xmm@00010001000100010001000100010bb8
0x18000b0b3  lea     rcx, [rbp+3Fh+TimeFields]; TimeFields
0x18000b0b7  mov     rdx, rax; Time
0x18000b0ba  movdqu  xmmword ptr [rbp+3Fh+TimeFields.Year], xmm0
0x18000b0bf  call    cs:__imp_RtlTimeFieldsToTime
0x18000b0c6  nop     dword ptr [rax+rax+00h]
0x18000b0cb  lea     r8, [rbx+40h]; TokenInformation
0x18000b0cf  mov     edx, 2; TokenInformationClass
0x18000b0d4  mov     [rbx+18h], r8
0x18000b0d8  lea     rax, [rsp+120h+TokenInformationLength]
0x18000b0dd  mov     r9d, [rsp+120h+TokenInformationLength]; TokenInformationLength
0x18000b0e2  mov     rcx, [rsp+120h+TokenHandle]; TokenHandle
0x18000b0e7  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18000b0ec  call    cs:__imp_NtQueryInformationToken
0x18000b0f3  nop     dword ptr [rax+rax+00h]
0x18000b0f8  mov     ebx, eax
0x18000b0fa  test    eax, eax
0x18000b0fc  js      loc_18000B304
0x18000b102  mov     ebx, [rsp+120h+TokenInformationLength]
0x18000b106  lea     rax, [rsp+120h+var_D8]
0x18000b10b  mov     rcx, [rbp+3Fh+P]
0x18000b10f  add     rbx, 47h ; 'G'
0x18000b113  add     rbx, rcx
0x18000b116  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18000b11b  and     rbx, 0FFFFFFFFFFFFFFF8h
0x18000b11f  mov     edx, 3; TokenInformationClass
0x18000b124  mov     r8, rbx; TokenInformation
0x18000b127  mov     [rcx+28h], rbx
0x18000b12b  mov     r9d, [rsp+120h+var_D8]; TokenInformationLength
0x18000b130  mov     rcx, [rsp+120h+TokenHandle]; TokenHandle
0x18000b135  call    cs:__imp_NtQueryInformationToken
0x18000b13c  nop     dword ptr [rax+rax+00h]
0x18000b141  test    eax, eax
0x18000b143  js      loc_18000B718
0x18000b149  mov     edi, [rsp+120h+var_D8]
0x18000b14d  mov     rcx, rsi; Sid
0x18000b150  add     rdi, 7
0x18000b154  add     rdi, rbx
0x18000b157  and     rdi, 0FFFFFFFFFFFFFFF8h
0x18000b15b  call    cs:__imp_RtlLengthSid
0x18000b162  nop     dword ptr [rax+rax+00h]
0x18000b167  mov     r8, rsi; SourceSid
0x18000b16a  mov     rdx, rdi; DestinationSid
0x18000b16d  mov     ecx, eax; DestinationSidLength
0x18000b16f  mov     ebx, eax
0x18000b171  call    cs:__imp_RtlCopySid
0x18000b178  nop     dword ptr [rax+rax+00h]
0x18000b17d  mov     rsi, [rbp+3Fh+P]
0x18000b181  mov     eax, ebx
0x18000b183  lea     rbx, [rdi+7]
0x18000b187  mov     edx, 5; TokenInformationClass
0x18000b18c  add     rbx, rax
0x18000b18f  lea     rax, [rsp+120h+var_DC]
0x18000b194  and     rbx, 0FFFFFFFFFFFFFFF8h
0x18000b198  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18000b19d  mov     [rsi+8], rdi
0x18000b1a1  mov     r8, rbx; TokenInformation
0x18000b1a4  mov     dword ptr [rsi+10h], 0
0x18000b1ab  mov     r9d, [rsp+120h+var_DC]; TokenInformationLength
0x18000b1b0  mov     rcx, [rsp+120h+TokenHandle]; TokenHandle
0x18000b1b5  call    cs:__imp_NtQueryInformationToken
0x18000b1bc  nop     dword ptr [rax+rax+00h]
0x18000b1c1  test    eax, eax
0x18000b1c3  js      loc_18000B713
0x18000b1c9  mov     rax, [rbx]
0x18000b1cc  mov     edx, 4; TokenInformationClass
0x18000b1d1  mov     [rsi+20h], rax
0x18000b1d5  mov     eax, [rsp+120h+var_DC]
0x18000b1d9  mov     r9d, [rsp+120h+var_E0]; TokenInformationLength
0x18000b1de  add     rax, 7
0x18000b1e2  mov     rcx, [rsp+120h+TokenHandle]; TokenHandle
0x18000b1e7  add     rbx, rax
0x18000b1ea  lea     rax, [rsp+120h+var_E0]
0x18000b1ef  and     rbx, 0FFFFFFFFFFFFFFF8h
0x18000b1f3  mov     r8, rbx; TokenInformation
0x18000b1f6  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18000b1fb  call    cs:__imp_NtQueryInformationToken
0x18000b202  nop     dword ptr [rax+rax+00h]
0x18000b207  test    eax, eax
  ... truncated ...
```
