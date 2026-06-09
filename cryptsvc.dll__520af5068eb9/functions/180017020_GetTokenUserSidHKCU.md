# GetTokenUserSidHKCU

- ea: `0x180017020`
- end: `0x180017146`
- name: `GetTokenUserSidHKCU`
- size: `294`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, HLOCAL *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009970`

## callees

- `0x18000e2f0`
- `0x180017020`
- `0x1800173b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001707b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001707b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001708c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800170d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001708c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800170d9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800170ef`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800170ef`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800170cd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800170cd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001706f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800170b5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001706f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800170b5`

## pseudocode

```c
__int64 __fastcall GetTokenUserSidHKCU(HANDLE TokenHandle, HLOCAL *a2)
{
  void *v2; // rbx
  unsigned int v5; // edi
  HLOCAL v6; // rax
  PSID *v7; // rsi
  DWORD LengthSid; // ebp
  HLOCAL v9; // rax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-128h] BYREF
  _BYTE TokenInformation[256]; // [rsp+38h] [rbp-120h] BYREF

  v2 = 0;
  *a2 = 0;
  TokenInformationLength = 256;
  v5 = GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x100u, &TokenInformationLength);
  if ( v5 )
  {
    v7 = (PSID *)TokenInformation;
    goto LABEL_7;
  }
  if ( GetLastError() == 122 )
  {
    v6 = LocalAlloc(0, TokenInformationLength);
    v2 = v6;
    if ( v6 )
    {
      v7 = (PSID *)v6;
      v5 = GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength);
      if ( v5 )
      {
LABEL_7:
        v5 = 0;
        LengthSid = GetLengthSid(*v7);
        v9 = LocalAlloc(0, LengthSid);
        *a2 = v9;
        if ( v9 )
        {
          v5 = CopySid(LengthSid, v9, *v7);
          if ( v5 )
            goto LABEL_11;
        }
      }
    }
  }
  if ( *a2 )
  {
    freeWithSavedLastError(*a2);
    *a2 = 0;
  }
LABEL_11:
  if ( v2 )
    freeWithSavedLastError(v2);
  return v5;
}

```

## disassembly

```asm
0x180017020  mov     [rsp+arg_10], rbx
0x180017025  mov     [rsp+arg_18], rbp
0x18001702a  push    rsi
0x18001702b  push    rdi
0x18001702c  push    r14
0x18001702e  sub     rsp, 140h
0x180017035  mov     rax, cs:__security_cookie
0x18001703c  xor     rax, rsp
0x18001703f  mov     [rsp+158h+var_20], rax
0x180017047  xor     ebx, ebx
0x180017049  lea     rax, [rsp+158h+TokenInformationLength]
0x18001704e  mov     r14, rdx
0x180017051  mov     [rdx], rbx
0x180017054  mov     r9d, 100h; TokenInformationLength
0x18001705a  mov     [rsp+158h+ReturnLength], rax; ReturnLength
0x18001705f  lea     r8, [rsp+158h+TokenInformation]; TokenInformation
0x180017064  mov     [rsp+158h+TokenInformationLength], r9d
0x180017069  lea     edx, [rbx+1]; TokenInformationClass
0x18001706c  mov     rbp, rcx
0x18001706f  call    cs:__imp_GetTokenInformation
0x180017075  mov     edi, eax
0x180017077  test    eax, eax
0x180017079  jnz     short loc_1800170C3
0x18001707b  call    cs:__imp_GetLastError
0x180017081  cmp     eax, 7Ah ; 'z'
0x180017084  jnz     short loc_1800170FB
0x180017086  mov     edx, [rsp+158h+TokenInformationLength]; uBytes
0x18001708a  xor     ecx, ecx; uFlags
0x18001708c  call    cs:__imp_LocalAlloc
0x180017092  mov     rbx, rax
0x180017095  test    rax, rax
0x180017098  jz      short loc_1800170FB
0x18001709a  mov     r9d, [rsp+158h+TokenInformationLength]; TokenInformationLength
0x18001709f  lea     edx, [rdi+1]; TokenInformationClass
0x1800170a2  mov     rsi, rax
0x1800170a5  mov     r8, rbx; TokenInformation
0x1800170a8  lea     rax, [rsp+158h+TokenInformationLength]
0x1800170ad  mov     rcx, rbp; TokenHandle
0x1800170b0  mov     [rsp+158h+ReturnLength], rax; ReturnLength
0x1800170b5  call    cs:__imp_GetTokenInformation
0x1800170bb  mov     edi, eax
0x1800170bd  test    eax, eax
0x1800170bf  jz      short loc_1800170FB
0x1800170c1  jmp     short loc_1800170C8
0x1800170c3  lea     rsi, [rsp+158h+TokenInformation]
0x1800170c8  mov     rcx, [rsi]; pSid
0x1800170cb  xor     edi, edi
0x1800170cd  call    cs:__imp_GetLengthSid
0x1800170d3  mov     edx, eax; uBytes
0x1800170d5  xor     ecx, ecx; uFlags
0x1800170d7  mov     ebp, eax
0x1800170d9  call    cs:__imp_LocalAlloc
0x1800170df  mov     [r14], rax
0x1800170e2  test    rax, rax
0x1800170e5  jz      short loc_1800170FB
0x1800170e7  mov     r8, [rsi]; pSourceSid
0x1800170ea  mov     rdx, rax; pDestinationSid
0x1800170ed  mov     ecx, ebp; nDestinationSidLength
0x1800170ef  call    cs:__imp_CopySid
0x1800170f5  mov     edi, eax
0x1800170f7  test    eax, eax
0x1800170f9  jnz     short loc_18001710F
0x1800170fb  mov     rcx, [r14]; hMem
0x1800170fe  test    rcx, rcx
0x180017101  jz      short loc_18001710F
0x180017103  call    freeWithSavedLastError
0x180017108  mov     qword ptr [r14], 0
0x18001710f  test    rbx, rbx
0x180017112  jz      short loc_18001711C
0x180017114  mov     rcx, rbx; hMem
0x180017117  call    freeWithSavedLastError
0x18001711c  mov     eax, edi
0x18001711e  mov     rcx, [rsp+158h+var_20]
0x180017126  xor     rcx, rsp; StackCookie
0x180017129  call    __security_check_cookie
0x18001712e  lea     r11, [rsp+158h+var_18]
0x180017136  mov     rbx, [r11+30h]
0x18001713a  mov     rbp, [r11+38h]
0x18001713e  mov     rsp, r11
0x180017141  pop     r14
0x180017143  pop     rdi
0x180017144  pop     rsi
0x180017145  retn
```
