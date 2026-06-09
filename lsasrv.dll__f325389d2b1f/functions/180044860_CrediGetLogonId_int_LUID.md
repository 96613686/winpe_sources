# CrediGetLogonId(int,_LUID *)

- ea: `0x180044860`
- end: `0x180044a89`
- name: `?CrediGetLogonId@@YAJHPEAU_LUID@@@Z`
- size: `553`
- prototype: `int __fastcall(int, struct _LUID *)`
- caller_count: `12`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180044560`
- `0x180044790`
- `0x180085bb0`
- `0x180089900`
- `0x18009060c`
- `0x1800f4070`
- `0x1800f4260`
- `0x1800f4370`
- `0x1800f43f0`
- `0x1800f4490`
- `0x1800f4650`
- `0x1800f4750`

## callees

- `0x180044860`
- `0x1800b86d0`
- `0x1800b9304`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800449ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800449ee`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180044996`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180044996`
- `ntdll!NtClose` at `0x1800449dd`
- `ntdll!NtClose` at `0x180044a0e`
- `ntdll!NtClose` at `0x180044a51`
- `ntdll!NtClose` at `0x1800449dd`
- `ntdll!NtClose` at `0x180044a0e`
- `ntdll!NtClose` at `0x180044a51`
- `ntdll!NtQueryInformationToken` at `0x180044920`
- `ntdll!NtQueryInformationToken` at `0x18004496a`
- `ntdll!NtQueryInformationToken` at `0x180044920`
- `ntdll!NtQueryInformationToken` at `0x18004496a`
- `ntdll!NtOpenThreadToken` at `0x1800448d5`
- `ntdll!NtOpenThreadToken` at `0x1800448d5`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800449ba`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800449ba`
- `RPCRT4!RpcRevertToSelf` at `0x180044a61`
- `RPCRT4!RpcRevertToSelf` at `0x180044a61`
- `RPCRT4!I_RpcMapWin32Status` at `0x180044897`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800449fc`
- `RPCRT4!I_RpcMapWin32Status` at `0x180044a71`
- `RPCRT4!I_RpcMapWin32Status` at `0x180044897`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800449fc`
- `RPCRT4!I_RpcMapWin32Status` at `0x180044a71`
- `RPCRT4!RpcImpersonateClient` at `0x180044889`
- `RPCRT4!RpcImpersonateClient` at `0x180044889`

## pseudocode

