# CredrEnumerate

- ea: `0x18003f1d0`
- end: `0x18003f4d2`
- name: `CredrEnumerate`
- size: `770`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18003f1d0`
- `0x18003f4e0`
- `0x1800405d0`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bc2c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f42d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f42d`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18003f336`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18003f336`
- `ntdll!NtClose` at `0x18003f387`
- `ntdll!NtClose` at `0x18003f387`
- `ntdll!NtQueryInformationToken` at `0x18003f2c0`
- `ntdll!NtQueryInformationToken` at `0x18003f309`
- `ntdll!NtQueryInformationToken` at `0x18003f2c0`
- `ntdll!NtQueryInformationToken` at `0x18003f309`
- `ntdll!NtOpenThreadToken` at `0x18003f275`
- `ntdll!NtOpenThreadToken` at `0x18003f275`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18003f360`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18003f360`
- `RPCRT4!RpcRevertToSelf` at `0x18003f3cd`
- `RPCRT4!RpcRevertToSelf` at `0x18003f3cd`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003f244`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003f43b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003f454`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003f244`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003f43b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003f454`
- `RPCRT4!RpcImpersonateClient` at `0x18003f236`
- `RPCRT4!RpcImpersonateClient` at `0x18003f236`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditCredentialsRead` at `0x18003f3fb`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditCredentialsRead` at `0x18003f3fb`

## pseudocode

