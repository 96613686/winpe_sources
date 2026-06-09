# NlEnsureClientIsNamedUser(_DOMAIN_INFO *,ushort *)

- ea: `0x18002daa8`
- end: `0x18002dd3f`
- name: `?NlEnsureClientIsNamedUser@@YAKPEAU_DOMAIN_INFO@@PEAG@Z`
- size: `663`
- prototype: `unsigned int __fastcall(struct _DOMAIN_INFO *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180034ea0`

## callees

- `0x180003320`
- `0x1800037f0`
- `0x180007e90`
- `0x18000c440`
- `0x18002daa8`
- `0x180038e20`
- `0x180041ccc`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002db36`
- `RPCRT4!RpcImpersonateClient` at `0x18002db36`
- `RPCRT4!RpcRevertToSelf` at `0x18002dd1d`
- `RPCRT4!RpcRevertToSelf` at `0x18002dd1d`
- `ntdll!NtOpenThreadToken` at `0x18002db7d`
- `ntdll!NtOpenThreadToken` at `0x18002db7d`
- `ntdll!NtQueryInformationToken` at `0x18002dbcc`
- `ntdll!NtQueryInformationToken` at `0x18002dc1a`
- `ntdll!NtQueryInformationToken` at `0x18002dbcc`
- `ntdll!NtQueryInformationToken` at `0x18002dc1a`
- `ntdll!RtlSubAuthoritySid` at `0x18002dc56`
- `ntdll!RtlSubAuthoritySid` at `0x18002dc56`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002dc42`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002dc9e`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002dc42`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002dc9e`
- `ntdll!NtClose` at `0x18002dd03`
- `ntdll!NtClose` at `0x18002dd03`
- `ntdll!RtlEqualSid` at `0x18002dcb6`
- `ntdll!RtlEqualSid` at `0x18002dcb6`

## string_xrefs

- `0x18002db0b`: `NlEnsureClientIsNamedUser: %ws: NlSamOpenNamedUser failed 0x%lx\n`
- `0x18002db4f`: `NlEnsureClientIsNamedUser: %ws: RpcImpersonateClient failed 0x%lx\n`
- `0x18002db90`: `NlEnsureClientIsNamedUser: %ws: NtOpenThreadToken failed 0x%lx\n`
- `0x18002dbe2`: `NlEnsureClientIsNamedUser: %ws: NtOpenQueryInformationThread failed 0x%lx\n`
- `0x18002dc2c`: `NlEnsureClientIsNamedUser: %ws: NtOpenQueryInformationThread (again) failed 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NlEnsureClientIsNamedUser(struct _DOMAIN_INFO *a1, unsigned __int16 *a2)
{
  NTSTATUS v4; // ebx
  unsigned __int16 *v5; // r8
  NTSTATUS v6; // ecx
  unsigned int v7; // ebx
  RPC_STATUS v8; // eax
  NTSTATUS v9; // r14d
  unsigned __int16 *v10; // r8
  PSID v11; // rbx
  PUCHAR v12; // rax
  PULONG v13; // rax
  unsigned int v14; // r14d
  void *v15; // rdx
  PUCHAR v16; // rax
  PULONG ReturnLength; // [rsp+20h] [rbp-30h]
  PSID *TokenInformation; // [rsp+40h] [rbp-10h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-8h] BYREF
  ULONG TokenInformationLength; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v22; // [rsp+88h] [rbp+38h] BYREF

  TokenHandle = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  v22 = 0;
  v4 = NlSamOpenNamedUser(a1, a2, 0, 0, 0, &v22, 0);
  if ( v4 < 0 )
  {
    v5 = L"NlEnsureClientIsNamedUser: %ws: NlSamOpenNamedUser failed 0x%lx\n";
LABEL_3:
    LODWORD(ReturnLength) = v4;
    NlPrintDomRoutine(0x100u, a1, v5, a2, ReturnLength);
    v6 = v4;
LABEL_4:
    v7 = NetpNtStatusToApiStatus(v6);
    goto LABEL_21;
  }
  v8 = RpcImpersonateClient(0);
  v7 = v8;
  if ( v8 )
  {
    LODWORD(ReturnLength) = v8;
    NlPrintDomRoutine(
      0x100u,
      a1,
      L"NlEnsureClientIsNamedUser: %ws: RpcImpersonateClient failed 0x%lx\n",
      a2,
      ReturnLength);
    goto LABEL_21;
  }
  v7 = 8;
  v9 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  if ( v9 < 0 )
  {
    v10 = L"NlEnsureClientIsNamedUser: %ws: NtOpenThreadToken failed 0x%lx\n";
LABEL_9:
    LODWORD(ReturnLength) = v9;
    NlPrintDomRoutine(0x100u, a1, v10, a2, ReturnLength);
    v6 = v9;
    goto LABEL_4;
  }
  v9 = NtQueryInformationToken(TokenHandle, TokenUser, &TokenInformation, 0, &TokenInformationLength);
  if ( v9 != -1073741789 )
  {
    v10 = L"NlEnsureClientIsNamedUser: %ws: NtOpenQueryInformationThread failed 0x%lx\n";
    goto LABEL_9;
  }
  TokenInformation = (PSID *)NetpMemoryAllocate(TokenInformationLength);
  if ( TokenInformation )
  {
    v4 = NtQueryInformationToken(
           TokenHandle,
           TokenUser,
           TokenInformation,
           TokenInformationLength,
           &TokenInformationLength);
    if ( v4 < 0 )
    {
      v5 = L"NlEnsureClientIsNamedUser: %ws: NtOpenQueryInformationThread (again) failed 0x%lx\n";
      goto LABEL_3;
    }
    v11 = *TokenInformation;
    v12 = RtlSubAuthorityCountSid(*TokenInformation);
    v13 = RtlSubAuthoritySid(v11, (unsigned int)*v12 - 1);
    v14 = v22;
    if ( v22 != *v13 )
    {
      LODWORD(ReturnLength) = v22;
      NlPrintDomRoutine(0x100u, a1, L"NlEnsureClientIsNamedUser: %ws: UserId mismatch 0x%lx\n", a2, ReturnLength);
      v15 = v11;
LABEL_17:
      NlpDumpSid(0x100u, v15);
      v7 = 5;
      goto LABEL_21;
    }
    v16 = RtlSubAuthorityCountSid(v11);
    --*v16;
    if ( !RtlEqualSid(*((PSID *)a1 + 23), v11) )
    {
      LODWORD(ReturnLength) = v14;
      NlPrintDomRoutine(0x100u, a1, L"NlEnsureClientIsNamedUser: %ws: DomainId mismatch 0x%lx\n", a2, ReturnLength);
      NlpDumpSid(0x100u, v11);
      v15 = (void *)*((_QWORD *)a1 + 23);
      goto LABEL_17;
    }
    v7 = 0;
  }
LABEL_21:
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( TokenInformation )
    NetpMemoryFree(TokenInformation);
  RpcRevertToSelf();
  return v7;
}

