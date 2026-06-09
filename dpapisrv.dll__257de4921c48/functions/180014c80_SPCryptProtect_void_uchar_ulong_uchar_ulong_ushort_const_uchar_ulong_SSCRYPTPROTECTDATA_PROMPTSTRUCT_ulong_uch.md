# SPCryptProtect(void *,uchar * *,ulong *,uchar *,ulong,ushort const *,uchar *,ulong,_SSCRYPTPROTECTDATA_PROMPTSTRUCT *,ulong,uchar *,ulong)

- ea: `0x180014c80`
- end: `0x18001635c`
- name: `?SPCryptProtect@@YAKPEAXPEAPEAEPEAKPEAEKPEBG3KPEAU_SSCRYPTPROTECTDATA_PROMPTSTRUCT@@K3K@Z`
- size: `5852`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *, unsigned __int8 **, unsigned int *, unsigned __int8 *, ULONG, WCHAR *Src, unsigned __int8 *, ULONG, struct _SSCRYPTPROTECTDATA_PROMPTSTRUCT *, unsigned int, unsigned __int8 *, ULONG)`
- caller_count: `2`
- callee_count: `33`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000e0c0`
- `0x180010870`

## callees

- `0x1800010ac`
- `0x1800029d0`
- `0x180002f18`
- `0x180003080`
- `0x1800063c0`
- `0x180006510`
- `0x180008000`
- `0x1800083b0`
- `0x18000a830`
- `0x18000b680`
- `0x18000bfa4`
- `0x18000c450`
- `0x18000c4a0`
- `0x18000c8c0`
- `0x18000e4b0`
- `0x18000fce0`
- `0x1800114b4`
- `0x180013f2c`
- `0x180013f70`
- `0x18001444c`
- `0x180014c80`
- `0x180018a20`
- `0x180019d00`
- `0x18001c340`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001e1b4`
- `0x18001eb8c`
- `0x18002b0ec`
- `0x18002c4f8`
- `0x18002c834`
- `0x18002def8`
- `0x18003c62c`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180015992`
- `RPCRT4!RpcImpersonateClient` at `0x180015992`
- `RPCRT4!UuidToStringW` at `0x18001533f`
- `RPCRT4!UuidToStringW` at `0x18001533f`
- `RPCRT4!RpcStringFreeW` at `0x18001537f`
- `RPCRT4!RpcStringFreeW` at `0x18001537f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180015a06`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180015a52`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180015a06`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180015a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001548f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001548f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014d60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800162c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016304`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016319`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014d60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800162c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016304`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016319`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015afb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015bb3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015afb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015bb3`
- `bcrypt!BCryptEncrypt` at `0x180015ead`
- `bcrypt!BCryptEncrypt` at `0x180015ead`
- `bcrypt!BCryptGenRandom` at `0x180015410`
- `bcrypt!BCryptGenRandom` at `0x180015711`
- `bcrypt!BCryptGenRandom` at `0x180015410`
- `bcrypt!BCryptGenRandom` at `0x180015711`
- `bcrypt!BCryptFinishHash` at `0x180015f95`
- `bcrypt!BCryptFinishHash` at `0x180015f95`
- `bcrypt!BCryptDestroyHash` at `0x1800156eb`
- `bcrypt!BCryptDestroyHash` at `0x1800162ec`
- `bcrypt!BCryptDestroyHash` at `0x1800156eb`
- `bcrypt!BCryptDestroyHash` at `0x1800162ec`
- `bcrypt!BCryptHashData` at `0x180015574`
- `bcrypt!BCryptHashData` at `0x1800155c6`
- `bcrypt!BCryptHashData` at `0x180015627`
- `bcrypt!BCryptHashData` at `0x18001586f`
- `bcrypt!BCryptHashData` at `0x1800158c6`
- `bcrypt!BCryptHashData` at `0x180015927`
- `bcrypt!BCryptHashData` at `0x180015f47`
- `bcrypt!BCryptHashData` at `0x180015574`
- `bcrypt!BCryptHashData` at `0x1800155c6`
- `bcrypt!BCryptHashData` at `0x180015627`
- `bcrypt!BCryptHashData` at `0x18001586f`
- `bcrypt!BCryptHashData` at `0x1800158c6`
- `bcrypt!BCryptHashData` at `0x180015927`
- `bcrypt!BCryptHashData` at `0x180015f47`
- `bcrypt!BCryptDestroyKey` at `0x1800162d6`
- `bcrypt!BCryptDestroyKey` at `0x1800162d6`
- `bcrypt!BCryptCreateHash` at `0x1800154fb`
- `bcrypt!BCryptCreateHash` at `0x18001581b`
- `bcrypt!BCryptCreateHash` at `0x1800154fb`
- `bcrypt!BCryptCreateHash` at `0x18001581b`
- `CRYPTBASE!SystemFunction041` at `0x1800159b1`
- `CRYPTBASE!SystemFunction041` at `0x1800159b1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180015353`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180015353`
- `ntdll!RtlEnterCriticalSection` at `0x180014d93`
- `ntdll!RtlEnterCriticalSection` at `0x180014d93`
- `ntdll!RtlNtStatusToDosError` at `0x180015550`
- `ntdll!RtlNtStatusToDosError` at `0x180015f02`
- `ntdll!RtlNtStatusToDosError` at `0x180015fea`
- `ntdll!RtlNtStatusToDosError` at `0x180015550`
- `ntdll!RtlNtStatusToDosError` at `0x180015f02`
- `ntdll!RtlNtStatusToDosError` at `0x180015fea`
- `ntdll!RtlLeaveCriticalSection` at `0x180014df8`
- `ntdll!RtlLeaveCriticalSection` at `0x180014df8`

## string_xrefs

- `0x18001514f`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`
- `0x1800151b0`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`

## pseudocode

