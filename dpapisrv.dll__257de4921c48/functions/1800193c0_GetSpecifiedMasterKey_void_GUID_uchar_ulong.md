# GetSpecifiedMasterKey(void *,_GUID *,uchar * *,ulong *)

- ea: `0x1800193c0`
- end: `0x180019cf8`
- name: `?GetSpecifiedMasterKey@@YAKPEAXPEAU_GUID@@PEAPEAEPEAK@Z`
- size: `2360`
- prototype: `__int64 __fastcall(HANDLE *, struct _GUID *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016370`
- `0x180039be0`

## callees

- `0x180004d80`
- `0x1800063c0`
- `0x180006510`
- `0x180006c60`
- `0x180008300`
- `0x1800090e8`
- `0x18000bc70`
- `0x18000e87c`
- `0x18000f910`
- `0x180013838`
- `0x180013b64`
- `0x180013f2c`
- `0x18001444c`
- `0x1800193c0`
- `0x18001af90`
- `0x18001c340`
- `0x18001c3a8`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001eb8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800194b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800194b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019733`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019c6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019c82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019733`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019c6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019c82`
- `LSASRV!LsaILookupUserAccountType` at `0x1800198c9`
- `LSASRV!LsaILookupUserAccountType` at `0x1800198c9`
- `ntdll!RtlNtStatusToDosError` at `0x180019912`
- `ntdll!RtlNtStatusToDosError` at `0x180019912`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019b9b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019b9b`

## string_xrefs

