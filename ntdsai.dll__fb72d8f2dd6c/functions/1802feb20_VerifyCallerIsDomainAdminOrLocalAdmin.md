# VerifyCallerIsDomainAdminOrLocalAdmin

- ea: `0x1802feb20`
- end: `0x1802fecc7`
- name: `VerifyCallerIsDomainAdminOrLocalAdmin`
- size: `423`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1802fb900`
- `0x1802fd40c`

## callees

- `0x18001e090`
- `0x1800c8bec`
- `0x180161d38`
- `0x18016a988`
- `0x18016ae88`
- `0x1802feb20`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1802feba5`
- `RPCRT4!RpcRevertToSelf` at `0x1802fec9c`
- `RPCRT4!RpcRevertToSelf` at `0x1802feba5`
- `RPCRT4!RpcRevertToSelf` at `0x1802fec9c`
- `RPCRT4!RpcImpersonateClient` at `0x1802feb7e`
- `RPCRT4!RpcImpersonateClient` at `0x1802feb7e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1802fec0d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1802fec0d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1802fec40`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1802fec40`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802febc1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802fec2a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802febc1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802fec2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802fec17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802fec34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802fec17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802fec34`
- `ntdll!RtlNtStatusToDosError` at `0x1802febad`
- `ntdll!RtlNtStatusToDosError` at `0x1802febad`

## pseudocode

```c
RPC_STATUS __fastcall VerifyCallerIsDomainAdminOrLocalAdmin(__int64 a1, void *a2, WINBOOL *a3)
{
  RPC_STATUS result; // eax
  DWORD LastError; // ebx
  NTSTATUS v8; // esi
  int v9; // eax
  PSID pSid; // [rsp+60h] [rbp-19h] BYREF
  __int128 v11; // [rsp+70h] [rbp-9h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+7h] BYREF
  _OWORD SidToCheck[2]; // [rsp+88h] [rbp+Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  SidToCheck[0] = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *a3 = 0;
  *(_OWORD *)((char *)SidToCheck + 12) = 0;
  AssignAuthzClientContext(a1 + 5960, 0);
  result = RpcImpersonateClient(0);
  LastError = result;
  if ( !result )
  {
    v8 = SampBuildNT4FullSid(a2);
    if ( v8 < 0 )
    {
      RpcRevertToSelf();
      return RtlNtStatusToDosError(v8);
    }
    if ( !CheckTokenMembership(0, SidToCheck, a3) )
      goto LABEL_7;
    if ( *a3 )
    {
LABEL_15:
      RpcRevertToSelf();
      return LastError;
    }
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      if ( !CheckTokenMembership(0, pSid, a3) )
        LastError = GetLastError();
      FreeSid(pSid);
    }
    else
    {
LABEL_7:
      LastError = GetLastError();
    }
    if ( !*a3 )
    {
      v9 = SCGetClassById(a1, 655427);
      v11 = RIGHT_DS_MIGRATE_SID_HISTORY;
      if ( (unsigned int)IsControlAccessGrantedEx(qword_18052B3C0, (int)qword_18052B2C0, v9, 0, 1) )
      {
        *a3 = 1;
        LastError = 0;
      }
      else
      {
        LastError = 8344;
      }
    }
    goto LABEL_15;
  }
  return result;
}

```

## disassembly

