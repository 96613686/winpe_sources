# GetProfileSidString(void *,ushort * *)

- ea: `0x18000e200`
- end: `0x18000f096`
- name: `?GetProfileSidString@@YAJPEAXPEAPEAG@Z`
- size: `3734`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f330`
- `0x180039160`

## callees

- `0x180005370`
- `0x18000b020`
- `0x18000dc10`
- `0x18000e1a0`
- `0x18000e200`
- `0x180011c00`
- `0x18001214c`
- `0x1800130d0`
- `0x180017520`
- `0x18001a0f0`
- `0x18001e690`
- `0x180026e5c`
- `0x180030ad0`
- `0x18003c870`
- `0x18003fff4`
- `0x180040bcc`
- `0x1800516b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e263`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e2e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e7b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e941`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000eae0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ebad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ec1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e263`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e2e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e7b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e941`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000eae0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ebad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ec1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e33c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e39e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e5b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e5ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e6e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e778`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e976`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e33c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e39e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e5b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e5ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e6e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e778`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e976`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ed30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e249`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e2ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e328`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e38a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e59f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e5eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e65c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e6cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e764`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e92d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e962`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e99f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e9ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eacc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ed1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ee0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ef17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e249`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e2ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e328`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e38a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e59f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e5eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e65c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e6cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e764`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e92d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e962`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e99f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e9ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eacc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ed1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ee0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ef17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000efe1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000efe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efc2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e3ec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e418`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e440`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e468`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e490`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e3ec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e418`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e440`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e468`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e490`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e648`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e89e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f038`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e648`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e89e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f038`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e8f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ea58`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e8f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ea58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e6bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e752`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e986`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000efd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e6bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e752`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e986`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000efd3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ecc7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ecfa`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ecc7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ecfa`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e306`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e306`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e2bd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e2bd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e29a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000edd1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e29a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000edd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e6f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e79a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e6f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e79a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000e367`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000e367`

## string_xrefs

- `0x18000e5d5`: `onecore\internal\ds\inc\profiles\sid.h`
- `0x18000e72b`: `onecore\internal\ds\inc\profiles\sid.h`
- `0x18000e9d6`: `onecore\internal\ds\inc\profiles\sid.h`
- `0x18000ee94`: `onecore\internal\ds\inc\profiles\sid.h`
- `0x18000e6a2`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18000eefc`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18000ef42`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetProfileSidString(HANDLE TokenHandle, unsigned __int16 **a2)
{
  HANDLE v2; // r13
  const WCHAR *v3; // r15
  unsigned __int64 v4; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rdx
  WCHAR *v7; // rsi
  void *v8; // r14
  int Error; // ebx
  DWORD LengthSid; // ebx
  HANDLE v11; // rax
  void *v12; // rax
  void *v13; // r15
  HANDLE v14; // rax
  int v15; // ebx
  HANDLE v16; // rax
  __int64 v17; // rbx
  unsigned int v18; // r13d
  int v19; // esi
  int v20; // eax
  WCHAR *v21; // r12
  WCHAR *v22; // r15
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rbx
  unsigned __int64 v25; // rsi
  int v26; // r14d
  HANDLE v27; // rax
  int v28; // ebx
  HANDLE v29; // rax
  HANDLE v30; // rcx
  HLOCAL v31; // rsi
  unsigned __int16 **v32; // r14
  unsigned __int64 v33; // rbx
  HANDLE v34; // rax
  unsigned __int64 v36; // r9
  __int64 v37; // rdx
  HANDLE v38; // rax
  const unsigned __int16 *v39; // rcx
  unsigned __int64 v40; // r8
  __int64 v41; // r9
  unsigned __int16 *v42; // r10
  unsigned __int16 v43; // ax
  __int64 v44; // rbx
  bool v45; // cf
  BYTE *v46; // r15
  int v47; // eax
  HKEY v48; // r14
  BYTE *v49; // rbx
  LSTATUS Value; // eax
  signed int v51; // esi
  unsigned int v52; // ebx
  HANDLE v53; // rax
  HANDLE v54; // rax
  HANDLE v55; // rcx
  HANDLE v56; // rax
  LSTATUS v57; // eax
  __int64 v58; // r14
  __int64 v59; // rax
  HANDLE v60; // rax
  WCHAR *v61; // rax
  WCHAR *v62; // rcx
  WCHAR *v63; // rdx
  WCHAR v64; // ax
  HANDLE v65; // rax
  HANDLE v66; // rax
  WCHAR *v67; // rax
  WCHAR *v68; // r8
  __int64 v69; // rdx
  const WCHAR *v70; // rcx
  WCHAR v71; // ax
  WCHAR *v72; // rax
  WCHAR *v73; // rdx
  __int64 v74; // r9
  const WCHAR *v75; // rcx
  __int64 v76; // r8
  __int64 v77; // r10
  WCHAR *v78; // r11
  WCHAR v79; // ax
  __int64 v80; // rbx
  DWORD v81; // eax
  DWORD v82; // r12d
  WCHAR *v83; // rax
  WCHAR *v84; // r13
  DWORD v85; // eax
  DWORD v86; // r14d
  HANDLE v87; // rax
  BOOL TokenInformation; // eax
  HANDLE v89; // rax
  int v90; // eax
  int OldSidString; // eax
  HANDLE v92; // rax
  __int64 v93; // rdx
  int v94; // eax
  unsigned int v95; // ebx
  int ReturnLength; // [rsp+20h] [rbp-69h]
  int ReturnLengtha; // [rsp+20h] [rbp-69h]
  LPVOID lpMem; // [rsp+38h] [rbp-51h] BYREF
  __int64 v99; // [rsp+40h] [rbp-49h]
  __int64 v100; // [rsp+48h] [rbp-41h]
  HLOCAL hMem[3]; // [rsp+50h] [rbp-39h] BYREF
  BYTE *v102; // [rsp+68h] [rbp-21h] BYREF
  __int64 v103; // [rsp+70h] [rbp-19h]
  __int64 v104; // [rsp+78h] [rbp-11h]
  HKEY phkResult; // [rsp+80h] [rbp-9h] BYREF
  LPCWSTR v106[11]; // [rsp+88h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  HKEY TokenInformationLength; // [rsp+100h] [rbp+77h] BYREF
  LPWSTR StringSid; // [rsp+108h] [rbp+7Fh] BYREF

  v2 = TokenHandle;
  *a2 = 0;
  v3 = 0;
  hMem[0] = 0;
  v4 = -1;
  hMem[1] = (HLOCAL)-1LL;
  hMem[2] = (HLOCAL)-1LL;
  LODWORD(TokenInformationLength) = 200;
  ProcessHeap = GetProcessHeap();
  v7 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0xC8u);
  StringSid = v7;
  if ( !v7 )
  {
    v15 = -2147024882;
    goto LABEL_20;
  }
  v8 = 0;
  if ( GetTokenInformation(v2, TokenUser, v7, (DWORD)TokenInformationLength, (PDWORD)&TokenInformationLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      Error = ResultFromHeapReAlloc(v7, (unsigned int)TokenInformationLength, (void **)&StringSid);
      v7 = StringSid;
      if ( Error < 0 )
        goto LABEL_10;
      TokenInformation = GetTokenInformation(
                           v2,
                           TokenUser,
                           StringSid,
                           (DWORD)TokenInformationLength,
                           (PDWORD)&TokenInformationLength);
      Error = ResultFromWin32Bool(TokenInformation);
    }
  }
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*(PSID *)v7);
    LODWORD(TokenInformationLength) = LengthSid;
    v11 = GetProcessHeap();
    v12 = HeapAlloc(v11, 8u, LengthSid);
    v13 = v12;
    if ( !v12 )
    {
      Error = -2147024882;
      goto LABEL_9;
    }
    if ( CopySid((DWORD)TokenInformationLength, v12, *(PSID *)v7) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        ResultFromHeapFree(v13);
        goto LABEL_9;
      }
    }
    v8 = v13;
LABEL_9:
    v3 = (const WCHAR *)hMem[0];
  }
LABEL_10:
  if ( v7 )
  {
    v14 = GetProcessHeap();
    if ( !HeapFree(v14, 0, v7) )
      ResultFromKnownLastError();
  }
  if ( Error < 0 )
    goto LABEL_184;
  StringSid = 0;
  if ( ConvertSidToStringSidW(v8, &StringSid) )
  {
    v15 = 0;
  }
  else
  {
    v15 = ResultFromKnownLastError();
    if ( v15 < 0 )
      goto LABEL_17;
  }
  v3 = StringSid;
  hMem[0] = StringSid;
LABEL_17:
  if ( v8 )
  {
    v16 = GetProcessHeap();
    if ( !HeapFree(v16, 0, v8) )
      ResultFromKnownLastError();
  }
LABEL_20:
  if ( v15 >= 0 )
  {
    v106[1] = (LPCWSTR)-1LL;
    v106[2] = (LPCWSTR)-1LL;
    lpMem = 0;
    v99 = 0;
    v100 = 0;
    if ( CompareStringOrdinal(v3, -1, L"S-1-5-18", -1, 1) == 2
      || CompareStringOrdinal(v3, -1, L"S-1-5-19", -1, 1) == 2
      || CompareStringOrdinal(v3, -1, L"S-1-5-20", -1, 1) == 2
      || CompareStringOrdinal(v3, -1, L"S-1-5-93-2-1", -1, 1) == 2
      || CompareStringOrdinal(v3, -1, L"S-1-5-93-2-2", -1, 1) == 2 )
    {
      TokenInformationLength = 0;
      v17 = 57;
      v18 = -2147024362;
      if ( is_mul_ok(0x39u, 2u) )
      {
        v66 = GetProcessHeap();
        v67 = (WCHAR *)HeapAlloc(v66, 0, 0x72u);
        v68 = v67;
        if ( v67 )
        {
          v100 = 57;
          lpMem = v67;
          *v67 = 0;
          v69 = 56;
          v70 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList";
          v19 = 0;
          while ( v69 )
          {
            v71 = *v70;
            if ( !*v70 )
              break;
            ++v70;
            *v68++ = v71;
            --v69;
            if ( !--v17 )
            {
              --v68;
              break;
            }
          }
          *v68 = 0;
          v99 = 56;
        }
        else
        {
          v19 = -2147024882;
        }
      }
      else
      {
        v19 = -2147024362;
      }
LABEL_29:
      if ( v19 < 0 )
      {
        v36 = (unsigned int)v19;
        v37 = 128;
      }
      else
      {
        v20 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
                &lpMem,
                L"\\%s",
                v3);
        if ( v20 >= 0 )
        {
          v21 = 0;
          v106[0] = 0;
          v22 = (WCHAR *)lpMem;
          if ( lpMem )
          {
            v102 = 0;
            v103 = 0;
            v104 = 0;
            v23 = v99;
            if ( v99 == -1 )
            {
              v23 = -1;
              do
                ++v23;
              while ( *((_WORD *)lpMem + v23) );
            }
            v24 = -1;
            do
              ++v24;
            while ( *((_WORD *)lpMem + v24) );
            if ( v23 == -1 )
            {
              v23 = v24;
            }
            else if ( v23 < v24 )
            {
              v24 = v23;
            }
            v25 = v23 + 1;
            if ( v23 + 1 >= v23 && (TokenInformationLength = 0, is_mul_ok(v25, 2u)) )
            {
              v60 = GetProcessHeap();
              v61 = (WCHAR *)HeapAlloc(v60, 0, 2 * v25);
              if ( v61 )
              {
                v21 = v61;
                *v61 = 0;
                v26 = 0;
                if ( v25 )
                {
                  if ( v24 > 0x7FFFFFFE || v25 > 0x7FFFFFFF )
                  {
                    *v61 = 0;
                  }
                  else
                  {
                    v62 = v22;
                    v63 = v61;
                    while ( v24 )
                    {
                      v64 = *v62;
                      if ( !*v62 )
                        break;
                      ++v62;
                      *v63++ = v64;
                      --v24;
                      if ( !--v25 )
                      {
                        --v63;
                        break;
                      }
                    }
                    *v63 = 0;
                  }
                }
              }
              else
              {
                v26 = -2147024882;
              }
            }
            else
            {
              v26 = -2147024362;
            }
            if ( v26 >= 0 )
            {
              v28 = v26;
              v106[0] = v21;
            }
            else
            {
              if ( v21 )
              {
                v27 = GetProcessHeap();
                HeapFree(v27, 0, v21);
              }
              v28 = v26;
              v21 = 0;
            }
            if ( v28 >= 0 )
            {
              v65 = GetProcessHeap();
              HeapFree(v65, 0, v22);
              goto LABEL_51;
            }
          }
          else
          {
            v26 = -2147023728;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x82,
            (unsigned int)"onecore\\internal\\ds\\inc\\profiles\\sid.h",
            (const char *)(unsigned int)v26,
            ReturnLengtha);
          if ( v22 )
          {
            v29 = GetProcessHeap();
            HeapFree(v29, 0, v22);
          }
          if ( v26 >= 0 )
          {
LABEL_51:
            TokenInformationLength = 0;
            if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v21, 0, 0x20019u, &TokenInformationLength) )
              goto LABEL_52;
            if ( (int)Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Concat(
                        v106,
                        L".bak",
                        4) < 0 )
            {
              v21 = (WCHAR *)v106[0];
            }
            else
            {
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                &TokenInformationLength,
                0);
              v21 = (WCHAR *)v106[0];
              if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v106[0], 0, 0x20019u, &TokenInformationLength) )
              {
LABEL_52:
                v30 = GetProcessHeap();
                v31 = hMem[0];
                do
                  ++v4;
                while ( *((_WORD *)hMem[0] + v4) );
                v32 = a2;
                *a2 = 0;
                v33 = v4 + 1;
                if ( v4 + 1 < v4 || !is_mul_ok(v33, 2u) )
                  goto LABEL_56;
                v6 = (unsigned __int16 *)HeapAlloc(v30, 0, 2 * v33);
                *a2 = v6;
                if ( !v6 )
                {
                  v18 = -2147024882;
LABEL_56:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x124,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
                    (const char *)v18,
                    ReturnLength);
                  if ( TokenInformationLength )
                    RegCloseKey(TokenInformationLength);
                  if ( v21 )
                  {
                    v34 = GetProcessHeap();
                    HeapFree(v34, 0, v21);
                  }
                  if ( v31 )
                    LocalFree(v31);
                  return v18;
                }
                if ( v33 > 0x7FFFFFFF )
                {
                  *v6 = 0;
                }
                else if ( v4 >= 0x7FFFFFFF )
                {
                  if ( v4 != -1 )
                    *v6 = 0;
                }
                else
                {
                  v39 = (const unsigned __int16 *)v31;
                  if ( !v31 )
                  {
                    v39 = &qword_1800649D8;
                    v4 = 0;
                  }
                  if ( v33 )
                  {
                    v40 = v33;
                    v41 = 0;
                    v42 = v6;
                    while ( v4 )
                    {
                      v43 = *v39;
                      if ( !*v39 )
                        break;
                      ++v39;
                      *v6++ = v43;
                      --v4;
                      ++v41;
                      if ( !--v40 )
                      {
                        *(v6 - 1) = 0;
                        goto LABEL_87;
                      }
                    }
                    *v6 = 0;
                    v45 = v33 == v41;
                    v44 = v33 - v41;
                    if ( !v45 && v44 != 1 && (unsigned __int64)(2 * v44) > 2 )
                      memset_0(&v42[v41 + 1], 0, 2 * v44 - 2);
                  }
                }
                goto LABEL_87;
              }
            }
            v32 = a2;
            v31 = hMem[0];
LABEL_87:
            if ( TokenInformationLength )
              RegCloseKey(TokenInformationLength);
            goto LABEL_67;
          }
LABEL_66:
          v31 = hMem[0];
          v32 = a2;
LABEL_67:
          if ( v21 )
          {
            v38 = GetProcessHeap();
            HeapFree(v38, 0, v21);
          }
          v2 = TokenHandle;
          goto LABEL_70;
        }
        v36 = (unsigned int)v20;
        v37 = 129;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"onecore\\internal\\ds\\inc\\profiles\\sid.h",
        (const char *)v36,
        ReturnLengtha);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpMem);
      v21 = 0;
      goto LABEL_66;
    }
    v99 = -1;
    v100 = -1;
    v46 = 0;
    v102 = 0;
    v103 = 0;
    v104 = 0;
    phkResult = 0;
    v47 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\ProfileList", 0, 0x20019u, &phkResult);
    if ( v47 > 0 )
      v47 = (unsigned __int16)v47 | 0x80070000;
    v19 = -2147024362;
    if ( v47 < 0 )
      goto LABEL_102;
    v48 = phkResult;
    v49 = 0;
    LODWORD(StringSid) = 0;
    LODWORD(TokenInformationLength) = 0;
    Value = RegQueryValueExW(phkResult, L"RedirectionKey", 0, (LPDWORD)&StringSid, 0, (LPDWORD)&TokenInformationLength);
    v51 = Value;
    if ( Value > 0 )
      v51 = (unsigned __int16)Value | 0x80070000;
    if ( v51 >= 0 )
    {
      if ( (unsigned int)((_DWORD)StringSid - 1) <= 1
        && (_DWORD)TokenInformationLength
        && ((unsigned __int8)TokenInformationLength & 1) == 0 )
      {
        v52 = (unsigned int)TokenInformationLength;
        v53 = GetProcessHeap();
        v49 = (BYTE *)HeapAlloc(v53, 0, v52);
        if ( !v49 )
        {
          v51 = -2147024882;
          goto LABEL_100;
        }
        v57 = RegQueryValueExW(v48, L"RedirectionKey", 0, (LPDWORD)&StringSid, v49, (LPDWORD)&TokenInformationLength);
        v51 = v57;
        if ( v57 > 0 )
          v51 = (unsigned __int16)v57 | 0x80070000;
        if ( v51 < 0 )
          goto LABEL_100;
        v58 = ((unsigned int)TokenInformationLength >> 1) - 1;
        if ( (_DWORD)StringSid == 2 )
        {
          v81 = ExpandEnvironmentStringsW((LPCWSTR)v49, 0, 0);
          v82 = v81;
          if ( v81 )
          {
            v83 = (WCHAR *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(2LL * v81);
            v84 = v83;
            if ( !v83 )
            {
              v51 = -2147024882;
              goto LABEL_100;
            }
            v85 = ExpandEnvironmentStringsW((LPCWSTR)v49, v83, v82);
            v86 = v85;
            if ( !v85 || v85 > v82 )
            {
              v51 = -2147024774;
              v89 = GetProcessHeap();
              HeapFree(v89, 0, v84);
              goto LABEL_100;
            }
            v51 = 0;
            v87 = GetProcessHeap();
            HeapFree(v87, 0, v49);
            v49 = (BYTE *)v84;
            v58 = v86 - 1;
          }
        }
        if ( !*(_WORD *)&v49[2 * v58] )
        {
          v103 = 0;
          v104 = 0;
          if ( v49 )
          {
            v59 = (unsigned int)(v58 + 1);
            if ( (_DWORD)v58 != -1 )
            {
              v46 = v49;
              v102 = v49;
              v104 = (unsigned int)v59;
              v103 = v59 - 1;
              *(_WORD *)&v49[2 * (unsigned int)v59 - 2] = 0;
            }
          }
          v49 = 0;
          goto LABEL_100;
        }
      }
      v51 = -2147024883;
    }
LABEL_100:
    v54 = GetProcessHeap();
    HeapFree(v54, 0, v49);
    RegCloseKey(phkResult);
    if ( v51 >= 0 )
    {
      v90 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(
              &v102,
              &lpMem);
      v19 = v90;
      if ( v90 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"onecore\\internal\\ds\\inc\\profiles\\sid.h",
          (const char *)(unsigned int)v90,
          ReturnLengtha);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v102);
        v18 = -2147024362;
        v3 = (const WCHAR *)hMem[0];
        goto LABEL_29;
      }
      goto LABEL_140;
    }
    v19 = -2147024362;
LABEL_102:
    v55 = GetProcessHeap();
    lpMem = 0;
    TokenInformationLength = 0;
    if ( !is_mul_ok(0x39u, 2u) )
    {
LABEL_103:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecore\\internal\\ds\\inc\\profiles\\sid.h",
        (const char *)(unsigned int)v19,
        ReturnLengtha);
      if ( v46 )
      {
        v56 = GetProcessHeap();
        HeapFree(v56, 0, v46);
      }
      v18 = -2147024362;
      v3 = (const WCHAR *)hMem[0];
      goto LABEL_29;
    }
    v72 = (WCHAR *)HeapAlloc(v55, 0, 0x72u);
    v73 = v72;
    lpMem = v72;
    if ( !v72 )
    {
      v19 = -2147024882;
      goto LABEL_103;
    }
    v74 = 56;
    v75 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList";
    v76 = 57;
    v77 = 0;
    v78 = v72;
    while ( v74 )
    {
      v79 = *v75;
      if ( !*v75 )
        break;
      ++v75;
      *v73++ = v79;
      --v74;
      ++v77;
      if ( !--v76 )
      {
        *(v73 - 1) = 0;
        goto LABEL_140;
      }
    }
    *v73 = 0;
    v80 = 57 - v77;
    if ( v77 != 57 && v77 != 56 && (unsigned __int64)(2 * v80) > 2 )
      memset_0(&v78[v77 + 1], 0, 2 * v80 - 2);
LABEL_140:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v102);
    v19 = 0;
    v18 = -2147024362;
    v3 = (const WCHAR *)hMem[0];
    goto LABEL_29;
  }
LABEL_184:
  v31 = hMem[0];
  v32 = a2;
LABEL_70:
  if ( *v32 )
    goto LABEL_71;
  OldSidString = GetOldSidString(v2, v6, v32);
  if ( OldSidString < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
      (const char *)(unsigned int)OldSidString,
      ReturnLength);
  if ( *v32 || (v92 = GetProcessHeap(), v94 = _AllocString<CTHeapAllocPolicy>(v92, v93, v31, v32), v95 = v94, v94 >= 0) )
  {
LABEL_71:
    if ( v31 )
      LocalFree(v31);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x131,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
      (const char *)(unsigned int)v94,
      ReturnLength);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(hMem);
    return v95;
  }
}

```

