# NlEnsureClientIsNamedUser(_DOMAIN_INFO *,ushort *)

- ea: `0x18002c098`
- end: `0x18002c2ef`
- name: `?NlEnsureClientIsNamedUser@@YAKPEAU_DOMAIN_INFO@@PEAG@Z`
- size: `599`
- prototype: `unsigned int __fastcall(struct _DOMAIN_INFO *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180032ff0`

## callees

- `0x180003200`
- `0x180003670`
- `0x180007b50`
- `0x18000bd98`
- `0x18002c098`
- `0x180036cc8`
- `0x18003f3bc`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18002c126`
- `RPCRT4!RpcImpersonateClient` at `0x18002c126`
- `RPCRT4!RpcRevertToSelf` at `0x18002c2d4`
- `RPCRT4!RpcRevertToSelf` at `0x18002c2d4`
- `ntdll!NtOpenThreadToken` at `0x18002c167`
- `ntdll!NtOpenThreadToken` at `0x18002c167`
- `ntdll!NtQueryInformationToken` at `0x18002c1ad`
- `ntdll!NtQueryInformationToken` at `0x18002c1f5`
- `ntdll!NtQueryInformationToken` at `0x18002c1ad`
- `ntdll!NtQueryInformationToken` at `0x18002c1f5`
- `ntdll!RtlSubAuthoritySid` at `0x18002c225`
- `ntdll!RtlSubAuthoritySid` at `0x18002c225`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002c217`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002c267`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002c217`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002c267`
- `ntdll!NtClose` at `0x18002c2c0`
- `ntdll!NtClose` at `0x18002c2c0`
- `ntdll!RtlEqualSid` at `0x18002c279`
- `ntdll!RtlEqualSid` at `0x18002c279`

## string_xrefs

- `0x18002c0fb`: `NlEnsureClientIsNamedUser: %ws: NlSamOpenNamedUser failed 0x%lx\n`
- `0x18002c139`: `NlEnsureClientIsNamedUser: %ws: RpcImpersonateClient failed 0x%lx\n`
- `0x18002c174`: `NlEnsureClientIsNamedUser: %ws: NtOpenThreadToken failed 0x%lx\n`
- `0x18002c1bd`: `NlEnsureClientIsNamedUser: %ws: NtOpenQueryInformationThread failed 0x%lx\n`
- `0x18002c201`: `NlEnsureClientIsNamedUser: %ws: NtOpenQueryInformationThread (again) failed 0x%lx\n`

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
0x18002c098  mov     r11, rsp
0x18002c09b  mov     [r11+8], rbx
0x18002c09f  mov     [r11+10h], rsi
0x18002c0a3  push    rbp
0x18002c0a4  push    rdi
0x18002c0a5  push    r14
0x18002c0a7  mov     rbp, rsp
0x18002c0aa  sub     rsp, 50h
0x18002c0ae  mov     qword ptr [r11-38h], 0
0x18002c0b6  lea     rax, [rbp+arg_18]
0x18002c0ba  mov     [r11-40h], rax
0x18002c0be  xor     r9d, r9d; unsigned int
0x18002c0c1  xor     r8d, r8d; unsigned int
0x18002c0c4  mov     qword ptr [r11-48h], 0
0x18002c0cc  mov     rsi, rdx
0x18002c0cf  mov     [rbp+TokenHandle], 0
0x18002c0d7  mov     rdi, rcx
0x18002c0da  mov     [rbp+TokenInformation], 0
0x18002c0e2  mov     [rbp+TokenInformationLength], 0
0x18002c0e9  mov     [rbp+arg_18], 0
0x18002c0f0  call    ?NlSamOpenNamedUser@@YAJPEAU_DOMAIN_INFO@@PEBGKKPEAPEAXPEAKPEAPEAU_USER_INTERNAL6_INFORMATION@@@Z; NlSamOpenNamedUser(_DOMAIN_INFO *,ushort const *,ulong,ulong,void * *,ulong *,_USER_INTERNAL6_INFORMATION * *)
0x18002c0f5  mov     ebx, eax
0x18002c0f7  test    eax, eax
0x18002c0f9  jns     short loc_18002C124
0x18002c0fb  lea     r8, aNlensureclient_5; "NlEnsureClientIsNamedUser: %ws: NlSamOp"...
0x18002c102  mov     r9, rsi
0x18002c105  mov     dword ptr [rsp+50h+ReturnLength], ebx
0x18002c109  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18002c10c  mov     ecx, 100h; unsigned int
0x18002c111  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002c116  mov     ecx, ebx; Status
0x18002c118  call    NetpNtStatusToApiStatus
0x18002c11d  mov     ebx, eax
0x18002c11f  jmp     loc_18002C2B7
0x18002c124  xor     ecx, ecx; BindingHandle
0x18002c126  call    cs:__imp_RpcImpersonateClient
0x18002c12c  mov     ebx, eax
0x18002c12e  test    eax, eax
0x18002c130  jz      short loc_18002C152
0x18002c132  mov     r9, rsi
0x18002c135  mov     dword ptr [rsp+50h+ReturnLength], eax
0x18002c139  lea     r8, aNlensureclient_3; "NlEnsureClientIsNamedUser: %ws: RpcImpe"...
0x18002c140  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18002c143  mov     ecx, 100h; unsigned int
0x18002c148  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002c14d  jmp     loc_18002C2B7
0x18002c152  mov     ebx, 8
0x18002c157  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002c15b  mov     edx, ebx; DesiredAccess
0x18002c15d  mov     r8b, 1; OpenAsSelf
0x18002c160  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002c167  call    cs:__imp_NtOpenThreadToken
0x18002c16d  mov     r14d, eax
0x18002c170  test    eax, eax
0x18002c172  jns     short loc_18002C195
0x18002c174  lea     r8, aNlensureclient_0; "NlEnsureClientIsNamedUser: %ws: NtOpenT"...
0x18002c17b  mov     r9, rsi
0x18002c17e  mov     dword ptr [rsp+50h+ReturnLength], r14d
0x18002c183  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18002c186  mov     ecx, 100h; unsigned int
0x18002c18b  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002c190  mov     ecx, r14d
0x18002c193  jmp     short loc_18002C118
0x18002c195  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002c199  lea     rax, [rbp+TokenInformationLength]
0x18002c19d  xor     r9d, r9d; TokenInformationLength
0x18002c1a0  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18002c1a5  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002c1a9  lea     edx, [r9+1]; TokenInformationClass
0x18002c1ad  call    cs:__imp_NtQueryInformationToken
0x18002c1b3  mov     r14d, eax
0x18002c1b6  cmp     eax, 0C0000023h
0x18002c1bb  jz      short loc_18002C1C6
0x18002c1bd  lea     r8, aNlensureclient_4; "NlEnsureClientIsNamedUser: %ws: NtOpenQ"...
0x18002c1c4  jmp     short loc_18002C17B
0x18002c1c6  mov     ecx, [rbp+TokenInformationLength]
0x18002c1c9  call    NetpMemoryAllocate
0x18002c1ce  mov     [rbp+TokenInformation], rax
0x18002c1d2  test    rax, rax
0x18002c1d5  jz      loc_18002C2B7
0x18002c1db  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002c1df  lea     rax, [rbp+TokenInformationLength]
0x18002c1e3  mov     r8, [rbp+TokenInformation]; TokenInformation
0x18002c1e7  mov     edx, 1; TokenInformationClass
0x18002c1ec  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002c1f0  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18002c1f5  call    cs:__imp_NtQueryInformationToken
0x18002c1fb  mov     ebx, eax
0x18002c1fd  test    eax, eax
0x18002c1ff  jns     short loc_18002C20D
0x18002c201  lea     r8, aNlensureclient_2; "NlEnsureClientIsNamedUser: %ws: NtOpenQ"...
0x18002c208  jmp     loc_18002C102
0x18002c20d  mov     rax, [rbp+TokenInformation]
0x18002c211  mov     rbx, [rax]
0x18002c214  mov     rcx, rbx; Sid
0x18002c217  call    cs:__imp_RtlSubAuthorityCountSid
0x18002c21d  mov     rcx, rbx; Sid
0x18002c220  movzx   edx, byte ptr [rax]
0x18002c223  dec     edx; SubAuthority
0x18002c225  call    cs:__imp_RtlSubAuthoritySid
0x18002c22b  mov     r14d, [rbp+arg_18]
0x18002c22f  cmp     r14d, [rax]
0x18002c232  jz      short loc_18002C264
0x18002c234  mov     r9, rsi
0x18002c237  mov     dword ptr [rsp+50h+ReturnLength], r14d
0x18002c23c  lea     r8, aNlensureclient_1; "NlEnsureClientIsNamedUser: %ws: UserId "...
0x18002c243  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18002c246  mov     ecx, 100h; unsigned int
0x18002c24b  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002c250  mov     rdx, rbx; void *
0x18002c253  mov     ecx, 100h; unsigned int
0x18002c258  call    ?NlpDumpSid@@YAXKPEAX@Z; NlpDumpSid(ulong,void *)
0x18002c25d  mov     ebx, 5
0x18002c262  jmp     short loc_18002C2B7
0x18002c264  mov     rcx, rbx; Sid
0x18002c267  call    cs:__imp_RtlSubAuthorityCountSid
0x18002c26d  mov     rdx, rbx; Sid2
0x18002c270  dec     byte ptr [rax]
0x18002c272  mov     rcx, [rdi+0B8h]; Sid1
0x18002c279  call    cs:__imp_RtlEqualSid
0x18002c27f  test    al, al
0x18002c281  jnz     short loc_18002C2B5
0x18002c283  mov     r9, rsi
0x18002c286  mov     dword ptr [rsp+50h+ReturnLength], r14d
0x18002c28b  lea     r8, aNlensureclient; "NlEnsureClientIsNamedUser: %ws: DomainI"...
0x18002c292  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18002c295  mov     ecx, 100h; unsigned int
0x18002c29a  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002c29f  mov     rdx, rbx; void *
0x18002c2a2  mov     ecx, 100h; unsigned int
0x18002c2a7  call    ?NlpDumpSid@@YAXKPEAX@Z; NlpDumpSid(ulong,void *)
0x18002c2ac  mov     rdx, [rdi+0B8h]
0x18002c2b3  jmp     short loc_18002C253
0x18002c2b5  xor     ebx, ebx
0x18002c2b7  mov     rcx, [rbp+TokenHandle]; Handle
0x18002c2bb  test    rcx, rcx
0x18002c2be  jz      short loc_18002C2C6
0x18002c2c0  call    cs:__imp_NtClose
0x18002c2c6  mov     rcx, [rbp+TokenInformation]
0x18002c2ca  test    rcx, rcx
0x18002c2cd  jz      short loc_18002C2D4
0x18002c2cf  call    NetpMemoryFree
0x18002c2d4  call    cs:__imp_RpcRevertToSelf
0x18002c2da  mov     rsi, [rsp+50h+arg_8]
0x18002c2df  mov     eax, ebx
0x18002c2e1  mov     rbx, [rsp+50h+arg_0]
0x18002c2e6  add     rsp, 50h
0x18002c2ea  pop     r14
0x18002c2ec  pop     rdi
0x18002c2ed  pop     rbp
0x18002c2ee  retn
```
