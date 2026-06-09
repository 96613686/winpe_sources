# NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(_LUID *,ulong *)

- ea: `0x1800357ac`
- end: `0x1800358dd`
- name: `?GetAuthenticationIdAndIntegrity@TSidUserContext@NSecurityLibrary@@QEBAJPEAU_LUID@@PEAK@Z`
- size: `305`
- prototype: `__int64 __fastcall(NSecurityLibrary::TSidUserContext *__hidden this, struct _LUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800359b0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180018d18`
- `0x1800357ac`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800358a6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800358a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003584d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003588f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003584d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003588f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800358b7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800358b7`

## pseudocode

```c
__int64 __fastcall NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(
        NSecurityLibrary::TSidUserContext *this,
        struct _LUID *a2,
        unsigned int *a3)
{
  int LastErrorAsHResult; // ebx
  void *v7; // rcx
  PUCHAR SidSubAuthorityCount; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-79h] BYREF
  int TokenInformation; // [rsp+38h] [rbp-71h] BYREF
  __int128 v12; // [rsp+3Ch] [rbp-6Dh]
  __int128 v13; // [rsp+4Ch] [rbp-5Dh]
  __int128 v14; // [rsp+5Ch] [rbp-4Dh]
  int v15; // [rsp+6Ch] [rbp-3Dh]
  PSID pSid[12]; // [rsp+70h] [rbp-39h] BYREF

  TokenInformation = 0;
  v15 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  memset_0(pSid, 0, 0x58u);
  LastErrorAsHResult = *((_DWORD *)this + 14);
  ReturnLength = 56;
  if ( LastErrorAsHResult >= 0 )
  {
    if ( a2 && a3 )
    {
      *a2 = 0;
      *a3 = 0;
      if ( GetTokenInformation(*((HANDLE *)this + 2), TokenStatistics, &TokenInformation, 0x38u, &ReturnLength) )
      {
        LastErrorAsHResult = 0;
        *a2 = *(struct _LUID *)((char *)&v12 + 4);
      }
      else
      {
        LastErrorAsHResult = GetLastErrorAsHResult();
        if ( LastErrorAsHResult < 0 )
          return (unsigned int)LastErrorAsHResult;
      }
      v7 = (void *)*((_QWORD *)this + 2);
      ReturnLength = 88;
      if ( GetTokenInformation(v7, TokenIntegrityLevel, pSid, 0x58u, &ReturnLength) )
      {
        SidSubAuthorityCount = GetSidSubAuthorityCount(pSid[0]);
        *a3 = *GetSidSubAuthority(pSid[0], (unsigned __int8)(*SidSubAuthorityCount - 1));
      }
      else
      {
        return (unsigned int)GetLastErrorAsHResult();
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x1800357ac  push    rbp
0x1800357ae  push    rbx
0x1800357af  push    rsi
0x1800357b0  push    rdi
0x1800357b1  push    r14
0x1800357b3  lea     rbp, [rsp-37h]
0x1800357b8  sub     rsp, 0E0h
0x1800357bf  mov     rax, cs:__security_cookie
0x1800357c6  xor     rax, rsp
0x1800357c9  mov     [rbp+57h+var_30], rax
0x1800357cd  xorps   xmm0, xmm0
0x1800357d0  mov     [rbp+57h+TokenInformation], 0
0x1800357d7  xor     eax, eax
0x1800357d9  mov     rsi, r8
0x1800357dc  mov     rdi, rdx
0x1800357df  mov     [rbp+57h+var_94], eax
0x1800357e2  mov     r14, rcx
0x1800357e5  xor     edx, edx; Val
0x1800357e7  lea     rcx, [rbp+57h+pSid]; void *
0x1800357eb  lea     r8d, [rax+58h]; Size
0x1800357ef  movups  [rbp+57h+var_C4], xmm0
0x1800357f3  movups  [rbp+57h+var_B4], xmm0
0x1800357f7  movups  [rbp+57h+var_A4], xmm0
0x1800357fb  call    memset_0
0x180035800  mov     ebx, [r14+38h]
0x180035804  mov     r9d, 38h ; '8'; TokenInformationLength
0x18003580a  mov     [rbp+57h+var_D0], r9d
0x18003580e  test    ebx, ebx
0x180035810  js      loc_1800358C1
0x180035816  test    rdi, rdi
0x180035819  jz      short loc_180035820
0x18003581b  test    rsi, rsi
0x18003581e  jnz     short loc_18003582A
0x180035820  mov     ebx, 80070057h
0x180035825  jmp     loc_1800358C1
0x18003582a  mov     qword ptr [rdi], 0
0x180035831  lea     rax, [rbp+57h+var_D0]
0x180035835  mov     dword ptr [rsi], 0
0x18003583b  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18003583f  mov     rcx, [r14+10h]; TokenHandle
0x180035843  mov     edx, 0Ah; TokenInformationClass
0x180035848  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x18003584d  call    cs:__imp_GetTokenInformation
0x180035853  test    eax, eax
0x180035855  jnz     short loc_180035864
0x180035857  call    GetLastErrorAsHResult
0x18003585c  mov     ebx, eax
0x18003585e  test    eax, eax
0x180035860  js      short loc_1800358C1
0x180035862  jmp     short loc_18003586D
0x180035864  mov     rax, qword ptr [rbp+57h+var_C4+4]
0x180035868  xor     ebx, ebx
0x18003586a  mov     [rdi], rax
0x18003586d  mov     rcx, [r14+10h]; TokenHandle
0x180035871  lea     rax, [rbp+57h+var_D0]
0x180035875  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18003587b  mov     [rbp+57h+var_D0], 58h ; 'X'
0x180035882  lea     r8, [rbp+57h+pSid]; TokenInformation
0x180035886  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x18003588b  lea     edx, [r9-3Fh]; TokenInformationClass
0x18003588f  call    cs:__imp_GetTokenInformation
0x180035895  test    eax, eax
0x180035897  jnz     short loc_1800358A2
0x180035899  call    GetLastErrorAsHResult
0x18003589e  mov     ebx, eax
0x1800358a0  jmp     short loc_1800358C1
0x1800358a2  mov     rcx, [rbp+57h+pSid]; pSid
0x1800358a6  call    cs:__imp_GetSidSubAuthorityCount
0x1800358ac  mov     cl, [rax]
0x1800358ae  dec     cl
0x1800358b0  movzx   edx, cl; nSubAuthority
0x1800358b3  mov     rcx, [rbp+57h+pSid]; pSid
0x1800358b7  call    cs:__imp_GetSidSubAuthority
0x1800358bd  mov     ecx, [rax]
0x1800358bf  mov     [rsi], ecx
0x1800358c1  mov     eax, ebx
0x1800358c3  mov     rcx, [rbp+57h+var_30]
0x1800358c7  xor     rcx, rsp; StackCookie
0x1800358ca  call    __security_check_cookie
0x1800358cf  add     rsp, 0E0h
0x1800358d6  pop     r14
0x1800358d8  pop     rdi
0x1800358d9  pop     rsi
0x1800358da  pop     rbx
0x1800358db  pop     rbp
0x1800358dc  retn
```
