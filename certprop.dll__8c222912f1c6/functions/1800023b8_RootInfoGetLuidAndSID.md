# RootInfoGetLuidAndSID

- ea: `0x1800023b8`
- end: `0x18000255a`
- name: `RootInfoGetLuidAndSID`
- size: `418`
- prototype: `__int64 __fastcall(__int64, __int64, void *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002690`

## callees

- `0x1800023b8`
- `0x180016090`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002473`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800024da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002473`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800024da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000250f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000252f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000250f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000252f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024fb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800024c4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800024c4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800024b2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800024b2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800024f1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800024f1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002418`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002445`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000249b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002418`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002445`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000249b`

## pseudocode

```c
__int64 __fastcall RootInfoGetLuidAndSID(__int64 a1, __int64 a2, void *a3, _QWORD *a4, _QWORD *a5)
{
  DWORD LastError; // ebx
  PSID *v8; // rdi
  void *v9; // rax
  void *v10; // rsi
  __int64 v11; // rax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-50h] BYREF
  _OWORD TokenInformation[3]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v15; // [rsp+68h] [rbp-18h]

  v15 = 0;
  TokenInformationLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( !GetTokenInformation(a3, TokenStatistics, TokenInformation, 0x38u, &TokenInformationLength) )
    return GetLastError();
  if ( GetTokenInformation(a3, TokenUser, 0, 0, &TokenInformationLength) )
    return 87;
  if ( GetLastError() == 122 )
  {
    LastError = 8;
    v8 = (PSID *)HeapAlloc(g_hHeap, 8u, TokenInformationLength);
    if ( v8 )
    {
      if ( GetTokenInformation(a3, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
      {
        if ( IsValidSid(*v8) )
        {
          TokenInformationLength = GetLengthSid(*v8);
          v9 = HeapAlloc(g_hHeap, 8u, TokenInformationLength);
          v10 = v9;
          if ( v9 )
          {
            if ( CopySid(TokenInformationLength, v9, *v8) )
            {
              v11 = *((_QWORD *)&TokenInformation[0] + 1);
              LastError = 0;
              *a5 = v10;
              *a4 = v11;
            }
            else
            {
              LastError = GetLastError();
              HeapFree(g_hHeap, 0, v10);
            }
          }
        }
        else
        {
          LastError = 87;
        }
      }
      else
      {
        LastError = GetLastError();
      }
      HeapFree(g_hHeap, 0, v8);
    }
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x1800023b8  mov     [rsp-28h+arg_0], rbx
0x1800023bd  push    rbp
0x1800023be  push    rsi
0x1800023bf  push    rdi
0x1800023c0  push    r14
0x1800023c2  push    r15
0x1800023c4  mov     rbp, rsp
0x1800023c7  sub     rsp, 80h
0x1800023ce  mov     rax, cs:__security_cookie
0x1800023d5  xor     rax, rsp
0x1800023d8  mov     [rbp+var_10], rax
0x1800023dc  mov     r15, [rbp+arg_20]
0x1800023e0  xor     eax, eax
0x1800023e2  xorps   xmm0, xmm0
0x1800023e5  mov     [rbp+var_18], rax
0x1800023e9  mov     rsi, r8
0x1800023ec  mov     [rbp+TokenInformationLength], eax
0x1800023ef  mov     r14, r9
0x1800023f2  lea     rax, [rbp+TokenInformationLength]
0x1800023f6  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800023fc  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180002401  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180002405  mov     rcx, rsi; TokenHandle
0x180002408  movups  [rbp+TokenInformation], xmm0
0x18000240c  lea     edx, [r9-2Eh]; TokenInformationClass
0x180002410  movups  [rbp+var_38], xmm0
0x180002414  movups  [rbp+var_28], xmm0
0x180002418  call    cs:__imp_GetTokenInformation
0x18000241e  test    eax, eax
0x180002420  jnz     short loc_18000242F
0x180002422  call    cs:__imp_GetLastError
0x180002428  mov     ebx, eax
0x18000242a  jmp     loc_180002535
0x18000242f  xor     r9d, r9d; TokenInformationLength
0x180002432  lea     rax, [rbp+TokenInformationLength]
0x180002436  xor     r8d, r8d; TokenInformation
0x180002439  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x18000243e  mov     rcx, rsi; TokenHandle
0x180002441  lea     edx, [r9+1]; TokenInformationClass
0x180002445  call    cs:__imp_GetTokenInformation
0x18000244b  cmp     eax, 1
0x18000244e  jnz     short loc_180002458
0x180002450  lea     ebx, [rax+56h]
0x180002453  jmp     loc_180002535
0x180002458  call    cs:__imp_GetLastError
0x18000245e  cmp     eax, 7Ah ; 'z'
0x180002461  jnz     short loc_180002422
0x180002463  mov     r8d, [rbp+TokenInformationLength]; dwBytes
0x180002467  lea     ebx, [rax-72h]
0x18000246a  mov     rcx, cs:g_hHeap; hHeap
0x180002471  mov     edx, ebx; dwFlags
0x180002473  call    cs:__imp_HeapAlloc
0x180002479  mov     rdi, rax
0x18000247c  test    rax, rax
0x18000247f  jz      loc_180002535
0x180002485  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180002489  lea     rax, [rbp+TokenInformationLength]
0x18000248d  mov     r8, rdi; TokenInformation
0x180002490  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180002495  lea     edx, [rbx-7]; TokenInformationClass
0x180002498  mov     rcx, rsi; TokenHandle
0x18000249b  call    cs:__imp_GetTokenInformation
0x1800024a1  test    eax, eax
0x1800024a3  jnz     short loc_1800024AF
0x1800024a5  call    cs:__imp_GetLastError
0x1800024ab  mov     ebx, eax
0x1800024ad  jmp     short loc_180002523
0x1800024af  mov     rcx, [rdi]; pSid
0x1800024b2  call    cs:__imp_IsValidSid
0x1800024b8  test    eax, eax
0x1800024ba  jnz     short loc_1800024C1
0x1800024bc  lea     ebx, [rax+57h]
0x1800024bf  jmp     short loc_180002523
0x1800024c1  mov     rcx, [rdi]; pSid
0x1800024c4  call    cs:__imp_GetLengthSid
0x1800024ca  mov     rcx, cs:g_hHeap; hHeap
0x1800024d1  mov     edx, ebx; dwFlags
0x1800024d3  mov     r8d, eax; dwBytes
0x1800024d6  mov     [rbp+TokenInformationLength], r8d
0x1800024da  call    cs:__imp_HeapAlloc
0x1800024e0  mov     rsi, rax
0x1800024e3  test    rax, rax
0x1800024e6  jz      short loc_180002523
0x1800024e8  mov     r8, [rdi]; pSourceSid
0x1800024eb  mov     rdx, rax; pDestinationSid
0x1800024ee  mov     ecx, [rbp+TokenInformationLength]; nDestinationSidLength
0x1800024f1  call    cs:__imp_CopySid
0x1800024f7  test    eax, eax
0x1800024f9  jnz     short loc_180002517
0x1800024fb  call    cs:__imp_GetLastError
0x180002501  mov     rcx, cs:g_hHeap; hHeap
0x180002508  mov     r8, rsi; lpMem
0x18000250b  xor     edx, edx; dwFlags
0x18000250d  mov     ebx, eax
0x18000250f  call    cs:__imp_HeapFree
0x180002515  jmp     short loc_180002523
0x180002517  mov     rax, qword ptr [rbp+TokenInformation+8]
0x18000251b  xor     ebx, ebx
0x18000251d  mov     [r15], rsi
0x180002520  mov     [r14], rax
0x180002523  mov     rcx, cs:g_hHeap; hHeap
0x18000252a  mov     r8, rdi; lpMem
0x18000252d  xor     edx, edx; dwFlags
0x18000252f  call    cs:__imp_HeapFree
0x180002535  mov     eax, ebx
0x180002537  mov     rcx, [rbp+var_10]
0x18000253b  xor     rcx, rsp; StackCookie
0x18000253e  call    __security_check_cookie
0x180002543  mov     rbx, [rsp+80h+arg_0]
0x18000254b  add     rsp, 80h
0x180002552  pop     r15
0x180002554  pop     r14
0x180002556  pop     rdi
0x180002557  pop     rsi
0x180002558  pop     rbp
0x180002559  retn
```
