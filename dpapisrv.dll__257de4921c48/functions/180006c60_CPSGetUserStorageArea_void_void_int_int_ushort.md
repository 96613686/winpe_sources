# CPSGetUserStorageArea(void *,void *,int,int,ushort * *)

- ea: `0x180006c60`
- end: `0x180007f09`
- name: `?CPSGetUserStorageArea@@YAKPEAX0HHPEAPEAG@Z`
- size: `4777`
- prototype: `__int64 __fastcall(_DWORD *, void *, unsigned int, int, unsigned __int16 **)`
- caller_count: `11`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008498`
- `0x180008c3c`
- `0x18000e9c0`
- `0x180018a20`
- `0x1800193c0`
- `0x18001b72c`
- `0x18001cd50`
- `0x18002a03c`
- `0x18002b0ec`
- `0x18002e310`
- `0x18002ea4c`

## callees

- `0x180006c60`
- `0x180007f10`
- `0x180008300`
- `0x180008a44`
- `0x18001c008`
- `0x18001c340`
- `0x18001d810`
- `0x18001d850`
- `0x18001e1b4`
- `0x18001eb8c`
- `0x18001ff94`
- `0x180021078`
- `0x18002f6bc`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800075f7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800075f7`
- `RPCRT4!RpcRevertToSelfEx` at `0x180007d25`
- `RPCRT4!RpcRevertToSelfEx` at `0x180007eea`
- `RPCRT4!RpcRevertToSelfEx` at `0x180007d25`
- `RPCRT4!RpcRevertToSelfEx` at `0x180007eea`
- `RPCRT4!RpcImpersonateClient` at `0x180007c9f`
- `RPCRT4!RpcImpersonateClient` at `0x180007d8f`
- `RPCRT4!RpcImpersonateClient` at `0x180007c9f`
- `RPCRT4!RpcImpersonateClient` at `0x180007d8f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006f76`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180007691`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006f76`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180007691`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006f8d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006f8d`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180006e9e`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800071f9`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180006e9e`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800071f9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006fbe`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006fbe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000711c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007505`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000711c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007505`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000763f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000763f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ded`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079e2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006f12`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800075ab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007748`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006f12`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800075ab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007748`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006dcb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000719f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006dcb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000719f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006ef3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000758c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007729`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006ef3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000758c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007729`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006e27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006fe3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000708e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800070ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800073dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000791e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006e27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006fe3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000708e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800070ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800073dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000791e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007b05`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006fa2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800072a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007359`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800074b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000765d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800076f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000796f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007b77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006fa2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800072a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007359`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800074b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000765d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800076f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000796f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007b77`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180007253`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180007253`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000760f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ceb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000760f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ceb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800073c1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800073c1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800079bf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800079bf`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000722a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000722a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180007024`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800078b0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180007024`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800078b0`
- `USERENV!GetUserProfileDirectoryW` at `0x1800075d0`
- `USERENV!GetUserProfileDirectoryW` at `0x1800075d0`

## string_xrefs

- `0x180007a3e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x180006df1`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180006ec0`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x1800071bb`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000720d`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180007458`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x1800074e1`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x1800076ad`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180007787`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180007bd6`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180007c1f`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180007cbb`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180007cdd`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180007d53`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180007d9b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180007dc9`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180007e37`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180007e74`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180007e82`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180007ad2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x180007dff`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c
__int64 __fastcall CPSGetUserStorageArea(_DWORD *a1, void *a2, unsigned int a3, int a4, unsigned __int16 **a5)
{
  HLOCAL *v5; // r14
  _DWORD *v7; // r13
  __int64 v8; // rbx
  unsigned int v9; // r15d
  __int64 v10; // rax
  DWORD v11; // r12d
  int v12; // eax
  __int64 LastError; // rdi
  void *v14; // rdx
  unsigned int v15; // ebx
  unsigned int v17; // r14d
  BOOL v18; // ebx
  HANDLE CurrentThread; // rax
  HANDLE v20; // rdi
  void *v21; // r13
  void *v22; // rcx
  HLOCAL v23; // r14
  PSID *v24; // r15
  DWORD LengthSid; // esi
  HLOCAL v26; // rax
  void *v27; // rbx
  int v28; // ebx
  BOOL v29; // eax
  LPWSTR v30; // r10
  __int64 v31; // rcx
  __int16 *p_Src; // r9
  LPWSTR v33; // rdx
  __int64 v34; // r8
  __int16 *v35; // rdx
  __int64 v36; // rsi
  __int64 v37; // rax
  bool v38; // zf
  int v39; // ecx
  void *v40; // rdx
  unsigned int v41; // r14d
  int v42; // r13d
  __int64 v43; // rax
  __int64 *v44; // r12
  __int64 v45; // rbx
  unsigned int v46; // r15d
  unsigned __int64 v47; // rax
  unsigned int v48; // r14d
  unsigned __int16 *v49; // rdi
  __int64 v50; // r13
  __int64 v51; // xmm0_8
  HLOCAL v52; // rdx
  char *v53; // rdi
  char *v54; // rdi
  unsigned __int16 **v55; // r12
  __int64 v56; // rax
  _WORD *v57; // r14
  __int64 v58; // rbx
  WCHAR *v59; // rax
  int v60; // edx
  WCHAR *v61; // r15
  __int64 v62; // r14
  HANDLE FileW; // rbx
  int v64; // ecx
  int v65; // r8d
  SIZE_T v66; // rbx
  HLOCAL v67; // rax
  _DWORD *v68; // rsi
  DWORD v69; // eax
  __int64 v70; // r9
  __int64 v71; // rcx
  HANDLE v72; // rax
  unsigned __int64 v73; // rax
  HLOCAL v74; // rax
  HANDLE v75; // rax
  __int128 v76; // xmm0
  unsigned __int16 *v77; // rax
  unsigned int v78; // r8d
  unsigned int UserDirFromRegistry; // eax
  __int64 v80; // r9
  __int64 v81; // rcx
  int v82; // ebx
  BOOL v83; // eax
  _WORD *v84; // rdx
  void *v85; // r10
  __int64 v86; // rcx
  _WORD *v87; // r9
  _WORD *v88; // rdx
  __int64 v89; // r8
  __int64 v90; // r14
  HLOCAL v91; // rax
  DWORD v92; // r12d
  int v93; // edx
  int v94; // r8d
  int v95; // edx
  DWORD v96; // eax
  int v97; // edx
  __int64 v98; // rsi
  unsigned __int16 *v99; // rax
  void *v100; // rcx
  unsigned int v101; // eax
  void *v102; // rcx
  DWORD v103; // eax
  __int64 v104; // r9
  void *v105; // rcx
  unsigned int v106; // eax
  unsigned __int64 v107; // rcx
  void *v108; // rcx
  DWORD TokenInformationLength[2]; // [rsp+50h] [rbp-B8h] BYREF
  _DWORD *v110; // [rsp+58h] [rbp-B0h]
  void *TokenHandle; // [rsp+60h] [rbp-A8h] BYREF
  DWORD cchSize[2]; // [rsp+68h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-98h]
  HANDLE hObject; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v115; // [rsp+80h] [rbp-88h] BYREF
  LPWSTR StringSid; // [rsp+88h] [rbp-80h] BYREF
  BOOL v117; // [rsp+90h] [rbp-78h]
  int v118; // [rsp+94h] [rbp-74h]
  void *v119; // [rsp+98h] [rbp-70h]
  __int64 v120; // [rsp+A0h] [rbp-68h] BYREF
  int v121; // [rsp+A8h] [rbp-60h]
  char v122[16]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v123[24]; // [rsp+C0h] [rbp-48h]
  __int64 v124; // [rsp+D8h] [rbp-30h]
  __int16 Src; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v126; // [rsp+EAh] [rbp-1Eh]
  __int64 v127; // [rsp+FAh] [rbp-Eh]
  WCHAR Buffer[264]; // [rsp+2F8h] [rbp+1F0h] BYREF
  _BYTE TokenInformation[256]; // [rsp+508h] [rbp+400h] BYREF
  _WORD v131[264]; // [rsp+608h] [rbp+500h] BYREF

  v5 = (HLOCAL *)a5;
  v7 = a1;
  v118 = a4;
  v115 = a3;
  v119 = a2;
  v110 = a1;
  *(_QWORD *)&v123[16] = *(_QWORD *)L"ct\\";
  v120 = *(_QWORD *)L"\\User";
  v121 = *(_DWORD *)L"r";
  *a5 = 0;
  *(_OWORD *)v123 = *(_OWORD *)L"ft\\Protect\\";
  if ( !a1 )
    return 87;
  v8 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    WPP_SF_Sdd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), (_DWORD)a2, a3, (_DWORD)a1 + 80, a1[15], a1[16]);
    v8 = WPP_GLOBAL_Control;
  }
  v9 = 87;
  if ( a2 )
  {
    TokenHandle = 0;
    v82 = 0;
    v83 = ConvertSidToStringSidW(a2, (LPWSTR *)&TokenHandle);
    v85 = TokenHandle;
    if ( v83 )
    {
      v86 = 2147483646;
      v87 = v131;
      v88 = TokenHandle;
      v89 = 261;
      do
      {
        if ( !v86 )
          break;
        if ( !*v88 )
          break;
        *v87++ = *v88++;
        --v86;
        --v89;
      }
      while ( v89 );
      v84 = v87 - 1;
      if ( v89 )
        v84 = v87;
      *v84 = 0;
      if ( v89 )
        v82 = 1;
    }
    if ( v85 )
      LocalFree(v85);
    if ( v82 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 29, WPP_5351e3ad169c3699daa4b130ec8527d7_Traceguids, v131);
      v36 = -1;
      v90 = -1;
      do
        ++v90;
      while ( v131[v90] );
      hObject = (HANDLE)v90;
      v91 = LocalAlloc(0, 2LL * (unsigned int)(v90 + 1));
      hMem = v91;
      if ( v91 )
      {
        memcpy_0(v91, v131, 2LL * (unsigned int)(v90 + 1));
        goto LABEL_70;
      }
      v5 = (HLOCAL *)a5;
      LODWORD(LastError) = 8;
    }
    else
    {
      LODWORD(LastError) = 87;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (_DWORD)v84,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwLastError",
          87,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
          12);
    }
