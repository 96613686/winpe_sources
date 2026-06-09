# SPCryptUnprotect(void *,uchar * *,ulong *,uchar *,ulong,ushort * *,uchar *,ulong,_SSCRYPTPROTECTDATA_PROMPTSTRUCT *,ulong,uchar *,ulong)

- ea: `0x180016370`
- end: `0x1800180c6`
- name: `?SPCryptUnprotect@@YAKPEAXPEAPEAEPEAKPEAEKPEAPEAG3KPEAU_SSCRYPTPROTECTDATA_PROMPTSTRUCT@@K3K@Z`
- size: `7510`
- prototype: `__int64 __fastcall(_DWORD *, unsigned __int8 **, UUID *, unsigned __int8 *, unsigned int, unsigned __int16 **, unsigned __int8 *, ULONG cbInput, struct _SSCRYPTPROTECTDATA_PROMPTSTRUCT *, signed int, unsigned __int8 *, ULONG)`
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ce90`
- `0x18000d540`

## callees

- `0x1800010ac`
- `0x1800029d0`
- `0x180002f18`
- `0x180008000`
- `0x1800083b0`
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
- `0x180016370`
- `0x1800193c0`
- `0x18001c340`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001e1b4`
- `0x18001eb8c`
- `0x180027f14`
- `0x18002a4dc`
- `0x18003c62c`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180017a23`
- `RPCRT4!RpcImpersonateClient` at `0x180017a23`
- `RPCRT4!UuidToStringW` at `0x18001672f`
- `RPCRT4!UuidToStringW` at `0x18001672f`
- `RPCRT4!RpcStringFreeW` at `0x18001676f`
- `RPCRT4!RpcStringFreeW` at `0x18001676f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017ab2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017ab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016dfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016dfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017458`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016f7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017b0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018051`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018094`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016f7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017a7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017b0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018051`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018094`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016b5c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017987`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017b3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017bb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016b5c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017987`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017b3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017bb7`
- `bcrypt!BCryptDecrypt` at `0x1800178ce`
- `bcrypt!BCryptDecrypt` at `0x1800178ce`
- `bcrypt!BCryptFinishHash` at `0x1800177be`
- `bcrypt!BCryptFinishHash` at `0x1800177be`
- `bcrypt!BCryptDestroyHash` at `0x180017402`
- `bcrypt!BCryptDestroyHash` at `0x18001807c`
- `bcrypt!BCryptDestroyHash` at `0x180017402`
- `bcrypt!BCryptDestroyHash` at `0x18001807c`
- `bcrypt!BCryptHashData` at `0x180017288`
- `bcrypt!BCryptHashData` at `0x1800172d4`
- `bcrypt!BCryptHashData` at `0x18001734e`
- `bcrypt!BCryptHashData` at `0x180017513`
- `bcrypt!BCryptHashData` at `0x18001756a`
- `bcrypt!BCryptHashData` at `0x1800175bf`
- `bcrypt!BCryptHashData` at `0x18001770e`
- `bcrypt!BCryptHashData` at `0x180017288`
- `bcrypt!BCryptHashData` at `0x1800172d4`
- `bcrypt!BCryptHashData` at `0x18001734e`
- `bcrypt!BCryptHashData` at `0x180017513`
- `bcrypt!BCryptHashData` at `0x18001756a`
- `bcrypt!BCryptHashData` at `0x1800175bf`
- `bcrypt!BCryptHashData` at `0x18001770e`
- `bcrypt!BCryptDestroyKey` at `0x180018066`
- `bcrypt!BCryptDestroyKey` at `0x180018066`
- `bcrypt!BCryptCreateHash` at `0x180017213`
- `bcrypt!BCryptCreateHash` at `0x1800174c1`
- `bcrypt!BCryptCreateHash` at `0x180017213`
- `bcrypt!BCryptCreateHash` at `0x1800174c1`
- `CRYPTBASE!SystemFunction040` at `0x180017aa4`
- `CRYPTBASE!SystemFunction040` at `0x180017aa4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180016743`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180016743`
- `ntdll!RtlEnterCriticalSection` at `0x180016466`
- `ntdll!RtlEnterCriticalSection` at `0x180016466`
- `ntdll!RtlNtStatusToDosError` at `0x180017261`
- `ntdll!RtlNtStatusToDosError` at `0x180017b22`
- `ntdll!RtlNtStatusToDosError` at `0x180017261`
- `ntdll!RtlNtStatusToDosError` at `0x180017b22`
- `ntdll!RtlLeaveCriticalSection` at `0x1800164d1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800164d1`

## string_xrefs

- `0x180016662`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`
- `0x1800166f4`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`
- `0x180016873`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`
- `0x1800168ad`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`
- `0x1800168f9`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`
- `0x180016958`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`
- `0x180016a47`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`
- `0x180016fc6`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`
- `0x180017d42`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`
- `0x180017d63`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32p.cpp`

## pseudocode

```c
__int64 __fastcall SPCryptUnprotect(
        _DWORD *a1,
        unsigned __int8 **a2,
        UUID *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int16 **a6,
        unsigned __int8 *a7,
        ULONG cbInput,
        struct _SSCRYPTPROTECTDATA_PROMPTSTRUCT *a9,
        signed int a10,
        unsigned __int8 *a11,
        ULONG a12)
{
  unsigned int *v13; // r13
  const unsigned __int16 *v14; // r15
  unsigned int v15; // r12d
  int v16; // ebx
  int v17; // edx
  __int64 v18; // r8
  int v19; // esi
  unsigned int v20; // r14d
  __int64 v21; // rcx
  __int64 v22; // r8
  signed int v23; // esi
  DWORD SpecifiedMasterKey; // edi
  UUID v25; // xmm0
  size_t v26; // rdx
  unsigned int v27; // eax
  __int64 v28; // rsi
  unsigned int v29; // eax
  unsigned __int8 *v30; // rbx
  unsigned int v31; // eax
  size_t v32; // rdi
  unsigned __int8 *v33; // rbx
  unsigned __int8 *v34; // rax
  size_t v35; // rcx
  unsigned __int8 *v36; // rax
  unsigned int *v37; // rbx
  unsigned int v38; // ecx
  unsigned int v39; // eax
  __int64 v40; // r12
  unsigned __int64 v41; // rdi
  size_t v42; // rcx
  unsigned int v43; // edi
  size_t v44; // rsi
  HLOCAL v45; // rax
  char *v46; // rbx
  void *v47; // rdx
  unsigned int v48; // eax
  unsigned int v49; // r15d
  __int64 v50; // rcx
  size_t v51; // r13
  DWORD LastError; // eax
  void *v53; // rsi
  BCRYPT_ALG_HANDLE v54; // rbx
  unsigned int v55; // r15d
  __int64 v56; // rsi
  int v57; // ebx
  void *v58; // rcx
  __int64 v59; // rcx
  unsigned int v60; // edx
  unsigned int v61; // r9d
  DWORD v62; // eax
  int v63; // edx
  int v64; // ebx
  int v65; // edx
  UCHAR *v66; // r12
  NTSTATUS v67; // eax
  int v68; // edx
  UCHAR *v69; // rbx
  NTSTATUS v70; // eax
  int v71; // edx
  unsigned int v72; // eax
  unsigned int v73; // edx
  DWORD v74; // eax
  NTSTATUS v75; // eax
  NTSTATUS v76; // eax
  int v77; // eax
  __int64 cbOutput; // rbx
  UCHAR *v79; // rsi
  unsigned int v80; // ecx
  NTSTATUS v81; // eax
  ULONG v82; // edi
  NTSTATUS v83; // eax
  unsigned __int64 v84; // r9
  int v85; // r10d
  UCHAR *v86; // rdx
  UCHAR *i; // r8
  int v88; // ecx
  int v89; // ecx
  unsigned __int8 v90; // r11
  char v91; // cl
  char v92; // al
  NTSTATUS v93; // eax
  ULONG v94; // eax
  const WCHAR *v95; // rdx
  ULONG *p_Data1; // r15
  unsigned int v97; // edi
  int v98; // eax
  unsigned __int8 *v99; // rax
  HLOCAL *v100; // r12
  RPC_STATUS v101; // eax
  int v102; // ebx
  unsigned __int8 *v103; // rax
  void **v104; // rsi
  size_t v105; // rdi
  HLOCAL v106; // rax
  __int64 v107; // rbx
  __int64 v108; // rax
  unsigned int v109; // ebx
  int v110; // edx
  __int64 v111; // rcx
  int v112; // r8d
  int v113; // r9d
  const WCHAR *v114; // rax
  unsigned int v115; // eax
  int v116; // eax
  __int64 v117; // rcx
  unsigned int v118; // r9d
  unsigned int v119; // r8d
  __int64 v120; // rax
  __int64 v121; // rcx
  unsigned int v122; // edx
  UCHAR *v123; // rax
  __int64 v124; // rcx
  UCHAR *v125; // rax
  __int64 v126; // rcx
  _BYTE *v127; // rcx
  __int64 v128; // rax
  PUCHAR pbSecret; // [rsp+20h] [rbp-E0h]
  char dwFlags; // [rsp+30h] [rbp-D0h]
  ULONG dwFlagsa[2]; // [rsp+30h] [rbp-D0h]
  ULONG pcbResult; // [rsp+60h] [rbp-A0h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v136; // [rsp+70h] [rbp-90h]
  unsigned int v137; // [rsp+74h] [rbp-8Ch]
  unsigned int v138; // [rsp+78h] [rbp-88h]
  ULONG v139; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v140; // [rsp+80h] [rbp-80h]
  unsigned int v141; // [rsp+84h] [rbp-7Ch]
  unsigned int v142; // [rsp+88h] [rbp-78h]
  unsigned int v143; // [rsp+8Ch] [rbp-74h]
  unsigned int v144; // [rsp+90h] [rbp-70h] BYREF
  RPC_WSTR StringUuid; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v146; // [rsp+A0h] [rbp-60h] BYREF
  void *Src; // [rsp+A8h] [rbp-58h]
  HLOCAL hMem; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v149; // [rsp+B8h] [rbp-48h]
  BCRYPT_KEY_HANDLE hKey; // [rsp+C0h] [rbp-40h] BYREF
  HLOCAL v151; // [rsp+C8h] [rbp-38h]
  UUID *p_Uuid; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 **v153; // [rsp+D8h] [rbp-28h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+E0h] [rbp-20h]
  PUCHAR v155; // [rsp+E8h] [rbp-18h]
  unsigned __int8 **v156; // [rsp+F0h] [rbp-10h]
  size_t Size; // [rsp+F8h] [rbp-8h]
  size_t v158; // [rsp+100h] [rbp+0h]
  void *BCryptProviderHandle; // [rsp+108h] [rbp+8h]
  _DWORD v160[4]; // [rsp+110h] [rbp+10h]
  char *v161; // [rsp+120h] [rbp+20h]
  PUCHAR v162; // [rsp+128h] [rbp+28h]
  PUCHAR v163; // [rsp+130h] [rbp+30h]
  BCRYPT_HANDLE hObject; // [rsp+138h] [rbp+38h]
  UUID Uuid; // [rsp+140h] [rbp+40h] BYREF
  UCHAR v166[16]; // [rsp+150h] [rbp+50h] BYREF
  int v167; // [rsp+160h] [rbp+60h]
  UCHAR pbInput[32]; // [rsp+168h] [rbp+68h] BYREF
  UCHAR v169[40]; // [rsp+188h] [rbp+88h] BYREF
  unsigned __int16 v170[40]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v171[64]; // [rsp+200h] [rbp+100h] BYREF
  UCHAR pbOutput[64]; // [rsp+280h] [rbp+180h] BYREF

  v153 = a6;
  v13 = a1;
  v162 = a4;
  v163 = a7;
  v14 = 0;
  *a2 = 0;
  v15 = 0;
  v167 = 0;
  v16 = 0;
  p_Uuid = a3;
  v156 = a2;
  v155 = a11;
  hKey = 0;
  phHash = 0;
  hMem = 0;
  v139 = 0;
  pcbResult = 0;
  v160[0] = 18;
  v160[1] = 19;
  v160[2] = 20;
  a3->Data1 = 0;
  Uuid = 0;
  v138 = 0;
  *(_OWORD *)v166 = 0;
  v137 = 0;
  v151 = 0;
  v136 = 0;
  Src = 0;
  v142 = 0;
  v143 = 0;
  v170[0] = 0;
  UpdateGlobals((int)a11);
  if ( dword_18004CCB4 )
  {
    RtlEnterCriticalSection(&stru_18004C978);
    v16 = 1;
  }
  v19 = 26115;
  v140 = 26115;
  if ( dword_18004C548 == 26115 )
    goto LABEL_6;
  v20 = 32782;
  v141 = 32782;
  if ( dword_18004C548 != -1 )
  {
    if ( dword_18004C548 != 26128 )
      goto LABEL_40;
LABEL_42:
    v19 = 26128;
    v140 = 26128;
    goto LABEL_7;
  }
  if ( dword_18004C550 == 32772 )
  {
LABEL_6:
    v20 = 32772;
LABEL_7:
    v141 = v20;
    goto LABEL_8;
  }
  if ( dword_18004C550 == 32782 )
    goto LABEL_42;
LABEL_40:
  v19 = 26625;
  v140 = 26625;
  if ( dword_18004C548 == 26625 )
    goto LABEL_6;
  v19 = 26128;
  v140 = 26128;
LABEL_8:
  v149 = -1;
  v144 = -1;
  if ( v16 )
    RtlLeaveCriticalSection(&stru_18004C978);
  v13[13] = v19;
  v13[14] = v20;
  v21 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    WPP_SF_q(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 27, v18, v13);
    v21 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        WPP_SF_q(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 28, v22, *((_QWORD *)v13 + 1));
        v21 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v21 != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(v21 + 28) & 4) != 0 )
        {
          WPP_SF_d(*(_QWORD *)(v21 + 16), 29, WPP_96027a338e1f3ff10006943bca18f271_Traceguids, v13[5]);
          v21 = WPP_GLOBAL_Control;
        }
        if ( (_UNKNOWN *)v21 != &WPP_GLOBAL_Control )
        {
          if ( (*(_BYTE *)(v21 + 28) & 4) != 0 )
          {
            WPP_SF_q(*(_QWORD *)(v21 + 16), 30, v22, *((_QWORD *)v13 + 3));
            v21 = WPP_GLOBAL_Control;
          }
          if ( (_UNKNOWN *)v21 != &WPP_GLOBAL_Control )
          {
            if ( (*(_BYTE *)(v21 + 28) & 4) != 0 )
            {
              WPP_SF_S(*(_QWORD *)(v21 + 16), 31, WPP_96027a338e1f3ff10006943bca18f271_Traceguids, v13 + 20);
              v21 = WPP_GLOBAL_Control;
            }
            if ( (_UNKNOWN *)v21 != &WPP_GLOBAL_Control )
            {
              if ( (*(_BYTE *)(v21 + 28) & 4) != 0 )
              {
                WPP_SF_dd(*(_QWORD *)(v21 + 16), 32, WPP_96027a338e1f3ff10006943bca18f271_Traceguids, v13[15], v13[16]);
                v21 = WPP_GLOBAL_Control;
              }
              if ( (_UNKNOWN *)v21 != &WPP_GLOBAL_Control && (*(_BYTE *)(v21 + 28) & 4) != 0 )
              {
                WPP_SF_d(*(_QWORD *)(v21 + 16), 33, WPP_96027a338e1f3ff10006943bca18f271_Traceguids, v13[12]);
                v21 = WPP_GLOBAL_Control;
              }
            }
          }
        }
      }
    }
  }
  v23 = a10;
  v146 = a10 & 0x4000000;
  if ( (a10 & 0x4000000) != 0 )
  {
    RemoveMasterKeyCache(0, 0);
    v21 = WPP_GLOBAL_Control;
  }
  if ( a5 < 0x1C )
  {
    SpecifiedMasterKey = 13;
    if ( (_UNKNOWN *)v21 != &WPP_GLOBAL_Control && (*(_BYTE *)(v21 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v21 + 16),
        v17,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        229);
    goto LABEL_356;
  }
  if ( *(_DWORD *)a4 != 1 )
  {
    SpecifiedMasterKey = 13;
    v15 = 1;
    if ( (_UNKNOWN *)v21 != &WPP_GLOBAL_Control && (*(_BYTE *)(v21 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v21 + 16),
        v17,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        238);
    goto LABEL_356;
  }
  v25 = *(UUID *)(a4 + 4);
  StringUuid = 0;
  Uuid = v25;
  if ( !UuidToStringW(&Uuid, &StringUuid) )
  {
    v27 = lstrlenW(StringUuid);
    if ( v27 < 0x28 )
      memcpy_0(v170, StringUuid, 2LL * (v27 + 1));
    RpcStringFreeW(&StringUuid);
  }
  v28 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 38, WPP_96027a338e1f3ff10006943bca18f271_Traceguids, v170);
    v28 = WPP_GLOBAL_Control;
  }
  v29 = *((_DWORD *)a4 + 5);
  v30 = a4 + 24;
  v136 = v29;
  if ( (_UNKNOWN *)v28 != &WPP_GLOBAL_Control && (*(_BYTE *)(v28 + 28) & 8) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(v28 + 16), 39, WPP_96027a338e1f3ff10006943bca18f271_Traceguids, v29);
    LOBYTE(v29) = v136;
    v28 = WPP_GLOBAL_Control;
  }
  if ( (v29 & 4) != 0 && *v13 == 624 )
  {
    v13[4] = 1;
    v28 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v28 != &WPP_GLOBAL_Control && (*(_BYTE *)(v28 + 28) & 4) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(v28 + 16), 40, WPP_96027a338e1f3ff10006943bca18f271_Traceguids, v13[4]);
    v28 = WPP_GLOBAL_Control;
  }
  v31 = a10 & 0x20000000;
  if ( (v136 & 0x20000000) != 0 )
  {
    if ( !v31 )
    {
      SpecifiedMasterKey = 13;
      v15 = 4;
      if ( (_UNKNOWN *)v28 != &WPP_GLOBAL_Control && (*(_BYTE *)(v28 + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(v28 + 16),
          v26,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          29);
LABEL_355:
      v23 = a10;
LABEL_356:
      v94 = pcbResult;
      goto LABEL_357;
    }
  }
  else if ( v31 && a10 >= 0 )
  {
    SpecifiedMasterKey = 13;
    v15 = 4;
    if ( (_UNKNOWN *)v28 != &WPP_GLOBAL_Control && (*(_BYTE *)(v28 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v28 + 16),
        v26,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        42);
    goto LABEL_355;
  }
  v32 = *(unsigned int *)v30;
  v33 = v30 + 4;
  if ( (int)v32 + 12 < (unsigned int)v32 )
  {
    SpecifiedMasterKey = 13;
    if ( (_UNKNOWN *)v28 != &WPP_GLOBAL_Control && (*(_BYTE *)(v28 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v28 + 16),
        v26,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        60);
    goto LABEL_355;
  }
  if ( a5 - 28 < (int)v32 + 12 )
  {
    SpecifiedMasterKey = 13;
    v15 = 3;
    if ( (_UNKNOWN *)v28 != &WPP_GLOBAL_Control && (*(_BYTE *)(v28 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v28 + 16),
        v26,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        68);
    v14 = (const unsigned __int16 *)Src;
    goto LABEL_355;
  }
  if ( (_DWORD)v32 )
  {
    if ( (v32 & 1) != 0 )
    {
      SpecifiedMasterKey = 13;
      if ( (_UNKNOWN *)v28 != &WPP_GLOBAL_Control && (*(_BYTE *)(v28 + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(v28 + 16),
          v26,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          82);
      v14 = 0;
      goto LABEL_355;
    }
    if ( !v33 )
      goto LABEL_349;
    v26 = v32;
    v35 = v32 >> 1;
    v36 = v33;
    for ( Size = v32; v35; --v35 )
    {
      if ( !*(_WORD *)v36 )
        break;
      v36 += 2;
    }
    if ( !v35 )
    {
LABEL_349:
      v14 = 0;
      SpecifiedMasterKey = 13;
      if ( (_UNKNOWN *)v28 != &WPP_GLOBAL_Control && (*(_BYTE *)(v28 + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(v28 + 16),
          v26,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          92);
      goto LABEL_355;
    }
    v34 = v33;
  }
  else
  {
    v34 = 0;
    v26 = 0;
    Size = 0;
  }
  Src = v34;
  v37 = (unsigned int *)&v33[v26];
  if ( (_UNKNOWN *)v28 != &WPP_GLOBAL_Control && (*(_BYTE *)(v28 + 28) & 8) != 0 )
  {
    WPP_SF_S(*(_QWORD *)(v28 + 16), 41, WPP_96027a338e1f3ff10006943bca18f271_Traceguids, v34);
    v28 = WPP_GLOBAL_Control;
  }
  v38 = *v37;
  v39 = v37[1];
  v142 = *v37;
  v138 = v39;
  if ( (_UNKNOWN *)v28 != &WPP_GLOBAL_Control && (*(_BYTE *)(v28 + 28) & 8) != 0 )
  {
    WPP_SF_Dd(*(_QWORD *)(v28 + 16), 42, &WPP_GLOBAL_Control, v38, v39);
    v28 = WPP_GLOBAL_Control;
  }
  v40 = v37[2];
  if ( (unsigned int)v40 > 0x20 )
  {
    SpecifiedMasterKey = 13;
    if ( (_UNKNOWN *)v28 != &WPP_GLOBAL_Control && (*(_BYTE *)(v28 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v28 + 16),
        v26,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        118);
    goto LABEL_102;
  }
  v41 = a5 - 28 - (unsigned int)v32 - 12;
  if ( v41 < v40 + 4 )
  {
    SpecifiedMasterKey = 13;
    v15 = 3;
    if ( (_UNKNOWN *)v28 != &WPP_GLOBAL_Control && (*(_BYTE *)(v28 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v28 + 16),
        v26,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        128);
    goto LABEL_295;
  }
  memcpy_0(pbInput, v37 + 3, v37[2]);
  v42 = *(unsigned int *)((char *)v37 + v40 + 12);
  v158 = v42;
  if ( (int)v42 + 12 < (unsigned int)v42 )
  {
    SpecifiedMasterKey = 13;
    if ( (_UNKNOWN *)v28 != &WPP_GLOBAL_Control && (*(_BYTE *)(v28 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v28 + 16),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        150);
    goto LABEL_102;
  }
  v43 = v41 - v40 - 4;
  if ( v43 < (int)v42 + 12 )
  {
    SpecifiedMasterKey = 13;
    v15 = 3;
    if ( (_UNKNOWN *)v28 != &WPP_GLOBAL_Control && (*(_BYTE *)(v28 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v28 + 16),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        157);
    goto LABEL_295;
  }
  v44 = v42;
  v45 = LocalAlloc(0, v42);
  v151 = v45;
  if ( !v45 )
  {
    SpecifiedMasterKey = 14;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
    {
LABEL_102:
      v15 = 0;
LABEL_295:
      v23 = a10;
      goto LABEL_296;
    }
    WPP_SF_sDsd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      (unsigned int)&WPP_GLOBAL_Control,
      (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
      (unsigned int)"dwRet",
      14,
      (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
      166);
LABEL_117:
    v15 = 0;
    goto LABEL_295;
  }
  v46 = (char *)v37 + v40 + 16;
  memcpy_0(v45, v46, v44);
  v48 = *(_DWORD *)&v46[v44 + 4];
  v49 = *(_DWORD *)&v46[v44];
  v137 = v48;
  v143 = v49;
  v50 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    WPP_SF_Dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 43, &WPP_GLOBAL_Control, v49, v48);
    v50 = WPP_GLOBAL_Control;
  }
  v51 = *(unsigned int *)&v46[v44 + 8];
  if ( (unsigned int)v51 > 0x20 )
  {
    SpecifiedMasterKey = 13;
    if ( (_UNKNOWN *)v50 == &WPP_GLOBAL_Control || (*(_BYTE *)(v50 + 28) & 1) == 0 )
      goto LABEL_126;
    dwFlags = -64;
LABEL_125:
    WPP_SF_sDsd(
      *(_QWORD *)(v50 + 16),
      (_DWORD)v47,
      (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
      (unsigned int)"dwRet",
      SpecifiedMasterKey,
      (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
      dwFlags);
LABEL_126:
    v15 = 0;
LABEL_294:
    v13 = a1;
    goto LABEL_295;
  }
  LODWORD(StringUuid) = v43 - v158 - 12;
  if ( (unsigned int)StringUuid < (unsigned int)v51 )
  {
    SpecifiedMasterKey = 13;
    v15 = 3;
    if ( (_UNKNOWN *)v50 != &WPP_GLOBAL_Control && (*(_BYTE *)(v50 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v50 + 16),
        (_DWORD)v47,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        201);
    goto LABEL_294;
  }
  memcpy_0(v169, &v46[v44 + 12], v51);
  v161 = &v46[v44 + 12 + v51];
  hObject = (BCRYPT_HANDLE)GetBCryptProviderHandle(v142);
  if ( !hObject )
  {
    LastError = GetLastError();
    SpecifiedMasterKey = LastError;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        217);
    v15 = 0;
    v13 = a1;
    v23 = a10;
    if ( SpecifiedMasterKey == 50 )
      SpecifiedMasterKey = 13;
    goto LABEL_296;
  }
  BCryptProviderHandle = (void *)GetBCryptProviderHandle(v49);
  v53 = BCryptProviderHandle;
  if ( !BCryptProviderHandle )
  {
    SpecifiedMasterKey = GetLastError();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        SpecifiedMasterKey,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        233);
LABEL_141:
    v15 = 0;
    if ( SpecifiedMasterKey == 50 )
      SpecifiedMasterKey = 13;
    goto LABEL_294;
  }
  hAlgorithm = (BCRYPT_ALG_HANDLE)GetBCryptProviderHandle(v49);
  v54 = hAlgorithm;
  if ( !hAlgorithm )
  {
    SpecifiedMasterKey = GetLastError();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        SpecifiedMasterKey,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        249);
    goto LABEL_141;
  }
  if ( (v136 & 1) != 0 && a10 >= 0 )
  {
    if ( (a10 & 1) != 0 )
    {
      SpecifiedMasterKey = 1325;
      v15 = 5;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          45,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          13);
      goto LABEL_294;
    }
    if ( !a9 )
    {
      SpecifiedMasterKey = 87;
      v50 = WPP_GLOBAL_Control;
      v47 = &WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_126;
      dwFlags = 20;
      goto LABEL_125;
    }
    if ( *(_DWORD *)a9 != 8 )
    {
      SpecifiedMasterKey = 87;
      v50 = WPP_GLOBAL_Control;
      v47 = &WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_126;
      dwFlags = 27;
      goto LABEL_125;
    }
    if ( (*((_DWORD *)a9 + 1) & 0xFFFFFFE4) != 0 )
    {
      SpecifiedMasterKey = 87;
      v50 = WPP_GLOBAL_Control;
      v47 = &WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_126;
      dwFlags = 37;
      goto LABEL_125;
    }
  }
  v55 = 0;
  if ( *a1 == 624 && (v55 = a1[12], v55 - 18 <= 2) )
  {
    v56 = 0;
    do
    {
      if ( *a1 == 624 )
      {
        v57 = v160[v56];
        if ( v57 != a1[12] )
        {
          v58 = (void *)*((_QWORD *)a1 + 5);
          if ( v58 )
          {
            LocalFree(v58);
            *((_QWORD *)a1 + 5) = 0;
          }
          a1[12] = v57;
        }
      }
      SpecifiedMasterKey = GetSpecifiedMasterKey(a1, &Uuid, (unsigned __int8 **)&hMem, &v139);
      if ( !SpecifiedMasterKey )
        break;
      v56 = (unsigned int)(v56 + 1);
    }
    while ( (unsigned int)v56 < 3 );
    CPSSetWellKnownAccount(a1, v55);
    v54 = hAlgorithm;
    v53 = BCryptProviderHandle;
  }
  else
  {
    SpecifiedMasterKey = GetSpecifiedMasterKey(a1, &Uuid, (unsigned __int8 **)&hMem, &v139);
  }
  if ( SpecifiedMasterKey )
  {
    v59 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_SD(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        44,
        (unsigned int)WPP_96027a338e1f3ff10006943bca18f271_Traceguids,
        (unsigned int)v170,
        SpecifiedMasterKey);
      v59 = WPP_GLOBAL_Control;
    }
    if ( v55 - 19 > 1 )
    {
      v15 = 6;
      goto LABEL_294;
    }
    if ( (_UNKNOWN *)v59 != &WPP_GLOBAL_Control && (*(_BYTE *)(v59 + 28) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(v59 + 16), 45, WPP_96027a338e1f3ff10006943bca18f271_Traceguids);
    CPSSetWellKnownAccount(a1, 0);
    SpecifiedMasterKey = GetSpecifiedMasterKey(a1, &Uuid, (unsigned __int8 **)&hMem, &v139);
    CPSSetWellKnownAccount(a1, v55);
    if ( SpecifiedMasterKey )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_SD(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          46,
          (unsigned int)WPP_96027a338e1f3ff10006943bca18f271_Traceguids,
          (unsigned int)v170,
          SpecifiedMasterKey);
        v15 = 0;
        goto LABEL_294;
      }
      goto LABEL_126;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 47, WPP_96027a338e1f3ff10006943bca18f271_Traceguids);
  }
  if ( !(unsigned int)FMyPrimitiveSHA((PUCHAR)hMem, v139, v166) )
  {
    SpecifiedMasterKey = 13;
    v50 = WPP_GLOBAL_Control;
    v47 = &WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_126;
    dwFlags = -111;
    goto LABEL_125;
  }
  if ( v143 == 32772 )
  {
    if ( !INCORRECT_FMyPrimitiveCryptHMAC(v166, v60, pbInput, v40, v53, 0x8004u, &phHash) )
    {
      v62 = GetLastError();
      SpecifiedMasterKey = v62;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          v62,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          163);
      goto LABEL_126;
    }
  }
  else
  {
    v64 = BCryptCreateHash(v54, &phHash, 0, 0, v166, 0x14u, 0);
    if ( v64 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v63,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"Status",
          v64,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          178);
      goto LABEL_206;
    }
    v64 = BCryptHashData(phHash, pbInput, v40, 0);
    if ( v64 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v65,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"Status",
          v64,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          189);
      goto LABEL_206;
    }
  }
  v66 = v163;
  if ( v163 )
  {
    v67 = BCryptHashData(phHash, v163, cbInput, 0);
    if ( v67 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v68,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"Status",
          v67,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          204);
LABEL_216:
      v15 = 0;
      SpecifiedMasterKey = -2146893819;
      goto LABEL_294;
    }
  }
  v69 = v155;
  if ( v155 )
  {
    if ( a12 )
    {
      v70 = BCryptHashData(phHash, v155, a12, 0);
      if ( v70 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            v71,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"Status",
            v70,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
            222);
        goto LABEL_216;
      }
    }
  }
  dwFlagsa[0] = v158;
  v72 = FMyDeriveBCryptKey(
          hObject,
          phHash,
          v142,
          v61,
          (v138 << 16) | 4,
          (unsigned __int8 *)v151,
          *(size_t *)dwFlagsa,
          0,
          0,
          &hKey);
  SpecifiedMasterKey = v72;
  if ( v72 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        v72,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        241);
    goto LABEL_126;
  }
  BCryptDestroyHash(phHash);
  phHash = 0;
  if ( v143 != 32772 )
  {
    v64 = BCryptCreateHash(hAlgorithm, &phHash, 0, 0, v166, 0x14u, 0);
    if ( v64 >= 0 )
    {
      v64 = BCryptHashData(phHash, v169, v51, 0);
      if ( v64 >= 0 )
      {
        v69 = v155;
        goto LABEL_241;
      }
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"Status",
          v64,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          33);
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"Status",
        v64,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        22);
    }
LABEL_206:
    v15 = 0;
    SpecifiedMasterKey = RtlNtStatusToDosError(v64);
    goto LABEL_294;
  }
  if ( !INCORRECT_FMyPrimitiveCryptHMAC(v166, v73, v169, v51, BCryptProviderHandle, 0x8004u, &phHash) )
  {
    v74 = GetLastError();
    SpecifiedMasterKey = v74;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        v74,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        7);
    goto LABEL_126;
  }
