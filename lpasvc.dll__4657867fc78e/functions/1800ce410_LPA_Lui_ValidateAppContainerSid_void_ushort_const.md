# LPA::Lui::ValidateAppContainerSid(void *,ushort const *)

- ea: `0x1800ce410`
- end: `0x1800ce574`
- name: `?ValidateAppContainerSid@Lui@LPA@@CAJPEAXPEBG@Z`
- size: `356`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPCWSTR StringSid)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800ce810`

## callees

- `0x18000e430`
- `0x180068c64`
- `0x18006ba8c`
- `0x1800ce410`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce4b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce4b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ce55f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ce55f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce477`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce4aa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce4f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce477`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce4aa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ce4f5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800ce51b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800ce51b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ce444`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ce444`

## pseudocode

```c
__int64 __fastcall LPA::Lui::ValidateAppContainerSid(HANDLE TokenHandle, LPCWSTR StringSid)
{
  int LastErrorToHResultAndForceFailure; // ebx
  CommonUtil *v4; // rcx
  CommonUtil *v5; // rcx
  unsigned __int64 v6; // rdx
  CommonUtil *v7; // rcx
  PSID *v8; // rdi
  const struct std::nothrow_t *v9; // rdx
  CommonUtil *v10; // rcx
  PSID Sid; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+30h] BYREF
  int TokenInformation; // [rsp+78h] [rbp+38h] BYREF

  Sid = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  LastErrorToHResultAndForceFailure = 0;
  if ( ConvertStringSidToSidW(StringSid, &Sid)
    || (LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v4),
        LastErrorToHResultAndForceFailure >= 0) )
  {
    if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &TokenInformationLength) )
    {
      if ( !TokenInformation )
      {
        LastErrorToHResultAndForceFailure = -2147024891;
        goto LABEL_22;
      }
    }
    else
    {
      LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v5);
    }
    if ( LastErrorToHResultAndForceFailure < 0 )
      goto LABEL_22;
    if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
    {
      LastErrorToHResultAndForceFailure = -2147418113;
    }
    else
    {
      if ( GetLastError() != 122 )
        LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v7);
      if ( LastErrorToHResultAndForceFailure >= 0 )
      {
        v8 = (PSID *)LPA::Util::CustomAllocator(TokenInformationLength, v6);
        if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, v8, TokenInformationLength, &TokenInformationLength)
          || (LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v10),
              LastErrorToHResultAndForceFailure >= 0) )
        {
          if ( v8 && *v8 )
          {
            if ( !EqualSid(*v8, Sid) )
              LastErrorToHResultAndForceFailure = -2147024891;
LABEL_20:
            operator delete(v8, v9);
            goto LABEL_22;
          }
          LastErrorToHResultAndForceFailure = -2147418113;
        }
        if ( !v8 )
          goto LABEL_22;
        goto LABEL_20;
      }
    }
  }
LABEL_22:
  if ( Sid )
    LocalFree(Sid);
  return (unsigned int)LastErrorToHResultAndForceFailure;
}