```asm
0x1802feb20  mov     [rsp-8+arg_18], rbx
0x1802feb25  push    rbp
0x1802feb26  push    rsi
0x1802feb27  push    rdi
0x1802feb28  push    r14
0x1802feb2a  push    r15
0x1802feb2c  lea     rbp, [rsp-37h]
0x1802feb31  sub     rsp, 0B0h
0x1802feb38  mov     rax, cs:__security_cookie
0x1802feb3f  xor     rax, rsp
0x1802feb42  mov     [rbp+57h+var_28], rax
0x1802feb46  xorps   xmm0, xmm0
0x1802feb49  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1802feb4f  xor     r15d, r15d
0x1802feb52  mov     rsi, rdx
0x1802feb55  mov     r14, rcx
0x1802feb58  mov     [rbp+57h+var_70], r15
0x1802feb5c  movups  xmmword ptr [rbp+57h+SidToCheck], xmm0
0x1802feb60  add     rcx, 1748h
0x1802feb67  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x1802feb6b  xor     edx, edx
0x1802feb6d  mov     [r8], r15d
0x1802feb70  movups  xmmword ptr [rbp+57h+SidToCheck+0Ch], xmm0
0x1802feb74  mov     rdi, r8
0x1802feb77  call    AssignAuthzClientContext
0x1802feb7c  xor     ecx, ecx; BindingHandle
0x1802feb7e  call    cs:__imp_RpcImpersonateClient
0x1802feb84  mov     ebx, eax
0x1802feb86  test    eax, eax
0x1802feb88  jnz     loc_1802FECA4
0x1802feb8e  lea     r8, [rbp+57h+SidToCheck]
0x1802feb92  mov     edx, 200h
0x1802feb97  mov     rcx, rsi; Src
0x1802feb9a  call    SampBuildNT4FullSid
0x1802feb9f  mov     esi, eax
0x1802feba1  test    eax, eax
0x1802feba3  jns     short loc_1802FEBB8
0x1802feba5  call    cs:__imp_RpcRevertToSelf
0x1802febab  mov     ecx, esi; Status
0x1802febad  call    cs:__imp_RtlNtStatusToDosError
0x1802febb3  jmp     loc_1802FECA4
0x1802febb8  mov     r8, rdi; IsMember
0x1802febbb  lea     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1802febbf  xor     ecx, ecx; TokenHandle
0x1802febc1  call    cs:__imp_CheckTokenMembership
0x1802febc7  test    eax, eax
0x1802febc9  jz      short loc_1802FEC17
0x1802febcb  cmp     [rdi], r15d
0x1802febce  jnz     loc_1802FEC9C
0x1802febd4  lea     rax, [rbp+57h+var_70]
0x1802febd8  mov     r9d, 220h; nSubAuthority1
0x1802febde  mov     [rsp+0D0h+pSid], rax; pSid
0x1802febe3  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1802febe7  mov     [rsp+0D0h+nSubAuthority7], r15d; nSubAuthority7
0x1802febec  mov     r8d, 20h ; ' '; nSubAuthority0
0x1802febf2  mov     [rsp+0D0h+nSubAuthority6], r15d; nSubAuthority6
0x1802febf7  mov     dl, 2; nSubAuthorityCount
0x1802febf9  mov     [rsp+0D0h+nSubAuthority5], r15d; nSubAuthority5
0x1802febfe  mov     [rsp+0D0h+nSubAuthority4], r15d; nSubAuthority4
0x1802fec03  mov     [rsp+0D0h+nSubAuthority3], r15d; nSubAuthority3
0x1802fec08  mov     [rsp+0D0h+nSubAuthority2], r15d; nSubAuthority2
0x1802fec0d  call    cs:__imp_AllocateAndInitializeSid
0x1802fec13  test    eax, eax
0x1802fec15  jnz     short loc_1802FEC21
0x1802fec17  call    cs:__imp_GetLastError
0x1802fec1d  mov     ebx, eax
0x1802fec1f  jmp     short loc_1802FEC46
0x1802fec21  mov     rdx, [rbp+57h+var_70]; SidToCheck
0x1802fec25  mov     r8, rdi; IsMember
0x1802fec28  xor     ecx, ecx; TokenHandle
0x1802fec2a  call    cs:__imp_CheckTokenMembership
0x1802fec30  test    eax, eax
0x1802fec32  jnz     short loc_1802FEC3C
0x1802fec34  call    cs:__imp_GetLastError
0x1802fec3a  mov     ebx, eax
0x1802fec3c  mov     rcx, [rbp+57h+var_70]; pSid
0x1802fec40  call    cs:__imp_FreeSid
0x1802fec46  cmp     [rdi], r15d
0x1802fec49  jnz     short loc_1802FEC9C
0x1802fec4b  mov     edx, 0A0043h
0x1802fec50  mov     rcx, r14
0x1802fec53  call    SCGetClassById
0x1802fec58  movups  xmm0, cs:RIGHT_DS_MIGRATE_SID_HISTORY
0x1802fec5f  mov     rdx, cs:qword_18052B2C0; int
0x1802fec66  lea     r9, [rbp+57h+var_60]
0x1802fec6a  mov     rcx, cs:qword_18052B3C0; int
0x1802fec71  mov     ebx, 1
0x1802fec76  mov     [rsp+0D0h+nSubAuthority3], ebx; int
0x1802fec7a  mov     r8, rax; int
0x1802fec7d  movdqu  [rbp+57h+var_60], xmm0
0x1802fec82  mov     [rsp+0D0h+nSubAuthority2], r15d; int
0x1802fec87  call    IsControlAccessGrantedEx
0x1802fec8c  test    eax, eax
0x1802fec8e  jz      short loc_1802FEC97
0x1802fec90  mov     [rdi], ebx
0x1802fec92  mov     ebx, r15d
0x1802fec95  jmp     short loc_1802FEC9C
0x1802fec97  mov     ebx, 2098h
0x1802fec9c  call    cs:__imp_RpcRevertToSelf
0x1802feca2  mov     eax, ebx
0x1802feca4  mov     rcx, [rbp+57h+var_28]
0x1802feca8  xor     rcx, rsp; StackCookie
0x1802fecab  call    __security_check_cookie
0x1802fecb0  mov     rbx, [rsp+0D0h+arg_18]
0x1802fecb8  add     rsp, 0B0h
0x1802fecbf  pop     r15
0x1802fecc1  pop     r14
0x1802fecc3  pop     rdi
0x1802fecc4  pop     rsi
0x1802fecc5  pop     rbp
0x1802fecc6  retn
```
