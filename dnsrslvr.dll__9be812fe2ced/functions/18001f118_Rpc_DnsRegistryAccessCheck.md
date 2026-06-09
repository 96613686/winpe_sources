# Rpc_DnsRegistryAccessCheck

- ea: `0x18001f118`
- end: `0x18001f301`
- name: `Rpc_DnsRegistryAccessCheck`
- size: `489`
- prototype: `__int64 __fastcall(DWORD DesiredAccess, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `17`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ece8`
- `0x18001ed50`
- `0x18001f094`
- `0x18002078c`
- `0x18004d514`
- `0x18004dfd4`
- `0x18004e054`
- `0x18004ed10`
- `0x18004f060`
- `0x18004f260`
- `0x18004f380`
- `0x18004f530`
- `0x18004f680`
- `0x18004f800`
- `0x18004f940`
- `0x18004faa0`
- `0x180050040`

## callees

- `0x18001f118`
- `0x180046ec0`
- `0x180086b1c`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18001f216`
- `RPCRT4!RpcRevertToSelf` at `0x18001f2b8`
- `RPCRT4!RpcRevertToSelf` at `0x18001f216`
- `RPCRT4!RpcRevertToSelf` at `0x18001f2b8`
- `RPCRT4!RpcImpersonateClient` at `0x18001f1a4`
- `RPCRT4!RpcImpersonateClient` at `0x18001f1a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f1fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f1fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f261`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f2ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f2ae`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f1ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f1ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f1d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f1d7`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001f257`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001f257`

## pseudocode

```c
__int64 __fastcall Rpc_DnsRegistryAccessCheck(DWORD DesiredAccess, PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  DWORD LastError; // eax
  unsigned int v5; // ebx
  int v6; // edi
  __int64 v7; // rdx
  HANDLE CurrentThread; // rax
  void *TokenHandle; // [rsp+40h] [rbp-19h] BYREF
  WINBOOL AccessStatus; // [rsp+48h] [rbp-11h] BYREF
  DWORD PrivilegeSetLength; // [rsp+4Ch] [rbp-Dh] BYREF
  DWORD GrantedAccess; // [rsp+50h] [rbp-9h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+58h] [rbp-1h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+68h] [rbp+Fh] BYREF

  AccessStatus = 0;
  GrantedAccess = 0;
  PrivilegeSetLength = 0;
  TokenHandle = 0;
  GenericMapping.GenericRead = 131097;
  GenericMapping.GenericExecute = 131097;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GenericMapping.GenericWrite = 131078;
  GenericMapping.GenericAll = 983103;
  if ( (xmmword_1800AB5A0 & 0x80u) != 0LL )
    WPP_SF_d(1031, 41, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, DesiredAccess);
  LastError = RpcImpersonateClient(0);
  v5 = LastError;
  if ( LastError )
  {
    v6 = 0;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_16;
    v7 = 42;
    goto LABEL_6;
  }
  CurrentThread = GetCurrentThread();
  v6 = 1;
  AccessStatus = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
  if ( AccessStatus )
  {
    RpcRevertToSelf();
    PrivilegeSetLength = 20;
    v6 = 0;
    if ( AccessCheck(
           pSecurityDescriptor,
           TokenHandle,
           DesiredAccess,
           &GenericMapping,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus) )
    {
      if ( (xmmword_1800AB5A0 & 0x80u) != 0LL )
        WPP_SF_d(1031, 45, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, (unsigned int)AccessStatus);
      v5 = AccessStatus == 0 ? 5 : 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        v7 = 44;
        goto LABEL_6;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v7 = 43;
LABEL_6:
      WPP_SF_d(1035, v7, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, LastError);
    }
  }
LABEL_16:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v6 )
    RpcRevertToSelf();
  if ( (xmmword_1800AB5A0 & 0x80u) != 0LL )
    WPP_SF_d(1031, 46, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18001f118  mov     [rsp-8+arg_10], rbx
0x18001f11d  push    rbp
0x18001f11e  push    rsi
0x18001f11f  push    rdi
0x18001f120  push    r12
0x18001f122  push    r14
0x18001f124  lea     rbp, [rsp-37h]
0x18001f129  sub     rsp, 90h
0x18001f130  mov     rax, cs:__security_cookie
0x18001f137  xor     rax, rsp
0x18001f13a  mov     [rbp+57h+var_30], rax
0x18001f13e  xor     eax, eax
0x18001f140  mov     [rbp+57h+var_68], 0
0x18001f147  mov     [rbp+57h+var_48.Privilege.Attributes], eax
0x18001f14a  xorps   xmm0, xmm0
0x18001f14d  mov     [rbp+57h+var_60], eax
0x18001f150  mov     r14, rdx
0x18001f153  mov     [rbp+57h+var_64], eax
0x18001f156  mov     esi, ecx
0x18001f158  mov     eax, 20019h
0x18001f15d  mov     [rbp+57h+TokenHandle], 0
0x18001f165  mov     [rbp+57h+GenericMapping.GenericRead], eax
0x18001f168  mov     [rbp+57h+GenericMapping.GenericExecute], eax
0x18001f16b  movups  xmmword ptr [rbp+57h+var_48.PrivilegeCount], xmm0
0x18001f16f  mov     [rbp+57h+GenericMapping.GenericWrite], 20006h
0x18001f176  mov     [rbp+57h+GenericMapping.GenericAll], 0F003Fh
0x18001f17d  cmp     byte ptr cs:xmmword_1800AB5A0, 0
0x18001f184  lea     r12, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids
0x18001f18b  jge     short loc_18001F1A2
0x18001f18d  mov     edx, 29h ; ')'
0x18001f192  mov     ecx, 407h
0x18001f197  mov     r9d, esi
0x18001f19a  mov     r8, r12
0x18001f19d  call    WPP_SF_d
0x18001f1a2  xor     ecx, ecx; BindingHandle
0x18001f1a4  call    cs:__imp_RpcImpersonateClient
0x18001f1aa  mov     ebx, eax
0x18001f1ac  test    eax, eax
0x18001f1ae  jz      short loc_18001F1D7
0x18001f1b0  xor     edi, edi
0x18001f1b2  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001f1b9  jz      loc_18001F2A5
0x18001f1bf  lea     edx, [rdi+2Ah]
0x18001f1c2  mov     ecx, 40Bh
0x18001f1c7  mov     r9d, eax
0x18001f1ca  mov     r8, r12
0x18001f1cd  call    WPP_SF_d
0x18001f1d2  jmp     loc_18001F2A5
0x18001f1d7  call    cs:__imp_GetCurrentThread
0x18001f1dd  mov     edi, 1
0x18001f1e2  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001f1e6  mov     rcx, rax; ThreadHandle
0x18001f1e9  mov     r8d, edi; OpenAsSelf
0x18001f1ec  lea     edx, [rdi+7]; DesiredAccess
0x18001f1ef  call    cs:__imp_OpenThreadToken
0x18001f1f5  mov     [rbp+57h+var_68], eax
0x18001f1f8  test    eax, eax
0x18001f1fa  jnz     short loc_18001F216
0x18001f1fc  call    cs:__imp_GetLastError
0x18001f202  mov     ebx, eax
0x18001f204  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001f20b  jz      loc_18001F2A5
0x18001f211  lea     edx, [rdi+2Ah]
0x18001f214  jmp     short loc_18001F1C2
0x18001f216  call    cs:__imp_RpcRevertToSelf
0x18001f21c  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x18001f220  lea     rax, [rbp+57h+var_68]
0x18001f224  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x18001f229  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18001f22d  lea     rax, [rbp+57h+var_60]
0x18001f231  mov     [rbp+57h+var_64], 14h
0x18001f238  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x18001f23d  mov     r8d, esi; DesiredAccess
0x18001f240  lea     rax, [rbp+57h+var_64]
0x18001f244  mov     rcx, r14; pSecurityDescriptor
0x18001f247  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18001f24c  xor     edi, edi
0x18001f24e  lea     rax, [rbp+57h+var_48]
0x18001f252  mov     [rsp+0B0h+PrivilegeSet], rax; PrivilegeSet
0x18001f257  call    cs:__imp_AccessCheck
0x18001f25d  test    eax, eax
0x18001f25f  jnz     short loc_18001F27A
0x18001f261  call    cs:__imp_GetLastError
0x18001f267  mov     ebx, eax
0x18001f269  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001f270  jz      short loc_18001F2A5
0x18001f272  lea     edx, [rdi+2Ch]
0x18001f275  jmp     loc_18001F1C2
0x18001f27a  cmp     byte ptr cs:xmmword_1800AB5A0, dil
0x18001f281  jge     short loc_18001F299
0x18001f283  mov     r9d, [rbp+57h+var_68]
0x18001f287  mov     edx, 2Dh ; '-'
0x18001f28c  mov     ecx, 407h
0x18001f291  mov     r8, r12
0x18001f294  call    WPP_SF_d
0x18001f299  mov     eax, [rbp+57h+var_68]
0x18001f29c  neg     eax
0x18001f29e  sbb     ebx, ebx
0x18001f2a0  not     ebx
0x18001f2a2  and     ebx, 5
0x18001f2a5  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18001f2a9  test    rcx, rcx
0x18001f2ac  jz      short loc_18001F2B4
0x18001f2ae  call    cs:__imp_CloseHandle
0x18001f2b4  test    edi, edi
0x18001f2b6  jz      short loc_18001F2BE
0x18001f2b8  call    cs:__imp_RpcRevertToSelf
0x18001f2be  cmp     byte ptr cs:xmmword_1800AB5A0, 0
0x18001f2c5  jge     short loc_18001F2DC
0x18001f2c7  mov     edx, 2Eh ; '.'
0x18001f2cc  mov     ecx, 407h
0x18001f2d1  mov     r9d, ebx
0x18001f2d4  mov     r8, r12
0x18001f2d7  call    WPP_SF_d
0x18001f2dc  mov     eax, ebx
0x18001f2de  mov     rcx, [rbp+57h+var_30]
0x18001f2e2  xor     rcx, rsp; StackCookie
0x18001f2e5  call    __security_check_cookie
0x18001f2ea  mov     rbx, [rsp+0B0h+arg_10]
0x18001f2f2  add     rsp, 90h
0x18001f2f9  pop     r14
0x18001f2fb  pop     r12
0x18001f2fd  pop     rdi
0x18001f2fe  pop     rsi
0x18001f2ff  pop     rbp
0x18001f300  retn
```
