# SampDsNotifyReplicatedInChange

- ea: `0x1803b5b50`
- end: `0x1803b5f00`
- name: `SampDsNotifyReplicatedInChange`
- size: `944`
- prototype: `__int64 __usercall@<rax>(PSID SourceSid@<rcx>, __int64, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x180006360`
- `0x18000bb80`
- `0x18001ea60`
- `0x180021aa3`
- `0x1803b5b50`
- `0x1803d9074`
- `0x1803e6708`
- `0x18042fb0c`
- `0x18042fc3c`
- `0x18042fe48`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x1803b5bf8`
- `ntdll!RtlSubAuthorityCountSid` at `0x1803b5c28`
- `ntdll!RtlSubAuthorityCountSid` at `0x1803b5bf8`
- `ntdll!RtlSubAuthorityCountSid` at `0x1803b5c28`
- `ntdll!RtlInitUnicodeString` at `0x1803b5e51`
- `ntdll!RtlInitUnicodeString` at `0x1803b5e51`
- `ntdll!RtlEqualSid` at `0x1803b5cab`
- `ntdll!RtlEqualSid` at `0x1803b5cab`
- `ntdll!RtlCopySid` at `0x1803b5bbe`
- `ntdll!RtlCopySid` at `0x1803b5bbe`
- `ntdll!RtlLengthSid` at `0x1803b5b81`
- `ntdll!RtlLengthSid` at `0x1803b5bb0`
- `ntdll!RtlLengthSid` at `0x1803b5e22`
- `ntdll!RtlLengthSid` at `0x1803b5b81`
- `ntdll!RtlLengthSid` at `0x1803b5bb0`
- `ntdll!RtlLengthSid` at `0x1803b5e22`
- `NETLOGON!I_NetNotifyDelta` at `0x1803b5db9`
- `NETLOGON!I_NetNotifyDelta` at `0x1803b5db9`
- `NETLOGON!I_NetNotifyMachineAccount` at `0x1803b5df2`
- `NETLOGON!I_NetNotifyMachineAccount` at `0x1803b5df2`
- `SAMSRV!SampInvalidateDomainCache` at `0x1803b5d09`
- `SAMSRV!SampInvalidateDomainCache` at `0x1803b5d09`
- `SAMSRV!SampReleaseSamLockExclusive` at `0x1803b5edc`
- `SAMSRV!SampReleaseSamLockExclusive` at `0x1803b5edc`
- `SAMSRV!SampAcquireSamLockExclusive` at `0x1803b5c57`
- `SAMSRV!SampAcquireSamLockExclusive` at `0x1803b5cc4`
- `SAMSRV!SampAcquireSamLockExclusive` at `0x1803b5cff`
- `SAMSRV!SampAcquireSamLockExclusive` at `0x1803b5d49`
- `SAMSRV!SampAcquireSamLockExclusive` at `0x1803b5c57`
- `SAMSRV!SampAcquireSamLockExclusive` at `0x1803b5cc4`
- `SAMSRV!SampAcquireSamLockExclusive` at `0x1803b5cff`
- `SAMSRV!SampAcquireSamLockExclusive` at `0x1803b5d49`
- `SAMSRV!SampSplitSid` at `0x1803b5bef`
- `SAMSRV!SampSplitSid` at `0x1803b5c1f`
- `SAMSRV!SampSplitSid` at `0x1803b5bef`
- `SAMSRV!SampSplitSid` at `0x1803b5c1f`
- `SAMSRV!SampCurrentThreadOwnsLock` at `0x1803b5c4d`
- `SAMSRV!SampCurrentThreadOwnsLock` at `0x1803b5cba`
- `SAMSRV!SampCurrentThreadOwnsLock` at `0x1803b5cf5`
- `SAMSRV!SampCurrentThreadOwnsLock` at `0x1803b5d3f`
- `SAMSRV!SampCurrentThreadOwnsLock` at `0x1803b5c4d`
- `SAMSRV!SampCurrentThreadOwnsLock` at `0x1803b5cba`
- `SAMSRV!SampCurrentThreadOwnsLock` at `0x1803b5cf5`
- `SAMSRV!SampCurrentThreadOwnsLock` at `0x1803b5d3f`
- `SAMSRV!SampUpdateMixedModeAndFindDomain` at `0x1803b5c66`
- `SAMSRV!SampUpdateMixedModeAndFindDomain` at `0x1803b5cd8`
- `SAMSRV!SampUpdateMixedModeAndFindDomain` at `0x1803b5d5d`
- `SAMSRV!SampUpdateMixedModeAndFindDomain` at `0x1803b5c66`
- `SAMSRV!SampUpdateMixedModeAndFindDomain` at `0x1803b5cd8`
- `SAMSRV!SampUpdateMixedModeAndFindDomain` at `0x1803b5d5d`
- `SAMSRV!SampAlInvalidateAliasInformation` at `0x1803b5ce2`
- `SAMSRV!SampAlInvalidateAliasInformation` at `0x1803b5ce2`
- `SAMSRV!SampValidateDomainCacheCallback` at `0x1803b5d0f`
- `SAMSRV!SampGetDownLevelDomainControllersPresent` at `0x1803b5d67`
- `SAMSRV!SampGetDownLevelDomainControllersPresent` at `0x1803b5d67`
- `SAMSRV!SampIncrementNetlogonChangeLogSerialNumber` at `0x1803b5d73`
- `SAMSRV!SampIncrementNetlogonChangeLogSerialNumber` at `0x1803b5d73`
- `SAMSRV!SampDuplicateUnicodeString` at `0x1803b5e63`
- `SAMSRV!SampDuplicateUnicodeString` at `0x1803b5e63`
- `SAMSRV!SampDeltaChangeNotify` at `0x1803b5ed0`
- `SAMSRV!SampDeltaChangeNotify` at `0x1803b5ed0`

## pseudocode

```c
void *__fastcall SampDsNotifyReplicatedInChange(
        PSID SourceSid,
        int a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        int a8,
        unsigned int a9,
        int a10)
{
  ULONG v14; // eax
  void *result; // rax
  void *v16; // rbx
  unsigned int Domain; // esi
  ULONG v18; // eax
  unsigned int v19; // r15d
  PUCHAR v20; // rax
  PUCHAR v21; // rax
  int v22; // r9d
  __int64 v23; // rax
  unsigned int v24; // r12d
  unsigned int v25; // esi
  __int64 v26; // r9
  char *v27; // rax
  char *v28; // rdi
  ULONG v29; // eax
  int v30; // r9d
  __int64 *v31; // rcx
  unsigned int v32; // [rsp+20h] [rbp-58h]
  char v33; // [rsp+50h] [rbp-28h]
  unsigned int v34; // [rsp+54h] [rbp-24h] BYREF
  unsigned int v35; // [rsp+58h] [rbp-20h]
  __int64 v36; // [rsp+60h] [rbp-18h] BYREF
  __int64 v37; // [rsp+68h] [rbp-10h] BYREF

  v34 = 0;
  v37 = 0;
  v36 = 0;
  v14 = RtlLengthSid(SourceSid);
  result = (void *)DSAllocAux(v14, 522849822);
  v16 = result;
  if ( !result )
    return result;
  v33 = 0;
  Domain = -1;
  v35 = 1;
  v18 = RtlLengthSid(SourceSid);
  RtlCopySid(v18, v16, SourceSid);
  v19 = a6;
  switch ( a4 )
  {
    case 1:
      v35 = 1;
      break;
    case 2:
      v35 = 3;
      goto LABEL_9;
    case 3:
      v35 = 4;
LABEL_9:
      SampSplitSid(SourceSid, 0, &v34);
      v21 = RtlSubAuthorityCountSid(v16);
      --*v21;
      break;
    case 4:
      v35 = 2;
      SampSplitSid(SourceSid, 0, &v34);
      v20 = RtlSubAuthorityCountSid(v16);
      --*v20;
      LODWORD(v37) = a6;
      break;
  }
  if ( *(int *)dword_18052B3E4 < 2 )
  {
    if ( !a2 && !(unsigned __int8)SampCurrentThreadOwnsLock() )
    {
      SampAcquireSamLockExclusive();
      v33 = 1;
    }
    Domain = SampUpdateMixedModeAndFindDomain(v16, a9);
  }
  SampProcessChangesToGroupCache(v34, a4, a10, a6, a3);
  if ( (unsigned int)(a4 - 2) > 1 )
    goto LABEL_26;
  if ( a7 < 0 )
  {
    if ( a4 == 3 )
    {
      if ( RtlEqualSid(v16, SampBuiltinDomainSid) )
      {
        if ( !a2 && !(unsigned __int8)SampCurrentThreadOwnsLock() )
        {
          SampAcquireSamLockExclusive();
          v33 = 1;
        }
        if ( Domain == -1 )
          Domain = SampUpdateMixedModeAndFindDomain(v16, a9);
        SampAlInvalidateAliasInformation(Domain);
      }
LABEL_31:
      if ( *(int *)dword_18052B3E4 >= 2 )
        goto LABEL_39;
      if ( !a2 && !(unsigned __int8)SampCurrentThreadOwnsLock() )
      {
        SampAcquireSamLockExclusive();
        v33 = 1;
      }
      if ( Domain == -1 )
        Domain = SampUpdateMixedModeAndFindDomain(v16, a9);
      if ( (unsigned __int8)SampGetDownLevelDomainControllersPresent(Domain) )
      {
        v23 = SampIncrementNetlogonChangeLogSerialNumber(Domain);
        v24 = v35;
        v25 = a3;
        v32 = v34;
        v36 = v23;
        I_NetNotifyDelta(1, v23, a3, v35);
      }
      else
      {
LABEL_39:
        v25 = a3;
        v24 = v35;
      }
      if ( (a6 & 0x1C0) != 0 )
      {
        v26 = 0;
        v32 = a5;
        if ( v25 != 3 )
        {
          v26 = a6;
          v19 = 0;
        }
        I_NetNotifyMachineAccount(v34, v16, v19, v26);
      }
      v27 = (char *)DFAlloc(64);
      v28 = v27;
      if ( v27 )
      {
        memset_0(v27, 0, 0x40u);
        v29 = RtlLengthSid(v16);
        memcpy_0(v28 + 8, v16, v29);
        *((_DWORD *)v28 + 1) = v25;
        *(_DWORD *)v28 = v24;
        *((_DWORD *)v28 + 9) = v34;
        *((_QWORD *)v28 + 7) = v36;
        RtlInitUnicodeString((PUNICODE_STRING)(v28 + 40), 0);
        if ( a5 && (int)SampDuplicateUnicodeString(v28 + 40, a5) < 0 )
          DFFreeNow(v28);
        else
          NotifyListAddNotification((unsigned int)SampNotifyKdcInBackground, (_DWORD)v28, 16, v30, v32, 0);
      }
      if ( (unsigned int)(a4 - 2) <= 1 )
        SampInvalidateAclConversionCache();
      v31 = &v37;
      if ( v24 != 2 )
        v31 = 0;
      SampDeltaChangeNotify(v16, a3, v24, v34, a5, &v36, v31);
      goto LABEL_54;
    }
LABEL_26:
    if ( a4 == 1 )
    {
      if ( !a2 && !(unsigned __int8)SampCurrentThreadOwnsLock() )
      {
        SampAcquireSamLockExclusive();
        v33 = 1;
      }
      SampInvalidateDomainCache();
      NotifyListAddNotification(SampValidateDomainCacheCallback, 0, 16, v22, v32, 0);
    }
    goto LABEL_31;
  }
LABEL_54:
  if ( v33 )
    SampReleaseSamLockExclusive();
  return (void *)DSFreeAux(v16, 522850163);
}