- `0x180019480`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x1800194fb`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x1800195ed`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x1800196d9`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall GetSpecifiedMasterKey(HANDLE *a1, struct _GUID *a2, unsigned __int8 **a3, unsigned int *a4)
{
  int ThreadAuthenticationId; // r15d
  HLOCAL v5; // rdi
  void **v6; // r12
  struct _GUID *v7; // r14
  int v9; // edx
  unsigned int LastError; // esi
  HANDLE CurrentThread; // rax
  int v12; // edx
  int v13; // ebx
  int v14; // r9d
  int v15; // edx
  int v16; // edx
  unsigned int v17; // r14d
  __int64 v18; // rbx
  void *v19; // r8
  BOOL v20; // ecx
  const char *v21; // r9
  HANDLE v22; // rcx
  const struct _TraceLoggingMetadata_t *v23; // rcx
  NTSTATUS v24; // ebx
  int v25; // r8d
  const wchar_t *v26; // rcx
  __int64 v27; // rax
  char *v29; // r9
  char *v30; // rax
  char v31; // cl
  char v34; // cl
  char v35; // dl
  __int64 v36; // rcx
  char UserDataCount; // [rsp+20h] [rbp-E0h]
  unsigned int v39; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v41; // [rsp+60h] [rbp-A0h] BYREF
  UUID *Uuid; // [rsp+68h] [rbp-98h] BYREF
  void **v43; // [rsp+70h] [rbp-90h] BYREF
  struct _LUID v44; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 **v45; // [rsp+80h] [rbp-80h]
  unsigned int v46; // [rsp+88h] [rbp-78h] BYREF
  unsigned int *v47; // [rsp+90h] [rbp-70h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C0h] [rbp-40h] BYREF
  char *v51; // [rsp+D0h] [rbp-30h]
  __int64 v52; // [rsp+D8h] [rbp-28h]
  HLOCAL *p_hMem; // [rsp+E0h] [rbp-20h]
  __int64 v54; // [rsp+E8h] [rbp-18h]
  void ***v55; // [rsp+F0h] [rbp-10h]
  __int64 v56; // [rsp+F8h] [rbp-8h]
  void *v57; // [rsp+100h] [rbp+0h]
  __int64 v58; // [rsp+108h] [rbp+8h]
  UUID **p_Uuid; // [rsp+110h] [rbp+10h]
  __int64 v60; // [rsp+118h] [rbp+18h]
  unsigned int *v61; // [rsp+120h] [rbp+20h]
  __int64 v62; // [rsp+128h] [rbp+28h]
  const wchar_t *v63; // [rsp+130h] [rbp+30h]
  int v64; // [rsp+138h] [rbp+38h]
  int v65; // [rsp+13Ch] [rbp+3Ch]

  ThreadAuthenticationId = 0;
  v47 = a4;
  v44 = 0;
  v45 = a3;
  v5 = 0;
  hMem = 0;
  v6 = 0;
  v39 = 0;
  v7 = a2;
  v43 = 0;
  v41 = 0;
  Uuid = a2;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF__guid_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), (_DWORD)a2, (_DWORD)a3, (_DWORD)a2, (__int64)(a1 + 10));
  LastError = CPSImpersonateClient(a1);
  if ( LastError )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v9,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwLastError",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
        222);
    goto LABEL_72;
  }
  CurrentThread = GetCurrentThread();
  ThreadAuthenticationId = GetThreadAuthenticationId(CurrentThread, &v44);
  if ( !ThreadAuthenticationId )
  {
    LastError = GetLastError();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v12,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwLastError",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
        230);
      CPSRevertToSelf(a1);
      goto LABEL_72;
    }
  }
  CPSRevertToSelf(a1);
  if ( !ThreadAuthenticationId )
    goto LABEL_72;
  v13 = 0;
  ThreadAuthenticationId = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_dd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      40,
      WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
      v44.LowPart,
      v44.HighPart);
  if ( a1 && *(_DWORD *)a1 == 624 && (v13 = *((_DWORD *)a1 + 12), v13 == 19) || (v14 = 1, v13 == 20) )
    v14 = 0;
  LastError = CPSGetUserStorageArea(a1, 0, 1u, v14, (unsigned __int16 **)&hMem);
  if ( LastError )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v15,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwLastError",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
        10);
    v5 = hMem;
    goto LABEL_72;
  }
  v5 = hMem;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 41, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, hMem);
  if ( (unsigned int)SearchMasterKeyCache(&v44, (const unsigned __int16 *)v5, v7, v45, v47) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 42, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    ThreadAuthenticationId = 1;
LABEL_114:
    if ( v5 )
      LocalFree(v5);
    goto LABEL_116;
  }
  LastError = CPSGetSidHistory(a1, &v43, &v41);
  if ( LastError )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v16,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwLastError",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
        41);
    v6 = v43;
    goto LABEL_72;
  }
  v17 = v41;
  v18 = 0;
  v6 = v43;
  if ( !v41 )
  {
LABEL_71:
    v7 = Uuid;
LABEL_72:
    v22 = a1[9];
    v41 = 0;
    v24 = LsaILookupUserAccountType(v22, &v41);
    if ( v24 < 0 )
    {
      LODWORD(v23) = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          47,
          WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
          (unsigned int)v24);
      if ( !LastError )
        LastError = RtlNtStatusToDosError(v24);
    }
    if ( (unsigned int)dword_18004C260 > 5 )
    {
      LODWORD(v23) = qword_18004C278;
      v25 = 0;
      if ( (qword_18004C270 & 0x400000000000LL) != 0 && (qword_18004C278 & 0x400000000000LL) == qword_18004C278 )
      {
        switch ( v41 )
        {
          case 0u:
            v26 = L"UnknownUserAccountType";
            break;
          case 1u:
            v26 = L"LocalUserAccountType";
            break;
          case 2u:
            v26 = L"PrimaryDomainUserAccountType";
            break;
          case 3u:
            v26 = L"ExternalDomainUserAccountType";
            break;
          case 4u:
            v26 = L"LocalConnectedUserAccountType";
            break;
          case 5u:
            v26 = L"AADUserAccountType";
            break;
          case 6u:
            v26 = L"InternetUserAccountType";
            break;
          default:
            v26 = &Class;
            break;
        }
        v46 = v39;
        v27 = -1;
        LODWORD(Uuid) = LastError;
        LODWORD(v43) = ThreadAuthenticationId;
        v49 = 1;
        while ( v26[++v27] != 0 )
          ;
        v63 = v26;
        v64 = 2 * v27 + 2;
        v23 = &TraceLoggingMetadata;
        v62 = 4;
        v61 = &v46;
        v65 = 0;
        p_Uuid = &Uuid;
        v57 = &v43;
        p_hMem = (HLOCAL *)&v49;
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = (ULONGLONG)off_18004C268;
        v60 = 4;
        v58 = 4;
        v55 = (void ***)v7;
        v56 = 16;
        v54 = 8;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0x400000000000LL;
        UserData.Size = *(unsigned __int16 *)off_18004C268;
        v51 = byte_180044D03;
        UserData.Reserved = 2;
        v52 = 0x100000078LL;
        LODWORD(hMem) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_18004C288 == TlgAggregateInternalRegisteredProviderEtwCallback )
        {
          LOBYTE(v25) = 0;
          v29 = &v51[(unsigned int)v52];
          v30 = v51 + 2;
          do
            v31 = *v30++;
          while ( v31 < 0 );
          while ( *v30++ )
            ;
          if ( v30 >= v29 )
            goto LABEL_108;
          while ( 1 )
          {
            while ( *v30++ )
              ;
            if ( *v30 >= 0 )
              break;
            v34 = *v30 & 0x7F;
            if ( v30[1] >= 0 )
              break;
            v35 = v30[2];
            v30 += 2;
            if ( v35 < 0 )
            {
              while ( v35 == (char)0x80 )
              {
                v35 = *++v30;
                if ( v35 >= 0 )
                  goto LABEL_103;
              }
              break;
            }
LABEL_103:
            if ( v34 == 9 && (unsigned __int8)(v35 - 113) <= 2u )
            {
              v36 = (unsigned __int8)v25;
              LOBYTE(v25) = v25 + 1;
              *((_BYTE *)&v54 + 16 * v36 + 5) = v35;
              if ( v30 < v29 )
                continue;
            }
            break;
          }
          if ( (_BYTE)v25 )
          {
            UserDataCount = v25;
            LOBYTE(v25) = 8;
            InsertEventEntryInLookUpTable(
              (unsigned int)&dword_18004C260,
              (unsigned int)&EventDescriptor,
              v25,
              (unsigned int)&UserData,
              UserDataCount);
          }
          else
          {
LABEL_108:
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &UserData);
          }
        }
      }
    }
    if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 4) != 0 )
    {
      LODWORD(Uuid) = v39;
      LODWORD(v43) = LastError;
      p_hMem = &hMem;
      v55 = &v43;
      v57 = &Uuid;
      LODWORD(hMem) = ThreadAuthenticationId;
      v51 = (char *)v7;
      v52 = 16;
      v54 = 4;
      v56 = 4;
      v58 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (_DWORD)v23,
        (unsigned int)ETW_LOG_DPAPI_MASTER_KEY_INACCESIBLE,
        v25,
        5,
        (__int64)&UserData);
    }
    EventDescriptor = (EVENT_DESCRIPTOR)*v7;
    CheckMissingMasterKeyDecryption((struct _GUID *)&EventDescriptor);
    goto LABEL_114;
  }
  while ( (_DWORD)v18 )
  {
    if ( v5 )
    {
      LocalFree(v5);
      hMem = 0;
    }
    if ( !(unsigned int)CPSGetUserStorageArea(a1, v6[v18], 1u, 0, (unsigned __int16 **)&hMem) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      {
        v5 = hMem;
        WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 44, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, hMem);
        v19 = v6[v18];
        v20 = 1;
        goto LABEL_53;
      }
      v5 = hMem;
      break;
    }
    v5 = hMem;
LABEL_70:
    v18 = (unsigned int)(v18 + 1);
    if ( (unsigned int)v18 >= v17 )
      goto LABEL_71;
  }
  v20 = v18 != 0;
  if ( (_DWORD)v18 )
    v19 = v6[v18];
  else
    v19 = 0;
LABEL_53:
  ThreadAuthenticationId = GetMasterKeyByGuid(a1, (const unsigned __int16 *)v5, v19, &v44, v20, Uuid, v45, v47, &v39);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    if ( v39 )
    {
      switch ( v39 )
      {
        case 1u:
          v21 = "Local backup";
          break;
        case 2u:
          v21 = "DC backup";
          break;
        case 3u:
          v21 = "Storage error";
          break;
        case 4u:
          v21 = "Delegation error";
          break;
        default:
          v21 = "Deadlock error";
          if ( v39 != 5 )
            v21 = "Unknown error";
          break;
      }
    }
    else
    {
      v21 = "Normal";
    }
    WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 45, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, v21);
  }
  if ( !ThreadAuthenticationId )
  {
    if ( v39 != 3 )
      goto LABEL_71;
    goto LABEL_70;
  }
  if ( v5 )
  {
    InsertMasterKeyCache(a1, &v44, (const unsigned __int16 *)v5, Uuid, *v45, *v47);
    goto LABEL_114;
  }
LABEL_116:
  if ( v6 )
    LocalFree(v6);
  if ( !LastError && !ThreadAuthenticationId )
    LastError = -2146893813;
  if ( v39 == 4 )
    return 2148074309LL;
  if ( v39 == 5 )
    return 1131;
  return LastError;
}

```

