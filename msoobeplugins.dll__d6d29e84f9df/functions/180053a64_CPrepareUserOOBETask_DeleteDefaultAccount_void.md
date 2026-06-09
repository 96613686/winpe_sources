# CPrepareUserOOBETask::_DeleteDefaultAccount(void)

- ea: `0x180053a64`
- end: `0x180053c6d`
- name: `?_DeleteDefaultAccount@CPrepareUserOOBETask@@AEAAJXZ`
- size: `521`
- prototype: `__int64 __fastcall(CPrepareUserOOBETask *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180052d20`
- `0x180053060`

## callees

- `0x180003470`
- `0x180008524`
- `0x180008544`
- `0x1800230b0`
- `0x180031ff0`
- `0x180046de8`
- `0x180046e0c`
- `0x180053a64`
- `0x180053e5c`
- `0x1800b8834`
- `0x1800bd2a8`
- `0x1800bda90`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180053af4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180053af4`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180053ad0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180053ad0`
- `USERENV!DeleteProfileW` at `0x180053b81`
- `USERENV!DeleteProfileW` at `0x180053b81`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x180053bb4`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x180053beb`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x180053bb4`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x180053beb`
- `samcli!NetUserDel` at `0x180053b38`
- `samcli!NetUserDel` at `0x180053b38`

## string_xrefs

- `0x180053bd6`: `DefaultAccountSID`
- `0x180053b03`: `shell\oobe\machine\plugins\useroobepreparation\prepareuseroobetask.cpp`
- `0x180053b5e`: `shell\oobe\machine\plugins\useroobepreparation\prepareuseroobetask.cpp`
- `0x180053b8b`: `shell\oobe\machine\plugins\useroobepreparation\prepareuseroobetask.cpp`
- `0x180053bc5`: `shell\oobe\machine\plugins\useroobepreparation\prepareuseroobetask.cpp`
- `0x180053bfc`: `shell\oobe\machine\plugins\useroobepreparation\prepareuseroobetask.cpp`
- `0x180053c21`: `shell\oobe\machine\plugins\useroobepreparation\prepareuseroobetask.cpp`
- `0x180053c35`: `Successfully deleting the default user account with deleteStatus = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPrepareUserOOBETask::_DeleteDefaultAccount(LPCWSTR *this)
{
  const char *v2; // r9
  __int64 v3; // rdx
  unsigned int LastError; // ebx
  DWORD v5; // eax
  int v6; // eax
  const char *v7; // r9
  unsigned int v8; // eax
  unsigned int v9; // eax
  int v10; // eax
  unsigned int ReferencedDomainName; // [rsp+20h] [rbp-69h]
  LPWSTR StringSid; // [rsp+40h] [rbp-49h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-41h] BYREF
  DWORD cchReferencedDomainName; // [rsp+4Ch] [rbp-3Dh] BYREF
  DWORD cbSid[4]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE Sid[80]; // [rsp+60h] [rbp-29h] BYREF
  WCHAR v18[16]; // [rsp+B0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  cbSid[0] = 68;
  cchReferencedDomainName = 16;
  peUse = 0;
  StringSid = 0;
  if ( !LookupAccountNameW(0, this[69], Sid, cbSid, v18, &cchReferencedDomainName, &peUse) )
  {
    v3 = 254;
LABEL_5:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v3,
                  (unsigned int)"shell\\oobe\\machine\\plugins\\useroobepreparation\\prepareuseroobetask.cpp",
                  v2);
    goto LABEL_18;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    v3 = 255;
    goto LABEL_5;
  }
  UnattendLogW(0, L"Deleting the default user account with name = %s", this[69]);
  v5 = NetUserDel(0, this[69]);
  if ( v5 )
  {
    v6 = NetpApiStatusToNtStatus(v5);
    LastError = v6 | 0x10000000;
    if ( v6 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x107,
        (unsigned int)"shell\\oobe\\machine\\plugins\\useroobepreparation\\prepareuseroobetask.cpp",
        (const char *)LastError,
        ReferencedDomainName);
  }
  else
  {
    if ( !DeleteProfileW(StringSid, 0, 0) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x10B,
        (unsigned int)"shell\\oobe\\machine\\plugins\\useroobepreparation\\prepareuseroobetask.cpp",
        v7);
    v8 = DeletePersistedRegistryValue(
           L"OOBE",
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
           L"DefaultAccountSAMName");
    if ( v8 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x10E,
        (unsigned int)"shell\\oobe\\machine\\plugins\\useroobepreparation\\prepareuseroobetask.cpp",
        (const char *)v8,
        ReferencedDomainName);
    v9 = DeletePersistedRegistryValue(
           L"OOBE",
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
           L"DefaultAccountSID");
    if ( v9 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x10F,
        (unsigned int)"shell\\oobe\\machine\\plugins\\useroobepreparation\\prepareuseroobetask.cpp",
        (const char *)v9,
        ReferencedDomainName);
    v10 = DeleteSystemDataRegistryKeyForUser(Sid);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x110,
        (unsigned int)"shell\\oobe\\machine\\plugins\\useroobepreparation\\prepareuseroobetask.cpp",
        (const char *)(unsigned int)v10,
        ReferencedDomainName);
    UnattendLogW(0, L"Successfully deleting the default user account with deleteStatus = %d", 0);
    LastError = 0;
  }
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>(&StringSid);
  return LastError;
}

```

