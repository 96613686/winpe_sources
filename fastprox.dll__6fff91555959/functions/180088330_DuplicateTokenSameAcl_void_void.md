# DuplicateTokenSameAcl(void *,void * *)

- ea: `0x180088330`
- end: `0x180088496`
- name: `?DuplicateTokenSameAcl@@YAHPEAXPEAPEAX@Z`
- size: `358`
- prototype: `__int64 __fastcall(HANDLE hExistingToken, PHANDLE phNewToken)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180087f54`

## callees

- `0x180088330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800883ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800883ea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180088377`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800883b0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180088377`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800883b0`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800883da`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180088427`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800883da`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180088427`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180088466`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180088466`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800883ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800883ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180088471`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180088471`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DuplicateTokenSameAcl(HANDLE hExistingToken, PHANDLE phNewToken)
{
  unsigned int KernelObjectSecurity; // ebx
  HLOCAL v5; // rax
  void *v6; // rbx
  unsigned int v7; // edi
  SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+30h] [rbp-30h] BYREF
  int TokenInformation; // [rsp+34h] [rbp-2Ch] BYREF
  HLOCAL v11; // [rsp+38h] [rbp-28h]
  struct _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+40h] [rbp-20h] BYREF
  DWORD nLengthNeeded; // [rsp+90h] [rbp+30h] BYREF
  DWORD ReturnLength; // [rsp+98h] [rbp+38h] BYREF

  ImpersonationLevel = SecurityAnonymous;
  TokenInformation = 0;
  ReturnLength = 4;
  if ( !GetTokenInformation(hExistingToken, TokenType, &TokenInformation, 4u, &ReturnLength) )
    return 0;
  if ( TokenInformation != 1 )
  {
    ReturnLength = 4;
    if ( GetTokenInformation(hExistingToken, TokenImpersonationLevel, &ImpersonationLevel, 4u, &ReturnLength) )
      goto LABEL_5;
    return 0;
  }
  ImpersonationLevel = SecurityImpersonation;
LABEL_5:
  nLengthNeeded = 0;
  KernelObjectSecurity = GetKernelObjectSecurity(hExistingToken, 4u, 0, 0, &nLengthNeeded);
  if ( KernelObjectSecurity || GetLastError() != 122 )
    return KernelObjectSecurity;
  v5 = LocalAlloc(0x40u, nLengthNeeded);
  v6 = v5;
  if ( !v5 )
    return 0;
  v11 = v5;
  if ( GetKernelObjectSecurity(hExistingToken, 4u, v5, nLengthNeeded, &nLengthNeeded) )
  {
    *(_QWORD *)&TokenAttributes.nLength = 24;
    *(_QWORD *)&TokenAttributes.bInheritHandle = 0;
    TokenAttributes.lpSecurityDescriptor = v6;
    v7 = DuplicateTokenEx(hExistingToken, 0x2Cu, &TokenAttributes, ImpersonationLevel, TokenImpersonation, phNewToken);
  }
  else
  {
    v7 = 0;
  }
  LocalFree(v6);
  return v7;
}