LABEL_191:
    if ( *v5 )
    {
      LocalFree(*v5);
      *v5 = 0;
    }
    return (unsigned int)LastError;
  }
  v10 = *((_QWORD *)v7 + 5);
  if ( !v10 )
  {
    hMem = 0;
    memset_0(&Src, 0, 0x20Au);
    if ( *v7 != 624 )
    {
      LODWORD(LastError) = 87;
      goto LABEL_19;
    }
    v11 = 0;
    v12 = v7[12];
    cchSize[0] = 0;
    if ( v7[4] || v12 == 18 )
    {
      v76 = xmmword_180041552;
    }
    else if ( v12 == 19 )
    {
      v76 = xmmword_180041622;
    }
    else
    {
      if ( v12 != 20 )
      {
        if ( v12 == 90 )
        {
          v17 = 13;
          v76 = xmmword_180042932;
          v127 = 0x31002D0032LL;
        }
        else
        {
          if ( v12 != 91 )
          {
            LODWORD(LastError) = 87;
            if ( v7[4] || v12 && (unsigned int)(v12 - 90) > 1 && v12 != 99 )
            {
              if ( !ImpersonateSelf(SecurityImpersonation) )
              {
                LODWORD(LastError) = GetLastError();
                DebugTraceError(
                  (unsigned int)LastError,
                  "dwLastError",
                  "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
                  816);
                if ( (_DWORD)LastError )
                  goto LABEL_19;
              }
LABEL_27:
              v17 = 260;
              TokenHandle = 0;
              v18 = 0;
              LODWORD(StringSid) = 260;
              v117 = 0;
              CurrentThread = GetCurrentThread();
              if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
                goto LABEL_56;
              v20 = TokenHandle;
              v21 = 0;
              TokenInformationLength[0] = 0;
              hObject = 0;
              if ( TokenHandle )
              {
                v22 = TokenHandle;
                hObject = TokenHandle;
              }
              else
              {
                v75 = GetCurrentThread();
                if ( !OpenThreadToken(v75, 8u, 1, &hObject) )
                {
LABEL_37:
                  if ( hObject && hObject != v20 )
                    CloseHandle(hObject);
                  if ( v11 )
                  {
                    StringSid = 0;
                    v28 = 0;
                    v29 = ConvertSidToStringSidW(v21, &StringSid);
                    v30 = StringSid;
                    if ( v29 )
                    {
                      v31 = 2147483646;
                      p_Src = &Src;
                      v33 = StringSid;
                      v34 = 261;
                      do
                      {
                        if ( !v31 )
                          break;
                        if ( !*v33 )
                          break;
                        *p_Src++ = *v33++;
                        --v31;
                        --v34;
                      }
                      while ( v34 );
                      v35 = p_Src - 1;
                      if ( v34 )
                        v35 = p_Src;
                      *v35 = 0;
                      if ( v34 )
                        v28 = 1;
                    }
                    if ( v30 )
                      LocalFree(v30);
                    v18 = v28 != 0;
                  }
                  else
                  {
                    v18 = v117;
                  }
                  if ( v21 )
                    LocalFree(v21);
                  v11 = cchSize[0];
                  v7 = v110;
LABEL_56:
                  if ( TokenHandle )
                    CloseHandle(TokenHandle);
                  v36 = -1;
                  if ( v18 )
                  {
                    v37 = -1;
                    do
                      v38 = *(&Src + ++v37) == 0;
                    while ( !v38 );
                    v17 = v37 + 1;
                  }
                  if ( *v7 != 624 )
                    goto LABEL_66;
                  if ( v7[4] || *((_QWORD *)v7 + 3) )
                  {
                    if ( RevertToSelf() )
                    {
LABEL_66:
                      LODWORD(LastError) = 8;
                      if ( !v18 )
                        goto LABEL_67;
                      v8 = WPP_GLOBAL_Control;
LABEL_139:
                      v73 = 2LL * v17;
                      if ( v73 > 0xFFFFFFFF )
                      {
                        LODWORD(LastError) = 534;
                        goto LABEL_68;
                      }
                      v74 = LocalAlloc(0, (unsigned int)v73);
                      hMem = v74;
                      if ( v74 )
                      {
                        memcpy_0(v74, &Src, 2 * v17);
                        LODWORD(LastError) = 0;
                        v11 = v17;
                      }
LABEL_67:
                      v8 = WPP_GLOBAL_Control;
LABEL_68:
                      if ( (_DWORD)LastError )
                        goto LABEL_137;
                      hObject = (HANDLE)(v11 - 1);
                      if ( (_UNKNOWN *)v8 != &WPP_GLOBAL_Control && (*(_BYTE *)(v8 + 28) & 4) != 0 )
                        WPP_SF_S(*(_QWORD *)(v8 + 16), 28, WPP_5351e3ad169c3699daa4b130ec8527d7_Traceguids, hMem);
LABEL_70:
                      LODWORD(LastError) = 87;
                      if ( *v7 == 624 )
                      {
                        if ( v7[4] || (v39 = v7[12]) != 0 && (unsigned int)(v39 - 90) > 1 && v39 != 99 )
                        {
                          if ( !ImpersonateSelf(SecurityImpersonation) )
                          {
                            LastError = GetLastError();
                            DebugTraceError(
                              LastError,
                              "dwLastError",
                              "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
                              816);
                            if ( (_DWORD)LastError )
                              goto LABEL_136;
                          }
LABEL_80:
                          if ( *v7 == 624 )
                          {
                            v41 = v7[12];
                            v42 = v7[4];
                          }
                          else
                          {
                            v41 = 0;
                            v42 = 0;
                          }
                          if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
                          {
                            if ( v41 - 90 <= 1 )
                              goto LABEL_158;
                          }
                          else
                          {
                            if ( v42 )
                            {
LABEL_84:
                              LODWORD(v43) = GetSystemDirectoryW(Buffer, 0x105u);
                              goto LABEL_85;
                            }
                            if ( v41 && v41 != 99 )
                            {
                              if ( v41 - 90 > 1 )
                                goto LABEL_84;
LABEL_158:
                              v77 = CPSGetTextualSidForWellKnownAccount(v41);
                              UserDirFromRegistry = GetUserDirFromRegistry(v77, Buffer, v78);
                              LODWORD(LastError) = UserDirFromRegistry;
                              if ( UserDirFromRegistry )
                              {
                                v80 = 1635;
                                v81 = UserDirFromRegistry;
LABEL_160:
                                DebugTraceError(
                                  v81,
                                  "dwLastError",
                                  "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
                                  v80);
                                goto LABEL_161;
                              }
                              goto LABEL_129;
                            }
                          }
                          cchSize[0] = 260;
                          Buffer[0] = 0;
                          TokenHandle = 0;
                          v72 = GetCurrentThread();
                          if ( OpenThreadToken(v72, 8u, 1, &TokenHandle) )
                          {
                            if ( GetUserProfileDirectoryW(TokenHandle, Buffer, cchSize) )
                            {
                              _o_wcscat_s(Buffer, 260, L"\\AppData\\Roaming");
                              LODWORD(LastError) = 0;
                            }
                            else
                            {
                              LastError = GetLastError();
                              DebugTraceError(
                                LastError,
                                "Status",
                                "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp",
                                1278);
                            }
                          }
                          else
                          {
                            v96 = GetLastError();
                            LODWORD(LastError) = v96;
                            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                            {
                              WPP_SF_sDsd(
                                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                                v97,
                                (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
                                (unsigned int)"Status",
                                v96,
                                (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp",
                                237);
                            }
                          }
                          if ( TokenHandle )
                            CloseHandle(TokenHandle);
                          if ( (_DWORD)LastError )
                          {
                            v80 = 1646;
                            v81 = (unsigned int)LastError;
                            goto LABEL_160;
                          }
LABEL_129:
                          v43 = -1;
                          do
                            ++v43;
                          while ( Buffer[v43] );
LABEL_85:
                          v44 = 0;
                          v45 = (unsigned int)(2 * v43);
                          v46 = 0;
                          if ( v41 == 18 && !v42 )
                          {
                            v46 = 10;
                            v44 = &v120;
                          }
                          if ( (_DWORD)v45 )
                          {
                            v47 = (unsigned __int64)(unsigned int)v45 >> 1;
                            if ( Buffer[v47 - 1] == 92 )
                            {
                              v107 = 2 * v47 - 2;
                              if ( v107 >= 0x20A )
                                _report_rangecheckfailure();
                              *(WCHAR *)((char *)Buffer + v107) = 0;
                              v45 = (unsigned int)(v45 - 2);
                            }
                            v48 = 2 * (_DWORD)hObject;
                            v49 = (unsigned __int16 *)LocalAlloc(
                                                        0,
                                                        (unsigned int)v45 + v46 + 2 * (_DWORD)hObject + 38 + 4LL);
                            *a5 = v49;
                            if ( !v49 )
                            {
                              LODWORD(LastError) = 1130;
                              v5 = (HLOCAL *)a5;
                              goto LABEL_162;
                            }
                            v50 = (unsigned int)v45;
                            memcpy_0(v49, Buffer, (unsigned int)v45);
                            v51 = *(_QWORD *)&v123[14];
                            v52 = hMem;
                            *(_OWORD *)((char *)v49 + v45) = *(_OWORD *)L"\\Microsoft\\Protect\\";
                            *(_OWORD *)((char *)v49 + v45 + 16) = *(_OWORD *)L"ft\\Protect\\";
                            *(_QWORD *)((char *)v49 + v45 + 30) = v51;
                            v53 = (char *)v49 + (unsigned int)v45 + 38;
                            memcpy_0(v53, v52, v48);
                            v54 = &v53[v48];
                            if ( v46 )
                            {
                              memcpy_0(v54, v44, v46);
                              v54 += v46;
                            }
                            if ( *((_WORD *)v54 - 1) != 92 )
                            {
                              *(_WORD *)v54 = 92;
                              v54 += 2;
                            }
                            *(_WORD *)v54 = 0;
                            if ( v115 )
                            {
                              v55 = a5;
                              v56 = -1;
                              v57 = *a5;
                              do
                                v38 = v57[++v56] == 0;
                              while ( !v38 );
                              v58 = (unsigned int)(2 * v56);
                              v59 = (WCHAR *)LocalAlloc(0, (unsigned int)(v58 + 18) + 2LL);
                              v61 = v59;
                              if ( v59 )
                              {
                                LODWORD(LastError) = 0;
                                memcpy_0(v59, v57, (unsigned int)v58);
                                v62 = 0;
                                *(_OWORD *)((char *)v61 + v58) = *(_OWORD *)L"Preferred";
                                *(_DWORD *)((char *)v61 + v58 + 16) = *(_DWORD *)L"d";
                                while ( 1 )
                                {
                                  FileW = CreateFileW(v61, 0x80000000, 1u, 0, 3u, 0x88000006, 0);
                                  if ( FileW != (HANDLE)-1LL )
                                    break;
                                  v92 = GetLastError();
                                  if ( v92 == 32 )
                                  {
                                    Sleep(*((_DWORD *)qword_180041408 + v62));
                                    v62 = (unsigned int)(v62 + 1);
                                    if ( *((_DWORD *)qword_180041408 + v62) )
                                      continue;
                                  }
                                  SetLastError(v92);
                                  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
                                  {
                                    WPP_SF_dSD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v93, v94, v62, (__int64)v61, v92);
                                  }
                                  LODWORD(LastError) = GetLastError();
                                  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                                  {
                                    WPP_SF_sDsd(
                                      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                                      v95,
                                      (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
                                      (unsigned int)"dwLastError",
                                      LastError,
                                      (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
                                      124);
                                  }
                                  break;
                                }
                                LocalFree(v61);
                                if ( !(_DWORD)LastError )
                                {
                                  CloseHandle(FileW);
                                  goto LABEL_109;
                                }
                                if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 0x10) != 0 )
                                {
                                  v115 = 0x80000000;
                                  *(_QWORD *)v123 = L"Preferred";
                                  *(_QWORD *)&v123[8] = 20;
                                  *(_QWORD *)&v123[16] = &v115;
                                  v124 = 4;
                                  McGenEventWrite_EtwEventWriteTransfer(
                                    v64,
                                    (unsigned int)ETW_LOG_MASTERKEY_FILE_OPEN_IN_STORAGE_FAILED,
                                    v65,
                                    3,
                                    (__int64)v122);
                                }
                                v55 = a5;
                              }
                              else
                              {
                                LODWORD(LastError) = 8;
                              }
                              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                              {
                                WPP_SF_sDsd(
                                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                                  v60,
                                  (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
                                  (unsigned int)"dwLastError",
                                  LastError,
                                  (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
                                  217);
                              }
                              if ( v118 )
                                LODWORD(LastError) = DPAPICreateNestedDirectories(
                                                       *v55,
                                                       (unsigned __int16 *)((char *)*v55 + v50 + 2));
                              if ( !(_DWORD)LastError )
                              {
LABEL_109:
                                v5 = (HLOCAL *)a5;
                                if ( !v119 )
                                {
                                  if ( *a5 )
                                  {
                                    do
                                      ++v36;
                                    while ( (*a5)[v36] );
                                  }
                                  else
                                  {
                                    LODWORD(v36) = 0;
                                  }
                                  v66 = 2LL * (unsigned int)(v36 + 1);
                                  v67 = LocalAlloc(0, v66);
                                  v68 = v110;
                                  *((_QWORD *)v110 + 5) = v67;
                                  if ( v67 )
                                    memcpy_0(v67, *a5, v66);
                                  else
                                    LODWORD(LastError) = 8;
                                  goto LABEL_114;
                                }
LABEL_162:
                                v68 = v110;
LABEL_114:
                                if ( *v68 != 624 )
                                  goto LABEL_19;
                                if ( v68[4] || *((_QWORD *)v68 + 3) )
                                {
                                  if ( RevertToSelf() )
                                    goto LABEL_19;
                                  v69 = GetLastError();
                                  v70 = 858;
                                  goto LABEL_119;
                                }
                                v108 = (void *)*((_QWORD *)v68 + 1);
                                if ( v108 )
                                {
                                  v69 = RpcRevertToSelfEx(v108);
                                  if ( v69 )
                                  {
                                    v70 = 872;
LABEL_119:
                                    v71 = v69;
LABEL_120:
                                    DebugTraceError(
                                      v71,
                                      "dwLastError",
                                      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
                                      v70);
                                  }
                                }
LABEL_19:
                                if ( hMem )
                                  LocalFree(hMem);
                                if ( !(_DWORD)LastError )
                                  return (unsigned int)LastError;
                                goto LABEL_191;
                              }
                            }
                            else
                            {
                              LODWORD(LastError) = 0;
                            }
                          }
                          else
                          {
                            LODWORD(LastError) = 1011;
                          }
LABEL_161:
                          v5 = (HLOCAL *)a5;
                          goto LABEL_162;
                        }
                        v40 = (void *)*((_QWORD *)v7 + 3);
                        if ( v40 )
                        {
                          if ( SetThreadToken(0, v40) )
                            goto LABEL_80;
                          LastError = GetLastError();
                          DebugTraceError(
                            LastError,
                            "dwLastError",
                            "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
                            752);
                          if ( !(_DWORD)LastError )
                            goto LABEL_80;
                          v9 = LastError;
                        }
                        else
                        {
                          v105 = (void *)*((_QWORD *)v7 + 1);
                          if ( v105 )
                          {
                            v106 = RpcImpersonateClient(v105);
                            v9 = v106;
                            if ( !v106 )
                              goto LABEL_80;
                            DebugTraceError(
                              v106,
                              "dwLastError",
                              "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
                              768);
                            LODWORD(LastError) = v9;
                          }
                        }
                        DebugTraceError(
                          v9,
                          "dwLastError",
                          "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
                          825);
                      }
LABEL_136:
                      DebugTraceError(
                        (unsigned int)LastError,
                        "dwLastError",
                        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
                        1575);
LABEL_137:
                      v5 = (HLOCAL *)a5;
                      goto LABEL_19;
                    }
                    v103 = GetLastError();
                    v104 = 858;
                  }
                  else
                  {
                    v102 = (void *)*((_QWORD *)v7 + 1);
                    if ( !v102 )
                      goto LABEL_66;
                    v103 = RpcRevertToSelfEx(v102);
                    if ( !v103 )
                      goto LABEL_66;
                    v104 = 872;
                  }
                  DebugTraceError(
                    v103,
                    "dwLastError",
                    "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
                    v104);
                  goto LABEL_66;
                }
                v22 = hObject;
              }
              TokenInformationLength[0] = 256;
              v23 = 0;
              v24 = (PSID *)TokenInformation;
              if ( !GetTokenInformation(v22, TokenUser, TokenInformation, 0x100u, TokenInformationLength)
                && GetLastError() == 122 )
              {
                v23 = LocalAlloc(0x40u, TokenInformationLength[0]);
                if ( !v23 )
                  goto LABEL_36;
                if ( !GetTokenInformation(hObject, TokenUser, v23, TokenInformationLength[0], TokenInformationLength) )
                {
LABEL_35:
                  LocalFree(v23);
LABEL_36:
                  v17 = (unsigned int)StringSid;
                  v9 = 87;
                  goto LABEL_37;
                }
                v24 = (PSID *)v23;
              }
              LengthSid = GetLengthSid(*v24);
              v26 = LocalAlloc(0x40u, LengthSid);
              v27 = v26;
              if ( v26 )
              {
                if ( CopySid(LengthSid, v26, *v24) )
                {
                  v21 = v27;
                  v11 = 1;
                }
                else
                {
                  LocalFree(v27);
                }
              }
              if ( !v23 )
                goto LABEL_36;
              goto LABEL_35;
            }
            v14 = (void *)*((_QWORD *)v7 + 3);
            if ( v14 )
            {
              if ( SetThreadToken(0, v14) )
                goto LABEL_27;
              LODWORD(LastError) = GetLastError();
              DebugTraceError(
                (unsigned int)LastError,
                "dwLastError",
                "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
                752);
              if ( !(_DWORD)LastError )
                goto LABEL_27;
              v15 = LastError;
            }
            else
            {
              v100 = (void *)*((_QWORD *)v7 + 1);
              if ( v100 )
              {
                v101 = RpcImpersonateClient(v100);
                v15 = v101;
                if ( !v101 )
                  goto LABEL_27;
                DebugTraceError(
                  v101,
                  "dwLastError",
                  "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
                  768);
                LODWORD(LastError) = v15;
              }
              else
              {
                v15 = 87;
              }
            }
            v70 = 825;
            v71 = v15;
            goto LABEL_120;
          }
          v17 = 13;
          v76 = xmmword_18004290A;
          v127 = 0x32002D0032LL;
        }
LABEL_150:
        LODWORD(LastError) = 8;
        Src = 83;
        v36 = -1;
        v126 = v76;
        goto LABEL_139;
      }
      v76 = xmmword_1800428CA;
    }
    v17 = 9;
    goto LABEL_150;
  }
  v98 = -1;
  do
    v38 = *(_WORD *)(v10 + 2 * v98++ + 2) == 0;
  while ( !v38 );
  v99 = (unsigned __int16 *)LocalAlloc(0, 2LL * (unsigned int)(v98 + 1));
  *a5 = v99;
  if ( !v99 )
    return 8;
  memcpy_0(v99, *((const void **)v7 + 5), 2LL * (unsigned int)(v98 + 1));
  return 0;
}

```

## disassembly

```asm
0x180006c60  mov     r11, rsp
0x180006c63  push    rbp
0x180006c64  push    rsi
0x180006c65  push    rdi
0x180006c66  push    r13
0x180006c68  push    r14
0x180006c6a  lea     rbp, [r11-778h]
0x180006c71  sub     rsp, 850h
0x180006c78  movaps  xmmword ptr [r11-48h], xmm6
0x180006c7d  movaps  xmmword ptr [r11-58h], xmm7
0x180006c82  mov     rax, cs:__security_cookie
0x180006c89  xor     rax, rsp
0x180006c8c  mov     [rbp+770h+var_60], rax
0x180006c93  mov     r14, [rbp+770h+arg_20]
0x180006c9a  xor     esi, esi
0x180006c9c  movsd   xmm0, qword ptr cs:aMicrosoftProte+20h; "ct\\"
0x180006ca4  mov     rdi, rdx
0x180006ca7  movsd   xmm1, qword ptr cs:aUser; "\\User"
0x180006caf  mov     r13, rcx
0x180006cb2  mov     eax, dword ptr cs:aUser+8; "r"
0x180006cb8  mov     [rbp+770h+var_7E4], r9d
0x180006cbc  mov     [rsp+870h+var_7F8], r8d
0x180006cc1  mov     [rbp+770h+var_7E0], rdx
0x180006cc5  mov     [rsp+870h+var_820], rcx
0x180006cca  mov     qword ptr [rsp+870h+var_830], r14
0x180006ccf  movsd   [rbp+770h+var_7A8], xmm0
0x180006cd4  movsd   [rbp+770h+var_7D8], xmm1
0x180006cd9  mov     [rbp+770h+var_7D0], eax
0x180006cdc  movups  xmm6, xmmword ptr cs:aMicrosoftProte+10h; "ft\\Protect\\"
0x180006ce3  movups  xmm7, xmmword ptr cs:aMicrosoftProte; "\\Microsoft\\Protect\\"
0x180006cea  mov     [r14], rsi
0x180006ced  movups  [rbp+770h+var_7B8], xmm6
0x180006cf1  test    rcx, rcx
0x180006cf4  jz      loc_180007B95
0x180006cfa  mov     [r11+18h], rbx
0x180006cfe  mov     rbx, cs:WPP_GLOBAL_Control
0x180006d05  mov     [r11-30h], r12
0x180006d09  lea     r12, WPP_GLOBAL_Control
0x180006d10  mov     [r11-38h], r15
0x180006d14  cmp     rbx, r12
0x180006d17  jnz     loc_1800077C8
0x180006d1d  mov     r15d, 57h ; 'W'
0x180006d23  test    rdi, rdi
0x180006d26  jnz     loc_1800078A1
0x180006d2c  mov     rax, [r13+28h]
0x180006d30  test    rax, rax
0x180006d33  jnz     loc_180007B58
0x180006d39  xor     edx, edx; Val
0x180006d3b  mov     [rsp+870h+hMem], rsi
0x180006d40  mov     r8d, 20Ah; Size
0x180006d46  lea     rcx, [rbp+770h+Src]; void *
0x180006d4a  call    memset_0
0x180006d4f  mov     ecx, [r13+0]
0x180006d53  cmp     ecx, 270h
0x180006d59  jnz     loc_180006E17
0x180006d5f  mov     r12d, esi
0x180006d62  mov     eax, [r13+30h]
0x180006d66  mov     [rsp+870h+cchSize], esi
0x180006d6a  cmp     [r13+10h], esi
0x180006d6e  jnz     loc_18000779D
0x180006d74  cmp     eax, 12h
0x180006d77  jz      loc_18000779D
0x180006d7d  cmp     eax, 13h
0x180006d80  jz      loc_180007C07
0x180006d86  cmp     eax, 14h
0x180006d89  jz      loc_180007C4C
0x180006d8f  cmp     eax, 5Ah ; 'Z'
0x180006d92  jz      loc_180007C58
0x180006d98  cmp     eax, 5Bh ; '['
0x180006d9b  jz      loc_180007C77
0x180006da1  mov     edi, r15d
0x180006da4  cmp     ecx, ecx
0x180006da6  jnz     short loc_180006E1A
0x180006da8  cmp     [r13+10h], esi
0x180006dac  jnz     loc_180006E99
0x180006db2  mov     ecx, eax
0x180006db4  test    eax, eax
0x180006db6  jnz     loc_180006E84
0x180006dbc  mov     rdx, [r13+18h]; Token
0x180006dc0  test    rdx, rdx
0x180006dc3  jz      loc_180007C96
0x180006dc9  xor     ecx, ecx; Thread
0x180006dcb  call    cs:__imp_SetThreadToken
0x180006dd2  nop     dword ptr [rax+rax+00h]
0x180006dd7  test    eax, eax
0x180006dd9  jnz     loc_180006EDF
0x180006ddf  call    cs:__imp_GetLastError
0x180006de6  nop     dword ptr [rax+rax+00h]
0x180006deb  mov     r9d, 2F0h
0x180006df1  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180006df8  mov     ecx, eax
0x180006dfa  lea     rdx, aDwlasterror; "dwLastError"
0x180006e01  mov     edi, eax
0x180006e03  call    DebugTraceError
0x180006e08  test    edi, edi
0x180006e0a  jz      loc_180006EDF
0x180006e10  mov     ebx, edi
0x180006e12  jmp     loc_180007CD7
0x180006e17  mov     edi, r15d
0x180006e1a  mov     rax, [rsp+870h+hMem]
0x180006e1f  test    rax, rax
0x180006e22  jz      short loc_180006E33
0x180006e24  mov     rcx, rax; hMem
0x180006e27  call    cs:__imp_LocalFree
0x180006e2e  nop     dword ptr [rax+rax+00h]
0x180006e33  test    edi, edi
0x180006e35  jnz     loc_180007A78
0x180006e3b  mov     eax, edi
0x180006e3d  mov     r12, [rsp+848h]
0x180006e45  mov     rbx, [rsp+870h+arg_10]
0x180006e4d  mov     r15, [rsp+870h+var_30]
0x180006e55  mov     rcx, [rbp+770h+var_60]
0x180006e5c  xor     rcx, rsp; StackCookie
0x180006e5f  call    __security_check_cookie
0x180006e64  movaps  xmm6, [rsp+870h+var_48+8]
0x180006e6c  movaps  xmm7, [rsp+870h+var_58+8]
0x180006e74  add     rsp, 850h
0x180006e7b  pop     r14
0x180006e7d  pop     r13
0x180006e7f  pop     rdi
0x180006e80  pop     rsi
0x180006e81  pop     rbp
0x180006e82  retn
0x180006e84  add     eax, 0FFFFFFA6h
0x180006e87  cmp     eax, 1
0x180006e8a  jbe     loc_180006DBC
0x180006e90  cmp     ecx, 63h ; 'c'
0x180006e93  jz      loc_180006DBC
0x180006e99  mov     ecx, 2; ImpersonationLevel
0x180006e9e  call    cs:__imp_ImpersonateSelf
0x180006ea5  nop     dword ptr [rax+rax+00h]
0x180006eaa  test    eax, eax
0x180006eac  jnz     short loc_180006EDF
0x180006eae  call    cs:__imp_GetLastError
0x180006eb5  nop     dword ptr [rax+rax+00h]
0x180006eba  mov     r9d, 330h
0x180006ec0  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180006ec7  mov     ecx, eax
0x180006ec9  lea     rdx, aDwlasterror; "dwLastError"
0x180006ed0  mov     edi, eax
0x180006ed2  call    DebugTraceError
0x180006ed7  test    edi, edi
0x180006ed9  jnz     loc_180006E1A
0x180006edf  mov     r14d, 104h
0x180006ee5  mov     [rsp+870h+TokenHandle], rsi
0x180006eea  mov     ebx, esi
0x180006eec  mov     dword ptr [rbp+770h+StringSid], r14d
0x180006ef0  mov     [rbp+770h+var_7E8], ebx
0x180006ef3  call    cs:__imp_GetCurrentThread
0x180006efa  nop     dword ptr [rax+rax+00h]
0x180006eff  lea     r9, [rsp+870h+TokenHandle]; TokenHandle
0x180006f04  mov     edx, 8; DesiredAccess
0x180006f09  mov     rcx, rax; ThreadHandle
0x180006f0c  mov     r8d, 1; OpenAsSelf
0x180006f12  call    cs:__imp_OpenThreadToken
0x180006f19  nop     dword ptr [rax+rax+00h]
0x180006f1e  test    eax, eax
0x180006f20  jz      loc_1800070C2
0x180006f26  mov     rdi, [rsp+870h+TokenHandle]
0x180006f2b  mov     r13, rsi
0x180006f2e  mov     [rsp+870h+TokenInformationLength], esi
0x180006f32  mov     [rsp+870h+hObject], rsi
0x180006f37  test    rdi, rdi
0x180006f3a  jz      loc_180007729
0x180006f40  mov     rcx, rdi; TokenHandle
0x180006f43  mov     [rsp+870h+hObject], rcx
0x180006f48  lea     rax, [rsp+870h+TokenInformationLength]
0x180006f4d  mov     [rsp+870h+TokenInformationLength], 100h
0x180006f55  mov     r9d, 100h; TokenInformationLength
0x180006f5b  mov     [rsp+870h+ReturnLength], rax; ReturnLength
0x180006f60  lea     r8, [rbp+770h+TokenInformation]; TokenInformation
0x180006f67  mov     edx, 1; TokenInformationClass
0x180006f6c  mov     r14, rsi
0x180006f6f  lea     r15, [rbp+770h+TokenInformation]
0x180006f76  call    cs:__imp_GetTokenInformation
0x180006f7d  nop     dword ptr [rax+rax+00h]
0x180006f82  test    eax, eax
0x180006f84  jz      loc_18000763F
0x180006f8a  mov     rcx, [r15]; pSid
0x180006f8d  call    cs:__imp_GetLengthSid
0x180006f94  nop     dword ptr [rax+rax+00h]
0x180006f99  mov     edx, eax; uBytes
0x180006f9b  mov     ecx, 40h ; '@'; uFlags
0x180006fa0  mov     esi, eax
0x180006fa2  call    cs:__imp_LocalAlloc
0x180006fa9  nop     dword ptr [rax+rax+00h]
0x180006fae  mov     rbx, rax
0x180006fb1  test    rax, rax
0x180006fb4  jz      short loc_180006FDB
0x180006fb6  mov     r8, [r15]; pSourceSid
0x180006fb9  mov     rdx, rax; pDestinationSid
0x180006fbc  mov     ecx, esi; nDestinationSidLength
0x180006fbe  call    cs:__imp_CopySid
0x180006fc5  nop     dword ptr [rax+rax+00h]
0x180006fca  test    eax, eax
0x180006fcc  jz      loc_180007B02
0x180006fd2  mov     r13, rbx
0x180006fd5  mov     r12d, 1
0x180006fdb  test    r14, r14
0x180006fde  jz      short loc_180006FEF
0x180006fe0  mov     rcx, r14; hMem
0x180006fe3  call    cs:__imp_LocalFree
0x180006fea  nop     dword ptr [rax+rax+00h]
0x180006fef  mov     r14d, dword ptr [rbp+770h+StringSid]
0x180006ff3  mov     r15d, 57h ; 'W'
0x180006ff9  mov     rcx, [rsp+870h+hObject]; hObject
0x180006ffe  test    rcx, rcx
0x180007001  jz      short loc_18000700C
0x180007003  cmp     rcx, rdi
0x180007006  jnz     loc_180007CEB
0x18000700c  test    r12d, r12d
0x18000700f  jz      loc_180007D10
0x180007015  xor     esi, esi
0x180007017  lea     rdx, [rbp+770h+StringSid]; StringSid
0x18000701b  mov     rcx, r13; Sid
0x18000701e  mov     [rbp+770h+StringSid], rsi
0x180007022  mov     ebx, esi
0x180007024  call    cs:__imp_ConvertSidToStringSidW
0x18000702b  nop     dword ptr [rax+rax+00h]
0x180007030  mov     r10, [rbp+770h+StringSid]
0x180007034  test    eax, eax
0x180007036  jz      short loc_180007086
0x180007038  mov     ecx, 7FFFFFFEh
0x18000703d  lea     r9, [rbp+770h+Src]
0x180007041  mov     rdx, r10
0x180007044  mov     r8d, 105h
0x18000704a  nop     word ptr [rax+rax+00h]
0x180007050  test    rcx, rcx
0x180007053  jz      short loc_180007072
0x180007055  movzx   eax, word ptr [rdx]
0x180007058  test    ax, ax
0x18000705b  jz      short loc_180007072
0x18000705d  mov     [r9], ax
0x180007061  add     rdx, 2
0x180007065  add     r9, 2
0x180007069  dec     rcx
0x18000706c  sub     r8, 1
0x180007070  jnz     short loc_180007050
0x180007072  test    r8, r8
0x180007075  lea     rdx, [r9-2]
0x180007079  cmovnz  rdx, r9
0x18000707d  mov     [rdx], si
0x180007080  jnz     loc_180007CFC
0x180007086  test    r10, r10
0x180007089  jz      short loc_18000709A
0x18000708b  mov     rcx, r10; hMem
0x18000708e  call    cs:__imp_LocalFree
0x180007095  nop     dword ptr [rax+rax+00h]
0x18000709a  test    ebx, ebx
0x18000709c  jnz     loc_180007D06
0x1800070a2  mov     ebx, esi
0x1800070a4  test    r13, r13
0x1800070a7  jz      short loc_1800070B8
0x1800070a9  mov     rcx, r13; hMem
0x1800070ac  call    cs:__imp_LocalFree
0x1800070b3  nop     dword ptr [rax+rax+00h]
0x1800070b8  mov     r12d, [rsp+870h+cchSize]
0x1800070bd  mov     r13, [rsp+870h+var_820]
0x1800070c2  mov     rcx, [rsp+870h+TokenHandle]; hObject
0x1800070c7  test    rcx, rcx
0x1800070ca  jz      short loc_1800070D8
0x1800070cc  call    cs:__imp_CloseHandle
0x1800070d3  nop     dword ptr [rax+rax+00h]
0x1800070d8  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800070df  test    ebx, ebx
0x1800070e1  jz      short loc_180007100
0x1800070e3  lea     rcx, [rbp+770h+Src]
0x1800070e7  mov     rax, rsi
0x1800070ea  nop     word ptr [rax+rax+00h]
0x1800070f0  cmp     word ptr [rcx+rax*2+2], 0
0x1800070f6  lea     rax, [rax+1]
0x1800070fa  jnz     short loc_1800070F0
0x1800070fc  lea     r14d, [rax+1]
0x180007100  cmp     dword ptr [r13+0], 270h
0x180007108  jnz     short loc_180007130
0x18000710a  cmp     dword ptr [r13+10h], 0
0x18000710f  jnz     short loc_18000711C
0x180007111  cmp     qword ptr [r13+18h], 0
0x180007116  jz      loc_180007D18
0x18000711c  call    cs:__imp_RevertToSelf
0x180007123  nop     dword ptr [rax+rax+00h]
0x180007128  test    eax, eax
0x18000712a  jz      loc_180007D41
0x180007130  mov     edi, 8
0x180007135  test    ebx, ebx
0x180007137  jnz     loc_1800076D5
0x18000713d  mov     rbx, cs:WPP_GLOBAL_Control
0x180007144  test    edi, edi
0x180007146  jnz     loc_180007D6D
0x18000714c  lea     eax, [r12-1]
0x180007151  mov     [rsp+870h+hObject], rax
0x180007156  lea     r12, WPP_GLOBAL_Control
0x18000715d  cmp     rbx, r12
0x180007160  jnz     loc_1800077F9
0x180007166  mov     rax, [rsp+870h+hMem]
0x18000716b  mov     [rsp+870h+hMem], rax
0x180007170  cmp     dword ptr [r13+0], 270h
0x180007178  mov     edi, r15d
0x18000717b  jnz     loc_1800076AD
0x180007181  cmp     dword ptr [r13+10h], 0
  ... truncated ...
```
