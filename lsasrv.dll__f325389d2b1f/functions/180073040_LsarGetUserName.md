# LsarGetUserName

- ea: `0x180073040`
- end: `0x1800734ab`
- name: `LsarGetUserName`
- size: `1131`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180073040`
- `0x1800b86d0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007344a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007345a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073488`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073497`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007344a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007345a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073488`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073497`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180073190`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800731cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007320c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007324a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180073190`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800731cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007320c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007324a`
- `ntdll!NtClose` at `0x1800730f2`
- `ntdll!NtClose` at `0x1800730f2`
- `ntdll!RtlCopyUnicodeString` at `0x1800731ec`
- `ntdll!RtlCopyUnicodeString` at `0x180073269`
- `ntdll!RtlCopyUnicodeString` at `0x1800731ec`
- `ntdll!RtlCopyUnicodeString` at `0x180073269`
- `ntdll!RtlEqualSid` at `0x180073159`
- `ntdll!RtlEqualSid` at `0x180073159`
- `ntdll!NtQueryInformationToken` at `0x1800733f1`
- `ntdll!NtQueryInformationToken` at `0x1800733f1`
- `ntdll!NtOpenThreadToken` at `0x1800733a6`
- `ntdll!NtOpenThreadToken` at `0x1800733a6`
- `RPCRT4!RpcRevertToSelf` at `0x1800733b4`
- `RPCRT4!RpcRevertToSelf` at `0x1800733b4`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800730c4`
- `RPCRT4!I_RpcMapWin32Status` at `0x18007335e`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800733c2`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800730c4`
- `RPCRT4!I_RpcMapWin32Status` at `0x18007335e`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800733c2`
- `RPCRT4!RpcImpersonateClient` at `0x180073350`
- `RPCRT4!RpcImpersonateClient` at `0x180073350`
- `RPCRT4!I_RpcBindingInqClientTokenAttributes` at `0x1800730b6`
- `RPCRT4!I_RpcBindingInqClientTokenAttributes` at `0x1800730b6`

## pseudocode

```c
__int64 __fastcall LsarGetUserName(__int64 a1, HLOCAL *a2, HLOCAL *a3)
{
  RPC_STATUS v5; // eax
  int v6; // ebx
  DWORD LowPart; // r15d
  LONG HighPart; // r14d
  __int64 v9; // rax
  __int64 v10; // rsi
  void *v11; // rcx
  const UNICODE_STRING *v12; // rbx
  const UNICODE_STRING *v13; // r14
  struct _UNICODE_STRING *v14; // rax
  struct _UNICODE_STRING *v15; // r15
  WCHAR *v16; // rax
  struct _UNICODE_STRING *v17; // rax
  struct _UNICODE_STRING *v18; // r15
  WCHAR *v19; // rax
  RPC_STATUS v21; // eax
  int v22; // eax
  RPC_STATUS v23; // eax
  int v24; // eax
  void *v25; // rcx
  void *v26; // rcx
  LUID AuthenticationId; // [rsp+30h] [rbp-59h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-51h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v30[2]; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v31[2]; // [rsp+58h] [rbp-31h] BYREF
  _OWORD TokenInformation[3]; // [rsp+68h] [rbp-21h] BYREF
  __int64 v33; // [rsp+98h] [rbp+Fh]

  if ( !*a2 && (!a3 || !*a3) )
  {
    Handle = 0;
    ReturnLength = 0;
    v33 = 0;
    AuthenticationId = 0;
    memset(TokenInformation, 0, sizeof(TokenInformation));
    v5 = I_RpcBindingInqClientTokenAttributes(0, 0, &AuthenticationId, 0);
    v6 = I_RpcMapWin32Status(v5);
    if ( v6 >= 0 )
    {
LABEL_5:
      v30[0] = AuthenticationId;
      LowPart = AuthenticationId.LowPart;
      HighPart = AuthenticationId.HighPart;
      goto LABEL_6;
    }
    v21 = RpcImpersonateClient(0);
    v22 = I_RpcMapWin32Status(v21);
    v6 = v22;
    if ( v22 == -1073610687 )
    {
      AuthenticationId = (LUID)998LL;
    }
    else
    {
      if ( v22 != -1073610726 && v22 != -1073610686 )
      {
        if ( !v22 )
        {
          v6 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xAu, 1u, &Handle);
          v23 = RpcRevertToSelf();
          v24 = I_RpcMapWin32Status(v23);
          if ( v6 < 0 )
            goto LABEL_46;
          v6 = v24;
        }
        if ( v6 >= 0 )
        {
          v6 = NtQueryInformationToken(Handle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
          if ( v6 >= 0 )
          {
            AuthenticationId = (LUID)*((_QWORD *)&TokenInformation[0] + 1);
            goto LABEL_5;
          }
        }
LABEL_46:
        LowPart = 0;
        HighPart = 0;
LABEL_6:
        if ( Handle )
          NtClose(Handle);
        if ( v6 < 0 )
          goto LABEL_50;
        v30[0] = HighPart;
        v30[1] = LowPart;
        v9 = (*((__int64 (__fastcall **)(void *, _QWORD *))LogonSessionPackage + 9))(LogonSessionTable, v30);
        v10 = v9;
        if ( !v9 || (v11 = *(void **)(v9 + 224)) == 0 )
        {
          v6 = -1073741729;
          if ( !v9 )
            goto LABEL_50;
          goto LABEL_26;
        }
        if ( RtlEqualSid(v11, *((PSID *)WellKnownSids + 108)) )
        {
          v12 = (const UNICODE_STRING *)((char *)WellKnownSids + 880);
          v13 = (const UNICODE_STRING *)((char *)WellKnownSids + 896);
        }
        else if ( LowPart != 999 || HighPart )
        {
          v12 = (const UNICODE_STRING *)(v10 + 160);
          v13 = (const UNICODE_STRING *)(v10 + 176);
        }
        else
        {
          v12 = (const UNICODE_STRING *)((char *)WellKnownSids + 752);
          if ( *((_DWORD *)WellKnownSids + 182) != 3 )
            v12 = (const UNICODE_STRING *)((char *)WellKnownSids + 736);
          v13 = (const UNICODE_STRING *)((char *)WellKnownSids + 752);
        }
        v14 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 0x10u);
        *a2 = v14;
        v15 = v14;
        if ( !v14 )
          goto LABEL_29;
        *v14 = *v12;
        if ( v12->Buffer )
        {
          if ( v12->MaximumLength )
          {
            v16 = (WCHAR *)LocalAlloc(0x40u, v12->MaximumLength);
            v15->Buffer = v16;
            if ( !v16 )
              goto LABEL_29;
            RtlCopyUnicodeString(v15, v12);
          }
          else
          {
            v14->Buffer = 0;
          }
        }
        v6 = 0;
        if ( !a3 )
          goto LABEL_26;
        v17 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 0x10u);
        *a3 = v17;
        v18 = v17;
        if ( v17 )
        {
          *v17 = *v13;
          if ( !v13->Buffer )
            goto LABEL_26;
          if ( !v13->MaximumLength )
          {
            v17->Buffer = 0;
LABEL_26:
            v31[0] = *(int *)(v10 + 116);
            v31[1] = *(unsigned int *)(v10 + 112);
            (*((void (__fastcall **)(void *, _QWORD *))LogonSessionPackage + 10))(LogonSessionTable, v31);
            if ( v6 >= 0 )
              return (unsigned int)v6;
LABEL_50:
            if ( *a2 )
            {
              v25 = (void *)*((_QWORD *)*a2 + 1);
              if ( v25 )
                LocalFree(v25);
              LocalFree(*a2);
              *a2 = 0;
            }
            if ( a3 && *a3 )
            {
              v26 = (void *)*((_QWORD *)*a3 + 1);
              if ( v26 )
                LocalFree(v26);
              LocalFree(*a3);
              *a3 = 0;
            }
            return (unsigned int)v6;
          }
          v19 = (WCHAR *)LocalAlloc(0x40u, v13->MaximumLength);
          v18->Buffer = v19;
          if ( v19 )
          {
            RtlCopyUnicodeString(v18, v13);
            goto LABEL_26;
          }
        }
LABEL_29:
        v6 = -1073741670;
        goto LABEL_26;
      }
      AuthenticationId = LsapGlobalProcessTokenLuid;
    }
    v6 = 0;
    goto LABEL_5;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x180073040  mov     [rsp-8+arg_0], rbx
