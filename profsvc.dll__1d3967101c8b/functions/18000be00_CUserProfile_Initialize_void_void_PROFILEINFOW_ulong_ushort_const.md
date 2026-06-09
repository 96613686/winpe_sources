# CUserProfile::Initialize(void *,void *,_PROFILEINFOW *,ulong,ushort const *)

- ea: `0x18000be00`
- end: `0x18000c990`
- name: `?Initialize@CUserProfile@@IEAAJPEAX0PEAU_PROFILEINFOW@@KPEBG@Z`
- size: `2960`
- prototype: `__int64 __fastcall(CUserProfile *this, WCHAR *, void *, struct _PROFILEINFOW *, DWORD TokenInformationLength, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000b540`
- `0x1800190f4`

## callees

- `0x180004170`
- `0x180004ff4`
- `0x180006580`
- `0x18000be00`
- `0x18000cb80`
- `0x18000d460`
- `0x1800111a0`
- `0x1800154e0`
- `0x18001dc80`
- `0x180021980`
- `0x1800245c0`
- `0x180024898`
- `0x180024c20`
- `0x18002541c`
- `0x18002cba8`
- `0x18002d2d8`
- `0x18003c118`
- `0x18003e8fc`
- `0x18003f42c`
- `0x180046a78`
- `0x180047cbc`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000be70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bed3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c013`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c078`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c31b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c4d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000be70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bed3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c013`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c078`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c31b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c4d8`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000c2f2`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000c546`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000c2f2`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000c546`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c0c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c10d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c0c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c10d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bec2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bfff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c067`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c2d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c30d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c535`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bec2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bfff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c067`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c2d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c30d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c535`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c7f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c7f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7e0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000beee`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000c093`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000beee`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000c093`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000beb7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000c05c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000beb7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000c05c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bea0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c044`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c698`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c72b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bea0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c044`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c698`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c72b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c252`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c27c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c489`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c783`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c252`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c27c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c489`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c783`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c7eb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000bf39`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c0e1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000bf39`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c0e1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c8b5`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c8b5`
- `OLEAUT32!__imp_VariantClear` at `0x18000c1c2`
- `OLEAUT32!__imp_VariantClear` at `0x18000c1c2`
- `ext-ms-win-profile-profsvc-l1-1-0!CreateRoamingProviderInstance` at `0x18000c215`
- `ext-ms-win-profile-profsvc-l1-1-0!CreateRoamingProviderInstance` at `0x18000c215`

## string_xrefs

- `0x18000c261`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000c470`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000c76a`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000c80a`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000c88e`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000c945`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CUserProfile::Initialize(
        CUserProfile *this,
        WCHAR *a2,
        void *a3,
        struct _PROFILEINFOW *a4,
        DWORD TokenInformationLength,
        const unsigned __int16 *a6)
{
  LPWSTR v7; // r14
  CUserProfile *v8; // r15
  LPWSTR v9; // r12
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // rdi
  void *v12; // rsi
  int Error; // ebx
  DWORD LengthSid; // ebx
  HANDLE v15; // rax
  void *v16; // rax
  void *v17; // r14
  HANDLE v18; // rax
  HANDLE v19; // rax
  WCHAR **v20; // r13
  unsigned __int64 v21; // r15
  unsigned __int64 v22; // rbx
  unsigned __int64 v23; // r8
  int RoamingProviderInstance; // esi
  void *v25; // rdi
  HANDLE v26; // rax
  WCHAR *v27; // rdi
  void *v28; // rsi
  DWORD v29; // ebx
  HANDLE v30; // rax
  void *v31; // rax
  void *v32; // r14
  int v33; // r14d
  HANDLE v34; // rax
  HANDLE v35; // rax
  unsigned int v36; // edi
  struct _PROFILEINFOW *v37; // r9
  LPWSTR lpUserName; // rbx
  LPWSTR lpDefaultPath; // rdx
  unsigned __int16 *v40; // r14
  const unsigned __int16 *lpProfilePath; // rsi
  int v42; // eax
  struct _PROFILEINFOW *v43; // r13
  HANDLE v44; // rax
  int v45; // eax
  __int64 v47; // rdx
  unsigned __int64 v48; // rdi
  WCHAR *v49; // rsi
  HANDLE v50; // rcx
  WCHAR *v51; // rax
  HANDLE v52; // rax
  WCHAR *v53; // rax
  WCHAR *v54; // r8
  unsigned __int64 v55; // rcx
  LPWSTR v56; // rdx
  WCHAR v57; // ax
  int v58; // eax
  int v59; // ebx
  unsigned __int64 v60; // rsi
  unsigned __int64 v61; // rdi
  WCHAR **v62; // r13
  unsigned __int64 v63; // r8
  WCHAR *v64; // r8
  unsigned __int64 v65; // r14
  WCHAR *v66; // r15
  HANDLE v67; // rax
  WCHAR *v68; // rax
  WCHAR *v69; // rax
  WCHAR *v70; // rdx
  unsigned __int64 v71; // rcx
  WCHAR v72; // ax
  BOOL TokenInformation; // eax
  BOOL v74; // eax
  DWORD LastError; // ebx
  int v76; // eax
  unsigned __int64 v77; // rbx
  int v78; // eax
  __int64 v79; // rdx
  unsigned __int16 *v80; // r10
  __int64 v81; // rcx
  VARIANTARG *ReturnLength; // [rsp+20h] [rbp-48h]
  LPWSTR StringSid; // [rsp+40h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  LPWSTR v87; // [rsp+B8h] [rbp+50h] BYREF
  void *v88; // [rsp+C0h] [rbp+58h]
  struct _PROFILEINFOW *v89; // [rsp+C8h] [rbp+60h]

  v89 = a4;
  v88 = a3;
  v87 = a2;
  v7 = a2;
  v8 = this;
  *((_QWORD *)this + 4) = a2;
  *((_QWORD *)this + 3) = a3;
  *((_DWORD *)this + 5) = TokenInformationLength;
  v9 = 0;
  *(_QWORD *)&pvarg.vt = 0;
  pvarg.llVal = -1;
  pvarg.pRecInfo = (IRecordInfo *)-1LL;
  TokenInformationLength = 200;
  ProcessHeap = GetProcessHeap();
  v11 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0xC8u);
  StringSid = v11;
  if ( !v11 )
  {
    Error = -2147024882;
LABEL_174:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F2,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)Error,
      (int)ReturnLength);
    if ( v9 )
      LocalFree(v9);
    return (unsigned int)Error;
  }
  v12 = 0;
  if ( GetTokenInformation(a3, TokenUser, v11, TokenInformationLength, &TokenInformationLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      Error = ResultFromHeapReAlloc(v11, TokenInformationLength, (void **)&StringSid);
      v11 = StringSid;
      if ( Error < 0 )
        goto LABEL_10;
      TokenInformation = GetTokenInformation(a3, TokenUser, StringSid, TokenInformationLength, &TokenInformationLength);
      Error = ResultFromWin32Bool(TokenInformation);
    }
  }
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*(PSID *)v11);
    TokenInformationLength = LengthSid;
    v15 = GetProcessHeap();
    v16 = HeapAlloc(v15, 8u, LengthSid);
    v17 = v16;
    if ( !v16 )
    {
      Error = -2147024882;
      goto LABEL_9;
    }
    if ( CopySid(TokenInformationLength, v16, *(PSID *)v11) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        ResultFromHeapFree(v17);
        goto LABEL_9;
      }
    }
    v12 = v17;
