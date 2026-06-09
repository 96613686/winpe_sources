# CUserProfile::Initialize(void *,void *,_PROFILEINFOW *,ulong,ushort const *)

- ea: `0x180009830`
- end: `0x18000a4dc`
- name: `?Initialize@CUserProfile@@IEAAJPEAX0PEAU_PROFILEINFOW@@KPEBG@Z`
- size: `3244`
- prototype: `__int64 __fastcall(CUserProfile *this, WCHAR *, void *, struct _PROFILEINFOW *, DWORD TokenInformationLength, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180008fa0`
- `0x18001bdd8`

## callees

- `0x180005370`
- `0x180009830`
- `0x18000a6e0`
- `0x18000b020`
- `0x18000e1a0`
- `0x180011c00`
- `0x18001214c`
- `0x180012ac8`
- `0x180019260`
- `0x180021cf0`
- `0x180024540`
- `0x180026e5c`
- `0x180027220`
- `0x18002744c`
- `0x180030ad0`
- `0x18003d678`
- `0x18003fff4`
- `0x180040bcc`
- `0x180048b60`
- `0x180049e10`
- `0x18004fcbc`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800098a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009921`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b16`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009e1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009fe8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800098a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009921`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b16`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009e1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009fe8`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180009de5`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000a062`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180009de5`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000a062`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009978`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800099d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009bcf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009cd0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009978`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800099d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009bcf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009cd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000988c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000990a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009964`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800099c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bbb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009cbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009dc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a04b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000988c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000990a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009964`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800099c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bbb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009cbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009dc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a04b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a333`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a314`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009942`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009b37`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009942`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009b37`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800098f9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009aee`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800098f9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009aee`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800098dc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009ad0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a1ba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a253`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800098dc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009ad0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a1ba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a253`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009d32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009d62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a2b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a325`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009d32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009d62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a2b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a325`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000999f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180009b97`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000999f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180009b97`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a3fb`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a3fb`
- `OLEAUT32!__imp_VariantClear` at `0x180009c8a`
- `OLEAUT32!__imp_VariantClear` at `0x180009c8a`
- `ext-ms-win-profile-profsvc-l1-1-0!CreateRoamingProviderInstance` at `0x180009cef`
- `ext-ms-win-profile-profsvc-l1-1-0!CreateRoamingProviderInstance` at `0x180009cef`

## string_xrefs

- `0x180009d47`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180009f73`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000a298`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000a350`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000a3d4`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000a491`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
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
  int ReturnLength; // [rsp+20h] [rbp-48h]
  void *v83; // [rsp+28h] [rbp-40h]
  LPWSTR StringSid; // [rsp+40h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  LPWSTR v88; // [rsp+B8h] [rbp+50h] BYREF
  void *v89; // [rsp+C0h] [rbp+58h]
  struct _PROFILEINFOW *v90; // [rsp+C8h] [rbp+60h]

  v90 = a4;
  v89 = a3;
  v88 = a2;
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
      ReturnLength);
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
    v7 = v88;
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
    v7 = v88;
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
      ReturnLength);
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
  v88 = v27;
  if ( !v27 )
  {
    Error = -2147024882;
LABEL_182:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
      (const char *)(unsigned int)Error,
      ReturnLength);
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
      Error = ResultFromHeapReAlloc(v27, TokenInformationLength, (void **)&v88);
      v27 = v88;
      if ( Error < 0 )
        goto LABEL_41;
      v74 = GetTokenInformation(v7, TokenUser, v88, TokenInformationLength, &TokenInformationLength);
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
  v88 = 0;
  if ( ConvertSidToStringSidW(v28, &v88) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_49;
  }
  *((_QWORD *)v8 + 9) = v88;
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
  v37 = v90;
  if ( !v90 )
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
  *((_DWORD *)v8 + 2) = v90->dwFlags;
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
          ReturnLength);
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::~NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>(&pvarg);
        return (unsigned int)Error;
      }
    }
    v40 = 0;
    lpProfilePath = a6;
    if ( a6 )
    {
      v36 = 3;
      v43 = v90;
      goto LABEL_105;
    }
    memset(&pvarg, 0, sizeof(pvarg));
    if ( (int)GetUserStateSetting(2u, (__int64)qword_18007FC90, 0x22u, 11, &pvarg, (__int64)v83, 0, 0) >= 0 )
    {
      v88 = 0;
      v77 = SysStringLen(pvarg.bstrVal) + 1;
      v78 = ResultFromHeapAllocArray<unsigned short>(v77, &v88);
      if ( v78 >= 0 )
      {
        v78 = StringCchCopyW(v88, v77, pvarg.bstrVal);
        if ( v78 >= 0 )
        {
          v40 = v80;
          v88 = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v88);
          ATL::CComVariant::~CComVariant((ATL::CComVariant *)&pvarg);
          v42 = 1;
LABEL_62:
          v43 = v90;
          if ( v42 )
          {
            lpProfilePath = v40;
            v36 = 2;
          }
          else
          {
            lpProfilePath = v90->lpProfilePath;
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
                  v89);
          v59 = v58;
          if ( v58 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x225,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
              (const char *)(unsigned int)v58,
              ReturnLength);
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
        ReturnLength);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long ResultFromHeapFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v88);
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
    v88 = 0;
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
    v37 = v90;
    goto LABEL_145;
  }
  v88 = 0;
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
    ReturnLength);
  if ( v9 )
    LocalFree(v9);
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x180009830  mov     [rsp-40h+arg_18], r9
0x180009835  mov     [rsp-40h+arg_10], r8
0x18000983a  mov     [rsp-40h+arg_8], rdx
0x18000983f  mov     [rsp-40h+arg_0], rcx
0x180009844  push    rbp
0x180009845  push    rbx
0x180009846  push    rsi
0x180009847  push    rdi
0x180009848  push    r12
0x18000984a  push    r13
0x18000984c  push    r14
0x18000984e  push    r15
0x180009850  mov     rbp, rsp
0x180009853  sub     rsp, 68h
0x180009857  mov     r13, r8
0x18000985a  mov     r14, rdx
0x18000985d  mov     r15, rcx
0x180009860  mov     [rcx+20h], rdx
0x180009864  mov     [rcx+18h], r8
0x180009868  mov     eax, [rbp+TokenInformationLength]
0x18000986b  mov     [rcx+14h], eax
0x18000986e  xor     r12d, r12d
0x180009871  mov     qword ptr [rbp+pvarg], r12
0x180009875  mov     qword ptr [rbp+pvarg+8], 0FFFFFFFFFFFFFFFFh
0x18000987d  mov     qword ptr [rbp+pvarg+10h], 0FFFFFFFFFFFFFFFFh
0x180009885  mov     [rbp+TokenInformationLength], 0C8h
0x18000988c  call    cs:__imp_GetProcessHeap
0x180009893  nop     dword ptr [rax+rax+00h]
0x180009898  mov     rcx, rax; hHeap
0x18000989b  mov     edx, 8; dwFlags
0x1800098a0  mov     r8d, 0C8h; dwBytes
0x1800098a6  call    cs:__imp_HeapAlloc
0x1800098ad  nop     dword ptr [rax+rax+00h]
0x1800098b2  mov     rdi, rax
0x1800098b5  mov     [rbp+StringSid], rax
0x1800098b9  test    rax, rax
0x1800098bc  jz      loc_18000A2C4
0x1800098c2  xor     esi, esi
0x1800098c4  lea     rax, [rbp+TokenInformationLength]
0x1800098c8  mov     [rsp+68h+ReturnLength], rax; int
0x1800098cd  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800098d1  mov     r8, rdi; TokenInformation
0x1800098d4  mov     edx, 1; TokenInformationClass
0x1800098d9  mov     rcx, r13; TokenHandle
0x1800098dc  call    cs:__imp_GetTokenInformation
0x1800098e3  nop     dword ptr [rax+rax+00h]
0x1800098e8  test    eax, eax
0x1800098ea  jz      loc_18000A173
0x1800098f0  xor     ebx, ebx
0x1800098f2  test    ebx, ebx
0x1800098f4  js      short loc_18000995F
0x1800098f6  mov     rcx, [rdi]; pSid
0x1800098f9  call    cs:__imp_GetLengthSid
0x180009900  nop     dword ptr [rax+rax+00h]
0x180009905  mov     ebx, eax
0x180009907  mov     [rbp+TokenInformationLength], ebx
0x18000990a  call    cs:__imp_GetProcessHeap
0x180009911  nop     dword ptr [rax+rax+00h]
0x180009916  mov     rcx, rax; hHeap
0x180009919  mov     r8d, ebx; dwBytes
0x18000991c  mov     edx, 8; dwFlags
0x180009921  call    cs:__imp_HeapAlloc
0x180009928  nop     dword ptr [rax+rax+00h]
0x18000992d  mov     r14, rax
0x180009930  test    rax, rax
0x180009933  jz      loc_18000A2CB
0x180009939  mov     r8, [rdi]; pSourceSid
0x18000993c  mov     rdx, rax; pDestinationSid
0x18000993f  mov     ecx, [rbp+TokenInformationLength]; nDestinationSidLength
0x180009942  call    cs:__imp_CopySid
0x180009949  nop     dword ptr [rax+rax+00h]
0x18000994e  test    eax, eax
0x180009950  jz      loc_18000A1DC
0x180009956  xor     ebx, ebx
0x180009958  mov     rsi, r14
0x18000995b  mov     r14, [rbp+arg_8]
0x18000995f  test    rdi, rdi
0x180009962  jz      short loc_18000998C
0x180009964  call    cs:__imp_GetProcessHeap
0x18000996b  nop     dword ptr [rax+rax+00h]
0x180009970  mov     rcx, rax; hHeap
0x180009973  mov     r8, rdi; lpMem
0x180009976  xor     edx, edx; dwFlags
0x180009978  call    cs:__imp_HeapFree
0x18000997f  nop     dword ptr [rax+rax+00h]
0x180009984  test    eax, eax
0x180009986  jz      loc_18000A2D5
0x18000998c  test    ebx, ebx
0x18000998e  js      loc_18000A291
0x180009994  mov     [rbp+StringSid], r12
0x180009998  lea     rdx, [rbp+StringSid]; StringSid
0x18000999c  mov     rcx, rsi; Sid
0x18000999f  call    cs:__imp_ConvertSidToStringSidW
0x1800099a6  nop     dword ptr [rax+rax+00h]
0x1800099ab  test    eax, eax
0x1800099ad  jz      loc_18000A15F
0x1800099b3  xor     ebx, ebx
0x1800099b5  mov     r12, [rbp+StringSid]
0x1800099b9  mov     qword ptr [rbp+pvarg], r12
0x1800099bd  test    rsi, rsi
0x1800099c0  jz      short loc_1800099EA
0x1800099c2  call    cs:__imp_GetProcessHeap
0x1800099c9  nop     dword ptr [rax+rax+00h]
0x1800099ce  mov     rcx, rax; hHeap
0x1800099d1  mov     r8, rsi; lpMem
0x1800099d4  xor     edx, edx; dwFlags
0x1800099d6  call    cs:__imp_HeapFree
0x1800099dd  nop     dword ptr [rax+rax+00h]
0x1800099e2  test    eax, eax
0x1800099e4  jz      loc_18000A2DF
0x1800099ea  test    ebx, ebx
0x1800099ec  js      loc_18000A291
0x1800099f2  lea     r13, [r15+30h]
0x1800099f6  test    r12, r12
0x1800099f9  jz      loc_18000A307
0x1800099ff  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180009a06  nop     word ptr [rax+rax+00000000h]
0x180009a10  inc     r15
0x180009a13  cmp     word ptr [r12+r15*2], 0
0x180009a19  jnz     short loc_180009A10
0x180009a1b  lea     rbx, [r15+1]
0x180009a1f  cmp     rbx, r15
0x180009a22  jb      short loc_180009A53
0x180009a24  mov     r8, [r13+10h]
0x180009a28  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180009a2c  jz      loc_180009FA0
0x180009a32  test    r8, r8
0x180009a35  jnz     loc_180009D82
0x180009a3b  mov     [rbp+StringSid], r8
0x180009a3f  mov     eax, 2
0x180009a44  mul     rbx
0x180009a47  mov     rdi, rax
0x180009a4a  test    rdx, rdx
0x180009a4d  jz      loc_180009E06
0x180009a53  mov     esi, 80070216h
0x180009a58  test    esi, esi
0x180009a5a  js      loc_180009D42
0x180009a60  mov     r15, [rbp+arg_0]
0x180009a64  mov     rdi, [r15+48h]
0x180009a68  test    rdi, rdi
0x180009a6b  jnz     loc_18000A314
0x180009a71  xor     r13d, r13d
0x180009a74  mov     [r15+48h], r13
0x180009a78  mov     [rbp+TokenInformationLength], 0C8h
0x180009a7f  call    cs:__imp_GetProcessHeap
0x180009a86  nop     dword ptr [rax+rax+00h]
0x180009a8b  mov     rcx, rax; hHeap
0x180009a8e  mov     edx, 8; dwFlags
0x180009a93  mov     r8d, 0C8h; dwBytes
0x180009a99  call    cs:__imp_HeapAlloc
0x180009aa0  nop     dword ptr [rax+rax+00h]
0x180009aa5  mov     rdi, rax
0x180009aa8  mov     [rbp+arg_8], rax
0x180009aac  test    rax, rax
0x180009aaf  jz      loc_18000A344
0x180009ab5  mov     esi, r13d
0x180009ab8  lea     rax, [rbp+TokenInformationLength]
0x180009abc  mov     [rsp+68h+ReturnLength], rax; int
0x180009ac1  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180009ac5  mov     r8, rdi; TokenInformation
0x180009ac8  mov     edx, 1; TokenInformationClass
0x180009acd  mov     rcx, r14; TokenHandle
0x180009ad0  call    cs:__imp_GetTokenInformation
0x180009ad7  nop     dword ptr [rax+rax+00h]
0x180009adc  test    eax, eax
0x180009ade  jz      loc_18000A20C
0x180009ae4  mov     ebx, r13d
0x180009ae7  test    ebx, ebx
0x180009ae9  js      short loc_180009B51
0x180009aeb  mov     rcx, [rdi]; pSid
0x180009aee  call    cs:__imp_GetLengthSid
0x180009af5  nop     dword ptr [rax+rax+00h]
0x180009afa  mov     ebx, eax
0x180009afc  mov     [rbp+TokenInformationLength], ebx
0x180009aff  call    cs:__imp_GetProcessHeap
0x180009b06  nop     dword ptr [rax+rax+00h]
0x180009b0b  mov     rcx, rax; hHeap
0x180009b0e  mov     r8d, ebx; dwBytes
0x180009b11  mov     edx, 8; dwFlags
0x180009b16  call    cs:__imp_HeapAlloc
0x180009b1d  nop     dword ptr [rax+rax+00h]
0x180009b22  mov     r14, rax
0x180009b25  test    rax, rax
0x180009b28  jz      loc_18000A36F
0x180009b2e  mov     r8, [rdi]; pSourceSid
0x180009b31  mov     rdx, rax; pDestinationSid
0x180009b34  mov     ecx, [rbp+TokenInformationLength]; nDestinationSidLength
0x180009b37  call    cs:__imp_CopySid
0x180009b3e  nop     dword ptr [rax+rax+00h]
0x180009b43  test    eax, eax
0x180009b45  jz      loc_18000A26D
0x180009b4b  mov     ebx, r13d
0x180009b4e  mov     rsi, r14
0x180009b51  mov     r14d, 8007000Eh
0x180009b57  test    rdi, rdi
0x180009b5a  jz      short loc_180009B84
0x180009b5c  call    cs:__imp_GetProcessHeap
0x180009b63  nop     dword ptr [rax+rax+00h]
0x180009b68  mov     rcx, rax; hHeap
0x180009b6b  mov     r8, rdi; lpMem
0x180009b6e  xor     edx, edx; dwFlags
0x180009b70  call    cs:__imp_HeapFree
0x180009b77  nop     dword ptr [rax+rax+00h]
0x180009b7c  test    eax, eax
0x180009b7e  jz      loc_18000A37D
0x180009b84  test    ebx, ebx
0x180009b86  js      loc_18000A349
0x180009b8c  mov     [rbp+arg_8], r13
0x180009b90  lea     rdx, [rbp+arg_8]; StringSid
0x180009b94  mov     rcx, rsi; Sid
0x180009b97  call    cs:__imp_ConvertSidToStringSidW
0x180009b9e  nop     dword ptr [rax+rax+00h]
0x180009ba3  test    eax, eax
0x180009ba5  jz      loc_18000A1F8
0x180009bab  mov     ebx, r13d
0x180009bae  mov     rax, [rbp+arg_8]
0x180009bb2  mov     [r15+48h], rax
0x180009bb6  test    rsi, rsi
0x180009bb9  jz      short loc_180009BE3
0x180009bbb  call    cs:__imp_GetProcessHeap
0x180009bc2  nop     dword ptr [rax+rax+00h]
0x180009bc7  mov     rcx, rax; hHeap
0x180009bca  mov     r8, rsi; lpMem
0x180009bcd  xor     edx, edx; dwFlags
0x180009bcf  call    cs:__imp_HeapFree
0x180009bd6  nop     dword ptr [rax+rax+00h]
0x180009bdb  test    eax, eax
0x180009bdd  jz      loc_18000A387
0x180009be3  test    ebx, ebx
0x180009be5  js      loc_18000A349
0x180009beb  mov     edi, r13d
0x180009bee  mov     r9, [rbp+arg_18]
0x180009bf2  test    r9, r9
0x180009bf5  jz      loc_180009CDC
0x180009bfb  mov     eax, [r9+4]
0x180009bff  mov     [r15+8], eax
0x180009c03  mov     rbx, [r9+8]
0x180009c07  test    rbx, rbx
0x180009c0a  jnz     loc_180009F1C
0x180009c10  mov     rdx, [r9+18h]
0x180009c14  test    rdx, rdx
0x180009c17  jnz     loc_18000A3B0
0x180009c1d  mov     r14, r13
0x180009c20  mov     rsi, [rbp+arg_28]
0x180009c24  test    rsi, rsi
0x180009c27  jnz     loc_180009EA7
0x180009c2d  xorps   xmm0, xmm0
0x180009c30  xor     eax, eax
0x180009c32  movups  xmmword ptr [rbp+pvarg], xmm0
0x180009c36  mov     qword ptr [rbp+pvarg+10h], rax
0x180009c3a  mov     [rsp+68h+var_30], r13
0x180009c3f  mov     [rsp+68h+var_38], r13d
0x180009c44  lea     rax, [rbp+pvarg]
0x180009c48  mov     [rsp+68h+ReturnLength], rax; int
0x180009c4d  mov     r9d, 0Bh
0x180009c53  mov     r8d, 22h ; '"'
0x180009c59  lea     rdx, qword_18007FC90
0x180009c60  mov     ecx, 2
0x180009c65  call    ?GetUserStateSetting@@YAJW4UST_COMPONENT_ID@@QEBUUSERSTATE_SETTING_DESCRIPTOR@@IIAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z; GetUserStateSetting(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const * const,uint,uint,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)
0x180009c6a  test    eax, eax
0x180009c6c  jns     loc_18000A3F3
0x180009c72  mov     eax, 0FFFh
0x180009c77  cmp     word ptr [rbp+pvarg], ax
0x180009c7b  jnz     short loc_180009C86
0x180009c7d  mov     eax, 8
0x180009c82  mov     word ptr [rbp+pvarg], ax
0x180009c86  lea     rcx, [rbp+pvarg]; pvarg
0x180009c8a  call    cs:__imp_VariantClear
0x180009c91  nop     dword ptr [rax+rax+00h]
0x180009c96  mov     eax, r13d
0x180009c99  mov     r13, [rbp+arg_18]
0x180009c9d  test    eax, eax
0x180009c9f  jnz     loc_18000A152
0x180009ca5  mov     rsi, [r13+10h]
0x180009ca9  mov     edi, 1
0x180009cae  test    rsi, rsi
0x180009cb1  jnz     loc_180009EB0
0x180009cb7  test    r14, r14
0x180009cba  jz      short loc_180009CDC
0x180009cbc  call    cs:__imp_GetProcessHeap
0x180009cc3  nop     dword ptr [rax+rax+00h]
0x180009cc8  mov     rcx, rax; hHeap
0x180009ccb  mov     r8, r14; lpMem
0x180009cce  xor     edx, edx; dwFlags
0x180009cd0  call    cs:__imp_HeapFree
0x180009cd7  nop     dword ptr [rax+rax+00h]
0x180009cdc  call    IsWaitForNetworkForRoamingProfilePresent
0x180009ce1  test    al, al
0x180009ce3  jz      short loc_180009D1E
0x180009ce5  lea     rdx, [r15+120h]
0x180009cec  mov     rcx, r15
0x180009cef  call    cs:__imp_CreateRoamingProviderInstance
0x180009cf6  nop     dword ptr [rax+rax+00h]
0x180009cfb  mov     esi, eax
0x180009cfd  test    eax, eax
0x180009cff  js      loc_18000A093
0x180009d05  test    edi, edi
0x180009d07  jz      short loc_180009D1E
0x180009d09  mov     rcx, [r15+120h]
0x180009d10  mov     rax, [rcx]
  ... truncated ...
```
