# AdvertisingIdHelpers::SetDaclForRootKey(HKEY__ *,ushort const *)

- ea: `0x180002b70`
- end: `0x1800032b4`
- name: `?SetDaclForRootKey@AdvertisingIdHelpers@@YAJPEAUHKEY__@@PEBG@Z`
- size: `1860`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY lpString2, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001af0`
- `0x1800061c4`

## callees

- `0x180001790`
- `0x180002b70`
- `0x1800032c0`
- `0x180004d70`
- `0x1800058d0`
- `0x180005d90`
- `0x1800064d0`
- `0x18000951c`
- `0x180009d9e`
- `0x180009dd0`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x180002e1d`
- `ntdll!RtlIsMultiSessionSku` at `0x180002e1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003296`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800032a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800032a9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180002fdf`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180002fdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ef0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000328b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800032a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ef0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000328b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800032a1`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180002e9b`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180002e9b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003072`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180002ee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180002ee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002cfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002e0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002ebb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002f21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002f65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002cfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002e0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002ebb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002f21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002f65`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002e60`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002e60`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000302b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000302b`

## pseudocode

```c
__int64 __fastcall AdvertisingIdHelpers::SetDaclForRootKey(
        HKEY hKey,
        const WCHAR *lpString2,
        const unsigned __int16 *a3)
{
  struct Windows::Internal::String *v5; // rdx
  HSTRING v6; // rbx
  WCHAR *v7; // rdx
  WCHAR *v8; // r9
  unsigned __int64 v9; // rdi
  __int64 v10; // rsi
  __int64 v11; // r8
  __int64 v12; // rcx
  WCHAR *v13; // rcx
  int v14; // r15d
  int v15; // r14d
  __int64 v16; // rdx
  WCHAR *v18; // rax
  _WORD *v19; // rdx
  unsigned __int16 *v20; // rcx
  _WORD *v21; // rcx
  unsigned int v22; // r8d
  const char *v23; // r9
  BOOL v24; // r12d
  void **v25; // rsi
  PSECURITY_DESCRIPTOR v26; // r15
  void *v27; // r14
  unsigned int v28; // eax
  int CurrentUserSid; // eax
  unsigned int v30; // ebx
  unsigned int v31; // eax
  void *v32; // rcx
  unsigned int LastError; // edi
  unsigned int v34; // eax
  unsigned int v35; // r8d
  const char *v36; // r9
  BOOL v37; // edi
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // eax
  unsigned __int64 v41; // rdx
  unsigned __int16 **v42; // r9
  int v43; // eax
  int v44; // eax
  unsigned __int64 v45; // rdx
  unsigned __int16 **v46; // r9
  int v47; // eax
  HSTRING v48; // rcx
  DWORD v49; // edi
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  unsigned int v52; // [rsp+28h] [rbp-D8h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbSid; // [rsp+40h] [rbp-C0h] BYREF
  void **p_string; // [rsp+48h] [rbp-B8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  char v58; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v59[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v60; // [rsp+70h] [rbp-90h]
  wchar_t v61; // [rsp+80h] [rbp-80h]
  _OWORD pSid[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v63; // [rsp+110h] [rbp+10h]
  _OWORD v64[12]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t v65; // [rsp+1E0h] [rbp+E0h]
  unsigned __int16 v66[256]; // [rsp+1F0h] [rbp+F0h] BYREF
  WCHAR StringSecurityDescriptor[620]; // [rsp+3F0h] [rbp+2F0h] BYREF
  _BYTE v68[8]; // [rsp+8C8h] [rbp+7C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+918h] [rbp+818h]

  pSid[0] = *(_OWORD *)L"D:P(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A;OICI;KR;;;AC)(A;OICI;KR;;;RC)";
  pSid[2] = *(_OWORD *)L"SY)(A;OICI;KA;;;BA)(A;OICI;KR;;;AC)(A;OICI;KR;;;RC)";
  pSid[1] = *(_OWORD *)L"CI;KA;;;SY)(A;OICI;KA;;;BA)(A;OICI;KR;;;AC)(A;OICI;KR;;;RC)";
  pSid[4] = *(_OWORD *)L"BA)(A;OICI;KR;;;AC)(A;OICI;KR;;;RC)";
  pSid[3] = *(_OWORD *)L"CI;KA;;;BA)(A;OICI;KR;;;AC)(A;OICI;KR;;;RC)";
  pSid[6] = *(_OWORD *)L"AC)(A;OICI;KR;;;RC)";
  pSid[5] = *(_OWORD *)L"CI;KR;;;AC)(A;OICI;KR;;;RC)";
  v63 = *(_QWORD *)L"RC)";
  pSid[7] = *(_OWORD *)L"CI;KR;;;RC)";
  memset_0(StringSecurityDescriptor, 0, sizeof(StringSecurityDescriptor));
  v61 = aAOiciKaS[16];
  *(_OWORD *)v59 = *(_OWORD *)L"(A;OICI;KA;;;%s)";
  v60 = *(_OWORD *)L"KA;;;%s)";
  memset_0(v66, 0, 0x1F8u);
  v6 = 0;
  string = 0;
  if ( lpString2 )
    goto LABEL_2;
  CurrentUserSid = AdvertisingIdHelpers::GetCurrentUserSid((AdvertisingIdHelpers *)&string, v5);
  v30 = CurrentUserSid;
  if ( CurrentUserSid >= 0 )
  {
    v6 = string;
    lpString2 = WindowsGetStringRawBuffer(string, 0);
LABEL_2:
    v7 = (WCHAR *)pSid;
    v8 = StringSecurityDescriptor;
    v9 = 620;
    v10 = 2147483646;
    v11 = 620;
    v12 = 2147483646;
    do
    {
      if ( !v12 )
        break;
      if ( !*v7 )
        break;
      *v8++ = *v7++;
      --v12;
      --v11;
    }
    while ( v11 );
    v13 = v8 - 1;
    v14 = -2147024774;
    v15 = -2147024774;
    if ( v11 )
    {
      v13 = v8;
      v15 = 0;
    }
    *v13 = 0;
    if ( !v11 )
    {
      v16 = 281;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
        (const char *)(unsigned int)v15,
        bIgnoreCase);
      if ( v6 )
        WindowsDeleteString(v6);
      return (unsigned int)v15;
    }
    v15 = StringCchPrintfW(v66, 0xFCu, v59, lpString2);
    if ( v15 < 0 )
    {
      v16 = 288;
      goto LABEL_10;
    }
    v18 = StringSecurityDescriptor;
    do
    {
      if ( !*v18 )
        break;
      ++v18;
      --v9;
    }
    while ( v9 );
    if ( v9 )
    {
      if ( v9 > 1 )
      {
        v19 = &v68[-2 * v9];
        v20 = v66;
        do
        {
          if ( !v10 )
            break;
          if ( !*v20 )
            break;
          *v19++ = *v20++;
          --v10;
          --v9;
        }
        while ( v9 );
        v21 = v19 - 1;
        if ( v9 )
        {
          v21 = v19;
          v14 = 0;
        }
        *v21 = 0;
        if ( v14 < 0 )
          goto LABEL_26;
LABEL_29:
        if ( (unsigned __int8)RtlIsMultiSessionSku() )
          goto LABEL_30;
        memset_0(pSid, 0, 0x44u);
        cbSid = 68;
        if ( !CreateWellKnownSid(WinAccountProtectedUsersSid|WinCreatorGroupSid, 0, pSid, &cbSid) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x134, v35, v36);
          goto LABEL_44;
        }
        string = 0;
        p_string = (void **)&string;
        SecurityDescriptor = 0;
        v58 = 1;
        v37 = ConvertSidToStringSidW(pSid, (LPWSTR *)&SecurityDescriptor);
        wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_string);
        if ( v37 )
        {
          if ( CompareStringOrdinal((LPCWCH)string, -1, lpString2, -1, 1) != 2 )
          {
            v40 = StringCchPrintfW(v66, 0xFCu, v59, string);
            LastError = v40;
            if ( v40 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x140,
                (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
                (const char *)(unsigned int)v40,
                (int)bIgnoreCasea);
              v32 = string;
              string = 0;
              if ( !v32 )
                goto LABEL_44;
              goto LABEL_53;
            }
            v43 = StringCchCatExW(StringSecurityDescriptor, v41, v66, v42, bIgnoreCasea, v52);
            LastError = v43;
            if ( v43 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x147,
                (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
                (const char *)(unsigned int)v43,
                (int)bIgnoreCasea);
              v32 = string;
              string = 0;
              if ( !v32 )
                goto LABEL_44;
              goto LABEL_53;
            }
          }
          v64[0] = *(_OWORD *)L"S-1-15-3-1024-3167453650-624722384-889205278-321484983-714554697-3592933102-807660695-1632717421";
          v65 = aS1153102431674[96];
          v64[1] = *(_OWORD *)L"-1024-3167453650-624722384-889205278-321484983-714554697-3592933102-807660695-1632717421";
          v64[2] = *(_OWORD *)L"67453650-624722384-889205278-321484983-714554697-3592933102-807660695-1632717421";
          v64[3] = *(_OWORD *)L"-624722384-889205278-321484983-714554697-3592933102-807660695-1632717421";
          v64[4] = *(_OWORD *)L"84-889205278-321484983-714554697-3592933102-807660695-1632717421";
          v64[5] = *(_OWORD *)L"5278-321484983-714554697-3592933102-807660695-1632717421";
          v64[6] = *(_OWORD *)L"484983-714554697-3592933102-807660695-1632717421";
          v64[7] = *(_OWORD *)L"14554697-3592933102-807660695-1632717421";
          v64[8] = *(_OWORD *)L"-3592933102-807660695-1632717421";
          v64[9] = *(_OWORD *)L"102-807660695-1632717421";
          v64[10] = *(_OWORD *)L"60695-1632717421";
          v64[11] = *(_OWORD *)L"32717421";
          v44 = StringCchPrintfW(v66, 0xFCu, v59, v64);
          LastError = v44;
          if ( v44 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x150,
              (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
              (const char *)(unsigned int)v44,
              (int)bIgnoreCasea);
            v32 = string;
            string = 0;
            if ( !v32 )
              goto LABEL_44;
            goto LABEL_53;
          }
          v47 = StringCchCatExW(StringSecurityDescriptor, v45, v66, v46, bIgnoreCasea, v52);
          LastError = v47;
          if ( v47 >= 0 )
          {
            v48 = string;
            string = 0;
            if ( v48 )
              LocalFree(v48);
LABEL_30:
            pSecurityDescriptor = 0;
            p_string = &pSecurityDescriptor;
            SecurityDescriptor = 0;
            v58 = 1;
            v24 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
                    StringSecurityDescriptor,
                    1u,
                    &SecurityDescriptor,
                    0);
            if ( v58 )
            {
              v25 = p_string;
              v26 = SecurityDescriptor;
              v27 = *p_string;
              if ( *p_string )
              {
                v49 = GetLastError();
                LocalFree(v27);
                SetLastError(v49);
              }
              *v25 = v26;
            }
            if ( v24 )
            {
              v28 = RegSetKeySecurity(hKey, 4u, pSecurityDescriptor);
              if ( !v28 )
              {
                if ( pSecurityDescriptor )
                  LocalFree(pSecurityDescriptor);
                if ( v6 )
                  WindowsDeleteString(v6);
                return 0;
              }
              v34 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x164,
                      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
                      (const char *)v28,
                      bIgnoreCase);
              v32 = pSecurityDescriptor;
              LastError = v34;
              if ( !pSecurityDescriptor )
                goto LABEL_44;
            }
            else
            {
              v31 = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x15F, v22, v23);
              v32 = pSecurityDescriptor;
              LastError = v31;
              if ( !pSecurityDescriptor )
              {
LABEL_44:
                if ( v6 )
                  WindowsDeleteString(v6);
                return LastError;
              }
            }
LABEL_53:
            LocalFree(v32);
            goto LABEL_44;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x157,
            (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
            (const char *)(unsigned int)v47,
            bIgnoreCase);
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x137, v38, v39);
        }
        v32 = string;
        string = 0;
        if ( !v32 )
          goto LABEL_44;
        goto LABEL_53;
      }
      if ( !v66[0] )
        goto LABEL_29;
    }
    else
    {
      v14 = -2147024809;
    }
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x127,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)(unsigned int)v14,
      bIgnoreCase);
    if ( v6 )
      WindowsDeleteString(v6);
    return (unsigned int)v14;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x111,
    (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
    (const char *)(unsigned int)CurrentUserSid,
    bIgnoreCase);
  if ( string )
    WindowsDeleteString(string);
  return v30;
}

```