0x180073045  push    rbp
0x180073046  push    rsi
0x180073047  push    rdi
0x180073048  push    r12
0x18007304a  push    r13
0x18007304c  push    r14
0x18007304e  push    r15
0x180073050  lea     rbp, [rsp-27h]
0x180073055  sub     rsp, 0B0h
0x18007305c  mov     rax, cs:__security_cookie
0x180073063  xor     rax, rsp
0x180073066  mov     [rbp+57h+var_40], rax
0x18007306a  xor     r13d, r13d
0x18007306d  mov     rdi, r8
0x180073070  mov     r12, rdx
0x180073073  cmp     [rdx], r13
0x180073076  jnz     loc_180073302
0x18007307c  test    r8, r8
0x18007307f  jz      short loc_18007308A
0x180073081  cmp     [r8], r13
0x180073084  jnz     loc_180073302
0x18007308a  xorps   xmm0, xmm0
0x18007308d  mov     [rbp+57h+Handle], r13
0x180073091  xor     eax, eax
0x180073093  mov     [rbp+57h+var_A8], r13d
0x180073097  xor     r9d, r9d; ModifiedId
0x18007309a  mov     [rbp+57h+var_48], rax
0x18007309e  lea     r8, [rbp+57h+AuthenticationId]; AuthenticationId
0x1800730a2  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], r13
0x1800730a6  xor     edx, edx; TokenId
0x1800730a8  xor     ecx, ecx; Binding
0x1800730aa  movups  [rbp+57h+TokenInformation], xmm0
0x1800730ae  movups  [rbp+57h+var_68], xmm0
0x1800730b2  movups  [rbp+57h+var_58], xmm0
0x1800730b6  call    cs:__imp_I_RpcBindingInqClientTokenAttributes
0x1800730bd  nop     dword ptr [rax+rax+00h]
0x1800730c2  mov     ecx, eax; Status
0x1800730c4  call    cs:__imp_I_RpcMapWin32Status
0x1800730cb  nop     dword ptr [rax+rax+00h]
0x1800730d0  mov     ebx, eax
0x1800730d2  test    eax, eax
0x1800730d4  js      loc_18007334E
0x1800730da  mov     rax, qword ptr [rbp+57h+AuthenticationId.LowPart]
0x1800730de  mov     [rbp+57h+var_98], rax
0x1800730e2  mov     r15d, eax
0x1800730e5  mov     r14d, dword ptr [rbp+57h+var_98+4]
0x1800730e9  mov     rcx, [rbp+57h+Handle]; Handle
0x1800730ed  test    rcx, rcx
0x1800730f0  jz      short loc_1800730FE
0x1800730f2  call    cs:__imp_NtClose
0x1800730f9  nop     dword ptr [rax+rax+00h]
0x1800730fe  test    ebx, ebx
0x180073100  js      loc_180073438
0x180073106  mov     rcx, cs:?LogonSessionTable@@3PEAXEA; void * LogonSessionTable
0x18007310d  lea     rdx, [rbp+57h+var_98]
0x180073111  movsxd  rax, r14d
0x180073114  mov     [rbp+57h+var_98], rax
0x180073118  mov     eax, r15d
0x18007311b  mov     [rbp+57h+var_90], rax
0x18007311f  mov     rax, cs:?LogonSessionPackage@@3PEAU_HANDLE_PACKAGE@@EA; _HANDLE_PACKAGE * LogonSessionPackage
0x180073126  mov     rax, [rax+48h]
0x18007312a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007312f  mov     rsi, rax
0x180073132  test    rax, rax
0x180073135  jz      loc_180073277
0x18007313b  mov     rcx, [rax+0E0h]; Sid1
0x180073142  test    rcx, rcx
0x180073145  jz      loc_180073277
0x18007314b  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180073152  mov     rdx, [rdx+360h]; Sid2
0x180073159  call    cs:__imp_RtlEqualSid
0x180073160  nop     dword ptr [rax+rax+00h]
0x180073165  test    al, al
0x180073167  jnz     loc_1800732E1
0x18007316d  cmp     r15d, 3E7h
0x180073174  jz      loc_180073309
0x18007317a  lea     rbx, [rsi+0A0h]
0x180073181  lea     r14, [rsi+0B0h]
0x180073188  mov     edx, 10h; uBytes
0x18007318d  lea     ecx, [rdx+30h]; uFlags
0x180073190  call    cs:__imp_LocalAlloc
0x180073197  nop     dword ptr [rax+rax+00h]
0x18007319c  mov     [r12], rax
0x1800731a0  mov     r15, rax
0x1800731a3  test    rax, rax
0x1800731a6  jz      loc_1800732FB
0x1800731ac  movups  xmm0, xmmword ptr [rbx]
0x1800731af  movdqu  xmmword ptr [rax], xmm0
0x1800731b3  cmp     [rbx+8], r13
0x1800731b7  jz      short loc_1800731F8
0x1800731b9  cmp     [rbx+2], r13w
0x1800731be  jz      loc_18007333C
0x1800731c4  movzx   edx, word ptr [rbx+2]; uBytes
0x1800731c8  mov     ecx, 40h ; '@'; uFlags
0x1800731cd  call    cs:__imp_LocalAlloc
0x1800731d4  nop     dword ptr [rax+rax+00h]
0x1800731d9  mov     [r15+8], rax
0x1800731dd  test    rax, rax
0x1800731e0  jz      loc_1800732FB
0x1800731e6  mov     rdx, rbx; SourceString
0x1800731e9  mov     rcx, r15; DestinationString
0x1800731ec  call    cs:__imp_RtlCopyUnicodeString
0x1800731f3  nop     dword ptr [rax+rax+00h]
0x1800731f8  mov     ebx, r13d
0x1800731fb  test    rdi, rdi
0x1800731fe  jz      loc_180073285
0x180073204  mov     edx, 10h; uBytes
0x180073209  lea     ecx, [rdx+30h]; uFlags
0x18007320c  call    cs:__imp_LocalAlloc
0x180073213  nop     dword ptr [rax+rax+00h]
0x180073218  mov     [rdi], rax
0x18007321b  mov     r15, rax
0x18007321e  test    rax, rax
0x180073221  jz      loc_1800732FB
0x180073227  movups  xmm0, xmmword ptr [r14]
0x18007322b  movdqu  xmmword ptr [rax], xmm0
0x18007322f  cmp     [r14+8], r13
0x180073233  jz      short loc_180073285
0x180073235  cmp     [r14+2], r13w
0x18007323a  jz      loc_180073345
0x180073240  movzx   edx, word ptr [r14+2]; uBytes
0x180073245  mov     ecx, 40h ; '@'; uFlags
0x18007324a  call    cs:__imp_LocalAlloc
0x180073251  nop     dword ptr [rax+rax+00h]
0x180073256  mov     [r15+8], rax
0x18007325a  test    rax, rax
0x18007325d  jz      loc_1800732FB
0x180073263  mov     rdx, r14; SourceString
0x180073266  mov     rcx, r15; DestinationString
0x180073269  call    cs:__imp_RtlCopyUnicodeString
0x180073270  nop     dword ptr [rax+rax+00h]
0x180073275  jmp     short loc_180073285
0x180073277  mov     ebx, 0C000005Fh
0x18007327c  test    rsi, rsi
0x18007327f  jz      loc_180073438
0x180073285  movsxd  rax, dword ptr [rsi+74h]
0x180073289  lea     rdx, [rbp+57h+var_88]
0x18007328d  mov     rcx, cs:?LogonSessionTable@@3PEAXEA; void * LogonSessionTable
0x180073294  mov     [rbp+57h+var_88], rax
0x180073298  mov     eax, [rsi+70h]
0x18007329b  mov     [rbp+57h+var_80], rax
0x18007329f  mov     rax, cs:?LogonSessionPackage@@3PEAU_HANDLE_PACKAGE@@EA; _HANDLE_PACKAGE * LogonSessionPackage
0x1800732a6  mov     rax, [rax+50h]
0x1800732aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800732af  test    ebx, ebx
0x1800732b1  js      loc_180073438
0x1800732b7  mov     eax, ebx
0x1800732b9  mov     rcx, [rbp+57h+var_40]
0x1800732bd  xor     rcx, rsp; StackCookie
0x1800732c0  call    __security_check_cookie
0x1800732c5  mov     rbx, [rsp+0E0h+arg_0]
0x1800732cd  add     rsp, 0B0h
0x1800732d4  pop     r15
0x1800732d6  pop     r14
0x1800732d8  pop     r13
0x1800732da  pop     r12
0x1800732dc  pop     rdi
0x1800732dd  pop     rsi
0x1800732de  pop     rbp
0x1800732df  retn
0x1800732e1  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800732e8  lea     rbx, [rax+370h]
0x1800732ef  lea     r14, [rax+380h]
0x1800732f6  jmp     loc_180073188
0x1800732fb  mov     ebx, 0C000009Ah
0x180073300  jmp     short loc_180073285
0x180073302  mov     eax, 0C000000Dh
0x180073307  jmp     short loc_1800732B9
0x180073309  test    r14d, r14d
0x18007330c  jnz     loc_18007317A
0x180073312  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180073319  cmp     dword ptr [rax+2D8h], 3
0x180073320  lea     rbx, [rax+2F0h]
0x180073327  jz      short loc_180073330
0x180073329  lea     rbx, [rax+2E0h]
0x180073330  lea     r14, [rax+2F0h]
0x180073337  jmp     loc_180073188
0x18007333c  mov     [rax+8], r13
0x180073340  jmp     loc_1800731F8
0x180073345  mov     [rax+8], r13
0x180073349  jmp     loc_180073285
0x18007334e  xor     ecx, ecx; BindingHandle
0x180073350  call    cs:__imp_RpcImpersonateClient
0x180073357  nop     dword ptr [rax+rax+00h]
0x18007335c  mov     ecx, eax; Status
0x18007335e  call    cs:__imp_I_RpcMapWin32Status
0x180073365  nop     dword ptr [rax+rax+00h]
0x18007336a  mov     ebx, eax
0x18007336c  cmp     eax, 0C0020041h
0x180073371  jz      loc_18007342E
0x180073377  cmp     eax, 0C002001Ah
0x18007337c  jz      loc_18007341B
0x180073382  cmp     eax, 0C0020042h
0x180073387  jz      loc_18007341B
0x18007338d  mov     esi, 0Ah
0x180073392  test    eax, eax
0x180073394  jnz     short loc_1800733D4
0x180073396  lea     r9, [rbp+57h+Handle]; TokenHandle
0x18007339a  mov     r8b, 1; OpenAsSelf
0x18007339d  mov     edx, esi; DesiredAccess
0x18007339f  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800733a6  call    cs:__imp_NtOpenThreadToken
0x1800733ad  nop     dword ptr [rax+rax+00h]
0x1800733b2  mov     ebx, eax
0x1800733b4  call    cs:__imp_RpcRevertToSelf
0x1800733bb  nop     dword ptr [rax+rax+00h]
0x1800733c0  mov     ecx, eax; Status
0x1800733c2  call    cs:__imp_I_RpcMapWin32Status
0x1800733c9  nop     dword ptr [rax+rax+00h]
0x1800733ce  test    ebx, ebx
0x1800733d0  js      short loc_180073410
0x1800733d2  mov     ebx, eax
0x1800733d4  test    ebx, ebx
0x1800733d6  js      short loc_180073410
0x1800733d8  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x1800733dc  lea     rax, [rbp+57h+var_A8]
0x1800733e0  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800733e6  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800733eb  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800733ef  mov     edx, esi; TokenInformationClass
0x1800733f1  call    cs:__imp_NtQueryInformationToken
0x1800733f8  nop     dword ptr [rax+rax+00h]
0x1800733fd  mov     ebx, eax
0x1800733ff  test    eax, eax
0x180073401  js      short loc_180073410
0x180073403  mov     rax, qword ptr [rbp+57h+TokenInformation+8]
0x180073407  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], rax
0x18007340b  jmp     loc_1800730DA
0x180073410  mov     r15d, r13d
0x180073413  mov     r14d, r13d
0x180073416  jmp     loc_1800730E9
0x18007341b  mov     rax, cs:?LsapGlobalProcessTokenLuid@@3U_LUID@@A; _LUID LsapGlobalProcessTokenLuid
0x180073422  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], rax
0x180073426  mov     ebx, r13d
0x180073429  jmp     loc_1800730DA
0x18007342e  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], 3E6h
0x180073436  jmp     short loc_180073426
0x180073438  mov     rax, [r12]
0x18007343c  test    rax, rax
0x18007343f  jz      short loc_18007346A
0x180073441  mov     rcx, [rax+8]; hMem
0x180073445  test    rcx, rcx
0x180073448  jz      short loc_180073456
0x18007344a  call    cs:__imp_LocalFree
0x180073451  nop     dword ptr [rax+rax+00h]
0x180073456  mov     rcx, [r12]; hMem
0x18007345a  call    cs:__imp_LocalFree
0x180073461  nop     dword ptr [rax+rax+00h]
0x180073466  mov     [r12], r13
0x18007346a  test    rdi, rdi
0x18007346d  jz      loc_1800732B7
0x180073473  mov     rax, [rdi]
0x180073476  test    rax, rax
0x180073479  jz      loc_1800732B7
0x18007347f  mov     rcx, [rax+8]; hMem
0x180073483  test    rcx, rcx
0x180073486  jz      short loc_180073494
0x180073488  call    cs:__imp_LocalFree
0x18007348f  nop     dword ptr [rax+rax+00h]
0x180073494  mov     rcx, [rdi]; hMem
0x180073497  call    cs:__imp_LocalFree
0x18007349e  nop     dword ptr [rax+rax+00h]
0x1800734a3  mov     [rdi], r13
0x1800734a6  jmp     loc_1800732B7
```
