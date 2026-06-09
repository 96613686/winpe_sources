# Windows::Compat::Inventory::Service::WinRtHost::GetUserSid(void *)

- ea: `0x1800c4840`
- end: `0x1800c4b13`
- name: `?GetUserSid@WinRtHost@Service@Inventory@Compat@Windows@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `723`
- prototype: `WCHAR *__fastcall(WCHAR *, RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c4d68`

## callees

- `0x180002bf0`
- `0x180003668`
- `0x180005483`
- `0x1800152d0`
- `0x18001f714`
- `0x1800c3d44`
- `0x1800c4840`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c48dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c490d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c497d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c49e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c48dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c490d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c497d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c49e2`
- `RPCRT4!RpcRevertToSelf` at `0x1800c4a03`
- `RPCRT4!RpcRevertToSelf` at `0x1800c4a03`
- `RPCRT4!RpcImpersonateClient` at `0x1800c488b`
- `RPCRT4!RpcImpersonateClient` at `0x1800c488b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c4ad3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c4ad3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800c4903`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800c4973`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800c4903`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800c4973`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c48c7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c4947`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c48c7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c4947`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c49d8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c49d8`

## string_xrefs

- `0x1800c4895`: `RpcImpersonateClient failed [%d]`
- `0x1800c48e3`: `CreateWellKnownSid failed [%d]`
- `0x1800c4957`: `CreateWellKnownSid failed [%d]`
- `0x1800c48a2`: `Windows::Compat::Inventory::Service::WinRtHost::GetUserSid`
- `0x1800c48cd`: `Windows::Compat::Inventory::Service::WinRtHost::GetUserSid`
- `0x1800c49b0`: `get_token_information_nothrow failed [%#x]`
- `0x1800c4913`: `CheckTokenMembership failed [%d]`
- `0x1800c4983`: `CheckTokenMembership failed [%d]`
- `0x1800c4ab3`: `Failed to get a user SID [%#x]`
- `0x1800c49e8`: `ConvertSidToStringSidW failed [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
WCHAR *__fastcall Windows::Compat::Inventory::Service::WinRtHost::GetUserSid(
        WCHAR *a1,
        RPC_BINDING_HANDLE BindingHandle)
{
  PSID *v3; // r14
  char v4; // r15
  RPC_STATUS v5; // eax
  const char *v6; // r9
  __int64 v7; // r8
  DWORD LastError; // eax
  const char *v9; // r9
  __int64 v10; // r8
  int token_information; // eax
  __int64 v12; // r8
  LPWSTR v13; // r9
  unsigned __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 v17; // [rsp+20h] [rbp-69h]
  WINBOOL IsMember; // [rsp+30h] [rbp-59h] BYREF
  DWORD cbSid; // [rsp+34h] [rbp-55h] BYREF
  int v20; // [rsp+38h] [rbp-51h]
  PSID *v21; // [rsp+40h] [rbp-49h] BYREF
  LPWSTR StringSid[3]; // [rsp+48h] [rbp-41h] BYREF
  _BYTE pSid[80]; // [rsp+60h] [rbp-29h] BYREF

  StringSid[1] = a1;
  v20 = 0;
  v3 = 0;
  v21 = 0;
  StringSid[0] = 0;
  v4 = 0;
  v5 = RpcImpersonateClient(BindingHandle);
  if ( v5 )
  {
    v6 = "RpcImpersonateClient failed [%d]";
    v7 = 422;
    goto LABEL_21;
  }
  cbSid = 68;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
  {
    LastError = GetLastError();
    v9 = "CreateWellKnownSid failed [%d]";
    v10 = 432;
LABEL_18:
    AslLogCallPrintf(1, "Windows::Compat::Inventory::Service::WinRtHost::GetUserSid", v10, v9, LastError);
    goto LABEL_19;
  }
  IsMember = 0;
  if ( !CheckTokenMembership(0, pSid, &IsMember) )
  {
    LastError = GetLastError();
    v9 = "CheckTokenMembership failed [%d]";
    v10 = 439;
    goto LABEL_18;
  }
  if ( IsMember )
    goto LABEL_8;
  cbSid = 68;
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
  {
    LastError = GetLastError();
    v9 = "CreateWellKnownSid failed [%d]";
    v10 = 452;
    goto LABEL_18;
  }
  if ( !CheckTokenMembership(0, pSid, &IsMember) )
  {
    LastError = GetLastError();
    v9 = "CheckTokenMembership failed [%d]";
    v10 = 458;
    goto LABEL_18;
  }
  if ( IsMember )
  {
LABEL_8:
    v4 = 1;
  }
  else
  {
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&v21, -5);
    if ( token_information >= 0 )
    {
      v3 = v21;
      if ( !ConvertSidToStringSidW(*v21, StringSid) )
      {
        LastError = GetLastError();
        v9 = "ConvertSidToStringSidW failed [%d]";
        v10 = 478;
        goto LABEL_18;
      }
    }
    else
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::Service::WinRtHost::GetUserSid",
        472,
        "get_token_information_nothrow failed [%#x]",
        token_information);
      v3 = v21;
    }
  }
LABEL_19:
  v5 = RpcRevertToSelf();
  if ( !v5 )
    goto LABEL_22;
  v6 = "RpcRevertToSelf failed [%d]";
  v7 = 489;
LABEL_21:
  LODWORD(v17) = v5;
  AslLogCallPrintf(1, "Windows::Compat::Inventory::Service::WinRtHost::GetUserSid", v7, v6, v17);
LABEL_22:
  *(_OWORD *)a1 = 0;
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 7;
  *a1 = 0;
  v20 = 1;
  if ( v4 )
  {
    *((_QWORD *)a1 + 2) = 3;
    memmove_0(a1, L"all", 6u);
    a1[3] = 0;
  }
  else
  {
    v13 = StringSid[0];
    if ( StringSid[0] )
    {
      v14 = -1;
      do
        ++v14;
      while ( StringSid[0][v14] );
      if ( v14 > 7 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          a1,
          v14,
          v12,
          StringSid[0]);
      }
      else
      {
        *((_QWORD *)a1 + 2) = v14;
        v15 = v14;
        memmove_0(a1, v13, 2 * v14);
        a1[v15] = 0;
      }
    }
    else
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::Service::WinRtHost::GetUserSid",
        504,
        "Failed to get a user SID [%#x]",
        -2147418113);
    }
  }
  if ( StringSid[0] )
    LocalFree(StringSid[0]);
  if ( v3 )
    operator delete(v3);
  return a1;
}

```

## disassembly

```asm
0x1800c4840  mov     [rsp-8+arg_10], rbx
0x1800c4845  mov     [rsp-8+arg_18], rsi
0x1800c484a  push    rbp
0x1800c484b  push    rdi
0x1800c484c  push    r12
0x1800c484e  push    r14
0x1800c4850  push    r15
0x1800c4852  lea     rbp, [rsp-37h]
0x1800c4857  sub     rsp, 0C0h
0x1800c485e  mov     rax, cs:__security_cookie
0x1800c4865  xor     rax, rsp
0x1800c4868  mov     [rbp+57h+var_30], rax
0x1800c486c  mov     rdi, rcx
0x1800c486f  mov     [rbp+57h+var_90], rcx
0x1800c4873  xor     r12d, r12d
0x1800c4876  mov     [rbp+57h+var_A8], r12d
0x1800c487a  mov     r14d, r12d
0x1800c487d  mov     [rbp+57h+var_A0], r12
0x1800c4881  mov     [rbp+57h+StringSid], r12
0x1800c4885  mov     r15b, r12b
0x1800c4888  mov     rcx, rdx; BindingHandle
0x1800c488b  call    cs:__imp_RpcImpersonateClient
0x1800c4891  test    eax, eax
0x1800c4893  jz      short loc_1800C48B3
0x1800c4895  lea     r9, aRpcimpersonate; "RpcImpersonateClient failed [%d]"
0x1800c489c  mov     r8d, 1A6h
0x1800c48a2  lea     rsi, aWindowsCompatI_57; "Windows::Compat::Inventory::Service::Wi"...
0x1800c48a9  lea     ebx, [r12+1]
0x1800c48ae  jmp     loc_1800C4A1A
0x1800c48b3  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1800c48ba  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800c48be  lea     r8, [rbp+57h+pSid]; pSid
0x1800c48c2  xor     edx, edx; DomainSid
0x1800c48c4  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800c48c7  call    cs:__imp_CreateWellKnownSid
0x1800c48cd  lea     rsi, aWindowsCompatI_57; "Windows::Compat::Inventory::Service::Wi"...
0x1800c48d4  mov     ebx, 1
0x1800c48d9  test    eax, eax
0x1800c48db  jnz     short loc_1800C48F5
0x1800c48dd  call    cs:__imp_GetLastError
0x1800c48e3  lea     r9, aCreatewellknow; "CreateWellKnownSid failed [%d]"
0x1800c48ea  mov     r8d, 1B0h
0x1800c48f0  jmp     loc_1800C49F5
0x1800c48f5  mov     [rbp+57h+IsMember], r12d
0x1800c48f9  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800c48fd  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x1800c4901  xor     ecx, ecx; TokenHandle
0x1800c4903  call    cs:__imp_CheckTokenMembership
0x1800c4909  test    eax, eax
0x1800c490b  jnz     short loc_1800C4925
0x1800c490d  call    cs:__imp_GetLastError
0x1800c4913  lea     r9, aChecktokenmemb; "CheckTokenMembership failed [%d]"
0x1800c491a  mov     r8d, 1B7h
0x1800c4920  jmp     loc_1800C49F5
0x1800c4925  cmp     [rbp+57h+IsMember], r12d
0x1800c4929  jz      short loc_1800C4933
0x1800c492b  mov     r15b, bl
0x1800c492e  jmp     loc_1800C4A03
0x1800c4933  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1800c493a  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800c493e  lea     r8, [rbp+57h+pSid]; pSid
0x1800c4942  xor     edx, edx; DomainSid
0x1800c4944  lea     ecx, [rdx+16h]; WellKnownSidType
0x1800c4947  call    cs:__imp_CreateWellKnownSid
0x1800c494d  test    eax, eax
0x1800c494f  jnz     short loc_1800C4969
0x1800c4951  call    cs:__imp_GetLastError
0x1800c4957  lea     r9, aCreatewellknow; "CreateWellKnownSid failed [%d]"
0x1800c495e  mov     r8d, 1C4h
0x1800c4964  jmp     loc_1800C49F5
0x1800c4969  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800c496d  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x1800c4971  xor     ecx, ecx; TokenHandle
0x1800c4973  call    cs:__imp_CheckTokenMembership
0x1800c4979  test    eax, eax
0x1800c497b  jnz     short loc_1800C4992
0x1800c497d  call    cs:__imp_GetLastError
0x1800c4983  lea     r9, aChecktokenmemb; "CheckTokenMembership failed [%d]"
0x1800c498a  mov     r8d, 1CAh
0x1800c4990  jmp     short loc_1800C49F5
0x1800c4992  cmp     [rbp+57h+IsMember], r12d
0x1800c4996  jnz     short loc_1800C492B
0x1800c4998  mov     rdx, 0FFFFFFFFFFFFFFFBh
0x1800c499f  lea     rcx, [rbp+57h+var_A0]
0x1800c49a3  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800c49a8  test    eax, eax
0x1800c49aa  jns     short loc_1800C49CD
0x1800c49ac  mov     [rsp+0E0h+var_C0], eax
0x1800c49b0  lea     r9, aGetTokenInform; "get_token_information_nothrow failed [%"...
0x1800c49b7  mov     r8d, 1D8h
0x1800c49bd  mov     rdx, rsi
0x1800c49c0  mov     ecx, ebx
0x1800c49c2  call    AslLogCallPrintf
0x1800c49c7  mov     r14, [rbp+57h+var_A0]
0x1800c49cb  jmp     short loc_1800C4A03
0x1800c49cd  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800c49d1  mov     r14, [rbp+57h+var_A0]
0x1800c49d5  mov     rcx, [r14]; Sid
0x1800c49d8  call    cs:__imp_ConvertSidToStringSidW
0x1800c49de  test    eax, eax
0x1800c49e0  jnz     short loc_1800C4A03
0x1800c49e2  call    cs:__imp_GetLastError
0x1800c49e8  lea     r9, aConvertsidtost; "ConvertSidToStringSidW failed [%d]"
0x1800c49ef  mov     r8d, 1DEh
0x1800c49f5  mov     [rsp+0E0h+var_C0], eax
0x1800c49f9  mov     rdx, rsi
0x1800c49fc  mov     ecx, ebx
0x1800c49fe  call    AslLogCallPrintf
0x1800c4a03  call    cs:__imp_RpcRevertToSelf
0x1800c4a09  test    eax, eax
0x1800c4a0b  jz      short loc_1800C4A28
0x1800c4a0d  lea     r9, aRpcreverttosel; "RpcRevertToSelf failed [%d]"
0x1800c4a14  mov     r8d, 1E9h
0x1800c4a1a  mov     [rsp+0E0h+var_C0], eax
0x1800c4a1e  mov     rdx, rsi
0x1800c4a21  mov     ecx, ebx
0x1800c4a23  call    AslLogCallPrintf
0x1800c4a28  xorps   xmm0, xmm0
0x1800c4a2b  movups  xmmword ptr [rdi], xmm0
0x1800c4a2e  mov     [rdi+10h], r12
0x1800c4a32  mov     qword ptr [rdi+18h], 7
0x1800c4a3a  mov     [rdi], r12w
0x1800c4a3e  mov     [rbp+57h+var_A8], ebx
0x1800c4a41  test    r15b, r15b
0x1800c4a44  jz      short loc_1800C4A6A
0x1800c4a46  mov     qword ptr [rdi+10h], 3
0x1800c4a4e  mov     r8d, 6; Size
0x1800c4a54  lea     rdx, S2; "all"
0x1800c4a5b  mov     rcx, rdi; void *
0x1800c4a5e  call    memmove_0
0x1800c4a63  mov     [rdi+6], r12w
0x1800c4a68  jmp     short loc_1800C4ACA
0x1800c4a6a  mov     r9, [rbp+57h+StringSid]
0x1800c4a6e  test    r9, r9
0x1800c4a71  jz      short loc_1800C4AAB
0x1800c4a73  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800c4a77  inc     rdx
0x1800c4a7a  cmp     [r9+rdx*2], r12w
0x1800c4a7f  jnz     short loc_1800C4A77
0x1800c4a81  mov     rcx, rdi; void *
0x1800c4a84  cmp     rdx, 7
0x1800c4a88  ja      short loc_1800C4AA4
0x1800c4a8a  mov     [rdi+10h], rdx
0x1800c4a8e  lea     rbx, [rdx+rdx]
0x1800c4a92  mov     r8, rbx; Size
0x1800c4a95  mov     rdx, r9; Src
0x1800c4a98  call    memmove_0
0x1800c4a9d  mov     [rbx+rdi], r12w
0x1800c4aa2  jmp     short loc_1800C4ACA
0x1800c4aa4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800c4aa9  jmp     short loc_1800C4ACA
0x1800c4aab  mov     [rsp+0E0h+var_C0], 8000FFFFh
0x1800c4ab3  lea     r9, aFailedToGetAUs; "Failed to get a user SID [%#x]"
0x1800c4aba  mov     r8d, 1F8h
0x1800c4ac0  mov     rdx, rsi
0x1800c4ac3  mov     ecx, ebx
0x1800c4ac5  call    AslLogCallPrintf
0x1800c4aca  mov     rcx, [rbp+57h+StringSid]; hMem
0x1800c4ace  test    rcx, rcx
0x1800c4ad1  jz      short loc_1800C4ADA
0x1800c4ad3  call    cs:__imp_LocalFree
0x1800c4ad9  nop
0x1800c4ada  test    r14, r14
0x1800c4add  jz      short loc_1800C4AE7
0x1800c4adf  mov     rcx, r14; Block
0x1800c4ae2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c4ae7  mov     rax, rdi
0x1800c4aea  mov     rcx, [rbp+57h+var_30]
0x1800c4aee  xor     rcx, rsp; StackCookie
0x1800c4af1  call    __security_check_cookie
0x1800c4af6  lea     r11, [rsp+0E0h+var_20]
0x1800c4afe  mov     rbx, [r11+40h]
0x1800c4b02  mov     rsi, [r11+48h]
0x1800c4b06  mov     rsp, r11
0x1800c4b09  pop     r15
0x1800c4b0b  pop     r14
0x1800c4b0d  pop     r12
0x1800c4b0f  pop     rdi
0x1800c4b10  pop     rbp
0x1800c4b11  retn
```
