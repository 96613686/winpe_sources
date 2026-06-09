# CSecurityAdmin2::VerifyUserNameAndSid(ISimpleTableWrite *,ushort *,void *,ulong,int *,void * *)

- ea: `0x180037340`
- end: `0x180037879`
- name: `?VerifyUserNameAndSid@CSecurityAdmin2@@QEAAHPEAUISimpleTableWrite@@PEAGPEAXKPEAHPEAPEAX@Z`
- size: `1337`
- prototype: `int(CSecurityAdmin2 *__hidden this, struct ISimpleTableWrite *, unsigned __int16 *, void *, unsigned int, int *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800367a8`

## callees

- `0x18000b6a0`
- `0x1800136d8`
- `0x18001a6c8`
- `0x180036604`
- `0x180037340`
- `0x180055502`
- `0x18005550e`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003749f`
- `msvcrt!_wcsicmp` at `0x18003749f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373df`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003769e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003769e`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180037717`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180037717`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180037676`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180037676`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003760f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003767f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800376cb`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003760f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003767f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800376cb`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180037630`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800376d3`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180037630`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800376d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003776c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003778e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003776c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003778e`
- `KERNEL32!GetComputerNameW` at `0x18003748d`
- `KERNEL32!GetComputerNameW` at `0x18003748d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003779d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037847`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003779d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037847`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037641`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003781c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037641`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003781c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180037734`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180037734`
- `logoncli!DsGetDcNameW` at `0x1800374d4`
- `logoncli!DsGetDcNameW` at `0x1800374d4`
- `netutils!NetApiBufferFree` at `0x180037560`
- `netutils!NetApiBufferFree` at `0x180037560`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800373d1`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800373d1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180037553`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180037553`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800375c0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800375c0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800375d4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800375e4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180037654`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18003765f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800376ab`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800376b6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800375d4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800375e4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180037654`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18003765f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800376ab`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800376b6`
- `ADVAPI32!LsaLookupNames` at `0x1800375b3`
- `ADVAPI32!LsaLookupNames` at `0x1800375b3`

## pseudocode

```c
__int64 __fastcall CSecurityAdmin2::VerifyUserNameAndSid(
        CSecurityAdmin2 *this,
        struct ISimpleTableWrite *a2,
        unsigned __int16 *a3,
        void *a4,
        unsigned int a5,
        int *a6,
        void **a7)
{
  _BYTE *v7; // rsi
  WELL_KNOWN_SID_TYPE v8; // ebx
  unsigned int v12; // edi
  DWORD LastError; // eax
  int v14; // eax
  unsigned int v15; // ecx
  unsigned int v16; // r8d
  unsigned __int64 v17; // rdx
  unsigned __int16 v18; // ax
  __int16 v19; // r8
  NTSTATUS v20; // ebx
  NTSTATUS v21; // ebx
  PSID v22; // rbx
  UCHAR v23; // dl
  UCHAR v24; // r14
  DWORD SidLengthRequired; // eax
  ULONG RelativeId; // ebx
  UCHAR *SidSubAuthorityCount; // rax
  DWORD v28; // eax
  SIZE_T v29; // rbx
  unsigned __int16 *v30; // rax
  unsigned __int16 *v31; // r14
  int v32; // ebx
  CSecurityAdmin2 *v33; // rcx
  void *v34; // rax
  DWORD cbSid; // [rsp+30h] [rbp-D0h] BYREF
  PLSA_TRANSLATED_SID Sids; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+58h] [rbp-A8h] BYREF
  DWORD nSize; // [rsp+5Ch] [rbp-A4h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+60h] [rbp-A0h] BYREF
  PVOID PolicyHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _LSA_UNICODE_STRING SystemName; // [rsp+70h] [rbp-90h] BYREF
  struct _LSA_UNICODE_STRING Names; // [rsp+80h] [rbp-80h] BYREF
  int *v47; // [rsp+90h] [rbp-70h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v49[4]; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t String2[8]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v51; // [rsp+E8h] [rbp-18h]
  WCHAR Buffer[16]; // [rsp+F8h] [rbp-8h] BYREF
  WCHAR ReferencedDomainName[20]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE Sid[64]; // [rsp+140h] [rbp+40h] BYREF

  v7 = Sid;
  v8 = WinNullSid;
  v47 = a6;
  cchReferencedDomainName = 16;
  *a7 = 0;
  v12 = 1;
  cbSid = 64;
  peUse = 0;
  while ( 1 )
  {
    if ( LookupAccountNameLocalW(a3, v7, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
      goto LABEL_38;
    LastError = GetLastError();
    if ( LastError != 122 )
      break;
    if ( cchReferencedDomainName > 0x10 || cbSid <= 0x40 )
      return v12;
    v7 = CoTaskMemAlloc(cbSid);
    if ( !v7 )
      goto LABEL_60;
  }
  if ( LastError == 1332 )
  {
    DomainControllerInfo = 0;
    *(_OWORD *)String2 = 0;
    v51 = 0;
    v14 = safe_lstrlenW(a3);
    v15 = 0;
    v16 = v14 + 1;
    while ( v15 < v16 )
    {
      if ( v15 > 0xF )
        goto LABEL_60;
      v17 = v15;
      v18 = a3[v17];
      if ( !v18 )
        goto LABEL_60;
      if ( v18 == 92 )
      {
        if ( v17 >= 16 )
          _report_rangecheckfailure();
        String2[v15] = 0;
        break;
      }
      String2[v15++] = v18;
    }
    nSize = 16;
    if ( GetComputerNameW(Buffer, &nSize) && !_wcsicmp(Buffer, String2) )
    {
LABEL_19:
      v12 = 0;
      goto LABEL_60;
    }
    if ( !DsGetDcNameW(0, String2, 0, 0, 0x10000u, &DomainControllerInfo) )
    {
      v49[2] = 1;
      PolicyHandle = 0;
      v49[0] = 12;
      ObjectAttributes.SecurityQualityOfService = v49;
      memset(&ObjectAttributes, 0, 40);
      v49[1] = 2;
      SystemName = 0;
      ObjectAttributes.Length = 48;
      SystemName.Buffer = DomainControllerInfo->DomainControllerName;
      SystemName.Length = 2 * safe_lstrlenW(SystemName.Buffer);
      SystemName.MaximumLength = v19 + SystemName.Length;
      v20 = LsaOpenPolicy(&SystemName, &ObjectAttributes, 0x800u, &PolicyHandle);
      NetApiBufferFree(DomainControllerInfo);
      if ( !v20 )
      {
        *(_QWORD *)&Names.Length = 0;
        ReferencedDomains = 0;
        Sids = 0;
        Names.Buffer = a3;
        Names.Length = 2 * safe_lstrlenW(a3);
        Names.MaximumLength = Names.Length + 2;
        v21 = LsaLookupNames(PolicyHandle, 1u, &Names, &ReferencedDomains, &Sids);
        LsaClose(PolicyHandle);
        if ( v21 )
        {
          if ( ReferencedDomains )
            LsaFreeMemory(ReferencedDomains);
          if ( Sids )
            LsaFreeMemory(Sids);
          v12 = 0;
          goto LABEL_60;
        }
        v22 = ReferencedDomains->Domains[Sids->DomainIndex].Sid;
        v23 = *GetSidSubAuthorityCount(v22);
        v24 = v23 + 1;
        if ( Sids->Use == SidTypeDomain )
          v24 = v23;
        SidLengthRequired = GetSidLengthRequired(v24);
        cbSid = SidLengthRequired;
        if ( SidLengthRequired > 0x40 )
        {
          v7 = CoTaskMemAlloc(SidLengthRequired);
          if ( !v7 )
          {
            LsaFreeMemory(ReferencedDomains);
            LsaFreeMemory(Sids);
            goto LABEL_60;
          }
          SidLengthRequired = cbSid;
        }
        CopySid(SidLengthRequired, v7, v22);
        *GetSidSubAuthorityCount(v7) = v24;
        if ( Sids->Use != SidTypeDomain )
        {
          RelativeId = Sids->RelativeId;
          *GetSidSubAuthority(v7, (unsigned int)v24 - 1) = RelativeId;
        }
        LsaFreeMemory(ReferencedDomains);
        LsaFreeMemory(Sids);
        v8 = WinNullSid;
LABEL_38:
        if ( g_bSysprepMode )
          a4 = 0;
        SidSubAuthorityCount = GetSidSubAuthorityCount(v7);
        v28 = GetSidLengthRequired(*SidSubAuthorityCount);
        cbSid = v28;
        if ( a4 )
        {
          if ( v28 == a5 && !memcmp_0(v7, a4, v28) )
          {
LABEL_58:
            v34 = CoTaskMemAlloc(cbSid);
            *a7 = v34;
            if ( v34 )
              memcpy_0(v34, v7, cbSid);
            goto LABEL_60;
          }
          goto LABEL_19;
        }
        while ( 1 )
        {
          if ( (unsigned int)v8 > WinBuiltinTerminalServerLicenseServersSid )
            goto LABEL_54;
          if ( IsWellKnownSid(v7, v8) )
            break;
          ++v8;
        }
        StringSid = 0;
        if ( ConvertSidToStringSidW(v7, &StringSid) )
        {
          v29 = 2 * (unsigned int)safe_lstrlenW(StringSid) + 2;
          v30 = (unsigned __int16 *)CoTaskMemAlloc(v29);
          v31 = v30;
          if ( !v30 )
          {
            v12 = 0;
            LocalFree(StringSid);
            goto LABEL_60;
          }
          v32 = StringCbCopyW(v30, v29, StringSid);
          LocalFree(StringSid);
          if ( v32 < 0 )
          {
            v12 = 0;
            CoTaskMemFree(v31);
            goto LABEL_60;
          }
          if ( (int)CSecurityAdmin2::UpdateCurrentRoleWithNewTextSid(v33, a2, v31, cbSid, v7) < 0 )
            goto LABEL_60;
LABEL_57:
          *v47 = 1;
          goto LABEL_58;
        }
LABEL_54:
        if ( (*(int (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)a2 + 128LL))(a2) >= 0
          && (*(int (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, _BYTE *))(*(_QWORD *)a2 + 160LL))(
               a2,
               3,
               cbSid,
               v7) >= 0 )
        {
          if ( (*(int (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)a2 + 144LL))(a2) < 0 )
            goto LABEL_58;
          goto LABEL_57;
        }
      }
    }
  }
LABEL_60:
  if ( v7 != Sid )
    CoTaskMemFree(v7);
  return v12;
}

```

## disassembly

```asm
0x180037340  mov     [rsp-8+arg_0], rbx
0x180037345  push    rbp
0x180037346  push    rsi
0x180037347  push    rdi
0x180037348  push    r12
0x18003734a  push    r13
0x18003734c  push    r14
0x18003734e  push    r15
0x180037350  lea     rbp, [rsp-90h]
0x180037358  sub     rsp, 190h
0x18003735f  mov     rax, cs:__security_cookie
0x180037366  xor     rax, rsp
0x180037369  mov     [rbp+0C0h+var_40], rax
0x180037370  mov     r13, [rbp+0C0h+arg_30]
0x180037377  lea     rsi, [rbp+0C0h+Sid]
0x18003737b  mov     rax, [rbp+0C0h+arg_28]
0x180037382  xor     ebx, ebx
0x180037384  mov     r12, r9
0x180037387  mov     [rbp+0C0h+var_130], rax
0x18003738b  mov     r14, r8
0x18003738e  mov     [rsp+1C0h+var_180], 10h
0x180037396  mov     [r13+0], rbx
0x18003739a  mov     r15, rdx
0x18003739d  mov     edi, 1
0x1800373a2  mov     [rsp+1C0h+cbSid], 40h ; '@'
0x1800373aa  mov     [rsp+1C0h+var_168], ebx
0x1800373ae  lea     rax, [rsp+1C0h+var_168]
0x1800373b3  mov     rdx, rsi; Sid
0x1800373b6  mov     [rsp+1C0h+peUse], rax; peUse
0x1800373bb  lea     r9, [rbp+0C0h+ReferencedDomainName]; ReferencedDomainName
0x1800373bf  lea     rax, [rsp+1C0h+var_180]
0x1800373c4  mov     rcx, r14; lpAccountName
0x1800373c7  lea     r8, [rsp+1C0h+cbSid]; cbSid
0x1800373cc  mov     [rsp+1C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800373d1  call    cs:__imp_LookupAccountNameLocalW
0x1800373d7  test    eax, eax
0x1800373d9  jnz     loc_1800376BE
0x1800373df  call    cs:__imp_GetLastError
0x1800373e5  cmp     eax, 7Ah ; 'z'
0x1800373e8  jnz     short loc_180037417
0x1800373ea  cmp     [rsp+1C0h+var_180], 10h
0x1800373ef  ja      loc_18003784D
0x1800373f5  cmp     [rsp+1C0h+cbSid], 40h ; '@'
0x1800373fa  jbe     loc_18003784D
0x180037400  mov     ecx, [rsp+1C0h+cbSid]; cb
0x180037404  call    cs:__imp_CoTaskMemAlloc
0x18003740a  mov     rsi, rax
0x18003740d  test    rax, rax
0x180037410  jnz     short loc_1800373AE
0x180037412  jmp     loc_18003783B
0x180037417  cmp     eax, 534h
0x18003741c  jnz     loc_18003783B
0x180037422  xorps   xmm0, xmm0
0x180037425  mov     [rsp+1C0h+DomainControllerInfo], rbx
0x18003742a  mov     rcx, r14; unsigned __int16 *
0x18003742d  movups  xmmword ptr [rbp+0C0h+String2], xmm0
0x180037431  movups  [rbp+0C0h+var_D8], xmm0
0x180037435  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003743a  mov     ecx, ebx
0x18003743c  lea     r8d, [rdi+rax]
0x180037440  cmp     ecx, r8d
0x180037443  jnb     short loc_18003747C
0x180037445  cmp     ecx, 0Fh
0x180037448  ja      loc_18003783B
0x18003744e  mov     eax, ecx
0x180037450  lea     rdx, [rax+rax]
0x180037454  movzx   eax, word ptr [rdx+r14]
0x180037459  test    ax, ax
0x18003745c  jz      loc_18003783B
0x180037462  cmp     ax, 5Ch ; '\'
0x180037466  jz      short loc_180037471
0x180037468  mov     [rbp+rdx+0C0h+String2], ax
0x18003746d  add     ecx, edi
0x18003746f  jmp     short loc_180037440
0x180037471  cmp     rdx, 20h ; ' '
0x180037475  jnb     short loc_1800374B0
0x180037477  mov     [rbp+rdx+0C0h+String2], bx
0x18003747c  lea     rdx, [rsp+1C0h+nSize]; nSize
0x180037481  mov     [rsp+1C0h+nSize], 10h
0x180037489  lea     rcx, [rbp+0C0h+Buffer]; lpBuffer
0x18003748d  call    cs:__imp_GetComputerNameW
0x180037493  test    eax, eax
0x180037495  jz      short loc_1800374B6
0x180037497  lea     rdx, [rbp+0C0h+String2]; String2
0x18003749b  lea     rcx, [rbp+0C0h+Buffer]; String1
0x18003749f  call    cs:__imp__wcsicmp
0x1800374a5  test    eax, eax
0x1800374a7  jnz     short loc_1800374B6
0x1800374a9  mov     edi, ebx
0x1800374ab  jmp     loc_18003783B
0x1800374b0  call    __report_rangecheckfailure
0x1800374b6  lea     rax, [rsp+1C0h+DomainControllerInfo]
0x1800374bb  xor     r9d, r9d; SiteName
0x1800374be  mov     [rsp+1C0h+peUse], rax; DomainControllerInfo
0x1800374c3  lea     rdx, [rbp+0C0h+String2]; DomainName
0x1800374c7  xor     r8d, r8d; DomainGuid
0x1800374ca  mov     dword ptr [rsp+1C0h+cchReferencedDomainName], 10000h; Flags
0x1800374d2  xor     ecx, ecx; ComputerName
0x1800374d4  call    cs:__imp_DsGetDcNameW
0x1800374da  test    eax, eax
0x1800374dc  jnz     loc_18003783B
0x1800374e2  xorps   xmm0, xmm0
0x1800374e5  mov     [rbp+0C0h+var_F0], edi
0x1800374e8  lea     r8d, [rax+2]
0x1800374ec  mov     [rsp+1C0h+PolicyHandle], rbx
0x1800374f1  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800374f5  lea     rax, [rbp+0C0h+var_F8]
0x1800374f9  mov     [rbp+0C0h+var_F8], 0Ch
0x180037500  mov     [rbp+0C0h+ObjectAttributes.SecurityQualityOfService], rax
0x180037504  mov     rax, [rsp+1C0h+DomainControllerInfo]
0x180037509  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.Length], xmm0
0x18003750d  mov     [rbp+0C0h+var_F4], r8d
0x180037511  movups  xmmword ptr [rsp+1C0h+SystemName.Length], xmm0
0x180037516  mov     [rbp+0C0h+ObjectAttributes.Length], 30h ; '0'
0x18003751d  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.ObjectName], xmm0
0x180037521  mov     rcx, [rax]; unsigned __int16 *
0x180037524  mov     [rsp+1C0h+SystemName.Buffer], rcx
0x180037529  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003752e  add     ax, ax
0x180037531  lea     r9, [rsp+1C0h+PolicyHandle]; PolicyHandle
0x180037536  mov     [rsp+1C0h+SystemName.Length], ax
0x18003753b  lea     rdx, [rbp+0C0h+ObjectAttributes]; ObjectAttributes
0x18003753f  add     ax, r8w
0x180037543  lea     rcx, [rsp+1C0h+SystemName]; SystemName
0x180037548  mov     r8d, 800h; DesiredAccess
0x18003754e  mov     [rsp+1C0h+SystemName.MaximumLength], ax
0x180037553  call    cs:__imp_LsaOpenPolicy
0x180037559  mov     rcx, [rsp+1C0h+DomainControllerInfo]; Buffer
0x18003755e  mov     ebx, eax
0x180037560  call    cs:__imp_NetApiBufferFree
0x180037566  xor     eax, eax
0x180037568  test    ebx, ebx
0x18003756a  jnz     loc_18003783B
0x180037570  mov     rcx, r14; unsigned __int16 *
0x180037573  mov     qword ptr [rbp+0C0h+Names.Length], rax
0x180037577  mov     [rsp+1C0h+ReferencedDomains], rax
0x18003757c  mov     [rsp+1C0h+Sids], rax
0x180037581  mov     [rbp+0C0h+Names.Buffer], r14
0x180037585  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003758a  mov     rcx, [rsp+1C0h+PolicyHandle]; PolicyHandle
0x18003758f  lea     r9, [rsp+1C0h+ReferencedDomains]; ReferencedDomains
0x180037594  add     ax, ax
0x180037597  lea     r8, [rbp+0C0h+Names]; Names
0x18003759b  mov     [rbp+0C0h+Names.Length], ax
0x18003759f  mov     edx, edi; Count
0x1800375a1  add     ax, 2
0x1800375a5  mov     [rbp+0C0h+Names.MaximumLength], ax
0x1800375a9  lea     rax, [rsp+1C0h+Sids]
0x1800375ae  mov     [rsp+1C0h+cchReferencedDomainName], rax; Sids
0x1800375b3  call    cs:__imp_LsaLookupNames
0x1800375b9  mov     rcx, [rsp+1C0h+PolicyHandle]; ObjectHandle
0x1800375be  mov     ebx, eax
0x1800375c0  call    cs:__imp_LsaClose
0x1800375c6  test    ebx, ebx
0x1800375c8  jz      short loc_1800375F1
0x1800375ca  mov     rcx, [rsp+1C0h+ReferencedDomains]; Buffer
0x1800375cf  test    rcx, rcx
0x1800375d2  jz      short loc_1800375DA
0x1800375d4  call    cs:__imp_LsaFreeMemory
0x1800375da  mov     rcx, [rsp+1C0h+Sids]; Buffer
0x1800375df  test    rcx, rcx
0x1800375e2  jz      short loc_1800375EA
0x1800375e4  call    cs:__imp_LsaFreeMemory
0x1800375ea  xor     edi, edi
0x1800375ec  jmp     loc_18003783B
0x1800375f1  mov     rax, [rsp+1C0h+Sids]
0x1800375f6  movsxd  rcx, dword ptr [rax+8]
0x1800375fa  mov     rax, [rsp+1C0h+ReferencedDomains]
0x1800375ff  lea     rdx, [rcx+rcx*2]
0x180037603  mov     rcx, [rax+8]
0x180037607  mov     rbx, [rcx+rdx*8+10h]
0x18003760c  mov     rcx, rbx; pSid
0x18003760f  call    cs:__imp_GetSidSubAuthorityCount
0x180037615  movzx   edx, byte ptr [rax]
0x180037618  mov     rax, [rsp+1C0h+Sids]
0x18003761d  mov     ecx, [rax]
0x18003761f  cmp     ecx, 3
0x180037622  lea     eax, [rdi+rdx]
0x180037625  movzx   r14d, al
0x180037629  cmovz   r14d, edx
0x18003762d  mov     cl, r14b; nSubAuthorityCount
0x180037630  call    cs:__imp_GetSidLengthRequired
0x180037636  mov     [rsp+1C0h+cbSid], eax
0x18003763a  cmp     eax, 40h ; '@'
0x18003763d  jbe     short loc_18003766E
0x18003763f  mov     ecx, eax; cb
0x180037641  call    cs:__imp_CoTaskMemAlloc
0x180037647  mov     rsi, rax
0x18003764a  test    rax, rax
0x18003764d  jnz     short loc_18003766A
0x18003764f  mov     rcx, [rsp+1C0h+ReferencedDomains]; Buffer
0x180037654  call    cs:__imp_LsaFreeMemory
0x18003765a  mov     rcx, [rsp+1C0h+Sids]; Buffer
0x18003765f  call    cs:__imp_LsaFreeMemory
0x180037665  jmp     loc_18003783B
0x18003766a  mov     eax, [rsp+1C0h+cbSid]
0x18003766e  mov     r8, rbx; pSourceSid
0x180037671  mov     rdx, rsi; pDestinationSid
0x180037674  mov     ecx, eax; nDestinationSidLength
0x180037676  call    cs:__imp_CopySid
0x18003767c  mov     rcx, rsi; pSid
0x18003767f  call    cs:__imp_GetSidSubAuthorityCount
0x180037685  mov     [rax], r14b
0x180037688  mov     rbx, [rsp+1C0h+Sids]
0x18003768d  cmp     dword ptr [rbx], 3
0x180037690  jz      short loc_1800376A6
0x180037692  mov     ebx, [rbx+4]
0x180037695  mov     rcx, rsi; pSid
0x180037698  movzx   edx, r14b
0x18003769c  sub     edx, edi; nSubAuthority
0x18003769e  call    cs:__imp_GetSidSubAuthority
0x1800376a4  mov     [rax], ebx
0x1800376a6  mov     rcx, [rsp+1C0h+ReferencedDomains]; Buffer
0x1800376ab  call    cs:__imp_LsaFreeMemory
0x1800376b1  mov     rcx, [rsp+1C0h+Sids]; Buffer
0x1800376b6  call    cs:__imp_LsaFreeMemory
0x1800376bc  xor     ebx, ebx
0x1800376be  cmp     cs:?g_bSysprepMode@@3HA, ebx; int g_bSysprepMode
0x1800376c4  mov     rcx, rsi; pSid
0x1800376c7  cmovnz  r12, rbx
0x1800376cb  call    cs:__imp_GetSidSubAuthorityCount
0x1800376d1  mov     cl, [rax]; nSubAuthorityCount
0x1800376d3  call    cs:__imp_GetSidLengthRequired
0x1800376d9  mov     [rsp+1C0h+cbSid], eax
0x1800376dd  test    r12, r12
0x1800376e0  jz      short loc_180037709
0x1800376e2  cmp     eax, [rbp+0C0h+arg_20]
0x1800376e8  jnz     loc_1800374A9
0x1800376ee  mov     r8d, eax; Size
0x1800376f1  mov     rdx, r12; Buf2
0x1800376f4  mov     rcx, rsi; Buf1
0x1800376f7  call    memcmp_0
0x1800376fc  test    eax, eax
0x1800376fe  jz      loc_180037818
0x180037704  jmp     loc_1800374A9
0x180037709  cmp     ebx, 3Ch ; '<'
0x18003770c  ja      loc_1800377C3
0x180037712  mov     edx, ebx; WellKnownSidType
0x180037714  mov     rcx, rsi; pSid
0x180037717  call    cs:__imp_IsWellKnownSid
0x18003771d  test    eax, eax
0x18003771f  jnz     short loc_180037725
0x180037721  add     ebx, edi
0x180037723  jmp     short loc_180037709
0x180037725  xor     ebx, ebx
0x180037727  lea     rdx, [rsp+1C0h+StringSid]; StringSid
0x18003772c  mov     rcx, rsi; Sid
0x18003772f  mov     [rsp+1C0h+StringSid], rbx
0x180037734  call    cs:__imp_ConvertSidToStringSidW
0x18003773a  test    eax, eax
0x18003773c  jz      loc_1800377C3
0x180037742  mov     rcx, [rsp+1C0h+StringSid]; unsigned __int16 *
0x180037747  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003774c  lea     eax, ds:2[rax*2]
0x180037753  mov     ecx, eax; cb
0x180037755  mov     ebx, eax
0x180037757  call    cs:__imp_CoTaskMemAlloc
0x18003775d  mov     r14, rax
0x180037760  test    rax, rax
0x180037763  jnz     short loc_180037777
0x180037765  mov     rcx, [rsp+1C0h+StringSid]; hMem
0x18003776a  xor     edi, edi
0x18003776c  call    cs:__imp_LocalFree
0x180037772  jmp     loc_18003783B
0x180037777  mov     r8, [rsp+1C0h+StringSid]; unsigned __int16 *
0x18003777c  mov     rdx, rbx; unsigned __int64
0x18003777f  mov     rcx, r14; unsigned __int16 *
0x180037782  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180037787  mov     rcx, [rsp+1C0h+StringSid]; hMem
0x18003778c  mov     ebx, eax
0x18003778e  call    cs:__imp_LocalFree
0x180037794  test    ebx, ebx
0x180037796  jns     short loc_1800377A8
0x180037798  xor     edi, edi
0x18003779a  mov     rcx, r14; pv
0x18003779d  call    cs:__imp_CoTaskMemFree
0x1800377a3  jmp     loc_18003783B
0x1800377a8  mov     r9d, [rsp+1C0h+cbSid]; unsigned int
0x1800377ad  mov     r8, r14; unsigned __int16 *
0x1800377b0  mov     rdx, r15; struct ISimpleTableWrite *
0x1800377b3  mov     [rsp+1C0h+cchReferencedDomainName], rsi; void *
0x1800377b8  call    ?UpdateCurrentRoleWithNewTextSid@CSecurityAdmin2@@QEAAJPEAUISimpleTableWrite@@PEAGKPEAX@Z; CSecurityAdmin2::UpdateCurrentRoleWithNewTextSid(ISimpleTableWrite *,ushort *,ulong,void *)
0x1800377bd  test    eax, eax
0x1800377bf  jns     short loc_180037812
0x1800377c1  jmp     short loc_18003783B
0x1800377c3  mov     rax, [r15]
0x1800377c6  mov     rcx, r15
0x1800377c9  mov     rax, [rax+80h]
0x1800377d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377d5  test    eax, eax
0x1800377d7  js      short loc_18003783B
0x1800377d9  mov     rax, [r15]
0x1800377dc  mov     r9, rsi
0x1800377df  mov     r8d, [rsp+1C0h+cbSid]
0x1800377e4  mov     edx, 3
0x1800377e9  mov     rcx, r15
0x1800377ec  mov     rax, [rax+0A0h]
0x1800377f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377f8  test    eax, eax
0x1800377fa  js      short loc_18003783B
  ... truncated ...
```
