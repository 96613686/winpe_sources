# DirectoryServerUtil::GetObjectSidUsingLdap(LdapServer *,ushort const *,ushort * *)

- ea: `0x18001d304`
- end: `0x18001d554`
- name: `?GetObjectSidUsingLdap@DirectoryServerUtil@@CAJPEAVLdapServer@@PEBGPEAPEAG@Z`
- size: `592`
- prototype: `static int(struct LdapServer *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004b240`

## callees

- `0x1800084f4`
- `0x18000cbd8`
- `0x18000ddf0`
- `0x18001d304`
- `0x18001d55c`
- `0x1800307c4`
- `0x18003fc7c`
- `0x180044300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d520`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d520`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001d499`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001d499`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18001d529`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18001d529`

## string_xrefs

- `0x18001d4ff`: `CopyStringW`
- `0x18001d352`: `DirectoryServerUtil::GetObjectSidUsingLdap`
- `0x18001d3d7`: `DirectoryServerUtil::GetObjectSidUsingLdap`
- `0x18001d412`: `DirectoryServerUtil::GetObjectSidUsingLdap`
- `0x18001d46e`: `DirectoryServerUtil::GetObjectSidUsingLdap`
- `0x18001d4cf`: `DirectoryServerUtil::GetObjectSidUsingLdap`
- `0x18001d506`: `DirectoryServerUtil::GetObjectSidUsingLdap`
- `0x18001d449`: `objectSid`
- `0x18001d4c8`: `ConvertSidToStringSid`
- `0x18001d3bf`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18001d3b8`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x18001d3e6`: `pcszComputerDn`
- `0x18001d3f9`: `pcszComputerDn`
- `0x18001d421`: `ppszObjectSid`
- `0x18001d434`: `ppszObjectSid`

## pseudocode

```c
__int64 __fastcall DirectoryServerUtil::GetObjectSidUsingLdap(
        struct LdapServer *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  struct berval **v4; // rsi
  unsigned int v5; // ebx
  __int64 v6; // r8
  int v7; // eax
  const wchar_t *v8; // r8
  const wchar_t *v9; // rdx
  const unsigned __int16 *v10; // rcx
  const unsigned __int16 *v11; // rdx
  int AttributeValues; // eax
  DWORD LastError; // eax
  signed int v14; // eax
  unsigned __int64 v15; // rdx
  unsigned int v17; // [rsp+30h] [rbp-50h] BYREF
  struct berval **v18; // [rsp+38h] [rbp-48h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v20[16]; // [rsp+48h] [rbp-38h] BYREF
  const unsigned __int16 *v21; // [rsp+58h] [rbp-28h]
  __int64 v22; // [rsp+60h] [rbp-20h]
  const unsigned __int16 *v23; // [rsp+68h] [rbp-18h]
  __int64 v24; // [rsp+70h] [rbp-10h]

  StringSid = 0;
  v4 = 0;
  v18 = 0;
  v17 = 0;
  if ( !a1 )
  {
    v5 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"DirectoryServerUtil::GetObjectSidUsingLdap", L"pLdapServer");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v21 = L"DirectoryServerUtil::GetObjectSidUsingLdap";
      v22 = 86;
      v23 = L"pLdapServer";
      v24 = 24;
      v7 = McGenEventWrite_EventWriteTransfer(
             &UserDeviceRegistrationEventProvider_Context,
             NullOrEmptyParameterFailureEvent,
             v6,
             3,
             v20);
      if ( v7 )
      {
        v8 = L"EventWriteNullOrEmptyParameterFailureEvent";
        v9 = L"Logger::WriteNullOrEmptyParameterFailureEvent";
        v10 = L"%s: %s failed with win32 error code: 0x%08x.";
LABEL_20:
        Logger::TraceError(v10, v9, v8, (unsigned int)v7);
        goto LABEL_21;
      }
    }
    goto LABEL_21;
  }
  if ( !a2 )
  {
    v5 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DirectoryServerUtil::GetObjectSidUsingLdap",
      L"pcszComputerDn");
    v11 = L"pcszComputerDn";
