# GetSingleEntry(LDAPConnection *,ushort *,ulong,ushort *,ushort * *,ldapmsg * *)

- ea: `0x18001cd90`
- end: `0x18001d045`
- name: `?GetSingleEntry@@YAKPEAVLDAPConnection@@PEAGK1PEAPEAGPEAPEAUldapmsg@@@Z`
- size: `693`
- prototype: `unsigned int __usercall@<eax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned __int16 *@<r9>, unsigned __int16 **, struct ldapmsg **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001d04c`

## callees

- `0x180018218`
- `0x18001cd90`
- `0x18001db68`
- `0x1800254a0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001cf0a`
- `KERNEL32!LeaveCriticalSection` at `0x18001cf0a`
- `KERNEL32!EnterCriticalSection` at `0x18001cef5`
- `KERNEL32!EnterCriticalSection` at `0x18001cef5`
- `KERNEL32!TryEnterCriticalSection` at `0x18001ced9`
- `KERNEL32!TryEnterCriticalSection` at `0x18001ced9`
- `KERNEL32!SwitchToThread` at `0x18001ceea`
- `KERNEL32!SwitchToThread` at `0x18001ceea`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001ce12`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001cf4a`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001ce12`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001cf4a`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001cf12`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001cf2d`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001cf12`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001cf2d`
- `WLDAP32!__imp_ldap_count_entries` at `0x18001d00d`
- `WLDAP32!__imp_ldap_count_entries` at `0x18001d00d`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001d025`
- `WLDAP32!__imp_ldap_msgfree` at `0x18001d025`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001cebb`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001d001`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001cebb`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001d001`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18001cde4`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18001cde4`

## string_xrefs

- `0x18001ce71`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Code = 0x%X \nExtended error info: %S`
- `0x18001cfb1`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Code = 0x%X \nExtended error info: %S`

## pseudocode

```c
__int64 __fastcall GetSingleEntry(
        LPCRITICAL_SECTION lpCriticalSection,
        unsigned __int16 *a2,
        ULONG a3,
        unsigned __int16 *a4,
        unsigned __int16 **a5,
        struct ldapmsg **a6)
{
  LDAPMessage **v7; // r14
  ULONG v8; // eax
  ULONG v9; // edi
  WCHAR *v10; // rcx
  const wchar_t *v11; // rsi
  int v12; // esi
  ULONG v13; // edi
  ULONG lm_returncode; // ecx
  WCHAR *v15; // rcx
  const wchar_t *v16; // rsi
  WCHAR *outvalue; // [rsp+A0h] [rbp+38h] BYREF