## disassembly

```asm
0x1800193c0  push    rbp
0x1800193c2  push    rbx
0x1800193c3  push    rsi
0x1800193c4  push    rdi
0x1800193c5  push    r12
0x1800193c7  push    r13
0x1800193c9  push    r14
0x1800193cb  push    r15
0x1800193cd  lea     rbp, [rsp-58h]
0x1800193d2  sub     rsp, 158h
0x1800193d9  mov     rax, cs:__security_cookie
0x1800193e0  xor     rax, rsp
0x1800193e3  mov     [rbp+90h+var_50], rax
0x1800193e7  xor     r15d, r15d
0x1800193ea  mov     [rbp+90h+var_100], r9
0x1800193ee  mov     rbx, r8
0x1800193f1  mov     qword ptr [rsp+190h+var_118.LowPart], r15
0x1800193f6  mov     [rbp+90h+var_110], rbx
0x1800193fa  mov     edi, r15d
0x1800193fd  mov     [rsp+190h+hMem], r15
0x180019402  mov     r12d, r15d
0x180019405  mov     [rsp+190h+var_140], r15d
0x18001940a  mov     r14, rdx
0x18001940d  mov     [rsp+190h+var_120], r15
0x180019412  mov     r13, rcx
0x180019415  mov     [rsp+190h+var_130], r15d
0x18001941a  mov     [rsp+190h+Uuid], rdx
0x18001941f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019426  lea     rax, WPP_GLOBAL_Control
0x18001942d  cmp     rcx, rax
0x180019430  jz      short loc_18001944D
0x180019432  test    byte ptr [rcx+1Ch], 4
0x180019436  jz      short loc_18001944D
0x180019438  mov     rcx, [rcx+10h]
0x18001943c  lea     rax, [r13+50h]
0x180019440  mov     r9, rdx
0x180019443  mov     qword ptr [rsp+190h+UserDataCount], rax
0x180019448  call    WPP_SF__guid_S
0x18001944d  mov     rcx, r13; void *
0x180019450  call    ?CPSImpersonateClient@@YAKPEAX@Z; CPSImpersonateClient(void *)
0x180019455  mov     esi, eax
0x180019457  test    eax, eax
0x180019459  jz      short loc_1800194B0
0x18001945b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019462  lea     rax, WPP_GLOBAL_Control
0x180019469  cmp     rcx, rax
0x18001946c  jz      loc_1800198B8
0x180019472  test    byte ptr [rcx+1Ch], 1
0x180019476  jz      loc_1800198B8
0x18001947c  mov     rcx, [rcx+10h]
0x180019480  lea     rax, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180019487  mov     dword ptr [rsp+190h+var_160], 7DEh
0x18001948f  lea     r9, aDwlasterror; "dwLastError"
0x180019496  mov     [rsp+190h+UserData], rax
0x18001949b  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x1800194a2  mov     [rsp+190h+UserDataCount], esi
0x1800194a6  call    WPP_SF_sDsd
0x1800194ab  jmp     loc_1800198B8
0x1800194b0  call    cs:__imp_GetCurrentThread
0x1800194b7  nop     dword ptr [rax+rax+00h]
0x1800194bc  mov     rcx, rax
0x1800194bf  lea     rdx, [rsp+190h+var_118]
0x1800194c4  call    GetThreadAuthenticationId
0x1800194c9  mov     r15d, eax
0x1800194cc  test    eax, eax
0x1800194ce  jnz     short loc_180019544
0x1800194d0  call    cs:__imp_GetLastError
0x1800194d7  nop     dword ptr [rax+rax+00h]
0x1800194dc  mov     esi, eax
0x1800194de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194e5  lea     rax, WPP_GLOBAL_Control
0x1800194ec  cmp     rcx, rax
0x1800194ef  jz      short loc_180019544
0x1800194f1  test    byte ptr [rcx+1Ch], 1
0x1800194f5  jz      short loc_180019544
0x1800194f7  mov     rcx, [rcx+10h]
0x1800194fb  lea     rax, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180019502  mov     dword ptr [rsp+190h+var_160], 7E6h
0x18001950a  lea     r9, aDwlasterror; "dwLastError"
0x180019511  mov     [rsp+190h+UserData], rax
0x180019516  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18001951d  mov     [rsp+190h+UserDataCount], esi
0x180019521  call    WPP_SF_sDsd
0x180019526  mov     rcx, r13; void *
0x180019529  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x18001952e  test    esi, esi
0x180019530  jnz     loc_1800198B8
0x180019536  test    r15d, r15d
0x180019539  jnz     loc_180019C3C
0x18001953f  jmp     loc_1800198B8
0x180019544  mov     rcx, r13; void *
0x180019547  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x18001954c  test    r15d, r15d
0x18001954f  jz      short loc_18001952E
0x180019551  xor     ebx, ebx
0x180019553  xor     r15d, r15d
0x180019556  mov     rcx, cs:WPP_GLOBAL_Control
0x18001955d  lea     rdi, WPP_GLOBAL_Control
0x180019564  cmp     rcx, rdi
0x180019567  jz      short loc_180019591
0x180019569  test    byte ptr [rcx+1Ch], 8
0x18001956d  jz      short loc_180019591
0x18001956f  mov     eax, [rsp+190h+var_118.HighPart]
0x180019573  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18001957a  mov     r9d, [rsp+190h+var_118.LowPart]
0x18001957f  mov     edx, 28h ; '('
0x180019584  mov     rcx, [rcx+10h]
0x180019588  mov     [rsp+190h+UserDataCount], eax
0x18001958c  call    WPP_SF_dd
0x180019591  test    r13, r13
0x180019594  jz      short loc_1800195A9
0x180019596  cmp     dword ptr [r13+0], 270h
0x18001959e  jnz     short loc_1800195A9
0x1800195a0  mov     ebx, [r13+30h]
0x1800195a4  cmp     ebx, 13h
0x1800195a7  jz      short loc_1800195B4
0x1800195a9  mov     r9d, 1
0x1800195af  cmp     ebx, 14h
0x1800195b2  jnz     short loc_1800195B7
0x1800195b4  xor     r9d, r9d; int
0x1800195b7  lea     rax, [rsp+190h+hMem]
0x1800195bc  xor     edx, edx; void *
0x1800195be  mov     r8d, 1; int
0x1800195c4  mov     qword ptr [rsp+190h+UserDataCount], rax; unsigned __int16 **
0x1800195c9  mov     rcx, r13; void *
0x1800195cc  call    ?CPSGetUserStorageArea@@YAKPEAX0HHPEAPEAG@Z; CPSGetUserStorageArea(void *,void *,int,int,ushort * *)
0x1800195d1  mov     esi, eax
0x1800195d3  test    eax, eax
0x1800195d5  jz      short loc_180019622
0x1800195d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195de  cmp     rcx, rdi
0x1800195e1  jz      short loc_180019618
0x1800195e3  test    byte ptr [rcx+1Ch], 1
0x1800195e7  jz      short loc_180019618
0x1800195e9  mov     rcx, [rcx+10h]
0x1800195ed  lea     rax, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800195f4  mov     dword ptr [rsp+190h+var_160], 80Ah
0x1800195fc  lea     r9, aDwlasterror; "dwLastError"
0x180019603  mov     [rsp+190h+UserData], rax
0x180019608  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18001960f  mov     [rsp+190h+UserDataCount], esi
0x180019613  call    WPP_SF_sDsd
0x180019618  mov     rdi, [rsp+190h+hMem]
0x18001961d  jmp     loc_1800198B8
0x180019622  mov     rcx, cs:WPP_GLOBAL_Control
0x180019629  lea     rbx, WPP_GLOBAL_Control
0x180019630  mov     rdi, [rsp+190h+hMem]
0x180019635  cmp     rcx, rbx
0x180019638  jz      short loc_180019658
0x18001963a  test    byte ptr [rcx+1Ch], 8
0x18001963e  jz      short loc_180019658
0x180019640  mov     rcx, [rcx+10h]
0x180019644  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18001964b  mov     edx, 29h ; ')'
0x180019650  mov     r9, rdi
0x180019653  call    WPP_SF_S
0x180019658  mov     rax, [rbp+90h+var_100]
0x18001965c  lea     rcx, [rsp+190h+var_118]; struct _LUID *
0x180019661  mov     r9, [rbp+90h+var_110]; unsigned __int8 **
0x180019665  mov     r8, r14; struct _GUID *
0x180019668  mov     rdx, rdi; unsigned __int16 *
0x18001966b  mov     qword ptr [rsp+190h+UserDataCount], rax; unsigned int *
0x180019670  call    ?SearchMasterKeyCache@@YAHPEAU_LUID@@PEBGPEAU_GUID@@PEAPEAEPEAK@Z; SearchMasterKeyCache(_LUID *,ushort const *,_GUID *,uchar * *,ulong *)
0x180019675  test    eax, eax
0x180019677  jz      short loc_1800196AB
0x180019679  mov     rcx, cs:WPP_GLOBAL_Control
0x180019680  cmp     rcx, rbx
0x180019683  jz      short loc_1800196A0
0x180019685  test    byte ptr [rcx+1Ch], 8
0x180019689  jz      short loc_1800196A0
0x18001968b  mov     rcx, [rcx+10h]
0x18001968f  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180019696  mov     edx, 2Ah ; '*'
0x18001969b  call    WPP_SF_
0x1800196a0  mov     r15d, 1
0x1800196a6  jmp     loc_180019C66
0x1800196ab  lea     r8, [rsp+190h+var_130]; unsigned int *
0x1800196b0  mov     rcx, r13; void *
0x1800196b3  lea     rdx, [rsp+190h+var_120]; void ***
0x1800196b8  call    ?CPSGetSidHistory@@YAKPEAXPEAPEAPEAXPEAK@Z; CPSGetSidHistory(void *,void * * *,ulong *)
0x1800196bd  mov     esi, eax
0x1800196bf  test    eax, eax
0x1800196c1  jz      short loc_18001970E
0x1800196c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196ca  cmp     rcx, rbx
0x1800196cd  jz      short loc_180019704
0x1800196cf  test    byte ptr [rcx+1Ch], 1
0x1800196d3  jz      short loc_180019704
0x1800196d5  mov     rcx, [rcx+10h]
0x1800196d9  lea     rax, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800196e0  mov     dword ptr [rsp+190h+var_160], 829h
0x1800196e8  lea     r9, aDwlasterror; "dwLastError"
0x1800196ef  mov     [rsp+190h+UserData], rax
0x1800196f4  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x1800196fb  mov     [rsp+190h+UserDataCount], esi
0x1800196ff  call    WPP_SF_sDsd
0x180019704  mov     r12, [rsp+190h+var_120]
0x180019709  jmp     loc_1800198B8
0x18001970e  mov     r14d, [rsp+190h+var_130]
0x180019713  xor     ebx, ebx
0x180019715  mov     r12, [rsp+190h+var_120]
0x18001971a  test    r14d, r14d
0x18001971d  jz      loc_1800198B3
0x180019723  test    ebx, ebx
0x180019725  jz      loc_1800197B1
0x18001972b  test    rdi, rdi
0x18001972e  jz      short loc_180019748
0x180019730  mov     rcx, rdi; hMem
0x180019733  call    cs:__imp_LocalFree
0x18001973a  nop     dword ptr [rax+rax+00h]
0x18001973f  mov     [rsp+190h+hMem], 0
0x180019748  mov     rdx, [r12+rbx*8]; void *
0x18001974c  lea     rax, [rsp+190h+hMem]
0x180019751  xor     r9d, r9d; int
0x180019754  mov     qword ptr [rsp+190h+UserDataCount], rax; unsigned __int16 **
0x180019759  mov     r8d, 1; int
0x18001975f  mov     rcx, r13; void *
0x180019762  call    ?CPSGetUserStorageArea@@YAKPEAX0HHPEAPEAG@Z; CPSGetUserStorageArea(void *,void *,int,int,ushort * *)
0x180019767  test    eax, eax
0x180019769  jnz     short loc_1800197C2
0x18001976b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019772  lea     rax, WPP_GLOBAL_Control
0x180019779  cmp     rcx, rax
0x18001977c  jz      short loc_1800197AC
0x18001977e  test    byte ptr [rcx+1Ch], 8
0x180019782  jz      short loc_1800197AC
0x180019784  mov     rdi, [rsp+190h+hMem]
0x180019789  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180019790  mov     rcx, [rcx+10h]
0x180019794  mov     r9, rdi
0x180019797  mov     edx, 2Ch ; ','
0x18001979c  call    WPP_SF_S
0x1800197a1  mov     r8, [r12+rbx*8]
0x1800197a5  mov     ecx, 1
0x1800197aa  jmp     short loc_1800197CF
0x1800197ac  mov     rdi, [rsp+190h+hMem]
0x1800197b1  xor     ecx, ecx
0x1800197b3  test    ebx, ebx
0x1800197b5  setnz   cl
0x1800197b8  test    ebx, ebx
0x1800197ba  jz      short loc_1800197CC
0x1800197bc  mov     r8, [r12+rbx*8]
0x1800197c0  jmp     short loc_1800197CF
0x1800197c2  mov     rdi, [rsp+190h+hMem]
0x1800197c7  jmp     loc_1800198A8
0x1800197cc  xor     r8d, r8d; void *
0x1800197cf  lea     rax, [rsp+190h+var_140]
0x1800197d4  mov     rdx, rdi; unsigned __int16 *
0x1800197d7  mov     [rsp+190h+var_150], rax; unsigned int *
0x1800197dc  lea     r9, [rsp+190h+var_118]; struct _LUID *
0x1800197e1  mov     rax, [rbp+90h+var_100]
0x1800197e5  mov     [rsp+190h+var_158], rax; unsigned int *
0x1800197ea  mov     rax, [rbp+90h+var_110]
0x1800197ee  mov     [rsp+190h+var_160], rax; unsigned __int8 **
0x1800197f3  mov     rax, [rsp+190h+Uuid]
0x1800197f8  mov     [rsp+190h+UserData], rax; Uuid
0x1800197fd  mov     [rsp+190h+UserDataCount], ecx; int
0x180019801  mov     rcx, r13; void *
0x180019804  call    ?GetMasterKeyByGuid@@YAHPEAXPEBG0PEAU_LUID@@HPEAU_GUID@@PEAPEAEPEAK5@Z; GetMasterKeyByGuid(void *,ushort const *,void *,_LUID *,int,_GUID *,uchar * *,ulong *,ulong *)
0x180019809  mov     r15d, eax
0x18001980c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019813  lea     rax, WPP_GLOBAL_Control
0x18001981a  cmp     rcx, rax
0x18001981d  jz      short loc_180019898
0x18001981f  test    byte ptr [rcx+1Ch], 8
0x180019823  jz      short loc_180019898
0x180019825  mov     eax, [rsp+190h+var_140]
0x180019829  test    eax, eax
0x18001982b  jnz     short loc_180019836
0x18001982d  lea     r9, aNormal; "Normal"
0x180019834  jmp     short loc_180019883
0x180019836  cmp     eax, 1
0x180019839  jnz     short loc_180019844
0x18001983b  lea     r9, aLocalBackup; "Local backup"
0x180019842  jmp     short loc_180019883
0x180019844  cmp     eax, 2
0x180019847  jnz     short loc_180019852
0x180019849  lea     r9, aDcBackup; "DC backup"
0x180019850  jmp     short loc_180019883
0x180019852  cmp     eax, 3
0x180019855  jnz     short loc_180019860
0x180019857  lea     r9, aStorageError; "Storage error"
0x18001985e  jmp     short loc_180019883
0x180019860  cmp     eax, 4
0x180019863  jnz     short loc_18001986E
0x180019865  lea     r9, aDelegationErro; "Delegation error"
0x18001986c  jmp     short loc_180019883
0x18001986e  cmp     eax, 5
0x180019871  lea     r9, aDeadlockError; "Deadlock error"
0x180019878  lea     rax, aUnknownError; "Unknown error"
0x18001987f  cmovnz  r9, rax
0x180019883  mov     rcx, [rcx+10h]
0x180019887  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18001988e  mov     edx, 2Dh ; '-'
0x180019893  call    WPP_SF_s
0x180019898  test    r15d, r15d
0x18001989b  jnz     loc_180019C33
0x1800198a1  cmp     [rsp+190h+var_140], 3
0x1800198a6  jnz     short loc_1800198B3
0x1800198a8  inc     ebx
  ... truncated ...
```
