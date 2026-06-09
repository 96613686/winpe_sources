# GetProfileSidString(void *,ushort * *)

- ea: `0x18000ff50`
- end: `0x180010cbf`
- name: `?GetProfileSidString@@YAJPEAXPEAPEAG@Z`
- size: `3439`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800140c0`
- `0x180037ce0`

## callees

- `0x180004170`
- `0x180004ff4`
- `0x180006580`
- `0x180008360`
- `0x18000d460`
- `0x18000fa10`
- `0x18000ff50`
- `0x1800111a0`
- `0x180016250`
- `0x180016680`
- `0x18001f060`
- `0x1800245c0`
- `0x18002d2d8`
- `0x18003b310`
- `0x18003e8fc`
- `0x18003f42c`
- `0x18004e444`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ffad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010017`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010451`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800105cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010736`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800107ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010858`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ffad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010017`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010451`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800105cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010736`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800107ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010858`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001005c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800100aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010292`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800102d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010397`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800103f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010423`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800105f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001066a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800108e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001096e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010a49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001005c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800100aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010292`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800102d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010397`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800103f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010423`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800105f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001066a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800108e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001096e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010a49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ff99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010006`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001004e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001009c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010284`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800102c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010323`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010389`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010415`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800105c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800105ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010615`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001065c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010728`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800108db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010960`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010b37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ff99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010006`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001004e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001009c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010284`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800102c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010323`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010389`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010415`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800105c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800105ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010615`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001065c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010728`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800108db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010960`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010b37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010c16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010c16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c03`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800100f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010118`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001013a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001015c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001017e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800100f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010118`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001013a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001015c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001017e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010315`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001053e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010c67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010315`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001053e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010c67`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001058a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800106b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001058a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800106b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001037d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010409`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010602`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001037d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010409`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010602`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c0e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180010913`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180010940`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180010913`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180010940`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180010032`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180010032`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000fffb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000fffb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000ffde`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010a06`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000ffde`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010a06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800103a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001043f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800103a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001043f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001007f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001007f`

## string_xrefs

- `0x1800102ae`: `onecore\internal\ds\inc\profiles\sid.h`
- `0x1800103d1`: `onecore\internal\ds\inc\profiles\sid.h`
- `0x180010646`: `onecore\internal\ds\inc\profiles\sid.h`
- `0x180010ab4`: `onecore\internal\ds\inc\profiles\sid.h`
- `0x180010bc1`: `onecore\internal\ds\inc\profiles\sid.h`
- `0x180010362`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x180010b1c`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x180010b5c`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

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
  HANDLE v15; // rax
  WCHAR *v16; // r14
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
  HANDLE v36; // rax
  HANDLE v37; // rax
  const unsigned __int16 *v38; // rcx
  unsigned __int64 v39; // r8
  __int64 v40; // r9
  unsigned __int16 *v41; // r10
  unsigned __int16 v42; // ax
  __int64 v43; // rbx
  bool v44; // cf
  BYTE *v45; // r13
  int v46; // eax
  HKEY v47; // r14
  BYTE *v48; // rbx
  LSTATUS Value; // eax
  signed int v50; // esi
  unsigned int v51; // ebx
  HANDLE v52; // rax
  HANDLE v53; // rax
  HANDLE v54; // rcx
  HANDLE v55; // rax
  LSTATUS v56; // eax
  __int64 v57; // r14
  __int64 v58; // rax
  HANDLE v59; // rax
  WCHAR *v60; // rax
  WCHAR *v61; // rcx
  WCHAR *v62; // rdx
  WCHAR v63; // ax
  HANDLE v64; // rax
  HANDLE v65; // rax
  WCHAR *v66; // rax
  __int64 v67; // rdx
  const WCHAR *v68; // rax
  WCHAR *v69; // r8
  WCHAR v70; // cx
  __int64 v71; // r9
  const WCHAR *v72; // rax
  __int64 v73; // rdx
  WCHAR *v74; // r8
  __int64 v75; // r10
  WCHAR v76; // cx
  __int64 v77; // rbx
  HANDLE v78; // rax
  DWORD v79; // eax
  DWORD v80; // r15d
  WCHAR *v81; // rax
  WCHAR *v82; // r12
  DWORD v83; // eax
  DWORD v84; // r14d
  HANDLE v85; // rax
  BOOL TokenInformation; // eax
  HANDLE v87; // rax
  int v88; // eax
  int OldSidString; // eax
  HANDLE v90; // rax
  __int64 v91; // rdx
  int v92; // eax
  unsigned int v93; // ebx
  int ReturnLength; // [rsp+20h] [rbp-69h]
  int ReturnLengtha; // [rsp+20h] [rbp-69h]
  LPVOID lpMem; // [rsp+38h] [rbp-51h] BYREF
  __int64 v97; // [rsp+40h] [rbp-49h]
  __int64 v98; // [rsp+48h] [rbp-41h]
  HLOCAL hMem[3]; // [rsp+50h] [rbp-39h] BYREF
  BYTE *v100; // [rsp+68h] [rbp-21h] BYREF
  __int64 v101; // [rsp+70h] [rbp-19h]
  __int64 v102; // [rsp+78h] [rbp-11h]
  HKEY phkResult; // [rsp+80h] [rbp-9h] BYREF
  LPCWSTR v104[11]; // [rsp+88h] [rbp-1h] BYREF
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
    Error = -2147024882;
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
  if ( Error >= 0 )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(v8, &StringSid) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_17;
    }
    v3 = StringSid;
    hMem[0] = StringSid;
LABEL_17:
    if ( v8 )
    {
      v15 = GetProcessHeap();
      if ( !HeapFree(v15, 0, v8) )
        ResultFromKnownLastError();
    }
  }
LABEL_20:
  if ( Error >= 0 )
  {
    v104[1] = (LPCWSTR)-1LL;
    v104[2] = (LPCWSTR)-1LL;
    v16 = 0;
    lpMem = 0;
    v97 = 0;
    v98 = 0;
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
        v65 = GetProcessHeap();
        v66 = (WCHAR *)HeapAlloc(v65, 0, 0x72u);
        if ( v66 )
        {
          v98 = 57;
          v16 = v66;
          lpMem = v66;
          *v66 = 0;
          v67 = 56;
          v68 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList";
          v69 = v16;
          v19 = 0;
          while ( v67 )
          {
            v70 = *v68;
            if ( !*v68 )
              break;
            ++v68;
            *v69++ = v70;
            --v67;
            if ( !--v17 )
            {
              --v69;
              break;
            }
          }
          *v69 = 0;
          v97 = 56;
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
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x80,
          (unsigned int)"onecore\\internal\\ds\\inc\\profiles\\sid.h",
          (const char *)(unsigned int)v19,
          ReturnLengtha);
        if ( v16 )
        {
          v36 = GetProcessHeap();
          HeapFree(v36, 0, v16);
        }
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
          v104[0] = 0;
          v22 = (WCHAR *)lpMem;
          if ( lpMem )
          {
            v100 = 0;
            v101 = 0;
            v102 = 0;
            v23 = v97;
            if ( v97 == -1 )
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
              v59 = GetProcessHeap();
              v60 = (WCHAR *)HeapAlloc(v59, 0, 2 * v25);
              if ( v60 )
              {
                v21 = v60;
                *v60 = 0;
                v26 = 0;
                if ( v25 )
                {
                  if ( v24 > 0x7FFFFFFE || v25 > 0x7FFFFFFF )
                  {
                    *v60 = 0;
                  }
                  else
                  {
                    v61 = v22;
                    v62 = v60;
                    while ( v24 )
                    {
                      v63 = *v61;
                      if ( !*v61 )
                        break;
                      ++v61;
                      *v62++ = v63;
                      --v24;
                      if ( !--v25 )
                      {
                        --v62;
                        break;
                      }
                    }
                    *v62 = 0;
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
              v104[0] = v21;
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
              v64 = GetProcessHeap();
              HeapFree(v64, 0, v22);
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
                        v104,
                        L".bak",
                        4) < 0 )
            {
              v21 = (WCHAR *)v104[0];
            }
            else
            {
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                &TokenInformationLength,
                0);
              v21 = (WCHAR *)v104[0];
              if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v104[0], 0, 0x20019u, &TokenInformationLength) )
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
                  v38 = (const unsigned __int16 *)v31;
                  if ( !v31 )
                  {
                    v38 = &qword_180061CC0;
                    v4 = 0;
                  }
                  if ( v33 )
                  {
                    v39 = v33;
                    v40 = 0;
                    v41 = v6;
                    while ( v4 )
                    {
                      v42 = *v38;
                      if ( !*v38 )
                        break;
                      ++v38;
                      *v6++ = v42;
                      --v4;
                      ++v40;
                      if ( !--v39 )
                      {
                        *(v6 - 1) = 0;
                        goto LABEL_88;
                      }
                    }
                    *v6 = 0;
                    v44 = v33 == v40;
                    v43 = v33 - v40;
                    if ( !v44 && v43 != 1 && (unsigned __int64)(2 * v43) > 2 )
                      memset_0(&v41[v40 + 1], 0, 2 * v43 - 2);
                  }
                }
                goto LABEL_88;
              }
            }
            v32 = a2;
            v31 = hMem[0];
LABEL_88:
            if ( TokenInformationLength )
              RegCloseKey(TokenInformationLength);
            goto LABEL_68;
          }
LABEL_67:
          v32 = a2;
          v31 = hMem[0];
LABEL_68:
          if ( v21 )
          {
            v37 = GetProcessHeap();
            HeapFree(v37, 0, v21);
          }
          v2 = TokenHandle;
          goto LABEL_71;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x81,
          (unsigned int)"onecore\\internal\\ds\\inc\\profiles\\sid.h",
          (const char *)(unsigned int)v20,
          ReturnLengtha);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpMem);
      }
      v21 = 0;
      goto LABEL_67;
    }
    v97 = -1;
    v98 = -1;
    v45 = 0;
    v100 = 0;
    v101 = 0;
    v102 = 0;
    phkResult = 0;
    v46 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\ProfileList", 0, 0x20019u, &phkResult);
    if ( v46 > 0 )
      v46 = (unsigned __int16)v46 | 0x80070000;
    v19 = -2147024362;
    if ( v46 < 0 )
      goto LABEL_103;
    v47 = phkResult;
    v48 = 0;
    LODWORD(StringSid) = 0;
    LODWORD(TokenInformationLength) = 0;
    Value = RegQueryValueExW(phkResult, L"RedirectionKey", 0, (LPDWORD)&StringSid, 0, (LPDWORD)&TokenInformationLength);
    v50 = Value;
    if ( Value > 0 )
      v50 = (unsigned __int16)Value | 0x80070000;
    if ( v50 >= 0 )
    {
      if ( (unsigned int)((_DWORD)StringSid - 1) <= 1
        && (_DWORD)TokenInformationLength
        && ((unsigned __int8)TokenInformationLength & 1) == 0 )
      {
        v51 = (unsigned int)TokenInformationLength;
        v52 = GetProcessHeap();
        v48 = (BYTE *)HeapAlloc(v52, 0, v51);
        if ( !v48 )
        {
          v50 = -2147024882;
          goto LABEL_101;
        }
        v56 = RegQueryValueExW(v47, L"RedirectionKey", 0, (LPDWORD)&StringSid, v48, (LPDWORD)&TokenInformationLength);
        v50 = v56;
        if ( v56 > 0 )
          v50 = (unsigned __int16)v56 | 0x80070000;
        if ( v50 < 0 )
          goto LABEL_101;
        v57 = ((unsigned int)TokenInformationLength >> 1) - 1;
        if ( (_DWORD)StringSid == 2 )
        {
          v79 = ExpandEnvironmentStringsW((LPCWSTR)v48, 0, 0);
          v80 = v79;
          if ( v79 )
          {
            v81 = (WCHAR *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(2LL * v79);
            v82 = v81;
            if ( !v81 )
            {
              v50 = -2147024882;
              goto LABEL_101;
            }
            v83 = ExpandEnvironmentStringsW((LPCWSTR)v48, v81, v80);
            v84 = v83;
            if ( !v83 || v83 > v80 )
            {
              v50 = -2147024774;
              v87 = GetProcessHeap();
              HeapFree(v87, 0, v82);
              goto LABEL_101;
            }
            v50 = 0;
            v85 = GetProcessHeap();
            HeapFree(v85, 0, v48);
            v48 = (BYTE *)v82;
            v57 = v84 - 1;
          }
        }
        if ( !*(_WORD *)&v48[2 * v57] )
        {
          v101 = 0;
          v102 = 0;
          if ( v48 )
          {
            v58 = (unsigned int)(v57 + 1);
            if ( (_DWORD)v57 != -1 )
            {
              v45 = v48;
              v100 = v48;
              v102 = (unsigned int)v58;
              v101 = v58 - 1;
              *(_WORD *)&v48[2 * (unsigned int)v58 - 2] = 0;
            }
          }
          v48 = 0;
          goto LABEL_101;
        }
      }
      v50 = -2147024883;
    }
LABEL_101:
    v53 = GetProcessHeap();
    HeapFree(v53, 0, v48);
    RegCloseKey(phkResult);
    if ( v50 >= 0 )
    {
      v88 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(
              (__int64)&v100,
              &lpMem);
      v19 = v88;
      if ( v88 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"onecore\\internal\\ds\\inc\\profiles\\sid.h",
          (const char *)(unsigned int)v88,
          ReturnLengtha);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v100);
        v16 = (WCHAR *)lpMem;
        v18 = -2147024362;
        v3 = (const WCHAR *)hMem[0];
        goto LABEL_29;
      }
      v16 = (WCHAR *)lpMem;
      goto LABEL_141;
    }
    v19 = -2147024362;
LABEL_103:
    v54 = GetProcessHeap();
    v16 = 0;
    lpMem = 0;
    TokenInformationLength = 0;
    if ( !is_mul_ok(0x39u, 2u) )
    {
LABEL_104:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecore\\internal\\ds\\inc\\profiles\\sid.h",
        (const char *)(unsigned int)v19,
        ReturnLengtha);
      if ( v45 )
      {
        v55 = GetProcessHeap();
        HeapFree(v55, 0, v45);
      }
      v18 = -2147024362;
      v3 = (const WCHAR *)hMem[0];
      goto LABEL_29;
    }
    v16 = (WCHAR *)HeapAlloc(v54, 0, 0x72u);
    lpMem = v16;
    if ( !v16 )
    {
      v19 = -2147024882;
      goto LABEL_104;
    }
    v71 = 56;
    v72 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList";
    v73 = 57;
    v74 = v16;
    v75 = 0;
    while ( v71 )
    {
      v76 = *v72;
      if ( !*v72 )
        break;
      ++v72;
      *v74++ = v76;
      --v71;
      ++v75;
      if ( !--v73 )
      {
        *(v74 - 1) = 0;
        goto LABEL_141;
      }
    }
    *v74 = 0;
    v77 = 57 - v75;
    if ( v75 != 57 && v75 != 56 && (unsigned __int64)(2 * v77) > 2 )
      memset_0(&v16[v75 + 1], 0, 2 * v77 - 2);
LABEL_141:
    if ( v45 )
    {
      v78 = GetProcessHeap();
      HeapFree(v78, 0, v45);
    }
    v19 = 0;
    v18 = -2147024362;
    v3 = (const WCHAR *)hMem[0];
    goto LABEL_29;
  }
  v31 = hMem[0];
  v32 = a2;
LABEL_71:
  if ( *v32 )
    goto LABEL_72;
  OldSidString = GetOldSidString(v2, v6, v32);
  if ( OldSidString < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x12C,
      (int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
      (const char *)(unsigned int)OldSidString);
  if ( *v32 || (v90 = GetProcessHeap(), v92 = _AllocString<CTHeapAllocPolicy>(v90, v91, v31, v32), v93 = v92, v92 >= 0) )
  {
LABEL_72:
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
      (const char *)(unsigned int)v92,
      ReturnLength);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(hMem);
    return v93;
  }
}

```

