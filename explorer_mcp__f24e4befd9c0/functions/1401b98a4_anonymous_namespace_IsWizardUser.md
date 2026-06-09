# _anonymous_namespace_::IsWizardUser

- ea: `0x1401b98a4`
- end: `0x1401b99c1`
- name: `_anonymous_namespace_::IsWizardUser`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1401b8e0c`

## callees

- `0x14000e160`
- `0x14001c364`
- `0x140027550`
- `0x1401b98a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b9918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b9918`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1401b98d2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1401b98d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1401b98ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1401b98ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b99a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b99a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401b9991`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401b9991`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1401b9904`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1401b9952`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1401b9904`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1401b9952`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1401b9971`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1401b9971`

## pseudocode

```c
bool anonymous_namespace_::IsWizardUser()
{
  bool v0; // di
  HANDLE CurrentProcess; // rax
  void **v2; // rbx
  void *v3; // rcx
  DWORD TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+28h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp+30h] BYREF

  v0 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    TokenInformationLength = 0;
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
    {
      v2 = (void **)wil::details::heap_allocator::allocate(TokenInformationLength);
      if ( v2 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
        {
          v3 = *v2;
          StringSid = 0;
          if ( ConvertSidToStringSidW(v3, &StringSid) )
          {
            v0 = IsWizardOnlyAccount(StringSid);
            LocalFree(StringSid);
          }
        }
        operator delete(v2);
      }
    }
    CloseHandle(TokenHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x1401b98a4  push    rbp
0x1401b98a6  push    rbx
0x1401b98a7  push    rdi
0x1401b98a8  mov     rbp, rsp
0x1401b98ab  sub     rsp, 30h
0x1401b98af  xor     dil, dil
0x1401b98b2  mov     [rbp+TokenHandle], 0
0x1401b98ba  call    cs:__imp_GetCurrentProcess
0x1401b98c1  nop     dword ptr [rax+rax+00h]
0x1401b98c6  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1401b98ca  mov     edx, 8; DesiredAccess
0x1401b98cf  mov     rcx, rax; ProcessHandle
0x1401b98d2  call    cs:__imp_OpenProcessToken
0x1401b98d9  nop     dword ptr [rax+rax+00h]
0x1401b98de  test    eax, eax
0x1401b98e0  jz      loc_1401B99B5
0x1401b98e6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1401b98ea  lea     rax, [rbp+TokenInformationLength]
0x1401b98ee  xor     r9d, r9d; TokenInformationLength
0x1401b98f1  mov     [rbp+TokenInformationLength], 0
0x1401b98f8  xor     r8d, r8d; TokenInformation
0x1401b98fb  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1401b9900  lea     edx, [r9+1]; TokenInformationClass
0x1401b9904  call    cs:__imp_GetTokenInformation
0x1401b990b  nop     dword ptr [rax+rax+00h]
0x1401b9910  test    eax, eax
0x1401b9912  jnz     loc_1401B99A5
0x1401b9918  call    cs:__imp_GetLastError
0x1401b991f  nop     dword ptr [rax+rax+00h]
0x1401b9924  cmp     eax, 7Ah ; 'z'
0x1401b9927  jnz     short loc_1401B99A5
0x1401b9929  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x1401b992c  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x1401b9931  mov     rbx, rax
0x1401b9934  test    rax, rax
0x1401b9937  jz      short loc_1401B99A5
0x1401b9939  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1401b993d  lea     rax, [rbp+TokenInformationLength]
0x1401b9941  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1401b9945  mov     r8, rbx; TokenInformation
0x1401b9948  mov     edx, 1; TokenInformationClass
0x1401b994d  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1401b9952  call    cs:__imp_GetTokenInformation
0x1401b9959  nop     dword ptr [rax+rax+00h]
0x1401b995e  test    eax, eax
0x1401b9960  jz      short loc_1401B999D
0x1401b9962  mov     rcx, [rbx]; Sid
0x1401b9965  lea     rdx, [rbp+StringSid]; StringSid
0x1401b9969  mov     [rbp+StringSid], 0
0x1401b9971  call    cs:__imp_ConvertSidToStringSidW
0x1401b9978  nop     dword ptr [rax+rax+00h]
0x1401b997d  test    eax, eax
0x1401b997f  jz      short loc_1401B999D
0x1401b9981  mov     rcx, [rbp+StringSid]; unsigned __int16 *
0x1401b9985  call    ?IsWizardOnlyAccount@@YA_NPEBG@Z; IsWizardOnlyAccount(ushort const *)
0x1401b998a  mov     rcx, [rbp+StringSid]; hMem
0x1401b998e  mov     dil, al
0x1401b9991  call    cs:__imp_LocalFree
0x1401b9998  nop     dword ptr [rax+rax+00h]
0x1401b999d  mov     rcx, rbx; lpMem
0x1401b99a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1401b99a5  mov     rcx, [rbp+TokenHandle]; hObject
0x1401b99a9  call    cs:__imp_CloseHandle
0x1401b99b0  nop     dword ptr [rax+rax+00h]
0x1401b99b5  mov     al, dil
0x1401b99b8  add     rsp, 30h
0x1401b99bc  pop     rdi
0x1401b99bd  pop     rbx
0x1401b99be  pop     rbp
0x1401b99bf  retn
```