LABEL_7:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DirectoryServerUtil::GetObjectSidUsingLdap", v11);
    goto LABEL_21;
  }
  if ( !a3 )
  {
    v5 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DirectoryServerUtil::GetObjectSidUsingLdap",
      L"ppszObjectSid");
    v11 = L"ppszObjectSid";
    goto LABEL_7;
  }
  *a3 = 0;
  AttributeValues = LdapServer::GetAttributeValues(a1, a2, (const unsigned __int16 *)a3, L"objectSid", &v17, &v18);
  v5 = AttributeValues;
  if ( AttributeValues >= 0 )
  {
    v4 = v18;
    if ( ConvertSidToStringSidW((*v18)->bv_val, &StringSid) )
    {
      v15 = -1;
      do
        ++v15;
      while ( StringSid[v15] );
      v7 = CopyStringW(StringSid, v15, a3);
      v5 = v7;
      if ( v7 < 0 )
      {
        v8 = L"CopyStringW";
        v9 = L"DirectoryServerUtil::GetObjectSidUsingLdap";
        v10 = L"%s: %s failed with error code: 0x%08x.";
        goto LABEL_20;
      }
    }
    else
    {
      LastError = GetLastError();
      Logger::WriteConvertSidToStringFailureEvent(LastError);
      v14 = GetLastError();
      v5 = v14;
      if ( v14 > 0 )
        v5 = (unsigned __int16)v14 | 0x80070000;
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x",
        L"DirectoryServerUtil::GetObjectSidUsingLdap",
        L"ConvertSidToStringSid",
        v5);
    }
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DirectoryServerUtil::GetObjectSidUsingLdap",
      L"LdapServer::GetAttributeValues",
      (unsigned int)AttributeValues);
    v4 = v18;
  }
LABEL_21:
  LocalFree(StringSid);
  ldap_value_free_len(v4);
  return v5;
}