```c
int __fastcall CrediGetLogonId(int a1, struct _LUID *a2)
{
  RPC_STATUS v4; // eax
  int result; // eax
  NTSTATUS v6; // ebx
  void *v7; // rcx
  RPC_STATUS IsClientLocal; // eax
  RPC_STATUS LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp-79h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-71h] BYREF
  int v12; // [rsp+3Ch] [rbp-6Dh] BYREF
  unsigned int ClientLocalFlag[4]; // [rsp+40h] [rbp-69h] BYREF
  _QWORD v14[12]; // [rsp+50h] [rbp-59h] BYREF
  _OWORD TokenInformation[3]; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v16; // [rsp+E0h] [rbp+37h]

  if ( a1 || (v4 = RpcImpersonateClient(0), result = I_RpcMapWin32Status(v4), result >= 0) )
  {
    TokenHandle = 0;
    v6 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
    if ( v6 < 0 )
      goto LABEL_17;
    ReturnLength = 0;
    v16 = 0;
    memset(TokenInformation, 0, sizeof(TokenInformation));
    v6 = NtQueryInformationToken(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
    if ( v6 >= 0 )
    {
      memset_0(v14, 0, 0x58u);
      v7 = TokenHandle;
      *a2 = *(struct _LUID *)((char *)TokenInformation + 8);
      v6 = NtQueryInformationToken(v7, TokenUser, v14, 0x58u, &ReturnLength);
      if ( v6 >= 0 )
      {
        v12 = 0;
        if ( (unsigned int)CheckTokenMembershipEx(TokenHandle, v14[0], 2, &v12) )
        {
          if ( v12 )
          {
            ClientLocalFlag[0] = 0;
            IsClientLocal = I_RpcBindingIsClientLocal(0, ClientLocalFlag);
            if ( IsClientLocal )
            {
              v6 = I_RpcMapWin32Status(IsClientLocal);
              if ( v6 >= 0 )
                goto LABEL_10;
              goto LABEL_16;
            }
            if ( ClientLocalFlag[0] )
            {
LABEL_10:
              NtClose(TokenHandle);
              return 0;
            }
          }
          v6 = -1073741790;
LABEL_16:
          NtClose(TokenHandle);
          goto LABEL_17;
        }
        LastError = GetLastError();
        v6 = I_RpcMapWin32Status(LastError);
      }
    }
    NtClose(TokenHandle);
    if ( v6 >= 0 )
      return v6;
LABEL_17:
    if ( !a1 )
      RpcRevertToSelf();
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180044860  push    rbp
0x180044862  push    rsi
0x180044863  push    rdi
0x180044864  lea     rbp, [rsp-47h]
0x180044869  sub     rsp, 0F0h
0x180044870  mov     rax, cs:__security_cookie
0x180044877  xor     rax, rsp
0x18004487a  mov     [rbp+57h+var_18], rax
0x18004487e  mov     rsi, rdx
0x180044881  mov     edi, ecx
0x180044883  test    ecx, ecx
0x180044885  jnz     short loc_1800448AB
0x180044887  xor     ecx, ecx; BindingHandle
0x180044889  call    cs:__imp_RpcImpersonateClient
0x180044890  nop     dword ptr [rax+rax+00h]
0x180044895  mov     ecx, eax; Status
0x180044897  call    cs:__imp_I_RpcMapWin32Status
0x18004489e  nop     dword ptr [rax+rax+00h]
0x1800448a3  test    eax, eax
0x1800448a5  js      loc_180044A30
0x1800448ab  mov     [rsp+100h+arg_0], rbx
0x1800448b3  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800448b7  mov     [rsp+100h+arg_10], r14
0x1800448bf  mov     r8b, 1; OpenAsSelf
0x1800448c2  xor     r14d, r14d
0x1800448c5  mov     edx, 8; DesiredAccess
0x1800448ca  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800448d1  mov     [rbp+57h+TokenHandle], r14
0x1800448d5  call    cs:__imp_NtOpenThreadToken
0x1800448dc  nop     dword ptr [rax+rax+00h]
0x1800448e1  mov     ebx, eax
0x1800448e3  test    eax, eax
0x1800448e5  js      loc_180044A5D
0x1800448eb  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800448ef  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800448f3  xorps   xmm0, xmm0
0x1800448f6  mov     [rbp+57h+var_C8], r14d
0x1800448fa  xor     eax, eax
0x1800448fc  mov     r9d, 38h ; '8'; TokenInformationLength
0x180044902  mov     [rbp+57h+var_20], rax
0x180044906  mov     edx, 0Ah; TokenInformationClass
0x18004490b  lea     rax, [rbp+57h+var_C8]
0x18004490f  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x180044914  movups  [rbp+57h+TokenInformation], xmm0
0x180044918  movups  [rbp+57h+var_40], xmm0
0x18004491c  movups  [rbp+57h+var_30], xmm0
0x180044920  call    cs:__imp_NtQueryInformationToken
0x180044927  nop     dword ptr [rax+rax+00h]
0x18004492c  mov     ebx, eax
0x18004492e  test    eax, eax
0x180044930  js      loc_180044A0A
0x180044936  xor     edx, edx; Val
0x180044938  lea     rcx, [rbp+57h+var_B0]; void *
0x18004493c  mov     r8d, 58h ; 'X'; Size
0x180044942  call    memset_0
0x180044947  mov     rax, qword ptr [rbp+57h+TokenInformation+8]
0x18004494b  lea     r8, [rbp+57h+var_B0]; TokenInformation
0x18004494f  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180044953  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180044959  mov     [rsi], rax
0x18004495c  mov     edx, 1; TokenInformationClass
0x180044961  lea     rax, [rbp+57h+var_C8]
0x180044965  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x18004496a  call    cs:__imp_NtQueryInformationToken
0x180044971  nop     dword ptr [rax+rax+00h]
0x180044976  mov     ebx, eax
0x180044978  test    eax, eax
0x18004497a  js      loc_180044A0A
0x180044980  mov     rdx, [rbp+57h+var_B0]
0x180044984  lea     r9, [rbp+57h+var_C4]
0x180044988  mov     rcx, [rbp+57h+TokenHandle]
0x18004498c  mov     r8d, 2
0x180044992  mov     [rbp+57h+var_C4], r14d
0x180044996  call    cs:__imp_CheckTokenMembershipEx
0x18004499d  nop     dword ptr [rax+rax+00h]
0x1800449a2  test    eax, eax
0x1800449a4  jz      short loc_1800449EE
0x1800449a6  cmp     [rbp+57h+var_C4], r14d
0x1800449aa  jz      loc_180044A48
0x1800449b0  lea     rdx, [rbp+57h+ClientLocalFlag]; ClientLocalFlag
0x1800449b4  mov     [rbp+57h+ClientLocalFlag], r14d
0x1800449b8  xor     ecx, ecx; BindingHandle
0x1800449ba  call    cs:__imp_I_RpcBindingIsClientLocal
0x1800449c1  nop     dword ptr [rax+rax+00h]
0x1800449c6  test    eax, eax
0x1800449c8  jnz     loc_180044A6F
0x1800449ce  cmp     [rbp+57h+ClientLocalFlag], r14d
0x1800449d2  setz    al
0x1800449d5  test    al, al
0x1800449d7  jnz     short loc_180044A48
0x1800449d9  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800449dd  call    cs:__imp_NtClose
0x1800449e4  nop     dword ptr [rax+rax+00h]
0x1800449e9  mov     eax, r14d
0x1800449ec  jmp     short loc_180044A20
0x1800449ee  call    cs:__imp_GetLastError
0x1800449f5  nop     dword ptr [rax+rax+00h]
0x1800449fa  mov     ecx, eax; Status
0x1800449fc  call    cs:__imp_I_RpcMapWin32Status
0x180044a03  nop     dword ptr [rax+rax+00h]
0x180044a08  mov     ebx, eax
0x180044a0a  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180044a0e  call    cs:__imp_NtClose
0x180044a15  nop     dword ptr [rax+rax+00h]
0x180044a1a  test    ebx, ebx
0x180044a1c  js      short loc_180044A5D
0x180044a1e  mov     eax, ebx
0x180044a20  mov     rbx, [rsp+100h+arg_0]
0x180044a28  mov     r14, [rsp+100h+arg_10]
0x180044a30  mov     rcx, [rbp+57h+var_18]
0x180044a34  xor     rcx, rsp; StackCookie
0x180044a37  call    __security_check_cookie
0x180044a3c  add     rsp, 0F0h
0x180044a43  pop     rdi
0x180044a44  pop     rsi
0x180044a45  pop     rbp
0x180044a46  retn
0x180044a48  mov     ebx, 0C0000022h
0x180044a4d  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180044a51  call    cs:__imp_NtClose
0x180044a58  nop     dword ptr [rax+rax+00h]
0x180044a5d  test    edi, edi
0x180044a5f  jnz     short loc_180044A1E
0x180044a61  call    cs:__imp_RpcRevertToSelf
0x180044a68  nop     dword ptr [rax+rax+00h]
0x180044a6d  jmp     short loc_180044A1E
0x180044a6f  mov     ecx, eax; Status
0x180044a71  call    cs:__imp_I_RpcMapWin32Status
0x180044a78  nop     dword ptr [rax+rax+00h]
0x180044a7d  mov     ebx, eax
0x180044a7f  test    eax, eax
0x180044a81  jns     loc_1800449D9
0x180044a87  jmp     short loc_180044A4D
```
