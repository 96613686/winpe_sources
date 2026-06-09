# NlValidateAccountSidKerberos(ulong,_SID *,int *)

- ea: `0x180059aec`
- end: `0x180059cf6`
- name: `?NlValidateAccountSidKerberos@@YAJKPEAU_SID@@PEAH@Z`
- size: `522`
- prototype: `int(unsigned int, struct _SID *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180060820`

## callees

- `0x180007278`
- `0x180055f74`
- `0x180059aec`
- `0x180059cfc`
- `0x18005a63c`
- `0x1800844d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180059c56`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180059ca3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180059cd0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180059c56`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180059ca3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180059cd0`
- `RPCRT4!RpcImpersonateClient` at `0x180059b43`
- `RPCRT4!RpcImpersonateClient` at `0x180059b43`
- `RPCRT4!RpcRevertToSelf` at `0x180059bb5`
- `RPCRT4!RpcRevertToSelf` at `0x180059cb2`
- `RPCRT4!RpcRevertToSelf` at `0x180059bb5`
- `RPCRT4!RpcRevertToSelf` at `0x180059cb2`
- `RPCRT4!I_RpcMapWin32Status` at `0x180059b4b`
- `RPCRT4!I_RpcMapWin32Status` at `0x180059b4b`
- `ntdll!NtOpenThreadToken` at `0x180059b8c`
- `ntdll!NtOpenThreadToken` at `0x180059b8c`
- `ntdll!NtQueryInformationToken` at `0x180059bd6`
- `ntdll!NtQueryInformationToken` at `0x180059c33`
- `ntdll!NtQueryInformationToken` at `0x180059bd6`
- `ntdll!NtQueryInformationToken` at `0x180059c33`
- `ntdll!RtlEqualSid` at `0x180059c8c`
- `ntdll!RtlEqualSid` at `0x180059c8c`
- `ntdll!RtlValidSid` at `0x180059c69`
- `ntdll!RtlValidSid` at `0x180059c69`

## string_xrefs

- `0x180059b9b`: `NlValidateAccountSidKerberos: NtOpenThreadToken failed %lx\n`
- `0x180059c42`: `NlValidateAccountSidKerberos: NtQueryInformationToken failed %lx\n`
- `0x180059b5a`: `NlValidateAccountSidKerberos: RpcImpersonateClient failed %lx\n`
- `0x180059be8`: `NlValidateAccountSidKerberos: NtQueryInformationToken for token size failed %lx\n`
- `0x180059c01`: `NlValidateAccountSidKerberos: OOM for allocating TokenUserBuffer\n`
- `0x180059cbc`: `NlValidateAccountSidKerberos: Invalid SID in token\n`

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
  PSID *v13; // rbx
  NTSTATUS v14; // eax
  NTSTATUS v15; // esi
  unsigned __int8 *v16; // rsi
  __int64 v17; // rcx
  int v18; // r13d
  ULONG ReturnLength; // [rsp+30h] [rbp-18h] BYREF
  void *TokenHandle[2]; // [rsp+38h] [rbp-10h] BYREF
  ULONG TokenInformationLength; // [rsp+A8h] [rbp+60h] BYREF

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
  TokenHandle[0] = 0;
  v11 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, TokenHandle);
  v9 = v11;
  if ( v11 < 0 )
  {
    NlPrintRoutine(0x100u, L"NlValidateAccountSidKerberos: NtOpenThreadToken failed %lx\n", (unsigned int)v11);
LABEL_10:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
    RpcRevertToSelf();
    return v9;
  }
  TokenInformationLength = 0;
  v12 = NtQueryInformationToken(TokenHandle[0], TokenUser, 0, 0, &TokenInformationLength);
  v9 = v12;
  if ( v12 != -1073741789 )
  {
    NlPrintRoutine(0x100u, L"NlValidateAccountSidKerberos: NtQueryInformationToken for token size failed %lx\n", v12);
    goto LABEL_10;
  }
  v13 = (PSID *)MIDL_user_allocate(TokenInformationLength);
  if ( !v13 )
  {
    NlPrintRoutine(0x100u, L"NlValidateAccountSidKerberos: OOM for allocating TokenUserBuffer\n");
    v9 = -1073741670;
    goto LABEL_10;
  }
  ReturnLength = 0;
  v14 = NtQueryInformationToken(TokenHandle[0], TokenUser, v13, TokenInformationLength, &ReturnLength);
  v15 = v14;
  if ( v14 < 0 )
  {
    NlPrintRoutine(0x100u, L"NlValidateAccountSidKerberos: NtQueryInformationToken failed %lx\n", (unsigned int)v14);
    free(v13);
    v9 = v15;
    goto LABEL_10;
  }
  v16 = (unsigned __int8 *)*v13;
  if ( !RtlValidSid(*v13) || (v17 = v16[1], !(_BYTE)v17) )
  {
    NlPrintRoutine(0x100u, L"NlValidateAccountSidKerberos: Invalid SID in token\n");
    free(v13);
    v9 = -1073741595;
    goto LABEL_10;
  }
  v18 = *(_DWORD *)&v16[4 * v17 + 4];
  v16[1] = v17 - 1;
  if ( !RtlEqualSid(a2, v16) || v18 != a1 )
    v10 = 0;
  *a3 = v10;
  free(v13);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
  RpcRevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x180059aec  push    rbp