LABEL_241:
  if ( v66 )
  {
    v75 = BCryptHashData(phHash, v66, cbInput, 0);
    if ( v75 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"Status",
          v75,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          48);
      goto LABEL_216;
    }
  }
  if ( v69 )
  {
    if ( a12 )
    {
      v76 = BCryptHashData(phHash, v69, a12, 0);
      if ( v76 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            (unsigned int)&WPP_GLOBAL_Control,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"Status",
            v76,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
            66);
        goto LABEL_216;
      }
    }
  }
  v77 = (_DWORD)StringUuid - v51;
  if ( (unsigned int)((_DWORD)StringUuid - v51) < 4 )
  {
    SpecifiedMasterKey = 13;
    v15 = 3;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        82);
    goto LABEL_294;
  }
  cbOutput = *(unsigned int *)v161;
  v79 = (UCHAR *)(v161 + 4);
  if ( (unsigned int)(v77 - 4) < (unsigned __int64)(cbOutput + 4) )
  {
    SpecifiedMasterKey = 13;
    v50 = WPP_GLOBAL_Control;
    v47 = &WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_126;
    dwFlags = 96;
    goto LABEL_125;
  }
  v80 = cbOutput + *(_DWORD *)&v79[cbOutput] + 4;
  if ( v80 < (unsigned int)cbOutput )
  {
    SpecifiedMasterKey = 13;
    v50 = WPP_GLOBAL_Control;
    v47 = &WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_126;
    dwFlags = 107;
    goto LABEL_125;
  }
  if ( v77 - 4 < v80 )
  {
    SpecifiedMasterKey = 13;
    v15 = 3;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        114);
    goto LABEL_294;
  }
  v81 = BCryptHashData(phHash, v162, cbOutput + (_DWORD)v79 - (_DWORD)v162, 0);
  if ( v81 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"Status",
        v81,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        125);
    goto LABEL_216;
  }
  v82 = v137 >> 3;
  if ( v137 >> 3 > 0x40 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"NTE_FAIL",
        32,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        139);
    goto LABEL_274;
  }
  v83 = BCryptFinishHash(phHash, pbOutput, v82, 0);
  if ( v83 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"Status",
        v83,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        150);
    goto LABEL_274;
  }
  if ( *(_DWORD *)&v79[cbOutput] != v82 )
  {
LABEL_274:
    v15 = 0;
    SpecifiedMasterKey = 13;
    goto LABEL_294;
  }
  v84 = v82;
  v85 = 0;
  v86 = &v79[cbOutput + 4];
  for ( i = pbOutput; v84 >= 4; v85 |= v89 )
  {
    v88 = *(_DWORD *)i;
    v84 -= 4LL;
    i += 4;
    v89 = *(_DWORD *)v86 ^ v88;
    v86 += 4;
  }
  if ( v84 )
  {
    v90 = 0;
    do
    {
      v91 = *i++;
      v92 = *v86++;
      v90 |= v92 ^ v91;
      --v84;
    }
    while ( v84 );
    v85 |= v90;
  }
  if ( v85 )
  {
    SpecifiedMasterKey = 13;
    v15 = 2;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        168);
    goto LABEL_294;
  }
  pcbResult = cbOutput;
  if ( (v136 & 0x10000000) == 0 )
  {
    v93 = BCryptDecrypt(hKey, v79, cbOutput, 0, 0, 0, v79, cbOutput, &pcbResult, 1u);
    if ( v93 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"Status",
          v93,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          190);
      SpecifiedMasterKey = 13;
LABEL_293:
      v15 = 0;
      goto LABEL_294;
    }
    LODWORD(cbOutput) = pcbResult;
  }
  p_Data1 = &p_Uuid->Data1;
  p_Uuid->Data1 = cbOutput;
  if ( (a10 & 0x60000000) != 0 )
  {
    v103 = (unsigned __int8 *)LocalAlloc(0, (unsigned int)cbOutput);
    v100 = (HLOCAL *)v156;
    *v156 = v103;
    if ( !v103 )
    {
      *p_Data1 = 0;
      SpecifiedMasterKey = 14;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          6);
      goto LABEL_293;
    }
    memcpy_0(v103, v79, *p_Data1);
    v13 = a1;
  }
  else
  {
    v97 = 8;
    v98 = cbOutput & 7;
    if ( v98 != 8 )
      v97 = 8 - v98;
    v99 = (unsigned __int8 *)LocalAlloc(0, (unsigned int)cbOutput + v97);
    v100 = (HLOCAL *)v156;
    *v156 = v99;
    if ( !v99 )
    {
      *p_Data1 = 0;
      SpecifiedMasterKey = 14;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          219);
      goto LABEL_293;
    }
    memcpy_0(v99, v79, *p_Data1);
    memset_0((char *)*v100 + *p_Data1, (unsigned __int8)v97, v97);
    *p_Data1 += v97;
    v13 = a1;
    v101 = RpcImpersonateClient(*((RPC_BINDING_HANDLE *)a1 + 1));
    SpecifiedMasterKey = v101;
    if ( v101 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          v101,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          229);
      LocalFree(*v100);
      *v100 = 0;
      *p_Data1 = 0;
      goto LABEL_313;
    }
    v102 = SystemFunction040(*v100, *p_Data1, 2u);
    RevertToSelf();
    if ( v102 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"Status",
          v102,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          245);
      LocalFree(*v100);
      *v100 = 0;
      *p_Data1 = 0;
      v15 = 0;
      SpecifiedMasterKey = RtlNtStatusToDosError(v102);
      goto LABEL_295;
    }
  }
  v104 = (void **)v153;
  if ( v153 )
  {
    v105 = Size;
    v106 = LocalAlloc(0, Size + 2);
    *v104 = v106;
    if ( !v106 )
    {
      LocalFree(*v100);
      SpecifiedMasterKey = 14;
      *v100 = 0;
      *p_Data1 = 0;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)&WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
          24);
        goto LABEL_117;
      }