  v7 = a6;
  v8 = ldap_search_ext_sW(
         *(LDAP **)&lpCriticalSection[2].LockCount,
         a2,
         a3,
         a4,
         a5,
         0,
         0,
         0,
         &LDAPConnection::SEARCH_TIMEOUT,
         0,
         a6);
  v9 = v8;
  if ( !v8 || v8 == 9 )
  {
    lm_returncode = (*v7)->lm_returncode;
    if ( lm_returncode )
    {
      v13 = LdapMapErrorToWin32(lm_returncode);
      outvalue = 0;
      if ( ldap_get_optionW(*(LDAP **)&lpCriticalSection[2].LockCount, 51, &outvalue) )
      {
        v15 = 0;
        outvalue = 0;
      }
      else
      {
        v15 = outvalue;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v16 = L"Failed to get extended error info";
        WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. "
                    "Code = 0x%X \n"
                    "Extended error info: %S");
        if ( outvalue )
          v16 = outvalue;
        WPP_SF_ssDS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (__int64)"ldap_search_ext_sW",
          (*v7)->lm_returncode,
          (__int64)v16);
        v15 = outvalue;
      }
      if ( v15 )
        ldap_memfreeW(v15);
    }
    else
    {
      if ( ldap_count_entries(*(LDAP **)&lpCriticalSection[2].LockCount, *v7) == 1 )
        return 0;
      v13 = 1317;
    }
  }
  else
  {
    outvalue = 0;
    if ( ldap_get_optionW(*(LDAP **)&lpCriticalSection[2].LockCount, 51, &outvalue) )
    {
      v10 = 0;
      outvalue = 0;
    }
    else
    {
      v10 = outvalue;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v11 = L"Failed to get extended error info";
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Co"
                  "de = 0x%X \n"
                  "Extended error info: %S");
      if ( outvalue )
        v11 = outvalue;
      WPP_SF_ssDS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"ldap_search_ext_sW", v9, (__int64)v11);
      v10 = outvalue;
    }
    if ( v10 )
      ldap_memfreeW(v10);
    if ( v9 == 81 )
    {
      lpCriticalSection[1].RecursionCount = 1;
    }
    else if ( v9 != 87 )
    {
      v12 = 0;
      while ( !TryEnterCriticalSection(lpCriticalSection) )
      {
        if ( ++v12 >= 100 )
        {
          EnterCriticalSection(lpCriticalSection);
          break;
        }
        SwitchToThread();
      }
      ++lpCriticalSection[1].LockCount;
      lpCriticalSection[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)GetSystemTimeAsDWORDLONG();
      LeaveCriticalSection(lpCriticalSection);
    }
    v13 = LdapMapErrorToWin32(v9);
  }
  if ( *v7 )
  {
    ldap_msgfree(*v7);
    *v7 = 0;
  }
  return v13;
}