0x180059aee  push    rbx
0x180059aef  push    rsi
0x180059af0  push    rdi
0x180059af1  push    r12
0x180059af3  push    r13
0x180059af5  push    r14
0x180059af7  push    r15
0x180059af9  mov     rbp, rsp
0x180059afc  sub     rsp, 48h
0x180059b00  mov     r14, r8
0x180059b03  mov     r15, rdx
0x180059b06  mov     r12d, ecx
0x180059b09  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_NetlogonHandleLeak@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_NetlogonHandleLeak@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_NetlogonHandleLeak> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_NetlogonHandleLeak>::GetImpl(void)'::`2'::impl
0x180059b10  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_NetlogonHandleLeak@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_NetlogonHandleLeak>::__private_IsEnabled(void)
0x180059b15  xor     r13d, r13d
0x180059b18  test    al, al
0x180059b1a  jnz     short loc_180059B2F
0x180059b1c  mov     r8, r14; int *
0x180059b1f  mov     rdx, r15; struct _SID *
0x180059b22  mov     ecx, r12d; unsigned int
0x180059b25  call    ?NlValidateAccountSidKerberosOld@@YAJKPEAU_SID@@PEAH@Z; NlValidateAccountSidKerberosOld(ulong,_SID *,int *)
0x180059b2a  jmp     loc_180059CE5
0x180059b2f  test    r14, r14
0x180059b32  jz      loc_180059CE0
0x180059b38  test    r15, r15
0x180059b3b  jz      loc_180059CE0
0x180059b41  xor     ecx, ecx; BindingHandle
0x180059b43  call    cs:__imp_RpcImpersonateClient
0x180059b49  mov     ecx, eax; Status
0x180059b4b  call    cs:__imp_I_RpcMapWin32Status
0x180059b51  mov     ebx, eax
0x180059b53  test    eax, eax
0x180059b55  jns     short loc_180059B72
0x180059b57  mov     r8d, eax
0x180059b5a  lea     rdx, aNlvalidateacco; "NlValidateAccountSidKerberos: RpcImpers"...
0x180059b61  mov     ecx, 100h; unsigned int
0x180059b66  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180059b6b  mov     eax, ebx
0x180059b6d  jmp     loc_180059CE5
0x180059b72  mov     edi, 1
0x180059b77  mov     [rbp+TokenHandle], r13
0x180059b7b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180059b7f  mov     r8b, dil; OpenAsSelf
0x180059b82  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180059b89  lea     edx, [rdi+7]; DesiredAccess
0x180059b8c  call    cs:__imp_NtOpenThreadToken
0x180059b92  mov     ebx, eax
0x180059b94  test    eax, eax
0x180059b96  jns     short loc_180059BBD
0x180059b98  mov     r8d, eax
0x180059b9b  lea     rdx, aNlvalidateacco_1; "NlValidateAccountSidKerberos: NtOpenThr"...
0x180059ba2  mov     ecx, 100h; unsigned int
0x180059ba7  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180059bac  lea     rcx, [rbp+TokenHandle]
0x180059bb0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180059bb5  call    cs:__imp_RpcRevertToSelf
0x180059bbb  jmp     short loc_180059B6B
0x180059bbd  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180059bc1  lea     rax, [rbp+TokenInformationLength]
0x180059bc5  xor     r9d, r9d; TokenInformationLength
0x180059bc8  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180059bcd  xor     r8d, r8d; TokenInformation
0x180059bd0  mov     [rbp+TokenInformationLength], r13d
0x180059bd4  mov     edx, edi; TokenInformationClass
0x180059bd6  call    cs:__imp_NtQueryInformationToken
0x180059bdc  mov     ebx, eax
0x180059bde  cmp     eax, 0C0000023h
0x180059be3  jz      short loc_180059BF1
0x180059be5  mov     r8d, eax
0x180059be8  lea     rdx, aNlvalidateacco_0; "NlValidateAccountSidKerberos: NtQueryIn"...
0x180059bef  jmp     short loc_180059BA2
0x180059bf1  mov     ecx, [rbp+TokenInformationLength]; size
0x180059bf4  call    MIDL_user_allocate
0x180059bf9  mov     rbx, rax
0x180059bfc  test    rax, rax
0x180059bff  jnz     short loc_180059C19
0x180059c01  lea     rdx, aNlvalidateacco_4; "NlValidateAccountSidKerberos: OOM for a"...
0x180059c08  mov     ecx, 100h; unsigned int
0x180059c0d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180059c12  mov     ebx, 0C000009Ah
0x180059c17  jmp     short loc_180059BAC
0x180059c19  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180059c1d  lea     rax, [rbp+var_18]
0x180059c21  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180059c25  mov     r8, rbx; TokenInformation
0x180059c28  mov     edx, edi; TokenInformationClass
0x180059c2a  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180059c2f  mov     [rbp+var_18], r13d
0x180059c33  call    cs:__imp_NtQueryInformationToken
0x180059c39  mov     esi, eax
0x180059c3b  test    eax, eax
0x180059c3d  jns     short loc_180059C63
0x180059c3f  mov     r8d, eax
0x180059c42  lea     rdx, aNlvalidateacco_2; "NlValidateAccountSidKerberos: NtQueryIn"...
0x180059c49  mov     ecx, 100h; unsigned int
0x180059c4e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180059c53  mov     rcx, rbx; Block
0x180059c56  call    cs:__imp_free
0x180059c5c  mov     ebx, esi
0x180059c5e  jmp     loc_180059BAC
0x180059c63  mov     rsi, [rbx]
0x180059c66  mov     rcx, rsi; Sid
0x180059c69  call    cs:__imp_RtlValidSid
0x180059c6f  test    al, al
0x180059c71  jz      short loc_180059CBC
0x180059c73  movzx   ecx, byte ptr [rsi+1]
0x180059c77  test    cl, cl
0x180059c79  jz      short loc_180059CBC
0x180059c7b  mov     r13d, [rsi+rcx*4+4]
0x180059c80  mov     rdx, rsi; Sid2
0x180059c83  sub     cl, dil
0x180059c86  mov     [rsi+1], cl
0x180059c89  mov     rcx, r15; Sid1
0x180059c8c  call    cs:__imp_RtlEqualSid
0x180059c92  test    al, al
0x180059c94  jz      short loc_180059C9B
0x180059c96  cmp     r13d, r12d
0x180059c99  jz      short loc_180059C9D
0x180059c9b  xor     edi, edi
0x180059c9d  mov     rcx, rbx; Block
0x180059ca0  mov     [r14], edi
0x180059ca3  call    cs:__imp_free
0x180059ca9  lea     rcx, [rbp+TokenHandle]
0x180059cad  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180059cb2  call    cs:__imp_RpcRevertToSelf
0x180059cb8  xor     eax, eax
0x180059cba  jmp     short loc_180059CE5
0x180059cbc  lea     rdx, aNlvalidateacco_3; "NlValidateAccountSidKerberos: Invalid S"...
0x180059cc3  mov     ecx, 100h; unsigned int
0x180059cc8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180059ccd  mov     rcx, rbx; Block
0x180059cd0  call    cs:__imp_free
0x180059cd6  mov     ebx, 0C00000E5h
0x180059cdb  jmp     loc_180059BAC
0x180059ce0  mov     eax, 0C000000Dh
0x180059ce5  add     rsp, 48h
0x180059ce9  pop     r15
0x180059ceb  pop     r14
0x180059ced  pop     r13
0x180059cef  pop     r12
0x180059cf1  pop     rdi
0x180059cf2  pop     rsi
0x180059cf3  pop     rbx
0x180059cf4  pop     rbp
0x180059cf5  retn
```
