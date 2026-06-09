# LsaDbpCheckCallerIsMemberOf(void * const,int *)

- ea: `0x180009f50`
- end: `0x18000a079`
- name: `?LsaDbpCheckCallerIsMemberOf@@YAJQEAXPEAH@Z`
- size: `297`
- prototype: `__int64 __fastcall(PSID SidToCheck, PBOOL IsMember)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a080`

## callees

- `0x180001670`
- `0x180009f50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a04e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a04e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000a034`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000a034`
- `RPCRT4!RpcImpersonateClient` at `0x180009fa0`
- `RPCRT4!RpcImpersonateClient` at `0x180009fa0`
- `RPCRT4!I_RpcMapWin32Status` at `0x180009fa8`
- `RPCRT4!I_RpcMapWin32Status` at `0x180009ffc`
- `RPCRT4!I_RpcMapWin32Status` at `0x180009fa8`
- `RPCRT4!I_RpcMapWin32Status` at `0x180009ffc`
- `RPCRT4!RpcRevertToSelf` at `0x180009ff4`
- `RPCRT4!RpcRevertToSelf` at `0x180009ff4`
- `ntdll!NtQueryInformationToken` at `0x180009fec`
- `ntdll!NtQueryInformationToken` at `0x180009fec`
- `ntdll!NtOpenThreadToken` at `0x180009fc9`
- `ntdll!NtOpenThreadToken` at `0x180009fc9`
- `ntdll!NtClose` at `0x18000a01f`
- `ntdll!NtClose` at `0x18000a01f`
- `ntdll!RtlGetLastNtStatus` at `0x18000a03e`
- `ntdll!RtlGetLastNtStatus` at `0x18000a03e`

## pseudocode

```c
__int64 __fastcall LsaDbpCheckCallerIsMemberOf(PSID SidToCheck, PBOOL IsMember)
{
  RPC_STATUS v4; // eax
  int v5; // edi
  RPC_STATUS v6; // eax
  int v7; // eax
  unsigned int LastNtStatus; // ebx
  void *v9; // rsi
  void *TokenHandle; // [rsp+30h] [rbp-50h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-48h] BYREF
  _OWORD TokenInformation[3]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v14; // [rsp+70h] [rbp-10h]

  TokenHandle = 0;
  ReturnLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v14 = 0;
  v4 = RpcImpersonateClient(0);
  v5 = I_RpcMapWin32Status(v4);
  if ( v5 >= 0 )
  {
    v5 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xAu, 1u, &TokenHandle);
    if ( v5 >= 0 )
      v5 = NtQueryInformationToken(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
    v6 = RpcRevertToSelf();
    v7 = I_RpcMapWin32Status(v6);
    LastNtStatus = v7;
    if ( v5 >= 0 )
    {
      if ( v7 >= 0 )
      {
        v9 = TokenHandle;
        if ( !CheckTokenMembership(TokenHandle, SidToCheck, IsMember) )
          LastNtStatus = RtlGetLastNtStatus();
        goto LABEL_13;
      }
      v5 = v7;
    }
  }
  v9 = 0;
  if ( TokenHandle )
    NtClose(TokenHandle);
  LastNtStatus = v5;
LABEL_13:
  if ( v9 )
    CloseHandle(v9);
  return LastNtStatus;
}

```

## disassembly

```asm
0x180009f50  mov     [rsp-28h+arg_10], rbx
0x180009f55  push    rbp
0x180009f56  push    rsi
0x180009f57  push    rdi
0x180009f58  push    r14
0x180009f5a  push    r15
0x180009f5c  mov     rbp, rsp
0x180009f5f  sub     rsp, 80h
0x180009f66  mov     rax, cs:__security_cookie
0x180009f6d  xor     rax, rsp
0x180009f70  mov     [rbp+var_8], rax
0x180009f74  xorps   xmm0, xmm0
0x180009f77  mov     [rbp+TokenHandle], 0
0x180009f7f  mov     r14, rcx
0x180009f82  mov     [rbp+var_48], 0
0x180009f89  xor     eax, eax
0x180009f8b  xor     ecx, ecx; BindingHandle
0x180009f8d  movups  [rbp+TokenInformation], xmm0
0x180009f91  mov     [rbp+var_10], rax
0x180009f95  mov     r15, rdx
0x180009f98  movups  [rbp+var_30], xmm0
0x180009f9c  movups  [rbp+var_20], xmm0
0x180009fa0  call    cs:__imp_RpcImpersonateClient
0x180009fa6  mov     ecx, eax; Status
0x180009fa8  call    cs:__imp_I_RpcMapWin32Status
0x180009fae  mov     edi, eax
0x180009fb0  test    eax, eax
0x180009fb2  js      short loc_18000A014
0x180009fb4  mov     ebx, 0Ah
0x180009fb9  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180009fbd  mov     edx, ebx; DesiredAccess
0x180009fbf  mov     r8b, 1; OpenAsSelf
0x180009fc2  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180009fc9  call    cs:__imp_NtOpenThreadToken
0x180009fcf  mov     edi, eax
0x180009fd1  test    eax, eax
0x180009fd3  js      short loc_180009FF4
0x180009fd5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180009fd9  lea     rax, [rbp+var_48]
0x180009fdd  lea     r9d, [rbx+2Eh]; TokenInformationLength
0x180009fe1  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180009fe6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180009fea  mov     edx, ebx; TokenInformationClass
0x180009fec  call    cs:__imp_NtQueryInformationToken
0x180009ff2  mov     edi, eax
0x180009ff4  call    cs:__imp_RpcRevertToSelf
0x180009ffa  mov     ecx, eax; Status
0x180009ffc  call    cs:__imp_I_RpcMapWin32Status
0x18000a002  mov     ebx, eax
0x18000a004  test    edi, edi
0x18000a006  js      short loc_18000A014
0x18000a008  test    eax, eax
0x18000a00a  js      short loc_18000A012
0x18000a00c  mov     rsi, [rbp+TokenHandle]
0x18000a010  jmp     short loc_18000A02B
0x18000a012  mov     edi, eax
0x18000a014  mov     rcx, [rbp+TokenHandle]; Handle
0x18000a018  xor     esi, esi
0x18000a01a  test    rcx, rcx
0x18000a01d  jz      short loc_18000A025
0x18000a01f  call    cs:__imp_NtClose
0x18000a025  mov     ebx, edi
0x18000a027  test    edi, edi
0x18000a029  js      short loc_18000A046
0x18000a02b  mov     r8, r15; IsMember
0x18000a02e  mov     rdx, r14; SidToCheck
0x18000a031  mov     rcx, rsi; TokenHandle
0x18000a034  call    cs:__imp_CheckTokenMembership
0x18000a03a  test    eax, eax
0x18000a03c  jnz     short loc_18000A046
0x18000a03e  call    cs:__imp_RtlGetLastNtStatus
0x18000a044  mov     ebx, eax
0x18000a046  test    rsi, rsi
0x18000a049  jz      short loc_18000A054
0x18000a04b  mov     rcx, rsi; hObject
0x18000a04e  call    cs:__imp_CloseHandle
0x18000a054  mov     eax, ebx
0x18000a056  mov     rcx, [rbp+var_8]
0x18000a05a  xor     rcx, rsp; StackCookie
0x18000a05d  call    __security_check_cookie
0x18000a062  mov     rbx, [rsp+80h+arg_10]
0x18000a06a  add     rsp, 80h
0x18000a071  pop     r15
0x18000a073  pop     r14
0x18000a075  pop     rdi
0x18000a076  pop     rsi
0x18000a077  pop     rbp
0x18000a078  retn
```