```

## disassembly

```asm
0x1800ce410  mov     [rsp-18h+arg_0], rbx
0x1800ce415  push    rbp
0x1800ce416  push    rsi
0x1800ce417  push    rdi
0x1800ce418  mov     rbp, rsp
0x1800ce41b  sub     rsp, 40h
0x1800ce41f  mov     rax, rdx
0x1800ce422  mov     [rbp+Sid], 0
0x1800ce42a  mov     rsi, rcx
0x1800ce42d  mov     [rbp+TokenInformation], 0
0x1800ce434  mov     rcx, rax; StringSid
0x1800ce437  mov     [rbp+TokenInformationLength], 0
0x1800ce43e  lea     rdx, [rbp+Sid]; Sid
0x1800ce442  xor     ebx, ebx
0x1800ce444  call    cs:__imp_ConvertStringSidToSidW
0x1800ce44a  test    eax, eax
0x1800ce44c  jnz     short loc_1800CE45D
0x1800ce44e  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ce453  mov     ebx, eax
0x1800ce455  test    eax, eax
0x1800ce457  js      loc_1800CE556
0x1800ce45d  mov     r9d, 4; TokenInformationLength
0x1800ce463  lea     rax, [rbp+TokenInformationLength]
0x1800ce467  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800ce46b  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800ce470  mov     rcx, rsi; TokenHandle
0x1800ce473  lea     edx, [r9+19h]; TokenInformationClass
0x1800ce477  call    cs:__imp_GetTokenInformation
0x1800ce47d  test    eax, eax
0x1800ce47f  jnz     loc_1800CE52C
0x1800ce485  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ce48a  mov     ebx, eax
0x1800ce48c  test    ebx, ebx
0x1800ce48e  js      loc_1800CE556
0x1800ce494  xor     r9d, r9d; TokenInformationLength
0x1800ce497  lea     rax, [rbp+TokenInformationLength]
0x1800ce49b  xor     r8d, r8d; TokenInformation
0x1800ce49e  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800ce4a3  mov     rcx, rsi; TokenHandle
0x1800ce4a6  lea     edx, [r9+1Fh]; TokenInformationClass
0x1800ce4aa  call    cs:__imp_GetTokenInformation
0x1800ce4b0  test    eax, eax
0x1800ce4b2  jnz     loc_1800CE551
0x1800ce4b8  call    cs:__imp_GetLastError
0x1800ce4be  cmp     eax, 7Ah ; 'z'
0x1800ce4c1  jz      short loc_1800CE4CA
0x1800ce4c3  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ce4c8  mov     ebx, eax
0x1800ce4ca  test    ebx, ebx
0x1800ce4cc  js      loc_1800CE556
0x1800ce4d2  mov     ecx, [rbp+TokenInformationLength]; Size
0x1800ce4d5  call    ?CustomAllocator@Util@LPA@@YAPEAX_K@Z; LPA::Util::CustomAllocator(unsigned __int64)
0x1800ce4da  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800ce4de  mov     rdi, rax
0x1800ce4e1  lea     rax, [rbp+TokenInformationLength]
0x1800ce4e5  mov     r8, rdi; TokenInformation
0x1800ce4e8  mov     edx, 1Fh; TokenInformationClass
0x1800ce4ed  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800ce4f2  mov     rcx, rsi; TokenHandle
0x1800ce4f5  call    cs:__imp_GetTokenInformation
0x1800ce4fb  test    eax, eax
0x1800ce4fd  jnz     short loc_1800CE50A
0x1800ce4ff  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ce504  mov     ebx, eax
0x1800ce506  test    eax, eax
0x1800ce508  js      short loc_1800CE542
0x1800ce50a  test    rdi, rdi
0x1800ce50d  jz      short loc_1800CE53D
0x1800ce50f  mov     rcx, [rdi]; pSid1
0x1800ce512  test    rcx, rcx
0x1800ce515  jz      short loc_1800CE53D
0x1800ce517  mov     rdx, [rbp+Sid]; pSid2
0x1800ce51b  call    cs:__imp_EqualSid
0x1800ce521  test    eax, eax
0x1800ce523  jnz     short loc_1800CE547
0x1800ce525  mov     ebx, 80070005h
0x1800ce52a  jmp     short loc_1800CE547
0x1800ce52c  cmp     [rbp+TokenInformation], 0
0x1800ce530  jnz     loc_1800CE48C
0x1800ce536  mov     ebx, 80070005h
0x1800ce53b  jmp     short loc_1800CE556
0x1800ce53d  mov     ebx, 8000FFFFh
0x1800ce542  test    rdi, rdi
0x1800ce545  jz      short loc_1800CE556
0x1800ce547  mov     rcx, rdi; void *
0x1800ce54a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ce54f  jmp     short loc_1800CE556
0x1800ce551  mov     ebx, 8000FFFFh
0x1800ce556  mov     rcx, [rbp+Sid]; hMem
0x1800ce55a  test    rcx, rcx
0x1800ce55d  jz      short loc_1800CE565
0x1800ce55f  call    cs:__imp_LocalFree
0x1800ce565  mov     eax, ebx
0x1800ce567  mov     rbx, [rsp+40h+arg_0]
0x1800ce56c  add     rsp, 40h
0x1800ce570  pop     rdi
0x1800ce571  pop     rsi
0x1800ce572  pop     rbp
0x1800ce573  retn
```