## disassembly

```asm
0x180053a64  mov     [rsp-8+arg_8], rbx
0x180053a69  push    rbp
0x180053a6a  lea     rbp, [rsp-57h]
0x180053a6f  sub     rsp, 0E0h
0x180053a76  mov     rax, cs:__security_cookie
0x180053a7d  xor     rax, rsp
0x180053a80  mov     [rbp+57h+var_10], rax
0x180053a84  mov     rbx, rcx
0x180053a87  mov     [rbp+57h+cbSid], 44h ; 'D'
0x180053a8e  mov     [rbp+57h+var_94], 10h
0x180053a95  mov     [rbp+57h+var_98], 0
0x180053a9c  mov     [rbp+57h+StringSid], 0
0x180053aa4  lea     rax, [rbp+57h+var_98]
0x180053aa8  mov     [rsp+0E0h+peUse], rax; peUse
0x180053aad  lea     rax, [rbp+57h+var_94]
0x180053ab1  mov     [rsp+0E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180053ab6  lea     rax, [rbp+57h+var_30]
0x180053aba  mov     [rsp+0E0h+ReferencedDomainName], rax; int
0x180053abf  lea     r9, [rbp+57h+cbSid]; cbSid
0x180053ac3  lea     r8, [rbp+57h+Sid]; Sid
0x180053ac7  mov     rdx, [rcx+228h]; lpAccountName
0x180053ace  xor     ecx, ecx; lpSystemName
0x180053ad0  call    cs:__imp_LookupAccountNameW
0x180053ad6  test    eax, eax
0x180053ad8  jnz     short loc_180053AE1
0x180053ada  mov     edx, 0FEh
0x180053adf  jmp     short loc_180053B03
0x180053ae1  xor     edx, edx
0x180053ae3  lea     rcx, [rbp+57h+StringSid]
0x180053ae7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180053aec  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180053af0  lea     rcx, [rbp+57h+Sid]; Sid
0x180053af4  call    cs:__imp_ConvertSidToStringSidW
0x180053afa  test    eax, eax
0x180053afc  jnz     short loc_180053B1A
0x180053afe  mov     edx, 0FFh; void *
0x180053b03  lea     r8, aShellOobeMachi_8; "shell\\oobe\\machine\\plugins\\useroobe"...
0x180053b0a  mov     rcx, [rbp+5Fh]; this
0x180053b0e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180053b13  mov     ebx, eax
0x180053b15  jmp     loc_180053C45
0x180053b1a  mov     r8, [rbx+228h]
0x180053b21  lea     rdx, aDeletingTheDef; "Deleting the default user account with "...
0x180053b28  xor     ecx, ecx
0x180053b2a  call    UnattendLogW
0x180053b2f  mov     rdx, [rbx+228h]; username
0x180053b36  xor     ecx, ecx; servername
0x180053b38  call    cs:__imp_NetUserDel
0x180053b3e  test    eax, eax
0x180053b40  jz      short loc_180053B74
0x180053b42  mov     ecx, eax
0x180053b44  call    NetpApiStatusToNtStatus
0x180053b49  mov     ebx, eax
0x180053b4b  or      ebx, 10000000h
0x180053b51  jge     loc_180053C45
0x180053b57  mov     rcx, [rbp+5Fh]; this
0x180053b5b  mov     r9d, ebx; char *
0x180053b5e  lea     r8, aShellOobeMachi_8; "shell\\oobe\\machine\\plugins\\useroobe"...
0x180053b65  mov     edx, 107h; void *
0x180053b6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053b6f  jmp     loc_180053C45
0x180053b74  mov     rbx, [rbp+5Fh]
0x180053b78  xor     r8d, r8d; lpComputerName
0x180053b7b  xor     edx, edx; lpProfilePath
0x180053b7d  mov     rcx, [rbp+57h+StringSid]; lpSidString
0x180053b81  call    cs:__imp_DeleteProfileW
0x180053b87  test    eax, eax
0x180053b89  jnz     short loc_180053B9F
0x180053b8b  lea     r8, aShellOobeMachi_8; "shell\\oobe\\machine\\plugins\\useroobe"...
0x180053b92  mov     edx, 10Bh; void *
0x180053b97  mov     rcx, rbx; this
0x180053b9a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180053b9f  lea     r8, aDefaultaccount_0; "DefaultAccountSAMName"
0x180053ba6  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180053bad  lea     rcx, aOobe_0; "OOBE"
0x180053bb4  call    cs:__imp_DeletePersistedRegistryValue
0x180053bba  mov     rcx, [rbp+5Fh]; this
0x180053bbe  test    eax, eax
0x180053bc0  jz      short loc_180053BD6
0x180053bc2  mov     r9d, eax; char *
0x180053bc5  lea     r8, aShellOobeMachi_8; "shell\\oobe\\machine\\plugins\\useroobe"...
0x180053bcc  mov     edx, 10Eh; void *
0x180053bd1  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180053bd6  lea     r8, aDefaultaccount_1; "DefaultAccountSID"
0x180053bdd  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180053be4  lea     rcx, aOobe_0; "OOBE"
0x180053beb  call    cs:__imp_DeletePersistedRegistryValue
0x180053bf1  mov     rcx, [rbp+5Fh]; this
0x180053bf5  test    eax, eax
0x180053bf7  jz      short loc_180053C0D
0x180053bf9  mov     r9d, eax; char *
0x180053bfc  lea     r8, aShellOobeMachi_8; "shell\\oobe\\machine\\plugins\\useroobe"...
0x180053c03  mov     edx, 10Fh; void *
0x180053c08  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180053c0d  lea     rcx, [rbp+57h+Sid]; void *
0x180053c11  call    ?DeleteSystemDataRegistryKeyForUser@@YAJPEAX@Z; DeleteSystemDataRegistryKeyForUser(void *)
0x180053c16  mov     rcx, [rbp+5Fh]; this
0x180053c1a  test    eax, eax
0x180053c1c  jns     short loc_180053C32
0x180053c1e  mov     r9d, eax; char *
0x180053c21  lea     r8, aShellOobeMachi_8; "shell\\oobe\\machine\\plugins\\useroobe"...
0x180053c28  mov     edx, 110h; void *
0x180053c2d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180053c32  xor     r8d, r8d
0x180053c35  lea     rdx, aSuccessfullyDe; "Successfully deleting the default user "...
0x180053c3c  xor     ecx, ecx
0x180053c3e  call    UnattendLogW
0x180053c43  xor     ebx, ebx
0x180053c45  lea     rcx, [rbp+57h+StringSid]
0x180053c49  call    ??1?$unique_storage@U?$resource_policy@PEAU_STORAGE_DEVICE_DESCRIPTOR@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>(void)
0x180053c4e  mov     eax, ebx
0x180053c50  mov     rcx, [rbp+57h+var_10]
0x180053c54  xor     rcx, rsp; StackCookie
0x180053c57  call    __security_check_cookie
0x180053c5c  mov     rbx, [rsp+0E0h+arg_8]
0x180053c64  add     rsp, 0E0h
0x180053c6b  pop     rbp
0x180053c6c  retn
```