```

## disassembly

```asm
0x18001cd90  mov     r11, rsp
0x18001cd93  push    rbp
0x18001cd94  push    rbx
0x18001cd95  push    rsi
0x18001cd96  push    rdi
0x18001cd97  push    r14
0x18001cd99  push    r15
0x18001cd9b  mov     rbp, rsp
0x18001cd9e  sub     rsp, 68h
0x18001cda2  mov     rbx, rcx
0x18001cda5  mov     r14, [rbp+arg_28]
0x18001cda9  mov     [r11-48h], r14
0x18001cdad  mov     [rsp+68h+SizeLimit], 0; SizeLimit
0x18001cdb5  lea     rax, ?SEARCH_TIMEOUT@LDAPConnection@@2Ul_timeval@@A; l_timeval LDAPConnection::SEARCH_TIMEOUT
0x18001cdbc  mov     [r11-58h], rax
0x18001cdc0  mov     qword ptr [r11-60h], 0
0x18001cdc8  mov     qword ptr [r11-68h], 0
0x18001cdd0  mov     [rsp+68h+attrsonly], 0; attrsonly
0x18001cdd8  mov     rax, [rbp+arg_20]
0x18001cddc  mov     [r11-78h], rax
0x18001cde0  mov     rcx, [rcx+58h]; ld
0x18001cde4  call    cs:__imp_ldap_search_ext_sW
0x18001cdea  mov     edi, eax
0x18001cdec  test    eax, eax
0x18001cdee  jz      loc_18001CF1F
0x18001cdf4  cmp     eax, 9
0x18001cdf7  jz      loc_18001CF1F
0x18001cdfd  mov     [rbp+outvalue], 0
0x18001ce05  lea     r8, [rbp+outvalue]; outvalue
0x18001ce09  mov     edx, 33h ; '3'; option
0x18001ce0e  mov     rcx, [rbx+58h]; ld
0x18001ce12  call    cs:__imp_ldap_get_optionW
0x18001ce18  test    eax, eax
0x18001ce1a  jz      short loc_18001CE24
0x18001ce1c  xor     ecx, ecx
0x18001ce1e  mov     [rbp+outvalue], rcx
0x18001ce22  jmp     short loc_18001CE28
0x18001ce24  mov     rcx, [rbp+outvalue]
0x18001ce28  lea     rdx, WPP_GLOBAL_Control
0x18001ce2f  mov     rax, cs:WPP_GLOBAL_Control
0x18001ce36  cmp     rax, rdx
0x18001ce39  jz      short loc_18001CEB6
0x18001ce3b  cmp     byte ptr [rax+19h], 2
0x18001ce3f  jb      short loc_18001CEB6
0x18001ce41  test    byte ptr [rax+1Ch], 4
0x18001ce45  jz      short loc_18001CEB6
0x18001ce47  lea     rsi, aFailedToGetExt; "Failed to get extended error info"
0x18001ce4e  mov     rax, rsi
0x18001ce51  test    rcx, rcx
0x18001ce54  cmovnz  rax, rcx
0x18001ce58  mov     [rsp+68h+var_48], rax
0x18001ce5d  mov     r9d, edi
0x18001ce60  lea     r15, aLdapSearchExtS; "ldap_search_ext_sW"
0x18001ce67  mov     r8, r15
0x18001ce6a  lea     rdx, aNpssvc; "NPSSVC"
0x18001ce71  lea     rcx, aCpuPidTidNowSL_1; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18001ce78  call    WppDbgPrint
0x18001ce7d  mov     rax, [rbp+outvalue]
0x18001ce81  test    rax, rax
0x18001ce84  cmovnz  rsi, rax
0x18001ce88  mov     edx, 0Fh
0x18001ce8d  mov     [rsp+68h+var_38], rsi; __int64
0x18001ce92  mov     [rsp+68h+attrsonly], edi; char
0x18001ce96  mov     [rsp+68h+var_48], r15; __int64
0x18001ce9b  lea     r8, WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids
0x18001cea2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cea9  mov     rcx, [rcx+10h]; LoggerHandle
0x18001cead  call    WPP_SF_ssDS
0x18001ceb2  mov     rcx, [rbp+outvalue]; Block
0x18001ceb6  test    rcx, rcx
0x18001ceb9  jz      short loc_18001CEC1
0x18001cebb  call    cs:__imp_ldap_memfreeW
0x18001cec1  cmp     edi, 51h ; 'Q'
0x18001cec4  jnz     short loc_18001CECF
0x18001cec6  mov     dword ptr [rbx+34h], 1
0x18001cecd  jmp     short loc_18001CF10
0x18001cecf  cmp     edi, 57h ; 'W'
0x18001ced2  jz      short loc_18001CF10
0x18001ced4  xor     esi, esi
0x18001ced6  mov     rcx, rbx; lpCriticalSection
0x18001ced9  call    cs:__imp_TryEnterCriticalSection
0x18001cedf  test    eax, eax
0x18001cee1  jnz     short loc_18001CEFB
0x18001cee3  inc     esi
0x18001cee5  cmp     esi, 64h ; 'd'
0x18001cee8  jge     short loc_18001CEF2
0x18001ceea  call    cs:__imp_SwitchToThread
0x18001cef0  jmp     short loc_18001CED6
0x18001cef2  mov     rcx, rbx; lpCriticalSection
0x18001cef5  call    cs:__imp_EnterCriticalSection
0x18001cefb  inc     dword ptr [rbx+30h]
0x18001cefe  call    GetSystemTimeAsDWORDLONG
0x18001cf03  mov     [rbx+28h], rax
0x18001cf07  mov     rcx, rbx; lpCriticalSection
0x18001cf0a  call    cs:__imp_LeaveCriticalSection
0x18001cf10  mov     ecx, edi; LdapError
0x18001cf12  call    cs:__imp_LdapMapErrorToWin32
0x18001cf18  mov     edi, eax
0x18001cf1a  jmp     loc_18001D01D
0x18001cf1f  mov     rdx, [r14]; res
0x18001cf22  mov     ecx, [rdx+38h]; LdapError
0x18001cf25  test    ecx, ecx
0x18001cf27  jz      loc_18001D009
0x18001cf2d  call    cs:__imp_LdapMapErrorToWin32
0x18001cf33  mov     edi, eax
0x18001cf35  mov     [rbp+outvalue], 0
0x18001cf3d  lea     r8, [rbp+outvalue]; outvalue
0x18001cf41  mov     edx, 33h ; '3'; option
0x18001cf46  mov     rcx, [rbx+58h]; ld
0x18001cf4a  call    cs:__imp_ldap_get_optionW
0x18001cf50  test    eax, eax
0x18001cf52  jz      short loc_18001CF5C
0x18001cf54  xor     ecx, ecx
0x18001cf56  mov     [rbp+outvalue], rcx
0x18001cf5a  jmp     short loc_18001CF60
0x18001cf5c  mov     rcx, [rbp+outvalue]
0x18001cf60  lea     rdx, WPP_GLOBAL_Control
0x18001cf67  mov     rax, cs:WPP_GLOBAL_Control
0x18001cf6e  cmp     rax, rdx
0x18001cf71  jz      loc_18001CFFC
0x18001cf77  cmp     byte ptr [rax+19h], 2
0x18001cf7b  jb      short loc_18001CFFC
0x18001cf7d  test    byte ptr [rax+1Ch], 4
0x18001cf81  jz      short loc_18001CFFC
0x18001cf83  lea     rsi, aFailedToGetExt; "Failed to get extended error info"
0x18001cf8a  mov     rax, rsi
0x18001cf8d  test    rcx, rcx
0x18001cf90  cmovnz  rax, rcx
0x18001cf94  mov     r9, [r14]
0x18001cf97  mov     [rsp+68h+var_48], rax
0x18001cf9c  mov     r9d, [r9+38h]
0x18001cfa0  lea     r15, aLdapSearchExtS; "ldap_search_ext_sW"
0x18001cfa7  mov     r8, r15
0x18001cfaa  lea     rdx, aNpssvc; "NPSSVC"
0x18001cfb1  lea     rcx, aCpuPidTidNowSL_1; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18001cfb8  call    WppDbgPrint
0x18001cfbd  mov     rax, [rbp+outvalue]
0x18001cfc1  test    rax, rax
0x18001cfc4  cmovnz  rsi, rax
0x18001cfc8  mov     rax, [r14]
0x18001cfcb  mov     edx, 10h
0x18001cfd0  mov     [rsp+68h+var_38], rsi; __int64
0x18001cfd5  mov     eax, [rax+38h]
0x18001cfd8  mov     [rsp+68h+attrsonly], eax; char
0x18001cfdc  mov     [rsp+68h+var_48], r15; __int64
0x18001cfe1  lea     r8, WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids
0x18001cfe8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfef  mov     rcx, [rcx+10h]; LoggerHandle
0x18001cff3  call    WPP_SF_ssDS
0x18001cff8  mov     rcx, [rbp+outvalue]; Block
0x18001cffc  test    rcx, rcx
0x18001cfff  jz      short loc_18001D01D
0x18001d001  call    cs:__imp_ldap_memfreeW
0x18001d007  jmp     short loc_18001D01D
0x18001d009  mov     rcx, [rbx+58h]; ld
0x18001d00d  call    cs:__imp_ldap_count_entries
0x18001d013  cmp     eax, 1
0x18001d016  jz      short loc_18001D036
0x18001d018  mov     edi, 525h
0x18001d01d  mov     rcx, [r14]; res
0x18001d020  test    rcx, rcx
0x18001d023  jz      short loc_18001D032
0x18001d025  call    cs:__imp_ldap_msgfree
0x18001d02b  mov     qword ptr [r14], 0
0x18001d032  mov     eax, edi
0x18001d034  jmp     short loc_18001D038
0x18001d036  xor     eax, eax
0x18001d038  add     rsp, 68h
0x18001d03c  pop     r15
0x18001d03e  pop     r14
0x18001d040  pop     rdi
0x18001d041  pop     rsi
0x18001d042  pop     rbx
0x18001d043  pop     rbp
0x18001d044  retn
```