## disassembly

```asm
0x180002b70  push    rbp
0x180002b72  push    rbx
0x180002b73  push    r12
0x180002b75  push    r13
0x180002b77  lea     rbp, [rsp-7F8h]
0x180002b7f  sub     rsp, 8F8h
0x180002b86  mov     rax, cs:__security_cookie
0x180002b8d  xor     rax, rsp
0x180002b90  mov     [rbp+810h+var_40], rax
0x180002b97  movaps  xmm0, xmmword ptr cs:aDPAOiciKaSyAOi; "D:P(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A;O"...
0x180002b9e  mov     r12, rdx
0x180002ba1  movaps  xmm1, xmmword ptr cs:aDPAOiciKaSyAOi+10h; "CI;KA;;;SY)(A;OICI;KA;;;BA)(A;OICI;KR;;"...
0x180002ba8  mov     r13, rcx
0x180002bab  movaps  [rbp+810h+pSid], xmm0
0x180002baf  lea     rcx, [rbp+810h+StringSecurityDescriptor]; void *
0x180002bb6  movaps  xmm0, xmmword ptr cs:aDPAOiciKaSyAOi+20h; "SY)(A;OICI;KA;;;BA)(A;OICI;KR;;;AC)(A;O"...
0x180002bbd  xor     edx, edx; Val
0x180002bbf  movaps  [rbp+810h+var_860], xmm0
0x180002bc3  mov     r8d, 4D8h; Size
0x180002bc9  movaps  xmm0, xmmword ptr cs:aDPAOiciKaSyAOi+40h; "BA)(A;OICI;KR;;;AC)(A;OICI;KR;;;RC)"
0x180002bd0  movaps  [rbp+810h+var_870], xmm1
0x180002bd4  movaps  xmm1, xmmword ptr cs:aDPAOiciKaSyAOi+30h; "CI;KA;;;BA)(A;OICI;KR;;;AC)(A;OICI;KR;;"...
0x180002bdb  movaps  [rbp+810h+var_840], xmm0
0x180002bdf  movaps  xmm0, xmmword ptr cs:aDPAOiciKaSyAOi+60h; "AC)(A;OICI;KR;;;RC)"
0x180002be6  movaps  [rbp+810h+var_850], xmm1
0x180002bea  movaps  xmm1, xmmword ptr cs:aDPAOiciKaSyAOi+50h; "CI;KR;;;AC)(A;OICI;KR;;;RC)"
0x180002bf1  movaps  [rbp+810h+var_820], xmm0
0x180002bf5  movsd   xmm0, qword ptr cs:aDPAOiciKaSyAOi+80h; "RC)"
0x180002bfd  movaps  [rbp+810h+var_830], xmm1
0x180002c01  movaps  xmm1, xmmword ptr cs:aDPAOiciKaSyAOi+70h; "CI;KR;;;RC)"
0x180002c08  movsd   [rbp+810h+var_800], xmm0
0x180002c0d  movaps  [rbp+810h+var_810], xmm1
0x180002c11  call    memset_0
0x180002c16  movups  xmm0, xmmword ptr cs:aAOiciKaS; "(A;OICI;KA;;;%s)"
0x180002c1d  movzx   eax, word ptr cs:aAOiciKaS+20h; ""
0x180002c24  xor     edx, edx; Val
0x180002c26  movups  xmm1, xmmword ptr cs:aAOiciKaS+10h; "KA;;;%s)"
0x180002c2d  mov     r8d, 1F8h; Size
0x180002c33  mov     [rbp+810h+var_890], ax
0x180002c37  lea     rcx, [rbp+810h+var_720]; void *
0x180002c3e  movups  xmmword ptr [rsp+910h+var_8B0], xmm0
0x180002c43  movups  [rsp+910h+var_8A0], xmm1
0x180002c48  call    memset_0
0x180002c4d  xor     ebx, ebx
0x180002c4f  mov     [rsp+910h+string], rbx
0x180002c54  test    r12, r12
0x180002c57  jz      loc_180002EC8
0x180002c5d  mov     [rsp+910h+arg_10], rsi
0x180002c65  lea     rdx, [rbp+810h+pSid]
0x180002c69  mov     [rsp+910h+var_20], rdi
0x180002c71  lea     r9, [rbp+810h+StringSecurityDescriptor]
0x180002c78  mov     edi, 26Ch
0x180002c7d  mov     [rsp+910h+var_28], r14
0x180002c85  mov     esi, 7FFFFFFEh
0x180002c8a  mov     [rsp+910h+var_30], r15
0x180002c92  mov     r8d, edi
0x180002c95  mov     ecx, esi
0x180002c97  test    rcx, rcx
0x180002c9a  jz      short loc_180002CB9
0x180002c9c  movzx   eax, word ptr [rdx]
0x180002c9f  test    ax, ax
0x180002ca2  jz      short loc_180002CB9
0x180002ca4  mov     [r9], ax
0x180002ca8  add     rdx, 2
0x180002cac  add     r9, 2
0x180002cb0  dec     rcx
0x180002cb3  sub     r8, 1
0x180002cb7  jnz     short loc_180002C97
0x180002cb9  xor     eax, eax
0x180002cbb  lea     rcx, [r9-2]
0x180002cbf  test    r8, r8
0x180002cc2  mov     r15d, 8007007Ah
0x180002cc8  mov     r14d, r15d
0x180002ccb  cmovnz  rcx, r9
0x180002ccf  cmovnz  r14d, eax
0x180002cd3  mov     [rcx], ax
0x180002cd6  jnz     short loc_180002D41
0x180002cd8  mov     edx, 119h; void *
0x180002cdd  mov     rcx, [rbp+818h]; this
0x180002ce4  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180002ceb  mov     r9d, r14d; char *
0x180002cee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002cf3  test    rbx, rbx
0x180002cf6  jz      short loc_180002D01
0x180002cf8  mov     rcx, rbx; string
0x180002cfb  call    cs:__imp_WindowsDeleteString
0x180002d01  mov     eax, r14d
0x180002d04  mov     r14, [rsp+910h+var_28]
0x180002d0c  mov     rdi, [rsp+910h+var_20]
0x180002d14  mov     rsi, [rsp+910h+arg_10]
0x180002d1c  mov     r15, [rsp+910h+var_30]
0x180002d24  mov     rcx, [rbp+810h+var_40]
0x180002d2b  xor     rcx, rsp; StackCookie
0x180002d2e  call    __security_check_cookie
0x180002d33  add     rsp, 8F8h
0x180002d3a  pop     r13
0x180002d3c  pop     r12
0x180002d3e  pop     rbx
0x180002d3f  pop     rbp
0x180002d40  retn
0x180002d41  mov     r9, r12
0x180002d44  lea     r8, [rsp+910h+var_8B0]; unsigned __int16 *
0x180002d49  mov     edx, 0FCh; unsigned __int64
0x180002d4e  lea     rcx, [rbp+810h+var_720]; unsigned __int16 *
0x180002d55  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002d5a  mov     r14d, eax
0x180002d5d  test    eax, eax
0x180002d5f  js      loc_180002F2E
0x180002d65  lea     rax, [rbp+810h+StringSecurityDescriptor]
0x180002d6c  nop     dword ptr [rax+00h]
0x180002d70  cmp     word ptr [rax], 0
0x180002d74  jz      short loc_180002D80
0x180002d76  add     rax, 2
0x180002d7a  sub     rdi, 1
0x180002d7e  jnz     short loc_180002D70
0x180002d80  xor     eax, eax
0x180002d82  mov     ecx, 80070057h
0x180002d87  test    rdi, rdi
0x180002d8a  cmovnz  ecx, eax
0x180002d8d  jz      loc_180002F38
0x180002d93  cmp     rdi, 1
0x180002d97  jbe     loc_180002FA4
0x180002d9d  lea     rax, [rdi+rdi]
0x180002da1  lea     rdx, [rbp+810h+var_48]
0x180002da8  sub     rdx, rax
0x180002dab  lea     rcx, [rbp+810h+var_720]
0x180002db2  test    rsi, rsi
0x180002db5  jz      short loc_180002DD3
0x180002db7  movzx   eax, word ptr [rcx]
0x180002dba  test    ax, ax
0x180002dbd  jz      short loc_180002DD3
0x180002dbf  mov     [rdx], ax
0x180002dc2  add     rcx, 2
0x180002dc6  add     rdx, 2
0x180002dca  dec     rsi
0x180002dcd  sub     rdi, 1
0x180002dd1  jnz     short loc_180002DB2
0x180002dd3  xor     eax, eax
0x180002dd5  lea     rcx, [rdx-2]
0x180002dd9  test    rdi, rdi
0x180002ddc  cmovnz  rcx, rdx
0x180002de0  cmovnz  r15d, eax
0x180002de4  mov     [rcx], ax
0x180002de7  test    r15d, r15d
0x180002dea  jns     short loc_180002E1D
0x180002dec  mov     rcx, [rbp+818h]; this
0x180002df3  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180002dfa  mov     r9d, r15d; char *
0x180002dfd  mov     edx, 127h; void *
0x180002e02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002e07  test    rbx, rbx
0x180002e0a  jz      short loc_180002E15
0x180002e0c  mov     rcx, rbx; string
0x180002e0f  call    cs:__imp_WindowsDeleteString
0x180002e15  mov     eax, r15d
0x180002e18  jmp     loc_180002D04
0x180002e1d  call    cs:__imp_RtlIsMultiSessionSku
0x180002e23  test    al, al
0x180002e25  jz      loc_180002FB6
0x180002e2b  lea     rax, [rsp+910h+pSecurityDescriptor]
0x180002e30  mov     [rsp+910h+pSecurityDescriptor], 0
0x180002e39  xor     r9d, r9d; SecurityDescriptorSize
0x180002e3c  mov     [rsp+910h+var_8C8], rax
0x180002e41  lea     r8, [rsp+910h+SecurityDescriptor]; SecurityDescriptor
0x180002e46  mov     [rsp+910h+SecurityDescriptor], 0
0x180002e4f  mov     edx, 1; StringSDRevision
0x180002e54  mov     [rsp+910h+var_8B8], 1
0x180002e59  lea     rcx, [rbp+810h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180002e60  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180002e66  cmp     [rsp+910h+var_8B8], 0
0x180002e6b  mov     r12d, eax
0x180002e6e  jz      short loc_180002E89
0x180002e70  mov     rsi, [rsp+910h+var_8C8]
0x180002e75  mov     r15, [rsp+910h+SecurityDescriptor]
0x180002e7a  mov     r14, [rsi]
0x180002e7d  test    r14, r14
0x180002e80  jnz     loc_180003296
0x180002e86  mov     [rsi], r15
0x180002e89  test    r12d, r12d
0x180002e8c  jz      short loc_180002EF8
0x180002e8e  mov     r8, [rsp+910h+pSecurityDescriptor]; pSecurityDescriptor
0x180002e93  mov     edx, 4; SecurityInformation
0x180002e98  mov     rcx, r13; hKey
0x180002e9b  call    cs:__imp_RegSetKeySecurity
0x180002ea1  test    eax, eax
0x180002ea3  jnz     loc_180002F72
0x180002ea9  mov     rcx, [rsp+910h+pSecurityDescriptor]; hMem
0x180002eae  test    rcx, rcx
0x180002eb1  jnz     short loc_180002EF0
0x180002eb3  test    rbx, rbx
0x180002eb6  jz      short loc_180002EC1
0x180002eb8  mov     rcx, rbx; string
0x180002ebb  call    cs:__imp_WindowsDeleteString
0x180002ec1  xor     eax, eax
0x180002ec3  jmp     loc_180002D04
0x180002ec8  lea     rcx, [rsp+910h+string]; this
0x180002ecd  call    ?GetCurrentUserSid@AdvertisingIdHelpers@@YAJPEAVString@Internal@Windows@@@Z; AdvertisingIdHelpers::GetCurrentUserSid(Windows::Internal::String *)
0x180002ed2  mov     ebx, eax
0x180002ed4  test    eax, eax
0x180002ed6  js      short loc_180002F40
0x180002ed8  mov     rbx, [rsp+910h+string]
0x180002edd  xor     edx, edx; length
0x180002edf  mov     rcx, rbx; string
0x180002ee2  call    cs:__imp_WindowsGetStringRawBuffer
0x180002ee8  mov     r12, rax
0x180002eeb  jmp     loc_180002C5D
0x180002ef0  call    cs:__imp_LocalFree
0x180002ef6  jmp     short loc_180002EB3
0x180002ef8  mov     rcx, [rbp+818h]; this
0x180002eff  mov     edx, 15Fh; void *
0x180002f04  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180002f09  mov     rcx, [rsp+910h+pSecurityDescriptor]
0x180002f0e  mov     edi, eax
0x180002f10  test    rcx, rcx
0x180002f13  jnz     loc_180002F99
0x180002f19  test    rbx, rbx
0x180002f1c  jz      short loc_180002F27
0x180002f1e  mov     rcx, rbx; string
0x180002f21  call    cs:__imp_WindowsDeleteString
0x180002f27  mov     eax, edi
0x180002f29  jmp     loc_180002D04
0x180002f2e  mov     edx, 120h
0x180002f33  jmp     loc_180002CDD
0x180002f38  mov     r15d, ecx
0x180002f3b  jmp     loc_180002DEC
0x180002f40  mov     rcx, [rbp+818h]; this
0x180002f47  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180002f4e  mov     r9d, ebx; char *
0x180002f51  mov     edx, 111h; void *
0x180002f56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002f5b  mov     rcx, [rsp+910h+string]; string
0x180002f60  test    rcx, rcx
0x180002f63  jz      short loc_180002F6B
0x180002f65  call    cs:__imp_WindowsDeleteString
0x180002f6b  mov     eax, ebx
0x180002f6d  jmp     loc_180002D24
0x180002f72  mov     rcx, [rbp+818h]; this
0x180002f79  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180002f80  mov     r9d, eax; char *
0x180002f83  mov     edx, 164h; void *
0x180002f88  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002f8d  mov     rcx, [rsp+910h+pSecurityDescriptor]; hMem
0x180002f92  mov     edi, eax
0x180002f94  test    rcx, rcx
0x180002f97  jz      short loc_180002F19
0x180002f99  call    cs:__imp_LocalFree
0x180002f9f  jmp     loc_180002F19
0x180002fa4  cmp     [rbp+810h+var_720], ax
0x180002fab  jz      loc_180002E1D
0x180002fb1  jmp     loc_180002DEC
0x180002fb6  xor     edx, edx; Val
0x180002fb8  lea     rcx, [rbp+810h+pSid]; void *
0x180002fbc  mov     r8d, 44h ; 'D'; Size
0x180002fc2  call    memset_0
0x180002fc7  lea     r9, [rsp+910h+cbSid]; cbSid
0x180002fcc  mov     [rsp+910h+cbSid], 44h ; 'D'
0x180002fd4  lea     r8, [rbp+810h+pSid]; pSid
0x180002fd8  xor     edx, edx; DomainSid
0x180002fda  mov     ecx, 6Fh ; 'o'; WellKnownSidType
0x180002fdf  call    cs:__imp_CreateWellKnownSid
0x180002fe5  test    eax, eax
0x180002fe7  jnz     short loc_180003001
0x180002fe9  mov     rcx, [rbp+818h]; this
0x180002ff0  mov     edx, 134h; void *
0x180002ff5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180002ffa  mov     edi, eax
0x180002ffc  jmp     loc_180002F19
0x180003001  lea     rax, [rsp+910h+string]
0x180003006  mov     [rsp+910h+string], 0
0x18000300f  lea     rdx, [rsp+910h+SecurityDescriptor]; StringSid
0x180003014  mov     [rsp+910h+var_8C8], rax
0x180003019  lea     rcx, [rbp+810h+pSid]; Sid
0x18000301d  mov     [rsp+910h+SecurityDescriptor], 0
0x180003026  mov     [rsp+910h+var_8B8], 1
0x18000302b  call    cs:__imp_ConvertSidToStringSidW
0x180003031  lea     rcx, [rsp+910h+var_8C8]
0x180003036  mov     edi, eax
0x180003038  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18000303d  test    edi, edi
0x18000303f  jnz     short loc_180003059
0x180003041  mov     rcx, [rbp+818h]; this
0x180003048  mov     edx, 137h; void *
0x18000304d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003052  mov     edi, eax
0x180003054  jmp     loc_180003258
0x180003059  mov     rcx, [rsp+910h+string]; lpString1
0x18000305e  mov     r9d, 0FFFFFFFFh; cchCount2
0x180003064  mov     edx, r9d; cchCount1
0x180003067  mov     dword ptr [rsp+910h+bIgnoreCase], 1; int
0x18000306f  mov     r8, r12; lpString2
0x180003072  call    cs:__imp_CompareStringOrdinal
0x180003078  cmp     eax, 2
0x18000307b  jz      loc_180003129
0x180003081  mov     r9, [rsp+910h+string]
0x180003086  lea     r8, [rsp+910h+var_8B0]; unsigned __int16 *
0x18000308b  mov     edx, 0FCh; unsigned __int64
0x180003090  lea     rcx, [rbp+810h+var_720]; unsigned __int16 *
0x180003097  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000309c  mov     edi, eax
0x18000309e  test    eax, eax
  ... truncated ...
```