```c
__int64 __fastcall CredrEnumerate(__int64 a1, unsigned __int16 *a2, __int64 a3, _DWORD *a4)
{
  unsigned int v5; // r15d
  struct _ENCRYPTED_CREDENTIALW ***v7; // rsi
  RPC_STATUS v8; // eax
  int v9; // ebx
  RPC_STATUS IsClientLocal; // eax
  RPC_STATUS LastError; // eax
  ULONG ReturnLength; // [rsp+30h] [rbp-89h] BYREF
  int v14; // [rsp+34h] [rbp-85h] BYREF
  unsigned int ClientLocalFlag; // [rsp+38h] [rbp-81h] BYREF
  int v16; // [rsp+3Ch] [rbp-7Dh] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-79h] BYREF
  struct _LUID v18; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v19[12]; // [rsp+50h] [rbp-69h] BYREF
  _OWORD TokenInformation[3]; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v21; // [rsp+E0h] [rbp+27h]

  v18 = 0;
  v16 = 0;
  v5 = a3;
  if ( a1 )
  {
    v9 = -1073741534;
  }
  else
  {
    if ( a4 )
    {
      if ( !*a4 )
      {
        v7 = (struct _ENCRYPTED_CREDENTIALW ***)(a4 + 2);
        if ( !*((_QWORD *)a4 + 1) )
        {
          v8 = RpcImpersonateClient(0);
          v9 = I_RpcMapWin32Status(v8);
          if ( v9 < 0 )
            goto LABEL_19;
          TokenHandle = 0;
          v9 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
          if ( v9 < 0 )
            goto LABEL_18;
          v21 = 0;
          ReturnLength = 0;
          memset(TokenInformation, 0, sizeof(TokenInformation));
          v9 = NtQueryInformationToken(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
          if ( v9 < 0
            || (memset_0(v19, 0, 0x58u),
                v18 = (struct _LUID)*((_QWORD *)&TokenInformation[0] + 1),
                v9 = NtQueryInformationToken(TokenHandle, TokenUser, v19, 0x58u, &ReturnLength),
                v9 < 0) )
          {
LABEL_14:
            NtClose(TokenHandle);
            if ( v9 >= 0 )
            {
              v9 = CrediCheckLowboxAccess(&v16);
              if ( v9 >= 0 )
              {
                if ( v16 )
                {
                  v9 = CrediEnumerate(&v18, 0, a2, v5, a4, v7);
                }
                else
                {
                  v9 = -1073741790;
                  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_08198cd3b5a53ccc17f5f0a0fdceec60_Traceguids);
                  }
                }
              }
            }
LABEL_18:
            RpcRevertToSelf();
            goto LABEL_19;
          }
          v14 = 0;
          if ( !(unsigned int)CheckTokenMembershipEx(TokenHandle, v19[0], 2, &v14) )
          {
            LastError = GetLastError();
            v9 = I_RpcMapWin32Status(LastError);
            goto LABEL_14;
          }
          if ( v14 )
          {
            ClientLocalFlag = 0;
            IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
            if ( IsClientLocal )
            {
              v9 = I_RpcMapWin32Status(IsClientLocal);
              if ( v9 < 0 )
                goto LABEL_14;
            }
            else if ( !ClientLocalFlag )
            {
              goto LABEL_13;
            }
            v9 = 0;
            goto LABEL_14;
          }
LABEL_13:
          v9 = -1073741790;
          goto LABEL_14;
        }
      }
    }
    v9 = -1073741811;
  }
LABEL_19:
  if ( (unsigned __int8)IsLsapAdtInitParametersArrayPresent(a1, a2, a3) )
    LsapAdtAuditCredentialsRead(&v18, 8100, a2, 0, *a4, v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003f1d0  mov     [rsp-8+arg_0], rbx
0x18003f1d5  push    rbp
0x18003f1d6  push    rsi
0x18003f1d7  push    rdi
0x18003f1d8  push    r14
0x18003f1da  push    r15
0x18003f1dc  lea     rbp, [rsp-37h]
0x18003f1e1  sub     rsp, 0F0h
0x18003f1e8  mov     rax, cs:__security_cookie
0x18003f1ef  xor     rax, rsp
0x18003f1f2  mov     [rbp+57h+var_28], rax
0x18003f1f6  mov     qword ptr [rbp+57h+var_C8.LowPart], 0
0x18003f1fe  mov     rdi, r9
0x18003f201  mov     [rbp+57h+var_D4], 0
0x18003f208  mov     r15d, r8d
0x18003f20b  mov     r14, rdx
0x18003f20e  test    rcx, rcx
0x18003f211  jnz     loc_18003F485
0x18003f217  test    r9, r9
0x18003f21a  jz      loc_18003F47B
0x18003f220  cmp     [r9], ecx
0x18003f223  jnz     loc_18003F47B
0x18003f229  lea     rsi, [r9+8]
0x18003f22d  cmp     [rsi], rcx
0x18003f230  jnz     loc_18003F47B
0x18003f236  call    cs:__imp_RpcImpersonateClient
0x18003f23d  nop     dword ptr [rax+rax+00h]
0x18003f242  mov     ecx, eax; Status
0x18003f244  call    cs:__imp_I_RpcMapWin32Status
0x18003f24b  nop     dword ptr [rax+rax+00h]
0x18003f250  mov     ebx, eax
0x18003f252  test    eax, eax
0x18003f254  js      loc_18003F3D9
0x18003f25a  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18003f25e  mov     [rbp+57h+TokenHandle], 0
0x18003f266  mov     r8b, 1; OpenAsSelf
0x18003f269  mov     edx, 8; DesiredAccess
0x18003f26e  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18003f275  call    cs:__imp_NtOpenThreadToken
0x18003f27c  nop     dword ptr [rax+rax+00h]
0x18003f281  mov     ebx, eax
0x18003f283  test    eax, eax
0x18003f285  js      loc_18003F3CD
0x18003f28b  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18003f28f  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18003f293  xor     eax, eax
0x18003f295  xorps   xmm0, xmm0
0x18003f298  mov     r9d, 38h ; '8'; TokenInformationLength
0x18003f29e  mov     [rbp+57h+var_30], rax
0x18003f2a2  mov     [rsp+110h+var_E0], eax
0x18003f2a6  lea     rax, [rsp+110h+var_E0]
0x18003f2ab  movups  [rbp+57h+TokenInformation], xmm0
0x18003f2af  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x18003f2b4  lea     edx, [r9-2Eh]; TokenInformationClass
0x18003f2b8  movups  [rbp+57h+var_50], xmm0
0x18003f2bc  movups  [rbp+57h+var_40], xmm0
0x18003f2c0  call    cs:__imp_NtQueryInformationToken
0x18003f2c7  nop     dword ptr [rax+rax+00h]
0x18003f2cc  mov     ebx, eax
0x18003f2ce  test    eax, eax
0x18003f2d0  js      loc_18003F383
0x18003f2d6  mov     ebx, 58h ; 'X'
0x18003f2db  lea     rcx, [rbp+57h+var_C0]; void *
0x18003f2df  mov     r8d, ebx; Size
0x18003f2e2  xor     edx, edx; Val
0x18003f2e4  call    memset_0
0x18003f2e9  mov     rax, qword ptr [rbp+57h+TokenInformation+8]
0x18003f2ed  lea     r8, [rbp+57h+var_C0]; TokenInformation
0x18003f2f1  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18003f2f5  lea     edx, [rbx-57h]; TokenInformationClass
0x18003f2f8  mov     qword ptr [rbp+57h+var_C8.LowPart], rax
0x18003f2fc  mov     r9d, ebx; TokenInformationLength
0x18003f2ff  lea     rax, [rsp+110h+var_E0]
0x18003f304  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x18003f309  call    cs:__imp_NtQueryInformationToken
0x18003f310  nop     dword ptr [rax+rax+00h]
0x18003f315  mov     ebx, eax
0x18003f317  test    eax, eax
0x18003f319  js      short loc_18003F383
0x18003f31b  mov     rdx, [rbp+57h+var_C0]
0x18003f31f  lea     r9, [rsp+110h+var_DC]
0x18003f324  mov     rcx, [rbp+57h+TokenHandle]
0x18003f328  mov     r8d, 2
0x18003f32e  mov     [rsp+110h+var_DC], 0
0x18003f336  call    cs:__imp_CheckTokenMembershipEx
0x18003f33d  nop     dword ptr [rax+rax+00h]
0x18003f342  test    eax, eax
0x18003f344  jz      loc_18003F42D
0x18003f34a  cmp     [rsp+110h+var_DC], 0
0x18003f34f  jz      short loc_18003F37E
0x18003f351  lea     rdx, [rsp+110h+ClientLocalFlag]; ClientLocalFlag
0x18003f356  mov     [rsp+110h+ClientLocalFlag], 0
0x18003f35e  xor     ecx, ecx; BindingHandle
0x18003f360  call    cs:__imp_I_RpcBindingIsClientLocal
0x18003f367  nop     dword ptr [rax+rax+00h]
0x18003f36c  test    eax, eax
0x18003f36e  jnz     loc_18003F452
0x18003f374  cmp     [rsp+110h+ClientLocalFlag], eax
0x18003f378  jnz     loc_18003F44E
0x18003f37e  mov     ebx, 0C0000022h
0x18003f383  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18003f387  call    cs:__imp_NtClose
0x18003f38e  nop     dword ptr [rax+rax+00h]
0x18003f393  test    ebx, ebx
0x18003f395  js      short loc_18003F3CD
0x18003f397  lea     rcx, [rbp+57h+var_D4]; int *
0x18003f39b  call    ?CrediCheckLowboxAccess@@YAJPEAH@Z; CrediCheckLowboxAccess(int *)
0x18003f3a0  mov     ebx, eax
0x18003f3a2  test    eax, eax
0x18003f3a4  js      short loc_18003F3CD
0x18003f3a6  cmp     [rbp+57h+var_D4], 0
0x18003f3aa  jz      loc_18003F48F
0x18003f3b0  mov     [rsp+110h+var_E8], rsi; struct _ENCRYPTED_CREDENTIALW ***
0x18003f3b5  lea     rcx, [rbp+57h+var_C8]; struct _LUID *
0x18003f3b9  mov     r9d, r15d; unsigned int
0x18003f3bc  mov     [rsp+110h+ReturnLength], rdi; unsigned int *
0x18003f3c1  mov     r8, r14; unsigned __int16 *
0x18003f3c4  xor     edx, edx; unsigned int
0x18003f3c6  call    ?CrediEnumerate@@YAJPEAU_LUID@@KPEAGKPEAKPEAPEAPEAU_ENCRYPTED_CREDENTIALW@@@Z; CrediEnumerate(_LUID *,ulong,ushort *,ulong,ulong *,_ENCRYPTED_CREDENTIALW * * *)
0x18003f3cb  mov     ebx, eax
0x18003f3cd  call    cs:__imp_RpcRevertToSelf
0x18003f3d4  nop     dword ptr [rax+rax+00h]
0x18003f3d9  call    IsLsapAdtInitParametersArrayPresent
0x18003f3de  test    al, al
0x18003f3e0  jz      short loc_18003F407
0x18003f3e2  mov     eax, [rdi]
0x18003f3e4  lea     rcx, [rbp+57h+var_C8]
0x18003f3e8  mov     dword ptr [rsp+110h+var_E8], ebx
0x18003f3ec  xor     r9d, r9d
0x18003f3ef  mov     r8, r14
0x18003f3f2  mov     dword ptr [rsp+110h+ReturnLength], eax
0x18003f3f6  mov     edx, 1FA4h
0x18003f3fb  call    cs:__imp_LsapAdtAuditCredentialsRead
0x18003f402  nop     dword ptr [rax+rax+00h]
0x18003f407  mov     eax, ebx
0x18003f409  mov     rcx, [rbp+57h+var_28]
0x18003f40d  xor     rcx, rsp; StackCookie
0x18003f410  call    __security_check_cookie
0x18003f415  mov     rbx, [rsp+110h+arg_0]
0x18003f41d  add     rsp, 0F0h
0x18003f424  pop     r15
0x18003f426  pop     r14
0x18003f428  pop     rdi
0x18003f429  pop     rsi
0x18003f42a  pop     rbp
0x18003f42b  retn
0x18003f42d  call    cs:__imp_GetLastError
0x18003f434  nop     dword ptr [rax+rax+00h]
0x18003f439  mov     ecx, eax; Status
0x18003f43b  call    cs:__imp_I_RpcMapWin32Status
0x18003f442  nop     dword ptr [rax+rax+00h]
0x18003f447  mov     ebx, eax
0x18003f449  jmp     loc_18003F383
0x18003f44e  xor     al, al
0x18003f450  jmp     short loc_18003F46C
0x18003f452  mov     ecx, eax; Status
0x18003f454  call    cs:__imp_I_RpcMapWin32Status
0x18003f45b  nop     dword ptr [rax+rax+00h]
0x18003f460  mov     ebx, eax
0x18003f462  xor     al, al
0x18003f464  test    ebx, ebx
0x18003f466  js      loc_18003F383
0x18003f46c  test    al, al
0x18003f46e  jnz     loc_18003F37E
0x18003f474  xor     ebx, ebx
0x18003f476  jmp     loc_18003F383
0x18003f47b  mov     ebx, 0C000000Dh
0x18003f480  jmp     loc_18003F3D9
0x18003f485  mov     ebx, 0C0000122h
0x18003f48a  jmp     loc_18003F3D9
0x18003f48f  mov     ebx, 0C0000022h
0x18003f494  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f49b  lea     rax, WPP_GLOBAL_Control
0x18003f4a2  cmp     rcx, rax
0x18003f4a5  jz      loc_18003F3CD
0x18003f4ab  test    dword ptr [rcx+1Ch], 200h
0x18003f4b2  jz      loc_18003F3CD
0x18003f4b8  mov     rcx, [rcx+10h]
0x18003f4bc  lea     r8, WPP_08198cd3b5a53ccc17f5f0a0fdceec60_Traceguids
0x18003f4c3  mov     edx, 10h
0x18003f4c8  call    WPP_SF_
0x18003f4cd  jmp     loc_18003F3CD
```
