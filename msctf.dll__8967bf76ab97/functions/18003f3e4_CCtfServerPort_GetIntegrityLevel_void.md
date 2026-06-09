# CCtfServerPort::GetIntegrityLevel(void *)

- ea: `0x18003f3e4`
- end: `0x18003f4d8`
- name: `?GetIntegrityLevel@CCtfServerPort@@AEAAKPEAX@Z`
- size: `244`
- prototype: `unsigned int(CCtfServerPort *__hidden this, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004004c`

## callees

- `0x18003f3e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f43f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f43f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003f40f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003f40f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f4c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f4c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f450`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f450`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f4b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f4b5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003f487`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003f495`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003f487`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18003f495`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003f435`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003f47a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003f435`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003f47a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003f4a5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003f4a5`

## pseudocode

```c
__int64 __fastcall CCtfServerPort::GetIntegrityLevel(CCtfServerPort *this, void *a2)
{
  DWORD v2; // edi
  PSID *v3; // rbx
  PUCHAR SidSubAuthorityCount; // rax
  PDWORD SidSubAuthority; // rax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  int v8; // [rsp+44h] [rbp+Ch]
  HANDLE TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v8 = HIDWORD(this);
  TokenHandle = 0;
  v2 = 0;
  TokenInformationLength = 0;
  if ( OpenProcessToken(a2, 8u, &TokenHandle)
    && (GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) || GetLastError() == 122) )
  {
    v3 = (PSID *)LocalAlloc(0, TokenInformationLength);
    if ( v3 )
    {
      if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v3, TokenInformationLength, &TokenInformationLength) )
      {
        if ( GetSidSubAuthorityCount(*v3) )
        {
          SidSubAuthorityCount = GetSidSubAuthorityCount(*v3);
          SidSubAuthority = GetSidSubAuthority(*v3, (unsigned __int8)(*SidSubAuthorityCount - 1));
          if ( SidSubAuthority )
            v2 = *SidSubAuthority;
        }
      }
      LocalFree(v3);
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v2;
}

```

## disassembly

```asm
0x18003f3e4  mov     rax, rsp
0x18003f3e7  mov     [rax+10h], rbx
0x18003f3eb  mov     [rax+8], rcx
0x18003f3ef  push    rdi
0x18003f3f0  sub     rsp, 30h
0x18003f3f4  mov     rcx, rdx; ProcessHandle
0x18003f3f7  mov     qword ptr [rax+18h], 0
0x18003f3ff  xor     edi, edi
0x18003f401  mov     dword ptr [rax+8], 0
0x18003f408  lea     r8, [rax+18h]; TokenHandle
0x18003f40c  lea     edx, [rdi+8]; DesiredAccess
0x18003f40f  call    cs:__imp_OpenProcessToken
0x18003f415  test    eax, eax
0x18003f417  jz      loc_18003F4BB
0x18003f41d  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18003f422  lea     rax, [rsp+38h+TokenInformationLength]
0x18003f427  xor     r9d, r9d; TokenInformationLength
0x18003f42a  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18003f42f  xor     r8d, r8d; TokenInformation
0x18003f432  lea     edx, [rdi+19h]; TokenInformationClass
0x18003f435  call    cs:__imp_GetTokenInformation
0x18003f43b  test    eax, eax
0x18003f43d  jnz     short loc_18003F44A
0x18003f43f  call    cs:__imp_GetLastError
0x18003f445  cmp     eax, 7Ah ; 'z'
0x18003f448  jnz     short loc_18003F4BB
0x18003f44a  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x18003f44e  xor     ecx, ecx; uFlags
0x18003f450  call    cs:__imp_LocalAlloc
0x18003f456  mov     rbx, rax
0x18003f459  test    rax, rax
0x18003f45c  jz      short loc_18003F4BB
0x18003f45e  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18003f463  lea     rax, [rsp+38h+TokenInformationLength]
0x18003f468  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18003f46d  mov     r8, rbx; TokenInformation
0x18003f470  mov     edx, 19h; TokenInformationClass
0x18003f475  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18003f47a  call    cs:__imp_GetTokenInformation
0x18003f480  test    eax, eax
0x18003f482  jz      short loc_18003F4B2
0x18003f484  mov     rcx, [rbx]; pSid
0x18003f487  call    cs:__imp_GetSidSubAuthorityCount
0x18003f48d  test    rax, rax
0x18003f490  jz      short loc_18003F4B2
0x18003f492  mov     rcx, [rbx]; pSid
0x18003f495  call    cs:__imp_GetSidSubAuthorityCount
0x18003f49b  mov     cl, [rax]
0x18003f49d  dec     cl
0x18003f49f  movzx   edx, cl; nSubAuthority
0x18003f4a2  mov     rcx, [rbx]; pSid
0x18003f4a5  call    cs:__imp_GetSidSubAuthority
0x18003f4ab  test    rax, rax
0x18003f4ae  jz      short loc_18003F4B2
0x18003f4b0  mov     edi, [rax]
0x18003f4b2  mov     rcx, rbx; hMem
0x18003f4b5  call    cs:__imp_LocalFree
0x18003f4bb  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18003f4c0  test    rcx, rcx
0x18003f4c3  jz      short loc_18003F4CB
0x18003f4c5  call    cs:__imp_CloseHandle
0x18003f4cb  mov     rbx, [rsp+38h+arg_8]
0x18003f4d0  mov     eax, edi
0x18003f4d2  add     rsp, 30h
0x18003f4d6  pop     rdi
0x18003f4d7  retn
```