LABEL_9:
    v7 = v87;
  }
LABEL_10:
  if ( v11 )
  {
    v18 = GetProcessHeap();
    if ( !HeapFree(v18, 0, v11) )
      ResultFromKnownLastError();
  }
  if ( Error < 0 )
    goto LABEL_174;
  StringSid = 0;
  if ( ConvertSidToStringSidW(v12, &StringSid) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_17;
  }
  v9 = StringSid;
  *(_QWORD *)&pvarg.vt = StringSid;
LABEL_17:
  if ( v12 )
  {
    v19 = GetProcessHeap();
    if ( !HeapFree(v19, 0, v12) )
      ResultFromKnownLastError();
  }
  if ( Error < 0 )
    goto LABEL_174;
  v20 = (WCHAR **)((char *)v8 + 48);
  if ( v9 )
  {
    v21 = -1;
    do
      ++v21;
    while ( v9[v21] );
    v22 = v21 + 1;
    if ( v21 + 1 < v21 )
      goto LABEL_28;
    v23 = (unsigned __int64)v20[2];
    if ( v23 == -1 )
    {
      v64 = v20[1];
      if ( v64 == (WCHAR *)-1LL )
      {
        if ( *v20 )
        {
          do
            v64 = (WCHAR *)((char *)v64 + 1);
          while ( (*v20)[(_QWORD)v64] );
        }
        else
        {
          v64 = 0;
        }
        v20[1] = v64;
      }
      v23 = (unsigned __int64)v64 + 1;
      if ( !*v20 )
        v23 = 0;
      v20[2] = (WCHAR *)v23;
    }
    if ( v23 )
    {
      RoamingProviderInstance = 0;
      if ( v22 > v23 )
      {
        v48 = 2 * v23;
        if ( !is_mul_ok(v23, 2u) )
          goto LABEL_28;
        if ( v23 > 0x800 )
          v48 = v23 + 2048;
        if ( v22 > v48 )
          v48 = v21 + 1;
        v49 = *v20;
        v50 = GetProcessHeap();
        if ( v49 )
          v51 = (WCHAR *)HeapReAlloc(v50, 0, v49, 2 * v48);
        else
          v51 = (WCHAR *)HeapAlloc(v50, 0, 2 * v48);
        if ( !v51 )
        {
          RoamingProviderInstance = -2147024882;
          goto LABEL_76;
        }
        RoamingProviderInstance = 0;
        v20[2] = (WCHAR *)v48;
        *v20 = v51;
      }
    }
    else
    {
      StringSid = 0;
      if ( !is_mul_ok(v22, 2u) )
      {
LABEL_28:
        RoamingProviderInstance = -2147024362;
        goto LABEL_29;
      }
      v52 = GetProcessHeap();
      v53 = (WCHAR *)HeapAlloc(v52, 0, 2 * v22);
      if ( v53 )
      {
        RoamingProviderInstance = 0;
        v20[2] = (WCHAR *)v22;
        *v20 = v53;
        *v53 = 0;
      }
      else
      {
        RoamingProviderInstance = -2147024882;
      }
      if ( RoamingProviderInstance < 0 )
        goto LABEL_76;
    }
    if ( v21 != -1 )
    {
      v54 = *v20;
      if ( v21 <= 0x7FFFFFFE && v22 <= 0x7FFFFFFF )
      {
        v55 = v21;
        v56 = v9;
        while ( v55 )
        {
          v57 = *v56;
          if ( !*v56 )
          {
            if ( !v22 )
            {
LABEL_100:
              --v54;
              break;
            }
            break;
          }
          ++v56;
          *v54++ = v57;
          --v55;
          if ( !--v22 )
            goto LABEL_100;
        }
      }
      *v54 = 0;
    }
    v20[1] = (WCHAR *)v21;
    v7 = v87;
LABEL_29:
    if ( RoamingProviderInstance >= 0 )
    {
      v8 = this;
      goto LABEL_31;
    }
LABEL_76:
    v47 = 499;
LABEL_77:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v47,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)RoamingProviderInstance,
      (int)ReturnLength);
    if ( v9 )
      LocalFree(v9);
    return (unsigned int)RoamingProviderInstance;
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((char *)v8 + 48);
LABEL_31:
  v25 = (void *)*((_QWORD *)v8 + 9);
  if ( v25 )
  {
    LastError = GetLastError();
    LocalFree(v25);
    SetLastError(LastError);
  }
  *((_QWORD *)v8 + 9) = 0;
  TokenInformationLength = 200;
  v26 = GetProcessHeap();
  v27 = (WCHAR *)HeapAlloc(v26, 8u, 0xC8u);
  v87 = v27;
  if ( !v27 )
  {
    Error = -2147024882;
LABEL_182:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)Error,
      (int)ReturnLength);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&pvarg);
    return (unsigned int)Error;
  }
  v28 = 0;
  if ( GetTokenInformation(v7, TokenUser, v27, TokenInformationLength, &TokenInformationLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      Error = ResultFromHeapReAlloc(v27, TokenInformationLength, (void **)&v87);
      v27 = v87;
      if ( Error < 0 )
        goto LABEL_41;
      v74 = GetTokenInformation(v7, TokenUser, v87, TokenInformationLength, &TokenInformationLength);
      Error = ResultFromWin32Bool(v74);
    }
  }
  if ( Error >= 0 )
  {
    v29 = GetLengthSid(*(PSID *)v27);
    TokenInformationLength = v29;
    v30 = GetProcessHeap();
    v31 = HeapAlloc(v30, 8u, v29);
    v32 = v31;
    if ( !v31 )
    {
      v33 = -2147024882;
      Error = -2147024882;
      goto LABEL_42;
    }
    if ( CopySid(TokenInformationLength, v31, *(PSID *)v27) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        ResultFromHeapFree(v32);
        goto LABEL_41;
      }
    }
    v28 = v32;
  }
