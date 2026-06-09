# DAS::DevnodeManagment::DevnodeManager::UserContextToSidString(unsigned __int64,ushort * *)

- ea: `0x180029884`
- end: `0x18002998e`
- name: `?UserContextToSidString@DevnodeManager@DevnodeManagment@DAS@@SAJ_KPEAPEAG@Z`
- size: `266`
- prototype: `static int(unsigned __int64, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003997c`
- `0x180039cec`

## callees

- `0x180019cbc`
- `0x180029884`
- `0x18002a948`
- `0x18002aa34`
- `0x18003c5ec`
- `0x18004e1c0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800298d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800298d7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180029935`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180029935`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002989f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002989f`

## string_xrefs

- `0x1800298b0`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x180029905`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x180029944`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::DevnodeManager::UserContextToSidString(__int64 a1, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int token_information; // eax
  void *v6; // rbx
  const char *v7; // r9
  unsigned int LastError; // edi
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HANDLE hObject; // [rsp+40h] [rbp+18h] BYREF
  void *Block; // [rsp+48h] [rbp+20h] BYREF

  hObject = 0;
  v3 = UMgrQueryUserToken(a1, &hObject);
  v4 = v3;
  if ( v3 >= 0 )
  {
    Block = 0;
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, (__int64)hObject);
    v4 = token_information;
    if ( token_information >= 0 )
    {
      v6 = Block;
      if ( ConvertSidToStringSidW(*(PSID *)Block, a2) )
      {
        if ( v6 )
          operator delete(v6);
        v4 = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x103,
                      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
                      v7);
        if ( v6 )
          operator delete(v6);
        v4 = LastError;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x102,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
        (const char *)(unsigned int)token_information,
        v10);
      if ( Block )
        operator delete(Block);
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
      (const char *)(unsigned int)v3,
      v10);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
  }
  return v4;
}

```

## disassembly

```asm
0x180029884  mov     [rsp+arg_0], rbx
0x180029889  push    rdi; int
0x18002988a  sub     rsp, 20h
0x18002988e  mov     rdi, rdx
0x180029891  mov     [rsp+28h+hObject], 0
0x18002989a  lea     rdx, [rsp+28h+hObject]
0x18002989f  call    cs:__imp_UMgrQueryUserToken
0x1800298a5  mov     ebx, eax
0x1800298a7  test    eax, eax
0x1800298a9  jns     short loc_1800298E2
0x1800298ab  mov     rcx, [rsp+28h]; this
0x1800298b0  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x1800298b7  mov     r9d, eax; char *
0x1800298ba  mov     edx, 100h; void *
0x1800298bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800298c4  mov     rcx, [rsp+28h+hObject]; hObject
0x1800298c9  lea     rdx, [rcx-1]
0x1800298cd  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800298d1  ja      loc_180029981
0x1800298d7  call    cs:__imp_CloseHandle
0x1800298dd  jmp     loc_180029981
0x1800298e2  mov     rdx, [rsp+28h+hObject]
0x1800298e7  lea     rcx, [rsp+28h+Block]
0x1800298ec  mov     [rsp+28h+Block], 0
0x1800298f5  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800298fa  mov     ebx, eax
0x1800298fc  test    eax, eax
0x1800298fe  jns     short loc_18002992A
0x180029900  mov     rcx, [rsp+28h]; this
0x180029905  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x18002990c  mov     r9d, eax; char *
0x18002990f  mov     edx, 102h; void *
0x180029914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029919  mov     rcx, [rsp+28h+Block]; Block
0x18002991e  test    rcx, rcx
0x180029921  jz      short loc_180029977
0x180029923  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029928  jmp     short loc_180029977
0x18002992a  mov     rbx, [rsp+28h+Block]
0x18002992f  mov     rdx, rdi; StringSid
0x180029932  mov     rcx, [rbx]; Sid
0x180029935  call    cs:__imp_ConvertSidToStringSidW
0x18002993b  test    eax, eax
0x18002993d  jnz     short loc_180029968
0x18002993f  mov     rcx, [rsp+28h]; this
0x180029944  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x18002994b  mov     edx, 103h; void *
0x180029950  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180029955  mov     edi, eax
0x180029957  test    rbx, rbx
0x18002995a  jz      short loc_180029964
0x18002995c  mov     rcx, rbx; Block
0x18002995f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029964  mov     ebx, edi
0x180029966  jmp     short loc_180029977
0x180029968  test    rbx, rbx
0x18002996b  jz      short loc_180029975
0x18002996d  mov     rcx, rbx; Block
0x180029970  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029975  xor     ebx, ebx
0x180029977  lea     rcx, [rsp+28h+hObject]
0x18002997c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180029981  mov     eax, ebx
0x180029983  mov     rbx, [rsp+28h+arg_0]
0x180029988  add     rsp, 20h
0x18002998c  pop     rdi
0x18002998d  retn
```
