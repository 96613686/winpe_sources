# IsClientAllowed

- ea: `0x18001050c`
- end: `0x18001064b`
- name: `IsClientAllowed`
- size: `319`
- prototype: `__int64 __fastcall(char)`
- caller_count: `9`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013de0`
- `0x1800157e0`
- `0x1800158d0`
- `0x180015980`
- `0x180015aa0`
- `0x180015cc0`
- `0x180015e70`
- `0x180015f70`
- `0x180016190`

## callees

- `0x180007c90`
- `0x18000f034`
- `0x18001050c`
- `0x1800122a4`
- `0x180012304`
- `0x180012368`
- `0x18001374c`
- `0x180016b04`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010588`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010588`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010575`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010575`
- `RPCRT4!RpcImpersonateClient` at `0x180010530`
- `RPCRT4!RpcImpersonateClient` at `0x180010530`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001061d`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001061d`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x1800105e9`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x1800105e9`

## string_xrefs

- `0x18001053d`: `IsClientAllowed::RpcImpersonateClient`
- `0x180010597`: `IsClientAllowed::OpenThreadToken`

## pseudocode

```c
__int64 __fastcall IsClientAllowed(char a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  BOOL v5; // eax
  DusmSvc *v6; // rcx
  unsigned int v7; // eax
  const char *v9; // [rsp+28h] [rbp-38h]
  const char *v10; // [rsp+28h] [rbp-38h]
  const char *v11; // [rsp+28h] [rbp-38h]
  void *v12; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v13[8]; // [rsp+40h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v2 = RpcImpersonateClient(0);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x25,
    (unsigned int)"onecoreuap\\net\\dusm\\svc\\dusmrpc.cpp",
    (const char *)v2,
    (unsigned int)"IsClientAllowed::RpcImpersonateClient",
    v9);
  TokenHandle = 0;
  v3 = 1;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  v5 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
  wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
    retaddr,
    (void *)0x2C,
    (unsigned int)"onecoreuap\\net\\dusm\\svc\\dusmrpc.cpp",
    (const char *)v5,
    (bool)"IsClientAllowed::OpenThreadToken",
    v10);
  if ( (a1 & 1) == 0 || (v12 = TokenHandle, !(unsigned int)DusmSvc::IsClientAdminCheck(v6, &v12)) )
  {
    if ( (a1 & 2) == 0
      || (v13[0] = 0,
          v7 = CapabilityCheck(TokenHandle, L"networkDataPlanProvisioning", v13),
          wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
            retaddr,
            (void *)0x3E,
            (unsigned int)"onecoreuap\\net\\dusm\\svc\\dusmrpc.cpp",
            (const char *)v7,
            (int)"IsClientAllowed::CapabilityCheck",
            v11),
          !v13[0]) )
    {
      v3 = 0;
    }
  }
  RpcRevertToSelfEx(0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v3;
}

```

## disassembly

```asm
0x18001050c  mov     [rsp-8+arg_0], rbx
0x180010511  mov     [rsp-8+arg_8], rdi
0x180010516  push    rbp
0x180010517  mov     rbp, rsp
0x18001051a  sub     rsp, 60h
0x18001051e  mov     rax, cs:__security_cookie
0x180010525  xor     rax, rsp
0x180010528  mov     [rbp+var_10], rax
0x18001052c  mov     edi, ecx
0x18001052e  xor     ecx, ecx; BindingHandle
0x180010530  call    cs:__imp_RpcImpersonateClient
0x180010536  mov     r9d, eax; char *
0x180010539  mov     rcx, [rbp+8]; this
0x18001053d  lea     rax, aIsclientallowe_0; "IsClientAllowed::RpcImpersonateClient"
0x180010544  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x180010549  lea     r8, aOnecoreuapNetD_5; "onecoreuap\\net\\dusm\\svc\\dusmrpc.cpp"
0x180010550  mov     edx, 25h ; '%'; void *
0x180010555  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18001055a  mov     [rbp+TokenHandle], 0
0x180010562  mov     ebx, 1
0x180010567  mov     [rbp+var_2F], bl
0x18001056a  xor     edx, edx
0x18001056c  lea     rcx, [rbp+TokenHandle]
0x180010570  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180010575  call    cs:__imp_GetCurrentThread
0x18001057b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001057f  mov     r8d, ebx; OpenAsSelf
0x180010582  lea     edx, [rbx+7]; DesiredAccess
0x180010585  mov     rcx, rax; ThreadHandle
0x180010588  call    cs:__imp_OpenThreadToken
0x18001058e  test    eax, eax
0x180010590  setnz   al
0x180010593  mov     rcx, [rbp+8]; this
0x180010597  lea     rdx, aIsclientallowe_1; "IsClientAllowed::OpenThreadToken"
0x18001059e  mov     qword ptr [rsp+60h+var_40], rdx; bool
0x1800105a3  movzx   r9d, al; char *
0x1800105a7  lea     r8, aOnecoreuapNetD_5; "onecoreuap\\net\\dusm\\svc\\dusmrpc.cpp"
0x1800105ae  lea     edx, [rbx+2Bh]; void *
0x1800105b1  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x1800105b6  test    bl, dil
0x1800105b9  jz      short loc_1800105D0
0x1800105bb  mov     rax, [rbp+TokenHandle]
0x1800105bf  mov     [rbp+var_28], rax
0x1800105c3  lea     rdx, [rbp+var_28]; void **
0x1800105c7  call    ?IsClientAdminCheck@DusmSvc@@AEAAHAEBQEAX@Z; DusmSvc::IsClientAdminCheck(void * const &)
0x1800105cc  test    eax, eax
0x1800105ce  jnz     short loc_18001061B
0x1800105d0  test    dil, 2
0x1800105d4  jz      short loc_180010619
0x1800105d6  mov     [rbp+var_20], 0
0x1800105da  lea     r8, [rbp+var_20]
0x1800105de  lea     rdx, aNetworkdatapla; "networkDataPlanProvisioning"
0x1800105e5  mov     rcx, [rbp+TokenHandle]
0x1800105e9  call    cs:__imp_CapabilityCheck
0x1800105ef  mov     r9d, eax; char *
0x1800105f2  mov     rcx, [rbp+8]; this
0x1800105f6  lea     rax, aIsclientallowe; "IsClientAllowed::CapabilityCheck"
0x1800105fd  mov     qword ptr [rsp+60h+var_40], rax; int
0x180010602  lea     r8, aOnecoreuapNetD_5; "onecoreuap\\net\\dusm\\svc\\dusmrpc.cpp"
0x180010609  mov     edx, 3Eh ; '>'; void *
0x18001060e  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180010613  cmp     [rbp+var_20], 0
0x180010617  jnz     short loc_18001061B
0x180010619  xor     ebx, ebx
0x18001061b  xor     ecx, ecx; BindingHandle
0x18001061d  call    cs:__imp_RpcRevertToSelfEx
0x180010623  nop
0x180010624  lea     rcx, [rbp+TokenHandle]
0x180010628  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001062d  mov     eax, ebx
0x18001062f  mov     rcx, [rbp+var_10]
0x180010633  xor     rcx, rsp; StackCookie
0x180010636  call    __security_check_cookie
0x18001063b  mov     rbx, [rsp+60h+arg_0]
0x180010640  mov     rdi, [rsp+60h+arg_8]
0x180010645  add     rsp, 60h
0x180010649  pop     rbp
0x18001064a  retn
```