LABEL_313:
      v15 = 0;
      goto LABEL_295;
    }
    memset_0(v106, 0, v105 + 2);
    if ( Src )
      memcpy_0(*v104, Src, v105);
  }
  v23 = a10;
  SpecifiedMasterKey = 0;
  if ( (a10 & 0x40) != 0 )
  {
    v107 = GetBCryptProviderHandle(v140);
    v108 = GetBCryptProviderHandle(v141);
    if ( v107 )
    {
      if ( v108 && (v149 > v138 || v144 > v137) )
        SpecifiedMasterKey = 593938;
    }
  }
  if ( v146 )
    RemoveMasterKeyCache(0, 0);
  v15 = 0;
LABEL_296:
  v14 = (const unsigned __int16 *)Src;
  v94 = pcbResult;
  if ( Src && *(_WORD *)Src )
  {
    LODWORD(v95) = (_DWORD)Src;
    goto LABEL_358;
  }
LABEL_357:
  v95 = &Class;
LABEL_358:
  v109 = v136;
  SendETWInformation(0, (_DWORD)v95, (unsigned int)&Uuid, v23, v136, SpecifiedMasterKey, v94);
  if ( SpecifiedMasterKey )
  {
    if ( (unsigned int)dword_18004C260 > 5 )
    {
      v111 = qword_18004C278;
      v110 = 0;
      if ( (qword_18004C270 & 0x400000000000LL) != 0 && (qword_18004C278 & 0x400000000000LL) == qword_18004C278 )
      {
        if ( !v14 || (v114 = v14, !*v14) )
          v114 = &Class;
        v153 = (unsigned __int16 **)v114;
        v146 = v109;
        p_Uuid = &Uuid;
        LODWORD(StringUuid) = v23;
        v144 = SpecifiedMasterKey;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          qword_18004C278,
          (unsigned int)byte_180044B3D,
          v112,
          v113,
          (__int64)&v144,
          (__int64)&p_Uuid,
          (__int64)&StringUuid,
          (__int64)&v146,
          (__int64)&v153);
      }
    }
    if ( Microsoft_Windows_Crypto_DPAPIEnableBits < 0 )
      McTemplateU0dq_EtwEventWriteTransfer(v111, ETW_LOG_DPAPI_UNPROTECT_FAILED, SpecifiedMasterKey, v15);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v110,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRet",
        SpecifiedMasterKey,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32p.cpp",
        95);
  }
  if ( ((v109 & 0x10) != 0 || SpecifiedMasterKey) && v14 && *v14 )
  {
    v115 = 0;
    while ( v142 != *((_DWORD *)&g_AlgToString + 4 * v115) )
    {
      if ( ++v115 >= 0x17 )
      {
        LODWORD(pbSecret) = v138;
        v116 = StringCchPrintfW(v171, 0x1Eu, L"Unknown 0x%lx - %d", v142, pbSecret);
        goto LABEL_380;
      }
    }
    v116 = StringCchPrintfW(v171, 0x1Eu, (const unsigned __int16 *)*(&g_AlgToString + 2 * v115 + 1), v138);
LABEL_380:
    if ( v116 )
      goto LABEL_384;
    v117 = -1;
    do
      ++v117;
    while ( v171[v117] );
    v118 = v137;
    v119 = v143;
    v120 = (unsigned int)v117;
    v121 = (unsigned int)(v117 + 1);
    v171[v120] = 44;
    v171[v121] = 32;
    if ( AlgIDToString(&v171[(unsigned int)(v121 + 1)], 0x20u, v119, v118) )
LABEL_384:
      v171[0] = 0;
    v122 = SpecifiedMasterKey;
    if ( SpecifiedMasterKey == 593938 )
      v122 = 0;
    CPSAudit(*((void **)v13 + 3), 0x257u, v170, v14, 0, v171, v122);
  }
  v123 = v166;
  v124 = 20;
  do
  {
    *v123++ = 0;
    --v124;
  }
  while ( v124 );
  v125 = pbInput;
  v126 = 32;
  do
  {
    *v125++ = 0;
    --v126;
  }
  while ( v126 );
  v127 = hMem;
  if ( hMem )
  {
    v128 = v139;
    if ( v139 )
    {
      do
      {
        *v127++ = 0;
        --v128;
      }
      while ( v128 );
      v127 = hMem;
    }
    LocalFree(v127);
  }
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v151 )
    LocalFree(v151);
  return SpecifiedMasterKey;
}