## disassembly

```asm
0x18000e200  mov     [rsp-8+arg_8], rdx
0x18000e205  mov     [rsp-8+arg_0], rcx
0x18000e20a  push    rbp
0x18000e20b  push    rbx
0x18000e20c  push    rsi
0x18000e20d  push    rdi
0x18000e20e  push    r12
0x18000e210  push    r13
0x18000e212  push    r14
0x18000e214  push    r15
0x18000e216  lea     rbp, [rsp-1Fh]
0x18000e21b  sub     rsp, 0A8h
0x18000e222  mov     r13, rcx
0x18000e225  mov     qword ptr [rdx], 0
0x18000e22c  xor     r15d, r15d
0x18000e22f  mov     [rbp+57h+hMem], r15
0x18000e233  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000e23a  mov     [rbp+57h+var_88], rdi
0x18000e23e  mov     [rbp+57h+var_80], rdi
0x18000e242  mov     dword ptr [rbp+57h+TokenInformationLength], 0C8h
0x18000e249  call    cs:__imp_GetProcessHeap
0x18000e250  nop     dword ptr [rax+rax+00h]
0x18000e255  mov     rcx, rax; hHeap
0x18000e258  mov     edx, 8; dwFlags
0x18000e25d  mov     r8d, 0C8h; dwBytes
0x18000e263  call    cs:__imp_HeapAlloc
0x18000e26a  nop     dword ptr [rax+rax+00h]
0x18000e26f  mov     rsi, rax
0x18000e272  mov     [rbp+57h+StringSid], rax
0x18000e276  test    rax, rax
0x18000e279  jz      loc_18000EF63
0x18000e27f  xor     r14d, r14d
0x18000e282  lea     rax, [rbp+57h+TokenInformationLength]
0x18000e286  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18000e28b  mov     r9d, dword ptr [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18000e28f  mov     r8, rsi; TokenInformation
0x18000e292  mov     edx, 1; TokenInformationClass
0x18000e297  mov     rcx, r13; TokenHandle
0x18000e29a  call    cs:__imp_GetTokenInformation
0x18000e2a1  nop     dword ptr [rax+rax+00h]
0x18000e2a6  mov     r12d, 8007000Eh
0x18000e2ac  test    eax, eax
0x18000e2ae  jz      loc_18000ED8A
0x18000e2b4  xor     ebx, ebx
0x18000e2b6  test    ebx, ebx
0x18000e2b8  js      short loc_18000E323
0x18000e2ba  mov     rcx, [rsi]; pSid
0x18000e2bd  call    cs:__imp_GetLengthSid
0x18000e2c4  nop     dword ptr [rax+rax+00h]
0x18000e2c9  mov     ebx, eax
0x18000e2cb  mov     dword ptr [rbp+57h+TokenInformationLength], ebx
0x18000e2ce  call    cs:__imp_GetProcessHeap
0x18000e2d5  nop     dword ptr [rax+rax+00h]
0x18000e2da  mov     rcx, rax; hHeap
0x18000e2dd  mov     r8d, ebx; dwBytes
0x18000e2e0  mov     edx, 8; dwFlags
0x18000e2e5  call    cs:__imp_HeapAlloc
0x18000e2ec  nop     dword ptr [rax+rax+00h]
0x18000e2f1  mov     r15, rax
0x18000e2f4  test    rax, rax
0x18000e2f7  jz      loc_18000EF71
0x18000e2fd  mov     r8, [rsi]; pSourceSid
0x18000e300  mov     rdx, rax; pDestinationSid
0x18000e303  mov     ecx, dword ptr [rbp+57h+TokenInformationLength]; nDestinationSidLength
0x18000e306  call    cs:__imp_CopySid
0x18000e30d  nop     dword ptr [rax+rax+00h]
0x18000e312  test    eax, eax
0x18000e314  jz      loc_18000EDEB
0x18000e31a  xor     ebx, ebx
0x18000e31c  mov     r14, r15
0x18000e31f  mov     r15, [rbp+57h+hMem]
0x18000e323  test    rsi, rsi
0x18000e326  jz      short loc_18000E350
0x18000e328  call    cs:__imp_GetProcessHeap
0x18000e32f  nop     dword ptr [rax+rax+00h]
0x18000e334  mov     rcx, rax; hHeap
0x18000e337  mov     r8, rsi; lpMem
0x18000e33a  xor     edx, edx; dwFlags
0x18000e33c  call    cs:__imp_HeapFree
0x18000e343  nop     dword ptr [rax+rax+00h]
0x18000e348  test    eax, eax
0x18000e34a  jz      loc_18000EF79
0x18000e350  test    ebx, ebx
0x18000e352  js      loc_18000F089
0x18000e358  mov     [rbp+57h+StringSid], 0
0x18000e360  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18000e364  mov     rcx, r14; Sid
0x18000e367  call    cs:__imp_ConvertSidToStringSidW
0x18000e36e  nop     dword ptr [rax+rax+00h]
0x18000e373  test    eax, eax
0x18000e375  jz      loc_18000ED76
0x18000e37b  xor     ebx, ebx
0x18000e37d  mov     r15, [rbp+57h+StringSid]
0x18000e381  mov     [rbp+57h+hMem], r15
0x18000e385  test    r14, r14
0x18000e388  jz      short loc_18000E3B2
0x18000e38a  call    cs:__imp_GetProcessHeap
0x18000e391  nop     dword ptr [rax+rax+00h]
0x18000e396  mov     rcx, rax; hHeap
0x18000e399  mov     r8, r14; lpMem
0x18000e39c  xor     edx, edx; dwFlags
0x18000e39e  call    cs:__imp_HeapFree
0x18000e3a5  nop     dword ptr [rax+rax+00h]
0x18000e3aa  test    eax, eax
0x18000e3ac  jz      loc_18000EF83
0x18000e3b2  test    ebx, ebx
0x18000e3b4  js      loc_18000F089
0x18000e3ba  mov     [rbp+57h+var_50], rdi
0x18000e3be  mov     [rbp+57h+var_48], rdi
0x18000e3c2  xor     r14d, r14d
0x18000e3c5  mov     [rbp+57h+lpSubKey], r14
0x18000e3c9  mov     [rbp+57h+lpMem], r14
0x18000e3cd  mov     [rbp+57h+var_A0], r14
0x18000e3d1  mov     [rbp+57h+var_98], r14
0x18000e3d5  mov     dword ptr [rsp+0E0h+ReturnLength], 1; bIgnoreCase
0x18000e3dd  mov     r9d, edi; cchCount2
0x18000e3e0  lea     r8, aS1518_0; "S-1-5-18"
0x18000e3e7  mov     edx, edi; cchCount1
0x18000e3e9  mov     rcx, r15; lpString1
0x18000e3ec  call    cs:__imp_CompareStringOrdinal
0x18000e3f3  nop     dword ptr [rax+rax+00h]
0x18000e3f8  cmp     eax, 2
0x18000e3fb  jz      loc_18000E4A5
0x18000e401  mov     dword ptr [rsp+0E0h+ReturnLength], 1; bIgnoreCase
0x18000e409  mov     r9d, edi; cchCount2
0x18000e40c  lea     r8, aS1519; "S-1-5-19"
0x18000e413  mov     edx, edi; cchCount1
0x18000e415  mov     rcx, r15; lpString1
0x18000e418  call    cs:__imp_CompareStringOrdinal
0x18000e41f  nop     dword ptr [rax+rax+00h]
0x18000e424  cmp     eax, 2
0x18000e427  jz      short loc_18000E4A5
0x18000e429  mov     dword ptr [rsp+0E0h+ReturnLength], 1; bIgnoreCase
0x18000e431  mov     r9d, edi; cchCount2
0x18000e434  lea     r8, aS1520_0; "S-1-5-20"
0x18000e43b  mov     edx, edi; cchCount1
0x18000e43d  mov     rcx, r15; lpString1
0x18000e440  call    cs:__imp_CompareStringOrdinal
0x18000e447  nop     dword ptr [rax+rax+00h]
0x18000e44c  cmp     eax, 2
0x18000e44f  jz      short loc_18000E4A5
0x18000e451  mov     dword ptr [rsp+0E0h+ReturnLength], 1; bIgnoreCase
0x18000e459  mov     r9d, edi; cchCount2
0x18000e45c  lea     r8, String2; "S-1-5-93-2-1"
0x18000e463  mov     edx, edi; cchCount1
0x18000e465  mov     rcx, r15; lpString1
0x18000e468  call    cs:__imp_CompareStringOrdinal
0x18000e46f  nop     dword ptr [rax+rax+00h]
0x18000e474  cmp     eax, 2
0x18000e477  jz      short loc_18000E4A5
0x18000e479  mov     dword ptr [rsp+0E0h+ReturnLength], 1; int
0x18000e481  mov     r9d, edi; cchCount2
0x18000e484  lea     r8, aS159322; "S-1-5-93-2-2"
0x18000e48b  mov     edx, edi; cchCount1
0x18000e48d  mov     rcx, r15; lpString1
0x18000e490  call    cs:__imp_CompareStringOrdinal
0x18000e497  nop     dword ptr [rax+rax+00h]
0x18000e49c  cmp     eax, 2
0x18000e49f  jnz     loc_18000E863
0x18000e4a5  mov     [rbp+57h+TokenInformationLength], r14
0x18000e4a9  mov     ebx, 39h ; '9'
0x18000e4ae  mov     eax, 2
0x18000e4b3  mul     rbx
0x18000e4b6  mov     rsi, rax
0x18000e4b9  mov     r13d, 80070216h
0x18000e4bf  test    rdx, rdx
0x18000e4c2  jz      loc_18000EB99
0x18000e4c8  mov     esi, r13d
0x18000e4cb  jmp     short loc_18000E4DE
0x18000e4cd  test    rbx, rbx
0x18000e4d0  jz      loc_18000EC0E
0x18000e4d6  mov     [r8], r14w
0x18000e4da  mov     [rbp+57h+var_A0], r9
0x18000e4de  test    esi, esi
0x18000e4e0  js      loc_18000E723
0x18000e4e6  mov     r8, r15
0x18000e4e9  lea     rdx, aS_1; "\\%s"
0x18000e4f0  lea     rcx, [rbp+57h+lpMem]
0x18000e4f4  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18000e4f9  test    eax, eax
0x18000e4fb  js      loc_18000EF95
0x18000e501  mov     r12, r14
0x18000e504  mov     [rbp+57h+lpSubKey], r14
0x18000e508  mov     [rbp+57h+var_58], r14
0x18000e50c  mov     r15, [rbp+57h+lpMem]
0x18000e510  test    r15, r15
0x18000e513  jz      loc_18000EFB7
0x18000e519  mov     [rbp+57h+var_78], r14
0x18000e51d  mov     [rbp+57h+var_70], r14
0x18000e521  mov     [rbp+57h+var_68], r14
0x18000e525  mov     rax, [rbp+57h+var_A0]
0x18000e529  cmp     rax, rdi
0x18000e52c  jnz     short loc_18000E53C
0x18000e52e  mov     rax, rdi
0x18000e531  inc     rax
0x18000e534  cmp     word ptr [r15+rax*2], 0
0x18000e53a  jnz     short loc_18000E531
0x18000e53c  test    r15, r15
0x18000e53f  jz      loc_18000EFA2
0x18000e545  mov     rbx, rdi
0x18000e548  nop     dword ptr [rax+rax+00000000h]
0x18000e550  inc     rbx
0x18000e553  cmp     word ptr [r15+rbx*2], 0
0x18000e559  jnz     short loc_18000E550
0x18000e55b  cmp     rax, rdi
0x18000e55e  jz      loc_18000E71B
0x18000e564  cmp     rax, rbx
0x18000e567  jb      loc_18000EE3C
0x18000e56d  lea     rsi, [rax+1]
0x18000e571  cmp     rsi, rax
0x18000e574  jb      short loc_18000E58E
0x18000e576  mov     [rbp+57h+TokenInformationLength], r14
0x18000e57a  mov     eax, 2
0x18000e57f  mul     rsi
0x18000e582  mov     r14, rax
0x18000e585  test    rdx, rdx
0x18000e588  jz      loc_18000EACC
0x18000e58e  mov     r14d, r13d
0x18000e591  test    r14d, r14d
0x18000e594  jns     loc_18000ED6A
0x18000e59a  test    r12, r12
0x18000e59d  jz      short loc_18000E5BF
0x18000e59f  call    cs:__imp_GetProcessHeap
0x18000e5a6  nop     dword ptr [rax+rax+00h]
0x18000e5ab  mov     rcx, rax; hHeap
0x18000e5ae  mov     r8, r12; lpMem
0x18000e5b1  xor     edx, edx; dwFlags
0x18000e5b3  call    cs:__imp_HeapFree
0x18000e5ba  nop     dword ptr [rax+rax+00h]
0x18000e5bf  mov     ebx, r14d
0x18000e5c2  mov     r12, [rbp+57h+lpSubKey]
0x18000e5c6  test    ebx, ebx
0x18000e5c8  jns     loc_18000EB74
0x18000e5ce  mov     rcx, [rbp+5Fh]; this
0x18000e5d2  mov     r9d, r14d; char *
0x18000e5d5  lea     r8, aOnecoreInterna_3; "onecore\\internal\\ds\\inc\\profiles\\s"...
0x18000e5dc  mov     edx, 82h; void *
0x18000e5e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e5e6  test    r15, r15
0x18000e5e9  jz      short loc_18000E60B
0x18000e5eb  call    cs:__imp_GetProcessHeap
0x18000e5f2  nop     dword ptr [rax+rax+00h]
0x18000e5f7  mov     rcx, rax; hHeap
0x18000e5fa  mov     r8, r15; lpMem
0x18000e5fd  xor     edx, edx; dwFlags
0x18000e5ff  call    cs:__imp_HeapFree
0x18000e606  nop     dword ptr [rax+rax+00h]
0x18000e60b  test    r14d, r14d
0x18000e60e  js      loc_18000E748
0x18000e614  xor     r15d, r15d
0x18000e617  mov     [rbp+57h+TokenInformationLength], r15
0x18000e61b  mov     rsi, [rbp+57h+TokenInformationLength]
0x18000e61f  test    rsi, rsi
0x18000e622  jnz     loc_18000EFC2
0x18000e628  mov     [rbp+57h+TokenInformationLength], r15
0x18000e62c  lea     rax, [rbp+57h+TokenInformationLength]
0x18000e630  mov     [rsp+0E0h+ReturnLength], rax; int
0x18000e635  mov     r9d, 20019h; samDesired
0x18000e63b  xor     r8d, r8d; ulOptions
0x18000e63e  mov     rdx, r12; lpSubKey
0x18000e641  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e648  call    cs:__imp_RegOpenKeyExW
0x18000e64f  nop     dword ptr [rax+rax+00h]
0x18000e654  test    eax, eax
0x18000e656  jnz     loc_18000EFF3
0x18000e65c  call    cs:__imp_GetProcessHeap
0x18000e663  nop     dword ptr [rax+rax+00h]
0x18000e668  mov     rcx, rax; hHeap
0x18000e66b  mov     rsi, [rbp+57h+hMem]
0x18000e66f  nop
0x18000e670  inc     rdi
0x18000e673  cmp     word ptr [rsi+rdi*2], 0
0x18000e678  jnz     short loc_18000E670
0x18000e67a  mov     r14, [rbp+57h+arg_8]
0x18000e67e  mov     [r14], r15
0x18000e681  lea     rbx, [rdi+1]
0x18000e685  cmp     rbx, rdi
0x18000e688  jb      short loc_18000E69B
0x18000e68a  mov     eax, 2
0x18000e68f  mul     rbx
0x18000e692  test    rdx, rdx
0x18000e695  jz      loc_18000E7AD
0x18000e69b  mov     rcx, [rbp+5Fh]; this
0x18000e69f  mov     r9d, r13d; char *
0x18000e6a2  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000e6a9  mov     edx, 124h; void *
0x18000e6ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e6b3  nop
0x18000e6b4  mov     rcx, [rbp+57h+TokenInformationLength]; hKey
0x18000e6b8  test    rcx, rcx
0x18000e6bb  jz      short loc_18000E6CA
0x18000e6bd  call    cs:__imp_RegCloseKey
0x18000e6c4  nop     dword ptr [rax+rax+00h]
0x18000e6c9  nop
0x18000e6ca  test    r12, r12
0x18000e6cd  jz      short loc_18000E6EF
0x18000e6cf  call    cs:__imp_GetProcessHeap
0x18000e6d6  nop     dword ptr [rax+rax+00h]
0x18000e6db  mov     rcx, rax; hHeap
0x18000e6de  mov     r8, r12; lpMem
  ... truncated ...
```
