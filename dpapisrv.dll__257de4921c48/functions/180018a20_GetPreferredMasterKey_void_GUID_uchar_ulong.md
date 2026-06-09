# GetPreferredMasterKey(void *,_GUID *,uchar * *,ulong *)

- ea: `0x180018a20`
- end: `0x1800193ae`
- name: `?GetPreferredMasterKey@@YAKPEAXPEAU_GUID@@PEAPEAEPEAK@Z`
- size: `2446`
- prototype: `__int64 __fastcall(_DWORD *, struct _GUID *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014c80`

## callees

- `0x180004920`
- `0x180004d80`
- `0x1800063c0`
- `0x180006510`
- `0x180006c60`
- `0x18000a830`
- `0x18000bc70`
- `0x18000e87c`
- `0x18000f910`
- `0x180013f2c`
- `0x18001444c`
- `0x1800180cc`
- `0x180018a20`
- `0x18001c340`
- `0x18001c3a8`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001eb8c`
- `0x180029ed4`
- `0x18002dd6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018b32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180018b32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019372`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019372`
- `ntdll!EtwEventWriteTransfer` at `0x180019240`
- `ntdll!EtwEventWriteTransfer` at `0x180019240`

## string_xrefs

- `0x180018ac8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x180018b4b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall GetPreferredMasterKey(_DWORD *a1, struct _GUID *a2, unsigned __int8 **a3, unsigned int *a4)
{
  unsigned int v6; // eax
  int v7; // edx
  unsigned int v8; // ebx
  __int64 v9; // rcx
  HANDLE CurrentThread; // rax
  int ThreadAuthenticationId; // esi
  DWORD LastError; // eax
  int v13; // edx
  __int64 v14; // rcx
  int v15; // ebx
  int v16; // r15d
  int v17; // r9d
  unsigned int v18; // eax
  int v19; // edx
  unsigned __int16 *v20; // rsi
  __int64 v21; // rcx
  __int64 v22; // rdx
  int v23; // r12d
  int PreferredMasterKeyGuid; // eax
  __int64 v25; // rcx
  unsigned int MasterKey; // eax
  int v27; // edx
  unsigned int MasterKeyByGuid; // eax
  const char *v29; // r9
  unsigned int v30; // eax
  int v31; // edx
  int v32; // ebx
  unsigned int v34; // [rsp+50h] [rbp-B0h] BYREF
  struct _LUID v35; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v36; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v37; // [rsp+64h] [rbp-9Ch] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  unsigned int *v39; // [rsp+70h] [rbp-90h]
  unsigned __int8 **v40; // [rsp+78h] [rbp-88h]
  int v41; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v42; // [rsp+88h] [rbp-78h] BYREF
  int *v43; // [rsp+A0h] [rbp-60h] BYREF
  int v44; // [rsp+A8h] [rbp-58h]
  int v45; // [rsp+ACh] [rbp-54h]
  __int16 *v46; // [rsp+B0h] [rbp-50h]
  int v47; // [rsp+B8h] [rbp-48h]
  int v48; // [rsp+BCh] [rbp-44h]
  int *v49; // [rsp+C0h] [rbp-40h]
  __int64 v50; // [rsp+C8h] [rbp-38h]
  unsigned int *v51; // [rsp+D0h] [rbp-30h]
  __int64 v52; // [rsp+D8h] [rbp-28h]
  unsigned int *v53; // [rsp+E0h] [rbp-20h]
  __int64 v54; // [rsp+E8h] [rbp-18h]

  v39 = a4;
  v35 = 0;
  hMem = 0;
  v34 = 0;
  v40 = a3;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 48, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, a1 + 20);
  v6 = CPSImpersonateClient(a1);
  v8 = v6;
  if ( v6 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v7,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwLastError",
          v6,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
          238);
        v9 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(v9 + 16), 49, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, v8);
    }
    return v8;
  }
  CurrentThread = GetCurrentThread();
  ThreadAuthenticationId = GetThreadAuthenticationId(CurrentThread, &v35);
  if ( !ThreadAuthenticationId )
  {
    LastError = GetLastError();
    v8 = LastError;
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v13,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwLastError",
          LastError,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
          247);
        v14 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 1) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(v14 + 16), 50, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, v8);
        CPSRevertToSelf(a1);
        return v8;
      }
    }
  }
  CPSRevertToSelf(a1);
  if ( !ThreadAuthenticationId )
    return v8;
  v15 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_dd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      52,
      WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
      v35.LowPart,
      v35.HighPart);
  v16 = 1;
  if ( a1 && *a1 == 624 && (v15 = a1[12], v15 == 19) || (v17 = 1, v15 == 20) )
    v17 = 0;
  v18 = CPSGetUserStorageArea(a1, 0, 1u, v17, (unsigned __int16 **)&hMem);
  v20 = (unsigned __int16 *)hMem;
  v8 = v18;
  if ( v18 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_109;
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v19,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwLastError",
        v18,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
        28);
      v21 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v21 == &WPP_GLOBAL_Control || (*(_BYTE *)(v21 + 28) & 1) == 0 )
      goto LABEL_109;
    v22 = 53;
    goto LABEL_34;
  }
  v23 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 54, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, hMem);
  v36 = IsDomainBackupRequired(a1) != 0;
  PreferredMasterKeyGuid = GetPreferredMasterKeyGuid(a1, v20, a2);
  if ( PreferredMasterKeyGuid >= 0 )
    goto LABEL_59;
  if ( PreferredMasterKeyGuid != -1073741711 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        57,
        WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
        (unsigned int)PreferredMasterKeyGuid);
    MasterKey = CreateMasterKey(a1, v20, a2, (__int64)&v35);
    v8 = MasterKey;
    if ( MasterKey )
    {
      v21 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_109;
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v27,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwLastError",
          MasterKey,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
          83);
        v21 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v21 == &WPP_GLOBAL_Control || (*(_BYTE *)(v21 + 28) & 1) == 0 )
        goto LABEL_109;
      v22 = 58;
LABEL_34:
      WPP_SF_d(*(_QWORD *)(v21 + 16), v22, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, v8);
LABEL_108:
      v21 = WPP_GLOBAL_Control;
      goto LABEL_109;
    }
    v23 = 1;
    goto LABEL_59;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 55, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, 3221225585LL);
  v42 = 0;
  v8 = CreateMasterKey(a1, v20, &v42, (__int64)&v35);
  if ( !v8 )
  {
    v23 = 1;
    *a2 = v42;
LABEL_59:
    v25 = WPP_GLOBAL_Control;
    goto LABEL_60;
  }
  v25 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_63;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 56, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, v8);
    goto LABEL_59;
  }
LABEL_60:
  if ( (_UNKNOWN *)v25 != &WPP_GLOBAL_Control && (*(_BYTE *)(v25 + 28) & 8) != 0 )
    WPP_SF__guid_(*(_QWORD *)(v25 + 16), 59, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, a2);
LABEL_63:
  if ( (unsigned int)SearchMasterKeyCache(&v35, v20, a2, v40, v39) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 60, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    if ( v23 )
    {
      SetPreferredMasterKeyGuid(a1, v20, a2);
      v8 = 0;
      goto LABEL_122;
    }
LABEL_119:
    v8 = 0;
    if ( v16 )
      goto LABEL_122;
LABEL_120:
    if ( !v20 )
      return v8;
    InsertMasterKeyCache(a1, &v35, v20, a2, *v40, *v39);
    goto LABEL_122;
  }
  MasterKeyByGuid = GetMasterKeyByGuid(a1, v20, 0, &v35, 0, a2, v40, v39, &v34);
  v37 = MasterKeyByGuid;
  v21 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    if ( v34 )
    {
      switch ( v34 )
      {
        case 1u:
          v29 = "Local backup";
          break;
        case 2u:
          v29 = "DC backup";
          break;
        case 3u:
          v29 = "Storage error";
          break;
        default:
          v29 = "Delegation error";
          if ( v34 != 4 )
            v29 = "Unknown error";
          break;
      }
    }
    else
    {
      v29 = "Normal";
    }
    WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 62, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, v29);
    v21 = WPP_GLOBAL_Control;
    MasterKeyByGuid = v37;
  }
  if ( MasterKeyByGuid )
  {
    v16 = 0;
    if ( !v23 )
      goto LABEL_119;
    goto LABEL_118;
  }
  if ( v34 - 3 <= 1 )
  {
    if ( (_UNKNOWN *)v21 != &WPP_GLOBAL_Control && (*(_BYTE *)(v21 + 28) & 8) != 0 )
      WPP_SF_(*(_QWORD *)(v21 + 16), 63, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    v30 = CreateMasterKey(a1, v20, a2, (__int64)&v35);
    v8 = v30;
    if ( v30 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_109;
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v31,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwLastError",
          v30,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
          162);
        v21 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v21 == &WPP_GLOBAL_Control || (*(_BYTE *)(v21 + 28) & 1) == 0 )
        goto LABEL_109;
      v22 = 64;
      goto LABEL_34;
    }
    v32 = GetMasterKeyByGuid(a1, v20, 0, &v35, 0, a2, v40, v39, &v34);
    if ( !v32
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 65, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    }
    if ( (unsigned int)dword_18004C260 > 5
      && (qword_18004C270 & 0x400000000000LL) != 0
      && (qword_18004C278 & 0x400000000000LL) == qword_18004C278 )
    {
      v37 = v36;
      v36 = v34;
      v53 = &v37;
      v51 = &v36;
      v49 = &v41;
      *(_DWORD *)&v42.Data2 = 5;
      v43 = off_18004C268;
      *(_QWORD *)v42.Data4 = 0x400000000000LL;
      v41 = v32;
      v54 = 4;
      v52 = 4;
      v50 = 4;
      v42.Data1 = 184549376;
      v44 = *(unsigned __int16 *)off_18004C268;
      v46 = &word_180044FB6;
      v45 = 2;
      v47 = 89;
      v48 = 1;
      LODWORD(hMem) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(RegHandle, &v42, 0, 0, 5, &v43);
    }
    if ( !v32 )
    {
      v21 = WPP_GLOBAL_Control;
      goto LABEL_105;
    }
LABEL_118:
    SetPreferredMasterKeyGuid(a1, v20, a2);
    v8 = 0;
    goto LABEL_120;
  }
  if ( !v8 )
  {
LABEL_105:
    v8 = -2146893813;
    if ( (_UNKNOWN *)v21 == &WPP_GLOBAL_Control || (*(_BYTE *)(v21 + 28) & 1) == 0 )
      goto LABEL_109;
    WPP_SF_(*(_QWORD *)(v21 + 16), 66, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    goto LABEL_108;
  }
LABEL_109:
  if ( v34 != 4 )
  {
LABEL_113:
    if ( v34 == 5 )
    {
      v8 = 1131;
      if ( (_UNKNOWN *)v21 != &WPP_GLOBAL_Control && (*(_BYTE *)(v21 + 28) & 1) != 0 )
        WPP_SF_(*(_QWORD *)(v21 + 16), 68, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    }
    goto LABEL_122;
  }
  v8 = -2146892987;
  if ( (_UNKNOWN *)v21 != &WPP_GLOBAL_Control && (*(_BYTE *)(v21 + 28) & 1) != 0 )
  {
    WPP_SF_(*(_QWORD *)(v21 + 16), 67, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    v21 = WPP_GLOBAL_Control;
    goto LABEL_113;
  }
LABEL_122:
  if ( v20 )
    LocalFree(v20);
  return v8;
}

```