```

## disassembly

```asm
0x180016370  push    rbp
0x180016372  push    rbx
0x180016373  push    rsi
0x180016374  push    rdi
0x180016375  push    r12
0x180016377  push    r13
0x180016379  push    r14
0x18001637b  push    r15
0x18001637d  lea     rbp, [rsp-1D8h]
0x180016385  sub     rsp, 2D8h
0x18001638c  mov     rax, cs:__security_cookie
0x180016393  xor     rax, rsp
0x180016396  mov     [rbp+210h+var_50], rax
0x18001639d  mov     rax, [rbp+210h+arg_28]
0x1800163a4  mov     rdi, r9
0x1800163a7  mov     [rbp+210h+var_238], rax
0x1800163ab  mov     r13, rcx
0x1800163ae  mov     rax, [rbp+210h+arg_30]
0x1800163b5  xorps   xmm0, xmm0
0x1800163b8  mov     [rbp+210h+var_1E8], r9
0x1800163bc  xorps   xmm1, xmm1
0x1800163bf  xor     r9d, r9d
0x1800163c2  mov     [rbp+210h+var_1E0], rax
0x1800163c6  mov     [rsp+310h+var_2B8], rcx
0x1800163cb  xor     eax, eax
0x1800163cd  mov     rcx, [rbp+210h+arg_50]; int
0x1800163d4  mov     r15d, r9d
0x1800163d7  mov     [rdx], r9
0x1800163da  mov     r12d, r9d
0x1800163dd  mov     [rbp+210h+var_1B0], eax
0x1800163e0  mov     ebx, r9d
0x1800163e3  mov     [rbp+210h+var_240], r8
0x1800163e7  mov     [rbp+210h+var_220], rdx
0x1800163eb  mov     [rbp+210h+var_228], rcx
0x1800163ef  mov     [rbp+210h+hKey], r9
0x1800163f3  mov     [rsp+310h+phHash], r9
0x1800163f8  mov     [rbp+210h+hMem], r9
0x1800163fc  mov     [rsp+310h+var_294], r9d
0x180016401  mov     [rsp+310h+var_2B0], r9d
0x180016406  mov     [rbp+210h+var_200], 12h
0x18001640d  mov     [rbp+210h+var_1FC], 13h
0x180016414  mov     [rbp+210h+var_1F8], 14h
0x18001641b  mov     [r8], r9d
0x18001641e  movups  xmmword ptr [rbp+210h+Uuid.Data1], xmm0
0x180016422  mov     [rsp+310h+var_298], r9d
0x180016427  movups  xmmword ptr [rbp+210h+var_1C0], xmm1
0x18001642b  mov     [rsp+310h+var_29C], r9d
0x180016430  mov     [rbp+210h+var_248], r9
0x180016434  mov     [rsp+310h+var_2A0], r9d
0x180016439  mov     [rbp+210h+Src], r9
0x18001643d  mov     [rsp+310h+var_2C0], r9d
0x180016442  mov     [rbp+210h+var_288], r9d
0x180016446  mov     [rbp+210h+var_284], r9d
0x18001644a  mov     [rbp+210h+var_160], r9w
0x180016452  call    ?UpdateGlobals@@YAKH@Z; UpdateGlobals(int)
0x180016457  cmp     cs:dword_18004CCB4, ebx
0x18001645d  jz      short loc_180016477
0x18001645f  lea     rcx, stru_18004C978; CriticalSection
0x180016466  call    cs:__imp_RtlEnterCriticalSection
0x18001646d  nop     dword ptr [rax+rax+00h]
0x180016472  mov     ebx, 1
0x180016477  mov     eax, cs:dword_18004C548
0x18001647d  mov     esi, 6603h
0x180016482  mov     [rbp+210h+var_290], esi
0x180016485  cmp     eax, esi
0x180016487  jz      short loc_1800164AE
0x180016489  mov     ecx, cs:dword_18004C550
0x18001648f  mov     r14d, 800Eh
0x180016495  mov     [rbp+210h+var_28C], r14d
0x180016499  cmp     eax, 0FFFFFFFFh
0x18001649c  jnz     loc_1800166A9
0x1800164a2  cmp     ecx, 8004h
0x1800164a8  jnz     loc_1800166B5
0x1800164ae  mov     r14d, 8004h
0x1800164b4  mov     [rbp+210h+var_28C], r14d
0x1800164b8  mov     [rbp+210h+var_258], 0FFFFFFFFh
0x1800164bf  mov     [rbp+210h+var_280], 0FFFFFFFFh
0x1800164c6  test    ebx, ebx
0x1800164c8  jz      short loc_1800164DD
0x1800164ca  lea     rcx, stru_18004C978; CriticalSection
0x1800164d1  call    cs:__imp_RtlLeaveCriticalSection
0x1800164d8  nop     dword ptr [rax+rax+00h]
0x1800164dd  mov     [r13+34h], esi
0x1800164e1  lea     rbx, WPP_GLOBAL_Control
0x1800164e8  mov     [r13+38h], r14d
0x1800164ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800164f3  test    byte ptr [rcx+1Ch], 4
0x1800164f7  jz      loc_18001662A
0x1800164fd  cmp     rcx, rbx
0x180016500  jz      loc_18001662A
0x180016506  mov     rcx, [rcx+10h]
0x18001650a  mov     edx, 1Bh
0x18001650f  mov     r9, r13
0x180016512  call    WPP_SF_q
0x180016517  mov     rcx, cs:WPP_GLOBAL_Control
0x18001651e  cmp     rcx, rbx
0x180016521  jz      loc_18001662A
0x180016527  test    byte ptr [rcx+1Ch], 4
0x18001652b  jz      short loc_180016546
0x18001652d  mov     r9, [r13+8]
0x180016531  mov     edx, 1Ch
0x180016536  mov     rcx, [rcx+10h]
0x18001653a  call    WPP_SF_q
0x18001653f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016546  cmp     rcx, rbx
0x180016549  jz      loc_18001662A
0x18001654f  test    byte ptr [rcx+1Ch], 4
0x180016553  jz      short loc_180016575
0x180016555  mov     r9d, [r13+14h]
0x180016559  lea     r8, WPP_96027a338e1f3ff10006943bca18f271_Traceguids
0x180016560  mov     rcx, [rcx+10h]
0x180016564  mov     edx, 1Dh
0x180016569  call    WPP_SF_d
0x18001656e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016575  cmp     rcx, rbx
0x180016578  jz      loc_18001662A
0x18001657e  test    byte ptr [rcx+1Ch], 4
0x180016582  jz      short loc_18001659D
0x180016584  mov     r9, [r13+18h]
0x180016588  mov     edx, 1Eh
0x18001658d  mov     rcx, [rcx+10h]
0x180016591  call    WPP_SF_q
0x180016596  mov     rcx, cs:WPP_GLOBAL_Control
0x18001659d  cmp     rcx, rbx
0x1800165a0  jz      loc_18001662A
0x1800165a6  test    byte ptr [rcx+1Ch], 4
0x1800165aa  jz      short loc_1800165CC
0x1800165ac  mov     rcx, [rcx+10h]
0x1800165b0  lea     r9, [r13+50h]
0x1800165b4  mov     edx, 1Fh
0x1800165b9  lea     r8, WPP_96027a338e1f3ff10006943bca18f271_Traceguids
0x1800165c0  call    WPP_SF_S
0x1800165c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165cc  cmp     rcx, rbx
0x1800165cf  jz      short loc_18001662A
0x1800165d1  test    byte ptr [rcx+1Ch], 4
0x1800165d5  jz      short loc_1800165FF
0x1800165d7  mov     eax, [r13+40h]
0x1800165db  lea     r8, WPP_96027a338e1f3ff10006943bca18f271_Traceguids
0x1800165e2  mov     r9d, [r13+3Ch]
0x1800165e6  mov     edx, 20h ; ' '
0x1800165eb  mov     rcx, [rcx+10h]
0x1800165ef  mov     dword ptr [rsp+310h+pbSecret], eax
0x1800165f3  call    WPP_SF_dd
0x1800165f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165ff  cmp     rcx, rbx
0x180016602  jz      short loc_18001662A
0x180016604  test    byte ptr [rcx+1Ch], 4
0x180016608  jz      short loc_18001662A
0x18001660a  mov     r9d, [r13+30h]
0x18001660e  lea     r8, WPP_96027a338e1f3ff10006943bca18f271_Traceguids
0x180016615  mov     rcx, [rcx+10h]
0x180016619  mov     edx, 21h ; '!'
0x18001661e  call    WPP_SF_d
0x180016623  mov     rcx, cs:WPP_GLOBAL_Control
0x18001662a  mov     esi, [rbp+210h+arg_48]
0x180016630  mov     eax, esi
0x180016632  and     eax, 4000000h
0x180016637  mov     [rbp+210h+var_270], eax
0x18001663a  jz      short loc_18001664C
0x18001663c  xor     edx, edx; unsigned __int16 *
0x18001663e  xor     ecx, ecx; struct _LUID *
0x180016640  call    ?RemoveMasterKeyCache@@YAHPEAU_LUID@@PEBG@Z; RemoveMasterKeyCache(_LUID *,ushort const *)
0x180016645  mov     rcx, cs:WPP_GLOBAL_Control
0x18001664c  mov     r14d, [rbp+210h+arg_20]
0x180016653  cmp     r14d, 1Ch
0x180016657  jnb     loc_1800166E4
0x18001665d  mov     edi, 0Dh
0x180016662  lea     r14, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180016669  cmp     rcx, rbx
0x18001666c  jz      loc_180017DA3
0x180016672  test    byte ptr [rcx+1Ch], 1
0x180016676  jz      loc_180017DA3
0x18001667c  mov     [rsp+310h+dwFlags], 4E5h
0x180016684  mov     rcx, [rcx+10h]
0x180016688  lea     r9, aDwret; "dwRet"
0x18001668f  mov     qword ptr [rsp+310h+cbSecret], r14
0x180016694  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18001669b  mov     dword ptr [rsp+310h+pbSecret], edi
0x18001669f  call    WPP_SF_sDsd
0x1800166a4  jmp     loc_180017DA3
0x1800166a9  cmp     eax, 6610h
0x1800166ae  jz      short loc_1800166D7
0x1800166b0  cmp     eax, 0FFFFFFFFh
0x1800166b3  jnz     short loc_1800166BA
0x1800166b5  cmp     ecx, r14d
0x1800166b8  jz      short loc_1800166D7
0x1800166ba  mov     esi, 6801h
0x1800166bf  mov     [rbp+210h+var_290], esi
0x1800166c2  cmp     eax, esi
0x1800166c4  jz      loc_1800164AE
0x1800166ca  mov     esi, 6610h
0x1800166cf  mov     [rbp+210h+var_290], esi
0x1800166d2  jmp     loc_1800164B8
0x1800166d7  mov     esi, 6610h
0x1800166dc  mov     [rbp+210h+var_290], esi
0x1800166df  jmp     loc_1800164B4
0x1800166e4  cmp     dword ptr [rdi], 1
0x1800166e7  jz      short loc_18001671B
0x1800166e9  mov     edi, 0Dh
0x1800166ee  mov     r12d, 1
0x1800166f4  lea     r14, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800166fb  cmp     rcx, rbx
0x1800166fe  jz      loc_180017DA3
0x180016704  test    [rcx+1Ch], r12b
0x180016708  jz      loc_180017DA3
0x18001670e  mov     [rsp+310h+dwFlags], 4EEh
0x180016716  jmp     loc_180016684
0x18001671b  movups  xmm0, xmmword ptr [rdi+4]
0x18001671f  lea     rdx, [rbp+210h+StringUuid]; StringUuid
0x180016723  mov     [rbp+210h+StringUuid], r12
0x180016727  lea     rcx, [rbp+210h+Uuid]; Uuid
0x18001672b  movups  xmmword ptr [rbp+210h+Uuid.Data1], xmm0
0x18001672f  call    cs:__imp_UuidToStringW
0x180016736  nop     dword ptr [rax+rax+00h]
0x18001673b  test    eax, eax
0x18001673d  jnz     short loc_18001677B
0x18001673f  mov     rcx, [rbp+210h+StringUuid]; lpString
0x180016743  call    cs:__imp_lstrlenW
0x18001674a  nop     dword ptr [rax+rax+00h]
0x18001674f  cmp     eax, 28h ; '('
0x180016752  jnb     short loc_18001676B
0x180016754  mov     rdx, [rbp+210h+StringUuid]; Src
0x180016758  lea     r8d, [rax+1]
0x18001675c  add     r8, r8; Size
0x18001675f  lea     rcx, [rbp+210h+var_160]; void *
0x180016766  call    memcpy_0
0x18001676b  lea     rcx, [rbp+210h+StringUuid]; String
0x18001676f  call    cs:__imp_RpcStringFreeW
0x180016776  nop     dword ptr [rax+rax+00h]
0x18001677b  mov     rsi, cs:WPP_GLOBAL_Control
0x180016782  lea     r8, WPP_GLOBAL_Control
0x180016789  cmp     rsi, r8
0x18001678c  jz      short loc_1800167BE
0x18001678e  test    byte ptr [rsi+1Ch], 8
0x180016792  jz      short loc_1800167BE
0x180016794  mov     rcx, [rsi+10h]
0x180016798  lea     r9, [rbp+210h+var_160]
0x18001679f  mov     edx, 26h ; '&'
0x1800167a4  lea     r8, WPP_96027a338e1f3ff10006943bca18f271_Traceguids
0x1800167ab  call    WPP_SF_S
0x1800167b0  mov     rsi, cs:WPP_GLOBAL_Control
0x1800167b7  lea     r8, WPP_GLOBAL_Control
0x1800167be  mov     eax, [rdi+14h]
0x1800167c1  lea     rbx, [rdi+18h]
0x1800167c5  mov     [rsp+310h+var_2A0], eax
0x1800167c9  cmp     rsi, r8
0x1800167cc  jz      short loc_1800167FE
0x1800167ce  test    byte ptr [rsi+1Ch], 8
0x1800167d2  jz      short loc_1800167FE
0x1800167d4  mov     rcx, [rsi+10h]
0x1800167d8  lea     r8, WPP_96027a338e1f3ff10006943bca18f271_Traceguids
0x1800167df  mov     edx, 27h ; '''
0x1800167e4  mov     r9d, eax
0x1800167e7  call    WPP_SF_d
0x1800167ec  mov     eax, [rsp+310h+var_2A0]
0x1800167f0  lea     r8, WPP_GLOBAL_Control
0x1800167f7  mov     rsi, cs:WPP_GLOBAL_Control
0x1800167fe  test    al, 4
0x180016800  jz      short loc_18001681B
0x180016802  cmp     dword ptr [r13+0], 270h
0x18001680a  jnz     short loc_18001681B
0x18001680c  mov     dword ptr [r13+10h], 1
0x180016814  mov     rsi, cs:WPP_GLOBAL_Control
0x18001681b  cmp     rsi, r8
0x18001681e  jz      short loc_18001684D
0x180016820  test    byte ptr [rsi+1Ch], 4
0x180016824  jz      short loc_18001684D
0x180016826  mov     r9d, [r13+10h]
0x18001682a  lea     r8, WPP_96027a338e1f3ff10006943bca18f271_Traceguids
0x180016831  mov     rcx, [rsi+10h]
0x180016835  mov     edx, 28h ; '('
0x18001683a  call    WPP_SF_d
0x18001683f  mov     rsi, cs:WPP_GLOBAL_Control
0x180016846  lea     r8, WPP_GLOBAL_Control
0x18001684d  mov     ecx, [rbp+210h+arg_48]
0x180016853  mov     eax, ecx
0x180016855  and     eax, 20000000h
0x18001685a  test    [rsp+310h+var_2A0], 20000000h
0x180016862  jz      short loc_18001689A
0x180016864  test    eax, eax
0x180016866  jnz     short loc_1800168D4
0x180016868  mov     edi, 0Dh
0x18001686d  mov     r12d, 4
0x180016873  lea     r14, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001687a  cmp     rsi, r8
0x18001687d  jz      loc_180017D9D
0x180016883  test    byte ptr [rsi+1Ch], 1
0x180016887  jz      loc_180017D9D
0x18001688d  mov     [rsp+310h+dwFlags], 51Dh
0x180016895  jmp     loc_180017D7D
0x18001689a  test    eax, eax
0x18001689c  jz      short loc_1800168D4
0x18001689e  test    ecx, ecx
0x1800168a0  js      short loc_1800168D4
0x1800168a2  mov     edi, 0Dh
0x1800168a7  mov     r12d, 4
0x1800168ad  lea     r14, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800168b4  cmp     rsi, r8
0x1800168b7  jz      loc_180017D9D
  ... truncated ...
```
