# ChangeDefaultTokenDacl(void *,void *)

- ea: `0x180035ecc`
- end: `0x180036122`
- name: `?ChangeDefaultTokenDacl@@YAJPEAX0@Z`
- size: `598`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID pSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180037234`

## callees

- `0x180035ecc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360cc`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180036032`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180036032`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180036052`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180036069`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180036083`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180036099`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180036052`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180036069`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180036083`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180036099`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800360b8`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800360b8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180035fd7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180035fe3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180035fef`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180035ffa`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180035fd7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180035fe3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180035fef`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180035ffa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003600c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003600c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036109`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036109`
- `iisutil!PuDbgPrintError` at `0x180035f4d`
- `iisutil!PuDbgPrintError` at `0x180035f4d`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x180035efe`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x180035f61`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x180035f9d`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x180035efe`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x180035f61`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x180035f9d`
- `iisutil!FreeWellKnownSid` at `0x1800360ec`
- `iisutil!FreeWellKnownSid` at `0x1800360f6`
- `iisutil!FreeWellKnownSid` at `0x180036100`
- `iisutil!FreeWellKnownSid` at `0x1800360ec`
- `iisutil!FreeWellKnownSid` at `0x1800360f6`
- `iisutil!FreeWellKnownSid` at `0x180036100`

## string_xrefs

- `0x180035f22`: `Error getting the SID for Local System\n`
- `0x180035f85`: `Error getting the SID for Administrators\n`
- `0x180035f42`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_config_store.cxx`
- `0x180035f36`: `ChangeDefaultTokenDacl`
- `0x180035fc1`: `Error getting the SID for CreatorOwner\n`

## pseudocode

```c
__int64 __fastcall ChangeDefaultTokenDacl(HANDLE TokenHandle, PSID pSid)
{
  struct _ACL *v2; // rdi
  int v5; // eax
  unsigned int v6; // ebx
  const char *v7; // rax
  __int64 v8; // r8
  int v9; // eax
  int v10; // eax
  DWORD LengthSid; // ebx
  DWORD v12; // ebx
  DWORD v13; // ebx
  DWORD v14; // ebx
  struct _ACL *v15; // rax
  signed int LastError; // eax
  PSID pSida; // [rsp+30h] [rbp-10h] BYREF
  struct _ACL *TokenInformation; // [rsp+38h] [rbp-8h] BYREF
  PSID v20; // [rsp+80h] [rbp+40h] BYREF
  PSID v21; // [rsp+88h] [rbp+48h] BYREF

  v2 = 0;
  v20 = 0;
  v21 = 0;
  pSida = 0;
  TokenInformation = 0;
  v5 = AllocateAndCreateWellKnownSid(WinLocalSystemSid, &v21);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v7 = "Error getting the SID for Local System\n";
      v8 = 1516;
LABEL_6:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
        v8,
        "ChangeDefaultTokenDacl",
        v6,
        v7);
    }
  }
  else
  {
    v9 = AllocateAndCreateWellKnownSid(WinBuiltinAdministratorsSid, &v20);
    v6 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v7 = "Error getting the SID for Administrators\n";
        v8 = 1529;
        goto LABEL_6;
      }
    }
    else
    {
      v10 = AllocateAndCreateWellKnownSid(WinCreatorOwnerRightsSid, &pSida);
      v6 = v10;
      if ( v10 )
      {
        if ( v10 > 0 )
          v6 = (unsigned __int16)v10 | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          v7 = "Error getting the SID for CreatorOwner\n";
          v8 = 1542;
          goto LABEL_6;
        }
      }
      else
      {
        LengthSid = GetLengthSid(pSida);
        v12 = GetLengthSid(v21) + LengthSid;
        v13 = GetLengthSid(v20) + v12;
        v14 = GetLengthSid(pSid) + 56 + v13;
        v15 = (struct _ACL *)LocalAlloc(0x40u, v14);
        v2 = v15;
        if ( v15 )
        {
          if ( !InitializeAcl(v15, v14, 2u)
            || !AddAccessAllowedAce(v2, 2u, 0x10000000u, v21)
            || !AddAccessAllowedAce(v2, 2u, 0x10000000u, v20)
            || !AddAccessAllowedAce(v2, 2u, 0x20000u, pSida)
            || !AddAccessAllowedAce(v2, 2u, 0x10000000u, pSid)
            || (v6 = 0, TokenInformation = v2,
                        !SetTokenInformation(TokenHandle, TokenDefaultDacl, &TokenInformation, 8u)) )
          {
            if ( GetLastError() )
            {
              LastError = GetLastError();
              v6 = LastError;
              if ( LastError > 0 )
                v6 = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              v6 = -2147467259;
            }
          }
        }
        else
        {
          v6 = -2147024888;
        }
      }
    }
  }
  FreeWellKnownSid(&v20);
  FreeWellKnownSid(&v21);
  FreeWellKnownSid(&pSida);
  LocalFree(v2);
  return v6;
}

```

