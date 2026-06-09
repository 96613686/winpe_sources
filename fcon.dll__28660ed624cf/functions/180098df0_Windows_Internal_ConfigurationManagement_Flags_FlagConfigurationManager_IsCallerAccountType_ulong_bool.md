# Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::IsCallerAccountType(ulong,bool &)

- ea: `0x180098df0`
- end: `0x180098f4d`
- name: `?IsCallerAccountType@FlagConfigurationManager@Flags@ConfigurationManagement@Internal@Windows@@CAJKAEA_N@Z`
- size: `349`
- prototype: `static int(unsigned int, bool *)`
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
- `0x180098df0`
- `0x1800993d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098e7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098e7d`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180098e73`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180098e73`

## string_xrefs

- `0x180098e21`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`
- `0x180098ef1`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\flagconfigurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::IsCallerAccountType(
        __int64 a1,
        bool *a2)
{
  signed int CurrentUserToken; // eax
  unsigned int v4; // ebx
  signed int LastError; // eax
  unsigned int v7; // ebx
  signed int IsLoggedInUserMatchSID; // eax
  unsigned int v9; // ebx
  unsigned int v10; // [rsp+20h] [rbp-58h]
  int v11; // [rsp+20h] [rbp-58h]
  unsigned int v12; // [rsp+28h] [rbp-50h]
  unsigned int v13; // [rsp+30h] [rbp-48h]
  unsigned int v14; // [rsp+38h] [rbp-40h]
  unsigned int v15; // [rsp+40h] [rbp-38h]
  unsigned int v16; // [rsp+48h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HANDLE ExistingTokenHandle; // [rsp+88h] [rbp+10h] BYREF
  HANDLE ClientToken; // [rsp+90h] [rbp+18h] BYREF
  void *DuplicateTokenHandle; // [rsp+98h] [rbp+20h] BYREF

  *a2 = 0;
  ExistingTokenHandle = 0;
  CurrentUserToken = Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::GetCurrentUserToken(
                       a1,
                       (__int64)&ExistingTokenHandle);
  v4 = CurrentUserToken;
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
                                 1u,
                                 0x12u,
                                 0,
                                 v10,
                                 v12,
                                 v13,
                                 v14,
                                 v15,
                                 v16,
                                 a2);
      v9 = IsLoggedInUserMatchSID;
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
          (void *)0x2ED,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
          (const char *)(unsigned int)IsLoggedInUserMatchSID,
          v11);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ClientToken);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
        return v9;
      }
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ClientToken);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D6,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\flagconfigurationmanager.cpp",
      (const char *)(unsigned int)CurrentUserToken,
      v10);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
    return v4;
  }
}

```

## disassembly

```asm
0x180098df0  mov     rax, rsp
0x180098df3  mov     [rax+8], ecx
0x180098df6  push    rbx
0x180098df7  push    rdi
0x180098df8  sub     rsp, 68h
0x180098dfc  mov     rdi, rdx
0x180098dff  mov     byte ptr [rdx], 0
0x180098e02  mov     qword ptr [rax+10h], 0
0x180098e0a  lea     rdx, [rax+10h]
0x180098e0e  call    ?GetCurrentUserToken@FlagConfigurationManager@Flags@ConfigurationManagement@Internal@Windows@@CAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::GetCurrentUserToken(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x180098e13  mov     ebx, eax
0x180098e15  test    eax, eax
0x180098e17  jns     short loc_180098E46
0x180098e19  mov     rcx, [rsp+78h]; this
0x180098e1e  mov     r9d, eax; char *
0x180098e21  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x180098e28  mov     edx, 2D6h; void *
0x180098e2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098e32  lea     rcx, [rsp+78h+ExistingTokenHandle]
0x180098e3a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180098e3f  mov     eax, ebx
0x180098e41  jmp     loc_180098F45
0x180098e46  mov     [rsp+78h+ClientToken], 0
0x180098e52  mov     [rsp+78h+DuplicateTokenHandle], 0
0x180098e5e  lea     r8, [rsp+78h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180098e66  mov     edx, 2; ImpersonationLevel
0x180098e6b  mov     rcx, [rsp+78h+ExistingTokenHandle]; ExistingTokenHandle
0x180098e73  call    cs:__imp_DuplicateToken
0x180098e79  test    eax, eax
0x180098e7b  jnz     short loc_180098EB3
0x180098e7d  call    cs:__imp_GetLastError
0x180098e83  mov     ebx, eax
0x180098e85  test    eax, eax
0x180098e87  jle     short loc_180098E92
0x180098e89  movzx   ebx, ax
0x180098e8c  or      ebx, 80070000h
0x180098e92  lea     rcx, [rsp+78h+ClientToken]
0x180098e9a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180098e9f  lea     rcx, [rsp+78h+ExistingTokenHandle]
0x180098ea7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180098eac  mov     eax, ebx
0x180098eae  jmp     loc_180098F45
0x180098eb3  mov     rdx, [rsp+78h+DuplicateTokenHandle]
0x180098ebb  lea     rcx, [rsp+78h+ClientToken]
0x180098ec3  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180098ec8  mov     [rsp+78h+var_28], rdi; bool *
0x180098ecd  xor     r9d, r9d; unsigned int
0x180098ed0  lea     r8d, [r9+12h]; unsigned int
0x180098ed4  mov     dl, 1; unsigned __int8
0x180098ed6  mov     rcx, [rsp+78h+ClientToken]; ClientToken
0x180098ede  call    ?IsLoggedInUserMatchSID@FlagConfigurationManager@Flags@ConfigurationManagement@Internal@Windows@@CAJPEAXEKKKKKKKKAEA_N@Z; Windows::Internal::ConfigurationManagement::Flags::FlagConfigurationManager::IsLoggedInUserMatchSID(void *,uchar,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,bool &)
0x180098ee3  mov     ebx, eax
0x180098ee5  test    eax, eax
0x180098ee7  jns     short loc_180098F20
0x180098ee9  mov     rcx, [rsp+78h]; this
0x180098eee  mov     r9d, eax; char *
0x180098ef1  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\featuremanage"...
0x180098ef8  mov     edx, 2EDh; void *
0x180098efd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098f02  lea     rcx, [rsp+78h+ClientToken]
0x180098f0a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180098f0f  lea     rcx, [rsp+78h+ExistingTokenHandle]
0x180098f17  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180098f1c  mov     eax, ebx
0x180098f1e  jmp     short loc_180098F45
0x180098f20  lea     rcx, [rsp+78h+ClientToken]
0x180098f28  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180098f2d  lea     rcx, [rsp+78h+ExistingTokenHandle]
0x180098f35  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180098f3a  xor     eax, eax
0x180098f3c  jmp     short loc_180098F45
0x180098f3e  mov     eax, [rsp+78h+arg_0]
0x180098f45  add     rsp, 68h
0x180098f49  pop     rdi
0x180098f4a  pop     rbx
0x180098f4b  retn
```