```

## disassembly

```asm
0x18001d304  mov     [rsp-28h+arg_18], rbx
0x18001d309  push    rbp
0x18001d30a  push    rsi
0x18001d30b  push    rdi
0x18001d30c  push    r14
0x18001d30e  push    r15
0x18001d310  mov     rbp, rsp
0x18001d313  sub     rsp, 80h
0x18001d31a  mov     rax, cs:__security_cookie
0x18001d321  xor     rax, rsp
0x18001d324  mov     [rbp+var_8], rax
0x18001d328  xor     r14d, r14d
0x18001d32b  mov     rdi, r8
0x18001d32e  mov     [rbp+StringSid], r14
0x18001d332  mov     esi, r14d
0x18001d335  mov     [rbp+var_48], r14
0x18001d339  mov     [rbp+var_50], r14d
0x18001d33d  test    rcx, rcx
0x18001d340  jnz     loc_18001D3D2
0x18001d346  lea     r15, aPldapserver; "pLdapServer"
0x18001d34d  mov     ebx, 80070057h
0x18001d352  lea     rdi, aDirectoryserve_1; "DirectoryServerUtil::GetObjectSidUsingL"...
0x18001d359  mov     r8, r15
0x18001d35c  mov     rdx, rdi
0x18001d35f  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18001d366  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001d36b  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18001d372  jz      loc_18001D51C
0x18001d378  lea     rax, [rbp+var_38]
0x18001d37c  mov     [rbp+var_28], rdi
0x18001d380  lea     r9d, [r14+3]
0x18001d384  mov     [rsp+80h+var_60], rax
0x18001d389  lea     rdx, NullOrEmptyParameterFailureEvent
0x18001d390  mov     [rbp+var_20], 56h ; 'V'
0x18001d398  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18001d39f  mov     [rbp+var_18], r15
0x18001d3a3  mov     [rbp+var_10], 18h
0x18001d3ab  call    McGenEventWrite_EventWriteTransfer
0x18001d3b0  test    eax, eax
0x18001d3b2  jz      loc_18001D51C
0x18001d3b8  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x18001d3bf  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18001d3c6  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18001d3cd  jmp     loc_18001D514
0x18001d3d2  test    rdx, rdx
0x18001d3d5  jnz     short loc_18001D40D
0x18001d3d7  lea     rdi, aDirectoryserve_1; "DirectoryServerUtil::GetObjectSidUsingL"...
0x18001d3de  mov     ebx, 80070057h
0x18001d3e3  mov     rdx, rdi
0x18001d3e6  lea     r8, aPcszcomputerdn; "pcszComputerDn"
0x18001d3ed  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18001d3f4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001d3f9  lea     rdx, aPcszcomputerdn; "pcszComputerDn"
0x18001d400  mov     rcx, rdi; unsigned __int16 *
0x18001d403  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18001d408  jmp     loc_18001D51C
0x18001d40d  test    rdi, rdi
0x18001d410  jnz     short loc_18001D43D
0x18001d412  lea     rdi, aDirectoryserve_1; "DirectoryServerUtil::GetObjectSidUsingL"...
0x18001d419  mov     ebx, 80070057h
0x18001d41e  mov     rdx, rdi
0x18001d421  lea     r8, aPpszobjectsid; "ppszObjectSid"
0x18001d428  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18001d42f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001d434  lea     rdx, aPpszobjectsid; "ppszObjectSid"
0x18001d43b  jmp     short loc_18001D400
0x18001d43d  lea     rax, [rbp+var_48]
0x18001d441  mov     [r8], r14
0x18001d444  mov     [rsp+80h+var_58], rax; struct berval ***
0x18001d449  lea     r9, aObjectsid; "objectSid"
0x18001d450  lea     rax, [rbp+var_50]
0x18001d454  mov     [rsp+80h+var_60], rax; unsigned int *
0x18001d459  call    ?GetAttributeValues@LdapServer@@QEAAJPEBG00PEAKPEAPEAPEAUberval@@@Z; LdapServer::GetAttributeValues(ushort const *,ushort const *,ushort const *,ulong *,berval * * *)
0x18001d45e  mov     ebx, eax
0x18001d460  test    eax, eax
0x18001d462  jns     short loc_18001D48A
0x18001d464  mov     r9d, eax
0x18001d467  lea     r8, aLdapserverGeta; "LdapServer::GetAttributeValues"
0x18001d46e  lea     rdx, aDirectoryserve_1; "DirectoryServerUtil::GetObjectSidUsingL"...
0x18001d475  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18001d47c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001d481  mov     rsi, [rbp+var_48]
0x18001d485  jmp     loc_18001D51C
0x18001d48a  mov     rsi, [rbp+var_48]
0x18001d48e  lea     rdx, [rbp+StringSid]; StringSid
0x18001d492  mov     rcx, [rsi]
0x18001d495  mov     rcx, [rcx+8]; Sid
0x18001d499  call    cs:__imp_ConvertSidToStringSidW
0x18001d49f  test    eax, eax
0x18001d4a1  jnz     short loc_18001D4DF
0x18001d4a3  call    cs:__imp_GetLastError
0x18001d4a9  mov     ecx, eax; unsigned int
0x18001d4ab  call    ?WriteConvertSidToStringFailureEvent@Logger@@SAJK@Z; Logger::WriteConvertSidToStringFailureEvent(ulong)
0x18001d4b0  call    cs:__imp_GetLastError
0x18001d4b6  mov     ebx, eax
0x18001d4b8  test    eax, eax
0x18001d4ba  jle     short loc_18001D4C5
0x18001d4bc  movzx   ebx, ax
0x18001d4bf  or      ebx, 80070000h
0x18001d4c5  mov     r9d, ebx
0x18001d4c8  lea     r8, aConvertsidtost_1; "ConvertSidToStringSid"
0x18001d4cf  lea     rdx, aDirectoryserve_1; "DirectoryServerUtil::GetObjectSidUsingL"...
0x18001d4d6  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x18001d4dd  jmp     short loc_18001D517
0x18001d4df  mov     rcx, [rbp+StringSid]; Source
0x18001d4e3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001d4e7  inc     rdx; unsigned __int64
0x18001d4ea  cmp     [rcx+rdx*2], r14w
0x18001d4ef  jnz     short loc_18001D4E7
0x18001d4f1  mov     r8, rdi; unsigned __int16 **
0x18001d4f4  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x18001d4f9  mov     ebx, eax
0x18001d4fb  test    eax, eax
0x18001d4fd  jns     short loc_18001D51C
0x18001d4ff  lea     r8, aCopystringw; "CopyStringW"
0x18001d506  lea     rdx, aDirectoryserve_1; "DirectoryServerUtil::GetObjectSidUsingL"...
0x18001d50d  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18001d514  mov     r9d, eax
0x18001d517  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001d51c  mov     rcx, [rbp+StringSid]; hMem
0x18001d520  call    cs:__imp_LocalFree
0x18001d526  mov     rcx, rsi; vals
0x18001d529  call    cs:__imp_ldap_value_free_len
0x18001d52f  mov     eax, ebx
0x18001d531  mov     rcx, [rbp+var_8]
0x18001d535  xor     rcx, rsp; StackCookie
0x18001d538  call    __security_check_cookie
0x18001d53d  mov     rbx, [rsp+80h+arg_18]
0x18001d545  add     rsp, 80h
0x18001d54c  pop     r15
0x18001d54e  pop     r14
0x18001d550  pop     rdi
0x18001d551  pop     rsi
0x18001d552  pop     rbp
0x18001d553  retn
```