```c
__int64 __fastcall SPCryptProtect(
        RPC_BINDING_HANDLE *a1,
        unsigned __int8 **a2,
        unsigned int *a3,
        unsigned __int8 *a4,
        ULONG a5,
        WCHAR *Src,
        unsigned __int8 *a7,
        ULONG a8,
        struct _SSCRYPTPROTECTDATA_PROMPTSTRUCT *a9,
        unsigned int a10,
        unsigned __int8 *a11,
        ULONG a12)
{
  int v12; // ebx
  RPC_BINDING_HANDLE *v13; // r14
  int v14; // edi
  __int64 v15; // r8
  unsigned int v16; // esi
  unsigned int v17; // r13d
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rdx
  unsigned int LastError; // ebx
  RPC_BINDING_HANDLE v22; // rcx
  HLOCAL v23; // rdi
  unsigned int updated; // eax
  int v25; // edx
  __int64 v26; // r12
  void *v27; // rdx
  __int64 v28; // rcx
  void *v29; // rdi
  DWORD v30; // eax
  void *v31; // r13
  DWORD v32; // eax
  unsigned int PreferredMasterKey; // eax
  unsigned int v34; // eax
  ULONG v35; // ecx
  ULONG v36; // eax
  unsigned int v37; // edx
  NTSTATUS v38; // ebx
  unsigned int v39; // r9d
  DWORD v40; // eax
  int v41; // ebx
  unsigned int v42; // eax
  NTSTATUS v43; // eax
  unsigned int v44; // edx
  NTSTATUS v45; // ebx
  ULONG v46; // r13d
  DWORD v47; // eax
  ULONG v48; // edi
  _BYTE *v49; // rbx
  NTSTATUS v50; // eax
  unsigned int v51; // edi
  ULONG v52; // eax
  UCHAR *v53; // rax
  unsigned int v54; // ebx
  int v55; // eax
  __int64 v56; // rax
  bool v57; // zf
  unsigned int v58; // eax
  unsigned int *v59; // rbx
  unsigned int v60; // eax
  unsigned __int8 *v61; // rax
  unsigned __int8 **v62; // rdi
  unsigned __int8 *v63; // r13
  size_t v64; // r8
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  unsigned int v69; // ecx
  char *v70; // rdi
  unsigned int v71; // ecx
  __int64 v72; // rbx
  unsigned int v73; // eax
  HLOCAL v74; // rdx
  size_t v75; // r8
  char *v76; // rdi
  __int64 v77; // rbx
  ULONG v78; // eax
  char *v79; // rdi
  __int64 v80; // rbx
  ULONG *v81; // rdi
  int v82; // ecx
  unsigned int v83; // r8d
  int v84; // eax
  unsigned int v85; // r8d
  unsigned int v86; // r13d
  int v87; // ebx
  ULONG v88; // eax
  PUCHAR v89; // rdx
  size_t v90; // r8
  __int64 v91; // rbx
  char *v92; // rdi
  UCHAR *v93; // rdi
  int v94; // r13d
  char *v95; // rbx
  NTSTATUS v96; // eax
  NTSTATUS v97; // edi
  unsigned __int8 **v98; // rdi
  unsigned int *v99; // rax
  WCHAR *v100; // rdi
  const WCHAR *v101; // rdx
  unsigned int v102; // r13d
  int v103; // edx
  __int64 v104; // rcx
  int v105; // r8d
  int v106; // r9d
  unsigned int v107; // eax
  int v108; // eax
  unsigned int v109; // edx
  unsigned int v110; // r9d
  __int64 v111; // rax
  int v112; // r12d
  UCHAR *v113; // rax
  __int64 v114; // rcx
  UCHAR *v115; // rax
  __int64 v116; // rcx
  _BYTE *v117; // rcx
  __int64 v118; // rax
  PUCHAR pbSecret; // [rsp+20h] [rbp-E0h]
  char dwFlags; // [rsp+30h] [rbp-D0h]
  ULONG dwFlagsa[2]; // [rsp+30h] [rbp-D0h]
  unsigned int dwFlagsb; // [rsp+30h] [rbp-D0h]
  unsigned int MemorySize; // [rsp+50h] [rbp-B0h]
  unsigned int v125; // [rsp+54h] [rbp-ACh]
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v127; // [rsp+60h] [rbp-A0h]
  unsigned int v128; // [rsp+64h] [rbp-9Ch]
  int v129; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v130; // [rsp+6Ch] [rbp-94h]
  unsigned int Size; // [rsp+70h] [rbp-90h] BYREF
  ULONG Size_4; // [rsp+74h] [rbp-8Ch]
  ULONG cbBuffer; // [rsp+78h] [rbp-88h]
  unsigned int v134; // [rsp+7Ch] [rbp-84h]
  unsigned int v135; // [rsp+80h] [rbp-80h]
  RPC_WSTR StringUuid; // [rsp+88h] [rbp-78h] BYREF
  ULONG pcbResult; // [rsp+90h] [rbp-70h] BYREF
  ULONG cbInput; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v139; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL v140; // [rsp+A0h] [rbp-60h] BYREF
  int v141; // [rsp+A8h] [rbp-58h]
  PUCHAR pbOutput; // [rsp+B0h] [rbp-50h]
  HLOCAL hMem; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int8 **v144; // [rsp+C0h] [rbp-40h]
  unsigned int *v145; // [rsp+C8h] [rbp-38h]
  BCRYPT_KEY_HANDLE hKey; // [rsp+D0h] [rbp-30h] BYREF
  PUCHAR v147; // [rsp+D8h] [rbp-28h]
  BCRYPT_HANDLE hObject; // [rsp+E0h] [rbp-20h] BYREF
  void *BCryptProviderHandle; // [rsp+E8h] [rbp-18h] BYREF
  PUCHAR pbInput; // [rsp+F0h] [rbp-10h]
  PVOID Memory; // [rsp+F8h] [rbp-8h]
  UUID Uuid; // [rsp+100h] [rbp+0h] BYREF
  UCHAR v153[24]; // [rsp+110h] [rbp+10h] BYREF
  UCHAR pbBuffer[16]; // [rsp+128h] [rbp+28h] BYREF
  __int128 v155; // [rsp+138h] [rbp+38h]
  UCHAR v156[40]; // [rsp+148h] [rbp+48h] BYREF
  unsigned __int16 v157[64]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v158[40]; // [rsp+1F0h] [rbp+F0h] BYREF

  v12 = 0;
  MemorySize = a5;
  v13 = a1;
  v14 = 0;
  pbInput = a7;
  LODWORD(a1) = 0;
  v147 = a11;
  Memory = a4;
  v145 = a3;
  v144 = a2;
  hKey = 0;
  phHash = 0;
  pcbResult = 0;
  v140 = 0;
  Size = 0;
  hMem = 0;
  cbInput = 0;
  v135 = 0;
  v158[0] = 0;
  *(_OWORD *)pbBuffer = 0;
  v155 = 0;
  Uuid = 0;
  if ( v13 )
  {
    if ( *(_DWORD *)v13 == 624 )
    {
      LODWORD(a1) = *((_DWORD *)v13 + 12);
      v135 = (unsigned int)a1;
      if ( (_DWORD)a1 == 19 )
        goto LABEL_7;
    }
  }
  v141 = 0;
  if ( (_DWORD)a1 != 20 )
    goto LABEL_12;
  v135 = 20;
  if ( v13 )
  {
    if ( *(_DWORD *)v13 == 624 )
    {
LABEL_7:
      if ( *((_DWORD *)v13 + 12) != 18 )
      {
        a1 = (RPC_BINDING_HANDLE *)v13[5];
        if ( a1 )
        {
          LocalFree(a1);
          v13[5] = 0;
        }
        *((_DWORD *)v13 + 12) = 18;
      }
    }
  }
  v141 = 1;
LABEL_12:
  UpdateGlobals((int)a1);
  if ( dword_18004CCB4 )
  {
    RtlEnterCriticalSection(&stru_18004C978);
    v12 = 1;
  }
  v16 = 26115;
  v127 = 26115;
  if ( dword_18004C548 == 26115 )
    goto LABEL_17;
  if ( dword_18004C548 != -1 )
  {
    if ( dword_18004C548 == 26128 )
      goto LABEL_60;
    goto LABEL_59;
  }
  if ( dword_18004C550 == 32772 )
  {
LABEL_17:
    v17 = 32772;
    goto LABEL_18;
  }
  if ( dword_18004C550 != 32782 )
  {
LABEL_59:
    v16 = 26625;
    v127 = 26625;
    if ( dword_18004C548 == 26625 )
      goto LABEL_17;
  }
LABEL_60:
  v16 = 26128;
  v17 = 32782;
  v127 = 26128;
LABEL_18:
  v125 = v17;
  v134 = -1;
  v130 = -1;
  if ( v12 )
    RtlLeaveCriticalSection(&stru_18004C978);
  *((_DWORD *)v13 + 13) = v16;
  *((_DWORD *)v13 + 14) = v17;
  if ( (a10 & 4) != 0 )
  {
    if ( *(_DWORD *)v13 == 624 )
      *((_DWORD *)v13 + 4) = 1;
    v14 = 4;
  }
  v18 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    WPP_SF_q(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, v15, v13);
    v18 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        WPP_SF_q(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, v19, v13[1]);
        v18 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(v18 + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *(_QWORD *)(v18 + 16),
            12,
            WPP_96027a338e1f3ff10006943bca18f271_Traceguids,
            *((unsigned int *)v13 + 4));
          v18 = WPP_GLOBAL_Control;
        }
        if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control )
        {
          if ( (*(_BYTE *)(v18 + 28) & 4) != 0 )
          {
            WPP_SF_d(
              *(_QWORD *)(v18 + 16),
              13,
              WPP_96027a338e1f3ff10006943bca18f271_Traceguids,
              *((unsigned int *)v13 + 5));
            v18 = WPP_GLOBAL_Control;
          }
          if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control )
          {
            if ( (*(_BYTE *)(v18 + 28) & 4) != 0 )
            {
              WPP_SF_q(*(_QWORD *)(v18 + 16), 14, v19, v13[3]);
              v18 = WPP_GLOBAL_Control;
            }
            if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control )
            {
              if ( (*(_BYTE *)(v18 + 28) & 4) != 0 )
              {
                WPP_SF_S(*(_QWORD *)(v18 + 16), 15, WPP_96027a338e1f3ff10006943bca18f271_Traceguids, v13 + 10);
                v18 = WPP_GLOBAL_Control;
              }
              if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control )
              {
                if ( (*(_BYTE *)(v18 + 28) & 4) != 0 )
                {
                  WPP_SF_dd(
                    *(_QWORD *)(v18 + 16),
                    16,
                    WPP_96027a338e1f3ff10006943bca18f271_Traceguids,
                    *((unsigned int *)v13 + 15),
                    *((_DWORD *)v13 + 16));
                  v18 = WPP_GLOBAL_Control;
                }
                if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control && (*(_BYTE *)(v18 + 28) & 4) != 0 )
                {
                  WPP_SF_d(
                    *(_QWORD *)(v18 + 16),
                    17,
                    WPP_96027a338e1f3ff10006943bca18f271_Traceguids,
                    *((unsigned int *)v13 + 12));
                  v18 = WPP_GLOBAL_Control;
                }
              }
            }
          }
        }
      }
    }
  }
  v139 = a10 & 0x4000000;
  if ( (a10 & 0x4000000) != 0 )
  {
    RemoveMasterKeyCache(0, 0);
    v18 = WPP_GLOBAL_Control;
  }
  if ( (a10 & 8) == 0 )
  {
    if ( (a10 & 0x80u) != 0 )
    {
      if ( (a10 & 0x9FFFFF7F) != 0 )
      {
        if ( (_UNKNOWN *)v18 == &WPP_GLOBAL_Control || (*(_BYTE *)(v18 + 28) & 1) == 0 )
          goto LABEL_55;
        v20 = 25;
        goto LABEL_54;
      }
      updated = DpapiUpdateLsaSecret(v13);
      LastError = updated;
      if ( updated
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v25,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          updated,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          128);
      }
      goto LABEL_317;
    }
    pbOutput = 0;
    v129 = 0;
    v128 = a10 & 0x20000010 | v14;
    hObject = (BCRYPT_HANDLE)GetBCryptProviderHandle(v16);
    v26 = -1;
    if ( !hObject )
    {
      LastError = GetLastError();
      v28 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_269;
      dwFlags = -110;
      goto LABEL_87;
    }
    BCryptProviderHandle = (void *)GetBCryptProviderHandle(v17);
    v29 = BCryptProviderHandle;
    if ( !BCryptProviderHandle )
    {
      v30 = GetLastError();
      LastError = v30;
      LODWORD(v28) = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          v30,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          157);
      goto LABEL_269;
    }
    v31 = (void *)GetBCryptProviderHandle(v17);
    if ( !v31 )
    {
      v32 = GetLastError();
      LastError = v32;
      LODWORD(v28) = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          v32,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          168);
      goto LABEL_269;
    }
    PreferredMasterKey = GetPreferredMasterKey(v13, &Uuid, (unsigned __int8 **)&hMem, &cbInput);
    LastError = PreferredMasterKey;
    if ( PreferredMasterKey )
    {
      v129 = 6;
      LODWORD(v28) = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          PreferredMasterKey,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          183);
      goto LABEL_269;
    }
    StringUuid = 0;
    if ( !UuidToStringW(&Uuid, &StringUuid) )
    {
      v34 = lstrlenW(StringUuid);
      if ( v34 < 0x28 )
        memcpy_0(v158, StringUuid, 2LL * (v34 + 1));
      RpcStringFreeW(&StringUuid);
    }
    if ( !(unsigned int)FMyPrimitiveSHA((PUCHAR)hMem, cbInput, v153) )
    {
      LastError = 13;
      v28 = WPP_GLOBAL_Control;
      v27 = &WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_269;
      dwFlags = -56;
      goto LABEL_87;
    }
    v35 = 16;
    v36 = 16;
    if ( v127 == 26128 )
      v36 = 32;
    Size_4 = v36;
    if ( v125 == 32782 )
      v35 = 32;
    cbBuffer = v35;
    v38 = BCryptGenRandom(0, pbBuffer, v36, 2u);
    if ( v38 < 0 )
    {
      LastError = v38 | 0x10000000;
      v28 = WPP_GLOBAL_Control;
      v27 = &WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_269;
      dwFlags = -32;
      goto LABEL_87;
    }
    if ( v125 == 32772 )
    {
      if ( !INCORRECT_FMyPrimitiveCryptHMAC(v153, v37, pbBuffer, Size_4, v29, 0x8004u, &phHash) )
      {
        v40 = GetLastError();
        LastError = v40;
        LODWORD(v28) = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            (unsigned int)&WPP_GLOBAL_Control,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"dwRet",
            v40,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
            245);
        goto LABEL_269;
      }
    }
    else
    {
      v41 = BCryptCreateHash(v31, &phHash, 0, 0, v153, 0x14u, 0);
      if ( v41 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            (unsigned int)&WPP_GLOBAL_Control,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"Status",
            v41,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
            4);
        goto LABEL_126;
      }
      v41 = BCryptHashData(phHash, pbBuffer, Size_4, 0);
      if ( v41 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            (unsigned int)&WPP_GLOBAL_Control,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"Status",
            v41,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
            15);
        goto LABEL_126;
      }
    }
    if ( pbInput )
    {
      v41 = BCryptHashData(phHash, pbInput, a8, 0);
      if ( v41 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            (unsigned int)&WPP_GLOBAL_Control,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"Status",
            v41,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
            30);
LABEL_126:
        LastError = RtlNtStatusToDosError(v41);
LABEL_269:
        v86 = MemorySize;
LABEL_270:
        v100 = (WCHAR *)&Class;
        if ( !Src || (LODWORD(v101) = (_DWORD)Src, !*Src) )
          v101 = &Class;
        dwFlagsb = v86;
        LOBYTE(v28) = 1;
        v102 = v128;
        SendETWInformation(v28, (_DWORD)v101, (unsigned int)&Uuid, a10, v128, LastError, dwFlagsb);
        if ( LastError )
        {
          if ( (unsigned int)dword_18004C260 > 5 )
          {
            v104 = qword_18004C278;
            v103 = 0;
            if ( (qword_18004C270 & 0x400000000000LL) != 0 && (qword_18004C278 & 0x400000000000LL) == qword_18004C278 )
            {
              if ( Src && *Src )
                v100 = Src;
              LODWORD(StringUuid) = a10;
              hObject = &Uuid;
              BCryptProviderHandle = v100;
              v139 = v102;
              Size = LastError;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                qword_18004C278,
                (unsigned int)byte_180044B95,
                v105,
                v106,
                (__int64)&Size,
                (__int64)&hObject,
                (__int64)&StringUuid,
                (__int64)&v139,
                (__int64)&BCryptProviderHandle);
            }
          }
          if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 0x40) != 0 )
            McTemplateU0dq_EtwEventWriteTransfer(v104, ETW_LOG_DPAPI_PROTECT_FAILED, LastError, (unsigned int)v129);
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_sDsd(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              v103,
              (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
              (unsigned int)"dwRet",
              LastError,
              (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
              249);
        }
        if ( ((v102 & 0x10) != 0 || LastError) && Src && *Src )
        {
          v107 = 0;
          while ( v127 != *((_DWORD *)&g_AlgToString + 4 * v107) )
          {
            if ( ++v107 >= 0x17 )
            {
              LODWORD(pbSecret) = v134;
              v108 = StringCchPrintfW(v157, 0x1Eu, L"Unknown 0x%lx - %d", v127, pbSecret);
              goto LABEL_295;
            }
          }
          v108 = StringCchPrintfW(v157, 0x1Eu, (const unsigned __int16 *)*(&g_AlgToString + 2 * v107 + 1), v134);
LABEL_295:
          if ( v108 )
            goto LABEL_298;
          do
            ++v26;
          while ( v157[v26] );
          v110 = v130;
          v111 = (unsigned int)v26;
          v112 = v26 + 1;
          v157[v111] = 44;
          v157[v112] = 32;
          if ( AlgIDToString(&v157[v112 + 1], v109, v125, v110) )
LABEL_298:
            v157[0] = 0;
          CPSAudit(v13[3], 0x256u, v158, Src, v102, v157, LastError);
        }
        v113 = v153;
        v114 = 20;
        do
        {
          *v113++ = 0;
          --v114;
        }
        while ( v114 );
        v115 = pbBuffer;
        v116 = 32;
        do
        {
          *v115++ = 0;
          --v116;
        }
        while ( v116 );
        v117 = hMem;
        if ( hMem )
        {
          v118 = cbInput;
          if ( cbInput )
          {
            do
            {
              *v117++ = 0;
              --v118;
            }
            while ( v118 );
            v117 = hMem;
          }
          LocalFree(v117);
        }
        if ( hKey )
          BCryptDestroyKey(hKey);
        if ( phHash )
          BCryptDestroyHash(phHash);
        if ( pbOutput )
          LocalFree(pbOutput);
        if ( v140 )
          LocalFree(v140);
        goto LABEL_317;
      }
    }
    if ( v147 )
    {
      if ( a12 )
      {
        v41 = BCryptHashData(phHash, v147, a12, 0);
        if ( v41 < 0 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_sDsd(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              (unsigned int)&WPP_GLOBAL_Control,
              (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
              (unsigned int)"Status",
              v41,
              (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
              48);
          goto LABEL_126;
        }
      }
    }
    dwFlagsa[0] = 0;
    v42 = FMyDeriveBCryptKey(
            hObject,
            phHash,
            v127,
            v39,
            4u,
            0,
            *(size_t *)dwFlagsa,
            (unsigned __int8 **)&v140,
            &Size,
            &hKey);
    LastError = v42;
    if ( v42 )
    {
      LODWORD(v28) = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          v42,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          68);
      goto LABEL_269;
    }
    BCryptDestroyHash(phHash);
    phHash = 0;
    v43 = BCryptGenRandom(0, v156, cbBuffer, 2u);
    v45 = v43;
    if ( v43 < 0 )
    {
      LODWORD(v28) = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"Status",
          v43,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          84);
      LastError = v45 | 0x10000000;
      goto LABEL_269;
    }
    if ( v125 == 32772 )
    {
      v46 = cbBuffer;
      if ( !INCORRECT_FMyPrimitiveCryptHMAC(v153, v44, v156, cbBuffer, BCryptProviderHandle, 0x8004u, &phHash) )
      {
        v47 = GetLastError();
        LastError = v47;
        LODWORD(v28) = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            (unsigned int)&WPP_GLOBAL_Control,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"dwRet",
            v47,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
            100);
        goto LABEL_269;
      }
    }
    else
    {
      v41 = BCryptCreateHash(v31, &phHash, 0, 0, v153, 0x14u, 0);
      if ( v41 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            (unsigned int)&WPP_GLOBAL_Control,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"Status",
            v41,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
            115);
        goto LABEL_126;
      }
      v46 = cbBuffer;
      v41 = BCryptHashData(phHash, v156, cbBuffer, 0);
      if ( v41 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            (unsigned int)&WPP_GLOBAL_Control,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"Status",
            v41,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
            126);
        goto LABEL_126;
      }
    }
    if ( pbInput )
    {
      v41 = BCryptHashData(phHash, pbInput, a8, 0);
      if ( v41 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            (unsigned int)&WPP_GLOBAL_Control,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"Status",
            v41,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
            141);
        goto LABEL_126;
      }
    }
    if ( v147 )
    {
      if ( a12 )
      {
        v41 = BCryptHashData(phHash, v147, a12, 0);
        if ( v41 < 0 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_sDsd(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              (unsigned int)&WPP_GLOBAL_Control,
              (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
              (unsigned int)"Status",
              v41,
              (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
              159);
          goto LABEL_126;
        }
      }
    }
    v48 = a5;
    if ( (a10 & 0x60000000) == 0 )
    {
      if ( a5 < 8 || (a5 & 7) != 0 )
      {
        LastError = 13;
        v28 = WPP_GLOBAL_Control;
        v27 = &WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_269;
        dwFlags = -77;
LABEL_87:
        WPP_SF_sDsd(
          *(_QWORD *)(v28 + 16),
          (_DWORD)v27,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          LastError,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          dwFlags);
        goto LABEL_269;
      }
      if ( !RpcImpersonateClient(v13[1]) )
      {
        v49 = Memory;
        v50 = SystemFunction041(Memory, a5, 2u);
        if ( v50 >= 0 )
        {
          RevertToSelf();
          v52 = (unsigned __int8)v49[a5 - 1];
          if ( v49[a5 - 1] && v52 <= a5 && v52 <= 8 )
          {
            v48 = a5 - v52;
            MemorySize = a5 - v52;
          }
          else
          {
            v28 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
LABEL_185:
              v51 = v48 + 16;
              if ( MemorySize > v51 )
              {
                LastError = 534;
                if ( (_UNKNOWN *)v28 == &WPP_GLOBAL_Control || (*(_BYTE *)(v28 + 28) & 1) == 0 )
                  goto LABEL_269;
                dwFlags = -33;
                goto LABEL_87;
              }
              v53 = (UCHAR *)LocalAlloc(0, v51);
              pbOutput = v53;
              if ( !v53 )
              {
                LastError = 14;
                v28 = WPP_GLOBAL_Control;
                v27 = &WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
                {
                  goto LABEL_269;
                }
                dwFlags = -24;
                goto LABEL_87;
              }
              v54 = v130 >> 3;
              LODWORD(StringUuid) = v130 >> 3;
              memcpy_0(v53, Memory, MemorySize);
              *v145 = 24;
              if ( Src )
              {
                v56 = -1;
                do
                  v57 = Src[++v56] == 0;
                while ( !v57 );
                v55 = 2 * v56 + 2;
              }
              else
              {
                v55 = 0;
              }
              v58 = v54 + v46 + v55;
              v59 = v145;
              v60 = Size + 64 + Size_4 + v51 + v58;
              *v145 = v60;
              v61 = (unsigned __int8 *)LocalAlloc(0, v60);
              v62 = v144;
              *v144 = v61;
              if ( !v61 )
              {
                *v59 = 0;
                LastError = 14;
                v28 = WPP_GLOBAL_Control;
                v27 = &WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
                {
                  goto LABEL_269;
                }
                dwFlags = -6;
                goto LABEL_87;
              }
              memset_0(v61, 0, *v59);
              v63 = *v62;
              *(_DWORD *)v63 = 1;
              *(UUID *)(v63 + 4) = Uuid;
              if ( Src )
              {
                v65 = -1;
                do
                  v57 = Src[++v65] == 0;
                while ( !v57 );
                *((_DWORD *)v63 + 6) = 2 * v65 + 2;
                v66 = -1;
                do
                  v57 = Src[++v66] == 0;
                while ( !v57 );
                v64 = 2 * v66 + 2;
              }
              else
              {
                *((_DWORD *)v63 + 6) = 0;
                v64 = 0;
              }
              memcpy_0(v63 + 28, Src, v64);
              if ( Src )
              {
                v68 = -1;
                do
                  v57 = Src[++v68] == 0;
                while ( !v57 );
                v67 = 2 * v68 + 2;
              }
              else
              {
                v67 = 0;
              }
              v69 = v134;
              v70 = (char *)&v63[v67 + 40];
              *(_DWORD *)&v63[v67 + 28] = v127;
              *(_DWORD *)&v63[v67 + 32] = v69;
              v71 = Size_4;
              *(_DWORD *)&v63[v67 + 36] = Size_4;
              v72 = v71;
              memcpy_0(v70, pbBuffer, v71);
              v73 = Size;
              v74 = v140;
              v75 = Size;
              *(_DWORD *)&v70[v72] = Size;
              v76 = &v70[v72 + 4];
              v77 = v73;
              memcpy_0(v76, v74, v75);
              *(_DWORD *)&v76[v77] = v125;
              *(_DWORD *)&v76[v77 + 4] = v130;
              v78 = cbBuffer;
              *(_DWORD *)&v76[v77 + 8] = cbBuffer;
              v79 = &v76[v77 + 12];
              v80 = v78;
              memcpy_0(v79, v156, v78);
              v81 = (ULONG *)&v79[v80];
              if ( a9 )
              {
                if ( *(_DWORD *)a9 != 8 )
                {
                  LastError = 87;
                  v28 = WPP_GLOBAL_Control;
                  v27 = &WPP_GLOBAL_Control;
                  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
                  {
                    goto LABEL_269;
                  }
                  dwFlags = 86;
                  goto LABEL_87;
                }
                v82 = *((_DWORD *)a9 + 1);
                if ( (v82 & 0xFFFFFFE4) != 0 )
                {
                  LastError = 87;
                  v28 = WPP_GLOBAL_Control;
                  v27 = &WPP_GLOBAL_Control;
                  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
                  {
                    goto LABEL_269;
                  }
                  dwFlags = 96;
                  goto LABEL_87;
                }
                if ( (v82 & 8) != 0 && (!v147 || !a12) )
                {
                  LastError = 87;
                  v28 = WPP_GLOBAL_Control;
                  v27 = &WPP_GLOBAL_Control;
                  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
                  {
                    goto LABEL_269;
                  }
                  dwFlags = 105;
                  goto LABEL_87;
                }
                if ( (v82 & 2) != 0 )
                {
                  if ( (a10 & 1) != 0 )
                  {
                    LastError = 1325;
                    v129 = 5;
                    v28 = WPP_GLOBAL_Control;
                    v27 = &WPP_GLOBAL_Control;
                    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                      || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
                    {
                      goto LABEL_269;
                    }
                    dwFlags = 116;
                    goto LABEL_87;
                  }
                  v83 = v128 | 2;
                }
                else
                {
                  v83 = v128;
                }
                v84 = v83 | 1;
                if ( (v82 & 1) == 0 )
                  v84 = v83;
                v85 = v84;
                if ( (v82 & 8) != 0 )
                  v85 = v84 | 8;
                v128 = v85;
              }
              else
              {
                v85 = v128;
              }
              *((_DWORD *)v63 + 5) = v85;
              v86 = MemorySize;
              pcbResult = MemorySize;
              v87 = BCryptEncrypt(hKey, pbOutput, MemorySize, 0, 0, 0, pbOutput, MemorySize + 16, &pcbResult, 1u);
              if ( v87 >= 0 )
              {
                v88 = pcbResult;
                v89 = pbOutput;
                v90 = pcbResult;
                *v81 = pcbResult;
                v91 = v88;
                v92 = (char *)(v81 + 1);
                memcpy_0(v92, v89, v90);
                v93 = (UCHAR *)&v92[v91];
                v87 = BCryptHashData(phHash, *v144, (_DWORD)v93 - *(_DWORD *)v144, 0);
                if ( v87 >= 0 )
                {
                  v94 = (int)StringUuid;
                  v95 = (char *)(v93 + 4);
                  v96 = BCryptFinishHash(phHash, v93 + 4, (ULONG)StringUuid, 0);
                  v97 = v96;
                  if ( v96 >= 0 )
                  {
                    v98 = v144;
                    v99 = v145;
                    *((_DWORD *)v95 - 1) = v94;
                    v57 = v139 == 0;
                    *v99 = v94 + (_DWORD)v95 - *(_DWORD *)v98;
                    if ( !v57 )
                      RemoveMasterKeyCache(0, 0);
                    LastError = 0;
                  }
                  else
                  {
                    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                    {
                      WPP_SF_sDsd(
                        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                        (unsigned int)&WPP_GLOBAL_Control,
                        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
                        (unsigned int)"Status",
                        v96,
                        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
                        196);
                    }
                    LastError = RtlNtStatusToDosError(v97);
                  }
                  goto LABEL_269;
                }
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  WPP_SF_sDsd(
                    *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                    (unsigned int)&WPP_GLOBAL_Control,
                    (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
                    (unsigned int)"Status",
                    v87,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
                    182);
                }
              }
              else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  (unsigned int)&WPP_GLOBAL_Control,
                  (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
                  (unsigned int)"Status",
                  v87,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
                  154);
              }
              LastError = RtlNtStatusToDosError(v87);
              goto LABEL_270;
            }
            WPP_SF_sDsd(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              (_DWORD)v27,
              (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
              (unsigned int)"dwRet",
              13,
              (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
              213);
          }
        }
        else
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_sDsd(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              (unsigned int)&WPP_GLOBAL_Control,
              (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
              (unsigned int)"Status",
              v50,
              (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
              192);
          RevertToSelf();
        }
      }
    }
    v28 = WPP_GLOBAL_Control;
    goto LABEL_185;
  }
  if ( (a10 & 0x9FFFFFF7) != 0 )
  {
    if ( (_UNKNOWN *)v18 == &WPP_GLOBAL_Control || (*(_BYTE *)(v18 + 28) & 1) == 0 )
      goto LABEL_55;
    v20 = 23;
LABEL_54:
    WPP_SF_d(*(_QWORD *)(v18 + 16), v20, WPP_96027a338e1f3ff10006943bca18f271_Traceguids, a10);
LABEL_55:
    LastError = 87;
    goto LABEL_317;
  }
  if ( (unsigned int)IsDomainBackupRequired(v13) )
  {
    LastError = CPSImpersonateClient(v13);
    if ( LastError )
      goto LABEL_317;
    v22 = v13[3];
    v140 = 0;
    v129 = 0;
    if ( !(unsigned int)GetTokenUserSid(v22, &v140) || (v23 = v140, IsZeroRecoveryDone(v140, &v129)) || v129 )
    {
      LastError = InitiateSynchronizeMasterKeys(v13);
    }
    else
    {
      LastError = InitiateForceSynchronizeMasterKeys(v13);
      if ( !LastError )
      {
        LastError = SetZeroRecoveryAsDone(v23);
        CPSRevertToSelf(v13);
        goto LABEL_317;
      }
    }
    CPSRevertToSelf(v13);
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, WPP_96027a338e1f3ff10006943bca18f271_Traceguids);
    LastError = 0;
  }
LABEL_317:
  if ( v141 )
    CPSSetWellKnownAccount(v13, v135);
  return LastError;
}

```

