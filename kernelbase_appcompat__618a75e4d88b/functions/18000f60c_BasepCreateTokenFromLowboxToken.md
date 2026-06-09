# BasepCreateTokenFromLowboxToken

- ea: `0x18000f60c`
- end: `0x18000f881`
- name: `BasepCreateTokenFromLowboxToken`
- size: `629`
- prototype: `__int64 __fastcall(HANDLE ExistingTokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ec14`

## callees

- `0x18000f60c`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18000f69e`
- `ntdll!RtlEqualSid` at `0x18000f7ad`
- `ntdll!RtlEqualSid` at `0x18000f69e`
- `ntdll!RtlEqualSid` at `0x18000f7ad`
- `ntdll!NtQueryInformationToken` at `0x18000f682`
- `ntdll!NtQueryInformationToken` at `0x18000f6f8`
- `ntdll!NtQueryInformationToken` at `0x18000f75d`
- `ntdll!NtQueryInformationToken` at `0x18000f682`
- `ntdll!NtQueryInformationToken` at `0x18000f6f8`
- `ntdll!NtQueryInformationToken` at `0x18000f75d`
- `ntdll!RtlGetAppContainerSidType` at `0x18000f6ba`
- `ntdll!RtlGetAppContainerSidType` at `0x18000f6ba`
- `ntdll!RtlFreeHeap` at `0x18000f820`
- `ntdll!RtlFreeHeap` at `0x18000f873`
- `ntdll!RtlFreeHeap` at `0x18000f820`
- `ntdll!RtlFreeHeap` at `0x18000f873`
- `ntdll!NtDuplicateToken` at `0x18000f7fb`
- `ntdll!NtDuplicateToken` at `0x18000f7fb`
- `ntdll!RtlAllocateHeap` at `0x18000f651`
- `ntdll!RtlAllocateHeap` at `0x18000f728`
- `ntdll!RtlAllocateHeap` at `0x18000f651`
- `ntdll!RtlAllocateHeap` at `0x18000f728`

## pseudocode

```c
__int64 __fastcall BasepCreateTokenFromLowboxToken(HANDLE ExistingTokenHandle, _QWORD *a2, HANDLE *a3)
{
  PSID *Heap; // r14
  NTSTATUS AppContainerSidType; // ebx
  int *v7; // rdi
  int v8; // eax
  __int64 v9; // rcx
  int v10; // ebp
  unsigned int i; // ebx
  BOOLEAN v12; // al
  int v14; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+38h] [rbp-40h]
  ULONG TokenInformationLength; // [rsp+98h] [rbp+20h] BYREF

  TokenInformationLength = 0;
  v14 = 0;
  Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x4Cu);
  if ( !Heap )
    return (unsigned int)-1073741801;
  AppContainerSidType = NtQueryInformationToken(
                          ExistingTokenHandle,
                          TokenAppContainerSid,
                          Heap,
                          0x4Cu,
                          &TokenInformationLength);
  if ( AppContainerSidType >= 0 )
  {
    if ( !RtlEqualSid(*Heap, (PSID)*a2) )
    {
      AppContainerSidType = -1073741811;
      goto LABEL_18;
    }
    AppContainerSidType = RtlGetAppContainerSidType(*a2, &v14);
    if ( AppContainerSidType >= 0 )
    {
      v7 = 0;
      if ( v14 == 1 )
        goto LABEL_17;
      AppContainerSidType = NtQueryInformationToken(
                              ExistingTokenHandle,
                              TokenCapabilities,
                              0,
                              0,
                              &TokenInformationLength);
      if ( AppContainerSidType == -1073741789 )
      {
        v7 = (int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength);
        if ( !v7 )
        {
          AppContainerSidType = -1073741801;
          goto LABEL_18;
        }
        AppContainerSidType = NtQueryInformationToken(
                                ExistingTokenHandle,
                                TokenCapabilities,
                                v7,
                                TokenInformationLength,
                                &TokenInformationLength);
        if ( AppContainerSidType < 0 )
          goto LABEL_24;
        v8 = *v7;
        if ( *((_DWORD *)a2 + 4) != *v7 )
        {
LABEL_23:
          AppContainerSidType = -1073741811;
          goto LABEL_24;
        }
        v9 = a2[1];
        v10 = 0;
        v15 = v9;
        if ( v8 )
        {
LABEL_11:
          for ( i = 0; i < *((_DWORD *)a2 + 4); ++i )
          {
            v12 = RtlEqualSid(*(PSID *)&v7[4 * v10 + 2], *(PSID *)(v9 + 16LL * i));
            v9 = v15;
            if ( v12 && v7[4 * v10 + 4] == *(_DWORD *)(v15 + 16LL * i + 8) )
            {
              if ( ++v10 < (unsigned int)*v7 )
                goto LABEL_11;
              goto LABEL_17;
            }
          }
          goto LABEL_23;
        }
LABEL_17:
        AppContainerSidType = NtDuplicateToken(ExistingTokenHandle, 0xF01FFu, 0, 0, TokenPrimary, a3);
        if ( !v7 )
          goto LABEL_18;
LABEL_24:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      }
    }
  }
