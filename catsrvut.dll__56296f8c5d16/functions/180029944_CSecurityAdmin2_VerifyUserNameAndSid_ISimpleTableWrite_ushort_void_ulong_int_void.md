# CSecurityAdmin2::VerifyUserNameAndSid(ISimpleTableWrite *,ushort *,void *,ulong,int *,void * *)

- ea: `0x180029944`
- end: `0x180029e7e`
- name: `?VerifyUserNameAndSid@CSecurityAdmin2@@QEAAHPEAUISimpleTableWrite@@PEAGPEAXKPEAHPEAPEAX@Z`
- size: `1338`
- prototype: `int(CSecurityAdmin2 *__hidden this, struct ISimpleTableWrite *, unsigned __int16 *, void *, unsigned int, int *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180028da8`

## callees

- `0x18000f7a8`
- `0x180015594`
- `0x18001c6a4`
- `0x180028c04`
- `0x180029944`
- `0x180055822`
- `0x18005582e`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180029aa3`
- `msvcrt!_wcsicmp` at `0x180029aa3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029da1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029e4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029da1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029e4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029a08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029c45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029d5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029e20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029a08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029c45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029d5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029e20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299e3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180029c7a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180029c7a`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180029d1b`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180029d1b`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180029c34`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180029cd7`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180029c34`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180029cd7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180029ca2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180029ca2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180029c13`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180029c83`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180029ccf`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180029c13`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180029c83`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180029ccf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d92`
- `KERNEL32!GetComputerNameW` at `0x180029a91`
- `KERNEL32!GetComputerNameW` at `0x180029a91`
- `netutils!NetApiBufferFree` at `0x180029b64`
- `netutils!NetApiBufferFree` at `0x180029b64`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800299d5`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800299d5`
- `ADVAPI32!LsaLookupNames` at `0x180029bb7`
- `ADVAPI32!LsaLookupNames` at `0x180029bb7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180029d38`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180029d38`
- `logoncli!DsGetDcNameW` at `0x180029ad8`
- `logoncli!DsGetDcNameW` at `0x180029ad8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180029bc4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180029bc4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180029bd8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180029be8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180029c58`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180029c63`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180029caf`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180029cba`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180029bd8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180029be8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180029c58`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180029c63`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180029caf`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180029cba`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180029b57`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180029b57`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSecurityAdmin2::VerifyUserNameAndSid(
        CSecurityAdmin2 *this,
        struct ISimpleTableWrite *a2,
        unsigned __int16 *a3,
        void *a4,
        unsigned int a5,
        int *a6,
        void **a7)
{
  unsigned int v10; // edi
  _BYTE *v11; // rsi
  WELL_KNOWN_SID_TYPE v12; // ebx
  DWORD LastError; // eax
  unsigned int v14; // r8d
  unsigned int i; // ecx
  unsigned __int64 v16; // rdx
  unsigned __int16 v17; // ax
  __int16 v18; // r8
  NTSTATUS v19; // ebx
  NTSTATUS v20; // ebx
  PSID v21; // rbx
  UCHAR v22; // dl
  UCHAR v23; // r14
  DWORD SidLengthRequired; // eax
  ULONG RelativeId; // ebx
  UCHAR *SidSubAuthorityCount; // rax
  DWORD v27; // eax
  SIZE_T v28; // rbx
  unsigned __int16 *v29; // rax
  unsigned __int16 *v30; // r14
  int v31; // ebx
  CSecurityAdmin2 *v32; // rcx
  void *v33; // rax
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
  int *v46; // [rsp+90h] [rbp-70h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v48[4]; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t String2[8]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v50; // [rsp+E8h] [rbp-18h]
  WCHAR Buffer[16]; // [rsp+F8h] [rbp-8h] BYREF
  WCHAR ReferencedDomainName[20]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE Sid[64]; // [rsp+140h] [rbp+40h] BYREF

  v46 = a6;
  v10 = 1;
  v11 = Sid;
  cchReferencedDomainName = 16;
  cbSid = 64;
  v12 = WinNullSid;
  peUse = 0;
  *a7 = 0;
  while ( 1 )
  {
    if ( LookupAccountNameLocalW(a3, v11, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
      goto LABEL_38;
    LastError = GetLastError();
    if ( LastError != 122 )
      break;
    if ( cchReferencedDomainName > 0x10 || cbSid <= 0x40 )
      return v10;
    v11 = CoTaskMemAlloc(cbSid);
    if ( !v11 )
      goto LABEL_60;
  }
  if ( LastError == 1332 )
  {
    *(_OWORD *)String2 = 0;
    v50 = 0;
    DomainControllerInfo = 0;
    v14 = safe_lstrlenW(a3) + 1;
    for ( i = 0; i < v14; ++i )
    {
      if ( i > 0xF )
        goto LABEL_60;
      v16 = i;
      v17 = a3[v16];
      if ( !v17 )
        goto LABEL_60;
      if ( v17 == 92 )
      {
        if ( v16 >= 16 )
          _report_rangecheckfailure();
        String2[i] = 0;
        break;
      }
      String2[i] = v17;
    }
    nSize = 16;
    if ( GetComputerNameW(Buffer, &nSize) && !_wcsicmp(Buffer, String2) )
    {
LABEL_19:
      v10 = 0;
      goto LABEL_60;
    }
    if ( !DsGetDcNameW(0, String2, 0, 0, 0x10000u, &DomainControllerInfo) )
    {
      v48[2] = 1;
      memset(&ObjectAttributes, 0, 40);
      PolicyHandle = 0;
      SystemName = 0;
      v48[0] = 12;
      v48[1] = 2;
      ObjectAttributes.Length = 48;
      ObjectAttributes.SecurityQualityOfService = v48;
      SystemName.Buffer = DomainControllerInfo->DomainControllerName;
      SystemName.Length = 2 * safe_lstrlenW(SystemName.Buffer);
      SystemName.MaximumLength = v18 + SystemName.Length;
      v19 = LsaOpenPolicy(&SystemName, &ObjectAttributes, 0x800u, &PolicyHandle);
      NetApiBufferFree(DomainControllerInfo);
      if ( !v19 )
      {
        *(_QWORD *)&Names.Length = 0;
        ReferencedDomains = 0;
        Sids = 0;
        Names.Buffer = a3;
        Names.Length = 2 * safe_lstrlenW(a3);
        Names.MaximumLength = Names.Length + 2;
        v20 = LsaLookupNames(PolicyHandle, 1u, &Names, &ReferencedDomains, &Sids);
        LsaClose(PolicyHandle);
        if ( v20 )
        {
          if ( ReferencedDomains )
            LsaFreeMemory(ReferencedDomains);
          if ( Sids )
            LsaFreeMemory(Sids);
          v10 = 0;
          goto LABEL_60;
        }
        v21 = ReferencedDomains->Domains[Sids->DomainIndex].Sid;
        v22 = *GetSidSubAuthorityCount(v21);
        v23 = v22 + 1;
        if ( Sids->Use == SidTypeDomain )
          v23 = v22;
        SidLengthRequired = GetSidLengthRequired(v23);
        cbSid = SidLengthRequired;
        if ( SidLengthRequired > 0x40 )
        {
          v11 = CoTaskMemAlloc(SidLengthRequired);
          if ( !v11 )
          {
            LsaFreeMemory(ReferencedDomains);
            LsaFreeMemory(Sids);
            goto LABEL_60;
          }
          SidLengthRequired = cbSid;
        }
        CopySid(SidLengthRequired, v11, v21);
        *GetSidSubAuthorityCount(v11) = v23;
        if ( Sids->Use != SidTypeDomain )
        {
          RelativeId = Sids->RelativeId;
          *GetSidSubAuthority(v11, (unsigned int)v23 - 1) = RelativeId;
        }
        LsaFreeMemory(ReferencedDomains);
        LsaFreeMemory(Sids);
        v12 = WinNullSid;
LABEL_38:
        if ( g_bSysprepMode )
          a4 = 0;
        SidSubAuthorityCount = GetSidSubAuthorityCount(v11);
        v27 = GetSidLengthRequired(*SidSubAuthorityCount);
        cbSid = v27;
        if ( a4 )
        {
          if ( v27 == a5 && !memcmp_0(v11, a4, v27) )
          {
LABEL_58:
            v33 = CoTaskMemAlloc(cbSid);
            *a7 = v33;
            if ( v33 )
              memcpy_0(v33, v11, cbSid);
            goto LABEL_60;
          }
          goto LABEL_19;
        }
        while ( 1 )
        {
          if ( (unsigned int)v12 > WinBuiltinTerminalServerLicenseServersSid )
            goto LABEL_54;
          if ( IsWellKnownSid(v11, v12) )
            break;
          ++v12;
        }
        StringSid = 0;
        if ( ConvertSidToStringSidW(v11, &StringSid) )
        {
          v28 = 2 * (unsigned int)safe_lstrlenW(StringSid) + 2;
          v29 = (unsigned __int16 *)CoTaskMemAlloc(v28);
          v30 = v29;
          if ( !v29 )
          {
            v10 = 0;
            LocalFree(StringSid);
            goto LABEL_60;
          }
          v31 = StringCbCopyW(v29, v28, StringSid);
          LocalFree(StringSid);
          if ( v31 < 0 )
          {
            v10 = 0;
            CoTaskMemFree(v30);
            goto LABEL_60;
          }
          if ( (int)CSecurityAdmin2::UpdateCurrentRoleWithNewTextSid(v32, a2, v30, cbSid, v11) < 0 )
            goto LABEL_60;
LABEL_57:
          *v46 = 1;
          goto LABEL_58;
        }
LABEL_54:
        if ( (*(int (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)a2 + 128LL))(a2) >= 0
          && (*(int (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, _BYTE *))(*(_QWORD *)a2 + 160LL))(
               a2,
               3,
               cbSid,
               v11) >= 0 )
        {
          if ( (*(int (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)a2 + 144LL))(a2) < 0 )
            goto LABEL_58;
          goto LABEL_57;
        }
      }
    }
  }
LABEL_60:
  if ( v11 != Sid )
    CoTaskMemFree(v11);
  return v10;
}

```

## disassembly

```asm
0x180029944  mov     [rsp-8+arg_0], rbx
0x180029949  push    rbp
0x18002994a  push    rsi
0x18002994b  push    rdi
0x18002994c  push    r12
0x18002994e  push    r13
0x180029950  push    r14
0x180029952  push    r15
0x180029954  lea     rbp, [rsp-90h]
0x18002995c  sub     rsp, 190h
0x180029963  mov     rax, cs:__security_cookie
0x18002996a  xor     rax, rsp
0x18002996d  mov     [rbp+0C0h+var_40], rax
0x180029974  mov     r12, r9
0x180029977  mov     r14, r8
0x18002997a  mov     r15, rdx
0x18002997d  mov     rax, [rbp+0C0h+arg_28]
0x180029984  mov     [rbp+0C0h+var_130], rax
0x180029988  mov     r13, [rbp+0C0h+arg_30]
0x18002998f  mov     edi, 1
0x180029994  lea     rsi, [rbp+0C0h+Sid]
0x180029998  mov     [rsp+1C0h+var_180], 10h
0x1800299a0  mov     [rsp+1C0h+cbSid], 40h ; '@'
0x1800299a8  xor     ebx, ebx
0x1800299aa  mov     [rsp+1C0h+var_168], ebx
0x1800299ae  mov     [r13+0], rbx
0x1800299b2  lea     rax, [rsp+1C0h+var_168]
0x1800299b7  mov     [rsp+1C0h+peUse], rax; peUse
0x1800299bc  lea     rax, [rsp+1C0h+var_180]
0x1800299c1  mov     [rsp+1C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800299c6  lea     r9, [rbp+0C0h+ReferencedDomainName]; ReferencedDomainName
0x1800299ca  lea     r8, [rsp+1C0h+cbSid]; cbSid
0x1800299cf  mov     rdx, rsi; Sid
0x1800299d2  mov     rcx, r14; lpAccountName
0x1800299d5  call    cs:__imp_LookupAccountNameLocalW
0x1800299db  test    eax, eax
0x1800299dd  jnz     loc_180029CC2
0x1800299e3  call    cs:__imp_GetLastError
0x1800299e9  cmp     eax, 7Ah ; 'z'
0x1800299ec  jnz     short loc_180029A1B
0x1800299ee  cmp     [rsp+1C0h+var_180], 10h
0x1800299f3  ja      loc_180029E52
0x1800299f9  cmp     [rsp+1C0h+cbSid], 40h ; '@'
0x1800299fe  jbe     loc_180029E52
0x180029a04  mov     ecx, [rsp+1C0h+cbSid]; cb
0x180029a08  call    cs:__imp_CoTaskMemAlloc
0x180029a0e  mov     rsi, rax
0x180029a11  test    rax, rax
0x180029a14  jnz     short loc_1800299B2
0x180029a16  jmp     loc_180029E3F
0x180029a1b  cmp     eax, 534h
0x180029a20  jnz     loc_180029E3F
0x180029a26  xorps   xmm0, xmm0
0x180029a29  movups  xmmword ptr [rbp+0C0h+String2], xmm0
0x180029a2d  movups  [rbp+0C0h+var_D8], xmm0
0x180029a31  mov     [rsp+1C0h+DomainControllerInfo], rbx
0x180029a36  mov     rcx, r14; unsigned __int16 *
0x180029a39  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180029a3e  lea     r8d, [rdi+rax]
0x180029a42  mov     ecx, ebx
0x180029a44  cmp     ecx, r8d
0x180029a47  jnb     short loc_180029A80
0x180029a49  cmp     ecx, 0Fh
0x180029a4c  ja      loc_180029E3F
0x180029a52  mov     eax, ecx
0x180029a54  lea     rdx, [rax+rax]
0x180029a58  movzx   eax, word ptr [rdx+r14]
0x180029a5d  test    ax, ax
0x180029a60  jz      loc_180029E3F
0x180029a66  cmp     ax, 5Ch ; '\'
0x180029a6a  jz      short loc_180029A75
0x180029a6c  mov     [rbp+rdx+0C0h+String2], ax
0x180029a71  add     ecx, edi
0x180029a73  jmp     short loc_180029A44
0x180029a75  cmp     rdx, 20h ; ' '
0x180029a79  jnb     short loc_180029AB4
0x180029a7b  mov     [rbp+rdx+0C0h+String2], bx
0x180029a80  mov     [rsp+1C0h+nSize], 10h
0x180029a88  lea     rdx, [rsp+1C0h+nSize]; nSize
0x180029a8d  lea     rcx, [rbp+0C0h+Buffer]; lpBuffer
0x180029a91  call    cs:__imp_GetComputerNameW
0x180029a97  test    eax, eax
0x180029a99  jz      short loc_180029ABA
0x180029a9b  lea     rdx, [rbp+0C0h+String2]; String2
0x180029a9f  lea     rcx, [rbp+0C0h+Buffer]; String1
0x180029aa3  call    cs:__imp__wcsicmp
0x180029aa9  test    eax, eax
0x180029aab  jnz     short loc_180029ABA
0x180029aad  mov     edi, ebx
0x180029aaf  jmp     loc_180029E3F
0x180029ab4  call    __report_rangecheckfailure
0x180029aba  lea     rax, [rsp+1C0h+DomainControllerInfo]
0x180029abf  mov     [rsp+1C0h+peUse], rax; DomainControllerInfo
0x180029ac4  mov     dword ptr [rsp+1C0h+cchReferencedDomainName], 10000h; Flags
0x180029acc  xor     r9d, r9d; SiteName
0x180029acf  xor     r8d, r8d; DomainGuid
0x180029ad2  lea     rdx, [rbp+0C0h+String2]; DomainName
0x180029ad6  xor     ecx, ecx; ComputerName
0x180029ad8  call    cs:__imp_DsGetDcNameW
0x180029ade  test    eax, eax
0x180029ae0  jnz     loc_180029E3F
0x180029ae6  mov     [rbp+0C0h+var_F0], edi
0x180029ae9  xorps   xmm0, xmm0
0x180029aec  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.Length], xmm0
0x180029af0  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.ObjectName], xmm0
0x180029af4  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180029af8  mov     [rsp+1C0h+PolicyHandle], rbx
0x180029afd  movups  xmmword ptr [rsp+1C0h+SystemName.Length], xmm0
0x180029b02  mov     [rbp+0C0h+var_F8], 0Ch
0x180029b09  lea     r8d, [rax+2]
0x180029b0d  mov     [rbp+0C0h+var_F4], r8d
0x180029b11  mov     [rbp+0C0h+ObjectAttributes.Length], 30h ; '0'
0x180029b18  lea     rax, [rbp+0C0h+var_F8]
0x180029b1c  mov     [rbp+0C0h+ObjectAttributes.SecurityQualityOfService], rax
0x180029b20  mov     rax, [rsp+1C0h+DomainControllerInfo]
0x180029b25  mov     rcx, [rax]; unsigned __int16 *
0x180029b28  mov     [rsp+1C0h+SystemName.Buffer], rcx
0x180029b2d  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180029b32  add     ax, ax
0x180029b35  mov     [rsp+1C0h+SystemName.Length], ax
0x180029b3a  add     ax, r8w
0x180029b3e  mov     [rsp+1C0h+SystemName.MaximumLength], ax
0x180029b43  lea     r9, [rsp+1C0h+PolicyHandle]; PolicyHandle
0x180029b48  mov     r8d, 800h; DesiredAccess
0x180029b4e  lea     rdx, [rbp+0C0h+ObjectAttributes]; ObjectAttributes
0x180029b52  lea     rcx, [rsp+1C0h+SystemName]; SystemName
0x180029b57  call    cs:__imp_LsaOpenPolicy
0x180029b5d  mov     ebx, eax
0x180029b5f  mov     rcx, [rsp+1C0h+DomainControllerInfo]; Buffer
0x180029b64  call    cs:__imp_NetApiBufferFree
0x180029b6a  xor     eax, eax
0x180029b6c  test    ebx, ebx
0x180029b6e  jnz     loc_180029E3F
0x180029b74  mov     qword ptr [rbp+0C0h+Names.Length], rax
0x180029b78  mov     [rsp+1C0h+ReferencedDomains], rax
0x180029b7d  mov     [rsp+1C0h+Sids], rax
0x180029b82  mov     [rbp+0C0h+Names.Buffer], r14
0x180029b86  mov     rcx, r14; unsigned __int16 *
0x180029b89  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180029b8e  add     ax, ax
0x180029b91  mov     [rbp+0C0h+Names.Length], ax
0x180029b95  add     ax, 2
0x180029b99  mov     [rbp+0C0h+Names.MaximumLength], ax
0x180029b9d  lea     rax, [rsp+1C0h+Sids]
0x180029ba2  mov     [rsp+1C0h+cchReferencedDomainName], rax; Sids
0x180029ba7  lea     r9, [rsp+1C0h+ReferencedDomains]; ReferencedDomains
0x180029bac  lea     r8, [rbp+0C0h+Names]; Names
0x180029bb0  mov     edx, edi; Count
0x180029bb2  mov     rcx, [rsp+1C0h+PolicyHandle]; PolicyHandle
0x180029bb7  call    cs:__imp_LsaLookupNames
0x180029bbd  mov     ebx, eax
0x180029bbf  mov     rcx, [rsp+1C0h+PolicyHandle]; ObjectHandle
0x180029bc4  call    cs:__imp_LsaClose
0x180029bca  test    ebx, ebx
0x180029bcc  jz      short loc_180029BF5
0x180029bce  mov     rcx, [rsp+1C0h+ReferencedDomains]; Buffer
0x180029bd3  test    rcx, rcx
0x180029bd6  jz      short loc_180029BDE
0x180029bd8  call    cs:__imp_LsaFreeMemory
0x180029bde  mov     rcx, [rsp+1C0h+Sids]; Buffer
0x180029be3  test    rcx, rcx
0x180029be6  jz      short loc_180029BEE
0x180029be8  call    cs:__imp_LsaFreeMemory
0x180029bee  xor     edi, edi
0x180029bf0  jmp     loc_180029E3F
0x180029bf5  mov     rax, [rsp+1C0h+Sids]
0x180029bfa  movsxd  rcx, dword ptr [rax+8]
0x180029bfe  lea     rdx, [rcx+rcx*2]
0x180029c02  mov     rax, [rsp+1C0h+ReferencedDomains]
0x180029c07  mov     rcx, [rax+8]
0x180029c0b  mov     rbx, [rcx+rdx*8+10h]
0x180029c10  mov     rcx, rbx; pSid
0x180029c13  call    cs:__imp_GetSidSubAuthorityCount
0x180029c19  movzx   edx, byte ptr [rax]
0x180029c1c  mov     rax, [rsp+1C0h+Sids]
0x180029c21  mov     ecx, [rax]
0x180029c23  lea     eax, [rdi+rdx]
0x180029c26  movzx   r14d, al
0x180029c2a  cmp     ecx, 3
0x180029c2d  cmovz   r14d, edx
0x180029c31  mov     cl, r14b; nSubAuthorityCount
0x180029c34  call    cs:__imp_GetSidLengthRequired
0x180029c3a  mov     [rsp+1C0h+cbSid], eax
0x180029c3e  cmp     eax, 40h ; '@'
0x180029c41  jbe     short loc_180029C72
0x180029c43  mov     ecx, eax; cb
0x180029c45  call    cs:__imp_CoTaskMemAlloc
0x180029c4b  mov     rsi, rax
0x180029c4e  test    rax, rax
0x180029c51  jnz     short loc_180029C6E
0x180029c53  mov     rcx, [rsp+1C0h+ReferencedDomains]; Buffer
0x180029c58  call    cs:__imp_LsaFreeMemory
0x180029c5e  mov     rcx, [rsp+1C0h+Sids]; Buffer
0x180029c63  call    cs:__imp_LsaFreeMemory
0x180029c69  jmp     loc_180029E3F
0x180029c6e  mov     eax, [rsp+1C0h+cbSid]
0x180029c72  mov     r8, rbx; pSourceSid
0x180029c75  mov     rdx, rsi; pDestinationSid
0x180029c78  mov     ecx, eax; nDestinationSidLength
0x180029c7a  call    cs:__imp_CopySid
0x180029c80  mov     rcx, rsi; pSid
0x180029c83  call    cs:__imp_GetSidSubAuthorityCount
0x180029c89  mov     [rax], r14b
0x180029c8c  mov     rbx, [rsp+1C0h+Sids]
0x180029c91  cmp     dword ptr [rbx], 3
0x180029c94  jz      short loc_180029CAA
0x180029c96  mov     ebx, [rbx+4]
0x180029c99  movzx   edx, r14b
0x180029c9d  sub     edx, edi; nSubAuthority
0x180029c9f  mov     rcx, rsi; pSid
0x180029ca2  call    cs:__imp_GetSidSubAuthority
0x180029ca8  mov     [rax], ebx
0x180029caa  mov     rcx, [rsp+1C0h+ReferencedDomains]; Buffer
0x180029caf  call    cs:__imp_LsaFreeMemory
0x180029cb5  mov     rcx, [rsp+1C0h+Sids]; Buffer
0x180029cba  call    cs:__imp_LsaFreeMemory
0x180029cc0  xor     ebx, ebx
0x180029cc2  cmp     cs:?g_bSysprepMode@@3HA, ebx; int g_bSysprepMode
0x180029cc8  cmovnz  r12, rbx
0x180029ccc  mov     rcx, rsi; pSid
0x180029ccf  call    cs:__imp_GetSidSubAuthorityCount
0x180029cd5  mov     cl, [rax]; nSubAuthorityCount
0x180029cd7  call    cs:__imp_GetSidLengthRequired
0x180029cdd  mov     [rsp+1C0h+cbSid], eax
0x180029ce1  test    r12, r12
0x180029ce4  jz      short loc_180029D0D
0x180029ce6  cmp     eax, [rbp+0C0h+arg_20]
0x180029cec  jnz     loc_180029AAD
0x180029cf2  mov     r8d, eax; Size
0x180029cf5  mov     rdx, r12; Buf2
0x180029cf8  mov     rcx, rsi; Buf1
0x180029cfb  call    memcmp_0
0x180029d00  test    eax, eax
0x180029d02  jz      loc_180029E1C
0x180029d08  jmp     loc_180029AAD
0x180029d0d  cmp     ebx, 3Ch ; '<'
0x180029d10  ja      loc_180029DC7
0x180029d16  mov     edx, ebx; WellKnownSidType
0x180029d18  mov     rcx, rsi; pSid
0x180029d1b  call    cs:__imp_IsWellKnownSid
0x180029d21  test    eax, eax
0x180029d23  jnz     short loc_180029D29
0x180029d25  add     ebx, edi
0x180029d27  jmp     short loc_180029D0D
0x180029d29  xor     ebx, ebx
0x180029d2b  mov     [rsp+1C0h+StringSid], rbx
0x180029d30  lea     rdx, [rsp+1C0h+StringSid]; StringSid
0x180029d35  mov     rcx, rsi; Sid
0x180029d38  call    cs:__imp_ConvertSidToStringSidW
0x180029d3e  test    eax, eax
0x180029d40  jz      loc_180029DC7
0x180029d46  mov     rcx, [rsp+1C0h+StringSid]; unsigned __int16 *
0x180029d4b  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180029d50  lea     eax, ds:2[rax*2]
0x180029d57  mov     ebx, eax
0x180029d59  mov     ecx, eax; cb
0x180029d5b  call    cs:__imp_CoTaskMemAlloc
0x180029d61  mov     r14, rax
0x180029d64  test    rax, rax
0x180029d67  jnz     short loc_180029D7B
0x180029d69  xor     edi, edi
0x180029d6b  mov     rcx, [rsp+1C0h+StringSid]; hMem
0x180029d70  call    cs:__imp_LocalFree
0x180029d76  jmp     loc_180029E3F
0x180029d7b  mov     r8, [rsp+1C0h+StringSid]; unsigned __int16 *
0x180029d80  mov     rdx, rbx; unsigned __int64
0x180029d83  mov     rcx, r14; unsigned __int16 *
0x180029d86  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180029d8b  mov     ebx, eax
0x180029d8d  mov     rcx, [rsp+1C0h+StringSid]; hMem
0x180029d92  call    cs:__imp_LocalFree
0x180029d98  test    ebx, ebx
0x180029d9a  jns     short loc_180029DAC
0x180029d9c  xor     edi, edi
0x180029d9e  mov     rcx, r14; pv
0x180029da1  call    cs:__imp_CoTaskMemFree
0x180029da7  jmp     loc_180029E3F
0x180029dac  mov     [rsp+1C0h+cchReferencedDomainName], rsi; void *
0x180029db1  mov     r9d, [rsp+1C0h+cbSid]; unsigned int
0x180029db6  mov     r8, r14; unsigned __int16 *
0x180029db9  mov     rdx, r15; struct ISimpleTableWrite *
0x180029dbc  call    ?UpdateCurrentRoleWithNewTextSid@CSecurityAdmin2@@QEAAJPEAUISimpleTableWrite@@PEAGKPEAX@Z; CSecurityAdmin2::UpdateCurrentRoleWithNewTextSid(ISimpleTableWrite *,ushort *,ulong,void *)
0x180029dc1  test    eax, eax
0x180029dc3  jns     short loc_180029E16
0x180029dc5  jmp     short loc_180029E3F
0x180029dc7  mov     rax, [r15]
0x180029dca  mov     rcx, r15
0x180029dcd  mov     rax, [rax+80h]
0x180029dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dd9  test    eax, eax
0x180029ddb  js      short loc_180029E3F
0x180029ddd  mov     rax, [r15]
0x180029de0  mov     r9, rsi
0x180029de3  mov     r8d, [rsp+1C0h+cbSid]
0x180029de8  mov     edx, 3
0x180029ded  mov     rcx, r15
0x180029df0  mov     rax, [rax+0A0h]
0x180029df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dfc  test    eax, eax
0x180029dfe  js      short loc_180029E3F
  ... truncated ...
```