## disassembly

```asm
0x180014c80  push    rbp
0x180014c82  push    rbx
0x180014c83  push    rsi
0x180014c84  push    rdi
0x180014c85  push    r12
0x180014c87  push    r13
0x180014c89  push    r14
0x180014c8b  push    r15
0x180014c8d  lea     rbp, [rsp-158h]
0x180014c95  sub     rsp, 258h
0x180014c9c  mov     rax, cs:__security_cookie
0x180014ca3  xor     rax, rsp
0x180014ca6  mov     [rbp+190h+var_50], rax
0x180014cad  mov     eax, [rbp+190h+arg_20]
0x180014cb3  xor     ebx, ebx
0x180014cb5  mov     r15, [rbp+190h+Src]
0x180014cbc  xorps   xmm0, xmm0
0x180014cbf  mov     [rsp+290h+MemorySize], eax
0x180014cc3  mov     r14, rcx
0x180014cc6  mov     rax, [rbp+190h+arg_30]
0x180014ccd  mov     edi, ebx
0x180014ccf  mov     [rbp+190h+pbInput], rax
0x180014cd3  mov     ecx, ebx
0x180014cd5  mov     rax, [rbp+190h+arg_50]
0x180014cdc  mov     [rbp+190h+var_1B8], rax
0x180014ce0  mov     [rbp+190h+Memory], r9
0x180014ce4  mov     [rbp+190h+var_1C8], r8
0x180014ce8  mov     [rbp+190h+var_1D0], rdx
0x180014cec  mov     [rbp+190h+hKey], rbx
0x180014cf0  mov     [rsp+290h+phHash], rbx
0x180014cf5  mov     [rbp+190h+var_200], ebx
0x180014cf8  mov     [rbp+190h+var_1F0], rbx
0x180014cfc  mov     dword ptr [rsp+290h+Size], ebx
0x180014d00  mov     [rbp+190h+hMem], rbx
0x180014d04  mov     [rbp+190h+cbInput], ebx
0x180014d07  mov     [rbp+190h+var_210], ebx
0x180014d0a  mov     [rbp+190h+var_A0], bx
0x180014d11  movups  xmmword ptr [rbp+190h+pbBuffer], xmm0
0x180014d15  movups  [rbp+190h+var_158], xmm0
0x180014d19  movups  xmmword ptr [rbp+190h+Uuid.Data1], xmm0
0x180014d1d  test    r14, r14
0x180014d20  jz      short loc_180014D37
0x180014d22  cmp     dword ptr [r14], 270h
0x180014d29  jnz     short loc_180014D37
0x180014d2b  mov     ecx, [r14+30h]
0x180014d2f  mov     [rbp+190h+var_210], ecx
0x180014d32  cmp     ecx, 13h
0x180014d35  jz      short loc_180014D50
0x180014d37  mov     [rbp+190h+var_1E8], ebx
0x180014d3a  cmp     ecx, 14h
0x180014d3d  jnz     short loc_180014D7F
0x180014d3f  mov     [rbp+190h+var_210], ecx
0x180014d42  test    r14, r14
0x180014d45  jz      short loc_180014D78
0x180014d47  cmp     dword ptr [r14], 270h
0x180014d4e  jnz     short loc_180014D78
0x180014d50  cmp     dword ptr [r14+30h], 12h
0x180014d55  jz      short loc_180014D78
0x180014d57  mov     rcx, [r14+28h]; hMem
0x180014d5b  test    rcx, rcx
0x180014d5e  jz      short loc_180014D70
0x180014d60  call    cs:__imp_LocalFree
0x180014d67  nop     dword ptr [rax+rax+00h]
0x180014d6c  mov     [r14+28h], rbx
0x180014d70  mov     dword ptr [r14+30h], 12h
0x180014d78  mov     [rbp+190h+var_1E8], 1
0x180014d7f  call    ?UpdateGlobals@@YAKH@Z; UpdateGlobals(int)
0x180014d84  cmp     cs:dword_18004CCB4, ebx
0x180014d8a  jz      short loc_180014DA4
0x180014d8c  lea     rcx, stru_18004C978; CriticalSection
0x180014d93  call    cs:__imp_RtlEnterCriticalSection
0x180014d9a  nop     dword ptr [rax+rax+00h]
0x180014d9f  mov     ebx, 1
0x180014da4  mov     eax, cs:dword_18004C548
0x180014daa  mov     esi, 6603h
0x180014daf  mov     [rsp+290h+var_230], esi
0x180014db3  cmp     eax, esi
0x180014db5  jz      short loc_180014DD2
0x180014db7  mov     ecx, cs:dword_18004C550
0x180014dbd  cmp     eax, 0FFFFFFFFh
0x180014dc0  jnz     loc_180014FFB
0x180014dc6  cmp     ecx, 8004h
0x180014dcc  jnz     loc_180015007
0x180014dd2  mov     r13d, 8004h
0x180014dd8  mov     [rsp+290h+var_23C], r13d
0x180014ddd  mov     [rsp+290h+var_214], 0FFFFFFFFh
0x180014de5  mov     [rsp+290h+var_224], 0FFFFFFFFh
0x180014ded  test    ebx, ebx
0x180014def  jz      short loc_180014E04
0x180014df1  lea     rcx, stru_18004C978; CriticalSection
0x180014df8  call    cs:__imp_RtlLeaveCriticalSection
0x180014dff  nop     dword ptr [rax+rax+00h]
0x180014e04  mov     ebx, [rbp+190h+arg_48]
0x180014e0a  mov     [r14+34h], esi
0x180014e0e  mov     [r14+38h], r13d
0x180014e12  test    bl, 4
0x180014e15  jz      short loc_180014E2D
0x180014e17  cmp     dword ptr [r14], 270h
0x180014e1e  jnz     short loc_180014E28
0x180014e20  mov     dword ptr [r14+10h], 1
0x180014e28  mov     edi, 4
0x180014e2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e34  lea     r12, WPP_GLOBAL_Control
0x180014e3b  test    byte ptr [rcx+1Ch], 4
0x180014e3f  jz      loc_180014FA1
0x180014e45  cmp     rcx, r12
0x180014e48  jz      loc_180014FA1
0x180014e4e  mov     rcx, [rcx+10h]
0x180014e52  mov     edx, 0Ah
0x180014e57  mov     r9, r14
0x180014e5a  call    WPP_SF_q
0x180014e5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e66  cmp     rcx, r12
0x180014e69  jz      loc_180014FA1
0x180014e6f  test    byte ptr [rcx+1Ch], 4
0x180014e73  jz      short loc_180014E8E
0x180014e75  mov     r9, [r14+8]
0x180014e79  mov     edx, 0Bh
0x180014e7e  mov     rcx, [rcx+10h]
0x180014e82  call    WPP_SF_q
0x180014e87  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e8e  cmp     rcx, r12
0x180014e91  jz      loc_180014FA1
0x180014e97  test    byte ptr [rcx+1Ch], 4
0x180014e9b  jz      short loc_180014EBD
0x180014e9d  mov     r9d, [r14+10h]
0x180014ea1  lea     r8, WPP_96027a338e1f3ff10006943bca18f271_Traceguids
0x180014ea8  mov     rcx, [rcx+10h]
0x180014eac  mov     edx, 0Ch
0x180014eb1  call    WPP_SF_d
0x180014eb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ebd  cmp     rcx, r12
0x180014ec0  jz      loc_180014FA1
0x180014ec6  test    byte ptr [rcx+1Ch], 4
0x180014eca  jz      short loc_180014EEC
0x180014ecc  mov     r9d, [r14+14h]
0x180014ed0  lea     r8, WPP_96027a338e1f3ff10006943bca18f271_Traceguids
0x180014ed7  mov     rcx, [rcx+10h]
0x180014edb  mov     edx, 0Dh
0x180014ee0  call    WPP_SF_d
0x180014ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x180014eec  cmp     rcx, r12
0x180014eef  jz      loc_180014FA1
0x180014ef5  test    byte ptr [rcx+1Ch], 4
0x180014ef9  jz      short loc_180014F14
0x180014efb  mov     r9, [r14+18h]
0x180014eff  mov     edx, 0Eh
0x180014f04  mov     rcx, [rcx+10h]
0x180014f08  call    WPP_SF_q
0x180014f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f14  cmp     rcx, r12
0x180014f17  jz      loc_180014FA1
0x180014f1d  test    byte ptr [rcx+1Ch], 4
0x180014f21  jz      short loc_180014F43
0x180014f23  mov     rcx, [rcx+10h]
0x180014f27  lea     r9, [r14+50h]
0x180014f2b  mov     edx, 0Fh
0x180014f30  lea     r8, WPP_96027a338e1f3ff10006943bca18f271_Traceguids
0x180014f37  call    WPP_SF_S
0x180014f3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f43  cmp     rcx, r12
0x180014f46  jz      short loc_180014FA1
0x180014f48  test    byte ptr [rcx+1Ch], 4
0x180014f4c  jz      short loc_180014F76
0x180014f4e  mov     eax, [r14+40h]
0x180014f52  lea     r8, WPP_96027a338e1f3ff10006943bca18f271_Traceguids
0x180014f59  mov     r9d, [r14+3Ch]
0x180014f5d  mov     edx, 10h
0x180014f62  mov     rcx, [rcx+10h]
0x180014f66  mov     dword ptr [rsp+290h+pbSecret], eax
0x180014f6a  call    WPP_SF_dd
0x180014f6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f76  cmp     rcx, r12
0x180014f79  jz      short loc_180014FA1
0x180014f7b  test    byte ptr [rcx+1Ch], 4
0x180014f7f  jz      short loc_180014FA1
0x180014f81  mov     r9d, [r14+30h]
0x180014f85  lea     r8, WPP_96027a338e1f3ff10006943bca18f271_Traceguids
0x180014f8c  mov     rcx, [rcx+10h]
0x180014f90  mov     edx, 11h
0x180014f95  call    WPP_SF_d
0x180014f9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fa1  mov     eax, ebx
0x180014fa3  and     eax, 4000000h
0x180014fa8  mov     [rbp+190h+var_1F8], eax
0x180014fab  jz      short loc_180014FBD
0x180014fad  xor     edx, edx; unsigned __int16 *
0x180014faf  xor     ecx, ecx; struct _LUID *
0x180014fb1  call    ?RemoveMasterKeyCache@@YAHPEAU_LUID@@PEBG@Z; RemoveMasterKeyCache(_LUID *,ushort const *)
0x180014fb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fbd  test    bl, 8
0x180014fc0  jz      loc_1800150F2
0x180014fc6  test    ebx, 9FFFFFF7h
0x180014fcc  jz      short loc_180015034
0x180014fce  cmp     rcx, r12
0x180014fd1  jz      short loc_180014FF1
0x180014fd3  test    byte ptr [rcx+1Ch], 1
0x180014fd7  jz      short loc_180014FF1
0x180014fd9  mov     edx, 17h
0x180014fde  mov     rcx, [rcx+10h]
0x180014fe2  lea     r8, WPP_96027a338e1f3ff10006943bca18f271_Traceguids
0x180014fe9  mov     r9d, ebx
0x180014fec  call    WPP_SF_d
0x180014ff1  mov     ebx, 57h ; 'W'
0x180014ff6  jmp     loc_180016325
0x180014ffb  cmp     eax, 6610h
0x180015000  jz      short loc_180015020
0x180015002  cmp     eax, 0FFFFFFFFh
0x180015005  jnz     short loc_18001500F
0x180015007  cmp     ecx, 800Eh
0x18001500d  jz      short loc_180015020
0x18001500f  mov     esi, 6801h
0x180015014  mov     [rsp+290h+var_230], esi
0x180015018  cmp     eax, esi
0x18001501a  jz      loc_180014DD2
0x180015020  mov     esi, 6610h
0x180015025  mov     r13d, 800Eh
0x18001502b  mov     [rsp+290h+var_230], esi
0x18001502f  jmp     loc_180014DD8
0x180015034  mov     rcx, r14; void *
0x180015037  call    ?IsDomainBackupRequired@@YAHPEAX@Z; IsDomainBackupRequired(void *)
0x18001503c  test    eax, eax
0x18001503e  jnz     short loc_18001506E
0x180015040  mov     rcx, cs:WPP_GLOBAL_Control
0x180015047  cmp     rcx, r12
0x18001504a  jz      short loc_180015067
0x18001504c  test    byte ptr [rcx+1Ch], 8
0x180015050  jz      short loc_180015067
0x180015052  mov     rcx, [rcx+10h]
0x180015056  lea     r8, WPP_96027a338e1f3ff10006943bca18f271_Traceguids
0x18001505d  mov     edx, 18h
0x180015062  call    WPP_SF_
0x180015067  xor     ebx, ebx
0x180015069  jmp     loc_180016325
0x18001506e  mov     rcx, r14; void *
0x180015071  call    ?CPSImpersonateClient@@YAKPEAX@Z; CPSImpersonateClient(void *)
0x180015076  mov     ebx, eax
0x180015078  test    eax, eax
0x18001507a  jnz     loc_180016325
0x180015080  mov     rcx, [r14+18h]
0x180015084  lea     rdx, [rbp+190h+var_1F0]
0x180015088  xor     eax, eax
0x18001508a  mov     [rbp+190h+var_1F0], rax
0x18001508e  mov     [rsp+290h+var_228], eax
0x180015092  call    GetTokenUserSid
0x180015097  test    eax, eax
0x180015099  jz      short loc_1800150DB
0x18001509b  mov     rdi, [rbp+190h+var_1F0]
0x18001509f  lea     rdx, [rsp+290h+var_228]; int *
0x1800150a4  mov     rcx, rdi; void *
0x1800150a7  call    ?IsZeroRecoveryDone@@YAKPEAXAEAH@Z; IsZeroRecoveryDone(void *,int &)
0x1800150ac  test    eax, eax
0x1800150ae  jnz     short loc_1800150DB
0x1800150b0  cmp     [rsp+290h+var_228], eax
0x1800150b4  jnz     short loc_1800150DB
0x1800150b6  mov     rcx, r14; void *
0x1800150b9  call    ?InitiateForceSynchronizeMasterKeys@@YAKPEAX@Z; InitiateForceSynchronizeMasterKeys(void *)
0x1800150be  mov     ebx, eax
0x1800150c0  test    eax, eax
0x1800150c2  jnz     short loc_1800150E5
0x1800150c4  mov     rcx, rdi; void *
0x1800150c7  call    ?SetZeroRecoveryAsDone@@YAKPEAX@Z; SetZeroRecoveryAsDone(void *)
0x1800150cc  mov     rcx, r14; void *
0x1800150cf  mov     ebx, eax
0x1800150d1  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x1800150d6  jmp     loc_180016325
0x1800150db  mov     rcx, r14; void *
0x1800150de  call    ?InitiateSynchronizeMasterKeys@@YAKPEAX@Z; InitiateSynchronizeMasterKeys(void *)
0x1800150e3  mov     ebx, eax
0x1800150e5  mov     rcx, r14; void *
0x1800150e8  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x1800150ed  jmp     loc_180016325
0x1800150f2  test    bl, bl
0x1800150f4  jns     loc_18001517F
0x1800150fa  test    ebx, 9FFFFF7Fh
0x180015100  jz      short loc_18001511F
0x180015102  cmp     rcx, r12
0x180015105  jz      loc_180014FF1
0x18001510b  test    byte ptr [rcx+1Ch], 1
0x18001510f  jz      loc_180014FF1
0x180015115  mov     edx, 19h
0x18001511a  jmp     loc_180014FDE
0x18001511f  mov     rcx, r14; void *
0x180015122  call    ?DpapiUpdateLsaSecret@@YAKPEAX@Z; DpapiUpdateLsaSecret(void *)
0x180015127  mov     ebx, eax
0x180015129  test    eax, eax
0x18001512b  jz      loc_180016325
0x180015131  mov     rcx, cs:WPP_GLOBAL_Control
0x180015138  cmp     rcx, r12
0x18001513b  jz      loc_180016325
0x180015141  test    byte ptr [rcx+1Ch], 1
0x180015145  jz      loc_180016325
0x18001514b  mov     rcx, [rcx+10h]
0x18001514f  lea     rsi, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180015156  mov     [rsp+290h+dwFlags], 180h
0x18001515e  lea     r9, aDwret; "dwRet"
0x180015165  mov     qword ptr [rsp+290h+cbSecret], rsi
0x18001516a  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180015171  mov     dword ptr [rsp+290h+pbSecret], eax
0x180015175  call    WPP_SF_sDsd
  ... truncated ...
```
