# Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::IsCallerAdminAccount(bool &)

- ea: `0x180098f54`
- end: `0x180099099`
- name: `?IsCallerAdminAccount@FlagConfigurationManager@Flags@ConfigurationManagement@Internal@Windows@@CAJAEA_N@Z`
- size: `325`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180099788`

## callees

- `0x18000949c`
- `0x18006f180`
- `0x18006fcec`
- `0x180098b74`
- `0x180098f54`
- `0x1800993d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098fd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098fd8`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180098fce`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180098fce`

## string_xrefs

- `0x180098f85`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x180099045`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::IsCallerAdminAccount(
        bool *a1)
{
  signed int CurrentUserToken; // eax
  unsigned int v3; // ebx
  signed int LastError; // eax
  unsigned int v6; // ebx
  signed int IsLoggedInUserMatchSID; // eax
  unsigned int v8; // ebx
  unsigned int v9; // [rsp+20h] [rbp-48h]
  int v10; // [rsp+20h] [rbp-48h]
  unsigned int v11; // [rsp+28h] [rbp-40h]
  unsigned int v12; // [rsp+30h] [rbp-38h]
  unsigned int v13; // [rsp+38h] [rbp-30h]
  unsigned int v14; // [rsp+40h] [rbp-28h]
  unsigned int v15; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HANDLE ExistingTokenHandle; // [rsp+70h] [rbp+8h] BYREF
  HANDLE ClientToken; // [rsp+78h] [rbp+10h] BYREF
  void *DuplicateTokenHandle; // [rsp+80h] [rbp+18h] BYREF

  *a1 = 0;
  ExistingTokenHandle = 0;
  CurrentUserToken = Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::GetCurrentUserToken(
                       (__int64)a1,
                       (__int64)&ExistingTokenHandle);
  v3 = CurrentUserToken;
  if ( CurrentUserToken >= 0 )
  {
    ClientToken = 0;
    DuplicateTokenHandle = 0;
    if ( DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &ClientToken,
        DuplicateTokenHandle);
      IsLoggedInUserMatchSID = Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::IsLoggedInUserMatchSID(
                                 ClientToken,
                                 2u,
                                 0x20u,
                                 0x220u,
                                 v9,
                                 v11,
                                 v12,
                                 v13,
                                 v14,
                                 v15,
                                 a1);
      v8 = IsLoggedInUserMatchSID;
      if ( IsLoggedInUserMatchSID >= 0 )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ClientToken);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x30D,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
          (const char *)(unsigned int)IsLoggedInUserMatchSID,
          v10);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ClientToken);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
        return v8;
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ClientToken);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
      return v6;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F9,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
      (const char *)(unsigned int)CurrentUserToken,
      v9);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
    return v3;
  }
}

```

## disassembly

```asm
0x180098f54  mov     [rsp+arg_18], rbx
0x180098f59  push    rdi
0x180098f5a  sub     rsp, 60h
0x180098f5e  mov     rdi, rcx
0x180098f61  mov     byte ptr [rcx], 0
0x180098f64  mov     [rsp+68h+ExistingTokenHandle], 0
0x180098f6d  lea     rdx, [rsp+68h+ExistingTokenHandle]
0x180098f72  call    ?GetCurrentUserToken@FlagConfigurationManager@Flags@ConfigurationManagement@Internal@Windows@@CAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::GetCurrentUserToken(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x180098f77  mov     ebx, eax
0x180098f79  test    eax, eax
0x180098f7b  jns     short loc_180098FA7
0x180098f7d  mov     rcx, [rsp+68h]; this
0x180098f82  mov     r9d, eax; char *
0x180098f85  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x180098f8c  mov     edx, 2F9h; void *
0x180098f91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098f96  lea     rcx, [rsp+68h+ExistingTokenHandle]
0x180098f9b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180098fa0  mov     eax, ebx
0x180098fa2  jmp     loc_18009908A
0x180098fa7  mov     [rsp+68h+ClientToken], 0
0x180098fb0  mov     [rsp+68h+DuplicateTokenHandle], 0
0x180098fbc  lea     r8, [rsp+68h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180098fc4  mov     edx, 2; ImpersonationLevel
0x180098fc9  mov     rcx, [rsp+68h+ExistingTokenHandle]; ExistingTokenHandle
0x180098fce  call    cs:__imp_DuplicateToken
0x180098fd4  test    eax, eax
0x180098fd6  jnz     short loc_180099008
0x180098fd8  call    cs:__imp_GetLastError
0x180098fde  mov     ebx, eax
0x180098fe0  test    eax, eax
0x180098fe2  jle     short loc_180098FED
0x180098fe4  movzx   ebx, ax
0x180098fe7  or      ebx, 80070000h
0x180098fed  lea     rcx, [rsp+68h+ClientToken]
0x180098ff2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180098ff7  lea     rcx, [rsp+68h+ExistingTokenHandle]
0x180098ffc  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180099001  mov     eax, ebx
0x180099003  jmp     loc_18009908A
0x180099008  mov     rdx, [rsp+68h+DuplicateTokenHandle]
0x180099010  lea     rcx, [rsp+68h+ClientToken]
0x180099015  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18009901a  mov     [rsp+68h+var_18], rdi; bool *
0x18009901f  mov     r9d, 220h; unsigned int
0x180099025  mov     r8d, 20h ; ' '; unsigned int
0x18009902b  mov     dl, 2; unsigned __int8
0x18009902d  mov     rcx, [rsp+68h+ClientToken]; ClientToken
0x180099032  call    ?IsLoggedInUserMatchSID@FlagConfigurationManager@Flags@ConfigurationManagement@Internal@Windows@@CAJPEAXEKKKKKKKKAEA_N@Z; Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::IsLoggedInUserMatchSID(void *,uchar,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,bool &)
0x180099037  mov     ebx, eax
0x180099039  test    eax, eax
0x18009903b  jns     short loc_18009906E
0x18009903d  mov     rcx, [rsp+68h]; this
0x180099042  mov     r9d, eax; char *
0x180099045  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x18009904c  mov     edx, 30Dh; void *
0x180099051  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099056  lea     rcx, [rsp+68h+ClientToken]
0x18009905b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180099060  lea     rcx, [rsp+68h+ExistingTokenHandle]
0x180099065  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009906a  mov     eax, ebx
0x18009906c  jmp     short loc_18009908A
0x18009906e  lea     rcx, [rsp+68h+ClientToken]
0x180099073  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180099078  lea     rcx, [rsp+68h+ExistingTokenHandle]
0x18009907d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180099082  xor     eax, eax
0x180099084  jmp     short loc_18009908A
0x180099086  mov     eax, dword ptr [rsp+68h+ExistingTokenHandle]
0x18009908a  mov     rbx, [rsp+68h+arg_18]
0x180099092  add     rsp, 60h
0x180099096  pop     rdi
0x180099097  retn
```