```

## disassembly

```asm
0x1803b5b50  mov     [rsp-40h+arg_10], r8d
0x1803b5b55  push    rbp
0x1803b5b56  push    rbx
0x1803b5b57  push    rsi
0x1803b5b58  push    rdi
0x1803b5b59  push    r12
0x1803b5b5b  push    r13
0x1803b5b5d  push    r14
0x1803b5b5f  push    r15
0x1803b5b61  mov     rbp, rsp
0x1803b5b64  sub     rsp, 78h
0x1803b5b68  xor     esi, esi
0x1803b5b6a  mov     r13d, r9d
0x1803b5b6d  mov     [rbp+var_24], esi
0x1803b5b70  mov     r14d, r8d
0x1803b5b73  mov     [rbp+var_10], rsi
0x1803b5b77  mov     r12d, edx
0x1803b5b7a  mov     [rbp+var_18], rsi
0x1803b5b7e  mov     rdi, rcx
0x1803b5b81  call    cs:__imp_RtlLengthSid
0x1803b5b87  mov     ecx, eax
0x1803b5b89  mov     edx, 1F2A0E1Eh
0x1803b5b8e  call    DSAllocAux
0x1803b5b93  mov     rbx, rax
0x1803b5b96  test    rax, rax
0x1803b5b99  jz      loc_1803B5EEF
0x1803b5b9f  mov     [rbp+var_28], sil
0x1803b5ba3  mov     rcx, rdi; Sid
0x1803b5ba6  or      esi, 0FFFFFFFFh
0x1803b5ba9  mov     [rbp+var_20], 1
0x1803b5bb0  call    cs:__imp_RtlLengthSid
0x1803b5bb6  mov     r8, rdi; SourceSid
0x1803b5bb9  mov     rdx, rbx; DestinationSid
0x1803b5bbc  mov     ecx, eax; DestinationSidLength
0x1803b5bbe  call    cs:__imp_RtlCopySid
0x1803b5bc4  mov     r15d, [rbp+arg_28]
0x1803b5bc8  mov     ecx, r13d
0x1803b5bcb  sub     ecx, 1
0x1803b5bce  jz      short loc_1803B5C32
0x1803b5bd0  sub     ecx, 1
0x1803b5bd3  jz      short loc_1803B5C0F
0x1803b5bd5  sub     ecx, 1
0x1803b5bd8  jz      short loc_1803B5C06
0x1803b5bda  cmp     ecx, 1
0x1803b5bdd  jnz     short loc_1803B5C39
0x1803b5bdf  lea     r8, [rbp+var_24]
0x1803b5be3  mov     [rbp+var_20], 2
0x1803b5bea  xor     edx, edx
0x1803b5bec  mov     rcx, rdi
0x1803b5bef  call    cs:__imp_SampSplitSid
0x1803b5bf5  mov     rcx, rbx; Sid
0x1803b5bf8  call    cs:__imp_RtlSubAuthorityCountSid
0x1803b5bfe  dec     byte ptr [rax]
0x1803b5c00  mov     dword ptr [rbp+var_10], r15d
0x1803b5c04  jmp     short loc_1803B5C39
0x1803b5c06  mov     [rbp+var_20], 4
0x1803b5c0d  jmp     short loc_1803B5C16
0x1803b5c0f  mov     [rbp+var_20], 3
0x1803b5c16  lea     r8, [rbp+var_24]
0x1803b5c1a  xor     edx, edx
0x1803b5c1c  mov     rcx, rdi
0x1803b5c1f  call    cs:__imp_SampSplitSid
0x1803b5c25  mov     rcx, rbx; Sid
0x1803b5c28  call    cs:__imp_RtlSubAuthorityCountSid
0x1803b5c2e  dec     byte ptr [rax]
0x1803b5c30  jmp     short loc_1803B5C39
0x1803b5c32  mov     [rbp+var_20], 1
0x1803b5c39  cmp     cs:dword_18052B3E4, 2
0x1803b5c40  mov     edi, [rbp+arg_40]
0x1803b5c46  jge     short loc_1803B5C6E
0x1803b5c48  test    r12d, r12d
0x1803b5c4b  jnz     short loc_1803B5C61
0x1803b5c4d  call    cs:__imp_SampCurrentThreadOwnsLock
0x1803b5c53  test    al, al
0x1803b5c55  jnz     short loc_1803B5C61
0x1803b5c57  call    cs:__imp_SampAcquireSamLockExclusive
0x1803b5c5d  mov     [rbp+var_28], 1
0x1803b5c61  mov     edx, edi
0x1803b5c63  mov     rcx, rbx
0x1803b5c66  call    cs:__imp_SampUpdateMixedModeAndFindDomain
0x1803b5c6c  mov     esi, eax
0x1803b5c6e  mov     r8d, [rbp+arg_48]
0x1803b5c75  mov     r9d, r15d
0x1803b5c78  mov     ecx, [rbp+var_24]
0x1803b5c7b  mov     edx, r13d
0x1803b5c7e  mov     dword ptr [rsp+78h+var_58], r14d
0x1803b5c83  call    SampProcessChangesToGroupCache
0x1803b5c88  lea     ecx, [r13-2]
0x1803b5c8c  cmp     ecx, 1
0x1803b5c8f  ja      short loc_1803B5CEA
0x1803b5c91  cmp     [rbp+arg_30], 0
0x1803b5c95  jge     loc_1803B5ED6
0x1803b5c9b  cmp     r13d, 3
0x1803b5c9f  jnz     short loc_1803B5CEA
0x1803b5ca1  mov     rdx, cs:SampBuiltinDomainSid; Sid2
0x1803b5ca8  mov     rcx, rbx; Sid1
0x1803b5cab  call    cs:__imp_RtlEqualSid
0x1803b5cb1  test    al, al
0x1803b5cb3  jz      short loc_1803B5D29
0x1803b5cb5  test    r12d, r12d
0x1803b5cb8  jnz     short loc_1803B5CCE
0x1803b5cba  call    cs:__imp_SampCurrentThreadOwnsLock
0x1803b5cc0  test    al, al
0x1803b5cc2  jnz     short loc_1803B5CCE
0x1803b5cc4  call    cs:__imp_SampAcquireSamLockExclusive
0x1803b5cca  mov     [rbp+var_28], 1
0x1803b5cce  cmp     esi, 0FFFFFFFFh
0x1803b5cd1  jnz     short loc_1803B5CE0
0x1803b5cd3  mov     edx, edi
0x1803b5cd5  mov     rcx, rbx
0x1803b5cd8  call    cs:__imp_SampUpdateMixedModeAndFindDomain
0x1803b5cde  mov     esi, eax
0x1803b5ce0  mov     ecx, esi
0x1803b5ce2  call    cs:__imp_SampAlInvalidateAliasInformation
0x1803b5ce8  jmp     short loc_1803B5D29
0x1803b5cea  cmp     r13d, 1
0x1803b5cee  jnz     short loc_1803B5D29
0x1803b5cf0  test    r12d, r12d
0x1803b5cf3  jnz     short loc_1803B5D09
0x1803b5cf5  call    cs:__imp_SampCurrentThreadOwnsLock
0x1803b5cfb  test    al, al
0x1803b5cfd  jnz     short loc_1803B5D09
0x1803b5cff  call    cs:__imp_SampAcquireSamLockExclusive
0x1803b5d05  mov     [rbp+var_28], r13b
0x1803b5d09  call    cs:__imp_SampInvalidateDomainCache
0x1803b5d0f  mov     rcx, cs:__imp_SampValidateDomainCacheCallback
0x1803b5d16  xor     edx, edx
0x1803b5d18  mov     dword ptr [rsp+78h+var_50], 0
0x1803b5d20  lea     r8d, [rdx+10h]
0x1803b5d24  call    NotifyListAddNotification
0x1803b5d29  cmp     cs:dword_18052B3E4, 2
0x1803b5d30  mov     r14, [rbp+arg_20]
0x1803b5d34  jge     loc_1803B5DC1
0x1803b5d3a  test    r12d, r12d
0x1803b5d3d  jnz     short loc_1803B5D53
0x1803b5d3f  call    cs:__imp_SampCurrentThreadOwnsLock
0x1803b5d45  test    al, al
0x1803b5d47  jnz     short loc_1803B5D53
0x1803b5d49  call    cs:__imp_SampAcquireSamLockExclusive
0x1803b5d4f  mov     [rbp+var_28], 1
0x1803b5d53  cmp     esi, 0FFFFFFFFh
0x1803b5d56  jnz     short loc_1803B5D65
0x1803b5d58  mov     edx, edi
0x1803b5d5a  mov     rcx, rbx
0x1803b5d5d  call    cs:__imp_SampUpdateMixedModeAndFindDomain
0x1803b5d63  mov     esi, eax
0x1803b5d65  mov     ecx, esi
0x1803b5d67  call    cs:__imp_SampGetDownLevelDomainControllersPresent
0x1803b5d6d  test    al, al
0x1803b5d6f  jz      short loc_1803B5DC1
0x1803b5d71  mov     ecx, esi
0x1803b5d73  call    cs:__imp_SampIncrementNetlogonChangeLogSerialNumber
0x1803b5d79  mov     r12d, [rbp+var_20]
0x1803b5d7d  mov     ecx, r15d
0x1803b5d80  mov     esi, [rbp+arg_10]
0x1803b5d83  mov     r9d, r12d
0x1803b5d86  shr     ecx, 6
0x1803b5d89  mov     r8d, esi
0x1803b5d8c  and     ecx, 1
0x1803b5d8f  mov     [rsp+78h+var_38], 0
0x1803b5d98  mov     [rsp+78h+var_40], ecx
0x1803b5d9c  mov     rdx, rax
0x1803b5d9f  mov     ecx, [rbp+var_24]
0x1803b5da2  mov     [rsp+78h+var_48], r14
0x1803b5da7  mov     [rsp+78h+var_50], rbx
0x1803b5dac  mov     dword ptr [rsp+78h+var_58], ecx
0x1803b5db0  mov     ecx, 1
0x1803b5db5  mov     [rbp+var_18], rax
0x1803b5db9  call    cs:__imp_I_NetNotifyDelta
0x1803b5dbf  jmp     short loc_1803B5DC8
0x1803b5dc1  mov     esi, [rbp+arg_10]
0x1803b5dc4  mov     r12d, [rbp+var_20]
0x1803b5dc8  test    r15d, 1C0h
0x1803b5dcf  jz      short loc_1803B5DF8
0x1803b5dd1  mov     ecx, [rbp+var_24]
0x1803b5dd4  xor     r9d, r9d
0x1803b5dd7  cmp     esi, 3
0x1803b5dda  mov     [rsp+78h+var_58], r14
0x1803b5ddf  mov     rdx, rbx
0x1803b5de2  cmovnz  r9d, r15d
0x1803b5de6  xor     eax, eax
0x1803b5de8  cmp     esi, 3
0x1803b5deb  cmovnz  r15d, eax
0x1803b5def  mov     r8d, r15d
0x1803b5df2  call    cs:__imp_I_NetNotifyMachineAccount
0x1803b5df8  mov     r15d, 40h ; '@'
0x1803b5dfe  mov     ecx, r15d
0x1803b5e01  call    DFAlloc
0x1803b5e06  mov     rdi, rax
0x1803b5e09  test    rax, rax
0x1803b5e0c  jz      loc_1803B5E94
0x1803b5e12  mov     r8d, r15d; Size
0x1803b5e15  xor     edx, edx; Val
0x1803b5e17  mov     rcx, rax; void *
0x1803b5e1a  call    memset_0
0x1803b5e1f  mov     rcx, rbx; Sid
0x1803b5e22  call    cs:__imp_RtlLengthSid
0x1803b5e28  mov     r8d, eax; Size
0x1803b5e2b  lea     rcx, [rdi+8]; void *
0x1803b5e2f  mov     rdx, rbx; Src
0x1803b5e32  call    memcpy_0
0x1803b5e37  mov     [rdi+4], esi
0x1803b5e3a  lea     rcx, [rdi+28h]; DestinationString
0x1803b5e3e  mov     [rdi], r12d
0x1803b5e41  xor     edx, edx; SourceString
0x1803b5e43  mov     eax, [rbp+var_24]
0x1803b5e46  mov     [rdi+24h], eax
0x1803b5e49  mov     rax, [rbp+var_18]
0x1803b5e4d  mov     [rdi+38h], rax
0x1803b5e51  call    cs:__imp_RtlInitUnicodeString
0x1803b5e57  test    r14, r14
0x1803b5e5a  jz      short loc_1803B5E77
0x1803b5e5c  mov     rdx, r14
0x1803b5e5f  lea     rcx, [rdi+28h]
0x1803b5e63  call    cs:__imp_SampDuplicateUnicodeString
0x1803b5e69  test    eax, eax
0x1803b5e6b  jns     short loc_1803B5E77
0x1803b5e6d  mov     rcx, rdi
0x1803b5e70  call    DFFreeNow
0x1803b5e75  jmp     short loc_1803B5E94
0x1803b5e77  mov     r8d, 10h
0x1803b5e7d  mov     dword ptr [rsp+78h+var_50], 0
0x1803b5e85  mov     rdx, rdi
0x1803b5e88  lea     rcx, ?SampNotifyKdcInBackground@@YAJPEAX@Z; SampNotifyKdcInBackground(void *)
0x1803b5e8f  call    NotifyListAddNotification
0x1803b5e94  lea     eax, [r13-2]
0x1803b5e98  cmp     eax, 1
0x1803b5e9b  ja      short loc_1803B5EA2
0x1803b5e9d  call    SampInvalidateAclConversionCache
0x1803b5ea2  mov     r9d, [rbp+var_24]
0x1803b5ea6  lea     rcx, [rbp+var_10]
0x1803b5eaa  mov     edx, [rbp+arg_10]
0x1803b5ead  xor     eax, eax
0x1803b5eaf  cmp     r12d, 2
0x1803b5eb3  mov     r8d, r12d
0x1803b5eb6  cmovnz  rcx, rax
0x1803b5eba  lea     rax, [rbp+var_18]
0x1803b5ebe  mov     [rsp+78h+var_48], rcx
0x1803b5ec3  mov     rcx, rbx
0x1803b5ec6  mov     [rsp+78h+var_50], rax
0x1803b5ecb  mov     [rsp+78h+var_58], r14
0x1803b5ed0  call    cs:__imp_SampDeltaChangeNotify
0x1803b5ed6  cmp     [rbp+var_28], 0
0x1803b5eda  jz      short loc_1803B5EE2
0x1803b5edc  call    cs:__imp_SampReleaseSamLockExclusive
0x1803b5ee2  mov     edx, 1F2A0F73h
0x1803b5ee7  mov     rcx, rbx
0x1803b5eea  call    DSFreeAux
0x1803b5eef  add     rsp, 78h
0x1803b5ef3  pop     r15
0x1803b5ef5  pop     r14
0x1803b5ef7  pop     r13
0x1803b5ef9  pop     r12
0x1803b5efb  pop     rdi
0x1803b5efc  pop     rsi
0x1803b5efd  pop     rbx
0x1803b5efe  pop     rbp
0x1803b5eff  retn
```