LABEL_18:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)AppContainerSidType;
}

```

## disassembly

```asm
0x18000f60c  mov     rax, rsp
0x18000f60f  mov     [rax+8], rbx
0x18000f613  mov     [rax+18h], r8
0x18000f617  push    rbp
0x18000f618  push    rsi
0x18000f619  push    rdi
0x18000f61a  push    r12
0x18000f61c  push    r13
0x18000f61e  push    r14
0x18000f620  push    r15
0x18000f622  sub     rsp, 40h
0x18000f626  mov     r13, rcx
0x18000f629  mov     dword ptr [rax+20h], 0
0x18000f630  mov     dword ptr [rax-48h], 0
0x18000f637  mov     rsi, rdx
0x18000f63a  mov     rcx, gs:60h
0x18000f643  mov     ebx, 4Ch ; 'L'
0x18000f648  mov     r8d, ebx; Size
0x18000f64b  xor     edx, edx; Flags
0x18000f64d  mov     rcx, [rcx+30h]; HeapHandle
0x18000f651  call    cs:__imp_RtlAllocateHeap
0x18000f658  nop     dword ptr [rax+rax+00h]
0x18000f65d  mov     r14, rax
0x18000f660  test    rax, rax
0x18000f663  jz      loc_18000F847
0x18000f669  lea     rax, [rsp+78h+TokenInformationLength]
0x18000f671  mov     r9d, ebx; TokenInformationLength
0x18000f674  mov     r8, r14; TokenInformation
0x18000f677  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18000f67c  lea     edx, [rbx-2Dh]; TokenInformationClass
0x18000f67f  mov     rcx, r13; TokenHandle
0x18000f682  call    cs:__imp_NtQueryInformationToken
0x18000f689  nop     dword ptr [rax+rax+00h]
0x18000f68e  mov     ebx, eax
0x18000f690  test    eax, eax
0x18000f692  js      loc_18000F80E
0x18000f698  mov     rdx, [rsi]; Sid2
0x18000f69b  mov     rcx, [r14]; Sid1
0x18000f69e  call    cs:__imp_RtlEqualSid
0x18000f6a5  nop     dword ptr [rax+rax+00h]
0x18000f6aa  test    al, al
0x18000f6ac  jz      loc_18000F84E
0x18000f6b2  mov     rcx, [rsi]
0x18000f6b5  lea     rdx, [rsp+78h+var_48]
0x18000f6ba  call    cs:__imp_RtlGetAppContainerSidType
0x18000f6c1  nop     dword ptr [rax+rax+00h]
0x18000f6c6  mov     ebx, eax
0x18000f6c8  test    eax, eax
0x18000f6ca  js      loc_18000F80E
0x18000f6d0  xor     edi, edi
0x18000f6d2  cmp     [rsp+78h+var_48], 1
0x18000f6d7  jz      loc_18000F7D8
0x18000f6dd  lea     rax, [rsp+78h+TokenInformationLength]
0x18000f6e5  xor     r9d, r9d; TokenInformationLength
0x18000f6e8  lea     ebp, [rdi+1Eh]
0x18000f6eb  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18000f6f0  mov     edx, ebp; TokenInformationClass
0x18000f6f2  xor     r8d, r8d; TokenInformation
0x18000f6f5  mov     rcx, r13; TokenHandle
0x18000f6f8  call    cs:__imp_NtQueryInformationToken
0x18000f6ff  nop     dword ptr [rax+rax+00h]
0x18000f704  mov     ebx, eax
0x18000f706  cmp     eax, 0C0000023h
0x18000f70b  jnz     loc_18000F80E
0x18000f711  mov     rcx, gs:60h
0x18000f71a  xor     edx, edx; Flags
0x18000f71c  mov     r8d, [rsp+78h+TokenInformationLength]; Size
0x18000f724  mov     rcx, [rcx+30h]; HeapHandle
0x18000f728  call    cs:__imp_RtlAllocateHeap
0x18000f72f  nop     dword ptr [rax+rax+00h]
0x18000f734  mov     rdi, rax
0x18000f737  test    rax, rax
0x18000f73a  jz      loc_18000F855
0x18000f740  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x18000f748  lea     rax, [rsp+78h+TokenInformationLength]
0x18000f750  mov     r8, rdi; TokenInformation
0x18000f753  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18000f758  mov     edx, ebp; TokenInformationClass
0x18000f75a  mov     rcx, r13; TokenHandle
0x18000f75d  call    cs:__imp_NtQueryInformationToken
0x18000f764  nop     dword ptr [rax+rax+00h]
0x18000f769  mov     ebx, eax
0x18000f76b  test    eax, eax
0x18000f76d  js      loc_18000F861
0x18000f773  mov     eax, [rdi]
0x18000f775  cmp     [rsi+10h], eax
0x18000f778  jnz     loc_18000F85C
0x18000f77e  mov     rcx, [rsi+8]
0x18000f782  xor     ebp, ebp
0x18000f784  mov     [rsp+78h+var_40], rcx
0x18000f789  test    eax, eax
0x18000f78b  jz      short loc_18000F7D8
0x18000f78d  xor     ebx, ebx
0x18000f78f  cmp     ebx, [rsi+10h]
0x18000f792  jnb     loc_18000F85C
0x18000f798  mov     r15d, ebx
0x18000f79b  mov     r12d, ebp
0x18000f79e  add     r15, r15
0x18000f7a1  add     r12, r12
0x18000f7a4  mov     rdx, [rcx+r15*8]; Sid2
0x18000f7a8  mov     rcx, [rdi+r12*8+8]; Sid1
0x18000f7ad  call    cs:__imp_RtlEqualSid
0x18000f7b4  nop     dword ptr [rax+rax+00h]
0x18000f7b9  mov     rcx, [rsp+78h+var_40]
0x18000f7be  test    al, al
0x18000f7c0  jnz     short loc_18000F7C6
0x18000f7c2  inc     ebx
0x18000f7c4  jmp     short loc_18000F78F
0x18000f7c6  mov     eax, [rcx+r15*8+8]
0x18000f7cb  cmp     [rdi+r12*8+10h], eax
0x18000f7d0  jnz     short loc_18000F7C2
0x18000f7d2  inc     ebp
0x18000f7d4  cmp     ebp, [rdi]
0x18000f7d6  jb      short loc_18000F78D
0x18000f7d8  mov     rax, [rsp+78h+arg_10]
0x18000f7e0  xor     r9d, r9d; EffectiveOnly
0x18000f7e3  mov     [rsp+78h+NewTokenHandle], rax; NewTokenHandle
0x18000f7e8  xor     r8d, r8d; ObjectAttributes
0x18000f7eb  mov     edx, 0F01FFh; DesiredAccess
0x18000f7f0  mov     dword ptr [rsp+78h+ReturnLength], 1; TokenType
0x18000f7f8  mov     rcx, r13; ExistingTokenHandle
0x18000f7fb  call    cs:__imp_NtDuplicateToken
0x18000f802  nop     dword ptr [rax+rax+00h]
0x18000f807  mov     ebx, eax
0x18000f809  test    rdi, rdi
0x18000f80c  jnz     short loc_18000F861
0x18000f80e  mov     rcx, gs:60h
0x18000f817  mov     r8, r14; P
0x18000f81a  xor     edx, edx; Flags
0x18000f81c  mov     rcx, [rcx+30h]; HeapHandle
0x18000f820  call    cs:__imp_RtlFreeHeap
0x18000f827  nop     dword ptr [rax+rax+00h]
0x18000f82c  mov     eax, ebx
0x18000f82e  mov     rbx, [rsp+78h+arg_0]
0x18000f836  add     rsp, 40h
0x18000f83a  pop     r15
0x18000f83c  pop     r14
0x18000f83e  pop     r13
0x18000f840  pop     r12
0x18000f842  pop     rdi
0x18000f843  pop     rsi
0x18000f844  pop     rbp
0x18000f845  retn
0x18000f847  mov     ebx, 0C0000017h
0x18000f84c  jmp     short loc_18000F82C
0x18000f84e  mov     ebx, 0C000000Dh
0x18000f853  jmp     short loc_18000F80E
0x18000f855  mov     ebx, 0C0000017h
0x18000f85a  jmp     short loc_18000F80E
0x18000f85c  mov     ebx, 0C000000Dh
0x18000f861  mov     rcx, gs:60h
0x18000f86a  mov     r8, rdi; P
0x18000f86d  xor     edx, edx; Flags
0x18000f86f  mov     rcx, [rcx+30h]; HeapHandle
0x18000f873  call    cs:__imp_RtlFreeHeap
0x18000f87a  nop     dword ptr [rax+rax+00h]
0x18000f87f  jmp     short loc_18000F80E
```
