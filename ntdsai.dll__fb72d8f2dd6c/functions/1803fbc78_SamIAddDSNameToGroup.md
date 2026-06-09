# SamIAddDSNameToGroup

- ea: `0x1803fbc78`
- end: `0x1803fbe04`
- name: `SamIAddDSNameToGroup`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18040720c`

## callees

- `0x1803fbc78`
- `0x1803fbf70`
- `0x1803fc2a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fbdb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fbdb4`
- `ntdll!RtlEqualSid` at `0x1803fbd60`
- `ntdll!RtlEqualSid` at `0x1803fbd60`
- `SAMSRV!SampUpdatePerformanceCounters` at `0x1803fbcbf`
- `SAMSRV!SampUpdatePerformanceCounters` at `0x1803fbcbf`
- `SAMSRV!SampSplitSid` at `0x1803fbd40`
- `SAMSRV!SampSplitSid` at `0x1803fbd40`
- `SAMSRV!SampReferenceContext` at `0x1803fbcc8`
- `SAMSRV!SampReferenceContext` at `0x1803fbcc8`
- `SAMSRV!SampDeReferenceContext` at `0x1803fbde3`
- `SAMSRV!SampDeReferenceContext` at `0x1803fbde3`
- `SAMSRV!SampTraceEvent` at `0x1803fbcaf`
- `SAMSRV!SampTraceEvent` at `0x1803fbdf4`
- `SAMSRV!SampTraceEvent` at `0x1803fbcaf`
- `SAMSRV!SampTraceEvent` at `0x1803fbdf4`
- `SAMSRV!SampGetDomainSidFromAccountContext` at `0x1803fbd53`
- `SAMSRV!SampGetDomainSidFromAccountContext` at `0x1803fbd53`
- `SAMSRV!SampAddSameDomainMemberToGlobalOrUniversalGroup` at `0x1803fbd80`
- `SAMSRV!SampAddSameDomainMemberToGlobalOrUniversalGroup` at `0x1803fbd80`
- `SAMSRV!SampAddAccountToGroupMembers` at `0x1803fbda8`
- `SAMSRV!SampAddAccountToGroupMembers` at `0x1803fbdc9`
- `SAMSRV!SampAddAccountToGroupMembers` at `0x1803fbda8`
- `SAMSRV!SampAddAccountToGroupMembers` at `0x1803fbdc9`

## pseudocode

```c
__int64 __fastcall SamIAddDSNameToGroup(__int64 a1, int a2)
{
  __int64 v4; // r8
  int v5; // ebx
  void *DomainSidFromAccountContext; // rax
  int v7; // eax
  __int64 v8; // rdx
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  PSID Sid1; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v12; // [rsp+60h] [rbp+20h] BYREF
  __int64 v13; // [rsp+70h] [rbp+30h] BYREF
  __int64 v14; // [rsp+78h] [rbp+38h] BYREF

  v14 = 0;
  v13 = 0;
  LOBYTE(v12) = 0;
  v10 = 0;
  SampTraceEvent(1);
  SampUpdatePerformanceCounters(5);
  SampReferenceContext(a1);
  if ( (*(_BYTE *)(a1 + 192) & 2) == 0 )
  {
    v5 = -1073741811;
    goto LABEL_17;
  }
  v5 = SampDsValidateName(a1, a2, (unsigned int)&v14, (unsigned int)&v13, (__int64)&v12, (__int64)&v10);
  if ( v5 < 0 )
  {
LABEL_17:
    v8 = 0;
    goto LABEL_18;
  }
  if ( (_BYTE)v12 )
  {
    v5 = -1073741445;
    goto LABEL_17;
  }
  if ( v14 )
  {
    v12 = 0;
    Sid1 = 0;
    v5 = SampSplitSid(v14, &Sid1, &v12);
    if ( v5 < 0 )
      goto LABEL_17;
    DomainSidFromAccountContext = (void *)SampGetDomainSidFromAccountContext(a1);
    if ( RtlEqualSid(Sid1, DomainSidFromAccountContext) )
    {
      v7 = SampAddSameDomainMemberToGlobalOrUniversalGroup(a1, v12, 0, v13, v10);
    }
    else
    {
      v5 = SampDsEnforceCrossDomainGroupMembershipChecks(a1, v14, v13);
      if ( v5 < 0 )
      {
LABEL_12:
        LocalFree(Sid1);
        goto LABEL_14;
      }
      v7 = SampAddAccountToGroupMembers(a1, 0, v13, v10);
    }
    v5 = v7;
    goto LABEL_12;
  }
  v5 = SampAddAccountToGroupMembers(a1, 0, v13, v10);
LABEL_14:
  if ( v5 < 0 )
    goto LABEL_17;
  LOBYTE(v8) = 1;
LABEL_18:
  SampDeReferenceContext(a1, v8, v4);
  SampTraceEvent(2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1803fbc78  push    rbp
0x1803fbc7a  push    rbx
0x1803fbc7b  push    rdi
0x1803fbc7c  mov     rbp, rsp
0x1803fbc7f  sub     rsp, 40h
0x1803fbc83  xor     r8d, r8d
0x1803fbc86  mov     [rbp+arg_18], 0
0x1803fbc8e  mov     rbx, rdx
0x1803fbc91  mov     [rbp+arg_10], 0
0x1803fbc99  mov     rdi, rcx
0x1803fbc9c  mov     byte ptr [rbp+arg_0], 0
0x1803fbca0  mov     [rbp+var_10], 0
0x1803fbca8  lea     edx, [r8+17h]
0x1803fbcac  lea     ecx, [rdx-16h]
0x1803fbcaf  call    cs:__imp_SampTraceEvent
0x1803fbcb5  xor     r8d, r8d
0x1803fbcb8  lea     edx, [r8+1]
0x1803fbcbc  lea     ecx, [rdx+4]
0x1803fbcbf  call    cs:__imp_SampUpdatePerformanceCounters
0x1803fbcc5  mov     rcx, rdi
0x1803fbcc8  call    cs:__imp_SampReferenceContext
0x1803fbcce  test    byte ptr [rdi+0C0h], 2
0x1803fbcd5  jz      loc_1803FBDD9
0x1803fbcdb  lea     rax, [rbp+var_10]
0x1803fbcdf  mov     rdx, rbx
0x1803fbce2  mov     [rsp+40h+var_18], rax
0x1803fbce7  lea     r9, [rbp+arg_10]
0x1803fbceb  lea     rax, [rbp+arg_0]
0x1803fbcef  mov     rcx, rdi
0x1803fbcf2  lea     r8, [rbp+arg_18]
0x1803fbcf6  mov     [rsp+40h+var_20], rax
0x1803fbcfb  call    SampDsValidateName
0x1803fbd00  mov     ebx, eax
0x1803fbd02  test    eax, eax
0x1803fbd04  js      loc_1803FBDDE
0x1803fbd0a  cmp     byte ptr [rbp+arg_0], 0
0x1803fbd0e  jz      short loc_1803FBD1A
0x1803fbd10  mov     ebx, 0C000017Bh
0x1803fbd15  jmp     loc_1803FBDDE
0x1803fbd1a  cmp     [rbp+arg_18], 0
0x1803fbd1f  jz      loc_1803FBDBC
0x1803fbd25  mov     rcx, [rbp+arg_18]
0x1803fbd29  lea     r8, [rbp+arg_0]
0x1803fbd2d  lea     rdx, [rbp+Sid1]
0x1803fbd31  mov     [rbp+arg_0], 0
0x1803fbd38  mov     [rbp+Sid1], 0
0x1803fbd40  call    cs:__imp_SampSplitSid
0x1803fbd46  mov     ebx, eax
0x1803fbd48  test    eax, eax
0x1803fbd4a  js      loc_1803FBDDE
0x1803fbd50  mov     rcx, rdi
0x1803fbd53  call    cs:__imp_SampGetDomainSidFromAccountContext
0x1803fbd59  mov     rcx, [rbp+Sid1]; Sid1
0x1803fbd5d  mov     rdx, rax; Sid2
0x1803fbd60  call    cs:__imp_RtlEqualSid
0x1803fbd66  mov     rcx, rdi
0x1803fbd69  test    al, al
0x1803fbd6b  jz      short loc_1803FBD88
0x1803fbd6d  mov     rax, [rbp+var_10]
0x1803fbd71  xor     r8d, r8d
0x1803fbd74  mov     r9, [rbp+arg_10]
0x1803fbd78  mov     edx, [rbp+arg_0]
0x1803fbd7b  mov     [rsp+40h+var_20], rax
0x1803fbd80  call    cs:__imp_SampAddSameDomainMemberToGlobalOrUniversalGroup
0x1803fbd86  jmp     short loc_1803FBDAE
0x1803fbd88  mov     r8, [rbp+arg_10]
0x1803fbd8c  mov     rdx, [rbp+arg_18]
0x1803fbd90  call    SampDsEnforceCrossDomainGroupMembershipChecks
0x1803fbd95  mov     ebx, eax
0x1803fbd97  test    eax, eax
0x1803fbd99  js      short loc_1803FBDB0
0x1803fbd9b  mov     r9, [rbp+var_10]
0x1803fbd9f  xor     edx, edx
0x1803fbda1  mov     r8, [rbp+arg_10]
0x1803fbda5  mov     rcx, rdi
0x1803fbda8  call    cs:__imp_SampAddAccountToGroupMembers
0x1803fbdae  mov     ebx, eax
0x1803fbdb0  mov     rcx, [rbp+Sid1]; hMem
0x1803fbdb4  call    cs:__imp_LocalFree
0x1803fbdba  jmp     short loc_1803FBDD1
0x1803fbdbc  mov     r9, [rbp+var_10]
0x1803fbdc0  xor     edx, edx
0x1803fbdc2  mov     r8, [rbp+arg_10]
0x1803fbdc6  mov     rcx, rdi
0x1803fbdc9  call    cs:__imp_SampAddAccountToGroupMembers
0x1803fbdcf  mov     ebx, eax
0x1803fbdd1  test    ebx, ebx
0x1803fbdd3  js      short loc_1803FBDDE
0x1803fbdd5  mov     dl, 1
0x1803fbdd7  jmp     short loc_1803FBDE0
0x1803fbdd9  mov     ebx, 0C000000Dh
0x1803fbdde  xor     edx, edx
0x1803fbde0  mov     rcx, rdi
0x1803fbde3  call    cs:__imp_SampDeReferenceContext
0x1803fbde9  mov     edx, 17h
0x1803fbdee  mov     r8d, ebx
0x1803fbdf1  lea     ecx, [rdx-15h]
0x1803fbdf4  call    cs:__imp_SampTraceEvent
0x1803fbdfa  mov     eax, ebx
0x1803fbdfc  add     rsp, 40h
0x1803fbe00  pop     rdi
0x1803fbe01  pop     rbx
0x1803fbe02  pop     rbp
0x1803fbe03  retn
```