## disassembly

```asm
0x180018a20  push    rbp
0x180018a22  push    rbx
0x180018a23  push    rdi
0x180018a24  push    r12
0x180018a26  push    r14
0x180018a28  push    r15
0x180018a2a  lea     rbp, [rsp-18h]
0x180018a2f  sub     rsp, 118h
0x180018a36  mov     rax, cs:__security_cookie
0x180018a3d  xor     rax, rsp
0x180018a40  mov     [rbp+40h+var_50], rax
0x180018a44  xor     r15d, r15d
0x180018a47  mov     [rsp+140h+var_D0], r9
0x180018a4c  mov     qword ptr [rsp+140h+var_E8.LowPart], r15
0x180018a51  mov     r14, rdx
0x180018a54  mov     [rsp+140h+hMem], r15
0x180018a59  mov     rdi, rcx
0x180018a5c  mov     [rsp+140h+var_F0], r15d
0x180018a61  mov     [rsp+140h+var_C8], r8
0x180018a66  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a6d  lea     r12, WPP_GLOBAL_Control
0x180018a74  cmp     rcx, r12
0x180018a77  jz      short loc_180018A98
0x180018a79  test    byte ptr [rcx+1Ch], 4
0x180018a7d  jz      short loc_180018A98
0x180018a7f  mov     rcx, [rcx+10h]
0x180018a83  lea     r9, [rdi+50h]
0x180018a87  mov     edx, 30h ; '0'
0x180018a8c  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180018a93  call    WPP_SF_S
0x180018a98  mov     rcx, rdi; void *
0x180018a9b  mov     [rsp+140h+var_38], r13
0x180018aa3  call    ?CPSImpersonateClient@@YAKPEAX@Z; CPSImpersonateClient(void *)
0x180018aa8  mov     ebx, eax
0x180018aaa  test    eax, eax
0x180018aac  jz      short loc_180018B2A
0x180018aae  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ab5  cmp     rcx, r12
0x180018ab8  jz      loc_180019386
0x180018abe  test    byte ptr [rcx+1Ch], 1
0x180018ac2  jz      short loc_180018AFA
0x180018ac4  mov     rcx, [rcx+10h]
0x180018ac8  lea     r13, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180018acf  mov     dword ptr [rsp+140h+var_110], 8EEh
0x180018ad7  lea     r9, aDwlasterror; "dwLastError"
0x180018ade  mov     [rsp+140h+Uuid], r13
0x180018ae3  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180018aea  mov     dword ptr [rsp+140h+var_120], eax
0x180018aee  call    WPP_SF_sDsd
0x180018af3  mov     rcx, cs:WPP_GLOBAL_Control
0x180018afa  cmp     rcx, r12
0x180018afd  jz      loc_180019386
0x180018b03  test    byte ptr [rcx+1Ch], 1
0x180018b07  jz      loc_180019386
0x180018b0d  mov     rcx, [rcx+10h]
0x180018b11  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180018b18  mov     edx, 31h ; '1'
0x180018b1d  mov     r9d, ebx
0x180018b20  call    WPP_SF_d
0x180018b25  jmp     loc_180019386
0x180018b2a  mov     [rsp+140h+var_30], rsi
0x180018b32  call    cs:__imp_GetCurrentThread
0x180018b39  nop     dword ptr [rax+rax+00h]
0x180018b3e  mov     rcx, rax
0x180018b41  lea     rdx, [rsp+140h+var_E8]
0x180018b46  call    GetThreadAuthenticationId
0x180018b4b  lea     r13, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180018b52  mov     esi, eax
0x180018b54  test    eax, eax
0x180018b56  jnz     short loc_180018BD7
0x180018b58  call    cs:__imp_GetLastError
0x180018b5f  nop     dword ptr [rax+rax+00h]
0x180018b64  mov     ebx, eax
0x180018b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b6d  cmp     rcx, r12
0x180018b70  jz      short loc_180018BD7
0x180018b72  test    byte ptr [rcx+1Ch], 1
0x180018b76  jz      short loc_180018BA7
0x180018b78  mov     rcx, [rcx+10h]
0x180018b7c  lea     r9, aDwlasterror; "dwLastError"
0x180018b83  mov     dword ptr [rsp+140h+var_110], 8F7h
0x180018b8b  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180018b92  mov     [rsp+140h+Uuid], r13
0x180018b97  mov     dword ptr [rsp+140h+var_120], eax
0x180018b9b  call    WPP_SF_sDsd
0x180018ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ba7  cmp     rcx, r12
0x180018baa  jz      short loc_180018BD7
0x180018bac  test    byte ptr [rcx+1Ch], 1
0x180018bb0  jz      short loc_180018BD7
0x180018bb2  mov     rcx, [rcx+10h]
0x180018bb6  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180018bbd  mov     edx, 32h ; '2'
0x180018bc2  mov     r9d, ebx
0x180018bc5  call    WPP_SF_d
0x180018bca  mov     rcx, rdi; void *
0x180018bcd  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x180018bd2  jmp     loc_18001937E
0x180018bd7  mov     rcx, rdi; void *
0x180018bda  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x180018bdf  test    esi, esi
0x180018be1  jz      loc_18001937E
0x180018be7  mov     ebx, r15d
0x180018bea  mov     rcx, cs:WPP_GLOBAL_Control
0x180018bf1  cmp     rcx, r12
0x180018bf4  jz      short loc_180018C1E
0x180018bf6  test    byte ptr [rcx+1Ch], 8
0x180018bfa  jz      short loc_180018C1E
0x180018bfc  mov     eax, [rsp+140h+var_E8.HighPart]
0x180018c00  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180018c07  mov     r9d, [rsp+140h+var_E8.LowPart]
0x180018c0c  mov     edx, 34h ; '4'
0x180018c11  mov     rcx, [rcx+10h]
0x180018c15  mov     dword ptr [rsp+140h+var_120], eax
0x180018c19  call    WPP_SF_dd
0x180018c1e  mov     r15d, 1
0x180018c24  test    rdi, rdi
0x180018c27  jz      short loc_180018C39
0x180018c29  cmp     dword ptr [rdi], 270h
0x180018c2f  jnz     short loc_180018C39
0x180018c31  mov     ebx, [rdi+30h]
0x180018c34  cmp     ebx, 13h
0x180018c37  jz      short loc_180018C41
0x180018c39  mov     r9d, r15d
0x180018c3c  cmp     ebx, 14h
0x180018c3f  jnz     short loc_180018C44
0x180018c41  xor     r9d, r9d; int
0x180018c44  lea     rax, [rsp+140h+hMem]
0x180018c49  mov     r8d, r15d; int
0x180018c4c  xor     edx, edx; void *
0x180018c4e  mov     [rsp+140h+var_120], rax; unsigned __int16 **
0x180018c53  mov     rcx, rdi; void *
0x180018c56  call    ?CPSGetUserStorageArea@@YAKPEAX0HHPEAPEAG@Z; CPSGetUserStorageArea(void *,void *,int,int,ushort * *)
0x180018c5b  mov     rsi, [rsp+140h+hMem]
0x180018c60  mov     ebx, eax
0x180018c62  test    eax, eax
0x180018c64  jz      short loc_180018CDB
0x180018c66  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c6d  cmp     rcx, r12
0x180018c70  jz      loc_180019294
0x180018c76  test    [rcx+1Ch], r15b
0x180018c7a  jz      short loc_180018CAB
0x180018c7c  mov     rcx, [rcx+10h]
0x180018c80  lea     r9, aDwlasterror; "dwLastError"
0x180018c87  mov     dword ptr [rsp+140h+var_110], 91Ch
0x180018c8f  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180018c96  mov     [rsp+140h+Uuid], r13
0x180018c9b  mov     dword ptr [rsp+140h+var_120], eax
0x180018c9f  call    WPP_SF_sDsd
0x180018ca4  mov     rcx, cs:WPP_GLOBAL_Control
0x180018cab  cmp     rcx, r12
0x180018cae  jz      loc_180019294
0x180018cb4  test    [rcx+1Ch], r15b
0x180018cb8  jz      loc_180019294
0x180018cbe  mov     edx, 35h ; '5'
0x180018cc3  mov     rcx, [rcx+10h]
0x180018cc7  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180018cce  mov     r9d, ebx
0x180018cd1  call    WPP_SF_d
0x180018cd6  jmp     loc_18001928D
0x180018cdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ce2  lea     rax, WPP_GLOBAL_Control
0x180018ce9  xor     r12d, r12d
0x180018cec  cmp     rcx, rax
0x180018cef  jz      short loc_180018D0F
0x180018cf1  test    byte ptr [rcx+1Ch], 8
0x180018cf5  jz      short loc_180018D0F
0x180018cf7  mov     rcx, [rcx+10h]
0x180018cfb  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180018d02  mov     edx, 36h ; '6'
0x180018d07  mov     r9, rsi
0x180018d0a  call    WPP_SF_S
0x180018d0f  mov     rcx, rdi; void *
0x180018d12  call    ?IsDomainBackupRequired@@YAHPEAX@Z; IsDomainBackupRequired(void *)
0x180018d17  xor     ecx, ecx
0x180018d19  mov     r8, r14; struct _GUID *
0x180018d1c  test    eax, eax
0x180018d1e  mov     rdx, rsi; Src
0x180018d21  setnz   cl
0x180018d24  mov     [rsp+140h+var_E0], ecx
0x180018d28  mov     rcx, rdi; void *
0x180018d2b  call    ?GetPreferredMasterKeyGuid@@YAJPEAXPEBGPEAU_GUID@@@Z; GetPreferredMasterKeyGuid(void *,ushort const *,_GUID *)
0x180018d30  test    eax, eax
0x180018d32  jns     loc_180018EA7
0x180018d38  cmp     eax, 0C0000071h
0x180018d3d  jnz     loc_180018DEE
0x180018d43  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d4a  lea     rax, WPP_GLOBAL_Control
0x180018d51  cmp     rcx, rax
0x180018d54  jz      short loc_180018D77
0x180018d56  test    byte ptr [rcx+1Ch], 8
0x180018d5a  jz      short loc_180018D77
0x180018d5c  mov     rcx, [rcx+10h]
0x180018d60  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180018d67  mov     edx, 37h ; '7'
0x180018d6c  mov     r9d, 0C0000071h
0x180018d72  call    WPP_SF_d
0x180018d77  xorps   xmm0, xmm0
0x180018d7a  lea     rax, [rsp+140h+var_E8]
0x180018d7f  mov     r9d, r15d
0x180018d82  mov     [rsp+140h+var_120], rax; __int64
0x180018d87  lea     r8, [rbp+40h+var_B8]; struct _GUID *
0x180018d8b  mov     rdx, rsi; unsigned __int16 *
0x180018d8e  mov     rcx, rdi; void *
0x180018d91  movups  xmmword ptr [rbp+40h+var_B8.Data1], xmm0
0x180018d95  call    CreateMasterKey
0x180018d9a  mov     ebx, eax
0x180018d9c  test    eax, eax
0x180018d9e  lea     rax, WPP_GLOBAL_Control
0x180018da5  jnz     short loc_180018DB7
0x180018da7  movups  xmm0, xmmword ptr [rbp+40h+var_B8.Data1]
0x180018dab  mov     r12d, r15d
0x180018dae  movups  xmmword ptr [r14], xmm0
0x180018db2  jmp     loc_180018EAE
0x180018db7  mov     rcx, cs:WPP_GLOBAL_Control
0x180018dbe  cmp     rcx, rax
0x180018dc1  jz      loc_180018ED8
0x180018dc7  test    byte ptr [rcx+1Ch], 8
0x180018dcb  jz      loc_180018EB5
0x180018dd1  mov     rcx, [rcx+10h]
0x180018dd5  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180018ddc  mov     edx, 38h ; '8'
0x180018de1  mov     r9d, ebx
0x180018de4  call    WPP_SF_d
0x180018de9  jmp     loc_180018EA7
0x180018dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180018df5  lea     r12, WPP_GLOBAL_Control
0x180018dfc  cmp     rcx, r12
0x180018dff  jz      short loc_180018E1F
0x180018e01  test    byte ptr [rcx+1Ch], 8
0x180018e05  jz      short loc_180018E1F
0x180018e07  mov     rcx, [rcx+10h]
0x180018e0b  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180018e12  mov     edx, 39h ; '9'
0x180018e17  mov     r9d, eax
0x180018e1a  call    WPP_SF_d
0x180018e1f  mov     r9d, [rsp+140h+var_E0]
0x180018e24  lea     rax, [rsp+140h+var_E8]
0x180018e29  mov     r8, r14; struct _GUID *
0x180018e2c  mov     [rsp+140h+var_120], rax; __int64
0x180018e31  mov     rdx, rsi; unsigned __int16 *
0x180018e34  mov     rcx, rdi; void *
0x180018e37  call    CreateMasterKey
0x180018e3c  mov     ebx, eax
0x180018e3e  test    eax, eax
0x180018e40  jz      short loc_180018EA4
0x180018e42  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e49  cmp     rcx, r12
0x180018e4c  jz      loc_180019294
0x180018e52  test    [rcx+1Ch], r15b
0x180018e56  jz      short loc_180018E87
0x180018e58  mov     rcx, [rcx+10h]
0x180018e5c  lea     r9, aDwlasterror; "dwLastError"
0x180018e63  mov     dword ptr [rsp+140h+var_110], 953h
0x180018e6b  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180018e72  mov     [rsp+140h+Uuid], r13
0x180018e77  mov     dword ptr [rsp+140h+var_120], eax
0x180018e7b  call    WPP_SF_sDsd
0x180018e80  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e87  cmp     rcx, r12
0x180018e8a  jz      loc_180019294
0x180018e90  test    [rcx+1Ch], r15b
0x180018e94  jz      loc_180019294
0x180018e9a  mov     edx, 3Ah ; ':'
0x180018e9f  jmp     loc_180018CC3
0x180018ea4  mov     r12d, r15d
0x180018ea7  lea     rax, WPP_GLOBAL_Control
0x180018eae  mov     rcx, cs:WPP_GLOBAL_Control
0x180018eb5  cmp     rcx, rax
0x180018eb8  jz      short loc_180018ED8
0x180018eba  test    byte ptr [rcx+1Ch], 8
0x180018ebe  jz      short loc_180018ED8
0x180018ec0  mov     rcx, [rcx+10h]
0x180018ec4  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180018ecb  mov     edx, 3Bh ; ';'
0x180018ed0  mov     r9, r14
0x180018ed3  call    WPP_SF__guid_
0x180018ed8  mov     rax, [rsp+140h+var_D0]
0x180018edd  lea     rcx, [rsp+140h+var_E8]; struct _LUID *
0x180018ee2  mov     r9, [rsp+140h+var_C8]; unsigned __int8 **
0x180018ee7  mov     r8, r14; struct _GUID *
0x180018eea  mov     rdx, rsi; unsigned __int16 *
0x180018eed  mov     [rsp+140h+var_120], rax; unsigned int *
0x180018ef2  call    ?SearchMasterKeyCache@@YAHPEAU_LUID@@PEBGPEAU_GUID@@PEAPEAEPEAK@Z; SearchMasterKeyCache(_LUID *,ushort const *,_GUID *,uchar * *,ulong *)
0x180018ef7  test    eax, eax
0x180018ef9  jz      short loc_180018F47
0x180018efb  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f02  lea     rax, WPP_GLOBAL_Control
0x180018f09  cmp     rcx, rax
0x180018f0c  jz      short loc_180018F29
0x180018f0e  test    byte ptr [rcx+1Ch], 8
0x180018f12  jz      short loc_180018F29
0x180018f14  mov     rcx, [rcx+10h]
0x180018f18  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180018f1f  mov     edx, 3Ch ; '<'
0x180018f24  call    WPP_SF_
0x180018f29  test    r12d, r12d
0x180018f2c  jz      loc_18001932F
0x180018f32  mov     r8, r14; struct _GUID *
0x180018f35  mov     rdx, rsi; unsigned __int16 *
  ... truncated ...
```
