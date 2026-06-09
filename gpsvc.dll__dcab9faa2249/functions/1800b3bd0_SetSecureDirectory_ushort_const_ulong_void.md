# SetSecureDirectory(ushort const *,ulong,void *)

- ea: `0x1800b3bd0`
- end: `0x1800b417f`
- name: `?SetSecureDirectory@@YAKPEBGKPEAX@Z`
- size: `1455`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800a1e20`

## callees

- `0x18001fdd0`
- `0x180033140`
- `0x1800756a0`
- `0x180075ec0`
- `0x18007d320`
- `0x1800b2424`
- `0x1800b2440`
- `0x1800b3404`
- `0x1800b3bd0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3c81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3f4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3fb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b40e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3c81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3f4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3fb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b40e2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b3e1b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b3e1b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b40d8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b40d8`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800b3f40`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800b3f40`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800b3e3d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800b3e3d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b3df4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b3dff`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b3e0c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b3df4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b3dff`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b3e0c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800b3fab`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800b3fab`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b3c77`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b3d2b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b3c77`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b3d2b`

## string_xrefs

- `0x1800b3ca2`: `SetSecureDirectory: failed to AllocateAndInitializeSid for System with error: %d.`
- `0x1800b3cd5`: `SetSecureDirectory: failed to AllocateAndInitializeSid for System with error: %d.`
- `0x1800b3d56`: `SetSecureDirectory: failed to AllocateAndInitializeSid for Administrators with error: %d.`
- `0x1800b3d7e`: `SetSecureDirectory: failed to AllocateAndInitializeSid for Administrators with error: %d.`
- `0x1800b3dc1`: `SetSecureDirectory: failed to GetUserSid with error: %d.`
- `0x1800b3de4`: `SetSecureDirectory: failed to GetUserSid with error: %d.`
- `0x1800b3e68`: `SetSecureDirectory: failed to InitializeAcl with error: %d.`
- `0x1800b3e8e`: `SetSecureDirectory: failed to InitializeAcl with error: %d.`
- `0x1800b3ecd`: `SetSecureDirectory: failed to AddACE for System with error: %d.`
- `0x1800b3ef3`: `SetSecureDirectory: failed to AddACE for System with error: %d.`
- `0x1800b3f6b`: `SetSecureDirectory: failed to InitializeSecurityDescriptor with error: %d.`
- `0x1800b3f91`: `SetSecureDirectory: failed to InitializeSecurityDescriptor with error: %d.`
- `0x1800b3fd6`: `SetSecureDirectory: failed to SetSecurityDescriptorDacl with error: %d.`
- `0x1800b3ffc`: `SetSecureDirectory: failed to SetSecurityDescriptorDacl with error: %d.`
- `0x1800b4035`: `SetSecureDirectory: failed to CheckAndCreateSubFolders for path %s with error: %d.`
- `0x1800b4068`: `SetSecureDirectory: failed to CheckAndCreateSubFolders for path %s with error: %d.`
- `0x1800b40a6`: `SetSecureDirectory: failed to SetFolderSecurity with error: %d.`
- `0x1800b40c4`: `SetSecureDirectory: failed to SetFolderSecurity with error: %d.`
- `0x1800b40ff`: `SetSecureDirectory: failed to SetFileAttributes with error: %d.`
- `0x1800b411d`: `SetSecureDirectory: failed to SetFileAttributes with error: %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SetSecureDirectory(const unsigned __int16 *a1, __int64 a2, void *a3)
{
  unsigned int LastError; // ebx
  void (*v6)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v7; // rdx
  const unsigned __int16 *v8; // rdx
  void *UserSid; // rax
  void *v10; // r15
  PSID v11; // rbx
  DWORD LengthSid; // edi
  DWORD v13; // ebx
  struct _ACL *v14; // rax
  struct _ACL *v15; // rdi
  PSID v17; // [rsp+60h] [rbp-29h] BYREF
  PSID pSid; // [rsp+68h] [rbp-21h] BYREF
  struct _ACL *v19; // [rsp+70h] [rbp-19h] BYREF
  void *v20; // [rsp+78h] [rbp-11h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+80h] [rbp-9h] BYREF
  __int64 v22; // [rsp+A0h] [rbp+17h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A8h] [rbp+1Fh] BYREF

  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v22 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  v17 = 0;
  v20 = 0;
  v19 = 0;
  if ( !a1 || !a3 )
  {
    LastError = 87;
    goto LABEL_80;
  }
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v17) )
    {
      UserSid = GetUserSid(a3);
      v10 = UserSid;
      v20 = UserSid;
      if ( UserSid )
      {
        v11 = v17;
        LengthSid = GetLengthSid(UserSid);
        LODWORD(v11) = GetLengthSid(v11) + LengthSid;
        v13 = GetLengthSid(pSid) + 32 + (_DWORD)v11;
        v14 = (struct _ACL *)LocalAlloc(0, v13);
        v15 = v14;
        v19 = v14;
        if ( !v14 )
        {
          LastError = 14;
          goto LABEL_80;
        }
        if ( InitializeAcl(v14, v13, 2u) )
        {
          LastError = AddACE(v15, 0, 0x1F01FFu, pSid);
          if ( LastError
            || (LastError = AddACE(v15, 1u, 0x1F01FFu, v17)) != 0
            || (LastError = AddACE(v15, 2u, 0xA0000000, v10)) != 0 )
          {
            if ( !*(_DWORD *)&g_dwDebugLevel )
              goto LABEL_80;
            v6 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              v7 = L"SetSecureDirectory: failed to AddACE for System with error: %d.";
              goto LABEL_7;
            }
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              v8 = L"SetSecureDirectory: failed to AddACE for System with error: %d.";
              goto LABEL_11;
            }
          }
          else if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
          {
            if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v15, 0) )
            {
              LastError = CheckAndCreateSubFolders(a1);
              if ( LastError )
              {
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(
                      2u,
                      L"SetSecureDirectory: failed to CheckAndCreateSubFolders for path %s with error: %d.",
                      a1,
                      LastError);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(
                      2u,
                      L"SetSecureDirectory: failed to CheckAndCreateSubFolders for path %s with error: %d.",
                      a1,
                      LastError);
                  }
                }
              }
              else
              {
                LastError = SetFolderSecurity(a1, pSecurityDescriptor);
                if ( LastError )
                {
                  if ( !*(_DWORD *)&g_dwDebugLevel )
                    goto LABEL_80;
                  v6 = g_lpDebugMsg;
                  if ( g_lpDebugMsg )
                  {
                    v7 = L"SetSecureDirectory: failed to SetFolderSecurity with error: %d.";
                    goto LABEL_7;
                  }
                  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    v8 = L"SetSecureDirectory: failed to SetFolderSecurity with error: %d.";
                    goto LABEL_11;
                  }
                }
                else if ( !SetFileAttributesW(a1, 4u) )
                {
                  LastError = GetLastError();
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    v6 = g_lpDebugMsg;
                    if ( g_lpDebugMsg )
                    {
                      v7 = L"SetSecureDirectory: failed to SetFileAttributes with error: %d.";
                      goto LABEL_7;
                    }
                    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      v8 = L"SetSecureDirectory: failed to SetFileAttributes with error: %d.";
                      goto LABEL_11;
                    }
                  }
                }
              }
            }
            else
            {
              LastError = GetLastError();
              if ( !*(_DWORD *)&g_dwDebugLevel )
                goto LABEL_80;
              v6 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                v7 = L"SetSecureDirectory: failed to SetSecurityDescriptorDacl with error: %d.";
                goto LABEL_7;
              }
              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                v8 = L"SetSecureDirectory: failed to SetSecurityDescriptorDacl with error: %d.";
                goto LABEL_11;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            if ( !*(_DWORD *)&g_dwDebugLevel )
              goto LABEL_80;
            v6 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              v7 = L"SetSecureDirectory: failed to InitializeSecurityDescriptor with error: %d.";
              goto LABEL_7;
            }
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              v8 = L"SetSecureDirectory: failed to InitializeSecurityDescriptor with error: %d.";
              goto LABEL_11;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          if ( !*(_DWORD *)&g_dwDebugLevel )
            goto LABEL_80;
          v6 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v7 = L"SetSecureDirectory: failed to InitializeAcl with error: %d.";
            goto LABEL_7;
          }
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v8 = L"SetSecureDirectory: failed to InitializeAcl with error: %d.";
            goto LABEL_11;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_80;
        v6 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v7 = L"SetSecureDirectory: failed to GetUserSid with error: %d.";
          goto LABEL_7;
        }
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v8 = L"SetSecureDirectory: failed to GetUserSid with error: %d.";
          goto LABEL_11;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_80;
      v6 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v7 = L"SetSecureDirectory: failed to AllocateAndInitializeSid for Administrators with error: %d.";
        goto LABEL_7;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v8 = L"SetSecureDirectory: failed to AllocateAndInitializeSid for Administrators with error: %d.";
        goto LABEL_11;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v6 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v7 = L"SetSecureDirectory: failed to AllocateAndInitializeSid for System with error: %d.";
LABEL_7:
        v6(2u, v7, LastError);
        goto LABEL_80;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v8 = L"SetSecureDirectory: failed to AllocateAndInitializeSid for System with error: %d.";
LABEL_11:
        RedirectDebugMsg(2u, v8, LastError);
      }
    }
  }
LABEL_80:
  XPtr<_ACL,&void * ACLFree(void *)>::~XPtr<_ACL,&void * ACLFree(void *)>((void **)&v19);
  XPtr<_SID,&void * SIDFree(void *)>::~XPtr<_SID,&void * SIDFree(void *)>(&v20);
  XPtr<_SID,&void * SIDFree(void *)>::~XPtr<_SID,&void * SIDFree(void *)>(&v17);
  XPtr<_SID,&void * SIDFree(void *)>::~XPtr<_SID,&void * SIDFree(void *)>(&pSid);
  return LastError;
}

```