## disassembly

```asm
0x180035ecc  mov     [rsp-28h+arg_0], rbx
0x180035ed1  push    rbp
0x180035ed2  push    rsi
0x180035ed3  push    rdi
0x180035ed4  push    r12
0x180035ed6  push    r14
0x180035ed8  mov     rbp, rsp
0x180035edb  sub     rsp, 40h
0x180035edf  xor     edi, edi
0x180035ee1  mov     rsi, rdx
0x180035ee4  mov     r14, rcx
0x180035ee7  mov     [rbp+arg_10], rdi
0x180035eeb  lea     rdx, [rbp+arg_18]
0x180035eef  mov     [rbp+arg_18], rdi
0x180035ef3  mov     [rbp+pSid], rdi
0x180035ef7  lea     ecx, [rdi+16h]
0x180035efa  mov     [rbp+TokenInformation], rdi
0x180035efe  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180035f04  mov     ebx, eax
0x180035f06  test    eax, eax
0x180035f08  jz      short loc_180035F58
0x180035f0a  jle     short loc_180035F15
0x180035f0c  movzx   ebx, ax
0x180035f0f  or      ebx, 80070000h
0x180035f15  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180035f1c  jz      loc_1800360E8
0x180035f22  lea     rax, aErrorGettingTh; "Error getting the SID for Local System"...
0x180035f29  mov     r8d, 5ECh
0x180035f2f  mov     rcx, cs:g_pDebug
0x180035f36  lea     r9, aChangedefaultt; "ChangeDefaultTokenDacl"
0x180035f3d  mov     [rsp+40h+var_18], rax
0x180035f42  lea     rdx, aServercommonIn_48; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180035f49  mov     [rsp+40h+var_20], ebx
0x180035f4d  call    cs:__imp_PuDbgPrintError
0x180035f53  jmp     loc_1800360E8
0x180035f58  lea     rdx, [rbp+arg_10]
0x180035f5c  mov     ecx, 1Ah
0x180035f61  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180035f67  mov     ebx, eax
0x180035f69  test    eax, eax
0x180035f6b  jz      short loc_180035F94
0x180035f6d  jle     short loc_180035F78
0x180035f6f  movzx   ebx, ax
0x180035f72  or      ebx, 80070000h
0x180035f78  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180035f7f  jz      loc_1800360E8
0x180035f85  lea     rax, aErrorGettingTh_0; "Error getting the SID for Administrator"...
0x180035f8c  mov     r8d, 5F9h
0x180035f92  jmp     short loc_180035F2F
0x180035f94  lea     rdx, [rbp+pSid]
0x180035f98  mov     ecx, 47h ; 'G'
0x180035f9d  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180035fa3  mov     ebx, eax
0x180035fa5  test    eax, eax
0x180035fa7  jz      short loc_180035FD3
0x180035fa9  jle     short loc_180035FB4
0x180035fab  movzx   ebx, ax
0x180035fae  or      ebx, 80070000h
0x180035fb4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180035fbb  jz      loc_1800360E8
0x180035fc1  lea     rax, aErrorGettingTh_2; "Error getting the SID for CreatorOwner"...
0x180035fc8  mov     r8d, 606h
0x180035fce  jmp     loc_180035F2F
0x180035fd3  mov     rcx, [rbp+pSid]; pSid
0x180035fd7  call    cs:__imp_GetLengthSid
0x180035fdd  mov     rcx, [rbp+arg_18]; pSid
0x180035fe1  mov     ebx, eax
0x180035fe3  call    cs:__imp_GetLengthSid
0x180035fe9  mov     rcx, [rbp+arg_10]; pSid
0x180035fed  add     ebx, eax
0x180035fef  call    cs:__imp_GetLengthSid
0x180035ff5  mov     rcx, rsi; pSid
0x180035ff8  add     ebx, eax
0x180035ffa  call    cs:__imp_GetLengthSid
0x180036000  add     eax, 38h ; '8'
0x180036003  mov     ecx, 40h ; '@'; uFlags
0x180036008  add     ebx, eax
0x18003600a  mov     edx, ebx; uBytes
0x18003600c  call    cs:__imp_LocalAlloc
0x180036012  mov     rdi, rax
0x180036015  test    rax, rax
0x180036018  jnz     short loc_180036024
0x18003601a  mov     ebx, 80070008h
0x18003601f  jmp     loc_1800360E8
0x180036024  mov     r12d, 2
0x18003602a  mov     edx, ebx; nAclLength
0x18003602c  mov     r8d, r12d; dwAclRevision
0x18003602f  mov     rcx, rdi; pAcl
0x180036032  call    cs:__imp_InitializeAcl
0x180036038  test    eax, eax
0x18003603a  jz      loc_1800360C2
0x180036040  mov     r9, [rbp+arg_18]; pSid
0x180036044  mov     ebx, 10000000h
0x180036049  mov     r8d, ebx; AccessMask
0x18003604c  mov     edx, r12d; dwAceRevision
0x18003604f  mov     rcx, rdi; pAcl
0x180036052  call    cs:__imp_AddAccessAllowedAce
0x180036058  test    eax, eax
0x18003605a  jz      short loc_1800360C2
0x18003605c  mov     r9, [rbp+arg_10]; pSid
0x180036060  mov     r8d, ebx; AccessMask
0x180036063  mov     edx, r12d; dwAceRevision
0x180036066  mov     rcx, rdi; pAcl
0x180036069  call    cs:__imp_AddAccessAllowedAce
0x18003606f  test    eax, eax
0x180036071  jz      short loc_1800360C2
0x180036073  mov     r9, [rbp+pSid]; pSid
0x180036077  mov     r8d, 20000h; AccessMask
0x18003607d  mov     edx, r12d; dwAceRevision
0x180036080  mov     rcx, rdi; pAcl
0x180036083  call    cs:__imp_AddAccessAllowedAce
0x180036089  test    eax, eax
0x18003608b  jz      short loc_1800360C2
0x18003608d  mov     r9, rsi; pSid
0x180036090  mov     r8d, ebx; AccessMask
0x180036093  mov     edx, r12d; dwAceRevision
0x180036096  mov     rcx, rdi; pAcl
0x180036099  call    cs:__imp_AddAccessAllowedAce
0x18003609f  test    eax, eax
0x1800360a1  jz      short loc_1800360C2
0x1800360a3  xor     ebx, ebx
0x1800360a5  mov     [rbp+TokenInformation], rdi
0x1800360a9  lea     r9d, [r12+6]; TokenInformationLength
0x1800360ae  mov     rcx, r14; TokenHandle
0x1800360b1  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800360b5  lea     edx, [rbx+6]; TokenInformationClass
0x1800360b8  call    cs:__imp_SetTokenInformation
0x1800360be  test    eax, eax
0x1800360c0  jnz     short loc_1800360E8
0x1800360c2  call    cs:__imp_GetLastError
0x1800360c8  test    eax, eax
0x1800360ca  jz      short loc_1800360E3
0x1800360cc  call    cs:__imp_GetLastError
0x1800360d2  mov     ebx, eax
0x1800360d4  test    eax, eax
0x1800360d6  jle     short loc_1800360E8
0x1800360d8  movzx   ebx, ax
0x1800360db  or      ebx, 80070000h
0x1800360e1  jmp     short loc_1800360E8
0x1800360e3  mov     ebx, 80004005h
0x1800360e8  lea     rcx, [rbp+arg_10]
0x1800360ec  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x1800360f2  lea     rcx, [rbp+arg_18]
0x1800360f6  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x1800360fc  lea     rcx, [rbp+pSid]
0x180036100  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x180036106  mov     rcx, rdi; hMem
0x180036109  call    cs:__imp_LocalFree
0x18003610f  mov     eax, ebx
0x180036111  mov     rbx, [rsp+40h+arg_0]
0x180036116  add     rsp, 40h
0x18003611a  pop     r14
0x18003611c  pop     r12
0x18003611e  pop     rdi
0x18003611f  pop     rsi
0x180036120  pop     rbp
0x180036121  retn
```
