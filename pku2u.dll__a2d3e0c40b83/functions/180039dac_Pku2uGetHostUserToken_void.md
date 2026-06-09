# Pku2uGetHostUserToken(void * *)

- ea: `0x180039dac`
- end: `0x180039f19`
- name: `?Pku2uGetHostUserToken@@YAJPEAPEAX@Z`
- size: `365`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180039908`

## callees

- `0x18001f750`
- `0x18001f7d4`
- `0x1800221e4`
- `0x1800264a4`
- `0x180038a0c`
- `0x180038a50`
- `0x180039dac`
- `0x180044d98`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039eb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039eb4`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180039e15`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180039e15`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180039ed6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180039ed6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180039df6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180039df6`

## string_xrefs

- `0x180039e2d`: `onecore\ds\security\protocols\pku2u\token.cxx`
- `0x180039e7f`: `onecore\ds\security\protocols\pku2u\token.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Pku2uGetHostUserToken(void **a1)
{
  unsigned int v2; // ebx
  __int64 v3; // r9
  __int64 v4; // rdx
  _QWORD *v5; // rbx
  int v6; // eax
  int v7; // eax
  __int64 v8; // r9
  __int64 v9; // rdx
  HANDLE v10; // rbx
  int v11; // eax
  HANDLE v12; // rax
  int v14[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  int v16; // [rsp+58h] [rbp+28h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp+30h] BYREF
  _QWORD *v18; // [rsp+68h] [rbp+38h] BYREF

  v18 = 0;
  v16 = 0;
  if ( !(unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    v2 = -2147467263;
    v3 = 2147500033LL;
    v4 = 921;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
      (const char *)v3,
      v14[0]);
    goto LABEL_20;
  }
  v5 = v18;
  if ( v18 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v14);
    UMgrFreeSessionUsers(v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
  }
  v18 = 0;
  v6 = UMgrEnumerateSessionUsers(&v16, &v18);
  v2 = v6;
  if ( v6 < 0 )
  {
    v3 = (unsigned int)v6;
    v4 = 922;
    goto LABEL_7;
  }
  v7 = v16;
  if ( v16 != 1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v7 = v16;
  }
  if ( !v7 )
  {
    v2 = -2147418113;
    v3 = 2147549183LL;
    v4 = 924;
    goto LABEL_7;
  }
  hObject = 0;
  if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    v10 = hObject;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v14);
      CloseHandle(v10);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
    }
    hObject = 0;
    v11 = UMgrQueryUserToken(*v18, &hObject);
    v2 = v11;
    if ( v11 >= 0 )
    {
      v12 = hObject;
      hObject = 0;
      *a1 = v12;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      v2 = 0;
      goto LABEL_20;
    }
    v8 = (unsigned int)v11;
    v9 = 928;
  }
  else
  {
    v2 = -2147467263;
    v8 = 2147500033LL;
    v9 = 927;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\token.cxx",
    (const char *)v8,
    v14[0]);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
LABEL_20:
  wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v18);
  return v2;
}

```

## disassembly

```asm
0x180039dac  push    rbp
0x180039dae  push    rbx
0x180039daf  push    rdi
0x180039db0  mov     rbp, rsp
0x180039db3  sub     rsp, 30h
0x180039db7  mov     rdi, rcx
0x180039dba  mov     [rbp+arg_18], 0
0x180039dc2  mov     [rbp+arg_8], 0
0x180039dc9  call    IsUMgrEnumerateSessionUsersPresent
0x180039dce  test    al, al
0x180039dd0  jnz     short loc_180039DE1
0x180039dd2  mov     ebx, 80004001h
0x180039dd7  mov     r9d, ebx
0x180039dda  mov     edx, 399h
0x180039ddf  jmp     short loc_180039E29
0x180039de1  mov     rbx, [rbp+arg_18]
0x180039de5  test    rbx, rbx
0x180039de8  jz      short loc_180039E05
0x180039dea  lea     rcx, [rbp+var_10]; this
0x180039dee  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180039df3  mov     rcx, rbx
0x180039df6  call    cs:__imp_UMgrFreeSessionUsers
0x180039dfc  lea     rcx, [rbp+var_10]; this
0x180039e00  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180039e05  mov     [rbp+arg_18], 0
0x180039e0d  lea     rdx, [rbp+arg_18]
0x180039e11  lea     rcx, [rbp+arg_8]
0x180039e15  call    cs:__imp_UMgrEnumerateSessionUsers
0x180039e1b  mov     ebx, eax
0x180039e1d  test    eax, eax
0x180039e1f  jns     short loc_180039E3E
0x180039e21  mov     r9d, eax; char *
0x180039e24  mov     edx, 39Ah; void *
0x180039e29  mov     rcx, [rbp+18h]; this
0x180039e2d  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\protocols\\pku2u"...
0x180039e34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039e39  jmp     loc_180039F06
0x180039e3e  mov     eax, [rbp+arg_8]
0x180039e41  cmp     eax, 1
0x180039e44  jz      short loc_180039E4E
0x180039e46  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180039e4b  mov     eax, [rbp+arg_8]
0x180039e4e  test    eax, eax
0x180039e50  jnz     short loc_180039E61
0x180039e52  mov     ebx, 8000FFFFh
0x180039e57  mov     r9d, ebx
0x180039e5a  mov     edx, 39Ch
0x180039e5f  jmp     short loc_180039E29
0x180039e61  mov     [rbp+hObject], 0
0x180039e69  call    IsUMgrEnumerateSessionUsersPresent
0x180039e6e  test    al, al
0x180039e70  jnz     short loc_180039E9A
0x180039e72  mov     ebx, 80004001h
0x180039e77  mov     r9d, ebx; char *
0x180039e7a  mov     edx, 39Fh; void *
0x180039e7f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\protocols\\pku2u"...
0x180039e86  mov     rcx, [rbp+18h]; this
0x180039e8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039e8f  lea     rcx, [rbp+hObject]
0x180039e93  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180039e98  jmp     short loc_180039F06
0x180039e9a  mov     rbx, [rbp+hObject]
0x180039e9e  lea     rax, [rbx-1]
0x180039ea2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180039ea6  ja      short loc_180039EC3
0x180039ea8  lea     rcx, [rbp+var_10]; this
0x180039eac  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180039eb1  mov     rcx, rbx; hObject
0x180039eb4  call    cs:__imp_CloseHandle
0x180039eba  lea     rcx, [rbp+var_10]; this
0x180039ebe  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180039ec3  mov     [rbp+hObject], 0
0x180039ecb  lea     rdx, [rbp+hObject]
0x180039ecf  mov     rcx, [rbp+arg_18]
0x180039ed3  mov     rcx, [rcx]
0x180039ed6  call    cs:__imp_UMgrQueryUserToken
0x180039edc  mov     ebx, eax
0x180039ede  test    eax, eax
0x180039ee0  jns     short loc_180039EEC
0x180039ee2  mov     r9d, eax
0x180039ee5  mov     edx, 3A0h
0x180039eea  jmp     short loc_180039E7F
0x180039eec  mov     rax, [rbp+hObject]
0x180039ef0  mov     [rbp+hObject], 0
0x180039ef8  mov     [rdi], rax
0x180039efb  lea     rcx, [rbp+hObject]
0x180039eff  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180039f04  xor     ebx, ebx
0x180039f06  lea     rcx, [rbp+arg_18]
0x180039f0a  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x180039f0f  mov     eax, ebx
0x180039f11  add     rsp, 30h
0x180039f15  pop     rdi
0x180039f16  pop     rbx
0x180039f17  pop     rbp
0x180039f18  retn
```
