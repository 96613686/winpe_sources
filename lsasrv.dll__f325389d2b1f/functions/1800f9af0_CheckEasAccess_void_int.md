# _CheckEasAccess(void *,int)

- ea: `0x1800f9af0`
- end: `0x1800f9dcd`
- name: `?_CheckEasAccess@@YAJPEAXH@Z`
- size: `733`
- prototype: `__int64 __fastcall(PSID SidToCheck, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800faef0`

## callees

- `0x180011278`
- `0x1800b86d0`
- `0x1800f9af0`
- `0x180139d5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9c0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9ccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9c0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9ccb`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800f9c60`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800f9c60`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800f9bfa`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800f9cbb`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800f9bfa`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800f9cbb`
- `ntdll!NtClose` at `0x1800f9d3e`
- `ntdll!NtClose` at `0x1800f9d3e`
- `ntdll!NtOpenThreadToken` at `0x1800f9bb6`
- `ntdll!NtOpenThreadToken` at `0x1800f9bb6`
- `RPCRT4!RpcRevertToSelf` at `0x1800f9d4f`
- `RPCRT4!RpcRevertToSelf` at `0x1800f9d4f`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800f9b3e`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800f9d5d`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800f9b3e`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800f9d5d`
- `RPCRT4!RpcImpersonateClient` at `0x1800f9b30`
- `RPCRT4!RpcImpersonateClient` at `0x1800f9b30`

## pseudocode

