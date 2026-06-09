# NlValidateAccountSidKerberos(ulong,_SID *,int *)

- ea: `0x18005db8c`
- end: `0x18005de02`
- name: `?NlValidateAccountSidKerberos@@YAJKPEAU_SID@@PEAH@Z`
- size: `630`
- prototype: `int(unsigned int, struct _SID *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180064d80`

## callees

- `0x180007518`
- `0x180059ccc`
- `0x18005db8c`
- `0x18005de08`
- `0x18005e800`
- `0x18005e83c`
- `0x18008a5c0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18005dbe5`
- `RPCRT4!RpcImpersonateClient` at `0x18005dbe5`
- `RPCRT4!RpcRevertToSelf` at `0x18005dc6d`
- `RPCRT4!RpcRevertToSelf` at `0x18005ddad`
- `RPCRT4!RpcRevertToSelf` at `0x18005dc6d`
- `RPCRT4!RpcRevertToSelf` at `0x18005ddad`
- `RPCRT4!I_RpcMapWin32Status` at `0x18005dbf3`
- `RPCRT4!I_RpcMapWin32Status` at `0x18005dbf3`
- `ntdll!NtOpenThreadToken` at `0x18005dc3e`
- `ntdll!NtOpenThreadToken` at `0x18005dc3e`
- `ntdll!NtQueryInformationToken` at `0x18005dc9f`
- `ntdll!NtQueryInformationToken` at `0x18005dd22`
- `ntdll!NtQueryInformationToken` at `0x18005dc9f`
- `ntdll!NtQueryInformationToken` at `0x18005dd22`
- `ntdll!RtlEqualSid` at `0x18005dd80`
- `ntdll!RtlEqualSid` at `0x18005dd80`
- `ntdll!RtlValidSid` at `0x18005dd57`
- `ntdll!RtlValidSid` at `0x18005dd57`

## string_xrefs

- `0x18005dc53`: `NlValidateAccountSidKerberos: NtOpenThreadToken failed %lx\n`
- `0x18005dd38`: `NlValidateAccountSidKerberos: NtQueryInformationToken failed %lx\n`
- `0x18005dc08`: `NlValidateAccountSidKerberos: RpcImpersonateClient failed %lx\n`
- `0x18005dcb7`: `NlValidateAccountSidKerberos: NtQueryInformationToken for token size failed %lx\n`
- `0x18005dcea`: `NlValidateAccountSidKerberos: OOM for allocating TokenUserBuffer\n`
- `0x18005ddbd`: `NlValidateAccountSidKerberos: Invalid SID in token\n`

## pseudocode

