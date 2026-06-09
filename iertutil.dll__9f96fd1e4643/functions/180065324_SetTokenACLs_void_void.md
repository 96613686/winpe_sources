# SetTokenACLs(void *,void *)

- ea: `0x180065324`
- end: `0x18006558f`
- name: `?SetTokenACLs@@YAHPEAX0@Z`
- size: `619`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, HANDLE)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180064c0c`

## callees

- `0x1800649d0`
- `0x180064a9c`
- `0x1800650b0`
- `0x180065324`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800653c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800654ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800653c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800654ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006555f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006555f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800653d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800653f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006551e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065537`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800653d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800653f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006551e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065537`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006552c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065545`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006552c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180065545`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006554e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065557`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006554e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065557`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180065513`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180065513`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800653bc`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800653bc`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180065439`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800654d4`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800654f6`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180065439`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800654d4`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800654f6`

## pseudocode

```c
__int64 __fastcall SetTokenACLs(HANDLE TokenHandle, HANDLE a2)
{
  unsigned int v4; // r13d
  PACL v5; // r14
  struct _ACL *v6; // r15
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  int TokenInformation_Heap; // eax
  HANDLE v10; // rax
  int v11; // eax
  __int64 v12; // r9
  __int64 v13; // r9
  DWORD v14; // eax
  DWORD v15; // eax
  int v17; // [rsp+60h] [rbp-29h] BYREF
  PSID *v18; // [rsp+68h] [rbp-21h]
  PACL *v19; // [rsp+70h] [rbp-19h]
  PACL pAcl; // [rsp+78h] [rbp-11h] BYREF
  struct _ACL *v21; // [rsp+80h] [rbp-9h] BYREF
  PSID pSid1; // [rsp+88h] [rbp-1h] BYREF
  PSID TokenInformation; // [rsp+90h] [rbp+7h] BYREF
  struct _ACL *v24; // [rsp+98h] [rbp+Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+17h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid1 = 0;
  v18 = 0;
  v19 = 0;
  pAcl = 0;
  v21 = 0;
  TokenInformation = 0;
  v24 = 0;
  v17 = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid1) )
    goto LABEL_2;
  ProcessHeap = GetProcessHeap();
  TokenInformation_Heap = GetTokenInformation_HeapFree<_TOKEN_USER>(ProcessHeap, TokenHandle);
  if ( TokenInformation_Heap >= 0 )
  {
    v10 = GetProcessHeap();
    v11 = GetTokenInformation_HeapFree<_TOKEN_DEFAULT_DACL>(v10, TokenHandle);
    if ( v11 >= 0 )
    {
      TokenInformation = *v18;
      if ( SetTokenInformation(a2, TokenOwner, &TokenInformation, 8u) )
      {
        if ( (unsigned int)SetSidOnAcl(*v19, pSid1, 0, v12, 0, &pAcl) )
        {
          v5 = pAcl;
          if ( (unsigned int)SetSidOnAcl(pAcl, *v18, 0x10000000u, v13, 1, &v21) )
          {
            v6 = v21;
            v24 = v21;
            if ( !SetTokenInformation(a2, TokenDefaultDacl, &v24, 8u)
              || (v17 = 1, !SetTokenInformation(a2, TokenVirtualizationEnabled, &v17, 4u)) )
            {
LABEL_2:
              LastError = GetLastError();
              goto LABEL_16;
            }
            LastError = 0;
            v4 = 1;
          }
          else
          {
            v15 = GetLastError();
            v6 = v21;
            LastError = v15;
          }
        }
        else
        {
          v14 = GetLastError();
          v5 = pAcl;
          LastError = v14;
        }
      }
      else
      {
        LastError = GetLastError();
      }
    }
    else
    {
      LastError = (unsigned __int16)v11;
    }
  }
  else
  {
    LastError = (unsigned __int16)TokenInformation_Heap;
  }