```c
__int64 __fastcall _CheckEasAccess(PSID SidToCheck, int a2)
{
  RPC_STATUS v4; // eax
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // r14d
  LsaHandleCache *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  NTSTATUS v11; // eax
  signed int v12; // eax
  signed int LastError; // eax
  signed int v14; // eax
  RPC_STATUS v15; // eax
  int v16; // edi
  WINBOOL IsMember; // [rsp+20h] [rbp-59h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-51h] BYREF
  DWORD cbSid[4]; // [rsp+30h] [rbp-49h] BYREF
  _BYTE pSid[80]; // [rsp+40h] [rbp-39h] BYREF

  IsMember = 0;
  cbSid[0] = 68;
  TokenHandle = 0;
  v4 = RpcImpersonateClient(0);
  v5 = I_RpcMapWin32Status(v4);
  v6 = v5;
  if ( v5 )
  {
    v7 = 0;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0xC0070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 10;
LABEL_7:
      v10 = v6;
LABEL_8:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_545c8b7f486339e055cd0f4d1a7ce3f2_Traceguids, v10);
      goto LABEL_40;
    }
    goto LABEL_40;
  }
  v7 = 1;
  v11 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  v6 = v11;
  if ( v11 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_40;
    v9 = 11;
    goto LABEL_13;
  }
  if ( !a2 || CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
  {
    if ( IsMember )
      goto LABEL_39;
    if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0xC0070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 13;
        goto LABEL_7;
      }
      goto LABEL_40;
    }
    if ( !CheckTokenMembership(TokenHandle, pSid, &IsMember) )
    {
      v14 = GetLastError();
      v6 = v14;
      if ( v14 > 0 )
        v6 = (unsigned __int16)v14 | 0xC0070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 14;
        goto LABEL_7;
      }
      goto LABEL_40;
    }
    if ( IsMember || (v11 = _CheckTCB(TokenHandle), v6 = v11, v11 >= 0) )
    {
LABEL_39:
      v6 = 0;
      goto LABEL_40;
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_40;
    v9 = 15;
LABEL_13:
    v10 = (unsigned int)v11;
    goto LABEL_8;
  }
  v12 = GetLastError();
  v6 = v12;
  if ( v12 > 0 )
    v6 = (unsigned __int16)v12 | 0xC0070000;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 12;
    goto LABEL_7;
  }
LABEL_40:
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( v7 )
  {
    v15 = RpcRevertToSelf();
    v16 = I_RpcMapWin32Status(v15);
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_545c8b7f486339e055cd0f4d1a7ce3f2_Traceguids, v6);
      if ( (v6 & 0x80000000) == 0 )
      {
        if ( v16 > 0 )
          return (unsigned __int16)v16 | 0xC0070000;
        else
          return (unsigned int)v16;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800f9af0  push    rbp
0x1800f9af2  push    rbx
0x1800f9af3  push    rsi
0x1800f9af4  push    rdi
0x1800f9af5  push    r13
0x1800f9af7  push    r14
0x1800f9af9  lea     rbp, [rsp-2Fh]
0x1800f9afe  sub     rsp, 0A8h
0x1800f9b05  mov     rax, cs:__security_cookie
0x1800f9b0c  xor     rax, rsp
0x1800f9b0f  mov     [rbp+57h+var_40], rax
0x1800f9b13  mov     rsi, rcx
0x1800f9b16  mov     [rbp+57h+IsMember], 0
0x1800f9b1d  xor     ecx, ecx; BindingHandle
0x1800f9b1f  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1800f9b26  mov     edi, edx
0x1800f9b28  mov     [rbp+57h+TokenHandle], 0
0x1800f9b30  call    cs:__imp_RpcImpersonateClient
0x1800f9b37  nop     dword ptr [rax+rax+00h]
0x1800f9b3c  mov     ecx, eax; Status
0x1800f9b3e  call    cs:__imp_I_RpcMapWin32Status
0x1800f9b45  nop     dword ptr [rax+rax+00h]
0x1800f9b4a  lea     r13, WPP_GLOBAL_Control
0x1800f9b51  mov     ebx, eax
0x1800f9b53  test    eax, eax
0x1800f9b55  jz      short loc_1800F9B9E
0x1800f9b57  xor     r14d, r14d
0x1800f9b5a  test    eax, eax
0x1800f9b5c  jle     short loc_1800F9B67
0x1800f9b5e  movzx   ebx, ax
0x1800f9b61  or      ebx, 0C0070000h
0x1800f9b67  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9b6e  cmp     rcx, r13
0x1800f9b71  jz      loc_1800F9D35
0x1800f9b77  test    byte ptr [rcx+1Ch], 1
0x1800f9b7b  jz      loc_1800F9D35
0x1800f9b81  mov     edx, 0Ah
0x1800f9b86  mov     r9d, ebx
0x1800f9b89  mov     rcx, [rcx+10h]
0x1800f9b8d  lea     r8, WPP_545c8b7f486339e055cd0f4d1a7ce3f2_Traceguids
0x1800f9b94  call    WPP_SF_d
0x1800f9b99  jmp     loc_1800F9D35
0x1800f9b9e  mov     r14d, 1
0x1800f9ba4  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800f9ba8  mov     r8b, r14b; OpenAsSelf
0x1800f9bab  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800f9bb2  lea     edx, [r14+7]; DesiredAccess
0x1800f9bb6  call    cs:__imp_NtOpenThreadToken
0x1800f9bbd  nop     dword ptr [rax+rax+00h]
0x1800f9bc2  mov     ebx, eax
0x1800f9bc4  test    eax, eax
0x1800f9bc6  jns     short loc_1800F9BEB
0x1800f9bc8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9bcf  cmp     rcx, r13
0x1800f9bd2  jz      loc_1800F9D35
0x1800f9bd8  test    [rcx+1Ch], r14b
0x1800f9bdc  jz      loc_1800F9D35
0x1800f9be2  lea     edx, [r14+0Ah]
0x1800f9be6  mov     r9d, eax
0x1800f9be9  jmp     short loc_1800F9B89
0x1800f9beb  test    edi, edi
0x1800f9bed  jz      short loc_1800F9C49
0x1800f9bef  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800f9bf3  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800f9bf7  mov     rdx, rsi; SidToCheck
0x1800f9bfa  call    cs:__imp_CheckTokenMembership
0x1800f9c01  nop     dword ptr [rax+rax+00h]
0x1800f9c06  test    eax, eax
0x1800f9c08  jnz     short loc_1800F9C49
0x1800f9c0a  call    cs:__imp_GetLastError
0x1800f9c11  nop     dword ptr [rax+rax+00h]
0x1800f9c16  mov     ebx, eax
0x1800f9c18  test    eax, eax
0x1800f9c1a  jle     short loc_1800F9C25
0x1800f9c1c  movzx   ebx, ax
0x1800f9c1f  or      ebx, 0C0070000h
0x1800f9c25  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9c2c  cmp     rcx, r13
0x1800f9c2f  jz      loc_1800F9D35
0x1800f9c35  test    [rcx+1Ch], r14b
0x1800f9c39  jz      loc_1800F9D35
0x1800f9c3f  mov     edx, 0Ch
0x1800f9c44  jmp     loc_1800F9B86
0x1800f9c49  cmp     [rbp+57h+IsMember], 0
0x1800f9c4d  jnz     loc_1800F9D33
0x1800f9c53  xor     edx, edx; DomainSid
0x1800f9c55  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800f9c59  lea     r8, [rbp+57h+pSid]; pSid
0x1800f9c5d  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800f9c60  call    cs:__imp_CreateWellKnownSid
0x1800f9c67  nop     dword ptr [rax+rax+00h]
0x1800f9c6c  test    eax, eax
0x1800f9c6e  jnz     short loc_1800F9CAF
0x1800f9c70  call    cs:__imp_GetLastError
0x1800f9c77  nop     dword ptr [rax+rax+00h]
0x1800f9c7c  mov     ebx, eax
0x1800f9c7e  test    eax, eax
0x1800f9c80  jle     short loc_1800F9C8B
0x1800f9c82  movzx   ebx, ax
0x1800f9c85  or      ebx, 0C0070000h
0x1800f9c8b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9c92  cmp     rcx, r13
0x1800f9c95  jz      loc_1800F9D35
0x1800f9c9b  test    [rcx+1Ch], r14b
0x1800f9c9f  jz      loc_1800F9D35
0x1800f9ca5  mov     edx, 0Dh
0x1800f9caa  jmp     loc_1800F9B86
0x1800f9caf  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800f9cb3  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800f9cb7  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x1800f9cbb  call    cs:__imp_CheckTokenMembership
0x1800f9cc2  nop     dword ptr [rax+rax+00h]
0x1800f9cc7  test    eax, eax
0x1800f9cc9  jnz     short loc_1800F9D02
0x1800f9ccb  call    cs:__imp_GetLastError
0x1800f9cd2  nop     dword ptr [rax+rax+00h]
0x1800f9cd7  mov     ebx, eax
0x1800f9cd9  test    eax, eax
0x1800f9cdb  jle     short loc_1800F9CE6
0x1800f9cdd  movzx   ebx, ax
0x1800f9ce0  or      ebx, 0C0070000h
0x1800f9ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9ced  cmp     rcx, r13
0x1800f9cf0  jz      short loc_1800F9D35
0x1800f9cf2  test    [rcx+1Ch], r14b
0x1800f9cf6  jz      short loc_1800F9D35
0x1800f9cf8  mov     edx, 0Eh
0x1800f9cfd  jmp     loc_1800F9B86
0x1800f9d02  cmp     [rbp+57h+IsMember], 0
0x1800f9d06  jnz     short loc_1800F9D33
0x1800f9d08  mov     rcx, [rbp+57h+TokenHandle]; void *
0x1800f9d0c  call    ?_CheckTCB@@YAJPEAX@Z; _CheckTCB(void *)
0x1800f9d11  mov     ebx, eax
0x1800f9d13  test    eax, eax
0x1800f9d15  jns     short loc_1800F9D33
0x1800f9d17  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9d1e  cmp     rcx, r13
0x1800f9d21  jz      short loc_1800F9D35
0x1800f9d23  test    [rcx+1Ch], r14b
0x1800f9d27  jz      short loc_1800F9D35
0x1800f9d29  mov     edx, 0Fh
0x1800f9d2e  jmp     loc_1800F9BE6
0x1800f9d33  xor     ebx, ebx
0x1800f9d35  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800f9d39  test    rcx, rcx
0x1800f9d3c  jz      short loc_1800F9D4A
0x1800f9d3e  call    cs:__imp_NtClose
0x1800f9d45  nop     dword ptr [rax+rax+00h]
0x1800f9d4a  test    r14d, r14d
0x1800f9d4d  jz      short loc_1800F9DAE
0x1800f9d4f  call    cs:__imp_RpcRevertToSelf
0x1800f9d56  nop     dword ptr [rax+rax+00h]
0x1800f9d5b  mov     ecx, eax; Status
0x1800f9d5d  call    cs:__imp_I_RpcMapWin32Status
0x1800f9d64  nop     dword ptr [rax+rax+00h]
0x1800f9d69  mov     edi, eax
0x1800f9d6b  test    eax, eax
0x1800f9d6d  jz      short loc_1800F9DAE
0x1800f9d6f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9d76  cmp     rcx, r13
0x1800f9d79  jz      short loc_1800F9D99
0x1800f9d7b  test    byte ptr [rcx+1Ch], 1
0x1800f9d7f  jz      short loc_1800F9D99
0x1800f9d81  mov     rcx, [rcx+10h]
0x1800f9d85  lea     r8, WPP_545c8b7f486339e055cd0f4d1a7ce3f2_Traceguids
0x1800f9d8c  mov     edx, 10h
0x1800f9d91  mov     r9d, ebx
0x1800f9d94  call    WPP_SF_d
0x1800f9d99  test    ebx, ebx
0x1800f9d9b  js      short loc_1800F9DAE
0x1800f9d9d  test    edi, edi
0x1800f9d9f  jg      short loc_1800F9DA5
0x1800f9da1  mov     ebx, edi
0x1800f9da3  jmp     short loc_1800F9DAE
0x1800f9da5  movzx   ebx, di
0x1800f9da8  or      ebx, 0C0070000h
0x1800f9dae  mov     eax, ebx
0x1800f9db0  mov     rcx, [rbp+57h+var_40]
0x1800f9db4  xor     rcx, rsp; StackCookie
0x1800f9db7  call    __security_check_cookie
0x1800f9dbc  add     rsp, 0A8h
0x1800f9dc3  pop     r14
0x1800f9dc5  pop     r13
0x1800f9dc7  pop     rdi
0x1800f9dc8  pop     rsi
0x1800f9dc9  pop     rbx
0x1800f9dca  pop     rbp
0x1800f9dcb  retn
```
