# LPA::Lui::ValidateOwnerUserSid(void *,ushort const *)

- ea: `0x1800cebf8`
- end: `0x1800ced0a`
- name: `?ValidateOwnerUserSid@Lui@LPA@@CAJPEAXPEBG@Z`
- size: `274`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800ce810`

## callees

- `0x18000e430`
- `0x180068c64`
- `0x18006ba8c`
- `0x1800cebf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cec65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cec65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cecf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cecf2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800cec5b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ceca1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800cec5b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ceca1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800cecca`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800cecca`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800cec2b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800cec2b`

## pseudocode

```c
__int64 __fastcall LPA::Lui::ValidateOwnerUserSid(HANDLE TokenHandle, const unsigned __int16 *a2)
{
  int LastErrorToHResultAndForceFailure; // ebx
  CommonUtil *v4; // rcx
  unsigned __int64 v5; // rdx
  CommonUtil *v6; // rcx
  PSID *v7; // rdi
  CommonUtil *v8; // rcx
  const struct std::nothrow_t *v9; // rdx
  DWORD TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF
  int v12; // [rsp+4Ch] [rbp+14h]
  PSID pSid2; // [rsp+50h] [rbp+18h] BYREF

  v12 = HIDWORD(a2);
  pSid2 = 0;
  TokenInformationLength = 0;
  LastErrorToHResultAndForceFailure = 0;
  if ( ConvertStringSidToSidW(L"S-1-5-80-1050781787-7300309-4211703609-49369207-2006124406", &pSid2)
    || (LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v4),
        LastErrorToHResultAndForceFailure >= 0) )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
LABEL_15:
      LastErrorToHResultAndForceFailure = -2147418113;
      goto LABEL_16;
    }
    if ( GetLastError() != 122 )
      LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v6);
    if ( LastErrorToHResultAndForceFailure >= 0 )
    {
      v7 = (PSID *)LPA::Util::CustomAllocator(TokenInformationLength, v5);
      if ( !GetTokenInformation(TokenHandle, TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
      {
        LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v8);
        if ( LastErrorToHResultAndForceFailure < 0 )
        {
          if ( !v7 )
            goto LABEL_16;
          goto LABEL_14;
        }
      }
      if ( v7 )
      {
        if ( !EqualSid(*v7, pSid2) )
          LastErrorToHResultAndForceFailure = -2147024891;
LABEL_14:
        operator delete(v7, v9);
        goto LABEL_16;
      }
      goto LABEL_15;
    }
  }
LABEL_16:
  if ( pSid2 )
    LocalFree(pSid2);
  return (unsigned int)LastErrorToHResultAndForceFailure;
}

```

## disassembly

```asm
0x1800cebf8  mov     rax, rsp
0x1800cebfb  mov     [rax+8], rbx
0x1800cebff  mov     [rax+20h], rsi
0x1800cec03  mov     [rax+10h], rdx
0x1800cec07  push    rdi
0x1800cec08  sub     rsp, 30h
0x1800cec0c  mov     rsi, rcx
0x1800cec0f  mov     qword ptr [rax+18h], 0
0x1800cec17  lea     rcx, StringSid; "S-1-5-80-1050781787-7300309-4211703609-"...
0x1800cec1e  mov     dword ptr [rax+10h], 0
0x1800cec25  lea     rdx, [rax+18h]; Sid
0x1800cec29  xor     ebx, ebx
0x1800cec2b  call    cs:__imp_ConvertStringSidToSidW
0x1800cec31  test    eax, eax
0x1800cec33  jnz     short loc_1800CEC44
0x1800cec35  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800cec3a  mov     ebx, eax
0x1800cec3c  test    eax, eax
0x1800cec3e  js      loc_1800CECE8
0x1800cec44  xor     r9d, r9d; TokenInformationLength
0x1800cec47  lea     rax, [rsp+38h+TokenInformationLength]
0x1800cec4c  xor     r8d, r8d; TokenInformation
0x1800cec4f  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800cec54  mov     rcx, rsi; TokenHandle
0x1800cec57  lea     edx, [r9+1]; TokenInformationClass
0x1800cec5b  call    cs:__imp_GetTokenInformation
0x1800cec61  test    eax, eax
0x1800cec63  jnz     short loc_1800CECE3
0x1800cec65  call    cs:__imp_GetLastError
0x1800cec6b  cmp     eax, 7Ah ; 'z'
0x1800cec6e  jz      short loc_1800CEC77
0x1800cec70  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800cec75  mov     ebx, eax
0x1800cec77  test    ebx, ebx
0x1800cec79  js      short loc_1800CECE8
0x1800cec7b  mov     ecx, [rsp+38h+TokenInformationLength]; Size
0x1800cec7f  call    ?CustomAllocator@Util@LPA@@YAPEAX_K@Z; LPA::Util::CustomAllocator(unsigned __int64)
0x1800cec84  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800cec89  mov     rdi, rax
0x1800cec8c  lea     rax, [rsp+38h+TokenInformationLength]
0x1800cec91  mov     r8, rdi; TokenInformation
0x1800cec94  mov     edx, 1; TokenInformationClass
0x1800cec99  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800cec9e  mov     rcx, rsi; TokenHandle
0x1800ceca1  call    cs:__imp_GetTokenInformation
0x1800ceca7  test    eax, eax
0x1800ceca9  jnz     short loc_1800CECBD
0x1800cecab  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800cecb0  mov     ebx, eax
0x1800cecb2  test    eax, eax
0x1800cecb4  jns     short loc_1800CECBD
0x1800cecb6  test    rdi, rdi
0x1800cecb9  jz      short loc_1800CECE8
0x1800cecbb  jmp     short loc_1800CECD9
0x1800cecbd  test    rdi, rdi
0x1800cecc0  jz      short loc_1800CECE3
0x1800cecc2  mov     rdx, [rsp+38h+pSid2]; pSid2
0x1800cecc7  mov     rcx, [rdi]; pSid1
0x1800cecca  call    cs:__imp_EqualSid
0x1800cecd0  test    eax, eax
0x1800cecd2  jnz     short loc_1800CECD9
0x1800cecd4  mov     ebx, 80070005h
0x1800cecd9  mov     rcx, rdi; void *
0x1800cecdc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800cece1  jmp     short loc_1800CECE8
0x1800cece3  mov     ebx, 8000FFFFh
0x1800cece8  mov     rcx, [rsp+38h+pSid2]; hMem
0x1800ceced  test    rcx, rcx
0x1800cecf0  jz      short loc_1800CECF8
0x1800cecf2  call    cs:__imp_LocalFree
0x1800cecf8  mov     rsi, [rsp+38h+arg_18]
0x1800cecfd  mov     eax, ebx
0x1800cecff  mov     rbx, [rsp+38h+arg_0]
0x1800ced04  add     rsp, 30h
0x1800ced08  pop     rdi
0x1800ced09  retn
```
