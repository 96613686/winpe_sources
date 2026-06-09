# _anonymous_namespace_::IsWizardUser

- ea: `0x1401bb2c0`
- end: `0x1401bb3a8`
- name: `_anonymous_namespace_::IsWizardUser`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1401ba8e8`

## callees

- `0x14000a880`
- `0x140016b3c`
- `0x14001a3c0`
- `0x1401bb2c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401bb31e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401bb31e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1401bb2d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1401bb2d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1401bb2e8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1401bb2e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bb397`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bb397`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401bb385`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401bb385`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1401bb314`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1401bb352`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1401bb314`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1401bb352`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1401bb36b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1401bb36b`

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
0x1401bb2c0  push    rbp
0x1401bb2c2  push    rbx
0x1401bb2c3  push    rdi
0x1401bb2c4  mov     rbp, rsp
0x1401bb2c7  sub     rsp, 30h
0x1401bb2cb  xor     dil, dil
0x1401bb2ce  mov     [rbp+TokenHandle], 0
0x1401bb2d6  call    cs:__imp_GetCurrentProcess
0x1401bb2dc  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1401bb2e0  mov     edx, 8; DesiredAccess
0x1401bb2e5  mov     rcx, rax; ProcessHandle
0x1401bb2e8  call    cs:__imp_OpenProcessToken
0x1401bb2ee  test    eax, eax
0x1401bb2f0  jz      loc_1401BB39D
0x1401bb2f6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1401bb2fa  lea     rax, [rbp+TokenInformationLength]
0x1401bb2fe  xor     r9d, r9d; TokenInformationLength
0x1401bb301  mov     [rbp+TokenInformationLength], 0
0x1401bb308  xor     r8d, r8d; TokenInformation
0x1401bb30b  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1401bb310  lea     edx, [r9+1]; TokenInformationClass
0x1401bb314  call    cs:__imp_GetTokenInformation
0x1401bb31a  test    eax, eax
0x1401bb31c  jnz     short loc_1401BB393
0x1401bb31e  call    cs:__imp_GetLastError
0x1401bb324  cmp     eax, 7Ah ; 'z'
0x1401bb327  jnz     short loc_1401BB393
0x1401bb329  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x1401bb32c  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x1401bb331  mov     rbx, rax
0x1401bb334  test    rax, rax
0x1401bb337  jz      short loc_1401BB393
0x1401bb339  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1401bb33d  lea     rax, [rbp+TokenInformationLength]
0x1401bb341  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1401bb345  mov     r8, rbx; TokenInformation
0x1401bb348  mov     edx, 1; TokenInformationClass
0x1401bb34d  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1401bb352  call    cs:__imp_GetTokenInformation
0x1401bb358  test    eax, eax
0x1401bb35a  jz      short loc_1401BB38B
0x1401bb35c  mov     rcx, [rbx]; Sid
0x1401bb35f  lea     rdx, [rbp+StringSid]; StringSid
0x1401bb363  mov     [rbp+StringSid], 0
0x1401bb36b  call    cs:__imp_ConvertSidToStringSidW
0x1401bb371  test    eax, eax
0x1401bb373  jz      short loc_1401BB38B
0x1401bb375  mov     rcx, [rbp+StringSid]; unsigned __int16 *
0x1401bb379  call    ?IsWizardOnlyAccount@@YA_NPEBG@Z; IsWizardOnlyAccount(ushort const *)
0x1401bb37e  mov     rcx, [rbp+StringSid]; hMem
0x1401bb382  mov     dil, al
0x1401bb385  call    cs:__imp_LocalFree
0x1401bb38b  mov     rcx, rbx; lpMem
0x1401bb38e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1401bb393  mov     rcx, [rbp+TokenHandle]; hObject
0x1401bb397  call    cs:__imp_CloseHandle
0x1401bb39d  mov     al, dil
0x1401bb3a0  add     rsp, 30h
0x1401bb3a4  pop     rdi
0x1401bb3a5  pop     rbx
0x1401bb3a6  pop     rbp
0x1401bb3a7  retn
```