LABEL_41:
  v33 = -2147024882;
LABEL_42:
  if ( v27 )
  {
    v34 = GetProcessHeap();
    if ( !HeapFree(v34, 0, v27) )
      ResultFromKnownLastError();
  }
  if ( Error < 0 )
    goto LABEL_182;
  v87 = 0;
  if ( ConvertSidToStringSidW(v28, &v87) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_49;
  }
  *((_QWORD *)v8 + 9) = v87;
LABEL_49:
  if ( v28 )
  {
    v35 = GetProcessHeap();
    if ( !HeapFree(v35, 0, v28) )
      ResultFromKnownLastError();
  }
  if ( Error < 0 )
    goto LABEL_182;
  v36 = 0;
  v37 = v89;
  if ( !v89 )
  {
LABEL_67:
    if ( !(unsigned __int8)IsWaitForNetworkForRoamingProfilePresent() )
    {
LABEL_71:
      v45 = *((_DWORD *)v8 + 2);
      if ( (v45 & 4) != 0 )
        *((_DWORD *)v8 + 2) = v45 | 1;
      if ( v9 )
        LocalFree(v9);
      return 0;
    }
    RoamingProviderInstance = CreateRoamingProviderInstance(v8, (char *)v8 + 288);
    if ( RoamingProviderInstance >= 0 )
    {
      if ( v36 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v8 + 36) + 64LL))(*((_QWORD *)v8 + 36), v36);
      goto LABEL_71;
    }
    v47 = 568;
    goto LABEL_77;
  }
  *((_DWORD *)v8 + 2) = v89->dwFlags;
  lpUserName = v37->lpUserName;
  if ( !lpUserName )
  {
LABEL_55:
    lpDefaultPath = v37->lpDefaultPath;
    if ( lpDefaultPath )
    {
      v76 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Initialize(
              (char *)v8 + 176,
              lpDefaultPath,
              -1);
      Error = v76;
      if ( v76 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x205,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)(unsigned int)v76,
          (int)ReturnLength);
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&pvarg);
        return (unsigned int)Error;
      }
    }
    v40 = 0;
    lpProfilePath = a6;
    if ( a6 )
    {
      v36 = 3;
      v43 = v89;
      goto LABEL_105;
    }
    memset(&pvarg, 0, sizeof(pvarg));
    ReturnLength = &pvarg;
    if ( (int)GetUserStateSetting(2, qword_18007CB80, 34, 11) >= 0 )
    {
      v87 = 0;
      v77 = SysStringLen(pvarg.bstrVal) + 1;
      v78 = ResultFromHeapAllocArray<unsigned short>(v77, &v87);
      if ( v78 >= 0 )
      {
        v78 = StringCchCopyW(v87, v77, pvarg.bstrVal);
        if ( v78 >= 0 )
        {
          v40 = v80;
          v87 = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v87);
          ATL::CComVariant::~CComVariant((ATL::CComVariant *)&pvarg);
          v42 = 1;
LABEL_62:
          v43 = v89;
          if ( v42 )
          {
            lpProfilePath = v40;
            v36 = 2;
          }
          else
          {
            lpProfilePath = v89->lpProfilePath;
            v36 = 1;
          }
          if ( !lpProfilePath )
          {
LABEL_65:
            if ( v40 )
            {
              v44 = GetProcessHeap();
              HeapFree(v44, 0, v40);
            }
            goto LABEL_67;
          }
LABEL_105:
          TokenInformationLength = 0;
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((char *)v8 + 104);
          *((_QWORD *)v8 + 14) = -1;
          *((_QWORD *)v8 + 15) = -1;
          v58 = AllocateAndExpandProfilePath(
                  *((const unsigned __int16 **)v8 + 10),
                  v43->lpServerName,
                  lpProfilePath,
                  (unsigned __int16 **)v8 + 13,
                  (PWSTR)&TokenInformationLength,
                  v88);
          v59 = v58;
          if ( v58 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x225,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
              (const char *)(unsigned int)v58,
              (int)ReturnLength);
            if ( v59 == -2147024774 && (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
              McTemplateU0z_EtwEventWriteTransfer(v81, EVENT_PROFILE_PATH_TOOLONG, v43->lpProfilePath);
          }
          else if ( TokenInformationLength )
          {
            *((_DWORD *)v8 + 3) |= 0x40001u;
            ProfileTelemetry::SuperMandatoryProfileSpecified();
          }
          goto LABEL_65;
        }
        v79 = 191;
      }
      else
      {
        v79 = 190;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v79,
        (unsigned int)"onecore\\internal\\ds\\inc\\profiles\\ProfileLocalSettings.h",
        (const char *)(unsigned int)v78,
        (int)&pvarg);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v87);
      ATL::CComVariant::~CComVariant((ATL::CComVariant *)&pvarg);
    }
    else
    {
      if ( pvarg.vt == 4095 )
        pvarg.vt = 8;
      VariantClear(&pvarg);
    }
    v42 = 0;
    goto LABEL_62;
  }
  v60 = -1;
  do
    ++v60;
  while ( lpUserName[v60] );
  v61 = v60 + 1;
  if ( v60 + 1 < v60 )
    goto LABEL_114;
  v62 = (WCHAR **)((char *)v8 + 80);
  v63 = *((_QWORD *)v8 + 12);
  if ( v63 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_EnsureCount((char *)v8 + 80);
    if ( *v62 )
      v63 = *((_QWORD *)v8 + 11) + 1LL;
    else
      v63 = 0;
    *((_QWORD *)v8 + 12) = v63;
  }
  if ( v63 )
  {
    if ( v61 <= v63 )
    {
LABEL_145:
      if ( v60 != -1 )
      {
        v70 = *v62;
        if ( v60 <= 0x7FFFFFFE && v61 <= 0x7FFFFFFF )
        {
          v71 = v60;
          while ( v71 )
          {
            v72 = *lpUserName;
            if ( !*lpUserName )
            {
              if ( !v61 )
              {
LABEL_152:
                --v70;
                break;
              }
              break;
            }
            ++lpUserName;
            *v70++ = v72;
            --v71;
            if ( !--v61 )
              goto LABEL_152;
          }
        }
        *v70 = 0;
      }
      v62[1] = (WCHAR *)v60;
      goto LABEL_55;
    }
    v87 = 0;
    v65 = 2 * v63;
    if ( !is_mul_ok(v63, 2u) )
      goto LABEL_114;
    if ( v63 > 0x800 )
      v65 = v63 + 2048;
    if ( v61 > v65 )
      v65 = v60 + 1;
    v66 = *v62;
    if ( *v62 )
    {
      v67 = GetProcessHeap();
      v68 = (WCHAR *)HeapReAlloc(v67, 0, v66, 2 * v65);
    }
    else
    {
      v68 = (WCHAR *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(2 * v65);
    }
    v9 = *(LPWSTR *)&pvarg.vt;
    if ( !v68 )
    {
      v33 = -2147024882;
      goto LABEL_115;
    }
    v62[2] = (WCHAR *)v65;
    *v62 = v68;
    v8 = this;
LABEL_144:
    v37 = v89;
    goto LABEL_145;
  }
  v87 = 0;
  if ( is_mul_ok(v61, 2u) )
  {
    v69 = (WCHAR *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(2 * v61);
    if ( v69 )
    {
      v33 = 0;
      *((_QWORD *)v8 + 12) = v61;
      *v62 = v69;
      *v69 = 0;
    }
    if ( v33 < 0 )
      goto LABEL_115;
    goto LABEL_144;
  }
LABEL_114:
  v33 = -2147024362;
LABEL_115:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x200,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)(unsigned int)v33,
    (int)ReturnLength);
  if ( v9 )
    LocalFree(v9);
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x18000be00  mov     [rsp-40h+arg_18], r9
0x18000be05  mov     [rsp-40h+arg_10], r8
0x18000be0a  mov     [rsp-40h+arg_8], rdx
0x18000be0f  mov     [rsp-40h+arg_0], rcx
0x18000be14  push    rbp
0x18000be15  push    rbx
0x18000be16  push    rsi
0x18000be17  push    rdi
0x18000be18  push    r12
0x18000be1a  push    r13
0x18000be1c  push    r14
0x18000be1e  push    r15
0x18000be20  mov     rbp, rsp
0x18000be23  sub     rsp, 68h
0x18000be27  mov     r13, r8
0x18000be2a  mov     r14, rdx
0x18000be2d  mov     r15, rcx
0x18000be30  mov     [rcx+20h], rdx
0x18000be34  mov     [rcx+18h], r8
0x18000be38  mov     eax, [rbp+TokenInformationLength]
0x18000be3b  mov     [rcx+14h], eax
0x18000be3e  xor     r12d, r12d
0x18000be41  mov     qword ptr [rbp+pvarg], r12
0x18000be45  mov     qword ptr [rbp+pvarg+8], 0FFFFFFFFFFFFFFFFh
0x18000be4d  mov     qword ptr [rbp+pvarg+10h], 0FFFFFFFFFFFFFFFFh
0x18000be55  mov     [rbp+TokenInformationLength], 0C8h
0x18000be5c  call    cs:__imp_GetProcessHeap
0x18000be62  mov     rcx, rax; hHeap
0x18000be65  mov     edx, 8; dwFlags
0x18000be6a  mov     r8d, 0C8h; dwBytes
0x18000be70  call    cs:__imp_HeapAlloc
0x18000be76  mov     rdi, rax
0x18000be79  mov     [rbp+StringSid], rax
0x18000be7d  test    rax, rax
0x18000be80  jz      loc_18000C790
0x18000be86  xor     esi, esi
0x18000be88  lea     rax, [rbp+TokenInformationLength]
0x18000be8c  mov     [rsp+68h+ReturnLength], rax; int
0x18000be91  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18000be95  mov     r8, rdi; TokenInformation
0x18000be98  mov     edx, 1; TokenInformationClass
0x18000be9d  mov     rcx, r13; TokenHandle
0x18000bea0  call    cs:__imp_GetTokenInformation
0x18000bea6  test    eax, eax
0x18000bea8  jz      loc_18000C651
0x18000beae  xor     ebx, ebx
0x18000beb0  test    ebx, ebx
0x18000beb2  js      short loc_18000BF05
0x18000beb4  mov     rcx, [rdi]; pSid
0x18000beb7  call    cs:__imp_GetLengthSid
0x18000bebd  mov     ebx, eax
0x18000bebf  mov     [rbp+TokenInformationLength], ebx
0x18000bec2  call    cs:__imp_GetProcessHeap
0x18000bec8  mov     rcx, rax; hHeap
0x18000becb  mov     r8d, ebx; dwBytes
0x18000bece  mov     edx, 8; dwFlags
0x18000bed3  call    cs:__imp_HeapAlloc
0x18000bed9  mov     r14, rax
0x18000bedc  test    rax, rax
0x18000bedf  jz      loc_18000C797
0x18000bee5  mov     r8, [rdi]; pSourceSid
0x18000bee8  mov     rdx, rax; pDestinationSid
0x18000beeb  mov     ecx, [rbp+TokenInformationLength]; nDestinationSidLength
0x18000beee  call    cs:__imp_CopySid
0x18000bef4  test    eax, eax
0x18000bef6  jz      loc_18000C6B4
0x18000befc  xor     ebx, ebx
0x18000befe  mov     rsi, r14
0x18000bf01  mov     r14, [rbp+arg_8]
0x18000bf05  test    rdi, rdi
0x18000bf08  jz      short loc_18000BF26
0x18000bf0a  call    cs:__imp_GetProcessHeap
0x18000bf10  mov     rcx, rax; hHeap
0x18000bf13  mov     r8, rdi; lpMem
0x18000bf16  xor     edx, edx; dwFlags
0x18000bf18  call    cs:__imp_HeapFree
0x18000bf1e  test    eax, eax
0x18000bf20  jz      loc_18000C7A1
0x18000bf26  test    ebx, ebx
0x18000bf28  js      loc_18000C763
0x18000bf2e  mov     [rbp+StringSid], r12
0x18000bf32  lea     rdx, [rbp+StringSid]; StringSid
0x18000bf36  mov     rcx, rsi; Sid
0x18000bf39  call    cs:__imp_ConvertSidToStringSidW
0x18000bf3f  test    eax, eax
0x18000bf41  jz      loc_18000C63D
0x18000bf47  xor     ebx, ebx
0x18000bf49  mov     r12, [rbp+StringSid]
0x18000bf4d  mov     qword ptr [rbp+pvarg], r12
0x18000bf51  test    rsi, rsi
0x18000bf54  jz      short loc_18000BF72
0x18000bf56  call    cs:__imp_GetProcessHeap
0x18000bf5c  mov     rcx, rax; hHeap
0x18000bf5f  mov     r8, rsi; lpMem
0x18000bf62  xor     edx, edx; dwFlags
0x18000bf64  call    cs:__imp_HeapFree
0x18000bf6a  test    eax, eax
0x18000bf6c  jz      loc_18000C7AB
0x18000bf72  test    ebx, ebx
0x18000bf74  js      loc_18000C763
0x18000bf7a  lea     r13, [r15+30h]
0x18000bf7e  test    r12, r12
0x18000bf81  jz      loc_18000C7D3
0x18000bf87  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18000bf8e  xchg    ax, ax
0x18000bf90  inc     r15
0x18000bf93  cmp     word ptr [r12+r15*2], 0
0x18000bf99  jnz     short loc_18000BF90
0x18000bf9b  lea     rbx, [r15+1]
0x18000bf9f  cmp     rbx, r15
0x18000bfa2  jb      short loc_18000BFD3
0x18000bfa4  mov     r8, [r13+10h]
0x18000bfa8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000bfac  jz      loc_18000C497
0x18000bfb2  test    r8, r8
0x18000bfb5  jnz     loc_18000C295
0x18000bfbb  mov     [rbp+StringSid], r8
0x18000bfbf  mov     eax, 2
0x18000bfc4  mul     rbx
0x18000bfc7  mov     rdi, rax
0x18000bfca  test    rdx, rdx
0x18000bfcd  jz      loc_18000C30D
0x18000bfd3  mov     esi, 80070216h
0x18000bfd8  test    esi, esi
0x18000bfda  js      loc_18000C25C
0x18000bfe0  mov     r15, [rbp+arg_0]
0x18000bfe4  mov     rdi, [r15+48h]
0x18000bfe8  test    rdi, rdi
0x18000bfeb  jnz     loc_18000C7E0
0x18000bff1  xor     r13d, r13d
0x18000bff4  mov     [r15+48h], r13
0x18000bff8  mov     [rbp+TokenInformationLength], 0C8h
0x18000bfff  call    cs:__imp_GetProcessHeap
0x18000c005  mov     rcx, rax; hHeap
0x18000c008  mov     edx, 8; dwFlags
0x18000c00d  mov     r8d, 0C8h; dwBytes
0x18000c013  call    cs:__imp_HeapAlloc
0x18000c019  mov     rdi, rax
0x18000c01c  mov     [rbp+arg_8], rax
0x18000c020  test    rax, rax
0x18000c023  jz      loc_18000C7FE
0x18000c029  mov     esi, r13d
0x18000c02c  lea     rax, [rbp+TokenInformationLength]
0x18000c030  mov     [rsp+68h+ReturnLength], rax; int
0x18000c035  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18000c039  mov     r8, rdi; TokenInformation
0x18000c03c  mov     edx, 1; TokenInformationClass
0x18000c041  mov     rcx, r14; TokenHandle
0x18000c044  call    cs:__imp_GetTokenInformation
0x18000c04a  test    eax, eax
0x18000c04c  jz      loc_18000C6E4
0x18000c052  mov     ebx, r13d
0x18000c055  test    ebx, ebx
0x18000c057  js      short loc_18000C0A7
0x18000c059  mov     rcx, [rdi]; pSid
0x18000c05c  call    cs:__imp_GetLengthSid
0x18000c062  mov     ebx, eax
0x18000c064  mov     [rbp+TokenInformationLength], ebx
0x18000c067  call    cs:__imp_GetProcessHeap
0x18000c06d  mov     rcx, rax; hHeap
0x18000c070  mov     r8d, ebx; dwBytes
0x18000c073  mov     edx, 8; dwFlags
0x18000c078  call    cs:__imp_HeapAlloc
0x18000c07e  mov     r14, rax
0x18000c081  test    rax, rax
0x18000c084  jz      loc_18000C829
0x18000c08a  mov     r8, [rdi]; pSourceSid
0x18000c08d  mov     rdx, rax; pDestinationSid
0x18000c090  mov     ecx, [rbp+TokenInformationLength]; nDestinationSidLength
0x18000c093  call    cs:__imp_CopySid
0x18000c099  test    eax, eax
0x18000c09b  jz      loc_18000C73F
0x18000c0a1  mov     ebx, r13d
0x18000c0a4  mov     rsi, r14
0x18000c0a7  mov     r14d, 8007000Eh
0x18000c0ad  test    rdi, rdi
0x18000c0b0  jz      short loc_18000C0CE
0x18000c0b2  call    cs:__imp_GetProcessHeap
0x18000c0b8  mov     rcx, rax; hHeap
0x18000c0bb  mov     r8, rdi; lpMem
0x18000c0be  xor     edx, edx; dwFlags
0x18000c0c0  call    cs:__imp_HeapFree
0x18000c0c6  test    eax, eax
0x18000c0c8  jz      loc_18000C837
0x18000c0ce  test    ebx, ebx
0x18000c0d0  js      loc_18000C803
0x18000c0d6  mov     [rbp+arg_8], r13
0x18000c0da  lea     rdx, [rbp+arg_8]; StringSid
0x18000c0de  mov     rcx, rsi; Sid
0x18000c0e1  call    cs:__imp_ConvertSidToStringSidW
0x18000c0e7  test    eax, eax
0x18000c0e9  jz      loc_18000C6D0
0x18000c0ef  mov     ebx, r13d
0x18000c0f2  mov     rax, [rbp+arg_8]
0x18000c0f6  mov     [r15+48h], rax
0x18000c0fa  test    rsi, rsi
0x18000c0fd  jz      short loc_18000C11B
0x18000c0ff  call    cs:__imp_GetProcessHeap
0x18000c105  mov     rcx, rax; hHeap
0x18000c108  mov     r8, rsi; lpMem
0x18000c10b  xor     edx, edx; dwFlags
0x18000c10d  call    cs:__imp_HeapFree
0x18000c113  test    eax, eax
0x18000c115  jz      loc_18000C841
0x18000c11b  test    ebx, ebx
0x18000c11d  js      loc_18000C803
0x18000c123  mov     edi, r13d
0x18000c126  mov     r9, [rbp+arg_18]
0x18000c12a  test    r9, r9
0x18000c12d  jz      loc_18000C202
0x18000c133  mov     eax, [r9+4]
0x18000c137  mov     [r15+8], eax
0x18000c13b  mov     rbx, [r9+8]
0x18000c13f  test    rbx, rbx
0x18000c142  jnz     loc_18000C417
0x18000c148  mov     rdx, [r9+18h]
0x18000c14c  test    rdx, rdx
0x18000c14f  jnz     loc_18000C86A
0x18000c155  mov     r14, r13
0x18000c158  mov     rsi, [rbp+arg_28]
0x18000c15c  test    rsi, rsi
0x18000c15f  jnz     loc_18000C3A2
0x18000c165  xorps   xmm0, xmm0
0x18000c168  xor     eax, eax
0x18000c16a  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000c16e  mov     qword ptr [rbp+pvarg+10h], rax
0x18000c172  mov     [rsp+68h+var_30], r13
0x18000c177  mov     [rsp+68h+var_38], r13d
0x18000c17c  lea     rax, [rbp+pvarg]
0x18000c180  mov     [rsp+68h+ReturnLength], rax; int
0x18000c185  mov     r9d, 0Bh
0x18000c18b  mov     r8d, 22h ; '"'
0x18000c191  lea     rdx, qword_18007CB80
0x18000c198  mov     ecx, 2
0x18000c19d  call    ?GetUserStateSetting@@YAJW4UST_COMPONENT_ID@@QEBUUSERSTATE_SETTING_DESCRIPTOR@@IIAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z; GetUserStateSetting(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const * const,uint,uint,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)
0x18000c1a2  test    eax, eax
0x18000c1a4  jns     loc_18000C8AD
0x18000c1aa  mov     eax, 0FFFh
0x18000c1af  cmp     word ptr [rbp+pvarg], ax
0x18000c1b3  jnz     short loc_18000C1BE
0x18000c1b5  mov     eax, 8
0x18000c1ba  mov     word ptr [rbp+pvarg], ax
0x18000c1be  lea     rcx, [rbp+pvarg]; pvarg
0x18000c1c2  call    cs:__imp_VariantClear
0x18000c1c8  mov     eax, r13d
0x18000c1cb  mov     r13, [rbp+arg_18]
0x18000c1cf  test    eax, eax
0x18000c1d1  jnz     loc_18000C630
0x18000c1d7  mov     rsi, [r13+10h]
0x18000c1db  mov     edi, 1
0x18000c1e0  test    rsi, rsi
0x18000c1e3  jnz     loc_18000C3AB
0x18000c1e9  test    r14, r14
0x18000c1ec  jz      short loc_18000C202
0x18000c1ee  call    cs:__imp_GetProcessHeap
0x18000c1f4  mov     rcx, rax; hHeap
0x18000c1f7  mov     r8, r14; lpMem
0x18000c1fa  xor     edx, edx; dwFlags
0x18000c1fc  call    cs:__imp_HeapFree
0x18000c202  call    IsWaitForNetworkForRoamingProfilePresent
0x18000c207  test    al, al
0x18000c209  jz      short loc_18000C23E
0x18000c20b  lea     rdx, [r15+120h]
0x18000c212  mov     rcx, r15
0x18000c215  call    cs:__imp_CreateRoamingProviderInstance
0x18000c21b  mov     esi, eax
0x18000c21d  test    eax, eax
0x18000c21f  js      loc_18000C571
0x18000c225  test    edi, edi
0x18000c227  jz      short loc_18000C23E
0x18000c229  mov     rcx, [r15+120h]
0x18000c230  mov     rax, [rcx]
0x18000c233  mov     edx, edi
0x18000c235  mov     rax, [rax+40h]
0x18000c239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c23e  mov     eax, [r15+8]
0x18000c242  test    al, 4
0x18000c244  jnz     loc_18000C984
0x18000c24a  test    r12, r12
0x18000c24d  jz      short loc_18000C258
0x18000c24f  mov     rcx, r12; hMem
0x18000c252  call    cs:__imp_LocalFree
0x18000c258  xor     eax, eax
0x18000c25a  jmp     short loc_18000C284
0x18000c25c  mov     edx, 1F3h; void *
0x18000c261  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000c268  mov     r9d, esi; char *
0x18000c26b  mov     rcx, [rbp+40h]; this
0x18000c26f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c274  test    r12, r12
0x18000c277  jz      short loc_18000C282
0x18000c279  mov     rcx, r12; hMem
0x18000c27c  call    cs:__imp_LocalFree
0x18000c282  mov     eax, esi
0x18000c284  add     rsp, 68h
0x18000c288  pop     r15
0x18000c28a  pop     r14
0x18000c28c  pop     r13
0x18000c28e  pop     r12
0x18000c290  pop     rdi
  ... truncated ...
```