## disassembly

```asm
0x18000ff50  mov     [rsp-8+arg_8], rdx
0x18000ff55  mov     [rsp-8+TokenHandle], rcx
0x18000ff5a  push    rbp
0x18000ff5b  push    rbx
0x18000ff5c  push    rsi
0x18000ff5d  push    rdi
0x18000ff5e  push    r12
0x18000ff60  push    r13
0x18000ff62  push    r14
0x18000ff64  push    r15
0x18000ff66  lea     rbp, [rsp-1Fh]
0x18000ff6b  sub     rsp, 0A8h
0x18000ff72  mov     r13, rcx
0x18000ff75  mov     qword ptr [rdx], 0
0x18000ff7c  xor     r15d, r15d
0x18000ff7f  mov     [rbp+57h+hMem], r15
0x18000ff83  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000ff8a  mov     [rbp+57h+var_88], rdi
0x18000ff8e  mov     [rbp+57h+var_80], rdi
0x18000ff92  mov     dword ptr [rbp+57h+TokenInformationLength], 0C8h
0x18000ff99  call    cs:__imp_GetProcessHeap
0x18000ff9f  mov     rcx, rax; hHeap
0x18000ffa2  mov     edx, 8; dwFlags
0x18000ffa7  mov     r8d, 0C8h; dwBytes
0x18000ffad  call    cs:__imp_HeapAlloc
0x18000ffb3  mov     rsi, rax
0x18000ffb6  mov     [rbp+57h+StringSid], rax
0x18000ffba  test    rax, rax
0x18000ffbd  jz      loc_180010B7D
0x18000ffc3  xor     r14d, r14d
0x18000ffc6  lea     rax, [rbp+57h+TokenInformationLength]
0x18000ffca  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18000ffcf  mov     r9d, dword ptr [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18000ffd3  mov     r8, rsi; TokenInformation
0x18000ffd6  mov     edx, 1; TokenInformationClass
0x18000ffdb  mov     rcx, r13; TokenHandle
0x18000ffde  call    cs:__imp_GetTokenInformation
0x18000ffe4  mov     r12d, 8007000Eh
0x18000ffea  test    eax, eax
0x18000ffec  jz      loc_1800109BF
0x18000fff2  xor     ebx, ebx
0x18000fff4  test    ebx, ebx
0x18000fff6  js      short loc_180010049
0x18000fff8  mov     rcx, [rsi]; pSid
0x18000fffb  call    cs:__imp_GetLengthSid
0x180010001  mov     ebx, eax
0x180010003  mov     dword ptr [rbp+57h+TokenInformationLength], ebx
0x180010006  call    cs:__imp_GetProcessHeap
0x18001000c  mov     rcx, rax; hHeap
0x18001000f  mov     r8d, ebx; dwBytes
0x180010012  mov     edx, 8; dwFlags
0x180010017  call    cs:__imp_HeapAlloc
0x18001001d  mov     r15, rax
0x180010020  test    rax, rax
0x180010023  jz      loc_180010B8D
0x180010029  mov     r8, [rsi]; pSourceSid
0x18001002c  mov     rdx, rax; pDestinationSid
0x18001002f  mov     ecx, dword ptr [rbp+57h+TokenInformationLength]; nDestinationSidLength
0x180010032  call    cs:__imp_CopySid
0x180010038  test    eax, eax
0x18001003a  jz      loc_180010A1A
0x180010040  xor     ebx, ebx
0x180010042  mov     r14, r15
0x180010045  mov     r15, [rbp+57h+hMem]
0x180010049  test    rsi, rsi
0x18001004c  jz      short loc_18001006A
0x18001004e  call    cs:__imp_GetProcessHeap
0x180010054  mov     rcx, rax; hHeap
0x180010057  mov     r8, rsi; lpMem
0x18001005a  xor     edx, edx; dwFlags
0x18001005c  call    cs:__imp_HeapFree
0x180010062  test    eax, eax
0x180010064  jz      loc_180010B95
0x18001006a  test    ebx, ebx
0x18001006c  js      loc_180010B86
0x180010072  xor     esi, esi
0x180010074  mov     [rbp+57h+StringSid], rsi
0x180010078  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18001007c  mov     rcx, r14; Sid
0x18001007f  call    cs:__imp_ConvertSidToStringSidW
0x180010085  test    eax, eax
0x180010087  jz      loc_1800109AB
0x18001008d  mov     ebx, esi
0x18001008f  mov     r15, [rbp+57h+StringSid]
0x180010093  mov     [rbp+57h+hMem], r15
0x180010097  test    r14, r14
0x18001009a  jz      short loc_1800100B8
0x18001009c  call    cs:__imp_GetProcessHeap
0x1800100a2  mov     rcx, rax; hHeap
0x1800100a5  mov     r8, r14; lpMem
0x1800100a8  xor     edx, edx; dwFlags
0x1800100aa  call    cs:__imp_HeapFree
0x1800100b0  test    eax, eax
0x1800100b2  jz      loc_180010B9F
0x1800100b8  test    ebx, ebx
0x1800100ba  js      loc_180010CB2
0x1800100c0  mov     [rbp+57h+var_50], rdi
0x1800100c4  mov     [rbp+57h+var_48], rdi
0x1800100c8  mov     [rbp+57h+lpSubKey], rsi
0x1800100cc  mov     r14, rsi
0x1800100cf  mov     [rbp+57h+lpMem], rsi
0x1800100d3  mov     [rbp+57h+var_A0], rsi
0x1800100d7  mov     [rbp+57h+var_98], rsi
0x1800100db  mov     dword ptr [rsp+0E0h+ReturnLength], 1; bIgnoreCase
0x1800100e3  mov     r9d, edi; cchCount2
0x1800100e6  lea     r8, String2; "S-1-5-18"
0x1800100ed  mov     edx, edi; cchCount1
0x1800100ef  mov     rcx, r15; lpString1
0x1800100f2  call    cs:__imp_CompareStringOrdinal
0x1800100f8  cmp     eax, 2
0x1800100fb  jz      loc_18001018D
0x180010101  mov     dword ptr [rsp+0E0h+ReturnLength], 1; bIgnoreCase
0x180010109  mov     r9d, edi; cchCount2
0x18001010c  lea     r8, aS1519; "S-1-5-19"
0x180010113  mov     edx, edi; cchCount1
0x180010115  mov     rcx, r15; lpString1
0x180010118  call    cs:__imp_CompareStringOrdinal
0x18001011e  cmp     eax, 2
0x180010121  jz      short loc_18001018D
0x180010123  mov     dword ptr [rsp+0E0h+ReturnLength], 1; bIgnoreCase
0x18001012b  mov     r9d, edi; cchCount2
0x18001012e  lea     r8, aS1520_0; "S-1-5-20"
0x180010135  mov     edx, edi; cchCount1
0x180010137  mov     rcx, r15; lpString1
0x18001013a  call    cs:__imp_CompareStringOrdinal
0x180010140  cmp     eax, 2
0x180010143  jz      short loc_18001018D
0x180010145  mov     dword ptr [rsp+0E0h+ReturnLength], 1; bIgnoreCase
0x18001014d  mov     r9d, edi; cchCount2
0x180010150  lea     r8, aS159321; "S-1-5-93-2-1"
0x180010157  mov     edx, edi; cchCount1
0x180010159  mov     rcx, r15; lpString1
0x18001015c  call    cs:__imp_CompareStringOrdinal
0x180010162  cmp     eax, 2
0x180010165  jz      short loc_18001018D
0x180010167  mov     dword ptr [rsp+0E0h+ReturnLength], 1; int
0x18001016f  mov     r9d, edi; cchCount2
0x180010172  lea     r8, aS159322; "S-1-5-93-2-2"
0x180010179  mov     edx, edi; cchCount1
0x18001017b  mov     rcx, r15; lpString1
0x18001017e  call    cs:__imp_CompareStringOrdinal
0x180010184  cmp     eax, 2
0x180010187  jnz     loc_180010503
0x18001018d  mov     [rbp+57h+TokenInformationLength], rsi
0x180010191  mov     ebx, 39h ; '9'
0x180010196  mov     eax, 2
0x18001019b  mul     rbx
0x18001019e  mov     rsi, rax
0x1800101a1  mov     r13d, 80070216h
0x1800101a7  test    rdx, rdx
0x1800101aa  jz      loc_1800107DC
0x1800101b0  mov     esi, r13d
0x1800101b3  jmp     short loc_1800101C8
0x1800101b5  test    rbx, rbx
0x1800101b8  jz      loc_18001084A
0x1800101be  xor     eax, eax
0x1800101c0  mov     [r8], ax
0x1800101c4  mov     [rbp+57h+var_A0], r9
0x1800101c8  test    esi, esi
0x1800101ca  js      loc_1800103CA
0x1800101d0  mov     r8, r15
0x1800101d3  lea     rdx, aS_1; "\\%s"
0x1800101da  lea     rcx, [rbp+57h+lpMem]
0x1800101de  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x1800101e3  test    eax, eax
0x1800101e5  js      loc_180010BBA
0x1800101eb  xor     r8d, r8d
0x1800101ee  mov     r12d, r8d
0x1800101f1  mov     [rbp+57h+lpSubKey], r8
0x1800101f5  mov     [rbp+57h+var_58], r8
0x1800101f9  mov     r15, [rbp+57h+lpMem]
0x1800101fd  test    r15, r15
0x180010200  jz      loc_180010BF8
0x180010206  mov     [rbp+57h+var_78], r8
0x18001020a  mov     [rbp+57h+var_70], r8
0x18001020e  mov     [rbp+57h+var_68], r8
0x180010212  mov     rax, [rbp+57h+var_A0]
0x180010216  cmp     rax, rdi
0x180010219  jnz     short loc_18001022A
0x18001021b  mov     rax, rdi
0x18001021e  xchg    ax, ax
0x180010220  inc     rax
0x180010223  cmp     [r15+rax*2], r8w
0x180010228  jnz     short loc_180010220
0x18001022a  test    r15, r15
0x18001022d  jz      loc_180010BE0
0x180010233  mov     rbx, rdi
0x180010236  inc     rbx
0x180010239  cmp     [r15+rbx*2], r8w
0x18001023e  jnz     short loc_180010236
0x180010240  cmp     rax, rdi
0x180010243  jz      loc_1800103C2
0x180010249  cmp     rax, rbx
0x18001024c  jb      loc_180010A5F
0x180010252  lea     rsi, [rax+1]
0x180010256  cmp     rsi, rax
0x180010259  jb      short loc_180010273
0x18001025b  mov     [rbp+57h+TokenInformationLength], r8
0x18001025f  mov     eax, 2
0x180010264  mul     rsi
0x180010267  mov     r14, rax
0x18001026a  test    rdx, rdx
0x18001026d  jz      loc_180010728
0x180010273  mov     r14d, r13d
0x180010276  test    r14d, r14d
0x180010279  jns     loc_18001099F
0x18001027f  test    r12, r12
0x180010282  jz      short loc_180010298
0x180010284  call    cs:__imp_GetProcessHeap
0x18001028a  mov     rcx, rax; hHeap
0x18001028d  mov     r8, r12; lpMem
0x180010290  xor     edx, edx; dwFlags
0x180010292  call    cs:__imp_HeapFree
0x180010298  mov     ebx, r14d
0x18001029b  mov     r12, [rbp+57h+lpSubKey]
0x18001029f  test    ebx, ebx
0x1800102a1  jns     loc_1800107C3
0x1800102a7  mov     rcx, [rbp+5Fh]; this
0x1800102ab  mov     r9d, r14d; char *
0x1800102ae  lea     r8, aOnecoreInterna_3; "onecore\\internal\\ds\\inc\\profiles\\s"...
0x1800102b5  mov     edx, 82h; void *
0x1800102ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800102bf  test    r15, r15
0x1800102c2  jz      short loc_1800102D8
0x1800102c4  call    cs:__imp_GetProcessHeap
0x1800102ca  mov     rcx, rax; hHeap
0x1800102cd  mov     r8, r15; lpMem
0x1800102d0  xor     edx, edx; dwFlags
0x1800102d2  call    cs:__imp_HeapFree
0x1800102d8  test    r14d, r14d
0x1800102db  js      loc_1800103FF
0x1800102e1  xor     r15d, r15d
0x1800102e4  mov     [rbp+57h+TokenInformationLength], r15
0x1800102e8  mov     rsi, [rbp+57h+TokenInformationLength]
0x1800102ec  test    rsi, rsi
0x1800102ef  jnz     loc_180010C03
0x1800102f5  mov     [rbp+57h+TokenInformationLength], r15
0x1800102f9  lea     rax, [rbp+57h+TokenInformationLength]
0x1800102fd  mov     [rsp+0E0h+ReturnLength], rax; int
0x180010302  mov     r9d, 20019h; samDesired
0x180010308  xor     r8d, r8d; ulOptions
0x18001030b  mov     rdx, r12; lpSubKey
0x18001030e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010315  call    cs:__imp_RegOpenKeyExW
0x18001031b  test    eax, eax
0x18001031d  jnz     loc_180010C22
0x180010323  call    cs:__imp_GetProcessHeap
0x180010329  mov     rcx, rax; hHeap
0x18001032c  mov     rsi, [rbp+57h+hMem]
0x180010330  inc     rdi
0x180010333  cmp     word ptr [rsi+rdi*2], 0
0x180010338  jnz     short loc_180010330
0x18001033a  mov     r14, [rbp+57h+arg_8]
0x18001033e  mov     [r14], r15
0x180010341  lea     rbx, [rdi+1]
0x180010345  cmp     rbx, rdi
0x180010348  jb      short loc_18001035B
0x18001034a  mov     eax, 2
0x18001034f  mul     rbx
0x180010352  test    rdx, rdx
0x180010355  jz      loc_18001044C
0x18001035b  mov     rcx, [rbp+5Fh]; this
0x18001035f  mov     r9d, r13d; char *
0x180010362  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180010369  mov     edx, 124h; void *
0x18001036e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010373  nop
0x180010374  mov     rcx, [rbp+57h+TokenInformationLength]; hKey
0x180010378  test    rcx, rcx
0x18001037b  jz      short loc_180010384
0x18001037d  call    cs:__imp_RegCloseKey
0x180010383  nop
0x180010384  test    r12, r12
0x180010387  jz      short loc_18001039D
0x180010389  call    cs:__imp_GetProcessHeap
0x18001038f  mov     rcx, rax; hHeap
0x180010392  mov     r8, r12; lpMem
0x180010395  xor     edx, edx; dwFlags
0x180010397  call    cs:__imp_HeapFree
0x18001039d  test    rsi, rsi
0x1800103a0  jz      short loc_1800103AB
0x1800103a2  mov     rcx, rsi; hMem
0x1800103a5  call    cs:__imp_LocalFree
0x1800103ab  mov     eax, r13d
0x1800103ae  add     rsp, 0A8h
0x1800103b5  pop     r15
0x1800103b7  pop     r14
0x1800103b9  pop     r13
0x1800103bb  pop     r12
0x1800103bd  pop     rdi
0x1800103be  pop     rsi
0x1800103bf  pop     rbx
0x1800103c0  pop     rbp
0x1800103c1  retn
0x1800103c2  mov     rax, rbx
0x1800103c5  jmp     loc_180010252
0x1800103ca  mov     rcx, [rbp+5Fh]; this
0x1800103ce  mov     r9d, esi; char *
0x1800103d1  lea     r8, aOnecoreInterna_3; "onecore\\internal\\ds\\inc\\profiles\\s"...
0x1800103d8  mov     edx, 80h; void *
  ... truncated ...
```