```

## disassembly

```asm
0x180088330  mov     [rsp-18h+arg_0], rbx
0x180088335  mov     [rsp-18h+arg_8], rsi
0x18008833a  push    rbp
0x18008833b  push    rdi
0x18008833c  push    r15
0x18008833e  mov     rbp, rsp
0x180088341  sub     rsp, 60h
0x180088345  mov     rsi, rdx
0x180088348  mov     rdi, rcx
0x18008834b  mov     [rbp+ImpersonationLevel], 0
0x180088352  mov     [rbp+TokenInformation], 0
0x180088359  mov     r15d, 4
0x18008835f  mov     [rbp+arg_18], r15d
0x180088363  lea     rax, [rbp+arg_18]
0x180088367  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x18008836c  mov     r9d, r15d; TokenInformationLength
0x18008836f  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180088373  lea     edx, [r15+4]; TokenInformationClass
0x180088377  call    cs:__imp_GetTokenInformation
0x18008837d  test    eax, eax
0x18008837f  jz      loc_18008847F
0x180088385  cmp     [rbp+TokenInformation], 1
0x180088389  jnz     short loc_180088394
0x18008838b  mov     [rbp+ImpersonationLevel], 2
0x180088392  jmp     short loc_1800883BE
0x180088394  mov     [rbp+arg_18], r15d
0x180088398  lea     rax, [rbp+arg_18]
0x18008839c  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x1800883a1  mov     r9d, r15d; TokenInformationLength
0x1800883a4  lea     r8, [rbp+ImpersonationLevel]; TokenInformation
0x1800883a8  mov     edx, 9; TokenInformationClass
0x1800883ad  mov     rcx, rdi; TokenHandle
0x1800883b0  call    cs:__imp_GetTokenInformation
0x1800883b6  test    eax, eax
0x1800883b8  jz      loc_18008847F
0x1800883be  mov     [rbp+nLengthNeeded], 0
0x1800883c5  lea     rax, [rbp+nLengthNeeded]
0x1800883c9  mov     [rsp+60h+ReturnLength], rax; lpnLengthNeeded
0x1800883ce  xor     r9d, r9d; nLength
0x1800883d1  xor     r8d, r8d; pSecurityDescriptor
0x1800883d4  mov     edx, r15d; RequestedInformation
0x1800883d7  mov     rcx, rdi; Handle
0x1800883da  call    cs:__imp_GetKernelObjectSecurity
0x1800883e0  mov     ebx, eax
0x1800883e2  test    eax, eax
0x1800883e4  jnz     loc_18008847B
0x1800883ea  call    cs:__imp_GetLastError
0x1800883f0  cmp     eax, 7Ah ; 'z'
0x1800883f3  jnz     loc_18008847B
0x1800883f9  mov     edx, [rbp+nLengthNeeded]; uBytes
0x1800883fc  lea     ecx, [rbx+40h]; uFlags
0x1800883ff  call    cs:__imp_LocalAlloc
0x180088405  mov     rbx, rax
0x180088408  test    rax, rax
0x18008840b  jz      short loc_18008847F
0x18008840d  mov     [rbp+var_28], rax
0x180088411  lea     rax, [rbp+nLengthNeeded]
0x180088415  mov     [rsp+60h+ReturnLength], rax; lpnLengthNeeded
0x18008841a  mov     r9d, [rbp+nLengthNeeded]; nLength
0x18008841e  mov     r8, rbx; pSecurityDescriptor
0x180088421  mov     edx, r15d; RequestedInformation
0x180088424  mov     rcx, rdi; Handle
0x180088427  call    cs:__imp_GetKernelObjectSecurity
0x18008842d  test    eax, eax
0x18008842f  jnz     short loc_180088435
0x180088431  xor     edi, edi
0x180088433  jmp     short loc_18008846E
0x180088435  mov     qword ptr [rbp+TokenAttributes.nLength], 18h
0x18008843d  mov     qword ptr [rbp+TokenAttributes.bInheritHandle], 0
0x180088445  mov     [rbp+TokenAttributes.lpSecurityDescriptor], rbx
0x180088449  mov     [rsp+60h+phNewToken], rsi; phNewToken
0x18008844e  mov     dword ptr [rsp+60h+ReturnLength], 2; TokenType
0x180088456  mov     r9d, [rbp+ImpersonationLevel]; ImpersonationLevel
0x18008845a  lea     r8, [rbp+TokenAttributes]; lpTokenAttributes
0x18008845e  mov     edx, 2Ch ; ','; dwDesiredAccess
0x180088463  mov     rcx, rdi; hExistingToken
0x180088466  call    cs:__imp_DuplicateTokenEx
0x18008846c  mov     edi, eax
0x18008846e  mov     rcx, rbx; hMem
0x180088471  call    cs:__imp_LocalFree
0x180088477  mov     eax, edi
0x180088479  jmp     short loc_180088481
0x18008847b  mov     eax, ebx
0x18008847d  jmp     short loc_180088481
0x18008847f  xor     eax, eax
0x180088481  lea     r11, [rsp+60h+var_s0]
0x180088486  mov     rbx, [r11+20h]
0x18008848a  mov     rsi, [r11+28h]
0x18008848e  mov     rsp, r11
0x180088491  pop     r15
0x180088493  pop     rdi
0x180088494  pop     rbp
0x180088495  retn
```