LABEL_16:
  if ( pSid1 )
    FreeSid(pSid1);
  LocalFree(v5);
  LocalFree(v6);
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x180065324  mov     [rsp-8+arg_10], rbx
0x180065329  push    rbp
0x18006532a  push    rsi
0x18006532b  push    rdi
0x18006532c  push    r12
0x18006532e  push    r13
0x180065330  push    r14
0x180065332  push    r15
0x180065334  lea     rbp, [rsp-27h]
0x180065339  sub     rsp, 0B0h
0x180065340  mov     rax, cs:__security_cookie
0x180065347  xor     rax, rsp
0x18006534a  mov     [rbp+57h+var_38], rax
0x18006534e  mov     rbx, rcx
0x180065351  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180065357  xor     ecx, ecx
0x180065359  lea     rax, [rbp+57h+pSid1]
0x18006535d  mov     [rsp+0E0h+pSid], rax; pSid
0x180065362  mov     r12, rdx
0x180065365  mov     [rsp+0E0h+nSubAuthority7], ecx; nSubAuthority7
0x180065369  mov     r13d, ecx
0x18006536c  mov     [rsp+0E0h+nSubAuthority6], ecx; nSubAuthority6
0x180065370  mov     edi, ecx
0x180065372  mov     [rsp+0E0h+nSubAuthority5], ecx; nSubAuthority5
0x180065376  lea     r8d, [rcx+20h]; nSubAuthority0
0x18006537a  mov     [rsp+0E0h+nSubAuthority4], ecx; nSubAuthority4
0x18006537e  mov     esi, ecx
0x180065380  mov     [rsp+0E0h+nSubAuthority3], ecx; nSubAuthority3
0x180065384  mov     r14d, ecx
0x180065387  mov     [rsp+0E0h+nSubAuthority2], ecx; nSubAuthority2
0x18006538b  mov     r15d, ecx
0x18006538e  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], ecx
0x180065391  mov     r9d, 220h; nSubAuthority1
0x180065397  mov     [rbp+57h+pSid1], rcx
0x18006539b  mov     dl, 2; nSubAuthorityCount
0x18006539d  mov     [rbp+57h+var_78], rcx
0x1800653a1  mov     [rbp+57h+var_70], rcx
0x1800653a5  mov     [rbp+57h+pAcl], rcx
0x1800653a9  mov     [rbp+57h+var_60], rcx
0x1800653ad  mov     [rbp+57h+TokenInformation], rcx
0x1800653b1  mov     [rbp+57h+var_48], rcx
0x1800653b5  mov     [rbp+57h+var_80], ecx
0x1800653b8  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800653bc  call    cs:__imp_AllocateAndInitializeSid
0x1800653c2  test    eax, eax
0x1800653c4  jnz     short loc_1800653D3
0x1800653c6  call    cs:__imp_GetLastError
0x1800653cc  mov     ebx, eax
0x1800653ce  jmp     loc_18006550A
0x1800653d3  call    cs:__imp_GetProcessHeap
0x1800653d9  lea     r9, [rbp+57h+var_78]
0x1800653dd  mov     rdx, rbx; TokenHandle
0x1800653e0  mov     rcx, rax; hHeap
0x1800653e3  call    ??$GetTokenInformation_HeapFree@U_TOKEN_USER@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_USER@@@Z; GetTokenInformation_HeapFree<_TOKEN_USER>(void *,void *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER * *)
0x1800653e8  test    eax, eax
0x1800653ea  jns     short loc_1800653F8
0x1800653ec  mov     rdi, [rbp+57h+var_78]
0x1800653f0  movzx   ebx, ax
0x1800653f3  jmp     loc_18006550A
0x1800653f8  call    cs:__imp_GetProcessHeap
0x1800653fe  lea     r9, [rbp+57h+var_70]
0x180065402  mov     rdx, rbx; TokenHandle
0x180065405  mov     rcx, rax; hHeap
0x180065408  call    ??$GetTokenInformation_HeapFree@U_TOKEN_DEFAULT_DACL@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_DEFAULT_DACL@@@Z; GetTokenInformation_HeapFree<_TOKEN_DEFAULT_DACL>(void *,void *,_TOKEN_INFORMATION_CLASS,_TOKEN_DEFAULT_DACL * *)
0x18006540d  mov     rdi, [rbp+57h+var_78]
0x180065411  test    eax, eax
0x180065413  jns     short loc_180065421
0x180065415  movzx   ebx, ax
0x180065418  mov     rsi, [rbp+57h+var_70]
0x18006541c  jmp     loc_18006550A
0x180065421  mov     rax, [rdi]
0x180065424  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180065428  mov     r9d, 8; TokenInformationLength
0x18006542e  mov     [rbp+57h+TokenInformation], rax
0x180065432  mov     rcx, r12; TokenHandle
0x180065435  lea     edx, [r9-4]; TokenInformationClass
0x180065439  call    cs:__imp_SetTokenInformation
0x18006543f  test    eax, eax
0x180065441  jnz     short loc_18006544D
0x180065443  call    cs:__imp_GetLastError
0x180065449  mov     ebx, eax
0x18006544b  jmp     short loc_180065418
0x18006544d  mov     rdx, [rbp+57h+pSid1]; pSid1
0x180065451  lea     rax, [rbp+57h+pAcl]
0x180065455  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; struct _ACL **
0x18006545a  xor     r8d, r8d; unsigned int
0x18006545d  mov     [rsp+0E0h+nSubAuthority2], esi; int
0x180065461  mov     rsi, [rbp+57h+var_70]
0x180065465  mov     rcx, [rsi]; pAcl
0x180065468  call    ?SetSidOnAcl@@YAHPEAU_ACL@@PEAXKEHPEAPEAU1@@Z; SetSidOnAcl(_ACL *,void *,ulong,uchar,int,_ACL * *)
0x18006546d  test    eax, eax
0x18006546f  jnz     short loc_180065482
0x180065471  call    cs:__imp_GetLastError
0x180065477  mov     r14, [rbp+57h+pAcl]
0x18006547b  mov     ebx, eax
0x18006547d  jmp     loc_18006550A
0x180065482  mov     r14, [rbp+57h+pAcl]
0x180065486  lea     rax, [rbp+57h+var_60]
0x18006548a  mov     rdx, [rdi]; pSid1
0x18006548d  mov     ebx, 1
0x180065492  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax; struct _ACL **
0x180065497  mov     rcx, r14; pAcl
0x18006549a  mov     r8d, 10000000h; unsigned int
0x1800654a0  mov     [rsp+0E0h+nSubAuthority2], ebx; int
0x1800654a4  call    ?SetSidOnAcl@@YAHPEAU_ACL@@PEAXKEHPEAPEAU1@@Z; SetSidOnAcl(_ACL *,void *,ulong,uchar,int,_ACL * *)
0x1800654a9  test    eax, eax
0x1800654ab  jnz     short loc_1800654BB
0x1800654ad  call    cs:__imp_GetLastError
0x1800654b3  mov     r15, [rbp+57h+var_60]
0x1800654b7  mov     ebx, eax
0x1800654b9  jmp     short loc_18006550A
0x1800654bb  mov     r15, [rbp+57h+var_60]
0x1800654bf  lea     r8, [rbp+57h+var_48]; TokenInformation
0x1800654c3  mov     r9d, 8; TokenInformationLength
0x1800654c9  mov     [rbp+57h+var_48], r15
0x1800654cd  mov     rcx, r12; TokenHandle
0x1800654d0  lea     edx, [r9-2]; TokenInformationClass
0x1800654d4  call    cs:__imp_SetTokenInformation
0x1800654da  test    eax, eax
0x1800654dc  jz      loc_1800653C6
0x1800654e2  mov     r9d, 4; TokenInformationLength
0x1800654e8  mov     [rbp+57h+var_80], ebx
0x1800654eb  lea     r8, [rbp+57h+var_80]; TokenInformation
0x1800654ef  mov     rcx, r12; TokenHandle
0x1800654f2  lea     edx, [r9+14h]; TokenInformationClass
0x1800654f6  call    cs:__imp_SetTokenInformation
0x1800654fc  test    eax, eax
0x1800654fe  jz      loc_1800653C6
0x180065504  xor     ebx, ebx
0x180065506  lea     r13d, [rbx+1]
0x18006550a  mov     rcx, [rbp+57h+pSid1]; pSid
0x18006550e  test    rcx, rcx
0x180065511  jz      short loc_180065519
0x180065513  call    cs:__imp_FreeSid
0x180065519  test    rdi, rdi
0x18006551c  jz      short loc_180065532
0x18006551e  call    cs:__imp_GetProcessHeap
0x180065524  mov     r8, rdi; lpMem
0x180065527  xor     edx, edx; dwFlags
0x180065529  mov     rcx, rax; hHeap
0x18006552c  call    cs:__imp_HeapFree
0x180065532  test    rsi, rsi
0x180065535  jz      short loc_18006554B
0x180065537  call    cs:__imp_GetProcessHeap
0x18006553d  mov     r8, rsi; lpMem
0x180065540  xor     edx, edx; dwFlags
0x180065542  mov     rcx, rax; hHeap
0x180065545  call    cs:__imp_HeapFree
0x18006554b  mov     rcx, r14; hMem
0x18006554e  call    cs:__imp_LocalFree
0x180065554  mov     rcx, r15; hMem
0x180065557  call    cs:__imp_LocalFree
0x18006555d  mov     ecx, ebx; dwErrCode
0x18006555f  call    cs:__imp_SetLastError
0x180065565  mov     eax, r13d
0x180065568  mov     rcx, [rbp+57h+var_38]
0x18006556c  xor     rcx, rsp; StackCookie
0x18006556f  call    __security_check_cookie
0x180065574  mov     rbx, [rsp+0E0h+arg_10]
0x18006557c  add     rsp, 0B0h
0x180065583  pop     r15
0x180065585  pop     r14
0x180065587  pop     r13
0x180065589  pop     r12
0x18006558b  pop     rdi
0x18006558c  pop     rsi
0x18006558d  pop     rbp
0x18006558e  retn
```