## disassembly

```asm
0x1800b3bd0  mov     [rsp-8+arg_8], rbx
0x1800b3bd5  mov     [rsp-8+arg_18], rsi
0x1800b3bda  push    rbp
0x1800b3bdb  push    rdi
0x1800b3bdc  push    r12
0x1800b3bde  push    r14
0x1800b3be0  push    r15
0x1800b3be2  lea     rbp, [rsp-37h]
0x1800b3be7  sub     rsp, 0C0h
0x1800b3bee  mov     rax, cs:__security_cookie
0x1800b3bf5  xor     rax, rsp
0x1800b3bf8  mov     [rbp+57h+var_30], rax
0x1800b3bfc  mov     rbx, r8
0x1800b3bff  mov     r14, rcx
0x1800b3c02  xorps   xmm0, xmm0
0x1800b3c05  xor     eax, eax
0x1800b3c07  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x1800b3c0b  movups  [rbp+57h+var_50], xmm0
0x1800b3c0f  mov     [rbp+57h+var_40], rax
0x1800b3c13  xor     r12d, r12d
0x1800b3c16  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x1800b3c1a  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800b3c20  mov     [rbp+57h+var_78], r12
0x1800b3c24  mov     [rbp+57h+var_80], r12
0x1800b3c28  mov     [rbp+57h+var_68], r12
0x1800b3c2c  mov     [rbp+57h+var_70], r12
0x1800b3c30  test    rcx, rcx
0x1800b3c33  jz      loc_1800B4129
0x1800b3c39  test    rbx, rbx
0x1800b3c3c  jz      loc_1800B4129
0x1800b3c42  lea     rax, [rbp+57h+var_78]
0x1800b3c46  mov     [rsp+0E0h+pSid], rax; pSid
0x1800b3c4b  mov     [rsp+0E0h+nSubAuthority7], r12d; nSubAuthority7
0x1800b3c50  mov     [rsp+0E0h+nSubAuthority6], r12d; nSubAuthority6
0x1800b3c55  mov     [rsp+0E0h+nSubAuthority5], r12d; nSubAuthority5
0x1800b3c5a  mov     [rsp+0E0h+nSubAuthority4], r12d; nSubAuthority4
0x1800b3c5f  mov     [rsp+0E0h+nSubAuthority3], r12d; nSubAuthority3
0x1800b3c64  mov     [rsp+0E0h+nSubAuthority2], r12d; nSubAuthority2
0x1800b3c69  xor     r9d, r9d; nSubAuthority1
0x1800b3c6c  lea     r8d, [r12+12h]; nSubAuthority0
0x1800b3c71  mov     dl, 1; nSubAuthorityCount
0x1800b3c73  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800b3c77  call    cs:__imp_AllocateAndInitializeSid
0x1800b3c7d  test    eax, eax
0x1800b3c7f  jnz     short loc_1800B3CEE
0x1800b3c81  call    cs:__imp_GetLastError
0x1800b3c87  mov     ebx, eax
0x1800b3c89  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b3c90  jz      loc_1800B412E
0x1800b3c96  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b3c9d  test    rax, rax
0x1800b3ca0  jz      short loc_1800B3CBB
0x1800b3ca2  lea     rdx, aSetsecuredirec_4; "SetSecureDirectory: failed to AllocateA"...
0x1800b3ca9  lea     ecx, [r12+2]
0x1800b3cae  mov     r8d, ebx
0x1800b3cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3cb6  jmp     loc_1800B412E
0x1800b3cbb  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b3cc2  jz      loc_1800B412E
0x1800b3cc8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b3ccf  jz      loc_1800B412E
0x1800b3cd5  lea     rdx, aSetsecuredirec_4; "SetSecureDirectory: failed to AllocateA"...
0x1800b3cdc  mov     ecx, 2; unsigned int
0x1800b3ce1  mov     r8d, ebx
0x1800b3ce4  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b3ce9  jmp     loc_1800B412E
0x1800b3cee  lea     rax, [rbp+57h+var_80]
0x1800b3cf2  mov     [rsp+0E0h+pSid], rax; pSid
0x1800b3cf7  mov     [rsp+0E0h+nSubAuthority7], r12d; nSubAuthority7
0x1800b3cfc  mov     [rsp+0E0h+nSubAuthority6], r12d; nSubAuthority6
0x1800b3d01  mov     [rsp+0E0h+nSubAuthority5], r12d; nSubAuthority5
0x1800b3d06  mov     [rsp+0E0h+nSubAuthority4], r12d; nSubAuthority4
0x1800b3d0b  mov     [rsp+0E0h+nSubAuthority3], r12d; nSubAuthority3
0x1800b3d10  mov     [rsp+0E0h+nSubAuthority2], r12d; unsigned __int8
0x1800b3d15  mov     esi, 2
0x1800b3d1a  mov     r9d, 220h; nSubAuthority1
0x1800b3d20  lea     r8d, [rsi+1Eh]; nSubAuthority0
0x1800b3d24  mov     dl, sil; nSubAuthorityCount
0x1800b3d27  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800b3d2b  call    cs:__imp_AllocateAndInitializeSid
0x1800b3d31  test    eax, eax
0x1800b3d33  jnz     short loc_1800B3D8C
0x1800b3d35  call    cs:__imp_GetLastError
0x1800b3d3b  mov     ebx, eax
0x1800b3d3d  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b3d44  jz      loc_1800B412E
0x1800b3d4a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b3d51  test    rax, rax
0x1800b3d54  jz      short loc_1800B3D64
0x1800b3d56  lea     rdx, aSetsecuredirec_3; "SetSecureDirectory: failed to AllocateA"...
0x1800b3d5d  mov     ecx, esi
0x1800b3d5f  jmp     loc_1800B3CAE
0x1800b3d64  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b3d6b  jz      loc_1800B412E
0x1800b3d71  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b3d78  jz      loc_1800B412E
0x1800b3d7e  lea     rdx, aSetsecuredirec_3; "SetSecureDirectory: failed to AllocateA"...
0x1800b3d85  mov     ecx, esi
0x1800b3d87  jmp     loc_1800B3CE1
0x1800b3d8c  mov     rcx, rbx; TokenHandle
0x1800b3d8f  call    ?GetUserSid@@YAPEAXPEAX@Z; GetUserSid(void *)
0x1800b3d94  mov     r15, rax
0x1800b3d97  mov     [rbp+57h+var_68], rax
0x1800b3d9b  test    rax, rax
0x1800b3d9e  jnz     short loc_1800B3DED
0x1800b3da0  call    cs:__imp_GetLastError
0x1800b3da6  mov     ebx, eax
0x1800b3da8  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b3daf  jz      loc_1800B412E
0x1800b3db5  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b3dbc  test    rax, rax
0x1800b3dbf  jz      short loc_1800B3DCA
0x1800b3dc1  lea     rdx, aSetsecuredirec_6; "SetSecureDirectory: failed to GetUserSi"...
0x1800b3dc8  jmp     short loc_1800B3D5D
0x1800b3dca  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b3dd1  jz      loc_1800B412E
0x1800b3dd7  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b3dde  jz      loc_1800B412E
0x1800b3de4  lea     rdx, aSetsecuredirec_6; "SetSecureDirectory: failed to GetUserSi"...
0x1800b3deb  jmp     short loc_1800B3D85
0x1800b3ded  mov     rbx, [rbp+57h+var_80]
0x1800b3df1  mov     rcx, r15; pSid
0x1800b3df4  call    cs:__imp_GetLengthSid
0x1800b3dfa  mov     edi, eax
0x1800b3dfc  mov     rcx, rbx; pSid
0x1800b3dff  call    cs:__imp_GetLengthSid
0x1800b3e05  lea     ebx, [rax+rdi]
0x1800b3e08  mov     rcx, [rbp+57h+var_78]; pSid
0x1800b3e0c  call    cs:__imp_GetLengthSid
0x1800b3e12  add     eax, 20h ; ' '
0x1800b3e15  add     ebx, eax
0x1800b3e17  mov     edx, ebx; uBytes
0x1800b3e19  xor     ecx, ecx; uFlags
0x1800b3e1b  call    cs:__imp_LocalAlloc
0x1800b3e21  mov     rdi, rax
0x1800b3e24  mov     [rbp+57h+var_70], rax
0x1800b3e28  test    rax, rax
0x1800b3e2b  jnz     short loc_1800B3E35
0x1800b3e2d  lea     ebx, [rax+0Eh]
0x1800b3e30  jmp     loc_1800B412E
0x1800b3e35  mov     r8d, esi; dwAclRevision
0x1800b3e38  mov     edx, ebx; nAclLength
0x1800b3e3a  mov     rcx, rdi; pAcl
0x1800b3e3d  call    cs:__imp_InitializeAcl
0x1800b3e43  test    eax, eax
0x1800b3e45  jnz     short loc_1800B3E9A
0x1800b3e47  call    cs:__imp_GetLastError
0x1800b3e4d  mov     ebx, eax
0x1800b3e4f  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b3e56  jz      loc_1800B412E
0x1800b3e5c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b3e63  test    rax, rax
0x1800b3e66  jz      short loc_1800B3E74
0x1800b3e68  lea     rdx, aSetsecuredirec_7; "SetSecureDirectory: failed to Initializ"...
0x1800b3e6f  jmp     loc_1800B3D5D
0x1800b3e74  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b3e7b  jz      loc_1800B412E
0x1800b3e81  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b3e88  jz      loc_1800B412E
0x1800b3e8e  lea     rdx, aSetsecuredirec_7; "SetSecureDirectory: failed to Initializ"...
0x1800b3e95  jmp     loc_1800B3D85
0x1800b3e9a  mov     r9, [rbp+57h+var_78]; void *
0x1800b3e9e  xor     edx, edx; dwAceIndex
0x1800b3ea0  mov     r8d, 1F01FFh; unsigned int
0x1800b3ea6  mov     rcx, rdi; pAcl
0x1800b3ea9  call    ?AddACE@@YAKPEAU_ACL@@KKPEAXE@Z; AddACE(_ACL *,ulong,ulong,void *,uchar)
0x1800b3eae  mov     ebx, eax
0x1800b3eb0  test    eax, eax
0x1800b3eb2  jz      short loc_1800B3EFF
0x1800b3eb4  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b3ebb  jz      loc_1800B412E
0x1800b3ec1  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b3ec8  test    rax, rax
0x1800b3ecb  jz      short loc_1800B3ED9
0x1800b3ecd  lea     rdx, aSetsecuredirec_1; "SetSecureDirectory: failed to AddACE fo"...
0x1800b3ed4  jmp     loc_1800B3D5D
0x1800b3ed9  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b3ee0  jz      loc_1800B412E
0x1800b3ee6  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b3eed  jz      loc_1800B412E
0x1800b3ef3  lea     rdx, aSetsecuredirec_1; "SetSecureDirectory: failed to AddACE fo"...
0x1800b3efa  jmp     loc_1800B3D85
0x1800b3eff  mov     r9, [rbp+57h+var_80]; void *
0x1800b3f03  mov     edx, 1; dwAceIndex
0x1800b3f08  mov     r8d, 1F01FFh; unsigned int
0x1800b3f0e  mov     rcx, rdi; pAcl
0x1800b3f11  call    ?AddACE@@YAKPEAU_ACL@@KKPEAXE@Z; AddACE(_ACL *,ulong,ulong,void *,uchar)
0x1800b3f16  mov     ebx, eax
0x1800b3f18  test    eax, eax
0x1800b3f1a  jnz     short loc_1800B3EB4
0x1800b3f1c  mov     r9, r15; void *
0x1800b3f1f  mov     r8d, 0A0000000h; unsigned int
0x1800b3f25  mov     edx, esi; dwAceIndex
0x1800b3f27  mov     rcx, rdi; pAcl
0x1800b3f2a  call    ?AddACE@@YAKPEAU_ACL@@KKPEAXE@Z; AddACE(_ACL *,ulong,ulong,void *,uchar)
0x1800b3f2f  mov     ebx, eax
0x1800b3f31  test    eax, eax
0x1800b3f33  jnz     loc_1800B3EB4
0x1800b3f39  lea     edx, [rax+1]; dwRevision
0x1800b3f3c  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800b3f40  call    cs:__imp_InitializeSecurityDescriptor
0x1800b3f46  test    eax, eax
0x1800b3f48  jnz     short loc_1800B3F9D
0x1800b3f4a  call    cs:__imp_GetLastError
0x1800b3f50  mov     ebx, eax
0x1800b3f52  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b3f59  jz      loc_1800B412E
0x1800b3f5f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b3f66  test    rax, rax
0x1800b3f69  jz      short loc_1800B3F77
0x1800b3f6b  lea     rdx, aSetsecuredirec_0; "SetSecureDirectory: failed to Initializ"...
0x1800b3f72  jmp     loc_1800B3D5D
0x1800b3f77  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b3f7e  jz      loc_1800B412E
0x1800b3f84  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b3f8b  jz      loc_1800B412E
0x1800b3f91  lea     rdx, aSetsecuredirec_0; "SetSecureDirectory: failed to Initializ"...
0x1800b3f98  jmp     loc_1800B3D85
0x1800b3f9d  xor     r9d, r9d; bDaclDefaulted
0x1800b3fa0  mov     r8, rdi; pDacl
0x1800b3fa3  lea     edx, [r9+1]; bDaclPresent
0x1800b3fa7  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800b3fab  call    cs:__imp_SetSecurityDescriptorDacl
0x1800b3fb1  test    eax, eax
0x1800b3fb3  jnz     short loc_1800B4008
0x1800b3fb5  call    cs:__imp_GetLastError
0x1800b3fbb  mov     ebx, eax
0x1800b3fbd  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b3fc4  jz      loc_1800B412E
0x1800b3fca  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b3fd1  test    rax, rax
0x1800b3fd4  jz      short loc_1800B3FE2
0x1800b3fd6  lea     rdx, aSetsecuredirec; "SetSecureDirectory: failed to SetSecuri"...
0x1800b3fdd  jmp     loc_1800B3D5D
0x1800b3fe2  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b3fe9  jz      loc_1800B412E
0x1800b3fef  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b3ff6  jz      loc_1800B412E
0x1800b3ffc  lea     rdx, aSetsecuredirec; "SetSecureDirectory: failed to SetSecuri"...
0x1800b4003  jmp     loc_1800B3D85
0x1800b4008  mov     rcx, r14; unsigned __int16 *
0x1800b400b  call    ?CheckAndCreateSubFolders@@YAKPEBG@Z; CheckAndCreateSubFolders(ushort const *)
0x1800b4010  mov     ebx, eax
0x1800b4012  test    eax, eax
0x1800b4014  jz      short loc_1800B407B
0x1800b4016  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b401d  jz      loc_1800B412E
0x1800b4023  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b402a  test    rax, rax
0x1800b402d  jz      short loc_1800B4048
0x1800b402f  mov     r9d, ebx
0x1800b4032  mov     r8, r14
0x1800b4035  lea     rdx, aSetsecuredirec_8; "SetSecureDirectory: failed to CheckAndC"...
0x1800b403c  mov     ecx, esi
0x1800b403e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4043  jmp     loc_1800B412E
0x1800b4048  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b404f  jz      loc_1800B412E
0x1800b4055  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b405c  jz      loc_1800B412E
0x1800b4062  mov     r9d, ebx
0x1800b4065  mov     r8, r14
0x1800b4068  lea     rdx, aSetsecuredirec_8; "SetSecureDirectory: failed to CheckAndC"...
0x1800b406f  mov     ecx, esi; unsigned int
0x1800b4071  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4076  jmp     loc_1800B412E
0x1800b407b  lea     rdx, [rbp+57h+pSecurityDescriptor]; void *
0x1800b407f  mov     rcx, r14; unsigned __int16 *
0x1800b4082  call    ?SetFolderSecurity@@YAKPEBGPEAX@Z; SetFolderSecurity(ushort const *,void *)
0x1800b4087  mov     ebx, eax
0x1800b4089  test    eax, eax
0x1800b408b  jz      short loc_1800B40D0
0x1800b408d  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b4094  jz      loc_1800B412E
0x1800b409a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b40a1  test    rax, rax
0x1800b40a4  jz      short loc_1800B40B2
0x1800b40a6  lea     rdx, aSetsecuredirec_2; "SetSecureDirectory: failed to SetFolder"...
0x1800b40ad  jmp     loc_1800B3D5D
0x1800b40b2  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b40b9  jz      short loc_1800B412E
0x1800b40bb  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b40c2  jz      short loc_1800B412E
0x1800b40c4  lea     rdx, aSetsecuredirec_2; "SetSecureDirectory: failed to SetFolder"...
0x1800b40cb  jmp     loc_1800B3D85
0x1800b40d0  mov     edx, 4; dwFileAttributes
0x1800b40d5  mov     rcx, r14; lpFileName
0x1800b40d8  call    cs:__imp_SetFileAttributesW
0x1800b40de  test    eax, eax
0x1800b40e0  jnz     short loc_1800B412E
0x1800b40e2  call    cs:__imp_GetLastError
0x1800b40e8  mov     ebx, eax
0x1800b40ea  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b40f1  jz      short loc_1800B412E
0x1800b40f3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b40fa  test    rax, rax
0x1800b40fd  jz      short loc_1800B410B
0x1800b40ff  lea     rdx, aSetsecuredirec_5; "SetSecureDirectory: failed to SetFileAt"...
0x1800b4106  jmp     loc_1800B3D5D
0x1800b410b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
  ... truncated ...
```