```

## disassembly

```asm
0x18002daa8  mov     r11, rsp
0x18002daab  mov     [r11+8], rbx
0x18002daaf  mov     [r11+10h], rsi
0x18002dab3  push    rbp
0x18002dab4  push    rdi
0x18002dab5  push    r14
0x18002dab7  mov     rbp, rsp
0x18002daba  sub     rsp, 50h
0x18002dabe  mov     qword ptr [r11-38h], 0
0x18002dac6  lea     rax, [rbp+arg_18]
0x18002daca  mov     [r11-40h], rax
0x18002dace  xor     r9d, r9d; unsigned int
0x18002dad1  xor     r8d, r8d; unsigned int
0x18002dad4  mov     qword ptr [r11-48h], 0
0x18002dadc  mov     rsi, rdx
0x18002dadf  mov     [rbp+TokenHandle], 0
0x18002dae7  mov     rdi, rcx
0x18002daea  mov     [rbp+TokenInformation], 0
0x18002daf2  mov     [rbp+TokenInformationLength], 0
0x18002daf9  mov     [rbp+arg_18], 0
0x18002db00  call    ?NlSamOpenNamedUser@@YAJPEAU_DOMAIN_INFO@@PEBGKKPEAPEAXPEAKPEAPEAU_USER_INTERNAL6_INFORMATION@@@Z; NlSamOpenNamedUser(_DOMAIN_INFO *,ushort const *,ulong,ulong,void * *,ulong *,_USER_INTERNAL6_INFORMATION * *)
0x18002db05  mov     ebx, eax
0x18002db07  test    eax, eax
0x18002db09  jns     short loc_18002DB34
0x18002db0b  lea     r8, aNlensureclient_5; "NlEnsureClientIsNamedUser: %ws: NlSamOp"...
0x18002db12  mov     r9, rsi
0x18002db15  mov     dword ptr [rsp+50h+ReturnLength], ebx
0x18002db19  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18002db1c  mov     ecx, 100h; unsigned int
0x18002db21  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002db26  mov     ecx, ebx; Status
0x18002db28  call    NetpNtStatusToApiStatus
0x18002db2d  mov     ebx, eax
0x18002db2f  jmp     loc_18002DCFA
0x18002db34  xor     ecx, ecx; BindingHandle
0x18002db36  call    cs:__imp_RpcImpersonateClient
0x18002db3d  nop     dword ptr [rax+rax+00h]
0x18002db42  mov     ebx, eax
0x18002db44  test    eax, eax
0x18002db46  jz      short loc_18002DB68
0x18002db48  mov     r9, rsi
0x18002db4b  mov     dword ptr [rsp+50h+ReturnLength], eax
0x18002db4f  lea     r8, aNlensureclient_3; "NlEnsureClientIsNamedUser: %ws: RpcImpe"...
0x18002db56  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18002db59  mov     ecx, 100h; unsigned int
0x18002db5e  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002db63  jmp     loc_18002DCFA
0x18002db68  mov     ebx, 8
0x18002db6d  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002db71  mov     edx, ebx; DesiredAccess
0x18002db73  mov     r8b, 1; OpenAsSelf
0x18002db76  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002db7d  call    cs:__imp_NtOpenThreadToken
0x18002db84  nop     dword ptr [rax+rax+00h]
0x18002db89  mov     r14d, eax
0x18002db8c  test    eax, eax
0x18002db8e  jns     short loc_18002DBB4
0x18002db90  lea     r8, aNlensureclient_0; "NlEnsureClientIsNamedUser: %ws: NtOpenT"...
0x18002db97  mov     r9, rsi
0x18002db9a  mov     dword ptr [rsp+50h+ReturnLength], r14d
0x18002db9f  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18002dba2  mov     ecx, 100h; unsigned int
0x18002dba7  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002dbac  mov     ecx, r14d
0x18002dbaf  jmp     loc_18002DB28
0x18002dbb4  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002dbb8  lea     rax, [rbp+TokenInformationLength]
0x18002dbbc  xor     r9d, r9d; TokenInformationLength
0x18002dbbf  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18002dbc4  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002dbc8  lea     edx, [r9+1]; TokenInformationClass
0x18002dbcc  call    cs:__imp_NtQueryInformationToken
0x18002dbd3  nop     dword ptr [rax+rax+00h]
0x18002dbd8  mov     r14d, eax
0x18002dbdb  cmp     eax, 0C0000023h
0x18002dbe0  jz      short loc_18002DBEB
0x18002dbe2  lea     r8, aNlensureclient_4; "NlEnsureClientIsNamedUser: %ws: NtOpenQ"...
0x18002dbe9  jmp     short loc_18002DB97
0x18002dbeb  mov     ecx, [rbp+TokenInformationLength]
0x18002dbee  call    NetpMemoryAllocate
0x18002dbf3  mov     [rbp+TokenInformation], rax
0x18002dbf7  test    rax, rax
0x18002dbfa  jz      loc_18002DCFA
0x18002dc00  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002dc04  lea     rax, [rbp+TokenInformationLength]
0x18002dc08  mov     r8, [rbp+TokenInformation]; TokenInformation
0x18002dc0c  mov     edx, 1; TokenInformationClass
0x18002dc11  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002dc15  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18002dc1a  call    cs:__imp_NtQueryInformationToken
0x18002dc21  nop     dword ptr [rax+rax+00h]
0x18002dc26  mov     ebx, eax
0x18002dc28  test    eax, eax
0x18002dc2a  jns     short loc_18002DC38
0x18002dc2c  lea     r8, aNlensureclient_2; "NlEnsureClientIsNamedUser: %ws: NtOpenQ"...
0x18002dc33  jmp     loc_18002DB12
0x18002dc38  mov     rax, [rbp+TokenInformation]
0x18002dc3c  mov     rbx, [rax]
0x18002dc3f  mov     rcx, rbx; Sid
0x18002dc42  call    cs:__imp_RtlSubAuthorityCountSid
0x18002dc49  nop     dword ptr [rax+rax+00h]
0x18002dc4e  mov     rcx, rbx; Sid
0x18002dc51  movzx   edx, byte ptr [rax]
0x18002dc54  dec     edx; SubAuthority
0x18002dc56  call    cs:__imp_RtlSubAuthoritySid
0x18002dc5d  nop     dword ptr [rax+rax+00h]
0x18002dc62  mov     r14d, [rbp+arg_18]
0x18002dc66  cmp     r14d, [rax]
0x18002dc69  jz      short loc_18002DC9B
0x18002dc6b  mov     r9, rsi
0x18002dc6e  mov     dword ptr [rsp+50h+ReturnLength], r14d
0x18002dc73  lea     r8, aNlensureclient_1; "NlEnsureClientIsNamedUser: %ws: UserId "...
0x18002dc7a  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18002dc7d  mov     ecx, 100h; unsigned int
0x18002dc82  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002dc87  mov     rdx, rbx; void *
0x18002dc8a  mov     ecx, 100h; unsigned int
0x18002dc8f  call    ?NlpDumpSid@@YAXKPEAX@Z; NlpDumpSid(ulong,void *)
0x18002dc94  mov     ebx, 5
0x18002dc99  jmp     short loc_18002DCFA
0x18002dc9b  mov     rcx, rbx; Sid
0x18002dc9e  call    cs:__imp_RtlSubAuthorityCountSid
0x18002dca5  nop     dword ptr [rax+rax+00h]
0x18002dcaa  mov     rdx, rbx; Sid2
0x18002dcad  dec     byte ptr [rax]
0x18002dcaf  mov     rcx, [rdi+0B8h]; Sid1
0x18002dcb6  call    cs:__imp_RtlEqualSid
0x18002dcbd  nop     dword ptr [rax+rax+00h]
0x18002dcc2  test    al, al
0x18002dcc4  jnz     short loc_18002DCF8
0x18002dcc6  mov     r9, rsi
0x18002dcc9  mov     dword ptr [rsp+50h+ReturnLength], r14d
0x18002dcce  lea     r8, aNlensureclient; "NlEnsureClientIsNamedUser: %ws: DomainI"...
0x18002dcd5  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18002dcd8  mov     ecx, 100h; unsigned int
0x18002dcdd  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002dce2  mov     rdx, rbx; void *
0x18002dce5  mov     ecx, 100h; unsigned int
0x18002dcea  call    ?NlpDumpSid@@YAXKPEAX@Z; NlpDumpSid(ulong,void *)
0x18002dcef  mov     rdx, [rdi+0B8h]
0x18002dcf6  jmp     short loc_18002DC8A
0x18002dcf8  xor     ebx, ebx
0x18002dcfa  mov     rcx, [rbp+TokenHandle]; Handle
0x18002dcfe  test    rcx, rcx
0x18002dd01  jz      short loc_18002DD0F
0x18002dd03  call    cs:__imp_NtClose
0x18002dd0a  nop     dword ptr [rax+rax+00h]
0x18002dd0f  mov     rcx, [rbp+TokenInformation]
0x18002dd13  test    rcx, rcx
0x18002dd16  jz      short loc_18002DD1D
0x18002dd18  call    NetpMemoryFree
0x18002dd1d  call    cs:__imp_RpcRevertToSelf
0x18002dd24  nop     dword ptr [rax+rax+00h]
0x18002dd29  mov     rsi, [rsp+50h+arg_8]
0x18002dd2e  mov     eax, ebx
0x18002dd30  mov     rbx, [rsp+50h+arg_0]
0x18002dd35  add     rsp, 50h
0x18002dd39  pop     r14
0x18002dd3b  pop     rdi
0x18002dd3c  pop     rbp
0x18002dd3d  retn
```