```c
int __fastcall NlValidateAccountSidKerberos(unsigned int a1, struct _SID *a2, int *a3)
{
  RPC_STATUS v7; // eax
  int v8; // eax
  int v9; // ebx
  int v10; // edi
  NTSTATUS v11; // eax
  unsigned int v12; // eax
  void *v13; // rax
  unsigned __int8 **v14; // rbx
  NTSTATUS v15; // eax
  NTSTATUS v16; // r14d
  unsigned __int8 *v17; // rbx
  __int64 v18; // rcx
  int v19; // r14d
  ULONG ReturnLength; // [rsp+30h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-18h] BYREF
  PVOID TokenInformation[2]; // [rsp+40h] [rbp-10h] BYREF
  ULONG TokenInformationLength; // [rsp+98h] [rbp+48h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_NetlogonHandleLeak>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_NetlogonHandleLeak>::GetImpl'::`2'::impl) )
    return NlValidateAccountSidKerberosOld(a1, a2, a3);
  if ( !a3 || !a2 )
    return -1073741811;
  v7 = RpcImpersonateClient(0);
  v8 = I_RpcMapWin32Status(v7);
  v9 = v8;
  if ( v8 < 0 )
  {
    NlPrintRoutine(0x100u, L"NlValidateAccountSidKerberos: RpcImpersonateClient failed %lx\n", (unsigned int)v8);
    return v9;
  }
  v10 = 1;
  TokenHandle = 0;
  v11 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  v9 = v11;
  if ( v11 < 0 )
  {
    NlPrintRoutine(0x100u, L"NlValidateAccountSidKerberos: NtOpenThreadToken failed %lx\n", (unsigned int)v11);
LABEL_10:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    RpcRevertToSelf();
    return v9;
  }
  TokenInformation[0] = 0;
  TokenInformationLength = 0;
  v12 = NtQueryInformationToken(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  v9 = v12;
  if ( v12 != -1073741789 )
  {
    NlPrintRoutine(0x100u, L"NlValidateAccountSidKerberos: NtQueryInformationToken for token size failed %lx\n", v12);
LABEL_24:
    wistd::unique_ptr<_TOKEN_USER,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::reset(
      TokenInformation,
      0);
    goto LABEL_10;
  }
  v13 = MIDL_user_allocate(TokenInformationLength);
  wistd::unique_ptr<_TOKEN_USER,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::reset(
    TokenInformation,
    v13);
  v14 = (unsigned __int8 **)TokenInformation[0];
  if ( !TokenInformation[0] )
  {
    NlPrintRoutine(0x100u, L"NlValidateAccountSidKerberos: OOM for allocating TokenUserBuffer\n");
    v9 = -1073741670;
    goto LABEL_24;
  }
  ReturnLength = 0;
  v15 = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation[0], TokenInformationLength, &ReturnLength);
  v16 = v15;
  if ( v15 < 0 )
  {
    NlPrintRoutine(0x100u, L"NlValidateAccountSidKerberos: NtQueryInformationToken failed %lx\n", (unsigned int)v15);
    v9 = v16;
    goto LABEL_24;
  }
  v17 = *v14;
  if ( !RtlValidSid(v17) || (v18 = v17[1], !(_BYTE)v18) )
  {
    NlPrintRoutine(0x100u, L"NlValidateAccountSidKerberos: Invalid SID in token\n");
    v9 = -1073741595;
    goto LABEL_24;
  }
  v19 = *(_DWORD *)&v17[4 * v18 + 4];
  v17[1] = v18 - 1;
  if ( !RtlEqualSid(a2, v17) || v19 != a1 )
    v10 = 0;
  *a3 = v10;
  wistd::unique_ptr<_TOKEN_USER,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::reset(
    TokenInformation,
    0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  RpcRevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x18005db8c  mov     [rsp-28h+arg_0], rbx
0x18005db91  mov     [rsp-28h+arg_8], rsi
0x18005db96  push    rbp
0x18005db97  push    rdi
0x18005db98  push    r12
0x18005db9a  push    r14
0x18005db9c  push    r15
0x18005db9e  mov     rbp, rsp
0x18005dba1  sub     rsp, 50h
0x18005dba5  mov     rsi, r8
0x18005dba8  mov     r15, rdx
0x18005dbab  mov     r12d, ecx
0x18005dbae  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_NetlogonHandleLeak@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_NetlogonHandleLeak@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_NetlogonHandleLeak> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_NetlogonHandleLeak>::GetImpl(void)'::`2'::impl
0x18005dbb5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_NetlogonHandleLeak@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_NetlogonHandleLeak>::__private_IsEnabled(void)
0x18005dbba  test    al, al
0x18005dbbc  jnz     short loc_18005DBD1
0x18005dbbe  mov     r8, rsi; int *
0x18005dbc1  mov     rdx, r15; struct _SID *
0x18005dbc4  mov     ecx, r12d; unsigned int
0x18005dbc7  call    ?NlValidateAccountSidKerberosOld@@YAJKPEAU_SID@@PEAH@Z; NlValidateAccountSidKerberosOld(ulong,_SID *,int *)
0x18005dbcc  jmp     loc_18005DDE8
0x18005dbd1  test    rsi, rsi
0x18005dbd4  jz      loc_18005DDE3
0x18005dbda  test    r15, r15
0x18005dbdd  jz      loc_18005DDE3
0x18005dbe3  xor     ecx, ecx; BindingHandle
0x18005dbe5  call    cs:__imp_RpcImpersonateClient
0x18005dbec  nop     dword ptr [rax+rax+00h]
0x18005dbf1  mov     ecx, eax; Status
0x18005dbf3  call    cs:__imp_I_RpcMapWin32Status
0x18005dbfa  nop     dword ptr [rax+rax+00h]
0x18005dbff  mov     ebx, eax
0x18005dc01  test    eax, eax
0x18005dc03  jns     short loc_18005DC20
0x18005dc05  mov     r8d, eax
0x18005dc08  lea     rdx, aNlvalidateacco; "NlValidateAccountSidKerberos: RpcImpers"...
0x18005dc0f  mov     ecx, 100h; unsigned int
0x18005dc14  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005dc19  mov     eax, ebx
0x18005dc1b  jmp     loc_18005DDE8
0x18005dc20  mov     edi, 1
0x18005dc25  mov     [rbp+TokenHandle], 0
0x18005dc2d  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18005dc31  mov     r8b, dil; OpenAsSelf
0x18005dc34  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18005dc3b  lea     edx, [rdi+7]; DesiredAccess
0x18005dc3e  call    cs:__imp_NtOpenThreadToken
0x18005dc45  nop     dword ptr [rax+rax+00h]
0x18005dc4a  mov     ebx, eax
0x18005dc4c  test    eax, eax
0x18005dc4e  jns     short loc_18005DC7B
0x18005dc50  mov     r8d, eax
0x18005dc53  lea     rdx, aNlvalidateacco_1; "NlValidateAccountSidKerberos: NtOpenThr"...
0x18005dc5a  mov     ecx, 100h; unsigned int
0x18005dc5f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005dc64  lea     rcx, [rbp+TokenHandle]
0x18005dc68  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005dc6d  call    cs:__imp_RpcRevertToSelf
0x18005dc74  nop     dword ptr [rax+rax+00h]
0x18005dc79  jmp     short loc_18005DC19
0x18005dc7b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18005dc7f  lea     rax, [rbp+TokenInformationLength]
0x18005dc83  xor     r9d, r9d; TokenInformationLength
0x18005dc86  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18005dc8b  xor     r8d, r8d; TokenInformation
0x18005dc8e  mov     [rbp+TokenInformation], 0
0x18005dc96  mov     edx, edi; TokenInformationClass
0x18005dc98  mov     [rbp+TokenInformationLength], 0
0x18005dc9f  call    cs:__imp_NtQueryInformationToken
0x18005dca6  nop     dword ptr [rax+rax+00h]
0x18005dcab  mov     ebx, eax
0x18005dcad  cmp     eax, 0C0000023h
0x18005dcb2  jz      short loc_18005DCCD
0x18005dcb4  mov     r8d, eax
0x18005dcb7  lea     rdx, aNlvalidateacco_0; "NlValidateAccountSidKerberos: NtQueryIn"...
0x18005dcbe  mov     ecx, 100h; unsigned int
0x18005dcc3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005dcc8  jmp     loc_18005DDD3
0x18005dccd  mov     ecx, [rbp+TokenInformationLength]; size
0x18005dcd0  call    MIDL_user_allocate
0x18005dcd5  mov     rdx, rax
0x18005dcd8  lea     rcx, [rbp+TokenInformation]
0x18005dcdc  call    ?reset@?$unique_ptr@U_TOKEN_USER@@U?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_TOKEN_USER@@@Z; wistd::unique_ptr<_TOKEN_USER,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::reset(_TOKEN_USER *)
0x18005dce1  mov     rbx, [rbp+TokenInformation]
0x18005dce5  test    rbx, rbx
0x18005dce8  jnz     short loc_18005DD05
0x18005dcea  lea     rdx, aNlvalidateacco_4; "NlValidateAccountSidKerberos: OOM for a"...
0x18005dcf1  mov     ecx, 100h; unsigned int
0x18005dcf6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005dcfb  mov     ebx, 0C000009Ah
0x18005dd00  jmp     loc_18005DDD3
0x18005dd05  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18005dd09  lea     rax, [rbp+var_20]
0x18005dd0d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18005dd11  mov     r8, rbx; TokenInformation
0x18005dd14  mov     edx, edi; TokenInformationClass
0x18005dd16  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18005dd1b  mov     [rbp+var_20], 0
0x18005dd22  call    cs:__imp_NtQueryInformationToken
0x18005dd29  nop     dword ptr [rax+rax+00h]
0x18005dd2e  mov     r14d, eax
0x18005dd31  test    eax, eax
0x18005dd33  jns     short loc_18005DD51
0x18005dd35  mov     r8d, eax
0x18005dd38  lea     rdx, aNlvalidateacco_2; "NlValidateAccountSidKerberos: NtQueryIn"...
0x18005dd3f  mov     ecx, 100h; unsigned int
0x18005dd44  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005dd49  mov     ebx, r14d
0x18005dd4c  jmp     loc_18005DDD3
0x18005dd51  mov     rbx, [rbx]
0x18005dd54  mov     rcx, rbx; Sid
0x18005dd57  call    cs:__imp_RtlValidSid
0x18005dd5e  nop     dword ptr [rax+rax+00h]
0x18005dd63  test    al, al
0x18005dd65  jz      short loc_18005DDBD
0x18005dd67  movzx   ecx, byte ptr [rbx+1]
0x18005dd6b  test    cl, cl
0x18005dd6d  jz      short loc_18005DDBD
0x18005dd6f  mov     r14d, [rbx+rcx*4+4]
0x18005dd74  mov     rdx, rbx; Sid2
0x18005dd77  sub     cl, dil
0x18005dd7a  mov     [rbx+1], cl
0x18005dd7d  mov     rcx, r15; Sid1
0x18005dd80  call    cs:__imp_RtlEqualSid
0x18005dd87  nop     dword ptr [rax+rax+00h]
0x18005dd8c  test    al, al
0x18005dd8e  jz      short loc_18005DD95
0x18005dd90  cmp     r14d, r12d
0x18005dd93  jz      short loc_18005DD97
0x18005dd95  xor     edi, edi
0x18005dd97  xor     edx, edx
0x18005dd99  mov     [rsi], edi
0x18005dd9b  lea     rcx, [rbp+TokenInformation]
0x18005dd9f  call    ?reset@?$unique_ptr@U_TOKEN_USER@@U?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_TOKEN_USER@@@Z; wistd::unique_ptr<_TOKEN_USER,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::reset(_TOKEN_USER *)
0x18005dda4  lea     rcx, [rbp+TokenHandle]
0x18005dda8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005ddad  call    cs:__imp_RpcRevertToSelf
0x18005ddb4  nop     dword ptr [rax+rax+00h]
0x18005ddb9  xor     eax, eax
0x18005ddbb  jmp     short loc_18005DDE8
0x18005ddbd  lea     rdx, aNlvalidateacco_3; "NlValidateAccountSidKerberos: Invalid S"...
0x18005ddc4  mov     ecx, 100h; unsigned int
0x18005ddc9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005ddce  mov     ebx, 0C00000E5h
0x18005ddd3  xor     edx, edx
0x18005ddd5  lea     rcx, [rbp+TokenInformation]
0x18005ddd9  call    ?reset@?$unique_ptr@U_TOKEN_USER@@U?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_TOKEN_USER@@@Z; wistd::unique_ptr<_TOKEN_USER,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::reset(_TOKEN_USER *)
0x18005ddde  jmp     loc_18005DC64
0x18005dde3  mov     eax, 0C000000Dh
0x18005dde8  lea     r11, [rsp+50h+var_s0]
0x18005dded  mov     rbx, [r11+30h]
0x18005ddf1  mov     rsi, [r11+38h]
0x18005ddf5  mov     rsp, r11
0x18005ddf8  pop     r15
0x18005ddfa  pop     r14
0x18005ddfc  pop     r12
0x18005ddfe  pop     rdi
0x18005ddff  pop     rbp
0x18005de00  retn
```
